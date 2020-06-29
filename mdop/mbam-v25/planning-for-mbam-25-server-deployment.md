---
title: 规划 MBAM 2.5 服务器部署
description: 规划 MBAM 2.5 服务器部署
author: dansimp
ms.assetid: 88774c89-31c8-4eb8-a845-a00bbec8c870
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d2ecb510fab821118ce210577f9ffb83c39be050
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803923"
---
# 规划 MBAM 2.5 服务器部署


本主题列出了为 MBAM 独立版和 Configuration Manager 拓扑部署的功能，并列出了部署这些拓扑所需的顺序。 每个拓扑都有一个建议的配置。 但是，你可以在不同的配置和多台服务器上配置 MBAM 服务器数据库和功能，具体取决于你的可伸缩性要求。

## 两种拓扑的重要规划注意事项


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">注意事项</th>
<th align="left">详细信息或用途</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>开始部署之前，请先查看以下内容：</p>
<ul>
<li><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)">独立和 Configuration Manager 集成拓扑的 MBAM 2.5 服务器先决条件</a></p></li>
<li><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)">MBAM 2.5 支持的配置</a></p></li>
</ul></td>
<td align="left"><p>每个 MBAM 功能都具有特定的先决条件，在开始 MBAM 安装之前必须满足这些先决条件。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MBAM 中的 BitLocker 恢复密钥在一次使用后过期。</p></td>
<td align="left"><p>一次使用意味着已通过管理和监视网站（也称为帮助桌面）、自助服务门户或使用 <strong> MbamBitLockerRecoveryKey </strong> Windows PowerShell cmdlet 检索恢复密钥。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>跟踪配置每个功能的计算机的名称。 您将在整个配置过程中使用此信息。</p></td>
<td align="left"><p>您可能希望使用 <a href="mbam-25-deployment-checklist.md" data-raw-source="[MBAM 2.5 Deployment Checklist](mbam-25-deployment-checklist.md)"> MBAM 2.5 部署清单 </a> 来实现此目的。</p></td>
</tr>
<tr class="even">
<td align="left"><p>仅配置 MDOP MBAM （BitLocker Management）节点中的组策略设置。 不要更改 "BitLocker 驱动器加密" 节点中的组策略设置。</p></td>
<td align="left"><p>如果更改了 BitLocker 驱动器加密节点中的组策略设置，MBAM 将不起作用。</p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="planning-for-mbam-server-deployment---stand-alone-topology"></a>规划 MBAM Server 部署-独立拓扑


对于独立拓扑，建议对生产环境使用双服务器配置，尽管可以使用3到4台服务器的配置。

MBAM 独立拓扑的服务器基础结构包含以下功能，这些功能必须按所列顺序进行配置：

1.  数据库（合规性和审核数据库和恢复数据库）

2.  报告

3.  Web 应用程序（及其相应的 web 服务）

    -   管理和监视网站

    -   自助服务门户

有关这些功能的说明，请参阅[具有独立拓扑的 MBAM 2.5 的高级别体系结构](high-level-architecture-of-mbam-25-with-stand-alone-topology.md)。

## <a href="" id="planning-for-mbam-server-deployment---configuration-manager-topology"></a>规划 MBAM Server 部署-配置管理器拓扑


对于 Configuration Manager 集成拓扑，虽然可以使用其他服务器的配置，但对于生产环境，建议使用三服务器配置。

MBAM Configuration Manager 拓扑的服务器基础结构包含以下功能，这些功能必须按所列顺序进行配置或执行：

1.  数据库（合规性和审核数据库和恢复数据库）

2.  报告

3.  Web 应用程序（及其相应的 web 服务）

    -   管理和监视网站

    -   自助服务门户

4.  System Center Configuration Manager 集成

有关这些功能的说明，请参阅[具有 Configuration Manager 集成拓扑的 MBAM 2.5 的高级别体系结构](high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md)。



## 相关主题


[规划部署 MBAM 2.5](planning-to-deploy-mbam-25.md)

[部署 MBAM 2.5 服务器基础结构](deploying-the-mbam-25-server-infrastructure.md)

 

## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





