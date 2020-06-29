---
title: “域委派”选项卡
description: “域委派”选项卡
author: dansimp
ms.assetid: 523cdf39-f4b8-4d20-a917-3485756658ce
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 86202b7a441946afe3f76c387e783287db192443
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801899"
---
# <span data-ttu-id="4bbe4-103">“域委派”选项卡</span><span class="sxs-lookup"><span data-stu-id="4bbe4-103">Domain Delegation Tab</span></span>


<span data-ttu-id="4bbe4-104">"**更改控制**" 窗格上的 "**域委派**" 选项卡提供了组策略管理员的列表，这些管理员对存档具有域级别的访问权限，并指明每个组的角色。</span><span class="sxs-lookup"><span data-stu-id="4bbe4-104">The **Domain Delegation** tab on the **Change Control** pane provides a list of Group Policy administrators who have domain-level access to the archive and indicates the roles of each.</span></span> <span data-ttu-id="4bbe4-105">此外，此选项卡允许 AGPM 管理员（完全控制）为编辑者、审批者、审阅者和其他 AGPM 管理员配置域级别的权限。</span><span class="sxs-lookup"><span data-stu-id="4bbe4-105">Additionally, this tab enables AGPM Administrators (Full Control) to configure domain-level permissions for Editors, Approvers, Reviewers, and other AGPM Administrators.</span></span> <span data-ttu-id="4bbe4-106">"**域委派**" 选项卡上有两个部分：配置电子邮件通知和域级别的高级组策略管理（AGPM）的基于角色的委派。</span><span class="sxs-lookup"><span data-stu-id="4bbe4-106">There are two sections on the **Domain Delegation** tab—configuration of e-mail notification and role-based delegation for Advanced Group Policy Management (AGPM) at the domain level.</span></span>

## <span data-ttu-id="4bbe4-107">电子邮件通知配置</span><span class="sxs-lookup"><span data-stu-id="4bbe4-107">Configuration of e-mail notification</span></span>


<span data-ttu-id="4bbe4-108">此选项卡的 "电子邮件通知" 部分标识当 AGPM 中的操作处于挂起状态时，将收到通知的审批者。</span><span class="sxs-lookup"><span data-stu-id="4bbe4-108">The e-mail notification section of this tab identifies the Approvers that will receive notification when operations are pending in AGPM.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4bbe4-109">设置</span><span class="sxs-lookup"><span data-stu-id="4bbe4-109">Setting</span></span></th>
<th align="left"><span data-ttu-id="4bbe4-110">描述</span><span class="sxs-lookup"><span data-stu-id="4bbe4-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="4bbe4-111">发件人电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="4bbe4-111">From e-mail address</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="4bbe4-112">将通知发送到审批者的 AGPM 别名。</span><span class="sxs-lookup"><span data-stu-id="4bbe4-112">The AGPM alias from which notification is sent to Approvers.</span></span> <span data-ttu-id="4bbe4-113">在具有多个域的环境中，这可以是整个环境中的相同别名，也可以是每个域的不同别名。</span><span class="sxs-lookup"><span data-stu-id="4bbe4-113">In an environment with multiple domains, this can be the same alias throughout the environment or a different alias for each domain.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="4bbe4-114">收件人电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="4bbe4-114">To e-mail address</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="4bbe4-115">要向其发送通知的审批者的电子邮件地址的逗号分隔列表</span><span class="sxs-lookup"><span data-stu-id="4bbe4-115">A comma-delimited list of e-mail addresses of Approvers to whom notification is to be sent</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="4bbe4-116">SMTP 服务器</span><span class="sxs-lookup"><span data-stu-id="4bbe4-116">SMTP server</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="4bbe4-117">电子邮件服务器的名称，例如 mail.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4bbe4-117">The name of the e-mail server, such as mail.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="4bbe4-118">用户名</span><span class="sxs-lookup"><span data-stu-id="4bbe4-118">User name</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="4bbe4-119">对 SMTP 服务器具有访问权限的用户</span><span class="sxs-lookup"><span data-stu-id="4bbe4-119">A user with access to the SMTP server</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="4bbe4-120">密码</span><span class="sxs-lookup"><span data-stu-id="4bbe4-120">Password</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="4bbe4-121">SMTP 服务器身份验证的用户密码</span><span class="sxs-lookup"><span data-stu-id="4bbe4-121">User's password for authentication to the SMTP server</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="4bbe4-122">确认密码</span><span class="sxs-lookup"><span data-stu-id="4bbe4-122">Confirm password</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="4bbe4-123">确认用户密码</span><span class="sxs-lookup"><span data-stu-id="4bbe4-123">Confirm user's password</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="4bbe4-124">域级基于角色的委派</span><span class="sxs-lookup"><span data-stu-id="4bbe4-124">Domain-level role-based delegation</span></span>


<span data-ttu-id="4bbe4-125">将显示此选项卡的 "基于角色的委派" 部分，并允许 AGPM 管理员为域上的每个组和用户委派对存档的访问权限，从而允许、拒绝和继承的权限。</span><span class="sxs-lookup"><span data-stu-id="4bbe4-125">The role-based delegation section of this tab displays and enables an AGPM Administrator to delegate allowed, denied, and inherited permissions for each group and user on the domain with access to the archive.</span></span> <span data-ttu-id="4bbe4-126">AGPM 管理员可以使用标准 AGPM 角色（编辑、审批者、审阅者和 AGPM 管理员）或每个组策略管理员的自定义权限组合来配置域范围权限。</span><span class="sxs-lookup"><span data-stu-id="4bbe4-126">An AGPM Administrator can configure domain-wide permissions using either standard AGPM roles (Editor, Approver, Reviewer, and AGPM Administrator) or a customized combination of permissions for each Group Policy administrator.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4bbe4-127">按钮</span><span class="sxs-lookup"><span data-stu-id="4bbe4-127">Button</span></span></th>
<th align="left"><span data-ttu-id="4bbe4-128">作用</span><span class="sxs-lookup"><span data-stu-id="4bbe4-128">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="4bbe4-129">添加</span><span class="sxs-lookup"><span data-stu-id="4bbe4-129">Add</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="4bbe4-130">将新条目添加到安全描述符中。</span><span class="sxs-lookup"><span data-stu-id="4bbe4-130">Add a new entry to the security descriptor.</span></span> <span data-ttu-id="4bbe4-131">Active Directory 中的任何用户或组都可以添加为组策略管理员。</span><span class="sxs-lookup"><span data-stu-id="4bbe4-131">Any users or groups in Active Directory can be added as Group Policy administrators.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="4bbe4-132">删除</span><span class="sxs-lookup"><span data-stu-id="4bbe4-132">Remove</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="4bbe4-133">从访问控制列表中删除所选组策略管理员。</span><span class="sxs-lookup"><span data-stu-id="4bbe4-133">Remove the selected Group Policy administrators from the Access Control List.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="4bbe4-134">属性</span><span class="sxs-lookup"><span data-stu-id="4bbe4-134">Properties</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="4bbe4-135">显示所选组策略管理员的属性。</span><span class="sxs-lookup"><span data-stu-id="4bbe4-135">Display the properties for the selected Group Policy administrators.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="4bbe4-136">高级</span><span class="sxs-lookup"><span data-stu-id="4bbe4-136">Advanced</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="4bbe4-137">打开 " <strong> 访问控制列表编辑器" </strong> 。</span><span class="sxs-lookup"><span data-stu-id="4bbe4-137">Open the <strong>Access Control List Editor</strong>.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="4bbe4-138">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="4bbe4-138">Additional considerations</span></span>

-   <span data-ttu-id="4bbe4-139">有关与特定任务相关的角色和权限的信息，请参阅[执行 AGPM 管理员任务](performing-agpm-administrator-tasks-agpm30ops.md)、[执行编辑任务](performing-editor-tasks-agpm30ops.md)、[执行审批者任务](performing-approver-tasks-agpm30ops.md)和[执行审阅者任务](performing-reviewer-tasks-agpm30ops.md)中的任务。</span><span class="sxs-lookup"><span data-stu-id="4bbe4-139">For information about roles and permissions related to specific tasks, see the tasks under [Performing AGPM Administrator Tasks](performing-agpm-administrator-tasks-agpm30ops.md), [Performing Editor Tasks](performing-editor-tasks-agpm30ops.md), [Performing Approver Tasks](performing-approver-tasks-agpm30ops.md), and [Performing Reviewer Tasks](performing-reviewer-tasks-agpm30ops.md).</span></span>

### <span data-ttu-id="4bbe4-140">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="4bbe4-140">Additional references</span></span>

-   [<span data-ttu-id="4bbe4-141">用户界面：高级组策略管理</span><span class="sxs-lookup"><span data-stu-id="4bbe4-141">User Interface: Advanced Group Policy Management</span></span>](user-interface-advanced-group-policy-management-agpm30ops.md)

-   [<span data-ttu-id="4bbe4-142">执行 AGPM 管理员任务</span><span class="sxs-lookup"><span data-stu-id="4bbe4-142">Performing AGPM Administrator Tasks</span></span>](performing-agpm-administrator-tasks-agpm30ops.md)

 

 





