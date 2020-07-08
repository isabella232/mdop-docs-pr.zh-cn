---
title: 部署 UE-V 代理
description: 部署 UE-V 代理
author: dansimp
ms.assetid: ec1c16c4-4be0-41ff-93bc-3e2b1afb5832
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 19f3b798ad7d3a43b0a274a25dd97b651435de51
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804117"
---
# 部署 UE-V 代理


Microsoft 用户体验虚拟化（UE-V） agent 必须在使用 UE-V 的每台计算机上运行，以便漫游应用程序和 Windows 设置。 AgentSetup.exe 在32位和64位操作系统上安装 UE-V agent 的单个安装程序文件。 UE-V Agent 的命令行参数如下所示：

**AgentSetup.exe 命令行参数**

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong>命令行参数</strong></th>
<th align="left"><strong>定义</strong></th>
<th align="left"><strong>注释</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>/help 或/h 或/？</p></td>
<td align="left"><p>显示 "AgentSetup.exe 用法" 对话框。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>SettingsStoragePath</p></td>
<td align="left"><p>指示用于定义存储设置的位置的通用命名约定（UNC）路径。</p></td>
<td align="left"><p>已接受% 用户名% 或% computername% 环境变量。 脚本可能需要转义变量。</p>
<p><strong>默认 </strong> ： &lt; 无 &gt; （Active Directory 用户 home）</p></td>
</tr>
<tr class="odd">
<td align="left"><p>SettingsTemplateCatalogPath</p></td>
<td align="left"><p>指示用于定义为新设置位置模板检查的位置的通用命名约定（UNC）路径。</p></td>
<td align="left"><p>仅对于自定义设置位置模板是必需的</p></td>
</tr>
<tr class="even">
<td align="left"><p>RegisterMSTemplates</p></td>
<td align="left"><p>指定是否应在安装期间注册默认 Microsoft 模板。</p></td>
<td align="left"><p>True |;</p>
<p><strong>默认值 </strong> ： True</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Powerschool</p></td>
<td align="left"><p>指定应使用的同步方法。</p></td>
<td align="left"><p>OfflineFiles |尚</p>
<p><strong>默认 </strong> ： OfflineFiles</p></td>
</tr>
<tr class="even">
<td align="left"><p>SyncTimeoutInMilliseconds</p></td>
<td align="left"><p>指定从设置存储位置检索用户设置时，计算机在超时之前等待的毫秒数。</p></td>
<td align="left"><p><strong>默认 </strong> ：2000毫秒</p>
<p>（等待2秒钟）</p></td>
</tr>
<tr class="odd">
<td align="left"><p>SyncEnabled</p></td>
<td align="left"><p>指定是启用还是禁用 UE-V 同步。</p></td>
<td align="left"><p>True |;</p>
<p><strong>默认值 </strong> ： True</p></td>
</tr>
<tr class="even">
<td align="left"><p>MaxPackageSizeInBytes</p></td>
<td align="left"><p>指定当 UE-V agent 报告文件超过阈值时的设置程序包文件大小（以字节为单位）。</p></td>
<td align="left"><p>&lt;size&gt;</p>
<p><strong>默认值 </strong> ：无（无警告阈值）</p></td>
</tr>
<tr class="odd">
<td align="left"><p>CEIPEnabled</p></td>
<td align="left"><p>指定参与客户体验改善计划的设置。 如果设置为 true，则将安装程序信息上载到 "Microsoft 客户体验改善计划" 网站。 如果设置为 false，则不会上载任何信息。</p></td>
<td align="left"><p>True |;</p>
<p><strong>默认值 </strong> ： False</p>
<p><strong>在 Windows 7 上 </strong> ： True</p></td>
</tr>
</tbody>
</table>

 

在安装期间，SettingsStoragePath 命令行参数指定设置值的设置存储位置。 可以在部署 UE-V Agent 之前定义设置存储位置。 如果未定义任何设置存储位置，则 UE-V 使用 Active Directory 用户主目录作为设置存储位置。 在设置过程中指定 SettingsStoragePath 配置并使用% username% 作为值的一部分时，这将在用户登录的所有计算机或会话上漫游相同的用户设置体验。 如果将%username%\\%computername% 变量指定为 SettingsStoragePath 值的一部分，这将保留每台计算机的设置体验。

除了组合的32位和64位安装程序之外，还为 UE-V agent 安装提供了特定于体系结构的 Windows Installer （.msi）文件。 AgentSetupx86.msi 或 AgentSetupx64.msi 安装文件小于 AgentSetup.exe 文件，因此可能会简化代理部署。 Windows Installer （.msi）安装支持 AgentSetup.exe 安装程序的命令行参数。

**注意** 在 UE-V agent 安装或卸载期间，你可以使用 AgentSetup.exe 文件或 AgentSetup xxx &lt; &gt; 文件，但不能同时使用这两者。 必须使用同一文件卸载 UE-V Agent，因为它是用于安装 UE-V Agent 的。

 

请确保在安装 UE-V agent 时使用正确的变量格式。 下表提供了使用 AgentSetup.exe 或 Windows Installer （.msi）安装文件的部署选项的示例。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong>部署类型</strong></th>
<th align="left"><strong>部署说明</strong></th>
<th align="left"><strong>示例</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>命令提示符</p></td>
<td align="left"><p>从命令提示符安装 UE-V agent 时，请使用% ^ username% 变量格式。 如果由于设置存储路径中的空格而需要引号，请使用批处理脚本文件进行部署。</p>
<p></p></td>
<td align="left"><p><code>AgentSetup.exe /quiet /norestart /log &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare%^username%</code></p>
<p></p>
<p><code>msiexec.exe /i &quot;&lt;path to msi file&gt;&quot; /quiet /norestart /l<em>v &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare%^username%</code></p></td>
</tr>
<tr class="even">
<td align="left"><p>批处理脚本</p></td>
<td align="left"><p>从批处理脚本文件安装 UE-V Agent 时，请使用%% 用户名%% 变量格式。 如果使用此安装方法，则必须使用%% 字符转义变量。 如果没有此字符，脚本将在安装时（而不是在运行时）扩展用户名变量，从而导致 UE-V 对所有用户使用单个设置存储位置。</p></td>
<td align="left"><p><code>AgentSetup.exe /quiet /norestart /log &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=&quot;\server\settingsshare%%username%%&quot;</code></p>
<p></p>
<p><code>msiexec.exe /i &quot;&lt;path to msi file&gt;&quot; /quiet /norestart /l</em>v &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=&quot;\server\settingsshare%%username%%&quot;</code></p>
<p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>PowerShell</p></td>
<td align="left"><p>从 PowerShell 提示或 PowerShell 脚本安装 UE-V agent 时，请使用% username% 变量格式。</p></td>
<td align="left"><p><code>&amp; AgentSetup.exe /quiet /norestart /log &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare%username%</code></p>
<p></p>
<p><code>&amp; msiexec.exe /i &quot;&lt;path to msi file&gt;&quot; /quiet /norestart /l<em>v &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare%username%</code></p>
<p></p></td>
</tr>
<tr class="even">
<td align="left"><p>电子软件分发，如 Configuration Manager 软件部署的部署）</p></td>
<td align="left"><p>当使用配置管理器安装 UE-V Agent 时，请使用 ^% 用户名 ^% 变量格式。</p></td>
<td align="left"><p><code>AgentSetup.exe /quiet /norestart /log &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare^%username^%</code></p>
<p></p>
<p><code>msiexec.exe /i &quot;&lt;path to msi file&gt;&quot; /quiet /norestart /l</em>v &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare^%username^%</code></p></td>
</tr>
</tbody>
</table>

 

**注意** 安装 U-EV 代理需要管理员权限，并且计算机需要重启才能运行 UE-V Agent。

 

## 来自网络共享的 UE-V Agent 部署方法


你可以使用以下方法来部署 UE-V agent：

-   可安装 Windows Installer （.msi）文件的电子软件分发（ESD）解决方案。

-   一个安装脚本，它引用在一个共享位置集中存储的 Windows Installer （.msi）文件。

-   在计算机上手动运行安装程序。

若要从网络共享部署 UE-V agent，请使用以下步骤：

**从网络共享安装和配置 UE-V Agent**

1.  在用户具有 "读取" 权限的网络共享上暂存 UE-V agent 安装文件（AgentSetup.exe）。

2.  将脚本部署到安装 UE-V agent 的用户计算机。 脚本应指定设置存储位置。

**更新 UE-V Agent**

UE-V agent 软件的更新将通过 Microsoft Update 提供。 在 UE-V agent 升级过程中，可能会更新常见 Microsoft 应用程序和 Windows 设置的默认设置位置模板组。 可以使用企业软件分发（ESD）基础结构部署 UE-V agent 更新。

## 相关主题


[部署 UE-V 1.0](deploying-ue-v-10.md)

[UE-V 1.0 支持的配置](supported-configurations-for-ue-v-10.md)

[为 UE-V 1.0 部署设置存储位置](deploying-the-settings-storage-location-for-ue-v-10.md)

[安装 UE-V 生成器](installing-the-ue-v-generator.md)

部署用户体验虚拟化代理
 

 





