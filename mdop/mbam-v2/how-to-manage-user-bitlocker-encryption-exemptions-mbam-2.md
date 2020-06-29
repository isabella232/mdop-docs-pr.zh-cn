---
title: 如何管理用户 BitLocker 加密免除
description: 如何管理用户 BitLocker 加密免除
author: dansimp
ms.assetid: 1bfd9d66-6a9a-4d0e-b54a-e5a6627f5ada
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4d5530701fd208d42dc1f6774fac11ee9ca2036b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803695"
---
# <span data-ttu-id="976f7-103">如何管理用户 BitLocker 加密免除</span><span class="sxs-lookup"><span data-stu-id="976f7-103">How to Manage User BitLocker Encryption Exemptions</span></span>


<span data-ttu-id="976f7-104">Microsoft BitLocker 管理和监视（MBAM）可用于通过 exempting 用户（如果存在不需要或希望其驱动器加密的用户）来管理 BitLocker 保护。</span><span class="sxs-lookup"><span data-stu-id="976f7-104">Microsoft BitLocker Administration and Monitoring (MBAM) can be used to manage BitLocker protection by exempting users if there are users who do not need or want their drives encrypted.</span></span>

<span data-ttu-id="976f7-105">若要从 BitLocker 保护中免除用户，组织将必须创建支持免除的用户的基础结构，例如向用户提供用于请求豁免的联系人电话号码、网页或通讯地址。</span><span class="sxs-lookup"><span data-stu-id="976f7-105">To exempt users from BitLocker protection, an organization will have to create an infrastructure to support exempted users, such as giving the user a contact telephone number, webpage, or mailing address to use to request an exemption.</span></span> <span data-ttu-id="976f7-106">此外，还必须将豁免用户添加到专为豁免用户创建的组策略对象的安全组。</span><span class="sxs-lookup"><span data-stu-id="976f7-106">Also, an exempt user will have to be added to a security group for a Group Policy Object that was created specifically for exempted users.</span></span> <span data-ttu-id="976f7-107">当此安全组的成员登录到计算机时，用户的组策略设置显示用户已被免除了 BitLocker 保护。</span><span class="sxs-lookup"><span data-stu-id="976f7-107">When members of this security group log on to a computer, the user’s Group Policy setting shows that the user is exempted from BitLocker protection.</span></span> <span data-ttu-id="976f7-108">用户的组策略设置将覆盖计算机策略，并且计算机将保持不受 BitLocker 加密的阻止。</span><span class="sxs-lookup"><span data-stu-id="976f7-108">The user’s Group Policy setting overwrites the computer policy, and the computer will remain exempt from BitLocker encryption.</span></span>

<span data-ttu-id="976f7-109">**注意** 如果计算机已受 BitLocker 保护，则用户豁免策略不起作用。</span><span class="sxs-lookup"><span data-stu-id="976f7-109">**Note** If the computer is already BitLocker-protected, the user exemption policy has no effect.</span></span>

 

<span data-ttu-id="976f7-110">下表显示了如何根据如何设置免除来应用 BitLocker 保护。</span><span class="sxs-lookup"><span data-stu-id="976f7-110">The following table shows how BitLocker protection is applied based on how exemptions are set.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="976f7-111">用户状态</span><span class="sxs-lookup"><span data-stu-id="976f7-111">User Status</span></span></th>
<th align="left"><span data-ttu-id="976f7-112">计算机未豁免</span><span class="sxs-lookup"><span data-stu-id="976f7-112">Computer Not Exempt</span></span></th>
<th align="left"><span data-ttu-id="976f7-113">计算机豁免</span><span class="sxs-lookup"><span data-stu-id="976f7-113">Computer Exempt</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="976f7-114">用户不豁免</span><span class="sxs-lookup"><span data-stu-id="976f7-114">User not exempt</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="976f7-115">在计算机上强制执行 BitLocker 保护</span><span class="sxs-lookup"><span data-stu-id="976f7-115">BitLocker protection is enforced on computer</span></span></p></td>
<td align="left"><p><span data-ttu-id="976f7-116">在计算机上未强制执行 BitLocker 保护</span><span class="sxs-lookup"><span data-stu-id="976f7-116">BitLocker protection is not enforced on computer</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="976f7-117">用户豁免</span><span class="sxs-lookup"><span data-stu-id="976f7-117">User exempt</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="976f7-118">在计算机上未强制执行 BitLocker 保护</span><span class="sxs-lookup"><span data-stu-id="976f7-118">BitLocker protection is not enforced on computer</span></span></p></td>
<td align="left"><p><span data-ttu-id="976f7-119">在计算机上未强制执行 BitLocker 保护</span><span class="sxs-lookup"><span data-stu-id="976f7-119">BitLocker protection is not enforced on computer</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="976f7-120">从 BitLocker 加密中免除用户</span><span class="sxs-lookup"><span data-stu-id="976f7-120">To exempt a user from BitLocker encryption</span></span>**

1.  <span data-ttu-id="976f7-121">创建将用于管理来自 BitLocker 加密要求的用户免除的 ActiveDirectoryDomainServices 安全组。</span><span class="sxs-lookup"><span data-stu-id="976f7-121">Create an ActiveDirectoryDomainServices security group that will be used to manage user exemptions from BitLocker encryption requirements.</span></span>

2.  <span data-ttu-id="976f7-122">使用 Microsoft BitLocker 管理和监视组策略模板创建组策略对象设置，并将其与您在上一步中创建的 Active Directory 组相关联。</span><span class="sxs-lookup"><span data-stu-id="976f7-122">Create a Group Policy Object setting by using the Microsoft BitLocker Administration and Monitoring Group Policy template and associate it with the Active Directory group that you created in the previous step.</span></span> <span data-ttu-id="976f7-123">可在**UserConfiguration\\Administrative Templates\\Windows COMPONENTS\\MDOP MBAM （BitLocker Management）** 下找到豁免用户的策略设置。</span><span class="sxs-lookup"><span data-stu-id="976f7-123">The policy settings to exempt users can be found under **UserConfiguration\\Administrative Templates\\Windows Components\\MDOP MBAM (BitLocker Management)**.</span></span>

3.  <span data-ttu-id="976f7-124">为 BitLocker 免除的用户创建安全组之后，将请求豁免的用户的名称添加到此群组。</span><span class="sxs-lookup"><span data-stu-id="976f7-124">After creating a security group for BitLocker-exempted users, add to this group the names of the users who are requesting an exemption.</span></span> <span data-ttu-id="976f7-125">当用户登录到由 BitLocker 控制的计算机时，MBAM 客户端将检查用户豁免策略设置，并根据用户是否属于 BitLocker 豁免安全组来暂停保护。</span><span class="sxs-lookup"><span data-stu-id="976f7-125">When users log on to a computer controlled by BitLocker, the MBAM client will check the User Exemption Policy setting and will suspend protection based on whether the user is part of the BitLocker exemption security group.</span></span>

    <span data-ttu-id="976f7-126">**重要提示** 使用用户例外时，共享计算机方案需要特殊考虑。</span><span class="sxs-lookup"><span data-stu-id="976f7-126">**Important** Shared computer scenarios require special consideration when using user exemptions.</span></span> <span data-ttu-id="976f7-127">如果非豁免用户登录到与豁免用户共享的计算机，则该计算机可能已加密。</span><span class="sxs-lookup"><span data-stu-id="976f7-127">If a non-exempt user logs on to a computer shared with an exempt user, the computer may be encrypted.</span></span>

     

**<span data-ttu-id="976f7-128">使用户能够向 BitLocker 加密请求豁免</span><span class="sxs-lookup"><span data-stu-id="976f7-128">To enable users to request an exemption from BitLocker encryption</span></span>**

1.  <span data-ttu-id="976f7-129">如果你已使用 MBAM 策略模板配置了用户豁免策略，则用户可以通过 MBAM 客户端请求 BitLocker 保护的豁免。</span><span class="sxs-lookup"><span data-stu-id="976f7-129">If you have configured user exemption policies by using the MBAM policy template, a user can request an exemption from BitLocker protection through the MBAM client.</span></span>

2.  <span data-ttu-id="976f7-130">当用户登录到需要加密的计算机时，他们将收到一则通知，告知其计算机将被加密。</span><span class="sxs-lookup"><span data-stu-id="976f7-130">When users log on to a computer that is required to be encrypted, they receive a notification that their computer is going to be encrypted.</span></span> <span data-ttu-id="976f7-131">他们可以选择 "**请求豁免** **"，** 然后通过选择 "开始"，然后选择 "**开始**" 接受 BitLocker 加密来推迟加密。</span><span class="sxs-lookup"><span data-stu-id="976f7-131">They can select **Request Exemption** and postpone the encryption by selecting **Later**, or select **Start** to accept the BitLocker encryption.</span></span>

    <span data-ttu-id="976f7-132">**注意** 选择 "**请求免除**" 将推迟 BitLocker 保护，直到用户豁免策略中设置的最长时间。</span><span class="sxs-lookup"><span data-stu-id="976f7-132">**Note** Selecting **Request Exemption** postpones the BitLocker protection until the maximum time that is set in the User Exemption Policy.</span></span>

     

3.  <span data-ttu-id="976f7-133">如果用户选择 "**请求豁免**"，他们将收到通知，告知他们联系您的组织的 BitLocker 管理组。</span><span class="sxs-lookup"><span data-stu-id="976f7-133">If users select **Request Exemption**, they receive a notification telling them to contact your organization’s BitLocker administration group.</span></span> <span data-ttu-id="976f7-134">根据配置用户豁免策略的配置方式，向用户提供以下一种或多种联系方法：</span><span class="sxs-lookup"><span data-stu-id="976f7-134">Depending on how the Configure User Exemption Policy is configured, users are provided with one or more of the following contact methods:</span></span>

    -   <span data-ttu-id="976f7-135">电话号码</span><span class="sxs-lookup"><span data-stu-id="976f7-135">Phone Number</span></span>

    -   <span data-ttu-id="976f7-136">网页 URL</span><span class="sxs-lookup"><span data-stu-id="976f7-136">Webpage URL</span></span>

    -   <span data-ttu-id="976f7-137">通讯地址</span><span class="sxs-lookup"><span data-stu-id="976f7-137">Mailing Address</span></span>

    <span data-ttu-id="976f7-138">收到豁免请求后，MBAM 管理员可以确定是否适合将用户添加到 BitLocker 豁免 Active Directory 组。</span><span class="sxs-lookup"><span data-stu-id="976f7-138">After the exemption request is received, the MBAM Administrator can take decide if it is appropriate to add the user to the BitLocker Exemption Active Directory group.</span></span>

    <span data-ttu-id="976f7-139">**注意** 用户提交免除请求后，MBAM 代理会将该用户报告为 "暂时豁免"，然后等待一段可配置的天数，然后再重新检查计算机的合规性。</span><span class="sxs-lookup"><span data-stu-id="976f7-139">**Note** Once a user submits an exemption request, the MBAM agent reports the user as “temporarily exempt” and then waits a configurable number of days before it checks the computer’s compliance again.</span></span> <span data-ttu-id="976f7-140">如果 MBAM 管理员拒绝免除请求，将停用 "免除请求" 选项，这将阻止用户再次请求例外。</span><span class="sxs-lookup"><span data-stu-id="976f7-140">If the MBAM administrator rejects the exemption request, the exemption request option is deactivated, which prevents the user from being able to request the exemption again.</span></span>

     

## <span data-ttu-id="976f7-141">相关主题</span><span class="sxs-lookup"><span data-stu-id="976f7-141">Related topics</span></span>


[<span data-ttu-id="976f7-142">管理 MBAM 2.0 功能</span><span class="sxs-lookup"><span data-stu-id="976f7-142">Administering MBAM 2.0 Features</span></span>](administering-mbam-20-features-mbam-2.md)

 

 





