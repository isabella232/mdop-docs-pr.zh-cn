---
title: 配置 AGPM 服务器连接
description: 配置 AGPM 服务器连接
author: dansimp
ms.assetid: bbbb15e8-35e7-403c-b695-7a6ebeb87839
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9b6b065b9855c6edf44456026baa32e8d9a4674f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802071"
---
# <span data-ttu-id="21ac1-103">配置 AGPM 服务器连接</span><span class="sxs-lookup"><span data-stu-id="21ac1-103">Configure AGPM Server Connections</span></span>


<span data-ttu-id="21ac1-104">每个受控制的组策略对象（GPO）的所有版本都存储在一个中央存档中，以便组策略管理员可以脱机查看和修改 Gpo，而不会立即影响每个 GPO 的已部署版本。</span><span class="sxs-lookup"><span data-stu-id="21ac1-104">All versions of each controlled Group Policy Object (GPO) are stored in a central archive so that Group Policy administrators can view and modify GPOs offline without immediately impacting the deployed version of each GPO.</span></span>

<span data-ttu-id="21ac1-105">具有 AGPM 管理员（完全控制）角色的用户帐户、创建在这些过程中使用的 GPO 的审批者的用户帐户，或者需要高级组策略管理（AGPM）中具有必要权限的用户帐户才能完成为所有组策略管理员集中配置存档位置的这些过程。</span><span class="sxs-lookup"><span data-stu-id="21ac1-105">A user account with the AGPM Administrator (Full Control) role, the user account of the Approver who created the GPO used in these procedures, or a user account with the necessary permissions in Advanced Group Policy Management (AGPM) is required to complete these procedures for centrally configuring archive locations for all Group Policy administrators.</span></span> <span data-ttu-id="21ac1-106">查看本主题中 "其他注意事项" 中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="21ac1-106">Review the details in "Additional considerations" in this topic.</span></span>

## <span data-ttu-id="21ac1-107">配置 AGPM 服务器连接</span><span class="sxs-lookup"><span data-stu-id="21ac1-107">Configuring AGPM Server connections</span></span>


<span data-ttu-id="21ac1-108">作为 AGPM 管理员，你可以通过集中配置关联的设置来确保所有组策略管理员都连接到同一 AGPM 服务器。</span><span class="sxs-lookup"><span data-stu-id="21ac1-108">As an AGPM Administrator, you can ensure that all Group Policy administrators connect to the same AGPM Server by centrally configuring the associated setting.</span></span> <span data-ttu-id="21ac1-109">如果你的环境需要某些或所有域的单独的 AGPM 服务器，请将这些其他 AGPM 服务器配置为默认的例外。</span><span class="sxs-lookup"><span data-stu-id="21ac1-109">If your environment requires separate AGPM Servers for some or all domains, configure those additional AGPM Servers as exceptions to the default.</span></span> <span data-ttu-id="21ac1-110">如果未集中配置 AGPM 服务器连接，则每个组策略管理员必须手动配置要为每个域显示的 AGPM 服务器。</span><span class="sxs-lookup"><span data-stu-id="21ac1-110">If you do not centrally configure AGPM Server connections, each Group Policy administrator must manually configure the AGPM Server to be displayed for each domain.</span></span>

-   [<span data-ttu-id="21ac1-111">为所有组策略管理员配置 AGPM 服务器连接</span><span class="sxs-lookup"><span data-stu-id="21ac1-111">Configure an AGPM Server connection for all Group Policy administrators</span></span>](#bkmk-defaultarchiveloc)

-   [<span data-ttu-id="21ac1-112">为所有组策略管理员配置其他 AGPM 服务器连接</span><span class="sxs-lookup"><span data-stu-id="21ac1-112">Configure additional AGPM Server connections for all Group Policy administrators</span></span>](#bkmk-additionalarchiveloc)

-   [<span data-ttu-id="21ac1-113">为你的帐户手动配置 AGPM 服务器连接</span><span class="sxs-lookup"><span data-stu-id="21ac1-113">Manually configure an AGPM Server connection for your account</span></span>](#bkmk-manuallyconfigurearchiveloc)

### <a href="" id="bkmk-defaultarchiveloc"></a>

**<span data-ttu-id="21ac1-114">为所有组策略管理员配置 AGPM 服务器连接</span><span class="sxs-lookup"><span data-stu-id="21ac1-114">To configure an AGPM Server connection for all Group Policy administrators</span></span>**

1.  <span data-ttu-id="21ac1-115">在**组策略管理控制台**树中，编辑应用到所有组策略管理员的 GPO。</span><span class="sxs-lookup"><span data-stu-id="21ac1-115">In the **Group Policy Management Console** tree, edit a GPO that is applied to all Group Policy administrators.</span></span> <span data-ttu-id="21ac1-116">（有关详细信息，请参阅[编辑 GPO](editing-a-gpo-agpm40.md)。）</span><span class="sxs-lookup"><span data-stu-id="21ac1-116">(For more information, see [Editing a GPO](editing-a-gpo-agpm40.md).)</span></span>

2.  <span data-ttu-id="21ac1-117">在**组策略管理编辑器**窗口中，单击 "**用户配置**"、"**策略**"、"**管理模板**"、" **Windows 组件**" 和 " **AGPM**"。</span><span class="sxs-lookup"><span data-stu-id="21ac1-117">In the **Group Policy Management Editor** window, click **User Configuration**, **Policies**, **Administrative Templates**, **Windows Components**, and **AGPM**.</span></span>

3.  <span data-ttu-id="21ac1-118">在 "详细信息" 窗格中，双击 " **AGPM：指定默认 Agpm 服务器（所有域）**"。</span><span class="sxs-lookup"><span data-stu-id="21ac1-118">In the details pane, double-click **AGPM: Specify default AGPM Server (all domains)**.</span></span>

4.  <span data-ttu-id="21ac1-119">在 "**属性**" 窗口中，选中 "**已启用**" 复选框，然后键入完全限定的计算机名称和端口（例如，server.contoso.com:4600）。</span><span class="sxs-lookup"><span data-stu-id="21ac1-119">In the **Properties** window, select the **Enabled** check box, and type the fully-qualified computer name and port (for example, server.contoso.com:4600).</span></span>

5.  <span data-ttu-id="21ac1-120">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="21ac1-120">Click **OK**.</span></span> <span data-ttu-id="21ac1-121">除非你想要配置其他 AGPM 服务器连接，否则请关闭 "**组策略管理编辑器**" 窗口并部署 GPO。</span><span class="sxs-lookup"><span data-stu-id="21ac1-121">Unless you want to configure additional AGPM Server connections, close the **Group Policy Management Editor** window and deploy the GPO.</span></span> <span data-ttu-id="21ac1-122">（有关详细信息，请参阅[部署 GPO](deploy-a-gpo-agpm40.md)。）更新组策略时，将为所有组策略管理员配置 AGPM 服务器连接。</span><span class="sxs-lookup"><span data-stu-id="21ac1-122">(For more information, see [Deploy a GPO](deploy-a-gpo-agpm40.md).) When Group Policy is updated, the AGPM Server connection is configured for all Group Policy administrators.</span></span>

### <a href="" id="bkmk-additionalarchiveloc"></a>

**<span data-ttu-id="21ac1-123">为所有组策略管理员配置其他 AGPM 服务器连接</span><span class="sxs-lookup"><span data-stu-id="21ac1-123">To configure additional AGPM Server connections for all Group Policy administrators</span></span>**

1.  <span data-ttu-id="21ac1-124">如果尚未配置 AGPM 服务器连接，请按照上述步骤为所有域配置默认的 AGPM 服务器。</span><span class="sxs-lookup"><span data-stu-id="21ac1-124">If no AGPM Server connection has been configured, follow the preceding procedure to configure a default AGPM Server for all domains.</span></span>

2.  <span data-ttu-id="21ac1-125">若要为部分或所有域配置单独的 AGPM 服务器（替代默认的 AGPM 服务器），请在**组策略管理控制台**树中，编辑应用到所有组策略管理员的 GPO。</span><span class="sxs-lookup"><span data-stu-id="21ac1-125">To configure separate AGPM Servers for some or all domains (overriding the default AGPM Server), in the **Group Policy Management Console** tree, edit a GPO that is applied to all Group Policy administrators.</span></span> <span data-ttu-id="21ac1-126">（有关详细信息，请参阅[编辑 GPO](editing-a-gpo-agpm40.md)。）</span><span class="sxs-lookup"><span data-stu-id="21ac1-126">(For more information, see [Editing a GPO](editing-a-gpo-agpm40.md).)</span></span>

3.  <span data-ttu-id="21ac1-127">在 "**组策略管理编辑器**" 窗口中，单击 "**用户配置**"、"**策略**"、"**管理模板**"、" **Windows 组件**" 和 " **AGPM**"。</span><span class="sxs-lookup"><span data-stu-id="21ac1-127">In the **Group Policy Management Editor** window, click **User Configuration**, **Policies**, **Administrative Templates**, **Windows Components**, and then **AGPM**.</span></span>

4.  <span data-ttu-id="21ac1-128">在 "详细信息" 窗格中，双击 " **agpm：指定 Agpm 服务器**"。</span><span class="sxs-lookup"><span data-stu-id="21ac1-128">In the details pane, double-click **AGPM: Specify AGPM Servers**.</span></span>

5.  <span data-ttu-id="21ac1-129">在 "**属性**" 窗口中，选中 "**已启用**" 复选框，然后单击 "**显示**"。</span><span class="sxs-lookup"><span data-stu-id="21ac1-129">In the **Properties** window, select the **Enabled** check box, and click **Show**.</span></span>

6.  <span data-ttu-id="21ac1-130">在 "**显示内容**" 窗口中：</span><span class="sxs-lookup"><span data-stu-id="21ac1-130">In the **Show Contents** window:</span></span>

    1.  <span data-ttu-id="21ac1-131">单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="21ac1-131">Click **Add**.</span></span>

    2.  <span data-ttu-id="21ac1-132">对于 "**值名称**"，请键入域名（例如，server1.contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="21ac1-132">For **Value Name**, type the domain name (for example, server1.contoso.com).</span></span>

    3.  <span data-ttu-id="21ac1-133">对于 "**值**"，请键入要用于此域的 AGPM 服务器名称和端口（例如，server2.contoso.com:4600），然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="21ac1-133">For **Value**, type the AGPM Server name and port to use for this domain (for example, server2.contoso.com:4600), and then click **OK**.</span></span> <span data-ttu-id="21ac1-134">（默认情况下，AGPM 服务在端口4600上侦听。</span><span class="sxs-lookup"><span data-stu-id="21ac1-134">(By default, the AGPM Service listens on port 4600.</span></span> <span data-ttu-id="21ac1-135">若要使用其他端口，请参阅[修改 AGPM 服务](modify-the-agpm-service-agpm40.md)。</span><span class="sxs-lookup"><span data-stu-id="21ac1-135">To use a different port, see [Modify the AGPM Service](modify-the-agpm-service-agpm40.md).)</span></span>

    4.  <span data-ttu-id="21ac1-136">对不使用默认 AGPM 服务器的每个域重复此操作。</span><span class="sxs-lookup"><span data-stu-id="21ac1-136">Repeat for each domain not using the default AGPM Server.</span></span>

7.  <span data-ttu-id="21ac1-137">单击 **"确定"** 以关闭 "**显示内容**和**属性**" 窗口。</span><span class="sxs-lookup"><span data-stu-id="21ac1-137">Click **OK** to close the **Show Contents** and **Properties** windows.</span></span>

8.  <span data-ttu-id="21ac1-138">关闭 "**组策略管理编辑器**" 窗口。</span><span class="sxs-lookup"><span data-stu-id="21ac1-138">Close the **Group Policy Management Editor** window.</span></span> <span data-ttu-id="21ac1-139">（有关详细信息，请参阅[部署 GPO](deploy-a-gpo-agpm40.md)。）更新组策略时，将为所有组策略管理员配置新的 AGPM 服务器连接。</span><span class="sxs-lookup"><span data-stu-id="21ac1-139">(For more information, see [Deploy a GPO](deploy-a-gpo-agpm40.md).) When Group Policy is updated, the new AGPM Server connections are configured for all Group Policy administrators.</span></span>

### <a href="" id="bkmk-manuallyconfigurearchiveloc"></a>

<span data-ttu-id="21ac1-140">如果已集中配置 AGPM 服务器连接，则用于手动配置它的选项对所有组策略管理员不可用。</span><span class="sxs-lookup"><span data-stu-id="21ac1-140">If you have centrally configured the AGPM Server connection, the option to manually configure it is unavailable for all Group Policy administrators.</span></span>

**<span data-ttu-id="21ac1-141">手动配置要为你的帐户显示的 AGPM 服务器</span><span class="sxs-lookup"><span data-stu-id="21ac1-141">To manually configure which AGPM Server to display for your account</span></span>**

1.  <span data-ttu-id="21ac1-142">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="21ac1-142">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="21ac1-143">在 "详细信息" 窗格中，单击 " **AGPM 服务器**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="21ac1-143">In the details pane, click the **AGPM Server** tab.</span></span>

3.  <span data-ttu-id="21ac1-144">输入用于管理用于此域的存档的 AGPM 服务器的完全限定计算机名（例如，server.contoso.com）和 AGPM 服务侦听的端口（默认情况下为端口4600）。</span><span class="sxs-lookup"><span data-stu-id="21ac1-144">Enter the fully-qualified computer name for the AGPM Server that manages the archive used for this domain (for example, server.contoso.com) and the port on which the AGPM Service listens (by default, port 4600).</span></span>

4.  <span data-ttu-id="21ac1-145">单击 "**应用**"，然后单击 **"是"** 进行确认。</span><span class="sxs-lookup"><span data-stu-id="21ac1-145">Click **Apply**, then click **Yes** to confirm.</span></span>

### <span data-ttu-id="21ac1-146">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="21ac1-146">Additional considerations</span></span>

-   <span data-ttu-id="21ac1-147">你必须能够编辑和部署 GPO，才能执行为所有组策略管理员集中配置 AGPM 服务器连接的过程。</span><span class="sxs-lookup"><span data-stu-id="21ac1-147">You must be able to edit and deploy a GPO to perform the procedures for centrally configuring AGPM Server connections for all Group Policy administrators.</span></span> <span data-ttu-id="21ac1-148">有关其他详细信息，请参阅[编辑 gpo](editing-a-gpo-agpm40.md)和[部署 gpo](deploy-a-gpo-agpm40.md) 。</span><span class="sxs-lookup"><span data-stu-id="21ac1-148">See [Editing a GPO](editing-a-gpo-agpm40.md) and [Deploy a GPO](deploy-a-gpo-agpm40.md) for additional detail.</span></span>

-   <span data-ttu-id="21ac1-149">所选的 AGPM 服务器确定在 "**目录**" 选项卡上显示哪些 gpo 以及应用 "**域委派**" 选项卡设置的位置。</span><span class="sxs-lookup"><span data-stu-id="21ac1-149">The selected AGPM Server determines which GPOs are displayed on the **Contents** tab and to what location the **Domain Delegation** tab settings are applied.</span></span> <span data-ttu-id="21ac1-150">如果不是通过管理模板进行集中管理，则每个组策略管理员必须将此设置配置为指向域的 AGPM 服务器。</span><span class="sxs-lookup"><span data-stu-id="21ac1-150">If not centrally managed through the Administrative template, each Group Policy administrator must configure this setting to point to the AGPM Server for the domain.</span></span>

-   <span data-ttu-id="21ac1-151">组策略创建者所有者组的成员身份应受到限制，soit 不会用于绕过对 Gpo 的访问的 AGPM 管理。</span><span class="sxs-lookup"><span data-stu-id="21ac1-151">Membership in the Group Policy Creator Owners group should be restricted, soit is not used to circumvent AGPM management of access to GPOs.</span></span> <span data-ttu-id="21ac1-152">（在**组策略管理控制台**中，单击要在其中管理 gpo 的林和域中的 "**组策略对象**"，单击 "**委派**"，然后配置设置以满足组织的需要。）</span><span class="sxs-lookup"><span data-stu-id="21ac1-152">(In the **Group Policy Management Console**, click **Group Policy Objects** in the forest and domain in which you want to manage GPOs, click **Delegation**, and then configure the settings to meet the needs of your organization.)</span></span>

### <span data-ttu-id="21ac1-153">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="21ac1-153">Additional references</span></span>

-   [<span data-ttu-id="21ac1-154">配置高级组策略管理</span><span class="sxs-lookup"><span data-stu-id="21ac1-154">Configuring Advanced Group Policy Management</span></span>](configuring-advanced-group-policy-management-agpm40.md)

 

 





