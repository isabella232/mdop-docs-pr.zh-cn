---
title: 使用 Windows PowerShell 配置高级设置
description: 使用 Windows PowerShell 配置高级设置
author: dansimp
ms.assetid: 437a31cc-2a11-456f-b448-b0b869fb53f7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 45a3ece3f76f6e982913aad2b25cfe0084542f32
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804159"
---
# <span data-ttu-id="ba7fa-103">使用 Windows PowerShell 配置高级设置</span><span class="sxs-lookup"><span data-stu-id="ba7fa-103">Configuring Advanced Settings by Using Windows PowerShell</span></span>


<span data-ttu-id="ba7fa-104">你创建的 MED-V 工作区程序包包括可在测试和部署 MED-V 工作区程序包之前进行编辑的 Windows PowerShell 脚本（ps1）文件。</span><span class="sxs-lookup"><span data-stu-id="ba7fa-104">The MED-V workspace package that you create includes a Windows PowerShell script (.ps1) file that you can edit before you test and deploy your MED-V workspace package.</span></span> <span data-ttu-id="ba7fa-105">本部分提供的信息和指南可帮助你在部署 MED-V 工作区之前使用 Windows PowerShell 管理 MED-V 配置设置。</span><span class="sxs-lookup"><span data-stu-id="ba7fa-105">This section provides information and guidance to help you manage MED-V configuration settings by using Windows PowerShell before you deploy the MED-V workspaces.</span></span>

## <span data-ttu-id="ba7fa-106">在 MED-V 中使用 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="ba7fa-106">Using Windows PowerShell Cmdlets in MED-V</span></span>


<span data-ttu-id="ba7fa-107">Microsoft 企业版虚拟化（MED-V）2.0 中提供了以下 Windows PowerShell cmdlet：</span><span class="sxs-lookup"><span data-stu-id="ba7fa-107">The following Windows PowerShell cmdlets are available in Microsoft Enterprise Desktop Virtualization (MED-V) 2.0:</span></span>

**<span data-ttu-id="ba7fa-108">新-MedvConfiguration</span><span class="sxs-lookup"><span data-stu-id="ba7fa-108">New-MedvConfiguration</span></span>**

**<span data-ttu-id="ba7fa-109">Export-MedvConfiguration</span><span class="sxs-lookup"><span data-stu-id="ba7fa-109">Export-MedvConfiguration</span></span>**

**<span data-ttu-id="ba7fa-110">新-MedvWorkspace</span><span class="sxs-lookup"><span data-stu-id="ba7fa-110">New-MedvWorkspace</span></span>**

**<span data-ttu-id="ba7fa-111">Export-MedvWorkspace</span><span class="sxs-lookup"><span data-stu-id="ba7fa-111">Export-MedvWorkspace</span></span>**

<span data-ttu-id="ba7fa-112">若要访问 MED-V 的 Windows PowerShell cmdlet，请打开 Windows PowerShell 并键入以下命令以导入 MED-V 模块。</span><span class="sxs-lookup"><span data-stu-id="ba7fa-112">To access Windows PowerShell cmdlets for MED-V, open Windows PowerShell and type the following command to import the MED-V modules.</span></span>

``` syntax
Import-Module microsoft.medv
```

<span data-ttu-id="ba7fa-113">导入模块后，您可以通过使用标准的 Windows PowerShell 帮助命令、 **man**或**get-help**来访问 cmdlet 的内联帮助。</span><span class="sxs-lookup"><span data-stu-id="ba7fa-113">After the modules are imported, you can access inline help for the cmdlets by using the standard Windows PowerShell Help commands, **man** or **get-help**.</span></span> <span data-ttu-id="ba7fa-114">例如，若要访问**MedvConfiguration** cmdlet 的描述，包括可用参数的完整列表，请键入以下命令。</span><span class="sxs-lookup"><span data-stu-id="ba7fa-114">For example, to access a description of the **New-MedvConfiguration** cmdlet including a complete list of available parameters, type the following command.</span></span>

``` syntax
get-help New-MedvConfiguration
```

<span data-ttu-id="ba7fa-115">您还可以查看特定参数的帮助。</span><span class="sxs-lookup"><span data-stu-id="ba7fa-115">You can also view help for specific parameters.</span></span> <span data-ttu-id="ba7fa-116">例如，若要查看参数 VmMemory 的帮助，请键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="ba7fa-116">For example, to view help for the parameter VmMemory, type the following:</span></span>

``` syntax
get-help New-MedvConfiguration -parameter VmMemory
```

<span data-ttu-id="ba7fa-117">若要查看所有 MED-V 配置设置及其默认设置的列表，请键入以下命令。</span><span class="sxs-lookup"><span data-stu-id="ba7fa-117">To view a list of all MED-V configuration settings and their defaults, type the following command.</span></span>

``` syntax
New-MedvConfiguration -ForceDefaults
```

<span data-ttu-id="ba7fa-118">若要查看所有 MED-V 配置设置及其当前值的列表，请键入以下命令。</span><span class="sxs-lookup"><span data-stu-id="ba7fa-118">To view a list of all MED-V configuration settings and their current values, type the following command.</span></span>

``` syntax
gwmi -Class "Setting” -Namespace "root/microsoft/medv”
```

## <span data-ttu-id="ba7fa-119">使用自定义设置创建 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="ba7fa-119">Creating a MED-V Workspace with Custom Settings</span></span>


<span data-ttu-id="ba7fa-120">使用 MED-V 工作区包装程序成功创建 MED-V 工作区程序包后，在指定用于保存包装程序文件的文件夹中生成 Windows PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="ba7fa-120">After you successfully create a MED-V workspace package by using the MED-V Workspace Packager, a Windows PowerShell script is generated in the folder you specified for saving your packager files.</span></span> <span data-ttu-id="ba7fa-121">此脚本的内容显示一些可以编辑的可用 MED-V 配置设置。</span><span class="sxs-lookup"><span data-stu-id="ba7fa-121">The contents of this script show some of the available MED-V configuration settings that you can edit.</span></span>

<span data-ttu-id="ba7fa-122">执行这些步骤后，你可以自定义脚本，然后在 Windows PowerShell 中运行它，以使用新设置创建 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="ba7fa-122">Following these steps, you can customize the script and then run it in Windows PowerShell to create a MED-V workspace with the new settings.</span></span>

<span data-ttu-id="ba7fa-123">**重要提示** 通过管理凭据运行 Windows PowerShell，并确保 Windows PowerShell 执行策略允许运行脚本。</span><span class="sxs-lookup"><span data-stu-id="ba7fa-123">**Important** Run Windows PowerShell with administrative credentials, and ensure that the Windows PowerShell execution policy allows the running of scripts.</span></span>

1.  <span data-ttu-id="ba7fa-124">编辑由 MED-V 工作区包装程序生成的 Windows PowerShell 脚本，或使用所需的配置设置创作新脚本。</span><span class="sxs-lookup"><span data-stu-id="ba7fa-124">Edit the Windows PowerShell script that was generated by the MED-V Workspace Packager, or author a new script with the configuration settings that you want.</span></span>

2.  <span data-ttu-id="ba7fa-125">通过管理凭据运行 Windows PowerShell，然后在命令提示符处键入以下命令。</span><span class="sxs-lookup"><span data-stu-id="ba7fa-125">Run Windows PowerShell with administrative credentials and at the command prompt, type the following command.</span></span>

    ``` syntax
    & “.\<workspacename>.ps1”
    ```

    <span data-ttu-id="ba7fa-126">此命令运行 Windows PowerShell 脚本并运行 MedvWorkspace cmdlet 以生成新**的**med-v 工作区程序包。</span><span class="sxs-lookup"><span data-stu-id="ba7fa-126">This command runs the Windows PowerShell script and runs the **New-MedvWorkspace** cmdlet to generate a new MED-V workspace package.</span></span> <span data-ttu-id="ba7fa-127">新的包装程序文件将保存在最初指定用于存储 MED-V 工作区包装程序文件的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="ba7fa-127">The new packager files are saved in the folder that you originally specified for storing your MED-V Workspace Packager files.</span></span> <span data-ttu-id="ba7fa-128">有关此 cmdlet 的其他帮助，请参阅 Windows PowerShell 帮助。</span><span class="sxs-lookup"><span data-stu-id="ba7fa-128">For additional help about this cmdlet, see the Windows PowerShell Help.</span></span>

 

## <span data-ttu-id="ba7fa-129">将 MED-V 配置导出到注册表文件</span><span class="sxs-lookup"><span data-stu-id="ba7fa-129">Exporting a MED-V Configuration to a Registry File</span></span>


<span data-ttu-id="ba7fa-130">在安装 MED-V 工作区后，您可以更新 MED-V 配置设置。</span><span class="sxs-lookup"><span data-stu-id="ba7fa-130">You can update MED-V configuration settings after the MED-V workspace is installed.</span></span> <span data-ttu-id="ba7fa-131">使用**MedvConfiguration** cmdlet 指定要更改的参数。</span><span class="sxs-lookup"><span data-stu-id="ba7fa-131">Use the **New-MedvConfiguration** cmdlet to specify the parameters that you want to change.</span></span> <span data-ttu-id="ba7fa-132">例如，若要创建可更改虚拟机内存设置的注册表文件，请键入以下命令。</span><span class="sxs-lookup"><span data-stu-id="ba7fa-132">For example, to create a registry file that changes the virtual machine memory setting, type the following commands.</span></span>

``` syntax
New-MedvConfiguration  -VmMemory 1024 | Export-MedvConfiguration -Path c:\medvConfiguration\myConfig.reg
```

<span data-ttu-id="ba7fa-133">你可以将最终的注册表文件从主机计算机导入到 MED-V 工作区，以应用新的配置设置。</span><span class="sxs-lookup"><span data-stu-id="ba7fa-133">You can import the resultant registry file from the host computer to a MED-V workspace to apply the new configuration settings.</span></span>

## <span data-ttu-id="ba7fa-134">相关主题</span><span class="sxs-lookup"><span data-stu-id="ba7fa-134">Related topics</span></span>


[<span data-ttu-id="ba7fa-135">管理 MED-V 工作区配置设置</span><span class="sxs-lookup"><span data-stu-id="ba7fa-135">Managing MED-V Workspace Configuration Settings</span></span>](managing-med-v-workspace-configuration-settings.md)

[<span data-ttu-id="ba7fa-136">测试和部署 MED-V 工作区程序包</span><span class="sxs-lookup"><span data-stu-id="ba7fa-136">Test And Deploy the MED-V Workspace Package</span></span>](test-and-deploy-the-med-v-workspace-package.md)

 

 





