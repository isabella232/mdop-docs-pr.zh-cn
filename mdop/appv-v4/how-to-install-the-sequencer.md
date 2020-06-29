---
title: 如何安装 Sequencer
description: 如何安装 Sequencer
author: dansimp
ms.assetid: 2cd16427-a0ba-4870-82d1-3e3c79e1959b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 75a0f987fcc76d1ed92631085a4364ae6e06c9ce
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801348"
---
# 如何安装 Sequencer


Microsoft Application Virtualization （App-v） Sequencer 监视和记录应用程序的安装和设置过程，以便可以将应用程序作为虚拟应用程序运行。 应在仅安装操作系统的计算机上安装 Sequencer。 或者，你可以在运行虚拟环境的计算机（例如 Microsoft 虚拟 PC）上安装 Sequencer。 此方法非常有用，因为它更易于维护干净的顺序环境，可以使用最少的额外配置来重用。

必须在用于对应用程序进行排序的计算机上具有管理权限，并且计算机必须连接到网络。 计算机不得运行任何版本的应用程序虚拟化（app-v）客户端。 使用 Sequencer 创建虚拟应用程序占用大量资源，因此在满足或超过推荐要求的计算机上安装 Sequencer 非常重要。 有关系统要求的详细信息，请参阅[Sequencer 硬件和软件要求](sequencer-hardware-and-software-requirements.md)。。

**安装 Microsoft Application Virtualization Sequencer**

1.  将 Microsoft Application Virtualization Sequencer 安装文件复制到要安装它的计算机上。

2.  若要启动 Microsoft Application Virtualization Sequencer 安装向导，请选择 " **setup.exe**"。 如果在安装之前未检测到**Microsoft Visual c + + SP1 可再发行程序包（x86）** ， **setup.exe**将安装该程序包。

3.  在 "**欢迎**" 页面上，单击 "**下一步**"。

4.  在 "**许可协议**" 页面上，要接受许可协议的条款，请选择 **"我接受许可协议中的条款"**。 单击“下一步”****。

5.  在 "**目标文件夹**" 页面上，要接受默认安装文件夹，请单击 "**下一步**"。 若要指定其他目标文件夹，请单击 "**更改**"，然后指定将用于安装的安装文件夹。 单击“下一步”****。

6.  在 "已**准备好安装程序**" 页面上，若要开始安装，请单击 "**安装**"。

7.  在 " **InstallShield 向导已完成**" 页面上，若要关闭安装向导并打开排序器，请单击 "**完成**"。 若要在不打开 Sequencer 的情况下关闭安装向导，请取消选中 **"启动程序"** ，然后单击 "**完成**"。

## 相关主题


[配置 Application Virtualization Sequencer](configuring-the-application-virtualization-sequencer.md)

 

 





