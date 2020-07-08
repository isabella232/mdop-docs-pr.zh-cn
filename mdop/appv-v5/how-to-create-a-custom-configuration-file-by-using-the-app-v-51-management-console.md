---
title: 如何使用 App-V 5.1 Management Console 创建自定义配置文件
description: 如何使用 App-V 5.1 Management Console 创建自定义配置文件
author: dansimp
ms.assetid: f5ab426a-f49a-47b3-93f3-b9d60aada8f4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 282207b5424442950e88c40a372194e9def768cb
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798517"
---
# 如何使用 App-V 5.1 Management Console 创建自定义配置文件


你可以使用动态配置为特定用户自定义 app-v 5.1 程序包。 但是，必须首先创建动态用户配置（.xml）文件或动态部署配置文件，然后才能使用这些文件。 文件的创建是一个高级手动操作。 有关动态用户配置文件的一般信息，请参阅[关于 app-v 5.1 动态配置](about-app-v-51-dynamic-configuration.md)。

使用以下过程，使用 App-v 5.1 管理控制台创建动态用户配置文件。

**创建动态用户配置文件**

1.  右键单击要查看的程序包的名称，然后选择 "**编辑 active directory 访问权限**" 以查看分配给给定用户组的配置。 或者，选择该程序包，然后单击 "**编辑**"。

2.  通过使用**具有 Access 的广告实体**的列表，选择要自定义的广告组。 从下拉列表中选择 "**自定义**" （如果尚未选中）。 将显示名为**Edit**的链接。

3.  单击**编辑**。 将显示分配给 AD 组的动态用户配置。

4.  单击 "**高级**"，然后单击 "**导出配置**"。 键入文件名，然后单击 "**保存**"。 现在，你可以编辑文件来为用户配置程序包。

    **注意**  
    若要在 Windows Server 上运行时导出配置，必须禁用 "IE 增强的安全配置"。 如果启用了此功能，并将其设置为 "阻止下载"，则不能从 App-v 服务器下载任何内容。



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## 相关主题


[App-V 5.1 的操作](operations-for-app-v-51.md)









