---
title: 如何安装 Sequencer
description: 如何安装 Sequencer
author: dansimp
ms.assetid: 5e8f1696-9bc0-4f44-8cb7-b809b2daae10
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b72330718a14cb8ffb0e582c946ff1e70539036c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798427"
---
# 如何安装 Sequencer


使用以下过程安装 Microsoft Application Virtualization （App-v） 5.1 sequencer。 将运行 sequencer 的计算机不能运行任何版本的 App-v 5.1 客户端。

不支持升级以前安装的 app-v sequencer。

**重要提示** 有关 sequencer 要求的完整列表，请参阅[app-v 5.1 先决条件](app-v-51-prerequisites.md)和[app-v 5.1 支持的配置](app-v-51-supported-configurations.md)的 sequencer 部分。

 

你还可以使用命令行安装 app-v 5.1 sequencer。 以下列表显示有关使用命令行和**appv\_sequencer\_setup.exe**安装 sequencer 的选项的信息：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">命令</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>/INSTALLDIR</p></td>
<td align="left"><p>指定安装目录。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/CEIPOPTIN</p></td>
<td align="left"><p>允许参与 Microsoft 客户体验改善计划。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/Log</p></td>
<td align="left"><p>指定将保存安装日志的位置，默认位置为 <strong> % Temp% </strong> 。 例如， <strong> C：\日志记录 \ </strong> .log。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/q</p></td>
<td align="left"><p>指定安静或静默安装。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/Uninstall</p></td>
<td align="left"><p>指定删除 sequencer。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/ACCEPTEULA</p></td>
<td align="left"><p>接受许可协议。 这是无人参与安装所必需的。 示例用法： <strong> /ACCEPTEULA </strong> 或 <strong> /ACCEPTEULA = 1 </strong> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/LAYOUT</p></td>
<td align="left"><p>指定关联的布局操作。 它还将 Windows Installer （.msi）和脚本文件提取到文件夹中，但不安装 app-v 5.1。 不应为任何值。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/LAYOUTDIR</p></td>
<td align="left"><p>指定布局目录。 需要字符串值。 示例用法： <strong> /LAYOUTDIR = "C:\Application Virtualization 客户端" </strong> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/? 或/h 或/help</p></td>
<td align="left"><p>显示相关帮助。</p></td>
</tr>
</tbody>
</table>

 

**安装 app-v 5.1 sequencer**

1.  将 app-v 5.1 sequencer 安装文件复制到将在其上安装的计算机。 双击 " **appv\_sequencer\_setup.exe** "，然后单击 "**安装**"。

2.  在 "**软件许可条款**" 页面上，应查看许可条款。 接受许可条款选择 "**我接受许可条款"。** 单击“下一步”****。

3.  在 "**使用 Microsoft 更新" 帮助保持计算机的安全和最新**页面上，若要启用 microsoft 更新，请选择 "**当我检查更新时使用 Microsoft 更新" （推荐）。** 若要从运行中禁用 Microsoft 更新，请选择 "**我不想使用 Microsoft 更新**"。 单击“下一步”****。

4.  在 "**客户体验改善计划**" 页面上，若要参与计划，请选择 "**加入客户体验改善计划"**。 这将允许收集有关使用 app-v 5.1 的方式的信息。 如果您不想参与该计划，请选择 "**我现在不想加入程序"**。 单击**安装**。

5.  若要打开排序器，请单击 "**开始**"，然后单击 " **Microsoft Application Virtualization sequencer**"。

**解决 app-v 5.1 sequencer 安装**

-   有关 sequencer 安装的详细信息，您可以在 **% temp%** 文件夹中查看错误日志。 若要查看日志文件，请单击 "**开始**"，键入 **% temp%**，然后查找**appv\_ 日志**。

    已**获得有关 app-v 的建议**？ 在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。 **遇到了 app-v 问题？** 使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相关主题


[计划部署 App-V](planning-to-deploy-app-v51.md)

 

 





