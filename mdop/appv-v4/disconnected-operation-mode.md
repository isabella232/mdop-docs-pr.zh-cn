---
title: 断开连接操作模式
description: 断开连接操作模式
author: dansimp
ms.assetid: 3f9849ea-ba53-4c68-85d3-87a4218f59c6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6e9534b93f23b17e5258ef5e2d548eb93213f2f8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803005"
---
# <span data-ttu-id="84b1a-103">断开连接操作模式</span><span class="sxs-lookup"><span data-stu-id="84b1a-103">Disconnected Operation Mode</span></span>


<span data-ttu-id="84b1a-104">已连接的操作模式设置（通过右键单击**应用程序虚拟化**节点，选择 "**属性**"，然后单击 "**连接**" 选项卡），启用远程桌面服务（以前称为终端服务）的应用程序虚拟化桌面客户端或客户端，以运行客户端无法连接到应用程序虚拟化管理服务器时存储在客户端的文件系统缓存中的应用程序。</span><span class="sxs-lookup"><span data-stu-id="84b1a-104">The disconnected operation mode settings—accessible by right-clicking the **Application Virtualization** node, selecting **Properties**, and clicking the **Connectivity** tab—enables the Application Virtualization Desktop Client or Client for Remote Desktop Services (formerly Terminal Services) to run applications that are stored in the file system cache of the client when the client is unable to connect to the Application Virtualization Management Server.</span></span>

<span data-ttu-id="84b1a-105">连接到服务器失败的原因包括服务器故障、网络中断或断开网络连接。</span><span class="sxs-lookup"><span data-stu-id="84b1a-105">Reasons for failure to connect to the server include server failure, network outage, or disconnection from the network.</span></span> <span data-ttu-id="84b1a-106">如果发生任何故障，客户端将自动切换到断开连接的操作。</span><span class="sxs-lookup"><span data-stu-id="84b1a-106">If any failure occurs, the client will automatically switch to disconnected operation.</span></span> <span data-ttu-id="84b1a-107">断开连接后，如果客户端需要服务器的其他数据才能继续运行应用程序，或者如果断开连接的操作超时时间已到，客户端将尝试重新连接到服务器。</span><span class="sxs-lookup"><span data-stu-id="84b1a-107">After it is disconnected, if the client needs additional data from the server to continue to run an application or if the disconnected operation time-out expires, the client will attempt to reconnect to the server.</span></span> <span data-ttu-id="84b1a-108">如果此连接尝试失败，应用程序将关闭。</span><span class="sxs-lookup"><span data-stu-id="84b1a-108">If this connection attempt fails, the application will be shut down.</span></span>

<span data-ttu-id="84b1a-109">默认情况下，已启用断开连接的操作，超时设置为90天。</span><span class="sxs-lookup"><span data-stu-id="84b1a-109">By default, disconnected operation is enabled and the time-out is set to 90 days.</span></span> <span data-ttu-id="84b1a-110">将超时值指定为你希望限制断开连接操作模式的天数，你可以输入1到999之间的值。</span><span class="sxs-lookup"><span data-stu-id="84b1a-110">The time-out value is specified as the number of days you want to limit disconnected operation mode, and you can enter a value from 1–999.</span></span>

## <span data-ttu-id="84b1a-111">相关主题</span><span class="sxs-lookup"><span data-stu-id="84b1a-111">Related topics</span></span>


[<span data-ttu-id="84b1a-112">如何禁用或修改断开连接操作模式设置</span><span class="sxs-lookup"><span data-stu-id="84b1a-112">How to Disable or Modify Disconnected Operation Mode Settings</span></span>](how-to-disable-or-modify-disconnected-operation-mode-settings.md)

 

 





