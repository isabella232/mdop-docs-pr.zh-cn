---
title: 委派针对单独 GPO 的访问权限
description: 委派针对单独 GPO 的访问权限
author: dansimp
ms.assetid: b2a7d550-14bf-4b41-b6e4-2cc091eedd2d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9e5d2ae8c6ef52eae39feb67b9df42e84f523300
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801935"
---
# <span data-ttu-id="66aea-103">委派针对单独 GPO 的访问权限</span><span class="sxs-lookup"><span data-stu-id="66aea-103">Delegate Access to an Individual GPO</span></span>


<span data-ttu-id="66aea-104">作为 AGPM 管理员（完全控制），你可以委派受控制的组策略对象（GPO）的管理，以便选定的组和编辑人员可以对其进行编辑，审阅者可以对其进行检查，并且审批者可以批准它。</span><span class="sxs-lookup"><span data-stu-id="66aea-104">As an AGPM Administrator (Full Control), you can delegate the management of a controlled Group Policy object (GPO), so selected groups and Editors can edit it, Reviewers can review it, and Approvers can approve it.</span></span>

<span data-ttu-id="66aea-105">具有 AGPM 管理员（完全控制）角色的用户帐户、创建 GPO 的审批者的用户帐户，或者需要高级组策略管理中具有必需权限的用户帐户才能完成此过程。</span><span class="sxs-lookup"><span data-stu-id="66aea-105">A user account with the AGPM Administrator (Full Control) role, the user account of the Approver who created the GPO, or a user account with the necessary permissions in Advanced Group Policy Management is required to complete this procedure.</span></span> <span data-ttu-id="66aea-106">查看本主题中 "其他注意事项" 中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="66aea-106">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="66aea-107">委派受控 GPO 的管理</span><span class="sxs-lookup"><span data-stu-id="66aea-107">To delegate the management of a controlled GPO</span></span>**

1.  <span data-ttu-id="66aea-108">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="66aea-108">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="66aea-109">在 "详细信息" 窗格中的 "**目录**" 选项卡上，单击 "**受控**" 选项卡以显示 "受控 gpo"，然后单击要委派的 GPO。</span><span class="sxs-lookup"><span data-stu-id="66aea-109">On the **Contents** tab in the details pane, click the **Controlled** tab to display controlled GPOs, and then click the GPO to delegate.</span></span>

3.  <span data-ttu-id="66aea-110">单击 "**添加**" 按钮，选择允许访问的用户或组，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="66aea-110">Click the **Add** button, select the users or groups to be permitted access, and then click **OK**.</span></span>

4.  <span data-ttu-id="66aea-111">若要自定义每个用户或组的权限，请单击 "**目录**" 选项卡上的 "**高级**" 按钮，然后选中 "允许或拒绝的角色权限"。</span><span class="sxs-lookup"><span data-stu-id="66aea-111">To customize the permissions for each user or group, click the **Advanced** button on the **Contents** tab and check role permissions to allow or deny.</span></span> <span data-ttu-id="66aea-112">（有关更多详细的控件，请单击 "**权限**" 对话框中的 "**高级**"。）</span><span class="sxs-lookup"><span data-stu-id="66aea-112">(For more detailed control, click **Advanced** in the **Permissions** dialog box.)</span></span>

5.  <span data-ttu-id="66aea-113">单击 "**应用**"，然后在 "**权限**" 对话框中单击 **"确定"** 。</span><span class="sxs-lookup"><span data-stu-id="66aea-113">Click **Apply**, and then click **OK** in the **Permissions** dialog box.</span></span>

### <span data-ttu-id="66aea-114">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="66aea-114">Additional considerations</span></span>

-   <span data-ttu-id="66aea-115">默认情况下，你必须是创建或控制 GPO 的审批者或 AGPM 管理员（完全控制）才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="66aea-115">By default, you must be the Approver who created or controlled the GPO or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="66aea-116">具体而言，您必须具有域的 "**列表内容**" 权限和 "修改 GPO 的**安全**权限"。</span><span class="sxs-lookup"><span data-stu-id="66aea-116">Specifically, you must have **List Contents** permission for the domain and **Modify Security** permission for the GPO.</span></span>

-   <span data-ttu-id="66aea-117">若要委派使用 AGPM 的组策略管理员的读取访问权限，必须授予它们**列表内容**和**读取设置**权限。</span><span class="sxs-lookup"><span data-stu-id="66aea-117">To delegate read access to Group Policy administrators who use AGPM, you must grant them **List Contents** as well as **Read Settings** permissions.</span></span> <span data-ttu-id="66aea-118">这使他们能够在 AGPM 的 "**目录**" 选项卡上查看 gpo。</span><span class="sxs-lookup"><span data-stu-id="66aea-118">This enables them to view GPOs on the **Contents** tab of AGPM.</span></span> <span data-ttu-id="66aea-119">设置要应用于**此对象和嵌套对象**的权限。</span><span class="sxs-lookup"><span data-stu-id="66aea-119">Set the permission to apply to **This object and nested objects**.</span></span> <span data-ttu-id="66aea-120">其他权限必须明确委派。</span><span class="sxs-lookup"><span data-stu-id="66aea-120">Other permissions must be explicitly delegated.</span></span>

-   <span data-ttu-id="66aea-121">对于已部署的 GPO 副本，编辑器必须具有 "**读取**" 权限，才能完全使用组策略软件安装。</span><span class="sxs-lookup"><span data-stu-id="66aea-121">Editors must have **Read** permission for the deployed copy of a GPO to make full use of Group Policy Software Installation.</span></span>

-   <span data-ttu-id="66aea-122">组策略创建者所有者组的成员身份应受到限制，以便它不会被用于绕过对 Gpo 的访问的 AGPM 管理。</span><span class="sxs-lookup"><span data-stu-id="66aea-122">Membership in the Group Policy Creator Owners group should be restricted so that it is not used to circumvent AGPM management of access to GPOs.</span></span> <span data-ttu-id="66aea-123">（在**组策略管理控制台**中，单击要在其中管理 gpo 的林和域中的 "**组策略对象**"，单击 "**委派**"，然后配置设置以满足组织的需要。）</span><span class="sxs-lookup"><span data-stu-id="66aea-123">(In the **Group Policy Management Console**, click **Group Policy Objects** in the forest and domain in which you want to manage GPOs, click **Delegation**, and then configure the settings to meet the needs of your organization.)</span></span>

### <span data-ttu-id="66aea-124">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="66aea-124">Additional references</span></span>

-   [<span data-ttu-id="66aea-125">执行 AGPM 管理员任务</span><span class="sxs-lookup"><span data-stu-id="66aea-125">Performing AGPM Administrator Tasks</span></span>](performing-agpm-administrator-tasks.md)

 

 





