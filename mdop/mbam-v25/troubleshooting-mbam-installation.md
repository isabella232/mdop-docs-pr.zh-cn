---
title: MBAM 2.5 安装问题疑难解答
description: 介绍了如何解决 MBAM 2.5 安装问题。
author: Deland-Han
ms.reviewer: dcscontentpm
manager: dansimp
ms.author: delhan
ms.sitesec: library
ms.prod: w10
ms.date: 09/16/2019
ms.openlocfilehash: 6ea152792801c630fa365f37d1668d1a4d84b3a5
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910627"
---
# <a name="troubleshooting-mbam-25-installation-problems"></a>MBAM 2.5 安装问题疑难解答

本文介绍了如何在独立配置中解决 Microsoft BitLocker (MBAM) 2.5 安装问题。

## <a name="referring-mbam-log-files-for-troubleshooting"></a>引用 MBAM 日志文件进行疑难解答

MBAM 包括服务器安装、客户端安装和事件的日志记录。 应引用此日志记录以进行故障排除。 
 
### <a name="mbam-server-installation-log-files"></a>MBAM 服务器安装日志文件

MBAMServerSetup.exe在 MBAM 安装期间，在用户的 %temp% 文件夹中生成以下日志文件：<br /> **Microsoft_BitLocker_Administration_and_Monitoring_<.log> 14 个数字**

MBAMServerSetup.exe MBAM 设置和 MBAM 服务器功能安装期间采取的操作：<br /> **Microsoft_BitLocker_Administration_and_Monitoring_<14_numbers>_0_MBAMServer.msi.log**

MBAMServerSetup.exe记录在安装过程中执行的其他操作。

### <a name="mbam-client-installation-log-file"></a>MBAM 客户端日志文件

客户端安装记录在 %temp% 日志文件文件夹或自定义位置 (，具体取决于客户端的安装) ： <br />**MSI \<five random characters\> .log**

此日志包含 MBAM 客户端安装期间采取的操作。
 
### <a name="mbam-client-event-logging-channel"></a>MBAM 客户端事件日志记录通道

MBAM 具有单独的事件日志记录通道。 管理、分析和操作日志文件位于事件查看器中的应用程序和服务日志**** Microsoft Windows  >  ****  >  ****  >  **MBAM 下**。

下表提供了每个事件日志的简要说明。
 
|事件日志| 描述|
|----------|-------|
|Microsoft-Windows-MBAM/Admin|  包含错误消息|
|Microsoft-Windows-MBAM/Analytic|   包含高级日志记录信息|
|Microsoft-Windows-MBAM/Operational|    包含成功消息|

### <a name="mbam-server-event-logging-channel"></a>MBAM 服务器事件日志记录通道

日志文件位于事件查看器中的应用程序和服务日志**** Microsoft Windows  >  ****  >  ****  >  **MBAM 下**。 下表包含 MBAM 2.5 中引入的服务器事件日志：

|事件日志| 描述|
|--------|-------------|
|Microsoft-Windows-MBAM/Admin|  包含错误消息|
|Microsoft-Windows-MBAM/Analytic|   包含高级日志记录信息|
|Microsoft-Windows-MBAM/Operational|    包含成功消息|

### <a name="mbam-web-service-logs"></a>MBAM Web 服务日志

每个 MBAM Web 服务日志将日志记录信息写入 SVCLOG 文件。 默认情况下，每个 Web 服务在 C：\inetpub\Microsoft BitLocker Management Solution\Logs 文件夹中使用其名称的文件夹下写入跟踪文件。

您可以使用服务跟踪查看器工具 (部分Microsoft Visual Studio) svclog 跟踪。

## <a name="troubleshooting-encryption-and-reporting-issues"></a>加密和报告问题疑难解答

本节包含有关服务器功能、客户端功能、配置设置和已知问题的疑难解答信息：
 
### <a name="mbam-client-installation-group-policy-settings"></a>MBAM 客户端安装，组策略设置

确定是否在客户端计算机上安装 MBAM 代理。 安装 MBAM 后，它将创建名为 BitLocker Management Client Service 的服务。 此服务配置为自动启动。 确定服务是否正在运行。

确保在客户端计算机上应用 MBAM 组策略设置。 如果在客户端计算机上应用了组策略设置，则创建以下注册表子 ** 项：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement**

验证此密钥是否存在并且已使用每个组策略设置的值填充。

### <a name="mbam-agent-in-the-initial-delay-period"></a>初始延迟期中的 MBAM 代理

MBAM 客户端不会在安装后立即启动操作。 MBAM 代理开始操作之前，初始随机延迟为 1–18 分钟。 除了初始延迟之外，还有至少 90 分钟的延迟。  (延迟取决于为检查客户端状态的频率配置的组策略设置。) 因此，客户端启动操作之前的总延迟*是随机启动*延迟客户端检查频率  +  *延迟*。

如果"操作"和"管理员"事件日志为空，则客户端尚未开始操作，并且将进入前面提到的延迟期。 如果要绕过延迟，请按照以下步骤操作：
 
1. 停止 BitLocker 管理客户端服务服务。

2. 在HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MBAM**注册表**子项下，创建**NoStartupDelay**注册表值，将它的类型设置为**REG_DWORD**，然后将它的值设置为**1。**

3. 在**HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement**下，将**ClientWakeupFrequency**和**StatusReportingFrequency**值设置为**1。** 在计算机进行组策略更新后，这些值将恢复为原始设置。

4. 启动 BitLocker 管理客户端服务服务。

服务启动后，如果在计算机上本地登录并且没有错误，则应该会收到一个在一分钟内加密计算机的请求。 如果未收到请求，应查看 MBAM 管理员日志，查看是否有错误条目。

### <a name="computer-does-not-have-a-tpm-device-or-the-tpm-device-is-not-enabled-in-the-bios"></a>计算机没有 TPM 设备，或者未在 BIOS 中启用 TPM 设备

查看 MBAM 管理员事件日志。 你将在 MBAM 管理事件日志中看到类似于以下内容的事件条目：

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          8/3/2013 12:31:10 PM
    Event ID:      9
    Task Category: None
    Level:         Error
    Keywords:      
    User:          SYSTEM
    Computer:      Mbamclient.contoso.com
    Description:
    The TPM hardware is missing.
    TPM is needed to encrypt the operating system drive with any TPM protector.

打开 TPM Management (tpm.msc) ，并检查计算机是否具有 TPM 设备。 如果 tpm.msc 未显示设备，请打开设备管理器 (devmgmt.msc) ，并检查安全设备下的受信任平台模块。 如果看不到受信任的平台模块设备，则这可能是由于以下原因之一：

* 你的系统没有受信任的平台模块 (TPM/安全) 设备。

* 在 BIOS 中禁用 TPM 设备。

* TPM 设备在 BIOS 中启用，但在 BIOS 中禁用从操作系统设置管理 TPM 设备。

* 你未将 Microsoft 驱动程序用于 TPM 设备。 查看设备管理器中列出的设备以标识 Microsoft TPM 设备驱动程序。

如果 TPM 设备没有使用 C:\Windows\System32\tpm.sys 驱动程序，你应该通过选择 C：\Windows\Inf\tpm.inf 文件来更新驱动程序。

### <a name="computer-does-not-have-a-valid-system-partition"></a>计算机没有有效的系统分区

查看 MBAM 管理员事件日志。 你将在 MBAM 管理事件日志中看到类似于以下内容的事件条目：

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          8/3/2013 4:13:37 AM
    Event ID:      8
    Task Category: None
    Level:         Error
    Keywords:      
    User:          SYSTEM
    Computer:      BITTESTVM.xtremelabs.com
    Description:
    The system volume is missing.
    SystemVolume is needed to encrypt the operating system drive.

BitLocker 需要 SYSTEM 分区才能在 ([7：常见问题Windows BitLocker 驱动器](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-7/ee449438(v=ws.10)?redirectedfrom=MSDN#bkmk_partitions)加密中启用) 。

MBAM 不会自动创建系统分区。 可以使用 BitLocker 驱动器准备实用程序 (bdehdcfg.exe) 创建系统分区并移动所需的启动文件。

例如，在部署 MBAM 加密驱动器之前，可以使用命令 **%windir%\system32\bdeHdCfg.exe -target default -size 300 –quiet** 以静默方式准备驱动器。 这需要重新启动。 如果需要，还可以编写操作脚本。 以下文档介绍了 BitLocker 驱动器准备工具：

[BitLocker 驱动器准备工具的说明](https://support.microsoft.com/help/933246)

### <a name="drives-are-not-formatted-to-have-a-compatible-file-system"></a>驱动器未格式化为具有兼容的文件系统

请参阅 [TechNet 文章了解 BitLocker 的文件系统要求](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-7/ee449438(v=ws.10)?redirectedfrom=MSDN#bkmk_hsrequirements)。

### <a name="group-policy-conflict"></a>组策略冲突

你将在 MBAM 管理事件日志中看到类似于以下内容的事件条目：

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          7/25/2013 9:27:58 PM
    Event ID:      22
    Task Category: None
    Level:         Error
    Keywords:      
    User:          SYSTEM
    Computer:      Mbamclient.contoso.com
    Description:
    Detected Fixed Data Drive volume encryption policies conflict.
    Check BitLocker and MBAM policies related to FDD drive protectors.

验证你的组策略设置以确保你在 MBAM 组策略设置之间没有冲突设置。

你应该使用 MDOP MBAM 模板而不是 BitLocker 驱动器加密模板来配置组策略。

例如：

在操作系统驱动器加密设置下，你选择了 TPM 作为保护程序，并且还选择了允许增强 **型 PIN 启动**。 这些是冲突的设置，因为仅 TPM 保护不需要 PIN。 因此，应禁用增强的 PIN 设置。

### <a name="user-may-have-requested-an-exemption"></a>用户可能请求豁免

如果启用了计算机配置\管理模板\Windows 组件\MDOP MBAM (BitLocker 管理) \客户端管理\配置用户豁免策略组策略设置，用户将可以选择请求豁免。

默认情况下，如果用户请求豁免，则豁免的有效期为 7 天，并且用户在此期间不会收到加密提示。  (策略配置期间可以增加或减小默认值。) 在免税期结束后，将提示用户进行加密。

当计算机位于用户豁免下时，你将在 MBAM 管理事件日志中看到以下条目：

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          8/3/2013 3:06:40 PM
    Event ID:      13
    Task Category: None
    Level:         Warning
    Keywords:      
    User:          SYSTEM
    Computer:      MBAMCLIENT.contoso.com
    Description:
    The user is exempt from encryption.

如果要手动替代计算机的用户豁免，请按照以下步骤操作：
 
1. 在下面的注册表子项下将 AllowUserExemption 值设置为**0：** <br />
**HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement**

2. 删除以下注册表子项下的所有注册表值****，AgentVersion、EncodedComputerName 和 Installed 除外： **** ****<br />
**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MBAM**

    **注意** 必须重新启动 MBAM 代理，更改才能生效。

请注意，将组策略应用于计算机后，这些值可能会恢复为原始设置。

### <a name="wmi-issue"></a>WMI 问题

MBAM 使用 win32_encryptablevolume 方法管理 BitLocker。 如果此模块未注册或损坏，MBAM 客户端将无法正常工作，并且你将在 MBAM 管理事件日志中看到以下事件条目：

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          7/27/2013 11:18:51 PM
    Event ID:      4
    Task Category: None
    Level:         Error
    Keywords:      
    User:          SYSTEM
    Computer:      BITTEST.xtremelabs.com
    Description:
    An error occurred while sending encryption status data.
    Error code:
    0x80041016 
    Details:
    NULL

此外，您可能注意到恢复和硬件策略不适用于错误代码0x8007007e。 这将转换为"找不到指定的模块"。

若要解决此问题，应通过使用以下命令重新注册 **win32_encryptablevolume** 类：

```cmd
mofcomp c:\Windows\System32\wbem\win32_encryptablevolume.mof
```

## <a name="troubleshooting-mbam-agent-communication-issues"></a>MBAM 代理通信问题疑难解答

本部分包含与 MBAM 代理通信相关的以下问题的疑难解答信息：

### <a name="incorrect-mbam-service-url"></a>MBAM 服务 URL 不正确

如果 MBAM 合规性状态服务或恢复与硬件服务的值不正确，你将在客户端计算机上的 MBAM 管理事件日志中看到类似于以下内容的事件条目：

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          8/3/2013 4:13:36 PM
    Event ID:      4
    Task Category: None
    Level:         Error
    Keywords:     
    User:          SYSTEM
    Computer:      Mbamclient.contoso.com
    Description:
    An error occurred while sending encryption status data.
    Error code:
    0x803d0010
    Details:
    The remote endpoint was not reachable.

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          8/3/2013 4:13:33 PM
    Event ID:      18
    Task Category: None
    Level:         Error
    Keywords:     
    User:          SYSTEM
    Computer:      Mbamclient.contoso.com
    Description:
    Unable to connect to the MBAM Recovery and Hardware service.
    Error code:
    0x803d0010
    Details:
    The remote endpoint was not reachable.

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          8/3/2013 4:20:32 PM
    Event ID:      4
    Task Category: None
    Level:         Error
    Keywords:     
    User:          SYSTEM
    Computer:      Mbamclient.contoso.com
    Description:
    An error occurred while sending encryption status data.
    Error code:
    0x803d0020
    Details:
    The endpoint address URL is invalid.

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          8/3/2013 4:20:32 PM
    Event ID:      18
    Task Category: None
    Level:         Error
    Keywords:     
    User:          SYSTEM
    Computer:      Mbamclient.contoso.com
    Description:
    Unable to connect to the MBAM Recovery and Hardware service.
    Error code:
    0x803d0020
    Details:
    The endpoint address URL is invalid.

在客户端计算机上的以下注册表子项下验证 **KeyRecoveryServiceEndPoint** 和 **StatusReportingServiceEndpoint** 的值： <br />
**HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement**

默认情况下，KeyRecoveryServiceEndPoint (MBAM 恢复和硬件服务终结点) URL 的格式如下： <br />
**http:// \<servername\> ： \<port\> /MBAMRecoveryAndHardwareService/CoreService.svc**

默认情况下，STATUSReportingServiceEndpoint (MBAM 状态报告服务终结点的 URL) 采用以下格式：<br />
**http:// \<servername\> ： \<port\> /MBAMComplianceStatusService/StatusReportingService.svc**

> [!Note]
> URL 中不应有空格。

如果服务 URL 不正确，应在以下组策略设置中更正服务 URL：

**计算机配置**  > **策略**  > **管理模板**  > **Windows组件**  > **MDOP MBAM (BitLocker Management) **  > **客户端管理**  > **配置 MBAM 服务**

### <a name="connectivity-issue-that-affects-the-mbam-administration-server"></a>影响 MBAM 管理服务器的连接问题

如果客户端代理和 MBAM 管理服务器之间存在连接问题，MBAM 代理将无法向数据库发布任何更新。 在这种情况下，你会注意到客户端计算机上的 MBAM 管理员事件日志中的连接失败条目：

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          29-04-2014 18:21:22
    Event ID:      2
    Task Category: None
    Level:         Error
    Keywords:     
    User:          SYSTEM
    Computer:      TESTLABS.CONTOSO.COM
    Description:
    An error occurred while applying MBAM policies.
    Volume ID:\\?\Volume{871c5858-2467-4d0b-8c83-d68af8ce10e5}\ 
    Error code:
    0x803D0010 
    Details:
    The remote endpoint was not reachable.
 
    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          29-04-2014 23:06:48
    Event ID:      2
    Task Category: None
    Level:         Error
    Keywords:     
    User:          SYSTEM
    Computer:      TESTLABS.CONTOSO.COM
    Description:
    An error occurred while applying MBAM policies.
    Volume ID:\\?\Volume{871c5858-2467-4d0b-8c83-d68af8ce10e5}\ 
    Error code:
    0x803D0006 
    Details:
    The operation did not complete within the time allotted.

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          02-09-2013 02:02:04
    Event ID:      18
    Task Category: None
    Level:         Error
    Keywords:     
    User:          SYSTEM
    Computer:      TESTLABS.CONTOSO.COM
    Description:
    Unable to connect to the MBAM Recovery and Hardware service.
    Error code:
    0x803D0010 
    Details:
    The remote endpoint was not reachable.

基本检查：

* 通过按名称和 IP ping MBAM 管理服务器来验证基本连接。 检查是否可以使用 telnet 或 portqry 连接到 MBAM 管理网站或服务端口。

* 验证 IIS 服务是否正在 MBAM 管理和监控服务器上运行，以及 MBAM Web 服务是否侦听在 MBAM 客户端计算机和 () 上配置的同一 `netstat –ano | find "portnumber"` 端口。

* 验证为 MBAM 网站配置的端口号是否使用 IIS 管理器 (inetmgr) 。 确保端口号与客户端侦听的端口号相同。 确保端口号未由另一个应用程序共享。 例如，服务器上另一个应用程序不应使用相同的端口。

* 如果存在防火墙，请确保端口在防火墙或代理服务器中打开。

* 如果客户端和服务器之间的通信是安全的，请确保使用有效的 SSL 证书。

* 验证 Web 服务器与数据要数据库服务器插入的服务器之间的网络连接。 您可以使用 ODBC 数据源管理员检查从 Web 服务器到 数据库服务器的数据库连接。 有关SQL Server疑难解答的详细信息，请参阅如何连接到 SQL Server 数据库引擎[。](https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx)

#### <a name="troubleshooting-the-connectivity-issue"></a>连接问题疑难解答

确保客户端上配置的服务 URL 正确。 从注册表中复制 KeyRecoveryServiceEndPoint ** (HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement) ** URL 的值，Internet Explorer。

同样，复制 StatusReportingServiceEndpoint ** (HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement) ** URL 的值，Internet Explorer。

> [!Note]
> 如果无法从客户端计算机浏览到 URL，应测试从客户端到运行 IIS 的服务器的基本网络连接。 请参阅上一节中的点 1、2、3 和 4。

此外，查看管理和监控服务器上应用程序日志是否有错误。

您可以在客户端和服务器之间进行并发网络跟踪，并查看跟踪以确定客户端代理与 MBAM 管理服务器之间的连接失败的原因。

> [!Note]
> 如果可以从客户端计算机浏览到服务 URL，并且 MBAM 管理事件日志中存在连接错误条目，这可能是因为管理服务器和服务器之间的连接数据库服务器。

如果可以成功浏览到这两个服务 URL，并且客户端和正在运行的服务器之间具有连接，IIS 将正常工作。 但是，运行 IIS 的服务器与运行 IIS 的服务器之间的通信数据库服务器。

MBAM 服务可能无法连接到 数据库服务器，因为网络问题或不正确的数据库连接字符串设置。 查看管理和监控服务器上应用程序日志。 您可能会看到来自 2.0.50727.0 ASP.NET 2.0.50727.0 的错误条目或警告，这些错误条目或警告类似于以下日志条目：

    Log Name:      Application
    Source:        ASP.NET 2.0.50727.0
    Date:          7/11/2013 6:16:34 PM
    Event ID:      1310
    Task Category: Web Event
    Level:         Warning
    Keywords:      Classic
    User:          N/A
    Computer:      MBAM2-Admin.contoso.com
    Description:
    Event code: 100001
    Event message: SQL error occurred
    Event time: 7/11/2013 6:16:34 PM
    Event time (UTC): 7/11/2013 12:46:34 PM
    Event ID: 6615fb8eb9d54e778b933d5bb7ca91ed
    Event sequence: 2
    Event occurrence: 1
    Event detail code: 0 
    Application information:
        Application domain: /LM/W3SVC/2/ROOT/MBAMAdministrationService-1-130180202570338699
        Trust level: Full
        Application Virtual Path: /MBAMAdministrationService
        Application Path: C:\inetpub\Microsoft BitLocker Management Solution\Administration Service\
        Machine name: MBAM2-ADMIN 
    
    Process information:
        Process ID: 1940
        Process name: w3wp.exe
        Account name: NT AUTHORITY\NETWORK SERVICE 
    
    Exception information:
        Exception type: SqlException
        Exception message: A network-related or instance-specific error occurred while establishing a connection to SQL Server. The server was not found or was not accessible. Verify that the instance name is correct and that SQL Server is configured to allow remote connections. (provider: Named Pipes Provider, error: 40 - Could not open a connection to SQL Server) 
    
    Request information:
        Request URL: 
        Request path: 
        User host address: 
        User: 
        Is authenticated: False
        Authentication Type: 
        Thread account name: NT AUTHORITY\NETWORK SERVICE 
    
    Thread information:
        Thread ID: 7
        Thread account name: NT AUTHORITY\NETWORK SERVICE
        Is impersonating: False
        Stack trace:    at System.Data.SqlClient.SqlInternalConnection.OnError(SqlException exception, Boolean breakConnection)
       at System.Data.SqlClient.TdsParser.ThrowExceptionAndWarning(TdsParserStateObject stateObj)
       at System.Data.SqlClient.TdsParser.Connect(ServerInfo serverInfo, SqlInternalConnectionTds connHandler, Boolean ignoreSniOpenTimeout, Int64 timerExpire, Boolean encrypt, Boolean trustServerCert, Boolean integratedSecurity, SqlConnection owningObject)
       at System.Data.SqlClient.SqlInternalConnectionTds.AttemptOneLogin(ServerInfo serverInfo, String newPassword, Boolean ignoreSniOpenTimeout, Int64 timerExpire, SqlConnection owningObject)
       at System.Data.SqlClient.SqlInternalConnectionTds.LoginNoFailover(String host, String newPassword, Boolean redirectedUserInstance, SqlConnection owningObject, SqlConnectionString connectionOptions, Int64 timerStart)
       at System.Data.SqlClient.SqlInternalConnectionTds.OpenLoginEnlist(SqlConnection owningObject, SqlConnectionString connectionOptions, String newPassword, Boolean redirectedUserInstance)
       at System.Data.SqlClient.SqlInternalConnectionTds..ctor(DbConnectionPoolIdentity identity, SqlConnectionString connectionOptions, Object providerInfo, String newPassword, SqlConnection owningObject, Boolean redirectedUserInstance)
       at System.Data.SqlClient.SqlConnectionFactory.CreateConnection(DbConnectionOptions options, Object poolGroupProviderInfo, DbConnectionPool pool, DbConnection owningConnection)
       at System.Data.ProviderBase.DbConnectionFactory.CreatePooledConnection(DbConnection owningConnection, DbConnectionPool pool, DbConnectionOptions options)
       at System.Data.ProviderBase.DbConnectionPool.CreateObject(DbConnection owningObject)
       at System.Data.ProviderBase.DbConnectionPool.UserCreateRequest(DbConnection owningObject)
       at System.Data.ProviderBase.DbConnectionPool.GetConnection(DbConnection owningObject)
       at System.Data.ProviderBase.DbConnectionFactory.GetConnection(DbConnection owningConnection)
       at System.Data.ProviderBase.DbConnectionClosed.OpenConnection(DbConnection outerConnection, DbConnectionFactory connectionFactory)
       at System.Data.SqlClient.SqlConnection.Open()
       at System.Data.Linq.SqlClient.SqlConnectionManager.UseConnection(IConnectionUser user)
       at System.Data.Linq.SqlClient.SqlProvider.get_IsSqlCe()
       at System.Data.Linq.SqlClient.SqlProvider.InitializeProviderMode()
       at System.Data.Linq.SqlClient.SqlProvider.System.Data.Linq.Provider.IProvider.Execute(Expression query)
       at System.Data.Linq.DataContext.ExecuteMethodCall(Object instance, MethodInfo methodInfo, Object[] parameters)
       at Microsoft.Mbam.Server.ServiceCommon.KeyRecoveryModelDataContext.GetRecoveryKeyIds(String partialRecoveryKeyId, String reason)
       at Microsoft.Mbam.ApplicationSupportService.AdministrationService.GetRecoveryKeyIds(String partialRecoveryKeyId, String reasonCode)
    
    Custom event details:
        Application: MBAMAdministrationService
        Sql Server:
        Database: MBAM Recovery and Hardware
        Database: MBAM Compliance Status
        Sql ErrorCode: 5
        Error Message: A network-related or instance-specific error occurred while establishing a connection to SQL Server. The server was not found or was not accessible. Verify that the instance name is correct and that SQL Server is configured to allow remote connections. (provider: Named Pipes Provider, error: 40 - Could not open a connection to SQL Server)

#### <a name="possible-causes"></a>可能的原因

##### <a name="cause-1"></a>原因 1

在管理和监控服务器组件的安装过程中，管理员可能指定了无效的数据库实例名称/数据库名称。

可以使用 IIS 管理控制台验证和更正数据库连接字符串。 为此，请打开 IIS 管理器，然后浏览到 Microsoft BitLocker 管理和监控。 对于左侧列出的每个服务，请按照以下步骤更改数据库连接字符串：

1. 在 **"功能视图**"中，双击"**连接字符串"。**

2. 在 **"连接字符串** "页上，选择要更改的连接字符串。

3. 在"**操作"窗格中**，选择"编辑 **"。**

4. 在"**编辑连接字符串**"对话框中，更改要更改的属性，然后选择"确定 **"。**

##### <a name="cause-2"></a>原因 2

SQL Server防火墙中阻止的端口。 验证配置为侦听SQL Server端口号，并确保该端口在管理服务器与服务器之间的防火墙中数据库服务器。

##### <a name="cause-3"></a>原因 3

错误SQL TCP/IP 绑定。 验证SQL上是否SQL Server 配置管理器 TCP/IP 数据库服务器。 MBAM 要求启用 TCP/IP 和命名管道协议以连接到数据库。

##### <a name="cause-4"></a>原因 4

NT Authority\Network Service 帐户或 MBAM 管理服务器的计算机帐户没有连接到 SQL 数据库所需的权限。

在安装程序上安装数据库组件数据库服务器，安装程序会创建两个本地组：MBAM 合规性审核数据库访问和 MBAM 恢复和硬件 DB 访问。

NT Authority\Network Service 帐户、MBAM 管理服务器的计算机帐户以及安装数据库组件的用户将自动添加到这些组中。

这些组在安装过程中被授予对数据库的必需权限。 属于此组的所有用户都会自动获得对数据库的必需权限。

如果满足以下一个或多个条件数据库服务器权限问题，Web 服务可能无法连接到 Web 服务：

* 前面提到的组已从本地组中删除数据库服务器。

* NT Authority\Network Service 帐户和 MBAM 管理服务器的计算机帐户不是这些组的成员。

* 这些组对数据库没有所需的权限。

如果满足之前的任何条件，你将注意到 MBAM 管理和监控服务器上应用程序日志中与权限相关的错误。 在这种情况下，您应手动添加 NT Authority\Network Service 帐户和 MBAM 管理服务器的计算机帐户，并授予他们在使用 SQL 数据库服务器 的 SQL Server Management Studio (上的公共角色 https://msdn.microsoft.com/library/aa337562.aspx) 。

#### <a name="review-the-web-service-logs"></a>查看 Web 服务日志

如果 MBAM 管理服务器上应用程序日志中未记录任何事件，那么应该查看 MBAM 管理和监控服务器上承载的 MBAM Web 服务的 Web 服务日志 (.svclog) 。 您必须使用服务跟踪查看器工具 (SvcTraceViewer.exe) https://msdn.microsoft.com/library/ms732023.aspx 查看日志文件。

应主要调查 RecoveryandHardwareService 和 ComplianceStatusService 的服务跟踪日志。 默认情况下，Web 服务日志位于 C：\inetpub\Microsoft BitLocker Management Solution\Logs 文件夹中。 其中，每个服务在其自己的文件夹下写入其 .svclog 文件。

查看服务跟踪日志中的活动，查看是否有错误或警告条目。 默认情况下，错误条目以红色突出显示。 选择跟踪查看器右窗格中的错误说明以查看有关错误条目的详细信息。 下面是跟踪日志中的示例错误条目：

    <E2ETraceEvent xmlns="http://schemas.microsoft.com/2004/06/E2ETraceEvent">
    <System xmlns="http://schemas.microsoft.com/2004/06/windows/eventlog/system">
    <EventID>15183</EventID>
    <Type>3</Type>
    <SubType Name="Error">0</SubType>
    <Level>2</Level>
    <TimeCreated SystemTime="2013-07-05T14:48:06.2821550Z" />
    <Source Name="Microsoft.Mbam.CoreService" />
    <Correlation ActivityID="{00000000-0000-0000-0000-000000000000}" />
    <Execution ProcessName="w3wp" ProcessID="4332" ThreadID="11" />
    <Channel />
    <Computer>XXXXXXXXXXX</Computer>
    </System>
    <ApplicationData>AddUpdateVolume: While executing sql transaction for add volume to store exception occurred Key Recovery Data Store processing error: Violation of UNIQUE KEY constraint 'UniqueRecoveryKeyId'. Cannot insert duplicate key in object 'RecoveryAndHardwareCore.Keys'. The duplicate key value is (8637036e-b379-4798-bd9e-5a0b36296de3).
    </ApplicationData>
    </E2ETraceEvent>

## <a name="re-installation-or-reconfiguration-of-mbam-infrastructure"></a>重新安装或重新配置 MBAM 基础结构

若要重新安装或重新配置 MBAM 基础结构，你必须了解以下内容：

* 应用程序池帐户

* MBAM 组 (支持人员、高级、报告用户组) 

* MBAM 报告 URL

* SQL Server名称和数据库名称

* MBAM ReadWrite 和 ReadOnly 帐户

### <a name="application-pool-account"></a>应用程序池帐户

若要查找应用程序池帐户，请登录到 MBAM Web 服务器，打开 **"IIS Internet Information Services (管理器) ，** 然后选择"**应用程序池"：**

![应用程序池。](images/troubleshooting-MBAM-installation-1.png)

必须在此帐户中 (SPN) 服务主体名称。 此设置对 MBAM 的功能非常重要。

### <a name="mbam-groups-helpdesk-advanced-report-users-group-and-reports-url"></a>MBAM 组 (支持人员、高级、报告用户组和报告 URL) 

![MBAM 组。](images/troubleshooting-MBAM-installation-2.png)

这将提供支持组、高级支持组、报告用户组和 MBAM 报告 URL 等信息。 MBAM 报告 URL 必须在 MBAM 设置中提供，并且应为：http (s) ：//servername/ReportServer。

### <a name="sql-server-name-and-database-db-names"></a>SQL Server DB 数据库 (数据库) 名称

若要查找托管 MBAM SQL SERVER的名称和实例，请登录到 MBAM Web (IIS) 服务器并浏览到以下注册表子项：

**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MBAM Server\Web**

![Regedit。](images/troubleshooting-MBAM-installation-3.png)

突出显示的部分为连接字符串。 它们应具有SQL Server名称、数据库名称和实例（如果 (名称) ）。

### <a name="mbam-readwrite-and-readonly-accounts"></a>MBAM ReadWrite 和 ReadOnly 帐户

此信息将位于SQL Server数据库中，我们已从 Web 服务器找到该名称。

#### <a name="readwrite-account"></a>ReadWrite 帐户

1. 登录到SQL Management Studio。

2. 右键单击 **"MBAM 恢复和硬件**"，选择 **"属性**"，然后选择"**权限"。**

例如，实验室帐户名称为 **MBAMWrite**。 应用程序池和 ReadWrite 帐户设置为相同。

![SQLDB。](images/troubleshooting-MBAM-installation-4.png)

![DB 属性。](images/troubleshooting-MBAM-installation-5.png)

浏览到 **"安全性**"，然后在"登录**SQL Management Studio"。** 浏览到上一屏幕截图中显示的帐户。

![SQL安全性。](images/troubleshooting-MBAM-installation-6.png)

右键单击帐户，转到"属性"" **用户映射"，** 然后找到 MBAM 恢复和硬件数据库：

![用户映射。](images/troubleshooting-MBAM-installation-7.png)

#### <a name="readonly-account"></a>ReadOnly 帐户

打开SQL Server Reporting Services SSRS Server 上的配置管理器。 选择 **"报告管理器 URL"，** 然后浏览**URL：**

![报表管理器。](images/troubleshooting-MBAM-installation-8.png)

选择 **"Microsoft Bitlocker 管理和监视"：**

![Bitlocker 管理和监控。](images/troubleshooting-MBAM-installation-9.png)

选择 **"马耳他数据源"：**

![DB。](images/troubleshooting-MBAM-installation-10.png)

![马耳他资源。](images/troubleshooting-MBAM-installation-11.png)

在 MbaM 设置中，应具有 ReadOnly 帐户名称，并且应该使用。

## <a name="reference"></a>参考

有关详细信息，请参阅以下文章：

[在独立配置中部署 MBAM 2.5](https://support.microsoft.com/help/3046555)

[Microsoft BitLocker 管理和监控 2.5](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/)
