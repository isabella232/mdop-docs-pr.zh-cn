---
title: 监视 Application Virtualization Server
description: 监视 Application Virtualization Server
author: dansimp
ms.assetid: d84355ae-4fe4-41d9-ac3a-3eaa32d9a61f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a53c0c37ca609c701727a7f4e18019a9f20110ed
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798912"
---
# <span data-ttu-id="3e2b2-103">监视 Application Virtualization Server</span><span class="sxs-lookup"><span data-stu-id="3e2b2-103">Monitoring Application Virtualization Servers</span></span>


<span data-ttu-id="3e2b2-104">若要简化应用程序虚拟化（App-v）服务器管理，您可以使用 System Center Operations Manager2007 管理包。</span><span class="sxs-lookup"><span data-stu-id="3e2b2-104">To simplify Application Virtualization (App-V) Server management, you can use the System Center Operations Manager2007 Management Pack.</span></span> <span data-ttu-id="3e2b2-105">此管理包仅支持应用程序虚拟化（App-v）4.5 服务器;它不支持以前的服务器版本。</span><span class="sxs-lookup"><span data-stu-id="3e2b2-105">This Management Pack supports only Application Virtualization (App-V) 4.5 servers; it does not support previous server versions.</span></span> <span data-ttu-id="3e2b2-106">管理包最大化了应用-v 服务器可用性以处理 app-v 客户端请求。</span><span class="sxs-lookup"><span data-stu-id="3e2b2-106">The Management Pack maximizes App-V Server availability for handling App-V Client requests.</span></span>

## <span data-ttu-id="3e2b2-107">状态指示器</span><span class="sxs-lookup"><span data-stu-id="3e2b2-107">Status Indicators</span></span>


<span data-ttu-id="3e2b2-108">App-v Server 运行状况状态指示器采用颜色编码。</span><span class="sxs-lookup"><span data-stu-id="3e2b2-108">The App-V Server health status indicators are color-coded.</span></span> <span data-ttu-id="3e2b2-109">颜色表示以下状态值：</span><span class="sxs-lookup"><span data-stu-id="3e2b2-109">The colors represent the following status values:</span></span>

-   <span data-ttu-id="3e2b2-110">无颜色表示服务器运行时没有不可恢复的错误。</span><span class="sxs-lookup"><span data-stu-id="3e2b2-110">No color indicates that the server is running without non-recoverable errors.</span></span>

-   <span data-ttu-id="3e2b2-111">黄色表示其中一个组件运行不正常。</span><span class="sxs-lookup"><span data-stu-id="3e2b2-111">Yellow indicates that one of the components is not functioning correctly.</span></span> <span data-ttu-id="3e2b2-112">服务器的整体功能已降级，但服务器仍然可用。</span><span class="sxs-lookup"><span data-stu-id="3e2b2-112">The overall functionality of the server is degraded, but the server is still available.</span></span>

-   <span data-ttu-id="3e2b2-113">红色表示服务器不可用，并且无法提供关键服务或与外部服务依赖关系进行通信。</span><span class="sxs-lookup"><span data-stu-id="3e2b2-113">Red indicates that the server is not available and that it cannot provide key services or communicate with external service dependencies.</span></span>

## <span data-ttu-id="3e2b2-114">监视条件</span><span class="sxs-lookup"><span data-stu-id="3e2b2-114">Monitoring Criteria</span></span>


<span data-ttu-id="3e2b2-115">管理包监视服务器运行状况的以下方面：</span><span class="sxs-lookup"><span data-stu-id="3e2b2-115">The Management Pack monitors the following aspects of server health:</span></span>

-   <span data-ttu-id="3e2b2-116">服务器状态-监视服务器事件以验证服务器是否提供其预期服务。</span><span class="sxs-lookup"><span data-stu-id="3e2b2-116">Server Status—monitors server events to validate that the server is providing its expected services.</span></span>

-   <span data-ttu-id="3e2b2-117">数据存储访问-跟踪一个或多个 App-v 管理服务器的功能，以便与 App-v 数据存储进行访问和通信。</span><span class="sxs-lookup"><span data-stu-id="3e2b2-117">Data Store Access—tracks the ability of one or more of the App-V Management Servers to access and communicate with the App-V data store.</span></span>

-   <span data-ttu-id="3e2b2-118">内容数据访问-监视对 \\Content 目录（可能是本地目录或网络共享）的访问权限，以及读取所请求的文件的功能。</span><span class="sxs-lookup"><span data-stu-id="3e2b2-118">Content Data Access—monitors access to the \\Content directory, which might be a local directory or a network share, and the ability to read the requested files.</span></span>

-   <span data-ttu-id="3e2b2-119">安全性——通过 app-v 服务器的证书和安全通信报告错误。</span><span class="sxs-lookup"><span data-stu-id="3e2b2-119">Security—reports errors with the App-V Server’s certificate and secure communications.</span></span>

-   <span data-ttu-id="3e2b2-120">客户端请求处理-监视一个或多个 App-v 服务器处理和正确响应客户端请求的能力。</span><span class="sxs-lookup"><span data-stu-id="3e2b2-120">Client Request Handling—monitors the ability of one or more of the App-V Servers to handle and correctly respond to client requests.</span></span> <span data-ttu-id="3e2b2-121">这些请求包括将诸如 "配置请求"、"软件包加载请求" 和 "退出顺序请求" 之类的项目发布。</span><span class="sxs-lookup"><span data-stu-id="3e2b2-121">These requests include publishing such items as configuration requests, package load requests, and out of sequence requests.</span></span>

-   <span data-ttu-id="3e2b2-122">服务器配置-检查 App-v 服务器的配置设置。</span><span class="sxs-lookup"><span data-stu-id="3e2b2-122">Server Configuration—checks the configuration settings of the App-V Server.</span></span> <span data-ttu-id="3e2b2-123">这些配置设置包括注册表中和 App-v 数据存储中的设置。</span><span class="sxs-lookup"><span data-stu-id="3e2b2-123">These configuration settings include the settings in the registry and in the App-V data store.</span></span>

## <span data-ttu-id="3e2b2-124">服务器差异</span><span class="sxs-lookup"><span data-stu-id="3e2b2-124">Server Differences</span></span>


<span data-ttu-id="3e2b2-125">App-v 管理服务器和 App-v 流式处理服务器之间的主要区别如下所示：</span><span class="sxs-lookup"><span data-stu-id="3e2b2-125">The main differences between the App-V Management Server and the App-V Streaming Server are as follows:</span></span>

-   <span data-ttu-id="3e2b2-126">App-v 管理服务器可提供发布、流式处理、管理和报告服务。</span><span class="sxs-lookup"><span data-stu-id="3e2b2-126">App-V Management Servers can provide publishing, streaming, management, and reporting services.</span></span> <span data-ttu-id="3e2b2-127">因此，管理包可以管理 app-v 管理服务器的更多方面，而不是它可以在仅提供软件包流的 App-v 流式处理服务器上管理。</span><span class="sxs-lookup"><span data-stu-id="3e2b2-127">Therefore, the Management Pack can manage more aspects of the App-V Management Server than it can manage on the App-V Streaming Server, which provides only package streaming.</span></span>

-   <span data-ttu-id="3e2b2-128">App-v 流式处理服务器没有 App-v 数据存储，因此不会监视数据存储访问。</span><span class="sxs-lookup"><span data-stu-id="3e2b2-128">The App-V Streaming Server does not have an App-V data store, so data store access is not monitored.</span></span> <span data-ttu-id="3e2b2-129">在注册表中管理 App-v 流服务器的配置信息。</span><span class="sxs-lookup"><span data-stu-id="3e2b2-129">The configuration information for the App-V Streaming Server is managed in the registry.</span></span>

-   <span data-ttu-id="3e2b2-130">App-v 流式处理服务器不使用 app-v Server 管理控制台界面;使用其他工具管理配置。</span><span class="sxs-lookup"><span data-stu-id="3e2b2-130">The App-V Streaming Server does not use the App-V Server Management Console interface; use other tools to manage the configuration.</span></span>

## <span data-ttu-id="3e2b2-131">相关主题</span><span class="sxs-lookup"><span data-stu-id="3e2b2-131">Related topics</span></span>


[<span data-ttu-id="3e2b2-132">Application Virtualization Server</span><span class="sxs-lookup"><span data-stu-id="3e2b2-132">Application Virtualization Server</span></span>](application-virtualization-server.md)

 

 





