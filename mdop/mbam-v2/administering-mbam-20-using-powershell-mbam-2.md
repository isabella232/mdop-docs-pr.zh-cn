---
title: 使用 PowerShell 管理 MBAM 2.0
description: 使用 PowerShell 管理 MBAM 2.0
author: dansimp
ms.assetid: d785a8df-0a8c-4d70-abd2-93a762b4f3de
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 736943e707b5d033b8ba6c26641393f02f0cdaf8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803381"
---
# <span data-ttu-id="da980-103">使用 PowerShell 管理 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="da980-103">Administering MBAM 2.0 Using PowerShell</span></span>


<span data-ttu-id="da980-104">Microsoft BitLocker 管理和监视（MBAM）提供以下列出的一组 Windows PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="da980-104">Microsoft BitLocker Administration and Monitoring (MBAM) provides the following listed set of Windows PowerShell cmdlets.</span></span> <span data-ttu-id="da980-105">管理员可以使用这些 PowerShell cmdlet 从命令行执行各种 Microsoft BitLocker 管理和监视服务器任务，而不是从 MBAM 管理网站执行。</span><span class="sxs-lookup"><span data-stu-id="da980-105">Administrators can use these PowerShell cmdlets to perform various Microsoft BitLocker Administration and Monitoring server tasks from the command line rather than from the MBAM administration website.</span></span>

## <span data-ttu-id="da980-106">如何使用 PowerShell 管理 MBAM</span><span class="sxs-lookup"><span data-stu-id="da980-106">How to Administer MBAM Using PowerShell</span></span>


<span data-ttu-id="da980-107">使用此处介绍的 PowerShell cmdlet 管理 MBAM。</span><span class="sxs-lookup"><span data-stu-id="da980-107">Use the PowerShell cmdlets described here to administer MBAM.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="da980-108">名称</span><span class="sxs-lookup"><span data-stu-id="da980-108">Name</span></span></th>
<th align="left"><span data-ttu-id="da980-109">描述</span><span class="sxs-lookup"><span data-stu-id="da980-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="da980-110">安装-Mbam</span><span class="sxs-lookup"><span data-stu-id="da980-110">Install-Mbam</span></span></p></td>
<td align="left"><p><span data-ttu-id="da980-111">安装提供高级策略、加密、密钥恢复和合规性报告的 MBAM 功能。</span><span class="sxs-lookup"><span data-stu-id="da980-111">Installs the MBAM features that provide advanced policy, encryption, key recovery, and compliance reporting.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="da980-112">卸载-Mbam</span><span class="sxs-lookup"><span data-stu-id="da980-112">Uninstall-Mbam</span></span></p></td>
<td align="left"><p><span data-ttu-id="da980-113">删除提供高级策略、加密、密钥恢复和合规性报告工具的 MBAM 功能。</span><span class="sxs-lookup"><span data-stu-id="da980-113">Removes the MBAM features that provide advanced policy, encryption, key recovery, and compliance reporting tools.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="da980-114">MbamBitLockerRecoveryKey</span><span class="sxs-lookup"><span data-stu-id="da980-114">Get-MbamBitLockerRecoveryKey</span></span></p></td>
<td align="left"><p><span data-ttu-id="da980-115">请求可使用户解锁计算机或加密驱动器的 MBAM 恢复密钥。</span><span class="sxs-lookup"><span data-stu-id="da980-115">Requests an MBAM recovery key that will enable users to unlock a computer or encrypted drive.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="da980-116">MbamTPMOwnerPassword</span><span class="sxs-lookup"><span data-stu-id="da980-116">Get-MbamTPMOwnerPassword</span></span></p></td>
<td align="left"><p><span data-ttu-id="da980-117">向用户提供 TPM 所有者密码，这些密码可用于在 TPM 已锁定并将不再接受其 PIN 时解锁受信任的平台模块（TPM）。</span><span class="sxs-lookup"><span data-stu-id="da980-117">Provides users with a TPM owner password that they can use to unlock a Trusted Platform Module (TPM) when the TPM has locked them out and will no longer accept their PIN.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="da980-118">相关主题</span><span class="sxs-lookup"><span data-stu-id="da980-118">Related topics</span></span>


[<span data-ttu-id="da980-119">MBAM 2.0 的操作</span><span class="sxs-lookup"><span data-stu-id="da980-119">Operations for MBAM 2.0</span></span>](operations-for-mbam-20-mbam-2.md)

 

 





