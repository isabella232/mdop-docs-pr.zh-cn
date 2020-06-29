---
title: 如何加载 PowerShell Cmdlet 和获取 Cmdlet 帮助
description: 如何加载 PowerShell Cmdlet 和获取 Cmdlet 帮助
author: dansimp
ms.assetid: 0624495b-943e-485b-9e54-b50e4ee6591c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/02/2016
ms.openlocfilehash: 7692d3e36aabc4f3142f664e94d9d71b2cfc1bd3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798425"
---
# <span data-ttu-id="d422c-103">如何加载 PowerShell Cmdlet 和获取 Cmdlet 帮助</span><span class="sxs-lookup"><span data-stu-id="d422c-103">How to Load the PowerShell Cmdlets and Get Cmdlet Help</span></span>


<span data-ttu-id="d422c-104">本主题包含的内容：</span><span class="sxs-lookup"><span data-stu-id="d422c-104">What this topic covers:</span></span>

-   [<span data-ttu-id="d422c-105">使用 PowerShell cmdlet 的要求</span><span class="sxs-lookup"><span data-stu-id="d422c-105">Requirements for using PowerShell cmdlets</span></span>](#bkmk-reqs-using-posh)

-   [<span data-ttu-id="d422c-106">加载 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="d422c-106">Loading the PowerShell cmdlets</span></span>](#bkmk-load-cmdlets)

-   [<span data-ttu-id="d422c-107">获取有关 PowerShell cmdlet 的帮助</span><span class="sxs-lookup"><span data-stu-id="d422c-107">Getting help for the PowerShell cmdlets</span></span>](#bkmk-get-cmdlet-help)

-   [<span data-ttu-id="d422c-108">显示 PowerShell cmdlet 的帮助</span><span class="sxs-lookup"><span data-stu-id="d422c-108">Displaying the help for a PowerShell cmdlet</span></span>](#bkmk-display-help-cmdlet)

## <a href="" id="bkmk-reqs-using-posh"></a><span data-ttu-id="d422c-109">使用 PowerShell cmdlet 的要求</span><span class="sxs-lookup"><span data-stu-id="d422c-109">Requirements for using PowerShell cmdlets</span></span>


<span data-ttu-id="d422c-110">查看有关使用 app-v PowerShell cmdlet 的以下要求：</span><span class="sxs-lookup"><span data-stu-id="d422c-110">Review the following requirements for using the App-V PowerShell cmdlets:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d422c-111">要求</span><span class="sxs-lookup"><span data-stu-id="d422c-111">Requirement</span></span></th>
<th align="left"><span data-ttu-id="d422c-112">详细信息</span><span class="sxs-lookup"><span data-stu-id="d422c-112">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d422c-113">仅当用户通过使用以下方法之一授予访问权限时，用户才可以运行 app-v 服务器 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="d422c-113">Users can run App-V Server cmdlets only if you grant them access by using one of the following methods:</span></span></p></td>
<td align="left"><ul>
<li><p><strong><span data-ttu-id="d422c-114">部署和配置 App-v 服务器时 </strong> ：</span><span class="sxs-lookup"><span data-stu-id="d422c-114">When you are deploying and configuring the App-V Server</strong>:</span></span></p>
<p><span data-ttu-id="d422c-115">指定具有管理 App-v 环境的权限的 Active Directory 组或单个用户。</span><span class="sxs-lookup"><span data-stu-id="d422c-115">Specify an Active Directory group or individual user that has permissions to manage the App-V environment.</span></span> <span data-ttu-id="d422c-116">请参阅 <a href="how-to-deploy-the-app-v-50-server-50sp3.md" data-raw-source="[How to Deploy the App-V 5.0 Server](how-to-deploy-the-app-v-50-server-50sp3.md)"> 如何部署 app-v 5.0 服务器 </a> 。</span><span class="sxs-lookup"><span data-stu-id="d422c-116">See <a href="how-to-deploy-the-app-v-50-server-50sp3.md" data-raw-source="[How to Deploy the App-V 5.0 Server](how-to-deploy-the-app-v-50-server-50sp3.md)">How to Deploy the App-V 5.0 Server</a>.</span></span></p></li>
<li><p><strong><span data-ttu-id="d422c-117">在部署 app-v 服务器之后 </strong> ：</span><span class="sxs-lookup"><span data-stu-id="d422c-117">After you’ve deployed the App-V Server</strong>:</span></span></p>
<p><span data-ttu-id="d422c-118">使用 app-v 管理控制台添加其他 Active Directory 组或用户。</span><span class="sxs-lookup"><span data-stu-id="d422c-118">Use the App-V Management console to add an additional Active Directory group or user.</span></span> <span data-ttu-id="d422c-119">请参阅 <a href="how-to-add-or-remove-an-administrator-by-using-the-management-console.md" data-raw-source="[How to Add or Remove an Administrator by Using the Management Console](how-to-add-or-remove-an-administrator-by-using-the-management-console.md)"> 如何使用管理控制台添加或删除管理员 </a> 。</span><span class="sxs-lookup"><span data-stu-id="d422c-119">See <a href="how-to-add-or-remove-an-administrator-by-using-the-management-console.md" data-raw-source="[How to Add or Remove an Administrator by Using the Management Console](how-to-add-or-remove-an-administrator-by-using-the-management-console.md)">How to Add or Remove an Administrator by Using the Management Console</a>.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d422c-120">需要提升的命令提示符的 cmdlet</span><span class="sxs-lookup"><span data-stu-id="d422c-120">Cmdlets that require an elevated command prompt</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="d422c-121">Add-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="d422c-121">Add-AppvClientPackage</span></span></p></li>
<li><p><span data-ttu-id="d422c-122">Remove-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="d422c-122">Remove-AppvClientPackage</span></span></p></li>
<li><p><span data-ttu-id="d422c-123">Set-AppvClientConfiguration</span><span class="sxs-lookup"><span data-stu-id="d422c-123">Set-AppvClientConfiguration</span></span></p></li>
<li><p><span data-ttu-id="d422c-124">Add-AppvClientConnectionGroup</span><span class="sxs-lookup"><span data-stu-id="d422c-124">Add-AppvClientConnectionGroup</span></span></p></li>
<li><p><span data-ttu-id="d422c-125">Remove-AppvClientConnectionGroup</span><span class="sxs-lookup"><span data-stu-id="d422c-125">Remove-AppvClientConnectionGroup</span></span></p></li>
<li><p><span data-ttu-id="d422c-126">Add-AppvPublishingServer</span><span class="sxs-lookup"><span data-stu-id="d422c-126">Add-AppvPublishingServer</span></span></p></li>
<li><p><span data-ttu-id="d422c-127">Remove-AppvPublishingServer</span><span class="sxs-lookup"><span data-stu-id="d422c-127">Remove-AppvPublishingServer</span></span></p></li>
<li><p><span data-ttu-id="d422c-128">Send-AppvClientReport</span><span class="sxs-lookup"><span data-stu-id="d422c-128">Send-AppvClientReport</span></span></p></li>
<li><p><span data-ttu-id="d422c-129">Set-AppvClientMode</span><span class="sxs-lookup"><span data-stu-id="d422c-129">Set-AppvClientMode</span></span></p></li>
<li><p><span data-ttu-id="d422c-130">Set-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="d422c-130">Set-AppvClientPackage</span></span></p></li>
<li><p><span data-ttu-id="d422c-131">Set-AppvPublishingServer</span><span class="sxs-lookup"><span data-stu-id="d422c-131">Set-AppvPublishingServer</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d422c-132">最终用户可以运行的 cmdlet，除非将其配置为需要提升的命令提示符</span><span class="sxs-lookup"><span data-stu-id="d422c-132">Cmdlets that end users can run, unless you configure them to require an elevated command prompt</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="d422c-133">发布-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="d422c-133">Publish-AppvClientPackage</span></span></p></li>
<li><p><span data-ttu-id="d422c-134">取消发布-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="d422c-134">Unpublish-AppvClientPackage</span></span></p></li>
</ul>
<p><span data-ttu-id="d422c-135">若要将这些 cmdlet 配置为需要提升的命令提示符，请使用以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="d422c-135">To configure these cmdlets to require an elevated command prompt, use one of the following methods:</span></span></p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d422c-136">方法</span><span class="sxs-lookup"><span data-stu-id="d422c-136">Method</span></span></th>
<th align="left"><span data-ttu-id="d422c-137">更多资源</span><span class="sxs-lookup"><span data-stu-id="d422c-137">More resources</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d422c-138"><strong> </strong> 通过 <strong> -RequirePublishAsAdmin 参数运行 AppvClientConfiguration cmdlet </strong> 。</span><span class="sxs-lookup"><span data-stu-id="d422c-138">Run the <strong>Set-AppvClientConfiguration</strong> cmdlet with the <strong>-RequirePublishAsAdmin</strong> parameter.</span></span></p></td>
<td align="left"><ul>
<li><p><a href="how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admin-only-posh-topic-cg" data-raw-source="[How to Manage Connection Groups on a Stand-alone Computer by Using PowerShell](how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admin-only-posh-topic-cg)"><span data-ttu-id="d422c-139">如何使用 PowerShell 管理独立计算机上的连接组</span><span class="sxs-lookup"><span data-stu-id="d422c-139">How to Manage Connection Groups on a Stand-alone Computer by Using PowerShell</span></span></a></p></li>
<li><p><a href="how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md" data-raw-source="[How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md)"><span data-ttu-id="d422c-140">如何使用 PowerShell 管理在独立计算机上运行的 App-V 5.0 程序包</span><span class="sxs-lookup"><span data-stu-id="d422c-140">How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell</span></span></a></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d422c-141">对 App-v 客户端启用 "要求发布为管理员" 组策略设置。</span><span class="sxs-lookup"><span data-stu-id="d422c-141">Enable the “Require publish as administrator” Group Policy setting for App-V Clients.</span></span></p></td>
<td align="left"><p><a href="how-to-publish-a-package-by-using-the-management-console-50.md" data-raw-source="[How to Publish a Package by Using the Management Console](how-to-publish-a-package-by-using-the-management-console-50.md)"><span data-ttu-id="d422c-142">如何使用管理控制台发布程序包</span><span class="sxs-lookup"><span data-stu-id="d422c-142">How to Publish a Package by Using the Management Console</span></span></a> </p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-load-cmdlets"></a><span data-ttu-id="d422c-143">加载 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="d422c-143">Loading the PowerShell cmdlets</span></span>
<span data-ttu-id="d422c-144">要加载 PowerShell cmdlet 模块，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d422c-144">To load the PowerShell cmdlet modules:</span></span>

1.  <span data-ttu-id="d422c-145">打开 Windows PowerShell 或 Windows PowerShell 集成脚本环境（ISE）。</span><span class="sxs-lookup"><span data-stu-id="d422c-145">Open Windows PowerShell or Windows PowerShell Integrated Scripting Environment (ISE).</span></span>

2.  <span data-ttu-id="d422c-146">键入以下命令之一，为所需的模块加载 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="d422c-146">Type one of the following commands to load the cmdlets for the module you want:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d422c-147">App-v 组件</span><span class="sxs-lookup"><span data-stu-id="d422c-147">App-V component</span></span></th>
<th align="left"><span data-ttu-id="d422c-148">要键入的命令</span><span class="sxs-lookup"><span data-stu-id="d422c-148">Command to type</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d422c-149">App-v 服务器</span><span class="sxs-lookup"><span data-stu-id="d422c-149">App-V Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="d422c-150">导入-模块 AppvServer</span><span class="sxs-lookup"><span data-stu-id="d422c-150">Import-Module AppvServer</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d422c-151">App-v 排序器</span><span class="sxs-lookup"><span data-stu-id="d422c-151">App-V Sequencer</span></span></p></td>
<td align="left"><p><span data-ttu-id="d422c-152">导入-模块 AppvSequencer</span><span class="sxs-lookup"><span data-stu-id="d422c-152">Import-Module AppvSequencer</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d422c-153">App-v 客户端</span><span class="sxs-lookup"><span data-stu-id="d422c-153">App-V Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="d422c-154">导入-模块 AppvClient</span><span class="sxs-lookup"><span data-stu-id="d422c-154">Import-Module AppvClient</span></span></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-get-cmdlet-help"></a><span data-ttu-id="d422c-155">获取有关 PowerShell cmdlet 的帮助</span><span class="sxs-lookup"><span data-stu-id="d422c-155">Getting help for the PowerShell cmdlets</span></span>
<span data-ttu-id="d422c-156">从 app-v 5.0 SP3 开始，cmdlet 帮助有两种格式：</span><span class="sxs-lookup"><span data-stu-id="d422c-156">Starting in App-V 5.0 SP3, cmdlet help is available in two formats:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d422c-157">格式</span><span class="sxs-lookup"><span data-stu-id="d422c-157">Format</span></span></th>
<th align="left"><span data-ttu-id="d422c-158">描述</span><span class="sxs-lookup"><span data-stu-id="d422c-158">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d422c-159">作为可下载的模块</span><span class="sxs-lookup"><span data-stu-id="d422c-159">As a downloadable module</span></span></p></td>
<td align="left"><p><span data-ttu-id="d422c-160">下载 cmdlet 模块后下载最新帮助：</span><span class="sxs-lookup"><span data-stu-id="d422c-160">To download the latest help after downloading the cmdlet module:</span></span></p>
<ol>
<li><p><span data-ttu-id="d422c-161">打开 Windows PowerShell 或 Windows PowerShell 集成脚本环境（ISE）。</span><span class="sxs-lookup"><span data-stu-id="d422c-161">Open Windows PowerShell or Windows PowerShell Integrated Scripting Environment (ISE).</span></span></p></li>
<li><p><span data-ttu-id="d422c-162">键入以下命令之一，为所需的模块加载 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="d422c-162">Type one of the following commands to load the cmdlets for the module you want:</span></span></p></li>
</ol>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d422c-163">App-v 组件</span><span class="sxs-lookup"><span data-stu-id="d422c-163">App-V component</span></span></th>
<th align="left"><span data-ttu-id="d422c-164">要键入的命令</span><span class="sxs-lookup"><span data-stu-id="d422c-164">Command to type</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d422c-165">App-v 服务器</span><span class="sxs-lookup"><span data-stu-id="d422c-165">App-V Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="d422c-166">Update-Help-Module AppvServer</span><span class="sxs-lookup"><span data-stu-id="d422c-166">Update-Help -Module AppvServer</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d422c-167">App-v 排序器</span><span class="sxs-lookup"><span data-stu-id="d422c-167">App-V Sequencer</span></span></p></td>
<td align="left"><p><span data-ttu-id="d422c-168">Update-Help-Module AppvSequencer</span><span class="sxs-lookup"><span data-stu-id="d422c-168">Update-Help -Module AppvSequencer</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d422c-169">App-v 客户端</span><span class="sxs-lookup"><span data-stu-id="d422c-169">App-V Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="d422c-170">Update-Help-Module AppvClient</span><span class="sxs-lookup"><span data-stu-id="d422c-170">Update-Help -Module AppvClient</span></span></p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d422c-171">在 TechNet 上作为网页</span><span class="sxs-lookup"><span data-stu-id="d422c-171">On TechNet as web pages</span></span></p></td>
<td align="left"><p><span data-ttu-id="d422c-172">在 <a href="https://technet.microsoft.com/library/dn520245.aspx" data-raw-source="[Microsoft Desktop Optimization Pack Automation with Windows PowerShell](https://technet.microsoft.com/library/dn520245.aspx)"> Windows PowerShell 的 Microsoft 桌面优化包自动化下，查看 app-v 节点 </a> 。</span><span class="sxs-lookup"><span data-stu-id="d422c-172">See the App-V node under <a href="https://technet.microsoft.com/library/dn520245.aspx" data-raw-source="[Microsoft Desktop Optimization Pack Automation with Windows PowerShell](https://technet.microsoft.com/library/dn520245.aspx)">Microsoft Desktop Optimization Pack Automation with Windows PowerShell</a>.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-display-help-cmdlet"></a><span data-ttu-id="d422c-173">显示 PowerShell cmdlet 的帮助</span><span class="sxs-lookup"><span data-stu-id="d422c-173">Displaying the help for a PowerShell cmdlet</span></span>
<span data-ttu-id="d422c-174">若要显示特定 PowerShell cmdlet 的帮助，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d422c-174">To display help for a specific PowerShell cmdlet:</span></span>

1.  <span data-ttu-id="d422c-175">打开 Windows PowerShell 或 Windows PowerShell 集成脚本环境（ISE）。</span><span class="sxs-lookup"><span data-stu-id="d422c-175">Open Windows PowerShell or Windows PowerShell Integrated Scripting Environment (ISE).</span></span>

2.  <span data-ttu-id="d422c-176">输入**get-help** &lt; *cmdlet* &gt; ，例如， **get-help AppvClientPackage**。</span><span class="sxs-lookup"><span data-stu-id="d422c-176">Type **Get-Help** &lt;*cmdlet*&gt;, for example, **Get-Help Publish-AppvClientPackage**.</span></span>

<span data-ttu-id="d422c-177">已**获得有关 app-v 的建议**？</span><span class="sxs-lookup"><span data-stu-id="d422c-177">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="d422c-178">在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="d422c-178">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> <span data-ttu-id="d422c-179">遇到**了 app-v 问题**？</span><span class="sxs-lookup"><span data-stu-id="d422c-179">**Got an App-V issue**?</span></span> <span data-ttu-id="d422c-180">使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="d422c-180">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

 

 





