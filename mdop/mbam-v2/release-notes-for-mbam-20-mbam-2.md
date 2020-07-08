---
title: MBAM 2.0 发行说明
description: MBAM 2.0 发行说明
author: dansimp
ms.assetid: c3f16cf3-94f2-47ac-b3a4-3dc505c6a8dd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2d5d3c7d539cf2828d28c1844321bc34ab7736ac
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803798"
---
# MBAM 2.0 发行说明


若要搜索这些发行说明，请按 Ctrl + F。

在安装 Microsoft BitLockerAdministration 和监控（MBAM）2.0 之前，请先阅读这些发行说明。 这些发行说明包含成功安装 BitLockerAdministration 和监控2.0 所需的信息，其中包含产品文档中不可用的信息。 如果这些发行说明和其他 MBAM 2.0 文档之间存在差异，则应将最新更改视为权威。 这些发行说明取代了本产品附带的内容。

## <a href="" id="---------mbam-2-0-known-issues"></a> MBAM 2.0 已知问题


本部分包含适用于 MBAM 2.0 的发行说明。

### 当您在 Microsoft System Center Configuration Manager 2007 上运行 MBAM 时，计算机名称字段可能不会显示在 BitLocker 计算机合规性和 BitLocker 企业合规性详细信息报告中

将 MBAM 与 Configuration Manager 2007 配合使用时，"计算机名称" 域在 BitLocker 计算机合规性和 BitLocker 企业合规性详细信息报告中可能为空。

解决方法：无。

### 升级独立的 MBAM 服务器基础结构后，无法更新企业合规性报告

如果你使用的是 MBAM 独立拓扑，并且将服务器基础结构从版本1.0 升级到2.0，则无法更新企业合规性报告。

解决方法：升级后，针对合规性和审核数据库运行以下脚本：

```sql
-- =============================================
-- Script Template
-- =============================================

DECLARE @DatabaseName nvarchar(255);
SET @DatabaseName = DB_NAME()

USE msdb;

DECLARE @JobID BINARY(16)
SELECT @JobID = job_id
FROM msdb.dbo.sysjobs
WHERE (name = N'CreateCache')

if (@JobID IS NOT NULL)
BEGIN
    EXEC dbo.sp_delete_job
         @job_name = N'CreateCache';
END

EXEC dbo.sp_add_job
    @job_name = N'CreateCache',
    @enabled = 1;

EXEC dbo.sp_add_jobstep
     @job_name = N'CreateCache',
     @step_name = N'Copy Data',
     @subsystem = N'TSQL',
     @command = N'EXEC [ComplianceCore].UpdateCache',
     @database_name = @DatabaseName,
     @retry_attempts = 5,
     @retry_interval = 5;


EXEC dbo.sp_add_jobschedule
     @job_name = N'CreateCache',
     @name = N'ReportCacheSchedule1am',
     @freq_type = 4,
     @freq_interval = 1,
     @active_start_time = 010000,
     @active_end_time = 020000;

EXEC dbo.sp_attach_schedule
     @job_name = N'CreateCache',
     @schedule_name = N'ReportCacheSchedule1am';

EXEC dbo.sp_add_jobschedule
     @job_name = N'CreateCache',
     @name = N'ReportCacheSchedule7am',
     @freq_type = 4,
     @freq_interval = 1,
     @active_start_time = 070000,
     @active_end_time = 080000;

EXEC dbo.sp_attach_schedule
     @job_name = N'CreateCache',
     @schedule_name = N'ReportCacheSchedule7am';

EXEC dbo.sp_add_jobschedule
     @job_name = N'CreateCache',
     @name = N'ReportCacheSchedule1pm',
     @freq_type = 4,
     @freq_interval = 1,
     @active_start_time = 130000,
     @active_end_time = 140000;

EXEC dbo.sp_attach_schedule
     @job_name = N'CreateCache',
     @schedule_name = N'ReportCacheSchedule1pm';

EXEC dbo.sp_add_jobschedule
     @job_name = N'CreateCache',
     @name = N'ReportCacheSchedule7pm',
     @freq_type = 4,
     @freq_interval = 1,
     @active_start_time = 190000,
     @active_end_time = 200000;

EXEC dbo.sp_attach_schedule
     @job_name = N'CreateCache',
     @schedule_name = N'ReportCacheSchedule7pm';

EXEC dbo.sp_add_jobserver
     @job_name = N'CreateCache';
```

### 如果未在 SSRS 中配置 SSL，技术支持门户中的报表将显示警告

如果 SQL Server Reporting Services （SSRS）未配置为使用安全套接字层（SSL），则在安装 MBAM 服务器时，报表的 URL 将设置为 HTTP，而不是 HTTPS。 如果您随后浏览到帮助台门户并选择报表，则会显示以下消息： "仅显示安全内容"。

解决方法：若要显示报表，请单击 "**显示所有内容**"。 若要解决此问题，请转到安装了 SQL Server Reporting Services 的 MBAM 计算机，运行**Reporting Services 配置管理器**，然后单击 " **Web 服务 URL**"。 为服务器选择相应的 SSL 证书，输入相应的 SSL 端口（默认端口为443），然后单击 "**应用**"。

### 不支持 Configuration Manager 数据库的非默认实例

MBAM 仅在 Configuration Manager 2007 和 SystemCenter2012 ConfigurationManager 中查看 Configuration Manager 数据库的默认实例。 如果使用非默认实例，则无法安装 MBAM。

解决方法：无。

### <a href="" id="clicking--back--in-the-compliance-summary-report-might-throw-an-error"></a>单击 "兼容性摘要" 报表中的 "后退" 可能会引发错误

如果向下钻取到合规性摘要报表，然后单击 SSRS 报表中的**Back**链接，则可能会引发错误。

解决方法：无。

### "仅使用空间" 加密不会正常工作

如果你在安装 MBAM 客户端后首次加密计算机，并且已将组策略对象设置为仅实现已使用的空间加密，则 MBAM 会错误地加密整个磁盘，而不是仅加密磁盘的已用空间。 如果在安装 MBAM 客户端时已对计算机进行了加密，并且设置了相同的组策略对象，则加密会正常工作，并且只加密计算机上已使用的磁盘空间。

解决方法：无。

### 密码强度在计算机合规性报告上显示错误

如果你未在 "**选择驱动器加密方法" 和 "密码强度**" 组策略对象中设置特定的密码强度，则配置管理器集成拓扑中的计算机合规性报告始终显示密码强度的 "unknown"，即使密码强度使用默认的128位加密也是如此。 如果在组策略对象中设置了特定的密码强度，则报表将显示正确的密码强度。

解决方法：在 "**选择驱动器加密方法" 和 "密码强度**" 组策略对象中始终设置特定的密码强度。

### 合规性状态按驱动器类型分布在更新配置项目后显示旧数据

在 SystemCenter2012 ConfigurationManager 中更新 MBAM 配置项目后，"BitLocker 企业合规性" 仪表板上的 "驱动器类型" 分布图中的合规性状态分布将显示基于来自旧版本的配置项目的信息的数据。

解决方法：无。 不支持修改 MBAM 配置项目，并且报表可能不会按预期显示。

### 增强的安全配置可能导致报表显示不正确

如果 Internet Explorer 增强的安全配置（ESC）处于打开状态，则当你尝试在 MBAM 服务器上查看报告时，可能会显示 "拒绝访问" 消息。 默认情况下，按 ESC 可保护服务器，方法是降低服务器对通过 web 内容和应用程序脚本可能发生的潜在攻击的影响。

解决方法：如果在 MBAM 服务器上尝试查看报表时出现 "拒绝访问" 消息，则可以在映像中设置组策略对象或手动更改默认设置，以禁用增强的安全配置。 您也可以从另一台计算机上查看未启用 ESC 的报告。

### 从 SQL Server 2008 升级到 SQL Server 2012 时，MBAM Server 安装失败

如果从 SQL Server 2008 升级到 SQL Server 2012，然后尝试安装合规性和审核数据库或恢复数据库，则安装将失败并回退。 发生故障的原因是在 SQL 升级期间删除了所需的 SQLCMD.exe 文件，但 MBAM 安装程序找不到该文件。 MSI 日志文件行可能看起来类似于以下内容：

RunDbInstallScript Recovery Db CA： BinDir-E:\\MSSQL\\100\\Tools\\Binn\\SqlCmd.exeRunDbInstallScript db ca： dbInstance-xxxxxx\\I01RunDbInstallScript sqlScript C:\\program files BitLocker 管理和 Files\\Microsoft\\Microsoft 恢复 Db CA： dbName-MONITORING\\SETUP\\KEYRECOVERY.SQLRUNDBINSTALLSCRIPT \ _Recovery \ _and \ _HardwareRunDbInstallScript 恢复 db ca： MBAM-defaultFileName \ _Recovery \ _and _HardwareRunDbInstallScript 恢复 Db CA： MBAM-defaultDataPathI01\\MSSQL\\DATA\\RunDbInstallScript Recovery Db CA： defaultLogPath-K:\\MSSQL\\MSSQL10。I01\\MSSQL\\Data\\RunDbInstallScript： scriptLogPath-C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\InstallKeyComplianceDatabase.log-e-E S xxxxxxx\\I01-i "C:\\program files Files\\Microsoft\\Microsoft BitLocker 管理和 Monitoring\\Setup\\KeyRecovery.sql"-v DatabaseName = "MBAM \ _Recovery \ _and \ _Hardware" DefaultFileName = "MBAM _Recovery \ _and" DefaultDataPath = "F:\\MSSQL\\MSSQL10。I01\\MSSQL\\DATA\\ "DefaultLogPath =" K:\\MSSQL\\MSSQL10。I01\\MSSQL\\Data\\ "-o" C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\InstallKeyComplianceDatabase.log "RunDbInstallScript 恢复数据库 CA：正在开始运行恢复数据库安装 scriptRunDbInstallScript 恢复数据库 CA： Sqlcmd 日志文件位于 C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\\\InstallKeyRecoveryDatabase.logRunDbInstallScript 恢复数据库 CA 异常：安装恢复数据库自定义操作命令行输出异常：系统找不到指定的文件

MBAM 服务器 Windows Installer 是硬编码的，可通过在 HKLM\\Software\\Microsoft\\Microsoft SQL Server\\100\\Tools\\ClientSetup. 下的注册表中查找 Path 字符串值来查找 SQLCMD.exe 路径。 从 SQL Server 2008 迁移到 SQL Server 2012 期间仍然存在该键，但由于 SQL 升级过程删除了该文件，因此由数据值引用的路径不包含 SQLCMD.exe 文件。

解决方法：临时将 HKLM\\Software\\Microsoft\\Microsoft SQL Server\\100\\Tools\\ClientSetup Path 字符串值重命名为**Path \ _old**，然后重新运行 MBAM Server Windows Installer。 当安装成功完成并在 SQL Server 2012 中创建数据库时，请将**路径 \ _old**值重命名为**path**。

## MBAM 2.0 版修补程序和知识库文章


本部分包含适用于 MBAM 2.0 的修补程序和知识库文章。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong>知识库文章</strong></th>
<th align="left">Title</th>
<th align="left"><strong>链接</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>2831166</p></td>
<td align="left"><p>安装 Microsoft BitLocker 管理和监视（MBAM）2.0 失败， &quot; 已安装 System CENTER CM 对象&quot;</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2831166/EN-US" data-raw-source="[support.microsoft.com/kb/2831166/EN-US](https://support.microsoft.com/kb/2831166/EN-US)">support.microsoft.com/kb/2831166/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2870849</p></td>
<td align="left"><p>用户无法使用 MBAM 2.0 自助服务门户检索 BitLocker 恢复密钥</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2870849/EN-US" data-raw-source="[support.microsoft.com/kb/2870849/EN-US](https://support.microsoft.com/kb/2870849/EN-US)">support.microsoft.com/kb/2870849/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2756402</p></td>
<td align="left"><p>MBAM 客户端将失败，并出现事件描述中的事件 ID 4 和错误代码0x8004100E</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2756402/EN-US" data-raw-source="[support.microsoft.com/kb/2756402/EN-US](https://support.microsoft.com/kb/2756402/EN-US)">support.microsoft.com/kb/2756402/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2620287</p></td>
<td align="left"><p>单击 MBAM 中的 "报表" 选项卡时，出现 "/Reports" 应用程序中的 "服务器错误" 错误消息</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2620287/EN-US" data-raw-source="[support.microsoft.com/kb/2620287/EN-US](https://support.microsoft.com/kb/2620287/EN-US)">support.microsoft.com/kb/2620287/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2639518</p></td>
<td align="left"><p>在 MBAM 中打开企业或计算机合规性报告时出错</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2639518/EN-US" data-raw-source="[support.microsoft.com/kb/2639518/EN-US](https://support.microsoft.com/kb/2639518/EN-US)">support.microsoft.com/kb/2639518/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2620269</p></td>
<td align="left"><p>MBAM 企业报告未获得更新</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2620269/EN-US" data-raw-source="[support.microsoft.com/kb/2620269/EN-US](https://support.microsoft.com/kb/2620269/EN-US)">support.microsoft.com/kb/2620269/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2712461</p></td>
<td align="left"><p>不支持在域控制器上安装 MBAM</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2712461/EN-US" data-raw-source="[support.microsoft.com/kb/2712461/EN-US](https://support.microsoft.com/kb/2712461/EN-US)">support.microsoft.com/kb/2712461/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2876732</p></td>
<td align="left"><p>在 MBAM 2.0 的独立或 Configuration Manager 集成设置期间收到错误代码0x80071a90</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2876732/EN-US" data-raw-source="[support.microsoft.com/kb/2876732/EN-US](https://support.microsoft.com/kb/2876732/EN-US)">support.microsoft.com/kb/2876732/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2754259</p></td>
<td align="left"><p>MBAM 和安全网络通信</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2754259/EN-US" data-raw-source="[support.microsoft.com/kb/2754259/EN-US](https://support.microsoft.com/kb/2754259/EN-US)">support.microsoft.com/kb/2754259/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2870842</p></td>
<td align="left"><p>MBAM 2.0 安装程序在 SQL Server 2008 的 Configuration Manager 集成方案期间失败</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2870842/EN-US" data-raw-source="[support.microsoft.com/kb/2870842/EN-US](https://support.microsoft.com/kb/2870842/EN-US)">support.microsoft.com/kb/2870842/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2668533</p></td>
<td align="left"><p>如果 SQL SSRS 的配置不正确，MBAM 安装将失败</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2668533/EN-US" data-raw-source="[support.microsoft.com/kb/2668533/EN-US](https://support.microsoft.com/kb/2668533/EN-US)">support.microsoft.com/kb/2668533/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2870847</p></td>
<td align="left"><p>MBAM 2.0 安装失败， &quot; 检索 &#39;Reporting Services 点&#39; 角色的 Configuration Manager 服务器角色设置时出错&quot;</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2870847/EN-US" data-raw-source="[support.microsoft.com/kb/2870847/EN-US](https://support.microsoft.com/kb/2870847/EN-US)">support.microsoft.com/kb/2870847/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2870839</p></td>
<td align="left"><p>由于 SQL 作业 CreateCache 失败，MBAM 2.0 企业版报表不会在 MBAM 2.0 独立拓扑中刷新</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2870839/EN-US" data-raw-source="[support.microsoft.com/kb/2870839/EN-US](https://support.microsoft.com/kb/2870839/EN-US)">support.microsoft.com/kb/2870839/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2620269</p></td>
<td align="left"><p>MBAM 企业报告未获得更新</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2620269/EN-US" data-raw-source="[support.microsoft.com/kb/2620269/EN-US](https://support.microsoft.com/kb/2620269/EN-US)">support.microsoft.com/kb/2620269/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2935997</p></td>
<td align="left"><p>MBAM 支持的计算机合规性报告不正确包括不支持的产品</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2935997/EN-US" data-raw-source="[support.microsoft.com/kb/2935997/EN-US](https://support.microsoft.com/kb/2935997/EN-US)">support.microsoft.com/kb/2935997/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2612822</p></td>
<td align="left"><p>MBAM 中的计算机记录被拒绝</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2612822/EN-US" data-raw-source="[support.microsoft.com/kb/2612822/EN-US](https://support.microsoft.com/kb/2612822/EN-US)">support.microsoft.com/kb/2612822/EN-US</a></p></td>
</tr>
</tbody>
</table>

 

## 相关主题


[关于 MBAM 2.0](about-mbam-20-mbam-2.md)

 

 





