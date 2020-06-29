---
title: 如何在最终用户计算机以外的计算机上以独立模式运行故障分析器
description: 如何在最终用户计算机以外的计算机上以独立模式运行故障分析器
author: dansimp
ms.assetid: 881d573f-2f18-4c5f-838e-2f5320179f94
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6f398c56b7c631145388541b71229d69c16bf6f3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803238"
---
# <span data-ttu-id="0cc7e-103">如何在最终用户计算机以外的计算机上以独立模式运行故障分析器</span><span class="sxs-lookup"><span data-stu-id="0cc7e-103">How to Run the Crash Analyzer in Stand-alone Mode on a Computer Other than an End-user Computer</span></span>


<span data-ttu-id="0cc7e-104">如果无法访问 Microsoft 调试工具 for Windows 或最终用户计算机上的符号文件，则可以从有问题的计算机复制转储文件，并将其分析到安装了独立版本的崩溃分析器（如帮助台管理员的计算机）的计算机上。</span><span class="sxs-lookup"><span data-stu-id="0cc7e-104">If you cannot access the Microsoft Debugging Tools for Windows or the symbol files on the end-user computer, you can copy the dump file from the problem computer and analyze it on a computer that has the stand-alone version of Crash Analyzer installed, such as a helpdesk administrator’s computer.</span></span>

**<span data-ttu-id="0cc7e-105">以独立模式运行崩溃分析器</span><span class="sxs-lookup"><span data-stu-id="0cc7e-105">To run the Crash Analyzer in stand-alone mode</span></span>**

1.  <span data-ttu-id="0cc7e-106">在安装了 DaRT7 的计算机上，单击 "**启动**  /  **All Programs**  /  **Microsoft DaRT 7**中的所有程序"。</span><span class="sxs-lookup"><span data-stu-id="0cc7e-106">On a computer with DaRT7 installed, click **Start** / **All Programs** / **Microsoft DaRT 7**.</span></span>

2.  <span data-ttu-id="0cc7e-107">提供以下内容所需的信息：</span><span class="sxs-lookup"><span data-stu-id="0cc7e-107">Provide the required information for the following:</span></span>

    -   <span data-ttu-id="0cc7e-108">适用于 Windows 的 Microsoft 调试工具</span><span class="sxs-lookup"><span data-stu-id="0cc7e-108">Microsoft Debugging Tools for Windows</span></span>

    -   <span data-ttu-id="0cc7e-109">符号文件</span><span class="sxs-lookup"><span data-stu-id="0cc7e-109">Symbol files</span></span>

        <span data-ttu-id="0cc7e-110">有关符号文件的详细信息，请参阅[如何确保崩溃分析器可以访问符号文件](how-to-ensure-that-crash-analyzer-can-access-symbol-files-dart-7.md)。</span><span class="sxs-lookup"><span data-stu-id="0cc7e-110">For more information about symbol files, see, [How to Ensure that Crash Analyzer Can Access Symbol Files](how-to-ensure-that-crash-analyzer-can-access-symbol-files-dart-7.md).</span></span>

    -   <span data-ttu-id="0cc7e-111">故障转储文件</span><span class="sxs-lookup"><span data-stu-id="0cc7e-111">A crash dump file</span></span>

        <span data-ttu-id="0cc7e-112">**注意** 使用 DaRT7 中的搜索工具查找复制的故障转储文件。</span><span class="sxs-lookup"><span data-stu-id="0cc7e-112">**Note** Use the Search tool in DaRT7 to locate the copied crash dump file.</span></span>

         

3.  <span data-ttu-id="0cc7e-113">**崩溃分析器**将扫描故障转储文件，并报告崩溃的可能原因。</span><span class="sxs-lookup"><span data-stu-id="0cc7e-113">The **Crash Analyzer** scans the crash dump file and reports a probable cause of the crash.</span></span> <span data-ttu-id="0cc7e-114">你可以查看有关崩溃的详细信息，如特定的崩溃消息和说明、在崩溃时加载的驱动程序以及分析的完整输出。</span><span class="sxs-lookup"><span data-stu-id="0cc7e-114">You can view more information about the crash, such as the specific crash message and description, the drivers loaded at the time of the crash, and the full output of the analysis.</span></span>

4.  <span data-ttu-id="0cc7e-115">确定合适的策略来解决该问题。</span><span class="sxs-lookup"><span data-stu-id="0cc7e-115">Decide upon an appropriate strategy to resolve the problem.</span></span> <span data-ttu-id="0cc7e-116">这可能需要通过使用 DaRT 中**计算机管理**工具的 "**服务和驱动程序**" 节点禁用或更新导致崩溃的设备驱动程序。</span><span class="sxs-lookup"><span data-stu-id="0cc7e-116">This may require disabling or updating the device driver that caused the crash by using the **Services and Drivers** node of the **Computer Management** tool in DaRT.</span></span>

## <span data-ttu-id="0cc7e-117">相关主题</span><span class="sxs-lookup"><span data-stu-id="0cc7e-117">Related topics</span></span>


[<span data-ttu-id="0cc7e-118">使用故障分析器诊断系统故障</span><span class="sxs-lookup"><span data-stu-id="0cc7e-118">Diagnosing System Failures with Crash Analyzer</span></span>](diagnosing-system-failures-with-crash-analyzer--dart-7.md)

 

 





