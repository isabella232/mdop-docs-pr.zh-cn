---
title: 独立和 Configuration Manager 集成拓扑的 MBAM 2.5 服务器先决条件
description: 独立和 Configuration Manager 集成拓扑的 MBAM 2.5 服务器先决条件
author: dansimp
ms.assetid: 76a6047a-5c6e-42ff-af09-a6f382a69537
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: c9af551b1d867f61912bbf3b759574a840b0645c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803880"
---
# <span data-ttu-id="d45c2-103">独立和 Configuration Manager 集成拓扑的 MBAM 2.5 服务器先决条件</span><span class="sxs-lookup"><span data-stu-id="d45c2-103">MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies</span></span>


<span data-ttu-id="d45c2-104">在开始 Microsoft BitLocker 管理和监视（MBAM）安装之前，必须完成本主题中列出的先决条件。</span><span class="sxs-lookup"><span data-stu-id="d45c2-104">Before starting the Microsoft BitLocker Administration and Monitoring (MBAM) installation, you must complete the prerequisites listed in this topic.</span></span> <span data-ttu-id="d45c2-105">这些先决条件适用于 MBAM 独立拓扑和 System Center Configuration Manager 集成拓扑。</span><span class="sxs-lookup"><span data-stu-id="d45c2-105">These prerequisites apply to the MBAM Stand-alone topology and System Center Configuration Manager Integration topology.</span></span>

<span data-ttu-id="d45c2-106">如果你使用 System Center Configuration Manager 部署 MBAM，则必须完成其他先决条件，这些先决条件将在[仅适用于 Configuration Manager 集成拓扑的 MBAM 2.5 服务器必备项](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)中列出。</span><span class="sxs-lookup"><span data-stu-id="d45c2-106">If you are deploying MBAM with System Center Configuration Manager, you must complete additional prerequisites, which are listed in [MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md).</span></span>

<span data-ttu-id="d45c2-107">有关 MBAM 支持的硬件和操作系统的列表，请参阅[MBAM 2.5 支持的配置](mbam-25-supported-configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="d45c2-107">For a list of the supported hardware and operating systems for MBAM, see [MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md).</span></span>

**<span data-ttu-id="d45c2-108">重要提示</span><span class="sxs-lookup"><span data-stu-id="d45c2-108">Important</span></span>**  
<span data-ttu-id="d45c2-109">如果在没有 MBAM 的情况下使用 BitLocker，则必须解密驱动器，然后使用清除 TPM。</span><span class="sxs-lookup"><span data-stu-id="d45c2-109">If BitLocker was used without MBAM, you must decrypt the drive and then clear TPM using tpm.msc.</span></span> <span data-ttu-id="d45c2-110">如果客户端电脑已加密，并且 TPM 所有者密码已创建，MBAM 不能取得 TPM 的所有权。</span><span class="sxs-lookup"><span data-stu-id="d45c2-110">MBAM cannot take ownership of TPM if the client PC is already encrypted and the TPM owner password created.</span></span>



## <span data-ttu-id="d45c2-111">必需的 MBAM 角色和帐户</span><span class="sxs-lookup"><span data-stu-id="d45c2-111">Required MBAM roles and accounts</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d45c2-112">必备</span><span class="sxs-lookup"><span data-stu-id="d45c2-112">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="d45c2-113">详细信息</span><span class="sxs-lookup"><span data-stu-id="d45c2-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d45c2-114">在 Active Directory 域服务（AD DS）中创建的组</span><span class="sxs-lookup"><span data-stu-id="d45c2-114">Groups created in Active Directory Domain Services (AD DS)</span></span></p></td>
<td align="left"><p><span data-ttu-id="d45c2-115">有关 <a href="planning-for-mbam-25-groups-and-accounts.md" data-raw-source="[Planning for MBAM 2.5 Groups and Accounts](planning-for-mbam-25-groups-and-accounts.md)"> 这些组和帐户的说明，请参阅规划 MBAM 2.5 组和帐户 </a> 。</span><span class="sxs-lookup"><span data-stu-id="d45c2-115">See <a href="planning-for-mbam-25-groups-and-accounts.md" data-raw-source="[Planning for MBAM 2.5 Groups and Accounts](planning-for-mbam-25-groups-and-accounts.md)">Planning for MBAM 2.5 Groups and Accounts</a> for a description of these groups and accounts.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="d45c2-116">恢复数据库的先决条件</span><span class="sxs-lookup"><span data-stu-id="d45c2-116">Prerequisites for the Recovery Database</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d45c2-117">必备</span><span class="sxs-lookup"><span data-stu-id="d45c2-117">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="d45c2-118">详细信息</span><span class="sxs-lookup"><span data-stu-id="d45c2-118">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d45c2-119">SQL Server 支持的版本</span><span class="sxs-lookup"><span data-stu-id="d45c2-119">Supported version of SQL Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="d45c2-120">安装包含 SQL_Latin1_General_CP1_CI_AS 排序规则的 Microsoft SQL Server。</span><span class="sxs-lookup"><span data-stu-id="d45c2-120">Install Microsoft SQL Server with SQL_Latin1_General_CP1_CI_AS collation.</span></span></p>
<p><span data-ttu-id="d45c2-121"><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"> </a> 有关支持的版本，请参阅 MBAM 2.5 支持的配置。</span><span class="sxs-lookup"><span data-stu-id="d45c2-121">See <a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)">MBAM 2.5 Supported Configurations</a> for supported versions.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d45c2-122">所需的 SQL Server 权限</span><span class="sxs-lookup"><span data-stu-id="d45c2-122">Required SQL Server permissions</span></span></p></td>
<td align="left"><p><span data-ttu-id="d45c2-123">所需权限：</span><span class="sxs-lookup"><span data-stu-id="d45c2-123">Required permissions:</span></span></p>
<ul>
<li><p><span data-ttu-id="d45c2-124">SQL Server 实例登录服务器角色：</span><span class="sxs-lookup"><span data-stu-id="d45c2-124">SQL Server instance login server roles:</span></span></p>
<ul>
<li><p><span data-ttu-id="d45c2-125">dbcreator</span><span class="sxs-lookup"><span data-stu-id="d45c2-125">dbcreator</span></span></p></li>
<li><p><span data-ttu-id="d45c2-126">processadmin</span><span class="sxs-lookup"><span data-stu-id="d45c2-126">processadmin</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="d45c2-127">SQL Server Reporting Services 实例权限：</span><span class="sxs-lookup"><span data-stu-id="d45c2-127">SQL Server Reporting Services instance rights:</span></span></p>
<ul>
<li><p><span data-ttu-id="d45c2-128">创建文件夹</span><span class="sxs-lookup"><span data-stu-id="d45c2-128">Create Folders</span></span></p></li>
<li><p><span data-ttu-id="d45c2-129">发布报表</span><span class="sxs-lookup"><span data-stu-id="d45c2-129">Publish Reports</span></span></p></li>
</ul></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d45c2-130">可选-安装 SQL Server 中可用的透明数据加密（TDE）功能</span><span class="sxs-lookup"><span data-stu-id="d45c2-130">Optional - Install the Transparent Data Encryption (TDE) feature available in SQL Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="d45c2-131">TDE SQL Server 功能对数据和日志文件执行实时 i/o 加密和解密，这有助于你遵守适用于各种行业的法律、法规和指南。</span><span class="sxs-lookup"><span data-stu-id="d45c2-131">The TDE SQL Server feature performs real-time I/O encryption and decryption of the data and log files, which can help you to comply with laws, regulations, and guidelines that apply to various industries.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="d45c2-132">注意</span><span class="sxs-lookup"><span data-stu-id="d45c2-132">Note</span></span></strong><br/><p><span data-ttu-id="d45c2-133">TDE 执行数据库信息的实时解密。</span><span class="sxs-lookup"><span data-stu-id="d45c2-133">TDE performs real-time decryption of database information.</span></span> <span data-ttu-id="d45c2-134">这意味着，如果你在 SQL Server 数据库中查看恢复密钥信息，并且在具有数据库权限的帐户上登录，则恢复密钥信息将可见。</span><span class="sxs-lookup"><span data-stu-id="d45c2-134">This means that, if you are viewing recovery key information in the SQL Server database and you are logged on under an account that has permissions to the database, the recovery key information is visible.</span></span> <span data-ttu-id="d45c2-135">若要了解有关 TDE 的详细信息，请参阅 <a href="mbam-25-security-considerations.md" data-raw-source="[MBAM 2.5 Security Considerations](mbam-25-security-considerations.md)"> MBAM 2.5 安全注意事项 </a> 。</span><span class="sxs-lookup"><span data-stu-id="d45c2-135">To read more about TDE, see <a href="mbam-25-security-considerations.md" data-raw-source="[MBAM 2.5 Security Considerations](mbam-25-security-considerations.md)">MBAM 2.5 Security Considerations</a>.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d45c2-136">SQL Server 数据库引擎服务</span><span class="sxs-lookup"><span data-stu-id="d45c2-136">SQL Server Database Engine Services</span></span></p></td>
<td align="left"><p><span data-ttu-id="d45c2-137">必须在 MBAM 服务器安装期间安装并运行 SQL Server 数据库引擎服务。</span><span class="sxs-lookup"><span data-stu-id="d45c2-137">SQL Server Database Engine Services must be installed and running during MBAM Server installation.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d45c2-138">Windows PowerShell 3.0 或更高版本</span><span class="sxs-lookup"><span data-stu-id="d45c2-138">Windows PowerShell 3.0 or later</span></span></p></td>
<td align="left"><p><span data-ttu-id="d45c2-139">如果使用 Windows PowerShell 配置来自远程计算机的数据库，则无需在恢复数据库服务器上安装 windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="d45c2-139">Windows PowerShell does not have to be installed on the Recovery Database server if you are using Windows PowerShell to configure the database from a remote computer.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="d45c2-140">合规性和审核数据库的先决条件</span><span class="sxs-lookup"><span data-stu-id="d45c2-140">Prerequisites for the Compliance and Audit Database</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d45c2-141">必备</span><span class="sxs-lookup"><span data-stu-id="d45c2-141">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="d45c2-142">详细信息</span><span class="sxs-lookup"><span data-stu-id="d45c2-142">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d45c2-143">SQL Server 支持的版本</span><span class="sxs-lookup"><span data-stu-id="d45c2-143">Supported version of SQL Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="d45c2-144">安装包含 SQL_Latin1_General_CP1_CI_AS 排序规则的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="d45c2-144">Install SQL Server with SQL_Latin1_General_CP1_CI_AS collation.</span></span></p>
<p><span data-ttu-id="d45c2-145"><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"> </a> 有关支持的版本，请参阅 MBAM 2.5 支持的配置。</span><span class="sxs-lookup"><span data-stu-id="d45c2-145">See <a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)">MBAM 2.5 Supported Configurations</a> for supported versions.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d45c2-146">所需的 SQL Server 权限</span><span class="sxs-lookup"><span data-stu-id="d45c2-146">Required SQL Server permissions</span></span></p></td>
<td align="left"><p><span data-ttu-id="d45c2-147">所需权限：</span><span class="sxs-lookup"><span data-stu-id="d45c2-147">Required permissions:</span></span></p>
<ul>
<li><p><span data-ttu-id="d45c2-148">SQL Server 实例登录服务器角色：</span><span class="sxs-lookup"><span data-stu-id="d45c2-148">SQL Server instance login server roles:</span></span></p>
<ul>
<li><p><span data-ttu-id="d45c2-149">dbcreator</span><span class="sxs-lookup"><span data-stu-id="d45c2-149">dbcreator</span></span></p></li>
<li><p><span data-ttu-id="d45c2-150">processadmin</span><span class="sxs-lookup"><span data-stu-id="d45c2-150">processadmin</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="d45c2-151">SQL Server Reporting Services 实例权限：</span><span class="sxs-lookup"><span data-stu-id="d45c2-151">SQL Server Reporting Services instance rights:</span></span></p>
<ul>
<li><p><span data-ttu-id="d45c2-152">创建文件夹</span><span class="sxs-lookup"><span data-stu-id="d45c2-152">Create Folders</span></span></p></li>
<li><p><span data-ttu-id="d45c2-153">发布报表</span><span class="sxs-lookup"><span data-stu-id="d45c2-153">Publish Reports</span></span></p></li>
</ul></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d45c2-154">可选-在 SQL Server 中安装透明数据加密（TDE）功能</span><span class="sxs-lookup"><span data-stu-id="d45c2-154">Optional - Install the Transparent Data Encryption (TDE) feature in SQL Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="d45c2-155">TDE SQL Server 功能对数据和日志文件执行实时 i/o 加密和解密，这有助于你遵守适用于各种行业的法律、法规和指南。</span><span class="sxs-lookup"><span data-stu-id="d45c2-155">The TDE SQL Server feature performs real-time I/O encryption and decryption of the data and log files, which can help you to comply with laws, regulations, and guidelines that apply to various industries.</span></span></p>
<p><span data-ttu-id="d45c2-156">TDE 执行数据库信息的实时解密。</span><span class="sxs-lookup"><span data-stu-id="d45c2-156">TDE performs real-time decryption of database information.</span></span> <span data-ttu-id="d45c2-157">这意味着，如果你在 SQL Server 数据库中查看恢复密钥信息，并且在具有数据库权限的帐户上登录，则恢复密钥信息将可见。</span><span class="sxs-lookup"><span data-stu-id="d45c2-157">This means that, if you are viewing recovery key information in the SQL Server database and you are logged on under an account that has permissions to the database, the recovery key information is visible.</span></span> <span data-ttu-id="d45c2-158">若要了解有关 TDE 的详细信息，请参阅 <a href="mbam-25-security-considerations.md" data-raw-source="[MBAM 2.5 Security Considerations](mbam-25-security-considerations.md)"> MBAM 2.5 安全注意事项 </a> 。</span><span class="sxs-lookup"><span data-stu-id="d45c2-158">To read more about TDE, see <a href="mbam-25-security-considerations.md" data-raw-source="[MBAM 2.5 Security Considerations](mbam-25-security-considerations.md)">MBAM 2.5 Security Considerations</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d45c2-159">SQL Server 数据库引擎服务</span><span class="sxs-lookup"><span data-stu-id="d45c2-159">SQL Server Database Engine Services</span></span></p></td>
<td align="left"><p><span data-ttu-id="d45c2-160">必须在 MBAM 服务器安装期间安装并运行 SQL Server 数据库引擎服务。</span><span class="sxs-lookup"><span data-stu-id="d45c2-160">SQL Server Database Engine Services must be installed and running during MBAM Server installation.</span></span> <span data-ttu-id="d45c2-161">但是，SQL Server 可以远程运行;它不必在要安装 MBAM Server 软件的同一服务器上。</span><span class="sxs-lookup"><span data-stu-id="d45c2-161">However, SQL Server can be running remotely; it doesn’t have to be on the same server on which you are installing the MBAM Server software.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d45c2-162">Windows PowerShell 3.0 或更高版本</span><span class="sxs-lookup"><span data-stu-id="d45c2-162">Windows PowerShell 3.0 or later</span></span></p></td>
<td align="left"><p><span data-ttu-id="d45c2-163">如果使用 Windows PowerShell 配置来自远程计算机的数据库，则无需在合规性和审核数据库服务器上安装 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="d45c2-163">Windows PowerShell does not have to be installed on the Compliance and Audit Database server if you are using Windows PowerShell to configure the database from a remote computer.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="d45c2-164">报表的先决条件</span><span class="sxs-lookup"><span data-stu-id="d45c2-164">Prerequisites for the Reports</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d45c2-165">必备</span><span class="sxs-lookup"><span data-stu-id="d45c2-165">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="d45c2-166">详细信息</span><span class="sxs-lookup"><span data-stu-id="d45c2-166">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d45c2-167">SQL Server 支持的版本</span><span class="sxs-lookup"><span data-stu-id="d45c2-167">Supported version of SQL Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="d45c2-168">安装包含 SQL_Latin1_General_CP1_CI_AS 排序规则的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="d45c2-168">Install SQL Server with SQL_Latin1_General_CP1_CI_AS collation.</span></span></p>
<p><span data-ttu-id="d45c2-169"><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"> </a> 有关支持的版本，请参阅 MBAM 2.5 支持的配置。</span><span class="sxs-lookup"><span data-stu-id="d45c2-169">See <a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)">MBAM 2.5 Supported Configurations</a> for supported versions.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d45c2-170">SQL Server Reporting Services （SSRS）</span><span class="sxs-lookup"><span data-stu-id="d45c2-170">SQL Server Reporting Services (SSRS)</span></span></p></td>
<td align="left"><p><span data-ttu-id="d45c2-171">在 MBAM 服务器安装期间，必须安装并运行 SSRS。</span><span class="sxs-lookup"><span data-stu-id="d45c2-171">SSRS must be installed and running during the MBAM Server installation.</span></span></p>
<p><span data-ttu-id="d45c2-172">在 &quot; 纯 &quot; 模式下配置 SSRS，而不是在未配置或 &quot; SharePoint &quot; 模式下配置 SSRS。</span><span class="sxs-lookup"><span data-stu-id="d45c2-172">Configure SSRS in &quot;native&quot; mode and not in unconfigured or &quot;SharePoint&quot; mode.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d45c2-173">SSRS 实例权限-仅当在配置了报表的服务器所在服务器上安装数据库时，才需要配置报表。</span><span class="sxs-lookup"><span data-stu-id="d45c2-173">SSRS instance rights – required for configuring Reports only if you are installing databases on a separate server from the server where Reports are configured.</span></span></p></td>
<td align="left"><p><span data-ttu-id="d45c2-174">所需实例权限：</span><span class="sxs-lookup"><span data-stu-id="d45c2-174">Required instance rights:</span></span></p>
<ul>
<li><p><span data-ttu-id="d45c2-175">创建文件夹</span><span class="sxs-lookup"><span data-stu-id="d45c2-175">Create Folders</span></span></p></li>
<li><p><span data-ttu-id="d45c2-176">发布报表</span><span class="sxs-lookup"><span data-stu-id="d45c2-176">Publish Reports</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d45c2-177">Windows PowerShell 3.0 或更高版本</span><span class="sxs-lookup"><span data-stu-id="d45c2-177">Windows PowerShell 3.0 or later</span></span></p></td>
<td align="left"><p><span data-ttu-id="d45c2-178">如果使用 Windows PowerShell 配置来自远程计算机的数据库，则无需在此数据库服务器上安装 windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="d45c2-178">Windows PowerShell does not have to be installed on this Database server if you are using Windows PowerShell to configure the database from a remote computer.</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-prereqsams"></a><span data-ttu-id="d45c2-179">管理和监视服务器的先决条件</span><span class="sxs-lookup"><span data-stu-id="d45c2-179">Prerequisites for the Administration and Monitoring Server</span></span>


<span data-ttu-id="d45c2-180">下表列出了 MBAM 管理和监视服务器的安装先决条件。</span><span class="sxs-lookup"><span data-stu-id="d45c2-180">The following table lists the installation prerequisites for the MBAM Administration and Monitoring Server.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d45c2-181">必备</span><span class="sxs-lookup"><span data-stu-id="d45c2-181">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="d45c2-182">详细信息</span><span class="sxs-lookup"><span data-stu-id="d45c2-182">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d45c2-183">Windows Server Web 服务器角色</span><span class="sxs-lookup"><span data-stu-id="d45c2-183">Windows Server Web Server Role</span></span></p></td>
<td align="left"><p><span data-ttu-id="d45c2-184">此角色必须添加到 "管理和监视服务器" 功能支持的服务器操作系统。</span><span class="sxs-lookup"><span data-stu-id="d45c2-184">This role must be added to a server operating system that is supported for the Administration and Monitoring Server feature.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d45c2-185">Web 服务器（IIS）管理工具</span><span class="sxs-lookup"><span data-stu-id="d45c2-185">Web Server (IIS) Management Tools</span></span></p></td>
<td align="left"><p><span data-ttu-id="d45c2-186">单击 " <strong> IIS 管理脚本和工具" </strong> 。</span><span class="sxs-lookup"><span data-stu-id="d45c2-186">Click <strong>IIS Management Scripts and Tools</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="d45c2-187">SSL 证书</span><span class="sxs-lookup"><span data-stu-id="d45c2-187">SSL Certificate</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="d45c2-188">可选。</span><span class="sxs-lookup"><span data-stu-id="d45c2-188">Optional.</span></span> <span data-ttu-id="d45c2-189">若要保护客户端计算机和 web 服务之间的通信，你必须获取并安装受信任的安全机构签名的证书。</span><span class="sxs-lookup"><span data-stu-id="d45c2-189">To secure communication between the client computers and the web services, you must obtain and install a certificate that a trusted security authority signed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d45c2-190">Web 服务器角色服务</span><span class="sxs-lookup"><span data-stu-id="d45c2-190">Web Server Role Services</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="d45c2-191">常见的 HTTP 功能：</span><span class="sxs-lookup"><span data-stu-id="d45c2-191">Common HTTP Features:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="d45c2-192">静态内容</span><span class="sxs-lookup"><span data-stu-id="d45c2-192">Static Content</span></span></p></li>
<li><p><span data-ttu-id="d45c2-193">默认文档</span><span class="sxs-lookup"><span data-stu-id="d45c2-193">Default Document</span></span></p></li>
</ul>
<p><strong><span data-ttu-id="d45c2-194">应用程序开发：</span><span class="sxs-lookup"><span data-stu-id="d45c2-194">Application Development:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="d45c2-195">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="d45c2-195">ASP.NET</span></span></p></li>
<li><p><span data-ttu-id="d45c2-196">.NET 扩展性</span><span class="sxs-lookup"><span data-stu-id="d45c2-196">.NET Extensibility</span></span></p></li>
<li><p><span data-ttu-id="d45c2-197">ISAPI 扩展</span><span class="sxs-lookup"><span data-stu-id="d45c2-197">ISAPI Extensions</span></span></p></li>
<li><p><span data-ttu-id="d45c2-198">ISAPI 筛选器</span><span class="sxs-lookup"><span data-stu-id="d45c2-198">ISAPI Filters</span></span></p></li>
</ul>
<p><strong><span data-ttu-id="d45c2-199">安全</span><span class="sxs-lookup"><span data-stu-id="d45c2-199">Security:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="d45c2-200">Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="d45c2-200">Windows Authentication</span></span></p></li>
<li><p><span data-ttu-id="d45c2-201">请求筛选</span><span class="sxs-lookup"><span data-stu-id="d45c2-201">Request Filtering</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d45c2-202">Windows Server 功能</span><span class="sxs-lookup"><span data-stu-id="d45c2-202">Windows Server Features</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="d45c2-203">.NET Framework 4.5 功能：</span><span class="sxs-lookup"><span data-stu-id="d45c2-203">.NET Framework 4.5 features:</span></span></strong></p>
<ul>
<li><p><strong><span data-ttu-id="d45c2-204">.NET Framework 4.5 或4。6</span><span class="sxs-lookup"><span data-stu-id="d45c2-204">.NET Framework 4.5 or 4.6</span></span></strong></p>
<ul>
<li><p><strong><span data-ttu-id="d45c2-205"></strong> - 已为这些版本的 windows server 安装了 windows server 2016 .net Framework 4.6，但必须启用它。</span><span class="sxs-lookup"><span data-stu-id="d45c2-205">Windows Server 2016</strong> - .NET Framework 4.6 is already installed for these versions of Windows Server, but you must enable it.</span></span></p></li>  
<li><p><strong><span data-ttu-id="d45c2-206">Windows server 2012 或 Windows Server 2012 R2 </strong> - .net Framework 4.5 已针对这些版本的 windows server 安装，但必须启用它。</span><span class="sxs-lookup"><span data-stu-id="d45c2-206">Windows Server 2012 or Windows Server 2012 R2</strong> - .NET Framework 4.5 is already installed for these versions of Windows Server, but you must enable it.</span></span></p></li>
<li><p><strong><span data-ttu-id="d45c2-207">Windows server 2008 R2 </strong> - .net framework 4.5 不包含在 windows Server 2008 R2 中，因此必须 <a href="https://go.microsoft.com/fwlink/?LinkId=392318" data-raw-source="[download Microsoft .NET Framework 4.5](https://go.microsoft.com/fwlink/?LinkId=392318)"> 下载 Microsoft .net Framework 4.5 </a> 并单独安装。</span><span class="sxs-lookup"><span data-stu-id="d45c2-207">Windows Server 2008 R2</strong> - .NET Framework 4.5 is not included with Windows Server 2008 R2, so you must <a href="https://go.microsoft.com/fwlink/?LinkId=392318" data-raw-source="[download Microsoft .NET Framework 4.5](https://go.microsoft.com/fwlink/?LinkId=392318)">download Microsoft .NET Framework 4.5</a> and install it separately.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="d45c2-208">注意</span><span class="sxs-lookup"><span data-stu-id="d45c2-208">Note</span></span></strong><br/><p><span data-ttu-id="d45c2-209">如果你要从 MBAM 2.0 或 MBAM 2.0 SP1 升级，并且需要安装 .NET Framework 4.5，请参阅 <a href="release-notes-for-mbam-25.md" data-raw-source="[Release Notes for MBAM 2.5](release-notes-for-mbam-25.md)"> MBAM 2.5 的发行说明， </a> 以使网站工作。</span><span class="sxs-lookup"><span data-stu-id="d45c2-209">If you are upgrading from MBAM 2.0 or MBAM 2.0 SP1 and need to install .NET Framework 4.5, see <a href="release-notes-for-mbam-25.md" data-raw-source="[Release Notes for MBAM 2.5](release-notes-for-mbam-25.md)">Release Notes for MBAM 2.5</a> for an additional required step to make the websites work.</span></span></p>
</div>
<div>

</div></li>
</ul></li>
<li><p><strong><span data-ttu-id="d45c2-210">WCF 激活</span><span class="sxs-lookup"><span data-stu-id="d45c2-210">WCF Activation</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="d45c2-211">HTTP 激活</span><span class="sxs-lookup"><span data-stu-id="d45c2-211">HTTP Activation</span></span></p></li>
<li><p><span data-ttu-id="d45c2-212">非 HTTP 激活（仅适用于 Windows Server 2008、2012和 2012 R2）</span><span class="sxs-lookup"><span data-stu-id="d45c2-212">Non-HTTP Activation (Only for Windows Server 2008, 2012, and 2012 R2)</span></span></p>
<p></p></li>
</ul></li>
<li><p><strong><span data-ttu-id="d45c2-213">TCP 激活</span><span class="sxs-lookup"><span data-stu-id="d45c2-213">TCP Activation</span></span></strong></p></li>
</ul>
<p><strong><span data-ttu-id="d45c2-214">Windows 进程激活服务：</span><span class="sxs-lookup"><span data-stu-id="d45c2-214">Windows Process Activation Service:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="d45c2-215">流程模型</span><span class="sxs-lookup"><span data-stu-id="d45c2-215">Process Model</span></span></p></li>
<li><p><span data-ttu-id="d45c2-216">.NET Framework 环境</span><span class="sxs-lookup"><span data-stu-id="d45c2-216">.NET Framework Environment</span></span></p></li>
<li><p><span data-ttu-id="d45c2-217">配置 Api</span><span class="sxs-lookup"><span data-stu-id="d45c2-217">Configuration APIs</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d45c2-218">ASP.NET MVC 4。0</span><span class="sxs-lookup"><span data-stu-id="d45c2-218">ASP.NET MVC 4.0</span></span></p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=392271" data-raw-source="[ASP.NET MVC 4 download](https://go.microsoft.com/fwlink/?LinkId=392271)"><span data-ttu-id="d45c2-219">ASP.NET MVC 4 下载</span><span class="sxs-lookup"><span data-stu-id="d45c2-219">ASP.NET MVC 4 download</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d45c2-220">服务主体名称（SPN）</span><span class="sxs-lookup"><span data-stu-id="d45c2-220">Service Principal Name (SPN)</span></span></p></td>
<td align="left"><p><span data-ttu-id="d45c2-221">Web 应用程序要求在用于 web 应用程序池的域帐户下的虚拟主机名称中使用 SPN。</span><span class="sxs-lookup"><span data-stu-id="d45c2-221">The web applications require an SPN for the virtual host name under the domain account that you use for the web application pools.</span></span></p>
<p><span data-ttu-id="d45c2-222">如果你的管理权限允许你在 Active Directory 域服务中创建 Spn，MBAM 会为你创建 SPN。</span><span class="sxs-lookup"><span data-stu-id="d45c2-222">If your administrative rights permit you to create SPNs in Active Directory Domain Services, MBAM creates the SPN for you.</span></span> <span data-ttu-id="d45c2-223"><a href="https://technet.microsoft.com/library/cc731241.aspx" data-raw-source="[Setspn](https://technet.microsoft.com/library/cc731241.aspx)"> </a> 有关创建 spn 所需的权限的信息，请参阅 Setspn。</span><span class="sxs-lookup"><span data-stu-id="d45c2-223">See <a href="https://technet.microsoft.com/library/cc731241.aspx" data-raw-source="[Setspn](https://technet.microsoft.com/library/cc731241.aspx)">Setspn</a> for information about the rights required to create SPNs.</span></span></p>
<p><span data-ttu-id="d45c2-224">如果你没有创建 Spn 的管理员权限，则必须使用以下命令让你的组织中的 Active Directory 管理员为你创建 SPN。</span><span class="sxs-lookup"><span data-stu-id="d45c2-224">If you do not have administrative rights to create SPNs, you must ask the Active Directory administrators in your organization to create the SPN for you by using the following command.</span></span></p>
<pre class="syntax" space="preserve"><code>Setspn -s http/mbamvirtual contoso\mbamapppooluser
Setspn -s http/mbamvirtual.contoso.com contoso\mbamapppooluser</code></pre>
<p><span data-ttu-id="d45c2-225">在该代码示例中，虚拟主机名为 mbamvirtual.contoso.com，用于 web 应用程序池的域帐户为 contoso\mbamapppooluser。</span><span class="sxs-lookup"><span data-stu-id="d45c2-225">In the code example, the virtual host name is mbamvirtual.contoso.com, and the domain account used for the web application pools is contoso\mbamapppooluser.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="d45c2-226">注意</span><span class="sxs-lookup"><span data-stu-id="d45c2-226">Note</span></span></strong><br/><p><span data-ttu-id="d45c2-227">如果要设置负载平衡，请在所有服务器上使用相同的应用程序池帐户。</span><span class="sxs-lookup"><span data-stu-id="d45c2-227">If you are setting up Load Balancing, use the same application pool account on all servers.</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="d45c2-228">有关为完全限定的、NetBIOS 和自定义主机名注册 Spn 的详细信息，请参阅 <a href="planning-how-to-secure-the-mbam-websites.md" data-raw-source="[Planning How to Secure the MBAM Websites](planning-how-to-secure-the-mbam-websites.md)"> 规划如何保护 MBAM 网站的安全 </a> 。</span><span class="sxs-lookup"><span data-stu-id="d45c2-228">For more information about registering SPNs for fully qualified, NetBIOS, and custom host names, see <a href="planning-how-to-secure-the-mbam-websites.md" data-raw-source="[Planning How to Secure the MBAM Websites](planning-how-to-secure-the-mbam-websites.md)">Planning How to Secure the MBAM Websites</a>.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="d45c2-229">自助服务门户的先决条件</span><span class="sxs-lookup"><span data-stu-id="d45c2-229">Prerequisites for the Self-Service Portal</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d45c2-230">必备</span><span class="sxs-lookup"><span data-stu-id="d45c2-230">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="d45c2-231">详细信息</span><span class="sxs-lookup"><span data-stu-id="d45c2-231">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d45c2-232">Windows Server 支持的版本</span><span class="sxs-lookup"><span data-stu-id="d45c2-232">Supported version of Windows Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="d45c2-233"><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"> </a> 有关支持的版本，请参阅 MBAM 2.5 支持的配置。</span><span class="sxs-lookup"><span data-stu-id="d45c2-233">See <a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)">MBAM 2.5 Supported Configurations</a> for supported versions.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d45c2-234">ASP.NET MVC 4。0</span><span class="sxs-lookup"><span data-stu-id="d45c2-234">ASP.NET MVC 4.0</span></span></p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=392271" data-raw-source="[ASP.NET MVC 4 download](https://go.microsoft.com/fwlink/?LinkId=392271)"><span data-ttu-id="d45c2-235">ASP.NET MVC 4 下载</span><span class="sxs-lookup"><span data-stu-id="d45c2-235">ASP.NET MVC 4 download</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d45c2-236">Web 服务 IIS 管理工具</span><span class="sxs-lookup"><span data-stu-id="d45c2-236">Web Service IIS Management Tools</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d45c2-237">服务主体名称（SPN）</span><span class="sxs-lookup"><span data-stu-id="d45c2-237">Service Principal Name (SPN)</span></span></p></td>
<td align="left"><p><span data-ttu-id="d45c2-238">Web 应用程序要求在用于 web 应用程序池的域帐户下的虚拟主机名称中使用 SPN。</span><span class="sxs-lookup"><span data-stu-id="d45c2-238">The web applications require an SPN for the virtual host name under the domain account that you use for the web application pools.</span></span></p>
<p><span data-ttu-id="d45c2-239">如果你的管理权限允许你在 Active Directory 域服务中创建 Spn，MBAM 会为你创建 SPN。</span><span class="sxs-lookup"><span data-stu-id="d45c2-239">If your administrative rights permit you to create SPNs in Active Directory Domain Services, MBAM creates the SPN for you.</span></span> <span data-ttu-id="d45c2-240"><a href="https://technet.microsoft.com/library/cc731241.aspx" data-raw-source="[Setspn](https://technet.microsoft.com/library/cc731241.aspx)"> </a> 有关创建 spn 所需的权限的信息，请参阅 Setspn。</span><span class="sxs-lookup"><span data-stu-id="d45c2-240">See <a href="https://technet.microsoft.com/library/cc731241.aspx" data-raw-source="[Setspn](https://technet.microsoft.com/library/cc731241.aspx)">Setspn</a> for information about the rights required to create SPNs.</span></span></p>
<p><span data-ttu-id="d45c2-241">如果您没有创建 Spn 的管理员权限，则必须让组织中的 Active Directory 管理员使用以下命令为您创建 SPN。</span><span class="sxs-lookup"><span data-stu-id="d45c2-241">If you do not have administrative rights to create SPNs, you must ask the Active Directory administrators in your organization administrators in your organization to create the SPN for you by using the following command.</span></span></p>
<pre class="syntax" space="preserve"><code>Setspn -s http/mbamvirtual contoso\mbamapppooluser
Setspn -s http/mbamvirtual.contoso.com contoso\mbamapppooluser</code></pre>
<p><span data-ttu-id="d45c2-242">在该代码示例中，虚拟主机名为 mbamvirtual.contoso.com，用于 web 应用程序池的域帐户为 contoso\mbamapppooluser。</span><span class="sxs-lookup"><span data-stu-id="d45c2-242">In the code example, the virtual host name is mbamvirtual.contoso.com, and the domain account used for the web application pools is contoso\mbamapppooluser.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="d45c2-243">注意</span><span class="sxs-lookup"><span data-stu-id="d45c2-243">Note</span></span></strong><br/><p><span data-ttu-id="d45c2-244">如果要设置负载平衡，请在所有服务器上使用相同的应用程序池帐户。</span><span class="sxs-lookup"><span data-stu-id="d45c2-244">If you are setting up Load Balancing, use the same application pool account on all servers.</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="d45c2-245">有关为完全限定的、NetBIOS 和自定义主机名注册 Spn 的详细信息，请参阅 <a href="planning-how-to-secure-the-mbam-websites.md" data-raw-source="[Planning How to Secure the MBAM Websites](planning-how-to-secure-the-mbam-websites.md)"> 规划如何保护 MBAM 网站的安全 </a> 。</span><span class="sxs-lookup"><span data-stu-id="d45c2-245">For more information about registering SPNs for fully qualified, NetBIOS, and custom host names, see <a href="planning-how-to-secure-the-mbam-websites.md" data-raw-source="[Planning How to Secure the MBAM Websites](planning-how-to-secure-the-mbam-websites.md)">Planning How to Secure the MBAM Websites</a>.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="d45c2-246">管理工作站的先决条件</span><span class="sxs-lookup"><span data-stu-id="d45c2-246">Prerequisites for the Management Workstation</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d45c2-247">必备</span><span class="sxs-lookup"><span data-stu-id="d45c2-247">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="d45c2-248">详细信息</span><span class="sxs-lookup"><span data-stu-id="d45c2-248">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d45c2-249">在安装 MBAM 客户端之前，请从 <a href="https://go.microsoft.com/fwlink/p/?LinkId=393941" data-raw-source="[How to Get MDOP Group Policy (.admx) Templates](https://go.microsoft.com/fwlink/p/?LinkId=393941)"> 如何获取 MDOP 组策略（admx）模板中下载 MBAM 组策略模板 </a> ，并使用你希望在你的企业中实现的用于 BitLocker 驱动器加密的设置配置这些模板。</span><span class="sxs-lookup"><span data-stu-id="d45c2-249">Before installing the MBAM Client, download the MBAM Group Policy Templates from <a href="https://go.microsoft.com/fwlink/p/?LinkId=393941" data-raw-source="[How to Get MDOP Group Policy (.admx) Templates](https://go.microsoft.com/fwlink/p/?LinkId=393941)">How to Get MDOP Group Policy (.admx) Templates</a> and configure them with the settings that you want to implement in your enterprise for BitLocker Drive Encryption.</span></span></p></td>
<td align="left"><p><span data-ttu-id="d45c2-250">在安装 MBAM 客户端之前，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d45c2-250">Before installing the MBAM Client, do the following:</span></span></p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d45c2-251">要执行的操作</span><span class="sxs-lookup"><span data-stu-id="d45c2-251">What to do</span></span></th>
<th align="left"><span data-ttu-id="d45c2-252">获取说明的位置</span><span class="sxs-lookup"><span data-stu-id="d45c2-252">Where to get instructions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d45c2-253">复制 MBAM 组策略模板</span><span class="sxs-lookup"><span data-stu-id="d45c2-253">Copy the MBAM Group Policy Templates</span></span></p></td>
<td align="left"><p><a href="copying-the-mbam-25-group-policy-templates.md" data-raw-source="[Copying the MBAM 2.5 Group Policy Templates](copying-the-mbam-25-group-policy-templates.md)"><span data-ttu-id="d45c2-254">复制 MBAM 2.5 组策略模板</span><span class="sxs-lookup"><span data-stu-id="d45c2-254">Copying the MBAM 2.5 Group Policy Templates</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d45c2-255">编辑组策略设置</span><span class="sxs-lookup"><span data-stu-id="d45c2-255">Edit the Group Policy settings</span></span></p></td>
<td align="left"><p><a href="editing-the-mbam-25-group-policy-settings.md" data-raw-source="[Editing the MBAM 2.5 Group Policy Settings](editing-the-mbam-25-group-policy-settings.md)"><span data-ttu-id="d45c2-256">编辑 MBAM 2.5 组策略设置</span><span class="sxs-lookup"><span data-stu-id="d45c2-256">Editing the MBAM 2.5 Group Policy Settings</span></span></a></p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>





## <span data-ttu-id="d45c2-257">相关主题</span><span class="sxs-lookup"><span data-stu-id="d45c2-257">Related topics</span></span>


[<span data-ttu-id="d45c2-258">为 MBAM 2.5 准备你的环境</span><span class="sxs-lookup"><span data-stu-id="d45c2-258">Preparing your Environment for MBAM 2.5</span></span>](preparing-your-environment-for-mbam-25.md)

[<span data-ttu-id="d45c2-259">规划部署 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="d45c2-259">Planning to Deploy MBAM 2.5</span></span>](planning-to-deploy-mbam-25.md)

[<span data-ttu-id="d45c2-260">MBAM 2.5 支持的配置</span><span class="sxs-lookup"><span data-stu-id="d45c2-260">MBAM 2.5 Supported Configurations</span></span>](mbam-25-supported-configurations.md)




## <span data-ttu-id="d45c2-261">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="d45c2-261">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="d45c2-262">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="d45c2-262">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span>
- <span data-ttu-id="d45c2-263">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="d45c2-263">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>




