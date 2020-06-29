---
title: MBAM 2.0 部署先决条件
description: MBAM 2.0 部署先决条件
author: dansimp
ms.assetid: 57d1c2bb-5ea3-457e-badd-dd9206ff0f20
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ef7ee64a3661009f18e0963d738c57a59885cb20
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803883"
---
# <span data-ttu-id="b24c3-103">MBAM 2.0 部署先决条件</span><span class="sxs-lookup"><span data-stu-id="b24c3-103">MBAM 2.0 Deployment Prerequisites</span></span>


<span data-ttu-id="b24c3-104">在开始 Microsoft BitLocker 管理和监视（MBAM）安装之前，应确保已满足安装该产品的先决条件。</span><span class="sxs-lookup"><span data-stu-id="b24c3-104">Before you start Microsoft BitLocker Administration and Monitoring (MBAM) Setup, you should ensure that you have met the prerequisites to install the product.</span></span> <span data-ttu-id="b24c3-105">本部分包含的信息可帮助你在部署 Microsoft BitLocker 管理和监视服务器功能和客户端之前成功地计划你的计算环境。</span><span class="sxs-lookup"><span data-stu-id="b24c3-105">This section contains information to help you successfully plan your computing environment before you deploy Microsoft BitLocker Administration and Monitoring Server features and Clients.</span></span> <span data-ttu-id="b24c3-106">如果你正在通过 Configuration Manager 安装 MBAM，请参阅[计划通过 Configuration manager](planning-to-deploy-mbam-with-configuration-manager-2.md)为其他先决条件部署 MBAM。</span><span class="sxs-lookup"><span data-stu-id="b24c3-106">If you are installing MBAM with Configuration Manager, see [Planning to Deploy MBAM with Configuration Manager](planning-to-deploy-mbam-with-configuration-manager-2.md) for additional prerequisites.</span></span>

## <span data-ttu-id="b24c3-107">MBAM 服务器功能的安装先决条件</span><span class="sxs-lookup"><span data-stu-id="b24c3-107">Installation Prerequisites for MBAM Server Features</span></span>


<span data-ttu-id="b24c3-108">每个 MBAM 服务器功能都具有特定的先决条件，必须先满足这些先决条件，然后才能成功安装 MBAM 功能。</span><span class="sxs-lookup"><span data-stu-id="b24c3-108">Each of the MBAM Server features has specific prerequisites that must be met before the MBAM features can be successfully installed.</span></span> <span data-ttu-id="b24c3-109">MBAM 安装程序检查在安装开始之前是否满足所有先决条件。</span><span class="sxs-lookup"><span data-stu-id="b24c3-109">MBAM Setup checks that all prerequisites are met before the installation starts.</span></span>

### <span data-ttu-id="b24c3-110">管理和监视服务器的先决条件</span><span class="sxs-lookup"><span data-stu-id="b24c3-110">Prerequisites for Administration and Monitoring Server</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b24c3-111">必备</span><span class="sxs-lookup"><span data-stu-id="b24c3-111">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="b24c3-112">详细信息</span><span class="sxs-lookup"><span data-stu-id="b24c3-112">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="b24c3-113">Windows Server Web 服务器角色</span><span class="sxs-lookup"><span data-stu-id="b24c3-113">Windows Server Web Server Role</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="b24c3-114">此角色必须添加到 "管理和监视服务器" 功能支持的服务器操作系统。</span><span class="sxs-lookup"><span data-stu-id="b24c3-114">This role must be added to a server operating system that is supported for the Administration and Monitoring Server feature.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="b24c3-115">Web 服务器（IIS）管理工具</span><span class="sxs-lookup"><span data-stu-id="b24c3-115">Web Server (IIS) Management Tools</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="b24c3-116">选择 " <strong> IIS 管理脚本和工具" </strong> 。</span><span class="sxs-lookup"><span data-stu-id="b24c3-116">Select <strong>IIS Management Scripts and Tools</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="b24c3-117">SSL 证书</span><span class="sxs-lookup"><span data-stu-id="b24c3-117">SSL Certificate</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="b24c3-118">可选。</span><span class="sxs-lookup"><span data-stu-id="b24c3-118">Optional.</span></span> <span data-ttu-id="b24c3-119">若要保护客户端与 web 服务之间的通信，你必须获取并安装受信任的安全机构签名的证书。</span><span class="sxs-lookup"><span data-stu-id="b24c3-119">To secure communication between the clients and the web services, you have to obtain and install a certificate that a trusted security authority signed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="b24c3-120">Web 服务器角色服务</span><span class="sxs-lookup"><span data-stu-id="b24c3-120">Web Server Role Services</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="b24c3-121">常见的 HTTP 功能：</span><span class="sxs-lookup"><span data-stu-id="b24c3-121">Common HTTP Features:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="b24c3-122">静态内容</span><span class="sxs-lookup"><span data-stu-id="b24c3-122">Static Content</span></span></p></li>
<li><p><span data-ttu-id="b24c3-123">默认文档</span><span class="sxs-lookup"><span data-stu-id="b24c3-123">Default Document</span></span></p></li>
</ul>
<p><strong><span data-ttu-id="b24c3-124">应用程序开发：</span><span class="sxs-lookup"><span data-stu-id="b24c3-124">Application Development:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="b24c3-125">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b24c3-125">ASP.NET</span></span></p></li>
<li><p><span data-ttu-id="b24c3-126">.NET 扩展性</span><span class="sxs-lookup"><span data-stu-id="b24c3-126">.NET Extensibility</span></span></p></li>
<li><p><span data-ttu-id="b24c3-127">ISAPI 扩展</span><span class="sxs-lookup"><span data-stu-id="b24c3-127">ISAPI Extensions</span></span></p></li>
<li><p><span data-ttu-id="b24c3-128">ISAPI 筛选器</span><span class="sxs-lookup"><span data-stu-id="b24c3-128">ISAPI Filters</span></span></p></li>
</ul>
<p><strong><span data-ttu-id="b24c3-129">安全</span><span class="sxs-lookup"><span data-stu-id="b24c3-129">Security:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="b24c3-130">Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="b24c3-130">Windows Authentication</span></span></p></li>
<li><p><span data-ttu-id="b24c3-131">请求筛选</span><span class="sxs-lookup"><span data-stu-id="b24c3-131">Request Filtering</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="b24c3-132">Windows Server 功能</span><span class="sxs-lookup"><span data-stu-id="b24c3-132">Windows Server Features</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="b24c3-133">.NET Framework 3.5.1 功能：</span><span class="sxs-lookup"><span data-stu-id="b24c3-133">.NET Framework 3.5.1 features:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="b24c3-134">.NET Framework 3.5。1</span><span class="sxs-lookup"><span data-stu-id="b24c3-134">.NET Framework 3.5.1</span></span></p></li>
<li><p><span data-ttu-id="b24c3-135">WCF 激活</span><span class="sxs-lookup"><span data-stu-id="b24c3-135">WCF Activation</span></span></p>
<ul>
<li><p><span data-ttu-id="b24c3-136">HTTP 激活</span><span class="sxs-lookup"><span data-stu-id="b24c3-136">HTTP Activation</span></span></p></li>
<li><p><span data-ttu-id="b24c3-137">非 HTTP 激活</span><span class="sxs-lookup"><span data-stu-id="b24c3-137">Non-HTTP Activation</span></span></p></li>
</ul></li>
</ul>
<p><strong><span data-ttu-id="b24c3-138">Windows 进程激活服务：</span><span class="sxs-lookup"><span data-stu-id="b24c3-138">Windows Process Activation Service:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="b24c3-139">流程模型</span><span class="sxs-lookup"><span data-stu-id="b24c3-139">Process Model</span></span></p></li>
<li><p><span data-ttu-id="b24c3-140">.NET 环境</span><span class="sxs-lookup"><span data-stu-id="b24c3-140">.NET Environment</span></span></p></li>
<li><p><span data-ttu-id="b24c3-141">配置 Api</span><span class="sxs-lookup"><span data-stu-id="b24c3-141">Configuration APIs</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="b24c3-142">注意</span><span class="sxs-lookup"><span data-stu-id="b24c3-142">Note</span></span>**  
<span data-ttu-id="b24c3-143">有关受支持的操作系统的列表，请参阅[MBAM 2.0 支持的配置](mbam-20-supported-configurations-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="b24c3-143">For a list of supported operating systems, see [MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md).</span></span>



### <span data-ttu-id="b24c3-144">合规性和审核报告的先决条件</span><span class="sxs-lookup"><span data-stu-id="b24c3-144">Prerequisites for the Compliance and Audit Reports</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b24c3-145">必备</span><span class="sxs-lookup"><span data-stu-id="b24c3-145">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="b24c3-146">详细信息</span><span class="sxs-lookup"><span data-stu-id="b24c3-146">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b24c3-147">SQL Server 支持的版本</span><span class="sxs-lookup"><span data-stu-id="b24c3-147">Supported version of SQL Server</span></span></p>
<p><span data-ttu-id="b24c3-148"><a href="mbam-20-supported-configurations-mbam-2.md" data-raw-source="[MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md)"> </a> 有关支持的版本，请参阅 MBAM 2.0 支持的配置。</span><span class="sxs-lookup"><span data-stu-id="b24c3-148">See <a href="mbam-20-supported-configurations-mbam-2.md" data-raw-source="[MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md)">MBAM 2.0 Supported Configurations</a> for supported versions.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b24c3-149">通过以下方式安装 SQL Server：</span><span class="sxs-lookup"><span data-stu-id="b24c3-149">Install SQL Server with:</span></span></p>
<ul>
<li><p><span data-ttu-id="b24c3-150">SQL_Latin1_General_CP1_CI_AS 排序规则</span><span class="sxs-lookup"><span data-stu-id="b24c3-150">SQL_Latin1_General_CP1_CI_AS collation</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b24c3-151">SQL Server Reporting Services （SSRS）</span><span class="sxs-lookup"><span data-stu-id="b24c3-151">SQL Server Reporting Services (SSRS)</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b24c3-152">SSRS 实例权限–只有在从报表的单独服务器上安装数据库时才需要安装报表。</span><span class="sxs-lookup"><span data-stu-id="b24c3-152">SSRS instance rights – required for installing reports only if you are installing databases on a separate server from the reports.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b24c3-153">所需实例权限：</span><span class="sxs-lookup"><span data-stu-id="b24c3-153">Required instance rights:</span></span></p>
<ul>
<li><p><span data-ttu-id="b24c3-154">创建文件夹</span><span class="sxs-lookup"><span data-stu-id="b24c3-154">Create Folders</span></span></p></li>
<li><p><span data-ttu-id="b24c3-155">发布报表</span><span class="sxs-lookup"><span data-stu-id="b24c3-155">Publish Reports</span></span></p></li>
</ul>
<p><span data-ttu-id="b24c3-156">在 MBAM 服务器安装期间，必须安装并运行 SSRS。</span><span class="sxs-lookup"><span data-stu-id="b24c3-156">SSRS must be installed and running during the MBAM Server installation.</span></span> <span data-ttu-id="b24c3-157">在 "本机" 模式下配置 SSRS，而不是在未配置或 "SharePoint" 模式下配置。</span><span class="sxs-lookup"><span data-stu-id="b24c3-157">Configure SSRS in “native” mode and not in unconfigured or “SharePoint” mode.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="b24c3-158">恢复数据库的先决条件</span><span class="sxs-lookup"><span data-stu-id="b24c3-158">Prerequisites for the Recovery Database</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b24c3-159">必备</span><span class="sxs-lookup"><span data-stu-id="b24c3-159">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="b24c3-160">详细信息</span><span class="sxs-lookup"><span data-stu-id="b24c3-160">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b24c3-161">SQL Server 支持的版本</span><span class="sxs-lookup"><span data-stu-id="b24c3-161">Supported version of SQL Server</span></span></p>
<p><span data-ttu-id="b24c3-162"><a href="mbam-20-supported-configurations-mbam-2.md" data-raw-source="[MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md)"> </a> 有关支持的版本，请参阅 MBAM 2.0 支持的配置。</span><span class="sxs-lookup"><span data-stu-id="b24c3-162">See <a href="mbam-20-supported-configurations-mbam-2.md" data-raw-source="[MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md)">MBAM 2.0 Supported Configurations</a> for supported versions.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b24c3-163">通过以下方式安装 SQL Server：</span><span class="sxs-lookup"><span data-stu-id="b24c3-163">Install SQL Server with:</span></span></p>
<ul>
<li><p><span data-ttu-id="b24c3-164">SQL_Latin1_General_CP1_CI_AS 排序规则</span><span class="sxs-lookup"><span data-stu-id="b24c3-164">SQL_Latin1_General_CP1_CI_AS collation</span></span></p></li>
<li><p><span data-ttu-id="b24c3-165">SQL Server 管理工具</span><span class="sxs-lookup"><span data-stu-id="b24c3-165">SQL Server Management Tools</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b24c3-166">所需的 SQL Server 权限</span><span class="sxs-lookup"><span data-stu-id="b24c3-166">Required SQL Server permissions</span></span></p></td>
<td align="left"><p><span data-ttu-id="b24c3-167">所需权限：</span><span class="sxs-lookup"><span data-stu-id="b24c3-167">Required permissions:</span></span></p>
<ul>
<li><p><span data-ttu-id="b24c3-168">SQL 实例登录服务器角色：</span><span class="sxs-lookup"><span data-stu-id="b24c3-168">SQL instance Login Server roles:</span></span></p>
<ul>
<li><p><span data-ttu-id="b24c3-169">dbcreator</span><span class="sxs-lookup"><span data-stu-id="b24c3-169">dbcreator</span></span></p></li>
<li><p><span data-ttu-id="b24c3-170">processadmin</span><span class="sxs-lookup"><span data-stu-id="b24c3-170">processadmin</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="b24c3-171">SQL Server Reporting Services 实例权限：</span><span class="sxs-lookup"><span data-stu-id="b24c3-171">SQL Server Reporting Services instance rights:</span></span></p>
<ul>
<li><p><span data-ttu-id="b24c3-172">创建文件夹</span><span class="sxs-lookup"><span data-stu-id="b24c3-172">Create Folders</span></span></p></li>
<li><p><span data-ttu-id="b24c3-173">发布报表</span><span class="sxs-lookup"><span data-stu-id="b24c3-173">Publish Reports</span></span></p></li>
</ul></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b24c3-174">SQL Server 中可用的可选安装透明数据加密（TDE）功能</span><span class="sxs-lookup"><span data-stu-id="b24c3-174">Optional - Install Transparent Data Encryption (TDE) feature available in SQL Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="b24c3-175">TDE SQL Server 功能对数据和日志文件执行实时 i/o 加密和解密，这有助于你遵守各种行业中建立的许多法律、法规和指南。</span><span class="sxs-lookup"><span data-stu-id="b24c3-175">The TDE SQL Server feature performs real-time I/O encryption and decryption of the data and log files, which can help you to comply with many laws, regulations, and guidelines established in various industries.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="b24c3-176">注意</span><span class="sxs-lookup"><span data-stu-id="b24c3-176">Note</span></span></strong><br/><p><span data-ttu-id="b24c3-177">TDE 执行数据库信息的实时解密，这意味着如果你在其下登录的帐户在 SQL Server 表中查看恢复密钥信息时有权访问数据库，则恢复密钥信息可见。</span><span class="sxs-lookup"><span data-stu-id="b24c3-177">TDE performs real-time decryption of database information, which means that, if the account under which you are logged on has permissions to the database while you are viewing the recovery key information in the SQL Server tables, the recovery key information is visible.</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="b24c3-178">有关 TDE 的更多信息： <a href="mbam-20-security-considerations-mbam-2.md" data-raw-source="[MBAM 2.0 Security Considerations](mbam-20-security-considerations-mbam-2.md)"> MBAM 2.0 安全注意事项 </a> 。</span><span class="sxs-lookup"><span data-stu-id="b24c3-178">More about TDE: <a href="mbam-20-security-considerations-mbam-2.md" data-raw-source="[MBAM 2.0 Security Considerations](mbam-20-security-considerations-mbam-2.md)">MBAM 2.0 Security Considerations</a>.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="b24c3-179">合规性和审核数据库的先决条件</span><span class="sxs-lookup"><span data-stu-id="b24c3-179">Prerequisites for the Compliance and Audit Database</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b24c3-180">必备</span><span class="sxs-lookup"><span data-stu-id="b24c3-180">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="b24c3-181">详细信息</span><span class="sxs-lookup"><span data-stu-id="b24c3-181">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b24c3-182">SQL Server 支持的版本</span><span class="sxs-lookup"><span data-stu-id="b24c3-182">Supported version of SQL Server</span></span></p>
<p><span data-ttu-id="b24c3-183"><a href="mbam-20-supported-configurations-mbam-2.md" data-raw-source="[MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md)"> </a> 有关支持的版本，请参阅 MBAM 2.0 支持的配置。</span><span class="sxs-lookup"><span data-stu-id="b24c3-183">See <a href="mbam-20-supported-configurations-mbam-2.md" data-raw-source="[MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md)">MBAM 2.0 Supported Configurations</a> for supported versions.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b24c3-184">通过以下方式安装 SQL Server：</span><span class="sxs-lookup"><span data-stu-id="b24c3-184">Install SQL Server with:</span></span></p>
<ul>
<li><p><span data-ttu-id="b24c3-185">SQL_Latin1_General_CP1_CI_AS 排序规则</span><span class="sxs-lookup"><span data-stu-id="b24c3-185">SQL_Latin1_General_CP1_CI_AS collation</span></span></p></li>
<li><p><span data-ttu-id="b24c3-186">SQL Server 管理工具</span><span class="sxs-lookup"><span data-stu-id="b24c3-186">SQL Server Management Tools</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b24c3-187">所需的 SQL Server 权限</span><span class="sxs-lookup"><span data-stu-id="b24c3-187">Required SQL Server permissions</span></span></p></td>
<td align="left"><p><span data-ttu-id="b24c3-188">所需权限：</span><span class="sxs-lookup"><span data-stu-id="b24c3-188">Required permissions:</span></span></p>
<ul>
<li><p><span data-ttu-id="b24c3-189">SQL 实例登录服务器角色：</span><span class="sxs-lookup"><span data-stu-id="b24c3-189">SQL instance Login Server roles:</span></span></p>
<ul>
<li><p><span data-ttu-id="b24c3-190">dbcreator</span><span class="sxs-lookup"><span data-stu-id="b24c3-190">dbcreator</span></span></p></li>
<li><p><span data-ttu-id="b24c3-191">processadmin</span><span class="sxs-lookup"><span data-stu-id="b24c3-191">processadmin</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="b24c3-192">SQL Server Reporting Services 实例权限：</span><span class="sxs-lookup"><span data-stu-id="b24c3-192">SQL Server Reporting Services instance rights:</span></span></p>
<ul>
<li><p><span data-ttu-id="b24c3-193">创建文件夹</span><span class="sxs-lookup"><span data-stu-id="b24c3-193">Create Folders</span></span></p></li>
<li><p><span data-ttu-id="b24c3-194">发布报表</span><span class="sxs-lookup"><span data-stu-id="b24c3-194">Publish Reports</span></span></p></li>
</ul></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b24c3-195">SQL Server 中的可选 "安装透明数据加密（TDE）" 功能。</span><span class="sxs-lookup"><span data-stu-id="b24c3-195">Optional - Install Transparent Data Encryption (TDE) feature in SQL Server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b24c3-196">TDE SQL Server 功能对数据和日志文件执行实时 i/o 加密和解密，这有助于你遵守各种行业中建立的许多法律、法规和指南。</span><span class="sxs-lookup"><span data-stu-id="b24c3-196">The TDE SQL Server feature performs real-time I/O encryption and decryption of the data and log files, which can help you to comply with many laws, regulations, and guidelines established in various industries.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="b24c3-197">注意</span><span class="sxs-lookup"><span data-stu-id="b24c3-197">Note</span></span></strong><br/><p><span data-ttu-id="b24c3-198">TDE 执行数据库信息的实时解密，这意味着如果你在其下登录的帐户在 SQL Server 表中查看恢复密钥信息时有权访问数据库，则恢复密钥信息可见。</span><span class="sxs-lookup"><span data-stu-id="b24c3-198">TDE performs real-time decryption of database information, which means that, if the account under which you are logged on has permissions to the database while you are viewing the recovery key information in the SQL Server tables, the recovery key information is visible.</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="b24c3-199">有关 TDE 的更多信息： <a href="mbam-20-security-considerations-mbam-2.md" data-raw-source="[MBAM 2.0 Security Considerations](mbam-20-security-considerations-mbam-2.md)"> MBAM 2.0 安全注意事项</span><span class="sxs-lookup"><span data-stu-id="b24c3-199">More about TDE: <a href="mbam-20-security-considerations-mbam-2.md" data-raw-source="[MBAM 2.0 Security Considerations](mbam-20-security-considerations-mbam-2.md)">MBAM 2.0 Security Considerations</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b24c3-200">在 MBAM 服务器安装期间，SQL Server 必须安装并运行数据库引擎服务。</span><span class="sxs-lookup"><span data-stu-id="b24c3-200">SQL Server must have Database Engine Services installed and running during MBAM Server installation.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b24c3-201">SQL Server 代理服务必须在所选 SQL Server 实例上运行并设置为 "自动启动"。</span><span class="sxs-lookup"><span data-stu-id="b24c3-201">The SQL Server Agent service must be running and set to auto-start on the selected instances of SQL Server.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="b24c3-202">自助服务门户的先决条件</span><span class="sxs-lookup"><span data-stu-id="b24c3-202">Prerequisites for the Self-Service Portal</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b24c3-203">必备</span><span class="sxs-lookup"><span data-stu-id="b24c3-203">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="b24c3-204">详细信息</span><span class="sxs-lookup"><span data-stu-id="b24c3-204">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b24c3-205">Windows Server 支持的版本</span><span class="sxs-lookup"><span data-stu-id="b24c3-205">Supported version of Windows Server</span></span></p>
<p><span data-ttu-id="b24c3-206"><a href="mbam-20-supported-configurations-mbam-2.md" data-raw-source="[MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md)"> </a> 有关支持的版本，请参阅 MBAM 2.0 支持的配置。</span><span class="sxs-lookup"><span data-stu-id="b24c3-206">See <a href="mbam-20-supported-configurations-mbam-2.md" data-raw-source="[MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md)">MBAM 2.0 Supported Configurations</a> for supported versions.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b24c3-207">ASP.NET MVC 2。0</span><span class="sxs-lookup"><span data-stu-id="b24c3-207">ASP.NET MVC 2.0</span></span></p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=392270" data-raw-source="[ASP.NET MVC 2 download](https://go.microsoft.com/fwlink/?LinkId=392270)"><span data-ttu-id="b24c3-208">ASP.NET MVC 2 下载</span><span class="sxs-lookup"><span data-stu-id="b24c3-208">ASP.NET MVC 2 download</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b24c3-209">Web 服务 IIS 管理工具</span><span class="sxs-lookup"><span data-stu-id="b24c3-209">Web Service IIS Management Tools</span></span></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="b24c3-210">MBAM 客户端的先决条件</span><span class="sxs-lookup"><span data-stu-id="b24c3-210">Prerequisites for MBAM Clients</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b24c3-211">必备</span><span class="sxs-lookup"><span data-stu-id="b24c3-211">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="b24c3-212">详细信息</span><span class="sxs-lookup"><span data-stu-id="b24c3-212">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="b24c3-213">Windows 7 客户端仅 </strong> - 必须具有受信任的平台模块（TPM）功能。</span><span class="sxs-lookup"><span data-stu-id="b24c3-213">Windows 7 clients only</strong> - must have Trusted Platform Module (TPM) capability.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b24c3-214">TPM 版本必须为1.2 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="b24c3-214">TPM version must be 1.2 or later.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b24c3-215">必须在 BIOS 中打开 TPM 芯片，并将其从操作系统中 resettable。</span><span class="sxs-lookup"><span data-stu-id="b24c3-215">The TPM chip must be turned on in the BIOS and be resettable from the operating system.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b24c3-216">有关详细信息，请参阅 BIOS 文档。</span><span class="sxs-lookup"><span data-stu-id="b24c3-216">For more information, see the BIOS documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="b24c3-217">仅限 Windows 8 客户端 </strong> ：要让 MBAM 存储和管理 TPM 恢复密钥：必须关闭 tpm 自动预配，并且必须在部署 MBAM 之前将 MBAM 设置为 TPM 的所有者。</span><span class="sxs-lookup"><span data-stu-id="b24c3-217">Windows 8 clients only</strong>: To have MBAM store and manage the TPM recovery keys: TPM auto-provisioning must be turned off, and MBAM must be set as the owner of the TPM before you deploy MBAM.</span></span> <span data-ttu-id="b24c3-218">要关闭 TPM 自动预配，请参阅 <a href="https://go.microsoft.com/fwlink/?LinkId=286468" data-raw-source="[Disable-TpmAutoProvisioning](https://go.microsoft.com/fwlink/?LinkId=286468)"> 禁用-TpmAutoProvisioning </a> 。</span><span class="sxs-lookup"><span data-stu-id="b24c3-218">To turn off TPM auto-provisioning, see <a href="https://go.microsoft.com/fwlink/?LinkId=286468" data-raw-source="[Disable-TpmAutoProvisioning](https://go.microsoft.com/fwlink/?LinkId=286468)">Disable-TpmAutoProvisioning</a>.</span></span></p>
<ul>
<li><p><span data-ttu-id="b24c3-219">TPM 自动预配必须处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="b24c3-219">TPM auto-provisioning must be turned off.</span></span></p></li>
<li><p><span data-ttu-id="b24c3-220">在部署 MBAM 之前，必须将 MBAM 设置为 TPM 的所有者。</span><span class="sxs-lookup"><span data-stu-id="b24c3-220">MBAM must be set as the owner of the TPM before you deploy MBAM.</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="b24c3-221">要关闭 TPM 自动预配，请参阅 <a href="https://go.microsoft.com/fwlink/?LinkId=286468" data-raw-source="[Disable-TpmAutoProvisioning](https://go.microsoft.com/fwlink/?LinkId=286468)"> 禁用-TpmAutoProvisioning </a> 。</span><span class="sxs-lookup"><span data-stu-id="b24c3-221">To turn off TPM auto-provisioning, see <a href="https://go.microsoft.com/fwlink/?LinkId=286468" data-raw-source="[Disable-TpmAutoProvisioning](https://go.microsoft.com/fwlink/?LinkId=286468)">Disable-TpmAutoProvisioning</a>.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="b24c3-222">注意</span><span class="sxs-lookup"><span data-stu-id="b24c3-222">Note</span></span></strong><br/><p><span data-ttu-id="b24c3-223">确保键盘、视频或鼠标直接连接，而不是通过键盘、视频或鼠标（KVM）切换器管理。</span><span class="sxs-lookup"><span data-stu-id="b24c3-223">Ensure that the keyboard, video, or mouse are directly connected and not managed through a keyboard, video, or mouse (KVM) switch.</span></span> <span data-ttu-id="b24c3-224">KVM 切换器可能会干扰计算机检测硬件实际存在的能力。</span><span class="sxs-lookup"><span data-stu-id="b24c3-224">A KVM switch can interfere with the ability of the computer to detect the physical presence of hardware.</span></span></p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="b24c3-225">相关主题</span><span class="sxs-lookup"><span data-stu-id="b24c3-225">Related topics</span></span>


[<span data-ttu-id="b24c3-226">计划部署 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="b24c3-226">Planning to Deploy MBAM 2.0</span></span>](planning-to-deploy-mbam-20-mbam-2.md)

[<span data-ttu-id="b24c3-227">MBAM 2.0 支持的配置</span><span class="sxs-lookup"><span data-stu-id="b24c3-227">MBAM 2.0 Supported Configurations</span></span>](mbam-20-supported-configurations-mbam-2.md)









