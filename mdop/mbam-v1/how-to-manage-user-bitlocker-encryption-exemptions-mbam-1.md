---
title: 如何管理用户 BitLocker 加密免除
description: 如何管理用户 BitLocker 加密免除
author: dansimp
ms.assetid: 48d69721-504f-4524-8a04-b9ce213ac9b4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8c3d70558a65c3288174413d6c36cc9c77bc9eaa
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798177"
---
# <span data-ttu-id="75fcf-103">如何管理用户 BitLocker 加密免除</span><span class="sxs-lookup"><span data-stu-id="75fcf-103">How to Manage User BitLocker Encryption Exemptions</span></span>


<span data-ttu-id="75fcf-104">Microsoft BitLocker 管理和监视（MBAM）可用于管理 BitLocker 保护，exempting 不需要或不希望其驱动器加密的用户。</span><span class="sxs-lookup"><span data-stu-id="75fcf-104">Microsoft BitLocker Administration and Monitoring (MBAM) can be used to manage BitLocker protection by exempting users who do not need or want their drives encrypted.</span></span>

<span data-ttu-id="75fcf-105">若要从 BitLocker 保护中免除用户，组织必须首先创建支持此类免除的基础结构。</span><span class="sxs-lookup"><span data-stu-id="75fcf-105">To exempt users from BitLocker protection, an organization must first create an infrastructure to support such exemptions.</span></span> <span data-ttu-id="75fcf-106">支持的基础结构可能包括用于请求豁免的联系人电话号码、网页或邮件地址。</span><span class="sxs-lookup"><span data-stu-id="75fcf-106">The supporting infrastructure might include a contact telephone number, webpage, or mailing address to request exemption.</span></span> <span data-ttu-id="75fcf-107">此外，必须将任何豁免用户添加到专为豁免用户创建的组策略的安全组中。</span><span class="sxs-lookup"><span data-stu-id="75fcf-107">Also, any exempt user will have to be added to a security group for Group Policy created specifically for exempted users.</span></span> <span data-ttu-id="75fcf-108">当此安全组的成员登录到计算机时，用户组策略将显示用户已被免除了 BitLocker 保护。</span><span class="sxs-lookup"><span data-stu-id="75fcf-108">When members of this security group log on to a computer, the user Group Policy shows that the user is exempted from BitLocker protection.</span></span> <span data-ttu-id="75fcf-109">用户策略将覆盖计算机策略，并且计算机将保持不受 BitLocker 加密的阻止。</span><span class="sxs-lookup"><span data-stu-id="75fcf-109">The user policy overwrites the computer policy, and the computer will remain exempt from BitLocker encryption.</span></span>

<span data-ttu-id="75fcf-110">**注意** 如果计算机已受 BitLocker 保护，则用户豁免策略不起作用。</span><span class="sxs-lookup"><span data-stu-id="75fcf-110">**Note** If the computer is already BitLocker-protected, the user exemption policy has no effect.</span></span>

 

<span data-ttu-id="75fcf-111">下表显示了如何根据如何设置免除来应用 BitLocker 保护。</span><span class="sxs-lookup"><span data-stu-id="75fcf-111">The following table shows how BitLocker protection is applied based on how exemptions are set.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="75fcf-112">用户状态</span><span class="sxs-lookup"><span data-stu-id="75fcf-112">User Status</span></span></th>
<th align="left"><span data-ttu-id="75fcf-113">计算机未豁免</span><span class="sxs-lookup"><span data-stu-id="75fcf-113">Computer Not Exempt</span></span></th>
<th align="left"><span data-ttu-id="75fcf-114">计算机豁免</span><span class="sxs-lookup"><span data-stu-id="75fcf-114">Computer Exempt</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="75fcf-115">用户不豁免</span><span class="sxs-lookup"><span data-stu-id="75fcf-115">User not exempt</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="75fcf-116">在计算机上强制执行 BitLocker 保护。</span><span class="sxs-lookup"><span data-stu-id="75fcf-116">BitLocker protection is enforced on the computer.</span></span></p></td>
<td align="left"><p><span data-ttu-id="75fcf-117">不会在计算机上强制执行 BitLocker 保护。</span><span class="sxs-lookup"><span data-stu-id="75fcf-117">BitLocker protection is not enforced on the computer.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="75fcf-118">用户豁免</span><span class="sxs-lookup"><span data-stu-id="75fcf-118">User exempt</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="75fcf-119">不会在计算机上强制执行 BitLocker 保护。</span><span class="sxs-lookup"><span data-stu-id="75fcf-119">BitLocker protection is not enforced on the computer.</span></span></p></td>
<td align="left"><p><span data-ttu-id="75fcf-120">不会在计算机上强制执行 BitLocker 保护。</span><span class="sxs-lookup"><span data-stu-id="75fcf-120">BitLocker protection is not enforced on the computer.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="75fcf-121">从 BitLocker 加密中免除用户</span><span class="sxs-lookup"><span data-stu-id="75fcf-121">To exempt a user from BitLocker Encryption</span></span>**

1.  <span data-ttu-id="75fcf-122">创建将用于管理来自 BitLocker 加密的用户免除的 ActiveDirectoryDomainServices 安全组。</span><span class="sxs-lookup"><span data-stu-id="75fcf-122">Create an ActiveDirectoryDomainServices security group that will be used to manage user exemptions from BitLocker encryption.</span></span>

2.  <span data-ttu-id="75fcf-123">通过使用 MBAM 组策略模板来创建组策略对象设置。</span><span class="sxs-lookup"><span data-stu-id="75fcf-123">Create a Group Policy Object setting by using the MBAM Group Policy template.</span></span> <span data-ttu-id="75fcf-124">将组策略对象与您在上一步中创建的 Active Directory 组相关联。</span><span class="sxs-lookup"><span data-stu-id="75fcf-124">Associate the Group Policy Object with the Active Directory group that you created in the previous step.</span></span> <span data-ttu-id="75fcf-125">有关使用户能够从 BitLocker 加密中请求豁免的必要策略设置的详细信息，请参阅[规划 MBAM 1.0 组策略要求](planning-for-mbam-10-group-policy-requirements.md)中的 "配置用户豁免策略" 部分。</span><span class="sxs-lookup"><span data-stu-id="75fcf-125">For more information about the necessary policy settings to enable users to request exemption from BitLocker encryption, see the Configure User Exemption Policy section in [Planning for MBAM 1.0 Group Policy Requirements](planning-for-mbam-10-group-policy-requirements.md).</span></span>

3.  <span data-ttu-id="75fcf-126">为 BitLocker 免除的用户创建安全组之后，将请求豁免的用户的名称添加到此群组。</span><span class="sxs-lookup"><span data-stu-id="75fcf-126">After creating a security group for BitLocker-exempted users, add to this group the names of the users who are requesting exemption.</span></span> <span data-ttu-id="75fcf-127">当用户登录到由 BitLocker 控制的计算机时，MBAM 客户端将检查用户豁免策略设置，并根据用户是否属于 BitLocker 豁免安全组来暂停保护。</span><span class="sxs-lookup"><span data-stu-id="75fcf-127">When a user logs on to a computer controlled by BitLocker, the MBAM client will check the User Exemption Policy setting and will suspend protection based on whether the user is part of the BitLocker exemption security group.</span></span>

    <span data-ttu-id="75fcf-128">**注意** 共享计算机方案需要针对用户例外的特殊注意事项。</span><span class="sxs-lookup"><span data-stu-id="75fcf-128">**Note** Shared computer scenarios require special consideration regarding user exemption.</span></span> <span data-ttu-id="75fcf-129">如果非豁免用户登录到与豁免用户共享的计算机，则该计算机可能已加密。</span><span class="sxs-lookup"><span data-stu-id="75fcf-129">If a non-exempt user logs on to a computer shared with an exempt user, the computer may be encrypted.</span></span>

     

**<span data-ttu-id="75fcf-130">使用户能够从 BitLocker 加密请求豁免</span><span class="sxs-lookup"><span data-stu-id="75fcf-130">To enable users to request exemption from BitLocker Encryption</span></span>**

1.  <span data-ttu-id="75fcf-131">通过 usingwith MBAM 策略模板配置用户豁免策略后，用户可以通过 MBAM 客户端请求 BitLocker 保护中的豁免。</span><span class="sxs-lookup"><span data-stu-id="75fcf-131">After you have configured user-exemption policies by usingwith the MBAM Policy template, a user can request exemption from BitLocker protection through the MBAM client.</span></span>

2.  <span data-ttu-id="75fcf-132">当用户登录到在 MBAM 硬件兼容性列表中标记为**兼容**的计算机时，系统会向用户显示计算机将要加密的通知。</span><span class="sxs-lookup"><span data-stu-id="75fcf-132">When a user logs on to a computer that is marked as **Compatible** in the MBAM Hardware Compatibility list, the system presents the user with a notification that the computer is going to be encrypted.</span></span> <span data-ttu-id="75fcf-133">用户可以选择 "**请求豁免** **"，** 然后通过选择 "开始"，然后选择 "**开始**" 接受 BitLocker 加密来推迟加密。</span><span class="sxs-lookup"><span data-stu-id="75fcf-133">The user can select **Request Exemption** and postpone the encryption by selecting **Later**, or select **Start** to accept the BitLocker encryption.</span></span>

    <span data-ttu-id="75fcf-134">**注意** 选择 "**请求豁免**" 将推迟 BitLocker 保护，直到用户豁免策略中设置的最长时间。</span><span class="sxs-lookup"><span data-stu-id="75fcf-134">**Note** Selecting **Request Exemption** will postpone the BitLocker protection until the maximum time set in the User Exemption Policy.</span></span>

     

3.  <span data-ttu-id="75fcf-135">当用户选择 "**请求豁免**" 时，系统会通知用户联系组织的 BitLocker 管理组。</span><span class="sxs-lookup"><span data-stu-id="75fcf-135">When a user selects **Request Exemption**, the user is notified to contact the organization's BitLocker administration group.</span></span> <span data-ttu-id="75fcf-136">根据配置用户豁免策略的配置方式，向用户提供以下一种或多种联系方法：</span><span class="sxs-lookup"><span data-stu-id="75fcf-136">Depending on how the Configure User Exemption Policy is configured, users are provided with one or more of the following contact methods:</span></span>

    -   <span data-ttu-id="75fcf-137">电话号码</span><span class="sxs-lookup"><span data-stu-id="75fcf-137">Phone Number</span></span>

    -   <span data-ttu-id="75fcf-138">网页 URL</span><span class="sxs-lookup"><span data-stu-id="75fcf-138">Webpage URL</span></span>

    -   <span data-ttu-id="75fcf-139">通讯地址</span><span class="sxs-lookup"><span data-stu-id="75fcf-139">Mailing Address</span></span>

    <span data-ttu-id="75fcf-140">提交请求后，MBAM 管理员可以确定是否适合将用户添加到 BitLocker 豁免 Active Directory 组。</span><span class="sxs-lookup"><span data-stu-id="75fcf-140">After submittal of the request, the MBAM Administrator can decide if it is appropriate to add the user to the BitLocker Exemption Active Directory group.</span></span>

    <span data-ttu-id="75fcf-141">**注意** 一旦用户豁免策略的延迟时间限制已过期，用户将看不到用于向加密策略请求豁免的选项。</span><span class="sxs-lookup"><span data-stu-id="75fcf-141">**Note** Once the postpone time limit from the User Exemption Policy has expired, users will not see the option to request exemption to the encryption policy.</span></span> <span data-ttu-id="75fcf-142">此时，用户必须直接联系 MBAM 管理员，以便从 BitLocker 保护接收豁免。</span><span class="sxs-lookup"><span data-stu-id="75fcf-142">At this point, users must contact the MBAM administrator directly in order to receive exemption from BitLocker Protection.</span></span>

     

## <span data-ttu-id="75fcf-143">相关主题</span><span class="sxs-lookup"><span data-stu-id="75fcf-143">Related topics</span></span>


[<span data-ttu-id="75fcf-144">管理 MBAM 1.0 功能</span><span class="sxs-lookup"><span data-stu-id="75fcf-144">Administering MBAM 1.0 Features</span></span>](administering-mbam-10-features.md)

 

 





