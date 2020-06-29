---
title: 使用 Application Virtualization Server 作为程序包管理解决方案
description: 使用 Application Virtualization Server 作为程序包管理解决方案
author: dansimp
ms.assetid: 41597355-e7bb-45e2-b300-7b1724419975
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2b81ed3ab6fa3a70fe4780904059091f22579d9e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798708"
---
# <span data-ttu-id="14853-103">使用 Application Virtualization Server 作为程序包管理解决方案</span><span class="sxs-lookup"><span data-stu-id="14853-103">Using Application Virtualization Servers as a Package Management Solution</span></span>


<span data-ttu-id="14853-104">如果您没有已有的 ESD 系统来部署应用程序虚拟化解决方案或不想使用其中一个，则需要安装一个或多个应用程序虚拟化管理服务器作为系统体系结构的核心。</span><span class="sxs-lookup"><span data-stu-id="14853-104">If you do not have an existing ESD system to deploy your Application Virtualization solution or do not wish to use one, you will need to install one or more Application Virtualization Management Servers as the core of your system architecture.</span></span> <span data-ttu-id="14853-105">应用程序虚拟化管理服务器需要专用的服务器计算机，并且需要 Microsoft SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="14853-105">The Application Virtualization Management Server requires a dedicated server computer and needs a Microsoft SQL Server database.</span></span> <span data-ttu-id="14853-106">数据库可以位于同一服务器上，也可以在可通过高速 LAN 连接的应用程序虚拟化管理服务器访问的企业数据库服务器上配置。</span><span class="sxs-lookup"><span data-stu-id="14853-106">The database can be on the same server, or it can be configured on a corporate database server that is accessible to the Application Virtualization Management Server over a high-speed LAN connection.</span></span> <span data-ttu-id="14853-107">此外，你需要在应用程序虚拟化管理服务器或指定的管理工作站上安装 Microsoft Application Virtualization 管理控制台，并且你将需要安装 Microsoft Application Virtualization Management Web 服务，该服务还可以安装在应用程序虚拟化管理服务器或单独的 IIS 服务器上。</span><span class="sxs-lookup"><span data-stu-id="14853-107">In addition, you will need to install the Microsoft Application Virtualization Management Console, on either the Application Virtualization Management Server or on a designated management workstation, and you will need to install the Microsoft Application Virtualization Management Web Service, which can also be installed on the Application Virtualization Management Server or on a separate IIS server.</span></span> <span data-ttu-id="14853-108">应用程序虚拟化管理控制台用于连接到应用程序虚拟化管理 Web 服务，使系统管理员能够与应用程序虚拟化管理服务器交互。</span><span class="sxs-lookup"><span data-stu-id="14853-108">The Application Virtualization Management Console is used to connect to the Application Virtualization Management Web Service, enabling the system administrator to interact with the Application Virtualization Management Server.</span></span>

<span data-ttu-id="14853-109">**注意** 对应用程序的访问受 Active Directory 域服务中的安全组的控制，因此你需要规划一个过程来为每个虚拟化应用程序设置安全组，并管理每个组中添加的用户。</span><span class="sxs-lookup"><span data-stu-id="14853-109">**Note** Access to the applications is controlled by means of Security Groups in Active Directory Domain Services, so you will need to plan a process to set up a security group for each virtualized application and for managing which users are added to each group.</span></span> <span data-ttu-id="14853-110">应用程序虚拟化管理服务器管理员将服务器配置为使用这些 Active Directory 组，然后服务器将根据 Active Directory 组成员身份自动控制对程序包的访问。</span><span class="sxs-lookup"><span data-stu-id="14853-110">The Application Virtualization Management Server administrator configures the server to use these Active Directory groups, and the server then automatically controls access to the packages based on Active Directory group membership.</span></span>

 

## <span data-ttu-id="14853-111">本部分内容</span><span class="sxs-lookup"><span data-stu-id="14853-111">In This Section</span></span>


<a href="" id="overview-of-the-application-virtualization-system-components"></a>[<span data-ttu-id="14853-112">Application Virtualization System 组件概述</span><span class="sxs-lookup"><span data-stu-id="14853-112">Overview of the Application Virtualization System Components</span></span>](overview-of-the-application-virtualization-system-components.md)  
<span data-ttu-id="14853-113">列出并介绍 Microsoft Application Virtualization 管理系统的主要组件。</span><span class="sxs-lookup"><span data-stu-id="14853-113">Lists and describes the primary components of the Microsoft Application Virtualization Management System.</span></span>

<a href="" id="publishing-virtual-applications-using-application-virtualization-management-servers"></a>[<span data-ttu-id="14853-114">使用 Application Virtualization Management Server 发布虚拟应用程序</span><span class="sxs-lookup"><span data-stu-id="14853-114">Publishing Virtual Applications Using Application Virtualization Management Servers</span></span>](publishing-virtual-applications-using-application-virtualization-management-servers.md)  
<span data-ttu-id="14853-115">提供有关如何在基于应用程序虚拟服务器的部署方案中发布虚拟应用程序的简要概述。</span><span class="sxs-lookup"><span data-stu-id="14853-115">Provides a brief overview of how virtual applications are published in an Application Virtualization Server-based deployment scenario.</span></span>

<a href="" id="planning-your-streaming-solution-in-an-application-virtualization-server-based-implementation"></a>[<span data-ttu-id="14853-116">在基于 Application Virtualization Server 的实现中计划流式处理解决方案</span><span class="sxs-lookup"><span data-stu-id="14853-116">Planning Your Streaming Solution in an Application Virtualization Server-Based Implementation</span></span>](planning-your-streaming-solution-in-an-application-virtualization-server-based-implementation.md)  
<span data-ttu-id="14853-117">介绍将应用程序虚拟化流服务器与基于应用程序虚拟化管理服务器的实现结合使用的可用选项。</span><span class="sxs-lookup"><span data-stu-id="14853-117">Describes available options for using Application Virtualization Streaming Servers in conjunction with your Application Virtualization Management Server-based implementation.</span></span>

## <span data-ttu-id="14853-118">相关主题</span><span class="sxs-lookup"><span data-stu-id="14853-118">Related topics</span></span>


[<span data-ttu-id="14853-119">基于 Application Virtualization Server 的方案</span><span class="sxs-lookup"><span data-stu-id="14853-119">Application Virtualization Server-Based Scenario</span></span>](application-virtualization-server-based-scenario.md)

[<span data-ttu-id="14853-120">规划 Application Virtualization System 部署</span><span class="sxs-lookup"><span data-stu-id="14853-120">Planning for Application Virtualization System Deployment</span></span>](planning-for-application-virtualization-system-deployment.md)

 

 





