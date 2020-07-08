---
title: “历史记录”窗口
description: “历史记录”窗口
author: dansimp
ms.assetid: 5bea62e7-d267-40b2-a66d-fb1be7373a1c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 81f19e3834e945a45238856e23f6ee4a86407c4a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802759"
---
# “历史记录”窗口


通过双击 GPO 或右键单击 GPO，然后单击 "**历史记录**"，可以显示组策略对象（GPO）的历史记录。 它还显示在组策略管理控制台（GPMC）中，作为每个 GPO 的选项卡。

历史记录在所选 GPO 的生命周期内提供事件记录。 在 "**历史记录**" 窗口中，你可以获取 gpo 版本中的设置的报告，比较 gpo 的多个版本，或者回滚到 gpo 的早期版本。

## 在 "历史记录" 窗口中筛选事件


"**历史记录**" 窗口中的选项卡将筛选 GPO 历史记录中的状态。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Tabs</th>
<th align="left">筛选</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>所有状态</strong></p></td>
<td align="left"><p>显示 GPO 历史记录中的所有状态。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>唯一版本</strong></p></td>
<td align="left"><p>仅显示已签入存档的 GPO 的唯一版本。 此列表中省略了部署到生产环境的版本、指向唯一版本的快捷方式和信息状态。</p></td>
</tr>
</tbody>
</table>



## 事件信息


为 GPO 历史记录中的每个状态提供了信息。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">GPO 属性</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>更改日期</strong></p></td>
<td align="left"><p>在 "状态" 列中执行操作的时间戳 <strong> </strong> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>State</strong></p></td>
<td align="left"><p>GPO 历史记录中的状态。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>更改者</strong></p></td>
<td align="left"><p>已签入或已部署 GPO 的人员。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>评论</strong></p></td>
<td align="left"><p>在此版本发生更改时由签入或部署 GPO 的人员输入的注释，用于识别版本的细节，以防需要回滚到早期版本。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>已</strong></p></td>
<td align="left"><p>如果存档中保留的每个 GPO 的唯一版本数受到限制，是否可以删除此 GPO 版本。</p>
<div class="alert">
<strong>注意</strong><br/><p>你可以通过右键单击 GPO，然后单击 "不 <strong> 允许删除" </strong> 或 " <strong> 允许删除" 来更改 gpo 的版本是否可以删除 </strong> 。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><strong>计算机版本</strong></p></td>
<td align="left"><p>GPO 的 "计算机配置" 部分的自动生成的版本。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>用户版本</strong></p></td>
<td align="left"><p>GPO 的用户配置部分的自动生成的版本。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>GPO 状态</strong></p></td>
<td align="left"><p>计算机配置和用户配置可以彼此分开管理。 此状态显示启用了 GPO 的哪些部分。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>源 GPO 信息</strong></p></td>
<td align="left"><p>对于从另一个目录林中导入的 GPO，原始 GPO 名称、域和用户以及与上次更改相关联的日期。</p></td>
</tr>
</tbody>
</table>



## 报告


"**设置**和**差异**" 按钮显示有关所选 gpo 版本或版本的 gpo 设置的报告。 此外，右键单击 GPO 版本或版本可提供用于显示基于 XML 的报表的选项。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">按钮</th>
<th align="left">作用</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>设置</strong></p></td>
<td align="left"><p>生成基于 HTML 的报表，显示所选版本的 GPO 中的设置。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>不同之处</strong></p></td>
<td align="left"><p>生成用于比较 GPO 的多个选定版本内的设置的基于 HTML 的报表。</p></td>
</tr>
</tbody>
</table>



### 差异报告的关键

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">符号</th>
<th align="left">含义</th>
<th align="left">颜色</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>无</p></td>
<td align="left"><p>具有两个 Gpo 中的相同设置的项目存在</p></td>
<td align="left"><p>级别不同</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>[#]</strong></p></td>
<td align="left"><p>项目存在于两个 Gpo 中，但具有更改后的设置</p></td>
<td align="left"><p>淡蓝</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>[-]</strong></p></td>
<td align="left"><p>项目仅存在于第一个 GPO 中</p></td>
<td align="left"><p>红色</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>[+]</strong></p></td>
<td align="left"><p>项目仅存在于第二个 GPO 中</p></td>
<td align="left"><p>绿色</p></td>
</tr>
</tbody>
</table>



-   对于具有已更改设置的项目，已更改的设置将在项目展开时标识。 每个 GPO 中属性的值的显示顺序与在报表中显示 Gpo 的顺序相同。

-   对设置所做的一些更改可能会导致将某项报告为两个项目（仅在第一个 GPO 中显示，另一个仅在第二个 GPO 中出现），而不是更改的一个项目。

### 其他参考资料

-   [“内容”选项卡](contents-tab-agpm40.md)









