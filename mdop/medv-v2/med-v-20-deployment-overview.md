---
title: MED-V 2.0 部署概述
description: MED-V 2.0 部署概述
author: dansimp
ms.assetid: 0b8998ea-c46f-4c81-a304-f380b2ed7cf8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ec2a5f86ac7d63295bd7c550bcb0a90004987e42
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803902"
---
# <span data-ttu-id="31318-103">MED-V 2.0 部署概述</span><span class="sxs-lookup"><span data-stu-id="31318-103">MED-V 2.0 Deployment Overview</span></span>


<span data-ttu-id="31318-104">本部分提供有关如何安装和部署 Microsoft 企业版桌面虚拟化（MED-V）2.0 的一般信息和说明。</span><span class="sxs-lookup"><span data-stu-id="31318-104">This section provides general information and instructions about how to install and deploy Microsoft Enterprise Desktop Virtualization (MED-V) 2.0.</span></span>

## <span data-ttu-id="31318-105">概述</span><span class="sxs-lookup"><span data-stu-id="31318-105">Overview</span></span>


<span data-ttu-id="31318-106">MED-V 2.0 基于应用程序模型，您用于部署应用程序的相同方法可用于部署和管理 MED-V。</span><span class="sxs-lookup"><span data-stu-id="31318-106">MED-V 2.0 is based on an application model, where the same methods that you use to deploy applications can be used to deploy and manage MED-V.</span></span> <span data-ttu-id="31318-107">已部署的 MED-V 解决方案包括两个组件： MED-V 主机代理和来宾代理。</span><span class="sxs-lookup"><span data-stu-id="31318-107">A deployed MED-V solution includes two components: the MED-V Host Agent and Guest Agent.</span></span> <span data-ttu-id="31318-108">MED-V 主机代理安装在 Windows 7 桌面版上，而 MED-V 来宾代理安装在 MED-V 工作区内部的 Windows XP 中。</span><span class="sxs-lookup"><span data-stu-id="31318-108">The MED-V Host Agent is installed on the Windows 7 desktop and the MED-V Guest Agent is installed on Windows XP inside the MED-V workspace.</span></span> <span data-ttu-id="31318-109">MED-V 还包括一个 MED-V 工作区包装程序，该包装程序提供创建和配置 MED-V 工作区所需的信息和工具。</span><span class="sxs-lookup"><span data-stu-id="31318-109">MED-V also includes a MED-V Workspace Packager that provides the information and tools necessary for creating and configuring MED-V workspaces.</span></span>

**<span data-ttu-id="31318-110">重要提示</span><span class="sxs-lookup"><span data-stu-id="31318-110">Important</span></span>**  
<span data-ttu-id="31318-111">MED-V 仅支持安装用于所有用户的 MED-V 工作区包装程序、MED-V 主机代理和 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="31318-111">MED-V only supports the installation of the MED-V Workspace Packager, the MED-V Host Agent, and the MED-V workspace for all users.</span></span> <span data-ttu-id="31318-112">仅通过选择**ALLUSERS = ""** 来为当前用户安装 med-v 会导致在组件安装和 med-v 工作区的设置中出现故障。</span><span class="sxs-lookup"><span data-stu-id="31318-112">Installing MED-V for the current user only by selecting **ALLUSERS=””** causes failures in the installation of the components and in the setup of the MED-V workspace.</span></span>



### <span data-ttu-id="31318-113">MED-V 安装文件</span><span class="sxs-lookup"><span data-stu-id="31318-113">The MED-V Installation Files</span></span>

<span data-ttu-id="31318-114">MED-V 包括运行 MED-V 所需的以下安装文件：</span><span class="sxs-lookup"><span data-stu-id="31318-114">MED-V includes the following installation files, required for running MED-V:</span></span>

**<span data-ttu-id="31318-115">MED-V 主机代理安装文件</span><span class="sxs-lookup"><span data-stu-id="31318-115">The MED-V Host Agent Installation File</span></span>**

<span data-ttu-id="31318-116">Host Agent 安装文件命名为 "MED-V\_HostAgent\_Setup.exe"。</span><span class="sxs-lookup"><span data-stu-id="31318-116">The Host Agent installation file is named MED-V\_HostAgent\_Setup.exe.</span></span> <span data-ttu-id="31318-117">此文件作为 MED-V 的企业内部部署的一部分，在每个相关的最终用户计算机上分发和安装。</span><span class="sxs-lookup"><span data-stu-id="31318-117">This file is distributed and installed on each relevant end-user computer as part of your enterprise-wide deployment of MED-V.</span></span>

**<span data-ttu-id="31318-118">MED-V 工作区包装程序安装文件</span><span class="sxs-lookup"><span data-stu-id="31318-118">The MED-V Workspace Packager Installation File</span></span>**

<span data-ttu-id="31318-119">MED-V 工作区包装程序安装文件命名为 "MED-V\_WorkspacePackager\_Setup.exe"。</span><span class="sxs-lookup"><span data-stu-id="31318-119">The MED-V Workspace Packager installation file is named MED-V\_WorkspacePackager\_Setup.exe.</span></span> <span data-ttu-id="31318-120">使用此文件在具有管理员权限的计算机上安装 MED-V 工作区包装程序。</span><span class="sxs-lookup"><span data-stu-id="31318-120">Use this file to install the MED-V Workspace Packager on a computer where you have administrator rights and permissions.</span></span> <span data-ttu-id="31318-121">桌面管理员使用 MED-V 工作区包装程序来创建和管理 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="31318-121">The desktop administrator uses the MED-V Workspace Packager to create and manage MED-V workspaces.</span></span>

**<span data-ttu-id="31318-122">注意</span><span class="sxs-lookup"><span data-stu-id="31318-122">Note</span></span>**  
<span data-ttu-id="31318-123">MED-V 来宾代理将在首次设置时自动安装。</span><span class="sxs-lookup"><span data-stu-id="31318-123">The MED-V Guest Agent is installed automatically during first time setup.</span></span>



### <span data-ttu-id="31318-124">MED-V 部署过程</span><span class="sxs-lookup"><span data-stu-id="31318-124">The MED-V Deployment Process</span></span>

<span data-ttu-id="31318-125">以下是 MED-V 安装和部署过程的高级概述：</span><span class="sxs-lookup"><span data-stu-id="31318-125">The following is a high-level overview of the MED-V installation and deployment process:</span></span>

1.  <span data-ttu-id="31318-126">在具有管理凭据且将用于构建 MED-V 工作区程序包的计算机上安装 MED-V 工作区包装程序。</span><span class="sxs-lookup"><span data-stu-id="31318-126">Install the MED-V Workspace Packager on the computer where you have administrative credentials and that you will be using to build the MED-V workspace packages.</span></span> <span data-ttu-id="31318-127">有关详细信息，请参阅[如何安装 Med-v 工作区包装程序](how-to-install-the-med-v-workspace-packager.md)。</span><span class="sxs-lookup"><span data-stu-id="31318-127">For more information, see [How to Install the MED-V Workspace Packager](how-to-install-the-med-v-workspace-packager.md).</span></span>

2.  <span data-ttu-id="31318-128">使用 MED-V 工作区包装器准备 MED-V 映像并创建 MED-V 工作区程序包。</span><span class="sxs-lookup"><span data-stu-id="31318-128">Prepare your MED-V image and create your MED-V workspace packages by using the MED-V Workspace Packager.</span></span> <span data-ttu-id="31318-129">有关详细信息，请参阅[med-v 的操作](operations-for-med-v.md)。</span><span class="sxs-lookup"><span data-stu-id="31318-129">For more information, see [Operations for MED-V](operations-for-med-v.md).</span></span>

3.  <span data-ttu-id="31318-130">在整个企业中部署所需的 MED-V 组件。</span><span class="sxs-lookup"><span data-stu-id="31318-130">Deploy the required MED-V components throughout your enterprise.</span></span> <span data-ttu-id="31318-131">MED-V 的必需组件是 Windows Virtual PC、MED-V 主机代理和 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="31318-131">The required components of MED-V are Windows Virtual PC, the MED-V Host Agent, and the MED-V workspace.</span></span>

**<span data-ttu-id="31318-132">重要提示</span><span class="sxs-lookup"><span data-stu-id="31318-132">Important</span></span>**  
<span data-ttu-id="31318-133">安装 MED-V 组件需要管理凭据。</span><span class="sxs-lookup"><span data-stu-id="31318-133">Installation of the MED-V components requires administrative credentials.</span></span> <span data-ttu-id="31318-134">如果最终用户正在安装 MED-V，系统将提示他们输入管理凭据。</span><span class="sxs-lookup"><span data-stu-id="31318-134">If an end user is installing MED-V, they are prompted to enter administrative credentials.</span></span> <span data-ttu-id="31318-135">或者，如果你使用电子软件分发（ESD）系统进行安装，则可以在上下文中提供管理凭据。</span><span class="sxs-lookup"><span data-stu-id="31318-135">Alternately, administrative credentials can be provided in context if you are installing by using an electronic software distribution (ESD) system.</span></span>



### <span data-ttu-id="31318-136">MED-V 组件</span><span class="sxs-lookup"><span data-stu-id="31318-136">The MED-V Components</span></span>

<span data-ttu-id="31318-137">在整个企业中部署的 MED-V 组件由以下部分组成：</span><span class="sxs-lookup"><span data-stu-id="31318-137">The MED-V components that you deploy throughout your enterprise consist of the following:</span></span>

**<span data-ttu-id="31318-138">Windows 虚拟电脑</span><span class="sxs-lookup"><span data-stu-id="31318-138">Windows Virtual PC</span></span>**

<span data-ttu-id="31318-139">Windows 虚拟 PC 映像内用于兼容性解决方案的 MED-V 函数。</span><span class="sxs-lookup"><span data-stu-id="31318-139">MED-V functions inside Windows Virtual PC images for its compatibility solution.</span></span> <span data-ttu-id="31318-140">需要 windows 虚拟 PC 和适用于 Windows 7 的更新（KB977206）。</span><span class="sxs-lookup"><span data-stu-id="31318-140">Windows Virtual PC and the update for Windows 7 (KB977206) are required.</span></span> <span data-ttu-id="31318-141">有关详细信息，请参阅[配置安装先决条件](configure-installation-prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="31318-141">For more information, see [Configure Installation Prerequisites](configure-installation-prerequisites.md).</span></span>

**<span data-ttu-id="31318-142">MED-V 主机代理安装文件</span><span class="sxs-lookup"><span data-stu-id="31318-142">The MED-V Host Agent Installation File</span></span>**

<span data-ttu-id="31318-143">MED-V\_HostAgent\_Setup.exe。</span><span class="sxs-lookup"><span data-stu-id="31318-143">MED-V\_HostAgent\_Setup.exe.</span></span>

**<span data-ttu-id="31318-144">MED-V 工作区安装文件</span><span class="sxs-lookup"><span data-stu-id="31318-144">The MED-V Workspace Installation Files</span></span>**

<span data-ttu-id="31318-145">在构建由以下内容组成的 MED-V 工作区程序包时，将创建 MED-V 工作区安装文件：</span><span class="sxs-lookup"><span data-stu-id="31318-145">The MED-V workspace installation files are created when you build your MED-V workspace package that consists of the following:</span></span>

<span data-ttu-id="31318-146">执行 MED-V 工作区安装的 setup.exe 可执行程序</span><span class="sxs-lookup"><span data-stu-id="31318-146">A setup.exe executable program that executes the MED-V workspace installation</span></span>

<span data-ttu-id="31318-147">&lt;Med-v \ _workspace \ _name &gt; .msi 安装程序</span><span class="sxs-lookup"><span data-stu-id="31318-147">A &lt;MED-V\_workspace\_name&gt;.msi installer</span></span>

<span data-ttu-id="31318-148">&lt;VHD \ _filename &gt; medv 文件，它是压缩的虚拟硬盘</span><span class="sxs-lookup"><span data-stu-id="31318-148">A &lt;VHD\_filename&gt;.medv file, which is the compressed virtual hard disk</span></span>

<span data-ttu-id="31318-149">用于配置设置的文件（ &lt; 工作区 \ _name &gt; .reg 和 &lt; 工作区 \ _name &gt; ps1）</span><span class="sxs-lookup"><span data-stu-id="31318-149">The files for configuration settings (&lt;workspace\_name&gt;.reg and &lt;workspace\_name&gt;.ps1)</span></span>

<span data-ttu-id="31318-150">若要部署 MED-V，请将所有所需的安装文件复制到主计算机或主机可访问的共享。</span><span class="sxs-lookup"><span data-stu-id="31318-150">To deploy MED-V, copy all the required installation files to the host computer or to a share that can be accessed by the host computer.</span></span> <span data-ttu-id="31318-151">运行 Windows Virtual PC、MED-V 主机代理和 MED-V 工作区的组件安装文件。</span><span class="sxs-lookup"><span data-stu-id="31318-151">Run the component installation files for Windows Virtual PC, the MED-V Host Agent, and the MED-V workspace.</span></span> <span data-ttu-id="31318-152">然后启动 MED-V 主机代理以在第一次安装 MED-V 时完成。</span><span class="sxs-lookup"><span data-stu-id="31318-152">Then start the MED-V Host Agent to complete the first time setup of MED-V.</span></span>

<span data-ttu-id="31318-153">你可以手动执行安装。</span><span class="sxs-lookup"><span data-stu-id="31318-153">You can perform the installation manually.</span></span> <span data-ttu-id="31318-154">但是，我们建议你使用电子软件分发方法自动部署组件。</span><span class="sxs-lookup"><span data-stu-id="31318-154">However, we recommend that you use an electronic software distribution method to automate the deployment of the components.</span></span> <span data-ttu-id="31318-155">有关详细信息，请参阅[如何通过电子软件分发系统部署 Med-v 工作区](how-to-deploy-a-med-v-workspace-through-an-electronic-software-distribution-system.md)。</span><span class="sxs-lookup"><span data-stu-id="31318-155">For more information, see [How to Deploy a MED-V Workspace Through an Electronic Software Distribution System](how-to-deploy-a-med-v-workspace-through-an-electronic-software-distribution-system.md).</span></span>

**<span data-ttu-id="31318-156">注意</span><span class="sxs-lookup"><span data-stu-id="31318-156">Note</span></span>**  
<span data-ttu-id="31318-157">有关控制安装选项的可用命令行参数的信息，请参阅[Med-v 安装文件的命令行选项](command-line-options-for-med-v-installation-files.md)。</span><span class="sxs-lookup"><span data-stu-id="31318-157">For information about available command-line arguments to control install options, see [Command-Line Options for MED-V Installation Files](command-line-options-for-med-v-installation-files.md).</span></span>



## <span data-ttu-id="31318-158">部署步骤</span><span class="sxs-lookup"><span data-stu-id="31318-158">Deployment Steps</span></span>


<span data-ttu-id="31318-159">在整个企业中部署 MED-V 时，有两个主要注意事项： "安装" 和 "首次设置"。</span><span class="sxs-lookup"><span data-stu-id="31318-159">When you deploy MED-V throughout your enterprise, there are two main considerations: installation and first time setup.</span></span>

### <span data-ttu-id="31318-160">安装</span><span class="sxs-lookup"><span data-stu-id="31318-160">Installation</span></span>

1.  <span data-ttu-id="31318-161">**Windows 虚拟电脑**-在安装期间，WINDOWS 虚拟 PC 的 med-v 检查及其所需的 windows 7 更新（KB977206）。</span><span class="sxs-lookup"><span data-stu-id="31318-161">**Windows Virtual PC** - During installation, MED-V checks for Windows Virtual PC and its required update for Windows 7 (KB977206).</span></span> <span data-ttu-id="31318-162">有关详细信息，请参阅[配置安装先决条件](configure-installation-prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="31318-162">For more information, see [Configure Installation Prerequisites](configure-installation-prerequisites.md).</span></span>

    <span data-ttu-id="31318-163">你可以在安装 MED-V 之前将它们安装为 Windows 7 安装的一部分，也可以将其安装为 MED-V 分发的一部分。</span><span class="sxs-lookup"><span data-stu-id="31318-163">You can install these as part of the Windows 7 installations before you install MED-V, or you can install them as part of the MED-V distribution.</span></span> <span data-ttu-id="31318-164">但是，MED-V 不包括其部署的机制;必须使用电子软件分发（ESD）系统或作为 Windows 7 映像的一部分来部署它们。</span><span class="sxs-lookup"><span data-stu-id="31318-164">However, MED-V does not include a mechanism for their deployment; they must be deployed by using an electronic software distribution (ESD) system or as part of the Windows 7 image.</span></span>

    **<span data-ttu-id="31318-165">重要提示</span><span class="sxs-lookup"><span data-stu-id="31318-165">Important</span></span>**  
    <span data-ttu-id="31318-166">在使用批处理文件安装 MED-V 组件时，最佳做法是指定在 MED-V 主机代理和 MED-V 工作区程序包文件之后安装 Windows 虚拟 PC 和 Windows 虚拟 PC 修补程序。</span><span class="sxs-lookup"><span data-stu-id="31318-166">When you install the MED-V components by using a batch file, a best practice is to specify that Windows Virtual PC and the Windows Virtual PC hotfix are installed after the MED-V Host Agent and the MED-V workspace package files.</span></span> <span data-ttu-id="31318-167">这意味着，Windows 更新不会通过需要重新启动来导致任何与安装过程的干扰。</span><span class="sxs-lookup"><span data-stu-id="31318-167">This means that Windows Update will not cause any interference with the installation process by requiring a restart.</span></span>



~~~
**Note**  
After you install Windows Virtual PC, the computer must be restarted.
~~~



2. <span data-ttu-id="31318-168">**Med-v 主机代理**-在将运行 Med-v 的 Windows 7 计算机上安装 Med-v 主机代理。</span><span class="sxs-lookup"><span data-stu-id="31318-168">**MED-V Host Agent** – Install the MED-V Host Agent on the Windows 7 computer where MED-V will be run.</span></span> <span data-ttu-id="31318-169">必须先安装此功能，然后才能安装 MED-V 工作区并进行检查以确保已安装 Windows 虚拟 PC。</span><span class="sxs-lookup"><span data-stu-id="31318-169">This must be installed before installing the MED-V workspace and checks to make sure that Windows Virtual PC is installed.</span></span>

3. <span data-ttu-id="31318-170">**Med-v 工作区**-通过使用 Med-v 工作区包装器创建在此安装中所需的文件： setup.exe、medv 和 .msi 文件。</span><span class="sxs-lookup"><span data-stu-id="31318-170">**MED-V workspace** – You create the files that are required in this installation by using the MED-V Workspace Packager: the setup.exe, .medv, and .msi files.</span></span> <span data-ttu-id="31318-171">若要安装 MED-V 工作区，请运行 setup.exe;这会根据需要触发其他文件。</span><span class="sxs-lookup"><span data-stu-id="31318-171">To install the MED-V workspace, run setup.exe; this triggers the other files as required.</span></span> <span data-ttu-id="31318-172">安装会将注册表中的一个条目放入本地计算机运行键，以启动 MED-V 主机代理，该代理在 Windows 启动时始终运行 MED-V。</span><span class="sxs-lookup"><span data-stu-id="31318-172">The installation places an entry in the registry under the local machine run key to start the MED-V Host Agent, which always runs MED-V when Windows is started.</span></span>

   **<span data-ttu-id="31318-173">重要提示</span><span class="sxs-lookup"><span data-stu-id="31318-173">Important</span></span>**  
   <span data-ttu-id="31318-174">MED-V 工作区的安装可由最终用户以交互方式运行或通过电子软件分发系统进行自动运行。</span><span class="sxs-lookup"><span data-stu-id="31318-174">The installation of the MED-V workspace can be run interactively by the end user or silently through an electronic software distribution system.</span></span> <span data-ttu-id="31318-175">安装 MED-V 工作区需要管理凭据，因此最终用户必须是其计算机的管理员才能安装 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="31318-175">Installation of the MED-V workspace requires administrative credentials, so end users must be administrators of their computers to install the MED-V workspace.</span></span> <span data-ttu-id="31318-176">或者，电子软件分发系统通常在系统上下文中运行，并且具有足够的权限。</span><span class="sxs-lookup"><span data-stu-id="31318-176">Alternately, an electronic software distribution system typically runs in the system context and has sufficient permissions.</span></span>



~~~
**Tip**  
Because of problems that can occur when you install MED-V from a network location, we recommend that you copy the MED-V workspace setup files locally and then run setup.exe.
~~~



### <span data-ttu-id="31318-177">首次设置</span><span class="sxs-lookup"><span data-stu-id="31318-177">First Time Setup</span></span>

<span data-ttu-id="31318-178">安装 MED-V 并安装其所需组件后，必须配置 MED-V。</span><span class="sxs-lookup"><span data-stu-id="31318-178">After MED-V and its required components are installed, MED-V must be configured.</span></span> <span data-ttu-id="31318-179">MED-V 的配置称为 "首次设置"。</span><span class="sxs-lookup"><span data-stu-id="31318-179">The configuration of MED-V is known as first time setup.</span></span> <span data-ttu-id="31318-180">通过使用**Med-v 工作区包装**程序，你可以将首次设置配置为以静默方式或交互方式运行。</span><span class="sxs-lookup"><span data-stu-id="31318-180">By using the **MED-V Workspace Packager**, you can configure first time setup to run silently or interactively.</span></span> <span data-ttu-id="31318-181">第一次设置 MED-V 需要最终用户输入其密码才能对 MED-V 工作区进行身份验证，但在其他情况下，用户几乎看不到它们。</span><span class="sxs-lookup"><span data-stu-id="31318-181">First time setup of MED-V requires end users to enter their password to authenticate to the MED-V workspace, but otherwise can be almost invisible to the user.</span></span> <span data-ttu-id="31318-182">通知区域中显示通知，如首次设置完成且应用程序已准备就绪。</span><span class="sxs-lookup"><span data-stu-id="31318-182">Notifications are shown in the notification area, such as when first time setup is complete and applications are ready.</span></span> <span data-ttu-id="31318-183">以下是第一次安装 MED-V 时发生的操作：</span><span class="sxs-lookup"><span data-stu-id="31318-183">The following are the actions that occur during first time setup of MED-V:</span></span>

1.  <span data-ttu-id="31318-184">必须配置虚拟硬盘。</span><span class="sxs-lookup"><span data-stu-id="31318-184">The virtual hard disk must be configured.</span></span> <span data-ttu-id="31318-185">"最小化安装" 运行并扩展 Windows XP 映像。</span><span class="sxs-lookup"><span data-stu-id="31318-185">Mini-Setup runs and expands the Windows XP image.</span></span> <span data-ttu-id="31318-186">通常，这发生在隐藏窗口中，但 MED-V 可以配置为在此配置期间显示。</span><span class="sxs-lookup"><span data-stu-id="31318-186">Typically, this occurs in a hidden window, but MED-V can be configured to display during this configuration.</span></span>

2.  <span data-ttu-id="31318-187">在 "最小化安装" 完成后，你可以运行你必须具有的命令以进行其他配置（如安装 ESD 软件或其他应用程序）或配置映像。</span><span class="sxs-lookup"><span data-stu-id="31318-187">After Mini-Setup finishes, you can run commands that you must have for additional configuration, such as installing ESD software or other applications, or configuring the image.</span></span> <span data-ttu-id="31318-188">这些可在 Sysprep.inf 文件中调用，但不是必需的。</span><span class="sxs-lookup"><span data-stu-id="31318-188">These can be called in the Sysprep.inf file, but are not required there.</span></span> <span data-ttu-id="31318-189">有关详细信息，请参阅[配置适用于 med-v 的 Windows 虚拟 PC 映像](configuring-a-windows-virtual-pc-image-for-med-v.md)。</span><span class="sxs-lookup"><span data-stu-id="31318-189">For more information, see [Configuring a Windows Virtual PC Image for MED-V](configuring-a-windows-virtual-pc-image-for-med-v.md).</span></span>

3.  <span data-ttu-id="31318-190">Ftscompletion.exe 作为配置中的最后一个步骤运行。</span><span class="sxs-lookup"><span data-stu-id="31318-190">Ftscompletion.exe is run as the last step in configuration.</span></span> <span data-ttu-id="31318-191">此过程完成 MED-V 配置，将用户添加到 RDP 组，使其可以访问 MED-V 工作区、复制日志、向 MED-V 工作区准备就绪，然后重新启动 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="31318-191">This process completes the MED-V configuration, adds the user to the RDP group to let them access the MED-V workspace, copies logs, signals MED-V that the MED-V workspace is ready, and then restarts the MED-V workspace.</span></span> <span data-ttu-id="31318-192">如果在创建 MED-V 工作区时配置此过程，此过程还可以将用户添加为 MED-V 工作区的管理员。</span><span class="sxs-lookup"><span data-stu-id="31318-192">This process can also add the user as an administrator of the MED-V workspace if this was configured when the MED-V workspace was created.</span></span> <span data-ttu-id="31318-193">Ftscompletion.exe 通常通过 Sysprep、inf 文件进行调用，但也可以通过另一种方法（如脚本）运行。</span><span class="sxs-lookup"><span data-stu-id="31318-193">Ftscompletion.exe is typically called through the Sysprep,inf file but can also be run through another method, such as a script.</span></span> <span data-ttu-id="31318-194">但是，Ftscompletion.exe 必须是在配置工作站时执行的最后一步操作。</span><span class="sxs-lookup"><span data-stu-id="31318-194">However, Ftscompletion.exe must be the last action that is performed when the workstation is configured.</span></span> <span data-ttu-id="31318-195">有关详细信息，请参阅[配置适用于 med-v 的 Windows 虚拟 PC 映像](configuring-a-windows-virtual-pc-image-for-med-v.md)。</span><span class="sxs-lookup"><span data-stu-id="31318-195">For more information, see [Configuring a Windows Virtual PC Image for MED-V](configuring-a-windows-virtual-pc-image-for-med-v.md).</span></span>

4.  <span data-ttu-id="31318-196">Ftscompletion.exe 重新启动 MED-V 工作区后，最终用户登录。</span><span class="sxs-lookup"><span data-stu-id="31318-196">After the MED-V workspace is restarted by Ftscompletion.exe, the end user is logged on.</span></span> <span data-ttu-id="31318-197">如果他们在首次设置时没有保存密码，系统将再次提示他们。</span><span class="sxs-lookup"><span data-stu-id="31318-197">If they did not save their password during first time setup, they are prompted for it again.</span></span> <span data-ttu-id="31318-198">然后为用户启动并配置 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="31318-198">The MED-V workspace is then started and configured for the user.</span></span> <span data-ttu-id="31318-199">配置包括应用组策略。</span><span class="sxs-lookup"><span data-stu-id="31318-199">Configuration includes applying Group Policy.</span></span>

    <span data-ttu-id="31318-200">我们建议你仅应用在 Windows XP 的应用程序兼容性环境中有意义的策略。</span><span class="sxs-lookup"><span data-stu-id="31318-200">We recommend that you apply only those policies that make sense in an application compatibility environment for Windows XP.</span></span> <span data-ttu-id="31318-201">例如，桌面个性化策略通常不需要应用，并且应被禁用。</span><span class="sxs-lookup"><span data-stu-id="31318-201">For example, desktop personalization policies do not typically need to be applied and should be disabled.</span></span> <span data-ttu-id="31318-202">有关如何仅允许本地配置文件的详细信息，请参阅[漫游用户配置文件（.）的组策略设置](https://go.microsoft.com/fwlink/?LinkId=205072) https://go.microsoft.com/fwlink/?LinkId=205072) 。</span><span class="sxs-lookup"><span data-stu-id="31318-202">For more information about how to allow only local profiles, see [Group Policy Settings for Roaming User Profiles](https://go.microsoft.com/fwlink/?LinkId=205072) (https://go.microsoft.com/fwlink/?LinkId=205072).</span></span>

<span data-ttu-id="31318-203">第一次设置完成后，系统会通知最终用户已发布的应用程序已准备就绪。</span><span class="sxs-lookup"><span data-stu-id="31318-203">After first time setup is complete, the end user is notified that the published applications are ready.</span></span> <span data-ttu-id="31318-204">然后，他们可以从其 "**开始**" 菜单访问 med-v 工作区中安装的应用程序。</span><span class="sxs-lookup"><span data-stu-id="31318-204">They are then able to access the applications installed in the MED-V workspace from their **Start** menu.</span></span>

## <span data-ttu-id="31318-205">相关主题</span><span class="sxs-lookup"><span data-stu-id="31318-205">Related topics</span></span>


[<span data-ttu-id="31318-206">为 MED-V 准备部署环境</span><span class="sxs-lookup"><span data-stu-id="31318-206">Prepare the Deployment Environment for MED-V</span></span>](prepare-the-deployment-environment-for-med-v.md)

[<span data-ttu-id="31318-207">MED-V 的部署</span><span class="sxs-lookup"><span data-stu-id="31318-207">Deployment of MED-V</span></span>](deployment-of-med-v.md)









