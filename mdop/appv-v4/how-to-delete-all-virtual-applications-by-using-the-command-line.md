---
title: 如何使用命令行删除所有的虚拟应用程序
description: 如何使用命令行删除所有的虚拟应用程序
author: dansimp
ms.assetid: bfe13b5c-825a-4eb1-a979-6c4b8d8b2a9c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 55c809df31fa5c19f2f1a56c143d492b092156c0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801456"
---
# 如何使用命令行删除所有的虚拟应用程序


你可以使用以下过程从特定计算机中删除所有虚拟应用程序。

**注意** 从程序包中删除所有应用程序时，应用程序虚拟化（app-v）客户端也会删除该程序包。

 

**删除所有应用程序**

-   运行以下命令以删除运行该命令的用户帐户的所有应用程序。 如果使用可选的/GLOBAL 开关运行命令，使用具有管理权限的帐户，将删除所有用户的所有应用程序。

    `SFTMIME DELETE OBJ:APP [/GLOBAL]`

    **注意** 从程序包中删除所有应用程序时，应用程序虚拟化（app-v）客户端也会删除该程序包。

     

## 相关主题


[如何使用命令行添加程序包](how-to-add-a-package-by-using-the-command-line.md)

[如何使用命令行删除程序包](how-to-remove-a-package-by-using-the-command-line.md)

 

 





