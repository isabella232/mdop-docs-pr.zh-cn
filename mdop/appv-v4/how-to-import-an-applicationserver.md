---
title: 如何导入应用程序
description: 如何导入应用程序
author: dansimp
ms.assetid: ab40acad-1025-478d-8e13-0e1ff1bd37e4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7d9cd6d065ca28b5d856acdae7d10a1280105e9d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801403"
---
# 如何导入应用程序


通常，你可以导入应用程序以使其可从应用程序虚拟化管理服务器流出。 你还可以手动添加应用程序，但必须提供有关应用程序的精确的详细信息来执行此操作。 有关详细信息，请参阅[如何手动添加应用程序](how-to-manually-add-an-application.md)。

**注意** 若要导入应用程序，你必须在服务器上具有已排序的开放式软件描述符（OSD）文件或其 Sequencer 项目（SPRJ）文件。

 

导入应用程序时，应确保服务器在 "**系统选项**" 对话框的 "**常规**" 选项卡上的 "**默认内容路径**" 字段中配置了一个值（可通过右键单击 App-v Server 控制台中的 "**应用程序虚拟化系统**" 节点进行访问）。 默认内容路径值定义将在何处导入应用程序，在导入过程中，此值用于修改在 OSD 文件中为 SFT 文件和图标快捷方式定义的路径。 在 OSD 文件中，SFT 文件的路径在基本代码 HREF 条目中指定，图标的路径在快捷方式条目中指定。

在导入过程中，在 "协议"、"服务器" 和 "（如果存在）" 中，在 OSD 文件的这两个路径中指定的端口将替换为默认内容路径中的值。 下表提供了导入路径将受到影响的示例。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">默认内容路径</th>
<th align="left">OSD 文件基本代码 HREF</th>
<th align="left">结果值</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>\server\content &lt; /p&gt;</td>
<td align="left"><p><a href="http://WebServer/myFolder/package.sft" data-raw-source="http://WebServer/myFolder/package.sft">http://WebServer/myFolder/package.sft</a></p></td>
<td align="left"><p>\server\content\myFolder\package.sft</p></td>
</tr>
</tbody>
</table>

 

**导入应用程序**

1.  右键单击左窗格中的 "**应用程序**" 节点，然后选择 "**导入应用程序**"。

2.  在 "**打开**" 对话框中，导航到应用程序的 SPRJ 或 OSD 文件。 突出显示该文件，然后单击 "**打开**"。

3.  在 "**新建应用程序" 向导**中，确保已选中要传输的应用程序的 "**启用**" 框。 您也可以输入说明并验证服务器和文件路径。 此外，如果你已设置许可证和服务器组，你可以选择这些组。

4.  单击“下一步”****。

5.  在 "**已发布的快捷方式**" 屏幕上，选择要在客户端计算机上显示应用程序快捷方式的位置的框。

6.  单击“下一步”****。

7.  在 "**文件关联**" 屏幕中，你可以向此应用程序添加新的文件关联。 若要执行此操作，请单击 "**添加**"，输入扩展名（不带上点），输入说明，然后单击 **"确定"**。

    **注意** 使用 Sequencer 4.0 排序的应用程序在通过管理控制台导入或创建文件时，将填充 "**文件关联**" 对话框。 以前的 Sequencer 版本程序包的应用程序不是。

     

8.  单击“下一步”****。

9.  在 "**访问权限**" 屏幕中，单击 "**添加**"。

10. 完成 "**选择组**" 对话框。 完成后，单击 **"确定"**。

11. 单击“下一步”****。

12. 在 "**摘要**" 屏幕上，您可以查看导入设置。 单击 "**完成**"，或单击 "**返回**" 以更改导入，或单击 "**取消**" 以取消导入。

## 相关主题


[如何在 Server Management Console 中管理应用程序组](how-to-manage-application-groups-in-the-server-management-console.md)

[如何在 Server Management Console 中管理应用程序](how-to-manage-applications-in-the-server-management-console.md)

[如何手动添加应用程序](how-to-manually-add-an-application.md)

 

 





