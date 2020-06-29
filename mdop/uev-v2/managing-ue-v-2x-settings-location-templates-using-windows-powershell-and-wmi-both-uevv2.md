---
title: 使用 Windows PowerShell 和 WMI 管理 UE-V 2. x 设置位置模板
description: 使用 Windows PowerShell 和 WMI 管理 UE-V 2. x 设置位置模板
author: dansimp
ms.assetid: b5253050-acc3-4274-90d0-1fa4c480331d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9788ff1a11f1c70e52b75dd2187a198f5472f77f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798156"
---
# 使用 Windows PowerShell 和 WMI 管理 UE-V 2. x 设置位置模板


Microsoft 用户体验虚拟化（UE-V）2.0、2.1 和 2.1 SP1 使用 XML 设置位置模板来定义用户体验虚拟化捕获和应用的设置。 UE-V 包含一组标准设置位置模板。 它还包括支持创建自定义设置位置模板的 UE-V 生成器工具。 创建和部署设置位置模板后，可以使用 Windows PowerShell 和 Windows Management Instrumentation （WMI）管理这些模板。 有关 UE-V PowerShell cmdlet 的完整列表，请参阅[ue-v 2 Cmdlet 参考](https://go.microsoft.com/fwlink/p/?LinkId=393495)（ https://go.microsoft.com/fwlink/p/?LinkId=393495) 。

## 使用 Windows PowerShell 管理 UE-V 2 设置位置模板


UE-V 的 WMI 和 Windows PowerShell 功能包括启用、禁用、注册、更新和注销设置位置模板的功能。 通过使用这些功能，你可以使用 UE-V Agent 自动执行注册、更新或注销模板的过程。 你还可以使用 WMI 和 Windows PowerShell 命令手动注册模板。 通过将这些功能与电子软件分发解决方案、组策略或其他自动部署方法（如脚本）结合使用，你可以进一步自动化该过程。

必须具有管理员权限才能更新、注册或注销设置位置模板。 启用、禁用或列出模板不需要管理员权限。

***<em>使用 Windows PowerShell 管理设置位置模板ell</em>***

1.  使用具有管理员权限的帐户打开 Windows PowerShell 命令提示符。

2.  使用以下 Windows PowerShell cmdlet 注册和管理 UE-V 设置位置模板。

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
    <td align="left"><p><code>Get-UevTemplate</code></p></td>
    <td align="left"><p>列出计算机上注册的所有设置位置模板。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Get-UevTemplate –Application &lt;string&gt;</code></p></td>
    <td align="left"><p>列出计算机上注册的所有设置位置模板，应用程序名称或模板名称包含 &lt; 字符串 &gt; 。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Get-UevTemplate –TemplateID &lt;string&gt;</code></p></td>
    <td align="left"><p>列出计算机上注册的所有设置位置模板，这些模板 ID 包含 &lt; 字符串 &gt; 。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Get-UevTemplate [-ApplicationOrTemplateID] &lt;string&gt;</code></p></td>
    <td align="left"><p>列出计算机上注册的所有设置位置模板（应用程序或模板名称或模板 ID 包含 &lt; 字符串） &gt; 。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Get-UevTemplateProgram [-ID] &lt;template ID&gt;</code></p></td>
    <td align="left"><p>获取程序和版本信息的名称，这些信息取决于模板 ID。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Get-UevAppXPackage</code></p></td>
    <td align="left"><p>获取 Windows 应用的有效列表。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Get-UevAppXPackage -Computer</code></p></td>
    <td align="left"><p>获取为计算机配置的 Windows 应用的列表。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Get-UevAppXPackage -CurrentComputerUser</code></p></td>
    <td align="left"><p>获取为当前用户配置的 Windows 应用的列表。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Register-UevTemplate [-Path] &lt;template file path&gt;[,&lt;template file path&gt;]</code></p></td>
    <td align="left"><p>通过使用相对路径和/或文件路径中的通配符，使用 UE-V 注册一个或多个设置位置模板。 注册模板后，UE-V 将在已注册模板的计算机之间的模板中定义的设置进行同步。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Register-UevTemplate –LiteralPath &lt;template file path&gt;[,&lt;template file path&gt;]</code></p></td>
    <td align="left"><p>使用文本路径将一个或多个设置位置模板注册到 UE-V，其中任何字符都不能解释为通配符。 注册模板后，UE-V 将在已注册模板的计算机之间的模板中定义的设置进行同步。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Unregister-UevTemplate [-ID] &lt;template ID&gt;</code></p></td>
    <td align="left"><p>使用 UE-V 注销设置位置模板。 当模板未注册时，UE-V 不再同步在计算机之间的模板中定义的设置。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Unregister-UevTemplate -All</code></p></td>
    <td align="left"><p>通过 UE-V 注销所有设置位置模板。 当模板未注册时，UE-V 不再同步在计算机之间的模板中定义的设置。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Update-UevTemplate [-Path] &lt;template file path&gt;[,&lt;template file path&gt;]</code></p></td>
    <td align="left"><p>使用较新版本的模板更新一个或多个设置位置模板。 在文件路径中使用相对路径和/或通配符。 新模板的版本应比现有模板的版本更新。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Update-UevTemplate –LiteralPath &lt;template file path&gt;[,&lt;template file path&gt;]</code></p></td>
    <td align="left"><p>使用较新版本的模板更新一个或多个设置位置模板。 使用指向模板文件的完整路径，其中任何字符均不能解释为通配符。 新模板的版本应比现有模板的版本更新。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Clear-UevAppXPackage –Computer [-PackageFamilyName] &lt;package family name&gt;[,&lt;package family name&gt;]</code></p></td>
    <td align="left"><p>从计算机 Windows 应用列表中删除一个或多个 Windows 应用。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Clear-UevAppXPackage -CurrentComputerUser</code></p></td>
    <td align="left"><p>从当前用户的 Windows 应用列表中删除 Windows 应用。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Clear-UevAppXPackage –Computer -All</code></p></td>
    <td align="left"><p>从计算机的 Windows 应用列表中删除所有 Windows 应用。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Clear-UevAppXPackage [–CurrentComputerUser] [-PackageFamilyName] &lt;package family name&gt;[,&lt;package family name&gt;]</code></p></td>
    <td align="left"><p>从当前用户的 Windows 应用列表中删除一个或多个 Windows 应用。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Clear-UevAppXPackage [–CurrentComputerUser] -All</code></p></td>
    <td align="left"><p>从当前用户的 Windows 应用列表中删除所有 Windows 应用。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Disable-UevTemplate [-ID] &lt;template ID&gt;</code></p></td>
    <td align="left"><p>对计算机的当前用户禁用设置位置模板。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Disable-UevAppXPackage –Computer [-PackageFamilyName] &lt;package family name&gt;[,&lt;package family name&gt;]</code></p></td>
    <td align="left"><p>在计算机 Windows 应用列表中禁用一个或多个 Windows 应用。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Disable-UevAppXPackage [–CurrentComputerUser] [-PackageFamilyName] &lt;package family name&gt;[,&lt;package family name&gt;]</code></p></td>
    <td align="left"><p>在当前用户的 Windows 应用列表中禁用一个或多个 Windows 应用。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Enable-UevTemplate [-ID] &lt;template ID&gt;</code></p></td>
    <td align="left"><p>为计算机的当前用户启用设置位置模板。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Enable-UevAppXPackage –Computer [-PackageFamilyName] &lt;package family name&gt;[,&lt;package family name&gt;]</code></p></td>
    <td align="left"><p>在计算机 Windows 应用列表中启用一个或多个 Windows 应用。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Enable-UevAppXPackage [–CurrentComputerUser] [-PackageFamilyName] &lt;package family name&gt;[,&lt;package family name&gt;]</code></p></td>
    <td align="left"><p>在当前用户的 Windows 应用列表中启用一个或多个 Windows 应用。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Test-UevTemplate [-Path] &lt;template file path&gt;[,&lt;template file path&gt;]</code></p></td>
    <td align="left"><p>确定一个或多个设置位置模板是否符合其 XML 架构。 可以使用相对路径和通配符。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Test-UevTemplate –LiteralPath &lt;template file path&gt;[,&lt;template file path&gt;]</code></p></td>
    <td align="left"><p>确定一个或多个设置位置模板是否符合其 XML 架构。 路径必须是模板文件的完整路径，但不包含通配符字符。</p></td>
    </tr>
    </tbody>
    </table>



借助 UE-V Windows PowerShell 功能，你可以管理企业中部署的一组设置模板。 使用以下过程，使用 Windows PowerShell 管理一组模板。

**使用 Windows PowerShell 管理一组设置位置模板**

1.  修改或更新所需的设置位置模板。

2.  如果要修改或更新设置位置模板，请将这些设置位置模板部署到本地计算机可以访问的文件夹。

3.  在本地计算机上，打开具有管理员权限的 Windows PowerShell 窗口。

4.  通过键入以下命令注销以前注册的所有版本的模板。

    ``` syntax
    Unregister-UevTemplate -All
    ```

    此命令将注销计算机上的所有活动模板。

5.  通过键入以下命令注册已更新的模板。

    ``` syntax
    Register-UevTemplate <path to template folder>\*.xml
    ```

    此命令将注册位于指定模板文件夹中的所有设置位置模板。

### <a href="" id="win8applist"></a>Windows 应用列表

通过在 Windows 应用列表中列出 Windows 应用，可以指定是启用还是禁用该应用以进行设置同步。 应用程序在列表中通过其程序包系列名称进行标识，以及是否应为该应用启用或禁用设置同步。 将这些设置与未列出的默认同步行为设置一起使用时，你可以控制是否同步 Windows 应用。

若要显示已安装的 Windows 应用的程序包系列名称，请在 Windows PowerShell 命令提示符处输入：

``` syntax
Get-AppxPackage | Sort-Object PackageFamilyName | Format-Table PackageFamilyName
```

若要在 Windows PowerShell 命令提示符下显示可将计算机上的设置与计算机的程序包系列名称、启用状态和已启用源同步的 Windows 应用的列表，请输入： `Get-UevAppxPackage`

**UevAppxPackage 属性的定义**

<a href="" id="displayname"></a>**DisplayName**  
在公司设置中心应用程序中向用户显示的名称。 该 `DisplayName` 属性派生自 `PackageFamilyName` 属性。

<a href="" id="packagefamilyname"></a>**PackageFamilyName**  
为当前用户安装的程序包的名称。

<a href="" id="enabled"></a>**启用**  
定义是否将应用的设置配置为同步。

<a href="" id="enabledsource"></a>**EnabledSource**  
设置启用或禁用应用的配置所在的位置。 可能的值包括： *NotSet*、 *LocalMachine*、 *LocalUser*、 *PolicyMachine*和*PolicyUser*。

<a href="" id="notset"></a>**NotSet**  
策略未配置为同步此应用。

<a href="" id="localmachine"></a>**Store**  
启用状态在注册表的 "本地计算机" 部分中设置。

<a href="" id="localuser"></a>**LocalUser**  
启用状态在注册表的 "当前用户" 部分中设置。

<a href="" id="policymachine"></a>**PolicyMachine**  
启用状态在注册表的 "本地计算机" 部分的 "策略" 部分中设置。

若要获取用户配置的 Windows 应用列表，请在 Windows PowerShell 命令提示符处输入： `Get-UevAppxPackage –CurrentComputerUser`

若要获取计算机配置的 Windows 应用列表，请在 Windows PowerShell 命令提示符处输入： `Get-UevAppxPackage –Computer`

对于参数、CurrentComputerUser 或计算机，cmdlet 返回在用户或计算机级别配置的 Windows 应用的列表。

**属性的定义**

<a href="" id="displayname"></a>**DisplayName**  
在公司设置中心应用程序中向用户显示的名称。 该 `DisplayName` 属性派生自 `PackageFamilyName` 属性。

<a href="" id="packagefamilyname"></a>**PackageFamilyName**  
为当前用户安装的程序包的名称。

<a href="" id="enabled"></a>**启用**  
定义是否将应用的设置配置为针对指定的交换机（即**用户**或**计算机**）进行同步。

<a href="" id="installed"></a>**已安装**  
如果应用（即为当前用户安装了 PackageFamilyName）为 True，则为 True。

### 使用 WMI 管理 UE-V 2 设置位置模板

用户体验虚拟化提供以下 WMI 命令集。 管理员可以使用这些接口从 Windows PowerShell 中管理设置位置模板，并自动执行模板管理任务。

**使用 WMI 管理设置位置模板**

1.  使用具有管理员权限的帐户打开 Windows PowerShell 窗口。

2.  使用以下 WMI 命令注册和管理 UE-V 设置位置模板。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><code>                         Windows PowerShell command</code></th>
    <th align="left">描述</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><code>Get-WmiObject -Namespace root\Microsoft\UEV SettingsLocationTemplate | Select-Object TemplateId,TemplateName, TemplateVersion,Enabled | Format-Table -Autosize</code></p></td>
    <td align="left"><p>列出为计算机注册的所有设置位置模板。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Invoke-WmiMethod –Namespace root\Microsoft\UEV –Class SettingsLocationTemplate –Name GetProcessInfoByTemplateId &lt;template Id&gt;</code></p></td>
    <td align="left"><p>获取程序和版本信息的名称，该名称取决于模板名称。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Get-WmiObject -Namespace root\Microsoft\UEV EffectiveWindows8App</code></p></td>
    <td align="left"><p>获取 Windows 应用的有效列表。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>WmiObject-命名空间 root\Microsoft\UEV MachineConfiguredWindows8App</p></td>
    <td align="left"><p>获取为计算机配置的 Windows 应用的列表。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Get-WmiObject -Namespace root\Microsoft\UEV UserConfiguredWindows8App</code></p></td>
    <td align="left"><p>获取为当前用户配置的 Windows 应用的列表。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name Register -ArgumentList &lt;template path &gt;</code></p></td>
    <td align="left"><p>使用 UE-V 注册设置位置模板。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name UnregisterByTemplateId -ArgumentList &lt;template ID&gt;</code></p></td>
    <td align="left"><p>使用 UE-V 注销设置位置模板。 模板注销后，UE-V 不再同步在计算机之间的模板中定义的设置。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name Update -ArgumentList &lt;template path&gt;</code></p></td>
    <td align="left"><p>使用 UE-V 更新设置位置模板。 新模板的版本应比现有模板新。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class MachineConfiguredWindows8App -Name RemoveApp -ArgumentList &lt;package family name | package family name&gt;</code></p></td>
    <td align="left"><p>从计算机 Windows 应用列表中删除一个或多个 Windows 应用。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class UserConfiguredWindows8App -Name RemoveApp -ArgumentList &lt;package family name | package family name&gt;</code></p></td>
    <td align="left"><p>从当前用户的 Windows 应用列表中删除一个或多个 Windows 应用。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name DisableByTemplateId -ArgumentList &lt;template ID&gt;</code></p></td>
    <td align="left"><p>通过 UE-V 禁用一个或多个设置位置模板。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class MachineConfiguredWindows8App -Name DisableApp -ArgumentList &lt;package family name | package family name&gt;</code></p></td>
    <td align="left"><p>在计算机 Windows 应用列表中禁用一个或多个 Windows 应用。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class UserConfiguredWindows8App -Name DisableApp -ArgumentList &lt;package family name | package family name&gt;</code></p></td>
    <td align="left"><p>在当前用户的 Windows 应用列表中禁用一个或多个 Windows 应用。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name EnableByTemplateId -ArgumentList &lt;template ID&gt;</code></p></td>
    <td align="left"><p>使用 UE-V 启用设置位置模板。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class MachineConfiguredWindows8App -Name EnableApp -ArgumentList &lt;package family name | package family name&gt;</code></p></td>
    <td align="left"><p>在计算机 Windows 应用列表中启用 Windows 应用。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class UserConfiguredWindows8App -Name EnableApp -ArgumentList &lt;package family name | package family name&gt;</code></p></td>
    <td align="left"><p>在当前用户的 Windows 应用列表中启用 Windows 应用。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name Validate -ArgumentList &lt;template path&gt;</code></p></td>
    <td align="left"><p>确定给定设置位置模板是否符合其 XML 架构。</p></td>
    </tr>
    </tbody>
    </table>



~~~
**Note**  
Where a list of Package Family Names is called by the WMI command, the list must be in quotes and separated by a pipe symbol, for example, `"<package family name | package family name>"`.
~~~



### 使用 Windows PowerShell 部署 UE-V Agent

**如何使用 Windows PowerShell 部署 UE-V Agent**

1.  在易于访问的网络共享中暂存 UE-V Agent 安装包。

    **注意**  
    使用 AgentSetup.exe 部署32位和64位的 UE-V Agent 版本。 Windows Installer 程序包（AgentSetupx86.msi 和 AgentSetupx64.msi）可用于每个体系结构。 若要在以后使用安装文件卸载 UE-V Agent，必须使用相同的文件类型。



2.  使用以下 Windows PowerShell 命令之一安装 UE-V Agent。

    -   `& AgentSetup.exe /quiet /norestart /log "%temp%\UE-VAgentInstaller.log" SettingsStoragePath=\\server\settingsshare\%username%`

    -   `& msiexec.exe /i "<path to msi file>" /quiet /norestart /l*v "%temp%\UE-VAgentInstaller.log" SettingsStoragePath=\\server\settingsshare\%username%`

已**获得有关 ue-v 的建议**？ 在[此处](http://uev.uservoice.com/forums/280428-microsoft-user-experience-virtualization)添加或投票建议。 是否**遇到了 ue-v 问题**？ 使用[Ue-v TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopuev)。

## 相关主题


[管理具有 Windows PowerShell 和 WMI 的 UE-V 2。](administering-ue-v-2x-with-windows-powershell-and-wmi-both-uevv2.md)

[管理 UE-V 2. x](administering-ue-v-2x-new-uevv2.md)









