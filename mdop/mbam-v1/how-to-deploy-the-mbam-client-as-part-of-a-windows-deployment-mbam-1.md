---
title: 如何在 Windows 部署过程中部署 MBAM 客户端
description: 如何在 Windows 部署过程中部署 MBAM 客户端
author: dansimp
ms.assetid: 8704bf33-535d-41da-b9b2-45b60754367e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a63311bcc93d84472ceff5c80c9222fefd5445c0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803663"
---
# <span data-ttu-id="1b716-103">如何在 Windows 部署过程中部署 MBAM 客户端</span><span class="sxs-lookup"><span data-stu-id="1b716-103">How to Deploy the MBAM Client as Part of a Windows Deployment</span></span>


<span data-ttu-id="1b716-104">Microsoft BitLocker 管理和监视（MBAM）客户端使管理员能够在企业中的计算机上实施和监视 BitLocker 驱动器加密。</span><span class="sxs-lookup"><span data-stu-id="1b716-104">The Microsoft BitLocker Administration and Monitoring (MBAM) Client enables administrators to enforce and monitor BitLocker drive encryption on computers in the enterprise.</span></span> <span data-ttu-id="1b716-105">通过在计算机映像和 Windows 部署过程中启用客户端计算机上的 BitLocker 管理和加密，可将 BitLocker 客户端集成到组织中。</span><span class="sxs-lookup"><span data-stu-id="1b716-105">The BitLocker Client can be integrated into an organization by enabling BitLocker management and encryption on client computers during the computer imaging and Windows deployment process.</span></span>

**<span data-ttu-id="1b716-106">注意</span><span class="sxs-lookup"><span data-stu-id="1b716-106">Note</span></span>**  
<span data-ttu-id="1b716-107">若要查看 MBAM 客户端系统要求，请参阅[MBAM 1.0 支持的配置](mbam-10-supported-configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="1b716-107">To review the MBAM Client system requirements, see [MBAM 1.0 Supported Configurations](mbam-10-supported-configurations.md).</span></span>



<span data-ttu-id="1b716-108">在 Windows 部署的初始映像阶段，使用 BitLocker 加密客户端计算机可以降低 MBAM 实现的管理开销。</span><span class="sxs-lookup"><span data-stu-id="1b716-108">Encryption of client computers with BitLocker during the initial imaging stage of a Windows deployment can lower the administrative overhead for MBAM implementation.</span></span> <span data-ttu-id="1b716-109">此方法还可确保已部署的每台计算机都已运行 BitLocker 且配置正确。</span><span class="sxs-lookup"><span data-stu-id="1b716-109">This approach also ensures that every computer that is deployed already has BitLocker running and is configured correctly.</span></span>

**<span data-ttu-id="1b716-110">警告</span><span class="sxs-lookup"><span data-stu-id="1b716-110">Warning</span></span>**  
<span data-ttu-id="1b716-111">本主题介绍如何使用注册表编辑器更改 Windows 注册表。</span><span class="sxs-lookup"><span data-stu-id="1b716-111">This topic describes how to change the Windows registry by using Registry Editor.</span></span> <span data-ttu-id="1b716-112">如果不正确地更改 Windows 注册表，则可能会导致严重问题，可能需要重新安装 Windows。</span><span class="sxs-lookup"><span data-stu-id="1b716-112">If you change the Windows registry incorrectly, you can cause serious problems that might require you to reinstall Windows.</span></span> <span data-ttu-id="1b716-113">在更改注册表之前，应创建注册表文件（.dat 和 .dat）的备份副本。</span><span class="sxs-lookup"><span data-stu-id="1b716-113">You should make a backup copy of the registry files (System.dat and User.dat) before you change the registry.</span></span> <span data-ttu-id="1b716-114">Microsoft 无法保证更改注册表时可能出现的问题可以解决。</span><span class="sxs-lookup"><span data-stu-id="1b716-114">Microsoft cannot guarantee that the problems that might occur when you change the registry can be resolved.</span></span> <span data-ttu-id="1b716-115">更改注册表的风险由您自己承担。</span><span class="sxs-lookup"><span data-stu-id="1b716-115">Change the registry at your own risk.</span></span>



**<span data-ttu-id="1b716-116">将计算机加密为 Windows 部署的一部分</span><span class="sxs-lookup"><span data-stu-id="1b716-116">To encrypt a computer as part of Windows deployment</span></span>**

1.  <span data-ttu-id="1b716-117">如果你的组织计划在 BitLocker 中使用受信任的平台模块（TPM）保护器选项或 TPM + PIN 保护程序选项，则必须在 MBAM 的初始部署之前激活 TPM 芯片。</span><span class="sxs-lookup"><span data-stu-id="1b716-117">If your organization plans to use the Trusted Platform Module (TPM) protector or the TPM + PIN protector options in BitLocker, you must activate the TPM chip before the initial deployment of MBAM.</span></span> <span data-ttu-id="1b716-118">当你激活 TPM 芯片时，你可以在该过程的稍后部分避免重新启动，并确保根据你的组织的要求正确配置 TPM 芯片。</span><span class="sxs-lookup"><span data-stu-id="1b716-118">When you activate the TPM chip, you avoid a reboot later in the process, and you ensure that the TPM chips are correctly configured according to the requirements of your organization.</span></span> <span data-ttu-id="1b716-119">必须在计算机的 BIOS 中手动激活 TPM 芯片。</span><span class="sxs-lookup"><span data-stu-id="1b716-119">You must activate the TPM chip manually in the computer's BIOS.</span></span> <span data-ttu-id="1b716-120">有关如何配置 TPM 芯片的更多详细信息，请参阅制造商文档。</span><span class="sxs-lookup"><span data-stu-id="1b716-120">Refer to the manufacturer documentation for more details about how to configure the TPM chip.</span></span>

2.  <span data-ttu-id="1b716-121">安装 MBAM 客户端代理。</span><span class="sxs-lookup"><span data-stu-id="1b716-121">Install the MBAM client agent.</span></span>

3.  <span data-ttu-id="1b716-122">我们建议你将计算机加入域 .。。</span><span class="sxs-lookup"><span data-stu-id="1b716-122">We recommend that you join the computer to a domain...</span></span>

    -   <span data-ttu-id="1b716-123">如果计算机未加入域，则恢复密码不会存储在 MBAM 密钥恢复服务中。</span><span class="sxs-lookup"><span data-stu-id="1b716-123">If the computer is not joined to a domain, the recovery password is not stored in the MBAM Key Recovery service.</span></span> <span data-ttu-id="1b716-124">默认情况下，除非可以存储恢复密钥，否则 MBAM 不允许进行加密。</span><span class="sxs-lookup"><span data-stu-id="1b716-124">By default, MBAM does not allow encryption to occur unless the recovery key can be stored.</span></span>

    -   <span data-ttu-id="1b716-125">如果在 MBAM 服务器上存储恢复密钥之前计算机在恢复模式下启动，则必须 reimaged 计算机。</span><span class="sxs-lookup"><span data-stu-id="1b716-125">If a computer starts in recovery mode before the recovery key is stored on the MBAM server, the computer has to be reimaged.</span></span> <span data-ttu-id="1b716-126">没有可用的恢复方法。</span><span class="sxs-lookup"><span data-stu-id="1b716-126">No recovery method is available.</span></span>

4.  <span data-ttu-id="1b716-127">以管理员身份打开命令提示符，停止 MBAM 服务，然后将服务设置为 "**手动** **" 或 "按需**"。</span><span class="sxs-lookup"><span data-stu-id="1b716-127">Open a command prompt as an administrator, stop the MBAM service, and then set the service to **manual** or **on demand**.</span></span> <span data-ttu-id="1b716-128">然后运行下列命令：</span><span class="sxs-lookup"><span data-stu-id="1b716-128">Then, run the following commands:</span></span>

    **<span data-ttu-id="1b716-129">net stop mbamagent</span><span class="sxs-lookup"><span data-stu-id="1b716-129">net stop mbamagent</span></span>**

    **<span data-ttu-id="1b716-130">sc config mbamagent start = demand</span><span class="sxs-lookup"><span data-stu-id="1b716-130">sc config mbamagent start= demand</span></span>**

5.  <span data-ttu-id="1b716-131">将 MBAM 代理的注册表设置设置为 "忽略组策略"，并运行**仅限操作系统**的 TPM 加密若要执行此操作，请运行**regedit**，然后从 c:\\program files Files\\Microsoft\\MDOP MBAM\\MBAMDeploymentKeyTemplate.reg. 导入注册表项模板。</span><span class="sxs-lookup"><span data-stu-id="1b716-131">Set the registry settings for the MBAM agent to ignore Group Policy and run the TPM for **operating system only encryption** To do this, run **regedit**, and then import the registry key template from C:\\Program Files\\Microsoft\\MDOP MBAM\\MBAMDeploymentKeyTemplate.reg.</span></span>

6.  <span data-ttu-id="1b716-132">在 regedit 中，转到 HKLM\\SOFTWARE\\Microsoft\\MBAM 并配置下表中列出的设置。</span><span class="sxs-lookup"><span data-stu-id="1b716-132">In regedit, go to HKLM\\SOFTWARE\\Microsoft\\MBAM and configure the settings that are listed in the following table.</span></span>

    <span data-ttu-id="1b716-133">注册表项</span><span class="sxs-lookup"><span data-stu-id="1b716-133">Registry entry</span></span>

    <span data-ttu-id="1b716-134">配置设置</span><span class="sxs-lookup"><span data-stu-id="1b716-134">Configuration settings</span></span>

    <span data-ttu-id="1b716-135">DeploymentTime</span><span class="sxs-lookup"><span data-stu-id="1b716-135">DeploymentTime</span></span>

    <span data-ttu-id="1b716-136">0 = 关闭</span><span class="sxs-lookup"><span data-stu-id="1b716-136">0 = OFF</span></span>

    <span data-ttu-id="1b716-137">1 = 使用部署时间策略设置（默认值）</span><span class="sxs-lookup"><span data-stu-id="1b716-137">1 = Use deployment time policy settings (default)</span></span>

    <span data-ttu-id="1b716-138">UseKeyRecoveryService</span><span class="sxs-lookup"><span data-stu-id="1b716-138">UseKeyRecoveryService</span></span>

    <span data-ttu-id="1b716-139">0 = 不使用密钥保管（这种情况下，不需要接下来的两个注册表项）。</span><span class="sxs-lookup"><span data-stu-id="1b716-139">0 = Do not use key escrow (The next two registry entries are not required in this case.)</span></span>

    <span data-ttu-id="1b716-140">1 = 在密钥恢复系统中使用密钥托管（默认）</span><span class="sxs-lookup"><span data-stu-id="1b716-140">1 = Use key escrow in Key Recovery system (default)</span></span>

    <span data-ttu-id="1b716-141">建议：计算机必须能够与密钥恢复服务进行通信。</span><span class="sxs-lookup"><span data-stu-id="1b716-141">Recommended: The computer must be able to communicate with the Key Recovery service.</span></span> <span data-ttu-id="1b716-142">继续之前，请验证计算机是否可以与服务通信。</span><span class="sxs-lookup"><span data-stu-id="1b716-142">Verify that the computer can communicate with the service before you proceed.</span></span>

    <span data-ttu-id="1b716-143">KeyRecoveryOptions</span><span class="sxs-lookup"><span data-stu-id="1b716-143">KeyRecoveryOptions</span></span>

    <span data-ttu-id="1b716-144">0 = 仅上载恢复密钥</span><span class="sxs-lookup"><span data-stu-id="1b716-144">0 = Upload Recovery Key Only</span></span>

    <span data-ttu-id="1b716-145">1 = 上载恢复密钥和密钥恢复包（默认值）</span><span class="sxs-lookup"><span data-stu-id="1b716-145">1 = Upload Recovery Key and Key Recovery Package (default)</span></span>

    <span data-ttu-id="1b716-146">KeyRecoveryServiceEndPoint</span><span class="sxs-lookup"><span data-stu-id="1b716-146">KeyRecoveryServiceEndPoint</span></span>

    <span data-ttu-id="1b716-147">将此值设置为密钥恢复 web 服务器的 URL。</span><span class="sxs-lookup"><span data-stu-id="1b716-147">Set this value to the URL for the Key Recovery web server.</span></span>

    <span data-ttu-id="1b716-148">示例： http:// &lt; 计算机名 &gt; /MBAMRecoveryAndHardwareService/CoreService.svc。</span><span class="sxs-lookup"><span data-stu-id="1b716-148">Example: http://&lt;computer name&gt;/MBAMRecoveryAndHardwareService/CoreService.svc.</span></span>



~~~
**Note**  
MBAM policy or registry values can be set here to override the previously set values.
~~~



7. <span data-ttu-id="1b716-149">MBAM 代理在 MBAM 客户端部署期间重新启动系统。</span><span class="sxs-lookup"><span data-stu-id="1b716-149">The MBAM agent restarts the system during MBAM client deployment.</span></span> <span data-ttu-id="1b716-150">当您准备好进行此重启时，请以管理员身份在命令提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="1b716-150">When you are ready for this reboot, run the following command at a command prompt as an administrator:</span></span>

   **<span data-ttu-id="1b716-151">net start mbamagent</span><span class="sxs-lookup"><span data-stu-id="1b716-151">net start mbamagent</span></span>**

8. <span data-ttu-id="1b716-152">当计算机重新启动并且 BIOS 提示您接受 TPM 更改时，请接受更改。</span><span class="sxs-lookup"><span data-stu-id="1b716-152">When the computers restarts and the BIOS prompts you to accept a TPM change, accept the change.</span></span>

9. <span data-ttu-id="1b716-153">在 Windows 客户端操作系统成像过程中，当你准备好开始加密时，请重新启动 MBAM 代理服务。</span><span class="sxs-lookup"><span data-stu-id="1b716-153">During the Windows client operating system imaging process, when you are ready to start encryption, restart the MBAM agent service.</span></span> <span data-ttu-id="1b716-154">然后，若要将 "开始" 设置为 "**自动**"，请以管理员身份打开命令提示符，并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="1b716-154">Then, to set start to **automatic**, open a command prompt as an administrator and run the following commands:</span></span>

   **<span data-ttu-id="1b716-155">sc config mbamagent start = auto</span><span class="sxs-lookup"><span data-stu-id="1b716-155">sc config mbamagent start= auto</span></span>**

   **<span data-ttu-id="1b716-156">net start mbamagent</span><span class="sxs-lookup"><span data-stu-id="1b716-156">net start mbamagent</span></span>**

10. <span data-ttu-id="1b716-157">删除旁路注册表值。</span><span class="sxs-lookup"><span data-stu-id="1b716-157">Remove the bypass registry values.</span></span> <span data-ttu-id="1b716-158">若要执行此操作，请运行 regedit，浏览到 HKLM\\SOFTWARE\\Microsoft 注册表项，右键单击**MBAM**节点，然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="1b716-158">To do this, run regedit, browse to the HKLM\\SOFTWARE\\Microsoft registry entry, right-click the **MBAM** node, and then click **Delete**.</span></span>

## <span data-ttu-id="1b716-159">相关主题</span><span class="sxs-lookup"><span data-stu-id="1b716-159">Related topics</span></span>


[<span data-ttu-id="1b716-160">部署 MBAM 1.0 客户端</span><span class="sxs-lookup"><span data-stu-id="1b716-160">Deploying the MBAM 1.0 Client</span></span>](deploying-the-mbam-10-client.md)









