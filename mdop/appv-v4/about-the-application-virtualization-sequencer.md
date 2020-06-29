---
title: 关于 Application Virtualization Sequencer
description: 关于 Application Virtualization Sequencer
author: dansimp
ms.assetid: bee193ca-58bd-40c9-b41a-310435633895
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 83709bcceabe3312fba34512b47d28a24b4dc52c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802440"
---
# 关于 Application Virtualization Sequencer


Microsoft Application Virtualization （App-v） Sequencer 监视和记录应用程序的所有安装和设置进程，并创建以下文件： **.ico**、 **OSD**、 **SFT**和**SPRJ**。 这些文件包含有关应用程序的所有必要信息，以便应用程序可以在目标计算机上的虚拟环境中运行。 你可以使用 Microsoft Application Virtualization （App-v） Sequencer 创建虚拟应用程序。 对应用程序进行排序后，可以将其流式传输到目标计算机，或者目标计算机可以通过下载虚拟应用程序包的内容并在本地运行应用程序来运行虚拟应用程序。

**重要提示** 若要运行虚拟应用程序包，目标计算机必须运行应用的相应版本的 App-v 客户端。

 

虚拟应用程序包在目标计算机上运行，但不与目标计算机上的基础操作系统交互，因为每个应用程序都在虚拟环境中运行，并且与在目标计算机上安装或运行的其他应用程序隔离。 这种隔离可减少应用程序冲突，并有助于减少所需的应用程序预部署测试量。

## Sequencer 术语


<a href="" id="application-virtualization-drive"></a>Application Virtualization 驱动器  
应用程序虚拟化驱动器是运行顺序应用程序的目标计算机上的默认驱动器（Q:\）。

<a href="" id="ico-file"></a>.ICO 文件  
客户端桌面上的图标文件，用于启动序列化的应用程序。

<a href="" id="installation-directory"></a>安装目录  
在安装期间，sequencer 用于放置安装文件的目录。

<a href="" id="open-software-descriptor--osd--file"></a>开放软件描述符（OSD）文件  
基于 XML 的文件，指示 App-v 客户端如何从 App-v 流式处理服务器检索序列化的应用程序，以及如何在虚拟环境中运行序列化的应用程序。

<a href="" id="package-root-directory"></a>程序包根目录  
排序计算机上安装序列化应用程序包的文件的目录。 此目录还存在于将对序列化的应用程序进行流式处理的计算机上。

<a href="" id="sequenced-application"></a>顺序应用程序  
由 sequencer 监视的应用程序被分解为主要和辅助功能块，流到运行应用程序 V 客户端 t 的目标计算机，并运行虚拟环境。

<a href="" id="sequenced-application-package"></a>顺序应用程序包  
构成虚拟应用程序并允许虚拟应用程序运行的文件。 这些文件是在排序后创建的， **.osd**具体包括 .osd **、** sprj、 **.sprj**和 **.ico**文件。

<a href="" id="sequencing"></a>引出  
使用 App-v 排序器创建应用程序包的过程。 在此过程中，将监视应用程序、配置其快捷方式，并创建序列化的应用程序包。

<a href="" id="sequencing-computer"></a>计算机排序  
用于对应用程序进行排序的计算机。

<a href="" id="virtual-application"></a>虚拟应用程序  
由 Sequencer 打包以在自包含虚拟环境中运行的应用程序。 虚拟环境包含在客户端上运行应用程序所需的信息，而无需本地安装应用程序。

<a href="" id="primary-feature-block"></a>主要功能块  
在目标计算机上运行应用程序所需的虚拟应用程序包中的最小内容。 主功能块中的内容在排序的应用阶段中标识，通常包含最常用的应用程序功能的内容。

## <a href="" id="sequencing-applications-"></a>排序应用程序


有两种方法可以在你的环境中创建和修改虚拟应用程序包。 第一种方法是使用**排序**向导。 **排序**向导允许你创建新的或修改现有的虚拟应用程序包。 有关使用**顺序**向导的详细信息，请参阅[如何对新应用程序进行排序](how-to-sequence-a-new-application.md)。 第二种方法是使用命令行。 命令行允许你使用命令提示符创建新的或修改现有的虚拟应用程序包。 有关使用命令行的详细信息，请参阅[如何使用命令行管理虚拟应用程序](how-to-manage-virtual-applications-using-the-command-line.md)。

**排序**向导提供以下用于创建虚拟应用程序包的函数：

1.  **程序包配置**：**排序**向导提示提供完成开放软件描述符（OSD）文件所需的程序包配置信息，该文件是启动顺序应用程序包所需的文件。

2.  **应用程序安装**：**排序**向导收集有关应用程序的安装和启动配置的信息。 它监视和记录与应用程序关联的安装和启动信息，以创建虚拟应用程序包所需的文件。

3.  **应用程序启动**：**排序**向导收集用于编译和排序的代码块的信息，以便在目标计算机上执行序列化应用程序包初始启动所需的代码块。 代码块的编译称为主功能块。

## 应用程序虚拟化 Sequencer 安全注意事项


App-v Sequencer 运行使用本地系统帐户在排序时间内检测到的所有服务，并且不会在服务控制请求上强制执行安全描述符。 如果该服务是使用其他用户帐户安装的，或者安全描述符打算授予不同的用户组特定的服务权限，请仔细考虑是否应虚拟化该服务。 在某些情况下，应在本地安装该服务，以确保保留预期的服务安全。

**重要提示** 你应该始终将虚拟应用程序包保存到安全位置。

 

## 相关主题


[Application Virtualization Sequencer 概述](application-virtualization-sequencer-overview.md)

 

 





