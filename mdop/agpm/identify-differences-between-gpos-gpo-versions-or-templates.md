---
title: 识别各 GPO、GPO 版本或模板之间的差异
description: 识别各 GPO、GPO 版本或模板之间的差异
author: dansimp
ms.assetid: 6320afc4-af81-47e8-9f4c-463ff99d5a53
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fd7966c9c72b2f0d30595af55520940c779a409f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802744"
---
# 识别各 GPO、GPO 版本或模板之间的差异


你可以生成基于 HTML 或基于 XML 的差异报表，以分析组策略对象（Gpo）、模板或 GPO 不同版本之间的差异。

需要具有审阅者、编辑者或 AGPM 管理员（完全控制）角色的用户帐户或高级组策略管理中的必需权限才能完成此过程。 查看本主题中 "其他注意事项" 中的详细信息。

## 确定 Gpo、GPO 版本或模板之间的差异


-   [在两个 Gpo 或模板之间](#bkmk-two-gpos)

-   [在 GPO 和模板之间](#bkmk-gpo-and-template)

-   [一个 GPO 的两个版本之间](#bkmk-two-versions)

-   [GPO 版本和模板之间](#bkmk-gpo-version-and-template)

## <a href="" id="bkmk-two-gpos"></a>


**确定两个 Gpo 或模板之间的差异**

1.  在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。

2.  在 "详细信息" 窗格中的 "**目录**" 选项卡上，单击选项卡以显示 gpo （如果比较两个模板，则是模板）。

3.  选择两个 Gpo 或模板。

4.  右键单击其中一个 Gpo 或模板，单击 "**差异**"，然后单击 " **HTML 报表**" 或 " **XML 报表**" 以显示汇总 gpo 或模板设置的差异报表。

### <a href="" id="bkmk-gpo-and-template"></a>

**确定 GPO 和模板之间的差异**

1.  在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。

2.  在 "详细信息" 窗格中的 "**目录**" 选项卡上，单击选项卡以显示 gpo （如果比较两个模板，则是模板）。

3.  右键单击该 GPO，单击 "**差异**"，然后单击 "**模板**"。

4.  选择模板和报告类型，然后单击 **"确定"** 以显示对 GPO 和模板设置进行汇总的差异报告。

### <a href="" id="bkmk-two-versions"></a>

**确定一个 GPO 的两个版本之间的差异**

1.  在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。

2.  在 "详细信息" 窗格中的 "**目录**" 选项卡上，单击选项卡以显示 gpo （如果比较两个模板，则是模板）。

3.  双击该 GPO 以显示其历史记录，然后突出显示要比较的版本。

4.  右键单击其中一个版本，单击 "**差异**"，然后单击 " **HTML 报表**" 或 " **XML 报表**" 以显示汇总 gpo 设置的差异报表。

### <a href="" id="bkmk-gpo-version-and-template"></a>

**确定 GPO 版本和模板之间的差异**

1.  在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。

2.  在 "详细信息" 窗格中的 "**目录**" 选项卡上，单击选项卡以显示 gpo （如果比较两个模板，则是模板）。

3.  双击该 GPO 以显示其历史记录。

4.  右键单击感兴趣的 GPO 版本，单击 "**差异**"，然后单击 "**模板**"。

5.  选择模板和报告类型，然后单击 **"确定"** 以显示对 GPO 版本和模板设置进行汇总的差异报告。

## 差异报告的关键


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

-   对设置所做的一些更改可能会导致将某项报告为两个不同的项目（仅在第一个 GPO 中出现，一个仅在第二个 GPO 中出现），而不是一个已更改的项目。

### 其他注意事项

-   默认情况下，你必须是审阅者、编辑者、审批者或 AGPM 管理员（完全控制）才能执行此过程。 具体而言，您必须具有该 GPO 的 "**列表内容**" 和 "**读取设置**" 权限。 此外，若要显示 Gpo 的列表，您必须拥有该域的 "**列表内容**" 权限。

### 其他参考资料

-   [执行审阅者任务](performing-reviewer-tasks.md)

 

 





