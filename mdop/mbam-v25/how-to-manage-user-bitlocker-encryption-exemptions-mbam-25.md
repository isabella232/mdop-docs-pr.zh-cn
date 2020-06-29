---
title: 如何管理用户 BitLocker 加密免除
description: 如何管理用户 BitLocker 加密免除
author: dansimp
ms.assetid: f582ab82-5bb5-4cd3-ad7c-483240533cf9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c4224a0fb6d905c2362659efe7cf05e16756f7c0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804039"
---
# <span data-ttu-id="e77b8-103">如何管理用户 BitLocker 加密免除</span><span class="sxs-lookup"><span data-stu-id="e77b8-103">How to Manage User BitLocker Encryption Exemptions</span></span>


<span data-ttu-id="e77b8-104">Microsoft BitLocker 管理和监视（MBAM）使你能够从 BitLocker 驱动器加密要求中免除用户。</span><span class="sxs-lookup"><span data-stu-id="e77b8-104">Microsoft BitLocker Administration and Monitoring (MBAM) enables you to exempt users from BitLocker Drive Encryption requirements.</span></span>

<span data-ttu-id="e77b8-105">若要从 BitLocker 保护中免除用户，您必须：</span><span class="sxs-lookup"><span data-stu-id="e77b8-105">To exempt users from BitLocker protection, you have to:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e77b8-106">任务</span><span class="sxs-lookup"><span data-stu-id="e77b8-106">Task</span></span></th>
<th align="left"><span data-ttu-id="e77b8-107">详细信息</span><span class="sxs-lookup"><span data-stu-id="e77b8-107">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e77b8-108">创建支持被免除的用户的基础结构。</span><span class="sxs-lookup"><span data-stu-id="e77b8-108">Create an infrastructure to support exempted users.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e77b8-109">此基础结构的示例包括向用户提供可用于请求豁免的联系人电话号码、网页或邮件地址。</span><span class="sxs-lookup"><span data-stu-id="e77b8-109">Examples of this infrastructure include providing users with a contact telephone number, webpage, or mailing address that they can use to request an exemption.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e77b8-110">将被免除的用户添加到为被免除的用户专门配置的组策略对象的安全组。</span><span class="sxs-lookup"><span data-stu-id="e77b8-110">Add the exempted user to a security group for a Group Policy Object that is configured specifically for exempted users.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e77b8-111">当此安全组的成员登录到计算机时，用户的组策略设置从 BitLocker 保护 exempts 用户。</span><span class="sxs-lookup"><span data-stu-id="e77b8-111">When members of this security group sign in to a computer, the user’s Group Policy setting exempts the user from BitLocker protection.</span></span> <span data-ttu-id="e77b8-112">用户的组策略设置将覆盖计算机策略，并且计算机将保持不受 BitLocker 加密的阻止。</span><span class="sxs-lookup"><span data-stu-id="e77b8-112">The user’s Group Policy setting overwrites the computer policy, and the computer will remain exempt from BitLocker encryption.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="e77b8-113">注意</span><span class="sxs-lookup"><span data-stu-id="e77b8-113">Note</span></span></strong><br/><p><span data-ttu-id="e77b8-114">如果计算机已受 BitLocker 保护且用户已被免除，MBAM 不会制定加密策略。</span><span class="sxs-lookup"><span data-stu-id="e77b8-114">MBAM does not enact the encryption policy if the computer is already BitLocker-protected and the user is exempted.</span></span> <span data-ttu-id="e77b8-115">但是，如果其他不是加密策略的用户登录到计算机，则会进行加密。</span><span class="sxs-lookup"><span data-stu-id="e77b8-115">However, if another user who is not exempt from the encryption policy signs in to the computer, encryption will take place.</span></span></p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



<span data-ttu-id="e77b8-116">以下步骤介绍最终用户通过 MBAM 客户端或通过组织使用的任何进程请求来自 BitLocker 驱动器加密豁免进程的豁免时发生的情况。</span><span class="sxs-lookup"><span data-stu-id="e77b8-116">The following steps describe what occurs when end users request an exemption from the BitLocker Drive Encryption exemption process through the MBAM Client or through whatever process your organization uses.</span></span> <span data-ttu-id="e77b8-117">必须将 MBAM 组策略设置配置为允许最终用户从 BitLocker 驱动器加密中请求豁免。</span><span class="sxs-lookup"><span data-stu-id="e77b8-117">You must configure MBAM Group Policy settings to allow end users to request an exemption from BitLocker Drive Encryption.</span></span>

1.  <span data-ttu-id="e77b8-118">当最终用户登录到需要加密的计算机时，他们将收到一则通知，告知其计算机将被加密。</span><span class="sxs-lookup"><span data-stu-id="e77b8-118">When end users sign in to a computer that is required to be encrypted, they receive a notification that their computer is going to be encrypted.</span></span> <span data-ttu-id="e77b8-119">他们可以通过选择 "**推迟**" 来选择 "**请求豁免**" 并推迟加密，或者可以选择 "**开始加密**" 以接受 BitLocker 加密。</span><span class="sxs-lookup"><span data-stu-id="e77b8-119">They can select **Request Exemption** and postpone the encryption by selecting **Postpone**, or they can select **Start Encryption** to accept the BitLocker encryption.</span></span>

    **<span data-ttu-id="e77b8-120">注意</span><span class="sxs-lookup"><span data-stu-id="e77b8-120">Note</span></span>**  
    <span data-ttu-id="e77b8-121">选择 "**请求免除**" 将推迟 BitLocker 保护，直到用户豁免策略中设置的最长时间。</span><span class="sxs-lookup"><span data-stu-id="e77b8-121">Selecting **Request Exemption** postpones the BitLocker protection until the maximum time that is set in the User Exemption Policy.</span></span>



2.  <span data-ttu-id="e77b8-122">如果最终用户选择 "**请求豁免**"，则会收到通知，告知他们联系组织的 BitLocker 管理组。</span><span class="sxs-lookup"><span data-stu-id="e77b8-122">If end users select **Request Exemption**, they receive a notification telling them to contact the organization’s BitLocker administration group.</span></span> <span data-ttu-id="e77b8-123">根据配置**用户豁免策略**的配置方式，向用户提供以下一种或多种联系方法：</span><span class="sxs-lookup"><span data-stu-id="e77b8-123">Depending on how the **Configure User Exemption Policy** is configured, users are provided with one or more of the following contact methods:</span></span>

    -   <span data-ttu-id="e77b8-124">电话号码</span><span class="sxs-lookup"><span data-stu-id="e77b8-124">Phone number</span></span>

    -   <span data-ttu-id="e77b8-125">网页 URL</span><span class="sxs-lookup"><span data-stu-id="e77b8-125">Webpage URL</span></span>

    -   <span data-ttu-id="e77b8-126">通讯地址</span><span class="sxs-lookup"><span data-stu-id="e77b8-126">Mailing address</span></span>

3.  <span data-ttu-id="e77b8-127">收到免除请求后，MBAM 管理员决定是否将用户添加到 BitLocker 豁免 Active Directory 域服务（AD DS）组。</span><span class="sxs-lookup"><span data-stu-id="e77b8-127">After the exemption request is received, the MBAM administrator decides whether to add the user to the BitLocker Exemption Active Directory Domain Services (AD DS) group.</span></span>

4.  <span data-ttu-id="e77b8-128">最终用户提交免除请求后，MBAM 客户端会将该用户报告为 "临时豁免"。</span><span class="sxs-lookup"><span data-stu-id="e77b8-128">After an end user submits an exemption request, the MBAM Client reports the user as “Temporarily exempt.”</span></span> <span data-ttu-id="e77b8-129">然后，客户端将等待指定的天数（IT 管理员配置的天数），然后再次检查计算机的合规性。</span><span class="sxs-lookup"><span data-stu-id="e77b8-129">The Client then waits a specified number of days, which IT administrators configure, before it checks the computer’s compliance again.</span></span> <span data-ttu-id="e77b8-130">如果 MBAM 管理员拒绝免除请求，将停用 "免除请求" 选项，这将阻止用户再次请求例外。</span><span class="sxs-lookup"><span data-stu-id="e77b8-130">If the MBAM administrator rejects the exemption request, the exemption request option is deactivated, which prevents the user from requesting the exemption again.</span></span>

<span data-ttu-id="e77b8-131">Microsoft BitLocker 管理和监视（MBAM）使你能够从 BitLocker 驱动器加密要求中免除用户。</span><span class="sxs-lookup"><span data-stu-id="e77b8-131">Microsoft BitLocker Administration and Monitoring (MBAM) enables you to exempt users from BitLocker Drive Encryption requirements.</span></span>

<span data-ttu-id="e77b8-132">若要从 BitLocker 保护中免除用户，您必须：</span><span class="sxs-lookup"><span data-stu-id="e77b8-132">To exempt users from BitLocker protection, you have to:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e77b8-133">任务</span><span class="sxs-lookup"><span data-stu-id="e77b8-133">Task</span></span></th>
<th align="left"><span data-ttu-id="e77b8-134">详细信息</span><span class="sxs-lookup"><span data-stu-id="e77b8-134">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e77b8-135">创建支持被免除的用户的基础结构。</span><span class="sxs-lookup"><span data-stu-id="e77b8-135">Create an infrastructure to support exempted users.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e77b8-136">此基础结构的示例包括向用户提供可用于请求豁免的联系人电话号码、网页或邮件地址。</span><span class="sxs-lookup"><span data-stu-id="e77b8-136">Examples of this infrastructure include providing users with a contact telephone number, webpage, or mailing address that they can use to request an exemption.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e77b8-137">将被免除的用户添加到为被免除的用户专门配置的组策略对象的安全组。</span><span class="sxs-lookup"><span data-stu-id="e77b8-137">Add the exempted user to a security group for a Group Policy Object that is configured specifically for exempted users.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e77b8-138">当此安全组的成员登录到计算机时，用户的组策略设置从 BitLocker 保护 exempts 用户。</span><span class="sxs-lookup"><span data-stu-id="e77b8-138">When members of this security group sign in to a computer, the user’s Group Policy setting exempts the user from BitLocker protection.</span></span> <span data-ttu-id="e77b8-139">用户的组策略设置将覆盖计算机策略，并且计算机将保持不受 BitLocker 加密的阻止。</span><span class="sxs-lookup"><span data-stu-id="e77b8-139">The user’s Group Policy setting overwrites the computer policy, and the computer will remain exempt from BitLocker encryption.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="e77b8-140">注意</span><span class="sxs-lookup"><span data-stu-id="e77b8-140">Note</span></span></strong><br/><p><span data-ttu-id="e77b8-141">如果计算机已受 BitLocker 保护，则用户豁免策略不起作用。</span><span class="sxs-lookup"><span data-stu-id="e77b8-141">If the computer is already BitLocker-protected, the User Exemption Policy has no effect.</span></span> <span data-ttu-id="e77b8-142">此外，如果其他用户登录的计算机不是加密策略的例外，将进行加密。</span><span class="sxs-lookup"><span data-stu-id="e77b8-142">In addition, if another user signs in to a computer that is not exempt from the encryption policy, encryption will take place.</span></span></p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



<span data-ttu-id="e77b8-143">以下步骤介绍最终用户通过 MBAM 客户端或通过组织使用的任何进程请求来自 BitLocker 驱动器加密豁免进程的豁免时发生的情况。</span><span class="sxs-lookup"><span data-stu-id="e77b8-143">The following steps describe what occurs when end users request an exemption from the BitLocker Drive Encryption exemption process through the MBAM Client or through whatever process your organization uses.</span></span> <span data-ttu-id="e77b8-144">必须将 MBAM 组策略设置配置为允许最终用户从 BitLocker 驱动器加密中请求豁免。</span><span class="sxs-lookup"><span data-stu-id="e77b8-144">You must configure MBAM Group Policy settings to allow end users to request an exemption from BitLocker Drive Encryption.</span></span>

1.  <span data-ttu-id="e77b8-145">当最终用户登录到需要加密的计算机时，他们将收到一则通知，告知其计算机将被加密。</span><span class="sxs-lookup"><span data-stu-id="e77b8-145">When end users sign in to a computer that is required to be encrypted, they receive a notification that their computer is going to be encrypted.</span></span> <span data-ttu-id="e77b8-146">他们可以通过选择 "**推迟**" 来选择 "**请求豁免**" 并推迟加密，或者可以选择 "**开始加密**" 以接受 BitLocker 加密。</span><span class="sxs-lookup"><span data-stu-id="e77b8-146">They can select **Request Exemption** and postpone the encryption by selecting **Postpone**, or they can select **Start Encryption** to accept the BitLocker encryption.</span></span>

    **<span data-ttu-id="e77b8-147">注意</span><span class="sxs-lookup"><span data-stu-id="e77b8-147">Note</span></span>**  
    <span data-ttu-id="e77b8-148">选择 "**请求免除**" 将推迟 BitLocker 保护，直到用户豁免策略中设置的最长时间。</span><span class="sxs-lookup"><span data-stu-id="e77b8-148">Selecting **Request Exemption** postpones the BitLocker protection until the maximum time that is set in the User Exemption Policy.</span></span>



2.  <span data-ttu-id="e77b8-149">如果最终用户选择 "**请求豁免**"，则会收到通知，告知他们联系组织的 BitLocker 管理组。</span><span class="sxs-lookup"><span data-stu-id="e77b8-149">If end users select **Request Exemption**, they receive a notification telling them to contact the organization’s BitLocker administration group.</span></span> <span data-ttu-id="e77b8-150">根据配置**用户豁免策略**的配置方式，向用户提供以下一种或多种联系方法：</span><span class="sxs-lookup"><span data-stu-id="e77b8-150">Depending on how the **Configure User Exemption Policy** is configured, users are provided with one or more of the following contact methods:</span></span>

    -   <span data-ttu-id="e77b8-151">电话号码</span><span class="sxs-lookup"><span data-stu-id="e77b8-151">Phone number</span></span>

    -   <span data-ttu-id="e77b8-152">网页 URL</span><span class="sxs-lookup"><span data-stu-id="e77b8-152">Webpage URL</span></span>

    -   <span data-ttu-id="e77b8-153">通讯地址</span><span class="sxs-lookup"><span data-stu-id="e77b8-153">Mailing address</span></span>

3.  <span data-ttu-id="e77b8-154">收到免除请求后，MBAM 管理员决定是否将用户添加到 BitLocker 豁免 Active Directory 域服务（AD DS）组。</span><span class="sxs-lookup"><span data-stu-id="e77b8-154">After the exemption request is received, the MBAM administrator decides whether to add the user to the BitLocker Exemption Active Directory Domain Services (AD DS) group.</span></span>

4.  <span data-ttu-id="e77b8-155">最终用户提交免除请求后，MBAM 客户端会将该用户报告为 "临时豁免"。</span><span class="sxs-lookup"><span data-stu-id="e77b8-155">After an end user submits an exemption request, the MBAM Client reports the user as “Temporarily exempt.”</span></span> <span data-ttu-id="e77b8-156">然后，客户端将等待指定的天数（IT 管理员配置的天数），然后再次检查计算机的合规性。</span><span class="sxs-lookup"><span data-stu-id="e77b8-156">The Client then waits a specified number of days, which IT administrators configure, before it checks the computer’s compliance again.</span></span> <span data-ttu-id="e77b8-157">如果 MBAM 管理员拒绝免除请求，将停用 "免除请求" 选项，这将阻止用户再次请求例外。</span><span class="sxs-lookup"><span data-stu-id="e77b8-157">If the MBAM administrator rejects the exemption request, the exemption request option is deactivated, which prevents the user from requesting the exemption again.</span></span>

**<span data-ttu-id="e77b8-158">从 BitLocker 驱动器加密中免除用户</span><span class="sxs-lookup"><span data-stu-id="e77b8-158">To exempt a user from BitLocker Drive Encryption</span></span>**

1.  <span data-ttu-id="e77b8-159">创建将用于管理来自 BitLocker 加密要求的用户免除的 AD DS 安全组。</span><span class="sxs-lookup"><span data-stu-id="e77b8-159">Create an AD DS security group that will be used to manage user exemptions from BitLocker encryption requirements.</span></span>

2.  <span data-ttu-id="e77b8-160">使用 Microsoft BitLocker 管理和监视组策略模板创建组策略对象。</span><span class="sxs-lookup"><span data-stu-id="e77b8-160">Create a Group Policy Object by using the Microsoft BitLocker Administration and Monitoring Group Policy Templates.</span></span>

3.  <span data-ttu-id="e77b8-161">将组策略对象与您在上一步中创建的 AD DS 组相关联。</span><span class="sxs-lookup"><span data-stu-id="e77b8-161">Associate the Group Policy Object with the AD DS group that you created in the previous step.</span></span> <span data-ttu-id="e77b8-162">豁免用户的策略设置位于： **UserConfiguration** &gt; **管理模板** &gt; **Windows 组件** &gt; **MDOP MBAM （BitLocker Management）**。</span><span class="sxs-lookup"><span data-stu-id="e77b8-162">The policy settings to exempt users are located at: **UserConfiguration** &gt; **Administrative Templates** &gt; **Windows Components** &gt; **MDOP MBAM (BitLocker Management)**.</span></span>

4.  <span data-ttu-id="e77b8-163">对于为 BitLocker 免除的用户创建的安全组，请添加请求豁免的用户的姓名。</span><span class="sxs-lookup"><span data-stu-id="e77b8-163">To the security group you created for BitLocker exempted users, add the names of the users who are requesting an exemption.</span></span>

    <span data-ttu-id="e77b8-164">当用户登录由 BitLocker 控制的计算机时，MBAM 客户端会检查用户豁免策略设置。</span><span class="sxs-lookup"><span data-stu-id="e77b8-164">When a user signs in to a computer controlled by BitLocker, the MBAM Client checks the User Exemption Policy setting.</span></span> <span data-ttu-id="e77b8-165">如果计算机已加密，则不会暂停 BitLocker 保护。</span><span class="sxs-lookup"><span data-stu-id="e77b8-165">If the computer is already encrypted, BitLocker protection is not suspended.</span></span> <span data-ttu-id="e77b8-166">如果计算机未加密，则 MBAM 不会提示用户进行加密。</span><span class="sxs-lookup"><span data-stu-id="e77b8-166">If the computer is not encrypted, MBAM does not prompt the user to encrypt.</span></span>

    **<span data-ttu-id="e77b8-167">重要提示</span><span class="sxs-lookup"><span data-stu-id="e77b8-167">Important</span></span>**  
    <span data-ttu-id="e77b8-168">使用 BitLocker 用户例外时，共享计算机方案需要特殊考虑。</span><span class="sxs-lookup"><span data-stu-id="e77b8-168">Shared computer scenarios require special consideration when you are using BitLocker user exemptions.</span></span> <span data-ttu-id="e77b8-169">如果非豁免用户登录与豁免用户共享的计算机，则该计算机可能已加密。</span><span class="sxs-lookup"><span data-stu-id="e77b8-169">If a non-exempt user signs in to a computer that is shared with an exempt user, the computer may be encrypted.</span></span>




## <span data-ttu-id="e77b8-170">相关主题</span><span class="sxs-lookup"><span data-stu-id="e77b8-170">Related topics</span></span>


[<span data-ttu-id="e77b8-171">管理 MBAM 2.5 功能</span><span class="sxs-lookup"><span data-stu-id="e77b8-171">Administering MBAM 2.5 Features</span></span>](administering-mbam-25-features.md)

[<span data-ttu-id="e77b8-172">规划 MBAM 2.5 组策略要求</span><span class="sxs-lookup"><span data-stu-id="e77b8-172">Planning for MBAM 2.5 Group Policy Requirements</span></span>](planning-for-mbam-25-group-policy-requirements.md)




## <span data-ttu-id="e77b8-173">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="e77b8-173">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="e77b8-174">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="e77b8-174">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="e77b8-175">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="e77b8-175">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>




