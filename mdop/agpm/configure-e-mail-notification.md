---
title: 配置电子邮件通知
description: 配置电子邮件通知
author: dansimp
ms.assetid: 6e152de0-4376-4963-8d1a-3e7f5866d30f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 46e8d00c2446a0185de30bbd1f39a7e3eaf90080
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802032"
---
# <span data-ttu-id="3ded8-103">配置电子邮件通知</span><span class="sxs-lookup"><span data-stu-id="3ded8-103">Configure E-Mail Notification</span></span>


<span data-ttu-id="3ded8-104">当编辑者或审阅者尝试创建、部署或删除组策略对象（GPO）时，将向指定的电子邮件地址或地址发送对此操作的请求，以便审批者可以评估请求并实现或拒绝它。</span><span class="sxs-lookup"><span data-stu-id="3ded8-104">When an Editor or a Reviewer attempts to create, deploy, or delete a Group Policy object (GPO), a request for this action is sent to a designated e-mail address or addresses so that an Approver can evaluate the request and implement or deny it.</span></span> <span data-ttu-id="3ded8-105">您确定要向其发送通知的电子邮件地址或地址，以及发送通知的别名。</span><span class="sxs-lookup"><span data-stu-id="3ded8-105">You determine the e-mail address or addresses to which notifications are sent, as well as the alias from which notifications are sent.</span></span>

<span data-ttu-id="3ded8-106">要完成此过程，需要具有 AGPM 管理员（完全控制）角色的用户帐户或高级组策略管理中的必需权限。</span><span class="sxs-lookup"><span data-stu-id="3ded8-106">A user account with the AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management is required to complete this procedure.</span></span> <span data-ttu-id="3ded8-107">查看本主题中 "其他注意事项" 中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="3ded8-107">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="3ded8-108">配置 AGPM 的电子邮件通知</span><span class="sxs-lookup"><span data-stu-id="3ded8-108">To configure e-mail notification for AGPM</span></span>**

1.  <span data-ttu-id="3ded8-109">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="3ded8-109">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="3ded8-110">在 "详细信息" 窗格中，单击 "**域委派**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="3ded8-110">In the details pane, click the **Domain Delegation** tab.</span></span>

3.  <span data-ttu-id="3ded8-111">在 "**发件**时间" 字段中，键入要从中发送通知的 AGPM 的电子邮件别名。</span><span class="sxs-lookup"><span data-stu-id="3ded8-111">In the **From** field, type the e-mail alias for AGPM from which notifications should be sent.</span></span>

4.  <span data-ttu-id="3ded8-112">在 "**收件人**" 字段中，键入应接收审批请求的审批者的电子邮件地址的逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="3ded8-112">In the **To** field, type a comma-delimited list of e-mail addresses of Approvers who should receive requests for approval.</span></span>

5.  <span data-ttu-id="3ded8-113">在 " **SMTP 服务器**" 字段中，键入有效的 SMTP 邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="3ded8-113">In the **SMTP server** field, type a valid SMTP mail server.</span></span>

6.  <span data-ttu-id="3ded8-114">在 "**用户名**" 和 "**密码**" 字段中，键入有权访问 SMTP 服务的用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="3ded8-114">In the **User name** and **Password** fields, type the credentials of a user with access to the SMTP service.</span></span>

7.  <span data-ttu-id="3ded8-115">单击**应用**。</span><span class="sxs-lookup"><span data-stu-id="3ded8-115">Click **Apply**.</span></span>

### <span data-ttu-id="3ded8-116">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="3ded8-116">Additional considerations</span></span>

-   <span data-ttu-id="3ded8-117">默认情况下，你必须是 AGPM 管理员（完全控制）才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="3ded8-117">By default, you must be an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="3ded8-118">具体而言，您必须具有域的 "**列表内容**" 和 "**修改选项**" 权限。</span><span class="sxs-lookup"><span data-stu-id="3ded8-118">Specifically, you must have **List Contents** and **Modify Options** permissions for the domain.</span></span>

-   <span data-ttu-id="3ded8-119">AGPM 的电子邮件通知是域级设置。</span><span class="sxs-lookup"><span data-stu-id="3ded8-119">E-mail notification for AGPM is a domain-level setting.</span></span> <span data-ttu-id="3ded8-120">可以在每个域的 "**域委派**" 选项卡上提供不同的审批者电子邮件地址或 AGPM 电子邮件别名，或在整个环境中使用相同的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="3ded8-120">You can provide different Approver e-mail addresses or AGPM e-mail aliases on each domain's **Domain Delegation** tab, or use the same e-mail addresses throughout your environment.</span></span>

### <span data-ttu-id="3ded8-121">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="3ded8-121">Additional references</span></span>

-   [<span data-ttu-id="3ded8-122">执行 AGPM 管理员任务</span><span class="sxs-lookup"><span data-stu-id="3ded8-122">Performing AGPM Administrator Tasks</span></span>](performing-agpm-administrator-tasks.md)

 

 





