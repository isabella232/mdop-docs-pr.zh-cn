---
title: 使用 App-V 部署 Microsoft Office 2016
description: 使用 App-V 部署 Microsoft Office 2016
author: dansimp
ms.assetid: cc675cde-cb8d-4b7c-a700-6104b78f1d89
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 07/25/2017
ms.openlocfilehash: dfedab98e0bdf0a0d5f5e407d9bedadbbf56ad69
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798591"
---
# <span data-ttu-id="380df-103">使用 App-V 部署 Microsoft Office 2016</span><span class="sxs-lookup"><span data-stu-id="380df-103">Deploying Microsoft Office 2016 by Using App-V</span></span>


<span data-ttu-id="380df-104">使用本文中的信息使用 Microsoft Application Virtualization 5.0 或更高版本，将 Microsoft Office 2016 作为虚拟化应用程序提供给组织中的计算机。</span><span class="sxs-lookup"><span data-stu-id="380df-104">Use the information in this article to use Microsoft Application Virtualization 5.0, or later versions, to deliver Microsoft Office 2016 as a virtualized application to computers in your organization.</span></span> <span data-ttu-id="380df-105">有关使用 app-v 交付 Office 2013 的信息，请参阅[使用 App-v 部署 Microsoft Office 2013](deploying-microsoft-office-2013-by-using-app-v.md)。</span><span class="sxs-lookup"><span data-stu-id="380df-105">For information about using App-V to deliver Office 2013, see [Deploying Microsoft Office 2013 by Using App-V](deploying-microsoft-office-2013-by-using-app-v.md).</span></span> <span data-ttu-id="380df-106">有关使用 app-v 交付 Office 2010 的信息，请参阅[使用 App-v 部署 Microsoft Office 2010](deploying-microsoft-office-2010-by-using-app-v.md)。</span><span class="sxs-lookup"><span data-stu-id="380df-106">For information about using App-V to deliver Office 2010, see [Deploying Microsoft Office 2010 by Using App-V](deploying-microsoft-office-2010-by-using-app-v.md).</span></span>

<span data-ttu-id="380df-107">本主题包含以下各节：</span><span class="sxs-lookup"><span data-stu-id="380df-107">This topic contains the following sections:</span></span>

-   [<span data-ttu-id="380df-108">开始之前需要了解的内容</span><span class="sxs-lookup"><span data-stu-id="380df-108">What to know before you start</span></span>](#bkmk-before-you-start)

-   [<span data-ttu-id="380df-109">使用 Office 部署工具为 App-v 创建 Office 2016 程序包</span><span class="sxs-lookup"><span data-stu-id="380df-109">Creating an Office 2016 package for App-V with the Office Deployment Tool</span></span>](#bkmk-create-office-pkg)

-   [<span data-ttu-id="380df-110">发布 app-v 5.0 的 Office 程序包</span><span class="sxs-lookup"><span data-stu-id="380df-110">Publishing the Office package for App-V 5.0</span></span>](#bkmk-pub-pkg-office)

-   [<span data-ttu-id="380df-111">自定义和管理 Office App-v 程序包</span><span class="sxs-lookup"><span data-stu-id="380df-111">Customizing and managing Office App-V packages</span></span>](#bkmk-custmz-manage-office-pkgs)

## <a href="" id="bkmk-before-you-start"></a><span data-ttu-id="380df-112">开始之前需要了解的内容</span><span class="sxs-lookup"><span data-stu-id="380df-112">What to know before you start</span></span>


<span data-ttu-id="380df-113">通过使用 App-v 部署 Office 2016 之前，请查看以下计划信息。</span><span class="sxs-lookup"><span data-stu-id="380df-113">Before you deploy Office 2016 by using App-V, review the following planning information.</span></span>

### <a href="" id="bkmk-supp-vers-coexist"></a><span data-ttu-id="380df-114">支持的 Office 版本和 Office 共存</span><span class="sxs-lookup"><span data-stu-id="380df-114">Supported Office versions and Office coexistence</span></span>

<span data-ttu-id="380df-115">使用下表获取有关受支持的 Office 版本的信息，以及有关运行版本更共存的 Office 的信息。</span><span class="sxs-lookup"><span data-stu-id="380df-115">Use the following table to get information about supported versions of Office and about running coexisting versions of Office.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="380df-116">要查看的信息</span><span class="sxs-lookup"><span data-stu-id="380df-116">Information to review</span></span></th>
<th align="left"><span data-ttu-id="380df-117">描述</span><span class="sxs-lookup"><span data-stu-id="380df-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="planning-for-using-app-v-with-office.md#bkmk-office-vers-supp-appv" data-raw-source="[Supported versions of Microsoft Office](planning-for-using-app-v-with-office.md#bkmk-office-vers-supp-appv)"><span data-ttu-id="380df-118">Microsoft Office 支持的版本</span><span class="sxs-lookup"><span data-stu-id="380df-118">Supported versions of Microsoft Office</span></span></a></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="380df-119">支持的 Office 版本</span><span class="sxs-lookup"><span data-stu-id="380df-119">Supported versions of Office</span></span></p></li>
<li><p><span data-ttu-id="380df-120">支持的部署类型（例如，桌面、个人虚拟桌面基础结构（VDI）、共用 VDI）</span><span class="sxs-lookup"><span data-stu-id="380df-120">Supported deployment types (for example, desktop, personal Virtual Desktop Infrastructure (VDI), pooled VDI)</span></span></p></li>
<li><p><span data-ttu-id="380df-121">Office 授权选项</span><span class="sxs-lookup"><span data-stu-id="380df-121">Office licensing options</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><a href="planning-for-using-app-v-with-office.md#bkmk-plan-coexisting" data-raw-source="[Planning for Using App-V with coexisting versions of Office](planning-for-using-app-v-with-office.md#bkmk-plan-coexisting)"><span data-ttu-id="380df-122">规划将 App-v 与早期版本的 Office 配合使用</span><span class="sxs-lookup"><span data-stu-id="380df-122">Planning for Using App-V with coexisting versions of Office</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="380df-123">在同一台计算机上安装不同版本的 Office 时的注意事项</span><span class="sxs-lookup"><span data-stu-id="380df-123">Considerations for installing different versions of Office on the same computer</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-pkg-pub-reqs"></a><span data-ttu-id="380df-124">打包、发布和部署要求</span><span class="sxs-lookup"><span data-stu-id="380df-124">Packaging, publishing, and deployment requirements</span></span>

<span data-ttu-id="380df-125">通过使用 App-v 部署 Office 之前，请查看以下要求。</span><span class="sxs-lookup"><span data-stu-id="380df-125">Before you deploy Office by using App-V, review the following requirements.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="380df-126">任务</span><span class="sxs-lookup"><span data-stu-id="380df-126">Task</span></span></th>
<th align="left"><span data-ttu-id="380df-127">要求</span><span class="sxs-lookup"><span data-stu-id="380df-127">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="380df-128">包装</span><span class="sxs-lookup"><span data-stu-id="380df-128">Packaging</span></span></p></td>
<td align="left">
<ul>
<li><p><span data-ttu-id="380df-129">要部署到用户的所有 Office 应用程序都必须位于单个程序包中。</span><span class="sxs-lookup"><span data-stu-id="380df-129">All of the Office applications that you want to deploy to users must be in a single package.</span></span></p></li>
<li><p><span data-ttu-id="380df-130">在 app-v 5.0 和更高版本中，必须使用 Office 部署工具创建程序包。</span><span class="sxs-lookup"><span data-stu-id="380df-130">In App-V 5.0 and later, you must use the Office Deployment Tool to create packages.</span></span> <span data-ttu-id="380df-131">不能使用 Sequencer。</span><span class="sxs-lookup"><span data-stu-id="380df-131">You cannot use the Sequencer.</span></span></p></li>
<li><p><span data-ttu-id="380df-132">如果要在 Office 中部署 Microsoft Visio 2016 和 Microsoft Project 2016，则必须将它们包含在与 Office 相同的程序包中。</span><span class="sxs-lookup"><span data-stu-id="380df-132">If you are deploying Microsoft Visio 2016 and Microsoft Project 2016 along with Office, you must include them in the same package with Office.</span></span> <span data-ttu-id="380df-133">有关详细信息，请参阅 <a href="#bkmk-deploy-visio-project" data-raw-source="[Deploying Visio 2016 and Project 2016 with Office](#bkmk-deploy-visio-project)"> 通过 Office 部署 Visio 2016 和 Project 2016 </a> 。</span><span class="sxs-lookup"><span data-stu-id="380df-133">For more information, see <a href="#bkmk-deploy-visio-project" data-raw-source="[Deploying Visio 2016 and Project 2016 with Office](#bkmk-deploy-visio-project)">Deploying Visio 2016 and Project 2016 with Office</a>.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="380df-134">发布</span><span class="sxs-lookup"><span data-stu-id="380df-134">Publishing</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="380df-135">您只能将一个 Office 程序包发布到每台客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="380df-135">You can publish only one Office package to each client computer.</span></span></p></li>
<li><p><span data-ttu-id="380df-136">您必须全局发布 Office 程序包。</span><span class="sxs-lookup"><span data-stu-id="380df-136">You must publish the Office package globally.</span></span> <span data-ttu-id="380df-137">您不能发布给用户。</span><span class="sxs-lookup"><span data-stu-id="380df-137">You cannot publish to the user.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="380df-138">通过使用远程桌面服务将以下任何产品部署到共享计算机：</span><span class="sxs-lookup"><span data-stu-id="380df-138">Deploying any of the following products to a shared computer, for example, by using Remote Desktop Services:</span></span></p>
<ul>
<li><p><span data-ttu-id="380df-139">适用于企业的 Microsoft 365 应用</span><span class="sxs-lookup"><span data-stu-id="380df-139">Microsoft 365 Apps for enterprise</span></span></p></li>
<li><p><span data-ttu-id="380df-140">Visio Pro for Office 365</span><span class="sxs-lookup"><span data-stu-id="380df-140">Visio Pro for Office 365</span></span></p></li>
<li><p><span data-ttu-id="380df-141">Project Pro for Office 365</span><span class="sxs-lookup"><span data-stu-id="380df-141">Project Pro for Office 365</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="380df-142">您必须启用 <a href="https://technet.microsoft.com/library/dn782860.aspx" data-raw-source="[shared computer activation](https://technet.microsoft.com/library/dn782860.aspx)"> 共享计算机激活 </a> 。</span><span class="sxs-lookup"><span data-stu-id="380df-142">You must enable <a href="https://technet.microsoft.com/library/dn782860.aspx" data-raw-source="[shared computer activation](https://technet.microsoft.com/library/dn782860.aspx)">shared computer activation</a>.</span></span></p>
</td>
</tr>
</tbody>
</table>



### <span data-ttu-id="380df-143">从程序包中排除 Office 应用程序</span><span class="sxs-lookup"><span data-stu-id="380df-143">Excluding Office applications from a package</span></span>

<span data-ttu-id="380df-144">下表介绍了从程序包中排除特定 Office 应用程序的推荐方法。</span><span class="sxs-lookup"><span data-stu-id="380df-144">The following table describes the recommended methods for excluding specific Office applications from a package.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="380df-145">任务</span><span class="sxs-lookup"><span data-stu-id="380df-145">Task</span></span></th>
<th align="left"><span data-ttu-id="380df-146">详细信息</span><span class="sxs-lookup"><span data-stu-id="380df-146">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="380df-147">使用 <strong> </strong> Office 部署工具创建程序包时，请使用 ExcludeApp 设置。</span><span class="sxs-lookup"><span data-stu-id="380df-147">Use the <strong>ExcludeApp</strong> setting when you create the package by using the Office Deployment Tool.</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="380df-148">使你能够在 Office 部署工具创建程序包时从程序包中排除特定的 Office 应用程序。</span><span class="sxs-lookup"><span data-stu-id="380df-148">Enables you to exclude specific Office applications from the package when the Office Deployment Tool creates the package.</span></span> <span data-ttu-id="380df-149">例如，你可以使用此设置创建仅包含 Microsoft Word 的程序包。</span><span class="sxs-lookup"><span data-stu-id="380df-149">For example, you can use this setting to create a package that contains only Microsoft Word.</span></span></p></li>
<li><p><span data-ttu-id="380df-150">有关详细信息，请参阅 <a href="https://technet.microsoft.com/library/jj219426.aspx#bkmk-excludeappelement" data-raw-source="[ExcludeApp element](https://technet.microsoft.com/library/jj219426.aspx#bkmk-excludeappelement)"> ExcludeApp 元素 </a> 。</span><span class="sxs-lookup"><span data-stu-id="380df-150">For more information, see <a href="https://technet.microsoft.com/library/jj219426.aspx#bkmk-excludeappelement" data-raw-source="[ExcludeApp element](https://technet.microsoft.com/library/jj219426.aspx#bkmk-excludeappelement)">ExcludeApp element</a>.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="380df-151">修改 DeploymentConfig.xml 文件</span><span class="sxs-lookup"><span data-stu-id="380df-151">Modify the DeploymentConfig.xml file</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="380df-152">创建程序包后修改 DeploymentConfig.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="380df-152">Modify the DeploymentConfig.xml file after the package has been created.</span></span> <span data-ttu-id="380df-153">此文件包含运行 App-V 客户端的计算机上所有用户的默认程序包设置。</span><span class="sxs-lookup"><span data-stu-id="380df-153">This file contains the default package settings for all users on a computer that is running the App-V Client.</span></span></p></li>
<li><p><span data-ttu-id="380df-154">有关详细信息，请参阅 <a href="#bkmk-disable-office-apps" data-raw-source="[Disabling Office 2016 applications](#bkmk-disable-office-apps)"> 禁用 Office 2016 应用程序 </a> 。</span><span class="sxs-lookup"><span data-stu-id="380df-154">For more information, see <a href="#bkmk-disable-office-apps" data-raw-source="[Disabling Office 2016 applications](#bkmk-disable-office-apps)">Disabling Office 2016 applications</a>.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-create-office-pkg"></a><span data-ttu-id="380df-155">使用 Office 部署工具为 App-v 创建 Office 2016 程序包</span><span class="sxs-lookup"><span data-stu-id="380df-155">Creating an Office 2016 package for App-V with the Office Deployment Tool</span></span>


<span data-ttu-id="380df-156">完成以下步骤，为 App-v 5.0 或更高版本创建 Office 2016 程序包。</span><span class="sxs-lookup"><span data-stu-id="380df-156">Complete the following steps to create an Office 2016 package for App-V 5.0 or later.</span></span>

><span data-ttu-id="380df-157">**重要提示** &nbsp; &nbsp;在 app-v 5.0 和更高版本中，必须使用 Office 部署工具创建程序包。</span><span class="sxs-lookup"><span data-stu-id="380df-157">**Important**&nbsp;&nbsp;In App-V 5.0 and later, you must use the Office Deployment Tool to create a package.</span></span> <span data-ttu-id="380df-158">不能使用 Sequencer 创建程序包。</span><span class="sxs-lookup"><span data-stu-id="380df-158">You cannot use the Sequencer to create packages.</span></span>

### <span data-ttu-id="380df-159">查看使用 Office 部署工具的先决条件</span><span class="sxs-lookup"><span data-stu-id="380df-159">Review prerequisites for using the Office Deployment Tool</span></span>

<span data-ttu-id="380df-160">安装 Office 部署工具的计算机必须具有：</span><span class="sxs-lookup"><span data-stu-id="380df-160">The computer on which you are installing the Office Deployment Tool must have:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="380df-161">必备</span><span class="sxs-lookup"><span data-stu-id="380df-161">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="380df-162">描述</span><span class="sxs-lookup"><span data-stu-id="380df-162">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="380df-163">必备软件</span><span class="sxs-lookup"><span data-stu-id="380df-163">Prerequisite software</span></span></p></td>
<td align="left"><p><span data-ttu-id="380df-164">.Net Framework 4</span><span class="sxs-lookup"><span data-stu-id="380df-164">.Net Framework 4</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="380df-165">支持的操作系统</span><span class="sxs-lookup"><span data-stu-id="380df-165">Supported operating systems</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="380df-166">64位版本的 Windows 10</span><span class="sxs-lookup"><span data-stu-id="380df-166">64-bit version of Windows 10</span></span></p></li>
<li><p><span data-ttu-id="380df-167">64位版本的 Windows 8 或8。1</span><span class="sxs-lookup"><span data-stu-id="380df-167">64-bit version of Windows 8 or 8.1</span></span></p></li>
<li><p><span data-ttu-id="380df-168">64位版本的 Windows 7</span><span class="sxs-lookup"><span data-stu-id="380df-168">64-bit version of Windows 7</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


><span data-ttu-id="380df-169">**注意** 在本主题中，术语 "Office 2016 App-v 程序包" 是指订阅许可。</span><span class="sxs-lookup"><span data-stu-id="380df-169">**Note**  In this topic, the term “Office 2016 App-V package” refers to subscription licensing.</span></span>


### <span data-ttu-id="380df-170">使用 Office 部署工具创建 Office 2016 App-v 程序包</span><span class="sxs-lookup"><span data-stu-id="380df-170">Create Office 2016 App-V Packages Using Office Deployment Tool</span></span>

<span data-ttu-id="380df-171">使用 Office 部署工具创建 Office 2016 App-v 程序包。</span><span class="sxs-lookup"><span data-stu-id="380df-171">You create Office 2016 App-V packages by using the Office Deployment Tool.</span></span> <span data-ttu-id="380df-172">以下说明介绍了如何使用订阅授权创建 Office 2016 App-v 包。</span><span class="sxs-lookup"><span data-stu-id="380df-172">The following instructions explain how to create an Office 2016 App-V package with Subscription Licensing.</span></span>

<span data-ttu-id="380df-173">在64位 Windows 计算机上创建 Office 2016 App-v 包。</span><span class="sxs-lookup"><span data-stu-id="380df-173">Create Office 2016 App-V packages on 64-bit Windows computers.</span></span> <span data-ttu-id="380df-174">创建后，Office 2016 App-v 包将在32位和64位 Windows 7、Windows 8.1 和 Windows 10 计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="380df-174">Once created, the Office 2016 App-V package will run on 32-bit and 64-bit Windows 7, Windows 8.1, and Windows 10 computers.</span></span>

### <span data-ttu-id="380df-175">下载 Office 部署工具</span><span class="sxs-lookup"><span data-stu-id="380df-175">Download the Office Deployment Tool</span></span>

<span data-ttu-id="380df-176">Office 2016 App-v 程序包是使用 Office 部署工具创建的，该工具生成 Office 2016 App-v 包。</span><span class="sxs-lookup"><span data-stu-id="380df-176">Office 2016 App-V Packages are created using the Office Deployment Tool, which generates an Office 2016 App-V Package.</span></span> <span data-ttu-id="380df-177">无法通过 App-v sequencer 创建或修改程序包。</span><span class="sxs-lookup"><span data-stu-id="380df-177">The package cannot be created or modified through the App-V sequencer.</span></span> <span data-ttu-id="380df-178">要开始创建软件包，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="380df-178">To begin package creation:</span></span>

1.  <span data-ttu-id="380df-179">下载[Office 2016 部署工具以进行即点](https://www.microsoft.com/download/details.aspx?id=49117)即用。</span><span class="sxs-lookup"><span data-stu-id="380df-179">Download the [Office 2016 Deployment Tool for Click-to-Run](https://www.microsoft.com/download/details.aspx?id=49117).</span></span>

> <span data-ttu-id="380df-180">**重要提示**必须使用 Office 2016 部署工具创建 Office 2016 App-v 程序包。</span><span class="sxs-lookup"><span data-stu-id="380df-180">**Important** You must use the Office 2016 Deployment Tool to create Office 2016 App-V Packages.</span></span>
> 2. <span data-ttu-id="380df-181">运行 .exe 文件，并将其功能提取到所需位置。</span><span class="sxs-lookup"><span data-stu-id="380df-181">Run the .exe file and extract its features into the desired location.</span></span> <span data-ttu-id="380df-182">若要使此过程更简单，您可以创建将保存功能的共享网络文件夹。</span><span class="sxs-lookup"><span data-stu-id="380df-182">To make this process easier, you can create a shared network folder where the features will be saved.</span></span>

    Example: \\\\Server\\Office2016

3. <span data-ttu-id="380df-183">检查 setup.exe 和 configuration.xml 文件是否存在以及是否位于指定的位置。</span><span class="sxs-lookup"><span data-stu-id="380df-183">Check that a setup.exe and a configuration.xml file exist and are in the location you specified.</span></span>

### <span data-ttu-id="380df-184">下载 Office 2016 应用程序</span><span class="sxs-lookup"><span data-stu-id="380df-184">Download Office 2016 applications</span></span>

<span data-ttu-id="380df-185">下载 Office 部署工具后，您可以使用它来获取最新的 Office 2016 应用程序。</span><span class="sxs-lookup"><span data-stu-id="380df-185">After you download the Office Deployment Tool, you can use it to get the latest Office 2016 applications.</span></span> <span data-ttu-id="380df-186">获取 Office 应用程序后，创建 Office 2016 App-v 包。</span><span class="sxs-lookup"><span data-stu-id="380df-186">After getting the Office applications, you create the Office 2016 App-V package.</span></span>

<span data-ttu-id="380df-187">Office 部署工具中包含的 XML 文件指定产品详细信息，如所含语言和 Office 应用程序。</span><span class="sxs-lookup"><span data-stu-id="380df-187">The XML file that is included in the Office Deployment Tool specifies the product details, such as the languages and Office applications included.</span></span>

1. <span data-ttu-id="380df-188">**自定义示例 XML 配置文件：** 使用您使用 Office 部署工具下载的示例 XML 配置文件自定义 Office 应用程序：</span><span class="sxs-lookup"><span data-stu-id="380df-188">**Customize the sample XML configuration file:** Use the sample XML configuration file that you downloaded with the Office Deployment Tool to customize the Office applications:</span></span>

   1. <span data-ttu-id="380df-189">在记事本或你喜爱的文本编辑器中打开示例 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="380df-189">Open the sample XML file in Notepad or your favorite text editor.</span></span>

   2. <span data-ttu-id="380df-190">示例 configuration.xml 文件打开并准备好进行编辑后，您可以指定产品、语言和保存 Office 2016 应用程序的路径。</span><span class="sxs-lookup"><span data-stu-id="380df-190">With the sample configuration.xml file open and ready for editing, you can specify products, languages, and the path to which you save the Office 2016 applications.</span></span> <span data-ttu-id="380df-191">下面是 configuration.xml 文件的基本示例：</span><span class="sxs-lookup"><span data-stu-id="380df-191">The following is a basic example of the configuration.xml file:</span></span>

      ```xml
      <Configuration>
         <Add SourcePath= "\\Server\Office2016” OfficeClientEdition="32" >
          <Product ID="O365ProPlusRetail ">
            <Language ID="en-us" />
          </Product>
          <Product ID="VisioProRetail">
            <Language ID="en-us" />
          </Product>
        </Add>
      </Configuration>
      ```

      ><span data-ttu-id="380df-192">**注意** 配置 XML 是一个示例 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="380df-192">**Note**  The configuration XML is a sample XML file.</span></span> <span data-ttu-id="380df-193">该文件包含注释掉的行。你可以 "取消注释" 这些行以自定义文件的其他设置。</span><span class="sxs-lookup"><span data-stu-id="380df-193">The file includes lines that are commented out. You can “uncomment” these lines to customize additional settings with the file.</span></span> <span data-ttu-id="380df-194">若要 "取消注释" 这些行，请删除 "<！</span><span class="sxs-lookup"><span data-stu-id="380df-194">To “uncomment” these lines, remove the "<!</span></span> <span data-ttu-id="380df-195">-从行的开头开始，在行的末尾 "-->"。</span><span class="sxs-lookup"><span data-stu-id="380df-195">- -" from the beginning of the line, and the "-- >" from the end of the line.</span></span>

      <span data-ttu-id="380df-196">以上 XML 配置文件指定 Office 2016 专业增强版32位版本（包括 Visio 专业增强版）将以英语下载到 \\\\server\\Office 2016，该版本是 Office 应用程序将保存到的位置。</span><span class="sxs-lookup"><span data-stu-id="380df-196">The above XML configuration file specifies that Office 2016 ProPlus 32-bit edition, including Visio ProPlus, will be downloaded in English to the \\\\server\\Office 2016, which is the location where Office applications will be saved to.</span></span> <span data-ttu-id="380df-197">请注意，应用程序的产品 ID 不会影响 Office 的最终许可。</span><span class="sxs-lookup"><span data-stu-id="380df-197">Note that the Product ID of the applications will not affect the final licensing of Office.</span></span> <span data-ttu-id="380df-198">通过在更高阶段指定授权，可以从相同的应用程序创建具有各种许可的 Office 2016 App-v 程序包。</span><span class="sxs-lookup"><span data-stu-id="380df-198">Office 2016 App-V packages with various licensing can be created from the same applications through specifying licensing in a later stage.</span></span> <span data-ttu-id="380df-199">下表总结了 XML 文件的可自定义属性和元素：</span><span class="sxs-lookup"><span data-stu-id="380df-199">The table below summarizes the customizable attributes and elements of XML file:</span></span>

      <table>
      <colgroup>
      <col width="33%" />
      <col width="33%" />
      <col width="33%" />
      </colgroup>
      <thead>
      <tr class="header">
      <th align="left"><span data-ttu-id="380df-200">输入</span><span class="sxs-lookup"><span data-stu-id="380df-200">Input</span></span></th>
      <th align="left"><span data-ttu-id="380df-201">说明</span><span class="sxs-lookup"><span data-stu-id="380df-201">Description</span></span></th>
      <th align="left"><span data-ttu-id="380df-202">示例</span><span class="sxs-lookup"><span data-stu-id="380df-202">Example</span></span></th>
      </tr>
      </thead>
      <tbody>
      <tr class="odd">
      <td align="left"><p><span data-ttu-id="380df-203">添加元素</span><span class="sxs-lookup"><span data-stu-id="380df-203">Add element</span></span></p></td>
      <td align="left"><p><span data-ttu-id="380df-204">指定要包含在程序包中的产品和语言。</span><span class="sxs-lookup"><span data-stu-id="380df-204">Specifies the products and languages to include in the package.</span></span></p></td>
      <td align="left"><p><span data-ttu-id="380df-205">不适用</span><span class="sxs-lookup"><span data-stu-id="380df-205">N/A</span></span></p></td>
      </tr>
      <tr class="even">
      <td align="left"><p><span data-ttu-id="380df-206">OfficeClientEdition （Add 元素的属性）</span><span class="sxs-lookup"><span data-stu-id="380df-206">OfficeClientEdition (attribute of Add element)</span></span></p></td>
      <td align="left"><p><span data-ttu-id="380df-207">指定要使用的 Office 2016 产品的版本：32位或64位。</span><span class="sxs-lookup"><span data-stu-id="380df-207">Specifies the edition of Office 2016 product to use: 32-bit or 64-bit.</span></span> <span data-ttu-id="380df-208">如果 <strong> OfficeClientEdition 未设置为有效值，则操作将失败 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="380df-208">The operation fails if <strong>OfficeClientEdition</strong> is not set to a valid value.</span></span></p></td>
      <td align="left"><p><strong><span data-ttu-id="380df-209">OfficeClientEdition </strong> = &quot; 32&quot;</span><span class="sxs-lookup"><span data-stu-id="380df-209">OfficeClientEdition</strong>=&quot;32&quot;</span></span></p>
      <p><strong><span data-ttu-id="380df-210">OfficeClientEdition </strong> = &quot; 64&quot;</span><span class="sxs-lookup"><span data-stu-id="380df-210">OfficeClientEdition</strong>=&quot;64&quot;</span></span></p></td>
      </tr>
      <tr class="odd">
      <td align="left"><p><span data-ttu-id="380df-211">Product 元素</span><span class="sxs-lookup"><span data-stu-id="380df-211">Product element</span></span></p></td>
      <td align="left"><p><span data-ttu-id="380df-212">指定应用程序。</span><span class="sxs-lookup"><span data-stu-id="380df-212">Specifies the application.</span></span> <span data-ttu-id="380df-213">必须在此处将 Project 2016 和 Visio 2016 指定为应用程序中包含的已添加产品。</span><span class="sxs-lookup"><span data-stu-id="380df-213">Project 2016 and Visio 2016 must be specified here as an added product to be included in the applications.</span></span>

      <span data-ttu-id="380df-214">有关产品 Id 的详细信息，请参阅 <a href="https://support.microsoft.com/kb/2842297" data-raw-source="[Product IDs that are supported by the Office Deployment Tool for Click-to-Run](https://support.microsoft.com/kb/2842297)"> Office 部署工具支持的即点即用支持的产品 id</span><span class="sxs-lookup"><span data-stu-id="380df-214">For more information about the product IDs, see <a href="https://support.microsoft.com/kb/2842297" data-raw-source="[Product IDs that are supported by the Office Deployment Tool for Click-to-Run](https://support.microsoft.com/kb/2842297)">Product IDs that are supported by the Office Deployment Tool for Click-to-Run</span></span></a>
      </p></td>
      <td align="left"><p><code>Product ID =&quot;O365ProPlusRetail &quot;</code></p>
      <p><code>Product ID =&quot;VisioProRetail&quot;</code></p>
      <p><code>Product ID =&quot;ProjectProRetail&quot;</code></p>
      </td>
      </tr>
      <tr class="even">
      <td align="left"><p><span data-ttu-id="380df-215">语言元素</span><span class="sxs-lookup"><span data-stu-id="380df-215">Language element</span></span></p></td>
      <td align="left"><p><span data-ttu-id="380df-216">指定应用程序中支持的语言</span><span class="sxs-lookup"><span data-stu-id="380df-216">Specifies the language supported in the applications</span></span></p></td>
      <td align="left"><p><code>Language ID=&quot;en-us&quot;</code></p></td>
      </tr>
      <tr class="odd">
      <td align="left"><p><span data-ttu-id="380df-217">版本（Add 元素的属性）</span><span class="sxs-lookup"><span data-stu-id="380df-217">Version (attribute of Add element)</span></span></p></td>
      <td align="left"><p><span data-ttu-id="380df-218">可选。</span><span class="sxs-lookup"><span data-stu-id="380df-218">Optional.</span></span> <span data-ttu-id="380df-219">指定要用于程序包的版本</span><span class="sxs-lookup"><span data-stu-id="380df-219">Specifies a build to use for the package</span></span></p>
      <p><span data-ttu-id="380df-220">默认为最新播发版本（在 Office 源 v32.CAB 中定义）。</span><span class="sxs-lookup"><span data-stu-id="380df-220">Defaults to latest advertised build (as defined in v32.CAB at the Office source).</span></span></p></td>
      <td align="left"><p><code>16.1.2.3</code></p></td>
      </tr>
      <tr class="even">
      <td align="left"><p><span data-ttu-id="380df-221">SourcePath （Add 元素的属性）</span><span class="sxs-lookup"><span data-stu-id="380df-221">SourcePath (attribute of Add element)</span></span></p></td>
      <td align="left"><p><span data-ttu-id="380df-222">指定应用程序将保存到的位置。</span><span class="sxs-lookup"><span data-stu-id="380df-222">Specifies the location in which the applications will be saved to.</span></span></p></td>
      <td align="left"><p><code>Sourcepath = &quot;\Server\Office2016”</code></p></td>
      </tr>
      <tr class="even">
      <td align="left"><p><span data-ttu-id="380df-223">频道（Add 元素的属性）</span><span class="sxs-lookup"><span data-stu-id="380df-223">Channel (attribute of Add element)</span></span></p></td>
      <td align="left"><p><span data-ttu-id="380df-224">可选。</span><span class="sxs-lookup"><span data-stu-id="380df-224">Optional.</span></span> <span data-ttu-id="380df-225">指定要下载或安装的产品的更新频道。</span><span class="sxs-lookup"><span data-stu-id="380df-225">Specifies the update channel for the product that you want to download or install.</span></span> </p><p><span data-ttu-id="380df-226">有关更新频道的详细信息，请参阅适用于企业的 Microsoft 365 应用的更新频道概述。</span><span class="sxs-lookup"><span data-stu-id="380df-226">For more information about update channels, see Overview of update channels for Microsoft 365 Apps for enterprise.</span></span></p></td>
      <td align="left"><p><code>Channel=&quot;Deferred&quot;</code></p></td>
      </tr>
      </tbody>
      </table>

      <span data-ttu-id="380df-227">编辑 configuration.xml 文件以指定所需的产品、语言以及 Office 2016 应用程序将保存到的位置时，可以保存配置文件，例如 Customconfig.xml。</span><span class="sxs-lookup"><span data-stu-id="380df-227">After editing the configuration.xml file to specify the desired product, languages, and also the location which the Office 2016 applications will be saved onto, you can save the configuration file, for example, as Customconfig.xml.</span></span>

2. <span data-ttu-id="380df-228">将**应用程序下载到指定位置：** 使用提升的命令提示符和64位操作系统下载稍后将转换为 App-v 包的 Office 2016 应用程序。</span><span class="sxs-lookup"><span data-stu-id="380df-228">**Download the applications into the specified location:** Use an elevated command prompt and a 64 bit operating system to download the Office 2016 applications that will later be converted into an App-V package.</span></span> <span data-ttu-id="380df-229">下面是带有详细说明的示例命令：</span><span class="sxs-lookup"><span data-stu-id="380df-229">Below is an example command with a description of details:</span></span>

   ``` syntax
   \\server\Office2016\setup.exe /download \\server\Office2016\Customconfig.xml
   ```

   <span data-ttu-id="380df-230">在示例中：</span><span class="sxs-lookup"><span data-stu-id="380df-230">In the example:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="380df-231">\server\Office2016</span><span class="sxs-lookup"><span data-stu-id="380df-231">\server\Office2016</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="380df-232">是包含 Office 部署工具和自定义 Configuration.xml 文件的网络共享位置 Customconfig.xml。</span><span class="sxs-lookup"><span data-stu-id="380df-232">is the network share location that contains the Office Deployment Tool and the custom Configuration.xml file, Customconfig.xml.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="380df-233">Setup.exe</span><span class="sxs-lookup"><span data-stu-id="380df-233">Setup.exe</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="380df-234">是 Office 部署工具。</span><span class="sxs-lookup"><span data-stu-id="380df-234">is the Office Deployment Tool.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="380df-235">/download</span><span class="sxs-lookup"><span data-stu-id="380df-235">/download</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="380df-236">下载在 customConfig.xml 文件中指定的 Office 2016 应用程序。</span><span class="sxs-lookup"><span data-stu-id="380df-236">downloads the Office 2016 applications that you specify in the customConfig.xml file.</span></span> <span data-ttu-id="380df-237">这些位可以在使用批量许可的 Office 2016 App-v 包中转换。</span><span class="sxs-lookup"><span data-stu-id="380df-237">These bits can be later converted in an Office 2016 App-V package with Volume Licensing.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="380df-238">\server\Office2016\Customconfig.xml</span><span class="sxs-lookup"><span data-stu-id="380df-238">\server\Office2016\Customconfig.xml</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="380df-239">传递完成下载过程所需的 XML 配置文件，在本示例中 customconfig.xml。</span><span class="sxs-lookup"><span data-stu-id="380df-239">passes the XML configuration file required to complete the download process, in this example, customconfig.xml.</span></span> <span data-ttu-id="380df-240">使用 "下载" 命令后，应在配置 xml 文件中指定的位置找到 Office 应用程序，本例中为 \Server\Office2016。</span><span class="sxs-lookup"><span data-stu-id="380df-240">After using the download command, Office applications should be found in the location specified in the configuration xml file, in this example \Server\Office2016.</span></span></p></td>
   </tr>
   </tbody>
   </table>



### <span data-ttu-id="380df-241">将 Office 应用程序转换为 App-v 包</span><span class="sxs-lookup"><span data-stu-id="380df-241">Convert the Office applications into an App-V package</span></span>

<span data-ttu-id="380df-242">通过 Office 部署工具下载 Office 2016 应用程序后，请使用 Office 部署工具将它们转换为 Office 2016 App-v 包。</span><span class="sxs-lookup"><span data-stu-id="380df-242">After you download the Office 2016 applications through the Office Deployment Tool, use the Office Deployment Tool to convert them into an Office 2016 App-V package.</span></span> <span data-ttu-id="380df-243">完成与你的许可模型对应的步骤。</span><span class="sxs-lookup"><span data-stu-id="380df-243">Complete the steps that correspond to your licensing model.</span></span>

**<span data-ttu-id="380df-244">需要执行的操作摘要：</span><span class="sxs-lookup"><span data-stu-id="380df-244">Summary of what you’ll need to do:</span></span>**

-   <span data-ttu-id="380df-245">在64位 Windows 计算机上创建 Office 2016 App-v 包。</span><span class="sxs-lookup"><span data-stu-id="380df-245">Create the Office 2016 App-V packages on 64-bit Windows computers.</span></span> <span data-ttu-id="380df-246">但是，该包将在32位和64位 Windows 7、Windows 8 或8.1 以及 Windows 10 计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="380df-246">However, the package will run on 32-bit and 64-bit Windows 7, Windows 8 or 8.1, and Windows 10 computers.</span></span>

-   <span data-ttu-id="380df-247">使用 Office 部署工具为订阅授权包创建 Office App-v 程序包，然后修改 CustomConfig.xml 配置文件。</span><span class="sxs-lookup"><span data-stu-id="380df-247">Create an Office App-V package for Subscription Licensing package by using the Office Deployment Tool, and then modify the CustomConfig.xml configuration file.</span></span>

    <span data-ttu-id="380df-248">下表汇总了您所使用的授权模型的 CustomConfig.xml 文件中需要输入的值。</span><span class="sxs-lookup"><span data-stu-id="380df-248">The following table summarizes the values you need to enter in the CustomConfig.xml file for the licensing model you’re using.</span></span> <span data-ttu-id="380df-249">表格后面的部分中的步骤将指定所需的确切条目。</span><span class="sxs-lookup"><span data-stu-id="380df-249">The steps in the sections that follow the table will specify the exact entries you need to make.</span></span>

><span data-ttu-id="380df-250">**Note** &nbsp; 注意 &nbsp;你可以使用 Office 部署工具为适用于企业的 Microsoft 365 应用创建 app-v 程序包。</span><span class="sxs-lookup"><span data-stu-id="380df-250">**Note**&nbsp;&nbsp;You can use the Office Deployment Tool to create App-V packages for Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="380df-251">不支持创建批量许可版本的 Office 专业增强版或 Office Standard 的程序包。</span><span class="sxs-lookup"><span data-stu-id="380df-251">Creating packages for the volume-licensed versions of Office Professional Plus or Office Standard is not supported.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="380df-252">产品 ID</span><span class="sxs-lookup"><span data-stu-id="380df-252">Product ID</span></span></th>
<th align="left"><span data-ttu-id="380df-253">订阅许可</span><span class="sxs-lookup"><span data-stu-id="380df-253">Subscription Licensing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="380df-254">Office 2016</span><span class="sxs-lookup"><span data-stu-id="380df-254">Office 2016</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="380df-255">O365proplusretail 用作</span><span class="sxs-lookup"><span data-stu-id="380df-255">O365ProPlusRetail</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="380df-256">Office 2016 与 Visio 2016</span><span class="sxs-lookup"><span data-stu-id="380df-256">Office 2016 with Visio 2016</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="380df-257">O365proplusretail 用作</span><span class="sxs-lookup"><span data-stu-id="380df-257">O365ProPlusRetail</span></span></p>
<p><span data-ttu-id="380df-258">VisioProRetail</span><span class="sxs-lookup"><span data-stu-id="380df-258">VisioProRetail</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="380df-259">Office 2016 与 Visio 2016 和 Project 2016</span><span class="sxs-lookup"><span data-stu-id="380df-259">Office 2016 with Visio 2016 and Project 2016</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="380df-260">O365proplusretail 用作</span><span class="sxs-lookup"><span data-stu-id="380df-260">O365ProPlusRetail</span></span></p>
<p><span data-ttu-id="380df-261">VisioProRetail</span><span class="sxs-lookup"><span data-stu-id="380df-261">VisioProRetail</span></span></p>
<p><span data-ttu-id="380df-262">ProjectProRetail</span><span class="sxs-lookup"><span data-stu-id="380df-262">ProjectProRetail</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="380df-263">如何将 Office 应用程序转换为 App-v 包</span><span class="sxs-lookup"><span data-stu-id="380df-263">How to convert the Office applications into an App-V package</span></span>**

1. <span data-ttu-id="380df-264">在记事本中，重新打开 CustomConfig.xml 文件，然后对文件进行以下更改：</span><span class="sxs-lookup"><span data-stu-id="380df-264">In Notepad, reopen the CustomConfig.xml file, and make the following changes to the file:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="380df-265">参数</span><span class="sxs-lookup"><span data-stu-id="380df-265">Parameter</span></span></th>
   <th align="left"><span data-ttu-id="380df-266">将值更改为</span><span class="sxs-lookup"><span data-stu-id="380df-266">What to change the value to</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="380df-267">SourcePath</span><span class="sxs-lookup"><span data-stu-id="380df-267">SourcePath</span></span></p></td>
   <td align="left"><p><span data-ttu-id="380df-268">指向之前下载的 Office 应用程序。</span><span class="sxs-lookup"><span data-stu-id="380df-268">Point to the Office applications downloaded earlier.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="380df-269">ProductID</span><span class="sxs-lookup"><span data-stu-id="380df-269">ProductID</span></span></p></td>
   <td align="left"><p><span data-ttu-id="380df-270">指定订阅许可，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="380df-270">Specify Subscription licensing, as shown in the following example:</span></span></p>
   <pre class="syntax" space="preserve"><code>&lt;Configuration&gt;
      &lt;Add SourcePath= &quot;\server\Office 2016&quot; OfficeClientEdition=&quot;32&quot; &gt;
       &lt;Product ID=&quot;O365ProPlusRetail&quot;&gt;
         &lt;Language ID=&quot;en-us&quot; /&gt;
       &lt;/Product&gt;
       &lt;Product ID=&quot;VisioProRetail&quot;&gt;
         &lt;Language ID=&quot;en-us&quot; /&gt;
       &lt;/Product&gt;
     &lt;/Add&gt;
   &lt;/Configuration&gt; </code></pre>
   <p><span data-ttu-id="380df-271">在此示例中，创建带有订阅授权的程序包的以下更改：</span><span class="sxs-lookup"><span data-stu-id="380df-271">In this example, the following changes were made to create a package with Subscription licensing:</span></span></p>
   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="380df-272">SourcePath</span><span class="sxs-lookup"><span data-stu-id="380df-272">SourcePath</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="380df-273">路径，该路径已更改为指向之前下载的 Office 应用程序。</span><span class="sxs-lookup"><span data-stu-id="380df-273">is the path, which was changed to point to the Office applications that were downloaded earlier.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="380df-274">产品 ID</span><span class="sxs-lookup"><span data-stu-id="380df-274">Product ID</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="380df-275">for Office 已更改为 <code>O365ProPlusRetail</code> 。</span><span class="sxs-lookup"><span data-stu-id="380df-275">for Office was changed to <code>O365ProPlusRetail</code>.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="380df-276">产品 ID</span><span class="sxs-lookup"><span data-stu-id="380df-276">Product ID</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="380df-277">Visio 的已更改为 <code>VisioProRetail</code> 。</span><span class="sxs-lookup"><span data-stu-id="380df-277">for Visio was changed to <code>VisioProRetail</code>.</span></span></p></td>
   </tr>
   </tbody>
   </table>
   <p></p>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="380df-278">ExcludeApp （可选）</span><span class="sxs-lookup"><span data-stu-id="380df-278">ExcludeApp (optional)</span></span></p></td>
   <td align="left"><p><span data-ttu-id="380df-279">允许你指定不希望包含在 Office 部署工具创建的 App-v 程序包中的 Office 程序。</span><span class="sxs-lookup"><span data-stu-id="380df-279">Lets you specify Office programs that you don’t want included in the App-V package that the Office Deployment Tool creates.</span></span> <span data-ttu-id="380df-280">例如，您可以排除 Access 和 InfoPath。</span><span class="sxs-lookup"><span data-stu-id="380df-280">For example, you can exclude Access and InfoPath.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="380df-281">PACKAGEGUID （可选）</span><span class="sxs-lookup"><span data-stu-id="380df-281">PACKAGEGUID (optional)</span></span></p></td>
   <td align="left"><p><span data-ttu-id="380df-282">默认情况下，Office 部署工具创建的所有 app-v 程序包共享相同的 App-v 包 ID。</span><span class="sxs-lookup"><span data-stu-id="380df-282">By default, all App-V packages created by the Office Deployment Tool share the same App-V Package ID.</span></span> <span data-ttu-id="380df-283">你可以使用 PACKAGEGUID 为每个程序包指定不同的程序包 ID，从而允许你发布由 Office 部署工具创建的多个 App-v 程序包，并使用 App-v 服务器对其进行管理。</span><span class="sxs-lookup"><span data-stu-id="380df-283">You can use PACKAGEGUID to specify a different package ID for each package, which allows you to publish multiple App-V packages, created by the Office Deployment Tool, and manage them by using the App-V Server.</span></span></p>
   <p><span data-ttu-id="380df-284">使用此参数的一个示例是为不同用户创建不同的程序包。</span><span class="sxs-lookup"><span data-stu-id="380df-284">An example of when to use this parameter is if you create different packages for different users.</span></span> <span data-ttu-id="380df-285">例如，你可以为某些用户创建一个仅包含 Office 2016 的程序包，并使用 Office 2016 和 Visio 2016 为另一组用户创建另一个程序包。</span><span class="sxs-lookup"><span data-stu-id="380df-285">For example, you can create a package with just Office 2016 for some users, and create another package with Office 2016 and Visio 2016 for another set of users.</span></span></p>
<span data-ttu-id="380df-286">&gt;<strong>注意 </strong> 即使你使用了唯一的程序包 id，你仍然可以将仅一个 app-v 包部署到单个设备。</span><span class="sxs-lookup"><span data-stu-id="380df-286">&gt;<strong>Note</strong> Even if you use unique package IDs, you can still deploy only one App-V package to a single device.</span></span>
   </td>
   </tr>
   </tbody>
   </table>



2. <span data-ttu-id="380df-287">使用/packager 命令可将 Office 应用程序转换为 Office 2016 App-v 包。</span><span class="sxs-lookup"><span data-stu-id="380df-287">Use the /packager command to convert the Office applications to an Office 2016 App-V package.</span></span>

   <span data-ttu-id="380df-288">例如：</span><span class="sxs-lookup"><span data-stu-id="380df-288">For example:</span></span>

   ``` syntax
   \\server\Office2016\setup.exe /packager \\server\Office2016\Customconfig.xml  \\server\share\Office2016AppV
   ```

   <span data-ttu-id="380df-289">在示例中：</span><span class="sxs-lookup"><span data-stu-id="380df-289">In the example:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="380df-290">\server\Office2016</span><span class="sxs-lookup"><span data-stu-id="380df-290">\server\Office2016</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="380df-291">是包含 Office 部署工具和自定义 Configuration.xml 文件的网络共享位置 Customconfig.xml。</span><span class="sxs-lookup"><span data-stu-id="380df-291">is the network share location that contains the Office Deployment Tool and the custom Configuration.xml file, Customconfig.xml.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="380df-292">Setup.exe</span><span class="sxs-lookup"><span data-stu-id="380df-292">Setup.exe</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="380df-293">是 Office 部署工具。</span><span class="sxs-lookup"><span data-stu-id="380df-293">is the Office Deployment Tool.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="380df-294">/packager</span><span class="sxs-lookup"><span data-stu-id="380df-294">/packager</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="380df-295">创建 Office 2016 App-v 包，其中包含在 customConfig.xml 文件中指定的许可类型。</span><span class="sxs-lookup"><span data-stu-id="380df-295">creates the Office 2016 App-V package with the type of licensing specified in the customConfig.xml file.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="380df-296">\server\Office2016\Customconfig.xml</span><span class="sxs-lookup"><span data-stu-id="380df-296">\server\Office2016\Customconfig.xml</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="380df-297">传递已针对打包阶段准备的配置 XML 文件（在本例中为 customConfig）。</span><span class="sxs-lookup"><span data-stu-id="380df-297">passes the configuration XML file (in this case customConfig) that has been prepared for the packaging stage.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="380df-298">\server\share\Office 2016AppV</span><span class="sxs-lookup"><span data-stu-id="380df-298">\server\share\Office 2016AppV</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="380df-299">指定新创建的 Office App-v 包的位置。</span><span class="sxs-lookup"><span data-stu-id="380df-299">specifies the location of the newly created Office App-V package.</span></span></p></td>
   </tr>
   </tbody>
   </table>



~~~
After you run the **/packager** command, the following folders appear up in the directory where you specified the package should be saved:

-   **App-V Packages** – contains an Office 2016 App-V package and two deployment configuration files.

-   **WorkingDir**

**Note** To troubleshoot any issues, see the log files in the %temp% directory (default).
~~~



3. <span data-ttu-id="380df-300">验证 Office 2016 App-v 程序包是否正常工作：</span><span class="sxs-lookup"><span data-stu-id="380df-300">Verify that the Office 2016 App-V package works correctly:</span></span>

   1.  <span data-ttu-id="380df-301">将你全局创建的 Office 2016 App-v 包发布到测试计算机，并验证是否显示 Office 2016 快捷方式。</span><span class="sxs-lookup"><span data-stu-id="380df-301">Publish the Office 2016 App-V package, which you created globally, to a test computer, and verify that the Office 2016 shortcuts appear.</span></span>

   2.  <span data-ttu-id="380df-302">启动一些 Office 2016 应用程序（如 Excel 或 Word），以确保程序包按预期工作。</span><span class="sxs-lookup"><span data-stu-id="380df-302">Start a few Office 2016 applications, such as Excel or Word, to ensure that your package is working as expected.</span></span>

## <a href="" id="bkmk-pub-pkg-office"></a><span data-ttu-id="380df-303">发布 app-v 的 Office 程序包</span><span class="sxs-lookup"><span data-stu-id="380df-303">Publishing the Office package for App-V</span></span>


<span data-ttu-id="380df-304">使用以下信息发布 Office 程序包。</span><span class="sxs-lookup"><span data-stu-id="380df-304">Use the following information to publish an Office package.</span></span>

### <span data-ttu-id="380df-305">用于发布 Office App-v 程序包的方法</span><span class="sxs-lookup"><span data-stu-id="380df-305">Methods for publishing Office App-V packages</span></span>

<span data-ttu-id="380df-306">使用用于任何其他程序包的相同方法部署 Office 2016 的 app-v 程序包：</span><span class="sxs-lookup"><span data-stu-id="380df-306">Deploy the App-V package for Office 2016 by using the same methods you use for any other package:</span></span>

-   <span data-ttu-id="380df-307">System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="380df-307">System Center Configuration Manager</span></span>

-   <span data-ttu-id="380df-308">App-v 服务器</span><span class="sxs-lookup"><span data-stu-id="380df-308">App-V Server</span></span>

-   <span data-ttu-id="380df-309">通过 PowerShell 命令独立运行</span><span class="sxs-lookup"><span data-stu-id="380df-309">Stand-alone through PowerShell commands</span></span>

### <span data-ttu-id="380df-310">发布先决条件和要求</span><span class="sxs-lookup"><span data-stu-id="380df-310">Publishing prerequisites and requirements</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="380df-311">先决条件或要求</span><span class="sxs-lookup"><span data-stu-id="380df-311">Prerequisite or requirement</span></span></th>
<th align="left"><span data-ttu-id="380df-312">详细信息</span><span class="sxs-lookup"><span data-stu-id="380df-312">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="380df-313">在 App-v 客户端上启用 PowerShell 脚本</span><span class="sxs-lookup"><span data-stu-id="380df-313">Enable PowerShell scripting on the App-V clients</span></span></p></td>
<td align="left"><p><span data-ttu-id="380df-314">若要发布 Office 2016 程序包，必须运行脚本。</span><span class="sxs-lookup"><span data-stu-id="380df-314">To publish Office 2016 packages, you must run a script.</span></span></p>
<p><span data-ttu-id="380df-315">默认情况下，在 App-v 客户端上禁用程序包脚本。</span><span class="sxs-lookup"><span data-stu-id="380df-315">Package scripts are disabled by default on App-V clients.</span></span> <span data-ttu-id="380df-316">若要启用脚本，请运行以下 PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="380df-316">To enable scripting, run the following PowerShell command:</span></span></p>
<pre class="syntax" space="preserve"><code>Set-AppvClientConfiguration –EnablePackageScripts 1</code></pre></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="380df-317">全局发布 Office 2016 程序包</span><span class="sxs-lookup"><span data-stu-id="380df-317">Publish the Office 2016 package globally</span></span></p></td>
<td align="left"><p><span data-ttu-id="380df-318">Office App-v 程序包中的扩展点需要在计算机级别安装。</span><span class="sxs-lookup"><span data-stu-id="380df-318">Extension points in the Office App-V package require installation at the computer level.</span></span></p>
<p><span data-ttu-id="380df-319">当您在计算机级别发布时，不需要任何先决条件操作或可再发行组件，并且 Office 2016 程序包全局使其应用程序可以像本地安装的 Office 一样工作，从而消除了管理员自定义程序包的需要。</span><span class="sxs-lookup"><span data-stu-id="380df-319">When you publish at the computer level, no prerequisite actions or redistributables are needed, and the Office 2016 package globally enables its applications to work like natively installed Office, eliminating the need for administrators to customize packages.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="380df-320">如何发布 Office 程序包</span><span class="sxs-lookup"><span data-stu-id="380df-320">How to publish an Office package</span></span>

<span data-ttu-id="380df-321">运行以下命令以在全球范围内发布 Office 程序包：</span><span class="sxs-lookup"><span data-stu-id="380df-321">Run the following command to publish an Office package globally:</span></span>

-   `Add-AppvClientPackage <Path_to_AppV_Package> | Publish-AppvClientPackage –global`

-   <span data-ttu-id="380df-322">从 App-v Server 上的 Web 管理控制台中，你可以向一组计算机（而不是用户组）添加权限，以使程序包能够在相应组中全局发布到计算机。</span><span class="sxs-lookup"><span data-stu-id="380df-322">From the Web Management Console on the App-V Server, you can add permissions to a group of computers instead of to a user group to enable packages to be published globally to the computers in the corresponding group.</span></span>

## <a href="" id="bkmk-custmz-manage-office-pkgs"></a><span data-ttu-id="380df-323">自定义和管理 Office App-v 程序包</span><span class="sxs-lookup"><span data-stu-id="380df-323">Customizing and managing Office App-V packages</span></span>


<span data-ttu-id="380df-324">若要管理 Office App-v 程序包，请使用与任何其他程序包相同的操作，但有一些例外，如下部分所述。</span><span class="sxs-lookup"><span data-stu-id="380df-324">To manage your Office App-V packages, use the same operations as you would for any other package, but there are a few exceptions, as outlined in the following sections.</span></span>

-   [<span data-ttu-id="380df-325">使用连接组启用 Office 插件</span><span class="sxs-lookup"><span data-stu-id="380df-325">Enabling Office plug-ins by using connection groups</span></span>](#bkmk-enable-office-plugins)

-   [<span data-ttu-id="380df-326">禁用 Office 2016 应用程序</span><span class="sxs-lookup"><span data-stu-id="380df-326">Disabling Office 2016 applications</span></span>](#bkmk-disable-office-apps)

-   [<span data-ttu-id="380df-327">禁用 Office 2016 快捷方式</span><span class="sxs-lookup"><span data-stu-id="380df-327">Disabling Office 2016 shortcuts</span></span>](#bkmk-disable-shortcuts)

-   [<span data-ttu-id="380df-328">管理 Office 2016 程序包升级</span><span class="sxs-lookup"><span data-stu-id="380df-328">Managing Office 2016 package upgrades</span></span>](#bkmk-manage-office-pkg-upgrd)

-   [<span data-ttu-id="380df-329">通过 Office 部署 Visio 2016 和 Project 2016</span><span class="sxs-lookup"><span data-stu-id="380df-329">Deploying Visio 2016 and Project 2016 with Office</span></span>](#bkmk-deploy-visio-project)

### <a href="" id="bkmk-enable-office-plugins"></a><span data-ttu-id="380df-330">使用连接组启用 Office 插件</span><span class="sxs-lookup"><span data-stu-id="380df-330">Enabling Office plug-ins by using connection groups</span></span>

<span data-ttu-id="380df-331">使用此部分中的步骤，通过 Office 程序包启用 Office 插件。</span><span class="sxs-lookup"><span data-stu-id="380df-331">Use the steps in this section to enable Office plug-ins with your Office package.</span></span> <span data-ttu-id="380df-332">若要使用 Office 插件，必须使用 App-v Sequencer 创建单独的程序包，该程序包只包含插件。不能使用 Office 部署工具创建插件程序包。</span><span class="sxs-lookup"><span data-stu-id="380df-332">To use Office plug-ins, you must use the App-V Sequencer to create a separate package that contains just the plug-ins. You cannot use the Office Deployment Tool to create the plug-ins package.</span></span> <span data-ttu-id="380df-333">然后，创建包含 Office 程序包和插件程序包的连接组，如以下步骤所述。</span><span class="sxs-lookup"><span data-stu-id="380df-333">You then create a connection group that contains the Office package and the plug-ins package, as described in the following steps.</span></span>

**<span data-ttu-id="380df-334">为 Office App-v 程序包启用插件</span><span class="sxs-lookup"><span data-stu-id="380df-334">To enable plug-ins for Office App-V packages</span></span>**

1.  <span data-ttu-id="380df-335">通过 App-v Server、System Center Configuration Manager 或 PowerShell cmdlet 添加连接组。</span><span class="sxs-lookup"><span data-stu-id="380df-335">Add a Connection Group through App-V Server, System Center Configuration Manager, or a PowerShell cmdlet.</span></span>

2.  <span data-ttu-id="380df-336">使用 App-v 排序器对插件进行排序。</span><span class="sxs-lookup"><span data-stu-id="380df-336">Sequence your plug-ins using the App-V Sequencer.</span></span> <span data-ttu-id="380df-337">确保在用于对插件进行排序的计算机上安装了 Office 2016。</span><span class="sxs-lookup"><span data-stu-id="380df-337">Ensure that Office 2016 is installed on the computer being used to sequence the plug-in.</span></span> <span data-ttu-id="380df-338">在序列化 Office 2016 插件时，建议使用排序计算机上的 Microsoft 365 应用 for enterprise （非虚拟）。</span><span class="sxs-lookup"><span data-stu-id="380df-338">It is recommended you use Microsoft 365 Apps for enterprise(non-virtual) on the sequencing computer when you sequence Office 2016 plug-ins.</span></span>

3.  <span data-ttu-id="380df-339">创建包含所需插件的 app-v 包。</span><span class="sxs-lookup"><span data-stu-id="380df-339">Create an App-V package that includes the desired plug-ins.</span></span>

4.  <span data-ttu-id="380df-340">通过 App-v server、System Center Configuration Manager 或 PowerShell cmdlet 添加连接组。</span><span class="sxs-lookup"><span data-stu-id="380df-340">Add a Connection Group through App-V server, System Center Configuration Manager, or a PowerShell cmdlet.</span></span>

5.  <span data-ttu-id="380df-341">将 Office 2016 App-v 包和已排序的插件包添加到你创建的连接组。</span><span class="sxs-lookup"><span data-stu-id="380df-341">Add the Office 2016 App-V package and the plug-ins package you sequenced to the Connection Group you created.</span></span>

    ><span data-ttu-id="380df-342">**重要提示**连接组中的程序包顺序决定了程序包内容的合并顺序。</span><span class="sxs-lookup"><span data-stu-id="380df-342">**Important** The order of the packages in the Connection Group determines the order in which the package contents are merged.</span></span> <span data-ttu-id="380df-343">在连接组描述符文件中，首先添加 Office 2016 App-v 包，然后添加插件 App-v 包。</span><span class="sxs-lookup"><span data-stu-id="380df-343">In your Connection group descriptor file, add the Office 2016 App-V package first, and then add the plug-in App-V package.</span></span>



6.  <span data-ttu-id="380df-344">请确保将两个程序包都发布到目标计算机，并对该插件程序包进行全局发布，以匹配已发布的 Office 2016 App-v 程序包的全局设置。</span><span class="sxs-lookup"><span data-stu-id="380df-344">Ensure that both packages are published to the target computer and that the plug-in package is published globally to match the global settings of the published Office 2016 App-V package.</span></span>

7.  <span data-ttu-id="380df-345">验证插件程序包的部署配置文件是否具有 Office 2016 App-v 程序包所具有的相同设置。</span><span class="sxs-lookup"><span data-stu-id="380df-345">Verify that the Deployment Configuration File of the plug-in package has the same settings that the Office 2016 App-V package has.</span></span>

    <span data-ttu-id="380df-346">由于 Office 2016 App-v 程序包与操作系统集成，因此插件程序包设置应匹配。</span><span class="sxs-lookup"><span data-stu-id="380df-346">Since the Office 2016 App-V package is integrated with the operating system, the plug-in package settings should match.</span></span> <span data-ttu-id="380df-347">你可以搜索 "COM 模式" 的部署配置文件，并确保插件程序包的值设置为 "集成"，并且 "InProcessEnabled" 和 "OutOfProcessEnabled" 与你发布的 Office 2016 App-v 包的设置相匹配。</span><span class="sxs-lookup"><span data-stu-id="380df-347">You can search the Deployment Configuration File for “COM Mode” and ensure that your plug-ins package has that value set as “Integrated” and that both "InProcessEnabled" and "OutOfProcessEnabled" match the settings of the Office 2016 App-V package you published.</span></span>

8.  <span data-ttu-id="380df-348">打开部署配置文件，并将**对象**的值设置为 " **false**"。</span><span class="sxs-lookup"><span data-stu-id="380df-348">Open the Deployment Configuration File and set the value for **Objects Enabled** to **false**.</span></span>

9.  <span data-ttu-id="380df-349">如果在排序后对部署配置文件进行了任何更改，请确保插件程序包已与文件一起发布。</span><span class="sxs-lookup"><span data-stu-id="380df-349">If you made any changes to the Deployment Configuration file after sequencing, ensure that the plug-in package is published with the file.</span></span>

10. <span data-ttu-id="380df-350">确保你创建的连接组已启用到你所需的计算机。</span><span class="sxs-lookup"><span data-stu-id="380df-350">Ensure that the Connection Group you created is enabled onto your desired computer.</span></span> <span data-ttu-id="380df-351">如果启用了连接组，在使用 Office 2016 App-v 包时，创建的连接组可能会 "挂起"。</span><span class="sxs-lookup"><span data-stu-id="380df-351">The Connection Group created will likely “pend” if the Office 2016 App-V package is in use when the Connection Group is enabled.</span></span> <span data-ttu-id="380df-352">如果出现这种情况，您必须重新启动才能成功启用连接组。</span><span class="sxs-lookup"><span data-stu-id="380df-352">If that happens, you have to reboot to successfully enable the Connection Group.</span></span>

11. <span data-ttu-id="380df-353">成功发布这两个程序包并启用连接组后，启动目标 Office 2016 应用程序，并验证你发布并添加到连接组的插件是否按预期工作。</span><span class="sxs-lookup"><span data-stu-id="380df-353">After you successfully publish both packages and enable the Connection Group, start the target Office 2016 application and verify that the plug-in you published and added to the connection group works as expected.</span></span>

### <a href="" id="bkmk-disable-office-apps"></a><span data-ttu-id="380df-354">禁用 Office 2016 应用程序</span><span class="sxs-lookup"><span data-stu-id="380df-354">Disabling Office 2016 applications</span></span>

<span data-ttu-id="380df-355">你可能希望在 Office App-v 包中禁用特定应用程序。</span><span class="sxs-lookup"><span data-stu-id="380df-355">You may want to disable specific applications in your Office App-V package.</span></span> <span data-ttu-id="380df-356">例如，您可以禁用 Access，但仍可使用所有其他 Office 应用程序。</span><span class="sxs-lookup"><span data-stu-id="380df-356">For instance, you can disable Access, but leave all other Office application main available.</span></span> <span data-ttu-id="380df-357">禁用应用程序时，最终用户将不再看到该应用程序的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="380df-357">When you disable an application, the end user will no longer see the shortcut for that application.</span></span> <span data-ttu-id="380df-358">不必重新对应用程序进行排序。</span><span class="sxs-lookup"><span data-stu-id="380df-358">You do not have to re-sequence the application.</span></span> <span data-ttu-id="380df-359">当你在发布 Office 2016 App-v 包后更改部署配置文件时，你将保存所做的更改，添加 Office 2016 App-v 程序包，然后使用新的部署配置文件重新发布它，以将新设置应用到 Office 2016 App-v 程序包应用程序。</span><span class="sxs-lookup"><span data-stu-id="380df-359">When you change the Deployment Configuration File after the Office 2016 App-V package has been published, you will save the changes, add the Office 2016 App-V package, and then republish it with the new Deployment Configuration File to apply the new settings to Office 2016 App-V Package applications.</span></span>

><span data-ttu-id="380df-360">**注意**若要在使用 Office 部署工具创建 App-v 包时排除特定的 Office 应用程序（例如，Access 和 InfoPath），请使用**ExcludeApp**设置。</span><span class="sxs-lookup"><span data-stu-id="380df-360">**Note** To exclude specific Office applications (for example, Access and InfoPath) when you create the App-V package with the Office Deployment Tool, use the **ExcludeApp** setting.</span></span>


**<span data-ttu-id="380df-361">禁用 Office 2016 应用程序</span><span class="sxs-lookup"><span data-stu-id="380df-361">To disable an Office 2016 application</span></span>**

1.  <span data-ttu-id="380df-362">使用文本编辑器（如**记事本**）打开部署配置文件，然后搜索 "应用程序"。</span><span class="sxs-lookup"><span data-stu-id="380df-362">Open a Deployment Configuration File with a text editor such as **Notepad** and search for “Applications."</span></span>

2.  <span data-ttu-id="380df-363">搜索要禁用的 Office 应用程序，例如 Access 2016。</span><span class="sxs-lookup"><span data-stu-id="380df-363">Search for the Office application you want to disable, for example, Access 2016.</span></span>

3.  <span data-ttu-id="380df-364">将 "Enabled" 的值从 "true" 更改为 "false"。</span><span class="sxs-lookup"><span data-stu-id="380df-364">Change the value of "Enabled" from "true" to "false."</span></span>

4.  <span data-ttu-id="380df-365">保存部署配置文件。</span><span class="sxs-lookup"><span data-stu-id="380df-365">Save the Deployment Configuration File.</span></span>

5.  <span data-ttu-id="380df-366">将 Office 2016 App-v 包添加到新的部署配置文件。</span><span class="sxs-lookup"><span data-stu-id="380df-366">Add the Office 2016 App-V Package with the new Deployment Configuration File.</span></span>

    ```xml
    <Application Id="[{AppVPackageRoot}]\office16\lync.exe" Enabled="true">
      <VisualElements>
        <Name>Lync 2016</Name>
        <Icon />
        <Description />
      </VisualElements>
    </Application>
    <Application Id="[(AppVPackageRoot}]\office16\MSACCESS.EXE" Enabled="true">
      <VisualElements>
        <Name>Access 2016</Name>
        <Icon />
        <Description />
      </VisualElements>
    </Application>
    ```

6.  <span data-ttu-id="380df-367">重新添加 Office 2016 App-v 程序包，然后使用新的部署配置文件重新添加它，以将新设置应用于 Office 2016 App-v 程序包应用程序。</span><span class="sxs-lookup"><span data-stu-id="380df-367">Re-add the Office 2016 App-V package, and then republish it with the new Deployment Configuration File to apply the new settings to Office 2016 App-V Package applications.</span></span>

### <a href="" id="bkmk-disable-shortcuts"></a><span data-ttu-id="380df-368">禁用 Office 2016 快捷方式</span><span class="sxs-lookup"><span data-stu-id="380df-368">Disabling Office 2016 shortcuts</span></span>

<span data-ttu-id="380df-369">你可能希望禁用某些 Office 应用程序的快捷方式，而不是取消发布或删除程序包。</span><span class="sxs-lookup"><span data-stu-id="380df-369">You may want to disable shortcuts for certain Office applications instead of unpublishing or removing the package.</span></span> <span data-ttu-id="380df-370">以下示例显示了如何禁用 Microsoft Access 的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="380df-370">The following example shows how to disable shortcuts for Microsoft Access.</span></span>

**<span data-ttu-id="380df-371">禁用 Office 2016 应用程序的快捷方式</span><span class="sxs-lookup"><span data-stu-id="380df-371">To disable shortcuts for Office 2016 applications</span></span>**

1.  <span data-ttu-id="380df-372">在记事本中打开部署配置文件，然后搜索 "快捷方式"。</span><span class="sxs-lookup"><span data-stu-id="380df-372">Open a Deployment Configuration File in Notepad and search for “Shortcuts”.</span></span>

2.  <span data-ttu-id="380df-373">若要禁用某些快捷方式，请删除或注释掉不需要的特定快捷方式。</span><span class="sxs-lookup"><span data-stu-id="380df-373">To disable certain shortcuts, delete or comment out the specific shortcuts you don’t want.</span></span> <span data-ttu-id="380df-374">必须保持子系统存在且已启用。</span><span class="sxs-lookup"><span data-stu-id="380df-374">You must keep the subsystem present and enabled.</span></span> <span data-ttu-id="380df-375">例如，在下面的示例中，删除 Microsoft Access 快捷方式，让子系统 &lt; 快捷方式保持 &gt; &lt; 原样/shortcut， &gt; 以禁用 Microsoft Access 快捷方式。</span><span class="sxs-lookup"><span data-stu-id="380df-375">For example, in the example below, delete the Microsoft Access shortcuts, while keeping the subsystems &lt;shortcut&gt; &lt;/shortcut&gt; intact to disable the Microsoft Access shortcut.</span></span>

    ``` syntax
    Shortcuts

    -->
     <Shortcuts Enabled="true">
      <Extensions>
        <Extension Category="AppV.Shortcut">
          <Shortcut>
           <File>[{Common Programs}]\Microsoft Office 2016\Access 2016.lnk</File>
           <Target>[{AppvPackageRoot}])office16\MSACCESS.EXE</Target>
           <Icon>[{Windows}]\Installer\{90150000-000F-0000-0000-000000FF1CE)\accicons.exe.Ø.ico</Icon>
           <Arguments />
           <WorkingDirectory />
           <AppuserModelId>Microsoft.Office.MSACCESS.EXE.15</AppUserModelId>
           <AppUserModelExcludeFromShowInNewInstall>true</AppUserModelExcludeFromShowInNewInstall>
           <Description>Build a professional app quickly to manage data.</Description>
           <ShowCommand>l</ShowCommand>
           <ApplicationId>[{AppVPackageRoot}]\office16\MSACCESS.EXE</ApplicationId>
        </Shortcut>
    ```

3.  <span data-ttu-id="380df-376">保存部署配置文件。</span><span class="sxs-lookup"><span data-stu-id="380df-376">Save the Deployment Configuration File.</span></span>

4.  <span data-ttu-id="380df-377">通过新的部署配置文件重新发布 Office 2016 App-v 程序包。</span><span class="sxs-lookup"><span data-stu-id="380df-377">Republish Office 2016 App-V Package with new Deployment Configuration File.</span></span>

<span data-ttu-id="380df-378">通过修改 app-v 程序包的部署配置（例如文件类型关联、虚拟文件系统等），可以更改许多其他设置。</span><span class="sxs-lookup"><span data-stu-id="380df-378">Many additional settings can be changed through modifying the Deployment Configuration for App-V packages, for example, file type associations, Virtual File System, and more.</span></span> <span data-ttu-id="380df-379">有关如何使用部署配置文件更改 App-v 程序包设置的其他信息，请参阅本文档末尾的 "其他资源" 部分。</span><span class="sxs-lookup"><span data-stu-id="380df-379">For additional information on how to use Deployment Configuration Files to change App-V package settings, refer to the additional resources section at the end of this document.</span></span>

### <a href="" id="bkmk-manage-office-pkg-upgrd"></a><span data-ttu-id="380df-380">管理 Office 2016 程序包升级</span><span class="sxs-lookup"><span data-stu-id="380df-380">Managing Office 2016 package upgrades</span></span>

<span data-ttu-id="380df-381">若要升级 Office 2016 程序包，请使用 Office 部署工具。</span><span class="sxs-lookup"><span data-stu-id="380df-381">To upgrade an Office 2016 package, use the Office Deployment Tool.</span></span> <span data-ttu-id="380df-382">若要升级以前部署的 Office 2016 程序包，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="380df-382">To upgrade a previously deployed Office 2016 package, perform the following steps.</span></span>

**<span data-ttu-id="380df-383">如何升级以前部署的 Office 2016 程序包</span><span class="sxs-lookup"><span data-stu-id="380df-383">How to upgrade a previously deployed Office 2016 package</span></span>**

1. <span data-ttu-id="380df-384">通过 Office 部署工具创建新的 Office 2016 程序包，该工具使用最新的 Office 2016 应用程序软件。</span><span class="sxs-lookup"><span data-stu-id="380df-384">Create a new Office 2016 package through the Office Deployment Tool that uses the most recent Office 2016 application software.</span></span> <span data-ttu-id="380df-385">最新的 Office 2016 位始终可以通过创建 Office 2016 App-v 程序包的下载阶段获取。</span><span class="sxs-lookup"><span data-stu-id="380df-385">The most recent Office 2016 bits can always be obtained through the download stage of creating an Office 2016 App-V Package.</span></span> <span data-ttu-id="380df-386">新创建的 Office 2016 程序包将具有最新的更新和新的版本 ID。</span><span class="sxs-lookup"><span data-stu-id="380df-386">The newly created Office 2016 package will have the most recent updates and a new Version ID.</span></span> <span data-ttu-id="380df-387">使用 Office 部署工具创建的所有程序包都具有相同的沿袭。</span><span class="sxs-lookup"><span data-stu-id="380df-387">All packages created using the Office Deployment Tool have the same lineage.</span></span>

   > <span data-ttu-id="380df-388">**注意**Office App-V 程序包具有两个版本 Id：</span><span class="sxs-lookup"><span data-stu-id="380df-388">**Note** Office App-V packages have two Version IDs:</span></span>
   > <ul>
   > <li><span data-ttu-id="380df-389">Office 2016 App-V 程序包版本 ID 在使用 Office 部署工具创建的所有程序包中都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="380df-389">An Office 2016 App-V Package Version ID that is unique across all packages created using the Office Deployment Tool.</span></span></li>
   > <li><span data-ttu-id="380df-390">第二个 App-v 包版本 ID，例如，在 AppX 清单中，仅当存在新版本的 Office 时才会更改。</span><span class="sxs-lookup"><span data-stu-id="380df-390">A second App-V Package Version ID, x.x.x.x for example, in the AppX manifest that will only change if there is a new version of Office itself.</span></span> <span data-ttu-id="380df-391">例如，如果有新的支持升级的 Office 2016 版本，并且通过 Office 部署工具创建了一个程序包以合并这些升级，则 X.x.x.x 版本 ID 将会更改，以反映 Office 版本本身是否已更改。</span><span class="sxs-lookup"><span data-stu-id="380df-391">For example, if a new Office 2016 release with upgrades is available, and a package is created through the Office Deployment Tool to incorporate these upgrades, the X.X.X.X version ID will change to reflect that the Office version itself has changed.</span></span> <span data-ttu-id="380df-392">App-v 服务器将使用 X.x.x.x 版本 ID 来区分此程序包，并识别它是否包含以前发布的程序包的新升级，因此，将其发布为现有 Office 2016 程序包的升级。</span><span class="sxs-lookup"><span data-stu-id="380df-392">The App-V server will use the X.X.X.X version ID to differentiate this package and recognize that it contains new upgrades to the previously published package, and as a result, publish it as an upgrade to the existing Office 2016 package.</span></span></li>
   > </ul>


2. <span data-ttu-id="380df-393">将新创建的 Office 2016 App-v 包全局发布到要应用新更新的计算机上。</span><span class="sxs-lookup"><span data-stu-id="380df-393">Globally publish the newly created Office 2016 App-V Packages onto computers where you would like to apply the new updates.</span></span> <span data-ttu-id="380df-394">由于新的程序包具有较旧的 Office 2016 App-v 程序包的沿袭，因此发布包含更新的新程序包将仅对旧程序包应用新的更改，因此速度将很快。</span><span class="sxs-lookup"><span data-stu-id="380df-394">Since the new package has the same lineage of the older Office 2016 App-V Package, publishing the new package with the updates will only apply the new changes to the old package, and thus will be fast.</span></span>

3. <span data-ttu-id="380df-395">将采用与任何全局发布的 App-v 程序包相同的方式应用升级。</span><span class="sxs-lookup"><span data-stu-id="380df-395">Upgrades will be applied in the same manner of any globally published App-V Packages.</span></span> <span data-ttu-id="380df-396">由于应用程序可能正在使用，升级可能会延迟，直到重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="380df-396">Because applications will probably be in use, upgrades might be delayed until the computer is rebooted.</span></span>


### <a href="" id="bkmk-deploy-visio-project"></a><span data-ttu-id="380df-397">通过 Office 部署 Visio 2016 和 Project 2016</span><span class="sxs-lookup"><span data-stu-id="380df-397">Deploying Visio 2016 and Project 2016 with Office</span></span>

<span data-ttu-id="380df-398">下表介绍了通过 Office 部署 Visio 2016 和 Project 2016 的要求和选项。</span><span class="sxs-lookup"><span data-stu-id="380df-398">The following table describes the requirements and options for deploying Visio 2016 and Project 2016 with Office.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="380df-399">任务</span><span class="sxs-lookup"><span data-stu-id="380df-399">Task</span></span></th>
<th align="left"><span data-ttu-id="380df-400">详细信息</span><span class="sxs-lookup"><span data-stu-id="380df-400">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="380df-401">如何将 Visio 2016 和 Project 2016 打包并发布到 Office？</span><span class="sxs-lookup"><span data-stu-id="380df-401">How do I package and publish Visio 2016 and Project 2016 with Office?</span></span></p></td>
<td align="left"><p><span data-ttu-id="380df-402">您必须在同一程序包中包含 Visio 2016 和 Project 2016 和 Office。</span><span class="sxs-lookup"><span data-stu-id="380df-402">You must include Visio 2016 and Project 2016 in the same package with Office.</span></span></p>
<p><span data-ttu-id="380df-403">如果不部署 Office，则可以创建一个包含 Visio 和/或项目的程序包，前提是遵循本主题中所述的打包、发布和部署要求。</span><span class="sxs-lookup"><span data-stu-id="380df-403">If you aren’t deploying Office, you can create a package that contains Visio and/or Project, as long as you follow the packaging, publishing, and deployment requirements described in this topic.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="380df-404">如何将 Visio 2016 和 Project 2016 部署到特定用户？</span><span class="sxs-lookup"><span data-stu-id="380df-404">How can I deploy Visio 2016 and Project 2016 to specific users?</span></span></p></td>
<td align="left"><p><span data-ttu-id="380df-405">使用以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="380df-405">Use one of the following methods:</span></span></p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="380df-406">如果需要 .。。</span><span class="sxs-lookup"><span data-stu-id="380df-406">If you want to...</span></span></th>
<th align="left"><span data-ttu-id="380df-407">...然后使用此方法</span><span class="sxs-lookup"><span data-stu-id="380df-407">...then use this method</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="380df-408">创建两个不同的程序包，并将每个程序包部署到不同组的用户</span><span class="sxs-lookup"><span data-stu-id="380df-408">Create two different packages and deploy each one to a different group of users</span></span></p></td>
<td align="left"><p><span data-ttu-id="380df-409">创建和部署以下程序包：</span><span class="sxs-lookup"><span data-stu-id="380df-409">Create and deploy the following packages:</span></span></p>
<ul>
<li><p><span data-ttu-id="380df-410">仅包含 Office 部署到用户仅需要 Office 的计算机的程序包。</span><span class="sxs-lookup"><span data-stu-id="380df-410">A package that contains only Office - deploy to computers whose users need only Office.</span></span></p></li>
<li><p><span data-ttu-id="380df-411">包含 Office、Visio 和 Project-部署到用户需要所有三个应用程序的计算机的程序包。</span><span class="sxs-lookup"><span data-stu-id="380df-411">A package that contains Office, Visio, and Project - deploy to computers whose users need all three applications.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="380df-412">如果您只需要整个组织的一个程序包，或者如果您有共享计算机的用户，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="380df-412">If you want only one package for the whole organization, or if you have users who share computers:</span></span></p></td>
<td align="left"><p><span data-ttu-id="380df-413">按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="380df-413">Follows these steps:</span></span></p>
<ol>
<li><p><span data-ttu-id="380df-414">创建包含 Office、Visio 和 Project 的程序包。</span><span class="sxs-lookup"><span data-stu-id="380df-414">Create a package that contains Office, Visio, and Project.</span></span></p></li>
<li><p><span data-ttu-id="380df-415">将程序包部署到所有用户。</span><span class="sxs-lookup"><span data-stu-id="380df-415">Deploy the package to all users.</span></span></p></li>
<li><p><span data-ttu-id="380df-416">使用 <a href="https://technet.microsoft.com/library/dd723678.aspx" data-raw-source="[Microsoft AppLocker](https://technet.microsoft.com/library/dd723678.aspx)"> Microsoft AppLocker </a> 阻止特定用户使用 Visio 和 Project。</span><span class="sxs-lookup"><span data-stu-id="380df-416">Use <a href="https://technet.microsoft.com/library/dd723678.aspx" data-raw-source="[Microsoft AppLocker](https://technet.microsoft.com/library/dd723678.aspx)">Microsoft AppLocker</a> to prevent specific users from using Visio and Project.</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="380df-417">其他资源</span><span class="sxs-lookup"><span data-stu-id="380df-417">Additional resources</span></span>


[<span data-ttu-id="380df-418">使用 App-V 部署 Microsoft Office 2013</span><span class="sxs-lookup"><span data-stu-id="380df-418">Deploying Microsoft Office 2013 by Using App-V</span></span>](deploying-microsoft-office-2013-by-using-app-v.md)

[<span data-ttu-id="380df-419">使用 App-V 部署 Microsoft Office 2010</span><span class="sxs-lookup"><span data-stu-id="380df-419">Deploying Microsoft Office 2010 by Using App-V</span></span>](deploying-microsoft-office-2010-by-using-app-v.md)

[<span data-ttu-id="380df-420">Office 2016 的 "即点即用" 部署工具</span><span class="sxs-lookup"><span data-stu-id="380df-420">Office 2016 Deployment Tool for Click-to-Run</span></span>](https://www.microsoft.com/download/details.aspx?id=49117)

**<span data-ttu-id="380df-421">连接组</span><span class="sxs-lookup"><span data-stu-id="380df-421">Connection Groups</span></span>**

[<span data-ttu-id="380df-422">在 Microsoft App 中部署连接组-V v5</span><span class="sxs-lookup"><span data-stu-id="380df-422">Deploying Connection Groups in Microsoft App-V v5</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330683)

[<span data-ttu-id="380df-423">管理连接组</span><span class="sxs-lookup"><span data-stu-id="380df-423">Managing Connection Groups</span></span>](managing-connection-groups.md)

**<span data-ttu-id="380df-424">动态配置</span><span class="sxs-lookup"><span data-stu-id="380df-424">Dynamic Configuration</span></span>**

[<span data-ttu-id="380df-425">关于 App-V 5.1 动态配置</span><span class="sxs-lookup"><span data-stu-id="380df-425">About App-V 5.1 Dynamic Configuration</span></span>](about-app-v-51-dynamic-configuration.md)





