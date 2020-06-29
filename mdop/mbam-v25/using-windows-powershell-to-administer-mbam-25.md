---
title: 使用 Windows PowerShell 管理 MBAM 2.5
description: 使用 Windows PowerShell 管理 MBAM 2.5
author: dansimp
ms.assetid: 64668e76-2cba-433d-8d2d-50df0a4b2997
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 11/02/2016
ms.openlocfilehash: 8db305bfbdf79723da2b186dd5cc00406a4089cc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798120"
---
# <span data-ttu-id="740df-103">使用 Windows PowerShell 管理 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="740df-103">Using Windows PowerShell to Administer MBAM 2.5</span></span>


<span data-ttu-id="740df-104">本主题介绍 Microsoft BitLocker 管理和监视（MBAM）的 Windows PowerShell cmdlet，这些 cmdlet 与用户锁定时恢复计算机或驱动器相关。</span><span class="sxs-lookup"><span data-stu-id="740df-104">This topic describes Windows PowerShell cmdlets for Microsoft BitLocker Administration and Monitoring (MBAM) that relate to recovering computers or drives when users get locked out.</span></span>

<span data-ttu-id="740df-105">对于用于配置 MBAM 服务器功能的 cmdlet，请参阅[使用 Windows PowerShell 配置 MBAM 2.5 服务器功能](configuring-mbam-25-server-features-by-using-windows-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="740df-105">For cmdlets that you use to configure MBAM Server features, see [Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md).</span></span>

## <a href="" id="cmdlets-for-recovering-computers-or-drives-that-are-managed-by-mbam-"></a><span data-ttu-id="740df-106">用于恢复由 MBAM 托管的计算机或驱动器的 cmdlet</span><span class="sxs-lookup"><span data-stu-id="740df-106">Cmdlets for recovering computers or drives that are managed by MBAM</span></span>


<span data-ttu-id="740df-107">使用以下 Windows PowerShell cmdlet 恢复由 MBAM 托管的计算机或驱动器。</span><span class="sxs-lookup"><span data-stu-id="740df-107">Use the following Windows PowerShell cmdlets to recover computers or drives that are managed by MBAM.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="740df-108">名称</span><span class="sxs-lookup"><span data-stu-id="740df-108">Name</span></span></th>
<th align="left"><span data-ttu-id="740df-109">描述</span><span class="sxs-lookup"><span data-stu-id="740df-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="740df-110">MbamBitLockerRecoveryKey</span><span class="sxs-lookup"><span data-stu-id="740df-110">Get-MbamBitLockerRecoveryKey</span></span></p></td>
<td align="left"><p><span data-ttu-id="740df-111">请求允许用户解锁计算机或加密驱动器的 MBAM 恢复密钥。</span><span class="sxs-lookup"><span data-stu-id="740df-111">Requests an MBAM recovery key that enables users to unlock a computer or encrypted drive.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="740df-112">MbamTPMOwnerPassword</span><span class="sxs-lookup"><span data-stu-id="740df-112">Get-MbamTPMOwnerPassword</span></span></p></td>
<td align="left"><p><span data-ttu-id="740df-113">向用户提供 TPM 所有者密码，这些密码可用于在 TPM 已锁定并将不再接受其 PIN 时解锁受信任的平台模块（TPM）。</span><span class="sxs-lookup"><span data-stu-id="740df-113">Provides users with a TPM owner password that they can use to unlock a Trusted Platform Module (TPM) when the TPM has locked them out and will no longer accept their PIN.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="---------mbam-cmdlet-help"></a> <span data-ttu-id="740df-114">MBAM cmdlet 帮助</span><span class="sxs-lookup"><span data-stu-id="740df-114">MBAM cmdlet Help</span></span>


<span data-ttu-id="740df-115">适用于 MBAM cmdlet 的 Windows PowerShell 帮助采用以下格式：</span><span class="sxs-lookup"><span data-stu-id="740df-115">Windows PowerShell Help for MBAM cmdlets is available in the following formats:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="740df-116">Windows PowerShell 帮助格式</span><span class="sxs-lookup"><span data-stu-id="740df-116">Windows PowerShell Help format</span></span></th>
<th align="left"><span data-ttu-id="740df-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="740df-117">More information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="740df-118">在 Windows PowerShell 命令提示符处，键入 <strong> get-help </strong> &lt; <em> cmdlet</em>&gt;</span><span class="sxs-lookup"><span data-stu-id="740df-118">At a Windows PowerShell command prompt, type <strong>Get-Help</strong> &lt;<em>cmdlet</em>&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="740df-119">若要上载最新的 Windows PowerShell cmdlet，请按照 <a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)"> 使用 Windows PowerShell 配置 MBAM 2.5 服务器功能中的说明进行操作</span><span class="sxs-lookup"><span data-stu-id="740df-119">To upload the latest Windows PowerShell cmdlets, follow the instructions in <a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)">Configuring MBAM 2.5 Server Features by Using Windows PowerShell</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="740df-120">在 TechNet 上作为网页</span><span class="sxs-lookup"><span data-stu-id="740df-120">On TechNet as webpages</span></span></p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393498" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393498">https://go.microsoft.com/fwlink/?LinkId=393498</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="740df-121">在下载中心中作为单词表文件</span><span class="sxs-lookup"><span data-stu-id="740df-121">On the Download Center as a Word .docx file</span></span></p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393497" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393497">https://go.microsoft.com/fwlink/?LinkId=393497</a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="740df-122">在下载中心中作为 .pdf 文件</span><span class="sxs-lookup"><span data-stu-id="740df-122">On the Download Center as a .pdf file</span></span></p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393499" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393499">https://go.microsoft.com/fwlink/?LinkId=393499</a></p></td>
</tr>
</tbody>
</table>

 



## <span data-ttu-id="740df-123">相关主题</span><span class="sxs-lookup"><span data-stu-id="740df-123">Related topics</span></span>


[<span data-ttu-id="740df-124">管理 MBAM 2.5 功能</span><span class="sxs-lookup"><span data-stu-id="740df-124">Administering MBAM 2.5 Features</span></span>](administering-mbam-25-features.md)

[<span data-ttu-id="740df-125">使用 Windows PowerShell 配置 MBAM 2.5 服务器功能</span><span class="sxs-lookup"><span data-stu-id="740df-125">Configuring MBAM 2.5 Server Features by Using Windows PowerShell</span></span>](configuring-mbam-25-server-features-by-using-windows-powershell.md)

 

## <span data-ttu-id="740df-126">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="740df-126">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="740df-127">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="740df-127">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="740df-128">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="740df-128">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





