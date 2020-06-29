---
title: AGPM 服务器连接设置
description: AGPM 服务器连接设置
author: dansimp
ms.assetid: 5f03e397-b868-4c49-9cbf-a5f5d0ddcc39
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d9ee1e67eb2c565bcf833314d82cdf611e2caa85
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798183"
---
# AGPM 服务器连接设置


你可以使用高级组策略管理（AGPM）的管理模板设置来集中配置组策略对象（GPO）应用了组策略对象（GPO）的 AGPM 服务器连接。

编辑 GPO 时，用户 Configuration\\Policies\\Administrative Templates\\Windows Components\\AGPM 下提供以下设置。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">设置</th>
<th align="left">作用</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>AGPM：指定默认的 AGPM 服务器（所有域）</strong></p></td>
<td align="left"><p>通过此策略设置，你可以为所有域指定默认的 AGPM 服务器。 这仅由 AGPM 客户端使用，并且限制组策略管理员连接到另一个存档。 你可以使用 AGPM： "指定 AGPM 服务器" 设置替代单个域的此默认 <strong> </strong> 设置。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>AGPM：指定 AGPM 服务器</strong></p></td>
<td align="left"><p>通过此策略设置，你可以为单个域指定 AGPM 服务器。 这仅由 AGPM 客户端使用，并且限制组策略管理员连接到指定域的其他存档。 若要指定默认的 AGPM 服务器，请使用 " <strong> AGPM：指定默认 Agpm 服务器（所有域）" </strong> 设置，并使用此策略设置替代每个域的默认值。</p></td>
</tr>
</tbody>
</table>

 

### 其他参考资料

-   [“管理模板”文件夹](administrative-templates-folder-agpm30ops.md)

-   [执行 AGPM 管理员任务](performing-agpm-administrator-tasks-agpm30ops.md)

 

 





