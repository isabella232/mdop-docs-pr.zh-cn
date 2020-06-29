---
title: MBAM 2.5 客户端的先决条件
description: MBAM 2.5 客户端的先决条件
author: dansimp
ms.assetid: fc230679-9c84-4b99-a77c-bae7e7bf8145
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 04/23/2017
ms.openlocfilehash: ac5e211e5ea038f47db3d5e68155eb5af38aa231
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804074"
---
# <span data-ttu-id="f66a0-103">MBAM 2.5 客户端的先决条件</span><span class="sxs-lookup"><span data-stu-id="f66a0-103">Prerequisites for MBAM 2.5 Clients</span></span>


<span data-ttu-id="f66a0-104">在最终用户的计算机上安装 MBAM 客户端软件之前，请确保你的环境和客户端计算机满足以下先决条件。</span><span class="sxs-lookup"><span data-stu-id="f66a0-104">Before you install the MBAM Client software on end users' computers, ensure that your environment and the client computers meet the following prerequisites.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f66a0-105">必备</span><span class="sxs-lookup"><span data-stu-id="f66a0-105">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="f66a0-106">详细信息</span><span class="sxs-lookup"><span data-stu-id="f66a0-106">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f66a0-107">企业域必须包含至少一个 Windows Server 2008 （或更高版本）域控制器。</span><span class="sxs-lookup"><span data-stu-id="f66a0-107">The enterprise domain must contain at least one Windows Server 2008 (or later) domain controller.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f66a0-108">客户端计算机必须登录到企业 intranet。</span><span class="sxs-lookup"><span data-stu-id="f66a0-108">The client computer must be logged on to the enterprise intranet.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f66a0-109">仅适用于 Windows 7 客户端计算机：每个客户端必须具有受信任的平台模块（TPM）功能（tpm 1.2 或更高版本）。</span><span class="sxs-lookup"><span data-stu-id="f66a0-109">For Windows 7 client computers only: Each client must have Trusted Platform Module (TPM) capability (TPM 1.2 or later).</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f66a0-110">对于 Windows 8.1、Windows 10 RTM 或 Windows 10 版本1511客户端计算机：如果你希望 MBAM 能够存储和管理 TPM 恢复密钥，则必须关闭 TPM 自动预配，并且必须在部署 MBAM 之前将 MBAM 设置为 TPM 的所有者。</span><span class="sxs-lookup"><span data-stu-id="f66a0-110">For Windows 8.1, Windows 10 RTM or Windows 10 version 1511 client computers only: If you want MBAM to be able to store and manage the TPM recovery keys, TPM auto-provisioning must be turned off, and MBAM must be set as the owner of the TPM before you deploy MBAM.</span></span></p>
<p><span data-ttu-id="f66a0-111">在 MBAM 2.5 SP1 中，你不再需要关闭 TPM 自动预配，但必须确保 TPM 组策略对象设置为不将 TPM 托管 OwnerAuth 到 Active Directory。</span><span class="sxs-lookup"><span data-stu-id="f66a0-111">In MBAM 2.5 SP1 only, you no longer need to turn off TPM auto-provisioning, but you must make sure that the TPM Group Policy Objects are set to not escrow TPM OwnerAuth to Active Directory.</span></span></p></td>
<td align="left"><p><a href="mbam-25-security-considerations.md#bkmk-tpm" data-raw-source="[MBAM 2.5 Security Considerations](mbam-25-security-considerations.md#bkmk-tpm)"><span data-ttu-id="f66a0-112">MBAM 2.5 安全注意事项</span><span class="sxs-lookup"><span data-stu-id="f66a0-112">MBAM 2.5 Security Considerations</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f66a0-113">对于 Windows 10 版本1607或更高版本，只有 Windows 可以获得 TPM 的所有权。</span><span class="sxs-lookup"><span data-stu-id="f66a0-113">For Windows 10, version 1607 or later, only Windows can take ownership of the TPM.</span></span> <span data-ttu-id="f66a0-114">在 addiiton 中，Windows 将不会在预配 TPM 时保留 TPM 所有者密码。</span><span class="sxs-lookup"><span data-stu-id="f66a0-114">In addiiton, Windows will not retain the TPM owner password when provisioning the TPM.</span></span></p>
<p><span data-ttu-id="f66a0-115">在 MBAM 2.5 SP1 中，必须启用自动预配。</span><span class="sxs-lookup"><span data-stu-id="f66a0-115">In MBAM 2.5 SP1, you must turn on auto-provisioning.</span></span></p>
</p></td>
<td align="left"><p><span data-ttu-id="f66a0-116"><a href="https://technet.microsoft.com/itpro/windows/keep-secure/change-the-tpm-owner-password" data-raw-source="[TPM owner password](https://technet.microsoft.com/itpro/windows/keep-secure/change-the-tpm-owner-password)"> </a> 有关进一步的详细信息，请参阅 TPM 所有者密码。</span><span class="sxs-lookup"><span data-stu-id="f66a0-116">See <a href="https://technet.microsoft.com/itpro/windows/keep-secure/change-the-tpm-owner-password" data-raw-source="[TPM owner password](https://technet.microsoft.com/itpro/windows/keep-secure/change-the-tpm-owner-password)">TPM owner password</a> for further details.</span></span>
</p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f66a0-117">必须在 BIOS 中打开 TPM 芯片，并将其从操作系统中 resettable。</span><span class="sxs-lookup"><span data-stu-id="f66a0-117">The TPM chip must be turned on in the BIOS and be resettable from the operating system.</span></span></p></td>
<td align="left"><p><span data-ttu-id="f66a0-118">有关详细信息，请参阅 BIOS 文档。</span><span class="sxs-lookup"><span data-stu-id="f66a0-118">See the BIOS documentation for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f66a0-119">计算机的硬盘必须至少有两个分区，并且必须使用 NTFS 文件系统进行格式化。</span><span class="sxs-lookup"><span data-stu-id="f66a0-119">The computer’s hard disk must have at least two partitions and must be formatted with the NTFS file system.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f66a0-120">计算机的硬盘必须具有与 TPM 兼容且在计算机启动期间支持 USB 设备的 BIOS。</span><span class="sxs-lookup"><span data-stu-id="f66a0-120">The computer’s hard disk must have a BIOS that is compatible with TPM and that supports USB devices during computer startup.</span></span></p></td>
<td align="left"><div class="alert">
<strong><span data-ttu-id="f66a0-121">注意</span><span class="sxs-lookup"><span data-stu-id="f66a0-121">Note</span></span></strong><br/><p><span data-ttu-id="f66a0-122">确保键盘、视频或鼠标直接连接，而不是通过键盘、视频或鼠标（KVM）切换器管理。</span><span class="sxs-lookup"><span data-stu-id="f66a0-122">Ensure that the keyboard, video, or mouse are directly connected and not managed through a keyboard, video, or mouse (KVM) switch.</span></span> <span data-ttu-id="f66a0-123">KVM 切换器可能会干扰计算机检测硬件实际存在的能力。</span><span class="sxs-lookup"><span data-stu-id="f66a0-123">A KVM switch can interfere with the ability of the computer to detect the physical presence of hardware.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f66a0-124">如果使用代理，它必须在系统上下文中可见。</span><span class="sxs-lookup"><span data-stu-id="f66a0-124">If you use a proxy, it must be visible in the system context.</span></span> <span data-ttu-id="f66a0-125">MBAM 在系统上下文下运行，而不是在用户上下文中运行。</span><span class="sxs-lookup"><span data-stu-id="f66a0-125">MBAM runs under the system context, not the user context.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="f66a0-126">重要提示</span><span class="sxs-lookup"><span data-stu-id="f66a0-126">Important</span></span>**  
<span data-ttu-id="f66a0-127">如果在没有 MBAM 的情况下使用 BitLocker，则可以安装 MBAM 并利用现有的 TPM 信息。</span><span class="sxs-lookup"><span data-stu-id="f66a0-127">If BitLocker was used without MBAM, MBAM can be installed and utilize the existing TPM information.</span></span>




## <span data-ttu-id="f66a0-128">相关主题</span><span class="sxs-lookup"><span data-stu-id="f66a0-128">Related topics</span></span>


[<span data-ttu-id="f66a0-129">MBAM 2.5 支持的配置</span><span class="sxs-lookup"><span data-stu-id="f66a0-129">MBAM 2.5 Supported Configurations</span></span>](mbam-25-supported-configurations.md)

[<span data-ttu-id="f66a0-130">规划部署 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="f66a0-130">Planning to Deploy MBAM 2.5</span></span>](planning-to-deploy-mbam-25.md)


## <span data-ttu-id="f66a0-131">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="f66a0-131">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="f66a0-132">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="f66a0-132">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span>
- <span data-ttu-id="f66a0-133">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="f66a0-133">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>






