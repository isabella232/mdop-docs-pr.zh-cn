---
title: 基于电子软件分发的方案
description: 基于电子软件分发的方案
author: dansimp
ms.assetid: 18be0f8d-60ee-449b-aa83-93c86d1a908e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 52b9a30f2b1d403ec41090252f331a984225fd19
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802999"
---
# <span data-ttu-id="e0029-103">基于电子软件分发的方案</span><span class="sxs-lookup"><span data-stu-id="e0029-103">Electronic Software Distribution-Based Scenario</span></span>


<span data-ttu-id="e0029-104">如果您计划对您的 Microsoft Application Virtualization 环境使用电子软件分发（ESD）部署方案，请务必了解进入和受该决策影响的因素。</span><span class="sxs-lookup"><span data-stu-id="e0029-104">If you plan to use an electronic software distribution (ESD) deployment scenario for your Microsoft Application Virtualization environment, it is important to understand the factors that go into and are affected by that decision.</span></span> <span data-ttu-id="e0029-105">本部分中的主题介绍 ESD 方案，并提供有关程序包传递方法、传输协议和在部署策略中需要考虑的外部组件的信息。</span><span class="sxs-lookup"><span data-stu-id="e0029-105">The topics in this section describe the ESD scenario and provide information about package delivery methods, transmission protocols, and external components that you will need to consider in your deployment strategy.</span></span> <span data-ttu-id="e0029-106">你还可以使用本节中的过程完成部署，从服务器配置阶段到部署验证阶段。</span><span class="sxs-lookup"><span data-stu-id="e0029-106">You can also use the procedures in this section to complete your deployment, from the server configuration phase through the deployment verification phase.</span></span>

## <span data-ttu-id="e0029-107">本部分内容</span><span class="sxs-lookup"><span data-stu-id="e0029-107">In This Section</span></span>


<a href="" id="electronic-software-distribution-based-scenario-overview"></a>[<span data-ttu-id="e0029-108">基于电子软件分发的方案概述</span><span class="sxs-lookup"><span data-stu-id="e0029-108">Electronic Software Distribution-Based Scenario Overview</span></span>](electronic-software-distribution-based-scenario-overview.md)  
<span data-ttu-id="e0029-109">提供有关可用于基于 ESD 的部署的发布和流处理方法的重要信息。</span><span class="sxs-lookup"><span data-stu-id="e0029-109">Provides important information about the publishing and streaming methods you can use for an ESD-based deployment.</span></span>

<a href="" id="how-to-configure-servers-for-esd-based-deployment"></a>[<span data-ttu-id="e0029-110">如何为基于 ESD 的部署配置服务器</span><span class="sxs-lookup"><span data-stu-id="e0029-110">How to Configure Servers for ESD-Based Deployment</span></span>](how-to-configure-servers-for-esd-based-deployment.md)  
<span data-ttu-id="e0029-111">本部分提供了可用于配置基于电子软件分发的部署策略的应用程序虚拟化流服务器、IIS 服务器和文件服务器的过程。</span><span class="sxs-lookup"><span data-stu-id="e0029-111">This section provides procedures you can use to configure the Application Virtualization Streaming Servers, the IIS server, and the file server for your electronic software distribution–based deployment strategy.</span></span>

<a href="" id="how-to-install-the-client-by-using-the-command-line"></a>[<span data-ttu-id="e0029-112">如何使用命令行安装客户端</span><span class="sxs-lookup"><span data-stu-id="e0029-112">How to Install the Client by Using the Command Line</span></span>](how-to-install-the-client-by-using-the-command-line-new.md)  
<span data-ttu-id="e0029-113">提供使用 setup.exe 或 setup.msi 文件安装应用程序虚拟化客户端的命令行过程。</span><span class="sxs-lookup"><span data-stu-id="e0029-113">Provides command-line procedures for installing the Application Virtualization Client, using either the setup.exe or the setup.msi file.</span></span>

<a href="" id="how-to-uninstall-the-app-v-client"></a>[<span data-ttu-id="e0029-114">如何卸载 App-V Client</span><span class="sxs-lookup"><span data-stu-id="e0029-114">How to Uninstall the App-V Client</span></span>](how-to-uninstall-the-app-v-client.md)  
<span data-ttu-id="e0029-115">提供可用于确认是否已安装应用程序虚拟化客户端并正常运行的分步过程。</span><span class="sxs-lookup"><span data-stu-id="e0029-115">Provides a step-by-step procedure you can use to confirm that the Application Virtualization Client has been installed and is functioning correctly.</span></span>

<a href="" id="how-to-publish-a-virtual-application-on-the-client"></a>[<span data-ttu-id="e0029-116">如何在客户端上发布虚拟应用程序</span><span class="sxs-lookup"><span data-stu-id="e0029-116">How to Publish a Virtual Application on the Client</span></span>](how-to-publish-a-virtual-application-on-the-client.md)  
<span data-ttu-id="e0029-117">提供使用 Windows Installer 或 SFTMIME 发布应用程序包的命令行过程。</span><span class="sxs-lookup"><span data-stu-id="e0029-117">Provides command-line procedures for publishing an application package, using either Windows Installer or SFTMIME.</span></span>

## <span data-ttu-id="e0029-118">参考</span><span class="sxs-lookup"><span data-stu-id="e0029-118">Reference</span></span>


[<span data-ttu-id="e0029-119">Application Virtualization Client 安装程序命令行参数</span><span class="sxs-lookup"><span data-stu-id="e0029-119">Application Virtualization Client Installer Command-Line Parameters</span></span>](application-virtualization-client-installer-command-line-parameters.md)

## <span data-ttu-id="e0029-120">相关部分</span><span class="sxs-lookup"><span data-stu-id="e0029-120">Related Sections</span></span>


[<span data-ttu-id="e0029-121">基于 Application Virtualization Server 的方案</span><span class="sxs-lookup"><span data-stu-id="e0029-121">Application Virtualization Server-Based Scenario</span></span>](application-virtualization-server-based-scenario.md)

## <span data-ttu-id="e0029-122">相关主题</span><span class="sxs-lookup"><span data-stu-id="e0029-122">Related topics</span></span>


[<span data-ttu-id="e0029-123">Application Virtualization 部署和升级注意事项</span><span class="sxs-lookup"><span data-stu-id="e0029-123">Application Virtualization Deployment and Upgrade Considerations</span></span>](application-virtualization-deployment-and-upgrade-considerations.md)

[<span data-ttu-id="e0029-124">适用于 Application Virtualization Client 的独立传递方案</span><span class="sxs-lookup"><span data-stu-id="e0029-124">Stand-Alone Delivery Scenario for Application Virtualization Clients</span></span>](stand-alone-delivery-scenario-for-application-virtualization-clients.md)

 

 





