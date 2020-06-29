---
title: MBAM 2.0 SP1 发行说明
description: MBAM 2.0 SP1 发行说明
author: dansimp
ms.assetid: b39002ba-33c6-45ec-9d1b-464327b60f5c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 54a77fc7a493b36217ae2cdc875226b25fdc6e7b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803797"
---
# MBAM 2.0 SP1 发行说明


若要搜索这些发行说明，请按 Ctrl + F。

安装 Microsoft BitLocker 管理和监视（MBAM） 2.0 Service Pack 1 （SP1）之前，请仔细阅读这些发行说明。 这些发行说明包含成功安装 BitLocker 管理和监视 2.0 SP1 所需的信息，其中包含产品文档中不可用的信息。 如果这些发行说明和其他 MBAM 2.0 SP1 文档之间存在差异，则应将最新更改视为权威。 这些发行说明取代了本产品附带的内容。

## <a href="" id="---------mbam-2-0-sp1-known-issues"></a> MBAM 2.0 SP1 已知问题


本部分包含 MBAM 2.0 SP1 的已知问题。

### 将 Configuration Manager 集成拓扑的 MBAM 升级到 MBAM 2.0 SP1 需要手动删除 Configuration Manager 对象

如果你将 MBAM 与 Configuration Manager 配合使用，并且希望升级到 MBAM 2.0 SP1，则必须手动删除已安装到 Configuration Manager 的所有 Configuration Manager 对象，作为 MBAM 安装的一部分。 必须手动删除的对象包括 MBAM 报表、MBAM 支持的计算机集合以及 BitLocker 保护配置基线及其关联的配置项目。

**解决方法**：通过完成以下步骤来升级 Configuration Manager 对象：

1.  将现有合规性数据备份到外部文件，如以下步骤中所述。

    **注意** 删除配置管理器中的现有基线后，所有现有的 BitLocker 合规性数据都将被删除。 将随着时间的推移重新生成数据，但建议你保存数据的副本，以防需要特定计算机的合规性数据，然后再重新生成合规性数据。

     

    1.  若要保存已记录的 BitLocker 合规性数据，请打开 " **Bitlocker 企业合规性详细信息**" 报表。

    2.  单击报表中的 "**保存**" 图标，然后选择 " **Excel**"。

        保存的报表将包含诸如计算机名、域名、合规性状态、豁免、设备用户、合规性状态详细信息和上次联系日期/时间等数据。 某些信息（如详细的卷信息和加密强度）将不会保存。

2.  通过使用**MBAM**安装程序从服务器卸载**MBAM** 。

3.  从配置管理器中手动删除以下对象：

    -   MBAM 支持的计算机集合

    -   BitLocker 保护基线

    -   BitLocker 操作系统驱动器保护配置项目

    -   BitLocker 固定数据驱动器保护配置项目

4.  在 Configuration Manager SQL Server Reporting Services 网站中手动删除 MBAM 报表文件夹。 若要实现此目的，请执行以下操作：

    1.  使用 Internet Explorer 浏览到 reporting services 点，例如，http:// &lt; yourcmserver &gt; /reports。

    2.  单击相应的 Configuration Manager "站点代码" 链接。

    3.  删除 MBAM 文件夹。

5.  使用 MBAM 服务器安装程序重新安装 Configuration Manager 集成对象。 客户端计算机将随着时间的推移再次开始上载 BitLocker 合规性数据。

### 自助服务门户上的 "提交" 按钮在 Internet Explorer10 中不起作用

使用 Internet Explorer10 访问管理和监视网站时，网站上的 "**提交**" 按钮不起作用。

**解决方法**：在安装了管理和监视网站的服务器上，安装[ASP.NET 浏览器定义文件的修复程序](https://go.microsoft.com/fwlink/?LinkId=317798)。

### 不支持国际域名

MBAM 2.0 SP1 不支持国际域名。

**解决方法**：无。

### 如果未在 SSRS 中配置 SSL，管理和监视网站中的报表将显示警告

如果未将 SQLServer Reporting Services （SSRS）配置为使用安全套接字层（SSL），则在安装 MBAM 服务器时，报表的 URL 将设置为 HTTP 而不是 HTTPS。 如果您随后浏览到 "管理和监视" 网站并选择一个报表，则会显示以下消息： "仅显示安全内容"。

**解决方法**：若要解决此问题，请在安装了 SQLServer Reporting SERVICES 的 MBAM 服务器上的**Reporting Services 配置管理器**中配置 SSL。 卸载并重新安装 "管理和监视服务器" 网站。

### 单击 "合规性摘要" 报表中的 "返回" 可能会产生错误

如果向下钻取到合规性摘要报表，然后单击 SSRS 报表中的**Back**链接，可能会出现错误。

**解决方法**：无。

### "仅使用空间" 加密不会正常工作

如果你在安装 MBAM 客户端后首次加密计算机，并且已将组策略对象设置为仅实现已使用的空间加密，则 MBAM 会错误地加密整个磁盘，而不是仅加密磁盘的已用空间。 如果在安装 MBAM 客户端之前已使用仅加密的计算机进行了加密，并且已设置了相同的已用空间 "仅加密组策略" 对象，则 MBAM 会识别该设置并在合规性报告中正确报告加密。

**解决方法**：无。

### 密码强度在计算机合规性报告中显示不正确

如果未在 "**选择驱动器加密方法" 和 "密码强度**" 组策略对象中设置特定的密码强度，则配置管理器集成拓扑中的 "计算机合规性报告" 将始终显示密码强度的 "**未知**"，即使密码强度使用默认值128位加密也是如此。 如果在组策略对象中设置了特定的密码强度，则报表将显示正确的密码强度。

**解决方法**：在 "**选择驱动器加密方法" 和 "密码强度**" 组策略对象中始终设置特定的密码强度。

### 合规性状态按驱动器类型分布在更新配置项目后显示旧数据

在 SystemCenter2012 ConfigurationManager 中更新 MBAM 配置项目后，"BitLocker 企业合规性" 仪表板上的 "驱动器类型" 分布图中的合规性状态分布将显示基于来自旧版本的配置项目的信息的数据。

**解决方法**：无。 不支持修改 MBAM 配置项目，并且报表可能不会按预期显示。

### 增强的安全配置可能导致报表显示不正确

如果 Internet Explorer 增强的安全配置（ESC）处于打开状态，则当你尝试在 MBAM 服务器上查看报告时，可能会显示 "**拒绝访问**" 消息。 默认情况下，已启用增强的安全配置以保护服务器，方法是降低服务器对通过 web 内容和应用程序脚本可能发生的潜在攻击的影响。

**解决方法**：如果尝试在 MBAM 服务器上查看报告时出现**拒绝访问**消息，则可以在映像中设置组策略对象或手动更改默认设置，以禁用增强的安全配置。 您也可以从其他计算机上查看未启用增强安全配置的报告。

### <a href="" id="-------------mbam-server-installation-fails-when-you-upgrade-from-sql-server-2008-to-sql-server-2012"></a> 从 SQLServer2008 升级到 SQLServer2012 时，MBAM 服务器安装失败

如果从 SQLServer2008 升级到 SQLServer2012，然后尝试安装合规性和审核数据库或恢复数据库，则安装将失败并回退。 发生故障的原因是，在 SQLServer 升级期间删除了所需的 SQLCMD.exe 文件，但 MBAM 安装程序无法找到该文件。 MSI 日志文件行可能看起来类似于以下内容：

RunDbInstallScript Recovery Db CA： BinDir-E:\\MSSQL\\100\\Tools\\Binn\\SqlCmd.exeRunDbInstallScript db ca： dbInstance-xxxxxx\\I01RunDbInstallScript sqlScript C:\\program files BitLocker 管理和 Files\\Microsoft\\Microsoft 恢复 Db CA： dbName-MONITORING\\SETUP\\KEYRECOVERY.SQLRUNDBINSTALLSCRIPT \ _Recovery \ _and \ _HardwareRunDbInstallScript 恢复 db ca： MBAM-defaultFileName \ _Recovery \ _and _HardwareRunDbInstallScript 恢复 Db CA： MBAM-defaultDataPathI01\\MSSQL\\DATA\\RunDbInstallScript Recovery Db CA： defaultLogPath-K:\\MSSQL\\MSSQL10。I01\\MSSQL\\Data\\RunDbInstallScript： scriptLogPath-C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\InstallKeyComplianceDatabase.log-e-E S xxxxxxx\\I01-i "C:\\program files Files\\Microsoft\\Microsoft BitLocker 管理和 Monitoring\\Setup\\KeyRecovery.sql"-v DatabaseName = "MBAM \ _Recovery \ _and \ _Hardware" DefaultFileName = "MBAM _Recovery \ _and" DefaultDataPath = "F:\\MSSQL\\MSSQL10。I01\\MSSQL\\DATA\\ "DefaultLogPath =" K:\\MSSQL\\MSSQL10。I01\\MSSQL\\Data\\ "-o" C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\InstallKeyComplianceDatabase.log "RunDbInstallScript 恢复数据库 CA：正在开始运行恢复数据库安装 scriptRunDbInstallScript 恢复数据库 CA： Sqlcmd 日志文件位于 C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\\\InstallKeyRecoveryDatabase.logRunDbInstallScript 恢复数据库 CA 异常：安装恢复数据库自定义操作命令行输出异常：系统找不到指定的文件

MBAM 服务器 Windows Installer 是硬编码的，可通过在 HKLM\\Software\\Microsoft\\Microsoft SQLServer\\100\\Tools\\ClientSetup. 下的注册表中查看 Path 字符串值来查找 SQLCMD.exe 路径。 从 SQLServer2008 到 SQLServer2012 的迁移期间，该键仍然存在，但数据值引用的路径不包含 SQLCMD.exe 文件，因为 SQLupgrade 进程删除了该文件。

**解决方法**：将 HKLM\\Software\\Microsoft\\Microsoft SQLServer\\100\\Tools\\ClientSetup path 字符串值暂时重命名为**path \ _old**，然后再次在 MBAM 服务器上运行 Windows Installer。 当安装成功完成并在 SQLServer2012 中创建数据库时，请将**路径 \ _old**重命名为**path**。

## 适用于 MBAM 2.0 SP1 的修补程序和知识文库文章


本部分包含适用于 MBAM 2.0 SP1 的修补程序和知识库文章。

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


[关于 MBAM 2.0 SP1](about-mbam-20-sp1.md)

 

 





