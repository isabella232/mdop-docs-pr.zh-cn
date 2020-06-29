---
title: 如何使用命令行删除程序包
description: 如何使用命令行删除程序包
author: dansimp
ms.assetid: 47697ec7-20e5-4258-8865-a0a710d41d5a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b282830802f34bfb0670ddfdb8e2852d3559e3f7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801171"
---
# 如何使用命令行删除程序包


你可以使用以下命令行过程从特定计算机上的应用程序虚拟化（app-v）客户端中删除虚拟应用程序包。

**删除所有用户的虚拟应用程序包**

-   如果以前通过使用/GLOBAL 开关为所有用户添加了程序包，请使用以下命令删除程序包以及全局文件类型和快捷方式。 需要管理员权限。 在此情况下不需要/GLOBAL 开关，因为该命令始终执行程序包全局删除。

    `SFTMIME DELETE PACKAGE:”name”`

**删除之前为单个用户添加的程序包**

1.  如果以前为单个用户添加了该程序包，则有多个选项。

    在发布程序包的每个人的用户帐户下运行以下命令。 这将在用户漫游到另一台计算机时拒绝用户访问应用程序。 它将从配置文件中删除特定用户的设置、快捷方式和文件类型，并在用户的上下文中停止后台加载。

    `SFTMIME UNPUBLISH PACKAGE:”name”`

2.  或者，在发布程序包的每个人的用户帐户下运行以下命令。

    `SFTMIME UNPUBLISH PACKAGE:”name”`

    然后对程序包运行此命令。

    `SFTMIME DELETE PACKAGE:”name”`

    这将完全删除程序包，并从其配置文件中删除所有用户设置、快捷方式和文件类型。 如果随后重新添加程序包，用户将必须再次指定其设置。 若要运行此命令，只需 "删除应用程序" （**DeleteApp**）权限。

3.  第三种方法是，无需使用**取消发布程序包**命令即可运行 "**删除包**" 命令。 在这种情况下，每个用户的文件类型和快捷方式均为隐藏而不是删除，并且用户设置已保留。 这意味着，如果随后为用户重新添加程序包，则会还原文件类型和快捷方式，并重新应用用户设置。

## 相关主题


[如何使用命令行添加程序包](how-to-add-a-package-by-using-the-command-line.md)

[如何使用命令行删除所有的虚拟应用程序](how-to-delete-all-virtual-applications-by-using-the-command-line.md)

 

 





