---
title: App-V 5.1 支持的配置
description: App-V 5.1 支持的配置
author: dansimp
ms.assetid: 8b8db63b-f71c-4ae9-80e7-a6752334e1f6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 04/02/2020
ms.openlocfilehash: fbda364de66b1f7b8730dca38f864a84f7848e58
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798617"
---
# <span data-ttu-id="0cf19-103">App-V 5.1 支持的配置</span><span class="sxs-lookup"><span data-stu-id="0cf19-103">App-V 5.1 Supported Configurations</span></span>

><span data-ttu-id="0cf19-104">适用于： Windows 10 版本 1607;Windows Server 2019;Windows Server 2016;Windows Server 2012 R2;Windows Server 2012;Windows Server 2008 R2 （扩展安全更新）</span><span class="sxs-lookup"><span data-stu-id="0cf19-104">Applies to: Windows 10, version 1607; Window Server 2019; Windows Server 2016; Windows Server 2012 R2; Windows Server 2012; Windows Server 2008 R2 (Extended Security Update)</span></span>

<span data-ttu-id="0cf19-105">本主题指定在你的环境中安装和运行 Microsoft Application Virtualization （app-v）5.1 的要求。</span><span class="sxs-lookup"><span data-stu-id="0cf19-105">This topic specifies the requirements to install and run Microsoft Application Virtualization (App-V) 5.1 in your environment.</span></span>

## <span data-ttu-id="0cf19-106">App-v Server 系统要求</span><span class="sxs-lookup"><span data-stu-id="0cf19-106">App-V Server system requirements</span></span>

<span data-ttu-id="0cf19-107">本部分列出了所有 app-v 服务器组件的操作系统和硬件要求。</span><span class="sxs-lookup"><span data-stu-id="0cf19-107">This section lists the operating system and hardware requirements for all of the App-V Server components.</span></span>

### <span data-ttu-id="0cf19-108">不支持的 app-v 5.1 服务器方案</span><span class="sxs-lookup"><span data-stu-id="0cf19-108">Unsupported App-V 5.1 Server scenarios</span></span>

<span data-ttu-id="0cf19-109">App-v 5.1 服务器不支持以下方案：</span><span class="sxs-lookup"><span data-stu-id="0cf19-109">The App-V 5.1 Server does not support the following scenarios:</span></span>

-   <span data-ttu-id="0cf19-110">部署到运行 Microsoft Windows Server Core 的计算机。</span><span class="sxs-lookup"><span data-stu-id="0cf19-110">Deployment to a computer that runs Microsoft Windows Server Core.</span></span>

-   <span data-ttu-id="0cf19-111">部署到运行早期版本的 App-v 5.1 Server 组件的计算机。</span><span class="sxs-lookup"><span data-stu-id="0cf19-111">Deployment to a computer that runs a previous version of App-V 5.1 Server components.</span></span> <span data-ttu-id="0cf19-112">你可以仅使用 app-v 4.5 轻型流服务器（LWS）服务器与 app-v 5.1 并行安装。</span><span class="sxs-lookup"><span data-stu-id="0cf19-112">You can install App-V 5.1 side by side with the App-V4.5 Lightweight Streaming Server (LWS) server only.</span></span> <span data-ttu-id="0cf19-113">不支持使用 app-v 4.5 应用程序虚拟管理服务（HWS）服务器并行部署 app-v。</span><span class="sxs-lookup"><span data-stu-id="0cf19-113">Deployment of App-V side by side with the App-V 4.5 Application Virtualization Management Service (HWS) server is not supported.</span></span>

-   <span data-ttu-id="0cf19-114">部署到运行 Microsoft SQL Server Express edition 的计算机。</span><span class="sxs-lookup"><span data-stu-id="0cf19-114">Deployment to a computer that runs Microsoft SQL Server Express edition.</span></span>

-   <span data-ttu-id="0cf19-115">部署到域控制器。</span><span class="sxs-lookup"><span data-stu-id="0cf19-115">Deployment to a domain controller.</span></span>

-   <span data-ttu-id="0cf19-116">短路径。</span><span class="sxs-lookup"><span data-stu-id="0cf19-116">Short paths.</span></span> <span data-ttu-id="0cf19-117">如果您计划使用短路径，则必须创建新卷。</span><span class="sxs-lookup"><span data-stu-id="0cf19-117">If you plan to use a short path, you must create a new volume.</span></span>

### <span data-ttu-id="0cf19-118">管理服务器操作系统要求</span><span class="sxs-lookup"><span data-stu-id="0cf19-118">Management server operating system requirements</span></span>

<span data-ttu-id="0cf19-119">下表列出了 app-v 5.1 管理服务器安装支持的操作系统。</span><span class="sxs-lookup"><span data-stu-id="0cf19-119">The following table lists the operating systems that are supported for the App-V 5.1 Management server installation.</span></span>

> [!NOTE]
> <span data-ttu-id="0cf19-120">Microsoft 提供对当前服务包的支持，在某些情况下，还提供了之前的服务包。</span><span class="sxs-lookup"><span data-stu-id="0cf19-120">Microsoft provides support for the current service pack and, in some cases, the immediately preceding service pack.</span></span> <span data-ttu-id="0cf19-121">若要查找产品的支持时间表，请参阅[支持生命周期的服务包](https://go.microsoft.com/fwlink/p/?LinkId=31975)。</span><span class="sxs-lookup"><span data-stu-id="0cf19-121">To find the support timelines for your product, see the [Lifecycle Supported Service Packs](https://go.microsoft.com/fwlink/p/?LinkId=31975).</span></span> <span data-ttu-id="0cf19-122">有关详细信息，请参阅[Microsoft 支持生命周期支持策略常见问题](https://go.microsoft.com/fwlink/p/?LinkId=31976)。</span><span class="sxs-lookup"><span data-stu-id="0cf19-122">See [Microsoft Support Lifecycle Support Policy FAQ](https://go.microsoft.com/fwlink/p/?LinkId=31976) for more information.</span></span>

 | <span data-ttu-id="0cf19-123">操作系统</span><span class="sxs-lookup"><span data-stu-id="0cf19-123">Operating System</span></span>                 | <span data-ttu-id="0cf19-124">Service Pack</span><span class="sxs-lookup"><span data-stu-id="0cf19-124">Service Pack</span></span> | <span data-ttu-id="0cf19-125">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="0cf19-125">System Architecture</span></span> |
|----------------------------------|--------------|---------------------|
| <span data-ttu-id="0cf19-126">Microsoft Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="0cf19-126">Microsoft Windows Server 2019</span></span>    |              |        <span data-ttu-id="0cf19-127">64 位</span><span class="sxs-lookup"><span data-stu-id="0cf19-127">64-bit</span></span>       |
| <span data-ttu-id="0cf19-128">Microsoft Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="0cf19-128">Microsoft Windows Server 2016</span></span>    |              |        <span data-ttu-id="0cf19-129">64 位</span><span class="sxs-lookup"><span data-stu-id="0cf19-129">64-bit</span></span>       |
| <span data-ttu-id="0cf19-130">Microsoft Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="0cf19-130">Microsoft Windows Server 2012 R2</span></span> |              |        <span data-ttu-id="0cf19-131">64 位</span><span class="sxs-lookup"><span data-stu-id="0cf19-131">64-bit</span></span>       |
| <span data-ttu-id="0cf19-132">Microsoft Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="0cf19-132">Microsoft Windows Server 2012</span></span>    |              |        <span data-ttu-id="0cf19-133">64 位</span><span class="sxs-lookup"><span data-stu-id="0cf19-133">64-bit</span></span>       |
| <span data-ttu-id="0cf19-134">Microsoft Windows Server 2008 R2[扩展安全更新](https://www.microsoft.com/windows-server/extended-security-updates)</span><span class="sxs-lookup"><span data-stu-id="0cf19-134">Microsoft Windows Server 2008 R2 [Extended Security Update](https://www.microsoft.com/windows-server/extended-security-updates)</span></span>|      <span data-ttu-id="0cf19-135">SP1</span><span class="sxs-lookup"><span data-stu-id="0cf19-135">SP1</span></span>     |        <span data-ttu-id="0cf19-136">64 位</span><span class="sxs-lookup"><span data-stu-id="0cf19-136">64-bit</span></span>       |
 

<span data-ttu-id="0cf19-137">**重要提示** 不支持将管理服务器角色部署到启用了远程桌面共享（RDS）的计算机。</span><span class="sxs-lookup"><span data-stu-id="0cf19-137">**Important** Deployment of the Management server role to a computer with Remote Desktop Sharing (RDS) enabled is not supported.</span></span>

 

### <a href="" id="management-server-hardware-requirements-"></a><span data-ttu-id="0cf19-138">管理服务器硬件要求</span><span class="sxs-lookup"><span data-stu-id="0cf19-138">Management server hardware requirements</span></span>

-   <span data-ttu-id="0cf19-139">处理器-1.4 GHz 或更快的64位（x64）处理器</span><span class="sxs-lookup"><span data-stu-id="0cf19-139">Processor—1.4 GHz or faster, 64-bit (x64) processor</span></span>

-   <span data-ttu-id="0cf19-140">RAM-1 GB RAM （64位）</span><span class="sxs-lookup"><span data-stu-id="0cf19-140">RAM—1 GB RAM (64-bit)</span></span>

-   <span data-ttu-id="0cf19-141">磁盘空间-200 MB 可用硬盘空间，不包括内容目录</span><span class="sxs-lookup"><span data-stu-id="0cf19-141">Disk space—200 MB available hard disk space, not including the content directory</span></span>

### <span data-ttu-id="0cf19-142">管理服务器数据库要求</span><span class="sxs-lookup"><span data-stu-id="0cf19-142">Management server database requirements</span></span>

<span data-ttu-id="0cf19-143">下表列出了 app-v 5.1 管理数据库安装支持的 SQL Server 版本。</span><span class="sxs-lookup"><span data-stu-id="0cf19-143">The following table lists the SQL Server versions that are supported for the App-V 5.1 Management database installation.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="0cf19-144">SQL Server 版本</span><span class="sxs-lookup"><span data-stu-id="0cf19-144">SQL Server version</span></span></th>
<th align="left"><span data-ttu-id="0cf19-145">Service pack</span><span class="sxs-lookup"><span data-stu-id="0cf19-145">Service pack</span></span></th>
<th align="left"><span data-ttu-id="0cf19-146">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="0cf19-146">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="even">
<td align="left"><p><span data-ttu-id="0cf19-147">Microsoft SQL Server 2019</span><span class="sxs-lookup"><span data-stu-id="0cf19-147">Microsoft SQL Server 2019</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="0cf19-148">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="0cf19-148">32-bit or 64-bit</span></span></p></td>
</tr>

<tr class="odd">
<td align="left"><p><span data-ttu-id="0cf19-149">Microsoft SQL Server 2017</span><span class="sxs-lookup"><span data-stu-id="0cf19-149">Microsoft SQL Server 2017</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="0cf19-150">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="0cf19-150">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0cf19-151">Microsoft SQL Server 2016</span><span class="sxs-lookup"><span data-stu-id="0cf19-151">Microsoft SQL Server 2016</span></span></p></td>
<td align="left"><p><span data-ttu-id="0cf19-152">SP2</span><span class="sxs-lookup"><span data-stu-id="0cf19-152">SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="0cf19-153">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="0cf19-153">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0cf19-154">Microsoft SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="0cf19-154">Microsoft SQL Server 2014</span></span></p></td>
<td align="left"><p><span data-ttu-id="0cf19-155">SP2</span><span class="sxs-lookup"><span data-stu-id="0cf19-155">SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="0cf19-156">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="0cf19-156">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0cf19-157">Microsoft SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="0cf19-157">Microsoft SQL Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="0cf19-158">SP2</span><span class="sxs-lookup"><span data-stu-id="0cf19-158">SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="0cf19-159">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="0cf19-159">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0cf19-160">Microsoft SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="0cf19-160">Microsoft SQL Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="0cf19-161">又</span><span class="sxs-lookup"><span data-stu-id="0cf19-161">SP3</span></span></p></td>
<td align="left"><p><span data-ttu-id="0cf19-162">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="0cf19-162">32-bit or 64-bit</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="0cf19-163">有关 SQL server 2016 或更高版本的用户配置文件的详细信息，请参阅[支持文章](https://support.microsoft.com/help/4548751/app-v-server-publishing-might-fail-when-you-apply-user-configuration-f)。</span><span class="sxs-lookup"><span data-stu-id="0cf19-163">For more information on user configuration files with SQL server 2016 or later, see the [support article](https://support.microsoft.com/help/4548751/app-v-server-publishing-might-fail-when-you-apply-user-configuration-f).</span></span>

### <span data-ttu-id="0cf19-164">发布服务器操作系统要求</span><span class="sxs-lookup"><span data-stu-id="0cf19-164">Publishing server operating system requirements</span></span>

<span data-ttu-id="0cf19-165">下表列出了 app-v 5.1 发布服务器安装支持的操作系统。</span><span class="sxs-lookup"><span data-stu-id="0cf19-165">The following table lists the operating systems that are supported for the App-V 5.1 Publishing server installation.</span></span>

| <span data-ttu-id="0cf19-166">操作系统</span><span class="sxs-lookup"><span data-stu-id="0cf19-166">Operating System</span></span>                 | <span data-ttu-id="0cf19-167">Service Pack</span><span class="sxs-lookup"><span data-stu-id="0cf19-167">Service Pack</span></span> | <span data-ttu-id="0cf19-168">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="0cf19-168">System Architecture</span></span> |
|----------------------------------|--------------|---------------------|
| <span data-ttu-id="0cf19-169">Microsoft Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="0cf19-169">Microsoft Windows Server 2019</span></span>    |              |        <span data-ttu-id="0cf19-170">64 位</span><span class="sxs-lookup"><span data-stu-id="0cf19-170">64-bit</span></span>       |
| <span data-ttu-id="0cf19-171">Microsoft Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="0cf19-171">Microsoft Windows Server 2016</span></span>    |              |        <span data-ttu-id="0cf19-172">64 位</span><span class="sxs-lookup"><span data-stu-id="0cf19-172">64-bit</span></span>       |
| <span data-ttu-id="0cf19-173">Microsoft Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="0cf19-173">Microsoft Windows Server 2012 R2</span></span> |              |        <span data-ttu-id="0cf19-174">64 位</span><span class="sxs-lookup"><span data-stu-id="0cf19-174">64-bit</span></span>       |
| <span data-ttu-id="0cf19-175">Microsoft Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="0cf19-175">Microsoft Windows Server 2012</span></span>    |              |        <span data-ttu-id="0cf19-176">64 位</span><span class="sxs-lookup"><span data-stu-id="0cf19-176">64-bit</span></span>       |
| <span data-ttu-id="0cf19-177">Microsoft Windows Server 2008 R2[扩展安全更新](https://www.microsoft.com/windows-server/extended-security-updates)</span><span class="sxs-lookup"><span data-stu-id="0cf19-177">Microsoft Windows Server 2008 R2 [Extended Security Update](https://www.microsoft.com/windows-server/extended-security-updates)</span></span> |      <span data-ttu-id="0cf19-178">SP1</span><span class="sxs-lookup"><span data-stu-id="0cf19-178">SP1</span></span>     |        <span data-ttu-id="0cf19-179">64 位</span><span class="sxs-lookup"><span data-stu-id="0cf19-179">64-bit</span></span>       |

### <a href="" id="publishing-server-hardware-requirements-"></a><span data-ttu-id="0cf19-180">发布服务器硬件要求</span><span class="sxs-lookup"><span data-stu-id="0cf19-180">Publishing server hardware requirements</span></span>

<span data-ttu-id="0cf19-181">App-v 除了在 Windows Server 之外还添加了其他要求。</span><span class="sxs-lookup"><span data-stu-id="0cf19-181">App-V adds no additional requirements beyond those of Windows Server.</span></span>

-   <span data-ttu-id="0cf19-182">处理器-1.4 GHz 或更快的64位（x64）处理器</span><span class="sxs-lookup"><span data-stu-id="0cf19-182">Processor—1.4 GHz or faster, 64-bit (x64) processor</span></span>

-   <span data-ttu-id="0cf19-183">RAM-2 GB RAM （64位）</span><span class="sxs-lookup"><span data-stu-id="0cf19-183">RAM—2 GB RAM (64-bit)</span></span>

-   <span data-ttu-id="0cf19-184">磁盘空间-200 MB 可用硬盘空间，不包括内容目录</span><span class="sxs-lookup"><span data-stu-id="0cf19-184">Disk space—200 MB available hard disk space, not including the content directory</span></span>

### <span data-ttu-id="0cf19-185">报表服务器操作系统要求</span><span class="sxs-lookup"><span data-stu-id="0cf19-185">Reporting server operating system requirements</span></span>

<span data-ttu-id="0cf19-186">下表列出了 app-v 5.1 Reporting server 安装支持的操作系统。</span><span class="sxs-lookup"><span data-stu-id="0cf19-186">The following table lists the operating systems that are supported for the App-V 5.1 Reporting server installation.</span></span>

| <span data-ttu-id="0cf19-187">操作系统</span><span class="sxs-lookup"><span data-stu-id="0cf19-187">Operating System</span></span>                 | <span data-ttu-id="0cf19-188">Service Pack</span><span class="sxs-lookup"><span data-stu-id="0cf19-188">Service Pack</span></span> | <span data-ttu-id="0cf19-189">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="0cf19-189">System Architecture</span></span> |
|----------------------------------|--------------|---------------------|
| <span data-ttu-id="0cf19-190">Microsoft Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="0cf19-190">Microsoft Windows Server 2019</span></span>    |              |        <span data-ttu-id="0cf19-191">64 位</span><span class="sxs-lookup"><span data-stu-id="0cf19-191">64-bit</span></span>       |
| <span data-ttu-id="0cf19-192">Microsoft Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="0cf19-192">Microsoft Windows Server 2016</span></span>    |              |        <span data-ttu-id="0cf19-193">64 位</span><span class="sxs-lookup"><span data-stu-id="0cf19-193">64-bit</span></span>       |
| <span data-ttu-id="0cf19-194">Microsoft Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="0cf19-194">Microsoft Windows Server 2012 R2</span></span> |              |        <span data-ttu-id="0cf19-195">64 位</span><span class="sxs-lookup"><span data-stu-id="0cf19-195">64-bit</span></span>       |
| <span data-ttu-id="0cf19-196">Microsoft Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="0cf19-196">Microsoft Windows Server 2012</span></span>    |              |        <span data-ttu-id="0cf19-197">64 位</span><span class="sxs-lookup"><span data-stu-id="0cf19-197">64-bit</span></span>       |
| <span data-ttu-id="0cf19-198">Microsoft Windows Server 2008 R2[扩展安全更新](https://www.microsoft.com/windows-server/extended-security-updates)</span><span class="sxs-lookup"><span data-stu-id="0cf19-198">Microsoft Windows Server 2008 R2 [Extended Security Update](https://www.microsoft.com/windows-server/extended-security-updates)</span></span> |      <span data-ttu-id="0cf19-199">SP1</span><span class="sxs-lookup"><span data-stu-id="0cf19-199">SP1</span></span>     |        <span data-ttu-id="0cf19-200">64 位</span><span class="sxs-lookup"><span data-stu-id="0cf19-200">64-bit</span></span>       |

### <a href="" id="reporting-server-hardware-requirements-"></a><span data-ttu-id="0cf19-201">报告服务器硬件要求</span><span class="sxs-lookup"><span data-stu-id="0cf19-201">Reporting server hardware requirements</span></span>

<span data-ttu-id="0cf19-202">App-v 除了在 Windows Server 之外还添加了其他要求。</span><span class="sxs-lookup"><span data-stu-id="0cf19-202">App-V adds no additional requirements beyond those of Windows Server.</span></span>

-   <span data-ttu-id="0cf19-203">处理器-1.4 GHz 或更快的64位（x64）处理器</span><span class="sxs-lookup"><span data-stu-id="0cf19-203">Processor—1.4 GHz or faster, 64-bit (x64) processor</span></span>

-   <span data-ttu-id="0cf19-204">RAM-2 GB RAM （64位）</span><span class="sxs-lookup"><span data-stu-id="0cf19-204">RAM—2 GB RAM (64-bit)</span></span>

-   <span data-ttu-id="0cf19-205">磁盘空间-200 MB 可用硬盘空间</span><span class="sxs-lookup"><span data-stu-id="0cf19-205">Disk space—200 MB available hard disk space</span></span>

### <span data-ttu-id="0cf19-206">报表服务器数据库要求</span><span class="sxs-lookup"><span data-stu-id="0cf19-206">Reporting server database requirements</span></span>

<span data-ttu-id="0cf19-207">下表列出了 app-v 5.1 Reporting 数据库安装支持的 SQL Server 版本。</span><span class="sxs-lookup"><span data-stu-id="0cf19-207">The following table lists the SQL Server versions that are supported for the App-V 5.1 Reporting database installation.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="0cf19-208">SQL Server 版本</span><span class="sxs-lookup"><span data-stu-id="0cf19-208">SQL Server version</span></span></th>
<th align="left"><span data-ttu-id="0cf19-209">Service pack</span><span class="sxs-lookup"><span data-stu-id="0cf19-209">Service pack</span></span></th>
<th align="left"><span data-ttu-id="0cf19-210">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="0cf19-210">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0cf19-211">Microsoft SQL Server 2017</span><span class="sxs-lookup"><span data-stu-id="0cf19-211">Microsoft SQL Server 2017</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="0cf19-212">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="0cf19-212">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0cf19-213">Microsoft SQL Server 2016</span><span class="sxs-lookup"><span data-stu-id="0cf19-213">Microsoft SQL Server 2016</span></span></p></td>
<td align="left"><p><span data-ttu-id="0cf19-214">SP2</span><span class="sxs-lookup"><span data-stu-id="0cf19-214">SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="0cf19-215">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="0cf19-215">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0cf19-216">Microsoft SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="0cf19-216">Microsoft SQL Server 2014</span></span></p></td>
<td align="left"><p><span data-ttu-id="0cf19-217">SP2</span><span class="sxs-lookup"><span data-stu-id="0cf19-217">SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="0cf19-218">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="0cf19-218">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0cf19-219">Microsoft SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="0cf19-219">Microsoft SQL Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="0cf19-220">SP2</span><span class="sxs-lookup"><span data-stu-id="0cf19-220">SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="0cf19-221">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="0cf19-221">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0cf19-222">Microsoft SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="0cf19-222">Microsoft SQL Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="0cf19-223">又</span><span class="sxs-lookup"><span data-stu-id="0cf19-223">SP3</span></span></p></td>
<td align="left"><p><span data-ttu-id="0cf19-224">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="0cf19-224">32-bit or 64-bit</span></span></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-client-supp-cfgs"></a><span data-ttu-id="0cf19-225">App-v 客户端系统要求</span><span class="sxs-lookup"><span data-stu-id="0cf19-225">App-V client system requirements</span></span>

<span data-ttu-id="0cf19-226">下表列出了 app-v 5.1 客户端安装支持的操作系统。</span><span class="sxs-lookup"><span data-stu-id="0cf19-226">The following table lists the operating systems that are supported for the App-V 5.1 client installation.</span></span>

> [!NOTE]
> <span data-ttu-id="0cf19-227">通过 Windows 10 周年版本（也称为1607版本），app-v 客户端是内置的，将阻止安装任何以前版本的 App-v 客户端</span><span class="sxs-lookup"><span data-stu-id="0cf19-227">With the Windows 10 Anniversary release (aka 1607 version), the App-V client is in-box and will block installation of any previous version of the App-V client</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="0cf19-228">操作系统</span><span class="sxs-lookup"><span data-stu-id="0cf19-228">Operating system</span></span></th>
<th align="left"><span data-ttu-id="0cf19-229">Service pack</span><span class="sxs-lookup"><span data-stu-id="0cf19-229">Service pack</span></span></th>
<th align="left"><span data-ttu-id="0cf19-230">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="0cf19-230">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0cf19-231">Microsoft Windows10 （预1607版本）</span><span class="sxs-lookup"><span data-stu-id="0cf19-231">Microsoft Windows10 (pre-1607 version)</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="0cf19-232">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="0cf19-232">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0cf19-233">Microsoft Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="0cf19-233">Microsoft Windows8.1</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="0cf19-234">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="0cf19-234">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0cf19-235">Windows7</span><span class="sxs-lookup"><span data-stu-id="0cf19-235">Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="0cf19-236">SP1</span><span class="sxs-lookup"><span data-stu-id="0cf19-236">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="0cf19-237">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="0cf19-237">32-bit or 64-bit</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="0cf19-238">以下 App-v 客户端安装方案不受支持，但所述除外：</span><span class="sxs-lookup"><span data-stu-id="0cf19-238">The following App-V client installation scenarios are not supported, except as noted:</span></span>

-   <span data-ttu-id="0cf19-239">运行 Windows Server 的计算机</span><span class="sxs-lookup"><span data-stu-id="0cf19-239">Computers that run Windows Server</span></span>

-   <span data-ttu-id="0cf19-240">运行 App-v 4.6 SP1 或更早版本的计算机</span><span class="sxs-lookup"><span data-stu-id="0cf19-240">Computers that run App-V4.6SP1 or earlier versions</span></span>

-   <span data-ttu-id="0cf19-241">只有支持 RDS 的服务器才支持 app-v 5.1 远程桌面服务客户端</span><span class="sxs-lookup"><span data-stu-id="0cf19-241">The App-V 5.1 Remote Desktop services client is supported only for RDS-enabled servers</span></span>

### <a href="" id="app-v-client-hardware-requirements-"></a><span data-ttu-id="0cf19-242">App-v 客户端硬件要求</span><span class="sxs-lookup"><span data-stu-id="0cf19-242">App-V client hardware requirements</span></span>

<span data-ttu-id="0cf19-243">以下列表显示了 app-v 5.1 客户端安装所支持的硬件配置。</span><span class="sxs-lookup"><span data-stu-id="0cf19-243">The following list displays the supported hardware configuration for the App-V 5.1 client installation.</span></span>

-   <span data-ttu-id="0cf19-244">处理器-1.4 GHz 或更快的32位（x86）或64位（x64）处理器</span><span class="sxs-lookup"><span data-stu-id="0cf19-244">Processor— 1.4 GHz or faster 32-bit (x86) or 64-bit (x64) processor</span></span>

-   <span data-ttu-id="0cf19-245">RAM-1 GB （32位）或 2 GB （64位）</span><span class="sxs-lookup"><span data-stu-id="0cf19-245">RAM— 1 GB (32-bit) or 2 GB (64-bit)</span></span>

-   <span data-ttu-id="0cf19-246">磁盘-100 MB 用于安装，不包括虚拟化应用程序使用的磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="0cf19-246">Disk— 100 MB for installation, not including the disk space that is used by virtualized applications.</span></span>

## <span data-ttu-id="0cf19-247">远程桌面服务客户端系统要求</span><span class="sxs-lookup"><span data-stu-id="0cf19-247">Remote Desktop Services client system requirements</span></span>


<span data-ttu-id="0cf19-248">下表列出了 App-v 5.1 远程桌面服务（RDS）客户端安装支持的操作系统。</span><span class="sxs-lookup"><span data-stu-id="0cf19-248">The following table lists the operating systems that are supported for App-V 5.1 Remote Desktop Services (RDS) client installation.</span></span>

| <span data-ttu-id="0cf19-249">操作系统</span><span class="sxs-lookup"><span data-stu-id="0cf19-249">Operating System</span></span>                 | <span data-ttu-id="0cf19-250">Service Pack</span><span class="sxs-lookup"><span data-stu-id="0cf19-250">Service Pack</span></span> | <span data-ttu-id="0cf19-251">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="0cf19-251">System Architecture</span></span> |
|----------------------------------|--------------|---------------------|
| <span data-ttu-id="0cf19-252">Microsoft Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="0cf19-252">Microsoft Windows Server 2019</span></span>    |              |        <span data-ttu-id="0cf19-253">64 位</span><span class="sxs-lookup"><span data-stu-id="0cf19-253">64-bit</span></span>       |
| <span data-ttu-id="0cf19-254">Microsoft Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="0cf19-254">Microsoft Windows Server 2016</span></span>    |              |        <span data-ttu-id="0cf19-255">64 位</span><span class="sxs-lookup"><span data-stu-id="0cf19-255">64-bit</span></span>       |
| <span data-ttu-id="0cf19-256">Microsoft Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="0cf19-256">Microsoft Windows Server 2012 R2</span></span> |              |        <span data-ttu-id="0cf19-257">64 位</span><span class="sxs-lookup"><span data-stu-id="0cf19-257">64-bit</span></span>       |
| <span data-ttu-id="0cf19-258">Microsoft Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="0cf19-258">Microsoft Windows Server 2012</span></span>    |              |        <span data-ttu-id="0cf19-259">64 位</span><span class="sxs-lookup"><span data-stu-id="0cf19-259">64-bit</span></span>       |
| <span data-ttu-id="0cf19-260">Microsoft Windows Server 2008 R2[扩展安全更新](https://www.microsoft.com/windows-server/extended-security-updates)</span><span class="sxs-lookup"><span data-stu-id="0cf19-260">Microsoft Windows Server 2008 R2 [Extended Security Update](https://www.microsoft.com/windows-server/extended-security-updates)</span></span> |      <span data-ttu-id="0cf19-261">SP1</span><span class="sxs-lookup"><span data-stu-id="0cf19-261">SP1</span></span>     |        <span data-ttu-id="0cf19-262">64 位</span><span class="sxs-lookup"><span data-stu-id="0cf19-262">64-bit</span></span>       |

### <span data-ttu-id="0cf19-263">远程桌面服务客户端硬件要求</span><span class="sxs-lookup"><span data-stu-id="0cf19-263">Remote Desktop Services client hardware requirements</span></span>

<span data-ttu-id="0cf19-264">App-v 除了在 Windows Server 之外还添加了其他要求。</span><span class="sxs-lookup"><span data-stu-id="0cf19-264">App-V adds no additional requirements beyond those of Windows Server.</span></span>

-   <span data-ttu-id="0cf19-265">处理器-1.4 GHz 或更快的64位（x64）处理器</span><span class="sxs-lookup"><span data-stu-id="0cf19-265">Processor—1.4 GHz or faster, 64-bit (x64) processor</span></span>

-   <span data-ttu-id="0cf19-266">RAM-2 GB RAM （64位）</span><span class="sxs-lookup"><span data-stu-id="0cf19-266">RAM—2 GB RAM (64-bit)</span></span>

-   <span data-ttu-id="0cf19-267">磁盘空间-200 MB 可用硬盘空间</span><span class="sxs-lookup"><span data-stu-id="0cf19-267">Disk space—200 MB available hard disk space</span></span>

## <span data-ttu-id="0cf19-268">Sequencer 系统要求</span><span class="sxs-lookup"><span data-stu-id="0cf19-268">Sequencer system requirements</span></span>

<span data-ttu-id="0cf19-269">下表列出了 app-v 5.1 Sequencer 安装支持的操作系统。</span><span class="sxs-lookup"><span data-stu-id="0cf19-269">The following table lists the operating systems that are supported for the App-V 5.1 Sequencer installation.</span></span>

| <span data-ttu-id="0cf19-270">操作系统</span><span class="sxs-lookup"><span data-stu-id="0cf19-270">Operating System</span></span>                 | <span data-ttu-id="0cf19-271">Service Pack</span><span class="sxs-lookup"><span data-stu-id="0cf19-271">Service Pack</span></span> | <span data-ttu-id="0cf19-272">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="0cf19-272">System Architecture</span></span> |
|----------------------------------|--------------|---------------------|
| <span data-ttu-id="0cf19-273">Microsoft Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="0cf19-273">Microsoft Windows Server 2019</span></span>    |              |        <span data-ttu-id="0cf19-274">64 位</span><span class="sxs-lookup"><span data-stu-id="0cf19-274">64-bit</span></span>       |
| <span data-ttu-id="0cf19-275">Microsoft Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="0cf19-275">Microsoft Windows Server 2016</span></span>    |              |        <span data-ttu-id="0cf19-276">64 位</span><span class="sxs-lookup"><span data-stu-id="0cf19-276">64-bit</span></span>       |
| <span data-ttu-id="0cf19-277">Microsoft Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="0cf19-277">Microsoft Windows Server 2012 R2</span></span> |              |        <span data-ttu-id="0cf19-278">64 位</span><span class="sxs-lookup"><span data-stu-id="0cf19-278">64-bit</span></span>       |
| <span data-ttu-id="0cf19-279">Microsoft Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="0cf19-279">Microsoft Windows Server 2012</span></span>    |              |        <span data-ttu-id="0cf19-280">64 位</span><span class="sxs-lookup"><span data-stu-id="0cf19-280">64-bit</span></span>       |
| <span data-ttu-id="0cf19-281">Microsoft Windows Server 2008 R2[扩展安全更新](https://www.microsoft.com/windows-server/extended-security-updates)</span><span class="sxs-lookup"><span data-stu-id="0cf19-281">Microsoft Windows Server 2008 R2 [Extended Security Update](https://www.microsoft.com/windows-server/extended-security-updates)</span></span> |      <span data-ttu-id="0cf19-282">SP1</span><span class="sxs-lookup"><span data-stu-id="0cf19-282">SP1</span></span>     |        <span data-ttu-id="0cf19-283">64 位</span><span class="sxs-lookup"><span data-stu-id="0cf19-283">64-bit</span></span>       |
| <span data-ttu-id="0cf19-284">Microsoft Windows 10</span><span class="sxs-lookup"><span data-stu-id="0cf19-284">Microsoft Windows 10</span></span>             |              | <span data-ttu-id="0cf19-285">32 位和 64 位 ：</span><span class="sxs-lookup"><span data-stu-id="0cf19-285">32-bit and 64-bit</span></span>   |
| <span data-ttu-id="0cf19-286">Microsoft Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="0cf19-286">Microsoft Windows 8.1</span></span>            |              | <span data-ttu-id="0cf19-287">32 位和 64 位 ：</span><span class="sxs-lookup"><span data-stu-id="0cf19-287">32-bit and 64-bit</span></span>   |
| <span data-ttu-id="0cf19-288">Microsoft Windows 7</span><span class="sxs-lookup"><span data-stu-id="0cf19-288">Microsoft Windows 7</span></span>              |      <span data-ttu-id="0cf19-289">SP1</span><span class="sxs-lookup"><span data-stu-id="0cf19-289">SP1</span></span>     | <span data-ttu-id="0cf19-290">32 位和 64 位 ：</span><span class="sxs-lookup"><span data-stu-id="0cf19-290">32-bit and 64-bit</span></span>   |

### <span data-ttu-id="0cf19-291">Sequencer 硬件要求</span><span class="sxs-lookup"><span data-stu-id="0cf19-291">Sequencer hardware requirements</span></span>

<span data-ttu-id="0cf19-292">有关硬件要求，请参阅 Windows 或 Windows Server 文档。</span><span class="sxs-lookup"><span data-stu-id="0cf19-292">See the Windows or Windows Server documentation for the hardware requirements.</span></span> <span data-ttu-id="0cf19-293">App-v 不增加任何其他硬件要求。</span><span class="sxs-lookup"><span data-stu-id="0cf19-293">App-V adds no additional hardware requirements.</span></span>

## <a href="" id="bkmk-supp-ver-sccm"></a><span data-ttu-id="0cf19-294">System Center Configuration Manager 支持的版本</span><span class="sxs-lookup"><span data-stu-id="0cf19-294">Supported versions of System Center Configuration Manager</span></span>

<span data-ttu-id="0cf19-295">App-v 客户端支持以下版本的 System Center Configuration Manager：</span><span class="sxs-lookup"><span data-stu-id="0cf19-295">The App-V client supports the following versions of System Center Configuration Manager:</span></span>

-   <span data-ttu-id="0cf19-296">MicrosoftSystemCenter2012 ConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="0cf19-296">MicrosoftSystemCenter2012 ConfigurationManager</span></span>

-   <span data-ttu-id="0cf19-297">System Center 2012 R2 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="0cf19-297">System Center 2012 R2 Configuration Manager</span></span>

-   <span data-ttu-id="0cf19-298">System Center 2012 R2 Configuration Manager SP1</span><span class="sxs-lookup"><span data-stu-id="0cf19-298">System Center 2012 R2 Configuration Manager SP1</span></span>

<span data-ttu-id="0cf19-299">以下应用程序-V 和 System Center Configuration Manager 版本矩阵显示所有正式支持的 app-v 和 Configuration Manager 组合。</span><span class="sxs-lookup"><span data-stu-id="0cf19-299">The following App-V and System Center Configuration Manager version matrix shows all officially supported combinations of App-V and Configuration Manager.</span></span>

> [!NOTE]
> <span data-ttu-id="0cf19-300">App-v 4.5 和4.6 均已退出主流支持。</span><span class="sxs-lookup"><span data-stu-id="0cf19-300">Both App-V 4.5 and 4.6 have exited Mainstream support.</span></span>

<table>
<colgroup>
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="0cf19-301">App-v 版本</span><span class="sxs-lookup"><span data-stu-id="0cf19-301">App-V Version</span></span></th>
<th align="left"><span data-ttu-id="0cf19-302">System Center Configuration Manager 2007</span><span class="sxs-lookup"><span data-stu-id="0cf19-302">System Center Configuration Manager 2007</span></span></th>
<th align="left"><span data-ttu-id="0cf19-303">System Center 2012 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="0cf19-303">System Center 2012 Configuration Manager</span></span></th>
<th align="left"><span data-ttu-id="0cf19-304">System Center 2012 Configuration Manager SP1</span><span class="sxs-lookup"><span data-stu-id="0cf19-304">System Center 2012 Configuration Manager SP1</span></span></th>
<th align="left"><span data-ttu-id="0cf19-305">System Center 2012 R2 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="0cf19-305">System Center 2012 R2 Configuration Manager</span></span></th>
<th align="left"><span data-ttu-id="0cf19-306">System Center 2012 R2 Configuration Manager SP1</span><span class="sxs-lookup"><span data-stu-id="0cf19-306">System Center 2012 R2 Configuration Manager SP1</span></span></th>
<th align="left"><span data-ttu-id="0cf19-307">System Center 2012 Configuration Manager SP2</span><span class="sxs-lookup"><span data-stu-id="0cf19-307">System Center 2012 Configuration Manager SP2</span></span></th>
<th align="left"><span data-ttu-id="0cf19-308">System Center Configuration Manager 版本1511</span><span class="sxs-lookup"><span data-stu-id="0cf19-308">System Center Configuration Manager Version 1511</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0cf19-309">App-v 5.0 SP3</span><span class="sxs-lookup"><span data-stu-id="0cf19-309">App-V 5.0 SP3</span></span></p></td>
<td align="left"><p><span data-ttu-id="0cf19-310">仅限 MSI-包装程序</span><span class="sxs-lookup"><span data-stu-id="0cf19-310">MSI-Wrapper Only</span></span></p></td>
<td align="left"><p><span data-ttu-id="0cf19-311">否</span><span class="sxs-lookup"><span data-stu-id="0cf19-311">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="0cf19-312">2012 SP1 CU4</span><span class="sxs-lookup"><span data-stu-id="0cf19-312">2012 SP1 CU4</span></span></p></td>
<td align="left"><p><span data-ttu-id="0cf19-313">2012 R2 CU1</span><span class="sxs-lookup"><span data-stu-id="0cf19-313">2012 R2 CU1</span></span></p></td>
<td align="left"><p><span data-ttu-id="0cf19-314">是</span><span class="sxs-lookup"><span data-stu-id="0cf19-314">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="0cf19-315">是</span><span class="sxs-lookup"><span data-stu-id="0cf19-315">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="0cf19-316">是</span><span class="sxs-lookup"><span data-stu-id="0cf19-316">Yes</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0cf19-317">App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="0cf19-317">App-V 5.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="0cf19-318">仅限 MSI-包装程序</span><span class="sxs-lookup"><span data-stu-id="0cf19-318">MSI-Wrapper Only</span></span></p></td>
<td align="left"><p><span data-ttu-id="0cf19-319">否</span><span class="sxs-lookup"><span data-stu-id="0cf19-319">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="0cf19-320">2012 SP1 CU4</span><span class="sxs-lookup"><span data-stu-id="0cf19-320">2012 SP1 CU4</span></span></p></td>
<td align="left"><p><span data-ttu-id="0cf19-321">2012 R2 CU1</span><span class="sxs-lookup"><span data-stu-id="0cf19-321">2012 R2 CU1</span></span></p></td>
<td align="left"><p><span data-ttu-id="0cf19-322">是</span><span class="sxs-lookup"><span data-stu-id="0cf19-322">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="0cf19-323">是</span><span class="sxs-lookup"><span data-stu-id="0cf19-323">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="0cf19-324">是</span><span class="sxs-lookup"><span data-stu-id="0cf19-324">Yes</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="0cf19-325">有关 Configuration Manager 如何与 app-v 集成的详细信息，请参阅[规划与 Configuration Manager 的 App-v 集成](https://technet.microsoft.com/library/jj822982.aspx)。</span><span class="sxs-lookup"><span data-stu-id="0cf19-325">For more information about how Configuration Manager integrates with App-V, see [Planning for App-V Integration with Configuration Manager](https://technet.microsoft.com/library/jj822982.aspx).</span></span>

## <span data-ttu-id="0cf19-326">相关主题</span><span class="sxs-lookup"><span data-stu-id="0cf19-326">Related topics</span></span>

[<span data-ttu-id="0cf19-327">计划部署 App-V</span><span class="sxs-lookup"><span data-stu-id="0cf19-327">Planning to Deploy App-V</span></span>](planning-to-deploy-app-v51.md)

[<span data-ttu-id="0cf19-328">App-V 5.1 先决条件</span><span class="sxs-lookup"><span data-stu-id="0cf19-328">App-V 5.1 Prerequisites</span></span>](app-v-51-prerequisites.md)
