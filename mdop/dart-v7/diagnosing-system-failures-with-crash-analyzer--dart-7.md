---
title: 使用故障分析器诊断系统故障
description: 使用故障分析器诊断系统故障
author: dansimp
ms.assetid: 170d40ef-4edb-4a32-a349-c285c0ea5e56
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3c5f8b7e189de024d7ceb84f8cfc151dc82d56ed
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803374"
---
# 使用故障分析器诊断系统故障


Microsoft Diagnostics 和恢复工具套件（DaRT）7中的崩溃分析器使你能够在基于 Windows 的计算机上调试故障转储文件，然后诊断任何相关的计算机错误。 崩溃分析器使用 Microsoft 调试工具 for Windows 检查导致计算机失败的驱动程序的故障转储文件。

## 在最终用户计算机上运行崩溃分析器


通常，你可以从出现问题的最终用户计算机上的 "诊断和恢复工具集" 窗口中运行崩溃分析器。 故障分析器将尝试在有问题的计算机上查找 Windows 的调试工具。 如果 "目录路径" 对话框为空，则必须输入位置或浏览到 Windows 调试工具的位置（可以从 Microsoft 下载文件）。 你还必须提供指向符号文件所在位置的路径。

如果你在创建 DaRT 恢复映像时包含适用于 Windows 的 Microsoft 调试工具和符号文件，则当你在有问题的计算机上运行崩溃分析器时，它们应该可用。

[如何在最终用户计算机上运行故障分析器](how-to-run-the-crash-analyzer-on-an-end-user-computer-dart-7.md)

## 在除最终用户计算机之外的计算机上以独立模式运行崩溃分析器


故障分析器将尝试在有问题的计算机上查找 Windows 的调试工具。 如果 "目录路径" 对话框为空，则必须输入位置或浏览到 Windows 调试工具的位置（可以从 Microsoft 下载文件）。 你还必须提供指向符号文件所在位置的路径。

如果你在创建 DaRT 恢复映像时未包含适用于 Windows 和符号文件的 Microsoft 调试工具，或者如果磁盘大小或网络连接问题阻止你获取它们，则可以从有问题的计算机复制转储文件，并将其分析到安装了独立版本的崩溃分析程序的计算机上，如帮助台管理员的计算机。

[如何在最终用户计算机以外的计算机上以独立模式运行故障分析器](how-to-run-the-crash-analyzer-in-stand-alone-mode-on-a-computer-other-than-an-end-user-computer-dart-7.md)

## 确保崩溃分析器可以访问符号文件


通常，调试信息存储在与可执行文件不同的符号文件中。 当你调试已停止响应的应用程序时（例如，如果该应用程序崩溃），你必须具有访问符号信息的权限。

当运行崩溃分析器时，将自动下载符号文件。 如果计算机没有 Internet 连接或网络要求计算机访问 HTTP 代理服务器，则无法下载符号文件。

[如何确保故障分析器可以访问符号文件](how-to-ensure-that-crash-analyzer-can-access-symbol-files-dart-7.md)

## 用于诊断故障分析器的系统故障的其他资源


[DaRT 7.0 的操作](operations-for-dart-70-new-ia.md)

 

 





