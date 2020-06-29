---
title: 计划使用电子软件分发系统部署 App-V 5.0
description: 计划使用电子软件分发系统部署 App-V 5.0
author: dansimp
ms.assetid: 8cd3f1fb-b84e-4260-9e72-a14d01e7cadf
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ca441820be7e6759e65902aea18b2db7f989e8f0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798287"
---
# 计划使用电子软件分发系统部署 App-V 5.0


如果您使用电子软件分发系统来部署 app-v 程序包，请查看以下规划注意事项。 有关使用 System Center Configuration Manager 部署 app-v 的信息，请参阅[配置管理器中的应用程序管理简介](https://go.microsoft.com/fwlink/?LinkId=281816)。

查看使用 ESD 部署 app-v 程序包时应用的以下组件和体系结构要求选项：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">部署要求或选项</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>不需要 app-v 管理服务器、管理数据库和发布服务器。</p></td>
<td align="left"><p>这些函数由实施的 ESD 解决方案处理。</p></td>
</tr>
<tr class="even">
<td align="left"><p>你可以与 ESD 并排部署 app-v 报告服务器和报告数据库。</p></td>
<td align="left"><p>并行部署使你可以收集数据并生成报表。</p>
<p>如果你启用 App-v 客户端以发送报表信息，而你未使用 App-v 报告服务器，则报告数据将存储在关联的 .xml 文件中。</p></td>
</tr>
</tbody>
</table>

 






 

 





