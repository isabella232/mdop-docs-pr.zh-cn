---
title: 通过 Windows PowerShell 和 WMI 管理 UE-V 2 x 代理和程序包
description: 通过 Windows PowerShell 和 WMI 管理 UE-V 2 x 代理和程序包
author: dansimp
ms.assetid: 56e6780b-8b2c-4717-91c8-2af63062ab75
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 6a709d2c66266cf33b8e89ddd905aa0f21eb7dfe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804041"
---
# <span data-ttu-id="426a1-103">通过 Windows PowerShell 和 WMI 管理 UE-V 2 x 代理和程序包</span><span class="sxs-lookup"><span data-stu-id="426a1-103">Managing the UE-V 2.x Agent and Packages with Windows PowerShell and WMI</span></span>


<span data-ttu-id="426a1-104">你可以使用 Windows Management Instrumentation （WMI）和 Windows PowerShell 来管理 Microsoft 用户体验虚拟化（UE-V）2.0、2.1 和 2.1 SP1 代理配置和同步行为。</span><span class="sxs-lookup"><span data-stu-id="426a1-104">You can use Windows Management Instrumentation (WMI) and Windows PowerShell to manage Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, and 2.1 SP1 Agent configuration and synchronization behavior.</span></span> <span data-ttu-id="426a1-105">有关 UE-V PowerShell cmdlet 的完整列表，请参阅[ue-v 2 Cmdlet 参考](https://go.microsoft.com/fwlink/?LinkId=393495)（ https://go.microsoft.com/fwlink/?LinkId=393495) 。</span><span class="sxs-lookup"><span data-stu-id="426a1-105">For a complete list of UE-V PowerShell cmdlets, see [UE-V 2 Cmdlet Reference](https://go.microsoft.com/fwlink/?LinkId=393495) (https://go.microsoft.com/fwlink/?LinkId=393495).</span></span>

**<span data-ttu-id="426a1-106">使用 Windows PowerShell 部署 UE-V Agent</span><span class="sxs-lookup"><span data-stu-id="426a1-106">To deploy the UE-V Agent by using Windows PowerShell</span></span>**

1.  <span data-ttu-id="426a1-107">在易于访问的网络共享中暂存 UE-V 安装程序文件。</span><span class="sxs-lookup"><span data-stu-id="426a1-107">Stage the UE-V installer file in an accessible network share.</span></span>

    **<span data-ttu-id="426a1-108">注意</span><span class="sxs-lookup"><span data-stu-id="426a1-108">Note</span></span>**  
    <span data-ttu-id="426a1-109">使用 AgentSetup.exe 部署32位和64位的 UE-V Agent 版本。</span><span class="sxs-lookup"><span data-stu-id="426a1-109">Use AgentSetup.exe to deploy both 32-bit and 64-bit versions of the UE-V Agent.</span></span> <span data-ttu-id="426a1-110">Windows Installer 程序包、AgentSetupx86.msi 和 AgentSetupx64.msi 适用于每个体系结构。</span><span class="sxs-lookup"><span data-stu-id="426a1-110">Windows Installer packages, AgentSetupx86.msi and AgentSetupx64.msi, are available for each architecture.</span></span> <span data-ttu-id="426a1-111">若要在以后使用安装文件卸载 UE-V Agent，必须使用相同的文件类型。</span><span class="sxs-lookup"><span data-stu-id="426a1-111">To uninstall the UE-V Agent at a later time by using the installation file, you must use the same file type.</span></span>



2.  <span data-ttu-id="426a1-112">使用以下 Windows PowerShell 命令之一安装 UE-V Agent。</span><span class="sxs-lookup"><span data-stu-id="426a1-112">Use one of the following Windows PowerShell commands to install the UE-V Agent.</span></span>

    -   `& AgentSetup.exe /quiet /norestart /log "%temp%\UE-VAgentInstaller.log" SettingsStoragePath=\\server\settingsshare\%username%`

    -   `& msiexec.exe /i "<path to msi file>" /quiet /norestart /l*v "%temp%\UE-VAgentInstaller.log" SettingsStoragePath=\\server\settingsshare\%username%`

**<span data-ttu-id="426a1-113">使用 Windows PowerShell 配置 UE-V Agent</span><span class="sxs-lookup"><span data-stu-id="426a1-113">To configure the UE-V Agent by using Windows PowerShell</span></span>**

1. <span data-ttu-id="426a1-114">打开 Windows PowerShell 窗口。</span><span class="sxs-lookup"><span data-stu-id="426a1-114">Open a Windows PowerShell window.</span></span> <span data-ttu-id="426a1-115">若要使用 "*计算机*" 参数管理影响计算机的所有用户的计算机设置，请使用具有管理员权限的帐户打开该窗口。</span><span class="sxs-lookup"><span data-stu-id="426a1-115">To manage computer settings that affect all users of the computer by using the *Computer* parameter, open the window with an account that has administrator rights.</span></span>

2. <span data-ttu-id="426a1-116">使用以下 Windows PowerShell 命令配置代理。</span><span class="sxs-lookup"><span data-stu-id="426a1-116">Use the following Windows PowerShell commands to configure the agent.</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="426a1-117">Windows PowerShell 命令</span><span class="sxs-lookup"><span data-stu-id="426a1-117">Windows PowerShell command</span></span></th>
   <th align="left"><span data-ttu-id="426a1-118">描述</span><span class="sxs-lookup"><span data-stu-id="426a1-118">Description</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><code>Get-UevConfiguration</code></p>
   <p></p></td>
   <td align="left"><p><span data-ttu-id="426a1-119">获取有效的 UE-V Agent 设置。</span><span class="sxs-lookup"><span data-stu-id="426a1-119">Gets the effective UE-V Agent settings.</span></span> <span data-ttu-id="426a1-120">特定于用户的设置优先于计算机设置。</span><span class="sxs-lookup"><span data-stu-id="426a1-120">User-specific settings have precedence over the computer settings.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Get-UevConfiguration - CurrentComputerUser</code></p>
   <p></p></td>
   <td align="left"><p><span data-ttu-id="426a1-121">仅为当前用户获取 UE-V Agent 设置值。</span><span class="sxs-lookup"><span data-stu-id="426a1-121">Gets the UE-V Agent settings values for the current user only.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Get-UevConfiguration -Computer</code></p></td>
   <td align="left"><p><span data-ttu-id="426a1-122">获取计算机上所有用户的 UE-V Agent 配置设置值。</span><span class="sxs-lookup"><span data-stu-id="426a1-122">Gets the UE-V Agent configuration settings values for all users on the computer.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Get-UevConfiguration -Details</code></p></td>
   <td align="left"><p><span data-ttu-id="426a1-123">获取每个配置设置的详细信息。</span><span class="sxs-lookup"><span data-stu-id="426a1-123">Gets the details for each configuration setting.</span></span> <span data-ttu-id="426a1-124">显示设置的配置位置或使用默认值。</span><span class="sxs-lookup"><span data-stu-id="426a1-124">Displays where the setting is configured or if it uses the default value.</span></span> <span data-ttu-id="426a1-125">如果当前设置有效，则显示 ""。</span><span class="sxs-lookup"><span data-stu-id="426a1-125">Is displayed if the current setting is valid.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -Computer –ContactITDescription &lt;IT description&gt;</code></p></td>
   <td align="left"><p><span data-ttu-id="426a1-126">设置 "帮助" 链接的 "公司设置中心" 中显示的文本。</span><span class="sxs-lookup"><span data-stu-id="426a1-126">Sets the text that is displayed in the Company Settings Center for the help link.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration -Computer -ContactITUrl &lt;string&gt;</code></p></td>
   <td align="left"><p><span data-ttu-id="426a1-127">在 "帮助" 链接的 "公司设置中心" 中设置链接的 URL。</span><span class="sxs-lookup"><span data-stu-id="426a1-127">Sets the URL of the link in the Company Settings Center for the help link.</span></span> <span data-ttu-id="426a1-128">任何 URL 协议均可使用。</span><span class="sxs-lookup"><span data-stu-id="426a1-128">Any URL protocol can be used.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -Computer –EnableDontSyncWindows8AppSettings</code></p></td>
   <td align="left"><p><span data-ttu-id="426a1-129">将 UE-V Agent 配置为不同步计算机上所有用户的任何 Windows 应用。</span><span class="sxs-lookup"><span data-stu-id="426a1-129">Configures the UE-V Agent to not synchronize any Windows apps for all users on the computer.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration -CurrentComputerUser – EnableDontSyncWindows8AppSettings</code></p></td>
   <td align="left"><p><span data-ttu-id="426a1-130">将 UE-V Agent 配置为不同步当前计算机用户的任何 Windows 应用。</span><span class="sxs-lookup"><span data-stu-id="426a1-130">Configures the UE-V Agent to not synchronize any Windows apps for the current computer user.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -Computer –EnableFirstUseNotification</code></p></td>
   <td align="left"><p><span data-ttu-id="426a1-131">配置 UE-V Agent，以便在代理首次为计算机上的所有用户运行时显示通知。</span><span class="sxs-lookup"><span data-stu-id="426a1-131">Configures the UE-V Agent to display notification the first time the agent runs for all users on the computer.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration -Computer –DisableFirstUseNotification</code></p></td>
   <td align="left"><p><span data-ttu-id="426a1-132">将 UE-V Agent 配置为在代理为计算机上的所有用户首次运行时不显示通知。</span><span class="sxs-lookup"><span data-stu-id="426a1-132">Configures the UE-V Agent to not display notification the first time that the agent runs for all users on the computer.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -Computer –EnableSettingsImportNotify</code></p></td>
   <td align="left"><p><span data-ttu-id="426a1-133">将 UE-V Agent 配置为在设置同步延迟时通知计算机上的所有用户。</span><span class="sxs-lookup"><span data-stu-id="426a1-133">Configures the UE-V Agent to notify all users on the computer when settings synchronization is delayed.</span></span></p>
   <p><span data-ttu-id="426a1-134">使用 <em> DisableSettingsImportNotify </em> 参数禁用通知。</span><span class="sxs-lookup"><span data-stu-id="426a1-134">Use the <em>DisableSettingsImportNotify</em> parameter to disable notification.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration - CurrentComputerUser -EnableSettingsImportNotify</code></p></td>
   <td align="left"><p><span data-ttu-id="426a1-135">将 UE-V Agent 配置为在设置同步延迟时通知当前用户。</span><span class="sxs-lookup"><span data-stu-id="426a1-135">Configures the UE-V Agent to notify the current user when settings synchronization is delayed.</span></span></p>
   <p><span data-ttu-id="426a1-136">使用 <em> DisableSettingsImportNotify </em> 参数禁用通知。</span><span class="sxs-lookup"><span data-stu-id="426a1-136">Use the <em>DisableSettingsImportNotify</em> parameter to disable notification.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -Computer –EnableSyncUnlistedWindows8Apps</code></p></td>
   <td align="left"><p><span data-ttu-id="426a1-137">配置 UE-V Agent 以同步 Windows 应用列表中未明确禁用的所有 Windows 应用（适用于计算机的所有用户）。</span><span class="sxs-lookup"><span data-stu-id="426a1-137">Configures the UE-V Agent to synchronize all Windows apps that are not explicitly disabled by the Windows app list for all users of the computer.</span></span> <span data-ttu-id="426a1-138">有关详细信息，请参阅 &quot; &quot; <a href="managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md" data-raw-source="[Managing UE-V 2.x Settings Location Templates Using Windows PowerShell and WMI](managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md)"> 使用 WINDOWS PowerShell 和 WMI 管理 Ue-v 2 UevAppxPackage 设置位置模板中的 "获取" </a> 。</span><span class="sxs-lookup"><span data-stu-id="426a1-138">For more information, see &quot;Get-UevAppxPackage&quot; in <a href="managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md" data-raw-source="[Managing UE-V 2.x Settings Location Templates Using Windows PowerShell and WMI](managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md)">Managing UE-V 2.x Settings Location Templates Using Windows PowerShell and WMI</a>.</span></span></p>
   <p><span data-ttu-id="426a1-139">使用 <em> DisableSyncUnlistedWindows8Apps </em> 参数将 ue-v Agent 配置为仅同步 Windows 应用列表显式启用的 windows 应用。</span><span class="sxs-lookup"><span data-stu-id="426a1-139">Use the <em>DisableSyncUnlistedWindows8Apps</em> parameter to configure the UE-V Agent to synchronize only Windows apps that are explicitly enabled by the Windows App List.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration - CurrentComputerUser - EnableSyncUnlistedWindows8Apps</code></p></td>
   <td align="left"><p><span data-ttu-id="426a1-140">将 UE-V Agent 配置为对计算机上当前用户未明确禁用的所有 Windows 应用进行同步。</span><span class="sxs-lookup"><span data-stu-id="426a1-140">Configures the UE-V Agent to synchronize all Windows apps that are not explicitly disabled by the Windows app list for the current user on the computer.</span></span> <span data-ttu-id="426a1-141">有关详细信息，请参阅 &quot; &quot; <a href="managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md" data-raw-source="[Managing UE-V 2.x Settings Location Templates Using Windows PowerShell and WMI](managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md)"> 使用 WINDOWS PowerShell 和 WMI 管理 Ue-v 2 UevAppxPackage 设置位置模板中的 "获取" </a> 。</span><span class="sxs-lookup"><span data-stu-id="426a1-141">For more information, see &quot;Get-UevAppxPackage&quot; in <a href="managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md" data-raw-source="[Managing UE-V 2.x Settings Location Templates Using Windows PowerShell and WMI](managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md)">Managing UE-V 2.x Settings Location Templates Using Windows PowerShell and WMI</a>.</span></span></p>
   <p><span data-ttu-id="426a1-142">使用 <em> DisableSyncUnlistedWindows8Apps </em> 参数将 ue-v Agent 配置为仅同步 Windows 应用列表显式启用的 windows 应用。</span><span class="sxs-lookup"><span data-stu-id="426a1-142">Use the <em>DisableSyncUnlistedWindows8Apps</em> parameter to configure the UE-V Agent to synchronize only Windows apps that are explicitly enabled by the Windows App List.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration –Computer –DisableSync</code></p></td>
   <td align="left"><p><span data-ttu-id="426a1-143">对计算机上的所有用户禁用 UE-V。</span><span class="sxs-lookup"><span data-stu-id="426a1-143">Disables UE-V for all the users on the computer.</span></span></p>
   <p><span data-ttu-id="426a1-144">使用 <em> EnableSync </em> 参数启用或重新启用。</span><span class="sxs-lookup"><span data-stu-id="426a1-144">Use the <em>EnableSync</em> parameter to enable or re-enable.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration –CurrentComputerUser -DisableSync</code></p></td>
   <td align="left"><p><span data-ttu-id="426a1-145">对计算机上的当前用户禁用 UE-V。</span><span class="sxs-lookup"><span data-stu-id="426a1-145">Disables UE-V for the current user on the computer.</span></span></p>
   <p><span data-ttu-id="426a1-146">使用 <em> EnableSync </em> 参数启用或重新启用。</span><span class="sxs-lookup"><span data-stu-id="426a1-146">Use the <em>EnableSync</em> parameter to enable or re-enable.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -Computer –EnableTrayIcon</code></p></td>
   <td align="left"><p><span data-ttu-id="426a1-147">为计算机的所有用户启用通知区域中的 UE-V 图标。</span><span class="sxs-lookup"><span data-stu-id="426a1-147">Enables the UE-V icon in the notification area for all users of the computer.</span></span></p>
   <p><span data-ttu-id="426a1-148">使用 <em> DisableTrayIcon </em> 参数禁用该图标。</span><span class="sxs-lookup"><span data-stu-id="426a1-148">Use the <em>DisableTrayIcon</em> parameter to disable the icon.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration -Computer -MaxPackageSizeInBytes &lt;size in bytes&gt;</code></p></td>
   <td align="left"><p><span data-ttu-id="426a1-149">配置 UE-V agent，以在设置包文件大小达到计算机上所有用户的已定义阈值时进行报告。</span><span class="sxs-lookup"><span data-stu-id="426a1-149">Configures the UE-V agent to report when a settings package file size reaches the defined threshold for all users on the computer.</span></span> <span data-ttu-id="426a1-150">设置阈值包大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="426a1-150">Sets the threshold package size in bytes.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -CurrentComputerUser -MaxPackageSizeInBytes &lt;size in bytes&gt;</code></p></td>
   <td align="left"><p><span data-ttu-id="426a1-151">配置 UE-V agent，以在设置包文件大小达到定义的阈值时进行报告。</span><span class="sxs-lookup"><span data-stu-id="426a1-151">Configures the UE-V agent to report when a settings package file size reaches the defined threshold.</span></span> <span data-ttu-id="426a1-152">设置当前用户的程序包大小警告阈值。</span><span class="sxs-lookup"><span data-stu-id="426a1-152">Sets the package size warning threshold for the current user.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration -Computer -SettingsImportNotifyDelayInSeconds</code></p></td>
   <td align="left"><p><span data-ttu-id="426a1-153">指定在用户通知计算机所有用户之前的时间（以秒为单位）</span><span class="sxs-lookup"><span data-stu-id="426a1-153">Specifies the time in seconds before the user is notified for all users of the computer</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration - CurrentComputerUser -SettingsImportNotifyDelayInSeconds</code></p></td>
   <td align="left"><p><span data-ttu-id="426a1-154">指定发送当前用户通知之前的时间（以秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="426a1-154">Specifies the time in seconds before notification for the current user is sent.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration -Computer -SettingsStoragePath &lt;path to _settings_storage_location&gt;</code></p></td>
   <td align="left"><p><span data-ttu-id="426a1-155">为计算机的所有用户定义一个每台计算机的设置存储位置。</span><span class="sxs-lookup"><span data-stu-id="426a1-155">Defines a per-computer settings storage location for all users of the computer.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -CurrentComputerUser -SettingsStoragePath &lt;path to _settings_storage_location&gt;</code></p></td>
   <td align="left"><p><span data-ttu-id="426a1-156">定义每用户设置存储位置。</span><span class="sxs-lookup"><span data-stu-id="426a1-156">Defines a per-user settings storage location.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration –Computer –SettingsTemplateCatalogPath &lt;path to catalog&gt;</code></p></td>
   <td align="left"><p><span data-ttu-id="426a1-157">为计算机的所有用户设置模板目录路径。</span><span class="sxs-lookup"><span data-stu-id="426a1-157">Sets the settings template catalog path for all users of the computer.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -Computer -SyncMethod &lt;sync method&gt;</code></p></td>
   <td align="left"><p><span data-ttu-id="426a1-158">为计算机的所有用户设置同步方法： SyncProvider 或 "无"。</span><span class="sxs-lookup"><span data-stu-id="426a1-158">Sets the synchronization method for all users of the computer: SyncProvider or None.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration -CurrentComputerUser  -SyncMethod &lt;sync method&gt;</code></p></td>
   <td align="left"><p><span data-ttu-id="426a1-159">设置当前用户的同步方法： SyncProvider 或 "无"。</span><span class="sxs-lookup"><span data-stu-id="426a1-159">Sets the synchronization method for the current user: SyncProvider or None.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -Computer -SyncTimeoutInMilliseconds &lt;timeout in milliseconds&gt;</code></p></td>
   <td align="left"><p><span data-ttu-id="426a1-160">为计算机的所有用户设置同步超时时间（以毫秒为单位）</span><span class="sxs-lookup"><span data-stu-id="426a1-160">Sets the synchronization time-out in milliseconds for all users of the computer</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set- UevConfiguration -CurrentComputerUser -SyncTimeoutInMilliseconds &lt;timeout in milliseconds&gt;</code></p></td>
   <td align="left"><p><span data-ttu-id="426a1-161">为当前用户设置同步超时。</span><span class="sxs-lookup"><span data-stu-id="426a1-161">Set the synchronization time-out for the current user.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Clear-UevConfiguration –Computer -&lt;setting name&gt;</code></p></td>
   <td align="left"><p><span data-ttu-id="426a1-162">为计算机上的所有用户清除指定的设置。</span><span class="sxs-lookup"><span data-stu-id="426a1-162">Clears the specified setting for all users on the computer.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Clear-UevConfiguration –CurrentComputerUser -&lt;setting name&gt;</code></p></td>
   <td align="left"><p><span data-ttu-id="426a1-163">仅为当前用户清除指定的设置。</span><span class="sxs-lookup"><span data-stu-id="426a1-163">Clears the specified setting for the current user only.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Export-UevConfiguration &lt;settings migration file&gt;</code></p></td>
   <td align="left"><p><span data-ttu-id="426a1-164">将 UE-V 计算机配置导出到设置迁移文件。</span><span class="sxs-lookup"><span data-stu-id="426a1-164">Exports the UE-V computer configuration to a settings migration file.</span></span> <span data-ttu-id="426a1-165">文件名扩展名必须为 uev。</span><span class="sxs-lookup"><span data-stu-id="426a1-165">The file name extension must be .uev.</span></span></p>
   <p><span data-ttu-id="426a1-166">该 <code>Export</code> cmdlet 导出可通过计算机参数进行配置的所有 Ue-v Agent 设置 <em> </em> 。</span><span class="sxs-lookup"><span data-stu-id="426a1-166">The <code>Export</code> cmdlet exports all UE-V Agent settings that are configurable with the <em>Computer</em> parameter.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Import-UevConfiguration &lt;settings migration file&gt;</code></p></td>
   <td align="left"><p><span data-ttu-id="426a1-167">从设置迁移文件导入 UE-V 计算机配置。</span><span class="sxs-lookup"><span data-stu-id="426a1-167">Imports the UE-V computer configuration from a settings migration file.</span></span> <span data-ttu-id="426a1-168">文件名扩展名必须为 uev。</span><span class="sxs-lookup"><span data-stu-id="426a1-168">The file name extension must be .uev.</span></span></p></td>
   </tr>
   </tbody>
   </table>



**<span data-ttu-id="426a1-169">导出 UE-V 程序包设置并使用 Windows PowerShell 修复 UE-V 模板</span><span class="sxs-lookup"><span data-stu-id="426a1-169">To export UE-V package settings and repair UE-V templates by using Windows PowerShell</span></span>**

1.  <span data-ttu-id="426a1-170">以管理员身份打开 Windows PowerShell 窗口。</span><span class="sxs-lookup"><span data-stu-id="426a1-170">Open a Windows PowerShell window as an administrator.</span></span>

2.  <span data-ttu-id="426a1-171">使用以下 Windows PowerShell 命令配置代理。</span><span class="sxs-lookup"><span data-stu-id="426a1-171">Use the following Windows PowerShell commands to configure the agent.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><strong><span data-ttu-id="426a1-172">Windows PowerShell 命令</span><span class="sxs-lookup"><span data-stu-id="426a1-172">Windows PowerShell command</span></span></strong></p></td>
    <td align="left"><p><strong><span data-ttu-id="426a1-173">描述</span><span class="sxs-lookup"><span data-stu-id="426a1-173">Description</span></span></strong></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="426a1-174">Export-UevPackage MicrosoftCalculator6 pkgx</span><span class="sxs-lookup"><span data-stu-id="426a1-174">Export-UevPackage MicrosoftCalculator6.pkgx</span></span></p></td>
    <td align="left"><p><span data-ttu-id="426a1-175">从 Microsoft 计算器包文件中提取设置，并将其转换为 XML 格式的可读格式。</span><span class="sxs-lookup"><span data-stu-id="426a1-175">Extracts the settings from a Microsoft Calculator package file and converts them into a human-readable format in XML.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="426a1-176">修复-UevTemplateIndex</span><span class="sxs-lookup"><span data-stu-id="426a1-176">Repair-UevTemplateIndex</span></span></p></td>
    <td align="left"><p><span data-ttu-id="426a1-177">修复 UE-V 设置位置模板的索引。</span><span class="sxs-lookup"><span data-stu-id="426a1-177">Repairs the index of the UE-V settings location templates.</span></span></p></td>
    </tr>
    </tbody>
    </table>



**<span data-ttu-id="426a1-178">使用 WMI 配置 UE-V Agent</span><span class="sxs-lookup"><span data-stu-id="426a1-178">To configure the UE-V Agent by using WMI</span></span>**

1.  <span data-ttu-id="426a1-179">用户体验虚拟化提供以下 WMI 命令集。</span><span class="sxs-lookup"><span data-stu-id="426a1-179">User Experience Virtualization provides the following set of WMI commands.</span></span> <span data-ttu-id="426a1-180">管理员可以使用此接口在命令行配置 UE-V agent 并自动执行典型配置任务。</span><span class="sxs-lookup"><span data-stu-id="426a1-180">Administrators can use this interface to configure the UE-V agent at the command line and automate typical configuration tasks.</span></span>

    <span data-ttu-id="426a1-181">使用具有管理员权限的帐户打开 Windows PowerShell 窗口。</span><span class="sxs-lookup"><span data-stu-id="426a1-181">Use an account with administrator rights to open a Windows PowerShell window.</span></span>

2.  <span data-ttu-id="426a1-182">使用以下 WMI 命令配置代理。</span><span class="sxs-lookup"><span data-stu-id="426a1-182">Use the following WMI commands to configure the agent.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><code>Windows PowerShell command</code></th>
    <th align="left"><span data-ttu-id="426a1-183">描述</span><span class="sxs-lookup"><span data-stu-id="426a1-183">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><code>Get-WmiObject -Namespace root\Microsoft\UEV Configuration</code></p>
    <p></p></td>
    <td align="left"><p><span data-ttu-id="426a1-184">显示活动的 UE-V Agent 设置。</span><span class="sxs-lookup"><span data-stu-id="426a1-184">Displays the active UE-V Agent settings.</span></span> <span data-ttu-id="426a1-185">特定于用户的设置优先于计算机设置。</span><span class="sxs-lookup"><span data-stu-id="426a1-185">User-specific settings have precedence over the computer settings.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Get-WmiObject -Namespace root\Microsoft\UEV UserConfiguration</code></p></td>
    <td align="left"><p><span data-ttu-id="426a1-186">显示为用户定义的 UE-V Agent 配置。</span><span class="sxs-lookup"><span data-stu-id="426a1-186">Displays the UE-V Agent configuration that is defined for a user.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p></td>
    <td align="left"><p><span data-ttu-id="426a1-187">显示为计算机定义的 UE-V Agent 配置。</span><span class="sxs-lookup"><span data-stu-id="426a1-187">Displays the UE-V Agent configuration that is defined for a computer.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Get-WmiObject –Namespace root\Microsoft\Uev ConfigurationItem</code></p></td>
    <td align="left"><p><span data-ttu-id="426a1-188">显示每个配置项目的详细信息。</span><span class="sxs-lookup"><span data-stu-id="426a1-188">Displays the details for each configuration item.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p>
    <p><code>$config.SettingsStoragePath = &lt;path_to_settings_storage_location&gt;</code></p>
    <p><span data-ttu-id="426a1-189">$config。Put （）</span><span class="sxs-lookup"><span data-stu-id="426a1-189">$config.Put()</span></span></p></td>
    <td align="left"><p><span data-ttu-id="426a1-190">定义每台计算机的设置存储位置。</span><span class="sxs-lookup"><span data-stu-id="426a1-190">Defines a per-computer settings storage location.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV UserConfiguration</code></p>
    <p><code>$config.SettingsStoragePath = &lt;path_to_settings_storage_location&gt;</code></p>
    <p><code>$config.Put()</code></p></td>
    <td align="left"><p><span data-ttu-id="426a1-191">定义每用户设置存储位置。</span><span class="sxs-lookup"><span data-stu-id="426a1-191">Defines a per-user settings storage location.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p>
    <p><code>$config.SyncTimeoutInMilliseconds = &lt;timeout_in_milliseconds&gt;</code></p>
    <p><code>$config.Put()</code></p></td>
    <td align="left"><p><span data-ttu-id="426a1-192">为计算机的所有用户设置同步超时时间（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="426a1-192">Sets the synchronization time-out in milliseconds for all users of the computer.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p>
    <p><code>$config.MaxPackageSizeInBytes = &lt;size_in_bytes&gt;</code></p>
    <p><code>$config.Put()</code></p></td>
    <td align="left"><p><span data-ttu-id="426a1-193">配置 UE-V Agent，以在设置包文件大小达到定义的阈值时进行报告。</span><span class="sxs-lookup"><span data-stu-id="426a1-193">Configures the UE-V Agent to report when a settings package file size reaches a defined threshold.</span></span> <span data-ttu-id="426a1-194">为计算机的所有用户设置阈值程序包文件大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="426a1-194">Set the threshold package file size in bytes for all users of the computer.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p>
    <p><code>$config.SyncMethod = &lt;sync_method&gt;</code></p>
    <p><code>$config.Put()</code></p></td>
    <td align="left"><p><span data-ttu-id="426a1-195">为计算机的所有用户设置同步方法： SyncProvider 或 "无"。</span><span class="sxs-lookup"><span data-stu-id="426a1-195">Sets the synchronization method for all users of the computer: SyncProvider or None.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p>
    <p><code>$config.&lt;setting name&gt; = $true</code></p>
    <p><code>$config.Put()</code></p></td>
    <td align="left"><p><span data-ttu-id="426a1-196">若要启用特定的每台计算机设置，请清除该设置，并使用 <em> $null </em> 作为设置值。</span><span class="sxs-lookup"><span data-stu-id="426a1-196">To enable a specific per-computer setting, clear the setting, and use <em>$null</em> as the setting value.</span></span> <span data-ttu-id="426a1-197">对每个用户的设置使用 UserConfiguration。</span><span class="sxs-lookup"><span data-stu-id="426a1-197">Use UserConfiguration for per-user settings.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p>
    <p><code>$config.&lt;setting name&gt; = $false</code></p>
    <p><code>$config.Put()</code></p></td>
    <td align="left"><p><span data-ttu-id="426a1-198">若要禁用特定的每台计算机设置，请清除该设置，并使用 <em> $null </em> 作为设置值。</span><span class="sxs-lookup"><span data-stu-id="426a1-198">To disable a specific per-computer setting, clear the setting, and use <em>$null</em> as the setting value.</span></span> <span data-ttu-id="426a1-199">对每用户设置使用 "用户配置"。</span><span class="sxs-lookup"><span data-stu-id="426a1-199">Use User Configuration for per-user settings.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p>
    <p><code>$config.&lt;setting name&gt; = &lt;setting value&gt;</code></p>
    <p><code>$config.Put()</code></p></td>
    <td align="left"><p><span data-ttu-id="426a1-200">更新特定的每台计算机设置。</span><span class="sxs-lookup"><span data-stu-id="426a1-200">Updates a specific per-computer setting.</span></span> <span data-ttu-id="426a1-201">若要清除该设置，请使用 <em> $null </em> 作为设置值。</span><span class="sxs-lookup"><span data-stu-id="426a1-201">To clear the setting, use <em>$null</em> as the setting value.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p>
    <p><code></code><span data-ttu-id="426a1-202">$config。 &lt;设置名称 &gt;  =  &lt; 设置值&gt;</span><span class="sxs-lookup"><span data-stu-id="426a1-202">$config.&lt;setting name&gt; = &lt;setting value&gt;</span></span></p>
    <p><code>$config.Put()</code></p></td>
    <td align="left"><p><span data-ttu-id="426a1-203">为计算机的所有用户更新特定的每用户设置。</span><span class="sxs-lookup"><span data-stu-id="426a1-203">Updates a specific per-user setting for all users of the computer.</span></span> <span data-ttu-id="426a1-204">若要清除该设置，请使用 <em> $null </em> 作为设置值。</span><span class="sxs-lookup"><span data-stu-id="426a1-204">To clear the setting, use <em>$null</em> as the setting value.</span></span></p></td>
    </tr>
    </tbody>
    </table>



~~~
Upon configuration of the UE-V Agent with WMI and Windows PowerShell, the defined configuration is stored in the registry in the following locations.

`\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\UEV\Agent\Configuration`

`\HKEY_CURRENT_USER\SOFTWARE\Microsoft\UEV\Agent\Configuration`
~~~

**<span data-ttu-id="426a1-205">导出 UE-V 程序包设置并使用 WMI 修复 UE-V 模板</span><span class="sxs-lookup"><span data-stu-id="426a1-205">To export UE-V package settings and repair UE-V templates by using WMI</span></span>**

1.  <span data-ttu-id="426a1-206">UE-V 提供以下 WMI 命令集。</span><span class="sxs-lookup"><span data-stu-id="426a1-206">UE-V provides the following set of WMI commands.</span></span> <span data-ttu-id="426a1-207">管理员可以使用此接口导出程序包或修复 UE-V 模板。</span><span class="sxs-lookup"><span data-stu-id="426a1-207">Administrators can use this interface to export a package or repair UE-V templates.</span></span>

2.  <span data-ttu-id="426a1-208">使用以下 WMI 命令。</span><span class="sxs-lookup"><span data-stu-id="426a1-208">Use the following WMI commands.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="426a1-209">WMI 命令</span><span class="sxs-lookup"><span data-stu-id="426a1-209">WMI command</span></span></th>
    <th align="left"><span data-ttu-id="426a1-210">描述</span><span class="sxs-lookup"><span data-stu-id="426a1-210">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class UserSettings -Name ExportPackage -ArgumentList &lt;package name&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="426a1-211">从程序包文件中提取设置，并将其转换为 XML 格式的可读格式。</span><span class="sxs-lookup"><span data-stu-id="426a1-211">Extracts the settings from a package file and converts them into a human-readable format in XML.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name RebuildIndex</code></p></td>
    <td align="left"><p><span data-ttu-id="426a1-212">修复 UE-V 设置位置模板的索引。</span><span class="sxs-lookup"><span data-stu-id="426a1-212">Repairs the index of the UE-V settings location templates.</span></span> <span data-ttu-id="426a1-213">必须以管理员身份运行。</span><span class="sxs-lookup"><span data-stu-id="426a1-213">Must be run as administrator.</span></span></p></td>
    </tr>
    </tbody>
    </table>



~~~
**Got a suggestion for UE-V**? Add or vote on suggestions [here](http://uev.uservoice.com/forums/280428-microsoft-user-experience-virtualization). **Got a UE-V issue**? Use the [UE-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopuev).
~~~

## <span data-ttu-id="426a1-214">相关主题</span><span class="sxs-lookup"><span data-stu-id="426a1-214">Related topics</span></span>


[<span data-ttu-id="426a1-215">管理具有 Windows PowerShell 和 WMI 的 UE-V 2。</span><span class="sxs-lookup"><span data-stu-id="426a1-215">Administering UE-V 2.x with Windows PowerShell and WMI</span></span>](administering-ue-v-2x-with-windows-powershell-and-wmi-both-uevv2.md)

[<span data-ttu-id="426a1-216">管理 UE-V 2. x</span><span class="sxs-lookup"><span data-stu-id="426a1-216">Administering UE-V 2.x</span></span>](administering-ue-v-2x-new-uevv2.md)









