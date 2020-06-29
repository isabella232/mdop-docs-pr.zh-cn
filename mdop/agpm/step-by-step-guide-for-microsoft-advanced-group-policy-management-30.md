---
title: Microsoft 高级组策略管理 3.0 分步指南
description: Microsoft 高级组策略管理 3.0 分步指南
author: dansimp
ms.assetid: d067f465-d7c8-4f6d-b311-66b9b06874f7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: b4efa5075027e99a3e50a344aafcdf6f6f69a147
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801772"
---
# <span data-ttu-id="77c1d-103">Microsoft 高级组策略管理 3.0 分步指南</span><span class="sxs-lookup"><span data-stu-id="77c1d-103">Step-by-Step Guide for Microsoft Advanced Group Policy Management 3.0</span></span>


<span data-ttu-id="77c1d-104">本分步指南介绍了使用组策略管理控制台（GPMC）和 Microsoft 高级组策略管理（AGPM）进行组策略管理的高级技术。</span><span class="sxs-lookup"><span data-stu-id="77c1d-104">This step-by-step guide demonstrates advanced techniques for Group Policy management using the Group Policy Management Console (GPMC) and Microsoft Advanced Group Policy Management (AGPM).</span></span> <span data-ttu-id="77c1d-105">AGPM 增加了 GPMC 的功能，提供：</span><span class="sxs-lookup"><span data-stu-id="77c1d-105">AGPM increases the capabilities of the GPMC, providing:</span></span>

-   <span data-ttu-id="77c1d-106">将管理组策略对象（Gpo）的权限委派给多个组策略管理员的标准角色，以及委派对生产环境中的 Gpo 的访问权限的功能。</span><span class="sxs-lookup"><span data-stu-id="77c1d-106">Standard roles for delegating permissions to manage Group Policy objects (GPOs) to multiple Group Policy administrators, as well as the ability to delegate access to GPOs in the production environment.</span></span>

-   <span data-ttu-id="77c1d-107">允许组策略管理员在将 Gpo 部署到生产环境之前脱机创建和修改 Gpo 的存档。</span><span class="sxs-lookup"><span data-stu-id="77c1d-107">An archive to enable Group Policy administrators to create and modify GPOs offline before deploying them to a production environment.</span></span>

-   <span data-ttu-id="77c1d-108">回滚到存档中的 GPO 的任何早期版本并限制存档中存储的版本数的功能。</span><span class="sxs-lookup"><span data-stu-id="77c1d-108">The ability to roll back to any previous version of a GPO in the archive and to limit the number of versions stored in the archive.</span></span>

-   <span data-ttu-id="77c1d-109">Gpo 的签入/签出功能，以确保组策略管理员不会无意间覆盖彼此的工作。</span><span class="sxs-lookup"><span data-stu-id="77c1d-109">Check-in/check-out capability for GPOs to ensure that Group Policy administrators do not inadvertently overwrite each other's work.</span></span>

## <span data-ttu-id="77c1d-110">AGPM 方案概述</span><span class="sxs-lookup"><span data-stu-id="77c1d-110">AGPM scenario overview</span></span>


<span data-ttu-id="77c1d-111">对于此方案，你将为 AGPM 中的每个角色使用单独的用户帐户，演示如何在具有不同级别的权限的多个组策略管理员的环境中管理组策略。</span><span class="sxs-lookup"><span data-stu-id="77c1d-111">For this scenario, you will use a separate user account for each role in AGPM to demonstrate how Group Policy can be managed in an environment with multiple Group Policy administrators who have different levels of permissions.</span></span> <span data-ttu-id="77c1d-112">具体地说，你将执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="77c1d-112">Specifically, you will perform the following tasks:</span></span>

-   <span data-ttu-id="77c1d-113">使用属于域管理员组成员的帐户，安装 AGPM 服务器并将 AGPM 管理员角色分配给帐户或组。</span><span class="sxs-lookup"><span data-stu-id="77c1d-113">Using an account that is a member of the Domain Admins group, install AGPM Server and assign the AGPM Administrator role to an account or group.</span></span>

-   <span data-ttu-id="77c1d-114">使用您将为其分配 AGPM 角色的帐户，安装 AGPM 客户端。</span><span class="sxs-lookup"><span data-stu-id="77c1d-114">Using accounts to which you will assign AGPM roles, install AGPM Client.</span></span>

-   <span data-ttu-id="77c1d-115">将帐户与 AGPM 管理员角色配合使用，配置 AGPM 并通过向其他帐户分配角色来委派对 Gpo 的访问权限。</span><span class="sxs-lookup"><span data-stu-id="77c1d-115">Using an account with the AGPM Administrator role, configure AGPM and delegate access to GPOs by assigning roles to other accounts.</span></span>

-   <span data-ttu-id="77c1d-116">使用具有 "编辑者" 角色的帐户，请求创建 GPO，然后使用审批者角色的帐户进行审批。</span><span class="sxs-lookup"><span data-stu-id="77c1d-116">Using an account with the Editor role, request the creation of a GPO, which you then approve using an account with the Approver role.</span></span> <span data-ttu-id="77c1d-117">通过编辑器帐户，将 GPO 从存档中签出，编辑 GPO，将 GPO 签入存档，然后请求部署。</span><span class="sxs-lookup"><span data-stu-id="77c1d-117">With the Editor account, check the GPO out of the archive, edit the GPO, check the GPO into the archive, and request deployment.</span></span>

-   <span data-ttu-id="77c1d-118">对审批者角色使用帐户，查看 GPO 并将其部署到生产环境。</span><span class="sxs-lookup"><span data-stu-id="77c1d-118">Using an account with the Approver role, review the GPO and deploy it to your production environment.</span></span>

-   <span data-ttu-id="77c1d-119">使用具有编辑器角色的帐户创建 GPO 模板，并将其用作创建新 GPO 的起始点。</span><span class="sxs-lookup"><span data-stu-id="77c1d-119">Using an account with the Editor role, create a GPO template and use it as a starting point to create a new GPO.</span></span>

-   <span data-ttu-id="77c1d-120">将帐户与审批者角色一起使用，删除和还原 GPO。</span><span class="sxs-lookup"><span data-stu-id="77c1d-120">Using an account with the Approver role, delete and restore a GPO.</span></span>

![组策略对象开发过程](images/ab77a1f3-f430-4e7d-be58-ee8f9bd1140e.gif)

## <span data-ttu-id="77c1d-122">要求</span><span class="sxs-lookup"><span data-stu-id="77c1d-122">Requirements</span></span>


<span data-ttu-id="77c1d-123">要安装 AGPM 的计算机必须满足以下要求，并且你必须创建用于此方案的帐户。</span><span class="sxs-lookup"><span data-stu-id="77c1d-123">Computers on which you want to install AGPM must meet the following requirements, and you must create accounts for use in this scenario.</span></span>

<span data-ttu-id="77c1d-124">**注意** 如果已安装了 AGPM 2.5，并且正在从 Windows Server®2003升级到 Windows Server2008 或 WindowsVista®，但未安装与 Service Pack1 WindowsVista 的 service pack，则必须先升级操作系统，然后才能升级到 AGPM 3.0。</span><span class="sxs-lookup"><span data-stu-id="77c1d-124">**Note** If you have AGPM 2.5 installed and are upgrading from Windows Server®2003 to Windows Server2008 or WindowsVista® with no service packs installed to WindowsVista with Service Pack1, you must upgrade the operating system before you can upgrade to AGPM3.0.</span></span>

 

### <span data-ttu-id="77c1d-125">AGPM 服务器要求</span><span class="sxs-lookup"><span data-stu-id="77c1d-125">AGPM Server requirements</span></span>

<span data-ttu-id="77c1d-126">对于安装了 "远程服务器管理工具（RSAT）" 的服务 Pack1 和 GPMC，AGPM 服务器3.0 需要 Windows Server2008 或 WindowsVista。</span><span class="sxs-lookup"><span data-stu-id="77c1d-126">AGPM Server3.0 requires Windows Server2008 or WindowsVista with Service Pack1 and the GPMC from Remote Server Administration Tools (RSAT) installed.</span></span> <span data-ttu-id="77c1d-127">支持32位和64位版本。</span><span class="sxs-lookup"><span data-stu-id="77c1d-127">Both 32-bit and 64-bit versions are supported.</span></span>

<span data-ttu-id="77c1d-128">在安装 AGPM 服务器之前，您必须是域管理员组的成员，除非另有说明，否则必须存在以下 Windows 功能：</span><span class="sxs-lookup"><span data-stu-id="77c1d-128">Before you install AGPM Server, you must be a member of the Domain Admins group and the following Windows features must be present unless otherwise noted:</span></span>

-   <span data-ttu-id="77c1d-129">GPMC.MSC</span><span class="sxs-lookup"><span data-stu-id="77c1d-129">GPMC</span></span>

    -   <span data-ttu-id="77c1d-130">Windows Server 2008：如果不存在，则由 AGPM 自动安装 GPMC。</span><span class="sxs-lookup"><span data-stu-id="77c1d-130">Windows Server 2008: The GPMC is automatically installed by AGPM if not present.</span></span>

    -   <span data-ttu-id="77c1d-131">Windows Vista：安装 AGPM 之前，必须从 RSAT 安装 GPMC。</span><span class="sxs-lookup"><span data-stu-id="77c1d-131">Windows Vista: You must install the GPMC from RSAT before you install AGPM.</span></span> <span data-ttu-id="77c1d-132">有关详细信息，请参阅 <https://go.microsoft.com/fwlink/?LinkID=116179>。</span><span class="sxs-lookup"><span data-stu-id="77c1d-132">For more information, see <https://go.microsoft.com/fwlink/?LinkID=116179>.</span></span>

-   <span data-ttu-id="77c1d-133">.NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="77c1d-133">.NET Framework 3.5</span></span>

<span data-ttu-id="77c1d-134">AGPM 服务器需要以下 Windows 功能，如果不存在，将自动安装这些功能：</span><span class="sxs-lookup"><span data-stu-id="77c1d-134">The following Windows features are required by AGPM Server and will be automatically installed if not present:</span></span>

-   <span data-ttu-id="77c1d-135">WCF 激活;非 HTTP 激活</span><span class="sxs-lookup"><span data-stu-id="77c1d-135">WCF Activation; Non-HTTP Activation</span></span>

-   <span data-ttu-id="77c1d-136">Windows Process Activation Service</span><span class="sxs-lookup"><span data-stu-id="77c1d-136">Windows Process Activation Service</span></span>

    -   <span data-ttu-id="77c1d-137">流程模型</span><span class="sxs-lookup"><span data-stu-id="77c1d-137">Process Model</span></span>

    -   <span data-ttu-id="77c1d-138">.NET 环境</span><span class="sxs-lookup"><span data-stu-id="77c1d-138">.NET Environment</span></span>

    -   <span data-ttu-id="77c1d-139">配置 Api</span><span class="sxs-lookup"><span data-stu-id="77c1d-139">Configuration APIs</span></span>

### <span data-ttu-id="77c1d-140">AGPM 客户端要求</span><span class="sxs-lookup"><span data-stu-id="77c1d-140">AGPM Client requirements</span></span>

<span data-ttu-id="77c1d-141">AGPM 客户端3.0 要求 Windows Server2008 或 WindowsVista Service Pack 1 和 GPMC 安装了远程服务器管理工具（RSAT）。</span><span class="sxs-lookup"><span data-stu-id="77c1d-141">AGPM Client3.0 requires Windows Server2008 or WindowsVista with Service Pack 1 and the GPMC from Remote Server Administration Tools (RSAT) installed.</span></span> <span data-ttu-id="77c1d-142">支持32位和64位版本。</span><span class="sxs-lookup"><span data-stu-id="77c1d-142">Both 32-bit and 64-bit versions are supported.</span></span> <span data-ttu-id="77c1d-143">可以在运行 AGPM 服务器的计算机上安装 AGPM 客户端。</span><span class="sxs-lookup"><span data-stu-id="77c1d-143">AGPM Client can be installed on a computer running AGPM Server.</span></span>

<span data-ttu-id="77c1d-144">以下 Windows 功能是 AGPM 客户端所必需的，如果不存在，则将自动安装，除非另有说明：</span><span class="sxs-lookup"><span data-stu-id="77c1d-144">The following Windows features are required by AGPM Client and will be automatically installed if not present unless otherwise noted:</span></span>

-   <span data-ttu-id="77c1d-145">GPMC.MSC</span><span class="sxs-lookup"><span data-stu-id="77c1d-145">GPMC</span></span>

    -   <span data-ttu-id="77c1d-146">Windows Server 2008：如果不存在，则由 AGPM 自动安装 GPMC。</span><span class="sxs-lookup"><span data-stu-id="77c1d-146">Windows Server 2008: The GPMC is automatically installed by AGPM if not present.</span></span>

    -   <span data-ttu-id="77c1d-147">Windows Vista：安装 AGPM 之前，必须从 RSAT 安装 GPMC。</span><span class="sxs-lookup"><span data-stu-id="77c1d-147">Windows Vista: You must install the GPMC from RSAT before you install AGPM.</span></span> <span data-ttu-id="77c1d-148">有关详细信息，请参阅 <https://go.microsoft.com/fwlink/?LinkID=116179>。</span><span class="sxs-lookup"><span data-stu-id="77c1d-148">For more information, see <https://go.microsoft.com/fwlink/?LinkID=116179>.</span></span>

-   <span data-ttu-id="77c1d-149">.NET Framework 3。0</span><span class="sxs-lookup"><span data-stu-id="77c1d-149">.NET Framework 3.0</span></span>

### <span data-ttu-id="77c1d-150">方案要求</span><span class="sxs-lookup"><span data-stu-id="77c1d-150">Scenario requirements</span></span>

<span data-ttu-id="77c1d-151">在开始此方案之前，请创建四个用户帐户。</span><span class="sxs-lookup"><span data-stu-id="77c1d-151">Before you begin this scenario, create four user accounts.</span></span> <span data-ttu-id="77c1d-152">在此方案中，你将为以下每个帐户分配以下 AGPM 角色之一： AGPM 管理员（完全控制）、审批者、编辑者和审阅者。</span><span class="sxs-lookup"><span data-stu-id="77c1d-152">During the scenario, you will assign one of the following AGPM roles to each of these accounts: AGPM Administrator (Full Control), Approver, Editor, and Reviewer.</span></span> <span data-ttu-id="77c1d-153">这些帐户必须能够发送和接收电子邮件。</span><span class="sxs-lookup"><span data-stu-id="77c1d-153">These accounts must be able to send and receive e-mail messages.</span></span> <span data-ttu-id="77c1d-154">为具有 AGPM 管理员、审批者和（可选）编辑器角色的帐户分配**链接 gpo**权限。</span><span class="sxs-lookup"><span data-stu-id="77c1d-154">Assign **Link GPOs** permission to the accounts with the AGPM Administrator, Approver, and (optionally) Editor roles.</span></span>

<span data-ttu-id="77c1d-155">**注意** 
默认情况下， **Link gpo**权限分配给域管理员和企业管理员的成员。</span><span class="sxs-lookup"><span data-stu-id="77c1d-155">**Note**
**Link GPOs** permission is assigned to members of Domain Administrators and Enterprise Administrators by default.</span></span> <span data-ttu-id="77c1d-156">若要将**链接 gpo**权限分配给其他用户或组（如具有 AGPM 管理员或审批者角色的帐户），请单击域的节点，然后单击 "**委派**" 选项卡，选择 "**链接 Gpo**"，单击 "**添加**"，然后选择要向其分配权限的用户或组。</span><span class="sxs-lookup"><span data-stu-id="77c1d-156">To assign **Link GPOs** permission to additional users or groups (such as accounts with the roles of AGPM Administrator or Approver), click the node for the domain and then click the **Delegation** tab, select **Link GPOs**, click **Add**, and select users or groups to which to assign the permission.</span></span>

 

## <span data-ttu-id="77c1d-157">安装和配置 AGPM 的步骤</span><span class="sxs-lookup"><span data-stu-id="77c1d-157">Steps for installing and configuring AGPM</span></span>


<span data-ttu-id="77c1d-158">必须完成以下步骤才能安装和配置 AGPM。</span><span class="sxs-lookup"><span data-stu-id="77c1d-158">You must complete the following steps to install and configure AGPM.</span></span>

[<span data-ttu-id="77c1d-159">步骤1：安装 AGPM 服务器</span><span class="sxs-lookup"><span data-stu-id="77c1d-159">Step 1: Install AGPM Server</span></span>](#bkmk-config1)

[<span data-ttu-id="77c1d-160">步骤2：安装 AGPM 客户端</span><span class="sxs-lookup"><span data-stu-id="77c1d-160">Step 2: Install AGPM Client</span></span>](#bkmk-config2)

[<span data-ttu-id="77c1d-161">步骤3：配置 AGPM 服务器连接</span><span class="sxs-lookup"><span data-stu-id="77c1d-161">Step 3: Configure an AGPM Server connection</span></span>](#bkmk-config3)

[<span data-ttu-id="77c1d-162">步骤4：配置电子邮件通知</span><span class="sxs-lookup"><span data-stu-id="77c1d-162">Step 4: Configure e-mail notification</span></span>](#bkmk-config4)

[<span data-ttu-id="77c1d-163">步骤5：代理访问</span><span class="sxs-lookup"><span data-stu-id="77c1d-163">Step 5: Delegate access</span></span>](#bkmk-config5)

### <a href="" id="bkmk-config1"></a><span data-ttu-id="77c1d-164">步骤1：安装 AGPM 服务器</span><span class="sxs-lookup"><span data-stu-id="77c1d-164">Step 1: Install AGPM Server</span></span>

<span data-ttu-id="77c1d-165">在此步骤中，将在将运行 AGPM 服务的成员服务器或域控制器上安装 AGPM 服务器，然后配置存档。</span><span class="sxs-lookup"><span data-stu-id="77c1d-165">In this step, you install AGPM Server on the member server or domain controller that will run the AGPM Service, and you configure the archive.</span></span> <span data-ttu-id="77c1d-166">所有 AGPM 操作都通过此 Windows 服务进行管理，并使用服务凭据执行。</span><span class="sxs-lookup"><span data-stu-id="77c1d-166">All AGPM operations are managed through this Windows service and are executed with the service's credentials.</span></span> <span data-ttu-id="77c1d-167">AGPM 服务器托管的存档可以托管在该服务器上，也可以在同一林中的另一台服务器上托管。</span><span class="sxs-lookup"><span data-stu-id="77c1d-167">The archive managed by an AGPM Server can be hosted on that server or on another server in the same forest.</span></span>

**<span data-ttu-id="77c1d-168">在将托管 AGPM 服务的计算机上安装 AGPM 服务器</span><span class="sxs-lookup"><span data-stu-id="77c1d-168">To install AGPM Server on the computer that will host the AGPM Service</span></span>**

1.  <span data-ttu-id="77c1d-169">使用域管理员组的成员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="77c1d-169">Log on with an account that is a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="77c1d-170">启动 Microsoft 桌面优化包 CD，然后按照屏幕上的说明选择 "**高级组策略管理-服务器**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-170">Start the Microsoft Desktop Optimization Pack CD and follow the instructions on screen to select **Advanced Group Policy Management - Server**.</span></span>

3.  <span data-ttu-id="77c1d-171">在 "**欢迎**" 对话框中，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-171">In the **Welcome** dialog box, click **Next**.</span></span>

4.  <span data-ttu-id="77c1d-172">在 " **Microsoft 软件许可条款**" 对话框中，接受条款，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-172">In the **Microsoft Software License Terms** dialog box, accept the terms and click **Next**.</span></span>

5.  <span data-ttu-id="77c1d-173">在 "**应用程序路径**" 对话框中，选择要在其中安装 AGPM 服务器的位置。</span><span class="sxs-lookup"><span data-stu-id="77c1d-173">In the **Application Path** dialog box, select a location in which to install AGPM Server.</span></span> <span data-ttu-id="77c1d-174">安装了 AGPM 服务器的计算机将托管 AGPM 服务并管理存档。</span><span class="sxs-lookup"><span data-stu-id="77c1d-174">The computer on which AGPM Server is installed will host the AGPM Service and manage the archive.</span></span> <span data-ttu-id="77c1d-175">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="77c1d-175">Click **Next**.</span></span>

6.  <span data-ttu-id="77c1d-176">在 "**存档路径**" 对话框中，选择用于相对于 AGPM 服务器的存档位置。</span><span class="sxs-lookup"><span data-stu-id="77c1d-176">In the **Archive Path** dialog box, select a location for the archive relative to the AGPM Server.</span></span> <span data-ttu-id="77c1d-177">存档路径可以指向 AGPM 服务器或其他位置上的文件夹，但你应该选择一个具有足够空间的位置来存储由此 AGPM 服务器管理的所有 Gpo 和历史记录数据。</span><span class="sxs-lookup"><span data-stu-id="77c1d-177">The archive path can point to a folder on the AGPM Server or elsewhere, but you should select a location with sufficient space to store all GPOs and history data managed by this AGPM Server.</span></span> <span data-ttu-id="77c1d-178">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="77c1d-178">Click **Next**.</span></span>

7.  <span data-ttu-id="77c1d-179">在 " **Agpm 服务帐户**" 对话框中，选择要在其下运行 AGPM 服务的服务帐户，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-179">In the **AGPM Service Account** dialog box, select a service account under which the AGPM Service will run and then click **Next**.</span></span>

8.  <span data-ttu-id="77c1d-180">在 "**存档所有者**" 对话框中，选择要向其初始分配 AGPM 管理员（完全控制）角色的帐户或组。</span><span class="sxs-lookup"><span data-stu-id="77c1d-180">In the **Archive Owner** dialog box, select an account or group to which to initially assign the AGPM Administrator (Full Control) role.</span></span> <span data-ttu-id="77c1d-181">此 AGPM 管理员可以为其他组策略管理员分配 AGPM 角色和权限（包括 AGPM 管理员的角色）。</span><span class="sxs-lookup"><span data-stu-id="77c1d-181">This AGPM Administrator can assign AGPM roles and permissions to other Group Policy administrators (including the role of AGPM Administrator).</span></span> <span data-ttu-id="77c1d-182">对于此方案，选择要在 AGPM 管理员角色中提供的帐户。</span><span class="sxs-lookup"><span data-stu-id="77c1d-182">For this scenario, select the account to serve in the AGPM Administrator role.</span></span> <span data-ttu-id="77c1d-183">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="77c1d-183">Click **Next**.</span></span>

9.  <span data-ttu-id="77c1d-184">在 "**端口配置**" 对话框中，键入 AGPM 服务应侦听的端口。</span><span class="sxs-lookup"><span data-stu-id="77c1d-184">In the **Port Configuration** dialog box, type a port on which the AGPM Service should listen.</span></span> <span data-ttu-id="77c1d-185">不要清除 "**将端口例外添加到防火墙**" 复选框，除非手动配置端口例外或使用规则配置端口例外。</span><span class="sxs-lookup"><span data-stu-id="77c1d-185">Do not clear the **Add port exception to firewall** check box unless you manually configure port exceptions or use rules to configure port exceptions.</span></span> <span data-ttu-id="77c1d-186">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="77c1d-186">Click **Next**.</span></span>

10. <span data-ttu-id="77c1d-187">在 "**语言**" 对话框中，选择要为 AGPM 服务器安装的一个或多个显示语言。</span><span class="sxs-lookup"><span data-stu-id="77c1d-187">In the **Languages** dialog box, select one or more display languages to install for AGPM Server.</span></span>

11. <span data-ttu-id="77c1d-188">单击 "**安装**"，然后单击 "**完成**" 退出设置向导。</span><span class="sxs-lookup"><span data-stu-id="77c1d-188">Click **Install**, and then click **Finish** to exit the Setup Wizard.</span></span>

    <span data-ttu-id="77c1d-189">**小心** 不要通过操作系统中的 "**管理工具**和**服务**" 修改 AGPM 服务的设置。</span><span class="sxs-lookup"><span data-stu-id="77c1d-189">**Caution** Do not modify settings for the AGPM Service through **Administrative Tools** and **Services** in the operating system.</span></span> <span data-ttu-id="77c1d-190">这样做可能会阻止 AGPM 服务启动。</span><span class="sxs-lookup"><span data-stu-id="77c1d-190">Doing so can prevent the AGPM Service from starting.</span></span> <span data-ttu-id="77c1d-191">有关如何修改服务设置的信息，请参阅高级组策略管理的帮助。</span><span class="sxs-lookup"><span data-stu-id="77c1d-191">For information on how to modify settings for the service, see Help for Advanced Group Policy Management.</span></span>

     

### <a href="" id="bkmk-config2"></a><span data-ttu-id="77c1d-192">步骤2：安装 AGPM 客户端</span><span class="sxs-lookup"><span data-stu-id="77c1d-192">Step 2: Install AGPM Client</span></span>

<span data-ttu-id="77c1d-193">每个组策略管理员（创建、编辑、部署、查看或删除 Gpo 的任何人）都必须在它们用于管理 Gpo 的计算机上安装 AGPM 客户端。</span><span class="sxs-lookup"><span data-stu-id="77c1d-193">Each Group Policy administrator—anyone who creates, edits, deploys, reviews, or deletes GPOs—must have AGPM Client installed on computers that they use to manage GPOs.</span></span> <span data-ttu-id="77c1d-194">对于此方案，请在至少一台计算机上安装 AGPM 客户端。</span><span class="sxs-lookup"><span data-stu-id="77c1d-194">For this scenario, you install AGPM Client on at least one computer.</span></span> <span data-ttu-id="77c1d-195">无需在不执行组策略管理的最终用户的计算机上安装 AGPM 客户端。</span><span class="sxs-lookup"><span data-stu-id="77c1d-195">You do not need to install AGPM Client on the computers of end users who do not perform Group Policy administration.</span></span>

**<span data-ttu-id="77c1d-196">在组策略管理员的计算机上安装 AGPM 客户端</span><span class="sxs-lookup"><span data-stu-id="77c1d-196">To install AGPM Client on the computer of a Group Policy administrator</span></span>**

1.  <span data-ttu-id="77c1d-197">启动 Microsoft 桌面优化包 CD，然后按照屏幕上的说明选择 "**高级组策略管理-客户端**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-197">Start the Microsoft Desktop Optimization Pack CD and follow the instructions on screen to select **Advanced Group Policy Management - Client**.</span></span>

2.  <span data-ttu-id="77c1d-198">在 "**欢迎**" 对话框中，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-198">In the **Welcome** dialog box, click **Next**.</span></span>

3.  <span data-ttu-id="77c1d-199">在 " **Microsoft 软件许可条款**" 对话框中，接受条款，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-199">In the **Microsoft Software License Terms** dialog box, accept the terms and click **Next**.</span></span>

4.  <span data-ttu-id="77c1d-200">在 "**应用程序路径**" 对话框中，选择要在其中安装 AGPM 客户端的位置。</span><span class="sxs-lookup"><span data-stu-id="77c1d-200">In the **Application Path** dialog box, select a location in which to install AGPM Client.</span></span> <span data-ttu-id="77c1d-201">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="77c1d-201">Click **Next**.</span></span>

5.  <span data-ttu-id="77c1d-202">在 " **AGPM 服务器**" 对话框中，键入 AGPM 服务器的完全限定的计算机名称和要连接到的端口。</span><span class="sxs-lookup"><span data-stu-id="77c1d-202">In the **AGPM Server** dialog box, type the fully-qualified computer name for the AGPM Server and the port to which to connect.</span></span> <span data-ttu-id="77c1d-203">AGPM 服务的默认端口为4600。</span><span class="sxs-lookup"><span data-stu-id="77c1d-203">The default port for the AGPM Service is 4600.</span></span> <span data-ttu-id="77c1d-204">不要清除 "**通过防火墙允许 Microsoft 管理控制台**" 复选框，除非手动配置端口例外或使用规则配置端口例外。</span><span class="sxs-lookup"><span data-stu-id="77c1d-204">Do not clear the **Allow Microsoft Management Console through the firewall** check box unless you manually configure port exceptions or use rules to configure port exceptions.</span></span> <span data-ttu-id="77c1d-205">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="77c1d-205">Click **Next**.</span></span>

6.  <span data-ttu-id="77c1d-206">在 "**语言**" 对话框中，选择要为 AGPM 客户端安装的一个或多个显示语言。</span><span class="sxs-lookup"><span data-stu-id="77c1d-206">In the **Languages** dialog box, select one or more display languages to install for AGPM Client.</span></span>

7.  <span data-ttu-id="77c1d-207">单击 "**安装**"，然后单击 "**完成**" 退出设置向导。</span><span class="sxs-lookup"><span data-stu-id="77c1d-207">Click **Install**, and then click **Finish** to exit the Setup Wizard.</span></span>

### <a href="" id="bkmk-config3"></a><span data-ttu-id="77c1d-208">步骤3：配置 AGPM 服务器连接</span><span class="sxs-lookup"><span data-stu-id="77c1d-208">Step 3: Configure an AGPM Server connection</span></span>

<span data-ttu-id="77c1d-209">AGPM 存储每个受控制的组策略对象（GPO）的所有版本— AGPM 提供更改控制的 GPO，因此组策略管理员可以脱机查看和修改 Gpo，而无需立即影响每个 GPO 的已部署版本。</span><span class="sxs-lookup"><span data-stu-id="77c1d-209">AGPM stores all versions of each controlled Group Policy object (GPO)—a GPO for which AGPM provides change control—in a central archive, so Group Policy administrators can view and modify GPOs offline without immediately impacting the deployed version of each GPO.</span></span>

<span data-ttu-id="77c1d-210">在此步骤中，配置 AGPM 服务器连接并确保所有组策略管理员都连接到同一 AGPM 服务器。</span><span class="sxs-lookup"><span data-stu-id="77c1d-210">In this step, you configure an AGPM Server connection and ensure that all Group Policy administrators connect to the same AGPM Server.</span></span> <span data-ttu-id="77c1d-211">（有关配置多个 AGPM 服务器的信息，请参阅高级组策略管理的帮助。）</span><span class="sxs-lookup"><span data-stu-id="77c1d-211">(For information about configuring multiple AGPM Servers, see Help for Advanced Group Policy Management.)</span></span>

**<span data-ttu-id="77c1d-212">为所有组策略管理员配置 AGPM 服务器连接</span><span class="sxs-lookup"><span data-stu-id="77c1d-212">To configure an AGPM Server connection for all Group Policy administrators</span></span>**

1.  <span data-ttu-id="77c1d-213">在已安装了 AGPM 客户端的计算机上，使用你选择作为存档所有者的用户帐户登录。</span><span class="sxs-lookup"><span data-stu-id="77c1d-213">On a computer on which you have installed AGPM Client, log on with the user account that you selected as the Archive Owner.</span></span> <span data-ttu-id="77c1d-214">此用户具有 AGPM 管理员的角色（"完全控制"）。</span><span class="sxs-lookup"><span data-stu-id="77c1d-214">This user has the role of AGPM Administrator (Full Control).</span></span>

2.  <span data-ttu-id="77c1d-215">单击 "**开始**"，指向 "**管理工具**"，然后单击 "**组策略管理**" 以打开 GPMC。</span><span class="sxs-lookup"><span data-stu-id="77c1d-215">Click **Start**, point to **Administrative Tools**, and click **Group Policy Management** to open the GPMC.</span></span>

3.  <span data-ttu-id="77c1d-216">编辑应用到所有组策略管理员的 GPO。</span><span class="sxs-lookup"><span data-stu-id="77c1d-216">Edit a GPO that is applied to all Group Policy administrators.</span></span>

4.  <span data-ttu-id="77c1d-217">在 "**组策略管理编辑器**" 窗口中，双击 **"用户配置**"、"**策略**"、"**管理模板**"、" **Windows 组件**" 和 " **AGPM**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-217">In the **Group Policy Management Editor** window, double-click **User Configuration**, **Policies**, **Administrative Templates**, **Windows Components**, and **AGPM**.</span></span>

5.  <span data-ttu-id="77c1d-218">在 "详细信息" 窗格中，双击 " **AGPM：指定默认 Agpm 服务器（所有域）**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-218">In the details pane, double-click **AGPM: Specify default AGPM Server (all domains)**.</span></span>

6.  <span data-ttu-id="77c1d-219">在 "**属性**" 窗口中，选择 "**已启用**"，然后为托管存档的服务器键入完全限定的计算机名称和端口（例如， **server.contoso.com:4600**）。</span><span class="sxs-lookup"><span data-stu-id="77c1d-219">In the **Properties** window, select **Enabled** and type the fully-qualified computer name and port (for example, **server.contoso.com:4600**) for the server hosting the archive.</span></span> <span data-ttu-id="77c1d-220">默认情况下，AGPM 服务使用端口4600。</span><span class="sxs-lookup"><span data-stu-id="77c1d-220">By default, the AGPM Service uses port 4600.</span></span>

7.  <span data-ttu-id="77c1d-221">单击 **"确定**"，然后关闭 "**组策略管理编辑器**" 窗口。</span><span class="sxs-lookup"><span data-stu-id="77c1d-221">Click **OK**, and then close the **Group Policy Management Editor** window.</span></span> <span data-ttu-id="77c1d-222">更新组策略时，将为每个组策略管理员配置 AGPM 服务器连接。</span><span class="sxs-lookup"><span data-stu-id="77c1d-222">When Group Policy is updated, the AGPM Server connection is configured for each Group Policy administrator.</span></span>

### <a href="" id="bkmk-config4"></a><span data-ttu-id="77c1d-223">步骤4：配置电子邮件通知</span><span class="sxs-lookup"><span data-stu-id="77c1d-223">Step 4: Configure e-mail notification</span></span>

<span data-ttu-id="77c1d-224">作为 AGPM 管理员（完全控制），你可以指定在编辑者尝试创建、部署或删除 GPO 时向其发送包含请求的电子邮件的审批者和 AGPM 管理员的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="77c1d-224">As an AGPM Administrator (Full Control), you designate the e-mail addresses of Approvers and AGPM Administrators to whom an e-mail message containing a request is sent when an Editor attempts to create, deploy, or delete a GPO.</span></span> <span data-ttu-id="77c1d-225">您还可以确定发送这些邮件的别名。</span><span class="sxs-lookup"><span data-stu-id="77c1d-225">You also determine the alias from which these messages are sent.</span></span>

**<span data-ttu-id="77c1d-226">配置 AGPM 的电子邮件通知</span><span class="sxs-lookup"><span data-stu-id="77c1d-226">To configure e-mail notification for AGPM</span></span>**

1.  <span data-ttu-id="77c1d-227">在 "详细信息" 窗格中，单击 "**域委派**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="77c1d-227">In the details pane, click the **Domain Delegation** tab.</span></span>

2.  <span data-ttu-id="77c1d-228">在 "**发件人电子邮件地址**" 字段中，键入要从中发送通知的 AGPM 的电子邮件别名。</span><span class="sxs-lookup"><span data-stu-id="77c1d-228">In the **From e-mail address** field, type the e-mail alias for AGPM from which notifications should be sent.</span></span>

3.  <span data-ttu-id="77c1d-229">在 "**收件人电子邮件地址**" 字段中，键入要向其分配审批者角色的用户帐户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="77c1d-229">In the **To e-mail address** field, type the e-mail address for the user account to which you intend to assign the Approver role.</span></span>

4.  <span data-ttu-id="77c1d-230">在 " **SMTP 服务器**" 字段中，键入有效的 SMTP 邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="77c1d-230">In the **SMTP server** field, type a valid SMTP mail server.</span></span>

5.  <span data-ttu-id="77c1d-231">在 "**用户名**" 和 "**密码**" 字段中，键入有权访问 SMTP 服务的用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="77c1d-231">In the **User name** and **Password** fields, type the credentials of a user with access to the SMTP service.</span></span> <span data-ttu-id="77c1d-232">单击**应用**。</span><span class="sxs-lookup"><span data-stu-id="77c1d-232">Click **Apply**.</span></span>

### <a href="" id="bkmk-config5"></a><span data-ttu-id="77c1d-233">步骤5：代理访问</span><span class="sxs-lookup"><span data-stu-id="77c1d-233">Step 5: Delegate access</span></span>

<span data-ttu-id="77c1d-234">作为 AGPM 管理员（完全控制），你可以委派域级别对 Gpo 的访问权限，并为每个组策略管理员的帐户分配角色。</span><span class="sxs-lookup"><span data-stu-id="77c1d-234">As an AGPM Administrator (Full Control), you delegate domain-level access to GPOs, assigning roles to the account of each Group Policy administrator.</span></span>

<span data-ttu-id="77c1d-235">**注意** 你还可以在 GPO 级别（而不是域级别）委派访问权限。</span><span class="sxs-lookup"><span data-stu-id="77c1d-235">**Note** You can also delegate access at the GPO level rather than the domain level.</span></span> <span data-ttu-id="77c1d-236">有关详细信息，请参阅高级组策略管理的帮助。</span><span class="sxs-lookup"><span data-stu-id="77c1d-236">For details, see Help for Advanced Group Policy Management.</span></span>

 

<span data-ttu-id="77c1d-237">**重要提示** 你应该限制 "组策略创建者所有者" 组中的成员身份，因此不能将其用于绕过对 Gpo 的访问的 AGPM 管理。</span><span class="sxs-lookup"><span data-stu-id="77c1d-237">**Important** You should restrict membership in the Group Policy Creator Owners group, so it cannot be used to circumvent AGPM management of access to GPOs.</span></span> <span data-ttu-id="77c1d-238">（在**组策略管理控制台**中，单击要在其中管理 gpo 的林和域中的 "**组策略对象**"，单击 "**委派**"，然后配置设置以满足组织的需要。）</span><span class="sxs-lookup"><span data-stu-id="77c1d-238">(In the **Group Policy Management Console**, click **Group Policy Objects** in the forest and domain in which you want to manage GPOs, click **Delegation**, and then configure the settings to meet the needs of your organization.)</span></span>

 

**<span data-ttu-id="77c1d-239">委派对整个域中的所有 Gpo 的访问权限</span><span class="sxs-lookup"><span data-stu-id="77c1d-239">To delegate access to all GPOs throughout a domain</span></span>**

1.  <span data-ttu-id="77c1d-240">在 "**域委派**" 选项卡上，单击 "**添加**" 按钮，选择要用作审批者的组策略管理员的用户帐户，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="77c1d-240">On the **Domain Delegation** tab, click the **Add** button, select the user account of the Group Policy administrator to serve as Approver, and then click **OK**.</span></span>

2.  <span data-ttu-id="77c1d-241">在 "**添加组或用户**" 对话框中，选择要向帐户分配该角色的**审批者**角色，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="77c1d-241">In the **Add Group or User** dialog box, select the **Approver** role to assign that role to the account, and then click **OK**.</span></span> <span data-ttu-id="77c1d-242">（此角色包括审阅者角色。）</span><span class="sxs-lookup"><span data-stu-id="77c1d-242">(This role includes the Reviewer role.)</span></span>

3.  <span data-ttu-id="77c1d-243">单击 "**添加**" 按钮，选择组策略管理员作为编辑器的用户帐户，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="77c1d-243">Click the **Add** button, select the user account of the Group Policy administrator to serve as Editor, and then click **OK**.</span></span>

4.  <span data-ttu-id="77c1d-244">在 "**添加组或用户**" 对话框中，选择要向帐户分配该角色的 "**编辑**者" 角色，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="77c1d-244">In the **Add Group or User** dialog box, select the **Editor** role to assign that role to the account, and then click **OK**.</span></span> <span data-ttu-id="77c1d-245">（此角色包括审阅者角色。）</span><span class="sxs-lookup"><span data-stu-id="77c1d-245">(This role includes the Reviewer role.)</span></span>

5.  <span data-ttu-id="77c1d-246">单击 "**添加**" 按钮，选择组策略管理员充当审阅者的用户帐户，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="77c1d-246">Click the **Add** button, select the user account of the Group Policy administrator to serve as Reviewer, and then click **OK**.</span></span>

6.  <span data-ttu-id="77c1d-247">在 "**添加组" 或 "用户**" 对话框中，选择**审阅者**角色以仅将该角色分配给帐户。</span><span class="sxs-lookup"><span data-stu-id="77c1d-247">In the **Add Group or User** dialog box, select the **Reviewer** role to assign only that role to the account.</span></span>

## <span data-ttu-id="77c1d-248">管理 Gpo 的步骤</span><span class="sxs-lookup"><span data-stu-id="77c1d-248">Steps for managing GPOs</span></span>


<span data-ttu-id="77c1d-249">必须完成以下步骤才能使用 AGPM 创建、编辑、查看和部署 Gpo。</span><span class="sxs-lookup"><span data-stu-id="77c1d-249">You must complete the following steps to create, edit, review, and deploy GPOs using AGPM.</span></span> <span data-ttu-id="77c1d-250">此外，你将创建一个模板，删除 GPO，然后还原已删除的 GPO。</span><span class="sxs-lookup"><span data-stu-id="77c1d-250">Additionally, you will create a template, delete a GPO, and restore a deleted GPO.</span></span>

[<span data-ttu-id="77c1d-251">步骤1：创建 GPO</span><span class="sxs-lookup"><span data-stu-id="77c1d-251">Step 1: Create a GPO</span></span>](#bkmk-manage1)

[<span data-ttu-id="77c1d-252">步骤2：编辑 GPO</span><span class="sxs-lookup"><span data-stu-id="77c1d-252">Step 2: Edit a GPO</span></span>](#bkmk-manage2)

[<span data-ttu-id="77c1d-253">步骤3：查看和部署 GPO</span><span class="sxs-lookup"><span data-stu-id="77c1d-253">Step 3: Review and deploy a GPO</span></span>](#bkmk-manage3)

[<span data-ttu-id="77c1d-254">步骤4：使用模板创建 GPO</span><span class="sxs-lookup"><span data-stu-id="77c1d-254">Step 4: Use a template to create a GPO</span></span>](#bkmk-manage4)

[<span data-ttu-id="77c1d-255">步骤5：删除和还原 GPO</span><span class="sxs-lookup"><span data-stu-id="77c1d-255">Step 5: Delete and restore a GPO</span></span>](#bkmk-manage5)

### <a href="" id="bkmk-manage1"></a><span data-ttu-id="77c1d-256">步骤1：创建 GPO</span><span class="sxs-lookup"><span data-stu-id="77c1d-256">Step 1: Create a GPO</span></span>

<span data-ttu-id="77c1d-257">在具有多个组策略管理员的环境中，具有编辑器角色的用户能够请求创建新的 Gpo，但此类请求必须由拥有审批者角色的人员批准，因为创建新 GPO 会影响生产环境。</span><span class="sxs-lookup"><span data-stu-id="77c1d-257">In an environment with multiple Group Policy administrators, those with the Editor role have the ability to request the creation of new GPOs, but such a request must be approved by someone with the Approver role because the creation of a new GPO impacts the production environment.</span></span>

<span data-ttu-id="77c1d-258">在此步骤中，您将使用具有编辑器角色的帐户请求创建新的 GPO。</span><span class="sxs-lookup"><span data-stu-id="77c1d-258">In this step, you use an account with the Editor role to request the creation of a new GPO.</span></span> <span data-ttu-id="77c1d-259">将帐户与审批者角色配合使用，即可批准此请求并完成 GPO 的创建。</span><span class="sxs-lookup"><span data-stu-id="77c1d-259">Using an account with the Approver role, you approve this request and complete the creation of a GPO.</span></span>

**<span data-ttu-id="77c1d-260">请求创建通过 AGPM 管理的新 GPO</span><span class="sxs-lookup"><span data-stu-id="77c1d-260">To request the creation of a new GPO managed through AGPM</span></span>**

1.  <span data-ttu-id="77c1d-261">在已安装了 AGPM 客户端的计算机上，使用已分配了 AGPM 中的编辑器角色的用户帐户登录。</span><span class="sxs-lookup"><span data-stu-id="77c1d-261">On a computer on which you have installed AGPM Client, log on with a user account that has been assigned the Editor role in AGPM.</span></span>

2.  <span data-ttu-id="77c1d-262">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-262">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

3.  <span data-ttu-id="77c1d-263">右键单击 "**更改控制**" 节点，然后单击 "**新建受控 GPO**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-263">Right-click the **Change Control** node, and then click **New Controlled GPO**.</span></span>

4.  <span data-ttu-id="77c1d-264">在 "**新建受控 GPO** " 对话框中：</span><span class="sxs-lookup"><span data-stu-id="77c1d-264">In the **New Controlled GPO** dialog box:</span></span>

    1.  <span data-ttu-id="77c1d-265">若要接收请求的副本，请在 "**抄送**" 字段中键入您的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="77c1d-265">To receive a copy of the request, type your e-mail address in the **Cc** field.</span></span>

    2.  <span data-ttu-id="77c1d-266">键入**MyGPO**作为新 GPO 的名称。</span><span class="sxs-lookup"><span data-stu-id="77c1d-266">Type **MyGPO** as the name for the new GPO.</span></span>

    3.  <span data-ttu-id="77c1d-267">键入新 GPO 的注释。</span><span class="sxs-lookup"><span data-stu-id="77c1d-267">Type a comment for the new GPO.</span></span>

    4.  <span data-ttu-id="77c1d-268">单击 "**创建实时**"，以便在批准后立即将新的 GPO 部署到生产环境。</span><span class="sxs-lookup"><span data-stu-id="77c1d-268">Click **Create live** so the new GPO will be deployed to the production environment immediately upon approval.</span></span> <span data-ttu-id="77c1d-269">单击**提交**。</span><span class="sxs-lookup"><span data-stu-id="77c1d-269">Click **Submit**.</span></span>

5.  <span data-ttu-id="77c1d-270">当**AGPM 进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-270">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="77c1d-271">新的 GPO 将显示在 "**挂起**" 选项卡上。</span><span class="sxs-lookup"><span data-stu-id="77c1d-271">The new GPO is displayed on the **Pending** tab.</span></span>

**<span data-ttu-id="77c1d-272">批准创建 GPO 的挂起请求</span><span class="sxs-lookup"><span data-stu-id="77c1d-272">To approve the pending request to create a GPO</span></span>**

1.  <span data-ttu-id="77c1d-273">在已安装了 AGPM 客户端的计算机上，使用已分配了 AGPM 审批者角色的用户帐户登录。</span><span class="sxs-lookup"><span data-stu-id="77c1d-273">On a computer on which you have installed AGPM Client, log on with a user account that has been assigned the role of Approver in AGPM.</span></span>

2.  <span data-ttu-id="77c1d-274">打开该帐户的电子邮件收件箱，请注意，您已收到一个来自 AGPM 别名的电子邮件，其中包含用于创建 GPO 的编辑器请求。</span><span class="sxs-lookup"><span data-stu-id="77c1d-274">Open the e-mail inbox for the account, and note that you have received an e-mail message from the AGPM alias with the Editor's request to create a GPO.</span></span>

3.  <span data-ttu-id="77c1d-275">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-275">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

4.  <span data-ttu-id="77c1d-276">在 "**目录**" 选项卡上，单击 "**挂起**" 选项卡以显示 "挂起的 gpo"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-276">On the **Contents** tab, click the **Pending** tab to display the pending GPOs.</span></span>

5.  <span data-ttu-id="77c1d-277">右键单击 " **MyGPO**"，然后单击 "**批准**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-277">Right-click **MyGPO**, and then click **Approve**.</span></span>

6.  <span data-ttu-id="77c1d-278">单击 **"是"** 以确认创建 GPO 的批准。</span><span class="sxs-lookup"><span data-stu-id="77c1d-278">Click **Yes** to confirm approval of the creation of the GPO.</span></span> <span data-ttu-id="77c1d-279">GPO 被移动到 "**受控**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="77c1d-279">The GPO is moved to the **Controlled** tab.</span></span>

### <a href="" id="bkmk-manage2"></a><span data-ttu-id="77c1d-280">步骤2：编辑 GPO</span><span class="sxs-lookup"><span data-stu-id="77c1d-280">Step 2: Edit a GPO</span></span>

<span data-ttu-id="77c1d-281">你可以使用 Gpo 配置计算机或用户设置，并将其部署到多台计算机或用户。</span><span class="sxs-lookup"><span data-stu-id="77c1d-281">You can use GPOs to configure computer or user settings and deploy them to many computers or users.</span></span> <span data-ttu-id="77c1d-282">在此步骤中，使用具有编辑器角色的帐户从存档中签出 GPO，脱机编辑 GPO，将编辑的 GPO 签入存档，并向生产环境请求 GPO 部署。</span><span class="sxs-lookup"><span data-stu-id="77c1d-282">In this step, you use an account with the Editor role to check out a GPO from the archive, edit the GPO offline, check the edited GPO into the archive, and request deployment of the GPO to the production environment.</span></span> <span data-ttu-id="77c1d-283">对于此方案，你可以在 GPO 中配置一个设置，要求密码长度至少为八个字符。</span><span class="sxs-lookup"><span data-stu-id="77c1d-283">For this scenario, you configure a setting in the GPO to require that the password be at least eight characters in length.</span></span>

**<span data-ttu-id="77c1d-284">从存档中签出 GPO 以进行编辑</span><span class="sxs-lookup"><span data-stu-id="77c1d-284">To check the GPO out from the archive for editing</span></span>**

1.  <span data-ttu-id="77c1d-285">在已安装了 AGPM 客户端的计算机上，使用已分配了 "编辑者在 AGPM 中的角色" 的用户帐户登录。</span><span class="sxs-lookup"><span data-stu-id="77c1d-285">On a computer on which you have installed AGPM Client, log on with a user account that has been assigned the role of Editor in AGPM.</span></span>

2.  <span data-ttu-id="77c1d-286">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-286">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

3.  <span data-ttu-id="77c1d-287">在 "详细信息" 窗格中的 "**目录**" 选项卡上，单击 "**受控**" 选项卡以显示受控 gpo。</span><span class="sxs-lookup"><span data-stu-id="77c1d-287">On the **Contents** tab in the details pane, click the **Controlled** tab to display the controlled GPOs.</span></span>

4.  <span data-ttu-id="77c1d-288">右键单击 " **MyGPO**"，然后单击 "**签出**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-288">Right-click **MyGPO**, and then click **Check Out**.</span></span>

5.  <span data-ttu-id="77c1d-289">键入要在已签出的 GPO 的历史记录中显示的注释，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="77c1d-289">Type a comment to be displayed in the history of the GPO while it is checked out, and then click **OK**.</span></span>

6.  <span data-ttu-id="77c1d-290">当**AGPM 进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-290">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="77c1d-291">在 "**受控**" 选项卡上，将 GPO 的状态标识为 "**已签出**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-291">On the **Controlled** tab, the state of the GPO is identified as **Checked Out**.</span></span>

**<span data-ttu-id="77c1d-292">脱机编辑 GPO 并配置最小密码长度</span><span class="sxs-lookup"><span data-stu-id="77c1d-292">To edit the GPO offline and configure the minimum password length</span></span>**

1.  <span data-ttu-id="77c1d-293">在 "**受控**" 选项卡上，右键单击 " **MyGPO**"，然后单击 "**编辑**" 以打开 "**组策略管理编辑器**" 窗口，并对 GPO 的脱机副本进行更改。</span><span class="sxs-lookup"><span data-stu-id="77c1d-293">On the **Controlled** tab, right-click **MyGPO**, and then click **Edit** to open the **Group Policy Management Editor** window and make changes to an offline copy of the GPO.</span></span> <span data-ttu-id="77c1d-294">对于此方案，请配置最小密码长度：</span><span class="sxs-lookup"><span data-stu-id="77c1d-294">For this scenario, configure the minimum password length:</span></span>

    1.  <span data-ttu-id="77c1d-295">在 "**计算机配置**" 下，双击 "**策略**"、" **Windows 设置**"、"**安全设置**"、"**帐户策略**" 和 "**密码策略**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-295">Under **Computer Configuration**, double-click **Policies**, **Windows Settings**, **Security Settings**, **Account Policies**, and **Password Policy**.</span></span>

    2.  <span data-ttu-id="77c1d-296">在 "详细信息" 窗格中，双击 "**最小密码长度**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-296">In the details pane, double-click **Minimum password length**.</span></span>

    3.  <span data-ttu-id="77c1d-297">在 "属性" 窗口中，选中 "**定义此策略设置**" 复选框，将字符数设置为**8**，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="77c1d-297">In the properties window, select the **Define this policy setting** check box, set the number of characters to **8**, and then click **OK**.</span></span>

2.  <span data-ttu-id="77c1d-298">关闭 "**组策略管理编辑器**" 窗口。</span><span class="sxs-lookup"><span data-stu-id="77c1d-298">Close the **Group Policy Management Editor** window.</span></span>

**<span data-ttu-id="77c1d-299">将 GPO 签入存档</span><span class="sxs-lookup"><span data-stu-id="77c1d-299">To check the GPO into the archive</span></span>**

1.  <span data-ttu-id="77c1d-300">在 "**受控**" 选项卡上，右键单击 " **MyGPO** "，然后单击 "**签入**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-300">On the **Controlled** tab, right-click **MyGPO** and then click **Check In**.</span></span>

2.  <span data-ttu-id="77c1d-301">键入批注，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="77c1d-301">Type a comment, and then click **OK**.</span></span>

3.  <span data-ttu-id="77c1d-302">当**AGPM 进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-302">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="77c1d-303">在 "**受控**" 选项卡上，将 GPO 的状态标识为 **"已签入**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-303">On the **Controlled** tab, the state of the GPO is identified as **Checked In**.</span></span>

**<span data-ttu-id="77c1d-304">请求将 GPO 部署到生产环境</span><span class="sxs-lookup"><span data-stu-id="77c1d-304">To request the deployment of the GPO to the production environment</span></span>**

1.  <span data-ttu-id="77c1d-305">在 "**受控**" 选项卡上，右键单击 " **MyGPO** "，然后单击 "**部署**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-305">On the **Controlled** tab, right-click **MyGPO** and then click **Deploy**.</span></span>

2.  <span data-ttu-id="77c1d-306">由于此帐户不是审批者或 AGPM 管理员，因此必须提交部署请求。</span><span class="sxs-lookup"><span data-stu-id="77c1d-306">Because this account is not an Approver or AGPM Administrator, you must submit a request for deployment.</span></span> <span data-ttu-id="77c1d-307">若要接收请求的副本，请在 "**抄送**" 字段中键入您的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="77c1d-307">To receive a copy of the request, type your e-mail address in the **Cc** field.</span></span> <span data-ttu-id="77c1d-308">键入要在 GPO 的历史记录中显示的注释，然后单击 "**提交**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-308">Type a comment to be displayed in the history of the GPO, and then click **Submit**.</span></span>

3.  <span data-ttu-id="77c1d-309">当**AGPM 进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-309">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="77c1d-310">**MyGPO**将显示在 "**挂起**" 选项卡上的 gpo 列表中。</span><span class="sxs-lookup"><span data-stu-id="77c1d-310">**MyGPO** is displayed on the list of GPOs on the **Pending** tab.</span></span>

### <a href="" id="bkmk-manage3"></a><span data-ttu-id="77c1d-311">步骤3：查看和部署 GPO</span><span class="sxs-lookup"><span data-stu-id="77c1d-311">Step 3: Review and deploy a GPO</span></span>

<span data-ttu-id="77c1d-312">在此步骤中，你充当审批者，创建报表和分析 GPO 中的设置以及对设置的更改，以确定是否应批准这些设置。</span><span class="sxs-lookup"><span data-stu-id="77c1d-312">In this step, you act as an Approver, creating reports and analyzing the settings and changes to settings in the GPO to determine whether you should approve them.</span></span> <span data-ttu-id="77c1d-313">评估 GPO 后，将其部署到生产环境并将其链接到域或组织单位（OU），以便在为该域或 OU 中的计算机刷新组策略时，它将生效。</span><span class="sxs-lookup"><span data-stu-id="77c1d-313">After evaluating the GPO, you deploy it to the production environment and link it to a domain or an organizational unit (OU) so that it takes effect when Group Policy is refreshed for computers in that domain or OU.</span></span>

**<span data-ttu-id="77c1d-314">查看 GPO 中的设置</span><span class="sxs-lookup"><span data-stu-id="77c1d-314">To review settings in the GPO</span></span>**

1. <span data-ttu-id="77c1d-315">在已安装了 AGPM 客户端的计算机上，使用已分配了 AGPM 审批者角色的用户帐户登录。</span><span class="sxs-lookup"><span data-stu-id="77c1d-315">On a computer on which you have installed AGPM Client, log on with a user account that has been assigned the role of Approver in AGPM.</span></span> <span data-ttu-id="77c1d-316">（包含在所有其他角色中的审阅者角色的任何组策略管理员可以查看 GPO 中的设置。）</span><span class="sxs-lookup"><span data-stu-id="77c1d-316">(Any Group Policy administrator with the Reviewer role, which is included in all of the other roles, can review the settings in a GPO.)</span></span>

2. <span data-ttu-id="77c1d-317">打开该帐户的电子邮件收件箱，请注意，您已收到来自 AGPM 别名的电子邮件，其中包含用于部署 GPO 的编辑器请求。</span><span class="sxs-lookup"><span data-stu-id="77c1d-317">Open the e-mail inbox for the account and note that you have received an e-mail message from the AGPM alias with an Editor's request to deploy a GPO.</span></span>

3. <span data-ttu-id="77c1d-318">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-318">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

4. <span data-ttu-id="77c1d-319">在 "详细信息" 窗格中的 "**目录**" 选项卡上，单击 "**挂起**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="77c1d-319">On the **Contents** tab in the details pane, click the **Pending** tab.</span></span>

5. <span data-ttu-id="77c1d-320">双击 " **MyGPO** " 以显示其历史记录。</span><span class="sxs-lookup"><span data-stu-id="77c1d-320">Double-click **MyGPO** to display its history.</span></span>

6. <span data-ttu-id="77c1d-321">查看最新版本的 MyGPO 中的设置：</span><span class="sxs-lookup"><span data-stu-id="77c1d-321">Review the settings in the most recent version of MyGPO:</span></span>

   1.  <span data-ttu-id="77c1d-322">在 "**历史记录**" 窗口中，右键单击具有最新时间戳的 GPO 版本，单击 "**设置**"，然后单击 " **HTML 报表**" 以显示 GPO 设置的摘要。</span><span class="sxs-lookup"><span data-stu-id="77c1d-322">In the **History** window, right-click the GPO version with the most recent timestamp, click **Settings**, and then click **HTML Report** to display a summary of the GPO's settings.</span></span>

   2.  <span data-ttu-id="77c1d-323">在 Web 浏览器中，单击 "**全部显示**" 以显示 GPO 中的所有设置。</span><span class="sxs-lookup"><span data-stu-id="77c1d-323">In the Web browser, click **show all** to display all of the settings in the GPO.</span></span> <span data-ttu-id="77c1d-324">关闭浏览器。</span><span class="sxs-lookup"><span data-stu-id="77c1d-324">Close the browser.</span></span>

7. <span data-ttu-id="77c1d-325">将最新版本的 MyGPO 与签入到存档中的第一个版本进行比较：</span><span class="sxs-lookup"><span data-stu-id="77c1d-325">Compare the most recent version of MyGPO to the first version checked in to the archive:</span></span>

   1. <span data-ttu-id="77c1d-326">在 "**历史记录**" 窗口中，单击具有最新时间戳的 GPO 版本。</span><span class="sxs-lookup"><span data-stu-id="77c1d-326">In the **History** window, click the GPO version with the most recent time stamp.</span></span> <span data-ttu-id="77c1d-327">按 CTRL 并单击**计算机版本**不是 \* \* \\ \* \* \* 的最旧 GPO 版本。</span><span class="sxs-lookup"><span data-stu-id="77c1d-327">Press CTRL and click the oldest GPO version for which the **Computer Version** is not \*\*\\*\*\*.</span></span>

   2. <span data-ttu-id="77c1d-328">单击 "**差异**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="77c1d-328">Click the **Differences** button.</span></span> <span data-ttu-id="77c1d-329">"**帐户策略/密码策略**" 部分以绿色突出显示，前面是**\ [+ \]**，表示此设置仅在 GPO 的后一版本中配置。</span><span class="sxs-lookup"><span data-stu-id="77c1d-329">The **Account Policies/Password Policy** section is highlighted in green and preceded by **\[+\]**, indicating that this setting is configured only in the latter version of the GPO.</span></span>

   3. <span data-ttu-id="77c1d-330">单击 "**帐户策略/密码策略**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-330">Click **Account Policies/Password Policy**.</span></span> <span data-ttu-id="77c1d-331">"**最小密码长度**" 设置也将以绿色突出显示，并以 " \**+ \**" 开头，以指示它仅在 GPO 的后版本中进行配置。</span><span class="sxs-lookup"><span data-stu-id="77c1d-331">The **Minimum password length** setting is also highlighted in green and preceded by **\[+\]**, indicating that it is configured only in the latter version of the GPO.</span></span>

   4. <span data-ttu-id="77c1d-332">关闭 Web 浏览器。</span><span class="sxs-lookup"><span data-stu-id="77c1d-332">Close the Web browser.</span></span>

**<span data-ttu-id="77c1d-333">将 GPO 部署到生产环境</span><span class="sxs-lookup"><span data-stu-id="77c1d-333">To deploy the GPO to the production environment</span></span>**

1.  <span data-ttu-id="77c1d-334">在 "**挂起**" 选项卡上，右键单击 " **MyGPO** "，然后单击 "**批准**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-334">On the **Pending** tab, right-click **MyGPO** and then click **Approve**.</span></span>

2.  <span data-ttu-id="77c1d-335">键入要包含在 GPO 历史记录中的注释。</span><span class="sxs-lookup"><span data-stu-id="77c1d-335">Type a comment to include in the history of the GPO.</span></span>

3.  <span data-ttu-id="77c1d-336">单击**是**。</span><span class="sxs-lookup"><span data-stu-id="77c1d-336">Click **Yes**.</span></span> <span data-ttu-id="77c1d-337">当**AGPM 进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-337">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="77c1d-338">GPO 已部署到生产环境。</span><span class="sxs-lookup"><span data-stu-id="77c1d-338">The GPO is deployed to the production environment.</span></span>

**<span data-ttu-id="77c1d-339">将 GPO 链接到域或组织单位</span><span class="sxs-lookup"><span data-stu-id="77c1d-339">To link the GPO to a domain or organizational unit</span></span>**

1.  <span data-ttu-id="77c1d-340">在 GPMC 中，右键单击要对其应用你配置的 GPO 的域或 OU，然后单击 "**链接现有 gpo**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-340">In the GPMC, right-click the domain or an OU to which to apply the GPO that you configured, and then click **Link an Existing GPO**.</span></span>

2.  <span data-ttu-id="77c1d-341">在 "**选择 GPO** " 对话框中，单击 " **MyGPO**"，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="77c1d-341">In the **Select GPO** dialog box, click **MyGPO**, and then click **OK**.</span></span>

### <a href="" id="bkmk-manage4"></a><span data-ttu-id="77c1d-342">步骤4：使用模板创建 GPO</span><span class="sxs-lookup"><span data-stu-id="77c1d-342">Step 4: Use a template to create a GPO</span></span>

<span data-ttu-id="77c1d-343">在此步骤中，使用具有编辑器角色的帐户创建模板（不可编辑的静态版本，用作创建新 Gpo 的起始点），然后基于该模板创建新的 GPO。</span><span class="sxs-lookup"><span data-stu-id="77c1d-343">In this step, you use an account with the Editor role to create a template—an uneditable, static version of a GPO for use as a starting point for creating new GPOs—and then create a new GPO based upon that template.</span></span> <span data-ttu-id="77c1d-344">模板对于快速创建包含许多相同设置的多个 Gpo 非常有用。</span><span class="sxs-lookup"><span data-stu-id="77c1d-344">Templates are useful for quickly creating multiple GPOs that include many of the same settings.</span></span>

**<span data-ttu-id="77c1d-345">基于现有 GPO 创建模板</span><span class="sxs-lookup"><span data-stu-id="77c1d-345">To create a template based on an existing GPO</span></span>**

1.  <span data-ttu-id="77c1d-346">在已安装了 AGPM 客户端的计算机上，使用已分配了 "编辑者在 AGPM 中的角色" 的用户帐户登录。</span><span class="sxs-lookup"><span data-stu-id="77c1d-346">On a computer on which you have installed AGPM Client, log on with a user account that has been assigned the role of Editor in AGPM.</span></span>

2.  <span data-ttu-id="77c1d-347">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-347">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

3.  <span data-ttu-id="77c1d-348">在 "详细信息" 窗格中的 "**目录**" 选项卡上，单击 "**受控**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="77c1d-348">On the **Contents** tab in the details pane, click the **Controlled** tab.</span></span>

4.  <span data-ttu-id="77c1d-349">右键单击 " **MyGPO**"，然后单击 "**另存为模板**"，创建一个模板，其中包含当前在 MyGPO 中的所有设置。</span><span class="sxs-lookup"><span data-stu-id="77c1d-349">Right-click **MyGPO**, and then click **Save as Template** to create a template incorporating all settings currently in MyGPO.</span></span>

5.  <span data-ttu-id="77c1d-350">键入**MyTemplate**作为模板名称和注释，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="77c1d-350">Type **MyTemplate** as the name for the template and a comment, and then click **OK**.</span></span>

6.  <span data-ttu-id="77c1d-351">当**AGPM 进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-351">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="77c1d-352">新模板将显示在 "**模板**" 选项卡上。</span><span class="sxs-lookup"><span data-stu-id="77c1d-352">The new template appears on the **Templates** tab.</span></span>

**<span data-ttu-id="77c1d-353">请求创建通过 AGPM 管理的新 GPO</span><span class="sxs-lookup"><span data-stu-id="77c1d-353">To request the creation of a new GPO managed through AGPM</span></span>**

1.  <span data-ttu-id="77c1d-354">单击 "**受控**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="77c1d-354">Click the **Controlled** tab.</span></span>

2.  <span data-ttu-id="77c1d-355">右键单击 "**更改控制**" 节点，然后单击 "**新建受控 GPO**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-355">Right-click the **Change Control** node, and then click **New Controlled GPO**.</span></span>

3.  <span data-ttu-id="77c1d-356">在 "**新建受控 GPO** " 对话框中：</span><span class="sxs-lookup"><span data-stu-id="77c1d-356">In the **New Controlled GPO** dialog box:</span></span>

    1.  <span data-ttu-id="77c1d-357">若要接收请求的副本，请在 "**抄送**" 字段中键入您的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="77c1d-357">To receive a copy of the request, type your e-mail address in the **Cc** field.</span></span>

    2.  <span data-ttu-id="77c1d-358">键入**MyOtherGPO**作为新 GPO 的名称。</span><span class="sxs-lookup"><span data-stu-id="77c1d-358">Type **MyOtherGPO** as the name for the new GPO.</span></span>

    3.  <span data-ttu-id="77c1d-359">键入新 GPO 的注释。</span><span class="sxs-lookup"><span data-stu-id="77c1d-359">Type a comment for the new GPO.</span></span>

    4.  <span data-ttu-id="77c1d-360">单击 "**创建实时**"，这样新的 GPO 将在批准后立即部署到生产环境中。</span><span class="sxs-lookup"><span data-stu-id="77c1d-360">Click **Create live**, so the new GPO will be deployed to the production environment immediately upon approval.</span></span>

    5.  <span data-ttu-id="77c1d-361">**在 "来自 GPO 模板**" 中，选择 " **MyTemplate**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-361">For **From GPO template**, select **MyTemplate**.</span></span> <span data-ttu-id="77c1d-362">单击**提交**。</span><span class="sxs-lookup"><span data-stu-id="77c1d-362">Click **Submit**.</span></span>

4.  <span data-ttu-id="77c1d-363">当**AGPM 进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-363">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="77c1d-364">新的 GPO 将显示在 "**挂起**" 选项卡上。</span><span class="sxs-lookup"><span data-stu-id="77c1d-364">The new GPO is displayed on the **Pending** tab.</span></span>

<span data-ttu-id="77c1d-365">使用已分配给审批者角色的帐户，以批准挂起的请求以创建 GPO （如步骤1中所[执行的操作）：创建 gpo](#bkmk-manage1)。</span><span class="sxs-lookup"><span data-stu-id="77c1d-365">Use an account that has been assigned the role of Approver to approve the pending request to create the GPO as you did in [Step 1: Create a GPO](#bkmk-manage1).</span></span> <span data-ttu-id="77c1d-366">MyTemplate 包含您在 MyGPO 中配置的所有设置。</span><span class="sxs-lookup"><span data-stu-id="77c1d-366">MyTemplate incorporates all of the settings that you configured in MyGPO.</span></span> <span data-ttu-id="77c1d-367">由于 MyOtherGPO 是使用 MyTemplate 创建的，因此它最初包含在创建 MyTemplate 时 MyGPO 包含的所有设置。</span><span class="sxs-lookup"><span data-stu-id="77c1d-367">Because MyOtherGPO was created using MyTemplate, it initially contains all of the settings that MyGPO contained at the time that MyTemplate was created.</span></span> <span data-ttu-id="77c1d-368">你可以通过生成差异报表来将 MyOtherGPO 与 MyTemplate 进行比较来确认。</span><span class="sxs-lookup"><span data-stu-id="77c1d-368">You can confirm this by generating a difference report to compare MyOtherGPO to MyTemplate.</span></span>

**<span data-ttu-id="77c1d-369">从存档中签出 GPO 以进行编辑</span><span class="sxs-lookup"><span data-stu-id="77c1d-369">To check the GPO out from the archive for editing</span></span>**

1.  <span data-ttu-id="77c1d-370">在已安装了 AGPM 客户端的计算机上，使用已分配了 "编辑者在 AGPM 中的角色" 的用户帐户登录。</span><span class="sxs-lookup"><span data-stu-id="77c1d-370">On a computer on which you have installed AGPM Client, log on with a user account that has been assigned the role of Editor in AGPM.</span></span>

2.  <span data-ttu-id="77c1d-371">右键单击 " **MyOtherGPO**"，然后单击 "**签出**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-371">Right-click **MyOtherGPO**, and then click **Check Out**.</span></span>

3.  <span data-ttu-id="77c1d-372">键入要在已签出的 GPO 的历史记录中显示的注释，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="77c1d-372">Type a comment to be displayed in the history of the GPO while it is checked out, and then click **OK**.</span></span>

4.  <span data-ttu-id="77c1d-373">当**AGPM 进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-373">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="77c1d-374">在 "**受控**" 选项卡上，将 GPO 的状态标识为 "**已签出**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-374">On the **Controlled** tab, the state of the GPO is identified as **Checked Out**.</span></span>

**<span data-ttu-id="77c1d-375">脱机编辑该 GPO 并配置帐户锁定时间</span><span class="sxs-lookup"><span data-stu-id="77c1d-375">To edit the GPO offline and configure the account lockout duration</span></span>**

1.  <span data-ttu-id="77c1d-376">在 "**受控**" 选项卡上，右键单击 " **MyOtherGPO**"，然后单击 "**编辑**" 以打开 "**组策略管理编辑器**" 窗口，并对 GPO 的脱机副本进行更改。</span><span class="sxs-lookup"><span data-stu-id="77c1d-376">On the **Controlled** tab, right-click **MyOtherGPO**, and then click **Edit** to open the **Group Policy Management Editor** window and make changes to an offline copy of the GPO.</span></span> <span data-ttu-id="77c1d-377">对于此方案，请配置最小密码长度：</span><span class="sxs-lookup"><span data-stu-id="77c1d-377">For this scenario, configure the minimum password length:</span></span>

    1.  <span data-ttu-id="77c1d-378">在 "**计算机配置**" 下，双击 "**策略**"、" **Windows 设置**"、"**安全设置**"、"**帐户策略**" 和 "**帐户锁定策略**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-378">Under **Computer Configuration**, double-click **Policies**, **Windows Settings**, **Security Settings**, **Account Policies**, and **Account Lockout Policy**.</span></span>

    2.  <span data-ttu-id="77c1d-379">在 "详细信息" 窗格中，双击 "**帐户锁定时间**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-379">In the details pane, double-click **Account lockout duration**.</span></span>

    3.  <span data-ttu-id="77c1d-380">在 "属性" 窗口中，选中 "**定义此策略设置**"，将 "持续时间" 设置为 " **30**分钟"，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="77c1d-380">In the properties window, check **Define this policy setting**, set the duration to **30** minutes, and then click **OK**.</span></span>

2.  <span data-ttu-id="77c1d-381">关闭 "**组策略管理编辑器**" 窗口。</span><span class="sxs-lookup"><span data-stu-id="77c1d-381">Close the **Group Policy Management Editor** window.</span></span>

<span data-ttu-id="77c1d-382">在[步骤2：编辑 GPO](#bkmk-manage2)中，将 MyOtherGPO 签入存档并请求部署。</span><span class="sxs-lookup"><span data-stu-id="77c1d-382">Check MyOtherGPO into the archive and request deployment as you did for MyGPO in [Step 2: Edit a GPO](#bkmk-manage2).</span></span> <span data-ttu-id="77c1d-383">你可以使用差异报告将 MyOtherGPO 与 MyGPO 或 MyTemplate 进行比较。</span><span class="sxs-lookup"><span data-stu-id="77c1d-383">You can compare MyOtherGPO to MyGPO or to MyTemplate using difference reports.</span></span> <span data-ttu-id="77c1d-384">任何包含审阅者角色的帐户（AGPM 管理员 \ [完全控制 \]、审批者、编辑者或审阅者）都可以生成报表。</span><span class="sxs-lookup"><span data-stu-id="77c1d-384">Any account that includes the Reviewer role (AGPM Administrator \[Full Control\], Approver, Editor, or Reviewer) can generate reports.</span></span>

**<span data-ttu-id="77c1d-385">将 GPO 与另一个 GPO 和模板进行比较</span><span class="sxs-lookup"><span data-stu-id="77c1d-385">To compare a GPO to another GPO and to a template</span></span>**

1.  <span data-ttu-id="77c1d-386">要比较 MyGPO 和 MyOtherGPO，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="77c1d-386">To compare MyGPO and MyOtherGPO:</span></span>

    1.  <span data-ttu-id="77c1d-387">在 "**受控**" 选项卡上，单击 " **MyGPO**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-387">On the **Controlled** tab, click **MyGPO**.</span></span> <span data-ttu-id="77c1d-388">按 CTRL，然后单击 " **MyOtherGPO**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-388">Press CTRL and then click **MyOtherGPO**.</span></span>

    2.  <span data-ttu-id="77c1d-389">右键单击 " **MyOtherGPO**"，指向 "**差异**"，然后单击 " **HTML 报表**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-389">Right-click **MyOtherGPO**, point to **Differences**, and click **HTML Report**.</span></span>

2.  <span data-ttu-id="77c1d-390">要比较 MyOtherGPO 和 MyTemplate，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="77c1d-390">To compare MyOtherGPO and MyTemplate:</span></span>

    1.  <span data-ttu-id="77c1d-391">在 "**受控**" 选项卡上，单击 " **MyOtherGPO**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-391">On the **Controlled** tab, click **MyOtherGPO**.</span></span>

    2.  <span data-ttu-id="77c1d-392">右键单击 " **MyOtherGPO**"，指向 "**差异**"，然后单击 "**模板**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-392">Right-click **MyOtherGPO**, point to **Differences**, and click **Template**.</span></span>

    3.  <span data-ttu-id="77c1d-393">选择 " **MyTemplate** " 和 " **HTML 报表**"，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="77c1d-393">Select **MyTemplate** and **HTML Report**, and then click **OK**.</span></span>

### <a href="" id="bkmk-manage5"></a><span data-ttu-id="77c1d-394">步骤5：删除和还原 GPO</span><span class="sxs-lookup"><span data-stu-id="77c1d-394">Step 5: Delete and restore a GPO</span></span>

<span data-ttu-id="77c1d-395">在此步骤中，你充当审批者以删除 GPO。</span><span class="sxs-lookup"><span data-stu-id="77c1d-395">In this step, you act as an Approver to delete a GPO.</span></span>

**<span data-ttu-id="77c1d-396">删除 GPO</span><span class="sxs-lookup"><span data-stu-id="77c1d-396">To delete a GPO</span></span>**

1.  <span data-ttu-id="77c1d-397">在已安装了 AGPM 客户端的计算机上，使用已分配有审批者角色的用户帐户登录。</span><span class="sxs-lookup"><span data-stu-id="77c1d-397">On a computer on which you have installed AGPM Client, log on with a user account that has been assigned the role of Approver.</span></span>

2.  <span data-ttu-id="77c1d-398">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-398">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

3.  <span data-ttu-id="77c1d-399">在 "**目录**" 选项卡上，单击 "**受控**" 选项卡以显示受控 gpo。</span><span class="sxs-lookup"><span data-stu-id="77c1d-399">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

4.  <span data-ttu-id="77c1d-400">右键单击 " **MyGPO**"，然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-400">Right-click **MyGPO**, and then click **Delete**.</span></span> <span data-ttu-id="77c1d-401">单击 "**从存档和生产中删除 GPO** " 以删除存档中的版本以及在生产环境中部署的 gpo 的部署版本。</span><span class="sxs-lookup"><span data-stu-id="77c1d-401">Click **Delete GPO from archive and production** to delete both the version in the archive as well as the deployed version of the GPO in the production environment.</span></span>

5.  <span data-ttu-id="77c1d-402">键入要显示在 GPO 审核跟踪中的注释，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="77c1d-402">Type a comment to be displayed in the audit trail for the GPO, and then click **OK**.</span></span>

6.  <span data-ttu-id="77c1d-403">当**AGPM 进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-403">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="77c1d-404">GPO 将从 "**受控**" 选项卡中删除，并显示在 "**回收站**" 选项卡上，可在其中还原或销毁。</span><span class="sxs-lookup"><span data-stu-id="77c1d-404">The GPO is removed from the **Controlled** tab and is displayed on the **Recycle Bin** tab, where it can be restored or destroyed.</span></span>

<span data-ttu-id="77c1d-405">有时，你可能会在删除仍需要的 GPO 后发现。</span><span class="sxs-lookup"><span data-stu-id="77c1d-405">Occasionally you may discover after deleting a GPO that it is still needed.</span></span> <span data-ttu-id="77c1d-406">在此步骤中，你充当审批者以还原已删除的 GPO。</span><span class="sxs-lookup"><span data-stu-id="77c1d-406">In this step, you act as an Approver to restore a GPO that has been deleted.</span></span>

**<span data-ttu-id="77c1d-407">还原已删除的 GPO</span><span class="sxs-lookup"><span data-stu-id="77c1d-407">To restore a deleted GPO</span></span>**

1.  <span data-ttu-id="77c1d-408">在 "**目录**" 选项卡上，单击 "**回收站**" 选项卡以显示已删除的 gpo。</span><span class="sxs-lookup"><span data-stu-id="77c1d-408">On the **Contents** tab, click the **Recycle Bin** tab to display deleted GPOs.</span></span>

2.  <span data-ttu-id="77c1d-409">右键单击 " **MyGPO**"，然后单击 "**还原**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-409">Right-click **MyGPO**, and then click **Restore**.</span></span>

3.  <span data-ttu-id="77c1d-410">键入要在 GPO 的历史记录中显示的注释，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="77c1d-410">Type a comment to be displayed in the history of the GPO, and then click **OK**.</span></span>

4.  <span data-ttu-id="77c1d-411">当**AGPM 进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-411">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="77c1d-412">该 GPO 将从 "**回收站**" 选项卡中删除，并显示在 "**受控**" 选项卡上。</span><span class="sxs-lookup"><span data-stu-id="77c1d-412">The GPO is removed from the **Recycle Bin** tab and is displayed on the **Controlled** tab.</span></span>

    <span data-ttu-id="77c1d-413">**注意** 将 GPO 还原到存档不会自动将其重新部署到生产环境。</span><span class="sxs-lookup"><span data-stu-id="77c1d-413">**Note** Restoring a GPO to the archive does not automatically redeploy it to the production environment.</span></span> <span data-ttu-id="77c1d-414">若要将 GPO 返回到生产环境，请按照[步骤3部署 gpo：查看和部署 gpo](#bkmk-manage3)。</span><span class="sxs-lookup"><span data-stu-id="77c1d-414">To return the GPO to the production environment, deploy the GPO as in [Step 3: Review and deploy a GPO](#bkmk-manage3).</span></span>

     

<span data-ttu-id="77c1d-415">在编辑和部署 GPO 之后，你可能会发现对 GPO 所做的最新更改会导致出现问题。</span><span class="sxs-lookup"><span data-stu-id="77c1d-415">After editing and deploying a GPO, you may discover that recent changes to the GPO are causing a problem.</span></span> <span data-ttu-id="77c1d-416">在此步骤中，你充当审批者以回退到 GPO 的以前版本。</span><span class="sxs-lookup"><span data-stu-id="77c1d-416">In this step, you act as an Approver to roll back to a previous version of the GPO.</span></span> <span data-ttu-id="77c1d-417">你可以回退到 GPO 历史记录中的任意版本。</span><span class="sxs-lookup"><span data-stu-id="77c1d-417">You can roll back to any version in the history of the GPO.</span></span> <span data-ttu-id="77c1d-418">你可以使用批注和标签来标识已知的有效版本以及进行特定的更改。</span><span class="sxs-lookup"><span data-stu-id="77c1d-418">You can use comments and labels to identify known good versions and when specific changes were made.</span></span>

**<span data-ttu-id="77c1d-419">回滚到 GPO 的以前版本</span><span class="sxs-lookup"><span data-stu-id="77c1d-419">To roll back to a previous version of a GPO</span></span>**

1.  <span data-ttu-id="77c1d-420">在 "**目录**" 选项卡上，单击 "**受控**" 选项卡以显示受控 gpo。</span><span class="sxs-lookup"><span data-stu-id="77c1d-420">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

2.  <span data-ttu-id="77c1d-421">双击 " **MyGPO** " 以显示其历史记录。</span><span class="sxs-lookup"><span data-stu-id="77c1d-421">Double-click **MyGPO** to display its history.</span></span>

3.  <span data-ttu-id="77c1d-422">右键单击要部署的版本，单击 "**部署**"，然后单击 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="77c1d-422">Right-click the version to be deployed, click **Deploy**, and then click **Yes**.</span></span>

4.  <span data-ttu-id="77c1d-423">当**进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-423">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="77c1d-424">在 "**历史记录**" 窗口中，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-424">In the **History** window, click **Close**.</span></span>

    <span data-ttu-id="77c1d-425">**注意** 若要验证已重新部署的版本是否为所需版本，请检查两个版本的差异报告。</span><span class="sxs-lookup"><span data-stu-id="77c1d-425">**Note** To verify that the version that has been redeployed is the version intended, examine a difference report for the two versions.</span></span> <span data-ttu-id="77c1d-426">在 GPO 的 "**历史记录**" 窗口中，选择两个版本，右键单击它们，指向 "**差异**"，然后单击 " **HTML 报表**" 或 " **XML 报表**"。</span><span class="sxs-lookup"><span data-stu-id="77c1d-426">In the **History** window for the GPO, select the two versions, right-click them, point to **Difference**, and then click either **HTML Report** or **XML Report**.</span></span>

     

 

 





