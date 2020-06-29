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
# <span data-ttu-id="55a6c-103">计划创建 DaRT 7.0 恢复映像</span><span class="sxs-lookup"><span data-stu-id="55a6c-103">Planning to Create the DaRT 7.0 Recovery Image</span></span>


<span data-ttu-id="55a6c-104">当你计划创建 Microsoft 诊断和恢复工具集（DaRT）7恢复映像时，请使用本部分中的信息。</span><span class="sxs-lookup"><span data-stu-id="55a6c-104">Use the information in this section when you plan for creating the Microsoft Diagnostics and Recovery Toolset (DaRT)7 recovery image.</span></span>

## <span data-ttu-id="55a6c-105">计划创建 DaRT 7 恢复映像</span><span class="sxs-lookup"><span data-stu-id="55a6c-105">Planning to Create the DaRT 7 Recovery Image</span></span>


<span data-ttu-id="55a6c-106">创建 DaRT 恢复映像时，必须确定要在映像中包含的工具。</span><span class="sxs-lookup"><span data-stu-id="55a6c-106">When you create the DaRT recovery image, you have to decide which tools to include on the image.</span></span> <span data-ttu-id="55a6c-107">做出决策时，请记住最终用户可能偶尔有权访问各种 DaRT 工具。</span><span class="sxs-lookup"><span data-stu-id="55a6c-107">When you make that decision, remember that end users might have access occasionally to the various DaRT tools.</span></span> <span data-ttu-id="55a6c-108">有关 DaRT 工具的详细信息，请参阅[DaRT 7.0 中的工具概述](overview-of-the-tools-in-dart-70-new-ia.md)。</span><span class="sxs-lookup"><span data-stu-id="55a6c-108">For more information about the DaRT tools, see [Overview of the Tools in DaRT 7.0](overview-of-the-tools-in-dart-70-new-ia.md).</span></span> <span data-ttu-id="55a6c-109">有关如何帮助创建安全恢复映像的详细信息，请参阅[DaRT 7.0 的安全注意事项](security-considerations-for-dart-70-dart-7.md)。</span><span class="sxs-lookup"><span data-stu-id="55a6c-109">For more information about how to help create a secure recovery image, see [Security Considerations for DaRT 7.0](security-considerations-for-dart-70-dart-7.md).</span></span>

<span data-ttu-id="55a6c-110">创建 DaRT 恢复映像时，你还将指定是否要包括其他驱动程序或文件。</span><span class="sxs-lookup"><span data-stu-id="55a6c-110">When you create the DaRT recovery image, you will also specify whether you want to include additional drivers or files.</span></span> <span data-ttu-id="55a6c-111">确定要包括在 DaRT 恢复映像中的任何其他驱动程序或文件的位置。</span><span class="sxs-lookup"><span data-stu-id="55a6c-111">Determine the locations of any additional drivers or files that you want to include on the DaRT recovery image.</span></span>

## <span data-ttu-id="55a6c-112">必备条件</span><span class="sxs-lookup"><span data-stu-id="55a6c-112">Prerequisites</span></span>


<span data-ttu-id="55a6c-113">创建 DaRT 恢复映像需要或推荐以下项目：</span><span class="sxs-lookup"><span data-stu-id="55a6c-113">The following items are required or recommended for creating the DaRT recovery image:</span></span>

-   <span data-ttu-id="55a6c-114">Windows 7 源文件</span><span class="sxs-lookup"><span data-stu-id="55a6c-114">Windows 7 source files</span></span>

    <span data-ttu-id="55a6c-115">你必须提供 Windows 7 DVD 或 Windows 7 源文件的路径。</span><span class="sxs-lookup"><span data-stu-id="55a6c-115">You must provide the path of a Windows 7 DVD or of Windows 7 source files.</span></span> <span data-ttu-id="55a6c-116">创建 DaRT 恢复映像需要 Windows 7 源文件。</span><span class="sxs-lookup"><span data-stu-id="55a6c-116">Windows 7 source files are required to create the DaRT recovery image.</span></span>

-   <span data-ttu-id="55a6c-117">适用于你的平台的 Windows 调试工具</span><span class="sxs-lookup"><span data-stu-id="55a6c-117">Windows Debugging Tools for your platform</span></span>

    <span data-ttu-id="55a6c-118">运行**崩溃分析**程序以确定计算机崩溃的原因时，需要使用 Windows 调试工具。</span><span class="sxs-lookup"><span data-stu-id="55a6c-118">Windows Debugging Tools are required when you run **Crash Analyzer** to determine the cause of a computer crash.</span></span> <span data-ttu-id="55a6c-119">我们建议你在创建 DaRT 恢复映像时指定 Windows 调试工具的路径。</span><span class="sxs-lookup"><span data-stu-id="55a6c-119">We recommend that you specify the path of the Windows Debugging Tools at the time that you create the DaRT recovery image.</span></span> <span data-ttu-id="55a6c-120">如果需要，您可以在此处下载 Windows 调试工具：[下载并安装 Windows 调试工具](https://go.microsoft.com/fwlink/?LinkId=99934)。</span><span class="sxs-lookup"><span data-stu-id="55a6c-120">If it is necessary, you can download the Windows Debugging Tools here: [Download and Install Debugging Tools for Windows](https://go.microsoft.com/fwlink/?LinkId=99934).</span></span>

-   <span data-ttu-id="55a6c-121">可选：**独立系统 Sweeper**定义</span><span class="sxs-lookup"><span data-stu-id="55a6c-121">Optional: **Standalone System Sweeper** definitions</span></span>

    <span data-ttu-id="55a6c-122">当你运行此工具时，**独立系统 Sweeper**的最新定义是必需的。</span><span class="sxs-lookup"><span data-stu-id="55a6c-122">The latest definitions for the **Standalone System Sweeper** are required when you run this tool.</span></span> <span data-ttu-id="55a6c-123">虽然你可以在运行**独立系统 Sweeper**时下载定义，但我们建议你在创建 DaRT 恢复映像时下载最新的定义。</span><span class="sxs-lookup"><span data-stu-id="55a6c-123">Although you can download the definitions when you run **Standalone System Sweeper**, we recommend that you download the latest definitions at the time you create the DaRT recovery image.</span></span> <span data-ttu-id="55a6c-124">通过这种方式，即使问题计算机没有网络连接，您仍然可以使用最新的定义运行该工具。</span><span class="sxs-lookup"><span data-stu-id="55a6c-124">In this manner, you can still run the tool with the latest definitions even if the problem computer does not have network connectivity.</span></span>

-   <span data-ttu-id="55a6c-125">可选： Windows 符号用于**故障分析器**的文件</span><span class="sxs-lookup"><span data-stu-id="55a6c-125">Optional: Windows symbols files for use with **Crash Analyzer**</span></span>

    <span data-ttu-id="55a6c-126">通常，调试信息存储在与可执行文件不同的符号文件中。</span><span class="sxs-lookup"><span data-stu-id="55a6c-126">Typically, debugging information is stored in a symbol file that is separate from the executable.</span></span> <span data-ttu-id="55a6c-127">当你调试已停止响应的应用程序时（例如，如果该应用程序崩溃），你必须具有访问符号信息的权限。</span><span class="sxs-lookup"><span data-stu-id="55a6c-127">You must have access to the symbol information when you debug an application that has stopped responding, for example if it crashed.</span></span> <span data-ttu-id="55a6c-128">有关详细信息，请参阅[诊断故障分析器的系统故障](diagnosing-system-failures-with-crash-analyzer--dart-7.md)。</span><span class="sxs-lookup"><span data-stu-id="55a6c-128">For more information, see [Diagnosing System Failures with Crash Analyzer](diagnosing-system-failures-with-crash-analyzer--dart-7.md).</span></span>

## <span data-ttu-id="55a6c-129">相关主题</span><span class="sxs-lookup"><span data-stu-id="55a6c-129">Related topics</span></span>


[<span data-ttu-id="55a6c-130">计划部署 DaRT 7.0</span><span class="sxs-lookup"><span data-stu-id="55a6c-130">Planning to Deploy DaRT 7.0</span></span>](planning-to-deploy-dart-70.md)

 

 





