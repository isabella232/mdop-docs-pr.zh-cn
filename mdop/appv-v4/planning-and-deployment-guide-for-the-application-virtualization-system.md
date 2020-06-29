---
title: 应用程序虚拟化系统的规划和部署指南
description: 应用程序虚拟化系统的规划和部署指南
author: dansimp
ms.assetid: 6c012e33-9ac6-4cd8-84ff-54f40973833f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 10bcac26fddae2f0e5826dbd7335adda06d3987e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798875"
---
# <span data-ttu-id="1d8c0-103">应用程序虚拟化系统的规划和部署指南</span><span class="sxs-lookup"><span data-stu-id="1d8c0-103">Planning and Deployment Guide for the Application Virtualization System</span></span>


<span data-ttu-id="1d8c0-104">Microsoft Application 虚拟化管理提供了使应用程序可供最终用户计算机使用的功能，而无需直接在这些计算机上安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="1d8c0-104">Microsoft Application Virtualization Management provides the capability to make applications available to end user computers without having to install the applications directly on those computers.</span></span> <span data-ttu-id="1d8c0-105">这可通过一个称为*应用程序顺序的*进程来实现，这使每个应用程序都可以在客户端计算机上其自己的自包含虚拟环境中运行。</span><span class="sxs-lookup"><span data-stu-id="1d8c0-105">This is made possible through a process known as *sequencing the application*, which enables each application to run in its own self-contained virtual environment on the client computer.</span></span> <span data-ttu-id="1d8c0-106">序列化的应用程序彼此隔离，消除了应用程序冲突，但仍可以与客户端计算机交互。</span><span class="sxs-lookup"><span data-stu-id="1d8c0-106">The sequenced applications are isolated from one another, eliminating application conflicts, yet can still interact with the client computer.</span></span>

<span data-ttu-id="1d8c0-107">应用程序虚拟化客户端是应用程序虚拟化系统组件，使最终用户能够在应用程序发布到计算机后与应用程序交互。</span><span class="sxs-lookup"><span data-stu-id="1d8c0-107">The Application Virtualization Client is the Application Virtualization system component that enables the end user to interact with the applications after they have been published to the computer.</span></span> <span data-ttu-id="1d8c0-108">客户端管理虚拟化应用程序在每台计算机上运行的虚拟环境。</span><span class="sxs-lookup"><span data-stu-id="1d8c0-108">The client manages the virtual environment in which the virtualized applications run on each computer.</span></span> <span data-ttu-id="1d8c0-109">在计算机上安装了客户端后，必须通过称为 "*发布*" 的进程将应用程序提供给计算机，这使最终用户能够运行虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="1d8c0-109">After the client has been installed on a computer, the applications must be made available to the computer through a process known as *publishing*, which enables the end user to run the virtual applications.</span></span> <span data-ttu-id="1d8c0-110">发布过程会将计算机上的虚拟应用程序图标和快捷方式置于计算机上（通常在 Windows 桌面或 "**开始**" 菜单上），并且还会将程序包定义和文件类型关联信息放置在计算机上。</span><span class="sxs-lookup"><span data-stu-id="1d8c0-110">The publishing process places the virtual application icons and shortcuts on the computer—typically on the Windows desktop or on the **Start** menu—and also places the package definition and file type association information on the computer.</span></span> <span data-ttu-id="1d8c0-111">发布还使应用程序包内容可供最终用户的计算机使用。</span><span class="sxs-lookup"><span data-stu-id="1d8c0-111">Publishing also makes the application package content available to the end user’s computer.</span></span>

<span data-ttu-id="1d8c0-112">虚拟应用程序包内容可以放置在一个或多个应用程序虚拟服务器上，以便可以按需将其传输到客户端并在本地缓存。</span><span class="sxs-lookup"><span data-stu-id="1d8c0-112">The virtual application package content can be placed on one or more Application Virtualization servers so that it can be streamed down to the clients on demand and cached locally.</span></span> <span data-ttu-id="1d8c0-113">文件服务器和 Web 服务器也可以用作流服务器，或者内容可以直接放置在最终用户的计算机上，例如，如果您使用的是电子软件分发系统（如 Microsoft 终结点配置管理器）。</span><span class="sxs-lookup"><span data-stu-id="1d8c0-113">File servers and Web servers can also be used as streaming servers, or the content can be placed directly on the end user’s computer—for example, if you are using an electronic software distribution system, such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="1d8c0-114">在多服务器实现中，在所有流式处理服务器上维护程序包内容并使其保持最新状态需要全面的程序包管理解决方案。</span><span class="sxs-lookup"><span data-stu-id="1d8c0-114">In a multi-server implementation, maintaining the package content and keeping it up to date on all the streaming servers requires a comprehensive package management solution.</span></span> <span data-ttu-id="1d8c0-115">根据你的组织的规模，你可能需要拥有可供全球各地的最终用户访问的多个虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="1d8c0-115">Depending on the size of your organization, you might need to have many virtual applications accessible to end users located all over the world.</span></span> <span data-ttu-id="1d8c0-116">管理程序包以确保所有用户在需要访问这些应用程序的情况下以及他们需要访问这些应用程序时，它们都可以使用。</span><span class="sxs-lookup"><span data-stu-id="1d8c0-116">Managing the packages to ensure that the right applications are available to all users where and when they need access to them is therefore an essential requirement.</span></span>

<span data-ttu-id="1d8c0-117">应用程序虚拟化规划和部署指南提供的信息可帮助你更好地了解和部署 Microsoft Application Virtualization 应用程序及其组件。</span><span class="sxs-lookup"><span data-stu-id="1d8c0-117">The Application Virtualization Planning and Deployment Guide provides information to help you better understand and deploy the Microsoft Application Virtualization application and its components.</span></span> <span data-ttu-id="1d8c0-118">它还提供了实现密钥部署方案的分步过程。</span><span class="sxs-lookup"><span data-stu-id="1d8c0-118">It also provides step-by-step procedures for implementing the key deployment scenarios.</span></span>

## <span data-ttu-id="1d8c0-119">本部分内容</span><span class="sxs-lookup"><span data-stu-id="1d8c0-119">In This Section</span></span>


<a href="" id="planning-for-application-virtualization-system-deployment"></a>[<span data-ttu-id="1d8c0-120">规划 Application Virtualization System 部署</span><span class="sxs-lookup"><span data-stu-id="1d8c0-120">Planning for Application Virtualization System Deployment</span></span>](planning-for-application-virtualization-system-deployment.md)  
<span data-ttu-id="1d8c0-121">提供规划应用程序虚拟化系统的实施和部署所需的指南。</span><span class="sxs-lookup"><span data-stu-id="1d8c0-121">Provides the guidance necessary to plan the implementation and deployment of your Application Virtualization system.</span></span>

<a href="" id="application-virtualization-deployment-and-upgrade-considerations"></a>[<span data-ttu-id="1d8c0-122">Application Virtualization 部署和升级注意事项</span><span class="sxs-lookup"><span data-stu-id="1d8c0-122">Application Virtualization Deployment and Upgrade Considerations</span></span>](application-virtualization-deployment-and-upgrade-considerations.md)  
<span data-ttu-id="1d8c0-123">提供有关安装各种应用程序虚拟化组件的硬件和软件要求以及升级信息的信息。</span><span class="sxs-lookup"><span data-stu-id="1d8c0-123">Provides information about hardware and software requirements for installing the various Application Virtualization components, as well as upgrade information.</span></span>

<a href="" id="electronic-software-distribution-based-scenario"></a>[<span data-ttu-id="1d8c0-124">基于电子软件分发的方案</span><span class="sxs-lookup"><span data-stu-id="1d8c0-124">Electronic Software Distribution-Based Scenario</span></span>](electronic-software-distribution-based-scenario.md)  
<span data-ttu-id="1d8c0-125">提供有关使用电子软件分发（ESD）系统部署应用程序虚拟化的信息。</span><span class="sxs-lookup"><span data-stu-id="1d8c0-125">Provides information about deploying Application Virtualization using an electronic software distribution (ESD) system.</span></span>

<a href="" id="application-virtualization-server-based-scenario"></a>[<span data-ttu-id="1d8c0-126">基于 Application Virtualization Server 的方案</span><span class="sxs-lookup"><span data-stu-id="1d8c0-126">Application Virtualization Server-Based Scenario</span></span>](application-virtualization-server-based-scenario.md)  
<span data-ttu-id="1d8c0-127">提供有关使用应用程序虚拟化管理服务器部署应用程序虚拟化的信息。</span><span class="sxs-lookup"><span data-stu-id="1d8c0-127">Provides information about deploying Application Virtualization using the Application Virtualization Management Server.</span></span>

<a href="" id="stand-alone-delivery-scenario-for-application-virtualization-clients"></a>[<span data-ttu-id="1d8c0-128">适用于 Application Virtualization Client 的独立传递方案</span><span class="sxs-lookup"><span data-stu-id="1d8c0-128">Stand-Alone Delivery Scenario for Application Virtualization Clients</span></span>](stand-alone-delivery-scenario-for-application-virtualization-clients.md)  
<span data-ttu-id="1d8c0-129">介绍如何在独立模式下部署应用程序虚拟化，而无需使用 ESD 或基于服务器的资源。</span><span class="sxs-lookup"><span data-stu-id="1d8c0-129">Describes how to deploy Application Virtualization in a stand-alone mode, without the use of ESD or server-based resources.</span></span>

<a href="" id="application-virtualization-reference"></a>[<span data-ttu-id="1d8c0-130">Application Virtualization 参考</span><span class="sxs-lookup"><span data-stu-id="1d8c0-130">Application Virtualization Reference</span></span>](application-virtualization-reference.md)  
<span data-ttu-id="1d8c0-131">包含与安装和管理系统组件相关的详细技术参考资料。</span><span class="sxs-lookup"><span data-stu-id="1d8c0-131">Contains detailed technical reference material related to installing and managing system components.</span></span>

 

 





