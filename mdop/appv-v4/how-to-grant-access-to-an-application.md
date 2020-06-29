---
title: 如何授予对应用程序的访问权限
description: 如何授予对应用程序的访问权限
author: dansimp
ms.assetid: e54d9e84-21f5-488f-b040-25f374d9289f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9cd3dfe4661f09bb7e7d3514a397955cb892be81
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801415"
---
# 如何授予对应用程序的访问权限


作为管理员，你可以使用应用程序虚拟化服务器管理控制台确定哪些用户可以访问哪些应用程序。 你可以在导入 Sequencer 项目（SPRJ）或打开软件描述符（OSD）文件时或使用应用程序的 "**属性**" 对话框的任何时候执行此操作。 对于这两种方法，请使用 "**访问权限**" 选项添加用户。

**向应用程序授予访问权限**

1.  对于现有应用程序，请单击左窗格中的 "**应用程序**" 节点。 右键单击右窗格中的应用程序，然后选择 "**属性**"。

2.  选择 "**访问权限**" 选项卡。

3.  若要添加用户组，请单击 "**添加**"。

4.  在 "**添加/编辑用户组**" 对话框中，导航到 "用户" 组。 您也可以通过在相应字段中键入信息来输入域和组。

5.  单击“确定”****。 您可以添加具有相同页面的其他组。

6.  当向导再次出现时，单击 **"确定"**。

    **注意** 在尝试授予对应用程序的访问权限之前，必须在 Active Directory 域服务中设置组。

     

## 相关主题


[如何拒绝对应用程序的访问](how-to-deny-access-to-an-application.md)

[如何在 Server Management Console 中管理应用程序组](how-to-manage-application-groups-in-the-server-management-console.md)

[如何在 Server Management Console 中管理应用程序许可证](how-to-manage-application-licenses-in-the-server-management-console.md)

[如何手动添加应用程序](how-to-manually-add-an-application.md)

 

 





