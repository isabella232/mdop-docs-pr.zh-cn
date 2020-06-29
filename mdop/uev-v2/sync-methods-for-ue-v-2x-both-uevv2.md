---
title: UE-V 2.x 的同步方法
description: UE-V 2.x 的同步方法
author: dansimp
ms.assetid: af0ae894-dfdc-41d2-927b-c2ab1b355ffe
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a163442e2ab3dbd777aca133b13b0086cdb8ae1a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803396"
---
# <span data-ttu-id="3423e-103">UE-V 2.x 的同步方法</span><span class="sxs-lookup"><span data-stu-id="3423e-103">Sync Methods for UE-V 2.x</span></span>


<span data-ttu-id="3423e-104">Microsoft 用户体验虚拟化（UE-V）2.0、2.1 和 2.1 SP1 代理使你可以将用户的应用程序和 Windows 设置与设置存储位置同步。</span><span class="sxs-lookup"><span data-stu-id="3423e-104">The Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, and 2.1 SP1 Agent lets you synchronize users’ application and Windows settings with the settings storage location.</span></span> <span data-ttu-id="3423e-105">*同步方法*配置定义了 ue-v Agent 如何将这些设置上载并下载到设置存储位置。</span><span class="sxs-lookup"><span data-stu-id="3423e-105">The *Sync Method* configuration defines how the UE-V Agent uploads and downloads those settings to the settings storage location.</span></span> <span data-ttu-id="3423e-106">UE-V 2. x 引入了名为*SyncProvider*的新 powerschool。</span><span class="sxs-lookup"><span data-stu-id="3423e-106">UE-V 2.x introduces a new SyncMethod called the *SyncProvider*.</span></span> <span data-ttu-id="3423e-107">有关启动应用程序和 Windows 设置同步的触发器事件的详细信息，请参阅[为 ue-v 2. x 同步触发器事件](sync-trigger-events-for-ue-v-2x-both-uevv2.md)。</span><span class="sxs-lookup"><span data-stu-id="3423e-107">For more information about trigger events that start the synchronization of application and Windows settings, see [Sync Trigger Events for UE-V 2.x](sync-trigger-events-for-ue-v-2x-both-uevv2.md).</span></span>

## <span data-ttu-id="3423e-108">Powerschool 配置</span><span class="sxs-lookup"><span data-stu-id="3423e-108">SyncMethod Configuration</span></span>


<span data-ttu-id="3423e-109">下表说明了对 Powerschool 的更改：从 UE-V v 1.0 到 v 2.0 到 v 2.1 以及每个配置的设置：</span><span class="sxs-lookup"><span data-stu-id="3423e-109">This table explains the changes to SyncMethod from UE-V v1.0 to v2.0 to v2.1, as well as the settings for each configuration:</span></span>

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="3423e-110">Powerschool 配置</span><span class="sxs-lookup"><span data-stu-id="3423e-110">SyncMethod Configuration</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="3423e-111">V 1。0</span><span class="sxs-lookup"><span data-stu-id="3423e-111">V1.0</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="3423e-112">V 2。0</span><span class="sxs-lookup"><span data-stu-id="3423e-112">V2.0</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="3423e-113">V 2.1 和 V 2.1 SP1</span><span class="sxs-lookup"><span data-stu-id="3423e-113">V2.1 and V2.1 SP1</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="3423e-114">描述</span><span class="sxs-lookup"><span data-stu-id="3423e-114">Description</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3423e-115">SyncProvider</span><span class="sxs-lookup"><span data-stu-id="3423e-115">SyncProvider</span></span></p></td>
<td align="left"><p><span data-ttu-id="3423e-116">不适用</span><span class="sxs-lookup"><span data-stu-id="3423e-116">n/a</span></span></p></td>
<td align="left"><p><span data-ttu-id="3423e-117">默认值</span><span class="sxs-lookup"><span data-stu-id="3423e-117">Default</span></span></p></td>
<td align="left"><p><span data-ttu-id="3423e-118">默认值</span><span class="sxs-lookup"><span data-stu-id="3423e-118">Default</span></span></p></td>
<td align="left"><p><span data-ttu-id="3423e-119">特定应用程序或全局 Windows 桌面设置的设置更改将保存到本地缓存文件夹中。</span><span class="sxs-lookup"><span data-stu-id="3423e-119">Settings changes for a specific application or for global Windows desktop settings are saved locally to a cache folder.</span></span> <span data-ttu-id="3423e-120">当发生同步触发事件时，这些更改将与设置存储位置同步。</span><span class="sxs-lookup"><span data-stu-id="3423e-120">These changes are then synchronized with the settings storage location when a synchronization trigger event takes place.</span></span> <span data-ttu-id="3423e-121">推送更改会将本地更改保存到设置存储路径。</span><span class="sxs-lookup"><span data-stu-id="3423e-121">Pushing out changes will save the local changes to the settings storage path.</span></span></p>
<p><span data-ttu-id="3423e-122">此默认设置是计算机的黄金标准。</span><span class="sxs-lookup"><span data-stu-id="3423e-122">This default setting is the gold standard for computers.</span></span> <span data-ttu-id="3423e-123">此选项尝试在短时间延迟后同步设置和超时，以确保应用程序或操作系统启动不会在很长一段时间内延迟。</span><span class="sxs-lookup"><span data-stu-id="3423e-123">This option attempts to synchronize the setting and times out after a short delay to ensure that the application or operating system startup isn’t delayed for a long period of time.</span></span></p>
<p><span data-ttu-id="3423e-124">此功能还与 "计划任务-同步控制器" 应用程序相关联。</span><span class="sxs-lookup"><span data-stu-id="3423e-124">This functionality is also tied to the Scheduled task – Sync Controller Application.</span></span> <span data-ttu-id="3423e-125">管理员控制计划任务的频率。</span><span class="sxs-lookup"><span data-stu-id="3423e-125">The administrator controls the frequency of the Scheduled task.</span></span> <span data-ttu-id="3423e-126">默认情况下，计算机在登录后每隔30分钟同步其设置。</span><span class="sxs-lookup"><span data-stu-id="3423e-126">By default, computers synchronize their settings every 30 min after logging on.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3423e-127">OfflineFiles</span><span class="sxs-lookup"><span data-stu-id="3423e-127">OfflineFiles</span></span></p></td>
<td align="left"><p><span data-ttu-id="3423e-128">默认值</span><span class="sxs-lookup"><span data-stu-id="3423e-128">Default</span></span></p></td>
<td align="left"><p><span data-ttu-id="3423e-129">已弃用</span><span class="sxs-lookup"><span data-stu-id="3423e-129">Deprecated</span></span></p></td>
<td align="left"><p><span data-ttu-id="3423e-130">已弃用</span><span class="sxs-lookup"><span data-stu-id="3423e-130">Deprecated</span></span></p></td>
<td align="left"><p><span data-ttu-id="3423e-131">的行为与 V 2.0 中的 SyncProvider 相同。</span><span class="sxs-lookup"><span data-stu-id="3423e-131">Behaves the same as SyncProvider in V2.0.</span></span></p>
<p><span data-ttu-id="3423e-132">如果启用了脱机文件，并且已将文件夹固定，则 UE-V 将取消该文件夹的固定，并将其直接同步到中央 SMB 目录。</span><span class="sxs-lookup"><span data-stu-id="3423e-132">If Offline files are enabled and the folder is pinned then UE-V will unpin this folder and sync directly to the central SMB directory.</span></span></p>
<p><strong><span data-ttu-id="3423e-133">注意： </strong> 在 V 1.0 中，如果你想要以企业的断开连接方式使用 ue-v （也就是使用膝上型电脑旅行），则指南是使用脱机文件确保你的设置漫游。</span><span class="sxs-lookup"><span data-stu-id="3423e-133">NOTE:</strong> In V1.0 if you wanted to use UE-V in a CorpNet disconnected manner (aka traveling with a Laptop), then the guidance is to use Offline Files to ensure that your settings roamed.</span></span><span data-ttu-id="3423e-134">我们收到了足够的客户反馈，可打开 "脱机文件" 是不重要的企业阻止程序。</span><span class="sxs-lookup"><span data-stu-id="3423e-134"> We received sufficient customer feedback that turning on Offline files is a non-trivial enterprise blocker.</span></span> <span data-ttu-id="3423e-135">因此，在 UE-V 2 中，我们创建了一个紧密耦合的同步引擎以在本地缓存数据，并将设置同步到中央服务器。</span><span class="sxs-lookup"><span data-stu-id="3423e-135">So in UE-V 2, we created a tightly coupled synchronization engine to cache your data locally and synchronize the settings to the central server.</span></span> <span data-ttu-id="3423e-136">此功能区域不会替换脱机文件或文件夹重定向。</span><span class="sxs-lookup"><span data-stu-id="3423e-136">This feature area does not replace Offline Files or Folder Redirection.</span></span></p>
<p><span data-ttu-id="3423e-137">UE-V 2 不能很好地处理脱机文件夹，因此指南不会将设置存储路径设置为已固定的脱机或 CSC 文件夹。</span><span class="sxs-lookup"><span data-stu-id="3423e-137">UE-V 2 does not work well with Offline folders so the guidance is not to set the settings storage path to a pinned Offline or CSC folder.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3423e-138">外部</span><span class="sxs-lookup"><span data-stu-id="3423e-138">External</span></span></p></td>
<td align="left"><p><span data-ttu-id="3423e-139">不适用</span><span class="sxs-lookup"><span data-stu-id="3423e-139">n/a</span></span></p></td>
<td align="left"><p><span data-ttu-id="3423e-140">不适用</span><span class="sxs-lookup"><span data-stu-id="3423e-140">n/a</span></span></p></td>
<td align="left"><p><span data-ttu-id="3423e-141">支持</span><span class="sxs-lookup"><span data-stu-id="3423e-141">Supported</span></span></p></td>
<td align="left"><p><span data-ttu-id="3423e-142">UE-V 2.1 中的新增功能，此配置方法指定如果 UE-V 设置写入到用户计算机上的本地文件夹，则可以使用任何外部同步引擎（如 OneDrive for Business、工作文件夹、Sharepoint 或 Dropbox）将这些设置应用于用户访问的不同计算机。</span><span class="sxs-lookup"><span data-stu-id="3423e-142">New in UE-V 2.1, this configuration method specifies that if UE-V settings are written to a local folder on the user computer, then any external sync engine (such as OneDrive for Business, Work Folders, Sharepoint, or Dropbox) can be used to apply these settings to the different computers that users access.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3423e-143">无</span><span class="sxs-lookup"><span data-stu-id="3423e-143">None</span></span></p></td>
<td align="left"><p><span data-ttu-id="3423e-144">是</span><span class="sxs-lookup"><span data-stu-id="3423e-144">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="3423e-145">是</span><span class="sxs-lookup"><span data-stu-id="3423e-145">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="3423e-146">是</span><span class="sxs-lookup"><span data-stu-id="3423e-146">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="3423e-147">此配置设置主要用于虚拟桌面基础结构（VDI）和流式处理应用程序体验。</span><span class="sxs-lookup"><span data-stu-id="3423e-147">This configuration setting is designed for the Virtual Desktop Infrastructure (VDI) and Streamed Application experience primarily.</span></span> <span data-ttu-id="3423e-148">应在数据中心中使用的 Windows Server 框上使用此设置，其中的连接将始终可用。</span><span class="sxs-lookup"><span data-stu-id="3423e-148">This setting should be used on Windows Server boxes used in a datacenter, where the connection will always be available.</span></span></p>
<p><span data-ttu-id="3423e-149">任何设置更改都将直接保存到服务器。</span><span class="sxs-lookup"><span data-stu-id="3423e-149">Any settings changes are saved directly to the server.</span></span> <span data-ttu-id="3423e-150">如果到设置存储路径的网络连接不可用，则设置更改将缓存在设备上，并且将在下次运行同步提供程序时进行同步。</span><span class="sxs-lookup"><span data-stu-id="3423e-150">If the network connection to the settings storage path is not available, then the settings changes are cached on the device and are synchronized the next time that the Sync Provider runs.</span></span> <span data-ttu-id="3423e-151">如果未找到设置存储路径，并且在注销时从池中的 VDI 环境中删除了用户配置文件，则这些设置更改将丢失，用户必须重新应用更改，然后计算机才能再次访问设置存储路径。</span><span class="sxs-lookup"><span data-stu-id="3423e-151">If the settings storage path is not found and the user profile is removed from a pooled VDI environment on logoff, then these settings changes are lost, and the user must reapply the change when the computer can again reach the settings storage path.</span></span></p>
<p><span data-ttu-id="3423e-152">应用和操作系统将无限期地等待要显示的位置。</span><span class="sxs-lookup"><span data-stu-id="3423e-152">Apps and OS will wait indefinitely for the location to be present.</span></span> <span data-ttu-id="3423e-153">如果找不到该位置，这可能会导致应用加载或操作系统登录时间大幅增加。</span><span class="sxs-lookup"><span data-stu-id="3423e-153">This could cause App load or OS logon time to dramatically increase if the location is not found.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="3423e-154">你可以通过以下方式配置同步方法：</span><span class="sxs-lookup"><span data-stu-id="3423e-154">You can configure the sync method in these ways:</span></span>

-   <span data-ttu-id="3423e-155">通过命令行参数或在批处理脚本中[部署 Ue-v Agent](https://technet.microsoft.com/library/dn458891.aspx#agent)时</span><span class="sxs-lookup"><span data-stu-id="3423e-155">When you [Deploy the UE-V Agent](https://technet.microsoft.com/library/dn458891.aspx#agent) through a command-line parameter or in a batch script</span></span>

-   <span data-ttu-id="3423e-156">通过[组策略](https://technet.microsoft.com/library/dn458893.aspx)设置</span><span class="sxs-lookup"><span data-stu-id="3423e-156">Through [Group Policy](https://technet.microsoft.com/library/dn458893.aspx) settings</span></span>

-   <span data-ttu-id="3423e-157">对于 UE-V 的[System Center 配置包](https://technet.microsoft.com/library/dn458917.aspx)</span><span class="sxs-lookup"><span data-stu-id="3423e-157">With the [System Center Configuration Pack](https://technet.microsoft.com/library/dn458917.aspx) for UE-V</span></span>

-   <span data-ttu-id="3423e-158">在安装 UE-V Agent 之后，使用[Windows PowerShell 或 Windows Management Instrumentation （WMI）](https://technet.microsoft.com/library/dn458937.aspx)</span><span class="sxs-lookup"><span data-stu-id="3423e-158">After installation of the UE-V Agent, by using [Windows PowerShell or Windows Management Instrumentation (WMI)](https://technet.microsoft.com/library/dn458937.aspx)</span></span>






## <span data-ttu-id="3423e-159">相关主题</span><span class="sxs-lookup"><span data-stu-id="3423e-159">Related topics</span></span>


[<span data-ttu-id="3423e-160">为 UE-V 2.x 部署所需功能</span><span class="sxs-lookup"><span data-stu-id="3423e-160">Deploy Required Features for UE-V 2.x</span></span>](deploy-required-features-for-ue-v-2x-new-uevv2.md#ssl)

[<span data-ttu-id="3423e-161">为 UE-V 2.x 部署所需功能</span><span class="sxs-lookup"><span data-stu-id="3423e-161">Deploy Required Features for UE-V 2.x</span></span>](deploy-required-features-for-ue-v-2x-new-uevv2.md#config)

[<span data-ttu-id="3423e-162">UE-V 2.x 的技术参考</span><span class="sxs-lookup"><span data-stu-id="3423e-162">Technical Reference for UE-V 2.x</span></span>](technical-reference-for-ue-v-2x-both-uevv2.md)

 

 





