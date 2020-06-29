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
# <span data-ttu-id="6304d-103">MBAM 2.0 发行说明</span><span class="sxs-lookup"><span data-stu-id="6304d-103">Release Notes for MBAM 2.0</span></span>


<span data-ttu-id="6304d-104">若要搜索这些发行说明，请按 Ctrl + F。</span><span class="sxs-lookup"><span data-stu-id="6304d-104">To search these release notes, press Ctrl+F.</span></span>

<span data-ttu-id="6304d-105">在安装 Microsoft BitLockerAdministration 和监控（MBAM）2.0 之前，请先阅读这些发行说明。</span><span class="sxs-lookup"><span data-stu-id="6304d-105">Read these release notes thoroughly before you install Microsoft BitLockerAdministration and Monitoring(MBAM)2.0.</span></span> <span data-ttu-id="6304d-106">这些发行说明包含成功安装 BitLockerAdministration 和监控2.0 所需的信息，其中包含产品文档中不可用的信息。</span><span class="sxs-lookup"><span data-stu-id="6304d-106">These release notes contain information that is required to successfully install BitLockerAdministration and Monitoring2.0 and contain information that is not available in the product documentation.</span></span> <span data-ttu-id="6304d-107">如果这些发行说明和其他 MBAM 2.0 文档之间存在差异，则应将最新更改视为权威。</span><span class="sxs-lookup"><span data-stu-id="6304d-107">If there is a difference between these release notes and other MBAM2.0 documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="6304d-108">这些发行说明取代了本产品附带的内容。</span><span class="sxs-lookup"><span data-stu-id="6304d-108">These release notes supersede the content that is included with this product.</span></span>

## <a href="" id="---------mbam-2-0-known-issues"></a> <span data-ttu-id="6304d-109">MBAM 2.0 已知问题</span><span class="sxs-lookup"><span data-stu-id="6304d-109">MBAM2.0 Known Issues</span></span>


<span data-ttu-id="6304d-110">本部分包含适用于 MBAM 2.0 的发行说明。</span><span class="sxs-lookup"><span data-stu-id="6304d-110">This section contains release notes for MBAM2.0.</span></span>

### <span data-ttu-id="6304d-111">当您在 Microsoft System Center Configuration Manager 2007 上运行 MBAM 时，计算机名称字段可能不会显示在 BitLocker 计算机合规性和 BitLocker 企业合规性详细信息报告中</span><span class="sxs-lookup"><span data-stu-id="6304d-111">Computer Name field may not appear in the BitLocker Computer Compliance and BitLocker Enterprise Compliance Details reports when you run MBAM with Microsoft System Center Configuration Manager 2007</span></span>

<span data-ttu-id="6304d-112">将 MBAM 与 Configuration Manager 2007 配合使用时，"计算机名称" 域在 BitLocker 计算机合规性和 BitLocker 企业合规性详细信息报告中可能为空。</span><span class="sxs-lookup"><span data-stu-id="6304d-112">The Computer Name field may be blank in the BitLocker Computer Compliance and BitLocker Enterprise Compliance Details reports when you use MBAM with Configuration Manager 2007.</span></span>

<span data-ttu-id="6304d-113">解决方法：无。</span><span class="sxs-lookup"><span data-stu-id="6304d-113">WORKAROUND: None.</span></span>

### <span data-ttu-id="6304d-114">升级独立的 MBAM 服务器基础结构后，无法更新企业合规性报告</span><span class="sxs-lookup"><span data-stu-id="6304d-114">Enterprise Compliance Report fails to update after you upgrade the Stand-alone MBAM server infrastructure</span></span>

<span data-ttu-id="6304d-115">如果你使用的是 MBAM 独立拓扑，并且将服务器基础结构从版本1.0 升级到2.0，则无法更新企业合规性报告。</span><span class="sxs-lookup"><span data-stu-id="6304d-115">If you are using the MBAM Stand-alone topology, and you upgrade the server infrastructure from version 1.0 to 2.0, the Enterprise Compliance Report fails to update.</span></span>

<span data-ttu-id="6304d-116">解决方法：升级后，针对合规性和审核数据库运行以下脚本：</span><span class="sxs-lookup"><span data-stu-id="6304d-116">WORKAROUND: After the upgrade, run the following script on the Compliance and Audit Database:</span></span>

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

### <span data-ttu-id="6304d-117">如果未在 SSRS 中配置 SSL，技术支持门户中的报表将显示警告</span><span class="sxs-lookup"><span data-stu-id="6304d-117">Reports in the Help Desk Portal display a warning if SSL is not configured in SSRS</span></span>

<span data-ttu-id="6304d-118">如果 SQL Server Reporting Services （SSRS）未配置为使用安全套接字层（SSL），则在安装 MBAM 服务器时，报表的 URL 将设置为 HTTP，而不是 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="6304d-118">If SQL Server Reporting Services (SSRS) was not configured to use Secure Socket Layer (SSL), the URL for the reports will be set to HTTP instead of HTTPS when you install the MBAM Server.</span></span> <span data-ttu-id="6304d-119">如果您随后浏览到帮助台门户并选择报表，则会显示以下消息： "仅显示安全内容"。</span><span class="sxs-lookup"><span data-stu-id="6304d-119">If you then browse to the Help Desk Portal and select a report, the following message displays: “Only Secure Content is Displayed.”</span></span>

<span data-ttu-id="6304d-120">解决方法：若要显示报表，请单击 "**显示所有内容**"。</span><span class="sxs-lookup"><span data-stu-id="6304d-120">WORKAROUND: To show the report, click **Show All Content**.</span></span> <span data-ttu-id="6304d-121">若要解决此问题，请转到安装了 SQL Server Reporting Services 的 MBAM 计算机，运行**Reporting Services 配置管理器**，然后单击 " **Web 服务 URL**"。</span><span class="sxs-lookup"><span data-stu-id="6304d-121">To address this issue, go to the MBAM computer where SQL Server Reporting Services is installed, run **Reporting Services Configuration Manager**, and then click **Web Service URL**.</span></span> <span data-ttu-id="6304d-122">为服务器选择相应的 SSL 证书，输入相应的 SSL 端口（默认端口为443），然后单击 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="6304d-122">Select the appropriate SSL certificate for the server, enter the appropriate SSL port (the default port is 443), and then click **Apply**.</span></span>

### <span data-ttu-id="6304d-123">不支持 Configuration Manager 数据库的非默认实例</span><span class="sxs-lookup"><span data-stu-id="6304d-123">Non-default instances of the Configuration Manager database are not supported</span></span>

<span data-ttu-id="6304d-124">MBAM 仅在 Configuration Manager 2007 和 SystemCenter2012 ConfigurationManager 中查看 Configuration Manager 数据库的默认实例。</span><span class="sxs-lookup"><span data-stu-id="6304d-124">MBAM looks only for the default instance of the Configuration Manager database in Configuration Manager 2007 and SystemCenter2012 ConfigurationManager.</span></span> <span data-ttu-id="6304d-125">如果使用非默认实例，则无法安装 MBAM。</span><span class="sxs-lookup"><span data-stu-id="6304d-125">If you use a non-default instance, you cannot install MBAM.</span></span>

<span data-ttu-id="6304d-126">解决方法：无。</span><span class="sxs-lookup"><span data-stu-id="6304d-126">WORKAROUND: None.</span></span>

### <a href="" id="clicking--back--in-the-compliance-summary-report-might-throw-an-error"></a><span data-ttu-id="6304d-127">单击 "兼容性摘要" 报表中的 "后退" 可能会引发错误</span><span class="sxs-lookup"><span data-stu-id="6304d-127">Clicking “Back” in the Compliance Summary report might throw an error</span></span>

<span data-ttu-id="6304d-128">如果向下钻取到合规性摘要报表，然后单击 SSRS 报表中的**Back**链接，则可能会引发错误。</span><span class="sxs-lookup"><span data-stu-id="6304d-128">If you drill down into a Compliance Summary report, and then click the **Back** link in the SSRS report, an error might be thrown.</span></span>

<span data-ttu-id="6304d-129">解决方法：无。</span><span class="sxs-lookup"><span data-stu-id="6304d-129">WORKAROUND: None.</span></span>

### <span data-ttu-id="6304d-130">"仅使用空间" 加密不会正常工作</span><span class="sxs-lookup"><span data-stu-id="6304d-130">Used Space Only Encryption does not work correctly</span></span>

<span data-ttu-id="6304d-131">如果你在安装 MBAM 客户端后首次加密计算机，并且已将组策略对象设置为仅实现已使用的空间加密，则 MBAM 会错误地加密整个磁盘，而不是仅加密磁盘的已用空间。</span><span class="sxs-lookup"><span data-stu-id="6304d-131">If you encrypt a computer for the first time after you install the MBAM Client, and you have set a Group Policy Object to implement Used Space Only encryption, MBAM erroneously encrypts the entire disk instead of encrypting only the disk’s used space.</span></span> <span data-ttu-id="6304d-132">如果在安装 MBAM 客户端时已对计算机进行了加密，并且设置了相同的组策略对象，则加密会正常工作，并且只加密计算机上已使用的磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="6304d-132">If a computer is already encrypted when you install the MBAM Client, and you have set the same Group Policy Object, the encryption works correctly and encrypts only the used disk space on your computer.</span></span>

<span data-ttu-id="6304d-133">解决方法：无。</span><span class="sxs-lookup"><span data-stu-id="6304d-133">WORKAROUND: None.</span></span>

### <span data-ttu-id="6304d-134">密码强度在计算机合规性报告上显示错误</span><span class="sxs-lookup"><span data-stu-id="6304d-134">Cipher strength displays incorrectly on the Computer Compliance report</span></span>

<span data-ttu-id="6304d-135">如果你未在 "**选择驱动器加密方法" 和 "密码强度**" 组策略对象中设置特定的密码强度，则配置管理器集成拓扑中的计算机合规性报告始终显示密码强度的 "unknown"，即使密码强度使用默认的128位加密也是如此。</span><span class="sxs-lookup"><span data-stu-id="6304d-135">If you do not set a specific cipher strength in the **Choose drive encryption method and cipher strength** Group Policy Object, the Computer Compliance report in the Configuration Manager Integration topology always displays “unknown” for the cipher strength, even when the cipher strength uses the default of 128-bit encryption.</span></span> <span data-ttu-id="6304d-136">如果在组策略对象中设置了特定的密码强度，则报表将显示正确的密码强度。</span><span class="sxs-lookup"><span data-stu-id="6304d-136">The report displays the correct cipher strength if you set a specific cipher strength in the Group Policy Object.</span></span>

<span data-ttu-id="6304d-137">解决方法：在 "**选择驱动器加密方法" 和 "密码强度**" 组策略对象中始终设置特定的密码强度。</span><span class="sxs-lookup"><span data-stu-id="6304d-137">WORKAROUND: Always set a specific cipher strength in the **Choose drive encryption method and cipher strength** Group Policy Object.</span></span>

### <span data-ttu-id="6304d-138">合规性状态按驱动器类型分布在更新配置项目后显示旧数据</span><span class="sxs-lookup"><span data-stu-id="6304d-138">Compliance Status Distribution By Drive Type displays old data after you update configuration items</span></span>

<span data-ttu-id="6304d-139">在 SystemCenter2012 ConfigurationManager 中更新 MBAM 配置项目后，"BitLocker 企业合规性" 仪表板上的 "驱动器类型" 分布图中的合规性状态分布将显示基于来自旧版本的配置项目的信息的数据。</span><span class="sxs-lookup"><span data-stu-id="6304d-139">After you update MBAM configuration items in SystemCenter2012 ConfigurationManager, the Compliance Status Distribution By Drive Type bar chart on the BitLocker Enterprise Compliance Dashboard shows data that is based on information from old versions of the configuration items.</span></span>

<span data-ttu-id="6304d-140">解决方法：无。</span><span class="sxs-lookup"><span data-stu-id="6304d-140">WORKAROUND: None.</span></span> <span data-ttu-id="6304d-141">不支持修改 MBAM 配置项目，并且报表可能不会按预期显示。</span><span class="sxs-lookup"><span data-stu-id="6304d-141">Modification of the MBAM configuration items is not supported, and the report might not appear as expected.</span></span>

### <span data-ttu-id="6304d-142">增强的安全配置可能导致报表显示不正确</span><span class="sxs-lookup"><span data-stu-id="6304d-142">Enhanced Security Configuration may cause reports to display incorrectly</span></span>

<span data-ttu-id="6304d-143">如果 Internet Explorer 增强的安全配置（ESC）处于打开状态，则当你尝试在 MBAM 服务器上查看报告时，可能会显示 "拒绝访问" 消息。</span><span class="sxs-lookup"><span data-stu-id="6304d-143">If Internet Explorer Enhanced Security Configuration (ESC) is turned on, an “Access Denied” message might appear when you try to view reports on the MBAM Server.</span></span> <span data-ttu-id="6304d-144">默认情况下，按 ESC 可保护服务器，方法是降低服务器对通过 web 内容和应用程序脚本可能发生的潜在攻击的影响。</span><span class="sxs-lookup"><span data-stu-id="6304d-144">By default, ESC is turned on to protect the server by decreasing the server’s exposure to potential attacks that can occur through web content and application scripts.</span></span>

<span data-ttu-id="6304d-145">解决方法：如果在 MBAM 服务器上尝试查看报表时出现 "拒绝访问" 消息，则可以在映像中设置组策略对象或手动更改默认设置，以禁用增强的安全配置。</span><span class="sxs-lookup"><span data-stu-id="6304d-145">WORKAROUND: If the “Access Denied” message appears when you try to view reports on the MBAM Server, you can set a Group Policy Object or change the default manually in your image to disable Enhanced Security Configuration.</span></span> <span data-ttu-id="6304d-146">您也可以从另一台计算机上查看未启用 ESC 的报告。</span><span class="sxs-lookup"><span data-stu-id="6304d-146">You can also alternatively view the reports from another computer on which ESC is not enabled.</span></span>

### <span data-ttu-id="6304d-147">从 SQL Server 2008 升级到 SQL Server 2012 时，MBAM Server 安装失败</span><span class="sxs-lookup"><span data-stu-id="6304d-147">MBAM Server installation fails when you upgrade from SQL Server 2008 to SQL Server 2012</span></span>

<span data-ttu-id="6304d-148">如果从 SQL Server 2008 升级到 SQL Server 2012，然后尝试安装合规性和审核数据库或恢复数据库，则安装将失败并回退。</span><span class="sxs-lookup"><span data-stu-id="6304d-148">If you upgrade from SQL Server 2008 to SQL Server 2012, and then try to install the Compliance and Audit Database or the Recovery Database, the installation fails and rolls back.</span></span> <span data-ttu-id="6304d-149">发生故障的原因是在 SQL 升级期间删除了所需的 SQLCMD.exe 文件，但 MBAM 安装程序找不到该文件。</span><span class="sxs-lookup"><span data-stu-id="6304d-149">The failure occurs because the required SQLCMD.exe file was removed during the SQL upgrade and cannot be found by the MBAM installer.</span></span> <span data-ttu-id="6304d-150">MSI 日志文件行可能看起来类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="6304d-150">The MSI log file lines may look similar to the following:</span></span>

<span data-ttu-id="6304d-151">RunDbInstallScript Recovery Db CA： BinDir-E:\\MSSQL\\100\\Tools\\Binn\\SqlCmd.exeRunDbInstallScript db ca： dbInstance-xxxxxx\\I01RunDbInstallScript sqlScript C:\\program files BitLocker 管理和 Files\\Microsoft\\Microsoft 恢复 Db CA： dbName-MONITORING\\SETUP\\KEYRECOVERY.SQLRUNDBINSTALLSCRIPT \ _Recovery \ _and \ _HardwareRunDbInstallScript 恢复 db ca： MBAM-defaultFileName \ _Recovery \ _and _HardwareRunDbInstallScript 恢复 Db CA： MBAM-defaultDataPathI01\\MSSQL\\DATA\\RunDbInstallScript Recovery Db CA： defaultLogPath-K:\\MSSQL\\MSSQL10。I01\\MSSQL\\Data\\RunDbInstallScript： scriptLogPath-C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\InstallKeyComplianceDatabase.log-e-E S xxxxxxx\\I01-i "C:\\program files Files\\Microsoft\\Microsoft BitLocker 管理和 Monitoring\\Setup\\KeyRecovery.sql"-v DatabaseName = "MBAM \ _Recovery \ _and \ _Hardware" DefaultFileName = "MBAM _Recovery \ _and" DefaultDataPath = "F:\\MSSQL\\MSSQL10。I01\\MSSQL\\DATA\\ "DefaultLogPath =" K:\\MSSQL\\MSSQL10。I01\\MSSQL\\Data\\ "-o" C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\InstallKeyComplianceDatabase.log "RunDbInstallScript 恢复数据库 CA：正在开始运行恢复数据库安装 scriptRunDbInstallScript 恢复数据库 CA： Sqlcmd 日志文件位于 C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\\\InstallKeyRecoveryDatabase.logRunDbInstallScript 恢复数据库 CA 异常：安装恢复数据库自定义操作命令行输出异常：系统找不到指定的文件</span><span class="sxs-lookup"><span data-stu-id="6304d-151">RunDbInstallScript Recovery Db CA: BinDir - E:\\MSSQL\\100\\Tools\\Binn\\SqlCmd.exeRunDbInstallScript Recovery Db CA: dbInstance - xxxxxx\\I01RunDbInstallScript Recovery Db CA: sqlScript- C:\\Program Files\\Microsoft\\Microsoft BitLocker Administration and Monitoring\\Setup\\KeyRecovery.sqlRunDbInstallScript Recovery Db CA: dbName- MBAM\_Recovery\_and\_HardwareRunDbInstallScript Recovery Db CA: defaultFileName- MBAM\_Recovery\_and\_HardwareRunDbInstallScript Recovery Db CA: defaultDataPath- F:\\MSSQL\\MSSQL10.I01\\MSSQL\\DATA\\RunDbInstallScript Recovery Db CA: defaultLogPath- K:\\MSSQL\\MSSQL10.I01\\MSSQL\\Data\\RunDbInstallScript Recovery Db CA: scriptLogPath - C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\InstallKeyComplianceDatabase.log-e -E -S xxxxxxx\\I01 -i "C:\\Program Files\\Microsoft\\Microsoft BitLocker Administration and Monitoring\\Setup\\KeyRecovery.sql" -v DatabaseName="MBAM\_Recovery\_and\_Hardware" DefaultFileName="MBAM\_Recovery\_and\_Hardware" DefaultDataPath="F:\\MSSQL\\MSSQL10.I01\\MSSQL\\DATA\\" DefaultLogPath="K:\\MSSQL\\MSSQL10.I01\\MSSQL\\Data\\" -o "C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\InstallKeyComplianceDatabase.log"RunDbInstallScript Recovery Db CA:Starting to run the Recovery database install scriptRunDbInstallScript Recovery Db CA: Sqlcmd log file is located in C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\\\InstallKeyRecoveryDatabase.logRunDbInstallScript Recovery Db CA Exception: Install Recovery database Custom Action command line output Exception: The system cannot find the file specified</span></span>

<span data-ttu-id="6304d-152">MBAM 服务器 Windows Installer 是硬编码的，可通过在 HKLM\\Software\\Microsoft\\Microsoft SQL Server\\100\\Tools\\ClientSetup. 下的注册表中查找 Path 字符串值来查找 SQLCMD.exe 路径。</span><span class="sxs-lookup"><span data-stu-id="6304d-152">The MBAM Server Windows Installer is hardcoded to find the SQLCMD.exe path by looking in the Path string value in the registry under HKLM\\Software\\Microsoft\\Microsoft SQL Server\\100\\Tools\\ClientSetup.</span></span> <span data-ttu-id="6304d-153">从 SQL Server 2008 迁移到 SQL Server 2012 期间仍然存在该键，但由于 SQL 升级过程删除了该文件，因此由数据值引用的路径不包含 SQLCMD.exe 文件。</span><span class="sxs-lookup"><span data-stu-id="6304d-153">The key is still present during the migration from SQL Server 2008 to SQL Server 2012, but the path that is referenced by the data value does not contain the SQLCMD.exe file, because the SQL upgrade process removed the file.</span></span>

<span data-ttu-id="6304d-154">解决方法：临时将 HKLM\\Software\\Microsoft\\Microsoft SQL Server\\100\\Tools\\ClientSetup Path 字符串值重命名为**Path \ _old**，然后重新运行 MBAM Server Windows Installer。</span><span class="sxs-lookup"><span data-stu-id="6304d-154">WORKAROUND: Temporarily rename the HKLM\\Software\\Microsoft\\Microsoft SQL Server\\100\\Tools\\ClientSetup Path string value to **Path\_old**, and then re-run the MBAM Server Windows Installer.</span></span> <span data-ttu-id="6304d-155">当安装成功完成并在 SQL Server 2012 中创建数据库时，请将**路径 \ _old**值重命名为**path**。</span><span class="sxs-lookup"><span data-stu-id="6304d-155">When the installation completes successfully and creates the databases in SQL Server 2012, rename the **Path\_old** value to **Path**.</span></span>

## <span data-ttu-id="6304d-156">MBAM 2.0 版修补程序和知识库文章</span><span class="sxs-lookup"><span data-stu-id="6304d-156">Hotfixes and Knowledge Base articles for MBAM2.0</span></span>


<span data-ttu-id="6304d-157">本部分包含适用于 MBAM 2.0 的修补程序和知识库文章。</span><span class="sxs-lookup"><span data-stu-id="6304d-157">This section contains hotfixes and KB articles for MBAM2.0.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="6304d-158">知识库文章</span><span class="sxs-lookup"><span data-stu-id="6304d-158">KB Article</span></span></strong></th>
<th align="left"><span data-ttu-id="6304d-159">Title</span><span class="sxs-lookup"><span data-stu-id="6304d-159">Title</span></span></th>
<th align="left"><strong><span data-ttu-id="6304d-160">链接</span><span class="sxs-lookup"><span data-stu-id="6304d-160">Link</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6304d-161">2831166</span><span class="sxs-lookup"><span data-stu-id="6304d-161">2831166</span></span></p></td>
<td align="left"><p><span data-ttu-id="6304d-162">安装 Microsoft BitLocker 管理和监视（MBAM）2.0 失败， &quot; 已安装 System CENTER CM 对象&quot;</span><span class="sxs-lookup"><span data-stu-id="6304d-162">Installing Microsoft BitLocker Administration and Monitoring (MBAM) 2.0 fails with &quot;System Center CM Objects Already Installed&quot;</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2831166/EN-US" data-raw-source="[support.microsoft.com/kb/2831166/EN-US](https://support.microsoft.com/kb/2831166/EN-US)"><span data-ttu-id="6304d-163">support.microsoft.com/kb/2831166/EN-US</span><span class="sxs-lookup"><span data-stu-id="6304d-163">support.microsoft.com/kb/2831166/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6304d-164">2870849</span><span class="sxs-lookup"><span data-stu-id="6304d-164">2870849</span></span></p></td>
<td align="left"><p><span data-ttu-id="6304d-165">用户无法使用 MBAM 2.0 自助服务门户检索 BitLocker 恢复密钥</span><span class="sxs-lookup"><span data-stu-id="6304d-165">Users cannot retrieve BitLocker Recovery key using MBAM2.0 Self Service Portal</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2870849/EN-US" data-raw-source="[support.microsoft.com/kb/2870849/EN-US](https://support.microsoft.com/kb/2870849/EN-US)"><span data-ttu-id="6304d-166">support.microsoft.com/kb/2870849/EN-US</span><span class="sxs-lookup"><span data-stu-id="6304d-166">support.microsoft.com/kb/2870849/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6304d-167">2756402</span><span class="sxs-lookup"><span data-stu-id="6304d-167">2756402</span></span></p></td>
<td align="left"><p><span data-ttu-id="6304d-168">MBAM 客户端将失败，并出现事件描述中的事件 ID 4 和错误代码0x8004100E</span><span class="sxs-lookup"><span data-stu-id="6304d-168">MBAM client would fail with Event ID 4 and error code 0x8004100E in the Event description</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2756402/EN-US" data-raw-source="[support.microsoft.com/kb/2756402/EN-US](https://support.microsoft.com/kb/2756402/EN-US)"><span data-ttu-id="6304d-169">support.microsoft.com/kb/2756402/EN-US</span><span class="sxs-lookup"><span data-stu-id="6304d-169">support.microsoft.com/kb/2756402/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6304d-170">2620287</span><span class="sxs-lookup"><span data-stu-id="6304d-170">2620287</span></span></p></td>
<td align="left"><p><span data-ttu-id="6304d-171">单击 MBAM 中的 "报表" 选项卡时，出现 "/Reports" 应用程序中的 "服务器错误" 错误消息</span><span class="sxs-lookup"><span data-stu-id="6304d-171">Error Message “Server Error in ‘/Reports’ Application” When You Click Reports Tab in MBAM</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2620287/EN-US" data-raw-source="[support.microsoft.com/kb/2620287/EN-US](https://support.microsoft.com/kb/2620287/EN-US)"><span data-ttu-id="6304d-172">support.microsoft.com/kb/2620287/EN-US</span><span class="sxs-lookup"><span data-stu-id="6304d-172">support.microsoft.com/kb/2620287/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6304d-173">2639518</span><span class="sxs-lookup"><span data-stu-id="6304d-173">2639518</span></span></p></td>
<td align="left"><p><span data-ttu-id="6304d-174">在 MBAM 中打开企业或计算机合规性报告时出错</span><span class="sxs-lookup"><span data-stu-id="6304d-174">Error opening Enterprise or Computer Compliance Reports in MBAM</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2639518/EN-US" data-raw-source="[support.microsoft.com/kb/2639518/EN-US](https://support.microsoft.com/kb/2639518/EN-US)"><span data-ttu-id="6304d-175">support.microsoft.com/kb/2639518/EN-US</span><span class="sxs-lookup"><span data-stu-id="6304d-175">support.microsoft.com/kb/2639518/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6304d-176">2620269</span><span class="sxs-lookup"><span data-stu-id="6304d-176">2620269</span></span></p></td>
<td align="left"><p><span data-ttu-id="6304d-177">MBAM 企业报告未获得更新</span><span class="sxs-lookup"><span data-stu-id="6304d-177">MBAM Enterprise Reporting Not Getting Updated</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2620269/EN-US" data-raw-source="[support.microsoft.com/kb/2620269/EN-US](https://support.microsoft.com/kb/2620269/EN-US)"><span data-ttu-id="6304d-178">support.microsoft.com/kb/2620269/EN-US</span><span class="sxs-lookup"><span data-stu-id="6304d-178">support.microsoft.com/kb/2620269/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6304d-179">2712461</span><span class="sxs-lookup"><span data-stu-id="6304d-179">2712461</span></span></p></td>
<td align="left"><p><span data-ttu-id="6304d-180">不支持在域控制器上安装 MBAM</span><span class="sxs-lookup"><span data-stu-id="6304d-180">Installing MBAM on a Domain Controller is not supported</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2712461/EN-US" data-raw-source="[support.microsoft.com/kb/2712461/EN-US](https://support.microsoft.com/kb/2712461/EN-US)"><span data-ttu-id="6304d-181">support.microsoft.com/kb/2712461/EN-US</span><span class="sxs-lookup"><span data-stu-id="6304d-181">support.microsoft.com/kb/2712461/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6304d-182">2876732</span><span class="sxs-lookup"><span data-stu-id="6304d-182">2876732</span></span></p></td>
<td align="left"><p><span data-ttu-id="6304d-183">在 MBAM 2.0 的独立或 Configuration Manager 集成设置期间收到错误代码0x80071a90</span><span class="sxs-lookup"><span data-stu-id="6304d-183">You receive error code 0x80071a90 during Standalone or Configuration Manager Integration setup of MBAM2.0</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2876732/EN-US" data-raw-source="[support.microsoft.com/kb/2876732/EN-US](https://support.microsoft.com/kb/2876732/EN-US)"><span data-ttu-id="6304d-184">support.microsoft.com/kb/2876732/EN-US</span><span class="sxs-lookup"><span data-stu-id="6304d-184">support.microsoft.com/kb/2876732/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6304d-185">2754259</span><span class="sxs-lookup"><span data-stu-id="6304d-185">2754259</span></span></p></td>
<td align="left"><p><span data-ttu-id="6304d-186">MBAM 和安全网络通信</span><span class="sxs-lookup"><span data-stu-id="6304d-186">MBAM and Secure Network Communication</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2754259/EN-US" data-raw-source="[support.microsoft.com/kb/2754259/EN-US](https://support.microsoft.com/kb/2754259/EN-US)"><span data-ttu-id="6304d-187">support.microsoft.com/kb/2754259/EN-US</span><span class="sxs-lookup"><span data-stu-id="6304d-187">support.microsoft.com/kb/2754259/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6304d-188">2870842</span><span class="sxs-lookup"><span data-stu-id="6304d-188">2870842</span></span></p></td>
<td align="left"><p><span data-ttu-id="6304d-189">MBAM 2.0 安装程序在 SQL Server 2008 的 Configuration Manager 集成方案期间失败</span><span class="sxs-lookup"><span data-stu-id="6304d-189">MBAM2.0 Setup fails during Configuration Manager Integration Scenario with SQL Server 2008</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2870842/EN-US" data-raw-source="[support.microsoft.com/kb/2870842/EN-US](https://support.microsoft.com/kb/2870842/EN-US)"><span data-ttu-id="6304d-190">support.microsoft.com/kb/2870842/EN-US</span><span class="sxs-lookup"><span data-stu-id="6304d-190">support.microsoft.com/kb/2870842/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6304d-191">2668533</span><span class="sxs-lookup"><span data-stu-id="6304d-191">2668533</span></span></p></td>
<td align="left"><p><span data-ttu-id="6304d-192">如果 SQL SSRS 的配置不正确，MBAM 安装将失败</span><span class="sxs-lookup"><span data-stu-id="6304d-192">MBAM Setup fails if SQL SSRS is not configured properly</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2668533/EN-US" data-raw-source="[support.microsoft.com/kb/2668533/EN-US](https://support.microsoft.com/kb/2668533/EN-US)"><span data-ttu-id="6304d-193">support.microsoft.com/kb/2668533/EN-US</span><span class="sxs-lookup"><span data-stu-id="6304d-193">support.microsoft.com/kb/2668533/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6304d-194">2870847</span><span class="sxs-lookup"><span data-stu-id="6304d-194">2870847</span></span></p></td>
<td align="left"><p><span data-ttu-id="6304d-195">MBAM 2.0 安装失败， &quot; 检索 &#39;Reporting Services 点&#39; 角色的 Configuration Manager 服务器角色设置时出错&quot;</span><span class="sxs-lookup"><span data-stu-id="6304d-195">MBAM 2.0 Setup fails with &quot;Error retrieving Configuration Manager Server role settings for &#39;Reporting Services Point&#39; role&quot;</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2870847/EN-US" data-raw-source="[support.microsoft.com/kb/2870847/EN-US](https://support.microsoft.com/kb/2870847/EN-US)"><span data-ttu-id="6304d-196">support.microsoft.com/kb/2870847/EN-US</span><span class="sxs-lookup"><span data-stu-id="6304d-196">support.microsoft.com/kb/2870847/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6304d-197">2870839</span><span class="sxs-lookup"><span data-stu-id="6304d-197">2870839</span></span></p></td>
<td align="left"><p><span data-ttu-id="6304d-198">由于 SQL 作业 CreateCache 失败，MBAM 2.0 企业版报表不会在 MBAM 2.0 独立拓扑中刷新</span><span class="sxs-lookup"><span data-stu-id="6304d-198">MBAM2.0 Enterprise Reports are not refreshed in MBAM2.0 Standalone topology due to SQL job CreateCache failure</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2870839/EN-US" data-raw-source="[support.microsoft.com/kb/2870839/EN-US](https://support.microsoft.com/kb/2870839/EN-US)"><span data-ttu-id="6304d-199">support.microsoft.com/kb/2870839/EN-US</span><span class="sxs-lookup"><span data-stu-id="6304d-199">support.microsoft.com/kb/2870839/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6304d-200">2620269</span><span class="sxs-lookup"><span data-stu-id="6304d-200">2620269</span></span></p></td>
<td align="left"><p><span data-ttu-id="6304d-201">MBAM 企业报告未获得更新</span><span class="sxs-lookup"><span data-stu-id="6304d-201">MBAM Enterprise Reporting Not Getting Updated</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2620269/EN-US" data-raw-source="[support.microsoft.com/kb/2620269/EN-US](https://support.microsoft.com/kb/2620269/EN-US)"><span data-ttu-id="6304d-202">support.microsoft.com/kb/2620269/EN-US</span><span class="sxs-lookup"><span data-stu-id="6304d-202">support.microsoft.com/kb/2620269/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6304d-203">2935997</span><span class="sxs-lookup"><span data-stu-id="6304d-203">2935997</span></span></p></td>
<td align="left"><p><span data-ttu-id="6304d-204">MBAM 支持的计算机合规性报告不正确包括不支持的产品</span><span class="sxs-lookup"><span data-stu-id="6304d-204">MBAM Supported Computers compliance reporting incorrectly includes unsupported products</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2935997/EN-US" data-raw-source="[support.microsoft.com/kb/2935997/EN-US](https://support.microsoft.com/kb/2935997/EN-US)"><span data-ttu-id="6304d-205">support.microsoft.com/kb/2935997/EN-US</span><span class="sxs-lookup"><span data-stu-id="6304d-205">support.microsoft.com/kb/2935997/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6304d-206">2612822</span><span class="sxs-lookup"><span data-stu-id="6304d-206">2612822</span></span></p></td>
<td align="left"><p><span data-ttu-id="6304d-207">MBAM 中的计算机记录被拒绝</span><span class="sxs-lookup"><span data-stu-id="6304d-207">Computer Record is Rejected in MBAM</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2612822/EN-US" data-raw-source="[support.microsoft.com/kb/2612822/EN-US](https://support.microsoft.com/kb/2612822/EN-US)"><span data-ttu-id="6304d-208">support.microsoft.com/kb/2612822/EN-US</span><span class="sxs-lookup"><span data-stu-id="6304d-208">support.microsoft.com/kb/2612822/EN-US</span></span></a></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="6304d-209">相关主题</span><span class="sxs-lookup"><span data-stu-id="6304d-209">Related topics</span></span>


[<span data-ttu-id="6304d-210">关于 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="6304d-210">About MBAM 2.0</span></span>](about-mbam-20-mbam-2.md)

 

 





