---
title: App-V Client 注册表值
description: App-V Client 注册表值
author: dansimp
ms.assetid: 46af5209-9762-47b9-afdb-9a2947e013f7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 05cd807ff9882bc478aca07abc4a28cdea83086a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802364"
---
# App-V Client 注册表值


Microsoft Application Virtualization （App-v）客户端将其配置存储在注册表中。 如果你了解注册表中的数据的格式，则可以收集有关客户端的一些有用信息。 您也可以通过更改注册表项来配置多个客户端操作。 本主题列出了所有应用程序虚拟化（app-v）客户端注册表项并解释其用法。

**重要提示**  
在运行64位操作系统的计算机上，以下部分中所述的键和值将在 HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\Client. 下。



## 配置键


下表提供了与 HKEY _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration 键相关联的注册表值的相关信息。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名称</th>
<th align="left">类型</th>
<th align="left">数据（示例）</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>ProductName</p></td>
<td align="left"><p>字符串</p></td>
<td align="left"><p>Microsoft Application Virtualization 桌面客户端</p></td>
<td align="left"><p>请勿修改。</p></td>
</tr>
<tr class="even">
<td align="left"><p>版本 </p></td>
<td align="left"><p>字符串 </p></td>
<td align="left"><p>4.5.0.xxx </p></td>
<td align="left"><p>请勿修改。 </p></td>
</tr>
<tr class="odd">
<td align="left"><p>驱动程序 </p></td>
<td align="left"><p>字符串 </p></td>
<td align="left"><p>Sftfs.sys </p></td>
<td align="left"><p>如果此项值存在，则它包含上次启动内核时导致停止错误的驱动程序的名称。 修复错误修复后，必须删除此项值，以便 sftlist 可以启动。</p></td>
</tr>
<tr class="even">
<td align="left"><p>InstallPath </p></td>
<td align="left"><p>字符串 </p></td>
<td align="left"><p>Default = C:\Program Files\Microsoft Application Virtualization 客户端</p></td>
<td align="left"><p>客户端的安装位置。 请勿修改。 </p></td>
</tr>
<tr class="odd">
<td align="left"><p>LogFileName </p></td>
<td align="left"><p>字符串 </p></td>
<td align="left"><p>默认值 = CSIDL_COMMON_APPDATA \Microsoft\Application 虚拟化 Client\sftlog.txt</p></td>
<td align="left"><p>客户端日志文件的路径和名称。</p>
<div class="alert">
<strong>注意</strong><br/><p>如果你运行的版本比 App-v 4.6、SP1 更早，而你修改了日志文件的名称或位置，则必须重新启动 sftlist 服务才能使更改生效。</p>
</div>
<div>

</div>
<p></p></td>
</tr>
<tr class="even">
<td align="left"><p>LogMinSeverity </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>默认值 = 4，信息</p></td>
<td align="left"><p>控制将哪些消息写入日志。 该值指示所记录内容的阈值，即记录小于或等于该值的所有内容。 例如，值0x3 （警告）表示记录警告（0x3）、错误（0x2）和严重错误（0x1）。</p>
<p>值范围： 0x0 = None，0x1 = 严重，0x2 = 错误，0x3 = Warning，0x4 = 信息（默认值），0x5 = Verbose。</p>
<p>日志级别可通过应用程序虚拟化（app-v）客户端控制台和命令提示符进行配置。 在命令提示符处，命令 sftlist.exe/verboselog 会将日志级别增加到详细。 有关命令行详细信息的详细信息，请参阅</p>
<p><a href="https://go.microsoft.com/fwlink/?LinkId=141467https://go.microsoft.com/fwlink/?LinkId=141467" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=141467https://go.microsoft.com/fwlink/?LinkId=141467">https://go.microsoft.com/fwlink/?LinkId=141467https://go.microsoft.com/fwlink/?LinkId=141467</a></p>
<p>.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>LogRolloverCount</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 4</p></td>
<td align="left"><p>定义在重置时保留的日志文件的备份副本数。 有效范围为0到9999。 默认值为4。 值0表示将不保留任何副本。</p></td>
</tr>
<tr class="even">
<td align="left"><p>LogMaxSize</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 256</p></td>
<td align="left"><p>定义在重置之前日志文件可以增长的最大大小（以兆字节（MB）为单位）。 默认大小为 256 MB。 达到此大小时，将在下次写入尝试时强制重置日志。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>SystemEventLogLevel</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 0x4 （App-v 4.5）</p>
<p>默认值 = 0x3 （App-v 4.6）</p></td>
<td align="left"><p>指示日志消息写入 NT 事件日志的日志记录级别。 该值指示所记录内容的阈值，即记录的所有内容都等于或小于该值。 例如，值0x3 （警告）表示记录警告（0x3）、错误（0x2）和严重错误（0x1）。</p>
<p>值范围</p>
<p>0x0 = None</p>
<p>0x1 = 严重</p>
<p>0x2 = 错误</p>
<p>0x3 = 警告</p>
<p>0x4 = 信息（默认值）</p>
<p>0x5 = 详细</p></td>
</tr>
<tr class="even">
<td align="left"><p>AllowIndependentFileStreaming</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 0</p></td>
<td align="left"><p>指示是否将启用来自文件的流，无论客户端是否已配置了 APPLICATIONSOURCEROOT 参数。 如果设置为 FALSE，则传输将不会启用来自文件的流处理，即使 OSD HREF 或 APPLICATIONSOURCEROOT 参数包含文件路径也是如此。</p>
<p>0x0 = False （默认值）</p>
<p>0x1 = True</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ApplicationSourceRoot</p></td>
<td align="left"><p>字符串</p></td>
<td align="left"><p>rtsps://mainserver:322/prodapps</p>
<p><a href="https://mainserver:443/prodapps" data-raw-source="https://mainserver:443/prodapps">https://mainserver:443/prodapps</a></p>
<p>文件：//\uncserver\share\prodapps</p>
<p>文件：//\uncserver\share</p></td>
<td align="left"><p>支持管理员或电子软件分发（ESD）系统，确保根据拓扑管理方案执行应用程序加载。 使用此关键字值替代应用程序的 HREF 元素（例如，源位置）的 OSD 基本代码。 应用程序源根目录支持 Url 和通用命名约定（UNC）路径格式。</p>
<p>URL 路径的正确格式为 protocol：/id： [port] [/path] [/]，其中 port 和 path 是可选的。 如果未指定端口，则使用协议的默认端口。 仅替换了 OSD URL 的协议：//server：端口部分。 </p>
<p>UNC 路径的正确格式为 \computername\sharefolder [folder] []，其中文件夹是可选的。 计算机名可以是完全限定的域名（FQDN）或 IP 地址，sharefolder 可以是驱动器号。 仅替换 OSD 路径的 \computername\sharefolder 或驱动器号部分。 </p></td>
</tr>
<tr class="even">
<td align="left"><p>OSDSourceRoot</p></td>
<td align="left"><p>字符串</p></td>
<td align="left"><p>\computername\sharefolder\resource</p>
<p>\computername\content</p>
<p>C:\foldername</p>
<p><a href="http://computername/productivity/" data-raw-source="http://computername/productivity/">http://computername/productivity/</a></p>
<p><a href="https://computername/productivity/" data-raw-source="https://computername/productivity/">https://computername/productivity/</a></p></td>
<td align="left"><p>允许管理员为发布期间的序列化应用程序包指定 OSD 文件检索的源位置。 OSDSourceRoot 的可接受格式包括 UNC 路径和 Url （http 或 https）。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>IconSourceRoot</p></td>
<td align="left"><p>字符串</p></td>
<td align="left"><p>\computername\sharefolder\resource</p>
<p>\computername\content</p>
<p>C:\foldername</p>
<p><a href="http://computername/productivity/" data-raw-source="http://computername/productivity/">http://computername/productivity/</a></p>
<p><a href="https://computername/productivity/" data-raw-source="https://computername/productivity/">https://computername/productivity/</a></p></td>
<td align="left"><p>允许管理员为发布期间的序列化应用程序包指定图标文件检索的源位置。 IconSourceRoot 的可接受格式包括 UNC 路径和 Url （http 或 https）。</p></td>
</tr>
<tr class="even">
<td align="left"><p>AutoLoadTriggers</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 5</p></td>
<td align="left"><p>AutoLoad 是一种客户端运行时策略配置参数，可使虚拟化应用程序的辅助功能块在后台自动流式传输到客户端。 AutoLoad 触发器是标志，用于指示启动应用程序自动加载的事件。 AutoLoad 隐式使用后台流，使应用程序能够完全加载到缓存中。 将首先加载主功能块，并将在后台加载剩余的功能块以启用前台操作，例如用户与应用程序交互，并提供最佳的感知性能。</p>
<p>位掩码值：</p>
<p>（0）从不：未设置任何位（值为0），不会执行自动加载，因为没有设置触发器。</p>
<p>（1） OnLaunch：当用户启动应用程序时开始加载。</p>
<p>（2） OnRefresh：发布应用程序时开始加载。 只要添加或更新软件包记录（例如，当发生发布刷新时），就会发生这种情况。</p>
<p>（4） OnLogin：用户登录时开始加载。</p>
<p>（5） OnLaunch 和 OnLogin： Default。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>AutoLoadTarget</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 1</p></td>
<td align="left"><p>指示在任何给定的 AutoLoad 触发器出现时将自动加载的内容。 位掩码值：</p>
<p>（0）无：不自动加载，无论可设置哪些触发器。</p>
<p>（1） PreviouslyUsed （默认值）：如果启用了任何 AutoLoad 触发器，则仅加载程序包中之前已使用过一个应用程序的程序包（即，已启动或 precached）。</p>
<p>（2）所有：如果启用了任何 AutoLoad 触发器，程序包中的所有应用程序（每个程序包）或所有程序包（为客户端设置）将自动加载，无论它们是否已启动。</p></td>
</tr>
<tr class="even">
<td align="left"><p>RequireAuthorizationIfCached</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 1</p></td>
<td align="left"><p>指示始终需要授权，无论应用程序是否已在缓存中。 可能值：</p>
<p>0 = False：始终尝试连接到服务器。 如果无法建立与服务器的连接，客户端仍允许用户启动以前加载到缓存中的应用程序。</p>
<p>1 = True （默认值）：应用程序始终必须在启动时获得授权。 对于 RTSP 流处理应用程序，将向服务器发送用户授权令牌以进行授权。 对于基于文件的应用程序，文件 Acl 控制用户是否可以访问应用程序。</p>
<p>重新启动 sftlist 服务以使更改生效。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>UserDataDirectory </p></td>
<td align="left"><p>字符串 </p></td>
<td align="left"><p>APPDATA</p></td>
<td align="left"><p>存储图标缓存和用户设置的位置。</p></td>
</tr>
<tr class="even">
<td align="left"><p>GlobalDataDirectory </p></td>
<td align="left"><p>字符串 </p></td>
<td align="left"><p>C:\Users\Public\Documents </p></td>
<td align="left"><p>用于全局 App-v 数据的目录，包括用于 OSD 文件、图标文件、快捷方式信息和 SystemGuard 资源（如 .ini 文件）的缓存。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>AllowCrashes </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>0 或 1 </p></td>
<td align="left"><p>默认值 = 0：值0表示客户端尝试捕获内部程序异常，以便其他用户应用程序可以在发生崩溃时恢复和继续。 值1表示客户端允许出现内部程序异常，以便可以在调试程序中捕获它们。</p></td>
</tr>
<tr class="even">
<td align="left"><p>CoreInternalTimeout </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>60</p></td>
<td align="left"><p>内核和前端之间的内部 IPC 请求超时（以秒为单位）。 请勿修改。 </p></td>
</tr>
<tr class="odd">
<td align="left"><p>DefaultSuiteCombineTime </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>10</p></td>
<td align="left"><p>此值用于指示启动程序后不久，在同一套件中运行另一个应用程序时，不会生成任何错误消息。 </p></td>
</tr>
<tr class="even">
<td align="left"><p>SerializedSuiteLaunchTimeout </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>默认 = 60000</p></td>
<td align="left"><p>定义当尝试序列化程序在同一套件中启动时，客户端将等待的时间（以毫秒为单位）。 如果客户端超时，程序启动将继续，但不会序列化。 </p></td>
</tr>
<tr class="odd">
<td align="left"><p>ScriptTimeout </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>300</p></td>
<td align="left"><p>如果 WAIT = TRUE，则 OSD 文件中脚本的默认超时值（以秒为单位）。 你可以通过超时（而不是等待）指定每脚本超时。 值0表示无等待，0xFFFFFFFF 表示永久等待。 </p></td>
</tr>
<tr class="even">
<td align="left"><p>LaunchRecordLogPath </p></td>
<td align="left"><p>字符串 </p></td>
<td align="left"><p></p></td>
<td align="left"><p>如果在 HKLM 或 HKCU 下，此值包含日志文件的有效路径，SFTTray 将在程序启动、关闭、启动失败时写入此日志，进入或退出断开连接模式。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>LaunchRecordMask </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>0x1A （26）日志启动错误和断开模式进入和退出活动。</p>
<p>0x1F （31）记录所有内容。</p>
<p>0x0 （0）不记录任何内容。 </p></td>
<td align="left"><p>指定要记录的五个事件中的哪一个（位掩码值）：</p>
<p>1表示程序启动</p>
<p>2表示启动失败错误</p>
<p>4个用于关机</p>
<p>8用于进入断开连接模式</p>
<p>16用于退出断开连接模式以重新连接到服务器</p>
<p>添加这些号码的任意组合以打开各自的邮件。 如果注册表中不0x1F，则默认为 ""。 </p></td>
</tr>
<tr class="even">
<td align="left"><p>LaunchRecordWriteTimeout </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>默认 = 3000</p></td>
<td align="left"><p>指定在尝试写入启动记录日志时托盘将等待多长时间（如果另一个进程正在使用它）。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ImportSearchPath </p></td>
<td align="left"><p>字符串 </p></td>
<td align="left"><p>d:\files;C:\documents 和 settings\user1\SFTs </p></td>
<td align="left"><p>一个分号分隔的列表，其中列出了最多五个目录，可在提示用户选择目录之前搜索便携式 SFT 文件。 路径中的尾部反斜杠是可选的。 默认情况下，此值不存在，必须手动设置。</p></td>
</tr>
<tr class="even">
<td align="left"><p>UserImportPath</p></td>
<td align="left"><p>字符串 </p></td>
<td align="left"><p>D:\SFTs\ </p></td>
<td align="left"><p>仅在 HKCU 下有效。 查找程序包导入的 SFT 文件时用户浏览到的最后一个位置。 如果已成功找到 SFT，则自动设置。 当尝试自动查找 SFT 文件时，将在连续的导入中使用此功能。</p></td>
</tr>
</tbody>
</table>



## 共享密钥


HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Shared 键控制跨 app-v 组件共享的值。 下表提供了与共享密钥相关联的注册表值的相关信息。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名称 </th>
<th align="left">类型 </th>
<th align="left">数据（示例） </th>
<th align="left">描述 </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>DumpPath </p></td>
<td align="left"><p>字符串 </p></td>
<td align="left"><p>默认值 = C：\ </p></td>
<td align="left"><p>在异常上生成小型转储时创建转储文件的默认路径。 默认值为 C：\如果未指定，则为。 客户端安装程序将此密钥设置为 &lt; 应用虚拟化全局数据目录 &gt; \Dumps。 Sequencer 安装程序将此密钥设置为安装目录。 </p></td>
</tr>
<tr class="even">
<td align="left"><p>DumpPathSizeLimit </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>1000</p></td>
<td align="left"><p>指定可用于存储 minidumps 的磁盘空间的最大总数量（以 mb 为单位）。 默认值 = 1000 MB。</p></td>
</tr>
</tbody>
</table>



## 网络密钥


HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network 键控制各种与网络相关的参数。 此密钥主要由网络传输代理使用。 下表提供了与网络密钥相关联的注册表值的相关信息。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名称 </th>
<th align="left">类型 </th>
<th align="left">数据（示例） </th>
<th align="left">描述 </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Online</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 1</p></td>
<td align="left"><p>启用或禁用脱机模式。 如果设置为0，则客户端将不会与 App-v 管理服务器或发布服务器通信。 在断开连接的操作中，客户端可以启动加载的应用程序，即使它未连接到 app-v 管理服务器也是如此。 在脱机模式下，客户端不会尝试连接到 app-v 管理服务器或发布服务器。 您必须允许断开连接的操作能够脱机工作。 默认值为1（联机），并且0为 "已禁用" （脱机）。</p></td>
</tr>
<tr class="even">
<td align="left"><p>AllowDisconnectedOperation </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>默认值 = 1</p></td>
<td align="left"><p>启用或禁用断开连接的操作。 默认值为1，并且禁用0。 启用断开连接操作后，即使未连接到 App-v 管理服务器，App-v 客户端也可以启动加载的应用程序。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>FastConnectTimeout</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 1000</p></td>
<td align="left"><p>此值指定 TCP 连接超时值（以毫秒为单位），用于确定何时进入断开连接的操作模式。 此值可用于替代20秒的默认 ConnectTimeout （用于网络事务的 App-v connect 超时）或系统的 TCP 超时约25秒。 这会将客户端快速带入断开连接的操作模式。 在下一次连接时应用。</p></td>
</tr>
<tr class="even">
<td align="left"><p>LimitDisconnectedOperation</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 1 </p></td>
<td align="left"><p>仅适用于 AllowDisconnectedOperation 为1的情况下，"已启用"。 此值确定在断开连接的操作中允许客户端运行多长时间时是否会出现时间限制。 1 = 受限。 0 = 无限制。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>DOTimeoutMinutes</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 129600</p></td>
<td align="left"><p>指示在断开连接的操作模式下可以使用的应用程序的分钟数。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>有效值为 1-以分钟为单位的999999（1-1439998560 分钟）。 默认值为90天或129600分钟。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>协议</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 8</p></td>
<td align="left"><p>要使用的默认协议（TCP 与 SSL）。 在 "选项" 对话框中配置。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ReadTimeout</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>名</p></td>
<td align="left"><p>查看网络事务的超时时间（以秒为单位）。 请勿修改。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>WriteTimeout</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>名</p></td>
<td align="left"><p>为网络事务写超时（以秒为单位）。 请勿修改。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ConnectTimeout</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>名</p></td>
<td align="left"><p>为网络事务连接超时（以秒为单位）。 请勿修改。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ReestablishmentRetries</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>三维空间</p></td>
<td align="left"><p>尝试重新建立已删除会话的次数。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ReestablishmentInterval</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>岁</p></td>
<td align="left"><p>在尝试重新建立已删除的会话之间等待的秒数。</p></td>
</tr>
</tbody>
</table>



## Http 密钥


HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\Http 键控制与 Http 流相关的参数。 此密钥主要由网络传输代理使用。 下表提供了与 Http 密钥相关联的注册表值的相关信息。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名称 </th>
<th align="left">类型 </th>
<th align="left">数据（示例） </th>
<th align="left">描述 </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>LaunchIfNotFound</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 0</p></td>
<td align="left"><p>控制当与 http 服务器建立连接且该程序包文件不再存在于 HTTP 服务器上时 HTTP 流的行为。 如果值不存在或未设置为1，则 App-v 客户端不允许启动以前加载到缓存中的应用程序。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>raid-1</p></td>
<td align="left"><p>如果此值设置为1，则 App-v 客户端允许你启动以前加载到缓存中的应用程序。</p></td>
</tr>
</tbody>
</table>



## 文件系统密钥


HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS 键下包含的值控制 App-v 的文件系统参数。 下表提供了与 AppFS 键相关联的注册表值的相关信息。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名称 </th>
<th align="left">类型 </th>
<th align="left">数据（示例） </th>
<th align="left">描述 </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>FileSize </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>4096</p></td>
<td align="left"><p>文件系统缓存文件的最大大小（以 mb 为单位）。 如果在注册表中更改此值，则必须将状态设置为0，然后重新启动。 </p></td>
</tr>
<tr class="even">
<td align="left"><p>FileName </p></td>
<td align="left"><p>字符串 </p></td>
<td align="left"><p>C:\Users\Public\Documents\SoftGrid Client\sftfs.fsd </p></td>
<td align="left"><p>文件系统缓存文件的位置。 如果在注册表中更改此值，则必须将 FileSize 保留相同，然后重新启动或将状态设置为0，然后重新启动。 </p></td>
</tr>
<tr class="odd">
<td align="left"><p>DriveLetter </p></td>
<td align="left"><p>字符串 </p></td>
<td align="left"><p>问： </p></td>
<td align="left"><p>将挂载 app-v 文件系统的驱动器（如果可用）。 此值由侦听器或安装程序设置，并且由文件系统读取。 </p></td>
</tr>
<tr class="even">
<td align="left"><p>State </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>0x100 </p></td>
<td align="left"><p>文件系统的状态。 设置为0，然后重新启动以完全清除文件系统缓存。 </p></td>
</tr>
<tr class="odd">
<td align="left"><p>FileSystemStorage </p></td>
<td align="left"><p>字符串 </p></td>
<td align="left"><p>C:\Profiles\Joe\SG </p></td>
<td align="left"><p>Symlinks 的路径，在 HKCU 下设置。 请勿修改（使用 "配置" 下的 "数据目录" 更改）。 </p></td>
</tr>
<tr class="even">
<td align="left"><p>GlobalFileSystemStorage </p></td>
<td align="left"><p>字符串 </p></td>
<td align="left"><p>C:\Users\Public\Documents\SoftGrid Client\AppFS 存储 </p></td>
<td align="left"><p>全局文件系统数据的路径。 请勿修改。 </p></td>
</tr>
<tr class="odd">
<td align="left"><p>MaxPercentToLockInCache </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>默认值 = 90 </p></td>
<td align="left"><p>指定可锁定的文件系统缓存文件的最大百分比。 请勿修改。</p></td>
</tr>
<tr class="even">
<td align="left"><p>UnloadLeastRecentlyUsed</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 1</p></td>
<td align="left"><p>文件系统缓存空间管理功能使用最近最少使用的（LRU）算法，并且默认情况下处于启用状态。 如果新程序包所需的空间超过缓存中的可用空间，则 App-v 客户端使用此功能确定它可以从缓存中删除的现有程序包（如果有），以便为新程序包腾出空间。 如果上次访问日期比在 MinPkgAge 注册表值中指定的值旧，客户端将删除该程序包。 值为0（已禁用）和1（默认值，已启用）。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MinPackageAge</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>raid-1</p></td>
<td align="left"><p>若要确定何时可以选择要放弃的程序包，请将此注册表值设置为等于自上次访问程序包后所需的最小天数。 不会放弃最近使用过的程序包。</p></td>
</tr>
</tbody>
</table>



## 权限密钥


为了帮助防止用户犯错误，管理员可以使用 HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Permissions 键来控制对非管理用户的某些操作的访问权限，例如，防止用户意外卸载程序。 具有管理权限的用户可以提供任何这些权限。 在共享系统（如远程桌面会话主机（RD 会话主机）服务器（以前称为终端服务器）系统）上，在向用户授予额外权限时要小心，因为这些权限中的某些权限将允许用户控制系统上所有用户使用的应用程序。 这些设置的可能值为1（允许）和0（不允许）。

权限密钥设置控制启用命名操作的所有接口。 其中包括 "选项" 对话框、"SFTTray" 和 "SFTMime"。 这些设置不会影响管理员。 下表提供了与权限密钥相关联的注册表值的相关信息。

名称类型数据（示例）描述 ChangeFSDrive

DWORD

默认值 = 0

值1允许用户选择用作文件系统驱动器的其他驱动器号。

ChangeCacheSize

DWORD

默认值 = 0

值1允许用户更改缓存大小。

ChangeLogSettings

DWORD

默认值 = 0

值1允许用户修改日志级别、更改其位置，然后通过用户界面重置它。

AddApp

DWORD

默认值 = 0

值1允许用户显式添加应用程序。 这不会影响通过发布刷新添加的应用程序，也不会阻止用户启动（并因此隐式添加）尚未添加的应用程序。 值为0或1。

LoadApp 

DWORD 

0

不允许用户加载应用程序。 这是 RD 会话主机的默认值。 如果你是移动用户，你可能希望将应用程序中的应用程序完全加载到缓存中，以便在断开连接操作或脱机模式下使用它们。 若要从 app-v 管理服务器或 App-v 流式处理服务器流处理应用程序，必须连接到服务器才能加载应用程序。

raid-1

允许用户加载应用程序。 这是 Windows 桌面版的默认设置。 

UnloadApp 

DWORD 

0

不允许用户卸载应用程序。 加载或卸载程序包时，程序包中的所有应用程序都将加载到或从缓存中删除。

raid-1

允许用户卸载应用程序。 

LockApp 

DWORD 

0

不允许用户锁定和解除锁定应用程序。 这是 RD 会话主机的默认值。 无法从缓存中删除已锁定的应用程序，以便为新应用程序腾出空间。 若要从远程桌面服务（以前称为终端服务）缓存的 App-v 桌面或客户端删除已锁定的应用程序，必须解除锁定。

raid-1

允许用户锁定和解除锁定应用程序。 这是 Windows 桌面版的默认设置。 

ManageTypes 

DWORD 

0

不允许用户单独为该用户添加、编辑或删除文件类型关联。 这是 RD 会话主机的默认值。 

raid-1

允许用户仅为该用户添加、编辑和删除文件类型关联，而不是全局。 这是 Windows 桌面版的默认设置。 

RefreshServer 

DWORD 

0

不允许用户触发 MIME 设置的刷新。 这是 RD 会话主机的默认值。 

raid-1

允许用户触发 MIME 设置的刷新。 这是 Windows 桌面版的默认设置。 

UpdateOSDFile

DWORD

默认值 = 0

如果值为1，则用户可以使用已修改的 OSD 文件。

ImportApp 

DWORD 

0

不允许用户将应用程序导入到缓存中。 负载和导入之间的区别在于，当触发加载时，客户端从在 OSD、ASR 或替代 URL 中包含的当前配置位置获取程序包。 使用导入时，必须指定从中获取程序包的位置。 

raid-1

允许用户将应用程序导入到缓存中。 

ChangeRefreshSettings

DWORD

默认值 = 0

值1允许用户修改服务器的刷新设置（登录时刷新和定期刷新）。 这并不意味着用户可以修改其他服务器设置（路径、主机等）。

ManageServers

DWORD

默认值 = 0

如果值为1，则允许用户添加、编辑和删除服务器，除了编辑刷新设置（由 ChangeRefreshSettings 权限控制）之外。

PublishShortcut

DWORD

默认值 = 0

值1允许用户通过用户界面发布快捷方式。 这不会影响在发布刷新期间发布的快捷方式。

ViewAllApplications

DWORD

默认值 = 0

值1通过用户界面显示所有应用程序;否则，仅显示用户的应用程序。

RepairApp

DWORD

默认值 = 1

值1允许用户在 SFTMime 或客户端管理控制台中的应用程序上使用修复操作。 修复应用程序时，删除任何自定义用户设置并还原默认设置。 此操作不会更改或删除快捷方式或文件类型关联，也不会从缓存中删除应用程序。

ClearApp

DWORD

默认值 = 1

值1允许用户对 SFTMime 或客户端管理控制台中的应用程序使用清除操作。 从控制台中清除应用程序后，您将无法再使用该应用程序。 但是，应用程序仍保留在缓存中，并且在同一系统上仍可供其他用户使用。 在发布刷新后，已清除的应用程序将再次变为可用。

DeleteApp

DWORD

默认值 = 0

值1允许用户对 SFTMime 或客户端管理控制台中的应用程序使用删除操作。 删除应用程序时，所选应用程序将不再可用于该客户端上的任何用户。 将删除快捷方式和文件类型关联，并从缓存中删除应用程序。 但是，如果另一个应用程序引用文件系统缓存或所选应用程序的设置数据中的数据，这些项目将不会被删除。

在发布刷新后，已删除的应用程序将再次可供你使用。

ToggleOfflineMode

DWORD

值1允许用户选择以脱机模式运行客户端。 在脱机模式下，应用程序虚拟化客户端可以启动加载的应用程序，即使该应用程序未连接到应用程序虚拟化服务器。



## 自定义设置


HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\CustomSettings 键包含特定于前端组件的值。 所有自定义设置均存储为字符串。 下表提供了与 CustomSettings 键相关联的注册表值的相关信息。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名称 </th>
<th align="left">类型 </th>
<th align="left">数据（示例） </th>
<th align="left">描述 </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>TrayErrorDelay </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>默认值 = 30 </p></td>
<td align="left"><p>应用程序虚拟化通知区域将显示错误消息（如启动失败）的时间（以秒为单位） &quot; &quot; 。 1的最小值。 </p></td>
</tr>
<tr class="even">
<td align="left"><p>TraySuccessDelay </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>默认值 = 10 </p></td>
<td align="left"><p>Appvmed 通知区域将显示成功消息（如 &quot; Word 已启动 &quot; 或 &quot; Excel 关闭）的时间（以秒为单位） &quot; 。 如果为0，将禁止显示这些消息。 </p></td>
</tr>
<tr class="odd">
<td align="left"><p>TrayVisibility</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 0</p></td>
<td align="left"><p>0 = 在使用虚拟化应用程序时显示托盘。</p>
<p>1 = 始终显示托盘。</p>
<p>2 = 从不显示托盘。</p></td>
</tr>
<tr class="even">
<td align="left"><p>TrayShowRefresh</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p></p></td>
<td align="left"><p>当存在并设置为1值时，允许在任务栏菜单上显示菜单项刷新应用程序，并可供用户访问。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>TrayShowLoad</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p></p></td>
<td align="left"><p>当存在并设置为1值时，允许在任务栏菜单上显示菜单项加载应用程序，并可供用户访问。</p></td>
</tr>
</tbody>
</table>



## 报告设置


HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Reporting 键包含特定于 App-v 管理服务器的报告值。 下表提供了与报告密钥相关联的注册表值的相关信息。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名称 </th>
<th align="left">类型 </th>
<th align="left">数据（示例） </th>
<th align="left">描述 </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>DataCacheLimit</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 20</p></td>
<td align="left"><p>此值指定用于存储报告信息的 XML 缓存的最大大小（以兆字节（MB）为单位）。 大小应用于内存中的缓存。 达到限制时，日志文件将翻转。 添加新记录（列表的底部）时，将删除一个或多个最旧的记录（列表顶部），以腾出空间。 第一次出现时，将向客户端日志和事件日志中记录一条警告，直到缓存成功地清除传输并再次填充日志后，才会再次记录该警告。</p></td>
</tr>
<tr class="even">
<td align="left"><p>DataBlockSize</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 65536</p></td>
<td align="left"><p>此值指定在发布刷新时同时传输到服务器的最大大小（以字节为单位），以避免日志达到较大大小时的永久传输失败。 默认值为65536。 将报表数据传输到服务器时，将从缓存中删除一个应用程序记录块（小于或等于 XML 数据的块大小），并将其发送到服务器。 每个块都将具有常规客户端数据和全局包列表数据，这些数据将不会考虑到块大小计算;极大的程序包列表可能存在通过低带宽或不可靠的连接导致传输失败的可能性。</p></td>
</tr>
</tbody>
</table>



## 相关主题


[Application Virtualization Client 参考](application-virtualization-client-reference.md)









