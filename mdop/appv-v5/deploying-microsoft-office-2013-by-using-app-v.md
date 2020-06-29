---
title: 使用 App-V 部署 Microsoft Office 2013
description: 使用 App-V 部署 Microsoft Office 2013
author: dansimp
ms.assetid: 02df5dc8-79e2-4c5c-8398-dbfb23344ab3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/02/2016
ms.openlocfilehash: c57227d531c61949f9160c27fc249db72dbc6523
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798594"
---
# <span data-ttu-id="8aa08-103">使用 App-V 部署 Microsoft Office 2013</span><span class="sxs-lookup"><span data-stu-id="8aa08-103">Deploying Microsoft Office 2013 by Using App-V</span></span>


<span data-ttu-id="8aa08-104">使用本文中的信息使用 Microsoft Application Virtualization 5.0 或更高版本，将 Microsoft Office 2013 作为虚拟化应用程序提供给组织中的计算机。</span><span class="sxs-lookup"><span data-stu-id="8aa08-104">Use the information in this article to use Microsoft Application Virtualization 5.0, or later versions, to deliver Microsoft Office 2013 as a virtualized application to computers in your organization.</span></span> <span data-ttu-id="8aa08-105">有关使用 app-v 交付 Office 2010 的信息，请参阅[使用 App-v 部署 Microsoft Office 2010](deploying-microsoft-office-2010-by-using-app-v.md)。</span><span class="sxs-lookup"><span data-stu-id="8aa08-105">For information about using App-V to deliver Office 2010, see [Deploying Microsoft Office 2010 by Using App-V](deploying-microsoft-office-2010-by-using-app-v.md).</span></span> <span data-ttu-id="8aa08-106">若要通过 App-v 成功部署 Office 2013，你需要熟悉 Office 2013 和 pp V。</span><span class="sxs-lookup"><span data-stu-id="8aa08-106">To successfully deploy Office 2013 with App-V, you need to be familiar with Office 2013 and pp-V.</span></span>

<span data-ttu-id="8aa08-107">本主题包含以下各节：</span><span class="sxs-lookup"><span data-stu-id="8aa08-107">This topic contains the following sections:</span></span>

-   [<span data-ttu-id="8aa08-108">开始之前需要了解的内容</span><span class="sxs-lookup"><span data-stu-id="8aa08-108">What to know before you start</span></span>](#bkmk-before-you-start)

-   [<span data-ttu-id="8aa08-109">使用 Office 部署工具为 App-v 创建 Office 2013 程序包</span><span class="sxs-lookup"><span data-stu-id="8aa08-109">Creating an Office 2013 package for App-V with the Office Deployment Tool</span></span>](#bkmk-create-office-pkg)

-   [<span data-ttu-id="8aa08-110">发布 app-v 5.0 的 Office 程序包</span><span class="sxs-lookup"><span data-stu-id="8aa08-110">Publishing the Office package for App-V 5.0</span></span>](#bkmk-pub-pkg-office)

-   [<span data-ttu-id="8aa08-111">自定义和管理 Office App-v 程序包</span><span class="sxs-lookup"><span data-stu-id="8aa08-111">Customizing and managing Office App-V packages</span></span>](#bkmk-custmz-manage-office-pkgs)

## <a href="" id="bkmk-before-you-start"></a><span data-ttu-id="8aa08-112">开始之前需要了解的内容</span><span class="sxs-lookup"><span data-stu-id="8aa08-112">What to know before you start</span></span>


<span data-ttu-id="8aa08-113">通过使用 App-v 部署 Office 2013 之前，请查看以下计划信息。</span><span class="sxs-lookup"><span data-stu-id="8aa08-113">Before you deploy Office 2013 by using App-V, review the following planning information.</span></span>

### <a href="" id="bkmk-supp-vers-coexist"></a><span data-ttu-id="8aa08-114">支持的 Office 版本和 Office 共存</span><span class="sxs-lookup"><span data-stu-id="8aa08-114">Supported Office versions and Office coexistence</span></span>

<span data-ttu-id="8aa08-115">使用下表获取有关受支持的 Office 版本的信息，以及有关运行版本更共存的 Office 的信息。</span><span class="sxs-lookup"><span data-stu-id="8aa08-115">Use the following table to get information about supported versions of Office and about running coexisting versions of Office.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8aa08-116">要查看的信息</span><span class="sxs-lookup"><span data-stu-id="8aa08-116">Information to review</span></span></th>
<th align="left"><span data-ttu-id="8aa08-117">描述</span><span class="sxs-lookup"><span data-stu-id="8aa08-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="planning-for-using-app-v-with-office.md#bkmk-office-vers-supp-appv" data-raw-source="[Planning for Using App-V with Office](planning-for-using-app-v-with-office.md#bkmk-office-vers-supp-appv)"><span data-ttu-id="8aa08-118">计划将 App-V 与 Office 结合使用</span><span class="sxs-lookup"><span data-stu-id="8aa08-118">Planning for Using App-V with Office</span></span></a></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="8aa08-119">支持的 Office 版本</span><span class="sxs-lookup"><span data-stu-id="8aa08-119">Supported versions of Office</span></span></p></li>
<li><p><span data-ttu-id="8aa08-120">支持的部署类型（例如，桌面、个人虚拟桌面基础结构（VDI）、共用 VDI）</span><span class="sxs-lookup"><span data-stu-id="8aa08-120">Supported deployment types (for example, desktop, personal Virtual Desktop Infrastructure (VDI), pooled VDI)</span></span></p></li>
<li><p><span data-ttu-id="8aa08-121">Office 授权选项</span><span class="sxs-lookup"><span data-stu-id="8aa08-121">Office licensing options</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><a href="planning-for-using-app-v-with-office.md#bkmk-plan-coexisting" data-raw-source="[Planning for Using App-V with Office](planning-for-using-app-v-with-office.md#bkmk-plan-coexisting)"><span data-ttu-id="8aa08-122">计划将 App-V 与 Office 结合使用</span><span class="sxs-lookup"><span data-stu-id="8aa08-122">Planning for Using App-V with Office</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="8aa08-123">在同一台计算机上安装不同版本的 Office 时的注意事项</span><span class="sxs-lookup"><span data-stu-id="8aa08-123">Considerations for installing different versions of Office on the same computer</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-pkg-pub-reqs"></a><span data-ttu-id="8aa08-124">打包、发布和部署要求</span><span class="sxs-lookup"><span data-stu-id="8aa08-124">Packaging, publishing, and deployment requirements</span></span>

<span data-ttu-id="8aa08-125">通过使用 App-v 部署 Office 之前，请查看以下要求。</span><span class="sxs-lookup"><span data-stu-id="8aa08-125">Before you deploy Office by using App-V, review the following requirements.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8aa08-126">任务</span><span class="sxs-lookup"><span data-stu-id="8aa08-126">Task</span></span></th>
<th align="left"><span data-ttu-id="8aa08-127">要求</span><span class="sxs-lookup"><span data-stu-id="8aa08-127">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8aa08-128">包装</span><span class="sxs-lookup"><span data-stu-id="8aa08-128">Packaging</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="8aa08-129">要部署到用户的所有 Office 应用程序都必须位于单个程序包中。</span><span class="sxs-lookup"><span data-stu-id="8aa08-129">All of the Office applications that you want to deploy to users must be in a single package.</span></span></p></li>
<li><p><span data-ttu-id="8aa08-130">在 app-v 5.0 和更高版本中，必须使用 Office 部署工具创建程序包。</span><span class="sxs-lookup"><span data-stu-id="8aa08-130">In App-V 5.0 and later, you must use the Office Deployment Tool to create packages.</span></span> <span data-ttu-id="8aa08-131">不能使用 Sequencer。</span><span class="sxs-lookup"><span data-stu-id="8aa08-131">You cannot use the Sequencer.</span></span></p></li>
<li><p><span data-ttu-id="8aa08-132">如果要在 Office 中部署 Microsoft Visio 2013 和 Microsoft Project 2013，则必须将它们包含在与 Office 相同的程序包中。</span><span class="sxs-lookup"><span data-stu-id="8aa08-132">If you are deploying Microsoft Visio 2013 and Microsoft Project 2013 along with Office, you must include them in the same package with Office.</span></span> <span data-ttu-id="8aa08-133">有关详细信息，请参阅 <a href="#bkmk-deploy-visio-project" data-raw-source="[Deploying Visio 2013 and Project 2013 with Office](#bkmk-deploy-visio-project)"> 通过 Office 部署 Visio 2013 和 Project 2013 </a> 。</span><span class="sxs-lookup"><span data-stu-id="8aa08-133">For more information, see <a href="#bkmk-deploy-visio-project" data-raw-source="[Deploying Visio 2013 and Project 2013 with Office](#bkmk-deploy-visio-project)">Deploying Visio 2013 and Project 2013 with Office</a>.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8aa08-134">发布</span><span class="sxs-lookup"><span data-stu-id="8aa08-134">Publishing</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="8aa08-135">您只能将一个 Office 程序包发布到每台客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="8aa08-135">You can publish only one Office package to each client computer.</span></span></p></li>
<li><p><span data-ttu-id="8aa08-136">您必须全局发布 Office 程序包。</span><span class="sxs-lookup"><span data-stu-id="8aa08-136">You must publish the Office package globally.</span></span> <span data-ttu-id="8aa08-137">您不能发布给用户。</span><span class="sxs-lookup"><span data-stu-id="8aa08-137">You cannot publish to the user.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8aa08-138">通过使用远程桌面服务将以下任何产品部署到共享计算机：</span><span class="sxs-lookup"><span data-stu-id="8aa08-138">Deploying any of the following products to a shared computer, for example, by using Remote Desktop Services:</span></span></p>
<ul>
<li><p><span data-ttu-id="8aa08-139">适用于企业的 Microsoft 365 应用</span><span class="sxs-lookup"><span data-stu-id="8aa08-139">Microsoft 365 Apps for enterprise</span></span></p></li>
<li><p><span data-ttu-id="8aa08-140">Visio Pro for Office 365</span><span class="sxs-lookup"><span data-stu-id="8aa08-140">Visio Pro for Office 365</span></span></p></li>
<li><p><span data-ttu-id="8aa08-141">Project Pro for Office 365</span><span class="sxs-lookup"><span data-stu-id="8aa08-141">Project Pro for Office 365</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="8aa08-142">您必须启用 <a href="https://technet.microsoft.com/library/dn782860.aspx" data-raw-source="[shared computer activation](https://technet.microsoft.com/library/dn782860.aspx)"> 共享计算机激活 </a> 。</span><span class="sxs-lookup"><span data-stu-id="8aa08-142">You must enable <a href="https://technet.microsoft.com/library/dn782860.aspx" data-raw-source="[shared computer activation](https://technet.microsoft.com/library/dn782860.aspx)">shared computer activation</a>.</span></span></p>
<p><span data-ttu-id="8aa08-143">如果你要部署批量许可产品，则不使用共享计算机激活，例如：</span><span class="sxs-lookup"><span data-stu-id="8aa08-143">You don’t use shared computer activation if you’re deploying a volume licensed product, such as:</span></span></p>
<ul>
<li><p><span data-ttu-id="8aa08-144">Office 专业增强版2013</span><span class="sxs-lookup"><span data-stu-id="8aa08-144">Office Professional Plus 2013</span></span></p></li>
<li><p><span data-ttu-id="8aa08-145">Visio Professional 2013</span><span class="sxs-lookup"><span data-stu-id="8aa08-145">Visio Professional 2013</span></span></p></li>
<li><p><span data-ttu-id="8aa08-146">Project Professional 2013</span><span class="sxs-lookup"><span data-stu-id="8aa08-146">Project Professional 2013</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="8aa08-147">从程序包中排除 Office 应用程序</span><span class="sxs-lookup"><span data-stu-id="8aa08-147">Excluding Office applications from a package</span></span>

<span data-ttu-id="8aa08-148">下表介绍了从程序包中排除特定 Office 应用程序的推荐方法。</span><span class="sxs-lookup"><span data-stu-id="8aa08-148">The following table describes the recommended methods for excluding specific Office applications from a package.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8aa08-149">任务</span><span class="sxs-lookup"><span data-stu-id="8aa08-149">Task</span></span></th>
<th align="left"><span data-ttu-id="8aa08-150">详细信息</span><span class="sxs-lookup"><span data-stu-id="8aa08-150">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8aa08-151">使用 <strong> </strong> Office 部署工具创建程序包时，请使用 ExcludeApp 设置。</span><span class="sxs-lookup"><span data-stu-id="8aa08-151">Use the <strong>ExcludeApp</strong> setting when you create the package by using the Office Deployment Tool.</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="8aa08-152">使你能够在 Office 部署工具创建程序包时从程序包中排除特定的 Office 应用程序。</span><span class="sxs-lookup"><span data-stu-id="8aa08-152">Enables you to exclude specific Office applications from the package when the Office Deployment Tool creates the package.</span></span> <span data-ttu-id="8aa08-153">例如，你可以使用此设置创建仅包含 Microsoft Word 的程序包。</span><span class="sxs-lookup"><span data-stu-id="8aa08-153">For example, you can use this setting to create a package that contains only Microsoft Word.</span></span></p></li>
<li><p><span data-ttu-id="8aa08-154">有关详细信息，请参阅 <a href="https://technet.microsoft.com/library/jj219426.aspx#bkmk-excludeappelement" data-raw-source="[ExcludeApp element](https://technet.microsoft.com/library/jj219426.aspx#bkmk-excludeappelement)"> ExcludeApp 元素 </a> 。</span><span class="sxs-lookup"><span data-stu-id="8aa08-154">For more information, see <a href="https://technet.microsoft.com/library/jj219426.aspx#bkmk-excludeappelement" data-raw-source="[ExcludeApp element](https://technet.microsoft.com/library/jj219426.aspx#bkmk-excludeappelement)">ExcludeApp element</a>.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8aa08-155">修改 DeploymentConfig.xml 文件</span><span class="sxs-lookup"><span data-stu-id="8aa08-155">Modify the DeploymentConfig.xml file</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="8aa08-156">创建程序包后修改 DeploymentConfig.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="8aa08-156">Modify the DeploymentConfig.xml file after the package has been created.</span></span> <span data-ttu-id="8aa08-157">此文件包含运行 App-V 客户端的计算机上所有用户的默认程序包设置。</span><span class="sxs-lookup"><span data-stu-id="8aa08-157">This file contains the default package settings for all users on a computer that is running the App-V Client.</span></span></p></li>
<li><p><span data-ttu-id="8aa08-158">有关详细信息，请参阅 <a href="#bkmk-disable-office-apps" data-raw-source="[Disabling Office 2013 applications](#bkmk-disable-office-apps)"> 禁用 Office 2013 应用程序 </a> 。</span><span class="sxs-lookup"><span data-stu-id="8aa08-158">For more information, see <a href="#bkmk-disable-office-apps" data-raw-source="[Disabling Office 2013 applications](#bkmk-disable-office-apps)">Disabling Office 2013 applications</a>.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-create-office-pkg"></a><span data-ttu-id="8aa08-159">使用 Office 部署工具为 App-v 创建 Office 2013 程序包</span><span class="sxs-lookup"><span data-stu-id="8aa08-159">Creating an Office 2013 package for App-V with the Office Deployment Tool</span></span>


<span data-ttu-id="8aa08-160">完成以下步骤，为 App-v 5.0 或更高版本创建 Office 2013 程序包。</span><span class="sxs-lookup"><span data-stu-id="8aa08-160">Complete the following steps to create an Office 2013 package for App-V 5.0 or later.</span></span>

**<span data-ttu-id="8aa08-161">重要提示</span><span class="sxs-lookup"><span data-stu-id="8aa08-161">Important</span></span>**  
<span data-ttu-id="8aa08-162">在 app-v 5.0 和更高版本中，你必须使用 Office 部署工具来创建程序包。</span><span class="sxs-lookup"><span data-stu-id="8aa08-162">In App-V 5.0 and later, you must the Office Deployment Tool to create a package.</span></span> <span data-ttu-id="8aa08-163">不能使用 Sequencer 创建程序包。</span><span class="sxs-lookup"><span data-stu-id="8aa08-163">You cannot use the Sequencer to create packages.</span></span>


### <span data-ttu-id="8aa08-164">查看使用 Office 部署工具的先决条件</span><span class="sxs-lookup"><span data-stu-id="8aa08-164">Review prerequisites for using the Office Deployment Tool</span></span>

<span data-ttu-id="8aa08-165">安装 Office 部署工具的计算机必须具有：</span><span class="sxs-lookup"><span data-stu-id="8aa08-165">The computer on which you are installing the Office Deployment Tool must have:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8aa08-166">必备</span><span class="sxs-lookup"><span data-stu-id="8aa08-166">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="8aa08-167">描述</span><span class="sxs-lookup"><span data-stu-id="8aa08-167">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8aa08-168">必备软件</span><span class="sxs-lookup"><span data-stu-id="8aa08-168">Prerequisite software</span></span></p></td>
<td align="left"><p><span data-ttu-id="8aa08-169">.Net Framework 4</span><span class="sxs-lookup"><span data-stu-id="8aa08-169">.Net Framework 4</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8aa08-170">支持的操作系统</span><span class="sxs-lookup"><span data-stu-id="8aa08-170">Supported operating systems</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="8aa08-171">64位版本的 Windows 8</span><span class="sxs-lookup"><span data-stu-id="8aa08-171">64-bit version of Windows 8</span></span></p></li>
<li><p><span data-ttu-id="8aa08-172">64位版本的 Windows 7</span><span class="sxs-lookup"><span data-stu-id="8aa08-172">64-bit version of Windows 7</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


**<span data-ttu-id="8aa08-173">注意</span><span class="sxs-lookup"><span data-stu-id="8aa08-173">Note</span></span>**  
<span data-ttu-id="8aa08-174">在本主题中，术语 "Office 2013 App-v 程序包" 是指订阅许可和批量许可。</span><span class="sxs-lookup"><span data-stu-id="8aa08-174">In this topic, the term “Office 2013 App-V package” refers to subscription licensing and volume licensing.</span></span>


### <span data-ttu-id="8aa08-175">使用 Office 部署工具创建 Office 2013 App-v 程序包</span><span class="sxs-lookup"><span data-stu-id="8aa08-175">Create Office 2013 App-V Packages Using Office Deployment Tool</span></span>

<span data-ttu-id="8aa08-176">使用 Office 部署工具创建 Office 2013 App-v 程序包。</span><span class="sxs-lookup"><span data-stu-id="8aa08-176">You create Office 2013 App-V packages by using the Office Deployment Tool.</span></span> <span data-ttu-id="8aa08-177">以下说明介绍了如何使用批量许可或订阅授权创建 Office 2013 App-v 程序包。</span><span class="sxs-lookup"><span data-stu-id="8aa08-177">The following instructions explain how to create an Office 2013 App-V package with Volume Licensing or Subscription Licensing.</span></span>

<span data-ttu-id="8aa08-178">在64位 Windows 计算机上创建 Office 2013 App-v 包。</span><span class="sxs-lookup"><span data-stu-id="8aa08-178">Create Office 2013 App-V packages on 64-bit Windows computers.</span></span> <span data-ttu-id="8aa08-179">创建后，Office 2013 App-v 包将在32位和64位 Windows 7 和 Windows 8 计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="8aa08-179">Once created, the Office 2013 App-V package will run on 32-bit and 64-bit Windows 7 and Windows 8 computers.</span></span>

### <span data-ttu-id="8aa08-180">下载 Office 部署工具</span><span class="sxs-lookup"><span data-stu-id="8aa08-180">Download the Office Deployment Tool</span></span>

<span data-ttu-id="8aa08-181">Office 2013 App-v 程序包是使用 Office 部署工具创建的，该工具生成 Office 2013 App-v 包。</span><span class="sxs-lookup"><span data-stu-id="8aa08-181">Office 2013 App-V Packages are created using the Office Deployment Tool, which generates an Office 2013 App-V Package.</span></span> <span data-ttu-id="8aa08-182">无法通过 App-v sequencer 创建或修改程序包。</span><span class="sxs-lookup"><span data-stu-id="8aa08-182">The package cannot be created or modified through the App-V sequencer.</span></span> <span data-ttu-id="8aa08-183">要开始创建软件包，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8aa08-183">To begin package creation:</span></span>

1.  <span data-ttu-id="8aa08-184">下载[Office 部署工具以进行即点](https://www.microsoft.com/download/details.aspx?id=36778)即用。</span><span class="sxs-lookup"><span data-stu-id="8aa08-184">Download the [Office Deployment Tool for Click-to-Run](https://www.microsoft.com/download/details.aspx?id=36778).</span></span>

2.  <span data-ttu-id="8aa08-185">运行 .exe 文件，并将其功能提取到所需位置。</span><span class="sxs-lookup"><span data-stu-id="8aa08-185">Run the .exe file and extract its features into the desired location.</span></span> <span data-ttu-id="8aa08-186">若要使此过程更简单，您可以创建将保存功能的共享网络文件夹。</span><span class="sxs-lookup"><span data-stu-id="8aa08-186">To make this process easier, you can create a shared network folder where the features will be saved.</span></span>

    <span data-ttu-id="8aa08-187">示例： \\\\Server\\Office2013</span><span class="sxs-lookup"><span data-stu-id="8aa08-187">Example: \\\\Server\\Office2013</span></span>

3.  <span data-ttu-id="8aa08-188">检查 setup.exe 和 configuration.xml 文件是否存在以及是否位于指定的位置。</span><span class="sxs-lookup"><span data-stu-id="8aa08-188">Check that a setup.exe and a configuration.xml file exist and are in the location you specified.</span></span>

### <span data-ttu-id="8aa08-189">下载 Office 2013 应用程序</span><span class="sxs-lookup"><span data-stu-id="8aa08-189">Download Office 2013 applications</span></span>

<span data-ttu-id="8aa08-190">下载 Office 部署工具后，您可以使用它来获取最新的 Office 2013 应用程序。</span><span class="sxs-lookup"><span data-stu-id="8aa08-190">After you download the Office Deployment Tool, you can use it to get the latest Office 2013 applications.</span></span> <span data-ttu-id="8aa08-191">获取 Office 应用程序后，创建 Office 2013 App-v 包。</span><span class="sxs-lookup"><span data-stu-id="8aa08-191">After getting the Office applications, you create the Office 2013 App-V package.</span></span>

<span data-ttu-id="8aa08-192">Office 部署工具中包含的 XML 文件指定产品详细信息，如所含语言和 Office 应用程序。</span><span class="sxs-lookup"><span data-stu-id="8aa08-192">The XML file that is included in the Office Deployment Tool specifies the product details, such as the languages and Office applications included.</span></span>

1. <span data-ttu-id="8aa08-193">**自定义示例 XML 配置文件：** 使用您使用 Office 部署工具下载的示例 XML 配置文件自定义 Office 应用程序：</span><span class="sxs-lookup"><span data-stu-id="8aa08-193">**Customize the sample XML configuration file:** Use the sample XML configuration file that you downloaded with the Office Deployment Tool to customize the Office applications:</span></span>

   1. <span data-ttu-id="8aa08-194">在记事本或你喜爱的文本编辑器中打开示例 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="8aa08-194">Open the sample XML file in Notepad or your favorite text editor.</span></span>

   2. <span data-ttu-id="8aa08-195">示例 configuration.xml 文件打开并准备好进行编辑后，您可以指定产品、语言和保存 Office 2013 应用程序的路径。</span><span class="sxs-lookup"><span data-stu-id="8aa08-195">With the sample configuration.xml file open and ready for editing, you can specify products, languages, and the path to which you save the Office 2013 applications.</span></span> <span data-ttu-id="8aa08-196">下面是 configuration.xml 文件的基本示例：</span><span class="sxs-lookup"><span data-stu-id="8aa08-196">The following is a basic example of the configuration.xml file:</span></span>

      ```xml
      <Configuration>
         <Add SourcePath= ”\\Server\Office2013” OfficeClientEdition="32" >
          <Product ID="O365ProPlusRetail ">
            <Language ID="en-us" />
          </Product>
          <Product ID="VisioProRetail">
            <Language ID="en-us" />
          </Product>
        </Add>
      </Configuration>
      ```

      **<span data-ttu-id="8aa08-197">注意</span><span class="sxs-lookup"><span data-stu-id="8aa08-197">Note</span></span>**  
      <span data-ttu-id="8aa08-198">配置 XML 是一个示例 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="8aa08-198">The configuration XML is a sample XML file.</span></span> <span data-ttu-id="8aa08-199">该文件包含注释掉的行。你可以 "取消注释" 这些行以自定义文件的其他设置。</span><span class="sxs-lookup"><span data-stu-id="8aa08-199">The file includes lines that are commented out. You can “uncomment” these lines to customize additional settings with the file.</span></span>

      <span data-ttu-id="8aa08-200">以上 XML 配置文件指定 Office 2013 专业增强版32位版本（包括 Visio 专业增强版）将以英语下载到 \\\\server\\Office 2013，该版本是 Office 应用程序将保存到的位置。</span><span class="sxs-lookup"><span data-stu-id="8aa08-200">The above XML configuration file specifies that Office 2013 ProPlus 32-bit edition, including Visio ProPlus, will be downloaded in English to the \\\\server\\Office 2013, which is the location where Office applications will be saved to.</span></span> <span data-ttu-id="8aa08-201">请注意，应用程序的产品 ID 不会影响 Office 的最终许可。</span><span class="sxs-lookup"><span data-stu-id="8aa08-201">Note that the Product ID of the applications will not affect the final licensing of Office.</span></span> <span data-ttu-id="8aa08-202">通过在更高阶段指定授权，可以从相同的应用程序创建具有各种许可的 Office 2013 App-v 程序包。</span><span class="sxs-lookup"><span data-stu-id="8aa08-202">Office 2013 App-V packages with various licensing can be created from the same applications through specifying licensing in a later stage.</span></span> <span data-ttu-id="8aa08-203">下表总结了 XML 文件的可自定义属性和元素：</span><span class="sxs-lookup"><span data-stu-id="8aa08-203">The table below summarizes the customizable attributes and elements of XML file:</span></span>

      <table>
      <colgroup>
      <col width="33%" />
      <col width="33%" />
      <col width="33%" />
      </colgroup>
      <thead>
      <tr class="header">
      <th align="left"><span data-ttu-id="8aa08-204">输入</span><span class="sxs-lookup"><span data-stu-id="8aa08-204">Input</span></span></th>
      <th align="left"><span data-ttu-id="8aa08-205">说明</span><span class="sxs-lookup"><span data-stu-id="8aa08-205">Description</span></span></th>
      <th align="left"><span data-ttu-id="8aa08-206">示例</span><span class="sxs-lookup"><span data-stu-id="8aa08-206">Example</span></span></th>
      </tr>
      </thead>
      <tbody>
      <tr class="odd">
      <td align="left"><p><span data-ttu-id="8aa08-207">添加元素</span><span class="sxs-lookup"><span data-stu-id="8aa08-207">Add element</span></span></p></td>
      <td align="left"><p><span data-ttu-id="8aa08-208">指定要包含在程序包中的产品和语言。</span><span class="sxs-lookup"><span data-stu-id="8aa08-208">Specifies the products and languages to include in the package.</span></span></p></td>
      <td align="left"><p><span data-ttu-id="8aa08-209">不适用</span><span class="sxs-lookup"><span data-stu-id="8aa08-209">N/A</span></span></p></td>
      </tr>
      <tr class="even">
      <td align="left"><p><span data-ttu-id="8aa08-210">OfficeClientEdition （Add 元素的属性）</span><span class="sxs-lookup"><span data-stu-id="8aa08-210">OfficeClientEdition (attribute of Add element)</span></span></p></td>
      <td align="left"><p><span data-ttu-id="8aa08-211">指定要使用的 Office 2013 产品的版本：32位或64位。</span><span class="sxs-lookup"><span data-stu-id="8aa08-211">Specifies the edition of Office 2013 product to use: 32-bit or 64-bit.</span></span> <span data-ttu-id="8aa08-212">如果 <strong> OfficeClientEdition 未设置为有效值，则操作将失败 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="8aa08-212">The operation fails if <strong>OfficeClientEdition</strong> is not set to a valid value.</span></span></p></td>
      <td align="left"><p><strong><span data-ttu-id="8aa08-213">OfficeClientEdition </strong> = &quot; 32&quot;</span><span class="sxs-lookup"><span data-stu-id="8aa08-213">OfficeClientEdition</strong>=&quot;32&quot;</span></span></p>
      <p><strong><span data-ttu-id="8aa08-214">OfficeClientEdition </strong> = &quot; 64&quot;</span><span class="sxs-lookup"><span data-stu-id="8aa08-214">OfficeClientEdition</strong>=&quot;64&quot;</span></span></p></td>
      </tr>
      <tr class="odd">
      <td align="left"><p><span data-ttu-id="8aa08-215">Product 元素</span><span class="sxs-lookup"><span data-stu-id="8aa08-215">Product element</span></span></p></td>
      <td align="left"><p><span data-ttu-id="8aa08-216">指定应用程序。</span><span class="sxs-lookup"><span data-stu-id="8aa08-216">Specifies the application.</span></span> <span data-ttu-id="8aa08-217">必须在此处将 Project 2013 和 Visio 2013 指定为应用程序中包含的已添加产品。</span><span class="sxs-lookup"><span data-stu-id="8aa08-217">Project 2013 and Visio 2013 must be specified here as an added product to be included in the applications.</span></span></p></td>
      <td align="left"><p><code>Product ID =&quot;O365ProPlusRetail &quot;</code></p>
      <p><code>Product ID =&quot;VisioProRetail&quot;</code></p>
      <p><code>Product ID =&quot;ProjectProRetail&quot;</code></p>
      <p><code>Product ID =&quot;ProPlusVolume&quot;</code></p>
      <p><code>Product ID =&quot;VisioProVolume&quot;</code></p>
      <p><code>Product ID = &quot;ProjectProVolume&quot;</code></p></td>
      </tr>
      <tr class="even">
      <td align="left"><p><span data-ttu-id="8aa08-218">语言元素</span><span class="sxs-lookup"><span data-stu-id="8aa08-218">Language element</span></span></p></td>
      <td align="left"><p><span data-ttu-id="8aa08-219">指定应用程序中支持的语言</span><span class="sxs-lookup"><span data-stu-id="8aa08-219">Specifies the language supported in the applications</span></span></p></td>
      <td align="left"><p><code>Language ID=&quot;en-us&quot;</code></p></td>
      </tr>
      <tr class="odd">
      <td align="left"><p><span data-ttu-id="8aa08-220">版本（Add 元素的属性）</span><span class="sxs-lookup"><span data-stu-id="8aa08-220">Version (attribute of Add element)</span></span></p></td>
      <td align="left"><p><span data-ttu-id="8aa08-221">可选。</span><span class="sxs-lookup"><span data-stu-id="8aa08-221">Optional.</span></span> <span data-ttu-id="8aa08-222">指定要用于程序包的版本</span><span class="sxs-lookup"><span data-stu-id="8aa08-222">Specifies a build to use for the package</span></span></p>
      <p><span data-ttu-id="8aa08-223">默认为最新播发版本（在 Office 源 v32.CAB 中定义）。</span><span class="sxs-lookup"><span data-stu-id="8aa08-223">Defaults to latest advertised build (as defined in v32.CAB at the Office source).</span></span></p></td>
      <td align="left"><p><code>15.1.2.3</code></p></td>
      </tr>
      <tr class="even">
      <td align="left"><p><span data-ttu-id="8aa08-224">SourcePath （Add 元素的属性）</span><span class="sxs-lookup"><span data-stu-id="8aa08-224">SourcePath (attribute of Add element)</span></span></p></td>
      <td align="left"><p><span data-ttu-id="8aa08-225">指定应用程序将保存到的位置。</span><span class="sxs-lookup"><span data-stu-id="8aa08-225">Specifies the location in which the applications will be saved to.</span></span></p></td>
      <td align="left"><p><code>Sourcepath = &quot;\Server\Office2013”</code></p></td>
      </tr>
      </tbody>
      </table>

      <span data-ttu-id="8aa08-226">编辑 configuration.xml 文件以指定所需的产品、语言以及 Office 2013 应用程序将保存到的位置时，可以保存配置文件，例如 Customconfig.xml。</span><span class="sxs-lookup"><span data-stu-id="8aa08-226">After editing the configuration.xml file to specify the desired product, languages, and also the location which the Office 2013 applications will be saved onto, you can save the configuration file, for example, as Customconfig.xml.</span></span>

2. <span data-ttu-id="8aa08-227">将**应用程序下载到指定位置：** 使用提升的命令提示符和64位操作系统下载稍后将转换为 App-v 包的 Office 2013 应用程序。</span><span class="sxs-lookup"><span data-stu-id="8aa08-227">**Download the applications into the specified location:** Use an elevated command prompt and a 64 bit operating system to download the Office 2013 applications that will later be converted into an App-V package.</span></span> <span data-ttu-id="8aa08-228">下面是包含详细信息说明的示例命令：</span><span class="sxs-lookup"><span data-stu-id="8aa08-228">Below is an example command with description of details:</span></span>

   ``` syntax
   \\server\Office2013\setup.exe /download \\server\Office2013\Customconfig.xml
   ```

   <span data-ttu-id="8aa08-229">在示例中：</span><span class="sxs-lookup"><span data-stu-id="8aa08-229">In the example:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="8aa08-230">\server\Office2013</span><span class="sxs-lookup"><span data-stu-id="8aa08-230">\server\Office2013</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="8aa08-231">是包含 Office 部署工具和自定义 Configuration.xml 文件的网络共享位置 Customconfig.xml。</span><span class="sxs-lookup"><span data-stu-id="8aa08-231">is the network share location that contains the Office Deployment Tool and the custom Configuration.xml file, Customconfig.xml.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="8aa08-232">Setup.exe</span><span class="sxs-lookup"><span data-stu-id="8aa08-232">Setup.exe</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="8aa08-233">是 Office 部署工具。</span><span class="sxs-lookup"><span data-stu-id="8aa08-233">is the Office Deployment Tool.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="8aa08-234">/download</span><span class="sxs-lookup"><span data-stu-id="8aa08-234">/download</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="8aa08-235">下载在 customConfig.xml 文件中指定的 Office 2013 应用程序。</span><span class="sxs-lookup"><span data-stu-id="8aa08-235">downloads the Office 2013 applications that you specify in the customConfig.xml file.</span></span> <span data-ttu-id="8aa08-236">这些位可以在使用批量许可的 Office 2013 App-v 包中转换。</span><span class="sxs-lookup"><span data-stu-id="8aa08-236">These bits can be later converted in an Office 2013 App-V package with Volume Licensing.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="8aa08-237">\server\Office2013\Customconfig.xml</span><span class="sxs-lookup"><span data-stu-id="8aa08-237">\server\Office2013\Customconfig.xml</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="8aa08-238">传递完成下载过程所需的 XML 配置文件，在本示例中 customconfig.xml。</span><span class="sxs-lookup"><span data-stu-id="8aa08-238">passes the XML configuration file required to complete the download process, in this example, customconfig.xml.</span></span> <span data-ttu-id="8aa08-239">使用 "下载" 命令后，应在配置 xml 文件中指定的位置找到 Office 应用程序，本例中为 \Server\Office2013。</span><span class="sxs-lookup"><span data-stu-id="8aa08-239">After using the download command, Office applications should be found in the location specified in the configuration xml file, in this example \Server\Office2013.</span></span></p></td>
   </tr>
   </tbody>
   </table>



### <span data-ttu-id="8aa08-240">将 Office 应用程序转换为 App-v 包</span><span class="sxs-lookup"><span data-stu-id="8aa08-240">Convert the Office applications into an App-V package</span></span>

<span data-ttu-id="8aa08-241">通过 Office 部署工具下载 Office 2013 应用程序后，请使用 Office 部署工具将它们转换为 Office 2013 App-v 包。</span><span class="sxs-lookup"><span data-stu-id="8aa08-241">After you download the Office 2013 applications through the Office Deployment Tool, use the Office Deployment Tool to convert them into an Office 2013 App-V package.</span></span> <span data-ttu-id="8aa08-242">完成与你的许可模型对应的步骤。</span><span class="sxs-lookup"><span data-stu-id="8aa08-242">Complete the steps that correspond to your licensing model.</span></span>

**<span data-ttu-id="8aa08-243">需要执行的操作摘要：</span><span class="sxs-lookup"><span data-stu-id="8aa08-243">Summary of what you’ll need to do:</span></span>**

-   <span data-ttu-id="8aa08-244">在64位 Windows 计算机上创建 Office 2013 App-v 包。</span><span class="sxs-lookup"><span data-stu-id="8aa08-244">Create the Office 2013 App-V packages on 64-bit Windows computers.</span></span> <span data-ttu-id="8aa08-245">但是，该包将在32位和64位 Windows 7 和 Windows 8 计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="8aa08-245">However, the package will run on 32-bit and 64-bit Windows 7 and Windows 8 computers.</span></span>

-   <span data-ttu-id="8aa08-246">使用 Office 部署工具为订阅授权包或批量许可证创建 Office App-v 程序包，然后修改 CustomConfig.xml 配置文件。</span><span class="sxs-lookup"><span data-stu-id="8aa08-246">Create an Office App-V package for either Subscription Licensing package or Volume Licensing by using the Office Deployment Tool, and then modify the CustomConfig.xml configuration file.</span></span>

    <span data-ttu-id="8aa08-247">下表汇总了您所使用的授权模型的 CustomConfig.xml 文件中需要输入的值。</span><span class="sxs-lookup"><span data-stu-id="8aa08-247">The following table summarizes the values you need to enter in the CustomConfig.xml file for the licensing model you’re using.</span></span> <span data-ttu-id="8aa08-248">表格后面的部分中的步骤将指定所需的确切条目。</span><span class="sxs-lookup"><span data-stu-id="8aa08-248">The steps in the sections that follow the table will specify the exact entries you need to make.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8aa08-249">产品 ID</span><span class="sxs-lookup"><span data-stu-id="8aa08-249">Product ID</span></span></th>
<th align="left"><span data-ttu-id="8aa08-250">批量许可</span><span class="sxs-lookup"><span data-stu-id="8aa08-250">Volume Licensing</span></span></th>
<th align="left"><span data-ttu-id="8aa08-251">订阅许可</span><span class="sxs-lookup"><span data-stu-id="8aa08-251">Subscription Licensing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="8aa08-252">Office 2013</span><span class="sxs-lookup"><span data-stu-id="8aa08-252">Office 2013</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="8aa08-253">ProPlusVolume</span><span class="sxs-lookup"><span data-stu-id="8aa08-253">ProPlusVolume</span></span></p></td>
<td align="left"><p><span data-ttu-id="8aa08-254">O365proplusretail 用作</span><span class="sxs-lookup"><span data-stu-id="8aa08-254">O365ProPlusRetail</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="8aa08-255">Office 2013 与 Visio 2013</span><span class="sxs-lookup"><span data-stu-id="8aa08-255">Office 2013 with Visio 2013</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="8aa08-256">ProPlusVolume</span><span class="sxs-lookup"><span data-stu-id="8aa08-256">ProPlusVolume</span></span></p>
<p><span data-ttu-id="8aa08-257">VisioProVolume</span><span class="sxs-lookup"><span data-stu-id="8aa08-257">VisioProVolume</span></span></p></td>
<td align="left"><p><span data-ttu-id="8aa08-258">O365proplusretail 用作</span><span class="sxs-lookup"><span data-stu-id="8aa08-258">O365ProPlusRetail</span></span></p>
<p><span data-ttu-id="8aa08-259">VisioProRetail</span><span class="sxs-lookup"><span data-stu-id="8aa08-259">VisioProRetail</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="8aa08-260">Office 2013 与 Visio 2013 和 Project 2013</span><span class="sxs-lookup"><span data-stu-id="8aa08-260">Office 2013 with Visio 2013 and Project 2013</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="8aa08-261">ProPlusVolume</span><span class="sxs-lookup"><span data-stu-id="8aa08-261">ProPlusVolume</span></span></p>
<p><span data-ttu-id="8aa08-262">VisioProVolume</span><span class="sxs-lookup"><span data-stu-id="8aa08-262">VisioProVolume</span></span></p>
<p><span data-ttu-id="8aa08-263">ProjectProVolume</span><span class="sxs-lookup"><span data-stu-id="8aa08-263">ProjectProVolume</span></span></p></td>
<td align="left"><p><span data-ttu-id="8aa08-264">O365proplusretail 用作</span><span class="sxs-lookup"><span data-stu-id="8aa08-264">O365ProPlusRetail</span></span></p>
<p><span data-ttu-id="8aa08-265">VisioProRetail</span><span class="sxs-lookup"><span data-stu-id="8aa08-265">VisioProRetail</span></span></p>
<p><span data-ttu-id="8aa08-266">ProjectProRetail</span><span class="sxs-lookup"><span data-stu-id="8aa08-266">ProjectProRetail</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="8aa08-267">如何将 Office 应用程序转换为 App-v 包</span><span class="sxs-lookup"><span data-stu-id="8aa08-267">How to convert the Office applications into an App-V package</span></span>**

1. <span data-ttu-id="8aa08-268">在记事本中，重新打开 CustomConfig.xml 文件，然后对文件进行以下更改：</span><span class="sxs-lookup"><span data-stu-id="8aa08-268">In Notepad, reopen the CustomConfig.xml file, and make the following changes to the file:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="8aa08-269">参数</span><span class="sxs-lookup"><span data-stu-id="8aa08-269">Parameter</span></span></th>
   <th align="left"><span data-ttu-id="8aa08-270">将值更改为</span><span class="sxs-lookup"><span data-stu-id="8aa08-270">What to change the value to</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="8aa08-271">SourcePath</span><span class="sxs-lookup"><span data-stu-id="8aa08-271">SourcePath</span></span></p></td>
   <td align="left"><p><span data-ttu-id="8aa08-272">指向之前下载的 Office 应用程序。</span><span class="sxs-lookup"><span data-stu-id="8aa08-272">Point to the Office applications downloaded earlier.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="8aa08-273">ProductID</span><span class="sxs-lookup"><span data-stu-id="8aa08-273">ProductID</span></span></p></td>
   <td align="left"><p><span data-ttu-id="8aa08-274">指定许可类型，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="8aa08-274">Specify the type of licensing, as shown in the following examples:</span></span></p>
   <ul>
   <li><p><span data-ttu-id="8aa08-275">订阅许可</span><span class="sxs-lookup"><span data-stu-id="8aa08-275">Subscription Licensing</span></span></p>
   <pre class="syntax" space="preserve"><code>&lt;Configuration&gt;
      &lt;Add SourcePath= &quot;\server\Office 2013&quot; OfficeClientEdition=&quot;32&quot; &gt;
       &lt;Product ID=&quot;O365ProPlusRetail&quot;&gt;
         &lt;Language ID=&quot;en-us&quot; /&gt;
       &lt;/Product&gt;
       &lt;Product ID=&quot;VisioProRetail&quot;&gt;
         &lt;Language ID=&quot;en-us&quot; /&gt;
       &lt;/Product&gt;
     &lt;/Add&gt;
   &lt;/Configuration&gt; </code></pre>
   <p><span data-ttu-id="8aa08-276">在此示例中，创建带有订阅授权的程序包的以下更改：</span><span class="sxs-lookup"><span data-stu-id="8aa08-276">In this example, the following changes were made to create a package with Subscription licensing:</span></span></p>
   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="8aa08-277">SourcePath</span><span class="sxs-lookup"><span data-stu-id="8aa08-277">SourcePath</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="8aa08-278">路径，该路径已更改为指向之前下载的 Office 应用程序。</span><span class="sxs-lookup"><span data-stu-id="8aa08-278">is the path, which was changed to point to the Office applications that were downloaded earlier.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="8aa08-279">产品 ID</span><span class="sxs-lookup"><span data-stu-id="8aa08-279">Product ID</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="8aa08-280">for Office 已更改为 <code>O365ProPlusRetail</code> 。</span><span class="sxs-lookup"><span data-stu-id="8aa08-280">for Office was changed to <code>O365ProPlusRetail</code>.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="8aa08-281">产品 ID</span><span class="sxs-lookup"><span data-stu-id="8aa08-281">Product ID</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="8aa08-282">Visio 的已更改为 <code>VisioProRetail</code> 。</span><span class="sxs-lookup"><span data-stu-id="8aa08-282">for Visio was changed to <code>VisioProRetail</code>.</span></span></p></td>
   </tr>
   </tbody>
   </table>
   <p> </p>
   <p></p></li>
   <li><p><span data-ttu-id="8aa08-283">批量许可</span><span class="sxs-lookup"><span data-stu-id="8aa08-283">Volume Licensing</span></span></p>
   <pre class="syntax" space="preserve"><code>&lt;Configuration&gt;
      &lt;Add SourcePath= &quot;\Server\Office2013&quot; OfficeClientEdition=&quot;32&quot; &gt;
       &lt;Product ID=&quot;ProPlusVolume&quot;&gt;
         &lt;Language ID=&quot;en-us&quot; /&gt;
       &lt;/Product&gt;
       &lt;Product ID=&quot;VisioProVolume&quot;&gt;
         &lt;Language ID=&quot;en-us&quot; /&gt;
       &lt;/Product&gt;
     &lt;/Add&gt;
   &lt;/Configuration&gt;</code></pre>
   <p><span data-ttu-id="8aa08-284">在此示例中，已进行以下更改：创建具有批量许可的程序包：</span><span class="sxs-lookup"><span data-stu-id="8aa08-284">In this example, the following changes were made to create a package with Volume licensing:</span></span></p>
   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="8aa08-285">SourcePath</span><span class="sxs-lookup"><span data-stu-id="8aa08-285">SourcePath</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="8aa08-286">路径，该路径已更改为指向之前下载的 Office 应用程序。</span><span class="sxs-lookup"><span data-stu-id="8aa08-286">is the path, which was changed to point to the Office applications that were downloaded earlier.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="8aa08-287">产品 ID</span><span class="sxs-lookup"><span data-stu-id="8aa08-287">Product ID</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="8aa08-288">for Office 已更改为 <code>ProPlusVolume</code> 。</span><span class="sxs-lookup"><span data-stu-id="8aa08-288">for Office was changed to <code>ProPlusVolume</code>.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="8aa08-289">产品 ID</span><span class="sxs-lookup"><span data-stu-id="8aa08-289">Product ID</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="8aa08-290">Visio 的已更改为 <code>VisioProVolume</code> 。</span><span class="sxs-lookup"><span data-stu-id="8aa08-290">for Visio was changed to <code>VisioProVolume</code>.</span></span></p></td>
   </tr>
   </tbody>
   </table>
   <p> </p>
   <p></p></li>
   </ul></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="8aa08-291">ExcludeApp （可选）</span><span class="sxs-lookup"><span data-stu-id="8aa08-291">ExcludeApp (optional)</span></span></p></td>
   <td align="left"><p><span data-ttu-id="8aa08-292">允许你指定不希望包含在 Office 部署工具创建的 App-v 程序包中的 Office 程序。</span><span class="sxs-lookup"><span data-stu-id="8aa08-292">Lets you specify Office programs that you don’t want included in the App-V package that the Office Deployment Tool creates.</span></span> <span data-ttu-id="8aa08-293">例如，您可以排除 Access 和 InfoPath。</span><span class="sxs-lookup"><span data-stu-id="8aa08-293">For example, you can exclude Access and InfoPath.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="8aa08-294">PACKAGEGUID （可选）</span><span class="sxs-lookup"><span data-stu-id="8aa08-294">PACKAGEGUID (optional)</span></span></p></td>
   <td align="left"><p><span data-ttu-id="8aa08-295">默认情况下，Office 部署工具创建的所有 app-v 程序包共享相同的 App-v 包 ID。</span><span class="sxs-lookup"><span data-stu-id="8aa08-295">By default, all App-V packages created by the Office Deployment Tool share the same App-V Package ID.</span></span> <span data-ttu-id="8aa08-296">你可以使用 PACKAGEGUID 为每个程序包指定不同的程序包 ID，从而允许你发布由 Office 部署工具创建的多个 App-v 程序包，并使用 App-v 服务器对其进行管理。</span><span class="sxs-lookup"><span data-stu-id="8aa08-296">You can use PACKAGEGUID to specify a different package ID for each package, which allows you to publish multiple App-V packages, created by the Office Deployment Tool, and manage them by using the App-V Server.</span></span></p>
   <p><span data-ttu-id="8aa08-297">使用此参数的一个示例是为不同用户创建不同的程序包。</span><span class="sxs-lookup"><span data-stu-id="8aa08-297">An example of when to use this parameter is if you create different packages for different users.</span></span> <span data-ttu-id="8aa08-298">例如，你可以为某些用户创建一个仅包含 Office 2013 的程序包，并使用 Office 2013 和 Visio 2013 为另一组用户创建另一个程序包。</span><span class="sxs-lookup"><span data-stu-id="8aa08-298">For example, you can create a package with just Office 2013 for some users, and create another package with Office 2013 and Visio 2013 for another set of users.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="8aa08-299">注意</span><span class="sxs-lookup"><span data-stu-id="8aa08-299">Note</span></span></strong><br/><p><span data-ttu-id="8aa08-300">即使你使用的是唯一的程序包 Id，你仍然可以将仅一个 App-v 包部署到单个设备。</span><span class="sxs-lookup"><span data-stu-id="8aa08-300">Even if you use unique package IDs, you can still deploy only one App-V package to a single device.</span></span></p>
   </div>
   <div>

   </div></td>
   </tr>
   </tbody>
   </table>



2. <span data-ttu-id="8aa08-301">使用/packager 命令可将 Office 应用程序转换为 Office 2013 App-v 包。</span><span class="sxs-lookup"><span data-stu-id="8aa08-301">Use the /packager command to convert the Office applications to an Office 2013 App-V package.</span></span>

   <span data-ttu-id="8aa08-302">例如：</span><span class="sxs-lookup"><span data-stu-id="8aa08-302">For example:</span></span>

   ``` syntax
   \\server\Office2013\setup.exe /packager \\server\Office2013\Customconfig.xml  \\server\share\Office2013AppV
   ```

   <span data-ttu-id="8aa08-303">在示例中：</span><span class="sxs-lookup"><span data-stu-id="8aa08-303">In the example:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="8aa08-304">\server\Office2013</span><span class="sxs-lookup"><span data-stu-id="8aa08-304">\server\Office2013</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="8aa08-305">是包含 Office 部署工具和自定义 Configuration.xml 文件的网络共享位置 Customconfig.xml。</span><span class="sxs-lookup"><span data-stu-id="8aa08-305">is the network share location that contains the Office Deployment Tool and the custom Configuration.xml file, Customconfig.xml.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="8aa08-306">Setup.exe</span><span class="sxs-lookup"><span data-stu-id="8aa08-306">Setup.exe</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="8aa08-307">是 Office 部署工具。</span><span class="sxs-lookup"><span data-stu-id="8aa08-307">is the Office Deployment Tool.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="8aa08-308">/packager</span><span class="sxs-lookup"><span data-stu-id="8aa08-308">/packager</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="8aa08-309">按照 customConfig.xml 文件中的指定，创建具有批量许可的 Office 2013 App-v 程序包。</span><span class="sxs-lookup"><span data-stu-id="8aa08-309">creates the Office 2013 App-V package with Volume Licensing as specified in the customConfig.xml file.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="8aa08-310">\server\Office2013\Customconfig.xml</span><span class="sxs-lookup"><span data-stu-id="8aa08-310">\server\Office2013\Customconfig.xml</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="8aa08-311">传递已针对打包阶段准备的配置 XML 文件（在本例中为 customConfig）。</span><span class="sxs-lookup"><span data-stu-id="8aa08-311">passes the configuration XML file (in this case customConfig) that has been prepared for the packaging stage.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="8aa08-312">\server\share\Office 2013AppV</span><span class="sxs-lookup"><span data-stu-id="8aa08-312">\server\share\Office 2013AppV</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="8aa08-313">指定新创建的 Office App-v 包的位置。</span><span class="sxs-lookup"><span data-stu-id="8aa08-313">specifies the location of the newly created Office App-V package.</span></span></p></td>
   </tr>
   </tbody>
   </table>



~~~
After you run the **/packager** command, the following folders appear up in the directory where you specified the package should be saved:

-   **App-V Packages** – contains an Office 2013 App-V package and two deployment configuration files.

-   **WorkingDir**

**Note**  
To troubleshoot any issues, see the log files in the %temp% directory (default).
~~~



3. <span data-ttu-id="8aa08-314">验证 Office 2013 App-v 程序包是否正常工作：</span><span class="sxs-lookup"><span data-stu-id="8aa08-314">Verify that the Office 2013 App-V package works correctly:</span></span>

   1.  <span data-ttu-id="8aa08-315">将你全局创建的 Office 2013 App-v 包发布到测试计算机，并验证是否显示 Office 2013 快捷方式。</span><span class="sxs-lookup"><span data-stu-id="8aa08-315">Publish the Office 2013 App-V package, which you created globally, to a test computer, and verify that the Office 2013 shortcuts appear.</span></span>

   2.  <span data-ttu-id="8aa08-316">启动一些 Office 2013 应用程序（如 Excel 或 Word），以确保程序包按预期工作。</span><span class="sxs-lookup"><span data-stu-id="8aa08-316">Start a few Office 2013 applications, such as Excel or Word, to ensure that your package is working as expected.</span></span>

## <a href="" id="bkmk-pub-pkg-office"></a><span data-ttu-id="8aa08-317">发布 app-v 5.0 的 Office 程序包</span><span class="sxs-lookup"><span data-stu-id="8aa08-317">Publishing the Office package for App-V 5.0</span></span>


<span data-ttu-id="8aa08-318">使用以下信息发布 Office 程序包。</span><span class="sxs-lookup"><span data-stu-id="8aa08-318">Use the following information to publish an Office package.</span></span>

### <span data-ttu-id="8aa08-319">用于发布 Office App-v 程序包的方法</span><span class="sxs-lookup"><span data-stu-id="8aa08-319">Methods for publishing Office App-V packages</span></span>

<span data-ttu-id="8aa08-320">使用用于任何其他程序包的相同方法部署 Office 2013 的 app-v 程序包：</span><span class="sxs-lookup"><span data-stu-id="8aa08-320">Deploy the App-V package for Office 2013 by using the same methods you use for any other package:</span></span>

-   <span data-ttu-id="8aa08-321">System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="8aa08-321">System Center Configuration Manager</span></span>

-   <span data-ttu-id="8aa08-322">App-v 服务器</span><span class="sxs-lookup"><span data-stu-id="8aa08-322">App-V Server</span></span>

-   <span data-ttu-id="8aa08-323">通过 PowerShell 命令独立运行</span><span class="sxs-lookup"><span data-stu-id="8aa08-323">Stand-alone through PowerShell commands</span></span>

### <span data-ttu-id="8aa08-324">发布先决条件和要求</span><span class="sxs-lookup"><span data-stu-id="8aa08-324">Publishing prerequisites and requirements</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8aa08-325">先决条件或要求</span><span class="sxs-lookup"><span data-stu-id="8aa08-325">Prerequisite or requirement</span></span></th>
<th align="left"><span data-ttu-id="8aa08-326">详细信息</span><span class="sxs-lookup"><span data-stu-id="8aa08-326">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8aa08-327">在 App-v 客户端上启用 PowerShell 脚本</span><span class="sxs-lookup"><span data-stu-id="8aa08-327">Enable PowerShell scripting on the App-V clients</span></span></p></td>
<td align="left"><p><span data-ttu-id="8aa08-328">若要发布 Office 2013 程序包，必须运行脚本。</span><span class="sxs-lookup"><span data-stu-id="8aa08-328">To publish Office 2013 packages, you must run a script.</span></span></p>
<p><span data-ttu-id="8aa08-329">默认情况下，在 App-v 客户端上禁用程序包脚本。</span><span class="sxs-lookup"><span data-stu-id="8aa08-329">Package scripts are disabled by default on App-V clients.</span></span> <span data-ttu-id="8aa08-330">若要启用脚本，请运行以下 PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="8aa08-330">To enable scripting, run the following PowerShell command:</span></span></p>
<pre class="syntax" space="preserve"><code>Set-AppvClientConfiguration –EnablePackageScripts 1</code></pre></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8aa08-331">全局发布 Office 2013 程序包</span><span class="sxs-lookup"><span data-stu-id="8aa08-331">Publish the Office 2013 package globally</span></span></p></td>
<td align="left"><p><span data-ttu-id="8aa08-332">Office App-v 程序包中的扩展点需要在计算机级别安装。</span><span class="sxs-lookup"><span data-stu-id="8aa08-332">Extension points in the Office App-V package require installation at the computer level.</span></span></p>
<p><span data-ttu-id="8aa08-333">当您在计算机级别发布时，不需要任何先决条件操作或可再发行组件，并且 Office 2013 程序包全局使其应用程序可以像本地安装的 Office 一样工作，从而消除了管理员自定义程序包的需要。</span><span class="sxs-lookup"><span data-stu-id="8aa08-333">When you publish at the computer level, no prerequisite actions or redistributables are needed, and the Office 2013 package globally enables its applications to work like natively installed Office, eliminating the need for administrators to customize packages.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="8aa08-334">如何发布 Office 程序包</span><span class="sxs-lookup"><span data-stu-id="8aa08-334">How to publish an Office package</span></span>

<span data-ttu-id="8aa08-335">运行以下命令以在全球范围内发布 Office 程序包：</span><span class="sxs-lookup"><span data-stu-id="8aa08-335">Run the following command to publish an Office package globally:</span></span>

-   `Add-AppvClientPackage <Path_to_AppV_Package> | Publish-AppvClientPackage –global`

-   <span data-ttu-id="8aa08-336">从 App-v Server 上的 Web 管理控制台中，你可以向一组计算机（而不是用户组）添加权限，以使程序包能够在相应组中全局发布到计算机。</span><span class="sxs-lookup"><span data-stu-id="8aa08-336">From the Web Management Console on the App-V Server, you can add permissions to a group of computers instead of to a user group to enable packages to be published globally to the computers in the corresponding group.</span></span>

## <a href="" id="bkmk-custmz-manage-office-pkgs"></a><span data-ttu-id="8aa08-337">自定义和管理 Office App-v 程序包</span><span class="sxs-lookup"><span data-stu-id="8aa08-337">Customizing and managing Office App-V packages</span></span>


<span data-ttu-id="8aa08-338">若要管理 Office App-v 程序包，请使用与任何其他程序包相同的操作，但有一些例外，如下部分所述。</span><span class="sxs-lookup"><span data-stu-id="8aa08-338">To manage your Office App-V packages, use the same operations as you would for any other package, but there are a few exceptions, as outlined in the following sections.</span></span>

-   [<span data-ttu-id="8aa08-339">使用连接组启用 Office 插件</span><span class="sxs-lookup"><span data-stu-id="8aa08-339">Enabling Office plug-ins by using connection groups</span></span>](#bkmk-enable-office-plugins)

-   [<span data-ttu-id="8aa08-340">禁用 Office 2013 应用程序</span><span class="sxs-lookup"><span data-stu-id="8aa08-340">Disabling Office 2013 applications</span></span>](#bkmk-disable-office-apps)

-   [<span data-ttu-id="8aa08-341">禁用 Office 2013 快捷方式</span><span class="sxs-lookup"><span data-stu-id="8aa08-341">Disabling Office 2013 shortcuts</span></span>](#bkmk-disable-shortcuts)

-   [<span data-ttu-id="8aa08-342">管理 Office 2013 程序包升级</span><span class="sxs-lookup"><span data-stu-id="8aa08-342">Managing Office 2013 package upgrades</span></span>](#bkmk-manage-office-pkg-upgrd)

-   [<span data-ttu-id="8aa08-343">管理 Office 2013 许可升级</span><span class="sxs-lookup"><span data-stu-id="8aa08-343">Managing Office 2013 licensing upgrades</span></span>](#bkmk-manage-office-lic-upgrd)

-   [<span data-ttu-id="8aa08-344">通过 Office 部署 Visio 2013 和 Project 2013</span><span class="sxs-lookup"><span data-stu-id="8aa08-344">Deploying Visio 2013 and Project 2013 with Office</span></span>](#bkmk-deploy-visio-project)

### <a href="" id="bkmk-enable-office-plugins"></a><span data-ttu-id="8aa08-345">使用连接组启用 Office 插件</span><span class="sxs-lookup"><span data-stu-id="8aa08-345">Enabling Office plug-ins by using connection groups</span></span>

<span data-ttu-id="8aa08-346">使用此部分中的步骤，通过 Office 程序包启用 Office 插件。</span><span class="sxs-lookup"><span data-stu-id="8aa08-346">Use the steps in this section to enable Office plug-ins with your Office package.</span></span> <span data-ttu-id="8aa08-347">若要使用 Office 插件，必须使用 App-v Sequencer 创建单独的程序包，该程序包只包含插件。不能使用 Office 部署工具创建插件程序包。</span><span class="sxs-lookup"><span data-stu-id="8aa08-347">To use Office plug-ins, you must use the App-V Sequencer to create a separate package that contains just the plug-ins. You cannot use the Office Deployment Tool to create the plug-ins package.</span></span> <span data-ttu-id="8aa08-348">然后，创建包含 Office 程序包和插件程序包的连接组，如以下步骤所述。</span><span class="sxs-lookup"><span data-stu-id="8aa08-348">You then create a connection group that contains the Office package and the plug-ins package, as described in the following steps.</span></span>

**<span data-ttu-id="8aa08-349">为 Office App-v 程序包启用插件</span><span class="sxs-lookup"><span data-stu-id="8aa08-349">To enable plug-ins for Office App-V packages</span></span>**

1.  <span data-ttu-id="8aa08-350">通过 App-v Server、System Center Configuration Manager 或 PowerShell cmdlet 添加连接组。</span><span class="sxs-lookup"><span data-stu-id="8aa08-350">Add a Connection Group through App-V Server, System Center Configuration Manager, or a PowerShell cmdlet.</span></span>

2.  <span data-ttu-id="8aa08-351">使用 app-v 5.0 Sequencer 对插件进行排序。</span><span class="sxs-lookup"><span data-stu-id="8aa08-351">Sequence your plug-ins using the App-V 5.0 Sequencer.</span></span> <span data-ttu-id="8aa08-352">确保在用于对插件进行排序的计算机上安装了 Office 2013。</span><span class="sxs-lookup"><span data-stu-id="8aa08-352">Ensure that Office 2013 is installed on the computer being used to sequence the plug-in.</span></span> <span data-ttu-id="8aa08-353">在序列化 Office 2013 插件时，建议使用排序计算机上的 Microsoft 365 应用 for enterprise （非虚拟）。</span><span class="sxs-lookup"><span data-stu-id="8aa08-353">It is recommended you use Microsoft 365 Apps for enterprise(non-virtual) on the sequencing computer when you sequence Office 2013 plug-ins.</span></span>

3.  <span data-ttu-id="8aa08-354">创建包含所需插件的 app-v 5.0 程序包。</span><span class="sxs-lookup"><span data-stu-id="8aa08-354">Create an App-V 5.0 package that includes the desired plug-ins.</span></span>

4.  <span data-ttu-id="8aa08-355">通过 App-v server、System Center Configuration Manager 或 PowerShell cmdlet 添加连接组。</span><span class="sxs-lookup"><span data-stu-id="8aa08-355">Add a Connection Group through App-V server, System Center Configuration Manager, or a PowerShell cmdlet.</span></span>

5.  <span data-ttu-id="8aa08-356">将 Office 2013 App-v 包和已排序的插件包添加到你创建的连接组。</span><span class="sxs-lookup"><span data-stu-id="8aa08-356">Add the Office 2013 App-V package and the plug-ins package you sequenced to the Connection Group you created.</span></span>

    **<span data-ttu-id="8aa08-357">重要提示</span><span class="sxs-lookup"><span data-stu-id="8aa08-357">Important</span></span>**  
    <span data-ttu-id="8aa08-358">连接组中的程序包顺序决定了程序包内容的合并顺序。</span><span class="sxs-lookup"><span data-stu-id="8aa08-358">The order of the packages in the Connection Group determines the order in which the package contents are merged.</span></span> <span data-ttu-id="8aa08-359">在连接组描述符文件中，首先添加 Office 2013 App-v 包，然后添加插件 App-v 包。</span><span class="sxs-lookup"><span data-stu-id="8aa08-359">In your Connection group descriptor file, add the Office 2013 App-V package first, and then add the plug-in App-V package.</span></span>



6.  <span data-ttu-id="8aa08-360">请确保将两个程序包都发布到目标计算机，并对该插件程序包进行全局发布，以匹配已发布的 Office 2013 App-v 程序包的全局设置。</span><span class="sxs-lookup"><span data-stu-id="8aa08-360">Ensure that both packages are published to the target computer and that the plug-in package is published globally to match the global settings of the published Office 2013 App-V package.</span></span>

7.  <span data-ttu-id="8aa08-361">验证插件程序包的部署配置文件是否具有 Office 2013 App-v 程序包所具有的相同设置。</span><span class="sxs-lookup"><span data-stu-id="8aa08-361">Verify that the Deployment Configuration File of the plug-in package has the same settings that the Office 2013 App-V package has.</span></span>

    <span data-ttu-id="8aa08-362">由于 Office 2013 App-v 程序包与操作系统集成，因此插件程序包设置应匹配。</span><span class="sxs-lookup"><span data-stu-id="8aa08-362">Since the Office 2013 App-V package is integrated with the operating system, the plug-in package settings should match.</span></span> <span data-ttu-id="8aa08-363">你可以搜索 "COM 模式" 的部署配置文件，并确保插件程序包的值设置为 "集成"，并且 "InProcessEnabled" 和 "OutOfProcessEnabled" 与你发布的 Office 2013 App-v 包的设置相匹配。</span><span class="sxs-lookup"><span data-stu-id="8aa08-363">You can search the Deployment Configuration File for “COM Mode” and ensure that your plug-ins package has that value set as “Integrated” and that both "InProcessEnabled" and "OutOfProcessEnabled" match the settings of the Office 2013 App-V package you published.</span></span>

8.  <span data-ttu-id="8aa08-364">打开部署配置文件，并将**对象**的值设置为 " **false**"。</span><span class="sxs-lookup"><span data-stu-id="8aa08-364">Open the Deployment Configuration File and set the value for **Objects Enabled** to **false**.</span></span>

9.  <span data-ttu-id="8aa08-365">如果在排序后对部署配置文件进行了任何更改，请确保插件程序包已与文件一起发布。</span><span class="sxs-lookup"><span data-stu-id="8aa08-365">If you made any changes to the Deployment Configuration file after sequencing, ensure that the plug-in package is published with the file.</span></span>

10. <span data-ttu-id="8aa08-366">确保你创建的连接组已启用到你所需的计算机。</span><span class="sxs-lookup"><span data-stu-id="8aa08-366">Ensure that the Connection Group you created is enabled onto your desired computer.</span></span> <span data-ttu-id="8aa08-367">如果启用了连接组，在使用 Office 2013 App-v 包时，创建的连接组可能会 "挂起"。</span><span class="sxs-lookup"><span data-stu-id="8aa08-367">The Connection Group created will likely “pend” if the Office 2013 App-V package is in use when the Connection Group is enabled.</span></span> <span data-ttu-id="8aa08-368">如果出现这种情况，您必须重新启动才能成功启用连接组。</span><span class="sxs-lookup"><span data-stu-id="8aa08-368">If that happens, you have to reboot to successfully enable the Connection Group.</span></span>

11. <span data-ttu-id="8aa08-369">成功发布这两个程序包并启用连接组后，启动目标 Office 2013 应用程序，并验证你发布并添加到连接组的插件是否按预期工作。</span><span class="sxs-lookup"><span data-stu-id="8aa08-369">After you successfully publish both packages and enable the Connection Group, start the target Office 2013 application and verify that the plug-in you published and added to the connection group works as expected.</span></span>

### <a href="" id="bkmk-disable-office-apps"></a><span data-ttu-id="8aa08-370">禁用 Office 2013 应用程序</span><span class="sxs-lookup"><span data-stu-id="8aa08-370">Disabling Office 2013 applications</span></span>

<span data-ttu-id="8aa08-371">你可能希望在 Office App-v 包中禁用特定应用程序。</span><span class="sxs-lookup"><span data-stu-id="8aa08-371">You may want to disable specific applications in your Office App-V package.</span></span> <span data-ttu-id="8aa08-372">例如，您可以禁用 Access，但仍可使用所有其他 Office 应用程序。</span><span class="sxs-lookup"><span data-stu-id="8aa08-372">For instance, you can disable Access, but leave all other Office application main available.</span></span> <span data-ttu-id="8aa08-373">禁用应用程序时，最终用户将不再看到该应用程序的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="8aa08-373">When you disable an application, the end user will no longer see the shortcut for that application.</span></span> <span data-ttu-id="8aa08-374">不必重新对应用程序进行排序。</span><span class="sxs-lookup"><span data-stu-id="8aa08-374">You do not have to re-sequence the application.</span></span> <span data-ttu-id="8aa08-375">当你在发布 Office 2013 App-v 包后更改部署配置文件时，你将保存所做的更改，添加 Office 2013 App-v 程序包，然后使用新的部署配置文件重新发布它，以将新设置应用到 Office 2013 App-v 程序包应用程序。</span><span class="sxs-lookup"><span data-stu-id="8aa08-375">When you change the Deployment Configuration File after the Office 2013 App-V package has been published, you will save the changes, add the Office 2013 App-V package, and then republish it with the new Deployment Configuration File to apply the new settings to Office 2013 App-V Package applications.</span></span>

**<span data-ttu-id="8aa08-376">注意</span><span class="sxs-lookup"><span data-stu-id="8aa08-376">Note</span></span>**  
<span data-ttu-id="8aa08-377">若要在使用 Office 部署工具创建 App-v 包时排除特定的 Office 应用程序（例如，Access 和 InfoPath），请使用**ExcludeApp**设置。</span><span class="sxs-lookup"><span data-stu-id="8aa08-377">To exclude specific Office applications (for example, Access and InfoPath) when you create the App-V package with the Office Deployment Tool, use the **ExcludeApp** setting.</span></span> <span data-ttu-id="8aa08-378">有关详细信息，请参阅[configuration.xml 文件的即点即用参考](https://technet.microsoft.com/library/jj219426.aspx)。</span><span class="sxs-lookup"><span data-stu-id="8aa08-378">For more information, see [Reference for Click-to-Run configuration.xml file](https://technet.microsoft.com/library/jj219426.aspx).</span></span>



**<span data-ttu-id="8aa08-379">禁用 Office 2013 应用程序</span><span class="sxs-lookup"><span data-stu-id="8aa08-379">To disable an Office 2013 application</span></span>**

1.  <span data-ttu-id="8aa08-380">使用文本编辑器（如**记事本**）打开部署配置文件，然后搜索 "应用程序"。</span><span class="sxs-lookup"><span data-stu-id="8aa08-380">Open a Deployment Configuration File with a text editor such as **Notepad** and search for “Applications."</span></span>

2.  <span data-ttu-id="8aa08-381">搜索要禁用的 Office 应用程序，例如 Access 2013。</span><span class="sxs-lookup"><span data-stu-id="8aa08-381">Search for the Office application you want to disable, for example, Access 2013.</span></span>

3.  <span data-ttu-id="8aa08-382">将 "Enabled" 的值从 "true" 更改为 "false"。</span><span class="sxs-lookup"><span data-stu-id="8aa08-382">Change the value of "Enabled" from "true" to "false."</span></span>

4.  <span data-ttu-id="8aa08-383">保存部署配置文件。</span><span class="sxs-lookup"><span data-stu-id="8aa08-383">Save the Deployment Configuration File.</span></span>

5.  <span data-ttu-id="8aa08-384">将 Office 2013 App-v 包添加到新的部署配置文件。</span><span class="sxs-lookup"><span data-stu-id="8aa08-384">Add the Office 2013 App-V Package with the new Deployment Configuration File.</span></span>

    ```xml
    <Application Id="[{AppVPackageRoot)]\officefl5\INFOPATH.EXE" Enabled="true">
      <VisualElements>
        <Name>InfoPath Filler 2013</Name>
        <Icon />
        <Description />
      </VisualElements>
    </Application>
    <Application Id="[{AppVPackageRoot}]\office15\lync.exe" Enabled="true">
      <VisualElements>
        <Name>Lync 2013</Name>
        <Icon />
        <Description />
      </VisualElements>
    </Application>
    <Application Id="[(AppVPackageRoot}]\office15\MSACCESS.EXE" Enabled="true">
      <VisualElements>
        <Name>Access 2013</Name>
        <Icon />
        <Description />
      </VisualElements>
    </Application>
    ```

6.  <span data-ttu-id="8aa08-385">重新添加 Office 2013 App-v 程序包，然后使用新的部署配置文件重新添加它，以将新设置应用于 Office 2013 App-v 程序包应用程序。</span><span class="sxs-lookup"><span data-stu-id="8aa08-385">Re-add the Office 2013 App-V package, and then republish it with the new Deployment Configuration File to apply the new settings to Office 2013 App-V Package applications.</span></span>

### <a href="" id="bkmk-disable-shortcuts"></a><span data-ttu-id="8aa08-386">禁用 Office 2013 快捷方式</span><span class="sxs-lookup"><span data-stu-id="8aa08-386">Disabling Office 2013 shortcuts</span></span>

<span data-ttu-id="8aa08-387">你可能希望禁用某些 Office 应用程序的快捷方式，而不是取消发布或删除程序包。</span><span class="sxs-lookup"><span data-stu-id="8aa08-387">You may want to disable shortcuts for certain Office applications instead of unpublishing or removing the package.</span></span> <span data-ttu-id="8aa08-388">以下示例显示了如何禁用 Microsoft Access 的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="8aa08-388">The following example shows how to disable shortcuts for Microsoft Access.</span></span>

**<span data-ttu-id="8aa08-389">禁用 Office 2013 应用程序的快捷方式</span><span class="sxs-lookup"><span data-stu-id="8aa08-389">To disable shortcuts for Office 2013 applications</span></span>**

1.  <span data-ttu-id="8aa08-390">在记事本中打开部署配置文件，然后搜索 "快捷方式"。</span><span class="sxs-lookup"><span data-stu-id="8aa08-390">Open a Deployment Configuration File in Notepad and search for “Shortcuts”.</span></span>

2.  <span data-ttu-id="8aa08-391">若要禁用某些快捷方式，请删除或注释掉不需要的特定快捷方式。</span><span class="sxs-lookup"><span data-stu-id="8aa08-391">To disable certain shortcuts, delete or comment out the specific shortcuts you don’t want.</span></span> <span data-ttu-id="8aa08-392">必须保持子系统存在且已启用。</span><span class="sxs-lookup"><span data-stu-id="8aa08-392">You must keep the subsystem present and enabled.</span></span> <span data-ttu-id="8aa08-393">例如，在下面的示例中，删除 Microsoft Access 快捷方式，让子系统 &lt; 快捷方式保持 &gt; &lt; 原样/shortcut， &gt; 以禁用 Microsoft Access 快捷方式。</span><span class="sxs-lookup"><span data-stu-id="8aa08-393">For example, in the example below, delete the Microsoft Access shortcuts, while keeping the subsystems &lt;shortcut&gt; &lt;/shortcut&gt; intact to disable the Microsoft Access shortcut.</span></span>

    ``` syntax
    Shortcuts

    -->
     <Shortcuts Enabled="true">
      <Extensions>
        <Extension Category="AppV.Shortcut">
          <Shortcut>
           <File>[{Common Programs}]\Microsoft Office 2013\Access 2013.lnk</File>
           <Target>[{AppvPackageRoot}])office15\MSACCESS.EXE</Target>
           <Icon>[{Windows}]\Installer\{90150000-000F-0000-0000-000000FF1CE)\accicons.exe.Ø.ico</Icon>
           <Arguments />
           <WorkingDirectory />
           <AppuserModelId>Microsoft.Office.MSACCESS.EXE.15</AppUserModelId>
           <AppUserModelExcludeFromShowInNewInstall>true</AppUserModelExcludeFromShowInNewInstall>
           <Description>Build a professional app quickly to manage data.</Description>
           <ShowCommand>l</ShowCommand>
           <ApplicationId>[{AppVPackageRoot}]\office15\MSACCESS.EXE</ApplicationId>
        </Shortcut>
    ```

3.  <span data-ttu-id="8aa08-394">保存部署配置文件。</span><span class="sxs-lookup"><span data-stu-id="8aa08-394">Save the Deployment Configuration File.</span></span>

4.  <span data-ttu-id="8aa08-395">通过新的部署配置文件重新发布 Office 2013 App-v 程序包。</span><span class="sxs-lookup"><span data-stu-id="8aa08-395">Republish Office 2013 App-V Package with new Deployment Configuration File.</span></span>

<span data-ttu-id="8aa08-396">通过修改 app-v 程序包的部署配置（例如文件类型关联、虚拟文件系统等），可以更改许多其他设置。</span><span class="sxs-lookup"><span data-stu-id="8aa08-396">Many additional settings can be changed through modifying the Deployment Configuration for App-V packages, for example, file type associations, Virtual File System, and more.</span></span> <span data-ttu-id="8aa08-397">有关如何使用部署配置文件更改 App-v 程序包设置的其他信息，请参阅本文档末尾的 "其他资源" 部分。</span><span class="sxs-lookup"><span data-stu-id="8aa08-397">For additional information on how to use Deployment Configuration Files to change App-V package settings, refer to the additional resources section at the end of this document.</span></span>

### <a href="" id="bkmk-manage-office-pkg-upgrd"></a><span data-ttu-id="8aa08-398">管理 Office 2013 程序包升级</span><span class="sxs-lookup"><span data-stu-id="8aa08-398">Managing Office 2013 package upgrades</span></span>

<span data-ttu-id="8aa08-399">若要升级 Office 2013 程序包，请使用 Office 部署工具。</span><span class="sxs-lookup"><span data-stu-id="8aa08-399">To upgrade an Office 2013 package, use the Office Deployment Tool.</span></span> <span data-ttu-id="8aa08-400">若要升级以前部署的 Office 2013 程序包，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="8aa08-400">To upgrade a previously deployed Office 2013 package, perform the following steps.</span></span>

**<span data-ttu-id="8aa08-401">如何升级以前部署的 Office 2013 程序包</span><span class="sxs-lookup"><span data-stu-id="8aa08-401">How to upgrade a previously deployed Office 2013 package</span></span>**

1.  <span data-ttu-id="8aa08-402">通过 Office 部署工具创建新的 Office 2013 程序包，该工具使用最新的 Office 2013 应用程序软件。</span><span class="sxs-lookup"><span data-stu-id="8aa08-402">Create a new Office 2013 package through the Office Deployment Tool that uses the most recent Office 2013 application software.</span></span> <span data-ttu-id="8aa08-403">最新的 Office 2013 位始终可以通过创建 Office 2013 App-v 程序包的下载阶段获取。</span><span class="sxs-lookup"><span data-stu-id="8aa08-403">The most recent Office 2013 bits can always be obtained through the download stage of creating an Office 2013 App-V Package.</span></span> <span data-ttu-id="8aa08-404">新创建的 Office 2013 程序包将具有最新的更新和新的版本 ID。</span><span class="sxs-lookup"><span data-stu-id="8aa08-404">The newly created Office 2013 package will have the most recent updates and a new Version ID.</span></span> <span data-ttu-id="8aa08-405">使用 Office 部署工具创建的所有程序包都具有相同的沿袭。</span><span class="sxs-lookup"><span data-stu-id="8aa08-405">All packages created using the Office Deployment Tool have the same lineage.</span></span>

    **<span data-ttu-id="8aa08-406">注意</span><span class="sxs-lookup"><span data-stu-id="8aa08-406">Note</span></span>**  
    <span data-ttu-id="8aa08-407">Office App-V 程序包具有两个版本 Id：</span><span class="sxs-lookup"><span data-stu-id="8aa08-407">Office App-V packages have two Version IDs:</span></span>

    -   <span data-ttu-id="8aa08-408">Office 2013 App-V 程序包版本 ID 在使用 Office 部署工具创建的所有程序包中都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="8aa08-408">An Office 2013 App-V Package Version ID that is unique across all packages created using the Office Deployment Tool.</span></span>

    -   <span data-ttu-id="8aa08-409">第二个 App-v 包版本 ID，例如，在 AppX 清单中，仅当存在新版本的 Office 时才会更改。</span><span class="sxs-lookup"><span data-stu-id="8aa08-409">A second App-V Package Version ID, x.x.x.x for example, in the AppX manifest that will only change if there is a new version of Office itself.</span></span> <span data-ttu-id="8aa08-410">例如，如果有新的支持升级的 Office 2013 版本，并且通过 Office 部署工具创建了一个程序包以合并这些升级，则 X.x.x.x 版本 ID 将会更改，以反映 Office 版本本身是否已更改。</span><span class="sxs-lookup"><span data-stu-id="8aa08-410">For example, if a new Office 2013 release with upgrades is available, and a package is created through the Office Deployment Tool to incorporate these upgrades, the X.X.X.X version ID will change to reflect that the Office version itself has changed.</span></span> <span data-ttu-id="8aa08-411">App-v 服务器将使用 X.x.x.x 版本 ID 来区分此程序包，并识别它是否包含以前发布的程序包的新升级，因此，将其发布为现有 Office 2013 程序包的升级。</span><span class="sxs-lookup"><span data-stu-id="8aa08-411">The App-V server will use the X.X.X.X version ID to differentiate this package and recognize that it contains new upgrades to the previously published package, and as a result, publish it as an upgrade to the existing Office 2013 package.</span></span>



2.  <span data-ttu-id="8aa08-412">将新创建的 Office 2013 App-v 包全局发布到要应用新更新的计算机上。</span><span class="sxs-lookup"><span data-stu-id="8aa08-412">Globally publish the newly created Office 2013 App-V Packages onto computers where you would like to apply the new updates.</span></span> <span data-ttu-id="8aa08-413">由于新的程序包具有较旧的 Office 2013 App-v 程序包的沿袭，因此发布包含更新的新程序包将仅对旧程序包应用新的更改，因此速度将很快。</span><span class="sxs-lookup"><span data-stu-id="8aa08-413">Since the new package has the same lineage of the older Office 2013 App-V Package, publishing the new package with the updates will only apply the new changes to the old package, and thus will be fast.</span></span>

3.  <span data-ttu-id="8aa08-414">将采用与任何全局发布的 App-v 程序包相同的方式应用升级。</span><span class="sxs-lookup"><span data-stu-id="8aa08-414">Upgrades will be applied in the same manner of any globally published App-V Packages.</span></span> <span data-ttu-id="8aa08-415">由于应用程序可能正在使用，升级可能会延迟，直到重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="8aa08-415">Because applications will probably be in use, upgrades might be delayed until the computer is rebooted.</span></span>

### <a href="" id="bkmk-manage-office-lic-upgrd"></a><span data-ttu-id="8aa08-416">管理 Office 2013 许可升级</span><span class="sxs-lookup"><span data-stu-id="8aa08-416">Managing Office 2013 licensing upgrades</span></span>

<span data-ttu-id="8aa08-417">如果新的 Office 2013 App-v 包的许可证与当前部署的 Office 2013 App-v 包不同。</span><span class="sxs-lookup"><span data-stu-id="8aa08-417">If a new Office 2013 App-V Package has a different license than the Office 2013 App-V Package currently deployed.</span></span> <span data-ttu-id="8aa08-418">例如，部署的 Office 2013 程序包是基于订阅的 Office 2013，而新的 Office 2013 程序包是基于批量许可的，请按照以下说明进行操作，以确保升级的流畅授权升级：</span><span class="sxs-lookup"><span data-stu-id="8aa08-418">For instance, the Office 2013 package deployed is a subscription based Office 2013 and the new Office 2013 package is Volume Licensing based, the following instructions must be followed to ensure smooth licensing upgrade:</span></span>

**<span data-ttu-id="8aa08-419">如何升级 Office 2013 许可证</span><span class="sxs-lookup"><span data-stu-id="8aa08-419">How to upgrade an Office 2013 License</span></span>**

1.  <span data-ttu-id="8aa08-420">取消发布已部署的 Office 2013 订阅授权 App-v 程序包。</span><span class="sxs-lookup"><span data-stu-id="8aa08-420">Unpublish the already deployed Office 2013 Subscription Licensing App-V package.</span></span>

2.  <span data-ttu-id="8aa08-421">删除未发布的 Office 2013 订阅许可证 App-v 包。</span><span class="sxs-lookup"><span data-stu-id="8aa08-421">Remove the unpublished Office 2013 Subscription Licensing App-V package.</span></span>

3.  <span data-ttu-id="8aa08-422">重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="8aa08-422">Restart the computer.</span></span>

4.  <span data-ttu-id="8aa08-423">添加新的 Office 2013 应用程序-V 程序包批量许可。</span><span class="sxs-lookup"><span data-stu-id="8aa08-423">Add the new Office 2013 App-V Package Volume Licensing.</span></span>

5.  <span data-ttu-id="8aa08-424">通过批量许可发布添加的 Office 2013 App-v 程序包。</span><span class="sxs-lookup"><span data-stu-id="8aa08-424">Publish the added Office 2013 App-V Package with Volume Licensing.</span></span>

<span data-ttu-id="8aa08-425">将成功部署使用所选授权的 Office 2013 App-v 程序包。</span><span class="sxs-lookup"><span data-stu-id="8aa08-425">An Office 2013 App-V Package with your chosen licensing will be successfully deployed.</span></span>

### <a href="" id="bkmk-deploy-visio-project"></a><span data-ttu-id="8aa08-426">通过 Office 部署 Visio 2013 和 Project 2013</span><span class="sxs-lookup"><span data-stu-id="8aa08-426">Deploying Visio 2013 and Project 2013 with Office</span></span>

<span data-ttu-id="8aa08-427">下表介绍了通过 Office 部署 Visio 2013 和 Project 2013 的要求和选项。</span><span class="sxs-lookup"><span data-stu-id="8aa08-427">The following table describes the requirements and options for deploying Visio 2013 and Project 2013 with Office.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8aa08-428">任务</span><span class="sxs-lookup"><span data-stu-id="8aa08-428">Task</span></span></th>
<th align="left"><span data-ttu-id="8aa08-429">详细信息</span><span class="sxs-lookup"><span data-stu-id="8aa08-429">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8aa08-430">如何将 Visio 2013 和 Project 2013 打包并发布到 Office？</span><span class="sxs-lookup"><span data-stu-id="8aa08-430">How do I package and publish Visio 2013 and Project 2013 with Office?</span></span></p></td>
<td align="left"><p><span data-ttu-id="8aa08-431">您必须在同一程序包中包含 Visio 2013 和 Project 2013 和 Office。</span><span class="sxs-lookup"><span data-stu-id="8aa08-431">You must include Visio 2013 and Project 2013 in the same package with Office.</span></span></p>
<p><span data-ttu-id="8aa08-432">如果不部署 Office，则可以创建一个包含 Visio 和/或项目的程序包，前提是 <a href="../appv-v5/deploying-microsoft-office-2010-by-using-app-v.md" data-raw-source="[Deploying Microsoft Office 2010 by Using App-V](../appv-v5/deploying-microsoft-office-2010-by-using-app-v.md)"> 使用 App-v 部署 Microsoft Office 2010 </a> 。</span><span class="sxs-lookup"><span data-stu-id="8aa08-432">If you aren’t deploying Office, you can create a package that contains Visio and/or Project, as long as you follow <a href="../appv-v5/deploying-microsoft-office-2010-by-using-app-v.md" data-raw-source="[Deploying Microsoft Office 2010 by Using App-V](../appv-v5/deploying-microsoft-office-2010-by-using-app-v.md)">Deploying Microsoft Office 2010 by Using App-V</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8aa08-433">如何将 Visio 2013 和 Project 2013 部署到特定用户？</span><span class="sxs-lookup"><span data-stu-id="8aa08-433">How can I deploy Visio 2013 and Project 2013 to specific users?</span></span></p></td>
<td align="left"><p><span data-ttu-id="8aa08-434">使用以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="8aa08-434">Use one of the following methods:</span></span></p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8aa08-435">如果需要 .。。</span><span class="sxs-lookup"><span data-stu-id="8aa08-435">If you want to...</span></span></th>
<th align="left"><span data-ttu-id="8aa08-436">...然后使用此方法</span><span class="sxs-lookup"><span data-stu-id="8aa08-436">...then use this method</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8aa08-437">创建两个不同的程序包，并将每个程序包部署到不同组的用户</span><span class="sxs-lookup"><span data-stu-id="8aa08-437">Create two different packages and deploy each one to a different group of users</span></span></p></td>
<td align="left"><p><span data-ttu-id="8aa08-438">创建和部署以下程序包：</span><span class="sxs-lookup"><span data-stu-id="8aa08-438">Create and deploy the following packages:</span></span></p>
<ul>
<li><p><span data-ttu-id="8aa08-439">仅包含 Office 部署到用户仅需要 Office 的计算机的程序包。</span><span class="sxs-lookup"><span data-stu-id="8aa08-439">A package that contains only Office - deploy to computers whose users need only Office.</span></span></p></li>
<li><p><span data-ttu-id="8aa08-440">包含 Office、Visio 和 Project-部署到用户需要所有三个应用程序的计算机的程序包。</span><span class="sxs-lookup"><span data-stu-id="8aa08-440">A package that contains Office, Visio, and Project - deploy to computers whose users need all three applications.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8aa08-441">如果您只需要整个组织的一个程序包，或者如果您有共享计算机的用户，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8aa08-441">If you want only one package for the whole organization, or if you have users who share computers:</span></span></p></td>
<td align="left"><p><span data-ttu-id="8aa08-442">按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="8aa08-442">Follows these steps:</span></span></p>
<ol>
<li><p><span data-ttu-id="8aa08-443">创建包含 Office、Visio 和 Project 的程序包。</span><span class="sxs-lookup"><span data-stu-id="8aa08-443">Create a package that contains Office, Visio, and Project.</span></span></p></li>
<li><p><span data-ttu-id="8aa08-444">将程序包部署到所有用户。</span><span class="sxs-lookup"><span data-stu-id="8aa08-444">Deploy the package to all users.</span></span></p></li>
<li><p><span data-ttu-id="8aa08-445">使用 <a href="https://technet.microsoft.com/library/dd723678.aspx" data-raw-source="[Microsoft AppLocker](https://technet.microsoft.com/library/dd723678.aspx)"> Microsoft AppLocker </a> 阻止特定用户使用 Visio 和 Project。</span><span class="sxs-lookup"><span data-stu-id="8aa08-445">Use <a href="https://technet.microsoft.com/library/dd723678.aspx" data-raw-source="[Microsoft AppLocker](https://technet.microsoft.com/library/dd723678.aspx)">Microsoft AppLocker</a> to prevent specific users from using Visio and Project.</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="8aa08-446">其他资源</span><span class="sxs-lookup"><span data-stu-id="8aa08-446">Additional resources</span></span>


**<span data-ttu-id="8aa08-447">Office 2013 App-V 5.0 程序包5.0 其他资源</span><span class="sxs-lookup"><span data-stu-id="8aa08-447">Office 2013 App-V 5.0 Packages 5.0 Additional Resources</span></span>**

[<span data-ttu-id="8aa08-448">Office 部署工具，用于即点即用</span><span class="sxs-lookup"><span data-stu-id="8aa08-448">Office Deployment Tool for Click-to-Run</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=330672)

[<span data-ttu-id="8aa08-449">将 Microsoft Office 部署为顺序式 App-v 程序包所支持的方案</span><span class="sxs-lookup"><span data-stu-id="8aa08-449">Supported scenarios for deploying Microsoft Office as a sequenced App-V Package</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330680)

**<span data-ttu-id="8aa08-450">Office 2010 应用程序-V 5.0 程序包</span><span class="sxs-lookup"><span data-stu-id="8aa08-450">Office 2010 App-V 5.0 Packages</span></span>**

[<span data-ttu-id="8aa08-451">Microsoft Application Virtualization 5.0 的 microsoft Office 2010 排序包</span><span class="sxs-lookup"><span data-stu-id="8aa08-451">Microsoft Office 2010 Sequencing Kit for Microsoft Application Virtualization 5.0</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330681)

[<span data-ttu-id="8aa08-452">创建或使用 app-v 5.0 Office 2010 程序包时的已知问题</span><span class="sxs-lookup"><span data-stu-id="8aa08-452">Known issues when you create or use an App-V 5.0 Office 2010 package</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330682)

[<span data-ttu-id="8aa08-453">如何在 Microsoft Application Virtualization 5.0 中对 Microsoft Office 2010 进行排序</span><span class="sxs-lookup"><span data-stu-id="8aa08-453">How to sequence Microsoft Office 2010 in Microsoft Application Virtualization 5.0</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330676)

**<span data-ttu-id="8aa08-454">连接组</span><span class="sxs-lookup"><span data-stu-id="8aa08-454">Connection Groups</span></span>**

[<span data-ttu-id="8aa08-455">在 Microsoft App 中部署连接组-V v5</span><span class="sxs-lookup"><span data-stu-id="8aa08-455">Deploying Connection Groups in Microsoft App-V v5</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330683)

[<span data-ttu-id="8aa08-456">管理连接组</span><span class="sxs-lookup"><span data-stu-id="8aa08-456">Managing Connection Groups</span></span>](managing-connection-groups.md)

**<span data-ttu-id="8aa08-457">动态配置</span><span class="sxs-lookup"><span data-stu-id="8aa08-457">Dynamic Configuration</span></span>**

[<span data-ttu-id="8aa08-458">关于 App-V 5.0 动态配置</span><span class="sxs-lookup"><span data-stu-id="8aa08-458">About App-V 5.0 Dynamic Configuration</span></span>](about-app-v-50-dynamic-configuration.md)














