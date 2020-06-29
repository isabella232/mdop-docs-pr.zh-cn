---
title: 如何通过使用 MBAM 将 BitLocker 作为 Windows 部署的一部分来启用
description: 如何通过使用 MBAM 将 BitLocker 作为 Windows 部署的一部分来启用
author: dansimp
ms.assetid: 7609ad7a-bb06-47be-b186-0a2db787c8a5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 04/23/2017
ms.openlocfilehash: 4b2cbf333c705088d0a068521fb65e99551bb1f1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803926"
---
# <span data-ttu-id="4d5da-103">如何通过使用 MBAM 将 BitLocker 作为 Windows 部署的一部分来启用</span><span class="sxs-lookup"><span data-stu-id="4d5da-103">How to Enable BitLocker by Using MBAM as Part of a Windows Deployment</span></span>


<span data-ttu-id="4d5da-104">本主题介绍如何通过将 MBAM 用作 Windows 映像和部署过程的一部分，在最终用户的计算机上启用 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="4d5da-104">This topic explains how to enable BitLocker on an end user's computer by using MBAM as part of your Windows imaging and deployment process.</span></span> <span data-ttu-id="4d5da-105">如果你在重启时看到黑屏（安装阶段结束后），指示无法解锁驱动器，请参阅[如果预配 BitLocker 与 Windows 10 版本1511一起使用，则不会在 "安装 windows 和配置管理器" 步骤之后开始使用较早的 Windows 版本](https://support.microsoft.com/en-us/help/4494799/earlier-windows-versions-don-t-start-after-you-use-pre-provision-bitlo)。</span><span class="sxs-lookup"><span data-stu-id="4d5da-105">If you see a black screen at restart (after Install phase concludes) indicating that the drive cannot be unlocked, see [Earlier Windows versions don't start after "Setup Windows and Configuration Manager" step if Pre-Provision BitLocker is used with Windows 10, version 1511](https://support.microsoft.com/en-us/help/4494799/earlier-windows-versions-don-t-start-after-you-use-pre-provision-bitlo).</span></span>

**<span data-ttu-id="4d5da-106">先决条件：</span><span class="sxs-lookup"><span data-stu-id="4d5da-106">Prerequisites:</span></span>**

-   <span data-ttu-id="4d5da-107">现有的 Windows 映像部署过程– Microsoft 部署工具包（MDT）、Microsoft System Center Configuration Manager 或其他映像工具或进程-必须放置</span><span class="sxs-lookup"><span data-stu-id="4d5da-107">An existing Windows image deployment process – Microsoft Deployment Toolkit (MDT), Microsoft System Center Configuration Manager, or some other imaging tool or process – must be in place</span></span>

-   <span data-ttu-id="4d5da-108">必须在 BIOS 中启用 TPM，并且操作系统可见</span><span class="sxs-lookup"><span data-stu-id="4d5da-108">TPM must be enabled in the BIOS and visible to the OS</span></span>

-   <span data-ttu-id="4d5da-109">MBAM 服务器基础结构必须到位且易于访问</span><span class="sxs-lookup"><span data-stu-id="4d5da-109">MBAM server infrastructure must be in place and accessible</span></span>

-   <span data-ttu-id="4d5da-110">必须创建 BitLocker 所需的系统分区</span><span class="sxs-lookup"><span data-stu-id="4d5da-110">The system partition required by BitLocker must be created</span></span>

-   <span data-ttu-id="4d5da-111">在 MBAM 中，计算机必须加入域才能完全启用 BitLocker</span><span class="sxs-lookup"><span data-stu-id="4d5da-111">The machine must be domain joined during imaging before MBAM fully enables BitLocker</span></span>

**<span data-ttu-id="4d5da-112">在 Windows 部署中使用 MBAM 2.5 SP1 启用 BitLocker</span><span class="sxs-lookup"><span data-stu-id="4d5da-112">To enable BitLocker using MBAM 2.5 SP1 as part of a Windows deployment</span></span>**

1. <span data-ttu-id="4d5da-113">在 MBAM 2.5 SP1 中，建议用于在 Windows 部署期间启用 BitLocker 的方法是使用 `Invoke-MbamClientDeployment.ps1` PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="4d5da-113">In MBAM 2.5 SP1, the recommended approach to enable BitLocker during a Windows Deployment is by using the `Invoke-MbamClientDeployment.ps1` PowerShell script.</span></span>

   -   <span data-ttu-id="4d5da-114">`Invoke-MbamClientDeployment.ps1`脚本在映像过程中 Enacts BitLocker。</span><span class="sxs-lookup"><span data-stu-id="4d5da-114">The `Invoke-MbamClientDeployment.ps1` script enacts BitLocker during the imaging process.</span></span> <span data-ttu-id="4d5da-115">当 BitLocker 策略需要时，MBAM 代理会立即提示域用户在域用户第一次登录后进行映像时创建 PIN 或密码。</span><span class="sxs-lookup"><span data-stu-id="4d5da-115">When required by BitLocker policy, the MBAM agent immediately prompts the domain user to create a PIN or password when the domain user first logs on after imaging.</span></span>

   -   <span data-ttu-id="4d5da-116">易于与 MDT、System Center Configuration Manager 或独立成像进程一起使用</span><span class="sxs-lookup"><span data-stu-id="4d5da-116">Easy to use with MDT, System Center Configuration Manager, or standalone imaging processes</span></span>

   -   <span data-ttu-id="4d5da-117">与 PowerShell 2.0 或更高版本兼容</span><span class="sxs-lookup"><span data-stu-id="4d5da-117">Compatible with PowerShell 2.0 or higher</span></span>

   -   <span data-ttu-id="4d5da-118">用 TPM 密钥保护程序加密操作系统卷</span><span class="sxs-lookup"><span data-stu-id="4d5da-118">Encrypt OS volume with TPM key protector</span></span>

   -   <span data-ttu-id="4d5da-119">完全支持 BitLocker 预配</span><span class="sxs-lookup"><span data-stu-id="4d5da-119">Fully support BitLocker pre-provisioning</span></span>

   -   <span data-ttu-id="4d5da-120">（可选）加密 FDDs</span><span class="sxs-lookup"><span data-stu-id="4d5da-120">Optionally encrypt FDDs</span></span>

   -   <span data-ttu-id="4d5da-121">托管 TPM OwnerAuth For Windows 7，MBAM 必须拥有 TPM 才能进行保管。</span><span class="sxs-lookup"><span data-stu-id="4d5da-121">Escrow TPM OwnerAuth For Windows 7, MBAM must own the TPM for escrow to occur.</span></span>
   <span data-ttu-id="4d5da-122">对于 Windows 8.1、Windows 10 RTM 和 Windows 10 版本1511，支持对 TPM OwnerAuth 进行托管。</span><span class="sxs-lookup"><span data-stu-id="4d5da-122">For Windows 8.1, Windows 10 RTM and Windows 10 version 1511, escrow of TPM OwnerAuth is supported.</span></span>
   <span data-ttu-id="4d5da-123">对于 Windows 10 版本1607或更高版本，只有 Windows 可以获得 TPM 的所有权。</span><span class="sxs-lookup"><span data-stu-id="4d5da-123">For Windows 10, version 1607 or later, only Windows can take ownership of the TPM.</span></span> <span data-ttu-id="4d5da-124">在 addiiton 中，Windows 将不会在预配 TPM 时保留 TPM 所有者密码。</span><span class="sxs-lookup"><span data-stu-id="4d5da-124">In addiiton, Windows will not retain the TPM owner password when provisioning the TPM.</span></span> <span data-ttu-id="4d5da-125">有关进一步的详细信息，请参阅[TPM 所有者密码](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password)。</span><span class="sxs-lookup"><span data-stu-id="4d5da-125">See [TPM owner password](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password) for further details.</span></span>

   -   <span data-ttu-id="4d5da-126">托管恢复密钥和恢复密钥程序包</span><span class="sxs-lookup"><span data-stu-id="4d5da-126">Escrow recovery keys and recovery key packages</span></span>

   -   <span data-ttu-id="4d5da-127">立即报告加密状态</span><span class="sxs-lookup"><span data-stu-id="4d5da-127">Report encryption status immediately</span></span>

   -   <span data-ttu-id="4d5da-128">新的 WMI 提供程序</span><span class="sxs-lookup"><span data-stu-id="4d5da-128">New WMI providers</span></span>

   -   <span data-ttu-id="4d5da-129">详细日志记录</span><span class="sxs-lookup"><span data-stu-id="4d5da-129">Detailed logging</span></span>

   -   <span data-ttu-id="4d5da-130">强健的错误处理</span><span class="sxs-lookup"><span data-stu-id="4d5da-130">Robust error handling</span></span>

   <span data-ttu-id="4d5da-131">你可以 `Invoke-MbamClientDeployment.ps1` 从[Microsoft.com 下载中心](https://www.microsoft.com/download/details.aspx?id=54439)下载脚本。</span><span class="sxs-lookup"><span data-stu-id="4d5da-131">You can download the `Invoke-MbamClientDeployment.ps1` script from [Microsoft.com Download Center](https://www.microsoft.com/download/details.aspx?id=54439).</span></span> <span data-ttu-id="4d5da-132">这是你的部署系统将调用以配置 BitLocker 驱动器加密的主脚本，并将恢复密钥与 MBAM 服务器一起记录。</span><span class="sxs-lookup"><span data-stu-id="4d5da-132">This is the main script that your deployment system will call to configure BitLocker drive encryption and record recovery keys with the MBAM Server.</span></span>

   <span data-ttu-id="4d5da-133">**MBAM 的 WMI 部署方法：** 在 MBAM 2.5 SP1 中添加了以下 WMI 方法以支持使用 `Invoke-MbamClientDeployment.ps1` PowerShell 脚本启用 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="4d5da-133">**WMI deployment methods for MBAM:** The following WMI methods have been added in MBAM 2.5 SP1 to support enabling BitLocker by using the `Invoke-MbamClientDeployment.ps1` PowerShell script.</span></span>

   <a href="" id="mbam-machine-wmi-class"></a><span data-ttu-id="4d5da-134">**MBAM \ _MACHINE WMI 类** 
   **PrepareTpmAndEscrowOwnerAuth：** 使用 MBAM 恢复服务读取 TPM OwnerAuth 并将其发送到 MBAM 恢复数据库。</span><span class="sxs-lookup"><span data-stu-id="4d5da-134">**MBAM\_Machine WMI Class**
**PrepareTpmAndEscrowOwnerAuth:** Reads the TPM OwnerAuth and sends it to the MBAM recovery database by using the MBAM recovery service.</span></span> <span data-ttu-id="4d5da-135">如果 TPM 未拥有且自动预配未打开，它将生成一个 TPM OwnerAuth 并取得所有权。</span><span class="sxs-lookup"><span data-stu-id="4d5da-135">If the TPM is not owned and auto-provisioning is not on, it generates a TPM OwnerAuth and takes ownership.</span></span> <span data-ttu-id="4d5da-136">如果失败，将返回错误代码进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="4d5da-136">If it fails, an error code is returned for troubleshooting.</span></span>

   <span data-ttu-id="4d5da-137">**注意**对于 Windows 10 版本1607或更高版本，只有 Windows 可以获得 TPM 的所有权。</span><span class="sxs-lookup"><span data-stu-id="4d5da-137">**Note** For Windows 10, version 1607 or later, only Windows can take ownership of the TPM.</span></span> <span data-ttu-id="4d5da-138">在 addiiton 中，Windows 将不会在预配 TPM 时保留 TPM 所有者密码。</span><span class="sxs-lookup"><span data-stu-id="4d5da-138">In addiiton, Windows will not retain the TPM owner password when provisioning the TPM.</span></span> <span data-ttu-id="4d5da-139">有关进一步的详细信息，请参阅[TPM 所有者密码](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password)。</span><span class="sxs-lookup"><span data-stu-id="4d5da-139">See [TPM owner password](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password) for further details.</span></span>

| <span data-ttu-id="4d5da-140">参数</span><span class="sxs-lookup"><span data-stu-id="4d5da-140">Parameter</span></span> | <span data-ttu-id="4d5da-141">描述</span><span class="sxs-lookup"><span data-stu-id="4d5da-141">Description</span></span> |
| -------- | ----------- |
| <span data-ttu-id="4d5da-142">RecoveryServiceEndPoint</span><span class="sxs-lookup"><span data-stu-id="4d5da-142">RecoveryServiceEndPoint</span></span> | <span data-ttu-id="4d5da-143">指定 MBAM 恢复服务终结点的字符串。</span><span class="sxs-lookup"><span data-stu-id="4d5da-143">A string specifying the MBAM recovery service endpoint.</span></span> |

<span data-ttu-id="4d5da-144">下面是常见错误消息的列表：</span><span class="sxs-lookup"><span data-stu-id="4d5da-144">Here are a list of common error messages:</span></span>

| <span data-ttu-id="4d5da-145">常见返回值</span><span class="sxs-lookup"><span data-stu-id="4d5da-145">Common return values</span></span> | <span data-ttu-id="4d5da-146">错误消息</span><span class="sxs-lookup"><span data-stu-id="4d5da-146">Error message</span></span> |
| -------------------- | ------------- |
|  **<span data-ttu-id="4d5da-147">S_OK</span><span class="sxs-lookup"><span data-stu-id="4d5da-147">S_OK</span></span>**<br /><span data-ttu-id="4d5da-148">0（0x0）</span><span class="sxs-lookup"><span data-stu-id="4d5da-148">0 (0x0)</span></span> | <span data-ttu-id="4d5da-149">该方法成功。</span><span class="sxs-lookup"><span data-stu-id="4d5da-149">The method was successful.</span></span> |
| **<span data-ttu-id="4d5da-150">MBAM_E_TPM_NOT_PRESENT</span><span class="sxs-lookup"><span data-stu-id="4d5da-150">MBAM_E_TPM_NOT_PRESENT</span></span>**<br /><span data-ttu-id="4d5da-151">2147746304（0x80040200）</span><span class="sxs-lookup"><span data-stu-id="4d5da-151">2147746304 (0x80040200)</span></span> | <span data-ttu-id="4d5da-152">计算机中不存在 TPM，或者 BIOS 配置中已禁用 TPM。</span><span class="sxs-lookup"><span data-stu-id="4d5da-152">TPM is not present in the computer or is disabled in the BIOS configuration.</span></span> |
| **<span data-ttu-id="4d5da-153">MBAM_E_TPM_INCORRECT_STATE</span><span class="sxs-lookup"><span data-stu-id="4d5da-153">MBAM_E_TPM_INCORRECT_STATE</span></span>**<br /><span data-ttu-id="4d5da-154">2147746305（0x80040201）</span><span class="sxs-lookup"><span data-stu-id="4d5da-154">2147746305 (0x80040201)</span></span> | <span data-ttu-id="4d5da-155">TPM 的状态不正确（启用、激活且允许所有者安装）。</span><span class="sxs-lookup"><span data-stu-id="4d5da-155">TPM is not in the correct state (enabled, activated and owner installation allowed).</span></span> |
| **<span data-ttu-id="4d5da-156">MBAM_E_TPM_AUTO_PROVISIONING_PENDING</span><span class="sxs-lookup"><span data-stu-id="4d5da-156">MBAM_E_TPM_AUTO_PROVISIONING_PENDING</span></span>**<br /><span data-ttu-id="4d5da-157">2147746306（0x80040202）</span><span class="sxs-lookup"><span data-stu-id="4d5da-157">2147746306 (0x80040202)</span></span> | <span data-ttu-id="4d5da-158">MBAM 无法取得 TPM 的所有权，因为自动设置处于挂起状态。</span><span class="sxs-lookup"><span data-stu-id="4d5da-158">MBAM cannot take ownership of TPM because auto-provisioning is pending.</span></span> <span data-ttu-id="4d5da-159">自动预配完成后重试。</span><span class="sxs-lookup"><span data-stu-id="4d5da-159">Try again after auto-provisioning is completed.</span></span> |
| **<span data-ttu-id="4d5da-160">MBAM_E_TPM_OWNERAUTH_READFAIL</span><span class="sxs-lookup"><span data-stu-id="4d5da-160">MBAM_E_TPM_OWNERAUTH_READFAIL</span></span>**<br /><span data-ttu-id="4d5da-161">2147746307（0x80040203）</span><span class="sxs-lookup"><span data-stu-id="4d5da-161">2147746307 (0x80040203)</span></span> | <span data-ttu-id="4d5da-162">MBAM 无法读取 TPM 所有者授权值。</span><span class="sxs-lookup"><span data-stu-id="4d5da-162">MBAM cannot read the TPM owner authorization value.</span></span> <span data-ttu-id="4d5da-163">此值可能已在成功托管后删除。</span><span class="sxs-lookup"><span data-stu-id="4d5da-163">The value might have been removed after a successful escrow.</span></span> <span data-ttu-id="4d5da-164">在 Windows 7 中，如果 TPM 归其他人所有，MBAM 无法读取该值。</span><span class="sxs-lookup"><span data-stu-id="4d5da-164">On Windows 7, MBAM cannot read the value if the TPM is owned by others.</span></span> |
| **<span data-ttu-id="4d5da-165">MBAM_E_REBOOT_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="4d5da-165">MBAM_E_REBOOT_REQUIRED</span></span>**<br /><span data-ttu-id="4d5da-166">2147746308（0x80040204）</span><span class="sxs-lookup"><span data-stu-id="4d5da-166">2147746308 (0x80040204)</span></span> | <span data-ttu-id="4d5da-167">必须重新启动计算机才能将 TPM 设置为正确状态。</span><span class="sxs-lookup"><span data-stu-id="4d5da-167">The computer must be restarted to set TPM to the correct state.</span></span> <span data-ttu-id="4d5da-168">您可能需要手动重启计算机。</span><span class="sxs-lookup"><span data-stu-id="4d5da-168">You might need to manually reboot the computer.</span></span> |
| **<span data-ttu-id="4d5da-169">MBAM_E_SHUTDOWN_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="4d5da-169">MBAM_E_SHUTDOWN_REQUIRED</span></span>**<br /><span data-ttu-id="4d5da-170">2147746309（0x80040205）</span><span class="sxs-lookup"><span data-stu-id="4d5da-170">2147746309 (0x80040205)</span></span> | <span data-ttu-id="4d5da-171">计算机必须关闭并重新打开，才能将 TPM 设置为正确状态。</span><span class="sxs-lookup"><span data-stu-id="4d5da-171">The computer must be shut down and turned back on to set TPM to the correct state.</span></span> <span data-ttu-id="4d5da-172">您可能需要手动重启计算机。</span><span class="sxs-lookup"><span data-stu-id="4d5da-172">You might need to manually reboot the computer.</span></span> |
| **<span data-ttu-id="4d5da-173">WS_E_ENDPOINT_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="4d5da-173">WS_E_ENDPOINT_ACCESS_DENIED</span></span>**<br /><span data-ttu-id="4d5da-174">2151481349（0x803D0005）</span><span class="sxs-lookup"><span data-stu-id="4d5da-174">2151481349 (0x803D0005)</span></span> | <span data-ttu-id="4d5da-175">远程终结点拒绝访问。</span><span class="sxs-lookup"><span data-stu-id="4d5da-175">Access was denied by the remote endpoint.</span></span> |
| **<span data-ttu-id="4d5da-176">WS_E_ENDPOINT_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="4d5da-176">WS_E_ENDPOINT_NOT_FOUND</span></span>**<br /><span data-ttu-id="4d5da-177">2151481357（0x803D000D）</span><span class="sxs-lookup"><span data-stu-id="4d5da-177">2151481357 (0x803D000D)</span></span> | <span data-ttu-id="4d5da-178">远程终结点不存在或无法定位。</span><span class="sxs-lookup"><span data-stu-id="4d5da-178">The remote endpoint does not exist or could not be located.</span></span> |
| <span data-ttu-id="4d5da-179">\* \* WS_E_ENDPOINT_FAILURE</span><span class="sxs-lookup"><span data-stu-id="4d5da-179">\*\*WS_E_ENDPOINT_FAILURE</span></span><br /><span data-ttu-id="4d5da-180">2151481357（0x803D000F）</span><span class="sxs-lookup"><span data-stu-id="4d5da-180">2151481357 (0x803D000F)</span></span> | <span data-ttu-id="4d5da-181">远程终结点无法处理请求。</span><span class="sxs-lookup"><span data-stu-id="4d5da-181">The remote endpoint could not process the request.</span></span> |
| **<span data-ttu-id="4d5da-182">WS_E_ENDPOINT_UNREACHABLE</span><span class="sxs-lookup"><span data-stu-id="4d5da-182">WS_E_ENDPOINT_UNREACHABLE</span></span>**<br /><span data-ttu-id="4d5da-183">2151481360（0x803D0010）</span><span class="sxs-lookup"><span data-stu-id="4d5da-183">2151481360 (0x803D0010)</span></span> | <span data-ttu-id="4d5da-184">无法访问远程终结点。</span><span class="sxs-lookup"><span data-stu-id="4d5da-184">The remote endpoint was not reachable.</span></span> |
| **<span data-ttu-id="4d5da-185">WS_E_ENDPOINT_FAULT_RECEIVED</span><span class="sxs-lookup"><span data-stu-id="4d5da-185">WS_E_ENDPOINT_FAULT_RECEIVED</span></span>**<br /><span data-ttu-id="4d5da-186">2151481363（0x803D0013）</span><span class="sxs-lookup"><span data-stu-id="4d5da-186">2151481363 (0x803D0013)</span></span> | <span data-ttu-id="4d5da-187">从远程终结点收到包含错误的消息。</span><span class="sxs-lookup"><span data-stu-id="4d5da-187">A message containing a fault was received from the remote endpoint.</span></span> <span data-ttu-id="4d5da-188">请确保连接到正确的服务终结点。</span><span class="sxs-lookup"><span data-stu-id="4d5da-188">Make sure you are connecting to the correct service endpoint.</span></span> |
| <span data-ttu-id="4d5da-189">**WS_E_INVALID_ENDPOINT_URL** 2151481376 （0x803D0020）</span><span class="sxs-lookup"><span data-stu-id="4d5da-189">**WS_E_INVALID_ENDPOINT_URL** 2151481376 (0x803D0020)</span></span> | <span data-ttu-id="4d5da-190">终结点地址 URL 无效。</span><span class="sxs-lookup"><span data-stu-id="4d5da-190">The endpoint address URL is not valid.</span></span> <span data-ttu-id="4d5da-191">URL 必须以 "http" 或 "https" 开头。</span><span class="sxs-lookup"><span data-stu-id="4d5da-191">The URL must start with “http” or “https”.</span></span> |

   <span data-ttu-id="4d5da-192">**ReportStatus：** 通过使用 MBAM 状态报告服务，读取卷的合规性状态并将其发送到 MBAM 合规性状态数据库。</span><span class="sxs-lookup"><span data-stu-id="4d5da-192">**ReportStatus:** Reads the compliance status of the volume and sends it to the MBAM compliance status database by using the MBAM status reporting service.</span></span> <span data-ttu-id="4d5da-193">状态包括密码强度、保护程序类型、保护程序状态和加密状态。</span><span class="sxs-lookup"><span data-stu-id="4d5da-193">The status includes cipher strength, protector type, protector state and encryption state.</span></span> <span data-ttu-id="4d5da-194">如果失败，将返回错误代码进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="4d5da-194">If it fails, an error code is returned for troubleshooting.</span></span>

   | <span data-ttu-id="4d5da-195">参数</span><span class="sxs-lookup"><span data-stu-id="4d5da-195">Parameter</span></span> | <span data-ttu-id="4d5da-196">描述</span><span class="sxs-lookup"><span data-stu-id="4d5da-196">Description</span></span> |
   | --------- | ----------- |
   | <span data-ttu-id="4d5da-197">ReportingServiceEndPoint</span><span class="sxs-lookup"><span data-stu-id="4d5da-197">ReportingServiceEndPoint</span></span> | <span data-ttu-id="4d5da-198">指定 MBAM 状态报告服务终结点的字符串。</span><span class="sxs-lookup"><span data-stu-id="4d5da-198">A string specifying the MBAM status reporting service endpoint.</span></span> |

   <span data-ttu-id="4d5da-199">下面是常见错误消息的列表：</span><span class="sxs-lookup"><span data-stu-id="4d5da-199">Here are a list of common error messages:</span></span>

   | <span data-ttu-id="4d5da-200">常见返回值</span><span class="sxs-lookup"><span data-stu-id="4d5da-200">Common return values</span></span> | <span data-ttu-id="4d5da-201">错误消息</span><span class="sxs-lookup"><span data-stu-id="4d5da-201">Error message</span></span> |
   | -------------------- | ------------- |
   | **<span data-ttu-id="4d5da-202">S_OK</span><span class="sxs-lookup"><span data-stu-id="4d5da-202">S_OK</span></span>**<br /> <span data-ttu-id="4d5da-203">0（0x0）</span><span class="sxs-lookup"><span data-stu-id="4d5da-203">0 (0x0)</span></span> | <span data-ttu-id="4d5da-204">该方法成功</span><span class="sxs-lookup"><span data-stu-id="4d5da-204">The method was successful</span></span> |
   | **<span data-ttu-id="4d5da-205">WS_E_ENDPOINT_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="4d5da-205">WS_E_ENDPOINT_ACCESS_DENIED</span></span>**<br /><span data-ttu-id="4d5da-206">2151481349（0x803D0005）</span><span class="sxs-lookup"><span data-stu-id="4d5da-206">2151481349 (0x803D0005)</span></span> | <span data-ttu-id="4d5da-207">远程终结点拒绝访问。</span><span class="sxs-lookup"><span data-stu-id="4d5da-207">Access was denied by the remote endpoint.</span></span>|
   | **<span data-ttu-id="4d5da-208">WS_E_ENDPOINT_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="4d5da-208">WS_E_ENDPOINT_NOT_FOUND</span></span>**<br /><span data-ttu-id="4d5da-209">2151481357（0x803D000D）</span><span class="sxs-lookup"><span data-stu-id="4d5da-209">2151481357 (0x803D000D)</span></span> | <span data-ttu-id="4d5da-210">远程终结点不存在或无法定位。</span><span class="sxs-lookup"><span data-stu-id="4d5da-210">The remote endpoint does not exist or could not be located.</span></span> |
   | **<span data-ttu-id="4d5da-211">WS_E_ENDPOINT_FAILURE</span><span class="sxs-lookup"><span data-stu-id="4d5da-211">WS_E_ENDPOINT_FAILURE</span></span>**<br /> <span data-ttu-id="4d5da-212">2151481357（0x803D000F）</span><span class="sxs-lookup"><span data-stu-id="4d5da-212">2151481357 (0x803D000F)</span></span> | <span data-ttu-id="4d5da-213">远程终结点无法处理请求。</span><span class="sxs-lookup"><span data-stu-id="4d5da-213">The remote endpoint could not process the request.</span></span> |
   | **<span data-ttu-id="4d5da-214">WS_E_ENDPOINT_UNREACHABLE</span><span class="sxs-lookup"><span data-stu-id="4d5da-214">WS_E_ENDPOINT_UNREACHABLE</span></span>**<br /><span data-ttu-id="4d5da-215">2151481360（0x803D0010）</span><span class="sxs-lookup"><span data-stu-id="4d5da-215">2151481360 (0x803D0010)</span></span> | <span data-ttu-id="4d5da-216">无法访问远程终结点。</span><span class="sxs-lookup"><span data-stu-id="4d5da-216">The remote endpoint was not reachable.</span></span> |
   | **<span data-ttu-id="4d5da-217">WS_E_ENDPOINT_FAULT_RECEIVED</span><span class="sxs-lookup"><span data-stu-id="4d5da-217">WS_E_ENDPOINT_FAULT_RECEIVED</span></span>**<br /><span data-ttu-id="4d5da-218">2151481363（0x803D0013）</span><span class="sxs-lookup"><span data-stu-id="4d5da-218">2151481363 (0x803D0013)</span></span> | <span data-ttu-id="4d5da-219">从远程终结点收到包含错误的消息。</span><span class="sxs-lookup"><span data-stu-id="4d5da-219">A message containing a fault was received from the remote endpoint.</span></span> <span data-ttu-id="4d5da-220">请确保连接到正确的服务终结点。</span><span class="sxs-lookup"><span data-stu-id="4d5da-220">Make sure you are connecting to the correct service endpoint.</span></span> |
   | **<span data-ttu-id="4d5da-221">WS_E_INVALID_ENDPOINT_URL</span><span class="sxs-lookup"><span data-stu-id="4d5da-221">WS_E_INVALID_ENDPOINT_URL</span></span>**<br /><span data-ttu-id="4d5da-222">2151481376（0x803D0020）</span><span class="sxs-lookup"><span data-stu-id="4d5da-222">2151481376 (0x803D0020)</span></span> | <span data-ttu-id="4d5da-223">终结点地址 URL 无效。</span><span class="sxs-lookup"><span data-stu-id="4d5da-223">The endpoint address URL is not valid.</span></span> <span data-ttu-id="4d5da-224">URL 必须以 "http" 或 "https" 开头。</span><span class="sxs-lookup"><span data-stu-id="4d5da-224">The URL must start with “http” or “https”.</span></span> |

   <a href="" id="mbam-volume-wmi-class"></a><span data-ttu-id="4d5da-225">**MBAM \ _VOLUME WMI Class** **EscrowRecoveryKey：** 读取卷的恢复数字密码和密钥包，并使用 MBAM 恢复服务将其发送到 MBAM 恢复数据库。</span><span class="sxs-lookup"><span data-stu-id="4d5da-225">**MBAM\_Volume WMI Class** **EscrowRecoveryKey:** Reads the recovery numerical password and key package of the volume and sends them to the MBAM recovery database by using the MBAM recovery service.</span></span> <span data-ttu-id="4d5da-226">如果失败，将返回错误代码进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="4d5da-226">If it fails, an error code is returned for troubleshooting.</span></span>

   | <span data-ttu-id="4d5da-227">参数</span><span class="sxs-lookup"><span data-stu-id="4d5da-227">Parameter</span></span> | <span data-ttu-id="4d5da-228">描述</span><span class="sxs-lookup"><span data-stu-id="4d5da-228">Description</span></span> |
   | --------- | ----------- |
   | <span data-ttu-id="4d5da-229">RecoveryServiceEndPoint</span><span class="sxs-lookup"><span data-stu-id="4d5da-229">RecoveryServiceEndPoint</span></span> | <span data-ttu-id="4d5da-230">指定 MBAM 恢复服务终结点的字符串。</span><span class="sxs-lookup"><span data-stu-id="4d5da-230">A string specifying the MBAM recovery service endpoint.</span></span> |

   <span data-ttu-id="4d5da-231">下面是常见错误消息的列表：</span><span class="sxs-lookup"><span data-stu-id="4d5da-231">Here are a list of common error messages:</span></span>

   | <span data-ttu-id="4d5da-232">常见返回值</span><span class="sxs-lookup"><span data-stu-id="4d5da-232">Common return values</span></span> | <span data-ttu-id="4d5da-233">错误消息</span><span class="sxs-lookup"><span data-stu-id="4d5da-233">Error message</span></span> |
   | -------------------- | ------------- |
   | **<span data-ttu-id="4d5da-234">S_OK</span><span class="sxs-lookup"><span data-stu-id="4d5da-234">S_OK</span></span>**<br /><span data-ttu-id="4d5da-235">0（0x0）</span><span class="sxs-lookup"><span data-stu-id="4d5da-235">0 (0x0)</span></span> | <span data-ttu-id="4d5da-236">该方法成功</span><span class="sxs-lookup"><span data-stu-id="4d5da-236">The method was successful</span></span> |
   | **<span data-ttu-id="4d5da-237">FVE_E_LOCKED_VOLUME</span><span class="sxs-lookup"><span data-stu-id="4d5da-237">FVE_E_LOCKED_VOLUME</span></span>**<br /><span data-ttu-id="4d5da-238">2150694912（0x80310000）</span><span class="sxs-lookup"><span data-stu-id="4d5da-238">2150694912 (0x80310000)</span></span> | <span data-ttu-id="4d5da-239">卷已锁定。</span><span class="sxs-lookup"><span data-stu-id="4d5da-239">The volume is locked.</span></span> |
   | **<span data-ttu-id="4d5da-240">FVE_E_PROTECTOR_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="4d5da-240">FVE_E_PROTECTOR_NOT_FOUND</span></span>**<br /><span data-ttu-id="4d5da-241">2150694963（0x80310033）</span><span class="sxs-lookup"><span data-stu-id="4d5da-241">2150694963 (0x80310033)</span></span> | <span data-ttu-id="4d5da-242">找不到卷的数字密码保护器。</span><span class="sxs-lookup"><span data-stu-id="4d5da-242">A Numerical Password protector was not found for the volume.</span></span> |
   | **<span data-ttu-id="4d5da-243">WS_E_ENDPOINT_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="4d5da-243">WS_E_ENDPOINT_ACCESS_DENIED</span></span>**<br /><span data-ttu-id="4d5da-244">2151481349（0x803D0005）</span><span class="sxs-lookup"><span data-stu-id="4d5da-244">2151481349 (0x803D0005)</span></span> | <span data-ttu-id="4d5da-245">远程终结点拒绝访问。</span><span class="sxs-lookup"><span data-stu-id="4d5da-245">Access was denied by the remote endpoint.</span></span> |
   | **<span data-ttu-id="4d5da-246">WS_E_ENDPOINT_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="4d5da-246">WS_E_ENDPOINT_NOT_FOUND</span></span>**<br /><span data-ttu-id="4d5da-247">2151481357（0x803D000D）</span><span class="sxs-lookup"><span data-stu-id="4d5da-247">2151481357 (0x803D000D)</span></span> | <span data-ttu-id="4d5da-248">远程终结点不存在或无法定位。</span><span class="sxs-lookup"><span data-stu-id="4d5da-248">The remote endpoint does not exist or could not be located.</span></span> |
   | **<span data-ttu-id="4d5da-249">WS_E_ENDPOINT_FAILURE</span><span class="sxs-lookup"><span data-stu-id="4d5da-249">WS_E_ENDPOINT_FAILURE</span></span>**<br /><span data-ttu-id="4d5da-250">2151481357（0x803D000F）</span><span class="sxs-lookup"><span data-stu-id="4d5da-250">2151481357 (0x803D000F)</span></span> | <span data-ttu-id="4d5da-251">远程终结点无法处理请求。</span><span class="sxs-lookup"><span data-stu-id="4d5da-251">The remote endpoint could not process the request.</span></span> |
   | **<span data-ttu-id="4d5da-252">WS_E_ENDPOINT_UNREACHABLE</span><span class="sxs-lookup"><span data-stu-id="4d5da-252">WS_E_ENDPOINT_UNREACHABLE</span></span>**<br /><span data-ttu-id="4d5da-253">2151481360（0x803D0010）</span><span class="sxs-lookup"><span data-stu-id="4d5da-253">2151481360 (0x803D0010)</span></span> | <span data-ttu-id="4d5da-254">无法访问远程终结点。</span><span class="sxs-lookup"><span data-stu-id="4d5da-254">The remote endpoint was not reachable.</span></span> |
   | **<span data-ttu-id="4d5da-255">WS_E_ENDPOINT_FAULT_RECEIVED</span><span class="sxs-lookup"><span data-stu-id="4d5da-255">WS_E_ENDPOINT_FAULT_RECEIVED</span></span>**<br /><span data-ttu-id="4d5da-256">2151481363（0x803D0013）</span><span class="sxs-lookup"><span data-stu-id="4d5da-256">2151481363 (0x803D0013)</span></span> | <span data-ttu-id="4d5da-257">从远程终结点收到包含错误的消息。</span><span class="sxs-lookup"><span data-stu-id="4d5da-257">A message containing a fault was received from the remote endpoint.</span></span> <span data-ttu-id="4d5da-258">请确保连接到正确的服务终结点。</span><span class="sxs-lookup"><span data-stu-id="4d5da-258">Make sure you are connecting to the correct service endpoint.</span></span> |
   | **<span data-ttu-id="4d5da-259">WS_E_INVALID_ENDPOINT_URL</span><span class="sxs-lookup"><span data-stu-id="4d5da-259">WS_E_INVALID_ENDPOINT_URL</span></span>**<br /><span data-ttu-id="4d5da-260">2151481376（0x803D0020）</span><span class="sxs-lookup"><span data-stu-id="4d5da-260">2151481376 (0x803D0020)</span></span> | <span data-ttu-id="4d5da-261">终结点地址 URL 无效。</span><span class="sxs-lookup"><span data-stu-id="4d5da-261">The endpoint address URL is not valid.</span></span> <span data-ttu-id="4d5da-262">URL 必须以 "http" 或 "https" 开头。</span><span class="sxs-lookup"><span data-stu-id="4d5da-262">The URL must start with “http” or “https”.</span></span> |
     

2. **<span data-ttu-id="4d5da-263">使用 Microsoft 部署工具包（MDT）和 PowerShell 部署 MBAM</span><span class="sxs-lookup"><span data-stu-id="4d5da-263">Deploy MBAM by using Microsoft Deployment Toolkit (MDT) and PowerShell</span></span>**

   1.  <span data-ttu-id="4d5da-264">在 MDT 中，创建新的部署共享或打开现有部署共享。</span><span class="sxs-lookup"><span data-stu-id="4d5da-264">In MDT, create a new deployment share or open an existing deployment share.</span></span>

       **<span data-ttu-id="4d5da-265">注意</span><span class="sxs-lookup"><span data-stu-id="4d5da-265">Note</span></span>**  
       <span data-ttu-id="4d5da-266">`Invoke-MbamClientDeployment.ps1`PowerShell 脚本可以与任何图像处理或工具一起使用。</span><span class="sxs-lookup"><span data-stu-id="4d5da-266">The `Invoke-MbamClientDeployment.ps1` PowerShell script can be used with any imaging process or tool.</span></span> <span data-ttu-id="4d5da-267">本部分介绍如何使用 MDT 集成它，但步骤类似于将其与任何其他进程或工具进行集成。</span><span class="sxs-lookup"><span data-stu-id="4d5da-267">This section shows how to integrate it by using MDT, but the steps are similar to integrating it with any other process or tool.</span></span>

       **<span data-ttu-id="4d5da-268">注意</span><span class="sxs-lookup"><span data-stu-id="4d5da-268">Caution</span></span>**  
       <span data-ttu-id="4d5da-269">如果您使用的是 BitLocker 预配（WinPE），并且想要维护 TPM 所有者授权值，则必须 `SaveWinPETpmOwnerAuth.wsf` 在安装重启到完整操作系统之前立即在 WinPE 中添加脚本。</span><span class="sxs-lookup"><span data-stu-id="4d5da-269">If you are using BitLocker pre-provisioning (WinPE) and want to maintain the TPM owner authorization value, you must add the `SaveWinPETpmOwnerAuth.wsf` script in WinPE immediately before the installation reboots into the full operating system.</span></span> **<span data-ttu-id="4d5da-270">如果不使用此脚本，重新启动时将丢失 TPM 所有者授权值。</span><span class="sxs-lookup"><span data-stu-id="4d5da-270">If you do not use this script, you will lose the TPM owner authorization value on reboot.</span></span>**

   2.  <span data-ttu-id="4d5da-271">复制 `Invoke-MbamClientDeployment.ps1` 到\*\* &lt; DeploymentShare &gt; \\Scripts\*\*。</span><span class="sxs-lookup"><span data-stu-id="4d5da-271">Copy `Invoke-MbamClientDeployment.ps1` to **&lt;DeploymentShare&gt;\\Scripts**.</span></span> <span data-ttu-id="4d5da-272">如果使用预配，请将 `SaveWinPETpmOwnerAuth.wsf` 文件复制到\*\* &lt; DeploymentShare &gt; \\Scripts\*\*。</span><span class="sxs-lookup"><span data-stu-id="4d5da-272">If you are using pre-provisioning, copy the `SaveWinPETpmOwnerAuth.wsf` file into **&lt;DeploymentShare&gt;\\Scripts**.</span></span>

   3.  <span data-ttu-id="4d5da-273">将 MBAM 2.5 SP1 客户端应用程序添加到部署共享中的 "应用程序" 节点。</span><span class="sxs-lookup"><span data-stu-id="4d5da-273">Add the MBAM 2.5 SP1 client application to the Applications node in the deployment share.</span></span>

       1.  <span data-ttu-id="4d5da-274">在 "**应用程序**" 节点下，单击 "**新建应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="4d5da-274">Under the **Applications** node, click **New Application**.</span></span>

       2.  <span data-ttu-id="4d5da-275">选择 "**应用程序包含源文件**"。</span><span class="sxs-lookup"><span data-stu-id="4d5da-275">Select **Application with Source Files**.</span></span> <span data-ttu-id="4d5da-276">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4d5da-276">Click **Next**.</span></span>

       3.  <span data-ttu-id="4d5da-277">在 "**应用程序名称**" 中，键入 "MBAM 2.5 SP1 Client"。</span><span class="sxs-lookup"><span data-stu-id="4d5da-277">In **Application Name**, type “MBAM 2.5 SP1 Client”.</span></span> <span data-ttu-id="4d5da-278">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4d5da-278">Click **Next**.</span></span>

       4.  <span data-ttu-id="4d5da-279">浏览到包含的目录 `MBAMClientSetup-<Version>.msi` 。</span><span class="sxs-lookup"><span data-stu-id="4d5da-279">Browse to the directory containing `MBAMClientSetup-<Version>.msi`.</span></span> <span data-ttu-id="4d5da-280">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4d5da-280">Click **Next**.</span></span>

       5.  <span data-ttu-id="4d5da-281">键入 "MBAM 2.5 SP1 Client" 作为要创建的目录。</span><span class="sxs-lookup"><span data-stu-id="4d5da-281">Type “MBAM 2.5 SP1 Client” as the directory to create.</span></span> <span data-ttu-id="4d5da-282">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4d5da-282">Click **Next**.</span></span>

       6.  <span data-ttu-id="4d5da-283">`msiexec /i MBAMClientSetup-<Version>.msi /quiet`在命令行中输入。</span><span class="sxs-lookup"><span data-stu-id="4d5da-283">Enter `msiexec /i MBAMClientSetup-<Version>.msi /quiet` at the command line.</span></span> <span data-ttu-id="4d5da-284">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4d5da-284">Click **Next**.</span></span>

       7.  <span data-ttu-id="4d5da-285">接受剩余的默认设置以完成 "新建应用程序" 向导。</span><span class="sxs-lookup"><span data-stu-id="4d5da-285">Accept the remaining defaults to complete the New Application wizard.</span></span>

   4.  <span data-ttu-id="4d5da-286">在 MDT 中，右键单击部署共享的名称，然后单击 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="4d5da-286">In MDT, right-click the name of the deployment share and click **Properties**.</span></span> <span data-ttu-id="4d5da-287">单击 "**规则**" 选项卡。添加以下行：</span><span class="sxs-lookup"><span data-stu-id="4d5da-287">Click the **Rules** tab. Add the following lines:</span></span>

       `SkipBitLocker=YES``BDEInstall=TPM``BDEInstallSuppress=NO``BDEWaitForEncryption=YES`

       <span data-ttu-id="4d5da-288">单击 "确定" 关闭窗口。</span><span class="sxs-lookup"><span data-stu-id="4d5da-288">Click OK to close the window.</span></span>

   5.  <span data-ttu-id="4d5da-289">在 "任务序列" 节点下，编辑用于 Windows 部署的现有任务序列。</span><span class="sxs-lookup"><span data-stu-id="4d5da-289">Under the Task Sequences node, edit an existing task sequence used for Windows Deployment.</span></span> <span data-ttu-id="4d5da-290">如果需要，您可以通过右键单击**任务序列**节点、选择 "**新建任务序列**" 和 "完成向导" 来创建新任务序列。</span><span class="sxs-lookup"><span data-stu-id="4d5da-290">If you want, you can create a new task sequence by right-clicking the **Task Sequences** node, selecting **New Task Sequence**, and completing the wizard.</span></span>

       <span data-ttu-id="4d5da-291">在所选任务序列的 "**任务序列**" 选项卡上，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="4d5da-291">On the **Task Sequence** tab of the selected task sequence, perform these steps:</span></span>

       1.  <span data-ttu-id="4d5da-292">在 "**预安装**" 文件夹下，如果希望在 WinPE 中启用 bitlocker，则启用可选任务 "**启用 bitlocker （脱机）** "，这将仅加密已使用的空间。</span><span class="sxs-lookup"><span data-stu-id="4d5da-292">Under the **Preinstall** folder, enable the optional task **Enable BitLocker (Offline)** if you want BitLocker enabled in WinPE, which encrypts used space only.</span></span>

       2.  <span data-ttu-id="4d5da-293">若要在使用预配时保留 TPM OwnerAuth，允许 MBAM 稍后进行保管，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4d5da-293">To persist TPM OwnerAuth when using pre-provisioning, allowing MBAM to escrow it later, do the following:</span></span>

           1.  <span data-ttu-id="4d5da-294">查找**安装操作系统**步骤</span><span class="sxs-lookup"><span data-stu-id="4d5da-294">Find the **Install Operating System** step</span></span>

           2.  <span data-ttu-id="4d5da-295">在其后添加新的**运行命令行**步骤</span><span class="sxs-lookup"><span data-stu-id="4d5da-295">Add a new **Run Command Line** step after it</span></span>

           3.  <span data-ttu-id="4d5da-296">对步骤**持久性 TPM OwnerAuth**命名</span><span class="sxs-lookup"><span data-stu-id="4d5da-296">Name the step **Persist TPM OwnerAuth**</span></span>

           4.  <span data-ttu-id="4d5da-297">将命令行设置为 `cscript.exe "%SCRIPTROOT%/SaveWinPETpmOwnerAuth.wsf"`
            **注意：** 对于 windows 10 版本1607或更高版本，只有 WINDOWS 可以获得 TPM 的所有权。</span><span class="sxs-lookup"><span data-stu-id="4d5da-297">Set the command line to `cscript.exe "%SCRIPTROOT%/SaveWinPETpmOwnerAuth.wsf"`
**Note:** For Windows 10, version 1607 or later, only Windows can take ownership of the TPM.</span></span> <span data-ttu-id="4d5da-298">在 addiiton 中，Windows 将不会在预配 TPM 时保留 TPM 所有者密码。</span><span class="sxs-lookup"><span data-stu-id="4d5da-298">In addiiton, Windows will not retain the TPM owner password when provisioning the TPM.</span></span> <span data-ttu-id="4d5da-299">有关进一步的详细信息，请参阅[TPM 所有者密码](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password)。</span><span class="sxs-lookup"><span data-stu-id="4d5da-299">See [TPM owner password](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password) for further details.</span></span>

       3.  <span data-ttu-id="4d5da-300">在 "**状态还原**" 文件夹中，删除 "**启用 BitLocker** " 任务。</span><span class="sxs-lookup"><span data-stu-id="4d5da-300">In the **State Restore** folder, delete the **Enable BitLocker** task.</span></span>

       4.  <span data-ttu-id="4d5da-301">在 "**自定义任务**" 下的 "**状态还原**" 文件夹中，创建新的**安装应用程序**任务并将其命名为**Install MBAM 代理**。</span><span class="sxs-lookup"><span data-stu-id="4d5da-301">In the **State Restore** folder under **Custom Tasks**, create a new **Install Application** task and name it **Install MBAM Agent**.</span></span> <span data-ttu-id="4d5da-302">单击 "**安装单个应用程序**" 单选按钮，然后浏览到以前创建的 MBAM 2.5 SP1 客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="4d5da-302">Click the **Install Single Application** radio button and browse to the MBAM 2.5 SP1 client application created earlier.</span></span>

       5.  <span data-ttu-id="4d5da-303">在 "**自定义任务**" 下的 "**状态还原**" 文件夹中，使用以下设置创建新的**运行 POWERSHELL 脚本**任务（在 MBAM 2.5 SP1 客户端应用程序步骤之后）（根据你的环境更新参数）：</span><span class="sxs-lookup"><span data-stu-id="4d5da-303">In the **State Restore** folder under **Custom Tasks**, create a new **Run PowerShell Script** task (after the MBAM 2.5 SP1 Client application step) with the following settings (update the parameters as appropriate for your environment):</span></span>

           -   <span data-ttu-id="4d5da-304">名称：为 MBAM 配置 BitLocker</span><span class="sxs-lookup"><span data-stu-id="4d5da-304">Name: Configure BitLocker for MBAM</span></span>

           -   <span data-ttu-id="4d5da-305">PowerShell 脚本：</span><span class="sxs-lookup"><span data-stu-id="4d5da-305">PowerShell script:</span></span> `Invoke-MbamClientDeployment.ps1`

           -   <span data-ttu-id="4d5da-306">实参</span><span class="sxs-lookup"><span data-stu-id="4d5da-306">Parameters:</span></span>

               <table>
               <colgroup>
               <col width="33%" />
               <col width="33%" />
               <col width="33%" />
               </colgroup>
               <tbody>
               <tr class="odd">
               <td align="left"><p><span data-ttu-id="4d5da-307">-RecoveryServiceEndpoint</span><span class="sxs-lookup"><span data-stu-id="4d5da-307">-RecoveryServiceEndpoint</span></span></p></td>
               <td align="left"><p><span data-ttu-id="4d5da-308">必需</span><span class="sxs-lookup"><span data-stu-id="4d5da-308">Required</span></span></p></td>
               <td align="left"><p><span data-ttu-id="4d5da-309">MBAM recovery 服务终结点</span><span class="sxs-lookup"><span data-stu-id="4d5da-309">MBAM recovery service endpoint</span></span></p></td>
               </tr>
               <tr class="even">
               <td align="left"><p><span data-ttu-id="4d5da-310">-StatusReportingServiceEndpoint</span><span class="sxs-lookup"><span data-stu-id="4d5da-310">-StatusReportingServiceEndpoint</span></span></p></td>
               <td align="left"><p><span data-ttu-id="4d5da-311">可选</span><span class="sxs-lookup"><span data-stu-id="4d5da-311">Optional</span></span></p></td>
               <td align="left"><p><span data-ttu-id="4d5da-312">MBAM 状态报告服务终结点</span><span class="sxs-lookup"><span data-stu-id="4d5da-312">MBAM status reporting service endpoint</span></span></p></td>
               </tr>
               <tr class="odd">
               <td align="left"><p><span data-ttu-id="4d5da-313">-EncryptionMethod</span><span class="sxs-lookup"><span data-stu-id="4d5da-313">-EncryptionMethod</span></span></p></td>
               <td align="left"><p><span data-ttu-id="4d5da-314">可选</span><span class="sxs-lookup"><span data-stu-id="4d5da-314">Optional</span></span></p></td>
               <td align="left"><p><span data-ttu-id="4d5da-315">加密方法（默认： AES 128）</span><span class="sxs-lookup"><span data-stu-id="4d5da-315">Encryption method (default: AES 128)</span></span></p></td>
               </tr>
               <tr class="even">
               <td align="left"><p><span data-ttu-id="4d5da-316">-EncryptAndEscrowDataVolume</span><span class="sxs-lookup"><span data-stu-id="4d5da-316">-EncryptAndEscrowDataVolume</span></span></p></td>
               <td align="left"><p><span data-ttu-id="4d5da-317">开关</span><span class="sxs-lookup"><span data-stu-id="4d5da-317">Switch</span></span></p></td>
               <td align="left"><p><span data-ttu-id="4d5da-318">指定加密数据卷和托管数据卷恢复密钥</span><span class="sxs-lookup"><span data-stu-id="4d5da-318">Specify to encrypt data volume(s) and escrow data volume recovery key(s)</span></span></p></td>
               </tr>
               <tr class="odd">
               <td align="left"><p><span data-ttu-id="4d5da-319">-WaitForEncryptionToComplete</span><span class="sxs-lookup"><span data-stu-id="4d5da-319">-WaitForEncryptionToComplete</span></span></p></td>
               <td align="left"><p><span data-ttu-id="4d5da-320">开关</span><span class="sxs-lookup"><span data-stu-id="4d5da-320">Switch</span></span></p></td>
               <td align="left"><p><span data-ttu-id="4d5da-321">指定等待加密完成</span><span class="sxs-lookup"><span data-stu-id="4d5da-321">Specify to wait for the encryption to complete</span></span></p></td>
               </tr>
               <tr class="even">
               <td align="left"><p><span data-ttu-id="4d5da-322">-DoNotResumeSuspendedEncryption</span><span class="sxs-lookup"><span data-stu-id="4d5da-322">-DoNotResumeSuspendedEncryption</span></span></p></td>
               <td align="left"><p><span data-ttu-id="4d5da-323">开关</span><span class="sxs-lookup"><span data-stu-id="4d5da-323">Switch</span></span></p></td>
               <td align="left"><p><span data-ttu-id="4d5da-324">指定部署脚本将不会恢复暂停的加密</span><span class="sxs-lookup"><span data-stu-id="4d5da-324">Specify that the deployment script will not resume suspended encryption</span></span></p></td>
               </tr>
               <tr class="odd">
               <td align="left"><p><span data-ttu-id="4d5da-325">-IgnoreEscrowOwnerAuthFailure</span><span class="sxs-lookup"><span data-stu-id="4d5da-325">-IgnoreEscrowOwnerAuthFailure</span></span></p></td>
               <td align="left"><p><span data-ttu-id="4d5da-326">开关</span><span class="sxs-lookup"><span data-stu-id="4d5da-326">Switch</span></span></p></td>
               <td align="left"><p><span data-ttu-id="4d5da-327">指定忽略 TPM 所有者-身份验证托管失败。</span><span class="sxs-lookup"><span data-stu-id="4d5da-327">Specify to ignore TPM owner-auth escrow failure.</span></span> <span data-ttu-id="4d5da-328">应在 MBAM 无法读取 TPM 所有者身份验证的情况下使用它，例如，如果启用了 TPM 自动预配</span><span class="sxs-lookup"><span data-stu-id="4d5da-328">It should be used in the scenarios where MBAM is not able to read the TPM owner-auth, e.g. if TPM auto provisioning is enabled</span></span></p></td>
               </tr>
               <tr class="even">
               <td align="left"><p><span data-ttu-id="4d5da-329">-IgnoreEscrowRecoveryKeyFailure</span><span class="sxs-lookup"><span data-stu-id="4d5da-329">-IgnoreEscrowRecoveryKeyFailure</span></span></p></td>
               <td align="left"><p><span data-ttu-id="4d5da-330">开关</span><span class="sxs-lookup"><span data-stu-id="4d5da-330">Switch</span></span></p></td>
               <td align="left"><p><span data-ttu-id="4d5da-331">指定忽略卷恢复密钥的托管失败</span><span class="sxs-lookup"><span data-stu-id="4d5da-331">Specify to ignore volume recovery key escrow failure</span></span></p></td>
               </tr>
               <tr class="odd">
               <td align="left"><p><span data-ttu-id="4d5da-332">-IgnoreReportStatusFailure</span><span class="sxs-lookup"><span data-stu-id="4d5da-332">-IgnoreReportStatusFailure</span></span></p></td>
               <td align="left"><p><span data-ttu-id="4d5da-333">开关</span><span class="sxs-lookup"><span data-stu-id="4d5da-333">Switch</span></span></p></td>
               <td align="left"><p><span data-ttu-id="4d5da-334">指定忽略状态报告失败</span><span class="sxs-lookup"><span data-stu-id="4d5da-334">Specify to ignore status reporting failure</span></span></p></td>
               </tr>
               </tbody>
               </table>

                 

**<span data-ttu-id="4d5da-335">在 Windows 部署中使用 MBAM 2.5 或更早版本启用 BitLocker</span><span class="sxs-lookup"><span data-stu-id="4d5da-335">To enable BitLocker using MBAM 2.5 or earlier as part of a Windows deployment</span></span>**

1.  <span data-ttu-id="4d5da-336">安装 MBAM 客户端。</span><span class="sxs-lookup"><span data-stu-id="4d5da-336">Install the MBAM Client.</span></span> <span data-ttu-id="4d5da-337">有关说明，请参阅[如何使用命令行部署 MBAM 客户端](how-to-deploy-the-mbam-client-by-using-a-command-line.md)。</span><span class="sxs-lookup"><span data-stu-id="4d5da-337">For instructions, see [How to Deploy the MBAM Client by Using a Command Line](how-to-deploy-the-mbam-client-by-using-a-command-line.md).</span></span>

2.  <span data-ttu-id="4d5da-338">将计算机加入域（推荐）。</span><span class="sxs-lookup"><span data-stu-id="4d5da-338">Join the computer to a domain (recommended).</span></span>

    -   <span data-ttu-id="4d5da-339">如果计算机未加入域，则恢复密码不会存储在 MBAM 密钥恢复服务中。</span><span class="sxs-lookup"><span data-stu-id="4d5da-339">If the computer is not joined to a domain, the recovery password is not stored in the MBAM Key Recovery service.</span></span> <span data-ttu-id="4d5da-340">默认情况下，除非可以存储恢复密钥，否则 MBAM 不允许进行加密。</span><span class="sxs-lookup"><span data-stu-id="4d5da-340">By default, MBAM does not allow encryption to occur unless the recovery key can be stored.</span></span>

    -   <span data-ttu-id="4d5da-341">如果在 MBAM 服务器上存储恢复密钥之前计算机在恢复模式下启动，则没有可用的恢复方法，并且必须 reimaged 计算机。</span><span class="sxs-lookup"><span data-stu-id="4d5da-341">If a computer starts in recovery mode before the recovery key is stored on the MBAM Server, no recovery method is available, and the computer has to be reimaged.</span></span>

3.  <span data-ttu-id="4d5da-342">以管理员身份打开命令提示符，并停止 MBAM 服务。</span><span class="sxs-lookup"><span data-stu-id="4d5da-342">Open a command prompt as an administrator, and stop the MBAM service.</span></span>

4.  <span data-ttu-id="4d5da-343">通过键入以下命令将服务设置为**手动**或按**需**：</span><span class="sxs-lookup"><span data-stu-id="4d5da-343">Set the service to **Manual** or **On demand** by typing the following commands:</span></span>

    **<span data-ttu-id="4d5da-344">net stop mbamagent</span><span class="sxs-lookup"><span data-stu-id="4d5da-344">net stop mbamagent</span></span>**

    **<span data-ttu-id="4d5da-345">sc config mbamagent start = demand</span><span class="sxs-lookup"><span data-stu-id="4d5da-345">sc config mbamagent start= demand</span></span>**

5.  <span data-ttu-id="4d5da-346">设置注册表值，以便 MBAM 客户端忽略组策略设置，而设置加密以启动将 Windows 部署到该客户端计算机的时间。</span><span class="sxs-lookup"><span data-stu-id="4d5da-346">Set the registry values so that the MBAM Client ignores the Group Policy settings and instead sets encryption to start the time Windows is deployed to that client computer.</span></span>

    <span data-ttu-id="4d5da-347">**小心** 此步骤介绍了如何修改 Windows 注册表。</span><span class="sxs-lookup"><span data-stu-id="4d5da-347">**Caution** This step describes how to modify the Windows registry.</span></span> <span data-ttu-id="4d5da-348">注册表编辑器使用不当可导致严重问题，这些问题可能需要重新安装 Windows。</span><span class="sxs-lookup"><span data-stu-id="4d5da-348">Using Registry Editor incorrectly can cause serious issues that can require you to reinstall Windows.</span></span> <span data-ttu-id="4d5da-349">我们无法保证无法通过错误地使用注册表编辑器来解决所产生的问题。</span><span class="sxs-lookup"><span data-stu-id="4d5da-349">We cannot guarantee that issues resulting from the incorrect use of Registry Editor can be resolved.</span></span> <span data-ttu-id="4d5da-350">使用注册表编辑器的风险由您自己承担。</span><span class="sxs-lookup"><span data-stu-id="4d5da-350">Use Registry Editor at your own risk.</span></span>

    1.  <span data-ttu-id="4d5da-351">设置仅适用于**操作系统**的 TPM 加密，运行 Regedit.exe，然后从 C:\\program files Files\\Microsoft\\MDOP MBAM\\MBAMDeploymentKeyTemplate.reg. 导入注册表项模板</span><span class="sxs-lookup"><span data-stu-id="4d5da-351">Set the TPM for **Operating system only encryption**, run Regedit.exe, and then import the registry key template from C:\\Program Files\\Microsoft\\MDOP MBAM\\MBAMDeploymentKeyTemplate.reg.</span></span>

    2.  <span data-ttu-id="4d5da-352">在 Regedit.exe 中，转到 HKLM\\SOFTWARE\\Microsoft\\MBAM，并配置下表中列出的设置。</span><span class="sxs-lookup"><span data-stu-id="4d5da-352">In Regedit.exe, go to HKLM\\SOFTWARE\\Microsoft\\MBAM, and configure the settings that are listed in the following table.</span></span>

        <span data-ttu-id="4d5da-353">**注意** 你可以在此处设置与 MBAM 相关的组策略设置或注册表值。</span><span class="sxs-lookup"><span data-stu-id="4d5da-353">**Note** You can set Group Policy settings or registry values related to MBAM here.</span></span> <span data-ttu-id="4d5da-354">这些设置将替代以前设置的值。</span><span class="sxs-lookup"><span data-stu-id="4d5da-354">These settings will override previously set values.</span></span>

        <span data-ttu-id="4d5da-355">注册表项配置设置</span><span class="sxs-lookup"><span data-stu-id="4d5da-355">Registry entry Configuration settings</span></span>

        <span data-ttu-id="4d5da-356">DeploymentTime</span><span class="sxs-lookup"><span data-stu-id="4d5da-356">DeploymentTime</span></span>

        <span data-ttu-id="4d5da-357">0 = 关闭</span><span class="sxs-lookup"><span data-stu-id="4d5da-357">0 = Off</span></span>

        <span data-ttu-id="4d5da-358">1 = 使用部署时间策略设置（默认值）-使用此设置可在将 Windows 部署到客户端计算机时启用加密。</span><span class="sxs-lookup"><span data-stu-id="4d5da-358">1 = Use deployment time policy settings (default) – use this setting to enable encryption at the time Windows is deployed to the client computer.</span></span>

        <span data-ttu-id="4d5da-359">UseKeyRecoveryService</span><span class="sxs-lookup"><span data-stu-id="4d5da-359">UseKeyRecoveryService</span></span>

        <span data-ttu-id="4d5da-360">0 = 不使用密钥保管（这种情况下，不需要接下来的两个注册表项）</span><span class="sxs-lookup"><span data-stu-id="4d5da-360">0 = Do not use key escrow (the next two registry entries are not required in this case)</span></span>

        <span data-ttu-id="4d5da-361">1 = 在密钥恢复系统中使用密钥托管（默认）</span><span class="sxs-lookup"><span data-stu-id="4d5da-361">1 = Use key escrow in Key Recovery system (default)</span></span>

        <span data-ttu-id="4d5da-362">这是推荐的设置，可使 MBAM 存储恢复密钥。</span><span class="sxs-lookup"><span data-stu-id="4d5da-362">This is the recommended setting, which enables MBAM to store the recovery keys.</span></span> <span data-ttu-id="4d5da-363">计算机必须能够与 MBAM 密钥恢复服务进行通信。</span><span class="sxs-lookup"><span data-stu-id="4d5da-363">The computer must be able to communicate with the MBAM Key Recovery service.</span></span> <span data-ttu-id="4d5da-364">继续之前，请验证计算机是否可以与服务通信。</span><span class="sxs-lookup"><span data-stu-id="4d5da-364">Verify that the computer can communicate with the service before you proceed.</span></span>

        <span data-ttu-id="4d5da-365">KeyRecoveryOptions</span><span class="sxs-lookup"><span data-stu-id="4d5da-365">KeyRecoveryOptions</span></span>

        <span data-ttu-id="4d5da-366">0 = 仅上载恢复密钥</span><span class="sxs-lookup"><span data-stu-id="4d5da-366">0 = Uploads Recovery Key only</span></span>

        <span data-ttu-id="4d5da-367">1 = 上载恢复密钥和密钥恢复包（默认）</span><span class="sxs-lookup"><span data-stu-id="4d5da-367">1 = Uploads Recovery Key and Key Recovery Package (default)</span></span>

        <span data-ttu-id="4d5da-368">KeyRecoveryServiceEndPoint</span><span class="sxs-lookup"><span data-stu-id="4d5da-368">KeyRecoveryServiceEndPoint</span></span>

        <span data-ttu-id="4d5da-369">将此值设置为运行密钥恢复服务的服务器的 URL，例如，http:// &lt; 计算机名 &gt; /MBAMRecoveryAndHardwareService/CoreService.svc。</span><span class="sxs-lookup"><span data-stu-id="4d5da-369">Set this value to the URL for the server running the Key Recovery service, for example, http://&lt;computer name&gt;/MBAMRecoveryAndHardwareService/CoreService.svc.</span></span>


6.  <span data-ttu-id="4d5da-370">MBAM 客户端将在 MBAM 客户端部署期间重新启动系统。</span><span class="sxs-lookup"><span data-stu-id="4d5da-370">The MBAM Client will restart the system during the MBAM Client deployment.</span></span> <span data-ttu-id="4d5da-371">当您准备好进行此重启时，请以管理员身份在命令提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="4d5da-371">When you are ready for this restart, run the following command at a command prompt as an administrator:</span></span>

    **<span data-ttu-id="4d5da-372">net start mbamagent</span><span class="sxs-lookup"><span data-stu-id="4d5da-372">net start mbamagent</span></span>**

7.  <span data-ttu-id="4d5da-373">当计算机重新启动，并且 BIOS 提示您时，请接受 TPM 更改。</span><span class="sxs-lookup"><span data-stu-id="4d5da-373">When the computers restarts, and the BIOS prompts you, accept the TPM change.</span></span>

8.  <span data-ttu-id="4d5da-374">在 Windows 客户端操作系统图像处理过程中，当你准备好开始加密时，请以管理员身份打开命令提示符，然后键入以下命令以将 "开始" 设置为 "**自动**"，然后重新启动 MBAM 客户端代理：</span><span class="sxs-lookup"><span data-stu-id="4d5da-374">During the Windows client operating system imaging process, when you are ready to start encryption, open a command prompt as an administrator, and type the following commands to set the start to **Automatic** and to restart the MBAM Client agent:</span></span>

    **<span data-ttu-id="4d5da-375">sc config mbamagent start = auto</span><span class="sxs-lookup"><span data-stu-id="4d5da-375">sc config mbamagent start= auto</span></span>**

    **<span data-ttu-id="4d5da-376">net start mbamagent</span><span class="sxs-lookup"><span data-stu-id="4d5da-376">net start mbamagent</span></span>**

9.  <span data-ttu-id="4d5da-377">若要删除绕过的注册表值，请运行 Regedit.exe，然后转到 HKLM\\SOFTWARE\\Microsoft 注册表项。</span><span class="sxs-lookup"><span data-stu-id="4d5da-377">To delete the bypass registry values, run Regedit.exe, and go to the HKLM\\SOFTWARE\\Microsoft registry entry.</span></span> <span data-ttu-id="4d5da-378">右键单击**MBAM**节点，然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="4d5da-378">Right-click the **MBAM** node, and then click **Delete**.</span></span>

## <span data-ttu-id="4d5da-379">相关主题</span><span class="sxs-lookup"><span data-stu-id="4d5da-379">Related topics</span></span>

[<span data-ttu-id="4d5da-380">部署 MBAM 2.5 客户端</span><span class="sxs-lookup"><span data-stu-id="4d5da-380">Deploying the MBAM 2.5 Client</span></span>](deploying-the-mbam-25-client.md)

[<span data-ttu-id="4d5da-381">规划 MBAM 2.5 客户端部署</span><span class="sxs-lookup"><span data-stu-id="4d5da-381">Planning for MBAM 2.5 Client Deployment</span></span>](planning-for-mbam-25-client-deployment.md)

## <span data-ttu-id="4d5da-382">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="4d5da-382">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="4d5da-383">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="4d5da-383">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span>
- <span data-ttu-id="4d5da-384">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="4d5da-384">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>
