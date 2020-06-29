---
title: 《应用程序虚拟化安全指南》简介
description: 《应用程序虚拟化安全指南》简介
author: dansimp
ms.assetid: 50e1d220-7a95-45b8-933b-3dadddebe26f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 4b41c65c5ad753aa606d47d2eafe4a28e035cc4e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798937"
---
# <span data-ttu-id="0d951-103">《应用程序虚拟化安全指南》简介</span><span class="sxs-lookup"><span data-stu-id="0d951-103">Introduction to the Application Virtualization Security Guide</span></span>


<span data-ttu-id="0d951-104">本 Microsoft Application Virtualization （App-v） security guide 为负责配置 app-v 部署所选安全功能的管理员提供说明。</span><span class="sxs-lookup"><span data-stu-id="0d951-104">This Microsoft Application Virtualization (App-V) security guide provides instructions for administrators who are responsible for configuring the security features that were selected for the App-V deployment.</span></span>

<span data-ttu-id="0d951-105">**注意** 本文档不提供选择特定安全选项的指南。</span><span class="sxs-lookup"><span data-stu-id="0d951-105">**Note** This documentation does not provide guidance for choosing the specific security options.</span></span> <span data-ttu-id="0d951-106">此信息在适用于的应用程序-V 安全最佳做法白皮书中提供 <https://go.microsoft.com/fwlink/?LinkId=127120> 。</span><span class="sxs-lookup"><span data-stu-id="0d951-106">That information is provided in the App-V Security Best Practices white paper available at <https://go.microsoft.com/fwlink/?LinkId=127120>.</span></span>

 

<span data-ttu-id="0d951-107">作为使用本指南的 app-v 管理员，你应该熟悉以下与安全相关的技术：</span><span class="sxs-lookup"><span data-stu-id="0d951-107">As an App-V administrator using this guide, you should be familiar with the following security-related technologies:</span></span>

-   <span data-ttu-id="0d951-108">Active Directory 域服务</span><span class="sxs-lookup"><span data-stu-id="0d951-108">Active Directory Domain Services</span></span>

-   <span data-ttu-id="0d951-109">公钥基础结构（PKI）</span><span class="sxs-lookup"><span data-stu-id="0d951-109">Public key infrastructure (PKI)</span></span>

-   <span data-ttu-id="0d951-110">Internet 协议安全（IPsec）</span><span class="sxs-lookup"><span data-stu-id="0d951-110">Internet Protocol Security (IPsec)</span></span>

-   <span data-ttu-id="0d951-111">组策略</span><span class="sxs-lookup"><span data-stu-id="0d951-111">Group Policies</span></span>

-   <span data-ttu-id="0d951-112">Internet information Services （IIS）</span><span class="sxs-lookup"><span data-stu-id="0d951-112">Internet Information Services (IIS)</span></span>

## <span data-ttu-id="0d951-113">APP-V 基础结构组件</span><span class="sxs-lookup"><span data-stu-id="0d951-113">APP-V Infrastructure Components</span></span>


<span data-ttu-id="0d951-114">在规划增强的安全 App-v 环境时，你可以考虑多种不同的基础结构模型。</span><span class="sxs-lookup"><span data-stu-id="0d951-114">When planning an enhanced security App-V environment, you can consider several different infrastructure models.</span></span>

<span data-ttu-id="0d951-115">**注意** 有关 App-v 基础结构模型的详细信息，请参阅以下文档：</span><span class="sxs-lookup"><span data-stu-id="0d951-115">**Note** For more information about App-V infrastructure models, see the following documentation:</span></span>

-   [<span data-ttu-id="0d951-116">App-v 规划和部署指南</span><span class="sxs-lookup"><span data-stu-id="0d951-116">App-V Planning and Deployment Guide</span></span>](https://go.microsoft.com/fwlink/?LinkId=122063)

-   [<span data-ttu-id="0d951-117">基础结构规划和设计指南系列</span><span class="sxs-lookup"><span data-stu-id="0d951-117">Infrastructure Planning and Design Guide Series</span></span>](https://go.microsoft.com/fwlink/?LinkId=151986)

 

<span data-ttu-id="0d951-118">这些模型将使用下图中所示的部分，但可能不是所有的 App-v 组件。</span><span class="sxs-lookup"><span data-stu-id="0d951-118">These models utilize some but possibly not all of the App-V components depicted in the following illustration.</span></span>

![app-v 分支 office 图表](images/appvbranchoffices.gif)

<a href="" id="application-virtualization--app-v--management-server"></a><span data-ttu-id="0d951-120">应用程序虚拟化（App-v）管理服务器</span><span class="sxs-lookup"><span data-stu-id="0d951-120">Application Virtualization (App-V) Management Server</span></span>  
<span data-ttu-id="0d951-121">App-v 管理服务器对程序包内容进行流式处理，并将快捷方式和文件类型关联发布到 App-v 客户端。</span><span class="sxs-lookup"><span data-stu-id="0d951-121">The App-V Management Server streams the package content and publishes the shortcuts and file-type associations to the App-V Client.</span></span> <span data-ttu-id="0d951-122">App-v 管理服务器还支持活动升级、许可证管理和可用于报告的数据库。</span><span class="sxs-lookup"><span data-stu-id="0d951-122">The App-V Management Server also supports active upgrade, license management, and a database that can be used for reporting.</span></span>

<a href="" id="application-virtualization--app-v--streaming-server"></a><span data-ttu-id="0d951-123">应用程序虚拟化（app-v）流式处理服务器</span><span class="sxs-lookup"><span data-stu-id="0d951-123">Application Virtualization (App-V) Streaming Server</span></span>  
<span data-ttu-id="0d951-124">App-v 流服务器托管用于流处理的程序包，用于在分支机构等环境中处理 V 客户端，在这种情况下，连接到 app-v 管理服务器的连接的带宽不足以流式处理程序包内容到客户端。</span><span class="sxs-lookup"><span data-stu-id="0d951-124">The App-V Streaming Server hosts the packages for streaming to App-V Clients in environments such as branch offices, where the bandwidth of the connection to the App-V Management Server is insufficient for streaming package content to clients.</span></span> <span data-ttu-id="0d951-125">流服务器仅包含流式处理功能，并且不会向你提供 app-v 管理控制台或 App-v 管理 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="0d951-125">The Streaming Server contains only streaming functionality and does not provide you with the App-V Management Console or the App-V Management Web Service.</span></span>

<a href="" id="application-virtualization--app-v--data-store"></a><span data-ttu-id="0d951-126">应用程序虚拟化（App-v）数据存储</span><span class="sxs-lookup"><span data-stu-id="0d951-126">Application Virtualization (App-V) Data Store</span></span>  
<span data-ttu-id="0d951-127">SQL 数据库中的 App-v 数据存储保留与 App-v 基础结构相关的信息。</span><span class="sxs-lookup"><span data-stu-id="0d951-127">The App-V data store, in the SQL database, retains information related to the App-V infrastructure.</span></span> <span data-ttu-id="0d951-128">App-v 数据存储中的信息包括所有应用程序记录、应用程序分配以及管理应用程序虚拟化环境的组。</span><span class="sxs-lookup"><span data-stu-id="0d951-128">The information in the App-V data store includes all application records, application assignments, and which groups manage the Application Virtualization environment.</span></span>

<a href="" id="application-virtualization--app-v--management-service"></a><span data-ttu-id="0d951-129">应用程序虚拟化（App-v）管理服务</span><span class="sxs-lookup"><span data-stu-id="0d951-129">Application Virtualization (App-V) Management Service</span></span>  
<span data-ttu-id="0d951-130">App-v 管理服务将读/写请求传递到 Application Virtualization 数据存储。</span><span class="sxs-lookup"><span data-stu-id="0d951-130">The App-V Management Service communicates read/write requests to the Application Virtualization data store.</span></span> <span data-ttu-id="0d951-131">该组件可以与 App-v 管理服务器安装在同一台计算机上，也可以安装在安装了 IIS 的单独计算机上。</span><span class="sxs-lookup"><span data-stu-id="0d951-131">This component can be installed on the same computer as the App-V Management Server or on a separate computer with IIS installed.</span></span>

<a href="" id="application-virtualization--app-v--management-console"></a><span data-ttu-id="0d951-132">应用程序虚拟化（App-v）管理控制台</span><span class="sxs-lookup"><span data-stu-id="0d951-132">Application Virtualization (App-V) Management Console</span></span>  
<span data-ttu-id="0d951-133">App-v 管理控制台是用于 App-v 服务器管理的管理单元管理实用工具。</span><span class="sxs-lookup"><span data-stu-id="0d951-133">The App-V Management Console is a snap-in management utility for App-V Server administration.</span></span> <span data-ttu-id="0d951-134">该组件可以与 App-v 服务器安装在同一台计算机上，也可以安装在具有 MMC 3.0 和的单独工作站上。已安装 NET 2.0。</span><span class="sxs-lookup"><span data-stu-id="0d951-134">This component can be installed on the same computer as the App-V Server or on a separate workstation that has MMC3.0 and .NET2.0 installed.</span></span>

<a href="" id="application-virtualization--app-v--sequencer"></a><span data-ttu-id="0d951-135">应用程序虚拟化（App-v） Sequencer</span><span class="sxs-lookup"><span data-stu-id="0d951-135">Application Virtualization (App-V) Sequencer</span></span>  
<span data-ttu-id="0d951-136">App-v 排序器监视和捕获应用程序的安装并创建虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="0d951-136">The App-V Sequencer monitors and captures the installation of applications and creates virtual application packages.</span></span> <span data-ttu-id="0d951-137">Sequencer 的输出包含应用程序图标、包含应用程序定义信息的 OSD 文件、程序包清单文件和包含应用程序内容文件的 SFT 文件。</span><span class="sxs-lookup"><span data-stu-id="0d951-137">The output of the Sequencer consists of the application icon, the OSD file containing application definition information, a package manifest file, and an SFT file containing the application’s content files.</span></span> <span data-ttu-id="0d951-138">或者，可以创建 Windows Installer 文件，以便在不使用 App-v 基础结构的情况下安装程序包。</span><span class="sxs-lookup"><span data-stu-id="0d951-138">Optionally, a Windows Installer file can be created for installing the package without using the App-V infrastructure.</span></span>

<a href="" id="application-virtualization--app-v--client"></a><span data-ttu-id="0d951-139">应用程序虚拟化（app-v）客户端</span><span class="sxs-lookup"><span data-stu-id="0d951-139">Application Virtualization (App-V) Client</span></span>  
<span data-ttu-id="0d951-140">App-v Client 安装在 app-v 桌面客户端计算机或 App-v 终端服务客户端计算机上。</span><span class="sxs-lookup"><span data-stu-id="0d951-140">The App-V Client is installed on the App-V Desktop Client computer or on the App-V Terminal Services Client computer.</span></span> <span data-ttu-id="0d951-141">它为虚拟应用程序包提供虚拟环境。</span><span class="sxs-lookup"><span data-stu-id="0d951-141">It provides the virtual environment for the virtual application packages.</span></span> <span data-ttu-id="0d951-142">App-v 客户端管理与应用程序虚拟化服务器的缓存、虚拟应用程序发布刷新和交互的程序包流。</span><span class="sxs-lookup"><span data-stu-id="0d951-142">The App-V Client manages the package streaming to the cache, virtual application publishing refresh, and interaction with the Application Virtualization Servers.</span></span>

 

 





