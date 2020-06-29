---
title: 还原已删除的 GPO
description: 还原已删除的 GPO
author: dansimp
ms.assetid: 853feb0a-d2d9-4be9-a07e-e113a56a9968
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: aae55a654cad44130816af3acc6aad03e96c9959
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801815"
---
# <span data-ttu-id="7bdd8-103">还原已删除的 GPO</span><span class="sxs-lookup"><span data-stu-id="7bdd8-103">Restore a Deleted GPO</span></span>


<span data-ttu-id="7bdd8-104">审批者可以从回收站还原已删除的组策略对象（GPO），并将其返回到存档。</span><span class="sxs-lookup"><span data-stu-id="7bdd8-104">Approvers can restore a deleted Group Policy Object (GPO) from the Recycle Bin, returning it to the archive.</span></span>

<span data-ttu-id="7bdd8-105">需要具有审批者或 AGPM 管理员（完全控制）角色的用户帐户或高级组策略管理（AGPM）中的必要权限才能完成此过程。</span><span class="sxs-lookup"><span data-stu-id="7bdd8-105">A user account with the Approver or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="7bdd8-106">查看本主题中 "其他注意事项" 中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="7bdd8-106">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="7bdd8-107">还原已删除的 GPO</span><span class="sxs-lookup"><span data-stu-id="7bdd8-107">To restore a deleted GPO</span></span>**

1.  <span data-ttu-id="7bdd8-108">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="7bdd8-108">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="7bdd8-109">在 "**目录**" 选项卡上，单击 "**回收站**" 选项卡以显示已删除的 gpo。</span><span class="sxs-lookup"><span data-stu-id="7bdd8-109">On the **Contents** tab, click the **Recycle Bin** tab to display the deleted GPOs.</span></span>

3.  <span data-ttu-id="7bdd8-110">右键单击要还原的 GPO，然后单击 "**还原**"。</span><span class="sxs-lookup"><span data-stu-id="7bdd8-110">Right-click the GPO to restore, and then click **Restore**.</span></span>

4.  <span data-ttu-id="7bdd8-111">键入要在 GPO 的历史记录中显示的注释，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="7bdd8-111">Type a comment to be displayed in the history of the GPO, and then click **OK**.</span></span>

5.  <span data-ttu-id="7bdd8-112">当**进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="7bdd8-112">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="7bdd8-113">该 GPO 将从 "**回收站**" 选项卡中删除，并显示在 "**受控**" 选项卡上。</span><span class="sxs-lookup"><span data-stu-id="7bdd8-113">The GPO is removed from the **Recycle Bin** tab and is displayed on the **Controlled** tab.</span></span>

<span data-ttu-id="7bdd8-114">**注意** 如果从生产环境中删除了某个 GPO，则将其还原到存档不会自动将其重新部署到生产环境。</span><span class="sxs-lookup"><span data-stu-id="7bdd8-114">**Note** If a GPO was deleted from the production environment, restoring it to the archive will not automatically redeploy it to the production environment.</span></span> <span data-ttu-id="7bdd8-115">若要将 GPO 返回到生产环境，请部署 GPO。</span><span class="sxs-lookup"><span data-stu-id="7bdd8-115">To return the GPO to the production environment, deploy the GPO.</span></span> <span data-ttu-id="7bdd8-116">有关信息，请参阅[部署 GPO](deploy-a-gpo-agpm30ops.md)。</span><span class="sxs-lookup"><span data-stu-id="7bdd8-116">For information, see [Deploy a GPO](deploy-a-gpo-agpm30ops.md).</span></span>

 

### <span data-ttu-id="7bdd8-117">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="7bdd8-117">Additional considerations</span></span>

-   <span data-ttu-id="7bdd8-118">默认情况下，你必须是审批者或 AGPM 管理员（完全控制）才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="7bdd8-118">By default, you must be an Approver or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="7bdd8-119">尤其是，你必须具有**列表内容**，或者为 GPO**部署 GPO**或**删除 gpo**权限。</span><span class="sxs-lookup"><span data-stu-id="7bdd8-119">Specifically, you must have **List Contents** and either **Deploy GPO** or **Delete GPO** permissions for the GPO.</span></span>

### <span data-ttu-id="7bdd8-120">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="7bdd8-120">Additional references</span></span>

-   [<span data-ttu-id="7bdd8-121">删除、还原或销毁 GPO</span><span class="sxs-lookup"><span data-stu-id="7bdd8-121">Deleting, Restoring, or Destroying a GPO</span></span>](deleting-restoring-or-destroying-a-gpo-agpm30ops.md)

 

 





