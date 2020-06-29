---
title: 如何为基于服务器的部署配置服务器
description: 如何为基于服务器的部署配置服务器
author: dansimp
ms.assetid: 6371c37a-46eb-44e8-ad6b-4430c866c8b4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4c60ae89bc42fddad8aeb6a4f6df0f2c0b4ee4f2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801608"
---
# <span data-ttu-id="a6f3e-103">如何为基于服务器的部署配置服务器</span><span class="sxs-lookup"><span data-stu-id="a6f3e-103">How to Configure Servers for Server-Based Deployment</span></span>


<span data-ttu-id="a6f3e-104">本部分提供了可用于配置 Microsoft System Center 应用程序虚拟化（App-v）管理服务器和 Microsoft System Center 应用程序虚拟化流服务器以及 Internet Information Services （IIS）和文件服务器（适用于基于应用程序虚拟服务器的部署策略）的过程。</span><span class="sxs-lookup"><span data-stu-id="a6f3e-104">This section provides procedures you can use to configure the Microsoft System Center Application Virtualization (App-V) Management Servers and Microsoft System Center Application Virtualization Streaming Servers, and the Internet Information Services (IIS) and file servers, as appropriate for your Application Virtualization Server-based deployment strategy.</span></span>

## <span data-ttu-id="a6f3e-105">本部分内容</span><span class="sxs-lookup"><span data-stu-id="a6f3e-105">In This Section</span></span>


<a href="" id="how-to-configure-the-application-virtualization-management-servers"></a>[<span data-ttu-id="a6f3e-106">如何配置 Application Virtualization Management Server</span><span class="sxs-lookup"><span data-stu-id="a6f3e-106">How to Configure the Application Virtualization Management Servers</span></span>](how-to-configure-the-application-virtualization-management-servers.md)  
<span data-ttu-id="a6f3e-107">提供配置应用程序虚拟化管理服务器的分步过程。</span><span class="sxs-lookup"><span data-stu-id="a6f3e-107">Provides a step-by-step procedure for configuring the Application Virtualization Management Servers.</span></span>

<a href="" id="how-to-configure-the-application-virtualization-streaming-servers"></a>[<span data-ttu-id="a6f3e-108">如何配置 Application Virtualization Streaming Server</span><span class="sxs-lookup"><span data-stu-id="a6f3e-108">How to Configure the Application Virtualization Streaming Servers</span></span>](how-to-configure-the-application-virtualization-streaming-servers.md)  
<span data-ttu-id="a6f3e-109">提供配置应用程序虚拟化流服务器的分步过程。</span><span class="sxs-lookup"><span data-stu-id="a6f3e-109">Provides a step-by-step procedure for configuring the Application Virtualization Streaming Servers.</span></span>

<a href="" id="how-to-configure-the-server-for-iis"></a>[<span data-ttu-id="a6f3e-110">如何为 IIS 配置服务器</span><span class="sxs-lookup"><span data-stu-id="a6f3e-110">How to Configure the Server for IIS</span></span>](how-to-configure-the-server-for-iis.md)  
<span data-ttu-id="a6f3e-111">提供为基于服务器的部署配置 IIS 服务器的分步过程。</span><span class="sxs-lookup"><span data-stu-id="a6f3e-111">Provides a step-by-step procedure for configuring the IIS server for your server-based deployment.</span></span>

<a href="" id="how-to-configure-the-server-to-be-trusted-for-delegation"></a>[<span data-ttu-id="a6f3e-112">如何将服务器配置为受信任以进行委派</span><span class="sxs-lookup"><span data-stu-id="a6f3e-112">How to Configure the Server to be Trusted for Delegation</span></span>](how-to-configure-the-server-to-be-trusted-for-delegation.md)  
<span data-ttu-id="a6f3e-113">提供有关如何将服务器配置为受信任的委派的详细说明。</span><span class="sxs-lookup"><span data-stu-id="a6f3e-113">Provides detailed instructions about how to configure the server to be trusted for delegation.</span></span>

<a href="" id="configuring-the-firewall-for-the-app-v-servers"></a>[<span data-ttu-id="a6f3e-114">为 App-V Server 配置防火墙</span><span class="sxs-lookup"><span data-stu-id="a6f3e-114">Configuring the Firewall for the App-V Servers</span></span>](configuring-the-firewall-for-the-app-v-servers.md)  
<span data-ttu-id="a6f3e-115">介绍 app-v 服务器所需的防火墙设置。</span><span class="sxs-lookup"><span data-stu-id="a6f3e-115">Describes the firewall settings required for the App-V servers.</span></span>

<a href="" id="how-to-install-and-configure-the-default-application"></a>[<span data-ttu-id="a6f3e-116">如何安装和配置默认应用程序</span><span class="sxs-lookup"><span data-stu-id="a6f3e-116">How to Install and Configure the Default Application</span></span>](how-to-install-and-configure-the-default-application.md)  
<span data-ttu-id="a6f3e-117">介绍如何安装和配置用于测试 App-v 系统的默认应用程序。</span><span class="sxs-lookup"><span data-stu-id="a6f3e-117">Describes how to install and configure the default application for testing the App-V system.</span></span>

## <span data-ttu-id="a6f3e-118">相关主题</span><span class="sxs-lookup"><span data-stu-id="a6f3e-118">Related topics</span></span>


[<span data-ttu-id="a6f3e-119">基于 Application Virtualization Server 的方案概述</span><span class="sxs-lookup"><span data-stu-id="a6f3e-119">Application Virtualization Server-Based Scenario Overview</span></span>](application-virtualization-server-based-scenario-overview.md)

[<span data-ttu-id="a6f3e-120">基于电子软件分发的方案</span><span class="sxs-lookup"><span data-stu-id="a6f3e-120">Electronic Software Distribution-Based Scenario</span></span>](electronic-software-distribution-based-scenario.md)

[<span data-ttu-id="a6f3e-121">如何安装服务器和系统组件</span><span class="sxs-lookup"><span data-stu-id="a6f3e-121">How to Install the Servers and System Components</span></span>](how-to-install-the-servers-and-system-components.md)

 

 





