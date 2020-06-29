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
# 更改 UE-V 2 x 计划任务的频率


Microsoft 用户体验虚拟化（UE-V）2.0、2.1 或 2.1 SP1 代理安装程序 AgentSetup.exe 在 UE-V Agent 安装期间创建以下计划任务：

-   **监视应用程序设置**

-   **同步控制器应用程序**

-   **在注销时同步设置**

-   **模板自动更新**

-   **收集 CEIP 数据**

-   **上载 CEIP 数据**

**注意** 除了收集 CEIP 数据，这些任务必须保持启用状态，因为 UE-V 在没有它们的情况下无法正常工作。

 

这些计划任务无法通过 UE-V 工具进行配置。 希望更改这些项目的计划任务的管理员可以创建使用 Schtasks.exe 命令行选项的脚本。

有关 Schtasks.exe 的详细信息，请参阅[如何使用 Schtasks、exe 在 Windows Server 2003 中安排任务](https://go.microsoft.com/fwlink/?LinkID=264854)。

有关详细信息

## UE-V 计划的任务


通过示例计划任务配置命令，UE-V 2 中包含以下计划任务。

### 收集 CEIP 数据

如果在安装时用户或管理员 choses 参与客户体验改善计划（CEIP），UE-V 将收集数据，以帮助改进未来版本中的产品。 此计划任务仅在登录时运行。 "**收集 CEIP 数据**" 任务将运行 "UevSqmSession.exe"，它位于 ue-v agent 安装目录中。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">任务名称</th>
<th align="left">默认事件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>\Microsoft\UE-V\Collect CEIP 数据</p></td>
<td align="left"><p>Logon</p></td>
</tr>
</tbody>
</table>

 

### 监视应用程序设置

"**监视器应用程序设置**" 任务用于同步 Windows 应用的设置。 它在登录时运行，但延迟30秒以不影响登录 detrimentally。 "监视应用程序状态" 任务运行 "UevAppMonitor.exe" 文件，该文件位于 UE-V Agent 安装目录中。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">任务名称</th>
<th align="left">默认事件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>\Microsoft\UE-V\Monitor 应用程序状态</p></td>
<td align="left"><p>Logon</p></td>
</tr>
</tbody>
</table>

 

### 同步控制器应用程序

**同步控制器应用程序**任务用于启动同步控制器，以便将计算机中的设置同步到设置存储位置。 默认情况下，任务每30分钟运行一次。 此时，本地设置将同步到设置存储位置，并且设置存储位置上的更新设置将同步到计算机。 同步控制器应用程序运行位于 UE-V Agent 安装目录中的 Microsoft.Uev.SyncController.exe。
**注意：** 根据 "**监视器应用程序设置**" 任务，此任务在登录时运行，但延迟30秒以不影响登录 detrimentally。
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">任务名称</th>
<th align="left">默认事件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>\Microsoft\UE-V\Sync 控制器应用程序</p></td>
<td align="left"><p>登录，此后每天30分钟</p></td>
</tr>
</tbody>
</table>

 

例如，以下命令将代理配置为每15分钟同步一次设置，而不是默认的30分钟。

``` syntax
Schtasks /change /tn “Microsoft\UE-V\Sync Controller Application” /ri 15
```

### 在注销时同步设置

注销任务的 "**同步设置**" 用于在登录时启动应用程序，以便在对 ue-v 注销时控制应用程序的同步。 "注销任务" 中的 "同步设置" 将运行位于 UE-V Agent 安装目录中的 Microsoft.Uev.SyncController.exe 文件。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">任务名称</th>
<th align="left">默认事件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>注销时的 \Microsoft\UE-V\Synchronize 设置</p></td>
<td align="left"><p>Logon</p></td>
</tr>
</tbody>
</table>

 

### 模板自动更新

**模板自动更新**任务检查设置模板目录中是否有新的、已更新或已删除的模板。 仅当配置了 SettingsTemplateCatalog 时，此任务才会运行。 **模板自动更新**任务运行 "ApplySettingsCatalog.exe" 文件，该文件位于 ue-v agent 安装目录中。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">任务名称</th>
<th align="left">默认事件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>\Microsoft\UE-V\Template 自动更新</p></td>
<td align="left"><p>系统启动和每天3:30 上午，在1小时窗口内随机时间</p></td>
</tr>
</tbody>
</table>

 

**示例：** 以下命令将每小时的 UE-V Agent 配置为检查设置模板目录存储。

``` syntax
schtasks /change /tn "Microsoft\UE-V\Template Auto Update" /ri 60
```

### 上载 CEIP 数据

如果用户或管理员选择参与客户体验改善计划（CEIP），则会在安装期间运行 "**上载 CEIP 数据**" 任务。 此任务将数据上载到 CEIP 服务器，在此服务器中，数据用于帮助改进此产品以供 UE-V 的未来版本使用。 此计划任务将在登录时和每4小时运行一次。 "**上载 CEIP 数据**" 任务将运行位于 ue-v Agent 安装目录中的 UevSqmUploader.exe 文件。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">任务名称</th>
<th align="left">默认事件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>\Microsoft\UE-V\Upload CEIP 数据</p></td>
<td align="left"><p>在登录时和每隔4小时</p></td>
</tr>
</tbody>
</table>

 

## UE-V 2 计划任务的详细信息


下图提供了有关 UE-V 2 的计划任务的其他信息：

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
<td align="left"><p><strong>任务名称 </strong> （文件名）</p></td>
<td align="left"><p><strong>默认频率</strong></p></td>
<td align="left"><p><strong>Power 开关</strong></p></td>
<td align="left"><p><strong>仅空闲</strong></p></td>
<td align="left"><p><strong>网络连接</strong></p></td>
<td align="left"><p><strong>描述</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>监视应用程序设置 </strong> （UevAppMonitor.exe）</p></td>
<td align="left"><p>在登录后的30秒内启动并继续，直到注销。</p></td>
<td align="left"><p>不可用</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>不适用</p></td>
<td align="left"><p>同步 Windows （AppX）应用的设置。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>同步控制器应用程序 </strong> （Microsoft.Uev.SyncController.exe）</p></td>
<td align="left"><p>在登录时和每隔30分钟之后。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>仅当网络已连接时</p></td>
<td align="left"><p>启动同步控制器，该控制器将本地设置与设置存储位置同步。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>在注销时同步设置 </strong> （Microsoft.Uev.SyncController.exe）</p></td>
<td align="left"><p>在登录时运行，然后等待注销同步设置。</p></td>
<td align="left"><p>不可用</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>不适用</p></td>
<td align="left"><p>在登录时启动应用程序以控制应用程序在注销时的同步。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>模板自动更新 </strong> （ApplySettingsCatalog.exe）</p></td>
<td align="left"><p>在初始登录时运行，此后每天 3:30 AM 运行。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>否</p></td>
<td align="left"><p>不适用</p></td>
<td align="left"><p>检查设置模板目录中是否有新的、已更新或已删除的模板。 仅当配置了 SettingsTemplateCatalog 时，此任务才会运行。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>收集 CEIP 数据 </strong> （UevSqmSession.exe）</p></td>
<td align="left"><p>在登录时启动服务</p></td>
<td align="left"><p>否</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>不适用</p></td>
<td align="left"><p>如果用户或管理员已加入客户体验改善计划（CEIP），此任务将收集可帮助改进 UE-V 未来版本的数据。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>上载 CEIP 数据 </strong> （UevSqmUploader.exe）</p></td>
<td align="left"><p>在登录时以及此后每天的 4:00 AM 运行。</p></td>
<td align="left"><p>否</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>仅当网络已连接时</p></td>
<td align="left"><p>如果用户或管理员已加入客户体验改善计划（CEIP），此任务会将数据上载到 CEIP 服务器。</p></td>
</tr>
</tbody>
</table>

 

**图表**

-   **Power 开关**-当未连接到交流电源时，任务计划程序将优化功率消耗。 如果计算机切换到电池电源，该任务可能会停止运行。

-   **仅空闲**-如果计算机停止空闲，任务将停止运行。 默认情况下，当计算机再次空闲时，不会重新启动任务。 此时，任务将在下一个任务触发器上再次开始。

-   **网络连接**-标记为 "是" 的任务仅当计算机有可用的网络连接时才运行。 标记为 "N/A" 的任务无论网络连接如何都运行。

### 如何管理计划任务

若要查找计划任务，请执行下列操作：

1.  在用户计算机上打开 "安排任务"。

2.  导航到：任务计划程序- &gt; 任务计划程序库- &gt; Microsoft &gt; ue-v

3.  在 "详细信息" 窗格中选择要管理和配置的计划任务。

### 其他信息

以下附加信息适用于 UE-V 计划的任务：

-   默认情况下，任务序列程序位于 UE-V Agent 安装文件夹中 `%programFiles%\Microsoft User Experience Virtualization\Agent\[architecture]\` 。

-   当 UE-V Powerschool 设置为 "SyncProvider" （UE-V 2 默认配置）时，同步控制器应用程序计划任务是关键组件。 此计划任务使 SettingsSToragePath 与设置程序包文件的本地缓存版本保持同步。 如果用户抱怨设置不会经常同步，则可以将计划任务设置减少为1分钟。如果需要，还可以将30分钟的默认值增加到更高的金额。 如果用户抱怨在登录时设置同步速度不够快，则可以删除计划任务的延迟设置。 （可以在 "**编辑触发器**" 对话框中找到 "延迟" 设置）

-   如果你使用另一种方法保持客户端的模板同步（即组策略或配置管理器基线），则不需要禁用模板自动更新计划任务。 将 SettingsTemplateCatalog 属性值保留为空将阻止 UE-V 检查自定义模板的设置目录。 此计划任务 ApplySettingsCatalog.exe 运行，实质上将立即返回。

-   "监视器应用程序设置计划任务" 将基于每个应用中内置的 Windows 应用程序设置触发器实时更新 Windows 应用（AppX）设置。






## 相关主题


[管理 UE-V 2. x](administering-ue-v-2x-new-uevv2.md)

[部署自定义应用程序的 UE-V 2。](deploy-ue-v-2x-for-custom-applications-new-uevv2.md#deploycatalogue)

 

 





