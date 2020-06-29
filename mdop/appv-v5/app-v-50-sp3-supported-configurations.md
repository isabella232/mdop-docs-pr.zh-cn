---
title: App-V 5.0 SP3 支持的配置
description: App-V 5.0 SP3 支持的配置
author: dansimp
ms.assetid: 08ced79a-0ed3-43c3-82e7-de01c1f33e81
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: b5a8858c703add3dc84c7eed4f62aa97e60ec9b0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798634"
---
# <span data-ttu-id="ec19b-103">App-V 5.0 SP3 支持的配置</span><span class="sxs-lookup"><span data-stu-id="ec19b-103">App-V 5.0 SP3 Supported Configurations</span></span>


<span data-ttu-id="ec19b-104">本主题指定在你的环境中安装和运行 Microsoft Application Virtualization （App-v） 5.0 SP3 的要求。</span><span class="sxs-lookup"><span data-stu-id="ec19b-104">This topic specifies the requirements to install and run Microsoft Application Virtualization (App-V) 5.0 SP3 in your environment.</span></span>

## <span data-ttu-id="ec19b-105">App-v Server 系统要求</span><span class="sxs-lookup"><span data-stu-id="ec19b-105">App-V Server system requirements</span></span>


<span data-ttu-id="ec19b-106">本部分列出了所有 app-v 服务器组件的操作系统和硬件要求。</span><span class="sxs-lookup"><span data-stu-id="ec19b-106">This section lists the operating system and hardware requirements for all of the App-V Server components.</span></span>

### <span data-ttu-id="ec19b-107">不支持的 app-v 5.0 SP3 服务器方案</span><span class="sxs-lookup"><span data-stu-id="ec19b-107">Unsupported App-V 5.0 SP3 Server scenarios</span></span>

<span data-ttu-id="ec19b-108">App-v 5.0 SP3 服务器不支持以下方案：</span><span class="sxs-lookup"><span data-stu-id="ec19b-108">The App-V 5.0 SP3 Server does not support the following scenarios:</span></span>

-   <span data-ttu-id="ec19b-109">部署到运行 Microsoft Windows Server Core 的计算机。</span><span class="sxs-lookup"><span data-stu-id="ec19b-109">Deployment to a computer that runs Microsoft Windows Server Core.</span></span>

-   <span data-ttu-id="ec19b-110">部署到运行早期版本的 App-v 5.0 SP3 Server 组件的计算机。</span><span class="sxs-lookup"><span data-stu-id="ec19b-110">Deployment to a computer that runs a previous version of App-V 5.0 SP3 Server components.</span></span> <span data-ttu-id="ec19b-111">你可以仅使用 app-v 4.5 轻型流服务器（LWS）服务器来安装 app-v 5.0 SP3。</span><span class="sxs-lookup"><span data-stu-id="ec19b-111">You can install App-V 5.0 SP3 side by side with the App-V4.5 Lightweight Streaming Server (LWS) server only.</span></span> <span data-ttu-id="ec19b-112">不支持使用 app-v 4.5 应用程序虚拟管理服务（HWS）服务器并行部署 app-v。</span><span class="sxs-lookup"><span data-stu-id="ec19b-112">Deployment of App-V side by side with the App-V 4.5 Application Virtualization Management Service (HWS) server is not supported.</span></span>

-   <span data-ttu-id="ec19b-113">部署到运行 Microsoft SQL Server Express edition 的计算机。</span><span class="sxs-lookup"><span data-stu-id="ec19b-113">Deployment to a computer that runs Microsoft SQL Server Express edition.</span></span>

-   <span data-ttu-id="ec19b-114">管理服务器数据库或报告数据库的远程部署。</span><span class="sxs-lookup"><span data-stu-id="ec19b-114">Remote deployment of the management server database or the reporting database.</span></span> <span data-ttu-id="ec19b-115">必须直接在运行 Microsoft SQL Server 的计算机上运行安装程序。</span><span class="sxs-lookup"><span data-stu-id="ec19b-115">You must run the installer directly on the computer that is running Microsoft SQL Server.</span></span>

-   <span data-ttu-id="ec19b-116">部署到域控制器。</span><span class="sxs-lookup"><span data-stu-id="ec19b-116">Deployment to a domain controller.</span></span>

-   <span data-ttu-id="ec19b-117">短路径。</span><span class="sxs-lookup"><span data-stu-id="ec19b-117">Short paths.</span></span> <span data-ttu-id="ec19b-118">如果您计划使用短路径，则必须创建新卷。</span><span class="sxs-lookup"><span data-stu-id="ec19b-118">If you plan to use a short path, you must create a new volume.</span></span>

### <span data-ttu-id="ec19b-119">管理服务器操作系统要求</span><span class="sxs-lookup"><span data-stu-id="ec19b-119">Management server operating system requirements</span></span>

<span data-ttu-id="ec19b-120">下表列出了 app-v 5.0 SP3 管理服务器安装支持的操作系统。</span><span class="sxs-lookup"><span data-stu-id="ec19b-120">The following table lists the operating systems that are supported for the App-V 5.0 SP3 Management server installation.</span></span>

<span data-ttu-id="ec19b-121">**注意** Microsoft 提供对当前服务包的支持，在某些情况下，还提供了之前的服务包。</span><span class="sxs-lookup"><span data-stu-id="ec19b-121">**Note** Microsoft provides support for the current service pack and, in some cases, the immediately preceding service pack.</span></span> <span data-ttu-id="ec19b-122">若要查找产品的支持时间表，请参阅[支持生命周期的服务包](https://go.microsoft.com/fwlink/p/?LinkId=31975)。</span><span class="sxs-lookup"><span data-stu-id="ec19b-122">To find the support timelines for your product, see the [Lifecycle Supported Service Packs](https://go.microsoft.com/fwlink/p/?LinkId=31975).</span></span> <span data-ttu-id="ec19b-123">有关详细信息，请参阅[Microsoft 支持生命周期支持策略常见问题](https://go.microsoft.com/fwlink/p/?LinkId=31976)。</span><span class="sxs-lookup"><span data-stu-id="ec19b-123">See [Microsoft Support Lifecycle Support Policy FAQ](https://go.microsoft.com/fwlink/p/?LinkId=31976) for more information.</span></span>

 

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ec19b-124">操作系统</span><span class="sxs-lookup"><span data-stu-id="ec19b-124">Operating system</span></span></th>
<th align="left"><span data-ttu-id="ec19b-125">Service Pack</span><span class="sxs-lookup"><span data-stu-id="ec19b-125">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="ec19b-126">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="ec19b-126">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ec19b-127">Microsoft Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="ec19b-127">Microsoft Windows Server 2012 R2</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ec19b-128">64 位</span><span class="sxs-lookup"><span data-stu-id="ec19b-128">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ec19b-129">Microsoft Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="ec19b-129">Microsoft Windows Server 2012</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ec19b-130">64 位</span><span class="sxs-lookup"><span data-stu-id="ec19b-130">64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ec19b-131">Microsoft Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="ec19b-131">Microsoft Windows Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="ec19b-132">SP1</span><span class="sxs-lookup"><span data-stu-id="ec19b-132">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="ec19b-133">64 位</span><span class="sxs-lookup"><span data-stu-id="ec19b-133">64-bit</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="ec19b-134">**重要提示** 不支持将管理服务器角色部署到启用了远程桌面共享（RDS）的计算机。</span><span class="sxs-lookup"><span data-stu-id="ec19b-134">**Important** Deployment of the Management server role to a computer with Remote Desktop Sharing (RDS) enabled is not supported.</span></span>

 

### <a href="" id="management-server-hardware-requirements-"></a><span data-ttu-id="ec19b-135">管理服务器硬件要求</span><span class="sxs-lookup"><span data-stu-id="ec19b-135">Management server hardware requirements</span></span>

-   <span data-ttu-id="ec19b-136">处理器-1.4 GHz 或更快的64位（x64）处理器</span><span class="sxs-lookup"><span data-stu-id="ec19b-136">Processor—1.4 GHz or faster, 64-bit (x64) processor</span></span>

-   <span data-ttu-id="ec19b-137">RAM-1 GB RAM （64位）</span><span class="sxs-lookup"><span data-stu-id="ec19b-137">RAM—1 GB RAM (64-bit)</span></span>

-   <span data-ttu-id="ec19b-138">磁盘空间-200 MB 可用硬盘空间，不包括内容目录</span><span class="sxs-lookup"><span data-stu-id="ec19b-138">Disk space—200 MB available hard disk space, not including the content directory</span></span>

### <span data-ttu-id="ec19b-139">管理服务器数据库要求</span><span class="sxs-lookup"><span data-stu-id="ec19b-139">Management server database requirements</span></span>

<span data-ttu-id="ec19b-140">下表列出了 app-v 5.0 SP3 管理数据库安装支持的 SQL Server 版本。</span><span class="sxs-lookup"><span data-stu-id="ec19b-140">The following table lists the SQL Server versions that are supported for the App-V 5.0 SP3 Management database installation.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ec19b-141">SQL Server 版本</span><span class="sxs-lookup"><span data-stu-id="ec19b-141">SQL Server version</span></span></th>
<th align="left"><span data-ttu-id="ec19b-142">Service pack</span><span class="sxs-lookup"><span data-stu-id="ec19b-142">Service pack</span></span></th>
<th align="left"><span data-ttu-id="ec19b-143">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="ec19b-143">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ec19b-144">Microsoft SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="ec19b-144">Microsoft SQL Server 2014</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ec19b-145">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="ec19b-145">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ec19b-146">Microsoft SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="ec19b-146">Microsoft SQL Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="ec19b-147">SP2</span><span class="sxs-lookup"><span data-stu-id="ec19b-147">SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="ec19b-148">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="ec19b-148">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ec19b-149">Microsoft SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="ec19b-149">Microsoft SQL Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="ec19b-150">又</span><span class="sxs-lookup"><span data-stu-id="ec19b-150">SP3</span></span></p></td>
<td align="left"><p><span data-ttu-id="ec19b-151">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="ec19b-151">32-bit or 64-bit</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="ec19b-152">发布服务器操作系统要求</span><span class="sxs-lookup"><span data-stu-id="ec19b-152">Publishing server operating system requirements</span></span>

<span data-ttu-id="ec19b-153">下表列出了 app-v 5.0 SP3 发布服务器安装支持的操作系统。</span><span class="sxs-lookup"><span data-stu-id="ec19b-153">The following table lists the operating systems that are supported for the App-V 5.0 SP3 Publishing server installation.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ec19b-154">操作系统</span><span class="sxs-lookup"><span data-stu-id="ec19b-154">Operating system</span></span></th>
<th align="left"><span data-ttu-id="ec19b-155">Service Pack</span><span class="sxs-lookup"><span data-stu-id="ec19b-155">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="ec19b-156">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="ec19b-156">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ec19b-157">Microsoft Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="ec19b-157">Microsoft Windows Server 2012 R2</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ec19b-158">64 位</span><span class="sxs-lookup"><span data-stu-id="ec19b-158">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ec19b-159">Microsoft Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="ec19b-159">Microsoft Windows Server 2012</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ec19b-160">64 位</span><span class="sxs-lookup"><span data-stu-id="ec19b-160">64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ec19b-161">Microsoft Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="ec19b-161">Microsoft Windows Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="ec19b-162">SP1</span><span class="sxs-lookup"><span data-stu-id="ec19b-162">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="ec19b-163">64 位</span><span class="sxs-lookup"><span data-stu-id="ec19b-163">64-bit</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="publishing-server-hardware-requirements-"></a><span data-ttu-id="ec19b-164">发布服务器硬件要求</span><span class="sxs-lookup"><span data-stu-id="ec19b-164">Publishing server hardware requirements</span></span>

<span data-ttu-id="ec19b-165">App-v 除了在 Windows Server 之外还添加了其他要求。</span><span class="sxs-lookup"><span data-stu-id="ec19b-165">App-V adds no additional requirements beyond those of Windows Server.</span></span>

-   <span data-ttu-id="ec19b-166">处理器-1.4 GHz 或更快的64位（x64）处理器</span><span class="sxs-lookup"><span data-stu-id="ec19b-166">Processor—1.4 GHz or faster, 64-bit (x64) processor</span></span>

-   <span data-ttu-id="ec19b-167">RAM-2 GB RAM （64位）</span><span class="sxs-lookup"><span data-stu-id="ec19b-167">RAM—2 GB RAM (64-bit)</span></span>

-   <span data-ttu-id="ec19b-168">磁盘空间-200 MB 可用硬盘空间，不包括内容目录</span><span class="sxs-lookup"><span data-stu-id="ec19b-168">Disk space—200 MB available hard disk space, not including the content directory</span></span>

### <span data-ttu-id="ec19b-169">报表服务器操作系统要求</span><span class="sxs-lookup"><span data-stu-id="ec19b-169">Reporting server operating system requirements</span></span>

<span data-ttu-id="ec19b-170">下表列出了 app-v 5.0 SP3 报告服务器安装支持的操作系统。</span><span class="sxs-lookup"><span data-stu-id="ec19b-170">The following table lists the operating systems that are supported for the App-V 5.0 SP3 Reporting server installation.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ec19b-171">操作系统</span><span class="sxs-lookup"><span data-stu-id="ec19b-171">Operating system</span></span></th>
<th align="left"><span data-ttu-id="ec19b-172">Service Pack</span><span class="sxs-lookup"><span data-stu-id="ec19b-172">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="ec19b-173">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="ec19b-173">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ec19b-174">Microsoft Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="ec19b-174">Microsoft Windows Server 2012 R2</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ec19b-175">64 位</span><span class="sxs-lookup"><span data-stu-id="ec19b-175">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ec19b-176">Microsoft Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="ec19b-176">Microsoft Windows Server 2012</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ec19b-177">64 位</span><span class="sxs-lookup"><span data-stu-id="ec19b-177">64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ec19b-178">Microsoft Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="ec19b-178">Microsoft Windows Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="ec19b-179">SP1</span><span class="sxs-lookup"><span data-stu-id="ec19b-179">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="ec19b-180">64 位</span><span class="sxs-lookup"><span data-stu-id="ec19b-180">64-bit</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="reporting-server-hardware-requirements-"></a><span data-ttu-id="ec19b-181">报告服务器硬件要求</span><span class="sxs-lookup"><span data-stu-id="ec19b-181">Reporting server hardware requirements</span></span>

<span data-ttu-id="ec19b-182">App-v 除了在 Windows Server 之外还添加了其他要求。</span><span class="sxs-lookup"><span data-stu-id="ec19b-182">App-V adds no additional requirements beyond those of Windows Server.</span></span>

-   <span data-ttu-id="ec19b-183">处理器-1.4 GHz 或更快的64位（x64）处理器</span><span class="sxs-lookup"><span data-stu-id="ec19b-183">Processor—1.4 GHz or faster, 64-bit (x64) processor</span></span>

-   <span data-ttu-id="ec19b-184">RAM-2 GB RAM （64位）</span><span class="sxs-lookup"><span data-stu-id="ec19b-184">RAM—2 GB RAM (64-bit)</span></span>

-   <span data-ttu-id="ec19b-185">磁盘空间-200 MB 可用硬盘空间</span><span class="sxs-lookup"><span data-stu-id="ec19b-185">Disk space—200 MB available hard disk space</span></span>

### <span data-ttu-id="ec19b-186">报表服务器数据库要求</span><span class="sxs-lookup"><span data-stu-id="ec19b-186">Reporting server database requirements</span></span>

<span data-ttu-id="ec19b-187">下表列出了 app-v 5.0 SP3 报告数据库安装支持的 SQL Server 版本。</span><span class="sxs-lookup"><span data-stu-id="ec19b-187">The following table lists the SQL Server versions that are supported for the App-V 5.0 SP3 Reporting database installation.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ec19b-188">SQL Server 版本</span><span class="sxs-lookup"><span data-stu-id="ec19b-188">SQL Server version</span></span></th>
<th align="left"><span data-ttu-id="ec19b-189">Service pack</span><span class="sxs-lookup"><span data-stu-id="ec19b-189">Service pack</span></span></th>
<th align="left"><span data-ttu-id="ec19b-190">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="ec19b-190">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ec19b-191">Microsoft SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="ec19b-191">Microsoft SQL Server 2014</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ec19b-192">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="ec19b-192">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ec19b-193">Microsoft SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="ec19b-193">Microsoft SQL Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="ec19b-194">SP2</span><span class="sxs-lookup"><span data-stu-id="ec19b-194">SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="ec19b-195">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="ec19b-195">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ec19b-196">Microsoft SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="ec19b-196">Microsoft SQL Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="ec19b-197">又</span><span class="sxs-lookup"><span data-stu-id="ec19b-197">SP3</span></span></p></td>
<td align="left"><p><span data-ttu-id="ec19b-198">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="ec19b-198">32-bit or 64-bit</span></span></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-client-supp-cfgs"></a><span data-ttu-id="ec19b-199">App-v 客户端系统要求</span><span class="sxs-lookup"><span data-stu-id="ec19b-199">App-V client system requirements</span></span>


<span data-ttu-id="ec19b-200">下表列出了 app-v 5.0 SP3 客户端安装支持的操作系统。</span><span class="sxs-lookup"><span data-stu-id="ec19b-200">The following table lists the operating systems that are supported for the App-V 5.0 SP3 client installation.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ec19b-201">操作系统</span><span class="sxs-lookup"><span data-stu-id="ec19b-201">Operating system</span></span></th>
<th align="left"><span data-ttu-id="ec19b-202">Service pack</span><span class="sxs-lookup"><span data-stu-id="ec19b-202">Service pack</span></span></th>
<th align="left"><span data-ttu-id="ec19b-203">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="ec19b-203">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ec19b-204">Microsoft Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="ec19b-204">Microsoft Windows8.1</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ec19b-205">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="ec19b-205">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ec19b-206">Microsoft Windows8</span><span class="sxs-lookup"><span data-stu-id="ec19b-206">Microsoft Windows8</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ec19b-207">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="ec19b-207">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ec19b-208">Windows7</span><span class="sxs-lookup"><span data-stu-id="ec19b-208">Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="ec19b-209">SP1</span><span class="sxs-lookup"><span data-stu-id="ec19b-209">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="ec19b-210">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="ec19b-210">32-bit or 64-bit</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="ec19b-211">以下 App-v 客户端安装方案不受支持，但所述除外：</span><span class="sxs-lookup"><span data-stu-id="ec19b-211">The following App-V client installation scenarios are not supported, except as noted:</span></span>

-   <span data-ttu-id="ec19b-212">运行 Windows Server 的计算机</span><span class="sxs-lookup"><span data-stu-id="ec19b-212">Computers that run Windows Server</span></span>

-   <span data-ttu-id="ec19b-213">运行 App-v 4.6 SP1 或更早版本的计算机</span><span class="sxs-lookup"><span data-stu-id="ec19b-213">Computers that run App-V4.6SP1 or earlier versions</span></span>

-   <span data-ttu-id="ec19b-214">只有启用了 RDS 的服务器才支持 app-v 5.0 SP3 远程桌面服务客户端</span><span class="sxs-lookup"><span data-stu-id="ec19b-214">The App-V 5.0 SP3 Remote Desktop services client is supported only for RDS-enabled servers</span></span>

### <a href="" id="app-v-client-hardware-requirements-"></a><span data-ttu-id="ec19b-215">App-v 客户端硬件要求</span><span class="sxs-lookup"><span data-stu-id="ec19b-215">App-V client hardware requirements</span></span>

<span data-ttu-id="ec19b-216">以下列表显示了 app-v 5.0 SP3 客户端安装所支持的硬件配置。</span><span class="sxs-lookup"><span data-stu-id="ec19b-216">The following list displays the supported hardware configuration for the App-V 5.0 SP3 client installation.</span></span>

-   <span data-ttu-id="ec19b-217">处理器-1.4 GHz 或更快的32位（x86）或64位（x64）处理器</span><span class="sxs-lookup"><span data-stu-id="ec19b-217">Processor— 1.4 GHz or faster 32-bit (x86) or 64-bit (x64) processor</span></span>

-   <span data-ttu-id="ec19b-218">RAM-1 GB （32位）或 2 GB （64位）</span><span class="sxs-lookup"><span data-stu-id="ec19b-218">RAM— 1 GB (32-bit) or 2 GB (64-bit)</span></span>

-   <span data-ttu-id="ec19b-219">磁盘-100 MB 用于安装，不包括虚拟化应用程序使用的磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="ec19b-219">Disk— 100 MB for installation, not including the disk space that is used by virtualized applications.</span></span>

## <span data-ttu-id="ec19b-220">远程桌面服务客户端系统要求</span><span class="sxs-lookup"><span data-stu-id="ec19b-220">Remote Desktop Services client system requirements</span></span>


<span data-ttu-id="ec19b-221">下表列出了 App-v 5.0 SP3 远程桌面服务（RDS）客户端安装支持的操作系统。</span><span class="sxs-lookup"><span data-stu-id="ec19b-221">The following table lists the operating systems that are supported for App-V 5.0 SP3 Remote Desktop Services (RDS) client installation.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ec19b-222">操作系统</span><span class="sxs-lookup"><span data-stu-id="ec19b-222">Operating system</span></span></th>
<th align="left"><span data-ttu-id="ec19b-223">Service Pack</span><span class="sxs-lookup"><span data-stu-id="ec19b-223">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="ec19b-224">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="ec19b-224">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ec19b-225">Microsoft Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="ec19b-225">Microsoft Windows Server 2012 R2</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ec19b-226">64 位</span><span class="sxs-lookup"><span data-stu-id="ec19b-226">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ec19b-227">Microsoft Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="ec19b-227">Microsoft Windows Server 2012</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ec19b-228">64 位</span><span class="sxs-lookup"><span data-stu-id="ec19b-228">64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ec19b-229">Microsoft Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="ec19b-229">Microsoft Windows Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="ec19b-230">SP1</span><span class="sxs-lookup"><span data-stu-id="ec19b-230">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="ec19b-231">64 位</span><span class="sxs-lookup"><span data-stu-id="ec19b-231">64-bit</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="ec19b-232">远程桌面服务客户端硬件要求</span><span class="sxs-lookup"><span data-stu-id="ec19b-232">Remote Desktop Services client hardware requirements</span></span>

<span data-ttu-id="ec19b-233">App-v 除了在 Windows Server 之外还添加了其他要求。</span><span class="sxs-lookup"><span data-stu-id="ec19b-233">App-V adds no additional requirements beyond those of Windows Server.</span></span>

-   <span data-ttu-id="ec19b-234">处理器-1.4 GHz 或更快的64位（x64）处理器</span><span class="sxs-lookup"><span data-stu-id="ec19b-234">Processor—1.4 GHz or faster, 64-bit (x64) processor</span></span>

-   <span data-ttu-id="ec19b-235">RAM-2 GB RAM （64位）</span><span class="sxs-lookup"><span data-stu-id="ec19b-235">RAM—2 GB RAM (64-bit)</span></span>

-   <span data-ttu-id="ec19b-236">磁盘空间-200 MB 可用硬盘空间</span><span class="sxs-lookup"><span data-stu-id="ec19b-236">Disk space—200 MB available hard disk space</span></span>

## <span data-ttu-id="ec19b-237">Sequencer 系统要求</span><span class="sxs-lookup"><span data-stu-id="ec19b-237">Sequencer system requirements</span></span>


<span data-ttu-id="ec19b-238">下表列出了 app-v 5.0 SP3 Sequencer 安装支持的操作系统。</span><span class="sxs-lookup"><span data-stu-id="ec19b-238">The following table lists the operating systems that are supported for the App-V 5.0 SP3 Sequencer installation.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ec19b-239">操作系统</span><span class="sxs-lookup"><span data-stu-id="ec19b-239">Operating system</span></span></th>
<th align="left"><span data-ttu-id="ec19b-240">Service pack</span><span class="sxs-lookup"><span data-stu-id="ec19b-240">Service pack</span></span></th>
<th align="left"><span data-ttu-id="ec19b-241">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="ec19b-241">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ec19b-242">Microsoft Windows Server2012 R2</span><span class="sxs-lookup"><span data-stu-id="ec19b-242">Microsoft Windows Server2012 R2</span></span></p></td>
<td align="left"></td>
<td align="left"><p><span data-ttu-id="ec19b-243">64 位</span><span class="sxs-lookup"><span data-stu-id="ec19b-243">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ec19b-244">Microsoft Windows Server2012</span><span class="sxs-lookup"><span data-stu-id="ec19b-244">Microsoft Windows Server2012</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ec19b-245">64 位</span><span class="sxs-lookup"><span data-stu-id="ec19b-245">64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ec19b-246">Microsoft Windows Server2008 R2</span><span class="sxs-lookup"><span data-stu-id="ec19b-246">Microsoft Windows Server2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="ec19b-247">SP1</span><span class="sxs-lookup"><span data-stu-id="ec19b-247">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="ec19b-248">64 位</span><span class="sxs-lookup"><span data-stu-id="ec19b-248">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ec19b-249">Microsoft Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="ec19b-249">Microsoft Windows8.1</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ec19b-250">32 位和 64 位 ：</span><span class="sxs-lookup"><span data-stu-id="ec19b-250">32-bit and 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ec19b-251">Microsoft Windows8</span><span class="sxs-lookup"><span data-stu-id="ec19b-251">Microsoft Windows8</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ec19b-252">32 位和 64 位 ：</span><span class="sxs-lookup"><span data-stu-id="ec19b-252">32-bit and 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ec19b-253">Microsoft Windows7</span><span class="sxs-lookup"><span data-stu-id="ec19b-253">Microsoft Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="ec19b-254">SP1</span><span class="sxs-lookup"><span data-stu-id="ec19b-254">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="ec19b-255">32 位和 64 位 ：</span><span class="sxs-lookup"><span data-stu-id="ec19b-255">32-bit and 64-bit</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="ec19b-256">Sequencer 硬件要求</span><span class="sxs-lookup"><span data-stu-id="ec19b-256">Sequencer hardware requirements</span></span>

<span data-ttu-id="ec19b-257">有关硬件要求，请参阅 Windows 或 Windows Server 文档。</span><span class="sxs-lookup"><span data-stu-id="ec19b-257">See the Windows or Windows Server documentation for the hardware requirements.</span></span> <span data-ttu-id="ec19b-258">App-v 不增加任何其他硬件要求。</span><span class="sxs-lookup"><span data-stu-id="ec19b-258">App-V adds no additional hardware requirements.</span></span>

## <a href="" id="bkmk-supp-ver-sccm"></a><span data-ttu-id="ec19b-259">System Center Configuration Manager 支持的版本</span><span class="sxs-lookup"><span data-stu-id="ec19b-259">Supported versions of System Center Configuration Manager</span></span>


<span data-ttu-id="ec19b-260">App-v 客户端支持以下版本的 System Center Configuration Manager：</span><span class="sxs-lookup"><span data-stu-id="ec19b-260">The App-V client supports the following versions of System Center Configuration Manager:</span></span>

-   <span data-ttu-id="ec19b-261">MicrosoftSystemCenter2012 ConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="ec19b-261">MicrosoftSystemCenter2012 ConfigurationManager</span></span>

-   <span data-ttu-id="ec19b-262">System Center 2012 R2 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="ec19b-262">System Center 2012 R2 Configuration Manager</span></span>

-   <span data-ttu-id="ec19b-263">System Center 2012 R2 Configuration Manager SP1</span><span class="sxs-lookup"><span data-stu-id="ec19b-263">System Center 2012 R2 Configuration Manager SP1</span></span>

<span data-ttu-id="ec19b-264">有关 Configuration Manager 如何与 app-v 集成的详细信息，请参阅[规划与 Configuration Manager 的 App-v 集成](https://technet.microsoft.com/library/jj822982.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ec19b-264">For more information about how Configuration Manager integrates with App-V, see [Planning for App-V Integration with Configuration Manager](https://technet.microsoft.com/library/jj822982.aspx).</span></span>






## <span data-ttu-id="ec19b-265">相关主题</span><span class="sxs-lookup"><span data-stu-id="ec19b-265">Related topics</span></span>


[<span data-ttu-id="ec19b-266">计划部署 App-V</span><span class="sxs-lookup"><span data-stu-id="ec19b-266">Planning to Deploy App-V</span></span>](planning-to-deploy-app-v.md)

[<span data-ttu-id="ec19b-267">App-V 5.0 SP3 先决条件</span><span class="sxs-lookup"><span data-stu-id="ec19b-267">App-V 5.0 SP3 Prerequisites</span></span>](app-v-50-sp3-prerequisites.md)

 

 





