---
title: 更改 UE-V 2 x 计划任务的频率
description: 更改 UE-V 2 x 计划任务的频率
author: dansimp
ms.assetid: ee486570-c6cf-4fd9-ba48-0059ba877c10
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 09/29/2016
ms.openlocfilehash: 1c1e3c091431dc56068dcd1fe0e849b0df1f6aa0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803566"
---
# <span data-ttu-id="95512-103">更改 UE-V 2 x 计划任务的频率</span><span class="sxs-lookup"><span data-stu-id="95512-103">Changing the Frequency of UE-V 2.x Scheduled Tasks</span></span>


<span data-ttu-id="95512-104">Microsoft 用户体验虚拟化（UE-V）2.0、2.1 或 2.1 SP1 代理安装程序 AgentSetup.exe 在 UE-V Agent 安装期间创建以下计划任务：</span><span class="sxs-lookup"><span data-stu-id="95512-104">The Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, or 2.1 SP1 Agent installer, AgentSetup.exe, creates the following scheduled tasks during the UE-V Agent installation:</span></span>

-   **<span data-ttu-id="95512-105">监视应用程序设置</span><span class="sxs-lookup"><span data-stu-id="95512-105">Monitor Application Settings</span></span>**

-   **<span data-ttu-id="95512-106">同步控制器应用程序</span><span class="sxs-lookup"><span data-stu-id="95512-106">Sync Controller Application</span></span>**

-   **<span data-ttu-id="95512-107">在注销时同步设置</span><span class="sxs-lookup"><span data-stu-id="95512-107">Synchronize Settings at Logoff</span></span>**

-   **<span data-ttu-id="95512-108">模板自动更新</span><span class="sxs-lookup"><span data-stu-id="95512-108">Template Auto Update</span></span>**

-   **<span data-ttu-id="95512-109">收集 CEIP 数据</span><span class="sxs-lookup"><span data-stu-id="95512-109">Collect CEIP data</span></span>**

-   **<span data-ttu-id="95512-110">上载 CEIP 数据</span><span class="sxs-lookup"><span data-stu-id="95512-110">Upload CEIP Data</span></span>**

<span data-ttu-id="95512-111">**注意** 除了收集 CEIP 数据，这些任务必须保持启用状态，因为 UE-V 在没有它们的情况下无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="95512-111">**Note** With the exception of Collect CEIP Data, these tasks must remain enabled as UE-V cannot function without them.</span></span>

 

<span data-ttu-id="95512-112">这些计划任务无法通过 UE-V 工具进行配置。</span><span class="sxs-lookup"><span data-stu-id="95512-112">These scheduled tasks are not configurable with the UE-V tools.</span></span> <span data-ttu-id="95512-113">希望更改这些项目的计划任务的管理员可以创建使用 Schtasks.exe 命令行选项的脚本。</span><span class="sxs-lookup"><span data-stu-id="95512-113">Administrators who want to change the scheduled task for these items can create a script that uses the Schtasks.exe command-line options.</span></span>

<span data-ttu-id="95512-114">有关 Schtasks.exe 的详细信息，请参阅[如何使用 Schtasks、exe 在 Windows Server 2003 中安排任务](https://go.microsoft.com/fwlink/?LinkID=264854)。</span><span class="sxs-lookup"><span data-stu-id="95512-114">For more information about Schtasks.exe, see [How to use Schtasks,exe to Schedule Tasks in Windows Server 2003](https://go.microsoft.com/fwlink/?LinkID=264854).</span></span>

<span data-ttu-id="95512-115">有关详细信息</span><span class="sxs-lookup"><span data-stu-id="95512-115">For more information about</span></span>

## <span data-ttu-id="95512-116">UE-V 计划的任务</span><span class="sxs-lookup"><span data-stu-id="95512-116">UE-V Scheduled Tasks</span></span>


<span data-ttu-id="95512-117">通过示例计划任务配置命令，UE-V 2 中包含以下计划任务。</span><span class="sxs-lookup"><span data-stu-id="95512-117">The following scheduled tasks are included in UE-V 2 with sample scheduled task configuration commands.</span></span>

### <span data-ttu-id="95512-118">收集 CEIP 数据</span><span class="sxs-lookup"><span data-stu-id="95512-118">Collect CEIP Data</span></span>

<span data-ttu-id="95512-119">如果在安装时用户或管理员 choses 参与客户体验改善计划（CEIP），UE-V 将收集数据，以帮助改进未来版本中的产品。</span><span class="sxs-lookup"><span data-stu-id="95512-119">If upon installation the user or administrator choses to participate in the Customer Experience Improvement Program (CEIP), UE-V collects data to help improve the product in future releases.</span></span> <span data-ttu-id="95512-120">此计划任务仅在登录时运行。</span><span class="sxs-lookup"><span data-stu-id="95512-120">This scheduled task only runs at logon.</span></span> <span data-ttu-id="95512-121">"**收集 CEIP 数据**" 任务将运行 "UevSqmSession.exe"，它位于 ue-v agent 安装目录中。</span><span class="sxs-lookup"><span data-stu-id="95512-121">The **Collect CEIP Data** task runs the UevSqmSession.exe, which is located in the UE-V Agent installation directory.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="95512-122">任务名称</span><span class="sxs-lookup"><span data-stu-id="95512-122">Task name</span></span></th>
<th align="left"><span data-ttu-id="95512-123">默认事件</span><span class="sxs-lookup"><span data-stu-id="95512-123">Default event</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="95512-124">\Microsoft\UE-V\Collect CEIP 数据</span><span class="sxs-lookup"><span data-stu-id="95512-124">\Microsoft\UE-V\Collect CEIP data</span></span></p></td>
<td align="left"><p><span data-ttu-id="95512-125">Logon</span><span class="sxs-lookup"><span data-stu-id="95512-125">Logon</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="95512-126">监视应用程序设置</span><span class="sxs-lookup"><span data-stu-id="95512-126">Monitor Application Settings</span></span>

<span data-ttu-id="95512-127">"**监视器应用程序设置**" 任务用于同步 Windows 应用的设置。</span><span class="sxs-lookup"><span data-stu-id="95512-127">The **Monitor Application Settings** task is used to synchronize settings for Windows apps.</span></span> <span data-ttu-id="95512-128">它在登录时运行，但延迟30秒以不影响登录 detrimentally。</span><span class="sxs-lookup"><span data-stu-id="95512-128">It is run at logon but is delayed by 30 seconds to not affect the logon detrimentally.</span></span> <span data-ttu-id="95512-129">"监视应用程序状态" 任务运行 "UevAppMonitor.exe" 文件，该文件位于 UE-V Agent 安装目录中。</span><span class="sxs-lookup"><span data-stu-id="95512-129">The Monitor Application Status task runs the UevAppMonitor.exe file, which is located in the UE-V Agent installation directory.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="95512-130">任务名称</span><span class="sxs-lookup"><span data-stu-id="95512-130">Task name</span></span></th>
<th align="left"><span data-ttu-id="95512-131">默认事件</span><span class="sxs-lookup"><span data-stu-id="95512-131">Default event</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="95512-132">\Microsoft\UE-V\Monitor 应用程序状态</span><span class="sxs-lookup"><span data-stu-id="95512-132">\Microsoft\UE-V\Monitor Application Status</span></span></p></td>
<td align="left"><p><span data-ttu-id="95512-133">Logon</span><span class="sxs-lookup"><span data-stu-id="95512-133">Logon</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="95512-134">同步控制器应用程序</span><span class="sxs-lookup"><span data-stu-id="95512-134">Sync Controller Application</span></span>

<span data-ttu-id="95512-135">**同步控制器应用程序**任务用于启动同步控制器，以便将计算机中的设置同步到设置存储位置。</span><span class="sxs-lookup"><span data-stu-id="95512-135">The **Sync Controller Application** task is used to start the Sync Controller to synchronize settings from the computer to the settings storage location.</span></span> <span data-ttu-id="95512-136">默认情况下，任务每30分钟运行一次。</span><span class="sxs-lookup"><span data-stu-id="95512-136">By default, the task runs every 30 minutes.</span></span> <span data-ttu-id="95512-137">此时，本地设置将同步到设置存储位置，并且设置存储位置上的更新设置将同步到计算机。</span><span class="sxs-lookup"><span data-stu-id="95512-137">At that time, local settings are synchronized to the settings storage location, and updated settings on the settings storage location are synchronized to the computer.</span></span> <span data-ttu-id="95512-138">同步控制器应用程序运行位于 UE-V Agent 安装目录中的 Microsoft.Uev.SyncController.exe。</span><span class="sxs-lookup"><span data-stu-id="95512-138">The Sync Controller application runs the Microsoft.Uev.SyncController.exe, which is located in the UE-V Agent installation directory.</span></span>
<span data-ttu-id="95512-139">**注意：** 根据 "**监视器应用程序设置**" 任务，此任务在登录时运行，但延迟30秒以不影响登录 detrimentally。</span><span class="sxs-lookup"><span data-stu-id="95512-139">**Note:** As per the **Monitor Application Settings** task, this task is run at logon but is delayed by 30 seconds to not affect the logon detrimentally.</span></span>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="95512-140">任务名称</span><span class="sxs-lookup"><span data-stu-id="95512-140">Task name</span></span></th>
<th align="left"><span data-ttu-id="95512-141">默认事件</span><span class="sxs-lookup"><span data-stu-id="95512-141">Default event</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="95512-142">\Microsoft\UE-V\Sync 控制器应用程序</span><span class="sxs-lookup"><span data-stu-id="95512-142">\Microsoft\UE-V\Sync Controller Application</span></span></p></td>
<td align="left"><p><span data-ttu-id="95512-143">登录，此后每天30分钟</span><span class="sxs-lookup"><span data-stu-id="95512-143">Logon, and every 30 minutes thereafter</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="95512-144">例如，以下命令将代理配置为每15分钟同步一次设置，而不是默认的30分钟。</span><span class="sxs-lookup"><span data-stu-id="95512-144">For example, the following command configures the agent to synchronize settings every 15 minutes instead of the default 30 minutes.</span></span>

``` syntax
Schtasks /change /tn “Microsoft\UE-V\Sync Controller Application” /ri 15
```

### <span data-ttu-id="95512-145">在注销时同步设置</span><span class="sxs-lookup"><span data-stu-id="95512-145">Synchronize Settings at Logoff</span></span>

<span data-ttu-id="95512-146">注销任务的 "**同步设置**" 用于在登录时启动应用程序，以便在对 ue-v 注销时控制应用程序的同步。</span><span class="sxs-lookup"><span data-stu-id="95512-146">The **Synchronize Settings at Logoff** task is used to start an application at logon that controls the synchronization of applications at logoff for UE-V.</span></span> <span data-ttu-id="95512-147">"注销任务" 中的 "同步设置" 将运行位于 UE-V Agent 安装目录中的 Microsoft.Uev.SyncController.exe 文件。</span><span class="sxs-lookup"><span data-stu-id="95512-147">The Synchronize Settings at Logoff task runs the Microsoft.Uev.SyncController.exe file, which is located in the UE-V Agent installation directory.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="95512-148">任务名称</span><span class="sxs-lookup"><span data-stu-id="95512-148">Task name</span></span></th>
<th align="left"><span data-ttu-id="95512-149">默认事件</span><span class="sxs-lookup"><span data-stu-id="95512-149">Default event</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="95512-150">注销时的 \Microsoft\UE-V\Synchronize 设置</span><span class="sxs-lookup"><span data-stu-id="95512-150">\Microsoft\UE-V\Synchronize Settings at Logoff</span></span></p></td>
<td align="left"><p><span data-ttu-id="95512-151">Logon</span><span class="sxs-lookup"><span data-stu-id="95512-151">Logon</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="95512-152">模板自动更新</span><span class="sxs-lookup"><span data-stu-id="95512-152">Template Auto Update</span></span>

<span data-ttu-id="95512-153">**模板自动更新**任务检查设置模板目录中是否有新的、已更新或已删除的模板。</span><span class="sxs-lookup"><span data-stu-id="95512-153">The **Template Auto Update** task checks the settings template catalog for new, updated, or removed templates.</span></span> <span data-ttu-id="95512-154">仅当配置了 SettingsTemplateCatalog 时，此任务才会运行。</span><span class="sxs-lookup"><span data-stu-id="95512-154">This task only runs if the SettingsTemplateCatalog is configured.</span></span> <span data-ttu-id="95512-155">**模板自动更新**任务运行 "ApplySettingsCatalog.exe" 文件，该文件位于 ue-v agent 安装目录中。</span><span class="sxs-lookup"><span data-stu-id="95512-155">The **Template Auto Update** task runs the ApplySettingsCatalog.exe file, which is located in the UE-V Agent installation directory.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="95512-156">任务名称</span><span class="sxs-lookup"><span data-stu-id="95512-156">Task name</span></span></th>
<th align="left"><span data-ttu-id="95512-157">默认事件</span><span class="sxs-lookup"><span data-stu-id="95512-157">Default event</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="95512-158">\Microsoft\UE-V\Template 自动更新</span><span class="sxs-lookup"><span data-stu-id="95512-158">\Microsoft\UE-V\Template Auto Update</span></span></p></td>
<td align="left"><p><span data-ttu-id="95512-159">系统启动和每天3:30 上午，在1小时窗口内随机时间</span><span class="sxs-lookup"><span data-stu-id="95512-159">System startup and at 3:30 AM every day, at a random time within a 1-hour window</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="95512-160">**示例：** 以下命令将每小时的 UE-V Agent 配置为检查设置模板目录存储。</span><span class="sxs-lookup"><span data-stu-id="95512-160">**Example:** The following command configures the UE-V Agent to check the settings template catalog store every hour.</span></span>

``` syntax
schtasks /change /tn "Microsoft\UE-V\Template Auto Update" /ri 60
```

### <span data-ttu-id="95512-161">上载 CEIP 数据</span><span class="sxs-lookup"><span data-stu-id="95512-161">Upload CEIP Data</span></span>

<span data-ttu-id="95512-162">如果用户或管理员选择参与客户体验改善计划（CEIP），则会在安装期间运行 "**上载 CEIP 数据**" 任务。</span><span class="sxs-lookup"><span data-stu-id="95512-162">The **Upload CEIP Data** task runs during the installation if the user or the administrator chose to participate in the Customer Experience Improvement Program (CEIP).</span></span> <span data-ttu-id="95512-163">此任务将数据上载到 CEIP 服务器，在此服务器中，数据用于帮助改进此产品以供 UE-V 的未来版本使用。</span><span class="sxs-lookup"><span data-stu-id="95512-163">This task uploads the data to the CEIP servers where the data is used to help improve the product for future releases of UE-V.</span></span> <span data-ttu-id="95512-164">此计划任务将在登录时和每4小时运行一次。</span><span class="sxs-lookup"><span data-stu-id="95512-164">This scheduled task runs at logon and every 4 hours afterwards.</span></span> <span data-ttu-id="95512-165">"**上载 CEIP 数据**" 任务将运行位于 ue-v Agent 安装目录中的 UevSqmUploader.exe 文件。</span><span class="sxs-lookup"><span data-stu-id="95512-165">The **Upload CEIP data** task runs the UevSqmUploader.exe file, which is located in the UE-V Agent installation directory.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="95512-166">任务名称</span><span class="sxs-lookup"><span data-stu-id="95512-166">Task name</span></span></th>
<th align="left"><span data-ttu-id="95512-167">默认事件</span><span class="sxs-lookup"><span data-stu-id="95512-167">Default event</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="95512-168">\Microsoft\UE-V\Upload CEIP 数据</span><span class="sxs-lookup"><span data-stu-id="95512-168">\Microsoft\UE-V\Upload CEIP data</span></span></p></td>
<td align="left"><p><span data-ttu-id="95512-169">在登录时和每隔4小时</span><span class="sxs-lookup"><span data-stu-id="95512-169">At logon and every 4 hours</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="95512-170">UE-V 2 计划任务的详细信息</span><span class="sxs-lookup"><span data-stu-id="95512-170">UE-V 2 Scheduled Task Details</span></span>


<span data-ttu-id="95512-171">下图提供了有关 UE-V 2 的计划任务的其他信息：</span><span class="sxs-lookup"><span data-stu-id="95512-171">The following chart provides additional information about scheduled tasks for UE-V 2:</span></span>

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="95512-172">任务名称 </strong> （文件名）</span><span class="sxs-lookup"><span data-stu-id="95512-172">Task Name</strong> (file name)</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="95512-173">默认频率</span><span class="sxs-lookup"><span data-stu-id="95512-173">Default Frequency</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="95512-174">Power 开关</span><span class="sxs-lookup"><span data-stu-id="95512-174">Power Toggle</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="95512-175">仅空闲</span><span class="sxs-lookup"><span data-stu-id="95512-175">Idle Only</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="95512-176">网络连接</span><span class="sxs-lookup"><span data-stu-id="95512-176">Network Connection</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="95512-177">描述</span><span class="sxs-lookup"><span data-stu-id="95512-177">Description</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="95512-178">监视应用程序设置 </strong> （UevAppMonitor.exe）</span><span class="sxs-lookup"><span data-stu-id="95512-178">Monitor Application Settings</strong> (UevAppMonitor.exe)</span></span></p></td>
<td align="left"><p><span data-ttu-id="95512-179">在登录后的30秒内启动并继续，直到注销。</span><span class="sxs-lookup"><span data-stu-id="95512-179">Starts 30 seconds after logon and continues until logoff.</span></span></p></td>
<td align="left"><p><span data-ttu-id="95512-180">不可用</span><span class="sxs-lookup"><span data-stu-id="95512-180">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="95512-181">是</span><span class="sxs-lookup"><span data-stu-id="95512-181">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="95512-182">不适用</span><span class="sxs-lookup"><span data-stu-id="95512-182">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="95512-183">同步 Windows （AppX）应用的设置。</span><span class="sxs-lookup"><span data-stu-id="95512-183">Synchronizes settings for Windows (AppX) apps.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="95512-184">同步控制器应用程序 </strong> （Microsoft.Uev.SyncController.exe）</span><span class="sxs-lookup"><span data-stu-id="95512-184">Sync Controller Application</strong> (Microsoft.Uev.SyncController.exe)</span></span></p></td>
<td align="left"><p><span data-ttu-id="95512-185">在登录时和每隔30分钟之后。</span><span class="sxs-lookup"><span data-stu-id="95512-185">At logon and every 30 min thereafter.</span></span></p></td>
<td align="left"><p><span data-ttu-id="95512-186">是</span><span class="sxs-lookup"><span data-stu-id="95512-186">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="95512-187">是</span><span class="sxs-lookup"><span data-stu-id="95512-187">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="95512-188">仅当网络已连接时</span><span class="sxs-lookup"><span data-stu-id="95512-188">Only if Network is connected</span></span></p></td>
<td align="left"><p><span data-ttu-id="95512-189">启动同步控制器，该控制器将本地设置与设置存储位置同步。</span><span class="sxs-lookup"><span data-stu-id="95512-189">Starts the Sync Controller which synchronizes local settings with the settings storage location.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="95512-190">在注销时同步设置 </strong> （Microsoft.Uev.SyncController.exe）</span><span class="sxs-lookup"><span data-stu-id="95512-190">Synchronize Settings at Logoff</strong> (Microsoft.Uev.SyncController.exe)</span></span></p></td>
<td align="left"><p><span data-ttu-id="95512-191">在登录时运行，然后等待注销同步设置。</span><span class="sxs-lookup"><span data-stu-id="95512-191">Runs at logon and then waits for Logoff to Synchronize settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="95512-192">不可用</span><span class="sxs-lookup"><span data-stu-id="95512-192">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="95512-193">是</span><span class="sxs-lookup"><span data-stu-id="95512-193">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="95512-194">不适用</span><span class="sxs-lookup"><span data-stu-id="95512-194">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="95512-195">在登录时启动应用程序以控制应用程序在注销时的同步。</span><span class="sxs-lookup"><span data-stu-id="95512-195">Start an application at logon that controls the synchronization of applications at logoff.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="95512-196">模板自动更新 </strong> （ApplySettingsCatalog.exe）</span><span class="sxs-lookup"><span data-stu-id="95512-196">Template Auto Update</strong> (ApplySettingsCatalog.exe)</span></span></p></td>
<td align="left"><p><span data-ttu-id="95512-197">在初始登录时运行，此后每天 3:30 AM 运行。</span><span class="sxs-lookup"><span data-stu-id="95512-197">Runs at initial logon and at 3:30 AM every day thereafter.</span></span></p></td>
<td align="left"><p><span data-ttu-id="95512-198">是</span><span class="sxs-lookup"><span data-stu-id="95512-198">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="95512-199">否</span><span class="sxs-lookup"><span data-stu-id="95512-199">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="95512-200">不适用</span><span class="sxs-lookup"><span data-stu-id="95512-200">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="95512-201">检查设置模板目录中是否有新的、已更新或已删除的模板。</span><span class="sxs-lookup"><span data-stu-id="95512-201">Checks the settings template catalog for new, updated, or removed templates.</span></span> <span data-ttu-id="95512-202">仅当配置了 SettingsTemplateCatalog 时，此任务才会运行。</span><span class="sxs-lookup"><span data-stu-id="95512-202">This task only runs if SettingsTemplateCatalog is configured.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="95512-203">收集 CEIP 数据 </strong> （UevSqmSession.exe）</span><span class="sxs-lookup"><span data-stu-id="95512-203">Collect CEIP data</strong> (UevSqmSession.exe)</span></span></p></td>
<td align="left"><p><span data-ttu-id="95512-204">在登录时启动服务</span><span class="sxs-lookup"><span data-stu-id="95512-204">At logon launches service</span></span></p></td>
<td align="left"><p><span data-ttu-id="95512-205">否</span><span class="sxs-lookup"><span data-stu-id="95512-205">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="95512-206">是</span><span class="sxs-lookup"><span data-stu-id="95512-206">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="95512-207">不适用</span><span class="sxs-lookup"><span data-stu-id="95512-207">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="95512-208">如果用户或管理员已加入客户体验改善计划（CEIP），此任务将收集可帮助改进 UE-V 未来版本的数据。</span><span class="sxs-lookup"><span data-stu-id="95512-208">If the user or administrator opts in to the Customer Experience Improvement Program (CEIP), this task collects data that helps improve UE-V future releases.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="95512-209">上载 CEIP 数据 </strong> （UevSqmUploader.exe）</span><span class="sxs-lookup"><span data-stu-id="95512-209">Upload CEIP Data</strong> (UevSqmUploader.exe)</span></span></p></td>
<td align="left"><p><span data-ttu-id="95512-210">在登录时以及此后每天的 4:00 AM 运行。</span><span class="sxs-lookup"><span data-stu-id="95512-210">Runs at logon and at 4:00 AM every day thereafter.</span></span></p></td>
<td align="left"><p><span data-ttu-id="95512-211">否</span><span class="sxs-lookup"><span data-stu-id="95512-211">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="95512-212">是</span><span class="sxs-lookup"><span data-stu-id="95512-212">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="95512-213">仅当网络已连接时</span><span class="sxs-lookup"><span data-stu-id="95512-213">Only if Network is connected</span></span></p></td>
<td align="left"><p><span data-ttu-id="95512-214">如果用户或管理员已加入客户体验改善计划（CEIP），此任务会将数据上载到 CEIP 服务器。</span><span class="sxs-lookup"><span data-stu-id="95512-214">If the user or administrator opts in to the Customer Experience Improvement Program (CEIP), this task uploads the data to the CEIP servers.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="95512-215">图表</span><span class="sxs-lookup"><span data-stu-id="95512-215">Legend</span></span>**

-   <span data-ttu-id="95512-216">**Power 开关**-当未连接到交流电源时，任务计划程序将优化功率消耗。</span><span class="sxs-lookup"><span data-stu-id="95512-216">**Power Toggle** – Task Scheduler will optimize power consumption when not connected to AC power.</span></span> <span data-ttu-id="95512-217">如果计算机切换到电池电源，该任务可能会停止运行。</span><span class="sxs-lookup"><span data-stu-id="95512-217">The task might stop running if the computer switches to battery power.</span></span>

-   <span data-ttu-id="95512-218">**仅空闲**-如果计算机停止空闲，任务将停止运行。</span><span class="sxs-lookup"><span data-stu-id="95512-218">**Idle Only** – The task will stop running if the computer ceases to be idle.</span></span> <span data-ttu-id="95512-219">默认情况下，当计算机再次空闲时，不会重新启动任务。</span><span class="sxs-lookup"><span data-stu-id="95512-219">By default the task will not restart when the computer is idle again.</span></span> <span data-ttu-id="95512-220">此时，任务将在下一个任务触发器上再次开始。</span><span class="sxs-lookup"><span data-stu-id="95512-220">Instead the task will begin again on the next task trigger.</span></span>

-   <span data-ttu-id="95512-221">**网络连接**-标记为 "是" 的任务仅当计算机有可用的网络连接时才运行。</span><span class="sxs-lookup"><span data-stu-id="95512-221">**Network Connection** – Tasks marked “Yes” only run if the computer has a network connection available.</span></span> <span data-ttu-id="95512-222">标记为 "N/A" 的任务无论网络连接如何都运行。</span><span class="sxs-lookup"><span data-stu-id="95512-222">Tasks marked “N/A” run regardless of network connectivity.</span></span>

### <span data-ttu-id="95512-223">如何管理计划任务</span><span class="sxs-lookup"><span data-stu-id="95512-223">How to Manage Scheduled Tasks</span></span>

<span data-ttu-id="95512-224">若要查找计划任务，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="95512-224">To find Scheduled Tasks, perform the following:</span></span>

1.  <span data-ttu-id="95512-225">在用户计算机上打开 "安排任务"。</span><span class="sxs-lookup"><span data-stu-id="95512-225">Open “Schedule Tasks” on the user computer.</span></span>

2.  <span data-ttu-id="95512-226">导航到：任务计划程序- &gt; 任务计划程序库- &gt; Microsoft &gt; ue-v</span><span class="sxs-lookup"><span data-stu-id="95512-226">Navigate to: Task Scheduler -&gt; Task Scheduler Library -&gt; Microsoft -&gt; UE-V</span></span>

3.  <span data-ttu-id="95512-227">在 "详细信息" 窗格中选择要管理和配置的计划任务。</span><span class="sxs-lookup"><span data-stu-id="95512-227">Select the scheduled task you wish to manage and configure in the details pane.</span></span>

### <span data-ttu-id="95512-228">其他信息</span><span class="sxs-lookup"><span data-stu-id="95512-228">Additional information</span></span>

<span data-ttu-id="95512-229">以下附加信息适用于 UE-V 计划的任务：</span><span class="sxs-lookup"><span data-stu-id="95512-229">The following additional information applies to UE-V scheduled tasks:</span></span>

-   <span data-ttu-id="95512-230">默认情况下，任务序列程序位于 UE-V Agent 安装文件夹中 `%programFiles%\Microsoft User Experience Virtualization\Agent\[architecture]\` 。</span><span class="sxs-lookup"><span data-stu-id="95512-230">ll task sequence programs are located in the UE-V Agent installation folder, `%programFiles%\Microsoft User Experience Virtualization\Agent\[architecture]\`, by default.</span></span>

-   <span data-ttu-id="95512-231">当 UE-V Powerschool 设置为 "SyncProvider" （UE-V 2 默认配置）时，同步控制器应用程序计划任务是关键组件。</span><span class="sxs-lookup"><span data-stu-id="95512-231">The Sync Controller Application Scheduled task is the crucial component when the UE-V SyncMethod is set to “SyncProvider” (UE-V 2 default configuration).</span></span> <span data-ttu-id="95512-232">此计划任务使 SettingsSToragePath 与设置程序包文件的本地缓存版本保持同步。</span><span class="sxs-lookup"><span data-stu-id="95512-232">This scheduled task keeps the SettingsSToragePath synchronized with the locally cached versions of the settings package files.</span></span> <span data-ttu-id="95512-233">如果用户抱怨设置不会经常同步，则可以将计划任务设置减少为1分钟。</span><span class="sxs-lookup"><span data-stu-id="95512-233">If users complain that settings do not synchronize often enough, then you can reduce the scheduled task setting to as little as 1 minute.</span></span><span data-ttu-id="95512-234">如果需要，还可以将30分钟的默认值增加到更高的金额。</span><span class="sxs-lookup"><span data-stu-id="95512-234"> You can also increase the 30 min default to a higher amount if necessary.</span></span> <span data-ttu-id="95512-235">如果用户抱怨在登录时设置同步速度不够快，则可以删除计划任务的延迟设置。</span><span class="sxs-lookup"><span data-stu-id="95512-235">If users complain that settings do not synchronize fast enough on logon, then you can remove the delay setting for the scheduled task.</span></span> <span data-ttu-id="95512-236">（可以在 "**编辑触发器**" 对话框中找到 "延迟" 设置）</span><span class="sxs-lookup"><span data-stu-id="95512-236">(You can find the delay setting in the **Edit Trigger** dialogue box)</span></span>

-   <span data-ttu-id="95512-237">如果你使用另一种方法保持客户端的模板同步（即组策略或配置管理器基线），则不需要禁用模板自动更新计划任务。</span><span class="sxs-lookup"><span data-stu-id="95512-237">You do not need to disable the Template Auto Update scheduled task if you use another method to keep the clients’ templates in sync (i.e. Group Policy or Configuration Manager Baselines).</span></span> <span data-ttu-id="95512-238">将 SettingsTemplateCatalog 属性值保留为空将阻止 UE-V 检查自定义模板的设置目录。</span><span class="sxs-lookup"><span data-stu-id="95512-238">Leaving the SettingsTemplateCatalog property value blank prevents UE-V from checking the settings catalog for custom templates.</span></span> <span data-ttu-id="95512-239">此计划任务 ApplySettingsCatalog.exe 运行，实质上将立即返回。</span><span class="sxs-lookup"><span data-stu-id="95512-239">This scheduled task runs ApplySettingsCatalog.exe and will essentially return immediately.</span></span>

-   <span data-ttu-id="95512-240">"监视器应用程序设置计划任务" 将基于每个应用中内置的 Windows 应用程序设置触发器实时更新 Windows 应用（AppX）设置。</span><span class="sxs-lookup"><span data-stu-id="95512-240">The Monitor Application Settings scheduled task will update Windows app (AppX) settings in real time, based on Windows app program setting triggers built into each app.</span></span>






## <span data-ttu-id="95512-241">相关主题</span><span class="sxs-lookup"><span data-stu-id="95512-241">Related topics</span></span>


[<span data-ttu-id="95512-242">管理 UE-V 2. x</span><span class="sxs-lookup"><span data-stu-id="95512-242">Administering UE-V 2.x</span></span>](administering-ue-v-2x-new-uevv2.md)

[<span data-ttu-id="95512-243">部署自定义应用程序的 UE-V 2。</span><span class="sxs-lookup"><span data-stu-id="95512-243">Deploy UE-V 2.x for Custom Applications</span></span>](deploy-ue-v-2x-for-custom-applications-new-uevv2.md#deploycatalogue)

 

 





