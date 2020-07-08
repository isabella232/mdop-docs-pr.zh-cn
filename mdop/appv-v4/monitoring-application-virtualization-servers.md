---
title: 监视 Application Virtualization Server
description: 监视 Application Virtualization Server
author: dansimp
ms.assetid: d84355ae-4fe4-41d9-ac3a-3eaa32d9a61f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a53c0c37ca609c701727a7f4e18019a9f20110ed
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798912"
---
# 监视 Application Virtualization Server


若要简化应用程序虚拟化（App-v）服务器管理，您可以使用 System Center Operations Manager2007 管理包。 此管理包仅支持应用程序虚拟化（App-v）4.5 服务器;它不支持以前的服务器版本。 管理包最大化了应用-v 服务器可用性以处理 app-v 客户端请求。

## 状态指示器


App-v Server 运行状况状态指示器采用颜色编码。 颜色表示以下状态值：

-   无颜色表示服务器运行时没有不可恢复的错误。

-   黄色表示其中一个组件运行不正常。 服务器的整体功能已降级，但服务器仍然可用。

-   红色表示服务器不可用，并且无法提供关键服务或与外部服务依赖关系进行通信。

## 监视条件


管理包监视服务器运行状况的以下方面：

-   服务器状态-监视服务器事件以验证服务器是否提供其预期服务。

-   数据存储访问-跟踪一个或多个 App-v 管理服务器的功能，以便与 App-v 数据存储进行访问和通信。

-   内容数据访问-监视对 \\Content 目录（可能是本地目录或网络共享）的访问权限，以及读取所请求的文件的功能。

-   安全性——通过 app-v 服务器的证书和安全通信报告错误。

-   客户端请求处理-监视一个或多个 App-v 服务器处理和正确响应客户端请求的能力。 这些请求包括将诸如 "配置请求"、"软件包加载请求" 和 "退出顺序请求" 之类的项目发布。

-   服务器配置-检查 App-v 服务器的配置设置。 这些配置设置包括注册表中和 App-v 数据存储中的设置。

## 服务器差异


App-v 管理服务器和 App-v 流式处理服务器之间的主要区别如下所示：

-   App-v 管理服务器可提供发布、流式处理、管理和报告服务。 因此，管理包可以管理 app-v 管理服务器的更多方面，而不是它可以在仅提供软件包流的 App-v 流式处理服务器上管理。

-   App-v 流式处理服务器没有 App-v 数据存储，因此不会监视数据存储访问。 在注册表中管理 App-v 流服务器的配置信息。

-   App-v 流式处理服务器不使用 app-v Server 管理控制台界面;使用其他工具管理配置。

## 相关主题


[Application Virtualization Server](application-virtualization-server.md)

 

 





