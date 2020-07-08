---
title: 如何使用管理控制台为特定 AD 组自定义虚拟应用程序扩展
description: 如何使用管理控制台为特定 AD 组自定义虚拟应用程序扩展
author: dansimp
ms.assetid: 4f249ee3-cc2d-4b1e-afe5-d1cbf9cabd88
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 57ce4b82cc552e0a4adc2272f849111d8da0be71
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798499"
---
# 如何使用管理控制台为特定 AD 组自定义虚拟应用程序扩展


使用以下过程自定义 Active Directory （AD）组的虚拟应用程序扩展。

**自定义 AD 组的虚拟应用程序扩展**

1.  若要查看要配置的程序包，请打开 App-v 5.0 管理控制台。 若要查看分配给给定用户组的配置，请选择该程序包，然后右键单击该程序包名称，然后选择 "**编辑 active directory 访问**"。 或者，选择程序包，然后单击 "**广告访问**" 窗格中的 "**编辑**"。

2.  若要自定义广告组，您可以从**具有 Access 的广告实体**列表中找到该组。 然后，使用 "**分配的配置**" 窗格中的下拉框，选择 "**自定义**"，然后单击 "**编辑**"。

3.  若要禁用给定应用程序的所有扩展，请清除 "**启用**"。

    若要为所选应用程序添加新的快捷方式，请右键单击 "**快捷方式**" 窗格中的应用程序，然后选择 "**添加新快捷方式**"。 若要删除快捷方式，请右键单击 "**快捷方式**" 窗格中的应用程序，然后选择 "**删除快捷方式**"。 若要编辑现有快捷方式，请右键单击该应用程序，然后选择 "**编辑快捷方式**"。

4.  若要查看任何其他应用程序扩展，请单击 "**高级**"，然后单击 "**导出配置**"。 键入文件名，然后单击 "**保存**"。 你可以使用配置文件查看与程序包关联的所有应用程序扩展。

5.  若要编辑其他应用程序扩展，请修改配置文件，然后单击 "**导入并覆盖此配置**"。 选择修改后的文件，然后单击 "**打开**"。 在对话框中，单击 "**覆盖**" 以完成该过程。

    已**获得有关 app-v 的建议**？ 在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。 **遇到了 app-v 问题？** 使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相关主题


[App-V 5.0 的操作](operations-for-app-v-50.md)

 

 





