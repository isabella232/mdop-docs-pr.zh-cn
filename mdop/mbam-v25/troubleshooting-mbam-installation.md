---
title: MBAM 2.5 安装问题疑难解答
description: 介绍如何对 MBAM 2.5 安装问题进行故障排除。
author: Deland-Han
ms.reviewer: dcscontentpm
manager: dansimp
ms.author: delhan
ms.sitesec: library
ms.prod: w10
ms.date: 09/16/2019
ms.openlocfilehash: ed56a87496e09601c44028b7f948eda39143e8c0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798152"
---
# <span data-ttu-id="df5a1-103">MBAM 2.5 安装问题疑难解答</span><span class="sxs-lookup"><span data-stu-id="df5a1-103">Troubleshooting MBAM 2.5 installation problems</span></span>

<span data-ttu-id="df5a1-104">本文介绍如何在独立配置中对 Microsoft BitLocker 管理和监视（MBAM）2.5 安装问题进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="df5a1-104">This article introduces how to troubleshoot Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 installation issues in a standalone configuration.</span></span>

## <span data-ttu-id="df5a1-105">引用 MBAM 日志文件以进行疑难解答</span><span class="sxs-lookup"><span data-stu-id="df5a1-105">Referring MBAM log files for troubleshooting</span></span>

<span data-ttu-id="df5a1-106">MBAM 包括服务器安装、客户端安装和事件的日志记录。</span><span class="sxs-lookup"><span data-stu-id="df5a1-106">MBAM includes logging for server installation, client installation, and events.</span></span> <span data-ttu-id="df5a1-107">应参考此日志记录进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="df5a1-107">This logging should be referred to for troubleshooting.</span></span> 
 
### <span data-ttu-id="df5a1-108">MBAM 服务器安装日志文件</span><span class="sxs-lookup"><span data-stu-id="df5a1-108">MBAM server installation log files</span></span>

<span data-ttu-id="df5a1-109">MBAM 安装期间，在用户的% temp% 文件夹中，MBAMServerSetup.exe 会生成以下日志文件：</span><span class="sxs-lookup"><span data-stu-id="df5a1-109">MBAMServerSetup.exe generates the following log files in the user’s %temp% folder during MBAM installation:</span></span><br /> **<span data-ttu-id="df5a1-110">Microsoft_BitLocker_Administration_and_Monitoring_<14 号> .log</span><span class="sxs-lookup"><span data-stu-id="df5a1-110">Microsoft_BitLocker_Administration_and_Monitoring_<14 numbers>.log</span></span>**

<span data-ttu-id="df5a1-111">MBAMServerSetup.exe 记录 MBAM 安装和 MBAM 服务器功能安装期间所执行的操作：</span><span class="sxs-lookup"><span data-stu-id="df5a1-111">MBAMServerSetup.exe logs the actions that were taken during MBAM setup and MBAM server feature installation:</span></span><br /> **<span data-ttu-id="df5a1-112">Microsoft_BitLocker_Administration_and_Monitoring_<14_numbers # C1_0_MBAMServer.msi .log</span><span class="sxs-lookup"><span data-stu-id="df5a1-112">Microsoft_BitLocker_Administration_and_Monitoring_<14_numbers>_0_MBAMServer.msi.log</span></span>**

<span data-ttu-id="df5a1-113">MBAMServerSetup.exe 记录安装期间所执行的其他操作。</span><span class="sxs-lookup"><span data-stu-id="df5a1-113">MBAMServerSetup.exe logs additional actions that were taken during installation.</span></span>

### <span data-ttu-id="df5a1-114">MBAM 客户端安装日志文件</span><span class="sxs-lookup"><span data-stu-id="df5a1-114">MBAM client installation log file</span></span>

<span data-ttu-id="df5a1-115">客户端安装将记录在% temp% 文件夹（或自定义位置，具体取决于客户端的安装方式）中的以下日志文件中：</span><span class="sxs-lookup"><span data-stu-id="df5a1-115">The client installation is recorded in the following log file in the %temp% folder (or a custom location, depending on how the client was installed):</span></span> <br />**<span data-ttu-id="df5a1-116">MSI \<five random characters\> 日志</span><span class="sxs-lookup"><span data-stu-id="df5a1-116">MSI\<five random characters\>.log</span></span>**

<span data-ttu-id="df5a1-117">此日志包含在 MBAM 客户端安装期间执行的操作。</span><span class="sxs-lookup"><span data-stu-id="df5a1-117">This log contains the actions that are taken during MBAM client installation.</span></span>
 
### <span data-ttu-id="df5a1-118">MBAM 客户端事件-日志记录频道</span><span class="sxs-lookup"><span data-stu-id="df5a1-118">MBAM client event-logging channel</span></span>

<span data-ttu-id="df5a1-119">MBAM 具有单独的事件日志记录通道。</span><span class="sxs-lookup"><span data-stu-id="df5a1-119">MBAM has separate event-logging channels.</span></span> <span data-ttu-id="df5a1-120">"管理"、"分析" 和 "操作日志" 文件位于 "**应用程序和服务日志**"  >  **Microsoft**  >  **Windows**  >  **MBAM**下的 "事件查看器" 中。</span><span class="sxs-lookup"><span data-stu-id="df5a1-120">The Admin, Analytical, and Operational log files are located in Event Viewer, under **Application and Services Logs** > **Microsoft** > **Windows** > **MBAM**.</span></span>

<span data-ttu-id="df5a1-121">下表提供了每个事件日志的简要说明。</span><span class="sxs-lookup"><span data-stu-id="df5a1-121">The following table provides a brief description of each event log.</span></span>
 
|<span data-ttu-id="df5a1-122">事件日志</span><span class="sxs-lookup"><span data-stu-id="df5a1-122">Event log</span></span>| <span data-ttu-id="df5a1-123">描述</span><span class="sxs-lookup"><span data-stu-id="df5a1-123">Description</span></span>|
|----------|-------|
|<span data-ttu-id="df5a1-124">Microsoft-Windows-MBAM/Admin</span><span class="sxs-lookup"><span data-stu-id="df5a1-124">Microsoft-Windows-MBAM/Admin</span></span>|  <span data-ttu-id="df5a1-125">包含错误消息</span><span class="sxs-lookup"><span data-stu-id="df5a1-125">Contains error messages</span></span>|
|<span data-ttu-id="df5a1-126">Microsoft-Windows-MBAM/分析</span><span class="sxs-lookup"><span data-stu-id="df5a1-126">Microsoft-Windows-MBAM/Analytic</span></span>|   <span data-ttu-id="df5a1-127">包含高级日志记录信息</span><span class="sxs-lookup"><span data-stu-id="df5a1-127">Contains advanced logging information</span></span>|
|<span data-ttu-id="df5a1-128">Microsoft-Windows-MBAM/运营</span><span class="sxs-lookup"><span data-stu-id="df5a1-128">Microsoft-Windows-MBAM/Operational</span></span>|    <span data-ttu-id="df5a1-129">包含成功消息</span><span class="sxs-lookup"><span data-stu-id="df5a1-129">Contains success messages</span></span>|

### <span data-ttu-id="df5a1-130">MBAM 服务器事件-日志记录频道</span><span class="sxs-lookup"><span data-stu-id="df5a1-130">MBAM server event-logging channel</span></span>

<span data-ttu-id="df5a1-131">日志文件位于 "**应用程序和服务日志**"  >  **Microsoft**  >  **Windows**  >  **MBAM**下的 "事件查看器" 中。</span><span class="sxs-lookup"><span data-stu-id="df5a1-131">The log files are located in Event Viewer, under **Application and Services Logs** > **Microsoft** > **Windows** > **MBAM**.</span></span> <span data-ttu-id="df5a1-132">下表列出了在 MBAM 2.5 中引入的服务器事件日志：</span><span class="sxs-lookup"><span data-stu-id="df5a1-132">The following table includes server event logs that were introduced in MBAM 2.5:</span></span>

|<span data-ttu-id="df5a1-133">事件日志</span><span class="sxs-lookup"><span data-stu-id="df5a1-133">Event log</span></span>| <span data-ttu-id="df5a1-134">描述</span><span class="sxs-lookup"><span data-stu-id="df5a1-134">Description</span></span>|
|--------|-------------|
|<span data-ttu-id="df5a1-135">Microsoft-Windows-MBAM/Admin</span><span class="sxs-lookup"><span data-stu-id="df5a1-135">Microsoft-Windows-MBAM/Admin</span></span>|  <span data-ttu-id="df5a1-136">包含错误消息</span><span class="sxs-lookup"><span data-stu-id="df5a1-136">Contains error messages</span></span>|
|<span data-ttu-id="df5a1-137">Microsoft-Windows-MBAM/分析</span><span class="sxs-lookup"><span data-stu-id="df5a1-137">Microsoft-Windows-MBAM/Analytic</span></span>|   <span data-ttu-id="df5a1-138">包含高级日志记录信息</span><span class="sxs-lookup"><span data-stu-id="df5a1-138">Contains advanced logging information</span></span>|
|<span data-ttu-id="df5a1-139">Microsoft-Windows-MBAM/运营</span><span class="sxs-lookup"><span data-stu-id="df5a1-139">Microsoft-Windows-MBAM/Operational</span></span>|    <span data-ttu-id="df5a1-140">包含成功消息</span><span class="sxs-lookup"><span data-stu-id="df5a1-140">Contains success messages</span></span>|

### <span data-ttu-id="df5a1-141">MBAM web 服务日志</span><span class="sxs-lookup"><span data-stu-id="df5a1-141">MBAM web service logs</span></span>

<span data-ttu-id="df5a1-142">每个 MBAM web 服务日志将日志记录信息写入 SVCLOG 文件。</span><span class="sxs-lookup"><span data-stu-id="df5a1-142">Each MBAM web service log writes logging information to an SVCLOG file.</span></span> <span data-ttu-id="df5a1-143">默认情况下，每个 web 服务在 C:\inetpub\Microsoft BitLocker Management Solution\Logs 文件夹中使用其名称的文件夹下写入跟踪文件。</span><span class="sxs-lookup"><span data-stu-id="df5a1-143">By default, each web service writes the trace file under a folder that uses its name in the C:\inetpub\Microsoft BitLocker Management Solution\Logs folder.</span></span>

<span data-ttu-id="df5a1-144">你可以使用服务跟踪查看器工具（Microsoft Visual Studio 的一部分）查看 svclog 跟踪。</span><span class="sxs-lookup"><span data-stu-id="df5a1-144">You can use the service trace viewer tool (part of Microsoft Visual Studio) to review the svclog traces.</span></span>

## <span data-ttu-id="df5a1-145">加密和报告问题疑难解答</span><span class="sxs-lookup"><span data-stu-id="df5a1-145">Troubleshooting encryption and reporting issues</span></span>

<span data-ttu-id="df5a1-146">本部分包含服务器功能、客户端功能、配置设置和已知问题的疑难解答信息：</span><span class="sxs-lookup"><span data-stu-id="df5a1-146">This section contains troubleshooting information for server functionality, client functionality, configuration settings, and known issues:</span></span>
 
### <span data-ttu-id="df5a1-147">MBAM 客户端安装，组策略设置</span><span class="sxs-lookup"><span data-stu-id="df5a1-147">MBAM client installation, Group Policy settings</span></span>

<span data-ttu-id="df5a1-148">确定客户端计算机上是否已安装 MBAM 代理。</span><span class="sxs-lookup"><span data-stu-id="df5a1-148">Determine whether the MBAM agent is installed on the client computer.</span></span> <span data-ttu-id="df5a1-149">安装 MBAM 时，它将创建一个名为 "BitLocker 管理客户端服务" 的服务。</span><span class="sxs-lookup"><span data-stu-id="df5a1-149">When MBAM is installed, it creates a service that is named BitLocker Management Client Service.</span></span> <span data-ttu-id="df5a1-150">此服务配置为自动启动。</span><span class="sxs-lookup"><span data-stu-id="df5a1-150">This service is configured to start automatically.</span></span> <span data-ttu-id="df5a1-151">确定服务是否正在运行。</span><span class="sxs-lookup"><span data-stu-id="df5a1-151">Determine whether the service is running.</span></span>

<span data-ttu-id="df5a1-152">请确保在客户端计算机上应用了 MBAM 组策略设置。</span><span class="sxs-lookup"><span data-stu-id="df5a1-152">Make sure that MBAM Group Policy settings are applied on the client computer.</span></span> <span data-ttu-id="df5a1-153">如果客户端计算机上应用了组策略设置，则会创建以下注册表子项： **HKEY_LOCAL_MACHINE \software\policies\microsoft\fve\mdopbitlockermanagement**</span><span class="sxs-lookup"><span data-stu-id="df5a1-153">The following registry subkey is created if the Group Policy settings were applied on the client computer: **HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement**</span></span>

<span data-ttu-id="df5a1-154">验证此项是否存在，并使用每个组策略设置的值进行填充。</span><span class="sxs-lookup"><span data-stu-id="df5a1-154">Verify that this key exists and is populated by using values per Group Policy settings.</span></span>

### <span data-ttu-id="df5a1-155">初始延迟期间的 MBAM 代理</span><span class="sxs-lookup"><span data-stu-id="df5a1-155">MBAM Agent in the initial delay period</span></span>

<span data-ttu-id="df5a1-156">MBAM 客户端在安装后将不会立即启动操作。</span><span class="sxs-lookup"><span data-stu-id="df5a1-156">The MBAM client doesn't start the operation immediately after installation.</span></span> <span data-ttu-id="df5a1-157">在 MBAM 代理启动其操作之前，有1至18分钟的初始延迟是随机延迟。</span><span class="sxs-lookup"><span data-stu-id="df5a1-157">There is an initial random delay of 1–18 minutes before the MBAM Agent starts its operation.</span></span> <span data-ttu-id="df5a1-158">除了初始延迟，还存在至少90分钟的延迟。</span><span class="sxs-lookup"><span data-stu-id="df5a1-158">In addition to the initial delay, there is a delay of at least 90 minutes.</span></span> <span data-ttu-id="df5a1-159">（延迟取决于为检查客户端状态的频率配置的组策略设置。）因此，客户端启动操作前的总延迟是*随机启动延迟*  +  *客户端检查频率延迟*。</span><span class="sxs-lookup"><span data-stu-id="df5a1-159">(The delay depends on the Group Policy settings that are configured for the frequency of checking the client status.) Therefore, the total delay before a client starts operation is *random startup delay* + *client checking frequency delay*.</span></span>

<span data-ttu-id="df5a1-160">如果 "操作" 和 "管理员" 事件日志为空，则客户端尚未启动操作，并且处于前面提到的延迟期间。</span><span class="sxs-lookup"><span data-stu-id="df5a1-160">If the Operational and Admin event logs are blank, the client has not started the operation yet and is in the delay period that was mentioned earlier.</span></span> <span data-ttu-id="df5a1-161">如果想要绕过延迟，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="df5a1-161">If you want to bypass the delay, follow these steps:</span></span>
 
1. <span data-ttu-id="df5a1-162">停止 BitLocker 管理客户端服务服务。</span><span class="sxs-lookup"><span data-stu-id="df5a1-162">Stop the BitLocker Management Client Service service.</span></span>

2. <span data-ttu-id="df5a1-163">在**HKEY_LOCAL_MACHINE \software\microsoft\mbam**注册表子项下，创建**NoStartupDelay**注册表值，将其类型设置为 " **REG_DWORD**"，然后将其值设置为**1**。</span><span class="sxs-lookup"><span data-stu-id="df5a1-163">Under the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MBAM** registry subkey, create the **NoStartupDelay** registry value, set its type to **REG_DWORD**, and then set its value to **1**.</span></span>

3. <span data-ttu-id="df5a1-164">在 " **HKEY_LOCAL_MACHINE \software\policies\microsoft\fve\mdopbitlockermanagement**" 下，将 " **ClientWakeupFrequency** " 和 " **StatusReportingFrequency** " 值设置为**1**。</span><span class="sxs-lookup"><span data-stu-id="df5a1-164">Under **HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement**, set the **ClientWakeupFrequency** and **StatusReportingFrequency** values to **1**.</span></span> <span data-ttu-id="df5a1-165">当组策略更新位于计算机上后，这些值将还原为其原始设置。</span><span class="sxs-lookup"><span data-stu-id="df5a1-165">These values will revert to their original settings after Group Policy updates are on the computer.</span></span>

4. <span data-ttu-id="df5a1-166">启动 BitLocker 管理客户端服务服务。</span><span class="sxs-lookup"><span data-stu-id="df5a1-166">Start the BitLocker Management Client Service service.</span></span>

<span data-ttu-id="df5a1-167">服务启动后，如果您在计算机本地登录，但没有错误，您应该收到一分钟内加密计算机的请求。</span><span class="sxs-lookup"><span data-stu-id="df5a1-167">After the service starts, if you log in locally on the computer and there are no errors, you should receive a request to encrypt the computer within one minute.</span></span> <span data-ttu-id="df5a1-168">如果您没有收到请求，您应该查看 MBAM 管理员日志中是否有任何错误条目。</span><span class="sxs-lookup"><span data-stu-id="df5a1-168">If you do not receive a request, you should review the MBAM Admin logs for any error entries.</span></span>

### <span data-ttu-id="df5a1-169">计算机没有 TPM 设备，或者 BIOS 中未启用 TPM 设备</span><span class="sxs-lookup"><span data-stu-id="df5a1-169">Computer does not have a TPM device, or the TPM device is not enabled in the BIOS</span></span>

<span data-ttu-id="df5a1-170">查看 MBAM 管理员事件日志。</span><span class="sxs-lookup"><span data-stu-id="df5a1-170">Review the MBAM Admin event log.</span></span> <span data-ttu-id="df5a1-171">你将在 MBAM 管理事件日志中看到类似于以下内容的事件条目：</span><span class="sxs-lookup"><span data-stu-id="df5a1-171">You will see an event entry that resembles the following in the MBAM Admin event log:</span></span>

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          8/3/2013 12:31:10 PM
    Event ID:      9
    Task Category: None
    Level:         Error
    Keywords:      
    User:          SYSTEM
    Computer:      Mbamclient.contoso.com
    Description:
    The TPM hardware is missing.
    TPM is needed to encrypt the operating system drive with any TPM protector.

<span data-ttu-id="df5a1-172">打开 TPM 管理（tpm），并检查计算机是否具有 TPM 设备。</span><span class="sxs-lookup"><span data-stu-id="df5a1-172">Open TPM Management (tpm.msc), and check whether the computer has a TPM device.</span></span> <span data-ttu-id="df5a1-173">如果 tpm 未显示设备，请打开 "设备管理器" （devmgmt），然后在 "安全设备" 下检查受信任的平台模块。</span><span class="sxs-lookup"><span data-stu-id="df5a1-173">If tpm.msc does not show a device, open Device Manager (devmgmt.msc), and check for a Trusted Platform Module under Security Devices.</span></span> <span data-ttu-id="df5a1-174">如果你看不到受信任的平台模块设备，则可能是由于以下原因之一所示：</span><span class="sxs-lookup"><span data-stu-id="df5a1-174">If you do not see a Trusted Platform Module device, this might be true for one of the following reasons:</span></span>

* <span data-ttu-id="df5a1-175">您的系统没有受信任的平台模块（TPM/Security）设备。</span><span class="sxs-lookup"><span data-stu-id="df5a1-175">Your system doesn't have a Trusted Platform Module (TPM/Security) device.</span></span>

* <span data-ttu-id="df5a1-176">TPM 设备在 BIOS 中处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="df5a1-176">The TPM device is disabled in the BIOS.</span></span>

* <span data-ttu-id="df5a1-177">BIOS 中已启用 TPM 设备，但在 BIOS 中禁用从操作系统设置对 TPM 设备进行管理。</span><span class="sxs-lookup"><span data-stu-id="df5a1-177">TPM Device is enabled in the BIOS, but management of the TPM device from the operating system setting is disabled in the BIOS.</span></span>

* <span data-ttu-id="df5a1-178">你没有为 TPM 设备使用 Microsoft 驱动程序。</span><span class="sxs-lookup"><span data-stu-id="df5a1-178">You aren't using a Microsoft driver for the TPM device.</span></span> <span data-ttu-id="df5a1-179">查看 "设备管理器" 中列出的设备以识别 Microsoft TPM 设备驱动程序。</span><span class="sxs-lookup"><span data-stu-id="df5a1-179">Review the devices that are listed in device manager to identify the Microsoft TPM device driver.</span></span>

<span data-ttu-id="df5a1-180">如果 TPM 设备未使用 C:\Windows\System32\tpm.sys 驱动程序，你应该通过选择 C:\Windows\Inf\tpm.inf 文件来更新驱动程序。</span><span class="sxs-lookup"><span data-stu-id="df5a1-180">If the TPM device is not using the C:\Windows\System32\tpm.sys driver, you should update the driver by selecting the C:\Windows\Inf\tpm.inf file.</span></span>

### <span data-ttu-id="df5a1-181">计算机没有有效的系统分区</span><span class="sxs-lookup"><span data-stu-id="df5a1-181">Computer does not have a valid SYSTEM partition</span></span>

<span data-ttu-id="df5a1-182">查看 MBAM 管理员事件日志。</span><span class="sxs-lookup"><span data-stu-id="df5a1-182">Review the MBAM Admin event log.</span></span> <span data-ttu-id="df5a1-183">你将在 MBAM 管理事件日志中看到类似于以下内容的事件条目：</span><span class="sxs-lookup"><span data-stu-id="df5a1-183">You will see an event entry that resembles the following in the MBAM Admin event log:</span></span>

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          8/3/2013 4:13:37 AM
    Event ID:      8
    Task Category: None
    Level:         Error
    Keywords:      
    User:          SYSTEM
    Computer:      BITTESTVM.xtremelabs.com
    Description:
    The system volume is missing.
    SystemVolume is needed to encrypt the operating system drive.

<span data-ttu-id="df5a1-184">BitLocker 需要系统分区才能启用加密（[在 Windows 7 中为 BitLocker 驱动器加密：常见问题](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-7/ee449438(v=ws.10)?redirectedfrom=MSDN#bkmk_partitions)）。</span><span class="sxs-lookup"><span data-stu-id="df5a1-184">BitLocker requires a SYSTEM partition to enable encryption ([BitLocker Drive Encryption in Windows 7: Frequently Asked Questions](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-7/ee449438(v=ws.10)?redirectedfrom=MSDN#bkmk_partitions)).</span></span>

<span data-ttu-id="df5a1-185">MBAM 不会自动创建系统分区。</span><span class="sxs-lookup"><span data-stu-id="df5a1-185">MBAM doesn't create the system partition automatically.</span></span> <span data-ttu-id="df5a1-186">你可以使用 BitLocker 驱动器准备实用工具（bdehdcfg.exe）创建系统分区并移动所需的启动文件。</span><span class="sxs-lookup"><span data-stu-id="df5a1-186">You can use the BitLocker drive preparation utility (bdehdcfg.exe) to create the system partition and move the required startup files.</span></span>

<span data-ttu-id="df5a1-187">例如，你可以使用 **% windir% \system32\bdeHdCfg.exe 目标默认大小 300-** 在部署 MBAM 以加密驱动器之前，安静模式准备驱动器。</span><span class="sxs-lookup"><span data-stu-id="df5a1-187">For example, you can use the command **%windir%\system32\bdeHdCfg.exe -target default -size 300 –quiet** to prepare the drive silently before you deploy MBAM to encrypt the drives.</span></span> <span data-ttu-id="df5a1-188">这需要重启。</span><span class="sxs-lookup"><span data-stu-id="df5a1-188">This requires a restart.</span></span> <span data-ttu-id="df5a1-189">如果需要，还可以编写操作脚本。</span><span class="sxs-lookup"><span data-stu-id="df5a1-189">You can also script the action if this is required.</span></span> <span data-ttu-id="df5a1-190">以下文档介绍了 BitLocker 驱动器准备工具：</span><span class="sxs-lookup"><span data-stu-id="df5a1-190">The following document describes the BitLocker Drive Preparation Tool:</span></span>

[<span data-ttu-id="df5a1-191">BitLocker 驱动器准备工具说明</span><span class="sxs-lookup"><span data-stu-id="df5a1-191">Description of the BitLocker Drive Preparation Tool</span></span>](https://support.microsoft.com/help/933246)

### <span data-ttu-id="df5a1-192">驱动器未格式化为具有兼容的文件系统</span><span class="sxs-lookup"><span data-stu-id="df5a1-192">Drives are not formatted to have a compatible file system</span></span>

<span data-ttu-id="df5a1-193">[有关 BitLocker 的文件系统要求](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-7/ee449438(v=ws.10)?redirectedfrom=MSDN#bkmk_hsrequirements)，请参阅 TechNet 文章。</span><span class="sxs-lookup"><span data-stu-id="df5a1-193">See the [TechNet article for file system requirements for BitLocker](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-7/ee449438(v=ws.10)?redirectedfrom=MSDN#bkmk_hsrequirements).</span></span>

### <span data-ttu-id="df5a1-194">组策略冲突</span><span class="sxs-lookup"><span data-stu-id="df5a1-194">Group Policy conflict</span></span>

<span data-ttu-id="df5a1-195">你将在 MBAM 管理事件日志中看到类似于以下内容的事件条目：</span><span class="sxs-lookup"><span data-stu-id="df5a1-195">You will see an event entry that resembles the following in the MBAM Admin event log:</span></span>

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          7/25/2013 9:27:58 PM
    Event ID:      22
    Task Category: None
    Level:         Error
    Keywords:      
    User:          SYSTEM
    Computer:      Mbamclient.contoso.com
    Description:
    Detected Fixed Data Drive volume encryption policies conflict.
    Check BitLocker and MBAM policies related to FDD drive protectors.

<span data-ttu-id="df5a1-196">验证组策略设置，确保 MBAM 组策略设置中没有相冲突的设置。</span><span class="sxs-lookup"><span data-stu-id="df5a1-196">Verify your Group Policy settings to make sure that you do not have a conflicting setting among the MBAM Group Policy settings.</span></span>

<span data-ttu-id="df5a1-197">你应该使用 MDOP MBAM 模板而不是 BitLocker 驱动器加密模板来配置组策略。</span><span class="sxs-lookup"><span data-stu-id="df5a1-197">You should configure Group Policy by using the MDOP MBAM template and not the BitLocker Drive Encryption template.</span></span>

<span data-ttu-id="df5a1-198">例如：</span><span class="sxs-lookup"><span data-stu-id="df5a1-198">For example:</span></span>

<span data-ttu-id="df5a1-199">在 "操作系统驱动器加密设置" 下，选择 "TPM" 作为保护器，并选择 "**允许增强的 pin 来启动**"。</span><span class="sxs-lookup"><span data-stu-id="df5a1-199">Under Operating system drive encryption settings, you selected TPM as the protector, and you also selected **Allow enhanced PINs for startup**.</span></span> <span data-ttu-id="df5a1-200">这些是冲突设置，因为仅 TPM 保护不需要 PIN 码。</span><span class="sxs-lookup"><span data-stu-id="df5a1-200">These are conflicting settings because TPM-only protection doesn't require a PIN.</span></span> <span data-ttu-id="df5a1-201">因此，您应该禁用 "增强引脚" 设置。</span><span class="sxs-lookup"><span data-stu-id="df5a1-201">Therefore, you should disable the enhanced PINs setting.</span></span>

### <span data-ttu-id="df5a1-202">用户可能已请求例外</span><span class="sxs-lookup"><span data-stu-id="df5a1-202">User may have requested an exemption</span></span>

<span data-ttu-id="df5a1-203">如果启用了计算机配置 \ 管理模板 \Windows Components\MDOP MBAM （BitLocker Management） \Client Management\Configure 用户豁免策略组策略设置，则会向用户提供请求豁免的选项。</span><span class="sxs-lookup"><span data-stu-id="df5a1-203">If you enabled the Computer Configuration\Administrative Templates\Windows Components\MDOP MBAM (BitLocker Management)\Client Management\Configure user exemption policy Group Policy setting, users will be offered the option to request an exemption.</span></span>

<span data-ttu-id="df5a1-204">默认情况下，如果用户请求豁免，则豁免将在7天内有效，用户在此期间将不会收到用于加密的提示。</span><span class="sxs-lookup"><span data-stu-id="df5a1-204">By default, if the user requests an exemption, the exemption will be valid for 7 days, and the user will not receive prompts to encrypt during this period.</span></span> <span data-ttu-id="df5a1-205">（在策略配置期间，可以增加或减少默认值。）在免除期限结束后，系统会提示用户进行加密。</span><span class="sxs-lookup"><span data-stu-id="df5a1-205">(The default value can be increased or decreased during policy configuration.) After the exemption period is over, the user is prompted to encrypt.</span></span>

<span data-ttu-id="df5a1-206">当计算机处于用户豁免下时，你将在 MBAM Admin 事件日志中看到以下条目：</span><span class="sxs-lookup"><span data-stu-id="df5a1-206">You will see the following entry in the MBAM Admin event log when a computer is under user exemption:</span></span>

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          8/3/2013 3:06:40 PM
    Event ID:      13
    Task Category: None
    Level:         Warning
    Keywords:      
    User:          SYSTEM
    Computer:      MBAMCLIENT.contoso.com
    Description:
    The user is exempt from encryption.

<span data-ttu-id="df5a1-207">如果要为计算机手动替代用户豁免，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="df5a1-207">If you want to manually override user exemption for a computer, follow these steps:</span></span>
 
1. <span data-ttu-id="df5a1-208">在以下注册表子项下将 AllowUserExemption 值设置为**0** ：</span><span class="sxs-lookup"><span data-stu-id="df5a1-208">Set the AllowUserExemption value to **0** under the following registry subkey:</span></span> <br />
**<span data-ttu-id="df5a1-209">HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement</span><span class="sxs-lookup"><span data-stu-id="df5a1-209">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement</span></span>**

2. <span data-ttu-id="df5a1-210">删除以下注册表子项下除 " **AgentVersion**"、" **EncodedComputerName**" 和 "**已安装**" 之外的所有注册表值：</span><span class="sxs-lookup"><span data-stu-id="df5a1-210">Delete all the registry values under the following registry subkey except for **AgentVersion**, **EncodedComputerName**, and **Installed**:</span></span><br />
**<span data-ttu-id="df5a1-211">HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\MBAM</span><span class="sxs-lookup"><span data-stu-id="df5a1-211">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MBAM</span></span>**

    <span data-ttu-id="df5a1-212">**注意**必须重新启动 MBAM 代理才能使更改生效。</span><span class="sxs-lookup"><span data-stu-id="df5a1-212">**Note** You must restart the MBAM agent for the changes to take effect.</span></span>

<span data-ttu-id="df5a1-213">请注意，在将组策略应用到计算机之后，这些值可能会还原为其原始设置。</span><span class="sxs-lookup"><span data-stu-id="df5a1-213">Be aware that after you apply Group Policy to the computer, these values may revert to their original settings.</span></span>

### <span data-ttu-id="df5a1-214">WMI 问题</span><span class="sxs-lookup"><span data-stu-id="df5a1-214">WMI issue</span></span>

<span data-ttu-id="df5a1-215">MBAM 使用 win32_encryptablevolume 类的方法来管理 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="df5a1-215">MBAM uses methods of the win32_encryptablevolume class to manage BitLocker.</span></span> <span data-ttu-id="df5a1-216">如果此模块未注册或已损坏，MBAM 客户端将无法正常运行，你将在 MBAM 管理员事件日志中看到以下事件条目：</span><span class="sxs-lookup"><span data-stu-id="df5a1-216">If this module is unregistered or corrupted, the MBAM client will not operate correctly, and you will see the following event entry in the MBAM Admin event log:</span></span>

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          7/27/2013 11:18:51 PM
    Event ID:      4
    Task Category: None
    Level:         Error
    Keywords:      
    User:          SYSTEM
    Computer:      BITTEST.xtremelabs.com
    Description:
    An error occurred while sending encryption status data.
    Error code:
    0x80041016 
    Details:
    NULL

<span data-ttu-id="df5a1-217">此外，你可能会注意到恢复和硬件策略不适用于错误代码0x8007007e。</span><span class="sxs-lookup"><span data-stu-id="df5a1-217">Additionally, you may notice that the Recovery and Hardware policies do not apply with Error Code 0x8007007e.</span></span> <span data-ttu-id="df5a1-218">这将转换为 "找不到指定的模块"。</span><span class="sxs-lookup"><span data-stu-id="df5a1-218">This translates to "The specified module could not be found."</span></span>

<span data-ttu-id="df5a1-219">若要解决此问题，应使用以下命令重新注册**win32_encryptablevolume**类：</span><span class="sxs-lookup"><span data-stu-id="df5a1-219">To resolve this issue, you should reregister the **win32_encryptablevolume** class by using the following command:</span></span>

```cmd
mofcomp c:\Windows\System32\wbem\win32_encryptablevolume.mof
```

## <span data-ttu-id="df5a1-220">MBAM 代理通信问题疑难解答</span><span class="sxs-lookup"><span data-stu-id="df5a1-220">Troubleshooting MBAM Agent communication issues</span></span>

<span data-ttu-id="df5a1-221">本部分包含与 MBAM 代理通信相关的以下问题的疑难解答信息：</span><span class="sxs-lookup"><span data-stu-id="df5a1-221">This section contains troubleshooting information for the following issues that are related to MBAM agent communication:</span></span>

### <span data-ttu-id="df5a1-222">不正确的 MBAM 服务 URL</span><span class="sxs-lookup"><span data-stu-id="df5a1-222">Incorrect MBAM service URL</span></span>

<span data-ttu-id="df5a1-223">如果 MBAM 合规性状态服务或恢复和硬件服务的值不正确，你将在客户端计算机上的 MBAM 管理员事件日志中看到类似于以下内容的事件条目：</span><span class="sxs-lookup"><span data-stu-id="df5a1-223">If the value of MBAM Compliance Status Service or Recovery and Hardware Service is incorrect, you'll see an event entry that resembles the following in the MBAM Admin event log on the client computer:</span></span>

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          8/3/2013 4:13:36 PM
    Event ID:      4
    Task Category: None
    Level:         Error
    Keywords:     
    User:          SYSTEM
    Computer:      Mbamclient.contoso.com
    Description:
    An error occurred while sending encryption status data.
    Error code:
    0x803d0010
    Details:
    The remote endpoint was not reachable.

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          8/3/2013 4:13:33 PM
    Event ID:      18
    Task Category: None
    Level:         Error
    Keywords:     
    User:          SYSTEM
    Computer:      Mbamclient.contoso.com
    Description:
    Unable to connect to the MBAM Recovery and Hardware service.
    Error code:
    0x803d0010
    Details:
    The remote endpoint was not reachable.

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          8/3/2013 4:20:32 PM
    Event ID:      4
    Task Category: None
    Level:         Error
    Keywords:     
    User:          SYSTEM
    Computer:      Mbamclient.contoso.com
    Description:
    An error occurred while sending encryption status data.
    Error code:
    0x803d0020
    Details:
    The endpoint address URL is invalid.

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          8/3/2013 4:20:32 PM
    Event ID:      18
    Task Category: None
    Level:         Error
    Keywords:     
    User:          SYSTEM
    Computer:      Mbamclient.contoso.com
    Description:
    Unable to connect to the MBAM Recovery and Hardware service.
    Error code:
    0x803d0020
    Details:
    The endpoint address URL is invalid.

<span data-ttu-id="df5a1-224">在客户端计算机上的以下注册表子项下验证**KeyRecoveryServiceEndPoint**和**StatusReportingServiceEndpoint**的值：</span><span class="sxs-lookup"><span data-stu-id="df5a1-224">Verify the values of **KeyRecoveryServiceEndPoint** and **StatusReportingServiceEndpoint** under the following registry subkey on the client computer:</span></span> <br />
**<span data-ttu-id="df5a1-225">HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement</span><span class="sxs-lookup"><span data-stu-id="df5a1-225">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement</span></span>**

<span data-ttu-id="df5a1-226">默认情况下，KeyRecoveryServiceEndPoint （MBAM 恢复和硬件服务终结点）的 URL 采用以下格式：</span><span class="sxs-lookup"><span data-stu-id="df5a1-226">By default, the URL for KeyRecoveryServiceEndPoint (MBAM Recovery and Hardware service endpoint) is in the following format:</span></span> <br />
**<span data-ttu-id="df5a1-227">http:// \<servername\> ： \<port\> /MBAMRecoveryAndHardwareService/CoreService.svc</span><span class="sxs-lookup"><span data-stu-id="df5a1-227">http://\<servername\>:\<port\>/MBAMRecoveryAndHardwareService/CoreService.svc</span></span>**

<span data-ttu-id="df5a1-228">默认情况下，StatusReportingServiceEndpoint （MBAM 状态报告服务终结点）的 URL 采用以下格式：</span><span class="sxs-lookup"><span data-stu-id="df5a1-228">By default, the URL for StatusReportingServiceEndpoint (MBAM Status reporting service endpoint) is in the following format:</span></span><br />
**<span data-ttu-id="df5a1-229">http:// \<servername\> ： \<port\> /MBAMComplianceStatusService/StatusReportingService.svc</span><span class="sxs-lookup"><span data-stu-id="df5a1-229">http://\<servername\>:\<port\>/MBAMComplianceStatusService/StatusReportingService.svc</span></span>**

> [!Note]
> <span data-ttu-id="df5a1-230">URL 中不应有空格。</span><span class="sxs-lookup"><span data-stu-id="df5a1-230">There should be no spaces in the URL.</span></span>

<span data-ttu-id="df5a1-231">如果服务 URL 不正确，则应在以下组策略设置中更正服务 URL：</span><span class="sxs-lookup"><span data-stu-id="df5a1-231">If the service URL is incorrect, you should correct the service URL in the following Group Policy setting:</span></span>

<span data-ttu-id="df5a1-232">**计算机配置**  > **策略**  > **管理模板**  > **Windows 组件**  > **MDOP MBAM （BitLocker 管理）**  > **客户端管理**  > **配置 MBAM 服务**</span><span class="sxs-lookup"><span data-stu-id="df5a1-232">**Computer configuration** > **Policies** > **Administrative Templates** > **Windows Components** > **MDOP MBAM (BitLocker Management)** > **Client Management** > **Configure MBAM Services**</span></span>

### <span data-ttu-id="df5a1-233">影响 MBAM 管理服务器的连接问题</span><span class="sxs-lookup"><span data-stu-id="df5a1-233">Connectivity issue that affects the MBAM administration server</span></span>

<span data-ttu-id="df5a1-234">如果客户端代理和 MBAM 管理服务器之间存在连接问题，MBAM 代理将无法发布对数据库的任何更新。</span><span class="sxs-lookup"><span data-stu-id="df5a1-234">The MBAM agent will be unable to post any updates to the database if connectivity issues exist between the client agent and the MBAM administration server.</span></span> <span data-ttu-id="df5a1-235">在这种情况下，你将注意到客户端计算机上 MBAM 管理员事件日志中的连接失败条目：</span><span class="sxs-lookup"><span data-stu-id="df5a1-235">In this case, you will notice connectivity failure entries in the MBAM Admin event log on the client computer:</span></span>

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          29-04-2014 18:21:22
    Event ID:      2
    Task Category: None
    Level:         Error
    Keywords:     
    User:          SYSTEM
    Computer:      TESTLABS.CONTOSO.COM
    Description:
    An error occurred while applying MBAM policies.
    Volume ID:\\?\Volume{871c5858-2467-4d0b-8c83-d68af8ce10e5}\ 
    Error code:
    0x803D0010 
    Details:
    The remote endpoint was not reachable.
 
    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          29-04-2014 23:06:48
    Event ID:      2
    Task Category: None
    Level:         Error
    Keywords:     
    User:          SYSTEM
    Computer:      TESTLABS.CONTOSO.COM
    Description:
    An error occurred while applying MBAM policies.
    Volume ID:\\?\Volume{871c5858-2467-4d0b-8c83-d68af8ce10e5}\ 
    Error code:
    0x803D0006 
    Details:
    The operation did not complete within the time allotted.

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          02-09-2013 02:02:04
    Event ID:      18
    Task Category: None
    Level:         Error
    Keywords:     
    User:          SYSTEM
    Computer:      TESTLABS.CONTOSO.COM
    Description:
    Unable to connect to the MBAM Recovery and Hardware service.
    Error code:
    0x803D0010 
    Details:
    The remote endpoint was not reachable.

<span data-ttu-id="df5a1-236">基本检查：</span><span class="sxs-lookup"><span data-stu-id="df5a1-236">Basic checks:</span></span>

* <span data-ttu-id="df5a1-237">通过 ping MBAM 管理服务器的名称和 IP 验证基本连接。</span><span class="sxs-lookup"><span data-stu-id="df5a1-237">Verify basic connectivity by pinging the MBAM administration server by name and IP.</span></span> <span data-ttu-id="df5a1-238">检查你是否可以使用 telnet 或 portqry 连接到 MBAM 管理网站或服务端口。</span><span class="sxs-lookup"><span data-stu-id="df5a1-238">Check whether you can connect to the MBAM administration website or service port by using telnet or portqry.</span></span>

* <span data-ttu-id="df5a1-239">验证 IIS 服务正在 MBAM 管理和监视服务器上运行，并且 MBAM web 服务正在侦听在 MBAM 客户端计算机（）上配置的同一端口 `netstat –ano | find "portnumber"` 。</span><span class="sxs-lookup"><span data-stu-id="df5a1-239">Verify that the IIS service is running on the MBAM administration and monitoring server and that the MBAM web service is listening on the same port that is configured on the MBAM client computer (`netstat –ano | find "portnumber"`).</span></span>

* <span data-ttu-id="df5a1-240">验证为 MBAM 网站配置的端口号是否使用 IIS 管理器（inetmgr）。</span><span class="sxs-lookup"><span data-stu-id="df5a1-240">Verify that the port number that is configured for the MBAM website is using IIS Manager (inetmgr).</span></span> <span data-ttu-id="df5a1-241">请确保端口号与客户端正在其上侦听的端口号相同。</span><span class="sxs-lookup"><span data-stu-id="df5a1-241">Make sure that the port number is the same as the port number on which the client is listening.</span></span> <span data-ttu-id="df5a1-242">请确保端口号不会被其他应用程序共享。</span><span class="sxs-lookup"><span data-stu-id="df5a1-242">Make sure that the port number is not shared by another application.</span></span> <span data-ttu-id="df5a1-243">例如，服务器上的另一个应用程序不应使用同一端口。</span><span class="sxs-lookup"><span data-stu-id="df5a1-243">For example, another application on the server should not be using the same port.</span></span>

* <span data-ttu-id="df5a1-244">如果有防火墙，请确保该端口已在防火墙或代理服务器中打开。</span><span class="sxs-lookup"><span data-stu-id="df5a1-244">If there is a firewall, make sure that the port is open in the firewall or proxy server.</span></span>

* <span data-ttu-id="df5a1-245">如果客户端和服务器之间的通信是安全的，请确保使用有效的 SSL 证书。</span><span class="sxs-lookup"><span data-stu-id="df5a1-245">If the communication between client and server is secure, make sure that you are using a valid SSL certificate.</span></span>

* <span data-ttu-id="df5a1-246">验证 web 服务器与发送数据以用于插入的数据库服务器之间的网络连接。</span><span class="sxs-lookup"><span data-stu-id="df5a1-246">Verify network connectivity between the web server and the database server to which the data is sent for insertion.</span></span> <span data-ttu-id="df5a1-247">可以使用 ODBC 数据源管理器检查从 web 服务器到数据库服务器的数据库连接。</span><span class="sxs-lookup"><span data-stu-id="df5a1-247">You can check database connectivity from the web server to the database server by using ODBC Data Source Administrator.</span></span> <span data-ttu-id="df5a1-248">有关[连接到 Sql Server 数据库引擎的疑难解答](https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx)的详细信息，请访问详细的 sql server 连接故障排除信息。</span><span class="sxs-lookup"><span data-stu-id="df5a1-248">Detailed SQL Server connection troubleshooting information is available in [How to Troubleshoot Connecting to the SQL Server Database Engine](https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx).</span></span>

#### <span data-ttu-id="df5a1-249">解决连接问题</span><span class="sxs-lookup"><span data-stu-id="df5a1-249">Troubleshooting the connectivity issue</span></span>

<span data-ttu-id="df5a1-250">请确保在客户端上配置的服务 URL 正确无误。</span><span class="sxs-lookup"><span data-stu-id="df5a1-250">Make sure that the service URL that is configured on the client is correct.</span></span> <span data-ttu-id="df5a1-251">从注册表中复制 KeyRecoveryServiceEndPoint 的 URL 的值（**HKEY_LOCAL_MACHINE \software\policies\microsoft\fve\mdopbitlockermanagement**），然后在 Internet Explorer 中打开它。</span><span class="sxs-lookup"><span data-stu-id="df5a1-251">Copy the value of the URL for KeyRecoveryServiceEndPoint (**HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement**) from the registry, and open it in Internet Explorer.</span></span>

<span data-ttu-id="df5a1-252">同样，复制 StatusReportingServiceEndpoint （**HKEY_LOCAL_MACHINE \software\policies\microsoft\fve\mdopbitlockermanagement**）的 URL 的值，然后在 Internet Explorer 中将其打开。</span><span class="sxs-lookup"><span data-stu-id="df5a1-252">Similarly, copy the value of the URL for StatusReportingServiceEndpoint (**HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement**), and open it in Internet Explorer.</span></span>

> [!Note]
> <span data-ttu-id="df5a1-253">如果无法浏览客户端计算机的 URL，则应测试客户端与运行 IIS 的服务器之间的基本网络连接。</span><span class="sxs-lookup"><span data-stu-id="df5a1-253">If you cannot browse to the URL from the client computer, you should test basic network connectivity from the client to the server that is running IIS.</span></span> <span data-ttu-id="df5a1-254">请参阅上一节中的点1、2、3和4。</span><span class="sxs-lookup"><span data-stu-id="df5a1-254">See points 1, 2, 3, and 4 in the previous section.</span></span>

<span data-ttu-id="df5a1-255">此外，请查看管理和监视服务器上的应用程序日志，查看是否存在任何错误。</span><span class="sxs-lookup"><span data-stu-id="df5a1-255">Additionally, review the Application logs on the administration and monitoring server for any errors.</span></span>

<span data-ttu-id="df5a1-256">你可以在客户端和服务器之间进行并发网络跟踪，并查看跟踪以确定客户端代理和 MBAM 管理服务器之间连接失败的原因。</span><span class="sxs-lookup"><span data-stu-id="df5a1-256">You can make a concurrent network trace between the client and the server, and review the trace to determine the cause of connection failure between the client agent and the MBAM administration server.</span></span>

> [!Note]
> <span data-ttu-id="df5a1-257">如果您可以从客户端计算机浏览到服务 Url，并且 MBAM 管理事件日志中存在连接错误条目，这可能是由于管理服务器和数据库服务器之间的连接失败造成的。</span><span class="sxs-lookup"><span data-stu-id="df5a1-257">If you can browse to the service URLs from the client computer and there are connectivity error entries in the MBAM admin event logs, this might be because of a connectivity failure between the administration server and the database server.</span></span>

<span data-ttu-id="df5a1-258">如果您可以成功浏览这两个服务 Url，并且客户端与运行的服务器之间存在连接，则 IIS 正常工作。</span><span class="sxs-lookup"><span data-stu-id="df5a1-258">If you can successfully browse to both service URLs, and there is connectivity between the client and the server that is running, IIS is working.</span></span> <span data-ttu-id="df5a1-259">但是，在运行 IIS 的服务器和数据库服务器之间的通信中可能存在问题。</span><span class="sxs-lookup"><span data-stu-id="df5a1-259">However, there may be a problem in communication between the server that is running IIS and the database server.</span></span>

<span data-ttu-id="df5a1-260">由于网络问题或数据库连接字符串设置不正确，MBAM 服务可能无法连接到数据库服务器。</span><span class="sxs-lookup"><span data-stu-id="df5a1-260">The MBAM services may be unable to connect to the database server because of a network issue or an incorrect database connection string setting.</span></span> <span data-ttu-id="df5a1-261">查看管理和监视服务器上的应用程序日志。</span><span class="sxs-lookup"><span data-stu-id="df5a1-261">Review the Application logs on the administration and monitoring server.</span></span> <span data-ttu-id="df5a1-262">您可能会看到来自来源 ASP.NET 2.0.50727.0 的错误条目或警告，类似于以下日志条目：</span><span class="sxs-lookup"><span data-stu-id="df5a1-262">You might see errors entries or warnings from source ASP.NET 2.0.50727.0 that resemble the following log entry:</span></span>

    Log Name:      Application
    Source:        ASP.NET 2.0.50727.0
    Date:          7/11/2013 6:16:34 PM
    Event ID:      1310
    Task Category: Web Event
    Level:         Warning
    Keywords:      Classic
    User:          N/A
    Computer:      MBAM2-Admin.contoso.com
    Description:
    Event code: 100001
    Event message: SQL error occurred
    Event time: 7/11/2013 6:16:34 PM
    Event time (UTC): 7/11/2013 12:46:34 PM
    Event ID: 6615fb8eb9d54e778b933d5bb7ca91ed
    Event sequence: 2
    Event occurrence: 1
    Event detail code: 0 
    Application information:
        Application domain: /LM/W3SVC/2/ROOT/MBAMAdministrationService-1-130180202570338699
        Trust level: Full
        Application Virtual Path: /MBAMAdministrationService
        Application Path: C:\inetpub\Microsoft BitLocker Management Solution\Administration Service\
        Machine name: MBAM2-ADMIN 
    
    Process information:
        Process ID: 1940
        Process name: w3wp.exe
        Account name: NT AUTHORITY\NETWORK SERVICE 
    
    Exception information:
        Exception type: SqlException
        Exception message: A network-related or instance-specific error occurred while establishing a connection to SQL Server. The server was not found or was not accessible. Verify that the instance name is correct and that SQL Server is configured to allow remote connections. (provider: Named Pipes Provider, error: 40 - Could not open a connection to SQL Server) 
    
    Request information:
        Request URL: 
        Request path: 
        User host address: 
        User: 
        Is authenticated: False
        Authentication Type: 
        Thread account name: NT AUTHORITY\NETWORK SERVICE 
    
    Thread information:
        Thread ID: 7
        Thread account name: NT AUTHORITY\NETWORK SERVICE
        Is impersonating: False
        Stack trace:    at System.Data.SqlClient.SqlInternalConnection.OnError(SqlException exception, Boolean breakConnection)
       at System.Data.SqlClient.TdsParser.ThrowExceptionAndWarning(TdsParserStateObject stateObj)
       at System.Data.SqlClient.TdsParser.Connect(ServerInfo serverInfo, SqlInternalConnectionTds connHandler, Boolean ignoreSniOpenTimeout, Int64 timerExpire, Boolean encrypt, Boolean trustServerCert, Boolean integratedSecurity, SqlConnection owningObject)
       at System.Data.SqlClient.SqlInternalConnectionTds.AttemptOneLogin(ServerInfo serverInfo, String newPassword, Boolean ignoreSniOpenTimeout, Int64 timerExpire, SqlConnection owningObject)
       at System.Data.SqlClient.SqlInternalConnectionTds.LoginNoFailover(String host, String newPassword, Boolean redirectedUserInstance, SqlConnection owningObject, SqlConnectionString connectionOptions, Int64 timerStart)
       at System.Data.SqlClient.SqlInternalConnectionTds.OpenLoginEnlist(SqlConnection owningObject, SqlConnectionString connectionOptions, String newPassword, Boolean redirectedUserInstance)
       at System.Data.SqlClient.SqlInternalConnectionTds..ctor(DbConnectionPoolIdentity identity, SqlConnectionString connectionOptions, Object providerInfo, String newPassword, SqlConnection owningObject, Boolean redirectedUserInstance)
       at System.Data.SqlClient.SqlConnectionFactory.CreateConnection(DbConnectionOptions options, Object poolGroupProviderInfo, DbConnectionPool pool, DbConnection owningConnection)
       at System.Data.ProviderBase.DbConnectionFactory.CreatePooledConnection(DbConnection owningConnection, DbConnectionPool pool, DbConnectionOptions options)
       at System.Data.ProviderBase.DbConnectionPool.CreateObject(DbConnection owningObject)
       at System.Data.ProviderBase.DbConnectionPool.UserCreateRequest(DbConnection owningObject)
       at System.Data.ProviderBase.DbConnectionPool.GetConnection(DbConnection owningObject)
       at System.Data.ProviderBase.DbConnectionFactory.GetConnection(DbConnection owningConnection)
       at System.Data.ProviderBase.DbConnectionClosed.OpenConnection(DbConnection outerConnection, DbConnectionFactory connectionFactory)
       at System.Data.SqlClient.SqlConnection.Open()
       at System.Data.Linq.SqlClient.SqlConnectionManager.UseConnection(IConnectionUser user)
       at System.Data.Linq.SqlClient.SqlProvider.get_IsSqlCe()
       at System.Data.Linq.SqlClient.SqlProvider.InitializeProviderMode()
       at System.Data.Linq.SqlClient.SqlProvider.System.Data.Linq.Provider.IProvider.Execute(Expression query)
       at System.Data.Linq.DataContext.ExecuteMethodCall(Object instance, MethodInfo methodInfo, Object[] parameters)
       at Microsoft.Mbam.Server.ServiceCommon.KeyRecoveryModelDataContext.GetRecoveryKeyIds(String partialRecoveryKeyId, String reason)
       at Microsoft.Mbam.ApplicationSupportService.AdministrationService.GetRecoveryKeyIds(String partialRecoveryKeyId, String reasonCode)
    
    Custom event details:
        Application: MBAMAdministrationService
        Sql Server:
        Database: MBAM Recovery and Hardware
        Database: MBAM Compliance Status
        Sql ErrorCode: 5
        Error Message: A network-related or instance-specific error occurred while establishing a connection to SQL Server. The server was not found or was not accessible. Verify that the instance name is correct and that SQL Server is configured to allow remote connections. (provider: Named Pipes Provider, error: 40 - Could not open a connection to SQL Server)

#### <span data-ttu-id="df5a1-263">可能的原因</span><span class="sxs-lookup"><span data-stu-id="df5a1-263">Possible causes</span></span>

##### <span data-ttu-id="df5a1-264">原因1</span><span class="sxs-lookup"><span data-stu-id="df5a1-264">Cause 1</span></span>

<span data-ttu-id="df5a1-265">管理员可能在安装管理和监视服务器组件期间指定了无效的数据库实例名称/数据库名称。</span><span class="sxs-lookup"><span data-stu-id="df5a1-265">The administrator may have specified an invalid database instance name/database name during installation of administration and monitoring server components.</span></span>

<span data-ttu-id="df5a1-266">你可以使用 IIS 管理控制台验证和更正数据库连接字符串。</span><span class="sxs-lookup"><span data-stu-id="df5a1-266">You can verify and correct the database connection strings by using the IIS Management console.</span></span> <span data-ttu-id="df5a1-267">若要执行此操作，请打开 IIS 管理器，然后浏览到 Microsoft BitLocker 管理和监视。</span><span class="sxs-lookup"><span data-stu-id="df5a1-267">To do this, open IIS Manager, and browse to Microsoft BitLocker Administration and Monitoring.</span></span> <span data-ttu-id="df5a1-268">对于左侧列出的每个服务，请按照以下步骤更改数据库连接字符串：</span><span class="sxs-lookup"><span data-stu-id="df5a1-268">For each service that is listed on the left side, follow these steps to change the database connection strings:</span></span>

1. <span data-ttu-id="df5a1-269">在 "**功能" 视图**中，双击 "**连接字符串**"。</span><span class="sxs-lookup"><span data-stu-id="df5a1-269">In **Features View**, double-select **Connection Strings**.</span></span>

2. <span data-ttu-id="df5a1-270">在 "**连接字符串**" 页面上，选择要更改的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="df5a1-270">On the **Connection Strings** page, select the connection string that you want to change.</span></span>

3. <span data-ttu-id="df5a1-271">在 "**操作**" 窗格中，选择 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="df5a1-271">In the **Actions** pane, select **Edit**.</span></span>

4. <span data-ttu-id="df5a1-272">在 "**编辑连接字符串**" 对话框中，更改要更改的属性，然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="df5a1-272">In the **Edit Connection String** dialog box, change the properties that you want to change, and then select **OK**.</span></span>

##### <span data-ttu-id="df5a1-273">原因2</span><span class="sxs-lookup"><span data-stu-id="df5a1-273">Cause 2</span></span>

<span data-ttu-id="df5a1-274">防火墙中已阻止 SQL Server 端口。</span><span class="sxs-lookup"><span data-stu-id="df5a1-274">SQL Server port blocked in firewall.</span></span> <span data-ttu-id="df5a1-275">验证 SQL Server 配置为要侦听的端口号，并确保该端口已在管理服务器和数据库服务器之间的防火墙中打开。</span><span class="sxs-lookup"><span data-stu-id="df5a1-275">Verify the port number to which SQL Server is configured to listen, and make sure that the port is open in the firewall between the administration server and database server.</span></span>

##### <span data-ttu-id="df5a1-276">原因3</span><span class="sxs-lookup"><span data-stu-id="df5a1-276">Cause 3</span></span>

<span data-ttu-id="df5a1-277">不正确的 SQL server TCP/IP 绑定。</span><span class="sxs-lookup"><span data-stu-id="df5a1-277">Incorrect SQL server TCP/IP bindings.</span></span> <span data-ttu-id="df5a1-278">在数据库服务器上的 SQL Server 配置管理器中验证 SQL TCP/IP 绑定。</span><span class="sxs-lookup"><span data-stu-id="df5a1-278">Verify SQL TCP/IP bindings in SQL Server Configuration Manager on the database server.</span></span> <span data-ttu-id="df5a1-279">MBAM 要求启用 TCP/IP 和命名管道协议以连接到数据库。</span><span class="sxs-lookup"><span data-stu-id="df5a1-279">MBAM requires that the TCP/IP and Named Pipes protocols are enabled to connect to the database.</span></span>

##### <span data-ttu-id="df5a1-280">原因4</span><span class="sxs-lookup"><span data-stu-id="df5a1-280">Cause 4</span></span>

<span data-ttu-id="df5a1-281">NT Authority\Network 服务帐户或 MBAM 管理服务器的计算机帐户没有连接到 SQL 数据库所需的权限。</span><span class="sxs-lookup"><span data-stu-id="df5a1-281">The NT Authority\Network Service account or the MBAM Administration Server’s computer account doesn't have the required permissions to connect to the SQL database.</span></span>

<span data-ttu-id="df5a1-282">在数据库服务器上安装数据库组件期间，安装程序将创建两个本地组： MBAM 合规性审核数据库访问和 MBAM 恢复和硬件数据库访问。</span><span class="sxs-lookup"><span data-stu-id="df5a1-282">During the installation of database components on the database server, the installer creates two local groups: MBAM Compliance Auditing DB Access and MBAM Recovery and Hardware DB Access.</span></span>

<span data-ttu-id="df5a1-283">NT Authority\Network 服务帐户、MBAM 管理服务器的计算机帐户和安装数据库组件的用户将自动添加到这些组中。</span><span class="sxs-lookup"><span data-stu-id="df5a1-283">The NT Authority\Network Service account, the MBAM administration server’s computer account, and the user who installs the database components are automatically added to these groups.</span></span>

<span data-ttu-id="df5a1-284">在安装期间，这些组被授予对数据库所需的权限。</span><span class="sxs-lookup"><span data-stu-id="df5a1-284">These groups are granted the required permissions on the database during the installation.</span></span> <span data-ttu-id="df5a1-285">属于该组的所有用户都会自动收到数据库所需的权限。</span><span class="sxs-lookup"><span data-stu-id="df5a1-285">All users who are part of this group automatically receive the required permissions on the database.</span></span>

<span data-ttu-id="df5a1-286">Web 服务可能无法连接到数据库服务器，因为如果存在以下一种或多种情况，则会出现权限问题：</span><span class="sxs-lookup"><span data-stu-id="df5a1-286">The web service may not connect to the database server because of a permissions issue if one or more of the following conditions are true:</span></span>

* <span data-ttu-id="df5a1-287">之前提到的组将从数据库服务器上的本地组中删除。</span><span class="sxs-lookup"><span data-stu-id="df5a1-287">The groups that were mentioned earlier are removed from the local groups on the database server.</span></span>

* <span data-ttu-id="df5a1-288">NT Authority\Network 服务帐户和 MBAM 管理服务器的计算机帐户不是这些组的成员。</span><span class="sxs-lookup"><span data-stu-id="df5a1-288">The NT Authority\Network Service account and the MBAM administration server’s computer account are not members of these groups.</span></span>

* <span data-ttu-id="df5a1-289">这些组没有数据库所需的权限。</span><span class="sxs-lookup"><span data-stu-id="df5a1-289">These groups do not have the required permissions on the database.</span></span>

<span data-ttu-id="df5a1-290">如果上述任何条件为 true，你将注意 MBAM 管理和监视服务器上的应用程序日志中与权限相关的错误。</span><span class="sxs-lookup"><span data-stu-id="df5a1-290">You will notice permissions-related errors in the Application logs on the MBAM administration and monitoring server if any of the previous conditions are true.</span></span> <span data-ttu-id="df5a1-291">在这种情况下，你应该手动添加 NT Authority\Network 服务帐户和 MBAM 管理服务器的计算机帐户，并在使用 SQL Server Management Studio （.）的 SQL 数据库服务器上授予其服务器范围内的公共角色 https://msdn.microsoft.com/library/aa337562.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="df5a1-291">In that case, you should manually add the NT Authority\Network Service account and MBAM administration server’s computer account and grant them a server-wide public role on the SQL database server that is using SQL Server Management Studio (https://msdn.microsoft.com/library/aa337562.aspx).</span></span>

#### <span data-ttu-id="df5a1-292">查看 web 服务日志</span><span class="sxs-lookup"><span data-stu-id="df5a1-292">Review the web service logs</span></span>

<span data-ttu-id="df5a1-293">如果 MBAM 管理服务器上的应用程序日志中未记录任何事件，现在就可以查看 MBAM 管理和监视服务器上托管的 MBAM web 服务的 web 服务日志（svclog）。</span><span class="sxs-lookup"><span data-stu-id="df5a1-293">If no events are logged in the Application logs on the MBAM administration server, it’s time to review the web service logs (.svclog) of the MBAM web service that is hosted on the MBAM administration and monitoring server.</span></span> <span data-ttu-id="df5a1-294">您必须使用服务跟踪查看器工具（SvcTraceViewer.exe） https://msdn.microsoft.com/library/ms732023.aspx 查看日志文件。</span><span class="sxs-lookup"><span data-stu-id="df5a1-294">You will have to use the Service Trace Viewer Tool (SvcTraceViewer.exe) https://msdn.microsoft.com/library/ms732023.aspx to view the log file.</span></span>

<span data-ttu-id="df5a1-295">你应该首先研究 RecoveryandHardwareService 和 ComplianceStatusService 的服务跟踪日志。</span><span class="sxs-lookup"><span data-stu-id="df5a1-295">You should primarily investigate the service trace logs of RecoveryandHardwareService and ComplianceStatusService.</span></span> <span data-ttu-id="df5a1-296">默认情况下，web 服务日志位于 C:\inetpub\Microsoft BitLocker Management Solution\Logs 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="df5a1-296">By default, web service logs are located in the C:\inetpub\Microsoft BitLocker Management Solution\Logs folder.</span></span> <span data-ttu-id="df5a1-297">在此情况下，每个服务在其自己的文件夹下写入其 svclog 文件。</span><span class="sxs-lookup"><span data-stu-id="df5a1-297">There, each service writes its .svclog file under its own folder.</span></span>

<span data-ttu-id="df5a1-298">在服务跟踪日志中查看任何错误或警告条目的活动。</span><span class="sxs-lookup"><span data-stu-id="df5a1-298">Review the activity in the service trace log for any error or warning entries.</span></span> <span data-ttu-id="df5a1-299">默认情况下，错误条目以红色突出显示。</span><span class="sxs-lookup"><span data-stu-id="df5a1-299">By default, error entries are highlighted in red.</span></span> <span data-ttu-id="df5a1-300">在跟踪查看器的右窗格中选择 "错误说明"，以查看有关错误条目的详细信息。</span><span class="sxs-lookup"><span data-stu-id="df5a1-300">Select the error description on the right pane of the trace viewer to view detailed information about the error entry.</span></span> <span data-ttu-id="df5a1-301">以下是跟踪日志中的示例错误条目：</span><span class="sxs-lookup"><span data-stu-id="df5a1-301">The following is a sample error entry from the trace log:</span></span>

    <E2ETraceEvent xmlns="http://schemas.microsoft.com/2004/06/E2ETraceEvent">
    <System xmlns="http://schemas.microsoft.com/2004/06/windows/eventlog/system">
    <EventID>15183</EventID>
    <Type>3</Type>
    <SubType Name="Error">0</SubType>
    <Level>2</Level>
    <TimeCreated SystemTime="2013-07-05T14:48:06.2821550Z" />
    <Source Name="Microsoft.Mbam.CoreService" />
    <Correlation ActivityID="{00000000-0000-0000-0000-000000000000}" />
    <Execution ProcessName="w3wp" ProcessID="4332" ThreadID="11" />
    <Channel />
    <Computer>XXXXXXXXXXX</Computer>
    </System>
    <ApplicationData>AddUpdateVolume: While executing sql transaction for add volume to store exception occurred Key Recovery Data Store processing error: Violation of UNIQUE KEY constraint 'UniqueRecoveryKeyId'. Cannot insert duplicate key in object 'RecoveryAndHardwareCore.Keys'. The duplicate key value is (8637036e-b379-4798-bd9e-5a0b36296de3).
    </ApplicationData>
    </E2ETraceEvent>

## <span data-ttu-id="df5a1-302">重新安装或重新配置 MBAM 基础结构</span><span class="sxs-lookup"><span data-stu-id="df5a1-302">Re-installation or reconfiguration of MBAM infrastructure</span></span>

<span data-ttu-id="df5a1-303">若要重新安装或重新配置 MBAM 基础结构，必须了解以下事项：</span><span class="sxs-lookup"><span data-stu-id="df5a1-303">To re-install or reconfigure MBAM infrastructure, you must know the following things:</span></span>

* <span data-ttu-id="df5a1-304">应用程序池帐户</span><span class="sxs-lookup"><span data-stu-id="df5a1-304">Application Pool account</span></span>

* <span data-ttu-id="df5a1-305">MBAM 组（"帮助台"、"高级"、"报表用户" 组）</span><span class="sxs-lookup"><span data-stu-id="df5a1-305">MBAM Groups (Helpdesk, Advanced, Report Users Group)</span></span>

* <span data-ttu-id="df5a1-306">MBAM 报表 URL</span><span class="sxs-lookup"><span data-stu-id="df5a1-306">MBAM Reports URL</span></span>

* <span data-ttu-id="df5a1-307">SQL Server 名称和数据库名称</span><span class="sxs-lookup"><span data-stu-id="df5a1-307">SQL Server name and database names</span></span>

* <span data-ttu-id="df5a1-308">MBAM ReadWrite 和只读帐户</span><span class="sxs-lookup"><span data-stu-id="df5a1-308">MBAM ReadWrite and ReadOnly Accounts</span></span>

### <span data-ttu-id="df5a1-309">应用程序池帐户</span><span class="sxs-lookup"><span data-stu-id="df5a1-309">Application Pool account</span></span>

<span data-ttu-id="df5a1-310">若要查找应用程序池帐户，请登录到 MBAM Web 服务器，打开 " **Internet 信息服务（IIS）管理器**"，然后选择 "**应用程序池**"：</span><span class="sxs-lookup"><span data-stu-id="df5a1-310">To find the Application Pool account, log on to the MBAM Web Server, open **Internet Information Services (IIS) Manager**, and then select **Application Pools**:</span></span>

![应用程序池](images/troubleshooting-MBAM-installation-1.png)

<span data-ttu-id="df5a1-312">服务主体名称（SPN）必须在此帐户中设置。</span><span class="sxs-lookup"><span data-stu-id="df5a1-312">The Service Principal Name (SPN) must be set in this account.</span></span> <span data-ttu-id="df5a1-313">此设置对 MBAM 的功能非常重要。</span><span class="sxs-lookup"><span data-stu-id="df5a1-313">This setting is very important to the functionality of MBAM.</span></span>

### <span data-ttu-id="df5a1-314">MBAM 组（"帮助台"、"高级"、"报表用户" 组和报表 URL）</span><span class="sxs-lookup"><span data-stu-id="df5a1-314">MBAM Groups (Helpdesk, Advanced, Report Users Group and Reports URL)</span></span>

![MBAM 组](images/troubleshooting-MBAM-installation-2.png)

<span data-ttu-id="df5a1-316">这将提供如帮助台组、高级帮助台组、报表用户组和 MBAM 报表 URL 等信息。</span><span class="sxs-lookup"><span data-stu-id="df5a1-316">This provides information such as Helpdesk Group, Advanced Helpdesk Group, Report Users group, and MBAM Reports URL.</span></span> <span data-ttu-id="df5a1-317">MBAM 报表 URL 必须在 MBAM 设置中提供，并且应读取为： http （s）：//servername/ReportServer。</span><span class="sxs-lookup"><span data-stu-id="df5a1-317">The MBAM Reports URL must be provided in the MBAM setup and should read as: http(s)://servername/ReportServer.</span></span>

### <span data-ttu-id="df5a1-318">SQL Server 名称和数据库（DB）名称</span><span class="sxs-lookup"><span data-stu-id="df5a1-318">SQL Server name and database (DB) names</span></span>

<span data-ttu-id="df5a1-319">若要查找托管 MBAM 的 SQL Server 名称和实例，请登录到 MBAM Web （IIS）服务器并浏览到 folowing 注册表子项：</span><span class="sxs-lookup"><span data-stu-id="df5a1-319">To find the SQL Server names and instances hosting the MBAM DBs, log on to the MBAM Web (IIS) server and browse to the folowing registry subkey:</span></span>

**<span data-ttu-id="df5a1-320">HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\MBAM Server\Web</span><span class="sxs-lookup"><span data-stu-id="df5a1-320">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MBAM Server\Web</span></span>**

![Regedit.exe](images/troubleshooting-MBAM-installation-3.png)

<span data-ttu-id="df5a1-322">突出显示的部分是连接字符串。</span><span class="sxs-lookup"><span data-stu-id="df5a1-322">The highlighted portions are connection strings.</span></span> <span data-ttu-id="df5a1-323">这些应具有 SQL Server 名称、数据库名称和实例（如果已命名）。</span><span class="sxs-lookup"><span data-stu-id="df5a1-323">These should have the SQL Server name, database names, and instances (if named).</span></span>

### <span data-ttu-id="df5a1-324">MBAM ReadWrite 和只读帐户</span><span class="sxs-lookup"><span data-stu-id="df5a1-324">MBAM ReadWrite and ReadOnly accounts</span></span>

<span data-ttu-id="df5a1-325">此信息将位于 SQL Server 数据库中，该数据库已找到来自 web 服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="df5a1-325">This information will be in the SQL Server database, for which we already found the name from the web server.</span></span>

#### <span data-ttu-id="df5a1-326">ReadWrite 帐户</span><span class="sxs-lookup"><span data-stu-id="df5a1-326">ReadWrite account</span></span>

1. <span data-ttu-id="df5a1-327">登录到 SQL Management Studio。</span><span class="sxs-lookup"><span data-stu-id="df5a1-327">Log in to the SQL Management Studio.</span></span>

2. <span data-ttu-id="df5a1-328">右键单击 " **MBAM 恢复和硬件**"，选择 "**属性**"，然后选择 "**权限**"。</span><span class="sxs-lookup"><span data-stu-id="df5a1-328">Right-click **MBAM Recovery and Hardware**, select **Properties**, and then select **Permissions**.</span></span>

<span data-ttu-id="df5a1-329">例如，实验室帐户名称为**MBAMWrite**。</span><span class="sxs-lookup"><span data-stu-id="df5a1-329">For example, The the lab account name is **MBAMWrite**.</span></span> <span data-ttu-id="df5a1-330">应用程序池和读写帐户设置为相同。</span><span class="sxs-lookup"><span data-stu-id="df5a1-330">The Application Pool and ReadWrite accounts are set to be the same.</span></span>

![SQL 数据库](images/troubleshooting-MBAM-installation-4.png)

![DB 属性](images/troubleshooting-MBAM-installation-5.png)

<span data-ttu-id="df5a1-333">在 SQL Management Studio 中浏览到 "**安全性**"，然后按 "**登录**"。</span><span class="sxs-lookup"><span data-stu-id="df5a1-333">Browse to **Security** and then **Logins** in SQL Management Studio.</span></span> <span data-ttu-id="df5a1-334">浏览到上一个屏幕截图中显示的帐户。</span><span class="sxs-lookup"><span data-stu-id="df5a1-334">Browse to the account shown in the previous screenshot.</span></span>

![SQL 安全性](images/troubleshooting-MBAM-installation-6.png)

<span data-ttu-id="df5a1-336">右键单击帐户，转到 "**属性用户映射**"，然后找到 MBAM 恢复和硬件数据库：</span><span class="sxs-lookup"><span data-stu-id="df5a1-336">Right-click the accounts, go to **Properties User Mapping**, and locate the MBAM Recovery and Hardware database:</span></span>

![用户映射](images/troubleshooting-MBAM-installation-7.png)

#### <span data-ttu-id="df5a1-338">只读帐户</span><span class="sxs-lookup"><span data-stu-id="df5a1-338">ReadOnly account</span></span>

<span data-ttu-id="df5a1-339">在 SSRS 服务器上打开 SQL Server Reporting Services 配置管理器。</span><span class="sxs-lookup"><span data-stu-id="df5a1-339">Open SQL Server Reporting Services Configuration Manager on the SSRS Server.</span></span> <span data-ttu-id="df5a1-340">选择 "**报表管理器 URL**"，然后浏览**url**：</span><span class="sxs-lookup"><span data-stu-id="df5a1-340">Select **Report Manager URL**, and then browse the **URLs**:</span></span>

![报表管理器](images/troubleshooting-MBAM-installation-8.png)

<span data-ttu-id="df5a1-342">选择 " **Microsoft Bitlocker 管理和监视**"：</span><span class="sxs-lookup"><span data-stu-id="df5a1-342">Select **Microsoft Bitlocker Administration and Monitoring**:</span></span>

![Bitlocker 管理和监视](images/troubleshooting-MBAM-installation-9.png)

<span data-ttu-id="df5a1-344">选择**MaltaDatasource**：</span><span class="sxs-lookup"><span data-stu-id="df5a1-344">Select **MaltaDatasource**:</span></span>

![It](images/troubleshooting-MBAM-installation-10.png)

![MaltaDatasource](images/troubleshooting-MBAM-installation-11.png)

<span data-ttu-id="df5a1-347">MaltaDataSource 应具有只读帐户名称，并且应在 MBAM 设置中使用。</span><span class="sxs-lookup"><span data-stu-id="df5a1-347">MaltaDataSource should have the ReadOnly Account name and should be used in MBAM setup.</span></span>

## <span data-ttu-id="df5a1-348">参考</span><span class="sxs-lookup"><span data-stu-id="df5a1-348">Reference</span></span>

<span data-ttu-id="df5a1-349">有关详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="df5a1-349">For more information, see the following articles:</span></span>

[<span data-ttu-id="df5a1-350">在独立配置中部署 MBAM 2。5</span><span class="sxs-lookup"><span data-stu-id="df5a1-350">Deploying MBAM 2.5 in a standalone configuration</span></span>](https://support.microsoft.com/help/3046555)

[<span data-ttu-id="df5a1-351">Microsoft BitLocker 管理和监控 2.5</span><span class="sxs-lookup"><span data-stu-id="df5a1-351">Microsoft BitLocker Administration and Monitoring 2.5</span></span>](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/)
