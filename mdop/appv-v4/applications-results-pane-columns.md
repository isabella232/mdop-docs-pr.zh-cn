---
title: “应用程序结果”窗格列
description: “应用程序结果”窗格列
author: dansimp
ms.assetid: abae5ce2-40df-4f47-8062-f5eb6295c88c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c0138e40647a6a7d131a08aa03a9c9c1fcb071b3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802240"
---
# <span data-ttu-id="1e1c9-103">“应用程序结果”窗格列</span><span class="sxs-lookup"><span data-stu-id="1e1c9-103">Applications Results Pane Columns</span></span>


<span data-ttu-id="1e1c9-104">应用程序虚拟化客户端管理控制台中的 "**应用程序**" 节点的 "**结果**" 窗格可以显示各种列。</span><span class="sxs-lookup"><span data-stu-id="1e1c9-104">The **Results** pane of the **Applications** node in the Application Virtualization Client Management Console can display a variety of columns.</span></span> <span data-ttu-id="1e1c9-105">默认情况下显示**应用程序**、**运行**、**锁定**和**程序包状态**。</span><span class="sxs-lookup"><span data-stu-id="1e1c9-105">**Application**, **Running**, **Locked**, and **Package Status** are shown by default.</span></span>

<span data-ttu-id="1e1c9-106">**注意** 右键单击 "**结果**" 窗格，选择 "**视图**"，然后选择 "**添加/删除列**"，即可添加或删除列。</span><span class="sxs-lookup"><span data-stu-id="1e1c9-106">**Note** You can add or remove columns by right-clicking in the **Results** pane, selecting **View**, and then selecting **Add/Remove Columns**.</span></span>

 

<span data-ttu-id="1e1c9-107">可以按任何列对列表进行排序。</span><span class="sxs-lookup"><span data-stu-id="1e1c9-107">The list can be sorted by any column.</span></span> <span data-ttu-id="1e1c9-108">包含日期和时间的列按时间顺序排序，而不是按字母顺序排序。</span><span class="sxs-lookup"><span data-stu-id="1e1c9-108">Columns that contain dates and times are sorted in chronological order, not alphabetical.</span></span> <span data-ttu-id="1e1c9-109">对于包含日期和时间和文本混合的列，日期和时间被视为位于任何其他文本之前。</span><span class="sxs-lookup"><span data-stu-id="1e1c9-109">For columns that contain a mix of dates and times and text, dates and times are considered to come before any other text.</span></span>

<span data-ttu-id="1e1c9-110">以下列可用。</span><span class="sxs-lookup"><span data-stu-id="1e1c9-110">The following columns are available.</span></span>

<a href="" id="application"></a>**<span data-ttu-id="1e1c9-111">应用程序</span><span class="sxs-lookup"><span data-stu-id="1e1c9-111">Application</span></span>**  
<span data-ttu-id="1e1c9-112">应用程序名称和版本（用空格分隔）。</span><span class="sxs-lookup"><span data-stu-id="1e1c9-112">The application name and version, separated by a space.</span></span>

<a href="" id="application-in-use"></a>**<span data-ttu-id="1e1c9-113">应用程序正在使用</span><span class="sxs-lookup"><span data-stu-id="1e1c9-113">Application In Use</span></span>**  
<span data-ttu-id="1e1c9-114">显示 **"是" 或 "** **否**"，具体取决于是否有任何用户正在使用该应用程序（即运行该应用程序或加载它）。</span><span class="sxs-lookup"><span data-stu-id="1e1c9-114">Displays **Yes** or **No** depending on whether any user is using the application (that is, running it or loading it).</span></span>

<a href="" id="app-virt-server"></a>**<span data-ttu-id="1e1c9-115">应用 Virt 服务器</span><span class="sxs-lookup"><span data-stu-id="1e1c9-115">App Virt Server</span></span>**  
<span data-ttu-id="1e1c9-116">从中流出数据包的应用程序虚拟化服务器。</span><span class="sxs-lookup"><span data-stu-id="1e1c9-116">The Application Virtualization server from which the package was streamed.</span></span>

<a href="" id="cached-icon-file"></a>**<span data-ttu-id="1e1c9-117">缓存的图标文件</span><span class="sxs-lookup"><span data-stu-id="1e1c9-117">Cached Icon File</span></span>**  
<span data-ttu-id="1e1c9-118">缓存中的图标文件的名称（当前实现中的 GUID）。</span><span class="sxs-lookup"><span data-stu-id="1e1c9-118">The name of the icon files in cache (a GUID in the current implementation).</span></span>

<a href="" id="cached-icon-path"></a>**<span data-ttu-id="1e1c9-119">缓存的图标路径</span><span class="sxs-lookup"><span data-stu-id="1e1c9-119">Cached Icon Path</span></span>**  
<span data-ttu-id="1e1c9-120">指向缓存中的图标文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="1e1c9-120">The full path to the icon files in cache.</span></span>

<a href="" id="cached-launch-percent"></a>**<span data-ttu-id="1e1c9-121">缓存启动百分比</span><span class="sxs-lookup"><span data-stu-id="1e1c9-121">Cached Launch Percent</span></span>**  
<span data-ttu-id="1e1c9-122">当前在缓存中的应用程序启动数据的百分比。</span><span class="sxs-lookup"><span data-stu-id="1e1c9-122">The percentage of the application’s launch data currently in cache.</span></span>

<a href="" id="cached-launch-size--mb-"></a>**<span data-ttu-id="1e1c9-123">缓存启动大小（MB）</span><span class="sxs-lookup"><span data-stu-id="1e1c9-123">Cached Launch Size (MB)</span></span>**  
<span data-ttu-id="1e1c9-124">当前在缓存中的应用程序启动数据量。</span><span class="sxs-lookup"><span data-stu-id="1e1c9-124">The amount of the application’s launch data currently in cache.</span></span>

<a href="" id="cached-osd-file"></a>**<span data-ttu-id="1e1c9-125">缓存的 OSD 文件</span><span class="sxs-lookup"><span data-stu-id="1e1c9-125">Cached OSD File</span></span>**  
<span data-ttu-id="1e1c9-126">缓存中的 OSD 文件的名称（即当前实现中的 GUID）。</span><span class="sxs-lookup"><span data-stu-id="1e1c9-126">The name of the OSD file in the cache (which is a GUID in the current implementation).</span></span>

<a href="" id="cached-osd-path"></a>**<span data-ttu-id="1e1c9-127">缓存的 OSD 路径</span><span class="sxs-lookup"><span data-stu-id="1e1c9-127">Cached OSD Path</span></span>**  
<span data-ttu-id="1e1c9-128">缓存中的 OSD 文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="1e1c9-128">The full path to the OSD file in the cache.</span></span>

<a href="" id="cached-package-percent"></a>**<span data-ttu-id="1e1c9-129">缓存的程序包百分比</span><span class="sxs-lookup"><span data-stu-id="1e1c9-129">Cached Package Percent</span></span>**  
<span data-ttu-id="1e1c9-130">当前在缓存中的程序包的百分比。</span><span class="sxs-lookup"><span data-stu-id="1e1c9-130">The percentage of the package currently in cache.</span></span>

<a href="" id="cached-package-size--mb-"></a>**<span data-ttu-id="1e1c9-131">缓存的程序包大小（MB）</span><span class="sxs-lookup"><span data-stu-id="1e1c9-131">Cached Package Size (MB)</span></span>**  
<span data-ttu-id="1e1c9-132">当前在缓存中的程序包部分的大小。</span><span class="sxs-lookup"><span data-stu-id="1e1c9-132">The size of the portion of the package currently in cache.</span></span>

<a href="" id="icon-file"></a>**<span data-ttu-id="1e1c9-133">图标文件</span><span class="sxs-lookup"><span data-stu-id="1e1c9-133">Icon File</span></span>**  
<span data-ttu-id="1e1c9-134">图标文件的原始名称。</span><span class="sxs-lookup"><span data-stu-id="1e1c9-134">The original name of the icon file.</span></span>

<a href="" id="icon-path"></a>**<span data-ttu-id="1e1c9-135">图标路径</span><span class="sxs-lookup"><span data-stu-id="1e1c9-135">Icon Path</span></span>**  
<span data-ttu-id="1e1c9-136">图标文件的原始路径或 URL。</span><span class="sxs-lookup"><span data-stu-id="1e1c9-136">The original path or URL for the icon file.</span></span>

<a href="" id="last-system-launch"></a>**<span data-ttu-id="1e1c9-137">上次系统启动</span><span class="sxs-lookup"><span data-stu-id="1e1c9-137">Last System Launch</span></span>**  
<span data-ttu-id="1e1c9-138">上次由系统启动应用程序的时间。</span><span class="sxs-lookup"><span data-stu-id="1e1c9-138">The last time the application was launched by the system.</span></span>

<a href="" id="last-user-launch"></a>**<span data-ttu-id="1e1c9-139">上次用户启动</span><span class="sxs-lookup"><span data-stu-id="1e1c9-139">Last User Launch</span></span>**  
<span data-ttu-id="1e1c9-140">上次用户启动应用程序的时间。</span><span class="sxs-lookup"><span data-stu-id="1e1c9-140">The last time the application was launched by the user.</span></span>

<a href="" id="launch-size--mb-"></a>**<span data-ttu-id="1e1c9-141">启动大小（MB）</span><span class="sxs-lookup"><span data-stu-id="1e1c9-141">Launch Size (MB)</span></span>**  
<span data-ttu-id="1e1c9-142">启动应用程序所需的软件包数据的未压缩大小。</span><span class="sxs-lookup"><span data-stu-id="1e1c9-142">The uncompressed size of the package data needed to launch the application.</span></span>

<a href="" id="locked"></a>**<span data-ttu-id="1e1c9-143">已锁定</span><span class="sxs-lookup"><span data-stu-id="1e1c9-143">Locked</span></span>**  
<span data-ttu-id="1e1c9-144">显示 **"是" 或 "** **否**"，具体取决于应用程序的程序包是否已在缓存中锁定。</span><span class="sxs-lookup"><span data-stu-id="1e1c9-144">Displays **Yes** or **No** depending on whether the application’s package is locked in the cache.</span></span>

<a href="" id="name"></a>**<span data-ttu-id="1e1c9-145">名称</span><span class="sxs-lookup"><span data-stu-id="1e1c9-145">Name</span></span>**  
<span data-ttu-id="1e1c9-146">应用程序名称。</span><span class="sxs-lookup"><span data-stu-id="1e1c9-146">The application name.</span></span>

<a href="" id="osd-file"></a>**<span data-ttu-id="1e1c9-147">OSD 文件</span><span class="sxs-lookup"><span data-stu-id="1e1c9-147">OSD File</span></span>**  
<span data-ttu-id="1e1c9-148">打开的软件描述符（OSD）文件的原始名称。</span><span class="sxs-lookup"><span data-stu-id="1e1c9-148">The original name of the Open Software Descriptor (OSD) file.</span></span>

<a href="" id="osd-path"></a>**<span data-ttu-id="1e1c9-149">OSD 路径</span><span class="sxs-lookup"><span data-stu-id="1e1c9-149">OSD Path</span></span>**  
<span data-ttu-id="1e1c9-150">OSD 文件的完整原始路径或 URL。</span><span class="sxs-lookup"><span data-stu-id="1e1c9-150">The full original path or URL to the OSD file.</span></span>

<a href="" id="package-name"></a>**<span data-ttu-id="1e1c9-151">程序包名称</span><span class="sxs-lookup"><span data-stu-id="1e1c9-151">Package Name</span></span>**  
<span data-ttu-id="1e1c9-152">程序包的名称。</span><span class="sxs-lookup"><span data-stu-id="1e1c9-152">The name of the package.</span></span>

<a href="" id="package-guid"></a>**<span data-ttu-id="1e1c9-153">程序包 GUID</span><span class="sxs-lookup"><span data-stu-id="1e1c9-153">Package GUID</span></span>**  
<span data-ttu-id="1e1c9-154">程序包的 GUID。</span><span class="sxs-lookup"><span data-stu-id="1e1c9-154">The GUID for the package.</span></span>

<a href="" id="package-size--mb-"></a>**<span data-ttu-id="1e1c9-155">程序包大小（MB）</span><span class="sxs-lookup"><span data-stu-id="1e1c9-155">Package Size (MB)</span></span>**  
<span data-ttu-id="1e1c9-156">程序包中的未压缩数据的总大小。</span><span class="sxs-lookup"><span data-stu-id="1e1c9-156">The total size of the uncompressed data in the package.</span></span>

<a href="" id="package-status"></a>**<span data-ttu-id="1e1c9-157">程序包状态</span><span class="sxs-lookup"><span data-stu-id="1e1c9-157">Package Status</span></span>**  
<span data-ttu-id="1e1c9-158">程序包的当前操作状态。</span><span class="sxs-lookup"><span data-stu-id="1e1c9-158">The current operational status of the package.</span></span>

<a href="" id="package-url"></a>**<span data-ttu-id="1e1c9-159">程序包 URL</span><span class="sxs-lookup"><span data-stu-id="1e1c9-159">Package URL</span></span>**  
<span data-ttu-id="1e1c9-160">程序包的 URL。</span><span class="sxs-lookup"><span data-stu-id="1e1c9-160">The URL for the package.</span></span>

<a href="" id="package-version"></a>**<span data-ttu-id="1e1c9-161">程序包版本</span><span class="sxs-lookup"><span data-stu-id="1e1c9-161">Package Version</span></span>**  
<span data-ttu-id="1e1c9-162">程序包的版本。</span><span class="sxs-lookup"><span data-stu-id="1e1c9-162">The version for the package.</span></span>

<a href="" id="package-version-guid"></a>**<span data-ttu-id="1e1c9-163">程序包版本 GUID</span><span class="sxs-lookup"><span data-stu-id="1e1c9-163">Package Version GUID</span></span>**  
<span data-ttu-id="1e1c9-164">程序包版本的 GUID。</span><span class="sxs-lookup"><span data-stu-id="1e1c9-164">The GUID for the package version.</span></span>

<a href="" id="running"></a>**<span data-ttu-id="1e1c9-165">Running</span><span class="sxs-lookup"><span data-stu-id="1e1c9-165">Running</span></span>**  
<span data-ttu-id="1e1c9-166">显示 **"是" 或 "** **否**"，具体取决于当前用户是否正在运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="1e1c9-166">Displays **Yes** or **No** depending on whether the current user is running the application.</span></span>

<a href="" id="source"></a>**<span data-ttu-id="1e1c9-167">来源</span><span class="sxs-lookup"><span data-stu-id="1e1c9-167">Source</span></span>**  
<span data-ttu-id="1e1c9-168">应用程序的来源（应用程序发布服务器的名称或直接从 OSD 文件添加的应用程序的 "本地"）。</span><span class="sxs-lookup"><span data-stu-id="1e1c9-168">Where the application came from—either the name of an application publishing server or "Local" for applications added from OSD files directly.</span></span>

<a href="" id="version"></a>**<span data-ttu-id="1e1c9-169">版本</span><span class="sxs-lookup"><span data-stu-id="1e1c9-169">Version</span></span>**  
<span data-ttu-id="1e1c9-170">应用程序版本。</span><span class="sxs-lookup"><span data-stu-id="1e1c9-170">The application version.</span></span>

## <span data-ttu-id="1e1c9-171">相关主题</span><span class="sxs-lookup"><span data-stu-id="1e1c9-171">Related topics</span></span>


[<span data-ttu-id="1e1c9-172">“应用程序”节点</span><span class="sxs-lookup"><span data-stu-id="1e1c9-172">Applications Node</span></span>](applications-node.md)

[<span data-ttu-id="1e1c9-173">“应用程序结果”窗格</span><span class="sxs-lookup"><span data-stu-id="1e1c9-173">Applications Results Pane</span></span>](applications-results-pane.md)

[<span data-ttu-id="1e1c9-174">Application Virtualization Client Management Console 参考</span><span class="sxs-lookup"><span data-stu-id="1e1c9-174">Application Virtualization Client Management Console Reference</span></span>](application-virtualization-client-management-console-reference.md)

 

 





