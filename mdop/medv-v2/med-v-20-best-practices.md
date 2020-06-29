---
title: MED-V 2.0 最佳做法
description: MED-V 2.0 最佳做法
author: dansimp
ms.assetid: 47ba2dd1-6c6e-4d6e-8e18-b42291f8e02a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7b664d33b403b821ce6bc9c045d937380ab4f91b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803903"
---
# <span data-ttu-id="25a44-103">MED-V 2.0 最佳做法</span><span class="sxs-lookup"><span data-stu-id="25a44-103">MED-V 2.0 Best Practices</span></span>


<span data-ttu-id="25a44-104">在您的企业中规划、部署和管理 MED-V 时，您可能会发现最佳做法建议非常有用。</span><span class="sxs-lookup"><span data-stu-id="25a44-104">When you are planning, deploying, and managing MED-V in your enterprise, you may find the best practice recommendations to be useful.</span></span>

### <span data-ttu-id="25a44-105">配置首次设置以无人参与运行</span><span class="sxs-lookup"><span data-stu-id="25a44-105">Configure first time setup to run unattended</span></span>

<span data-ttu-id="25a44-106">虽然你可以指定所需的任何设置，但 MED-V 最佳做法是创建 Sysprep.inf 文件，以便首次运行时可以在**无人参与**模式下运行。</span><span class="sxs-lookup"><span data-stu-id="25a44-106">Although you can specify any settings that you prefer, a MED-V best practice is that you create the Sysprep.inf file so that first time setup can be run in **Unattended** mode.</span></span> <span data-ttu-id="25a44-107">这要求你在继续**安装管理器**向导时提供所有所需的设置信息。</span><span class="sxs-lookup"><span data-stu-id="25a44-107">This requires you to provide all the required settings information as you continue through the **Setup Manager** wizard.</span></span> <span data-ttu-id="25a44-108">有关如何配置 MED-V 映像的详细信息，请参阅[配置适用于 med-v 的 Windows 虚拟 PC 映像](configuring-a-windows-virtual-pc-image-for-med-v.md)。</span><span class="sxs-lookup"><span data-stu-id="25a44-108">For more information about how to configure the MED-V image, see [Configuring a Windows Virtual PC Image for MED-V](configuring-a-windows-virtual-pc-image-for-med-v.md).</span></span>

### <span data-ttu-id="25a44-109">在虚拟机上禁用还原点</span><span class="sxs-lookup"><span data-stu-id="25a44-109">Disable restore points on the virtual machine</span></span>

<span data-ttu-id="25a44-110">在创建 MED-V 工作区程序包之前，我们建议你在虚拟机上禁用还原点，以防止差异磁盘无限增长。</span><span class="sxs-lookup"><span data-stu-id="25a44-110">Before you create the MED-V workspace package, we recommend that you disable restore points on the virtual machine to prevent the differencing disk from growing unbounded.</span></span> <span data-ttu-id="25a44-111">有关详细信息，请参阅[如何在 WINDOWS XP 中关闭和打开系统还原](https://go.microsoft.com/fwlink/?LinkId=195927)（ https://go.microsoft.com/fwlink/?LinkId=195927) 。</span><span class="sxs-lookup"><span data-stu-id="25a44-111">For more information, see [How to turn off and turn on System Restore in Windows XP](https://go.microsoft.com/fwlink/?LinkId=195927) (https://go.microsoft.com/fwlink/?LinkId=195927).</span></span>

### <span data-ttu-id="25a44-112">将 MED-V 映像配置为使用本地配置文件</span><span class="sxs-lookup"><span data-stu-id="25a44-112">Configure MED-V image to use local profiles</span></span>

<span data-ttu-id="25a44-113">我们建议你仅应用在 Windows XP 的应用程序兼容性环境中有意义的策略。</span><span class="sxs-lookup"><span data-stu-id="25a44-113">We recommend that you apply only those policies that make sense in an application compatibility environment for Windows XP.</span></span> <span data-ttu-id="25a44-114">例如，桌面自定义策略通常不需要应用，应禁用。</span><span class="sxs-lookup"><span data-stu-id="25a44-114">For example, desktop customization policies do not typically have to be applied and should be disabled.</span></span> <span data-ttu-id="25a44-115">有关如何仅允许本地配置文件的详细信息，请参阅[漫游用户配置文件（.）的组策略设置](https://go.microsoft.com/fwlink/?LinkId=205072) https://go.microsoft.com/fwlink/?LinkId=205072) 。</span><span class="sxs-lookup"><span data-stu-id="25a44-115">For more information about how to allow only local profiles, see [Group Policy Settings for Roaming User Profiles](https://go.microsoft.com/fwlink/?LinkId=205072) (https://go.microsoft.com/fwlink/?LinkId=205072).</span></span>

### <span data-ttu-id="25a44-116">配置组策略性能更新</span><span class="sxs-lookup"><span data-stu-id="25a44-116">Configure a Group Policy performance update</span></span>

<span data-ttu-id="25a44-117">默认情况下，组策略一次下载到计算机一个字节。</span><span class="sxs-lookup"><span data-stu-id="25a44-117">By default, Group Policy is downloaded to a computer one byte at a time.</span></span> <span data-ttu-id="25a44-118">这将导致在 MED-V 加入到域时出现延迟。</span><span class="sxs-lookup"><span data-stu-id="25a44-118">This causes delays when MED-V is being joined to the domain.</span></span> <span data-ttu-id="25a44-119">若要提高组策略的性能，建议将以下注册表项值设置为注册表：</span><span class="sxs-lookup"><span data-stu-id="25a44-119">To increase the performance of Group Policy, we recommend that you set the following registry key value to the registry:</span></span>

<span data-ttu-id="25a44-120">注册表子项： HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon</span><span class="sxs-lookup"><span data-stu-id="25a44-120">Registry subkey: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon</span></span>

<span data-ttu-id="25a44-121">Entry： BufferPolicyReads</span><span class="sxs-lookup"><span data-stu-id="25a44-121">Entry: BufferPolicyReads</span></span>

<span data-ttu-id="25a44-122">类型：DWORD</span><span class="sxs-lookup"><span data-stu-id="25a44-122">Type: DWORD</span></span>

<span data-ttu-id="25a44-123">值：1</span><span class="sxs-lookup"><span data-stu-id="25a44-123">Value: 1</span></span>

### <span data-ttu-id="25a44-124">通过组策略（而不是在 MED-V 映像）分发法律公告</span><span class="sxs-lookup"><span data-stu-id="25a44-124">Distribute legal notice through Group Policy instead of in the MED-V image</span></span>

<span data-ttu-id="25a44-125">如果希望最终用户在访问 MED-V 之前看到服务级别协议（SLA），我们建议你稍后通过组策略强制实施 SLA，以便在首次完成设置后向最终用户显示 SLA。</span><span class="sxs-lookup"><span data-stu-id="25a44-125">If you want end users to see a service level agreement (SLA) before they access MED-V, we recommend that you enforce the SLA through Group Policy later so that the SLA is displayed to the end user after the first time setup is finished.</span></span>

<span data-ttu-id="25a44-126">**小心** 尽管最佳做法是在**无人参与**模式下首次运行设置，但如果你决定将本地策略或注册表项设置为在映像（虚拟硬盘）中包含 SLA，则还必须指定首次在**参与**模式下运行设置，或者首次安装失败。</span><span class="sxs-lookup"><span data-stu-id="25a44-126">**Caution** Even though a best practice is to run first time setup in **Unattended** mode, if you decide to set the local policy or registry entry to include an SLA in your image (virtual hard disk), you must also specify that first time setup is run in **Attended** mode, or first time setup can fail.</span></span>

 

### <span data-ttu-id="25a44-127">压缩虚拟硬盘</span><span class="sxs-lookup"><span data-stu-id="25a44-127">Compact the virtual hard disk</span></span>

<span data-ttu-id="25a44-128">我们建议你压缩虚拟硬盘以回收空磁盘空间并减小虚拟硬盘的大小。</span><span class="sxs-lookup"><span data-stu-id="25a44-128">We recommend that you compact your virtual hard disk to reclaim empty disk space and reduce the size of the virtual hard disk.</span></span> <span data-ttu-id="25a44-129">有关如何压缩虚拟硬盘的详细信息，请参阅[压缩 Med-v 虚拟硬盘](compacting-the-med-v-virtual-hard-disk.md)。</span><span class="sxs-lookup"><span data-stu-id="25a44-129">For more information about how to compact your virtual hard disk, see [Compacting the MED-V Virtual Hard Disk](compacting-the-med-v-virtual-hard-disk.md).</span></span>

### <span data-ttu-id="25a44-130">将虚拟机配置为在蓝色屏幕崩溃时重启</span><span class="sxs-lookup"><span data-stu-id="25a44-130">Configure virtual machine to restart on blue screen crash</span></span>

<span data-ttu-id="25a44-131">我们建议你将 MED-V 工作区虚拟机配置为在遇到蓝色屏幕崩溃时自动重启。</span><span class="sxs-lookup"><span data-stu-id="25a44-131">We recommend that you configure the MED-V workspace virtual machine to automatically restart when it encounters a blue screen crash.</span></span> <span data-ttu-id="25a44-132">若要在来宾中配置此设置，请将 HKEY \ _LOCAL \ _MACHINE \\SYSTEM\\CurrentControlSet\\Control\\CrashControl 项中的 AutoReboot 值设置为 "1"。</span><span class="sxs-lookup"><span data-stu-id="25a44-132">To configure this setting in the guest, set the AutoReboot value in the HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Control\\CrashControl key to “1”.</span></span>

<span data-ttu-id="25a44-133">您也可以通过单击 "**开始**"，单击 **"控制面板**"，然后单击 "**系统**" 来配置此设置。</span><span class="sxs-lookup"><span data-stu-id="25a44-133">You can also configure this setting by clicking **Start**, clicking **Control Panel**, and then clicking **System**.</span></span> <span data-ttu-id="25a44-134">然后，在 "**高级**" 选项卡的 "**启动和恢复**" 区域中，单击 "**设置**"。</span><span class="sxs-lookup"><span data-stu-id="25a44-134">Then, in the **Startup and Recovery** area of the **Advanced** tab, click **Settings**.</span></span> <span data-ttu-id="25a44-135">选中 "**自动重新启动**" 复选框，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="25a44-135">Select the **Automatically restart** check box and click **OK**.</span></span>

### <span data-ttu-id="25a44-136">在密封 MED-V 图像之前对其进行备份</span><span class="sxs-lookup"><span data-stu-id="25a44-136">Back up MED-V image before sealing it</span></span>

<span data-ttu-id="25a44-137">我们建议你先创建 MED-V 映像的备份副本，然后再进行密封。</span><span class="sxs-lookup"><span data-stu-id="25a44-137">We recommend that you create a backup copy of the MED-V image before you seal it.</span></span> <span data-ttu-id="25a44-138">有关密封 MED-V 映像的详细信息，请参阅[配置适用于 med-v 的 Windows 虚拟 PC 映像](configuring-a-windows-virtual-pc-image-for-med-v.md)。</span><span class="sxs-lookup"><span data-stu-id="25a44-138">For more information about sealing your MED-V image, see [Configuring a Windows Virtual PC Image for MED-V](configuring-a-windows-virtual-pc-image-for-med-v.md).</span></span>

### <span data-ttu-id="25a44-139">从批处理文件安装时最后安装 Windows Virtual 电脑</span><span class="sxs-lookup"><span data-stu-id="25a44-139">Install Windows Virtual PC last when installing from a batch file</span></span>

<span data-ttu-id="25a44-140">使用批处理文件安装 MED-V 组件时，请指定在 MED-V 主机代理和 MED-V 工作区程序包文件之后安装 Windows 虚拟 PC 和 Windows 虚拟 PC 修补程序。</span><span class="sxs-lookup"><span data-stu-id="25a44-140">When you install the MED-V components by using a batch file, specify that Windows Virtual PC and the Windows Virtual PC hotfix are installed after the MED-V Host Agent and the MED-V workspace package files.</span></span> <span data-ttu-id="25a44-141">这可确保 Windows 更新不会通过需要重新启动来导致任何与安装过程的干扰。</span><span class="sxs-lookup"><span data-stu-id="25a44-141">This ensures that Windows Update will not cause any interference with the installation process by requiring a restart.</span></span>

### <span data-ttu-id="25a44-142">从本地文件夹安装 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="25a44-142">Install MED-V workspace from local folder</span></span>

<span data-ttu-id="25a44-143">由于从网络位置安装 MED-V 时可能出现的问题，我们建议你在本地复制 MED-V 工作区设置文件，然后运行 setup.exe。</span><span class="sxs-lookup"><span data-stu-id="25a44-143">Because of problems that can occur when you install MED-V from a network location, we recommend that you copy the MED-V workspace setup files locally and then run setup.exe.</span></span>

### <a href="" id="manage-printer-redirection-in-one-manner-only-"></a><span data-ttu-id="25a44-144">仅以一种方式管理打印机重定向</span><span class="sxs-lookup"><span data-stu-id="25a44-144">Manage printer redirection in one manner only</span></span>

<span data-ttu-id="25a44-145">如果在 MED-V 来宾虚拟机上手动安装了打印机，并且在主机上安装了相同的打印机，则结果是在来宾中安装了两次。</span><span class="sxs-lookup"><span data-stu-id="25a44-145">If a printer is manually installed on the MED-V guest virtual machine, and the same printer is later installed on the host computer, the result is that it is installed two times in the guest.</span></span> <span data-ttu-id="25a44-146">为避免这种情况，我们建议采用一种仅以一种方式管理打印机重定向的 MED-V 最佳做法：禁用重定向并在来宾上手动安装打印机，或者启用重定向，不要在来宾上手动安装打印机。</span><span class="sxs-lookup"><span data-stu-id="25a44-146">To avoid this situation, we recommend as MED-V best practice that you manage printer redirection in one manner only: either disable redirection and install printers manually on the guest, or enable redirection and do not install printers manually on the guest.</span></span>

### <a href="" id="configure-settings-for-med-v-guest-patching-"></a><span data-ttu-id="25a44-147">为 MED-V 来宾修补程序配置设置</span><span class="sxs-lookup"><span data-stu-id="25a44-147">Configure settings for MED-V guest patching</span></span>

<span data-ttu-id="25a44-148">你可以通过在注册表中定义相关的配置值来控制 MED-V 虚拟机 awakens 接收自动更新的时间和时间。</span><span class="sxs-lookup"><span data-stu-id="25a44-148">You can control when and for how long the MED-V virtual machine awakens to receive automatic updates by defining the relevant configuration values in the registry.</span></span> <span data-ttu-id="25a44-149">MED-V 最佳做法是设置唤醒时间间隔，以匹配为 MED-V 虚拟机安排定期更新的时间。</span><span class="sxs-lookup"><span data-stu-id="25a44-149">A MED-V best practice is to set your wake-up interval to match the time when you have scheduled regular updates for MED-V virtual machines.</span></span> <span data-ttu-id="25a44-150">此外，我们建议你将这些设置配置为类似于主机的行为。</span><span class="sxs-lookup"><span data-stu-id="25a44-150">In addition, we recommend that you configure these settings to resemble the host computer’s behavior.</span></span>

<span data-ttu-id="25a44-151">有关如何配置 MED-V 来宾修补的设置的详细信息，请参阅[管理 Med-v 工作区的自动更新](managing-automatic-updates-for-med-v-workspaces.md)。</span><span class="sxs-lookup"><span data-stu-id="25a44-151">For more information about how to configure settings for MED-V guest patching, see [Managing Automatic Updates for MED-V Workspaces](managing-automatic-updates-for-med-v-workspaces.md).</span></span>

### <span data-ttu-id="25a44-152">配置防病毒/备份软件</span><span class="sxs-lookup"><span data-stu-id="25a44-152">Configure antivirus/backup software</span></span>

<span data-ttu-id="25a44-153">为了防止防病毒活动影响虚拟桌面的性能，我们建议你在可以时从运行于 MED-V 主机计算机上的任何防病毒软件或备份进程中排除以下虚拟机文件类型：</span><span class="sxs-lookup"><span data-stu-id="25a44-153">To prevent antivirus activity from affecting the performance of the virtual desktop, we recommend that when you can, you exclude the following virtual machine file types from any antivirus or backup process that is running on the MED-V host computer:</span></span>

-   <span data-ttu-id="25a44-154">\*.VMC</span><span class="sxs-lookup"><span data-stu-id="25a44-154">\*.VMC</span></span>

-   <span data-ttu-id="25a44-155">\*.VUD</span><span class="sxs-lookup"><span data-stu-id="25a44-155">\*.VUD</span></span>

-   <span data-ttu-id="25a44-156">\*.VSV</span><span class="sxs-lookup"><span data-stu-id="25a44-156">\*.VSV</span></span>

-   <span data-ttu-id="25a44-157">\*..VHD</span><span class="sxs-lookup"><span data-stu-id="25a44-157">\*.VHD</span></span>

## <span data-ttu-id="25a44-158">相关主题</span><span class="sxs-lookup"><span data-stu-id="25a44-158">Related topics</span></span>


[<span data-ttu-id="25a44-159">MED-V 的安全和保护</span><span class="sxs-lookup"><span data-stu-id="25a44-159">Security and Protection for MED-V</span></span>](security-and-protection-for-med-v.md)

 

 





