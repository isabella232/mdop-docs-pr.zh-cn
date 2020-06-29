---
title: MED-V 1.0 发行说明
description: MED-V 1.0 发行说明
author: dansimp
ms.assetid: 006a3537-5c5b-43b5-8df8-4bf6ddd3cd2f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 683056f768a3d547828996a9b191d58337c21ad6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803999"
---
# MED-V 1.0 发行说明


## 有关 MED-V 的已知问题


本部分提供有关 Microsoft 企业桌面虚拟化（MED-V）平台的一般问题的最新信息。 这些问题不会显示在产品文档中，在某些情况下，可能会矛盾现有产品文档。 只要有可能，这些问题将在以后的版本中解决。

### 文件下载不遵循 Web 重定向规则

文件下载不遵循 MED-V 工作区策略中设置的 Web 重定向规则。

### 将控制台发布的应用程序窗口展开到全屏时，它将消失

如果在无缝集成模式下配置的 MED-V 工作区中将控制台发布的应用程序（如 cmd.exe）窗口展开为全屏，则应用程序窗口可能会消失或不响应。

### 在完整桌面模式下工作时，桌面上的图标位置不会保存

在完整桌面模式下工作时，桌面上的图标的手动位置更改不会保存在 MED-V 工作区会话中。

### 同一域中不能存在具有相同名称的本地映像和测试映像

如果本地映像已加入域，并且管理员使用与测试映像相同的计算机名称创建新版本的同一映像，则当测试映像加入域时，加入域操作失败或成功，并且将从域中删除本地映像。

### MED-V 不支持 Windows Aero 功能

MED-V 不支持 Windows Aero 功能（如 Aero Flip 3D）。

### 每台计算机只能有一个 Windows 用户使用管理控制台

MED-V 管理控制台只能由管理员和安装了管理应用程序的 Windows 用户使用。

### MED-V 服务器配置实用工具在用户上下文中测试 Microsoft SQL Server 连接，而不是在 MED-V 服务器服务上下文中

MED-V 使用 MED-V 服务器服务上下文收集 Microsoft SQL Server 报表数据库中的报表。 MED-V 服务器配置实用程序验证数据库并测试数据库连接字符串。 它不验证数据库的 MED-V 服务器服务的访问权限。

 

 





