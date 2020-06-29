---
title: 如何在最终用户计算机以外的计算机上以独立模式运行故障分析器
description: 如何在最终用户计算机以外的计算机上以独立模式运行故障分析器
author: dansimp
ms.assetid: 881d573f-2f18-4c5f-838e-2f5320179f94
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6f398c56b7c631145388541b71229d69c16bf6f3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803238"
---
# 如何在最终用户计算机以外的计算机上以独立模式运行故障分析器


如果无法访问 Microsoft 调试工具 for Windows 或最终用户计算机上的符号文件，则可以从有问题的计算机复制转储文件，并将其分析到安装了独立版本的崩溃分析器（如帮助台管理员的计算机）的计算机上。

**以独立模式运行崩溃分析器**

1.  在安装了 DaRT7 的计算机上，单击 "**启动**  /  **All Programs**  /  **Microsoft DaRT 7**中的所有程序"。

2.  提供以下内容所需的信息：

    -   适用于 Windows 的 Microsoft 调试工具

    -   符号文件

        有关符号文件的详细信息，请参阅[如何确保崩溃分析器可以访问符号文件](how-to-ensure-that-crash-analyzer-can-access-symbol-files-dart-7.md)。

    -   故障转储文件

        **注意** 使用 DaRT7 中的搜索工具查找复制的故障转储文件。

         

3.  **崩溃分析器**将扫描故障转储文件，并报告崩溃的可能原因。 你可以查看有关崩溃的详细信息，如特定的崩溃消息和说明、在崩溃时加载的驱动程序以及分析的完整输出。

4.  确定合适的策略来解决该问题。 这可能需要通过使用 DaRT 中**计算机管理**工具的 "**服务和驱动程序**" 节点禁用或更新导致崩溃的设备驱动程序。

## 相关主题


[使用故障分析器诊断系统故障](diagnosing-system-failures-with-crash-analyzer--dart-7.md)

 

 





