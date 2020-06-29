---
title: MBAM 1.0 的安全注意事项
description: MBAM 1.0 的安全注意事项
author: dansimp
ms.assetid: 5e1c8b8c-235b-4a92-8b0b-da50dca17353
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: b06c343c8193293dde91bc7af2541f35f332d261
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803919"
---
# <span data-ttu-id="99296-103">MBAM 1.0 的安全注意事项</span><span class="sxs-lookup"><span data-stu-id="99296-103">Security Considerations for MBAM 1.0</span></span>


<span data-ttu-id="99296-104">本主题包含帐户和组、日志文件以及有关 Microsoft BitLocker 管理和监视的其他与安全相关的注意事项（MBAM）的简要概述。</span><span class="sxs-lookup"><span data-stu-id="99296-104">This topic contains a brief overview of the accounts and groups, log files, and other security-related considerations for Microsoft BitLocker Administration and Monitoring (MBAM).</span></span> <span data-ttu-id="99296-105">有关详细信息，请访问本文中的链接。</span><span class="sxs-lookup"><span data-stu-id="99296-105">For more information, follow the links in this article.</span></span>

## <span data-ttu-id="99296-106">常规安全注意事项</span><span class="sxs-lookup"><span data-stu-id="99296-106">General security considerations</span></span>


**<span data-ttu-id="99296-107">了解安全风险。</span><span class="sxs-lookup"><span data-stu-id="99296-107">Understand the security risks.</span></span>** <span data-ttu-id="99296-108">MBAM 最严重的风险是，未经授权的用户可能会被未经授权的用户劫持，这样就可以在 MBAM 客户端上重新配置 BitLocker 加密和获取 BitLocker 加密密钥数据。</span><span class="sxs-lookup"><span data-stu-id="99296-108">The most serious risk to MBAM is that its functionality could be hijacked by an unauthorized user who could then reconfigure BitLocker encryption and gain BitLocker encryption key data on MBAM Clients.</span></span> <span data-ttu-id="99296-109">但是，由于拒绝服务攻击，MBAM 功能在短时间内丢失通常不会产生灾难性影响。</span><span class="sxs-lookup"><span data-stu-id="99296-109">However, the loss of MBAM functionality for a short period of time due to a denial-of-service attack would not generally have a catastrophic impact.</span></span>

<span data-ttu-id="99296-110">**确保计算机的物理安全**。</span><span class="sxs-lookup"><span data-stu-id="99296-110">**Physically secure your computers**.</span></span> <span data-ttu-id="99296-111">安全性不完整，没有物理安全。</span><span class="sxs-lookup"><span data-stu-id="99296-111">Security is incomplete without physical security.</span></span> <span data-ttu-id="99296-112">对 MBAM 服务器具有物理访问权限的任何人都可能会攻击整个客户群。</span><span class="sxs-lookup"><span data-stu-id="99296-112">Anyone with physical access to an MBAM Server could potentially attack the entire client base.</span></span> <span data-ttu-id="99296-113">任何潜在的物理攻击都必须被视为高风险并相应地缓解。</span><span class="sxs-lookup"><span data-stu-id="99296-113">Any potential physical attacks must be considered high risk and mitigated appropriately.</span></span> <span data-ttu-id="99296-114">MBAM 服务器应存储在具有可控访问权限的物理安全的服务器机房中。</span><span class="sxs-lookup"><span data-stu-id="99296-114">MBAM servers should be stored in a physically secure server room with controlled access.</span></span> <span data-ttu-id="99296-115">通过让操作系统锁定计算机，或使用安全的屏幕保护程序，确保管理员不在物理上显示这些计算机。</span><span class="sxs-lookup"><span data-stu-id="99296-115">Secure these computers when administrators are not physically present by having the operating system lock the computer, or by using a secured screen saver.</span></span>

<span data-ttu-id="99296-116">**对所有计算机应用最新的安全更新**。</span><span class="sxs-lookup"><span data-stu-id="99296-116">**Apply the most recent security updates to all computers**.</span></span> <span data-ttu-id="99296-117">通过订阅安全通知服务（），随时了解操作系统、Microsoft SQL Server 和 MBAM 的新更新 <https://go.microsoft.com/fwlink/p/?LinkId=28819> 。</span><span class="sxs-lookup"><span data-stu-id="99296-117">Stay informed about new updates for operating systems, Microsoft SQL Server, and MBAM by subscribing to the Security Notification service (<https://go.microsoft.com/fwlink/p/?LinkId=28819>).</span></span>

<span data-ttu-id="99296-118">**使用强密码或密码短语**。</span><span class="sxs-lookup"><span data-stu-id="99296-118">**Use strong passwords or pass phrases**.</span></span> <span data-ttu-id="99296-119">对于所有 MBAM 和 MBAM 管理员帐户，请始终使用具有15个或更多字符的强密码。</span><span class="sxs-lookup"><span data-stu-id="99296-119">Always use strong passwords with 15 or more characters for all MBAM and MBAM administrator accounts.</span></span> <span data-ttu-id="99296-120">千万不要使用空白密码。</span><span class="sxs-lookup"><span data-stu-id="99296-120">Never use blank passwords.</span></span> <span data-ttu-id="99296-121">有关密码概念的详细信息，请参阅 TechNet 上的 "帐户密码和策略" 白皮书（ <https://go.microsoft.com/fwlink/p/?LinkId=30009> ）。</span><span class="sxs-lookup"><span data-stu-id="99296-121">For more information about password concepts, see the “Account Passwords and Policies” white paper on TechNet (<https://go.microsoft.com/fwlink/p/?LinkId=30009>).</span></span>

## <span data-ttu-id="99296-122">MBAM 中的帐户和组</span><span class="sxs-lookup"><span data-stu-id="99296-122">Accounts and Groups in MBAM</span></span>


<span data-ttu-id="99296-123">用户帐户管理的最佳做法是创建域全局组并向其添加用户帐户。</span><span class="sxs-lookup"><span data-stu-id="99296-123">A best practice for user account management is to create domain global groups and add user accounts to them.</span></span> <span data-ttu-id="99296-124">然后，将域全局帐户添加到 MBAM 服务器上必需的 MBAM 本地组。</span><span class="sxs-lookup"><span data-stu-id="99296-124">Then, add the domain global accounts to the necessary MBAM local groups on the MBAM Servers.</span></span>

### <span data-ttu-id="99296-125">ActiveDirectoryDomainServices 组</span><span class="sxs-lookup"><span data-stu-id="99296-125">ActiveDirectoryDomainServices Groups</span></span>

<span data-ttu-id="99296-126">MBAM 安装期间不会自动创建任何组。</span><span class="sxs-lookup"><span data-stu-id="99296-126">No groups are created automatically during MBAM Setup.</span></span> <span data-ttu-id="99296-127">但是，你应该创建以下 ActiveDirectoryDomainServices 全局组来管理 MBAM 操作。</span><span class="sxs-lookup"><span data-stu-id="99296-127">However, you should create the following ActiveDirectoryDomainServices global groups to manage MBAM operations.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="99296-128">组名称</span><span class="sxs-lookup"><span data-stu-id="99296-128">Group Name</span></span></th>
<th align="left"><span data-ttu-id="99296-129">详细信息</span><span class="sxs-lookup"><span data-stu-id="99296-129">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="99296-130">MBAM 高级帮助台用户</span><span class="sxs-lookup"><span data-stu-id="99296-130">MBAM Advanced Helpdesk Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="99296-131">创建此组以管理在 MBAM 设置期间创建的 MBAM 高级帮助台用户本地组的成员。</span><span class="sxs-lookup"><span data-stu-id="99296-131">Create this group to manage members of the MBAM Advanced Helpdesk Users local group that was created during MBAM Setup.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="99296-132">MBAM 合规性审核数据库访问</span><span class="sxs-lookup"><span data-stu-id="99296-132">MBAM Compliance Auditing DB Access</span></span></p></td>
<td align="left"><p><span data-ttu-id="99296-133">创建此组以管理在 MBAM 设置期间创建的 MBAM 合规性审核数据库 Access 本地组的成员。</span><span class="sxs-lookup"><span data-stu-id="99296-133">Create this group to manage members of the MBAM Compliance Auditing DB Access local group that was created during MBAM Setup.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="99296-134">MBAM 硬件用户</span><span class="sxs-lookup"><span data-stu-id="99296-134">MBAM Hardware Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="99296-135">创建此组以管理在 MBAM 设置期间创建的 MBAM 硬件用户本地组的成员。</span><span class="sxs-lookup"><span data-stu-id="99296-135">Create this group to manage members of the MBAM Hardware Users local group that was created during MBAM Setup.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="99296-136">MBAM 帮助台用户</span><span class="sxs-lookup"><span data-stu-id="99296-136">MBAM Helpdesk Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="99296-137">创建此组以管理在 MBAM 设置期间创建的 MBAM 帮助台用户本地组的成员。</span><span class="sxs-lookup"><span data-stu-id="99296-137">Create this group to manage members of the MBAM Helpdesk Users local group that was created during MBAM Setup.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="99296-138">MBAM 恢复和硬件 DB 访问</span><span class="sxs-lookup"><span data-stu-id="99296-138">MBAM Recovery and Hardware DB Access</span></span></p></td>
<td align="left"><p><span data-ttu-id="99296-139">创建此组以管理在 MBAM 设置期间创建的 MBAM 恢复和硬件数据库 Access 本地组的成员。</span><span class="sxs-lookup"><span data-stu-id="99296-139">Create this group to manage members of the MBAM Recovery and Hardware DB Access local group that was created during MBAM Setup.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="99296-140">MBAM 报表用户</span><span class="sxs-lookup"><span data-stu-id="99296-140">MBAM Report Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="99296-141">创建此组以管理在 MBAM 设置期间创建的 MBAM 报表用户本地组的成员。</span><span class="sxs-lookup"><span data-stu-id="99296-141">Create this group to manage members of the MBAM Report Users local group that was created during MBAM Setup.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="99296-142">MBAM 系统管理员</span><span class="sxs-lookup"><span data-stu-id="99296-142">MBAM System Administrators</span></span></p></td>
<td align="left"><p><span data-ttu-id="99296-143">创建此组以管理在 MBAM 设置期间创建的 MBAM 系统管理员本地组的成员。</span><span class="sxs-lookup"><span data-stu-id="99296-143">Create this group to manage members of the MBAM System Administrators local group that was created during MBAM Setup.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="99296-144">BitLocker 加密免除</span><span class="sxs-lookup"><span data-stu-id="99296-144">BitLocker Encryption Exemptions</span></span></p></td>
<td align="left"><p><span data-ttu-id="99296-145">创建此组以管理应从登录的计算机上开始免除 BitLocker 加密的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="99296-145">Create this group to manage user accounts that should be exempted from BitLocker encryption starting on computers that they log on to.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="99296-146">MBAM 服务器本地组</span><span class="sxs-lookup"><span data-stu-id="99296-146">MBAM Server Local Groups</span></span>

<span data-ttu-id="99296-147">MBAM 安装程序创建本地组以支持 MBAM 操作。</span><span class="sxs-lookup"><span data-stu-id="99296-147">MBAM Setup creates local groups to support MBAM operations.</span></span> <span data-ttu-id="99296-148">应将 ActiveDirectoryDomainServices 全局组添加到相应的 MBAM 本地组，以配置 MBAM 安全和数据访问权限。</span><span class="sxs-lookup"><span data-stu-id="99296-148">You should add the ActiveDirectoryDomainServices Global Groups to the appropriate MBAM local groups to configure MBAM security and data access permissions.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="99296-149">组名称</span><span class="sxs-lookup"><span data-stu-id="99296-149">Group Name</span></span></th>
<th align="left"><span data-ttu-id="99296-150">详细信息</span><span class="sxs-lookup"><span data-stu-id="99296-150">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="99296-151">MBAM 高级帮助台用户</span><span class="sxs-lookup"><span data-stu-id="99296-151">MBAM Advanced Helpdesk Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="99296-152">此组的成员已扩展对 Microsoft BitLocker 管理和监视的帮助台功能的访问权限。</span><span class="sxs-lookup"><span data-stu-id="99296-152">Members of this group have expanded access to the Helpdesk features of Microsoft BitLocker Administration and Monitoring.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="99296-153">MBAM 合规性审核数据库访问</span><span class="sxs-lookup"><span data-stu-id="99296-153">MBAM Compliance Auditing DB Access</span></span></p></td>
<td align="left"><p><span data-ttu-id="99296-154">此组包含有权访问 MBAM 合规性审核数据库的计算机。</span><span class="sxs-lookup"><span data-stu-id="99296-154">This group contains the machines that have access to the MBAM Compliance Auditing Database.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="99296-155">MBAM 硬件用户</span><span class="sxs-lookup"><span data-stu-id="99296-155">MBAM Hardware Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="99296-156">此组的成员可以访问 Microsoft BitLocker 管理和监视中的某些硬件功能功能。</span><span class="sxs-lookup"><span data-stu-id="99296-156">Members of this group have access to some of the Hardware Capability features from Microsoft BitLocker Administration and Monitoring.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="99296-157">MBAM 帮助台用户</span><span class="sxs-lookup"><span data-stu-id="99296-157">MBAM Helpdesk Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="99296-158">本组成员可以访问 Microsoft BitLocker 管理和监视中的某些帮助台功能。</span><span class="sxs-lookup"><span data-stu-id="99296-158">Members of this group have access to some of the Helpdesk features from Microsoft BitLocker Administration and Monitoring.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="99296-159">MBAM 恢复和硬件 DB 访问</span><span class="sxs-lookup"><span data-stu-id="99296-159">MBAM Recovery and Hardware DB Access</span></span></p></td>
<td align="left"><p><span data-ttu-id="99296-160">此组包含有权访问 MBAM 恢复和硬件数据库的计算机。</span><span class="sxs-lookup"><span data-stu-id="99296-160">This group contains the computers that have access to the MBAM Recovery and Hardware Database.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="99296-161">MBAM 报表用户</span><span class="sxs-lookup"><span data-stu-id="99296-161">MBAM Report Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="99296-162">本组成员可以访问 Microsoft BitLocker 管理和监视中的合规性和审核报告。</span><span class="sxs-lookup"><span data-stu-id="99296-162">Members of this group have access to the Compliance and Audit reports from Microsoft BitLocker Administration and Monitoring.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="99296-163">MBAM 系统管理员</span><span class="sxs-lookup"><span data-stu-id="99296-163">MBAM System Administrators</span></span></p></td>
<td align="left"><p><span data-ttu-id="99296-164">此组的成员具有 Microsoft BitLocker 管理和监视的所有功能的访问权限。</span><span class="sxs-lookup"><span data-stu-id="99296-164">Members of this group have access to all the features of Microsoft BitLocker Administration and Monitoring.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="99296-165">SSRS 报表访问帐户</span><span class="sxs-lookup"><span data-stu-id="99296-165">SSRS Reports Access Account</span></span>

<span data-ttu-id="99296-166">SQL Server Reporting Services （SSRS）报表服务帐户提供用于运行 SSRS 提供的 MBAM 报告的安全上下文。</span><span class="sxs-lookup"><span data-stu-id="99296-166">The SQL Server Reporting Services (SSRS) Reports Service Account provides the security context to run the MBAM reports available through SSRS.</span></span> <span data-ttu-id="99296-167">此帐户在 MBAM 安装期间配置。</span><span class="sxs-lookup"><span data-stu-id="99296-167">This account is configured during MBAM Setup.</span></span>

## <span data-ttu-id="99296-168">MBAM 日志文件</span><span class="sxs-lookup"><span data-stu-id="99296-168">MBAM Log Files</span></span>


<span data-ttu-id="99296-169">在 MBAM 设置期间，以下 MBAM 安装日志文件将在安装了该文件的用户的% temp% 文件夹中创建。</span><span class="sxs-lookup"><span data-stu-id="99296-169">During MBAM Setup, the following MBAM Setup log files are created in the %temp% folder of the user who installs the</span></span>

**<span data-ttu-id="99296-170">MBAM Server 安装程序日志文件</span><span class="sxs-lookup"><span data-stu-id="99296-170">MBAM Server Setup log files</span></span>**

<a href="" id="msi-five-random-characters--log"></a><span data-ttu-id="99296-171">MSI <em> &lt; 5 个随机字符 &gt; </em> 。日志</span><span class="sxs-lookup"><span data-stu-id="99296-171">MSI<em>&lt;five random characters&gt;</em>.log</span></span>  
<span data-ttu-id="99296-172">记录 MBAM 安装和 MBAM 服务器功能安装期间所执行的操作。</span><span class="sxs-lookup"><span data-stu-id="99296-172">Logs the actions taken during MBAM Setup and MBAM Server Feature installation.</span></span>

<a href="" id="installcompliancedatabase-log"></a><span data-ttu-id="99296-173">InstallComplianceDatabase</span><span class="sxs-lookup"><span data-stu-id="99296-173">InstallComplianceDatabase.log</span></span>  
<span data-ttu-id="99296-174">记录创建 MBAM 合规性状态数据库设置所执行的操作。</span><span class="sxs-lookup"><span data-stu-id="99296-174">Logs the actions taken to create the MBAM Compliance Status database setup.</span></span>

<a href="" id="installkeycompliancedatabase-log"></a><span data-ttu-id="99296-175">InstallKeyComplianceDatabase</span><span class="sxs-lookup"><span data-stu-id="99296-175">InstallKeyComplianceDatabase.log</span></span>  
<span data-ttu-id="99296-176">记录创建 MBAM 恢复和硬件数据库所执行的操作。</span><span class="sxs-lookup"><span data-stu-id="99296-176">Logs the actions taken to create the MBAM Recovery and Hardware database.</span></span>

<a href="" id="addhelpdeskdbauditusers-log"></a><span data-ttu-id="99296-177">AddHelpDeskDbAuditUsers</span><span class="sxs-lookup"><span data-stu-id="99296-177">AddHelpDeskDbAuditUsers.log</span></span>  
<span data-ttu-id="99296-178">记录在 MBAM 合规性状态数据库上创建 SQL Server 登录并针对报表向数据库授权支持人员 web 服务所执行的操作。</span><span class="sxs-lookup"><span data-stu-id="99296-178">Logs the actions taken to create the SQL Server logins on the MBAM Compliance Status database and authorize helpdesk web service to the database for reports.</span></span>

<a href="" id="addhelpdeskdbusers-log"></a><span data-ttu-id="99296-179">AddHelpDeskDbUsers</span><span class="sxs-lookup"><span data-stu-id="99296-179">AddHelpDeskDbUsers.log</span></span>  
<span data-ttu-id="99296-180">记录对用于密钥恢复的数据库进行授权 web 服务所执行的操作，并创建 MBAM 恢复和硬件数据库的登录。</span><span class="sxs-lookup"><span data-stu-id="99296-180">Logs the actions taken to authorize web services to database for key recovery and create logins to the MBAM Recovery and Hardware database.</span></span>

<a href="" id="addkeycompliancedbusers-log"></a><span data-ttu-id="99296-181">AddKeyComplianceDbUsers</span><span class="sxs-lookup"><span data-stu-id="99296-181">AddKeyComplianceDbUsers.log</span></span>  
<span data-ttu-id="99296-182">将授权 web 服务所执行的操作记录到符合性报告的 MBAM 合规性状态数据库中。</span><span class="sxs-lookup"><span data-stu-id="99296-182">Logs the actions taken to authorize web services to MBAM Compliance Status database for compliance reporting.</span></span>

<a href="" id="addrecoveryandhardwaredbusers-log"></a><span data-ttu-id="99296-183">AddRecoveryAndHardwareDbUsers</span><span class="sxs-lookup"><span data-stu-id="99296-183">AddRecoveryAndHardwareDbUsers.log</span></span>  
<span data-ttu-id="99296-184">记录授权 web 服务以 MBAM 恢复和硬件数据库进行密钥恢复所执行的操作。</span><span class="sxs-lookup"><span data-stu-id="99296-184">Logs the actions taken to authorize web services to MBAM Recovery and Hardware database for key recovery.</span></span>

<span data-ttu-id="99296-185">**注意** 为了获取其他 MBAM 安装日志文件，必须使用**msiexec**程序包和 **/l** Location 选项安装 Microsoft BitLocker 管理和监视 &lt; &gt; 。</span><span class="sxs-lookup"><span data-stu-id="99296-185">**Note** In order to obtain additional MBAM Setup log files, you must install Microsoft BitLocker Administration and Monitoring by using the **msiexec** package and the **/l** &lt;location&gt; option.</span></span> <span data-ttu-id="99296-186">在指定位置创建日志文件。</span><span class="sxs-lookup"><span data-stu-id="99296-186">Log files are created in the location specified.</span></span>

 

**<span data-ttu-id="99296-187">MBAM 客户端安装程序日志文件</span><span class="sxs-lookup"><span data-stu-id="99296-187">MBAM Client Setup log files</span></span>**

<a href="" id="msi-five-random-characters--log"></a><span data-ttu-id="99296-188">MSI <em> &lt; 5 个随机字符 &gt; </em> 。日志</span><span class="sxs-lookup"><span data-stu-id="99296-188">MSI<em>&lt;five random characters&gt;</em>.log</span></span>  
<span data-ttu-id="99296-189">记录在 MBAM 客户端安装期间执行的操作。</span><span class="sxs-lookup"><span data-stu-id="99296-189">Logs the actions taken during MBAM Client installation.</span></span>

## <span data-ttu-id="99296-190">MBAM 数据库 TDE 注意事项</span><span class="sxs-lookup"><span data-stu-id="99296-190">MBAM Database TDE considerations</span></span>


<span data-ttu-id="99296-191">SQL Server 2008 中可用的 "透明数据加密" （TDE）功能是将托管数据库功能的数据库实例的必需安装必备项。</span><span class="sxs-lookup"><span data-stu-id="99296-191">The Transparent Data Encryption (TDE) feature available in SQL Server 2008 is a required installation prerequisite for the database instances that will host MBAM database features.</span></span>

<span data-ttu-id="99296-192">通过 TDE，你可以执行实时、完整数据库级别的加密。</span><span class="sxs-lookup"><span data-stu-id="99296-192">With TDE, you can perform real-time, full database-level encryption.</span></span> <span data-ttu-id="99296-193">TDE 是一种非常合适的选项，可用于批量加密以满足合规性或公司数据安全标准。</span><span class="sxs-lookup"><span data-stu-id="99296-193">TDE is a well-suited choice for bulk encryption to meet regulatory compliance or corporate data security standards.</span></span> <span data-ttu-id="99296-194">TDE 适用于文件级别，它类似于两个 Windows 功能：加密文件系统（EFS）和 BitLocker 驱动器加密，这两者也会对硬盘上的数据进行加密。</span><span class="sxs-lookup"><span data-stu-id="99296-194">TDE works at the file level, which is similar to two Windows features: the Encrypting File System (EFS) and BitLocker Drive Encryption, both of which also encrypt data on the hard drive.</span></span> <span data-ttu-id="99296-195">TDE 不会替换单元级加密、EFS 或 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="99296-195">TDE does not replace cell-level encryption, EFS, or BitLocker.</span></span>

<span data-ttu-id="99296-196">在数据库上启用 TDE 时，将加密所有备份。</span><span class="sxs-lookup"><span data-stu-id="99296-196">When TDE is enabled on a database, all backups are encrypted.</span></span> <span data-ttu-id="99296-197">因此，必须特别注意才能确保使用数据库备份对用于保护数据库加密密钥（DEK）的证书进行备份和维护。</span><span class="sxs-lookup"><span data-stu-id="99296-197">Thus, special care must be taken to ensure that the certificate that was used to protect the Database Encryption Key (DEK) is backed up and maintained with the database backup.</span></span> <span data-ttu-id="99296-198">如果没有证书，数据将不可读。</span><span class="sxs-lookup"><span data-stu-id="99296-198">Without a certificate, the data will be unreadable.</span></span> <span data-ttu-id="99296-199">备份证书和数据库。</span><span class="sxs-lookup"><span data-stu-id="99296-199">Back up the certificate along with the database.</span></span> <span data-ttu-id="99296-200">每个证书备份都应具有两个文件;这两个文件都应存档。最好将它们与数据库备份文件分开存档，以确保安全。</span><span class="sxs-lookup"><span data-stu-id="99296-200">Each certificate backup should have two files; both of these files should be archived .It is best to archive them separately from the database backup file for security.</span></span>

<span data-ttu-id="99296-201">有关如何为 MBAM 数据库实例启用 TDE 的示例，请参阅[评估 MBAM 1.0](evaluating-mbam-10.md)。</span><span class="sxs-lookup"><span data-stu-id="99296-201">For an example of how to enable TDE for MBAM database instances, see [Evaluating MBAM 1.0](evaluating-mbam-10.md).</span></span>

<span data-ttu-id="99296-202">有关 SQLServer 2008 中的 TDE 的详细信息，请参阅[SQL Server 2008 企业版中的数据库加密](https://go.microsoft.com/fwlink/?LinkId=269703)。</span><span class="sxs-lookup"><span data-stu-id="99296-202">For more information about TDE in SQLServer 2008, see [Database Encryption in SQL Server 2008 Enterprise Edition](https://go.microsoft.com/fwlink/?LinkId=269703).</span></span>

## <span data-ttu-id="99296-203">相关主题</span><span class="sxs-lookup"><span data-stu-id="99296-203">Related topics</span></span>


[<span data-ttu-id="99296-204">MBAM 1.0 的安全和隐私</span><span class="sxs-lookup"><span data-stu-id="99296-204">Security and Privacy for MBAM 1.0</span></span>](security-and-privacy-for-mbam-10.md)

 

 





