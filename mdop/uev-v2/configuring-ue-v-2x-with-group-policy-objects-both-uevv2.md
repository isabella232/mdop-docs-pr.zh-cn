---
title: 通过组策略对象配置 UE-V 2. x
description: 通过组策略对象配置 UE-V 2. x
author: dansimp
ms.assetid: 2bb55834-26ee-4f19-9860-dfdf3c797143
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: bdff63b948752b9bec83e77e275f1cb20a384463
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803565"
---
# <span data-ttu-id="42f42-103">通过组策略对象配置 UE-V 2. x</span><span class="sxs-lookup"><span data-stu-id="42f42-103">Configuring UE-V 2.x with Group Policy Objects</span></span>


<span data-ttu-id="42f42-104">某些 Microsoft 用户体验虚拟化（UE-V）2.0、2.1 和 2.1 SP1 组策略设置可为计算机定义，并且可以为用户定义其他组策略设置。</span><span class="sxs-lookup"><span data-stu-id="42f42-104">Some Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, and 2.1 SP1 Group Policy settings can be defined for computers, and other Group Policy settings can be defined for users.</span></span> <span data-ttu-id="42f42-105">有关如何安装 UE-V 组策略 ADMX 文件的信息，请参阅[安装 ue-v 2 组策略 Admx 模板](https://technet.microsoft.com/library/dn458891.aspx#admx)。</span><span class="sxs-lookup"><span data-stu-id="42f42-105">For information about how to install UE-V Group Policy ADMX files, see [Installing the UE-V 2 Group Policy ADMX Templates](https://technet.microsoft.com/library/dn458891.aspx#admx).</span></span>

<span data-ttu-id="42f42-106">可以为 UE-V 配置以下策略设置。</span><span class="sxs-lookup"><span data-stu-id="42f42-106">The following policy settings can be configured for UE-V.</span></span>

**<span data-ttu-id="42f42-107">组策略设置</span><span class="sxs-lookup"><span data-stu-id="42f42-107">Group Policy settings</span></span>**

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="42f42-108">组策略设置名称</span><span class="sxs-lookup"><span data-stu-id="42f42-108">Group Policy setting name</span></span></th>
<th align="left"><span data-ttu-id="42f42-109">目标</span><span class="sxs-lookup"><span data-stu-id="42f42-109">Target</span></span></th>
<th align="left"><span data-ttu-id="42f42-110">组策略设置说明</span><span class="sxs-lookup"><span data-stu-id="42f42-110">Group Policy setting description</span></span></th>
<th align="left"><span data-ttu-id="42f42-111">配置选项</span><span class="sxs-lookup"><span data-stu-id="42f42-111">Configuration options</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="42f42-112">联系 IT 链接文本</span><span class="sxs-lookup"><span data-stu-id="42f42-112">Contact IT Link Text</span></span></p></td>
<td align="left"><p><span data-ttu-id="42f42-113">仅限计算机</span><span class="sxs-lookup"><span data-stu-id="42f42-113">Computers Only</span></span></p></td>
<td align="left"><p><span data-ttu-id="42f42-114">此组策略设置在 "公司设置中心" 中指定 "联系 IT URL" 超链接的文本。</span><span class="sxs-lookup"><span data-stu-id="42f42-114">This Group Policy setting specifies the text of the Contact IT URL hyperlink in the Company Settings Center.</span></span></p></td>
<td align="left"><p><span data-ttu-id="42f42-115">如果启用此组策略设置，公司设置中心将在指向联系人 IT URL 的链接中显示指定文本。</span><span class="sxs-lookup"><span data-stu-id="42f42-115">If you enable this Group Policy setting, the Company Settings Center displays the specified text in the link to the Contact IT URL.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="42f42-116">联系 IT URL</span><span class="sxs-lookup"><span data-stu-id="42f42-116">Contact IT URL</span></span></p></td>
<td align="left"><p><span data-ttu-id="42f42-117">仅限计算机</span><span class="sxs-lookup"><span data-stu-id="42f42-117">Computers Only</span></span></p></td>
<td align="left"><p><span data-ttu-id="42f42-118">此组策略设置在 "公司设置中心" 中指定 "联系人 IT" 链接的 URL。</span><span class="sxs-lookup"><span data-stu-id="42f42-118">This Group Policy setting specifies the URL for the Contact IT link in the Company Settings Center.</span></span></p></td>
<td align="left"><p><span data-ttu-id="42f42-119">如果启用此设置，公司设置中心将联系 IT 文本链接到指定的 URL。</span><span class="sxs-lookup"><span data-stu-id="42f42-119">If you enable this setting, the Company Settings Center Contact IT text links to the specified URL.</span></span> <span data-ttu-id="42f42-120">该链接可以是任何标准协议，如 HTTP 或 mailto。</span><span class="sxs-lookup"><span data-stu-id="42f42-120">The link can be of any standard protocol, such as HTTP or mailto.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="42f42-121">不使用同步提供程序</span><span class="sxs-lookup"><span data-stu-id="42f42-121">Do not use the sync provider</span></span></p></td>
<td align="left"><p><span data-ttu-id="42f42-122">计算机和用户</span><span class="sxs-lookup"><span data-stu-id="42f42-122">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="42f42-123">通过使用此组策略设置，你可以配置 UE-V 是否使用同步提供程序功能。</span><span class="sxs-lookup"><span data-stu-id="42f42-123">By using this Group Policy setting, you can configure whether UE-V uses the sync provider feature.</span></span> <span data-ttu-id="42f42-124">此策略设置还允许你启用在延迟导入用户设置时显示通知。</span><span class="sxs-lookup"><span data-stu-id="42f42-124">This policy setting also lets you enable notification to appear when the import of user settings is delayed.</span></span></p></td>
<td align="left"><p><span data-ttu-id="42f42-125">启用此设置以将 UE-V Agent 配置为不使用同步提供程序。</span><span class="sxs-lookup"><span data-stu-id="42f42-125">Enable this setting to configure the UE-V Agent not to use the sync provider.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="42f42-126">首次使用通知</span><span class="sxs-lookup"><span data-stu-id="42f42-126">First Use Notification</span></span></p></td>
<td align="left"><p><span data-ttu-id="42f42-127">仅限计算机</span><span class="sxs-lookup"><span data-stu-id="42f42-127">Computers Only</span></span></p></td>
<td align="left"><p><span data-ttu-id="42f42-128">此组策略设置启用在 UE-V 的通知区域中出现的通知</span><span class="sxs-lookup"><span data-stu-id="42f42-128">This Group Policy setting enables a notification in the notification area that appears when the UE-V</span></span></p>
<p><span data-ttu-id="42f42-129">代理首次运行。</span><span class="sxs-lookup"><span data-stu-id="42f42-129">agent runs for the first time.</span></span></p></td>
<td align="left"><p><span data-ttu-id="42f42-130">默认值为 "已启用"。</span><span class="sxs-lookup"><span data-stu-id="42f42-130">The default is enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="42f42-131">漫游 Windows 设置</span><span class="sxs-lookup"><span data-stu-id="42f42-131">Roam Windows settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="42f42-132">计算机和用户</span><span class="sxs-lookup"><span data-stu-id="42f42-132">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="42f42-133">此组策略设置配置 Windows 设置的同步。</span><span class="sxs-lookup"><span data-stu-id="42f42-133">This Group Policy setting configures the synchronization of Windows settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="42f42-134">选择要在计算机之间同步的 Windows 设置。</span><span class="sxs-lookup"><span data-stu-id="42f42-134">Select which Windows settings synchronize between computers.</span></span></p>
<p><span data-ttu-id="42f42-135">默认情况下，Windows 主题、桌面设置和轻松访问设置在同一操作系统版本的计算机之间同步设置。</span><span class="sxs-lookup"><span data-stu-id="42f42-135">By default, Windows themes, desktop settings, and Ease of Access settings synchronize settings between computers of the same operating system version.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="42f42-136">设置程序包大小警告阈值</span><span class="sxs-lookup"><span data-stu-id="42f42-136">Settings package size warning threshold</span></span></p></td>
<td align="left"><p><span data-ttu-id="42f42-137">计算机和用户</span><span class="sxs-lookup"><span data-stu-id="42f42-137">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="42f42-138">此组策略设置允许你配置 UE-V Agent，以在设置包文件大小达到定义的阈值时进行报告。</span><span class="sxs-lookup"><span data-stu-id="42f42-138">This Group Policy setting lets you configure the UE-V Agent to report when a settings package file size reaches a defined threshold.</span></span></p></td>
<td align="left"><p><span data-ttu-id="42f42-139">指定设置包大小的首选阈值（KB）。</span><span class="sxs-lookup"><span data-stu-id="42f42-139">Specify the preferred threshold for settings package sizes in kilobytes (KB).</span></span></p>
<p><span data-ttu-id="42f42-140">默认情况下，UE-V Agent 没有程序包文件大小阈值。</span><span class="sxs-lookup"><span data-stu-id="42f42-140">By default, the UE-V Agent does not have a package file size threshold.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="42f42-141">设置存储路径</span><span class="sxs-lookup"><span data-stu-id="42f42-141">Settings storage path</span></span></p></td>
<td align="left"><p><span data-ttu-id="42f42-142">计算机和用户</span><span class="sxs-lookup"><span data-stu-id="42f42-142">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="42f42-143">此组策略设置配置要存储用户设置的位置。</span><span class="sxs-lookup"><span data-stu-id="42f42-143">This Group Policy setting configures where the user settings are to be stored.</span></span></p></td>
<td align="left"><p><span data-ttu-id="42f42-144">输入通用命名约定（UNC）路径和变量（如 \Server\SettingsShare%username%.）</span><span class="sxs-lookup"><span data-stu-id="42f42-144">Enter a Universal Naming Convention (UNC) path and variables such as \Server\SettingsShare%username%.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="42f42-145">设置模板目录路径</span><span class="sxs-lookup"><span data-stu-id="42f42-145">Settings template catalog path</span></span></p></td>
<td align="left"><p><span data-ttu-id="42f42-146">仅限计算机</span><span class="sxs-lookup"><span data-stu-id="42f42-146">Computers Only</span></span></p></td>
<td align="left"><p><span data-ttu-id="42f42-147">此组策略设置配置自定义设置位置模板的存储位置。</span><span class="sxs-lookup"><span data-stu-id="42f42-147">This Group Policy setting configures where custom settings location templates are stored.</span></span> <span data-ttu-id="42f42-148">此策略设置还配置目录是否用于替换随 UE-V Agent 一起安装的默认 Microsoft 模板。</span><span class="sxs-lookup"><span data-stu-id="42f42-148">This policy setting also configures whether the catalog is to be used to replace the default Microsoft templates that are installed with the UE-V Agent.</span></span></p></td>
<td align="left"><p><span data-ttu-id="42f42-149">在计算机上输入通用命名约定（UNC）路径，如 \Server\TemplateShare 或文件夹位置。</span><span class="sxs-lookup"><span data-stu-id="42f42-149">Enter a Universal Naming Convention (UNC) path such as \Server\TemplateShare or a folder location on the computer.</span></span></p>
<p><span data-ttu-id="42f42-150">选中复选框以替换默认的 Microsoft 模板。</span><span class="sxs-lookup"><span data-stu-id="42f42-150">Select the check box to replace the default Microsoft templates.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="42f42-151">通过按流量计费的连接同步设置</span><span class="sxs-lookup"><span data-stu-id="42f42-151">Sync settings over metered connections</span></span></p></td>
<td align="left"><p><span data-ttu-id="42f42-152">计算机和用户</span><span class="sxs-lookup"><span data-stu-id="42f42-152">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="42f42-153">此组策略设置定义 UE-V 是否通过按流量计费的连接同步设置。</span><span class="sxs-lookup"><span data-stu-id="42f42-153">This Group Policy setting defines whether UE-V synchronizes settings over metered connections.</span></span></p></td>
<td align="left"><p><span data-ttu-id="42f42-154">默认情况下，UE-V Agent 不会通过按流量计费的连接同步设置。</span><span class="sxs-lookup"><span data-stu-id="42f42-154">By default, the UE-V Agent does not synchronize settings over a metered connection.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="42f42-155">即使在漫游时也通过按流量计费的连接同步设置</span><span class="sxs-lookup"><span data-stu-id="42f42-155">Sync settings over metered connections even when roaming</span></span></p></td>
<td align="left"><p><span data-ttu-id="42f42-156">计算机和用户</span><span class="sxs-lookup"><span data-stu-id="42f42-156">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="42f42-157">此组策略设置定义了 UE-V 是否通过主提供商网络之外的按流量计费的连接（例如，当数据连接处于漫游模式时）同步设置。</span><span class="sxs-lookup"><span data-stu-id="42f42-157">This Group Policy setting defines whether UE-V synchronizes settings over metered connections outside of the home provider network, for example, when the data connection is in roaming mode.</span></span></p></td>
<td align="left"><p><span data-ttu-id="42f42-158">默认情况下，UE-V 在漫游模式下不会通过按流量计费的连接同步设置。</span><span class="sxs-lookup"><span data-stu-id="42f42-158">By default, UE-V does not synchronize settings over a metered connection when it is in roaming mode.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="42f42-159">同步超时</span><span class="sxs-lookup"><span data-stu-id="42f42-159">Synchronization timeout</span></span></p></td>
<td align="left"><p><span data-ttu-id="42f42-160">计算机和用户</span><span class="sxs-lookup"><span data-stu-id="42f42-160">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="42f42-161">此组策略设置配置在从远程设置位置检索用户设置时，计算机在超时之前等待的毫秒数。</span><span class="sxs-lookup"><span data-stu-id="42f42-161">This Group Policy setting configures the number of milliseconds that the computer waits before a time-out when it retrieves user settings from the remote settings location.</span></span> <span data-ttu-id="42f42-162">如果 "远程存储" 位置不可用，并且用户不使用同步提供程序，则应用程序启动将延迟数毫秒。</span><span class="sxs-lookup"><span data-stu-id="42f42-162">If the remote storage location is unavailable, and the user does not use the sync provider, the application start is delayed by this many milliseconds.</span></span></p></td>
<td align="left"><p><span data-ttu-id="42f42-163">指定首选同步超时时间（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="42f42-163">Specify the preferred synchronization time-out in milliseconds.</span></span> <span data-ttu-id="42f42-164">默认值为2000毫秒。</span><span class="sxs-lookup"><span data-stu-id="42f42-164">The default value is 2000 milliseconds.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="42f42-165">托盘图标</span><span class="sxs-lookup"><span data-stu-id="42f42-165">Tray Icon</span></span></p></td>
<td align="left"><p><span data-ttu-id="42f42-166">仅限计算机</span><span class="sxs-lookup"><span data-stu-id="42f42-166">Computers Only</span></span></p></td>
<td align="left"><p><span data-ttu-id="42f42-167">此组策略设置启用用户体验虚拟化（UE-V）托盘图标。</span><span class="sxs-lookup"><span data-stu-id="42f42-167">This Group Policy setting enables the User Experience Virtualization (UE-V) tray icon.</span></span></p></td>
<td align="left"><p><span data-ttu-id="42f42-168">默认值为 "已启用"。</span><span class="sxs-lookup"><span data-stu-id="42f42-168">The default is enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="42f42-169">使用用户体验虚拟化（UE-V）</span><span class="sxs-lookup"><span data-stu-id="42f42-169">Use User Experience Virtualization (UE-V)</span></span></p></td>
<td align="left"><p><span data-ttu-id="42f42-170">计算机和用户</span><span class="sxs-lookup"><span data-stu-id="42f42-170">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="42f42-171">此组策略设置允许你启用或禁用用户体验虚拟化（UE-V）。</span><span class="sxs-lookup"><span data-stu-id="42f42-171">This Group Policy setting lets you enable or disable User Experience Virtualization (UE-V).</span></span></p></td>
<td align="left"><p><span data-ttu-id="42f42-172">启用或禁用此组策略设置。</span><span class="sxs-lookup"><span data-stu-id="42f42-172">Enable or disable this Group Policy setting.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="42f42-173">**注意** 此外，许多桌面应用程序和 Windows 应用均可使用组策略设置。</span><span class="sxs-lookup"><span data-stu-id="42f42-173">**Note** In addition, Group Policy settings are available for many desktop applications and Windows apps.</span></span> <span data-ttu-id="42f42-174">你可以使用这些设置启用或禁用特定应用程序的设置同步。</span><span class="sxs-lookup"><span data-stu-id="42f42-174">You can use these settings to enable or disable settings synchronization for specific applications.</span></span>

 

**<span data-ttu-id="42f42-175">Windows 应用组策略设置</span><span class="sxs-lookup"><span data-stu-id="42f42-175">Windows App Group Policy settings</span></span>**

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="42f42-176">组策略设置名称</span><span class="sxs-lookup"><span data-stu-id="42f42-176">Group Policy setting name</span></span></th>
<th align="left"><span data-ttu-id="42f42-177">目标</span><span class="sxs-lookup"><span data-stu-id="42f42-177">Target</span></span></th>
<th align="left"><span data-ttu-id="42f42-178">组策略设置说明</span><span class="sxs-lookup"><span data-stu-id="42f42-178">Group Policy setting description</span></span></th>
<th align="left"><span data-ttu-id="42f42-179">配置选项</span><span class="sxs-lookup"><span data-stu-id="42f42-179">Configuration options</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="42f42-180">不同步 Windows 应用</span><span class="sxs-lookup"><span data-stu-id="42f42-180">Do not synchronize Windows Apps</span></span></p></td>
<td align="left"><p><span data-ttu-id="42f42-181">计算机和用户</span><span class="sxs-lookup"><span data-stu-id="42f42-181">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="42f42-182">此组策略设置定义 UE-V Agent 是否同步 Windows 应用的设置。</span><span class="sxs-lookup"><span data-stu-id="42f42-182">This Group Policy setting defines whether the UE-V Agent synchronizes settings for Windows apps.</span></span></p></td>
<td align="left"><p><span data-ttu-id="42f42-183">默认为同步 Windows 应用。</span><span class="sxs-lookup"><span data-stu-id="42f42-183">The default is to synchronize Windows apps.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="42f42-184">Windows 应用列表</span><span class="sxs-lookup"><span data-stu-id="42f42-184">Windows App List</span></span></p></td>
<td align="left"><p><span data-ttu-id="42f42-185">计算机和用户</span><span class="sxs-lookup"><span data-stu-id="42f42-185">Computer and User</span></span></p></td>
<td align="left"><p><span data-ttu-id="42f42-186">此设置列出 Windows 应用的系列程序包名称，并明确表明 UE-V 是否同步了该应用的设置。</span><span class="sxs-lookup"><span data-stu-id="42f42-186">This setting lists the family package names of the Windows apps and states expressly whether UE-V synchronizes that app’s settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="42f42-187">你可以使用此设置指定应用的设置永远不会通过 UE-V 同步，即使所有其他 Windows 应用的设置都已同步。</span><span class="sxs-lookup"><span data-stu-id="42f42-187">You can use this setting to specify that settings of an app are never synchronized by UE-V, even if the settings of all other Windows apps are synchronized.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="42f42-188">同步未列出的 Windows 应用</span><span class="sxs-lookup"><span data-stu-id="42f42-188">Sync Unlisted Windows Apps</span></span></p></td>
<td align="left"><p><span data-ttu-id="42f42-189">计算机和用户</span><span class="sxs-lookup"><span data-stu-id="42f42-189">Computer and User</span></span></p></td>
<td align="left"><p><span data-ttu-id="42f42-190">此组策略设置定义未在 Windows 应用列表中显式列出的 Windows 应用的 UE-V Agent 的默认设置同步行为。</span><span class="sxs-lookup"><span data-stu-id="42f42-190">This Group Policy setting defines the default settings sync behavior of the UE-V Agent for Windows apps that are not explicitly listed in the Windows app list.</span></span></p></td>
<td align="left"><p><span data-ttu-id="42f42-191">默认情况下，UE-V Agent 仅同步 Windows 应用列表中包含的那些 Windows 应用的设置。</span><span class="sxs-lookup"><span data-stu-id="42f42-191">By default, the UE-V Agent only synchronizes settings of those Windows apps that are included in the Windows app list.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="42f42-192">有关同步 Windows 应用的详细信息，请参阅[Windows 应用列表](https://technet.microsoft.com/library/dn458925.aspx#win8applist)。</span><span class="sxs-lookup"><span data-stu-id="42f42-192">For more information about synchronizing Windows apps, see [Windows App List](https://technet.microsoft.com/library/dn458925.aspx#win8applist).</span></span>

**<span data-ttu-id="42f42-193">配置以计算机为目标的组策略设置</span><span class="sxs-lookup"><span data-stu-id="42f42-193">To configure computer-targeted Group Policy settings</span></span>**

1.  <span data-ttu-id="42f42-194">在充当域控制器的计算机上使用组策略管理控制台（GPMC）或高级组策略管理（AGPM），以管理 UE-V 计算机的组策略设置。</span><span class="sxs-lookup"><span data-stu-id="42f42-194">Use the Group Policy Management Console (GPMC) or the Advanced Group Policy Management (AGPM) on the computer that acts as a domain controller to manage Group Policy settings for UE-V computers.</span></span> <span data-ttu-id="42f42-195">导航到 "**计算机配置**"，选择 "**策略**"，选择 "**管理模板**"，单击 " **Windows 组件**"，然后选择 " **Microsoft 用户体验虚拟化**"。</span><span class="sxs-lookup"><span data-stu-id="42f42-195">Navigate to **Computer configuration**, select **Policies**, select **Administrative Templates**, click **Windows Components**, and then select **Microsoft User Experience Virtualization**.</span></span>

2.  <span data-ttu-id="42f42-196">选择要编辑的组策略设置。</span><span class="sxs-lookup"><span data-stu-id="42f42-196">Select the Group Policy setting to be edited.</span></span>

**<span data-ttu-id="42f42-197">配置用户定向的组策略设置</span><span class="sxs-lookup"><span data-stu-id="42f42-197">To configure user-targeted Group Policy settings</span></span>**

1.  <span data-ttu-id="42f42-198">在域控制器计算机上的 Microsoft 桌面优化包（MDOP）中使用组策略管理控制台（GPMC）或高级组策略管理（AGPM）工具管理 UE-V 的组策略设置。</span><span class="sxs-lookup"><span data-stu-id="42f42-198">Use the Group Policy Management Console (GPMC) or the Advanced Group Policy Management (AGPM) tool in Microsoft Desktop Optimization Pack (MDOP) on the domain controller computer to manage Group Policy settings for UE-V.</span></span> <span data-ttu-id="42f42-199">导航到 "**用户配置**"，选择 "**策略**"，选择 "**管理模板**"，单击 " **Windows 组件**"，然后选择 " **Microsoft 用户体验虚拟化**"。</span><span class="sxs-lookup"><span data-stu-id="42f42-199">Navigate to **User configuration**, select **Policies**, select **Administrative Templates**, click **Windows Components**, and then select **Microsoft User Experience Virtualization**.</span></span>

2.  <span data-ttu-id="42f42-200">选择 "已编辑的组策略" 设置。</span><span class="sxs-lookup"><span data-stu-id="42f42-200">Select the edited Group Policy setting.</span></span>

<span data-ttu-id="42f42-201">UE-V Agent 使用以下优先级顺序确定同步。</span><span class="sxs-lookup"><span data-stu-id="42f42-201">The UE-V Agent uses the following order of precedence to determine synchronization.</span></span>

**<span data-ttu-id="42f42-202">UE-V 设置的优先级顺序</span><span class="sxs-lookup"><span data-stu-id="42f42-202">Order of precedence for UE-V settings</span></span>**

1.  <span data-ttu-id="42f42-203">由组策略设置管理的由用户设定的设置-这些配置设置由 "组策略" 下的 "组策略" 存储在注册表项中 `HKEY_CURRENT_USER\Software\Policies\Microsoft\Uev\Agent\Configuration` 。</span><span class="sxs-lookup"><span data-stu-id="42f42-203">User-targeted settings that are managed by Group Policy settings - These configuration settings are stored in the registry key by Group Policy under `HKEY_CURRENT_USER\Software\Policies\Microsoft\Uev\Agent\Configuration`.</span></span>

2.  <span data-ttu-id="42f42-204">由组策略设置管理的由计算机设定的设置-这些配置设置由 "组策略" 下的 "组策略" 存储在注册表项中 `HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Uev\Agent\Configuration` 。</span><span class="sxs-lookup"><span data-stu-id="42f42-204">Computer-targeted settings that are managed by Group Policy settings - These configuration settings are stored in the registry key by Group Policy under `HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Uev\Agent\Configuration`.</span></span>

3.  <span data-ttu-id="42f42-205">由当前用户使用 Windows PowerShell 或 Windows 管理规范（WMI）定义的配置设置，这些配置设置由 UE-V Agent 在此注册表位置下存储： `HKEY_CURRENT_USER\Software\Microsoft\Uev\Agent\Configuration` 。</span><span class="sxs-lookup"><span data-stu-id="42f42-205">Configuration settings that are defined by the current user by using Windows PowerShell or Windows management Instrumentation (WMI) - These configuration settings are stored by the UE-V Agent under this registry location: `HKEY_CURRENT_USER\Software\Microsoft\Uev\Agent\Configuration`.</span></span>

4.  <span data-ttu-id="42f42-206">使用 Windows PowerShell 或 WMI 为计算机定义的配置设置。</span><span class="sxs-lookup"><span data-stu-id="42f42-206">Configuration settings that are defined for the computer by using Windows PowerShell or WMI.</span></span> <span data-ttu-id="42f42-207">这些配置设置由 UE-V Agent 在此注册表位置下存储： `HKEY_LOCAL_MACHINE\Software\Microsoft\Uev\Agent\Configuration` 。</span><span class="sxs-lookup"><span data-stu-id="42f42-207">These configuration settings are stored by the UE-V Agent under this registry location: `HKEY_LOCAL_MACHINE\Software\Microsoft\Uev\Agent\Configuration`.</span></span>

    <span data-ttu-id="42f42-208">已**获得有关 ue-v 的建议**？</span><span class="sxs-lookup"><span data-stu-id="42f42-208">**Got a suggestion for UE-V**?</span></span> <span data-ttu-id="42f42-209">在[此处](http://uev.uservoice.com/forums/280428-microsoft-user-experience-virtualization)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="42f42-209">Add or vote on suggestions [here](http://uev.uservoice.com/forums/280428-microsoft-user-experience-virtualization).</span></span> <span data-ttu-id="42f42-210">是否**遇到了 ue-v 问题**？</span><span class="sxs-lookup"><span data-stu-id="42f42-210">**Got a UE-V issue**?</span></span> <span data-ttu-id="42f42-211">使用[Ue-v TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopuev)。</span><span class="sxs-lookup"><span data-stu-id="42f42-211">Use the [UE-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopuev).</span></span>

## <span data-ttu-id="42f42-212">相关主题</span><span class="sxs-lookup"><span data-stu-id="42f42-212">Related topics</span></span>


[<span data-ttu-id="42f42-213">管理 UE-V 2. x</span><span class="sxs-lookup"><span data-stu-id="42f42-213">Administering UE-V 2.x</span></span>](administering-ue-v-2x-new-uevv2.md)

[<span data-ttu-id="42f42-214">管理 UE-V 2.x 的配置</span><span class="sxs-lookup"><span data-stu-id="42f42-214">Manage Configurations for UE-V 2.x</span></span>](manage-configurations-for-ue-v-2x-new-uevv2.md)

 

 





