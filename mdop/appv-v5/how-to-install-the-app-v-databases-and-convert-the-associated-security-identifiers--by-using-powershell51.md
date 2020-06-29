---
title: 如何使用 PowerShell 安装 app-v 数据库并转换关联的安全标识符
description: 如何使用 PowerShell 安装 app-v 数据库并转换关联的安全标识符
author: dansimp
ms.assetid: 2be6fb72-f3a6-4550-bba1-6defa78ca08a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 39651df4d62971e39c4228ffce665386d5c9769d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798445"
---
# <span data-ttu-id="94c3c-103">如何使用 PowerShell 安装 app-v 数据库并转换关联的安全标识符</span><span class="sxs-lookup"><span data-stu-id="94c3c-103">How to Install the App-V Databases and Convert the Associated Security Identifiers by Using PowerShell</span></span>

<span data-ttu-id="94c3c-104">使用以下 PowerShell 过程将任意数量的 Active Directory 域服务（AD DS）用户或计算机帐户转换为采用标准格式的格式安全标识符（Sid）和 Microsoft SQL Server 在运行 SQL 脚本时使用的十六进制格式。</span><span class="sxs-lookup"><span data-stu-id="94c3c-104">Use the following PowerShell procedure to convert any number of Active Directory Domain Services (AD DS) user or machine accounts into formatted Security Identifiers (SIDs) both in the standard format and in the hexadecimal format used by Microsoft SQL Server when running SQL scripts.</span></span>

<span data-ttu-id="94c3c-105">在尝试执行此过程之前，应阅读并理解下表中显示的信息和示例：</span><span class="sxs-lookup"><span data-stu-id="94c3c-105">Before attempting this procedure, you should read and understand the information and examples displayed in the following list:</span></span>

- <span data-ttu-id="94c3c-106">**.输入**-用于转换为 SID 格式的帐户或帐户。</span><span class="sxs-lookup"><span data-stu-id="94c3c-106">**.INPUTS** – The account or accounts used to convert to SID format.</span></span> <span data-ttu-id="94c3c-107">这可以是单个帐户名称或帐户名称的数组。</span><span class="sxs-lookup"><span data-stu-id="94c3c-107">This can be a single account name or an array of account names.</span></span>

- <span data-ttu-id="94c3c-108">**.输出**-包含标准和十六进制格式的相应 SID 的帐户名称列表。</span><span class="sxs-lookup"><span data-stu-id="94c3c-108">**.OUTPUTS** - A list of account names with the corresponding SID in standard and hexadecimal formats.</span></span>

- <span data-ttu-id="94c3c-109">**说明** -</span><span class="sxs-lookup"><span data-stu-id="94c3c-109">**Examples** -</span></span>

    <span data-ttu-id="94c3c-110">**.\\ConvertToSID.ps1 DOMAIN\\user\ _account1 DOMAIN\\machine\ _account1 $ DOMAIN\\user\ _account2 |"格式"-列表**。</span><span class="sxs-lookup"><span data-stu-id="94c3c-110">**.\\ConvertToSID.ps1 DOMAIN\\user\_account1 DOMAIN\\machine\_account1$ DOMAIN\\user\_account2 | Format-List**.</span></span>

    **<span data-ttu-id="94c3c-111">$accountsArray = @ （"DOMAIN\\user\ _account1"，"DOMAIN\\machine\ _account1 $"，"DOMAIN \ _user \ _account2"）</span><span class="sxs-lookup"><span data-stu-id="94c3c-111">$accountsArray = @("DOMAIN\\user\_account1", "DOMAIN\\machine\_account1$", "DOMAIN\_user\_account2")</span></span>**

    **<span data-ttu-id="94c3c-112">.\\ConvertToSID.ps1 $accountsArray |写入输出-FilePath .\\SIDs.txt-Width 200</span><span class="sxs-lookup"><span data-stu-id="94c3c-112">.\\ConvertToSID.ps1 $accountsArray | Write-Output -FilePath .\\SIDs.txt -Width 200</span></span>**

## <span data-ttu-id="94c3c-113">将任意数量的 Active Directory 域服务（AD DS）用户或计算机帐户转换为已设置格式的安全标识符（Sid）</span><span class="sxs-lookup"><span data-stu-id="94c3c-113">To convert any number of Active Directory Domain Services (AD DS) user or machine accounts into formatted Security Identifiers (SIDs)</span></span>

1. <span data-ttu-id="94c3c-114">将以下脚本复制到文本编辑器中，并将其另存为 PowerShell 脚本文件，例如**ConvertToSIDs.ps1**。</span><span class="sxs-lookup"><span data-stu-id="94c3c-114">Copy the following script into a text editor and save it as a PowerShell script file, for example **ConvertToSIDs.ps1**.</span></span>
1. <span data-ttu-id="94c3c-115">若要打开 PowerShell 控制台，请单击 "**开始**"，然后键入**powershell**。</span><span class="sxs-lookup"><span data-stu-id="94c3c-115">To open a PowerShell console click **Start** and type **PowerShell**.</span></span> <span data-ttu-id="94c3c-116">右键单击**Windows PowerShell**，然后选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="94c3c-116">Right-click **Windows PowerShell** and select **Run as Administrator**.</span></span>

   ```powershell
   <#
   .SYNOPSIS
   This PowerShell script will take an array of account names and try to convert each of them to the corresponding SID in standard and hexadecimal formats.
   .DESCRIPTION
   This is a PowerShell script that converts any number of Active Directory (AD) user or machine accounts into formatted Security Identifiers (SIDs) both in the standard format and in the hexadecimal format used by SQL server when running SQL scripts.
   .INPUTS
   The account(s) to convert to SID format. This can be a single account name or an array of account names. Please see examples below.
   .OUTPUTS
   A list of account names with the corresponding SID in standard and hexadecimal formats
   .EXAMPLE
   .\ConvertToSID.ps1 DOMAIN\user_account1 DOMAIN\machine_account1$ DOMAIN\user_account2 | Format-List
   .EXAMPLE
   $accountsArray = @("DOMAIN\user_account1", "DOMAIN\machine_account1$", "DOMAIN_user_account2")
   .\ConvertToSID.ps1 $accountsArray | Write-Output -FilePath .\SIDs.txt -Width 200
   #>

   function ConvertSIDToHexFormat
   {

      param([System.Security.Principal.SecurityIdentifier]$sidToConvert)

      $sb = New-Object System.Text.StringBuilder
      [int] $binLength = $sidToConvert.BinaryLength
      [Byte[]] $byteArray = New-Object Byte[] $binLength
      $sidToConvert.GetBinaryForm($byteArray, 0)
      foreach($byte in $byteArray)
      {
          $sb.Append($byte.ToString("X2")) |Out-Null
      }
      return $sb.ToString()
   }
    [string[]]$myArgs = $args
   if(($myArgs.Length -lt 1) -or ($myArgs[0].CompareTo("/?") -eq 0))
   {

    [string]::Format("{0}====== Description ======{0}{0}" +
                  "  Converts any number of user or machine account names to string and hexadecimal SIDs.{0}" +
                  "  Pass the account(s) as space separated command line parameters. (For example 'ConvertToSID.ps1 DOMAIN\Account1 DOMAIN\Account2 ...'){0}" +
                  "  The output is written to the console in the format 'Account name    SID as string   SID as hexadecimal'{0}" +
                  "  And can be written out to a file using standard PowerShell redirection{0}" +
                  "  Please specify user accounts in the format 'DOMAIN\username'{0}" +
                  "  Please specify machine accounts in the format 'DOMAIN\machinename$'{0}" +
                  "  For more help content, please run 'Get-Help ConvertToSID.ps1'{0}" +
                  "{0}====== Arguments ======{0}" +
                  "{0}  /?    Show this help message", [Environment]::NewLine)
   }
   else
   {
       #If an array was passed in, try to split it
       if($myArgs.Length -eq 1)
       {
           $myArgs = $myArgs.Split(' ')
       }

       #Parse the arguments for account names
       foreach($accountName in $myArgs)
       {
           [string[]] $splitString = $accountName.Split('\')  # We're looking for the format "DOMAIN\Account" so anything that does not match, we reject
           if($splitString.Length -ne 2)
           {
               $message = [string]::Format("{0} is not a valid account name. Expected format 'Domain\username' for user accounts or 'DOMAIN\machinename$' for machine accounts.", $accountName)
               Write-Error -Message $message
               continue
           }

           #Convert any account names to SIDs
           try
           {
               [System.Security.Principal.NTAccount] $account = New-Object System.Security.Principal.NTAccount($splitString[0], $splitString[1])
               [System.Security.Principal.SecurityIdentifier] $SID = [System.Security.Principal.SecurityIdentifier]($account.Translate([System.Security.Principal.SecurityIdentifier]))
           }
           catch [System.Security.Principal.IdentityNotMappedException]
           {
               $message = [string]::Format("Failed to translate account object '{0}' to a SID. Please verify that this is a valid user or machine account.", $account.ToString())
               Write-Error -Message $message
               continue
           }

           #Convert regular SID to binary format used by SQL
           $hexSIDString = ConvertSIDToHexFormat $SID

           $SIDs = New-Object PSObject
           $SIDs | Add-Member NoteProperty Account $accountName
           $SIDs | Add-Member NoteProperty SID $SID.ToString()
           $SIDs | Add-Member NoteProperty Hexadecimal $hexSIDString

           Write-Output $SIDs
       }
   }
   ```

1. <span data-ttu-id="94c3c-117">运行步骤1中保存的脚本，该过程将传递要转换为参数的帐户。</span><span class="sxs-lookup"><span data-stu-id="94c3c-117">Run the script you saved in step one of this procedure passing the accounts to convert as arguments.</span></span>

   <span data-ttu-id="94c3c-118">例如，</span><span class="sxs-lookup"><span data-stu-id="94c3c-118">For example,</span></span>

   **<span data-ttu-id="94c3c-119">.\\ConvertToSID.ps1 DOMAIN\\user\ _account1 DOMAIN\\machine\ _account1 $ DOMAIN\\user\ _account2 |格式-列表</span><span class="sxs-lookup"><span data-stu-id="94c3c-119">.\\ConvertToSID.ps1 DOMAIN\\user\_account1 DOMAIN\\machine\_account1$ DOMAIN\\user\_account2 | Format-List</span></span>**
   
   <span data-ttu-id="94c3c-120">或者</span><span class="sxs-lookup"><span data-stu-id="94c3c-120">or</span></span>
   
   <span data-ttu-id="94c3c-121">**$accountsArray = @ （"DOMAIN\\user\ _account1"，"DOMAIN\\machine\ _account1 $"，"DOMAIN \ _user \ _account2"）** 
    **.\\ConvertToSID.ps1 $accountsArray |写入输出-FilePath .\\SIDs.txt-Width 200**</span><span class="sxs-lookup"><span data-stu-id="94c3c-121">**$accountsArray = @("DOMAIN\\user\_account1", "DOMAIN\\machine\_account1$", "DOMAIN\_user\_account2")**
 **.\\ConvertToSID.ps1 $accountsArray | Write-Output -FilePath .\\SIDs.txt -Width 200**</span></span>

**<span data-ttu-id="94c3c-122">遇到了 app-v 问题？</span><span class="sxs-lookup"><span data-stu-id="94c3c-122">Got an App-V issue?</span></span>** <span data-ttu-id="94c3c-123">使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="94c3c-123">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="94c3c-124">相关主题</span><span class="sxs-lookup"><span data-stu-id="94c3c-124">Related topics</span></span>

[<span data-ttu-id="94c3c-125">使用 PowerShell 管理 App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="94c3c-125">Administering App-V 5.1 by Using PowerShell</span></span>](administering-app-v-51-by-using-powershell.md)
