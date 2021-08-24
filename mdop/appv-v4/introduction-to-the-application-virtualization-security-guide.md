---
title: Application Virtualization Security Guide 简介
description: Application Virtualization Security Guide 简介
author: dansimp
ms.assetid: 50e1d220-7a95-45b8-933b-3dadddebe26f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 82914de48a5a5777f6ce4b50fe3e8af34dd82494
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910777"
---
# <a name="introduction-to-the-application-virtualization-security-guide"></a>Application Virtualization Security Guide 简介


本 Microsoft Application Virtualization (App-V) 安全指南为负责配置为 App-V 部署选择的安全功能的管理员提供了说明。

**注意**  
本文档不提供选择特定安全选项的指导。 该信息在 App-V 安全性最佳实践白皮书（位于 ）中提供 <https://go.microsoft.com/fwlink/?LinkId=127120> 。

 

作为使用本指南的 App-V 管理员，您应熟悉以下与安全相关的技术：

-   Active Directory 域服务

-   PKI (公钥基础结构) 

-   IPsec (Internet 协议) 

-   组策略

-   Internet Information Services (IIS) 

## <a name="app-v-infrastructure-components"></a>APP-V 基础结构组件


在规划增强的安全性 App-V 环境时，可以考虑几个不同的基础结构模型。

**注意**  
有关 App-V 基础结构模型详细信息，请参阅以下文档：

-   [App-V 规划和部署指南](https://go.microsoft.com/fwlink/?LinkId=122063)

-   [基础结构规划和设计指南系列](https://go.microsoft.com/fwlink/?LinkId=151986)

 

这些模型利用下图中所示的一些（但可能并非所有）App-V 组件。

![app-v 分支机构关系图。](images/appvbranchoffices.gif)

<a href="" id="application-virtualization--app-v--management-server"></a>Application Virtualization (App-V) Management Server  
App-V 管理服务器流式传输包内容，将快捷方式和文件类型关联发布到 App-V 客户端。 App-V 管理服务器还支持活动升级、许可证管理和可用于报告的数据库。

<a href="" id="application-virtualization--app-v--streaming-server"></a>Application Virtualization (App-V) Streaming Server  
App-V 流式处理服务器托管在分支机构等环境中流式传输至 App-V 客户端的程序包，其中连接到 App-V 管理服务器的带宽不足，无法将包内容流式处理到客户端。 流式服务器仅包含流式处理功能，不提供 App-V 管理控制台或 App-V 管理 Web 服务。

<a href="" id="application-virtualization--app-v--data-store"></a>Application Virtualization (App-V) Data Store  
App-V 数据存储在 SQL 数据库中，保留与 App-V 基础结构有关的信息。 App-V 数据存储中的信息包括所有应用程序记录、应用程序分配以及管理 Application Virtualization 环境的组。

<a href="" id="application-virtualization--app-v--management-service"></a>Application Virtualization (App-V) Management Service  
App-V 管理服务将读/写请求传达给 Application Virtualization 数据存储。 此组件可以与 App-V 管理服务器安装在同一计算机上，也可以安装在安装了 IIS 的单独计算机上。

<a href="" id="application-virtualization--app-v--management-console"></a>Application Virtualization (App-V) Management Console  
App-V 管理控制台是 App-V 服务器管理的一个管理单元管理实用工具。 此组件可以与 App-V 服务器安装在同一计算机上，也可以安装在安装了 MMC 3.0 和 .NET 2.0 的单独工作站上。

<a href="" id="application-virtualization--app-v--sequencer"></a>Application Virtualization (App-V) Sequencer  
App-V Sequencer 监视和捕获应用程序的安装并创建虚拟应用程序包。 Sequencer 的输出由应用程序图标、包含应用程序定义信息的 OSD 文件、程序包清单文件和包含应用程序内容文件的 SFT 文件组成。 （可选）Windows安装程序文件，无需使用 App-V 基础结构即可安装程序包。

<a href="" id="application-virtualization--app-v--client"></a>Application Virtualization (App-V) Client  
App-V 客户端安装在 App-V 桌面客户端计算机或 App-V 终端服务客户端计算机上。 它为虚拟应用程序包提供了虚拟环境。 App-V 客户端管理到缓存的程序包流、虚拟应用程序发布刷新以及与 Application Virtualization Servers 的交互。

 

 





