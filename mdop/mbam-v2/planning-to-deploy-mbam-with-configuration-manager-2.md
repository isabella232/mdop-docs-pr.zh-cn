---
title: 计划使用 Configuration Manager 部署 MBAM
description: 计划使用 Configuration Manager 部署 MBAM
author: dansimp
ms.assetid: fb768306-48c2-40b4-ac4e-c279db987391
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e8588ce03c86a8a5138d591327e5f95503dce5ad
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803806"
---
# <span data-ttu-id="3f130-103">计划使用 Configuration Manager 部署 MBAM</span><span class="sxs-lookup"><span data-stu-id="3f130-103">Planning to Deploy MBAM with Configuration Manager</span></span>


<span data-ttu-id="3f130-104">若要使用 Configuration Manager 拓扑部署 MBAM，建议使用支持200000客户端的三服务器体系结构。</span><span class="sxs-lookup"><span data-stu-id="3f130-104">To deploy MBAM with the Configuration Manager topology, a three-server architecture, which supports 200,000 clients, is recommended.</span></span> <span data-ttu-id="3f130-105">使用单独的服务器运行配置管理器，并在两台服务器上安装基本的管理和监视功能，如入门中的体系结构图所示[-将 MBAM 与 Configuration Manager 配合使用](getting-started---using-mbam-with-configuration-manager.md)。</span><span class="sxs-lookup"><span data-stu-id="3f130-105">Use a separate server to run Configuration Manager, and install the basic Administration and Monitoring features on two servers, as shown in the architecture image in [Getting Started - Using MBAM with Configuration Manager](getting-started---using-mbam-with-configuration-manager.md).</span></span>

**<span data-ttu-id="3f130-106">重要提示</span><span class="sxs-lookup"><span data-stu-id="3f130-106">Important</span></span>**  
<span data-ttu-id="3f130-107">将 MBAM 的集成拓扑安装到 Configuration Manager 2007 时，不支持 Windows To Go。</span><span class="sxs-lookup"><span data-stu-id="3f130-107">Windows To Go is not supported when you install the integrated topology of MBAM with Configuration Manager 2007.</span></span>



## <span data-ttu-id="3f130-108">通过 Configuration Manager 安装 MBAM 的部署先决条件</span><span class="sxs-lookup"><span data-stu-id="3f130-108">Deployment Prerequisites for Installing MBAM with Configuration Manager</span></span>


<span data-ttu-id="3f130-109">在使用 Configuration Manager 安装 MBAM 之前，请确保满足以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="3f130-109">Ensure that you have met the following prerequisites before you install MBAM with Configuration Manager:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3f130-110">必备</span><span class="sxs-lookup"><span data-stu-id="3f130-110">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="3f130-111">其他信息</span><span class="sxs-lookup"><span data-stu-id="3f130-111">Additional Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3f130-112">确保 Configuration Manager 服务器是 Configuration Manager 系统中的主站点。</span><span class="sxs-lookup"><span data-stu-id="3f130-112">Ensure that the Configuration Manager Server is a primary site in the Configuration Manager system.</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f130-113">不适用</span><span class="sxs-lookup"><span data-stu-id="3f130-113">N/A</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3f130-114">在 Configuration Manager 服务器上启用硬件清单客户端代理。</span><span class="sxs-lookup"><span data-stu-id="3f130-114">Enable the Hardware Inventory Client Agent on the Configuration Manager Server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f130-115">有关 Configuration Manager 2007 的详细说明，请参阅 <a href="https://go.microsoft.com/fwlink/?LinkId=301656" data-raw-source="[How to Configure Hardware Inventory for a Site](https://go.microsoft.com/fwlink/?LinkId=301656)"> 如何为网站配置硬件清单 </a> 。</span><span class="sxs-lookup"><span data-stu-id="3f130-115">For Configuration Manager 2007, see <a href="https://go.microsoft.com/fwlink/?LinkId=301656" data-raw-source="[How to Configure Hardware Inventory for a Site](https://go.microsoft.com/fwlink/?LinkId=301656)">How to Configure Hardware Inventory for a Site</a>.</span></span></p>
<p><span data-ttu-id="3f130-116">对于 System Center 2012 配置管理器，请参阅 <a href="https://go.microsoft.com/fwlink/?LinkId=301685" data-raw-source="[How to Configure Hardware Inventory in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301685)"> 如何在 Configuration manager 中配置硬件清单 </a> 。</span><span class="sxs-lookup"><span data-stu-id="3f130-116">For System Center 2012 Configuration Manager, see <a href="https://go.microsoft.com/fwlink/?LinkId=301685" data-raw-source="[How to Configure Hardware Inventory in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301685)">How to Configure Hardware Inventory in Configuration Manager</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3f130-117">根据你使用的 Configuration Manager 版本启用所需的配置管理（DCM）代理或合规性设置。</span><span class="sxs-lookup"><span data-stu-id="3f130-117">Enable the Desired Configuration Management (DCM) agent or the compliance settings, depending on the version of Configuration Manager that you are using.</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f130-118">对于 Configuration Manager 2007，请启用 "查看 <a href="https://go.microsoft.com/fwlink/?LinkId=301686" data-raw-source="[Desired Configuration Management Client Agent Properties](https://go.microsoft.com/fwlink/?LinkId=301686)"> 所需的配置管理客户端代理" 属性 </a> 。</span><span class="sxs-lookup"><span data-stu-id="3f130-118">For Configuration Manager 2007, enable the see <a href="https://go.microsoft.com/fwlink/?LinkId=301686" data-raw-source="[Desired Configuration Management Client Agent Properties](https://go.microsoft.com/fwlink/?LinkId=301686)">Desired Configuration Management Client Agent Properties</a>.</span></span></p>
<p><span data-ttu-id="3f130-119">对于 System Center 2012 配置管理器，请参阅配置 <a href="https://go.microsoft.com/fwlink/?LinkId=301687" data-raw-source="[Configuring Compliance Settings in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301687)"> 管理器中的配置合规性设置 </a> 。</span><span class="sxs-lookup"><span data-stu-id="3f130-119">For System Center 2012 Configuration Manager, see <a href="https://go.microsoft.com/fwlink/?LinkId=301687" data-raw-source="[Configuring Compliance Settings in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301687)">Configuring Compliance Settings in Configuration Manager</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3f130-120">在配置管理器中定义 reporting services 点。</span><span class="sxs-lookup"><span data-stu-id="3f130-120">Define a reporting services point in Configuration Manager.</span></span> <span data-ttu-id="3f130-121">对于 SQL Reporting Services 是必需的。</span><span class="sxs-lookup"><span data-stu-id="3f130-121">Required for SQL Reporting Services.</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f130-122">有关 Configuration Manager 2007 的详细说明，请参阅 <a href="https://go.microsoft.com/fwlink/?LinkId=301688" data-raw-source="[How to Create a Reporting Services Point for SQL Reporting Services](https://go.microsoft.com/fwlink/?LinkId=301688)"> 如何为 SQL Reporting Services 创建 Reporting Services 点 </a> 。</span><span class="sxs-lookup"><span data-stu-id="3f130-122">For Configuration Manager 2007, see <a href="https://go.microsoft.com/fwlink/?LinkId=301688" data-raw-source="[How to Create a Reporting Services Point for SQL Reporting Services](https://go.microsoft.com/fwlink/?LinkId=301688)">How to Create a Reporting Services Point for SQL Reporting Services</a>.</span></span></p>
<p><span data-ttu-id="3f130-123">对于 System Center 2012 配置管理器，请参阅 <a href="https://go.microsoft.com/fwlink/?LinkId=301689" data-raw-source="[Prerequisites for Reporting in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301689)"> 配置管理器中的报告先决条件 </a> 。</span><span class="sxs-lookup"><span data-stu-id="3f130-123">For System Center 2012 Configuration Manager, see <a href="https://go.microsoft.com/fwlink/?LinkId=301689" data-raw-source="[Prerequisites for Reporting in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301689)">Prerequisites for Reporting in Configuration Manager</a>.</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="---------configuration-manager-supported-versions"></a> <span data-ttu-id="3f130-124">Configuration Manager 支持的版本</span><span class="sxs-lookup"><span data-stu-id="3f130-124">Configuration Manager Supported Versions</span></span>


<span data-ttu-id="3f130-125">MBAM 支持以下版本的 Configuration Manager：</span><span class="sxs-lookup"><span data-stu-id="3f130-125">MBAM supports the following versions of Configuration Manager:</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3f130-126">支持的版本</span><span class="sxs-lookup"><span data-stu-id="3f130-126">Supported version</span></span></th>
<th align="left"><span data-ttu-id="3f130-127">Service pack</span><span class="sxs-lookup"><span data-stu-id="3f130-127">Service pack</span></span></th>
<th align="left"><span data-ttu-id="3f130-128">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="3f130-128">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3f130-129">Microsoft System Center Configuration Manager 2007 R2</span><span class="sxs-lookup"><span data-stu-id="3f130-129">Microsoft System Center Configuration Manager 2007 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f130-130">SP1 或更高版本</span><span class="sxs-lookup"><span data-stu-id="3f130-130">SP1 or later</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f130-131">64 位</span><span class="sxs-lookup"><span data-stu-id="3f130-131">64-bit</span></span></p>
<div class="alert">
<strong><span data-ttu-id="3f130-132">注意</span><span class="sxs-lookup"><span data-stu-id="3f130-132">Note</span></span></strong><br/><p><span data-ttu-id="3f130-133">虽然 Configuration Manager 2007 是32位，但必须在64位操作系统上安装它和 SQL Server 才能匹配64位 MBAM 软件。</span><span class="sxs-lookup"><span data-stu-id="3f130-133">Although Configuration Manager 2007 is 32 bit, you must install it and SQL Server on a 64-bit operating system in order to match the 64-bit MBAM software.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3f130-134">Microsoft System Center 2012 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="3f130-134">Microsoft System Center 2012 Configuration Manager</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f130-135">SP1</span><span class="sxs-lookup"><span data-stu-id="3f130-135">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f130-136">64 位</span><span class="sxs-lookup"><span data-stu-id="3f130-136">64-bit</span></span></p></td>
</tr>
</tbody>
</table>



<span data-ttu-id="3f130-137">有关 Configuration Manager 服务器支持的配置的列表，请参阅适用于你正在使用的 Configuration Manager 版本的相应网页。</span><span class="sxs-lookup"><span data-stu-id="3f130-137">For a list of supported configurations for the Configuration Manager Server, see the appropriate webpage for the version of Configuration Manager that you are using.</span></span> <span data-ttu-id="3f130-138">MBAM 配置管理器服务器没有其他系统要求。</span><span class="sxs-lookup"><span data-stu-id="3f130-138">MBAM has no additional system requirements for the Configuration Manager Server.</span></span>

## <a href="" id="---------mbam-and-sql-server-system-requirements"></a> <span data-ttu-id="3f130-139">MBAM 和 SQL Server 系统要求</span><span class="sxs-lookup"><span data-stu-id="3f130-139">MBAM and SQL Server System Requirements</span></span>


<span data-ttu-id="3f130-140">MBAM 服务器和配置管理器拓扑的 SQL Server 支持的配置和系统要求与独立拓扑的支持配置和系统要求相同。</span><span class="sxs-lookup"><span data-stu-id="3f130-140">The supported configurations and system requirements for the MBAM servers and SQL Server for the Configuration Manager topology are the same as those for the Stand-alone topology.</span></span> <span data-ttu-id="3f130-141">有关独立系统要求，请参阅[MBAM 2.0 支持的配置](mbam-20-supported-configurations-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="3f130-141">For the Stand-alone system requirements, see [MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md).</span></span> <span data-ttu-id="3f130-142">有关 Configuration Manager 拓扑的 MBAM 服务器和 SQL Server 处理器、RAM 和磁盘空间要求，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="3f130-142">For the MBAM Server and SQL Server processor, RAM, and disk space requirements for the Configuration Manager topology, see the following sections.</span></span>

## <span data-ttu-id="3f130-143">MBAM 服务器处理器、RAM 和磁盘空间要求 MBAM</span><span class="sxs-lookup"><span data-stu-id="3f130-143">MBAM Server Processor, RAM, and Disk Space Requirements for MBAM</span></span>


<span data-ttu-id="3f130-144">下表列出了使用 Configuration Manager 集成拓扑时 MBAM 服务器的服务器处理器、RAM 和磁盘空间要求。</span><span class="sxs-lookup"><span data-stu-id="3f130-144">The following table lists the server processor, RAM, and disk space requirements for MBAM servers when you are using the Configuration Manager Integration topology.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3f130-145">硬件组件</span><span class="sxs-lookup"><span data-stu-id="3f130-145">Hardware Component</span></span></th>
<th align="left"><span data-ttu-id="3f130-146">最低要求</span><span class="sxs-lookup"><span data-stu-id="3f130-146">Minimum Requirement</span></span></th>
<th align="left"><span data-ttu-id="3f130-147">建议的要求</span><span class="sxs-lookup"><span data-stu-id="3f130-147">Recommended Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3f130-148">处理者</span><span class="sxs-lookup"><span data-stu-id="3f130-148">Processor</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f130-149">2.33 GHz</span><span class="sxs-lookup"><span data-stu-id="3f130-149">2.33 GHz</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f130-150">2.33 GHz 或更高版本</span><span class="sxs-lookup"><span data-stu-id="3f130-150">2.33 GHz or greater</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3f130-151">RAM</span><span class="sxs-lookup"><span data-stu-id="3f130-151">RAM</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f130-152">4 GB</span><span class="sxs-lookup"><span data-stu-id="3f130-152">4 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f130-153">8 GB</span><span class="sxs-lookup"><span data-stu-id="3f130-153">8 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3f130-154">可用磁盘空间</span><span class="sxs-lookup"><span data-stu-id="3f130-154">Free disk space</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f130-155">1 GB</span><span class="sxs-lookup"><span data-stu-id="3f130-155">1 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f130-156">2 GB</span><span class="sxs-lookup"><span data-stu-id="3f130-156">2 GB</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="3f130-157">SQL Server 处理器、RAM 和磁盘空间要求</span><span class="sxs-lookup"><span data-stu-id="3f130-157">SQL Server Processor, RAM, and Disk Space Requirements</span></span>


<span data-ttu-id="3f130-158">下表列出了使用 Configuration Manager 集成拓扑时 SQL Server 计算机的服务器处理器、RAM 和磁盘空间要求。</span><span class="sxs-lookup"><span data-stu-id="3f130-158">The following table lists the server processor, RAM, and disk space requirements for the SQL Server computer when you are using the Configuration Manager Integration topology.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3f130-159">硬件组件</span><span class="sxs-lookup"><span data-stu-id="3f130-159">Hardware Component</span></span></th>
<th align="left"><span data-ttu-id="3f130-160">最低要求</span><span class="sxs-lookup"><span data-stu-id="3f130-160">Minimum Requirement</span></span></th>
<th align="left"><span data-ttu-id="3f130-161">建议的要求</span><span class="sxs-lookup"><span data-stu-id="3f130-161">Recommended Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3f130-162">处理者</span><span class="sxs-lookup"><span data-stu-id="3f130-162">Processor</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f130-163">2.33 GHz</span><span class="sxs-lookup"><span data-stu-id="3f130-163">2.33 GHz</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f130-164">2.33 GHz 或更高版本</span><span class="sxs-lookup"><span data-stu-id="3f130-164">2.33 GHz or greater</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3f130-165">RAM</span><span class="sxs-lookup"><span data-stu-id="3f130-165">RAM</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f130-166">4 GB</span><span class="sxs-lookup"><span data-stu-id="3f130-166">4 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f130-167">8 GB</span><span class="sxs-lookup"><span data-stu-id="3f130-167">8 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3f130-168">可用磁盘空间</span><span class="sxs-lookup"><span data-stu-id="3f130-168">Free disk space</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f130-169">5 GB</span><span class="sxs-lookup"><span data-stu-id="3f130-169">5 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f130-170">5 GB 或以上</span><span class="sxs-lookup"><span data-stu-id="3f130-170">5 GB or greater</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="3f130-171">安装 MBAM 服务器所需的权限</span><span class="sxs-lookup"><span data-stu-id="3f130-171">Required permissions to install the MBAM Server</span></span>


<span data-ttu-id="3f130-172">若要使用 Configuration Manager 安装 MBAM，你必须在配置管理器中拥有具有下表中列出的最低权限的安全角色的管理用户。</span><span class="sxs-lookup"><span data-stu-id="3f130-172">To install MBAM with Configuration Manager, you must have an administrative user in Configuration Manager who has a security role with the minimum permissions listed in the following table.</span></span> <span data-ttu-id="3f130-173">该表还显示了您必须拥有的权限，但不限于基本的计算机管理员权限，以便安装 MBAM 服务器。</span><span class="sxs-lookup"><span data-stu-id="3f130-173">The table also shows the rights that you must have, beyond basic computer administrator rights, to install the MBAM Server.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3f130-174">权限</span><span class="sxs-lookup"><span data-stu-id="3f130-174">Permissions</span></span></th>
<th align="left"><span data-ttu-id="3f130-175">MBAM Server 功能</span><span class="sxs-lookup"><span data-stu-id="3f130-175">MBAM Server Feature</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3f130-176">SQL 实例登录服务器角色：-dbcreator-processadmin</span><span class="sxs-lookup"><span data-stu-id="3f130-176">SQL instance Login Server Roles: - dbcreator- processadmin</span></span></p></td>
<td align="left"><p>- <span data-ttu-id="3f130-177">恢复数据库-审核数据库</span><span class="sxs-lookup"><span data-stu-id="3f130-177">Recovery Database- Audit Database</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3f130-178">SQL Server Reporting Services 实例权限：-创建文件夹-发布报表</span><span class="sxs-lookup"><span data-stu-id="3f130-178">SQL Server Reporting Services instance rights: - Create Folders- Publish Reports</span></span></p></td>
<td align="left"><p>- <span data-ttu-id="3f130-179">System Center Configuration Manager 集成</span><span class="sxs-lookup"><span data-stu-id="3f130-179">System Center Configuration Manager Integration</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="3f130-180">System Center 2012 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="3f130-180">System Center 2012 Configuration Manager</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3f130-181">权限</span><span class="sxs-lookup"><span data-stu-id="3f130-181">Permissions</span></span></th>
<th align="left"><span data-ttu-id="3f130-182">Configuration Manager 服务器功能</span><span class="sxs-lookup"><span data-stu-id="3f130-182">Configuration Manager Server Feature</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3f130-183">Configuration Manager 网站权限：-已读</span><span class="sxs-lookup"><span data-stu-id="3f130-183">Configuration Manager site rights:- Read</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f130-184">System Center Configuration Manager 集成</span><span class="sxs-lookup"><span data-stu-id="3f130-184">System Center Configuration Manager integration</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3f130-185">配置管理器收集权限：-Create-Delete-Read-Modify-部署配置项目</span><span class="sxs-lookup"><span data-stu-id="3f130-185">Configuration Manager collection rights: - Create- Delete- Read- Modify- Deploy Configuration Items</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f130-186">System Center Configuration Manager 集成</span><span class="sxs-lookup"><span data-stu-id="3f130-186">System Center Configuration Manager integration</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3f130-187">Configuration Manager 配置项目权限：-Create-Delete-Read</span><span class="sxs-lookup"><span data-stu-id="3f130-187">Configuration Manager configuration item rights: - Create- Delete- Read</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f130-188">System Center Configuration Manager 集成</span><span class="sxs-lookup"><span data-stu-id="3f130-188">System Center Configuration Manager integration</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="3f130-189">配置管理器 2007</span><span class="sxs-lookup"><span data-stu-id="3f130-189">Configuration Manager 2007</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3f130-190">权限</span><span class="sxs-lookup"><span data-stu-id="3f130-190">Permissions</span></span></th>
<th align="left"><span data-ttu-id="3f130-191">Configuration Manager 服务器功能</span><span class="sxs-lookup"><span data-stu-id="3f130-191">Configuration Manager Server Feature</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3f130-192">Configuration Manager 网站权限：-已读</span><span class="sxs-lookup"><span data-stu-id="3f130-192">Configuration Manager site rights:- Read</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f130-193">System Center Configuration Manager 集成</span><span class="sxs-lookup"><span data-stu-id="3f130-193">System Center Configuration Manager integration</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3f130-194">Configuration Manager 收集权限：-Create-Delete-ReadResource</span><span class="sxs-lookup"><span data-stu-id="3f130-194">Configuration Manager collection rights: - Create- Delete- Read- ReadResource</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f130-195">System Center Configuration Manager 集成</span><span class="sxs-lookup"><span data-stu-id="3f130-195">System Center Configuration Manager integration</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3f130-196">Configuration Manager 配置项目权限：-创建-删除-已读-分发</span><span class="sxs-lookup"><span data-stu-id="3f130-196">Configuration Manager configuration item rights: - Create- Delete- Read- Distribute</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f130-197">System Center Configuration Manager 集成</span><span class="sxs-lookup"><span data-stu-id="3f130-197">System Center Configuration Manager integration</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="3f130-198">配置管理器拓扑的 MBAM 功能的部署顺序</span><span class="sxs-lookup"><span data-stu-id="3f130-198">Order of Deployment of MBAM Features for the Configuration Manager Topology</span></span>


<span data-ttu-id="3f130-199">在 Configuration Manager 服务器上部署 MBAM 时，必须按照以下顺序完成部署任务：</span><span class="sxs-lookup"><span data-stu-id="3f130-199">When deploying MBAM on the Configuration Manager Server, you must complete the deployment tasks in the following order:</span></span>

1.  <span data-ttu-id="3f130-200">在 Configuration Manager 服务器上编辑配置 mof 文件。</span><span class="sxs-lookup"><span data-stu-id="3f130-200">Edit the configuration.mof file on the Configuration Manager Server.</span></span>

2.  <span data-ttu-id="3f130-201">创建或编辑 sms \ _def. mof 文件配置管理器服务器。</span><span class="sxs-lookup"><span data-stu-id="3f130-201">Create or edit the sms\_def.mof file Configuration Manager Server.</span></span>

3.  <span data-ttu-id="3f130-202">在 Configuration Manager 服务器上安装 MBAM。</span><span class="sxs-lookup"><span data-stu-id="3f130-202">Install MBAM on the Configuration Manager Server.</span></span>

4.  <span data-ttu-id="3f130-203">在数据库服务器上安装恢复数据库和审核数据库。</span><span class="sxs-lookup"><span data-stu-id="3f130-203">Install the Recovery Database and the Audit Database on the Database server.</span></span>

5.  <span data-ttu-id="3f130-204">在 "管理和监视" 服务器上安装 MBAM 功能。</span><span class="sxs-lookup"><span data-stu-id="3f130-204">Install the MBAM features on the Administration and Monitoring Server.</span></span>

## <span data-ttu-id="3f130-205">有关通过 Configuration Manager 安装 MBAM 的规划清单</span><span class="sxs-lookup"><span data-stu-id="3f130-205">Planning Checklist for Installing MBAM with Configuration Manager</span></span>


<span data-ttu-id="3f130-206">此清单列出了在规划使用 Configuration Manager 进行 Microsoft BitLocker 管理和监视部署时需要考虑的推荐步骤和高级别的项目列表。</span><span class="sxs-lookup"><span data-stu-id="3f130-206">This checklist outlines the recommended steps and a high-level list of items to consider when planning for an Microsoft BitLocker Administration and Monitoring deployment with Configuration Manager.</span></span> <span data-ttu-id="3f130-207">建议将此清单复制到电子表格程序中，然后对其进行自定义以供使用。</span><span class="sxs-lookup"><span data-stu-id="3f130-207">It is recommended that you copy this checklist into a spreadsheet program and customize it for your use.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left"><span data-ttu-id="3f130-208">任务</span><span class="sxs-lookup"><span data-stu-id="3f130-208">Task</span></span></th>
<th align="left"><span data-ttu-id="3f130-209">引用</span><span class="sxs-lookup"><span data-stu-id="3f130-209">References</span></span></th>
<th align="left"><span data-ttu-id="3f130-210">注释</span><span class="sxs-lookup"><span data-stu-id="3f130-210">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="3f130-211">查看入门信息，介绍 Configuration Manager 如何与 MBAM 配合工作，并显示推荐的高级别体系结构。</span><span class="sxs-lookup"><span data-stu-id="3f130-211">Review the getting started information, which describes how Configuration Manager works with MBAM and shows the recommended high-level architecture.</span></span></p></td>
<td align="left"><p><a href="getting-started---using-mbam-with-configuration-manager.md" data-raw-source="[Getting Started - Using MBAM with Configuration Manager](getting-started---using-mbam-with-configuration-manager.md)"><span data-ttu-id="3f130-212">入门 - 结合使用 MBAM 和 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="3f130-212">Getting Started - Using MBAM with Configuration Manager</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="3f130-213">查看规划信息，其中介绍了每个功能的部署先决条件、支持的配置、所需权限和部署顺序。</span><span class="sxs-lookup"><span data-stu-id="3f130-213">Review the planning information, which describes the deployment prerequisites, supported configurations, required permissions, and deployment order for each feature.</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f130-214">计划使用 Configuration Manager 部署 MBAM</span><span class="sxs-lookup"><span data-stu-id="3f130-214">Planning to Deploy MBAM with Configuration Manager</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="3f130-215">规划和配置 MBAM 组策略要求。</span><span class="sxs-lookup"><span data-stu-id="3f130-215">Plan for and configure MBAM Group Policy requirements.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-20-group-policy-requirements-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Group Policy Requirements](planning-for-mbam-20-group-policy-requirements-mbam-2.md)"><span data-ttu-id="3f130-216">计划 MBAM 2.0 组策略要求</span><span class="sxs-lookup"><span data-stu-id="3f130-216">Planning for MBAM 2.0 Group Policy Requirements</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="3f130-217">规划和创建必要的 Active Directory 域服务安全组，并针对 MBAM 本地安全组成员身份要求进行规划。</span><span class="sxs-lookup"><span data-stu-id="3f130-217">Plan for and create necessary Active Directory Domain Services security groups and plan for MBAM local security group membership requirements.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-20-administrator-roles-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Administrator Roles](planning-for-mbam-20-administrator-roles-mbam-2.md)"><span data-ttu-id="3f130-218">计划 MBAM 2.0 管理员角色</span><span class="sxs-lookup"><span data-stu-id="3f130-218">Planning for MBAM 2.0 Administrator Roles</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="3f130-219">规划部署 MBAM 客户端部署。</span><span class="sxs-lookup"><span data-stu-id="3f130-219">Plan for deploying MBAM Client deployment.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-20-client-deployment-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Client Deployment](planning-for-mbam-20-client-deployment-mbam-2.md)"><span data-ttu-id="3f130-220">计划 MBAM 2.0 客户端部署</span><span class="sxs-lookup"><span data-stu-id="3f130-220">Planning for MBAM 2.0 Client Deployment</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="3f130-221">相关主题</span><span class="sxs-lookup"><span data-stu-id="3f130-221">Related topics</span></span>


[<span data-ttu-id="3f130-222">结合使用 MBAM 和 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="3f130-222">Using MBAM with Configuration Manager</span></span>](using-mbam-with-configuration-manager.md)









