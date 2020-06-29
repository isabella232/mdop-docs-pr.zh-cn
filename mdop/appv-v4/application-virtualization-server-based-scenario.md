---
title: 基于 Application Virtualization Server 的方案
description: 基于 Application Virtualization Server 的方案
author: dansimp
ms.assetid: 10ed0b18-087d-470f-951b-5083f4cb076f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d6699bdc734258f67e4938e33266a2f061531939
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802252"
---
# <span data-ttu-id="df12e-103">基于 Application Virtualization Server 的方案</span><span class="sxs-lookup"><span data-stu-id="df12e-103">Application Virtualization Server-Based Scenario</span></span>


<span data-ttu-id="df12e-104">如果你打算对 Microsoft Application Virtualization （App-v）环境使用基于服务器的部署方案，你应该了解应用程序虚拟化管理服务器和应用程序虚拟化流服务器之间的差异。</span><span class="sxs-lookup"><span data-stu-id="df12e-104">If you plan to use a server-based deployment scenario for your Microsoft Application Virtualization (App-V) environment, you should understand the differences between the Application Virtualization Management Server and the Application Virtualization Streaming Server.</span></span> <span data-ttu-id="df12e-105">本部分中的主题描述了这些差异，还提供了有关程序包传递方法、传输协议和外部组件的信息，在你继续部署时必须考虑这些信息。</span><span class="sxs-lookup"><span data-stu-id="df12e-105">The topics in this section describe those differences and also provide information about package delivery methods, transmission protocols, and external components that you have to consider as you continue with your deployment.</span></span> <span data-ttu-id="df12e-106">本节还提供安装和配置 App-v 管理服务器和应用程序虚拟化流服务器的分步过程。</span><span class="sxs-lookup"><span data-stu-id="df12e-106">This section also provides step-by-step procedures for installing and configuring the App-V Management Server and the Application Virtualization Streaming Servers.</span></span>

## <span data-ttu-id="df12e-107">本部分内容</span><span class="sxs-lookup"><span data-stu-id="df12e-107">In This Section</span></span>


<a href="" id="application-virtualization-server-based-scenario-overview"></a>[<span data-ttu-id="df12e-108">基于 Application Virtualization Server 的方案概述</span><span class="sxs-lookup"><span data-stu-id="df12e-108">Application Virtualization Server-Based Scenario Overview</span></span>](application-virtualization-server-based-scenario-overview.md)  
<span data-ttu-id="df12e-109">提供有关应用程序虚拟化管理服务器、应用程序虚拟流服务器以及与基于服务器的部署计划相关的程序包传递方法、协议和外部组件的重要部署信息。</span><span class="sxs-lookup"><span data-stu-id="df12e-109">Provides important deployment information about the Application Virtualization Management Server, the Application Virtualization Streaming Server, and the package delivery methods, protocols, and external components relevant to your server-based deployment plan.</span></span>

<a href="" id="how-to-install-the-servers-and-system-components"></a>[<span data-ttu-id="df12e-110">如何安装服务器和系统组件</span><span class="sxs-lookup"><span data-stu-id="df12e-110">How to Install the Servers and System Components</span></span>](how-to-install-the-servers-and-system-components.md)  
<span data-ttu-id="df12e-111">介绍如何安装基于服务器的部署所需的 Microsoft Application Virtualization 平台组件。</span><span class="sxs-lookup"><span data-stu-id="df12e-111">Describes how to install the Microsoft Application Virtualization platform components required for your server-based deployment.</span></span>

<a href="" id="how-to-configure-servers-for-server-based-deployment"></a>[<span data-ttu-id="df12e-112">如何为基于服务器的部署配置服务器</span><span class="sxs-lookup"><span data-stu-id="df12e-112">How to Configure Servers for Server-Based Deployment</span></span>](how-to-configure-servers-for-server-based-deployment.md)  
<span data-ttu-id="df12e-113">介绍如何配置应用程序虚拟化管理服务器、应用程序虚拟化流服务器、Internet Information Integration （IIS）服务器和文件服务器。</span><span class="sxs-lookup"><span data-stu-id="df12e-113">Describes how to configure the Application Virtualization Management Server, the Application Virtualization Streaming Server, the Internet Information Integration (IIS) server, and the file server.</span></span>

<a href="" id="how-to-configure-a-read-only-cache-on-the-app-v-client--vdi-"></a>[<span data-ttu-id="df12e-114">如何在 App-V Client (VDI) 上配置只读缓存</span><span class="sxs-lookup"><span data-stu-id="df12e-114">How to Configure a Read-only Cache on the App-V Client (VDI)</span></span>](how-to-configure-a-read-only-cache-on-the-app-v-client--vdi-.md)  
<span data-ttu-id="df12e-115">介绍如何配置 App-v 客户端以使用只读缓存。</span><span class="sxs-lookup"><span data-stu-id="df12e-115">Describes how to configure the App-V client to use read-only cache.</span></span>

<a href="" id="how-to-configure-a-read-only-cache-on-the-app-v-client--rds-"></a>[<span data-ttu-id="df12e-116">如何在 App-V Client (RDS) 上配置只读缓存</span><span class="sxs-lookup"><span data-stu-id="df12e-116">How to Configure a Read-only Cache on the App-V Client (RDS)</span></span>](how-to-configure-a-read-only-cache-on-the-app-v-client--rds--sp1.md)  
<span data-ttu-id="df12e-117">介绍如何配置 App-v 客户端以使用只读缓存。</span><span class="sxs-lookup"><span data-stu-id="df12e-117">Describes how to configure the App-V client to use read-only cache.</span></span>

<a href="" id="how-to-configure-microsoft-sql-server-mirroring-support-for-app-v"></a>[<span data-ttu-id="df12e-118">如何为 App-V 配置 Microsoft SQL Server 镜像支持</span><span class="sxs-lookup"><span data-stu-id="df12e-118">How to Configure Microsoft SQL Server Mirroring Support for App-V</span></span>](how-to-configure-microsoft-sql-server-mirroring-support-for-app-v.md)  
<span data-ttu-id="df12e-119">介绍如何使用适用于 app-v 系统的 Microsoft SQL Server 配置数据库镜像。</span><span class="sxs-lookup"><span data-stu-id="df12e-119">Describes how to configure database mirroring by using Microsoft SQL Server for your App-V system.</span></span>

## <span data-ttu-id="df12e-120">参考</span><span class="sxs-lookup"><span data-stu-id="df12e-120">Reference</span></span>


[<span data-ttu-id="df12e-121">Application Virtualization Client 安装程序命令行参数</span><span class="sxs-lookup"><span data-stu-id="df12e-121">Application Virtualization Client Installer Command-Line Parameters</span></span>](application-virtualization-client-installer-command-line-parameters.md)

## <span data-ttu-id="df12e-122">相关部分</span><span class="sxs-lookup"><span data-stu-id="df12e-122">Related Sections</span></span>


[<span data-ttu-id="df12e-123">基于电子软件分发的方案</span><span class="sxs-lookup"><span data-stu-id="df12e-123">Electronic Software Distribution-Based Scenario</span></span>](electronic-software-distribution-based-scenario.md)

## <span data-ttu-id="df12e-124">相关主题</span><span class="sxs-lookup"><span data-stu-id="df12e-124">Related topics</span></span>


[<span data-ttu-id="df12e-125">Application Virtualization 部署和升级注意事项</span><span class="sxs-lookup"><span data-stu-id="df12e-125">Application Virtualization Deployment and Upgrade Considerations</span></span>](application-virtualization-deployment-and-upgrade-considerations.md)

[<span data-ttu-id="df12e-126">适用于 Application Virtualization Client 的独立传递方案</span><span class="sxs-lookup"><span data-stu-id="df12e-126">Stand-Alone Delivery Scenario for Application Virtualization Clients</span></span>](stand-alone-delivery-scenario-for-application-virtualization-clients.md)

 

 





