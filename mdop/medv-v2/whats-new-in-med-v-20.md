---
title: MED-V 2.0 中的新增功能
description: MED-V 2.0 中的新增功能
author: dansimp
ms.assetid: 53b10bff-2b6f-463b-bdc2-5edc56526792
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 78dba25fec7ae2bb41da00902b59dcd15030f2b6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803421"
---
# <span data-ttu-id="5d33a-103">MED-V 2.0 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="5d33a-103">What's New in MED-V 2.0</span></span>


<span data-ttu-id="5d33a-104">Microsoft 企业版桌面虚拟化（MED-V）2.0 发展了适用于 Windows 7 的应用程序兼容性支持和删除了此方案不需要的功能。</span><span class="sxs-lookup"><span data-stu-id="5d33a-104">Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 has evolved the application compatibility support for Windows 7 and removed functionality that is not required for this scenario.</span></span> <span data-ttu-id="5d33a-105">例如，"MED-V" 工作区、"集中的 MED-V 服务器" 和 "MED-V 工作区剪裁传输" 等功能已被删除。</span><span class="sxs-lookup"><span data-stu-id="5d33a-105">For example, features such as encryption of the MED-V workspace, the centralized MED-V server, and MED-V workspace trim transfer have been removed.</span></span>

## <span data-ttu-id="5d33a-106">标准功能的更改</span><span class="sxs-lookup"><span data-stu-id="5d33a-106">Changes in Standard Functionality</span></span>


<span data-ttu-id="5d33a-107">本部分讨论了 MED-V 2.0 功能发生更改的关键区域。</span><span class="sxs-lookup"><span data-stu-id="5d33a-107">This section discusses the key areas where MED-V 2.0 functionality has changed.</span></span>

### <span data-ttu-id="5d33a-108">MED-V 工作区创建</span><span class="sxs-lookup"><span data-stu-id="5d33a-108">MED-V Workspace Creation</span></span>

<span data-ttu-id="5d33a-109">现已在 Windows 虚拟 PC 中创建用于 MED-V 工作区的虚拟硬盘。</span><span class="sxs-lookup"><span data-stu-id="5d33a-109">The virtual hard disk used for the MED-V workspace is now created in Windows Virtual PC.</span></span> <span data-ttu-id="5d33a-110">用于创建 MED-V 工作区的方法包括安装 Windows XP SP3、更新操作系统以及准备通过软件管理基础结构管理。</span><span class="sxs-lookup"><span data-stu-id="5d33a-110">The methods that are used to create the MED-V workspace include installing Windows XP SP3, updating the operating system, and preparing it to be managed through software management infrastructure.</span></span>

<span data-ttu-id="5d33a-111">除了专有的 MED-V 工作区加密和压缩功能之外，还删除了脱机管理和剪裁传输功能。</span><span class="sxs-lookup"><span data-stu-id="5d33a-111">The offline management and trim transfer functionality were removed, in addition to the proprietary MED-V workspace encryption and compression functionality.</span></span> <span data-ttu-id="5d33a-112">创建 MED-V 工作区时，管理员应在映像中准备和配置适当的应用程序和管理工具，而不是使用 MED-V 1.0 中提供的虚拟机准备工具。</span><span class="sxs-lookup"><span data-stu-id="5d33a-112">When you create a MED-V workspace, an administrator should prepare and configure appropriate applications and management tools in the image instead of using the virtual machine preparation tool that is provided in MED-V 1.0.</span></span>

<span data-ttu-id="5d33a-113">现在，在将 MED-V 工作区打包期间，需要并验证在 MED-V 映像上运行 Sysprep。</span><span class="sxs-lookup"><span data-stu-id="5d33a-113">Running Sysprep on the MED-V image is now required and validated during the packaging of the MED-V workspace.</span></span> <span data-ttu-id="5d33a-114">MED-V 工作区包装程序提供了一个图形用户界面（GUI），可指导管理员完成打包过程。</span><span class="sxs-lookup"><span data-stu-id="5d33a-114">The MED-V Workspace Packager provides a graphical user interface (GUI) that guides the administrator through the packaging process.</span></span> <span data-ttu-id="5d33a-115">从 MED-V 1.0 中的控制台与管理图像的功能、管理 MED-V 工作区配置文件以及暂存和加密 MED-V 工作区的要求一起删除。</span><span class="sxs-lookup"><span data-stu-id="5d33a-115">The console from MED-V 1.0 was removed together with the functionality of managing images, managing MED-V workspace profiles, and the requirement to stage and encrypt MED-V workspaces.</span></span>

### <span data-ttu-id="5d33a-116">MED-V 工作区部署</span><span class="sxs-lookup"><span data-stu-id="5d33a-116">MED-V Workspace Deployment</span></span>

<span data-ttu-id="5d33a-117">若要部署 MED-V 工作区，管理员现在可以利用其电子软件分发工具。</span><span class="sxs-lookup"><span data-stu-id="5d33a-117">To deploy a MED-V workspace, an administrator is now able to take advantage of their electronic software distribution tools.</span></span> <span data-ttu-id="5d33a-118">已删除 MED-V 1.0 中可用的客户端拉取方法，现在，使用 MED-V 之外的方法提供了 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="5d33a-118">The client-pull method available in MED-V 1.0 was removed and the MED-V workspace is now delivered by using methods outside MED-V.</span></span> <span data-ttu-id="5d33a-119">管理员可以像处理任何其他应用程序包那样处理 MED-V 工作区，并可以通过使用现有工具和进程来安排 MED-V 的部署和安装。</span><span class="sxs-lookup"><span data-stu-id="5d33a-119">Administrators can treat MED-V workspaces as they would any other application package and can schedule deployments and installations of MED-V by using their existing tools and processes.</span></span> <span data-ttu-id="5d33a-120">MED-V 安装可以自行部署，并且可以在现有软件分发基础结构中轻松管理。</span><span class="sxs-lookup"><span data-stu-id="5d33a-120">MED-V installations can be deployed silently and can easily be managed inside an existing software distribution infrastructure.</span></span>

### <span data-ttu-id="5d33a-121">MED-V 工作区管理</span><span class="sxs-lookup"><span data-stu-id="5d33a-121">MED-V Workspace Management</span></span>

<span data-ttu-id="5d33a-122">MED-V 2.0 中的 MED-V 工作区基于 Windows 虚拟 PC 虚拟硬盘。</span><span class="sxs-lookup"><span data-stu-id="5d33a-122">The MED-V workspace in MED-V 2.0 is based on a Windows Virtual PC virtual hard disk.</span></span> <span data-ttu-id="5d33a-123">MED-V 已扩展了 Windows 虚拟 PC 提供的功能，无需加密或特殊工具即可访问 MED-V 工作区，从而提高了无缝体验。</span><span class="sxs-lookup"><span data-stu-id="5d33a-123">MED-V has extended the capabilities that Windows Virtual PC provides by improving the seamless experience without requiring encryption or special tools to access the MED-V workspace.</span></span>

<span data-ttu-id="5d33a-124">将 MED-V 部署到工作站后，可以使用 Windows 虚拟 PC 以全屏模式打开 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="5d33a-124">After MED-V is deployed to a workstation, the MED-V workspace can be opened in full-screen mode by using Windows Virtual PC.</span></span> <span data-ttu-id="5d33a-125">这一新功能删除了针对无缝或全屏模式设置首选项的策略的要求，同时还删除了需要为诊断和故障排除强制全屏的需要。</span><span class="sxs-lookup"><span data-stu-id="5d33a-125">This new functionality removed the requirement for policies that set a preference for seamless or full-screen modes and also removed the need to force full-screen for diagnostics and troubleshooting.</span></span>

<span data-ttu-id="5d33a-126">将应用程序发布到 MED-V 工作区后，将不再通过配置文件和手动输入应用程序的路径来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="5d33a-126">Publishing applications to the MED-V workspace is no longer performed with profiles and by manually entering the path to applications.</span></span> <span data-ttu-id="5d33a-127">而是在来宾上安装应用程序时自动发生。</span><span class="sxs-lookup"><span data-stu-id="5d33a-127">Instead, it occurs automatically as applications are installed on the guest.</span></span> <span data-ttu-id="5d33a-128">将删除包含通过裁切传送传送的图像版本的中央图像存储库。</span><span class="sxs-lookup"><span data-stu-id="5d33a-128">The central image repository that included versions of the images that were delivered through trim transfer is removed.</span></span> <span data-ttu-id="5d33a-129">相反，MED-V 使管理员能够像管理物理计算机一样管理 MED-V 工作区，方法是让应用程序和更新在没有专用的 MED-V 基础结构复杂的情况下分发。</span><span class="sxs-lookup"><span data-stu-id="5d33a-129">Instead, MED-V enables administrators to manage the MED-V workspace as they would a physical computer, by letting applications and updates be distributed without the complexity of a dedicated MED-V infrastructure.</span></span>

## <span data-ttu-id="5d33a-130">MED-V 功能中的更改</span><span class="sxs-lookup"><span data-stu-id="5d33a-130">Changes in MED-V Features</span></span>


<span data-ttu-id="5d33a-131">MED-V 2.0 的几个关键领域反映了对以下功能的改进或补充。</span><span class="sxs-lookup"><span data-stu-id="5d33a-131">Several key areas of MED-V 2.0 reflect improvements or additions to the following features.</span></span>

### <span data-ttu-id="5d33a-132">MED-V 工作区创建</span><span class="sxs-lookup"><span data-stu-id="5d33a-132">MED-V Workspace Creation</span></span>

<span data-ttu-id="5d33a-133">MED-V 工作区必须使用 Windows 虚拟 PC 创建。</span><span class="sxs-lookup"><span data-stu-id="5d33a-133">MED-V workspaces must be created by using Windows Virtual PC.</span></span> <span data-ttu-id="5d33a-134">必须迁移现有的虚拟 PC 2007 映像。</span><span class="sxs-lookup"><span data-stu-id="5d33a-134">Existing Virtual PC 2007 images must be migrated.</span></span> <span data-ttu-id="5d33a-135">Virtual machine "准备" 工具不包括在 MED-V 2.0 中，管理员应根据 MED-V 2.0 帮助文件配置、更新和优化其图像。</span><span class="sxs-lookup"><span data-stu-id="5d33a-135">The virtual machine Prep tool is not included in MED-V 2.0 and administrators should configure, update, and optimize their images according to the MED-V 2.0 Help file.</span></span> <span data-ttu-id="5d33a-136">在 MED-V 映像上运行 Sysprep 是必需的步骤，必须在打包之前执行。</span><span class="sxs-lookup"><span data-stu-id="5d33a-136">Running Sysprep on the MED-V image is a required step and must be performed before packaging.</span></span>

### <span data-ttu-id="5d33a-137">MED-V 工作区打包</span><span class="sxs-lookup"><span data-stu-id="5d33a-137">MED-V Workspace Packaging</span></span>

<span data-ttu-id="5d33a-138">Windows PowerShell 是 MED-V 工作区包装程序的基础。</span><span class="sxs-lookup"><span data-stu-id="5d33a-138">Windows PowerShell is the foundation of the MED-V Workspace Packager.</span></span> <span data-ttu-id="5d33a-139">此功能将取代 MED-V 的托管集中功能的一些以前的控制台功能和功能。</span><span class="sxs-lookup"><span data-stu-id="5d33a-139">This functionality replaces some former console abilities and functionality that managed centralized functions of MED-V.</span></span> <span data-ttu-id="5d33a-140">MED-V 工作区包装程序仅使用适当的设置和映像打包虚拟硬盘，以便管理员可以轻松地部署它。</span><span class="sxs-lookup"><span data-stu-id="5d33a-140">The MED-V Workspace Packager merely packages the virtual hard disk with the appropriate settings and image so that it can be easily deployed by administrators.</span></span> <span data-ttu-id="5d33a-141">使用 Windows PowerShell 提供高级功能。</span><span class="sxs-lookup"><span data-stu-id="5d33a-141">Advanced features are provided by using Windows PowerShell.</span></span>

### <span data-ttu-id="5d33a-142">MED-V 工作区分布</span><span class="sxs-lookup"><span data-stu-id="5d33a-142">MED-V Workspace Distribution</span></span>

<span data-ttu-id="5d33a-143">对于 MED-V 2.0 不再需要专用服务器基础结构，删除了用于部署 MED-V 工作区的客户端 pull 方法。</span><span class="sxs-lookup"><span data-stu-id="5d33a-143">Dedicated server infrastructure is no longer required for MED-V 2.0 and the client pull method to deploy MED-V workspaces was removed.</span></span> <span data-ttu-id="5d33a-144">现在，使用电子软件分发基础结构部署 MED-V 工作区，并且可以存储在用于其他安装程序包的常见共享上。</span><span class="sxs-lookup"><span data-stu-id="5d33a-144">MED-V workspaces are now deployed using your electronic software distribution infrastructure and can be stored on common shares that are used for other installation packages.</span></span>

### <span data-ttu-id="5d33a-145">首次设置</span><span class="sxs-lookup"><span data-stu-id="5d33a-145">First Time Setup</span></span>

<span data-ttu-id="5d33a-146">第一次设置过程现已与 Sysprep 的标准成像约定集成。</span><span class="sxs-lookup"><span data-stu-id="5d33a-146">The first time setup process is now integrated with the standard imaging convention of Sysprep.</span></span> <span data-ttu-id="5d33a-147">当 MED-V 工作区首次运行时，安装过程可在开始 "最小化安装" 时将在 MED-V 工作区包装程序中指定的设置动态应用于该映像。</span><span class="sxs-lookup"><span data-stu-id="5d33a-147">The MED-V workspace first time setup process can dynamically apply settings specified in the MED-V Workspace Packager to the image as it begins Mini-Setup.</span></span> <span data-ttu-id="5d33a-148">已删除控制台中的脚本工具，第一次设置过程现在基于管理员的 MED-V 工作区中配置的选项。</span><span class="sxs-lookup"><span data-stu-id="5d33a-148">The scripting tool in the console was removed and the first time setup process is now based on options that are configured in the MED-V Workspace Packager by the administrator.</span></span>

### <span data-ttu-id="5d33a-149">应用程序发布</span><span class="sxs-lookup"><span data-stu-id="5d33a-149">Application Publishing</span></span>

<span data-ttu-id="5d33a-150">在部署 MED-V 工作区后，或者通过结合使用二者，管理员可以在进行打包之前在 MED-V 映像上安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="5d33a-150">Administrators can install applications on the MED-V image either before packaging, after the MED-V workspace is deployed, or by using a combination of both.</span></span> <span data-ttu-id="5d33a-151">MED-V 不会再检查 MED-V 工作区策略来发布应用程序，而是指在来宾上实际安装的内容。</span><span class="sxs-lookup"><span data-stu-id="5d33a-151">MED-V no longer examines MED-V workspace policy to publish applications, but instead refers to what is actually installed on the guest.</span></span> <span data-ttu-id="5d33a-152">在来宾上安装应用程序时，系统会自动检测和发布这些应用程序，并将其发布到主机 "**开始**" 菜单，并准备好由最终用户启动。</span><span class="sxs-lookup"><span data-stu-id="5d33a-152">As applications are installed on the guest, they are automatically detected and published to the host **Start** menu and are ready to be started by the end user.</span></span>

### <span data-ttu-id="5d33a-153">URL 重定向</span><span class="sxs-lookup"><span data-stu-id="5d33a-153">URL Redirection</span></span>

<span data-ttu-id="5d33a-154">MED-V 2.0 提供了基于管理员配置和管理的策略的无缝主机到来宾 web 地址重定向。</span><span class="sxs-lookup"><span data-stu-id="5d33a-154">MED-V 2.0 provides seamless host-to-guest web address redirection based on the policies configured and managed by the administrator.</span></span> <span data-ttu-id="5d33a-155">将 URL 重定向到来宾浏览器后，默认体验是尝试将用户限制到该重定向网站。</span><span class="sxs-lookup"><span data-stu-id="5d33a-155">After a URL is redirected to the guest browser, the default experience is to attempt to limit the user to that redirected site.</span></span> <span data-ttu-id="5d33a-156">这将最大程度地减少用户可以执行的、不是由管理员使用的浏览活动。</span><span class="sxs-lookup"><span data-stu-id="5d33a-156">This minimizes the browsing activities that a user can perform that are not intended by the administrator.</span></span> <span data-ttu-id="5d33a-157">已删除来宾到主机浏览器重定向。</span><span class="sxs-lookup"><span data-stu-id="5d33a-157">Guest-to-host browser redirection was removed.</span></span>

### <span data-ttu-id="5d33a-158">疑难解答</span><span class="sxs-lookup"><span data-stu-id="5d33a-158">Troubleshooting</span></span>

<span data-ttu-id="5d33a-159">现在，MED-V 利用基于主机的标准进程进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="5d33a-159">MED-V now takes advantage of standard host-based processes for troubleshooting.</span></span> <span data-ttu-id="5d33a-160">由于 MED-V 工作区不再是加密的，因此它可以在 Windows 虚拟 PC 控制台内以全屏模式打开，可在其中以标准工作站的形式查看和处理它。</span><span class="sxs-lookup"><span data-stu-id="5d33a-160">Because the MED-V workspace is no longer encrypted, it can be opened in full-screen mode within the Windows Virtual PC console, where it can be viewed and worked with as a standard workstation.</span></span> <span data-ttu-id="5d33a-161">此外，日志不再在本地加密和集中记录。</span><span class="sxs-lookup"><span data-stu-id="5d33a-161">In addition, the logs are no longer encrypted locally and logged centrally.</span></span> <span data-ttu-id="5d33a-162">现在，MED-V 可以轻松地配置本地事件日志的大量使用，以及输出的日志记录级别（从信息到调试级别）。</span><span class="sxs-lookup"><span data-stu-id="5d33a-162">MED-V now makes extensive use of the local event logs, and the logging level of the output, from informational to debug levels, can be easily configured.</span></span> <span data-ttu-id="5d33a-163">最后，我们提供了疑难解答工具包，以便管理员和技术支持人员可以获得所有疑难解答选项的图形化视图，并且他们可以轻松选择最适合其需要的活动。</span><span class="sxs-lookup"><span data-stu-id="5d33a-163">Finally, a troubleshooting toolkit is now provided so administrators and helpdesk personnel can have a graphical, aggregated view of all the troubleshooting options, and they can effortlessly select the activities that most suit their needs.</span></span>

<span data-ttu-id="5d33a-164">MED-V 已不再作为系统服务运行。</span><span class="sxs-lookup"><span data-stu-id="5d33a-164">MED-V is no longer run as a system service.</span></span> <span data-ttu-id="5d33a-165">相反，它以用户拥有的进程的形式运行，并且仅在用户登录时运行。</span><span class="sxs-lookup"><span data-stu-id="5d33a-165">Instead, it is run as user-owned processes, and it only runs when a user is logged on.</span></span><span data-ttu-id="5d33a-166">以前由系统拥有的服务提供的功能现在在用户端流程中提供。</span><span class="sxs-lookup"><span data-stu-id="5d33a-166">Functionality that was formerly provided by the system-owned service is now provided in the user-side processes.</span></span>

## <span data-ttu-id="5d33a-167">相关主题</span><span class="sxs-lookup"><span data-stu-id="5d33a-167">Related topics</span></span>


[<span data-ttu-id="5d33a-168">MED-V 的部署</span><span class="sxs-lookup"><span data-stu-id="5d33a-168">Deployment of MED-V</span></span>](deployment-of-med-v.md)

[<span data-ttu-id="5d33a-169">MED-V 的操作</span><span class="sxs-lookup"><span data-stu-id="5d33a-169">Operations for MED-V</span></span>](operations-for-med-v.md)

 

 





