---
title: 委派域级访问权限
description: 委派域级访问权限
author: dansimp
ms.assetid: 64c8e773-38cc-4991-9ed2-5a801094d06e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7eb4c33e60b0d995e45fca6c9e91a26c30dd4a7f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802840"
---
# <span data-ttu-id="b8bc2-103">委派域级访问权限</span><span class="sxs-lookup"><span data-stu-id="b8bc2-103">Delegate Domain-Level Access</span></span>


<span data-ttu-id="b8bc2-104">为你的环境设置委派，以便组策略管理员对组策略对象（Gpo）具有适当的访问权限和控制权限。</span><span class="sxs-lookup"><span data-stu-id="b8bc2-104">Set up delegation for your environment so Group Policy administrators have the appropriate access to and control over Group Policy objects (GPOs).</span></span> <span data-ttu-id="b8bc2-105">你可以应用基准权限，以使高级组策略管理（AGPM）的操作更高效。</span><span class="sxs-lookup"><span data-stu-id="b8bc2-105">There are baseline permissions you can apply to make the operation of Advanced Group Policy Management (AGPM) more efficient.</span></span> <span data-ttu-id="b8bc2-106">你可以采用满足组织需求的任何方式授予权限。</span><span class="sxs-lookup"><span data-stu-id="b8bc2-106">You can grant permissions in any manner that meets the needs of your organization.</span></span>

<span data-ttu-id="b8bc2-107">要完成此过程，需要具有 AGPM 管理员（完全控制）角色的用户帐户或高级组策略管理中的必需权限。</span><span class="sxs-lookup"><span data-stu-id="b8bc2-107">A user account with the AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management is required to complete this procedure.</span></span> <span data-ttu-id="b8bc2-108">查看本主题中 "其他注意事项" 中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b8bc2-108">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="b8bc2-109">委派访问权限，以便用户和组对整个域中的所有 Gpo 具有适当的权限</span><span class="sxs-lookup"><span data-stu-id="b8bc2-109">To delegate access so users and groups have appropriate permissions to all GPOs throughout a domain</span></span>**

1.  <span data-ttu-id="b8bc2-110">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="b8bc2-110">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="b8bc2-111">单击 "**域委派**" 选项卡，然后单击 "**高级**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="b8bc2-111">Click the **Domain Delegation** tab, then click the **Advanced** button.</span></span>

3.  <span data-ttu-id="b8bc2-112">在 "**权限**" 对话框中，单击要分配给个人的每个角色对应的复选框，然后单击 "**高级**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="b8bc2-112">In the **Permissions** dialog box, click the check box for each role to be assigned to an individual, and then click the **Advanced** button.</span></span>

    <span data-ttu-id="b8bc2-113">**注意** 编辑者和审批者包括审阅者权限。</span><span class="sxs-lookup"><span data-stu-id="b8bc2-113">**Note** Editor and Approver include Reviewer permissions.</span></span>

     

4.  <span data-ttu-id="b8bc2-114">在 "**高级安全设置**" 对话框中，选择一个组策略管理员，然后单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="b8bc2-114">In the **Advanced Security Settings** dialog box, select a Group Policy administrator, and then click **Edit**.</span></span>

5.  <span data-ttu-id="b8bc2-115">对于 "**应用于**"，请选择 "**此对象和嵌套的对象**"，配置除标准 AGPM 角色之外的任何特殊权限，然后在 "**权限\*\*\*\*条目**" 对话框中单击 **"确定"** 。</span><span class="sxs-lookup"><span data-stu-id="b8bc2-115">For **Apply onto**, select **This object and nested objects**, configure any special permissions beyond the standard AGPM roles, then click **OK** in the **Permission** **Entry** dialog box.</span></span>

6.  <span data-ttu-id="b8bc2-116">在 "**高级安全设置**" 对话框中，单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="b8bc2-116">In the **Advanced Security Settings** dialog box, click **OK**.</span></span>

7.  <span data-ttu-id="b8bc2-117">在 "**权限**" 对话框中，单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="b8bc2-117">In the **Permissions** dialog box, click **OK**.</span></span>

### <span data-ttu-id="b8bc2-118">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="b8bc2-118">Additional considerations</span></span>

-   <span data-ttu-id="b8bc2-119">默认情况下，你必须是 AGPM 管理员（完全控制）才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="b8bc2-119">By default, you must be an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="b8bc2-120">具体说来，您必须具有域的 "**修改安全**权限"。</span><span class="sxs-lookup"><span data-stu-id="b8bc2-120">Specifically, you must have **Modify Security** permission for the domain.</span></span>

-   <span data-ttu-id="b8bc2-121">若要委派使用 AGPM 的组策略管理员的读取访问权限，必须授予它们**列表内容**和**读取设置**权限。</span><span class="sxs-lookup"><span data-stu-id="b8bc2-121">To delegate read access to Group Policy administrators who use AGPM, you must grant them **List Contents** as well as **Read Settings** permissions.</span></span> <span data-ttu-id="b8bc2-122">这使他们能够在 AGPM 的 "**目录**" 选项卡上查看 gpo。</span><span class="sxs-lookup"><span data-stu-id="b8bc2-122">This enables them to view GPOs on the **Contents** tab of AGPM.</span></span> <span data-ttu-id="b8bc2-123">设置要应用于**此对象和嵌套对象**的权限。</span><span class="sxs-lookup"><span data-stu-id="b8bc2-123">Set the permission to apply to **This object and nested objects**.</span></span> <span data-ttu-id="b8bc2-124">其他权限必须明确委派。</span><span class="sxs-lookup"><span data-stu-id="b8bc2-124">Other permissions must be explicitly delegated.</span></span>

-   <span data-ttu-id="b8bc2-125">必须为编辑者授予对 GPO 的已部署副本的 "**读取**" 权限，以充分利用组策略软件安装。</span><span class="sxs-lookup"><span data-stu-id="b8bc2-125">Editors must be granted **Read** permission for the deployed copy of a GPO to make full use of Group Policy Software Installation.</span></span>

-   <span data-ttu-id="b8bc2-126">组策略创建者所有者组的成员身份应受到限制，以便它不会被用于绕过对 Gpo 的访问的 AGPM 管理。</span><span class="sxs-lookup"><span data-stu-id="b8bc2-126">Membership in the Group Policy Creator Owners group should be restricted so that it is not used to circumvent AGPM management of access to GPOs.</span></span> <span data-ttu-id="b8bc2-127">（在**组策略管理控制台**中，单击要在其中管理 gpo 的林和域中的 "**组策略对象**"，单击 "**委派**"，然后配置设置以满足组织的需要。）</span><span class="sxs-lookup"><span data-stu-id="b8bc2-127">(In the **Group Policy Management Console**, click **Group Policy Objects** in the forest and domain in which you want to manage GPOs, click **Delegation**, and then configure the settings to meet the needs of your organization.)</span></span>

### <span data-ttu-id="b8bc2-128">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="b8bc2-128">Additional references</span></span>

-   [<span data-ttu-id="b8bc2-129">执行 AGPM 管理员任务</span><span class="sxs-lookup"><span data-stu-id="b8bc2-129">Performing AGPM Administrator Tasks</span></span>](performing-agpm-administrator-tasks.md)

 

 





