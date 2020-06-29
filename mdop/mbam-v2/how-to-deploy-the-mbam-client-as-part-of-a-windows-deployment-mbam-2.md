---
title: 如何在 Windows 部署过程中部署 MBAM 客户端
description: 如何在 Windows 部署过程中部署 MBAM 客户端
author: dansimp
ms.assetid: 67387de7-8b02-4412-9850-3b8d8e5c18af
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d75e5748167d2d4866f98e9d3611584067ecd418
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803605"
---
# <span data-ttu-id="36f8e-103">如何在 Windows 部署过程中部署 MBAM 客户端</span><span class="sxs-lookup"><span data-stu-id="36f8e-103">How to Deploy the MBAM Client as Part of a Windows Deployment</span></span>


<span data-ttu-id="36f8e-104">Microsoft BitLocker 管理和监视（MBAM）客户端使管理员能够在企业中的计算机上实施和监视 BitLocker 驱动器加密。</span><span class="sxs-lookup"><span data-stu-id="36f8e-104">The Microsoft BitLocker Administration and Monitoring (MBAM) Client enables administrators to enforce and monitor BitLocker drive encryption on computers in the enterprise.</span></span> <span data-ttu-id="36f8e-105">如果具有受信任的平台模块（TPM）芯片的计算机，则可以通过在客户端计算机上启用 BitLocker 管理和加密作为映像和 Windows 部署过程的一部分，将 BitLocker 客户端集成到组织中。</span><span class="sxs-lookup"><span data-stu-id="36f8e-105">If computers that have a Trusted Platform Module (TPM) chip, the BitLocker client can be integrated into an organization by enabling BitLocker management and encryption on client computers as part of the imaging and Windows deployment process.</span></span>

**<span data-ttu-id="36f8e-106">注意</span><span class="sxs-lookup"><span data-stu-id="36f8e-106">Note</span></span>**  
<span data-ttu-id="36f8e-107">若要查看 Microsoft BitLocker 管理和监视客户端系统要求，请参阅[MBAM 2.0 支持的配置](mbam-20-supported-configurations-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="36f8e-107">To review the Microsoft BitLocker Administration and Monitoring Client system requirements, see [MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md).</span></span>



<span data-ttu-id="36f8e-108">在 Windows 部署的初始映像阶段使用 BitLocker 加密客户端计算机可以降低在组织中实施 MBAM 所需的管理开销。</span><span class="sxs-lookup"><span data-stu-id="36f8e-108">Encrypting client computers with BitLocker during the initial imaging stage of a Windows deployment can lower the administrative overhead necessary for implementing MBAM in an organization.</span></span> <span data-ttu-id="36f8e-109">它还确保已部署的每台计算机都已运行 BitLocker 且配置正确。</span><span class="sxs-lookup"><span data-stu-id="36f8e-109">It also ensures that every computer that is deployed already has BitLocker running and is configured correctly.</span></span>

**<span data-ttu-id="36f8e-110">注意</span><span class="sxs-lookup"><span data-stu-id="36f8e-110">Note</span></span>**  
<span data-ttu-id="36f8e-111">本主题介绍修改 Windows 注册表的过程。</span><span class="sxs-lookup"><span data-stu-id="36f8e-111">The procedure in this topic describes modifying the Windows registry.</span></span> <span data-ttu-id="36f8e-112">注册表编辑器使用不当可能导致严重问题，可能需要重新安装 Windows。</span><span class="sxs-lookup"><span data-stu-id="36f8e-112">Using Registry Editor incorrectly can cause serious problems that may require you to reinstall Windows.</span></span> <span data-ttu-id="36f8e-113">Microsoft 无法保证无法通过错误地使用注册表编辑器来解决所产生的问题。</span><span class="sxs-lookup"><span data-stu-id="36f8e-113">Microsoft cannot guarantee that problems resulting from the incorrect use of Registry Editor can be solved.</span></span> <span data-ttu-id="36f8e-114">使用注册表编辑器的风险由您自己承担。</span><span class="sxs-lookup"><span data-stu-id="36f8e-114">Use Registry Editor at your own risk.</span></span>



**<span data-ttu-id="36f8e-115">将计算机加密为 Windows 部署的一部分</span><span class="sxs-lookup"><span data-stu-id="36f8e-115">To encrypt a computer as part of Windows deployment</span></span>**

1.  <span data-ttu-id="36f8e-116">如果你的组织计划在 BitLocker 中使用受信任的平台模块（TPM）保护器选项或 TPM + PIN 保护程序选项，则必须在 MBAM 的初始部署之前激活 TPM 芯片。</span><span class="sxs-lookup"><span data-stu-id="36f8e-116">If your organization is planning to use the Trusted Platform Module (TPM) protector or the TPM + PIN protector options in BitLocker, you must activate the TPM chip before the initial deployment of MBAM.</span></span> <span data-ttu-id="36f8e-117">当你激活 TPM 芯片时，你可以在该过程的稍后部分避免重新启动，并确保根据你的组织的要求正确配置 TPM 芯片。</span><span class="sxs-lookup"><span data-stu-id="36f8e-117">When you activate the TPM chip, you avoid a reboot later in the process, and you ensure that the TPM chips are correctly configured according to the requirements of your organization.</span></span> <span data-ttu-id="36f8e-118">必须在计算机的 BIOS 中手动激活 TPM 芯片。</span><span class="sxs-lookup"><span data-stu-id="36f8e-118">You must activate the TPM chip manually in the BIOS of the computer.</span></span>

    **<span data-ttu-id="36f8e-119">注意</span><span class="sxs-lookup"><span data-stu-id="36f8e-119">Note</span></span>**  
    <span data-ttu-id="36f8e-120">某些供应商提供的工具可在操作系统内打开和激活 BIOS 中的 TPM 芯片。</span><span class="sxs-lookup"><span data-stu-id="36f8e-120">Some vendors provide tools to turn on and activate the TPM chip in the BIOS from within the operating system.</span></span> <span data-ttu-id="36f8e-121">有关如何配置 TPM 芯片的更多详细信息，请参阅制造商文档。</span><span class="sxs-lookup"><span data-stu-id="36f8e-121">Refer to the manufacturer documentation for more details about how to configure the TPM chip.</span></span>



2.  <span data-ttu-id="36f8e-122">安装 Microsoft BitLocker 管理和监视客户端代理。</span><span class="sxs-lookup"><span data-stu-id="36f8e-122">Install the Microsoft BitLocker Administration and Monitoring client agent.</span></span>

3.  <span data-ttu-id="36f8e-123">将计算机加入域（推荐）。</span><span class="sxs-lookup"><span data-stu-id="36f8e-123">Join the computer to a domain (recommended).</span></span>

    -   <span data-ttu-id="36f8e-124">如果计算机未加入域，则恢复密码不会存储在 MBAM 密钥恢复服务中。</span><span class="sxs-lookup"><span data-stu-id="36f8e-124">If the computer is not joined to the domain, the recovery password is not stored in the MBAM Key Recovery service.</span></span> <span data-ttu-id="36f8e-125">默认情况下，除非可以存储恢复密钥，否则 MBAM 不允许进行加密。</span><span class="sxs-lookup"><span data-stu-id="36f8e-125">By default, MBAM does not allow encryption to occur unless the recovery key can be stored.</span></span>

    -   <span data-ttu-id="36f8e-126">如果在 MBAM 服务器上存储恢复密钥之前计算机在恢复模式下启动，则必须 reimaged 计算机。</span><span class="sxs-lookup"><span data-stu-id="36f8e-126">If a computer starts in recovery mode before the recovery key is stored on the MBAM Server, the computer has to be reimaged.</span></span> <span data-ttu-id="36f8e-127">没有可用的恢复方法。</span><span class="sxs-lookup"><span data-stu-id="36f8e-127">No recovery method is available.</span></span>

4.  <span data-ttu-id="36f8e-128">以管理员身份运行命令提示符，停止 MBAM 服务，然后将该服务设置为**手动**或**按需**，然后通过键入以下命令开始：</span><span class="sxs-lookup"><span data-stu-id="36f8e-128">Run the command prompt as an administrator, stop the MBAM service, and then set the service to **manual** or **on demand**, and then start by typing the following commands:</span></span>

    **<span data-ttu-id="36f8e-129">net stop mbamagent</span><span class="sxs-lookup"><span data-stu-id="36f8e-129">net stop mbamagent</span></span>**

    **<span data-ttu-id="36f8e-130">sc config mbamagent start = demand</span><span class="sxs-lookup"><span data-stu-id="36f8e-130">sc config mbamagent start= demand</span></span>**

5.  <span data-ttu-id="36f8e-131">将 MBAM 代理的注册表设置设置为 "忽略组策略"，并通过运行**Regedit**，然后从 C:\\program files Files\\Microsoft\\MDOP MBAM\\MBAMDeploymentKeyTemplate.reg. 导入注册表项模板来运行**仅限操作系统加密**的 TPM</span><span class="sxs-lookup"><span data-stu-id="36f8e-131">Set the registry settings for the MBAM agent to ignore Group Policy and run the TPM for **operating system only encryption** by running **Regedit**, and then importing the registry key template from C:\\Program Files\\Microsoft\\MDOP MBAM\\MBAMDeploymentKeyTemplate.reg.</span></span>

6.  <span data-ttu-id="36f8e-132">在 regedit 中，转到 HKLM\\SOFTWARE\\Microsoft\\MBAM，并配置下表中列出的设置。</span><span class="sxs-lookup"><span data-stu-id="36f8e-132">In regedit, go to HKLM\\SOFTWARE\\Microsoft\\MBAM, and configure the settings that are listed in the following table.</span></span>

    <span data-ttu-id="36f8e-133">注册表项</span><span class="sxs-lookup"><span data-stu-id="36f8e-133">Registry entry</span></span>

    <span data-ttu-id="36f8e-134">配置设置</span><span class="sxs-lookup"><span data-stu-id="36f8e-134">Configuration settings</span></span>

    <span data-ttu-id="36f8e-135">DeploymentTime</span><span class="sxs-lookup"><span data-stu-id="36f8e-135">DeploymentTime</span></span>

    <span data-ttu-id="36f8e-136">0 = 关闭</span><span class="sxs-lookup"><span data-stu-id="36f8e-136">0 = OFF</span></span>

    <span data-ttu-id="36f8e-137">1 = 使用部署时间策略设置（默认值）</span><span class="sxs-lookup"><span data-stu-id="36f8e-137">1 = Use deployment time policy settings (default)</span></span>

    <span data-ttu-id="36f8e-138">UseKeyRecoveryService</span><span class="sxs-lookup"><span data-stu-id="36f8e-138">UseKeyRecoveryService</span></span>

    <span data-ttu-id="36f8e-139">0 = 不使用密钥保管（这种情况下，不需要接下来的两个注册表项）</span><span class="sxs-lookup"><span data-stu-id="36f8e-139">0 = Do not use key escrow ( the next two registry entries are not required in this case)</span></span>

    <span data-ttu-id="36f8e-140">1 = 在密钥恢复系统中使用密钥托管（默认）</span><span class="sxs-lookup"><span data-stu-id="36f8e-140">1 = Use key escrow in Key Recovery system (default)</span></span>

    <span data-ttu-id="36f8e-141">建议：计算机必须能够与密钥恢复服务进行通信。</span><span class="sxs-lookup"><span data-stu-id="36f8e-141">Recommended: The computer must be able to communicate with the Key Recovery service.</span></span> <span data-ttu-id="36f8e-142">继续之前，请验证计算机是否可以与服务通信。</span><span class="sxs-lookup"><span data-stu-id="36f8e-142">Verify that the computer can communicate with the service before you proceed.</span></span>

    <span data-ttu-id="36f8e-143">KeyRecoveryOptions</span><span class="sxs-lookup"><span data-stu-id="36f8e-143">KeyRecoveryOptions</span></span>

    <span data-ttu-id="36f8e-144">0 = 仅上载恢复密钥</span><span class="sxs-lookup"><span data-stu-id="36f8e-144">0 = Uploads Recovery Key Only</span></span>

    <span data-ttu-id="36f8e-145">1 = 上载恢复密钥和密钥恢复包（默认）</span><span class="sxs-lookup"><span data-stu-id="36f8e-145">1 = Uploads Recovery Key and Key Recovery Package (default)</span></span>

    <span data-ttu-id="36f8e-146">KeyRecoveryServiceEndPoint</span><span class="sxs-lookup"><span data-stu-id="36f8e-146">KeyRecoveryServiceEndPoint</span></span>

    <span data-ttu-id="36f8e-147">将此值设置为密钥恢复 web 服务器的 URL，例如，http:// &lt; 计算机名 &gt; /MBAMRecoveryAndHardwareService/CoreService.svc。</span><span class="sxs-lookup"><span data-stu-id="36f8e-147">Set this value to the URL for the Key Recovery web server, for example, http://&lt;computer name&gt;/MBAMRecoveryAndHardwareService/CoreService.svc.</span></span>



~~~
**Note**  
MBAM policy or registry values can be set here to override previously set values.
~~~



7. <span data-ttu-id="36f8e-148">MBAM 代理在 MBAM 客户端部署期间重新启动系统。</span><span class="sxs-lookup"><span data-stu-id="36f8e-148">The MBAM agent restarts the system during MBAM client deployment.</span></span> <span data-ttu-id="36f8e-149">当您准备好进行此重启时，请以管理员身份在命令提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="36f8e-149">When you are ready for this reboot, run the following command at a command prompt as an administrator:</span></span>

   **<span data-ttu-id="36f8e-150">net start mbamagent</span><span class="sxs-lookup"><span data-stu-id="36f8e-150">net start mbamagent</span></span>**

8. <span data-ttu-id="36f8e-151">当计算机重新启动，并且 BIOS 提示您接受 TPM 更改时，请接受更改。</span><span class="sxs-lookup"><span data-stu-id="36f8e-151">When the computers restarts, and the BIOS prompts you to accept a TPM change, accept the change.</span></span>

9. <span data-ttu-id="36f8e-152">在 Windows 客户端操作系统成像过程中，当你准备好开始加密时，请重新启动 MBAM 代理服务，并通过以管理员身份运行命令提示符并键入以下命令来将 "开始" 设置为 "**自动**"：</span><span class="sxs-lookup"><span data-stu-id="36f8e-152">During the Windows client operating system imaging process, when you are ready to start encryption, restart the MBAM agent service, and set start to **automatic** by running a command prompt as an administrator and typing the following commands:</span></span>

   **<span data-ttu-id="36f8e-153">sc config mbamagent start = auto</span><span class="sxs-lookup"><span data-stu-id="36f8e-153">sc config mbamagent start= auto</span></span>**

   **<span data-ttu-id="36f8e-154">net start mbamagent</span><span class="sxs-lookup"><span data-stu-id="36f8e-154">net start mbamagent</span></span>**

10. <span data-ttu-id="36f8e-155">通过运行 Regedit 并转到 HKLM\\SOFTWARE\\Microsoft 注册表项来删除旁路注册表值。</span><span class="sxs-lookup"><span data-stu-id="36f8e-155">Remove the bypass registry values by running Regedit and going to the HKLM\\SOFTWARE\\Microsoft registry entry.</span></span> <span data-ttu-id="36f8e-156">若要删除**MBAM**节点，请右键单击该节点，然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="36f8e-156">To delete the **MBAM** node, right-click the node and click **Delete**.</span></span>

## <span data-ttu-id="36f8e-157">相关主题</span><span class="sxs-lookup"><span data-stu-id="36f8e-157">Related topics</span></span>


[<span data-ttu-id="36f8e-158">部署 MBAM 2.0 客户端</span><span class="sxs-lookup"><span data-stu-id="36f8e-158">Deploying the MBAM 2.0 Client</span></span>](deploying-the-mbam-20-client-mbam-2.md)









