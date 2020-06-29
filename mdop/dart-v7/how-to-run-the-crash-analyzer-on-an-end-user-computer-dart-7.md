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
# <span data-ttu-id="7e603-103">如何在最终用户计算机上运行故障分析器</span><span class="sxs-lookup"><span data-stu-id="7e603-103">How to Run the Crash Analyzer on an End-user Computer</span></span>


<span data-ttu-id="7e603-104">通常，你可以从遇到问题的最终用户计算机上的诊断和恢复工具集窗口中运行 Microsoft 诊断和恢复工具集（DaRT）7故障分析器。</span><span class="sxs-lookup"><span data-stu-id="7e603-104">Typically, you run Microsoft Diagnostics and Recovery Toolset (DaRT)7 Crash Analyzer from the Diagnostics and Recovery Toolset window on an end-user computer that has problems.</span></span> <span data-ttu-id="7e603-105">故障分析器将尝试在有问题的计算机上查找 Windows 的调试工具。</span><span class="sxs-lookup"><span data-stu-id="7e603-105">The Crash Analyzer tries to locate the Debugging Tools for Windows on the problem computer.</span></span> <span data-ttu-id="7e603-106">如果 "目录路径" 对话框为空，则必须输入位置或浏览到 Windows 调试工具的位置（可以从 Microsoft 下载文件）。</span><span class="sxs-lookup"><span data-stu-id="7e603-106">If the directory path dialog box is empty, you must enter the location or browse to the location of the Debugging Tools for Windows (you can download the files from Microsoft).</span></span> <span data-ttu-id="7e603-107">你还必须提供指向符号文件所在位置的路径。</span><span class="sxs-lookup"><span data-stu-id="7e603-107">You must also provide a path to where the symbol files are located.</span></span>

**<span data-ttu-id="7e603-108">在最终用户计算机上打开并运行崩溃分析器</span><span class="sxs-lookup"><span data-stu-id="7e603-108">To open and run the Crash Analyzer on an end-user computer</span></span>**

1.  <span data-ttu-id="7e603-109">在最终用户计算机上的 "**诊断和恢复工具集**" 窗口中，单击 "**崩溃分析器**"。</span><span class="sxs-lookup"><span data-stu-id="7e603-109">On the **Diagnostics and Recovery Toolset** window on an end-user computer, click **Crash Analyzer**.</span></span>

2.  <span data-ttu-id="7e603-110">提供以下内容所需的信息：</span><span class="sxs-lookup"><span data-stu-id="7e603-110">Provide the required information for the following:</span></span>

    -   <span data-ttu-id="7e603-111">适用于 Windows 的 Microsoft 调试工具</span><span class="sxs-lookup"><span data-stu-id="7e603-111">Microsoft Debugging Tools for Windows</span></span>

    -   <span data-ttu-id="7e603-112">符号文件</span><span class="sxs-lookup"><span data-stu-id="7e603-112">Symbol files</span></span>

        <span data-ttu-id="7e603-113">有关符号文件的详细信息，请参阅[如何确保崩溃分析器可以访问符号文件](how-to-ensure-that-crash-analyzer-can-access-symbol-files-dart-7.md)。</span><span class="sxs-lookup"><span data-stu-id="7e603-113">For more information about symbol files, see, [How to Ensure that Crash Analyzer Can Access Symbol Files](how-to-ensure-that-crash-analyzer-can-access-symbol-files-dart-7.md).</span></span>

    -   <span data-ttu-id="7e603-114">故障转储文件</span><span class="sxs-lookup"><span data-stu-id="7e603-114">A crash dump file</span></span>

        <span data-ttu-id="7e603-115">按照以下步骤确定故障转储文件的位置：</span><span class="sxs-lookup"><span data-stu-id="7e603-115">Follow these steps to determine the location of the crash dump file:</span></span>

        1.  <span data-ttu-id="7e603-116">打开 "**系统属性**" 窗口。</span><span class="sxs-lookup"><span data-stu-id="7e603-116">Open the **System Properties** window.</span></span>

            <span data-ttu-id="7e603-117">单击 "**开始**"，键入 sysdm.cpl，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="7e603-117">Click **Start**, type sysdm.cpl, and then press Enter.</span></span>

        2.  <span data-ttu-id="7e603-118">单击**高级**选项卡。</span><span class="sxs-lookup"><span data-stu-id="7e603-118">Click the **Advanced** tab.</span></span>

        3.  <span data-ttu-id="7e603-119">在 "**启动和故障恢复**" 区域中，单击 "**设置**"。</span><span class="sxs-lookup"><span data-stu-id="7e603-119">In the **Startup and Recovery** area, click **Settings**.</span></span>

        <span data-ttu-id="7e603-120">**注意** 如果您无法访问 "**系统属性**" 窗口，则可以使用 DaRT 中的**搜索**工具在最终用户计算机上搜索转储文件。</span><span class="sxs-lookup"><span data-stu-id="7e603-120">**Note** If you do not have access to the **System Properties** window, you can search for dump files on the end-user computer by using the **Search** tool in DaRT.</span></span>

         

3.  <span data-ttu-id="7e603-121">**崩溃分析器**将扫描故障转储文件，并报告崩溃的可能原因。</span><span class="sxs-lookup"><span data-stu-id="7e603-121">The **Crash Analyzer** scans the crash dump file and reports a probable cause of the crash.</span></span> <span data-ttu-id="7e603-122">你可以查看有关崩溃的详细信息，如特定的崩溃消息和说明、在崩溃时加载的驱动程序以及分析的完整输出。</span><span class="sxs-lookup"><span data-stu-id="7e603-122">You can view more information about the crash, such as the specific crash message and description, the drivers loaded at the time of the crash, and the full output of the analysis.</span></span>

4.  <span data-ttu-id="7e603-123">确定合适的策略来解决该问题。</span><span class="sxs-lookup"><span data-stu-id="7e603-123">Decide upon an appropriate strategy to resolve the problem.</span></span> <span data-ttu-id="7e603-124">这可能需要通过使用 DaRT 中**计算机管理**工具的 "**服务和驱动程序**" 节点禁用或更新导致崩溃的设备驱动程序。</span><span class="sxs-lookup"><span data-stu-id="7e603-124">This may require disabling or updating the device driver that caused the crash by using the **Services and Drivers** node of the **Computer Management** tool in DaRT.</span></span>

## <span data-ttu-id="7e603-125">相关主题</span><span class="sxs-lookup"><span data-stu-id="7e603-125">Related topics</span></span>


[<span data-ttu-id="7e603-126">使用故障分析器诊断系统故障</span><span class="sxs-lookup"><span data-stu-id="7e603-126">Diagnosing System Failures with Crash Analyzer</span></span>](diagnosing-system-failures-with-crash-analyzer--dart-7.md)

 

 





