---
title: 如何确保故障分析器可以访问符号文件
description: 如何确保故障分析器可以访问符号文件
author: dansimp
ms.assetid: 99839013-1cd8-44d1-8484-0e15261c5a4b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 944198b95528a548acbe1229f9f3aad4c224af29
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802926"
---
# 如何确保故障分析器可以访问符号文件


通常，调试信息存储在与程序分离的符号文件中。 调试已停止响应的应用程序时，您必须具有访问符号信息的权限。

当运行**崩溃分析器**时，将自动下载符号文件。 如果计算机没有 Internet 连接或网络要求计算机访问 HTTP 代理服务器，则无法下载符号文件。

**确保崩溃分析器可以访问符号文件**

1.  **将转储文件复制到另一台计算机上。** 如果由于缺少 Internet 连接而无法下载符号，请将内存转储文件复制到具有 Internet 连接的计算机上，并在该计算机上运行独立的**故障分析器向导**。

2.  **从另一台计算机访问符号文件。** 如果由于缺少 Internet 连接而无法下载符号，则可以从具有 Internet 连接的计算机下载符号，然后将其复制到没有 Internet 连接的计算机上，也可以将网络驱动器映射到本地网络上的符号可用的位置。 如果你在 Windows 恢复环境（WindowsRE）中运行**崩溃分析**程序，你可以在 Microsoft 诊断和恢复工具集（DaRT）8.0 恢复映像上包括符号文件。

3.  **通过 HTTP 代理服务器访问符号文件。** 如果无法下载符号，因为必须访问 HTTP 代理服务器，请使用以下步骤访问 HTTP 代理服务器。 在 DaRT 8.0 中，**故障分析器向导**在 "**指定符号文件位置**" 对话框页面上提供了一个设置，使用标签**代理服务器（可选，使用 "服务器：端口" 格式）** 标记。 可以使用此文本框指定代理服务器。 在 " ** &lt; 主机名 &gt; ： &lt; 端口 &gt; **" 窗体中输入代理地址，其中 &lt; **主机名** &gt; 是 DNS 名称或 IP 地址，而 &lt; **端口** &gt; 是 TCP 端口号，通常为80。 可通过两种模式运行**崩溃分析器**。 下面介绍如何在其中每种模式下使用代理设置：

    -   **联机模式：** 在此模式下，如果 "代理服务器" 字段保留为空，向导将使用 "控制面板" 中的 "Internet 选项" 中的代理设置。 如果在提供的文本框中输入代理地址，则将使用该地址，并且它将覆盖 "Internet 选项" 中的设置。

    -   Windows 恢复环境（WindowsRE）：从 "**诊断和恢复工具集**" 窗口运行**崩溃分析**程序时，没有默认的代理地址。 如果计算机直接连接到 Internet，则不需要代理地址。 因此，您可以在向导设置中将此字段保留为空。 如果计算机未直接连接到 Internet，并且它位于具有代理服务器的网络环境中，则必须在向导中将 "代理" 字段设置为 "访问符号存储区"。 可以从网络管理员处获取代理地址。 只有当公用符号存储连接到 Internet 时，设置代理服务器才很重要。 如果这些符号已在 DaRT 恢复映像上，或者如果它们在本地可用，则不需要设置代理服务器。

## 相关主题


[使用故障分析器诊断系统故障](diagnosing-system-failures-with-crash-analyzer--dart-8.md)

[DaRT 8.0 的操作](operations-for-dart-80-dart-8.md)

 

 





