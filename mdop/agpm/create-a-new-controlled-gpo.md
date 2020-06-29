---
title: 创建新的受控 GPO
description: 创建新的受控 GPO
author: dansimp
ms.assetid: b43ce0f4-4519-4278-83c4-c7d5163ddd11
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0a64e22036bfe99e1d5012d732e3f2e081acdcca
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802879"
---
# <span data-ttu-id="39528-103">创建新的受控 GPO</span><span class="sxs-lookup"><span data-stu-id="39528-103">Create a New Controlled GPO</span></span>


<span data-ttu-id="39528-104">通过 "**更改控制**" 节点创建的新组策略对象（gpo）将自动受控制，从而使你能够使用高级组策略管理（AGPM）管理这些对象。</span><span class="sxs-lookup"><span data-stu-id="39528-104">New Group Policy objects (GPOs) created through the **Change Control** node will automatically be controlled, enabling you to manage them with Advanced Group Policy Management (AGPM).</span></span>

<span data-ttu-id="39528-105">需要具有审批者或 AGPM 管理员（完全控制）角色的用户帐户或高级组策略管理中的必要权限才能完成此过程。</span><span class="sxs-lookup"><span data-stu-id="39528-105">A user account with the Approver or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management is required to complete this procedure.</span></span> <span data-ttu-id="39528-106">查看本主题中 "其他注意事项" 中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="39528-106">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="39528-107">使用通过 AGPM 管理的更改控制创建新 GPO</span><span class="sxs-lookup"><span data-stu-id="39528-107">To create a new GPO with change control managed through AGPM</span></span>**

1.  <span data-ttu-id="39528-108">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="39528-108">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="39528-109">右键单击 "**更改控制**" 节点，然后单击 "**新建受控 GPO**"。</span><span class="sxs-lookup"><span data-stu-id="39528-109">Right-click the **Change Control** node, and then click **New Controlled GPO**.</span></span>

3.  <span data-ttu-id="39528-110">在 "**新建受控 GPO** " 对话框中：</span><span class="sxs-lookup"><span data-stu-id="39528-110">In the **New Controlled GPO** dialog box:</span></span>

    1.  <span data-ttu-id="39528-111">键入新 GPO 的名称。</span><span class="sxs-lookup"><span data-stu-id="39528-111">Type a name for the new GPO.</span></span>

    2.  <span data-ttu-id="39528-112">可选：键入要在 GPO 的**历史记录**中显示的新 GPO 的注释。</span><span class="sxs-lookup"><span data-stu-id="39528-112">Optional: Type a comment for the new GPO to be displayed in the **History** for the GPO.</span></span>

    3.  <span data-ttu-id="39528-113">要立即将新的 GPO 部署到生产环境，请单击 "**创建 live**"。</span><span class="sxs-lookup"><span data-stu-id="39528-113">To immediately deploy the new GPO to the production environment, click **Create live**.</span></span> <span data-ttu-id="39528-114">若要在不立即部署的情况下创建新的 GPO，请单击 "**脱机创建**"。</span><span class="sxs-lookup"><span data-stu-id="39528-114">To create the new GPO offline without immediately deploying it, click **Create offline**.</span></span>

    4.  <span data-ttu-id="39528-115">选择要用作新 GPO 的起始点的 GPO 模板。</span><span class="sxs-lookup"><span data-stu-id="39528-115">Select the GPO template to use as a starting point for the new GPO.</span></span>

    5.  <span data-ttu-id="39528-116">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="39528-116">Click **OK**.</span></span>

4.  <span data-ttu-id="39528-117">当**进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="39528-117">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="39528-118">新的 GPO 将显示在 "**受控**" 选项卡上的 gpo 列表中。</span><span class="sxs-lookup"><span data-stu-id="39528-118">The new GPO is displayed in the list of GPOs on the **Controlled** tab.</span></span>

### <span data-ttu-id="39528-119">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="39528-119">Additional considerations</span></span>

-   <span data-ttu-id="39528-120">默认情况下，你必须是审批者或 AGPM 管理员（完全控制）才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="39528-120">By default, you must be an Approver or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="39528-121">具体而言，您必须拥有**列表内容**并为域**创建 GPO**权限。</span><span class="sxs-lookup"><span data-stu-id="39528-121">Specifically, you must have **List Contents** and **Create GPO** permissions for the domain.</span></span>

### <span data-ttu-id="39528-122">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="39528-122">Additional references</span></span>

-   [<span data-ttu-id="39528-123">创建、控制或导入 GPO</span><span class="sxs-lookup"><span data-stu-id="39528-123">Creating, Controlling, or Importing a GPO</span></span>](creating-controlling-or-importing-a-gpo-approver.md)

 

 





