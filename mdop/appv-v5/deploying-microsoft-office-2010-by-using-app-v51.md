---
title: 使用 App-V 部署 Microsoft Office 2010
description: 使用 App-V 部署 Microsoft Office 2010
author: dansimp
ms.assetid: ae0b0459-c0d6-4946-b62d-ff153f52d1fb
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 90454373e9a1c894eba8cbf1b8642656b986bc94
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798592"
---
# <span data-ttu-id="f6eee-103">使用 App-V 部署 Microsoft Office 2010</span><span class="sxs-lookup"><span data-stu-id="f6eee-103">Deploying Microsoft Office 2010 by Using App-V</span></span>


<span data-ttu-id="f6eee-104">你可以使用以下方法之一为 Microsoft Application Virtualization （app-v）5.1 创建 Office 2010 程序包：</span><span class="sxs-lookup"><span data-stu-id="f6eee-104">You can create Office 2010 packages for Microsoft Application Virtualization (App-V) 5.1 using one of the following methods:</span></span>

-   <span data-ttu-id="f6eee-105">应用程序虚拟化（App-v） Sequencer</span><span class="sxs-lookup"><span data-stu-id="f6eee-105">Application Virtualization (App-V) Sequencer</span></span>

-   <span data-ttu-id="f6eee-106">应用程序虚拟化（App-v）程序包加速器</span><span class="sxs-lookup"><span data-stu-id="f6eee-106">Application Virtualization (App-V) Package Accelerator</span></span>

## <span data-ttu-id="f6eee-107">Office 2010 的 app-v 支持</span><span class="sxs-lookup"><span data-stu-id="f6eee-107">App-V support for Office 2010</span></span>


<span data-ttu-id="f6eee-108">下表显示了应用程序-V 版本、Office 程序包的创建方法、支持的许可以及 Office 2010 支持的部署。</span><span class="sxs-lookup"><span data-stu-id="f6eee-108">The following table shows the App-V versions, methods of Office package creation, supported licensing, and supported deployments for Office 2010.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f6eee-109">支持的项目</span><span class="sxs-lookup"><span data-stu-id="f6eee-109">Supported item</span></span></th>
<th align="left"><span data-ttu-id="f6eee-110">支持级别</span><span class="sxs-lookup"><span data-stu-id="f6eee-110">Level of support</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f6eee-111">支持的应用-V 版本</span><span class="sxs-lookup"><span data-stu-id="f6eee-111">Supported App-V versions</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="f6eee-112">4.6</span><span class="sxs-lookup"><span data-stu-id="f6eee-112">4.6</span></span></p></li>
<li><p><span data-ttu-id="f6eee-113">5.0</span><span class="sxs-lookup"><span data-stu-id="f6eee-113">5.0</span></span></p></li>
<li><p><span data-ttu-id="f6eee-114">5.1</span><span class="sxs-lookup"><span data-stu-id="f6eee-114">5.1</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f6eee-115">程序包创建</span><span class="sxs-lookup"><span data-stu-id="f6eee-115">Package creation</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="f6eee-116">引出</span><span class="sxs-lookup"><span data-stu-id="f6eee-116">Sequencing</span></span></p></li>
<li><p><span data-ttu-id="f6eee-117">程序包加速器</span><span class="sxs-lookup"><span data-stu-id="f6eee-117">Package Accelerator</span></span></p></li>
<li><p><span data-ttu-id="f6eee-118">Office 部署工具包</span><span class="sxs-lookup"><span data-stu-id="f6eee-118">Office Deployment Kit</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f6eee-119">支持的许可</span><span class="sxs-lookup"><span data-stu-id="f6eee-119">Supported licensing</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6eee-120">批量许可</span><span class="sxs-lookup"><span data-stu-id="f6eee-120">Volume Licensing</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f6eee-121">支持的部署</span><span class="sxs-lookup"><span data-stu-id="f6eee-121">Supported deployments</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="f6eee-122">桌面</span><span class="sxs-lookup"><span data-stu-id="f6eee-122">Desktop</span></span></p></li>
<li><p><span data-ttu-id="f6eee-123">个人 VDI</span><span class="sxs-lookup"><span data-stu-id="f6eee-123">Personal VDI</span></span></p></li>
<li><p><span data-ttu-id="f6eee-124">RDS</span><span class="sxs-lookup"><span data-stu-id="f6eee-124">RDS</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="f6eee-125">使用 sequencer 创建 Office 2010 App-V 5。1</span><span class="sxs-lookup"><span data-stu-id="f6eee-125">Creating Office 2010 App-V 5.1 using the sequencer</span></span>


<span data-ttu-id="f6eee-126">对 Office 2010 进行排序是在 App-v 5.1 上创建 Office 2010 程序包的主要方法之一。</span><span class="sxs-lookup"><span data-stu-id="f6eee-126">Sequencing Office 2010 is one of the main methods for creating an Office 2010 package on App-V 5.1.</span></span> <span data-ttu-id="f6eee-127">Microsoft 已通过知识文库文章提供了详细的食谱。</span><span class="sxs-lookup"><span data-stu-id="f6eee-127">Microsoft has provided a detailed recipe through a Knowledge Base article.</span></span> <span data-ttu-id="f6eee-128">若要在 App-V 5.1 上创建 Office 2010 程序包，请参阅以下链接获取详细说明：</span><span class="sxs-lookup"><span data-stu-id="f6eee-128">To create an Office 2010 package on App-V 5.1, refer to the following link for detailed instructions:</span></span>

[<span data-ttu-id="f6eee-129">如何在 Microsoft Application Virtualization 5.0 中对 Microsoft Office 2010 进行排序</span><span class="sxs-lookup"><span data-stu-id="f6eee-129">How To Sequence Microsoft Office 2010 in Microsoft Application Virtualization 5.0</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330676)

## <span data-ttu-id="f6eee-130">使用包加速器创建 Office 2010 App-v 5.1 程序包</span><span class="sxs-lookup"><span data-stu-id="f6eee-130">Creating Office 2010 App-V 5.1 packages using package accelerators</span></span>


<span data-ttu-id="f6eee-131">Office 2010 App-V 5.1 程序包可以通过程序包加速器创建。</span><span class="sxs-lookup"><span data-stu-id="f6eee-131">Office 2010 App-V 5.1 packages can be created through package accelerators.</span></span> <span data-ttu-id="f6eee-132">Microsoft 提供了用于在 Windows 10、Windows 8 和 Windows 7 上创建 Office 2010 的程序包加速器。</span><span class="sxs-lookup"><span data-stu-id="f6eee-132">Microsoft has provided package accelerators for creating Office 2010 on Windows 10, Windows 8 and Windows 7.</span></span> <span data-ttu-id="f6eee-133">若要使用程序包加速器在 App-v 上创建 Office 2010 程序包，请参阅以下页面以访问相应的程序包加速器：</span><span class="sxs-lookup"><span data-stu-id="f6eee-133">To create Office 2010 packages on App-V using Package accelerators, refer to the following pages to access the appropriate package accelerator:</span></span>

-   [<span data-ttu-id="f6eee-134">适用于 Office Professional Plus 2010 的 app-v 5.0 程序包加速器-Windows 8</span><span class="sxs-lookup"><span data-stu-id="f6eee-134">App-V 5.0 Package Accelerator for Office Professional Plus 2010 – Windows 8</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330677)

-   [<span data-ttu-id="f6eee-135">适用于 Office Professional Plus 2010 的 app-v 5.0 程序包加速器– Windows 7</span><span class="sxs-lookup"><span data-stu-id="f6eee-135">App-V 5.0 Package Accelerator for Office Professional Plus 2010 – Windows 7</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330678)

<span data-ttu-id="f6eee-136">有关如何使用 App-v 程序包加速器创建虚拟应用程序包的详细说明，请参阅[如何使用 App-v 包加速器创建虚拟应用程序包](how-to-create-a-virtual-application-package-using-an-app-v-package-accelerator51.md)。</span><span class="sxs-lookup"><span data-stu-id="f6eee-136">For detailed instructions on how to create virtual application packages using App-V package accelerators, see [How to Create a Virtual Application Package Using an App-V Package Accelerator](how-to-create-a-virtual-application-package-using-an-app-v-package-accelerator51.md).</span></span>

## <span data-ttu-id="f6eee-137">部署 app-v 5.1 的 Microsoft Office 程序包</span><span class="sxs-lookup"><span data-stu-id="f6eee-137">Deploying the Microsoft Office package for App-V 5.1</span></span>


<span data-ttu-id="f6eee-138">你可以使用以下任何应用程序 V 部署方法部署 Office 2010 程序包：</span><span class="sxs-lookup"><span data-stu-id="f6eee-138">You can deploy Office 2010 packages by using any of the following App-V deployment methods:</span></span>

-   <span data-ttu-id="f6eee-139">System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f6eee-139">System Center Configuration Manager</span></span>

-   <span data-ttu-id="f6eee-140">App-v 服务器</span><span class="sxs-lookup"><span data-stu-id="f6eee-140">App-V server</span></span>

-   <span data-ttu-id="f6eee-141">通过 PowerShell 命令独立运行</span><span class="sxs-lookup"><span data-stu-id="f6eee-141">Stand-alone through PowerShell commands</span></span>

## <span data-ttu-id="f6eee-142">Office App-V 程序包管理和自定义</span><span class="sxs-lookup"><span data-stu-id="f6eee-142">Office App-V package management and customization</span></span>


<span data-ttu-id="f6eee-143">通过已知的程序包管理机制，可以像管理任何其他 App-v 5.1 程序包一样管理 Office 2010 程序包。</span><span class="sxs-lookup"><span data-stu-id="f6eee-143">Office 2010 packages can be managed like any other App-V 5.1 packages through known package management mechanisms.</span></span> <span data-ttu-id="f6eee-144">例如，不需要特殊说明来添加、发布、取消发布或删除 Office 程序包。</span><span class="sxs-lookup"><span data-stu-id="f6eee-144">No special instructions are needed, for example, to add, publish, unpublish, or remove Office packages.</span></span>

## <span data-ttu-id="f6eee-145">Microsoft Office 与 Windows 集成</span><span class="sxs-lookup"><span data-stu-id="f6eee-145">Microsoft Office integration with Windows</span></span>


<span data-ttu-id="f6eee-146">下表提供了 Office 2010 受支持的集成点的完整列表。</span><span class="sxs-lookup"><span data-stu-id="f6eee-146">The following table provides a full list of supported integration points for Office 2010.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f6eee-147">扩展点</span><span class="sxs-lookup"><span data-stu-id="f6eee-147">Extension Point</span></span></th>
<th align="left"><span data-ttu-id="f6eee-148">描述</span><span class="sxs-lookup"><span data-stu-id="f6eee-148">Description</span></span></th>
<th align="left"><span data-ttu-id="f6eee-149">Office 2010</span><span class="sxs-lookup"><span data-stu-id="f6eee-149">Office 2010</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f6eee-150">适用于 Firefox 和 Chrome 的 Lync 会议加入插件</span><span class="sxs-lookup"><span data-stu-id="f6eee-150">Lync meeting Join Plug-in for Firefox and Chrome</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6eee-151">用户可以从 Firefox 和 Chrome 加入 Lync 会议</span><span class="sxs-lookup"><span data-stu-id="f6eee-151">User can join Lync meetings from Firefox and Chrome</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f6eee-152">已发送到 OneNote 打印驱动程序</span><span class="sxs-lookup"><span data-stu-id="f6eee-152">Sent to OneNote Print Driver</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6eee-153">用户可以打印到 OneNote</span><span class="sxs-lookup"><span data-stu-id="f6eee-153">User can print to OneNote</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6eee-154">是</span><span class="sxs-lookup"><span data-stu-id="f6eee-154">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f6eee-155">OneNote 链接笔记</span><span class="sxs-lookup"><span data-stu-id="f6eee-155">OneNote Linked Notes</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6eee-156">OneNote 链接笔记</span><span class="sxs-lookup"><span data-stu-id="f6eee-156">OneNote Linked Notes</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f6eee-157">发送到 OneNote Internet Explorer 加载项</span><span class="sxs-lookup"><span data-stu-id="f6eee-157">Send to OneNote Internet Explorer Add-In</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6eee-158">用户可以从 IE 发送到 OneNote</span><span class="sxs-lookup"><span data-stu-id="f6eee-158">User can send to OneNote from IE</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f6eee-159">Lync 和 Outlook 的防火墙例外</span><span class="sxs-lookup"><span data-stu-id="f6eee-159">Firewall Exception for Lync and Outlook</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6eee-160">Lync 和 Outlook 的防火墙例外</span><span class="sxs-lookup"><span data-stu-id="f6eee-160">Firewall Exception for Lync and Outlook</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f6eee-161">MAPI 客户端</span><span class="sxs-lookup"><span data-stu-id="f6eee-161">MAPI Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6eee-162">本机应用和外接程序可以通过 MAPI 与虚拟 Outlook 进行交互</span><span class="sxs-lookup"><span data-stu-id="f6eee-162">Native apps and add-ins can interact with virtual Outlook through MAPI</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f6eee-163">适用于 Firefox 的 SharePoint 插件</span><span class="sxs-lookup"><span data-stu-id="f6eee-163">SharePoint Plugin for Firefox</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6eee-164">用户可以使用 Firefox 中的 SharePoint 功能</span><span class="sxs-lookup"><span data-stu-id="f6eee-164">User can use SharePoint features in Firefox</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f6eee-165">"邮件控制面板" 小程序</span><span class="sxs-lookup"><span data-stu-id="f6eee-165">Mail Control Panel Applet</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6eee-166">用户在 Outlook 中获取 "邮件" 控制面板小程序</span><span class="sxs-lookup"><span data-stu-id="f6eee-166">User gets the mail control panel applet in Outlook</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6eee-167">是</span><span class="sxs-lookup"><span data-stu-id="f6eee-167">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f6eee-168">主互操作程序集</span><span class="sxs-lookup"><span data-stu-id="f6eee-168">Primary Interop Assemblies</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6eee-169">支持托管加载项</span><span class="sxs-lookup"><span data-stu-id="f6eee-169">Support managed add-ins</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f6eee-170">Office 文档缓存处理程序</span><span class="sxs-lookup"><span data-stu-id="f6eee-170">Office Document Cache Handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6eee-171">允许 Office 应用程序的文档缓存</span><span class="sxs-lookup"><span data-stu-id="f6eee-171">Allows Document Cache for Office applications</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f6eee-172">Outlook 协议搜索处理程序</span><span class="sxs-lookup"><span data-stu-id="f6eee-172">Outlook Protocol Search handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6eee-173">用户可以在 outlook 中搜索</span><span class="sxs-lookup"><span data-stu-id="f6eee-173">User can search in outlook</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6eee-174">是</span><span class="sxs-lookup"><span data-stu-id="f6eee-174">Yes</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f6eee-175">活动 X 控件：</span><span class="sxs-lookup"><span data-stu-id="f6eee-175">Active X Controls:</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6eee-176">有关 ActiveX 控件的详细信息，请参阅 <a href="https://go.microsoft.com/fwlink/p/?LinkId=331361" data-raw-source="[ActiveX Control API Reference](https://go.microsoft.com/fwlink/p/?LinkId=331361)"> Activex 控件 API 参考 </a> 。</span><span class="sxs-lookup"><span data-stu-id="f6eee-176">For more information on ActiveX controls, refer to <a href="https://go.microsoft.com/fwlink/p/?LinkId=331361" data-raw-source="[ActiveX Control API Reference](https://go.microsoft.com/fwlink/p/?LinkId=331361)">ActiveX Control API Reference</a>.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="f6eee-177">Groove。 SiteClient</span><span class="sxs-lookup"><span data-stu-id="f6eee-177">Groove.SiteClient</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6eee-178">活动 X 控件</span><span class="sxs-lookup"><span data-stu-id="f6eee-178">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="f6eee-179">PortalConnect.PersonalSite</span><span class="sxs-lookup"><span data-stu-id="f6eee-179">PortalConnect.PersonalSite</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6eee-180">活动 X 控件</span><span class="sxs-lookup"><span data-stu-id="f6eee-180">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="f6eee-181">OpenDocuments</span><span class="sxs-lookup"><span data-stu-id="f6eee-181">SharePoint.openDocuments</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6eee-182">活动 X 控件</span><span class="sxs-lookup"><span data-stu-id="f6eee-182">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="f6eee-183">ExportDatabase</span><span class="sxs-lookup"><span data-stu-id="f6eee-183">SharePoint.ExportDatabase</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6eee-184">活动 X 控件</span><span class="sxs-lookup"><span data-stu-id="f6eee-184">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="f6eee-185">SpreadSheetLauncher</span><span class="sxs-lookup"><span data-stu-id="f6eee-185">SharePoint.SpreadSheetLauncher</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6eee-186">活动 X 控件</span><span class="sxs-lookup"><span data-stu-id="f6eee-186">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="f6eee-187">StssyncHander</span><span class="sxs-lookup"><span data-stu-id="f6eee-187">SharePoint.StssyncHander</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6eee-188">活动 X 控件</span><span class="sxs-lookup"><span data-stu-id="f6eee-188">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="f6eee-189">DragUploadCtl</span><span class="sxs-lookup"><span data-stu-id="f6eee-189">SharePoint.DragUploadCtl</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6eee-190">活动 X 控件</span><span class="sxs-lookup"><span data-stu-id="f6eee-190">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="f6eee-191">DragDownloadCtl</span><span class="sxs-lookup"><span data-stu-id="f6eee-191">SharePoint.DragDownloadCtl</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6eee-192">活动 X 控件</span><span class="sxs-lookup"><span data-stu-id="f6eee-192">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="f6eee-193">Sharpoint.OpenXMLDocuments</span><span class="sxs-lookup"><span data-stu-id="f6eee-193">Sharpoint.OpenXMLDocuments</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6eee-194">活动 X 控件</span><span class="sxs-lookup"><span data-stu-id="f6eee-194">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="f6eee-195">ClipboardCtl</span><span class="sxs-lookup"><span data-stu-id="f6eee-195">Sharepoint.ClipboardCtl</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6eee-196">活动 X 控件</span><span class="sxs-lookup"><span data-stu-id="f6eee-196">Active X control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="f6eee-197">WinProj</span><span class="sxs-lookup"><span data-stu-id="f6eee-197">WinProj.Activator</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6eee-198">活动 X 控件</span><span class="sxs-lookup"><span data-stu-id="f6eee-198">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="f6eee-199">NameCtrl</span><span class="sxs-lookup"><span data-stu-id="f6eee-199">Name.NameCtrl</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6eee-200">活动 X 控件</span><span class="sxs-lookup"><span data-stu-id="f6eee-200">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="f6eee-201">STSUPld.CopyCtl</span><span class="sxs-lookup"><span data-stu-id="f6eee-201">STSUPld.CopyCtl</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6eee-202">活动 X 控件</span><span class="sxs-lookup"><span data-stu-id="f6eee-202">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="f6eee-203">CommunicatorMeetingJoinAx.JoinManager</span><span class="sxs-lookup"><span data-stu-id="f6eee-203">CommunicatorMeetingJoinAx.JoinManager</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6eee-204">活动 X 控件</span><span class="sxs-lookup"><span data-stu-id="f6eee-204">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="f6eee-205">LISTNET.Listnet</span><span class="sxs-lookup"><span data-stu-id="f6eee-205">LISTNET.Listnet</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6eee-206">活动 X 控件</span><span class="sxs-lookup"><span data-stu-id="f6eee-206">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="f6eee-207">OneDrive Pro 浏览器帮助程序</span><span class="sxs-lookup"><span data-stu-id="f6eee-207">OneDrive Pro Browser Helper</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6eee-208">活动 X 控件]</span><span class="sxs-lookup"><span data-stu-id="f6eee-208">Active X Control]</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f6eee-209">OneDrive Pro 图标覆盖</span><span class="sxs-lookup"><span data-stu-id="f6eee-209">OneDrive Pro Icon Overlays</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6eee-210">当用户查看文件夹 OneDrive Pro 文件夹时，Windows 资源管理器 shell 图标重叠</span><span class="sxs-lookup"><span data-stu-id="f6eee-210">Windows explorer shell icon overlays when users look at folders OneDrive Pro folders</span></span></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="f6eee-211">其他资源</span><span class="sxs-lookup"><span data-stu-id="f6eee-211">Additional resources</span></span>


**<span data-ttu-id="f6eee-212">Office 2013 App-v 程序包其他资源</span><span class="sxs-lookup"><span data-stu-id="f6eee-212">Office 2013 App-V Packages Additional Resources</span></span>**

[<span data-ttu-id="f6eee-213">将 Microsoft Office 部署为顺序式 App-v 程序包所支持的方案</span><span class="sxs-lookup"><span data-stu-id="f6eee-213">Supported scenarios for deploying Microsoft Office as a sequenced App-V Package</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330680)

**<span data-ttu-id="f6eee-214">Office 2010 应用程序-V 程序包</span><span class="sxs-lookup"><span data-stu-id="f6eee-214">Office 2010 App-V Packages</span></span>**

[<span data-ttu-id="f6eee-215">Microsoft Application Virtualization 5.0 的 microsoft Office 2010 排序包</span><span class="sxs-lookup"><span data-stu-id="f6eee-215">Microsoft Office 2010 Sequencing Kit for Microsoft Application Virtualization 5.0</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330681)

[<span data-ttu-id="f6eee-216">创建或使用 app-v 5.0 Office 2010 程序包时的已知问题</span><span class="sxs-lookup"><span data-stu-id="f6eee-216">Known issues when you create or use an App-V 5.0 Office 2010 package</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330682)

[<span data-ttu-id="f6eee-217">如何在 Microsoft Application Virtualization 5.0 中对 Microsoft Office 2010 进行排序</span><span class="sxs-lookup"><span data-stu-id="f6eee-217">How to sequence Microsoft Office 2010 in Microsoft Application Virtualization 5.0</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330676)

**<span data-ttu-id="f6eee-218">连接组</span><span class="sxs-lookup"><span data-stu-id="f6eee-218">Connection Groups</span></span>**

[<span data-ttu-id="f6eee-219">在 Microsoft App 中部署连接组-V v5</span><span class="sxs-lookup"><span data-stu-id="f6eee-219">Deploying Connection Groups in Microsoft App-V v5</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330683)

[<span data-ttu-id="f6eee-220">管理连接组</span><span class="sxs-lookup"><span data-stu-id="f6eee-220">Managing Connection Groups</span></span>](managing-connection-groups51.md)

**<span data-ttu-id="f6eee-221">动态配置</span><span class="sxs-lookup"><span data-stu-id="f6eee-221">Dynamic Configuration</span></span>**

[<span data-ttu-id="f6eee-222">关于 App-V 5.1 动态配置</span><span class="sxs-lookup"><span data-stu-id="f6eee-222">About App-V 5.1 Dynamic Configuration</span></span>](about-app-v-51-dynamic-configuration.md)






 

 





