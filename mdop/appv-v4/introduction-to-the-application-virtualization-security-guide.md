---
title: 《应用程序虚拟化安全指南》简介
description: 《应用程序虚拟化安全指南》简介
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
ms.openlocfilehash: 4b41c65c5ad753aa606d47d2eafe4a28e035cc4e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798937"
---
# 《应用程序虚拟化安全指南》简介


本 Microsoft Application Virtualization （App-v） security guide 为负责配置 app-v 部署所选安全功能的管理员提供说明。

**注意** 本文档不提供选择特定安全选项的指南。 此信息在适用于的应用程序-V 安全最佳做法白皮书中提供 <https://go.microsoft.com/fwlink/?LinkId=127120> 。

 

作为使用本指南的 app-v 管理员，你应该熟悉以下与安全相关的技术：

-   Active Directory 域服务

-   公钥基础结构（PKI）

-   Internet 协议安全（IPsec）

-   组策略

-   Internet information Services （IIS）

## APP-V 基础结构组件


在规划增强的安全 App-v 环境时，你可以考虑多种不同的基础结构模型。

**注意** 有关 App-v 基础结构模型的详细信息，请参阅以下文档：

-   [App-v 规划和部署指南](https://go.microsoft.com/fwlink/?LinkId=122063)

-   [基础结构规划和设计指南系列](https://go.microsoft.com/fwlink/?LinkId=151986)

 

这些模型将使用下图中所示的部分，但可能不是所有的 App-v 组件。

![app-v 分支 office 图表](images/appvbranchoffices.gif)

<a href="" id="application-virtualization--app-v--management-server"></a>应用程序虚拟化（App-v）管理服务器  
App-v 管理服务器对程序包内容进行流式处理，并将快捷方式和文件类型关联发布到 App-v 客户端。 App-v 管理服务器还支持活动升级、许可证管理和可用于报告的数据库。

<a href="" id="application-virtualization--app-v--streaming-server"></a>应用程序虚拟化（app-v）流式处理服务器  
App-v 流服务器托管用于流处理的程序包，用于在分支机构等环境中处理 V 客户端，在这种情况下，连接到 app-v 管理服务器的连接的带宽不足以流式处理程序包内容到客户端。 流服务器仅包含流式处理功能，并且不会向你提供 app-v 管理控制台或 App-v 管理 Web 服务。

<a href="" id="application-virtualization--app-v--data-store"></a>应用程序虚拟化（App-v）数据存储  
SQL 数据库中的 App-v 数据存储保留与 App-v 基础结构相关的信息。 App-v 数据存储中的信息包括所有应用程序记录、应用程序分配以及管理应用程序虚拟化环境的组。

<a href="" id="application-virtualization--app-v--management-service"></a>应用程序虚拟化（App-v）管理服务  
App-v 管理服务将读/写请求传递到 Application Virtualization 数据存储。 该组件可以与 App-v 管理服务器安装在同一台计算机上，也可以安装在安装了 IIS 的单独计算机上。

<a href="" id="application-virtualization--app-v--management-console"></a>应用程序虚拟化（App-v）管理控制台  
App-v 管理控制台是用于 App-v 服务器管理的管理单元管理实用工具。 该组件可以与 App-v 服务器安装在同一台计算机上，也可以安装在具有 MMC 3.0 和的单独工作站上。已安装 NET 2.0。

<a href="" id="application-virtualization--app-v--sequencer"></a>应用程序虚拟化（App-v） Sequencer  
App-v 排序器监视和捕获应用程序的安装并创建虚拟应用程序包。 Sequencer 的输出包含应用程序图标、包含应用程序定义信息的 OSD 文件、程序包清单文件和包含应用程序内容文件的 SFT 文件。 或者，可以创建 Windows Installer 文件，以便在不使用 App-v 基础结构的情况下安装程序包。

<a href="" id="application-virtualization--app-v--client"></a>应用程序虚拟化（app-v）客户端  
App-v Client 安装在 app-v 桌面客户端计算机或 App-v 终端服务客户端计算机上。 它为虚拟应用程序包提供虚拟环境。 App-v 客户端管理与应用程序虚拟化服务器的缓存、虚拟应用程序发布刷新和交互的程序包流。

 

 





