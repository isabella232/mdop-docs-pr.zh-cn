---
title: 使用 Application Virtualization Management Server 发布虚拟应用程序
description: 使用 Application Virtualization Management Server 发布虚拟应用程序
author: dansimp
ms.assetid: f3d79284-3f82-4ca3-b741-1a80b61490da
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 01b85d73ed0a6a8bf723be381e947fbbc003bf6d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798837"
---
# <span data-ttu-id="de861-103">使用 Application Virtualization Management Server 发布虚拟应用程序</span><span class="sxs-lookup"><span data-stu-id="de861-103">Publishing Virtual Applications Using Application Virtualization Management Servers</span></span>


<span data-ttu-id="de861-104">在基于应用程序虚拟服务器的部署中，已排序、测试和找到可部署的虚拟应用程序包将复制到应用程序虚拟管理服务器要使用的主内容共享。</span><span class="sxs-lookup"><span data-stu-id="de861-104">In an Application Virtualization Server-based deployment, virtual application packages that have been sequenced, tested, and found deployable are copied to the main CONTENT share to be used by the Application Virtualization Management Server.</span></span> <span data-ttu-id="de861-105">在应用程序虚拟化管理服务器上导入程序包后，可以将它们发布给最终用户。</span><span class="sxs-lookup"><span data-stu-id="de861-105">After the packages are imported on the Application Virtualization Management Server, they can be published to the end users.</span></span>

<span data-ttu-id="de861-106">**注意** 内容共享应位于服务器的已连接磁盘存储中。</span><span class="sxs-lookup"><span data-stu-id="de861-106">**Note** The CONTENT share should be located on the server’s attached disk storage.</span></span> <span data-ttu-id="de861-107">应仔细考虑使用网络存储设备（如 SAN 或 DFS 共享），因为网络的影响。</span><span class="sxs-lookup"><span data-stu-id="de861-107">Using a network storage device such as a SAN or a DFS share should be considered carefully because of the network impact.</span></span>

 

<span data-ttu-id="de861-108">将应用程序预配到 Active Directory 组。</span><span class="sxs-lookup"><span data-stu-id="de861-108">Applications are provisioned to Active Directory groups.</span></span> <span data-ttu-id="de861-109">通常情况下，应用程序虚拟化管理员将为每个要发布的虚拟应用程序创建 Active Directory 组，然后向这些组添加相应的用户。</span><span class="sxs-lookup"><span data-stu-id="de861-109">Typically, the Application Virtualization administrator will create Active Directory groups for each virtual application to be published and then add the appropriate users to those groups.</span></span> <span data-ttu-id="de861-110">当用户登录到其工作站时，应用程序虚拟化客户端在默认情况下使用已登录用户的凭据执行发布刷新。</span><span class="sxs-lookup"><span data-stu-id="de861-110">When the users log on to their workstations, the Application Virtualization Client, by default, performs a publishing refresh using the credentials of the logged on user.</span></span> <span data-ttu-id="de861-111">然后，用户可以从放置快捷方式的任何位置启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="de861-111">The user can then start applications from wherever the shortcuts have been placed.</span></span> <span data-ttu-id="de861-112">应用程序虚拟化管理员确定在应用程序排序期间，在客户端系统上的快捷方式所在的位置和数量。</span><span class="sxs-lookup"><span data-stu-id="de861-112">The Application Virtualization administrator determines where and how many shortcuts are located on the client system during the sequencing of the application.</span></span>

<span data-ttu-id="de861-113">**注意** *发布刷新*是在应用程序虚拟化客户端上定义的应用程序虚拟化服务器的调用，用于确定向客户端发送哪些虚拟应用程序快捷方式供最终用户使用。</span><span class="sxs-lookup"><span data-stu-id="de861-113">**Note** A *publishing refresh* is a call to the Application Virtualization Server that is defined on the Application Virtualization Client, to determine which virtual application shortcuts are sent to the client for use by the end user.</span></span>

 

## <span data-ttu-id="de861-114">相关主题</span><span class="sxs-lookup"><span data-stu-id="de861-114">Related topics</span></span>


[<span data-ttu-id="de861-115">基于 Application Virtualization Server 的方案</span><span class="sxs-lookup"><span data-stu-id="de861-115">Application Virtualization Server-Based Scenario</span></span>](application-virtualization-server-based-scenario.md)

[<span data-ttu-id="de861-116">如何在客户端上发布虚拟应用程序</span><span class="sxs-lookup"><span data-stu-id="de861-116">How to Publish a Virtual Application on the Client</span></span>](how-to-publish-a-virtual-application-on-the-client.md)

[<span data-ttu-id="de861-117">Application Virtualization System 组件概述</span><span class="sxs-lookup"><span data-stu-id="de861-117">Overview of the Application Virtualization System Components</span></span>](overview-of-the-application-virtualization-system-components.md)

[<span data-ttu-id="de861-118">在基于 Application Virtualization Server 的实现中计划流式处理解决方案</span><span class="sxs-lookup"><span data-stu-id="de861-118">Planning Your Streaming Solution in an Application Virtualization Server-Based Implementation</span></span>](planning-your-streaming-solution-in-an-application-virtualization-server-based-implementation.md)

 

 





