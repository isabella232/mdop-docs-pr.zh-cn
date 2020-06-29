---
title: App-V 预安装清单
description: App-V 预安装清单
author: dansimp
ms.assetid: 3af609b1-2c09-4edb-b083-b913b6d5e8c4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 70e71d3dea02daeadedb4cff78c58302ac743dda
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802356"
---
# App-V 预安装清单


下面的清单旨在提供要考虑的项目的高级列表，并概括介绍在安装 Microsoft Application Virtualization （app-v）服务器之前应执行的步骤。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">步骤</th>
<th align="left">参考</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>确保你的计算环境满足 App-v 所需的支持配置。</p></td>
<td align="left"><p><a href="application-virtualization-deployment-requirements.md" data-raw-source="[Application Virtualization Deployment Requirements](application-virtualization-deployment-requirements.md)">Application Virtualization 部署要求</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>配置必要的 Active Directory 组和帐户。</p></td>
<td align="left"><p><a href="configuring-prerequisite-groups-in-active-directory-for-app-v.md" data-raw-source="[Configuring Prerequisite Groups in Active Directory for App-V](configuring-prerequisite-groups-in-active-directory-for-app-v.md)">在 Active Directory 中为 App-V 配置必备组</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>在运行 IIS 的服务器上配置 Internet 信息服务（IIS）设置。</p></td>
<td align="left"><p><a href="how-to-configure-windows-server-2008-for-app-v-management-servers.md" data-raw-source="[How to Configure Windows Server 2008 for App-V Management Servers](how-to-configure-windows-server-2008-for-app-v-management-servers.md)">如何为 App-V Management Server 配置 Windows Server 2008</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>将运行 IIS 的服务器配置为受信任的委派。</p>
<div class="alert">
<strong>注意</strong><br/><p>只有当你使用分布式系统体系结构安装 app-v 管理服务器（即，如果你在不同计算机上安装了 app-v 管理控制台、管理 Web 服务和数据库）时，此操作才是必需的。</p>
</div>
<div>

</div></td>
<td align="left"><p><a href="how-to-configure-the-server-to-be-trusted-for-delegation.md" data-raw-source="[How to Configure the Server to be Trusted for Delegation](how-to-configure-the-server-to-be-trusted-for-delegation.md)">如何将服务器配置为受信任以进行委派</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>安装 Microsoft SQL Server 2008。</p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=181924" data-raw-source="[Install SQL Server 2008](https://go.microsoft.com/fwlink/?LinkId=181924)">安装 SQL Server 2008 </a> （ <a href="https://go.microsoft.com/fwlink/?LinkId=181924" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=181924"> https://go.microsoft.com/fwlink/?LinkId=181924 </a> ）。</p></td>
</tr>
</tbody>
</table>



## 相关主题


[Application Virtualization 部署和升级清单](application-virtualization-deployment-and-upgrade-checklists.md)

[App-V 安装清单](app-v-installation-checklist.md)









