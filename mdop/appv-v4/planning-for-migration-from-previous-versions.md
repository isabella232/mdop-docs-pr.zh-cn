---
title: 规划从之前的版本进行迁移
description: 规划从之前的版本进行迁移
author: dansimp
ms.assetid: 62967bf1-542f-41b0-838f-c62f3430ac73
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9b239e09da06270b30b401151cf12e817e2cf8d4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798869"
---
# <span data-ttu-id="20bd6-103">规划从之前的版本进行迁移</span><span class="sxs-lookup"><span data-stu-id="20bd6-103">Planning for Migration from Previous Versions</span></span>


<span data-ttu-id="20bd6-104">在尝试升级到 Microsoft Application Virtualization 4.5 或更高版本之前，必须将4.1 之前的任何版本升级到版本4.1。</span><span class="sxs-lookup"><span data-stu-id="20bd6-104">Before attempting to upgrade to Microsoft Application Virtualization4.5 or later versions, any version prior to4.1 must be upgraded to version4.1.</span></span> <span data-ttu-id="20bd6-105">你应该首先计划升级客户端，然后升级服务器组件。</span><span class="sxs-lookup"><span data-stu-id="20bd6-105">You should plan to upgrade your clients first, and then upgrade the server components.</span></span> <span data-ttu-id="20bd6-106">已升级到4.5 的客户端将继续处理尚未升级的 Application Virtualization 服务器。</span><span class="sxs-lookup"><span data-stu-id="20bd6-106">Clients that have been upgraded to4.5 will continue to work with Application Virtualization servers that have not yet been upgraded.</span></span> <span data-ttu-id="20bd6-107">升级到4.5 的服务器不支持早期版本的客户端。</span><span class="sxs-lookup"><span data-stu-id="20bd6-107">Earlier versions of the client are not supported on servers that have been upgraded to4.5.</span></span> <span data-ttu-id="20bd6-108">有关升级系统组件的详细信息，请参阅[应用程序虚拟化部署和升级注意事项](application-virtualization-deployment-and-upgrade-considerations.md)。</span><span class="sxs-lookup"><span data-stu-id="20bd6-108">For more information about upgrading the system components, see [Application Virtualization Deployment and Upgrade Considerations](application-virtualization-deployment-and-upgrade-considerations.md).</span></span>

<span data-ttu-id="20bd6-109">为了帮助确保迁移成功，应按照以下顺序升级应用程序虚拟化系统组件：</span><span class="sxs-lookup"><span data-stu-id="20bd6-109">To help ensure a successful migration, the Application Virtualization system components should be upgraded in the following order:</span></span>

1.  **<span data-ttu-id="20bd6-110">Microsoft Application Virtualization 客户端。</span><span class="sxs-lookup"><span data-stu-id="20bd6-110">Microsoft Application Virtualization Clients.</span></span>** <span data-ttu-id="20bd6-111">有关分步升级说明，请参阅[如何升级应用程序虚拟化客户端](how-to-upgrade-the-application-virtualization-client.md)。</span><span class="sxs-lookup"><span data-stu-id="20bd6-111">For step-by-step upgrade instructions, see [How to Upgrade the Application Virtualization Client](how-to-upgrade-the-application-virtualization-client.md).</span></span>

2.  **<span data-ttu-id="20bd6-112">Microsoft Application Virtualization 服务器和数据库。</span><span class="sxs-lookup"><span data-stu-id="20bd6-112">Microsoft Application Virtualization Servers and Database.</span></span>** <span data-ttu-id="20bd6-113">有关分步升级说明，请参阅[如何升级服务器和系统组件](how-to-upgrade-the-servers-and-system-components.md)。</span><span class="sxs-lookup"><span data-stu-id="20bd6-113">For step-by-step upgrade instructions, see [How to Upgrade the Servers and System Components](how-to-upgrade-the-servers-and-system-components.md).</span></span>

    <span data-ttu-id="20bd6-114">**注意** 如果您有多个服务器共享访问应用程序虚拟化数据库，则所有这些服务器都必须在数据库升级时联机。</span><span class="sxs-lookup"><span data-stu-id="20bd6-114">**Note** If you have more than one server sharing access to the Application Virtualization database, all those servers must be taken offline while the database is being upgraded.</span></span> <span data-ttu-id="20bd6-115">你应遵循数据库升级的正常业务做法，但强烈建议你先在测试服务器上使用数据库的备份副本测试数据库升级。</span><span class="sxs-lookup"><span data-stu-id="20bd6-115">You should follow your normal business practices for the database upgrade, but it is highly advisable that you test the database upgrade by using a backup copy of the database first on a test server.</span></span> <span data-ttu-id="20bd6-116">然后，你应该选择其中一个服务器进行首次升级，这将升级数据库架构。</span><span class="sxs-lookup"><span data-stu-id="20bd6-116">Then, you should select one of the servers for the first upgrade, which will upgrade the database schema.</span></span> <span data-ttu-id="20bd6-117">成功升级生产数据库后，您可以升级其他服务器。</span><span class="sxs-lookup"><span data-stu-id="20bd6-117">After the production database has been successfully upgraded, you can upgrade the other servers.</span></span>

     

3.  **<span data-ttu-id="20bd6-118">Microsoft Application Virtualization 管理 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="20bd6-118">Microsoft Application Virtualization Management Web Service.</span></span>** <span data-ttu-id="20bd6-119">此步骤仅适用于管理 Web 服务位于单独服务器上的情况，这将要求你在单独的服务器上运行服务器安装程序以升级 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="20bd6-119">This step applies only if the Management Web Service is on a separate server, which would require that you run the server installer program on that separate server to upgrade the Web service.</span></span> <span data-ttu-id="20bd6-120">否则，以前的服务器升级步骤将自动升级管理 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="20bd6-120">Otherwise, the previous server upgrade step will automatically upgrade the Management Web Service.</span></span>

4.  **<span data-ttu-id="20bd6-121">Microsoft Application Virtualization 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="20bd6-121">Microsoft Application Virtualization Management Console.</span></span>** <span data-ttu-id="20bd6-122">此步骤仅适用于管理控制台位于单独计算机上的情况，这需要你在单独的计算机上运行服务器安装程序才能升级该控制台。</span><span class="sxs-lookup"><span data-stu-id="20bd6-122">This step applies only if the Management Console is on a separate computer, which would require that you run the server installer program on that separate computer to upgrade the console.</span></span> <span data-ttu-id="20bd6-123">否则，以前的服务器升级步骤将升级管理控制台。</span><span class="sxs-lookup"><span data-stu-id="20bd6-123">Otherwise, the previous server upgrade step will upgrade the Management Console.</span></span>

5.  **<span data-ttu-id="20bd6-124">Microsoft Application Virtualization Sequencer。</span><span class="sxs-lookup"><span data-stu-id="20bd6-124">Microsoft Application Virtualization Sequencer.</span></span>** <span data-ttu-id="20bd6-125">有关分步说明，请参阅[如何安装 Application Virtualization Sequencer](how-to-install-the-application-virtualization-sequencer.md)。</span><span class="sxs-lookup"><span data-stu-id="20bd6-125">For step-by-step instructions, see [How to Install the Application Virtualization Sequencer](how-to-install-the-application-virtualization-sequencer.md).</span></span> <span data-ttu-id="20bd6-126">在版本4.2 中排序的任何虚拟应用程序包无需重新排序，即可与版本4.5 配合使用。</span><span class="sxs-lookup"><span data-stu-id="20bd6-126">Any virtual application packages sequenced in version4.2 will not have to be re-sequenced for use with version4.5.</span></span> <span data-ttu-id="20bd6-127">但是，如果你想要应用默认的访问控制列表（Acl）或生成 Windows Installer 文件，应考虑将虚拟程序包升级为 Microsoft Application Virtualization 4.5 格式。</span><span class="sxs-lookup"><span data-stu-id="20bd6-127">However, you should consider upgrading the virtual packages to the Microsoft Application Virtualization4.5 format if you would like to apply default access control lists (ACLs) or generate a Windows Installer file.</span></span> <span data-ttu-id="20bd6-128">这是一个简单的过程，只要求使用4.5 排序器打开和保存现有虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="20bd6-128">This is a simple process and requires only that the existing virtual application package be opened and saved with the4.5 Sequencer.</span></span> <span data-ttu-id="20bd6-129">可通过使用应用程序虚拟化 Sequencer 命令行界面自动执行此操作。</span><span class="sxs-lookup"><span data-stu-id="20bd6-129">This can be automated by using the Application Virtualization Sequencer command-line interface.</span></span>

## <a href="" id="app-v-4-6-client-package-support-"></a><span data-ttu-id="20bd6-130">App-v 4.6 客户端软件包支持</span><span class="sxs-lookup"><span data-stu-id="20bd6-130">App-V4.6 Client Package Support</span></span>


<span data-ttu-id="20bd6-131">你可以将在早期版本的 app-v 中创建的程序包部署到 App-v 4.6 客户端。</span><span class="sxs-lookup"><span data-stu-id="20bd6-131">You can deploy packages created in previous versions of App-V to App-V4.6 Clients.</span></span> <span data-ttu-id="20bd6-132">但是，你必须修改关联的 **.osd**文件，以便它包括相应的操作系统和芯片体系结构信息。</span><span class="sxs-lookup"><span data-stu-id="20bd6-132">However, you must modify the associated **.osd** file so that it includes the appropriate operating system and chip architecture information.</span></span> <span data-ttu-id="20bd6-133">使用以下值。</span><span class="sxs-lookup"><span data-stu-id="20bd6-133">Use the following values.</span></span>

<table>
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="20bd6-134">操作系统值</span><span class="sxs-lookup"><span data-stu-id="20bd6-134">OS Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="20bd6-135">&lt;OS 值 = "Win2003TS"/&gt;</span><span class="sxs-lookup"><span data-stu-id="20bd6-135">&lt;OS VALUE=”Win2003TS”/&gt;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="20bd6-136">&lt;OS 值 = "Win2003TS64"/&gt;</span><span class="sxs-lookup"><span data-stu-id="20bd6-136">&lt;OS VALUE=”Win2003TS64”/&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="20bd6-137">&lt;OS 值 = "Win2008TS"/&gt;</span><span class="sxs-lookup"><span data-stu-id="20bd6-137">&lt;OS VALUE=”Win2008TS”/&gt;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="20bd6-138">&lt;OS 值 = "Win2008TS64"/&gt;</span><span class="sxs-lookup"><span data-stu-id="20bd6-138">&lt;OS VALUE=”Win2008TS64”/&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="20bd6-139">&lt;OS 值 = "Win2008R2TS64"/&gt;</span><span class="sxs-lookup"><span data-stu-id="20bd6-139">&lt;OS VALUE=”Win2008R2TS64”/&gt;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="20bd6-140">&lt;OS 值 = "Win7"/&gt;</span><span class="sxs-lookup"><span data-stu-id="20bd6-140">&lt;OS VALUE=”Win7”/&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="20bd6-141">&lt;OS 值 = "Win764"/&gt;</span><span class="sxs-lookup"><span data-stu-id="20bd6-141">&lt;OS VALUE=”Win764”/&gt;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="20bd6-142">&lt;OS 值 = "WinVista"/&gt;</span><span class="sxs-lookup"><span data-stu-id="20bd6-142">&lt;OS VALUE=”WinVista”/&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="20bd6-143">&lt;OS 值 = "WinVista64"/&gt;</span><span class="sxs-lookup"><span data-stu-id="20bd6-143">&lt;OS VALUE=”WinVista64”/&gt;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="20bd6-144">&lt;OS 值 = "WinXP"/&gt;</span><span class="sxs-lookup"><span data-stu-id="20bd6-144">&lt;OS VALUE=”WinXP”/&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="20bd6-145">&lt;OS 值 = "WinXP64"/&gt;</span><span class="sxs-lookup"><span data-stu-id="20bd6-145">&lt;OS VALUE=”WinXP64”/&gt;</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="20bd6-146">若要运行新创建的32位程序包，必须在运行32位操作系统的计算机上对应用程序进行排序，安装了 app-v 4.6 Sequencer。</span><span class="sxs-lookup"><span data-stu-id="20bd6-146">To run a newly created 32-bit package, you must sequence the application on a computer running a 32-bit operating system with the App-V4.6 Sequencer installed.</span></span> <span data-ttu-id="20bd6-147">对应用程序进行排序后，在 Sequencer 控制台中，选择 "**部署**" 选项卡，然后根据需要指定相应的操作系统和芯片体系结构。</span><span class="sxs-lookup"><span data-stu-id="20bd6-147">After you have sequenced the application, in the Sequencer console, select the **Deployment** tab and then specify the appropriate operating system and chip architecture as required.</span></span>

<span data-ttu-id="20bd6-148">**重要提示** 在运行64位操作系统的计算机上排序的应用程序必须部署到运行64位操作系统的计算机上。</span><span class="sxs-lookup"><span data-stu-id="20bd6-148">**Important** Applications sequenced on a computer running a 64-bit operating system must be deployed to computers running a 64-bit operating system.</span></span> <span data-ttu-id="20bd6-149">使用 app-v 4.6 Sequencer 创建的新32位程序包将不会在运行 App-v 4.5 客户端的计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="20bd6-149">New 32-bit packages created by using the App-V4.6 Sequencer will not run on computers running the App-V 4.5 Client.</span></span>

 

<span data-ttu-id="20bd6-150">若要在 App-V 4.6 客户端上运行新的64位程序包，必须在运行 App-v 4.6 Sequencer 和运行64位操作系统的计算机上对应用程序进行排序。</span><span class="sxs-lookup"><span data-stu-id="20bd6-150">To run new 64-bit packages on the App-V4.6 Client, you must sequence the application on a computer running the App-V4.6 Sequencer and that is running a 64-bit operating system.</span></span> <span data-ttu-id="20bd6-151">对应用程序进行排序后，在 Sequencer 控制台中，选择 "**部署**" 选项卡，然后根据需要指定相应的操作系统和芯片体系结构。</span><span class="sxs-lookup"><span data-stu-id="20bd6-151">After you have sequenced the application, in the Sequencer console, select the **Deployment** tab and then specify the appropriate operating system and chip architecture as required.</span></span>

<span data-ttu-id="20bd6-152">下表列出了哪些客户端版本将运行使用各种版本的 Sequencer 创建的程序包。</span><span class="sxs-lookup"><span data-stu-id="20bd6-152">The following table lists which client versions will run packages created by using the various versions of the Sequencer.</span></span>

<table style="width:100%;">
<colgroup>
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left"><span data-ttu-id="20bd6-153">使用 app-v 4.2 Sequencer 进行排序</span><span class="sxs-lookup"><span data-stu-id="20bd6-153">Sequenced by using the App-V 4.2 Sequencer</span></span></th>
<th align="left"><span data-ttu-id="20bd6-154">使用 app-v 4.5 Sequencer 进行排序</span><span class="sxs-lookup"><span data-stu-id="20bd6-154">Sequenced by using the App-V 4.5 Sequencer</span></span></th>
<th align="left"><span data-ttu-id="20bd6-155">使用32位 App-v 4.6 Sequencer 进行排序</span><span class="sxs-lookup"><span data-stu-id="20bd6-155">Sequenced by using the 32-bit App-V 4.6 Sequencer</span></span></th>
<th align="left"><span data-ttu-id="20bd6-156">使用64位 App-v 4.6 Sequencer 进行排序</span><span class="sxs-lookup"><span data-stu-id="20bd6-156">Sequenced by using the 64-bit App-V 4.6 Sequencer</span></span></th>
<th align="left"><span data-ttu-id="20bd6-157">使用32位 App-v 4.6 SP1 排序器进行排序</span><span class="sxs-lookup"><span data-stu-id="20bd6-157">Sequenced by using the 32-bit App-V 4.6 SP1 Sequencer</span></span></th>
<th align="left"><span data-ttu-id="20bd6-158">使用64位 App-v 4.6 SP1 排序器进行排序</span><span class="sxs-lookup"><span data-stu-id="20bd6-158">Sequenced by using the 64-bit App-V 4.6 SP1 Sequencer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="20bd6-159">4.2 客户端</span><span class="sxs-lookup"><span data-stu-id="20bd6-159">4.2 Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="20bd6-160">是</span><span class="sxs-lookup"><span data-stu-id="20bd6-160">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="20bd6-161">否</span><span class="sxs-lookup"><span data-stu-id="20bd6-161">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="20bd6-162">否</span><span class="sxs-lookup"><span data-stu-id="20bd6-162">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="20bd6-163">否</span><span class="sxs-lookup"><span data-stu-id="20bd6-163">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="20bd6-164">否</span><span class="sxs-lookup"><span data-stu-id="20bd6-164">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="20bd6-165">否</span><span class="sxs-lookup"><span data-stu-id="20bd6-165">No</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="20bd6-166">4.5 客户端¹</span><span class="sxs-lookup"><span data-stu-id="20bd6-166">4.5 Client ¹</span></span></p></td>
<td align="left"><p><span data-ttu-id="20bd6-167">是</span><span class="sxs-lookup"><span data-stu-id="20bd6-167">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="20bd6-168">是</span><span class="sxs-lookup"><span data-stu-id="20bd6-168">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="20bd6-169">否</span><span class="sxs-lookup"><span data-stu-id="20bd6-169">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="20bd6-170">否</span><span class="sxs-lookup"><span data-stu-id="20bd6-170">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="20bd6-171">否</span><span class="sxs-lookup"><span data-stu-id="20bd6-171">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="20bd6-172">否</span><span class="sxs-lookup"><span data-stu-id="20bd6-172">No</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="20bd6-173">4.6 客户端（32位）</span><span class="sxs-lookup"><span data-stu-id="20bd6-173">4.6 Client (32-bit)</span></span></p></td>
<td align="left"><p><span data-ttu-id="20bd6-174">是</span><span class="sxs-lookup"><span data-stu-id="20bd6-174">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="20bd6-175">是</span><span class="sxs-lookup"><span data-stu-id="20bd6-175">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="20bd6-176">是</span><span class="sxs-lookup"><span data-stu-id="20bd6-176">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="20bd6-177">不可用</span><span class="sxs-lookup"><span data-stu-id="20bd6-177">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="20bd6-178">是</span><span class="sxs-lookup"><span data-stu-id="20bd6-178">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="20bd6-179">否</span><span class="sxs-lookup"><span data-stu-id="20bd6-179">No</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="20bd6-180">4.6 客户端（64位）</span><span class="sxs-lookup"><span data-stu-id="20bd6-180">4.6 Client (64-bit)</span></span></p></td>
<td align="left"><p><span data-ttu-id="20bd6-181">是</span><span class="sxs-lookup"><span data-stu-id="20bd6-181">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="20bd6-182">是</span><span class="sxs-lookup"><span data-stu-id="20bd6-182">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="20bd6-183">是</span><span class="sxs-lookup"><span data-stu-id="20bd6-183">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="20bd6-184">是</span><span class="sxs-lookup"><span data-stu-id="20bd6-184">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="20bd6-185">是</span><span class="sxs-lookup"><span data-stu-id="20bd6-185">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="20bd6-186">是</span><span class="sxs-lookup"><span data-stu-id="20bd6-186">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="20bd6-187">4.6 SP1 客户端</span><span class="sxs-lookup"><span data-stu-id="20bd6-187">4.6 SP1 Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="20bd6-188">是</span><span class="sxs-lookup"><span data-stu-id="20bd6-188">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="20bd6-189">是</span><span class="sxs-lookup"><span data-stu-id="20bd6-189">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="20bd6-190">是</span><span class="sxs-lookup"><span data-stu-id="20bd6-190">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="20bd6-191">不可用</span><span class="sxs-lookup"><span data-stu-id="20bd6-191">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="20bd6-192">是</span><span class="sxs-lookup"><span data-stu-id="20bd6-192">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="20bd6-193">否</span><span class="sxs-lookup"><span data-stu-id="20bd6-193">No</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="20bd6-194">4.6 SP1 客户端（64位）</span><span class="sxs-lookup"><span data-stu-id="20bd6-194">4.6 SP1 Client (64-bit)</span></span></p></td>
<td align="left"><p><span data-ttu-id="20bd6-195">是</span><span class="sxs-lookup"><span data-stu-id="20bd6-195">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="20bd6-196">是</span><span class="sxs-lookup"><span data-stu-id="20bd6-196">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="20bd6-197">是</span><span class="sxs-lookup"><span data-stu-id="20bd6-197">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="20bd6-198">是</span><span class="sxs-lookup"><span data-stu-id="20bd6-198">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="20bd6-199">是</span><span class="sxs-lookup"><span data-stu-id="20bd6-199">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="20bd6-200">是</span><span class="sxs-lookup"><span data-stu-id="20bd6-200">Yes</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="20bd6-201">¹适用于应用-v 4.5 客户端的所有版本，包括 App-v 4.5、app-v 4.5 CU1 和 App-v 4.5 SP1。</span><span class="sxs-lookup"><span data-stu-id="20bd6-201">¹Applies to all versions of the App-V4.5 Client, including App-V4.5, App-V4.5CU1 and App-V4.5 SP1.</span></span>

## <span data-ttu-id="20bd6-202">其他迁移注意事项</span><span class="sxs-lookup"><span data-stu-id="20bd6-202">Additional Migration Considerations</span></span>


<span data-ttu-id="20bd6-203">App-v 4.5 排序器的功能之一是将 Windows Installer 文件（.msi）创建为虚拟应用程序包与电子软件分发（ESD）系统（如 Microsoft 终结点配置管理器）的互操作性的控制点。</span><span class="sxs-lookup"><span data-stu-id="20bd6-203">One of the features of the App-V4.5 Sequencer is the ability to create Windows Installer files (.msi) as control points for virtual application package interoperability with electronic software distribution (ESD) systems such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="20bd6-204">使用 .msi 工具创建的以前的 Windows 安装程序文件，这些文件已安装在应用程序虚拟化的应用程序虚拟化（随后升级到4.5 的客户端）上，但它们不能安装在4.5 客户端上。</span><span class="sxs-lookup"><span data-stu-id="20bd6-204">Previous Windows Installer files created with the .msi tool for Application Virtualization that were installed on a App-V4.1 or4.2 Client that is subsequently upgraded to4.5 continue to work, although they cannot be installed on the4.5 Client.</span></span> <span data-ttu-id="20bd6-205">但是，除非在4.5 排序器中升级，否则无法删除或升级它们。</span><span class="sxs-lookup"><span data-stu-id="20bd6-205">However, they cannot be removed or upgraded unless they are upgraded in the4.5 Sequencer.</span></span> <span data-ttu-id="20bd6-206">需要在4.5 排序器中打开原始的4.5 虚拟应用程序包，然后将其另存为 Windows Installer 文件。</span><span class="sxs-lookup"><span data-stu-id="20bd6-206">The original pre-4.5 virtual application package would need to be opened in the4.5 Sequencer and then saved as a Windows Installer File.</span></span>

<span data-ttu-id="20bd6-207">**注意** 如果应用程序 V 4.2 客户端已升级到4.5，则可以使用脚本作为解决方法来在4.5 客户端上保留4.2 程序包，并允许对其进行管理。</span><span class="sxs-lookup"><span data-stu-id="20bd6-207">**Note** If the App-V4.2 Client has already been upgraded to4.5, it is possible to use script as a workaround to preserve the4.2 packages on4.5 clients and allow them to be managed.</span></span> <span data-ttu-id="20bd6-208">此脚本必须将两个文件（msvcp71.dll 和 msvcr71.dll）复制到 App-v 安装文件夹，并在注册表项 \ [HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\] 下设置以下注册表项值：</span><span class="sxs-lookup"><span data-stu-id="20bd6-208">This script must copy two files, msvcp71.dll and msvcr71.dll, to the App-V installation folder and set the following registry key values under the registry key \[HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\]:</span></span>

<span data-ttu-id="20bd6-209">"ClientVersion" = "4.2.1.20"</span><span class="sxs-lookup"><span data-stu-id="20bd6-209">"ClientVersion"="4.2.1.20"</span></span>

<span data-ttu-id="20bd6-210">"GlobalDataDirectory" = "C:\\\\Documents 和 Settings\\\\All Users\\\\Documents\\\\" （全局可写位置）</span><span class="sxs-lookup"><span data-stu-id="20bd6-210">"GlobalDataDirectory"="C:\\\\Documents and Settings\\\\All Users\\\\Documents\\\\" (a globally writeable location)</span></span>

 

<span data-ttu-id="20bd6-211">当你尝试在 App-v 4.6 客户端上运行时，由 app-v 4.5 Sequencer 生成的 Windows Installer 文件将显示错误消息 "此程序包需要 Microsoft Application Virtualization 客户端4.5 或更高版本"。</span><span class="sxs-lookup"><span data-stu-id="20bd6-211">Windows Installer files generated by the App-V 4.5 Sequencer display the error message "This package requires Microsoft Application Virtualization Client 4.5 or later" when you try to run them on an App-V 4.6 Client.</span></span> <span data-ttu-id="20bd6-212">使用 app-v 4.5 SP1 Sequencer 或 App-v 4.6 排序器打开旧程序包，并为程序包生成新的 .msi。</span><span class="sxs-lookup"><span data-stu-id="20bd6-212">Open the old package with either the App-V 4.5 SP1 Sequencer or the App-V 4.6 Sequencer and generate a new .msi for the package.</span></span>

<span data-ttu-id="20bd6-213">当服务器升级到4.5 时，创建和保存的任何4.2 报告将被覆盖。</span><span class="sxs-lookup"><span data-stu-id="20bd6-213">Any4.2 reports that were created and saved will be overwritten when the server is upgraded to4.5.</span></span> <span data-ttu-id="20bd6-214">如果需要保留这些报表，则必须保存位于服务器的 SoftGrid 管理控制台文件夹中的 SftMMC 文件的备份副本，然后使用该副本替换升级期间安装的新 SftMMC。</span><span class="sxs-lookup"><span data-stu-id="20bd6-214">If you need to keep these reports, you must save a backup copy of the SftMMC.msc file located in the SoftGrid Management Console folder on the server and use that copy to replace the new SftMMC.msc that is installed during the upgrade.</span></span>

<span data-ttu-id="20bd6-215">有关从早期版本升级的其他信息，请参阅[升级到 Microsoft Application Virtualization 4.5 常见问题](https://go.microsoft.com/fwlink/?LinkId=120358)（ https://go.microsoft.com/fwlink/?LinkId=120358) 。</span><span class="sxs-lookup"><span data-stu-id="20bd6-215">For additional information about upgrading from previous versions, see [Upgrading to Microsoft Application Virtualization 4.5 FAQ](https://go.microsoft.com/fwlink/?LinkId=120358) (https://go.microsoft.com/fwlink/?LinkId=120358).</span></span>

## <span data-ttu-id="20bd6-216">相关主题</span><span class="sxs-lookup"><span data-stu-id="20bd6-216">Related topics</span></span>


[<span data-ttu-id="20bd6-217">规划 Application Virtualization System 部署</span><span class="sxs-lookup"><span data-stu-id="20bd6-217">Planning for Application Virtualization System Deployment</span></span>](planning-for-application-virtualization-system-deployment.md)

 

 





