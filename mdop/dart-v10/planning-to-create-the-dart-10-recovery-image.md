---
title: 计划创建 DaRT 10 恢复映像
description: 计划创建 DaRT 10 恢复映像
author: dansimp
ms.assetid: a0087d93-b88f-454b-81b2-3c7ce3718023
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 44cf052eaffd19645885618da9104e5b0a50cfd5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803276"
---
# 计划创建 DaRT 10 恢复映像


当你计划创建 Microsoft 诊断和恢复工具集（DaRT）10恢复映像时，请使用本部分中的信息。

## 计划创建 DaRT 10 恢复映像


创建 DaRT 恢复映像时，必须确定要在映像中包含的工具。 若要做出决策，请考虑最终用户可以访问这些工具。 如果支持工程师将恢复图像媒体转到最终用户的计算机以诊断问题，则可能需要在恢复映像上安装所有工具。 如果你打算远程诊断最终用户的计算机，你可能希望禁用某些工具，如 "磁盘擦除" 和 "注册表编辑器"，然后启用其他工具，包括远程连接。

创建 DaRT 恢复映像时，你还将指定是否要包括其他驱动程序或文件。 确定要包括在 DaRT 恢复映像中的任何其他驱动程序或文件的位置。

有关 DaRT 工具的详细信息，请参阅[dart 10 中的工具概述](overview-of-the-tools-in-dart-10.md)。 有关如何帮助创建安全恢复映像的详细信息，请参阅[DaRT 10 的安全注意事项](security-considerations-for-dart-10.md)。

## 恢复映像的先决条件


创建 DaRT 恢复映像需要或推荐以下项目：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>必备</strong></p></td>
<td align="left"><p><strong>详细信息</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 10 源文件</p></td>
<td align="left"><p>创建 DaRT 恢复映像所需。 提供 Windows 10 DVD 或 Windows 10 源文件的路径。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>适用于你的平台的 Windows 调试工具</p></td>
<td align="left"><p>在运行 <strong> 崩溃分析器 </strong> 以确定计算机故障原因时需要。 我们建议你在创建 DaRT 恢复映像时指定 Windows 调试工具的路径。 你可以在此处下载 Windows 调试工具： <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/" data-raw-source="[Download and Install Debugging Tools for Windows](https://docs.microsoft.com/windows-hardware/drivers/debugger/)"> 下载并安装 Windows 调试工具 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>可选： Windows 符号用于 <strong> 故障分析器的文件</strong></p></td>
<td align="left"><p>通常，调试信息存储在与程序分离的符号文件中。 调试已停止响应的应用程序时，您必须具有访问符号信息的权限，例如，如果该应用程序停止工作。 有关详细信息，请参阅 <a href="diagnosing-system-failures-with-crash-analyzer-dart-10.md" data-raw-source="[Diagnosing System Failures with Crash Analyzer](diagnosing-system-failures-with-crash-analyzer-dart-10.md)"> 诊断故障分析器的系统故障 </a> 。</p></td>
</tr>
</tbody>
</table>

 

## 相关主题

[计划部署 DaRT 10](planning-to-deploy-dart-10.md)

 

 




