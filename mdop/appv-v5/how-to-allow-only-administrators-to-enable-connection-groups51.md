---
title: 如何仅允许管理员启用连接组
description: 如何仅允许管理员启用连接组
author: dansimp
ms.assetid: 42ca3157-5d85-467b-a148-09404f8f737a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 083d6386f02996d35255f90958705798f2cd5fb9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798549"
---
# 如何仅允许管理员启用连接组


你可以配置 App-v 客户端，以便只有管理员（而非最终用户）可以启用或禁用连接组。 在早期版本的 App-v 中，你不能阻止最终用户执行这些任务。

**注意** 
**从 app-v 5.0 SP3 开始，支持此功能。**

 

使用以下方法之一，仅允许管理员启用或禁用连接组。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">方法</th>
<th align="left">步骤</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>组策略设置</p></td>
<td align="left"><p>启用 "要求发布为管理员" 组策略设置，该设置位于以下组策略对象节点中：</p>
<p><strong>计算机配置 &gt; 策略 &gt; 管理模板 &gt; 系统 &gt; 应用程序-V &gt; 发布</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>PowerShell cmdlet</p></td>
<td align="left"><p><strong> </strong> 通过 <strong> -RequirePublishAsAdmin 参数运行 AppvClientConfiguration cmdlet </strong> 。</p>
<p>参数值：</p>
<ul>
<li><p>0-假</p></li>
<li><p>1-True</p></li>
</ul>
<p><strong>示例： </strong> ： Set-AppvClientConfiguration-RequirePublishAsAdmin1</p></td>
</tr>
</tbody>
</table>

 

已**获得有关 app-v 的建议**？ 在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。 **遇到了 app-v 问题？** 使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相关主题


[管理连接组](managing-connection-groups51.md)

 

 





