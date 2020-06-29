---
title: 委派对受控 GPO 的管理
description: 委派对受控 GPO 的管理
author: dansimp
ms.assetid: 509b02e7-ce0b-4919-b58a-c3a33051152e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9d34231f25c172951cd0176b3e490dab84b98f1d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801928"
---
# <span data-ttu-id="926d7-103">委派对受控 GPO 的管理</span><span class="sxs-lookup"><span data-stu-id="926d7-103">Delegate Management of a Controlled GPO</span></span>


<span data-ttu-id="926d7-104">审批者可以委派由该审批者创建的受控组策略对象（GPO）的管理。</span><span class="sxs-lookup"><span data-stu-id="926d7-104">An Approver can delegate the management of a controlled Group Policy Object (GPO) that was created by that Approver.</span></span> <span data-ttu-id="926d7-105">与 AGPM 管理员（完全控制）一样，审批者可以委派对此类 GPO 的访问权限，以便选定的编辑者可以对其进行编辑、审阅者可以对其进行审阅，并且其他审批者可以批准它。</span><span class="sxs-lookup"><span data-stu-id="926d7-105">Like an AGPM Administrator (Full Control), the Approver can delegate access to such a GPO so that selected Editors can edit it, Reviewers can review it, and other Approvers can approve it.</span></span> <span data-ttu-id="926d7-106">默认情况下，审批者无法委派对由其他组策略管理员创建的 Gpo 的访问权限。</span><span class="sxs-lookup"><span data-stu-id="926d7-106">By default, an Approver cannot delegate access to GPOs created by another Group Policy administrator.</span></span>

<span data-ttu-id="926d7-107">具有 AGPM 管理员（完全控制）角色的用户帐户、创建 GPO 的审批者的用户帐户，或者需要高级组策略管理（AGPM）中具有必要权限的用户帐户才能完成此过程。</span><span class="sxs-lookup"><span data-stu-id="926d7-107">A user account with the AGPM Administrator (Full Control) role, the user account of the Approver who created the GPO, or a user account with the necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="926d7-108">查看本主题中 "其他注意事项" 中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="926d7-108">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="926d7-109">委派受控 GPO 的管理</span><span class="sxs-lookup"><span data-stu-id="926d7-109">To delegate the management of a controlled GPO</span></span>**

1.  <span data-ttu-id="926d7-110">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="926d7-110">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="926d7-111">在 "详细信息" 窗格中的 "**目录**" 选项卡上，单击 "**受控**" 选项卡以显示 "受控 gpo"，然后单击要委派的 GPO：</span><span class="sxs-lookup"><span data-stu-id="926d7-111">On the **Contents** tab in the details pane, click the **Controlled** tab to display controlled GPOs, and then click the GPO to delegate:</span></span>

    1.  <span data-ttu-id="926d7-112">若要为用户或组添加访问权限，请单击 "**添加**" 按钮，选择用户或组，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="926d7-112">To add access for a user or group, click the **Add** button, select the user or group, and click **OK**.</span></span> <span data-ttu-id="926d7-113">在 "**添加组" 或 "用户**" 对话框中，选择一个角色，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="926d7-113">In the **Add Group or User** dialog box, select a role and click **OK**.</span></span>

    2.  <span data-ttu-id="926d7-114">若要删除用户或组的访问权限，请选择该用户或组，然后单击 "**删除**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="926d7-114">To remove access for a user or group, select the user or group, and then click the **Remove** button.</span></span>

        <span data-ttu-id="926d7-115">**注意** 如果用户或组继承了域范围的访问权限，则 "**删除**" 按钮不可用。</span><span class="sxs-lookup"><span data-stu-id="926d7-115">**Note** If a user or group inherits domain-wide access, the **Remove** button is unavailable.</span></span> <span data-ttu-id="926d7-116">可以在 "**域委派**" 选项卡上修改域范围的访问权限。</span><span class="sxs-lookup"><span data-stu-id="926d7-116">You can modify domain-wide access on the **Domain Delegation** tab.</span></span>

         

    3.  <span data-ttu-id="926d7-117">若要修改委派给用户或组的角色和权限，请单击 "**高级**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="926d7-117">To modify the roles and permissions delegated to a user or group, click the **Advanced** button.</span></span> <span data-ttu-id="926d7-118">在 "**权限**" 对话框中，选择 "用户" 或 "组"，选中要分配给该用户或组的每个角色的复选框，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="926d7-118">In the **Permissions** dialog box, select the user or group, select the check box for each role to be assigned to that user or group, and then click **OK**.</span></span>

        <span data-ttu-id="926d7-119">**注意** 编辑者和审批者包括审阅者权限。</span><span class="sxs-lookup"><span data-stu-id="926d7-119">**Note** Editor and Approver include Reviewer permissions.</span></span>

         

### <span data-ttu-id="926d7-120">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="926d7-120">Additional considerations</span></span>

-   <span data-ttu-id="926d7-121">默认情况下，你必须是创建或控制 GPO 的审批者或 AGPM 管理员（完全控制）才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="926d7-121">By default, you must be the Approver who created or controlled the GPO or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="926d7-122">具体而言，您必须具有域的 "**列表内容**" 权限和 "修改 GPO 的**安全**权限"。</span><span class="sxs-lookup"><span data-stu-id="926d7-122">Specifically, you must have **List Contents** permission for the domain and **Modify Security** permission for the GPO.</span></span>

-   <span data-ttu-id="926d7-123">若要委派使用 AGPM 的组策略管理员的读取访问权限，必须授予它们**列表内容**和**读取设置**权限。</span><span class="sxs-lookup"><span data-stu-id="926d7-123">To delegate read access to Group Policy administrators who use AGPM, you must grant them **List Contents** as well as **Read Settings** permissions.</span></span> <span data-ttu-id="926d7-124">这使他们能够在 AGPM 的 "**目录**" 选项卡上查看 gpo。</span><span class="sxs-lookup"><span data-stu-id="926d7-124">This enables them to view GPOs on the **Contents** tab of AGPM.</span></span> <span data-ttu-id="926d7-125">其他权限必须明确委派。</span><span class="sxs-lookup"><span data-stu-id="926d7-125">Other permissions must be explicitly delegated.</span></span>

-   <span data-ttu-id="926d7-126">对于已部署的 GPO 副本，编辑器必须具有 "**读取**" 权限，才能完全使用组策略软件安装。</span><span class="sxs-lookup"><span data-stu-id="926d7-126">Editors must have **Read** permission for the deployed copy of a GPO to make full use of Group Policy Software Installation.</span></span>

### <span data-ttu-id="926d7-127">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="926d7-127">Additional references</span></span>

-   [<span data-ttu-id="926d7-128">创建、控制或导入 GPO</span><span class="sxs-lookup"><span data-stu-id="926d7-128">Creating, Controlling, or Importing a GPO</span></span>](creating-controlling-or-importing-a-gpo-editor-agpm30ops.md)

 

 





