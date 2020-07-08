---
title: 使用故障分析器诊断系统故障
description: 使用故障分析器诊断系统故障
author: dansimp
ms.assetid: ce3d3186-54fb-45b2-b5ce-9bb7841db28f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: abb9d1ec99236199e0866a3b23219dd412bc9da6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803589"
---
# 使用故障分析器诊断系统故障


Microsoft Diagnostics 和恢复工具套件（DaRT）8.0 中的**崩溃分析器**使你能够在基于 Windows 的计算机上调试内存转储文件，然后诊断任何相关的计算机错误。 **崩溃分析器**使用 Microsoft 调试工具 for Windows 检查导致计算机失败的驱动程序的内存转储文件。 你可以在终端用户计算机上或在非最终用户计算机之外的计算机上运行崩溃分析器。

## 在最终用户计算机上运行崩溃分析器


通常，你可以从遇到问题的最终用户计算机上的 "**诊断和恢复工具集**" 窗口中运行**崩溃分析器**。 **故障分析器**将尝试在有问题的计算机上查找 Windows 的调试工具。 如果 "目录路径" 对话框为空，则必须输入位置，或浏览到 Windows 调试工具的位置（可以从 Microsoft 下载文件）。 你还必须提供指向符号文件所在位置的路径。

如果你在创建 DaRT 8.0 恢复映像时包含适用于 Windows 和符号文件的 Microsoft 调试工具和符号文件，则当你在问题计算机上运行**崩溃分析器**时，工具和符号文件应该可用。 如果你未将它们包含在 DaRT 恢复映像中，或者如果磁盘大小或网络连接问题阻止你获取它们，你也可以在除最终用户计算机之外的计算机上以独立模式运行崩溃分析器，如下部分所述。

[如何在最终用户计算机上运行故障分析器](how-to-run-the-crash-analyzer-on-an-end-user-computer-dart-8.md)

## <a href="" id="run-the-crash-analyzer-in-stand-alone-mode-on-a-computer-other-than-an-end-user-s-computer"></a>在除最终用户的计算机之外的计算机上以独立模式运行崩溃分析器


尽管你通常在遇到问题的最终用户计算机上运行**崩溃分析**程序，但你也可以在独立模式下运行崩溃分析器，而不是最终用户的计算机。 如果你未在 DaRT 恢复映像中包含 Windows 调试工具，或者当磁盘大小或网络连接问题阻止你获取调试工具时，你可以选择此选项。 在这种情况下，你可以从有问题的计算机复制转储文件，并将其分析到安装了独立版本的**崩溃分析器**的计算机上，例如在技术支持代理的计算机上。

[如何在最终用户计算机以外的计算机上以独立模式运行故障分析器](how-to-run-the-crash-analyzer-in-stand-alone-mode-on-a-computer-other-than-an-end-user-computer-dart-8.md)

## 如何确保崩溃分析器可以访问符号文件


若要调试已停止响应的应用程序，您需要访问符号文件，该文件与程序分开。 尽管在运行崩溃分析器时将自动下载符号文件，但有时问题计算机无法访问 Internet。 有多种方法可确保您有权访问符号文件。

[如何确保故障分析器可以访问符号文件](how-to-ensure-that-crash-analyzer-can-access-symbol-files.md)

## 用于诊断故障分析器的系统故障的其他资源


[DaRT 8.0 的操作](operations-for-dart-80-dart-8.md)

 

 





