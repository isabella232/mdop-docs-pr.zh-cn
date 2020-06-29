---
title: 如何生成报告
description: 如何生成报告
author: dansimp
ms.assetid: 9f8ba28e-1993-4c11-a28a-493718051e5d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 930b7061d3e5e2fb9951d45b1422915836cbc00e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804079"
---
# 如何生成报告


以下报告类型可由管理员在 MED-V 中创建：

-   [状态](#bkmk-generatingastatusreport)—使用 "状态" 报表，可根据定义的时间段查看每个用户的所有活动用户和所有 med-v 工作区的当前状态。 这包括查看当前已连接到服务器的计算机或当前未连接的计算机、其上次连接到服务器的日期和时间、每台计算机的状态以及其他相关信息。

-   [活动日志](#bkmk-generatinganactivitylogreport)-使用此报告查看来自定义的日期范围内的特定主机或用户的事件。

-   [错误日志](#bkmk-generatinganerrorlogreport)-使用此报告查看来自定义的日期范围内的特定主机或用户的错误。

可通过单击相应的列名称按任何列对报告结果进行排序。

可通过将列标题拖动到报表顶部来对报表结果进行分组。 拖动多个列标题，将一个列逐个分组。

## <a href="" id="bkmk-generatingastatusreport"></a>如何生成状态报告


**生成状态报告**

1.  单击 "**报告**管理" 按钮。

2.  在 "**报表" 模块的**"**报表类型**" 菜单上，选择 "**状态**"，然后单击 "**生成**"。

    将显示 "报表参数" 对话框。

3.  在 "**报表参数**" 对话框中的 "**天数**" 字段中，输入一个数字或使用箭头选择要在状态报告中包含的天数，然后单击 **"确定"**。

    将生成状态报告。 下表中定义了报表参数。

**客户端 MED-V 工作区属性**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">属性</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>时间</p></td>
<td align="left"><p>事件发生的日期和时间。</p>
<div class="alert">
<strong>注意</strong><br/><p>默认情况下，事件以降序显示日期顺序。 但是，可以通过单击 "接收时间" 列来更改它。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>用户名</p></td>
<td align="left"><p>启动事件的用户。</p>
<div class="alert">
<strong>注意</strong><br/><p>如果在用户登录之前发生事件，则用户名为 "SYSTEM"。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>主机名</p></td>
<td align="left"><p>主计算机的名称。</p></td>
</tr>
<tr class="even">
<td align="left"><p>工作区名称</p></td>
<td align="left"><p>MED-V 工作区的名称。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>工作区计算机名</p></td>
<td align="left"><p>MED-V 工作区在其上运行的计算机的名称。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Online</p></td>
<td align="left"><p>客户端计算机的当前状态：</p>
<ul>
<li><p><strong>禁用</strong></p></li>
<li><p><strong>在 &lt; 工作区开始的日期和时间开始&gt;</strong></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>客户端版本</p></td>
<td align="left"><p>客户端的版本号。</p></td>
</tr>
<tr class="even">
<td align="left"><p>策略版本</p></td>
<td align="left"><p>MED-V 工作区当前使用的策略版本。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>图像名称</p></td>
<td align="left"><p>图像的名称。</p></td>
</tr>
<tr class="even">
<td align="left"><p>图像版本</p></td>
<td align="left"><p>MED-V 工作区当前正在使用的映像版本。</p>
<div class="alert">
<strong>注意</strong><br/><p>如果 MED-V 工作区版本尚未下载到计算机，则可能是未知的。</p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-generatinganactivitylogreport"></a>如何生成活动日志报告


**生成活动日志报告**

1.  单击 "**报告**管理" 按钮。

    将显示 "报告" 模块。

2.  在 "**报表" 模块的**"**报表类型**" 菜单上，选择 "**活动日志**"，然后单击 "**生成**"。

3.  在 "**报表参数**" 对话框中，配置以下一个或多个参数：

    -   **天数**-在报表中显示的天数。

    -   **用户名包含**-报告中包含用户名包含输入文本的任何事件。

    -   **主机名包含**-报告中包含主机名中包含输入文本的任何事件。

4.  单击“确定”****。

    将生成一个报表，其中包含所选事件和日期。 下表中定义了报表参数。

**活动日志报表属性**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">属性</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>事件 ID</p></td>
<td align="left"><p>事件 ID。</p></td>
</tr>
<tr class="even">
<td align="left"><p>严重性</p></td>
<td align="left"><p><strong>信息、错误、警告</strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p>类型</p></td>
<td align="left"><p>报表所引用的模块。</p></td>
</tr>
<tr class="even">
<td align="left"><p>描述</p></td>
<td align="left"><p>事件的说明。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>收到时间</p></td>
<td align="left"><p>在服务器上接收事件的日期和时间。</p>
<div class="alert">
<strong>注意</strong><br/><p>如果客户端脱机工作，服务器将在客户端联机时收到报告。</p>
</div>
<div>

</div>
<div class="alert">
<strong>注意</strong><br/><p>默认情况下，事件以降序显示日期顺序。 但是，可以通过单击 "接收时间" 列来更改它 <strong> </strong> 。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>客户端时间</p></td>
<td align="left"><p>根据客户端时钟事件发生的日期和时间。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>主机名</p></td>
<td align="left"><p>主计算机的名称。</p></td>
</tr>
<tr class="even">
<td align="left"><p>用户名</p></td>
<td align="left"><p>启动事件的用户。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>工作区名称</p></td>
<td align="left"><p>MED-V 工作区的名称。</p></td>
</tr>
<tr class="even">
<td align="left"><p>工作区计算机名</p></td>
<td align="left"><p>MED-V 工作区在其上运行的计算机的名称。</p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-generatinganerrorlogreport"></a>如何生成错误日志报告


**生成错误日志报告**

1.  单击 "**报告**管理" 按钮。

2.  在 "**报表" 模块的**"**报表类型**" 菜单上，选择 "**错误日志**"，然后单击 "**生成**"。

3.  在 "**报表参数**" 对话框中，配置以下一个或多个参数：

    -   **天数**-在报表中显示的天数。

    -   **用户名包含**-报告中包含用户名包含输入文本的任何事件。

    -   **主机名包含**-报告中包含主机名中包含输入文本的任何事件。

4.  单击“确定”****。

    将生成一个报表，其中包含所选事件和日期。 下表中定义了报表参数。

**错误日志报告属性**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">属性</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>事件 ID</p></td>
<td align="left"><p>事件 ID。</p></td>
</tr>
<tr class="even">
<td align="left"><p>类型</p></td>
<td align="left"><p>报表所引用的模块。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>描述</p></td>
<td align="left"><p>事件的说明。</p></td>
</tr>
<tr class="even">
<td align="left"><p>收到时间</p></td>
<td align="left"><p>在服务器上接收事件的日期和时间。</p>
<div class="alert">
<strong>注意</strong><br/><p>如果客户端脱机工作，服务器将在客户端联机时收到报告。</p>
</div>
<div>

</div>
<div class="alert">
<strong>注意</strong><br/><p>默认情况下，事件以降序显示日期顺序。 但是，可以通过单击 "接收时间" 列来更改它 <strong> </strong> 。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>客户端时间</p></td>
<td align="left"><p>根据客户端时钟事件发生的日期和时间。</p></td>
</tr>
<tr class="even">
<td align="left"><p>主机名</p></td>
<td align="left"><p>主计算机的名称。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>用户名</p></td>
<td align="left"><p>启动事件的用户。</p></td>
</tr>
<tr class="even">
<td align="left"><p>工作区名称</p></td>
<td align="left"><p>MED-V 工作区的名称。</p></td>
</tr>
</tbody>
</table>











