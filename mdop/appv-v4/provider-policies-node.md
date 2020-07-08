---
title: “提供程序策略”节点
description: “提供程序策略”节点
author: dansimp
ms.assetid: 89b47076-7732-4128-93cc-8e6d5b671c8e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 221171b22471a4a8614b13023b24dd21fd571dd3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798850"
---
# “提供程序策略”节点


"**提供程序策略**" 节点位于应用程序虚拟化服务器管理控制台的 "**范围**" 窗格中 "应用程序虚拟化系统" 节点下的一个级别。 选择此节点时，"**结果**" 窗格将显示提供商策略的列表。 右键单击 "**提供商策略**" 节点以显示包含以下元素的弹出菜单。

<a href="" id="new-provider-policy"></a>**新的提供商策略**  
显示 "新建提供程序策略" 向导。 此向导包含以下页面：

1.  在 "**提供商策略名称**" 字段中输入一个名称。 如果需要此功能，请选中 "**使用管理控制台管理客户端桌面"** 复选框。 如果需要相关联的功能，请选中以下一个或两个复选框：

    -   **用户登录时刷新发布配置**

    -   **刷新配置间隔**。 选择此选项后，输入一个数字，然后从下拉菜单中选择单位。 有效条目最少**30 分钟**到最大**999 天**。

2.  单击 "**添加**" 或 "**删除**" 添加或删除组分配。 使用标准的**Windows "浏览**" 对话框查找用户组。

3.  在 "**提供商管道配置**" 对话框中选择以下复选框之一，启用相关联的功能：

    -   **身份验证**-从下拉列表中选择身份验证类型。

    -   **强制实施访问权限设置**

    -   **日志使用信息**

    -   **许可**-从下拉列表中选择强制方案。

4.  单击 "**完成**" 以添加新的提供商策略。

<a href="" id="view"></a>**视图**  
更改 "**结果**" 窗格的外观和内容。

<a href="" id="new-window-from-here"></a>**从此处新建窗口**  
打开新的管理控制台，其中将选定的节点作为根节点。

<a href="" id="refresh"></a>**刷新**  
刷新服务器的视图。

<a href="" id="export-list"></a>**导出列表**  
创建一个制表符分隔的文本文件，其中包含 "**结果**" 窗格的内容。 此项显示一个标准的 "**文件保存**" 对话框，您可以在其中指定要创建的文本文件的位置。

<a href="" id="help"></a>**帮助**  
显示应用程序虚拟化服务器管理控制台的帮助系统。

## 相关主题


[Server Management Console：“提供程序策略”节点](server-management-console-provider-policies-node.md)

 

 





