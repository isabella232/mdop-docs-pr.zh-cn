---
title: App-V 4.6 发行说明
description: App-V 4.6 发行说明
author: dansimp
ms.assetid: a3eba129-edac-48bf-a933-3bf43a9873e5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9eee3c309a927a72155dec707d8dd95f43e90fb9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803154"
---
# App-V 4.6 发行说明


若要搜索这些发行说明，请按 CTRL + F。

**重要提示** 在安装 Microsoft Application Virtualization （app-v）管理系统之前，请仔细阅读这些发行说明。 这些发行说明包含成功安装应用程序虚拟化（app-v）4.6 所需的信息。 本文档包含产品文档中不可用的信息。 如果这些发行说明和其他 App-v 文档之间存在差异，则应将最新更改视为权威。

 

## 防范安全漏洞和病毒


若要帮助防范安全漏洞和病毒，请务必为正在安装的任何新软件安装最新的可用安全更新。 有关详细信息，请参阅[Microsoft 安全性网站](https://go.microsoft.com/fwlink/?LinkId=3482)（ https://go.microsoft.com/fwlink/?LinkId=3482) 。

## 应用程序虚拟化4.6 的已知问题


本部分提供有关 Microsoft Application Virtualization （app-v）4.6 问题的最新信息。 这些问题不会显示在产品文档中，在某些情况下，可能会矛盾现有产品文档。 只要有可能，这些问题将在以后的版本中解决。

### 运行由 app-v 4.5 Sequencer 生成的 Windows Installer 文件时出现加载/安装错误

在 app-v 4.6 客户端上运行 app-v 4.5 排序器时，运行由 app-v 4.5 排序器生成的 Windows Installer 文件会产生加载/安装错误。 你将看到以下消息： "此程序包需要 Microsoft Application Virtualization Client 4.5 或更高版本"。 请使用以下解决方法。

使用 app-v 4.5 SP1 Sequencer 或 App-v 4.6 排序器 WORKAROUNDOpen 旧程序包，并为程序包生成新的 .msi 文件。

**注意** 或者，在命令提示符处，App-v Sequencer 可通过使用 */OPEN*和 */MSI*参数（例如，）生成新的 .msi 文件 `SFTSequencer /Open:”package.sprj” /MSI` 。 有关详细信息，请参阅[如何使用命令行升级虚拟应用程序](how-to-upgrade-a-virtual-application-by-using-the-command-line.md)。

 

### 发行说明版权信息

本文档 "按现状" 提供。 本文档中表达的信息和视图（包括 URL 和其他 Internet 网站引用）如有更改，恕不另行通知。 使用本文档的风险由你自己承担。

此处描述的一些示例仅供说明，并且是虚构的。不打算或应该推断出真正的关联或连接。

本文档未向你提供针对任何 Microsoft 产品的任何知识产权的任何法律权限。 可以复制本文档并将其用于进行内部参考。 你可以出于内部参考目的修改此文档。



Microsoft、Active Directory、ActiveSync、ActiveX、Excel、SQL Server、Windows、Windows PowerShell、Windows Server 和 Windows Vista 是 Microsoft 组公司的商标。

所有其他商标的所有权属于其各自所有者。

 

 





