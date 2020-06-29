---
title: 关于 MBAM 2.5 SP1
description: 关于 MBAM 2.5 SP1
author: dansimp
ms.assetid: 6f12e605-44e6-4646-9c20-aee89c8ff0b7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 09/27/2016
ms.openlocfilehash: 41e47e1561629c00d30b45ad2dcd94f37753af5b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803437"
---
# <span data-ttu-id="b6d97-103">关于 MBAM 2.5 SP1</span><span class="sxs-lookup"><span data-stu-id="b6d97-103">About MBAM 2.5 SP1</span></span>


<span data-ttu-id="b6d97-104">MBAM 2.5 SP1 为 BitLocker 驱动器加密提供简化的管理接口。</span><span class="sxs-lookup"><span data-stu-id="b6d97-104">MBAM 2.5 SP1 provides a simplified administrative interface for BitLocker Drive Encryption.</span></span> <span data-ttu-id="b6d97-105">对于丢失或被盗的计算机，BitLocker 提供增强的防护功能，防止数据失窃或数据暴露。</span><span class="sxs-lookup"><span data-stu-id="b6d97-105">BitLocker offers enhanced protection against data theft or data exposure for computers that are lost or stolen.</span></span> <span data-ttu-id="b6d97-106">BitLocker 将加密存储在 Windows 操作系统和驱动器以及配置的数据驱动器上的所有数据。</span><span class="sxs-lookup"><span data-stu-id="b6d97-106">BitLocker encrypts all data that is stored on the Windows operating system and drives and configured data drives.</span></span>

## <span data-ttu-id="b6d97-107">MBAM 概述</span><span class="sxs-lookup"><span data-stu-id="b6d97-107">Overview of MBAM</span></span>


<span data-ttu-id="b6d97-108">MBAM 2.5 SP1 具有以下功能：</span><span class="sxs-lookup"><span data-stu-id="b6d97-108">MBAM 2.5 SP1 has the following features:</span></span>

-   <span data-ttu-id="b6d97-109">使管理员能够自动对企业内的客户端计算机上的卷进行加密的过程。</span><span class="sxs-lookup"><span data-stu-id="b6d97-109">Enables administrators to automate the process of encrypting volumes on client computers across the enterprise.</span></span>

-   <span data-ttu-id="b6d97-110">使安全监察官能够快速确定单个计算机或甚至企业本身的合规性状态。</span><span class="sxs-lookup"><span data-stu-id="b6d97-110">Enables security officers to quickly determine the compliance state of individual computers or even of the enterprise itself.</span></span>

-   <span data-ttu-id="b6d97-111">通过 Microsoft System Center Configuration Manager 提供集中报告和硬件管理。</span><span class="sxs-lookup"><span data-stu-id="b6d97-111">Provides centralized reporting and hardware management with Microsoft System Center Configuration Manager.</span></span>

-   <span data-ttu-id="b6d97-112">减少了帮助台上的工作负荷，帮助最终用户提供 BitLocker PIN 和恢复密钥请求。</span><span class="sxs-lookup"><span data-stu-id="b6d97-112">Reduces the workload on the Help Desk to assist end users with BitLocker PIN and recovery key requests.</span></span>

-   <span data-ttu-id="b6d97-113">使最终用户能够使用自助服务门户单独恢复加密的设备。</span><span class="sxs-lookup"><span data-stu-id="b6d97-113">Enables end users to recover encrypted devices independently by using the Self-Service Portal.</span></span>

-   <span data-ttu-id="b6d97-114">使安全专员能够轻松审核 access 以恢复密钥信息。</span><span class="sxs-lookup"><span data-stu-id="b6d97-114">Enables security officers to easily audit access to recover key information.</span></span>

-   <span data-ttu-id="b6d97-115">使 Windows 企业用户能够在任何位置继续工作，确保其企业数据受到保护。</span><span class="sxs-lookup"><span data-stu-id="b6d97-115">Empowers Windows Enterprise users to continue working anywhere with the assurance that their corporate data is protected.</span></span>

<span data-ttu-id="b6d97-116">MBAM 强制执行你为你的企业设置的 BitLocker 加密策略选项，监视客户端计算机与这些策略的合规性，并报告企业和个人计算机的加密状态。</span><span class="sxs-lookup"><span data-stu-id="b6d97-116">MBAM enforces the BitLocker encryption policy options that you set for your enterprise, monitors the compliance of client computers with those policies, and reports on the encryption status of the enterprise’s and individual’s computers.</span></span> <span data-ttu-id="b6d97-117">此外，MBAM 允许你在用户忘记其 PIN 或密码时，或者在其 BIOS 或启动记录发生更改时访问恢复密钥信息。</span><span class="sxs-lookup"><span data-stu-id="b6d97-117">In addition, MBAM lets you access the recovery key information when users forget their PIN or password, or when their BIOS or boot records change.</span></span>

<span data-ttu-id="b6d97-118">以下组可能对使用 MBAM 管理 BitLocker 感兴趣：</span><span class="sxs-lookup"><span data-stu-id="b6d97-118">The following groups might be interested in using MBAM to manage BitLocker:</span></span>

-   <span data-ttu-id="b6d97-119">管理员、IT 安全专家和合规性监察官负责确保机密数据在未经授权的情况下不公开</span><span class="sxs-lookup"><span data-stu-id="b6d97-119">Administrators, IT security professionals, and compliance officers who are responsible for ensuring that confidential data is not disclosed without authorization</span></span>

-   <span data-ttu-id="b6d97-120">负责远程或分支办公室中的计算机安全的管理员</span><span class="sxs-lookup"><span data-stu-id="b6d97-120">Administrators who are responsible for computer security in remote or branch offices</span></span>

-   <span data-ttu-id="b6d97-121">负责运行 Windows 的客户端计算机的管理员</span><span class="sxs-lookup"><span data-stu-id="b6d97-121">Administrators who are responsible for client computers that are running Windows</span></span>

<span data-ttu-id="b6d97-122">**注意** 在本 MBAM 文档中不详细介绍 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="b6d97-122">**Note** BitLocker is not explained in detail in this MBAM documentation.</span></span> <span data-ttu-id="b6d97-123">有关详细信息，请参阅[BitLocker 驱动器加密概述](https://go.microsoft.com/fwlink/p/?LinkId=225013)。</span><span class="sxs-lookup"><span data-stu-id="b6d97-123">For more information, see [BitLocker Drive Encryption Overview](https://go.microsoft.com/fwlink/p/?LinkId=225013).</span></span>

 

## <a href="" id="what-s-new-in-mbam-2-5-sp1"></a><span data-ttu-id="b6d97-124">MBAM 2.5 SP1 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="b6d97-124">What’s new in MBAM 2.5 SP1</span></span>


<span data-ttu-id="b6d97-125">本部分介绍了 MBAM 2.5 SP1 中的新增功能。</span><span class="sxs-lookup"><span data-stu-id="b6d97-125">This section describes the new features in MBAM 2.5 SP1.</span></span>

### <span data-ttu-id="b6d97-126">MBAM 2.5 SP1 客户端的新支持语言</span><span class="sxs-lookup"><span data-stu-id="b6d97-126">Newly Supported Languages for the MBAM 2.5 SP1 Client</span></span>

<span data-ttu-id="b6d97-127">以下附加语言现在仅在 MBAM 客户端的 MBAM 2.5 SP1 中受支持，包括自助门户：</span><span class="sxs-lookup"><span data-stu-id="b6d97-127">The following additional languages are now supported in MBAM 2.5 SP1 for the MBAM Client only, including the Self-Service Portal:</span></span>

<span data-ttu-id="b6d97-128">捷克语（捷克共和国） cs-CZ</span><span class="sxs-lookup"><span data-stu-id="b6d97-128">Czech (Czech Republic) cs-CZ</span></span>

<span data-ttu-id="b6d97-129">丹麦语（丹麦） da-深色</span><span class="sxs-lookup"><span data-stu-id="b6d97-129">Danish (Denmark) da-DK</span></span>

<span data-ttu-id="b6d97-130">荷兰语（荷兰） nl-NL</span><span class="sxs-lookup"><span data-stu-id="b6d97-130">Dutch (Netherlands) nl-NL</span></span>

<span data-ttu-id="b6d97-131">芬兰语（芬兰） wlan</span><span class="sxs-lookup"><span data-stu-id="b6d97-131">Finnish (Finland) fi-FI</span></span>

<span data-ttu-id="b6d97-132">希腊语（希腊） el-GR</span><span class="sxs-lookup"><span data-stu-id="b6d97-132">Greek (Greece) el-GR</span></span>

<span data-ttu-id="b6d97-133">匈牙利语（匈牙利） hu-HU</span><span class="sxs-lookup"><span data-stu-id="b6d97-133">Hungarian (Hungary) hu-HU</span></span>

<span data-ttu-id="b6d97-134">挪威语、博克马尔语（挪威） nb-否</span><span class="sxs-lookup"><span data-stu-id="b6d97-134">Norwegian, Bokmål (Norway) nb-NO</span></span>

<span data-ttu-id="b6d97-135">波兰语（波兰） pl-PL</span><span class="sxs-lookup"><span data-stu-id="b6d97-135">Polish (Poland) pl-PL</span></span>

<span data-ttu-id="b6d97-136">葡萄牙语（葡萄牙） pt</span><span class="sxs-lookup"><span data-stu-id="b6d97-136">Portuguese (Portugal) pt-PT</span></span>

<span data-ttu-id="b6d97-137">斯洛伐克语（斯洛伐克） sk-SK</span><span class="sxs-lookup"><span data-stu-id="b6d97-137">Slovak (Slovakia) sk-SK</span></span>

<span data-ttu-id="b6d97-138">斯洛文尼亚语（斯洛文尼亚） sl-SI</span><span class="sxs-lookup"><span data-stu-id="b6d97-138">Slovenian (Slovenia) sl-SI</span></span>

<span data-ttu-id="b6d97-139">瑞典语（瑞典） sv-SE</span><span class="sxs-lookup"><span data-stu-id="b6d97-139">Swedish (Sweden) sv-SE</span></span>

<span data-ttu-id="b6d97-140">土耳其语（土耳其） tr-TR</span><span class="sxs-lookup"><span data-stu-id="b6d97-140">Turkish (Turkey) tr-TR</span></span>

<span data-ttu-id="b6d97-141">有关 MBAM 2.5 和 MBAM 2.5 SP1 中的客户端和服务器支持的所有语言的列表，请参阅[MBAM 2.5 支持的配置](mbam-25-supported-configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="b6d97-141">For a list of all languages supported for client and server in MBAM 2.5 and MBAM 2.5 SP1, see [MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md).</span></span>

### <span data-ttu-id="b6d97-142">Windows 10 支持</span><span class="sxs-lookup"><span data-stu-id="b6d97-142">Support for Windows 10</span></span>

<span data-ttu-id="b6d97-143">MBAM 2.5 SP1 除了更早版本的 MBAM 支持的同一软件外，还添加了对 Windows 10 和 Windows Server 2016 的支持。</span><span class="sxs-lookup"><span data-stu-id="b6d97-143">MBAM 2.5 SP1 adds support for Windows 10 and Windows Server 2016, in addition to the same software that is supported in earlier versions of MBAM.</span></span>

<span data-ttu-id="b6d97-144">Windows 10 在 MBAM 2.5 和 MBAM 2.5 SP1 中均受支持。</span><span class="sxs-lookup"><span data-stu-id="b6d97-144">Windows 10 is supported in both MBAM 2.5 and MBAM 2.5 SP1.</span></span>

### <span data-ttu-id="b6d97-145">Microsoft SQL Server 2014 SP1 的支持</span><span class="sxs-lookup"><span data-stu-id="b6d97-145">Support for Microsoft SQL Server 2014 SP1</span></span>

<span data-ttu-id="b6d97-146">MBAM 2.5 SP1 不仅增加了对 Microsoft SQL Server 2014 SP1 的支持，还添加了与早期版本的 MBAM 中支持的同一软件。</span><span class="sxs-lookup"><span data-stu-id="b6d97-146">MBAM 2.5 SP1 adds support for Microsoft SQL Server 2014 SP1, in addition to the same software that is supported in earlier versions of MBAM.</span></span>

### <span data-ttu-id="b6d97-147">MBAM 不再附带单独的 MSI</span><span class="sxs-lookup"><span data-stu-id="b6d97-147">MBAM no longer ships with separate MSI</span></span>

<span data-ttu-id="b6d97-148">从 MBAM 2.5 SP1 开始，MBAM 产品不再附带单独的 MSI。</span><span class="sxs-lookup"><span data-stu-id="b6d97-148">Beginning in MBAM 2.5 SP1, a separate MSI is no longer included with the MBAM product.</span></span> <span data-ttu-id="b6d97-149">但是，你可以从产品附带的可执行文件（.exe）中提取 MSI。</span><span class="sxs-lookup"><span data-stu-id="b6d97-149">However, you can extract the MSI from the executable file (.exe) that is included with the product.</span></span>

### <span data-ttu-id="b6d97-150">MBAM 可以在不拥有 TPM 的情况下保管 OwnerAuth 密码</span><span class="sxs-lookup"><span data-stu-id="b6d97-150">MBAM can escrow OwnerAuth passwords without owning the TPM</span></span>

<span data-ttu-id="b6d97-151">以前，如果 MBAM 不拥有 TPM，则无法将 TPM OwnerAuth escrowed 到 MBAM 数据库。</span><span class="sxs-lookup"><span data-stu-id="b6d97-151">Previously, if MBAM did not own the TPM, the TPM OwnerAuth could not be escrowed to the MBAM database.</span></span> <span data-ttu-id="b6d97-152">若要将 MBAM 配置为拥有 TPM 并存储密码，必须禁用 TPM 自动预配，并在客户端计算机上清除 TPM。</span><span class="sxs-lookup"><span data-stu-id="b6d97-152">To configure MBAM to own the TPM and to store the passwords, you had to disable TPM auto-provisioning and clear the TPM on the client computer.</span></span>

<span data-ttu-id="b6d97-153">在 Windows 8 及更高版本中，MBAM 2.5 SP1 现在可以在不拥有 TPM 的情况下保管 OwnerAuth 密码。</span><span class="sxs-lookup"><span data-stu-id="b6d97-153">In Windows 8 and higher, MBAM 2.5 SP1 can now escrow the OwnerAuth passwords without owning the TPM.</span></span> <span data-ttu-id="b6d97-154">在服务启动期间，MBAM 查询以查看 TPM 是否已拥有，如果是，则它会从操作系统请求密码。</span><span class="sxs-lookup"><span data-stu-id="b6d97-154">During service startup, MBAM queries to see if the TPM is already owned and if so, it requests the passwords from the operating system.</span></span> <span data-ttu-id="b6d97-155">然后，密码将 escrowed 到 MBAM 数据库。</span><span class="sxs-lookup"><span data-stu-id="b6d97-155">The passwords are then escrowed to the MBAM database.</span></span> <span data-ttu-id="b6d97-156">此外，必须设置组策略以防止 OwnerAuth 在本地删除。</span><span class="sxs-lookup"><span data-stu-id="b6d97-156">In addition, Group Policy must be set to prevent the OwnerAuth from being deleted locally.</span></span>

<span data-ttu-id="b6d97-157">在 Windows 7 中，MBAM 必须拥有 TPM 才能在 MBAM 数据库中自动托管 TPM OwnerAuth 信息。</span><span class="sxs-lookup"><span data-stu-id="b6d97-157">In Windows 7, MBAM must own the TPM to automatically escrow TPM OwnerAuth information in the MBAM database.</span></span> <span data-ttu-id="b6d97-158">如果 MBAM 不拥有 TPM，并且通过组策略配置 TPM 的 Active Directory （AD）备份，则必须使用**MBAM Active Directory （ad）数据导入 cmdlet**将 TPM OWNERAUTH 从 AD 复制到 MBAM 数据库。</span><span class="sxs-lookup"><span data-stu-id="b6d97-158">If MBAM does not own the TPM and Active Directory (AD) backup of the TPM is configured through Group Policy, you must use the **MBAM Active Directory (AD) Data Import cmdlets** to copy TPM OwnerAuth from AD into the MBAM database.</span></span> <span data-ttu-id="b6d97-159">以下是五个新的 PowerShell cmdlet，这些 cmdlet 预填充了存储在 Active Directory 中的卷恢复和 TPM 所有者信息的 MBAM 数据库。</span><span class="sxs-lookup"><span data-stu-id="b6d97-159">These are five new PowerShell cmdlets that pre-populate MBAM databases with the Volume recovery and TPM owner information stored in Active Directory.</span></span>

<span data-ttu-id="b6d97-160">有关详细信息，请参阅[MBAM 2.5 安全注意事项](mbam-25-security-considerations.md#bkmk-tpm)。</span><span class="sxs-lookup"><span data-stu-id="b6d97-160">For more information, see [MBAM 2.5 Security Considerations](mbam-25-security-considerations.md#bkmk-tpm).</span></span>

### <span data-ttu-id="b6d97-161">MBAM 可以在锁定后自动解锁 TPM</span><span class="sxs-lookup"><span data-stu-id="b6d97-161">MBAM can automatically unlock the TPM after a lockout</span></span>

<span data-ttu-id="b6d97-162">在运行 TPM 1.2 的计算机上，你现在可以将 MBAM 配置为在锁定时自动解锁 TPM。</span><span class="sxs-lookup"><span data-stu-id="b6d97-162">On computers running TPM 1.2, you can now configure MBAM to automatically unlock the TPM in case of a lockout.</span></span> <span data-ttu-id="b6d97-163">如果启用了 TPM 锁定自动重置功能，MBAM 可以检测到用户已被锁定，然后获取 MBAM 数据库中的 OwnerAuth 密码，以便为用户自动解锁 TPM。</span><span class="sxs-lookup"><span data-stu-id="b6d97-163">If the TPM lockout auto reset feature is enabled, MBAM can detect that a user is locked out and then get the OwnerAuth password from the MBAM database to automatically unlock the TPM for the user.</span></span>

<span data-ttu-id="b6d97-164">必须在服务器端和客户端上的组策略中启用此功能。</span><span class="sxs-lookup"><span data-stu-id="b6d97-164">This feature must be enabled on both the server side and in Group Policy on the client side.</span></span> <span data-ttu-id="b6d97-165">有关详细信息，请参阅[MBAM 2.5 安全注意事项](mbam-25-security-considerations.md#bkmk-autounlock)。</span><span class="sxs-lookup"><span data-stu-id="b6d97-165">For more information, see [MBAM 2.5 Security Considerations](mbam-25-security-considerations.md#bkmk-autounlock).</span></span>

### <span data-ttu-id="b6d97-166">支持 FIPS 兼容的 BitLocker 数字密码保护器</span><span class="sxs-lookup"><span data-stu-id="b6d97-166">Support for FIPS-compliant BitLocker numerical password protectors</span></span>

<span data-ttu-id="b6d97-167">在 MBAM 2.5 中，为运行 Windows 8.1 操作系统的设备上的联邦信息处理标准（FIPS）兼容的 BitLocker 恢复密钥添加了支持。</span><span class="sxs-lookup"><span data-stu-id="b6d97-167">In MBAM2.5, support was added for Federal Information Processing Standard (FIPS)-compliant BitLocker recovery keys on devices running the Windows 8.1 operating system.</span></span> <span data-ttu-id="b6d97-168">但是，Windows 未在 Windows 7 中实现符合 FIPS 的恢复密钥。</span><span class="sxs-lookup"><span data-stu-id="b6d97-168">However, Windows did not implement FIPS-compliant recovery keys in Windows 7.</span></span> <span data-ttu-id="b6d97-169">因此，Windows 7 和 Windows 8 设备仍需要用于恢复的数据恢复代理（DRA）保护程序。</span><span class="sxs-lookup"><span data-stu-id="b6d97-169">Therefore, Windows 7 and Windows 8 devices still required a Data Recovery Agent (DRA) protector for recovery.</span></span>

<span data-ttu-id="b6d97-170">Windows 团队拥有 backported FIPS 兼容的恢复密钥和一个修补程序，MBAM 2.5 SP1 还添加了对它们的支持。</span><span class="sxs-lookup"><span data-stu-id="b6d97-170">The Windows team has backported FIPS-compliant recovery keys with a hotfix, and MBAM 2.5 SP1 has added support for them as well.</span></span>

<span data-ttu-id="b6d97-171">**注意** 运行 Windows8 操作系统的客户端计算机仍需要 DRA 保护器，因为该修补程序不会 backported 该操作系统。</span><span class="sxs-lookup"><span data-stu-id="b6d97-171">**Note** Client computers that are running the Windows8 operating system still require a DRA protector since the hotfix was not backported to that OS.</span></span> <span data-ttu-id="b6d97-172">请参阅[Bitlocker 管理和监视2.5 的修补程序包 2](https://support.microsoft.com/kb/3015477) ，下载并安装适用于 windows 7 和 windows 8 计算机的 bitlocker 修补程序。</span><span class="sxs-lookup"><span data-stu-id="b6d97-172">See [Hotfix Package 2 for BitLocker Administration and Monitoring 2.5](https://support.microsoft.com/kb/3015477) to download and install the BitLocker hotfix for Windows 7 and Windows 8 computers.</span></span> <span data-ttu-id="b6d97-173">有关 DRA 的信息，请参阅将[数据恢复代理与 BitLocker 配合使用](https://go.microsoft.com/fwlink/?LinkId=393557)。</span><span class="sxs-lookup"><span data-stu-id="b6d97-173">For information about DRA, see [Using Data Recovery Agents with BitLocker](https://go.microsoft.com/fwlink/?LinkId=393557).</span></span>

 

<span data-ttu-id="b6d97-174">若要在你的组织中启用 FIPS 合规性，必须配置联邦信息处理标准（FIPS）组策略设置。</span><span class="sxs-lookup"><span data-stu-id="b6d97-174">To enable FIPS compliance in your organization, you must configure the Federal Information Processing Standard (FIPS) Group Policy settings.</span></span> <span data-ttu-id="b6d97-175">有关配置说明，请参阅[BitLocker 组策略设置](https://go.microsoft.com/fwlink/?LinkId=393560)。</span><span class="sxs-lookup"><span data-stu-id="b6d97-175">For configuration instructions, see [BitLocker Group Policy Settings](https://go.microsoft.com/fwlink/?LinkId=393560).</span></span>

### <span data-ttu-id="b6d97-176">通过新的组策略设置自定义启动前恢复消息和 URL</span><span class="sxs-lookup"><span data-stu-id="b6d97-176">Customize pre-boot recovery message and URL with new Group Policy setting</span></span>

<span data-ttu-id="b6d97-177">新的组策略设置，**配置预启动恢复消息和 URL**，让你可以配置自定义恢复消息或指定一个在操作系统驱动器锁定时在预启动 BitLocker 恢复屏幕上显示的 URL。</span><span class="sxs-lookup"><span data-stu-id="b6d97-177">A new Group Policy setting, **Configure pre-boot recovery message and URL**, lets you configure a custom recovery message or specify a URL that is then displayed on the pre-boot BitLocker recovery screen when the OS drive is locked.</span></span> <span data-ttu-id="b6d97-178">此设置仅在运行 Windows 10 的客户端计算机上可用。</span><span class="sxs-lookup"><span data-stu-id="b6d97-178">This setting is only available on client computers running Windows 10.</span></span>

<span data-ttu-id="b6d97-179">如果启用此策略设置，你可以为预启动恢复消息选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="b6d97-179">If you enable this policy setting, you can you can select one of these options for the pre-boot recovery message:</span></span>

-   <span data-ttu-id="b6d97-180">**使用自定义恢复消息**：选择此选项可在预启动 BitLocker 恢复屏幕中包含自定义消息。</span><span class="sxs-lookup"><span data-stu-id="b6d97-180">**Use custom recovery message**: Select this option to include a custom message in the pre-boot BitLocker recovery screen.</span></span>

-   <span data-ttu-id="b6d97-181">**使用自定义恢复 URL**：选择此选项可替换 "预启动 BitLocker 恢复" 屏幕中显示的默认 URL。</span><span class="sxs-lookup"><span data-stu-id="b6d97-181">**Use custom recovery URL**: Select this option to replace the default URL that is displayed in the pre-boot BitLocker recovery screen.</span></span>

-   <span data-ttu-id="b6d97-182">**使用默认的恢复消息和 URL**：选择此选项可在预启动 bitlocker 恢复屏幕中显示默认的 BitLocker 恢复消息和 url。</span><span class="sxs-lookup"><span data-stu-id="b6d97-182">**Use default recovery message and URL**: Select this option to display the default BitLocker recovery message and URL in the pre-boot BitLocker recovery screen.</span></span> <span data-ttu-id="b6d97-183">如果以前配置了自定义恢复消息或 URL 并希望还原为默认消息，则必须启用此策略，然后选择此选项。</span><span class="sxs-lookup"><span data-stu-id="b6d97-183">If you previously configured a custom recovery message or URL and want to revert to the default message, you must enable this policy and select this option.</span></span>

<span data-ttu-id="b6d97-184">新组策略设置位于以下 GPO 节点中：**计算机配置** &gt; **策略** &gt; **管理模板** &gt; **Windows 组件** &gt; **MDOP MBAM （BitLocker 管理）** &gt; **操作系统驱动器**。</span><span class="sxs-lookup"><span data-stu-id="b6d97-184">The new Group Policy setting is located in the following GPO node: **Computer Configuration** &gt; **Policies** &gt; **Administrative Templates** &gt; **Windows Components** &gt; **MDOP MBAM (BitLocker Management)** &gt; **Operating System Drive**.</span></span> <span data-ttu-id="b6d97-185">有关详细信息，请参阅[规划 MBAM 2.5 组策略要求](planning-for-mbam-25-group-policy-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b6d97-185">For more information, see [Planning for MBAM 2.5 Group Policy Requirements](planning-for-mbam-25-group-policy-requirements.md).</span></span>

### <span data-ttu-id="b6d97-186">MBAM 添加了对已用空间加密的支持</span><span class="sxs-lookup"><span data-stu-id="b6d97-186">MBAM added support for Used Space Encryption</span></span>

<span data-ttu-id="b6d97-187">在 MBAM 2.5 SP1 中，如果通过 BitLocker 组策略启用已使用的空间加密，MBAM 客户端将接受它。</span><span class="sxs-lookup"><span data-stu-id="b6d97-187">In MBAM 2.5 SP1, if you enable Used Space Encryption via BitLocker Group Policy, the MBAM Client honors it.</span></span>

<span data-ttu-id="b6d97-188">此组策略设置称为 **"在操作系统驱动器上强制执行驱动器加密类型"** ，位于以下 GPO 节点中： "**计算机配置** &gt; **管理模板**" &gt; **Windows 组件**" &gt; **BitLocker 驱动器加密** &gt; **操作系统驱动器**"。</span><span class="sxs-lookup"><span data-stu-id="b6d97-188">This Group Policy setting is called **Enforce drive encryption type on operating system drives** and is located in the following GPO node: **Computer Configuration** &gt; **Administrative Templates** &gt; **Windows Components** &gt; **BitLocker Drive Encryption** &gt; **Operating System Drives**.</span></span> <span data-ttu-id="b6d97-189">如果启用此策略并选择 "**仅限已用空间" 加密**的加密类型，则 MBAM 将接受该策略，并且 BitLocker 将仅加密卷上使用的磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="b6d97-189">If you enable this policy and select the encryption type as **Used Space Only encryption**, MBAM will honor the policy and BitLocker will only encrypt disk space that is used on the volume.</span></span>

<span data-ttu-id="b6d97-190">有关详细信息，请参阅[规划 MBAM 2.5 组策略要求](planning-for-mbam-25-group-policy-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b6d97-190">For more information, see [Planning for MBAM 2.5 Group Policy Requirements](planning-for-mbam-25-group-policy-requirements.md).</span></span>

### <span data-ttu-id="b6d97-191">MBAM 客户端对加密硬驱的支持</span><span class="sxs-lookup"><span data-stu-id="b6d97-191">MBAM Client support for Encrypted Hard Drives</span></span>

<span data-ttu-id="b6d97-192">MBAM 支持在满足 Opal 的 TCG 规范要求和 IEEE 1667 标准的加密硬盘上支持 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="b6d97-192">MBAM supports BitLocker on Encrypted Hard Drives that meet TCG specification requirements for Opal as well as IEEE 1667 standards.</span></span> <span data-ttu-id="b6d97-193">在这些设备上启用 BitLocker 时，它将在已加密的驱动器上生成密钥并执行管理功能。</span><span class="sxs-lookup"><span data-stu-id="b6d97-193">When BitLocker is enabled on these devices, it will generate keys and perform management functions on the encrypted drive.</span></span> <span data-ttu-id="b6d97-194">有关详细信息，请参阅[加密的硬驱](https://technet.microsoft.com/library/hh831627.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b6d97-194">See [Encrypted Hard Drive](https://technet.microsoft.com/library/hh831627.aspx) for more information.</span></span>

### <span data-ttu-id="b6d97-195">注册 Spn 时不再需要委派配置</span><span class="sxs-lookup"><span data-stu-id="b6d97-195">Delegation configuration no longer required when registering SPNs</span></span>

<span data-ttu-id="b6d97-196">在 MBAM 2.5 SP1 中不再需要为你注册应用程序池帐户所注册的 Spn 配置受限委派的要求。</span><span class="sxs-lookup"><span data-stu-id="b6d97-196">The requirement to configure constrained delegation for SPNs that you register for the application pool account is no longer necessary in MBAM 2.5 SP1.</span></span> <span data-ttu-id="b6d97-197">但是，它仍是 MBAM 2.5 的必要条件。</span><span class="sxs-lookup"><span data-stu-id="b6d97-197">However, it is still a requirement for MBAM 2.5.</span></span>

### <span data-ttu-id="b6d97-198">使用 MBAM 作为 Windows 部署的一部分启用 BitLocker</span><span class="sxs-lookup"><span data-stu-id="b6d97-198">Enable BitLocker using MBAM as Part of a Windows Deployment</span></span>

<span data-ttu-id="b6d97-199">在 MBAM 2.5 SP1 中，你可以使用 PowerShell 脚本将 BitLocker 驱动器加密和托管恢复密钥配置为 MBAM 服务器。</span><span class="sxs-lookup"><span data-stu-id="b6d97-199">In MBAM 2.5 SP1, you can use a PowerShell script to configure BitLocker drive encryption and escrow recovery keys to the MBAM Server.</span></span>

<span data-ttu-id="b6d97-200">有关详细信息，请参阅[使用 MBAM 作为 Windows 部署的一部分来启用 BitLocker](how-to-enable-bitlocker-by-using-mbam-as-part-of-a-windows-deploymentmbam-25.md)</span><span class="sxs-lookup"><span data-stu-id="b6d97-200">For more information, see [How to Enable BitLocker by Using MBAM as Part of a Windows Deployment](how-to-enable-bitlocker-by-using-mbam-as-part-of-a-windows-deploymentmbam-25.md)</span></span>

### <span data-ttu-id="b6d97-201">可以使用 PowerShell 或 SSP 自定义向导自定义自助服务门户</span><span class="sxs-lookup"><span data-stu-id="b6d97-201">Self-Service Portal can be customized by using either PowerShell or the SSP customization wizard</span></span>

<span data-ttu-id="b6d97-202">从 MBAM 2.5 SP1，自助服务门户可通过使用自定义向导以及使用 PowerShell 进行配置。</span><span class="sxs-lookup"><span data-stu-id="b6d97-202">As of MBAM 2.5 SP1, the Self-Service Portal can be configured by using the customization wizard as well as by using PowerShell.</span></span> <span data-ttu-id="b6d97-203">请参阅[如何配置 MBAM 2.5 Web 应用程序](how-to-configure-the-mbam-25-web-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="b6d97-203">See [How to Configure the MBAM 2.5 Web Applications](how-to-configure-the-mbam-25-web-applications.md).</span></span>

### <span data-ttu-id="b6d97-204">Web 浏览器不再无意间以管理员身份运行</span><span class="sxs-lookup"><span data-stu-id="b6d97-204">Web browser no longer unintentionally runs as administrator</span></span>

<span data-ttu-id="b6d97-205">MBAM 2.5 中的问题导致了服务器配置工具中的帮助链接，导致浏览器窗口以管理员权限打开。</span><span class="sxs-lookup"><span data-stu-id="b6d97-205">An issue in MBAM 2.5 caused help links in the Server Configuration tool to cause browser windows to open with administrator rights.</span></span> <span data-ttu-id="b6d97-206">此问题在 MBAM 2.5 SP1 中已修复。</span><span class="sxs-lookup"><span data-stu-id="b6d97-206">This issue is fixed in MBAM 2.5 SP1.</span></span>

### <span data-ttu-id="b6d97-207">当 CDN 不可访问时，不再需要下载 JavaScript 文件以配置自助服务门户</span><span class="sxs-lookup"><span data-stu-id="b6d97-207">No longer need to download the JavaScript files to configure the Self-Service Portal when the CDN is inaccessible</span></span>

<span data-ttu-id="b6d97-208">在 MBAM 2.5 和更早版本中，如果访问自助服务门户的客户没有 internet 访问权限，则必须提前从 CDN 下载用于配置自助服务门户的 jQuery 文件。</span><span class="sxs-lookup"><span data-stu-id="b6d97-208">In MBAM 2.5 and earlier, the jQuery files used for configuration of the Self-Service Portal had to be downloaded from the CDN in advance if clients accessing the Self-Service Portal did not have internet access.</span></span> <span data-ttu-id="b6d97-209">在 MBAM 2.5 SP1 中，所有 JavaScript 文件都包含在产品中，因此不需要下载它们。</span><span class="sxs-lookup"><span data-stu-id="b6d97-209">In MBAM 2.5 SP1, all JavaScript files are included in the product, so downloading them is unnecessary.</span></span>

### <span data-ttu-id="b6d97-210">可以在报表生成器3.0 中打开报表</span><span class="sxs-lookup"><span data-stu-id="b6d97-210">Reports can be opened in Report Builder 3.0</span></span>

<span data-ttu-id="b6d97-211">在 MBAM 2.5 SP1 中，报表已更新为最新的报表定义语言架构，允许用户在报表生成器3.0 中打开和自定义报表，并将其立即保存，而不损坏报表文件。</span><span class="sxs-lookup"><span data-stu-id="b6d97-211">In MBAM 2.5 SP1, the reports have been updated to the latest report definition language schema, allowing users to open and customize the reports in Report Builder 3.0 and save them immediately without corrupting the report file.</span></span>

### <span data-ttu-id="b6d97-212">新的 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="b6d97-212">New PowerShell cmdlets</span></span>

<span data-ttu-id="b6d97-213">MBAM 2.5 SP1 的新 PowerShell cmdlet 使你可以配置和管理不同的 MBAM 功能，包括数据库、报表和 web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="b6d97-213">New PowerShell cmdlets for MBAM 2.5 SP1 enable you to configure and manage different MBAM features, including databases, reports, and web applications.</span></span> <span data-ttu-id="b6d97-214">每个功能都具有相应的 PowerShell cmdlet，可用于启用或禁用功能，或获取有关该功能的信息。</span><span class="sxs-lookup"><span data-stu-id="b6d97-214">Each feature has a corresponding PowerShell cmdlet that you can use to enable or disable features, or to get information about the feature.</span></span>

<span data-ttu-id="b6d97-215">已针对 MBAM 2.5 SP1 实现以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="b6d97-215">The following cmdlets have been implemented for MBAM 2.5 SP1:</span></span>

-   <span data-ttu-id="b6d97-216">Write-MbamTpmInformation</span><span class="sxs-lookup"><span data-stu-id="b6d97-216">Write-MbamTpmInformation</span></span>

-   <span data-ttu-id="b6d97-217">Write-MbamRecoveryInformation</span><span class="sxs-lookup"><span data-stu-id="b6d97-217">Write-MbamRecoveryInformation</span></span>

-   <span data-ttu-id="b6d97-218">Read ADTpmInformation</span><span class="sxs-lookup"><span data-stu-id="b6d97-218">Read-ADTpmInformation</span></span>

-   <span data-ttu-id="b6d97-219">Read ADRecoveryInformation</span><span class="sxs-lookup"><span data-stu-id="b6d97-219">Read-ADRecoveryInformation</span></span>

-   <span data-ttu-id="b6d97-220">Write-MbamComputerUser</span><span class="sxs-lookup"><span data-stu-id="b6d97-220">Write-MbamComputerUser</span></span>

<span data-ttu-id="b6d97-221">以下参数已在 MBAM 2.5 SP1 的 Enable-MbamWebApplication 和 MbamWebApplication cmdlet 中实现：</span><span class="sxs-lookup"><span data-stu-id="b6d97-221">The following parameters have been implemented in the Enable-MbamWebApplication and Test-MbamWebApplication cmdlets for MBAM 2.5 SP1:</span></span>

-   <span data-ttu-id="b6d97-222">DataMigrationAccessGroup</span><span class="sxs-lookup"><span data-stu-id="b6d97-222">DataMigrationAccessGroup</span></span>

-   <span data-ttu-id="b6d97-223">TpmAutoUnlock</span><span class="sxs-lookup"><span data-stu-id="b6d97-223">TpmAutoUnlock</span></span>

<span data-ttu-id="b6d97-224">有关 cmdlet 的详细信息，请参阅[MBAM 2.5 安全注意事项](mbam-25-security-considerations.md)和[Microsoft Bitlocker 管理和监视 Cmdlet 帮助](https://technet.microsoft.com/library/dn720418.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b6d97-224">For information about the cmdlets, see [MBAM 2.5 Security Considerations](mbam-25-security-considerations.md) and [Microsoft Bitlocker Administration and Monitoring Cmdlet Help](https://technet.microsoft.com/library/dn720418.aspx).</span></span>

### <span data-ttu-id="b6d97-225">MBAM 代理检测演示模式</span><span class="sxs-lookup"><span data-stu-id="b6d97-225">MBAM agent detects presentation mode</span></span>

<span data-ttu-id="b6d97-226">MBAM 代理可以检测计算机何时处于演示模式，避免在此时调用 MBAM UI。</span><span class="sxs-lookup"><span data-stu-id="b6d97-226">The MBAM agent can detect when the computer is in presentation mode and avoid invoking the MBAM UI at that time.</span></span>

### <span data-ttu-id="b6d97-227">MBAM 代理服务现在配置为使用延迟启动</span><span class="sxs-lookup"><span data-stu-id="b6d97-227">MBAM agent service now configured to use delayed start</span></span>

<span data-ttu-id="b6d97-228">安装完成后，服务将立即将 MBAM 代理服务设置为使用延迟启动，减少启动 Windows 所需的时间量。</span><span class="sxs-lookup"><span data-stu-id="b6d97-228">After installation, the service will now set the MBAM agent service to use delayed start, decreasing the amount of time it takes to start Windows.</span></span>

### <span data-ttu-id="b6d97-229">已锁定的固定数据卷现在报告为合规</span><span class="sxs-lookup"><span data-stu-id="b6d97-229">Locked Fixed Data volumes now report as Compliant</span></span>

<span data-ttu-id="b6d97-230">"已锁定的固定数据" 卷的合规性计算逻辑已更改为将卷报告为 "合规"，但保护性状态和加密状态为 "Unknown"，并且具有 "卷已锁定" 的合规性状态详细信息。</span><span class="sxs-lookup"><span data-stu-id="b6d97-230">The compliance calculation logic for "Locked Fixed Data" volumes has been changed to report the volumes as "Compliant," but with a Protector State and Encryption State of "Unknown" and with a Compliance Status Detail of "Volume is locked".</span></span> <span data-ttu-id="b6d97-231">以前，锁定的卷被报告为 "不合规"、"已加密" 的保护程序状态、"Unknown" 的加密状态以及 "未知错误" 的符合性状态详细信息。</span><span class="sxs-lookup"><span data-stu-id="b6d97-231">Previously, locked volumes were reported as “Non-Compliant”, a Protector State of "Encrypted", an Encryption State of "Unknown", and a Compliance Status Detail of "An unknown error".</span></span>


## <span data-ttu-id="b6d97-232">如何获取 MDOP 技术</span><span class="sxs-lookup"><span data-stu-id="b6d97-232">How to Get MDOP Technologies</span></span>


<span data-ttu-id="b6d97-233">MBAM 是 Microsoft 桌面优化包（MDOP）的一部分。</span><span class="sxs-lookup"><span data-stu-id="b6d97-233">MBAM is a part of the Microsoft Desktop Optimization Pack (MDOP).</span></span> <span data-ttu-id="b6d97-234">MDOP 是 Microsoft 软件保障计划的一部分。</span><span class="sxs-lookup"><span data-stu-id="b6d97-234">MDOP is part of the Microsoft Software Assurance program.</span></span> <span data-ttu-id="b6d97-235">有关 Microsoft 软件保证计划以及如何获取 MDOP 的详细信息，请参阅[如何获取 mdop？](https://go.microsoft.com/fwlink/?LinkId=322049)。</span><span class="sxs-lookup"><span data-stu-id="b6d97-235">For more information about the Microsoft Software Assurance program and how to acquire the MDOP, see [How Do I Get MDOP?](https://go.microsoft.com/fwlink/?LinkId=322049).</span></span>

## <span data-ttu-id="b6d97-236">MBAM 2.5 SP1 发行说明</span><span class="sxs-lookup"><span data-stu-id="b6d97-236">MBAM 2.5 SP1 Release Notes</span></span>


<span data-ttu-id="b6d97-237">有关此文档中未包括的详细信息和最新新闻，请参阅[MBAM 2.5 SP1 的发行说明](release-notes-for-mbam-25-sp1.md)。</span><span class="sxs-lookup"><span data-stu-id="b6d97-237">For more information and late-breaking news that is not included in this documentation, see [Release Notes for MBAM 2.5 SP1](release-notes-for-mbam-25-sp1.md).</span></span>

## <span data-ttu-id="b6d97-238">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="b6d97-238">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="b6d97-239">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="b6d97-239">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="b6d97-240">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="b6d97-240">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>

## <span data-ttu-id="b6d97-241">相关主题</span><span class="sxs-lookup"><span data-stu-id="b6d97-241">Related topics</span></span>


[<span data-ttu-id="b6d97-242">Microsoft BitLocker 管理和监控 2.5</span><span class="sxs-lookup"><span data-stu-id="b6d97-242">Microsoft BitLocker Administration and Monitoring 2.5</span></span>](index.md)

[<span data-ttu-id="b6d97-243">MBAM 2.5 入门</span><span class="sxs-lookup"><span data-stu-id="b6d97-243">Getting Started with MBAM 2.5</span></span>](getting-started-with-mbam-25.md)

 

 





