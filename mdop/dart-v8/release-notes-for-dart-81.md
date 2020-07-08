---
title: DaRT 8.1 发行说明
description: DaRT 8.1 发行说明
author: dansimp
ms.assetid: 44303107-60f4-485c-848a-7e0529f142d4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0d0ba817ddd5bbdefcf7fed833f4c47e7b9d9ce0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803633"
---
# DaRT 8.1 发行说明


**若要搜索这些发行说明，请按 CTRL + F。**

在安装 Microsoft 诊断和恢复工具集（DaRT）8.1 之前，请仔细阅读这些发行说明。

这些发行说明包含成功安装诊断和恢复工具集8.1 所需的信息。 发行说明还包含产品文档中不可用的信息。 如果这些发行说明和其他 DaRT 文档之间存在差异，则应将最新更改视为权威。 这些发行说明取代了本产品附带的内容。

## DaRT 8.1 的已知问题


### Disk 指挥无法在 Windows 8.1 的物理分区中修复损坏的主启动记录

在 Windows 8.1 中，"还原主启动记录（MBR）或磁盘中 GUID 分区表（GPT）的头" 选项无法修复物理分区中损坏的主启动记录，因此无法启动客户端计算机。

**解决方法：** 启动 "**启动修复**"，单击 "**疑难解答**"，单击 "**高级选项**"，然后单击 "**开始修复**"。

### 针对同一个驱动器的多个磁盘擦除实例会导致除最后一个实例之外的所有实例报告故障

如果你启动磁盘擦除的多个实例，然后尝试使用两个单独的磁盘擦除实例来擦除相同的驱动器，则除最后一个磁盘之外的所有实例都将报告无法擦除驱动器。

**解决方法：** 尚.

### 磁盘擦除可能无法清除具有闪存的固态驱动器上的所有数据

如果使用 "磁盘擦除" 清除具有闪存的固态驱动器（SSD）上的数据，则所有数据都可能不会被清除。 出现此问题的原因是 SSD 固件在执行磁盘擦除时控制写入的物理位置。

**解决方法：** 尚.

### 运行 Locksmith 向导或注册表编辑器时系统还原失败

如果您运行的是 Locksmith 向导、注册表编辑器和可能的其他工具，系统还原将失败。

**解决方法：** 关闭并重新启动 DaRT，然后启动 "系统还原"。

### 启动和关闭 Locksmith 向导或计算机管理后，系统文件检查器（SFC）扫描无法运行

如果在 "计算机管理" 中启动然后关闭 Locksmith 向导或工具，系统文件检查器将无法运行。

**解决方法：** 关闭并重新启动 DaRT，然后启动系统文件检查器。

### <a href="" id="-------------dart-installer-does-not-fail-when-the-windows-assessment-and-deployment-kit-is-not-installed"></a> 当未安装 Windows 评估和部署工具包时，DaRT 安装程序不会失败

如果你通过使用命令行运行 Windows Installer （.msi），并且尚未安装 Windows 评估和部署工具包（WindowsADK）来安装 DaRT 8.1，则 DaRT 安装应该会失败。 目前，DaRT 8.1 安装程序安装了除 DaRT 恢复映像之外的所有组件。

**解决方法：** 尚.

### Windows Defender 无法在 Locksmith 向导、注册表编辑器、崩溃分析程序和计算机管理启动后启动

如果已启动 Locksmith 向导、注册表编辑器、崩溃分析程序和计算机管理，Windows Defender 不会启动。

**解决方法：** 关闭并重新启动 DaRT，然后启动 Windows Defender。

### Windows Defender 启动速度可能很慢

Windows Defender 有时需要几分钟才能启动。 进度栏指示当前加载状态。

**解决方法：** 尚.

## 相关主题


[关于 DaRT 8.1](about-dart-81.md)

 

 





