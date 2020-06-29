---
title: “历史记录”窗口
description: “历史记录”窗口
author: dansimp
ms.assetid: f11f9ad9-bffe-4c56-8c46-fe9c0a8e55c1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 02b4336409f33d6c1f2868bceb22cb95120f2198
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802756"
---
# “历史记录”窗口


通过双击 GPO 或右键单击 GPO，然后单击 "**历史记录**"，可以显示组策略对象（GPO）的历史记录。 它还显示在**组策略管理控制台**（GPMC）中，作为每个 GPO 的选项卡。

历史记录提供在存档中保存的选定 GPO 的所有版本的列表。 在 "**历史记录**" 窗口中，你可以获取 gpo 中的设置的报表、比较 gpo 的多个版本或回退到 gpo 的早期版本。

## 在 "历史记录" 窗口中筛选事件


"**历史记录**" 窗口中的选项卡将筛选显示的事件。

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
<td align="left"><p><strong>全部显示</strong></p></td>
<td align="left"><p>显示 GPO 的所有版本。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>已签入</strong></p></td>
<td align="left"><p>仅显示 GPO 的已签入版本。 此列表中省略了已部署的版本。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>仅限标签</strong></p></td>
<td align="left"><p>仅显示与其相关联的标签的 Gpo。</p></td>
</tr>
</tbody>
</table>

 

## 事件信息


为所选 GPO 的历史记录中的每个事件提供了信息。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">GPO 特性</th>
<th align="left">说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>计算机</strong></p></td>
<td align="left"><p>GPO 的计算机配置部分的自动生成的版本。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>用户</strong></p></td>
<td align="left"><p>GPO 的用户配置部分的自动生成的版本。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>时间</strong></p></td>
<td align="left"><p>在执行 "状态" 字段中的操作时，GPO 版本的时间戳。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>State</strong></p></td>
<td align="left"><p>GPO 的选定版本的状态：</p>
<p><img src="images/36f6b687-f5cc-40d1-805f-b191d1fb1ace.gif" alt="Deployed GPO icon" /> <strong>已部署 </strong> ：此版本的 GPO 当前处于生产环境中。</p>
<p><img src="images/57b610a5-1c71-4d26-9173-d04abd495fcc.gif" alt="Checked in GPO icon" /> <strong>已签入 </strong> ：此版本的 GPO 可供授权编辑人员签出以进行编辑或组策略管理员进行部署。</p>
<p><img src="images/8e7a7c4e-809a-435a-8b29-30d797936210.gif" alt="Checked out GPO icon" /> <strong>已签出 </strong> ：该 GPO 的当前版本当前由一个编辑器签出，并且不适用于其他编辑器。 （签出状态不会记录在 <strong>历史记录 </strong> ，除了指示 GPO 当前是否已签出。）</p>
<p><img src="images/327623bd-0842-4372-be1f-bdc4b8c3481c.gif" alt="Created GPO icon" /> <strong>已创建 </strong> ：标识最初创建 GPO 的日期和时间。</p>
<p><img src="images/8356fcdc-1279-425b-ab14-a23bcfe391da.gif" alt="Labeled GPO icon" /> <strong>标记 </strong> ：标识 GPO 的标记版本。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>GPO 状态</strong></p></td>
<td align="left"><p>计算机配置和用户配置可以彼此分开管理。 此状态显示启用了 GPO 的哪些部分。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>所有者</strong></p></td>
<td align="left"><p>已签入或已部署 GPO 的人员。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>评论</strong></p></td>
<td align="left"><p>修改此版本时 GPO 所有者输入的评论。 在需要回滚到以前版本的情况下，用于识别版本的详细信息。</p></td>
</tr>
</tbody>
</table>

 

## 报告


根据是否选择了单个 GPO 版本或多个 GPO 版本，"**设置**" 和 "**差异**" 按钮将显示有关 GPO 设置的报告。 右键单击 "GPO 版本" 提供了用于显示基于 XML 的报表的选项。

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
<td align="left"><p><strong>“设置”</strong></p></td>
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

-   对设置所做的一些更改可能会导致将某项报告为两个不同的项目（仅在第一个 GPO 中显示，另一个仅在第二个 GPO 中出现），而不是更改的一个项目。

### 其他参考资料

-   [“内容”选项卡](contents-tab.md)

 

 





