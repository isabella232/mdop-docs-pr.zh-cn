---
title: 配置 AGPM 服务器连接
description: 配置 AGPM 服务器连接
author: dansimp
ms.assetid: 9a42b5bc-41be-44ef-a6e2-6f56e2cf1996
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 88182f0e79f1a8bcce53e0d50c014e8d4aa29286
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802007"
---
# <span data-ttu-id="afa58-103">配置 AGPM 服务器连接</span><span class="sxs-lookup"><span data-stu-id="afa58-103">Configure the AGPM Server Connection</span></span>


<span data-ttu-id="afa58-104">高级组策略管理（AGPM）将每个受控制的组策略对象（GPO）的所有版本存储在一个中心存档中，因此组策略管理员可以脱机查看和修改 Gpo，而不会立即影响每个 GPO 的已部署版本。</span><span class="sxs-lookup"><span data-stu-id="afa58-104">Advanced Group Policy Management (AGPM) stores all versions of each controlled Group Policy object (GPO) in a central archive, so Group Policy administrators can view and modify GPOs offline without immediately impacting the deployed version of each GPO.</span></span>

<span data-ttu-id="afa58-105">具有 AGPM 管理员（完全控制）角色的用户帐户、创建在这些过程中使用的 GPO 的审批者的用户帐户，或者需要高级组策略管理中具有必要权限的用户帐户才能完成为所有组策略管理员集中配置存档位置的步骤。</span><span class="sxs-lookup"><span data-stu-id="afa58-105">A user account with the AGPM Administrator (Full Control) role, the user account of the Approver who created the GPO used in these procedures, or a user account with the necessary permissions in Advanced Group Policy Management is required to complete these procedures for centrally configuring archive locations for all Group Policy administrators.</span></span> <span data-ttu-id="afa58-106">查看本主题中 "其他注意事项" 中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="afa58-106">Review the details in "Additional considerations" in this topic.</span></span>

## <span data-ttu-id="afa58-107">配置 AGPM 服务器连接</span><span class="sxs-lookup"><span data-stu-id="afa58-107">Configuring the AGPM Server connection</span></span>


<span data-ttu-id="afa58-108">作为 AGPM 管理员（完全控制），你可以通过集中配置设置来确保所有组策略管理员都连接到同一 AGPM 服务器。</span><span class="sxs-lookup"><span data-stu-id="afa58-108">As an AGPM Administrator (Full Control), you can ensure that all Group Policy administrators connect to the same AGPM Server by centrally configuring the setting.</span></span> <span data-ttu-id="afa58-109">如果你的环境需要某些或所有域的单独的 AGPM 服务器，请将这些其他 AGPM 服务器配置为默认的例外。</span><span class="sxs-lookup"><span data-stu-id="afa58-109">If your environment requires separate AGPM Servers for some or all domains, configure those additional AGPM Servers as exceptions to the default.</span></span> <span data-ttu-id="afa58-110">如果未集中配置 AGPM 服务器连接，则每个组策略管理员必须手动配置要为每个域显示的 AGPM 服务器。</span><span class="sxs-lookup"><span data-stu-id="afa58-110">If you do not centrally configure AGPM Server connections, each Group Policy administrator must manually configure the AGPM Server to be displayed for each domain.</span></span>

-   [<span data-ttu-id="afa58-111">为所有组策略管理员配置 AGPM 服务器</span><span class="sxs-lookup"><span data-stu-id="afa58-111">Configure an AGPM Server for all Group Policy administrators</span></span>](#bkmk-defaultarchiveloc)

-   [<span data-ttu-id="afa58-112">为所有组策略管理员配置其他 AGPM 服务器</span><span class="sxs-lookup"><span data-stu-id="afa58-112">Configure additional AGPM Servers for all Group Policy administrators</span></span>](#bkmk-additionalarchiveloc)

-   [<span data-ttu-id="afa58-113">为你的帐户手动配置 AGPM 服务器</span><span class="sxs-lookup"><span data-stu-id="afa58-113">Manually configure an AGPM Server for your account</span></span>](#bkmk-manuallyconfigurearchiveloc)

### <a href="" id="bkmk-defaultarchiveloc"></a>

**<span data-ttu-id="afa58-114">为所有组策略管理员配置 AGPM 服务器</span><span class="sxs-lookup"><span data-stu-id="afa58-114">To configure an AGPM Server for all Group Policy administrators</span></span>**

1.  <span data-ttu-id="afa58-115">在**组策略管理控制台**树中，编辑应用到所有组策略管理员的 GPO。</span><span class="sxs-lookup"><span data-stu-id="afa58-115">In the **Group Policy Management Console** tree, edit a GPO that is applied to all Group Policy administrators.</span></span> <span data-ttu-id="afa58-116">（有关详细信息，请参阅[编辑 GPO](editing-a-gpo.md)。）</span><span class="sxs-lookup"><span data-stu-id="afa58-116">(For more information, see [Editing a GPO](editing-a-gpo.md).)</span></span>

2.  <span data-ttu-id="afa58-117">在 "**组策略对象编辑器**" 中，单击 "**用户配置**"、"**管理模板**" 和 " **Windows 组件**"。</span><span class="sxs-lookup"><span data-stu-id="afa58-117">In the **Group Policy Object Editor**, click **User Configuration**, **Administrative Templates**, and **Windows Components**.</span></span>

3.  <span data-ttu-id="afa58-118">如果 " **Windows 组件**" 下列出的是**AGPM**未列出：</span><span class="sxs-lookup"><span data-stu-id="afa58-118">If **AGPM** is not listed under **Windows Components**:</span></span>

    1.  <span data-ttu-id="afa58-119">右键单击 "**管理模板**"，然后单击 "**添加/删除模板**"。</span><span class="sxs-lookup"><span data-stu-id="afa58-119">Right-click **Administrative Templates** and click **Add/Remove Templates**.</span></span>

    2.  <span data-ttu-id="afa58-120">单击 "**添加**"，选择 " **agpm** " 或 " **agpm .Adm**"，单击 "**打开**"，然后单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="afa58-120">Click **Add**, select **agpm.admx** or **agpm.adm**, click **Open**, and then click **Close**.</span></span>

4.  <span data-ttu-id="afa58-121">在 " **Windows 组件**" 下，双击 " **AGPM**"。</span><span class="sxs-lookup"><span data-stu-id="afa58-121">Under **Windows Components**, double-click **AGPM**.</span></span>

5.  <span data-ttu-id="afa58-122">在 "详细信息" 窗格中，双击 " **AGPM 服务器（所有域）**"。</span><span class="sxs-lookup"><span data-stu-id="afa58-122">In the details pane, double-click **AGPM Server (all domains)**.</span></span>

6.  <span data-ttu-id="afa58-123">在 " **AGPM 服务器（所有域）属性**" 窗口中，选中 "**已启用**" 复选框，然后键入完全限定的计算机名称和端口（例如，server.contoso.com:4600）。</span><span class="sxs-lookup"><span data-stu-id="afa58-123">In the **AGPM Server (all domains) Properties** window, select the **Enabled** check box, and type the fully-qualified computer name and port (for example, server.contoso.com:4600).</span></span>

7.  <span data-ttu-id="afa58-124">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="afa58-124">Click **OK**.</span></span> <span data-ttu-id="afa58-125">除非你想要配置其他 AGPM 服务器连接，否则请关闭**组策略对象编辑器**并部署 GPO。</span><span class="sxs-lookup"><span data-stu-id="afa58-125">Unless you want to configure additional AGPM Server connections, close the **Group Policy Object Editor** and deploy the GPO.</span></span> <span data-ttu-id="afa58-126">（有关详细信息，请参阅[部署 GPO](deploy-a-gpo.md)。）更新组策略时，将为所有组策略管理员配置 AGPM 服务器连接。</span><span class="sxs-lookup"><span data-stu-id="afa58-126">(For more information, see [Deploy a GPO](deploy-a-gpo.md).) When Group Policy is updated, the AGPM Server connection is configured for all Group Policy administrators.</span></span>

### <a href="" id="bkmk-additionalarchiveloc"></a>

**<span data-ttu-id="afa58-127">为所有组策略管理员配置其他 AGPM 服务器</span><span class="sxs-lookup"><span data-stu-id="afa58-127">To configure additional AGPM Servers for all Group Policy administrators</span></span>**

1.  <span data-ttu-id="afa58-128">如果尚未配置 AGPM 服务器连接，请按照上述步骤为所有域配置默认的 AGPM 服务器。</span><span class="sxs-lookup"><span data-stu-id="afa58-128">If no AGPM Server connection has been configured, follow the preceding procedure to configure a default AGPM Server for all domains.</span></span>

2.  <span data-ttu-id="afa58-129">若要为部分或所有域配置单独的 AGPM 服务器（替代默认的 AGPM 服务器），请在**组策略管理控制台**树中，编辑应用到所有组策略管理员的 GPO。</span><span class="sxs-lookup"><span data-stu-id="afa58-129">To configure separate AGPM Servers for some or all domains (overriding the default AGPM Server), in the **Group Policy Management Console** tree, edit a GPO that is applied to all Group Policy administrators.</span></span> <span data-ttu-id="afa58-130">（有关详细信息，请参阅[编辑 GPO](editing-a-gpo.md)。）</span><span class="sxs-lookup"><span data-stu-id="afa58-130">(For more information, see [Editing a GPO](editing-a-gpo.md).)</span></span>

3.  <span data-ttu-id="afa58-131">在 "**组策略对象编辑器**" 中的 "**用户配置**" 下，双击 "**管理模板**"、" **Windows 组件**"，然后单击 " **AGPM**"。</span><span class="sxs-lookup"><span data-stu-id="afa58-131">Under **User Configuration** in the **Group Policy Object Editor**, double-click **Administrative Templates**, **Windows Components**, and then **AGPM**.</span></span>

4.  <span data-ttu-id="afa58-132">在 "详细信息" 窗格中，双击 " **AGPM 服务器**"。</span><span class="sxs-lookup"><span data-stu-id="afa58-132">In the details pane, double-click **AGPM Server**.</span></span>

5.  <span data-ttu-id="afa58-133">在 " **AGPM 服务器属性**" 窗口中，选中 "**已启用**" 复选框，然后单击 "**显示**"。</span><span class="sxs-lookup"><span data-stu-id="afa58-133">In the **AGPM Server Properties** window, select the **Enabled** check box, and click **Show**.</span></span>

6.  <span data-ttu-id="afa58-134">在 "**显示内容**" 窗口中：</span><span class="sxs-lookup"><span data-stu-id="afa58-134">In the **Show Contents** window:</span></span>

    1.  <span data-ttu-id="afa58-135">单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="afa58-135">Click **Add**.</span></span>

    2.  <span data-ttu-id="afa58-136">对于 "**值名称**"，请键入域名（例如，server1.contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="afa58-136">For **Value Name**, type the domain name (for example, server1.contoso.com).</span></span>

    3.  <span data-ttu-id="afa58-137">对于 "**值**"，请键入要用于此域的 AGPM 服务器名称和端口（例如，server2.contoso.com:4600），然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="afa58-137">For **Value**, type the AGPM Server name and port to use for this domain (for example, server2.contoso.com:4600), and then click **OK**.</span></span> <span data-ttu-id="afa58-138">（默认情况下，AGPM 服务在端口4600上侦听。</span><span class="sxs-lookup"><span data-stu-id="afa58-138">(By default, the AGPM Service listens on port 4600.</span></span> <span data-ttu-id="afa58-139">若要使用其他端口，请参阅[修改 AGPM 服务侦听的端口](modify-the-port-on-which-the-agpm-service-listens.md)。）</span><span class="sxs-lookup"><span data-stu-id="afa58-139">To use a different port, see [Modify the Port on Which the AGPM Service Listens](modify-the-port-on-which-the-agpm-service-listens.md).)</span></span>

    4.  <span data-ttu-id="afa58-140">对不使用默认 AGPM 服务器的每个域重复此操作。</span><span class="sxs-lookup"><span data-stu-id="afa58-140">Repeat for each domain not using the default AGPM Server.</span></span>

7.  <span data-ttu-id="afa58-141">单击 **"确定"** 关闭 "**显示内容**" 和 " **AGPM 服务器属性**" 窗口。</span><span class="sxs-lookup"><span data-stu-id="afa58-141">Click **OK** to close the **Show Contents** and **AGPM Server Properties** windows.</span></span>

8.  <span data-ttu-id="afa58-142">关闭 "**组策略对象编辑器**"。</span><span class="sxs-lookup"><span data-stu-id="afa58-142">Close the **Group Policy Object Editor**.</span></span> <span data-ttu-id="afa58-143">（有关详细信息，请参阅[部署 GPO](deploy-a-gpo.md)。）更新组策略时，将为所有组策略管理员配置新的 AGPM 服务器连接。</span><span class="sxs-lookup"><span data-stu-id="afa58-143">(For more information, see [Deploy a GPO](deploy-a-gpo.md).) When Group Policy is updated, the new AGPM Server connections are configured for all Group Policy administrators.</span></span>

### <a href="" id="bkmk-manuallyconfigurearchiveloc"></a>

<span data-ttu-id="afa58-144">如果已集中配置了 AGPM 服务器连接，则用于手动设置的选项对所有组策略管理员不可用。</span><span class="sxs-lookup"><span data-stu-id="afa58-144">If you have centrally configured the AGPM Server connection, the option to manually it is unavailable for all Group Policy administrators.</span></span>

**<span data-ttu-id="afa58-145">手动配置要为你的帐户显示的 AGPM 服务器</span><span class="sxs-lookup"><span data-stu-id="afa58-145">To manually configure the AGPM Server to display for your account</span></span>**

1.  <span data-ttu-id="afa58-146">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="afa58-146">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="afa58-147">在 "详细信息" 窗格中，单击 " **AGPM 服务器**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="afa58-147">In the details pane, click the **AGPM Server** tab.</span></span>

3.  <span data-ttu-id="afa58-148">输入用于管理用于此域的存档的 AGPM 服务器的完全限定计算机名（例如，server.contoso.com）和 AGPM 服务侦听的端口（默认情况下为端口4600）。</span><span class="sxs-lookup"><span data-stu-id="afa58-148">Enter the fully-qualified computer name for the AGPM Server that manages the archive used for this domain (for example, server.contoso.com) and the port on which the AGPM Service listens (by default, port 4600).</span></span>

4.  <span data-ttu-id="afa58-149">单击 "**应用**"，然后单击 **"是"** 进行确认。</span><span class="sxs-lookup"><span data-stu-id="afa58-149">Click **Apply**, then click **Yes** to confirm.</span></span>

### <span data-ttu-id="afa58-150">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="afa58-150">Additional considerations</span></span>

-   <span data-ttu-id="afa58-151">你必须能够编辑和部署 GPO，才能执行为所有组策略管理员集中配置 AGPM 服务器连接的过程。</span><span class="sxs-lookup"><span data-stu-id="afa58-151">You must be able to edit and deploy a GPO to perform the procedures for centrally configuring AGPM Server connections for all Group Policy administrators.</span></span> <span data-ttu-id="afa58-152">有关其他详细信息，请参阅[编辑 gpo](editing-a-gpo.md)和[部署 gpo](deploy-a-gpo.md) 。</span><span class="sxs-lookup"><span data-stu-id="afa58-152">See [Editing a GPO](editing-a-gpo.md) and [Deploy a GPO](deploy-a-gpo.md) for additional detail.</span></span>

-   <span data-ttu-id="afa58-153">所选的 AGPM 服务器确定在 "**目录**" 选项卡上显示哪些 gpo 以及应用 "**域委派**" 选项卡设置的位置。</span><span class="sxs-lookup"><span data-stu-id="afa58-153">The AGPM Server selected determines which GPOs are displayed on the **Contents** tab and to what location the **Domain Delegation** tab settings are applied.</span></span> <span data-ttu-id="afa58-154">如果不是通过管理模板进行集中管理，则每个组策略管理员必须将此设置配置为指向域的 AGPM 服务器。</span><span class="sxs-lookup"><span data-stu-id="afa58-154">If not centrally managed through the Administrative Template, each Group Policy administrator must configure this setting to point to the AGPM Server for the domain.</span></span>

-   <span data-ttu-id="afa58-155">组策略创建者所有者组中的成员身份应受到限制，以便它不会被 AGPM 通过 AGPM 对 Gpo 的访问进行管理。</span><span class="sxs-lookup"><span data-stu-id="afa58-155">Membership in the Group Policy Creator Owners group should be restricted so that it is not used to circumvent the management of access to GPOs by AGPM.</span></span> <span data-ttu-id="afa58-156">（在**组策略管理控制台**中，单击要在其中管理 gpo 的林和域中的 "**组策略对象**"，单击 "**委派**"，然后配置设置以满足组织的需要。）</span><span class="sxs-lookup"><span data-stu-id="afa58-156">(In the **Group Policy Management Console**, click **Group Policy Objects** in the forest and domain in which you want to manage GPOs, click **Delegation**, and then configure the settings to meet the needs of your organization.)</span></span>

### <span data-ttu-id="afa58-157">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="afa58-157">Additional references</span></span>

-   [<span data-ttu-id="afa58-158">执行 AGPM 管理员任务</span><span class="sxs-lookup"><span data-stu-id="afa58-158">Performing AGPM Administrator Tasks</span></span>](performing-agpm-administrator-tasks.md)

 

 





