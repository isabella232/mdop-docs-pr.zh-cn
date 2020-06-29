---
title: 规划 Application Virtualization Client 部署
description: 规划 Application Virtualization Client 部署
author: dansimp
ms.assetid: a352f80f-f0f9-4fbf-ac10-24c510b2d6be
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6c9fc4f29020af83a8606827015947e78761f4d7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798874"
---
# <span data-ttu-id="3acfd-103">规划 Application Virtualization Client 部署</span><span class="sxs-lookup"><span data-stu-id="3acfd-103">Planning for Application Virtualization Client Deployment</span></span>


<span data-ttu-id="3acfd-104">确定如何将虚拟应用程序包发布和部署到最终用户计算机后，应规划应用程序虚拟化客户端软件的部署。</span><span class="sxs-lookup"><span data-stu-id="3acfd-104">After you have decided how you will publish and deploy virtual application packages to your end user computers, you should plan the deployment of the Application Virtualization Client software.</span></span>

<span data-ttu-id="3acfd-105">应用程序虚拟化客户端是实际运行虚拟应用程序的组件。</span><span class="sxs-lookup"><span data-stu-id="3acfd-105">The Application Virtualization Client is the component that actually runs the virtual applications.</span></span> <span data-ttu-id="3acfd-106">应用程序虚拟化客户端使用户能够与图标交互，并双击文件类型以启动虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="3acfd-106">The Application Virtualization Client enables users to interact with icons and to double-click file types to start a virtual application.</span></span> <span data-ttu-id="3acfd-107">它还处理流服务器中的应用程序内容的流式处理，并在启动应用程序之前对其进行缓存。</span><span class="sxs-lookup"><span data-stu-id="3acfd-107">It also handles streaming of the application content from a streaming server and caches it before starting the application.</span></span> <span data-ttu-id="3acfd-108">应用程序内容结构化，以便启动应用程序和处理初始用户交互所需的所有内容首先被流式传输到最终用户计算机。</span><span class="sxs-lookup"><span data-stu-id="3acfd-108">The application content is structured such that all the content needed to start the application and handle initial user interaction is streamed to the end user computer first.</span></span> <span data-ttu-id="3acfd-109">有两种不同类型的应用程序虚拟化客户端软件：用于远程桌面服务（以前称为终端服务）的应用程序虚拟化客户端，用于远程桌面会话主机（RDSession 主机）服务器系统上的应用程序虚拟化桌面客户端，以及用于所有其他计算机的应用程序虚拟化桌面客户端。</span><span class="sxs-lookup"><span data-stu-id="3acfd-109">There are two different types of Application Virtualization Client software: the Application Virtualization Client for Remote Desktop Services (formerly Terminal Services), which is used on Remote Desktop Session Host (RDSession Host) server systems, and the Application Virtualization Desktop Client, which is used for all other computers.</span></span>

<span data-ttu-id="3acfd-110">应用程序虚拟化客户端应在安装时通过应用程序虚拟化管理控制台或通过安装程序命令行（包括以下几个重要设置）进行配置：</span><span class="sxs-lookup"><span data-stu-id="3acfd-110">The Application Virtualization Client should be configured at installation time, either in the Application Virtualization Management Console or via the installer command line, with a number of important settings, including the following:</span></span>

-   <span data-ttu-id="3acfd-111">所有应用程序的图标的位置。</span><span class="sxs-lookup"><span data-stu-id="3acfd-111">Locations of the icons for all the applications.</span></span>

-   <span data-ttu-id="3acfd-112">包含程序包定义信息的 OSD 文件的位置。</span><span class="sxs-lookup"><span data-stu-id="3acfd-112">The location of the OSD file that contains the package definition information.</span></span>

-   <span data-ttu-id="3acfd-113">应用程序内容源。</span><span class="sxs-lookup"><span data-stu-id="3acfd-113">The application content source.</span></span>

-   <span data-ttu-id="3acfd-114">检索前面的项目时要使用的通信协议。</span><span class="sxs-lookup"><span data-stu-id="3acfd-114">The communications protocol to be used when retrieving the preceding items.</span></span>

-   <span data-ttu-id="3acfd-115">要使用的缓存大小和缓存大小管理方法。</span><span class="sxs-lookup"><span data-stu-id="3acfd-115">The cache size and cache size management method to be used.</span></span>

<span data-ttu-id="3acfd-116">若要在使用电子软件分发（ESD）解决方案时加速应用程序虚拟化客户端软件的部署，必须提前仔细定义前面的设置。</span><span class="sxs-lookup"><span data-stu-id="3acfd-116">To expedite the deployment of the Application Virtualization Client software when using an electronic software distribution (ESD) solution, the preceding settings must be defined carefully in advance.</span></span> <span data-ttu-id="3acfd-117">如果你的计算机位于不同的办事处，并且需要将其客户端配置为使用不同的源位置，这一点尤其重要。</span><span class="sxs-lookup"><span data-stu-id="3acfd-117">This is especially important when you have computers in different offices, where their clients would need to be configured to use different source locations.</span></span>

**<span data-ttu-id="3acfd-118">注意</span><span class="sxs-lookup"><span data-stu-id="3acfd-118">Note</span></span>**  
-   <span data-ttu-id="3acfd-119">在选择发布方法时，无论使用的是 Windows Installer 还是 SFTMIME，图标位置和 OSD 文件值都是要考虑的重要因素。</span><span class="sxs-lookup"><span data-stu-id="3acfd-119">The icon location and OSD file values are an important factor to consider when choosing your publishing method, whether using Windows Installer or SFTMIME.</span></span> <span data-ttu-id="3acfd-120">应用程序内容源的设置由你选择的流式处理方法定义。</span><span class="sxs-lookup"><span data-stu-id="3acfd-120">The setting for the application content source is defined by your choice of streaming method.</span></span>

-   <span data-ttu-id="3acfd-121">若要确保缓存为所有可能部署的程序包分配了足够的空间，请在配置客户端时使用 "**使用可用磁盘空间阈值**" 设置，以便缓存可以根据需要增长。</span><span class="sxs-lookup"><span data-stu-id="3acfd-121">To ensure that the cache has sufficient space allocated for all packages that might be deployed, use the **Use free disk space threshold** setting when you configure the client so that the cache can grow as needed.</span></span> <span data-ttu-id="3acfd-122">或者，提前确定应用 V 缓存所需的磁盘空间量，并在安装时设置相应的缓存大小。</span><span class="sxs-lookup"><span data-stu-id="3acfd-122">Alternatively, determine in advance how much disk space will be needed for the App-V cache, and at installation time, set the cache size accordingly.</span></span> <span data-ttu-id="3acfd-123">有关缓存空间管理功能的详细信息，请参阅如何使用 Microsoft Application Virtualization （App-v）操作指南中**的缓存空间管理功能**。</span><span class="sxs-lookup"><span data-stu-id="3acfd-123">For more information about the cache space management feature, see **How to Use the Cache Space Management Feature** in the Microsoft Application Virtualization (App-V) Operations Guide.</span></span>

-   <span data-ttu-id="3acfd-124">在发布和 HTTP （S）流操作过程中，App-v 4.5 SP1 客户端使用在用户计算机上的 Internet Explorer 中配置的代理服务器设置。</span><span class="sxs-lookup"><span data-stu-id="3acfd-124">During both the publishing and HTTP(S) streaming operations,App-V 4.5 SP1 clients use the proxy server settings that are configured in Internet Explorer on the user’s computer.</span></span>

<span data-ttu-id="3acfd-125">有关配置客户端安装参数的详细信息，请参阅[应用程序虚拟化客户端安装程序命令行参数](application-virtualization-client-installer-command-line-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="3acfd-125">For more information about configuring the client installation parameters, see [Application Virtualization Client Installer Command-Line Parameters](application-virtualization-client-installer-command-line-parameters.md).</span></span>

 

<span data-ttu-id="3acfd-126">最后，你需要确定如何为桌面客户端部署应用程序虚拟化桌面客户端软件。</span><span class="sxs-lookup"><span data-stu-id="3acfd-126">Finally, you need to determine how to deploy the Application Virtualization Desktop Client software for the desktop clients.</span></span> <span data-ttu-id="3acfd-127">虽然可以在每台计算机上手动部署应用程序虚拟化桌面客户端，但大多数组织都需要通过某些自动化过程来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="3acfd-127">Although it is possible to deploy the Application Virtualization Desktop Client manually on each computer, most organizations would need to do this through some automated process.</span></span> <span data-ttu-id="3acfd-128">中等或大型组织可能会有 ESD 系统正在运行，这将是部署客户端的理想方法。</span><span class="sxs-lookup"><span data-stu-id="3acfd-128">A medium or large organization might have an ESD system in operation, and that would be an ideal way to deploy the client.</span></span> <span data-ttu-id="3acfd-129">如果不存在 ESD 系统，则可以使用你的标准方法在组织中安装软件。</span><span class="sxs-lookup"><span data-stu-id="3acfd-129">If no ESD system exists, you can use your standard method of installing software in your organization.</span></span> <span data-ttu-id="3acfd-130">选项包括组策略或各种脚本技术。</span><span class="sxs-lookup"><span data-stu-id="3acfd-130">Choices include Group Policy or various scripting techniques.</span></span> <span data-ttu-id="3acfd-131">根据你拥有的办事处的数量和大小，此部署过程可能会很复杂，因此你需要采用结构化的方法来确保所有计算机获得安装了正确配置的客户端，这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="3acfd-131">Depending on the number and size of the offices you have, this deployment process can be complex, and it is essential that you take a structured approach to ensure all computers get a client installed with the correct configuration.</span></span>

## <span data-ttu-id="3acfd-132">相关主题</span><span class="sxs-lookup"><span data-stu-id="3acfd-132">Related topics</span></span>


[<span data-ttu-id="3acfd-133">规划 Application Virtualization System 部署</span><span class="sxs-lookup"><span data-stu-id="3acfd-133">Planning for Application Virtualization System Deployment</span></span>](planning-for-application-virtualization-system-deployment.md)

[<span data-ttu-id="3acfd-134">如何使用命令行安装客户端</span><span class="sxs-lookup"><span data-stu-id="3acfd-134">How to Install the Client by Using the Command Line</span></span>](how-to-install-the-client-by-using-the-command-line-new.md)

[<span data-ttu-id="3acfd-135">如何在客户端上发布虚拟应用程序</span><span class="sxs-lookup"><span data-stu-id="3acfd-135">How to Publish a Virtual Application on the Client</span></span>](how-to-publish-a-virtual-application-on-the-client.md)

[<span data-ttu-id="3acfd-136">如何升级 Application Virtualization Client</span><span class="sxs-lookup"><span data-stu-id="3acfd-136">How to Upgrade the Application Virtualization Client</span></span>](how-to-upgrade-the-application-virtualization-client.md)

[<span data-ttu-id="3acfd-137">如何卸载 App-V Client</span><span class="sxs-lookup"><span data-stu-id="3acfd-137">How to Uninstall the App-V Client</span></span>](how-to-uninstall-the-app-v-client.md)

 

 





