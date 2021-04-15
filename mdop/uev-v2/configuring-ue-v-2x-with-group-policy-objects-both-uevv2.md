---
title: 使用组策略对象配置 UE-V 2.x
description: 使用组策略对象配置 UE-V 2.x
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
ms.openlocfilehash: b6c9636df36a53cbf65bf1904965f2809484b99c
ms.sourcegitcommit: bdc377477a8cc9e973fbcdd67c2f07b882c5d61e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "11494057"
---
# <a name="configuring-ue-v-2x-with-group-policy-objects"></a><span data-ttu-id="5678c-103">使用组策略对象配置 UE-V 2.x</span><span class="sxs-lookup"><span data-stu-id="5678c-103">Configuring UE-V 2.x with Group Policy Objects</span></span>


<span data-ttu-id="5678c-104">某些 Microsoft 用户体验虚拟化 (UE-V) 2.0、2.1 和 2.1 SP1 组策略设置可以定义用于计算机，也可以为用户定义其他组策略设置。</span><span class="sxs-lookup"><span data-stu-id="5678c-104">Some Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, and 2.1 SP1 Group Policy settings can be defined for computers, and other Group Policy settings can be defined for users.</span></span> <span data-ttu-id="5678c-105">若要了解如何安装 UE-V 组策略 ADMX 文件，请参阅安装 [UE-V 2 组策略 ADMX 模板](https://technet.microsoft.com/library/dn458891.aspx#admx)。</span><span class="sxs-lookup"><span data-stu-id="5678c-105">For information about how to install UE-V Group Policy ADMX files, see [Installing the UE-V 2 Group Policy ADMX Templates](https://technet.microsoft.com/library/dn458891.aspx#admx).</span></span>

<span data-ttu-id="5678c-106">可以针对 UE-V 配置以下策略设置。</span><span class="sxs-lookup"><span data-stu-id="5678c-106">The following policy settings can be configured for UE-V.</span></span>

**<span data-ttu-id="5678c-107">组策略设置</span><span class="sxs-lookup"><span data-stu-id="5678c-107">Group Policy settings</span></span>**

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="5678c-108">组策略设置名称</span><span class="sxs-lookup"><span data-stu-id="5678c-108">Group Policy setting name</span></span></th>
<th align="left"><span data-ttu-id="5678c-109">目标</span><span class="sxs-lookup"><span data-stu-id="5678c-109">Target</span></span></th>
<th align="left"><span data-ttu-id="5678c-110">组策略设置说明</span><span class="sxs-lookup"><span data-stu-id="5678c-110">Group Policy setting description</span></span></th>
<th align="left"><span data-ttu-id="5678c-111">配置选项</span><span class="sxs-lookup"><span data-stu-id="5678c-111">Configuration options</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5678c-112">配置 Sync 方法</span><span class="sxs-lookup"><span data-stu-id="5678c-112">Configure Sync Method</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-113">计算机和用户</span><span class="sxs-lookup"><span data-stu-id="5678c-113">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-114">通过使用此组策略设置，您可以配置用户体验虚拟化 (UE-V) 是否使用同步提供程序功能。</span><span class="sxs-lookup"><span data-stu-id="5678c-114">By using this Group Policy setting, you can configure whether User Experience Virtualization (UE-V) uses the sync provider feature.</span></span> <span data-ttu-id="5678c-115">此策略设置还允许您在用户设置导入延迟时显示通知。</span><span class="sxs-lookup"><span data-stu-id="5678c-115">This policy setting also lets you enable a notification to appear when the import of user settings is delayed.</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-116">启用此设置可配置 UE-V 代理不使用同步提供程序或使用外部同步引擎。</span><span class="sxs-lookup"><span data-stu-id="5678c-116">Enable this setting to configure the UE-V agent not to use the sync provider, or to use the external synchronization engine.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5678c-117">联系 IT 链接文本</span><span class="sxs-lookup"><span data-stu-id="5678c-117">Contact IT Link Text</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-118">仅计算机</span><span class="sxs-lookup"><span data-stu-id="5678c-118">Computers Only</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-119">此组策略设置指定公司设置中心中"联系人 IT URL"超链接的文本。</span><span class="sxs-lookup"><span data-stu-id="5678c-119">This Group Policy setting specifies the text of the Contact IT URL hyperlink in the Company Settings Center.</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-120">如果启用此组策略设置，公司设置中心将在指向"联系人 IT URL"的链接中显示指定的文本。</span><span class="sxs-lookup"><span data-stu-id="5678c-120">If you enable this Group Policy setting, the Company Settings Center displays the specified text in the link to the Contact IT URL.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5678c-121">联系 IT URL</span><span class="sxs-lookup"><span data-stu-id="5678c-121">Contact IT URL</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-122">仅计算机</span><span class="sxs-lookup"><span data-stu-id="5678c-122">Computers Only</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-123">此组策略设置指定公司设置中心中"联系人 IT"链接的 URL。</span><span class="sxs-lookup"><span data-stu-id="5678c-123">This Group Policy setting specifies the URL for the Contact IT link in the Company Settings Center.</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-124">如果启用此设置，公司设置中心"联系 IT 人员"文本将链接到指定的 URL。</span><span class="sxs-lookup"><span data-stu-id="5678c-124">If you enable this setting, the Company Settings Center Contact IT text links to the specified URL.</span></span> <span data-ttu-id="5678c-125">该链接可以是任何标准协议，如 HTTP 或 mailto。</span><span class="sxs-lookup"><span data-stu-id="5678c-125">The link can be of any standard protocol, such as HTTP or mailto.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5678c-126">首次使用通知</span><span class="sxs-lookup"><span data-stu-id="5678c-126">First Use Notification</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-127">仅计算机</span><span class="sxs-lookup"><span data-stu-id="5678c-127">Computers Only</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-128">此组策略设置启用当 UE-V 时在通知区域中显示的通知</span><span class="sxs-lookup"><span data-stu-id="5678c-128">This Group Policy setting enables a notification in the notification area that appears when the UE-V</span></span></p>
<p><span data-ttu-id="5678c-129">代理首次运行。</span><span class="sxs-lookup"><span data-stu-id="5678c-129">agent runs for the first time.</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-130">默认值为启用。</span><span class="sxs-lookup"><span data-stu-id="5678c-130">The default is enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5678c-131">同步前 Ping 设置存储位置</span><span class="sxs-lookup"><span data-stu-id="5678c-131">Ping the settings storage location before sync</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-132">计算机和用户</span><span class="sxs-lookup"><span data-stu-id="5678c-132">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-133">此策略设置允许配置 UE-V 同步提供程序在尝试同步设置之前 ping 设置存储路径，以便验证连接。</span><span class="sxs-lookup"><span data-stu-id="5678c-133">This policy setting allows configuration of the UE-V sync provider to ping the settings storage path before attempting to sync settings in order to verify the connection.</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-134">启用或禁用此组策略设置。</span><span class="sxs-lookup"><span data-stu-id="5678c-134">Enable or disable this Group Policy setting.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5678c-135">设置程序包大小警告阈值</span><span class="sxs-lookup"><span data-stu-id="5678c-135">Settings package size warning threshold</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-136">计算机和用户</span><span class="sxs-lookup"><span data-stu-id="5678c-136">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-137">通过此组策略设置，可以将 UE-V 代理配置为在设置包文件大小达到定义的阈值时报告。</span><span class="sxs-lookup"><span data-stu-id="5678c-137">This Group Policy setting lets you configure the UE-V Agent to report when a settings package file size reaches a defined threshold.</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-138">指定设置包大小的首选阈值（以 KB (KB) ）。</span><span class="sxs-lookup"><span data-stu-id="5678c-138">Specify the preferred threshold for settings package sizes in kilobytes (KB).</span></span></p>
<p><span data-ttu-id="5678c-139">默认情况下，UE-V 代理没有程序包文件大小阈值。</span><span class="sxs-lookup"><span data-stu-id="5678c-139">By default, the UE-V Agent does not have a package file size threshold.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5678c-140">设置存储路径</span><span class="sxs-lookup"><span data-stu-id="5678c-140">Settings storage path</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-141">计算机和用户</span><span class="sxs-lookup"><span data-stu-id="5678c-141">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-142">此组策略设置配置存储用户设置的位置。</span><span class="sxs-lookup"><span data-stu-id="5678c-142">This Group Policy setting configures where the user settings are to be stored.</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-143">在 UNC 路径和变量（如 \Server\SettingsShare%username%） () UNC (通用命名约定。</span><span class="sxs-lookup"><span data-stu-id="5678c-143">Enter a Universal Naming Convention (UNC) path and variables such as \Server\SettingsShare%username%.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5678c-144">设置模板目录路径</span><span class="sxs-lookup"><span data-stu-id="5678c-144">Settings template catalog path</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-145">仅计算机</span><span class="sxs-lookup"><span data-stu-id="5678c-145">Computers Only</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-146">此组策略设置配置存储自定义设置位置模板的位置。</span><span class="sxs-lookup"><span data-stu-id="5678c-146">This Group Policy setting configures where custom settings location templates are stored.</span></span> <span data-ttu-id="5678c-147">此策略设置还配置目录是否用于替换随 UE-V 代理一起安装的默认 Microsoft 模板。</span><span class="sxs-lookup"><span data-stu-id="5678c-147">This policy setting also configures whether the catalog is to be used to replace the default Microsoft templates that are installed with the UE-V Agent.</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-148">输入 UNC (通用命名) 路径，如 \Server\TemplateShare 或计算机上文件夹位置。</span><span class="sxs-lookup"><span data-stu-id="5678c-148">Enter a Universal Naming Convention (UNC) path such as \Server\TemplateShare or a folder location on the computer.</span></span></p>
<p><span data-ttu-id="5678c-149">选中此复选框以替换默认的 Microsoft 模板。</span><span class="sxs-lookup"><span data-stu-id="5678c-149">Select the check box to replace the default Microsoft templates.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5678c-150">通过按流量计费的连接同步设置</span><span class="sxs-lookup"><span data-stu-id="5678c-150">Sync settings over metered connections</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-151">计算机和用户</span><span class="sxs-lookup"><span data-stu-id="5678c-151">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-152">此组策略设置定义 UE-V 是否通过按流量计费的连接同步设置。</span><span class="sxs-lookup"><span data-stu-id="5678c-152">This Group Policy setting defines whether UE-V synchronizes settings over metered connections.</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-153">默认情况下，UE-V 代理不会通过按流量计费的连接同步设置。</span><span class="sxs-lookup"><span data-stu-id="5678c-153">By default, the UE-V Agent does not synchronize settings over a metered connection.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5678c-154">即使漫游时，也通过按流量计费的连接同步设置</span><span class="sxs-lookup"><span data-stu-id="5678c-154">Sync settings over metered connections even when roaming</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-155">计算机和用户</span><span class="sxs-lookup"><span data-stu-id="5678c-155">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-156">此组策略设置定义 UE-V 是否通过主提供商网络外部的按流量计费的连接同步设置，例如，当数据连接在漫游模式下时。</span><span class="sxs-lookup"><span data-stu-id="5678c-156">This Group Policy setting defines whether UE-V synchronizes settings over metered connections outside of the home provider network, for example, when the data connection is in roaming mode.</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-157">默认情况下，当 UE-V 在漫游模式下时，它不会通过按流量计费的连接同步设置。</span><span class="sxs-lookup"><span data-stu-id="5678c-157">By default, UE-V does not synchronize settings over a metered connection when it is in roaming mode.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5678c-158">同步超时</span><span class="sxs-lookup"><span data-stu-id="5678c-158">Synchronization timeout</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-159">计算机和用户</span><span class="sxs-lookup"><span data-stu-id="5678c-159">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-160">此组策略设置配置计算机从远程设置位置检索用户设置时在退出之前等待的毫秒数。</span><span class="sxs-lookup"><span data-stu-id="5678c-160">This Group Policy setting configures the number of milliseconds that the computer waits before a time-out when it retrieves user settings from the remote settings location.</span></span> <span data-ttu-id="5678c-161">如果远程存储位置不可用，并且用户不使用同步提供程序，则应用程序启动将延迟多毫秒。</span><span class="sxs-lookup"><span data-stu-id="5678c-161">If the remote storage location is unavailable, and the user does not use the sync provider, the application start is delayed by this many milliseconds.</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-162">指定首选同步的退出时间（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="5678c-162">Specify the preferred synchronization time-out in milliseconds.</span></span> <span data-ttu-id="5678c-163">默认值为 2000 毫秒。</span><span class="sxs-lookup"><span data-stu-id="5678c-163">The default value is 2000 milliseconds.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5678c-164">同步 Windows 设置</span><span class="sxs-lookup"><span data-stu-id="5678c-164">Synchronize Windows settings</span></span> </p></td>
<td align="left"><p><span data-ttu-id="5678c-165">计算机和用户</span><span class="sxs-lookup"><span data-stu-id="5678c-165">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-166">此组策略设置配置 Windows 设置的同步。</span><span class="sxs-lookup"><span data-stu-id="5678c-166">This Group Policy setting configures the synchronization of Windows settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-167">选择在计算机之间同步的 Windows 设置。</span><span class="sxs-lookup"><span data-stu-id="5678c-167">Select which Windows settings synchronize between computers.</span></span></p>
<p><span data-ttu-id="5678c-168">默认情况下，Windows 主题、桌面设置和轻松使用设置在相同操作系统版本的计算机之间同步设置。</span><span class="sxs-lookup"><span data-stu-id="5678c-168">By default, Windows themes, desktop settings, and Ease of Access settings synchronize settings between computers of the same operating system version.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5678c-169">任务栏图标</span><span class="sxs-lookup"><span data-stu-id="5678c-169">Tray Icon</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-170">仅计算机</span><span class="sxs-lookup"><span data-stu-id="5678c-170">Computers Only</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-171">此组策略设置启用 UE-V 任务栏图标。</span><span class="sxs-lookup"><span data-stu-id="5678c-171">This Group Policy setting enables the UE-V tray icon.</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-172">默认值为启用。</span><span class="sxs-lookup"><span data-stu-id="5678c-172">The default is enabled.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5678c-173">使用用户体验虚拟化 (UE-V) </span><span class="sxs-lookup"><span data-stu-id="5678c-173">Use User Experience Virtualization (UE-V)</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-174">计算机和用户</span><span class="sxs-lookup"><span data-stu-id="5678c-174">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-175">此组策略设置允许你启用或禁用 UE-V。</span><span class="sxs-lookup"><span data-stu-id="5678c-175">This Group Policy setting lets you enable or disable UE-V.</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-176">启用或禁用此组策略设置。</span><span class="sxs-lookup"><span data-stu-id="5678c-176">Enable or disable this Group Policy setting.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5678c-177">VDI 配置</span><span class="sxs-lookup"><span data-stu-id="5678c-177">VDI Configuration</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-178">计算机和用户</span><span class="sxs-lookup"><span data-stu-id="5678c-178">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-179">此策略设置为在池 VDI 环境中运行的计算机配置 UE-V 回滚信息的同步。</span><span class="sxs-lookup"><span data-stu-id="5678c-179">This policy setting configures the synchronization of UE-V rollback information for computers running in a pooled VDI environment.</span></span> <span data-ttu-id="5678c-180">如果启用此策略，则 UE-V 回滚状态在注销时复制到设置存储位置，在登录时还原。</span><span class="sxs-lookup"><span data-stu-id="5678c-180">If this policy is enabled, the UE-V rollback state is copied to the settings storage location on logout and restored on login.</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-181">启用或禁用此组策略设置。</span><span class="sxs-lookup"><span data-stu-id="5678c-181">Enable or disable this Group Policy setting.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="5678c-182">注意</span><span class="sxs-lookup"><span data-stu-id="5678c-182">Note</span></span>**  
<span data-ttu-id="5678c-183">此外，组策略设置可用于许多桌面应用程序和 Windows 应用。</span><span class="sxs-lookup"><span data-stu-id="5678c-183">In addition, Group Policy settings are available for many desktop applications and Windows apps.</span></span> <span data-ttu-id="5678c-184">可以使用这些设置为特定应用程序启用或禁用设置同步。</span><span class="sxs-lookup"><span data-stu-id="5678c-184">You can use these settings to enable or disable settings synchronization for specific applications.</span></span>

 

**<span data-ttu-id="5678c-185">Windows 应用组策略设置</span><span class="sxs-lookup"><span data-stu-id="5678c-185">Windows App Group Policy settings</span></span>**

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="5678c-186">组策略设置名称</span><span class="sxs-lookup"><span data-stu-id="5678c-186">Group Policy setting name</span></span></th>
<th align="left"><span data-ttu-id="5678c-187">目标</span><span class="sxs-lookup"><span data-stu-id="5678c-187">Target</span></span></th>
<th align="left"><span data-ttu-id="5678c-188">组策略设置说明</span><span class="sxs-lookup"><span data-stu-id="5678c-188">Group Policy setting description</span></span></th>
<th align="left"><span data-ttu-id="5678c-189">配置选项</span><span class="sxs-lookup"><span data-stu-id="5678c-189">Configuration options</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5678c-190">不同步 Windows 应用</span><span class="sxs-lookup"><span data-stu-id="5678c-190">Do not synchronize Windows Apps</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-191">计算机和用户</span><span class="sxs-lookup"><span data-stu-id="5678c-191">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-192">此组策略设置定义 UE-V 代理是否同步 Windows 应用的设置。</span><span class="sxs-lookup"><span data-stu-id="5678c-192">This Group Policy setting defines whether the UE-V Agent synchronizes settings for Windows apps.</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-193">默认设置是同步 Windows 应用。</span><span class="sxs-lookup"><span data-stu-id="5678c-193">The default is to synchronize Windows apps.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5678c-194">Windows 应用列表</span><span class="sxs-lookup"><span data-stu-id="5678c-194">Windows App List</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-195">计算机和用户</span><span class="sxs-lookup"><span data-stu-id="5678c-195">Computer and User</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-196">此设置列出 Windows 应用的系列程序包名称，并明确指出 UE-V 是否同步该应用的设置。</span><span class="sxs-lookup"><span data-stu-id="5678c-196">This setting lists the family package names of the Windows apps and states expressly whether UE-V synchronizes that app’s settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-197">可以使用此设置指定 UE-V 从不同步应用的设置，即使所有其他 Windows 应用的设置已同步。</span><span class="sxs-lookup"><span data-stu-id="5678c-197">You can use this setting to specify that settings of an app are never synchronized by UE-V, even if the settings of all other Windows apps are synchronized.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5678c-198">同步未列出的 Windows 应用</span><span class="sxs-lookup"><span data-stu-id="5678c-198">Sync Unlisted Windows Apps</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-199">计算机和用户</span><span class="sxs-lookup"><span data-stu-id="5678c-199">Computer and User</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-200">此组策略设置定义未在 Windows 应用列表中显式列出的 Windows 应用的 UE-V 代理的默认设置同步行为。</span><span class="sxs-lookup"><span data-stu-id="5678c-200">This Group Policy setting defines the default settings sync behavior of the UE-V Agent for Windows apps that are not explicitly listed in the Windows app list.</span></span></p></td>
<td align="left"><p><span data-ttu-id="5678c-201">默认情况下，UE-V 代理仅同步 Windows 应用列表中包含的这些 Windows 应用的设置。</span><span class="sxs-lookup"><span data-stu-id="5678c-201">By default, the UE-V Agent only synchronizes settings of those Windows apps that are included in the Windows app list.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="5678c-202">有关同步 Windows 应用详细信息，请参阅 Windows [应用列表](https://technet.microsoft.com/library/dn458925.aspx#win8applist)。</span><span class="sxs-lookup"><span data-stu-id="5678c-202">For more information about synchronizing Windows apps, see [Windows App List](https://technet.microsoft.com/library/dn458925.aspx#win8applist).</span></span>

**<span data-ttu-id="5678c-203">配置面向计算机的组策略设置</span><span class="sxs-lookup"><span data-stu-id="5678c-203">To configure computer-targeted Group Policy settings</span></span>**

1.  <span data-ttu-id="5678c-204">在充当域控制器的计算机上使用组策略管理控制台 (GPMC) 或高级组策略管理 (AGPM) 来管理 UE-V 计算机的组策略设置。</span><span class="sxs-lookup"><span data-stu-id="5678c-204">Use the Group Policy Management Console (GPMC) or the Advanced Group Policy Management (AGPM) on the computer that acts as a domain controller to manage Group Policy settings for UE-V computers.</span></span> <span data-ttu-id="5678c-205">导航到 **"计算机配置"，** 选择"**策略\*\*\*\*"，选择"管理模板"，** 单击 **"Windows**组件"，然后选择 **"Microsoft 用户体验虚拟化"。**</span><span class="sxs-lookup"><span data-stu-id="5678c-205">Navigate to **Computer configuration**, select **Policies**, select **Administrative Templates**, click **Windows Components**, and then select **Microsoft User Experience Virtualization**.</span></span>

2.  <span data-ttu-id="5678c-206">选择要编辑的组策略设置。</span><span class="sxs-lookup"><span data-stu-id="5678c-206">Select the Group Policy setting to be edited.</span></span>

**<span data-ttu-id="5678c-207">配置面向用户的组策略设置</span><span class="sxs-lookup"><span data-stu-id="5678c-207">To configure user-targeted Group Policy settings</span></span>**

1.  <span data-ttu-id="5678c-208">使用域控制器计算机上 Microsoft 桌面优化包 (MDOP) 中的组策略管理控制台 (GPMC) 或高级组策略管理 (AGPM) 工具管理 UE-V 的组策略设置。</span><span class="sxs-lookup"><span data-stu-id="5678c-208">Use the Group Policy Management Console (GPMC) or the Advanced Group Policy Management (AGPM) tool in Microsoft Desktop Optimization Pack (MDOP) on the domain controller computer to manage Group Policy settings for UE-V.</span></span> <span data-ttu-id="5678c-209">导航到 **"用户配置"，** 选择"**策略**"，选择"**管理模板"，** 单击 **"Windows**组件"，然后选择 **"Microsoft 用户体验虚拟化"。**</span><span class="sxs-lookup"><span data-stu-id="5678c-209">Navigate to **User configuration**, select **Policies**, select **Administrative Templates**, click **Windows Components**, and then select **Microsoft User Experience Virtualization**.</span></span>

2.  <span data-ttu-id="5678c-210">选择已编辑的组策略设置。</span><span class="sxs-lookup"><span data-stu-id="5678c-210">Select the edited Group Policy setting.</span></span>

<span data-ttu-id="5678c-211">UE-V 代理按以下优先顺序确定同步。</span><span class="sxs-lookup"><span data-stu-id="5678c-211">The UE-V Agent uses the following order of precedence to determine synchronization.</span></span>

**<span data-ttu-id="5678c-212">UE-V 设置的优先级顺序</span><span class="sxs-lookup"><span data-stu-id="5678c-212">Order of precedence for UE-V settings</span></span>**

1.  <span data-ttu-id="5678c-213">由组策略设置管理的用户目标设置 - 这些配置设置由 下的组策略存储在注册表项中 `HKEY_CURRENT_USER\Software\Policies\Microsoft\Uev\Agent\Configuration` 。</span><span class="sxs-lookup"><span data-stu-id="5678c-213">User-targeted settings that are managed by Group Policy settings - These configuration settings are stored in the registry key by Group Policy under `HKEY_CURRENT_USER\Software\Policies\Microsoft\Uev\Agent\Configuration`.</span></span>

2.  <span data-ttu-id="5678c-214">由组策略设置管理的计算机目标设置 - 这些配置设置由 下的组策略存储在注册表项中 `HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Uev\Agent\Configuration` 。</span><span class="sxs-lookup"><span data-stu-id="5678c-214">Computer-targeted settings that are managed by Group Policy settings - These configuration settings are stored in the registry key by Group Policy under `HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Uev\Agent\Configuration`.</span></span>

3.  <span data-ttu-id="5678c-215">当前用户使用 Windows PowerShell 或 Windows management Instrumentation (WMI) 定义的配置设置 - 这些配置设置由 UE-V 代理存储在此注册表位置下 `HKEY_CURRENT_USER\Software\Microsoft\Uev\Agent\Configuration` ：。</span><span class="sxs-lookup"><span data-stu-id="5678c-215">Configuration settings that are defined by the current user by using Windows PowerShell or Windows management Instrumentation (WMI) - These configuration settings are stored by the UE-V Agent under this registry location: `HKEY_CURRENT_USER\Software\Microsoft\Uev\Agent\Configuration`.</span></span>

4.  <span data-ttu-id="5678c-216">通过使用或 WMI 为计算机定义的Windows PowerShell设置。</span><span class="sxs-lookup"><span data-stu-id="5678c-216">Configuration settings that are defined for the computer by using Windows PowerShell or WMI.</span></span> <span data-ttu-id="5678c-217">这些配置设置由 UE-V 代理存储在此注册表位置下 `HKEY_LOCAL_MACHINE\Software\Microsoft\Uev\Agent\Configuration` ：。</span><span class="sxs-lookup"><span data-stu-id="5678c-217">These configuration settings are stored by the UE-V Agent under this registry location: `HKEY_LOCAL_MACHINE\Software\Microsoft\Uev\Agent\Configuration`.</span></span>

    <span data-ttu-id="5678c-218">**收到有关 UE-V 的建议**？</span><span class="sxs-lookup"><span data-stu-id="5678c-218">**Got a suggestion for UE-V**?</span></span> <span data-ttu-id="5678c-219">在此处添加建议或对建议 [投票](http://uev.uservoice.com/forums/280428-microsoft-user-experience-virtualization)。</span><span class="sxs-lookup"><span data-stu-id="5678c-219">Add or vote on suggestions [here](http://uev.uservoice.com/forums/280428-microsoft-user-experience-virtualization).</span></span> <span data-ttu-id="5678c-220">**有 UE-V 问题**？</span><span class="sxs-lookup"><span data-stu-id="5678c-220">**Got a UE-V issue**?</span></span> <span data-ttu-id="5678c-221">使用 [UE-V TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopuev)。</span><span class="sxs-lookup"><span data-stu-id="5678c-221">Use the [UE-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopuev).</span></span>

## <a name="related-topics"></a><span data-ttu-id="5678c-222">相关主题</span><span class="sxs-lookup"><span data-stu-id="5678c-222">Related topics</span></span>


[<span data-ttu-id="5678c-223">管理 UE-V 2.x</span><span class="sxs-lookup"><span data-stu-id="5678c-223">Administering UE-V 2.x</span></span>](administering-ue-v-2x-new-uevv2.md)

[<span data-ttu-id="5678c-224">管理 UE-V 2.x 的配置</span><span class="sxs-lookup"><span data-stu-id="5678c-224">Manage Configurations for UE-V 2.x</span></span>](manage-configurations-for-ue-v-2x-new-uevv2.md)

 

 
