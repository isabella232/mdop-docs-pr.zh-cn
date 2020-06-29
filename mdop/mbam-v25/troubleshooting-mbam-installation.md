---
title: MBAM 2.5 安装问题疑难解答
description: 介绍如何对 MBAM 2.5 安装问题进行故障排除。
author: Deland-Han
ms.reviewer: dcscontentpm
manager: dansimp
ms.author: delhan
ms.sitesec: library
ms.prod: w10
ms.date: 09/16/2019
ms.openlocfilehash: ed56a87496e09601c44028b7f948eda39143e8c0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798152"
---
# MBAM 2.5 安装问题疑难解答

本文介绍如何在独立配置中对 Microsoft BitLocker 管理和监视（MBAM）2.5 安装问题进行故障排除。

## 引用 MBAM 日志文件以进行疑难解答

MBAM 包括服务器安装、客户端安装和事件的日志记录。 应参考此日志记录进行故障排除。 
 
### MBAM 服务器安装日志文件

MBAM 安装期间，在用户的% temp% 文件夹中，MBAMServerSetup.exe 会生成以下日志文件：<br /> **Microsoft_BitLocker_Administration_and_Monitoring_<14 号> .log**

MBAMServerSetup.exe 记录 MBAM 安装和 MBAM 服务器功能安装期间所执行的操作：<br /> **Microsoft_BitLocker_Administration_and_Monitoring_<14_numbers # C1_0_MBAMServer.msi .log**

MBAMServerSetup.exe 记录安装期间所执行的其他操作。

### MBAM 客户端安装日志文件

客户端安装将记录在% temp% 文件夹（或自定义位置，具体取决于客户端的安装方式）中的以下日志文件中： <br />**MSI \<five random characters\> 日志**

此日志包含在 MBAM 客户端安装期间执行的操作。
 
### MBAM 客户端事件-日志记录频道

MBAM 具有单独的事件日志记录通道。 "管理"、"分析" 和 "操作日志" 文件位于 "**应用程序和服务日志**"  >  **Microsoft**  >  **Windows**  >  **MBAM**下的 "事件查看器" 中。

下表提供了每个事件日志的简要说明。
 
|事件日志| 描述|
|----------|-------|
|Microsoft-Windows-MBAM/Admin|  包含错误消息|
|Microsoft-Windows-MBAM/分析|   包含高级日志记录信息|
|Microsoft-Windows-MBAM/运营|    包含成功消息|

### MBAM 服务器事件-日志记录频道

日志文件位于 "**应用程序和服务日志**"  >  **Microsoft**  >  **Windows**  >  **MBAM**下的 "事件查看器" 中。 下表列出了在 MBAM 2.5 中引入的服务器事件日志：

|事件日志| 描述|
|--------|-------------|
|Microsoft-Windows-MBAM/Admin|  包含错误消息|
|Microsoft-Windows-MBAM/分析|   包含高级日志记录信息|
|Microsoft-Windows-MBAM/运营|    包含成功消息|

### MBAM web 服务日志

每个 MBAM web 服务日志将日志记录信息写入 SVCLOG 文件。 默认情况下，每个 web 服务在 C:\inetpub\Microsoft BitLocker Management Solution\Logs 文件夹中使用其名称的文件夹下写入跟踪文件。

你可以使用服务跟踪查看器工具（Microsoft Visual Studio 的一部分）查看 svclog 跟踪。

## 加密和报告问题疑难解答

本部分包含服务器功能、客户端功能、配置设置和已知问题的疑难解答信息：
 
### MBAM 客户端安装，组策略设置

确定客户端计算机上是否已安装 MBAM 代理。 安装 MBAM 时，它将创建一个名为 "BitLocker 管理客户端服务" 的服务。 此服务配置为自动启动。 确定服务是否正在运行。

请确保在客户端计算机上应用了 MBAM 组策略设置。 如果客户端计算机上应用了组策略设置，则会创建以下注册表子项： **HKEY_LOCAL_MACHINE \software\policies\microsoft\fve\mdopbitlockermanagement**

验证此项是否存在，并使用每个组策略设置的值进行填充。

### 初始延迟期间的 MBAM 代理

MBAM 客户端在安装后将不会立即启动操作。 在 MBAM 代理启动其操作之前，有1至18分钟的初始延迟是随机延迟。 除了初始延迟，还存在至少90分钟的延迟。 （延迟取决于为检查客户端状态的频率配置的组策略设置。）因此，客户端启动操作前的总延迟是*随机启动延迟*  +  *客户端检查频率延迟*。

如果 "操作" 和 "管理员" 事件日志为空，则客户端尚未启动操作，并且处于前面提到的延迟期间。 如果想要绕过延迟，请按照下列步骤操作：
 
1. 停止 BitLocker 管理客户端服务服务。

2. 在**HKEY_LOCAL_MACHINE \software\microsoft\mbam**注册表子项下，创建**NoStartupDelay**注册表值，将其类型设置为 " **REG_DWORD**"，然后将其值设置为**1**。

3. 在 " **HKEY_LOCAL_MACHINE \software\policies\microsoft\fve\mdopbitlockermanagement**" 下，将 " **ClientWakeupFrequency** " 和 " **StatusReportingFrequency** " 值设置为**1**。 当组策略更新位于计算机上后，这些值将还原为其原始设置。

4. 启动 BitLocker 管理客户端服务服务。

服务启动后，如果您在计算机本地登录，但没有错误，您应该收到一分钟内加密计算机的请求。 如果您没有收到请求，您应该查看 MBAM 管理员日志中是否有任何错误条目。

### 计算机没有 TPM 设备，或者 BIOS 中未启用 TPM 设备

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

打开 TPM 管理（tpm），并检查计算机是否具有 TPM 设备。 如果 tpm 未显示设备，请打开 "设备管理器" （devmgmt），然后在 "安全设备" 下检查受信任的平台模块。 如果你看不到受信任的平台模块设备，则可能是由于以下原因之一所示：

* 您的系统没有受信任的平台模块（TPM/Security）设备。

* TPM 设备在 BIOS 中处于禁用状态。

* BIOS 中已启用 TPM 设备，但在 BIOS 中禁用从操作系统设置对 TPM 设备进行管理。

* 你没有为 TPM 设备使用 Microsoft 驱动程序。 查看 "设备管理器" 中列出的设备以识别 Microsoft TPM 设备驱动程序。

如果 TPM 设备未使用 C:\Windows\System32\tpm.sys 驱动程序，你应该通过选择 C:\Windows\Inf\tpm.inf 文件来更新驱动程序。

### 计算机没有有效的系统分区

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

BitLocker 需要系统分区才能启用加密（[在 Windows 7 中为 BitLocker 驱动器加密：常见问题](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-7/ee449438(v=ws.10)?redirectedfrom=MSDN#bkmk_partitions)）。

MBAM 不会自动创建系统分区。 你可以使用 BitLocker 驱动器准备实用工具（bdehdcfg.exe）创建系统分区并移动所需的启动文件。

例如，你可以使用 **% windir% \system32\bdeHdCfg.exe 目标默认大小 300-** 在部署 MBAM 以加密驱动器之前，安静模式准备驱动器。 这需要重启。 如果需要，还可以编写操作脚本。 以下文档介绍了 BitLocker 驱动器准备工具：

[BitLocker 驱动器准备工具说明](https://support.microsoft.com/help/933246)

### 驱动器未格式化为具有兼容的文件系统

[有关 BitLocker 的文件系统要求](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-7/ee449438(v=ws.10)?redirectedfrom=MSDN#bkmk_hsrequirements)，请参阅 TechNet 文章。

### 组策略冲突

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

验证组策略设置，确保 MBAM 组策略设置中没有相冲突的设置。

你应该使用 MDOP MBAM 模板而不是 BitLocker 驱动器加密模板来配置组策略。

例如：

在 "操作系统驱动器加密设置" 下，选择 "TPM" 作为保护器，并选择 "**允许增强的 pin 来启动**"。 这些是冲突设置，因为仅 TPM 保护不需要 PIN 码。 因此，您应该禁用 "增强引脚" 设置。

### 用户可能已请求例外

如果启用了计算机配置 \ 管理模板 \Windows Components\MDOP MBAM （BitLocker Management） \Client Management\Configure 用户豁免策略组策略设置，则会向用户提供请求豁免的选项。

默认情况下，如果用户请求豁免，则豁免将在7天内有效，用户在此期间将不会收到用于加密的提示。 （在策略配置期间，可以增加或减少默认值。）在免除期限结束后，系统会提示用户进行加密。

当计算机处于用户豁免下时，你将在 MBAM Admin 事件日志中看到以下条目：

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

如果要为计算机手动替代用户豁免，请按照下列步骤操作：
 
1. 在以下注册表子项下将 AllowUserExemption 值设置为**0** ： <br />
**HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement**

2. 删除以下注册表子项下除 " **AgentVersion**"、" **EncodedComputerName**" 和 "**已安装**" 之外的所有注册表值：<br />
**HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\MBAM**

    **注意**必须重新启动 MBAM 代理才能使更改生效。

请注意，在将组策略应用到计算机之后，这些值可能会还原为其原始设置。

### WMI 问题

MBAM 使用 win32_encryptablevolume 类的方法来管理 BitLocker。 如果此模块未注册或已损坏，MBAM 客户端将无法正常运行，你将在 MBAM 管理员事件日志中看到以下事件条目：

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

此外，你可能会注意到恢复和硬件策略不适用于错误代码0x8007007e。 这将转换为 "找不到指定的模块"。

若要解决此问题，应使用以下命令重新注册**win32_encryptablevolume**类：

```cmd
mofcomp c:\Windows\System32\wbem\win32_encryptablevolume.mof
```

## MBAM 代理通信问题疑难解答

本部分包含与 MBAM 代理通信相关的以下问题的疑难解答信息：

### 不正确的 MBAM 服务 URL

如果 MBAM 合规性状态服务或恢复和硬件服务的值不正确，你将在客户端计算机上的 MBAM 管理员事件日志中看到类似于以下内容的事件条目：

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

在客户端计算机上的以下注册表子项下验证**KeyRecoveryServiceEndPoint**和**StatusReportingServiceEndpoint**的值： <br />
**HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement**

默认情况下，KeyRecoveryServiceEndPoint （MBAM 恢复和硬件服务终结点）的 URL 采用以下格式： <br />
**http:// \<servername\> ： \<port\> /MBAMRecoveryAndHardwareService/CoreService.svc**

默认情况下，StatusReportingServiceEndpoint （MBAM 状态报告服务终结点）的 URL 采用以下格式：<br />
**http:// \<servername\> ： \<port\> /MBAMComplianceStatusService/StatusReportingService.svc**

> [!Note]
> URL 中不应有空格。

如果服务 URL 不正确，则应在以下组策略设置中更正服务 URL：

**计算机配置**  > **策略**  > **管理模板**  > **Windows 组件**  > **MDOP MBAM （BitLocker 管理）**  > **客户端管理**  > **配置 MBAM 服务**

### 影响 MBAM 管理服务器的连接问题

如果客户端代理和 MBAM 管理服务器之间存在连接问题，MBAM 代理将无法发布对数据库的任何更新。 在这种情况下，你将注意到客户端计算机上 MBAM 管理员事件日志中的连接失败条目：

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

* 通过 ping MBAM 管理服务器的名称和 IP 验证基本连接。 检查你是否可以使用 telnet 或 portqry 连接到 MBAM 管理网站或服务端口。

* 验证 IIS 服务正在 MBAM 管理和监视服务器上运行，并且 MBAM web 服务正在侦听在 MBAM 客户端计算机（）上配置的同一端口 `netstat –ano | find "portnumber"` 。

* 验证为 MBAM 网站配置的端口号是否使用 IIS 管理器（inetmgr）。 请确保端口号与客户端正在其上侦听的端口号相同。 请确保端口号不会被其他应用程序共享。 例如，服务器上的另一个应用程序不应使用同一端口。

* 如果有防火墙，请确保该端口已在防火墙或代理服务器中打开。

* 如果客户端和服务器之间的通信是安全的，请确保使用有效的 SSL 证书。

* 验证 web 服务器与发送数据以用于插入的数据库服务器之间的网络连接。 可以使用 ODBC 数据源管理器检查从 web 服务器到数据库服务器的数据库连接。 有关[连接到 Sql Server 数据库引擎的疑难解答](https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx)的详细信息，请访问详细的 sql server 连接故障排除信息。

#### 解决连接问题

请确保在客户端上配置的服务 URL 正确无误。 从注册表中复制 KeyRecoveryServiceEndPoint 的 URL 的值（**HKEY_LOCAL_MACHINE \software\policies\microsoft\fve\mdopbitlockermanagement**），然后在 Internet Explorer 中打开它。

同样，复制 StatusReportingServiceEndpoint （**HKEY_LOCAL_MACHINE \software\policies\microsoft\fve\mdopbitlockermanagement**）的 URL 的值，然后在 Internet Explorer 中将其打开。

> [!Note]
> 如果无法浏览客户端计算机的 URL，则应测试客户端与运行 IIS 的服务器之间的基本网络连接。 请参阅上一节中的点1、2、3和4。

此外，请查看管理和监视服务器上的应用程序日志，查看是否存在任何错误。

你可以在客户端和服务器之间进行并发网络跟踪，并查看跟踪以确定客户端代理和 MBAM 管理服务器之间连接失败的原因。

> [!Note]
> 如果您可以从客户端计算机浏览到服务 Url，并且 MBAM 管理事件日志中存在连接错误条目，这可能是由于管理服务器和数据库服务器之间的连接失败造成的。

如果您可以成功浏览这两个服务 Url，并且客户端与运行的服务器之间存在连接，则 IIS 正常工作。 但是，在运行 IIS 的服务器和数据库服务器之间的通信中可能存在问题。

由于网络问题或数据库连接字符串设置不正确，MBAM 服务可能无法连接到数据库服务器。 查看管理和监视服务器上的应用程序日志。 您可能会看到来自来源 ASP.NET 2.0.50727.0 的错误条目或警告，类似于以下日志条目：

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

#### 可能的原因

##### 原因1

管理员可能在安装管理和监视服务器组件期间指定了无效的数据库实例名称/数据库名称。

你可以使用 IIS 管理控制台验证和更正数据库连接字符串。 若要执行此操作，请打开 IIS 管理器，然后浏览到 Microsoft BitLocker 管理和监视。 对于左侧列出的每个服务，请按照以下步骤更改数据库连接字符串：

1. 在 "**功能" 视图**中，双击 "**连接字符串**"。

2. 在 "**连接字符串**" 页面上，选择要更改的连接字符串。

3. 在 "**操作**" 窗格中，选择 "**编辑**"。

4. 在 "**编辑连接字符串**" 对话框中，更改要更改的属性，然后选择 **"确定"**。

##### 原因2

防火墙中已阻止 SQL Server 端口。 验证 SQL Server 配置为要侦听的端口号，并确保该端口已在管理服务器和数据库服务器之间的防火墙中打开。

##### 原因3

不正确的 SQL server TCP/IP 绑定。 在数据库服务器上的 SQL Server 配置管理器中验证 SQL TCP/IP 绑定。 MBAM 要求启用 TCP/IP 和命名管道协议以连接到数据库。

##### 原因4

NT Authority\Network 服务帐户或 MBAM 管理服务器的计算机帐户没有连接到 SQL 数据库所需的权限。

在数据库服务器上安装数据库组件期间，安装程序将创建两个本地组： MBAM 合规性审核数据库访问和 MBAM 恢复和硬件数据库访问。

NT Authority\Network 服务帐户、MBAM 管理服务器的计算机帐户和安装数据库组件的用户将自动添加到这些组中。

在安装期间，这些组被授予对数据库所需的权限。 属于该组的所有用户都会自动收到数据库所需的权限。

Web 服务可能无法连接到数据库服务器，因为如果存在以下一种或多种情况，则会出现权限问题：

* 之前提到的组将从数据库服务器上的本地组中删除。

* NT Authority\Network 服务帐户和 MBAM 管理服务器的计算机帐户不是这些组的成员。

* 这些组没有数据库所需的权限。

如果上述任何条件为 true，你将注意 MBAM 管理和监视服务器上的应用程序日志中与权限相关的错误。 在这种情况下，你应该手动添加 NT Authority\Network 服务帐户和 MBAM 管理服务器的计算机帐户，并在使用 SQL Server Management Studio （.）的 SQL 数据库服务器上授予其服务器范围内的公共角色 https://msdn.microsoft.com/library/aa337562.aspx) 。

#### 查看 web 服务日志

如果 MBAM 管理服务器上的应用程序日志中未记录任何事件，现在就可以查看 MBAM 管理和监视服务器上托管的 MBAM web 服务的 web 服务日志（svclog）。 您必须使用服务跟踪查看器工具（SvcTraceViewer.exe） https://msdn.microsoft.com/library/ms732023.aspx 查看日志文件。

你应该首先研究 RecoveryandHardwareService 和 ComplianceStatusService 的服务跟踪日志。 默认情况下，web 服务日志位于 C:\inetpub\Microsoft BitLocker Management Solution\Logs 文件夹中。 在此情况下，每个服务在其自己的文件夹下写入其 svclog 文件。

在服务跟踪日志中查看任何错误或警告条目的活动。 默认情况下，错误条目以红色突出显示。 在跟踪查看器的右窗格中选择 "错误说明"，以查看有关错误条目的详细信息。 以下是跟踪日志中的示例错误条目：

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

## 重新安装或重新配置 MBAM 基础结构

若要重新安装或重新配置 MBAM 基础结构，必须了解以下事项：

* 应用程序池帐户

* MBAM 组（"帮助台"、"高级"、"报表用户" 组）

* MBAM 报表 URL

* SQL Server 名称和数据库名称

* MBAM ReadWrite 和只读帐户

### 应用程序池帐户

若要查找应用程序池帐户，请登录到 MBAM Web 服务器，打开 " **Internet 信息服务（IIS）管理器**"，然后选择 "**应用程序池**"：

![应用程序池](images/troubleshooting-MBAM-installation-1.png)

服务主体名称（SPN）必须在此帐户中设置。 此设置对 MBAM 的功能非常重要。

### MBAM 组（"帮助台"、"高级"、"报表用户" 组和报表 URL）

![MBAM 组](images/troubleshooting-MBAM-installation-2.png)

这将提供如帮助台组、高级帮助台组、报表用户组和 MBAM 报表 URL 等信息。 MBAM 报表 URL 必须在 MBAM 设置中提供，并且应读取为： http （s）：//servername/ReportServer。

### SQL Server 名称和数据库（DB）名称

若要查找托管 MBAM 的 SQL Server 名称和实例，请登录到 MBAM Web （IIS）服务器并浏览到 folowing 注册表子项：

**HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\MBAM Server\Web**

![Regedit.exe](images/troubleshooting-MBAM-installation-3.png)

突出显示的部分是连接字符串。 这些应具有 SQL Server 名称、数据库名称和实例（如果已命名）。

### MBAM ReadWrite 和只读帐户

此信息将位于 SQL Server 数据库中，该数据库已找到来自 web 服务器的名称。

#### ReadWrite 帐户

1. 登录到 SQL Management Studio。

2. 右键单击 " **MBAM 恢复和硬件**"，选择 "**属性**"，然后选择 "**权限**"。

例如，实验室帐户名称为**MBAMWrite**。 应用程序池和读写帐户设置为相同。

![SQL 数据库](images/troubleshooting-MBAM-installation-4.png)

![DB 属性](images/troubleshooting-MBAM-installation-5.png)

在 SQL Management Studio 中浏览到 "**安全性**"，然后按 "**登录**"。 浏览到上一个屏幕截图中显示的帐户。

![SQL 安全性](images/troubleshooting-MBAM-installation-6.png)

右键单击帐户，转到 "**属性用户映射**"，然后找到 MBAM 恢复和硬件数据库：

![用户映射](images/troubleshooting-MBAM-installation-7.png)

#### 只读帐户

在 SSRS 服务器上打开 SQL Server Reporting Services 配置管理器。 选择 "**报表管理器 URL**"，然后浏览**url**：

![报表管理器](images/troubleshooting-MBAM-installation-8.png)

选择 " **Microsoft Bitlocker 管理和监视**"：

![Bitlocker 管理和监视](images/troubleshooting-MBAM-installation-9.png)

选择**MaltaDatasource**：

![It](images/troubleshooting-MBAM-installation-10.png)

![MaltaDatasource](images/troubleshooting-MBAM-installation-11.png)

MaltaDataSource 应具有只读帐户名称，并且应在 MBAM 设置中使用。

## 参考

有关详细信息，请参阅以下文章：

[在独立配置中部署 MBAM 2。5](https://support.microsoft.com/help/3046555)

[Microsoft BitLocker 管理和监控 2.5](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/)
