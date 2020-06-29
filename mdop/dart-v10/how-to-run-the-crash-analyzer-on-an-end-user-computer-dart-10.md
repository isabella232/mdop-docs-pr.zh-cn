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
# <span data-ttu-id="e8b11-103">如何在最终用户计算机上运行故障分析器</span><span class="sxs-lookup"><span data-stu-id="e8b11-103">How to Run the Crash Analyzer on an End-user Computer</span></span>


<span data-ttu-id="e8b11-104">若要从遇到问题的最终用户计算机上的 "**诊断和恢复工具集**" 窗口中运行**崩溃分析器**，必须具有 Windows 的 Microsoft 调试工具和所安装的符号文件。</span><span class="sxs-lookup"><span data-stu-id="e8b11-104">To run **Crash Analyzer** from the **Diagnostics and Recovery Toolset** window on an end-user computer that is experiencing problems, you must have the Microsoft Debugging Tools for Windows and the symbol files installed.</span></span> <span data-ttu-id="e8b11-105">若要下载 Windows 调试工具，请参阅[Windows 调试工具](https://go.microsoft.com/fwlink/?LinkId=266248)。</span><span class="sxs-lookup"><span data-stu-id="e8b11-105">To download the Windows Debugging Tools, see [Debugging Tools for Windows](https://go.microsoft.com/fwlink/?LinkId=266248).</span></span>

**<span data-ttu-id="e8b11-106">在最终用户计算机上运行崩溃分析器</span><span class="sxs-lookup"><span data-stu-id="e8b11-106">To run the Crash Analyzer on an end-user computer</span></span>**

1.  <span data-ttu-id="e8b11-107">在最终用户计算机上的 "**诊断和恢复工具集**" 窗口中，单击 "**崩溃分析器**"。</span><span class="sxs-lookup"><span data-stu-id="e8b11-107">On the **Diagnostics and Recovery Toolset** window on an end-user computer, click **Crash Analyzer**.</span></span>

2.  <span data-ttu-id="e8b11-108">提供适用于 Windows 的 Microsoft 调试工具所需的信息。</span><span class="sxs-lookup"><span data-stu-id="e8b11-108">Provide the required information for the Microsoft Debugging Tools for Windows.</span></span>

3.  <span data-ttu-id="e8b11-109">提供符号文件所需的信息。</span><span class="sxs-lookup"><span data-stu-id="e8b11-109">Provide the required information for the symbol files.</span></span> <span data-ttu-id="e8b11-110">有关符号文件的详细信息，请参阅[如何确保崩溃分析器可以访问符号文件](how-to-ensure-that-crash-analyzer-can-access-symbol-files-dart-10.md)。</span><span class="sxs-lookup"><span data-stu-id="e8b11-110">For more information about symbol files, see [How to Ensure that Crash Analyzer Can Access Symbol Files](how-to-ensure-that-crash-analyzer-can-access-symbol-files-dart-10.md).</span></span>

4.  <span data-ttu-id="e8b11-111">提供内存转储文件所需的信息。</span><span class="sxs-lookup"><span data-stu-id="e8b11-111">Provide the required information for a memory dump file.</span></span> <span data-ttu-id="e8b11-112">要确定内存转储文件的位置，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e8b11-112">To determine the location of the memory dump file:</span></span>

    1.  <span data-ttu-id="e8b11-113">打开 "**系统属性**" 窗口。</span><span class="sxs-lookup"><span data-stu-id="e8b11-113">Open the **System Properties** window.</span></span>

    2.  <span data-ttu-id="e8b11-114">单击 "**开始**"，键入**sysdm.cpl**，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="e8b11-114">Click **Start**, type **sysdm.cpl**, and then press **Enter**.</span></span>

    3.  <span data-ttu-id="e8b11-115">单击**高级**选项卡。</span><span class="sxs-lookup"><span data-stu-id="e8b11-115">Click the **Advanced** tab.</span></span>

    4.  <span data-ttu-id="e8b11-116">在 "**启动和故障恢复**" 区域中，单击 "**设置**"。</span><span class="sxs-lookup"><span data-stu-id="e8b11-116">In the **Startup and Recovery** area, click **Settings**.</span></span>

        <span data-ttu-id="e8b11-117">如果你无法访问 "**系统属性**" 窗口，则可以使用 Microsoft 诊断和恢复工具集（DaRT）10中的**搜索**工具在最终用户计算机上搜索转储文件。</span><span class="sxs-lookup"><span data-stu-id="e8b11-117">If you do not have access to the **System Properties** window, you can search for dump files on the end-user computer by using the **Search** tool in Microsoft Diagnostics and Recovery Toolset (DaRT) 10.</span></span>

    <span data-ttu-id="e8b11-118">**崩溃分析器**将扫描内存转储文件，并报告问题的可能原因。</span><span class="sxs-lookup"><span data-stu-id="e8b11-118">The **Crash Analyzer** scans the memory dump file and reports a probable cause of the problem.</span></span> <span data-ttu-id="e8b11-119">你可以查看有关失败的详细信息，如特定内存转储消息和说明、在出现故障时加载的驱动程序以及分析的完整输出。</span><span class="sxs-lookup"><span data-stu-id="e8b11-119">You can view more information about the failure, such as the specific memory dump message and description, the drivers loaded at the time of the failure, and the full output of the analysis.</span></span>

5.  <span data-ttu-id="e8b11-120">确定解决问题的相应策略。</span><span class="sxs-lookup"><span data-stu-id="e8b11-120">Identify the appropriate strategy to resolve the problem.</span></span> <span data-ttu-id="e8b11-121">通过使用 DaRT 10 中**计算机管理**工具的 "**服务和驱动程序**" 节点，策略可能需要禁用或更新导致故障的设备驱动程序。</span><span class="sxs-lookup"><span data-stu-id="e8b11-121">The strategy may require disabling or updating the device driver that caused the failure by using the **Services and Drivers** node of the **Computer Management** tool in DaRT 10.</span></span>

## <span data-ttu-id="e8b11-122">相关主题</span><span class="sxs-lookup"><span data-stu-id="e8b11-122">Related topics</span></span>


[<span data-ttu-id="e8b11-123">使用故障分析器诊断系统故障</span><span class="sxs-lookup"><span data-stu-id="e8b11-123">Diagnosing System Failures with Crash Analyzer</span></span>](diagnosing-system-failures-with-crash-analyzer-dart-10.md)

[<span data-ttu-id="e8b11-124">DaRT 10 的操作</span><span class="sxs-lookup"><span data-stu-id="e8b11-124">Operations for DaRT 10</span></span>](operations-for-dart-10.md)

 

 





