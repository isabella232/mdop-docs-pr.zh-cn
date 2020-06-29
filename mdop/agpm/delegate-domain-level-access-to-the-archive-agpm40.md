---
title: 委派针对存档的域级访问权限
description: 委派针对存档的域级访问权限
author: dansimp
ms.assetid: 11ca1d40-4b5c-496e-8922-d01412717858
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b33c0ec8821248ab4eddc051e67e7f0e6c073a9e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801931"
---
# <span data-ttu-id="88ad8-103">委派针对存档的域级访问权限</span><span class="sxs-lookup"><span data-stu-id="88ad8-103">Delegate Domain-Level Access to the Archive</span></span>


<span data-ttu-id="88ad8-104">为你的环境设置委派，以便组策略管理员对存档中的组策略对象（Gpo）具有适当的访问权限和控制权限。</span><span class="sxs-lookup"><span data-stu-id="88ad8-104">Set up delegation for your environment so that Group Policy administrators have the appropriate access to and control over Group Policy Objects (GPOs) in the archive.</span></span> <span data-ttu-id="88ad8-105">你可以应用基准权限，使操作更高效。</span><span class="sxs-lookup"><span data-stu-id="88ad8-105">There are baseline permissions you can apply to make operation more efficient.</span></span> <span data-ttu-id="88ad8-106">你可以采用满足组织需求的任何方式授予权限。</span><span class="sxs-lookup"><span data-stu-id="88ad8-106">You can grant permissions in any manner that meets the needs of your organization.</span></span>

<span data-ttu-id="88ad8-107">需要具有 AGPM 管理员（完全控制）角色的用户帐户或高级组策略管理（AGPM）中的必需权限才能完成此过程。</span><span class="sxs-lookup"><span data-stu-id="88ad8-107">A user account with the AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="88ad8-108">查看本主题中 "其他注意事项" 中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="88ad8-108">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="88ad8-109">委派访问权限，以便用户和组对整个域中的所有 Gpo 具有适当的权限</span><span class="sxs-lookup"><span data-stu-id="88ad8-109">To delegate access so that users and groups have appropriate permissions to all GPOs throughout a domain</span></span>**

1.  <span data-ttu-id="88ad8-110">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="88ad8-110">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="88ad8-111">单击 "**域委派**" 选项卡，并配置对域中所有 gpo 的访问权限：</span><span class="sxs-lookup"><span data-stu-id="88ad8-111">Click the **Domain Delegation** tab, and configure access to all GPOs in the domain:</span></span>

    1.  <span data-ttu-id="88ad8-112">若要为用户或组添加访问权限，请单击 "**添加**" 按钮，选择用户或组，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="88ad8-112">To add access for a user or group, click the **Add** button, select the user or group, and click **OK**.</span></span> <span data-ttu-id="88ad8-113">在 "**添加组" 或 "用户**" 对话框中，选择一个角色，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="88ad8-113">In the **Add Group or User** dialog box, select a role and click **OK**.</span></span>

    2.  <span data-ttu-id="88ad8-114">若要删除用户或组的访问权限，请选择该用户或组，然后单击 "**删除**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="88ad8-114">To remove access for a user or group, select the user or group, and click the **Remove** button.</span></span>

    3.  <span data-ttu-id="88ad8-115">若要修改委派给用户或组的角色和权限，请选择 "**高级**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="88ad8-115">To modify the roles and permissions delegated to a user or group, select click the **Advanced** button.</span></span> <span data-ttu-id="88ad8-116">在 "**权限**" 对话框中，选择 "用户" 或 "组"，选中要分配给该用户或组的每个角色的复选框，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="88ad8-116">In the **Permissions** dialog box, select the user or group, select the check box for each role to be assigned to that user or group, and then click **OK**.</span></span>

        <span data-ttu-id="88ad8-117">**注意** 编辑者和审批者包括审阅者权限。</span><span class="sxs-lookup"><span data-stu-id="88ad8-117">**Note** Editor and Approver include Reviewer permissions.</span></span>

         

### <span data-ttu-id="88ad8-118">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="88ad8-118">Additional considerations</span></span>

-   <span data-ttu-id="88ad8-119">默认情况下，你必须是 AGPM 管理员（完全控制）才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="88ad8-119">By default, you must be an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="88ad8-120">具体说来，您必须具有域的 "**修改安全**权限"。</span><span class="sxs-lookup"><span data-stu-id="88ad8-120">Specifically, you must have **Modify Security** permission for the domain.</span></span>

-   <span data-ttu-id="88ad8-121">若要委派使用 AGPM 的组策略管理员的读取访问权限，必须授予它们**列表内容**和**读取设置**权限。</span><span class="sxs-lookup"><span data-stu-id="88ad8-121">To delegate read access to Group Policy administrators who use AGPM, you must grant them **List Contents** as well as **Read Settings** permissions.</span></span> <span data-ttu-id="88ad8-122">这使他们能够在 AGPM 的 "**目录**" 选项卡上查看 gpo。</span><span class="sxs-lookup"><span data-stu-id="88ad8-122">This enables them to view GPOs on the **Contents** tab of AGPM.</span></span> <span data-ttu-id="88ad8-123">其他权限必须明确委派。</span><span class="sxs-lookup"><span data-stu-id="88ad8-123">Other permissions must be explicitly delegated.</span></span>

-   <span data-ttu-id="88ad8-124">必须为编辑者授予对 GPO 的已部署副本的 "**读取**" 权限，以充分利用组策略软件安装。</span><span class="sxs-lookup"><span data-stu-id="88ad8-124">Editors must be granted **Read** permission for the deployed copy of a GPO to make full use of Group Policy Software Installation.</span></span>

-   <span data-ttu-id="88ad8-125">组策略创建者所有者组的成员身份应受到限制，soit 不会用于绕过对 Gpo 的访问的 AGPM 管理。</span><span class="sxs-lookup"><span data-stu-id="88ad8-125">Membership in the Group Policy Creator Owners group should be restricted, soit is not used to circumvent AGPM management of access to GPOs.</span></span> <span data-ttu-id="88ad8-126">（在**组策略管理控制台**中，单击要在其中管理 gpo 的林和域中的 "**组策略对象**"，单击 "**委派**"，然后配置设置以满足组织的需要。）</span><span class="sxs-lookup"><span data-stu-id="88ad8-126">(In the **Group Policy Management Console**, click **Group Policy Objects** in the forest and domain in which you want to manage GPOs, click **Delegation**, and then configure the settings to meet the needs of your organization.)</span></span>

### <span data-ttu-id="88ad8-127">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="88ad8-127">Additional references</span></span>

-   [<span data-ttu-id="88ad8-128">管理存档</span><span class="sxs-lookup"><span data-stu-id="88ad8-128">Managing the Archive</span></span>](managing-the-archive-agpm40.md)

 

 





