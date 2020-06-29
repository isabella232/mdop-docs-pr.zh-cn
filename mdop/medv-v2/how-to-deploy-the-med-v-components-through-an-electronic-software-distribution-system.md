---
title: 如何通过电子软件分发系统部署 MED-V 组件
description: 如何通过电子软件分发系统部署 MED-V 组件
author: dansimp
ms.assetid: 8a800bdf-6fa4-47b4-b417-df053289d4e8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: d772702c770340796fe770273146bd0308617a69
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803651"
---
# <span data-ttu-id="460d7-103">如何通过电子软件分发系统部署 MED-V 组件</span><span class="sxs-lookup"><span data-stu-id="460d7-103">How to Deploy the MED-V Components Through an Electronic Software Distribution System</span></span>


<span data-ttu-id="460d7-104">电子软件分发系统可帮助你将软件通过慢速或快速网络连接高效地移动到多台计算机。</span><span class="sxs-lookup"><span data-stu-id="460d7-104">An electronic software distribution system can help you efficiently move software to many computers over slow or fast network connections.</span></span> <span data-ttu-id="460d7-105">以下部分提供了可帮助你使用软件分发系统在整个企业中部署 Microsoft 企业桌面虚拟化（MED-V）2.0 组件的信息和说明。</span><span class="sxs-lookup"><span data-stu-id="460d7-105">The following section provides information and instructions to help you deploy the Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 components throughout your enterprise by using a software distribution system.</span></span>

**<span data-ttu-id="460d7-106">注意</span><span class="sxs-lookup"><span data-stu-id="460d7-106">Note</span></span>**  
<span data-ttu-id="460d7-107">无论使用哪种软件分发解决方案，您都必须熟悉特定解决方案的要求。</span><span class="sxs-lookup"><span data-stu-id="460d7-107">Whichever software distribution solution that you use, you must be familiar with the requirements of your particular solution.</span></span> <span data-ttu-id="460d7-108">如果您使用的是 System Center Configuration Manager 2007 R2 或更高版本，请参阅 Microsoft 技术库（）中的[Configuration Manager 文档库](https://go.microsoft.com/fwlink/?LinkId=66999) https://go.microsoft.com/fwlink/?LinkId=66999) 。</span><span class="sxs-lookup"><span data-stu-id="460d7-108">If you are using System Center Configuration Manager 2007 R2 or a later version, see the [Configuration Manager Documentation Library](https://go.microsoft.com/fwlink/?LinkId=66999) in the Microsoft Technical Library (https://go.microsoft.com/fwlink/?LinkId=66999).</span></span>



**<span data-ttu-id="460d7-109">重要提示</span><span class="sxs-lookup"><span data-stu-id="460d7-109">Important</span></span>**  
<span data-ttu-id="460d7-110">如果你使用的是 System Center Configuration Manager 2007 SP2，并且你的 MED-V 工作区配置为在**NAT**模式下运行，则虚拟机将归为基于 Internet 的客户端，并且无法找到要从中下载内容的最近分发点。</span><span class="sxs-lookup"><span data-stu-id="460d7-110">If you are using System Center Configuration Manager 2007 SP2 and your MED-V workspaces are configured to operate in **NAT** mode, the virtual machines are classified as Internet-based clients and cannot find the closest distribution points from which to download content.</span></span>

<span data-ttu-id="460d7-111">[用于改进由 med-v 管理的 vm 的功能的修复程序](https://go.microsoft.com/fwlink/?LinkId=201088)（ https://go.microsoft.com/fwlink/?LinkId=201088) 将新功能添加到由 med-v 托管的虚拟机并配置为在**NAT**模式下运行。</span><span class="sxs-lookup"><span data-stu-id="460d7-111">The [hotfix to improve the functionality for VMs that are managed by MED-V](https://go.microsoft.com/fwlink/?LinkId=201088) (https://go.microsoft.com/fwlink/?LinkId=201088) adds new functionality to virtual machines that are managed by MED-V and that are configured to operate in **NAT** mode.</span></span> <span data-ttu-id="460d7-112">新功能允许虚拟机访问最近的分发点。</span><span class="sxs-lookup"><span data-stu-id="460d7-112">The new functionality lets virtual machines access the closest distribution points.</span></span> <span data-ttu-id="460d7-113">因此，管理员可以采用同样的方式管理虚拟机和主机。</span><span class="sxs-lookup"><span data-stu-id="460d7-113">Therefore, the administrator can manage the virtual machine and the host computer in the same manner.</span></span> <span data-ttu-id="460d7-114">此修补程序必须首先在网站服务器上安装，然后再安装在客户端上。</span><span class="sxs-lookup"><span data-stu-id="460d7-114">This hotfix must be installed first on the site server and then on the client.</span></span>

<span data-ttu-id="460d7-115">该更新已公开提供。</span><span class="sxs-lookup"><span data-stu-id="460d7-115">The update is publicly available.</span></span> <span data-ttu-id="460d7-116">但是，系统可能会提示您接受 Microsoft 服务协议。</span><span class="sxs-lookup"><span data-stu-id="460d7-116">However, you might be prompted to accept an agreement for Microsoft Services.</span></span> <span data-ttu-id="460d7-117">按照后续网页上的提示检索此修补程序。</span><span class="sxs-lookup"><span data-stu-id="460d7-117">Follow the prompts on the successive webpages to retrieve this hotfix.</span></span>



**<span data-ttu-id="460d7-118">注意</span><span class="sxs-lookup"><span data-stu-id="460d7-118">Note</span></span>**  
<span data-ttu-id="460d7-119">必须安装 MED-V 工作区包装程序并构建你的 MED-V 工作区，然后才能通过你的软件分发系统部署 MED-V 组件。</span><span class="sxs-lookup"><span data-stu-id="460d7-119">You must install the MED-V workspace packager and build your MED-V workspaces before you can deploy the MED-V components through your software distribution system.</span></span> <span data-ttu-id="460d7-120">有关如何准备映像和构建 MED-V 工作区的详细信息，请参阅[med-v 的操作](operations-for-med-v.md)。</span><span class="sxs-lookup"><span data-stu-id="460d7-120">For more information about how to prepare an image and to build your MED-V workspaces, see [Operations for MED-V](operations-for-med-v.md).</span></span>



**<span data-ttu-id="460d7-121">使用软件分发系统部署 MED-V 组件</span><span class="sxs-lookup"><span data-stu-id="460d7-121">To deploy the MED-V components by using a software distribution system</span></span>**

1.  <span data-ttu-id="460d7-122">将电子软件分发系统中的一组计算机和用户定义为计算机/用户的目标组。</span><span class="sxs-lookup"><span data-stu-id="460d7-122">Define a group of computers and users in the electronic software distribution system as the target set of computers/users.</span></span>

2.  <span data-ttu-id="460d7-123">为每个需要分发的 Microsoft 安装文件创建程序包。</span><span class="sxs-lookup"><span data-stu-id="460d7-123">Create packages for each Microsoft installation file that needs to be distributed.</span></span> <span data-ttu-id="460d7-124">以下是所需的文件和必须安装它们的顺序：</span><span class="sxs-lookup"><span data-stu-id="460d7-124">The following are the required files and the order in which they must be installed:</span></span>

    1.  <span data-ttu-id="460d7-125">**Windows 虚拟 PC** -如果尚未安装（需要重启计算机）。</span><span class="sxs-lookup"><span data-stu-id="460d7-125">**Windows Virtual PC** – if not already installed (a computer restart is required).</span></span> <span data-ttu-id="460d7-126">有关详细信息，请参阅[配置安装先决条件](configure-installation-prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="460d7-126">For more information, see [Configure Installation Prerequisites](configure-installation-prerequisites.md).</span></span>

    2.  <span data-ttu-id="460d7-127">**Windows 虚拟 PC 的添加和更新**-如果尚未安装。</span><span class="sxs-lookup"><span data-stu-id="460d7-127">**Windows Virtual PC Additions and Updates** – if not already installed.</span></span> <span data-ttu-id="460d7-128">有关详细信息，请参阅[配置安装先决条件](configure-installation-prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="460d7-128">For more information, see [Configure Installation Prerequisites](configure-installation-prerequisites.md).</span></span>

    3.  <span data-ttu-id="460d7-129">**Med-v Host Agent 安装文件**-安装主机代理（med-v \ _HostAgent \ _Setup 安装文件）。</span><span class="sxs-lookup"><span data-stu-id="460d7-129">**MED-V Host Agent Installation File** – installs the Host Agent (MED-V\_HostAgent\_Setup installation file).</span></span> <span data-ttu-id="460d7-130">有关详细信息，请参阅[如何手动安装 Med-v 主机代理](how-to-manually-install-the-med-v-host-agent.md)。</span><span class="sxs-lookup"><span data-stu-id="460d7-130">For more information, see [How to Manually Install the MED-V Host Agent](how-to-manually-install-the-med-v-host-agent.md).</span></span>

        **<span data-ttu-id="460d7-131">警告</span><span class="sxs-lookup"><span data-stu-id="460d7-131">Warning</span></span>**  
        <span data-ttu-id="460d7-132">在安装 MED-V 主机代理之前关闭 Internet Explorer，否则可能会在 URL 重定向中出现冲突。</span><span class="sxs-lookup"><span data-stu-id="460d7-132">Close Internet Explorer before you install the MED-V Host Agent, otherwise conflicts can occur later with URL redirection.</span></span> <span data-ttu-id="460d7-133">您也可以通过在分发期间指定计算机重启来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="460d7-133">You can also do this by specifying a computer restart during a distribution.</span></span>   

    4.  <span data-ttu-id="460d7-134">**Med-v 工作区安装程序、VHD 和安装可执行文件**-在**Med-v 工作区包装**程序中创建。</span><span class="sxs-lookup"><span data-stu-id="460d7-134">**MED-V Workspace Installer, VHD, and Setup Executable** – created in the **MED-V Workspace Packager**.</span></span> <span data-ttu-id="460d7-135">有关详细信息，请参阅[创建 Med-v 工作区程序包](create-a-med-v-workspace-package.md)。</span><span class="sxs-lookup"><span data-stu-id="460d7-135">For more information, see [Create a MED-V Workspace Package](create-a-med-v-workspace-package.md).</span></span>

        **<span data-ttu-id="460d7-136">重要提示</span><span class="sxs-lookup"><span data-stu-id="460d7-136">Important</span></span>**  
        <span data-ttu-id="460d7-137">压缩的虚拟硬盘文件（medv）和设置可执行程序（setup.exe）必须与 MED-V 工作区安装程序位于同一个文件夹中。</span><span class="sxs-lookup"><span data-stu-id="460d7-137">The compressed virtual hard disk file (.medv) and the Setup executable program (setup.exe) must be in the same folder as the MED-V workspace installer.</span></span> <span data-ttu-id="460d7-138">然后，通过运行 setup.exe 安装 MED-V 工作区安装程序。</span><span class="sxs-lookup"><span data-stu-id="460d7-138">Then, install the MED-V workspace installer by running setup.exe.</span></span>

        **<span data-ttu-id="460d7-139">提示</span><span class="sxs-lookup"><span data-stu-id="460d7-139">Tip</span></span>**  
        <span data-ttu-id="460d7-140">由于从网络位置安装 MED-V 时可能出现的问题，我们建议你在本地复制 MED-V 工作区设置文件，然后运行 setup.exe。</span><span class="sxs-lookup"><span data-stu-id="460d7-140">Because problems that can occur when you install MED-V from a network location, we recommend that you copy the MED-V workspace setup files locally and then run setup.exe.</span></span>       

3.  <span data-ttu-id="460d7-141">将程序包配置为在静默模式下运行（无需用户交互）。</span><span class="sxs-lookup"><span data-stu-id="460d7-141">Configure the packages to run in silent mode (no user interaction is required).</span></span>

    <span data-ttu-id="460d7-142">如果在缄默模式下运行，则不会提示关闭 Internet Explorer （如果正在运行）以及启动 MED-V Host Agent 的提示。</span><span class="sxs-lookup"><span data-stu-id="460d7-142">Running in silent mode eliminates the prompt to close Internet Explorer if it is running and the prompt to start the MED-V Host Agent.</span></span> <span data-ttu-id="460d7-143">重新启动计算机时，将执行这两项操作。</span><span class="sxs-lookup"><span data-stu-id="460d7-143">Both actions are performed when the computer is restarted.</span></span>

    **<span data-ttu-id="460d7-144">注意</span><span class="sxs-lookup"><span data-stu-id="460d7-144">Note</span></span>**  
    <span data-ttu-id="460d7-145">安装 Windows 虚拟 PC 需要重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="460d7-145">Installation of Windows Virtual PC requires you to restart the computer.</span></span> <span data-ttu-id="460d7-146">如果禁止重启和忽略 MED-V 安装所需的先决条件，则可以创建单个安装过程并同时安装所有组件。</span><span class="sxs-lookup"><span data-stu-id="460d7-146">You can create a single installation process and install all the components at the same time if you suppress the restart and ignore the prerequisites necessary for MED-V to install.</span></span> <span data-ttu-id="460d7-147">也可以通过使用命令行参数执行此操作。</span><span class="sxs-lookup"><span data-stu-id="460d7-147">You can also do this by using command-line arguments.</span></span> <span data-ttu-id="460d7-148">有关这些参数的示例，请参阅[使用批处理文件安装 med-v 组件](#bkmk-batch)。</span><span class="sxs-lookup"><span data-stu-id="460d7-148">For an example of these arguments, see [To install the MED-V components by using a batch file](#bkmk-batch).</span></span> <span data-ttu-id="460d7-149">当计算机重新启动时，MED-V 会自动启动。</span><span class="sxs-lookup"><span data-stu-id="460d7-149">MED-V automatically starts when the computer is restarted.</span></span>

4.  <span data-ttu-id="460d7-150">安装 Windows 虚拟电脑之前安装 MED-V 及其组件。</span><span class="sxs-lookup"><span data-stu-id="460d7-150">Install MED-V and its components before installing Windows Virtual PC.</span></span> <span data-ttu-id="460d7-151">请参阅本主题后面的批处理文件示例。</span><span class="sxs-lookup"><span data-stu-id="460d7-151">See the example batch file later in this topic.</span></span>

    **<span data-ttu-id="460d7-152">重要提示</span><span class="sxs-lookup"><span data-stu-id="460d7-152">Important</span></span>**  
    <span data-ttu-id="460d7-153">选择 "**忽略 \ _PREREQUISITES** " 选项（如示例批处理文件中所示），以便可以在必需的 VPC 组件之前安装 med-v 组件。</span><span class="sxs-lookup"><span data-stu-id="460d7-153">Select the **IGNORE\_PREREQUISITES** option as shown in the example batch file so that the MED-V components can be installed prior to the required VPC components.</span></span> <span data-ttu-id="460d7-154">按此顺序安装 MED-V 组件以允许单个重启。</span><span class="sxs-lookup"><span data-stu-id="460d7-154">Install the MED-V components in this order to allow for the single restart.</span></span>

5.  <span data-ttu-id="460d7-155">确定安装和软件分发系统所需的任何其他要求，例如目标平台和可用磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="460d7-155">Identify any other requirements necessary for the installation and for your software distribution system, such as target platforms and the free disk space.</span></span>

6.  <span data-ttu-id="460d7-156">将程序包分配给计算机/用户的目标组。</span><span class="sxs-lookup"><span data-stu-id="460d7-156">Assign the packages to the target set of computers/users.</span></span>

    <span data-ttu-id="460d7-157">当计算机运行时，软件分发系统客户端识别出新的程序包可用并开始按照定义和要求安装程序包。</span><span class="sxs-lookup"><span data-stu-id="460d7-157">As computers are running, the software distribution system client recognizes that new packages are available and begins to install the packages per the definition and requirements.</span></span> <span data-ttu-id="460d7-158">安装应按静默模式运行。</span><span class="sxs-lookup"><span data-stu-id="460d7-158">The installations should run sequentially in silent mode.</span></span> <span data-ttu-id="460d7-159">我们建议以单个进程的形式执行此操作，直到安装所有软件包才需要重启。</span><span class="sxs-lookup"><span data-stu-id="460d7-159">We recommend that this is performed as a single process that does not require a restart until all the packages are installed.</span></span>

7.  <span data-ttu-id="460d7-160">安装完成后，重新启动已更新的计算机。</span><span class="sxs-lookup"><span data-stu-id="460d7-160">After the installations are complete, restart the updated computers.</span></span>

    <span data-ttu-id="460d7-161">根据软件分发系统，你可以计划重启计算机，或者最终用户可以在正常工作期间手动重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="460d7-161">Depending on the software distribution system, you can schedule a restart of the computer or the end users can restart the computers manually during their regular work.</span></span> <span data-ttu-id="460d7-162">重新启动计算机后，在最终用户登录后，MED-V 将自动启动。</span><span class="sxs-lookup"><span data-stu-id="460d7-162">After the computer is restarted, MED-V automatically starts after an end user logs on.</span></span> <span data-ttu-id="460d7-163">当 MED-V 首次启动时，它将在首次设置时运行。</span><span class="sxs-lookup"><span data-stu-id="460d7-163">When MED-V starts for the first time, it runs first time setup.</span></span>

<span data-ttu-id="460d7-164">首次设置启动，可能需要几分钟才能完成，具体取决于你指定的虚拟硬盘的大小以及启动时应用到 MED-V 工作区的策略数。</span><span class="sxs-lookup"><span data-stu-id="460d7-164">First time setup starts and might take several minutes to finish, depending on the size of the virtual hard disk that you specified and the number of policies applied to the MED-V workspace on startup.</span></span> <span data-ttu-id="460d7-165">最终用户可以通过在通知区域中观看 MED-V 图标来跟踪进度。</span><span class="sxs-lookup"><span data-stu-id="460d7-165">The end user can track the progress by watching the MED-V icon in the notification area.</span></span> <span data-ttu-id="460d7-166">有关首次设置的详细信息，请参阅[med-v 2.0 部署概述](med-v-20-deployment-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="460d7-166">For more information about first time setup, see [MED-V 2.0 Deployment Overview](med-v-20-deployment-overview.md).</span></span>

<a href="" id="bkmk-batch"></a>**<span data-ttu-id="460d7-167">使用批处理文件安装 MED-V 组件</span><span class="sxs-lookup"><span data-stu-id="460d7-167">To install the MED-V components by using a batch file</span></span>**

1.  <span data-ttu-id="460d7-168">使用管理凭据在命令提示符处运行安装。</span><span class="sxs-lookup"><span data-stu-id="460d7-168">Run the installation at a command prompt with administrative credentials.</span></span>

2.  <span data-ttu-id="460d7-169">将每个组件部署到单个目录。</span><span class="sxs-lookup"><span data-stu-id="460d7-169">Deploy each component to a single directory.</span></span> <span data-ttu-id="460d7-170">如果从网络共享运行，解压缩 medv 文件需要较长时间。</span><span class="sxs-lookup"><span data-stu-id="460d7-170">If run from a network share, a longer time is required to decompress the .medv file.</span></span>

3.  <span data-ttu-id="460d7-171">最佳做法是指定在 MED-V 主机代理和 MED-V 工作区程序包文件之后安装 Windows 虚拟 PC 和 Windows 虚拟 PC 修补程序。</span><span class="sxs-lookup"><span data-stu-id="460d7-171">As a best practice, specify that Windows Virtual PC and the Windows Virtual PC hotfix are installed after the MED-V Host Agent and the MED-V workspace package files.</span></span> <span data-ttu-id="460d7-172">这意味着，Windows 更新不会通过需要重新启动来导致任何与安装过程的干扰。</span><span class="sxs-lookup"><span data-stu-id="460d7-172">This means that Windows Update will not cause any interference with the installation process by requiring a restart.</span></span>

4.  <span data-ttu-id="460d7-173">批处理文件完成后重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="460d7-173">Restart the computer after the batch file is finished.</span></span>

<span data-ttu-id="460d7-174">重启后，系统会提示用户第一次运行安装并完成 MED-V 的配置。</span><span class="sxs-lookup"><span data-stu-id="460d7-174">After the restart, the user is prompted to run first time setup and complete the configuration of MED-V.</span></span>

<span data-ttu-id="460d7-175">以下使用指定参数的示例显示了如何在单个进程中安装64位 MED-V 组件：</span><span class="sxs-lookup"><span data-stu-id="460d7-175">The following example, with the specified arguments, shows how to install 64-bit MED-V components in a single process:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="460d7-176">参数</span><span class="sxs-lookup"><span data-stu-id="460d7-176">Argument</span></span></th>
<th align="left"><span data-ttu-id="460d7-177">描述</span><span class="sxs-lookup"><span data-stu-id="460d7-177">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="460d7-178">/norestart</span><span class="sxs-lookup"><span data-stu-id="460d7-178">/norestart</span></span></p></td>
<td align="left"><p><span data-ttu-id="460d7-179">阻止 Windows 虚拟电脑和 Windows 虚拟 PC 更新的安装重新启动主机计算机。</span><span class="sxs-lookup"><span data-stu-id="460d7-179">Prevents the installation of Windows Virtual PC and the Windows Virtual PC update from restarting the host computer.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="460d7-180">/quiet</span><span class="sxs-lookup"><span data-stu-id="460d7-180">/quiet</span></span></p></td>
<td align="left"><p><span data-ttu-id="460d7-181">无需用户交互即可在安静模式下安装 MED-V 组件。</span><span class="sxs-lookup"><span data-stu-id="460d7-181">Installs the MED-V components in quiet mode without user interaction.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="460d7-182">/qn</span><span class="sxs-lookup"><span data-stu-id="460d7-182">/qn</span></span></p></td>
<td align="left"><p><span data-ttu-id="460d7-183">安装不带用户界面的 MED-V 组件。</span><span class="sxs-lookup"><span data-stu-id="460d7-183">Installs the MED-V components without a user interface.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="460d7-184">IGNORE_PREREQUISITES</span><span class="sxs-lookup"><span data-stu-id="460d7-184">IGNORE_PREREQUISITES</span></span></p></td>
<td align="left"><p><span data-ttu-id="460d7-185">安装而不检查 Windows 虚拟 PC。</span><span class="sxs-lookup"><span data-stu-id="460d7-185">Installs without checking for Windows Virtual PC.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="460d7-186">注意</span><span class="sxs-lookup"><span data-stu-id="460d7-186">Note</span></span></strong><br/><p><span data-ttu-id="460d7-187">仅当在此安装过程中安装 Windows 虚拟电脑时，才指定此参数。</span><span class="sxs-lookup"><span data-stu-id="460d7-187">Only specify this argument if you are installing Windows Virtual PC as part of this installation.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="460d7-188">OVERWRITEVHD</span><span class="sxs-lookup"><span data-stu-id="460d7-188">OVERWRITEVHD</span></span></p></td>
<td align="left"><p><span data-ttu-id="460d7-189">强制安装 MED-V 工作区并阻止它可能生成的任何提示。</span><span class="sxs-lookup"><span data-stu-id="460d7-189">Forces the installation of the MED-V workspace and prevents any prompts that it might generate.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="460d7-190">示例</span><span class="sxs-lookup"><span data-stu-id="460d7-190">Example</span></span>


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

## <span data-ttu-id="460d7-191">相关主题</span><span class="sxs-lookup"><span data-stu-id="460d7-191">Related topics</span></span>


[<span data-ttu-id="460d7-192">MED-V 2.0 部署概述</span><span class="sxs-lookup"><span data-stu-id="460d7-192">MED-V 2.0 Deployment Overview</span></span>](med-v-20-deployment-overview.md)

[<span data-ttu-id="460d7-193">部署 MED-V 组件</span><span class="sxs-lookup"><span data-stu-id="460d7-193">Deploy the MED-V Components</span></span>](deploy-the-med-v-components.md)









