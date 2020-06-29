---
title: 如何创建连接组
description: 如何创建连接组
author: dansimp
ms.assetid: 9d272052-2d28-4e41-989c-89610482a0ca
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 816fc3b37be056ed54a88c394ef64fa1edaf47ee
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798521"
---
# 如何创建连接组


使用以下步骤创建使用 App-v 管理控制台的连接组。 若要使用 PowerShell 创建连接组，请参阅[如何使用 Powershell 管理独立计算机上的连接组](how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell.md)。

将程序包放置在连接组中时，它们的程序包根路径将合并。 如果删除程序包，则仅剩下剩余的程序包保留合并的根。

**创建连接组**

1.  在 App-v 5.0 管理控制台中，选择 "**程序包**"。

2.  选择 "**连接组**" 以显示 "连接组" 库。

3.  选择 "**添加连接组**" 以创建新的连接组。

4.  在 "**新建连接组**" 窗格中，键入组的说明。

5.  在 "**已连接的程序包**" 窗格中单击 "**编辑**"，将新应用程序添加到连接组。

6.  在 "**打包整个库**" 窗格中，选择要添加的应用程序，然后单击箭头以添加应用程序。

    若要删除应用程序，请在 "**包**的" 窗格中选择要删除的应用程序，然后单击箭头。

    若要重新调整连接组中的应用程序，请使用 "**程序包的**" 窗格中的箭头。

    **重要提示** 默认情况下，与特定应用程序相关联的 Active Directory 域服务访问配置不会添加到连接组。 若要转移 Active Directory 访问配置，请选择 "**添加对组访问的程序包访问**"，它位于 "**程序包**" 窗格中。

     

7.  添加所有应用程序并配置 Active Directory 访问后，单击 "**应用**"。

    已**获得有关 app-v 的建议**？ 在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。 **遇到了 app-v 问题？** 使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相关主题


[App-V 5.0 的操作](operations-for-app-v-50.md)

[管理连接组](managing-connection-groups.md)

 

 





