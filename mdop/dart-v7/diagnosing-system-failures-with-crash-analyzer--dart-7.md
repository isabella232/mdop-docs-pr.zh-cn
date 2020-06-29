---
title: 使用故障分析器诊断系统故障
description: 使用故障分析器诊断系统故障
author: dansimp
ms.assetid: 170d40ef-4edb-4a32-a349-c285c0ea5e56
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3c5f8b7e189de024d7ceb84f8cfc151dc82d56ed
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803374"
---
# <span data-ttu-id="1790a-103">使用故障分析器诊断系统故障</span><span class="sxs-lookup"><span data-stu-id="1790a-103">Diagnosing System Failures with Crash Analyzer</span></span>


<span data-ttu-id="1790a-104">Microsoft Diagnostics 和恢复工具套件（DaRT）7中的崩溃分析器使你能够在基于 Windows 的计算机上调试故障转储文件，然后诊断任何相关的计算机错误。</span><span class="sxs-lookup"><span data-stu-id="1790a-104">The Crash Analyzer in Microsoft Diagnostics and Recovery Toolset (DaRT)7 lets you debug a crash dump file on a Windows-based computer and then diagnose any related computer errors.</span></span> <span data-ttu-id="1790a-105">崩溃分析器使用 Microsoft 调试工具 for Windows 检查导致计算机失败的驱动程序的故障转储文件。</span><span class="sxs-lookup"><span data-stu-id="1790a-105">The Crash Analyzer uses the Microsoft Debugging Tools for Windows to examine a crash dump file for the driver that caused the computer to fail.</span></span>

## <span data-ttu-id="1790a-106">在最终用户计算机上运行崩溃分析器</span><span class="sxs-lookup"><span data-stu-id="1790a-106">Run the Crash Analyzer on an End-user Computer</span></span>


<span data-ttu-id="1790a-107">通常，你可以从出现问题的最终用户计算机上的 "诊断和恢复工具集" 窗口中运行崩溃分析器。</span><span class="sxs-lookup"><span data-stu-id="1790a-107">Typically, you run Crash Analyzer from the Diagnostics and Recovery Toolset window on an end-user computer that has problems.</span></span> <span data-ttu-id="1790a-108">故障分析器将尝试在有问题的计算机上查找 Windows 的调试工具。</span><span class="sxs-lookup"><span data-stu-id="1790a-108">The Crash Analyzer tries to locate the Debugging Tools for Windows on the problem computer.</span></span> <span data-ttu-id="1790a-109">如果 "目录路径" 对话框为空，则必须输入位置或浏览到 Windows 调试工具的位置（可以从 Microsoft 下载文件）。</span><span class="sxs-lookup"><span data-stu-id="1790a-109">If the directory path dialog box is empty, you must enter the location or browse to the location of the Debugging Tools for Windows (you can download the files from Microsoft).</span></span> <span data-ttu-id="1790a-110">你还必须提供指向符号文件所在位置的路径。</span><span class="sxs-lookup"><span data-stu-id="1790a-110">You must also provide a path to where the symbol files are located.</span></span>

<span data-ttu-id="1790a-111">如果你在创建 DaRT 恢复映像时包含适用于 Windows 的 Microsoft 调试工具和符号文件，则当你在有问题的计算机上运行崩溃分析器时，它们应该可用。</span><span class="sxs-lookup"><span data-stu-id="1790a-111">If you included the Microsoft Debugging Tools for Windows and the symbol files when you created the DaRT recovery image, they should be available when you run the Crash Analyzer on the problem computer.</span></span>

[<span data-ttu-id="1790a-112">如何在最终用户计算机上运行故障分析器</span><span class="sxs-lookup"><span data-stu-id="1790a-112">How to Run the Crash Analyzer on an End-user Computer</span></span>](how-to-run-the-crash-analyzer-on-an-end-user-computer-dart-7.md)

## <span data-ttu-id="1790a-113">在除最终用户计算机之外的计算机上以独立模式运行崩溃分析器</span><span class="sxs-lookup"><span data-stu-id="1790a-113">Run the Crash Analyzer in stand-alone mode on a computer other than an end-user computer</span></span>


<span data-ttu-id="1790a-114">故障分析器将尝试在有问题的计算机上查找 Windows 的调试工具。</span><span class="sxs-lookup"><span data-stu-id="1790a-114">The Crash Analyzer tries to locate the Debugging Tools for Windows on the problem computer.</span></span> <span data-ttu-id="1790a-115">如果 "目录路径" 对话框为空，则必须输入位置或浏览到 Windows 调试工具的位置（可以从 Microsoft 下载文件）。</span><span class="sxs-lookup"><span data-stu-id="1790a-115">If the directory path dialog box is empty, you must enter the location or browse to the location of the Debugging Tools for Windows (you can download the files from Microsoft).</span></span> <span data-ttu-id="1790a-116">你还必须提供指向符号文件所在位置的路径。</span><span class="sxs-lookup"><span data-stu-id="1790a-116">You must also provide a path to where the symbol files are located.</span></span>

<span data-ttu-id="1790a-117">如果你在创建 DaRT 恢复映像时未包含适用于 Windows 和符号文件的 Microsoft 调试工具，或者如果磁盘大小或网络连接问题阻止你获取它们，则可以从有问题的计算机复制转储文件，并将其分析到安装了独立版本的崩溃分析程序的计算机上，如帮助台管理员的计算机。</span><span class="sxs-lookup"><span data-stu-id="1790a-117">If you did not include the Microsoft Debugging Tools for Windows and the symbol files when you created the DaRT recovery image, or if disk size or network connectivity problems are preventing you from obtaining them, then you can copy the dump file from the problem computer and analyze it on a computer that has the stand-alone version of Crash Analyzer installed, such as a helpdesk administrator’s computer.</span></span>

[<span data-ttu-id="1790a-118">如何在最终用户计算机以外的计算机上以独立模式运行故障分析器</span><span class="sxs-lookup"><span data-stu-id="1790a-118">How to Run the Crash Analyzer in Stand-alone Mode on a Computer Other than an End-user Computer</span></span>](how-to-run-the-crash-analyzer-in-stand-alone-mode-on-a-computer-other-than-an-end-user-computer-dart-7.md)

## <span data-ttu-id="1790a-119">确保崩溃分析器可以访问符号文件</span><span class="sxs-lookup"><span data-stu-id="1790a-119">Ensure that Crash Analyzer can access symbol files</span></span>


<span data-ttu-id="1790a-120">通常，调试信息存储在与可执行文件不同的符号文件中。</span><span class="sxs-lookup"><span data-stu-id="1790a-120">Typically, debugging information is stored in a symbol file that is separate from the executable.</span></span> <span data-ttu-id="1790a-121">当你调试已停止响应的应用程序时（例如，如果该应用程序崩溃），你必须具有访问符号信息的权限。</span><span class="sxs-lookup"><span data-stu-id="1790a-121">You must have access to the symbol information when you debug an application that has stopped responding, for example if it crashed.</span></span>

<span data-ttu-id="1790a-122">当运行崩溃分析器时，将自动下载符号文件。</span><span class="sxs-lookup"><span data-stu-id="1790a-122">Symbol files are automatically downloaded when you run Crash Analyzer.</span></span> <span data-ttu-id="1790a-123">如果计算机没有 Internet 连接或网络要求计算机访问 HTTP 代理服务器，则无法下载符号文件。</span><span class="sxs-lookup"><span data-stu-id="1790a-123">If the computer does not have an Internet connection or the network requires the computer to access an HTTP proxy server, the symbol files cannot be downloaded.</span></span>

[<span data-ttu-id="1790a-124">如何确保故障分析器可以访问符号文件</span><span class="sxs-lookup"><span data-stu-id="1790a-124">How to Ensure that Crash Analyzer Can Access Symbol Files</span></span>](how-to-ensure-that-crash-analyzer-can-access-symbol-files-dart-7.md)

## <span data-ttu-id="1790a-125">用于诊断故障分析器的系统故障的其他资源</span><span class="sxs-lookup"><span data-stu-id="1790a-125">Other resources for diagnosing system failures with Crash Analyzer</span></span>


[<span data-ttu-id="1790a-126">DaRT 7.0 的操作</span><span class="sxs-lookup"><span data-stu-id="1790a-126">Operations for DaRT 7.0</span></span>](operations-for-dart-70-new-ia.md)

 

 





