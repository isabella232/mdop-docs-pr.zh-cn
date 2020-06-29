---
title: MBAM 2.0 支持的配置
description: MBAM 2.0 支持的配置
author: dansimp
ms.assetid: dca63391-39fe-4273-a570-76d0a2f8a0fd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 8f314adcf818c1bdb17b0b239a7469f97fa849e4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803462"
---
# <span data-ttu-id="9daf5-103">MBAM 2.0 支持的配置</span><span class="sxs-lookup"><span data-stu-id="9daf5-103">MBAM 2.0 Supported Configurations</span></span>


<span data-ttu-id="9daf5-104">本主题通过使用独立拓扑指定在你的环境中安装和运行 Microsoft BitLocker 管理和监视（MBAM）2.0 的要求。</span><span class="sxs-lookup"><span data-stu-id="9daf5-104">This topic specifies the requirements to install and run Microsoft BitLocker Administration and Monitoring (MBAM) 2.0 in your environment by using the Stand-alone topology.</span></span> <span data-ttu-id="9daf5-105">有关适用于更高版本的受支持的配置，请参阅适用版本的文档。</span><span class="sxs-lookup"><span data-stu-id="9daf5-105">For supported configurations that apply to later releases, see the documentation for the applicable release.</span></span>

<span data-ttu-id="9daf5-106">如果你计划通过使用 Configuration Manager 拓扑安装 MBAM 2.0 并希望查看系统要求的列表，请参阅[计划使用 Configuration Manager 部署 MBAM](planning-to-deploy-mbam-with-configuration-manager-2.md)。</span><span class="sxs-lookup"><span data-stu-id="9daf5-106">If you plan to install MBAM 2.0 by using the Configuration Manager topology and want to review a list of the system requirements, see [Planning to Deploy MBAM with Configuration Manager](planning-to-deploy-mbam-with-configuration-manager-2.md).</span></span>

<span data-ttu-id="9daf5-107">在生产环境中运行 MBAM 的推荐配置是两台服务器，具体取决于你的可伸缩性要求。</span><span class="sxs-lookup"><span data-stu-id="9daf5-107">The recommended configuration for running MBAM in a production environment is with two servers, depending on your scalability requirements.</span></span> <span data-ttu-id="9daf5-108">此配置最多支持 200000 MBAM 客户端。</span><span class="sxs-lookup"><span data-stu-id="9daf5-108">This configuration supports up to 200,000 MBAM clients.</span></span> <span data-ttu-id="9daf5-109">有关独立 MBAM 服务器基础结构的图像和说明，请参阅[MBAM 2.0 的高级别体系结构](high-level-architecture-for-mbam-20-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="9daf5-109">For an image and descriptions of the Stand-alone MBAM server infrastructure, see [High-Level Architecture for MBAM 2.0](high-level-architecture-for-mbam-20-mbam-2.md).</span></span>

<span data-ttu-id="9daf5-110">**注意** Microsoft 提供对当前服务包的支持，在某些情况下，还提供了之前的服务包。</span><span class="sxs-lookup"><span data-stu-id="9daf5-110">**Note** Microsoft provides support for the current service pack and, in some cases, the immediately preceding service pack.</span></span> <span data-ttu-id="9daf5-111">若要查找产品的支持时间表，请参阅[支持生命周期的服务包](https://go.microsoft.com/fwlink/p/?LinkId=31975)。</span><span class="sxs-lookup"><span data-stu-id="9daf5-111">To find the support timelines for your product, see the [Lifecycle Supported Service Packs](https://go.microsoft.com/fwlink/p/?LinkId=31975).</span></span> <span data-ttu-id="9daf5-112">有关 Microsoft 支持生命周期策略的其他信息，请参阅[Microsoft 支持生命周期支持策略常见问题解答](https://go.microsoft.com/fwlink/p/?LinkId=31976)。</span><span class="sxs-lookup"><span data-stu-id="9daf5-112">For additional information about Microsoft Support Lifecycle Policy, see [Microsoft Support Lifecycle Support Policy FAQ](https://go.microsoft.com/fwlink/p/?LinkId=31976).</span></span>

 

## <a href="" id="---------mbam-server-system-requirements"></a> <span data-ttu-id="9daf5-113">MBAM 服务器系统要求</span><span class="sxs-lookup"><span data-stu-id="9daf5-113">MBAM Server System Requirements</span></span>


### <span data-ttu-id="9daf5-114">服务器操作系统要求</span><span class="sxs-lookup"><span data-stu-id="9daf5-114">Server Operating System Requirements</span></span>

<span data-ttu-id="9daf5-115">下表列出了 Microsoft BitLocker 管理和监视服务器安装支持的操作系统。</span><span class="sxs-lookup"><span data-stu-id="9daf5-115">The following table lists the operating systems that are supported for the Microsoft BitLocker Administration and Monitoring Server installation.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9daf5-116">操作系统</span><span class="sxs-lookup"><span data-stu-id="9daf5-116">Operating system</span></span></th>
<th align="left"><span data-ttu-id="9daf5-117">版本</span><span class="sxs-lookup"><span data-stu-id="9daf5-117">Edition</span></span></th>
<th align="left"><span data-ttu-id="9daf5-118">Service pack</span><span class="sxs-lookup"><span data-stu-id="9daf5-118">Service pack</span></span></th>
<th align="left"><span data-ttu-id="9daf5-119">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="9daf5-119">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9daf5-120">WindowsServer2008 R2</span><span class="sxs-lookup"><span data-stu-id="9daf5-120">WindowsServer2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="9daf5-121">标准版、企业版或数据中心版</span><span class="sxs-lookup"><span data-stu-id="9daf5-121">Standard, Enterprise, or Datacenter Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="9daf5-122">SP1</span><span class="sxs-lookup"><span data-stu-id="9daf5-122">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="9daf5-123">64 位</span><span class="sxs-lookup"><span data-stu-id="9daf5-123">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9daf5-124">WindowsServer2012</span><span class="sxs-lookup"><span data-stu-id="9daf5-124">WindowsServer2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="9daf5-125">标准版或数据中心版</span><span class="sxs-lookup"><span data-stu-id="9daf5-125">Standard or Datacenter Edition</span></span></p></td>
<td align="left"></td>
<td align="left"><p><span data-ttu-id="9daf5-126">64 位</span><span class="sxs-lookup"><span data-stu-id="9daf5-126">64-bit</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="9daf5-127">**注意** 不支持在域控制器计算机上安装 MBAM 服务、报表或数据库。</span><span class="sxs-lookup"><span data-stu-id="9daf5-127">**Note** There is no support for installing MBAM services, reports, or databases on a domain controller computer.</span></span>

 

### <a href="" id="server-processor--ram--and-disk-space-requirements-"></a><span data-ttu-id="9daf5-128">服务器处理器、RAM 和磁盘空间要求</span><span class="sxs-lookup"><span data-stu-id="9daf5-128">Server Processor, RAM, and Disk Space Requirements</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9daf5-129">硬件组件</span><span class="sxs-lookup"><span data-stu-id="9daf5-129">Hardware component</span></span></th>
<th align="left"><span data-ttu-id="9daf5-130">最低要求</span><span class="sxs-lookup"><span data-stu-id="9daf5-130">Minimum requirement</span></span></th>
<th align="left"><span data-ttu-id="9daf5-131">建议的要求</span><span class="sxs-lookup"><span data-stu-id="9daf5-131">Recommended requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9daf5-132">处理者</span><span class="sxs-lookup"><span data-stu-id="9daf5-132">Processor</span></span></p></td>
<td align="left"><p><span data-ttu-id="9daf5-133">2.33 GHz</span><span class="sxs-lookup"><span data-stu-id="9daf5-133">2.33 GHz</span></span></p></td>
<td align="left"><p><span data-ttu-id="9daf5-134">2.33 GHz 或更高版本</span><span class="sxs-lookup"><span data-stu-id="9daf5-134">2.33 GHz or greater</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9daf5-135">RAM</span><span class="sxs-lookup"><span data-stu-id="9daf5-135">RAM</span></span></p></td>
<td align="left"><p><span data-ttu-id="9daf5-136">8 GB</span><span class="sxs-lookup"><span data-stu-id="9daf5-136">8 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="9daf5-137">12 GB</span><span class="sxs-lookup"><span data-stu-id="9daf5-137">12 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9daf5-138">可用磁盘空间</span><span class="sxs-lookup"><span data-stu-id="9daf5-138">Free disk space</span></span></p></td>
<td align="left"><p><span data-ttu-id="9daf5-139">1 GB</span><span class="sxs-lookup"><span data-stu-id="9daf5-139">1 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="9daf5-140">2 GB</span><span class="sxs-lookup"><span data-stu-id="9daf5-140">2 GB</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="sql-server-database-requirements-"></a><span data-ttu-id="9daf5-141">SQLServer 数据库要求</span><span class="sxs-lookup"><span data-stu-id="9daf5-141">SQLServer Database Requirements</span></span>

<span data-ttu-id="9daf5-142">下表列出了管理和监视服务器功能安装支持的 SQLServer 版本，其中包括恢复数据库、合规性和审核数据库以及合规性和审核报告。</span><span class="sxs-lookup"><span data-stu-id="9daf5-142">The following table lists the SQLServer versions that are supported for the Administration and Monitoring Server feature installation, which includes the Recovery Database, Compliance and Audit Database, and Compliance and Audit Reports.</span></span> <span data-ttu-id="9daf5-143">数据库还需要安装 SQL Server 管理工具。</span><span class="sxs-lookup"><span data-stu-id="9daf5-143">The databases additionally require the installation of SQL Server Management Tools.</span></span>

<span data-ttu-id="9daf5-144">**注意** MBAM 本身不支持 SQL 群集、镜像或可用性组。</span><span class="sxs-lookup"><span data-stu-id="9daf5-144">**Note** MBAM does not natively support SQL clustering, mirroring, or Availability Groups.</span></span> <span data-ttu-id="9daf5-145">若要安装数据库，必须在独立 SQL Server 上运行 MBAM Server 安装。</span><span class="sxs-lookup"><span data-stu-id="9daf5-145">To install the databases, you must run the MBAM Server installation on a stand-alone SQL server.</span></span>

 

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9daf5-146">SQL Server 版本</span><span class="sxs-lookup"><span data-stu-id="9daf5-146">SQL Server version</span></span></th>
<th align="left"><span data-ttu-id="9daf5-147">版本</span><span class="sxs-lookup"><span data-stu-id="9daf5-147">Edition</span></span></th>
<th align="left"><span data-ttu-id="9daf5-148">Service pack</span><span class="sxs-lookup"><span data-stu-id="9daf5-148">Service pack</span></span></th>
<th align="left"><span data-ttu-id="9daf5-149">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="9daf5-149">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9daf5-150">MicrosoftSQLServer2008 R2</span><span class="sxs-lookup"><span data-stu-id="9daf5-150">MicrosoftSQLServer2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="9daf5-151">标准版、企业版或数据中心版</span><span class="sxs-lookup"><span data-stu-id="9daf5-151">Standard, Enterprise, or Datacenter Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="9daf5-152">SP1</span><span class="sxs-lookup"><span data-stu-id="9daf5-152">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="9daf5-153">64 位</span><span class="sxs-lookup"><span data-stu-id="9daf5-153">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9daf5-154">MicrosoftSQLServer2012</span><span class="sxs-lookup"><span data-stu-id="9daf5-154">MicrosoftSQLServer2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="9daf5-155">标准版、企业版或数据中心版</span><span class="sxs-lookup"><span data-stu-id="9daf5-155">Standard, Enterprise, or Datacenter Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="9daf5-156">SP1</span><span class="sxs-lookup"><span data-stu-id="9daf5-156">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="9daf5-157">64 位</span><span class="sxs-lookup"><span data-stu-id="9daf5-157">64-bit</span></span></p></td>
</tr>
</tbody>
</table>

 

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9daf5-158">硬件组件</span><span class="sxs-lookup"><span data-stu-id="9daf5-158">Hardware component</span></span></th>
<th align="left"><span data-ttu-id="9daf5-159">最低要求</span><span class="sxs-lookup"><span data-stu-id="9daf5-159">Minimum requirement</span></span></th>
<th align="left"><span data-ttu-id="9daf5-160">建议的要求</span><span class="sxs-lookup"><span data-stu-id="9daf5-160">Recommended requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9daf5-161">处理者</span><span class="sxs-lookup"><span data-stu-id="9daf5-161">Processor</span></span></p></td>
<td align="left"><p><span data-ttu-id="9daf5-162">2.33 GHz</span><span class="sxs-lookup"><span data-stu-id="9daf5-162">2.33 GHz</span></span></p></td>
<td align="left"><p><span data-ttu-id="9daf5-163">2.33 GHz 或更高版本</span><span class="sxs-lookup"><span data-stu-id="9daf5-163">2.33 GHz or greater</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9daf5-164">RAM</span><span class="sxs-lookup"><span data-stu-id="9daf5-164">RAM</span></span></p></td>
<td align="left"><p><span data-ttu-id="9daf5-165">8 GB</span><span class="sxs-lookup"><span data-stu-id="9daf5-165">8 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="9daf5-166">12 GB</span><span class="sxs-lookup"><span data-stu-id="9daf5-166">12 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9daf5-167">可用磁盘空间</span><span class="sxs-lookup"><span data-stu-id="9daf5-167">Free disk space</span></span></p></td>
<td align="left"><p><span data-ttu-id="9daf5-168">5 GB</span><span class="sxs-lookup"><span data-stu-id="9daf5-168">5 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="9daf5-169">5 GB 或以上</span><span class="sxs-lookup"><span data-stu-id="9daf5-169">5 GB or greater</span></span></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="---------mbam-client-system-requirements"></a> <span data-ttu-id="9daf5-170">MBAM 客户端系统要求</span><span class="sxs-lookup"><span data-stu-id="9daf5-170">MBAM Client System Requirements</span></span>


### <span data-ttu-id="9daf5-171">客户端操作系统要求</span><span class="sxs-lookup"><span data-stu-id="9daf5-171">Client Operating System Requirements</span></span>

<span data-ttu-id="9daf5-172">下表列出了 Microsoft BitLocker 管理和监视客户端安装支持的操作系统。</span><span class="sxs-lookup"><span data-stu-id="9daf5-172">The following table lists the operating systems that are supported for Microsoft BitLocker Administration and Monitoring Client installation.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9daf5-173">操作系统</span><span class="sxs-lookup"><span data-stu-id="9daf5-173">Operating system</span></span></th>
<th align="left"><span data-ttu-id="9daf5-174">版本</span><span class="sxs-lookup"><span data-stu-id="9daf5-174">Edition</span></span></th>
<th align="left"><span data-ttu-id="9daf5-175">Service pack</span><span class="sxs-lookup"><span data-stu-id="9daf5-175">Service pack</span></span></th>
<th align="left"><span data-ttu-id="9daf5-176">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="9daf5-176">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9daf5-177">Windows7</span><span class="sxs-lookup"><span data-stu-id="9daf5-177">Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="9daf5-178">企业版或旗舰版</span><span class="sxs-lookup"><span data-stu-id="9daf5-178">Enterprise or Ultimate Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="9daf5-179">SP1</span><span class="sxs-lookup"><span data-stu-id="9daf5-179">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="9daf5-180">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="9daf5-180">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9daf5-181">Windows 8</span><span class="sxs-lookup"><span data-stu-id="9daf5-181">Windows 8</span></span></p></td>
<td align="left"><p><span data-ttu-id="9daf5-182">企业版</span><span class="sxs-lookup"><span data-stu-id="9daf5-182">Enterprise Edition</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="9daf5-183">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="9daf5-183">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9daf5-184">Windows To Go</span><span class="sxs-lookup"><span data-stu-id="9daf5-184">Windows To Go</span></span></p></td>
<td align="left"><p><span data-ttu-id="9daf5-185">Windows 8 企业版</span><span class="sxs-lookup"><span data-stu-id="9daf5-185">Windows 8 Enterprise Edition</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="9daf5-186">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="9daf5-186">32-bit or 64-bit</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="client-ram-requirements-"></a><span data-ttu-id="9daf5-187">客户端 RAM 要求</span><span class="sxs-lookup"><span data-stu-id="9daf5-187">Client RAM Requirements</span></span>

<span data-ttu-id="9daf5-188">不存在特定于 Microsoft BitLocker 管理和监视客户端安装的 RAM 要求。</span><span class="sxs-lookup"><span data-stu-id="9daf5-188">There are no RAM requirements that are specific to the Microsoft BitLocker Administration and Monitoring Client installation.</span></span>

## <a href="" id="---------mbam-group-policy-system-requirements"></a> <span data-ttu-id="9daf5-189">MBAM 组策略系统要求</span><span class="sxs-lookup"><span data-stu-id="9daf5-189">MBAM Group Policy System Requirements</span></span>


<span data-ttu-id="9daf5-190">下表列出了 Microsoft BitLocker 管理和监视组策略模板安装所支持的操作系统。</span><span class="sxs-lookup"><span data-stu-id="9daf5-190">The following table lists the operating systems that are supported for Microsoft BitLocker Administration and Monitoring Group Policy template installation.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9daf5-191">操作系统</span><span class="sxs-lookup"><span data-stu-id="9daf5-191">Operating system</span></span></th>
<th align="left"><span data-ttu-id="9daf5-192">版本</span><span class="sxs-lookup"><span data-stu-id="9daf5-192">Edition</span></span></th>
<th align="left"><span data-ttu-id="9daf5-193">Service pack</span><span class="sxs-lookup"><span data-stu-id="9daf5-193">Service pack</span></span></th>
<th align="left"><span data-ttu-id="9daf5-194">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="9daf5-194">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9daf5-195">Windows7</span><span class="sxs-lookup"><span data-stu-id="9daf5-195">Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="9daf5-196">企业版或旗舰版</span><span class="sxs-lookup"><span data-stu-id="9daf5-196">Enterprise, or Ultimate Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="9daf5-197">SP1</span><span class="sxs-lookup"><span data-stu-id="9daf5-197">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="9daf5-198">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="9daf5-198">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9daf5-199">Windows 8</span><span class="sxs-lookup"><span data-stu-id="9daf5-199">Windows 8</span></span></p></td>
<td align="left"><p><span data-ttu-id="9daf5-200">企业版</span><span class="sxs-lookup"><span data-stu-id="9daf5-200">Enterprise Edition</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="9daf5-201">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="9daf5-201">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9daf5-202">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="9daf5-202">Windows Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="9daf5-203">标准版、企业版或数据中心版</span><span class="sxs-lookup"><span data-stu-id="9daf5-203">Standard, Enterprise, or Datacenter Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="9daf5-204">SP1</span><span class="sxs-lookup"><span data-stu-id="9daf5-204">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="9daf5-205">64 位</span><span class="sxs-lookup"><span data-stu-id="9daf5-205">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9daf5-206">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="9daf5-206">Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="9daf5-207">标准版或数据中心版</span><span class="sxs-lookup"><span data-stu-id="9daf5-207">Standard or Datacenter Edition</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="9daf5-208">64 位</span><span class="sxs-lookup"><span data-stu-id="9daf5-208">64-bit</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="9daf5-209">相关主题</span><span class="sxs-lookup"><span data-stu-id="9daf5-209">Related topics</span></span>


[<span data-ttu-id="9daf5-210">计划部署 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="9daf5-210">Planning to Deploy MBAM 2.0</span></span>](planning-to-deploy-mbam-20-mbam-2.md)

[<span data-ttu-id="9daf5-211">MBAM 2.0 部署先决条件</span><span class="sxs-lookup"><span data-stu-id="9daf5-211">MBAM 2.0 Deployment Prerequisites</span></span>](mbam-20-deployment-prerequisites-mbam-2.md)

 

 





