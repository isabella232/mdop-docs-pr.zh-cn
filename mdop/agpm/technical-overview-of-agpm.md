---
title: AGPM 技术概述
description: AGPM 技术概述
author: dansimp
ms.assetid: 36bc0ab5-f752-474c-8559-721ea95169c2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 0cc635f46c2aabb0c9fa1f472a258a3e65a07b55
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801760"
---
# <span data-ttu-id="caf26-103">AGPM 技术概述</span><span class="sxs-lookup"><span data-stu-id="caf26-103">Technical Overview of AGPM</span></span>


<span data-ttu-id="caf26-104">Microsoft 高级组策略管理（AGPM）是一个客户端/服务器应用程序。</span><span class="sxs-lookup"><span data-stu-id="caf26-104">Microsoft Advanced Group Policy Management (AGPM) is a client/server application.</span></span> <span data-ttu-id="caf26-105">AGPM 服务器在 AGPM 在服务器的文件系统上创建的存档中存储组策略对象（Gpo）。</span><span class="sxs-lookup"><span data-stu-id="caf26-105">The AGPM Server stores Group Policy Objects (GPOs) offline in the archive that AGPM creates on the server's file system.</span></span> <span data-ttu-id="caf26-106">组策略管理员使用组策略管理控制台（GPMC）的 AGPM 管理单元来处理托管存档的服务器上的 Gpo。</span><span class="sxs-lookup"><span data-stu-id="caf26-106">Group Policy administrators use the AGPM snap-in for the Group Policy Management Console (GPMC) to work with GPOs on the server that hosts the archive.</span></span> <span data-ttu-id="caf26-107">了解 AGPM 和相关项目的组成部分、如何在文件系统中存储 Gpo 以及权限如何控制每个用户角色的操作可通过 AGPM 提高组策略管理员的有效性。</span><span class="sxs-lookup"><span data-stu-id="caf26-107">Understanding the parts of AGPM and related items, how they store GPOs in the file system, and how permissions control the actions available to each user role can improve Group Policy administrators' effectiveness with AGPM.</span></span>

## <span data-ttu-id="caf26-108">术语</span><span class="sxs-lookup"><span data-stu-id="caf26-108">Terminology</span></span>


<span data-ttu-id="caf26-109">下面介绍了基本的 AGPM 术语。</span><span class="sxs-lookup"><span data-stu-id="caf26-109">The following explains the basic AGPM terms.</span></span>

-   <span data-ttu-id="caf26-110">**AGPM 客户端：** 运行组策略管理控制台（GPMC）和组策略管理员管理 Gpo 的 AGPM 管理单元的计算机。</span><span class="sxs-lookup"><span data-stu-id="caf26-110">**AGPM Client:** A computer that runs the AGPM snap-in for the Group Policy Management Console (GPMC) and from which Group Policy administrators manage GPOs.</span></span>

-   <span data-ttu-id="caf26-111">**AGPM 管理单元：** 在 AGPM 客户端上安装的 AGPM 的软件组件，以便它们可以管理 Gpo。</span><span class="sxs-lookup"><span data-stu-id="caf26-111">**AGPM snap-in:** The software component of AGPM installed on AGPM Clients so that they can manage GPOs.</span></span>

-   <span data-ttu-id="caf26-112">**AGPM 服务器：** 运行 AGPM 服务并管理存档的服务器。</span><span class="sxs-lookup"><span data-stu-id="caf26-112">**AGPM Server:** A server that runs the AGPM Service and manages an archive.</span></span> <span data-ttu-id="caf26-113">每个 AGPM 服务器只能管理一个存档，但一个 AGPM 服务器可以在一个存档中管理多个域的存档数据。</span><span class="sxs-lookup"><span data-stu-id="caf26-113">Each AGPM Server can manage only one archive, but one AGPM Server can manage archive data for multiple domains in one archive.</span></span> <span data-ttu-id="caf26-114">存档可以托管在不是 AGPM 服务器的计算机上。</span><span class="sxs-lookup"><span data-stu-id="caf26-114">An archive can be hosted on a computer other than an AGPM Server.</span></span>

-   <span data-ttu-id="caf26-115">**AGPM 服务：** 在 AGPM 服务器上作为服务运行的 AGPM 的软件组件。</span><span class="sxs-lookup"><span data-stu-id="caf26-115">**AGPM Service:** The software component of AGPM that runs on an AGPM Server as a service.</span></span> <span data-ttu-id="caf26-116">该服务管理存档中和该林中生产环境中的 Gpo。</span><span class="sxs-lookup"><span data-stu-id="caf26-116">The service manages GPOs in the archive and in the production environment in that forest.</span></span>

-   <span data-ttu-id="caf26-117">**存档：** 在 AGPM 中，包含关联的 AGPM 服务器管理的受控 Gpo 的中央存储，以及其中每个 Gpo 的历史记录。</span><span class="sxs-lookup"><span data-stu-id="caf26-117">**Archive:** In AGPM, a central store that contains the controlled GPOs that the associated AGPM Server manages, in addition to the history for each of those GPOs.</span></span> <span data-ttu-id="caf26-118">这包括每个 GPO 的所有以前的受控制版本。</span><span class="sxs-lookup"><span data-stu-id="caf26-118">This includes all previous controlled versions of each GPO.</span></span> <span data-ttu-id="caf26-119">存档包含存档索引文件和关联的存档数据，其中可能包含多个域中的 Gpo 的数据。</span><span class="sxs-lookup"><span data-stu-id="caf26-119">An archive consists of an archive index file and associated archive data that may include data for GPOs in multiple domains.</span></span> <span data-ttu-id="caf26-120">存档可以托管在不是 AGPM 服务器的计算机上。</span><span class="sxs-lookup"><span data-stu-id="caf26-120">An archive can be hosted on a computer other than an AGPM Server.</span></span>

-   <span data-ttu-id="caf26-121">**受控 GPO：** 由 AGPM 管理的 GPO。</span><span class="sxs-lookup"><span data-stu-id="caf26-121">**Controlled GPO:** A GPO that is being managed by AGPM.</span></span> <span data-ttu-id="caf26-122">AGPM 管理受控制 Gpo 的历史记录和权限，它存储在存档中。</span><span class="sxs-lookup"><span data-stu-id="caf26-122">AGPM manages the history and permissions of controlled GPOs, which it stores in the archive.</span></span>

-   <span data-ttu-id="caf26-123">不**受控制的 GPO：** 域生产环境中的 GPO，而不是由 AGPM 托管。</span><span class="sxs-lookup"><span data-stu-id="caf26-123">**Uncontrolled GPO:** A GPO in the production environment for a domain and not managed by AGPM.</span></span>

## <span data-ttu-id="caf26-124">哪些 AGPM 安装、创建和影响</span><span class="sxs-lookup"><span data-stu-id="caf26-124">What AGPM installs, creates, and affects</span></span>


<span data-ttu-id="caf26-125">在 AGPM 服务器上，AGPM 设置程序将安装 AGPM 服务。</span><span class="sxs-lookup"><span data-stu-id="caf26-125">On an AGPM Server, the AGPM Setup program installs the AGPM Service.</span></span> <span data-ttu-id="caf26-126">AGPM 不会更改 Active Directory®目录服务或架构。</span><span class="sxs-lookup"><span data-stu-id="caf26-126">AGPM does not alter the Active Directory® directory service or the schema.</span></span> <span data-ttu-id="caf26-127">默认情况下，AGPM 服务器程序文件安装在%ProgramFiles%\\Microsoft\\AGPM\\Server。</span><span class="sxs-lookup"><span data-stu-id="caf26-127">By default, the AGPM Server program files are installed in %ProgramFiles%\\Microsoft\\AGPM\\Server.</span></span> <span data-ttu-id="caf26-128">如果需要，您可以在域控制器上安装 AGPM 服务;但是，我们建议你在成员服务器上安装 AGPM 服务。</span><span class="sxs-lookup"><span data-stu-id="caf26-128">You can install the AGPM Service on a domain controller if you have to; however, we recommend that you install the AGPM Service on a member server.</span></span>

<span data-ttu-id="caf26-129">在 AGPM 客户端上，AGPM 设置程序将安装 AGPM 管理单元，将 "**更改控制**" 文件夹添加到 GPMC 中显示的每个域。</span><span class="sxs-lookup"><span data-stu-id="caf26-129">On an AGPM Client, the AGPM Setup program installs the AGPM snap-in, adding a **Change Control** folder to each domain that appears in the GPMC.</span></span> <span data-ttu-id="caf26-130">默认情况下，AGPM 客户端程序文件安装在%ProgramFiles%\\Microsoft\\AGPM\\Client。</span><span class="sxs-lookup"><span data-stu-id="caf26-130">By default, the AGPM Client program files are installed in %ProgramFiles%\\Microsoft\\AGPM\\Client.</span></span>

<span data-ttu-id="caf26-131">表1介绍了 AGPM 安装或创建的项目以及影响 AGPM 操作的操作系统部分。</span><span class="sxs-lookup"><span data-stu-id="caf26-131">Table 1 describes both the items that AGPM installs or creates and the parts of the operating system that affect AGPM operation.</span></span>

**<span data-ttu-id="caf26-132">表1：已安装、已创建或受 AGPM 影响的项目</span><span class="sxs-lookup"><span data-stu-id="caf26-132">Table 1: Items installed, created, or affected by AGPM</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="caf26-133">项目</span><span class="sxs-lookup"><span data-stu-id="caf26-133">Item</span></span></th>
<th align="left"><span data-ttu-id="caf26-134">描述</span><span class="sxs-lookup"><span data-stu-id="caf26-134">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="caf26-135">AGPM 服务</span><span class="sxs-lookup"><span data-stu-id="caf26-135">AGPM Service</span></span></p></td>
<td align="left"><p><span data-ttu-id="caf26-136">AGPM 服务在 AGPM 服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="caf26-136">The AGPM Service runs on the AGPM Server.</span></span> <span data-ttu-id="caf26-137">该服务在生产环境中管理包含脱机 Gpo 和受控 Gpo 的存档。</span><span class="sxs-lookup"><span data-stu-id="caf26-137">The service manages the archive, which contains offline GPOs, and controlled GPOs in the production environment.</span></span> <span data-ttu-id="caf26-138">AGPM 服务的默认配置如下所示：</span><span class="sxs-lookup"><span data-stu-id="caf26-138">The default configuration of the AGPM Service is as follows:</span></span></p>
<ul>
<li><p><strong><span data-ttu-id="caf26-139">服务名称： </strong> AGPM 服务</span><span class="sxs-lookup"><span data-stu-id="caf26-139">Service name:</strong> AGPM Service</span></span></p></li>
<li><p><strong><span data-ttu-id="caf26-140">显示名称： </strong> AGPM 服务</span><span class="sxs-lookup"><span data-stu-id="caf26-140">Display name:</strong> AGPM Service</span></span></p></li>
<li><p><strong><span data-ttu-id="caf26-141">可执行文件的路径： </strong> % ProgramFiles% \Microsoft\AGPM\Server\Agpm.exe</span><span class="sxs-lookup"><span data-stu-id="caf26-141">Path to executable:</strong> %ProgramFiles%\Microsoft\AGPM\Server\Agpm.exe</span></span></p></li>
<li><p><strong><span data-ttu-id="caf26-142">启动： </strong> 自动</span><span class="sxs-lookup"><span data-stu-id="caf26-142">Startup:</strong> Automatic</span></span></p></li>
<li><p><strong><span data-ttu-id="caf26-143">在 </strong> 安装 Agpm 服务器期间指定的 Agpm 服务帐户（可使用 <strong> </strong> "控制面板" 中的 "程序和功能" 更改 <strong> ）进行登录 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="caf26-143">Log on as:</strong> AGPM Service Account specified during installation of AGPM Server, which can be changed using <strong>Programs and Features</strong> in the <strong>Control Panel</strong>.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="caf26-144">AGPM 存档</span><span class="sxs-lookup"><span data-stu-id="caf26-144">AGPM archive</span></span></p></td>
<td align="left"><p><span data-ttu-id="caf26-145">默认情况下，AGPM 在 AGPM 服务器上的%ProgramData%\Microsoft\AGPM 中创建存档。</span><span class="sxs-lookup"><span data-stu-id="caf26-145">By default, AGPM creates the archive in %ProgramData%\Microsoft\AGPM on the AGPM Server.</span></span> <span data-ttu-id="caf26-146">存档提供脱机 Gpo 的存储，并且它可以存储每个 GPO 的多个版本。</span><span class="sxs-lookup"><span data-stu-id="caf26-146">The archive provides storage for offline GPOs, and it can store multiple versions of each GPO.</span></span> <span data-ttu-id="caf26-147">AGPM 对存档中的 Gpo 所做的更改不会影响生产环境，直到 AGPM 管理员或审批者将 GPO 部署到生产环境并将 GPO 链接到组织单元（OU）。</span><span class="sxs-lookup"><span data-stu-id="caf26-147">Changes that AGPM makes to GPOs in the archive do not affect the production environment until an AGPM Administrator or Approver deploys the GPO to the production environment and links the GPO to an organizational unit (OU).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="caf26-148">Windows 防火墙</span><span class="sxs-lookup"><span data-stu-id="caf26-148">Windows Firewall</span></span></p></td>
<td align="left"><p><span data-ttu-id="caf26-149">在安装期间，AGPM 支持允许 AGPM 客户端与 AGPM 服务器通信的入站 Windows 防火墙规则。</span><span class="sxs-lookup"><span data-stu-id="caf26-149">During installation, AGPM enables an inbound Windows Firewall rule that allows the AGPM Client to communicate with the AGPM Server.</span></span> <span data-ttu-id="caf26-150">默认的 Windows 防火墙规则如下所示：</span><span class="sxs-lookup"><span data-stu-id="caf26-150">The default Windows Firewall rule is the following:</span></span></p>
<ul>
<li><p><strong><span data-ttu-id="caf26-151">名称： </strong> AGPM 服务</span><span class="sxs-lookup"><span data-stu-id="caf26-151">Name:</strong> AGPM Service</span></span></p></li>
<li><p><strong><span data-ttu-id="caf26-152">操作： </strong> 允许连接</span><span class="sxs-lookup"><span data-stu-id="caf26-152">Action:</strong> Allow the connection</span></span></p></li>
<li><p><strong><span data-ttu-id="caf26-153">程序： </strong> 满足指定条件的所有程序</span><span class="sxs-lookup"><span data-stu-id="caf26-153">Programs:</strong> All programs that meet the specified conditions</span></span></p></li>
<li><p><strong><span data-ttu-id="caf26-154">协议类型： </strong> TCP</span><span class="sxs-lookup"><span data-stu-id="caf26-154">Protocol type:</strong> TCP</span></span></p></li>
<li><p><strong><span data-ttu-id="caf26-155">本地端口： </strong> 4600</span><span class="sxs-lookup"><span data-stu-id="caf26-155">Local port:</strong> 4600</span></span></p></li>
<li><p><strong><span data-ttu-id="caf26-156">远程端口： </strong> 所有端口</span><span class="sxs-lookup"><span data-stu-id="caf26-156">Remote port:</strong> All ports</span></span></p></li>
<li><p><strong><span data-ttu-id="caf26-157">本地 IP 地址： </strong> 任意</span><span class="sxs-lookup"><span data-stu-id="caf26-157">Local IP address:</strong> Any</span></span></p></li>
<li><p><strong><span data-ttu-id="caf26-158">远程 IP 地址： </strong> 任何</span><span class="sxs-lookup"><span data-stu-id="caf26-158">Remote IP address:</strong> Any</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="caf26-159">电子邮件服务器</span><span class="sxs-lookup"><span data-stu-id="caf26-159">E-mail server</span></span></p></td>
<td align="left"><p><span data-ttu-id="caf26-160">AGPM 使用简单邮件传输协议（SMTP）将电子邮件请求发送到 " <strong> 域委派" 选项卡上配置的地址 </strong> 。例如，当一个编辑器请求创建新的 GPO 时，AGPM 会通知在 " <strong> 域委派" 选项卡上指定的每个电子邮件地址 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="caf26-160">AGPM uses Simple Mail Transfer Protocol (SMTP) to send e-mail requests to the addresses configured on the <strong>Domain Delegation</strong> tab. For example, when an Editor requests that a new GPO be created, AGPM notifies each e-mail address specified on the <strong>Domain Delegation</strong> tab.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="caf26-161">AGPM 管理单元</span><span class="sxs-lookup"><span data-stu-id="caf26-161">AGPM snap-in</span></span></p></td>
<td align="left"><p><span data-ttu-id="caf26-162">GPMC 的 AGPM 管理单元在 AGPM 客户端上运行，由组策略管理员用于管理 Gpo。</span><span class="sxs-lookup"><span data-stu-id="caf26-162">The AGPM snap-in for the GPMC runs on AGPM Clients and is used by Group Policy administrators to manage GPOs.</span></span> <span data-ttu-id="caf26-163">管理单元将在 GPMC 中显示为 <strong> </strong> 每个域中的更改控制文件夹。</span><span class="sxs-lookup"><span data-stu-id="caf26-163">The snap-in appears in the GPMC as a <strong>Change Control</strong> folder in each domain.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="caf26-164">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="caf26-164">Additional references</span></span>

<span data-ttu-id="caf26-165">有关 AGPM 安装的文件的详细信息，请参阅[agpm 的规划指南](https://go.microsoft.com/fwlink/?LinkId=160060)。</span><span class="sxs-lookup"><span data-stu-id="caf26-165">For more information about the files installed by AGPM, see the [Planning Guide for AGPM](https://go.microsoft.com/fwlink/?LinkId=160060).</span></span>

## <span data-ttu-id="caf26-166">Archive</span><span class="sxs-lookup"><span data-stu-id="caf26-166">Archive</span></span>


<span data-ttu-id="caf26-167">默认情况下，AGPM 服务器安装过程会在%ProgramData%\\Microsoft\\AGPM. 上的 AGPM 服务器的本地硬盘上创建存档。</span><span class="sxs-lookup"><span data-stu-id="caf26-167">By default, the AGPM Server installation process creates the archive on the local hard disk of the AGPM Server at %ProgramData%\\Microsoft\\AGPM.</span></span> <span data-ttu-id="caf26-168">但是，你可以在安装过程中更改路径，甚至可以在 AGPM 服务器之外的服务器上创建存档。</span><span class="sxs-lookup"><span data-stu-id="caf26-168">However, you can change the path during installation and even create the archive on a server other than the AGPM Server.</span></span>

<span data-ttu-id="caf26-169">存档包含存档包含的每个 GPO 版本的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="caf26-169">The archive contains a subfolder for each version of each GPO the archive contains.</span></span> <span data-ttu-id="caf26-170">每个子文件夹的名称是一个 GUID，用于标识 GPO 的一个版本。</span><span class="sxs-lookup"><span data-stu-id="caf26-170">The name of each subfolder is a GUID that identifies a version of the GPO.</span></span>

<span data-ttu-id="caf26-171">gpostate.xml 文件记录存档中每个 GPO 的状态。</span><span class="sxs-lookup"><span data-stu-id="caf26-171">The gpostate.xml file records the state of each GPO in the archive.</span></span> <span data-ttu-id="caf26-172">该文件是描述存档内容的清单。</span><span class="sxs-lookup"><span data-stu-id="caf26-172">The file is a manifest that describes the contents of the archive.</span></span> <span data-ttu-id="caf26-173">例如，GPO 可以有多个版本，每个版本都位于存档中各自的子文件夹中。</span><span class="sxs-lookup"><span data-stu-id="caf26-173">For example, a GPO can have many versions, and each version is in its own subfolder in the archive.</span></span> <span data-ttu-id="caf26-174">gpostate.xml 文件指示哪些子文件夹包含单个 GPO 的不同版本。</span><span class="sxs-lookup"><span data-stu-id="caf26-174">The gpostate.xml file indicates which subfolders contain different versions of a single GPO.</span></span> <span data-ttu-id="caf26-175">此外，GPO 模板在存档中具有子文件夹，但 gpostate.xml 指示这些模板是模板，而不是受控制的 Gpo。</span><span class="sxs-lookup"><span data-stu-id="caf26-175">Additionally, GPO templates have subfolders in the archive, but gpostate.xml indicates that these are templates and not controlled GPOs.</span></span> <span data-ttu-id="caf26-176">同样，当组策略管理员删除 Gpo 时，AGPM 会在 gpostate.xml 中更改其状态，以指示它们位于**回收站**中，但实际上并不会从存档中删除 gpo 的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="caf26-176">Similarly, when Group Policy administrators delete GPOs, AGPM changes their states in gpostate.xml to indicate that they are in the **Recycle Bin** but does not actually remove the GPOs' subfolders from the archive.</span></span>

<span data-ttu-id="caf26-177">**小心** 不要手动编辑 gpostate.xml 或存档包含的 Gpo。</span><span class="sxs-lookup"><span data-stu-id="caf26-177">**Caution** Do not manually edit gpostate.xml or the GPOs the archive contains.</span></span> <span data-ttu-id="caf26-178">提供此信息只是为了增强对 AGPM 存档的理解。</span><span class="sxs-lookup"><span data-stu-id="caf26-178">This information is provided only to enhance understanding of the AGPM archive.</span></span> <span data-ttu-id="caf26-179">请改为使用 AGPM 管理单元更改 Gpo。</span><span class="sxs-lookup"><span data-stu-id="caf26-179">Instead, use the AGPM snap-in to change GPOs.</span></span>

 

<span data-ttu-id="caf26-180">当 AGPM 创建存档时，它会向系统、管理员和 AGPM 服务帐户（在 AGPM 服务器的设置中指定）授予完全控制权。</span><span class="sxs-lookup"><span data-stu-id="caf26-180">When AGPM creates the archive, it gives Full Control to SYSTEM, Administrators, and the AGPM Service Account (specified in the setup of AGPM Server).</span></span> <span data-ttu-id="caf26-181">通过使用 AGPM 管理单元上的 AGPM 用户界面更改权限不会改变对存档的权限，因为 AGPM 服务帐户代表登录用户执行所有操作。</span><span class="sxs-lookup"><span data-stu-id="caf26-181">Changing permissions by using the AGPM user interface on the AGPM snap-in does not alter permissions on the archive, because the AGPM Service Account performs all operations on behalf of the logged-on user.</span></span>

### <span data-ttu-id="caf26-182">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="caf26-182">Additional references</span></span>

<span data-ttu-id="caf26-183">有关如何备份存档、从备份还原存档或同时移动 AGPM 服务器和存档的信息，请参阅[适用于 agpm 的操作指南](https://go.microsoft.com/fwlink/?LinkId=160061)中的 "执行 Agpm 管理员任务" 部分。</span><span class="sxs-lookup"><span data-stu-id="caf26-183">For information about how to back up the archive, restore the archive from a backup, or move both the AGPM Server and the archive, see the "Performing AGPM Administrator Tasks" section in the [Operations Guide for AGPM](https://go.microsoft.com/fwlink/?LinkId=160061).</span></span>

## <span data-ttu-id="caf26-184">角色和权限</span><span class="sxs-lookup"><span data-stu-id="caf26-184">Roles and permissions</span></span>


<span data-ttu-id="caf26-185">角色简化了委派。</span><span class="sxs-lookup"><span data-stu-id="caf26-185">Roles simplify delegation.</span></span> <span data-ttu-id="caf26-186">对于组策略管理员而言，AGPM 管理员可以向组策略管理员分配以下四个角色之一，让他们可以执行与该角色相关的工作：</span><span class="sxs-lookup"><span data-stu-id="caf26-186">Instead of assigning detailed permissions to Group Policy administrators, AGPM Administrators can assign one of four roles to Group Policy administrators to let them perform work related to that role:</span></span>

-   <span data-ttu-id="caf26-187">**AGPM 管理员：** 分配了 AGPM 管理员（完全控制）角色的组策略管理员可以在 AGPM 中执行任何任务。</span><span class="sxs-lookup"><span data-stu-id="caf26-187">**AGPM Administrator:** Group Policy administrators assigned the AGPM Administrator (Full Control) role can perform any task in AGPM.</span></span> <span data-ttu-id="caf26-188">AGPM 管理员可以配置域范围的选项并将权限委派给其他组策略管理员。</span><span class="sxs-lookup"><span data-stu-id="caf26-188">AGPM Administrators can configure domain-wide options and delegate permissions to other Group Policy administrators.</span></span>

-   <span data-ttu-id="caf26-189">**审批者：** 分配了审批者角色的组策略管理员可以将 Gpo 部署到域的生产环境中。</span><span class="sxs-lookup"><span data-stu-id="caf26-189">**Approver:** Group Policy administrators assigned the Approver role can deploy GPOs to the production environment for a domain.</span></span> <span data-ttu-id="caf26-190">审批者还可以创建和删除 Gpo，并批准或拒绝来自编辑者的请求。</span><span class="sxs-lookup"><span data-stu-id="caf26-190">Approvers can also create and delete GPOs and approve or reject requests from Editors.</span></span> <span data-ttu-id="caf26-191">审批者可以查看域中的 Gpo 列表、查看 Gpo 中的策略设置以及创建和查看 GPO 中的策略设置报告。</span><span class="sxs-lookup"><span data-stu-id="caf26-191">Approvers can view the list of GPOs in a domain, view the policy settings in GPOs, and create and view reports of the policy settings in a GPO.</span></span> <span data-ttu-id="caf26-192">它们不能编辑 Gpo 中的策略设置，除非它们也分配有编辑者角色。</span><span class="sxs-lookup"><span data-stu-id="caf26-192">They cannot edit the policy settings in GPOs unless they are also assigned the Editor role.</span></span>

-   <span data-ttu-id="caf26-193">**编辑器：** 分配了 "编辑" 角色的组策略管理员可以查看域中的 Gpo 列表、查看 Gpo 中的策略设置、编辑 Gpo 中的策略设置以及创建和查看 GPO 中的策略设置报告。</span><span class="sxs-lookup"><span data-stu-id="caf26-193">**Editor:** Group Policy administrators assigned the Editor role can view the list of GPOs in a domain, view the policy settings in GPOs, edit the policy settings in GPOs, and create and view reports of the policy settings in a GPO.</span></span> <span data-ttu-id="caf26-194">除非它们也分配给审批者角色，否则编辑者无法创建、部署或删除 Gpo。</span><span class="sxs-lookup"><span data-stu-id="caf26-194">Unless they are also assigned the Approver role, Editors cannot create, deploy, or delete GPOs.</span></span> <span data-ttu-id="caf26-195">但是，他们可以请求创建、部署或删除 Gpo。</span><span class="sxs-lookup"><span data-stu-id="caf26-195">However, they can request that GPOs be created, deployed, or deleted.</span></span>

-   <span data-ttu-id="caf26-196">**审阅者：** 分配了审阅者角色的组策略管理员可以查看域中的 Gpo 列表，并在 GPO 中创建和查看策略设置的报告。</span><span class="sxs-lookup"><span data-stu-id="caf26-196">**Reviewer:** Group Policy administrators assigned the Reviewer role can view the list of GPOs in a domain and create and view reports of the policy settings in a GPO.</span></span> <span data-ttu-id="caf26-197">除非它们也分配有编辑器角色，否则它们不能在 GPO 中编辑策略设置。</span><span class="sxs-lookup"><span data-stu-id="caf26-197">Unless they are also assigned the Editor role, they cannot edit policy settings in a GPO.</span></span>

<span data-ttu-id="caf26-198">AGPM 使 AGPM 管理员能够通过使用 AGPM 管理单元以比角色更详细的级别配置权限。</span><span class="sxs-lookup"><span data-stu-id="caf26-198">AGPM gives AGPM Administrators the flexibility to configure permissions at a more detailed level than roles by using the AGPM snap-in.</span></span> <span data-ttu-id="caf26-199">表2描述了这些权限，并指明了默认授予每个角色的权限。</span><span class="sxs-lookup"><span data-stu-id="caf26-199">Table 2 describes these permissions and indicates the permissions granted to each role by default.</span></span>

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="caf26-200">权限</span><span class="sxs-lookup"><span data-stu-id="caf26-200">Permission</span></span></th>
<th align="left"><span data-ttu-id="caf26-201">描述</span><span class="sxs-lookup"><span data-stu-id="caf26-201">Description</span></span></th>
<th align="left"><span data-ttu-id="caf26-202">AGPM 管理员</span><span class="sxs-lookup"><span data-stu-id="caf26-202">AGPM Administrator</span></span></th>
<th align="left"><span data-ttu-id="caf26-203">审批者</span><span class="sxs-lookup"><span data-stu-id="caf26-203">Approver</span></span></th>
<th align="left"><span data-ttu-id="caf26-204">编辑器</span><span class="sxs-lookup"><span data-stu-id="caf26-204">Editor</span></span></th>
<th align="left"><span data-ttu-id="caf26-205">姓名</span><span class="sxs-lookup"><span data-stu-id="caf26-205">Reviewer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="caf26-206">完全控制</span><span class="sxs-lookup"><span data-stu-id="caf26-206">Full Control</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="caf26-207">具有所有权限。</span><span class="sxs-lookup"><span data-stu-id="caf26-207">Have all permissions.</span></span></p></td>
<td align="left"><p><span data-ttu-id="caf26-208">是</span><span class="sxs-lookup"><span data-stu-id="caf26-208">Yes</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="caf26-209">创建 GPO</span><span class="sxs-lookup"><span data-stu-id="caf26-209">Create GPO</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="caf26-210">在域中创建 Gpo。</span><span class="sxs-lookup"><span data-stu-id="caf26-210">Create GPOs in a domain.</span></span></p></td>
<td align="left"><p><span data-ttu-id="caf26-211">是</span><span class="sxs-lookup"><span data-stu-id="caf26-211">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="caf26-212">是</span><span class="sxs-lookup"><span data-stu-id="caf26-212">Yes</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="caf26-213">列表内容</span><span class="sxs-lookup"><span data-stu-id="caf26-213">List Contents</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="caf26-214">列出域中的 Gpo。</span><span class="sxs-lookup"><span data-stu-id="caf26-214">List the GPOs in a domain.</span></span></p></td>
<td align="left"><p><span data-ttu-id="caf26-215">是</span><span class="sxs-lookup"><span data-stu-id="caf26-215">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="caf26-216">是</span><span class="sxs-lookup"><span data-stu-id="caf26-216">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="caf26-217">是</span><span class="sxs-lookup"><span data-stu-id="caf26-217">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="caf26-218">是</span><span class="sxs-lookup"><span data-stu-id="caf26-218">Yes</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="caf26-219">读取设置</span><span class="sxs-lookup"><span data-stu-id="caf26-219">Read Settings</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="caf26-220">阅读 GPO 中的策略设置。</span><span class="sxs-lookup"><span data-stu-id="caf26-220">Read the policy settings within a GPO.</span></span></p></td>
<td align="left"><p><span data-ttu-id="caf26-221">是</span><span class="sxs-lookup"><span data-stu-id="caf26-221">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="caf26-222">是</span><span class="sxs-lookup"><span data-stu-id="caf26-222">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="caf26-223">是</span><span class="sxs-lookup"><span data-stu-id="caf26-223">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="caf26-224">是</span><span class="sxs-lookup"><span data-stu-id="caf26-224">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="caf26-225">编辑设置</span><span class="sxs-lookup"><span data-stu-id="caf26-225">Edit Settings</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="caf26-226">更改 GPO 中的策略设置。</span><span class="sxs-lookup"><span data-stu-id="caf26-226">Change the policy settings in a GPO.</span></span></p></td>
<td align="left"><p><span data-ttu-id="caf26-227">是</span><span class="sxs-lookup"><span data-stu-id="caf26-227">Yes</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="caf26-228">是</span><span class="sxs-lookup"><span data-stu-id="caf26-228">Yes</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="caf26-229">删除 GPO</span><span class="sxs-lookup"><span data-stu-id="caf26-229">Delete GPO</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="caf26-230">删除 GPO。</span><span class="sxs-lookup"><span data-stu-id="caf26-230">Delete a GPO.</span></span></p></td>
<td align="left"><p><span data-ttu-id="caf26-231">是</span><span class="sxs-lookup"><span data-stu-id="caf26-231">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="caf26-232">是</span><span class="sxs-lookup"><span data-stu-id="caf26-232">Yes</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="caf26-233">修改安全性</span><span class="sxs-lookup"><span data-stu-id="caf26-233">Modify Security</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="caf26-234">委派域级别的访问权限，委派对单个 GPO 的访问，并委派对生产环境的访问权限。</span><span class="sxs-lookup"><span data-stu-id="caf26-234">Delegate domain-level access, delegate access to a single GPO, and delegate access to the production environment.</span></span></p></td>
<td align="left"><p><span data-ttu-id="caf26-235">是</span><span class="sxs-lookup"><span data-stu-id="caf26-235">Yes</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="caf26-236">部署 GPO</span><span class="sxs-lookup"><span data-stu-id="caf26-236">Deploy GPO</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="caf26-237">将 GPO 从存档部署到生产环境。</span><span class="sxs-lookup"><span data-stu-id="caf26-237">Deploy a GPO from the archive to the production environment.</span></span></p></td>
<td align="left"><p><span data-ttu-id="caf26-238">是</span><span class="sxs-lookup"><span data-stu-id="caf26-238">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="caf26-239">是</span><span class="sxs-lookup"><span data-stu-id="caf26-239">Yes</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="caf26-240">创建模板</span><span class="sxs-lookup"><span data-stu-id="caf26-240">Create Template</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="caf26-241">在 AGPM 中创建 GPO 模板。</span><span class="sxs-lookup"><span data-stu-id="caf26-241">Create a GPO template in AGPM.</span></span></p></td>
<td align="left"><p><span data-ttu-id="caf26-242">是</span><span class="sxs-lookup"><span data-stu-id="caf26-242">Yes</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="caf26-243">是</span><span class="sxs-lookup"><span data-stu-id="caf26-243">Yes</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="caf26-244">修改选项</span><span class="sxs-lookup"><span data-stu-id="caf26-244">Modify Options</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="caf26-245">配置 AGPM 电子邮件通知，并限制存档中存储的 GPO 版本。</span><span class="sxs-lookup"><span data-stu-id="caf26-245">Configure AGPM e-mail notification and limit the GPO versions stored in the archive.</span></span></p></td>
<td align="left"><p><span data-ttu-id="caf26-246">是</span><span class="sxs-lookup"><span data-stu-id="caf26-246">Yes</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="caf26-247">导出 GPO</span><span class="sxs-lookup"><span data-stu-id="caf26-247">Export GPO</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="caf26-248">将 GPO 导出到文件。</span><span class="sxs-lookup"><span data-stu-id="caf26-248">Export a GPO to a file.</span></span></p></td>
<td align="left"><p><span data-ttu-id="caf26-249">是</span><span class="sxs-lookup"><span data-stu-id="caf26-249">Yes</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="caf26-250">是</span><span class="sxs-lookup"><span data-stu-id="caf26-250">Yes</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="caf26-251">导入 GPO</span><span class="sxs-lookup"><span data-stu-id="caf26-251">Import GPO</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="caf26-252">从文件导入 GPO。</span><span class="sxs-lookup"><span data-stu-id="caf26-252">Import a GPO from a file.</span></span></p></td>
<td align="left"><p><span data-ttu-id="caf26-253">是</span><span class="sxs-lookup"><span data-stu-id="caf26-253">Yes</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="caf26-254">是</span><span class="sxs-lookup"><span data-stu-id="caf26-254">Yes</span></span></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="caf26-255">**注意** 
**导出 gpo**和**导入 GPO**权限在 AGPM 3.0 或2.5 中不可用。</span><span class="sxs-lookup"><span data-stu-id="caf26-255">**Note**
**Export GPO** and **Import GPO** permissions are not available in AGPM 3.0 or 2.5.</span></span>

<span data-ttu-id="caf26-256">在 AGPM 2.5 中不提供在生产环境中委派对域的 Gpo 的访问权限，以及限制存储的 GPO 版本数的能力。</span><span class="sxs-lookup"><span data-stu-id="caf26-256">The ability to delegate access to GPOs in the production environment for a domain and the ability to limit the number of GPO versions stored are not available in AGPM 2.5.</span></span>

 

### <span data-ttu-id="caf26-257">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="caf26-257">Additional references</span></span>

<span data-ttu-id="caf26-258">有关分配了特定角色的组策略管理员可以执行哪些任务或有关执行特定任务所需权限的信息，请参阅[AGPM 的操作指南](https://go.microsoft.com/fwlink/?LinkId=160061)。</span><span class="sxs-lookup"><span data-stu-id="caf26-258">For information about what tasks can be performed by Group Policy administrators assigned a particular role or about which permissions are required to perform a specific task, see the [Operations Guide for AGPM](https://go.microsoft.com/fwlink/?LinkId=160061).</span></span>

 

 





