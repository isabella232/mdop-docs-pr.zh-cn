---
title: 委派针对生产环境的访问权限
description: 委派针对生产环境的访问权限
author: dansimp
ms.assetid: c1ebae2e-909b-4e64-b368-b7d3cc67b1eb
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4667a23f1584d7aab6143860721e326da6407afb
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802847"
---
# <span data-ttu-id="85f3a-103">委派针对生产环境的访问权限</span><span class="sxs-lookup"><span data-stu-id="85f3a-103">Delegate Access to the Production Environment</span></span>


<span data-ttu-id="85f3a-104">你可以更改生产环境中的组策略对象（Gpo）的访问权限，替换这些 Gpo 上的任何现有权限。</span><span class="sxs-lookup"><span data-stu-id="85f3a-104">You can change access to Group Policy Objects (GPOs) in the production environment, replacing any existing permissions on those GPOs.</span></span> <span data-ttu-id="85f3a-105">你可以在域级别配置权限，以允许或阻止用户在未使用组策略管理控制台（GPMC）中的 "**更改控制**" 文件夹时编辑、删除或修改生产环境中的 gpo 的安全。</span><span class="sxs-lookup"><span data-stu-id="85f3a-105">You can configure permissions at the domain level to either allow or prevent users from editing, deleting, or modifying the security of GPOs in the production environment when they are not using the **Change Control** folder in the Group Policy Management Console (GPMC).</span></span>

**<span data-ttu-id="85f3a-106">注意</span><span class="sxs-lookup"><span data-stu-id="85f3a-106">Note</span></span>**  
-   <span data-ttu-id="85f3a-107">委派对生产环境的访问权限不会影响用户链接 Gpo 的能力。</span><span class="sxs-lookup"><span data-stu-id="85f3a-107">Delegating access to the production environment does not affect users’ ability to link GPOs.</span></span>

-   <span data-ttu-id="85f3a-108">当 Gpo 受控制或部署时，将删除除具有 "**读取**" 和 "**应用**" 权限的帐户之外的任何其他帐户的访问权限。</span><span class="sxs-lookup"><span data-stu-id="85f3a-108">When GPOs are controlled or deployed, access for any other accounts except those with **Read** and **Apply** permissions is removed.</span></span>

 

<span data-ttu-id="85f3a-109">要完成此过程，必须具有高级组策略管理（AGPM）中的必要权限或 AGPM 管理员（完全控制）角色的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="85f3a-109">A user account that has either the necessary permissions in Advanced Group Policy Management (AGPM) or the role of AGPM Administrator (Full Control) is required to complete this procedure.</span></span> <span data-ttu-id="85f3a-110">查看本主题中 "其他注意事项" 中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="85f3a-110">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="85f3a-111">更改对生产环境中的 Gpo 的访问权限</span><span class="sxs-lookup"><span data-stu-id="85f3a-111">To change access to GPOs in the production environment</span></span>**

1.  <span data-ttu-id="85f3a-112">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="85f3a-112">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="85f3a-113">单击 "**生产委派**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="85f3a-113">Click the **Production Delegation** tab.</span></span>

3.  <span data-ttu-id="85f3a-114">若要为无权访问生产环境的用户或组添加权限，或者替换具有访问权限的用户或组的权限，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="85f3a-114">To add permissions for a user or group that does not have access to the production environment, or to replace the permissions for a user or group that does have access:</span></span>

    1.  <span data-ttu-id="85f3a-115">单击 "**添加**"，选择用户或组，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="85f3a-115">Click **Add**, select a user or group, and then click **OK**.</span></span>

    2.  <span data-ttu-id="85f3a-116">为生产环境选择要委派给该用户或组的权限，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="85f3a-116">Select permissions to delegate to that user or group for the production environment, and then click **OK**.</span></span>

4.  <span data-ttu-id="85f3a-117">若要删除用户或组对生产环境的所有权限，请选择该用户或组，单击 "**删除**"，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="85f3a-117">To remove all permissions to the production environment for a user or group, select the user or group, click **Remove**, and then click **OK**.</span></span>

### <span data-ttu-id="85f3a-118">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="85f3a-118">Additional considerations</span></span>

-   <span data-ttu-id="85f3a-119">默认情况下，你必须是 AGPM 管理员（完全控制）才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="85f3a-119">By default, you must be an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="85f3a-120">具体说来，您必须具有域的 "**修改安全**权限"。</span><span class="sxs-lookup"><span data-stu-id="85f3a-120">Specifically, you must have **Modify Security** permission for the domain.</span></span>

-   <span data-ttu-id="85f3a-121">无法在 "**生产委派**" 选项卡上更改 AGPM 服务帐户的权限。</span><span class="sxs-lookup"><span data-stu-id="85f3a-121">Permissions for the AGPM Service Account cannot be changed on the **Production Delegation** tab.</span></span>

-   <span data-ttu-id="85f3a-122">默认情况下，以下帐户具有生产环境中的 Gpo 的权限：</span><span class="sxs-lookup"><span data-stu-id="85f3a-122">By default, the following accounts have permissions for GPOs in the production environment:</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="85f3a-123">帐户</span><span class="sxs-lookup"><span data-stu-id="85f3a-123">Account</span></span></th>
    <th align="left"><span data-ttu-id="85f3a-124">Gpo 的默认权限</span><span class="sxs-lookup"><span data-stu-id="85f3a-124">Default Permissions for GPOs</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="85f3a-125">&lt;AGPM 服务帐户&gt;</span><span class="sxs-lookup"><span data-stu-id="85f3a-125">&lt;AGPM Service Account&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="85f3a-126">编辑设置、删除、修改安全性</span><span class="sxs-lookup"><span data-stu-id="85f3a-126">Edit Settings, Delete, Modify Security</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="85f3a-127">经过身份验证的用户</span><span class="sxs-lookup"><span data-stu-id="85f3a-127">Authenticated Users</span></span></p></td>
    <td align="left"><p><span data-ttu-id="85f3a-128">阅读、应用</span><span class="sxs-lookup"><span data-stu-id="85f3a-128">Read, Apply</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="85f3a-129">域管理员</span><span class="sxs-lookup"><span data-stu-id="85f3a-129">Domain Admins</span></span></p></td>
    <td align="left"><p><span data-ttu-id="85f3a-130">编辑设置、删除、修改安全性</span><span class="sxs-lookup"><span data-stu-id="85f3a-130">Edit Settings, Delete, Modify Security</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="85f3a-131">企业管理员</span><span class="sxs-lookup"><span data-stu-id="85f3a-131">Enterprise Admins</span></span></p></td>
    <td align="left"><p><span data-ttu-id="85f3a-132">编辑设置、删除、修改安全性</span><span class="sxs-lookup"><span data-stu-id="85f3a-132">Edit Settings, Delete, Modify Security</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="85f3a-133">企业域控制器</span><span class="sxs-lookup"><span data-stu-id="85f3a-133">Enterprise Domain Controllers</span></span></p></td>
    <td align="left"><p><span data-ttu-id="85f3a-134">已阅读</span><span class="sxs-lookup"><span data-stu-id="85f3a-134">Read</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="85f3a-135">系统</span><span class="sxs-lookup"><span data-stu-id="85f3a-135">System</span></span></p></td>
    <td align="left"><p><span data-ttu-id="85f3a-136">编辑设置、删除、修改安全性</span><span class="sxs-lookup"><span data-stu-id="85f3a-136">Edit Settings, Delete, Modify Security</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

-   <span data-ttu-id="85f3a-137">组策略创建者所有者组的成员身份应受到限制，soit 不会用于绕过对 Gpo 的访问的 AGPM 管理。</span><span class="sxs-lookup"><span data-stu-id="85f3a-137">Membership in the Group Policy Creator Owners group should be restricted, soit is not used to circumvent AGPM management of access to GPOs.</span></span> <span data-ttu-id="85f3a-138">（在**组策略管理控制台**中，单击要在其中管理 gpo 的林和域中的 "**组策略对象**"，单击 "**委派**"，然后配置设置以满足组织的需要。）</span><span class="sxs-lookup"><span data-stu-id="85f3a-138">(In the **Group Policy Management Console**, click **Group Policy Objects** in the forest and domain in which you want to manage GPOs, click **Delegation**, and then configure the settings to meet the needs of your organization.)</span></span>

### <span data-ttu-id="85f3a-139">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="85f3a-139">Additional references</span></span>

-   [<span data-ttu-id="85f3a-140">配置高级组策略管理</span><span class="sxs-lookup"><span data-stu-id="85f3a-140">Configuring Advanced Group Policy Management</span></span>](configuring-advanced-group-policy-management.md)

 

 





