---
title: 监视 Web 服务请求性能计数器
description: 监视 Web 服务请求性能计数器
author: dansimp
ms.assetid: bdb812a1-465a-4098-b4c0-cb99890d1b0d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 2db96e3375562b48d289ea5a21dc7e89b800d1ad
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803456"
---
# 监视 Web 服务请求性能计数器


Microsoft BitLocker 管理和监视（MBAM）提供的性能计数器记录发送到以下 web 服务的请求的性能：

-   **StatusReportingService** –接收合规性状态请求的服务

-   **CoreService** –接收对密钥恢复尝试的请求的服务

## MBAM 提供的性能计数器


MBAM 为由其 StatusReportingService 和 CoreService web 服务实现的每个公共方法提供以下性能计数器：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">性能计数器的类型</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>请求总数</p></td>
<td align="left"><p>提供启动或重启服务器时从零开始的增量计数。</p>
<p>提供系统活动的整体视图。 可通过自动化工具进行监视，以确保服务器的运行状况并验证计数器在指定时间段内持续增加。</p></td>
</tr>
<tr class="even">
<td align="left"><p>每秒请求数</p></td>
<td align="left"><p>指示 MBAM 服务器的当前吞吐量，因为它支持 MBAM 客户端基础。</p>
<p>使网站管理员能够：</p>
<ul>
<li><p>基于 MBAM 客户端数及其报告频率，计算每秒的平均请求数。</p></li>
<li><p>验证每秒的请求数是否广泛与计算每秒的平均请求数之和。 显著的差异可指示 MBAM 客户端未安装在客户端基础的一定百分比或 MBAM 组策略对象未成功部署。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>请求持续时间</p></td>
<td align="left"><p>记录请求的持续时间（以毫秒为单位）。</p>
<p>虽然此计数器在每个请求的持续时间内更新，但 Windows 性能监视器仅定期（通常是每秒）对其进行采样，因此你可能会在值中看到一些可变性。 出于此原因，请考虑使用性能监视器显示的平均值。</p></td>
</tr>
</tbody>
</table>

 

## 性能计数器结果和建议


将新的 MBAM 客户添加到具有备用容量的 MBAM 服务器时，预计每秒的请求数会增加。 此增长将与新客户端计算机的数量成比例。 平均请求持续时间将保持相对静态。 当服务器接近其最大容量时，每秒的请求开始到 "停止"，并且平均请求持续时间开始时间较长。

如果你担心你的 MBAM 服务器是否可以支持你的客户端基础，请考虑在客户端计算机的不同集合阶段部署 MBAM。 当你将 MBAM 部署到每个客户端计算机集合时，我们建议你拍摄性能计数器的快照，以查看部署到每个新客户端集合的相对影响。 如果每秒的请求数从 "开始" 到 "级别"，并且平均请求持续时间增加，请考虑通过执行下列操作之一来增强 MBAM 服务器基础结构：

-   将 MBAM 数据库移动到专用 Microsoft SQL Server 或 SQL Server 群集

-   跨多个 Internet Information Services （IIS） web 服务器的负载平衡 MBAM

-   在功能更强大的服务器硬件上部署 MBAM

## 查看性能计数器


用于查看 MBAM 性能计数器的推荐工具是 Windows 性能监视器，它随 Windows 提供。 如果你使用的是 Windows PowerShell，则无需在查看计数器之前启用它们，因为它们由 Windows PowerShell **enable webapplication** cmdlet 自动注册。

有关如何查看性能计数器的详细说明，请参阅[如何查看 MBAM 性能计数器](https://go.microsoft.com/fwlink/?LinkId=393457)。



## 相关主题


[维护 MBAM 2.5](maintaining-mbam-25.md)

 

 


## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。


