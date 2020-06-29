---
title: 计划创建 DaRT 7.0 恢复映像
description: 计划创建 DaRT 7.0 恢复映像
author: dansimp
ms.assetid: e5d49bee-ae4e-467b-9976-c1203f6355f9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: c370d2a69ec8ccea217696045e64e9a0ae724815
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802947"
---
# 计划创建 DaRT 7.0 恢复映像


当你计划创建 Microsoft 诊断和恢复工具集（DaRT）7恢复映像时，请使用本部分中的信息。

## 计划创建 DaRT 7 恢复映像


创建 DaRT 恢复映像时，必须确定要在映像中包含的工具。 做出决策时，请记住最终用户可能偶尔有权访问各种 DaRT 工具。 有关 DaRT 工具的详细信息，请参阅[DaRT 7.0 中的工具概述](overview-of-the-tools-in-dart-70-new-ia.md)。 有关如何帮助创建安全恢复映像的详细信息，请参阅[DaRT 7.0 的安全注意事项](security-considerations-for-dart-70-dart-7.md)。

创建 DaRT 恢复映像时，你还将指定是否要包括其他驱动程序或文件。 确定要包括在 DaRT 恢复映像中的任何其他驱动程序或文件的位置。

## 必备条件


创建 DaRT 恢复映像需要或推荐以下项目：

-   Windows 7 源文件

    你必须提供 Windows 7 DVD 或 Windows 7 源文件的路径。 创建 DaRT 恢复映像需要 Windows 7 源文件。

-   适用于你的平台的 Windows 调试工具

    运行**崩溃分析**程序以确定计算机崩溃的原因时，需要使用 Windows 调试工具。 我们建议你在创建 DaRT 恢复映像时指定 Windows 调试工具的路径。 如果需要，您可以在此处下载 Windows 调试工具：[下载并安装 Windows 调试工具](https://go.microsoft.com/fwlink/?LinkId=99934)。

-   可选：**独立系统 Sweeper**定义

    当你运行此工具时，**独立系统 Sweeper**的最新定义是必需的。 虽然你可以在运行**独立系统 Sweeper**时下载定义，但我们建议你在创建 DaRT 恢复映像时下载最新的定义。 通过这种方式，即使问题计算机没有网络连接，您仍然可以使用最新的定义运行该工具。

-   可选： Windows 符号用于**故障分析器**的文件

    通常，调试信息存储在与可执行文件不同的符号文件中。 当你调试已停止响应的应用程序时（例如，如果该应用程序崩溃），你必须具有访问符号信息的权限。 有关详细信息，请参阅[诊断故障分析器的系统故障](diagnosing-system-failures-with-crash-analyzer--dart-7.md)。

## 相关主题


[计划部署 DaRT 7.0](planning-to-deploy-dart-70.md)

 

 





