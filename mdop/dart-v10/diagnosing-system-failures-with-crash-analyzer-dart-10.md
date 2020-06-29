---
title: 使用故障分析器诊断系统故障
description: 使用故障分析器诊断系统故障
author: dansimp
ms.assetid: 7ebef49e-a294-4173-adb1-7e6994aa01ad
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7d0f4b71bf267d65ec53dd1b3e23fd8a59190b0b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798213"
---
# <span data-ttu-id="4302b-103">使用故障分析器诊断系统故障</span><span class="sxs-lookup"><span data-stu-id="4302b-103">Diagnosing System Failures with Crash Analyzer</span></span>


<span data-ttu-id="4302b-104">Microsoft 诊断和恢复工具套件（DaRT）10中的**崩溃分析器**允许你在基于 Windows 的计算机上调试内存转储文件，然后诊断任何相关的计算机错误。</span><span class="sxs-lookup"><span data-stu-id="4302b-104">The **Crash Analyzer** in Microsoft Diagnostics and Recovery Toolset (DaRT) 10 lets you debug a memory dump file on a Windows-based computer and then diagnose any related computer errors.</span></span> <span data-ttu-id="4302b-105">**崩溃分析器**使用 Microsoft 调试工具 for Windows 检查导致计算机失败的驱动程序的内存转储文件。</span><span class="sxs-lookup"><span data-stu-id="4302b-105">The **Crash Analyzer** uses the Microsoft Debugging Tools for Windows to examine a memory dump file for the driver that caused the computer to fail.</span></span> <span data-ttu-id="4302b-106">你可以在终端用户计算机上或在非最终用户计算机之外的计算机上运行崩溃分析器。</span><span class="sxs-lookup"><span data-stu-id="4302b-106">You can run the Crash Analyzer on an end-user computer or in stand-alone mode on a computer other than an end-user computer.</span></span>

## <span data-ttu-id="4302b-107">在最终用户计算机上运行崩溃分析器</span><span class="sxs-lookup"><span data-stu-id="4302b-107">Run the Crash Analyzer on an end-user-computer</span></span>


<span data-ttu-id="4302b-108">通常，你可以从遇到问题的最终用户计算机上的 "**诊断和恢复工具集**" 窗口中运行**崩溃分析器**。</span><span class="sxs-lookup"><span data-stu-id="4302b-108">Typically, you run **Crash Analyzer** from the **Diagnostics and Recovery Toolset** window on an end-user computer that is experiencing the problem.</span></span> <span data-ttu-id="4302b-109">**故障分析器**将尝试在有问题的计算机上查找 Windows 的调试工具。</span><span class="sxs-lookup"><span data-stu-id="4302b-109">The **Crash Analyzer** tries to locate the Debugging Tools for Windows on the problem computer.</span></span> <span data-ttu-id="4302b-110">如果 "目录路径" 对话框为空，则必须输入位置，或浏览到 Windows 调试工具的位置（可以从 Microsoft 下载文件）。</span><span class="sxs-lookup"><span data-stu-id="4302b-110">If the directory path dialog box is empty, you must enter the location, or browse to the location of the Debugging Tools for Windows (you can download the files from Microsoft).</span></span> <span data-ttu-id="4302b-111">你还必须提供指向符号文件所在位置的路径。</span><span class="sxs-lookup"><span data-stu-id="4302b-111">You must also provide a path to where the symbol files are located.</span></span>

<span data-ttu-id="4302b-112">如果你在创建 DaRT 10 恢复映像时包含适用于 Windows 和符号文件的 Microsoft 调试工具和符号文件，则当你在问题计算机上运行**崩溃分析器**时，工具和符号文件应该可用。</span><span class="sxs-lookup"><span data-stu-id="4302b-112">If you included the Microsoft Debugging Tools for Windows and the symbol files when you created the DaRT 10 recovery image, the Tools and symbol files should be available when you run the **Crash Analyzer** on the problem computer.</span></span> <span data-ttu-id="4302b-113">如果你未将它们包含在 DaRT 恢复映像中，或者如果磁盘大小或网络连接问题阻止你获取它们，你也可以在除最终用户计算机之外的计算机上以独立模式运行崩溃分析器，如下部分所述。</span><span class="sxs-lookup"><span data-stu-id="4302b-113">If you did not include them in the DaRT recovery image, or if disk size or network connectivity problems are preventing you from obtaining them, you can alternatively run the Crash Analyzer in stand-alone mode on a computer other than the end user’s computer, as described in the following section.</span></span>

[<span data-ttu-id="4302b-114">如何在最终用户计算机上运行故障分析器</span><span class="sxs-lookup"><span data-stu-id="4302b-114">How to Run the Crash Analyzer on an End-user Computer</span></span>](how-to-run-the-crash-analyzer-on-an-end-user-computer-dart-10.md)

## <a href="" id="run-the-crash-analyzer-in-stand-alone-mode-on-a-computer-other-than-an-end-user-s-computer"></a><span data-ttu-id="4302b-115">在除最终用户的计算机之外的计算机上以独立模式运行崩溃分析器</span><span class="sxs-lookup"><span data-stu-id="4302b-115">Run the Crash Analyzer in stand-alone mode on a computer other than an end user’s computer</span></span>


<span data-ttu-id="4302b-116">尽管你通常在遇到问题的最终用户计算机上运行**崩溃分析**程序，但你也可以在独立模式下运行崩溃分析器，而不是最终用户的计算机。</span><span class="sxs-lookup"><span data-stu-id="4302b-116">Although you typically run **Crash Analyzer** on the end-user computer that is experiencing the problem, you can also run the Crash Analyzer in stand-alone mode, on a computer other than an end-user computer.</span></span> <span data-ttu-id="4302b-117">如果你未在 DaRT 恢复映像中包含 Windows 调试工具，或者当磁盘大小或网络连接问题阻止你获取调试工具时，你可以选择此选项。</span><span class="sxs-lookup"><span data-stu-id="4302b-117">You might choose this option if you did not include the Windows Debugging Tools in the DaRT recovery image, or if disk size or network connectivity problems are preventing you from obtaining the Debugging Tools.</span></span> <span data-ttu-id="4302b-118">在这种情况下，你可以从有问题的计算机复制转储文件，并将其分析到安装了独立版本的**崩溃分析器**的计算机上，例如在技术支持代理的计算机上。</span><span class="sxs-lookup"><span data-stu-id="4302b-118">In this case, you can copy the dump file from the problem computer and analyze it on a computer that has the stand-alone version of **Crash Analyzer** installed, such as on a help desk agent’s computer.</span></span>

[<span data-ttu-id="4302b-119">如何在最终用户计算机以外的计算机上以独立模式运行故障分析器</span><span class="sxs-lookup"><span data-stu-id="4302b-119">How to Run the Crash Analyzer in Stand-alone Mode on a Computer Other than an End-user Computer</span></span>](how-to-run-the-crash-analyzer-in-stand-alone-mode-on-a-computer-other-than-an-end-user-computer-dart-10.md)

## <span data-ttu-id="4302b-120">如何确保崩溃分析器可以访问符号文件</span><span class="sxs-lookup"><span data-stu-id="4302b-120">How to ensure that Crash Analyzer can access symbol files</span></span>


<span data-ttu-id="4302b-121">若要调试已停止响应的应用程序，您需要访问符号文件，该文件与程序分开。</span><span class="sxs-lookup"><span data-stu-id="4302b-121">To debug applications that have stopped responding, you need access to the symbol file, which is separate from the program.</span></span> <span data-ttu-id="4302b-122">尽管在运行崩溃分析器时将自动下载符号文件，但有时问题计算机无法访问 Internet。</span><span class="sxs-lookup"><span data-stu-id="4302b-122">Although symbol files are automatically downloaded when you run Crash Analyzer, there might be times when the problem computer does not have access to the Internet.</span></span> <span data-ttu-id="4302b-123">有多种方法可确保您有权访问符号文件。</span><span class="sxs-lookup"><span data-stu-id="4302b-123">There are several ways to ensure that you have guaranteed access to symbol files.</span></span>

[<span data-ttu-id="4302b-124">如何确保故障分析器可以访问符号文件</span><span class="sxs-lookup"><span data-stu-id="4302b-124">How to Ensure that Crash Analyzer Can Access Symbol Files</span></span>](how-to-ensure-that-crash-analyzer-can-access-symbol-files-dart-10.md)

## <span data-ttu-id="4302b-125">用于诊断故障分析器的系统故障的其他资源</span><span class="sxs-lookup"><span data-stu-id="4302b-125">Other resources for diagnosing system failures with Crash Analyzer</span></span>


[<span data-ttu-id="4302b-126">DaRT 10 的操作</span><span class="sxs-lookup"><span data-stu-id="4302b-126">Operations for DaRT 10</span></span>](operations-for-dart-10.md)

 

 





