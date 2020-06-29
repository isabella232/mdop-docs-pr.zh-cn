---
title: 如何恢复已损坏的驱动器
description: 如何恢复已损坏的驱动器
author: dansimp
ms.assetid: fa5b846b-dda6-4ae4-bf6c-39e4f1d8aa00
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: fd9fd8a65d57cbfe965197fa26b57319ee046784
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803191"
---
# <span data-ttu-id="fbc94-103">如何恢复已损坏的驱动器</span><span class="sxs-lookup"><span data-stu-id="fbc94-103">How to Recover a Corrupted Drive</span></span>


<span data-ttu-id="fbc94-104">你可以将此过程与管理和监视网站（也称为帮助桌面）网站结合使用，以恢复受 BitLocker 保护的损坏的驱动器。</span><span class="sxs-lookup"><span data-stu-id="fbc94-104">You can use this procedure with the Administration and Monitoring Website (also referred to as the Help Desk) Website to recover a corrupted drive that is protected by BitLocker.</span></span> <span data-ttu-id="fbc94-105">若要执行此操作，您将完成下表中列出的任务。</span><span class="sxs-lookup"><span data-stu-id="fbc94-105">To do this, you will complete the tasks outlined in the following table.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="fbc94-106">任务</span><span class="sxs-lookup"><span data-stu-id="fbc94-106">Task</span></span></th>
<th align="left"><span data-ttu-id="fbc94-107">详细信息和详细信息</span><span class="sxs-lookup"><span data-stu-id="fbc94-107">Details and more information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="fbc94-108">通过访问 <strong> </strong> 管理和监视网站的驱动器恢复区域来创建恢复密钥包文件。</span><span class="sxs-lookup"><span data-stu-id="fbc94-108">Create a recovery key package file by accessing the <strong>Drive Recovery</strong> area of the Administration and Monitoring Website.</span></span></p></td>
<td align="left"><p><span data-ttu-id="fbc94-109">要访问 <strong> 驱动器恢复 </strong> 区域，你必须被分配 MBAM 帮助台用户角色或 MBAM 高级帮助台用户角色。</span><span class="sxs-lookup"><span data-stu-id="fbc94-109">To access the <strong>Drive Recovery</strong> area, you must be assigned the MBAM Helpdesk Users role or the MBAM Advanced Helpdesk Users role.</span></span> <span data-ttu-id="fbc94-110">创建这些角色时，可能会为这些角色指定不同的名称。</span><span class="sxs-lookup"><span data-stu-id="fbc94-110">You may have given these roles different names when you created them.</span></span> <span data-ttu-id="fbc94-111">有关详细信息，请参阅 <a href="planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles" data-raw-source="[Planning for MBAM 2.5 Groups and Accounts](planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles)"> 规划 MBAM 2.5 组和帐户 </a> 。</span><span class="sxs-lookup"><span data-stu-id="fbc94-111">For more information, see <a href="planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles" data-raw-source="[Planning for MBAM 2.5 Groups and Accounts](planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles)">Planning for MBAM 2.5 Groups and Accounts</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="fbc94-112">将程序包文件复制到包含损坏的驱动器的计算机。</span><span class="sxs-lookup"><span data-stu-id="fbc94-112">Copy the package file to the computer that contains the corrupted drive.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="fbc94-113">使用 <code>repair-bde</code> 命令完成恢复过程。</span><span class="sxs-lookup"><span data-stu-id="fbc94-113">Use the <code>repair-bde</code> command to complete the recovery process.</span></span></p></td>
<td align="left"><p><span data-ttu-id="fbc94-114">为了避免可能丢失数据，强烈建议你 <a href="https://go.microsoft.com/fwlink/?LinkId=393567" data-raw-source="[Manage-bde](https://go.microsoft.com/fwlink/?LinkId=393567)"> 先查看 manage-bde </a> 命令，然后再使用它。</span><span class="sxs-lookup"><span data-stu-id="fbc94-114">To avoid a potential loss of data, it is strongly recommended that you review the <a href="https://go.microsoft.com/fwlink/?LinkId=393567" data-raw-source="[Manage-bde](https://go.microsoft.com/fwlink/?LinkId=393567)">Manage-bde</a> command before using it.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="fbc94-115">恢复损坏的驱动器</span><span class="sxs-lookup"><span data-stu-id="fbc94-115">To recover a corrupted drive</span></span>**

1.  <span data-ttu-id="fbc94-116">打开 web 浏览器并导航到 "**管理和监视" 网站**。</span><span class="sxs-lookup"><span data-stu-id="fbc94-116">Open a web browser and navigate to the **Administration and Monitoring Website**.</span></span>

2.  <span data-ttu-id="fbc94-117">在左窗格中，选择 "**驱动器恢复**" 以打开 "**恢复对加密驱动器的访问**" 页面。</span><span class="sxs-lookup"><span data-stu-id="fbc94-117">In the left pane, select **Drive Recovery** to open the **Recover access to an encrypted drive** page.</span></span>

3.  <span data-ttu-id="fbc94-118">输入最终用户的 Windows 登录域和用户名、解锁驱动器的原因以及最终用户的恢复密码 ID。</span><span class="sxs-lookup"><span data-stu-id="fbc94-118">Enter the end user’s Windows log-on domain and user name, the reason for unlocking the drive, and the end user’s recovery password ID.</span></span>

    <span data-ttu-id="fbc94-119">**注意** 如果您是 "高级帮助台用户" 访问组的成员，则无需输入用户的域名或用户名。</span><span class="sxs-lookup"><span data-stu-id="fbc94-119">**Note** If you are a member of the Advanced Helpdesk Users access group, you do not have to enter the user’s domain name or user name.</span></span>

     

4.  <span data-ttu-id="fbc94-120">单击**提交**。</span><span class="sxs-lookup"><span data-stu-id="fbc94-120">Click **Submit**.</span></span> <span data-ttu-id="fbc94-121">将显示恢复密钥。</span><span class="sxs-lookup"><span data-stu-id="fbc94-121">The recovery key will be displayed.</span></span>

5.  <span data-ttu-id="fbc94-122">单击 "**保存**"，然后选择 "**恢复密钥包**"。</span><span class="sxs-lookup"><span data-stu-id="fbc94-122">Click **Save**, and then select **Recovery Key Package**.</span></span> <span data-ttu-id="fbc94-123">将在你的计算机上创建恢复密钥包。</span><span class="sxs-lookup"><span data-stu-id="fbc94-123">The recovery key package will be created on your computer.</span></span>

6.  <span data-ttu-id="fbc94-124">将恢复密钥包复制到包含损坏的驱动器的计算机。</span><span class="sxs-lookup"><span data-stu-id="fbc94-124">Copy the recovery key package to the computer that has the corrupted drive.</span></span>

7.  <span data-ttu-id="fbc94-125">打开提升的命令提示符。</span><span class="sxs-lookup"><span data-stu-id="fbc94-125">Open an elevated command prompt.</span></span> <span data-ttu-id="fbc94-126">若要执行此操作，请单击 "**开始**"，然后 `cmd` 在 "**搜索程序和文件**" 文本框中键入。</span><span class="sxs-lookup"><span data-stu-id="fbc94-126">To do this, click **Start** and type `cmd` in the **Search programs and files** text box.</span></span> <span data-ttu-id="fbc94-127">右键单击**cmd.exe**，然后选择 "**以管理员身份运行**"。</span><span class="sxs-lookup"><span data-stu-id="fbc94-127">Right-click **cmd.exe**, and select **Run as Administrator**.</span></span>

8.  <span data-ttu-id="fbc94-128">在命令提示符处，键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="fbc94-128">At the command prompt, type the following:</span></span>

    `repair-bde <corrupted drive> <fixed drive> -kp <location of keypackage> -rp <recovery password>`

    <span data-ttu-id="fbc94-129">**注意** 将 &lt; *固定驱动器*替换 &gt; 为具有等于或大于损坏的驱动器上的数据的可用硬盘空间。</span><span class="sxs-lookup"><span data-stu-id="fbc94-129">**Note** Replace &lt;*fixed drive*&gt; with an available hard disk drive that has free space equal to or larger than the data on the corrupted drive.</span></span> <span data-ttu-id="fbc94-130">已损坏的驱动器上的数据将恢复并移动到指定的硬盘驱动器。</span><span class="sxs-lookup"><span data-stu-id="fbc94-130">Data on the corrupted drive is recovered and moved to the specified hard disk drive.</span></span>

     


## <span data-ttu-id="fbc94-131">相关主题</span><span class="sxs-lookup"><span data-stu-id="fbc94-131">Related topics</span></span>


[<span data-ttu-id="fbc94-132">使用 MBAM 2.5 执行 BitLocker 管理</span><span class="sxs-lookup"><span data-stu-id="fbc94-132">Performing BitLocker Management with MBAM 2.5</span></span>](performing-bitlocker-management-with-mbam-25.md)

 
## <span data-ttu-id="fbc94-133">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="fbc94-133">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="fbc94-134">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="fbc94-134">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="fbc94-135">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="fbc94-135">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>
 





