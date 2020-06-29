---
title: 销毁 GPO
description: 销毁 GPO
author: dansimp
ms.assetid: d74941a3-beef-46cd-a4ca-80a324dcfadf
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5545918c417fce16bfc2369ebc6fc2199390adc6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801900"
---
# <span data-ttu-id="985f7-103">销毁 GPO</span><span class="sxs-lookup"><span data-stu-id="985f7-103">Destroy a GPO</span></span>


<span data-ttu-id="985f7-104">高级组策略管理（AGPM）使审批者能够销毁组策略对象（GPO），将其从回收站中删除并将其永久删除，这样就不能再还原。</span><span class="sxs-lookup"><span data-stu-id="985f7-104">Advanced Group Policy Management (AGPM) enables Approvers to destroy a Group Policy object (GPO), removing it from the Recycle Bin and permanently deleting it so that it can no longer be restored.</span></span>

<span data-ttu-id="985f7-105">需要具有审批者或 AGPM 管理员（完全控制）角色的用户帐户或高级组策略管理中的必要权限才能完成此过程。</span><span class="sxs-lookup"><span data-stu-id="985f7-105">A user account with the Approver or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management is required to complete this procedure.</span></span> <span data-ttu-id="985f7-106">查看本主题中 "其他注意事项" 中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="985f7-106">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="985f7-107">永久删除 GPO，使其无法再还原</span><span class="sxs-lookup"><span data-stu-id="985f7-107">To permanently delete a GPO so it can no longer be restored</span></span>**

1.  <span data-ttu-id="985f7-108">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="985f7-108">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="985f7-109">在 "**目录**" 选项卡上，单击 "**回收站**" 选项卡以显示已删除的 gpo。</span><span class="sxs-lookup"><span data-stu-id="985f7-109">On the **Contents** tab, click the **Recycle Bin** tab to display the deleted GPOs.</span></span>

3.  <span data-ttu-id="985f7-110">右键单击要销毁的 GPO，然后单击 "**销毁**"。</span><span class="sxs-lookup"><span data-stu-id="985f7-110">Right-click the GPO to destroy, and then click **Destroy**.</span></span>

4.  <span data-ttu-id="985f7-111">单击 **"是"** 以确认要从存档中永久删除所选 GPO 和所有备份。</span><span class="sxs-lookup"><span data-stu-id="985f7-111">Click **Yes** to confirm that you want to permanently delete the selected GPO and all backups from the archive.</span></span>

5.  <span data-ttu-id="985f7-112">当**进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="985f7-112">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="985f7-113">该 GPO 将从 "**回收站**" 选项卡中删除，并被永久删除。</span><span class="sxs-lookup"><span data-stu-id="985f7-113">The GPO is removed from the **Recycle Bin** tab and is permanently deleted.</span></span>

### <span data-ttu-id="985f7-114">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="985f7-114">Additional considerations</span></span>

-   <span data-ttu-id="985f7-115">默认情况下，你必须是审批者或 AGPM 管理员（完全控制）才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="985f7-115">By default, you must be an Approver or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="985f7-116">具体而言，您必须拥有**列表内容**并删除 GPO 的**gpo**权限。</span><span class="sxs-lookup"><span data-stu-id="985f7-116">Specifically, you must have **List Contents** and **Delete GPO** permissions for the GPO.</span></span>

### <span data-ttu-id="985f7-117">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="985f7-117">Additional references</span></span>

-   [<span data-ttu-id="985f7-118">删除、还原或销毁 GPO</span><span class="sxs-lookup"><span data-stu-id="985f7-118">Deleting, Restoring, or Destroying a GPO</span></span>](deleting-restoring-or-destroying-a-gpo.md)

 

 





