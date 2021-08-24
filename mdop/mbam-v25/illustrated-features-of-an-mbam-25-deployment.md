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
ms.openlocfilehash: 139980fb6712b40685a41bab45610da670803afa
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910617"
---
# <a name="illustrated-features-of-an-mbam-25-deployment"></a>图示 MBAM 2.5 部署的功能


本主题介绍以下拓扑的 Microsoft BitLocker 管理和监视 (MBAM) 2.5 部署中的单个功能：

-   MBAM 独立

-   System Center Configuration Manager集成

**重要提示**  
这些功能不表示用于部署 MBAM 的建议体系结构。 使用此信息仅作为指南来了解作为 MBAM 部署要素的单个功能。 有关 [MBAM 的建议体系结构，请参阅 MBAM 2.5](high-level-architecture-for-mbam-25.md) 高级体系结构。



有关本主题中提到的软件受支持版本的列表，请参阅[MBAM 2.5 Supported Configurations。](mbam-25-supported-configurations.md)

## <a name="mbam-stand-alone-topology"></a><a href="" id="bkmk-standalone"></a> MBAM 独立拓扑


下图和表说明了 MBAM 独立拓扑中的功能。

![mbab2\-5。](images/mbam2-5-standalonecomponents.png)

|功能类型|描述|数据库|
|-|-|-|
|恢复数据库|此数据库存储从 MBAM 客户端计算机收集的恢复数据。|此功能在运行 Windows 服务器和支持的 SQL Server 实例上配置。|
|合规性和审核数据库|此数据库存储合规性数据，这些数据主要用于托管SQL Server Reporting Services报告。|此功能在运行 Windows 服务器和支持的 SQL Server 实例上配置。|
|合规性和审核报告|||
|报告 Web 服务|此 Web 服务支持管理和监控网站与存储SQL Server报告数据的实例之间的通信。|此功能安装在运行 Windows Server 的服务器上。|
|报告网站 (管理和监控网站) |您从管理和监控网站查看报告。 报告提供有关企业中客户端计算机的恢复审核和合规性状态数据。|此功能在运行 Windows 服务器上配置。|
|SQL Server Reporting Services (SSRS) |报告在 SSRS 数据库实例中配置。 可以直接从 SSRS 或管理和监控网站查看报告。|此功能在运行 Windows Server 的服务器和SQL Server SSRS 的受支持实例上配置。|
|Self-Service 服务器|||
|Self-Service Web 服务|此 Web 服务由 MBAM 客户端、管理和监控网站以及 Self-Service门户用于与恢复数据库进行通信。|此功能安装在运行 Windows Server 的计算机上。|
|Self-Service网站 (自助服务门户) |利用此网站，客户端计算机上的最终用户可以在丢失或忘记 BitLocker 密码时独立登录到网站，获取恢复密钥。|此功能在运行 Windows Server 的计算机上配置。|
|管理和监控服务器|||
|管理和监控 Web 服务|MBAM 客户端和网站使用监控 Web 服务与数据库通信。|此功能安装在运行 Windows Server 的计算机上。|

**重要提示**  
Microsoft BitLocker 管理和监视 (MBAM) 2.5 SP1 中不再提供 Self-Service Web 服务，其中 MBAM 客户端、管理和监控网站以及 Self-Service 门户直接与恢复数据库进行通信。

**重要提示**  
Microsoft BitLocker 管理和监视 (MBAM) 2.5 SP1 中不再提供监控 Web 服务，因为 MBAM 客户端和网站直接与恢复数据库通信。


## <a name="system-center-configuration-manager-integration-topology"></a><a href="" id="bkmk-cmintegrated"></a>System Center Configuration Manager集成拓扑

下图和表说明了 System Center Configuration Manager 拓扑中的功能。

![mbam2\-5。](images/mbam2-5-cmcomponents.png)

**重要提示**  
Microsoft BitLocker 管理和监视 (MBAM) 2.5 SP1 中不再提供 Self-Service Web 服务，其中 MBAM 客户端、管理和监控网站以及 Self-Service 门户直接与恢复数据库进行通信。

**警告**  
Microsoft BitLocker 管理和监视 (MBAM) 2.5 SP1 中不再提供监控 Web 服务，因为 MBAM 客户端和网站直接与恢复数据库通信。


|                        功能类型                        |                                                                                                    描述                                                                                                    |
|------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                    Self-Service 服务器                     |                                                                                                                                                                                                                   |
|                  Self-Service Web 服务                  |                                                 此 Web 服务由 MBAM 客户端和 Self-Service 门户用于与恢复数据库通信。                                                  |
|                    Self-Service 网站                    |                          利用此网站，客户端计算机上的最终用户可以在丢失或忘记 BitLocker 密码时独立登录到网站，获取恢复密钥。                          |
| 管理和监控服务器/恢复审核报告 |                                                                                                                                                                                                                   |
|         管理和监控 Web 服务          |                               此 Web 服务支持管理和监控网站与存储报告SQL Server的数据库之间的通信。                               |
|           管理和监控网站            | 从管理和监控网站查看恢复审核报告。 使用 Configuration Manager 控制台查看所有其他报告，或直接从 SQL Server Reporting Services。 |
|                         数据库                          |                                                                                                                                                                                                                   |
|                     恢复数据库                      |                                                                 此数据库存储从 MBAM 客户端计算机收集的恢复数据。                                                                  |
|                       审核数据库                       |                                                                   此数据库存储有关恢复尝试和活动的审核信息。                                                                    |
|               Configuration Manager 功能               |                                                                                                                                                                                                                   |
|          Configuration Manager 管理控制台          |                                                                   此控制台内置于 Configuration Manager 中，用于查看报告。                                                                   |
|               Configuration Manager 报告                |                                                             报告显示企业中客户端计算机的合规性和恢复审核数据。                                                              |
|               SQL Server Reporting Services                |                                                SSRS 启用 MBAM 报告。 可以直接从 SSRS 或 Configuration Manager 控制台查看报告。                                                 |

## <a name="related-topics"></a>相关主题

[MBAM 2.5 的高级别体系结构](high-level-architecture-for-mbam-25.md)

[MBAM 2.5 入门](getting-started-with-mbam-25.md)

## <a name="got-a-suggestion-for-mbam"></a>有关于 MBAM 的建议吗？
- 在此处添加建议或对建议 [投票](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)。 
- 对于 MBAM 问题，请使用 [MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。




