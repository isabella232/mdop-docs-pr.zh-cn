---
title: 如何使用连接组中的可选程序包
description: 如何使用连接组中的可选程序包
author: dansimp
ms.assetid: 4d08a81b-55e5-471a-91dc-9a684fb3c9a1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 64a2c0758294bfa617d3d85f888cfce3a2c0d21e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798344"
---
# <span data-ttu-id="4230b-103">如何使用连接组中的可选程序包</span><span class="sxs-lookup"><span data-stu-id="4230b-103">How to Use Optional Packages in Connection Groups</span></span>


<span data-ttu-id="4230b-104">从 Microsoft Application Virtualization （App-v） 5.0 SP3 开始，你可以将可选程序包添加到连接组以简化连接组管理。</span><span class="sxs-lookup"><span data-stu-id="4230b-104">Starting in Microsoft Application Virtualization (App-V) 5.0 SP3, you can add optional packages to your connection groups to simplify connection group management.</span></span> <span data-ttu-id="4230b-105">下表总结了使用可选程序包可以更轻松地完成的任务，并提供了指向每个任务的说明的链接。</span><span class="sxs-lookup"><span data-stu-id="4230b-105">The following table summarizes the tasks that you can complete more easily by using optional packages, and provides links to instructions for each task.</span></span>

<span data-ttu-id="4230b-106">**注意** 
**仅在 app-v 5.0 SP3 中支持可选程序包。**</span><span class="sxs-lookup"><span data-stu-id="4230b-106">**Note**
**Optional packages are supported only in App-V 5.0 SP3.**</span></span>

 

<span data-ttu-id="4230b-107">使用可选程序包之前，请参阅[在连接组中使用可选程序包的要求](#bkmk-reqs-using-cg)。</span><span class="sxs-lookup"><span data-stu-id="4230b-107">Before using optional packages, see [Requirements for using optional packages in connection groups](#bkmk-reqs-using-cg).</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4230b-108">链接到说明</span><span class="sxs-lookup"><span data-stu-id="4230b-108">Link to instructions</span></span></th>
<th align="left"><span data-ttu-id="4230b-109">任务</span><span class="sxs-lookup"><span data-stu-id="4230b-109">Task</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="#bkmk-apps-plugs-optional" data-raw-source="[Use one connection group, with optional packages, for multiple users who have different packages entitled to them](#bkmk-apps-plugs-optional)"><span data-ttu-id="4230b-110">对具有不同程序包的多个用户使用一个连接组和可选程序包</span><span class="sxs-lookup"><span data-stu-id="4230b-110">Use one connection group, with optional packages, for multiple users who have different packages entitled to them</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="4230b-111">使用单个连接组，让不同的最终用户可以使用不同组的应用程序和插件。</span><span class="sxs-lookup"><span data-stu-id="4230b-111">Use a single connection group to make different groups of applications and plug-ins available to different end users.</span></span></p>
<p><span data-ttu-id="4230b-112">例如，你希望将 Microsoft Office 分发给所有最终用户，但将不同的插件分发给不同的用户子集。</span><span class="sxs-lookup"><span data-stu-id="4230b-112">For example, you want to distribute Microsoft Office to all end users, but distribute different plug-ins to different subsets of users.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="#bkmk-unpub-del-optl-pkg" data-raw-source="[Unpublish or delete an optional package, or unpublish an optional package and republish it later, without changing the connection group](#bkmk-unpub-del-optl-pkg)"><span data-ttu-id="4230b-113">取消发布或删除可选程序包，或取消发布可选程序包并在以后重新发布，而无需更改连接组</span><span class="sxs-lookup"><span data-stu-id="4230b-113">Unpublish or delete an optional package, or unpublish an optional package and republish it later, without changing the connection group</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="4230b-114">取消发布、删除或重新发布可选程序包，而无需在 App-v 客户端上禁用、删除、编辑、添加和重新启用连接组。</span><span class="sxs-lookup"><span data-stu-id="4230b-114">Unpublish, delete, or republish an optional package without having to disable, remove, edit, add, and re-enable the connection group on the App-V Client.</span></span></p>
<p><span data-ttu-id="4230b-115">您还可以取消发布可选程序包并在以后重新发布，而无需禁用或重新发布连接组。</span><span class="sxs-lookup"><span data-stu-id="4230b-115">You can also unpublish the optional package and republish it later without having to disable or republish the connection group.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-apps-plugs-optional"></a><span data-ttu-id="4230b-116">将一个连接组与可选程序包一起使用，让多个用户有权使用不同的程序包</span><span class="sxs-lookup"><span data-stu-id="4230b-116">Use one connection group, with optional packages, for multiple users with different packages entitled to them</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4230b-117">任务说明</span><span class="sxs-lookup"><span data-stu-id="4230b-117">Task description</span></span></th>
<th align="left"><span data-ttu-id="4230b-118">如何执行任务</span><span class="sxs-lookup"><span data-stu-id="4230b-118">How to perform the task</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="4230b-119">通过 app-v 5.0 SP3</span><span class="sxs-lookup"><span data-stu-id="4230b-119">With App-V 5.0 SP3</span></span></strong></p>
<p><span data-ttu-id="4230b-120">你可以将可选程序包添加到连接组，这使你可以为不同的最终用户提供不同的应用程序和插件组合。</span><span class="sxs-lookup"><span data-stu-id="4230b-120">You can add optional packages to connection groups, which enables you to provide different combinations of applications and plug-ins to different end users.</span></span></p>
<p><strong><span data-ttu-id="4230b-121">示例 </strong> ：你想要将 Microsoft Office 分发给最终用户，但仅为用户子集启用特定插件。</span><span class="sxs-lookup"><span data-stu-id="4230b-121">Example</strong>: You want to distribute Microsoft Office to your end users, but enable a certain plug-in for only a subset of users.</span></span></p>
<p><span data-ttu-id="4230b-122">若要执行此操作，请创建包含带有 Office 的程序包的连接组，以及使用 Office 插件的其他程序包，然后使插件程序包可选。</span><span class="sxs-lookup"><span data-stu-id="4230b-122">To do this, create a connection group that contains a package with Office, and another package with Office plug-ins, and then make the plug-ins package optional.</span></span></p>
<p><span data-ttu-id="4230b-123">不具备插件程序包权利的最终用户仍能运行 Office。</span><span class="sxs-lookup"><span data-stu-id="4230b-123">End users who are not entitled to the plug-in package will still be able to run Office.</span></span></p></td>
<td align="left"><table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4230b-124">方法</span><span class="sxs-lookup"><span data-stu-id="4230b-124">Method</span></span></th>
<th align="left"><span data-ttu-id="4230b-125">步骤</span><span class="sxs-lookup"><span data-stu-id="4230b-125">Steps</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4230b-126">App-v Server-管理控制台</span><span class="sxs-lookup"><span data-stu-id="4230b-126">App-V Server – Management Console</span></span></p></td>
<td align="left"><ol>
<li><p><span data-ttu-id="4230b-127">在管理控制台中，选择 <strong> </strong> "程序包" 以打开 "程序包" 页面。</span><span class="sxs-lookup"><span data-stu-id="4230b-127">In the Management Console, select <strong>PACKAGES</strong> to open the PACKAGES page.</span></span></p></li>
<li><p><span data-ttu-id="4230b-128">选择 " <strong> 连接组 </strong> " 以显示 "连接组" 库。</span><span class="sxs-lookup"><span data-stu-id="4230b-128">Select <strong>CONNECTION GROUPS</strong> to display the Connection Groups library.</span></span></p></li>
<li><p><span data-ttu-id="4230b-129">从 "连接组" 库中选择正确的连接组。</span><span class="sxs-lookup"><span data-stu-id="4230b-129">Select the correct connection group from the Connection Groups library.</span></span></p></li>
<li><p><span data-ttu-id="4230b-130"><strong> </strong> 在 "已连接的程序包" 窗格中单击 "编辑"。</span><span class="sxs-lookup"><span data-stu-id="4230b-130">Click <strong>EDIT</strong> in the CONNECTED PACKAGES pane.</span></span></p></li>
<li><p><span data-ttu-id="4230b-131">选择 <strong> </strong> 程序包名称旁边的 "可选"。</span><span class="sxs-lookup"><span data-stu-id="4230b-131">Select <strong>Optional</strong> next to the package name.</span></span></p></li>
<li><p><span data-ttu-id="4230b-132">选中 " <strong> 添加对组访问的程序包访问权限" </strong> 复选框。</span><span class="sxs-lookup"><span data-stu-id="4230b-132">Select the <strong>ADD PACKAGE ACCESS TO GROUP ACCESS</strong> check box.</span></span> <span data-ttu-id="4230b-133">在将程序包分配给 Active Directory 组时，此必需步骤会将你以前配置的程序包权利添加到连接组。</span><span class="sxs-lookup"><span data-stu-id="4230b-133">This required step adds to the connection group the package entitlements that you configured earlier when you assigned packages to Active Directory groups.</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4230b-134">App-v 服务器-PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="4230b-134">App-V Server - PowerShell cmdlet</span></span></p></td>
<td align="left"><p><span data-ttu-id="4230b-135">使用以下 cmdlet，并指定 <strong> -可选 </strong> 参数：</span><span class="sxs-lookup"><span data-stu-id="4230b-135">Use the following cmdlet, and specify the <strong>-Optional</strong> parameter:</span></span></p>
<p><strong><span data-ttu-id="4230b-136">Add-AppvServerConnectionGroupPackage</span><span class="sxs-lookup"><span data-stu-id="4230b-136">Add-AppvServerConnectionGroupPackage</span></span></strong></p>
<p><strong><span data-ttu-id="4230b-137">语法</span><span class="sxs-lookup"><span data-stu-id="4230b-137">Syntax:</span></span></strong></p>
<p><code>Add-AppvServerConnectionGroupPackage [-AppvServerConnectionGroup] &lt;SerializableConnectionGroup&gt; [[-AppvServerPackage] &lt;PackageVersion&gt;] [-Optional] [-Order &lt;int&gt;] [-UseAnyPackageVersion]</code></p>
<p><strong><span data-ttu-id="4230b-138">示例：</span><span class="sxs-lookup"><span data-stu-id="4230b-138">Example:</span></span></strong></p>
<p><code>Add-AppvServerConnectionGroupPackage -Name &quot;Connection Group 1&quot; -PackageName &quot;Package 1&quot; -Optional</code></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4230b-139">独立计算机上的 app-v 客户端</span><span class="sxs-lookup"><span data-stu-id="4230b-139">App-V Client on a Stand-alone computer</span></span></p></td>
<td align="left"><ol>
<li><p><span data-ttu-id="4230b-140">创建连接组 XML 文档，并将 <strong> 程序包 </strong> 标签属性 IsOptional 设置 <strong> </strong> 为 <strong> "true"。</span><span class="sxs-lookup"><span data-stu-id="4230b-140">Create the connection group XML document, and set the <strong>Package</strong> tag attribute <strong>IsOptional</strong> to <strong>“true”.</span></span></strong></p></li>
<li><p><span data-ttu-id="4230b-141">使用以下 cmdlet 添加和启用连接组：</span><span class="sxs-lookup"><span data-stu-id="4230b-141">Use the following cmdlets to add and enable the connection group:</span></span></p>
<ul>
<li><p><span data-ttu-id="4230b-142">Add-AppvClientConnectionGroup</span><span class="sxs-lookup"><span data-stu-id="4230b-142">Add-AppvClientConnectionGroup</span></span></p></li>
<li><p><span data-ttu-id="4230b-143">Enable-AppvClientConnectionGroup</span><span class="sxs-lookup"><span data-stu-id="4230b-143">Enable-AppvClientConnectionGroup</span></span></p></li>
</ul></li>
</ol>
<p><strong><span data-ttu-id="4230b-144">带有可选程序包的连接组 XML 文档示例：</span><span class="sxs-lookup"><span data-stu-id="4230b-144">Example connection group XML document with optional packages:</span></span></strong></p>
<pre class="syntax" space="preserve"><code>&lt;?xml version=&quot;1.0&quot; ?&gt;
&lt;AppConnectionGroup
   xmlns=&quot;<a href="https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup&amp;quot" data-raw-source="https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup&amp;quot">https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup&quot</a>;
   AppConnectionGroupId=&quot;8105CCD5-244B-4BA1-8888-E321E688D2CB&quot;
   VersionId=&quot;84CE3797-F1CB-4475-A223-757918929EB4&quot;
   DisplayName=&quot;Contoso Software Connection Group&quot; &gt;
&lt;Packages&gt;
&lt;Package
   PackageId=&quot;7735d1a8-5ef9-4df9-a1cf-3aa92ef54fe7&quot;
   VersionId=&quot;ec560d6f-e62e-48eb-a9e5-7c52a8c2e149&quot;
   DisplayName=&quot;Contoso Business Manager&quot;
/&gt;

&lt;Package
   PackageId=&quot;fc6fe0f7-be3d-4643-b37d-fc3f62d4dd5c&quot;
   VersionId=&quot;c67a71cd-3542-4a48-93e8-20c643c50970&quot;
   DisplayName=&quot;Contoso Forms&quot;
   IsOptional=&quot;false&quot;
/&gt;

&lt;Package
   PackageId=&quot;8f6301a5-4348-4039-9560-b27a5bb72711&quot;
   VersionId=&quot;6c694b45-3e19-46c6-a327-d159aa39e1d2&quot;
   DisplayName=&quot;Contoso Tax&quot;
   IsOptional=&quot;true&quot;
/&gt;

&lt;Package
   PackageId=&quot;89d701bc-d507-4299-b6b6-000000003472&quot;
   VersionId=&quot;*&quot;
   DisplayName=&quot;Contoso Accounts&quot;
   IsOptional=&quot;true&quot;
/&gt;

&lt;/Packages&gt;
&lt;/AppConnectionGroup&gt;</code></pre></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="4230b-145">对于早于 app-v 5.0 SP3 的版本</span><span class="sxs-lookup"><span data-stu-id="4230b-145">With versions earlier than App-V 5.0 SP3</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="4230b-146">您必须创建许多连接组才能使特定用户能够使用特定的应用程序和插件组合。</span><span class="sxs-lookup"><span data-stu-id="4230b-146">You had to create many connection groups to make specific application and plug-in combinations available to specific users.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-unpub-del-optl-pkg"></a><span data-ttu-id="4230b-147">取消发布或删除可选程序包，或取消发布可选程序包并在以后重新发布，而无需更改连接组</span><span class="sxs-lookup"><span data-stu-id="4230b-147">Unpublish or delete an optional package, or unpublish an optional package and republish it later, without changing the connection group</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4230b-148">任务说明</span><span class="sxs-lookup"><span data-stu-id="4230b-148">Task description</span></span></th>
<th align="left"><span data-ttu-id="4230b-149">如何执行任务</span><span class="sxs-lookup"><span data-stu-id="4230b-149">How to perform the task</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="4230b-150">通过 app-v 5.0 SP3</span><span class="sxs-lookup"><span data-stu-id="4230b-150">With App-V 5.0 SP3</span></span></strong></p>
<p><span data-ttu-id="4230b-151">你可以取消发布、删除或重新发布位于连接组中的可选程序包，而无需在 App-v 客户端上禁用或重新启用连接组。</span><span class="sxs-lookup"><span data-stu-id="4230b-151">You can unpublish, delete, or republish an optional package, which is in a connection group, without having to disable or re-enable the connection group on the App-V Client.</span></span></p>
<p><span data-ttu-id="4230b-152">您也可以取消发布可选程序包，稍后重新发布它，而无需禁用或重新发布连接组。</span><span class="sxs-lookup"><span data-stu-id="4230b-152">You can also unpublish an optional package and republish it later without having to disable or republish the connection group.</span></span></p>
<p><strong><span data-ttu-id="4230b-153">示例 </strong> ：如果发布包含 Microsoft Office 插件的可选程序包，并且想要删除该插件，则可以取消发布程序包，而无需禁用连接组。</span><span class="sxs-lookup"><span data-stu-id="4230b-153">Example</strong>: If you publish an optional package that contains a Microsoft Office plug-in, and you want to remove the plug-in, you can unpublish the package without having to disable the connection group.</span></span></p></td>
<td align="left"><table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4230b-154">方法</span><span class="sxs-lookup"><span data-stu-id="4230b-154">Method</span></span></th>
<th align="left"><span data-ttu-id="4230b-155">步骤</span><span class="sxs-lookup"><span data-stu-id="4230b-155">Steps</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4230b-156">App-v Server-管理控制台</span><span class="sxs-lookup"><span data-stu-id="4230b-156">App-V Server – Management Console</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="4230b-157">若要取消发布程序包，请执行以下操作：在管理控制台中，选择 "选择 <strong> 程序包" </strong> 页面，右键单击要取消发布的程序包，然后单击 " <strong> 取消发布" </strong> 。</span><span class="sxs-lookup"><span data-stu-id="4230b-157">To unpublish the package: In the Management Console, select elect the <strong>PACKAGES</strong> page, right-click the package that you want to unpublish, and click <strong>unpublish</strong>.</span></span></p></li>
<li><p><span data-ttu-id="4230b-158">若要从连接组中删除可选程序包，请执行以下操作：在 " <strong> 连接组" </strong> 页面上，选择要删除的程序包，然后单击右箭头从左下角的 "连接" 组窗格中删除程序包。</span><span class="sxs-lookup"><span data-stu-id="4230b-158">To remove an optional package from a connection group: On the <strong>CONNECTION GROUPS</strong> page, select the package that you want to remove, and click the right arrow to remove the package from the connection group pane on the bottom left.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4230b-159">独立计算机上的 app-v 客户端</span><span class="sxs-lookup"><span data-stu-id="4230b-159">App-V Client on a Stand-alone computer</span></span></p></td>
<td align="left"><p><span data-ttu-id="4230b-160">使用以下现有 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="4230b-160">Use the following existing cmdlets:</span></span></p>
<ul>
<li><p><span data-ttu-id="4230b-161">取消发布-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="4230b-161">Unpublish-AppvClientPackage</span></span></p></li>
<li><p><span data-ttu-id="4230b-162">Remove-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="4230b-162">Remove-AppvClientPackage</span></span></p></li>
</ul>
<p><span data-ttu-id="4230b-163">有关详细信息，请参阅 <a href="how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md" data-raw-source="[How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md)"> 使用 PowerShell 管理独立计算机上运行的 app-v 5.0 程序包 </a> 。</span><span class="sxs-lookup"><span data-stu-id="4230b-163">For more information, see <a href="how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md" data-raw-source="[How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md)">How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell</a>.</span></span></p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="4230b-164">对于早于 app-v 5.0 SP3 的版本</span><span class="sxs-lookup"><span data-stu-id="4230b-164">With versions earlier than App-V 5.0 SP3</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="4230b-165">您必须：</span><span class="sxs-lookup"><span data-stu-id="4230b-165">You had to:</span></span></p>
<ol>
<li><p><span data-ttu-id="4230b-166">从每个已启用的 App-v 客户端计算机中删除连接组。</span><span class="sxs-lookup"><span data-stu-id="4230b-166">Remove the connection group from each App-V Client computer where it was enabled.</span></span></p></li>
<li><p><span data-ttu-id="4230b-167">取消发布程序包。</span><span class="sxs-lookup"><span data-stu-id="4230b-167">Unpublish the package.</span></span></p></li>
<li><p><span data-ttu-id="4230b-168">从连接组的定义中删除程序包。</span><span class="sxs-lookup"><span data-stu-id="4230b-168">Remove the package from the connection group’s definition.</span></span></p></li>
<li><p><span data-ttu-id="4230b-169">重新发布连接组。</span><span class="sxs-lookup"><span data-stu-id="4230b-169">Republish the connection group.</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-reqs-using-cg"></a><span data-ttu-id="4230b-170">在连接组中使用可选程序包的要求</span><span class="sxs-lookup"><span data-stu-id="4230b-170">Requirements for using optional packages in connection groups</span></span>


<span data-ttu-id="4230b-171">在连接组中使用可选程序包之前，请查看以下要求：</span><span class="sxs-lookup"><span data-stu-id="4230b-171">Review the following requirements before using optional packages in connection groups:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4230b-172">要求</span><span class="sxs-lookup"><span data-stu-id="4230b-172">Requirement</span></span></th>
<th align="left"><span data-ttu-id="4230b-173">详细信息</span><span class="sxs-lookup"><span data-stu-id="4230b-173">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4230b-174">连接组必须至少包含一个非可选程序包。</span><span class="sxs-lookup"><span data-stu-id="4230b-174">Connection groups must contain at least one non-optional package.</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="4230b-175">请仔细检查你是否满足此要求，因为 App-v Server 和 PowerShell cmdlet 不会验证是否已满足要求。</span><span class="sxs-lookup"><span data-stu-id="4230b-175">Check carefully that you meet this requirement, as the App-V Server and the PowerShell cmdlet don’t validate that the requirement has been met.</span></span></p></li>
<li><p><span data-ttu-id="4230b-176">如果您意外创建了一个不包含至少一个非可选程序包的连接组，并且最终用户尝试在该连接组中打开一个打包的应用程序，则连接组将失败。</span><span class="sxs-lookup"><span data-stu-id="4230b-176">If you accidentally create a connection group that does not contain at least one non-optional package, and the end user tries to open a packaged application in that connection group, the connection group will fail.</span></span></p></li>
</ul>
<p></p></td>
</tr>
<tr class="even">
<td align="left"><ul>
<li><p><span data-ttu-id="4230b-177">用户发布的连接组可以包含全局发布或向用户发布的程序包。</span><span class="sxs-lookup"><span data-stu-id="4230b-177">User-published connection groups can contain packages that are published globally or to the user.</span></span></p></li>
<li><p><span data-ttu-id="4230b-178">全局发布的连接组必须仅包含全局发布的程序包。</span><span class="sxs-lookup"><span data-stu-id="4230b-178">Globally published connection groups must contain only globally published packages.</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="4230b-179">全局发布的连接组必须包含全局发布的程序包，以确保程序包将在启动连接组的虚拟环境时可用。</span><span class="sxs-lookup"><span data-stu-id="4230b-179">Globally published connection groups must contain packages that are published globally to ensure that the packages will be available when starting the connection group’s virtual environment.</span></span></p>
<p><span data-ttu-id="4230b-180">如果你尝试添加或启用包含用户发布的程序包的全局发布的连接组，则连接组将失败。</span><span class="sxs-lookup"><span data-stu-id="4230b-180">If you try to add or enable globally published connection groups that contain user-published packages, the connection group will fail.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4230b-181">发布包含这些程序包的连接组之前，必须发布所有非可选程序包。</span><span class="sxs-lookup"><span data-stu-id="4230b-181">You must publish all non-optional packages before publishing the connection group that contains those packages.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4230b-182">如果缺少任何非可选程序包，则连接组的虚拟环境无法启动。</span><span class="sxs-lookup"><span data-stu-id="4230b-182">A connection group’s virtual environment cannot start if any non-optional packages are missing.</span></span></p>
<p><span data-ttu-id="4230b-183">如果未发布任何非可选程序包，则 App-v 客户端无法添加或启用连接组。</span><span class="sxs-lookup"><span data-stu-id="4230b-183">The App-V Client fails to add or enable a connection group if any non-optional packages have not been published.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4230b-184">取消发布全局发布的程序包之前，请确保有权使用该计算机上所有用户的连接组不再需要该程序包。</span><span class="sxs-lookup"><span data-stu-id="4230b-184">Before you unpublish a globally published package, ensure that the connection groups that are entitled to all the users on that computer no longer require the package.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4230b-185">系统不检查软件包是否属于另一个用户的连接组。</span><span class="sxs-lookup"><span data-stu-id="4230b-185">The system does not check whether the package is part of another user’s connection group.</span></span> <span data-ttu-id="4230b-186">取消发布全局程序包将使该计算机上的每个用户都无法使用它，因此请确保每个用户的连接组不再包含该程序包，或者将程序包设置为可选程序包。</span><span class="sxs-lookup"><span data-stu-id="4230b-186">Unpublishing a global package will make it unavailable to every user on that computer, so make sure that each user’s connection groups no longer contain the package, or alternatively make the package optional.</span></span></p></td>
</tr>
</tbody>
</table>

 






## <span data-ttu-id="4230b-187">相关主题</span><span class="sxs-lookup"><span data-stu-id="4230b-187">Related topics</span></span>


[<span data-ttu-id="4230b-188">管理连接组</span><span class="sxs-lookup"><span data-stu-id="4230b-188">Managing Connection Groups</span></span>](managing-connection-groups.md)

 

 





