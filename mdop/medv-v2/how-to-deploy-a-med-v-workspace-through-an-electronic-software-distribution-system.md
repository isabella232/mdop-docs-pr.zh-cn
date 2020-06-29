---
title: 如何通过电子软件分发系统部署 MED-V 工作区
description: 如何通过电子软件分发系统部署 MED-V 工作区
author: dansimp
ms.assetid: b5134c35-e1de-470c-93f8-ead6218d9dce
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 56d21b0c2f010f63c04056d9fadd7763531bd9d5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798184"
---
# <span data-ttu-id="d43f1-103">如何通过电子软件分发系统部署 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="d43f1-103">How to Deploy a MED-V Workspace Through an Electronic Software Distribution System</span></span>


<span data-ttu-id="d43f1-104">电子软件分发系统旨在通过慢速或快速网络连接高效地将软件移动到许多不同的计算机。</span><span class="sxs-lookup"><span data-stu-id="d43f1-104">An electronic software distribution system is designed to efficiently move software to many different computers over slow or fast network connections.</span></span> <span data-ttu-id="d43f1-105">以下部分提供了可帮助你使用软件分发系统在整个企业中部署 MED-V 工作区的信息和说明。</span><span class="sxs-lookup"><span data-stu-id="d43f1-105">The following section provides information and instructions to help you deploy your MED-V workspace throughout your enterprise by using a software distribution system.</span></span>

**<span data-ttu-id="d43f1-106">注意</span><span class="sxs-lookup"><span data-stu-id="d43f1-106">Note</span></span>**  
<span data-ttu-id="d43f1-107">无论使用哪种软件分发解决方案，您都必须熟悉特定解决方案的要求。</span><span class="sxs-lookup"><span data-stu-id="d43f1-107">Whichever software distribution solution that you use, you must be familiar with the requirements of your particular solution.</span></span> <span data-ttu-id="d43f1-108">如果您使用的是 System Center Configuration Manager 2007 R2 或更高版本，请参阅 Microsoft 技术库（）中的[Configuration Manager 文档库](https://go.microsoft.com/fwlink/?LinkId=66999) https://go.microsoft.com/fwlink/?LinkId=66999) 。</span><span class="sxs-lookup"><span data-stu-id="d43f1-108">If you are using System Center Configuration Manager 2007 R2 or a later version, see the [Configuration Manager Documentation Library](https://go.microsoft.com/fwlink/?LinkId=66999) in the Microsoft Technical Library (https://go.microsoft.com/fwlink/?LinkId=66999).</span></span>



**<span data-ttu-id="d43f1-109">重要提示</span><span class="sxs-lookup"><span data-stu-id="d43f1-109">Important</span></span>**  
<span data-ttu-id="d43f1-110">如果你使用的是 System Center Configuration Manager 2007 SP2，并且你的 MED-V 工作区配置为在**NAT**模式下运行，则虚拟机将归为基于 Internet 的客户端，并且无法找到要从中下载内容的最近分发点。</span><span class="sxs-lookup"><span data-stu-id="d43f1-110">If you are using System Center Configuration Manager 2007 SP2 and your MED-V workspaces are configured to operate in **NAT** mode, the virtual machines are classified as Internet-based clients and cannot find the closest distribution points from which to download content.</span></span>

<span data-ttu-id="d43f1-111">[用于改进由 med-v 管理的 vm 的功能的修复程序](https://go.microsoft.com/fwlink/?LinkId=201088)（ https://go.microsoft.com/fwlink/?LinkId=201088) 将新功能添加到由 med-v 托管的虚拟机并配置为在**NAT**模式下运行。</span><span class="sxs-lookup"><span data-stu-id="d43f1-111">The [hotfix to improve the functionality for VMs that are managed by MED-V](https://go.microsoft.com/fwlink/?LinkId=201088) (https://go.microsoft.com/fwlink/?LinkId=201088) adds new functionality to virtual machines that are managed by MED-V and that are configured to operate in **NAT** mode.</span></span> <span data-ttu-id="d43f1-112">新功能允许虚拟机访问最近的分发点。</span><span class="sxs-lookup"><span data-stu-id="d43f1-112">The new functionality lets virtual machines access the closest distribution points.</span></span> <span data-ttu-id="d43f1-113">因此，管理员可以采用同样的方式管理虚拟机和主机。</span><span class="sxs-lookup"><span data-stu-id="d43f1-113">Therefore, the administrator can manage the virtual machine and the host computer in the same manner.</span></span> <span data-ttu-id="d43f1-114">此修补程序必须首先在网站服务器上安装，然后再安装在客户端上。</span><span class="sxs-lookup"><span data-stu-id="d43f1-114">This hotfix must be installed first on the site server and then on the client.</span></span>

<span data-ttu-id="d43f1-115">该更新已公开提供。</span><span class="sxs-lookup"><span data-stu-id="d43f1-115">The update is publicly available.</span></span> <span data-ttu-id="d43f1-116">但是，系统可能会提示您接受 Microsoft 服务协议。</span><span class="sxs-lookup"><span data-stu-id="d43f1-116">However, you might be prompted to accept an agreement for Microsoft Services.</span></span> <span data-ttu-id="d43f1-117">按照后续网页上的提示检索此修补程序。</span><span class="sxs-lookup"><span data-stu-id="d43f1-117">Follow the prompts on the successive webpages to retrieve this hotfix.</span></span>



<span data-ttu-id="d43f1-118">你还可以使用批处理文件将 MED-V 组件一起部署，但这需要在安装 Windows 虚拟 PC 后重新启动。</span><span class="sxs-lookup"><span data-stu-id="d43f1-118">You can also deploy the MED-V components together by using a batch file, but this requires a restart after the installation of Windows Virtual PC.</span></span> <span data-ttu-id="d43f1-119">若要跳过此要求，可以在安装所有组件后指定一个重启。</span><span class="sxs-lookup"><span data-stu-id="d43f1-119">To bypass this requirement, you can specify a single restart after all of the components are installed.</span></span> <span data-ttu-id="d43f1-120">单次重启也会自动启动 MED-V-V，因为 MED-V 工作区安装会在 RUNKEY 中放置一个条目。</span><span class="sxs-lookup"><span data-stu-id="d43f1-120">The single restart also automatically starts MED-V because the MED-V workspace installation places an entry in the RUNKEY.</span></span>

**<span data-ttu-id="d43f1-121">使用软件分发系统部署 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="d43f1-121">To deploy a MED-V workspace by using a software distribution system</span></span>**

1.  <span data-ttu-id="d43f1-122">将电子软件分发系统中的一组计算机和用户定义为计算机/用户的目标组。</span><span class="sxs-lookup"><span data-stu-id="d43f1-122">Define a group of computers and users in the electronic software distribution system as the target set of computers/users.</span></span>

2.  <span data-ttu-id="d43f1-123">为每个需要分发的 Microsoft 安装文件创建程序包。</span><span class="sxs-lookup"><span data-stu-id="d43f1-123">Create packages for each Microsoft installation file that needs to be distributed.</span></span> <span data-ttu-id="d43f1-124">以下是所需的文件和必须安装它们的顺序：</span><span class="sxs-lookup"><span data-stu-id="d43f1-124">The following are the required files and the order in which they must be installed:</span></span>

    1.  <span data-ttu-id="d43f1-125">**Windows 虚拟 PC** -如果尚未安装（需要重启计算机）。</span><span class="sxs-lookup"><span data-stu-id="d43f1-125">**Windows Virtual PC** – if not already installed (a computer restart is required).</span></span> <span data-ttu-id="d43f1-126">有关详细信息，请参阅[配置安装先决条件](configure-installation-prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="d43f1-126">For more information, see [Configure Installation Prerequisites](configure-installation-prerequisites.md).</span></span>

    2.  <span data-ttu-id="d43f1-127">**Windows 虚拟 PC 的添加和更新**-如果尚未安装。</span><span class="sxs-lookup"><span data-stu-id="d43f1-127">**Windows Virtual PC Additions and Updates** – if not already installed.</span></span> <span data-ttu-id="d43f1-128">有关详细信息，请参阅[配置安装先决条件](configure-installation-prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="d43f1-128">For more information, see [Configure Installation Prerequisites](configure-installation-prerequisites.md).</span></span>

    3.  <span data-ttu-id="d43f1-129">**Med-v Host Agent 安装文件**-安装主机代理（med-v \ _HostAgent \ _Setup 安装文件）。</span><span class="sxs-lookup"><span data-stu-id="d43f1-129">**MED-V Host Agent Installation File** – installs the Host Agent (MED-V\_HostAgent\_Setup installation file).</span></span> <span data-ttu-id="d43f1-130">有关详细信息，请参阅[如何手动安装 Med-v 主机代理](how-to-manually-install-the-med-v-host-agent.md)。</span><span class="sxs-lookup"><span data-stu-id="d43f1-130">For more information, see [How to Manually Install the MED-V Host Agent](how-to-manually-install-the-med-v-host-agent.md).</span></span>

        **<span data-ttu-id="d43f1-131">警告</span><span class="sxs-lookup"><span data-stu-id="d43f1-131">Warning</span></span>**  
        <span data-ttu-id="d43f1-132">在安装 MED-V 主机代理之前关闭 Internet Explorer，否则可能会在 URL 重定向中出现冲突。</span><span class="sxs-lookup"><span data-stu-id="d43f1-132">Close Internet Explorer before you install the MED-V Host Agent, otherwise conflicts can occur later with URL redirection.</span></span> <span data-ttu-id="d43f1-133">您也可以通过在分发期间指定计算机重启来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="d43f1-133">You can also do this by specifying a computer restart during a distribution.</span></span>



    4.  <span data-ttu-id="d43f1-134">**Med-v 工作区安装程序、VHD 和安装可执行文件**-在**Med-v 工作区包装**程序中创建。</span><span class="sxs-lookup"><span data-stu-id="d43f1-134">**MED-V Workspace Installer, VHD, and Setup Executable** – created in the **MED-V Workspace Packager**.</span></span> <span data-ttu-id="d43f1-135">有关详细信息，请参阅[创建 Med-v 工作区程序包](create-a-med-v-workspace-package.md)。</span><span class="sxs-lookup"><span data-stu-id="d43f1-135">For more information, see [Create a MED-V Workspace Package](create-a-med-v-workspace-package.md).</span></span>

        **<span data-ttu-id="d43f1-136">重要提示</span><span class="sxs-lookup"><span data-stu-id="d43f1-136">Important</span></span>**  
        <span data-ttu-id="d43f1-137">压缩的虚拟硬盘文件（medv）和设置可执行程序（setup.exe）必须与 MED-V 工作区安装程序位于同一个文件夹中。</span><span class="sxs-lookup"><span data-stu-id="d43f1-137">The compressed virtual hard disk file (.medv) and the Setup executable program (setup.exe) must be in the same folder as the MED-V workspace installer.</span></span> <span data-ttu-id="d43f1-138">然后，通过运行 setup.exe 安装 MED-V 工作区安装程序。</span><span class="sxs-lookup"><span data-stu-id="d43f1-138">Then, install the MED-V workspace installer by running setup.exe.</span></span>



~~~
    **Tip**  
    Because problems can occur when you install MED-V from a network location, we recommend that you copy the MED-V workspace setup files locally and then run setup.exe.
~~~



3. <span data-ttu-id="d43f1-139">将程序包配置为在静默模式下运行（无需用户交互）。</span><span class="sxs-lookup"><span data-stu-id="d43f1-139">Configure the packages to run in silent mode (no user interaction is required).</span></span>

   <span data-ttu-id="d43f1-140">如果在缄默模式下运行，则不会提示关闭 Internet Explorer （如果正在运行）以及启动 MED-V Host Agent 的提示。</span><span class="sxs-lookup"><span data-stu-id="d43f1-140">Running in silent mode eliminates the prompt to close Internet Explorer if it is running and the prompt to start the MED-V Host Agent.</span></span> <span data-ttu-id="d43f1-141">重新启动计算机时，将执行这两项操作。</span><span class="sxs-lookup"><span data-stu-id="d43f1-141">Both actions are performed when the computer is restarted.</span></span>

   **<span data-ttu-id="d43f1-142">注意</span><span class="sxs-lookup"><span data-stu-id="d43f1-142">Note</span></span>**  
   <span data-ttu-id="d43f1-143">安装 Windows 虚拟 PC 需要重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="d43f1-143">Installation of Windows Virtual PC requires you to restart the computer.</span></span> <span data-ttu-id="d43f1-144">如果禁止重启和忽略 MED-V 安装所需的先决条件，则可以创建单个安装过程并同时安装所有组件。</span><span class="sxs-lookup"><span data-stu-id="d43f1-144">You can create a single installation process and install all the components at the same time if you suppress the restart and ignore the prerequisites necessary for MED-V to install.</span></span> <span data-ttu-id="d43f1-145">也可以通过使用命令行参数执行此操作。</span><span class="sxs-lookup"><span data-stu-id="d43f1-145">You can also do this by using command-line arguments.</span></span> <span data-ttu-id="d43f1-146">有关这些参数的示例，请参阅[如何通过电子软件分发系统部署 Med-v 组件](how-to-deploy-the-med-v-components-through-an-electronic-software-distribution-system.md#bkmk-batch)。</span><span class="sxs-lookup"><span data-stu-id="d43f1-146">For an example of these arguments, see [How to Deploy the MED-V Components Through an Electronic Software Distribution System](how-to-deploy-the-med-v-components-through-an-electronic-software-distribution-system.md#bkmk-batch).</span></span> <span data-ttu-id="d43f1-147">当计算机重新启动时，MED-V 会自动启动。</span><span class="sxs-lookup"><span data-stu-id="d43f1-147">MED-V automatically starts when the computer is restarted.</span></span>



4. <span data-ttu-id="d43f1-148">安装 Windows 虚拟电脑之前安装 MED-V 及其组件。</span><span class="sxs-lookup"><span data-stu-id="d43f1-148">Install MED-V and its components before installing Windows Virtual PC.</span></span> <span data-ttu-id="d43f1-149">请参阅本主题后面的批处理文件示例。</span><span class="sxs-lookup"><span data-stu-id="d43f1-149">See the example batch file later in this topic.</span></span>

   **<span data-ttu-id="d43f1-150">重要提示</span><span class="sxs-lookup"><span data-stu-id="d43f1-150">Important</span></span>**  
   <span data-ttu-id="d43f1-151">选择 "**忽略 \ _PREREQUISITES** " 选项（如示例批处理文件中所示），以便可以在必需的 VPC 组件之前安装 med-v 组件。</span><span class="sxs-lookup"><span data-stu-id="d43f1-151">Select the **IGNORE\_PREREQUISITES** option as shown in the example batch file so that the MED-V components can be installed prior to the required VPC components.</span></span> <span data-ttu-id="d43f1-152">按此顺序安装 MED-V 组件以允许单个重启。</span><span class="sxs-lookup"><span data-stu-id="d43f1-152">Install the MED-V components in this order to allow for the single restart.</span></span>



5. <span data-ttu-id="d43f1-153">确定安装和软件分发系统所需的任何其他要求，例如目标平台和可用磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="d43f1-153">Identify any other requirements necessary for the installation and for your software distribution system, such as target platforms and the free disk space.</span></span>

6. <span data-ttu-id="d43f1-154">将程序包分配给计算机/用户的目标组。</span><span class="sxs-lookup"><span data-stu-id="d43f1-154">Assign the packages to the target set of computers/users.</span></span>

   <span data-ttu-id="d43f1-155">当计算机运行时，软件分发系统客户端识别出新的程序包可用并开始按照定义和要求安装程序包。</span><span class="sxs-lookup"><span data-stu-id="d43f1-155">As computers are running, the software distribution system client recognizes that new packages are available and begins to install the packages per the definition and requirements.</span></span> <span data-ttu-id="d43f1-156">安装应以静默顺序运行。</span><span class="sxs-lookup"><span data-stu-id="d43f1-156">The installations should run sequentially in silent.</span></span> <span data-ttu-id="d43f1-157">我们建议以单个进程的形式执行此操作，直到安装所有软件包才需要重启。</span><span class="sxs-lookup"><span data-stu-id="d43f1-157">We recommend that this is performed as a single process that does not require a restart until all the packages are installed.</span></span>

7. <span data-ttu-id="d43f1-158">安装完成后，重新启动已更新的计算机。</span><span class="sxs-lookup"><span data-stu-id="d43f1-158">After the installations are complete, restart the updated computers.</span></span>

   <span data-ttu-id="d43f1-159">根据软件分发系统，你可以计划重启计算机，或者最终用户可以在正常工作期间手动重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="d43f1-159">Depending on the software distribution system, you can schedule a restart of the computer or the end users can restart the computers manually during their regular work.</span></span> <span data-ttu-id="d43f1-160">重新启动计算机后，在最终用户登录后，MED-V 将自动启动。</span><span class="sxs-lookup"><span data-stu-id="d43f1-160">After the computer is restarted, MED-V automatically starts after an end user logs on.</span></span> <span data-ttu-id="d43f1-161">当 MED-V 首次启动时，它将在首次设置时运行。</span><span class="sxs-lookup"><span data-stu-id="d43f1-161">When MED-V starts for the first time, it runs first time setup.</span></span>

<span data-ttu-id="d43f1-162">首次设置启动，可能需要几分钟才能完成，具体取决于你指定的虚拟硬盘的大小以及启动时应用到 MED-V 工作区的策略数。</span><span class="sxs-lookup"><span data-stu-id="d43f1-162">First time setup starts and might take several minutes to finish, depending on the size of the virtual hard disk that you specified and the number of policies applied to the MED-V workspace on startup.</span></span> <span data-ttu-id="d43f1-163">最终用户可以通过在通知区域中观看 MED-V 图标来跟踪进度。</span><span class="sxs-lookup"><span data-stu-id="d43f1-163">The end user can track the progress by watching the MED-V icon in the notification area.</span></span> <span data-ttu-id="d43f1-164">有关首次设置的详细信息，请参阅[med-v 2.0 部署概述](med-v-20-deployment-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="d43f1-164">For more information about first time setup, see [MED-V 2.0 Deployment Overview](med-v-20-deployment-overview.md).</span></span>

**<span data-ttu-id="d43f1-165">使用批处理文件安装 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="d43f1-165">To install the MED-V workspace by using a batch file</span></span>**

1.  <span data-ttu-id="d43f1-166">使用管理凭据在命令提示符处运行安装。</span><span class="sxs-lookup"><span data-stu-id="d43f1-166">Run the installation at a command prompt with administrative credentials.</span></span>

2.  <span data-ttu-id="d43f1-167">将每个组件部署到单个目录。</span><span class="sxs-lookup"><span data-stu-id="d43f1-167">Deploy each component to a single directory.</span></span> <span data-ttu-id="d43f1-168">如果从网络共享运行，解压缩 medv 文件需要较长时间。</span><span class="sxs-lookup"><span data-stu-id="d43f1-168">If run from a network share, a longer time is required to decompress the .medv file.</span></span>

3.  <span data-ttu-id="d43f1-169">最佳做法是指定在 MED-V 主机代理和 MED-V 工作区程序包文件之后安装 Windows 虚拟 PC 和 Windows 虚拟 PC 修补程序。</span><span class="sxs-lookup"><span data-stu-id="d43f1-169">As a best practice, specify that Windows Virtual PC and the Windows Virtual PC hotfix are installed after the MED-V Host Agent and the MED-V workspace package files.</span></span> <span data-ttu-id="d43f1-170">这意味着，Windows 更新不会通过需要重新启动来导致任何与安装过程的干扰。</span><span class="sxs-lookup"><span data-stu-id="d43f1-170">This means that Windows Update will not cause any interference with the installation process by requiring a restart.</span></span>

4.  <span data-ttu-id="d43f1-171">批处理文件完成后重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="d43f1-171">Restart the computer after the batch file is finished.</span></span>

<span data-ttu-id="d43f1-172">重启后，系统会提示用户第一次运行安装并完成 MED-V 的配置。</span><span class="sxs-lookup"><span data-stu-id="d43f1-172">After the restart, the user is prompted to run first time setup and complete the configuration of MED-V.</span></span>

<span data-ttu-id="d43f1-173">以下使用指定参数的示例显示了如何在单个进程中安装64位 MED-V 组件：</span><span class="sxs-lookup"><span data-stu-id="d43f1-173">The following example, with the specified arguments, shows how to install 64-bit MED-V components in a single process:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d43f1-174">参数</span><span class="sxs-lookup"><span data-stu-id="d43f1-174">Argument</span></span></th>
<th align="left"><span data-ttu-id="d43f1-175">描述</span><span class="sxs-lookup"><span data-stu-id="d43f1-175">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d43f1-176">/norestart</span><span class="sxs-lookup"><span data-stu-id="d43f1-176">/norestart</span></span></p></td>
<td align="left"><p><span data-ttu-id="d43f1-177">阻止 Windows 虚拟电脑和 Windows 虚拟 PC 更新的安装重新启动主机计算机。</span><span class="sxs-lookup"><span data-stu-id="d43f1-177">Prevents the installation of Windows Virtual PC and the Windows Virtual PC update from restarting the host computer.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d43f1-178">/quiet</span><span class="sxs-lookup"><span data-stu-id="d43f1-178">/quiet</span></span></p></td>
<td align="left"><p><span data-ttu-id="d43f1-179">无需用户交互即可在安静模式下安装 MED-V 组件。</span><span class="sxs-lookup"><span data-stu-id="d43f1-179">Installs the MED-V components in quiet mode without user interaction.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d43f1-180">/qn</span><span class="sxs-lookup"><span data-stu-id="d43f1-180">/qn</span></span></p></td>
<td align="left"><p><span data-ttu-id="d43f1-181">安装不带用户界面的 MED-V 组件。</span><span class="sxs-lookup"><span data-stu-id="d43f1-181">Installs the MED-V components without a user interface.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d43f1-182">IGNORE_PREREQUISITES</span><span class="sxs-lookup"><span data-stu-id="d43f1-182">IGNORE_PREREQUISITES</span></span></p></td>
<td align="left"><p><span data-ttu-id="d43f1-183">安装而不检查 Windows 虚拟 PC。</span><span class="sxs-lookup"><span data-stu-id="d43f1-183">Installs without checking for Windows Virtual PC.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="d43f1-184">注意</span><span class="sxs-lookup"><span data-stu-id="d43f1-184">Note</span></span></strong><br/><p><span data-ttu-id="d43f1-185">仅当在此安装过程中安装 Windows 虚拟电脑时，才指定此参数。</span><span class="sxs-lookup"><span data-stu-id="d43f1-185">Only specify this argument if you are installing Windows Virtual PC as part of this installation.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d43f1-186">OVERWRITEVHD</span><span class="sxs-lookup"><span data-stu-id="d43f1-186">OVERWRITEVHD</span></span></p></td>
<td align="left"><p><span data-ttu-id="d43f1-187">强制安装 MED-V 工作区并阻止它可能生成的任何提示。</span><span class="sxs-lookup"><span data-stu-id="d43f1-187">Forces the installation of the MED-V workspace and prevents any prompts that it might generate.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="d43f1-188">示例</span><span class="sxs-lookup"><span data-stu-id="d43f1-188">Example</span></span>


``` syntax
:: Install MED-V and the Pre-requisites

:: Install the MED-V Host Agent: install in quiet mode, ignore that Windows Virtual PC is not installed completely, and log results
start /WAIT .\MED-V_HostAgent_Setup.exe /qn IGNORE_PREREQUISITES=1 /l* %TEMP%\MEDVhost.log

:: Install the MED-V Workspace: install in quiet mode, Overwrite the VHD if it already exists, and log results
start /WAIT .\setup.exe /qn OVERWRITEVHD=1 /l* %TEMP%\MEDVworkspace.log

:: Install Windows Virtual PC: install in quiet mode and do not reboot
start /WAIT wusa.exe Windows6.1-KB958559-x64.msu /norestart /quiet

:: Install Windows Virtual PC patch to support non-HAV: install in quiet mode and do not reboot
wusa.exe Windows6.1-KB977206-x64.msu /norestart /quiet

:: After successful installation of the above components, a reboot of the host computer is required to complete installation.
```

## <span data-ttu-id="d43f1-189">相关主题</span><span class="sxs-lookup"><span data-stu-id="d43f1-189">Related topics</span></span>


[<span data-ttu-id="d43f1-190">MED-V 2.0 部署概述</span><span class="sxs-lookup"><span data-stu-id="d43f1-190">MED-V 2.0 Deployment Overview</span></span>](med-v-20-deployment-overview.md)

[<span data-ttu-id="d43f1-191">如何在 Windows 7 映像中部署 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="d43f1-191">How to Deploy a MED-V Workspace in a Windows 7 Image</span></span>](how-to-deploy-a-med-v-workspace-in-a-windows-7-image.md)









