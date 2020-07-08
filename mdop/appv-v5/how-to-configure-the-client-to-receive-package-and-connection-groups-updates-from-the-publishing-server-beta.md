---
title: 如何将 Client 配置为从发布服务器接收程序包和连接组更新
description: 如何将 Client 配置为从发布服务器接收程序包和连接组更新
author: dansimp
ms.assetid: f5dfd96d-4b63-468c-8d93-9dfdf47c28fd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7e9df1f8b324430449d8d1dd3624d9f1157968a5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798533"
---
# 如何将 Client 配置为从发布服务器接收程序包和连接组更新


使用 App-v 5.0 发布服务器部署程序包和连接组非常有用，因为它提供了单点管理和高可伸缩性。

使用以下步骤将 App-v 5.0 客户端配置为接收来自发布服务器的更新。

**注意** 对于以下过程，管理服务器安装在名为**MyMgmtSrv**的计算机上，并且发布服务器安装在名为**MyPubSrv**的计算机上。

 

**将 App-v 5.0 客户端配置为接收来自发布服务器的更新**

1.  部署 app-v 5.0 管理和发布服务器，并添加所需的程序包和连接组。 有关添加程序包和连接组的详细信息，请参阅[如何使用管理控制台添加或升级程序包](how-to-add-or-upgrade-packages-by-using-the-management-console-beta-gb18030.md)，以及[如何创建连接组](how-to-create-a-connection-group.md)。

2.  若要打开管理控制台，请单击以下链接，打开浏览器并键入以下内容： http://MyMgmtSrv/AppvManagement/Console.html 在 web 浏览器中，然后导入、发布和 entitle 特定用户组所需的所有程序包和连接组。

3.  在运行 App-v 5.0 客户端的计算机上，打开提升的 PowerShell 命令提示符，运行以下命令：

    **Add-AppvPublishingServer-Name ABC-URL http://MyPubSrv/AppvPublishing**

    此命令将配置指定的发布服务器。 您应看到类似于以下内容的输出：

    Id：1

    SetByGroupPolicy： False

    名称： ABC

    URL： http://MyPubSrv/AppvPublishing

    GlobalRefreshEnabled： False

    GlobalRefreshOnLogon： False

    GlobalRefreshInterval：0

    GlobalRefreshIntervalUnit： Day

    UserRefreshEnabled： True

    UserRefreshOnLogon： True

    UserRefreshInterval：0

    UserRefreshIntervalUnit： Day

    返回的 Id-在本例中为1

4.  在运行 App-v 5.0 客户端的计算机上，打开一个 PowerShell 命令提示符，然后键入以下命令：

    **Sync-AppvPublishingServer-ServerId 1**

    该命令将根据管理服务器上配置的程序包和连接组的权利，为需要为此特定客户添加或删除的程序包和连接组查询发布服务器。

    已**获得有关 app-v 的建议**？ 在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。 **遇到了 app-v 问题？** 使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相关主题


[App-V 5.0 的操作](operations-for-app-v-50.md)

 

 





