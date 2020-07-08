---
title: 如何使用性能计数器管理 App-V Client 缓存
description: 如何使用性能计数器管理 App-V Client 缓存
author: dansimp
ms.assetid: 49d6c3f2-68b8-4c69-befa-7598a8737d05
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 396cceaf9a3bde661200be2771a85596a512732f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801295"
---
# 如何使用性能计数器管理 App-V Client 缓存


你可以使用以下过程通过使用性能监视器以图形方式显示信息来确定应用程序虚拟化（app-v）客户端缓存中的可用空间量。 此信息在客户端计算机上由名为 "App Virt 客户端缓存" 的性能计数器捕获，其中包括以下计数器： "缓存大小（MB）"、"缓存可用空间（MB）" 和 "% 可用空间"。

**确定客户端缓存空间使用率**

1.  以管理员身份打开命令提示符，或单击 "**开始**"、"**运行**"，键入**perfmon.exe**，然后单击 **"确定"**。

2.  根据所使用的 Windows 操作系统，在 MMC 窗口打开后，单击 "性能监视器" 或 "系统监视器" 工具。

3.  若要添加计数器，请右键单击图形区域，然后选择 "**添加计数器**"。

4.  单击下拉列表以显示可用计数器的列表，滚动到 "查找**应用 Virt 客户端缓存**"，然后添加三个计数器。

    **重要提示** App-v 性能计数器在32位 DLL 中实现，因此，若要查看它们，必须使用以下命令启动32位的性能监视器版本： **mmc/32 perfmon**。 必须直接在受监视的计算机上运行此命令，并且不能使用该命令监视运行64位操作系统的远程计算机。

     

## 相关主题


[如何使用命令行管理虚拟应用程序](how-to-manage-virtual-applications-by-using-the-command-line.md)

 

 





