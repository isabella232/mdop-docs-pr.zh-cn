---
title: 如何使用命令行打开已排序的应用程序
description: 如何使用命令行打开已排序的应用程序
author: dansimp
ms.assetid: dc23ee65-8aea-470e-bb3f-a2f2b06cb241
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c99ab6b41947fc255afa9cad5b3ed2e22e672c3e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801208"
---
# 如何使用命令行打开已排序的应用程序


可以使用命令行打开虚拟应用程序包。 您必须以管理员身份运行**cmd**提示符。

使用以下过程使用命令行打开序列化的应用程序包

**使用命令行打开序列化的应用程序**

1.  若要打开命令提示符，请单击 "**开始**"，然后选择 "**运行**"，键入**Cmd**，然后单击 **"确定"**。

2.  在命令提示符处，键入**cd\\**并指定安装 Sequencer 的目录的路径，然后按**Enter。**

3.  在命令提示符处，键入以下命令，将斜体文本替换为值：

    SFTSequencer/OPEN：*"指定要打开的 sprj 文件"*

    按**enter**。

4.  你还可以指定以下可选参数。 在命令提示符处，键入以下命令，将斜体文本替换为值：

    /PACKAGENAME： "*指定程序包名称"*

    /MSI-指定生成关联的 Microsoft Windows Installer。

    /COMPRESS –指定是否将压缩程序包。 默认情况下，不压缩程序包。

    按**enter**。

    **注意** 如果安装程序或 Windows 安装程序包具有图形用户界面，则在指定命令行参数后将显示该界面。

     

## 相关主题


[如何使用命令行管理虚拟应用程序](how-to-manage-virtual-applications-using-the-command-line.md)

 

 





