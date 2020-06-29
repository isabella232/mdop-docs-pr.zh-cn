---
title: 如何在恢复模式下恢复驱动器
description: 如何在恢复模式下恢复驱动器
author: dansimp
ms.assetid: e126eaf8-9ae7-40fe-a28e-dbd78d26859e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d15f33f461e60fceeed3acbce3a0c82b02b56f98
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803354"
---
# <span data-ttu-id="94ff2-103">如何在恢复模式下恢复驱动器</span><span class="sxs-lookup"><span data-stu-id="94ff2-103">How to Recover a Drive in Recovery Mode</span></span>


<span data-ttu-id="94ff2-104">本主题介绍了如何使用管理和监视网站（也称为帮助桌面）获取恢复密码，以便在其受 BitLocker 保护的驱动器进入恢复模式时向最终用户提供。</span><span class="sxs-lookup"><span data-stu-id="94ff2-104">This topic explains how to use the Administration and Monitoring Website (also referred to as the Help Desk) to get a recovery password to give to end users if their BitLocker-protected drive goes into recovery mode.</span></span> <span data-ttu-id="94ff2-105">如果用户丢失或忘记了其 PIN 或密码，或者受信任的模块平台（TPM）芯片检测到计算机的 BIOS 或启动文件发生更改，则驱动器将进入恢复模式。</span><span class="sxs-lookup"><span data-stu-id="94ff2-105">Drives go into recovery mode if users lose or forget their PIN or password or if the Trusted Module Platform (TPM) chip detects changes to the BIOS or startup files of a computer.</span></span>

<span data-ttu-id="94ff2-106">若要获取恢复密码，请使用管理和监视网站的**驱动器恢复**区域。</span><span class="sxs-lookup"><span data-stu-id="94ff2-106">To get a recovery password, use the **Drive Recovery** area of the Administration and Monitoring Website.</span></span> <span data-ttu-id="94ff2-107">你必须被分配 MBAM 帮助台用户角色或 MBAM 高级帮助台用户角色才能访问该网站的此区域。</span><span class="sxs-lookup"><span data-stu-id="94ff2-107">You must be assigned the MBAM Helpdesk Users role or the MBAM Advanced Helpdesk Users role to access this area of the website.</span></span>

**<span data-ttu-id="94ff2-108">注意</span><span class="sxs-lookup"><span data-stu-id="94ff2-108">Note</span></span>**  
<span data-ttu-id="94ff2-109">创建这些角色时，可能会为这些角色指定不同的名称。</span><span class="sxs-lookup"><span data-stu-id="94ff2-109">You may have given these roles different names when you created them.</span></span> <span data-ttu-id="94ff2-110">有关详细信息，请参阅[规划 MBAM 2.5 组和帐户](planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles)。</span><span class="sxs-lookup"><span data-stu-id="94ff2-110">For more information, see [Planning for MBAM 2.5 Groups and Accounts](planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles).</span></span>



**<span data-ttu-id="94ff2-111">重要提示</span><span class="sxs-lookup"><span data-stu-id="94ff2-111">Important</span></span>**  
<span data-ttu-id="94ff2-112">恢复密码在一次使用后过期。</span><span class="sxs-lookup"><span data-stu-id="94ff2-112">Recovery passwords expire after a single use.</span></span> <span data-ttu-id="94ff2-113">在操作系统驱动器和固定数据驱动器上，自动应用单一使用规则。</span><span class="sxs-lookup"><span data-stu-id="94ff2-113">On operating system drives and fixed data drives, the single-use rule is applied automatically.</span></span> <span data-ttu-id="94ff2-114">在可移动驱动器上，当驱动器被删除，然后在已激活组策略设置以管理可移动驱动器的计算机上重新插入和解锁时，将应用该驱动器。</span><span class="sxs-lookup"><span data-stu-id="94ff2-114">On removable drives, it is applied when the drive is removed and then reinserted and unlocked on a computer that has Group Policy settings activated to manage removable drives.</span></span>



**<span data-ttu-id="94ff2-115">在恢复模式下恢复驱动器</span><span class="sxs-lookup"><span data-stu-id="94ff2-115">To recover a drive in recovery mode</span></span>**

1.  <span data-ttu-id="94ff2-116">打开 web 浏览器并导航到 "**管理和监视" 网站**。</span><span class="sxs-lookup"><span data-stu-id="94ff2-116">Open a web browser and navigate to the **Administration and Monitoring Website**.</span></span>

2.  <span data-ttu-id="94ff2-117">在左窗格中，选择 "**驱动器恢复**" 以打开 "**恢复对加密驱动器的访问**" 页面。</span><span class="sxs-lookup"><span data-stu-id="94ff2-117">In the left pane, select **Drive Recovery** to open the **Recover access to an encrypted drive** page.</span></span>

3.  <span data-ttu-id="94ff2-118">输入最终用户的 Windows 登录域和用户名以查看恢复信息。</span><span class="sxs-lookup"><span data-stu-id="94ff2-118">Enter the end user’s Windows log-on domain and user name to view recovery information.</span></span>

    **<span data-ttu-id="94ff2-119">注意</span><span class="sxs-lookup"><span data-stu-id="94ff2-119">Note</span></span>**  
    <span data-ttu-id="94ff2-120">如果您在 MBAM 高级帮助台用户组中，则不需要 "用户域" 和 "用户 ID" 字段。</span><span class="sxs-lookup"><span data-stu-id="94ff2-120">If you are in the MBAM Advanced Helpdesk Users group, the user domain and user ID fields are not required.</span></span>



4.  <span data-ttu-id="94ff2-121">输入恢复密钥 ID 的前八位数字以查看可能匹配的恢复密钥的列表，或输入整个恢复密钥 ID 以获取准确的恢复密钥。</span><span class="sxs-lookup"><span data-stu-id="94ff2-121">Enter the first eight digits of the recovery key ID to see a list of possible matching recovery keys, or enter the entire recovery key ID to get the exact recovery key.</span></span>

5.  <span data-ttu-id="94ff2-122">从 "**驱动器解锁**" 列表中，选择一个预定义的选项，然后单击 "**提交**"。</span><span class="sxs-lookup"><span data-stu-id="94ff2-122">From the **Reason for Drive Unlock** list, select one of the predefined options, and then click **Submit**.</span></span>

    <span data-ttu-id="94ff2-123">MBAM 返回以下内容：</span><span class="sxs-lookup"><span data-stu-id="94ff2-123">MBAM returns the following:</span></span>

    -   <span data-ttu-id="94ff2-124">找不到匹配的恢复密码时出现的错误消息</span><span class="sxs-lookup"><span data-stu-id="94ff2-124">An error message if no matching recovery password is found</span></span>

    -   <span data-ttu-id="94ff2-125">如果用户具有多个匹配的恢复密码，则可以进行多个可能的匹配</span><span class="sxs-lookup"><span data-stu-id="94ff2-125">Multiple possible matches if the user has multiple matching recovery passwords</span></span>

    -   <span data-ttu-id="94ff2-126">已提交用户的恢复密码和恢复程序包</span><span class="sxs-lookup"><span data-stu-id="94ff2-126">The recovery password and recovery package for the submitted user</span></span>

        **<span data-ttu-id="94ff2-127">注意</span><span class="sxs-lookup"><span data-stu-id="94ff2-127">Note</span></span>**  
        <span data-ttu-id="94ff2-128">如果要恢复损坏的驱动器，恢复包选项将提供 BitLocker，其中包含恢复驱动器所需的关键信息。</span><span class="sxs-lookup"><span data-stu-id="94ff2-128">If you are recovering a damaged drive, the recovery package option provides BitLocker with critical information that it needs to recover the drive.</span></span>



~~~
After the recovery password and recovery package are retrieved, the recovery password is displayed.
~~~

6. <span data-ttu-id="94ff2-129">若要复制密码，请单击 "**复制密钥**"，然后将恢复密码粘贴到电子邮件中。</span><span class="sxs-lookup"><span data-stu-id="94ff2-129">To copy the password, click **Copy Key**, and then paste the recovery password into an email message.</span></span> <span data-ttu-id="94ff2-130">或者，单击 "**保存**" 以将恢复密码保存到文件。</span><span class="sxs-lookup"><span data-stu-id="94ff2-130">Alternatively, click **Save** to save the recovery password to a file.</span></span>

   <span data-ttu-id="94ff2-131">当用户在系统中键入恢复密码或使用恢复包时，驱动器将解锁。</span><span class="sxs-lookup"><span data-stu-id="94ff2-131">When the user types the recovery password into the system or uses the recovery package, the drive is unlocked.</span></span>



## <span data-ttu-id="94ff2-132">相关主题</span><span class="sxs-lookup"><span data-stu-id="94ff2-132">Related topics</span></span>


[<span data-ttu-id="94ff2-133">使用 MBAM 2.5 执行 BitLocker 管理</span><span class="sxs-lookup"><span data-stu-id="94ff2-133">Performing BitLocker Management with MBAM 2.5</span></span>](performing-bitlocker-management-with-mbam-25.md)



## <span data-ttu-id="94ff2-134">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="94ff2-134">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="94ff2-135">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="94ff2-135">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="94ff2-136">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="94ff2-136">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





