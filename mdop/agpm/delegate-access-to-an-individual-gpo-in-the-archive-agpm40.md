---
title: 委派针对存档中单独 GPO 的访问权限
description: 委派针对存档中单独 GPO 的访问权限
author: dansimp
ms.assetid: 284d2aa2-7c10-4ffa-8978-bbe30867c1c1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9da2a699568f961d030b05a966b76e08aef3aec8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802856"
---
# <span data-ttu-id="2859f-103">委派针对存档中单独 GPO 的访问权限</span><span class="sxs-lookup"><span data-stu-id="2859f-103">Delegate Access to an Individual GPO in the Archive</span></span>


<span data-ttu-id="2859f-104">作为 AGPM 管理员（完全控制），你可以委派存档中受控制的组策略对象（GPO）的管理，以便所选组和编辑可以对其进行编辑，审阅者可以查看它，并且审批者可以批准它。</span><span class="sxs-lookup"><span data-stu-id="2859f-104">As an AGPM Administrator (Full Control), you can delegate the management of a controlled Group Policy Object (GPO) in the archive so that selected groups and Editors can edit it, Reviewers can review it, and Approvers can approve it.</span></span>

<span data-ttu-id="2859f-105">具有 AGPM 管理员（完全控制）角色的用户帐户、创建 GPO 的审批者的用户帐户，或者需要高级组策略管理（AGPM）中具有必要权限的用户帐户才能完成此过程。</span><span class="sxs-lookup"><span data-stu-id="2859f-105">A user account with the AGPM Administrator (Full Control) role, the user account of the Approver who created the GPO, or a user account with the necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="2859f-106">查看本主题中 "其他注意事项" 中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="2859f-106">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="2859f-107">委派受控 GPO 的管理</span><span class="sxs-lookup"><span data-stu-id="2859f-107">To delegate the management of a controlled GPO</span></span>**

1.  <span data-ttu-id="2859f-108">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="2859f-108">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="2859f-109">在 "详细信息" 窗格中的 "**目录**" 选项卡上，单击 "**受控**" 选项卡以显示 "受控 gpo"，然后单击要委派的 GPO：</span><span class="sxs-lookup"><span data-stu-id="2859f-109">On the **Contents** tab in the details pane, click the **Controlled** tab to display controlled GPOs, and then click the GPO to delegate:</span></span>

    1.  <span data-ttu-id="2859f-110">若要为用户或组添加访问权限，请单击 "**添加**" 按钮，选择用户或组，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="2859f-110">To add access for a user or group, click the **Add** button, select the user or group, and click **OK**.</span></span> <span data-ttu-id="2859f-111">在 "**添加组" 或 "用户**" 对话框中，选择一个角色，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="2859f-111">In the **Add Group or User** dialog box, select a role and click **OK**.</span></span>

    2.  <span data-ttu-id="2859f-112">若要删除用户或组的访问权限，请选择该用户或组，然后单击 "**删除**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="2859f-112">To remove access for a user or group, select the user or group, and click the **Remove** button.</span></span>

        <span data-ttu-id="2859f-113">**注意** 如果用户或组继承了域范围的访问权限，则 "**删除**" 按钮不可用。</span><span class="sxs-lookup"><span data-stu-id="2859f-113">**Note** If a user or group inherits domain-wide access, the **Remove** button is unavailable.</span></span> <span data-ttu-id="2859f-114">可以在 "**域委派**" 选项卡上修改域范围的访问权限。</span><span class="sxs-lookup"><span data-stu-id="2859f-114">You can modify domain-wide access on the **Domain Delegation** tab.</span></span>

         

    3.  <span data-ttu-id="2859f-115">若要修改委派给用户或组的角色和权限，请单击 "**高级**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="2859f-115">To modify the roles and permissions delegated to a user or group, click the **Advanced** button.</span></span> <span data-ttu-id="2859f-116">在 "**权限**" 对话框中，选择 "用户" 或 "组"，选中要分配给该用户或组的每个角色的复选框，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="2859f-116">In the **Permissions** dialog box, select the user or group, select the check box for each role to be assigned to that user or group, and click **OK**.</span></span>

        <span data-ttu-id="2859f-117">**注意** 编辑者和审批者包括审阅者权限。</span><span class="sxs-lookup"><span data-stu-id="2859f-117">**Note** Editor and Approver include Reviewer permissions.</span></span>

         

### <span data-ttu-id="2859f-118">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="2859f-118">Additional considerations</span></span>

-   <span data-ttu-id="2859f-119">默认情况下，你必须是创建或控制 GPO 的审批者或 AGPM 管理员（完全控制）才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="2859f-119">By default, you must be the Approver who created or controlled the GPO or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="2859f-120">具体而言，您必须具有域的 "**列表内容**" 权限和 "修改 GPO 的**安全**权限"。</span><span class="sxs-lookup"><span data-stu-id="2859f-120">Specifically, you must have **List Contents** permission for the domain and **Modify Security** permission for the GPO.</span></span>

-   <span data-ttu-id="2859f-121">若要委派使用 AGPM 的组策略管理员的读取访问权限，必须授予它们**列表内容**和**读取设置**权限。</span><span class="sxs-lookup"><span data-stu-id="2859f-121">To delegate read access to Group Policy administrators who use AGPM, you must grant them **List Contents** as well as **Read Settings** permissions.</span></span> <span data-ttu-id="2859f-122">这使他们能够在 AGPM 的 "**目录**" 选项卡上查看 gpo。</span><span class="sxs-lookup"><span data-stu-id="2859f-122">This enables them to view GPOs on the **Contents** tab of AGPM.</span></span> <span data-ttu-id="2859f-123">其他权限必须明确委派。</span><span class="sxs-lookup"><span data-stu-id="2859f-123">Other permissions must be explicitly delegated.</span></span>

-   <span data-ttu-id="2859f-124">对于已部署的 GPO 副本，编辑器必须具有 "**读取**" 权限，才能完全使用组策略软件安装。</span><span class="sxs-lookup"><span data-stu-id="2859f-124">Editors must have **Read** permission for the deployed copy of a GPO to make full use of Group Policy Software Installation.</span></span>

-   <span data-ttu-id="2859f-125">组策略创建者所有者组的成员身份应受到限制，soit 不会用于绕过对 Gpo 的访问的 AGPM 管理。</span><span class="sxs-lookup"><span data-stu-id="2859f-125">Membership in the Group Policy Creator Owners group should be restricted, soit is not used to circumvent AGPM management of access to GPOs.</span></span> <span data-ttu-id="2859f-126">（在**组策略管理控制台**中，单击要在其中管理 gpo 的林和域中的 "**组策略对象**"，单击 "**委派**"，然后配置设置以满足组织的需要。）</span><span class="sxs-lookup"><span data-stu-id="2859f-126">(In the **Group Policy Management Console**, click **Group Policy Objects** in the forest and domain in which you want to manage GPOs, click **Delegation**, and then configure the settings to meet the needs of your organization.)</span></span>

### <span data-ttu-id="2859f-127">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="2859f-127">Additional references</span></span>

-   [<span data-ttu-id="2859f-128">管理存档</span><span class="sxs-lookup"><span data-stu-id="2859f-128">Managing the Archive</span></span>](managing-the-archive-agpm40.md)

 

 





