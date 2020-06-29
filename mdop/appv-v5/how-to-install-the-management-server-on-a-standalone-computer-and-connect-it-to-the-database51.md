---
title: 如何在独立计算机上安装 Management Server 并将其连接到数据库
description: 如何在独立计算机上安装 Management Server 并将其连接到数据库
author: dansimp
ms.assetid: 3f83c335-d976-4abd-b8f8-d7f5e50b4318
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f2cce96f914f65e7432b5ed9e7c5ecb1a6306990
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798439"
---
# 如何在独立计算机上安装 Management Server 并将其连接到数据库


使用以下过程在独立计算机上安装管理服务器，并将其连接到数据库。

**在独立计算机上安装管理服务器并将其连接到数据库**

1.  将 app-v 5.1 服务器安装文件复制到要在其上安装它的计算机上。 若要启动 app-v 5.1 服务器安装，请右键单击并以管理员身份运行**appv\_server\_setup.exe** 。 单击**安装**。

2.  在 "**入门**" 页面上，查看并接受许可条款，然后单击 "**下一步**"。

3.  在 "**使用 Microsoft 更新" 帮助保持计算机的安全和最新**页面上，若要启用 Microsoft 更新，请选择 "**当我检查更新时使用 Microsoft 更新" （推荐）。** 若要禁用 Microsoft 更新，请选择 "**我不想使用 Microsoft 更新**"。 单击“下一步”****。

4.  在**功能选择**页面上，选中 "**管理服务器**" 复选框，然后单击 "**下一步**"。

5.  在 "**安装位置**" 页面上，接受默认位置，然后单击 "**下一步**"。

6.  在 "**配置现有管理数据库**" 页面上，选择 "**使用远程 SQL Server**"，然后键入运行 Microsoft sql sql 的计算机的计算机名称，例如**SqlServerMachine**。

    **注意**  
    如果 Microsoft SQL Server 部署在同一台服务器上，请选择 "**使用本地 SQL server**"。



~~~
For the SQL Server Instance, select **Use the default instance**. If you are using a custom Microsoft SQL Server instance, you must select **Use a custom instance** and then type the name of the instance.

Specify the **SQL Server Database name** that this management server will use, for example **AppvManagement**.
~~~

7. 在 "**配置管理服务器配置**" 页面上，指定将连接到管理控制台（例如**MyDomain\\MyUser**或**MyDomain\\AdminGroup**）的广告组或帐户。 将启用你指定的帐户或 AD 组，以便通过管理控制台管理服务器。 安装后，你可以使用管理控制台添加其他用户或组

   指定要用于管理服务的**网站名称**。 如果您没有自定义名称，请接受默认值。 对于**端口绑定**，请指定要使用的唯一端口号，例如**12345**。

8. 单击**安装**。

9. 若要确认安装程序已成功完成，请打开 web 浏览器，然后键入以下 URL： http://managementserver:portnumber/Console 。 如果安装成功，你应该会看到 "**管理控制台**" 出现，并且不会显示任何错误消息或警告。

   已**获得有关 app-v 的建议**？ 在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。 **遇到了 app-v 问题？** 使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相关主题


[部署 App-V 5.1](deploying-app-v-51.md)









