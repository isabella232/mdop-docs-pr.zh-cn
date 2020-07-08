---
title: 如何在最终用户计算机以外的计算机上以独立模式运行故障分析器
description: 如何在最终用户计算机以外的计算机上以独立模式运行故障分析器
author: dansimp
ms.assetid: 27c1e1c6-123a-4f8a-b7d2-5bddc9ca3249
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 485823c17d650323ca68cccf1308ac8ec9e5212b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803197"
---
# 如何在最终用户计算机以外的计算机上以独立模式运行故障分析器


如果无法访问 Microsoft 调试工具 for Windows 或最终用户计算机上的符号文件，则可以从有问题的计算机复制转储文件，并将其分析到安装了独立版本的崩溃分析器的计算机上，例如包含 Microsoft 诊断和恢复工具集（DaRT）10的技术支持计算机。

若要在独立模式下运行崩溃分析程序，请从有问题的计算机复制内存转储文件，然后在另一台计算机（如技术支持计算机）上分析该文件，该计算机安装有**崩溃分析器**。

**以独立模式运行崩溃分析器**

1.  在安装了 DaRT 10 的计算机上，单击 "**开始**"，键入**故障分析器**，然后单击 "**崩溃分析器**"。

2.  按照[如何在最终用户计算机上运行崩溃分析器](how-to-run-the-crash-analyzer-on-an-end-user-computer-dart-10.md)中所述，按照向导中的步骤操作。

## 相关主题


[DaRT 10 的操作](operations-for-dart-10.md)

[使用故障分析器诊断系统故障](diagnosing-system-failures-with-crash-analyzer-dart-10.md)

[如何确保故障分析器可以访问符号文件](how-to-ensure-that-crash-analyzer-can-access-symbol-files-dart-10.md)

 

 





