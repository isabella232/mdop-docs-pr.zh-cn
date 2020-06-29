---
title: 请求控制不受控的 GPO
description: 请求控制不受控的 GPO
author: dansimp
ms.assetid: b668a67a-5a2c-4f6a-8b1c-efa3ca0794d4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8cf1ede496a54d6d3d211c2e3cfc23c506217ca7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801823"
---
# <span data-ttu-id="8a2e5-103">请求控制不受控的 GPO</span><span class="sxs-lookup"><span data-stu-id="8a2e5-103">Request Control of an Uncontrolled GPO</span></span>


<span data-ttu-id="8a2e5-104">若要为现有组策略对象（GPO）提供更改控制，则必须控制 GPO。</span><span class="sxs-lookup"><span data-stu-id="8a2e5-104">To provide change control for an existing Group Policy Object (GPO), the GPO must be controlled.</span></span> <span data-ttu-id="8a2e5-105">除非你是审批者或 AGPM 管理员（完全控制），否则你必须请求控制 GPO。</span><span class="sxs-lookup"><span data-stu-id="8a2e5-105">Unless you are an Approver or an AGPM Administrator (Full Control), you must request that the GPO be controlled.</span></span>

<span data-ttu-id="8a2e5-106">需要高级组策略管理（AGPM）中具有编辑者或审阅者角色或必需权限的用户帐户才能完成此过程。</span><span class="sxs-lookup"><span data-stu-id="8a2e5-106">A user account with the Editor or Reviewer role or necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="8a2e5-107">查看本主题中 "其他注意事项" 中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8a2e5-107">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="8a2e5-108">控制不受控制的 GPO</span><span class="sxs-lookup"><span data-stu-id="8a2e5-108">To control an uncontrolled GPO</span></span>**

1.  <span data-ttu-id="8a2e5-109">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="8a2e5-109">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="8a2e5-110">在 "详细信息" 窗格中的 "**目录**" 选项卡上，单击 "未**控制**" 选项卡以显示非受控 gpo。</span><span class="sxs-lookup"><span data-stu-id="8a2e5-110">On the **Contents** tab in the details pane, click the **Uncontrolled** tab to display the uncontrolled GPOs.</span></span>

3.  <span data-ttu-id="8a2e5-111">右键单击要通过 AGPM 控制的 GPO，然后单击 "**控制**"。</span><span class="sxs-lookup"><span data-stu-id="8a2e5-111">Right-click the GPO to be controlled with AGPM, and then click **Control**.</span></span>

4.  <span data-ttu-id="8a2e5-112">除非拥有控制 Gpo 的特殊权限，否则必须提交控制请求。</span><span class="sxs-lookup"><span data-stu-id="8a2e5-112">Unless you have special permission to control GPOs, you must submit a request for control.</span></span> <span data-ttu-id="8a2e5-113">若要接收请求的副本，请在 "**抄送**" 字段中键入您的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="8a2e5-113">To receive a copy of the request, type your e-mail address in the **Cc** field.</span></span> <span data-ttu-id="8a2e5-114">键入要在 GPO 的**历史记录**中显示的注释，然后单击 "**提交**"。</span><span class="sxs-lookup"><span data-stu-id="8a2e5-114">Type a comment to be displayed in the **History** of the GPO, and then click **Submit**.</span></span>

5.  <span data-ttu-id="8a2e5-115">当**进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="8a2e5-115">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="8a2e5-116">该 GPO 将从 "不可**控制**" 选项卡上的列表中删除，并添加到 "**挂起**" 选项卡。当审批者批准你的请求后，GPO 将移到 "已**控制**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="8a2e5-116">The GPO is removed from the list on the **Uncontrolled** tab and added to the **Pending** tab. When an Approver has approved your request, the GPO will be moved to the **Controlled** tab.</span></span>

### <span data-ttu-id="8a2e5-117">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="8a2e5-117">Additional considerations</span></span>

-   <span data-ttu-id="8a2e5-118">默认情况下，你必须是编辑者或审阅者才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="8a2e5-118">By default, you must be an Editor or a Reviewer to perform this procedure.</span></span> <span data-ttu-id="8a2e5-119">具体而言，您必须具有 "**列表内容**" 和 "**读取设置**" 的域权限。</span><span class="sxs-lookup"><span data-stu-id="8a2e5-119">Specifically, you must have **List Contents** and **Read Settings** permissions for the domain.</span></span>

-   <span data-ttu-id="8a2e5-120">若要撤消已批准的请求，请单击 "**挂起**" 选项卡。右键单击该 GPO，然后单击 "**撤消**"。</span><span class="sxs-lookup"><span data-stu-id="8a2e5-120">To withdraw your request before it has been approved, click the **Pending** tab. Right-click the GPO, and then click **Withdraw**.</span></span> <span data-ttu-id="8a2e5-121">GPO 将返回到 "不**受控制**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="8a2e5-121">The GPO will be returned to the **Uncontrolled** tab.</span></span>

### <span data-ttu-id="8a2e5-122">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="8a2e5-122">Additional references</span></span>

-   [<span data-ttu-id="8a2e5-123">创建、控制或导入 GPO</span><span class="sxs-lookup"><span data-stu-id="8a2e5-123">Creating, Controlling, or Importing a GPO</span></span>](creating-controlling-or-importing-a-gpo-agpm30ops.md)

 

 





