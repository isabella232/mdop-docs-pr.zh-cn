---
title: 如何使用 PowerShell 管理在独立计算机上运行的 App-V 5.1 程序包
description: 如何使用 PowerShell 管理在独立计算机上运行的 App-V 5.1 程序包
author: dansimp
ms.assetid: c3fd06f6-102f-43d1-a577-d5ced6ac537d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: b454014da4e5f349af913d3fea8ea3837598a039
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798415"
---
# <span data-ttu-id="20c17-103">如何使用 PowerShell 管理在独立计算机上运行的 App-V 5.1 程序包</span><span class="sxs-lookup"><span data-stu-id="20c17-103">How to Manage App-V 5.1 Packages Running on a Stand-Alone Computer by Using PowerShell</span></span>


<span data-ttu-id="20c17-104">以下各部分介绍了如何使用 PowerShell 在独立客户端计算机上执行各种管理任务：</span><span class="sxs-lookup"><span data-stu-id="20c17-104">The following sections explain how to perform various management tasks on a stand-alone client computer by using PowerShell:</span></span>

-   [<span data-ttu-id="20c17-105">返回程序包列表</span><span class="sxs-lookup"><span data-stu-id="20c17-105">To return a list of packages</span></span>](#bkmk-return-pkgs-standalone-posh)

-   [<span data-ttu-id="20c17-106">添加程序包</span><span class="sxs-lookup"><span data-stu-id="20c17-106">To add a package</span></span>](#bkmk-add-pkgs-standalone-posh)

-   [<span data-ttu-id="20c17-107">发布程序包</span><span class="sxs-lookup"><span data-stu-id="20c17-107">To publish a package</span></span>](#bkmk-pub-pkg-standalone-posh)

-   [<span data-ttu-id="20c17-108">将程序包发布到特定用户</span><span class="sxs-lookup"><span data-stu-id="20c17-108">To publish a package to a specific user</span></span>](#bkmk-pub-pkg-a-user-standalone-posh)

-   [<span data-ttu-id="20c17-109">添加和发布程序包</span><span class="sxs-lookup"><span data-stu-id="20c17-109">To add and publish a package</span></span>](#bkmk-add-pub-pkg-standalone-posh)

-   [<span data-ttu-id="20c17-110">取消发布现有程序包</span><span class="sxs-lookup"><span data-stu-id="20c17-110">To unpublish an existing package</span></span>](#bkmk-unpub-pkg-standalone-posh)

-   [<span data-ttu-id="20c17-111">取消发布特定用户的程序包</span><span class="sxs-lookup"><span data-stu-id="20c17-111">To unpublish a package for a specific user</span></span>](#bkmk-unpub-pkg-specfc-use)

-   [<span data-ttu-id="20c17-112">删除现有程序包</span><span class="sxs-lookup"><span data-stu-id="20c17-112">To remove an existing package</span></span>](#bkmk-remove-pkg-standalone-posh)

-   [<span data-ttu-id="20c17-113">仅允许管理员发布或取消发布程序包</span><span class="sxs-lookup"><span data-stu-id="20c17-113">To enable only administrators to publish or unpublish packages</span></span>](#bkmk-admins-pub-pkgs)

-   [<span data-ttu-id="20c17-114">了解挂起程序包（UserPending 和 GlobalPending）</span><span class="sxs-lookup"><span data-stu-id="20c17-114">Understanding pending packages (UserPending and GlobalPending)</span></span>](#bkmk-understd-pend-pkgs)

## <a href="" id="bkmk-return-pkgs-standalone-posh"></a><span data-ttu-id="20c17-115">返回程序包列表</span><span class="sxs-lookup"><span data-stu-id="20c17-115">To return a list of packages</span></span>


<span data-ttu-id="20c17-116">使用以下信息返回有权使用特定用户的程序包的列表：</span><span class="sxs-lookup"><span data-stu-id="20c17-116">Use the following information to return a list of packages that are entitled to a specific user:</span></span>

<span data-ttu-id="20c17-117">**Cmdlet**： AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="20c17-117">**Cmdlet**: Get-AppvClientPackage</span></span>

<span data-ttu-id="20c17-118">**参数**：-Name-Version-PackageID-VersionID</span><span class="sxs-lookup"><span data-stu-id="20c17-118">**Parameters**: -Name -Version -PackageID -VersionID</span></span>

<span data-ttu-id="20c17-119">**示例**： AppvClientPackage-Name "ContosoApplication"-版本2</span><span class="sxs-lookup"><span data-stu-id="20c17-119">**Example**: Get-AppvClientPackage –Name “ContosoApplication” -Version 2</span></span>

## <a href="" id="bkmk-add-pkgs-standalone-posh"></a><span data-ttu-id="20c17-120">添加程序包</span><span class="sxs-lookup"><span data-stu-id="20c17-120">To add a package</span></span>


<span data-ttu-id="20c17-121">使用以下信息将程序包添加到计算机。</span><span class="sxs-lookup"><span data-stu-id="20c17-121">Use the following information to add a package to a computer.</span></span>

<span data-ttu-id="20c17-122">**重要提示** 此示例仅添加程序包。</span><span class="sxs-lookup"><span data-stu-id="20c17-122">**Important** This example only adds a package.</span></span> <span data-ttu-id="20c17-123">它不会将程序包发布给用户或计算机。</span><span class="sxs-lookup"><span data-stu-id="20c17-123">It does not publish the package to the user or the computer.</span></span>

 

<span data-ttu-id="20c17-124">**Cmdlet**： Add-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="20c17-124">**Cmdlet**: Add-AppvClientPackage</span></span>

<span data-ttu-id="20c17-125">**示例**： $Contoso = Add-AppvClientPackage \\\\path\\to\\appv\\package.appv</span><span class="sxs-lookup"><span data-stu-id="20c17-125">**Example**: $Contoso = Add-AppvClientPackage \\\\path\\to\\appv\\package.appv</span></span>

## <a href="" id="bkmk-pub-pkg-standalone-posh"></a><span data-ttu-id="20c17-126">发布程序包</span><span class="sxs-lookup"><span data-stu-id="20c17-126">To publish a package</span></span>


<span data-ttu-id="20c17-127">使用以下信息将已添加到特定用户或全局的程序包发布到计算机上的任何用户。</span><span class="sxs-lookup"><span data-stu-id="20c17-127">Use the following information to publish a package that has been added to a specific user or globally to any user on the computer.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="20c17-128">发布方法</span><span class="sxs-lookup"><span data-stu-id="20c17-128">Publishing method</span></span></th>
<th align="left"><span data-ttu-id="20c17-129">Cmdlet 和示例</span><span class="sxs-lookup"><span data-stu-id="20c17-129">Cmdlet and example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="20c17-130">发布到用户</span><span class="sxs-lookup"><span data-stu-id="20c17-130">Publishing to the user</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="20c17-131">Cmdlet </strong> ： Publish-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="20c17-131">Cmdlet</strong>: Publish-AppvClientPackage</span></span></p>
<p><strong><span data-ttu-id="20c17-132">示例 </strong> ： Publish-AppvClientPackage "ContosoApplication"</span><span class="sxs-lookup"><span data-stu-id="20c17-132">Example</strong>: Publish-AppvClientPackage “ContosoApplication”</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="20c17-133">全球发布</span><span class="sxs-lookup"><span data-stu-id="20c17-133">Publishing globally</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="20c17-134">Cmdlet </strong> ： Publish-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="20c17-134">Cmdlet</strong>: Publish-AppvClientPackage</span></span></p>
<p><strong><span data-ttu-id="20c17-135">示例 </strong> ： Publish-AppvClientPackage "ContosoApplication"-Global</span><span class="sxs-lookup"><span data-stu-id="20c17-135">Example</strong>: Publish-AppvClientPackage “ContosoApplication” -Global</span></span></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-pub-pkg-a-user-standalone-posh"></a><span data-ttu-id="20c17-136">将程序包发布到特定用户</span><span class="sxs-lookup"><span data-stu-id="20c17-136">To publish a package to a specific user</span></span>


<span data-ttu-id="20c17-137">**注意** 必须使用 App-v 5.0 SP2 修补程序包5或更高版本才能使用此参数。</span><span class="sxs-lookup"><span data-stu-id="20c17-137">**Note** You must use App-V 5.0 SP2 Hotfix Package 5 or later to use this parameter.</span></span>

 

<span data-ttu-id="20c17-138">管理员可以通过使用**AppvClientPackage** cmdlet 指定可选 **– UserSID**参数来将程序包发布到特定用户，其中 **-UserSID**表示最终用户的安全标识符（SID）。</span><span class="sxs-lookup"><span data-stu-id="20c17-138">An administrator can publish a package to a specific user by specifying the optional **–UserSID** parameter with the **Publish-AppvClientPackage** cmdlet, where **-UserSID** represents the end user’s security identifier (SID).</span></span>

<span data-ttu-id="20c17-139">要使用此参数，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="20c17-139">To use this parameter:</span></span>

-   <span data-ttu-id="20c17-140">你可以从用户或管理员会话运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="20c17-140">You can run this cmdlet from the user or administrator session.</span></span>

-   <span data-ttu-id="20c17-141">必须使用管理凭据登录才能使用该参数。</span><span class="sxs-lookup"><span data-stu-id="20c17-141">You must be logged in with administrative credentials to use the parameter.</span></span>

-   <span data-ttu-id="20c17-142">最终用户必须登录。</span><span class="sxs-lookup"><span data-stu-id="20c17-142">The end user must be logged in.</span></span>

-   <span data-ttu-id="20c17-143">您必须提供最终用户的安全标识符（SID）。</span><span class="sxs-lookup"><span data-stu-id="20c17-143">You must provide the end user’s security identifier (SID).</span></span>

<span data-ttu-id="20c17-144">**Cmdlet**： Publish-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="20c17-144">**Cmdlet**: Publish-AppvClientPackage</span></span>

<span data-ttu-id="20c17-145">**示例**： Publish-AppvClientPackage "ContosoApplication"-UserSID S-1-2-34-56789012-3456789012-345678901-2345</span><span class="sxs-lookup"><span data-stu-id="20c17-145">**Example**: Publish-AppvClientPackage “ContosoApplication” -UserSID S-1-2-34-56789012-3456789012-345678901-2345</span></span>

## <a href="" id="bkmk-add-pub-pkg-standalone-posh"></a><span data-ttu-id="20c17-146">添加和发布程序包</span><span class="sxs-lookup"><span data-stu-id="20c17-146">To add and publish a package</span></span>


<span data-ttu-id="20c17-147">使用以下信息将程序包添加到计算机并将其发布给用户。</span><span class="sxs-lookup"><span data-stu-id="20c17-147">Use the following information to add a package to a computer and publish it to the user.</span></span>

<span data-ttu-id="20c17-148">**Cmdlet**： Add-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="20c17-148">**Cmdlet**: Add-AppvClientPackage</span></span>

<span data-ttu-id="20c17-149">**示例**： Add-AppvClientPackage \\\\path\\to\\appv\\package.appv |发布-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="20c17-149">**Example**: Add-AppvClientPackage \\\\path\\to\\appv\\package.appv | Publish-AppvClientPackage</span></span>

## <a href="" id="bkmk-unpub-pkg-standalone-posh"></a><span data-ttu-id="20c17-150">取消发布现有程序包</span><span class="sxs-lookup"><span data-stu-id="20c17-150">To unpublish an existing package</span></span>


<span data-ttu-id="20c17-151">使用以下信息取消发布已获得用户资格但不从计算机中删除程序包的程序包。</span><span class="sxs-lookup"><span data-stu-id="20c17-151">Use the following information to unpublish a package which has been entitled to a user but not remove the package from the computer.</span></span>

<span data-ttu-id="20c17-152">**Cmdlet**：取消发布-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="20c17-152">**Cmdlet**: Unpublish-AppvClientPackage</span></span>

<span data-ttu-id="20c17-153">**示例**：取消发布-AppvClientPackage "ContosoApplication"</span><span class="sxs-lookup"><span data-stu-id="20c17-153">**Example**: Unpublish-AppvClientPackage “ContosoApplication”</span></span>

## <a href="" id="bkmk-unpub-pkg-specfc-use"></a><span data-ttu-id="20c17-154">取消发布特定用户的程序包</span><span class="sxs-lookup"><span data-stu-id="20c17-154">To unpublish a package for a specific user</span></span>


<span data-ttu-id="20c17-155">**注意** 必须使用 App-v 5.0 SP2 修补程序包5或更高版本才能使用此参数。</span><span class="sxs-lookup"><span data-stu-id="20c17-155">**Note** You must use App-V 5.0 SP2 Hotfix Package 5 or later to use this parameter.</span></span>

 

<span data-ttu-id="20c17-156">管理员可以通过将 optional- **UserSID**参数与**AppvClientPackage** cmdlet 一起使用可选的- **UserSID**表示最终用户的安全标识符（SID）来取消发布特定用户的程序包。</span><span class="sxs-lookup"><span data-stu-id="20c17-156">An administrator can unpublish a package for a specific user by using the optional **–UserSID** parameter with the **Unpublish-AppvClientPackage** cmdlet, where **-UserSID** represents the end user’s security identifier (SID).</span></span>

<span data-ttu-id="20c17-157">要使用此参数，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="20c17-157">To use this parameter:</span></span>

-   <span data-ttu-id="20c17-158">你可以从用户或管理员会话运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="20c17-158">You can run this cmdlet from the user or administrator session.</span></span>

-   <span data-ttu-id="20c17-159">必须使用管理凭据登录才能使用该参数。</span><span class="sxs-lookup"><span data-stu-id="20c17-159">You must be logged in with administrative credentials to use the parameter.</span></span>

-   <span data-ttu-id="20c17-160">最终用户必须登录。</span><span class="sxs-lookup"><span data-stu-id="20c17-160">The end user must be logged in.</span></span>

-   <span data-ttu-id="20c17-161">您必须提供最终用户的安全标识符（SID）。</span><span class="sxs-lookup"><span data-stu-id="20c17-161">You must provide the end user’s security identifier (SID).</span></span>

<span data-ttu-id="20c17-162">**Cmdlet**：取消发布-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="20c17-162">**Cmdlet**: Unpublish-AppvClientPackage</span></span>

<span data-ttu-id="20c17-163">**示例**：取消发布-AppvClientPackage "ContosoApplication"-UserSID S-1-2-34-56789012-3456789012-345678901-2345</span><span class="sxs-lookup"><span data-stu-id="20c17-163">**Example**: Unpublish-AppvClientPackage “ContosoApplication” -UserSID S-1-2-34-56789012-3456789012-345678901-2345</span></span>

## <a href="" id="bkmk-remove-pkg-standalone-posh"></a><span data-ttu-id="20c17-164">删除现有程序包</span><span class="sxs-lookup"><span data-stu-id="20c17-164">To remove an existing package</span></span>


<span data-ttu-id="20c17-165">使用以下信息从计算机中删除程序包。</span><span class="sxs-lookup"><span data-stu-id="20c17-165">Use the following information to remove a package from the computer.</span></span>

<span data-ttu-id="20c17-166">**Cmdlet**： Remove-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="20c17-166">**Cmdlet**: Remove-AppvClientPackage</span></span>

<span data-ttu-id="20c17-167">**示例**： Remove-AppvClientPackage "ContosoApplication"</span><span class="sxs-lookup"><span data-stu-id="20c17-167">**Example**: Remove-AppvClientPackage “ContosoApplication”</span></span>

<span data-ttu-id="20c17-168">**注意** 对于前面示例的变量，已将 app-v cmdlet 分配给变量，仅供你明确使用;不要求赋值。</span><span class="sxs-lookup"><span data-stu-id="20c17-168">**Note** App-V cmdlets have been assigned to variables for the previous examples for clarity only; assignment is not a requirement.</span></span> <span data-ttu-id="20c17-169">大多数 cmdlet 可以合并为中显示的，[以添加和发布程序包](#bkmk-add-pub-pkg-standalone-posh)。</span><span class="sxs-lookup"><span data-stu-id="20c17-169">Most cmdlets can be combined as displayed in [To add and publish a package](#bkmk-add-pub-pkg-standalone-posh).</span></span> <span data-ttu-id="20c17-170">有关详细教程，请参阅[App-V 5.0 客户端 PowerShell 深入](https://go.microsoft.com/fwlink/?LinkId=324466)了解。</span><span class="sxs-lookup"><span data-stu-id="20c17-170">For a detailed tutorial, see [App-V 5.0 Client PowerShell Deep Dive](https://go.microsoft.com/fwlink/?LinkId=324466).</span></span>

 

## <a href="" id="bkmk-admins-pub-pkgs"></a><span data-ttu-id="20c17-171">仅允许管理员发布或取消发布程序包</span><span class="sxs-lookup"><span data-stu-id="20c17-171">To enable only administrators to publish or unpublish packages</span></span>


<span data-ttu-id="20c17-172">**注意** 
**从 app-v 5.0 SP3 开始，支持此功能。**</span><span class="sxs-lookup"><span data-stu-id="20c17-172">**Note**
**This feature is supported starting in App-V 5.0 SP3.**</span></span>

 

<span data-ttu-id="20c17-173">使用以下 cmdlet 和参数以仅允许管理员（而非最终用户）发布或取消发布程序包：</span><span class="sxs-lookup"><span data-stu-id="20c17-173">Use the following cmdlet and parameter to enable only administrators (not end users) to publish or unpublish packages:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="20c17-174">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="20c17-174">Cmdlet</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="20c17-175">Set-AppvClientConfiguration</span><span class="sxs-lookup"><span data-stu-id="20c17-175">Set-AppvClientConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="20c17-176">参数</span><span class="sxs-lookup"><span data-stu-id="20c17-176">Parameter</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="20c17-177">-RequirePublishAsAdmin</span><span class="sxs-lookup"><span data-stu-id="20c17-177">-RequirePublishAsAdmin</span></span></p>
<p><span data-ttu-id="20c17-178">参数值：</span><span class="sxs-lookup"><span data-stu-id="20c17-178">Parameter values:</span></span></p>
<ul>
<li><p><span data-ttu-id="20c17-179">0-假</span><span class="sxs-lookup"><span data-stu-id="20c17-179">0 - False</span></span></p></li>
<li><p><span data-ttu-id="20c17-180">1-True</span><span class="sxs-lookup"><span data-stu-id="20c17-180">1 - True</span></span></p></li>
</ul>
<p><strong><span data-ttu-id="20c17-181">示例： </strong> ： Set-AppvClientConfiguration-RequirePublishAsAdmin1</span><span class="sxs-lookup"><span data-stu-id="20c17-181">Example:</strong>: Set-AppvClientConfiguration –RequirePublishAsAdmin1</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="20c17-182">若要使用 App-v 管理控制台设置此配置，请参阅[如何使用管理控制台发布程序包](how-to-publish-a-package-by-using-the-management-console-51.md)。</span><span class="sxs-lookup"><span data-stu-id="20c17-182">To use the App-V Management console to set this configuration, see [How to Publish a Package by Using the Management Console](how-to-publish-a-package-by-using-the-management-console-51.md).</span></span>

## <a href="" id="bkmk-understd-pend-pkgs"></a><span data-ttu-id="20c17-183">了解挂起程序包（UserPending 和 GlobalPending）</span><span class="sxs-lookup"><span data-stu-id="20c17-183">Understanding pending packages (UserPending and GlobalPending)</span></span>


<span data-ttu-id="20c17-184">**从 app-v 5.0 SP2 开始**：如果你运行的 PowerShell cmdlet 影响当前正在使用的程序包，你尝试执行的任务将置于挂起状态。</span><span class="sxs-lookup"><span data-stu-id="20c17-184">**Starting in App-V 5.0 SP2**: If you run a PowerShell cmdlet that affects a package that is currently in use, the task that you are trying to perform is placed in a pending state.</span></span> <span data-ttu-id="20c17-185">例如，如果你尝试在使用该程序包中的应用程序时发布程序包，然后运行**AppvClientPackage**，则会在 cmdlet 输出中显示挂起状态，如下所示：</span><span class="sxs-lookup"><span data-stu-id="20c17-185">For example, if you try to publish a package when an application in that package is being used, and then run **Get-AppvClientPackage**, the pending status appears in the cmdlet output as follows:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="20c17-186">Cmdlet 输出项目</span><span class="sxs-lookup"><span data-stu-id="20c17-186">Cmdlet output item</span></span></th>
<th align="left"><span data-ttu-id="20c17-187">描述</span><span class="sxs-lookup"><span data-stu-id="20c17-187">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="20c17-188">UserPending</span><span class="sxs-lookup"><span data-stu-id="20c17-188">UserPending</span></span></p></td>
<td align="left"><p><span data-ttu-id="20c17-189">指示列出的程序包是否有正在应用于用户的挂起任务：</span><span class="sxs-lookup"><span data-stu-id="20c17-189">Indicates whether the listed package has a pending task that is being applied to the user:</span></span></p>
<ul>
<li><p><span data-ttu-id="20c17-190">True</span><span class="sxs-lookup"><span data-stu-id="20c17-190">True</span></span></p></li>
<li><p><span data-ttu-id="20c17-191">False</span><span class="sxs-lookup"><span data-stu-id="20c17-191">False</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="20c17-192">GlobalPending</span><span class="sxs-lookup"><span data-stu-id="20c17-192">GlobalPending</span></span></p></td>
<td align="left"><p><span data-ttu-id="20c17-193">指示列出的程序包是否具有正在全局应用于计算机的挂起任务：</span><span class="sxs-lookup"><span data-stu-id="20c17-193">Indicates whether the listed package has a pending task that is being applied globally to the computer:</span></span></p>
<ul>
<li><p><span data-ttu-id="20c17-194">True</span><span class="sxs-lookup"><span data-stu-id="20c17-194">True</span></span></p></li>
<li><p><span data-ttu-id="20c17-195">False</span><span class="sxs-lookup"><span data-stu-id="20c17-195">False</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="20c17-196">根据以下规则，待决任务将在以后运行：</span><span class="sxs-lookup"><span data-stu-id="20c17-196">The pending task will run later, according to the following rules:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="20c17-197">任务类型</span><span class="sxs-lookup"><span data-stu-id="20c17-197">Task type</span></span></th>
<th align="left"><span data-ttu-id="20c17-198">适用规则</span><span class="sxs-lookup"><span data-stu-id="20c17-198">Applicable rule</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="20c17-199">基于用户的任务，例如将程序包发布给用户</span><span class="sxs-lookup"><span data-stu-id="20c17-199">User-based task, e.g., publishing a package to a user</span></span></p></td>
<td align="left"><p><span data-ttu-id="20c17-200">将在用户注销后执行挂起的任务，然后重新登录。</span><span class="sxs-lookup"><span data-stu-id="20c17-200">The pending task will be performed after the user logs off and then logs back on.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="20c17-201">基于全球的任务，例如，全局启用连接组</span><span class="sxs-lookup"><span data-stu-id="20c17-201">Globally based task, e.g., enabling a connection group globally</span></span></p></td>
<td align="left"><p><span data-ttu-id="20c17-202">当计算机关闭然后重新启动时，将执行挂起的任务。</span><span class="sxs-lookup"><span data-stu-id="20c17-202">The pending task will be performed when the computer is shut down and then restarted.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="20c17-203">有关挂起任务的详细信息，请参阅[关于 App-V 5.0 SP2](about-app-v-50-sp2.md#bkmk-pkg-upgr-pendg-tasks)。</span><span class="sxs-lookup"><span data-stu-id="20c17-203">For more information about pending tasks, see [About App-V 5.0 SP2](about-app-v-50-sp2.md#bkmk-pkg-upgr-pendg-tasks).</span></span>

<span data-ttu-id="20c17-204">已**获得有关 app-v 的建议**？</span><span class="sxs-lookup"><span data-stu-id="20c17-204">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="20c17-205">在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="20c17-205">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="20c17-206">遇到了 app-v 问题？</span><span class="sxs-lookup"><span data-stu-id="20c17-206">Got an App-V issue?</span></span>** <span data-ttu-id="20c17-207">使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="20c17-207">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="20c17-208">相关主题</span><span class="sxs-lookup"><span data-stu-id="20c17-208">Related topics</span></span>


[<span data-ttu-id="20c17-209">App-V 5.1 的操作</span><span class="sxs-lookup"><span data-stu-id="20c17-209">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

[<span data-ttu-id="20c17-210">使用 PowerShell 管理 App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="20c17-210">Administering App-V 5.1 by Using PowerShell</span></span>](administering-app-v-51-by-using-powershell.md)

 

 





