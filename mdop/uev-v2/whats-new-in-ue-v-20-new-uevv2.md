---
title: UE-V 2.0 中的新增功能
description: UE-V 2.0 中的新增功能
author: dansimp
ms.assetid: 5d852beb-f293-4e3a-a33b-c40df59a7515
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a7566bd82432dcf7e4c46e1fa3e66e55d1515b79
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803673"
---
# <span data-ttu-id="a3a8a-103">UE-V 2.0 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="a3a8a-103">What's New in UE-V 2.0</span></span>


<span data-ttu-id="a3a8a-104">Microsoft 用户体验虚拟化（UE-V）2.0 提供了与 UE-V 1.0 相比的这些新功能和功能。</span><span class="sxs-lookup"><span data-stu-id="a3a8a-104">Microsoft User Experience Virtualization (UE-V) 2.0 provides these new features and functionality compared to UE-V 1.0.</span></span> <span data-ttu-id="a3a8a-105">[Microsoft 用户体验虚拟化（ue-v）2.0 发行说明](microsoft-user-experience-virtualization--ue-v--20-release-notesuevv2.md)提供了有关 ue-v 2.0 版本的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a3a8a-105">The [Microsoft User Experience Virtualization (UE-V) 2.0 Release Notes](microsoft-user-experience-virtualization--ue-v--20-release-notesuevv2.md) provide more information about the UE-V 2.0 release.</span></span>

## <span data-ttu-id="a3a8a-106">不再需要客户端缓存（CSC）</span><span class="sxs-lookup"><span data-stu-id="a3a8a-106">Client-side cache (CSC) no longer required</span></span>


<span data-ttu-id="a3a8a-107">此版本的 UE-V 引入了**同步提供程序**，这将替代 Windows 脱机文件功能的要求以支持设置的客户端缓存。</span><span class="sxs-lookup"><span data-stu-id="a3a8a-107">This version of UE-V introduces the **sync provider**, which replaces the requirement for the Windows Offline Files feature to support a client-side cache of settings.</span></span>

<span data-ttu-id="a3a8a-108">虽然 UE-V 仅用于在应用程序打开、关闭或 Windows 锁定或注销时同步设置，或者在登录或注销时同步设置，请参阅同步提供程序 .。。</span><span class="sxs-lookup"><span data-stu-id="a3a8a-108">Whereas UE-V used to synchronize settings only when an application opened, closed, or when Windows locked or unlocked, or at logon or logoff, the sync provider also …</span></span>

-   <span data-ttu-id="a3a8a-109">使用 "**触发器事件**" 在带外同步本地应用程序和 Windows 设置</span><span class="sxs-lookup"><span data-stu-id="a3a8a-109">Synchronizes local application and Windows settings out-of-band using "**trigger events**"</span></span>

-   <span data-ttu-id="a3a8a-110">使用**计划任务**以你为企业要求选择的任何间隔同步设置存储包（默认情况下，每隔30分钟）</span><span class="sxs-lookup"><span data-stu-id="a3a8a-110">Uses a **scheduled task** to sync the settings storage package in any interval you choose for your enterprise requirements (every 30 minutes by default)</span></span>

<span data-ttu-id="a3a8a-111">某些条件提供更频繁的同步。</span><span class="sxs-lookup"><span data-stu-id="a3a8a-111">Certain conditions provide more frequent synchronization.</span></span>

-   <span data-ttu-id="a3a8a-112">当用户单击新的公司设置中心应用程序中的 "**立即同步**" 按钮时，设置将同步。</span><span class="sxs-lookup"><span data-stu-id="a3a8a-112">Settings synchronize when the user clicks the **Sync Now** button in the new Company Settings Center application.</span></span>

-   <span data-ttu-id="a3a8a-113">同步提供程序也可以在不等待计划同步任务的情况下为单个应用程序启动。</span><span class="sxs-lookup"><span data-stu-id="a3a8a-113">The sync provider can also start for a single application without waiting for the scheduled synchronization task.</span></span> <span data-ttu-id="a3a8a-114">例如，当应用程序关闭时，任何设置更改都将写入本地缓存，同步提供程序进程将异步运行以将这些新的设置更改移动到设置存储位置。</span><span class="sxs-lookup"><span data-stu-id="a3a8a-114">For example, when an application is closed, any settings changes are written to the local cache, and the sync provider process runs asynchronously to move those new settings changes to the settings storage location.</span></span>

## <span data-ttu-id="a3a8a-115">Windows 应用同步</span><span class="sxs-lookup"><span data-stu-id="a3a8a-115">Windows app synchronization</span></span>


<span data-ttu-id="a3a8a-116">Windows 应用的开发人员可以定义要同步的设置（如果有），并且这些设置现在可以通过 UE-V 捕获并同步。</span><span class="sxs-lookup"><span data-stu-id="a3a8a-116">The developer of a Windows app can define which settings, if any, are to be synchronized, and these settings can now be captured and synchronized with UE-V.</span></span>

<span data-ttu-id="a3a8a-117">默认情况下，UE-V 同步 Windows 8 和 Windows 8.1 中包含的许多 Windows 应用的设置。</span><span class="sxs-lookup"><span data-stu-id="a3a8a-117">By default, UE-V synchronizes the settings of many of the Windows apps included in Windows 8 and Windows 8.1.</span></span> <span data-ttu-id="a3a8a-118">你可以通过 Windows PowerShell、Windows Management Instrumentation （WMI）或组策略修改已同步应用的列表。</span><span class="sxs-lookup"><span data-stu-id="a3a8a-118">You can modify the list of synchronized apps with Windows PowerShell, Windows Management Instrumentation (WMI), or Group Policy.</span></span>

<span data-ttu-id="a3a8a-119">**注意** 如果域用户将他们的登录凭据链接到其 Microsoft 帐户，UE-V 不会同步 Windows 应用设置。</span><span class="sxs-lookup"><span data-stu-id="a3a8a-119">**Note** UE-V does not synchronize Windows app settings if the domain users link their sign-in credentials to their Microsoft account.</span></span> <span data-ttu-id="a3a8a-120">此链接会将设置同步到 Microsoft OneDrive，因此 UE-V 仅同步桌面应用程序。</span><span class="sxs-lookup"><span data-stu-id="a3a8a-120">This linking synchronizes settings to Microsoft OneDrive so UE-V only synchronizes the desktop applications.</span></span>

 

## <span data-ttu-id="a3a8a-121">Microsoft 帐户链接</span><span class="sxs-lookup"><span data-stu-id="a3a8a-121">Microsoft account linking</span></span>


<span data-ttu-id="a3a8a-122">使用 Microsoft 帐户登录或将 Microsoft 帐户链接到域帐户时，通过 OneDrive 的设置同步是 Windows 8 的新增功能。</span><span class="sxs-lookup"><span data-stu-id="a3a8a-122">Settings synchronization via OneDrive is new to Windows 8 when you are signed in with a Microsoft account or if you link your Microsoft account to your domain account.</span></span> <span data-ttu-id="a3a8a-123">如果域用户使用 UE-V 并已登录到 Microsoft 帐户，那么 .。。</span><span class="sxs-lookup"><span data-stu-id="a3a8a-123">If a domain user uses UE-V and has signed in to a Microsoft account, then…</span></span>

-   <span data-ttu-id="a3a8a-124">UE-V 仅同步桌面应用程序的设置</span><span class="sxs-lookup"><span data-stu-id="a3a8a-124">UE-V only synchronizes settings for desktop applications</span></span>

-   <span data-ttu-id="a3a8a-125">Microsoft 帐户处理 Windows 应用设置和 Windows 桌面设置</span><span class="sxs-lookup"><span data-stu-id="a3a8a-125">Microsoft account handles Windows app settings and Windows desktop settings</span></span>

## <span data-ttu-id="a3a8a-126">公司设置中心</span><span class="sxs-lookup"><span data-stu-id="a3a8a-126">Company Settings Center</span></span>


<span data-ttu-id="a3a8a-127">你可以通过名为 "公司设置中心" 的 UE-V 2 中的应用程序向你的用户提供一些设置的控制。</span><span class="sxs-lookup"><span data-stu-id="a3a8a-127">You can provide your users with some control over which settings are synchronized through an application in UE-V 2 called Company Settings Center.</span></span> <span data-ttu-id="a3a8a-128">公司设置中心与 UE-V Agent 一起安装，用户可以从 "控制面板"、"**开始**" 菜单或 "**开始**" 屏幕以及从 ue-v 通知区域图标访问它。</span><span class="sxs-lookup"><span data-stu-id="a3a8a-128">Company Settings Center is installed along with the UE-V Agent, and users can access it from Control Panel, the **Start** menu or **Start** screen, and from the UE-V notification area icon.</span></span>

<span data-ttu-id="a3a8a-129">公司设置中心显示哪些设置是同步的，并且允许用户查看 UE-V 的同步状态。</span><span class="sxs-lookup"><span data-stu-id="a3a8a-129">Company Settings Center displays which settings are synchronized and lets users see the synchronization status of UE-V.</span></span> <span data-ttu-id="a3a8a-130">如果你允许，用户可以使用公司设置中心来选择要同步的设置。</span><span class="sxs-lookup"><span data-stu-id="a3a8a-130">If you let them, users can use Company Settings Center to select which settings to synchronize.</span></span> <span data-ttu-id="a3a8a-131">他们还可以单击 "**立即同步**" 按钮，立即同步所有设置。</span><span class="sxs-lookup"><span data-stu-id="a3a8a-131">They can also click the **Sync Now** button to synchronize all settings immediately.</span></span>






## <span data-ttu-id="a3a8a-132">相关主题</span><span class="sxs-lookup"><span data-stu-id="a3a8a-132">Related topics</span></span>


[<span data-ttu-id="a3a8a-133">UE-V 2.x 入门</span><span class="sxs-lookup"><span data-stu-id="a3a8a-133">Get Started with UE-V 2.x</span></span>](get-started-with-ue-v-2x-new-uevv2.md)

[<span data-ttu-id="a3a8a-134">准备 UE-V 2. x 部署</span><span class="sxs-lookup"><span data-stu-id="a3a8a-134">Prepare a UE-V 2.x Deployment</span></span>](prepare-a-ue-v-2x-deployment-new-uevv2.md)

[<span data-ttu-id="a3a8a-135">Microsoft 用户体验虚拟化 (UE-V) 2.0 发行说明</span><span class="sxs-lookup"><span data-stu-id="a3a8a-135">Microsoft User Experience Virtualization (UE-V) 2.0 Release Notes</span></span>](microsoft-user-experience-virtualization--ue-v--20-release-notesuevv2.md)

 

 





