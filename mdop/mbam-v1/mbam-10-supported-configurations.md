---
title: MBAM 1.0 支持的配置
description: MBAM 1.0 支持的配置
author: dansimp
ms.assetid: 1f5ac58e-6a3f-47df-8a9b-4b57631ab9ee
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 2c72320379d1c9328a6b40537d37998402b1b38b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803868"
---
# <span data-ttu-id="91819-103">MBAM 1.0 支持的配置</span><span class="sxs-lookup"><span data-stu-id="91819-103">MBAM 1.0 Supported Configurations</span></span>


<span data-ttu-id="91819-104">本主题指定在你的环境中安装和运行 Microsoft BitLocker 管理和监视（MBAM）的必要要求。</span><span class="sxs-lookup"><span data-stu-id="91819-104">This topic specifies the necessary requirements to install and run Microsoft BitLocker Administration and Monitoring (MBAM) in your environment.</span></span>

## <a href="" id="---------mbam-server-system-requirements"></a> <span data-ttu-id="91819-105">MBAM 服务器系统要求</span><span class="sxs-lookup"><span data-stu-id="91819-105">MBAM server system Requirements</span></span>


### <span data-ttu-id="91819-106">服务器操作系统要求</span><span class="sxs-lookup"><span data-stu-id="91819-106">Server operating system requirements</span></span>

<span data-ttu-id="91819-107">下表列出了 Microsoft BitLocker 管理和监视服务器安装支持的操作系统。</span><span class="sxs-lookup"><span data-stu-id="91819-107">The following table lists the operating systems that are supported for the Microsoft BitLocker Administration and Monitoring Server installation.</span></span>

**<span data-ttu-id="91819-108">注意</span><span class="sxs-lookup"><span data-stu-id="91819-108">Note</span></span>**  
<span data-ttu-id="91819-109">Microsoft 提供对当前服务包的支持，在某些情况下，还提供了之前的服务包。</span><span class="sxs-lookup"><span data-stu-id="91819-109">Microsoft provides support for the current service pack and, in some cases, the immediately preceding service pack.</span></span> <span data-ttu-id="91819-110">若要查找产品的支持时间表，请参阅[支持生命周期的服务包](https://go.microsoft.com/fwlink/p/?LinkId=31975)。</span><span class="sxs-lookup"><span data-stu-id="91819-110">To find the support timelines for your product, see the [Lifecycle Supported Service Packs](https://go.microsoft.com/fwlink/p/?LinkId=31975).</span></span> <span data-ttu-id="91819-111">有关 Microsoft 支持生命周期策略的其他信息，请参阅[Microsoft 支持生命周期支持策略常见问题解答](https://go.microsoft.com/fwlink/p/?LinkId=31976)。</span><span class="sxs-lookup"><span data-stu-id="91819-111">For additional information about Microsoft Support Lifecycle Policy, see [Microsoft Support Lifecycle Support Policy FAQ](https://go.microsoft.com/fwlink/p/?LinkId=31976).</span></span>



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="91819-112">操作系统</span><span class="sxs-lookup"><span data-stu-id="91819-112">Operating System</span></span></th>
<th align="left"><span data-ttu-id="91819-113">版本</span><span class="sxs-lookup"><span data-stu-id="91819-113">Edition</span></span></th>
<th align="left"><span data-ttu-id="91819-114">Service Pack</span><span class="sxs-lookup"><span data-stu-id="91819-114">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="91819-115">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="91819-115">System Architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="91819-116">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="91819-116">Windows Server 2008</span></span></p></td>
<td align="left"><p><span data-ttu-id="91819-117">标准版、企业版、数据中心版或 Web 服务器</span><span class="sxs-lookup"><span data-stu-id="91819-117">Standard, Enterprise, Datacenter, or Web Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="91819-118">仅 SP2</span><span class="sxs-lookup"><span data-stu-id="91819-118">SP2 only</span></span></p></td>
<td align="left"><p><span data-ttu-id="91819-119">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="91819-119">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="91819-120">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="91819-120">Windows Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="91819-121">标准版、企业版、数据中心版或 Web 服务器</span><span class="sxs-lookup"><span data-stu-id="91819-121">Standard, Enterprise, Datacenter, or Web Server</span></span></p></td>
<td align="left"></td>
<td align="left"><p><span data-ttu-id="91819-122">64 位</span><span class="sxs-lookup"><span data-stu-id="91819-122">64-bit</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="91819-123">警告</span><span class="sxs-lookup"><span data-stu-id="91819-123">Warning</span></span>**  
<span data-ttu-id="91819-124">不支持在域控制器计算机上安装 MBAM 服务、报表或数据库。</span><span class="sxs-lookup"><span data-stu-id="91819-124">There is no support for installing MBAM services, reports, or databases on a domain controller computer.</span></span>



### <a href="" id="server-random-access-memory--ram--requirements-"></a><span data-ttu-id="91819-125">服务器随机访问内存（RAM）要求</span><span class="sxs-lookup"><span data-stu-id="91819-125">Server random access memory (RAM) requirements</span></span>

<span data-ttu-id="91819-126">没有特定于 MBAM 服务器安装的 RAM 要求。</span><span class="sxs-lookup"><span data-stu-id="91819-126">There are no RAM requirements that are specific to MBAM Server installation.</span></span>

### <a href="" id="sql-server-database-requirements-"></a><span data-ttu-id="91819-127">SQL Server 数据库要求</span><span class="sxs-lookup"><span data-stu-id="91819-127">SQL Server Database requirements</span></span>

<span data-ttu-id="91819-128">下表列出了 MBAM Server 功能安装支持的 SQL Server 版本。</span><span class="sxs-lookup"><span data-stu-id="91819-128">The following table lists the SQL Server versions that are supported for the MBAM Server feature installation.</span></span>

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
<th align="left"><span data-ttu-id="91819-129">MBAM Server 功能</span><span class="sxs-lookup"><span data-stu-id="91819-129">MBAM Server Feature</span></span></th>
<th align="left"><span data-ttu-id="91819-130">SQL Server 版本</span><span class="sxs-lookup"><span data-stu-id="91819-130">SQL Server Version</span></span></th>
<th align="left"><span data-ttu-id="91819-131">版本</span><span class="sxs-lookup"><span data-stu-id="91819-131">Edition</span></span></th>
<th align="left"><span data-ttu-id="91819-132">Service Pack</span><span class="sxs-lookup"><span data-stu-id="91819-132">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="91819-133">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="91819-133">System Architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="91819-134">合规性和审核报告</span><span class="sxs-lookup"><span data-stu-id="91819-134">Compliance and Audit Reports</span></span></p></td>
<td align="left"><p><span data-ttu-id="91819-135">Microsoft SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="91819-135">Microsoft SQL Server 2008</span></span> </p></td>
<td align="left"><p><span data-ttu-id="91819-136">R2、Standard、Enterprise、Datacenter 或开发人员版本</span><span class="sxs-lookup"><span data-stu-id="91819-136">R2, Standard, Enterprise, Datacenter, or Developer Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="91819-137">SP2</span><span class="sxs-lookup"><span data-stu-id="91819-137">SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="91819-138">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="91819-138">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="91819-139">恢复和硬件数据库</span><span class="sxs-lookup"><span data-stu-id="91819-139">Recovery and Hardware Database</span></span></p></td>
<td align="left"><p><span data-ttu-id="91819-140">Microsoft SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="91819-140">Microsoft SQL Server 2008</span></span> </p></td>
<td align="left"><p><span data-ttu-id="91819-141">R2、企业版、数据中心版或开发人员版</span><span class="sxs-lookup"><span data-stu-id="91819-141">R2, Enterprise, Datacenter, or Developer Edition</span></span></p>
<div class="alert">
<strong><span data-ttu-id="91819-142">重要提示</span><span class="sxs-lookup"><span data-stu-id="91819-142">Important</span></span></strong><br/><p><span data-ttu-id="91819-143">SQL Server 标准版不支持 MBAM 恢复和硬件数据库服务器功能安装。</span><span class="sxs-lookup"><span data-stu-id="91819-143">SQL Server Standard Editions are not supported for MBAM Recovery and Hardware Database Server feature installation.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="91819-144">SP2</span><span class="sxs-lookup"><span data-stu-id="91819-144">SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="91819-145">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="91819-145">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="91819-146">合规性和审核数据库</span><span class="sxs-lookup"><span data-stu-id="91819-146">Compliance and Audit Database</span></span></p></td>
<td align="left"><p><span data-ttu-id="91819-147">Microsoft SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="91819-147">Microsoft SQL Server 2008</span></span> </p></td>
<td align="left"><p><span data-ttu-id="91819-148">R2、Standard、Enterprise、Datacenter 或开发人员版本</span><span class="sxs-lookup"><span data-stu-id="91819-148">R2, Standard, Enterprise, Datacenter, or Developer Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="91819-149">SP2</span><span class="sxs-lookup"><span data-stu-id="91819-149">SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="91819-150">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="91819-150">32-bit or 64-bit</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="---------mbam-client-system-requirements"></a> <span data-ttu-id="91819-151">MBAM 客户端系统要求</span><span class="sxs-lookup"><span data-stu-id="91819-151">MBAM Client system requirements</span></span>


### <span data-ttu-id="91819-152">客户端操作系统要求</span><span class="sxs-lookup"><span data-stu-id="91819-152">Client operating system requirements</span></span>

<span data-ttu-id="91819-153">下表列出了 MBAM 客户端安装支持的操作系统。</span><span class="sxs-lookup"><span data-stu-id="91819-153">The following table lists the operating systems that are supported for MBAM Client installation.</span></span>

**<span data-ttu-id="91819-154">注意</span><span class="sxs-lookup"><span data-stu-id="91819-154">Note</span></span>**  
<span data-ttu-id="91819-155">Microsoft 提供对当前服务包的支持，在某些情况下，还提供了之前的服务包。</span><span class="sxs-lookup"><span data-stu-id="91819-155">Microsoft provides support for the current service pack and, in some cases, the immediately preceding service pack.</span></span> <span data-ttu-id="91819-156">若要查找产品的支持时间表，请参阅[支持生命周期的服务包](https://go.microsoft.com/fwlink/p/?LinkId=31975)。</span><span class="sxs-lookup"><span data-stu-id="91819-156">To find the support timelines for your product, see the [Lifecycle Supported Service Packs](https://go.microsoft.com/fwlink/p/?LinkId=31975).</span></span> <span data-ttu-id="91819-157">有关 Microsoft 支持生命周期策略的其他信息，请参阅[Microsoft 支持生命周期支持策略常见问题解答](https://go.microsoft.com/fwlink/p/?LinkId=31976)。</span><span class="sxs-lookup"><span data-stu-id="91819-157">For additional information about Microsoft Support Lifecycle Policy, see [Microsoft Support Lifecycle Support Policy FAQ](https://go.microsoft.com/fwlink/p/?LinkId=31976).</span></span>



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="91819-158">操作系统</span><span class="sxs-lookup"><span data-stu-id="91819-158">Operating System</span></span></th>
<th align="left"><span data-ttu-id="91819-159">版本</span><span class="sxs-lookup"><span data-stu-id="91819-159">Edition</span></span></th>
<th align="left"><span data-ttu-id="91819-160">Service Pack</span><span class="sxs-lookup"><span data-stu-id="91819-160">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="91819-161">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="91819-161">System Architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="91819-162">Windows 7</span><span class="sxs-lookup"><span data-stu-id="91819-162">Windows 7</span></span></p></td>
<td align="left"><p><span data-ttu-id="91819-163">企业版</span><span class="sxs-lookup"><span data-stu-id="91819-163">Enterprise Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="91819-164">无、SP1</span><span class="sxs-lookup"><span data-stu-id="91819-164">None, SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="91819-165">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="91819-165">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="91819-166">Windows 7</span><span class="sxs-lookup"><span data-stu-id="91819-166">Windows 7</span></span></p></td>
<td align="left"><p><span data-ttu-id="91819-167">旗舰版</span><span class="sxs-lookup"><span data-stu-id="91819-167">Ultimate Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="91819-168">无、SP1</span><span class="sxs-lookup"><span data-stu-id="91819-168">None, SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="91819-169">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="91819-169">32-bit or 64-bit</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="client-ram-requirements-"></a><span data-ttu-id="91819-170">客户端 RAM 要求</span><span class="sxs-lookup"><span data-stu-id="91819-170">Client RAM requirements</span></span>

<span data-ttu-id="91819-171">没有特定于 MBAM 客户端安装的 RAM 要求。</span><span class="sxs-lookup"><span data-stu-id="91819-171">There are no RAM requirements that are specific to the MBAM Client installation.</span></span>

## <span data-ttu-id="91819-172">相关主题</span><span class="sxs-lookup"><span data-stu-id="91819-172">Related topics</span></span>


[<span data-ttu-id="91819-173">计划部署 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="91819-173">Planning to Deploy MBAM 1.0</span></span>](planning-to-deploy-mbam-10.md)

[<span data-ttu-id="91819-174">MBAM 1.0 部署先决条件</span><span class="sxs-lookup"><span data-stu-id="91819-174">MBAM 1.0 Deployment Prerequisites</span></span>](mbam-10-deployment-prerequisites.md)









