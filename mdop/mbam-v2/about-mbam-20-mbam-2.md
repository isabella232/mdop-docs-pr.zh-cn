---
title: 关于 MBAM 2.0
description: 关于 MBAM 2.0
author: dansimp
ms.assetid: b43a0ba9-1c83-4854-a2c5-14eea0070e36
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7bdf24d1f375dd1fa8b18ac90c2fc49d2887c6c5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803544"
---
# <span data-ttu-id="47dab-103">关于 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="47dab-103">About MBAM 2.0</span></span>


<span data-ttu-id="47dab-104">Microsoft BitLockerAdministration 和监视（MBAM）2.0 为 BitLocker 驱动器加密提供了简化的管理接口。</span><span class="sxs-lookup"><span data-stu-id="47dab-104">Microsoft BitLockerAdministration and Monitoring(MBAM)2.0 provides a simplified administrative interface to BitLocker drive encryption.</span></span> <span data-ttu-id="47dab-105">对于丢失或被盗的计算机，BitLocker 提供增强的防护功能，防止数据失窃或数据暴露。</span><span class="sxs-lookup"><span data-stu-id="47dab-105">BitLocker offers enhanced protection against data theft or data exposure for computers that are lost or stolen.</span></span> <span data-ttu-id="47dab-106">BitLocker 将加密存储在 Windows 操作系统卷和已配置数据卷上的所有数据。</span><span class="sxs-lookup"><span data-stu-id="47dab-106">BitLocker encrypts all data that is stored on the Windows operating system volume and configured data volumes.</span></span>

## <span data-ttu-id="47dab-107">关于 MBAM 2。0</span><span class="sxs-lookup"><span data-stu-id="47dab-107">About MBAM2.0</span></span>


<span data-ttu-id="47dab-108">BitLockerAdministration 和 Monitoring 2.0 强制执行你为你的企业设置的 BitLocker 加密策略选项，监视客户端计算机与这些策略的合规性，并报告企业和个人计算机的加密状态。</span><span class="sxs-lookup"><span data-stu-id="47dab-108">BitLockerAdministration and Monitoring2.0 enforces the BitLocker encryption policy options that you set for your enterprise, monitors the compliance of client computers with those policies, and reports on the encryption status of both the enterprise and the individual computers.</span></span> <span data-ttu-id="47dab-109">此外，MBAM 允许你在用户忘记其 PIN 或密码时，或者在其 BIOS 或启动记录发生更改时访问恢复密钥信息。</span><span class="sxs-lookup"><span data-stu-id="47dab-109">In addition, MBAM lets you access the recovery key information when users forget their PIN or password, or when their BIOS or boot record changes.</span></span>

<span data-ttu-id="47dab-110">**注意** 本指南中未详细介绍 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="47dab-110">**Note** BitLocker is not covered in detail in this guide.</span></span> <span data-ttu-id="47dab-111">有关 BitLocker 的概述，请参阅[Bitlocker 驱动器加密概述](https://go.microsoft.com/fwlink/p/?LinkId=225013)。</span><span class="sxs-lookup"><span data-stu-id="47dab-111">For an overview of BitLocker, see [BitLocker Drive Encryption Overview](https://go.microsoft.com/fwlink/p/?LinkId=225013).</span></span>

 

<span data-ttu-id="47dab-112">以下组可能对使用 MBAM 管理 BitLocker 感兴趣：</span><span class="sxs-lookup"><span data-stu-id="47dab-112">The following groups might be interested in using MBAM to manage BitLocker:</span></span>

-   <span data-ttu-id="47dab-113">管理员、IT 安全专家和合规性监察官负责确保机密数据在未经授权的情况下不公开</span><span class="sxs-lookup"><span data-stu-id="47dab-113">Administrators, IT security professionals, and compliance officers who are responsible for ensuring that confidential data is not disclosed without authorization</span></span>

-   <span data-ttu-id="47dab-114">负责远程或分支办公室中的计算机安全的管理员</span><span class="sxs-lookup"><span data-stu-id="47dab-114">Administrators who are responsible for computer security in remote or branch offices</span></span>

-   <span data-ttu-id="47dab-115">负责运行 Windows 的客户端计算机的管理员</span><span class="sxs-lookup"><span data-stu-id="47dab-115">Administrators who are responsible for client computers that are running Windows</span></span>

## <a href="" id="what-s-new-in-mbam-2-0"></a><span data-ttu-id="47dab-116">MBAM 2.0 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="47dab-116">What’s New in MBAM2.0</span></span>


<span data-ttu-id="47dab-117">MBAM 2.0 提供以下新增功能和功能。</span><span class="sxs-lookup"><span data-stu-id="47dab-117">MBAM2.0 provides the following new features and functionality.</span></span>

### <span data-ttu-id="47dab-118">将 System Center Configuration Manager 与 MBAM 集成</span><span class="sxs-lookup"><span data-stu-id="47dab-118">Integration of System Center Configuration Manager with MBAM</span></span>

<span data-ttu-id="47dab-119">MBAM 现支持与 System Center Configuration Manager 集成。</span><span class="sxs-lookup"><span data-stu-id="47dab-119">MBAM now supports integration with System Center Configuration Manager.</span></span> <span data-ttu-id="47dab-120">此集成将 MBAM 合规基础结构移动到 Configuration Manager 的本机环境中。</span><span class="sxs-lookup"><span data-stu-id="47dab-120">This integration moves the MBAM compliance infrastructure into the native environment of Configuration Manager.</span></span> <span data-ttu-id="47dab-121">在企业中使用 Configuration Manager 的 IT 管理员现在可以在 Microsoft 管理控制台中查看其企业的合规性状态，并深入查看报表以查看个别计算机。</span><span class="sxs-lookup"><span data-stu-id="47dab-121">IT administrators who use Configuration Manager in their enterprise can now view the compliance status of their enterprise in the Microsoft Management Console and drill into reports to view individual computers.</span></span>

### <span data-ttu-id="47dab-122">硬件兼容性仅在 Configuration Manager 集成拓扑中可用</span><span class="sxs-lookup"><span data-stu-id="47dab-122">Hardware Compatibility is Available Only in the Configuration Manager Integration Topology</span></span>

<span data-ttu-id="47dab-123">将配置管理器与 MBAM 集成支持允许或禁止对某些硬件类型使用 MBAM 的配置管理器功能，并提供比 MBAM 1.0 中提供的硬件兼容性更大的灵活性。</span><span class="sxs-lookup"><span data-stu-id="47dab-123">Integrating Configuration Manager with MBAM enables Configuration Manager capabilities that allow or prohibit the use of certain hardware types with MBAM and provides more flexibility than the hardware compatibility that was available in MBAM 1.0.</span></span> <span data-ttu-id="47dab-124">IT 管理员可以创建自己的集合来限制硬件，并且可以将 MBAM 配置基线部署到这些集合。</span><span class="sxs-lookup"><span data-stu-id="47dab-124">IT administrators can create their own collections to limit hardware and can deploy the MBAM configuration baseline to those collections.</span></span> <span data-ttu-id="47dab-125">1.0 中显示的 MBAM 硬件兼容性现在仅在 MBAM Configuration Manager 拓扑中可用，并且从 Configuration Manager 管理。</span><span class="sxs-lookup"><span data-stu-id="47dab-125">The MBAM hardware compatibility that was present in MBAM 1.0 is now available only in the MBAM Configuration Manager topology and is administered from Configuration Manager.</span></span>

### <span data-ttu-id="47dab-126">保护灵活的策略</span><span class="sxs-lookup"><span data-stu-id="47dab-126">Protectors Flexible Policy</span></span>

<span data-ttu-id="47dab-127">已使用保护器加密的计算机（例如，TPM + PIN 或自动解锁和密码），并且接收需要该加密的子集的 MBAM 策略（例如，TPM 或自动解锁）被视为合规性。</span><span class="sxs-lookup"><span data-stu-id="47dab-127">Computers that are already encrypted with a protector (for example, TPM + PIN or Auto-Unlock and password) and that receive an MBAM policy that requires a subset of that encryption (for example, TPM or Auto-Unlock) are considered compliant.</span></span> <span data-ttu-id="47dab-128">在上述示例中，不会自动删除 PIN 和密码，除非 IT 管理员专门定义不再允许的这些功能。</span><span class="sxs-lookup"><span data-stu-id="47dab-128">In the example above, PIN and password would not be removed automatically unless the IT administrator specifically defines these features as no longer allowed.</span></span>

<span data-ttu-id="47dab-129">未加密且收到 MBAM 策略（例如，TPM 或自动解锁）的计算机会相应地加密。</span><span class="sxs-lookup"><span data-stu-id="47dab-129">Computers that are not encrypted and that receive an MBAM policy (for example, TPM or Auto-Unlock) are encrypted accordingly.</span></span> <span data-ttu-id="47dab-130">允许本地管理员的用户使用 BitLocker 工具（控制面板项 BitLocker 驱动器加密或 manage-bde）添加或修改现有保护器（例如，TPM + PIN 或自动解锁和密码）。</span><span class="sxs-lookup"><span data-stu-id="47dab-130">Users who are local administrators are allowed to use the BitLocker tools (Control Panel item BitLocker Drive Encryption or Manage-bde) to add or modify the existing protectors (for example, TPM + PIN or Auto-Unlock and password).</span></span> <span data-ttu-id="47dab-131">除非 MBAM 策略明确定义，否则它们保持合规。</span><span class="sxs-lookup"><span data-stu-id="47dab-131">They remain compliant unless MBAM policies specifically define them.</span></span>

### <span data-ttu-id="47dab-132">升级 MBAM 客户端的能力</span><span class="sxs-lookup"><span data-stu-id="47dab-132">Ability to Upgrade the MBAM Client</span></span>

<span data-ttu-id="47dab-133">MBAM 2.0 客户端 Windows 安装程序检测现有客户端的版本，并执行所需步骤以升级到以前版本的 MBAM 2.0 客户端。</span><span class="sxs-lookup"><span data-stu-id="47dab-133">The MBAM2.0 Client Windows Installer detects the version of the existing client and performs the required steps to upgrade to the MBAM2.0 Client from previous versions.</span></span>

### <span data-ttu-id="47dab-134">从早期版本升级 MBAM 服务器的功能</span><span class="sxs-lookup"><span data-stu-id="47dab-134">Ability to Upgrade the MBAM Server from Previous Versions</span></span>

<span data-ttu-id="47dab-135">你可以从早期版本的 MBAM 升级 MBAM 2.0 服务器基础结构，如下所示：</span><span class="sxs-lookup"><span data-stu-id="47dab-135">You can upgrade the MBAM2.0 Server infrastructure from previous versions of MBAM as follows:</span></span>

<span data-ttu-id="47dab-136">**手动就地服务器更换**-必须手动卸载现有的 MBAM 服务器基础结构，然后安装 MBAM 2.0 服务器基础结构。</span><span class="sxs-lookup"><span data-stu-id="47dab-136">**Manual in-place server replacement** – You must manually uninstall the existing MBAM server infrastructure, and then install the MBAM 2.0 Server infrastructure.</span></span> <span data-ttu-id="47dab-137">不必删除数据库即可进行升级。</span><span class="sxs-lookup"><span data-stu-id="47dab-137">You do not have to remove the databases to do the upgrade.</span></span> <span data-ttu-id="47dab-138">而是选择 MBAM 客户端的早期版本创建的现有数据库。</span><span class="sxs-lookup"><span data-stu-id="47dab-138">Instead, you select the existing databases, which the previous version of the MBAM Client created.</span></span> <span data-ttu-id="47dab-139">然后，MBAM 2.0 升级安装将现有数据库迁移到 MBAM 2.0。</span><span class="sxs-lookup"><span data-stu-id="47dab-139">The MBAM2.0 upgrade installation then migrates the existing databases to MBAM 2.0.</span></span>

<span data-ttu-id="47dab-140">**分布式客户端升级**-如果你使用的是独立的 MBAM 拓扑，则可以在安装 MBAM 2.0 服务器基础结构后逐步升级 MBAM 客户端。</span><span class="sxs-lookup"><span data-stu-id="47dab-140">**Distributed client upgrade** – If you are using the Stand-alone MBAM topology, you can upgrade the MBAM Clients gradually after you install the MBAM 2.0 Server infrastructure.</span></span> <span data-ttu-id="47dab-141">MBAM 2.0 服务器检测现有客户端的版本并执行升级到2.0 客户端所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="47dab-141">The MBAM 2.0 Server detects the version of the existing Client and performs the required steps to upgrade to the 2.0 Client.</span></span>

<span data-ttu-id="47dab-142">升级 MBAM 2.0 服务器基础结构后，MBAM 1.0 客户端会继续向 MBAM 2.0 服务器报告 escrowing 恢复数据，但合规性将基于 MBAM 1.0 中的策略。</span><span class="sxs-lookup"><span data-stu-id="47dab-142">After you upgrade the MBAM 2.0 Server infrastructure, MBAM 1.0 Clients continue to report to the MBAM 2.0 Server successfully, escrowing recovery data, but compliance will be based on the policies in MBAM 1.0.</span></span> <span data-ttu-id="47dab-143">必须将客户端升级到 MBAM 2.0 以使客户端计算机能够根据 MBAM 2.0 策略准确地报告合规性。</span><span class="sxs-lookup"><span data-stu-id="47dab-143">You must upgrade clients to MBAM 2.0 to have client computers accurately report compliance against the MBAM 2.0 policies.</span></span> <span data-ttu-id="47dab-144">你可以将客户端升级到 MBAM 2.0 客户端，而不卸载以前的客户端，并且客户端将开始应用和报告 MBAM 2.0 策略。</span><span class="sxs-lookup"><span data-stu-id="47dab-144">You can upgrade the clients to the MBAM 2.0 Client without uninstalling the previous client, and the client will start to apply and report MBAM 2.0 policies.</span></span>

<span data-ttu-id="47dab-145">如果你将 MBAM 与 Configuration Manager 配合使用，则必须将 MBAM 1.0 客户端升级到 MBAM 2.0。</span><span class="sxs-lookup"><span data-stu-id="47dab-145">If you are using MBAM with Configuration Manager, you must upgrade the MBAM 1.0 clients to MBAM 2.0.</span></span>

### <a href="" id="mbam-support-for-bitlocker-s-enterprise-scenarios-on-the-windows-8-platform"></a><span data-ttu-id="47dab-146">适用于 Windows 8 平台上的 BitLocker 企业方案的 MBAM 支持</span><span class="sxs-lookup"><span data-stu-id="47dab-146">MBAM Support for BitLocker’s Enterprise Scenarios on the Windows 8 Platform</span></span>

<span data-ttu-id="47dab-147">MBAM 支持 Windows 8 操作系统作为 MBAM 客户端安装的目标平台。</span><span class="sxs-lookup"><span data-stu-id="47dab-147">MBAM supports the Windows 8 operating system as a target platform for the MBAM Client installation.</span></span> <span data-ttu-id="47dab-148">此支持使 IT 管理员能够安装 MBAM 代理、加密 Windows 8 操作系统驱动器以及报告计算机合规性。</span><span class="sxs-lookup"><span data-stu-id="47dab-148">This support enables IT administrators to install the MBAM agent, to encrypt Windows 8 operating system drives, and to report on the compliance of the computers.</span></span> <span data-ttu-id="47dab-149">MBAM 利用 TPM 和 TPM + PIN 保护器管理 Windows 8 操作系统，就像处理 Windows 7 操作系统一样。</span><span class="sxs-lookup"><span data-stu-id="47dab-149">MBAM leverages the TPM and TPM+PIN protectors to manage the Windows 8 operating system just as it does the Windows 7 operating system.</span></span> <span data-ttu-id="47dab-150">MBAM 2.0 还添加了对加密 Windows To Go 客户端的支持。</span><span class="sxs-lookup"><span data-stu-id="47dab-150">MBAM2.0 also adds support for encrypting Windows To Go clients.</span></span>

### <span data-ttu-id="47dab-151">自助服务门户的添加</span><span class="sxs-lookup"><span data-stu-id="47dab-151">Addition of the Self-Service Portal</span></span>

<span data-ttu-id="47dab-152">最终用户现在可以使用自助服务门户来恢复其恢复密钥。</span><span class="sxs-lookup"><span data-stu-id="47dab-152">End users can now use the Self-Service Portal to recover their recovery keys.</span></span> <span data-ttu-id="47dab-153">自助服务门户可以在具有其他 MBAM 功能的单个服务器上部署，或者在单独的服务器上，让 IT 管理员能够灵活地根据需要向用户公开自助服务器门户。</span><span class="sxs-lookup"><span data-stu-id="47dab-153">The Self-Service Portal can be deployed on a single server with the other MBAM features, or on a separate server that gives IT administrators the flexibility to expose the Self-Server Portal to users, as required.</span></span> <span data-ttu-id="47dab-154">在自助服务门户对用户进行身份验证后，用户只需输入恢复密钥 ID 的前八位数字即可接收其恢复密钥。</span><span class="sxs-lookup"><span data-stu-id="47dab-154">After the Self-Service Portal authenticates users, users have to enter only the first eight digits of the recovery key ID to receive their recovery key.</span></span>

<span data-ttu-id="47dab-155">MBAM 还通过允许用户仅恢复他们为其用户的计算机来恢复密钥，从而降低其他用户获得未经授权访问权限的风险。</span><span class="sxs-lookup"><span data-stu-id="47dab-155">MBAM also secures the key by allowing users to recover keys only for those computers on which they are users, which reduces the risk that other users gain unauthorized access.</span></span>

### <span data-ttu-id="47dab-156">从暂停状态自动恢复 BitLocker 保护的功能</span><span class="sxs-lookup"><span data-stu-id="47dab-156">Ability to Automatically Resume BitLocker Protection from a Suspended State</span></span>

<span data-ttu-id="47dab-157">MBAM 不再允许 IT 管理员在长时间内暂停和不保护 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="47dab-157">MBAM no longer allows IT administrators to keep BitLocker suspended and unprotected for prolonged periods of time.</span></span> <span data-ttu-id="47dab-158">如果 IT 管理员暂停 BitLocker，MBAM 会在重新启动计算机时自动重新启用它，从而降低计算机受攻击的风险。</span><span class="sxs-lookup"><span data-stu-id="47dab-158">If an IT administrator suspends BitLocker, MBAM re-enables it automatically when the computer is rebooted, which reduces the risk that the computer can be attacked.</span></span>

### <span data-ttu-id="47dab-159">固定数据驱动器可以配置为在没有密码的情况下自动解锁</span><span class="sxs-lookup"><span data-stu-id="47dab-159">Fixed Data Drives Can Be Configured to Automatically Unlock Without a Password</span></span>

<span data-ttu-id="47dab-160">现可将固定数据驱动器（FDD）策略配置为允许不使用密码自动解锁驱动器。</span><span class="sxs-lookup"><span data-stu-id="47dab-160">A Fixed Data Drive (FDD) policy can now be configured to allow automatic unlocking of the drive without a password.</span></span> <span data-ttu-id="47dab-161">在加密 FDD 之前，系统不会提示用户输入密码，并且 FDD 将受到保护，并使用操作系统驱动器自动解锁。</span><span class="sxs-lookup"><span data-stu-id="47dab-161">Users are not prompted for a password before the FDD is encrypted, and the FDD will be secured and auto-unlocked with the operating system drive.</span></span>

## <a href="" id="---------mbam-2-0-release-notes"></a> <span data-ttu-id="47dab-162">MBAM 2.0 发行说明</span><span class="sxs-lookup"><span data-stu-id="47dab-162">MBAM2.0 Release Notes</span></span>


<span data-ttu-id="47dab-163">有关详细信息以及文档中未包含的最新新闻，请参阅[MBAM 2.0 的发行说明](release-notes-for-mbam-20-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="47dab-163">For more information, and for late-breaking news that is not included in the documentation, see the [Release Notes for MBAM 2.0](release-notes-for-mbam-20-mbam-2.md).</span></span>

## <span data-ttu-id="47dab-164">如何获取 MBAM 2。0</span><span class="sxs-lookup"><span data-stu-id="47dab-164">How to Get MBAM2.0</span></span>


<span data-ttu-id="47dab-165">此技术是 Microsoft 桌面优化包（MDOP）的一部分。</span><span class="sxs-lookup"><span data-stu-id="47dab-165">This technology is a part of the Microsoft Desktop Optimization Pack (MDOP).</span></span> <span data-ttu-id="47dab-166">企业客户可以通过 Microsoft 软件保障获得 MDOP。</span><span class="sxs-lookup"><span data-stu-id="47dab-166">Enterprise customers can get MDOP with Microsoft Software Assurance.</span></span> <span data-ttu-id="47dab-167">有关 Microsoft 软件保证和获取 MDOP 的详细信息，请参阅[如何获取 mdop？](https://go.microsoft.com/fwlink/p/?LinkId=322049)</span><span class="sxs-lookup"><span data-stu-id="47dab-167">For more information about Microsoft Software Assurance and acquiring MDOP, see [How Do I Get MDOP?](https://go.microsoft.com/fwlink/p/?LinkId=322049)</span></span>

## <span data-ttu-id="47dab-168">相关主题</span><span class="sxs-lookup"><span data-stu-id="47dab-168">Related topics</span></span>


[<span data-ttu-id="47dab-169">MBAM 2.0 入门</span><span class="sxs-lookup"><span data-stu-id="47dab-169">Getting Started with MBAM 2.0</span></span>](getting-started-with-mbam-20-mbam-2.md)

 

 





