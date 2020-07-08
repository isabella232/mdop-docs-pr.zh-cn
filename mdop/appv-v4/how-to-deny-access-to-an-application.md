---
title: 如何拒绝对应用程序的访问
description: 如何拒绝对应用程序的访问
author: dansimp
ms.assetid: 14f5e201-7265-462c-b738-57938dc3fc30
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 56a89669ea8c6323023b585d6d58620cd203fc00
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801448"
---
# 如何拒绝对应用程序的访问


用户必须位于应用程序的**访问权限**列表中才能加载和使用该应用程序。 尽管应用程序虚拟化服务器管理控制台不支持显式拒绝用户组对应用程序的访问，但你可以从应用程序的属性中删除用户组来实现此目的。

**拒绝访问应用程序**

1.  对于现有应用程序，请单击左窗格中的 "**应用程序**" 节点。

2.  右键单击右窗格中的应用程序，然后选择 "**属性**"。 然后选择 "**访问权限**" 选项卡。

3.  若要删除用户组的访问权限，请突出显示 "用户" 组，然后单击 "**删除**"。

4.  单击“确定”****。

    **注意** 若要控制对应用程序的访问，您还可以限制应用程序许可证。 在 Active Directory 域服务中设置适当的用户组可提供授予和拒绝特定用户集访问权限的最简单方式。

     

## 相关主题


[如何授予对应用程序的访问权限](how-to-grant-access-to-an-application.md)

[如何在 Server Management Console 中管理应用程序许可证](how-to-manage-application-licenses-in-the-server-management-console.md)

[如何在 Server Management Console 中管理应用程序](how-to-manage-applications-in-the-server-management-console.md)

 

 





