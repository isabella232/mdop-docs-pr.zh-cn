---
title: 规划 MBAM 2.5 组和帐户
description: 规划 MBAM 2.5 组和帐户
author: dansimp
ms.assetid: 73bb9fe5-5900-4b6f-b271-ade62991fca1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 11/02/2016
ms.openlocfilehash: 3431c3602685a4f96cb4c1333700107ba9c38b96
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803841"
---
# <span data-ttu-id="27428-103">规划 MBAM 2.5 组和帐户</span><span class="sxs-lookup"><span data-stu-id="27428-103">Planning for MBAM 2.5 Groups and Accounts</span></span>


<span data-ttu-id="27428-104">本主题列出了必须在 Active Directory 域服务（AD DS）中创建的角色和帐户，以便为 Microsoft BitLocker 管理和监视（MBAM）数据库、报表和 web 应用程序提供安全和访问权限。</span><span class="sxs-lookup"><span data-stu-id="27428-104">This topic lists the roles and accounts that you must create in Active Directory Domain Services (AD DS) to provide security and access rights for the Microsoft BitLocker Administration and Monitoring (MBAM) databases, reports, and web applications.</span></span> <span data-ttu-id="27428-105">对于每个角色和帐户，提供了 MBAM Server 配置向导中的相应字段。</span><span class="sxs-lookup"><span data-stu-id="27428-105">For each role and account, the corresponding field in the MBAM Server Configuration wizard is provided.</span></span> <span data-ttu-id="27428-106">有关与这些帐户对应的 Windows PowerShell cmdlet 和参数的列表，请参阅[使用 Windows PowerShell 配置 MBAM 2.5 服务器功能](configuring-mbam-25-server-features-by-using-windows-powershell.md#bkmk-reqd-posh-accts)。</span><span class="sxs-lookup"><span data-stu-id="27428-106">For a list of Windows PowerShell cmdlets and parameters that correspond to these accounts, see [Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md#bkmk-reqd-posh-accts).</span></span>

**<span data-ttu-id="27428-107">注意</span><span class="sxs-lookup"><span data-stu-id="27428-107">Note</span></span>**  
<span data-ttu-id="27428-108">MBAM 不支持使用托管服务帐户。</span><span class="sxs-lookup"><span data-stu-id="27428-108">MBAM does not support the use of managed service accounts.</span></span>



## <span data-ttu-id="27428-109">数据库帐户</span><span class="sxs-lookup"><span data-stu-id="27428-109">Database accounts</span></span>


<span data-ttu-id="27428-110">为合规性和审核数据库以及恢复数据库创建以下帐户。</span><span class="sxs-lookup"><span data-stu-id="27428-110">Create the following accounts for the Compliance and Audit Database and the Recovery Database.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="27428-111">帐户名称和用途</span><span class="sxs-lookup"><span data-stu-id="27428-111">Account name and purpose</span></span></th>
<th align="left"><span data-ttu-id="27428-112">帐户类型</span><span class="sxs-lookup"><span data-stu-id="27428-112">Account type</span></span></th>
<th align="left"><span data-ttu-id="27428-113">与此帐户对应的 MBAM 服务器配置向导字段</span><span class="sxs-lookup"><span data-stu-id="27428-113">MBAM Server Configuration wizard field that corresponds to this account</span></span></th>
<th align="left"><span data-ttu-id="27428-114">与此帐户对应的 "MBAM 服务器配置向导" 字段的说明</span><span class="sxs-lookup"><span data-stu-id="27428-114">Description of the MBAM Server Configuration wizard field that corresponds to this account</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="27428-115">合规性和审核数据库和恢复数据库对报表的读/写用户或组</span><span class="sxs-lookup"><span data-stu-id="27428-115">Compliance and Audit Database and Recovery Database read/write user or group for reports</span></span></p></td>
<td align="left"><p><span data-ttu-id="27428-116">用户或组</span><span class="sxs-lookup"><span data-stu-id="27428-116">User or Group</span></span></p></td>
<td align="left"><p><span data-ttu-id="27428-117">读/写访问域用户或组</span><span class="sxs-lookup"><span data-stu-id="27428-117">Read/write access domain user or group</span></span></p></td>
<td align="left"><p><span data-ttu-id="27428-118">对合规性和审核数据库和恢复数据库具有读/写访问权限的域用户或组，使 web 应用程序能够访问这些数据库中的数据和报告。</span><span class="sxs-lookup"><span data-stu-id="27428-118">Domain user or group that has read/write access to the Compliance and Audit Database and the Recovery Database to enable the web applications to access the data and reports in these databases.</span></span></p>
<p><span data-ttu-id="27428-119">如果在此字段中输入用户名，它必须与 <strong> </strong> " <strong> 配置 web 应用程序" 页面上的 "web 服务应用程序池域帐户" 字段中的值相同 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="27428-119">If you enter a user name in this field, it must be the same value as the value in the <strong>Web service application pool domain account</strong> field on the <strong>Configure Web Applications</strong> page.</span></span></p>
<p><span data-ttu-id="27428-120">如果在此字段中输入组名称，则 " <strong> 配置 Web 应用程序" 页面上的 "Web 服务应用程序池域帐户" 字段中的值 </strong> <strong> </strong> 必须是您在此字段中输入的组的成员。</span><span class="sxs-lookup"><span data-stu-id="27428-120">If you enter a group name in this field, the value in the <strong>Web service application pool domain account</strong> field on the <strong>Configure Web Applications</strong> page must be a member of the group you enter in this field.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="27428-121">对报表的合规性和审核数据库只读用户或组</span><span class="sxs-lookup"><span data-stu-id="27428-121">Compliance and Audit Database read-only user or group for reports</span></span></p></td>
<td align="left"><p><span data-ttu-id="27428-122">用户或组</span><span class="sxs-lookup"><span data-stu-id="27428-122">User or Group</span></span></p></td>
<td align="left"><p><span data-ttu-id="27428-123">只读访问域用户或组</span><span class="sxs-lookup"><span data-stu-id="27428-123">Read-only access domain user or group</span></span></p></td>
<td align="left"><p><span data-ttu-id="27428-124">将对合规性和审核数据库具有只读访问权限的用户或组的名称，以使报表能够访问此数据库中的合规性和审核数据。</span><span class="sxs-lookup"><span data-stu-id="27428-124">Name of the user or group that will have read-only access to the Compliance and Audit Database to enable the reports to access the compliance and audit data in this database.</span></span></p>
<p><span data-ttu-id="27428-125">如果在此字段中输入用户名，则该用户名必须与你在 <strong> </strong> "配置报告" 页面上的 "合规性和审核数据库域帐户" 字段中指定的用户相同 <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="27428-125">If you enter a user name in this field, it must be the same user as the one you specify in the <strong>Compliance and Audit Database domain account</strong> field on the <strong>Configure Reports</strong> page.</span></span></p>
<p><span data-ttu-id="27428-126">如果在此字段中输入组名称，则在 <strong> "配置报告" 页面上的 "合规性和审核数据库域帐户" 字段中指定的值 </strong> <strong> </strong> 必须是您在此字段中指定的组的成员。</span><span class="sxs-lookup"><span data-stu-id="27428-126">If you enter a group name in this field, the value that you specify in the <strong>Compliance and Audit Database domain account</strong> field on the <strong>Configure Reports</strong> page must be a member of the group that you specify in this field.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="27428-127">报告帐户</span><span class="sxs-lookup"><span data-stu-id="27428-127">Reporting accounts</span></span>


<span data-ttu-id="27428-128">为 "报表" 功能创建以下帐户。</span><span class="sxs-lookup"><span data-stu-id="27428-128">Create the following accounts for the Reports feature.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="27428-129">帐户名称/用途</span><span class="sxs-lookup"><span data-stu-id="27428-129">Account name/purpose</span></span></th>
<th align="left"><span data-ttu-id="27428-130">帐户类型</span><span class="sxs-lookup"><span data-stu-id="27428-130">Account type</span></span></th>
<th align="left"><span data-ttu-id="27428-131">与此帐户对应的 MBAM 服务器配置向导字段</span><span class="sxs-lookup"><span data-stu-id="27428-131">MBAM Server Configuration wizard field that corresponds to this account</span></span></th>
<th align="left"><span data-ttu-id="27428-132">与此帐户对应的 "MBAM 服务器配置向导" 字段的说明</span><span class="sxs-lookup"><span data-stu-id="27428-132">Description of the MBAM Server Configuration wizard field that corresponds to this account</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="27428-133">报告只读域访问组</span><span class="sxs-lookup"><span data-stu-id="27428-133">Reports read-only domain access group</span></span></p></td>
<td align="left"><p><span data-ttu-id="27428-134">组</span><span class="sxs-lookup"><span data-stu-id="27428-134">Group</span></span></p></td>
<td align="left"><p><span data-ttu-id="27428-135">报告角色域组</span><span class="sxs-lookup"><span data-stu-id="27428-135">Reporting role domain group</span></span></p></td>
<td align="left"><p><span data-ttu-id="27428-136">指定对管理和监视网站中的报表具有只读访问权限的域用户组。</span><span class="sxs-lookup"><span data-stu-id="27428-136">Specifies the domain user group that has read-only access to the reports in the Administration and Monitoring Website.</span></span> <span data-ttu-id="27428-137">你指定的组必须是在启用 web 应用时为 "报表只读访问" 组参数指定的相同组。</span><span class="sxs-lookup"><span data-stu-id="27428-137">The group you specify must be the same group you specified for the Reports Read Only Access Group parameter when the web apps are enabled.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="27428-138">合规性和审核数据库域用户帐户</span><span class="sxs-lookup"><span data-stu-id="27428-138">Compliance and Audit Database domain user account</span></span></p></td>
<td align="left"><p><span data-ttu-id="27428-139">用户</span><span class="sxs-lookup"><span data-stu-id="27428-139">User</span></span></p></td>
<td align="left"><p><span data-ttu-id="27428-140">合规性和审核数据库域帐户</span><span class="sxs-lookup"><span data-stu-id="27428-140">Compliance and Audit Database domain account</span></span></p></td>
<td align="left"><p><span data-ttu-id="27428-141">本地 SQL Server Reporting Services 实例用于访问合规性和审核数据库的域用户帐户和密码。</span><span class="sxs-lookup"><span data-stu-id="27428-141">Domain user account and password that the local SQL Server Reporting Services instance uses to access the Compliance and Audit Database.</span></span> <span data-ttu-id="27428-142">此帐户需要 <strong> 以批处理权限登录 </strong> 到 SQL Server Reporting Services 服务器。</span><span class="sxs-lookup"><span data-stu-id="27428-142">This account requires <strong>Log On as Batch</strong> rights to the SQL Server Reporting Services server.</span></span></p>
<p><span data-ttu-id="27428-143">如果您在 <strong> "配置数据库" 页面上的 "只读访问域用户" 或 "组" 字段中输入的值 </strong> <strong> </strong> 是用户名，则必须在此字段中输入相同的值。</span><span class="sxs-lookup"><span data-stu-id="27428-143">If the value you enter in the <strong>Read-only access domain user or group</strong> field on the <strong>Configure Databases</strong> page is a user name, you must enter that same value in this field.</span></span></p>
<p><span data-ttu-id="27428-144">如果您在 <strong> "配置数据库" 页面上的 "只读访问域用户" 或 "组" 字段中输入的值 </strong> <strong> </strong> 是组名称，则您在此字段中输入的值必须是该组的成员。</span><span class="sxs-lookup"><span data-stu-id="27428-144">If the value you enter in the <strong>Read-only access domain user or group</strong> field on the <strong>Configure Databases</strong> page is a group name, the value that you enter in this field must be a member of that group.</span></span></p>
<p><span data-ttu-id="27428-145">将此帐户的密码配置为永不过期。</span><span class="sxs-lookup"><span data-stu-id="27428-145">Configure the password for this account to never expire.</span></span> <span data-ttu-id="27428-146">用户帐户应该能够访问 MBAM Reports Users 组中可用的所有数据。</span><span class="sxs-lookup"><span data-stu-id="27428-146">The user account should be able to access all data that is available to the MBAM Reports Users group.</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-helpdesk-roles"></a><span data-ttu-id="27428-147">管理和监控网站（帮助台）帐户</span><span class="sxs-lookup"><span data-stu-id="27428-147">Administration and Monitoring Website (Help Desk) accounts</span></span>


<span data-ttu-id="27428-148">为 "管理和监视" 网站创建以下帐户。</span><span class="sxs-lookup"><span data-stu-id="27428-148">Create the following accounts for the Administration and Monitoring Website.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="27428-149">帐户名称/用途</span><span class="sxs-lookup"><span data-stu-id="27428-149">Account name/purpose</span></span></th>
<th align="left"><span data-ttu-id="27428-150">帐户类型</span><span class="sxs-lookup"><span data-stu-id="27428-150">Account type</span></span></th>
<th align="left"><span data-ttu-id="27428-151">与此帐户对应的 MBAM 服务器配置向导字段</span><span class="sxs-lookup"><span data-stu-id="27428-151">MBAM Server Configuration wizard field that corresponds to this account</span></span></th>
<th align="left"><span data-ttu-id="27428-152">与此帐户对应的 "MBAM 服务器配置向导" 字段的说明</span><span class="sxs-lookup"><span data-stu-id="27428-152">Description of the MBAM Server Configuration wizard field that corresponds to this account</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="27428-153">Web 服务应用程序池域帐户</span><span class="sxs-lookup"><span data-stu-id="27428-153">Web service application pool domain account</span></span></p></td>
<td align="left"><p><span data-ttu-id="27428-154">用户</span><span class="sxs-lookup"><span data-stu-id="27428-154">User</span></span></p></td>
<td align="left"><p><span data-ttu-id="27428-155">Web 服务应用程序池域帐户</span><span class="sxs-lookup"><span data-stu-id="27428-155">Web service application pool domain account</span></span></p></td>
<td align="left"><p><span data-ttu-id="27428-156">要由 web 应用程序的应用程序池使用的域用户帐户。</span><span class="sxs-lookup"><span data-stu-id="27428-156">Domain user account to be used by the application pool for the web applications.</span></span></p>
<p><span data-ttu-id="27428-157">如果在 <strong> "配置数据库" 页面上的 "读/写访问域" 用户或组字段中输入用户名 </strong> <strong> </strong> ，则必须在此字段中输入相同的值。</span><span class="sxs-lookup"><span data-stu-id="27428-157">If you enter a user name in the <strong>Read/write access domain user or group</strong> field on the <strong>Configure Databases</strong> page, you must enter that same value in this field.</span></span></p>
<p><span data-ttu-id="27428-158">如果在 <strong> "配置数据库" 页面上的 "读/写访问域" 用户或组字段中输入组名称 </strong> <strong> </strong> ，则在此字段中输入的值必须是该组的成员。</span><span class="sxs-lookup"><span data-stu-id="27428-158">If you enter a group name in the <strong>Read/write access domain user or group</strong> field on the <strong>Configure Databases</strong> page, the value you enter in this field must be a member of that group.</span></span></p>
<p><span data-ttu-id="27428-159">如果不指定凭据，将使用为以前启用的任何 web 应用程序指定的凭据。</span><span class="sxs-lookup"><span data-stu-id="27428-159">If you do not specify credentials, the credentials that were specified for any previously enabled web application will be used.</span></span> <span data-ttu-id="27428-160">所有 web 应用程序都必须使用相同的应用程序池凭据。</span><span class="sxs-lookup"><span data-stu-id="27428-160">All web applications must use the same application pool credentials.</span></span> <span data-ttu-id="27428-161">如果为不同的 web 应用程序指定不同的凭据，将使用最近指定的值。</span><span class="sxs-lookup"><span data-stu-id="27428-161">If you specify different credentials for different web applications, the most recently specified value will be used.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="27428-162">重要提示</span><span class="sxs-lookup"><span data-stu-id="27428-162">Important</span></span></strong><br/><p><span data-ttu-id="27428-163">为了提高安全性，请将凭据中指定的帐户设置为具有受限的用户权限。</span><span class="sxs-lookup"><span data-stu-id="27428-163">For improved security, set the account that is specified in the credentials to have limited user rights.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="27428-164">MBAM 高级帮助台用户访问组</span><span class="sxs-lookup"><span data-stu-id="27428-164">MBAM Advanced Helpdesk Users access group</span></span></p></td>
<td align="left"><p><span data-ttu-id="27428-165">组</span><span class="sxs-lookup"><span data-stu-id="27428-165">Group</span></span></p></td>
<td align="left"><p><span data-ttu-id="27428-166">MBAM 高级帮助台用户</span><span class="sxs-lookup"><span data-stu-id="27428-166">MBAM Advanced Helpdesk Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="27428-167">其成员有权访问管理和监视网站的所有恢复区域的域用户组。</span><span class="sxs-lookup"><span data-stu-id="27428-167">Domain user group whose members have access to all recovery areas of the Administration and Monitoring Website.</span></span> <span data-ttu-id="27428-168">具有此角色的用户必须在帮助最终用户恢复其驱动器时仅输入恢复密钥，而不是最终用户的域和用户名。</span><span class="sxs-lookup"><span data-stu-id="27428-168">Users who have this role have to enter only the recovery key, and not the end user’s domain and user name, when helping end users recover their drives.</span></span> <span data-ttu-id="27428-169">如果用户是 MBAM 支持人员组和 MBAM 高级帮助台用户组的成员，则 MBAM 高级帮助台用户组权限将替代 MBAM 帮助台组权限。</span><span class="sxs-lookup"><span data-stu-id="27428-169">If a user is a member of both the MBAM Helpdesk Users group and the MBAM Advanced Helpdesk Users group, the MBAM Advanced Helpdesk Users group permissions override the MBAM Helpdesk Group permissions.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="27428-170">MBAM 帮助台用户访问组</span><span class="sxs-lookup"><span data-stu-id="27428-170">MBAM Helpdesk Users access group</span></span></p></td>
<td align="left"><p><span data-ttu-id="27428-171">组</span><span class="sxs-lookup"><span data-stu-id="27428-171">Group</span></span></p></td>
<td align="left"><p><span data-ttu-id="27428-172">MBAM 帮助台用户</span><span class="sxs-lookup"><span data-stu-id="27428-172">MBAM Helpdesk Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="27428-173">其成员有权访问 MBAM 管理和监视网站的 "管理 TPM 和驱动器恢复" 区域的域用户组。</span><span class="sxs-lookup"><span data-stu-id="27428-173">Domain user group whose members have access to the Manage TPM and Drive Recovery areas of the MBAM Administration and Monitoring Website.</span></span> <span data-ttu-id="27428-174">具有此角色的人员必须填写所有字段，包括最终用户的域和帐户名称，同时使用任一选项。</span><span class="sxs-lookup"><span data-stu-id="27428-174">Individuals who have this role must fill-in all fields, including the end-user’s domain and account name, when they use either option.</span></span></p>
<p><span data-ttu-id="27428-175">如果用户是 MBAM 支持人员组和 MBAM 高级帮助台用户组的成员，则 MBAM 高级帮助台用户组权限将替代 MBAM 帮助台组权限。</span><span class="sxs-lookup"><span data-stu-id="27428-175">If a user is a member of both the MBAM Helpdesk Users group and the MBAM Advanced Helpdesk Users group, the MBAM Advanced Helpdesk Users group permissions override the MBAM Helpdesk Group permissions.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="27428-176">MBAM 报表用户访问组</span><span class="sxs-lookup"><span data-stu-id="27428-176">MBAM Report Users access group</span></span></p></td>
<td align="left"><p><span data-ttu-id="27428-177">组</span><span class="sxs-lookup"><span data-stu-id="27428-177">Group</span></span></p></td>
<td align="left"><p><span data-ttu-id="27428-178">MBAM 报表用户</span><span class="sxs-lookup"><span data-stu-id="27428-178">MBAM Report Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="27428-179">其成员对管理和监视网站的 "报告" 区域中的报表具有只读访问权限的域用户组。</span><span class="sxs-lookup"><span data-stu-id="27428-179">Domain user group whose members have read-only access to the reports in the Reports area of the Administration and Monitoring Website.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="27428-180">MBAM 数据迁移用户组</span><span class="sxs-lookup"><span data-stu-id="27428-180">MBAM Data Migration User Group</span></span></p></td>
<td align="left"><p><span data-ttu-id="27428-181">组</span><span class="sxs-lookup"><span data-stu-id="27428-181">Group</span></span></p></td>
<td align="left"><p><span data-ttu-id="27428-182">MBAM 数据迁移用户</span><span class="sxs-lookup"><span data-stu-id="27428-182">MBAM Data Migration Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="27428-183">可选域用户组，其成员具有使用 MBAM 服务器上运行的 MBAM 恢复和硬件服务将数据写入 MBAM 的权限。</span><span class="sxs-lookup"><span data-stu-id="27428-183">Optional domain user group whose members have permissions to write data to MBAM by using the MBAM Recovery and Hardware Service running on the MBAM server.</span></span> <span data-ttu-id="27428-184">此帐户通常与 Write-Mbam \* cmdlet 一起使用，用于将恢复和 TPM 数据从 Active Directory 写入 MBAM 数据库。</span><span class="sxs-lookup"><span data-stu-id="27428-184">This account is generally used with the Write-Mbam\* cmdlets to write recovery and TPM data from Active Directory into the MBAM database.</span></span></p>
<p><span data-ttu-id="27428-185">有关详细信息，请参阅 <a href="mbam-25-security-considerations.md" data-raw-source="[MBAM 2.5 Security Considerations](mbam-25-security-considerations.md)"> MBAM 2.5 安全注意事项 </a> 。</span><span class="sxs-lookup"><span data-stu-id="27428-185">For more information, see <a href="mbam-25-security-considerations.md" data-raw-source="[MBAM 2.5 Security Considerations](mbam-25-security-considerations.md)">MBAM 2.5 Security Considerations</a>.</span></span></p></td>
</tr>
</tbody>
</table>




## <span data-ttu-id="27428-186">相关主题</span><span class="sxs-lookup"><span data-stu-id="27428-186">Related topics</span></span>


[<span data-ttu-id="27428-187">为 MBAM 2.5 准备你的环境</span><span class="sxs-lookup"><span data-stu-id="27428-187">Preparing your Environment for MBAM 2.5</span></span>](preparing-your-environment-for-mbam-25.md)

[<span data-ttu-id="27428-188">MBAM 2.5 部署先决条件</span><span class="sxs-lookup"><span data-stu-id="27428-188">MBAM 2.5 Deployment Prerequisites</span></span>](mbam-25-deployment-prerequisites.md)



## <span data-ttu-id="27428-189">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="27428-189">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="27428-190">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="27428-190">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="27428-191">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="27428-191">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





