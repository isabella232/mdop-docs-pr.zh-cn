---
title: 请求部署 GPO
description: 请求部署 GPO
author: dansimp
ms.assetid: 9aa9af29-4754-4f72-b624-bb3e1087cbe1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2a9e5fdbbd352adb6d542932c7180c513cfac8b2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802592"
---
# <span data-ttu-id="7ac5b-103">请求部署 GPO</span><span class="sxs-lookup"><span data-stu-id="7ac5b-103">Request Deployment of a GPO</span></span>


<span data-ttu-id="7ac5b-104">修改并签入组策略对象（GPO）后，部署 GPO，以便它在生产环境中生效。</span><span class="sxs-lookup"><span data-stu-id="7ac5b-104">After you have modified and checked in a Group Policy object (GPO), deploy the GPO, so it will take effect in the production environment.</span></span>

<span data-ttu-id="7ac5b-105">要完成此过程，需要在高级组策略管理中具有编辑者角色或必需权限的用户帐户才能完成此过程。</span><span class="sxs-lookup"><span data-stu-id="7ac5b-105">A user account with the Editor role or necessary permissions in Advanced Group Policy Management is required to complete this procedure.</span></span> <span data-ttu-id="7ac5b-106">查看本主题中 "其他注意事项" 中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="7ac5b-106">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="7ac5b-107">请求将 GPO 部署到生产环境</span><span class="sxs-lookup"><span data-stu-id="7ac5b-107">To request the deployment of a GPO to the production environment</span></span>**

1.  <span data-ttu-id="7ac5b-108">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="7ac5b-108">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="7ac5b-109">在 "详细信息" 窗格中的 "**目录**" 选项卡上，单击 "**受控**" 选项卡以显示受控 gpo。</span><span class="sxs-lookup"><span data-stu-id="7ac5b-109">On the **Contents** tab in the details pane, click the **Controlled** tab to display the controlled GPOs.</span></span>

3.  <span data-ttu-id="7ac5b-110">右键单击要部署的 GPO，然后单击 "**部署**"。</span><span class="sxs-lookup"><span data-stu-id="7ac5b-110">Right-click the GPO to be deployed, and then click **Deploy**.</span></span>

4.  <span data-ttu-id="7ac5b-111">除非你是审批者或 AGPM 管理员或具有部署 Gpo 的特殊权限，否则你必须提交部署请求。</span><span class="sxs-lookup"><span data-stu-id="7ac5b-111">Unless you are an Approver or AGPM Administrator or have special permission to deploy GPOs, you must submit a request for deployment.</span></span> <span data-ttu-id="7ac5b-112">若要接收请求的副本，请在 "**抄送**" 字段中键入您的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="7ac5b-112">To receive a copy of the request, type your e-mail address in the **Cc** field.</span></span> <span data-ttu-id="7ac5b-113">键入要在 GPO 的**历史记录**中显示的注释，然后单击 "**提交**"。</span><span class="sxs-lookup"><span data-stu-id="7ac5b-113">Type a comment to be displayed in the **History** for the GPO, and then click **Submit**.</span></span>

5.  <span data-ttu-id="7ac5b-114">当**进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="7ac5b-114">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="7ac5b-115">GPO 将显示在 "**挂起**" 选项卡上的 gpo 列表中。当审批者批准你的请求后，GPO 将从 "**挂起**" 选项卡移到 "已**控制**" 选项卡并进行部署。</span><span class="sxs-lookup"><span data-stu-id="7ac5b-115">The GPO is displayed on the list of GPOs on the **Pending** tab. When an Approver has approved your request, the GPO will be moved from the **Pending** tab to the **Controlled** tab and be deployed.</span></span>

### <span data-ttu-id="7ac5b-116">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="7ac5b-116">Additional considerations</span></span>

-   <span data-ttu-id="7ac5b-117">默认情况下，你必须是编辑器才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="7ac5b-117">By default, you must be an Editor to perform this procedure.</span></span> <span data-ttu-id="7ac5b-118">具体而言，您必须具有该 GPO 的 "**列表内容**" 和 "**编辑设置**" 权限。</span><span class="sxs-lookup"><span data-stu-id="7ac5b-118">Specifically, you must have **List Contents** and **Edit Settings** permissions for the GPO.</span></span>

-   <span data-ttu-id="7ac5b-119">若要撤消已批准的请求，请单击 "**挂起**" 选项卡。右键单击该 GPO，然后单击 "**撤消**"。</span><span class="sxs-lookup"><span data-stu-id="7ac5b-119">To withdraw your request before it has been approved, click the **Pending** tab. Right-click the GPO, and then click **Withdraw**.</span></span> <span data-ttu-id="7ac5b-120">GPO 将返回到 "**受控**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="7ac5b-120">The GPO will be returned to the **Controlled** tab.</span></span>

### <span data-ttu-id="7ac5b-121">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="7ac5b-121">Additional references</span></span>

-   [<span data-ttu-id="7ac5b-122">编辑 GPO</span><span class="sxs-lookup"><span data-stu-id="7ac5b-122">Editing a GPO</span></span>](editing-a-gpo.md)

 

 





