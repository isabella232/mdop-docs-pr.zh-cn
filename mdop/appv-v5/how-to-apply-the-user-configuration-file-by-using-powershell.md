---
title: 如何使用 PowerShell 应用用户配置文件
description: 如何使用 PowerShell 应用用户配置文件
author: dansimp
ms.assetid: f7d7c595-4fdd-4096-b53d-9eead111c339
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 95ae5840f5eee04a29431716a956ddec7d0487aa
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798545"
---
# 如何使用 PowerShell 应用用户配置文件


当程序包发布到特定用户并确定该程序包的运行方式时，将应用动态用户配置文件。

使用以下过程指定特定于用户的配置文件。 下面的过程基于示例：

**c:\\Packages\\Contoso\\MyApp.appv**

**应用用户配置文件**

1.  若要使用 PowerShell 控制台将程序包添加到计算机，请键入以下命令：

    **AppVClientPackage c:\\Packages\\Contoso\\MyApp.appv**。

2.  使用以下命令将程序包发布到用户并指定已更新的动态用户配置文件：

    **发布-AppVClientPackage $pkg-DynamicUserConfigurationPath c:\\Packages\\Contoso\\config.xml**

    已**获得有关 app-v 的建议**？ 在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。 **遇到了 app-v 问题？** 使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相关主题


[App-V 5.0 的操作](operations-for-app-v-50.md)

 

 





