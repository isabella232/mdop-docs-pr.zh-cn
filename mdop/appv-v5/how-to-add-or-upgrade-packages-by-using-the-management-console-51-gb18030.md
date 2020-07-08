---
title: 如何使用管理控制台添加或升级程序包
description: 如何使用管理控制台添加或升级程序包
author: dansimp
ms.assetid: 62417b63-06b2-437c-8584-523e1dea97c3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4ac458a5e33b83e19d72fee39cf837aa6bd57bc5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798557"
---
# 如何使用管理控制台添加或升级程序包


你可以通过以下过程将程序包添加到 app-v 5.1 管理控制台或将其升级到该管理控制台。 若要升级管理控制台中已存在的程序包，请使用以下步骤，并使用相同的程序包**名称**导入升级后的程序包。

**将程序包添加到管理控制台**

1.  在管理控制台显示的导航窗格中单击 "**程序包**" 选项卡。

    该控制台将显示已添加到服务器的程序包列表以及每个程序包的状态信息。 选择程序包后，有关程序包的详细信息将显示在 "**程序包**" 窗格中。

    单击 "**取消分组**" 下拉列表框并指定程序包在控制台中的显示方式。 也可以单击关联的列标题对程序包进行排序。

2.  若要指定要添加的程序包，请单击 "**添加或升级程序包**"。

3.  键入要添加的程序包的完整路径。 使用 UNC 或 HTTP 路径格式，例如**\\\\servername\\sharename\\foldername\\packagename.appv**或，然后 **http://server.1234/file.appv** 单击 "**添加**"。

    **重要提示** 必须选择一个具有**appv**文件扩展名的程序包。

     

4.  页面将显示 "**添加 &lt; Packagename &gt; **" 状态消息。 单击 "**导入状态**" 以检查已导入的程序包的状态。

    单击 **"确定"** 添加程序包并关闭 "**添加程序包**" 页面。 如果在导入过程中出现错误，请单击 "**程序包导入**" 页面上的 "**详细**信息" 以了解详细信息。 新添加的程序包现在在 "**程序包**" 窗格中可用。

5.  单击 "**关闭**" 以关闭 "**添加或升级程序包**" 页面。

    已**获得有关 app-v 的建议**？ 在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。 **遇到了 app-v 问题？** 使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相关主题


[App-V 5.1 的操作](operations-for-app-v-51.md)

 

 





