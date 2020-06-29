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
# 使用 Application Virtualization Management Server 发布虚拟应用程序


在基于应用程序虚拟服务器的部署中，已排序、测试和找到可部署的虚拟应用程序包将复制到应用程序虚拟管理服务器要使用的主内容共享。 在应用程序虚拟化管理服务器上导入程序包后，可以将它们发布给最终用户。

**注意** 内容共享应位于服务器的已连接磁盘存储中。 应仔细考虑使用网络存储设备（如 SAN 或 DFS 共享），因为网络的影响。

 

将应用程序预配到 Active Directory 组。 通常情况下，应用程序虚拟化管理员将为每个要发布的虚拟应用程序创建 Active Directory 组，然后向这些组添加相应的用户。 当用户登录到其工作站时，应用程序虚拟化客户端在默认情况下使用已登录用户的凭据执行发布刷新。 然后，用户可以从放置快捷方式的任何位置启动应用程序。 应用程序虚拟化管理员确定在应用程序排序期间，在客户端系统上的快捷方式所在的位置和数量。

**注意** *发布刷新*是在应用程序虚拟化客户端上定义的应用程序虚拟化服务器的调用，用于确定向客户端发送哪些虚拟应用程序快捷方式供最终用户使用。

 

## 相关主题


[基于 Application Virtualization Server 的方案](application-virtualization-server-based-scenario.md)

[如何在客户端上发布虚拟应用程序](how-to-publish-a-virtual-application-on-the-client.md)

[Application Virtualization System 组件概述](overview-of-the-application-virtualization-system-components.md)

[在基于 Application Virtualization Server 的实现中计划流式处理解决方案](planning-your-streaming-solution-in-an-application-virtualization-server-based-implementation.md)

 

 





