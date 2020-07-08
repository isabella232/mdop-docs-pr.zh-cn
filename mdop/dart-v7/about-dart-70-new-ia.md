---
title: 关于 DaRT 7.0
description: 关于 DaRT 7.0
author: dansimp
ms.assetid: 217ffafc-6d73-4b80-88d9-71870460d4ab
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cd647b2f596ce88ce38580f08422ff8f92b35c06
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803335"
---
# 关于 DaRT 7.0


Microsoft 诊断和恢复工具集（DaRT）7帮助你诊断和修复基于 Windows 的桌面。 这包括无法启动的桌面。 DaRT 是一组功能强大的工具，用于扩展 Windows 恢复环境（WinRE）。 通过使用 DaRT，你可以分析问题以确定其原因，例如检查计算机的事件日志或系统注册表。

DaRT 还提供工具来帮助您在确定原因后立即修复问题。 例如，你可以使用 DaRT 中的工具禁用错误的设备驱动程序、删除修补程序、还原已删除的文件和扫描计算机，即使你无法或不应启动已安装的 Windows 操作系统也是如此。

DaRT 可帮助你快速恢复运行32位或64位版本的 Windows 7 的计算机，通常比重新映像计算机所花费的时间更少。

## 关于 DaRT 7 恢复映像


通过 DaRT 中的功能，你可以创建基于 WinRE 的恢复映像，并将其与 DaRT 提供的一组工具结合使用。 DaRT 恢复映像利用 WinRE，可从中访问 "**诊断和恢复工具集**" 窗口。

使用**Dart 恢复映像向导**创建 DaRT 恢复映像。 默认情况下，向导在桌面上创建一个名为 DaRT70 的国际组织标准化（ISO）图像文件，但你可以指定不同的位置和文件名。 该向导还允许你将图像刻录到 CD 或 DVD。 完成向导后，您可以将恢复映像保存到 USB 闪存驱动器，或将其保存为可用于创建远程分区或恢复分区的格式。

当你必须使用 DaRT 启动不会启动的最终用户计算机时，你可以按照有关[如何使用 DaRT 恢复映像恢复本地计算机](how-to-recover-local-computers-using-the-dart-recovery-image-dart-7.md)的说明进行操作。

有关 DaRT 中的工具的详细信息，请参阅[dart 7.0 中的工具概述](overview-of-the-tools-in-dart-70-new-ia.md)。

## <a href="" id="what-s-new-in-dart-7"></a>DaRT 7 中的新增功能


DaRT7 将继续支持以前版本中包含的所有方案，并且除了三个新的部署选项之外，还会添加新的远程连接功能。

### DaRT 7 映像创建

用于创建 DaRT ISO 映像的向导现在称为**DaRT 恢复映像**，它现在支持启用或禁用新的远程连接功能的选项。 远程连接允许帮助台代理从远程位置运行 DaRT 工具。 在以前的版本中，帮助台工程师必须在最终用户计算机上物理显示才能运行 DaRT 工具。

该向导还允许你自定义 "远程连接" 功能的欢迎消息（当最终用户运行远程连接工具时显示消息）。 IT 管理员还可以配置远程连接应使用的端口号。

有关**DaRT 恢复映像向导**或远程连接的详细信息，请参阅[创建 DaRT 7.0 恢复映像](creating-the-dart-70-recovery-image-dart-7.md)。

### DaRT 7 ISO 部署

除了刻录到 CD 或 DVD 外，在部署包含 DaRT 恢复映像的 ISO 时，DaRT7 还将添加三个新选项：

-   USB 闪存驱动器部署

-   远程分区部署

-   恢复分区部署

USB 闪存驱动器部署选项允许公司在没有 CD 或 DVD 驱动器可用的计算机上使用 DaRT。 通过恢复和远程分区选项，最终用户可以轻松访问 DaRT 映像并启用远程连接功能。

有关如何部署 DaRT 恢复映像的详细信息，请参阅[部署 dart 7.0 恢复映像](deploying-the-dart-70-recovery-image-dart-7.md)。

## 相关主题


[DaRT 7.0 入门](getting-started-with-dart-70-new-ia.md)

[DaRT 7.0 发行说明](release-notes-for-dart-70-new-ia.md)

 

 





