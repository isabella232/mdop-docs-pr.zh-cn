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
# 如何在 Application Virtualization 中实现脱机或联机工作


如果你计划在长时间内断开与网络的连接，你可以在脱机模式下工作，以消除应用程序虚拟化客户端尝试与服务器通信时可能出现的延迟。 在脱机模式下，应用程序虚拟化客户端将不会尝试与发布服务器通信，因此应用程序必须在启用脱机模式之前完全缓存。 即使它们位于计算机上的本地磁盘上，也不会从内容共享中检索应用程序。 你可以使用以下 Application Virtualization 客户端过程在脱机工作和联机工作之间进行切换。

**注意** 默认情况下，对于远程桌面服务（以前称为终端服务）的客户端，**脱机工作**处于禁用状态。 你的系统管理员必须更改你的用户权限，才能允许你在远程桌面服务客户端上使用此设置。

 

**脱机工作**

-   右键单击通知区域中的 "应用程序虚拟化系统" 图标，然后从弹出菜单中选择 "**脱机工作**"。

**联机工作**

-   右键单击通知区域中的 "应用程序虚拟化系统" 图标，然后从弹出菜单中选择 "**联机工作**"。

## 相关主题


[如何为 Application Virtualization Client Management 使用桌面通知区域](how-to-use-the-desktop-notification-area-for-application-virtualization-client-management.md)

 

 





