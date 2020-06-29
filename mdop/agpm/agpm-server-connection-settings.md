---
title: AGPM 服务器连接设置
description: AGPM 服务器连接设置
author: dansimp
ms.assetid: faf78e5b-2b0d-4069-9b8c-910add892200
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d63163de0a1adf744e6d442b8073e5b32352ed67
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798191"
---
# AGPM 服务器连接设置


你可以使用高级组策略管理（AGPM）的管理模板设置来集中配置组策略对象（GPO）应用了组策略对象（GPO）的 AGPM 服务器连接。

编辑 GPO 时，用户 Configuration\\Administrative Templates\\Windows Components\\AGPM 下提供以下设置。 如果此路径不可见，请右键单击 "**管理模板**"，然后添加 "agpm" 或 "agpm .adm" 模板。

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
<td align="left"><p><strong>AGPM 服务器（所有域）</strong></p></td>
<td align="left"><p>如果已启用，此设置将集中配置一个 AGPM 服务器连接供所有域使用，并禁用 <strong> 组策略管理员的 AGPM 服务器选项卡上的设置 </strong> 。 对于多个 AGPM 服务器，使用默认服务器配置此设置，然后 <strong> </strong> 在 "管理模板" 中配置 AGPM 服务器设置以替代其他域的此服务器。</p>
<p>如果已禁用或未配置，每个组策略管理员必须在 <strong> agpm 的 Agpm 服务器选项卡上选择要为每个域显示的 AGPM 服务器 </strong> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>AGPM 服务器</strong></p></td>
<td align="left"><p>如果启用，此设置将集中配置多个特定于域的 AGPM 服务器，替代 <strong> 管理模板中的 "AGPM 服务器（所有域）" </strong> 设置。 如果你的环境仅需要单个 AGPM 服务器，请仅使用 <strong> 管理模板中的 "Agpm 服务器（所有域）" </strong> 设置。</p>
<p>如果 "已禁用" 或 "未配置"，则 <strong> 管理模板中的 "AGPM 服务器（所有域）" </strong> 设置将配置 AGPM 服务器连接。</p></td>
</tr>
</tbody>
</table>

 

### 其他参考资料

-   [管理模板设置](administrative-template-settings.md)

-   [执行 AGPM 管理员任务](performing-agpm-administrator-tasks.md)

 

 





