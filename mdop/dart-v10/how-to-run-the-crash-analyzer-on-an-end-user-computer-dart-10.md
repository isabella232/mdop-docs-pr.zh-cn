---
title: 如何在最终用户计算机上运行故障分析器
description: 如何在最终用户计算机上运行故障分析器
author: dansimp
ms.assetid: 10334800-ff8e-43ac-a9c2-d28807473ec2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 4abf1ba2ae1a0cb1dfb129c1f5a26e11f5045290
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803214"
---
# 如何在最终用户计算机上运行故障分析器


若要从遇到问题的最终用户计算机上的 "**诊断和恢复工具集**" 窗口中运行**崩溃分析器**，必须具有 Windows 的 Microsoft 调试工具和所安装的符号文件。 若要下载 Windows 调试工具，请参阅[Windows 调试工具](https://go.microsoft.com/fwlink/?LinkId=266248)。

**在最终用户计算机上运行崩溃分析器**

1.  在最终用户计算机上的 "**诊断和恢复工具集**" 窗口中，单击 "**崩溃分析器**"。

2.  提供适用于 Windows 的 Microsoft 调试工具所需的信息。

3.  提供符号文件所需的信息。 有关符号文件的详细信息，请参阅[如何确保崩溃分析器可以访问符号文件](how-to-ensure-that-crash-analyzer-can-access-symbol-files-dart-10.md)。

4.  提供内存转储文件所需的信息。 要确定内存转储文件的位置，请执行以下操作：

    1.  打开 "**系统属性**" 窗口。

    2.  单击 "**开始**"，键入**sysdm.cpl**，然后按**Enter**。

    3.  单击**高级**选项卡。

    4.  在 "**启动和故障恢复**" 区域中，单击 "**设置**"。

        如果你无法访问 "**系统属性**" 窗口，则可以使用 Microsoft 诊断和恢复工具集（DaRT）10中的**搜索**工具在最终用户计算机上搜索转储文件。

    **崩溃分析器**将扫描内存转储文件，并报告问题的可能原因。 你可以查看有关失败的详细信息，如特定内存转储消息和说明、在出现故障时加载的驱动程序以及分析的完整输出。

5.  确定解决问题的相应策略。 通过使用 DaRT 10 中**计算机管理**工具的 "**服务和驱动程序**" 节点，策略可能需要禁用或更新导致故障的设备驱动程序。

## 相关主题


[使用故障分析器诊断系统故障](diagnosing-system-failures-with-crash-analyzer-dart-10.md)

[DaRT 10 的操作](operations-for-dart-10.md)

 

 





