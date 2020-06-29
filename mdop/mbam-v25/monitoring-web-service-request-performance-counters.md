---
title: 监视 Web 服务请求性能计数器
description: 监视 Web 服务请求性能计数器
author: dansimp
ms.assetid: bdb812a1-465a-4098-b4c0-cb99890d1b0d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 2db96e3375562b48d289ea5a21dc7e89b800d1ad
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803456"
---
# <span data-ttu-id="165e5-103">监视 Web 服务请求性能计数器</span><span class="sxs-lookup"><span data-stu-id="165e5-103">Monitoring Web Service Request Performance Counters</span></span>


<span data-ttu-id="165e5-104">Microsoft BitLocker 管理和监视（MBAM）提供的性能计数器记录发送到以下 web 服务的请求的性能：</span><span class="sxs-lookup"><span data-stu-id="165e5-104">Microsoft BitLocker Administration and Monitoring (MBAM) provides performance counters that record the performance of requests that are sent to the following web services:</span></span>

-   <span data-ttu-id="165e5-105">**StatusReportingService** –接收合规性状态请求的服务</span><span class="sxs-lookup"><span data-stu-id="165e5-105">**StatusReportingService.svc** – service that receives requests for compliance status</span></span>

-   <span data-ttu-id="165e5-106">**CoreService** –接收对密钥恢复尝试的请求的服务</span><span class="sxs-lookup"><span data-stu-id="165e5-106">**CoreService.svc** – service that receives requests for key recovery attempts</span></span>

## <span data-ttu-id="165e5-107">MBAM 提供的性能计数器</span><span class="sxs-lookup"><span data-stu-id="165e5-107">Performance counters that MBAM provides</span></span>


<span data-ttu-id="165e5-108">MBAM 为由其 StatusReportingService 和 CoreService web 服务实现的每个公共方法提供以下性能计数器：</span><span class="sxs-lookup"><span data-stu-id="165e5-108">MBAM provides the following performance counters for each of the public methods that is implemented by its StatusReportingService and CoreService web services:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="165e5-109">性能计数器的类型</span><span class="sxs-lookup"><span data-stu-id="165e5-109">Type of performance counter</span></span></th>
<th align="left"><span data-ttu-id="165e5-110">描述</span><span class="sxs-lookup"><span data-stu-id="165e5-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="165e5-111">请求总数</span><span class="sxs-lookup"><span data-stu-id="165e5-111">Total number of requests</span></span></p></td>
<td align="left"><p><span data-ttu-id="165e5-112">提供启动或重启服务器时从零开始的增量计数。</span><span class="sxs-lookup"><span data-stu-id="165e5-112">Provides an incrementing count that starts from zero when the server is started or restarted.</span></span></p>
<p><span data-ttu-id="165e5-113">提供系统活动的整体视图。</span><span class="sxs-lookup"><span data-stu-id="165e5-113">Provides an overall view of system activity.</span></span> <span data-ttu-id="165e5-114">可通过自动化工具进行监视，以确保服务器的运行状况并验证计数器在指定时间段内持续增加。</span><span class="sxs-lookup"><span data-stu-id="165e5-114">Can be monitored by automated tools to ensure the health of the server and to validate that the counter continually increments over a specified period of time.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="165e5-115">每秒请求数</span><span class="sxs-lookup"><span data-stu-id="165e5-115">Requests per second</span></span></p></td>
<td align="left"><p><span data-ttu-id="165e5-116">指示 MBAM 服务器的当前吞吐量，因为它支持 MBAM 客户端基础。</span><span class="sxs-lookup"><span data-stu-id="165e5-116">Indicates the current throughput of the MBAM Server as it supports the MBAM client base.</span></span></p>
<p><span data-ttu-id="165e5-117">使网站管理员能够：</span><span class="sxs-lookup"><span data-stu-id="165e5-117">Enables site administrators to:</span></span></p>
<ul>
<li><p><span data-ttu-id="165e5-118">基于 MBAM 客户端数及其报告频率，计算每秒的平均请求数。</span><span class="sxs-lookup"><span data-stu-id="165e5-118">Calculate the average number of requests per second, based on the number of MBAM Clients and their reporting frequency.</span></span></p></li>
<li><p><span data-ttu-id="165e5-119">验证每秒的请求数是否广泛与计算每秒的平均请求数之和。</span><span class="sxs-lookup"><span data-stu-id="165e5-119">Validate that the number of requests per second broadly correlates with the calculated average number of requests per second.</span></span> <span data-ttu-id="165e5-120">显著的差异可指示 MBAM 客户端未安装在客户端基础的一定百分比或 MBAM 组策略对象未成功部署。</span><span class="sxs-lookup"><span data-stu-id="165e5-120">A significant variance can indicate that the MBAM Client isn't installed on a percentage of the client base or that an MBAM Group Policy Object hasn't been successfully deployed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="165e5-121">请求持续时间</span><span class="sxs-lookup"><span data-stu-id="165e5-121">Request duration</span></span></p></td>
<td align="left"><p><span data-ttu-id="165e5-122">记录请求的持续时间（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="165e5-122">Records the duration of requests in milliseconds.</span></span></p>
<p><span data-ttu-id="165e5-123">虽然此计数器在每个请求的持续时间内更新，但 Windows 性能监视器仅定期（通常是每秒）对其进行采样，因此你可能会在值中看到一些可变性。</span><span class="sxs-lookup"><span data-stu-id="165e5-123">Although this counter is updated with the duration of each request, Windows Performance Monitor samples it only periodically (typically every second), so you might see some variability in the value.</span></span> <span data-ttu-id="165e5-124">出于此原因，请考虑使用性能监视器显示的平均值。</span><span class="sxs-lookup"><span data-stu-id="165e5-124">For this reason, consider using the average value displayed by Performance Monitor.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="165e5-125">性能计数器结果和建议</span><span class="sxs-lookup"><span data-stu-id="165e5-125">Performance counter results and recommendations</span></span>


<span data-ttu-id="165e5-126">将新的 MBAM 客户添加到具有备用容量的 MBAM 服务器时，预计每秒的请求数会增加。</span><span class="sxs-lookup"><span data-stu-id="165e5-126">As you add new MBAM Clients to an MBAM Server with spare capacity, expect to see an increase in the number of requests per second.</span></span> <span data-ttu-id="165e5-127">此增长将与新客户端计算机的数量成比例。</span><span class="sxs-lookup"><span data-stu-id="165e5-127">This increase will be proportional to the number of new client computers.</span></span> <span data-ttu-id="165e5-128">平均请求持续时间将保持相对静态。</span><span class="sxs-lookup"><span data-stu-id="165e5-128">The average request duration will remain relatively static.</span></span> <span data-ttu-id="165e5-129">当服务器接近其最大容量时，每秒的请求开始到 "停止"，并且平均请求持续时间开始时间较长。</span><span class="sxs-lookup"><span data-stu-id="165e5-129">As the server nears its maximum capacity, the requests per second start to level out, and the average request duration starts to get longer.</span></span>

<span data-ttu-id="165e5-130">如果你担心你的 MBAM 服务器是否可以支持你的客户端基础，请考虑在客户端计算机的不同集合阶段部署 MBAM。</span><span class="sxs-lookup"><span data-stu-id="165e5-130">If you are concerned about whether your MBAM Servers can support your client base, consider deploying MBAM in phases across different collections of client computers.</span></span> <span data-ttu-id="165e5-131">当你将 MBAM 部署到每个客户端计算机集合时，我们建议你拍摄性能计数器的快照，以查看部署到每个新客户端集合的相对影响。</span><span class="sxs-lookup"><span data-stu-id="165e5-131">As you deploy MBAM to each collection of client computers, we recommend that you take snapshots of the performance counters to see the relative impact of deploying to each new client collection.</span></span> <span data-ttu-id="165e5-132">如果每秒的请求数从 "开始" 到 "级别"，并且平均请求持续时间增加，请考虑通过执行下列操作之一来增强 MBAM 服务器基础结构：</span><span class="sxs-lookup"><span data-stu-id="165e5-132">If the number of requests per second starts to level off and the average request duration increases, consider enhancing your MBAM Server infrastructure by doing one of the following:</span></span>

-   <span data-ttu-id="165e5-133">将 MBAM 数据库移动到专用 Microsoft SQL Server 或 SQL Server 群集</span><span class="sxs-lookup"><span data-stu-id="165e5-133">Moving the MBAM database onto a dedicated Microsoft SQL Server or SQL Server cluster</span></span>

-   <span data-ttu-id="165e5-134">跨多个 Internet Information Services （IIS） web 服务器的负载平衡 MBAM</span><span class="sxs-lookup"><span data-stu-id="165e5-134">Load-balancing MBAM across multiple Internet Information Services (IIS) web servers</span></span>

-   <span data-ttu-id="165e5-135">在功能更强大的服务器硬件上部署 MBAM</span><span class="sxs-lookup"><span data-stu-id="165e5-135">Deploying MBAM on more powerful server hardware</span></span>

## <span data-ttu-id="165e5-136">查看性能计数器</span><span class="sxs-lookup"><span data-stu-id="165e5-136">Viewing performance counters</span></span>


<span data-ttu-id="165e5-137">用于查看 MBAM 性能计数器的推荐工具是 Windows 性能监视器，它随 Windows 提供。</span><span class="sxs-lookup"><span data-stu-id="165e5-137">The recommended tool for viewing MBAM performance counters is Windows Performance Monitor, which comes with Windows.</span></span> <span data-ttu-id="165e5-138">如果你使用的是 Windows PowerShell，则无需在查看计数器之前启用它们，因为它们由 Windows PowerShell **enable webapplication** cmdlet 自动注册。</span><span class="sxs-lookup"><span data-stu-id="165e5-138">If you are using Windows PowerShell, you don’t need to enable the counters before viewing them, as they are automatically registered by the Windows PowerShell **Enable-webapplication** cmdlet.</span></span>

<span data-ttu-id="165e5-139">有关如何查看性能计数器的详细说明，请参阅[如何查看 MBAM 性能计数器](https://go.microsoft.com/fwlink/?LinkId=393457)。</span><span class="sxs-lookup"><span data-stu-id="165e5-139">For detailed instructions on how to view performance counters, see [How to View MBAM Performance Counters](https://go.microsoft.com/fwlink/?LinkId=393457).</span></span>



## <span data-ttu-id="165e5-140">相关主题</span><span class="sxs-lookup"><span data-stu-id="165e5-140">Related topics</span></span>


[<span data-ttu-id="165e5-141">维护 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="165e5-141">Maintaining MBAM 2.5</span></span>](maintaining-mbam-25.md)

 

 


## <span data-ttu-id="165e5-142">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="165e5-142">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="165e5-143">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="165e5-143">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="165e5-144">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="165e5-144">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>


