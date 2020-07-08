---
title: 功能可见性设置
description: 功能可见性设置
author: dansimp
ms.assetid: 9db2ba03-fb75-4f95-9138-ec89b9fc8d01
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 26f19895d0a9163885779688ba7d89f6d16f2a17
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802764"
---
# 功能可见性设置


通过高级组策略管理（AGPM）的管理模板设置，你可以集中配置组策略对象（GPO）应用了组策略对象（GPO）的 "**更改控制**节点和**历史记录**" 选项卡的可见性。

在组策略管理控制台（GPMC）中编辑 GPO 时，"组策略对象编辑器" 中的 "用户 Configuration\\Administrative" 下提供了以下设置： "**组策略对象编辑器**" 中的 "Components\\Microsoft 管理控制台 \ \ 受限/允许 Snap-ins\\Extension" 管理单元。 如果此路径不可见，请右键单击 "**管理模板**"，然后添加 "agpm" 或 "agpm .adm" 模板。

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
<td align="left"><p><strong>AGPM 更改控件</strong></p></td>
<td align="left"><p>如果已启用或未配置，则在 <strong> GPMC 中将显示 "更改控制 </strong> " 节点。</p>
<p>如果已禁用，则 " <strong> 更改控制" </strong> 节点在 GPMC 中不可见。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>AGPM 链接扩展</strong></p></td>
<td align="left"><p>如果已启用或未配置， <strong> 则 </strong> 会在 GPMC 中为每个链接的 GPO 显示 "历史记录" 选项卡。</p>
<p>如果已禁用，则 " <strong> 历史记录" </strong> 选项卡对于链接的 gpo 不可见。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>AGPM GPO 扩展</strong></p></td>
<td align="left"><p>如果已启用或未配置， <strong> 则 </strong> 会在 GPMC 中为每个 GPO 显示 "历史记录" 选项卡。</p>
<p>如果禁用，则 " <strong> 历史记录" </strong> 选项卡对于 gpo 不可见。</p></td>
</tr>
</tbody>
</table>

 

### 其他参考资料

-   [管理模板设置](administrative-template-settings.md)

 

 





