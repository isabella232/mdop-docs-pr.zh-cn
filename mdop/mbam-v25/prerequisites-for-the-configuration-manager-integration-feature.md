---
title: Configuration Manager 集成功能的先决条件
description: Configuration Manager 集成功能的先决条件
author: dansimp
ms.assetid: b318cbd3-b009-44b8-991b-f7364c1cae88
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: af7abd50f6218810dd6718f091512b48fee32652
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803683"
---
# <span data-ttu-id="ae22a-103">Configuration Manager 集成功能的先决条件</span><span class="sxs-lookup"><span data-stu-id="ae22a-103">Prerequisites for the Configuration Manager Integration Feature</span></span>


<span data-ttu-id="ae22a-104">如果使用 System Center Configuration Manager 集成拓扑部署 MBAM，我们建议使用三个服务器体系结构，如[使用 Configuration Manager 集成拓扑的 MBAM 2.5 的高级别体系结构](high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="ae22a-104">If you deploy MBAM with the System Center Configuration Manager Integration topology, we recommend a three-server architecture, as described in [High-Level Architecture of MBAM 2.5 with Configuration Manager Integration Topology](high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md).</span></span> <span data-ttu-id="ae22a-105">此体系结构可以支持500000客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="ae22a-105">This architecture can support 500,000 client computers.</span></span>

**<span data-ttu-id="ae22a-106">重要提示</span><span class="sxs-lookup"><span data-stu-id="ae22a-106">Important</span></span>**  
<span data-ttu-id="ae22a-107">使用 Configuration Manager 2007 时，Configuration Manager 集成拓扑安装不支持 Windows To Go。</span><span class="sxs-lookup"><span data-stu-id="ae22a-107">Windows To Go is not supported for the Configuration Manager Integration topology installation when you are using Configuration Manager 2007.</span></span>



## <span data-ttu-id="ae22a-108">Configuration Manager 集成功能的常规先决条件</span><span class="sxs-lookup"><span data-stu-id="ae22a-108">General prerequisites for the Configuration Manager Integration feature</span></span>


<span data-ttu-id="ae22a-109">当使用配置管理器安装 MBAM 时，除独立拓扑的先决条件之外还需要以下其他先决条件。</span><span class="sxs-lookup"><span data-stu-id="ae22a-109">When you install MBAM with Configuration Manager, the following additional prerequisites are required in addition to the prerequisites for the Stand-alone topology.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ae22a-110">必备</span><span class="sxs-lookup"><span data-stu-id="ae22a-110">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="ae22a-111">其他信息</span><span class="sxs-lookup"><span data-stu-id="ae22a-111">Additional information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ae22a-112">Configuration Manager 服务器是 Configuration Manager 系统中的主站点。</span><span class="sxs-lookup"><span data-stu-id="ae22a-112">The Configuration Manager Server is a primary site in the Configuration Manager system.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ae22a-113">不适用</span><span class="sxs-lookup"><span data-stu-id="ae22a-113">N/A</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ae22a-114">硬件清单客户端代理位于 Configuration Manager 服务器上。</span><span class="sxs-lookup"><span data-stu-id="ae22a-114">The Hardware Inventory Client Agent is on the Configuration Manager Server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ae22a-115">对于 System Center 2012 配置管理器，请参阅 <a href="https://go.microsoft.com/fwlink/?LinkId=301685" data-raw-source="[How to Configure Hardware Inventory in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301685)"> 如何在 Configuration manager 中配置硬件清单 </a> 。</span><span class="sxs-lookup"><span data-stu-id="ae22a-115">For System Center 2012 Configuration Manager, see <a href="https://go.microsoft.com/fwlink/?LinkId=301685" data-raw-source="[How to Configure Hardware Inventory in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301685)">How to Configure Hardware Inventory in Configuration Manager</a>.</span></span></p>
<p><span data-ttu-id="ae22a-116">有关 Configuration Manager 2007 的详细说明，请参阅 <a href="https://go.microsoft.com/fwlink/?LinkId=301656" data-raw-source="[How to Configure Hardware Inventory for a Site](https://go.microsoft.com/fwlink/?LinkId=301656)"> 如何为网站配置硬件清单 </a> 。</span><span class="sxs-lookup"><span data-stu-id="ae22a-116">For Configuration Manager 2007, see <a href="https://go.microsoft.com/fwlink/?LinkId=301656" data-raw-source="[How to Configure Hardware Inventory for a Site](https://go.microsoft.com/fwlink/?LinkId=301656)">How to Configure Hardware Inventory for a Site</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ae22a-117">根据你使用的 Configuration Manager 版本，启用以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="ae22a-117">One of the following is enabled, depending on the version of Configuration Manager that you are using:</span></span></p>
<ul>
<li><p><span data-ttu-id="ae22a-118">合规性设置-（System Center 2012 Configuration Manager）</span><span class="sxs-lookup"><span data-stu-id="ae22a-118">Compliance Settings - (System Center 2012 Configuration Manager)</span></span></p></li>
<li><p><span data-ttu-id="ae22a-119">所需配置管理（DCM）客户端代理–（Configuration Manager 2007）</span><span class="sxs-lookup"><span data-stu-id="ae22a-119">Desired Configuration Management (DCM) Client Agent – (Configuration Manager 2007)</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="ae22a-120">对于 System Center 2012 配置管理器，请参阅配置 <a href="https://go.microsoft.com/fwlink/?LinkId=301687" data-raw-source="[Configuring Compliance Settings in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301687)"> 管理器中的配置合规性设置 </a> 。</span><span class="sxs-lookup"><span data-stu-id="ae22a-120">For System Center 2012 Configuration Manager, see <a href="https://go.microsoft.com/fwlink/?LinkId=301687" data-raw-source="[Configuring Compliance Settings in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301687)">Configuring Compliance Settings in Configuration Manager</a>.</span></span></p>
<p><span data-ttu-id="ae22a-121">对于 Configuration Manager 2007，请参阅 <a href="https://go.microsoft.com/fwlink/?LinkId=301686" data-raw-source="[Desired Configuration Management Client Agent Properties](https://go.microsoft.com/fwlink/?LinkId=301686)"> 所需的配置管理客户端代理属性 </a> 。</span><span class="sxs-lookup"><span data-stu-id="ae22a-121">For Configuration Manager 2007, see <a href="https://go.microsoft.com/fwlink/?LinkId=301686" data-raw-source="[Desired Configuration Management Client Agent Properties](https://go.microsoft.com/fwlink/?LinkId=301686)">Desired Configuration Management Client Agent Properties</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ae22a-122">报告服务点在配置管理器中定义。</span><span class="sxs-lookup"><span data-stu-id="ae22a-122">A reporting services point is defined in Configuration Manager.</span></span> <span data-ttu-id="ae22a-123">对于 SQL Server Reporting Services （SSRS）是必需的。</span><span class="sxs-lookup"><span data-stu-id="ae22a-123">Required for SQL Server Reporting Services (SSRS).</span></span></p></td>
<td align="left"><p><span data-ttu-id="ae22a-124">对于 System Center 2012 配置管理器，请参阅 <a href="https://go.microsoft.com/fwlink/?LinkId=301689" data-raw-source="[Prerequisites for Reporting in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301689)"> 配置管理器中的报告先决条件 </a> 。</span><span class="sxs-lookup"><span data-stu-id="ae22a-124">For System Center 2012 Configuration Manager, see <a href="https://go.microsoft.com/fwlink/?LinkId=301689" data-raw-source="[Prerequisites for Reporting in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301689)">Prerequisites for Reporting in Configuration Manager</a>.</span></span></p>
<p><span data-ttu-id="ae22a-125">有关 Configuration Manager 2007 的详细说明，请参阅 <a href="https://go.microsoft.com/fwlink/?LinkId=301688" data-raw-source="[How to Create a Reporting Services Point for SQL Reporting Services](https://go.microsoft.com/fwlink/?LinkId=301688)"> 如何为 SQL Reporting Services 创建 Reporting Services 点 </a> 。</span><span class="sxs-lookup"><span data-stu-id="ae22a-125">For Configuration Manager 2007, see <a href="https://go.microsoft.com/fwlink/?LinkId=301688" data-raw-source="[How to Create a Reporting Services Point for SQL Reporting Services](https://go.microsoft.com/fwlink/?LinkId=301688)">How to Create a Reporting Services Point for SQL Reporting Services</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ae22a-126">Configuration Manager 2007 需要 Microsoft .NET Framework 2。0</span><span class="sxs-lookup"><span data-stu-id="ae22a-126">Configuration Manager 2007 requires Microsoft .NET Framework 2.0</span></span></p></td>
<td align="left"><p><span data-ttu-id="ae22a-127">Configuration Manager 2007 中所需的配置管理（DCM）客户端代理需要 .NET Framework 2.0 来报告合规性。</span><span class="sxs-lookup"><span data-stu-id="ae22a-127">The Desired Configuration Management (DCM) Client Agent in Configuration Manager 2007 requires .NET Framework 2.0 to report compliance.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="ae22a-128">注意</span><span class="sxs-lookup"><span data-stu-id="ae22a-128">Note</span></span></strong><br/><p><span data-ttu-id="ae22a-129">安装 .NET Framework 3.5 会自动安装 .NET Framework 2.0。</span><span class="sxs-lookup"><span data-stu-id="ae22a-129">Installing .NET Framework 3.5 automatically installs .NET Framework 2.0.</span></span></p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="ae22a-130">通过 Configuration Manager 安装 MBAM 所需的权限</span><span class="sxs-lookup"><span data-stu-id="ae22a-130">Required permissions to install MBAM with Configuration Manager</span></span>


<span data-ttu-id="ae22a-131">若要使用 Configuration Manager 安装 MBAM，你必须在配置管理器中拥有具有下表中列出的最低权限的安全角色的管理用户。</span><span class="sxs-lookup"><span data-stu-id="ae22a-131">To install MBAM with Configuration Manager, you must have an administrative user in Configuration Manager who has a security role with the minimum permissions listed in the following table.</span></span> <span data-ttu-id="ae22a-132">该表还显示了您必须拥有的权限，但不限于基本的计算机管理员权限，以便安装 MBAM 服务器。</span><span class="sxs-lookup"><span data-stu-id="ae22a-132">The table also shows the rights that you must have, beyond basic computer administrator rights, to install the MBAM Server.</span></span>

**<span data-ttu-id="ae22a-133">下表中的权限适用于两个版本的 Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="ae22a-133">The permissions in the following table apply to both versions of Configuration Manager.</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ae22a-134">权限</span><span class="sxs-lookup"><span data-stu-id="ae22a-134">Permissions</span></span></th>
<th align="left"><span data-ttu-id="ae22a-135">MBAM Server 功能</span><span class="sxs-lookup"><span data-stu-id="ae22a-135">MBAM Server feature</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ae22a-136">SQL Server 实例登录服务器角色：-dbcreator-processadmin</span><span class="sxs-lookup"><span data-stu-id="ae22a-136">SQL Server instance login server roles: - dbcreator- processadmin</span></span></p></td>
<td align="left"><p>- <span data-ttu-id="ae22a-137">恢复数据库-审核数据库</span><span class="sxs-lookup"><span data-stu-id="ae22a-137">Recovery Database- Audit Database</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ae22a-138">SSRS 实例权限：-创建文件夹-发布报表</span><span class="sxs-lookup"><span data-stu-id="ae22a-138">SSRS instance rights: - Create Folders- Publish Reports</span></span></p></td>
<td align="left"><p>- <span data-ttu-id="ae22a-139">System Center Configuration Manager 集成</span><span class="sxs-lookup"><span data-stu-id="ae22a-139">System Center Configuration Manager Integration</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="ae22a-140">System Center 2012 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="ae22a-140">System Center 2012 Configuration Manager</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ae22a-141">权限</span><span class="sxs-lookup"><span data-stu-id="ae22a-141">Permissions</span></span></th>
<th align="left"><span data-ttu-id="ae22a-142">Configuration Manager 服务器功能</span><span class="sxs-lookup"><span data-stu-id="ae22a-142">Configuration Manager Server feature</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ae22a-143">Configuration Manager 网站权限：-已读</span><span class="sxs-lookup"><span data-stu-id="ae22a-143">Configuration Manager site rights:- Read</span></span></p></td>
<td align="left"><p><span data-ttu-id="ae22a-144">System Center Configuration Manager 集成</span><span class="sxs-lookup"><span data-stu-id="ae22a-144">System Center Configuration Manager Integration</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ae22a-145">配置管理器收集权限：-Create-Delete-Read-Modify-部署配置项目</span><span class="sxs-lookup"><span data-stu-id="ae22a-145">Configuration Manager collection rights: - Create- Delete- Read- Modify- Deploy Configuration Items</span></span></p></td>
<td align="left"><p><span data-ttu-id="ae22a-146">System Center Configuration Manager 集成</span><span class="sxs-lookup"><span data-stu-id="ae22a-146">System Center Configuration Manager Integration</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ae22a-147">Configuration Manager 配置项目权限：-Create-Delete-Read</span><span class="sxs-lookup"><span data-stu-id="ae22a-147">Configuration Manager configuration item rights: - Create- Delete- Read</span></span></p></td>
<td align="left"><p><span data-ttu-id="ae22a-148">System Center Configuration Manager 集成</span><span class="sxs-lookup"><span data-stu-id="ae22a-148">System Center Configuration Manager Integration</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="ae22a-149">配置管理器 2007</span><span class="sxs-lookup"><span data-stu-id="ae22a-149">Configuration Manager 2007</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ae22a-150">权限</span><span class="sxs-lookup"><span data-stu-id="ae22a-150">Permissions</span></span></th>
<th align="left"><span data-ttu-id="ae22a-151">Configuration Manager 服务器功能</span><span class="sxs-lookup"><span data-stu-id="ae22a-151">Configuration Manager Server feature</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ae22a-152">Configuration Manager 网站权限：-已读</span><span class="sxs-lookup"><span data-stu-id="ae22a-152">Configuration Manager site rights:- Read</span></span></p></td>
<td align="left"><p><span data-ttu-id="ae22a-153">System Center Configuration Manager 集成</span><span class="sxs-lookup"><span data-stu-id="ae22a-153">System Center Configuration Manager Integration</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ae22a-154">Configuration Manager 收集权限：-Create-Delete-ReadResource</span><span class="sxs-lookup"><span data-stu-id="ae22a-154">Configuration Manager collection rights: - Create- Delete- Read- ReadResource</span></span></p></td>
<td align="left"><p><span data-ttu-id="ae22a-155">System Center Configuration Manager 集成</span><span class="sxs-lookup"><span data-stu-id="ae22a-155">System Center Configuration Manager Integration</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ae22a-156">Configuration Manager 配置项目权限：-创建-删除-已读-分发</span><span class="sxs-lookup"><span data-stu-id="ae22a-156">Configuration Manager configuration item rights: - Create- Delete- Read- Distribute</span></span></p></td>
<td align="left"><p><span data-ttu-id="ae22a-157">System Center Configuration Manager 集成</span><span class="sxs-lookup"><span data-stu-id="ae22a-157">System Center Configuration Manager Integration</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="ae22a-158">对 mof 文件所需的更改</span><span class="sxs-lookup"><span data-stu-id="ae22a-158">Required changes for the .mof files</span></span>


<span data-ttu-id="ae22a-159">若要使客户端计算机能够通过 MBAM Configuration Manager 报表报告 BitLocker 合规性详细信息，你必须编辑 System Center 2012 Configuration Manager 和 Microsoft System Center Configuration Manager 2007 的 Configuration 文件和 Sms \ _def mof 文件。</span><span class="sxs-lookup"><span data-stu-id="ae22a-159">To enable the client computers to report BitLocker compliance details through the MBAM Configuration Manager reports, you have to edit the Configuration.mof file and Sms\_def.mof file for System Center 2012 Configuration Manager and Microsoft System Center Configuration Manager 2007.</span></span> <span data-ttu-id="ae22a-160">有关说明，请参阅[仅适用于 Configuration Manager 集成拓扑的 MBAM 2.5 Server 先决条件](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="ae22a-160">For instructions, see [MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md).</span></span>



## <span data-ttu-id="ae22a-161">相关主题</span><span class="sxs-lookup"><span data-stu-id="ae22a-161">Related topics</span></span>


[<span data-ttu-id="ae22a-162">独立和 Configuration Manager 集成拓扑的 MBAM 2.5 服务器先决条件</span><span class="sxs-lookup"><span data-stu-id="ae22a-162">MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies</span></span>](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)

[<span data-ttu-id="ae22a-163">仅适用于 Configuration Manager 集成拓扑的 MBAM 2.5 服务器先决条件</span><span class="sxs-lookup"><span data-stu-id="ae22a-163">MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology</span></span>](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)



## <span data-ttu-id="ae22a-164">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="ae22a-164">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="ae22a-165">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="ae22a-165">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="ae22a-166">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="ae22a-166">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





