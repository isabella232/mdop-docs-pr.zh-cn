---
title: Application Virtualization Server 的故障排除信息
description: Application Virtualization Server 的故障排除信息
author: dansimp
ms.assetid: e9d43d9b-84f2-4d1b-bb90-a13740151e0c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7c98ad42a00e20900263d0598822a6381e2df1ef
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798721"
---
# Application Virtualization Server 的故障排除信息


本主题包含可用于解决应用程序虚拟化（app-v）服务器上的各种问题的信息。

## 安装服务器后，在安装程序日志中出现警告消息25017


安装后，你可能会在服务器设置日志中发现以下消息。

*警告25017。 安装程序无法为服务器创建 Active Directory 标记对象。 用于安装的帐户没有足够的权限写入 Active Directory 或 Active Directory 不可用。*

App-v 管理或流式服务器安装程序在 Active Directory 域服务（添加）中的计算机对象下创建一个服务连接点条目，此条目对应于运行安装程序的帐户具有相应权限时安装了该服务器的计算机。 如果无法创建此条目，则不会导致安装失败，这不会对产品的功能产生任何影响。 出现故障的可能原因是用于运行安装的用户帐户没有足够的权限来进行添加。 尽管在 "添加" 中注册 app-v 服务器是可选的，但执行此操作的一个优点是支持集中管理工具找到用于清单和管理用途的 app-v 服务器。

## 相关主题


[Application Virtualization Server](application-virtualization-server.md)

 

 





