---
title: 在管理控制台中配置应用程序和默认虚拟应用程序扩展
description: 如何使用管理控制台查看和配置应用程序和默认虚拟应用程序扩展
author: dansimp
ms.assetid: 1e1941d3-fb22-4077-8ec6-7a0cb80335d8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 09/26/2019
ms.openlocfilehash: 7c29ba0e40cf1adbc2b2297124cfb245a65a7ffe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798612"
---
#   在管理控制台中配置应用程序和默认虚拟应用程序扩展

使用以下过程*查看*和*配置*默认程序包扩展。

**查看和配置默认虚拟应用程序扩展**

1.  若要查看要配置的程序包，请打开 App-v 5.1 管理控制台。 选择要配置的程序包，右键单击程序包名称，然后选择 "**编辑默认配置**"。

2.  若要查看指定程序包中包含的应用程序，请在 "**默认配置**" 窗格中单击 "**应用程序**"。 若要查看该程序包的快捷方式，请单击 "**快捷方式**"。 若要查看该程序包的文件类型关联，请单击 "**文件类型**"。

3.  若要启用应用程序扩展，请选择 "**启用**"。

    若要启用快捷方式，请选择 "**启用快捷方式**"。 若要为所选应用程序添加新的快捷方式，请右键单击 "**快捷方式**" 窗格中的应用程序，然后选择 "**添加新快捷方式**"。 若要删除快捷方式，请右键单击 "**快捷方式**" 窗格中的应用程序，然后选择 "**删除快捷方式**"。 若要编辑现有快捷方式，请右键单击该应用程序，然后选择 "**编辑快捷方式**"。

4.  若要查看任何其他应用程序扩展，请单击 "**高级**"，然后单击 "**导出配置**"。 键入文件名，然后单击 "**保存**"。 你可以使用配置文件查看与程序包关联的所有应用程序扩展。

5.  若要编辑其他应用程序扩展，请修改配置文件，然后单击 "**导入并覆盖此配置**"。 选择修改后的文件，然后单击 "**打开**"。 在对话框中，单击 "**覆盖**" 以完成该过程。

>**注意**如果上载失败且配置文件的大小高于4MB，则需要增加服务器所允许的最大文件大小。 可通过将 maxRequestLength 属性添加为大于配置文件（KB）的值的 httpRuntime 元素添加到的行26上的元素来完成此操作 `C:\Program Files\Microsoft Application Virtualization Server\ManagementService\Web.config` 。  
例如，更改 `<httpRuntime targetFramework="4.5"/>` 为 `<httpRuntime targetFramework="4.5" maxRequestLength="8192"/>` 将把最大大小增加到8mb


已**获得有关 app-v 的建议**？ 在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。 **遇到了 app-v 问题？** 使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相关主题


[App-V 5.1 的操作](operations-for-app-v-51.md)

 

 





