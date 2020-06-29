---
title: 系统使用率报告
description: 系统使用率报告
author: dansimp
ms.assetid: 4d490d15-2d1f-4f2c-99bb-0685447c0672
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fe7ff547d969c63ace234104c3e6b7146da2c113
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798734"
---
# <span data-ttu-id="ed42c-103">系统使用率报告</span><span class="sxs-lookup"><span data-stu-id="ed42c-103">System Utilization Report</span></span>


<span data-ttu-id="ed42c-104">使用 "系统使用率" 报表来绘制每日总系统使用率。</span><span class="sxs-lookup"><span data-stu-id="ed42c-104">Use the System Utilization Report to graph the total daily system usage.</span></span> <span data-ttu-id="ed42c-105">你可以使用此报表确定你的应用程序虚拟化系统上的负载。</span><span class="sxs-lookup"><span data-stu-id="ed42c-105">You can use this report to determine the load on your Application Virtualization System.</span></span>

<span data-ttu-id="ed42c-106">此报告跟踪在指定服务器或服务器组的报告期间的时间段内的使用情况。</span><span class="sxs-lookup"><span data-stu-id="ed42c-106">This report tracks the usage over time during the reporting period for the specified server or for the server group.</span></span>

<span data-ttu-id="ed42c-107">"系统使用率" 报表还将图形为以下系统用法：</span><span class="sxs-lookup"><span data-stu-id="ed42c-107">The System Utilization Report also graphs the following system usage:</span></span>

-   <span data-ttu-id="ed42c-108">按周的某一天的使用情况</span><span class="sxs-lookup"><span data-stu-id="ed42c-108">Usage by day of the week</span></span>

-   <span data-ttu-id="ed42c-109">按天的小时使用</span><span class="sxs-lookup"><span data-stu-id="ed42c-109">Usage by hour of the day</span></span>

<span data-ttu-id="ed42c-110">"系统使用率" 报表还包括特定用户的总系统使用率和总会话计数的摘要。</span><span class="sxs-lookup"><span data-stu-id="ed42c-110">The System Utilization Report also includes a summary of the total system usage for specific users and total session counts.</span></span>

<span data-ttu-id="ed42c-111">创建报表时，指定报表运行时用于收集数据的参数。</span><span class="sxs-lookup"><span data-stu-id="ed42c-111">When you create a report, you specify the parameters that are used for collecting the data when the report is run.</span></span>

<span data-ttu-id="ed42c-112">报表不会自动运行;必须显式运行它们才能生成输出数据。</span><span class="sxs-lookup"><span data-stu-id="ed42c-112">Reports are not run automatically; you must run them explicitly to generate output data.</span></span> <span data-ttu-id="ed42c-113">运行此报告所需的时间长度由数据存储中收集的数据量决定。</span><span class="sxs-lookup"><span data-stu-id="ed42c-113">The length of time it takes to run this report is determined by the amount of data collected in the data store.</span></span>

<span data-ttu-id="ed42c-114">运行报表并在应用程序虚拟化服务器管理控制台中显示输出后，您可以将报表导出为以下格式：</span><span class="sxs-lookup"><span data-stu-id="ed42c-114">After you run a report and the output is displayed in the Application Virtualization Server Management Console, you can export the report into the following formats:</span></span>

-   <span data-ttu-id="ed42c-115">Adobe Acrobat （PDF）</span><span class="sxs-lookup"><span data-stu-id="ed42c-115">Adobe Acrobat (PDF)</span></span>

-   <span data-ttu-id="ed42c-116">Microsoft Office Excel</span><span class="sxs-lookup"><span data-stu-id="ed42c-116">Microsoft Office Excel</span></span>

<span data-ttu-id="ed42c-117">**注意** 从客户端报告的 app-v 服务器名称必须是默认服务器组的一部分，才能使 "系统使用率" 报表显示数据。</span><span class="sxs-lookup"><span data-stu-id="ed42c-117">**Note** The App-V server name reported from the clients must be part of the Default Server Group in order for the System Utilization report to show data.</span></span> <span data-ttu-id="ed42c-118">例如，如果你将多台服务器与网络负载平衡器（NLB）配合使用，则必须将 NLB 群集名称添加到默认服务器组。</span><span class="sxs-lookup"><span data-stu-id="ed42c-118">For example, if you are using multiple servers with a Network Load Balancer (NLB), you must add the NLB cluster name to the Default Server Group.</span></span>

 

## <span data-ttu-id="ed42c-119">相关主题</span><span class="sxs-lookup"><span data-stu-id="ed42c-119">Related topics</span></span>


[<span data-ttu-id="ed42c-120">如何创建报告</span><span class="sxs-lookup"><span data-stu-id="ed42c-120">How to Create a Report</span></span>](how-to-create-a-reportserver.md)

[<span data-ttu-id="ed42c-121">如何删除报告</span><span class="sxs-lookup"><span data-stu-id="ed42c-121">How to Delete a Report</span></span>](how-to-delete-a-reportserver.md)

[<span data-ttu-id="ed42c-122">如何导出报告</span><span class="sxs-lookup"><span data-stu-id="ed42c-122">How to Export a Report</span></span>](how-to-export-a-reportserver.md)

[<span data-ttu-id="ed42c-123">如何打印报告</span><span class="sxs-lookup"><span data-stu-id="ed42c-123">How to Print a Report</span></span>](how-to-print-a-reportserver.md)

[<span data-ttu-id="ed42c-124">如何运行报告</span><span class="sxs-lookup"><span data-stu-id="ed42c-124">How to Run a Report</span></span>](how-to-run-a-reportserver.md)

 

 





