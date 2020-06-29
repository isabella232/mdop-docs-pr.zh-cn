---
title: DaRT 7.0 发行说明
description: DaRT 7.0 发行说明
author: dansimp
ms.assetid: fad227d0-5c22-4efd-9187-0e5922f7250b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 5114acfe5a46a2c78f722a2bb6394c0dbef55dd4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803233"
---
# DaRT 7.0 发行说明


**若要搜索这些发行说明，请按 CTRL + F。**

安装 Microsoft 诊断和恢复工具集（DaRT）7之前，请仔细阅读这些发行说明。

## 关于 Microsoft 诊断和恢复工具集7。0


这些发行说明包含成功安装 DaRT7 所需的信息，其中包含产品文档中不可用的信息。 如果这些发行说明和其他 DaRT 平台文档之间存在差异，则应将最新更改视为权威。 这些发行说明取代了本产品附带的内容。

## 关于产品文档


Microsoft 诊断和恢复工具集（DaRT）7的文档随产品和连接网站一起分发。

有关如何使用 DaRT7 中的工具的详细帮助，请参阅 "**诊断和恢复工具集**" 菜单上的可用帮助文件。

## 提供反馈


我们对 DaRT7 的反馈感兴趣。 您可以向 dart7feedback@microsoft.com 发送反馈。 此电子邮件地址不是支持频道，但你的反馈将帮助我们为这些工具计划将来的更改，以使其在将来更有用。

## 防范安全漏洞和病毒


为了帮助防范安全漏洞和病毒，我们建议你为正在安装的任何新软件安装最新的可用安全更新。 有关详细信息，请参阅[Microsoft Security](https://go.microsoft.com/fwlink/?LinkId=3482) （ https://go.microsoft.com/fwlink/?LinkId=3482) 。

## DaRT 7.0 的已知问题


### 如果独立系统 Sweeper 处于打开状态，则无法启动 SFC 扫描

如果独立系统 Sweeper 正在运行，则无法启动或运行 SFC 扫描，因为这两个工具之间存在资源冲突。

**解决方法：** 在尝试打开或运行 "SFC 扫描" 工具之前，请关闭独立系统 Sweeper。

### Unicode 字符可能不会显示在文件名中

如果删除文件名中包含 Unicode 字符的文件并尝试使用 "文件还原" 工具还原文件，则不会找到该文件。 仅当你使用的语言不是用于创建恢复映像的 Windows DVD 语言之外的字符时，才会发生这种情况。

**解决方法：** 请确保 DaRT 使用的语言与尝试从中还原文件的操作系统所使用的语言相匹配。

### DaRT 命令行安装可能会悄悄地失败

如果使用安静模式选项运行，则 DaRT 命令行安装将失败，除非使用提升的管理员权限运行。

**解决方法：** 使用提升的管理员权限运行命令行安装。 DaRT 安装支持命令行安装的典型 Windows 安装程序选项。 有关多个可用开关的详细信息，请参阅 Windows Installer 的[命令行选项](https://go.microsoft.com/fwlink/?LinkId=160689)。

### 文件搜索无法将文件夹移动到不同的卷

文件搜索应用程序不支持在卷之间移动文件夹。 如果你尝试在 "文件搜索" 中将文件夹移动到另一个卷，则会返回以下错误： "写入文件* &lt; 文件名 &gt; *时出错。 请确保驱动器有足够的空间，并且目标路径可访问。

**解决方法：** 使用资源管理器将文件夹移动到不同的卷。

### 在重新映射驱动器号的计算机上，某些数据可能不可用

此问题可能会在启用了 BitLocker 的计算机和多重引导计算机上发生。 出现这种情况是因为脱机注册表中的某些信息具有硬编码的驱动器号，并且 DaRT 对相同的卷使用不同的字母。 典型效果包括无法访问注册表编辑器中的某些本地用户帐户。 此外，某些工具可能无法获取依赖于解析文件路径的属性。

**解决方法：** 在 DaRT 启动时使用该选项重新映射驱动器号。 这通常会将典型的驱动器号与预期的相符。

### 修补程序卸载可能不会卸载某些更新

无法卸载某些更新和服务包，因为它们被标记为 "不可安装"，或者因为它们需要从 Windows 7 内部卸载。 在这些情况下，修复程序卸载工具可能会指示这些更新尚未卸载，即使它们尚未安装。

**解决方法：** 从 Windows 7 卸载这些有问题的更新。

### 磁盘擦除：无法删除具有跨区卷、带区卷或镜像卷的磁盘

磁盘擦除不支持删除跨一个或多个卷的跨区、镜像或带区的磁盘。

**解决方法：** 单独选择并删除卷中的每个磁盘。

## 发行说明版权信息


本文档 "按现状" 提供。 本文档中表示的信息和视图（包括 URL 和其他 Internet 网站引用）如有更改，恕不另行通知。 使用本文档的风险由你自己承担。

此处描述的一些示例仅供说明，并且是虚构的。不打算或应该推断出真正的关联或连接。

本文档未向你提供针对任何 Microsoft 产品的任何知识产权的任何法律权限。 本文档是 Microsoft 的机密和专有文档。 它是公开的，并且只能依照保密协议使用。



Microsoft、Active Directory、ActiveSync、MS-DOS、Windows、WindowsServer 和 Windows Vista 是 Microsoft 公司组的商标。

所有其他商标的所有权属于其各自所有者。

## 相关主题


[关于 DaRT 7.0](about-dart-70-new-ia.md)

 

 





