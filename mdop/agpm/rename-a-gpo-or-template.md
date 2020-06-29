---
title: 重命名 GPO 或模板
description: 重命名 GPO 或模板
author: dansimp
ms.assetid: 64a1aaf4-f672-48b5-94c6-473bf1076cf3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 495fc090487ff324bc19c89dcd36ecf0efbcb151
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801839"
---
# <span data-ttu-id="65f9c-103">重命名 GPO 或模板</span><span class="sxs-lookup"><span data-stu-id="65f9c-103">Rename a GPO or Template</span></span>


<span data-ttu-id="65f9c-104">你可以重命名受控制的组策略对象（GPO）或模板。</span><span class="sxs-lookup"><span data-stu-id="65f9c-104">You can rename a controlled Group Policy object (GPO) or a template.</span></span>

<span data-ttu-id="65f9c-105">具有编辑器或 AGPM 管理员（完全控制）角色的用户帐户、创建 GPO 的审批者的用户帐户，或者需要高级组策略管理中具有必需权限的用户帐户才能完成此过程。</span><span class="sxs-lookup"><span data-stu-id="65f9c-105">A user account with the Editor or AGPM Administrator (Full Control) role, the user account of the Approver who created the GPO, or a user account with the necessary permissions in Advanced Group Policy Management is required to complete this procedure.</span></span> <span data-ttu-id="65f9c-106">查看本主题中 "其他注意事项" 中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="65f9c-106">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="65f9c-107">重命名 GPO 或模板</span><span class="sxs-lookup"><span data-stu-id="65f9c-107">To rename a GPO or template</span></span>**

1.  <span data-ttu-id="65f9c-108">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="65f9c-108">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="65f9c-109">在 "**目录**" 选项卡上，单击 "**受控**模板" 或 "**模板**" 选项卡以显示要重命名的项目。</span><span class="sxs-lookup"><span data-stu-id="65f9c-109">On the **Contents** tab, click the **Controlled** or **Templates** tab to display the item to rename.</span></span>

3.  <span data-ttu-id="65f9c-110">右键单击要重命名的 GPO 或模板，然后单击 "**重命名**"。</span><span class="sxs-lookup"><span data-stu-id="65f9c-110">Right-click the GPO or template to rename and click **Rename**.</span></span>

4.  <span data-ttu-id="65f9c-111">键入 GPO 或模板的新名称和注释，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="65f9c-111">Type the new name for the GPO or template and a comment, then click **OK**.</span></span>

5.  <span data-ttu-id="65f9c-112">当**进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="65f9c-112">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="65f9c-113">GPO 或模板将显示在 "**目录**" 选项卡上的新名称下。</span><span class="sxs-lookup"><span data-stu-id="65f9c-113">The GPO or template appears under the new name on the **Contents** tab.</span></span>

### <span data-ttu-id="65f9c-114">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="65f9c-114">Additional considerations</span></span>

-   <span data-ttu-id="65f9c-115">默认情况下，你必须是创建或控制 GPO、编辑器或 AGPM 管理员（完全控制）的审批者才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="65f9c-115">By default, you must be the Approver who created or controlled the GPO, an Editor, or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="65f9c-116">具体而言，您必须具有该 GPO 的 "**列表内容**" 和 "**编辑设置**" 权限。</span><span class="sxs-lookup"><span data-stu-id="65f9c-116">Specifically, you must have **List Contents** and **Edit Settings** permission for the GPO.</span></span>

-   <span data-ttu-id="65f9c-117">重命名已部署的 GPO 时，将立即在存档中更改名称。</span><span class="sxs-lookup"><span data-stu-id="65f9c-117">When you rename a GPO that has been deployed, the name is immediately changed in the archive.</span></span> <span data-ttu-id="65f9c-118">只有重新部署 GPO 时，才会在生产环境中更改名称。</span><span class="sxs-lookup"><span data-stu-id="65f9c-118">The name is changed in the production environment only when the GPO is redeployed.</span></span>

    <span data-ttu-id="65f9c-119">重新部署 GPO （或删除生产副本）之前，旧名称仍将在生产环境中使用，因此不能用于另一个 GPO。</span><span class="sxs-lookup"><span data-stu-id="65f9c-119">Until the GPO is redeployed (or the production copy is deleted), the old name is still in use in the production environment and therefore cannot be used for another GPO.</span></span> <span data-ttu-id="65f9c-120">同样，在部署 GPO （更改生产副本的名称）或生产副本已被删除之前，不能将存档中的 GPO 重命名回其原始名称。</span><span class="sxs-lookup"><span data-stu-id="65f9c-120">Likewise, the GPO in the archive cannot be renamed back to its original name until the GPO has been deployed (changing the name of the production copy) or the production copy has been deleted.</span></span>

### <span data-ttu-id="65f9c-121">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="65f9c-121">Additional references</span></span>

-   [<span data-ttu-id="65f9c-122">编辑 GPO</span><span class="sxs-lookup"><span data-stu-id="65f9c-122">Editing a GPO</span></span>](editing-a-gpo.md)

 

 





