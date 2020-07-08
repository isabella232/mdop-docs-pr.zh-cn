---
title: 关于 Client 配置设置
description: 关于 Client 配置设置
author: dansimp
ms.assetid: 18bb307a-7eda-4dd6-a83e-6afaefd99470
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fb547eedf63bf165b1e8f5fd024839b3c2af3e4c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798672"
---
# 关于 Client 配置设置


Microsoft Application Virtualization （App-v）5.1 客户端将其配置存储在注册表中。 如果你了解注册表中的数据的格式，则可以收集有关客户端的一些有用信息。 您也可以通过更改注册表项来配置多个客户端操作。 本主题列出了 app-v 5.1 客户端配置设置并解释其用法。 你可以使用 PowerShell 修改客户端配置设置。 有关使用 PowerShell 和 App-v 5.1 的详细信息，请参阅[使用 PowerShell 管理 app-v 5.1](administering-app-v-51-by-using-powershell.md)。

## <a href="" id="---------app-v-5-1-client-configuration-settings"></a> App-v 5.1 客户端配置设置


下表显示了有关 App-v 5.1 客户端配置设置的信息：

|设置名称 | 设置标志 | 描述 | 设置选项 | 注册表项值 | 已禁用策略状态键和值 |
|-------------|------------|-------------|-----------------|--------------------|--------------------------------------|
| PackageInstallationRoot | PACKAGEINSTALLATIONROOT | 指定将安装所有新应用程序和更新的目录。 | 字符串 | Streaming\PackageInstallationRoot | 未写入策略值（与 "未配置" 相同） |
| PackageSourceRoot | PACKAGESOURCEROOT | 替代用于下载软件包内容的源位置。 | 字符串 | Streaming\PackageSourceRoot | 未写入策略值（与 "未配置" 相同） |
| AllowHighCostLaunch | 不可用。 |此设置控制是否在通过按流量计费的网络连接（例如，4G）连接的 Windows 10 计算机上启动虚拟化应用程序。 | True （已启用）;False （已禁用状态） | Streaming\AllowHighCostLaunch | 0 |
| ReestablishmentRetries | 不可用。 | 指定重试已删除的会话的次数。 | 整数（0-99） | Streaming\ReestablishmentRetries | 未写入策略值（与 "未配置" 相同） |
| ReestablishmentInterval | 不可用。 | 指定尝试重新建立已删除会话之间的秒数。 | 整数（0-3600） | Streaming\ReestablishmentInterval | 未写入策略值（与 "未配置" 相同） |
| LocationProvider | 不可用。 | 指定 IAppvPackageLocationProvider 接口的兼容实现的 CLSID。 | 字符串 | Streaming\LocationProvider | 未写入策略值（与 "未配置" 相同） |
| CertFilterForClientSsl | 不可用。 | 指定证书存储中的有效证书的路径。 | 字符串 | Streaming\CertFilterForClientSsl | 未写入策略值（与 "未配置" 相同） |
| VerifyCertificateRevocationList | 不可用。 | 在 steaming 使用 HTTPS 之前验证服务器证书吊销状态。 | True （已启用）;False （已禁用状态） | Streaming\VerifyCertificateRevocationList | 0 |
| SharedContentStoreMode | SHAREDCONTENTSTOREMODE | 指定流式处理的程序包内容将不会保存到本地硬盘。 | True （已启用）;False （已禁用状态） | Streaming\SharedContentStoreMode | 0 |
| 名称<br>**注意**无法使用**AppvclientConfiguration** cmdLet 修改此设置。 你必须使用**AppvPublishingServer** cmdlet。 | PUBLISHINGSERVERNAME | 显示发布服务器的名称。 | 字符串 | Publishing\Servers\ {serverId} \ FriendlyName | 未写入策略值（与 "未配置" 相同） |
| URL<br>**注意**无法使用**AppvclientConfiguration** cmdLet 修改此设置。 你必须使用**AppvPublishingServer** cmdlet。 | PUBLISHINGSERVERURL | 显示发布服务器的 URL。 | 字符串 | Publishing\Servers\ {serverId} \ URL | 未写入策略值（与 "未配置" 相同） |
| GlobalRefreshEnabled<br>**注意**无法使用**AppvclientConfiguration** cmdLet 修改此设置。 你必须使用**AppvPublishingServer** cmdlet。 | GLOBALREFRESHENABLED | 启用全局发布刷新（布尔值） | True （已启用）;False （已禁用状态） | Publishing\Servers\{serverId}\GlobalEnabled | False |
| GlobalRefreshOnLogon<br>**注意**无法使用**AppvclientConfiguration** cmdLet 修改此设置。 你必须使用**AppvPublishingServer** cmdlet。 | GLOBALREFRESHONLOGON | 在登录时触发全局发布刷新。 布尔 | True （已启用）;False （已禁用状态） | Publishing\Servers\{serverId}\GlobalLogonRefresh | False |
| GlobalRefreshInterval<br>**注意**无法使用**AppvclientConfiguration** cmdLet 修改此设置。 你必须使用**AppvPublishingServer** cmdlet。 | GLOBALREFRESHINTERVAL | 使用 GlobalRefreshIntervalUnit 指定发布刷新间隔。 若要禁用程序包刷新，请选择 "0"。 | 整数（0-744） | Publishing\Servers\{serverId}\GlobalPeriodicRefreshInterval | 0 |
| GlobalRefreshIntervalUnit <br>**注意**无法使用**AppvclientConfiguration** cmdLet 修改此设置。 你必须使用**AppvPublishingServer** cmdlet。 | GLOBALREFRESHINTERVALUNI | 指定间隔单位（小时0-23，第0-31 天）。 | 0表示小时，1表示天 | Publishing\Servers\{serverId}\GlobalPeriodicRefreshIntervalUnit | raid-1 |
| UserRefreshEnabled<br>**注意**无法使用**AppvclientConfiguration** cmdLet 修改此设置。 你必须使用**AppvPublishingServer** cmdlet。 | USERREFRESHENABLED | 启用用户发布刷新（布尔值） | True （已启用）;False （已禁用状态） | Publishing\Servers\{serverId}\UserEnabled | False |
| UserRefreshOnLogon<br>**注意**无法使用**AppvclientConfiguration** cmdLet 修改此设置。 你必须使用**AppvPublishingServer** cmdlet。 | USERREFRESHONLOGON | 触发用户发布刷新 onlogon。 布尔<br>字数统计（带空格）：60 | True （已启用）;False （已禁用状态） | Publishing\Servers\{serverId}\UserLogonRefresh | False |
| UserRefreshInterval<br>**注意**无法使用**AppvclientConfiguration** cmdLet 修改此设置。 你必须使用**AppvPublishingServer** cmdlet。 | USERREFRESHINTERVAL | 使用 UserRefreshIntervalUnit 指定发布刷新间隔。 若要禁用程序包刷新，请选择 "0"。 | 字数统计（带空格）：85<br>整数（0-744 小时） | Publishing\Servers\{serverId}\UserPeriodicRefreshInterval | 0 |
| UserRefreshIntervalUnit<br>**注意**无法使用**AppvclientConfiguration** cmdLet 修改此设置。 你必须使用**AppvPublishingServer** cmdlet。 | USERREFRESHINTERVALUNIT | 指定间隔单位（小时0-23，第0-31 天）。 | 0表示小时，1表示天 | Publishing\Servers\{serverId}\UserPeriodicRefreshIntervalUnit | raid-1 |
| MigrationMode | MIGRATIONMODE | 迁移模式允许 App-v 客户端修改使用早期版本的 App-v 创建的程序包的快捷方式和 FTA。 | True （已启用状态）;False （已禁用状态） | Coexistence\MigrationMode | |
| CEIPOPTIN | CEIPOPTIN | 允许运行 app-v 5.1 客户端的计算机收集并返回某些使用信息，以帮助我们进一步改进应用程序。 | 0表示已禁用;1表示已启用 | 软件/Microsoft/AppV/CEIP/CEIPEnable | 0 | 
| EnablePackageScripts | ENABLEPACKAGESCRIPTS | 支持在应运行的配置文件的程序包清单中定义的脚本。 | True （已启用）;False （已禁用状态） | \Scripting\EnablePackageScripts | | 
| RoamingFileExclusions | ROAMINGFILEEXCLUSIONS | 指定相对于% userprofile% 的文件路径，不要与用户的配置文件一起漫游。 示例用法：/ROAMINGFILEEXCLUSIONS = "桌面; 我的图片" | | | |
| RoamingRegistryExclusions | ROAMINGREGISTRYEXCLUSIONS | 指定不与用户配置文件一起漫游的注册表路径。 示例用法：/ROAMINGREGISTRYEXCLUSIONS = software\\classes; software\\clients | 字符串 | Integration\RoamingRegistryExclusions | 未写入策略值（与 "未配置" 相同） |
| IntegrationRootUser | 不可用。 | 指定创建与每用户已发布程序包的当前版本相关联的符号链接的位置。 所有虚拟应用程序扩展（例如快捷方式和文件类型关联）都将指向此路径。 如果不指定路径，则在发布包时不会使用符号链接。 例如：%localappdata%\Microsoft\AppV\Client\Integration。| 字符串 | Integration\IntegrationRootUser | 未写入策略值（与 "未配置" 相同） |
|IntegrationRootGlobal | 不可用。| 指定创建与全局发布的程序包的当前版本相关联的符号链接的位置。 所有虚拟应用程序扩展（例如快捷方式和文件类型关联）都将指向此路径。 如果不指定路径，则在发布包时不会使用符号链接。 例如：%allusersprofile%\Microsoft\AppV\Client\Integration | 字符串 | Integration\IntegrationRootGlobal | 未写入策略值（与 "未配置" 相同） |
| VirtualizableExtensions | 不可用。 | 可用于确定本地安装的应用程序是否可以在虚拟环境中运行的文件扩展名的逗号分隔列表。<br>在发布期间创建快捷方式、FTAs 和其他扩展点时，如果与扩展点关联的应用程序在本地安装，则 App-v 会将文件扩展名与列表进行比较。 如果扩展已找到，则将添加**RunVirtual**命令行参数，并且应用程序将完全运行。<br>有关**RunVirtual**参数的详细信息，请参阅[在虚拟环境中使用虚拟化的应用程序运行本地安装的应用程序](running-a-locally-installed-application-inside-a-virtual-environment-with-virtualized-applications51.md)。 | 字符串 | Integration\VirtualizableExtensions | 策略值未写入 |
| ReportingEnabled | 不可用。 | 使客户端能够将信息返回到报表服务器。 | True （已启用）;False （已禁用状态） | Reporting\EnableReporting | False |
| ReportingServerURL | 不可用。 | 指定报表服务器上保存客户端信息的位置。 | 字符串 | Reporting\ReportingServer | 未写入策略值（与 "未配置" 相同） |
| ReportingDataCacheLimit | 不可用。 | 指定用于存储报告信息的 XML 缓存的最大大小（以兆字节（MB）为单位）。 大小应用于内存中的缓存。 达到限制时，日志文件将翻转。 在0和1024之间设置。 | Integer [0-1024] | Reporting\DataCacheLimit | 未写入策略值（与 "未配置" 相同） |
| ReportingDataBlockSize| 不可用。 | 指定用于报告上载请求的服务器传输到服务器的最大大小（以字节为单位）。 这有助于避免在日志达到较大大小时出现永久性传输故障。 设置为1024和无限制。 | Integer [1024-无限] | Reporting\DataBlockSize | 未写入策略值（与 "未配置" 相同） |
| ReportingStartTime | 不可用。 | 指定启动客户端以将数据发送到报告服务器的时间。 你必须在0-23 之间指定一个有效的整数，对应于一天中的小时。 默认情况下， **ReportingStartTime**将在当前日期的10个第 M 个、第 M 个或第22天开始。<br>**注意**当运行 App-v 5.1 客户端的计算机最有可能处于离线状态时，应将此设置配置为一个时间。 | 整数（0–23） | 报告 \ 开始 | 未写入策略值（与 "未配置" 相同） |
| ReportingInterval | 不可用。 | 指定客户端将用于向报告服务器重新发送数据的重试间隔。 | 整型 | Reporting\RetryInterval | 未写入策略值（与 "未配置" 相同） |
| ReportingRandomDelay | 不可用。 | 指定发送到报告服务器的数据的最大延迟（以分钟为单位）。 当计划任务启动时，客户端会在0和**ReportingRandomDelay**之间生成一个随机延迟，并在发送数据之前等待指定的持续时间。 这有助于防止服务器冲突。 | Integer [0-ReportingRandomDelay] | Reporting\RandomDelay | 未写入策略值（与 "未配置" 相同） |
| EnableDynamicVirtualization<br>**重要提示**此设置仅适用于 app-v 5.0 SP2 或更高版本。 | 不可用。 | 启用要虚拟化并与虚拟应用程序一起运行的受支持的 Shell 扩展、浏览器帮助程序对象和 Active X 控件。 | 1（已启用），0（已禁用） | HKEY_LOCAL_MACHINE \Software\Microsoft\AppV\Client\Virtualization | |
| EnablePublishingRefreshUI<br>**重要提示**此设置仅适用于 app-v 5.0 SP2。 | 不可用。 | 为运行 app-v 5.1 客户端的计算机启用发布刷新进度栏。 | 1（已启用），0（已禁用） | HKEY_LOCAL_MACHINE \Software\Microsoft\AppV\Client\Publishing | |
| HideUI<br>**重要提示** 此设置仅适用于 app-v 5.0 SP2。| 不可用。 | 隐藏发布刷新进度栏。 | 1（已启用），0（已禁用） | | |
| ProcessesUsingVirtualComponents | 不可用。 | 指定处理路径（可能包含通配符）的列表，这些路径是使用动态虚拟化（支持的 shell 扩展、浏览器帮助程序对象和 ActiveX 控件）的候选对象。 只有其完整路径与其中一个项目相匹配的进程才能使用动态虚拟化。 | 字符串 | Virtualization\ProcessesUsingVirtualComponents | 空字符串。 |






## 相关主题


[部署 App-V 5.1 Sequencer 和 Client](deploying-the-app-v-51-sequencer-and-client.md)

[如何使用 ADMX 模板和组策略修改 App-V 5.1 Client 配置](how-to-modify-app-v-51-client-configuration-using-the-admx-template-and-group-policy.md)

[如何部署 App-V Client](how-to-deploy-the-app-v-client-51gb18030.md)

 

 





