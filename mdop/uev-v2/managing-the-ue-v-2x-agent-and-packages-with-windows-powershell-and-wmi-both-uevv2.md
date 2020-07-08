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
# 通过 Windows PowerShell 和 WMI 管理 UE-V 2 x 代理和程序包


你可以使用 Windows Management Instrumentation （WMI）和 Windows PowerShell 来管理 Microsoft 用户体验虚拟化（UE-V）2.0、2.1 和 2.1 SP1 代理配置和同步行为。 有关 UE-V PowerShell cmdlet 的完整列表，请参阅[ue-v 2 Cmdlet 参考](https://go.microsoft.com/fwlink/?LinkId=393495)（ https://go.microsoft.com/fwlink/?LinkId=393495) 。

**使用 Windows PowerShell 部署 UE-V Agent**

1.  在易于访问的网络共享中暂存 UE-V 安装程序文件。

    **注意**  
    使用 AgentSetup.exe 部署32位和64位的 UE-V Agent 版本。 Windows Installer 程序包、AgentSetupx86.msi 和 AgentSetupx64.msi 适用于每个体系结构。 若要在以后使用安装文件卸载 UE-V Agent，必须使用相同的文件类型。



2.  使用以下 Windows PowerShell 命令之一安装 UE-V Agent。

    -   `& AgentSetup.exe /quiet /norestart /log "%temp%\UE-VAgentInstaller.log" SettingsStoragePath=\\server\settingsshare\%username%`

    -   `& msiexec.exe /i "<path to msi file>" /quiet /norestart /l*v "%temp%\UE-VAgentInstaller.log" SettingsStoragePath=\\server\settingsshare\%username%`

**使用 Windows PowerShell 配置 UE-V Agent**

1. 打开 Windows PowerShell 窗口。 若要使用 "*计算机*" 参数管理影响计算机的所有用户的计算机设置，请使用具有管理员权限的帐户打开该窗口。

2. 使用以下 Windows PowerShell 命令配置代理。

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">Windows PowerShell 命令</th>
   <th align="left">描述</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><code>Get-UevConfiguration</code></p>
   <p></p></td>
   <td align="left"><p>获取有效的 UE-V Agent 设置。 特定于用户的设置优先于计算机设置。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Get-UevConfiguration - CurrentComputerUser</code></p>
   <p></p></td>
   <td align="left"><p>仅为当前用户获取 UE-V Agent 设置值。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Get-UevConfiguration -Computer</code></p></td>
   <td align="left"><p>获取计算机上所有用户的 UE-V Agent 配置设置值。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Get-UevConfiguration -Details</code></p></td>
   <td align="left"><p>获取每个配置设置的详细信息。 显示设置的配置位置或使用默认值。 如果当前设置有效，则显示 ""。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -Computer –ContactITDescription &lt;IT description&gt;</code></p></td>
   <td align="left"><p>设置 "帮助" 链接的 "公司设置中心" 中显示的文本。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration -Computer -ContactITUrl &lt;string&gt;</code></p></td>
   <td align="left"><p>在 "帮助" 链接的 "公司设置中心" 中设置链接的 URL。 任何 URL 协议均可使用。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -Computer –EnableDontSyncWindows8AppSettings</code></p></td>
   <td align="left"><p>将 UE-V Agent 配置为不同步计算机上所有用户的任何 Windows 应用。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration -CurrentComputerUser – EnableDontSyncWindows8AppSettings</code></p></td>
   <td align="left"><p>将 UE-V Agent 配置为不同步当前计算机用户的任何 Windows 应用。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -Computer –EnableFirstUseNotification</code></p></td>
   <td align="left"><p>配置 UE-V Agent，以便在代理首次为计算机上的所有用户运行时显示通知。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration -Computer –DisableFirstUseNotification</code></p></td>
   <td align="left"><p>将 UE-V Agent 配置为在代理为计算机上的所有用户首次运行时不显示通知。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -Computer –EnableSettingsImportNotify</code></p></td>
   <td align="left"><p>将 UE-V Agent 配置为在设置同步延迟时通知计算机上的所有用户。</p>
   <p>使用 <em> DisableSettingsImportNotify </em> 参数禁用通知。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration - CurrentComputerUser -EnableSettingsImportNotify</code></p></td>
   <td align="left"><p>将 UE-V Agent 配置为在设置同步延迟时通知当前用户。</p>
   <p>使用 <em> DisableSettingsImportNotify </em> 参数禁用通知。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -Computer –EnableSyncUnlistedWindows8Apps</code></p></td>
   <td align="left"><p>配置 UE-V Agent 以同步 Windows 应用列表中未明确禁用的所有 Windows 应用（适用于计算机的所有用户）。 有关详细信息，请参阅 &quot; &quot; <a href="managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md" data-raw-source="[Managing UE-V 2.x Settings Location Templates Using Windows PowerShell and WMI](managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md)"> 使用 WINDOWS PowerShell 和 WMI 管理 Ue-v 2 UevAppxPackage 设置位置模板中的 "获取" </a> 。</p>
   <p>使用 <em> DisableSyncUnlistedWindows8Apps </em> 参数将 ue-v Agent 配置为仅同步 Windows 应用列表显式启用的 windows 应用。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration - CurrentComputerUser - EnableSyncUnlistedWindows8Apps</code></p></td>
   <td align="left"><p>将 UE-V Agent 配置为对计算机上当前用户未明确禁用的所有 Windows 应用进行同步。 有关详细信息，请参阅 &quot; &quot; <a href="managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md" data-raw-source="[Managing UE-V 2.x Settings Location Templates Using Windows PowerShell and WMI](managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md)"> 使用 WINDOWS PowerShell 和 WMI 管理 Ue-v 2 UevAppxPackage 设置位置模板中的 "获取" </a> 。</p>
   <p>使用 <em> DisableSyncUnlistedWindows8Apps </em> 参数将 ue-v Agent 配置为仅同步 Windows 应用列表显式启用的 windows 应用。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration –Computer –DisableSync</code></p></td>
   <td align="left"><p>对计算机上的所有用户禁用 UE-V。</p>
   <p>使用 <em> EnableSync </em> 参数启用或重新启用。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration –CurrentComputerUser -DisableSync</code></p></td>
   <td align="left"><p>对计算机上的当前用户禁用 UE-V。</p>
   <p>使用 <em> EnableSync </em> 参数启用或重新启用。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -Computer –EnableTrayIcon</code></p></td>
   <td align="left"><p>为计算机的所有用户启用通知区域中的 UE-V 图标。</p>
   <p>使用 <em> DisableTrayIcon </em> 参数禁用该图标。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration -Computer -MaxPackageSizeInBytes &lt;size in bytes&gt;</code></p></td>
   <td align="left"><p>配置 UE-V agent，以在设置包文件大小达到计算机上所有用户的已定义阈值时进行报告。 设置阈值包大小（以字节为单位）。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -CurrentComputerUser -MaxPackageSizeInBytes &lt;size in bytes&gt;</code></p></td>
   <td align="left"><p>配置 UE-V agent，以在设置包文件大小达到定义的阈值时进行报告。 设置当前用户的程序包大小警告阈值。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration -Computer -SettingsImportNotifyDelayInSeconds</code></p></td>
   <td align="left"><p>指定在用户通知计算机所有用户之前的时间（以秒为单位）</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration - CurrentComputerUser -SettingsImportNotifyDelayInSeconds</code></p></td>
   <td align="left"><p>指定发送当前用户通知之前的时间（以秒为单位）。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration -Computer -SettingsStoragePath &lt;path to _settings_storage_location&gt;</code></p></td>
   <td align="left"><p>为计算机的所有用户定义一个每台计算机的设置存储位置。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -CurrentComputerUser -SettingsStoragePath &lt;path to _settings_storage_location&gt;</code></p></td>
   <td align="left"><p>定义每用户设置存储位置。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration –Computer –SettingsTemplateCatalogPath &lt;path to catalog&gt;</code></p></td>
   <td align="left"><p>为计算机的所有用户设置模板目录路径。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -Computer -SyncMethod &lt;sync method&gt;</code></p></td>
   <td align="left"><p>为计算机的所有用户设置同步方法： SyncProvider 或 "无"。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration -CurrentComputerUser  -SyncMethod &lt;sync method&gt;</code></p></td>
   <td align="left"><p>设置当前用户的同步方法： SyncProvider 或 "无"。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -Computer -SyncTimeoutInMilliseconds &lt;timeout in milliseconds&gt;</code></p></td>
   <td align="left"><p>为计算机的所有用户设置同步超时时间（以毫秒为单位）</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set- UevConfiguration -CurrentComputerUser -SyncTimeoutInMilliseconds &lt;timeout in milliseconds&gt;</code></p></td>
   <td align="left"><p>为当前用户设置同步超时。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Clear-UevConfiguration –Computer -&lt;setting name&gt;</code></p></td>
   <td align="left"><p>为计算机上的所有用户清除指定的设置。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Clear-UevConfiguration –CurrentComputerUser -&lt;setting name&gt;</code></p></td>
   <td align="left"><p>仅为当前用户清除指定的设置。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Export-UevConfiguration &lt;settings migration file&gt;</code></p></td>
   <td align="left"><p>将 UE-V 计算机配置导出到设置迁移文件。 文件名扩展名必须为 uev。</p>
   <p>该 <code>Export</code> cmdlet 导出可通过计算机参数进行配置的所有 Ue-v Agent 设置 <em> </em> 。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Import-UevConfiguration &lt;settings migration file&gt;</code></p></td>
   <td align="left"><p>从设置迁移文件导入 UE-V 计算机配置。 文件名扩展名必须为 uev。</p></td>
   </tr>
   </tbody>
   </table>



**导出 UE-V 程序包设置并使用 Windows PowerShell 修复 UE-V 模板**

1.  以管理员身份打开 Windows PowerShell 窗口。

2.  使用以下 Windows PowerShell 命令配置代理。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><strong>Windows PowerShell 命令</strong></p></td>
    <td align="left"><p><strong>描述</strong></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Export-UevPackage MicrosoftCalculator6 pkgx</p></td>
    <td align="left"><p>从 Microsoft 计算器包文件中提取设置，并将其转换为 XML 格式的可读格式。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>修复-UevTemplateIndex</p></td>
    <td align="left"><p>修复 UE-V 设置位置模板的索引。</p></td>
    </tr>
    </tbody>
    </table>



**使用 WMI 配置 UE-V Agent**

1.  用户体验虚拟化提供以下 WMI 命令集。 管理员可以使用此接口在命令行配置 UE-V agent 并自动执行典型配置任务。

    使用具有管理员权限的帐户打开 Windows PowerShell 窗口。

2.  使用以下 WMI 命令配置代理。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><code>Windows PowerShell command</code></th>
    <th align="left">描述</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><code>Get-WmiObject -Namespace root\Microsoft\UEV Configuration</code></p>
    <p></p></td>
    <td align="left"><p>显示活动的 UE-V Agent 设置。 特定于用户的设置优先于计算机设置。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Get-WmiObject -Namespace root\Microsoft\UEV UserConfiguration</code></p></td>
    <td align="left"><p>显示为用户定义的 UE-V Agent 配置。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p></td>
    <td align="left"><p>显示为计算机定义的 UE-V Agent 配置。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Get-WmiObject –Namespace root\Microsoft\Uev ConfigurationItem</code></p></td>
    <td align="left"><p>显示每个配置项目的详细信息。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p>
    <p><code>$config.SettingsStoragePath = &lt;path_to_settings_storage_location&gt;</code></p>
    <p>$config。Put （）</p></td>
    <td align="left"><p>定义每台计算机的设置存储位置。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV UserConfiguration</code></p>
    <p><code>$config.SettingsStoragePath = &lt;path_to_settings_storage_location&gt;</code></p>
    <p><code>$config.Put()</code></p></td>
    <td align="left"><p>定义每用户设置存储位置。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p>
    <p><code>$config.SyncTimeoutInMilliseconds = &lt;timeout_in_milliseconds&gt;</code></p>
    <p><code>$config.Put()</code></p></td>
    <td align="left"><p>为计算机的所有用户设置同步超时时间（以毫秒为单位）。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p>
    <p><code>$config.MaxPackageSizeInBytes = &lt;size_in_bytes&gt;</code></p>
    <p><code>$config.Put()</code></p></td>
    <td align="left"><p>配置 UE-V Agent，以在设置包文件大小达到定义的阈值时进行报告。 为计算机的所有用户设置阈值程序包文件大小（以字节为单位）。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p>
    <p><code>$config.SyncMethod = &lt;sync_method&gt;</code></p>
    <p><code>$config.Put()</code></p></td>
    <td align="left"><p>为计算机的所有用户设置同步方法： SyncProvider 或 "无"。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p>
    <p><code>$config.&lt;setting name&gt; = $true</code></p>
    <p><code>$config.Put()</code></p></td>
    <td align="left"><p>若要启用特定的每台计算机设置，请清除该设置，并使用 <em> $null </em> 作为设置值。 对每个用户的设置使用 UserConfiguration。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p>
    <p><code>$config.&lt;setting name&gt; = $false</code></p>
    <p><code>$config.Put()</code></p></td>
    <td align="left"><p>若要禁用特定的每台计算机设置，请清除该设置，并使用 <em> $null </em> 作为设置值。 对每用户设置使用 "用户配置"。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p>
    <p><code>$config.&lt;setting name&gt; = &lt;setting value&gt;</code></p>
    <p><code>$config.Put()</code></p></td>
    <td align="left"><p>更新特定的每台计算机设置。 若要清除该设置，请使用 <em> $null </em> 作为设置值。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p>
    <p><code></code>$config。 &lt;设置名称 &gt;  =  &lt; 设置值&gt;</p>
    <p><code>$config.Put()</code></p></td>
    <td align="left"><p>为计算机的所有用户更新特定的每用户设置。 若要清除该设置，请使用 <em> $null </em> 作为设置值。</p></td>
    </tr>
    </tbody>
    </table>



~~~
Upon configuration of the UE-V Agent with WMI and Windows PowerShell, the defined configuration is stored in the registry in the following locations.

`\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\UEV\Agent\Configuration`

`\HKEY_CURRENT_USER\SOFTWARE\Microsoft\UEV\Agent\Configuration`
~~~

**导出 UE-V 程序包设置并使用 WMI 修复 UE-V 模板**

1.  UE-V 提供以下 WMI 命令集。 管理员可以使用此接口导出程序包或修复 UE-V 模板。

2.  使用以下 WMI 命令。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">WMI 命令</th>
    <th align="left">描述</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class UserSettings -Name ExportPackage -ArgumentList &lt;package name&gt;</code></p></td>
    <td align="left"><p>从程序包文件中提取设置，并将其转换为 XML 格式的可读格式。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name RebuildIndex</code></p></td>
    <td align="left"><p>修复 UE-V 设置位置模板的索引。 必须以管理员身份运行。</p></td>
    </tr>
    </tbody>
    </table>



~~~
**Got a suggestion for UE-V**? Add or vote on suggestions [here](http://uev.uservoice.com/forums/280428-microsoft-user-experience-virtualization). **Got a UE-V issue**? Use the [UE-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopuev).
~~~

## 相关主题


[管理具有 Windows PowerShell 和 WMI 的 UE-V 2。](administering-ue-v-2x-with-windows-powershell-and-wmi-both-uevv2.md)

[管理 UE-V 2. x](administering-ue-v-2x-new-uevv2.md)









