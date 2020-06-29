---
title: 关于 DaRT 8.0
description: 关于 DaRT 8.0
author: dansimp
ms.assetid: ce91efd6-7d78-44cb-bb8f-1f43f768ebaa
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e70816425dc4775b11596b91d7b5c0045830c6ad
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802937"
---
# 关于 DaRT 8.0


Microsoft 诊断和恢复工具集（DaRT）8.0 帮助你诊断和修复基于 Windows 的计算机。 这包括无法启动的计算机。 DaRT 8.0 是一组功能强大的工具，用于扩展 Windows 恢复环境（WinRE）。 通过使用 DaRT，你可以分析问题以确定其原因，例如检查计算机的事件日志或系统注册表。 DaRT 支持恢复包含分区（例如，主分区和逻辑驱动器）的基本硬盘，并支持卷恢复。

**注意** DaRT 不支持动态磁盘的恢复。

 

DaRT 还提供工具来帮助您在确定原因后立即修复问题。 例如，你可以使用 DaRT 中的工具禁用错误的设备驱动程序、删除修补程序、还原已删除的文件和扫描计算机，即使你无法或不应启动已安装的 Windows 操作系统也是如此。

DaRT 可帮助你快速恢复运行32位或64位版本的 Windows 8 的计算机，通常比重新映像计算机所花费的时间更少。

DaRT 中的功能允许你创建恢复映像。 恢复映像将启动 Windows 恢复环境（Windows RE），从该环境中，你可以启动**诊断和恢复工具集**窗口并访问 DaRT 工具。

使用**Dart 恢复映像向导**创建 DaRT 恢复映像。 默认情况下，向导创建国际标准化组织（ISO）图像文件和 Windows 映像格式（WIM）文件，并允许你将映像刻录到 CD、DVD 或 USB。 你可以在最终用户的计算机本地部署映像，也可以从本地硬盘上的远程网络分区或恢复分区部署该映像。

## <a href="" id="what-s-new-in-dart-8-0"></a>DaRT 8.0 中的新增功能


DaRT 8.0 可帮助你快速恢复运行32位或64位版本的 Windows 8 的计算机，通常比重新映像计算机所用的时间更少。 DaRT 8.0 具有以下新增功能。

### 使用 Windows 8 或 Windows Server 2012 创建 DaRT 映像

DaRT 8.0 使你能够使用 Windows®8或 Windows Server®2012创建 DaRT 映像。 对于早于 Windows 8 和 Windows Server 2012 的 Windows 版本，客户应继续使用早期版本的 DaRT。

### 从一台计算机生成32和64位图像

DaRT 8.0 使你可以从运行 DaRT 的单个计算机生成32位和64位图像，无论该计算机是32还是64位计算机。 在 DaRT7 中，创建的映像与运行 DaRT 的计算机必须具有相同的、比上的相同。

### 创建一个支持具有 BIOS 或 UEFI 接口的计算机的映像

DaRT 8.0 对统一可扩展固件接口（UEFI）和 BIOS 接口的支持使你能够仅创建一个可与具有任何接口的计算机配合使用的映像。

### 使用 GUID 分区表（GPT）进行分区

DaRT 8.0 工具现在支持 Windows 8 GPT 磁盘，这提供了一种比较旧的主引导记录（MBR）分区方案更灵活的磁盘分区。 DaRT 8.0 工具继续支持 MBR 分区。

### 在本地硬盘上安装 Windows 8 和 Windows Server 2012

只有当 Windows 8 和 Windows Server 2012 安装在本地硬盘上时，才能使用 DaRT 8.0 工具。 目前，不支持 Windows To Go。

### <a href="" id="-------------dart-8-0-release-notes"></a> DaRT 8.0 发行说明

有关详细信息，以及未在文档中执行的最新消息，请参阅[DaRT 8.0 的发行说明](release-notes-for-dart-80--dart-8.md)。

## 如何获取 DaRT 8。0


此技术是 Microsoft 桌面优化包（MDOP）的一部分。 MDOP 是 Microsoft 软件保障的一部分。 有关 Microsoft 软件保证和获取 MDOP 的详细信息，请参阅[如何获取 mdop](https://go.microsoft.com/fwlink/?LinkId=322049) （ https://go.microsoft.com/fwlink/?LinkId=322049) 。

## 相关主题


[DaRT 8.0 入门](getting-started-with-dart-80-dart-8.md)

[DaRT 8.0 发行说明](release-notes-for-dart-80--dart-8.md)

 

 





