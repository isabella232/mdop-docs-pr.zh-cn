---
title: 图示 MBAM 2.5 部署的功能
description: 图示 MBAM 2.5 部署的功能
author: dansimp
ms.assetid: 7b5eff42-af8c-4bd0-a20a-18cc2e779f01
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/15/2018
ms.openlocfilehash: c3b205d4f0b4b18cf8bdbf51982b5a59e5e1b9d5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798035"
---
# 图示 MBAM 2.5 部署的功能


本主题介绍了组成以下拓扑的 Microsoft BitLocker 管理和监视（MBAM）2.5 部署的各个功能：

-   MBAM 独立

-   System Center Configuration Manager 集成

**重要提示**  
这些功能不表示用于部署 MBAM 的推荐体系结构。 仅将此信息用作了解组成 MBAM 部署的各个功能的指南。 请参阅适用于 MBAM 的推荐体系结构的[MBAM 2.5 的高级别体系结构](high-level-architecture-for-mbam-25.md)。



有关本主题中所述软件的受支持版本的列表，请参阅[MBAM 2.5 支持的配置](mbam-25-supported-configurations.md)。

## <a href="" id="bkmk-standalone"></a> MBAM 独立拓扑


以下图像和表介绍了 MBAM 独立拓扑中的功能。

![mbab2\-5](images/mbam2-5-standalonecomponents.png)

|功能类型|描述|数据库|
|-|-|-|
|恢复数据库|此数据库存储从 MBAM 客户端计算机收集的恢复数据。|此功能在运行 Windows Server 和支持的 SQL Server 实例的服务器上配置。|
|合规性和审核数据库|此数据库存储合规性数据，该数据主要用于 SQL Server Reporting Services 主机的报表。|此功能在运行 Windows Server 和支持的 SQL Server 实例的服务器上配置。|
|合规性和审核报告|||
|报表 Web 服务|此 web 服务支持管理和监视网站与存储报告数据的 SQL Server 实例之间的通信。|此功能安装在运行 Windows Server 的服务器上。|
|报告网站（管理和监视网站）|可从 "管理和监视" 网站查看报表。 报告提供有关您的企业中的客户端计算机的恢复审核和合规性状态数据。|此功能在运行 Windows Server 的服务器上配置。|
|SQL Server Reporting Services （SSRS）|在 SSRS 数据库实例中配置报表。 可以直接从 SSRS 或管理和监视网站查看报表。|此功能在运行 Windows Server 的服务器上配置，并且在运行 SSRS 的受支持的 SQL Server 实例上配置。|
|自助服务服务器|||
|自助服务 Web 服务|此 web 服务由 MBAM 客户端和管理和监控网站和自助服务门户使用，用于与恢复数据库通信。|此功能安装在运行 Windows Server 的计算机上。|
|自助服务网站（自助服务门户）|此网站使客户端计算机上的最终用户能够独立登录到网站，以便在丢失或忘记其 BitLocker 密码时获取恢复密钥。|此功能在运行 Windows Server 的计算机上配置。|
|管理和监视服务器|||
|管理和监视 Web 服务|监视 Web 服务由 MBAM 客户端和网站用于与数据库通信。|此功能安装在运行 Windows Server 的计算机上。|

**重要提示**  
自助服务 Web 服务在 Microsoft BitLocker 管理和监视（MBAM） 2.5 SP1 中不再可用，其中 MBAM 客户端、管理和监视网站以及自助服务门户直接与恢复数据库进行通信。

**重要提示**  
由于 MBAM 客户端和网站直接与恢复数据库通信，因此在 Microsoft BitLocker 管理和监视（MBAM） 2.5 SP1 中不再提供监视 Web 服务。


## <a href="" id="bkmk-cmintegrated"></a>System Center Configuration Manager 集成拓扑

以下图像和表介绍了 System Center Configuration Manager 集成拓扑中的功能。

![mbam2\-5](images/mbam2-5-cmcomponents.png)

**重要提示**  
自助服务 Web 服务在 Microsoft BitLocker 管理和监视（MBAM） 2.5 SP1 中不再可用，其中 MBAM 客户端、管理和监视网站以及自助服务门户直接与恢复数据库进行通信。

**警告**  
由于 MBAM 客户端和网站直接与恢复数据库通信，因此在 Microsoft BitLocker 管理和监视（MBAM） 2.5 SP1 中不再提供监视 Web 服务。


|                        功能类型                        |                                                                                                    描述                                                                                                    |
|------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                    自助服务服务器                     |                                                                                                                                                                                                                   |
|                  自助服务 Web 服务                  |                                                 此 web 服务由 MBAM 客户端和自助服务门户用于与恢复数据库通信。                                                  |
|                    自助服务网站                    |                          此网站使客户端计算机上的最终用户能够独立登录到网站，以便在丢失或忘记其 BitLocker 密码时获取恢复密钥。                          |
| 管理和监视服务器/恢复审核报告 |                                                                                                                                                                                                                   |
|         管理和监视 Web 服务          |                               此 web 服务支持管理和监视网站与存储报告数据的 SQL Server 数据库之间的通信。                               |
|           管理和监视网站            | 可通过管理和监视网站查看恢复审核报告。 使用 Configuration Manager 控制台查看所有其他报表，或直接从 SQL Server Reporting Services 查看报表。 |
|                         数据库                          |                                                                                                                                                                                                                   |
|                     恢复数据库                      |                                                                 此数据库存储从 MBAM 客户端计算机收集的恢复数据。                                                                  |
|                       审核数据库                       |                                                                   此数据库存储有关恢复尝试和活动的审核信息。                                                                    |
|               配置管理器功能               |                                                                                                                                                                                                                   |
|          Configuration Manager 管理控制台          |                                                                   此控制台内置于 Configuration Manager 中，用于查看报表。                                                                   |
|               配置管理器报告                |                                                             报表显示企业版客户端计算机的合规性和恢复审核数据。                                                              |
|               SQL Server Reporting Services                |                                                SSRS 启用 MBAM 报表。 可以直接从 SSRS 或配置管理器控制台查看报表。                                                 |

## 相关主题

[MBAM 2.5 的高级别体系结构](high-level-architecture-for-mbam-25.md)

[MBAM 2.5 入门](getting-started-with-mbam-25.md)

## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。




