---
title: 如何重置 TPM 锁定
description: 如何重置 TPM 锁定
author: dansimp
ms.assetid: dd20a728-c52e-48e6-9f6c-1311c71dee74
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f5aea277e80c54fb01d1a6c00b62f0c617d1ad12
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803345"
---
# <span data-ttu-id="90d7e-103">如何重置 TPM 锁定</span><span class="sxs-lookup"><span data-stu-id="90d7e-103">How to Reset a TPM Lockout</span></span>


<span data-ttu-id="90d7e-104">本主题介绍了如何使用管理和监视网站（也称为帮助桌面）重置 TPM 锁定。</span><span class="sxs-lookup"><span data-stu-id="90d7e-104">This topic explains how to use the Administration and Monitoring Website (also referred to as the Help Desk) to reset a TPM lockout.</span></span> <span data-ttu-id="90d7e-105">如果最终用户输入错误 PIN 的次数过多，可能会发生 TPM 锁定。</span><span class="sxs-lookup"><span data-stu-id="90d7e-105">TPM lockouts can occur if an end user enters the incorrect PIN too many times.</span></span> <span data-ttu-id="90d7e-106">用户在 TPM 锁定之前可以输入不正确的 PIN 的次数因制造商而异。</span><span class="sxs-lookup"><span data-stu-id="90d7e-106">The number of times that a user can enter an incorrect PIN before the TPM locks varies from manufacturer to manufacturer.</span></span>

<span data-ttu-id="90d7e-107">在管理和监视网站的 "**管理 TPM** " 区域中，你可以访问集中密钥恢复数据系统，该系统在你提供计算机 ID 和关联的用户标识符时提供 TPM 所有者密码文件。</span><span class="sxs-lookup"><span data-stu-id="90d7e-107">From the **Manage TPM** area of the Administration and Monitoring Website, you can access the centralized Key Recovery data system, which provides a TPM owner password file when you supply a computer ID and associated user identifier.</span></span>

<span data-ttu-id="90d7e-108">若要访问管理和监视网站的 "管理 TPM" 区域，你必须分配 MBAM 帮助台用户角色或 MBAM 高级帮助台用户角色。</span><span class="sxs-lookup"><span data-stu-id="90d7e-108">To access the Manage TPM area of the Administration and Monitoring Website, you must be assigned the MBAM Helpdesk Users role or the MBAM Advanced Helpdesk Users role.</span></span> <span data-ttu-id="90d7e-109">这些角色是管理员在 Active Directory 中创建的组。</span><span class="sxs-lookup"><span data-stu-id="90d7e-109">These roles are groups that administrators create in Active Directory.</span></span> <span data-ttu-id="90d7e-110">你可以为这些组使用任何名称。</span><span class="sxs-lookup"><span data-stu-id="90d7e-110">You can use any name for these groups.</span></span> <span data-ttu-id="90d7e-111">有关详细信息，请参阅[规划 MBAM 2.5 组和帐户](planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles)。</span><span class="sxs-lookup"><span data-stu-id="90d7e-111">For more information, see [Planning for MBAM 2.5 Groups and Accounts](planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles).</span></span>

<span data-ttu-id="90d7e-112">有关 MBAM 和 TPM 所有权的信息，请参阅[MBAM 2.5 安全注意事项](mbam-25-security-considerations.md#bkmk-tpm)。</span><span class="sxs-lookup"><span data-stu-id="90d7e-112">For information about MBAM and TPM ownership, see [MBAM 2.5 Security Considerations](mbam-25-security-considerations.md#bkmk-tpm).</span></span>

**<span data-ttu-id="90d7e-113">重置 TPM 锁定</span><span class="sxs-lookup"><span data-stu-id="90d7e-113">To reset a TPM lockout</span></span>**

1.  <span data-ttu-id="90d7e-114">打开 web 浏览器并导航到 "**管理和监视" 网站**。</span><span class="sxs-lookup"><span data-stu-id="90d7e-114">Open a web browser and navigate to the **Administration and Monitoring Website**.</span></span>

2.  <span data-ttu-id="90d7e-115">在左窗格中，单击 "**管理 tpm** " 以打开 "**管理 tpm** " 页面。</span><span class="sxs-lookup"><span data-stu-id="90d7e-115">In the left pane, click **Manage TPM** to open the **Manage TPM** page.</span></span>

3.  <span data-ttu-id="90d7e-116">输入计算机和计算机名称的完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="90d7e-116">Enter the fully qualified domain name for the computer and the computer name.</span></span>

4.  <span data-ttu-id="90d7e-117">输入最终用户的 Windows 登录域和用户名以检索 TPM 所有者密码文件。</span><span class="sxs-lookup"><span data-stu-id="90d7e-117">Enter the end user’s Windows log-on domain and user name to retrieve the TPM owner password file.</span></span>

    <span data-ttu-id="90d7e-118">**注意** 如果您在 MBAM 高级帮助台用户组中，则不需要 "用户域" 和 "用户 ID" 字段。</span><span class="sxs-lookup"><span data-stu-id="90d7e-118">**Note** If you are in the MBAM Advanced Helpdesk Users group, the user domain and user ID fields are not required.</span></span>

     

5.  <span data-ttu-id="90d7e-119">从 "**请求 TPM 所有者密码文件**" 列表的原因中，选择请求的原因，然后单击 "**提交**"。</span><span class="sxs-lookup"><span data-stu-id="90d7e-119">From the **Reason for requesting TPM owner password file** list, select a reason for the request, and click **Submit**.</span></span>

    <span data-ttu-id="90d7e-120">MBAM 返回以下值之一：</span><span class="sxs-lookup"><span data-stu-id="90d7e-120">MBAM returns one of the following:</span></span>

    -   <span data-ttu-id="90d7e-121">找不到匹配的 TPM 所有者密码文件时出现的错误消息</span><span class="sxs-lookup"><span data-stu-id="90d7e-121">An error message if no matching TPM owner password file is found</span></span>

    -   <span data-ttu-id="90d7e-122">已提交计算机的 TPM 所有者密码文件</span><span class="sxs-lookup"><span data-stu-id="90d7e-122">The TPM owner password file for the submitted computer</span></span>

    <span data-ttu-id="90d7e-123">检索 TPM 所有者密码后，将显示所有者密码。</span><span class="sxs-lookup"><span data-stu-id="90d7e-123">After the TPM owner password is retrieved, the owner password is displayed.</span></span>

6.  <span data-ttu-id="90d7e-124">若要将密码保存到 tpm 文件，请单击 "**保存**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="90d7e-124">To save the password to a .tpm file, click the **Save** button.</span></span>

7.  <span data-ttu-id="90d7e-125">在**管理和监视网站**的 "**管理 tpm** " 区域中，选择 "**重置 tpm 锁定**" 选项并提供 TPM 所有者密码文件。</span><span class="sxs-lookup"><span data-stu-id="90d7e-125">In the **Manage TPM** area of the **Administration and Monitoring Website**, select the **Reset TPM lockout** option and provide the TPM owner password file.</span></span>

    <span data-ttu-id="90d7e-126">将重置 TPM 锁定，并还原最终用户的访问权限。</span><span class="sxs-lookup"><span data-stu-id="90d7e-126">The TPM lockout is reset and the end user’s access is restored.</span></span>

    <span data-ttu-id="90d7e-127">**重要提示** 不要向最终用户提供 TPM 哈希值或 TPM 所有者密码文件。</span><span class="sxs-lookup"><span data-stu-id="90d7e-127">**Important** Do not give the TPM hash value or TPM owner password file to end users.</span></span> <span data-ttu-id="90d7e-128">由于 TPM 信息不会更改，因此为最终用户提供文件会带来安全风险。</span><span class="sxs-lookup"><span data-stu-id="90d7e-128">Because the TPM information does not change, giving the file to end users creates a security risk.</span></span>

     



## <span data-ttu-id="90d7e-129">相关主题</span><span class="sxs-lookup"><span data-stu-id="90d7e-129">Related topics</span></span>


[<span data-ttu-id="90d7e-130">使用 MBAM 2.5 执行 BitLocker 管理</span><span class="sxs-lookup"><span data-stu-id="90d7e-130">Performing BitLocker Management with MBAM 2.5</span></span>](performing-bitlocker-management-with-mbam-25.md)

 

## <span data-ttu-id="90d7e-131">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="90d7e-131">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="90d7e-132">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="90d7e-132">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="90d7e-133">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="90d7e-133">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





