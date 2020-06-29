---
title: App-V 5.0 中的新增功能
description: App-V 5.0 中的新增功能
author: dansimp
ms.assetid: 79ff6e02-e926-4803-87d8-248a6b28099d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dabe264f033bd5c9897f07d931f799a42e6b72e9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798241"
---
# <span data-ttu-id="44109-103">App-V 5.0 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="44109-103">What's New in App-V 5.0</span></span>


<span data-ttu-id="44109-104">本部分适用于已熟悉 app-v 的用户，想要了解在 app-v 5.0 中更改的内容（如果你还不熟悉 App-v），应首先阅读 " [app-v 5.0 规划](planning-for-app-v-50-rc.md)"。</span><span class="sxs-lookup"><span data-stu-id="44109-104">This section is for users who are already familiar with App-V and want to know what has changed in App-V 5.0 If you are not already familiar with App-V, you should start by reading [Planning for App-V 5.0](planning-for-app-v-50-rc.md).</span></span>

## <span data-ttu-id="44109-105">标准功能的更改</span><span class="sxs-lookup"><span data-stu-id="44109-105">Changes in Standard Functionality</span></span>


<span data-ttu-id="44109-106">以下各节包含有关 App-v 5.0 的标准功能更改的信息。</span><span class="sxs-lookup"><span data-stu-id="44109-106">The following sections contain information about the changes in standard functionality for App-V 5.0.</span></span>

### <span data-ttu-id="44109-107">对支持的操作系统的更改</span><span class="sxs-lookup"><span data-stu-id="44109-107">Changes to Supported Operating Systems</span></span>

<span data-ttu-id="44109-108">有关详细信息，请参阅[App-V 5.0 支持的配置](app-v-50-supported-configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="44109-108">For more information, see [App-V 5.0 Supported Configurations](app-v-50-supported-configurations.md).</span></span>

## <span data-ttu-id="44109-109">对 sequencer 的更改</span><span class="sxs-lookup"><span data-stu-id="44109-109">Changes to the sequencer</span></span>


<span data-ttu-id="44109-110">以下各节包含有关 app-v 5.0 sequencer 中的更改的信息。</span><span class="sxs-lookup"><span data-stu-id="44109-110">The following sections contain information about the changes in the App-V 5.0 sequencer.</span></span>

### <span data-ttu-id="44109-111">对排序器的特定更改</span><span class="sxs-lookup"><span data-stu-id="44109-111">Specific change to the sequencer</span></span>

<span data-ttu-id="44109-112">下表显示了有关应用 V 5.0 sequencer 的更改信息</span><span class="sxs-lookup"><span data-stu-id="44109-112">The following table displays information about what has changed with the App-V 5.0 sequencer</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="44109-113">Sequencer 功能</span><span class="sxs-lookup"><span data-stu-id="44109-113">Sequencer Feature</span></span></th>
<th align="left"><span data-ttu-id="44109-114">App-v 5.0 Sequencer 功能</span><span class="sxs-lookup"><span data-stu-id="44109-114">App-V 5.0 Sequencer Functionality</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="44109-115">重启处理</span><span class="sxs-lookup"><span data-stu-id="44109-115">Reboot processing</span></span></p></td>
<td align="left"><p><span data-ttu-id="44109-116">当应用程序提示重新启动时，你应该允许应用程序重新启动运行 sequencer 的计算机。</span><span class="sxs-lookup"><span data-stu-id="44109-116">When an application prompts for a restart, you should allow the application to restart the computer running the sequencer.</span></span> <span data-ttu-id="44109-117">运行 sequencer 的计算机将重新启动，并且 sequencer 将在监视模式下继续。</span><span class="sxs-lookup"><span data-stu-id="44109-117">The computer running the sequencer will restart and the sequencer will resume in monitoring mode.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="44109-118">指定虚拟应用程序目录</span><span class="sxs-lookup"><span data-stu-id="44109-118">Specifying the virtual application directory</span></span></p></td>
<td align="left"><p><span data-ttu-id="44109-119">虚拟应用程序目录是必需的参数。</span><span class="sxs-lookup"><span data-stu-id="44109-119">Virtual Application Directory is a mandatory parameter.</span></span> <span data-ttu-id="44109-120">为了获得最佳结果，它应与应用程序安装程序的安装目录相匹配。</span><span class="sxs-lookup"><span data-stu-id="44109-120">For best results, it should match the installation directory of the application installer.</span></span> <span data-ttu-id="44109-121">这将导致更最佳的性能和应用程序兼容性。</span><span class="sxs-lookup"><span data-stu-id="44109-121">This results in more optimal performance and application compatibility.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="44109-122">编辑快捷方式/FTAs</span><span class="sxs-lookup"><span data-stu-id="44109-122">Editing shortcuts/FTAs</span></span></p></td>
<td align="left"><p><span data-ttu-id="44109-123">在 <strong> 排序向导完成后，"快捷方式/FTA" 页面位于 "高级 </strong> 编辑" 页面上。</span><span class="sxs-lookup"><span data-stu-id="44109-123">The Shortcuts/FTA page is on the <strong>Advanced</strong> editing page after the sequencing wizard has completed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="44109-124">“更改历史记录”选项卡</span><span class="sxs-lookup"><span data-stu-id="44109-124">Change History Tab</span></span></p></td>
<td align="left"><p><span data-ttu-id="44109-125">已删除 app-v 5.0 的 "更改历史记录" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="44109-125">The Change History tab has been removed for App-V 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="44109-126">“OSD”选项卡</span><span class="sxs-lookup"><span data-stu-id="44109-126">OSD Tab</span></span></p></td>
<td align="left"><p><span data-ttu-id="44109-127">已删除 app-v 5.0 的 OSD 选项卡。</span><span class="sxs-lookup"><span data-stu-id="44109-127">The OSD tab has been removed for App-V 5.0.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="44109-128">“虚拟服务”选项卡</span><span class="sxs-lookup"><span data-stu-id="44109-128">Virtual Services Tab</span></span></p></td>
<td align="left"><p><span data-ttu-id="44109-129">已删除 app-v 5.0 的 "虚拟服务" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="44109-129">The virtual services tab has been removed for App-V 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="44109-130">"文件/虚拟文件系统" 选项卡</span><span class="sxs-lookup"><span data-stu-id="44109-130">Files/Virtual File System Tab</span></span></p></td>
<td align="left"><p><span data-ttu-id="44109-131">组合这些选项卡，并允许您修改软件包文件。</span><span class="sxs-lookup"><span data-stu-id="44109-131">These tabs are combined and allow you to modify package files.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="44109-132">“部署”选项卡</span><span class="sxs-lookup"><span data-stu-id="44109-132">Deployment Tab</span></span></p></td>
<td align="left"><p><span data-ttu-id="44109-133">没有更长的选项可用于在程序包中配置服务器 URL。</span><span class="sxs-lookup"><span data-stu-id="44109-133">There are no longer options to configure the server URL in the packages.</span></span> <span data-ttu-id="44109-134">你应该立即使用部署配置或管理服务器对此进行配置。</span><span class="sxs-lookup"><span data-stu-id="44109-134">You should configure this now using deployment configuration, or the management server.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="44109-135">程序包转换器工具</span><span class="sxs-lookup"><span data-stu-id="44109-135">Package Converter Tool</span></span></p></td>
<td align="left"><p><span data-ttu-id="44109-136">现在，你可以使用 PowerShell 转换在早期版本中创建的程序包。</span><span class="sxs-lookup"><span data-stu-id="44109-136">You can now use PowerShell to convert packages created in previous versions.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="44109-137">加载项/中间件</span><span class="sxs-lookup"><span data-stu-id="44109-137">Add-on/Middleware</span></span></p></td>
<td align="left"><p><span data-ttu-id="44109-138">在对加载项或中间件应用程序进行排序时，可以展开父包。</span><span class="sxs-lookup"><span data-stu-id="44109-138">You can expand parent packages when you are sequencing an Add-On or Middleware application.</span></span> <span data-ttu-id="44109-139">加载项和中间件程序包必须使用 App-v 5.0 中的连接组进行连接。</span><span class="sxs-lookup"><span data-stu-id="44109-139">Add-ons and Middleware packages must be connected using connection groups in App-V 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="44109-140">文件输出</span><span class="sxs-lookup"><span data-stu-id="44109-140">Files output</span></span></p></td>
<td align="left"><p><span data-ttu-id="44109-141">以下文件是使用 app-v 5.0、Windows Installer （.msi）、appv、部署配置、用户配置和 Report.XML 创建的。</span><span class="sxs-lookup"><span data-stu-id="44109-141">The following files are created with App-V 5.0, Windows Installer (.msi), .appv, deployment configuration, user configuration, and the Report.XML.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="44109-142">压缩/安全描述符/MSI 程序包</span><span class="sxs-lookup"><span data-stu-id="44109-142">Compression/Security descriptors/MSI packages</span></span></p></td>
<td align="left"><p><span data-ttu-id="44109-143">压缩和创建 Windows Installer （.msi）文件对所有程序包都是自动的，不能再替代安全描述符。</span><span class="sxs-lookup"><span data-stu-id="44109-143">Compression and the creation of a Windows Installer (.msi) file are automatic for all packages and you can no longer override security descriptors.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="44109-144">工具/选项</span><span class="sxs-lookup"><span data-stu-id="44109-144">Tools / Options</span></span></p></td>
<td align="left"><p><span data-ttu-id="44109-145">"诊断" 窗口已删除，还有其他一些设置。</span><span class="sxs-lookup"><span data-stu-id="44109-145">The Diagnostics window has been removed as well as several other settings.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="44109-146">安装驱动器</span><span class="sxs-lookup"><span data-stu-id="44109-146">Installation Drive</span></span></p></td>
<td align="left"><p><span data-ttu-id="44109-147">安装应用程序时，不再需要安装驱动器。</span><span class="sxs-lookup"><span data-stu-id="44109-147">An installation drive is no longer required when you install an application.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="44109-148">OOS 流</span><span class="sxs-lookup"><span data-stu-id="44109-148">OOS Streaming</span></span></p></td>
<td align="left"><p><span data-ttu-id="44109-149">如果未执行任何流优化，则当运行 App-v 5.0 客户端的计算机请求程序包，直到它们启动时，程序包才会出现流错误。</span><span class="sxs-lookup"><span data-stu-id="44109-149">If no stream optimization is performed, packages are stream faulted when they are requested by computers running the App-V 5.0 client until they can launch.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="44109-150">问： &lt; /p&gt;</span><span class="sxs-lookup"><span data-stu-id="44109-150">Q:&lt;/p&gt;</span></span></td>
<td align="left"><p><span data-ttu-id="44109-151">App-v 5.0 使用本机文件系统，不再需要 Q:。</span><span class="sxs-lookup"><span data-stu-id="44109-151">App-V 5.0 uses the native file system and no longer requires a Q:.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="44109-152">序列错误检测</span><span class="sxs-lookup"><span data-stu-id="44109-152">Sequencing error detection</span></span>


<span data-ttu-id="44109-153">App-v 5.0 sequencer 可检测排序期间的常见排序问题。</span><span class="sxs-lookup"><span data-stu-id="44109-153">The App-V 5.0 sequencer can detect common sequencing issues during sequencing.</span></span> <span data-ttu-id="44109-154">排序向导结束时的 "**安装报告**" 页面显示根据问题的严重程度，归类为**错误**、**警告**和**信息**的诊断消息。</span><span class="sxs-lookup"><span data-stu-id="44109-154">The **Installation Report** page at the end of the sequencing wizard displays diagnostic messages categorized into **Errors**, **Warnings**, and **Info** depending on the severity of the issue.</span></span>

<span data-ttu-id="44109-155">若要显示有关事件的更多详细信息，请双击要在报表中查看的项目。</span><span class="sxs-lookup"><span data-stu-id="44109-155">To display more detailed information about an event, double-click the item you want to review in the report.</span></span> <span data-ttu-id="44109-156">将显示排序问题以及有关如何解决这些问题的建议。</span><span class="sxs-lookup"><span data-stu-id="44109-156">The sequencing issues, as well as suggestions about how to resolve the issues are displayed.</span></span> <span data-ttu-id="44109-157">创建程序包后，将汇总系统准备报告和安装报告中的信息。</span><span class="sxs-lookup"><span data-stu-id="44109-157">Information from the system preparation report and the installation report are summarized when you have finished creating a package.</span></span> <span data-ttu-id="44109-158">以下列表显示了报告中可用的问题类型：</span><span class="sxs-lookup"><span data-stu-id="44109-158">The following list displays the types of issues available in the report:</span></span>

-   <span data-ttu-id="44109-159">排除的文件。</span><span class="sxs-lookup"><span data-stu-id="44109-159">Excluded files.</span></span>

-   <span data-ttu-id="44109-160">驱动程序信息。</span><span class="sxs-lookup"><span data-stu-id="44109-160">Driver information.</span></span>

-   <span data-ttu-id="44109-161">COM + 系统差异。</span><span class="sxs-lookup"><span data-stu-id="44109-161">COM+ system differences.</span></span>

-   <span data-ttu-id="44109-162">并行（SxS）冲突。</span><span class="sxs-lookup"><span data-stu-id="44109-162">Side-by-side (SxS) conflicts.</span></span>

-   <span data-ttu-id="44109-163">外壳扩展。</span><span class="sxs-lookup"><span data-stu-id="44109-163">Shell Extensions.</span></span>

-   <span data-ttu-id="44109-164">有关不支持的服务的信息。</span><span class="sxs-lookup"><span data-stu-id="44109-164">Information about unsupported services.</span></span>

-   <span data-ttu-id="44109-165">DCOM.</span><span class="sxs-lookup"><span data-stu-id="44109-165">DCOM.</span></span>

## <span data-ttu-id="44109-166">连接组</span><span class="sxs-lookup"><span data-stu-id="44109-166">Connection Groups</span></span>


<span data-ttu-id="44109-167">以前称为 "**动态套件合成**" 的 app-v 功能现在称为 "app-v 5.0 中的**连接组**"。</span><span class="sxs-lookup"><span data-stu-id="44109-167">The App-V feature formerly known as **Dynamic Suite Composition** is now referred to as **Connection Groups** in App-V 5.0.</span></span> <span data-ttu-id="44109-168">有关使用连接组的详细信息，请参阅[管理连接组](managing-connection-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="44109-168">For more information about using Connection Groups see [Managing Connection Groups](managing-connection-groups.md).</span></span>

## <span data-ttu-id="44109-169">许可和测定功能</span><span class="sxs-lookup"><span data-stu-id="44109-169">Licensing and Metering Functionality</span></span>


<span data-ttu-id="44109-170">应用程序和许可功能已在 App-v 5.0 中删除。</span><span class="sxs-lookup"><span data-stu-id="44109-170">The application and licensing functionality has been removed in App-V 5.0.</span></span> <span data-ttu-id="44109-171">环境中的实际许可证位置取决于相关联的许可条款所授予的特定软件标题许可证和使用权利。</span><span class="sxs-lookup"><span data-stu-id="44109-171">The actual license positions in your environment depend on the specific software title license and usage rights granted by the associated license terms.</span></span>

## <span data-ttu-id="44109-172">文件和应用程序缓存</span><span class="sxs-lookup"><span data-stu-id="44109-172">File and Application Cache</span></span>


<span data-ttu-id="44109-173">App-v 5.0 没有可用的文件或应用程序缓存。</span><span class="sxs-lookup"><span data-stu-id="44109-173">There is no file or application cache available with App-V 5.0.</span></span>






## <span data-ttu-id="44109-174">相关主题</span><span class="sxs-lookup"><span data-stu-id="44109-174">Related topics</span></span>


[<span data-ttu-id="44109-175">关于 App-V 5.0</span><span class="sxs-lookup"><span data-stu-id="44109-175">About App-V 5.0</span></span>](about-app-v-50.md)

 

 





