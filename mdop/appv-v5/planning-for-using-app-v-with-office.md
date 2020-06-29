---
title: 计划将 App-V 与 Office 结合使用
description: 计划将 App-V 与 Office 结合使用
author: dansimp
ms.assetid: c4371869-4bfc-4d13-9198-ef19f99fc192
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ff523c8f8827e295c8fb9a2d9fd0e02d5b019aa8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798292"
---
# <span data-ttu-id="557d3-103">计划将 App-V 与 Office 结合使用</span><span class="sxs-lookup"><span data-stu-id="557d3-103">Planning for Using App-V with Office</span></span>


<span data-ttu-id="557d3-104">使用以下信息规划如何使用 App-v 部署 Office。</span><span class="sxs-lookup"><span data-stu-id="557d3-104">Use the following information to plan how to deploy Office by using App-V.</span></span> <span data-ttu-id="557d3-105">本文包括：</span><span class="sxs-lookup"><span data-stu-id="557d3-105">This article includes:</span></span>

-   [<span data-ttu-id="557d3-106">语言包的 app-v 支持</span><span class="sxs-lookup"><span data-stu-id="557d3-106">App-V support for Language Packs</span></span>](#bkmk-lang-pack)

-   [<span data-ttu-id="557d3-107">Microsoft Office 支持的版本</span><span class="sxs-lookup"><span data-stu-id="557d3-107">Supported versions of Microsoft Office</span></span>](#bkmk-office-vers-supp-appv)

-   [<span data-ttu-id="557d3-108">规划将 App-v 与早期版本的 Office 配合使用</span><span class="sxs-lookup"><span data-stu-id="557d3-108">Planning for using App-V with coexisting versions of Office</span></span>](#bkmk-plan-coexisting)

-   [<span data-ttu-id="557d3-109">Office 在部署时如何与 Windows 集成使用 app-v 部署 Office</span><span class="sxs-lookup"><span data-stu-id="557d3-109">How Office integrates with Windows when you deploy use App-V to deploy Office</span></span>](#bkmk-office-integration-win)

## <a href="" id="bkmk-lang-pack"></a><span data-ttu-id="557d3-110">语言包的 app-v 支持</span><span class="sxs-lookup"><span data-stu-id="557d3-110">App-V support for Language Packs</span></span>


<span data-ttu-id="557d3-111">你可以使用 app-v 5.0 Sequencer 为语言包、语言界面包、校对工具和屏幕提示语言创建插件包。</span><span class="sxs-lookup"><span data-stu-id="557d3-111">You can use the App-V 5.0 Sequencer to create plug-in packages for Language Packs, Language Interface Packs, Proofing Tools and ScreenTip Languages.</span></span> <span data-ttu-id="557d3-112">然后，你可以在连接组中包含插件程序包，以及使用 Office 部署工具包创建的 Office 2013 程序包。</span><span class="sxs-lookup"><span data-stu-id="557d3-112">You can then include the plug-in packages in a Connection Group, along with the Office 2013 package that you create by using the Office Deployment Toolkit.</span></span> <span data-ttu-id="557d3-113">Office 应用程序和插件语言包在同一连接组中无缝交互，就像在连接组中组合在一起的任何其他程序包一样。</span><span class="sxs-lookup"><span data-stu-id="557d3-113">The Office applications and the plug-in Language Packs interact seamlessly in the same connection group, just like any other packages that are grouped together in a connection group.</span></span>

<span data-ttu-id="557d3-114">**注意** Microsoft Visio 和 Microsoft Project 不提供对泰语语言包的支持。</span><span class="sxs-lookup"><span data-stu-id="557d3-114">**Note** Microsoft Visio and Microsoft Project do not provide support for the Thai Language Pack.</span></span>

 

## <a href="" id="bkmk-office-vers-supp-appv"></a><span data-ttu-id="557d3-115">Microsoft Office 支持的版本</span><span class="sxs-lookup"><span data-stu-id="557d3-115">Supported versions of Microsoft Office</span></span>


<span data-ttu-id="557d3-116">下表列出了 App-v 支持的 Microsoft Office 版本、Office 程序包的创建方法、支持的许可以及支持的部署。</span><span class="sxs-lookup"><span data-stu-id="557d3-116">The following table lists the versions of Microsoft Office that App-V supports, methods of Office package creation, supported licensing, and supported deployments.</span></span>

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
<th align="left"><span data-ttu-id="557d3-117">支持的 Office 版本</span><span class="sxs-lookup"><span data-stu-id="557d3-117">Supported Office Version</span></span></th>
<th align="left"><span data-ttu-id="557d3-118">支持的应用-V 版本</span><span class="sxs-lookup"><span data-stu-id="557d3-118">Supported App-V Versions</span></span></th>
<th align="left"><span data-ttu-id="557d3-119">程序包创建</span><span class="sxs-lookup"><span data-stu-id="557d3-119">Package Creation</span></span></th>
<th align="left"><span data-ttu-id="557d3-120">支持的许可</span><span class="sxs-lookup"><span data-stu-id="557d3-120">Supported Licensing</span></span></th>
<th align="left"><span data-ttu-id="557d3-121">支持的部署</span><span class="sxs-lookup"><span data-stu-id="557d3-121">Supported Deployments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="557d3-122">适用于企业的 Microsoft 365 应用</span><span class="sxs-lookup"><span data-stu-id="557d3-122">Microsoft 365 Apps for enterprise</span></span></p>
<p><span data-ttu-id="557d3-123">还支持：</span><span class="sxs-lookup"><span data-stu-id="557d3-123">Also supported:</span></span></p>
<ul>
<li><p><span data-ttu-id="557d3-124">Visio Pro for Office 365</span><span class="sxs-lookup"><span data-stu-id="557d3-124">Visio Pro for Office 365</span></span></p></li>
<li><p><span data-ttu-id="557d3-125">Project Pro for Office 365</span><span class="sxs-lookup"><span data-stu-id="557d3-125">Project Pro for Office 365</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="557d3-126">App-v 5。0</span><span class="sxs-lookup"><span data-stu-id="557d3-126">App-V 5.0</span></span></p></li>
<li><p><span data-ttu-id="557d3-127">App-v 5.0 SP1</span><span class="sxs-lookup"><span data-stu-id="557d3-127">App-V 5.0 SP1</span></span></p></li>
<li><p><span data-ttu-id="557d3-128">App-v 5.0 SP2</span><span class="sxs-lookup"><span data-stu-id="557d3-128">App-V 5.0 SP2</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="557d3-129">Office 部署工具</span><span class="sxs-lookup"><span data-stu-id="557d3-129">Office Deployment Tool</span></span></p></td>
<td align="left"><p><span data-ttu-id="557d3-130">订阅</span><span class="sxs-lookup"><span data-stu-id="557d3-130">Subscription</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="557d3-131">桌面</span><span class="sxs-lookup"><span data-stu-id="557d3-131">Desktop</span></span></p></li>
<li><p><span data-ttu-id="557d3-132">个人 VDI</span><span class="sxs-lookup"><span data-stu-id="557d3-132">Personal VDI</span></span></p></li>
<li><p><span data-ttu-id="557d3-133">汇集了 VDI</span><span class="sxs-lookup"><span data-stu-id="557d3-133">Pooled VDI</span></span></p></li>
<li><p><span data-ttu-id="557d3-134">RDS</span><span class="sxs-lookup"><span data-stu-id="557d3-134">RDS</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="557d3-135">Office 专业增强版2013</span><span class="sxs-lookup"><span data-stu-id="557d3-135">Office Professional Plus 2013</span></span></p>
<p><span data-ttu-id="557d3-136">还支持：</span><span class="sxs-lookup"><span data-stu-id="557d3-136">Also supported:</span></span></p>
<ul>
<li><p><span data-ttu-id="557d3-137">Visio Professional 2013</span><span class="sxs-lookup"><span data-stu-id="557d3-137">Visio Professional 2013</span></span></p></li>
<li><p><span data-ttu-id="557d3-138">Project Professional 2013</span><span class="sxs-lookup"><span data-stu-id="557d3-138">Project Professional 2013</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="557d3-139">App-v 5。0</span><span class="sxs-lookup"><span data-stu-id="557d3-139">App-V 5.0</span></span></p></li>
<li><p><span data-ttu-id="557d3-140">App-v 5.0 SP1</span><span class="sxs-lookup"><span data-stu-id="557d3-140">App-V 5.0 SP1</span></span></p></li>
<li><p><span data-ttu-id="557d3-141">App-v 5.0 SP2</span><span class="sxs-lookup"><span data-stu-id="557d3-141">App-V 5.0 SP2</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="557d3-142">Office 部署工具</span><span class="sxs-lookup"><span data-stu-id="557d3-142">Office Deployment Tool</span></span></p></td>
<td align="left"><p><span data-ttu-id="557d3-143">批量许可</span><span class="sxs-lookup"><span data-stu-id="557d3-143">Volume Licensing</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="557d3-144">桌面</span><span class="sxs-lookup"><span data-stu-id="557d3-144">Desktop</span></span></p></li>
<li><p><span data-ttu-id="557d3-145">个人 VDI</span><span class="sxs-lookup"><span data-stu-id="557d3-145">Personal VDI</span></span></p></li>
<li><p><span data-ttu-id="557d3-146">汇集了 VDI</span><span class="sxs-lookup"><span data-stu-id="557d3-146">Pooled VDI</span></span></p></li>
<li><p><span data-ttu-id="557d3-147">RDS</span><span class="sxs-lookup"><span data-stu-id="557d3-147">RDS</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-plan-coexisting"></a><span data-ttu-id="557d3-148">规划将 App-v 与早期版本的 Office 配合使用</span><span class="sxs-lookup"><span data-stu-id="557d3-148">Planning for using App-V with coexisting versions of Office</span></span>


<span data-ttu-id="557d3-149">你可以使用 "Microsoft Office 共存" 在同一台计算机上并排安装多个版本的 Microsoft Office。</span><span class="sxs-lookup"><span data-stu-id="557d3-149">You can install more than one version of Microsoft Office side by side on the same computer by using “Microsoft Office coexistence.”</span></span> <span data-ttu-id="557d3-150">你可以通过使用基于 Windows Installer （MSi）版本的 Office、即点即用和 App-v 5.0 SP2 的所有主要版本的 office 共存和安装方法来实现 Office 共存。</span><span class="sxs-lookup"><span data-stu-id="557d3-150">You can implement Office coexistence with combinations of all major versions of Office and with installation methods, as applicable, by using the Windows Installer-based (MSi) version of Office, Click-to-Run, and App-V 5.0 SP2.</span></span> <span data-ttu-id="557d3-151">但是，Microsoft 不建议使用 Office 共存。</span><span class="sxs-lookup"><span data-stu-id="557d3-151">However, using Office coexistence is not recommended by Microsoft.</span></span>

<span data-ttu-id="557d3-152">Microsoft 建议的最佳做法是完全避免 Office 共存，以防止兼容性问题。</span><span class="sxs-lookup"><span data-stu-id="557d3-152">Microsoft’s recommended best practice is to avoid Office coexistence completely to prevent compatibility issues.</span></span> <span data-ttu-id="557d3-153">但是，当你迁移到较新版本的 Office 时，偶尔会出现不能立即解决的问题，因此你可以临时实现共存，以便更快地迁移到最新的产品版本。</span><span class="sxs-lookup"><span data-stu-id="557d3-153">However, when you are migrating to a newer version of Office, issues occasionally arise that can’t be resolved immediately, so you can temporarily implement coexistence to help facilitate a faster migration to the latest product version.</span></span> <span data-ttu-id="557d3-154">永远不建议在短期内使用 Office 共存，并且你的组织应制定一个计划，以便在将来立即完全过渡。</span><span class="sxs-lookup"><span data-stu-id="557d3-154">Using Office coexistence on a long-term basis is never recommended, and your organization should have a plan to fully transition in the immediate future.</span></span>

### <span data-ttu-id="557d3-155">实现 Office 共存之前</span><span class="sxs-lookup"><span data-stu-id="557d3-155">Before you implement Office coexistence</span></span>

<span data-ttu-id="557d3-156">在实现 Office 共存之前，请查看以下 Office 文档。</span><span class="sxs-lookup"><span data-stu-id="557d3-156">Before implementing Office coexistence, review the following Office documentation.</span></span> <span data-ttu-id="557d3-157">选择对应于你计划为其实施共存的最新版本的 Office 的文章。</span><span class="sxs-lookup"><span data-stu-id="557d3-157">Choose the article that corresponds to the newest version of Office for which you plan to implement coexistence.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="557d3-158">Office 版本</span><span class="sxs-lookup"><span data-stu-id="557d3-158">Office version</span></span></th>
<th align="left"><span data-ttu-id="557d3-159">链接到指南</span><span class="sxs-lookup"><span data-stu-id="557d3-159">Link to guidance</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="557d3-160">Office 2013</span><span class="sxs-lookup"><span data-stu-id="557d3-160">Office 2013</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2784668" data-raw-source="[Information about how to use Office 2013 suites and programs (MSI deployment) on a computer that is running another version of Office](https://support.microsoft.com/kb/2784668)"><span data-ttu-id="557d3-161">有关如何在运行其他版本的 Office 的计算机上使用 Office 2013 套件和程序（MSI 部署）的信息</span><span class="sxs-lookup"><span data-stu-id="557d3-161">Information about how to use Office 2013 suites and programs (MSI deployment) on a computer that is running another version of Office</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="557d3-162">Office 2010</span><span class="sxs-lookup"><span data-stu-id="557d3-162">Office 2010</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2121447" data-raw-source="[Information about how to use Office 2010 suites and programs on a computer that is running another version of Office](https://support.microsoft.com/kb/2121447)"><span data-ttu-id="557d3-163">有关如何在运行其他版本的 Office 的计算机上使用 Office 2010 套件和程序的信息</span><span class="sxs-lookup"><span data-stu-id="557d3-163">Information about how to use Office 2010 suites and programs on a computer that is running another version of Office</span></span></a></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="557d3-164">Office 文档提供了有关基于 Windows Installer （MSi）的共存和 Office 的即点即用安装的详细指南。</span><span class="sxs-lookup"><span data-stu-id="557d3-164">The Office documentation provides extensive guidance on coexistence for Windows Installer-based (MSi) and Click-to-Run installations of Office.</span></span> <span data-ttu-id="557d3-165">有关共存的此 App-v 主题补充了 Office 指南，其信息更特定于 App-v 部署。</span><span class="sxs-lookup"><span data-stu-id="557d3-165">This App-V topic on coexistence supplements the Office guidance with information that is more specific to App-V deployments.</span></span>

### <span data-ttu-id="557d3-166">受支持的 Office 共存方案</span><span class="sxs-lookup"><span data-stu-id="557d3-166">Supported Office coexistence scenarios</span></span>

<span data-ttu-id="557d3-167">下表总结了受支持的共存方案。</span><span class="sxs-lookup"><span data-stu-id="557d3-167">The following tables summarize the supported coexistence scenarios.</span></span> <span data-ttu-id="557d3-168">根据你开始的版本和部署方法以及你要迁移到的版本和部署方法对它们进行组织。</span><span class="sxs-lookup"><span data-stu-id="557d3-168">They are organized according to the version and deployment method you’re starting with and the version and deployment method you are migrating to.</span></span> <span data-ttu-id="557d3-169">请确保在将所有共存解决方案部署到生产用户之前对其进行全面测试。</span><span class="sxs-lookup"><span data-stu-id="557d3-169">Be sure to fully test all coexistence solutions before deploying them to a production audience.</span></span>

<span data-ttu-id="557d3-170">**注意** Microsoft 不支持在启用远程桌面会话主机角色服务的 Windows Server 环境中使用多个版本的 Office。</span><span class="sxs-lookup"><span data-stu-id="557d3-170">**Note** Microsoft does not support the use of multiple versions of Office in Windows Server environments that have the Remote Desktop Session Host role service enabled.</span></span> <span data-ttu-id="557d3-171">若要运行 Office 共存方案，必须禁用此角色服务。</span><span class="sxs-lookup"><span data-stu-id="557d3-171">To run Office coexistence scenarios, you must disable this role service.</span></span>

 

### <span data-ttu-id="557d3-172">Windows 集成 & 的 Office 共存</span><span class="sxs-lookup"><span data-stu-id="557d3-172">Windows integrations & Office coexistence</span></span>

<span data-ttu-id="557d3-173">基于 Windows 安装程序和单击到运行的 Office 安装方法与基础 Windows 操作系统的某些点集成。</span><span class="sxs-lookup"><span data-stu-id="557d3-173">The Windows Installer-based and Click-to-Run Office installation methods integrate with certain points of the underlying Windows operating system.</span></span> <span data-ttu-id="557d3-174">使用共存时，两个 Office 版本之间的常见操作系统集成可能会发生冲突，从而导致兼容性和用户体验问题。</span><span class="sxs-lookup"><span data-stu-id="557d3-174">When you use coexistence, common operating system integrations between two Office versions can conflict, causing compatibility and user experience issues.</span></span> <span data-ttu-id="557d3-175">通过 App-v，你可以对某些版本的 Office 进行排序以排除集成，从而将其与操作系统隔离。</span><span class="sxs-lookup"><span data-stu-id="557d3-175">With App-V, you can sequence certain versions of Office to exclude integrations, thereby “isolating” them from the operating system.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left"><span data-ttu-id="557d3-176">在此模式下，app-v 可以对此版本的 Office 进行排序</span><span class="sxs-lookup"><span data-stu-id="557d3-176">Mode in which App-V can sequence this version of Office</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="557d3-177">Office 2007</span><span class="sxs-lookup"><span data-stu-id="557d3-177">Office 2007</span></span></p></td>
<td align="left"><p><span data-ttu-id="557d3-178">始终不集成。</span><span class="sxs-lookup"><span data-stu-id="557d3-178">Always non-integrated.</span></span> <span data-ttu-id="557d3-179">App-v 不会提供与虚拟化版本的 Office 2007 的任何操作系统集成。</span><span class="sxs-lookup"><span data-stu-id="557d3-179">App-V does not offer any operating system integrations with a virtualized version of Office 2007.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="557d3-180">Office 2010</span><span class="sxs-lookup"><span data-stu-id="557d3-180">Office 2010</span></span></p></td>
<td align="left"><p><span data-ttu-id="557d3-181">集成模式和非集成模式。</span><span class="sxs-lookup"><span data-stu-id="557d3-181">Integrated and non-integrated mode.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="557d3-182">Office 2013</span><span class="sxs-lookup"><span data-stu-id="557d3-182">Office 2013</span></span></p></td>
<td align="left"><p><span data-ttu-id="557d3-183">始终集成。</span><span class="sxs-lookup"><span data-stu-id="557d3-183">Always integrated.</span></span> <span data-ttu-id="557d3-184">无法禁用 Windows 操作系统集成。</span><span class="sxs-lookup"><span data-stu-id="557d3-184">Windows operating system integrations cannot be disabled.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="557d3-185">Microsoft 建议你仅通过一个集成的 Office 实例部署 Office 共存。</span><span class="sxs-lookup"><span data-stu-id="557d3-185">Microsoft recommends that you deploy Office coexistence with only one integrated Office instance.</span></span> <span data-ttu-id="557d3-186">例如，如果你使用 App-v 部署 Office 2010 和 Office 2013，则应在非集成模式下序列化 Office 2010。</span><span class="sxs-lookup"><span data-stu-id="557d3-186">For example, if you’re using App-V to deploy Office 2010 and Office 2013, you should sequence Office 2010 in non-integrated mode.</span></span> <span data-ttu-id="557d3-187">有关在非集成（独立）模式下排列 Office 的详细信息，请参阅[如何在 Microsoft Application Virtualization 5.0 中对 Microsoft Office 2010](https://support.microsoft.com/kb/2830069)进行排序。</span><span class="sxs-lookup"><span data-stu-id="557d3-187">For more information about sequencing Office in non-integration (isolated) mode, see [How to sequence Microsoft Office 2010 in Microsoft Application Virtualization 5.0](https://support.microsoft.com/kb/2830069).</span></span>

### <span data-ttu-id="557d3-188">Office 共存方案的已知限制</span><span class="sxs-lookup"><span data-stu-id="557d3-188">Known limitations of Office coexistence scenarios</span></span>

<span data-ttu-id="557d3-189">以下部分介绍了使用 App-v 实现与 Office 的共存时可能遇到的一些问题。</span><span class="sxs-lookup"><span data-stu-id="557d3-189">The following sections describe some issues that you might encounter when using App-V to implement coexistence with Office.</span></span>

### <span data-ttu-id="557d3-190">基于 Windows Installer/单击到运行和 App-v Office 共存方案的常见限制</span><span class="sxs-lookup"><span data-stu-id="557d3-190">Limitations common to Windows Installer-based/Click-to-Run and App-V Office coexistence scenarios</span></span>

<span data-ttu-id="557d3-191">在同一台计算机上安装以下版本的 Office 时，可能会出现以下限制：</span><span class="sxs-lookup"><span data-stu-id="557d3-191">The following limitations can occur when you install the following versions of Office on the same computer:</span></span>

-   <span data-ttu-id="557d3-192">使用基于 Windows Installer 的版本的 Office 2010</span><span class="sxs-lookup"><span data-stu-id="557d3-192">Office 2010 by using the Windows Installer-based version</span></span>

-   <span data-ttu-id="557d3-193">使用 App-v 的 Office 2013</span><span class="sxs-lookup"><span data-stu-id="557d3-193">Office 2013 by using App-V</span></span>

<span data-ttu-id="557d3-194">通过将 app-v 与基于 Windows Installer 的 Office 2010 的早期版本结合使用来发布 Office 2013 后，可能还会导致 Windows 安装程序启动。</span><span class="sxs-lookup"><span data-stu-id="557d3-194">After you publish Office 2013 by using App-V side by side with an earlier version of the Windows Installer-based Office 2010 might also cause the Windows Installer to start.</span></span> <span data-ttu-id="557d3-195">这是因为基于 Windows 安装程序或单击到运行版本的 Office 2010 试图自动注册到计算机。</span><span class="sxs-lookup"><span data-stu-id="557d3-195">This is because the Windows Installer-based or Click-to-Run version of Office 2010 is trying to automatically register itself to the computer.</span></span>

<span data-ttu-id="557d3-196">若要绕过本机 Word 2010 的自动注册操作，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="557d3-196">To bypass the auto-registration operation for native Word 2010, follow these steps:</span></span>

1.  <span data-ttu-id="557d3-197">退出 Word 2010。</span><span class="sxs-lookup"><span data-stu-id="557d3-197">Exit Word 2010.</span></span>

2.  <span data-ttu-id="557d3-198">通过执行下列操作来启动注册表编辑器：</span><span class="sxs-lookup"><span data-stu-id="557d3-198">Start the Registry Editor by doing the following:</span></span>

    -   <span data-ttu-id="557d3-199">在 Windows 7 中：单击 "**开始**"，在 "开始搜索" 框中键入**regedit** ，然后按 enter。</span><span class="sxs-lookup"><span data-stu-id="557d3-199">In Windows 7: Click **Start**, type **regedit** in the Start Search box, and then press Enter.</span></span>

    -   <span data-ttu-id="557d3-200">在 Windows 8 中，键入**regedit**按 "开始" 页面上的 enter，然后按 enter。</span><span class="sxs-lookup"><span data-stu-id="557d3-200">In Windows 8, type **regedit** press Enter on the Start page and then press Enter.</span></span>

    <span data-ttu-id="557d3-201">如果系统提示您输入管理员密码或进行确认，请键入密码，或单击 "**继续**"。</span><span class="sxs-lookup"><span data-stu-id="557d3-201">If you are prompted for an administrator password or for a confirmation, type the password, or click **Continue**.</span></span>

3.  <span data-ttu-id="557d3-202">找到并选择下面的注册表子项：</span><span class="sxs-lookup"><span data-stu-id="557d3-202">Locate and then select the following registry subkey:</span></span>

    ``` syntax
    HKEY_CURRENT_USER\Software\Microsoft\Office\14.0\Word\Options
    ```

4.  <span data-ttu-id="557d3-203">在 "**编辑**" 菜单上，单击 "**新建**"，然后单击 " **DWORD 值**"。</span><span class="sxs-lookup"><span data-stu-id="557d3-203">On the **Edit** menu, click **New**, and then click **DWORD Value**.</span></span>

5.  <span data-ttu-id="557d3-204">键入**NoReReg**，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="557d3-204">Type **NoReReg**, and then press Enter.</span></span>

6.  <span data-ttu-id="557d3-205">右键单击 " **NoReReg** "，然后单击 "**修改**"。</span><span class="sxs-lookup"><span data-stu-id="557d3-205">Right-click **NoReReg** and then click **Modify**.</span></span>

7.  <span data-ttu-id="557d3-206">在 " **Valuedata** " 框中，键入**1**，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="557d3-206">In the **Valuedata** box, type **1**, and then click **OK**.</span></span>

8.  <span data-ttu-id="557d3-207">在 "文件" 菜单上，单击 "**退出**" 以关闭注册表编辑器。</span><span class="sxs-lookup"><span data-stu-id="557d3-207">On the File menu, click **Exit** to close Registry Editor.</span></span>

## <a href="" id="bkmk-office-integration-win"></a><span data-ttu-id="557d3-208">使用 App-v 部署 Office 时 Office 与 Windows 的集成方式</span><span class="sxs-lookup"><span data-stu-id="557d3-208">How Office integrates with Windows when you use App-V to deploy Office</span></span>


<span data-ttu-id="557d3-209">当您使用 App-v 部署 Office 2013 时，Office 将与操作系统完全集成，这将向最终用户提供与 Office 在不使用 App-v 部署时的功能和功能相同的功能和功能。</span><span class="sxs-lookup"><span data-stu-id="557d3-209">When you deploy Office 2013 by using App-V, Office is fully integrated with the operating system, which provides end users with the same features and functionality as Office has when it is deployed without App-V.</span></span>

<span data-ttu-id="557d3-210">Office 2013 App-v 程序包支持 Windows 操作系统的以下集成点：</span><span class="sxs-lookup"><span data-stu-id="557d3-210">The Office 2013 App-V package supports the following integration points with the Windows operating system:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="557d3-211">扩展点</span><span class="sxs-lookup"><span data-stu-id="557d3-211">Extension Point</span></span></th>
<th align="left"><span data-ttu-id="557d3-212">描述</span><span class="sxs-lookup"><span data-stu-id="557d3-212">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="557d3-213">适用于 Firefox 和 Chrome 的 Lync 会议加入插件</span><span class="sxs-lookup"><span data-stu-id="557d3-213">Lync meeting Join Plug-in for Firefox and Chrome</span></span></p></td>
<td align="left"><p><span data-ttu-id="557d3-214">用户可以从 Firefox 和 Chrome 加入 Lync 会议</span><span class="sxs-lookup"><span data-stu-id="557d3-214">User can join Lync meetings from Firefox and Chrome</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="557d3-215">已发送到 OneNote 打印驱动程序</span><span class="sxs-lookup"><span data-stu-id="557d3-215">Sent to OneNote Print Driver</span></span></p></td>
<td align="left"><p><span data-ttu-id="557d3-216">用户可以打印到 OneNote</span><span class="sxs-lookup"><span data-stu-id="557d3-216">User can print to OneNote</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="557d3-217">OneNote 链接笔记</span><span class="sxs-lookup"><span data-stu-id="557d3-217">OneNote Linked Notes</span></span></p></td>
<td align="left"><p><span data-ttu-id="557d3-218">OneNote 链接笔记</span><span class="sxs-lookup"><span data-stu-id="557d3-218">OneNote Linked Notes</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="557d3-219">发送到 OneNote Internet Explorer 加载项</span><span class="sxs-lookup"><span data-stu-id="557d3-219">Send to OneNote Internet Explorer Add-In</span></span></p></td>
<td align="left"><p><span data-ttu-id="557d3-220">用户可以从 IE 发送到 OneNote</span><span class="sxs-lookup"><span data-stu-id="557d3-220">User can send to OneNote from IE</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="557d3-221">Lync 和 Outlook 的防火墙例外</span><span class="sxs-lookup"><span data-stu-id="557d3-221">Firewall Exception for Lync and Outlook</span></span></p></td>
<td align="left"><p><span data-ttu-id="557d3-222">Lync 和 Outlook 的防火墙例外</span><span class="sxs-lookup"><span data-stu-id="557d3-222">Firewall Exception for Lync and Outlook</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="557d3-223">MAPI 客户端</span><span class="sxs-lookup"><span data-stu-id="557d3-223">MAPI Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="557d3-224">本机应用和外接程序可以通过 MAPI 与虚拟 Outlook 进行交互</span><span class="sxs-lookup"><span data-stu-id="557d3-224">Native apps and add-ins can interact with virtual Outlook through MAPI</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="557d3-225">用于 Firefox 的 SharePoint 插件</span><span class="sxs-lookup"><span data-stu-id="557d3-225">SharePoint Plug-in for Firefox</span></span></p></td>
<td align="left"><p><span data-ttu-id="557d3-226">用户可以使用 Firefox 中的 SharePoint 功能</span><span class="sxs-lookup"><span data-stu-id="557d3-226">User can use SharePoint features in Firefox</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="557d3-227">"邮件控制面板" 小程序</span><span class="sxs-lookup"><span data-stu-id="557d3-227">Mail Control Panel Applet</span></span></p></td>
<td align="left"><p><span data-ttu-id="557d3-228">用户在 Outlook 中获取 "邮件" 控制面板小程序</span><span class="sxs-lookup"><span data-stu-id="557d3-228">User gets the mail control panel applet in Outlook</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="557d3-229">主互操作程序集</span><span class="sxs-lookup"><span data-stu-id="557d3-229">Primary Interop Assemblies</span></span></p></td>
<td align="left"><p><span data-ttu-id="557d3-230">支持托管加载项</span><span class="sxs-lookup"><span data-stu-id="557d3-230">Support managed add-ins</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="557d3-231">Office 文档缓存处理程序</span><span class="sxs-lookup"><span data-stu-id="557d3-231">Office Document Cache Handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="557d3-232">允许 Office 应用程序的文档缓存</span><span class="sxs-lookup"><span data-stu-id="557d3-232">Allows Document Cache for Office applications</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="557d3-233">Outlook 协议搜索处理程序</span><span class="sxs-lookup"><span data-stu-id="557d3-233">Outlook Protocol Search handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="557d3-234">用户可以在 outlook 中搜索</span><span class="sxs-lookup"><span data-stu-id="557d3-234">User can search in outlook</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="557d3-235">活动 X 控件：</span><span class="sxs-lookup"><span data-stu-id="557d3-235">Active X Controls:</span></span></p></td>
<td align="left"><p><span data-ttu-id="557d3-236">有关 ActiveX 控件的详细信息，请参阅 <a href="https://go.microsoft.com/fwlink/p/?LinkId=331361" data-raw-source="[ActiveX Control API Reference](https://go.microsoft.com/fwlink/p/?LinkId=331361)"> Activex 控件 API 参考 </a> 。</span><span class="sxs-lookup"><span data-stu-id="557d3-236">For more information on ActiveX controls, refer to <a href="https://go.microsoft.com/fwlink/p/?LinkId=331361" data-raw-source="[ActiveX Control API Reference](https://go.microsoft.com/fwlink/p/?LinkId=331361)">ActiveX Control API Reference</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="557d3-237">Groove。 SiteClient</span><span class="sxs-lookup"><span data-stu-id="557d3-237">Groove.SiteClient</span></span></p></td>
<td align="left"><p><span data-ttu-id="557d3-238">活动 X 控件</span><span class="sxs-lookup"><span data-stu-id="557d3-238">Active X Control</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="557d3-239">PortalConnect.PersonalSite</span><span class="sxs-lookup"><span data-stu-id="557d3-239">PortalConnect.PersonalSite</span></span></p></td>
<td align="left"><p><span data-ttu-id="557d3-240">活动 X 控件</span><span class="sxs-lookup"><span data-stu-id="557d3-240">Active X Control</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="557d3-241">OpenDocuments</span><span class="sxs-lookup"><span data-stu-id="557d3-241">SharePoint.openDocuments</span></span></p></td>
<td align="left"><p><span data-ttu-id="557d3-242">活动 X 控件</span><span class="sxs-lookup"><span data-stu-id="557d3-242">Active X Control</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="557d3-243">ExportDatabase</span><span class="sxs-lookup"><span data-stu-id="557d3-243">SharePoint.ExportDatabase</span></span></p></td>
<td align="left"><p><span data-ttu-id="557d3-244">活动 X 控件</span><span class="sxs-lookup"><span data-stu-id="557d3-244">Active X Control</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="557d3-245">SpreadSheetLauncher</span><span class="sxs-lookup"><span data-stu-id="557d3-245">SharePoint.SpreadSheetLauncher</span></span></p></td>
<td align="left"><p><span data-ttu-id="557d3-246">活动 X 控件</span><span class="sxs-lookup"><span data-stu-id="557d3-246">Active X Control</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="557d3-247">StssyncHander</span><span class="sxs-lookup"><span data-stu-id="557d3-247">SharePoint.StssyncHander</span></span></p></td>
<td align="left"><p><span data-ttu-id="557d3-248">活动 X 控件</span><span class="sxs-lookup"><span data-stu-id="557d3-248">Active X Control</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="557d3-249">DragUploadCtl</span><span class="sxs-lookup"><span data-stu-id="557d3-249">SharePoint.DragUploadCtl</span></span></p></td>
<td align="left"><p><span data-ttu-id="557d3-250">活动 X 控件</span><span class="sxs-lookup"><span data-stu-id="557d3-250">Active X Control</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="557d3-251">DragDownloadCtl</span><span class="sxs-lookup"><span data-stu-id="557d3-251">SharePoint.DragDownloadCtl</span></span></p></td>
<td align="left"><p><span data-ttu-id="557d3-252">活动 X 控件</span><span class="sxs-lookup"><span data-stu-id="557d3-252">Active X Control</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="557d3-253">OpenXMLDocuments</span><span class="sxs-lookup"><span data-stu-id="557d3-253">Sharepoint.OpenXMLDocuments</span></span></p></td>
<td align="left"><p><span data-ttu-id="557d3-254">活动 X 控件</span><span class="sxs-lookup"><span data-stu-id="557d3-254">Active X Control</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="557d3-255">ClipboardCtl</span><span class="sxs-lookup"><span data-stu-id="557d3-255">Sharepoint.ClipboardCtl</span></span></p></td>
<td align="left"><p><span data-ttu-id="557d3-256">活动 X 控件</span><span class="sxs-lookup"><span data-stu-id="557d3-256">Active X control</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="557d3-257">WinProj</span><span class="sxs-lookup"><span data-stu-id="557d3-257">WinProj.Activator</span></span></p></td>
<td align="left"><p><span data-ttu-id="557d3-258">活动 X 控件</span><span class="sxs-lookup"><span data-stu-id="557d3-258">Active X Control</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="557d3-259">NameCtrl</span><span class="sxs-lookup"><span data-stu-id="557d3-259">Name.NameCtrl</span></span></p></td>
<td align="left"><p><span data-ttu-id="557d3-260">活动 X 控件</span><span class="sxs-lookup"><span data-stu-id="557d3-260">Active X Control</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="557d3-261">STSUPld.CopyCtl</span><span class="sxs-lookup"><span data-stu-id="557d3-261">STSUPld.CopyCtl</span></span></p></td>
<td align="left"><p><span data-ttu-id="557d3-262">活动 X 控件</span><span class="sxs-lookup"><span data-stu-id="557d3-262">Active X Control</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="557d3-263">CommunicatorMeetingJoinAx.JoinManager</span><span class="sxs-lookup"><span data-stu-id="557d3-263">CommunicatorMeetingJoinAx.JoinManager</span></span></p></td>
<td align="left"><p><span data-ttu-id="557d3-264">活动 X 控件</span><span class="sxs-lookup"><span data-stu-id="557d3-264">Active X Control</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="557d3-265">LISTNET.Listnet</span><span class="sxs-lookup"><span data-stu-id="557d3-265">LISTNET.Listnet</span></span></p></td>
<td align="left"><p><span data-ttu-id="557d3-266">活动 X 控件</span><span class="sxs-lookup"><span data-stu-id="557d3-266">Active X Control</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="557d3-267">OneDrive Pro 浏览器帮助程序</span><span class="sxs-lookup"><span data-stu-id="557d3-267">OneDrive Pro Browser Helper</span></span></p></td>
<td align="left"><p><span data-ttu-id="557d3-268">活动 X 控件]</span><span class="sxs-lookup"><span data-stu-id="557d3-268">Active X Control]</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="557d3-269">OneDrive Pro 图标覆盖</span><span class="sxs-lookup"><span data-stu-id="557d3-269">OneDrive Pro Icon Overlays</span></span></p></td>
<td align="left"><p><span data-ttu-id="557d3-270">当用户查看文件夹 OneDrive Pro 文件夹时，Windows 资源管理器 shell 图标重叠</span><span class="sxs-lookup"><span data-stu-id="557d3-270">Windows Explorer shell icon overlays when users look at folders OneDrive Pro folders</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="557d3-271">Shell 扩展</span><span class="sxs-lookup"><span data-stu-id="557d3-271">Shell extensions</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="557d3-272">指向</span><span class="sxs-lookup"><span data-stu-id="557d3-272">Shortcuts</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="557d3-273">Windows 搜索</span><span class="sxs-lookup"><span data-stu-id="557d3-273">Windows Search</span></span></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 






 

 





