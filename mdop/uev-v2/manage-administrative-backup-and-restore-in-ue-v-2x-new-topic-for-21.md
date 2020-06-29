---
title: 在 UE-V 2. x 中管理管理备份和还原
description: 在 UE-V 2. x 中管理管理备份和还原
author: dansimp
ms.assetid: 2eb5ae75-65e5-4afc-adb6-4e83cf4364ae
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 11c168b54b71731c51417b2b7c4737c85f42035a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804158"
---
# 在 UE-V 2. x 中管理管理备份和还原


作为 Microsoft 用户体验虚拟化（UE-V）2.0、2.1 或 2.1 SP1 的管理员，你可以将应用程序和 Windows 设置还原到其原始状态。 此外，在 UE-V 2.1 中，你还可以在用户采用新设备时还原其他设置。

## 当用户采用新设备时，在 UE-V 2.1 或 UE-V 2.1 SP1 中还原设置


若要在用户使用新设备时还原设置，可以使用 UevTemplateProfile PowerShell cmdlet 将设置位置模板放置在 "**备份**" 或 "**漫游" （默认）** 配置文件中。 除了用户设置外，此功能还允许将计算机设置与新计算机同步。 为该设备备份分配给备份配置文件的模板，并基于每台设备进行配置。 若要备份模板的设置，请在 Windows PowerShell 中使用以下 cmdlet：

``` syntax
Set-UevTemplateProfile -ID <TemplateID> -Profile <backup>
```

-   &lt;TemplateID &gt; 是 Ue-v 模板 ID

-   &lt;备份 &gt; 可以是备份或漫游

当用户的域、用户名和设备名称全部匹配时，当替换用户的设备时，UE-V 会自动还原设置。 将自动在设备上还原所有已同步和任何备份数据。

你还可以使用新的 PowerShell cmdlet UevBackup 还原其他设备中的设置。 若要克隆新设备的设置程序包，请使用 Windows PowerShell 中的以下 cmdlet：

``` syntax
Restore-UevBackup –Machine <MachineName>
```

其中 &lt; 计算机 &gt; 名是设备的计算机名。

包含许多应用程序的模板（如 Office 2013 模板）既可以包含在漫游（默认）还是备份配置文件中。 模板套件中的单个应用关注组。 Office 2013 内置模板包括漫游和仅备份设置。 仅备份设置不能包含在漫游配置文件中。

作为 "备份/还原" 功能的一部分，UE-V 将 "**最后一次正确的" （LKG）** 添加到用于回退到设置的选项。 在此版本中，你可以返回到原始设置或 LKG 设置。 LKG 设置允许用户回退到设置的前 UE-V 状态之前的中间和稳定点。

### 如何通过 UE-V 备份/还原模板

以下是 UE-V 的主要备份和还原组件：

-   模板配置文件

-   设置存储位置模板内的设置程序包位置

-   备份触发器

-   如何还原设置

**模板配置文件**

在设备上注册模板或通过 PowerShell/WMI 配置实用程序发布注册时，将定义 UE-V 模板配置文件。 配置文件类型包括：

-   漫游（默认）

-   备份

-   BackupOnly

除非另行指定，否则在注册后，所有模板都将包含在漫游配置文件中。 这些模板将设置同步到启用了相应模板的所有 UE-V 启用的设备。

可使用 UevTemplateProfile cmdlet 将模板添加到具有 PowerShell 或 WMI 的备份配置文件。 备份配置文件中的模板将这些设置备份到 "特殊设备名称" 目录中的 "设置" 存储位置。 指定的设置将备份到此位置。

指定 BackupOnly 的模板包括特定于该设备的设置，除非显式还原，否则不应进行同步。 这些设置存储在设置存储位置上的同一特定于设备的设置程序包位置，作为 Backedup 设置。 这些模板具有嵌入在模板中的特殊标识符，用于指定这些模板应属于此配置文件的一部分。

**设置存储位置模板内的设置程序包位置**

漫游配置文件设置存储在设置存储位置。 分配给备份或 BackupOnly 配置文件的模板将其设置存储在特殊设备名称目录中的设置存储位置。 每台具有这些配置文件中的模板的设备都有其自己的设备名称。 UE-V 不会清理这些目录。

**备份触发器**

备份由触发 UE-V 同步的相同事件触发。

**如何还原设置**

还原用户的设备会将当前注册的模板设置从其他设备的备份文件夹和所有同步设置还原到当前计算机。 可通过以下两种方式还原设置：

-   **自动还原**

    如果用户的 UE-V 设置存储路径、域和计算机名称与当前用户匹配，则该用户的所有设置都将同步，并且仅应用最新设置。 如果用户首次登录到新设备并满足这些条件，则设置数据将应用到该设备。

    **注意**  
    辅助功能和 Windows 桌面设置要求用户重新登录到要应用的 Windows。



-   **手动还原**

    如果你想要在刷新期间通过还原设备来帮助用户，你可以选择使用 UevBackup cmdlet。 此命令会导致从设置存储位置下载用户的设置。

## 将应用程序和 Windows 设置还原为原始状态


WMI 和 Windows PowerShell 命令允许你在安装 UE-V Agent 后首次启动应用程序时，将应用程序和 Windows 设置还原到计算机上的设置值。 将在每个应用程序或 Windows 设置基础上执行此还原操作。 下次应用程序运行时，将恢复这些设置，或者当用户登录到操作系统时还原设置。

**将应用程序设置和 Windows 设置还原为适用于 UE-V 2 的 Windows PowerShell。 x**

1.  打开 Windows PowerShell 窗口。

2.  输入以下 Windows PowerShell cmdlet 以还原应用程序设置和 Windows 设置。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong>Windows PowerShell cmdlet</strong></th>
    <th align="left"><strong>描述</strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><code>Restore-UevUserSetting -&lt;TemplateID&gt;</code></p></td>
    <td align="left"><p>还原应用程序的用户设置或还原一组 Windows 设置。</p></td>
    </tr>
    </tbody>
    </table>



**通过 WMI 还原应用程序设置和 Windows 设置**

1.  打开 Windows PowerShell 窗口。

2.  输入以下 WMI 命令以还原应用程序设置和 Windows 设置。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong>WMI 命令</strong></th>
    <th align="left"><strong>描述</strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class UserSettings -Name RestoreByTemplateId -ArgumentList &lt;template_ID&gt;</code></p></td>
    <td align="left"><p>还原应用程序的用户设置或还原一组 Windows 设置。</p></td>
    </tr>
    </tbody>
    </table>



~~~
**Note**  
UE-V does not provide a settings rollback for Windows apps.
~~~








## 相关主题


[管理具有 Windows PowerShell 和 WMI 的 UE-V 2。](administering-ue-v-2x-with-windows-powershell-and-wmi-both-uevv2.md)

[管理 UE-V 2. x](administering-ue-v-2x-new-uevv2.md)









