---
title: “安装文件”页
description: “安装文件”页
author: dansimp
ms.assetid: b0aad26f-b143-4f09-87a1-9f016a23cb62
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 08a2e7318271503f072298ca137a1e65e16c0178
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798952"
---
# “安装文件”页


使用 "**安装文件**" 页面指定用于创建在此向导的 "**选择程序包**" 页面上指定的虚拟应用程序包的安装文件。 如果你创建了一个包含多个应用程序的虚拟应用程序包，则应将所有所需的安装文件复制到运行 Microsoft Application Virtualization Sequencer 的计算机上的单个文件夹。

此页面包含以下元素：

<a href="" id="original-installation-files"></a>**原始安装文件**  
单击 "**浏览**" 以指定最初用于创建虚拟应用程序包的安装文件。 你指定的父目录应保存到运行 Sequencer 的计算机，并且必须包含所有必需的安装文件或包含安装文件的子文件夹。 安装文件可以包含在父文件夹中，也可以包含在指定父文件夹的任何子文件夹中。

<a href="" id="files-installed-on-local-system"></a>**本地系统上安装的文件**  
单击 "**浏览**" 以指定运行 Sequencer 的计算机上本地安装的安装文件。 仅当已将应用程序安装文件安装到应用程序的默认位置时，才能选择此选项。

**注意** 你提供的默认安装位置取决于以下条件：

 

-   最初创建程序包时指定的程序包根目录。

-   最初创建程序包时在 Windows Installer 中指定的安装位置。

-   默认应用程序安装路径。

例如，如果指定的程序包根是**Q:\\Office12** ，并且在安装期间，默认安装位置从**c:\\program files Files\\Office12**更改为**Q:\\Office12**，则冻结期间指定的路径必须是**c:\\program files Files\\Office 12**。

如果指定的程序包根是**Q:\\Microsoft** ，并且在安装期间，默认安装位置从**c:\\program files Files\\Office12**更改为**Q:\\Microsoft\\Office12**，则冻结期间指定的路径必须是**c:\\program files 文件**。

使用程序包加速器创建程序包时，程序包中的每个文件（例如**Q:\\Office12\\file.txt**在本地计算机上）通过将程序包根**Q:\\Office12**替换为创建程序包加速器时指定的默认位置，例如**c:\\program files Files\\Office12**。 在前面的示例中，该文件应位于**c:\\program files Files\\Office12\\file.txt**中。

## 相关主题


[“创建包加速器”向导 (AppV 4.6 SP1)](create-package-accelerator-wizard--appv-46-sp1-.md)

 

 





