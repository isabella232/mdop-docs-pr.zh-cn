---
title: 确定设备接收不合规消息的原因
description: 确定设备接收不合规消息的原因
author: dansimp
ms.assetid: 793df330-a0ee-4759-b53a-95618ac74428
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/22/2017
ms.openlocfilehash: ce1d344676ebf4328506228f1bfa87c76e8036f9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803595"
---
# <span data-ttu-id="d0029-103">确定设备接收不合规消息的原因</span><span class="sxs-lookup"><span data-stu-id="d0029-103">Determining why a Device Receives a Noncompliance Message</span></span>


<span data-ttu-id="d0029-104">以下不符合的代码由 WMI 提供，并描述了 MBAM 将特定设备报告为不符合的原因。</span><span class="sxs-lookup"><span data-stu-id="d0029-104">The following noncompliance codes are provided by WMI and describe the reasons why a particular device is reported by MBAM as noncompliant.</span></span>

<span data-ttu-id="d0029-105">你可以使用你的首选方法查看 WMI。</span><span class="sxs-lookup"><span data-stu-id="d0029-105">You can use your preferred method to view WMI.</span></span> <span data-ttu-id="d0029-106">如果使用 PowerShell，请 `gwmi -class mbam_volume -Namespace root\microsoft\mbam` 从 PowerShell 提示符运行，然后搜索 ReasonsForNoncompliance。</span><span class="sxs-lookup"><span data-stu-id="d0029-106">If you use PowerShell, run `gwmi -class mbam_volume -Namespace root\microsoft\mbam` from a PowerShell prompt and search for ReasonsForNoncompliance.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d0029-107">不合规代码</span><span class="sxs-lookup"><span data-stu-id="d0029-107">Non-Compliance Code</span></span></th>
<th align="left"><span data-ttu-id="d0029-108">违反合规性的原因</span><span class="sxs-lookup"><span data-stu-id="d0029-108">Reason for Non-Compliance</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d0029-109">0</span><span class="sxs-lookup"><span data-stu-id="d0029-109">0</span></span></p></td>
<td align="left"><p><span data-ttu-id="d0029-110">密码长度不是 AES 256。</span><span class="sxs-lookup"><span data-stu-id="d0029-110">Cipher strength not AES 256.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d0029-111">raid-1</span><span class="sxs-lookup"><span data-stu-id="d0029-111">1</span></span></p></td>
<td align="left"><p><span data-ttu-id="d0029-112">MBAM 策略要求将此卷加密，而不是。</span><span class="sxs-lookup"><span data-stu-id="d0029-112">MBAM Policy requires this volume to be encrypted but it is not.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d0029-113">ppls-2</span><span class="sxs-lookup"><span data-stu-id="d0029-113">2</span></span></p></td>
<td align="left"><p><span data-ttu-id="d0029-114">MBAM 策略要求此卷不加密，但它是。</span><span class="sxs-lookup"><span data-stu-id="d0029-114">MBAM Policy requires this volume to NOT be encrypted, but it is.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d0029-115">三维空间</span><span class="sxs-lookup"><span data-stu-id="d0029-115">3</span></span></p></td>
<td align="left"><p><span data-ttu-id="d0029-116">MBAM 策略需要此卷使用 TPM 保护程序，但不需要。</span><span class="sxs-lookup"><span data-stu-id="d0029-116">MBAM Policy requires this volume use a TPM protector, but it does not.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d0029-117">第</span><span class="sxs-lookup"><span data-stu-id="d0029-117">4</span></span></p></td>
<td align="left"><p><span data-ttu-id="d0029-118">MBAM 策略需要此卷使用 TPM + 引脚保护程序，但不需要。</span><span class="sxs-lookup"><span data-stu-id="d0029-118">MBAM Policy requires this volume use a TPM+PIN protector, but it does not.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d0029-119">级</span><span class="sxs-lookup"><span data-stu-id="d0029-119">5</span></span></p></td>
<td align="left"><p><span data-ttu-id="d0029-120">MBAM 策略不允许非 TPM 计算机报告为合规。</span><span class="sxs-lookup"><span data-stu-id="d0029-120">MBAM Policy does not allow non TPM machines to report as compliant.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d0029-121">型</span><span class="sxs-lookup"><span data-stu-id="d0029-121">6</span></span></p></td>
<td align="left"><p><span data-ttu-id="d0029-122">卷具有 TPM 保护程序，但 TPM 不可见（使用恢复密钥在 BIOS 中禁用 TPM 后启动）。</span><span class="sxs-lookup"><span data-stu-id="d0029-122">Volume has a TPM protector but the TPM is not visible (booted with recover key after disabling TPM in BIOS?).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d0029-123">7</span><span class="sxs-lookup"><span data-stu-id="d0029-123">7</span></span></p></td>
<td align="left"><p><span data-ttu-id="d0029-124">MBAM 策略需要此卷使用密码保护程序，但没有密码保护程序。</span><span class="sxs-lookup"><span data-stu-id="d0029-124">MBAM Policy requires this volume use a password protector, but it does not have one.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d0029-125">个</span><span class="sxs-lookup"><span data-stu-id="d0029-125">8</span></span></p></td>
<td align="left"><p><span data-ttu-id="d0029-126">MBAM 策略要求此卷不使用密码保护程序，但有一个密码保护器。</span><span class="sxs-lookup"><span data-stu-id="d0029-126">MBAM Policy requires this volume NOT use a password protector, but it has one.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d0029-127">db-9</span><span class="sxs-lookup"><span data-stu-id="d0029-127">9</span></span></p></td>
<td align="left"><p><span data-ttu-id="d0029-128">MBAM 策略需要此卷使用自动解锁保护程序，但没有该卷。</span><span class="sxs-lookup"><span data-stu-id="d0029-128">MBAM Policy requires this volume use an auto-unlock protector, but it does not have one.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d0029-129">10</span><span class="sxs-lookup"><span data-stu-id="d0029-129">10</span></span></p></td>
<td align="left"><p><span data-ttu-id="d0029-130">MBAM 策略需要此卷不使用自动解锁保护程序，但它有一个。</span><span class="sxs-lookup"><span data-stu-id="d0029-130">MBAM Policy requires this volume NOT use an auto-unlock protector, but it has one.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d0029-131">11</span><span class="sxs-lookup"><span data-stu-id="d0029-131">11</span></span></p></td>
<td align="left"><p><span data-ttu-id="d0029-132">检测到策略冲突阻止 MBAM 将此卷报告为合规。</span><span class="sxs-lookup"><span data-stu-id="d0029-132">Policy conflict detected preventing MBAM from reporting this volume as compliant.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d0029-133">至</span><span class="sxs-lookup"><span data-stu-id="d0029-133">12</span></span></p></td>
<td align="left"><p><span data-ttu-id="d0029-134">需要系统卷来加密操作系统卷，但该卷不存在。</span><span class="sxs-lookup"><span data-stu-id="d0029-134">A system volume is needed to encrypt the OS volume but it is not present.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d0029-135">13</span><span class="sxs-lookup"><span data-stu-id="d0029-135">13</span></span></p></td>
<td align="left"><p><span data-ttu-id="d0029-136">已针对卷暂停保护。</span><span class="sxs-lookup"><span data-stu-id="d0029-136">Protection is suspended for the volume.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d0029-137">14</span><span class="sxs-lookup"><span data-stu-id="d0029-137">14</span></span></p></td>
<td align="left"><p><span data-ttu-id="d0029-138">AutoUnlock 不安全，除非操作系统卷已加密。</span><span class="sxs-lookup"><span data-stu-id="d0029-138">AutoUnlock unsafe unless the OS volume is encrypted.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d0029-139">岁</span><span class="sxs-lookup"><span data-stu-id="d0029-139">15</span></span></p></td>
<td align="left"><p><span data-ttu-id="d0029-140">策略要求最低的 cypher 强度为 XTS-128 位，实际 cypher 强度比这更弱。</span><span class="sxs-lookup"><span data-stu-id="d0029-140">Policy requires minimum cypher strength is XTS-AES-128 bit, actual cypher strength is weaker than that.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d0029-141">utf-16</span><span class="sxs-lookup"><span data-stu-id="d0029-141">16</span></span></p></td>
<td align="left"><p><span data-ttu-id="d0029-142">策略要求最低的 cypher 强度为 XTS-256 位，实际 cypher 强度比这更弱。</span><span class="sxs-lookup"><span data-stu-id="d0029-142">Policy requires minimum cypher strength is XTS-AES-256 bit, actual cypher strength is weaker than that.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="d0029-143">相关主题</span><span class="sxs-lookup"><span data-stu-id="d0029-143">Related topics</span></span>


[<span data-ttu-id="d0029-144">MBAM 2.5 的技术参考</span><span class="sxs-lookup"><span data-stu-id="d0029-144">Technical Reference for MBAM 2.5</span></span>](technical-reference-for-mbam-25.md)

[<span data-ttu-id="d0029-145">使用 Windows PowerShell 配置 MBAM 2.5 服务器功能</span><span class="sxs-lookup"><span data-stu-id="d0029-145">Configuring MBAM 2.5 Server Features by Using Windows PowerShell</span></span>](configuring-mbam-25-server-features-by-using-windows-powershell.md)

 
## <span data-ttu-id="d0029-146">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="d0029-146">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="d0029-147">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="d0029-147">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="d0029-148">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="d0029-148">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>
 





