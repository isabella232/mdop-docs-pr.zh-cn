---
title: 在安装 App-V 5.x Server 前检查注册表项
description: 在安装 App-V 5.x Server 前检查注册表项
author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.openlocfilehash: 9fe5a1b37d0fb5208d138939bb2fc79c89171fb3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798613"
---
# <span data-ttu-id="e338c-103">在安装 App-V 5.x Server 前检查注册表项</span><span class="sxs-lookup"><span data-stu-id="e338c-103">Check Registry Keys before installing App-V 5.x Server</span></span>

<span data-ttu-id="e338c-104">如果你要从 App-v 5.0 SP1 修补程序包3或更高版本升级 app-v 服务器，请先完成本节中的步骤，然后再安装 app-v 5 a.x 服务器</span><span class="sxs-lookup"><span data-stu-id="e338c-104">If you are upgrading the App-V Server from App-V 5.0 SP1 Hotfix Package 3 or later, complete the steps in this section before installing the App-V 5.x Server</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="e338c-105">需要执行此步骤时</span><span class="sxs-lookup"><span data-stu-id="e338c-105">When this step is required</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e338c-106">从 App-v 5.0 SP1 升级到使用 .msp 文件安装的任何后续修补程序包。</span><span class="sxs-lookup"><span data-stu-id="e338c-106">You are upgrading from App-V 5.0 SP1 with any subsequent Hotfix Packages that you installed by using an .msp file.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="e338c-107">哪些组件需要执行此步骤</span><span class="sxs-lookup"><span data-stu-id="e338c-107">Which components require that you do this step</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e338c-108">仅限你要升级的 app-v Server 组件。</span><span class="sxs-lookup"><span data-stu-id="e338c-108">Only the App-V Server components that you are upgrading.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="e338c-109">需要执行此步骤时</span><span class="sxs-lookup"><span data-stu-id="e338c-109">When you need to do this step</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e338c-110">在将 app-v Server 升级到 App-v 5 之前。 x</span><span class="sxs-lookup"><span data-stu-id="e338c-110">Before you upgrade the App-V Server to App-V 5.x</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="e338c-111">需要执行的操作</span><span class="sxs-lookup"><span data-stu-id="e338c-111">What you need to do</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e338c-112">使用下表中的信息，使用 <code>HKLM\Software\Microsoft\AppV\Server</code> 您在原始服务器安装中提供的值更新下的每个注册表项值。</span><span class="sxs-lookup"><span data-stu-id="e338c-112">Using the information in the following tables, update each registry key value under <code>HKLM\Software\Microsoft\AppV\Server</code> with the value that you provided in your original server installation.</span></span> <span data-ttu-id="e338c-113">完成此步骤将还原在安装 app-v 5.0 SP1 修补程序包时可能已删除的注册表值。</span><span class="sxs-lookup"><span data-stu-id="e338c-113">Completing this step restores registry values that may have been removed when App-V 5.0 SP1 Hotfix Packages were installed.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="e338c-114">ManagementDatabase 键</span><span class="sxs-lookup"><span data-stu-id="e338c-114">ManagementDatabase key</span></span>**

<span data-ttu-id="e338c-115">如果要安装管理数据库，请在 "" 下设置这些注册表项 `HKLM\Software\Microsoft\AppV\Server\ManagementDatabase` 。</span><span class="sxs-lookup"><span data-stu-id="e338c-115">If you are installing the Management database, set these registry keys under `HKLM\Software\Microsoft\AppV\Server\ManagementDatabase`.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e338c-116">键名</span><span class="sxs-lookup"><span data-stu-id="e338c-116">Key name</span></span></th>
<th align="left"><span data-ttu-id="e338c-117">描述</span><span class="sxs-lookup"><span data-stu-id="e338c-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e338c-118">IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="e338c-118">IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</span></span></p></td>
<td align="left"><p><span data-ttu-id="e338c-119">描述访问非本地管理数据库是否需要公共访问帐户。</span><span class="sxs-lookup"><span data-stu-id="e338c-119">Describes whether a public access account is required to access non-local management databases.</span></span> <span data-ttu-id="e338c-120">如果需要，值设置为 "1"。</span><span class="sxs-lookup"><span data-stu-id="e338c-120">Value is set to “1” if it is required.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e338c-121">MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="e338c-121">MANAGEMENT_DB_NAME</span></span></p></td>
<td align="left"><p><span data-ttu-id="e338c-122">管理数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="e338c-122">Name of the Management database.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e338c-123">MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="e338c-123">MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="e338c-124">用于读取（公共）访问管理数据库的帐户。</span><span class="sxs-lookup"><span data-stu-id="e338c-124">Account used for read (public) access to the Management database.</span></span></p>
<p><span data-ttu-id="e338c-125">在 <code>IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> 设置为1时使用。</span><span class="sxs-lookup"><span data-stu-id="e338c-125">Used when <code>IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> is set to 1.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e338c-126">MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_SID</span><span class="sxs-lookup"><span data-stu-id="e338c-126">MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_SID</span></span></p></td>
<td align="left"><p><span data-ttu-id="e338c-127">用于读取（公共）访问管理数据库的帐户的安全标识符（SID）。</span><span class="sxs-lookup"><span data-stu-id="e338c-127">Secure identifier (SID) of the account used for read (public) access to the Management database.</span></span></p>
<p><span data-ttu-id="e338c-128">在 <code>IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> 设置为1时使用。</span><span class="sxs-lookup"><span data-stu-id="e338c-128">Used when <code>IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> is set to 1.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e338c-129">MANAGEMENT_DB_SQL_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="e338c-129">MANAGEMENT_DB_SQL_INSTANCE</span></span></p></td>
<td align="left"><p><span data-ttu-id="e338c-130">管理数据库的 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="e338c-130">SQL Server instance for the Management database.</span></span></p>
<p><span data-ttu-id="e338c-131">如果值为空，则使用默认数据库实例。</span><span class="sxs-lookup"><span data-stu-id="e338c-131">If the value is blank, the default database instance is used.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e338c-132">MANAGEMENT_DB_WRITE_ACCESS_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="e338c-132">MANAGEMENT_DB_WRITE_ACCESS_ACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="e338c-133">用于写入（管理员）访问管理数据库的帐户。</span><span class="sxs-lookup"><span data-stu-id="e338c-133">Account used for write (administrator) access to the Management database.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e338c-134">MANAGEMENT_DB_WRITE_ACCESS_ACCOUNT_SID</span><span class="sxs-lookup"><span data-stu-id="e338c-134">MANAGEMENT_DB_WRITE_ACCESS_ACCOUNT_SID</span></span></p></td>
<td align="left"><p><span data-ttu-id="e338c-135">用于写入（管理员）访问管理数据库的帐户的安全标识符（SID）。</span><span class="sxs-lookup"><span data-stu-id="e338c-135">Secure identifier (SID) of the account used for write (administrator) access to the Management database.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e338c-136">MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="e338c-136">MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="e338c-137">管理服务器远程计算机帐户（域 \ 帐户）。</span><span class="sxs-lookup"><span data-stu-id="e338c-137">Management server remote computer account (domain\account).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e338c-138">MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="e338c-138">MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="e338c-139">管理服务器（域 \ 帐户）的安装管理员登录。</span><span class="sxs-lookup"><span data-stu-id="e338c-139">Installation administrator login for the Management server (domain\account).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e338c-140">MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="e338c-140">MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span></span></p></td>
<td align="left"><p><span data-ttu-id="e338c-141">有效值为：</span><span class="sxs-lookup"><span data-stu-id="e338c-141">Valid values are:</span></span></p>
<ul>
<li><p><strong><span data-ttu-id="e338c-142">1 </strong> -管理服务位于本地计算机上，即 MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT 为空。</span><span class="sxs-lookup"><span data-stu-id="e338c-142">1</strong> – the Management service is on the local computer, that is, MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT is blank.</span></span></p></li>
<li><p><strong><span data-ttu-id="e338c-143">0 </strong> - 管理服务位于本地计算机的不同计算机上。</span><span class="sxs-lookup"><span data-stu-id="e338c-143">0</strong> - the Management service is on a different computer from the local computer.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="e338c-144">ManagementService 键</span><span class="sxs-lookup"><span data-stu-id="e338c-144">ManagementService key</span></span>**

<span data-ttu-id="e338c-145">如果要安装管理服务器，请在 "" 下设置这些注册表项 `HKLM\Software\Microsoft\AppV\Server\ManagementService` 。</span><span class="sxs-lookup"><span data-stu-id="e338c-145">If you are installing the Management server, set these registry keys under `HKLM\Software\Microsoft\AppV\Server\ManagementService`.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e338c-146">键名</span><span class="sxs-lookup"><span data-stu-id="e338c-146">Key name</span></span></th>
<th align="left"><span data-ttu-id="e338c-147">描述</span><span class="sxs-lookup"><span data-stu-id="e338c-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e338c-148">MANAGEMENT_ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="e338c-148">MANAGEMENT_ADMINACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="e338c-149">已授权管理 App-v （域 \ 帐户）的 Active Directory 域服务（AD DS）组或帐户。</span><span class="sxs-lookup"><span data-stu-id="e338c-149">Active Directory Domain Services (AD DS) group or account that is authorized to manage App-V (domain\account).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e338c-150">MANAGEMENT_DB_SQL_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="e338c-150">MANAGEMENT_DB_SQL_INSTANCE</span></span></p></td>
<td align="left"><p><span data-ttu-id="e338c-151">包含管理数据库的 SQL server 实例。</span><span class="sxs-lookup"><span data-stu-id="e338c-151">SQL server instance that contains the Management database.</span></span></p>
<p><span data-ttu-id="e338c-152">如果值为空，则使用默认数据库实例。</span><span class="sxs-lookup"><span data-stu-id="e338c-152">If the value is blank, the default database instance is used.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e338c-153">MANAGEMENT_DB_SQL_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="e338c-153">MANAGEMENT_DB_SQL_SERVER_NAME</span></span></p></td>
<td align="left"><p><span data-ttu-id="e338c-154">带有管理数据库的远程 SQL server 的名称。</span><span class="sxs-lookup"><span data-stu-id="e338c-154">Name of the remote SQL server with the Management database.</span></span></p>
<p><span data-ttu-id="e338c-155">如果值为空，则使用本地计算机。</span><span class="sxs-lookup"><span data-stu-id="e338c-155">If the value is blank, the local computer is used.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="e338c-156">ReportingDatabase 键</span><span class="sxs-lookup"><span data-stu-id="e338c-156">ReportingDatabase key</span></span>**

<span data-ttu-id="e338c-157">如果要安装报告数据库，请在 "" 下设置这些注册表项 `HKLM\Software\Microsoft\AppV\Server\ReportingDatabase` 。</span><span class="sxs-lookup"><span data-stu-id="e338c-157">If you are installing the Reporting database, set these registry keys under `HKLM\Software\Microsoft\AppV\Server\ReportingDatabase`.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e338c-158">键名</span><span class="sxs-lookup"><span data-stu-id="e338c-158">Key name</span></span></th>
<th align="left"><span data-ttu-id="e338c-159">描述</span><span class="sxs-lookup"><span data-stu-id="e338c-159">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e338c-160">IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="e338c-160">IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</span></span></p></td>
<td align="left"><p><span data-ttu-id="e338c-161">描述访问非本地报告数据库是否需要公共访问帐户。</span><span class="sxs-lookup"><span data-stu-id="e338c-161">Describes whether a public access account is required to access non-local reporting databases.</span></span> <span data-ttu-id="e338c-162">如果需要，值设置为 "1"。</span><span class="sxs-lookup"><span data-stu-id="e338c-162">Value is set to “1” if it is required.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e338c-163">REPORTING_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="e338c-163">REPORTING_DB_NAME</span></span></p></td>
<td align="left"><p><span data-ttu-id="e338c-164">报告数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="e338c-164">Name of the Reporting database.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e338c-165">REPORTING_DB_PUBLIC_ACCESS_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="e338c-165">REPORTING_DB_PUBLIC_ACCESS_ACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="e338c-166">用于对报告数据库进行读取（公共）访问的帐户。</span><span class="sxs-lookup"><span data-stu-id="e338c-166">Account used for read (public) access to the Reporting database.</span></span></p>
<p><span data-ttu-id="e338c-167">在 <code>IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> 设置为1时使用。</span><span class="sxs-lookup"><span data-stu-id="e338c-167">Used when <code>IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> is set to 1.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e338c-168">REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_SID</span><span class="sxs-lookup"><span data-stu-id="e338c-168">REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_SID</span></span></p></td>
<td align="left"><p><span data-ttu-id="e338c-169">用于对报告数据库进行读取（公共）访问的帐户的安全标识符（SID）。</span><span class="sxs-lookup"><span data-stu-id="e338c-169">Secure identifier (SID) of the account used for read (public) access to the Reporting database.</span></span></p>
<p><span data-ttu-id="e338c-170">在 <code>IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> 设置为1时使用。</span><span class="sxs-lookup"><span data-stu-id="e338c-170">Used when <code>IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> is set to 1.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e338c-171">REPORTING_DB_SQL_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="e338c-171">REPORTING_DB_SQL_INSTANCE</span></span></p></td>
<td align="left"><p><span data-ttu-id="e338c-172">报告数据库的 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="e338c-172">SQL Server instance for the Reporting database.</span></span></p>
<p><span data-ttu-id="e338c-173">如果值为空，则使用默认数据库实例。</span><span class="sxs-lookup"><span data-stu-id="e338c-173">If the value is blank, the default database instance is used.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e338c-174">REPORTING_DB_WRITE_ACCESS_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="e338c-174">REPORTING_DB_WRITE_ACCESS_ACCOUNT</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e338c-175">REPORTING_DB_WRITE_ACCESS_ACCOUNT_SID</span><span class="sxs-lookup"><span data-stu-id="e338c-175">REPORTING_DB_WRITE_ACCESS_ACCOUNT_SID</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e338c-176">REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="e338c-176">REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="e338c-177">报表服务器远程计算机帐户（域 \ 帐户）。</span><span class="sxs-lookup"><span data-stu-id="e338c-177">Reporting server remote computer account (domain\account).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e338c-178">REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="e338c-178">REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="e338c-179">报告服务器（域 \ 帐户）的安装管理员登录。</span><span class="sxs-lookup"><span data-stu-id="e338c-179">Installation administrator login for the Reporting server (domain\account).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e338c-180">REPORTING_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="e338c-180">REPORTING_SERVER_MACHINE_USE_LOCAL</span></span></p></td>
<td align="left"><p><span data-ttu-id="e338c-181">有效值为：</span><span class="sxs-lookup"><span data-stu-id="e338c-181">Valid values are:</span></span></p>
<ul>
<li><p><strong><span data-ttu-id="e338c-182">1 </strong> -报告服务在本地计算机上，即 REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT 为空。</span><span class="sxs-lookup"><span data-stu-id="e338c-182">1</strong> – the Reporting service is on the local computer, that is, REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT is blank.</span></span></p></li>
<li><p><strong><span data-ttu-id="e338c-183">0 </strong> - 报告服务位于本地计算机的不同计算机上。</span><span class="sxs-lookup"><span data-stu-id="e338c-183">0</strong> - the Reporting service is on a different computer from the local computer.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="e338c-184">ReportingService 键</span><span class="sxs-lookup"><span data-stu-id="e338c-184">ReportingService key</span></span>**

<span data-ttu-id="e338c-185">如果要安装报表服务器，请在 "" 下设置这些注册表项 `HKLM\Software\Microsoft\AppV\Server\ReportingService` 。</span><span class="sxs-lookup"><span data-stu-id="e338c-185">If you are installing the Reporting server, set these registry keys under `HKLM\Software\Microsoft\AppV\Server\ReportingService`.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e338c-186">键名</span><span class="sxs-lookup"><span data-stu-id="e338c-186">Key name</span></span></th>
<th align="left"><span data-ttu-id="e338c-187">描述</span><span class="sxs-lookup"><span data-stu-id="e338c-187">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e338c-188">REPORTING_DB_SQL_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="e338c-188">REPORTING_DB_SQL_INSTANCE</span></span></p></td>
<td align="left"><p><span data-ttu-id="e338c-189">报告数据库的 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="e338c-189">SQL Server instance for the Reporting database.</span></span></p>
<p><span data-ttu-id="e338c-190">如果值为空，则使用默认数据库实例。</span><span class="sxs-lookup"><span data-stu-id="e338c-190">If the value is blank, the default database instance is used.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e338c-191">REPORTING_DB_SQL_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="e338c-191">REPORTING_DB_SQL_SERVER_NAME</span></span></p></td>
<td align="left"><p><span data-ttu-id="e338c-192">带有报告数据库的远程 SQL 服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="e338c-192">Name of the remote SQL server with the Reporting database.</span></span></p>
<p><span data-ttu-id="e338c-193">如果值为空，则使用本地计算机。</span><span class="sxs-lookup"><span data-stu-id="e338c-193">If the value is blank, the local computer is used.</span></span></p></td>
</tr>
</tbody>
</table>

