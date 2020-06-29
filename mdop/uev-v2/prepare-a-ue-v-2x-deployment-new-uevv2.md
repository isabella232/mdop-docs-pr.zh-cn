---
title: 准备 UE-V 2. x 部署
description: 准备 UE-V 2. x 部署
author: dansimp
ms.assetid: c429fd06-13ff-48c5-b9c9-fa1ec01ab800
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 04/19/2017
ms.openlocfilehash: e6b2de407990536e1a08532632dcea19ea0d0ee9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803965"
---
# <span data-ttu-id="26310-103">准备 UE-V 2. x 部署</span><span class="sxs-lookup"><span data-stu-id="26310-103">Prepare a UE-V 2.x Deployment</span></span>


<span data-ttu-id="26310-104">在将 Microsoft 用户体验虚拟化（UE-V）2.0 或2.1 部署到企业中用户访问的设备之间进行设置的解决方案之前，需要执行一些计划和准备。</span><span class="sxs-lookup"><span data-stu-id="26310-104">There is some planning and preparation to do before you deploy Microsoft User Experience Virtualization (UE-V) 2.0 or 2.1 as a solution for synchronizing settings between devices that users access in your enterprise.</span></span> <span data-ttu-id="26310-105">本主题将帮助你确定要执行的部署类型以及你可以提前执行的准备，以便你的部署成功。</span><span class="sxs-lookup"><span data-stu-id="26310-105">This topic helps you determine what type of deployment you'll be doing and what preparation you can make beforehand so that your deployment is successful.</span></span>

<span data-ttu-id="26310-106">首先，让我们看一下部署 UE-V 需要执行的任务：</span><span class="sxs-lookup"><span data-stu-id="26310-106">First, let’s look at the tasks you’ll do to deploy UE-V:</span></span>

-   <span data-ttu-id="26310-107">规划 UE-V 部署</span><span class="sxs-lookup"><span data-stu-id="26310-107">Plan your UE-V Deployment</span></span>

    <span data-ttu-id="26310-108">在部署任何内容之前，最好的第一步是执行一些计划，以便你可以确定要部署的 UE-V 功能。</span><span class="sxs-lookup"><span data-stu-id="26310-108">Before you deploy anything, a good first step is to do a little bit of planning so that you can determine which UE-V features you’ll deploy.</span></span> <span data-ttu-id="26310-109">因此，如果您离开此页面，请确保您返回并阅读下面的规划信息。</span><span class="sxs-lookup"><span data-stu-id="26310-109">So if you leave this page, make sure you come back and read through the planning information below.</span></span>

-   [<span data-ttu-id="26310-110">为 UE-V 2.x 部署所需功能</span><span class="sxs-lookup"><span data-stu-id="26310-110">Deploy Required Features for UE-V 2.x</span></span>](deploy-required-features-for-ue-v-2x-new-uevv2.md)

    <span data-ttu-id="26310-111">每个 UE-V 部署都需要这些活动：</span><span class="sxs-lookup"><span data-stu-id="26310-111">Every UE-V deployment requires these activities:</span></span>

    -   [<span data-ttu-id="26310-112">定义设置存储位置</span><span class="sxs-lookup"><span data-stu-id="26310-112">Define a settings storage location</span></span>](https://technet.microsoft.com/library/dn458891.aspx#ssl)

    -   [<span data-ttu-id="26310-113">确定如何部署 UE-V Agent 和管理 UE-V 配置</span><span class="sxs-lookup"><span data-stu-id="26310-113">Decide how to deploy the UE-V Agent and manage UE-V configurations</span></span>](https://technet.microsoft.com/library/dn458891.aspx#config)

    -   <span data-ttu-id="26310-114">在需要同步设置的每台用户计算机上[安装 Ue-v Agent](https://technet.microsoft.com/library/dn458891.aspx#agent)</span><span class="sxs-lookup"><span data-stu-id="26310-114">[Install the UE-V Agent](https://technet.microsoft.com/library/dn458891.aspx#agent) on every user computer that needs settings synchronized</span></span>

-   <span data-ttu-id="26310-115">或者，你可以[为自定义应用程序部署 ue-v 2。](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)</span><span class="sxs-lookup"><span data-stu-id="26310-115">Optionally, you can [Deploy UE-V 2.x for Custom Applications](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)</span></span>

    <span data-ttu-id="26310-116">规划将帮助你确定是否希望 UE-V 支持自定义应用程序（第三方或业务线）的设置同步，这需要这些 UE-V 功能：</span><span class="sxs-lookup"><span data-stu-id="26310-116">Planning will help you figure out whether you want UE-V to support the synchronization of settings for custom applications (third-party or line-of-business), which requires these UE-V features:</span></span>

    -   <span data-ttu-id="26310-117">[安装 UEV 生成器](https://technet.microsoft.com/library/dn458942.aspx#uevgen)，以便可以创建、编辑和验证同步自定义应用程序设置所需的自定义设置位置模板</span><span class="sxs-lookup"><span data-stu-id="26310-117">[Install the UEV Generator](https://technet.microsoft.com/library/dn458942.aspx#uevgen) so you can create, edit, and validate the custom settings location templates required to synchronize custom application settings</span></span>

    -   <span data-ttu-id="26310-118">使用 UE-V 生成器[创建自定义设置位置模板](https://technet.microsoft.com/library/dn458942.aspx#createcustomtemplates)</span><span class="sxs-lookup"><span data-stu-id="26310-118">[Create custom settings location templates](https://technet.microsoft.com/library/dn458942.aspx#createcustomtemplates) by using the UE-V Generator</span></span>

    -   <span data-ttu-id="26310-119">部署用于存储自定义设置位置模板的[ue-v 设置模板目录](https://technet.microsoft.com/library/dn458942.aspx#deploycatalogue)</span><span class="sxs-lookup"><span data-stu-id="26310-119">[Deploy a UE-V settings template catalog](https://technet.microsoft.com/library/dn458942.aspx#deploycatalogue) that you use to store your custom settings location templates</span></span>

<span data-ttu-id="26310-120">此工作流图提供对 UE-V 部署的高级理解，以及决定如何在企业中部署 UE-V 的决策。</span><span class="sxs-lookup"><span data-stu-id="26310-120">This workflow diagram provides a high-level understanding of a UE-V deployment and the decisions that determine how you deploy UE-V in your enterprise.</span></span>

![deploymentworkflow](images/deploymentworkflow.png)

<span data-ttu-id="26310-122">**规划 ue-v 部署：** 首先，你需要执行一些计划，以便你可以确定要部署的 UE-V 组件。</span><span class="sxs-lookup"><span data-stu-id="26310-122">**Planning a UE-V deployment:** First, you want to do a little bit of planning so that you can determine which UE-V components you’ll be deploying.</span></span> <span data-ttu-id="26310-123">规划 UE-V 部署涉及以下事项：</span><span class="sxs-lookup"><span data-stu-id="26310-123">Planning a UE-V deployment involves these things:</span></span>

-   [<span data-ttu-id="26310-124">确定是否同步自定义应用程序的设置</span><span class="sxs-lookup"><span data-stu-id="26310-124">Decide whether to synchronize settings for custom applications</span></span>](#deciding)

    <span data-ttu-id="26310-125">这确定你是否将在部署期间安装 UE-V 生成器，这使你可以创建自定义设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="26310-125">This determines whether you will install the UE-V Generator during deployment, which lets you create custom settings location templates.</span></span> <span data-ttu-id="26310-126">它涉及以下内容：</span><span class="sxs-lookup"><span data-stu-id="26310-126">It involves the following:</span></span>

    <span data-ttu-id="26310-127">查看[在 ue-v 部署中自动同步的设置](#autosyncsettings)。</span><span class="sxs-lookup"><span data-stu-id="26310-127">Review the [settings that are synchronized automatically in a UE-V deployment](#autosyncsettings).</span></span>

    <span data-ttu-id="26310-128">[确定是否需要为其他应用程序同步设置](#determinesettingssync)。</span><span class="sxs-lookup"><span data-stu-id="26310-128">[Determine whether you need settings synchronized for other applications](#determinesettingssync).</span></span>

-   <span data-ttu-id="26310-129">查看部署 UE-V （如高可用性和容量规划）[的其他注意事项](#considerations)。</span><span class="sxs-lookup"><span data-stu-id="26310-129">Review [other considerations for deploying UE-V](#considerations), such as high availability and capacity planning.</span></span>

-   [<span data-ttu-id="26310-130">确认系统必备和支持的 UE-V 配置</span><span class="sxs-lookup"><span data-stu-id="26310-130">Confirm prerequisites and supported configurations for UE-V</span></span>](#prereqs)

## <a href="" id="deciding"></a><span data-ttu-id="26310-131">确定是否同步自定义应用程序的设置</span><span class="sxs-lookup"><span data-stu-id="26310-131">Decide Whether to Synchronize Settings for Custom Applications</span></span>


<span data-ttu-id="26310-132">在 UE-V 部署中，许多设置将自动同步。</span><span class="sxs-lookup"><span data-stu-id="26310-132">In a UE-V deployment, many settings are automatically synchronized.</span></span> <span data-ttu-id="26310-133">但是，你也可以自定义 UE-V 以同步其他应用程序的设置，如业务线和第三方应用。</span><span class="sxs-lookup"><span data-stu-id="26310-133">But you can also customize UE-V to synchronize settings for other applications, such as line-of-business and third-party apps.</span></span>

<span data-ttu-id="26310-134">确定是否希望 UE-V 同步自定义应用程序的设置可能是规划 UE-V 部署的最重要部分。</span><span class="sxs-lookup"><span data-stu-id="26310-134">Deciding if you want UE-V to synchronize settings for custom applications is probably the most important part of planning your UE-V deployment.</span></span> <span data-ttu-id="26310-135">本部分中的主题将帮助您做出该决策。</span><span class="sxs-lookup"><span data-stu-id="26310-135">The topics in this section will help you make that decision.</span></span>

### <a href="" id="autosyncsettings"></a><span data-ttu-id="26310-136">在 UE-V 部署中自动同步的设置</span><span class="sxs-lookup"><span data-stu-id="26310-136">Settings that are automatically synchronized in a UE-V deployment</span></span>

<span data-ttu-id="26310-137">本节提供有关默认情况下在 UE-V 中同步的设置的信息，包括：</span><span class="sxs-lookup"><span data-stu-id="26310-137">This section provides information about the settings that are synchronized by default in UE-V, including the following:</span></span>

<span data-ttu-id="26310-138">默认情况下同步其设置的桌面应用程序</span><span class="sxs-lookup"><span data-stu-id="26310-138">Desktop applications whose settings are synchronized by default</span></span>

<span data-ttu-id="26310-139">默认同步的 Windows 桌面设置</span><span class="sxs-lookup"><span data-stu-id="26310-139">Windows desktop settings that are synchronized by default</span></span>

<span data-ttu-id="26310-140">Windows 应用设置同步的支持语句</span><span class="sxs-lookup"><span data-stu-id="26310-140">A statement of support for Windows app setting synchronization</span></span>

<span data-ttu-id="26310-141">请参阅[Microsoft Office 的用户体验虚拟化（ue-v）设置模板](https://www.microsoft.com/download/details.aspx?id=46367)，下载由 ue-v 同步的特定 Microsoft office 2013、microsoft office 2010 和 microsoft office 2007 设置的完整列表。</span><span class="sxs-lookup"><span data-stu-id="26310-141">See [User Experience Virtualization (UE-V) settings templates for Microsoft Office](https://www.microsoft.com/download/details.aspx?id=46367) to download a complete list of the specific Microsoft Office 2013, Microsoft Office 2010, and Microsoft Office 2007 settings that are synchronized by UE-V.</span></span>

### <span data-ttu-id="26310-142">UE-V 2.1 和 UE-V 2.1 SP1 中默认同步的桌面应用程序</span><span class="sxs-lookup"><span data-stu-id="26310-142">Desktop applications synchronized by default in UE-V 2.1 and UE-V 2.1 SP1</span></span>

<span data-ttu-id="26310-143">当安装 UE-V 2.1 或 2.1 SP1 代理时，它将注册一个默认设置位置模板组，用于捕获这些常见 Microsoft 应用程序的设置值。</span><span class="sxs-lookup"><span data-stu-id="26310-143">When you install the UE-V 2.1 or 2.1 SP1 Agent, it registers a default group of settings location templates that capture settings values for these common Microsoft applications.</span></span>

**<span data-ttu-id="26310-144">提示</span><span class="sxs-lookup"><span data-stu-id="26310-144">Tip</span></span>**  
<span data-ttu-id="26310-145">**Microsoft office 2007 设置同步**-在 ue-v 2.1 和 2.1 SP1 中，默认情况下不再为 Office 2007 应用程序包括设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="26310-145">**Microsoft Office 2007 Settings Synchronization** – In UE-V 2.1 and 2.1 SP1, a settings location template is no longer included by default for Office 2007 applications.</span></span> <span data-ttu-id="26310-146">但是，你仍然可以使用 UE-V 2.0 或更早版本的 Office 2007 模板，并可以从[ue-v 模板库](https://go.microsoft.com/fwlink/p/?LinkID=246589)中获取模板。</span><span class="sxs-lookup"><span data-stu-id="26310-146">However, you can still use Office 2007 templates from UE-V 2.0 or earlier and can get the templates from the [UE-V template gallery](https://go.microsoft.com/fwlink/p/?LinkID=246589).</span></span>



<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="26310-147">应用程序类别</span><span class="sxs-lookup"><span data-stu-id="26310-147">Application category</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="26310-148">描述</span><span class="sxs-lookup"><span data-stu-id="26310-148">Description</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="26310-149">Microsoft Office 2010 应用程序</span><span class="sxs-lookup"><span data-stu-id="26310-149">Microsoft Office 2010 applications</span></span></p>
<p><span data-ttu-id="26310-150">（ <a href="https://www.microsoft.com/download/details.aspx?id=46367" data-raw-source="[Download a list of all settings synced](https://www.microsoft.com/download/details.aspx?id=46367)"> 下载已同步的所有设置的列表 </a> ）</span><span class="sxs-lookup"><span data-stu-id="26310-150">(<a href="https://www.microsoft.com/download/details.aspx?id=46367" data-raw-source="[Download a list of all settings synced](https://www.microsoft.com/download/details.aspx?id=46367)">Download a list of all settings synced</a>)</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-151">Microsoft Word 2010</span><span class="sxs-lookup"><span data-stu-id="26310-151">Microsoft Word 2010</span></span></p>
<p><span data-ttu-id="26310-152">Microsoft Excel 2010</span><span class="sxs-lookup"><span data-stu-id="26310-152">Microsoft Excel 2010</span></span></p>
<p><span data-ttu-id="26310-153">Microsoft Outlook 2010</span><span class="sxs-lookup"><span data-stu-id="26310-153">Microsoft Outlook 2010</span></span></p>
<p><span data-ttu-id="26310-154">Microsoft Access 2010</span><span class="sxs-lookup"><span data-stu-id="26310-154">Microsoft Access 2010</span></span></p>
<p><span data-ttu-id="26310-155">Microsoft Project 2010</span><span class="sxs-lookup"><span data-stu-id="26310-155">Microsoft Project 2010</span></span></p>
<p><span data-ttu-id="26310-156">Microsoft PowerPoint 2010</span><span class="sxs-lookup"><span data-stu-id="26310-156">Microsoft PowerPoint 2010</span></span></p>
<p><span data-ttu-id="26310-157">Microsoft Publisher 2010</span><span class="sxs-lookup"><span data-stu-id="26310-157">Microsoft Publisher 2010</span></span></p>
<p><span data-ttu-id="26310-158">Microsoft Visio 2010</span><span class="sxs-lookup"><span data-stu-id="26310-158">Microsoft Visio 2010</span></span></p>
<p><span data-ttu-id="26310-159">Microsoft SharePoint Workspace 2010</span><span class="sxs-lookup"><span data-stu-id="26310-159">Microsoft SharePoint Workspace 2010</span></span></p>
<p><span data-ttu-id="26310-160">Microsoft InfoPath 2010</span><span class="sxs-lookup"><span data-stu-id="26310-160">Microsoft InfoPath 2010</span></span></p>
<p><span data-ttu-id="26310-161">Microsoft Lync 2010</span><span class="sxs-lookup"><span data-stu-id="26310-161">Microsoft Lync 2010</span></span></p>
<p><span data-ttu-id="26310-162">Microsoft OneNote 2010</span><span class="sxs-lookup"><span data-stu-id="26310-162">Microsoft OneNote 2010</span></span></p>
<p><span data-ttu-id="26310-163">Microsoft SharePoint Designer 2010</span><span class="sxs-lookup"><span data-stu-id="26310-163">Microsoft SharePoint Designer 2010</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="26310-164">Microsoft Office 2013 应用程序</span><span class="sxs-lookup"><span data-stu-id="26310-164">Microsoft Office 2013 applications</span></span></p>
<p><span data-ttu-id="26310-165">（ <a href="https://www.microsoft.com/download/details.aspx?id=46367" data-raw-source="[Download a list of all settings synced](https://www.microsoft.com/download/details.aspx?id=46367)"> 下载已同步的所有设置的列表 </a> ）</span><span class="sxs-lookup"><span data-stu-id="26310-165">(<a href="https://www.microsoft.com/download/details.aspx?id=46367" data-raw-source="[Download a list of all settings synced](https://www.microsoft.com/download/details.aspx?id=46367)">Download a list of all settings synced</a>)</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-166">Microsoft Word 2013</span><span class="sxs-lookup"><span data-stu-id="26310-166">Microsoft Word 2013</span></span></p>
<p><span data-ttu-id="26310-167">Microsoft Excel 2013</span><span class="sxs-lookup"><span data-stu-id="26310-167">Microsoft Excel 2013</span></span></p>
<p><span data-ttu-id="26310-168">Microsoft Outlook 2013</span><span class="sxs-lookup"><span data-stu-id="26310-168">Microsoft Outlook 2013</span></span></p>
<p><span data-ttu-id="26310-169">Microsoft Access 2013</span><span class="sxs-lookup"><span data-stu-id="26310-169">Microsoft Access 2013</span></span></p>
<p><span data-ttu-id="26310-170">Microsoft Project 2013</span><span class="sxs-lookup"><span data-stu-id="26310-170">Microsoft Project 2013</span></span></p>
<p><span data-ttu-id="26310-171">Microsoft PowerPoint 2013</span><span class="sxs-lookup"><span data-stu-id="26310-171">Microsoft PowerPoint 2013</span></span></p>
<p><span data-ttu-id="26310-172">Microsoft Publisher 2013</span><span class="sxs-lookup"><span data-stu-id="26310-172">Microsoft Publisher 2013</span></span></p>
<p><span data-ttu-id="26310-173">Microsoft Visio 2013</span><span class="sxs-lookup"><span data-stu-id="26310-173">Microsoft Visio 2013</span></span></p>
<p><span data-ttu-id="26310-174">Microsoft InfoPath 2013</span><span class="sxs-lookup"><span data-stu-id="26310-174">Microsoft InfoPath 2013</span></span></p>
<p><span data-ttu-id="26310-175">Microsoft Lync 2013</span><span class="sxs-lookup"><span data-stu-id="26310-175">Microsoft Lync 2013</span></span></p>
<p><span data-ttu-id="26310-176">Microsoft OneNote 2013</span><span class="sxs-lookup"><span data-stu-id="26310-176">Microsoft OneNote 2013</span></span></p>
<p><span data-ttu-id="26310-177">Microsoft SharePoint Designer 2013</span><span class="sxs-lookup"><span data-stu-id="26310-177">Microsoft SharePoint Designer 2013</span></span></p>
<p><span data-ttu-id="26310-178">Microsoft Office 2013 上传中心</span><span class="sxs-lookup"><span data-stu-id="26310-178">Microsoft Office 2013 Upload Center</span></span></p>
<p><span data-ttu-id="26310-179">Microsoft OneDrive for Business 2013</span><span class="sxs-lookup"><span data-stu-id="26310-179">Microsoft OneDrive for Business 2013</span></span></p>
<p><span data-ttu-id="26310-180">UE-V 2.1 和 2.1 SP1 Microsoft Office 2013 设置位置模板包括改进的 Outlook 签名支持。</span><span class="sxs-lookup"><span data-stu-id="26310-180">The UE-V 2.1 and 2.1 SP1 Microsoft Office 2013 settings location templates include improved Outlook signature support.</span></span> <span data-ttu-id="26310-181">我们已为新的、答复和转发的电子邮件添加了默认签名设置的同步。</span><span class="sxs-lookup"><span data-stu-id="26310-181">We’ve added synchronization of default signature settings for new, reply, and forwarded emails.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="26310-182">注意</span><span class="sxs-lookup"><span data-stu-id="26310-182">Note</span></span></strong><br/><p><span data-ttu-id="26310-183">必须为用户要同步其 Outlook 签名的任何设备创建 Outlook 配置文件。</span><span class="sxs-lookup"><span data-stu-id="26310-183">An Outlook profile must be created for any device on which a user wants to sync their Outlook signature.</span></span> <span data-ttu-id="26310-184">如果尚未创建配置文件，则用户可以创建一个配置文件，然后在该设备上重新启动 Outlook 以启用签名同步。</span><span class="sxs-lookup"><span data-stu-id="26310-184">If the profile is not already created, the user can create one and then restart Outlook on that device to enable signature synchronization.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="26310-185">浏览器选项： Internet Explorer 8、Internet Explorer 9、Internet Explorer 10 和 Internet Explorer 11</span><span class="sxs-lookup"><span data-stu-id="26310-185">Browser options: Internet Explorer 8, Internet Explorer 9, Internet Explorer 10, and Internet Explorer 11</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-186">"收藏夹"、"主页"、"选项卡" 和 "工具栏"。</span><span class="sxs-lookup"><span data-stu-id="26310-186">Favorites, home page, tabs, and toolbars.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="26310-187">注意</span><span class="sxs-lookup"><span data-stu-id="26310-187">Note</span></span></strong><br/><p><span data-ttu-id="26310-188">UE-V 不会漫游 Internet Explorer cookie 的设置。</span><span class="sxs-lookup"><span data-stu-id="26310-188">UE-V does not roam settings for Internet Explorer cookies.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="26310-189">Windows 附件</span><span class="sxs-lookup"><span data-stu-id="26310-189">Windows accessories</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-190">Microsoft 计算器、记事本和写字板。</span><span class="sxs-lookup"><span data-stu-id="26310-190">Microsoft Calculator, Notepad, WordPad.</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="26310-191">注意</span><span class="sxs-lookup"><span data-stu-id="26310-191">Note</span></span>**  
<span data-ttu-id="26310-192">UE-V 2.1 SP1 不会在 Windows 10 中的 Microsoft 计算器和以前操作系统中的 Microsoft 计算器之间同步设置。</span><span class="sxs-lookup"><span data-stu-id="26310-192">UE-V 2.1 SP1 does not synchronize settings between the Microsoft Calculator in Windows 10 and the Microsoft Calculator in previous operating systems.</span></span>



### <span data-ttu-id="26310-193">UE-V 2.0 中默认同步的桌面应用程序</span><span class="sxs-lookup"><span data-stu-id="26310-193">Desktop applications synchronized by default in UE-V 2.0</span></span>

<span data-ttu-id="26310-194">安装 UE-V 2.0 代理时，它将注册一个默认的设置位置模板组，用于捕获这些常见 Microsoft 应用程序的设置值。</span><span class="sxs-lookup"><span data-stu-id="26310-194">When you install the UE-V 2.0 Agent, it registers a default group of settings location templates that capture settings values for these common Microsoft applications.</span></span>

**<span data-ttu-id="26310-195">提示</span><span class="sxs-lookup"><span data-stu-id="26310-195">Tip</span></span>**  
<span data-ttu-id="26310-196">**Microsoft office 2013 设置同步**-在 Ue-v 2.0 中，默认情况下不包括 Office 2013 应用程序的设置位置模板，但可从[ue-v 模板库](https://go.microsoft.com/fwlink/p/?LinkID=246589)中下载。</span><span class="sxs-lookup"><span data-stu-id="26310-196">**Microsoft Office 2013 Settings Synchronization** – In UE-V 2.0, a settings location template is not included by default for Office 2013 applications, but is available for download from the [UE-V template gallery](https://go.microsoft.com/fwlink/p/?LinkID=246589).</span></span> <span data-ttu-id="26310-197">将[office 2013 与 ue-v 2.0 同步](synchronizing-office-2013-with-ue-v-20-both-uevv2.md)提供有关支持的模板的详细信息，这些模板可同步 Office 2013 设置。</span><span class="sxs-lookup"><span data-stu-id="26310-197">[Synchronizing Office 2013 with UE-V 2.0](synchronizing-office-2013-with-ue-v-20-both-uevv2.md) provides details about the supported templates that synchronize Office 2013 settings.</span></span>



<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="26310-198">应用程序类别</span><span class="sxs-lookup"><span data-stu-id="26310-198">Application category</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="26310-199">描述</span><span class="sxs-lookup"><span data-stu-id="26310-199">Description</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="26310-200">Microsoft Office 2007 应用程序</span><span class="sxs-lookup"><span data-stu-id="26310-200">Microsoft Office 2007 applications</span></span></p>
<p><span data-ttu-id="26310-201">（ <a href="https://www.microsoft.com/download/details.aspx?id=46367" data-raw-source="[Download a list of all settings synced](https://www.microsoft.com/download/details.aspx?id=46367)"> 下载已同步的所有设置的列表 </a> ）</span><span class="sxs-lookup"><span data-stu-id="26310-201">(<a href="https://www.microsoft.com/download/details.aspx?id=46367" data-raw-source="[Download a list of all settings synced](https://www.microsoft.com/download/details.aspx?id=46367)">Download a list of all settings synced</a>)</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-202">Microsoft Access 2007</span><span class="sxs-lookup"><span data-stu-id="26310-202">Microsoft Access 2007</span></span></p>
<p><span data-ttu-id="26310-203">Microsoft Communicator 2007</span><span class="sxs-lookup"><span data-stu-id="26310-203">Microsoft Communicator 2007</span></span></p>
<p><span data-ttu-id="26310-204">Microsoft Excel 2007</span><span class="sxs-lookup"><span data-stu-id="26310-204">Microsoft Excel 2007</span></span></p>
<p><span data-ttu-id="26310-205">Microsoft InfoPath 2007</span><span class="sxs-lookup"><span data-stu-id="26310-205">Microsoft InfoPath 2007</span></span></p>
<p><span data-ttu-id="26310-206">Microsoft OneNote 2007</span><span class="sxs-lookup"><span data-stu-id="26310-206">Microsoft OneNote 2007</span></span></p>
<p><span data-ttu-id="26310-207">Microsoft Outlook 2007</span><span class="sxs-lookup"><span data-stu-id="26310-207">Microsoft Outlook 2007</span></span></p>
<p><span data-ttu-id="26310-208">Microsoft PowerPoint 2007</span><span class="sxs-lookup"><span data-stu-id="26310-208">Microsoft PowerPoint 2007</span></span></p>
<p><span data-ttu-id="26310-209">Microsoft Project 2007</span><span class="sxs-lookup"><span data-stu-id="26310-209">Microsoft Project 2007</span></span></p>
<p><span data-ttu-id="26310-210">Microsoft Publisher 2007</span><span class="sxs-lookup"><span data-stu-id="26310-210">Microsoft Publisher 2007</span></span></p>
<p><span data-ttu-id="26310-211">Microsoft SharePoint Designer 2007</span><span class="sxs-lookup"><span data-stu-id="26310-211">Microsoft SharePoint Designer 2007</span></span></p>
<p><span data-ttu-id="26310-212">Microsoft Visio 2007</span><span class="sxs-lookup"><span data-stu-id="26310-212">Microsoft Visio 2007</span></span></p>
<p><span data-ttu-id="26310-213">Microsoft Word 2007</span><span class="sxs-lookup"><span data-stu-id="26310-213">Microsoft Word 2007</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="26310-214">Microsoft Office 2010 应用程序</span><span class="sxs-lookup"><span data-stu-id="26310-214">Microsoft Office 2010 applications</span></span></p>
<p><span data-ttu-id="26310-215">（ <a href="https://www.microsoft.com/download/details.aspx?id=46367" data-raw-source="[Download a list of all settings synced](https://www.microsoft.com/download/details.aspx?id=46367)"> 下载已同步的所有设置的列表 </a> ）</span><span class="sxs-lookup"><span data-stu-id="26310-215">(<a href="https://www.microsoft.com/download/details.aspx?id=46367" data-raw-source="[Download a list of all settings synced](https://www.microsoft.com/download/details.aspx?id=46367)">Download a list of all settings synced</a>)</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-216">Microsoft Word 2010</span><span class="sxs-lookup"><span data-stu-id="26310-216">Microsoft Word 2010</span></span></p>
<p><span data-ttu-id="26310-217">Microsoft Excel 2010</span><span class="sxs-lookup"><span data-stu-id="26310-217">Microsoft Excel 2010</span></span></p>
<p><span data-ttu-id="26310-218">Microsoft Outlook 2010</span><span class="sxs-lookup"><span data-stu-id="26310-218">Microsoft Outlook 2010</span></span></p>
<p><span data-ttu-id="26310-219">Microsoft Access 2010</span><span class="sxs-lookup"><span data-stu-id="26310-219">Microsoft Access 2010</span></span></p>
<p><span data-ttu-id="26310-220">Microsoft Project 2010</span><span class="sxs-lookup"><span data-stu-id="26310-220">Microsoft Project 2010</span></span></p>
<p><span data-ttu-id="26310-221">Microsoft PowerPoint 2010</span><span class="sxs-lookup"><span data-stu-id="26310-221">Microsoft PowerPoint 2010</span></span></p>
<p><span data-ttu-id="26310-222">Microsoft Publisher 2010</span><span class="sxs-lookup"><span data-stu-id="26310-222">Microsoft Publisher 2010</span></span></p>
<p><span data-ttu-id="26310-223">Microsoft Visio 2010</span><span class="sxs-lookup"><span data-stu-id="26310-223">Microsoft Visio 2010</span></span></p>
<p><span data-ttu-id="26310-224">Microsoft SharePoint Workspace 2010</span><span class="sxs-lookup"><span data-stu-id="26310-224">Microsoft SharePoint Workspace 2010</span></span></p>
<p><span data-ttu-id="26310-225">Microsoft InfoPath 2010</span><span class="sxs-lookup"><span data-stu-id="26310-225">Microsoft InfoPath 2010</span></span></p>
<p><span data-ttu-id="26310-226">Microsoft Lync 2010</span><span class="sxs-lookup"><span data-stu-id="26310-226">Microsoft Lync 2010</span></span></p>
<p><span data-ttu-id="26310-227">Microsoft OneNote 2010</span><span class="sxs-lookup"><span data-stu-id="26310-227">Microsoft OneNote 2010</span></span></p>
<p><span data-ttu-id="26310-228">Microsoft SharePoint Designer 2010</span><span class="sxs-lookup"><span data-stu-id="26310-228">Microsoft SharePoint Designer 2010</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="26310-229">浏览器选项： Internet Explorer 8、Internet Explorer 9 和 Internet Explorer 10</span><span class="sxs-lookup"><span data-stu-id="26310-229">Browser options: Internet Explorer 8, Internet Explorer 9, and Internet Explorer 10</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-230">"收藏夹"、"主页"、"选项卡" 和 "工具栏"。</span><span class="sxs-lookup"><span data-stu-id="26310-230">Favorites, home page, tabs, and toolbars.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="26310-231">注意</span><span class="sxs-lookup"><span data-stu-id="26310-231">Note</span></span></strong><br/><p><span data-ttu-id="26310-232">UE-V 不会漫游 Internet Explorer cookie 的设置。</span><span class="sxs-lookup"><span data-stu-id="26310-232">UE-V does not roam settings for Internet Explorer cookies.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="26310-233">Windows 附件</span><span class="sxs-lookup"><span data-stu-id="26310-233">Windows accessories</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-234">Microsoft 计算器、记事本和写字板。</span><span class="sxs-lookup"><span data-stu-id="26310-234">Microsoft Calculator, Notepad, WordPad.</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="autosyncsettings2"></a><span data-ttu-id="26310-235">默认同步的 Windows 设置</span><span class="sxs-lookup"><span data-stu-id="26310-235">Windows settings synchronized by default</span></span>

<span data-ttu-id="26310-236">UE-V 包括用于捕获这些 Windows 设置的设置值的设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="26310-236">UE-V includes settings location templates that capture settings values for these Windows settings.</span></span>

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="26310-237">Windows 设置</span><span class="sxs-lookup"><span data-stu-id="26310-237">Windows settings</span></span></th>
<th align="left"><span data-ttu-id="26310-238">描述</span><span class="sxs-lookup"><span data-stu-id="26310-238">Description</span></span></th>
<th align="left"><span data-ttu-id="26310-239">适用于</span><span class="sxs-lookup"><span data-stu-id="26310-239">Apply on</span></span></th>
<th align="left"><span data-ttu-id="26310-240">导出</span><span class="sxs-lookup"><span data-stu-id="26310-240">Export on</span></span></th>
<th align="left"><span data-ttu-id="26310-241">默认状态</span><span class="sxs-lookup"><span data-stu-id="26310-241">Default state</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="26310-242">桌面背景</span><span class="sxs-lookup"><span data-stu-id="26310-242">Desktop background</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-243">当前处于活动状态的桌面背景或墙纸。</span><span class="sxs-lookup"><span data-stu-id="26310-243">Currently active desktop background or wallpaper.</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-244">登录、解锁、远程连接、计划任务事件。</span><span class="sxs-lookup"><span data-stu-id="26310-244">Logon, unlock, remote connect, Scheduled Task events.</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-245">注销、锁定、远程断开连接、用户 <strong> </strong> 在 "公司设置中心" 中单击 "立即同步" 或 "计划任务间隔"</span><span class="sxs-lookup"><span data-stu-id="26310-245">Logoff, lock, remote disconnect, user clicking <strong>Sync Now</strong> in Company Settings Center, or scheduled task interval</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-246">启用</span><span class="sxs-lookup"><span data-stu-id="26310-246">Enabled</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="26310-247">轻松使用</span><span class="sxs-lookup"><span data-stu-id="26310-247">Ease of Access</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-248">辅助功能和输入设置、Microsoft 放大镜、讲述人和屏幕键盘。</span><span class="sxs-lookup"><span data-stu-id="26310-248">Accessibility and input settings, Microsoft Magnifier, Narrator, and on-Screen Keyboard.</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-249">仅登录。</span><span class="sxs-lookup"><span data-stu-id="26310-249">Logon only.</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-250">注销，用户 <strong> </strong> 在 "公司设置中心" 中单击 "立即同步" 或 "计划任务间隔"</span><span class="sxs-lookup"><span data-stu-id="26310-250">Logoff, user clicking <strong>Sync Now</strong> in Company Settings Center, or scheduled task interval</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-251">启用</span><span class="sxs-lookup"><span data-stu-id="26310-251">Enabled</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="26310-252">桌面设置</span><span class="sxs-lookup"><span data-stu-id="26310-252">Desktop settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-253">"开始" 菜单和任务栏设置、文件夹选项、默认桌面图标、附加时钟以及区域和语言设置。</span><span class="sxs-lookup"><span data-stu-id="26310-253">Start menu and Taskbar settings, Folder options, Default desktop icons, Additional clocks, and Region and Language settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-254">仅登录。</span><span class="sxs-lookup"><span data-stu-id="26310-254">Logon only.</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-255"><strong> </strong> 在公司设置中心或计划任务中注销、用户单击 "立即同步"</span><span class="sxs-lookup"><span data-stu-id="26310-255">Logoff, user clicking <strong>Sync Now</strong> in Company Settings Center, or scheduled task</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-256">启用</span><span class="sxs-lookup"><span data-stu-id="26310-256">Enabled</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="26310-257">注意</span><span class="sxs-lookup"><span data-stu-id="26310-257">Note</span></span>**  
<span data-ttu-id="26310-258">从 Windows 8 开始，UE-V 不会漫游与 "开始" 屏幕相关的设置，例如 "项目" 和 "位置"。</span><span class="sxs-lookup"><span data-stu-id="26310-258">Starting in Windows 8, UE-V does not roam settings related to the Start screen, such as items and locations.</span></span> <span data-ttu-id="26310-259">此外，UE-V 不支持同步已固定的任务栏项目或 Windows 文件快捷方式。</span><span class="sxs-lookup"><span data-stu-id="26310-259">In addition, UE-V does not support synchronization of pinned taskbar items or Windows file shortcuts.</span></span>



**<span data-ttu-id="26310-260">重要提示</span><span class="sxs-lookup"><span data-stu-id="26310-260">Important</span></span>**  
<span data-ttu-id="26310-261">UE-V 2.1 SP1 在 Windows 10 设备之间漫游任务栏设置。</span><span class="sxs-lookup"><span data-stu-id="26310-261">UE-V 2.1 SP1 roams taskbar settings between Windows 10 devices.</span></span> <span data-ttu-id="26310-262">但是，UE-V 不会在运行以前操作系统的 Windows 10 设备和设备之间同步任务栏设置。</span><span class="sxs-lookup"><span data-stu-id="26310-262">However, UE-V does not synchronize taskbar settings between Windows 10 devices and devices running previous operating systems.</span></span>



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="26310-263">设置组</span><span class="sxs-lookup"><span data-stu-id="26310-263">Settings group</span></span></th>
<th align="left"><span data-ttu-id="26310-264">类型</span><span class="sxs-lookup"><span data-stu-id="26310-264">Category</span></span></th>
<th align="left"><span data-ttu-id="26310-265">捕获</span><span class="sxs-lookup"><span data-stu-id="26310-265">Capture</span></span></th>
<th align="left"><span data-ttu-id="26310-266">“应用”</span><span class="sxs-lookup"><span data-stu-id="26310-266">Apply</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="26310-267">应用程序设置</span><span class="sxs-lookup"><span data-stu-id="26310-267">Application Settings</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="26310-268">Windows 应用</span><span class="sxs-lookup"><span data-stu-id="26310-268">Windows apps</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-269">关闭应用</span><span class="sxs-lookup"><span data-stu-id="26310-269">Close app</span></span></p>
<p><span data-ttu-id="26310-270">Windows 应用设置更改事件</span><span class="sxs-lookup"><span data-stu-id="26310-270">Windows app settings change event</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-271">启动时启动 UE-V 应用监视器</span><span class="sxs-lookup"><span data-stu-id="26310-271">Start the UE-V App Monitor at startup</span></span></p>
<p><span data-ttu-id="26310-272">打开应用</span><span class="sxs-lookup"><span data-stu-id="26310-272">Open app</span></span></p>
<p><span data-ttu-id="26310-273">Windows 应用设置更改事件</span><span class="sxs-lookup"><span data-stu-id="26310-273">Windows App Settings change event</span></span></p>
<p><span data-ttu-id="26310-274">设置包的到达</span><span class="sxs-lookup"><span data-stu-id="26310-274">Arrival of a settings package</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="26310-275">桌面应用程序</span><span class="sxs-lookup"><span data-stu-id="26310-275">Desktop applications</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-276">应用程序关闭</span><span class="sxs-lookup"><span data-stu-id="26310-276">Application closes</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-277">应用程序打开和关闭</span><span class="sxs-lookup"><span data-stu-id="26310-277">Application opens and closes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="26310-278">桌面设置</span><span class="sxs-lookup"><span data-stu-id="26310-278">Desktop settings</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="26310-279">桌面背景</span><span class="sxs-lookup"><span data-stu-id="26310-279">Desktop background</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-280">锁定或注销</span><span class="sxs-lookup"><span data-stu-id="26310-280">Lock or logoff</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-281">登录、解锁、远程连接、新软件包到达通知、用户单击 <strong> </strong> 公司设置中心的 "立即同步" 或 "计划任务运行"。</span><span class="sxs-lookup"><span data-stu-id="26310-281">Logon, unlock, remote connect, notification of new package arrival, user clicks <strong>Sync Now</strong> in Company Settings Center, or scheduled task runs.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="26310-282">轻松访问（通用-辅助功能、讲述人、放大镜、屏幕键盘）</span><span class="sxs-lookup"><span data-stu-id="26310-282">Ease of Access (Common – Accessibility, Narrator, Magnifier, On-Screen-Keyboard)</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-283">锁定或注销</span><span class="sxs-lookup"><span data-stu-id="26310-283">Lock or Logoff</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-284">Logon</span><span class="sxs-lookup"><span data-stu-id="26310-284">Logon</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="26310-285">轻松访问（Shell-音频、辅助功能、键盘和鼠标）</span><span class="sxs-lookup"><span data-stu-id="26310-285">Ease of Access (Shell - Audio, Accessibility, Keyboard, Mouse)</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-286">锁定或注销</span><span class="sxs-lookup"><span data-stu-id="26310-286">Lock or logoff</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-287">登录、解锁、远程连接、新程序包到达通知、用户 <strong> </strong> 在 "公司设置中心" 中单击 "同步" 或 "计划任务运行"</span><span class="sxs-lookup"><span data-stu-id="26310-287">Logon, unlock, remote connect, notification of new package arrival, user clicks <strong>Sync Now</strong> in Company Settings Center, or scheduled task runs</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="26310-288">桌面设置</span><span class="sxs-lookup"><span data-stu-id="26310-288">Desktop settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-289">锁定或注销</span><span class="sxs-lookup"><span data-stu-id="26310-289">Lock or logoff</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-290">Logon</span><span class="sxs-lookup"><span data-stu-id="26310-290">Logon</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="26310-291">UE-V-支持 Windows 应用</span><span class="sxs-lookup"><span data-stu-id="26310-291">UE-V-support for Windows Apps</span></span>

<span data-ttu-id="26310-292">对于 Windows 应用，应用开发人员将指定同步的设置。</span><span class="sxs-lookup"><span data-stu-id="26310-292">For Windows apps, the app developer specifies the settings that are synchronized.</span></span> <span data-ttu-id="26310-293">你可以指定启用哪些 Windows 应用进行设置同步。</span><span class="sxs-lookup"><span data-stu-id="26310-293">You can specify which Windows apps are enabled for settings synchronization.</span></span>

<span data-ttu-id="26310-294">若要在 Windows PowerShell 命令提示符下显示可将计算机上的设置与计算机的程序包系列名称、启用状态和已启用源同步的 Windows 应用的列表，请输入：</span><span class="sxs-lookup"><span data-stu-id="26310-294">To display a list of Windows apps that can synchronize settings on a computer with their package family name, enabled status, and enabled source, at a Windows PowerShell command prompt, enter:</span></span> `Get-UevAppxPackage`

**<span data-ttu-id="26310-295">注意</span><span class="sxs-lookup"><span data-stu-id="26310-295">Note</span></span>**  
<span data-ttu-id="26310-296">在 Windows 8 中，如果域用户将他们的登录凭据链接到其 Microsoft 帐户，UE-V 不会同步 Windows 应用设置。</span><span class="sxs-lookup"><span data-stu-id="26310-296">As of Windows 8, UE-V does not synchronize Windows app settings if the domain user links their sign-in credentials to their Microsoft Account.</span></span> <span data-ttu-id="26310-297">此链接会将设置同步到 Microsoft OneDrive，从而使 UE-V 可以禁用 Windows 应用设置同步。</span><span class="sxs-lookup"><span data-stu-id="26310-297">This linking synchronizes settings to Microsoft OneDrive so UE-V, which disables synchronization of Windows app settings.</span></span>



### <span data-ttu-id="26310-298">UE-V-支持漫游打印机</span><span class="sxs-lookup"><span data-stu-id="26310-298">UE-V-support for Roaming Printers</span></span>

<span data-ttu-id="26310-299">UE-V 2.1 SP1 允许网络打印机在设备之间漫游，以便用户登录到网络上的任何设备时可以访问其网络打印机。</span><span class="sxs-lookup"><span data-stu-id="26310-299">UE-V 2.1 SP1 lets network printers roam between devices so that a user has access to their network printers when logged on to any device on the network.</span></span> <span data-ttu-id="26310-300">这包括将其设置为默认打印机的漫游打印机。</span><span class="sxs-lookup"><span data-stu-id="26310-300">This includes roaming the printer that they set as the default.</span></span>

<span data-ttu-id="26310-301">UE-V 中的打印机漫游需要以下其中一种方案：</span><span class="sxs-lookup"><span data-stu-id="26310-301">Printer roaming in UE-V requires one of these scenarios:</span></span>

-   <span data-ttu-id="26310-302">打印服务器在漫游到新设备时可以下载所需的驱动程序。</span><span class="sxs-lookup"><span data-stu-id="26310-302">The print server can download the required driver when it roams to a new device.</span></span>

-   <span data-ttu-id="26310-303">漫游网络打印机的驱动程序已在需要访问该网络打印机的任何设备上预安装。</span><span class="sxs-lookup"><span data-stu-id="26310-303">The driver for the roaming network printer is pre-installed on any device that needs to access that network printer.</span></span>

-   <span data-ttu-id="26310-304">可以从 Windows Update 获取打印机驱动程序。</span><span class="sxs-lookup"><span data-stu-id="26310-304">The printer driver can be obtained from Windows Update.</span></span>

**<span data-ttu-id="26310-305">注意</span><span class="sxs-lookup"><span data-stu-id="26310-305">Note</span></span>**  
<span data-ttu-id="26310-306">UE-V 打印机漫游**功能不会漫游打印机**设置或首选项，例如双面打印。</span><span class="sxs-lookup"><span data-stu-id="26310-306">The UE-V printer roaming feature does **not** roam printer settings or preferences, such as printing double-sided.</span></span>



### <a href="" id="determinesettingssync"></a><span data-ttu-id="26310-307">确定是否需要同步其他应用程序的设置</span><span class="sxs-lookup"><span data-stu-id="26310-307">Determine whether you need settings synchronized for other applications</span></span>

<span data-ttu-id="26310-308">在你查看了在 UE-V 部署中自动同步的设置后，你希望确定是否将同步其他应用程序的设置，因为这决定了如何在整个企业中部署 UE-V。</span><span class="sxs-lookup"><span data-stu-id="26310-308">After you have reviewed the settings that are synchronized automatically in a UE-V deployment, you want to decide whether you will synchronize settings for other applications since this determines how you deploy UE-V throughout your enterprise.</span></span>

<span data-ttu-id="26310-309">作为管理员，当你考虑要包含在 UE-V 解决方案中的桌面应用程序时，请考虑哪些设置可以由用户自定义，以及应用程序存储其设置的方式和位置。</span><span class="sxs-lookup"><span data-stu-id="26310-309">As an administrator, when you consider which desktop applications to include in your UE-V solution, consider which settings can be customized by users, and how and where the application stores its settings.</span></span> <span data-ttu-id="26310-310">并非所有桌面应用程序都具有可自定义或经常由用户自定义的设置。</span><span class="sxs-lookup"><span data-stu-id="26310-310">Not all desktop applications have settings that can be customized or that are routinely customized by users.</span></span> <span data-ttu-id="26310-311">此外，并非所有桌面应用程序设置都可以在多台计算机或环境中安全地同步。</span><span class="sxs-lookup"><span data-stu-id="26310-311">In addition, not all desktop applications settings can safely be synchronized across multiple computers or environments.</span></span>

<span data-ttu-id="26310-312">通常，你可以同步满足以下条件的设置：</span><span class="sxs-lookup"><span data-stu-id="26310-312">In general, you can synchronize settings that meet the following criteria:</span></span>

-   <span data-ttu-id="26310-313">存储在用户易于访问的位置的设置。</span><span class="sxs-lookup"><span data-stu-id="26310-313">Settings that are stored in user-accessible locations.</span></span> <span data-ttu-id="26310-314">例如，不要同步 HKEY 中存储的设置或注册表的 \ _CURRENT \ _USER （HKCU）部分之外的设置。</span><span class="sxs-lookup"><span data-stu-id="26310-314">For example, do not synchronize settings that are stored in System32 or outside the HKEY\_CURRENT\_USER (HKCU) section of the registry.</span></span>

-   <span data-ttu-id="26310-315">不特定于特定计算机的设置。</span><span class="sxs-lookup"><span data-stu-id="26310-315">Settings that are not specific to the particular computer.</span></span> <span data-ttu-id="26310-316">例如，排除网络或硬件配置。</span><span class="sxs-lookup"><span data-stu-id="26310-316">For example, exclude network or hardware configurations.</span></span>

-   <span data-ttu-id="26310-317">可以在计算机之间同步的设置，而不会损坏数据。</span><span class="sxs-lookup"><span data-stu-id="26310-317">Settings that can be synchronized between computers without risk of corrupted data.</span></span> <span data-ttu-id="26310-318">例如，不要使用存储在数据库文件中的设置。</span><span class="sxs-lookup"><span data-stu-id="26310-318">For example, do not use settings that are stored in a database file.</span></span>

### <a href="" id="checklistsettingssync"></a><span data-ttu-id="26310-319">评估自定义应用程序的清单</span><span class="sxs-lookup"><span data-stu-id="26310-319">Checklist for evaluating custom applications</span></span>

<span data-ttu-id="26310-320">如果你确定需要同步其他应用程序的设置，你可以使用此清单来帮助确定你将包括哪些应用程序。</span><span class="sxs-lookup"><span data-stu-id="26310-320">If you’ve decided that you need settings synchronized for other applications, you can use this checklist to help figure out which applications you’ll include.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left"><span data-ttu-id="26310-321">描述</span><span class="sxs-lookup"><span data-stu-id="26310-321">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="26310-322">此应用程序是否包含用户可自定义的设置？</span><span class="sxs-lookup"><span data-stu-id="26310-322">Does this application contain settings that the user can customize?</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="26310-323">用户对这些设置的同步是否重要？</span><span class="sxs-lookup"><span data-stu-id="26310-323">Is it important for the user that these settings are synchronized?</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="26310-324">这些用户设置是否已由应用程序管理或设置策略解决方案管理？</span><span class="sxs-lookup"><span data-stu-id="26310-324">Are these user settings already managed by an application management or settings policy solution?</span></span> <span data-ttu-id="26310-325">UE-V 在登录、解锁或远程连接事件时，在应用程序启动和 Windows 设置中应用应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="26310-325">UE-V applies application settings at application startup and Windows settings at logon, unlock, or remote connect events.</span></span> <span data-ttu-id="26310-326">如果你将 UE-V 与其他设置共享解决方案配合使用，则用户可能会在同步设置中遇到不一致的情况。</span><span class="sxs-lookup"><span data-stu-id="26310-326">If you use UE-V with other settings sharing solutions, users might experience inconsistency across synchronized settings.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="26310-327">应用程序设置是否特定于计算机？</span><span class="sxs-lookup"><span data-stu-id="26310-327">Are the application settings specific to the computer?</span></span> <span data-ttu-id="26310-328">与硬件或特定计算机配置相关联的应用程序首选项和自定义不会在多个会话之间持续同步，并且可能导致应用程序体验较差。</span><span class="sxs-lookup"><span data-stu-id="26310-328">Application preferences and customizations that are associated with hardware or specific computer configurations do not consistently synchronize across sessions and can cause a poor application experience.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="26310-329">应用程序将设置存储在程序文件目录中还是位于 <strong> 用户 </strong> [用户名] &lt; 强 &gt; AppData </strong> &lt; 强 &gt; LocalLow </strong> 目录中的文件目录？</span><span class="sxs-lookup"><span data-stu-id="26310-329">Does the application store settings in the Program Files directory or in the file directory that is located in the <strong>Users</strong>[User name]&lt;strong&gt;AppData</strong>&lt;strong&gt;LocalLow</strong> directory?</span></span> <span data-ttu-id="26310-330">存储在其中任一位置的应用程序数据通常不应与用户同步，因为此数据特定于计算机，或者由于数据太大而无法同步。</span><span class="sxs-lookup"><span data-stu-id="26310-330">Application data that is stored in either of these locations usually should not synchronize with the user, because this data is specific to the computer or because the data is too large to synchronize.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="26310-331">应用程序是否在包含不应同步的其他应用程序数据的文件中存储任何设置？</span><span class="sxs-lookup"><span data-stu-id="26310-331">Does the application store any settings in a file that contains other application data that should not synchronize?</span></span> <span data-ttu-id="26310-332">UE-V 将文件作为单个单元进行同步。</span><span class="sxs-lookup"><span data-stu-id="26310-332">UE-V synchronizes files as a single unit.</span></span> <span data-ttu-id="26310-333">如果设置存储在包含应用程序数据而不是设置的文件中，则同步这些附加数据可能会导致应用程序体验较差。</span><span class="sxs-lookup"><span data-stu-id="26310-333">If settings are stored in files that include application data other than settings, then synchronizing this additional data can cause a poor application experience.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="26310-334">包含这些设置的文件有多大？</span><span class="sxs-lookup"><span data-stu-id="26310-334">How large are the files that contain the settings?</span></span> <span data-ttu-id="26310-335">设置同步的性能可能会受到大型文件的影响。</span><span class="sxs-lookup"><span data-stu-id="26310-335">The performance of the settings synchronization can be affected by large files.</span></span> <span data-ttu-id="26310-336">包括大型文件可能会影响设置同步的性能。</span><span class="sxs-lookup"><span data-stu-id="26310-336">Including large files can affect the performance of settings synchronization.</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="considerations"></a><span data-ttu-id="26310-337">准备 UE-V 部署时的其他注意事项</span><span class="sxs-lookup"><span data-stu-id="26310-337">Other Considerations when Preparing a UE-V Deployment</span></span>


<span data-ttu-id="26310-338">在准备部署 UE-V 时，还应考虑以下事项：</span><span class="sxs-lookup"><span data-stu-id="26310-338">You should also consider these things when you are preparing to deploy UE-V:</span></span>

-   [<span data-ttu-id="26310-339">管理凭据同步</span><span class="sxs-lookup"><span data-stu-id="26310-339">Managing credentials synchronization</span></span>](#creds)

-   [<span data-ttu-id="26310-340">Windows 应用设置同步</span><span class="sxs-lookup"><span data-stu-id="26310-340">Windows app settings synchronization</span></span>](#appxsettings)

-   [<span data-ttu-id="26310-341">自定义 UE-V 设置位置模板</span><span class="sxs-lookup"><span data-stu-id="26310-341">Custom UE-V settings location templates</span></span>](#custom)

-   [<span data-ttu-id="26310-342">无意间的用户设置配置</span><span class="sxs-lookup"><span data-stu-id="26310-342">Unintentional user settings configurations</span></span>](#prevent)

-   [<span data-ttu-id="26310-343">性能和容量</span><span class="sxs-lookup"><span data-stu-id="26310-343">Performance and capacity</span></span>](#capacity)

-   [<span data-ttu-id="26310-344">高可用性</span><span class="sxs-lookup"><span data-stu-id="26310-344">High availability</span></span>](#high)

-   [<span data-ttu-id="26310-345">计算机时钟同步</span><span class="sxs-lookup"><span data-stu-id="26310-345">Computer clock synchronization</span></span>](#clocksync)

### <a href="" id="creds"></a><span data-ttu-id="26310-346">在 UE-V 2.1 和 UE-V 2.1 SP1 中管理凭据同步</span><span class="sxs-lookup"><span data-stu-id="26310-346">Managing credentials synchronization in UE-V 2.1 and UE-V 2.1 SP1</span></span>

<span data-ttu-id="26310-347">许多企业应用程序（包括 Microsoft Outlook 和 Lync）在登录时提示用户输入其域凭据。</span><span class="sxs-lookup"><span data-stu-id="26310-347">Many enterprise applications, including Microsoft Outlook and Lync, prompt users for their domain credentials at login.</span></span> <span data-ttu-id="26310-348">用户可以选择将其凭据保存到磁盘，以防止每次打开这些应用程序时都必须输入它们。</span><span class="sxs-lookup"><span data-stu-id="26310-348">Users have the option of saving their credentials to disk to prevent having to enter them every time they open these applications.</span></span> <span data-ttu-id="26310-349">启用漫游凭据同步使用户可以在一台计算机上保存其凭据，避免在其环境中使用的每台计算机上重新输入它们。</span><span class="sxs-lookup"><span data-stu-id="26310-349">Enabling roaming credentials synchronization lets users save their credentials on one computer and avoid re-entering them on every computer they use in their environment.</span></span> <span data-ttu-id="26310-350">用户可将某些域凭据与 UE-V 2.1 和 2.1 SP1 同步。</span><span class="sxs-lookup"><span data-stu-id="26310-350">Users can synchronize some domain credentials with UE-V 2.1 and 2.1 SP1.</span></span>

**<span data-ttu-id="26310-351">重要提示</span><span class="sxs-lookup"><span data-stu-id="26310-351">Important</span></span>**  
<span data-ttu-id="26310-352">默认情况下，凭据同步处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="26310-352">Credentials synchronization is disabled by default.</span></span> <span data-ttu-id="26310-353">你必须在部署期间显式启用凭据同步以实现此功能。</span><span class="sxs-lookup"><span data-stu-id="26310-353">You must explicitly enable credentials synchronization during deployment to implement this feature.</span></span>



<span data-ttu-id="26310-354">UE-V 2.1 和 2.1 SP1 可以同步企业凭据，但不要漫游仅供在本地计算机上使用的凭据。</span><span class="sxs-lookup"><span data-stu-id="26310-354">UE-V 2.1 and 2.1 SP1 can synchronize enterprise credentials, but do not roam credentials intended only for use on the local computer.</span></span>

<span data-ttu-id="26310-355">凭据是同步设置，这意味着在 UE-V 同步后首次登录到你的配置文件时，这些凭据会应用到你的配置文件。</span><span class="sxs-lookup"><span data-stu-id="26310-355">Credentials are synchronous settings, meaning they are applied to your profile the first time you log in to your computer after UE-V synchronizes.</span></span>

<span data-ttu-id="26310-356">凭据同步由其自己的设置位置模板管理，默认情况下该模板处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="26310-356">Credentials synchronization is managed by its own settings location template, which is disabled by default.</span></span> <span data-ttu-id="26310-357">你可以通过用于其他模板的相同方法启用或禁用此模板。</span><span class="sxs-lookup"><span data-stu-id="26310-357">You can enable or disable this template through the same methods used for other templates.</span></span> <span data-ttu-id="26310-358">此功能的模板标识符为 RoamingCredentialSettings。</span><span class="sxs-lookup"><span data-stu-id="26310-358">The template identifier for this feature is RoamingCredentialSettings.</span></span>

**<span data-ttu-id="26310-359">重要提示</span><span class="sxs-lookup"><span data-stu-id="26310-359">Important</span></span>**  
<span data-ttu-id="26310-360">如果你在你的环境中使用 Active Directory 凭据漫游，我们建议你不要启用 UE-V 凭据漫游模板。</span><span class="sxs-lookup"><span data-stu-id="26310-360">If you are using Active Directory Credential Roaming in your environment, we recommend that you don’t enable the UE-V credential roaming template.</span></span>



<span data-ttu-id="26310-361">使用以下方法之一启用凭据同步：</span><span class="sxs-lookup"><span data-stu-id="26310-361">Use one of these methods to enable credentials synchronization:</span></span>

-   <span data-ttu-id="26310-362">公司设置中心</span><span class="sxs-lookup"><span data-stu-id="26310-362">Company Settings Center</span></span>

-   <span data-ttu-id="26310-363">PowerShell</span><span class="sxs-lookup"><span data-stu-id="26310-363">PowerShell</span></span>

-   <span data-ttu-id="26310-364">组策略</span><span class="sxs-lookup"><span data-stu-id="26310-364">Group Policy</span></span>

**<span data-ttu-id="26310-365">注意</span><span class="sxs-lookup"><span data-stu-id="26310-365">Note</span></span>**  
<span data-ttu-id="26310-366">凭据在同步期间加密。</span><span class="sxs-lookup"><span data-stu-id="26310-366">Credentials are encrypted during synchronization.</span></span>



<span data-ttu-id="26310-367">[公司设置中心](https://technet.microsoft.com/library/dn458903.aspx)**：** 选中 "Windows 设置" 下的 "漫游凭据设置" 复选框以启用凭据同步。</span><span class="sxs-lookup"><span data-stu-id="26310-367">[Company Settings Center](https://technet.microsoft.com/library/dn458903.aspx)**:** Check the Roaming Credential Settings check box under Windows Settings to enable credential synchronization.</span></span> <span data-ttu-id="26310-368">取消选中该框以禁用它。</span><span class="sxs-lookup"><span data-stu-id="26310-368">Uncheck the box to disable it.</span></span> <span data-ttu-id="26310-369">只有当您的帐户未配置为使用 Microsoft 帐户同步设置时，此复选框才会出现在 "公司设置中心" 中。</span><span class="sxs-lookup"><span data-stu-id="26310-369">This check box only appears in Company Settings Center if your account is not configured to synchronize settings using a Microsoft Account.</span></span>

<span data-ttu-id="26310-370">[Powershell](https://technet.microsoft.com/library/dn458937.aspx)**：** 此 PowerShell cmdlet 支持凭据同步：</span><span class="sxs-lookup"><span data-stu-id="26310-370">[PowerShell](https://technet.microsoft.com/library/dn458937.aspx)**:** This PowerShell cmdlet enables credential synchronization:</span></span>

``` syntax
Enable-UevTemplate RoamingCredentialSettings
```

<span data-ttu-id="26310-371">此 PowerShell cmdlet 禁用凭据同步：</span><span class="sxs-lookup"><span data-stu-id="26310-371">This PowerShell cmdlet disables credential synchronization:</span></span>

``` syntax
Disable-UevTemplate RoamingCredentialSettings
```

<span data-ttu-id="26310-372">[组策略](https://technet.microsoft.com/library/dn458893.aspx)**：** 必须[部署最新的 MDOP ADMX 模板](https://go.microsoft.com/fwlink/p/?LinkId=393944)，才能通过组策略启用凭据同步。</span><span class="sxs-lookup"><span data-stu-id="26310-372">[Group Policy](https://technet.microsoft.com/library/dn458893.aspx)**:** You must [deploy the latest MDOP ADMX template](https://go.microsoft.com/fwlink/p/?LinkId=393944) to enable credential synchronization through group policy.</span></span> <span data-ttu-id="26310-373">通过 Windows 设置管理凭据同步。</span><span class="sxs-lookup"><span data-stu-id="26310-373">Credentials synchronization is managed with the Windows settings.</span></span> <span data-ttu-id="26310-374">若要使用组策略管理此功能，请启用 "同步 Windows 设置" 策略。</span><span class="sxs-lookup"><span data-stu-id="26310-374">To manage this feature with Group Policy, enable the Synchronize Windows settings policy.</span></span>

1.  <span data-ttu-id="26310-375">打开组策略编辑器并导航到 "**用户配置"-"管理模板-Windows 组件-Microsoft 用户体验虚拟化**"。</span><span class="sxs-lookup"><span data-stu-id="26310-375">Open Group Policy Editor and navigate to **User Configuration – Administrative Templates – Windows Components – Microsoft User Experience Virtualization**.</span></span>

2.  <span data-ttu-id="26310-376">双击 "**同步 Windows 设置**"。</span><span class="sxs-lookup"><span data-stu-id="26310-376">Double-click on **Synchronize Windows settings**.</span></span>

3.  <span data-ttu-id="26310-377">如果启用此策略，则可以通过选中 "**漫游凭据**" 复选框，或通过取消选中 "禁用凭据同步" 来启用凭据同步。</span><span class="sxs-lookup"><span data-stu-id="26310-377">If this policy is enabled, you can enable credentials synchronization by checking the **Roaming Credentials** check box, or disable credentials synchronization by unchecking it.</span></span>

4.  <span data-ttu-id="26310-378">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="26310-378">Click **OK**.</span></span>

### <span data-ttu-id="26310-379">由 UE-V 同步的凭据位置</span><span class="sxs-lookup"><span data-stu-id="26310-379">Credential locations synchronized by UE-V</span></span>

<span data-ttu-id="26310-380">应用程序保存到以下位置的凭据文件是同步的：</span><span class="sxs-lookup"><span data-stu-id="26310-380">Credential files saved by applications into the following locations are synchronized:</span></span>

-   <span data-ttu-id="26310-381">%UserProfile%\\AppData\\Roaming\\Microsoft\\Credentials</span><span class="sxs-lookup"><span data-stu-id="26310-381">%UserProfile%\\AppData\\Roaming\\Microsoft\\Credentials</span></span>\\

-   <span data-ttu-id="26310-382">%UserProfile%\\AppData\\Roaming\\Microsoft\\Crypto</span><span class="sxs-lookup"><span data-stu-id="26310-382">%UserProfile%\\AppData\\Roaming\\Microsoft\\Crypto</span></span>\\

-   <span data-ttu-id="26310-383">%UserProfile%\\AppData\\Roaming\\Microsoft\\Protect</span><span class="sxs-lookup"><span data-stu-id="26310-383">%UserProfile%\\AppData\\Roaming\\Microsoft\\Protect</span></span>\\

-   <span data-ttu-id="26310-384">%UserProfile%\\AppData\\Roaming\\Microsoft\\SystemCertificates</span><span class="sxs-lookup"><span data-stu-id="26310-384">%UserProfile%\\AppData\\Roaming\\Microsoft\\SystemCertificates</span></span>\\

<span data-ttu-id="26310-385">保存到其他位置的凭据不会通过 UE-V 同步。</span><span class="sxs-lookup"><span data-stu-id="26310-385">Credentials saved to other locations are not synchronized by UE-V.</span></span>

### <a href="" id="appxsettings"></a><span data-ttu-id="26310-386">Windows 应用设置同步</span><span class="sxs-lookup"><span data-stu-id="26310-386">Windows app settings synchronization</span></span>

<span data-ttu-id="26310-387">UE-V 通过三种方式管理 Windows 应用设置同步：</span><span class="sxs-lookup"><span data-stu-id="26310-387">UE-V manages Windows app settings synchronization in three ways:</span></span>

-   <span data-ttu-id="26310-388">**同步 Windows 应用：** 允许或拒绝任何 Windows 应用同步</span><span class="sxs-lookup"><span data-stu-id="26310-388">**Sync Windows Apps:** Allow or deny any Windows app synchronization</span></span>

-   <span data-ttu-id="26310-389">**Windows 应用列表：** 同步 Windows 应用列表</span><span class="sxs-lookup"><span data-stu-id="26310-389">**Windows App List:** Synchronize a list of Windows apps</span></span>

-   <span data-ttu-id="26310-390">未**列出的默认同步行为：** 确定不在 Windows 应用列表中的 Windows 应用的同步行为。</span><span class="sxs-lookup"><span data-stu-id="26310-390">**Unlisted Default Sync Behavior:** Determine the synchronization behavior of Windows apps that are not in the Windows app list.</span></span>

<span data-ttu-id="26310-391">有关详细信息，请参阅[Windows 应用列表](https://technet.microsoft.com/library/dn458925.aspx#win8applist)。</span><span class="sxs-lookup"><span data-stu-id="26310-391">For more information, see the [Windows App List](https://technet.microsoft.com/library/dn458925.aspx#win8applist).</span></span>

### <a href="" id="custom"></a><span data-ttu-id="26310-392">自定义 UE-V 设置位置模板</span><span class="sxs-lookup"><span data-stu-id="26310-392">Custom UE-V settings location templates</span></span>

<span data-ttu-id="26310-393">如果你要部署 UE-V 以同步自定义应用程序的设置，你将使用 UE-V 生成器为这些桌面应用程序创建自定义设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="26310-393">If you are deploying UE-V to synchronize settings for custom applications, you will use the UE-V Generator to create custom settings location templates for those desktop applications.</span></span> <span data-ttu-id="26310-394">在测试环境中创建和测试自定义设置位置模板后，可以将设置位置模板部署到企业中的计算机。</span><span class="sxs-lookup"><span data-stu-id="26310-394">After you create and test a custom settings location template in a test environment, you can deploy the settings location templates to computers in the enterprise.</span></span>

<span data-ttu-id="26310-395">自定义设置位置模板必须使用现有部署基础结构（如企业软件分发（ESD）方法，如 System Center Configuration Manager）或通过配置 UE-V 设置模板目录进行部署。</span><span class="sxs-lookup"><span data-stu-id="26310-395">Custom settings location templates must be deployed with an existing deployment infrastructure, like an enterprise software distribution (ESD) method such as System Center Configuration Manager, with preferences, or by configuring an UE-V settings template catalog.</span></span> <span data-ttu-id="26310-396">必须使用 UE-V WMI 或 Windows PowerShell 注册使用 Configuration Manager 或组策略部署的模板。</span><span class="sxs-lookup"><span data-stu-id="26310-396">Templates that are deployed with Configuration Manager or Group Policy must be registered by using UE-V WMI or Windows PowerShell.</span></span>

<span data-ttu-id="26310-397">有关自定义设置位置模板的详细信息，请参阅[为自定义应用程序部署 ue-v 2。](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)</span><span class="sxs-lookup"><span data-stu-id="26310-397">For more information about custom settings location templates, see [Deploy UE-V 2.x for Custom Applications](deploy-ue-v-2x-for-custom-applications-new-uevv2.md).</span></span> <span data-ttu-id="26310-398">有关将 UE-V 与 Configuration Manager 配合使用的详细信息，请参阅[使用 System Center Configuration Manager 2012 配置 ue-v 2。](configuring-ue-v-2x-with-system-center-configuration-manager-2012-both-uevv2.md)</span><span class="sxs-lookup"><span data-stu-id="26310-398">For more information about using UE-V with Configuration Manager, see [Configuring UE-V 2.x with System Center Configuration Manager 2012](configuring-ue-v-2x-with-system-center-configuration-manager-2012-both-uevv2.md).</span></span>

### <a href="" id="prevent"></a><span data-ttu-id="26310-399">防止无意间的用户设置配置</span><span class="sxs-lookup"><span data-stu-id="26310-399">Prevent unintentional user settings configuration</span></span>

<span data-ttu-id="26310-400">UE-V 从设置存储位置下载新的用户设置信息，并在这些实例中将这些设置应用于本地计算机：</span><span class="sxs-lookup"><span data-stu-id="26310-400">UE-V downloads new user settings information from a settings storage location and applies the settings to the local computer in these instances:</span></span>

-   <span data-ttu-id="26310-401">每次启动具有注册的 UE-V 模板的应用程序时。</span><span class="sxs-lookup"><span data-stu-id="26310-401">Every time an application is started that has a registered UE-V template.</span></span>

-   <span data-ttu-id="26310-402">当用户登录到计算机时。</span><span class="sxs-lookup"><span data-stu-id="26310-402">When a user logs on to a computer.</span></span>

-   <span data-ttu-id="26310-403">用户解锁计算机时。</span><span class="sxs-lookup"><span data-stu-id="26310-403">When a user unlocks a computer.</span></span>

-   <span data-ttu-id="26310-404">连接到安装了 UE-V 的远程桌面计算机时。</span><span class="sxs-lookup"><span data-stu-id="26310-404">When a connection is made to a remote desktop computer that has UE-V installed.</span></span>

-   <span data-ttu-id="26310-405">当运行同步控制器应用程序计划任务时。</span><span class="sxs-lookup"><span data-stu-id="26310-405">When the Sync Controller Application scheduled task is run.</span></span>

<span data-ttu-id="26310-406">如果 UE-V 已安装在计算机 A 和计算机 B 上，而你希望应用程序的设置位于计算机 A 上，则计算机 A 应首先打开并关闭该应用程序。</span><span class="sxs-lookup"><span data-stu-id="26310-406">If UE-V is installed on computer A and computer B, and the settings that you want for the application are on computer A, then computer A should open and close the application first.</span></span> <span data-ttu-id="26310-407">如果首先在计算机 B 上打开和关闭应用程序，则计算机 A 上的应用程序设置将配置为计算机 B 上的应用程序设置。每个应用程序基础上的设置在计算机之间同步。</span><span class="sxs-lookup"><span data-stu-id="26310-407">If the application is opened and closed on computer B first, then the application settings on computer A are configured to the application settings on computer B. Settings are synchronized between computers on per-application basis.</span></span> <span data-ttu-id="26310-408">随着时间的推移，在计算机上打开和关闭首选设置时，设置会保持一致。</span><span class="sxs-lookup"><span data-stu-id="26310-408">Over time, settings become consistent between computers as they are opened and closed with preferred settings.</span></span>

<span data-ttu-id="26310-409">此方案也适用于 Windows 设置。</span><span class="sxs-lookup"><span data-stu-id="26310-409">This scenario also applies to Windows settings.</span></span> <span data-ttu-id="26310-410">如果计算机 B 上的 Windows 设置应该与计算机 A 上的 Windows 设置相同，则用户应该先登录，然后再注销计算机 A。</span><span class="sxs-lookup"><span data-stu-id="26310-410">If the Windows settings on computer B should be the same as the Windows settings on computer A, then the user should log on and log off computer A first.</span></span>

<span data-ttu-id="26310-411">如果用户所需的用户设置按错误的顺序应用，则可以通过针对覆盖了这些设置的计算机上的特定应用程序或 Windows 配置执行还原操作来恢复它们。</span><span class="sxs-lookup"><span data-stu-id="26310-411">If the user settings that the user wants are applied in the wrong order, they can be recovered by performing a restore operation for the specific application or Windows configuration on the computer on which the settings were overwritten.</span></span> <span data-ttu-id="26310-412">有关详细信息，请参阅[在 ue-v 2 中管理管理备份和还原](manage-administrative-backup-and-restore-in-ue-v-2x-new-topic-for-21.md)。</span><span class="sxs-lookup"><span data-stu-id="26310-412">For more information, see [Manage Administrative Backup and Restore in UE-V 2.x](manage-administrative-backup-and-restore-in-ue-v-2x-new-topic-for-21.md).</span></span>

### <a href="" id="capacity"></a><span data-ttu-id="26310-413">性能和容量规划</span><span class="sxs-lookup"><span data-stu-id="26310-413">Performance and capacity planning</span></span>

<span data-ttu-id="26310-414">通过标准磁盘容量和网络运行状况监视，指定你对 UE-V 的要求。</span><span class="sxs-lookup"><span data-stu-id="26310-414">Specify your requirements for UE-V with standard disk capacity and network health monitoring.</span></span>

<span data-ttu-id="26310-415">UE-V 使用服务器消息块（SMB）共享存储设置程序包。</span><span class="sxs-lookup"><span data-stu-id="26310-415">UE-V uses a Server Message Block (SMB) share for the storage of settings packages.</span></span> <span data-ttu-id="26310-416">设置包的大小根据每个应用程序的设置信息而有所不同。</span><span class="sxs-lookup"><span data-stu-id="26310-416">The size of settings packages varies depending on the settings information for each application.</span></span> <span data-ttu-id="26310-417">虽然大多数设置程序包较小，但同步可能较大的文件（如桌面映像）可能会导致性能较差，尤其是在速度较慢的网络上。</span><span class="sxs-lookup"><span data-stu-id="26310-417">While most settings packages are small, the synchronization of potentially large files, such as desktop images, can result in poor performance, particularly on slower networks.</span></span>

<span data-ttu-id="26310-418">若要减少网络延迟问题，请在用户计算机所在的同一本地网络上创建设置存储位置。</span><span class="sxs-lookup"><span data-stu-id="26310-418">To reduce problems with network latency, create settings storage locations on the same local networks where the users’ computers reside.</span></span> <span data-ttu-id="26310-419">我们建议每个用户 20 MB 的磁盘空间用于设置存储位置。</span><span class="sxs-lookup"><span data-stu-id="26310-419">We recommend 20 MB of disk space per user for the settings storage location.</span></span>

<span data-ttu-id="26310-420">默认情况下，UE-V 同步将在2秒后超时，以防止由于大型设置包而产生过多的延迟。</span><span class="sxs-lookup"><span data-stu-id="26310-420">By default, UE-V synchronization times out after 2 seconds to prevent excessive lag due to a large settings package.</span></span> <span data-ttu-id="26310-421">你可以使用[组策略对象](https://technet.microsoft.com/library/dn458893.aspx)配置 Powerschool = SyncProvider 设置。</span><span class="sxs-lookup"><span data-stu-id="26310-421">You can configure the SyncMethod=SyncProvider setting by using [Group Policy Objects](https://technet.microsoft.com/library/dn458893.aspx).</span></span>

### <a href="" id="high"></a><span data-ttu-id="26310-422">UE-V 的高可用性</span><span class="sxs-lookup"><span data-stu-id="26310-422">High Availability for UE-V</span></span>

<span data-ttu-id="26310-423">UE-V 设置存储位置和设置模板目录支持将用户数据存储在任何可写的共享上。</span><span class="sxs-lookup"><span data-stu-id="26310-423">The UE-V settings storage location and settings template catalog support storing user data on any writable share.</span></span> <span data-ttu-id="26310-424">为确保高可用性，请遵循以下条件：</span><span class="sxs-lookup"><span data-stu-id="26310-424">To ensure high availability, follow these criteria:</span></span>

-   <span data-ttu-id="26310-425">使用 NTFS 文件系统设置存储卷的格式。</span><span class="sxs-lookup"><span data-stu-id="26310-425">Format the storage volume with an NTFS file system.</span></span>

-   <span data-ttu-id="26310-426">共享可以使用分布式文件系统（DFS），但有一些限制。</span><span class="sxs-lookup"><span data-stu-id="26310-426">The share can use Distributed File System (DFS) but there are restrictions.</span></span>
<span data-ttu-id="26310-427">特别是，支持分布式文件系统复制（使用或不使用分布式文件系统命名空间（DFS-N）的单个目标配置。</span><span class="sxs-lookup"><span data-stu-id="26310-427">Specifically, Distributed File System Replication (DFS-R) single target configuration with or without a Distributed File System Namespace (DFS-N) is supported.</span></span>
<span data-ttu-id="26310-428">同样，DFS-N 仅支持单个目标配置。</span><span class="sxs-lookup"><span data-stu-id="26310-428">Likewise, only single target configuration is supported with DFS-N.</span></span>
<span data-ttu-id="26310-429">有关详细信息，请参阅[microsoft 有关复制的用户配置文件数据的支持声明](https://go.microsoft.com/fwlink/p/?LinkId=313991)，以及[有关适用于 DFS 和 dfs 部署方案的 microsoft 支持策略的信息](https://support.microsoft.com/kb/2533009)。</span><span class="sxs-lookup"><span data-stu-id="26310-429">For detailed information, see [Microsoft’s Support Statement Around Replicated User Profile Data](https://go.microsoft.com/fwlink/p/?LinkId=313991) and also [Information about Microsoft support policy for a DFS-R and DFS-N deployment scenario](https://support.microsoft.com/kb/2533009).</span></span>

    <span data-ttu-id="26310-430">此外，由于 SYSVOL 使用 DFS 进行复制，因此无法将 SYSVOL 用于 UE-V 数据文件复制。</span><span class="sxs-lookup"><span data-stu-id="26310-430">In addition, because SYSVOL uses DFS-R for replication, SYSVOL cannot be used for UE-V data file replication.</span></span>

-   <span data-ttu-id="26310-431">配置在[部署 ue-v 2. x 的设置存储位置](https://technet.microsoft.com/library/dn458891.aspx#ssl)中指定的共享权限和 NTFS 访问控制列表（acl）。</span><span class="sxs-lookup"><span data-stu-id="26310-431">Configure the share permissions and NTFS access control lists (ACLs) as specified in [Deploying the Settings Storage Location for UE-V 2.x](https://technet.microsoft.com/library/dn458891.aspx#ssl).</span></span>

-   <span data-ttu-id="26310-432">将文件服务器群集与 UE-V Agent 配合使用，可在通信失败时提供对用户状态数据副本的访问权限。</span><span class="sxs-lookup"><span data-stu-id="26310-432">Use file server clustering along with the UE-V Agent to provide access to copies of user state data in the event of communications failures.</span></span>

-   <span data-ttu-id="26310-433">你可以将设置存储路径数据（用户数据）和设置模板目录模板存储在群集共享、DFS-N 共享或两者上。</span><span class="sxs-lookup"><span data-stu-id="26310-433">You can store the settings storage path data (user data) and settings template catalog templates on clustered shares, on DFS-N shares, or on both.</span></span>

### <a href="" id="clocksync"></a><span data-ttu-id="26310-434">同步 UE-V 设置同步的计算机时钟</span><span class="sxs-lookup"><span data-stu-id="26310-434">Synchronize computer clocks for UE-V settings synchronization</span></span>

<span data-ttu-id="26310-435">运行 UE-V Agent 的计算机必须使用时间服务器保持一致的设置体验。</span><span class="sxs-lookup"><span data-stu-id="26310-435">Computers that run the UE-V Agent must use a time server to maintain a consistent settings experience.</span></span> <span data-ttu-id="26310-436">UE-V 使用时间戳确定设置是否必须从设置存储位置同步。</span><span class="sxs-lookup"><span data-stu-id="26310-436">UE-V uses time stamps to determine if settings must be synchronized from the settings storage location.</span></span> <span data-ttu-id="26310-437">如果计算机时钟不准确，则较旧的设置可能会覆盖较新的设置，或者新设置可能不会保存到设置存储位置。</span><span class="sxs-lookup"><span data-stu-id="26310-437">If the computer clock is inaccurate, older settings can overwrite newer settings, or the new settings might not be saved to the settings storage location.</span></span>

## <a href="" id="prereqs"></a><span data-ttu-id="26310-438">确认系统必备和支持的 UE-V 配置</span><span class="sxs-lookup"><span data-stu-id="26310-438">Confirm Prerequisites and Supported Configurations for UE-V</span></span>


<span data-ttu-id="26310-439">在继续操作之前，请确保你的环境包括运行 UE-V 的这些要求。</span><span class="sxs-lookup"><span data-stu-id="26310-439">Before you proceed, make sure your environment includes these requirements for running UE-V.</span></span>

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
<th align="left"><strong><span data-ttu-id="26310-440">操作系统</span><span class="sxs-lookup"><span data-stu-id="26310-440">Operating system</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="26310-441">版本</span><span class="sxs-lookup"><span data-stu-id="26310-441">Edition</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="26310-442">Service pack</span><span class="sxs-lookup"><span data-stu-id="26310-442">Service pack</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="26310-443">系统体系结构</span><span class="sxs-lookup"><span data-stu-id="26310-443">System architecture</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="26310-444">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="26310-444">Windows PowerShell</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="26310-445">Microsoft .NET Framework</span><span class="sxs-lookup"><span data-stu-id="26310-445">Microsoft .NET Framework</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="26310-446">Windows 7</span><span class="sxs-lookup"><span data-stu-id="26310-446">Windows 7</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-447">旗舰版、企业版或专业版</span><span class="sxs-lookup"><span data-stu-id="26310-447">Ultimate, Enterprise, or Professional Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-448">SP1</span><span class="sxs-lookup"><span data-stu-id="26310-448">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-449">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="26310-449">32-bit or 64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-450">Windows PowerShell 3.0 或更高版本</span><span class="sxs-lookup"><span data-stu-id="26310-450">Windows PowerShell 3.0 or higher</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-451">用于 UE-V 2.1 的 .NET Framework 4.5 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="26310-451">.NET Framework 4.5 or higher for UE-V 2.1.</span></span></p>
<p><span data-ttu-id="26310-452">用于 UE-V 2.0 的 .NET Framework 4 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="26310-452">.NET Framework 4 or higher for UE-V 2.0.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="26310-453">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="26310-453">Windows Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-454">标准版、企业版、数据中心版或 Web 服务器</span><span class="sxs-lookup"><span data-stu-id="26310-454">Standard, Enterprise, Datacenter, or Web Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-455">SP1</span><span class="sxs-lookup"><span data-stu-id="26310-455">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-456">64 位</span><span class="sxs-lookup"><span data-stu-id="26310-456">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-457">Windows PowerShell 3.0 或更高版本</span><span class="sxs-lookup"><span data-stu-id="26310-457">Windows PowerShell 3.0 or higher</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-458">用于 UE-V 2.1 的 .NET Framework 4.5 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="26310-458">.NET Framework 4.5 or higher for UE-V 2.1.</span></span></p>
<p><span data-ttu-id="26310-459">用于 UE-V 2.0 的 .NET Framework 4 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="26310-459">.NET Framework 4 or higher for UE-V 2.0.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="26310-460">Windows 8 和 Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="26310-460">Windows 8 and Windows 8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-461">企业版或专业版</span><span class="sxs-lookup"><span data-stu-id="26310-461">Enterprise or Pro</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-462">无</span><span class="sxs-lookup"><span data-stu-id="26310-462">None</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-463">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="26310-463">32-bit or 64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-464">Windows PowerShell 3.0 或更高版本</span><span class="sxs-lookup"><span data-stu-id="26310-464">Windows PowerShell 3.0 or higher</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-465">.NET Framework 4.5 或更高版本</span><span class="sxs-lookup"><span data-stu-id="26310-465">.NET Framework 4.5 or higher</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="26310-466">Windows 10 预1607版本</span><span class="sxs-lookup"><span data-stu-id="26310-466">Windows 10, pre-1607 version</span></span></p>
<div class="alert">
<strong><span data-ttu-id="26310-467">注意</span><span class="sxs-lookup"><span data-stu-id="26310-467">Note</span></span></strong><br/><p><span data-ttu-id="26310-468">仅 UE-V 2.1 SP1 支持 Windows 10 的预1607版本</span><span class="sxs-lookup"><span data-stu-id="26310-468">Only UE-V 2.1 SP1 supports Windows 10, pre-1607 version</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="26310-469">企业版或专业版</span><span class="sxs-lookup"><span data-stu-id="26310-469">Enterprise or Pro</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-470">无</span><span class="sxs-lookup"><span data-stu-id="26310-470">None</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-471">32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="26310-471">32-bit or 64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-472">Windows PowerShell 3.0 或更高版本</span><span class="sxs-lookup"><span data-stu-id="26310-472">Windows PowerShell 3.0 or higher</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-473">.NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="26310-473">.NET Framework 4.6</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="26310-474">Windows Server 2012 和 Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="26310-474">Windows Server 2012 and Windows Server 2012 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-475">标准版或数据中心</span><span class="sxs-lookup"><span data-stu-id="26310-475">Standard or Datacenter</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-476">无</span><span class="sxs-lookup"><span data-stu-id="26310-476">None</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-477">64 位</span><span class="sxs-lookup"><span data-stu-id="26310-477">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-478">Windows PowerShell 3.0 或更高版本</span><span class="sxs-lookup"><span data-stu-id="26310-478">Windows PowerShell 3.0 or higher</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-479">.NET Framework 4.5 或更高版本</span><span class="sxs-lookup"><span data-stu-id="26310-479">.NET Framework 4.5 or higher</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="26310-480">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="26310-480">Windows Server 2016</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-481">标准版或数据中心</span><span class="sxs-lookup"><span data-stu-id="26310-481">Standard or Datacenter</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-482">无</span><span class="sxs-lookup"><span data-stu-id="26310-482">None</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-483">64 位</span><span class="sxs-lookup"><span data-stu-id="26310-483">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-484">Windows PowerShell 3.0 或更高版本</span><span class="sxs-lookup"><span data-stu-id="26310-484">Windows PowerShell 3.0 or higher</span></span></p></td>
<td align="left"><p><span data-ttu-id="26310-485">.NET Framework 4.6 或更高版本</span><span class="sxs-lookup"><span data-stu-id="26310-485">.NET Framework 4.6 or higher</span></span></p></td>
</tr>
</tbody>
</table>



<span data-ttu-id="26310-486">同样 .。。</span><span class="sxs-lookup"><span data-stu-id="26310-486">Also…</span></span>

-   <span data-ttu-id="26310-487">**MDOP 许可证：** 此技术是 Microsoft 桌面优化包（MDOP）的一部分。</span><span class="sxs-lookup"><span data-stu-id="26310-487">**MDOP License:** This technology is a part of the Microsoft Desktop Optimization Pack (MDOP).</span></span> <span data-ttu-id="26310-488">企业客户可以通过 Microsoft 软件保障获得 MDOP。</span><span class="sxs-lookup"><span data-stu-id="26310-488">Enterprise customers can get MDOP with Microsoft Software Assurance.</span></span> <span data-ttu-id="26310-489">有关 Microsoft 软件保证和获取 MDOP 的详细信息，请参阅如何获取 MDOP （ https://go.microsoft.com/fwlink/p/?LinkId=322049) 。</span><span class="sxs-lookup"><span data-stu-id="26310-489">For more information about Microsoft Software Assurance and acquiring MDOP, see How Do I Get MDOP (https://go.microsoft.com/fwlink/p/?LinkId=322049).</span></span>

-   <span data-ttu-id="26310-490">要安装的任何计算机的**管理凭据**</span><span class="sxs-lookup"><span data-stu-id="26310-490">**Administrative Credentials** for any computer on which you’ll be installing</span></span>

**<span data-ttu-id="26310-491">注意</span><span class="sxs-lookup"><span data-stu-id="26310-491">Note</span></span>**  

-   <span data-ttu-id="26310-492">从 WIndows 10 版本1607开始，UE-V 已包含在[windows 10 For 企业](https://www.microsoft.com/WindowsForBusiness/windows-for-enterprise)中，不再属于 Microsoft 桌面优化包。</span><span class="sxs-lookup"><span data-stu-id="26310-492">Starting with WIndows 10, version 1607, UE-V is included with [Windows 10 for Enterprise](https://www.microsoft.com/WindowsForBusiness/windows-for-enterprise) and is no longer part of the Microsoft Desktop Optimization Pack.</span></span>

-   <span data-ttu-id="26310-493">UE-V Agent 的 UE-V Windows PowerShell 功能需要安装 .NET Framework 4 或更高版本以及 Windows PowerShell 3.0 或更高版本才能启用。</span><span class="sxs-lookup"><span data-stu-id="26310-493">The UE-V Windows PowerShell feature of the UE-V Agent requires .NET Framework 4 or higher and Windows PowerShell 3.0 or higher to be enabled.</span></span> <span data-ttu-id="26310-494">[在此处](https://go.microsoft.com/fwlink/?LinkId=309609)下载 Windows PowerShell 3.0。</span><span class="sxs-lookup"><span data-stu-id="26310-494">Download Windows PowerShell 3.0 [here](https://go.microsoft.com/fwlink/?LinkId=309609).</span></span>

-   <span data-ttu-id="26310-495">在运行 Windows 7 或 Windows Server 2008 R2 操作系统的计算机上安装 .NET Framework 4 或 .NET Framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="26310-495">Install .NET Framework 4 or .NET Framework 4.5 on computers that run the Windows 7 or the Windows Server 2008 R2 operating system.</span></span> <span data-ttu-id="26310-496">Windows 8、Windows 8.1 和 Windows Server 2012 操作系统附带了 .NET Framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="26310-496">The Windows 8, Windows 8.1, and Windows Server 2012 operating systems come with .NET Framework 4.5 installed.</span></span> <span data-ttu-id="26310-497">Windows 10 操作系统附带了 .NET Framework 4.6。</span><span class="sxs-lookup"><span data-stu-id="26310-497">The Windows 10 operating system comes with .NET Framework 4.6 installed.</span></span>
-   <span data-ttu-id="26310-498">UE-V 不支持强制配置文件的 "删除漫游缓存" 策略，不应使用。</span><span class="sxs-lookup"><span data-stu-id="26310-498">The “Delete Roaming Cache” policy for Mandatory profiles is not supported with UE-V and should not be used.</span></span>



<span data-ttu-id="26310-499">不存在特定于 UE-V 的特殊随机访问内存（RAM）要求。</span><span class="sxs-lookup"><span data-stu-id="26310-499">There are no special random access memory (RAM) requirements specific to UE-V.</span></span>

### <span data-ttu-id="26310-500">通过同步提供程序同步设置</span><span class="sxs-lookup"><span data-stu-id="26310-500">Synchronization of Settings through the Sync Provider</span></span>

<span data-ttu-id="26310-501">同步提供程序是用户的默认设置，用于将本地缓存与这些实例中的设置存储位置同步：</span><span class="sxs-lookup"><span data-stu-id="26310-501">Sync Provider is the default setting for users, which synchronizes a local cache with the settings storage location in these instances:</span></span>

-   <span data-ttu-id="26310-502">登录/注销</span><span class="sxs-lookup"><span data-stu-id="26310-502">Logon/logoff</span></span>

-   <span data-ttu-id="26310-503">锁定/解锁</span><span class="sxs-lookup"><span data-stu-id="26310-503">Lock/unlock</span></span>

-   <span data-ttu-id="26310-504">远程桌面连接/断开连接</span><span class="sxs-lookup"><span data-stu-id="26310-504">Remote desktop connect/disconnect</span></span>

-   <span data-ttu-id="26310-505">应用程序打开/关闭</span><span class="sxs-lookup"><span data-stu-id="26310-505">Application open/close</span></span>

<span data-ttu-id="26310-506">计划任务每隔30分钟或通过某些应用程序的特定触发事件来管理此设置的同步。</span><span class="sxs-lookup"><span data-stu-id="26310-506">A scheduled task manages this synchronization of settings every 30 minutes or through certain trigger events for certain applications.</span></span> <span data-ttu-id="26310-507">有关详细信息，请参阅[更改 ue-v 2. x 计划任务的频率](changing-the-frequency-of-ue-v-2x-scheduled-tasks-both-uevv2.md)。</span><span class="sxs-lookup"><span data-stu-id="26310-507">For more information, see [Changing the Frequency of UE-V 2.x Scheduled Tasks](changing-the-frequency-of-ue-v-2x-scheduled-tasks-both-uevv2.md).</span></span>

<span data-ttu-id="26310-508">UE-V Agent 会同步不始终连接到企业网络（远程计算机和笔记本电脑）的计算机的用户设置，以及始终连接到网络（运行 Windows Server 和托管虚拟桌面界面（VDI）会话的计算机）的计算机的用户设置。</span><span class="sxs-lookup"><span data-stu-id="26310-508">The UE-V Agent synchronizes user settings for computers that are not always connected to the enterprise network (remote computers and laptops) and computers that are always connected to the network (computers that run Windows Server and host virtual desktop interface (VDI) sessions).</span></span>

<span data-ttu-id="26310-509">**对始终可用的连接的计算机进行同步：** 在始终连接到网络的计算机上使用 UE-V 时，必须使用*powerschool = None*参数配置 ue-v Agent 以同步设置，该参数将设置存储服务器视为标准网络共享。</span><span class="sxs-lookup"><span data-stu-id="26310-509">**Synchronization for computers with always-available connections:** When you use UE-V on computers that are always connected to the network, you must configure the UE-V Agent to synchronize settings by using the *SyncMethod=None* parameter, which treats the settings storage server as a standard network share.</span></span> <span data-ttu-id="26310-510">在此配置中，可以配置 UE-V Agent 以通知应用程序设置的导入是否已延迟。</span><span class="sxs-lookup"><span data-stu-id="26310-510">In this configuration, the UE-V Agent can be configured to notify if the import of the application settings is delayed.</span></span>

<span data-ttu-id="26310-511">通过以下方法之一启用此配置：</span><span class="sxs-lookup"><span data-stu-id="26310-511">Enable this configuration through one of these methods:</span></span>

-   <span data-ttu-id="26310-512">在 UE-V 安装期间，在命令提示符处或在批处理文件中，设置 AgentSetup.exe 参数*powerschool = None*。</span><span class="sxs-lookup"><span data-stu-id="26310-512">During UE-V installation, at the command prompt or in a batch file, set the AgentSetup.exe parameter *SyncMethod = None*.</span></span> <span data-ttu-id="26310-513">[部署 ue-v 2. x agent](https://technet.microsoft.com/library/dn458891.aspx#agent)可提供更多信息。</span><span class="sxs-lookup"><span data-stu-id="26310-513">[Deploying the UE-V 2.x Agent](https://technet.microsoft.com/library/dn458891.aspx#agent) provides more information.</span></span>

-   <span data-ttu-id="26310-514">在 UE-V 安装之后，使用 System Center 2012 配置管理器中的设置管理功能或 MDOP ADMX 模板推送*powerschool = None*配置。</span><span class="sxs-lookup"><span data-stu-id="26310-514">After the UE-V installation, use the Settings Management feature in System Center 2012 Configuration Manager or the MDOP ADMX templates to push the *SyncMethod = None* configuration.</span></span>

-   <span data-ttu-id="26310-515">使用 Windows PowerShell 或 Windows Management Instrumentation （WMI）设置*powerschool = None*配置。</span><span class="sxs-lookup"><span data-stu-id="26310-515">Use Windows PowerShell or Windows Management Instrumentation (WMI) to set the *SyncMethod = None* configuration.</span></span>

    **<span data-ttu-id="26310-516">注意</span><span class="sxs-lookup"><span data-stu-id="26310-516">Note</span></span>**  
    <span data-ttu-id="26310-517">最后两种方法对虚拟桌面基础结构（VDI）环境不起作用。</span><span class="sxs-lookup"><span data-stu-id="26310-517">These last two methods do not work for pooled virtual desktop infrastructure (VDI) environments.</span></span>



<span data-ttu-id="26310-518">必须重新启动计算机才能使设置开始同步。</span><span class="sxs-lookup"><span data-stu-id="26310-518">You must restart the computer before the settings start to synchronize.</span></span>

**<span data-ttu-id="26310-519">注意</span><span class="sxs-lookup"><span data-stu-id="26310-519">Note</span></span>**  
<span data-ttu-id="26310-520">如果设置*powerschool = None*，则任何设置更改都将直接保存到服务器。</span><span class="sxs-lookup"><span data-stu-id="26310-520">If you set *SyncMethod = None*, any settings changes are saved directly to the server.</span></span> <span data-ttu-id="26310-521">如果找不到指向设置存储路径的网络连接，则设置更改将缓存在设备上，并且将在下次运行同步提供程序时进行同步。</span><span class="sxs-lookup"><span data-stu-id="26310-521">If the network connection to the settings storage path is not found, then the settings changes are cached on the device and are synchronized the next time that the sync provider runs.</span></span> <span data-ttu-id="26310-522">如果未找到设置存储路径，并且在注销时从池中的 VDI 环境中删除了用户配置文件，则会丢失设置更改，并且用户必须在计算机重新连接到设置存储路径时重新应用更改。</span><span class="sxs-lookup"><span data-stu-id="26310-522">If the settings storage path is not found and the user profile is removed from a pooled VDI environment on logoff, settings changes are lost and the user must reapply the change when the computer is reconnected to the settings storage path.</span></span>



<span data-ttu-id="26310-523">\**外部同步引擎的同步：\*\*\*Powerschool = External*参数指定如果 ue-v 设置写入到用户计算机上的本地文件夹，则可以使用任何外部同步引擎（如 OneDrive for Business、工作文件夹、Sharepoint 或 Dropbox）将这些设置应用于用户访问的不同计算机。</span><span class="sxs-lookup"><span data-stu-id="26310-523">**Synchronization for external sync engines:** The *SyncMethod=External* parameter specifies that if UE-V settings are written to a local folder on the user computer, then any external sync engine (such as OneDrive for Business, Work Folders, Sharepoint, or Dropbox) can be used to apply these settings to the different computers that users access.</span></span>

<span data-ttu-id="26310-524">**对共享的 VDI 会话的支持：** UE-V 2.1 和 2.1 SP1 提供对在最终用户之间共享的 VDI 会话的支持。</span><span class="sxs-lookup"><span data-stu-id="26310-524">**Support for shared VDI sessions:** UE-V 2.1 and 2.1 SP1 provide support for VDI sessions that are shared among end users.</span></span> <span data-ttu-id="26310-525">你可以注册和配置特殊的 VDI 模板，从而确保 UE-V 将其所有功能完整地保留为非永久性 VDI 会话。</span><span class="sxs-lookup"><span data-stu-id="26310-525">You can register and configure a special VDI template, which ensures that UE-V keeps all of its functionality intact for non-persistent VDI sessions.</span></span>

**<span data-ttu-id="26310-526">注意</span><span class="sxs-lookup"><span data-stu-id="26310-526">Note</span></span>**  
<span data-ttu-id="26310-527">如果您不为非永久性 VDI 会话启用 VDI 模式，则某些功能不起作用，如[备份/还原和上一次正常工作（LKG）](https://technet.microsoft.com/library/dn878331.aspx)。</span><span class="sxs-lookup"><span data-stu-id="26310-527">If you do not enable VDI mode for non-persistent VDI sessions, certain features do not work, such as [back-up/restore and last known good (LKG)](https://technet.microsoft.com/library/dn878331.aspx).</span></span>



<span data-ttu-id="26310-528">VDI 模板由 UE-V 2.1 和 2.1 SP1 提供，并且在安装后，通常在此处可用 C:\\program files Files\\Microsoft 用户体验 Virtualization\\Templates\\VdiState.xml</span><span class="sxs-lookup"><span data-stu-id="26310-528">The VDI template is provided with UE-V 2.1 and 2.1 SP1 and is typically available here after installation: C:\\Program Files\\Microsoft User Experience Virtualization\\Templates\\VdiState.xml</span></span>

### <span data-ttu-id="26310-529">UE-V 发电机支持的先决条件</span><span class="sxs-lookup"><span data-stu-id="26310-529">Prerequisites for UE-V Generator support</span></span>

<span data-ttu-id="26310-530">在用于创建自定义设置位置模板的计算机上安装 UE-V 发生器。</span><span class="sxs-lookup"><span data-stu-id="26310-530">Install the UE-V Generator on the computer that is used to create custom settings location templates.</span></span> <span data-ttu-id="26310-531">此计算机应该能够运行其设置已同步的应用程序。</span><span class="sxs-lookup"><span data-stu-id="26310-531">This computer should be able to run the applications whose settings are synchronized.</span></span> <span data-ttu-id="26310-532">您必须是运行 UE-V 发生器软件的计算机上 "管理员" 组的成员。</span><span class="sxs-lookup"><span data-stu-id="26310-532">You must be a member of the Administrators group on the computer that runs the UE-V Generator software.</span></span>

<span data-ttu-id="26310-533">UE-V 生成器必须安装在使用 NTFS 文件系统的计算机上。</span><span class="sxs-lookup"><span data-stu-id="26310-533">The UE-V Generator must be installed on a computer that uses an NTFS file system.</span></span> <span data-ttu-id="26310-534">UE-V 发生器软件需要 .NET Framework 4。</span><span class="sxs-lookup"><span data-stu-id="26310-534">The UE-V Generator software requires .NET Framework 4.</span></span> <span data-ttu-id="26310-535">有关详细信息，请参阅[为自定义应用程序部署 ue-v 2。](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)</span><span class="sxs-lookup"><span data-stu-id="26310-535">For more information, see [Deploy UE-V 2.x for Custom Applications](deploy-ue-v-2x-for-custom-applications-new-uevv2.md).</span></span>

## <span data-ttu-id="26310-536">此产品的其他资源</span><span class="sxs-lookup"><span data-stu-id="26310-536">Other resources for this product</span></span>


-   [<span data-ttu-id="26310-537">Microsoft 用户体验虚拟化（UE-V） 2. x</span><span class="sxs-lookup"><span data-stu-id="26310-537">Microsoft User Experience Virtualization (UE-V) 2.x</span></span>](index.md)

-   [<span data-ttu-id="26310-538">UE-V 2.x 入门</span><span class="sxs-lookup"><span data-stu-id="26310-538">Get Started with UE-V 2.x</span></span>](get-started-with-ue-v-2x-new-uevv2.md)

-   [<span data-ttu-id="26310-539">管理 UE-V 2. x</span><span class="sxs-lookup"><span data-stu-id="26310-539">Administering UE-V 2.x</span></span>](administering-ue-v-2x-new-uevv2.md)

-   [<span data-ttu-id="26310-540">解决 UE-V 2. x</span><span class="sxs-lookup"><span data-stu-id="26310-540">Troubleshooting UE-V 2.x</span></span>](troubleshooting-ue-v-2x-both-uevv2.md)

-   [<span data-ttu-id="26310-541">UE-V 2.x 的技术参考</span><span class="sxs-lookup"><span data-stu-id="26310-541">Technical Reference for UE-V 2.x</span></span>](technical-reference-for-ue-v-2x-both-uevv2.md)














