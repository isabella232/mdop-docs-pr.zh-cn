---
title: 如何使用命令行添加程序包
description: 如何使用命令行添加程序包
author: dansimp
ms.assetid: e75af49e-811a-407a-a7f0-6de8562b9188
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ab418017a075300f308d4ef4c6eceb4f623a05c7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802962"
---
# 如何使用命令行添加程序包


以下过程列出了将虚拟应用程序包添加到特定计算机上的应用程序虚拟化（app-v）客户端所需的步骤。

**为特定用户添加虚拟应用程序包**

-   在要获取程序包的人员的用户帐户下运行以下命令。 该命令为该用户添加和发布程序包。

    `SFTMIME ADD PACKAGE:”name” /MANIFEST <manifest-path>`

**为所有用户添加虚拟应用程序包**

-   在具有管理员权限的帐户下运行以下命令。 将为计算机上的所有用户添加和发布程序包。

    `SFTMIME ADD PACKAGE:”name” /MANIFEST <manifest-path> /GLOBAL`

**使用电子软件分发系统添加程序包**

1.  如果您使用的电子软件分发系统在计算机的**系统**帐户下运行命令，则仅为该帐户发布程序包，除非您使用/GLOBAL 开关。 运行以下命令为计算机上的所有用户添加和发布程序包：

    `SFTMIME ADD PACKAGE:”name” /MANIFEST <manifest-path> /GLOBAL`

2.  

    如果只想为特定用户添加程序包，请运行 "**添加程序包**" 命令，然后通过在每个人员的用户帐户下运行以下 "**发布包**" 命令，为每个用户显式发布程序包：

    `SFTMIME ADD PACKAGE:”name” /MANIFEST <manifest-path>`

    `SFTMIME PUBLISH PACKAGE:”name” /MANIFEST <manifest-path>`

    发布没有全局参数的程序包会授予用户对程序包中的应用程序的访问权限，并将清单中列出的文件类型和快捷方式发布到用户的配置文件中。 所需权限包括 "管理文件类型关联" （**ManageTypes**）和 "发布快捷方式" （**PublishShortcut**）。

## 相关主题


[如何使用命令行删除所有的虚拟应用程序](how-to-delete-all-virtual-applications-by-using-the-command-line.md)

[如何使用命令行删除程序包](how-to-remove-a-package-by-using-the-command-line.md)

 

 





