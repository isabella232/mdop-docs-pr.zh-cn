---
title: 如何使连接组忽略程序包版本
description: 如何使连接组忽略程序包版本
author: dansimp
ms.assetid: 6ebc1bff-d190-4f4c-a6da-e09a4cca7874
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b64d1938419aef184c5df667bf71b8157de0450a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798426"
---
# 如何使连接组忽略程序包版本


Microsoft Application Virtualization （App-v） 5.0 SP3 使你能够将连接组配置为使用任何版本的程序包，从而简化程序包升级并减少你需要创建的连接组的数量。

若要升级早期版本的 app-v 中的程序包，必须执行几个步骤，包括禁用连接组和修改连接组的 XML 定义文件。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">带有 App-v 5.0 SP3 的任务说明</th>
<th align="left">如何通过 App-v 5.0 SP3 执行任务</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>你可以将连接组配置为接受程序包的任何版本，这使你可以升级程序包，而无需禁用连接组。</p>
<p><strong>该功能的工作原理：</strong></p>
<ul>
<li><p>如果连接组具有对程序包的多个版本的访问权限，则使用最新版本。</p></li>
<li><p>如果连接组包含具有不正确版本的可选程序包，则会忽略该程序包，并且不会阻止创建连接组的虚拟环境。</p></li>
<li><p>如果连接组包含具有不正确版本的非可选程序包，则无法创建连接组的虚拟环境。</p></li>
</ul></td>
<td align="left"><table>
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
<td align="left"><p>App-v Server-管理控制台</p></td>
<td align="left"><ol>
<li><p>在管理控制台中，选择 " <strong> 程序包 </strong> &gt; <strong> 连接组" </strong> 。</p></li>
<li><p>从 "连接组" 库中选择正确的连接组。</p></li>
<li><p><strong> </strong> 在 "已连接的程序包" 窗格中单击 "编辑"。</p></li>
<li><p>选中 <strong> </strong> 程序包名称旁边的 "使用任意版本" 复选框，然后单击 " <strong> 应用" </strong> 。</p></li>
</ol>
<p>有关添加或升级程序包的详细信息，请参阅 <a href="how-to-add-or-upgrade-packages-by-using-the-management-console-beta-gb18030.md" data-raw-source="[How to Add or Upgrade Packages by Using the Management Console](how-to-add-or-upgrade-packages-by-using-the-management-console-beta-gb18030.md)"> 如何使用管理控制台添加或升级程序包 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>独立计算机上的 app-v 客户端</p></td>
<td align="left"><ol>
<li><p>创建连接组 XML 文档。</p></li>
<li><p>对于要升级的程序包，请将 " <strong> 程序包 </strong> 标签" 属性 "VersionID" 设置 <strong> </strong> 为星号（ <strong>*</strong> ）。</p></li>
<li><p>使用以下 cmdlet 添加连接组，并包含连接组 XML 文档的路径：</p>
<p><strong>Add-AppvClientConnectionGroup</strong></p></li>
<li><p>升级程序包时，请使用以下 cmdlet 删除旧程序包、添加已升级的程序包并发布已升级的程序包：</p>
<ul>
<li><p>RemoveAppvClientPackage</p></li>
<li><p>Add-AppvClientPackage</p></li>
<li><p>发布-AppvClientPackage</p></li>
</ul></li>
</ol>
<p>有关详细信息，请参阅：</p>
<ul>
<li><p><strong>此部分中包含可选程序包的示例 XML 文件、连接组 XML 文件 </strong> ： <a href="how-to-use-optional-packages-in-connection-groups.md#bkmk-apps-plugs-optional" data-raw-source="[How to Use Optional Packages in Connection Groups](how-to-use-optional-packages-in-connection-groups.md#bkmk-apps-plugs-optional)"> 如何在连接组中使用可选程序包</a></p></li>
<li><p><a href="how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md" data-raw-source="[How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md)">如何使用 PowerShell 管理在独立计算机上运行的 App-V 5.0 程序包</a></p></li>
</ul></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>

 






## 相关主题


[管理连接组](managing-connection-groups.md)

 

 





