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
ms.openlocfilehash: cd4086ca6bb2ea8d253ea3b743f4efe7efbbb6c1
ms.sourcegitcommit: 325c4b77f9a9df0f3de268457fed06184623bb94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2021
ms.locfileid: "11626179"
---
# <a name="how-to-enable-bitlocker-by-using-mbam-as-part-of-a-windows-deployment"></a><span data-ttu-id="e20c8-103">如何通过使用 MBAM 将 BitLocker 作为 Windows 部署的一部分来启用</span><span class="sxs-lookup"><span data-stu-id="e20c8-103">How to Enable BitLocker by Using MBAM as Part of a Windows Deployment</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e20c8-104">这些说明与 Configuration Manager BitLocker 管理不相关。</span><span class="sxs-lookup"><span data-stu-id="e20c8-104">These instructions do not pertain to Configuration Manager BitLocker Management.</span></span> <span data-ttu-id="e20c8-105">不支持 `Invoke-MbamClientDeployment.ps1` 将 PowerShell 脚本与 Configuration Manager 中的 BitLocker 管理一同使用。</span><span class="sxs-lookup"><span data-stu-id="e20c8-105">The `Invoke-MbamClientDeployment.ps1` PowerShell script is not supported for use with BitLocker Management in Configuration Manager.</span></span> <span data-ttu-id="e20c8-106">这包括在 Configuration Manager 任务序列期间托管 BitLocker 恢复密钥。</span><span class="sxs-lookup"><span data-stu-id="e20c8-106">This includes escrowing of BitLocker recovery keys during a Configuration Manager task sequence.</span></span> <span data-ttu-id="e20c8-107">此外，从 Configuration Manager Current Branch 2103 开始，Configuration Manager BitLocker Management 不再使用 MBAM 密钥恢复服务站点托管密钥。</span><span class="sxs-lookup"><span data-stu-id="e20c8-107">Furthermore, starting with Configuration Manager Current Branch 2103, Configuration Manager BitLocker Management no longer uses the MBAM key recovery services site to escrow keys.</span></span> <span data-ttu-id="e20c8-108">尝试将 PowerShell 脚本与 Configuration Manager Current Branch 2103 或更高版本一同使用可能会导致 `Invoke-MbamClientDeployment.ps1` Configuration Manager 站点出现严重问题。</span><span class="sxs-lookup"><span data-stu-id="e20c8-108">Attempting to use the `Invoke-MbamClientDeployment.ps1` PowerShell script with Configuration Manager Current Branch 2103 or newer can result in serious problems with the Configuration Manager site.</span></span> <span data-ttu-id="e20c8-109">已知问题包括创建大量面向所有设备的策略，这可能会导致策略风暴。</span><span class="sxs-lookup"><span data-stu-id="e20c8-109">Known problems include creation of a large amount of policy targeted to all devices which can cause policy storms.</span></span> <span data-ttu-id="e20c8-110">这将主要在配置管理器中和管理点SQL性能严重下降。</span><span class="sxs-lookup"><span data-stu-id="e20c8-110">This will lead to severe degradation of performance in Configuration Manager primarily in SQL and with Management Points.</span></span>

<span data-ttu-id="e20c8-111">本主题介绍如何在最终用户的计算机上将 MBAM 用作映像和部署过程的一Windows BitLocker。</span><span class="sxs-lookup"><span data-stu-id="e20c8-111">This topic explains how to enable BitLocker on an end user's computer by using MBAM as part of your Windows imaging and deployment process.</span></span> <span data-ttu-id="e20c8-112">如果在安装阶段结束) 后重启 (时看到黑屏，指示无法解锁驱动器，请参阅早期版本的 Windows 版本在"安装程序 Windows 和配置管理器"步骤后不启动（如果预预配 BitLocker 与 Windows 10 版本[1511](https://support.microsoft.com/en-us/help/4494799/earlier-windows-versions-don-t-start-after-you-use-pre-provision-bitlo)一起使用）。</span><span class="sxs-lookup"><span data-stu-id="e20c8-112">If you see a black screen at restart (after Install phase concludes) indicating that the drive cannot be unlocked, see [Earlier Windows versions don't start after "Setup Windows and Configuration Manager" step if Pre-Provision BitLocker is used with Windows 10, version 1511](https://support.microsoft.com/en-us/help/4494799/earlier-windows-versions-don-t-start-after-you-use-pre-provision-bitlo).</span></span>

**<span data-ttu-id="e20c8-113">先决条件：</span><span class="sxs-lookup"><span data-stu-id="e20c8-113">Prerequisites:</span></span>**

-   <span data-ttu-id="e20c8-114">必须Windows映像部署过程（Microsoft Deployment Toolkit (MDT) 、Microsoft System Center Configuration Manager 或其他一些映像工具或进程）</span><span class="sxs-lookup"><span data-stu-id="e20c8-114">An existing Windows image deployment process – Microsoft Deployment Toolkit (MDT), Microsoft System Center Configuration Manager, or some other imaging tool or process – must be in place</span></span>

-   <span data-ttu-id="e20c8-115">必须在 BIOS 中启用 TPM，并且对操作系统可见</span><span class="sxs-lookup"><span data-stu-id="e20c8-115">TPM must be enabled in the BIOS and visible to the OS</span></span>

-   <span data-ttu-id="e20c8-116">MBAM 服务器基础结构必须就位且可访问</span><span class="sxs-lookup"><span data-stu-id="e20c8-116">MBAM server infrastructure must be in place and accessible</span></span>

-   <span data-ttu-id="e20c8-117">必须创建 BitLocker 所需的系统分区</span><span class="sxs-lookup"><span data-stu-id="e20c8-117">The system partition required by BitLocker must be created</span></span>

-   <span data-ttu-id="e20c8-118">在 MBAM 完全启用 BitLocker 之前，计算机必须在映像期间加入域</span><span class="sxs-lookup"><span data-stu-id="e20c8-118">The machine must be domain joined during imaging before MBAM fully enables BitLocker</span></span>

**<span data-ttu-id="e20c8-119">在部署中启用使用 MBAM 2.5 SP1 Windows BitLocker</span><span class="sxs-lookup"><span data-stu-id="e20c8-119">To enable BitLocker using MBAM 2.5 SP1 as part of a Windows deployment</span></span>**

1. <span data-ttu-id="e20c8-120">在 MBAM 2.5 SP1 中，建议在部署期间启用 BitLocker Windows方法是使用 `Invoke-MbamClientDeployment.ps1` PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="e20c8-120">In MBAM 2.5 SP1, the recommended approach to enable BitLocker during a Windows Deployment is by using the `Invoke-MbamClientDeployment.ps1` PowerShell script.</span></span>

   -   <span data-ttu-id="e20c8-121">该 `Invoke-MbamClientDeployment.ps1` 脚本在映像过程中会安装 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="e20c8-121">The `Invoke-MbamClientDeployment.ps1` script enacts BitLocker during the imaging process.</span></span> <span data-ttu-id="e20c8-122">当 BitLocker 策略要求时，MBAM 代理在域用户首次登录映像后立即提示域用户创建 PIN 或密码。</span><span class="sxs-lookup"><span data-stu-id="e20c8-122">When required by BitLocker policy, the MBAM agent immediately prompts the domain user to create a PIN or password when the domain user first logs on after imaging.</span></span>

   -   <span data-ttu-id="e20c8-123">易于与 MDT、System Center Configuration Manager或独立映像过程一同使用</span><span class="sxs-lookup"><span data-stu-id="e20c8-123">Easy to use with MDT, System Center Configuration Manager, or standalone imaging processes</span></span>

   -   <span data-ttu-id="e20c8-124">与 PowerShell 2.0 或更高版本兼容</span><span class="sxs-lookup"><span data-stu-id="e20c8-124">Compatible with PowerShell 2.0 or higher</span></span>

   -   <span data-ttu-id="e20c8-125">使用 TPM 密钥保护程序加密操作系统卷</span><span class="sxs-lookup"><span data-stu-id="e20c8-125">Encrypt OS volume with TPM key protector</span></span>

   -   <span data-ttu-id="e20c8-126">完全支持 BitLocker 预预配</span><span class="sxs-lookup"><span data-stu-id="e20c8-126">Fully support BitLocker pre-provisioning</span></span>

   -   <span data-ttu-id="e20c8-127">（可选）加密 FD</span><span class="sxs-lookup"><span data-stu-id="e20c8-127">Optionally encrypt FDDs</span></span>

   -   <span data-ttu-id="e20c8-128">托管 TPM OwnerAuth 对于 Windows 7，MBAM 必须拥有 TPM，托管发生。</span><span class="sxs-lookup"><span data-stu-id="e20c8-128">Escrow TPM OwnerAuth For Windows 7, MBAM must own the TPM for escrow to occur.</span></span>
   <span data-ttu-id="e20c8-129">对于 Windows 8.1、Windows 10 RTM Windows 10版本 1511，支持托管 TPM OwnerAuth。</span><span class="sxs-lookup"><span data-stu-id="e20c8-129">For Windows 8.1, Windows 10 RTM and Windows 10 version 1511, escrow of TPM OwnerAuth is supported.</span></span>
   <span data-ttu-id="e20c8-130">对于Windows 10版本 1607 或更高版本，Windows可以取得 TPM 的所有权。</span><span class="sxs-lookup"><span data-stu-id="e20c8-130">For Windows 10, version 1607 or later, only Windows can take ownership of the TPM.</span></span> <span data-ttu-id="e20c8-131">在 addiiton 中，Windows TPM 时不会保留 TPM 所有者密码。</span><span class="sxs-lookup"><span data-stu-id="e20c8-131">In addiiton, Windows will not retain the TPM owner password when provisioning the TPM.</span></span> <span data-ttu-id="e20c8-132">有关 [更多详细信息，请参阅 TPM](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password) 所有者密码。</span><span class="sxs-lookup"><span data-stu-id="e20c8-132">See [TPM owner password](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password) for further details.</span></span>

   -   <span data-ttu-id="e20c8-133">托管恢复密钥和恢复密钥包</span><span class="sxs-lookup"><span data-stu-id="e20c8-133">Escrow recovery keys and recovery key packages</span></span>

   -   <span data-ttu-id="e20c8-134">立即报告加密状态</span><span class="sxs-lookup"><span data-stu-id="e20c8-134">Report encryption status immediately</span></span>

   -   <span data-ttu-id="e20c8-135">新的 WMI 提供程序</span><span class="sxs-lookup"><span data-stu-id="e20c8-135">New WMI providers</span></span>

   -   <span data-ttu-id="e20c8-136">详细日志记录</span><span class="sxs-lookup"><span data-stu-id="e20c8-136">Detailed logging</span></span>

   -   <span data-ttu-id="e20c8-137">可靠的错误处理</span><span class="sxs-lookup"><span data-stu-id="e20c8-137">Robust error handling</span></span>

   <span data-ttu-id="e20c8-138">可以从下载 `Invoke-MbamClientDeployment.ps1` 中心下载 [Microsoft.com 脚本](https://www.microsoft.com/download/details.aspx?id=54439)。</span><span class="sxs-lookup"><span data-stu-id="e20c8-138">You can download the `Invoke-MbamClientDeployment.ps1` script from [Microsoft.com Download Center](https://www.microsoft.com/download/details.aspx?id=54439).</span></span> <span data-ttu-id="e20c8-139">这是部署系统调用的主要脚本，用于配置 BitLocker 驱动器加密，以及使用 MBAM 服务器记录恢复密钥。</span><span class="sxs-lookup"><span data-stu-id="e20c8-139">This is the main script that your deployment system will call to configure BitLocker drive encryption and record recovery keys with the MBAM Server.</span></span>

   <span data-ttu-id="e20c8-140">**MBAM 的 WMI 部署方法：** MBAM 2.5 SP1 中添加了以下 WMI 方法，以支持使用 PowerShell 脚本启用 `Invoke-MbamClientDeployment.ps1` BitLocker。</span><span class="sxs-lookup"><span data-stu-id="e20c8-140">**WMI deployment methods for MBAM:** The following WMI methods have been added in MBAM 2.5 SP1 to support enabling BitLocker by using the `Invoke-MbamClientDeployment.ps1` PowerShell script.</span></span>

   <a href="" id="mbam-machine-wmi-class"></a><span data-ttu-id="e20c8-141">**MBAM\_Machine WMI 类** 
   **PrepareTpmAndEscrowOwnerAuth：** 读取 TPM OwnerAuth，然后使用 MBAM 恢复服务将其发送到 MBAM 恢复数据库。</span><span class="sxs-lookup"><span data-stu-id="e20c8-141">**MBAM\_Machine WMI Class**
**PrepareTpmAndEscrowOwnerAuth:** Reads the TPM OwnerAuth and sends it to the MBAM recovery database by using the MBAM recovery service.</span></span> <span data-ttu-id="e20c8-142">如果 TPM 不归所有，并且自动预配未打开，它将生成 TPM OwnerAuth 并取得所有权。</span><span class="sxs-lookup"><span data-stu-id="e20c8-142">If the TPM is not owned and auto-provisioning is not on, it generates a TPM OwnerAuth and takes ownership.</span></span> <span data-ttu-id="e20c8-143">如果失败，将返回错误代码进行疑难解答。</span><span class="sxs-lookup"><span data-stu-id="e20c8-143">If it fails, an error code is returned for troubleshooting.</span></span>

   <span data-ttu-id="e20c8-144">**注意**对于Windows 10版本 1607 或更高版本，Windows可以取得 TPM 的所有权。</span><span class="sxs-lookup"><span data-stu-id="e20c8-144">**Note** For Windows 10, version 1607 or later, only Windows can take ownership of the TPM.</span></span> <span data-ttu-id="e20c8-145">在 addiiton 中，Windows TPM 时不会保留 TPM 所有者密码。</span><span class="sxs-lookup"><span data-stu-id="e20c8-145">In addiiton, Windows will not retain the TPM owner password when provisioning the TPM.</span></span> <span data-ttu-id="e20c8-146">有关 [更多详细信息，请参阅 TPM](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password) 所有者密码。</span><span class="sxs-lookup"><span data-stu-id="e20c8-146">See [TPM owner password](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password) for further details.</span></span>

| <span data-ttu-id="e20c8-147">参数</span><span class="sxs-lookup"><span data-stu-id="e20c8-147">Parameter</span></span> | <span data-ttu-id="e20c8-148">描述</span><span class="sxs-lookup"><span data-stu-id="e20c8-148">Description</span></span> |
| -------- | ----------- |
| <span data-ttu-id="e20c8-149">RecoveryServiceEndPoint</span><span class="sxs-lookup"><span data-stu-id="e20c8-149">RecoveryServiceEndPoint</span></span> | <span data-ttu-id="e20c8-150">指定 MBAM 恢复服务终结点的字符串。</span><span class="sxs-lookup"><span data-stu-id="e20c8-150">A string specifying the MBAM recovery service endpoint.</span></span> |

<span data-ttu-id="e20c8-151">以下是常见错误消息的列表：</span><span class="sxs-lookup"><span data-stu-id="e20c8-151">Here are a list of common error messages:</span></span>

| <span data-ttu-id="e20c8-152">常见返回值</span><span class="sxs-lookup"><span data-stu-id="e20c8-152">Common return values</span></span> | <span data-ttu-id="e20c8-153">错误消息</span><span class="sxs-lookup"><span data-stu-id="e20c8-153">Error message</span></span> |
| -------------------- | ------------- |
|  **<span data-ttu-id="e20c8-154">S_OK</span><span class="sxs-lookup"><span data-stu-id="e20c8-154">S_OK</span></span>**<br /><span data-ttu-id="e20c8-155">0 (0x0) </span><span class="sxs-lookup"><span data-stu-id="e20c8-155">0 (0x0)</span></span> | <span data-ttu-id="e20c8-156">方法成功。</span><span class="sxs-lookup"><span data-stu-id="e20c8-156">The method was successful.</span></span> |
| **<span data-ttu-id="e20c8-157">MBAM_E_TPM_NOT_PRESENT</span><span class="sxs-lookup"><span data-stu-id="e20c8-157">MBAM_E_TPM_NOT_PRESENT</span></span>**<br /><span data-ttu-id="e20c8-158">2147746304 (0x80040200) </span><span class="sxs-lookup"><span data-stu-id="e20c8-158">2147746304 (0x80040200)</span></span> | <span data-ttu-id="e20c8-159">TPM 不在计算机中，或在 BIOS 配置中处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="e20c8-159">TPM is not present in the computer or is disabled in the BIOS configuration.</span></span> |
| **<span data-ttu-id="e20c8-160">MBAM_E_TPM_INCORRECT_STATE</span><span class="sxs-lookup"><span data-stu-id="e20c8-160">MBAM_E_TPM_INCORRECT_STATE</span></span>**<br /><span data-ttu-id="e20c8-161">2147746305 (0x80040201) </span><span class="sxs-lookup"><span data-stu-id="e20c8-161">2147746305 (0x80040201)</span></span> | <span data-ttu-id="e20c8-162">TPM 未处于正确的状态， (启用、激活和所有者安装) 。</span><span class="sxs-lookup"><span data-stu-id="e20c8-162">TPM is not in the correct state (enabled, activated and owner installation allowed).</span></span> |
| **<span data-ttu-id="e20c8-163">MBAM_E_TPM_AUTO_PROVISIONING_PENDING</span><span class="sxs-lookup"><span data-stu-id="e20c8-163">MBAM_E_TPM_AUTO_PROVISIONING_PENDING</span></span>**<br /><span data-ttu-id="e20c8-164">2147746306 (0x80040202) </span><span class="sxs-lookup"><span data-stu-id="e20c8-164">2147746306 (0x80040202)</span></span> | <span data-ttu-id="e20c8-165">MBAM 无法获得 TPM 的所有权，因为自动预配挂起。</span><span class="sxs-lookup"><span data-stu-id="e20c8-165">MBAM cannot take ownership of TPM because auto-provisioning is pending.</span></span> <span data-ttu-id="e20c8-166">请在完成自动设置后重试。</span><span class="sxs-lookup"><span data-stu-id="e20c8-166">Try again after auto-provisioning is completed.</span></span> |
| **<span data-ttu-id="e20c8-167">MBAM_E_TPM_OWNERAUTH_READFAIL</span><span class="sxs-lookup"><span data-stu-id="e20c8-167">MBAM_E_TPM_OWNERAUTH_READFAIL</span></span>**<br /><span data-ttu-id="e20c8-168">2147746307 (0x80040203) </span><span class="sxs-lookup"><span data-stu-id="e20c8-168">2147746307 (0x80040203)</span></span> | <span data-ttu-id="e20c8-169">MBAM 无法读取 TPM 所有者授权值。</span><span class="sxs-lookup"><span data-stu-id="e20c8-169">MBAM cannot read the TPM owner authorization value.</span></span> <span data-ttu-id="e20c8-170">成功托管后，该值可能已删除。</span><span class="sxs-lookup"><span data-stu-id="e20c8-170">The value might have been removed after a successful escrow.</span></span> <span data-ttu-id="e20c8-171">在 Windows 7 上，如果 TPM 归其他人所有，MBAM 将无法读取该值。</span><span class="sxs-lookup"><span data-stu-id="e20c8-171">On Windows 7, MBAM cannot read the value if the TPM is owned by others.</span></span> |
| **<span data-ttu-id="e20c8-172">MBAM_E_REBOOT_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="e20c8-172">MBAM_E_REBOOT_REQUIRED</span></span>**<br /><span data-ttu-id="e20c8-173">2147746308 (0x80040204) </span><span class="sxs-lookup"><span data-stu-id="e20c8-173">2147746308 (0x80040204)</span></span> | <span data-ttu-id="e20c8-174">必须重新启动计算机才能将 TPM 设置为正确的状态。</span><span class="sxs-lookup"><span data-stu-id="e20c8-174">The computer must be restarted to set TPM to the correct state.</span></span> <span data-ttu-id="e20c8-175">您可能需要手动重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="e20c8-175">You might need to manually reboot the computer.</span></span> |
| **<span data-ttu-id="e20c8-176">MBAM_E_SHUTDOWN_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="e20c8-176">MBAM_E_SHUTDOWN_REQUIRED</span></span>**<br /><span data-ttu-id="e20c8-177">2147746309 (0x80040205) </span><span class="sxs-lookup"><span data-stu-id="e20c8-177">2147746309 (0x80040205)</span></span> | <span data-ttu-id="e20c8-178">计算机必须关闭并再次打开，以将 TPM 设置为正确的状态。</span><span class="sxs-lookup"><span data-stu-id="e20c8-178">The computer must be shut down and turned back on to set TPM to the correct state.</span></span> <span data-ttu-id="e20c8-179">您可能需要手动重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="e20c8-179">You might need to manually reboot the computer.</span></span> |
| **<span data-ttu-id="e20c8-180">WS_E_ENDPOINT_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="e20c8-180">WS_E_ENDPOINT_ACCESS_DENIED</span></span>**<br /><span data-ttu-id="e20c8-181">2151481349 (0x803D0005) </span><span class="sxs-lookup"><span data-stu-id="e20c8-181">2151481349 (0x803D0005)</span></span> | <span data-ttu-id="e20c8-182">远程终结点拒绝访问。</span><span class="sxs-lookup"><span data-stu-id="e20c8-182">Access was denied by the remote endpoint.</span></span> |
| **<span data-ttu-id="e20c8-183">WS_E_ENDPOINT_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="e20c8-183">WS_E_ENDPOINT_NOT_FOUND</span></span>**<br /><span data-ttu-id="e20c8-184">2151481357 (0x803D000D) </span><span class="sxs-lookup"><span data-stu-id="e20c8-184">2151481357 (0x803D000D)</span></span> | <span data-ttu-id="e20c8-185">远程终结点不存在或无法定位。</span><span class="sxs-lookup"><span data-stu-id="e20c8-185">The remote endpoint does not exist or could not be located.</span></span> |
| <span data-ttu-id="e20c8-186">\*\*WS_E_ENDPOINT_FAILURE</span><span class="sxs-lookup"><span data-stu-id="e20c8-186">\*\*WS_E_ENDPOINT_FAILURE</span></span><br /><span data-ttu-id="e20c8-187">2151481357 (0x803D000F) </span><span class="sxs-lookup"><span data-stu-id="e20c8-187">2151481357 (0x803D000F)</span></span> | <span data-ttu-id="e20c8-188">远程终结点无法处理请求。</span><span class="sxs-lookup"><span data-stu-id="e20c8-188">The remote endpoint could not process the request.</span></span> |
| **<span data-ttu-id="e20c8-189">WS_E_ENDPOINT_UNREACHABLE</span><span class="sxs-lookup"><span data-stu-id="e20c8-189">WS_E_ENDPOINT_UNREACHABLE</span></span>**<br /><span data-ttu-id="e20c8-190">2151481360 (0x803D0010) </span><span class="sxs-lookup"><span data-stu-id="e20c8-190">2151481360 (0x803D0010)</span></span> | <span data-ttu-id="e20c8-191">远程终结点不可访问。</span><span class="sxs-lookup"><span data-stu-id="e20c8-191">The remote endpoint was not reachable.</span></span> |
| **<span data-ttu-id="e20c8-192">WS_E_ENDPOINT_FAULT_RECEIVED</span><span class="sxs-lookup"><span data-stu-id="e20c8-192">WS_E_ENDPOINT_FAULT_RECEIVED</span></span>**<br /><span data-ttu-id="e20c8-193">2151481363 (0x803D0013) </span><span class="sxs-lookup"><span data-stu-id="e20c8-193">2151481363 (0x803D0013)</span></span> | <span data-ttu-id="e20c8-194">从远程终结点收到包含错误的消息。</span><span class="sxs-lookup"><span data-stu-id="e20c8-194">A message containing a fault was received from the remote endpoint.</span></span> <span data-ttu-id="e20c8-195">确保连接到正确的服务终结点。</span><span class="sxs-lookup"><span data-stu-id="e20c8-195">Make sure you are connecting to the correct service endpoint.</span></span> |
| <span data-ttu-id="e20c8-196">**WS_E_INVALID_ENDPOINT_URL** 2151481376 (0x803D0020) </span><span class="sxs-lookup"><span data-stu-id="e20c8-196">**WS_E_INVALID_ENDPOINT_URL** 2151481376 (0x803D0020)</span></span> | <span data-ttu-id="e20c8-197">终结点地址 URL 无效。</span><span class="sxs-lookup"><span data-stu-id="e20c8-197">The endpoint address URL is not valid.</span></span> <span data-ttu-id="e20c8-198">URL 必须以"http"或"https"开始。</span><span class="sxs-lookup"><span data-stu-id="e20c8-198">The URL must start with “http” or “https”.</span></span> |

   <span data-ttu-id="e20c8-199">**ReportStatus：** 读取卷的合规性状态，然后使用 MBAM 状态报告服务将其发送到 MBAM 合规性状态数据库。</span><span class="sxs-lookup"><span data-stu-id="e20c8-199">**ReportStatus:** Reads the compliance status of the volume and sends it to the MBAM compliance status database by using the MBAM status reporting service.</span></span> <span data-ttu-id="e20c8-200">状态包括加密强度、保护程序类型、保护程序状态和加密状态。</span><span class="sxs-lookup"><span data-stu-id="e20c8-200">The status includes cipher strength, protector type, protector state and encryption state.</span></span> <span data-ttu-id="e20c8-201">如果失败，将返回错误代码进行疑难解答。</span><span class="sxs-lookup"><span data-stu-id="e20c8-201">If it fails, an error code is returned for troubleshooting.</span></span>

   | <span data-ttu-id="e20c8-202">参数</span><span class="sxs-lookup"><span data-stu-id="e20c8-202">Parameter</span></span> | <span data-ttu-id="e20c8-203">描述</span><span class="sxs-lookup"><span data-stu-id="e20c8-203">Description</span></span> |
   | --------- | ----------- |
   | <span data-ttu-id="e20c8-204">ReportingServiceEndPoint</span><span class="sxs-lookup"><span data-stu-id="e20c8-204">ReportingServiceEndPoint</span></span> | <span data-ttu-id="e20c8-205">指定 MBAM 状态报告服务终结点的字符串。</span><span class="sxs-lookup"><span data-stu-id="e20c8-205">A string specifying the MBAM status reporting service endpoint.</span></span> |

   <span data-ttu-id="e20c8-206">以下是常见错误消息的列表：</span><span class="sxs-lookup"><span data-stu-id="e20c8-206">Here are a list of common error messages:</span></span>

   | <span data-ttu-id="e20c8-207">常见返回值</span><span class="sxs-lookup"><span data-stu-id="e20c8-207">Common return values</span></span> | <span data-ttu-id="e20c8-208">错误消息</span><span class="sxs-lookup"><span data-stu-id="e20c8-208">Error message</span></span> |
   | -------------------- | ------------- |
   | **<span data-ttu-id="e20c8-209">S_OK</span><span class="sxs-lookup"><span data-stu-id="e20c8-209">S_OK</span></span>**<br /> <span data-ttu-id="e20c8-210">0 (0x0) </span><span class="sxs-lookup"><span data-stu-id="e20c8-210">0 (0x0)</span></span> | <span data-ttu-id="e20c8-211">方法成功</span><span class="sxs-lookup"><span data-stu-id="e20c8-211">The method was successful</span></span> |
   | **<span data-ttu-id="e20c8-212">WS_E_ENDPOINT_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="e20c8-212">WS_E_ENDPOINT_ACCESS_DENIED</span></span>**<br /><span data-ttu-id="e20c8-213">2151481349 (0x803D0005) </span><span class="sxs-lookup"><span data-stu-id="e20c8-213">2151481349 (0x803D0005)</span></span> | <span data-ttu-id="e20c8-214">远程终结点拒绝访问。</span><span class="sxs-lookup"><span data-stu-id="e20c8-214">Access was denied by the remote endpoint.</span></span>|
   | **<span data-ttu-id="e20c8-215">WS_E_ENDPOINT_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="e20c8-215">WS_E_ENDPOINT_NOT_FOUND</span></span>**<br /><span data-ttu-id="e20c8-216">2151481357 (0x803D000D) </span><span class="sxs-lookup"><span data-stu-id="e20c8-216">2151481357 (0x803D000D)</span></span> | <span data-ttu-id="e20c8-217">远程终结点不存在或无法定位。</span><span class="sxs-lookup"><span data-stu-id="e20c8-217">The remote endpoint does not exist or could not be located.</span></span> |
   | **<span data-ttu-id="e20c8-218">WS_E_ENDPOINT_FAILURE</span><span class="sxs-lookup"><span data-stu-id="e20c8-218">WS_E_ENDPOINT_FAILURE</span></span>**<br /> <span data-ttu-id="e20c8-219">2151481357 (0x803D000F) </span><span class="sxs-lookup"><span data-stu-id="e20c8-219">2151481357 (0x803D000F)</span></span> | <span data-ttu-id="e20c8-220">远程终结点无法处理请求。</span><span class="sxs-lookup"><span data-stu-id="e20c8-220">The remote endpoint could not process the request.</span></span> |
   | **<span data-ttu-id="e20c8-221">WS_E_ENDPOINT_UNREACHABLE</span><span class="sxs-lookup"><span data-stu-id="e20c8-221">WS_E_ENDPOINT_UNREACHABLE</span></span>**<br /><span data-ttu-id="e20c8-222">2151481360 (0x803D0010) </span><span class="sxs-lookup"><span data-stu-id="e20c8-222">2151481360 (0x803D0010)</span></span> | <span data-ttu-id="e20c8-223">远程终结点不可访问。</span><span class="sxs-lookup"><span data-stu-id="e20c8-223">The remote endpoint was not reachable.</span></span> |
   | **<span data-ttu-id="e20c8-224">WS_E_ENDPOINT_FAULT_RECEIVED</span><span class="sxs-lookup"><span data-stu-id="e20c8-224">WS_E_ENDPOINT_FAULT_RECEIVED</span></span>**<br /><span data-ttu-id="e20c8-225">2151481363 (0x803D0013) </span><span class="sxs-lookup"><span data-stu-id="e20c8-225">2151481363 (0x803D0013)</span></span> | <span data-ttu-id="e20c8-226">从远程终结点收到包含错误的消息。</span><span class="sxs-lookup"><span data-stu-id="e20c8-226">A message containing a fault was received from the remote endpoint.</span></span> <span data-ttu-id="e20c8-227">确保连接到正确的服务终结点。</span><span class="sxs-lookup"><span data-stu-id="e20c8-227">Make sure you are connecting to the correct service endpoint.</span></span> |
   | **<span data-ttu-id="e20c8-228">WS_E_INVALID_ENDPOINT_URL</span><span class="sxs-lookup"><span data-stu-id="e20c8-228">WS_E_INVALID_ENDPOINT_URL</span></span>**<br /><span data-ttu-id="e20c8-229">2151481376 (0x803D0020) </span><span class="sxs-lookup"><span data-stu-id="e20c8-229">2151481376 (0x803D0020)</span></span> | <span data-ttu-id="e20c8-230">终结点地址 URL 无效。</span><span class="sxs-lookup"><span data-stu-id="e20c8-230">The endpoint address URL is not valid.</span></span> <span data-ttu-id="e20c8-231">URL 必须以"http"或"https"开始。</span><span class="sxs-lookup"><span data-stu-id="e20c8-231">The URL must start with “http” or “https”.</span></span> |

   <a href="" id="mbam-volume-wmi-class"></a><span data-ttu-id="e20c8-232">**MBAM\_Volume WMI Class** **EscrowRecoveryKey：** 读取卷的恢复数字密码和密钥包，然后使用 MBAM 恢复服务将它们发送到 MBAM 恢复数据库。</span><span class="sxs-lookup"><span data-stu-id="e20c8-232">**MBAM\_Volume WMI Class** **EscrowRecoveryKey:** Reads the recovery numerical password and key package of the volume and sends them to the MBAM recovery database by using the MBAM recovery service.</span></span> <span data-ttu-id="e20c8-233">如果失败，将返回错误代码进行疑难解答。</span><span class="sxs-lookup"><span data-stu-id="e20c8-233">If it fails, an error code is returned for troubleshooting.</span></span>

   | <span data-ttu-id="e20c8-234">参数</span><span class="sxs-lookup"><span data-stu-id="e20c8-234">Parameter</span></span> | <span data-ttu-id="e20c8-235">描述</span><span class="sxs-lookup"><span data-stu-id="e20c8-235">Description</span></span> |
   | --------- | ----------- |
   | <span data-ttu-id="e20c8-236">RecoveryServiceEndPoint</span><span class="sxs-lookup"><span data-stu-id="e20c8-236">RecoveryServiceEndPoint</span></span> | <span data-ttu-id="e20c8-237">指定 MBAM 恢复服务终结点的字符串。</span><span class="sxs-lookup"><span data-stu-id="e20c8-237">A string specifying the MBAM recovery service endpoint.</span></span> |

   <span data-ttu-id="e20c8-238">以下是常见错误消息的列表：</span><span class="sxs-lookup"><span data-stu-id="e20c8-238">Here are a list of common error messages:</span></span>

   | <span data-ttu-id="e20c8-239">常见返回值</span><span class="sxs-lookup"><span data-stu-id="e20c8-239">Common return values</span></span> | <span data-ttu-id="e20c8-240">错误消息</span><span class="sxs-lookup"><span data-stu-id="e20c8-240">Error message</span></span> |
   | -------------------- | ------------- |
   | **<span data-ttu-id="e20c8-241">S_OK</span><span class="sxs-lookup"><span data-stu-id="e20c8-241">S_OK</span></span>**<br /><span data-ttu-id="e20c8-242">0 (0x0) </span><span class="sxs-lookup"><span data-stu-id="e20c8-242">0 (0x0)</span></span> | <span data-ttu-id="e20c8-243">方法成功</span><span class="sxs-lookup"><span data-stu-id="e20c8-243">The method was successful</span></span> |
   | **<span data-ttu-id="e20c8-244">FVE_E_LOCKED_VOLUME</span><span class="sxs-lookup"><span data-stu-id="e20c8-244">FVE_E_LOCKED_VOLUME</span></span>**<br /><span data-ttu-id="e20c8-245">2150694912 (0x80310000) </span><span class="sxs-lookup"><span data-stu-id="e20c8-245">2150694912 (0x80310000)</span></span> | <span data-ttu-id="e20c8-246">卷已锁定。</span><span class="sxs-lookup"><span data-stu-id="e20c8-246">The volume is locked.</span></span> |
   | **<span data-ttu-id="e20c8-247">FVE_E_PROTECTOR_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="e20c8-247">FVE_E_PROTECTOR_NOT_FOUND</span></span>**<br /><span data-ttu-id="e20c8-248">2150694963 (0x80310033) </span><span class="sxs-lookup"><span data-stu-id="e20c8-248">2150694963 (0x80310033)</span></span> | <span data-ttu-id="e20c8-249">未找到卷的数字密码保护程序。</span><span class="sxs-lookup"><span data-stu-id="e20c8-249">A Numerical Password protector was not found for the volume.</span></span> |
   | **<span data-ttu-id="e20c8-250">WS_E_ENDPOINT_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="e20c8-250">WS_E_ENDPOINT_ACCESS_DENIED</span></span>**<br /><span data-ttu-id="e20c8-251">2151481349 (0x803D0005) </span><span class="sxs-lookup"><span data-stu-id="e20c8-251">2151481349 (0x803D0005)</span></span> | <span data-ttu-id="e20c8-252">远程终结点拒绝访问。</span><span class="sxs-lookup"><span data-stu-id="e20c8-252">Access was denied by the remote endpoint.</span></span> |
   | **<span data-ttu-id="e20c8-253">WS_E_ENDPOINT_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="e20c8-253">WS_E_ENDPOINT_NOT_FOUND</span></span>**<br /><span data-ttu-id="e20c8-254">2151481357 (0x803D000D) </span><span class="sxs-lookup"><span data-stu-id="e20c8-254">2151481357 (0x803D000D)</span></span> | <span data-ttu-id="e20c8-255">远程终结点不存在或无法定位。</span><span class="sxs-lookup"><span data-stu-id="e20c8-255">The remote endpoint does not exist or could not be located.</span></span> |
   | **<span data-ttu-id="e20c8-256">WS_E_ENDPOINT_FAILURE</span><span class="sxs-lookup"><span data-stu-id="e20c8-256">WS_E_ENDPOINT_FAILURE</span></span>**<br /><span data-ttu-id="e20c8-257">2151481357 (0x803D000F) </span><span class="sxs-lookup"><span data-stu-id="e20c8-257">2151481357 (0x803D000F)</span></span> | <span data-ttu-id="e20c8-258">远程终结点无法处理请求。</span><span class="sxs-lookup"><span data-stu-id="e20c8-258">The remote endpoint could not process the request.</span></span> |
   | **<span data-ttu-id="e20c8-259">WS_E_ENDPOINT_UNREACHABLE</span><span class="sxs-lookup"><span data-stu-id="e20c8-259">WS_E_ENDPOINT_UNREACHABLE</span></span>**<br /><span data-ttu-id="e20c8-260">2151481360 (0x803D0010) </span><span class="sxs-lookup"><span data-stu-id="e20c8-260">2151481360 (0x803D0010)</span></span> | <span data-ttu-id="e20c8-261">远程终结点不可访问。</span><span class="sxs-lookup"><span data-stu-id="e20c8-261">The remote endpoint was not reachable.</span></span> |
   | **<span data-ttu-id="e20c8-262">WS_E_ENDPOINT_FAULT_RECEIVED</span><span class="sxs-lookup"><span data-stu-id="e20c8-262">WS_E_ENDPOINT_FAULT_RECEIVED</span></span>**<br /><span data-ttu-id="e20c8-263">2151481363 (0x803D0013) </span><span class="sxs-lookup"><span data-stu-id="e20c8-263">2151481363 (0x803D0013)</span></span> | <span data-ttu-id="e20c8-264">从远程终结点收到包含错误的消息。</span><span class="sxs-lookup"><span data-stu-id="e20c8-264">A message containing a fault was received from the remote endpoint.</span></span> <span data-ttu-id="e20c8-265">确保连接到正确的服务终结点。</span><span class="sxs-lookup"><span data-stu-id="e20c8-265">Make sure you are connecting to the correct service endpoint.</span></span> |
   | **<span data-ttu-id="e20c8-266">WS_E_INVALID_ENDPOINT_URL</span><span class="sxs-lookup"><span data-stu-id="e20c8-266">WS_E_INVALID_ENDPOINT_URL</span></span>**<br /><span data-ttu-id="e20c8-267">2151481376 (0x803D0020) </span><span class="sxs-lookup"><span data-stu-id="e20c8-267">2151481376 (0x803D0020)</span></span> | <span data-ttu-id="e20c8-268">终结点地址 URL 无效。</span><span class="sxs-lookup"><span data-stu-id="e20c8-268">The endpoint address URL is not valid.</span></span> <span data-ttu-id="e20c8-269">URL 必须以"http"或"https"开始。</span><span class="sxs-lookup"><span data-stu-id="e20c8-269">The URL must start with “http” or “https”.</span></span> |
     

2. **<span data-ttu-id="e20c8-270">使用 Microsoft Deployment Toolkit (MDT) 和 PowerShell 部署 MBAM</span><span class="sxs-lookup"><span data-stu-id="e20c8-270">Deploy MBAM by using Microsoft Deployment Toolkit (MDT) and PowerShell</span></span>**

   1.  <span data-ttu-id="e20c8-271">在 MDT 中，创建新的部署共享或打开现有部署共享。</span><span class="sxs-lookup"><span data-stu-id="e20c8-271">In MDT, create a new deployment share or open an existing deployment share.</span></span>

       **<span data-ttu-id="e20c8-272">注意</span><span class="sxs-lookup"><span data-stu-id="e20c8-272">Note</span></span>**  
       <span data-ttu-id="e20c8-273">`Invoke-MbamClientDeployment.ps1`PowerShell 脚本可用于任何映像过程或工具。</span><span class="sxs-lookup"><span data-stu-id="e20c8-273">The `Invoke-MbamClientDeployment.ps1` PowerShell script can be used with any imaging process or tool.</span></span> <span data-ttu-id="e20c8-274">本部分演示如何使用 MDT 集成它，但步骤类似于将其与任何其他进程或工具集成。</span><span class="sxs-lookup"><span data-stu-id="e20c8-274">This section shows how to integrate it by using MDT, but the steps are similar to integrating it with any other process or tool.</span></span>

       **<span data-ttu-id="e20c8-275">注意</span><span class="sxs-lookup"><span data-stu-id="e20c8-275">Caution</span></span>**  
       <span data-ttu-id="e20c8-276">如果你使用的是 BitLocker 预预配 (WinPE) 并且想要保留 TPM 所有者授权值，则必须在安装重新启动到完整操作系统之前，立即在 WinPE 中添加脚本。 `SaveWinPETpmOwnerAuth.wsf`</span><span class="sxs-lookup"><span data-stu-id="e20c8-276">If you are using BitLocker pre-provisioning (WinPE) and want to maintain the TPM owner authorization value, you must add the `SaveWinPETpmOwnerAuth.wsf` script in WinPE immediately before the installation reboots into the full operating system.</span></span> **<span data-ttu-id="e20c8-277">如果不使用此脚本，将在重新启动时丢失 TPM 所有者授权值。</span><span class="sxs-lookup"><span data-stu-id="e20c8-277">If you do not use this script, you will lose the TPM owner authorization value on reboot.</span></span>**

   2.  <span data-ttu-id="e20c8-278">复制到 `Invoke-MbamClientDeployment.ps1` \*\* &lt; DeploymentShare &gt; \\Scripts\*\*。</span><span class="sxs-lookup"><span data-stu-id="e20c8-278">Copy `Invoke-MbamClientDeployment.ps1` to **&lt;DeploymentShare&gt;\\Scripts**.</span></span> <span data-ttu-id="e20c8-279">如果你使用的是预预配，将文件 `SaveWinPETpmOwnerAuth.wsf` 复制到\*\* &lt; DeploymentShare &gt; \\Scripts\*\*中。</span><span class="sxs-lookup"><span data-stu-id="e20c8-279">If you are using pre-provisioning, copy the `SaveWinPETpmOwnerAuth.wsf` file into **&lt;DeploymentShare&gt;\\Scripts**.</span></span>

   3.  <span data-ttu-id="e20c8-280">将 MBAM 2.5 SP1 客户端应用程序添加到部署共享中的 Applications 节点。</span><span class="sxs-lookup"><span data-stu-id="e20c8-280">Add the MBAM 2.5 SP1 client application to the Applications node in the deployment share.</span></span>

       1.  <span data-ttu-id="e20c8-281">在"**应用程序"节点**下，单击"**新建应用程序"。**</span><span class="sxs-lookup"><span data-stu-id="e20c8-281">Under the **Applications** node, click **New Application**.</span></span>

       2.  <span data-ttu-id="e20c8-282">选择 **"使用源文件的应用程序"。**</span><span class="sxs-lookup"><span data-stu-id="e20c8-282">Select **Application with Source Files**.</span></span> <span data-ttu-id="e20c8-283">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e20c8-283">Click **Next**.</span></span>

       3.  <span data-ttu-id="e20c8-284">在 **"应用程序名称"** 中，键入"MBAM 2.5 SP1 客户端"。</span><span class="sxs-lookup"><span data-stu-id="e20c8-284">In **Application Name**, type “MBAM 2.5 SP1 Client”.</span></span> <span data-ttu-id="e20c8-285">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e20c8-285">Click **Next**.</span></span>

       4.  <span data-ttu-id="e20c8-286">浏览到包含 的目录 `MBAMClientSetup-<Version>.msi` 。</span><span class="sxs-lookup"><span data-stu-id="e20c8-286">Browse to the directory containing `MBAMClientSetup-<Version>.msi`.</span></span> <span data-ttu-id="e20c8-287">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e20c8-287">Click **Next**.</span></span>

       5.  <span data-ttu-id="e20c8-288">键入"MBAM 2.5 SP1 客户端"作为要创建的目录。</span><span class="sxs-lookup"><span data-stu-id="e20c8-288">Type “MBAM 2.5 SP1 Client” as the directory to create.</span></span> <span data-ttu-id="e20c8-289">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e20c8-289">Click **Next**.</span></span>

       6.  <span data-ttu-id="e20c8-290">在 `msiexec /i MBAMClientSetup-<Version>.msi /quiet` 命令行中输入 。</span><span class="sxs-lookup"><span data-stu-id="e20c8-290">Enter `msiexec /i MBAMClientSetup-<Version>.msi /quiet` at the command line.</span></span> <span data-ttu-id="e20c8-291">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e20c8-291">Click **Next**.</span></span>

       7.  <span data-ttu-id="e20c8-292">接受其余默认值以完成"新建应用程序"向导。</span><span class="sxs-lookup"><span data-stu-id="e20c8-292">Accept the remaining defaults to complete the New Application wizard.</span></span>

   4.  <span data-ttu-id="e20c8-293">在 MDT 中，右键单击部署共享的名称，然后单击 **属性**。</span><span class="sxs-lookup"><span data-stu-id="e20c8-293">In MDT, right-click the name of the deployment share and click **Properties**.</span></span> <span data-ttu-id="e20c8-294">单击" **规则"** 选项卡。添加以下行：</span><span class="sxs-lookup"><span data-stu-id="e20c8-294">Click the **Rules** tab. Add the following lines:</span></span>

       `SkipBitLocker=YES``BDEInstall=TPM``BDEInstallSuppress=NO``BDEWaitForEncryption=YES`

       <span data-ttu-id="e20c8-295">单击"确定"关闭窗口。</span><span class="sxs-lookup"><span data-stu-id="e20c8-295">Click OK to close the window.</span></span>

   5.  <span data-ttu-id="e20c8-296">在"任务序列"节点下，编辑用于部署Windows序列。</span><span class="sxs-lookup"><span data-stu-id="e20c8-296">Under the Task Sequences node, edit an existing task sequence used for Windows Deployment.</span></span> <span data-ttu-id="e20c8-297">如果需要，可以通过右键单击"任务序列"节点，选择"新建任务\*\*\*\* 序列"并完成向导\*\*\*\* 来创建一个新任务序列。</span><span class="sxs-lookup"><span data-stu-id="e20c8-297">If you want, you can create a new task sequence by right-clicking the **Task Sequences** node, selecting **New Task Sequence**, and completing the wizard.</span></span>

       <span data-ttu-id="e20c8-298">在所选 **任务序列** 的"任务序列"选项卡上，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="e20c8-298">On the **Task Sequence** tab of the selected task sequence, perform these steps:</span></span>

       1.  <span data-ttu-id="e20c8-299">在 **"预安装** "文件夹下，启用可选任务"启用 \*\*BitLocker \*\* (脱机) "（如果你希望 BitLocker 在 WinPE 中启用，这将仅加密已用空间）。</span><span class="sxs-lookup"><span data-stu-id="e20c8-299">Under the **Preinstall** folder, enable the optional task **Enable BitLocker (Offline)** if you want BitLocker enabled in WinPE, which encrypts used space only.</span></span>

       2.  <span data-ttu-id="e20c8-300">若要在使用预预配时保留 TPM OwnerAuth，允许 MBAM 稍后托管它，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="e20c8-300">To persist TPM OwnerAuth when using pre-provisioning, allowing MBAM to escrow it later, do the following:</span></span>

           1.  <span data-ttu-id="e20c8-301">查找 **安装操作系统** 步骤</span><span class="sxs-lookup"><span data-stu-id="e20c8-301">Find the **Install Operating System** step</span></span>

           2.  <span data-ttu-id="e20c8-302">在命令行 **后添加新的"运行命令行** "步骤</span><span class="sxs-lookup"><span data-stu-id="e20c8-302">Add a new **Run Command Line** step after it</span></span>

           3.  <span data-ttu-id="e20c8-303">将步骤命名 **为 Persist TPM OwnerAuth**</span><span class="sxs-lookup"><span data-stu-id="e20c8-303">Name the step **Persist TPM OwnerAuth**</span></span>

           4.  <span data-ttu-id="e20c8-304">将命令行设置为"注意 `cscript.exe "%SCRIPTROOT%/SaveWinPETpmOwnerAuth.wsf"`
            **："Windows 10**版本 1607 或更高版本，Windows TPM 的所有权。</span><span class="sxs-lookup"><span data-stu-id="e20c8-304">Set the command line to `cscript.exe "%SCRIPTROOT%/SaveWinPETpmOwnerAuth.wsf"`
**Note:** For Windows 10, version 1607 or later, only Windows can take ownership of the TPM.</span></span> <span data-ttu-id="e20c8-305">在 addiiton 中，Windows TPM 时不会保留 TPM 所有者密码。</span><span class="sxs-lookup"><span data-stu-id="e20c8-305">In addiiton, Windows will not retain the TPM owner password when provisioning the TPM.</span></span> <span data-ttu-id="e20c8-306">有关 [更多详细信息，请参阅 TPM](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password) 所有者密码。</span><span class="sxs-lookup"><span data-stu-id="e20c8-306">See [TPM owner password](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password) for further details.</span></span>

       3.  <span data-ttu-id="e20c8-307">在状态 **还原文件夹中** ，删除启用 **BitLocker** 任务。</span><span class="sxs-lookup"><span data-stu-id="e20c8-307">In the **State Restore** folder, delete the **Enable BitLocker** task.</span></span>

       4.  <span data-ttu-id="e20c8-308">在"**状态还原"** 文件夹中的"自定义任务"**下**，创建新的"**安装应用程序"** 任务，并将其命名为 **"安装 MBAM 代理"。**</span><span class="sxs-lookup"><span data-stu-id="e20c8-308">In the **State Restore** folder under **Custom Tasks**, create a new **Install Application** task and name it **Install MBAM Agent**.</span></span> <span data-ttu-id="e20c8-309">单击" **安装单个应用程序"** 单选按钮并浏览到之前创建的 MBAM 2.5 SP1 客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="e20c8-309">Click the **Install Single Application** radio button and browse to the MBAM 2.5 SP1 client application created earlier.</span></span>

       5.  <span data-ttu-id="e20c8-310">在"\*\*\*\* 自定义任务"下的\*\*\*\*"状态还原"文件夹中，在 MBAM 2.5 SP1 客户端应用程序步骤 () 后创建新的"运行**PowerShell**脚本"任务) 并 (根据你的环境环境) ：</span><span class="sxs-lookup"><span data-stu-id="e20c8-310">In the **State Restore** folder under **Custom Tasks**, create a new **Run PowerShell Script** task (after the MBAM 2.5 SP1 Client application step) with the following settings (update the parameters as appropriate for your environment):</span></span>

           -   <span data-ttu-id="e20c8-311">名称：为 MBAM 配置 BitLocker</span><span class="sxs-lookup"><span data-stu-id="e20c8-311">Name: Configure BitLocker for MBAM</span></span>

           -   <span data-ttu-id="e20c8-312">PowerShell 脚本：</span><span class="sxs-lookup"><span data-stu-id="e20c8-312">PowerShell script:</span></span> `Invoke-MbamClientDeployment.ps1`

           -   <span data-ttu-id="e20c8-313">参数：</span><span class="sxs-lookup"><span data-stu-id="e20c8-313">Parameters:</span></span>

               <table>
               <colgroup>
               <col width="33%" />
               <col width="33%" />
               <col width="33%" />
               </colgroup>
               <tbody>
               <tr class="odd">
               <td align="left"><p><span data-ttu-id="e20c8-314">-RecoveryServiceEndpoint</span><span class="sxs-lookup"><span data-stu-id="e20c8-314">-RecoveryServiceEndpoint</span></span></p></td>
               <td align="left"><p><span data-ttu-id="e20c8-315">必需</span><span class="sxs-lookup"><span data-stu-id="e20c8-315">Required</span></span></p></td>
               <td align="left"><p><span data-ttu-id="e20c8-316">MBAM 恢复服务终结点</span><span class="sxs-lookup"><span data-stu-id="e20c8-316">MBAM recovery service endpoint</span></span></p></td>
               </tr>
               <tr class="even">
               <td align="left"><p><span data-ttu-id="e20c8-317">-StatusReportingServiceEndpoint</span><span class="sxs-lookup"><span data-stu-id="e20c8-317">-StatusReportingServiceEndpoint</span></span></p></td>
               <td align="left"><p><span data-ttu-id="e20c8-318">可选</span><span class="sxs-lookup"><span data-stu-id="e20c8-318">Optional</span></span></p></td>
               <td align="left"><p><span data-ttu-id="e20c8-319">MBAM 状态报告服务终结点</span><span class="sxs-lookup"><span data-stu-id="e20c8-319">MBAM status reporting service endpoint</span></span></p></td>
               </tr>
               <tr class="odd">
               <td align="left"><p><span data-ttu-id="e20c8-320">-EncryptionMethod</span><span class="sxs-lookup"><span data-stu-id="e20c8-320">-EncryptionMethod</span></span></p></td>
               <td align="left"><p><span data-ttu-id="e20c8-321">可选</span><span class="sxs-lookup"><span data-stu-id="e20c8-321">Optional</span></span></p></td>
               <td align="left"><p><span data-ttu-id="e20c8-322">加密方法 (默认值：AES 128) </span><span class="sxs-lookup"><span data-stu-id="e20c8-322">Encryption method (default: AES 128)</span></span></p></td>
               </tr>
               <tr class="even">
               <td align="left"><p><span data-ttu-id="e20c8-323">-EncryptAndEscrowDataVolume</span><span class="sxs-lookup"><span data-stu-id="e20c8-323">-EncryptAndEscrowDataVolume</span></span></p></td>
               <td align="left"><p><span data-ttu-id="e20c8-324">开关</span><span class="sxs-lookup"><span data-stu-id="e20c8-324">Switch</span></span></p></td>
               <td align="left"><p><span data-ttu-id="e20c8-325">指定对数据卷 (加密) 和托管数据卷恢复密钥 () </span><span class="sxs-lookup"><span data-stu-id="e20c8-325">Specify to encrypt data volume(s) and escrow data volume recovery key(s)</span></span></p></td>
               </tr>
               <tr class="odd">
               <td align="left"><p><span data-ttu-id="e20c8-326">-WaitForEncryptionToComplete</span><span class="sxs-lookup"><span data-stu-id="e20c8-326">-WaitForEncryptionToComplete</span></span></p></td>
               <td align="left"><p><span data-ttu-id="e20c8-327">开关</span><span class="sxs-lookup"><span data-stu-id="e20c8-327">Switch</span></span></p></td>
               <td align="left"><p><span data-ttu-id="e20c8-328">指定等待加密完成</span><span class="sxs-lookup"><span data-stu-id="e20c8-328">Specify to wait for the encryption to complete</span></span></p></td>
               </tr>
               <tr class="even">
               <td align="left"><p><span data-ttu-id="e20c8-329">-DoNotResumeSuspendedEncryption</span><span class="sxs-lookup"><span data-stu-id="e20c8-329">-DoNotResumeSuspendedEncryption</span></span></p></td>
               <td align="left"><p><span data-ttu-id="e20c8-330">开关</span><span class="sxs-lookup"><span data-stu-id="e20c8-330">Switch</span></span></p></td>
               <td align="left"><p><span data-ttu-id="e20c8-331">指定部署脚本将不会恢复挂起的加密</span><span class="sxs-lookup"><span data-stu-id="e20c8-331">Specify that the deployment script will not resume suspended encryption</span></span></p></td>
               </tr>
               <tr class="odd">
               <td align="left"><p><span data-ttu-id="e20c8-332">-IgnoreEscrowOwnerAuthFailure</span><span class="sxs-lookup"><span data-stu-id="e20c8-332">-IgnoreEscrowOwnerAuthFailure</span></span></p></td>
               <td align="left"><p><span data-ttu-id="e20c8-333">开关</span><span class="sxs-lookup"><span data-stu-id="e20c8-333">Switch</span></span></p></td>
               <td align="left"><p><span data-ttu-id="e20c8-334">指定以忽略 TPM 所有者-身份验证托管失败。</span><span class="sxs-lookup"><span data-stu-id="e20c8-334">Specify to ignore TPM owner-auth escrow failure.</span></span> <span data-ttu-id="e20c8-335">它应在 MBAM 无法读取 TPM 所有者身份验证的情况下使用，例如，如果启用了 TPM 自动预配</span><span class="sxs-lookup"><span data-stu-id="e20c8-335">It should be used in the scenarios where MBAM is not able to read the TPM owner-auth, e.g. if TPM auto provisioning is enabled</span></span></p></td>
               </tr>
               <tr class="even">
               <td align="left"><p><span data-ttu-id="e20c8-336">-IgnoreEscrowRecoveryKeyFailure</span><span class="sxs-lookup"><span data-stu-id="e20c8-336">-IgnoreEscrowRecoveryKeyFailure</span></span></p></td>
               <td align="left"><p><span data-ttu-id="e20c8-337">开关</span><span class="sxs-lookup"><span data-stu-id="e20c8-337">Switch</span></span></p></td>
               <td align="left"><p><span data-ttu-id="e20c8-338">指定忽略卷恢复密钥托管失败</span><span class="sxs-lookup"><span data-stu-id="e20c8-338">Specify to ignore volume recovery key escrow failure</span></span></p></td>
               </tr>
               <tr class="odd">
               <td align="left"><p><span data-ttu-id="e20c8-339">-IgnoreReportStatusFailure</span><span class="sxs-lookup"><span data-stu-id="e20c8-339">-IgnoreReportStatusFailure</span></span></p></td>
               <td align="left"><p><span data-ttu-id="e20c8-340">开关</span><span class="sxs-lookup"><span data-stu-id="e20c8-340">Switch</span></span></p></td>
               <td align="left"><p><span data-ttu-id="e20c8-341">指定忽略状态报告失败</span><span class="sxs-lookup"><span data-stu-id="e20c8-341">Specify to ignore status reporting failure</span></span></p></td>
               </tr>
               </tbody>
               </table>

                 

**<span data-ttu-id="e20c8-342">在部署中启用使用 MBAM 2.5 或更早版本Windows BitLocker</span><span class="sxs-lookup"><span data-stu-id="e20c8-342">To enable BitLocker using MBAM 2.5 or earlier as part of a Windows deployment</span></span>**

1.  <span data-ttu-id="e20c8-343">安装 MBAM 客户端。</span><span class="sxs-lookup"><span data-stu-id="e20c8-343">Install the MBAM Client.</span></span> <span data-ttu-id="e20c8-344">有关说明，请参阅 [如何使用命令行部署 MBAM 客户端](how-to-deploy-the-mbam-client-by-using-a-command-line.md)。</span><span class="sxs-lookup"><span data-stu-id="e20c8-344">For instructions, see [How to Deploy the MBAM Client by Using a Command Line](how-to-deploy-the-mbam-client-by-using-a-command-line.md).</span></span>

2.  <span data-ttu-id="e20c8-345">将计算机加入推荐 (域) 。</span><span class="sxs-lookup"><span data-stu-id="e20c8-345">Join the computer to a domain (recommended).</span></span>

    -   <span data-ttu-id="e20c8-346">如果计算机未加入域，则恢复密码不会存储在 MBAM 密钥恢复服务中。</span><span class="sxs-lookup"><span data-stu-id="e20c8-346">If the computer is not joined to a domain, the recovery password is not stored in the MBAM Key Recovery service.</span></span> <span data-ttu-id="e20c8-347">默认情况下，MBAM 不允许加密，除非可以存储恢复密钥。</span><span class="sxs-lookup"><span data-stu-id="e20c8-347">By default, MBAM does not allow encryption to occur unless the recovery key can be stored.</span></span>

    -   <span data-ttu-id="e20c8-348">如果计算机在恢复密钥存储在 MBAM 服务器上之前以恢复模式启动，则没有可用的恢复方法，并且计算机必须重新进行想象。</span><span class="sxs-lookup"><span data-stu-id="e20c8-348">If a computer starts in recovery mode before the recovery key is stored on the MBAM Server, no recovery method is available, and the computer has to be reimaged.</span></span>

3.  <span data-ttu-id="e20c8-349">以管理员角色打开命令提示符，并停止 MBAM 服务。</span><span class="sxs-lookup"><span data-stu-id="e20c8-349">Open a command prompt as an administrator, and stop the MBAM service.</span></span>

4.  <span data-ttu-id="e20c8-350">通过**键入以下命令**，将\*\*\*\* 服务设置为手动或按需：</span><span class="sxs-lookup"><span data-stu-id="e20c8-350">Set the service to **Manual** or **On demand** by typing the following commands:</span></span>

    **<span data-ttu-id="e20c8-351">net stop mbamagent</span><span class="sxs-lookup"><span data-stu-id="e20c8-351">net stop mbamagent</span></span>**

    **<span data-ttu-id="e20c8-352">sc config mbamagent start= demand</span><span class="sxs-lookup"><span data-stu-id="e20c8-352">sc config mbamagent start= demand</span></span>**

5.  <span data-ttu-id="e20c8-353">设置注册表值，以便 MBAM 客户端忽略组策略设置，改为设置加密以启动Windows部署到该客户端计算机的时间。</span><span class="sxs-lookup"><span data-stu-id="e20c8-353">Set the registry values so that the MBAM Client ignores the Group Policy settings and instead sets encryption to start the time Windows is deployed to that client computer.</span></span>

    **<span data-ttu-id="e20c8-354">注意</span><span class="sxs-lookup"><span data-stu-id="e20c8-354">Caution</span></span>**  
    <span data-ttu-id="e20c8-355">此步骤介绍如何修改Windows注册表。</span><span class="sxs-lookup"><span data-stu-id="e20c8-355">This step describes how to modify the Windows registry.</span></span> <span data-ttu-id="e20c8-356">不正确地使用注册表编辑器可能会导致严重问题，可能需要重新安装Windows。</span><span class="sxs-lookup"><span data-stu-id="e20c8-356">Using Registry Editor incorrectly can cause serious issues that can require you to reinstall Windows.</span></span> <span data-ttu-id="e20c8-357">我们无法保证由于不正确地使用注册表编辑器而导致的问题能够得到解决。</span><span class="sxs-lookup"><span data-stu-id="e20c8-357">We cannot guarantee that issues resulting from the incorrect use of Registry Editor can be resolved.</span></span> <span data-ttu-id="e20c8-358">使用注册表编辑器的风险由你自己承担。</span><span class="sxs-lookup"><span data-stu-id="e20c8-358">Use Registry Editor at your own risk.</span></span>

    1.  <span data-ttu-id="e20c8-359">为仅操作系统加密设置\*\*\*\* TPM，运行 Regedit.exe，然后从 C：\\Program Files\\Microsoft\\MDOP MBAM\\MBAMDeploymentKeyTemplate.reg 导入注册表项模板。</span><span class="sxs-lookup"><span data-stu-id="e20c8-359">Set the TPM for **Operating system only encryption**, run Regedit.exe, and then import the registry key template from C:\\Program Files\\Microsoft\\MDOP MBAM\\MBAMDeploymentKeyTemplate.reg.</span></span>

    2.  <span data-ttu-id="e20c8-360">在Regedit.exe中，转到 HKLM\\SOFTWARE\\Microsoft\\MBAM，然后配置下表中列出的设置。</span><span class="sxs-lookup"><span data-stu-id="e20c8-360">In Regedit.exe, go to HKLM\\SOFTWARE\\Microsoft\\MBAM, and configure the settings that are listed in the following table.</span></span>

        **<span data-ttu-id="e20c8-361">注意</span><span class="sxs-lookup"><span data-stu-id="e20c8-361">Note</span></span>**  
        <span data-ttu-id="e20c8-362">你可以在此处设置与 MBAM 相关的组策略设置或注册表值。</span><span class="sxs-lookup"><span data-stu-id="e20c8-362">You can set Group Policy settings or registry values related to MBAM here.</span></span> <span data-ttu-id="e20c8-363">这些设置将替代之前设置的值。</span><span class="sxs-lookup"><span data-stu-id="e20c8-363">These settings will override previously set values.</span></span>

        <span data-ttu-id="e20c8-364">注册表项 配置设置</span><span class="sxs-lookup"><span data-stu-id="e20c8-364">Registry entry Configuration settings</span></span>

        <span data-ttu-id="e20c8-365">DeploymentTime</span><span class="sxs-lookup"><span data-stu-id="e20c8-365">DeploymentTime</span></span>

        <span data-ttu-id="e20c8-366">0 = 关闭</span><span class="sxs-lookup"><span data-stu-id="e20c8-366">0 = Off</span></span>

        <span data-ttu-id="e20c8-367">1 = 将部署时间策略 (默认设置) – 使用此设置在将 Windows部署到客户端计算机时启用加密。</span><span class="sxs-lookup"><span data-stu-id="e20c8-367">1 = Use deployment time policy settings (default) – use this setting to enable encryption at the time Windows is deployed to the client computer.</span></span>

        <span data-ttu-id="e20c8-368">UseKeyRecoveryService</span><span class="sxs-lookup"><span data-stu-id="e20c8-368">UseKeyRecoveryService</span></span>

        <span data-ttu-id="e20c8-369">0 = 请勿使用 (两个注册表项，在这种情况下，无需使用) </span><span class="sxs-lookup"><span data-stu-id="e20c8-369">0 = Do not use key escrow (the next two registry entries are not required in this case)</span></span>

        <span data-ttu-id="e20c8-370">1 = 使用密钥恢复系统中的密钥托管 (默认) </span><span class="sxs-lookup"><span data-stu-id="e20c8-370">1 = Use key escrow in Key Recovery system (default)</span></span>

        <span data-ttu-id="e20c8-371">这是推荐设置，它使 MBAM 能够存储恢复密钥。</span><span class="sxs-lookup"><span data-stu-id="e20c8-371">This is the recommended setting, which enables MBAM to store the recovery keys.</span></span> <span data-ttu-id="e20c8-372">计算机必须能够与 MBAM 密钥恢复服务通信。</span><span class="sxs-lookup"><span data-stu-id="e20c8-372">The computer must be able to communicate with the MBAM Key Recovery service.</span></span> <span data-ttu-id="e20c8-373">在继续之前，请验证计算机能否与该服务通信。</span><span class="sxs-lookup"><span data-stu-id="e20c8-373">Verify that the computer can communicate with the service before you proceed.</span></span>

        <span data-ttu-id="e20c8-374">KeyRecoveryOptions</span><span class="sxs-lookup"><span data-stu-id="e20c8-374">KeyRecoveryOptions</span></span>

        <span data-ttu-id="e20c8-375">0 = 仅上载恢复密钥</span><span class="sxs-lookup"><span data-stu-id="e20c8-375">0 = Uploads Recovery Key only</span></span>

        <span data-ttu-id="e20c8-376">1 = 将恢复密钥和密钥恢复包 (默认) </span><span class="sxs-lookup"><span data-stu-id="e20c8-376">1 = Uploads Recovery Key and Key Recovery Package (default)</span></span>

        <span data-ttu-id="e20c8-377">KeyRecoveryServiceEndPoint</span><span class="sxs-lookup"><span data-stu-id="e20c8-377">KeyRecoveryServiceEndPoint</span></span>

        <span data-ttu-id="e20c8-378">将此值设置为运行密钥恢复服务的服务器的 URL，例如，http:// 计算机名称 &lt; &gt; /MBAMRecoveryAndHardwareService/CoreService.svc。</span><span class="sxs-lookup"><span data-stu-id="e20c8-378">Set this value to the URL for the server running the Key Recovery service, for example, http://&lt;computer name&gt;/MBAMRecoveryAndHardwareService/CoreService.svc.</span></span>


6.  <span data-ttu-id="e20c8-379">MBAM 客户端将在 MBAM 客户端部署期间重新启动系统。</span><span class="sxs-lookup"><span data-stu-id="e20c8-379">The MBAM Client will restart the system during the MBAM Client deployment.</span></span> <span data-ttu-id="e20c8-380">准备好执行此重启后，以管理员角色在命令提示符下运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e20c8-380">When you are ready for this restart, run the following command at a command prompt as an administrator:</span></span>

    **<span data-ttu-id="e20c8-381">net start mbamagent</span><span class="sxs-lookup"><span data-stu-id="e20c8-381">net start mbamagent</span></span>**

7.  <span data-ttu-id="e20c8-382">当计算机重新启动，并且 BIOS 提示您时，接受 TPM 更改。</span><span class="sxs-lookup"><span data-stu-id="e20c8-382">When the computers restarts, and the BIOS prompts you, accept the TPM change.</span></span>

8.  <span data-ttu-id="e20c8-383">在 Windows 客户端操作系统映像过程中，当你准备好开始加密时，以管理员角色打开命令提示符，并键入以下命令以将开始设置为自动并重新启动 MBAM\*\*\*\* 客户端代理：</span><span class="sxs-lookup"><span data-stu-id="e20c8-383">During the Windows client operating system imaging process, when you are ready to start encryption, open a command prompt as an administrator, and type the following commands to set the start to **Automatic** and to restart the MBAM Client agent:</span></span>

    **<span data-ttu-id="e20c8-384">sc config mbamagent start= auto</span><span class="sxs-lookup"><span data-stu-id="e20c8-384">sc config mbamagent start= auto</span></span>**

    **<span data-ttu-id="e20c8-385">net start mbamagent</span><span class="sxs-lookup"><span data-stu-id="e20c8-385">net start mbamagent</span></span>**

9.  <span data-ttu-id="e20c8-386">若要删除绕过注册表值，请运行 Regedit.exe，然后转到 HKLM\\SOFTWARE\\Microsoft 注册表项。</span><span class="sxs-lookup"><span data-stu-id="e20c8-386">To delete the bypass registry values, run Regedit.exe, and go to the HKLM\\SOFTWARE\\Microsoft registry entry.</span></span> <span data-ttu-id="e20c8-387">右键单击**MBAM**节点，然后单击"删除 **"。**</span><span class="sxs-lookup"><span data-stu-id="e20c8-387">Right-click the **MBAM** node, and then click **Delete**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e20c8-388">相关主题</span><span class="sxs-lookup"><span data-stu-id="e20c8-388">Related topics</span></span>

[<span data-ttu-id="e20c8-389">部署 MBAM 2.5 客户端</span><span class="sxs-lookup"><span data-stu-id="e20c8-389">Deploying the MBAM 2.5 Client</span></span>](deploying-the-mbam-25-client.md)

[<span data-ttu-id="e20c8-390">规划 MBAM 2.5 客户端部署</span><span class="sxs-lookup"><span data-stu-id="e20c8-390">Planning for MBAM 2.5 Client Deployment</span></span>](planning-for-mbam-25-client-deployment.md)

## <a name="got-a-suggestion-for-mbam"></a><span data-ttu-id="e20c8-391">有关于 MBAM 的建议吗？</span><span class="sxs-lookup"><span data-stu-id="e20c8-391">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="e20c8-392">在此处添加建议或对建议 [投票](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)。</span><span class="sxs-lookup"><span data-stu-id="e20c8-392">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span>
- <span data-ttu-id="e20c8-393">对于 MBAM 问题，请使用 [MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="e20c8-393">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>
