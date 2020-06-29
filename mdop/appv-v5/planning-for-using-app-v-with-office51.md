---
title: 计划将 App-V 与 Office 结合使用
description: 计划将 App-V 与 Office 结合使用
author: dansimp
ms.assetid: e7a19b43-1746-469f-bad6-8e75cf4b3f67
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 03/16/2017
ms.openlocfilehash: ae225db3c47faca5fba790fb9963bfd4dc2c66b0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798289"
---
# <span data-ttu-id="61584-103">计划将 App-V 与 Office 结合使用</span><span class="sxs-lookup"><span data-stu-id="61584-103">Planning for Using App-V with Office</span></span>


<span data-ttu-id="61584-104">使用以下信息规划如何使用 Microsoft Application Virtualization （App-v）5.1 部署 Office。</span><span class="sxs-lookup"><span data-stu-id="61584-104">Use the following information to plan how to deploy Office by using Microsoft Application Virtualization (App-V) 5.1.</span></span> <span data-ttu-id="61584-105">本文包括：</span><span class="sxs-lookup"><span data-stu-id="61584-105">This article includes:</span></span>

-   [<span data-ttu-id="61584-106">语言包的 app-v 支持</span><span class="sxs-lookup"><span data-stu-id="61584-106">App-V support for Language Packs</span></span>](#bkmk-lang-pack)

-   [<span data-ttu-id="61584-107">Microsoft Office 支持的版本</span><span class="sxs-lookup"><span data-stu-id="61584-107">Supported versions of Microsoft Office</span></span>](#bkmk-office-vers-supp-appv)

-   [<span data-ttu-id="61584-108">规划将 App-v 与早期版本的 Office 配合使用</span><span class="sxs-lookup"><span data-stu-id="61584-108">Planning for using App-V with coexisting versions of Office</span></span>](#bkmk-plan-coexisting)

-   [<span data-ttu-id="61584-109">Office 在部署时如何与 Windows 集成使用 app-v 部署 Office</span><span class="sxs-lookup"><span data-stu-id="61584-109">How Office integrates with Windows when you deploy use App-V to deploy Office</span></span>](#bkmk-office-integration-win)

## <a href="" id="bkmk-lang-pack"></a><span data-ttu-id="61584-110">语言包的 app-v 支持</span><span class="sxs-lookup"><span data-stu-id="61584-110">App-V support for Language Packs</span></span>


<span data-ttu-id="61584-111">你可以使用 app-v 5.1 Sequencer 为语言包、语言界面包、校对工具和屏幕提示语言创建插件包。</span><span class="sxs-lookup"><span data-stu-id="61584-111">You can use the App-V 5.1 Sequencer to create plug-in packages for Language Packs, Language Interface Packs, Proofing Tools and ScreenTip Languages.</span></span> <span data-ttu-id="61584-112">然后，你可以在连接组中包含插件程序包，以及使用 Office 部署工具包创建的 Office 2013 程序包。</span><span class="sxs-lookup"><span data-stu-id="61584-112">You can then include the plug-in packages in a Connection Group, along with the Office 2013 package that you create by using the Office Deployment Toolkit.</span></span> <span data-ttu-id="61584-113">Office 应用程序和插件语言包在同一连接组中无缝交互，就像在连接组中组合在一起的任何其他程序包一样。</span><span class="sxs-lookup"><span data-stu-id="61584-113">The Office applications and the plug-in Language Packs interact seamlessly in the same connection group, just like any other packages that are grouped together in a connection group.</span></span>

><span data-ttu-id="61584-114">**注意** Microsoft Visio 和 Microsoft Project 不提供对泰语语言包的支持。</span><span class="sxs-lookup"><span data-stu-id="61584-114">**Note** Microsoft Visio and Microsoft Project do not provide support for the Thai Language Pack.</span></span>

 

## <a href="" id="bkmk-office-vers-supp-appv"></a><span data-ttu-id="61584-115">Microsoft Office 支持的版本</span><span class="sxs-lookup"><span data-stu-id="61584-115">Supported versions of Microsoft Office</span></span>

<span data-ttu-id="61584-116">有关支持的 Office 产品列表，请参阅[应用程序 V 支持的 Microsoft Office 产品 id](https://support.microsoft.com/help/2842297/product-ids-that-are-supported-by-the-office-deployment-tool-for-click) 。</span><span class="sxs-lookup"><span data-stu-id="61584-116">See [Microsoft Office Product IDs that App-V supports](https://support.microsoft.com/help/2842297/product-ids-that-are-supported-by-the-office-deployment-tool-for-click) for a list of supported Office products.</span></span>
><span data-ttu-id="61584-117">**Note** &nbsp; 注意 &nbsp;你必须使用 Office 部署工具为适用于企业的 Microsoft 365 应用创建 app-v 程序包。</span><span class="sxs-lookup"><span data-stu-id="61584-117">**Note**&nbsp;&nbsp;You must use the Office Deployment Tool to create App-V packages for Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="61584-118">不支持创建批量许可版本的 Office 专业增强版或 Office Standard 的程序包。</span><span class="sxs-lookup"><span data-stu-id="61584-118">Creating packages for the volume-licensed versions of Office Professional Plus or Office Standard is not supported.</span></span> <span data-ttu-id="61584-119">不能使用 App-v 排序器。</span><span class="sxs-lookup"><span data-stu-id="61584-119">You cannot use the App-V Sequencer.</span></span>

 

## <a href="" id="bkmk-plan-coexisting"></a><span data-ttu-id="61584-120">规划将 App-v 与早期版本的 Office 配合使用</span><span class="sxs-lookup"><span data-stu-id="61584-120">Planning for using App-V with coexisting versions of Office</span></span>


<span data-ttu-id="61584-121">你可以使用 "Microsoft Office 共存" 在同一台计算机上并排安装多个版本的 Microsoft Office。</span><span class="sxs-lookup"><span data-stu-id="61584-121">You can install more than one version of Microsoft Office side by side on the same computer by using “Microsoft Office coexistence.”</span></span> <span data-ttu-id="61584-122">你可以通过使用基于 Windows Installer （MSi）的 Office、即点即用和 App-v 5.1 的各种主要版本的所有主要版本和安装方法来实现 Office 共存。</span><span class="sxs-lookup"><span data-stu-id="61584-122">You can implement Office coexistence with combinations of all major versions of Office and with installation methods, as applicable, by using the Windows Installer-based (MSi) version of Office, Click-to-Run, and App-V 5.1.</span></span> <span data-ttu-id="61584-123">但是，Microsoft 不建议使用 Office 共存。</span><span class="sxs-lookup"><span data-stu-id="61584-123">However, using Office coexistence is not recommended by Microsoft.</span></span>

<span data-ttu-id="61584-124">Microsoft 建议的最佳做法是完全避免 Office 共存，以防止兼容性问题。</span><span class="sxs-lookup"><span data-stu-id="61584-124">Microsoft’s recommended best practice is to avoid Office coexistence completely to prevent compatibility issues.</span></span> <span data-ttu-id="61584-125">但是，当你迁移到较新版本的 Office 时，偶尔会出现不能立即解决的问题，因此你可以临时实现共存，以便更快地迁移到最新的产品版本。</span><span class="sxs-lookup"><span data-stu-id="61584-125">However, when you are migrating to a newer version of Office, issues occasionally arise that can’t be resolved immediately, so you can temporarily implement coexistence to help facilitate a faster migration to the latest product version.</span></span> <span data-ttu-id="61584-126">永远不建议在短期内使用 Office 共存，并且你的组织应制定一个计划，以便在将来立即完全过渡。</span><span class="sxs-lookup"><span data-stu-id="61584-126">Using Office coexistence on a long-term basis is never recommended, and your organization should have a plan to fully transition in the immediate future.</span></span>

### <span data-ttu-id="61584-127">实现 Office 共存之前</span><span class="sxs-lookup"><span data-stu-id="61584-127">Before you implement Office coexistence</span></span>

<span data-ttu-id="61584-128">在实现 Office 共存之前，请查看以下 Office 文档。</span><span class="sxs-lookup"><span data-stu-id="61584-128">Before implementing Office coexistence, review the following Office documentation.</span></span> <span data-ttu-id="61584-129">选择对应于你计划为其实施共存的最新版本的 Office 的文章。</span><span class="sxs-lookup"><span data-stu-id="61584-129">Choose the article that corresponds to the newest version of Office for which you plan to implement coexistence.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="61584-130">Office 版本</span><span class="sxs-lookup"><span data-stu-id="61584-130">Office version</span></span></th>
<th align="left"><span data-ttu-id="61584-131">链接到指南</span><span class="sxs-lookup"><span data-stu-id="61584-131">Link to guidance</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="61584-132">Office 2013</span><span class="sxs-lookup"><span data-stu-id="61584-132">Office 2013</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2784668" data-raw-source="[Information about how to use Office 2013 suites and programs (MSI deployment) on a computer that is running another version of Office](https://support.microsoft.com/kb/2784668)"><span data-ttu-id="61584-133">有关如何在运行其他版本的 Office 的计算机上使用 Office 2013 套件和程序（MSI 部署）的信息</span><span class="sxs-lookup"><span data-stu-id="61584-133">Information about how to use Office 2013 suites and programs (MSI deployment) on a computer that is running another version of Office</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="61584-134">Office 2010</span><span class="sxs-lookup"><span data-stu-id="61584-134">Office 2010</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2121447" data-raw-source="[Information about how to use Office 2010 suites and programs on a computer that is running another version of Office](https://support.microsoft.com/kb/2121447)"><span data-ttu-id="61584-135">有关如何在运行其他版本的 Office 的计算机上使用 Office 2010 套件和程序的信息</span><span class="sxs-lookup"><span data-stu-id="61584-135">Information about how to use Office 2010 suites and programs on a computer that is running another version of Office</span></span></a></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="61584-136">Office 文档提供了有关基于 Windows Installer （MSi）的共存和 Office 的即点即用安装的详细指南。</span><span class="sxs-lookup"><span data-stu-id="61584-136">The Office documentation provides extensive guidance on coexistence for Windows Installer-based (MSi) and Click-to-Run installations of Office.</span></span> <span data-ttu-id="61584-137">有关共存的此 App-v 主题补充了 Office 指南，其信息更特定于 App-v 部署。</span><span class="sxs-lookup"><span data-stu-id="61584-137">This App-V topic on coexistence supplements the Office guidance with information that is more specific to App-V deployments.</span></span>

### <span data-ttu-id="61584-138">受支持的 Office 共存方案</span><span class="sxs-lookup"><span data-stu-id="61584-138">Supported Office coexistence scenarios</span></span>

<span data-ttu-id="61584-139">下表总结了受支持的共存方案。</span><span class="sxs-lookup"><span data-stu-id="61584-139">The following tables summarize the supported coexistence scenarios.</span></span> <span data-ttu-id="61584-140">根据你开始的版本和部署方法以及你要迁移到的版本和部署方法对它们进行组织。</span><span class="sxs-lookup"><span data-stu-id="61584-140">They are organized according to the version and deployment method you’re starting with and the version and deployment method you are migrating to.</span></span> <span data-ttu-id="61584-141">请确保在将所有共存解决方案部署到生产用户之前对其进行全面测试。</span><span class="sxs-lookup"><span data-stu-id="61584-141">Be sure to fully test all coexistence solutions before deploying them to a production audience.</span></span>

><span data-ttu-id="61584-142">**注意** Microsoft 不支持在启用远程桌面会话主机角色服务的 Windows Server 环境中使用多个版本的 Office。</span><span class="sxs-lookup"><span data-stu-id="61584-142">**Note** Microsoft does not support the use of multiple versions of Office in Windows Server environments that have the Remote Desktop Session Host role service enabled.</span></span> <span data-ttu-id="61584-143">若要运行 Office 共存方案，必须禁用此角色服务。</span><span class="sxs-lookup"><span data-stu-id="61584-143">To run Office coexistence scenarios, you must disable this role service.</span></span>

 

### <span data-ttu-id="61584-144">Windows 集成 & 的 Office 共存</span><span class="sxs-lookup"><span data-stu-id="61584-144">Windows integrations & Office coexistence</span></span>

<span data-ttu-id="61584-145">基于 Windows 安装程序和单击到运行的 Office 安装方法与基础 Windows 操作系统的某些点集成。</span><span class="sxs-lookup"><span data-stu-id="61584-145">The Windows Installer-based and Click-to-Run Office installation methods integrate with certain points of the underlying Windows operating system.</span></span> <span data-ttu-id="61584-146">使用共存时，两个 Office 版本之间的常见操作系统集成可能会发生冲突，从而导致兼容性和用户体验问题。</span><span class="sxs-lookup"><span data-stu-id="61584-146">When you use coexistence, common operating system integrations between two Office versions can conflict, causing compatibility and user experience issues.</span></span> <span data-ttu-id="61584-147">通过 App-v，你可以对某些版本的 Office 进行排序以排除集成，从而将其与操作系统隔离。</span><span class="sxs-lookup"><span data-stu-id="61584-147">With App-V, you can sequence certain versions of Office to exclude integrations, thereby “isolating” them from the operating system.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left"><span data-ttu-id="61584-148">在此模式下，app-v 可以对此版本的 Office 进行排序</span><span class="sxs-lookup"><span data-stu-id="61584-148">Mode in which App-V can sequence this version of Office</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="61584-149">Office 2007</span><span class="sxs-lookup"><span data-stu-id="61584-149">Office 2007</span></span></p></td>
<td align="left"><p><span data-ttu-id="61584-150">始终不集成。</span><span class="sxs-lookup"><span data-stu-id="61584-150">Always non-integrated.</span></span> <span data-ttu-id="61584-151">App-v 不会提供与虚拟化版本的 Office 2007 的任何操作系统集成。</span><span class="sxs-lookup"><span data-stu-id="61584-151">App-V does not offer any operating system integrations with a virtualized version of Office 2007.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="61584-152">Office 2010</span><span class="sxs-lookup"><span data-stu-id="61584-152">Office 2010</span></span></p></td>
<td align="left"><p><span data-ttu-id="61584-153">集成模式和非集成模式。</span><span class="sxs-lookup"><span data-stu-id="61584-153">Integrated and non-integrated mode.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="61584-154">Office 2013</span><span class="sxs-lookup"><span data-stu-id="61584-154">Office 2013</span></span></p></td>
<td align="left"><p><span data-ttu-id="61584-155">始终集成。</span><span class="sxs-lookup"><span data-stu-id="61584-155">Always integrated.</span></span> <span data-ttu-id="61584-156">无法禁用 Windows 操作系统集成。</span><span class="sxs-lookup"><span data-stu-id="61584-156">Windows operating system integrations cannot be disabled.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="61584-157">Microsoft 建议你仅通过一个集成的 Office 实例部署 Office 共存。</span><span class="sxs-lookup"><span data-stu-id="61584-157">Microsoft recommends that you deploy Office coexistence with only one integrated Office instance.</span></span> <span data-ttu-id="61584-158">例如，如果你使用 App-v 部署 Office 2010 和 Office 2013，则应在非集成模式下序列化 Office 2010。</span><span class="sxs-lookup"><span data-stu-id="61584-158">For example, if you’re using App-V to deploy Office 2010 and Office 2013, you should sequence Office 2010 in non-integrated mode.</span></span> <span data-ttu-id="61584-159">有关在非集成（独立）模式下排列 Office 的详细信息，请参阅[如何在 Microsoft Application Virtualization 5.0 中对 Microsoft Office 2010](https://support.microsoft.com/kb/2830069)进行排序。</span><span class="sxs-lookup"><span data-stu-id="61584-159">For more information about sequencing Office in non-integration (isolated) mode, see [How to sequence Microsoft Office 2010 in Microsoft Application Virtualization 5.0](https://support.microsoft.com/kb/2830069).</span></span>

### <span data-ttu-id="61584-160">Office 共存方案的已知限制</span><span class="sxs-lookup"><span data-stu-id="61584-160">Known limitations of Office coexistence scenarios</span></span>

<span data-ttu-id="61584-161">以下部分介绍了使用 App-v 实现与 Office 的共存时可能遇到的一些问题。</span><span class="sxs-lookup"><span data-stu-id="61584-161">The following sections describe some issues that you might encounter when using App-V to implement coexistence with Office.</span></span>

### <span data-ttu-id="61584-162">基于 Windows Installer/单击到运行和 App-v Office 共存方案的常见限制</span><span class="sxs-lookup"><span data-stu-id="61584-162">Limitations common to Windows Installer-based/Click-to-Run and App-V Office coexistence scenarios</span></span>

<span data-ttu-id="61584-163">在同一台计算机上安装以下版本的 Office 时，可能会出现以下限制：</span><span class="sxs-lookup"><span data-stu-id="61584-163">The following limitations can occur when you install the following versions of Office on the same computer:</span></span>

-   <span data-ttu-id="61584-164">使用基于 Windows Installer 的版本的 Office 2010</span><span class="sxs-lookup"><span data-stu-id="61584-164">Office 2010 by using the Windows Installer-based version</span></span>

-   <span data-ttu-id="61584-165">使用 App-v 的 Office 2013</span><span class="sxs-lookup"><span data-stu-id="61584-165">Office 2013 by using App-V</span></span>

<span data-ttu-id="61584-166">通过将 app-v 与基于 Windows Installer 的 Office 2010 的早期版本结合使用来发布 Office 2013 后，可能还会导致 Windows 安装程序启动。</span><span class="sxs-lookup"><span data-stu-id="61584-166">After you publish Office 2013 by using App-V side by side with an earlier version of the Windows Installer-based Office 2010 might also cause the Windows Installer to start.</span></span> <span data-ttu-id="61584-167">这是因为基于 Windows 安装程序或单击到运行版本的 Office 2010 试图自动注册到计算机。</span><span class="sxs-lookup"><span data-stu-id="61584-167">This is because the Windows Installer-based or Click-to-Run version of Office 2010 is trying to automatically register itself to the computer.</span></span>

<span data-ttu-id="61584-168">若要绕过本机 Word 2010 的自动注册操作，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="61584-168">To bypass the auto-registration operation for native Word 2010, follow these steps:</span></span>

1.  <span data-ttu-id="61584-169">退出 Word 2010。</span><span class="sxs-lookup"><span data-stu-id="61584-169">Exit Word 2010.</span></span>

2.  <span data-ttu-id="61584-170">通过执行下列操作来启动注册表编辑器：</span><span class="sxs-lookup"><span data-stu-id="61584-170">Start the Registry Editor by doing the following:</span></span>

    -   <span data-ttu-id="61584-171">在 Windows 7 中：单击 "**开始**"，在 "开始搜索" 框中键入**regedit** ，然后按 enter。</span><span class="sxs-lookup"><span data-stu-id="61584-171">In Windows 7: Click **Start**, type **regedit** in the Start Search box, and then press Enter.</span></span>

    -   <span data-ttu-id="61584-172">在 Windows 8.1 或 Windows 10 中，键入**regedit**按下 "开始" 页面上的 enter，然后按 enter。</span><span class="sxs-lookup"><span data-stu-id="61584-172">In Windows 8.1 or Windows 10, type **regedit** press Enter on the Start page and then press Enter.</span></span>

    <span data-ttu-id="61584-173">如果系统提示您输入管理员密码或进行确认，请键入密码，或单击 "**继续**"。</span><span class="sxs-lookup"><span data-stu-id="61584-173">If you are prompted for an administrator password or for a confirmation, type the password, or click **Continue**.</span></span>

3.  <span data-ttu-id="61584-174">找到并选择下面的注册表子项：</span><span class="sxs-lookup"><span data-stu-id="61584-174">Locate and then select the following registry subkey:</span></span>

    ``` syntax
    HKEY_CURRENT_USER\Software\Microsoft\Office\14.0\Word\Options
    ```

4.  <span data-ttu-id="61584-175">在 "**编辑**" 菜单上，单击 "**新建**"，然后单击 " **DWORD 值**"。</span><span class="sxs-lookup"><span data-stu-id="61584-175">On the **Edit** menu, click **New**, and then click **DWORD Value**.</span></span>

5.  <span data-ttu-id="61584-176">键入**NoReReg**，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="61584-176">Type **NoReReg**, and then press Enter.</span></span>

6.  <span data-ttu-id="61584-177">右键单击 " **NoReReg** "，然后单击 "**修改**"。</span><span class="sxs-lookup"><span data-stu-id="61584-177">Right-click **NoReReg** and then click **Modify**.</span></span>

7.  <span data-ttu-id="61584-178">在 " **Valuedata** " 框中，键入**1**，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="61584-178">In the **Valuedata** box, type **1**, and then click **OK**.</span></span>

8.  <span data-ttu-id="61584-179">在 "文件" 菜单上，单击 "**退出**" 以关闭注册表编辑器。</span><span class="sxs-lookup"><span data-stu-id="61584-179">On the File menu, click **Exit** to close Registry Editor.</span></span>

## <a href="" id="bkmk-office-integration-win"></a><span data-ttu-id="61584-180">使用 App-v 部署 Office 时 Office 与 Windows 的集成方式</span><span class="sxs-lookup"><span data-stu-id="61584-180">How Office integrates with Windows when you use App-V to deploy Office</span></span>


<span data-ttu-id="61584-181">当您使用 App-v 部署 Office 2013 时，Office 将与操作系统完全集成，这将向最终用户提供与 Office 在不使用 App-v 部署时的功能和功能相同的功能和功能。</span><span class="sxs-lookup"><span data-stu-id="61584-181">When you deploy Office 2013 by using App-V, Office is fully integrated with the operating system, which provides end users with the same features and functionality as Office has when it is deployed without App-V.</span></span>

<span data-ttu-id="61584-182">Office 2013 App-v 程序包支持 Windows 操作系统的以下集成点：</span><span class="sxs-lookup"><span data-stu-id="61584-182">The Office 2013 App-V package supports the following integration points with the Windows operating system:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="61584-183">扩展点</span><span class="sxs-lookup"><span data-stu-id="61584-183">Extension Point</span></span></th>
<th align="left"><span data-ttu-id="61584-184">描述</span><span class="sxs-lookup"><span data-stu-id="61584-184">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="61584-185">适用于 Firefox 和 Chrome 的 Lync 会议加入插件</span><span class="sxs-lookup"><span data-stu-id="61584-185">Lync meeting Join Plug-in for Firefox and Chrome</span></span></p></td>
<td align="left"><p><span data-ttu-id="61584-186">用户可以从 Firefox 和 Chrome 加入 Lync 会议</span><span class="sxs-lookup"><span data-stu-id="61584-186">User can join Lync meetings from Firefox and Chrome</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="61584-187">已发送到 OneNote 打印驱动程序</span><span class="sxs-lookup"><span data-stu-id="61584-187">Sent to OneNote Print Driver</span></span></p></td>
<td align="left"><p><span data-ttu-id="61584-188">用户可以打印到 OneNote</span><span class="sxs-lookup"><span data-stu-id="61584-188">User can print to OneNote</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="61584-189">OneNote 链接笔记</span><span class="sxs-lookup"><span data-stu-id="61584-189">OneNote Linked Notes</span></span></p></td>
<td align="left"><p><span data-ttu-id="61584-190">OneNote 链接笔记</span><span class="sxs-lookup"><span data-stu-id="61584-190">OneNote Linked Notes</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="61584-191">发送到 OneNote Internet Explorer 加载项</span><span class="sxs-lookup"><span data-stu-id="61584-191">Send to OneNote Internet Explorer Add-In</span></span></p></td>
<td align="left"><p><span data-ttu-id="61584-192">用户可以从 IE 发送到 OneNote</span><span class="sxs-lookup"><span data-stu-id="61584-192">User can send to OneNote from IE</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="61584-193">Lync 和 Outlook 的防火墙例外</span><span class="sxs-lookup"><span data-stu-id="61584-193">Firewall Exception for Lync and Outlook</span></span></p></td>
<td align="left"><p><span data-ttu-id="61584-194">Lync 和 Outlook 的防火墙例外</span><span class="sxs-lookup"><span data-stu-id="61584-194">Firewall Exception for Lync and Outlook</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="61584-195">MAPI 客户端</span><span class="sxs-lookup"><span data-stu-id="61584-195">MAPI Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="61584-196">本机应用和外接程序可以通过 MAPI 与虚拟 Outlook 进行交互</span><span class="sxs-lookup"><span data-stu-id="61584-196">Native apps and add-ins can interact with virtual Outlook through MAPI</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="61584-197">用于 Firefox 的 SharePoint 插件</span><span class="sxs-lookup"><span data-stu-id="61584-197">SharePoint Plug-in for Firefox</span></span></p></td>
<td align="left"><p><span data-ttu-id="61584-198">用户可以使用 Firefox 中的 SharePoint 功能</span><span class="sxs-lookup"><span data-stu-id="61584-198">User can use SharePoint features in Firefox</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="61584-199">"邮件控制面板" 小程序</span><span class="sxs-lookup"><span data-stu-id="61584-199">Mail Control Panel Applet</span></span></p></td>
<td align="left"><p><span data-ttu-id="61584-200">用户在 Outlook 中获取 "邮件" 控制面板小程序</span><span class="sxs-lookup"><span data-stu-id="61584-200">User gets the mail control panel applet in Outlook</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="61584-201">主互操作程序集</span><span class="sxs-lookup"><span data-stu-id="61584-201">Primary Interop Assemblies</span></span></p></td>
<td align="left"><p><span data-ttu-id="61584-202">支持托管加载项</span><span class="sxs-lookup"><span data-stu-id="61584-202">Support managed add-ins</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="61584-203">Office 文档缓存处理程序</span><span class="sxs-lookup"><span data-stu-id="61584-203">Office Document Cache Handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="61584-204">允许 Office 应用程序的文档缓存</span><span class="sxs-lookup"><span data-stu-id="61584-204">Allows Document Cache for Office applications</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="61584-205">Outlook 协议搜索处理程序</span><span class="sxs-lookup"><span data-stu-id="61584-205">Outlook Protocol Search handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="61584-206">用户可以在 outlook 中搜索</span><span class="sxs-lookup"><span data-stu-id="61584-206">User can search in outlook</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="61584-207">活动 X 控件：</span><span class="sxs-lookup"><span data-stu-id="61584-207">Active X Controls:</span></span></p></td>
<td align="left"><p><span data-ttu-id="61584-208">有关 ActiveX 控件的详细信息，请参阅 <a href="https://go.microsoft.com/fwlink/p/?LinkId=331361" data-raw-source="[ActiveX Control API Reference](https://go.microsoft.com/fwlink/p/?LinkId=331361)"> Activex 控件 API 参考 </a> 。</span><span class="sxs-lookup"><span data-stu-id="61584-208">For more information on ActiveX controls, refer to <a href="https://go.microsoft.com/fwlink/p/?LinkId=331361" data-raw-source="[ActiveX Control API Reference](https://go.microsoft.com/fwlink/p/?LinkId=331361)">ActiveX Control API Reference</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="61584-209">Groove。 SiteClient</span><span class="sxs-lookup"><span data-stu-id="61584-209">Groove.SiteClient</span></span></p></td>
<td align="left"><p><span data-ttu-id="61584-210">活动 X 控件</span><span class="sxs-lookup"><span data-stu-id="61584-210">Active X Control</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="61584-211">PortalConnect.PersonalSite</span><span class="sxs-lookup"><span data-stu-id="61584-211">PortalConnect.PersonalSite</span></span></p></td>
<td align="left"><p><span data-ttu-id="61584-212">活动 X 控件</span><span class="sxs-lookup"><span data-stu-id="61584-212">Active X Control</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="61584-213">OpenDocuments</span><span class="sxs-lookup"><span data-stu-id="61584-213">SharePoint.openDocuments</span></span></p></td>
<td align="left"><p><span data-ttu-id="61584-214">活动 X 控件</span><span class="sxs-lookup"><span data-stu-id="61584-214">Active X Control</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="61584-215">ExportDatabase</span><span class="sxs-lookup"><span data-stu-id="61584-215">SharePoint.ExportDatabase</span></span></p></td>
<td align="left"><p><span data-ttu-id="61584-216">活动 X 控件</span><span class="sxs-lookup"><span data-stu-id="61584-216">Active X Control</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="61584-217">SpreadSheetLauncher</span><span class="sxs-lookup"><span data-stu-id="61584-217">SharePoint.SpreadSheetLauncher</span></span></p></td>
<td align="left"><p><span data-ttu-id="61584-218">活动 X 控件</span><span class="sxs-lookup"><span data-stu-id="61584-218">Active X Control</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="61584-219">StssyncHander</span><span class="sxs-lookup"><span data-stu-id="61584-219">SharePoint.StssyncHander</span></span></p></td>
<td align="left"><p><span data-ttu-id="61584-220">活动 X 控件</span><span class="sxs-lookup"><span data-stu-id="61584-220">Active X Control</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="61584-221">DragUploadCtl</span><span class="sxs-lookup"><span data-stu-id="61584-221">SharePoint.DragUploadCtl</span></span></p></td>
<td align="left"><p><span data-ttu-id="61584-222">活动 X 控件</span><span class="sxs-lookup"><span data-stu-id="61584-222">Active X Control</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="61584-223">DragDownloadCtl</span><span class="sxs-lookup"><span data-stu-id="61584-223">SharePoint.DragDownloadCtl</span></span></p></td>
<td align="left"><p><span data-ttu-id="61584-224">活动 X 控件</span><span class="sxs-lookup"><span data-stu-id="61584-224">Active X Control</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="61584-225">OpenXMLDocuments</span><span class="sxs-lookup"><span data-stu-id="61584-225">Sharepoint.OpenXMLDocuments</span></span></p></td>
<td align="left"><p><span data-ttu-id="61584-226">活动 X 控件</span><span class="sxs-lookup"><span data-stu-id="61584-226">Active X Control</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="61584-227">ClipboardCtl</span><span class="sxs-lookup"><span data-stu-id="61584-227">Sharepoint.ClipboardCtl</span></span></p></td>
<td align="left"><p><span data-ttu-id="61584-228">活动 X 控件</span><span class="sxs-lookup"><span data-stu-id="61584-228">Active X control</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="61584-229">WinProj</span><span class="sxs-lookup"><span data-stu-id="61584-229">WinProj.Activator</span></span></p></td>
<td align="left"><p><span data-ttu-id="61584-230">活动 X 控件</span><span class="sxs-lookup"><span data-stu-id="61584-230">Active X Control</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="61584-231">NameCtrl</span><span class="sxs-lookup"><span data-stu-id="61584-231">Name.NameCtrl</span></span></p></td>
<td align="left"><p><span data-ttu-id="61584-232">活动 X 控件</span><span class="sxs-lookup"><span data-stu-id="61584-232">Active X Control</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="61584-233">STSUPld.CopyCtl</span><span class="sxs-lookup"><span data-stu-id="61584-233">STSUPld.CopyCtl</span></span></p></td>
<td align="left"><p><span data-ttu-id="61584-234">活动 X 控件</span><span class="sxs-lookup"><span data-stu-id="61584-234">Active X Control</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="61584-235">CommunicatorMeetingJoinAx.JoinManager</span><span class="sxs-lookup"><span data-stu-id="61584-235">CommunicatorMeetingJoinAx.JoinManager</span></span></p></td>
<td align="left"><p><span data-ttu-id="61584-236">活动 X 控件</span><span class="sxs-lookup"><span data-stu-id="61584-236">Active X Control</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="61584-237">LISTNET.Listnet</span><span class="sxs-lookup"><span data-stu-id="61584-237">LISTNET.Listnet</span></span></p></td>
<td align="left"><p><span data-ttu-id="61584-238">活动 X 控件</span><span class="sxs-lookup"><span data-stu-id="61584-238">Active X Control</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="61584-239">OneDrive Pro 浏览器帮助程序</span><span class="sxs-lookup"><span data-stu-id="61584-239">OneDrive Pro Browser Helper</span></span></p></td>
<td align="left"><p><span data-ttu-id="61584-240">活动 X 控件]</span><span class="sxs-lookup"><span data-stu-id="61584-240">Active X Control]</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="61584-241">OneDrive Pro 图标覆盖</span><span class="sxs-lookup"><span data-stu-id="61584-241">OneDrive Pro Icon Overlays</span></span></p></td>
<td align="left"><p><span data-ttu-id="61584-242">当用户查看文件夹 OneDrive Pro 文件夹时，Windows 资源管理器 shell 图标重叠</span><span class="sxs-lookup"><span data-stu-id="61584-242">Windows Explorer shell icon overlays when users look at folders OneDrive Pro folders</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="61584-243">Shell 扩展</span><span class="sxs-lookup"><span data-stu-id="61584-243">Shell extensions</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="61584-244">指向</span><span class="sxs-lookup"><span data-stu-id="61584-244">Shortcuts</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="61584-245">Windows 搜索</span><span class="sxs-lookup"><span data-stu-id="61584-245">Windows Search</span></span></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 






 

 





