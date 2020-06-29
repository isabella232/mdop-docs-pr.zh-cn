---
title: UE-V 2.x 的同步触发器事件
description: UE-V 2.x 的同步触发器事件
author: dansimp
ms.assetid: 4ed71a13-6a4f-4376-996f-74b126536bbc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f3e89a0370790e7f462b2f469792128dba033460
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804040"
---
# <span data-ttu-id="3471b-103">UE-V 2.x 的同步触发器事件</span><span class="sxs-lookup"><span data-stu-id="3471b-103">Sync Trigger Events for UE-V 2.x</span></span>


<span data-ttu-id="3471b-104">Microsoft 用户体验虚拟化（UE-V）2.0、2.1 和 2.1 SP1 使你可以在所有加入域的设备上同步你的应用程序和 Windows 设置。</span><span class="sxs-lookup"><span data-stu-id="3471b-104">Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, and 2.1 SP1 lets you synchronize your application and Windows settings across all your domain-joined devices.</span></span> <span data-ttu-id="3471b-105">*同步触发器事件*定义了 ue-v Agent 何时将这些设置与设置存储位置同步。</span><span class="sxs-lookup"><span data-stu-id="3471b-105">*Sync trigger events* define when the UE-V Agent synchronizes those settings with the settings storage location.</span></span> <span data-ttu-id="3471b-106">UE-V 2 引入了一个名为*SyncProvider*的新*同步方法*。</span><span class="sxs-lookup"><span data-stu-id="3471b-106">UE-V 2 introduces a new *Sync Method* called the *SyncProvider*.</span></span> <span data-ttu-id="3471b-107">有关同步方法配置的详细信息，请参阅[ue-v 2. x 的同步方法](sync-methods-for-ue-v-2x-both-uevv2.md)。</span><span class="sxs-lookup"><span data-stu-id="3471b-107">For more information about Sync Method configuration, see [Sync Methods for UE-V 2.x](sync-methods-for-ue-v-2x-both-uevv2.md).</span></span>

## <span data-ttu-id="3471b-108">UE-V 2 同步触发事件</span><span class="sxs-lookup"><span data-stu-id="3471b-108">UE-V 2 Sync Trigger Events</span></span>


<span data-ttu-id="3471b-109">下表介绍了经典应用程序和 Windows 设置的触发器事件。</span><span class="sxs-lookup"><span data-stu-id="3471b-109">The following table explains the trigger events for classic applications and Windows settings.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="3471b-110">UE-V 2 触发器事件</span><span class="sxs-lookup"><span data-stu-id="3471b-110">UE-V 2 Trigger Event</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="3471b-111">Powerschool = SyncProvider</span><span class="sxs-lookup"><span data-stu-id="3471b-111">SyncMethod=SyncProvider</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="3471b-112">Powerschool = None</span><span class="sxs-lookup"><span data-stu-id="3471b-112">SyncMethod=None</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="3471b-113">Windows 登录</span><span class="sxs-lookup"><span data-stu-id="3471b-113">Windows Logon</span></span></strong></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="3471b-114">将从设置存储位置将应用程序和 Windows 设置导入到本地缓存。</span><span class="sxs-lookup"><span data-stu-id="3471b-114">Application and Windows settings are imported to the local cache from the settings storage location.</span></span></p></li>
<li><p><a href="https://technet.microsoft.com/library/dn458932.aspx#autosyncsettings2" data-raw-source="[Asynchronous Windows settings](https://technet.microsoft.com/library/dn458932.aspx#autosyncsettings2)"><span data-ttu-id="3471b-115">已应用异步 Windows 设置 </a> 。</span><span class="sxs-lookup"><span data-stu-id="3471b-115">Asynchronous Windows settings</a> are applied.</span></span></p></li>
<li><p><span data-ttu-id="3471b-116">将在下次 Windows 登录期间应用同步 Windows 设置。</span><span class="sxs-lookup"><span data-stu-id="3471b-116">Synchronous Windows settings will be applied during the next Windows logon.</span></span></p></li>
<li><p><span data-ttu-id="3471b-117">应用程序设置将在应用程序启动时应用。</span><span class="sxs-lookup"><span data-stu-id="3471b-117">Application settings will be applied when the application starts.</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="3471b-118">从 "设置" 存储位置直接读取 "应用程序" 和 "Windows 设置"。</span><span class="sxs-lookup"><span data-stu-id="3471b-118">Application and Windows settings are read directly from the settings storage location.</span></span></p></li>
<li><p><span data-ttu-id="3471b-119">应用了异步和同步 Windows 设置。</span><span class="sxs-lookup"><span data-stu-id="3471b-119">Asynchronous and synchronous Windows settings are applied.</span></span></p></li>
<li><p><span data-ttu-id="3471b-120">应用程序设置将在应用程序启动时应用。</span><span class="sxs-lookup"><span data-stu-id="3471b-120">Application settings will be applied when the application starts.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="3471b-121">Windows 注销</span><span class="sxs-lookup"><span data-stu-id="3471b-121">Windows Logoff</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3471b-122">将更改存储在本地，并将异步和同步 Windows 设置缓存和复制到设置存储位置服务器（如果可用）</span><span class="sxs-lookup"><span data-stu-id="3471b-122">Store changes locally and cache and copy asynchronous and synchronous Windows settings to the settings storage location server, if available</span></span></p></td>
<td align="left"><p><span data-ttu-id="3471b-123">将更改存储到异步和同步 Windows 设置存储位置</span><span class="sxs-lookup"><span data-stu-id="3471b-123">Store changes to asynchronous and synchronous Windows settings storage location</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="3471b-124">Windows Connect （RDP）/解锁</span><span class="sxs-lookup"><span data-stu-id="3471b-124">Windows Connect (RDP) / Unlock</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3471b-125">将任何异步 Windows 设置从 "设置存储位置" 同步到 "本地缓存" （如果可用）。</span><span class="sxs-lookup"><span data-stu-id="3471b-125">Synchronize any asynchronous Windows settings from settings storage location to local cache, if available.</span></span></p>
<p><span data-ttu-id="3471b-126">应用缓存的 Windows 设置</span><span class="sxs-lookup"><span data-stu-id="3471b-126">Apply cached Windows settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="3471b-127">从设置存储位置下载和应用异步 windows 设置</span><span class="sxs-lookup"><span data-stu-id="3471b-127">Download and apply asynchronous windows settings from settings storage location</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="3471b-128">Windows 断开连接（RDP）/锁</span><span class="sxs-lookup"><span data-stu-id="3471b-128">Windows Disconnect (RDP) / Lock</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3471b-129">将异步 Windows 设置更改存储到本地缓存。</span><span class="sxs-lookup"><span data-stu-id="3471b-129">Store asynchronous Windows settings changes to the local cache.</span></span></p>
<p><span data-ttu-id="3471b-130">将本地缓存中的任何异步 Windows 设置同步到设置存储位置（如果可用）</span><span class="sxs-lookup"><span data-stu-id="3471b-130">Synchronize any asynchronous Windows settings from the local cache to settings storage location, if available</span></span></p></td>
<td align="left"><p><span data-ttu-id="3471b-131">将异步 Windows 设置更改存储到设置存储位置</span><span class="sxs-lookup"><span data-stu-id="3471b-131">Store asynchronous Windows settings changes to the settings storage location</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="3471b-132">应用程序启动</span><span class="sxs-lookup"><span data-stu-id="3471b-132">Application start</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3471b-133">应用程序启动时从本地缓存应用应用程序设置</span><span class="sxs-lookup"><span data-stu-id="3471b-133">Apply application settings from local cache as the application starts</span></span></p></td>
<td align="left"><p><span data-ttu-id="3471b-134">应用程序启动时从设置存储位置应用应用程序设置</span><span class="sxs-lookup"><span data-stu-id="3471b-134">Apply application settings from settings storage location as the application starts</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="3471b-135">应用程序关闭</span><span class="sxs-lookup"><span data-stu-id="3471b-135">Application closes</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3471b-136">将任何应用程序设置更改存储到本地缓存并将设置复制到设置存储位置（如果可用）</span><span class="sxs-lookup"><span data-stu-id="3471b-136">Store any application settings changes to the local cache and copy settings to settings storage location, if available</span></span></p></td>
<td align="left"><p><span data-ttu-id="3471b-137">将任何应用程序设置更改存储到设置存储位置</span><span class="sxs-lookup"><span data-stu-id="3471b-137">Store any application settings changes to settings storage location</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="3471b-138">从公司设置中心运行同步控制器计划任务或 "立即同步"</span><span class="sxs-lookup"><span data-stu-id="3471b-138">Sync Controller Scheduled Task or “Sync Now” is run from the Company Settings Center</span></span></strong></p>
<p></p></td>
<td align="left"><p><span data-ttu-id="3471b-139">应用程序和 Windows 设置在设置存储位置和本地缓存之间同步。</span><span class="sxs-lookup"><span data-stu-id="3471b-139">Application and Windows settings are synchronized between the settings storage location and the local cache.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="3471b-140">注意</span><span class="sxs-lookup"><span data-stu-id="3471b-140">Note</span></span></strong><br/><p><span data-ttu-id="3471b-141">在应用程序关闭之前，不会将设置更改缓存到本地。</span><span class="sxs-lookup"><span data-stu-id="3471b-141">Settings changes are not cached locally until an application closes.</span></span> <span data-ttu-id="3471b-142">此触发器将不会导出对当前运行的应用程序所做的更改。</span><span class="sxs-lookup"><span data-stu-id="3471b-142">This trigger will not export changes made to a currently running application.</span></span></p>
<p><span data-ttu-id="3471b-143">对于 Windows 设置，这意味着不会在本地和导出任何更改，直到下一个锁定（异步）或注销（异步和同步）。</span><span class="sxs-lookup"><span data-stu-id="3471b-143">For Windows settings, this means that any changes will not be cached locally and exported until the next Lock (Asynchronous) or Logoff (Asynchronous and Synchronous).</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="3471b-144">在以下情况下应用设置：</span><span class="sxs-lookup"><span data-stu-id="3471b-144">Settings are applied in these cases:</span></span></p>
<ul>
<li><p><span data-ttu-id="3471b-145">将直接应用异步 Windows 设置。</span><span class="sxs-lookup"><span data-stu-id="3471b-145">Asynchronous Windows settings are applied directly.</span></span></p></li>
<li><p><span data-ttu-id="3471b-146">应用程序设置在应用程序启动时应用。</span><span class="sxs-lookup"><span data-stu-id="3471b-146">Application settings are applied when the application starts.</span></span></p></li>
<li><p><span data-ttu-id="3471b-147">在下次 Windows 登录期间，将应用异步和同步 Windows 设置。</span><span class="sxs-lookup"><span data-stu-id="3471b-147">Both asynchronous and synchronous Windows settings are applied during the next Windows logon.</span></span></p></li>
<li><p><span data-ttu-id="3471b-148">Windows 应用（AppX）设置将在下一次刷新期间应用。</span><span class="sxs-lookup"><span data-stu-id="3471b-148">Windows app (AppX) settings are applied during the next refresh.</span></span> <span data-ttu-id="3471b-149"><a href="https://technet.microsoft.com/library/dn458944.aspx" data-raw-source="[Monitor Application Settings](https://technet.microsoft.com/library/dn458944.aspx)">有关详细信息，请参阅监视应用程序设置 </a> 。</span><span class="sxs-lookup"><span data-stu-id="3471b-149">See <a href="https://technet.microsoft.com/library/dn458944.aspx" data-raw-source="[Monitor Application Settings](https://technet.microsoft.com/library/dn458944.aspx)">Monitor Application Settings</a> for more information.</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="3471b-150">NA</span><span class="sxs-lookup"><span data-stu-id="3471b-150">NA</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="3471b-151">在远程存储上更新的异步设置 \*</span><span class="sxs-lookup"><span data-stu-id="3471b-151">Asynchronous Settings updated on remote store\*</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3471b-152">从缓存加载和应用新的异步设置。</span><span class="sxs-lookup"><span data-stu-id="3471b-152">Load and apply new asynchronous settings from the cache.</span></span></p></td>
<td align="left"><p><span data-ttu-id="3471b-153">从中央服务器加载和应用设置</span><span class="sxs-lookup"><span data-stu-id="3471b-153">Load and apply settings from central server</span></span></p></td>
</tr>
</tbody>
</table>








## <span data-ttu-id="3471b-154">相关主题</span><span class="sxs-lookup"><span data-stu-id="3471b-154">Related topics</span></span>


[<span data-ttu-id="3471b-155">UE-V 2.x 的技术参考</span><span class="sxs-lookup"><span data-stu-id="3471b-155">Technical Reference for UE-V 2.x</span></span>](technical-reference-for-ue-v-2x-both-uevv2.md)

[<span data-ttu-id="3471b-156">更改 UE-V 2 x 计划任务的频率</span><span class="sxs-lookup"><span data-stu-id="3471b-156">Changing the Frequency of UE-V 2.x Scheduled Tasks</span></span>](changing-the-frequency-of-ue-v-2x-scheduled-tasks-both-uevv2.md)

[<span data-ttu-id="3471b-157">选择 UE-V 2 的配置方法。</span><span class="sxs-lookup"><span data-stu-id="3471b-157">Choose the Configuration Method for UE-V 2.x</span></span>](https://technet.microsoft.com/library/dn458891.aspx#config)









