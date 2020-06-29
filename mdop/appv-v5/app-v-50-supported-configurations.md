---
title: App-V 5.0 支持的配置
description: App-V 5.0 支持的配置
author: dansimp
ms.assetid: 3787ff63-7ce7-45a8-8f01-81b4b6dced34
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 60236743d2a6b418ca7f4705168a7bf064b82156
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798633"
---
# <span data-ttu-id="3e5f6-103">App-V 5.0 支持的配置</span><span class="sxs-lookup"><span data-stu-id="3e5f6-103">App-V 5.0 Supported Configurations</span></span>


<span data-ttu-id="3e5f6-104">本主题指定在你的环境中安装和运行 Microsoft Application Virtualization （app-v）5.0 所需的要求。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-104">This topic specifies the requirements that are necessary to install and run Microsoft Application Virtualization (App-V) 5.0 in your environment.</span></span>

**<span data-ttu-id="3e5f6-105">重要提示</span><span class="sxs-lookup"><span data-stu-id="3e5f6-105">Important</span></span>**  
<span data-ttu-id="3e5f6-106">**本文中受支持的配置仅适用于 app-v 5.0**。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-106">**The supported configurations in this article apply only to App-V 5.0**.</span></span> <span data-ttu-id="3e5f6-107">有关适用于 App-v 5.0 Service Pack 的受支持配置，请参阅以下网页：</span><span class="sxs-lookup"><span data-stu-id="3e5f6-107">For supported configurations that apply to App-V 5.0 Service Packs, see the following web pages:</span></span>

-   [<span data-ttu-id="3e5f6-108">App-V 5.0 SP1 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="3e5f6-108">What's new in App-V 5.0 SP1</span></span>](whats-new-in-app-v-50-sp1.md)

-   [<span data-ttu-id="3e5f6-109">关于 App-V 5.0 SP2</span><span class="sxs-lookup"><span data-stu-id="3e5f6-109">About App-V 5.0 SP2</span></span>](about-app-v-50-sp2.md)

-   [<span data-ttu-id="3e5f6-110">App-V 5.0 SP3 支持的配置</span><span class="sxs-lookup"><span data-stu-id="3e5f6-110">App-V 5.0 SP3 Supported Configurations</span></span>](app-v-50-sp3-supported-configurations.md)



## <a href="" id="---------app-v-5-0-server-system-requirements"></a> <span data-ttu-id="3e5f6-111">App-v 5.0 服务器系统要求</span><span class="sxs-lookup"><span data-stu-id="3e5f6-111">App-V 5.0 server system requirements</span></span>


**<span data-ttu-id="3e5f6-112">重要提示</span><span class="sxs-lookup"><span data-stu-id="3e5f6-112">Important</span></span>**  
<span data-ttu-id="3e5f6-113">App-v 5.0 服务器不支持以下方案：</span><span class="sxs-lookup"><span data-stu-id="3e5f6-113">The App-V 5.0 server does not support the following scenarios:</span></span>



-   <span data-ttu-id="3e5f6-114">部署到运行 Microsoft Windows Server Core 的计算机。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-114">Deployment to a computer that runs Microsoft Windows Server Core.</span></span>

-   <span data-ttu-id="3e5f6-115">部署到运行早期版本的 App-v 5.0 server 组件的计算机。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-115">Deployment to a computer that runs a previous version of App-V 5.0 server components.</span></span>

    **<span data-ttu-id="3e5f6-116">注意</span><span class="sxs-lookup"><span data-stu-id="3e5f6-116">Note</span></span>**  
    <span data-ttu-id="3e5f6-117">你可以仅使用 app-v 4.5 轻型流服务器（LWS）服务器并行安装 app-v 5.0。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-117">You can install App-V 5.0 side-by-side with the App-V 4.5 Lightweight Streaming Server (LWS) server only.</span></span> <span data-ttu-id="3e5f6-118">不支持使用 app-v 4.5 应用程序虚拟化管理服务（HWS）服务器并行部署 app-v 5.0。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-118">Deployment of App-V 5.0 side-by-side with the App-V 4.5 Application Virtualization Management Service (HWS) server is not supported.</span></span>



-   <span data-ttu-id="3e5f6-119">部署到运行 Microsoft SQL Server Express edition 的计算机。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-119">Deployment to a computer that runs Microsoft SQL Server Express edition.</span></span>

-   <span data-ttu-id="3e5f6-120">管理服务器数据库或报告数据库的远程部署。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-120">Remote deployment of the management server database or the reporting database.</span></span> <span data-ttu-id="3e5f6-121">安装程序必须直接在运行 Microsoft SQL 的计算机上运行，才能成功完成数据库安装。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-121">The installer must be run directly on the computer running Microsoft SQL for the database installation to succeed.</span></span>

-   <span data-ttu-id="3e5f6-122">部署到域控制器。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-122">Deployment to a domain controller.</span></span>

-   <span data-ttu-id="3e5f6-123">短路径不受支持。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-123">Short paths are not supported.</span></span> <span data-ttu-id="3e5f6-124">如果您计划使用短路径，则必须创建新卷。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-124">If you plan to use a short path you must create a new volume.</span></span>

### <span data-ttu-id="3e5f6-125">管理服务器操作系统要求</span><span class="sxs-lookup"><span data-stu-id="3e5f6-125">Management Server operating system requirements</span></span>

<span data-ttu-id="3e5f6-126">下表列出了 app-v 5.0 管理服务器安装支持的操作系统。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-126">The following table lists the operating systems that are supported for the App-V 5.0 management server installation.</span></span>

**<span data-ttu-id="3e5f6-127">注意</span><span class="sxs-lookup"><span data-stu-id="3e5f6-127">Note</span></span>**  
<span data-ttu-id="3e5f6-128">Microsoft 提供对当前服务包的支持，在某些情况下，还提供了之前的服务包。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-128">Microsoft provides support for the current service pack and, in some cases, the immediately preceding service pack.</span></span> <span data-ttu-id="3e5f6-129">若要查找产品的支持时间表，请参阅[支持生命周期的服务包](https://go.microsoft.com/fwlink/p/?LinkId=31975)。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-129">To find the support timelines for your product, see the [Lifecycle Supported Service Packs](https://go.microsoft.com/fwlink/p/?LinkId=31975).</span></span> <span data-ttu-id="3e5f6-130">有关 Microsoft 支持生命周期策略的其他信息，请参阅[Microsoft 支持生命周期支持策略常见问题解答](https://go.microsoft.com/fwlink/p/?LinkId=31976)。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-130">For additional information about Microsoft Support Lifecycle Policy, see [Microsoft Support Lifecycle Support Policy FAQ](https://go.microsoft.com/fwlink/p/?LinkId=31976).</span></span>



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3e5f6-131">操作系统</span><span class="sxs-lookup"><span data-stu-id="3e5f6-131">Operating system</span></span></th>
<th align="left"><span data-ttu-id="3e5f6-132">版本</span><span class="sxs-lookup"><span data-stu-id="3e5f6-132">Edition</span></span></th>
<th align="left"><span data-ttu-id="3e5f6-133">Service pack</span><span class="sxs-lookup"><span data-stu-id="3e5f6-133">Service pack</span></span></th>
<th align="left"><span data-ttu-id="3e5f6-134">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="3e5f6-134">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3e5f6-135">Microsoft Windows Server 2008 （标准版、企业版、数据中心版或 Web 服务器）</span><span class="sxs-lookup"><span data-stu-id="3e5f6-135">Microsoft Windows Server 2008 (Standard, Enterprise, Datacenter, or Web Server)</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e5f6-136">R2</span><span class="sxs-lookup"><span data-stu-id="3e5f6-136">R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e5f6-137">SP1 及更高版本</span><span class="sxs-lookup"><span data-stu-id="3e5f6-137">SP1 and higher</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e5f6-138">64 位</span><span class="sxs-lookup"><span data-stu-id="3e5f6-138">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3e5f6-139">Microsoft Windows Server 2012 （Standard、Datacenter）</span><span class="sxs-lookup"><span data-stu-id="3e5f6-139">Microsoft Windows Server 2012 (Standard, Datacenter)</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"></td>
<td align="left"><p><span data-ttu-id="3e5f6-140">64 位</span><span class="sxs-lookup"><span data-stu-id="3e5f6-140">64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3e5f6-141">Microsoft Windows Server 2012 （Standard、Datacenter）</span><span class="sxs-lookup"><span data-stu-id="3e5f6-141">Microsoft Windows Server 2012 (Standard, Datacenter)</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e5f6-142">R2</span><span class="sxs-lookup"><span data-stu-id="3e5f6-142">R2</span></span></p></td>
<td align="left"></td>
<td align="left"><p><span data-ttu-id="3e5f6-143">64 位</span><span class="sxs-lookup"><span data-stu-id="3e5f6-143">64-bit</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="3e5f6-144">重要提示</span><span class="sxs-lookup"><span data-stu-id="3e5f6-144">Important</span></span>**  
<span data-ttu-id="3e5f6-145">不支持将管理服务器角色部署到启用了远程桌面共享（RDS）的计算机。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-145">Deployment of the management server role to a computer with Remote Desktop Sharing (RDS) enabled is not supported.</span></span>



### <a href="" id="management-server-hardware-requirements-"></a><span data-ttu-id="3e5f6-146">管理服务器硬件要求</span><span class="sxs-lookup"><span data-stu-id="3e5f6-146">Management Server hardware requirements</span></span>

-   <span data-ttu-id="3e5f6-147">处理器-1.4 GHz 或更快的64位（x64）处理器</span><span class="sxs-lookup"><span data-stu-id="3e5f6-147">Processor—1.4 GHz or faster, 64-bit (x64) processor</span></span>

-   <span data-ttu-id="3e5f6-148">RAM-1 GB RAM （64位）</span><span class="sxs-lookup"><span data-stu-id="3e5f6-148">RAM— 1 GB RAM (64-bit)</span></span>

-   <span data-ttu-id="3e5f6-149">磁盘空间-200 MB 可用硬盘空间，不包括内容目录。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-149">Disk space—200 MB available hard disk space, not including the content directory.</span></span>

### <span data-ttu-id="3e5f6-150">发布服务器操作系统要求</span><span class="sxs-lookup"><span data-stu-id="3e5f6-150">Publishing Server operating system requirements</span></span>

<span data-ttu-id="3e5f6-151">下表列出了 app-v 5.0 发布服务器安装支持的操作系统。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-151">The following table lists the operating systems that are supported for the App-V 5.0 publishing server installation.</span></span>

**<span data-ttu-id="3e5f6-152">注意</span><span class="sxs-lookup"><span data-stu-id="3e5f6-152">Note</span></span>**  
<span data-ttu-id="3e5f6-153">Microsoft 提供对当前服务包的支持，在某些情况下，还提供了之前的服务包。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-153">Microsoft provides support for the current service pack and, in some cases, the immediately preceding service pack.</span></span> <span data-ttu-id="3e5f6-154">若要查找产品的支持时间表，请参阅[支持生命周期的服务包](https://go.microsoft.com/fwlink/p/?LinkId=31975)。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-154">To find the support timelines for your product, see the [Lifecycle Supported Service Packs](https://go.microsoft.com/fwlink/p/?LinkId=31975).</span></span> <span data-ttu-id="3e5f6-155">有关 Microsoft 支持生命周期策略的其他信息，请参阅[Microsoft 支持生命周期支持策略常见问题解答](https://go.microsoft.com/fwlink/p/?LinkId=31976)。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-155">For additional information about Microsoft Support Lifecycle Policy, see [Microsoft Support Lifecycle Support Policy FAQ](https://go.microsoft.com/fwlink/p/?LinkId=31976).</span></span>



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3e5f6-156">操作系统</span><span class="sxs-lookup"><span data-stu-id="3e5f6-156">Operating system</span></span></th>
<th align="left"><span data-ttu-id="3e5f6-157">版本</span><span class="sxs-lookup"><span data-stu-id="3e5f6-157">Edition</span></span></th>
<th align="left"><span data-ttu-id="3e5f6-158">Service pack</span><span class="sxs-lookup"><span data-stu-id="3e5f6-158">Service pack</span></span></th>
<th align="left"><span data-ttu-id="3e5f6-159">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="3e5f6-159">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3e5f6-160">Microsoft Windows Server 2008 （标准版、企业版、数据中心版或 Web 服务器）</span><span class="sxs-lookup"><span data-stu-id="3e5f6-160">Microsoft Windows Server 2008 (Standard, Enterprise, Datacenter, or Web Server)</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e5f6-161">R2</span><span class="sxs-lookup"><span data-stu-id="3e5f6-161">R2</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="3e5f6-162">64 位</span><span class="sxs-lookup"><span data-stu-id="3e5f6-162">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3e5f6-163">Microsoft Windows Server 2012 （Standard、Datacenter）</span><span class="sxs-lookup"><span data-stu-id="3e5f6-163">Microsoft Windows Server 2012 (Standard, Datacenter)</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"></td>
<td align="left"><p><span data-ttu-id="3e5f6-164">64 位</span><span class="sxs-lookup"><span data-stu-id="3e5f6-164">64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3e5f6-165">Microsoft Windows Server 2012 （Standard、Datacenter）</span><span class="sxs-lookup"><span data-stu-id="3e5f6-165">Microsoft Windows Server 2012 (Standard, Datacenter)</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e5f6-166">R2</span><span class="sxs-lookup"><span data-stu-id="3e5f6-166">R2</span></span></p></td>
<td align="left"></td>
<td align="left"><p><span data-ttu-id="3e5f6-167">64 位</span><span class="sxs-lookup"><span data-stu-id="3e5f6-167">64-bit</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="publishing-server-hardware-requirements-"></a><span data-ttu-id="3e5f6-168">发布服务器硬件要求</span><span class="sxs-lookup"><span data-stu-id="3e5f6-168">Publishing Server hardware requirements</span></span>

-   <span data-ttu-id="3e5f6-169">处理器-1.4 GHz 或更快。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-169">Processor—1.4 GHz or faster.</span></span> <span data-ttu-id="3e5f6-170">64位（x64）处理器</span><span class="sxs-lookup"><span data-stu-id="3e5f6-170">64-bit (x64) processor</span></span>

-   <span data-ttu-id="3e5f6-171">RAM-2 GB RAM （64位）</span><span class="sxs-lookup"><span data-stu-id="3e5f6-171">RAM— 2 GB RAM (64-bit)</span></span>

-   <span data-ttu-id="3e5f6-172">磁盘空间-200 MB 可用硬盘空间。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-172">Disk space—200 MB available hard disk space.</span></span> <span data-ttu-id="3e5f6-173">不包含内容目录</span><span class="sxs-lookup"><span data-stu-id="3e5f6-173">not including content directory</span></span>

### <span data-ttu-id="3e5f6-174">报表服务器操作系统要求</span><span class="sxs-lookup"><span data-stu-id="3e5f6-174">Reporting Server operating system requirements</span></span>

<span data-ttu-id="3e5f6-175">下表列出了 app-v 5.0 reporting server 安装支持的操作系统。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-175">The following table lists the operating systems that are supported for the App-V 5.0 reporting server installation.</span></span>

**<span data-ttu-id="3e5f6-176">注意</span><span class="sxs-lookup"><span data-stu-id="3e5f6-176">Note</span></span>**  
<span data-ttu-id="3e5f6-177">Microsoft 提供对当前服务包的支持，在某些情况下，还提供了之前的服务包。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-177">Microsoft provides support for the current service pack and, in some cases, the immediately preceding service pack.</span></span> <span data-ttu-id="3e5f6-178">若要查找产品的支持时间表，请参阅[支持生命周期的服务包](https://go.microsoft.com/fwlink/p/?LinkId=31975)。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-178">To find the support timelines for your product, see the [Lifecycle Supported Service Packs](https://go.microsoft.com/fwlink/p/?LinkId=31975).</span></span> <span data-ttu-id="3e5f6-179">有关 Microsoft 支持生命周期策略的其他信息，请参阅[Microsoft 支持生命周期支持策略常见问题解答](https://go.microsoft.com/fwlink/p/?LinkId=31976)。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-179">For additional information about Microsoft Support Lifecycle Policy, see [Microsoft Support Lifecycle Support Policy FAQ](https://go.microsoft.com/fwlink/p/?LinkId=31976).</span></span>



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3e5f6-180">操作系统</span><span class="sxs-lookup"><span data-stu-id="3e5f6-180">Operating system</span></span></th>
<th align="left"><span data-ttu-id="3e5f6-181">版本</span><span class="sxs-lookup"><span data-stu-id="3e5f6-181">Edition</span></span></th>
<th align="left"><span data-ttu-id="3e5f6-182">Service Pack</span><span class="sxs-lookup"><span data-stu-id="3e5f6-182">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="3e5f6-183">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="3e5f6-183">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3e5f6-184">Microsoft Windows Server 2008 （标准版、企业版、数据中心版或 Web 服务器）</span><span class="sxs-lookup"><span data-stu-id="3e5f6-184">Microsoft Windows Server 2008 (Standard, Enterprise, Datacenter, or Web Server)</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e5f6-185">R2</span><span class="sxs-lookup"><span data-stu-id="3e5f6-185">R2</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="3e5f6-186">64 位</span><span class="sxs-lookup"><span data-stu-id="3e5f6-186">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3e5f6-187">Microsoft Windows Server 2012 （Standard、Datacenter）</span><span class="sxs-lookup"><span data-stu-id="3e5f6-187">Microsoft Windows Server 2012 (Standard, Datacenter)</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"></td>
<td align="left"><p><span data-ttu-id="3e5f6-188">64 位</span><span class="sxs-lookup"><span data-stu-id="3e5f6-188">64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3e5f6-189">Microsoft Windows Server 2012 （Standard、Datacenter）</span><span class="sxs-lookup"><span data-stu-id="3e5f6-189">Microsoft Windows Server 2012 (Standard, Datacenter)</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e5f6-190">R2</span><span class="sxs-lookup"><span data-stu-id="3e5f6-190">R2</span></span></p></td>
<td align="left"></td>
<td align="left"><p><span data-ttu-id="3e5f6-191">64 位</span><span class="sxs-lookup"><span data-stu-id="3e5f6-191">64-bit</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="reporting-server-hardware-requirements-"></a><span data-ttu-id="3e5f6-192">报告服务器硬件要求</span><span class="sxs-lookup"><span data-stu-id="3e5f6-192">Reporting Server hardware requirements</span></span>

-   <span data-ttu-id="3e5f6-193">处理器-1.4 GHz 或更快。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-193">Processor—1.4 GHz or faster.</span></span> <span data-ttu-id="3e5f6-194">64位（x64）处理器</span><span class="sxs-lookup"><span data-stu-id="3e5f6-194">64-bit (x64) processor</span></span>

-   <span data-ttu-id="3e5f6-195">RAM-2 GB RAM （64位）</span><span class="sxs-lookup"><span data-stu-id="3e5f6-195">RAM—2 GB RAM (64-bit)</span></span>

-   <span data-ttu-id="3e5f6-196">磁盘空间-200 MB 可用硬盘空间</span><span class="sxs-lookup"><span data-stu-id="3e5f6-196">Disk space—200 MB available hard disk space</span></span>

### <a href="" id="sql-server-database-requirements-"></a><span data-ttu-id="3e5f6-197">SQL Server 数据库要求</span><span class="sxs-lookup"><span data-stu-id="3e5f6-197">SQL Server database requirements</span></span>

<span data-ttu-id="3e5f6-198">下表列出了 app-v 5.0 数据库和服务器安装支持的 SQL Server 版本。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-198">The following table lists the SQL Server versions that are supported for the App-V 5.0 database and server installation.</span></span>

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3e5f6-199">App-v 5.0 服务器类型</span><span class="sxs-lookup"><span data-stu-id="3e5f6-199">App-V 5.0 server type</span></span></th>
<th align="left"><span data-ttu-id="3e5f6-200">SQL Server 版本</span><span class="sxs-lookup"><span data-stu-id="3e5f6-200">SQL Server version</span></span></th>
<th align="left"><span data-ttu-id="3e5f6-201">版本</span><span class="sxs-lookup"><span data-stu-id="3e5f6-201">Edition</span></span></th>
<th align="left"><span data-ttu-id="3e5f6-202">Service pack</span><span class="sxs-lookup"><span data-stu-id="3e5f6-202">Service pack</span></span></th>
<th align="left"><span data-ttu-id="3e5f6-203">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="3e5f6-203">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3e5f6-204">管理/报告</span><span class="sxs-lookup"><span data-stu-id="3e5f6-204">Management / Reporting</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e5f6-205">Microsoft SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="3e5f6-205">Microsoft SQL Server 2008</span></span></p>
<p><span data-ttu-id="3e5f6-206">（标准版、企业版、数据中心版或开发人员版，具有以下功能： <strong>数据库引擎服务 </strong> 。）</span><span class="sxs-lookup"><span data-stu-id="3e5f6-206">(Standard, Enterprise, Datacenter, or the Developer Edition with the following feature: <strong>Database Engine Services</strong>.)</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="3e5f6-207">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="3e5f6-207">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3e5f6-208">管理/报告</span><span class="sxs-lookup"><span data-stu-id="3e5f6-208">Management / Reporting</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e5f6-209">Microsoft SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="3e5f6-209">Microsoft SQL Server 2008</span></span> </p>
<p><span data-ttu-id="3e5f6-210">（标准版、企业版、数据中心版或开发人员版，具有以下功能： <strong>数据库引擎服务 </strong> 。）</span><span class="sxs-lookup"><span data-stu-id="3e5f6-210">(Standard, Enterprise, Datacenter, or the Developer Edition with the following feature: <strong>Database Engine Services</strong>.)</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e5f6-211">R2</span><span class="sxs-lookup"><span data-stu-id="3e5f6-211">R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e5f6-212">SP2</span><span class="sxs-lookup"><span data-stu-id="3e5f6-212">SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e5f6-213">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="3e5f6-213">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3e5f6-214">管理/报告</span><span class="sxs-lookup"><span data-stu-id="3e5f6-214">Management / Reporting</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e5f6-215">Microsoft SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="3e5f6-215">Microsoft SQL Server 2012</span></span></p>
<p><span data-ttu-id="3e5f6-216">（标准版、企业版、数据中心版或开发人员版，具有以下功能： <strong>数据库引擎服务 </strong> 。）</span><span class="sxs-lookup"><span data-stu-id="3e5f6-216">(Standard, Enterprise, Datacenter, or the Developer Edition with the following feature: <strong>Database Engine Services</strong>.)</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="3e5f6-217">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="3e5f6-217">32-bit or 64-bit</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-client-supp-cfgs"></a> <span data-ttu-id="3e5f6-218">App-v 5.0 客户端系统要求</span><span class="sxs-lookup"><span data-stu-id="3e5f6-218">App-V 5.0 client system requirements</span></span>


<span data-ttu-id="3e5f6-219">下表列出了 app-v 5.0 客户端安装支持的操作系统。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-219">The following table lists the operating systems that are supported for the App-V 5.0 client installation.</span></span>

**<span data-ttu-id="3e5f6-220">注意</span><span class="sxs-lookup"><span data-stu-id="3e5f6-220">Note</span></span>**  
<span data-ttu-id="3e5f6-221">Microsoft 提供对当前服务包的支持，在某些情况下，还提供了之前的服务包。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-221">Microsoft provides support for the current service pack and, in some cases, the immediately preceding service pack.</span></span> <span data-ttu-id="3e5f6-222">若要查找产品的支持时间表，请参阅[支持生命周期的服务包](https://go.microsoft.com/fwlink/p/?LinkId=31975)。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-222">To find the support timelines for your product, see the [Lifecycle Supported Service Packs](https://go.microsoft.com/fwlink/p/?LinkId=31975).</span></span> <span data-ttu-id="3e5f6-223">有关 Microsoft 支持生命周期策略的其他信息，请参阅[Microsoft 支持生命周期支持策略常见问题解答](https://go.microsoft.com/fwlink/p/?LinkId=31976)。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-223">For additional information about Microsoft Support Lifecycle Policy, see [Microsoft Support Lifecycle Support Policy FAQ](https://go.microsoft.com/fwlink/p/?LinkId=31976).</span></span>



<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3e5f6-224">操作系统</span><span class="sxs-lookup"><span data-stu-id="3e5f6-224">Operating system</span></span></th>
<th align="left"><span data-ttu-id="3e5f6-225">Service pack</span><span class="sxs-lookup"><span data-stu-id="3e5f6-225">Service pack</span></span></th>
<th align="left"><span data-ttu-id="3e5f6-226">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="3e5f6-226">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3e5f6-227">Microsoft Windows 7</span><span class="sxs-lookup"><span data-stu-id="3e5f6-227">Microsoft Windows 7</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e5f6-228">SP1</span><span class="sxs-lookup"><span data-stu-id="3e5f6-228">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e5f6-229">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="3e5f6-229">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3e5f6-230">Microsoft Windows 8</span><span class="sxs-lookup"><span data-stu-id="3e5f6-230">Microsoft Windows 8</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="3e5f6-231">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="3e5f6-231">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><div class="alert">
<strong><span data-ttu-id="3e5f6-232">重要提示</span><span class="sxs-lookup"><span data-stu-id="3e5f6-232">Important</span></span></strong><br/><p><span data-ttu-id="3e5f6-233">Windows 8.1 仅受 App-v 5.0 SP2 支持</span><span class="sxs-lookup"><span data-stu-id="3e5f6-233">Windows 8.1 is only supported by App-V 5.0 SP2</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="3e5f6-234">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="3e5f6-234">Windows 8.1</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="3e5f6-235">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="3e5f6-235">32-bit or 64-bit</span></span></p></td>
</tr>
</tbody>
</table>



<span data-ttu-id="3e5f6-236">以下 App-v 客户端安装方案不受支持，但所述除外：</span><span class="sxs-lookup"><span data-stu-id="3e5f6-236">The following App-V client installation scenarios are not supported, except as noted:</span></span>

-   <span data-ttu-id="3e5f6-237">运行 Windows Server 的计算机</span><span class="sxs-lookup"><span data-stu-id="3e5f6-237">Computers that run Windows Server</span></span>

-   <span data-ttu-id="3e5f6-238">运行 App-v 4.6 SP1 或更早版本的计算机</span><span class="sxs-lookup"><span data-stu-id="3e5f6-238">Computers that run App-V 4.6 SP1 or earlier versions</span></span>

-   <span data-ttu-id="3e5f6-239">只有支持 RDS 的服务器才支持 app-v 5.0 远程桌面服务客户端</span><span class="sxs-lookup"><span data-stu-id="3e5f6-239">The App-V 5.0 Remote Desktop services client is supported only for RDS-enabled servers</span></span>

### <a href="" id="client-hardware-requirements-"></a><span data-ttu-id="3e5f6-240">客户端硬件要求</span><span class="sxs-lookup"><span data-stu-id="3e5f6-240">Client hardware requirements</span></span>

<span data-ttu-id="3e5f6-241">以下列表显示了 app-v 5.0 客户端安装所支持的硬件配置。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-241">The following list displays the supported hardware configuration for the App-V 5.0 client installation.</span></span>

-   <span data-ttu-id="3e5f6-242">处理器-1.4 GHz 或更快的32位（x86）或64位（x64）处理器</span><span class="sxs-lookup"><span data-stu-id="3e5f6-242">Processor— 1.4 GHz or faster 32-bit (x86) or 64-bit (x64) processor</span></span>

-   <span data-ttu-id="3e5f6-243">RAM-1 GB （32位）或 2 GB （64位）</span><span class="sxs-lookup"><span data-stu-id="3e5f6-243">RAM— 1 GB (32-bit) or 2 GB (64-bit)</span></span>

-   <span data-ttu-id="3e5f6-244">磁盘-100 MB 用于安装，不包括虚拟化应用程序使用的磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-244">Disk— 100 MB for installation, not including the disk space that is used by virtualized applications.</span></span>

## <a href="" id="---------app-v-5-0-remote-desktop-client-system-requirements"></a> <span data-ttu-id="3e5f6-245">App-v 5.0 远程桌面客户端系统要求</span><span class="sxs-lookup"><span data-stu-id="3e5f6-245">App-V 5.0 Remote Desktop client system requirements</span></span>


<span data-ttu-id="3e5f6-246">下表列出了 App-v 5.0 远程桌面客户端安装支持的操作系统。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-246">The following table lists the operating systems that are supported for App-V 5.0 Remote Desktop client installation.</span></span>

**<span data-ttu-id="3e5f6-247">注意</span><span class="sxs-lookup"><span data-stu-id="3e5f6-247">Note</span></span>**  
<span data-ttu-id="3e5f6-248">Microsoft 提供对当前服务包的支持，在某些情况下，还提供了之前的服务包。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-248">Microsoft provides support for the current service pack and, in some cases, the immediately preceding service pack.</span></span> <span data-ttu-id="3e5f6-249">若要查找产品的支持时间表，请参阅[支持生命周期的服务包](https://go.microsoft.com/fwlink/p/?LinkId=31975)。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-249">To find the support timelines for your product, see the [Lifecycle Supported Service Packs](https://go.microsoft.com/fwlink/p/?LinkId=31975).</span></span> <span data-ttu-id="3e5f6-250">有关 Microsoft 支持生命周期策略的其他信息，请参阅[Microsoft 支持生命周期支持策略常见问题解答](https://go.microsoft.com/fwlink/p/?LinkId=31976)。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-250">For additional information about Microsoft Support Lifecycle Policy, see [Microsoft Support Lifecycle Support Policy FAQ](https://go.microsoft.com/fwlink/p/?LinkId=31976).</span></span>



<span data-ttu-id="3e5f6-251">操作系统版本 Service pack Microsoft Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="3e5f6-251">Operating system Edition Service pack Microsoft Windows Server 2008</span></span>

<span data-ttu-id="3e5f6-252">R2</span><span class="sxs-lookup"><span data-stu-id="3e5f6-252">R2</span></span>

<span data-ttu-id="3e5f6-253">SP1</span><span class="sxs-lookup"><span data-stu-id="3e5f6-253">SP1</span></span>

<span data-ttu-id="3e5f6-254">Microsoft Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="3e5f6-254">Microsoft Windows Server 2012</span></span>

**<span data-ttu-id="3e5f6-255">重要提示</span><span class="sxs-lookup"><span data-stu-id="3e5f6-255">Important</span></span>**  
<span data-ttu-id="3e5f6-256">Windows Server 2012 R2 仅受 App-v 5.0 SP2 支持</span><span class="sxs-lookup"><span data-stu-id="3e5f6-256">Windows Server 2012 R2 is only supported by App-V 5.0 SP2</span></span>



<span data-ttu-id="3e5f6-257">Microsoft Windows Server 2012 （Standard、Datacenter）</span><span class="sxs-lookup"><span data-stu-id="3e5f6-257">Microsoft Windows Server 2012 (Standard, Datacenter)</span></span>

<span data-ttu-id="3e5f6-258">R2</span><span class="sxs-lookup"><span data-stu-id="3e5f6-258">R2</span></span>

<span data-ttu-id="3e5f6-259">64 位</span><span class="sxs-lookup"><span data-stu-id="3e5f6-259">64-bit</span></span>



### <a href="" id="remote-desktop-client-hardware-requirements-"></a><span data-ttu-id="3e5f6-260">远程桌面客户端硬件要求</span><span class="sxs-lookup"><span data-stu-id="3e5f6-260">Remote Desktop client hardware requirements</span></span>

<span data-ttu-id="3e5f6-261">以下列表显示了 app-v 5.0 客户端安装所支持的硬件配置。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-261">The following list displays the supported hardware configuration for the App-V 5.0 client installation.</span></span>

-   <span data-ttu-id="3e5f6-262">处理器-1.4 GHz 或更快的32位（x86）或64位（x64）处理器</span><span class="sxs-lookup"><span data-stu-id="3e5f6-262">Processor— 1.4 GHz or faster 32-bit (x86) or 64-bit (x64) processor</span></span>

-   <span data-ttu-id="3e5f6-263">RAM-1 GB （32位）或 2 GB （64位）</span><span class="sxs-lookup"><span data-stu-id="3e5f6-263">RAM— 1 GB (32-bit) or 2 GB (64-bit)</span></span>

-   <span data-ttu-id="3e5f6-264">磁盘-100 MB 用于安装，不包括虚拟化应用程序使用的磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-264">Disk— 100 MB for installation, not including the disk space that is used by virtualized applications.</span></span>

## <a href="" id="---------app-v-5-0-sequencer-system-requirements"></a> <span data-ttu-id="3e5f6-265">App-v 5.0 Sequencer 系统要求</span><span class="sxs-lookup"><span data-stu-id="3e5f6-265">App-V 5.0 Sequencer system requirements</span></span>


<span data-ttu-id="3e5f6-266">下表列出了应用 V 5.0 Sequencer 安装支持的操作系统。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-266">The following table lists the operating systems that are supported for App-V 5.0 Sequencer installation.</span></span>

**<span data-ttu-id="3e5f6-267">注意</span><span class="sxs-lookup"><span data-stu-id="3e5f6-267">Note</span></span>**  
<span data-ttu-id="3e5f6-268">Microsoft 提供对当前服务包的支持，在某些情况下，还提供了之前的服务包。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-268">Microsoft provides support for the current service pack and, in some cases, the immediately preceding service pack.</span></span> <span data-ttu-id="3e5f6-269">若要查找产品的支持时间表，请参阅[支持生命周期的服务包](https://go.microsoft.com/fwlink/p/?LinkId=31975)。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-269">To find the support timelines for your product, see the [Lifecycle Supported Service Packs](https://go.microsoft.com/fwlink/p/?LinkId=31975).</span></span> <span data-ttu-id="3e5f6-270">有关 Microsoft 支持生命周期策略的其他信息，请参阅[Microsoft 支持生命周期支持策略常见问题解答](https://go.microsoft.com/fwlink/p/?LinkId=31976)。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-270">For additional information about Microsoft Support Lifecycle Policy, see [Microsoft Support Lifecycle Support Policy FAQ](https://go.microsoft.com/fwlink/p/?LinkId=31976).</span></span>



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3e5f6-271">操作系统</span><span class="sxs-lookup"><span data-stu-id="3e5f6-271">Operating system</span></span></th>
<th align="left"><span data-ttu-id="3e5f6-272">版本</span><span class="sxs-lookup"><span data-stu-id="3e5f6-272">Edition</span></span></th>
<th align="left"><span data-ttu-id="3e5f6-273">Service pack</span><span class="sxs-lookup"><span data-stu-id="3e5f6-273">Service pack</span></span></th>
<th align="left"><span data-ttu-id="3e5f6-274">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="3e5f6-274">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3e5f6-275">Microsoft Windows 7</span><span class="sxs-lookup"><span data-stu-id="3e5f6-275">Microsoft Windows 7</span></span></p></td>
<td align="left"></td>
<td align="left"><p><span data-ttu-id="3e5f6-276">SP1</span><span class="sxs-lookup"><span data-stu-id="3e5f6-276">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e5f6-277">32 位和 64 位 ：</span><span class="sxs-lookup"><span data-stu-id="3e5f6-277">32-bit and 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3e5f6-278">Microsoft Windows 8</span><span class="sxs-lookup"><span data-stu-id="3e5f6-278">Microsoft Windows 8</span></span></p></td>
<td align="left"></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="3e5f6-279">32 位和 64 位 ：</span><span class="sxs-lookup"><span data-stu-id="3e5f6-279">32-bit and 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><div class="alert">
<strong><span data-ttu-id="3e5f6-280">重要提示</span><span class="sxs-lookup"><span data-stu-id="3e5f6-280">Important</span></span></strong><br/><p><span data-ttu-id="3e5f6-281">Windows 8.1 仅受 App-v 5.0 SP2 支持</span><span class="sxs-lookup"><span data-stu-id="3e5f6-281">Windows 8.1 is only supported by App-V 5.0 SP2</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="3e5f6-282">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="3e5f6-282">Windows 8.1</span></span></p></td>
<td align="left"></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="3e5f6-283">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="3e5f6-283">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3e5f6-284">Microsoft Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="3e5f6-284">Microsoft Windows Server 2008</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e5f6-285">R2</span><span class="sxs-lookup"><span data-stu-id="3e5f6-285">R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e5f6-286">SP1</span><span class="sxs-lookup"><span data-stu-id="3e5f6-286">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e5f6-287">32 位和 64 位 ：</span><span class="sxs-lookup"><span data-stu-id="3e5f6-287">32-bit and 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3e5f6-288">Microsoft Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="3e5f6-288">Microsoft Windows Server 2012</span></span></p></td>
<td align="left"></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="3e5f6-289">32 位和 64 位 ：</span><span class="sxs-lookup"><span data-stu-id="3e5f6-289">32-bit and 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><div class="alert">
<strong><span data-ttu-id="3e5f6-290">重要提示</span><span class="sxs-lookup"><span data-stu-id="3e5f6-290">Important</span></span></strong><br/><p><span data-ttu-id="3e5f6-291">Windows Server 2012 R2 仅受 App-v 5.0 SP2 支持</span><span class="sxs-lookup"><span data-stu-id="3e5f6-291">Windows Server 2012 R2 is only supported by App-V 5.0 SP2</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="3e5f6-292">Microsoft Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="3e5f6-292">Microsoft Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e5f6-293">R2</span><span class="sxs-lookup"><span data-stu-id="3e5f6-293">R2</span></span></p></td>
<td align="left"></td>
<td align="left"><p><span data-ttu-id="3e5f6-294">64 位</span><span class="sxs-lookup"><span data-stu-id="3e5f6-294">64-bit</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-supp-ver-sccm"></a><span data-ttu-id="3e5f6-295">System Center Configuration Manager 支持的版本</span><span class="sxs-lookup"><span data-stu-id="3e5f6-295">Supported versions of System Center Configuration Manager</span></span>


<span data-ttu-id="3e5f6-296">你可以使用 Microsoft System Center 2012 Configuration Manager 或 System Center 2012 R2 配置管理器管理 App-v 虚拟应用程序、报告和其他功能。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-296">You can use Microsoft System Center 2012 Configuration Manager or System Center 2012 R2 Configuration Manager to manage App-V virtual applications, reporting, and other functions.</span></span> <span data-ttu-id="3e5f6-297">下表列出了每个适用版本的 App-v 的受支持的 Configuration Manager 版本。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-297">The following table lists the supported versions of Configuration Manager for each applicable version of App-V.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3e5f6-298">支持的 Configuration Manager 版本</span><span class="sxs-lookup"><span data-stu-id="3e5f6-298">Supported Configuration Manager version</span></span></th>
<th align="left"><span data-ttu-id="3e5f6-299">App-v 版本</span><span class="sxs-lookup"><span data-stu-id="3e5f6-299">App-V version</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3e5f6-300">Microsoft System Center 2012 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="3e5f6-300">Microsoft System Center 2012 Configuration Manager</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="3e5f6-301">App-v 5。0</span><span class="sxs-lookup"><span data-stu-id="3e5f6-301">App-V 5.0</span></span></p></li>
<li><p><span data-ttu-id="3e5f6-302">App-v 5.0 SP1</span><span class="sxs-lookup"><span data-stu-id="3e5f6-302">App-V 5.0 SP1</span></span></p></li>
<li><p><span data-ttu-id="3e5f6-303">App-v 5.0 SP2</span><span class="sxs-lookup"><span data-stu-id="3e5f6-303">App-V 5.0 SP2</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3e5f6-304">System Center 2012 R2 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="3e5f6-304">System Center 2012 R2 Configuration Manager</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="3e5f6-305">App-v 5。0</span><span class="sxs-lookup"><span data-stu-id="3e5f6-305">App-V 5.0</span></span></p></li>
<li><p><span data-ttu-id="3e5f6-306">App-v 5.0 SP1</span><span class="sxs-lookup"><span data-stu-id="3e5f6-306">App-V 5.0 SP1</span></span></p></li>
<li><p><span data-ttu-id="3e5f6-307">App-v 5.0 SP2</span><span class="sxs-lookup"><span data-stu-id="3e5f6-307">App-V 5.0 SP2</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>



<span data-ttu-id="3e5f6-308">有关 Configuration Manager 如何与 app-v 集成的详细信息，请参阅[规划与 Configuration Manager 的 App-v 集成](https://technet.microsoft.com/library/jj822982.aspx)。</span><span class="sxs-lookup"><span data-stu-id="3e5f6-308">For more information about how Configuration Manager integrates with App-V, see [Planning for App-V Integration with Configuration Manager](https://technet.microsoft.com/library/jj822982.aspx).</span></span>






## <span data-ttu-id="3e5f6-309">相关主题</span><span class="sxs-lookup"><span data-stu-id="3e5f6-309">Related topics</span></span>


[<span data-ttu-id="3e5f6-310">计划部署 App-V</span><span class="sxs-lookup"><span data-stu-id="3e5f6-310">Planning to Deploy App-V</span></span>](planning-to-deploy-app-v.md)

[<span data-ttu-id="3e5f6-311">App-V 5.0 先决条件</span><span class="sxs-lookup"><span data-stu-id="3e5f6-311">App-V 5.0 Prerequisites</span></span>](app-v-50-prerequisites.md)









