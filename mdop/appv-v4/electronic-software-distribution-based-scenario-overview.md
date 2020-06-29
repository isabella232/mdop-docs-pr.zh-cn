---
title: 基于电子软件分发的方案概述
description: 基于电子软件分发的方案概述
author: dansimp
ms.assetid: e9e94b8a-6cba-4de8-9b57-73897796b6a0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: cfbdf40f5ac0f61721c05d0da5cd49e910b16154
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803000"
---
# <span data-ttu-id="76c4d-103">基于电子软件分发的方案概述</span><span class="sxs-lookup"><span data-stu-id="76c4d-103">Electronic Software Distribution-Based Scenario Overview</span></span>


<span data-ttu-id="76c4d-104">如果您计划使用电子软件分发（ESD）解决方案来部署虚拟应用程序，请务必了解进入和受该决策影响的因素。</span><span class="sxs-lookup"><span data-stu-id="76c4d-104">If you plan to use an electronic software distribution (ESD) solution to deploy virtual applications, it is important to understand the factors that go into and are affected by that decision.</span></span> <span data-ttu-id="76c4d-105">本主题介绍使用基于 ESD 的方案的优点，并提供有关发布和打包流方法的信息，在你继续部署时需要考虑这些方法。</span><span class="sxs-lookup"><span data-stu-id="76c4d-105">This topic describes the benefits of using an ESD-based scenario and provides information about the publishing and package streaming methods that you will need to consider as you proceed with your deployment.</span></span>

<span data-ttu-id="76c4d-106">**重要提示** 无论使用哪种 ESD 解决方案，您都必须熟悉特定解决方案的要求。</span><span class="sxs-lookup"><span data-stu-id="76c4d-106">**Important** Whichever ESD solution you use, you must be familiar with the requirements of your particular solution.</span></span> <span data-ttu-id="76c4d-107">如果您使用的是 Microsoft 终结点配置管理器，请参阅配置管理器文档 <https://go.microsoft.com/fwlink/?LinkId=66999> 。</span><span class="sxs-lookup"><span data-stu-id="76c4d-107">If you are using Microsoft Endpoint Configuration Manager, see the Configuration Manager documentation at <https://go.microsoft.com/fwlink/?LinkId=66999>.</span></span>

 

<span data-ttu-id="76c4d-108">使用现有 ESD 系统可为你提供以下好处：</span><span class="sxs-lookup"><span data-stu-id="76c4d-108">Using an existing ESD system provides you with the following benefits:</span></span>

-   <span data-ttu-id="76c4d-109">消除了双重管理基础架构</span><span class="sxs-lookup"><span data-stu-id="76c4d-109">Eliminates dual management infrastructures</span></span>

-   <span data-ttu-id="76c4d-110">降低额外硬件的成本</span><span class="sxs-lookup"><span data-stu-id="76c4d-110">Reduces the cost of additional hardware</span></span>

-   <span data-ttu-id="76c4d-111">降低其他操作系统和数据库许可证的成本</span><span class="sxs-lookup"><span data-stu-id="76c4d-111">Reduces the cost of additional operating system and database licenses</span></span>

## <span data-ttu-id="76c4d-112">发布方法</span><span class="sxs-lookup"><span data-stu-id="76c4d-112">Publishing Methods</span></span>


<span data-ttu-id="76c4d-113">使用基于 ESD 的方案时，你可以选择将应用程序发布到客户端：</span><span class="sxs-lookup"><span data-stu-id="76c4d-113">When using an ESD-based scenario, you have the following choices for publishing the application to the clients:</span></span>

-   **<span data-ttu-id="76c4d-114">独立的 Windows Installer。</span><span class="sxs-lookup"><span data-stu-id="76c4d-114">Stand-alone Windows Installer.</span></span>** <span data-ttu-id="76c4d-115">Windows Installer 文件包含客户端用于配置程序包的清单和 OSD 和 .ICO 文件。</span><span class="sxs-lookup"><span data-stu-id="76c4d-115">The Windows Installer file contains the manifest and the OSD and ICO files the clients use to configure a package.</span></span> <span data-ttu-id="76c4d-116">Windows Installer 文件还将 SFT 文件复制到客户端，因为此方案不使用服务器。</span><span class="sxs-lookup"><span data-stu-id="76c4d-116">The Windows Installer file also copies the SFT file to the client because this scenario does not use a server.</span></span>

-   **<span data-ttu-id="76c4d-117">带有程序包清单的 Windows 安装程序。</span><span class="sxs-lookup"><span data-stu-id="76c4d-117">Windows Installer with the package manifest.</span></span>** <span data-ttu-id="76c4d-118">Windows Installer 文件包含客户端用于配置程序包的清单和 OSD 和 .ICO 文件。</span><span class="sxs-lookup"><span data-stu-id="76c4d-118">The Windows Installer file contains the manifest and the OSD and ICO files the clients use to configure a package.</span></span> <span data-ttu-id="76c4d-119">SFT 文件存储在服务器上。</span><span class="sxs-lookup"><span data-stu-id="76c4d-119">The SFT file is stored on a server.</span></span> <span data-ttu-id="76c4d-120">命令行参数将客户端定向到 SFT 文件的位置。</span><span class="sxs-lookup"><span data-stu-id="76c4d-120">A command-line parameter directs the client to the location of the SFT file.</span></span>

-   **<span data-ttu-id="76c4d-121">SFTMIME 命令。</span><span class="sxs-lookup"><span data-stu-id="76c4d-121">SFTMIME commands.</span></span>** <span data-ttu-id="76c4d-122">SFTMIME 命令与清单、OSD、.ICO 和 SFT 文件配合使用，以向客户端添加程序包。</span><span class="sxs-lookup"><span data-stu-id="76c4d-122">SFTMIME commands are used with the manifest, OSD, ICO, and SFT files to add packages to the client.</span></span> <span data-ttu-id="76c4d-123">清单文件必须位于客户端计算机上，或者必须可通过 UNC 路径进行访问。</span><span class="sxs-lookup"><span data-stu-id="76c4d-123">The manifest file must be on the client computer, or it must be accessible through a UNC path.</span></span> <span data-ttu-id="76c4d-124">根据客户端配置和命令行选项，OSD、.ICO 和 SFT 文件可以位于客户端计算机上或服务器上。</span><span class="sxs-lookup"><span data-stu-id="76c4d-124">Depending on the client configuration and the command-line options, the OSD, ICO, and SFT files can be on the client computer or on a server.</span></span>

<span data-ttu-id="76c4d-125">有关以前发布方法的详细信息，请参阅[确定发布方法](determine-your-publishing-method.md)。</span><span class="sxs-lookup"><span data-stu-id="76c4d-125">For more detailed information about the preceding publishing methods, see [Determine Your Publishing Method](determine-your-publishing-method.md).</span></span>

## <span data-ttu-id="76c4d-126">程序包流式处理方法</span><span class="sxs-lookup"><span data-stu-id="76c4d-126">Package Streaming Methods</span></span>


<span data-ttu-id="76c4d-127">你将需要确定你的应用程序虚拟化系统将用于将虚拟应用程序包（或 SFT 文件）从服务器传输到客户端的方法。</span><span class="sxs-lookup"><span data-stu-id="76c4d-127">You will need to determine the method your Application Virtualization System will use to stream the virtual application packages, or SFT files, from the server to the clients.</span></span> <span data-ttu-id="76c4d-128">以下流式处理选项可用：</span><span class="sxs-lookup"><span data-stu-id="76c4d-128">The following streaming options are available:</span></span>

-   **<span data-ttu-id="76c4d-129">应用程序虚拟化流服务器。</span><span class="sxs-lookup"><span data-stu-id="76c4d-129">Application Virtualization Streaming Server.</span></span>** <span data-ttu-id="76c4d-130">如果你在配置中使用应用程序虚拟流服务器，则将使用 RTSP 或 RTSPS 协议将 SFT 文件流到该服务器中的客户端。</span><span class="sxs-lookup"><span data-stu-id="76c4d-130">If you use an Application Virtualization Streaming Server in your configuration, the SFT files are streamed to the clients from that server using RTSP or RTSPS protocols.</span></span> <span data-ttu-id="76c4d-131">必须在计算机上安装服务器软件，并且必须通过注册表配置它，但此配置不依赖于诸如 SQL 或 Active Directory 域服务之类的服务。</span><span class="sxs-lookup"><span data-stu-id="76c4d-131">You must install the server software on a computer and you must configure it through the registry, but this configuration does not depend on services such as SQL or Active Directory Domain Services.</span></span> <span data-ttu-id="76c4d-132">SFT 文件存储在服务器上由客户端访问的位置。</span><span class="sxs-lookup"><span data-stu-id="76c4d-132">The SFT files are stored on the server at a location accessible by the clients.</span></span> <span data-ttu-id="76c4d-133">发布信息可通过任何分发机制分发给客户端。</span><span class="sxs-lookup"><span data-stu-id="76c4d-133">Publishing information can be distributed to the clients through any distribution mechanism.</span></span> <span data-ttu-id="76c4d-134">但是，当配置时，客户端将自动接收程序包升级，并且支持活动升级。</span><span class="sxs-lookup"><span data-stu-id="76c4d-134">However, when configured, the client receives package upgrades automatically and active upgrade is supported.</span></span>

-   **<span data-ttu-id="76c4d-135">应用程序虚拟化管理服务器。</span><span class="sxs-lookup"><span data-stu-id="76c4d-135">Application Virtualization Management Server.</span></span>** <span data-ttu-id="76c4d-136">如果你在配置中使用应用程序虚拟化管理服务器，则将使用 RTSP 或 RTSPS 协议将 SFT 文件流到该服务器中的客户端。</span><span class="sxs-lookup"><span data-stu-id="76c4d-136">If you use an Application Virtualization Management Server in your configuration, the SFT files are streamed to the clients from that server using RTSP or RTSPS protocols.</span></span> <span data-ttu-id="76c4d-137">可通过应用程序虚拟化管理控制台管理此服务器。</span><span class="sxs-lookup"><span data-stu-id="76c4d-137">You manage this server through the Application Virtualization Management Console.</span></span> <span data-ttu-id="76c4d-138">此配置使用 SQL 数据库和 Active Directory 服务。</span><span class="sxs-lookup"><span data-stu-id="76c4d-138">This configuration uses a SQL database and Active Directory services.</span></span> <span data-ttu-id="76c4d-139">服务器可以将发布信息分发给客户端，因此不需要其他发布机制。</span><span class="sxs-lookup"><span data-stu-id="76c4d-139">The server can distribute publishing information to the clients, so additional publishing mechanisms are not needed.</span></span>

-   **<span data-ttu-id="76c4d-140">文件服务器。</span><span class="sxs-lookup"><span data-stu-id="76c4d-140">File server.</span></span>** <span data-ttu-id="76c4d-141">如果你在配置中使用文件服务器，则将使用 SMB 协议将 SFT 文件传输到其他客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="76c4d-141">If you use a file server in your configuration, the SFT files are streamed to the other client computers by using SMB protocols.</span></span> <span data-ttu-id="76c4d-142">在此配置中使用的文件服务器通过在文件共享和 SFT 文件上创建访问控制列表（Acl）进行管理。</span><span class="sxs-lookup"><span data-stu-id="76c4d-142">File servers used in this configuration are managed by creating access control lists (ACLs) on the file shares and SFT files.</span></span> <span data-ttu-id="76c4d-143">必须小心，才能将客户端定向到文件服务器上的正确文件。</span><span class="sxs-lookup"><span data-stu-id="76c4d-143">Care must be taken to direct the clients to the correct files on the file server.</span></span>

-   **<span data-ttu-id="76c4d-144">IIS 服务器。</span><span class="sxs-lookup"><span data-stu-id="76c4d-144">IIS server.</span></span>** <span data-ttu-id="76c4d-145">如果你在配置中使用 IIS 服务器，则将从该服务器使用 HTTP 或 HTTPS 协议将 SFT 文件传输到客户端。</span><span class="sxs-lookup"><span data-stu-id="76c4d-145">If you use an IIS server in your configuration, the SFT files are streamed to the clients from that server using HTTP or HTTPS protocols.</span></span> <span data-ttu-id="76c4d-146">IIS 服务器易于配置和管理。</span><span class="sxs-lookup"><span data-stu-id="76c4d-146">The IIS server is easy to configure and manage.</span></span> <span data-ttu-id="76c4d-147">必须小心，才能将客户端定向到 IIS 服务器上的正确文件。</span><span class="sxs-lookup"><span data-stu-id="76c4d-147">Care must be taken to direct the clients to the correct files on the IIS server.</span></span>

<span data-ttu-id="76c4d-148">有关上述流方法的更多详细信息，请参阅[确定流式处理方法](determine-your-streaming-method.md)。</span><span class="sxs-lookup"><span data-stu-id="76c4d-148">For more detailed information about the preceding streaming methods, see [Determine Your Streaming Method](determine-your-streaming-method.md).</span></span>

## <span data-ttu-id="76c4d-149">相关主题</span><span class="sxs-lookup"><span data-stu-id="76c4d-149">Related topics</span></span>


[<span data-ttu-id="76c4d-150">Application Virtualization Client 安装程序命令行参数</span><span class="sxs-lookup"><span data-stu-id="76c4d-150">Application Virtualization Client Installer Command-Line Parameters</span></span>](application-virtualization-client-installer-command-line-parameters.md)

[<span data-ttu-id="76c4d-151">基于 Application Virtualization Server 的方案</span><span class="sxs-lookup"><span data-stu-id="76c4d-151">Application Virtualization Server-Based Scenario</span></span>](application-virtualization-server-based-scenario.md)

[<span data-ttu-id="76c4d-152">确定发布方法</span><span class="sxs-lookup"><span data-stu-id="76c4d-152">Determine Your Publishing Method</span></span>](determine-your-publishing-method.md)

[<span data-ttu-id="76c4d-153">确定流式处理方法</span><span class="sxs-lookup"><span data-stu-id="76c4d-153">Determine Your Streaming Method</span></span>](determine-your-streaming-method.md)

[<span data-ttu-id="76c4d-154">基于电子软件分发的方案</span><span class="sxs-lookup"><span data-stu-id="76c4d-154">Electronic Software Distribution-Based Scenario</span></span>](electronic-software-distribution-based-scenario.md)

[<span data-ttu-id="76c4d-155">SFTMIME 命令引用</span><span class="sxs-lookup"><span data-stu-id="76c4d-155">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





