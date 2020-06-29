---
title: MBAM 2.0 安全注意事项
description: MBAM 2.0 安全注意事项
author: dansimp
ms.assetid: 0aa5c6e2-d92c-4e30-9f6a-b48abb667ae5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 04dc9b667faddecab629b50f4c5d909fd7b2829e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803463"
---
# <span data-ttu-id="5277e-103">MBAM 2.0 安全注意事项</span><span class="sxs-lookup"><span data-stu-id="5277e-103">MBAM 2.0 Security Considerations</span></span>


<span data-ttu-id="5277e-104">本主题包含有关帐户和组、日志文件以及有关 Microsoft BitLocker 管理和监视的其他与安全相关的注意事项（MBAM）的简要概述。</span><span class="sxs-lookup"><span data-stu-id="5277e-104">This topic contains a brief overview about the accounts and groups, log files, and other security-related considerations for Microsoft BitLocker Administration and Monitoring (MBAM).</span></span> <span data-ttu-id="5277e-105">有关详细信息，请访问本文中的链接。</span><span class="sxs-lookup"><span data-stu-id="5277e-105">For more information, follow the links within this article.</span></span>

## <span data-ttu-id="5277e-106">常规安全注意事项</span><span class="sxs-lookup"><span data-stu-id="5277e-106">General Security Considerations</span></span>


**<span data-ttu-id="5277e-107">了解安全风险。</span><span class="sxs-lookup"><span data-stu-id="5277e-107">Understand the security risks.</span></span>** <span data-ttu-id="5277e-108">Microsoft BitLocker 管理和监视的最严重的风险是，未经授权的用户可能会截获其功能，这样就可以在 MBAM 客户端上重新配置 BitLocker 加密和获取 BitLocker 加密密钥数据。</span><span class="sxs-lookup"><span data-stu-id="5277e-108">The most serious risk from Microsoft BitLocker Administration and Monitoring is that its functionality could be hijacked by an unauthorized user who could then reconfigure BitLocker encryption and gain BitLocker encryption key data on MBAM Clients.</span></span> <span data-ttu-id="5277e-109">但是，由于拒绝服务攻击，较短时间内的 MBAM 功能损失通常不会产生灾难性影响，如电子邮件、网络通信、轻型和强大的。</span><span class="sxs-lookup"><span data-stu-id="5277e-109">However, the loss of MBAM functionality for a short period of time, due to a denial-of-service attack, does not generally have a catastrophic impact, unlike, for example, e-mail, network communications, light, and power.</span></span>

<span data-ttu-id="5277e-110">**确保计算机的物理安全**。</span><span class="sxs-lookup"><span data-stu-id="5277e-110">**Physically secure your computers**.</span></span> <span data-ttu-id="5277e-111">没有物理安全的安全性。</span><span class="sxs-lookup"><span data-stu-id="5277e-111">There is no security without physical security.</span></span> <span data-ttu-id="5277e-112">获得 MBAM 服务器物理访问权限的攻击者可能会使用它来攻击整个客户端。</span><span class="sxs-lookup"><span data-stu-id="5277e-112">An attacker who gets physical access to an MBAM Server could potentially use it to attack the entire client base.</span></span> <span data-ttu-id="5277e-113">所有潜在的物理攻击都必须被视为高风险并相应地缓解。</span><span class="sxs-lookup"><span data-stu-id="5277e-113">All potential physical attacks must be considered high risk and mitigated appropriately.</span></span> <span data-ttu-id="5277e-114">MBAM 服务器应存储在具有受控访问权限的安全服务器机房中。</span><span class="sxs-lookup"><span data-stu-id="5277e-114">MBAM servers should be stored in a secure server room with controlled access.</span></span> <span data-ttu-id="5277e-115">通过让操作系统锁定计算机，或使用安全的屏幕保护程序，确保管理员不在物理上显示这些计算机。</span><span class="sxs-lookup"><span data-stu-id="5277e-115">Secure these computers when administrators are not physically present by having the operating system lock the computer, or by using a secured screen saver.</span></span>

<span data-ttu-id="5277e-116">**对所有计算机应用最新的安全更新**。</span><span class="sxs-lookup"><span data-stu-id="5277e-116">**Apply the most recent security updates to all computers**.</span></span> <span data-ttu-id="5277e-117">通过订阅安全通知服务（），随时了解操作系统、Microsoft SQL Server 和 MBAM 的新更新 <https://go.microsoft.com/fwlink/?LinkId=28819> 。</span><span class="sxs-lookup"><span data-stu-id="5277e-117">Stay informed about new updates for operating systems, Microsoft SQL Server, and MBAM by subscribing to the Security Notification service (<https://go.microsoft.com/fwlink/?LinkId=28819>).</span></span>

<span data-ttu-id="5277e-118">**使用强密码或密码短语**。</span><span class="sxs-lookup"><span data-stu-id="5277e-118">**Use strong passwords or pass phrases**.</span></span> <span data-ttu-id="5277e-119">对于所有 MBAM 和 MBAM 管理员帐户，请始终使用具有15个或更多字符的强密码。</span><span class="sxs-lookup"><span data-stu-id="5277e-119">Always use strong passwords with 15 or more characters for all MBAM and MBAM administrator accounts.</span></span> <span data-ttu-id="5277e-120">千万不要使用空白密码。</span><span class="sxs-lookup"><span data-stu-id="5277e-120">Never use blank passwords.</span></span> <span data-ttu-id="5277e-121">有关密码概念的详细信息，请参阅 TechNet 上的 "帐户密码和策略" 白皮书（ <https://go.microsoft.com/fwlink/?LinkId=30009> ）。</span><span class="sxs-lookup"><span data-stu-id="5277e-121">For more information about password concepts, see the “Account Passwords and Policies” white paper on TechNet (<https://go.microsoft.com/fwlink/?LinkId=30009>).</span></span>

## <span data-ttu-id="5277e-122">MBAM 中的帐户和组</span><span class="sxs-lookup"><span data-stu-id="5277e-122">Accounts and Groups in MBAM</span></span>


<span data-ttu-id="5277e-123">管理用户帐户的最佳做法是创建域全局组并向其添加用户帐户。</span><span class="sxs-lookup"><span data-stu-id="5277e-123">The best practice for managing user accounts is to create domain global groups and add user accounts to them.</span></span> <span data-ttu-id="5277e-124">然后，将域全局帐户添加到 MBAM 服务器上必需的 MBAM 本地组。</span><span class="sxs-lookup"><span data-stu-id="5277e-124">Then, add the domain global accounts to the necessary MBAM local groups on the MBAM Servers.</span></span>

### <span data-ttu-id="5277e-125">ActiveDirectoryDomainServices 组</span><span class="sxs-lookup"><span data-stu-id="5277e-125">ActiveDirectoryDomainServices Groups</span></span>

<span data-ttu-id="5277e-126">在 MBAM 设置过程中，不会自动创建任何 Active Directory 组。</span><span class="sxs-lookup"><span data-stu-id="5277e-126">No Active Directory groups are created automatically during the MBAM setup process.</span></span> <span data-ttu-id="5277e-127">但是，建议你创建以下 ActiveDirectoryDomainServices 全局组以管理 MBAM 操作。</span><span class="sxs-lookup"><span data-stu-id="5277e-127">However, it is recommended that you create the following ActiveDirectoryDomainServices global groups to manage MBAM operations.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="5277e-128">组名称</span><span class="sxs-lookup"><span data-stu-id="5277e-128">Group Name</span></span></th>
<th align="left"><span data-ttu-id="5277e-129">详细信息</span><span class="sxs-lookup"><span data-stu-id="5277e-129">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5277e-130">MBAM 高级帮助台用户</span><span class="sxs-lookup"><span data-stu-id="5277e-130">MBAM Advanced Helpdesk Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="5277e-131">创建此组以管理在 MBAM 设置期间创建的 MBAM 高级帮助台用户本地组的成员。</span><span class="sxs-lookup"><span data-stu-id="5277e-131">Create this group to manage members of the MBAM Advanced Helpdesk Users local group created during MBAM Setup.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5277e-132">MBAM 合规性审核数据库访问</span><span class="sxs-lookup"><span data-stu-id="5277e-132">MBAM Compliance Auditing DB Access</span></span></p></td>
<td align="left"><p><span data-ttu-id="5277e-133">创建此组以管理在 MBAM 安装期间创建的 MBAM 合规性审核 DB Access 本地组的成员。</span><span class="sxs-lookup"><span data-stu-id="5277e-133">Create this group to manage members of the MBAM Compliance Auditing DB Access local group created during MBAM Setup.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5277e-134">MBAM 帮助台用户</span><span class="sxs-lookup"><span data-stu-id="5277e-134">MBAM Helpdesk Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="5277e-135">创建此组以管理在 MBAM 设置期间创建的 MBAM 帮助台用户本地组的成员。</span><span class="sxs-lookup"><span data-stu-id="5277e-135">Create this group to manage members of the MBAM Helpdesk Users local group created during MBAM Setup.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5277e-136">MBAM 恢复和硬件 DB 访问</span><span class="sxs-lookup"><span data-stu-id="5277e-136">MBAM Recovery and Hardware DB Access</span></span></p></td>
<td align="left"><p><span data-ttu-id="5277e-137">创建此组以管理在 MBAM 安装期间创建的 MBAM 恢复和硬件 DB Access 本地组的成员。</span><span class="sxs-lookup"><span data-stu-id="5277e-137">Create this group to manage members of the MBAM Recovery and Hardware DB Access local group created during MBAM Setup.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5277e-138">MBAM 报表用户</span><span class="sxs-lookup"><span data-stu-id="5277e-138">MBAM Report Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="5277e-139">创建此组以管理在 MBAM 设置期间创建的 MBAM 报表用户本地组的成员。</span><span class="sxs-lookup"><span data-stu-id="5277e-139">Create this group to manage members of the MBAM Report Users local group created during MBAM Setup.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5277e-140">MBAM 系统管理员</span><span class="sxs-lookup"><span data-stu-id="5277e-140">MBAM System Administrators</span></span></p></td>
<td align="left"><p><span data-ttu-id="5277e-141">创建此组以管理在 MBAM 设置期间创建的 MBAM 系统管理员本地组的成员。</span><span class="sxs-lookup"><span data-stu-id="5277e-141">Create this group to manage members of the MBAM System Administrators local group created during MBAM Setup.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5277e-142">BitLocker 加密免除</span><span class="sxs-lookup"><span data-stu-id="5277e-142">BitLocker Encryption Exemptions</span></span></p></td>
<td align="left"><p><span data-ttu-id="5277e-143">创建此组以管理应从登录的计算机上开始免除 BitLocker 加密的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="5277e-143">Create this group to manage user accounts that should be exempted from BitLocker encryption starting on computers that they log on to.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="-------------mbam-server-local-groups"></a> <span data-ttu-id="5277e-144">MBAM 服务器本地组</span><span class="sxs-lookup"><span data-stu-id="5277e-144">MBAM Server Local Groups</span></span>

<span data-ttu-id="5277e-145">MBAM 安装程序创建本地组以支持 MBAM 操作。</span><span class="sxs-lookup"><span data-stu-id="5277e-145">MBAM Setup creates local groups to support MBAM operations.</span></span> <span data-ttu-id="5277e-146">应将 ActiveDirectoryDomainServices 全局组添加到相应的 MBAM 本地组，以配置 MBAM 安全和数据访问权限。</span><span class="sxs-lookup"><span data-stu-id="5277e-146">You should add the ActiveDirectoryDomainServices global groups to the appropriate MBAM local groups to configure MBAM security and data access permissions.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="5277e-147">组名称</span><span class="sxs-lookup"><span data-stu-id="5277e-147">Group Name</span></span></th>
<th align="left"><span data-ttu-id="5277e-148">详细信息</span><span class="sxs-lookup"><span data-stu-id="5277e-148">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5277e-149">MBAM 高级帮助台用户</span><span class="sxs-lookup"><span data-stu-id="5277e-149">MBAM Advanced Helpdesk Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="5277e-150">本组成员已增加了对 MBAM 中技术支持功能的访问权限。</span><span class="sxs-lookup"><span data-stu-id="5277e-150">Members of this group have increased access to the Help Desk features from MBAM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5277e-151">MBAM 合规性审核数据库访问</span><span class="sxs-lookup"><span data-stu-id="5277e-151">MBAM Compliance Auditing DB Access</span></span></p></td>
<td align="left"><p><span data-ttu-id="5277e-152">包含有权访问 MBAM 合规性和审核数据库的计算机。</span><span class="sxs-lookup"><span data-stu-id="5277e-152">Contains the machines that have access to the MBAM Compliance and Auditing Database.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5277e-153">MBAM 帮助台用户</span><span class="sxs-lookup"><span data-stu-id="5277e-153">MBAM Helpdesk Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="5277e-154">本组成员可以访问 MBAM 中的某些技术支持功能。</span><span class="sxs-lookup"><span data-stu-id="5277e-154">Members of this group have access to some of the Help Desk features from MBAM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5277e-155">MBAM 恢复和硬件 DB 访问</span><span class="sxs-lookup"><span data-stu-id="5277e-155">MBAM Recovery and Hardware DB Access</span></span></p></td>
<td align="left"><p><span data-ttu-id="5277e-156">包含有权访问 MBAM 恢复数据库的计算机。</span><span class="sxs-lookup"><span data-stu-id="5277e-156">Contains the machines that have access to the MBAM Recovery Database.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5277e-157">MBAM 报表用户</span><span class="sxs-lookup"><span data-stu-id="5277e-157">MBAM Report Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="5277e-158">本组成员可以访问 MBAM 中的合规性和审核报告。</span><span class="sxs-lookup"><span data-stu-id="5277e-158">Members of this group have access to the Compliance and Audit reports from MBAM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5277e-159">MBAM 系统管理员</span><span class="sxs-lookup"><span data-stu-id="5277e-159">MBAM System Administrators</span></span></p></td>
<td align="left"><p><span data-ttu-id="5277e-160">本组成员有权访问所有 MBAM 功能。</span><span class="sxs-lookup"><span data-stu-id="5277e-160">Members of this group have access to all MBAM features.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="5277e-161">SSRS 报表服务帐户</span><span class="sxs-lookup"><span data-stu-id="5277e-161">SSRS Reports Service Account</span></span>

<span data-ttu-id="5277e-162">SSRS 报表服务帐户提供用于运行通过 SSRS 提供的 MBAM 报告的安全上下文。</span><span class="sxs-lookup"><span data-stu-id="5277e-162">The SSRS Reports service account provides the security context to run the MBAM reports available through SSRS.</span></span> <span data-ttu-id="5277e-163">它在 MBAM 安装期间进行配置。</span><span class="sxs-lookup"><span data-stu-id="5277e-163">It is configured during MBAM Setup.</span></span>

<span data-ttu-id="5277e-164">当配置 SSRS 报表服务帐户时，请指定域用户帐户，并将密码配置为永不过期。</span><span class="sxs-lookup"><span data-stu-id="5277e-164">When you configure the SSRS Reports service account, specify a domain user account, and configure the password to never expire.</span></span>

<span data-ttu-id="5277e-165">**注意** 如果在部署 MBAM 后更改服务帐户的名称，则必须将报告数据源重新配置为使用新的服务帐户凭据。</span><span class="sxs-lookup"><span data-stu-id="5277e-165">**Note** If you change the name of the service account after you deploy MBAM, you must reconfigure the reporting data source to use the new service account credentials.</span></span> <span data-ttu-id="5277e-166">否则，您将不能访问技术支持门户。</span><span class="sxs-lookup"><span data-stu-id="5277e-166">Otherwise, you will not be able to access the Help Desk Portal.</span></span>

 

## <a href="" id="---------mbam-log-files"></a> <span data-ttu-id="5277e-167">MBAM 日志文件</span><span class="sxs-lookup"><span data-stu-id="5277e-167">MBAM Log Files</span></span>


<span data-ttu-id="5277e-168">在 MBAM 安装期间，在安装用户的% temp% 文件夹中创建以下 MBAM 安装日志文件：</span><span class="sxs-lookup"><span data-stu-id="5277e-168">The following MBAM Setup log files are created in the installing user’s %temp% folder during MBAM Setup:</span></span>

**<span data-ttu-id="5277e-169">MBAM Server 安装程序日志文件</span><span class="sxs-lookup"><span data-stu-id="5277e-169">MBAM Server Setup log files</span></span>**

<a href="" id="msi-five-random-characters--log"></a><span data-ttu-id="5277e-170">MSI <em> &lt; 5 个随机字符 &gt; </em> 。日志</span><span class="sxs-lookup"><span data-stu-id="5277e-170">MSI<em>&lt;five random characters&gt;</em>.log</span></span>  
<span data-ttu-id="5277e-171">记录 MBAM 安装和 MBAM 服务器功能安装期间所执行的操作。</span><span class="sxs-lookup"><span data-stu-id="5277e-171">Logs the actions taken during MBAM Setup and MBAM Server Feature installation.</span></span>

<a href="" id="installcompliancedatabase-log"></a><span data-ttu-id="5277e-172">InstallComplianceDatabase</span><span class="sxs-lookup"><span data-stu-id="5277e-172">InstallComplianceDatabase.log</span></span>  
<span data-ttu-id="5277e-173">记录创建 MBAM 合规性和审核数据库设置所执行的操作。</span><span class="sxs-lookup"><span data-stu-id="5277e-173">Logs actions taken to create the MBAM Compliance and Audit Database setup.</span></span>

<a href="" id="installkeycompliancedatabase-log"></a><span data-ttu-id="5277e-174">InstallKeyComplianceDatabase</span><span class="sxs-lookup"><span data-stu-id="5277e-174">InstallKeyComplianceDatabase.log</span></span>  
<span data-ttu-id="5277e-175">记录创建 MBAM 恢复数据库所执行的操作。</span><span class="sxs-lookup"><span data-stu-id="5277e-175">Logs actions taken to create the MBAM Recovery Database.</span></span>

<a href="" id="addhelpdeskdbauditusers-log"></a><span data-ttu-id="5277e-176">AddHelpDeskDbAuditUsers</span><span class="sxs-lookup"><span data-stu-id="5277e-176">AddHelpDeskDbAuditUsers.log</span></span>  
<span data-ttu-id="5277e-177">记录在 MBAM 合规性和审核数据库上创建 SQL Server 登录并针对报表向数据库授权支持人员 web 服务所执行的操作。</span><span class="sxs-lookup"><span data-stu-id="5277e-177">Logs actions taken to create the SQL Server logins on the MBAM Compliance and Audit database and authorize the HelpDesk web service to the database for reports.</span></span>

<a href="" id="addhelpdeskdbusers-log"></a><span data-ttu-id="5277e-178">AddHelpDeskDbUsers</span><span class="sxs-lookup"><span data-stu-id="5277e-178">AddHelpDeskDbUsers.log</span></span>  
<span data-ttu-id="5277e-179">记录对用于密钥恢复的数据库进行授权 web 服务所需的操作，并创建到 MBAM 恢复数据库的登录。</span><span class="sxs-lookup"><span data-stu-id="5277e-179">Logs actions taken to authorize web services to database for key recovery and create logins to the MBAM Recovery Database.</span></span>

<a href="" id="addkeycompliancedbusers-log"></a><span data-ttu-id="5277e-180">AddKeyComplianceDbUsers</span><span class="sxs-lookup"><span data-stu-id="5277e-180">AddKeyComplianceDbUsers.log</span></span>  
<span data-ttu-id="5277e-181">记录授权 web 服务以 MBAM 合规性和审核数据库以实现合规性报告所执行的操作。</span><span class="sxs-lookup"><span data-stu-id="5277e-181">Logs actions taken to authorize web services to MBAM Compliance and Audit Database for compliance reporting.</span></span>

<a href="" id="addrecoveryandhardwaredbusers-log"></a><span data-ttu-id="5277e-182">AddRecoveryAndHardwareDbUsers</span><span class="sxs-lookup"><span data-stu-id="5277e-182">AddRecoveryAndHardwareDbUsers.log</span></span>  
<span data-ttu-id="5277e-183">记录用于将 web 服务授权到 MBAM 恢复数据库以执行密钥恢复的操作。</span><span class="sxs-lookup"><span data-stu-id="5277e-183">Logs actions taken to authorize web services to the MBAM Recovery database for key recovery.</span></span>

<span data-ttu-id="5277e-184">**注意** 为了获取其他 MBAM 安装日志文件，必须使用 msiexec 程序包和/L &lt; location 选项安装 MBAM &gt; 。</span><span class="sxs-lookup"><span data-stu-id="5277e-184">**Note** In order to obtain additional MBAM Setup log files, you have to install MBAM by using the msiexec package and the /L &lt;location&gt; option.</span></span> <span data-ttu-id="5277e-185">在指定位置创建日志文件。</span><span class="sxs-lookup"><span data-stu-id="5277e-185">Log files are created in the location specified.</span></span>

 

**<span data-ttu-id="5277e-186">MBAM 客户端安装程序日志文件</span><span class="sxs-lookup"><span data-stu-id="5277e-186">MBAM Client Setup log files</span></span>**

<a href="" id="msi-five-random-characters--log"></a><span data-ttu-id="5277e-187">MSI <em> &lt; 5 个随机字符 &gt; </em> 。日志</span><span class="sxs-lookup"><span data-stu-id="5277e-187">MSI<em>&lt;five random characters&gt;</em>.log</span></span>  
<span data-ttu-id="5277e-188">记录在 MBAM 客户端安装期间执行的操作。</span><span class="sxs-lookup"><span data-stu-id="5277e-188">Logs the actions taken during MBAM Client installation.</span></span>

## <a href="" id="---------mbam-database-tde-considerations"></a> <span data-ttu-id="5277e-189">MBAM 数据库 TDE 注意事项</span><span class="sxs-lookup"><span data-stu-id="5277e-189">MBAM Database TDE Considerations</span></span>


<span data-ttu-id="5277e-190">SQL Server 中可用的透明数据加密（TDE）功能是对将托管数据库功能 MBAM 的数据库实例的可选安装。</span><span class="sxs-lookup"><span data-stu-id="5277e-190">The transparent data encryption (TDE) feature that is available in SQL Server is an optional installation for the database instances that will host MBAM database features.</span></span>

<span data-ttu-id="5277e-191">通过 TDE，你可以执行实时、完整数据库级别的加密。</span><span class="sxs-lookup"><span data-stu-id="5277e-191">With TDE, you can perform real-time, full database-level encryption.</span></span> <span data-ttu-id="5277e-192">TDE 是批量加密的最佳选择，可满足法规遵从性或公司数据安全标准。</span><span class="sxs-lookup"><span data-stu-id="5277e-192">TDE is the optimal choice for bulk encryption to meet regulatory compliance or corporate data security standards.</span></span> <span data-ttu-id="5277e-193">TDE 适用于文件级别，它类似于两个 Windows 功能：加密文件系统（EFS）和 BitLocker 驱动器加密，这两者也会对硬盘上的数据进行加密。</span><span class="sxs-lookup"><span data-stu-id="5277e-193">TDE works at the file level, which is similar to two Windows features: the Encrypting File System (EFS) and BitLocker Drive Encryption, both of which also encrypt data on the hard drive.</span></span> <span data-ttu-id="5277e-194">TDE 不会替换单元级加密、EFS 或 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="5277e-194">TDE does not replace cell-level encryption, EFS, or BitLocker.</span></span>

<span data-ttu-id="5277e-195">在数据库上启用 TDE 时，将加密所有备份。</span><span class="sxs-lookup"><span data-stu-id="5277e-195">When TDE is enabled on a database, all backups are encrypted.</span></span> <span data-ttu-id="5277e-196">因此，必须特别注意才能确保使用数据库备份对用于保护数据库加密密钥的证书进行备份和维护。</span><span class="sxs-lookup"><span data-stu-id="5277e-196">Thus, special care must be taken to ensure that the certificate that was used to protect the database encryption key is backed up and maintained with the database backup.</span></span> <span data-ttu-id="5277e-197">如果此证书（或证书）丢失，则数据将不可读。</span><span class="sxs-lookup"><span data-stu-id="5277e-197">If this certificate (or certificates) is lost, the data will be unreadable.</span></span> <span data-ttu-id="5277e-198">备份证书和数据库。</span><span class="sxs-lookup"><span data-stu-id="5277e-198">Back up the certificate along with the database.</span></span> <span data-ttu-id="5277e-199">每个证书备份都应具有两个文件。</span><span class="sxs-lookup"><span data-stu-id="5277e-199">Each certificate backup should have two files.</span></span> <span data-ttu-id="5277e-200">应存档这两个文件（最好从数据库备份文件中的安全）进行存档。</span><span class="sxs-lookup"><span data-stu-id="5277e-200">Both of these files should be archived (ideally separately from the database backup file for security).</span></span> <span data-ttu-id="5277e-201">您也可以考虑使用可扩展密钥管理（EKM）功能（请参阅可扩展密钥管理）存储和维护用于 TDE 的密钥。</span><span class="sxs-lookup"><span data-stu-id="5277e-201">You can alternatively consider using the extensible key management (EKM) feature (see Extensible Key Management) for storage and maintenance of keys used for TDE.</span></span>

<span data-ttu-id="5277e-202">有关如何为 MBAM 数据库实例启用 TDE 的示例，请参阅[评估 MBAM 2.0](evaluating-mbam-20-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="5277e-202">For an example of how to enable TDE for MBAM database instances, see [Evaluating MBAM 2.0](evaluating-mbam-20-mbam-2.md).</span></span>

<span data-ttu-id="5277e-203">有关 SQLServer 2008 中的 TDE 的详细信息，请参阅[SQL Server 加密]( https://go.microsoft.com/fwlink/?LinkId=299883)。</span><span class="sxs-lookup"><span data-stu-id="5277e-203">For more information about TDE in SQLServer 2008, see [SQL Server Encryption]( https://go.microsoft.com/fwlink/?LinkId=299883).</span></span>

## <span data-ttu-id="5277e-204">相关主题</span><span class="sxs-lookup"><span data-stu-id="5277e-204">Related topics</span></span>


[<span data-ttu-id="5277e-205">MBAM 2.0 的安全和隐私</span><span class="sxs-lookup"><span data-stu-id="5277e-205">Security and Privacy for MBAM 2.0</span></span>](security-and-privacy-for-mbam-20-mbam-2.md)

 

 





