---
title: 使用 PowerShell 和 WMI 管理 UE-V 1.0 设置位置模板
description: 使用 PowerShell 和 WMI 管理 UE-V 1.0 设置位置模板
author: dansimp
ms.assetid: 4b911c78-a5e9-4199-bfeb-72ab764d47c1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d8dab0997cdfaf7c96862fcce4bc012c3edfe0c0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798059"
---
# 使用 PowerShell 和 WMI 管理 UE-V 1.0 设置位置模板


Microsoft 用户体验虚拟化（UE-V）使用设置位置模板（XML 文件），这些模板定义用户体验虚拟化捕获和应用的设置。 UE-V 包含一组标准设置位置模板。 它还包括支持创建自定义设置位置模板的 UE-V 生成器工具。 创建和部署设置位置模板后，您可以使用 PowerShell 或 WMI 管理这些模板。

## 通过 WMI 和 PowerShell 管理设置位置模板


UE-V 的 WMI 和 PowerShell 功能包括启用、禁用、注册、更新和注销设置位置模板的功能。 通过使用这些功能，你可以使用 UE-V agent 自动执行注册、更新或注销模板的过程。 你还可以使用 WMI 和 PowerShell 命令手动注册模板。 通过将这些功能与电子软件分发解决方案、组策略或其他自动部署方法（如脚本）结合使用，你可以进一步自动化该过程。

必须具有管理员权限才能更新、注册或注销设置位置模板。 启用或禁用模板不需要管理员权限。

**通过 PowerShell 管理设置位置模板**

1.  使用具有管理员权限的帐户打开 Windows PowerShell 窗口。 若要导入**MICROSOFT Ue-v PowerShell**模块，请在 PowerShell 命令提示符处键入以下命令。

    ``` syntax
    Import-module UEV
    ```

2.  使用以下 PowerShell cmdlet 注册和管理 UE-V 设置位置模板。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong>PowerShell 命令</strong></th>
    <th align="left"><strong>描述</strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>UevTemplate</p></td>
    <td align="left"><p>列出计算机上注册的所有设置位置模板。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>注册-UevTemplate</p></td>
    <td align="left"><p>使用 UE-V 注册设置位置模板。 注册模板后，UE-V 将在已注册模板的计算机之间同步模板中定义的设置。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>注销-UevTemplate</p></td>
    <td align="left"><p>使用 UE-V 注销设置位置模板。 模板注销后，UE-V 将不再同步在计算机之间的模板中定义的设置。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Update-UevTemplate</p></td>
    <td align="left"><p>使用最新版本的模板更新设置位置模板。 新模板的版本应晚于现有模板的版本。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>Disable-UevTemplate</p></td>
    <td align="left"><p>对计算机的当前用户禁用设置位置模板。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Enable-UevTemplate</p></td>
    <td align="left"><p>为计算机的当前用户启用设置位置模板。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>Test-UevTemplate</p></td>
    <td align="left"><p>确定给定设置位置模板是否符合其 XML 架构。</p></td>
    </tr>
    </tbody>
    </table>

     

UE-V PowerShell 功能允许你管理在你的企业中部署的一组设置模板。 若要使用 PowerShell 管理一组模板，请执行下列操作。

**使用 PowerShell 管理一组设置位置模板**

1.  修改或更新所需的设置位置模板。

2.  将所需的设置位置模板部署到本地计算机可访问的文件夹。

3.  在本地计算机上，打开具有管理员权限的 Windows PowerShell 窗口。

4.  通过键入以下命令导入 Microsoft UE-V PowerShell 模块。

    ``` syntax
    Import-module UEV
    ```

5.  通过键入以下命令注销以前注册的所有版本的模板。

    ``` syntax
    Get-UevTemplate | Unregister-UevTemplate
    ```

    这将注销计算机上的所有活动模板。

6.  通过键入以下命令注册已更新的模板。

    ``` syntax
    Register-UevTemplate <path to template folder>\*.xml
    ```

    这将注册位于指定模板文件夹中的所有设置位置模板。

用户体验虚拟化提供以下 WMI 命令集。 管理员可以使用这些接口从 Windows PowerShell 中管理设置位置模板，并自动执行模板管理任务。

**通过 WMI 管理设置位置模板**

1.  使用具有管理员权限的帐户打开 Windows PowerShell 窗口。

2.  使用以下 WMI 命令注册和管理 UE-V 设置位置模板。

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
    <td align="left"><p>WmiObject-命名空间 root\Microsoft\UEV SettingsLocationTemplate |选择-Object TemplateId、TemplateName、TemplateVersion、Enabled |格式表-自动调整</p></td>
    <td align="left"><p>列出为计算机注册的所有设置位置模板。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>WmiMethod-命名空间 root\Microsoft\UEV 类 SettingsLocationTemplate 名称 Register-ArgumentList &lt; 模板路径&gt;</p></td>
    <td align="left"><p>使用 UE-V 注册设置位置模板。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>WmiMethod-命名空间 root\Microsoft\UEV 类 SettingsLocationTemplate-Name UnregisterByTemplateId-ArgumentList &lt; 模板 ID&gt;</p></td>
    <td align="left"><p>使用 UE-V 注销设置位置模板。 模板注销后，UE-V 将不再同步在计算机之间的模板中定义的设置。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>WmiMethod-命名空间 root\Microsoft\UEV 类 SettingsLocationTemplate-Name EnableByTemplateId-ArgumentList &lt; 模板 ID&gt;</p></td>
    <td align="left"><p>使用 UE-V 启用设置位置模板</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>WmiMethod-命名空间 root\Microsoft\UEV 类 SettingsLocationTemplate-Name DisableByTemplateId-ArgumentList &lt; 模板 ID&gt;</p></td>
    <td align="left"><p>使用 UE-V 禁用设置位置模板</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>WmiMethod-命名空间 root\Microsoft\UEV 类 SettingsLocationTemplate-Name Update-ArgumentList &lt; 模板路径&gt;</p></td>
    <td align="left"><p>使用 UE-V 更新设置位置模板。 新模板的版本应高于现有模板的版本。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>WmiMethod-命名空间 root\Microsoft\UEV 类 SettingsLocationTemplate-Name Validate ArgumentList &lt; 模板路径&gt;</p></td>
    <td align="left"><p>确定给定设置位置模板是否符合其 XML 架构。</p></td>
    </tr>
    </tbody>
    </table>

     

**如何通过 PowerShell 部署 UE-V agent**

1.  在易于访问的网络共享中暂存 UE-V 安装程序文件。

    **注意** 使用 AgentSetup.exe 部署32位和64位的 UE-V Agent 版本。 Windows Installer 文件版本、AgentSetupx86.msi 和 AgentSetupx64.msi 适用于每个体系结构。 若要在以后使用安装文件卸载 UE-V Agent，必须使用相同的文件类型。

     

2.  使用以下 PowerShell 命令之一安装代理。

    `& AgentSetup.exe /quiet /norestart /log "%temp%\UE-VAgentInstaller.log" SettingsStoragePath=\\server\settingsshare\%username%`

    `& msiexec.exe /i "<path to msi file>" /quiet /norestart /l*v "%temp%\UE-VAgentInstaller.log" SettingsStoragePath=\\server\settingsshare\%username%`

## 相关主题


[使用 PowerShell 和 WMI 管理 UE-V 1.0 代理和程序包](managing-the-ue-v-10-agent-and-packages-with-powershell-and-wmi.md)

[管理 UE-V 1.0](administering-ue-v-10.md)

[UE-V 1.0 的操作](operations-for-ue-v-10.md)

 

 





