---
title: 如何在 Application Virtualization 中实现脱机或联机工作
description: 如何在 Application Virtualization 中实现脱机或联机工作
author: dansimp
ms.assetid: aa532b37-8a00-4db4-9b51-e1e8354b2495
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0dfdd315fe607156135247c4a34d0248ef8fbdd9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798959"
---
# <span data-ttu-id="0ab66-103">如何在 Application Virtualization 中实现脱机或联机工作</span><span class="sxs-lookup"><span data-stu-id="0ab66-103">How to Work Offline or Online with Application Virtualization</span></span>


<span data-ttu-id="0ab66-104">如果你计划在长时间内断开与网络的连接，你可以在脱机模式下工作，以消除应用程序虚拟化客户端尝试与服务器通信时可能出现的延迟。</span><span class="sxs-lookup"><span data-stu-id="0ab66-104">If you plan to be disconnected from the network for an extended period of time, you can work in offline mode to eliminate possible delays when the Application Virtualization client attempts to communicate with the server.</span></span> <span data-ttu-id="0ab66-105">在脱机模式下，应用程序虚拟化客户端将不会尝试与发布服务器通信，因此应用程序必须在启用脱机模式之前完全缓存。</span><span class="sxs-lookup"><span data-stu-id="0ab66-105">In offline mode, the Application Virtualization client will not attempt to communicate with the publishing server, so applications must be fully cached before enabling offline mode.</span></span> <span data-ttu-id="0ab66-106">即使它们位于计算机上的本地磁盘上，也不会从内容共享中检索应用程序。</span><span class="sxs-lookup"><span data-stu-id="0ab66-106">Applications will not be retrieved from the content share even if they are on the local disk on the computer.</span></span> <span data-ttu-id="0ab66-107">你可以使用以下 Application Virtualization 客户端过程在脱机工作和联机工作之间进行切换。</span><span class="sxs-lookup"><span data-stu-id="0ab66-107">You can use the following Application Virtualization Client procedure to toggle between working offline and online.</span></span>

<span data-ttu-id="0ab66-108">**注意** 默认情况下，对于远程桌面服务（以前称为终端服务）的客户端，**脱机工作**处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="0ab66-108">**Note** By default, **Work Offline** is disabled for the Client for Remote Desktop Services (formerly Terminal Services).</span></span> <span data-ttu-id="0ab66-109">你的系统管理员必须更改你的用户权限，才能允许你在远程桌面服务客户端上使用此设置。</span><span class="sxs-lookup"><span data-stu-id="0ab66-109">Your system administrator must change your user permissions to allow you to use this setting on a Client for Remote Desktop Services.</span></span>

 

**<span data-ttu-id="0ab66-110">脱机工作</span><span class="sxs-lookup"><span data-stu-id="0ab66-110">To work offline</span></span>**

-   <span data-ttu-id="0ab66-111">右键单击通知区域中的 "应用程序虚拟化系统" 图标，然后从弹出菜单中选择 "**脱机工作**"。</span><span class="sxs-lookup"><span data-stu-id="0ab66-111">Right-click the Application Virtualization System icon in the notification area, and select **Work Offline** from the pop-up menu.</span></span>

**<span data-ttu-id="0ab66-112">联机工作</span><span class="sxs-lookup"><span data-stu-id="0ab66-112">To work online</span></span>**

-   <span data-ttu-id="0ab66-113">右键单击通知区域中的 "应用程序虚拟化系统" 图标，然后从弹出菜单中选择 "**联机工作**"。</span><span class="sxs-lookup"><span data-stu-id="0ab66-113">Right-click the Application Virtualization System icon in the notification area, and select **Work Online** from the pop-up menu.</span></span>

## <span data-ttu-id="0ab66-114">相关主题</span><span class="sxs-lookup"><span data-stu-id="0ab66-114">Related topics</span></span>


[<span data-ttu-id="0ab66-115">如何为 Application Virtualization Client Management 使用桌面通知区域</span><span class="sxs-lookup"><span data-stu-id="0ab66-115">How to Use the Desktop Notification Area for Application Virtualization Client Management</span></span>](how-to-use-the-desktop-notification-area-for-application-virtualization-client-management.md)

 

 





