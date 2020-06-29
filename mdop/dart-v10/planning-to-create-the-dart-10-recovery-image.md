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
# <span data-ttu-id="c5fde-103">计划创建 DaRT 10 恢复映像</span><span class="sxs-lookup"><span data-stu-id="c5fde-103">Planning to Create the DaRT 10 Recovery Image</span></span>


<span data-ttu-id="c5fde-104">当你计划创建 Microsoft 诊断和恢复工具集（DaRT）10恢复映像时，请使用本部分中的信息。</span><span class="sxs-lookup"><span data-stu-id="c5fde-104">Use the information in this section when you are planning to create the Microsoft Diagnostics and Recovery Toolset (DaRT) 10 recovery image.</span></span>

## <span data-ttu-id="c5fde-105">计划创建 DaRT 10 恢复映像</span><span class="sxs-lookup"><span data-stu-id="c5fde-105">Planning to create the DaRT 10 recovery image</span></span>


<span data-ttu-id="c5fde-106">创建 DaRT 恢复映像时，必须确定要在映像中包含的工具。</span><span class="sxs-lookup"><span data-stu-id="c5fde-106">When you create the DaRT recovery image, you have to decide which tools to include on the image.</span></span> <span data-ttu-id="c5fde-107">若要做出决策，请考虑最终用户可以访问这些工具。</span><span class="sxs-lookup"><span data-stu-id="c5fde-107">To make the decision, consider that end users may have access to those tools.</span></span> <span data-ttu-id="c5fde-108">如果支持工程师将恢复图像媒体转到最终用户的计算机以诊断问题，则可能需要在恢复映像上安装所有工具。</span><span class="sxs-lookup"><span data-stu-id="c5fde-108">If support engineers will take the recovery image media to end users’ computers to diagnose issues, you may want to install all of the tools on the recovery image.</span></span> <span data-ttu-id="c5fde-109">如果你打算远程诊断最终用户的计算机，你可能希望禁用某些工具，如 "磁盘擦除" 和 "注册表编辑器"，然后启用其他工具，包括远程连接。</span><span class="sxs-lookup"><span data-stu-id="c5fde-109">If you plan to diagnose end user’s computers remotely, you may want to disable some of the tools, such as Disk Wipe and Registry Editor, and then enable other tools, including Remote Connection.</span></span>

<span data-ttu-id="c5fde-110">创建 DaRT 恢复映像时，你还将指定是否要包括其他驱动程序或文件。</span><span class="sxs-lookup"><span data-stu-id="c5fde-110">When you create the DaRT recovery image, you will also specify whether you want to include additional drivers or files.</span></span> <span data-ttu-id="c5fde-111">确定要包括在 DaRT 恢复映像中的任何其他驱动程序或文件的位置。</span><span class="sxs-lookup"><span data-stu-id="c5fde-111">Determine the locations of any additional drivers or files that you want to include on the DaRT recovery image.</span></span>

<span data-ttu-id="c5fde-112">有关 DaRT 工具的详细信息，请参阅[dart 10 中的工具概述](overview-of-the-tools-in-dart-10.md)。</span><span class="sxs-lookup"><span data-stu-id="c5fde-112">For more information about the DaRT tools, see [Overview of the Tools in DaRT 10](overview-of-the-tools-in-dart-10.md).</span></span> <span data-ttu-id="c5fde-113">有关如何帮助创建安全恢复映像的详细信息，请参阅[DaRT 10 的安全注意事项](security-considerations-for-dart-10.md)。</span><span class="sxs-lookup"><span data-stu-id="c5fde-113">For more information about how to help create a secure recovery image, see [Security Considerations for DaRT 10](security-considerations-for-dart-10.md).</span></span>

## <span data-ttu-id="c5fde-114">恢复映像的先决条件</span><span class="sxs-lookup"><span data-stu-id="c5fde-114">Prerequisites for the recovery image</span></span>


<span data-ttu-id="c5fde-115">创建 DaRT 恢复映像需要或推荐以下项目：</span><span class="sxs-lookup"><span data-stu-id="c5fde-115">The following items are required or recommended for creating the DaRT recovery image:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="c5fde-116">必备</span><span class="sxs-lookup"><span data-stu-id="c5fde-116">Prerequisite</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="c5fde-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="c5fde-117">Details</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c5fde-118">Windows 10 源文件</span><span class="sxs-lookup"><span data-stu-id="c5fde-118">Windows 10 source files</span></span></p></td>
<td align="left"><p><span data-ttu-id="c5fde-119">创建 DaRT 恢复映像所需。</span><span class="sxs-lookup"><span data-stu-id="c5fde-119">Required to create the DaRT recovery image.</span></span> <span data-ttu-id="c5fde-120">提供 Windows 10 DVD 或 Windows 10 源文件的路径。</span><span class="sxs-lookup"><span data-stu-id="c5fde-120">Provide the path of a Windows 10 DVD or of Windows 10 source files.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c5fde-121">适用于你的平台的 Windows 调试工具</span><span class="sxs-lookup"><span data-stu-id="c5fde-121">Windows Debugging Tools for your platform</span></span></p></td>
<td align="left"><p><span data-ttu-id="c5fde-122">在运行 <strong> 崩溃分析器 </strong> 以确定计算机故障原因时需要。</span><span class="sxs-lookup"><span data-stu-id="c5fde-122">Required when you run the <strong>Crash Analyzer</strong> to determine the cause of a computer failure.</span></span> <span data-ttu-id="c5fde-123">我们建议你在创建 DaRT 恢复映像时指定 Windows 调试工具的路径。</span><span class="sxs-lookup"><span data-stu-id="c5fde-123">We recommend that you specify the path of the Windows Debugging Tools at the time that you create the DaRT recovery image.</span></span> <span data-ttu-id="c5fde-124">你可以在此处下载 Windows 调试工具： <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/" data-raw-source="[Download and Install Debugging Tools for Windows](https://docs.microsoft.com/windows-hardware/drivers/debugger/)"> 下载并安装 Windows 调试工具 </a> 。</span><span class="sxs-lookup"><span data-stu-id="c5fde-124">You can download the Windows Debugging Tools here: <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/" data-raw-source="[Download and Install Debugging Tools for Windows](https://docs.microsoft.com/windows-hardware/drivers/debugger/)">Download and Install Debugging Tools for Windows</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c5fde-125">可选： Windows 符号用于 <strong> 故障分析器的文件</span><span class="sxs-lookup"><span data-stu-id="c5fde-125">Optional: Windows symbols files for use with <strong>Crash Analyzer</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="c5fde-126">通常，调试信息存储在与程序分离的符号文件中。</span><span class="sxs-lookup"><span data-stu-id="c5fde-126">Typically, debugging information is stored in a symbol file that is separate from the program.</span></span> <span data-ttu-id="c5fde-127">调试已停止响应的应用程序时，您必须具有访问符号信息的权限，例如，如果该应用程序停止工作。</span><span class="sxs-lookup"><span data-stu-id="c5fde-127">You must have access to the symbol information when you debug an application that has stopped responding, for example, if it stopped working.</span></span> <span data-ttu-id="c5fde-128">有关详细信息，请参阅 <a href="diagnosing-system-failures-with-crash-analyzer-dart-10.md" data-raw-source="[Diagnosing System Failures with Crash Analyzer](diagnosing-system-failures-with-crash-analyzer-dart-10.md)"> 诊断故障分析器的系统故障 </a> 。</span><span class="sxs-lookup"><span data-stu-id="c5fde-128">For more information, see <a href="diagnosing-system-failures-with-crash-analyzer-dart-10.md" data-raw-source="[Diagnosing System Failures with Crash Analyzer](diagnosing-system-failures-with-crash-analyzer-dart-10.md)">Diagnosing System Failures with Crash Analyzer</a>.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="c5fde-129">相关主题</span><span class="sxs-lookup"><span data-stu-id="c5fde-129">Related topics</span></span>

[<span data-ttu-id="c5fde-130">计划部署 DaRT 10</span><span class="sxs-lookup"><span data-stu-id="c5fde-130">Planning to Deploy DaRT 10</span></span>](planning-to-deploy-dart-10.md)

 

 




