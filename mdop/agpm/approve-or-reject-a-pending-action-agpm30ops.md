---
title: 批准或拒绝挂起的操作
description: 批准或拒绝挂起的操作
author: dansimp
ms.assetid: 6d78989a-b600-4876-9dd9-bc6207ff2ce7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5a787e032a441a8b33a48667afecfc98ec2a3642
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802140"
---
# <span data-ttu-id="3a475-103">批准或拒绝挂起的操作</span><span class="sxs-lookup"><span data-stu-id="3a475-103">Approve or Reject a Pending Action</span></span>


<span data-ttu-id="3a475-104">审批者的核心责任是对组策略对象（GPO）创建、部署和删除的请求进行评估，然后批准或拒绝不具有完成这些操作的权限的编辑者或审阅者的请求。</span><span class="sxs-lookup"><span data-stu-id="3a475-104">The core responsibility of an Approver is to evaluate and then approve or reject requests for Group Policy Object (GPO) creation, deployment, and deletion from Editors or Reviewers who do not have permission to complete those actions.</span></span> <span data-ttu-id="3a475-105">报表可帮助审批者评估新版本的 GPO。</span><span class="sxs-lookup"><span data-stu-id="3a475-105">Reports can assist an Approver with evaluating a new version of a GPO.</span></span>

<span data-ttu-id="3a475-106">需要具有审批者或 AGPM 管理员（完全控制）角色的用户帐户或高级组策略管理（AGPM）中的必要权限才能完成此过程。</span><span class="sxs-lookup"><span data-stu-id="3a475-106">A user account with the Approver or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="3a475-107">查看本主题中 "其他注意事项" 中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="3a475-107">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="3a475-108">批准或拒绝挂起的请求</span><span class="sxs-lookup"><span data-stu-id="3a475-108">To approve or reject a pending request</span></span>**

1.  <span data-ttu-id="3a475-109">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="3a475-109">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="3a475-110">在 "**目录**" 选项卡上，单击 "**挂起**" 选项卡以显示 "挂起的 gpo"。</span><span class="sxs-lookup"><span data-stu-id="3a475-110">On the **Contents** tab, click the **Pending** tab to display the pending GPOs.</span></span>

3.  <span data-ttu-id="3a475-111">右键单击挂起的 GPO，然后单击 "**批准**" 或 "**拒绝**"。</span><span class="sxs-lookup"><span data-stu-id="3a475-111">Right-click a pending GPO, and then click either **Approve** or **Reject**.</span></span>

4.  <span data-ttu-id="3a475-112">如果要批准部署，请单击 "**批准挂起操作**" 对话框中的 "**高级**" 以查看指向该 GPO 的链接。</span><span class="sxs-lookup"><span data-stu-id="3a475-112">If approving deployment, click **Advanced** in the **Approve Pending Operation** dialog box to review links to the GPO.</span></span> <span data-ttu-id="3a475-113">将鼠标指针暂停在树中的某个项目上以显示详细信息。</span><span class="sxs-lookup"><span data-stu-id="3a475-113">Pause the mouse pointer on an item in the tree to display details.</span></span>

    -   <span data-ttu-id="3a475-114">默认情况下，将还原指向该 GPO 的所有链接。</span><span class="sxs-lookup"><span data-stu-id="3a475-114">By default, all links to the GPO will be restored.</span></span>

    -   <span data-ttu-id="3a475-115">若要阻止还原某个链接，请清除该链接的复选框。</span><span class="sxs-lookup"><span data-stu-id="3a475-115">To prevent a link from being restored, clear the check box for that link.</span></span>

    -   <span data-ttu-id="3a475-116">若要阻止还原所有链接，请清除 "**部署 GPO** " 对话框中的 "**还原链接**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="3a475-116">To prevent all links from being restored, clear the **Restore Links** check box in the **Deploy GPO** dialog box.</span></span>

5.  <span data-ttu-id="3a475-117">单击 **"是"** 或 **"确定"** 以确认批准或拒绝待处理的操作。</span><span class="sxs-lookup"><span data-stu-id="3a475-117">Click **Yes** or **OK** to confirm approval or rejection of the pending action.</span></span> <span data-ttu-id="3a475-118">如果您已批准该请求，则 GPO 将移到相应的选项卡上以执行操作。</span><span class="sxs-lookup"><span data-stu-id="3a475-118">If you have approved the request, the GPO is moved to the appropriate tab for the action performed.</span></span>

    <span data-ttu-id="3a475-119">**注意** 如果审批者的电子邮件地址包含在 "**域\*\*\*\*委派**" 选项卡上的 "**收件人电子邮件地址**" 字段中，则当编辑者或审阅者提交请求时，审批者将收到 AGPM 别名发送的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="3a475-119">**Note** If an Approver's e-mail address is included in the **To e-mail address** field on the **Domain** **Delegation** tab, the Approver will receive e-mail from the AGPM alias when an Editor or Reviewer submits a request.</span></span>

     

### <span data-ttu-id="3a475-120">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="3a475-120">Additional considerations</span></span>

-   <span data-ttu-id="3a475-121">默认情况下，你必须是审批者或 AGPM 管理员（完全控制）才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="3a475-121">By default, you must be an Approver or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="3a475-122">具体而言，您必须具有执行要审批的请求所需的权限。</span><span class="sxs-lookup"><span data-stu-id="3a475-122">Specifically, you must have the permissions required to perform the request that you are approving.</span></span>

### <span data-ttu-id="3a475-123">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="3a475-123">Additional references</span></span>

-   [<span data-ttu-id="3a475-124">执行审批者任务</span><span class="sxs-lookup"><span data-stu-id="3a475-124">Performing Approver Tasks</span></span>](performing-approver-tasks-agpm30ops.md)

 

 





