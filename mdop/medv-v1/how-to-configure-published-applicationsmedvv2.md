---
title: 如何配置已发布的应用程序
description: 如何配置已发布的应用程序
author: dansimp
ms.assetid: 43a59ff7-5d4e-49dc-84e5-1082bc4dd8f4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cb5736382f03e818ef10aa814a8e61044ca2b73a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803543"
---
# 如何配置已发布的应用程序


与主机操作系统不兼容的应用程序可以在 MED-V 工作区中运行，也可以从从桌面开始的相同方式（从 "开始" 菜单或从本地主机快捷方式开始）内运行。 所选和定义的应用程序称为已发布的应用程序。 本节中的过程介绍了如何添加和删除已发布的应用程序。

可通过以下方式之一发布应用程序：

-   作为应用程序-通过在应用程序的命令行中键入来选择特定应用程序。 仅发布选定的应用程序。

-   作为菜单-选择包含多个应用程序的文件夹。 文件夹中的所有应用程序都将发布并显示为菜单。

## <a href="" id="bkmk-addingapublishedapplication"></a>如何将已发布的应用程序添加到 MED-V 工作区


**将应用程序添加到 MED-V 工作区**

1.  单击要配置的 MED-V 工作区。

2.  在 "**应用程序**" 窗格的 "**已发布的应用程序**" 部分中，单击 "**添加**" 以添加新应用程序。

3.  按下表所述配置应用程序属性。

4.  在 "**策略**" 菜单上，选择 "**提交**"。

    **注意**  
    如果你将 Internet Explorer 设置为已发布的应用程序以确保 Web 重定向正常工作，请确保所有参数都不在括号中。



**已发布的应用程序属性**

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
<td align="left"><p>启用</p></td>
<td align="left"><p>选中此复选框以启用已发布的应用程序。</p></td>
</tr>
<tr class="even">
<td align="left"><p>显示名称</p></td>
<td align="left"><p>用户&#39;s Windows "开始" 菜单中的快捷方式的名称。</p>
<div class="alert">
<strong>注意</strong><br/><p>显示名称 <strong> 不 </strong> 区分大小写。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>描述</p></td>
<td align="left"><p>已发布应用程序的说明，当用户&#39;s 鼠标悬停在快捷方式上时，该说明将显示为工具提示。</p></td>
</tr>
<tr class="even">
<td align="left"><p>命令行</p></td>
<td align="left"><p>用于从 MED-V 工作区中运行应用程序的命令。 完整路径是必需的，并且参数可以与任何其他 Windows 命令中类似的方式传递到应用程序。</p>
<p>在 revertible med-v 工作区中，你可以使用 MapNetworkDrive 语法： &quot; <em> MapNetworkDrive &lt; 驱动器 &gt; &lt; 路径 &gt; </em> &quot; （例如 &quot; <em> MapNetworkDrive t： \tux\date） </em> &quot; 映射网络驱动器。</p>
<p>例如，若要发布 Windows 资源管理器，请使用以下语法： &quot; <em> c： &lt; /em &gt; &quot; 或 &quot; <em> c：\windows </em> 。&quot;</p>
<div class="alert">
<strong>注意</strong><br/><p>若要进行名称解析，您需要执行下列操作之一：</p>
</div>
<div>

</div>
<ul>
<li><p>在 "基本 MED-V-V" 工作区映像中配置 DNS。</p></li>
<li><p>验证主机中是否定义了 DNS 解析，并将其配置为使用主机 DNS。</p></li>
<li><p>使用 IP 定义网络驱动器。</p></li>
</ul>
<div class="alert">
<strong>注意</strong><br/><p>如果路径中包含空格，则整个路径必须位于引号内。</p>
</div>
<div>

</div>
<div class="alert">
<strong>注意</strong><br/><p>路径不应以反斜杠（）结尾。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>“开始”菜单</p></td>
<td align="left"><p>选中此复选框可在用户&#39;s Windows "开始" 菜单中创建应用程序的快捷方式。</p></td>
</tr>
</tbody>
</table>



所有发布的应用程序在 Windows "**开始**" 菜单中显示为快捷方式（"**启动 &gt; 所有程序" &gt; med-v 应用程序**）。

## 如何从 MED-V 工作区中删除已发布的应用程序


**从 MED-V 工作区中删除应用程序**

1.  单击 MED-V 工作区。

2.  在 "**应用程序**" 窗格的 "**已发布的应用程序**" 部分中，选择要删除的应用程序。

3.  单击 "**删除**"。

    该应用程序将从已发布的应用程序列表中删除。

4.  在 "**策略**" 菜单上，选择 "**提交**"。

## 如何将已发布的菜单添加到 MED-V 工作区


**将发布的菜单添加到 MED-V 工作区**

1.  单击要配置的 MED-V 工作区。

2.  在 "**应用程序**" 窗格的 "**已发布的菜单**" 部分中，单击 "**添加**" 以添加新菜单。

3.  按下表所述配置菜单属性。

4.  在 "**策略**" 菜单上，选择 "**提交**"。

**已发布的菜单属性**

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
<td align="left"><p>启用</p></td>
<td align="left"><p>选中此复选框以启用 "已发布" 菜单。</p></td>
</tr>
<tr class="even">
<td align="left"><p>显示名称</p></td>
<td align="left"><p>用户&#39;s Windows "开始" 菜单中的快捷方式的名称。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>描述</p></td>
<td align="left"><p>说明，当用户&#39;s 鼠标悬停在快捷方式上时显示为工具提示。</p></td>
</tr>
<tr class="even">
<td align="left"><p>工作区中的文件夹</p></td>
<td align="left"><p>选择要发布的文件夹，将其作为包含文件夹中所有应用程序的菜单。</p>
<p>显示的文本是 "程序" 文件夹中的相对路径。</p>
<div class="alert">
<strong>注意</strong><br/><p>如果保留为空，将把主机上的所有程序发布为一个菜单。</p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



所有已发布的菜单在 Windows "**开始**" 菜单中显示为快捷方式（"**启动 &gt; 所有程序" &gt; med-v 应用程序**）。 可以在 "**开始-菜单快捷方式" 文件夹**字段中更改快捷方式的名称。

**注意**  
配置两个 MED-V 工作区时，建议为 "开始" 菜单快捷方式文件夹配置不同的名称。



## 如何从 MED-V 工作区中删除已发布的菜单


**从 MED-V 工作区中删除已发布的菜单**

1.  单击 MED-V 工作区。

2.  在 "**应用程序**" 窗格的 "**已发布的菜单**" 部分中，选择要删除的菜单。

3.  单击 "**删除**"。

    将从已发布菜单的列表中删除该菜单。

4.  在 "**策略**" 菜单上，选择 "**提交**"。

## 从客户端上的命令行运行已发布的应用程序


管理员可以使用以下命令从任意位置（如桌面快捷方式）运行已发布的应用程序：

``` syntax
"<Install path>\Manager\KidaroCommands.exe" /run "<published application name>" "<MED-V workspace name>"
```

**注意**  
在其中定义已发布应用程序的 MED-V 工作区必须正在运行。



## 相关主题


[如何使用高级设置编辑已发布的应用程序](how-to-edit-a-published-application-with-advanced-settings.md)

[使用 MED-V 管理控制台用户界面](using-the-med-v-management-console-user-interface.md)

[创建 MED-V 工作区](creating-a-med-v-workspacemedv-10-sp1.md)









