---
title: 搜索和筛选 GPO 列表
description: 搜索和筛选 GPO 列表
author: dansimp
ms.assetid: 1bc58a38-033c-4aed-9eb4-c239827f5501
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5646a51a37a4ca9195fb9ef858e8c5920ca7738a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802547"
---
# 搜索和筛选 GPO 列表


在高级组策略管理（AGPM）中，您可以搜索组策略对象（Gpo）的列表及其属性以筛选所显示的 Gpo 列表。 例如，您可以搜索具有特定名称、状态或注释的 Gpo。 你还可以搜索特定组策略管理员或特定日期上次更改的 Gpo。

## 执行复杂的搜索


你可以使用 format *GPO 属性1：搜索字符串 1 GPO 属性2：搜索字符串 2 .。。所有列搜索字符串*。 搜索不区分大小写。

-   **GPO 属性：** 在除**计算机版本**或**用户版本**之外的 AGPM 中的 gpo 列表中的任何列标题。 GPO 属性包括 GPO 名称、状态、最近更改了 GPO 的用户、最新更改 gpo 的日期和时间、注释、GPO 状态和应用到 GPO 的 WMI 筛选器。

-   **搜索字符串：** 要在指定列中搜索的文本。 如果字符串包含空格，则必须用引号将字符串引起来。

-   **所有列搜索字符串：** 要在除**计算机版本**和**用户版本**之外的 AGPM 的 gpo 列表中的所有列中搜索的文本。 可以包含以空格分隔的多个字符串。 如果字符串包含空格，则必须用引号将字符串引起来。

每个 GPO 属性和搜索字符串对以及每个全列搜索字符串都使用逻辑 AND 运算组合。 结果是所有 Gpo 的列表，其中每个指定的属性都包含指定的搜索字符串，并且所有所有列的搜索字符串都显示在至少一个列中。 搜索将返回字符串的任何部分匹配项，以便你可以输入 GPO 名称或用户名的一部分，并查看其名称中包含该文本的所有 Gpo 的列表。

下面是搜索的示例：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">搜索结果说明</th>
<th align="left">搜索查询</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>名称中包含文本安全性和北美的所有 Gpo <strong> </strong> <strong> </strong> 。</p></td>
<td align="left"><p><strong>名称： </strong><strong> 安全 </strong><strong> 名称： </strong> 北美 &quot; <strong></strong>&quot;</p></td>
</tr>
<tr class="even">
<td align="left"><p>所有已签出的 Gpo。</p></td>
<td align="left"><p><strong>状态： </strong> &quot; <strong> 已签出</strong>&quot;</p></td>
</tr>
<tr class="odd">
<td align="left"><p>所有最近由用户（名为管理员）更改的 Gpo <strong> </strong> 和上个月内最近更改的 gpo。</p></td>
<td align="left"><p><strong>更改者： </strong><strong> 管理员 </strong><strong> 更改日期： </strong><strong> lastmonth</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>在 <strong> 最新注释中包含 word 防火墙的所有 gpo </strong> 以及 word <strong> 安全性 </strong> 出现在任何列中的所有 gpo。</p></td>
<td align="left"><p><strong>注释： </strong><strong> 防火墙 </strong><strong> 安全性</strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p>所有设置状态为 "已禁用" 的所有 Gpo <strong> </strong> 。</p></td>
<td align="left"><p><strong>gpo 状态： </strong><strong> 全部</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>应用了名为 <strong> "我的 Wmi 筛选器" </strong> 且状态为 "已 <strong> 禁用用户配置设置" 的 wmi 筛选器的所有 gpo </strong> 。</p></td>
<td align="left"><p><strong>wmi 筛选器： </strong> &quot; <strong> 我的 wmi 筛选器 </strong> &quot; <strong> gpo 状态： </strong><strong> 用户</strong></p></td>
</tr>
</tbody>
</table>

 

## 指定日期


你可以在特定时间通过使用在 Windows 中搜索时可用的相同特殊条件来搜索在特定日期、特定时间或一段时间内更改的 Gpo。 如果输入特定日期或时间，则必须使用 "**更改日期**" 列中使用的格式。 以下是 "**更改日期**" 列的搜索示例：

-   **更改日期：****10/10/2009**

-   **更改日期：****10/10/2009 9:00:00 AM**

-   **更改日期：****thisweek**

当您搜索 "**更改日期**" 列时，可以使用以下特殊术语（它们不区分大小写）：

-   **今天**

-   **昨天**

-   **ThisWeek**

-   **LastWeek**

-   **ThisMonth**

-   **LastMonth**

-   **TwoMonths**

-   **ThreeMonths**

-   **ThisYear**

-   **LastYear**

### 其他注意事项

-   默认情况下，你必须是审阅者、编辑者、审批者或 AGPM 管理员（完全控制）才能执行此过程。 具体而言，您必须具有域的 "**列表内容**" 权限。

-   有关 GPO 属性的详细信息，请参阅[目录选项卡功能](contents-tab-features-agpm40.md)。

### 其他参考资料

-   [高级组策略管理 4.0](advanced-group-policy-management-40.md)

 

 





