---
title: MED-V 2.0 的端到端操作方案
description: MED-V 2.0 的端到端操作方案
author: dansimp
ms.assetid: 1d87f5f3-9fc5-4731-8bd1-c155714f34ee
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 90a7c2135ad27040ed87dac980b67321eb771574
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803914"
---
# <span data-ttu-id="ed089-103">MED-V 2.0 的端到端操作方案</span><span class="sxs-lookup"><span data-stu-id="ed089-103">End-to-End Operations Scenario for MED-V 2.0</span></span>


<span data-ttu-id="ed089-104">Microsoft 企业桌面虚拟化（MED-V）2.0 的此示例方案可帮助你通过端到端使用多个方案来部署和管理 MED-V。</span><span class="sxs-lookup"><span data-stu-id="ed089-104">This sample scenario for Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 helps you deploy and manage MED-V by using multiple scenarios end-to-end.</span></span> <span data-ttu-id="ed089-105">你可以将此示例方案视为一个案例研究，可帮助在上下文中放置单个方案和过程。</span><span class="sxs-lookup"><span data-stu-id="ed089-105">You can think of this sample scenario as a case study that helps put the individual scenarios and procedures in context.</span></span>

<span data-ttu-id="ed089-106">本部分提供了创建、部署和管理 MED-V 工作区的基本信息和指导，作为你企业中的端到端解决方案。</span><span class="sxs-lookup"><span data-stu-id="ed089-106">This section provides basic information and directions for creating, deploying, and managing MED-V workspaces as an end-to-end solution in your enterprise.</span></span>

## <span data-ttu-id="ed089-107">MED-V 操作分步方案</span><span class="sxs-lookup"><span data-stu-id="ed089-107">MED-V Operations Step-by-step Scenario</span></span>


<span data-ttu-id="ed089-108">你在 MED-V 操作方案中遵循的分步过程包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="ed089-108">The step-by-step procedures that you follow in a MED-V operations scenario include the following:</span></span>

-   <span data-ttu-id="ed089-109">[创建用于 med-v 的 Windows 虚拟 Pc 映像](creating-a-windows-virtual-pc-image-for-med-v.md#bkmk-creatingavirtualmachinebyusingmicrosoftvirtualpc)查看如何为 med-v 创建和配置 WINDOWS 虚拟 pc 映像。</span><span class="sxs-lookup"><span data-stu-id="ed089-109">[Creating a Windows Virtual PC Image for MED-V](creating-a-windows-virtual-pc-image-for-med-v.md#bkmk-creatingavirtualmachinebyusingmicrosoftvirtualpc) reviews how to create and configure a Windows Virtual PC image for MED-V.</span></span> <span data-ttu-id="ed089-110">在你可以向用户提供 MED-V 工作区之前，必须先准备一个虚拟硬盘（VHD），用于为 MED-V 构建 MED-V 工作区安装程序包。</span><span class="sxs-lookup"><span data-stu-id="ed089-110">Before you can deliver a MED-V workspace to users, you must first prepare a virtual hard disk (VHD) that you use to build the MED-V workspace installer package for MED-V.</span></span>

-   <span data-ttu-id="ed089-111">[创建用于 med-v 的 Windows 虚拟 Pc 映像](creating-a-windows-virtual-pc-image-for-med-v.md#bkmk-installingwindowsxpontovpc)查看如何在 WINDOWS 虚拟 pc 映像上安装 WINDOWS XP SP3 操作系统。</span><span class="sxs-lookup"><span data-stu-id="ed089-111">[Creating a Windows Virtual PC Image for MED-V](creating-a-windows-virtual-pc-image-for-med-v.md#bkmk-installingwindowsxpontovpc) reviews how to install the Windows XP SP3 operating system on your Windows Virtual PC image.</span></span> <span data-ttu-id="ed089-112">在构建 MED-V 工作区之前，MED-V 要求在 Windows 虚拟 PC 映像上安装 Windows XP SP3。</span><span class="sxs-lookup"><span data-stu-id="ed089-112">MED-V requires that Windows XP SP3 is installed on the Windows Virtual PC image before you build the MED-V workspace.</span></span>

-   <span data-ttu-id="ed089-113">[创建用于 med-v 的 Windows 虚拟 Pc 映像](creating-a-windows-virtual-pc-image-for-med-v.md#bkmk-installingnet)查看如何将 .net FRAMEWORK 3.5 SP1 和更新 KB959209 手动安装到你准备用于 Med-v 的 WINDOWS 虚拟 pc 映像中。</span><span class="sxs-lookup"><span data-stu-id="ed089-113">[Creating a Windows Virtual PC Image for MED-V](creating-a-windows-virtual-pc-image-for-med-v.md#bkmk-installingnet) reviews how to manually install the .NET Framework 3.5 SP1 and the update KB959209 into the Windows Virtual PC image that you prepare for use with MED-V.</span></span> <span data-ttu-id="ed089-114">MED-V 需要 .NET Framework 3.5 SP1 和更新[KB959209](https://go.microsoft.com/fwlink/?LinkId=204950) （ https://go.microsoft.com/fwlink/?LinkId=204950) 解决几个已知的应用程序兼容性问题。</span><span class="sxs-lookup"><span data-stu-id="ed089-114">MED-V requires the .NET Framework 3.5 SP1, and the update [KB959209](https://go.microsoft.com/fwlink/?LinkId=204950) (https://go.microsoft.com/fwlink/?LinkId=204950) addresses several known application compatibility issues.</span></span>

-   <span data-ttu-id="ed089-115">[创建用于 med-v 的 Windows 虚拟 PC 映像](creating-a-windows-virtual-pc-image-for-med-v.md#bkmk-applypatchestovpc)查看如何使用最新的软件更新以及运行 med-v 所需的其他修补程序（重要）更新 windows XP 映像。</span><span class="sxs-lookup"><span data-stu-id="ed089-115">[Creating a Windows Virtual PC Image for MED-V](creating-a-windows-virtual-pc-image-for-med-v.md#bkmk-applypatchestovpc) reviews how to update your Windows XP image with the latest software updates and other hotfixes necessary or important for running MED-V.</span></span>

-   <span data-ttu-id="ed089-116">[创建用于 med-v 的 Windows 虚拟 PC 映像](creating-a-windows-virtual-pc-image-for-med-v.md#bkmk-installintegration)查看如何在 Windows XP 映像中安装集成组件程序包。</span><span class="sxs-lookup"><span data-stu-id="ed089-116">[Creating a Windows Virtual PC Image for MED-V](creating-a-windows-virtual-pc-image-for-med-v.md#bkmk-installintegration) reviews how to install the integration components package in your Windows XP image.</span></span> <span data-ttu-id="ed089-117">这些功能提供了改进虚拟环境和物理计算机之间的交互的功能。</span><span class="sxs-lookup"><span data-stu-id="ed089-117">These provide features that improve the interaction between the virtual environment and the physical computer.</span></span>

-   <span data-ttu-id="ed089-118">[在 Windows 虚拟 PC 映像上安装应用程序](installing-applications-on-a-windows-virtual-pc-image.md)查看如何在 windows XP 映像上安装某些类型的软件，这些软件在你运行 med-v （如电子软件分发系统和防病毒软件）时非常有用。</span><span class="sxs-lookup"><span data-stu-id="ed089-118">[Installing Applications on a Windows Virtual PC Image](installing-applications-on-a-windows-virtual-pc-image.md) reviews how you can install certain kinds of software on your Windows XP image that are helpful when you are running MED-V, such as an electronic software distribution system and antivirus software.</span></span>

-   <span data-ttu-id="ed089-119">[为 Med-v 配置 Windows 虚拟 PC 映像](configuring-a-windows-virtual-pc-image-for-med-v.md)介绍如何使用 Sysprep 来配置映像，以确保它可以与 med-v 配合使用。</span><span class="sxs-lookup"><span data-stu-id="ed089-119">[Configuring a Windows Virtual PC Image for MED-V](configuring-a-windows-virtual-pc-image-for-med-v.md) discusses how to configure the image by using Sysprep to make sure that it is ready for use with MED-V.</span></span> <span data-ttu-id="ed089-120">然后，使用准备好的 MED-V 图像创建 MED-V 工作区程序包。</span><span class="sxs-lookup"><span data-stu-id="ed089-120">The prepared MED-V image is then used to create your MED-V workspace package.</span></span>

-   <span data-ttu-id="ed089-121">[创建 Med-v 工作区程序包](create-a-med-v-workspace-package.md)查看如何构建在整个企业中部署的 med-v 工作区程序包。</span><span class="sxs-lookup"><span data-stu-id="ed089-121">[Create a MED-V Workspace Package](create-a-med-v-workspace-package.md) reviews how to build the MED-V workspace package that you deploy throughout your enterprise.</span></span> <span data-ttu-id="ed089-122">部署 MED-V 工作区程序包以在最终用户计算机上安装 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="ed089-122">You deploy the MED-V workspace package to install the MED-V workspace on end-user computers.</span></span> <span data-ttu-id="ed089-123">MED-V 工作区是最终用户与由 MED-V 提供的虚拟机交互的 Windows XP 桌面环境。</span><span class="sxs-lookup"><span data-stu-id="ed089-123">A MED-V workspace is the Windows XP desktop environment from which end users interact with the virtual machine provided by MED-V.</span></span>

-   <span data-ttu-id="ed089-124">[测试 Med-v 工作区程序包](testing-the-med-v-workspace-package.md)介绍如何创建可在其中测试 med-v 工作区程序包功能的测试环境，例如首次设置设置和应用程序发布。</span><span class="sxs-lookup"><span data-stu-id="ed089-124">[Testing the MED-V Workspace Package](testing-the-med-v-workspace-package.md) discusses how to create a test environment in which you can test the functionality of the MED-V workspace package, such as first time setup settings and application publishing.</span></span> <span data-ttu-id="ed089-125">在完成对 MED-V 工作区程序包的测试并验证它是否按预期运行后，您可以在整个企业中部署它。</span><span class="sxs-lookup"><span data-stu-id="ed089-125">After you have completed testing your MED-V workspace package and have verified that it is functioning as intended, you can deploy it throughout your enterprise.</span></span>

-   <span data-ttu-id="ed089-126">[部署 Med-v 工作区程序包](deploying-the-med-v-workspace-package.md)讨论如何使用电子软件分发系统或在 Windows 7 映像中部署 med-v 工作区。</span><span class="sxs-lookup"><span data-stu-id="ed089-126">[Deploying the MED-V Workspace Package](deploying-the-med-v-workspace-package.md) discusses how to deploy the MED-V workspace either by using an electronic software distribution system or in a Windows 7 image.</span></span> <span data-ttu-id="ed089-127">或者，如果你愿意，此部分还会向你介绍如何手动部署 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="ed089-127">Or if you prefer, this section also shows you how you can deploy the MED-V workspace manually.</span></span>

-   <span data-ttu-id="ed089-128">[监视 Med-v 工作区](monitor-med-v-workspaces.md)查看如何监视 med-v 工作区的部署，以确定首次设置是否成功完成。</span><span class="sxs-lookup"><span data-stu-id="ed089-128">[Monitor MED-V Workspaces](monitor-med-v-workspaces.md) reviews how to monitor the deployment of MED-V workspaces to determine whether first time setup completed successfully.</span></span> <span data-ttu-id="ed089-129">监视首次设置是否成功是很重要的，因为在首次安装成功完成之前，MED-V 未处于可用状态。</span><span class="sxs-lookup"><span data-stu-id="ed089-129">Monitoring the success of first time setup is important because MED-V is not in a usable state until first time setup has completed successfully.</span></span> <span data-ttu-id="ed089-130">此部分还介绍了如何设置你的环境，以检测可能影响 MED-V 的网络更改。</span><span class="sxs-lookup"><span data-stu-id="ed089-130">This section also shows you can set up your environment to detect those network changes that can affect MED-V.</span></span>

-   <span data-ttu-id="ed089-131">[管理 Med-v 工作区应用程序](manage-med-v-workspace-applications.md)查看如何在已部署的 med-v 工作区上安装和删除或发布和取消发布应用程序。</span><span class="sxs-lookup"><span data-stu-id="ed089-131">[Manage MED-V Workspace Applications](manage-med-v-workspace-applications.md) reviews how to install and remove or publish and unpublish applications on a deployed MED-V workspace.</span></span> <span data-ttu-id="ed089-132">本部分还介绍了如何在 MED-V 工作区中手动更新软件以及如何管理自动更新。</span><span class="sxs-lookup"><span data-stu-id="ed089-132">This section also shows how to manually update software in a MED-V workspace and how to manage automatic updates.</span></span> <span data-ttu-id="ed089-133">MED-V 工作区是包含单独操作系统的虚拟机，该操作系统的自动软件更新过程必须与企业中的物理计算机完全一样。</span><span class="sxs-lookup"><span data-stu-id="ed089-133">The MED-V workspace is a virtual machine that contains a separate operating system whose automatic software update process must be managed exactly like the physical computers in your enterprise.</span></span>

-   <span data-ttu-id="ed089-134">[管理 MED-V URL 重定向](manage-med-v-url-redirection.md)查看如何在已部署的 med-v 工作区中添加和删除 web 地址重定向设置。</span><span class="sxs-lookup"><span data-stu-id="ed089-134">[Manage MED-V URL Redirection](manage-med-v-url-redirection.md) reviews how to add and remove web address redirection settings on the deployed MED-V workspace.</span></span> <span data-ttu-id="ed089-135">你可以通过注册表或通过重建 MED-V 工作区来添加或删除 URL 重定向信息。</span><span class="sxs-lookup"><span data-stu-id="ed089-135">You can add or remove URL redirection information through the registry or by rebuilding the MED-V workspace.</span></span> <span data-ttu-id="ed089-136">你还可以使用 MED-V 工作区包装程序上的向导管理 web 地址重定向。</span><span class="sxs-lookup"><span data-stu-id="ed089-136">You can also use the wizard on the MED-V Workspace Packager to manage web address redirection.</span></span>

-   <span data-ttu-id="ed089-137">[管理 Med-v 工作区设置](manage-med-v-workspace-settings.md)查看如何使用 Med-v 工作区包装程序查看和编辑 med-v 配置设置。</span><span class="sxs-lookup"><span data-stu-id="ed089-137">[Manage MED-V Workspace Settings](manage-med-v-workspace-settings.md) reviews how to view and edit MED-V configuration settings by using the MED-V Workspace Packager.</span></span> <span data-ttu-id="ed089-138">此部分列出了所有可配置的 MED-V 注册表项，包括每个的类型、默认和说明。</span><span class="sxs-lookup"><span data-stu-id="ed089-138">This section lists all the configurable MED-V registry keys and includes the type, default, and description of each.</span></span> <span data-ttu-id="ed089-139">本节还包括有关如何管理 MED-V 工作区中的打印机的信息。</span><span class="sxs-lookup"><span data-stu-id="ed089-139">This section also includes information about how to manage printers in MED-V workspaces.</span></span> <span data-ttu-id="ed089-140">在 MED-V 2.0 中，打印机重定向使用户在 MED-V 虚拟机和主机之间具有一致的打印体验。</span><span class="sxs-lookup"><span data-stu-id="ed089-140">In MED-V 2.0, printer redirection gives users a consistent printing experience between the MED-V virtual machine and the host computer.</span></span>

## <span data-ttu-id="ed089-141">相关主题</span><span class="sxs-lookup"><span data-stu-id="ed089-141">Related topics</span></span>


[<span data-ttu-id="ed089-142">MED-V 的操作</span><span class="sxs-lookup"><span data-stu-id="ed089-142">Operations for MED-V</span></span>](operations-for-med-v.md)

[<span data-ttu-id="ed089-143">MED-V 2.0 的端到端规划方案</span><span class="sxs-lookup"><span data-stu-id="ed089-143">End-to-End Planning Scenario for MED-V 2.0</span></span>](end-to-end-planning-scenario-for-med-v-20.md)

[<span data-ttu-id="ed089-144">MED-V 2.0 的端到端部署方案</span><span class="sxs-lookup"><span data-stu-id="ed089-144">End-to-End Deployment Scenario for MED-V 2.0</span></span>](end-to-end-deployment-scenario-for-med-v-20.md)

 

 





