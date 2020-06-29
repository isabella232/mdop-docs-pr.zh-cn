---
title: 关于 Client 配置设置
description: 关于 Client 配置设置
author: dansimp
ms.assetid: cc7ae28c-b2ac-4f68-b992-5ccdbd5316a4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 289f5b35ac223d488152ff7ee1f42b1cf50341df
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798671"
---
# 关于 Client 配置设置


Microsoft Application Virtualization （App-v）5.0 客户端将其配置存储在注册表中。 如果你了解注册表中的数据的格式，则可以收集有关客户端的一些有用信息。 您也可以通过更改注册表项来配置多个客户端操作。 本主题列出了 app-v 5.0 客户端配置设置并解释其用法。 你可以使用 PowerShell 修改客户端配置设置。 有关使用 PowerShell 和 App-v 5.0 的详细信息，请参阅[使用 Powershell 管理 app-v](administering-app-v-by-using-powershell.md)。

## <a href="" id="---------app-v-5-0-client-configuration-settings"></a> App-v 5.0 客户端配置设置


下表显示了有关 App-v 5.0 客户端配置设置的信息：

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">设置名称</th>
<th align="left">设置标志</th>
<th align="left">描述</th>
<th align="left">设置选项</th>
<th align="left">注册表项值</th>
<th align="left">已禁用策略状态键和值</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>PackageInstallationRoot</p></td>
<td align="left"><p>PACKAGEINSTALLATIONROOT</p></td>
<td align="left"><p>指定将安装所有新应用程序和更新的目录。</p></td>
<td align="left"><p>字符串</p></td>
<td align="left"><p>Streaming\PackageInstallationRoot</p></td>
<td align="left"><p>未写入策略值（与 "未配置" 相同）</p></td>
</tr>
<tr class="even">
<td align="left"><p>PackageSourceRoot</p></td>
<td align="left"><p>PACKAGESOURCEROOT</p></td>
<td align="left"><p>替代用于下载软件包内容的源位置。</p></td>
<td align="left"><p>字符串</p></td>
<td align="left"><p>Streaming\PackageSourceRoot</p></td>
<td align="left"><p>未写入策略值（与 "未配置" 相同）</p></td>
</tr>
<tr class="odd">
<td align="left"><p>AllowHighCostLaunch</p></td>
<td align="left"><p>不可用。</p></td>
<td align="left"><p>此设置控制是否在通过按流量计费的网络连接（例如，4G）连接的 Windows 8 计算机上启动虚拟化的应用程序。</p></td>
<td align="left"><p>True （已启用）;False （已禁用状态）</p></td>
<td align="left"><p>Streaming\AllowHighCostLaunch</p></td>
<td align="left"><p>0</p></td>
</tr>
<tr class="even">
<td align="left"><p>ReestablishmentRetries</p></td>
<td align="left"><p>不可用。</p></td>
<td align="left"><p>指定重试已删除的会话的次数。</p></td>
<td align="left"><p>整数（0-99）</p></td>
<td align="left"><p>Streaming\ReestablishmentRetries</p></td>
<td align="left"><p>未写入策略值（与 "未配置" 相同）</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ReestablishmentInterval</p></td>
<td align="left"><p>不可用。</p></td>
<td align="left"><p>指定尝试重新建立已删除会话之间的秒数。</p></td>
<td align="left"><p>整数（0-3600）</p></td>
<td align="left"><p>Streaming\ReestablishmentInterval</p></td>
<td align="left"><p>未写入策略值（与 "未配置" 相同）</p></td>
</tr>
<tr class="even">
<td align="left"><p>AutoLoad</p></td>
<td align="left"><p>AUTOLOAD</p></td>
<td align="left"><p>指定如何在特定计算机上使用 app-v 自动加载新程序包。</p></td>
<td align="left"><p>（0x0）无;（0x1）以前使用过的;（0x2） All</p></td>
<td align="left"><p>Streaming\AutoLoad</p></td>
<td align="left"><p>未写入策略值（与 "未配置" 相同）</p></td>
</tr>
<tr class="odd">
<td align="left"><p>LocationProvider</p></td>
<td align="left"><p>不可用。</p></td>
<td align="left"><p>指定 IAppvPackageLocationProvider 接口的兼容实现的 CLSID。</p></td>
<td align="left"><p>字符串</p></td>
<td align="left"><p>Streaming\LocationProvider</p></td>
<td align="left"><p>未写入策略值（与 "未配置" 相同）</p></td>
</tr>
<tr class="even">
<td align="left"><p>CertFilterForClientSsl</p></td>
<td align="left"><p>不可用。</p></td>
<td align="left"><p>指定证书存储中的有效证书的路径。</p></td>
<td align="left"><p>字符串</p></td>
<td align="left"><p>Streaming\CertFilterForClientSsl</p></td>
<td align="left"><p>未写入策略值（与 "未配置" 相同）</p></td>
</tr>
<tr class="odd">
<td align="left"><p>VerifyCertificateRevocationList</p></td>
<td align="left"><p>不可用。</p></td>
<td align="left"><p>在 steaming 使用 HTTPS 之前验证服务器证书吊销状态。</p></td>
<td align="left"><p>True （已启用）;False （已禁用状态）</p></td>
<td align="left"><p>Streaming\VerifyCertificateRevocationList</p></td>
<td align="left"><p>0</p></td>
</tr>
<tr class="even">
<td align="left"><p>SharedContentStoreMode</p></td>
<td align="left"><p>SHAREDCONTENTSTOREMODE</p></td>
<td align="left"><p>指定流式处理的程序包内容将不会保存到本地硬盘。</p></td>
<td align="left"><p>True （已启用）;False （已禁用状态）</p></td>
<td align="left"><p>Streaming\SharedContentStoreMode</p></td>
<td align="left"><p>0</p></td>
</tr>
<tr class="odd">
<td align="left"><p>名称</p>
<div class="alert">
<strong>注意</strong><br/><p>无法使用 AppvclientConfiguration cmdLet 修改此设置 <strong> </strong> 。 你必须使用 <strong> AppvPublishingServer </strong> cmdlet。</p>
</div>
<div>

</div></td>
<td align="left"><p>PUBLISHINGSERVERNAME</p></td>
<td align="left"><p>显示发布服务器的名称。</p></td>
<td align="left"><p>字符串</p></td>
<td align="left"><p>Publishing\Servers {serverId} \ FriendlyName</p></td>
<td align="left"><p>未写入策略值（与 "未配置" 相同）</p></td>
</tr>
<tr class="even">
<td align="left"><p>URL</p>
<div class="alert">
<strong>注意</strong><br/><p>无法使用 AppvclientConfiguration cmdLet 修改此设置 <strong> </strong> 。 你必须使用 <strong> AppvPublishingServer </strong> cmdlet。</p>
</div>
<div>

</div></td>
<td align="left"><p>PUBLISHINGSERVERURL</p></td>
<td align="left"><p>显示发布服务器的 URL。</p></td>
<td align="left"><p>字符串</p></td>
<td align="left"><p>Publishing\Servers {serverId} \ URL</p></td>
<td align="left"><p>未写入策略值（与 "未配置" 相同）</p></td>
</tr>
<tr class="odd">
<td align="left"><p>GlobalRefreshEnabled</p>
<div class="alert">
<strong>注意</strong><br/><p>无法使用 AppvclientConfiguration cmdLet 修改此设置 <strong> </strong> 。 你必须使用 <strong> AppvPublishingServer </strong> cmdlet。</p>
</div>
<div>

</div></td>
<td align="left"><p>GLOBALREFRESHENABLED</p></td>
<td align="left"><p>启用全局发布刷新（布尔值）</p></td>
<td align="left"><p>True （已启用）;False （已禁用状态）</p></td>
<td align="left"><p>Publishing\Servers{serverId}\GlobalEnabled</p></td>
<td align="left"><p>False</p></td>
</tr>
<tr class="even">
<td align="left"><p>GlobalRefreshOnLogon</p>
<div class="alert">
<strong>注意</strong><br/><p>无法使用 AppvclientConfiguration cmdLet 修改此设置 <strong> </strong> 。 你必须使用 <strong> AppvPublishingServer </strong> cmdlet。</p>
</div>
<div>

</div></td>
<td align="left"><p>GLOBALREFRESHONLOGON</p></td>
<td align="left"><p>在登录时触发全局发布刷新。 布尔</p></td>
<td align="left"><p>True （已启用）;False （已禁用状态）</p></td>
<td align="left"><p>Publishing\Servers{serverId}\GlobalLogonRefresh</p></td>
<td align="left"><p>False</p></td>
</tr>
<tr class="odd">
<td align="left"><p>GlobalRefreshInterval</p>
<div class="alert">
<strong>注意</strong><br/><p>无法使用 AppvclientConfiguration cmdLet 修改此设置 <strong> </strong> 。 你必须使用 <strong> AppvPublishingServer </strong> cmdlet。</p>
</div>
<div>

</div></td>
<td align="left"><p>GLOBALREFRESHINTERVAL  </p></td>
<td align="left"><p>使用 GlobalRefreshIntervalUnit 指定发布刷新间隔。 若要禁用程序包刷新，请选择 "0"。</p></td>
<td align="left"><p>整数（0-744</p></td>
<td align="left"><p>Publishing\Servers{serverId}\GlobalPeriodicRefreshInterval</p></td>
<td align="left"><p>0</p></td>
</tr>
<tr class="even">
<td align="left"><p>GlobalRefreshIntervalUnit</p>
<div class="alert">
<strong>注意</strong><br/><p>无法使用 AppvclientConfiguration cmdLet 修改此设置 <strong> </strong> 。 你必须使用 <strong> AppvPublishingServer </strong> cmdlet。</p>
</div>
<div>

</div></td>
<td align="left"><p>GLOBALREFRESHINTERVALUNI</p></td>
<td align="left"><p>指定间隔单位（小时0-23，第0-31 天）。 </p></td>
<td align="left"><p>0表示小时，1表示天</p></td>
<td align="left"><p>Publishing\Servers{serverId}\GlobalPeriodicRefreshIntervalUnit</p></td>
<td align="left"><p>raid-1</p></td>
</tr>
<tr class="odd">
<td align="left"><p>UserRefreshEnabled</p>
<div class="alert">
<strong>注意</strong><br/><p>无法使用 AppvclientConfiguration cmdLet 修改此设置 <strong> </strong> 。 你必须使用 <strong> AppvPublishingServer </strong> cmdlet。</p>
</div>
<div>

</div></td>
<td align="left"><p>USERREFRESHENABLED </p></td>
<td align="left"><p>启用用户发布刷新（布尔值）</p></td>
<td align="left"><p>True （已启用）;False （已禁用状态）</p></td>
<td align="left"><p>Publishing\Servers{serverId}\UserEnabled</p></td>
<td align="left"><p>False</p></td>
</tr>
<tr class="even">
<td align="left"><p>UserRefreshOnLogon</p>
<div class="alert">
<strong>注意</strong><br/><p>无法使用 AppvclientConfiguration cmdLet 修改此设置 <strong> </strong> 。 你必须使用 <strong> AppvPublishingServer </strong> cmdlet。</p>
</div>
<div>

</div></td>
<td align="left"><p>USERREFRESHONLOGON</p></td>
<td align="left"><p>触发用户发布刷新 onlogon。 布尔</p>
<p>字数统计（带空格）：60</p></td>
<td align="left"><p>True （已启用）;False （已禁用状态）</p></td>
<td align="left"><p>Publishing\Servers{serverId}\UserLogonRefresh</p></td>
<td align="left"><p>False</p></td>
</tr>
<tr class="odd">
<td align="left"><p>UserRefreshInterval</p>
<div class="alert">
<strong>注意</strong><br/><p>无法使用 AppvclientConfiguration cmdLet 修改此设置 <strong> </strong> 。 你必须使用 <strong> AppvPublishingServer </strong> cmdlet。</p>
</div>
<div>

</div></td>
<td align="left"><p>USERREFRESHINTERVAL     </p></td>
<td align="left"><p>使用 UserRefreshIntervalUnit 指定发布刷新间隔。 若要禁用程序包刷新，请选择 "0"。</p>
<p>字数统计（带空格）：85</p></td>
<td align="left"><p>整数（0-744 小时）</p></td>
<td align="left"><p>Publishing\Servers{serverId}\UserPeriodicRefreshInterval</p></td>
<td align="left"><p>0</p></td>
</tr>
<tr class="even">
<td align="left"><p>UserRefreshIntervalUnit</p>
<div class="alert">
<strong>注意</strong><br/><p>无法使用 AppvclientConfiguration cmdLet 修改此设置 <strong> </strong> 。 你必须使用 <strong> AppvPublishingServer </strong> cmdlet。</p>
</div>
<div>

</div></td>
<td align="left"><p>USERREFRESHINTERVALUNIT  </p></td>
<td align="left"><p>指定间隔单位（小时0-23，第0-31 天）。 </p></td>
<td align="left"><p>0表示小时，1表示天</p></td>
<td align="left"><p>Publishing\Servers{serverId}\UserPeriodicRefreshIntervalUnit</p></td>
<td align="left"><p>raid-1</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MigrationMode</p></td>
<td align="left"><p>MIGRATIONMODE</p></td>
<td align="left"><p>迁移模式允许 App-v 客户端修改使用早期版本的 App-v 创建的程序包的快捷方式和 FTA。</p></td>
<td align="left"><p>True （已启用状态）;False （已禁用状态）</p></td>
<td align="left"><p>Coexistence\MigrationMode</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>CEIPOPTIN</p></td>
<td align="left"><p>CEIPOPTIN</p></td>
<td align="left"><p>允许运行 app-v 5.0 客户端的计算机收集并返回某些使用信息，以帮助我们进一步改进应用程序。</p></td>
<td align="left"><p>0表示已禁用;1表示已启用</p></td>
<td align="left"><p>软件/Microsoft/AppV/CEIP/CEIPEnable</p></td>
<td align="left"><p>0</p></td>
</tr>
<tr class="odd">
<td align="left"><p>EnablePackageScripts</p></td>
<td align="left"><p>ENABLEPACKAGESCRIPTS</p></td>
<td align="left"><p>支持在应运行的配置文件的程序包清单中定义的脚本。</p></td>
<td align="left"><p>True （已启用）;False （已禁用状态）</p></td>
<td align="left"><p>\Scripting\EnablePackageScripts</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>RoamingFileExclusions</p></td>
<td align="left"><p>ROAMINGFILEEXCLUSIONS</p></td>
<td align="left"><p>指定相对于% userprofile% 的文件路径，不要与用户&#39;s 配置文件一起漫游。 示例用法：/ROAMINGFILEEXCLUSIONS =&#39;桌面; 我的图片&#39;</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>RoamingRegistryExclusions</p></td>
<td align="left"><p>ROAMINGREGISTRYEXCLUSIONS</p></td>
<td align="left"><p>指定不与用户配置文件一起漫游的注册表路径。 示例用法：/ROAMINGREGISTRYEXCLUSIONS = software\classes; software\clients</p></td>
<td align="left"><p>字符串</p></td>
<td align="left"><p>Integration\RoamingRegistryExclusions</p></td>
<td align="left"><p>未写入策略值（与 "未配置" 相同）</p></td>
</tr>
<tr class="even">
<td align="left"><p>IntegrationRootUser</p></td>
<td align="left"><p>不可用。</p></td>
<td align="left"><p>指定创建与每用户已发布程序包的当前版本相关联的符号链接的位置。 所有虚拟应用程序扩展（例如快捷方式和文件类型关联）都将指向此路径。 如果不指定路径，则在发布包时不会使用符号链接。 例如：%localappdata%\Microsoft\AppV\Client\Integration。</p></td>
<td align="left"><p>字符串</p></td>
<td align="left"><p>Integration\IntegrationRootUser</p></td>
<td align="left"><p>未写入策略值（与 "未配置" 相同）</p></td>
</tr>
<tr class="odd">
<td align="left"><p>IntegrationRootGlobal</p></td>
<td align="left"><p>不可用。</p></td>
<td align="left"><p>指定创建与全局发布的程序包的当前版本相关联的符号链接的位置。 所有虚拟应用程序扩展（例如快捷方式和文件类型关联）都将指向此路径。 如果不指定路径，则在发布包时不会使用符号链接。 例如：%allusersprofile%\Microsoft\AppV\Client\Integration</p></td>
<td align="left"><p>字符串</p></td>
<td align="left"><p>Integration\IntegrationRootGlobal</p></td>
<td align="left"><p>未写入策略值（与 "未配置" 相同）</p></td>
</tr>
<tr class="even">
<td align="left"><p>VirtualizableExtensions</p></td>
<td align="left"><p>不可用。</p></td>
<td align="left"><p>可用于确定本地安装的应用程序是否可以在虚拟环境中运行的文件扩展名的逗号分隔列表。</p>
<p>在发布期间创建快捷方式、FTAs 和其他扩展点时，如果与扩展点关联的应用程序在本地安装，则 App-v 会将文件扩展名与列表进行比较。 如果扩展已找到，则 <strong> </strong> 将添加 RunVirtual 命令行参数，并且应用程序将完全运行。</p>
<p>有关 RunVirtual 参数的详细 <strong> 信息 </strong> ，请参阅 <a href="running-a-locally-installed-application-inside-a-virtual-environment-with-virtualized-applications.md" data-raw-source="[Running a Locally Installed Application Inside a Virtual Environment with Virtualized Applications](running-a-locally-installed-application-inside-a-virtual-environment-with-virtualized-applications.md)"> 在虚拟环境中使用虚拟化的应用程序运行本地安装的应用程序 </a> 。</p></td>
<td align="left"><p>字符串</p></td>
<td align="left"><p>Integration\VirtualizableExtensions</p></td>
<td align="left"><p>策略值未写入</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ReportingEnabled</p></td>
<td align="left"><p>不可用。</p></td>
<td align="left"><p>使客户端能够将信息返回到报表服务器。</p></td>
<td align="left"><p>True （已启用）;False （已禁用状态）</p></td>
<td align="left"><p>Reporting\EnableReporting</p></td>
<td align="left"><p>False</p></td>
</tr>
<tr class="even">
<td align="left"><p>ReportingServerURL</p></td>
<td align="left"><p>不可用。</p></td>
<td align="left"><p>指定报表服务器上保存客户端信息的位置。</p></td>
<td align="left"><p>字符串</p></td>
<td align="left"><p>Reporting\ReportingServer</p></td>
<td align="left"><p>未写入策略值（与 "未配置" 相同）</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ReportingDataCacheLimit</p></td>
<td align="left"><p>不可用。</p></td>
<td align="left"><p>指定用于存储报告信息的 XML 缓存的最大大小（以兆字节（MB）为单位）。 大小应用于内存中的缓存。 达到限制时，日志文件将翻转。 在0和1024之间设置。</p></td>
<td align="left"><p>Integer [0-1024]</p></td>
<td align="left"><p>Reporting\DataCacheLimit</p></td>
<td align="left"><p>未写入策略值（与 "未配置" 相同）</p></td>
</tr>
<tr class="even">
<td align="left"><p>ReportingDataBlockSize</p></td>
<td align="left"><p>不可用。</p></td>
<td align="left"><p>指定用于报告上载请求的服务器传输到服务器的最大大小（以字节为单位）。 这有助于避免在日志达到较大大小时出现永久性传输故障。 设置为1024和无限制。</p></td>
<td align="left"><p>Integer [1024-无限]</p></td>
<td align="left"><p>Reporting\DataBlockSize</p></td>
<td align="left"><p>未写入策略值（与 "未配置" 相同）</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ReportingStartTime</p></td>
<td align="left"><p>不可用。</p></td>
<td align="left"><p>指定启动客户端以将数据发送到报告服务器的时间。 你必须在0-23 之间指定一个有效的整数，对应于一天中的小时。 默认情况下， <strong> ReportingStartTime </strong> 将在当前日期的10个第 M 个、第 M 个或第22天开始。</p>
<div class="alert">
<strong>注意</strong><br/><p>当运行 App-v 5.0 客户端的计算机最有可能处于离线状态时，应将此设置配置为一个时间。</p>
</div>
<div>

</div></td>
<td align="left"><p>整数（0–23）</p></td>
<td align="left"><p>报告 \ 开始</p></td>
<td align="left"><p>未写入策略值（与 "未配置" 相同）</p></td>
</tr>
<tr class="even">
<td align="left"><p>ReportingInterval</p></td>
<td align="left"><p>不可用。</p></td>
<td align="left"><p>指定客户端将用于向报告服务器重新发送数据的重试间隔。</p></td>
<td align="left"><p>整型</p></td>
<td align="left"><p>Reporting\RetryInterval</p></td>
<td align="left"><p>未写入策略值（与 "未配置" 相同）</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ReportingRandomDelay</p></td>
<td align="left"><p>不可用。</p></td>
<td align="left"><p>指定发送到报告服务器的数据的最大延迟（以分钟为单位）。 当计划任务启动时，客户端会在0和 ReportingRandomDelay 之间生成一个随机延迟， <strong> </strong> 并在发送数据之前等待指定的持续时间。 这有助于防止服务器冲突。</p></td>
<td align="left"><p>Integer [0-ReportingRandomDelay]</p></td>
<td align="left"><p>Reporting\RandomDelay</p></td>
<td align="left"><p>未写入策略值（与 "未配置" 相同）</p></td>
</tr>
<tr class="even">
<td align="left"><p>EnableDynamicVirtualization</p>
<div class="alert">
<strong>重要提示</strong><br/><p>此设置仅适用于 app-v 5.0 SP2 或更高版本。</p>
</div>
<div>

</div></td>
<td align="left"><p>不可用。</p></td>
<td align="left"><p>启用要虚拟化并与虚拟应用程序一起运行的受支持的 Shell 扩展、浏览器帮助程序对象和 Active X 控件。</p></td>
<td align="left"><p>1（已启用），0（已禁用）</p></td>
<td align="left"><p>HKEY_LOCAL_MACHINE \Software\Microsoft\AppV\Client\Virtualization</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>EnablePublishingRefreshUI</p>
<div class="alert">
<strong>重要提示</strong><br/><p>此设置仅适用于 app-v 5.0 SP2。</p>
</div>
<div>

</div></td>
<td align="left"><p>不可用。</p></td>
<td align="left"><p>为运行 app-v 5.0 客户端的计算机启用发布刷新进度栏。</p></td>
<td align="left"><p>1（已启用），0（已禁用）</p></td>
<td align="left"><p>HKEY_LOCAL_MACHINE \Software\Microsoft\AppV\Client\Publishing</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>HideUI</p>
<div class="alert">
<strong>重要提示</strong><br/><p>此设置仅适用于 app-v 5.0 SP2。</p>
</div>
<div>

</div></td>
<td align="left"><p>不可用。</p></td>
<td align="left"><p>隐藏发布刷新进度栏。</p></td>
<td align="left"><p>1（已启用），0（已禁用）</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>ProcessesUsingVirtualComponents</p></td>
<td align="left"><p>不可用。</p></td>
<td align="left"><p>指定处理路径（可能包含通配符）的列表，这些路径是使用动态虚拟化（支持的 shell 扩展、浏览器帮助程序对象和 ActiveX 控件）的候选对象。 只有其完整路径与其中一个项目相匹配的进程才能使用动态虚拟化。</p></td>
<td align="left"><p>字符串</p></td>
<td align="left"><p>Virtualization\ProcessesUsingVirtualComponents</p></td>
<td align="left"><p>空字符串。</p></td>
</tr>
</tbody>
</table>








## 相关主题


[部署 App-V 5.0 Sequencer 和 Client](deploying-the-app-v-50-sequencer-and-client.md)

[如何使用 ADMX 模板和组策略修改 App-V 5.0 Client 配置](how-to-modify-app-v-50-client-configuration-using-the-admx-template-and-group-policy.md)

[如何部署 App-V Client](how-to-deploy-the-app-v-client-gb18030.md)









