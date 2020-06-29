---
title: 删除受控的 GPO
description: 删除受控的 GPO
author: dansimp
ms.assetid: f51c1737-c116-4faf-a6f6-c72303f60a3b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 365554d90ac13d749508edbc84dacd432ac4ceec
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801927"
---
# <span data-ttu-id="3e430-103">删除受控的 GPO</span><span class="sxs-lookup"><span data-stu-id="3e430-103">Delete a Controlled GPO</span></span>


<span data-ttu-id="3e430-104">审批者可以删除一个受控制的组策略对象（GPO），将其移动到回收站。</span><span class="sxs-lookup"><span data-stu-id="3e430-104">Approvers can delete a controlled Group Policy Object (GPO), moving it to the Recycle Bin.</span></span>

<span data-ttu-id="3e430-105">需要具有审批者或 AGPM 管理员（完全控制）角色的用户帐户或高级组策略管理（AGPM）中的必要权限才能完成此过程。</span><span class="sxs-lookup"><span data-stu-id="3e430-105">A user account with the Approver or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="3e430-106">查看本主题中 "其他注意事项" 中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="3e430-106">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="3e430-107">删除受控 GPO</span><span class="sxs-lookup"><span data-stu-id="3e430-107">To delete a controlled GPO</span></span>**

1.  <span data-ttu-id="3e430-108">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="3e430-108">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="3e430-109">在 "**目录**" 选项卡上，单击 "**受控**" 选项卡以显示受控 gpo。</span><span class="sxs-lookup"><span data-stu-id="3e430-109">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

3.  <span data-ttu-id="3e430-110">右键单击要删除的 GPO，然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="3e430-110">Right-click the GPO you want to delete, and then click **Delete**.</span></span>

    -   <span data-ttu-id="3e430-111">若要从存档中删除 GPO，同时在生产环境中保持 GPO 的部署版本，请单击 "**仅从存档中删除 gpo**"。</span><span class="sxs-lookup"><span data-stu-id="3e430-111">To delete the GPO from the archive while leaving the deployed version of the GPO untouched in the production environment, click **Delete GPO from archive only**.</span></span>

    -   <span data-ttu-id="3e430-112">若要从存档和生产环境中删除 GPO，请单击 "**从存档和生产中删除 gpo**"。</span><span class="sxs-lookup"><span data-stu-id="3e430-112">To delete the GPO from both the archive and production environment, click **Delete GPO from archive and production**.</span></span>

4.  <span data-ttu-id="3e430-113">键入要显示在 GPO 审核跟踪中的注释，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="3e430-113">Type a comment to be displayed in the audit trail for the GPO, and then click **OK**.</span></span>

5.  <span data-ttu-id="3e430-114">当**进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="3e430-114">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="3e430-115">GPO 将从 "**受控**" 选项卡中删除，并显示在 "**回收站**" 选项卡上，可在其中还原或销毁。</span><span class="sxs-lookup"><span data-stu-id="3e430-115">The GPO is removed from the **Controlled** tab and is displayed on the **Recycle Bin** tab, where it can be restored or destroyed.</span></span> <span data-ttu-id="3e430-116">如果仅从存档中删除了该 GPO，它也会显示在 "不**受控制**" 选项卡上。</span><span class="sxs-lookup"><span data-stu-id="3e430-116">If the GPO was deleted only from the archive, it is also displayed on the **Uncontrolled** tab.</span></span>

### <span data-ttu-id="3e430-117">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="3e430-117">Additional considerations</span></span>

-   <span data-ttu-id="3e430-118">默认情况下，你必须是审批者或 AGPM 管理员（完全控制）才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="3e430-118">By default, you must be an Approver or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="3e430-119">具体而言，您必须拥有**列表内容**并删除 GPO 的**gpo**权限。</span><span class="sxs-lookup"><span data-stu-id="3e430-119">Specifically, you must have **List Contents** and **Delete GPO** permissions for the GPO.</span></span>

-   <span data-ttu-id="3e430-120">若要从生产环境中删除不受管理的 GPO 而不先对其进行控制，请在**组策略管理控制台**中单击 "**林**"，单击 "**域**"，单击 " \*\* &lt; MyDomain &gt; **"，然后单击 "**组策略对象\*\*"。</span><span class="sxs-lookup"><span data-stu-id="3e430-120">To delete an uncontrolled GPO from the production environment without first controlling it, in the **Group Policy Management Console**, click **Forest**, click **Domains**, click **&lt;MyDomain&gt;**, and then click **Group Policy Objects**.</span></span> <span data-ttu-id="3e430-121">右键单击不受控制的 GPO，然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="3e430-121">Right-click the uncontrolled GPO, and then click **Delete**.</span></span>

### <span data-ttu-id="3e430-122">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="3e430-122">Additional references</span></span>

-   [<span data-ttu-id="3e430-123">删除、还原或销毁 GPO</span><span class="sxs-lookup"><span data-stu-id="3e430-123">Deleting, Restoring, or Destroying a GPO</span></span>](deleting-restoring-or-destroying-a-gpo-agpm30ops.md)

 

 





