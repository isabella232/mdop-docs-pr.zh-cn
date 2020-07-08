---
title: App-V 5.1 发行说明
description: App-V 5.1 发行说明
author: dansimp
ms.assetid: 62c5be3b-0a46-4512-93ed-97c23184f343
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 09/26/2016
ms.openlocfilehash: 7437a16bc10b21bb15b0f8307c2711177e78cb72
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798263"
---
# App-V 5.1 发行说明


以下是 Microsoft Application Virtualization （App-v）5.1 中的已知问题。

## 在 Windows 10 上的 App-v 5.0 SP3 管理服务器和 App-v 5.1 客户端之间的发布刷新期间出现错误


将程序包从 App-v 5.0 SP3 管理服务器同步到 Windows 10 上的 App-v 5.1 客户端时，将在发布刷新期间生成错误。 出现此错误的原因是，app-v 5.0 SP3 服务器不理解发布 URL 中指定的 Windows 10 操作系统。 此问题适用于 app-v 5.1 发布服务器，但不适用于 app-v 5.0 SP3 或更早版本的 backported。

**解决方法**：将 App-v 5.0 管理服务器升级到适用于 Windows 10 客户端的 App-v 5.1 管理服务器。

## 如果使用 App-v 5.1 Server 进行设置，则不会为将在全局发布的程序包应用自定义配置


如果将程序包分配给包含计算机帐户的 AD 组，并使用 App-v 服务器将自定义配置应用到该组，则不会将自定义配置应用到这些计算机。 App-v 5.1 客户端将在全局范围内发布分配给计算机帐户的程序包。 但是，它会在每个用户的配置文件中存储每个用户的自定义配置文件。 全局发布的程序包将无法访问此自定义配置。

**解决方法**：执行下列操作之一：

-   将程序包分配给仅包含用户帐户的组。 这将确保程序包的自定义配置将存储在每个用户的配置文件中，并且将正确应用。

-   创建自定义部署配置文件，并将其应用于客户端上的程序包，并将 AppvClientPackage cmdlet 与-DynamicDeploymentConfiguration 参数结合使用。 有关详细信息，请参阅[关于 App-V 5.1 动态配置](about-app-v-51-dynamic-configuration.md)。

-   使用 App-v 5.1 Sequencer 创建具有自定义配置的新程序包。

## 在新应用-V 5.1 服务器安装后未删除的服务器文件


如果卸载 V 5.0 SP1 服务器，然后安装 app-v 5.1 服务器，安装将失败，安装的管理服务器版本不正确，并返回错误消息。 出现此问题的原因是，卸载 app-v 5.0 SP1 时未删除服务器文件，因此安装过程将执行升级而不是全新安装。

**解决方法**：在开始安装 app-v 5.1 之前删除此注册表项：

在 "HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Wow6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall" 下，找到并删除包含 "Microsoft Application Virtualization （app-v）服务器" 值数据的 DWORD 值 "DisplayName" 的安装 GUID 注册表项。 这是唯一应删除的键。

## 手动添加的文件类型关联未正确保存


使用应用程序升级向导末尾的 "快捷方式" 和 "FTAs" 选项卡手动添加到应用程序包中的文件类型关联不会正确保存。 当再次更新已保存的程序包时，应用程序或 Sequencer 将无法使用它们。

**解决方法**：若要添加文件类型关联，请打开要修改的程序包，然后运行 "更新向导"。 在安装步骤中，通过操作系统添加新的文件类型关联。 Sequencer 将检测系统注册表中的新关联，并将其添加到程序包的虚拟注册表，该关联将可用于客户端。

## 将共享内容存储（SCS）模式中的流包添加到同时使用 AppLocker 托管的客户端时，会将其他数据写入本地磁盘。


若要减少写入客户端本地磁盘的数据量，可以在 App-v 5.1 客户端上启用 SCS 模式，以根据需要流式处理程序包的内容。 但是，如果 AppLocker 在程序包中管理应用程序，则某些数据可能会写入到不会被写入的客户端本地磁盘中。

**解决方法**：无

## 在 "管理控制台添加程序包" 对话框中，使用 Chrome 或 Firefox 时，"浏览" 按钮不可用


在管理控制台的 "程序包" 页面上，如果在右下角单击 "**添加" 或 "升级**"，将显示 "**添加程序包**" 对话框。 如果您使用 Chrome 或 Firefox 作为浏览器访问管理控制台，您将无法浏览到程序包的位置。

**解决方法**：在 "**添加包**" 输入字段中键入或复制并粘贴程序包的路径。 如果管理控制台有权访问此路径，你将能够添加程序包。 如果程序包位于网络共享位置，则可以通过执行以下步骤浏览到使用文件资源管理器的位置：

1.  按**Shift**的同时，右键单击软件包文件

2.  选择 "**复制为路径**"

3.  将路径粘贴到 "**添加包**" 对话框输入字段

## <a href="" id="upgrading-app-v-management-server-to-5-1-sometimes-fails-with-the-message--a-database-error-occurred-"></a>将 App-v 管理服务器升级到5.1 有时会失败，并出现消息 "数据库出错"


如果安装了 app-v 5.0 SP1 管理服务器，然后尝试升级到 app-v 5.1 服务器，当配置和启用多个连接组时，将显示以下错误： "数据库出错。 原因： "列名称" PackageOptional "无效。 无效的列名称 "VersionOptional"。 "

**解决方法**：在 SQL 数据库上运行此命令：

`ALTER TABLE AppVManagement.dbo.PackageGroupMembers ADD PackageOptional bit NOT NULL DEFAULT 0, VersionOptional bit NOT NULL DEFAULT 0`

其中 "AppVManagement" 是数据库的名称。

## 如果添加或删除可选程序包，则用户无法打开用户发布的连接组中的程序包


在运行 RDS 客户端的环境中或每台计算机有多个并发用户的环境中，如果在连接组中添加或删除了可选程序包，则登录用户无法打开用户发布的连接组中的程序包中的应用程序。

**解决方法**：让用户注销，然后重新登录。

## 将连接组仅发布给用户时错误消息被错误地显示


当你运行 AppvClientConnectionGroup 时，将显示以下错误，即使仅将连接组发布给用户： "内部应用 V 集成错误：未针对用户集成程序包。 请确保程序包已添加到计算机并发布给用户。 "

**解决方法**：执行下列操作之一：

-   发布连接组中的所有程序包。

    如果正在修复的连接组具有缺失或不可用于用户的程序包（即，未在全局发布或向用户发布），则会出现此问题。 但是，如果所有连接组的程序包都可用，则修复将正常运行，因此请确保发布所有程序包。

-   使用 AppvClientPackage 命令（而不是 Repair AppvClientConnectionGroup 命令）单独修复程序包。

    确定哪些程序包对用户可用，然后对每个程序包运行 AppvClientPackage 命令一次。 使用 PowerShell cmdlet 执行以下操作：

    1.  获取连接组中的所有程序包。

    2.  检查是否每个程序包当前是否已发布。

    3.  如果程序包当前已发布，请在该程序包上运行 AppvClientPackage。

## Sequencer 中的图标未正确显示


修改 app-v 排序器中的程序包时，"快捷方式" 和 "文件类型关联" 选项卡中的图标不会正确显示。 如果图标的大小不是16x16 或32x32，则会出现此问题。

**解决方法**：仅使用16x16 或32x32 的图标。

## 管理数据库不再需要 InsertVersionInfo 脚本


晚于 app-v 5.0 SP3 的 App-v 管理数据库的版本不需要 InsertVersionInfo 脚本。

应根据[知识库文章 3031340](https://support.microsoft.com/kb/3031340)中的**步骤 2**更新权限。

**重要提示** 
在 app-v 5.0 SP3 之后的 app-v 版本中不需要**步骤 1** 。

 

## Microsoft Visual Studio 2012 不受支持


App-v 5.1 不支持 Visual Studio 2012。

**解决方法**：无

## 应用的应用程序文件名限制-V-V 排序器


App-v 5. x Sequencer 无法序列文件名与 "CO_ x" 匹配的应用 &lt; 程序 &gt; ，其中 x 是任何数字。 将生成错误0x8007139F。

**解决方法**：使用其他文件名

## 装入程序包时出现间歇性的 "找不到文件" 错误


有时，当装载程序包时，将生成 "找不到文件" （0x80070002）错误。 通常，当 App-v 包中的文件夹包含许多文件（即20K 或更多文件）时，会发生这种情况。 这可能导致流出的时间比预期长，并将生成 "找不到文件" 错误。

**解决方法**：从 HF06 开始，引入了新的注册表项以启用延长此超时周期。

<table>
<colgroup>
<col width="20%" />
<col width="80%" />
</colgroup>
<tbody>
<tr>
<td align="left">路径</td>
<td align="left">HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\AppV\Client\Streaming</td>
</tr>
<tr>
<td align="left">设置</td>
<td align="left">StreamResponseWaitTimeout</td>
</tr>
<tr>
<td align="left">Udt</td>
<td align="left">DWORD</td>
</tr>
<tr>
<td align="left">刻度</td>
<td align="left">秒</td>
</tr>
<tr>
<td align="left">默认值</td>
<td align="left">级<br />
<strong>注意 </strong> ：如果未定义注册表项或指定了值 = 5，则此值为默认值 &lt; 。
</td>
</tr>
</tbody>
</table>






## 相关主题


[关于 App-V 5.1](about-app-v-51.md)

 

 





