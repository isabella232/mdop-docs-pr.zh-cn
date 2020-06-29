---
title: 如何在最终用户计算机上运行故障分析器
description: 如何在最终用户计算机上运行故障分析器
author: dansimp
ms.assetid: 40af4ead-6588-4a81-8eaa-3dc00c397e1d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 943e3956609ae7e24deaca4313036445802a8f7f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803448"
---
# 如何在最终用户计算机上运行故障分析器


通常，你可以从遇到问题的最终用户计算机上的诊断和恢复工具集窗口中运行 Microsoft 诊断和恢复工具集（DaRT）7故障分析器。 故障分析器将尝试在有问题的计算机上查找 Windows 的调试工具。 如果 "目录路径" 对话框为空，则必须输入位置或浏览到 Windows 调试工具的位置（可以从 Microsoft 下载文件）。 你还必须提供指向符号文件所在位置的路径。

**在最终用户计算机上打开并运行崩溃分析器**

1.  在最终用户计算机上的 "**诊断和恢复工具集**" 窗口中，单击 "**崩溃分析器**"。

2.  提供以下内容所需的信息：

    -   适用于 Windows 的 Microsoft 调试工具

    -   符号文件

        有关符号文件的详细信息，请参阅[如何确保崩溃分析器可以访问符号文件](how-to-ensure-that-crash-analyzer-can-access-symbol-files-dart-7.md)。

    -   故障转储文件

        按照以下步骤确定故障转储文件的位置：

        1.  打开 "**系统属性**" 窗口。

            单击 "**开始**"，键入 sysdm.cpl，然后按 Enter。

        2.  单击**高级**选项卡。

        3.  在 "**启动和故障恢复**" 区域中，单击 "**设置**"。

        **注意** 如果您无法访问 "**系统属性**" 窗口，则可以使用 DaRT 中的**搜索**工具在最终用户计算机上搜索转储文件。

         

3.  **崩溃分析器**将扫描故障转储文件，并报告崩溃的可能原因。 你可以查看有关崩溃的详细信息，如特定的崩溃消息和说明、在崩溃时加载的驱动程序以及分析的完整输出。

4.  确定合适的策略来解决该问题。 这可能需要通过使用 DaRT 中**计算机管理**工具的 "**服务和驱动程序**" 节点禁用或更新导致崩溃的设备驱动程序。

## 相关主题


[使用故障分析器诊断系统故障](diagnosing-system-failures-with-crash-analyzer--dart-7.md)

 

 





