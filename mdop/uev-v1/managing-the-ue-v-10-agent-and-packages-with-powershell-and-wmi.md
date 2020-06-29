---
title: 使用 PowerShell 和 WMI 管理 UE-V 1.0 代理和程序包
description: 使用 PowerShell 和 WMI 管理 UE-V 1.0 代理和程序包
author: dansimp
ms.assetid: c8989b01-1769-4e69-82b1-4aadb261d2d5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 79268e3384aaaf08bdd4e9b92d74b039ce96596a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802160"
---
# 使用 PowerShell 和 WMI 管理 UE-V 1.0 代理和程序包


你可以使用 WMI 和 PowerShell 来管理 Microsoft 用户体验虚拟化（UE-V） Agent 配置和同步行为。

**如何通过 PowerShell 部署 UE-V agent**

1.  在易于访问的网络共享中暂存 UE-V 安装程序文件。

    **注意**  
    使用 AgentSetup.exe 部署32位和64位的 UE-V Agent 版本。 Windows Installer 文件版本、AgentSetupx86.msi 和 AgentSetupx64.msi 适用于每个体系结构。 若要在以后使用安装文件卸载 UE-V Agent，必须使用相同的文件类型。



2.  使用以下 PowerShell 命令之一安装代理。

    `& AgentSetup.exe /quiet /norestart /log "%temp%\UE-VAgentInstaller.log" SettingsStoragePath=\\server\settingsshare\%username%`

    `& msiexec.exe /i "<path to msi file>" /quiet /norestart /l*v "%temp%\UE-VAgentInstaller.log" SettingsStoragePath=\\server\settingsshare\%username%`

**如何通过 PowerShell 配置 UE-V Agent**

1.  使用具有管理员权限的帐户打开 PowerShell 窗口。 使用以下命令导入 UE-V PowerShell 模块。

    ``` syntax
    Import-module UEV
    ```

2.  使用以下 PowerShell 命令配置代理。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><strong>PowerShell 命令</strong></p></td>
    <td align="left"><p><strong>描述</strong></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>UevConfiguration</p>
    <p></p></td>
    <td align="left"><p>查看有效的 UE-V agent 设置。 特定于用户的设置优先于计算机设置。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>UevConfiguration-CurrentComputerUser</p>
    <p></p></td>
    <td align="left"><p>仅查看当前用户的 UE-V agent 设置值。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>UevConfiguration-计算机</p></td>
    <td align="left"><p>查看计算机上所有用户的 UE-V agent 配置设置值。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>UevConfiguration-计算机-SettingsStoragePath &lt; 到 _settings_storage_location 的路径&gt;</p></td>
    <td align="left"><p>定义每台计算机的设置存储位置。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>UevConfiguration-CurrentComputerUser-SettingsStoragePath _settings_storage_location 的 &lt; 路径&gt;</p></td>
    <td align="left"><p>定义每用户设置存储位置。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>设置-UevConfiguration-计算机-SyncTimeoutInMilliseconds &lt; 超时（毫秒）&gt;</p></td>
    <td align="left"><p>设置同步超时（以毫秒为单位）</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>UevConfiguration-CurrentComputerUser-SyncTimeoutInMilliseconds &lt; 超时（以毫秒为单位）&gt;</p></td>
    <td align="left"><p>为当前用户设置同步超时。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>UevConfiguration-计算机-MaxPackageSizeInBytes &lt; 大小（以字节为单位）&gt;</p></td>
    <td align="left"><p>配置 UE-V agent，以在设置包文件大小达到定义的阈值时进行报告。 设置阈值包大小（以字节为单位）。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>UevConfiguration-CurrentComputerUser-MaxPackageSizeInBytes 的 &lt; 字节大小&gt;</p></td>
    <td align="left"><p>为当前用户设置程序包大小警告阈值。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>UevConfiguration-计算机-SettingsTemplateCatalogPath &lt; 目录的路径&gt;</p></td>
    <td align="left"><p>设置 "设置" 模板的目录路径。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>UevConfiguration-Powerschool &lt; 同步方法&gt;</p></td>
    <td align="left"><p>设置同步方法： OfflineFiles 或 "无"。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>UevConfiguration-CurrentComputerUser-Powerschool &lt; sync 方法&gt;</p></td>
    <td align="left"><p>为当前用户设置同步方法： OfflineFiles 或 "无"。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>UEVConfiguration-计算机-EnableSettingsImportNotify</p></td>
    <td align="left"><p>启用用户设置导入延迟时出现的通知。</p>
    <p>使用– DisableSettingsImportNotify 禁用通知。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>Set-UEVConfiguration-CurrentComputerUser-EnableSettingsImportNotify</p></td>
    <td align="left"><p>当延迟导入用户设置时，对当前用户启用通知。</p>
    <p>使用– DisableSettingsImportNotify 禁用通知。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Set-UEVConfiguration-计算机-SettingsImportNotifyDelayInSeconds</p></td>
    <td align="left"><p>指定通知用户前的时间（以秒为单位）</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>Set-UEVConfiguration-CurrentComputerUser-SettingsImportNotifyDelayInSeconds</p></td>
    <td align="left"><p>指定在通知当前用户之前的时间（以秒为单位）。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>UevConfiguration-计算机-DisableSync</p></td>
    <td align="left"><p>对计算机上的所有用户禁用 UE-V。</p>
    <p>使用– EnableSync 启用或重新启用。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>Set-UevConfiguration-CurrentComputerUser-DisableSync</p></td>
    <td align="left"><p>对计算机上的当前用户禁用 UE-V。</p>
    <p>使用– EnableSync 启用或重新启用。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Clear-UevConfiguration-计算机 &lt; 设置名称&gt;</p></td>
    <td align="left"><p>为计算机上的所有用户清除特定设置。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>UevConfiguration-CurrentComputerUser- &lt; 设置名称&gt;</p></td>
    <td align="left"><p>为当前用户清除特定设置。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Export-UevConfiguration &lt; 设置迁移文件&gt;</p></td>
    <td align="left"><p>将 UE-V 计算机配置导出到设置迁移文件。 文件的扩展名必须是 ". uev"。</p>
    <p>导出 cmdlet 导出可通过-计算机参数进行配置的所有 UE-V agent 设置。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>Import-UevConfiguration &lt; 设置迁移文件&gt;</p></td>
    <td align="left"><p>从设置迁移文件（uev 文件）导入 UE-V 计算机配置。</p></td>
    </tr>
    </tbody>
    </table>



**如何导出 UE-V 程序包设置并通过 PowerShell 修复 UE-V 模板**

1.  以管理员身份打开 PowerShell 窗口。 通过以下命令导入 UE-V PowerShell 模块。

    ``` syntax
    Import-module UEV
    ```

2.  使用以下 PowerShell 命令配置代理。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><strong>PowerShell 命令</strong></p></td>
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



**如何将 UE-V Agent 配置为 WMI**

1.  用户体验虚拟化提供以下 WMI 命令集。 管理员可以使用此接口从命令行配置 UE-V agent 并自动执行典型配置任务。

    使用具有管理员权限的帐户打开 PowerShell 窗口。

2.  使用以下 WMI 命令配置代理。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">PowerShell 命令</th>
    <th align="left">描述</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>WmiObject-命名空间 root\Microsoft\UEV 配置</p>
    <p></p></td>
    <td align="left"><p>查看活动的 UE-V agent 设置。 特定于用户的设置优先于计算机设置。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>WmiObject-命名空间 root\Microsoft\UEV UserConfiguration</p></td>
    <td align="left"><p>查看为用户定义的 UE-V agent 配置。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>WmiObject-命名空间 root\Microsoft\UEV ComputerConfiguration</p></td>
    <td align="left"><p>查看为计算机定义的 UE-V agent 配置。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>$config = WmiObject-命名空间 root\Microsoft\UEV ComputerConfiguration</p>
    <p>$config。SettingsStoragePath = &lt; path_to_settings_storage_location&gt;</p>
    <p>$config。Put （）</p></td>
    <td align="left"><p>定义每台计算机的设置存储位置。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>$config = WmiObject-命名空间 root\Microsoft\UEV UserConfiguration</p>
    <p>$config。SettingsStoragePath = &lt; path_to_settings_storage_location&gt;</p>
    <p>$config。Put （）</p></td>
    <td align="left"><p>定义每用户设置存储位置。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>$config = WmiObject-命名空间 root\Microsoft\UEV ComputerConfiguration</p>
    <p>$config。SyncTimeoutInMilliseconds = &lt; timeout_in_milliseconds&gt;</p>
    <p>$config。Put （）</p></td>
    <td align="left"><p>设置同步超时（以毫秒为单位）。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>$config = WmiObject-命名空间 root\Microsoft\UEV ComputerConfiguration</p>
    <p>$config。MaxPackageSizeInBytes = &lt; size_in_bytes&gt;</p>
    <p>$config。Put （）</p></td>
    <td align="left"><p>配置 UE-V agent，以在设置包文件大小达到定义的阈值时进行报告。 设置阈值程序包文件大小（以字节为单位）。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>$config = WmiObject-命名空间 root\Microsoft\UEV ComputerConfiguration</p>
    <p>$config。Powerschool = &lt; sync_method&gt;</p>
    <p>$config。Put （）</p></td>
    <td align="left"><p>设置同步方法： OfflineFiles 或 "无"。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>$config = WmiObject-命名空间 root\Microsoft\UEV ComputerConfiguration</p>
    <p>$config。 &lt;设置名称 &gt;  =  &lt; 设置值&gt;</p>
    <p>$config。Put （）</p></td>
    <td align="left"><p>更新特定于每台计算机的设置。 若要清除该设置，请使用 $null 作为设置值。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>$config = WmiObject-命名空间 root\Microsoft\UEV ComputerConfiguration</p>
    <p>$config。 &lt;设置名称 &gt;  =  &lt; 设置值&gt;</p>
    <p>$config。Put （）</p></td>
    <td align="left"><p>更新特定的每用户设置。 若要清除该设置，请使用 $null 作为设置值。</p></td>
    </tr>
    </tbody>
    </table>



~~~
Upon configuration of the UE-V Agent with WMI and PowerShell, the defined configuration is stored in the registry in the following locations:

`\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\UEV\Agent\Configuration`

`\HKEY_CURRENT_USER\SOFTWARE\Microsoft\UEV\Agent\Configuration`
~~~

## 相关主题


[管理 UE-V 1.0](administering-ue-v-10.md)

[UE-V 1.0 的操作](operations-for-ue-v-10.md)









