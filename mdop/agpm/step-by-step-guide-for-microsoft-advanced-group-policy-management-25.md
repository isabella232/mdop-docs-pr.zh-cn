---
title: Microsoft 高级组策略管理 2.5 分步指南
description: Microsoft 高级组策略管理 2.5 分步指南
author: dansimp
ms.assetid: 454298c9-0fab-497a-9808-c0246a4c8db5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 67925e417e4fb1f5398dfd030f366936f1d36909
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802519"
---
# <span data-ttu-id="aebdf-103">Microsoft 高级组策略管理 2.5 分步指南</span><span class="sxs-lookup"><span data-stu-id="aebdf-103">Step-by-Step Guide for Microsoft Advanced Group Policy Management 2.5</span></span>


<span data-ttu-id="aebdf-104">本分步指南介绍了使用组策略管理控制台（GPMC）和 Microsoft 高级组策略管理（AGPM）进行组策略管理的高级技术。</span><span class="sxs-lookup"><span data-stu-id="aebdf-104">This step-by-step guide demonstrates advanced techniques for Group Policy management using the Group Policy Management Console (GPMC) and Microsoft Advanced Group Policy Management (AGPM).</span></span> <span data-ttu-id="aebdf-105">AGPM 增加了 GPMC 的功能，提供：</span><span class="sxs-lookup"><span data-stu-id="aebdf-105">AGPM increases the capabilities of the GPMC, providing:</span></span>

-   <span data-ttu-id="aebdf-106">将管理组策略对象（Gpo）的权限委派给多个组策略管理员的标准角色。</span><span class="sxs-lookup"><span data-stu-id="aebdf-106">Standard roles for delegating permissions to manage Group Policy objects (GPOs) to multiple Group Policy administrators.</span></span>

-   <span data-ttu-id="aebdf-107">允许组策略管理员在将 Gpo 部署到生产环境之前脱机创建和修改 Gpo 的存档。</span><span class="sxs-lookup"><span data-stu-id="aebdf-107">An archive to enable Group Policy administrators to create and modify GPOs offline before deploying them to a production environment.</span></span>

-   <span data-ttu-id="aebdf-108">回滚到任何以前版本的 GPO 的功能。</span><span class="sxs-lookup"><span data-stu-id="aebdf-108">The ability to roll back to any previous version of a GPO.</span></span>

-   <span data-ttu-id="aebdf-109">Gpo 的签入/签出功能，以确保组策略管理员不会无意间覆盖彼此的工作。</span><span class="sxs-lookup"><span data-stu-id="aebdf-109">Check-in/check-out capability for GPOs to ensure that Group Policy administrators do not inadvertently overwrite each other's work.</span></span>

## <span data-ttu-id="aebdf-110">AGPM 方案概述</span><span class="sxs-lookup"><span data-stu-id="aebdf-110">AGPM scenario overview</span></span>


<span data-ttu-id="aebdf-111">对于此方案，你将为 AGPM 中的每个角色使用单独的用户帐户，演示如何在具有不同级别的权限的多个组策略管理员的环境中管理组策略。</span><span class="sxs-lookup"><span data-stu-id="aebdf-111">For this scenario, you will use a separate user account for each role in AGPM to demonstrate how Group Policy can be managed in an environment with multiple Group Policy administrators who have different levels of permissions.</span></span> <span data-ttu-id="aebdf-112">具体地说，你将执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="aebdf-112">Specifically, you will perform the following tasks:</span></span>

-   <span data-ttu-id="aebdf-113">使用属于域管理员组成员的帐户，安装 AGPM 服务器并将 AGPM 管理员角色分配给帐户或组。</span><span class="sxs-lookup"><span data-stu-id="aebdf-113">Using an account that is a member of the Domain Admins group, install AGPM Server and assign the AGPM Administrator role to an account or group.</span></span>

-   <span data-ttu-id="aebdf-114">使用您将为其分配 AGPM 角色的帐户，安装 AGPM 客户端。</span><span class="sxs-lookup"><span data-stu-id="aebdf-114">Using accounts to which you will assign AGPM roles, install AGPM Client.</span></span>

-   <span data-ttu-id="aebdf-115">将帐户与 AGPM 管理员角色配合使用，配置 AGPM 并通过向其他帐户分配角色来委派对 Gpo 的访问权限。</span><span class="sxs-lookup"><span data-stu-id="aebdf-115">Using an account with the AGPM Administrator role, configure AGPM and delegate access to GPOs by assigning roles to other accounts.</span></span>

-   <span data-ttu-id="aebdf-116">使用具有 "编辑者" 角色的帐户，请求创建 GPO，然后使用审批者角色的帐户进行审批。</span><span class="sxs-lookup"><span data-stu-id="aebdf-116">Using an account with the Editor role, request the creation of a GPO, which you then approve using an account with the Approver role.</span></span> <span data-ttu-id="aebdf-117">通过编辑器帐户，将 GPO 从存档中签出，编辑 GPO，将 GPO 签入存档，然后请求部署。</span><span class="sxs-lookup"><span data-stu-id="aebdf-117">With the Editor account, check the GPO out of the archive, edit the GPO, check the GPO into the archive, and request deployment.</span></span>

-   <span data-ttu-id="aebdf-118">对审批者角色使用帐户，查看 GPO 并将其部署到生产环境。</span><span class="sxs-lookup"><span data-stu-id="aebdf-118">Using an account with the Approver role, review the GPO and deploy it to your production environment.</span></span>

-   <span data-ttu-id="aebdf-119">使用具有编辑器角色的帐户创建 GPO 模板，并将其用作创建新 GPO 的起始点。</span><span class="sxs-lookup"><span data-stu-id="aebdf-119">Using an account with the Editor role, create a GPO template and use it as a starting point to create a new GPO.</span></span>

-   <span data-ttu-id="aebdf-120">将帐户与审批者角色一起使用，删除和还原 GPO。</span><span class="sxs-lookup"><span data-stu-id="aebdf-120">Using an account with the Approver role, delete and restore a GPO.</span></span>

![组策略对象开发过程](images/ab77a1f3-f430-4e7d-be58-ee8f9bd1140e.gif)

## <span data-ttu-id="aebdf-122">要求</span><span class="sxs-lookup"><span data-stu-id="aebdf-122">Requirements</span></span>


<span data-ttu-id="aebdf-123">要安装 AGPM 的计算机必须满足以下要求，并且你必须创建用于此方案的帐户。</span><span class="sxs-lookup"><span data-stu-id="aebdf-123">Computers on which you want to install AGPM must meet the following requirements, and you must create accounts for use in this scenario.</span></span>

### <span data-ttu-id="aebdf-124">AGPM 服务器要求</span><span class="sxs-lookup"><span data-stu-id="aebdf-124">AGPM Server requirements</span></span>

<span data-ttu-id="aebdf-125">AGPM 服务器2.5 需要 WindowsVista®（32位版本），但未安装 service pack 或 Windows Server®2003（32位版本）以及 GPMC。</span><span class="sxs-lookup"><span data-stu-id="aebdf-125">AGPM Server2.5 requires WindowsVista® (32-bit version) with no service packs installed or Windows Server®2003 (32-bit version), as well as the GPMC.</span></span> <span data-ttu-id="aebdf-126">此外，您必须是域管理员组的成员才能安装 AGPM 服务器。</span><span class="sxs-lookup"><span data-stu-id="aebdf-126">Additionally, you must be a member of the Domain Admins group to install AGPM Server.</span></span>

<span data-ttu-id="aebdf-127">你应该在成员服务器或域控制器上安装 AGPM 服务器，该服务器可供你使用且受 AGPM 支持的最新 GPMC 版本。</span><span class="sxs-lookup"><span data-stu-id="aebdf-127">You should install AGPM Server on a member server or domain controller with the most recent version of the GPMC that is available to you and supported by AGPM.</span></span> <span data-ttu-id="aebdf-128">AGPM 使用 GPMC 备份和还原 Gpo，较新版本的 GPMC 提供了在以前版本中不可用的其他策略设置。</span><span class="sxs-lookup"><span data-stu-id="aebdf-128">AGPM uses the GPMC to back up and restore GPOs, and newer versions of the GPMC provide additional policy settings not available in preceding versions.</span></span> <span data-ttu-id="aebdf-129">如果你的 AGPM 服务器上的 GPMC 版本比管理员用于管理组策略的计算机上的版本旧，则 AGPM 服务器将无法存储这些策略设置，这些设置在 GPMC 的较早版本中不可用。</span><span class="sxs-lookup"><span data-stu-id="aebdf-129">If the version of the GPMC on your AGPM Server is older than the version on the computers that administrators use to manage Group Policy, the AGPM Server will be unable to store those policy settings not available in the older version of the GPMC.</span></span>

<span data-ttu-id="aebdf-130">尤其是，如果你的 AGPM 服务器运行的是 Windows Server2003 以及该 GPMC 附带的 GPMC 版本，并且你的组策略管理员计算机运行的是 WindowsVista 和它附带的 GPMC 版本，你仍然可以管理大多数策略设置。</span><span class="sxs-lookup"><span data-stu-id="aebdf-130">Specifically, if your AGPM Server is running Windows Server2003 and the version of the GPMC that accompanied it, and your Group Policy administrators’ computers are running WindowsVista and the version of the GPMC that accompanied it, you can still manage most policy settings.</span></span> <span data-ttu-id="aebdf-131">但是，对于 windows Server 2003 中的 GPMC （如与文件夹重定向、无线网络（IEEE 802.11）和已部署的打印机相关的策略设置），无法通过 AGPM 服务器存储这些策略设置，即使管理员可以在其计算机上使用 AGPM 配置它们。</span><span class="sxs-lookup"><span data-stu-id="aebdf-131">However, policy settings from the GPMC in Windows Vista that are not available in the GPMC in Windows Server 2003—such as those related to folder redirection, wireless networking (IEEE 802.11), and deployed printers—cannot be stored by the AGPM Server, even though administrators can configure them using AGPM on their computers.</span></span>

<span data-ttu-id="aebdf-132">如果必须在使用 GPMC 的旧版本的计算机上安装 AGPM 服务器，而不是组策略管理员正在运行，请参阅组策略设置参考，了解有关哪些操作系统可使用哪些策略设置的详细信息。</span><span class="sxs-lookup"><span data-stu-id="aebdf-132">If you must install AGPM Server on a computer with an older version of GPMC than your Group Policy administrators are running, see the Group Policy Settings Reference for details about which policy settings are available with which operating systems.</span></span> <span data-ttu-id="aebdf-133">若要下载组策略设置参考，请参阅 <https://go.microsoft.com/fwlink/?LinkID=106147> 。</span><span class="sxs-lookup"><span data-stu-id="aebdf-133">To download the Group Policy Settings Reference, see <https://go.microsoft.com/fwlink/?LinkID=106147>.</span></span>

<span data-ttu-id="aebdf-134">**注意** 存档无法从 AGPM 服务器或运行 Windows Server2003 的 GPOVault 服务器迁移到运行 WindowsVista 的 AGPM 服务器。</span><span class="sxs-lookup"><span data-stu-id="aebdf-134">**Note** Archives cannot be migrated from an AGPM Server or a GPOVault Server running Windows Server2003 to an AGPM Server running WindowsVista.</span></span>

<span data-ttu-id="aebdf-135">对于 Windows Server2003，如果要在其上安装 AGPM Server 的计算机上安装了 GPOVault 服务器，建议在开始安装之前不要卸载 GPOVault 服务器。</span><span class="sxs-lookup"><span data-stu-id="aebdf-135">For Windows Server2003, if GPOVault Server is installed on the computer on which you want to install AGPM Server, it is recommended that you do not uninstall GPOVault Server before beginning the installation.</span></span> <span data-ttu-id="aebdf-136">安装 AGPM 服务器将卸载 GPOVault Server 并自动将现有 GPOVault 存档数据传输到 AGPM 存档。</span><span class="sxs-lookup"><span data-stu-id="aebdf-136">The installation of AGPM Server will uninstall GPOVault Server and automatically transfer your existing GPOVault archive data to an AGPM archive.</span></span>

 

### <span data-ttu-id="aebdf-137">AGPM 客户端要求</span><span class="sxs-lookup"><span data-stu-id="aebdf-137">AGPM Client requirements</span></span>

<span data-ttu-id="aebdf-138">AGPM 客户端2.5 需要 WindowsVista （32位版本），并且未安装 service pack 或 Windows Server2003 （32位版本）以及 GPMC。</span><span class="sxs-lookup"><span data-stu-id="aebdf-138">AGPM Client2.5 requires WindowsVista (32-bit version) with no service packs installed or Windows Server2003 (32-bit version), as well as the GPMC.</span></span> <span data-ttu-id="aebdf-139">可以在运行 AGPM 服务器的计算机上安装 AGPM 客户端。</span><span class="sxs-lookup"><span data-stu-id="aebdf-139">AGPM Client can be installed on a computer running AGPM Server.</span></span>

### <span data-ttu-id="aebdf-140">方案要求</span><span class="sxs-lookup"><span data-stu-id="aebdf-140">Scenario requirements</span></span>

<span data-ttu-id="aebdf-141">在开始此方案之前，请创建四个用户帐户。</span><span class="sxs-lookup"><span data-stu-id="aebdf-141">Before you begin this scenario, create four user accounts.</span></span> <span data-ttu-id="aebdf-142">在此方案中，你将为以下每个帐户分配以下 AGPM 角色之一： AGPM 管理员（完全控制）、审批者、编辑者和审阅者。</span><span class="sxs-lookup"><span data-stu-id="aebdf-142">During the scenario, you will assign one of the following AGPM roles to each of these accounts: AGPM Administrator (Full Control), Approver, Editor, and Reviewer.</span></span> <span data-ttu-id="aebdf-143">这些帐户必须能够发送和接收电子邮件。</span><span class="sxs-lookup"><span data-stu-id="aebdf-143">These accounts must be able to send and receive e-mail messages.</span></span> <span data-ttu-id="aebdf-144">为具有 AGPM 管理员、审批者和（可选）编辑器角色的帐户分配**链接 gpo**权限。</span><span class="sxs-lookup"><span data-stu-id="aebdf-144">Assign **Link GPOs** permission to the accounts with the AGPM Administrator, Approver, and (optionally) Editor roles.</span></span>

<span data-ttu-id="aebdf-145">**注意** 
默认情况下， **Link gpo**权限分配给域管理员和企业管理员的成员。</span><span class="sxs-lookup"><span data-stu-id="aebdf-145">**Note**
**Link GPOs** permission is assigned to members of Domain Administrators and Enterprise Administrators by default.</span></span> <span data-ttu-id="aebdf-146">若要将**链接 gpo**权限分配给其他用户或组（如具有 AGPM 管理员或审批者角色的帐户），请单击域的节点，然后单击 "**委派**" 选项卡，选择 "**链接 Gpo**"，单击 "**添加**"，然后选择要向其分配权限的用户或组。</span><span class="sxs-lookup"><span data-stu-id="aebdf-146">To assign **Link GPOs** permission to additional users or groups (such as accounts with the roles of AGPM Administrator or Approver), click the node for the domain and then click the **Delegation** tab, select **Link GPOs**, click **Add**, and select users or groups to which to assign the permission.</span></span>

 

<span data-ttu-id="aebdf-147">在这种情况下，您可以用不同的帐户执行操作。</span><span class="sxs-lookup"><span data-stu-id="aebdf-147">For this scenario, you perform actions with different accounts.</span></span> <span data-ttu-id="aebdf-148">你可以按所示方式使用每个帐户登录，或者可以使用 "**运行身份**" 命令，使用指定的帐户启动 GPMC。</span><span class="sxs-lookup"><span data-stu-id="aebdf-148">You can either log on with each account as indicated, or you can use the **Run as** command to start the GPMC with the indicated account.</span></span>

<span data-ttu-id="aebdf-149">**注意** 若要在 Windows Server2003 上将 "**运行方式**" 命令与 GPMC 一起使用，请单击 "**开始**"，指向 "**管理工具**"，右键单击 "**组策略管理**"，然后单击 "**运行方式**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-149">**Note** To use the **Run as** command with GPMC on Windows Server2003, click **Start**, point to **Administrative Tools**, right-click **Group Policy Management**, and click **Run as**.</span></span> <span data-ttu-id="aebdf-150">单击**以下用户**并输入帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="aebdf-150">Click **The following user** and enter credentials for an account.</span></span>

<span data-ttu-id="aebdf-151">若要在 Windows Vista 上将 "**运行方式**" 命令与 GPMC 配合使用，请单击 "**开始**" 按钮，指向 "**运行**"，然后键入**runas/user：** <em> DomainName\\UserName </em> **"mmc%windir%\\system32\\gpmc.msc"**，然后单击 **"确定**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-151">To use the **Run as** command with GPMC on Windows Vista, click the **Start** button, point to **Run**, and type **runas /user:**<em>DomainName\\UserName</em>**"mmc %windir%\\system32\\gpmc.msc"**, and click **OK**.</span></span> <span data-ttu-id="aebdf-152">出现提示时，键入帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="aebdf-152">Type the password for the account when prompted.</span></span>

 

## <span data-ttu-id="aebdf-153">安装和配置 AGPM 的步骤</span><span class="sxs-lookup"><span data-stu-id="aebdf-153">Steps for installing and configuring AGPM</span></span>


<span data-ttu-id="aebdf-154">必须完成以下步骤才能安装和配置 AGPM。</span><span class="sxs-lookup"><span data-stu-id="aebdf-154">You must complete the following steps to install and configure AGPM.</span></span>

[<span data-ttu-id="aebdf-155">步骤1：安装 AGPM 服务器</span><span class="sxs-lookup"><span data-stu-id="aebdf-155">Step 1: Install AGPM Server</span></span>](#bkmk-config1)

[<span data-ttu-id="aebdf-156">步骤2：安装 AGPM 客户端</span><span class="sxs-lookup"><span data-stu-id="aebdf-156">Step 2: Install AGPM Client</span></span>](#bkmk-config2)

[<span data-ttu-id="aebdf-157">步骤3：配置 AGPM 服务器连接</span><span class="sxs-lookup"><span data-stu-id="aebdf-157">Step 3: Configure an AGPM Server connection</span></span>](#bkmk-config3)

[<span data-ttu-id="aebdf-158">步骤4：配置电子邮件通知</span><span class="sxs-lookup"><span data-stu-id="aebdf-158">Step 4: Configure e-mail notification</span></span>](#bkmk-config4)

[<span data-ttu-id="aebdf-159">步骤5：代理访问</span><span class="sxs-lookup"><span data-stu-id="aebdf-159">Step 5: Delegate access</span></span>](#bkmk-config5)

### <a href="" id="bkmk-config1"></a><span data-ttu-id="aebdf-160">步骤1：安装 AGPM 服务器</span><span class="sxs-lookup"><span data-stu-id="aebdf-160">Step 1: Install AGPM Server</span></span>

<span data-ttu-id="aebdf-161">在此步骤中，将在将运行 AGPM 服务的成员服务器或域控制器上安装 AGPM 服务器，然后配置存档。</span><span class="sxs-lookup"><span data-stu-id="aebdf-161">In this step, you install AGPM Server on the member server or domain controller that will run the AGPM Service, and you configure the archive.</span></span> <span data-ttu-id="aebdf-162">所有 AGPM 操作都通过此 Windows 服务进行管理，并使用服务凭据执行。</span><span class="sxs-lookup"><span data-stu-id="aebdf-162">All AGPM operations are managed through this Windows service and are executed with the service's credentials.</span></span> <span data-ttu-id="aebdf-163">AGPM 服务器托管的存档可以托管在该服务器上，也可以在同一林中的另一台服务器上托管。</span><span class="sxs-lookup"><span data-stu-id="aebdf-163">The archive managed by an AGPM Server can be hosted on that server or on another server in the same forest.</span></span>

**<span data-ttu-id="aebdf-164">在将托管 AGPM 服务的计算机上安装 AGPM 服务器</span><span class="sxs-lookup"><span data-stu-id="aebdf-164">To install AGPM Server on the computer that will host the AGPM Service</span></span>**

1.  <span data-ttu-id="aebdf-165">使用域管理员组的成员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="aebdf-165">Log on with an account that is a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="aebdf-166">启动 Microsoft 桌面优化包 CD，然后按照屏幕上的说明选择 "**高级组策略管理-服务器**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-166">Start the Microsoft Desktop Optimization Pack CD and follow the instructions on screen to select **Advanced Group Policy Management - Server**.</span></span>

3.  <span data-ttu-id="aebdf-167">在 "**欢迎**" 对话框中，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-167">In the **Welcome** dialog box, click **Next**.</span></span>

4.  <span data-ttu-id="aebdf-168">在 " **Microsoft 软件许可条款**" 对话框中，接受条款，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-168">In the **Microsoft Software License Terms** dialog box, accept the terms and click **Next**.</span></span>

5.  <span data-ttu-id="aebdf-169">在 "**应用程序路径**" 对话框中，选择要在其中安装 AGPM 服务器的位置。</span><span class="sxs-lookup"><span data-stu-id="aebdf-169">In the **Application Path** dialog box, select a location in which to install AGPM Server.</span></span> <span data-ttu-id="aebdf-170">安装了 AGPM 服务器的计算机将托管 AGPM 服务并管理存档。</span><span class="sxs-lookup"><span data-stu-id="aebdf-170">The computer on which AGPM Server is installed will host the AGPM Service and manage the archive.</span></span> <span data-ttu-id="aebdf-171">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aebdf-171">Click **Next**.</span></span>

6.  <span data-ttu-id="aebdf-172">在 "**存档路径**" 对话框中，选择用于相对于 AGPM 服务器的存档位置。</span><span class="sxs-lookup"><span data-stu-id="aebdf-172">In the **Archive Path** dialog box, select a location for the archive relative to the AGPM Server.</span></span> <span data-ttu-id="aebdf-173">存档路径可以指向 AGPM 服务器或其他位置上的文件夹，但你应该选择一个具有足够空间的位置来存储由此 AGPM 服务器管理的所有 Gpo 和历史记录数据。</span><span class="sxs-lookup"><span data-stu-id="aebdf-173">The archive path can point to a folder on the AGPM Server or elsewhere, but you should select a location with sufficient space to store all GPOs and history data managed by this AGPM Server.</span></span> <span data-ttu-id="aebdf-174">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aebdf-174">Click **Next**.</span></span>

7.  <span data-ttu-id="aebdf-175">在 " **Agpm 服务帐户**" 对话框中，选择要在其下运行 AGPM 服务的服务帐户，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-175">In the **AGPM Service Account** dialog box, select a service account under which the AGPM Service will run and then click **Next**.</span></span>

8.  <span data-ttu-id="aebdf-176">在 "**存档所有者**" 对话框中，选择要向其初始分配 AGPM 管理员（完全控制）角色的帐户或组。</span><span class="sxs-lookup"><span data-stu-id="aebdf-176">In the **Archive Owner** dialog box, select an account or group to which to initially assign the AGPM Administrator (Full Control) role.</span></span> <span data-ttu-id="aebdf-177">此 AGPM 管理员可以为其他组策略管理员分配 AGPM 角色和权限（包括 AGPM 管理员的角色）。</span><span class="sxs-lookup"><span data-stu-id="aebdf-177">This AGPM Administrator can assign AGPM roles and permissions to other Group Policy administrators (including the role of AGPM Administrator).</span></span> <span data-ttu-id="aebdf-178">对于此方案，选择要在 AGPM 管理员角色中提供的帐户。</span><span class="sxs-lookup"><span data-stu-id="aebdf-178">For this scenario, select the account to serve in the AGPM Administrator role.</span></span> <span data-ttu-id="aebdf-179">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aebdf-179">Click **Next**.</span></span>

9.  <span data-ttu-id="aebdf-180">单击 "**安装**"，然后单击 "**完成**" 退出设置向导。</span><span class="sxs-lookup"><span data-stu-id="aebdf-180">Click **Install**, and then click **Finish** to exit the Setup Wizard.</span></span>

    <span data-ttu-id="aebdf-181">**小心** 不要通过操作系统中的 "**管理工具**和**服务**" 修改 AGPM 服务的设置。</span><span class="sxs-lookup"><span data-stu-id="aebdf-181">**Caution** Do not modify settings for the AGPM Service through **Administrative Tools** and **Services** in the operating system.</span></span> <span data-ttu-id="aebdf-182">这样做可能会阻止 AGPM 服务启动。</span><span class="sxs-lookup"><span data-stu-id="aebdf-182">Doing so can prevent the AGPM Service from starting.</span></span> <span data-ttu-id="aebdf-183">有关如何修改服务设置的信息，请参阅高级组策略管理的帮助。</span><span class="sxs-lookup"><span data-stu-id="aebdf-183">For information on how to modify settings for the service, see Help for Advanced Group Policy Management.</span></span>

     

### <a href="" id="bkmk-config2"></a><span data-ttu-id="aebdf-184">步骤2：安装 AGPM 客户端</span><span class="sxs-lookup"><span data-stu-id="aebdf-184">Step 2: Install AGPM Client</span></span>

<span data-ttu-id="aebdf-185">每个组策略管理员（创建、编辑、部署、查看或删除 Gpo 的任何人）都必须在它们用于管理 Gpo 的计算机上安装 AGPM 客户端。</span><span class="sxs-lookup"><span data-stu-id="aebdf-185">Each Group Policy administrator—anyone who creates, edits, deploys, reviews, or deletes GPOs—must have AGPM Client installed on computers that they use to manage GPOs.</span></span> <span data-ttu-id="aebdf-186">对于此方案，请在至少一台计算机上安装 AGPM 客户端。</span><span class="sxs-lookup"><span data-stu-id="aebdf-186">For this scenario, you install AGPM Client on at least one computer.</span></span> <span data-ttu-id="aebdf-187">无需在不执行组策略管理的最终用户的计算机上安装 AGPM 客户端。</span><span class="sxs-lookup"><span data-stu-id="aebdf-187">You do not need to install AGPM Client on the computers of end users who do not perform Group Policy administration.</span></span>

**<span data-ttu-id="aebdf-188">在组策略管理员的计算机上安装 AGPM 客户端</span><span class="sxs-lookup"><span data-stu-id="aebdf-188">To install AGPM Client on the computer of a Group Policy administrator</span></span>**

1.  <span data-ttu-id="aebdf-189">启动 Microsoft 桌面优化包 CD，然后按照屏幕上的说明选择 "**高级组策略管理-客户端**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-189">Start the Microsoft Desktop Optimization Pack CD and follow the instructions on screen to select **Advanced Group Policy Management - Client**.</span></span>

2.  <span data-ttu-id="aebdf-190">在 "**欢迎**" 对话框中，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-190">In the **Welcome** dialog box, click **Next**.</span></span>

3.  <span data-ttu-id="aebdf-191">在 " **Microsoft 软件许可条款**" 对话框中，接受条款，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-191">In the **Microsoft Software License Terms** dialog box, accept the terms and click **Next**.</span></span>

4.  <span data-ttu-id="aebdf-192">在 "**应用程序路径**" 对话框中，选择要在其中安装 AGPM 客户端的位置。</span><span class="sxs-lookup"><span data-stu-id="aebdf-192">In the **Application Path** dialog box, select a location in which to install AGPM Client.</span></span> <span data-ttu-id="aebdf-193">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aebdf-193">Click **Next**.</span></span>

5.  <span data-ttu-id="aebdf-194">在 " **AGPM 服务器**" 对话框中，键入要连接到的 AGPM 服务器的完全限定的计算机名和端口。</span><span class="sxs-lookup"><span data-stu-id="aebdf-194">In the **AGPM Server** dialog box, type the fully-qualified computer name and the port for the AGPM Server to which to connect.</span></span> <span data-ttu-id="aebdf-195">AGPM 服务的默认端口为4600。</span><span class="sxs-lookup"><span data-stu-id="aebdf-195">The default port for the AGPM Service is 4600.</span></span> <span data-ttu-id="aebdf-196">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aebdf-196">Click **Next**.</span></span>

6.  <span data-ttu-id="aebdf-197">单击 "**安装**"，然后单击 "**完成**" 退出设置向导。</span><span class="sxs-lookup"><span data-stu-id="aebdf-197">Click **Install**, and then click **Finish** to exit the Setup Wizard.</span></span>

### <a href="" id="bkmk-config3"></a><span data-ttu-id="aebdf-198">步骤3：配置 AGPM 服务器连接</span><span class="sxs-lookup"><span data-stu-id="aebdf-198">Step 3: Configure an AGPM Server connection</span></span>

<span data-ttu-id="aebdf-199">AGPM 存储每个受控制的组策略对象（GPO）的所有版本— AGPM 提供更改控制的 GPO，因此组策略管理员可以脱机查看和修改 Gpo，而无需立即影响每个 GPO 的已部署版本。</span><span class="sxs-lookup"><span data-stu-id="aebdf-199">AGPM stores all versions of each controlled Group Policy object (GPO)—a GPO for which AGPM provides change control—in a central archive, so Group Policy administrators can view and modify GPOs offline without immediately impacting the deployed version of each GPO.</span></span>

<span data-ttu-id="aebdf-200">在此步骤中，配置 AGPM 服务器连接并确保所有组策略管理员都连接到同一 AGPM 服务器。</span><span class="sxs-lookup"><span data-stu-id="aebdf-200">In this step, you configure an AGPM Server connection and ensure that all Group Policy administrators connect to the same AGPM Server.</span></span> <span data-ttu-id="aebdf-201">（有关配置多个 AGPM 服务器的信息，请参阅高级组策略管理的帮助。）</span><span class="sxs-lookup"><span data-stu-id="aebdf-201">(For information about configuring multiple AGPM Servers, see Help for Advanced Group Policy Management.)</span></span>

**<span data-ttu-id="aebdf-202">为所有组策略管理员配置 AGPM 服务器连接</span><span class="sxs-lookup"><span data-stu-id="aebdf-202">To configure an AGPM Server connection for all Group Policy administrators</span></span>**

1.  <span data-ttu-id="aebdf-203">在已安装了 AGPM 客户端的计算机上，使用你选择作为存档所有者的用户帐户登录。</span><span class="sxs-lookup"><span data-stu-id="aebdf-203">On a computer on which you have installed AGPM Client, log on with the user account that you selected as the Archive Owner.</span></span> <span data-ttu-id="aebdf-204">此用户具有 AGPM 管理员的角色（"完全控制"）。</span><span class="sxs-lookup"><span data-stu-id="aebdf-204">This user has the role of AGPM Administrator (Full Control).</span></span>

2.  <span data-ttu-id="aebdf-205">单击 "**开始**"，指向 "**管理工具**"，然后单击 "**组策略管理**" 以打开**组策略管理控制台（GPMC）**。</span><span class="sxs-lookup"><span data-stu-id="aebdf-205">Click **Start**, point to **Administrative Tools**, and click **Group Policy Management** to open the **Group Policy Management Console (GPMC)**.</span></span>

3.  <span data-ttu-id="aebdf-206">在**组策略管理控制台**树中，编辑应用到所有组策略管理员的 GPO。</span><span class="sxs-lookup"><span data-stu-id="aebdf-206">In the **Group Policy Management Console** tree, edit a GPO that is applied to all Group Policy administrators.</span></span>

4.  <span data-ttu-id="aebdf-207">在 "**组策略对象编辑器**" 窗口中，单击 "**用户配置**"、"**管理模板**" 和 " **Windows 组件**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-207">In the **Group Policy Object Editor** window, click **User Configuration**, **Administrative Templates**, and **Windows Components**.</span></span>

5.  <span data-ttu-id="aebdf-208">如果 " **Windows 组件**" 下列出的是**AGPM**未列出：</span><span class="sxs-lookup"><span data-stu-id="aebdf-208">If **AGPM** is not listed under **Windows Components**:</span></span>

    1.  <span data-ttu-id="aebdf-209">右键单击 "**管理模板**"，然后选择 "**添加/删除模板**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-209">Right-click **Administrative Templates** and select **Add/Remove Templates**.</span></span>

    2.  <span data-ttu-id="aebdf-210">单击 "**添加**"，选择 " **agpm** " 或 " **agpm .Adm**"，单击 "**打开**"，然后单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-210">Click **Add**, select **agpm.admx** or **agpm.adm**, click **Open**, and then click **Close**.</span></span>

6.  <span data-ttu-id="aebdf-211">在 " **Windows 组件**" 下，双击 " **AGPM**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-211">Under **Windows Components**, double-click **AGPM**.</span></span>

7.  <span data-ttu-id="aebdf-212">在 "详细信息" 窗格中，双击 " **AGPM 服务器（所有域）**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-212">In the details pane, double-click **AGPM Server (all domains)**.</span></span>

8.  <span data-ttu-id="aebdf-213">在 " **AGPM 服务器（所有域）属性**" 窗口中，选择 "**已启用**"，然后为托管存档的服务器键入完全限定的计算机名称和端口（例如，server.contoso.com:4600）。</span><span class="sxs-lookup"><span data-stu-id="aebdf-213">In the **AGPM Server (all domains) Properties** window, select **Enabled** and type the fully-qualified computer name and port (for example, server.contoso.com:4600) for the server hosting the archive.</span></span> <span data-ttu-id="aebdf-214">AGPM 服务使用的端口是端口4600。</span><span class="sxs-lookup"><span data-stu-id="aebdf-214">The port used by the AGPM Service is port 4600.</span></span>

9.  <span data-ttu-id="aebdf-215">单击 **"确定**"，然后关闭 "**组策略对象编辑器**" 窗口。</span><span class="sxs-lookup"><span data-stu-id="aebdf-215">Click **OK**, and then close the **Group Policy Object Editor** window.</span></span> <span data-ttu-id="aebdf-216">更新组策略时，将为每个组策略管理员配置 AGPM 服务器连接。</span><span class="sxs-lookup"><span data-stu-id="aebdf-216">When Group Policy is updated, the AGPM Server connection is configured for each Group Policy administrator.</span></span>

### <a href="" id="bkmk-config4"></a><span data-ttu-id="aebdf-217">步骤4：配置电子邮件通知</span><span class="sxs-lookup"><span data-stu-id="aebdf-217">Step 4: Configure e-mail notification</span></span>

<span data-ttu-id="aebdf-218">作为 AGPM 管理员（完全控制），你可以指定在编辑者尝试创建、部署或删除 GPO 时向其发送包含请求的电子邮件的审批者和 AGPM 管理员的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="aebdf-218">As an AGPM Administrator (Full Control), you designate the e-mail addresses of Approvers and AGPM Administrators to whom an e-mail message containing a request is sent when an Editor attempts to create, deploy, or delete a GPO.</span></span> <span data-ttu-id="aebdf-219">您还可以确定发送这些邮件的别名。</span><span class="sxs-lookup"><span data-stu-id="aebdf-219">You also determine the alias from which these messages are sent.</span></span>

**<span data-ttu-id="aebdf-220">配置 AGPM 的电子邮件通知</span><span class="sxs-lookup"><span data-stu-id="aebdf-220">To configure e-mail notification for AGPM</span></span>**

1.  <span data-ttu-id="aebdf-221">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-221">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="aebdf-222">在 "详细信息" 窗格中，单击 "**域委派**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="aebdf-222">In the details pane, click the **Domain Delegation** tab.</span></span>

3.  <span data-ttu-id="aebdf-223">在 "**发件**时间" 字段中，键入要从中发送通知的 AGPM 的电子邮件别名。</span><span class="sxs-lookup"><span data-stu-id="aebdf-223">In the **From** field, type the e-mail alias for AGPM from which notifications should be sent.</span></span>

4.  <span data-ttu-id="aebdf-224">在 "**收件人**" 字段中，键入要向其分配审批者角色的用户帐户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="aebdf-224">In the **To** field, type the e-mail address for the user account to which you intend to assign the Approver role.</span></span>

5.  <span data-ttu-id="aebdf-225">在 " **SMTP 服务器**" 字段中，键入有效的 SMTP 邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="aebdf-225">In the **SMTP server** field, type a valid SMTP mail server.</span></span>

6.  <span data-ttu-id="aebdf-226">在 "**用户名**" 和 "**密码**" 字段中，键入有权访问 SMTP 服务的用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="aebdf-226">In the **User name** and **Password** fields, type the credentials of a user with access to the SMTP service.</span></span>

7.  <span data-ttu-id="aebdf-227">单击**应用**。</span><span class="sxs-lookup"><span data-stu-id="aebdf-227">Click **Apply**.</span></span>

### <a href="" id="bkmk-config5"></a><span data-ttu-id="aebdf-228">步骤5：代理访问</span><span class="sxs-lookup"><span data-stu-id="aebdf-228">Step 5: Delegate access</span></span>

<span data-ttu-id="aebdf-229">作为 AGPM 管理员（完全控制），你可以委派域级别对 Gpo 的访问权限，并为每个组策略管理员的帐户分配角色。</span><span class="sxs-lookup"><span data-stu-id="aebdf-229">As an AGPM Administrator (Full Control), you delegate domain-level access to GPOs, assigning roles to the account of each Group Policy administrator.</span></span>

<span data-ttu-id="aebdf-230">**注意** 你还可以在 GPO 级别（而不是域级别）委派访问权限。</span><span class="sxs-lookup"><span data-stu-id="aebdf-230">**Note** You can also delegate access at the GPO level rather than the domain level.</span></span> <span data-ttu-id="aebdf-231">有关详细信息，请参阅高级组策略管理的帮助。</span><span class="sxs-lookup"><span data-stu-id="aebdf-231">For details, see Help for Advanced Group Policy Management.</span></span>

 

<span data-ttu-id="aebdf-232">**重要提示** 你应该限制 "组策略创建者所有者" 组中的成员身份，因此不能将其用于绕过对 Gpo 的访问的 AGPM 管理。</span><span class="sxs-lookup"><span data-stu-id="aebdf-232">**Important** You should restrict membership in the Group Policy Creator Owners group, so it cannot be used to circumvent AGPM management of access to GPOs.</span></span> <span data-ttu-id="aebdf-233">（在**组策略管理控制台**中，单击要在其中管理 gpo 的林和域中的 "**组策略对象**"，单击 "**委派**"，然后配置设置以满足组织的需要。）</span><span class="sxs-lookup"><span data-stu-id="aebdf-233">(In the **Group Policy Management Console**, click **Group Policy Objects** in the forest and domain in which you want to manage GPOs, click **Delegation**, and then configure the settings to meet the needs of your organization.)</span></span>

 

**<span data-ttu-id="aebdf-234">委派对整个域中的所有 Gpo 的访问权限</span><span class="sxs-lookup"><span data-stu-id="aebdf-234">To delegate access to all GPOs throughout a domain</span></span>**

1.  <span data-ttu-id="aebdf-235">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-235">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="aebdf-236">在 "**域委派**" 选项卡上，单击 "**高级**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="aebdf-236">On the **Domain Delegation** tab, click the **Advanced** button.</span></span>

3.  <span data-ttu-id="aebdf-237">在 "**权限**" 对话框中：</span><span class="sxs-lookup"><span data-stu-id="aebdf-237">In the **Permissions** dialog box:</span></span>

    1.  <span data-ttu-id="aebdf-238">单击组策略管理员的用户帐户，然后选中 "**审批者**" 复选框以将该角色分配给帐户。</span><span class="sxs-lookup"><span data-stu-id="aebdf-238">Click the user account of a Group Policy administrator, and then select the **Approver** check box to assign that role to the account.</span></span> <span data-ttu-id="aebdf-239">清除 "**编辑器**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="aebdf-239">Clear the **Editor** check box.</span></span> <span data-ttu-id="aebdf-240">（此角色包括审阅者角色。）</span><span class="sxs-lookup"><span data-stu-id="aebdf-240">(This role includes the Reviewer role.)</span></span>

    2.  <span data-ttu-id="aebdf-241">单击另一个组策略管理员的用户帐户，然后选择 "**编辑**" 复选框以将该角色分配给帐户。</span><span class="sxs-lookup"><span data-stu-id="aebdf-241">Click the user account of another Group Policy administrator, and then select the **Editor** check box to assign that role to the account.</span></span> <span data-ttu-id="aebdf-242">（此角色包括审阅者角色。）</span><span class="sxs-lookup"><span data-stu-id="aebdf-242">(This role includes the Reviewer role.)</span></span>

    3.  <span data-ttu-id="aebdf-243">单击第三个帐户，然后选中 "**审阅者**" 复选框以仅将审阅者角色分配给该组策略管理员的帐户。</span><span class="sxs-lookup"><span data-stu-id="aebdf-243">Click a third account and then select the **Reviewer** check box to assign only the Reviewer role to the account of that Group Policy administrator.</span></span> <span data-ttu-id="aebdf-244">清除 "**编辑器**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="aebdf-244">Clear the **Editor** check box.</span></span>

    4.  <span data-ttu-id="aebdf-245">单击 "**高级**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="aebdf-245">Click the **Advanced** button.</span></span>

4.  <span data-ttu-id="aebdf-246">在 "**高级安全设置**" 对话框中：</span><span class="sxs-lookup"><span data-stu-id="aebdf-246">In the **Advanced Security Settings** dialog box:</span></span>

    1.  <span data-ttu-id="aebdf-247">选择组策略管理员，然后单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-247">Select a Group Policy administrator, and then click **Edit**.</span></span>

    2.  <span data-ttu-id="aebdf-248">对于 "**应用于**"，请选择 "**此对象和嵌套的对象**"，然后在 "**权限\*\*\*\*条目**" 对话框中单击 **"确定"** 。</span><span class="sxs-lookup"><span data-stu-id="aebdf-248">For **Apply onto**, select **This object and nested objects**, and then click **OK** in the **Permission** **Entry** dialog box.</span></span>

    3.  <span data-ttu-id="aebdf-249">对每个组策略管理员重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="aebdf-249">Repeat for each Group Policy administrator.</span></span>

5.  <span data-ttu-id="aebdf-250">在 "**高级安全设置**" 对话框中，单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="aebdf-250">In the **Advanced Security Settings** dialog box, click **OK**.</span></span>

6.  <span data-ttu-id="aebdf-251">在 "**权限**" 对话框中，单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="aebdf-251">In the **Permissions** dialog box, click **OK**.</span></span>

## <span data-ttu-id="aebdf-252">管理 Gpo 的步骤</span><span class="sxs-lookup"><span data-stu-id="aebdf-252">Steps for managing GPOs</span></span>


<span data-ttu-id="aebdf-253">必须完成以下步骤才能使用 AGPM 创建、编辑、查看和部署 Gpo。</span><span class="sxs-lookup"><span data-stu-id="aebdf-253">You must complete the following steps to create, edit, review, and deploy GPOs using AGPM.</span></span> <span data-ttu-id="aebdf-254">此外，你将创建一个模板，删除 GPO，然后还原已删除的 GPO。</span><span class="sxs-lookup"><span data-stu-id="aebdf-254">Additionally, you will create a template, delete a GPO, and restore a deleted GPO.</span></span>

[<span data-ttu-id="aebdf-255">步骤1：创建 GPO</span><span class="sxs-lookup"><span data-stu-id="aebdf-255">Step 1: Create a GPO</span></span>](#bkmk-manage1)

[<span data-ttu-id="aebdf-256">步骤2：编辑 GPO</span><span class="sxs-lookup"><span data-stu-id="aebdf-256">Step 2: Edit a GPO</span></span>](#bkmk-manage2)

[<span data-ttu-id="aebdf-257">步骤3：查看和部署 GPO</span><span class="sxs-lookup"><span data-stu-id="aebdf-257">Step 3: Review and deploy a GPO</span></span>](#bkmk-manage3)

[<span data-ttu-id="aebdf-258">步骤4：使用模板创建 GPO</span><span class="sxs-lookup"><span data-stu-id="aebdf-258">Step 4: Use a template to create a GPO</span></span>](#bkmk-manage4)

[<span data-ttu-id="aebdf-259">步骤5：删除和还原 GPO</span><span class="sxs-lookup"><span data-stu-id="aebdf-259">Step 5: Delete and restore a GPO</span></span>](#bkmk-manage5)

### <a href="" id="bkmk-manage1"></a><span data-ttu-id="aebdf-260">步骤1：创建 GPO</span><span class="sxs-lookup"><span data-stu-id="aebdf-260">Step 1: Create a GPO</span></span>

<span data-ttu-id="aebdf-261">在具有多个组策略管理员的环境中，具有编辑器角色的用户能够请求创建新的 Gpo，但此类请求必须由拥有审批者角色的人员批准，因为创建新 GPO 会影响生产环境。</span><span class="sxs-lookup"><span data-stu-id="aebdf-261">In an environment with multiple Group Policy administrators, those with the Editor role have the ability to request the creation of new GPOs, but such a request must be approved by someone with the Approver role because the creation of a new GPO impacts the production environment.</span></span>

<span data-ttu-id="aebdf-262">在此步骤中，您将使用具有编辑器角色的帐户请求创建新的 GPO。</span><span class="sxs-lookup"><span data-stu-id="aebdf-262">In this step, you use an account with the Editor role to request the creation of a new GPO.</span></span> <span data-ttu-id="aebdf-263">将帐户与审批者角色配合使用，即可批准此请求并完成 GPO 的创建。</span><span class="sxs-lookup"><span data-stu-id="aebdf-263">Using an account with the Approver role, you approve this request and complete the creation of a GPO.</span></span>

**<span data-ttu-id="aebdf-264">请求创建通过 AGPM 管理的新 GPO</span><span class="sxs-lookup"><span data-stu-id="aebdf-264">To request the creation of a new GPO managed through AGPM</span></span>**

1.  <span data-ttu-id="aebdf-265">在已安装了 AGPM 客户端的计算机上，使用已分配了 AGPM 中的编辑器角色的用户帐户登录。</span><span class="sxs-lookup"><span data-stu-id="aebdf-265">On a computer on which you have installed AGPM Client, log on with a user account that has been assigned the Editor role in AGPM.</span></span>

2.  <span data-ttu-id="aebdf-266">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-266">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

3.  <span data-ttu-id="aebdf-267">右键单击 "**更改控制**" 节点，然后单击 "**新建受控 GPO**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-267">Right-click the **Change Control** node, and then click **New Controlled GPO**.</span></span>

4.  <span data-ttu-id="aebdf-268">在 "**新建受控 GPO** " 对话框中：</span><span class="sxs-lookup"><span data-stu-id="aebdf-268">In the **New Controlled GPO** dialog box:</span></span>

    1.  <span data-ttu-id="aebdf-269">若要接收请求的副本，请在 "**抄送**" 字段中键入您的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="aebdf-269">To receive a copy of the request, type your e-mail address in the **Cc** field.</span></span>

    2.  <span data-ttu-id="aebdf-270">键入**MyGPO**作为新 GPO 的名称。</span><span class="sxs-lookup"><span data-stu-id="aebdf-270">Type **MyGPO** as the name for the new GPO.</span></span>

    3.  <span data-ttu-id="aebdf-271">键入新 GPO 的注释。</span><span class="sxs-lookup"><span data-stu-id="aebdf-271">Type a comment for the new GPO.</span></span>

    4.  <span data-ttu-id="aebdf-272">单击 "**创建实时**"，以便在批准后立即将新的 GPO 部署到生产环境。</span><span class="sxs-lookup"><span data-stu-id="aebdf-272">Click **Create live** so the new GPO will be deployed to the production environment immediately upon approval.</span></span>

    5.  <span data-ttu-id="aebdf-273">单击**提交**。</span><span class="sxs-lookup"><span data-stu-id="aebdf-273">Click **Submit**.</span></span>

5.  <span data-ttu-id="aebdf-274">当**AGPM 进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-274">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="aebdf-275">新的 GPO 将显示在 "**挂起**" 选项卡上。</span><span class="sxs-lookup"><span data-stu-id="aebdf-275">The new GPO is displayed on the **Pending** tab.</span></span>

**<span data-ttu-id="aebdf-276">批准创建 GPO 的挂起请求</span><span class="sxs-lookup"><span data-stu-id="aebdf-276">To approve the pending request to create a GPO</span></span>**

1.  <span data-ttu-id="aebdf-277">在已安装了 AGPM 客户端的计算机上，使用已分配了 AGPM 审批者角色的用户帐户登录。</span><span class="sxs-lookup"><span data-stu-id="aebdf-277">On a computer on which you have installed AGPM Client, log on with a user account that has been assigned the role of Approver in AGPM.</span></span>

2.  <span data-ttu-id="aebdf-278">打开该帐户的电子邮件收件箱，请注意，您已收到一个来自 AGPM 别名的电子邮件，其中包含用于创建 GPO 的编辑器请求。</span><span class="sxs-lookup"><span data-stu-id="aebdf-278">Open the e-mail inbox for the account, and note that you have received an e-mail message from the AGPM alias with the Editor's request to create a GPO.</span></span>

3.  <span data-ttu-id="aebdf-279">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-279">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

4.  <span data-ttu-id="aebdf-280">在 "**目录**" 选项卡上，单击 "**挂起**" 选项卡以显示 "挂起的 gpo"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-280">On the **Contents** tab, click the **Pending** tab to display the pending GPOs.</span></span>

5.  <span data-ttu-id="aebdf-281">右键单击 " **MyGPO**"，然后单击 "**批准**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-281">Right-click **MyGPO**, and then click **Approve**.</span></span>

6.  <span data-ttu-id="aebdf-282">单击 **"是"** 以确认创建 GPO 的批准。</span><span class="sxs-lookup"><span data-stu-id="aebdf-282">Click **Yes** to confirm approval of the creation of the GPO.</span></span> <span data-ttu-id="aebdf-283">GPO 被移动到 "**受控**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="aebdf-283">The GPO is moved to the **Controlled** tab.</span></span>

### <a href="" id="bkmk-manage2"></a><span data-ttu-id="aebdf-284">步骤2：编辑 GPO</span><span class="sxs-lookup"><span data-stu-id="aebdf-284">Step 2: Edit a GPO</span></span>

<span data-ttu-id="aebdf-285">你可以使用 Gpo 配置计算机或用户设置，并将其部署到多台计算机或用户。</span><span class="sxs-lookup"><span data-stu-id="aebdf-285">You can use GPOs to configure computer or user settings and deploy them to many computers or users.</span></span> <span data-ttu-id="aebdf-286">在此步骤中，使用具有编辑器角色的帐户从存档中签出 GPO，脱机编辑 GPO，将编辑的 GPO 签入存档，并向生产环境请求 GPO 部署。</span><span class="sxs-lookup"><span data-stu-id="aebdf-286">In this step, you use an account with the Editor role to check out a GPO from the archive, edit the GPO offline, check the edited GPO into the archive, and request deployment of the GPO to the production environment.</span></span> <span data-ttu-id="aebdf-287">对于此方案，你可以在 GPO 中配置一个设置，要求密码长度至少为八个字符。</span><span class="sxs-lookup"><span data-stu-id="aebdf-287">For this scenario, you configure a setting in the GPO to require that the password be at least eight characters in length.</span></span>

**<span data-ttu-id="aebdf-288">从存档中签出 GPO 以进行编辑</span><span class="sxs-lookup"><span data-stu-id="aebdf-288">To check the GPO out from the archive for editing</span></span>**

1.  <span data-ttu-id="aebdf-289">在已安装了 AGPM 客户端的计算机上，使用已分配了 "编辑者在 AGPM 中的角色" 的用户帐户登录。</span><span class="sxs-lookup"><span data-stu-id="aebdf-289">On a computer on which you have installed AGPM Client, log on with a user account that has been assigned the role of Editor in AGPM.</span></span>

2.  <span data-ttu-id="aebdf-290">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-290">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

3.  <span data-ttu-id="aebdf-291">在 "详细信息" 窗格中的 "**目录**" 选项卡上，单击 "**受控**" 选项卡以显示受控 gpo。</span><span class="sxs-lookup"><span data-stu-id="aebdf-291">On the **Contents** tab in the details pane, click the **Controlled** tab to display the controlled GPOs.</span></span>

4.  <span data-ttu-id="aebdf-292">右键单击 " **MyGPO**"，然后单击 "**签出**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-292">Right-click **MyGPO**, and then click **Check Out**.</span></span>

5.  <span data-ttu-id="aebdf-293">键入要在已签出的 GPO 的**历史记录**中显示的注释，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="aebdf-293">Type a comment to be displayed in the **History** of the GPO while it is checked out, and then click **OK**.</span></span>

6.  <span data-ttu-id="aebdf-294">当**AGPM 进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-294">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="aebdf-295">在 "**受控**" 选项卡上，将 GPO 的状态标识为 "**已签出**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-295">On the **Controlled** tab, the state of the GPO is identified as **Checked Out**.</span></span>

**<span data-ttu-id="aebdf-296">脱机编辑 GPO 并配置最小密码长度</span><span class="sxs-lookup"><span data-stu-id="aebdf-296">To edit the GPO offline and configure the minimum password length</span></span>**

1.  <span data-ttu-id="aebdf-297">在 "**受控**" 选项卡上，右键单击 " **MyGPO**"，然后单击 "**编辑**" 以打开 "**组策略对象编辑器**" 窗口，并对 GPO 的脱机副本进行更改。</span><span class="sxs-lookup"><span data-stu-id="aebdf-297">On the **Controlled** tab, right-click **MyGPO**, and then click **Edit** to open the **Group Policy Object Editor** window and make changes to an offline copy of the GPO.</span></span> <span data-ttu-id="aebdf-298">对于此方案，请配置最小密码长度：</span><span class="sxs-lookup"><span data-stu-id="aebdf-298">For this scenario, configure the minimum password length:</span></span>

    1.  <span data-ttu-id="aebdf-299">在 "**计算机配置**" 下，双击 " **Windows 设置**"，双击 "**安全设置**"，双击 "**帐户策略**"，然后双击 "**密码策略**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-299">Under **Computer Configuration**, double-click **Windows Settings**, double-click **Security Settings**, double-click **Account Policies**, and double-click **Password Policy**.</span></span>

    2.  <span data-ttu-id="aebdf-300">在 "详细信息" 窗格中，双击 "**最小密码长度**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-300">In the details pane, double-click **Minimum password length**.</span></span>

    3.  <span data-ttu-id="aebdf-301">在 "属性" 窗口中，选中 "**定义此策略设置**" 复选框，将字符数设置为**8**，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="aebdf-301">In the properties window, select the **Define this policy setting** check box, set the number of characters to **8**, and then click **OK**.</span></span>

2.  <span data-ttu-id="aebdf-302">关闭 "**组策略对象编辑器**" 窗口。</span><span class="sxs-lookup"><span data-stu-id="aebdf-302">Close the **Group Policy Object Editor** window.</span></span>

**<span data-ttu-id="aebdf-303">将 GPO 签入存档</span><span class="sxs-lookup"><span data-stu-id="aebdf-303">To check the GPO into the archive</span></span>**

1.  <span data-ttu-id="aebdf-304">在 "**受控**" 选项卡上，右键单击 " **MyGPO** "，然后单击 "**签入**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-304">On the **Controlled** tab, right-click **MyGPO** and then click **Check In**.</span></span>

2.  <span data-ttu-id="aebdf-305">键入批注，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="aebdf-305">Type a comment, and then click **OK**.</span></span>

3.  <span data-ttu-id="aebdf-306">当**AGPM 进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-306">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="aebdf-307">在 "**受控**" 选项卡上，将 GPO 的状态标识为 **"已签入**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-307">On the **Controlled** tab, the state of the GPO is identified as **Checked In**.</span></span>

**<span data-ttu-id="aebdf-308">请求将 GPO 部署到生产环境</span><span class="sxs-lookup"><span data-stu-id="aebdf-308">To request the deployment of the GPO to the production environment</span></span>**

1.  <span data-ttu-id="aebdf-309">在 "**受控**" 选项卡上，右键单击 " **MyGPO** "，然后单击 "**部署**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-309">On the **Controlled** tab, right-click **MyGPO** and then click **Deploy**.</span></span>

2.  <span data-ttu-id="aebdf-310">由于此帐户不是审批者或 AGPM 管理员，因此必须提交部署请求。</span><span class="sxs-lookup"><span data-stu-id="aebdf-310">Because this account is not an Approver or AGPM Administrator, you must submit a request for deployment.</span></span> <span data-ttu-id="aebdf-311">若要接收请求的副本，请在 "**抄送**" 字段中键入您的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="aebdf-311">To receive a copy of the request, type your e-mail address in the **Cc** field.</span></span> <span data-ttu-id="aebdf-312">键入要在 GPO 的**历史记录**中显示的注释，然后单击 "**提交**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-312">Type a comment to be displayed in the **History** of the GPO, and then click **Submit**.</span></span>

3.  <span data-ttu-id="aebdf-313">当**AGPM 进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-313">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="aebdf-314">**MyGPO**将显示在 "**挂起**" 选项卡上的 gpo 列表中。</span><span class="sxs-lookup"><span data-stu-id="aebdf-314">**MyGPO** is displayed on the list of GPOs on the **Pending** tab.</span></span>

### <a href="" id="bkmk-manage3"></a><span data-ttu-id="aebdf-315">步骤3：查看和部署 GPO</span><span class="sxs-lookup"><span data-stu-id="aebdf-315">Step 3: Review and deploy a GPO</span></span>

<span data-ttu-id="aebdf-316">在此步骤中，你充当审批者，创建报表和分析 GPO 中的设置以及对设置的更改，以确定是否应批准这些设置。</span><span class="sxs-lookup"><span data-stu-id="aebdf-316">In this step, you act as an Approver, creating reports and analyzing the settings and changes to settings in the GPO to determine whether you should approve them.</span></span> <span data-ttu-id="aebdf-317">评估 GPO 后，将其部署到生产环境并将其链接到域或组织单位（OU），以便在为该域或 OU 中的计算机刷新组策略时，它将生效。</span><span class="sxs-lookup"><span data-stu-id="aebdf-317">After evaluating the GPO, you deploy it to the production environment and link it to a domain or an organizational unit (OU) so that it takes effect when Group Policy is refreshed for computers in that domain or OU.</span></span>

**<span data-ttu-id="aebdf-318">查看 GPO 中的设置</span><span class="sxs-lookup"><span data-stu-id="aebdf-318">To review settings in the GPO</span></span>**

1.  <span data-ttu-id="aebdf-319">在已安装了 AGPM 客户端的计算机上，使用已分配了 AGPM 审批者角色的用户帐户登录。</span><span class="sxs-lookup"><span data-stu-id="aebdf-319">On a computer on which you have installed AGPM Client, log on with a user account that has been assigned the role of Approver in AGPM.</span></span> <span data-ttu-id="aebdf-320">（包含在所有其他角色中的审阅者角色的任何组策略管理员可以查看 GPO 中的设置。）</span><span class="sxs-lookup"><span data-stu-id="aebdf-320">(Any Group Policy administrator with the Reviewer role, which is included in all of the other roles, can review the settings in a GPO.)</span></span>

2.  <span data-ttu-id="aebdf-321">打开该帐户的电子邮件收件箱，请注意，您已收到来自 AGPM 别名的电子邮件，其中包含用于部署 GPO 的编辑器请求。</span><span class="sxs-lookup"><span data-stu-id="aebdf-321">Open the e-mail inbox for the account and note that you have received an e-mail message from the AGPM alias with an Editor's request to deploy a GPO.</span></span>

3.  <span data-ttu-id="aebdf-322">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-322">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

4.  <span data-ttu-id="aebdf-323">在 "详细信息" 窗格中的 "**目录**" 选项卡上，单击 "**挂起**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="aebdf-323">On the **Contents** tab in the details pane, click the **Pending** tab.</span></span>

5.  <span data-ttu-id="aebdf-324">双击 " **MyGPO** " 以显示其历史记录。</span><span class="sxs-lookup"><span data-stu-id="aebdf-324">Double-click **MyGPO** to display its history.</span></span>

6.  <span data-ttu-id="aebdf-325">查看最新版本的 MyGPO 中的设置：</span><span class="sxs-lookup"><span data-stu-id="aebdf-325">Review the settings in the most recent version of MyGPO:</span></span>

    1.  <span data-ttu-id="aebdf-326">在 "**历史记录**" 窗口中，右键单击具有最新时间戳的 GPO 版本，单击 "**设置**"，然后单击 " **HTML 报表**" 以显示 GPO 设置的摘要。</span><span class="sxs-lookup"><span data-stu-id="aebdf-326">In the **History** window, right-click the GPO version with the most recent timestamp, click **Settings**, and then click **HTML Report** to display a summary of the GPO's settings.</span></span>

    2.  <span data-ttu-id="aebdf-327">在 Web 浏览器中，单击 "**全部显示**" 以显示 GPO 中的所有设置。</span><span class="sxs-lookup"><span data-stu-id="aebdf-327">In the Web browser, click **show all** to display all of the settings in the GPO.</span></span>

    3.  <span data-ttu-id="aebdf-328">关闭浏览器。</span><span class="sxs-lookup"><span data-stu-id="aebdf-328">Close the browser.</span></span>

7.  <span data-ttu-id="aebdf-329">将最新版本的 MyGPO 与签入到存档中的第一个版本进行比较：</span><span class="sxs-lookup"><span data-stu-id="aebdf-329">Compare the most recent version of MyGPO to the first version checked in to the archive:</span></span>

    1.  <span data-ttu-id="aebdf-330">在 "**历史记录**" 窗口中，单击具有最新时间戳的 GPO 版本。</span><span class="sxs-lookup"><span data-stu-id="aebdf-330">In the **History** window, click the GPO version with the most recent timestamp.</span></span> <span data-ttu-id="aebdf-331">按**CTRL**并单击处于**签入**状态的最早的 GPO 版本。</span><span class="sxs-lookup"><span data-stu-id="aebdf-331">Press **CTRL** and click the oldest GPO version that has a state of **Checked In**.</span></span>

    2.  <span data-ttu-id="aebdf-332">单击 "**差异**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="aebdf-332">Click the **Differences** button.</span></span> <span data-ttu-id="aebdf-333">"**帐户策略/密码策略**" 部分以绿色突出显示，前面是**\ [+ \]**，表示此设置仅在 GPO 的后一版本中配置。</span><span class="sxs-lookup"><span data-stu-id="aebdf-333">The **Account Policies/Password Policy** section is highlighted in green and preceded by **\[+\]**, indicating that this setting is configured only in the latter version of the GPO.</span></span>

    3.  <span data-ttu-id="aebdf-334">单击 "**帐户策略/密码策略**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-334">Click **Account Policies/Password Policy**.</span></span> <span data-ttu-id="aebdf-335">"**最小密码长度**" 设置也将以绿色突出显示，并以 " \**+ \**" 开头，以指示它仅在 GPO 的后版本中进行配置。</span><span class="sxs-lookup"><span data-stu-id="aebdf-335">The **Minimum password length** setting is also highlighted in green and preceded by **\[+\]**, indicating that it is configured only in the latter version of the GPO.</span></span>

    4.  <span data-ttu-id="aebdf-336">关闭 Web 浏览器。</span><span class="sxs-lookup"><span data-stu-id="aebdf-336">Close the Web browser.</span></span>

**<span data-ttu-id="aebdf-337">将 GPO 部署到生产环境</span><span class="sxs-lookup"><span data-stu-id="aebdf-337">To deploy the GPO to the production environment</span></span>**

1.  <span data-ttu-id="aebdf-338">在 "**挂起**" 选项卡上，右键单击 " **MyGPO** "，然后单击 "**批准**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-338">On the **Pending** tab, right-click **MyGPO** and then click **Approve**.</span></span>

2.  <span data-ttu-id="aebdf-339">键入要包含在 GPO 历史记录中的注释。</span><span class="sxs-lookup"><span data-stu-id="aebdf-339">Type a comment to include in the history of the GPO.</span></span>

3.  <span data-ttu-id="aebdf-340">单击**是**。</span><span class="sxs-lookup"><span data-stu-id="aebdf-340">Click **Yes**.</span></span> <span data-ttu-id="aebdf-341">当**AGPM 进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-341">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="aebdf-342">GPO 已部署到生产环境。</span><span class="sxs-lookup"><span data-stu-id="aebdf-342">The GPO is deployed to the production environment.</span></span>

**<span data-ttu-id="aebdf-343">将 GPO 链接到域或组织单位</span><span class="sxs-lookup"><span data-stu-id="aebdf-343">To link the GPO to a domain or organizational unit</span></span>**

1.  <span data-ttu-id="aebdf-344">在 GPMC 中，右键单击要对其应用你配置的 GPO 的域或 OU，然后单击 "**链接现有 gpo**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-344">In the GPMC, right-click the domain or an OU to which to apply the GPO that you configured, and then click **Link an Existing GPO**.</span></span>

2.  <span data-ttu-id="aebdf-345">在 "**选择 GPO** " 对话框中，单击 " **MyGPO**"，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="aebdf-345">In the **Select GPO** dialog box, click **MyGPO**, and then click **OK**.</span></span>

### <a href="" id="bkmk-manage4"></a><span data-ttu-id="aebdf-346">步骤4：使用模板创建 GPO</span><span class="sxs-lookup"><span data-stu-id="aebdf-346">Step 4: Use a template to create a GPO</span></span>

<span data-ttu-id="aebdf-347">在此步骤中，使用具有编辑器角色的帐户创建模板（不可编辑的静态版本，用作创建新 Gpo 的起始点），然后基于该模板创建新的 GPO。</span><span class="sxs-lookup"><span data-stu-id="aebdf-347">In this step, you use an account with the Editor role to create a template—an uneditable, static version of a GPO for use as a starting point for creating new GPOs—and then create a new GPO based upon that template.</span></span> <span data-ttu-id="aebdf-348">模板对于快速创建包含许多相同设置的多个 Gpo 非常有用。</span><span class="sxs-lookup"><span data-stu-id="aebdf-348">Templates are useful for quickly creating multiple GPOs that include many of the same settings.</span></span>

**<span data-ttu-id="aebdf-349">基于现有 GPO 创建模板</span><span class="sxs-lookup"><span data-stu-id="aebdf-349">To create a template based on an existing GPO</span></span>**

1.  <span data-ttu-id="aebdf-350">在已安装了 AGPM 客户端的计算机上，使用已分配了 "编辑者在 AGPM 中的角色" 的用户帐户登录。</span><span class="sxs-lookup"><span data-stu-id="aebdf-350">On a computer on which you have installed AGPM Client, log on with a user account that has been assigned the role of Editor in AGPM.</span></span>

2.  <span data-ttu-id="aebdf-351">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-351">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

3.  <span data-ttu-id="aebdf-352">在 "详细信息" 窗格中的 "**目录**" 选项卡上，单击 "**受控**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="aebdf-352">On the **Contents** tab in the details pane, click the **Controlled** tab.</span></span>

4.  <span data-ttu-id="aebdf-353">右键单击 " **MyGPO**"，然后单击 "**另存为模板**"，创建一个模板，其中包含当前在 MyGPO 中的所有设置。</span><span class="sxs-lookup"><span data-stu-id="aebdf-353">Right-click **MyGPO**, and then click **Save as Template** to create a template incorporating all settings currently in MyGPO.</span></span>

5.  <span data-ttu-id="aebdf-354">键入**MyTemplate**作为模板名称和注释，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="aebdf-354">Type **MyTemplate** as the name for the template and a comment, and then click **OK**.</span></span>

6.  <span data-ttu-id="aebdf-355">当**AGPM 进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-355">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="aebdf-356">新模板将显示在 "**模板**" 选项卡上。</span><span class="sxs-lookup"><span data-stu-id="aebdf-356">The new template appears on the **Templates** tab.</span></span>

**<span data-ttu-id="aebdf-357">请求创建通过 AGPM 管理的新 GPO</span><span class="sxs-lookup"><span data-stu-id="aebdf-357">To request the creation of a new GPO managed through AGPM</span></span>**

1.  <span data-ttu-id="aebdf-358">单击 "**受控**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="aebdf-358">Click the **Controlled** tab.</span></span>

2.  <span data-ttu-id="aebdf-359">右键单击 "**更改控制**" 节点，然后单击 "**新建受控 GPO**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-359">Right-click the **Change Control** node, and then click **New Controlled GPO**.</span></span>

3.  <span data-ttu-id="aebdf-360">在 "**新建受控 GPO** " 对话框中：</span><span class="sxs-lookup"><span data-stu-id="aebdf-360">In the **New Controlled GPO** dialog box:</span></span>

    1.  <span data-ttu-id="aebdf-361">若要接收请求的副本，请在 "**抄送**" 字段中键入您的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="aebdf-361">To receive a copy of the request, type your e-mail address in the **Cc** field.</span></span>

    2.  <span data-ttu-id="aebdf-362">键入**MyOtherGPO**作为新 GPO 的名称。</span><span class="sxs-lookup"><span data-stu-id="aebdf-362">Type **MyOtherGPO** as the name for the new GPO.</span></span>

    3.  <span data-ttu-id="aebdf-363">键入新 GPO 的注释。</span><span class="sxs-lookup"><span data-stu-id="aebdf-363">Type a comment for the new GPO.</span></span>

    4.  <span data-ttu-id="aebdf-364">单击 "**创建实时**"，这样新的 GPO 将在批准后立即部署到生产环境中。</span><span class="sxs-lookup"><span data-stu-id="aebdf-364">Click **Create live**, so the new GPO will be deployed to the production environment immediately upon approval.</span></span>

    5.  <span data-ttu-id="aebdf-365">**在 "来自 GPO 模板**" 中，选择 " **MyTemplate**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-365">For **From GPO template**, select **MyTemplate**.</span></span>

    6.  <span data-ttu-id="aebdf-366">单击**提交**。</span><span class="sxs-lookup"><span data-stu-id="aebdf-366">Click **Submit**.</span></span>

4.  <span data-ttu-id="aebdf-367">当**AGPM 进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-367">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="aebdf-368">新的 GPO 将显示在 "**挂起**" 选项卡上。</span><span class="sxs-lookup"><span data-stu-id="aebdf-368">The new GPO is displayed on the **Pending** tab.</span></span>

<span data-ttu-id="aebdf-369">使用已分配给审批者角色的帐户，以批准挂起的请求以创建 GPO （如步骤1中所[执行的操作）：创建 gpo](#bkmk-manage1)。</span><span class="sxs-lookup"><span data-stu-id="aebdf-369">Use an account that has been assigned the role of Approver to approve the pending request to create the GPO as you did in [Step 1: Create a GPO](#bkmk-manage1).</span></span> <span data-ttu-id="aebdf-370">MyTemplate 包含您在 MyGPO 中配置的所有设置。</span><span class="sxs-lookup"><span data-stu-id="aebdf-370">MyTemplate incorporates all of the settings that you configured in MyGPO.</span></span> <span data-ttu-id="aebdf-371">由于 MyOtherGPO 是使用 MyTemplate 创建的，因此它最初包含在创建 MyTemplate 时 MyGPO 包含的所有设置。</span><span class="sxs-lookup"><span data-stu-id="aebdf-371">Because MyOtherGPO was created using MyTemplate, it initially contains all of the settings that MyGPO contained at the time that MyTemplate was created.</span></span> <span data-ttu-id="aebdf-372">你可以通过生成差异报表来将 MyOtherGPO 与 MyTemplate 进行比较来确认。</span><span class="sxs-lookup"><span data-stu-id="aebdf-372">You can confirm this by generating a difference report to compare MyOtherGPO to MyTemplate.</span></span>

**<span data-ttu-id="aebdf-373">从存档中签出 GPO 以进行编辑</span><span class="sxs-lookup"><span data-stu-id="aebdf-373">To check the GPO out from the archive for editing</span></span>**

1.  <span data-ttu-id="aebdf-374">在已安装了 AGPM 客户端的计算机上，使用已分配了 "编辑者在 AGPM 中的角色" 的用户帐户登录。</span><span class="sxs-lookup"><span data-stu-id="aebdf-374">On a computer on which you have installed AGPM Client, log on with a user account that has been assigned the role of Editor in AGPM.</span></span>

2.  <span data-ttu-id="aebdf-375">右键单击 " **MyOtherGPO**"，然后单击 "**签出**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-375">Right-click **MyOtherGPO**, and then click **Check Out**.</span></span>

3.  <span data-ttu-id="aebdf-376">键入要在已签出的 GPO 的历史记录中显示的注释，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="aebdf-376">Type a comment to be displayed in the history of the GPO while it is checked out, and then click **OK**.</span></span>

4.  <span data-ttu-id="aebdf-377">当**AGPM 进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-377">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="aebdf-378">在 "**受控**" 选项卡上，将 GPO 的状态标识为 "**已签出**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-378">On the **Controlled** tab, the state of the GPO is identified as **Checked Out**.</span></span>

**<span data-ttu-id="aebdf-379">脱机编辑该 GPO 并配置帐户锁定时间</span><span class="sxs-lookup"><span data-stu-id="aebdf-379">To edit the GPO offline and configure the account lockout duration</span></span>**

1.  <span data-ttu-id="aebdf-380">在 "**受控**" 选项卡上，右键单击 " **MyOtherGPO**"，然后单击 "**编辑**" 以打开 "**组策略对象编辑器**" 窗口，并对 GPO 的脱机副本进行更改。</span><span class="sxs-lookup"><span data-stu-id="aebdf-380">On the **Controlled** tab, right-click **MyOtherGPO**, and then click **Edit** to open the **Group Policy Object Editor** window and make changes to an offline copy of the GPO.</span></span> <span data-ttu-id="aebdf-381">对于此方案，请配置最小密码长度：</span><span class="sxs-lookup"><span data-stu-id="aebdf-381">For this scenario, configure the minimum password length:</span></span>

    1.  <span data-ttu-id="aebdf-382">在 "**计算机配置**" 下，双击 " **Windows 设置**"，双击 "**安全设置**"，双击 "**帐户策略**"，然后双击 "**帐户锁定策略**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-382">Under **Computer Configuration**, double-click **Windows Settings**, double-click **Security Settings**, double-click **Account Policies**, and double-click **Account Lockout Policy**.</span></span>

    2.  <span data-ttu-id="aebdf-383">在 "详细信息" 窗格中，双击 "**帐户锁定时间**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-383">In the details pane, double-click **Account lockout duration**.</span></span>

    3.  <span data-ttu-id="aebdf-384">在 "属性" 窗口中，选中 "**定义此策略设置**"，将 "持续时间" 设置为 " **30**分钟"，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="aebdf-384">In the properties window, check **Define this policy setting**, set the duration to **30** minutes, and then click **OK**.</span></span>

2.  <span data-ttu-id="aebdf-385">关闭 "**组策略对象编辑器**" 窗口。</span><span class="sxs-lookup"><span data-stu-id="aebdf-385">Close the **Group Policy Object Editor** window.</span></span>

<span data-ttu-id="aebdf-386">在[步骤2：编辑 GPO](#bkmk-manage2)中，将 MyOtherGPO 签入存档并请求部署。</span><span class="sxs-lookup"><span data-stu-id="aebdf-386">Check MyOtherGPO into the archive and request deployment as you did for MyGPO in [Step 2: Edit a GPO](#bkmk-manage2).</span></span> <span data-ttu-id="aebdf-387">你可以使用差异报告将 MyOtherGPO 与 MyGPO 或 MyTemplate 进行比较。</span><span class="sxs-lookup"><span data-stu-id="aebdf-387">You can compare MyOtherGPO to MyGPO or to MyTemplate using difference reports.</span></span> <span data-ttu-id="aebdf-388">任何包含审阅者角色的帐户（AGPM 管理员 \ [完全控制 \]、审批者、编辑者或审阅者）都可以生成报表。</span><span class="sxs-lookup"><span data-stu-id="aebdf-388">Any account that includes the Reviewer role (AGPM Administrator \[Full Control\], Approver, Editor, or Reviewer) can generate reports.</span></span>

**<span data-ttu-id="aebdf-389">将 GPO 与另一个 GPO 和模板进行比较</span><span class="sxs-lookup"><span data-stu-id="aebdf-389">To compare a GPO to another GPO and to a template</span></span>**

1.  <span data-ttu-id="aebdf-390">要比较 MyGPO 和 MyOtherGPO，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="aebdf-390">To compare MyGPO and MyOtherGPO:</span></span>

    1.  <span data-ttu-id="aebdf-391">在 "**受控**" 选项卡上，单击 " **MyGPO**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-391">On the **Controlled** tab, click **MyGPO**.</span></span> <span data-ttu-id="aebdf-392">按**CTRL** ，然后单击 " **MyOtherGPO**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-392">Press **CTRL** and then click **MyOtherGPO**.</span></span>

    2.  <span data-ttu-id="aebdf-393">右键单击 " **MyOtherGPO**"，指向 "**差异**"，然后单击 " **HTML 报表**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-393">Right-click **MyOtherGPO**, point to **Differences**, and click **HTML Report**.</span></span>

2.  <span data-ttu-id="aebdf-394">要比较 MyOtherGPO 和 MyTemplate，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="aebdf-394">To compare MyOtherGPO and MyTemplate:</span></span>

    1.  <span data-ttu-id="aebdf-395">在 "**受控**" 选项卡上，单击 " **MyOtherGPO**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-395">On the **Controlled** tab, click **MyOtherGPO**.</span></span>

    2.  <span data-ttu-id="aebdf-396">右键单击 " **MyOtherGPO**"，指向 "**差异**"，然后单击 "**模板**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-396">Right-click **MyOtherGPO**, point to **Differences**, and click **Template**.</span></span>

    3.  <span data-ttu-id="aebdf-397">选择 " **MyTemplate** " 和 " **HTML 报表**"，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="aebdf-397">Select **MyTemplate** and **HTML Report**, and then click **OK**.</span></span>

### <a href="" id="bkmk-manage5"></a><span data-ttu-id="aebdf-398">步骤5：删除和还原 GPO</span><span class="sxs-lookup"><span data-stu-id="aebdf-398">Step 5: Delete and restore a GPO</span></span>

<span data-ttu-id="aebdf-399">在此步骤中，你充当审批者以删除 GPO。</span><span class="sxs-lookup"><span data-stu-id="aebdf-399">In this step, you act as an Approver to delete a GPO.</span></span>

**<span data-ttu-id="aebdf-400">删除 GPO</span><span class="sxs-lookup"><span data-stu-id="aebdf-400">To delete a GPO</span></span>**

1.  <span data-ttu-id="aebdf-401">在已安装了 AGPM 客户端的计算机上，使用已分配有审批者角色的用户帐户登录。</span><span class="sxs-lookup"><span data-stu-id="aebdf-401">On a computer on which you have installed AGPM Client, log on with a user account that has been assigned the role of Approver.</span></span>

2.  <span data-ttu-id="aebdf-402">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-402">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

3.  <span data-ttu-id="aebdf-403">在 "**目录**" 选项卡上，单击 "**受控**" 选项卡以显示受控 gpo。</span><span class="sxs-lookup"><span data-stu-id="aebdf-403">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

4.  <span data-ttu-id="aebdf-404">右键单击 " **MyGPO**"，然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-404">Right-click **MyGPO**, and then click **Delete**.</span></span> <span data-ttu-id="aebdf-405">单击 "**从存档和生产中删除 GPO** " 以删除存档中的版本以及在生产环境中部署的 gpo 的部署版本。</span><span class="sxs-lookup"><span data-stu-id="aebdf-405">Click **Delete GPO from archive and production** to delete both the version in the archive as well as the deployed version of the GPO in the production environment.</span></span>

5.  <span data-ttu-id="aebdf-406">键入要显示在 GPO 审核跟踪中的注释，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="aebdf-406">Type a comment to be displayed in the audit trail for the GPO, and then click **OK**.</span></span>

6.  <span data-ttu-id="aebdf-407">当**AGPM 进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-407">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="aebdf-408">GPO 将从 "**受控**" 选项卡中删除，并显示在 "**回收站**" 选项卡上，可在其中还原或销毁。</span><span class="sxs-lookup"><span data-stu-id="aebdf-408">The GPO is removed from the **Controlled** tab and is displayed on the **Recycle Bin** tab, where it can be restored or destroyed.</span></span>

<span data-ttu-id="aebdf-409">有时，你可能会在删除仍需要的 GPO 后发现。</span><span class="sxs-lookup"><span data-stu-id="aebdf-409">Occasionally you may discover after deleting a GPO that it is still needed.</span></span> <span data-ttu-id="aebdf-410">在此步骤中，你充当审批者以还原已删除的 GPO。</span><span class="sxs-lookup"><span data-stu-id="aebdf-410">In this step, you act as an Approver to restore a GPO that has been deleted.</span></span>

**<span data-ttu-id="aebdf-411">还原已删除的 GPO</span><span class="sxs-lookup"><span data-stu-id="aebdf-411">To restore a deleted GPO</span></span>**

1.  <span data-ttu-id="aebdf-412">在 "**目录**" 选项卡上，单击 "**回收站**" 选项卡以显示已删除的 gpo。</span><span class="sxs-lookup"><span data-stu-id="aebdf-412">On the **Contents** tab, click the **Recycle Bin** tab to display deleted GPOs.</span></span>

2.  <span data-ttu-id="aebdf-413">右键单击 " **MyGPO**"，然后单击 "**还原**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-413">Right-click **MyGPO**, and then click **Restore**.</span></span>

3.  <span data-ttu-id="aebdf-414">键入要在 GPO 的历史记录中显示的注释，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="aebdf-414">Type a comment to be displayed in the history of the GPO, and then click **OK**.</span></span>

4.  <span data-ttu-id="aebdf-415">当**AGPM 进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-415">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="aebdf-416">该 GPO 将从 "**回收站**" 选项卡中删除，并显示在 "**受控**" 选项卡上。</span><span class="sxs-lookup"><span data-stu-id="aebdf-416">The GPO is removed from the **Recycle Bin** tab and is displayed on the **Controlled** tab.</span></span>

    <span data-ttu-id="aebdf-417">**注意** 将 GPO 还原到存档不会自动将其重新部署到生产环境。</span><span class="sxs-lookup"><span data-stu-id="aebdf-417">**Note** Restoring a GPO to the archive does not automatically redeploy it to the production environment.</span></span> <span data-ttu-id="aebdf-418">若要将 GPO 返回到生产环境，请按照[步骤3部署 gpo：查看和部署 gpo](#bkmk-manage3)。</span><span class="sxs-lookup"><span data-stu-id="aebdf-418">To return the GPO to the production environment, deploy the GPO as in [Step 3: Review and deploy a GPO](#bkmk-manage3).</span></span>

     

<span data-ttu-id="aebdf-419">在编辑和部署 GPO 之后，你可能会发现对 GPO 所做的最新更改会导致出现问题。</span><span class="sxs-lookup"><span data-stu-id="aebdf-419">After editing and deploying a GPO, you may discover that recent changes to the GPO are causing a problem.</span></span> <span data-ttu-id="aebdf-420">在此步骤中，你充当审批者以回退到 GPO 的以前版本。</span><span class="sxs-lookup"><span data-stu-id="aebdf-420">In this step, you act as an Approver to roll back to a previous version of the GPO.</span></span> <span data-ttu-id="aebdf-421">你可以回退到 GPO 历史记录中的任意版本。</span><span class="sxs-lookup"><span data-stu-id="aebdf-421">You can roll back to any version in the history of the GPO.</span></span> <span data-ttu-id="aebdf-422">你可以使用批注和标签来标识已知的有效版本以及进行特定的更改。</span><span class="sxs-lookup"><span data-stu-id="aebdf-422">You can use comments and labels to identify known good versions and when specific changes were made.</span></span>

**<span data-ttu-id="aebdf-423">回滚到 GPO 的以前版本</span><span class="sxs-lookup"><span data-stu-id="aebdf-423">To roll back to a previous version of a GPO</span></span>**

1.  <span data-ttu-id="aebdf-424">在 "**目录**" 选项卡上，单击 "**受控**" 选项卡以显示受控 gpo。</span><span class="sxs-lookup"><span data-stu-id="aebdf-424">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

2.  <span data-ttu-id="aebdf-425">双击 " **MyGPO** " 以显示其历史记录。</span><span class="sxs-lookup"><span data-stu-id="aebdf-425">Double-click **MyGPO** to display its history.</span></span>

3.  <span data-ttu-id="aebdf-426">右键单击要部署的版本，单击 "**部署**"，然后单击 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="aebdf-426">Right-click the version to be deployed, click **Deploy**, and then click **Yes**.</span></span>

4.  <span data-ttu-id="aebdf-427">当**进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-427">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="aebdf-428">在 "**历史记录**" 窗口中，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-428">In the **History** window, click **Close**.</span></span>

    <span data-ttu-id="aebdf-429">**注意** 若要验证已重新部署的版本是否为所需版本，请检查两个版本的差异报告。</span><span class="sxs-lookup"><span data-stu-id="aebdf-429">**Note** To verify that the version that has been redeployed is the version intended, examine a difference report for the two versions.</span></span> <span data-ttu-id="aebdf-430">在 GPO 的 "**历史记录**" 窗口中，选择两个版本，右键单击它们，指向 "**差异**"，然后单击 " **HTML 报表**" 或 " **XML 报表**"。</span><span class="sxs-lookup"><span data-stu-id="aebdf-430">In the **History** window for the GPO, select the two versions, right-click them, point to **Difference**, and then click either **HTML Report** or **XML Report**.</span></span>

     

 

 





