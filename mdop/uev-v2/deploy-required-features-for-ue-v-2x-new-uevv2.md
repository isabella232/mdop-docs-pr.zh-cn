---
title: 为 UE-V 2.x 部署所需功能
description: 为 UE-V 2.x 部署所需功能
author: dansimp
ms.assetid: 10399bb3-cc7b-4578-bc0c-2f6b597abe4d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f2123ec75fb151a8f5b836b9b2522a9d6090b043
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803614"
---
# 为 UE-V 2.x 部署所需功能


所有 Microsoft 用户体验虚拟化（UE-V）2.0、2.1 和 2.1 SP1 部署都需要这些功能

-   部署最终用户易于访问的[设置存储位置](#ssl)。

    这是一个标准的网络共享，用于存储和检索用户设置。

-   [选择 UE-V 的配置方法](#config)

    可以使用通用管理工具（包括组策略、配置管理器或 Windows 管理基础结构和 Powershell）部署和配置 UE-V。

-   部署要在同步设置的每台计算机上安装的[Ue-v Agent](#agent) 。

    这将监视已注册应用程序和操作系统的任何设置更改，并在计算机之间同步这些设置。

本部分中的主题介绍了如何部署这些功能。

## <a href="" id="ssl"></a>部署 UE-V 设置存储位置


UE-V 需要在设置包文件中存储用户设置的位置。 你可以通过以下方式之一配置此设置存储位置：

-   创建您自己的设置存储位置

-   将现有 Active Directory 用于设置存储位置

如果不创建设置存储位置，则 UE-V Agent 默认情况下将使用 Active Directory （AD）。

**注意**  
作为[性能和容量规划](https://technet.microsoft.com/library/dn458932.aspx#capacity)以及减少网络延迟问题，请在用户计算机所在的同一本地网络上创建设置存储位置。 我们建议每个用户 20 MB 的磁盘空间用于设置存储位置。



### 创建 UE-V 设置存储位置

在定义设置存储位置之前，必须为在共享上存储设置的用户创建一个具有读/写权限的 root 目录。 UE-V Agent 在此根目录下创建特定于用户的文件夹。

设置存储位置通过设置 SettingsStoragePath 配置选项来定义，可通过以下方法之一进行配置：

-   通过命令行参数或在批处理脚本中[部署 Ue-v Agent](#agent)时

-   通过[组策略](https://technet.microsoft.com/library/dn458893.aspx)设置

-   对于 UE-V 的[System Center 配置包](https://technet.microsoft.com/library/dn458917.aspx)

-   在安装 UE-V Agent 之后，使用[Windows PowerShell 或 Windows Management Instrumentation （WMI）](https://technet.microsoft.com/library/dn458937.aspx)

路径必须位于服务器和共享的通用命名约定（UNC）路径中。 例如， **\\\\Server\\Settingsshare\\**。 此配置选项支持使用变量来启用特定的同步方案。 例如，你可以 `%username%\%computername%` 在以下情况下使用变量来保留最终用户设置体验：

-   在您的企业中使用多台物理计算机的最终用户

-   多个最终用户使用的企业计算机

UE-V Agent `SettingsPackages` 基于**SettingsStoragePath**的配置设置，动态创建一个特定于用户的设置存储路径，该路径具有一个名为的隐藏系统文件夹。 代理读取并将设置写入到此位置，如注册的 UE-V 设置位置模板所定义。

**Ue-v 设置由 "最后一次写入的 wins" 规则确定：** 如果对于具有多台托管计算机的用户而言，设置存储位置是相同的，则一个 UE-V Agent 将在其他计算机上运行的代理独立地读取和写入设置位置。 最后写入的设置和值是在下一个代理从设置存储位置读取时应用的值。

**部署设置存储位置：** 请按照以下步骤定义设置存储位置，而不是使用现有的 Active Directory 服务。 你应该将对设置存储共享的访问限制到需要它的用户，如下表所示。

**部署 UE-V 网络共享**

1.  为 UE-V 用户创建新的安全组。

2.  在存储 UE-V settings 程序包的集中位置的计算机上创建一个新文件夹，然后向 UE-V 用户授予对该文件夹的组权限。 支持 UE-V 的管理员必须具有此共享文件夹的权限。

3.  为 "设置存储位置" 文件夹设置以下共享级服务器消息块（SMB）权限。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong>用户帐户</strong></th>
    <th align="left"><strong>推荐的权限</strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>所有人</p></td>
    <td align="left"><p>无权限</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>UE-V 用户的安全组</p></td>
    <td align="left"><p>完全控制</p></td>
    </tr>
    </tbody>
    </table>



4.  为 "设置存储位置" 文件夹设置以下 NTFS 文件系统权限。

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong>用户帐户</strong></th>
    <th align="left"><strong>推荐的权限</strong></th>
    <th align="left"><strong>文件夹</strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>创建者/所有者</p></td>
    <td align="left"><p>完全控制</p></td>
    <td align="left"><p>仅子文件夹和文件</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>UE-V 用户的安全组</p></td>
    <td align="left"><p>列出文件夹/读取数据、创建文件夹/附加数据</p></td>
    <td align="left"><p>仅此文件夹</p></td>
    </tr>
    </tbody>
    </table>



通过此配置，UE-V Agent 在用户的上下文中运行时创建并保护 Settingspackage 文件夹，并授予每个用户创建设置存储文件夹的权限。 用户接收 Settingspackage 文件夹的完全控制，而其他用户无法访问它。

**注意**  
如果在运行 Windows Server 操作系统的计算机上创建设置存储共享，请配置 UE-V 以验证本地管理员组或当前用户是否为存储设置包的文件夹的所有者。 若要启用此附加安全性，请在 Windows Server 注册表编辑器中指定此设置：

1.  将名为 **"RepositoryOwnerCheckEnabled"** 的**REG \ _DWORD**注册表项添加到**HKEY \ _LOCAL \ _MACHINE \\software\\microsoft\\uev\\agent\\configuration**。

2.  将注册表项值设置为*1*。



### 将 Active Directory 与 UE-V 2. x 配合使用

如果未另外定义设置存储位置，则 UE-V Agent 默认使用 Active Directory （AD）。 在这些情况下，UE-V Agent 会在每个用户的广告主目录的根目录下动态创建设置存储文件夹。 但是，如果在 AD 中配置了自定义目录设置，则改为使用该目录。

## <a href="" id="config"></a>选择 UE-V 2 的配置方法。


你想要确定你将用于在部署后管理 UE-V 的配置方法，因为这将是你用于部署 UE-V Agent 的配置方法。 通常，这是你已在你的环境中使用的配置方法，例如 Windows PowerShell 或配置管理器。

你可以在 UE-V Agent 安装前后配置 UE-V，具体取决于你使用的配置方法。

-   [组策略](https://technet.microsoft.com/library/dn458893.aspx)**：** 您可以使用现有的组策略结构在 ue-v agent 部署之前或之后配置 ue-v。 UE-V 组策略 ADMX 模板支持集中管理常见的 UE-V Agent 配置选项，其中包括用于配置 UE-V 同步的设置。

    **安装 Ue-v 组策略 ADMX 模板：** UE-V 的组策略 ADMX 模板配置 UE-V Agent 的同步设置，并通过使用现有的组策略基础结构启用常见 UE-V Agent 配置设置的集中管理。

    部署组策略对象的域控制器支持的操作系统包括以下内容：

    Windows Server 2008 R2

    Windows Server 2012 和 Windows Server 2012 R2

-   [配置管理器](https://technet.microsoft.com/library/dn458917.aspx)**：** ue-v 配置包使你可以使用 System Center configuration Manager 2012 SP1 或更高版本的合规性设置功能在安装了 ue-v 和配置管理器的网站之间应用一致的配置。

-   [Windows powershell 和 WMI](https://technet.microsoft.com/library/dn458937.aspx)**：** 你可以使用 windows powershell 和 windows Management Instrumentation （WMI）的脚本命令在安装 ue-v Agent 后修改配置。

    **注意**  
    注册表修改可能导致数据丢失或计算机无法响应。 我们建议你使用其他配置方法。



-   **命令行或批处理脚本安装：**[部署 Ue-v Agent](#agent)时使用的参数配置许多 ue-v 设置。 电子软件分发系统（如 System Center 2012 配置管理器）在部署和安装 UE-V Agent 软件时使用这些参数配置其客户端。

## <a href="" id="agent"></a>部署 UE-V 2. x 代理


UE-V Agent 是 UE-V 部署的核心，并且必须在使用 UE-V 的每台计算机上运行以同步应用程序和 Windows 设置。

**Ue-v Agent 安装文件：** AgentSetup.exe 在32位和64位操作系统上安装 UE-V Agent 的单个安装文件。 此外，提供了 AgentSetupx86.msi 或 AgentSetupx64.msi 体系结构特定的 Windows Installer 文件，由于它们较小，因此它们可能会简化代理部署。 Windows Installer 安装还支持[AgentSetup.exe 安装程序的命令行参数](#params)。

**重要提示**  
在 UE-V Agent 安装或卸载期间，你可以使用 AgentSetup.exe 文件或 AgentSetup xxx &lt; &gt; 文件，但不能同时使用这两者。 必须使用相同的文件卸载用于安装 UE-V Agent 的 UE-V Agent 程序。



### 部署 UE-V Agent

你可以使用以下方法来部署 UE-V Agent：

-   可安装 Windows Installer （.msi）文件的电子软件分发（ESD）解决方案系统（如配置管理器）。

-   一个安装脚本，它引用在一个共享位置集中存储的 Windows Installer （.msi）文件。

-   在计算机上手动运行的安装程序。

使用以下过程从网络共享部署 UE-V Agent。

**从网络共享安装和配置 UE-V Agent**

1.  在用户具有 "读取" 权限的网络共享上，暂存 UE-V Agent 安装文件 AgentSetup.exe。

2.  将脚本部署到安装 UE-V Agent 的用户计算机。 脚本应指定设置存储位置。

**部署选项：** 请确保在安装 UE-V Agent 时使用正确的变量格式。 下表提供了使用 AgentSetup.exe 或 Windows Installer （.msi）文件的部署选项的示例。

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
<td align="left"><p>在命令提示符处安装 UE-V Agent 时，请使用 <em> % ^ username% </em> 变量格式。 如果由于设置存储路径中的空格而需要引号，请使用批处理脚本文件进行部署。</p>
<p></p></td>
<td align="left"><p><code>AgentSetup.exe /quiet /norestart /log &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare%^username%</code></p>
<p></p>
<p><code>msiexec.exe /i &quot;&lt;path to msi file&gt;&quot; /quiet /norestart /l<em>v &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare%^username%</code></p></td>
</tr>
<tr class="even">
<td align="left"><p>批处理脚本</p></td>
<td align="left"><p>从批处理脚本文件安装 UE-V Agent 时，请使用 <em> %% 用户名%% </em> 变量格式。 如果使用此安装方法，则必须使用%% 字符转义变量。 如果没有此字符，脚本将 <em> </em> 在安装时（而不是在运行时）扩展用户名变量，从而导致 ue-v 对所有用户使用单个设置存储位置。</p></td>
<td align="left"><p><code>AgentSetup.exe /quiet /norestart /log &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=&quot;\server\settingsshare%%username%%&quot;</code></p>
<p></p>
<p><code>msiexec.exe /i &quot;&lt;path to msi file&gt;&quot; /quiet /norestart /l</em>v &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=&quot;\server\settingsshare%%username%%&quot;</code></p>
<p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows PowerShell</p></td>
<td align="left"><p>从 Windows PowerShell 提示或 Windows PowerShell 脚本安装 UE-V Agent 时，请使用 <em> % username% </em> 变量格式。</p></td>
<td align="left"><p><code>&amp; AgentSetup.exe /quiet /norestart /log &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare%username%</code></p>
<p></p>
<p><code>&amp; msiexec.exe /i &quot;&lt;path to msi file&gt;&quot; /quiet /norestart /l<em>v &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare%username%</code></p>
<p></p></td>
</tr>
<tr class="even">
<td align="left"><p>电子软件分发，如 Configuration Manager 软件部署的部署</p></td>
<td align="left"><p>使用配置管理器安装 UE-V Agent 时，请使用 <em> ^% 用户名 ^% </em> 变量格式。</p></td>
<td align="left"><p><code>AgentSetup.exe /quiet /norestart /log &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare^%username^%</code></p>
<p></p>
<p><code>msiexec.exe /i &quot;&lt;path to msi file&gt;&quot; /quiet /norestart /l</em>v &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare^%username^%</code></p></td>
</tr>
</tbody>
</table>



**注意**  
UE-V Agent 的安装需要管理员权限，并且计算机需要重启才能运行 UE-V Agent。



### <a href="" id="params"></a>UE-V Agent 部署的命令行参数

UE-V Agent 的命令行参数如下所示。

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
<td align="left"><div class="alert">
<strong>重要提示</strong><br/><p>必须在 UE-V 2.1 和 UE-V 2.1 SP1 中指定 SettingsStoragePath。 你可以设置 AdHomePath 字符串以指定使用用户&#39;s Active Directory 主路径。 例如，<code>SettingsStoragePath = \share\path|AdHomePath</code>。</p>
<p>在 UE-V 2.0 中，可以将 SettingsStoragePath 保留为空，以改用 Active Directory 主路径。</p>
</div>
<div>

</div>
<p>已接受% 用户名% 或% computername% 环境变量。 脚本可能需要转义变量。</p>
<p><strong>默认 </strong> ： &lt; 无&gt;</p></td>
</tr>
<tr class="odd">
<td align="left"><p>SettingsStoragePathReg</p></td>
<td align="left"><p>在安装期间获取来自注册表的 SettingsStoragePath 值。</p></td>
<td align="left"><p>在命令提示符处，键入以下示例，强制 UE-V 使用 Active Directory 主路径，而不是特定的 UNC。</p>
<p><code>msiexec.exe /i AgentSetupx64.msi acceptlicenseterms=true SettingsStoragePathReg=TRUE /quiet /norestart</code></p></td>
</tr>
<tr class="even">
<td align="left"><p>SettingsTemplateCatalogPath</p></td>
<td align="left"><p>指示用于定义为新设置位置模板检查的位置的通用命名约定（UNC）路径。</p></td>
<td align="left"><p>仅对于自定义设置位置模板是必需的</p></td>
</tr>
<tr class="odd">
<td align="left"><p>RegisterMSTemplates</p></td>
<td align="left"><p>指定是否应在安装期间注册默认 Microsoft 模板。</p></td>
<td align="left"><p>True |;</p>
<p><strong>默认值 </strong> ： True</p></td>
</tr>
<tr class="even">
<td align="left"><p>Powerschool</p></td>
<td align="left"><p>指定应使用的同步方法。</p></td>
<td align="left"><p>SyncProvider |尚</p>
<p><strong>默认 </strong> ： SyncProvider</p></td>
</tr>
<tr class="odd">
<td align="left"><p>SyncTimeoutInMilliseconds</p></td>
<td align="left"><p>指定在从设置存储位置检索用户设置时，计算机超时之前等待的毫秒数。</p></td>
<td align="left"><p><strong>默认 </strong> ：2000毫秒</p>
<p>（等待2秒钟）</p></td>
</tr>
<tr class="even">
<td align="left"><p>SyncEnabled</p></td>
<td align="left"><p>指定是启用还是禁用 UE-V 同步。</p></td>
<td align="left"><p>True |;</p>
<p><strong>默认值 </strong> ： True</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MaxPackageSizeInBytes</p></td>
<td align="left"><p>指定当 UE-V Agent 报告文件超过阈值时的设置程序包文件大小（以字节为单位）。</p></td>
<td align="left"><p>&lt;size&gt;</p>
<p><strong>默认值 </strong> ：无（无警告阈值）</p></td>
</tr>
<tr class="even">
<td align="left"><p>CEIPEnabled</p></td>
<td align="left"><p>指定参与客户体验改善计划的设置。 如果设置为 <strong> True </strong> ，则将安装程序信息上载到 "Microsoft 客户体验改善计划" 网站。 如果设置为 <strong> False </strong> ，则不会上载任何信息。</p></td>
<td align="left"><p>True |;</p>
<p><strong>默认值 </strong> ： False</p></td>
</tr>
<tr class="odd">
<td align="left"><p>NoRestart</p></td>
<td align="left"><p>支持在安装 UE-V Agent 后延迟计算机重启。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>INSTALLFOLDER</p></td>
<td align="left"><p>允许为 UE-V Agent 或 UE-V 发生器设置不同的安装文件夹。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>MUENABLED</p></td>
<td align="left"><p>使安装程序能够接受包含在 Microsoft Update 程序中的选项。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>ACCEPTLICENSETERMS</p></td>
<td align="left"><p>让 UE-V 可以自行安装。 必须将此值设置为 <strong> True </strong> 才能以静默方式安装 ue-v，并绕过用户接受 ue-v 许可条款的要求。 如果设置为 <strong> False </strong> 或保留为空，用户将收到一条错误消息，并且未安装 ue-v。</p></td>
<td align="left"><div class="alert">
<strong>重要提示</strong><br/><p>此参数是自行安装 UE-V 所必需的。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>NORESTART</p></td>
<td align="left"><p>阻止在安装 UE-V Agent 后强制重启。</p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



### 更新 UE-V Agent

UE-V Agent 软件的更新通过 Microsoft Update 提供。 你可以使用企业软件分发（ESD）基础结构系统部署 UE-V Agent 更新。

在 UE-V Agent 升级过程中，可以更新常见 Microsoft 应用程序和 Windows 设置的默认设置位置模板组。

### 升级 UE-V 2. x 代理

UE-V 2 x Agent 引入了许多新功能，并修改了代理将内容上载到设置存储共享的方式和时间。 升级过程将自动执行这些更改。 若要升级 UE-V Agent，请在用户的计算机上运行 UE-V Agent 安装程序包（AgentSetup.exe、AgentSetupx86.msi 或 AgentSetupx64.msi）。

**注意**  
升级 UE-V Agent 时，必须使用安装了以前的 UE-V Agent 的同一安装程序类型（.exe 文件或 .msi 数据包）。 例如，使用 UE-V 2 AgentSetup.exe 升级使用 AgentSetup.exe 安装的 UE-V 1.0 代理。



当代理安装程序运行时，将保留以下配置：

-   设置存储路径

-   注册表设置

-   计划任务（间隔设置被重置为默认值）

**注意**  
具有 UE-V 2 个设置位置模板的计算机，这些位置模板在 UE-V 1.0 代理中注册了 Windows 事件日志中的错误。



你可以使用 Microsoft System Center 2012 Configuration Manager 或其他企业版软件分发工具自动执行并分发 UE-V Agent 升级。

**建议：** 我们建议你升级计算环境中的所有 UE-V 1.0 代理，但这不是必需的。 UE-V 2. x 设置位置模板可以与 UE-V 1.0 代理交互，因为它们仅共享设置存储路径中的设置。 但是，我们建议你将部署移动到单个代理版本以简化管理并支持 UE-V。

### 升级失败后修复 UE-V Agent

在尝试下列操作之一后，可能会遇到错误：

-   从 UE-V 1.0 升级到 UE-V 2

-   升级到较新版本的 Windows，例如从 Windows 7 升级到 Windows 8 或从 Windows 8 升级到 Windows 8.1。

-   升级 UE-V Agent 后卸载代理

若要解决任何问题，请尝试通过在安装了代理的计算机上的命令提示符处输入此命令来修复 UE-V Agent。

``` syntax
msiexec.exe /f "<path to msi file>" /quiet /norestart /l*v "%temp%\UE-VAgentInstaller.log
```

然后，你可以通过安装较新版本的 UE-V Agent 重试卸载过程或升级。






## 相关主题


[准备 UE-V 2. x 部署](prepare-a-ue-v-2x-deployment-new-uevv2.md)

[部署自定义应用程序的 UE-V 2。](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)









