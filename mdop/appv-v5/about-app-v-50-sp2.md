---
title: 关于 App-V 5.0 SP2
description: 关于 App-V 5.0 SP2
author: dansimp
ms.assetid: 16ca8452-cef2-464e-b4b5-c10d4630fa6a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9a476f3bf273717b5a85a4244c5796f893b0c617
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798681"
---
# <span data-ttu-id="a3cb9-103">关于 App-V 5.0 SP2</span><span class="sxs-lookup"><span data-stu-id="a3cb9-103">About App-V 5.0 SP2</span></span>


<span data-ttu-id="a3cb9-104">App-v 5.0 SP2 提供改进的集成平台、更灵活的虚拟化和针对虚拟化应用程序的强大管理。</span><span class="sxs-lookup"><span data-stu-id="a3cb9-104">App-V 5.0SP2 provides an improved integrated platform, more flexible virtualization, and powerful management for virtualized applications.</span></span> <span data-ttu-id="a3cb9-105">有关详细信息，请参阅[App-V 5.0 概述](https://go.microsoft.com/fwlink/p/?LinkId=325265)（ https://go.microsoft.com/fwlink/?LinkId=325265) 。</span><span class="sxs-lookup"><span data-stu-id="a3cb9-105">For more information see, [App-V 5.0 Overview](https://go.microsoft.com/fwlink/p/?LinkId=325265) (https://go.microsoft.com/fwlink/?LinkId=325265).</span></span>

## <span data-ttu-id="a3cb9-106">标准 App V 5.0 SP2 功能中的更改</span><span class="sxs-lookup"><span data-stu-id="a3cb9-106">Changes in Standard App-V 5.0SP2 Functionality</span></span>


<span data-ttu-id="a3cb9-107">以下各节包含有关 App-v 5.0 SP2 的标准功能更改的信息。</span><span class="sxs-lookup"><span data-stu-id="a3cb9-107">The following sections contain information about the changes in standard functionality for App-V 5.0SP2.</span></span>

### <a href="" id="bkmk-sp2-supported-cfg"></a><span data-ttu-id="a3cb9-108">Windows Server 2012 R2 和 Windows 8.1 的支持</span><span class="sxs-lookup"><span data-stu-id="a3cb9-108">Support for Windows Server 2012 R2 and Windows 8.1</span></span>

<span data-ttu-id="a3cb9-109">App-v 5.0 包括对 Windows Server 2012 R2 和 Windows 8.1 的支持</span><span class="sxs-lookup"><span data-stu-id="a3cb9-109">App-V 5.0 includes support for Windows Server 2012 R2 and Windows 8.1</span></span>

### <a href="" id="-------------app-v-5-0-sp2-now-supports-folder-redirection-for-the-user-s-roaming-appdata-directory"></a> <span data-ttu-id="a3cb9-110">App-v 5.0 SP2 现在支持用户的漫游 AppData 目录的文件夹重定向</span><span class="sxs-lookup"><span data-stu-id="a3cb9-110">App-V 5.0SP2 now supports folder redirection for the user’s roaming AppData directory</span></span>

<span data-ttu-id="a3cb9-111">App-v 5.0 SP2 支持漫游 AppData （% AppData%）文件夹重定向。</span><span class="sxs-lookup"><span data-stu-id="a3cb9-111">App-V 5.0SP2 supports roaming AppData (%AppData%) folder redirection.</span></span> <span data-ttu-id="a3cb9-112">有关详细信息，请参阅[规划使用 app-v 的文件夹重定向](planning-to-use-folder-redirection-with-app-v.md)。</span><span class="sxs-lookup"><span data-stu-id="a3cb9-112">For more information, see the [Planning to Use Folder Redirection with App-V](planning-to-use-folder-redirection-with-app-v.md).</span></span>

### <a href="" id="bkmk-pkg-upgr-pendg-tasks"></a><span data-ttu-id="a3cb9-113">程序包升级改进和挂起的任务</span><span class="sxs-lookup"><span data-stu-id="a3cb9-113">Package upgrade improvements and pending tasks</span></span>

<span data-ttu-id="a3cb9-114">在 App-v 5.0 SP2 中，当发布了更新版本的程序包或连接组时，不再提示关闭正在运行的虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="a3cb9-114">In App-V 5.0SP2, you are no longer prompted to close a running virtual application when a newer version of the package or connection group is published.</span></span> <span data-ttu-id="a3cb9-115">如果尝试执行相关任务时程序包或连接组正在使用，则会显示一条消息，指示该对象正在使用，并且稍后将尝试该操作。</span><span class="sxs-lookup"><span data-stu-id="a3cb9-115">If a package or connection group is in use when you try to perform a related task, a message displays to indicate that the object is in use, and that the operation will be attempted at a later time.</span></span>

<span data-ttu-id="a3cb9-116">将根据以下规则执行已置入挂起状态的任务：</span><span class="sxs-lookup"><span data-stu-id="a3cb9-116">Tasks that have been placed in a pending state will be performed according to the following rules:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a3cb9-117">任务类型</span><span class="sxs-lookup"><span data-stu-id="a3cb9-117">Task type</span></span></th>
<th align="left"><span data-ttu-id="a3cb9-118">适用规则</span><span class="sxs-lookup"><span data-stu-id="a3cb9-118">Applicable rule</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a3cb9-119">基于用户的任务，例如将程序包发布给用户</span><span class="sxs-lookup"><span data-stu-id="a3cb9-119">User-based task, e.g., publishing a package to a user</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3cb9-120">将在用户注销后执行挂起的任务，然后重新登录。</span><span class="sxs-lookup"><span data-stu-id="a3cb9-120">The pending task will be performed after the user logs off and then logs back on.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a3cb9-121">基于全球的任务，例如，全局启用连接组</span><span class="sxs-lookup"><span data-stu-id="a3cb9-121">Globally based task, e.g., enabling a connection group globally</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3cb9-122">当计算机关闭然后重新启动时，将执行挂起的任务。</span><span class="sxs-lookup"><span data-stu-id="a3cb9-122">The pending task will be performed when the computer is shut down and then restarted.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="a3cb9-123">当任务置于挂起状态时，App-v 客户端还会为挂起任务生成注册表项，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a3cb9-123">When a task is placed in a pending state, the App-V client also generates a registry key for the pending task, as follows:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a3cb9-124">基于用户或基于全球的任务</span><span class="sxs-lookup"><span data-stu-id="a3cb9-124">User-based or globally based task</span></span></th>
<th align="left"><span data-ttu-id="a3cb9-125">注册表项的生成位置</span><span class="sxs-lookup"><span data-stu-id="a3cb9-125">Where the registry key is generated</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a3cb9-126">基于用户的任务</span><span class="sxs-lookup"><span data-stu-id="a3cb9-126">User-based tasks</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3cb9-127">KEY_CURRENT_USER \Software\Microsoft\AppV\Client\PendingTasks</span><span class="sxs-lookup"><span data-stu-id="a3cb9-127">KEY_CURRENT_USER\Software\Microsoft\AppV\Client\PendingTasks</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a3cb9-128">基于全球的任务</span><span class="sxs-lookup"><span data-stu-id="a3cb9-128">Globally based tasks</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3cb9-129">HKEY_LOCAL_MACHINE \Software\Microsoft\AppV\Client\PendingTasks</span><span class="sxs-lookup"><span data-stu-id="a3cb9-129">HKEY_LOCAL_MACHINE\Software\Microsoft\AppV\Client\PendingTasks</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="a3cb9-130">使用 App-v 5.0 虚拟化 Microsoft Office 2013 和 Microsoft Office 2010</span><span class="sxs-lookup"><span data-stu-id="a3cb9-130">Virtualizing Microsoft Office 2013 and Microsoft Office 2010 using App-V 5.0</span></span>

<span data-ttu-id="a3cb9-131">有关 App-v 5.0 支持的 Microsoft Office 方案的详细信息，请使用以下链接。</span><span class="sxs-lookup"><span data-stu-id="a3cb9-131">Use the following link for more information about App-V 5.0 supported Microsoft Office scenarios.</span></span>

[<span data-ttu-id="a3cb9-132">虚拟化适用于 Application Virtualization (App-V) 5.0 的 Microsoft Office 2013</span><span class="sxs-lookup"><span data-stu-id="a3cb9-132">Virtualizing Microsoft Office 2013 for Application Virtualization (App-V) 5.0</span></span>](../solutions/virtualizing-microsoft-office-2013-for-application-virtualization--app-v--50-solutions.md)

<span data-ttu-id="a3cb9-133">**注意** 本文档重点介绍如何创建 Microsoft Office 2013 App-v 5.0 程序包。</span><span class="sxs-lookup"><span data-stu-id="a3cb9-133">**Note** This document focuses on creating a Microsoft Office 2013 App-V 5.0 Package.</span></span> <span data-ttu-id="a3cb9-134">但是，它还提供了有关 Microsoft Office 2010 的应用程序与 app-v 5.0 相关的信息。</span><span class="sxs-lookup"><span data-stu-id="a3cb9-134">However, it also provides information about scenarios for Microsoft Office 2010 with App-V 5.0.</span></span>

 

### <a href="" id="-------------app-v-5-0-client-management-user-interface-application"></a> <span data-ttu-id="a3cb9-135">App-v 5.0 客户端管理用户界面应用程序</span><span class="sxs-lookup"><span data-stu-id="a3cb9-135">App-V 5.0 Client Management User Interface Application</span></span>

<span data-ttu-id="a3cb9-136">在早期版本的 App-v 5.0 中，客户端管理用户界面（UI）随 App-v 5.0 客户端安装提供。</span><span class="sxs-lookup"><span data-stu-id="a3cb9-136">In previous versions of App-V 5.0 the Client Management User Interface (UI) was provided with the App-V 5.0 Client installation.</span></span> <span data-ttu-id="a3cb9-137">有了 app-v 5.0 SP2，这就不再是这样。</span><span class="sxs-lookup"><span data-stu-id="a3cb9-137">With App-V 5.0SP2 this is no longer the case.</span></span> <span data-ttu-id="a3cb9-138">管理员现在可以选择将 app-v 5.0 客户端 UI 部署为虚拟应用程序（使用所有受支持的应用程序 V 部署配置）或安装的应用程序。</span><span class="sxs-lookup"><span data-stu-id="a3cb9-138">Administrators now have the option to deploy the App-V 5.0 Client UI as a Virtual Application (using all supported App-V deployment configurations) or as an installed application.</span></span>

<span data-ttu-id="a3cb9-139">有关详细信息，请参阅[Microsoft Application Virtualization 5.0 客户端 UI 应用程序](https://go.microsoft.com/fwlink/p/?LinkId=386345)（ https://go.microsoft.com/fwlink/?LinkId=386345) 。</span><span class="sxs-lookup"><span data-stu-id="a3cb9-139">For more information see [Microsoft Application Virtualization 5.0 Client UI Application](https://go.microsoft.com/fwlink/p/?LinkId=386345) (https://go.microsoft.com/fwlink/?LinkId=386345).</span></span>

### <span data-ttu-id="a3cb9-140">并行（SxS）程序集自动打包和部署</span><span class="sxs-lookup"><span data-stu-id="a3cb9-140">Side-by-Side (SxS) Assembly Automatic Packaging and Deployment</span></span>

<span data-ttu-id="a3cb9-141">App-v 5.0 SP2 现在会自动检测运行 App-v 5.0 SP2 客户端的计算机上的并行（SxS）程序集和部署。</span><span class="sxs-lookup"><span data-stu-id="a3cb9-141">App-V 5.0SP2 now automatically detects side-by-side (SxS) assemblies, and deployment on the computer running the App-V 5.0SP2 client.</span></span> <span data-ttu-id="a3cb9-142">SxS 程序集主要由 VC + + 运行时依赖项或 MSXML 组成。</span><span class="sxs-lookup"><span data-stu-id="a3cb9-142">A SxS assembly primarily consists of VC++ run-time dependencies or MSXML.</span></span> <span data-ttu-id="a3cb9-143">在早期版本的 App-v 中，具有 VC 运行时依赖项的虚拟应用程序需要在运行 App-v 5.0 SP2 客户端的计算机上本地运行这些依赖关系。</span><span class="sxs-lookup"><span data-stu-id="a3cb9-143">In previous versions of App-V, virtual applications that had dependencies on VC run-times required these dependencies to be locally on the computer running the App-V 5.0SP2 client.</span></span>

<span data-ttu-id="a3cb9-144">现在支持以下功能：</span><span class="sxs-lookup"><span data-stu-id="a3cb9-144">The following functionality is now supported:</span></span>

-   <span data-ttu-id="a3cb9-145">App-v 5.0 sequencer 会自动捕获程序包中的 SxS 程序集，而不管是否已在运行 sequencer 的计算机上安装了 VC 运行时。</span><span class="sxs-lookup"><span data-stu-id="a3cb9-145">The App-V 5.0 sequencer automatically captures the SxS assembly in the package regardless of whether the VC run-time has already been installed on the computer running the sequencer.</span></span>

-   <span data-ttu-id="a3cb9-146">App-v 5.0 客户端会根据需要在发布时将所需的 SxS 程序集自动安装到运行客户端的计算机。</span><span class="sxs-lookup"><span data-stu-id="a3cb9-146">The App-V 5.0 client automatically installs the required SxS assembly to the computer running the client as required at publishing time.</span></span>

-   <span data-ttu-id="a3cb9-147">App-v 5.0 sequencer 使用 sequencer 报告机制报告 VC 运行时依赖关系。</span><span class="sxs-lookup"><span data-stu-id="a3cb9-147">The App-V 5.0 sequencer reports the VC run-time dependency using the sequencer reporting mechanism.</span></span>

-   <span data-ttu-id="a3cb9-148">现在，App-v 5.0 sequencer 允许你在运行 sequencer 的计算机上已提供依赖项的情况中排除 VC 运行时依赖关系。</span><span class="sxs-lookup"><span data-stu-id="a3cb9-148">The App-V 5.0 sequencer now allows you to exclude the VC run-time dependency in the event that the dependency is already available on the computer running the sequencer.</span></span>

### <span data-ttu-id="a3cb9-149">发布刷新改进</span><span class="sxs-lookup"><span data-stu-id="a3cb9-149">Publishing Refresh Improvements</span></span>

<span data-ttu-id="a3cb9-150">App-v 5.0 支持添加了多个功能，以提高为特定用户刷新一组应用程序的总体体验。</span><span class="sxs-lookup"><span data-stu-id="a3cb9-150">App-V 5.0 supports several features were added to improve the overall experience of refreshing a set of applications for a specific user.</span></span>

<span data-ttu-id="a3cb9-151">以下列表显示了发布刷新增强功能：</span><span class="sxs-lookup"><span data-stu-id="a3cb9-151">The following list displays the publishing refresh enhancements:</span></span>

<span data-ttu-id="a3cb9-152">以下列表包含有关如何启用新的发布刷新改进的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a3cb9-152">The following list contains more information about how to enable the new publishing refresh improvements.</span></span>

-   <span data-ttu-id="a3cb9-153">**EnablePublishingRefreshUI** -为运行 App-v 5.0 客户端的计算机启用发布刷新进度栏。</span><span class="sxs-lookup"><span data-stu-id="a3cb9-153">**EnablePublishingRefreshUI** - Enables the publishing refresh progress bar for the computer running the App-V 5.0 Client.</span></span>

-   <span data-ttu-id="a3cb9-154">**HideUI** -在手动同步期间隐藏发布刷新进度栏。</span><span class="sxs-lookup"><span data-stu-id="a3cb9-154">**HideUI** - Hides the publishing refresh progress bar during a manual sync.</span></span>

### <span data-ttu-id="a3cb9-155">新的客户端配置设置</span><span class="sxs-lookup"><span data-stu-id="a3cb9-155">New Client Configuration Setting</span></span>

<span data-ttu-id="a3cb9-156">以下新的客户端配置设置可用于 App-v 5.0 SP2：</span><span class="sxs-lookup"><span data-stu-id="a3cb9-156">The following new client configuration setting is available with App-V 5.0 SP2:</span></span>

<span data-ttu-id="a3cb9-157">**EnableDynamicVirtualization** -支持要虚拟化并与虚拟应用程序一起运行的支持的 Shell 扩展、浏览器帮助程序对象和 Active X 控件。</span><span class="sxs-lookup"><span data-stu-id="a3cb9-157">**EnableDynamicVirtualization** - Enables supported Shell Extensions, Browser Helper Objects, and Active X controls to be virtualized and run with virtual applications.</span></span>

<span data-ttu-id="a3cb9-158">有关详细信息，请参阅[关于客户端配置设置](about-client-configuration-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="a3cb9-158">For more information, see [About Client Configuration Settings](about-client-configuration-settings.md).</span></span>

### <a href="" id="-------------app-v-5-0-shell-extensions"></a> <span data-ttu-id="a3cb9-159">App-v 5.0 外壳扩展</span><span class="sxs-lookup"><span data-stu-id="a3cb9-159">App-V 5.0 Shell extensions</span></span>

<span data-ttu-id="a3cb9-160">现在，app-v 5.0 SP2 支持外壳扩展。</span><span class="sxs-lookup"><span data-stu-id="a3cb9-160">App-V 5.0 SP2 now supports shell extensions.</span></span>

<span data-ttu-id="a3cb9-161">有关详细信息，请参阅[创建和管理 app-v 5.0 虚拟化应用程序](creating-and-managing-app-v-50-virtualized-applications.md)的 APP-V **5.0 sp2 shell 扩展支持**部分。</span><span class="sxs-lookup"><span data-stu-id="a3cb9-161">For more information see the **App-V 5.0SP2 shell extension support** section of [Creating and Managing App-V 5.0 Virtualized Applications](creating-and-managing-app-v-50-virtualized-applications.md).</span></span>

## <a href="" id="---------app-v-5-0-documentation-updates"></a> <span data-ttu-id="a3cb9-162">App-v 5.0 文档更新</span><span class="sxs-lookup"><span data-stu-id="a3cb9-162">App-V 5.0 documentation updates</span></span>


<span data-ttu-id="a3cb9-163">App-v 5.0 SP2 提供以下方案的更新文档：</span><span class="sxs-lookup"><span data-stu-id="a3cb9-163">App-V 5.0 SP2 provides updated documentation for the following scenarios:</span></span>

-   [<span data-ttu-id="a3cb9-164">从以前版本迁移</span><span class="sxs-lookup"><span data-stu-id="a3cb9-164">Migrating from a Previous Version</span></span>](migrating-from-a-previous-version-app-v-50.md)

-   [<span data-ttu-id="a3cb9-165">关于 App-V 5.0</span><span class="sxs-lookup"><span data-stu-id="a3cb9-165">About App-V 5.0</span></span>](about-app-v-50.md)

-   <span data-ttu-id="a3cb9-166">[关于应用-V 5.0 报告](about-app-v-50-reporting.md)（常见问题部分）</span><span class="sxs-lookup"><span data-stu-id="a3cb9-166">[About App-V 5.0 Reporting](about-app-v-50-reporting.md) (frequently asked questions section)</span></span>

## <span data-ttu-id="a3cb9-167">如何获取 MDOP 技术</span><span class="sxs-lookup"><span data-stu-id="a3cb9-167">How to Get MDOP Technologies</span></span>


<span data-ttu-id="a3cb9-168">App-v 5.0 是 Microsoft 桌面优化包（MDOP）的一部分。</span><span class="sxs-lookup"><span data-stu-id="a3cb9-168">App-V 5.0 is a part of the Microsoft Desktop Optimization Pack (MDOP).</span></span> <span data-ttu-id="a3cb9-169">MDOP 是 Microsoft 软件保障的一部分。</span><span class="sxs-lookup"><span data-stu-id="a3cb9-169">MDOP is part of Microsoft Software Assurance.</span></span> <span data-ttu-id="a3cb9-170">有关 Microsoft 软件保证和获取 MDOP 的详细信息，请参阅[如何获取 mdop](https://go.microsoft.com/fwlink/?LinkId=322049) （ https://go.microsoft.com/fwlink/?LinkId=322049) 。</span><span class="sxs-lookup"><span data-stu-id="a3cb9-170">For more information about Microsoft Software Assurance and acquiring MDOP, see [How Do I Get MDOP](https://go.microsoft.com/fwlink/?LinkId=322049) (https://go.microsoft.com/fwlink/?LinkId=322049).</span></span>






## <span data-ttu-id="a3cb9-171">相关主题</span><span class="sxs-lookup"><span data-stu-id="a3cb9-171">Related topics</span></span>


[<span data-ttu-id="a3cb9-172">App-V 5.0 SP2 发行说明</span><span class="sxs-lookup"><span data-stu-id="a3cb9-172">Release Notes for App-V 5.0 SP2</span></span>](release-notes-for-app-v-50-sp2.md)

 

 





