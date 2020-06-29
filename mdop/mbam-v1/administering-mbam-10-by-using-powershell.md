---
title: 使用 PowerShell 管理 MBAM 1.0
description: 使用 PowerShell 管理 MBAM 1.0
author: dansimp
ms.assetid: 3bf2eca5-4ab7-4e84-9e80-c0c7d709647b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3547bee9b2efc58252bb6f0a1cb0aa4c484e4e80
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803708"
---
# <span data-ttu-id="40902-103">使用 PowerShell 管理 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="40902-103">Administering MBAM 1.0 by Using PowerShell</span></span>


<span data-ttu-id="40902-104">Microsoft BitLocker 管理和监视（MBAM）提供以下列出的一组 Windows PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="40902-104">Microsoft BitLocker Administration and Monitoring (MBAM) provides the following listed set of Windows PowerShell cmdlets.</span></span> <span data-ttu-id="40902-105">管理员可以使用这些 PowerShell cmdlet 从命令提示符处而不是 MBAM 管理网站执行各种 MBAM 服务器任务。</span><span class="sxs-lookup"><span data-stu-id="40902-105">Administrators can use these PowerShell cmdlets to perform various MBAM server tasks from the command prompt rather than from the MBAM administration website.</span></span>

## <span data-ttu-id="40902-106">如何使用 PowerShell 管理 MBAM</span><span class="sxs-lookup"><span data-stu-id="40902-106">How to administer MBAM by using PowerShell</span></span>


<span data-ttu-id="40902-107">使用此处介绍的 PowerShell cmdlet 管理 MBAM。</span><span class="sxs-lookup"><span data-stu-id="40902-107">Use the PowerShell cmdlets described here to administer MBAM.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="40902-108">名称</span><span class="sxs-lookup"><span data-stu-id="40902-108">Name</span></span></th>
<th align="left"><span data-ttu-id="40902-109">描述</span><span class="sxs-lookup"><span data-stu-id="40902-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="40902-110">Add-MbamHardwareType</span><span class="sxs-lookup"><span data-stu-id="40902-110">Add-MbamHardwareType</span></span></p></td>
<td align="left"><p><span data-ttu-id="40902-111">将新硬件模型添加到 MBAM 硬件清单。</span><span class="sxs-lookup"><span data-stu-id="40902-111">Adds a new hardware model to the MBAM hardware inventory.</span></span> <span data-ttu-id="40902-112">此 cmdlet 还可指定 BitLocker 驱动器加密是否支持或不支持硬件。</span><span class="sxs-lookup"><span data-stu-id="40902-112">This cmdlet can also specify whether the hardware is supported or unsupported for BitLocker drive encryption.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="40902-113">MbamBitLockerRecoveryKey</span><span class="sxs-lookup"><span data-stu-id="40902-113">Get-MbamBitLockerRecoveryKey</span></span></p></td>
<td align="left"><p><span data-ttu-id="40902-114">请求将使用户能够解锁计算机或加密驱动器的 MBAM 恢复密钥。</span><span class="sxs-lookup"><span data-stu-id="40902-114">Requests an MBAM recovery key that will enable a user to unlock a computer or encrypted drive.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="40902-115">MbamHardwareType</span><span class="sxs-lookup"><span data-stu-id="40902-115">Get-MbamHardwareType</span></span></p></td>
<td align="left"><p><span data-ttu-id="40902-116">获取包含指示硬件模型是否兼容或与 BitLocker 驱动器加密不兼容的数据的主硬件清单。</span><span class="sxs-lookup"><span data-stu-id="40902-116">Gets a master hardware inventory that contains data that indicates whether hardware models are compatible or incompatible with BitLocker drive encryption.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="40902-117">MbamTPMOwnerPassword</span><span class="sxs-lookup"><span data-stu-id="40902-117">Get-MbamTPMOwnerPassword</span></span></p></td>
<td align="left"><p><span data-ttu-id="40902-118">为用户提供 TPM 所有者密码以管理其 TPM （受信任的平台模块）访问。</span><span class="sxs-lookup"><span data-stu-id="40902-118">Provides a TPM owner password for a user to manage their TPM (Trusted Platform Module) access.</span></span> <span data-ttu-id="40902-119">当 TPM 已锁定并将不再接受其 PIN 时，可帮助用户。</span><span class="sxs-lookup"><span data-stu-id="40902-119">Helps users when TPM has locked them out and will no longer accept their PIN.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="40902-120">安装-Mbam</span><span class="sxs-lookup"><span data-stu-id="40902-120">Install-Mbam</span></span></p></td>
<td align="left"><p><span data-ttu-id="40902-121">安装提供高级组策略、加密、密钥恢复和合规性报告工具的 MBAM 功能。</span><span class="sxs-lookup"><span data-stu-id="40902-121">Installs MBAM features that provide advanced group policy, encryption, key recovery, and compliance reporting tools.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="40902-122">Remove-MbamHardwareType</span><span class="sxs-lookup"><span data-stu-id="40902-122">Remove-MbamHardwareType</span></span></p></td>
<td align="left"><p><span data-ttu-id="40902-123">从硬件清单中删除硬件型号。</span><span class="sxs-lookup"><span data-stu-id="40902-123">Removes the hardware models from the hardware inventory.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="40902-124">Set-MbamHardwareType</span><span class="sxs-lookup"><span data-stu-id="40902-124">Set-MbamHardwareType</span></span></p></td>
<td align="left"><p><span data-ttu-id="40902-125">允许管理主硬件清单，以指定硬件模型是否支持或不能执行 BitLocker 加密。</span><span class="sxs-lookup"><span data-stu-id="40902-125">Allows management of a master hardware inventory to designate whether or not hardware models are capable or incapable to perform BitLocker encryption.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="40902-126">卸载-Mbam</span><span class="sxs-lookup"><span data-stu-id="40902-126">Uninstall-Mbam</span></span></p></td>
<td align="left"><p><span data-ttu-id="40902-127">删除以前安装的 MBAM 功能，这些功能提供高级策略、加密、密钥恢复和合规性报告工具。</span><span class="sxs-lookup"><span data-stu-id="40902-127">Removes previously installed MBAM features that provide advanced policy, encryption, key recovery, and compliance reporting tools.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="40902-128">相关主题</span><span class="sxs-lookup"><span data-stu-id="40902-128">Related topics</span></span>


[<span data-ttu-id="40902-129">MBAM 1.0 的操作</span><span class="sxs-lookup"><span data-stu-id="40902-129">Operations for MBAM 1.0</span></span>](operations-for-mbam-10.md)

 

 





