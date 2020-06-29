---
title: Microsoft 高级组策略管理 4.0 分步指南
description: Microsoft 高级组策略管理 4.0 分步指南
author: dansimp
ms.assetid: dc6f9b16-b1d4-48f3-88bb-f29301f0131c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 819d536451095d23080115799016aa0ac5242dee
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802520"
---
# <span data-ttu-id="3ae92-103">Microsoft 高级组策略管理 4.0 分步指南</span><span class="sxs-lookup"><span data-stu-id="3ae92-103">Step-by-Step Guide for Microsoft Advanced Group Policy Management 4.0</span></span>


<span data-ttu-id="3ae92-104">本分步指南介绍了使用组策略管理控制台（GPMC）和 Microsoft 高级组策略管理（AGPM）的组策略管理的高级技术。</span><span class="sxs-lookup"><span data-stu-id="3ae92-104">This step-by-step guide demonstrates advanced techniques for Group Policy management that use the Group Policy Management Console (GPMC) and Microsoft Advanced Group Policy Management (AGPM).</span></span> <span data-ttu-id="3ae92-105">AGPM 增加了 GPMC 的功能，提供：</span><span class="sxs-lookup"><span data-stu-id="3ae92-105">AGPM increases the capabilities of the GPMC, providing:</span></span>

-   <span data-ttu-id="3ae92-106">将管理组策略对象（Gpo）的权限委派给多个组策略管理员的标准角色，以及委派对生产环境中的 Gpo 的访问权限的功能。</span><span class="sxs-lookup"><span data-stu-id="3ae92-106">Standard roles for delegating permissions to manage Group Policy Objects (GPOs) to multiple Group Policy administrators, in addition to the ability to delegate access to GPOs in the production environment.</span></span>

-   <span data-ttu-id="3ae92-107">用于启用组策略管理员在将 Gpo 部署到生产环境之前脱机创建和修改 Gpo 的存档。</span><span class="sxs-lookup"><span data-stu-id="3ae92-107">An archive to enable Group Policy administrators to create and modify GPOs offline before the GPOs are deployed into a production environment.</span></span>

-   <span data-ttu-id="3ae92-108">回滚到存档中的 GPO 的任何早期版本的功能，并限制存档中存储的版本数。</span><span class="sxs-lookup"><span data-stu-id="3ae92-108">The ability to roll back to any earlier version of a GPO in the archive and to limit the number of versions stored in the archive.</span></span>

-   <span data-ttu-id="3ae92-109">Gpo 的签入和签出功能，以确保组策略管理员不会无意间覆盖彼此的工作。</span><span class="sxs-lookup"><span data-stu-id="3ae92-109">Check-in and check-out capability for GPOs to make sure that Group Policy administrators do not unintentionally overwrite each other's work.</span></span>

-   <span data-ttu-id="3ae92-110">搜索具有特定属性的 Gpo 并筛选所显示的 Gpo 列表的功能。</span><span class="sxs-lookup"><span data-stu-id="3ae92-110">The ability to search for GPOs with specific attributes and to filter the list of GPOs displayed.</span></span>

## <span data-ttu-id="3ae92-111">AGPM 方案概述</span><span class="sxs-lookup"><span data-stu-id="3ae92-111">AGPM scenario overview</span></span>


<span data-ttu-id="3ae92-112">对于此方案，你将为 AGPM 中的每个角色使用单独的用户帐户，演示如何在具有不同级别的权限的多个组策略管理员的环境中管理组策略。</span><span class="sxs-lookup"><span data-stu-id="3ae92-112">For this scenario, you will use a separate user account for each role in AGPM to demonstrate how Group Policy can be managed in an environment that has multiple Group Policy administrators who have different levels of permissions.</span></span> <span data-ttu-id="3ae92-113">具体地说，你将执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="3ae92-113">Specifically, you will perform the following tasks:</span></span>

-   <span data-ttu-id="3ae92-114">使用属于域管理员组成员的帐户，安装 AGPM 服务器并将 AGPM 管理员角色分配给帐户或组。</span><span class="sxs-lookup"><span data-stu-id="3ae92-114">Using an account that is a member of the Domain Admins group, install AGPM Server and assign the AGPM Administrator role to an account or group.</span></span>

-   <span data-ttu-id="3ae92-115">使用您将为其分配 AGPM 角色的帐户，安装 AGPM 客户端。</span><span class="sxs-lookup"><span data-stu-id="3ae92-115">Using accounts to which you will assign AGPM roles, install AGPM Client.</span></span>

-   <span data-ttu-id="3ae92-116">使用具有 AGPM 管理员角色的帐户配置 AGPM 并通过向其他帐户分配角色来委派对 Gpo 的访问权限。</span><span class="sxs-lookup"><span data-stu-id="3ae92-116">Using an account that has the AGPM Administrator role, configure AGPM and delegate access to GPOs by assigning roles to other accounts.</span></span>

-   <span data-ttu-id="3ae92-117">从具有 "编辑者" 角色的帐户中，请求创建一个新的 GPO，然后通过使用具有审批者角色的帐户进行审批。</span><span class="sxs-lookup"><span data-stu-id="3ae92-117">From an account that has the Editor role, request that a new GPO be created that you then approve by using an account that has the Approver role.</span></span> <span data-ttu-id="3ae92-118">使用编辑器帐户将 GPO 从存档中签出，编辑 GPO，将 GPO 签入存档，然后请求部署。</span><span class="sxs-lookup"><span data-stu-id="3ae92-118">Use the Editor account to check the GPO out of the archive, edit the GPO, check the GPO into the archive, and then request deployment.</span></span>

-   <span data-ttu-id="3ae92-119">使用具有审批者角色的帐户，查看 GPO 并将其部署到生产环境。</span><span class="sxs-lookup"><span data-stu-id="3ae92-119">Using an account that has the Approver role, review the GPO and deploy it to your production environment.</span></span>

-   <span data-ttu-id="3ae92-120">使用具有编辑器角色的帐户创建一个 GPO 模板，并将其用作创建新 GPO 的起始点。</span><span class="sxs-lookup"><span data-stu-id="3ae92-120">Using an account that has the Editor role, create a GPO template and use it as a starting point to create a new GPO.</span></span>

-   <span data-ttu-id="3ae92-121">使用具有审批者角色的帐户，删除和还原 GPO。</span><span class="sxs-lookup"><span data-stu-id="3ae92-121">Using an account that has the Approver role, delete and restore a GPO.</span></span>

![组策略对象开发过程](images/ab77a1f3-f430-4e7d-be58-ee8f9bd1140e.gif)

## <span data-ttu-id="3ae92-123">要求</span><span class="sxs-lookup"><span data-stu-id="3ae92-123">Requirements</span></span>


<span data-ttu-id="3ae92-124">要安装 AGPM 的计算机必须满足以下要求，并且你必须创建用于此方案的帐户。</span><span class="sxs-lookup"><span data-stu-id="3ae92-124">Computers on which you want to install AGPM must meet the following requirements, and you must create accounts for use in this scenario.</span></span>

<span data-ttu-id="3ae92-125">**注意** 如果已安装了 AGPM 2.5，并且正在从 Windows Server®2003升级到 Windows Server2008R2 或 Windows Server2008，或者从 WindowsVista 升级到 Windows7 或 WindowsVista®使用服务 Pack1 （SP1），则必须升级操作系统，然后才能升级到 AGPM 4.0。</span><span class="sxs-lookup"><span data-stu-id="3ae92-125">**Note** If you have AGPM 2.5 installed and are upgrading from Windows Server®2003 to Windows Server2008R2 or Windows Server2008, or are upgrading from WindowsVista with no service packs installed to Windows7 or WindowsVista® with Service Pack1 (SP1), you must upgrade the operating system before you can upgrade to AGPM4.0.</span></span>

<span data-ttu-id="3ae92-126">如果安装了 AGPM 3.0，则无需在升级到 AGPM 4.0 之前升级操作系统</span><span class="sxs-lookup"><span data-stu-id="3ae92-126">If you have AGPM 3.0 installed, you do not have to upgrade the operating system before you upgrade to AGPM 4.0</span></span>

 

<span data-ttu-id="3ae92-127">在包含较新版本和较旧操作系统的混合环境中，功能有一些限制，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="3ae92-127">In a mixed environment that includes both newer and older operating systems, there are some limitations to functionality, as indicated in the following table.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3ae92-128">在其上运行 AGPM 服务器4.0 的操作系统</span><span class="sxs-lookup"><span data-stu-id="3ae92-128">Operating system on which AGPM Server 4.0 runs</span></span></th>
<th align="left"><span data-ttu-id="3ae92-129">在其上运行 AGPM 客户端4.0 的操作系统</span><span class="sxs-lookup"><span data-stu-id="3ae92-129">Operating system on which AGPM Client 4.0 runs</span></span></th>
<th align="left"><span data-ttu-id="3ae92-130">AGPM 4.0 支持的状态</span><span class="sxs-lookup"><span data-stu-id="3ae92-130">Status of AGPM 4.0 support</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3ae92-131">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="3ae92-131">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ae92-132">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="3ae92-132">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ae92-133">支持</span><span class="sxs-lookup"><span data-stu-id="3ae92-133">Supported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3ae92-134">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="3ae92-134">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ae92-135">Windows Server2008 或 Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="3ae92-135">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ae92-136">受支持，但不能编辑仅存在于 Windows Server2008R2 或 Windows7 中的策略设置或首选项</span><span class="sxs-lookup"><span data-stu-id="3ae92-136">Supported, but cannot edit policy settings or preference items that exist only in Windows Server2008R2 or Windows7</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3ae92-137">Windows Server2008 或 Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="3ae92-137">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ae92-138">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="3ae92-138">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ae92-139">不支持</span><span class="sxs-lookup"><span data-stu-id="3ae92-139">Unsupported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3ae92-140">Windows Server2008 或 Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="3ae92-140">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ae92-141">Windows Server2008 或 Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="3ae92-141">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ae92-142">受支持，但无法报告或编辑仅存在于 Windows Server2008R2 或 Windows7 中的策略设置或首选项</span><span class="sxs-lookup"><span data-stu-id="3ae92-142">Supported, but cannot report or edit policy settings or preference items that exist only in Windows Server2008R2 or Windows7</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="3ae92-143">AGPM 服务器要求</span><span class="sxs-lookup"><span data-stu-id="3ae92-143">AGPM Server requirements</span></span>

<span data-ttu-id="3ae92-144">AGPM Server 4.0 要求 Windows Server2008R2、Windows Server2008、Windows7 和 GPMC 来自远程服务器管理工具（RSAT），或者 Windows Vista 中安装了来自 RSAT 的 SP1 和 GPMC。</span><span class="sxs-lookup"><span data-stu-id="3ae92-144">AGPM Server4.0 requires Windows Server2008R2, Windows Server2008, Windows7 and the GPMC from Remote Server Administration Tools (RSAT), or Windows Vista with SP1 and the GPMC from RSAT installed.</span></span> <span data-ttu-id="3ae92-145">支持32位和64位版本。</span><span class="sxs-lookup"><span data-stu-id="3ae92-145">Both 32-bit and 64-bit versions are supported.</span></span>

<span data-ttu-id="3ae92-146">在安装 AGPM 服务器之前，您必须是域管理员组的成员，除非另有说明，否则必须存在以下 Windows 功能：</span><span class="sxs-lookup"><span data-stu-id="3ae92-146">Before you install AGPM Server, you must be a member of the Domain Admins group and the following Windows features must be present unless otherwise noted:</span></span>

-   <span data-ttu-id="3ae92-147">GPMC.MSC</span><span class="sxs-lookup"><span data-stu-id="3ae92-147">GPMC</span></span>

    -   <span data-ttu-id="3ae92-148">Windows Server2008R2 或 Windows Server2008：如果 GPMC 不存在，则由 AGPM 自动安装。</span><span class="sxs-lookup"><span data-stu-id="3ae92-148">Windows Server2008R2 or Windows Server2008: If the GPMC is not present, it is automatically installed by AGPM.</span></span>

    -   <span data-ttu-id="3ae92-149">Windows7：安装 AGPM 之前，必须从 RSAT 安装 GPMC。</span><span class="sxs-lookup"><span data-stu-id="3ae92-149">Windows7: You must install the GPMC from RSAT before you install AGPM.</span></span> <span data-ttu-id="3ae92-150">有关详细信息，请参阅[适用于 Windows 7 的远程服务器管理工具](https://go.microsoft.com/fwlink/?LinkID=131280)（ https://go.microsoft.com/fwlink/?LinkID=131280) 。</span><span class="sxs-lookup"><span data-stu-id="3ae92-150">For more information, see [Remote Server Administration Tools for Windows 7](https://go.microsoft.com/fwlink/?LinkID=131280) (https://go.microsoft.com/fwlink/?LinkID=131280).</span></span>

    -   <span data-ttu-id="3ae92-151">Windows Vista with SP1：安装 AGPM 之前，必须从 RSAT 安装 GPMC。</span><span class="sxs-lookup"><span data-stu-id="3ae92-151">Windows Vista with SP1: You must install the GPMC from RSAT before you install AGPM.</span></span> <span data-ttu-id="3ae92-152">有关详细信息，请参阅[适用于 Windows Vista 的远程服务器管理工具 Service Pack 1](https://go.microsoft.com/fwlink/?LinkID=116179) （ https://go.microsoft.com/fwlink/?LinkID=116179) 。</span><span class="sxs-lookup"><span data-stu-id="3ae92-152">For more information, see [Remote Server Administration Tools for Windows Vista with Service Pack 1](https://go.microsoft.com/fwlink/?LinkID=116179) (https://go.microsoft.com/fwlink/?LinkID=116179).</span></span>

-   <span data-ttu-id="3ae92-153">.NET Framework 3.5 或更高版本</span><span class="sxs-lookup"><span data-stu-id="3ae92-153">The .NET Framework 3.5 or later versions</span></span>

    -   <span data-ttu-id="3ae92-154">Windows Server2008R2 或 Windows7：如果不存在 .NET Framework 3.5 或更高版本，则由 AGPM 自动安装 .NET Framework 3.5。</span><span class="sxs-lookup"><span data-stu-id="3ae92-154">Windows Server2008R2 or Windows7: If the .NET Framework 3.5 or later version is not present, the .NET Framework 3.5 is automatically installed by AGPM.</span></span>

    -   <span data-ttu-id="3ae92-155">Windows Server2008 或 Windows Vista SP1：安装 AGPM 之前，必须先安装 .NET Framework 3.5 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="3ae92-155">Windows Server2008 or Windows Vista with SP1: You must install the .NET Framework 3.5 or a later version before you install AGPM.</span></span>

<span data-ttu-id="3ae92-156">AGPM 服务器需要以下 Windows 功能，如果不存在，将自动安装这些功能：</span><span class="sxs-lookup"><span data-stu-id="3ae92-156">The following Windows features are required by AGPM Server and will be automatically installed if they are not present:</span></span>

-   <span data-ttu-id="3ae92-157">WCF 激活;非 HTTP 激活</span><span class="sxs-lookup"><span data-stu-id="3ae92-157">WCF Activation; Non-HTTP Activation</span></span>

-   <span data-ttu-id="3ae92-158">Windows Process Activation Service</span><span class="sxs-lookup"><span data-stu-id="3ae92-158">Windows Process Activation Service</span></span>

    -   <span data-ttu-id="3ae92-159">流程模型</span><span class="sxs-lookup"><span data-stu-id="3ae92-159">Process Model</span></span>

    -   <span data-ttu-id="3ae92-160">.NET 环境</span><span class="sxs-lookup"><span data-stu-id="3ae92-160">The .NET Environment</span></span>

    -   <span data-ttu-id="3ae92-161">配置 Api</span><span class="sxs-lookup"><span data-stu-id="3ae92-161">Configuration APIs</span></span>

### <span data-ttu-id="3ae92-162">AGPM 客户端要求</span><span class="sxs-lookup"><span data-stu-id="3ae92-162">AGPM Client requirements</span></span>

<span data-ttu-id="3ae92-163">AGPM 客户端4.0 要求来自 RSAT 的 Windows Server2008R2、Windows Server2008、Windows7 和 GPMC，或者 Windows Vista SP1 和从 RSAT 安装的 GPMC。</span><span class="sxs-lookup"><span data-stu-id="3ae92-163">AGPM Client4.0 requires Windows Server2008R2, Windows Server2008, Windows7 and the GPMC from RSAT, or Windows Vista with SP1 and the GPMC from RSAT installed.</span></span> <span data-ttu-id="3ae92-164">支持32位和64位版本。</span><span class="sxs-lookup"><span data-stu-id="3ae92-164">Both 32-bit and 64-bit versions are supported.</span></span> <span data-ttu-id="3ae92-165">可以在运行 AGPM 服务器的计算机上安装 AGPM 客户端。</span><span class="sxs-lookup"><span data-stu-id="3ae92-165">AGPM Client can be installed on a computer that is running AGPM Server.</span></span>

<span data-ttu-id="3ae92-166">AGPM 客户端需要以下 Windows 功能，除非另有说明，否则将自动安装这些功能（如果不存在）：</span><span class="sxs-lookup"><span data-stu-id="3ae92-166">The following Windows features are required by AGPM Client and unless otherwise noted are automatically installed if they are not present:</span></span>

-   <span data-ttu-id="3ae92-167">GPMC.MSC</span><span class="sxs-lookup"><span data-stu-id="3ae92-167">GPMC</span></span>

    -   <span data-ttu-id="3ae92-168">Windows Server2008R2 或 Windows Server2008：如果 GPMC 不存在，则由 AGPM 自动安装。</span><span class="sxs-lookup"><span data-stu-id="3ae92-168">Windows Server2008R2 or Windows Server2008: If the GPMC is not present, it is automatically installed by AGPM.</span></span>

    -   <span data-ttu-id="3ae92-169">Windows7：安装 AGPM 之前，必须从 RSAT 安装 GPMC。</span><span class="sxs-lookup"><span data-stu-id="3ae92-169">Windows7: You must install the GPMC from RSAT before you install AGPM.</span></span> <span data-ttu-id="3ae92-170">有关详细信息，请参阅[适用于 Windows 7 的远程服务器管理工具](https://go.microsoft.com/fwlink/?LinkID=131280)（ https://go.microsoft.com/fwlink/?LinkID=131280) 。</span><span class="sxs-lookup"><span data-stu-id="3ae92-170">For more information, see [Remote Server Administration Tools for Windows 7](https://go.microsoft.com/fwlink/?LinkID=131280) (https://go.microsoft.com/fwlink/?LinkID=131280).</span></span>

    -   <span data-ttu-id="3ae92-171">Windows Vista with SP1：安装 AGPM 之前，必须从 RSAT 安装 GPMC。</span><span class="sxs-lookup"><span data-stu-id="3ae92-171">Windows Vista with SP1: You must install the GPMC from RSAT before you install AGPM.</span></span> <span data-ttu-id="3ae92-172">有关详细信息，请参阅[适用于 Windows Vista 的远程服务器管理工具 Service Pack 1](https://go.microsoft.com/fwlink/?LinkID=116179) （ https://go.microsoft.com/fwlink/?LinkID=116179) 。</span><span class="sxs-lookup"><span data-stu-id="3ae92-172">For more information, see [Remote Server Administration Tools for Windows Vista with Service Pack 1](https://go.microsoft.com/fwlink/?LinkID=116179) (https://go.microsoft.com/fwlink/?LinkID=116179).</span></span>

-   <span data-ttu-id="3ae92-173">.NET Framework 3.0 或更高版本</span><span class="sxs-lookup"><span data-stu-id="3ae92-173">The .NET Framework 3.0 or later version</span></span>

    -   <span data-ttu-id="3ae92-174">Windows Server2008R2 或 Windows7：如果不存在 .NET Framework 3.0 或更高版本，则由 AGPM 自动安装 .NET Framework 3.5。</span><span class="sxs-lookup"><span data-stu-id="3ae92-174">Windows Server2008R2 or Windows7: If the .NET Framework 3.0 or later version is not present, the .NET Framework 3.5 is automatically installed by AGPM.</span></span>

    -   <span data-ttu-id="3ae92-175">使用 SP1 的 windows Server2008 或 Windows Vista：如果不存在 .NET Framework 3.0 或更高版本，则由 AGPM 自动安装 .NET Framework 3.0。</span><span class="sxs-lookup"><span data-stu-id="3ae92-175">Windows Server2008 or Windows Vista with SP1: If the .NET Framework 3.0 or later version is not present, the .NET Framework 3.0 is automatically installed by AGPM.</span></span>

### <span data-ttu-id="3ae92-176">方案要求</span><span class="sxs-lookup"><span data-stu-id="3ae92-176">Scenario requirements</span></span>

<span data-ttu-id="3ae92-177">在开始此方案之前，请创建四个用户帐户。</span><span class="sxs-lookup"><span data-stu-id="3ae92-177">Before you begin this scenario, create four user accounts.</span></span> <span data-ttu-id="3ae92-178">在此方案中，你将为以下每个帐户分配以下 AGPM 角色之一： AGPM 管理员（完全控制）、审批者、编辑者和审阅者。</span><span class="sxs-lookup"><span data-stu-id="3ae92-178">During the scenario, you will assign one of the following AGPM roles to each of these accounts: AGPM Administrator (Full Control), Approver, Editor, and Reviewer.</span></span> <span data-ttu-id="3ae92-179">这些帐户必须能够发送和接收电子邮件。</span><span class="sxs-lookup"><span data-stu-id="3ae92-179">These accounts must be able to send and receive e-mail messages.</span></span> <span data-ttu-id="3ae92-180">为具有 AGPM 管理员、审批者和（可选）编辑器角色的帐户分配**链接 gpo**权限。</span><span class="sxs-lookup"><span data-stu-id="3ae92-180">Assign **Link GPOs** permission to the accounts that have the AGPM Administrator, Approver, and (optionally) Editor roles.</span></span>

<span data-ttu-id="3ae92-181">**注意** 
默认情况下， **Link gpo**权限分配给域管理员和企业管理员的成员。</span><span class="sxs-lookup"><span data-stu-id="3ae92-181">**Note**
**Link GPOs** permission is assigned to members of Domain Administrators and Enterprise Administrators by default.</span></span> <span data-ttu-id="3ae92-182">若要将**链接 gpo**权限分配给其他用户或组（如具有 AGPM 管理员或审批者角色的帐户），请单击域的节点，然后单击 "**委派**" 选项卡，选择 "**链接 Gpo**"，单击 "**添加**"，然后选择要向其分配权限的用户或组。</span><span class="sxs-lookup"><span data-stu-id="3ae92-182">To assign **Link GPOs** permission to additional users or groups (such as accounts that have the roles of AGPM Administrator or Approver), click the node for the domain and then click the **Delegation** tab, select **Link GPOs**, click **Add**, and select users or groups to which you want to assign the permission.</span></span>

 

## <span data-ttu-id="3ae92-183">安装和配置 AGPM 的步骤</span><span class="sxs-lookup"><span data-stu-id="3ae92-183">Steps for installing and configuring AGPM</span></span>


<span data-ttu-id="3ae92-184">必须完成以下步骤才能安装和配置 AGPM。</span><span class="sxs-lookup"><span data-stu-id="3ae92-184">You must complete the following steps to install and configure AGPM.</span></span>

[<span data-ttu-id="3ae92-185">步骤1：安装 AGPM 服务器</span><span class="sxs-lookup"><span data-stu-id="3ae92-185">Step 1: Install AGPM Server</span></span>](#bkmk-config1)

[<span data-ttu-id="3ae92-186">步骤2：安装 AGPM 客户端</span><span class="sxs-lookup"><span data-stu-id="3ae92-186">Step 2: Install AGPM Client</span></span>](#bkmk-config2)

[<span data-ttu-id="3ae92-187">步骤3：配置 AGPM 服务器连接</span><span class="sxs-lookup"><span data-stu-id="3ae92-187">Step 3: Configure an AGPM Server connection</span></span>](#bkmk-config3)

[<span data-ttu-id="3ae92-188">步骤4：配置电子邮件通知</span><span class="sxs-lookup"><span data-stu-id="3ae92-188">Step 4: Configure e-mail notification</span></span>](#bkmk-config4)

[<span data-ttu-id="3ae92-189">步骤5：代理访问</span><span class="sxs-lookup"><span data-stu-id="3ae92-189">Step 5: Delegate access</span></span>](#bkmk-config5)

### <a href="" id="bkmk-config1"></a><span data-ttu-id="3ae92-190">步骤1：安装 AGPM 服务器</span><span class="sxs-lookup"><span data-stu-id="3ae92-190">Step 1: Install AGPM Server</span></span>

<span data-ttu-id="3ae92-191">在此步骤中，将在将运行 AGPM 服务的成员服务器或域控制器上安装 AGPM 服务器，然后配置存档。</span><span class="sxs-lookup"><span data-stu-id="3ae92-191">In this step, you install AGPM Server on the member server or domain controller that will run the AGPM Service, and you configure the archive.</span></span> <span data-ttu-id="3ae92-192">所有 AGPM 操作都通过此 Windows 服务进行管理，并使用服务凭据执行。</span><span class="sxs-lookup"><span data-stu-id="3ae92-192">All AGPM operations are managed through this Windows service and are executed with the service's credentials.</span></span> <span data-ttu-id="3ae92-193">AGPM 服务器托管的存档可以托管在该服务器上，也可以在同一林中的另一台服务器上托管。</span><span class="sxs-lookup"><span data-stu-id="3ae92-193">The archive managed by an AGPM Server can be hosted on that server or on another server in the same forest.</span></span>

**<span data-ttu-id="3ae92-194">在将托管 AGPM 服务的计算机上安装 AGPM 服务器</span><span class="sxs-lookup"><span data-stu-id="3ae92-194">To install AGPM Server on the computer that will host the AGPM Service</span></span>**

1.  <span data-ttu-id="3ae92-195">使用域管理员组的成员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="3ae92-195">Log on with an account that is a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="3ae92-196">启动 Microsoft 桌面优化包 CD，然后按照屏幕上的说明选择 "**高级组策略管理-服务器**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-196">Start the Microsoft Desktop Optimization Pack CD and follow the instructions on screen to select **Advanced Group Policy Management - Server**.</span></span>

3.  <span data-ttu-id="3ae92-197">在 "**欢迎**" 对话框中，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-197">In the **Welcome** dialog box, click **Next**.</span></span>

4.  <span data-ttu-id="3ae92-198">在 " **Microsoft 软件许可条款**" 对话框中，接受条款，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-198">In the **Microsoft Software License Terms** dialog box, accept the terms and then click **Next**.</span></span>

5.  <span data-ttu-id="3ae92-199">在 "**应用程序路径**" 对话框中，选择要在其中安装 AGPM 服务器的位置。</span><span class="sxs-lookup"><span data-stu-id="3ae92-199">In the **Application Path** dialog box, select a location in which to install AGPM Server.</span></span> <span data-ttu-id="3ae92-200">安装了 AGPM 服务器的计算机将托管 AGPM 服务并管理存档。</span><span class="sxs-lookup"><span data-stu-id="3ae92-200">The computer on which AGPM Server is installed will host the AGPM Service and manage the archive.</span></span> <span data-ttu-id="3ae92-201">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3ae92-201">Click **Next**.</span></span>

6.  <span data-ttu-id="3ae92-202">在 "**存档路径**" 对话框中，选择存档相对于 AGPM 服务器的位置。</span><span class="sxs-lookup"><span data-stu-id="3ae92-202">In the **Archive Path** dialog box, select a location for the archive in relation to the AGPM Server.</span></span> <span data-ttu-id="3ae92-203">存档路径可以指向 AGPM 服务器或其他位置上的文件夹。</span><span class="sxs-lookup"><span data-stu-id="3ae92-203">The archive path can point to a folder on the AGPM Server or elsewhere.</span></span> <span data-ttu-id="3ae92-204">但是，你应该选择一个具有足够空间的位置来存储由此 AGPM 服务器管理的所有 Gpo 和历史记录数据。</span><span class="sxs-lookup"><span data-stu-id="3ae92-204">However, you should select a location with sufficient space to store all GPOs and history data managed by this AGPM Server.</span></span> <span data-ttu-id="3ae92-205">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3ae92-205">Click **Next**.</span></span>

7.  <span data-ttu-id="3ae92-206">在 " **Agpm 服务帐户**" 对话框中，选择要在其下运行 AGPM 服务的服务帐户，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-206">In the **AGPM Service Account** dialog box, select a service account under which the AGPM Service will run and then click **Next**.</span></span>

    <span data-ttu-id="3ae92-207">此帐户必须是域管理员组的成员，或者对于最低权限配置，由 AGPM 服务器管理的每个域中的以下组：</span><span class="sxs-lookup"><span data-stu-id="3ae92-207">This account must be a member of the either the Domain Admins group or, for a least-privilege configuration, the following groups in each domain managed by the AGPM Server:</span></span>

    -   <span data-ttu-id="3ae92-208">组策略创建者所有者</span><span class="sxs-lookup"><span data-stu-id="3ae92-208">Group Policy Creator Owners</span></span>

    -   <span data-ttu-id="3ae92-209">备份操作员</span><span class="sxs-lookup"><span data-stu-id="3ae92-209">Backup Operators</span></span>

    <span data-ttu-id="3ae92-210">此外，此帐户需要对以下文件夹的 "完全控制" 权限：</span><span class="sxs-lookup"><span data-stu-id="3ae92-210">Additionally, this account requires Full Control permission for the following folders:</span></span>

    -   <span data-ttu-id="3ae92-211">AGPM 存档文件夹，当在本地驱动器上安装了 AGPM 服务器的安装期间，此权限会自动授予此权限。</span><span class="sxs-lookup"><span data-stu-id="3ae92-211">The AGPM archive folder, for which this permission is automatically granted during the installation of AGPM Server if it is installed on a local drive.</span></span>

    -   <span data-ttu-id="3ae92-212">本地系统 temp 文件夹，通常为%windir%\\temp。</span><span class="sxs-lookup"><span data-stu-id="3ae92-212">The local system temp folder, typically %windir%\\temp.</span></span>

8.  <span data-ttu-id="3ae92-213">在 "**存档所有者**" 对话框中，选择要向其分配 AGPM 管理员（完全控制）角色的帐户或组。</span><span class="sxs-lookup"><span data-stu-id="3ae92-213">In the **Archive Owner** dialog box, select an account or group to which you assign the AGPM Administrator (Full Control) role.</span></span> <span data-ttu-id="3ae92-214">AGPM 管理员可以为其他组策略管理员分配 AGPM 角色和权限，以便稍后可以将 AGPM 管理员角色分配给其他组策略管理员。</span><span class="sxs-lookup"><span data-stu-id="3ae92-214">AGPM Administrators can assign AGPM roles and permissions to other Group Policy administrators, so that later you can assign the role of AGPM Administrator to additional Group Policy administrators.</span></span> <span data-ttu-id="3ae92-215">对于此方案，选择要在 AGPM 管理员角色中提供的帐户。</span><span class="sxs-lookup"><span data-stu-id="3ae92-215">For this scenario, select the account to serve in the AGPM Administrator role.</span></span> <span data-ttu-id="3ae92-216">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3ae92-216">Click **Next**.</span></span>

9.  <span data-ttu-id="3ae92-217">在 "**端口配置**" 对话框中，键入 AGPM 服务应侦听的端口。</span><span class="sxs-lookup"><span data-stu-id="3ae92-217">In the **Port Configuration** dialog box, type a port on which the AGPM Service should listen.</span></span> <span data-ttu-id="3ae92-218">不要清除 "**将端口例外添加到防火墙**" 复选框，除非手动配置端口例外或使用规则配置端口例外。</span><span class="sxs-lookup"><span data-stu-id="3ae92-218">Do not clear the **Add port exception to firewall** check box unless you manually configure port exceptions or use rules to configure port exceptions.</span></span> <span data-ttu-id="3ae92-219">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3ae92-219">Click **Next**.</span></span>

10. <span data-ttu-id="3ae92-220">在 "**语言**" 对话框中，选择要为 AGPM 服务器安装的一个或多个显示语言。</span><span class="sxs-lookup"><span data-stu-id="3ae92-220">In the **Languages** dialog box, select one or more display languages to install for AGPM Server.</span></span>

11. <span data-ttu-id="3ae92-221">单击 "**安装**"，然后单击 "**完成**" 退出设置向导。</span><span class="sxs-lookup"><span data-stu-id="3ae92-221">Click **Install**, and then click **Finish** to exit the Setup Wizard.</span></span>

    <span data-ttu-id="3ae92-222">**小心** 不要通过操作系统中的 "**管理工具**和**服务**" 更改 AGPM 服务的设置。</span><span class="sxs-lookup"><span data-stu-id="3ae92-222">**Caution** Do not change settings for the AGPM Service through **Administrative Tools** and **Services** in the operating system.</span></span> <span data-ttu-id="3ae92-223">这样做可能会阻止 AGPM 服务启动。</span><span class="sxs-lookup"><span data-stu-id="3ae92-223">Doing this can prevent the AGPM Service from starting.</span></span> <span data-ttu-id="3ae92-224">有关如何更改服务设置的信息，请参阅高级组策略管理的帮助。</span><span class="sxs-lookup"><span data-stu-id="3ae92-224">For information about how to change settings for the service, see Help for Advanced Group Policy Management.</span></span>

     

### <a href="" id="bkmk-config2"></a><span data-ttu-id="3ae92-225">步骤2：安装 AGPM 客户端</span><span class="sxs-lookup"><span data-stu-id="3ae92-225">Step 2: Install AGPM Client</span></span>

<span data-ttu-id="3ae92-226">每个组策略管理员（创建、编辑、部署、查看或删除 Gpo 的任何人）都必须在它们用于管理 Gpo 的计算机上安装 AGPM 客户端。</span><span class="sxs-lookup"><span data-stu-id="3ae92-226">Each Group Policy administrator—anyone who creates, edits, deploys, reviews, or deletes GPOs—must have AGPM Client installed on computers that they use to manage GPOs.</span></span> <span data-ttu-id="3ae92-227">只有在安装了 AGPM 客户端的情况下，才会在组策略管理控制台中显示用于执行许多 GPO 管理任务的 "更改控制" 节点。</span><span class="sxs-lookup"><span data-stu-id="3ae92-227">The Change Control node, which you use to perform many of the GPO management tasks, appears in the Group Policy Management Console only if you install the AGPM Client.</span></span> <span data-ttu-id="3ae92-228">对于此方案，请在至少一台计算机上安装 AGPM 客户端。</span><span class="sxs-lookup"><span data-stu-id="3ae92-228">For this scenario, you install AGPM Client on at least one computer.</span></span> <span data-ttu-id="3ae92-229">无需在不执行组策略管理的最终用户的计算机上安装 AGPM 客户端。</span><span class="sxs-lookup"><span data-stu-id="3ae92-229">You do not need to install AGPM Client on the computers of end users who do not perform Group Policy administration.</span></span>

**<span data-ttu-id="3ae92-230">在组策略管理员的计算机上安装 AGPM 客户端</span><span class="sxs-lookup"><span data-stu-id="3ae92-230">To install AGPM Client on the computer of a Group Policy administrator</span></span>**

1.  <span data-ttu-id="3ae92-231">启动 Microsoft 桌面优化包 CD，然后按照屏幕上的说明选择 "**高级组策略管理-客户端**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-231">Start the Microsoft Desktop Optimization Pack CD and follow the instructions on screen to select **Advanced Group Policy Management - Client**.</span></span>

2.  <span data-ttu-id="3ae92-232">在 "**欢迎**" 对话框中，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-232">In the **Welcome** dialog box, click **Next**.</span></span>

3.  <span data-ttu-id="3ae92-233">在 " **Microsoft 软件许可条款**" 对话框中，接受条款，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-233">In the **Microsoft Software License Terms** dialog box, accept the terms and then click **Next**.</span></span>

4.  <span data-ttu-id="3ae92-234">在 "**应用程序路径**" 对话框中，选择要在其中安装 AGPM 客户端的位置。</span><span class="sxs-lookup"><span data-stu-id="3ae92-234">In the **Application Path** dialog box, select a location in which to install AGPM Client.</span></span> <span data-ttu-id="3ae92-235">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3ae92-235">Click **Next**.</span></span>

5.  <span data-ttu-id="3ae92-236">在 " **AGPM 服务器**" 对话框中，键入 AGPM 服务器的 DNS 名称或 IP 地址以及要连接到的端口。</span><span class="sxs-lookup"><span data-stu-id="3ae92-236">In the **AGPM Server** dialog box, type the DNS name or IP address for the AGPM Server and the port to which you want to connect.</span></span> <span data-ttu-id="3ae92-237">AGPM 服务的默认端口为4600。</span><span class="sxs-lookup"><span data-stu-id="3ae92-237">The default port for the AGPM Service is 4600.</span></span> <span data-ttu-id="3ae92-238">不要清除 "**通过防火墙允许 Microsoft 管理控制台**" 复选框，除非手动配置端口例外或使用规则配置端口例外。</span><span class="sxs-lookup"><span data-stu-id="3ae92-238">Do not clear the **Allow Microsoft Management Console through the firewall** check box unless you manually configure port exceptions or use rules to configure port exceptions.</span></span> <span data-ttu-id="3ae92-239">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3ae92-239">Click **Next**.</span></span>

6.  <span data-ttu-id="3ae92-240">在 "**语言**" 对话框中，选择要为 AGPM 客户端安装的一个或多个显示语言。</span><span class="sxs-lookup"><span data-stu-id="3ae92-240">In the **Languages** dialog box, select one or more display languages to install for AGPM Client.</span></span>

7.  <span data-ttu-id="3ae92-241">单击 "**安装**"，然后单击 "**完成**" 退出设置向导。</span><span class="sxs-lookup"><span data-stu-id="3ae92-241">Click **Install**, and then click **Finish** to exit the Setup Wizard.</span></span>

### <a href="" id="bkmk-config3"></a><span data-ttu-id="3ae92-242">步骤3：配置 AGPM 服务器连接</span><span class="sxs-lookup"><span data-stu-id="3ae92-242">Step 3: Configure an AGPM Server connection</span></span>

<span data-ttu-id="3ae92-243">AGPM 存储每个受控制的组策略对象（GPO）的所有版本，即 AGPM 在中心存档中提供更改控制的每个 GPO。</span><span class="sxs-lookup"><span data-stu-id="3ae92-243">AGPM stores all versions of each controlled Group Policy Object (GPO), that is, each GPO for which AGPM provides change control, in a central archive.</span></span> <span data-ttu-id="3ae92-244">这样，组策略管理员可以在不立即影响每个 GPO 的已部署版本的情况下查看和更改 Gpo。</span><span class="sxs-lookup"><span data-stu-id="3ae92-244">This lets Group Policy administrators view and change GPOs offline without immediately affecting the deployed version of each GPO.</span></span>

<span data-ttu-id="3ae92-245">在此步骤中，配置 AGPM 服务器连接并确保所有组策略管理员都连接到同一 AGPM 服务器。</span><span class="sxs-lookup"><span data-stu-id="3ae92-245">In this step, you configure an AGPM Server connection and ensure that all Group Policy administrators connect to the same AGPM Server.</span></span> <span data-ttu-id="3ae92-246">（有关如何配置多台 AGPM 服务器的信息，请参阅高级组策略管理的帮助。）</span><span class="sxs-lookup"><span data-stu-id="3ae92-246">(For information about how to configure multiple AGPM Servers, see Help for Advanced Group Policy Management.)</span></span>

**<span data-ttu-id="3ae92-247">为所有组策略管理员配置 AGPM 服务器连接</span><span class="sxs-lookup"><span data-stu-id="3ae92-247">To configure an AGPM Server connection for all Group Policy administrators</span></span>**

1.  <span data-ttu-id="3ae92-248">在已安装了 AGPM 客户端的计算机上，使用你选择作为存档所有者的用户帐户登录。</span><span class="sxs-lookup"><span data-stu-id="3ae92-248">On a computer on which you have installed AGPM Client, log on with the user account that you selected as the Archive Owner.</span></span> <span data-ttu-id="3ae92-249">此用户具有 AGPM 管理员的角色（"完全控制"）。</span><span class="sxs-lookup"><span data-stu-id="3ae92-249">This user has the role of AGPM Administrator (Full Control).</span></span>

2.  <span data-ttu-id="3ae92-250">单击 "**开始**"，指向 "**管理工具**"，然后单击 "**组策略管理**" 以打开 GPMC。</span><span class="sxs-lookup"><span data-stu-id="3ae92-250">Click **Start**, point to **Administrative Tools**, and then click **Group Policy Management** to open the GPMC.</span></span>

3.  <span data-ttu-id="3ae92-251">编辑应用到所有组策略管理员的 GPO。</span><span class="sxs-lookup"><span data-stu-id="3ae92-251">Edit a GPO that is applied to all Group Policy administrators.</span></span>

4.  <span data-ttu-id="3ae92-252">在 "**组策略管理编辑器**" 窗口中，双击 **"用户配置**"、"**策略**"、"**管理模板**"、" **Windows 组件**" 和 " **AGPM**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-252">In the **Group Policy Management Editor** window, double-click **User Configuration**, **Policies**, **Administrative Templates**, **Windows Components**, and **AGPM**.</span></span>

5.  <span data-ttu-id="3ae92-253">在 "详细信息" 窗格中，双击 " **AGPM：指定默认 Agpm 服务器（所有域）**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-253">In the details pane, double-click **AGPM: Specify default AGPM Server (all domains)**.</span></span>

6.  <span data-ttu-id="3ae92-254">在 "**属性**" 窗口中，选择 "**已启用**"，然后为托管存档的服务器键入 DNS 名称或 IP 地址以及端口（例如， **server.contoso.com:4600**）。</span><span class="sxs-lookup"><span data-stu-id="3ae92-254">In the **Properties** window, select **Enabled** and type the DNS name or IP address and port (for example, **server.contoso.com:4600**) for the server hosting the archive.</span></span> <span data-ttu-id="3ae92-255">默认情况下，AGPM 服务使用端口4600。</span><span class="sxs-lookup"><span data-stu-id="3ae92-255">By default, the AGPM Service uses port 4600.</span></span>

7.  <span data-ttu-id="3ae92-256">单击 **"确定**"，然后关闭 "**组策略管理编辑器**" 窗口。</span><span class="sxs-lookup"><span data-stu-id="3ae92-256">Click **OK**, and then close the **Group Policy Management Editor** window.</span></span> <span data-ttu-id="3ae92-257">更新组策略时，将为每个组策略管理员配置 AGPM 服务器连接。</span><span class="sxs-lookup"><span data-stu-id="3ae92-257">When Group Policy is updated, the AGPM Server connection is configured for each Group Policy administrator.</span></span>

### <a href="" id="bkmk-config4"></a><span data-ttu-id="3ae92-258">步骤4：配置电子邮件通知</span><span class="sxs-lookup"><span data-stu-id="3ae92-258">Step 4: Configure e-mail notification</span></span>

<span data-ttu-id="3ae92-259">作为 AGPM 管理员（完全控制），你可以指定在编辑者尝试创建、部署或删除 GPO 时，将向其发送包含请求的电子邮件的审批者和 AGPM 管理员的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="3ae92-259">As an AGPM Administrator (Full Control), you designate the e-mail addresses of Approvers and AGPM Administrators to whom an e-mail message that contains a request is sent when an Editor tries to create, deploy, or delete a GPO.</span></span> <span data-ttu-id="3ae92-260">您还可以确定发送这些邮件的别名。</span><span class="sxs-lookup"><span data-stu-id="3ae92-260">You also determine the alias from which these messages are sent.</span></span>

**<span data-ttu-id="3ae92-261">配置 AGPM 的电子邮件通知</span><span class="sxs-lookup"><span data-stu-id="3ae92-261">To configure e-mail notification for AGPM</span></span>**

1.  <span data-ttu-id="3ae92-262">在**组策略管理编辑器**中，导航到 "**更改控制**" 文件夹</span><span class="sxs-lookup"><span data-stu-id="3ae92-262">In **Group Policy Management Editor** , navigate to the **Change Control** folder</span></span> 

2.  <span data-ttu-id="3ae92-263">在 "详细信息" 窗格中，单击 "**域委派**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="3ae92-263">In the details pane, click the **Domain Delegation** tab.</span></span>

3.  <span data-ttu-id="3ae92-264">在 "**发件人电子邮件地址**" 字段中，键入要从中发送通知的 AGPM 的电子邮件别名。</span><span class="sxs-lookup"><span data-stu-id="3ae92-264">In the **From e-mail address** field, type the e-mail alias for AGPM from which notifications should be sent.</span></span>

4.  <span data-ttu-id="3ae92-265">在 "**收件人电子邮件地址**" 字段中，键入要向其分配审批者角色的用户帐户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="3ae92-265">In the **To e-mail address** field, type the e-mail address for the user account to which you intend to assign the Approver role.</span></span>

5.  <span data-ttu-id="3ae92-266">在 " **SMTP 服务器**" 字段中，键入有效的 SMTP 邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="3ae92-266">In the **SMTP server** field, type a valid SMTP mail server.</span></span>

6.  <span data-ttu-id="3ae92-267">在 "**用户名**" 和 "**密码**" 字段中，键入有权访问 SMTP 服务的用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="3ae92-267">In the **User name** and **Password** fields, type the credentials of a user who has access to the SMTP service.</span></span> <span data-ttu-id="3ae92-268">单击**应用**。</span><span class="sxs-lookup"><span data-stu-id="3ae92-268">Click **Apply**.</span></span>

### <a href="" id="bkmk-config5"></a><span data-ttu-id="3ae92-269">步骤5：代理访问</span><span class="sxs-lookup"><span data-stu-id="3ae92-269">Step 5: Delegate access</span></span>

<span data-ttu-id="3ae92-270">作为 AGPM 管理员（完全控制），你可以委派域级别对 Gpo 的访问权限，并为每个组策略管理员的帐户分配角色。</span><span class="sxs-lookup"><span data-stu-id="3ae92-270">As an AGPM Administrator (Full Control), you delegate domain-level access to GPOs, assigning roles to the account of each Group Policy administrator.</span></span>

<span data-ttu-id="3ae92-271">**注意** 你还可以在 GPO 级别（而不是域级别）委派访问权限。</span><span class="sxs-lookup"><span data-stu-id="3ae92-271">**Note** You can also delegate access at the GPO level instead of the domain level.</span></span> <span data-ttu-id="3ae92-272">有关详细信息，请参阅高级组策略管理的帮助。</span><span class="sxs-lookup"><span data-stu-id="3ae92-272">For more information, see Help for Advanced Group Policy Management.</span></span>

 

<span data-ttu-id="3ae92-273">**重要提示** 应限制 "组策略创建者所有者" 组中的成员身份，以便它不能用于绕过对 Gpo 的访问的 AGPM 管理。</span><span class="sxs-lookup"><span data-stu-id="3ae92-273">**Important** You should restrict membership in the Group Policy Creator Owners group so that it cannot be used to circumvent AGPM management of access to GPOs.</span></span> <span data-ttu-id="3ae92-274">（在**组策略管理控制台**中，单击要在其中管理 gpo 的林和域中的 "**组策略对象**"，单击 "**委派**"，然后配置设置以满足组织的需要。）</span><span class="sxs-lookup"><span data-stu-id="3ae92-274">(In the **Group Policy Management Console**, click **Group Policy Objects** in the forest and domain in which you want to manage GPOs, click **Delegation**, and then configure the settings to meet the needs of your organization.)</span></span>

 

**<span data-ttu-id="3ae92-275">委派对整个域中的所有 Gpo 的访问权限</span><span class="sxs-lookup"><span data-stu-id="3ae92-275">To delegate access to all GPOs throughout a domain</span></span>**

1.  <span data-ttu-id="3ae92-276">在 "**域委派**" 选项卡上，单击 "**添加**" 按钮，选择要用作审批者的组策略管理员的用户帐户，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="3ae92-276">On the **Domain Delegation** tab, click the **Add** button, select the user account of the Group Policy administrator to serve as Approver, and then click **OK**.</span></span>

2.  <span data-ttu-id="3ae92-277">在 "**添加组或用户**" 对话框中，选择要向帐户分配该角色的**审批者**角色，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="3ae92-277">In the **Add Group or User** dialog box, select the **Approver** role to assign that role to the account, and then click **OK**.</span></span> <span data-ttu-id="3ae92-278">（此角色包括审阅者角色。）</span><span class="sxs-lookup"><span data-stu-id="3ae92-278">(This role includes the Reviewer role.)</span></span>

3.  <span data-ttu-id="3ae92-279">单击 "**添加**" 按钮，选择组策略管理员作为编辑器的用户帐户，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="3ae92-279">Click the **Add** button, select the user account of the Group Policy administrator to serve as Editor, and then click **OK**.</span></span>

4.  <span data-ttu-id="3ae92-280">在 "**添加组或用户**" 对话框中，选择要向帐户分配该角色的 "**编辑**者" 角色，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="3ae92-280">In the **Add Group or User** dialog box, select the **Editor** role to assign that role to the account, and then click **OK**.</span></span> <span data-ttu-id="3ae92-281">（此角色包括审阅者角色。）</span><span class="sxs-lookup"><span data-stu-id="3ae92-281">(This role includes the Reviewer role.)</span></span>

5.  <span data-ttu-id="3ae92-282">单击 "**添加**" 按钮，选择组策略管理员充当审阅者的用户帐户，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="3ae92-282">Click the **Add** button, select the user account of the Group Policy administrator to serve as Reviewer, and then click **OK**.</span></span>

6.  <span data-ttu-id="3ae92-283">在 "**添加组" 或 "用户**" 对话框中，选择**审阅者**角色以仅将该角色分配给帐户。</span><span class="sxs-lookup"><span data-stu-id="3ae92-283">In the **Add Group or User** dialog box, select the **Reviewer** role to assign only that role to the account.</span></span>

## <span data-ttu-id="3ae92-284">管理 Gpo 的步骤</span><span class="sxs-lookup"><span data-stu-id="3ae92-284">Steps for managing GPOs</span></span>


<span data-ttu-id="3ae92-285">必须完成以下步骤才能使用 AGPM 创建、编辑、审阅和部署 Gpo。</span><span class="sxs-lookup"><span data-stu-id="3ae92-285">You must complete the following steps to create, edit, review, and deploy GPOs by using AGPM.</span></span> <span data-ttu-id="3ae92-286">此外，你将创建一个模板，删除 GPO，然后还原已删除的 GPO。</span><span class="sxs-lookup"><span data-stu-id="3ae92-286">Additionally, you will create a template, delete a GPO, and restore a deleted GPO.</span></span>

[<span data-ttu-id="3ae92-287">步骤1：创建 GPO</span><span class="sxs-lookup"><span data-stu-id="3ae92-287">Step 1: Create a GPO</span></span>](#bkmk-manage1)

[<span data-ttu-id="3ae92-288">步骤2：编辑 GPO</span><span class="sxs-lookup"><span data-stu-id="3ae92-288">Step 2: Edit a GPO</span></span>](#bkmk-manage2)

[<span data-ttu-id="3ae92-289">步骤3：查看和部署 GPO</span><span class="sxs-lookup"><span data-stu-id="3ae92-289">Step 3: Review and deploy a GPO</span></span>](#bkmk-manage3)

[<span data-ttu-id="3ae92-290">步骤4：使用模板创建 GPO</span><span class="sxs-lookup"><span data-stu-id="3ae92-290">Step 4: Use a template to create a GPO</span></span>](#bkmk-manage4)

[<span data-ttu-id="3ae92-291">步骤5：删除和还原 GPO</span><span class="sxs-lookup"><span data-stu-id="3ae92-291">Step 5: Delete and restore a GPO</span></span>](#bkmk-manage5)

### <a href="" id="bkmk-manage1"></a><span data-ttu-id="3ae92-292">步骤1：创建 GPO</span><span class="sxs-lookup"><span data-stu-id="3ae92-292">Step 1: Create a GPO</span></span>

<span data-ttu-id="3ae92-293">在具有多个组策略管理员的环境中，具有编辑器角色的环境可以请求创建新的 Gpo。</span><span class="sxs-lookup"><span data-stu-id="3ae92-293">In an environment that has multiple Group Policy administrators, those with the Editor role can request that new GPOs be created.</span></span> <span data-ttu-id="3ae92-294">但是，该请求必须由拥有审批者角色的人员批准。</span><span class="sxs-lookup"><span data-stu-id="3ae92-294">However, that request must be approved by someone with the Approver role.</span></span>

<span data-ttu-id="3ae92-295">在此步骤中，使用具有编辑器角色的帐户以请求创建新的 GPO。</span><span class="sxs-lookup"><span data-stu-id="3ae92-295">In this step, you use an account that has the Editor role to request that a new GPO be created.</span></span> <span data-ttu-id="3ae92-296">使用具有审批者角色的帐户，批准此请求以创建 GPO。</span><span class="sxs-lookup"><span data-stu-id="3ae92-296">Using an account that has the Approver role, you approve this request to create the GPO.</span></span>

**<span data-ttu-id="3ae92-297">请求通过 AGPM 创建和管理新的 GPO</span><span class="sxs-lookup"><span data-stu-id="3ae92-297">To request that a new GPO be created and managed through AGPM</span></span>**

1.  <span data-ttu-id="3ae92-298">在已安装了 AGPM 客户端的计算机上，使用分配了 AGPM 中的编辑器角色的用户帐户登录。</span><span class="sxs-lookup"><span data-stu-id="3ae92-298">On a computer on which you have installed AGPM Client, log on with a user account that is assigned the Editor role in AGPM.</span></span>

2.  <span data-ttu-id="3ae92-299">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-299">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

3.  <span data-ttu-id="3ae92-300">右键单击 "**更改控制**" 节点，然后单击 "**新建受控 GPO**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-300">Right-click the **Change Control** node, and then click **New Controlled GPO**.</span></span>

4.  <span data-ttu-id="3ae92-301">在 "**新建受控 GPO** " 对话框中：</span><span class="sxs-lookup"><span data-stu-id="3ae92-301">In the **New Controlled GPO** dialog box:</span></span>

    1.  <span data-ttu-id="3ae92-302">若要接收请求的副本，请在 "**抄送**" 字段中键入您的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="3ae92-302">To receive a copy of the request, type your e-mail address in the **Cc** field.</span></span>

    2.  <span data-ttu-id="3ae92-303">键入**MyGPO**作为新 GPO 的名称。</span><span class="sxs-lookup"><span data-stu-id="3ae92-303">Type **MyGPO** as the name for the new GPO.</span></span>

    3.  <span data-ttu-id="3ae92-304">键入新 GPO 的注释。</span><span class="sxs-lookup"><span data-stu-id="3ae92-304">Type a comment for the new GPO.</span></span>

    4.  <span data-ttu-id="3ae92-305">单击 "**创建实时**"，以便在批准后立即将新的 GPO 部署到生产环境。</span><span class="sxs-lookup"><span data-stu-id="3ae92-305">Click **Create live** so that the new GPO will be deployed to the production environment immediately upon approval.</span></span> <span data-ttu-id="3ae92-306">单击**提交**。</span><span class="sxs-lookup"><span data-stu-id="3ae92-306">Click **Submit**.</span></span>

5.  <span data-ttu-id="3ae92-307">当**AGPM 进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-307">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="3ae92-308">新的 GPO 将显示在 "**挂起**" 选项卡上。</span><span class="sxs-lookup"><span data-stu-id="3ae92-308">The new GPO is displayed on the **Pending** tab.</span></span>

**<span data-ttu-id="3ae92-309">批准创建 GPO 的挂起请求</span><span class="sxs-lookup"><span data-stu-id="3ae92-309">To approve the pending request to create a GPO</span></span>**

1.  <span data-ttu-id="3ae92-310">在已安装了 AGPM 客户端的计算机上，使用具有 AGPM 中审批者角色的用户帐户登录。</span><span class="sxs-lookup"><span data-stu-id="3ae92-310">On a computer on which you have installed AGPM Client, log on with a user account that has the role of Approver in AGPM.</span></span>

2.  <span data-ttu-id="3ae92-311">打开该帐户的电子邮件收件箱，请注意，您已收到一个来自 AGPM 别名的电子邮件，其中包含用于创建 GPO 的编辑器请求。</span><span class="sxs-lookup"><span data-stu-id="3ae92-311">Open the e-mail inbox for the account, and notice that you have received an e-mail message from the AGPM alias with the Editor's request to create a GPO.</span></span>

3.  <span data-ttu-id="3ae92-312">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-312">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

4.  <span data-ttu-id="3ae92-313">在 "**目录**" 选项卡上，单击 "**挂起**" 选项卡以显示 "挂起的 gpo"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-313">On the **Contents** tab, click the **Pending** tab to display the pending GPOs.</span></span>

5.  <span data-ttu-id="3ae92-314">右键单击 " **MyGPO**"，然后单击 "**批准**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-314">Right-click **MyGPO**, and then click **Approve**.</span></span>

6.  <span data-ttu-id="3ae92-315">单击 **"是"** 确认审批，并将 GPO 移动到 "已**控制**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="3ae92-315">Click **Yes** to confirm approval and move the GPO to the **Controlled** tab.</span></span>

### <a href="" id="bkmk-manage2"></a><span data-ttu-id="3ae92-316">步骤2：编辑 GPO</span><span class="sxs-lookup"><span data-stu-id="3ae92-316">Step 2: Edit a GPO</span></span>

<span data-ttu-id="3ae92-317">你可以使用 Gpo 配置计算机或用户设置，并将其部署到多台计算机或用户。</span><span class="sxs-lookup"><span data-stu-id="3ae92-317">You can use GPOs to configure computer or user settings and deploy them to many computers or users.</span></span> <span data-ttu-id="3ae92-318">在此步骤中，你使用具有编辑器角色的帐户从存档中签出 GPO，脱机编辑 GPO，将已编辑的 GPO 签入存档，并向生产环境请求 GPO 部署。</span><span class="sxs-lookup"><span data-stu-id="3ae92-318">In this step, you use an account that has the Editor role to check out a GPO from the archive, edit the GPO offline, check the edited GPO into the archive, and request deployment of the GPO to the production environment.</span></span> <span data-ttu-id="3ae92-319">在这种情况下，你可以在 GPO 中配置一个设置，要求密码长度至少为八个字符。</span><span class="sxs-lookup"><span data-stu-id="3ae92-319">For this scenario, you configure a setting in the GPO to require that the password be at least eight characters long.</span></span>

**<span data-ttu-id="3ae92-320">从存档中签出 GPO 以进行编辑</span><span class="sxs-lookup"><span data-stu-id="3ae92-320">To check the GPO out from the archive for editing</span></span>**

1.  <span data-ttu-id="3ae92-321">在已安装了 AGPM 客户端的计算机上，使用在 AGPM 中具有 "编辑者" 角色的用户帐户登录。</span><span class="sxs-lookup"><span data-stu-id="3ae92-321">On a computer on which you have installed AGPM Client, log on with a user account that has the role of Editor in AGPM.</span></span>

2.  <span data-ttu-id="3ae92-322">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-322">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

3.  <span data-ttu-id="3ae92-323">在 "详细信息" 窗格中的 "**目录**" 选项卡上，单击 "**受控**" 选项卡以显示受控 gpo。</span><span class="sxs-lookup"><span data-stu-id="3ae92-323">On the **Contents** tab in the details pane, click the **Controlled** tab to display the controlled GPOs.</span></span>

4.  <span data-ttu-id="3ae92-324">右键单击 " **MyGPO**"，然后单击 "**签出**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-324">Right-click **MyGPO**, and then click **Check Out**.</span></span>

5.  <span data-ttu-id="3ae92-325">键入要在已签出的 GPO 的历史记录中显示的注释，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="3ae92-325">Type a comment to be displayed in the history of the GPO while it is checked out, and then click **OK**.</span></span>

6.  <span data-ttu-id="3ae92-326">当**AGPM 进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-326">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="3ae92-327">在 "**受控**" 选项卡上，将 GPO 的状态标识为 "**已签出**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-327">On the **Controlled** tab, the state of the GPO is identified as **Checked Out**.</span></span>

**<span data-ttu-id="3ae92-328">脱机编辑 GPO 并配置最小密码长度</span><span class="sxs-lookup"><span data-stu-id="3ae92-328">To edit the GPO offline and configure the minimum password length</span></span>**

1.  <span data-ttu-id="3ae92-329">在 "**受控**" 选项卡上，右键单击 " **MyGPO**"，然后单击 "**编辑**" 以打开 "**组策略管理编辑器**" 窗口，并更改该 GPO 的脱机副本。</span><span class="sxs-lookup"><span data-stu-id="3ae92-329">On the **Controlled** tab, right-click **MyGPO**, and then click **Edit** to open the **Group Policy Management Editor** window and change an offline copy of the GPO.</span></span> <span data-ttu-id="3ae92-330">对于此方案，请配置最小密码长度：</span><span class="sxs-lookup"><span data-stu-id="3ae92-330">For this scenario, configure the minimum password length:</span></span>

    1.  <span data-ttu-id="3ae92-331">在 "**计算机配置**" 下，双击 "**策略**"、" **Windows 设置**"、"**安全设置**"、"**帐户策略**" 和 "**密码策略**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-331">Under **Computer Configuration**, double-click **Policies**, **Windows Settings**, **Security Settings**, **Account Policies**, and **Password Policy**.</span></span>

    2.  <span data-ttu-id="3ae92-332">在 "详细信息" 窗格中，双击 "**最小密码长度**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-332">In the details pane, double-click **Minimum password length**.</span></span>

    3.  <span data-ttu-id="3ae92-333">在 "属性" 窗口中，选中 "**定义此策略设置**" 复选框，将字符数设置为**8**，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="3ae92-333">In the properties window, select the **Define this policy setting** check box, set the number of characters to **8**, and then click **OK**.</span></span>

2.  <span data-ttu-id="3ae92-334">关闭 "**组策略管理编辑器**" 窗口。</span><span class="sxs-lookup"><span data-stu-id="3ae92-334">Close the **Group Policy Management Editor** window.</span></span>

**<span data-ttu-id="3ae92-335">将 GPO 签入存档</span><span class="sxs-lookup"><span data-stu-id="3ae92-335">To check the GPO into the archive</span></span>**

1.  <span data-ttu-id="3ae92-336">在 "**受控**" 选项卡上，右键单击 " **MyGPO** "，然后单击 "**签入**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-336">On the **Controlled** tab, right-click **MyGPO** and then click **Check In**.</span></span>

2.  <span data-ttu-id="3ae92-337">键入批注，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="3ae92-337">Type a comment, and then click **OK**.</span></span>

3.  <span data-ttu-id="3ae92-338">当**AGPM 进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-338">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="3ae92-339">在 "**受控**" 选项卡上，将 GPO 的状态标识为 **"已签入**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-339">On the **Controlled** tab, the state of the GPO is identified as **Checked In**.</span></span>

**<span data-ttu-id="3ae92-340">请求将 GPO 部署到生产环境</span><span class="sxs-lookup"><span data-stu-id="3ae92-340">To request the deployment of the GPO to the production environment</span></span>**

1.  <span data-ttu-id="3ae92-341">在 "**受控**" 选项卡上，右键单击 " **MyGPO** "，然后单击 "**部署**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-341">On the **Controlled** tab, right-click **MyGPO** and then click **Deploy**.</span></span>

2.  <span data-ttu-id="3ae92-342">由于此帐户不是审批者或 AGPM 管理员，因此必须提交部署请求。</span><span class="sxs-lookup"><span data-stu-id="3ae92-342">Because this account is not an Approver or AGPM Administrator, you must submit a request for deployment.</span></span> <span data-ttu-id="3ae92-343">若要接收请求的副本，请在 "**抄送**" 字段中键入您的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="3ae92-343">To receive a copy of the request, type your e-mail address in the **Cc** field.</span></span> <span data-ttu-id="3ae92-344">键入要在 GPO 的历史记录中显示的注释，然后单击 "**提交**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-344">Type a comment to be displayed in the history of the GPO, and then click **Submit**.</span></span>

3.  <span data-ttu-id="3ae92-345">当**AGPM 进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-345">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="3ae92-346">**MyGPO**将显示在 "**挂起**" 选项卡上的 gpo 列表中。</span><span class="sxs-lookup"><span data-stu-id="3ae92-346">**MyGPO** is displayed on the list of GPOs on the **Pending** tab.</span></span>

### <a href="" id="bkmk-manage3"></a><span data-ttu-id="3ae92-347">步骤3：查看和部署 GPO</span><span class="sxs-lookup"><span data-stu-id="3ae92-347">Step 3: Review and deploy a GPO</span></span>

<span data-ttu-id="3ae92-348">在此步骤中，你充当审批者，创建报表和分析 GPO 中的设置以及对设置的更改，以确定是否应批准这些设置。</span><span class="sxs-lookup"><span data-stu-id="3ae92-348">In this step, you act as an Approver, creating reports and analyzing the settings and changes to settings in the GPO to determine whether you should approve them.</span></span> <span data-ttu-id="3ae92-349">评估 GPO 后，将其部署到生产环境，并将 GPO 链接到域或组织单位（OU）。</span><span class="sxs-lookup"><span data-stu-id="3ae92-349">After you evaluate the GPO, you deploy it to the production environment and link the GPO to a domain or an organizational unit (OU).</span></span> <span data-ttu-id="3ae92-350">当为该域或 OU 中的计算机刷新组策略时，GPO 将生效。</span><span class="sxs-lookup"><span data-stu-id="3ae92-350">The GPO takes effect when Group Policy is refreshed for computers in that domain or OU.</span></span>

**<span data-ttu-id="3ae92-351">查看 GPO 中的设置</span><span class="sxs-lookup"><span data-stu-id="3ae92-351">To review settings in the GPO</span></span>**

1. <span data-ttu-id="3ae92-352">在安装了 AGPM 客户端的计算机上，使用为 AGPM 中的审批者角色分配的用户帐户进行登录。</span><span class="sxs-lookup"><span data-stu-id="3ae92-352">On a computer on which you have installed AGPM Client, log on with a user account that is assigned the role of Approver in AGPM.</span></span> <span data-ttu-id="3ae92-353">任何具有审阅者角色（包括在所有其他角色中）的组策略管理员都可以查看 GPO 中的设置。</span><span class="sxs-lookup"><span data-stu-id="3ae92-353">Any Group Policy administrator with the Reviewer role, which is included in all of the other roles, can review the settings in a GPO.</span></span>

2. <span data-ttu-id="3ae92-354">打开帐户的电子邮件收件箱，请注意，你已收到来自 AGPM 别名的电子邮件，其中包含用于部署 GPO 的编辑器请求。</span><span class="sxs-lookup"><span data-stu-id="3ae92-354">Open the e-mail inbox for the account and notice that you have received an e-mail message from the AGPM alias with an Editor's request to deploy a GPO.</span></span>

3. <span data-ttu-id="3ae92-355">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-355">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

4. <span data-ttu-id="3ae92-356">在 "详细信息" 窗格中的 "**目录**" 选项卡上，单击 "**挂起**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="3ae92-356">On the **Contents** tab in the details pane, click the **Pending** tab.</span></span>

5. <span data-ttu-id="3ae92-357">双击 " **MyGPO** " 以显示其历史记录。</span><span class="sxs-lookup"><span data-stu-id="3ae92-357">Double-click **MyGPO** to display its history.</span></span>

6. <span data-ttu-id="3ae92-358">查看最新版本的 MyGPO 中的设置：</span><span class="sxs-lookup"><span data-stu-id="3ae92-358">Review the settings in the most recent version of MyGPO:</span></span>

   1.  <span data-ttu-id="3ae92-359">在 "**历史记录**" 窗口中，右键单击具有最近时间戳的 GPO 版本，单击 "**设置**"，然后单击 " **HTML 报表**" 以显示该 gpo 的设置摘要。</span><span class="sxs-lookup"><span data-stu-id="3ae92-359">In the **History** window, right-click the GPO version with the most recent time stamp, click **Settings**, and then click **HTML Report** to display a summary of the GPO's settings.</span></span>

   2.  <span data-ttu-id="3ae92-360">在 Web 浏览器中，单击 "**全部显示**" 以显示 GPO 中的所有设置。</span><span class="sxs-lookup"><span data-stu-id="3ae92-360">In the Web browser, click **show all** to display all the settings in the GPO.</span></span> <span data-ttu-id="3ae92-361">关闭浏览器。</span><span class="sxs-lookup"><span data-stu-id="3ae92-361">Close the browser.</span></span>

7. <span data-ttu-id="3ae92-362">将最新版本的 MyGPO 与签入到存档中的第一个版本进行比较：</span><span class="sxs-lookup"><span data-stu-id="3ae92-362">Compare the most recent version of MyGPO to the first version checked in to the archive:</span></span>

   1. <span data-ttu-id="3ae92-363">在 "**历史记录**" 窗口中，单击具有最新时间戳的 GPO 版本。</span><span class="sxs-lookup"><span data-stu-id="3ae92-363">In the **History** window, click the GPO version with the most recent time stamp.</span></span> <span data-ttu-id="3ae92-364">按 CTRL，然后单击**计算机版本**不是 \* \* \\ \* \* \* 的最旧 GPO 版本。</span><span class="sxs-lookup"><span data-stu-id="3ae92-364">Press CTRL and then click the oldest GPO version for which the **Computer Version** is not \*\*\\*\*\*.</span></span>

   2. <span data-ttu-id="3ae92-365">单击 "**差异**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="3ae92-365">Click the **Differences** button.</span></span> <span data-ttu-id="3ae92-366">"**帐户策略/密码策略**" 部分以绿色突出显示，并以 " \**+ \**" 开头。</span><span class="sxs-lookup"><span data-stu-id="3ae92-366">The **Account Policies/Password Policy** section is highlighted in green and preceded by **\[+\]**.</span></span> <span data-ttu-id="3ae92-367">这表示仅在 GPO 的后一版本中配置该设置。</span><span class="sxs-lookup"><span data-stu-id="3ae92-367">This indicates that the setting is configured only in the latter version of the GPO.</span></span>

   3. <span data-ttu-id="3ae92-368">单击 "**帐户策略/密码策略**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-368">Click **Account Policies/Password Policy**.</span></span> <span data-ttu-id="3ae92-369">"**最小密码长度**" 设置也将以绿色突出显示，并以 " \**+ \**" 开头，以指示它仅在 GPO 的后版本中进行配置。</span><span class="sxs-lookup"><span data-stu-id="3ae92-369">The **Minimum password length** setting is also highlighted in green and preceded by **\[+\]**, indicating that it is configured only in the latter version of the GPO.</span></span>

   4. <span data-ttu-id="3ae92-370">关闭 Web 浏览器。</span><span class="sxs-lookup"><span data-stu-id="3ae92-370">Close the Web browser.</span></span>

**<span data-ttu-id="3ae92-371">将 GPO 部署到生产环境</span><span class="sxs-lookup"><span data-stu-id="3ae92-371">To deploy the GPO to the production environment</span></span>**

1.  <span data-ttu-id="3ae92-372">在 "**挂起**" 选项卡上，右键单击 " **MyGPO** "，然后单击 "**批准**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-372">On the **Pending** tab, right-click **MyGPO** and then click **Approve**.</span></span>

2.  <span data-ttu-id="3ae92-373">键入要包含在 GPO 历史记录中的注释。</span><span class="sxs-lookup"><span data-stu-id="3ae92-373">Type a comment to include in the history of the GPO.</span></span>

3.  <span data-ttu-id="3ae92-374">单击**是**。</span><span class="sxs-lookup"><span data-stu-id="3ae92-374">Click **Yes**.</span></span> <span data-ttu-id="3ae92-375">当**AGPM 进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-375">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="3ae92-376">GPO 已部署到生产环境。</span><span class="sxs-lookup"><span data-stu-id="3ae92-376">The GPO is deployed to the production environment.</span></span>

**<span data-ttu-id="3ae92-377">将 GPO 链接到域或组织单位</span><span class="sxs-lookup"><span data-stu-id="3ae92-377">To link the GPO to a domain or organizational unit</span></span>**

1.  <span data-ttu-id="3ae92-378">在 GPMC 中，右键单击要对其应用所配置 GPO 的域或组织单位（OU），然后单击 "**链接现有 gpo**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-378">In the GPMC, right-click either the domain or an organizational unit (OU) to which you want to apply the GPO that you configured, and then click **Link an Existing GPO**.</span></span>

2.  <span data-ttu-id="3ae92-379">在 "**选择 GPO** " 对话框中，单击 " **MyGPO**"，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="3ae92-379">In the **Select GPO** dialog box, click **MyGPO**, and then click **OK**.</span></span>

### <a href="" id="bkmk-manage4"></a><span data-ttu-id="3ae92-380">步骤4：使用模板创建 GPO</span><span class="sxs-lookup"><span data-stu-id="3ae92-380">Step 4: Use a template to create a GPO</span></span>

<span data-ttu-id="3ae92-381">在此步骤中，使用具有编辑器角色的帐户创建和使用模板。</span><span class="sxs-lookup"><span data-stu-id="3ae92-381">In this step, you use an account that has the Editor role to create and use a template.</span></span> <span data-ttu-id="3ae92-382">该模板是 GPO 的静态版本，用作创建新 Gpo 的起始点。</span><span class="sxs-lookup"><span data-stu-id="3ae92-382">That template is a static version of a GPO for use as a starting point for creating new GPOs.</span></span> <span data-ttu-id="3ae92-383">虽然您无法编辑模板，但您可以基于模板创建新的 GPO。</span><span class="sxs-lookup"><span data-stu-id="3ae92-383">Although you cannot edit a template, you can create a new GPO based on a template.</span></span> <span data-ttu-id="3ae92-384">模板对于快速创建包含许多相同策略设置的多个 Gpo 非常有用。</span><span class="sxs-lookup"><span data-stu-id="3ae92-384">Templates are useful for quickly creating multiple GPOs that include many of the same policy settings.</span></span>

**<span data-ttu-id="3ae92-385">基于现有 GPO 创建模板</span><span class="sxs-lookup"><span data-stu-id="3ae92-385">To create a template based on an existing GPO</span></span>**

1.  <span data-ttu-id="3ae92-386">在已安装了 AGPM 客户端的计算机上，使用在 AGPM 中分配有 "编辑者" 角色的用户帐户登录。</span><span class="sxs-lookup"><span data-stu-id="3ae92-386">On a computer on which you have installed AGPM Client, log on with a user account that is assigned the role of Editor in AGPM.</span></span>

2.  <span data-ttu-id="3ae92-387">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-387">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

3.  <span data-ttu-id="3ae92-388">在 "详细信息" 窗格中的 "**目录**" 选项卡上，单击 "**受控**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="3ae92-388">On the **Contents** tab in the details pane, click the **Controlled** tab.</span></span>

4.  <span data-ttu-id="3ae92-389">右键单击 " **MyGPO**"，然后单击 "**另存为模板**"，创建一个模板，其中包含当前在 MyGPO 中的所有设置。</span><span class="sxs-lookup"><span data-stu-id="3ae92-389">Right-click **MyGPO**, and then click **Save as Template** to create a template incorporating all settings currently in MyGPO.</span></span>

5.  <span data-ttu-id="3ae92-390">键入**MyTemplate**作为模板名称和注释，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="3ae92-390">Type **MyTemplate** as the name for the template and a comment, and then click **OK**.</span></span>

6.  <span data-ttu-id="3ae92-391">当**AGPM 进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-391">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="3ae92-392">新模板将显示在 "**模板**" 选项卡上。</span><span class="sxs-lookup"><span data-stu-id="3ae92-392">The new template appears on the **Templates** tab.</span></span>

**<span data-ttu-id="3ae92-393">请求通过 AGPM 创建和管理新的 GPO</span><span class="sxs-lookup"><span data-stu-id="3ae92-393">To request that a new GPO be created and managed through AGPM</span></span>**

1.  <span data-ttu-id="3ae92-394">单击 "**受控**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="3ae92-394">Click the **Controlled** tab.</span></span>

2.  <span data-ttu-id="3ae92-395">右键单击 "**更改控制**" 节点，然后单击 "**新建受控 GPO**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-395">Right-click the **Change Control** node, and then click **New Controlled GPO**.</span></span>

3.  <span data-ttu-id="3ae92-396">在 "**新建受控 GPO** " 对话框中：</span><span class="sxs-lookup"><span data-stu-id="3ae92-396">In the **New Controlled GPO** dialog box:</span></span>

    1.  <span data-ttu-id="3ae92-397">若要接收请求的副本，请在 "**抄送**" 字段中键入您的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="3ae92-397">To receive a copy of the request, type your e-mail address in the **Cc** field.</span></span>

    2.  <span data-ttu-id="3ae92-398">键入**MyOtherGPO**作为新 GPO 的名称。</span><span class="sxs-lookup"><span data-stu-id="3ae92-398">Type **MyOtherGPO** as the name for the new GPO.</span></span>

    3.  <span data-ttu-id="3ae92-399">键入新 GPO 的注释。</span><span class="sxs-lookup"><span data-stu-id="3ae92-399">Type a comment for the new GPO.</span></span>

    4.  <span data-ttu-id="3ae92-400">单击 "**创建实时**"，以便在批准后立即将新的 GPO 部署到生产环境。</span><span class="sxs-lookup"><span data-stu-id="3ae92-400">Click **Create live** so that the new GPO will be deployed to the production environment immediately upon approval.</span></span>

    5.  <span data-ttu-id="3ae92-401">**在 "来自 GPO 模板**" 中，选择 " **MyTemplate**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-401">For **From GPO template**, select **MyTemplate**.</span></span> <span data-ttu-id="3ae92-402">单击**提交**。</span><span class="sxs-lookup"><span data-stu-id="3ae92-402">Click **Submit**.</span></span>

4.  <span data-ttu-id="3ae92-403">当**AGPM 进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-403">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="3ae92-404">新的 GPO 将显示在 "**挂起**" 选项卡上。</span><span class="sxs-lookup"><span data-stu-id="3ae92-404">The new GPO is displayed on the **Pending** tab.</span></span>

<span data-ttu-id="3ae92-405">使用为审批者角色分配的帐户批准挂起的请求以创建 GPO （如步骤1中所执行的[操作）：创建 gpo](#bkmk-manage1)。</span><span class="sxs-lookup"><span data-stu-id="3ae92-405">Use an account that is assigned the role of Approver to approve the pending request to create the GPO as you did in [Step 1: Create a GPO](#bkmk-manage1).</span></span> <span data-ttu-id="3ae92-406">MyTemplate 包含您在 MyGPO 中配置的所有设置。</span><span class="sxs-lookup"><span data-stu-id="3ae92-406">MyTemplate incorporates all the settings that you configured in MyGPO.</span></span> <span data-ttu-id="3ae92-407">由于 MyOtherGPO 是使用 MyTemplate 创建的，因此它最初包含在创建 MyTemplate 时 MyGPO 包含的所有设置。</span><span class="sxs-lookup"><span data-stu-id="3ae92-407">Because MyOtherGPO was created using MyTemplate, it at first contains all the settings that MyGPO contained at the time that MyTemplate was created.</span></span> <span data-ttu-id="3ae92-408">你可以通过生成差异报表来将 MyOtherGPO 与 MyTemplate 进行比较来确认。</span><span class="sxs-lookup"><span data-stu-id="3ae92-408">You can confirm this by generating a difference report to compare MyOtherGPO to MyTemplate.</span></span>

**<span data-ttu-id="3ae92-409">从存档中签出 GPO 以进行编辑</span><span class="sxs-lookup"><span data-stu-id="3ae92-409">To check the GPO out from the archive for editing</span></span>**

1.  <span data-ttu-id="3ae92-410">在已安装了 AGPM 客户端的计算机上，使用在 AGPM 中分配有 "编辑者" 角色的用户帐户登录。</span><span class="sxs-lookup"><span data-stu-id="3ae92-410">On a computer on which you have installed AGPM Client, log on with a user account that is assigned the role of Editor in AGPM.</span></span>

2.  <span data-ttu-id="3ae92-411">右键单击 " **MyOtherGPO**"，然后单击 "**签出**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-411">Right-click **MyOtherGPO**, and then click **Check Out**.</span></span>

3.  <span data-ttu-id="3ae92-412">键入要在已签出的 GPO 的历史记录中显示的注释，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="3ae92-412">Type a comment to be displayed in the history of the GPO while it is checked out, and then click **OK**.</span></span>

4.  <span data-ttu-id="3ae92-413">当**AGPM 进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-413">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="3ae92-414">在 "**受控**" 选项卡上，将 GPO 的状态标识为 "**已签出**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-414">On the **Controlled** tab, the state of the GPO is identified as **Checked Out**.</span></span>

**<span data-ttu-id="3ae92-415">脱机编辑该 GPO 并配置帐户锁定时间</span><span class="sxs-lookup"><span data-stu-id="3ae92-415">To edit the GPO offline and configure the account lockout duration</span></span>**

1.  <span data-ttu-id="3ae92-416">在 "**受控**" 选项卡上，右键单击 " **MyOtherGPO**"，然后单击 "**编辑**" 以打开 "**组策略管理编辑器**" 窗口，并更改该 GPO 的脱机副本。</span><span class="sxs-lookup"><span data-stu-id="3ae92-416">On the **Controlled** tab, right-click **MyOtherGPO**, and then click **Edit** to open the **Group Policy Management Editor** window and change an offline copy of the GPO.</span></span> <span data-ttu-id="3ae92-417">对于此方案，请配置最小密码长度：</span><span class="sxs-lookup"><span data-stu-id="3ae92-417">For this scenario, configure the minimum password length:</span></span>

    1.  <span data-ttu-id="3ae92-418">在 "**计算机配置**" 下，双击 "**策略**"、" **Windows 设置**"、"**安全设置**"、"**帐户策略**" 和 "**帐户锁定策略**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-418">Under **Computer Configuration**, double-click **Policies**, **Windows Settings**, **Security Settings**, **Account Policies**, and **Account Lockout Policy**.</span></span>

    2.  <span data-ttu-id="3ae92-419">在 "详细信息" 窗格中，双击 "**帐户锁定时间**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-419">In the details pane, double-click **Account lockout duration**.</span></span>

    3.  <span data-ttu-id="3ae92-420">在 "属性" 窗口中，选中 "**定义此策略设置**"，将 "持续时间" 设置为 " **30**分钟"，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="3ae92-420">In the properties window, check **Define this policy setting**, set the duration to **30** minutes, and then click **OK**.</span></span>

2.  <span data-ttu-id="3ae92-421">关闭 "**组策略管理编辑器**" 窗口。</span><span class="sxs-lookup"><span data-stu-id="3ae92-421">Close the **Group Policy Management Editor** window.</span></span>

<span data-ttu-id="3ae92-422">在[步骤2：编辑 GPO](#bkmk-manage2)中，将 MyOtherGPO 签入存档并请求部署。</span><span class="sxs-lookup"><span data-stu-id="3ae92-422">Check MyOtherGPO into the archive and request deployment as you did for MyGPO in [Step 2: Edit a GPO](#bkmk-manage2).</span></span> <span data-ttu-id="3ae92-423">你可以使用差异报告将 MyOtherGPO 与 MyGPO 或 MyTemplate 进行比较。</span><span class="sxs-lookup"><span data-stu-id="3ae92-423">You can compare MyOtherGPO to MyGPO or to MyTemplate by using difference reports.</span></span> <span data-ttu-id="3ae92-424">任何包含审阅者角色的帐户（AGPM 管理员 \ [完全控制 \]、审批者、编辑者或审阅者）都可以生成报表。</span><span class="sxs-lookup"><span data-stu-id="3ae92-424">Any account that includes the Reviewer role (AGPM Administrator \[Full Control\], Approver, Editor, or Reviewer) can generate reports.</span></span>

**<span data-ttu-id="3ae92-425">将 GPO 与另一个 GPO 和模板进行比较</span><span class="sxs-lookup"><span data-stu-id="3ae92-425">To compare a GPO to another GPO and to a template</span></span>**

1.  <span data-ttu-id="3ae92-426">要比较 MyGPO 和 MyOtherGPO，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3ae92-426">To compare MyGPO and MyOtherGPO:</span></span>

    1.  <span data-ttu-id="3ae92-427">在 "**受控**" 选项卡上，单击 " **MyGPO**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-427">On the **Controlled** tab, click **MyGPO**.</span></span> <span data-ttu-id="3ae92-428">按 CTRL，然后单击 " **MyOtherGPO**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-428">Press CTRL and then click **MyOtherGPO**.</span></span>

    2.  <span data-ttu-id="3ae92-429">右键单击 " **MyOtherGPO**"，指向 "**差异**"，然后单击 " **HTML 报表**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-429">Right-click **MyOtherGPO**, point to **Differences**, and then click **HTML Report**.</span></span>

2.  <span data-ttu-id="3ae92-430">要比较 MyOtherGPO 和 MyTemplate，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3ae92-430">To compare MyOtherGPO and MyTemplate:</span></span>

    1.  <span data-ttu-id="3ae92-431">在 "**受控**" 选项卡上，单击 " **MyOtherGPO**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-431">On the **Controlled** tab, click **MyOtherGPO**.</span></span>

    2.  <span data-ttu-id="3ae92-432">右键单击 " **MyOtherGPO**"，指向 "**差异**"，然后单击 "**模板**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-432">Right-click **MyOtherGPO**, point to **Differences**, and then click **Template**.</span></span>

    3.  <span data-ttu-id="3ae92-433">选择 " **MyTemplate** " 和 " **HTML 报表**"，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="3ae92-433">Select **MyTemplate** and **HTML Report**, and then click **OK**.</span></span>

### <a href="" id="bkmk-manage5"></a><span data-ttu-id="3ae92-434">步骤5：删除和还原 GPO</span><span class="sxs-lookup"><span data-stu-id="3ae92-434">Step 5: Delete and restore a GPO</span></span>

<span data-ttu-id="3ae92-435">在此步骤中，你充当审批者以删除 GPO。</span><span class="sxs-lookup"><span data-stu-id="3ae92-435">In this step, you act as an Approver to delete a GPO.</span></span>

**<span data-ttu-id="3ae92-436">删除 GPO</span><span class="sxs-lookup"><span data-stu-id="3ae92-436">To delete a GPO</span></span>**

1.  <span data-ttu-id="3ae92-437">在已安装了 AGPM 客户端的计算机上，使用分配了审批者角色的用户帐户登录。</span><span class="sxs-lookup"><span data-stu-id="3ae92-437">On a computer on which you have installed AGPM Client, log on with a user account that is assigned the role of Approver.</span></span>

2.  <span data-ttu-id="3ae92-438">在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-438">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

3.  <span data-ttu-id="3ae92-439">在 "**目录**" 选项卡上，单击 "**受控**" 选项卡以显示受控 gpo。</span><span class="sxs-lookup"><span data-stu-id="3ae92-439">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

4.  <span data-ttu-id="3ae92-440">右键单击 " **MyGPO**"，然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-440">Right-click **MyGPO**, and then click **Delete**.</span></span> <span data-ttu-id="3ae92-441">单击 "**从存档和生产中删除 GPO** " 以删除存档中的版本和生产环境中部署的 GPO 的部署版本。</span><span class="sxs-lookup"><span data-stu-id="3ae92-441">Click **Delete GPO from archive and production** to delete both the version in the archive and the deployed version of the GPO in the production environment.</span></span>

5.  <span data-ttu-id="3ae92-442">键入要显示在 GPO 审核跟踪中的注释，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="3ae92-442">Type a comment to be displayed in the audit trail for the GPO, and then click **OK**.</span></span>

6.  <span data-ttu-id="3ae92-443">当**AGPM 进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-443">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="3ae92-444">GPO 将从 "**受控**" 选项卡中删除，并显示在 "**回收站**" 选项卡上，可在其中还原或销毁。</span><span class="sxs-lookup"><span data-stu-id="3ae92-444">The GPO is removed from the **Controlled** tab and is displayed on the **Recycle Bin** tab, where it can be restored or destroyed.</span></span>

<span data-ttu-id="3ae92-445">有时，你可能会在删除仍需要的 GPO 后发现。</span><span class="sxs-lookup"><span data-stu-id="3ae92-445">Occasionally you may discover after you delete a GPO that it is still needed.</span></span> <span data-ttu-id="3ae92-446">在此步骤中，你充当审批者以还原已删除的 GPO。</span><span class="sxs-lookup"><span data-stu-id="3ae92-446">In this step, you act as an Approver to restore a GPO that was deleted.</span></span>

**<span data-ttu-id="3ae92-447">还原已删除的 GPO</span><span class="sxs-lookup"><span data-stu-id="3ae92-447">To restore a deleted GPO</span></span>**

1.  <span data-ttu-id="3ae92-448">在 "**目录**" 选项卡上，单击 "**回收站**" 选项卡以显示已删除的 gpo。</span><span class="sxs-lookup"><span data-stu-id="3ae92-448">On the **Contents** tab, click the **Recycle Bin** tab to display deleted GPOs.</span></span>

2.  <span data-ttu-id="3ae92-449">右键单击 " **MyGPO**"，然后单击 "**还原**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-449">Right-click **MyGPO**, and then click **Restore**.</span></span>

3.  <span data-ttu-id="3ae92-450">键入要在 GPO 的历史记录中显示的注释，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="3ae92-450">Type a comment to be displayed in the history of the GPO, and then click **OK**.</span></span>

4.  <span data-ttu-id="3ae92-451">当**AGPM 进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-451">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="3ae92-452">该 GPO 将从 "**回收站**" 选项卡中删除，并显示在 "**受控**" 选项卡上。</span><span class="sxs-lookup"><span data-stu-id="3ae92-452">The GPO is removed from the **Recycle Bin** tab and is displayed on the **Controlled** tab.</span></span>

    <span data-ttu-id="3ae92-453">**注意** 将 GPO 还原到存档不会自动将其重新部署到生产环境。</span><span class="sxs-lookup"><span data-stu-id="3ae92-453">**Note** Restoring a GPO to the archive does not automatically redeploy it to the production environment.</span></span> <span data-ttu-id="3ae92-454">若要将 GPO 返回到生产环境，请按照[步骤3部署 gpo：查看和部署 gpo](#bkmk-manage3)。</span><span class="sxs-lookup"><span data-stu-id="3ae92-454">To return the GPO to the production environment, deploy the GPO as in [Step 3: Review and deploy a GPO](#bkmk-manage3).</span></span>

     

<span data-ttu-id="3ae92-455">在编辑和部署 GPO 之后，你可能会发现对 GPO 所做的最新更改会导致出现问题。</span><span class="sxs-lookup"><span data-stu-id="3ae92-455">After editing and deploying a GPO, you may discover that recent changes to the GPO are causing a problem.</span></span> <span data-ttu-id="3ae92-456">在此步骤中，你充当审批者以回退到 GPO 的早期版本。</span><span class="sxs-lookup"><span data-stu-id="3ae92-456">In this step, you act as an Approver to roll back to an earlier version of the GPO.</span></span> <span data-ttu-id="3ae92-457">你可以回退到 GPO 历史记录中的任意版本。</span><span class="sxs-lookup"><span data-stu-id="3ae92-457">You can roll back to any version in the history of the GPO.</span></span> <span data-ttu-id="3ae92-458">你可以使用批注和标签来标识已知的有效版本以及进行特定的更改。</span><span class="sxs-lookup"><span data-stu-id="3ae92-458">You can use comments and labels to identify known good versions and when specific changes were made.</span></span>

**<span data-ttu-id="3ae92-459">回滚到 GPO 的早期版本</span><span class="sxs-lookup"><span data-stu-id="3ae92-459">To roll back to an earlier version of a GPO</span></span>**

1.  <span data-ttu-id="3ae92-460">在 "**目录**" 选项卡上，单击 "**受控**" 选项卡以显示受控 gpo。</span><span class="sxs-lookup"><span data-stu-id="3ae92-460">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

2.  <span data-ttu-id="3ae92-461">双击 " **MyGPO** " 以显示其历史记录。</span><span class="sxs-lookup"><span data-stu-id="3ae92-461">Double-click **MyGPO** to display its history.</span></span>

3.  <span data-ttu-id="3ae92-462">右键单击要部署的版本，单击 "**部署**"，然后单击 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="3ae92-462">Right-click the version to be deployed, click **Deploy**, and then click **Yes**.</span></span>

4.  <span data-ttu-id="3ae92-463">当**进度**窗口指示整个进度完成时，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-463">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="3ae92-464">在 "**历史记录**" 窗口中，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-464">In the **History** window, click **Close**.</span></span>

    <span data-ttu-id="3ae92-465">**注意** 若要验证重新部署的版本是否为所需的版本，请检查两个版本的差异报告。</span><span class="sxs-lookup"><span data-stu-id="3ae92-465">**Note** To verify that the version that was redeployed is the version intended, examine a difference report for the two versions.</span></span> <span data-ttu-id="3ae92-466">在 GPO 的 "**历史记录**" 窗口中，选择两个版本，右键单击它们，指向 "**差异**"，然后单击 " **HTML 报表**" 或 " **XML 报表**"。</span><span class="sxs-lookup"><span data-stu-id="3ae92-466">In the **History** window for the GPO, select the two versions, right-click them, point to **Difference**, and then click either **HTML Report** or **XML Report**.</span></span>

     

 

 





