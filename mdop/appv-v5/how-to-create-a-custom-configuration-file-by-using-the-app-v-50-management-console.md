---
title: 如何使用 App-V 5.0 Management Console 创建自定义配置文件
description: 如何使用 App-V 5.0 Management Console 创建自定义配置文件
author: dansimp
ms.assetid: 0d1f6768-be30-4682-8eeb-aa95918b24c3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d54e68caa380025b2ff6f3ea79d30f275b589b30
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798518"
---
# 如何使用 App-V 5.0 Management Console 创建自定义配置文件


你可以使用动态配置为特定用户自定义 app-v 5.0 程序包。 但是，必须首先创建动态用户配置（.xml）文件或动态部署配置文件，然后才能使用这些文件。 文件的创建是一个高级手动操作。 有关动态用户配置文件的一般信息，请参阅[关于 app-v 5.0 动态配置](about-app-v-50-dynamic-configuration.md)。

使用以下过程，使用 App-v 5.0 管理控制台创建动态用户配置文件。

**创建动态用户配置文件**

1.  右键单击要查看的程序包的名称，然后选择 "**编辑 active directory 访问权限**" 以查看分配给给定用户组的配置。 或者，选择该程序包，然后单击 "**编辑**"。

2.  通过使用**具有 Access 的广告实体**的列表，选择要自定义的广告组。 从下拉列表中选择 "**自定义**" （如果尚未选中）。 将显示名为**Edit**的链接。

3.  单击**编辑**。 将显示分配给 AD 组的动态用户配置。

4.  单击 "**高级**"，然后单击 "**导出配置**"。 键入文件名，然后单击 "**保存**"。 现在，你可以编辑文件来为用户配置程序包。

    已**获得有关 app-v 的建议**？ 在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。 **遇到了 app-v 问题？** 使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相关主题


[App-V 5.0 的操作](operations-for-app-v-50.md)

 

 





