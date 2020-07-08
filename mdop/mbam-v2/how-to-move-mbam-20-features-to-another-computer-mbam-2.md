---
title: 如何将 MBAM 2.0 功能移到另一台计算机
description: 如何将 MBAM 2.0 功能移到另一台计算机
author: dansimp
ms.assetid: 49bc0792-60a4-473f-89cc-ada30191e04a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 340d87e26d87f124a9ab64c63d33e89c293d8a86
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803696"
---
# 如何将 MBAM 2.0 功能移到另一台计算机


本主题介绍将一个或多个 Microsoft BitLocker 管理和监视（MBAM）功能移动到另一台计算机时应采取的步骤。 移动多个 Microsoft BitLocker 管理和监视功能时，应按照以下顺序移动它们：

1.  恢复数据库

2.  合规性和审核数据库

3.  合规性和审核报告

4.  管理和监视

## 移动恢复数据库


若要将恢复数据库从一台计算机移动到另一台计算机（例如从服务器 A 移动到服务器 B），请使用以下过程。

1.  停止管理和监视网站的所有实例。

2.  在服务器 B 上运行 MBAM 安装程序。

3.  备份服务器 A 上的 MBAM 恢复数据库。

4.  将 MBAM 恢复数据库从服务器 A 移动到 B。

5.  还原服务器 B 上的 MBAM 恢复数据库。

6.  在服务器 B 上配置对 MBAM 恢复数据库的访问权限。

7.  在 MBAM 管理和监视服务器上更新数据库连接数据。

8.  恢复 MBAM 管理和监视网站的所有实例。

**停止 MBAM 管理和监视网站的所有实例**

1.  在运行 MBAM 管理和监视功能的每台服务器上，使用 Internet Information Services （IIS）管理器控制台停止名为**Microsoft BitLocker 管理和监视**的 MBAM 网站。

2.  若要自动执行此过程，你可以使用 Windows PowerShell 输入类似于以下内容的命令行：

    `PS C:\> Stop-Website “Microsoft BitLocker Administration and Monitoring”`

    **注意**  
    若要运行此 PowerShell 命令行，必须将用于 PowerShell 的 IIS 模块添加到当前的 PowerShell 实例。 此外，必须更新 PowerShell 执行策略以启用脚本执行。



**在服务器 B 上运行 MBAM 设置**

1.  在服务器 B 上运行 MBAM 设置，并仅选择要安装的**恢复数据库**。

2.  若要自动执行此过程，你可以使用 Windows PowerShell 输入类似于以下内容的命令行：

    `PS C:\> MbamSetup.exe /qn I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 AddLocal=KeyDatabase ADMINANDMON_MACHINENAMES=$DOMAIN$\$SERVERNAME$$ RECOVERYANDHWDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ TOPOLOGY=$X$`

    **注意**  
    将上述示例中的以下值替换为与你的环境匹配的值：

    -   $SERVERNAME $ \\ $SQLINSTANCENAME $-输入要将恢复数据库移动到的服务器和实例的名称。

    -   $DOMAIN $ \\ $SERVERNAME $-输入将与恢复数据库联系的每个 MBAM 管理和监视服务器的域名和服务器名称。 使用分号分隔列表中的每个域和服务器对（例如，$DOMAIN \\SERVERNAME $; $DOMAIN \ $SERVERNAME $ $）。 每个服务器名称必须后跟一个 "$" 符号，如示例中所示（MyDomain\\MyServerName1 $;MyDomain\\MyServerName2 $）。

    -   如果你要安装 MBAM 独立拓扑，请 $X $-输入**0** ，如果你要安装 MBAM Configuration Manager 拓扑，则输入**1** 。



**备份服务器 A 上的恢复数据库**

1.  若要备份服务器 A 上的恢复数据库，请使用 SQL Server Management Studio 和名为 "备份" 的任务。 默认情况下，数据库名称是**MBAM 恢复数据库**。

2.  若要自动执行此过程，请创建包含以下 SQL 脚本的 SQL 文件（.sql）：

    修改 MBAM 恢复数据库以使用完整恢复模式。

    ```sql
    USE master;

    GO

    ALTER DATABASE "MBAM Recovery and Hardware"

       SET RECOVERY FULL;

    GO

    -- Create MBAM Recovery Database Data and MBAM Recovery logical backup devices.

    USE master

    GO

    EXEC sp_addumpdevice 'disk', 'MBAM Recovery and Hardware Database Data Device',

    'Z:\MBAM Recovery Database Data.bak';

    GO

    -- Back up the full MBAM Recovery Database.

    BACKUP DATABASE [MBAM Recovery and Hardware] TO [MBAM Recovery and Hardware Database Data Device];

    GO

    BACKUP CERTIFICATE [MBAM Recovery Encryption Certificate]

    TO FILE = 'Z:\SQLServerInstanceCertificateFile'

    WITH PRIVATE KEY

    (

        FILE = ' Z:\SQLServerInstanceCertificateFilePrivateKey',

        ENCRYPTION BY PASSWORD = '$PASSWORD$'

    );

    GO
    ```

    **注意**  
    将上述示例中的以下值替换为与你的环境匹配的值：

    -   $PASSWORD $-输入将用于加密私钥文件的密码。



3.  使用 SQL Server PowerShell 和类似于以下内容的命令行运行 SQL 文件：

    `PS C:\> Invoke-Sqlcmd -InputFile 'Z:\BackupMBAMRecoveryandHardwarDatabaseScript.sql' -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$`

    **注意**  
    将上述示例中的以下值替换为与你的环境匹配的值：

    -   $SERVERNAME $ \\ $SQLINSTANCENAME $-输入服务器和实例的名称，将从该名称备份恢复数据库。



**将恢复数据库和证书从服务器 A 移动到服务器 B**

1.  使用 Windows 资源管理器将以下文件从服务器 A 移动到服务器 B。

    -   MBAM 恢复数据库数据 .bak

2.  若要移动加密数据库的证书，请使用以下自动化步骤。 若要自动执行此过程，你可以使用 Windows PowerShell 输入类似于以下内容的命令行：

    `PS C:\> Copy-Item “Z:\MBAM Recovery Database Data.bak” \\$SERVERNAME$\$DESTINATIONSHARE$`

    `PS C:\> Copy-Item “Z:\SQLServerInstanceCertificateFile” \\$SERVERNAME$\$DESTINATIONSHARE$`

    `PS C:\> Copy-Item “Z:\SQLServerInstanceCertificateFilePrivateKey” \\$SERVERNAME$\$DESTINATIONSHARE$`

    **注意**  
    将上述示例中的以下值替换为与你的环境匹配的值：

    -   $SERVERNAME $-输入要将文件复制到的服务器的名称。

    -   $DESTINATIONSHARE $-输入要将文件复制到的共享和路径的名称。



**还原服务器 B 上的恢复数据库**

1.  使用 SQL Server Management Studio 和名为**Restore database**的任务还原服务器 B 上的恢复数据库。

2.  完成任务后，选择数据库备份文件，方法是选择 "**发件人设备**" 选项，然后使用 "**添加**" 命令选择 MBAM 恢复数据库**数据 .bak**文件。

3.  选择 **"确定"** 完成还原过程。

4.  若要自动执行此过程，请创建包含以下 SQL 脚本的 SQL 文件（.sql）：

    ```sql
    -- Restore MBAM Recovery Database. 

    USE master

    GO

    -- Drop certificate created by MBAM Setup.

    DROP CERTIFICATE [MBAM Recovery Encryption Certificate]

    GO

    --Add certificate

    CREATE CERTIFICATE [MBAM Recovery Encryption Certificate]

    FROM FILE = 'Z: \SQLServerInstanceCertificateFile'

    WITH PRIVATE KEY

    (

        FILE = ' Z:\SQLServerInstanceCertificateFilePrivateKey',

        DECRYPTION BY PASSWORD = '$PASSWORD$'

    );

    GO

    -- Restore the MBAM Recovery Database data and log files.

    RESTORE DATABASE [MBAM Recovery and Hardware]

       FROM DISK = 'Z:\MBAM Recovery Database Data.bak'

       WITH REPLACE
    ```

    **注意**  
    将上述示例中的以下值替换为与你的环境匹配的值：

    -   $PASSWORD $-输入用于加密私钥文件的密码。



5.  可以使用 Windows PowerShell 输入类似于以下内容的命令行：

    `PS C:\> Invoke-Sqlcmd -InputFile 'Z:\RestoreMBAMRecoveryandHardwarDatabaseScript.sql' -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$`

    **注意**  
    将上述示例中的以下值替换为与你的环境匹配的值：

    -   $SERVERNAME $ \\ $SQLINSTANCENAME $-输入恢复数据库将还原到的服务器和实例的名称。



**在服务器 B 上配置对恢复数据库的访问权限**

1.  在服务器 B 上，使用服务器管理器中的 "本地用户和组" 管理单元将运行 MBAM 管理和监视功能的每台服务器中的计算机帐户添加到名为**MBAM 恢复和硬件数据库访问**的本地组。

2.  验证还原的数据库上的 SQL 登录**MBAM 恢复和硬件数据库访问**是否映射到登录名 **$MachineName $ \\MBAM 恢复和硬件数据库访问**。 如果未按所述进行映射，请使用类似的组成员身份创建另一个登录，并将其映射到登录名 **$MachineName $ \\MBAM 恢复和硬件数据库访问**。

3.  若要自动执行此过程，可以在服务器 B 上使用 Windows PowerShell 输入类似于以下内容的命令行：

    `PS C:\> net localgroup "MBAM Recovery and Hardware DB Access" $DOMAIN$\$SERVERNAME$$  /add`

    **注意**  
    将上述示例中的以下值替换为适用于你的环境的适用值：

    -   $DOMAIN $ \ \ $SERVERNAME $ $-输入 MBAM 管理和监视服务器的域名和计算机名。 服务器名称后面必须是 $，如示例中所示（例如，MyDomain\\MyServerName1 $）。



~~~
This command line must be run for each Administration and Monitoring Server that will be accessing the database in your environment.
~~~

**更新 MBAM 管理和监视服务器上的恢复数据库连接数据**

1. 在运行 MBAM 管理和监视功能的每台服务器上，使用 Internet Information Services （IIS）管理器控制台更新以下应用程序的连接字符串信息，这些应用程序位于管理和监视网站中：

   -   MBAMAdministrationService

   -   MBAMRecoveryAndHardwareService

2. 选择每个应用程序并使用 "**配置编辑器**" 功能，该功能位于 "功能"**视图**的 "**管理**" 部分下。

3. 从 "**节列表**" 控件中选择 " **configurationStrings** " 选项。

4. 选择名为 **（集合）** 的行，然后通过选择行右侧的按钮打开**集合编辑器**。

5. 在**集合编辑器**中，在更新 MBAMAdministrationService 应用程序的配置或名为 Mbam 的行时，选择名为**KeyRecoveryConnectionString**的行 <strong> 。 </strong>当更新 MBAMRecoveryAndHardwareService 的配置时，ConnectionString。

6. 更新**configurationStrings**属性的**数据源 =** 值以列出服务器名称和实例（例如，$SERVERNAME $ \\ $SQLINSTANCENAME $），从中移动了恢复数据库。

7. 若要自动执行此过程，可以在每个管理和监视服务器上使用 Windows 输入与以下内容类似的命令行：

   `PS C:\> Set-WebConfigurationProperty '/connectionStrings/add[@name="KeyRecoveryConnectionString"]' -PSPath "IIS:\sites\Microsoft Bitlocker Administration and Monitoring\MBAMAdministrationService" -Name "connectionString" -Value “Data Source=$SERVERNAME$\$SQLINSTANCENAME$;Initial Catalog=MBAM Recovery and Hardware;Integrated Security=SSPI;”`

   `PS C:\> Set-WebConfigurationProperty '/connectionStrings/add[@name="Microsoft.Mbam.RecoveryAndHardwareDataStore.ConnectionString"]' -PSPath "IIS:\sites\Microsoft Bitlocker Administration and Monitoring\MBAMRecoveryAndHardwareService" -Name "connectionString" -Value "Data Source=$SERVERNAME$\$SQLINSTANCENAME$;Initial Catalog=MBAM Recovery and Hardware;Integrated Security=SSPI;"`

   **注意**  
   将上述示例中的以下值替换为与你的环境匹配的值：

   -   $SERVERNAME $ \\ $SQLINSTANCENAME $-输入恢复数据库所在的服务器名称和实例。



**恢复 MBAM 管理和监视网站的所有实例**

1.  在运行 MBAM 管理和监视功能的每台服务器上，使用 Internet Information Services （IIS）管理器控制台启动名为**Microsoft BitLocker 管理和监视**的 MBAM 网站。

2.  若要自动执行此过程，你可以使用 Windows PowerShell 输入类似于以下内容的命令行：

    `PS C:\> Start-Website “Microsoft BitLocker Administration and Monitoring”`

## 移动合规性和审核数据库功能


如果要将 MBAM 合规性和审核数据库从一台计算机移动到另一台计算机（即，将数据库从服务器 A 移动到服务器 B），请使用以下过程。 该过程包括以下高级别步骤：

1.  停止管理和监视网站的所有实例。

2.  在服务器 B 上运行 MBAM 安装程序。

3.  在服务器 A 上备份数据库。

4.  将数据库从服务器 A 移动到 B。

5.  在服务器 B 上还原数据库。

6.  在服务器 B 上配置对数据库的访问权限。

7.  更新 MBAM 管理和监视服务器上的数据库连接数据。

8.  通过合规性和审核数据库的新位置更新 SSRS 报表数据源连接字符串。

9.  恢复管理和监视网站的所有实例。

**停止管理和监视网站的所有实例**

1.  在运行 MBAM 管理和监视功能的每台服务器上，使用 Internet Information Services （IIS）管理器控制台停止名为**Microsoft BitLocker 管理和监视**的 MBAM 网站。

2.  若要自动执行此过程，你可以使用 Windows PowerShell 输入类似于以下内容的命令行：

    `PS C:\> Stop-s “Microsoft BitLocker Administration and Monitoring”`

    **注意**  
    若要运行此命令行，必须将用于 PowerShell 的 IIS 模块添加到 PowerShell 的当前实例。 此外，你必须更新 PowerShell 执行策略以允许运行脚本。



**在服务器 B 上运行 MBAM 设置**

1.  在服务器 B 上运行 MBAM 设置，并仅选择**合规性和审核数据库**进行安装。

2.  若要自动执行此过程，你可以使用 Windows PowerShell 输入类似于以下内容的命令行：

    `PS C:\> MbamSetup.exe /qn I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 AddLocal= ReportsDatabase ADMINANDMON_MACHINENAMES=$DOMAIN$\$SERVERNAME$ COMPLIDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ REPORTS_USERACCOUNT=$DOMAIN$\$USERNAME$ TOPOLOGY=$X$`

    **注意**  
    注意：将上述示例中的以下值替换为与你的环境匹配的值：

    -   $SERVERNAME $ \\ $SQLINSTANCENAME $-输入要将合规性和审核数据库移动到的服务器名称和实例。

    -   $DOMAIN $ \\ $SERVERNAME $-输入将与合规性和审核数据库联系的每个 MBAM 管理和监视服务器的域名和服务器名称。 使用分号分隔列表中的每个域和服务器对（例如，$DOMAIN \\SERVERNAME $; $DOMAIN \ $SERVERNAME $ $）。 每个服务器名称必须后跟一个 "$" 符号，如示例中所示（MyDomain\\MyServerName1 $;MyDomain\\MyServerName2 $）。

    -   $DOMAIN $ \\ $USERNAME $-输入合规性和审核报告功能将用于连接到合规性和审核数据库的域名和用户名。

    -   如果你要安装 MBAM 独立拓扑，请 $X $-输入**0** ，如果你要安装 MBAM Configuration Manager 拓扑，则输入**1** 。



**在服务器 A 上备份合规性和审核数据库**

1.  若要备份服务器 A 上的合规性和审核数据库，请使用 SQL Server Management Studio 和名为 "**备份**" 的任务。 默认情况下，数据库名称是**MBAM 合规性状态数据库**。

2.  若要自动执行此过程，请创建包含以下 SQL 脚本的 SQL 文件（.sql）：

    ```sql
    -- Modify the MBAM Compliance Status Database to use the full recovery model.

    USE master;

    GO

    ALTER DATABASE "MBAM Compliance Status"

       SET RECOVERY FULL;

    GO

    -- Create MBAM Compliance Status Data logical backup devices.

    USE master

    GO

    EXEC sp_addumpdevice 'disk', 'MBAM Compliance Status Database Data Device',

    'Z: \MBAM Compliance Status Database Data.bak';

    GO

    -- Back up the full MBAM Recovery database.

    BACKUP DATABASE [MBAM Compliance Status] TO [MBAM Compliance Status Database Data Device];

    GO
    ```

3.  使用 Windows PowerShell 命令行运行 SQL 文件，如下所示：

    `PS C:\> Invoke-Sqlcmd -InputFile "Z:\BackupMBAMComplianceStatusDatabaseScript.sql" –ServerInstance $SERVERNAME$\$SQLINSTANCENAME$`

    **注意**  
    将上述示例中的以下值替换为与你的环境匹配的值：

    -   $SERVERNAME $ \\ $SQLINSTANCENAME $-输入将从中备份合规性和审核数据库的服务器名称和实例。



**将合规性和审核数据库从服务器 A 移动到 B**

1.  使用 Windows 资源管理器将以下文件从服务器 A 移动到服务器 B。

    -   MBAM 合规性状态数据库数据 .bak

2.  若要自动执行此过程，你可以使用 Windows PowerShell 输入类似于以下内容的命令行：

    `PS C:\> Copy-Item “Z:\MBAM Compliance Status Database Data.bak” \\$SERVERNAME$\$DESTINATIONSHARE$`

    **注意**  
    将上述示例中的以下值替换为与你的环境匹配的值：

    -   $SERVERNAME $-输入要将文件复制到的服务器名称。

    -   $DESTINATIONSHARE $-输入要将文件复制到的共享和路径的名称。



**在服务器 B 上还原合规性和审核数据库**

1.  使用 SQL Server Management Studio 和名为**Restore database**的任务在服务器 B 上还原合规性和审核数据库。

2.  完成任务后，选择数据库备份文件，方法是选择 "**发件人设备**" 选项，然后使用 "**添加**" 命令选择 MBAM 合规性状态数据库数据 .bak 文件。 选择 **"确定"** 完成还原过程。

3.  若要自动执行此过程，请创建包含以下 SQL 脚本的 SQL 文件（.sql）：

    ```sql
    -- Create MBAM Compliance Status Database Data logical backup devices. 

    Use master

    GO

    -- Restore the MBAM Compliance Status database data files.

    RESTORE DATABASE [MBAM Compliance Status]

       FROM DISK = 'C:\test\MBAM Compliance Status Database Data.bak'

       WITH REPLACE
    ```

4.  使用 Windows PowerShell 命令行运行 SQL 文件，如下所示：

    `PS C:\> Invoke-Sqlcmd -InputFile "Z:\RestoreMBAMComplianceStatusDatabaseScript.sql" -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$`

    **注意**  
    将上述示例中的以下值替换为与你的环境匹配的值：

    -   $SERVERNAME $ \\ $SQLINSTANCENAME $-输入要将合规性和审核数据库还原到的服务器名称和实例。



**在服务器 B 上配置合规性和审核数据库的访问权限**

1.  在服务器 B 上，使用服务器管理器中的 "本地用户和组" 管理单元将运行 MBAM 管理和监视功能的每台服务器中的计算机帐户添加到名为**MBAM 合规性状态数据库访问**的本地组。

2.  验证已还原数据库上的 SQL 登录**MBAM 合规性审核数据库访问**是否映射到登录名 **$MACHINENAME $ \\ MBAM 合规性审核数据库访问**。 如果未按所述进行映射，请使用类似的组成员身份创建另一个登录，并将其映射到登录名 **$MachineName $ \\ MBAM 合规性审核数据库访问**。

3.  若要自动执行此过程，你可以使用 Windows PowerShell 在服务器 B 上输入类似于以下内容的命令行：

    `PS C:\> net localgroup "MBAM Compliance Auditing DB Access" $DOMAIN$\$SERVERNAME$$  /add`

    `PS C:\> net localgroup "MBAM Compliance Auditing DB Access" $DOMAIN$\$REPORTSUSERNAME$  /add`

    **注意**  
    将上述示例中的以下值替换为适用于你的环境的适用值：

    -   $DOMAIN $ \ \ $SERVERNAME $ $-输入 MBAM 管理和监视服务器的域名和计算机名。 服务器名称必须后跟 "$"，如示例中所示。 （例如，MyDomain\\MyServerName1 $）

    -   $DOMAIN $ \\ $REPORTSUSERNAME $-输入用于配置合规性和审核报告的数据源的用户帐户名称。



~~~
The command line for adding the servers to the MBAM Compliance and Audit Database access local group must be run for each Administration and Monitoring Server that will be accessing the database in your environment.
~~~

**在 MBAM 管理和监视服务器上更新数据库连接数据**

1.  在运行 MBAM 管理和监视功能的每台服务器上，使用 Internet Information Services （IIS）管理器控制台更新以下应用程序的连接字符串信息，这些应用程序位于管理和监视网站中：

    -   MBAMAdministrationService

    -   MBAMComplianceStatusService

2.  选择每个应用程序并使用 "**配置编辑器**" 功能，该功能位于 "功能"**视图**的 "**管理**" 部分下。

3.  从 "**节列表**" 控件中选择 " **configurationStrings** " 选项。

4.  选择名为 **（集合）** 的行，然后通过选择行右侧的按钮打开**集合编辑器**。

5.  在**集合编辑器**中，在更新 MBAMComplianceStatusService 的配置时，选择名为 " **ComplianceStatusConnectionString** " 的行作为 MBAMAdministrationService 应用程序的配置或名为**BitLockerManagement. StatusReportDataStore**的行。

6.  更新**configurationStrings**属性的**数据源 =** value，以列出要将恢复数据库移动到的服务器和实例的名称（例如 $SERVERNAME $ \\ $SQLINSTANCENAME）。

7.  若要自动执行此过程，你可以使用 Windows 在与以下内容类似的每个管理和监视服务器上输入命令行：

    `PS C:\> Set-WebConfigurationProperty '/connectionStrings/add[@name="ComplianceStatusConnectionString"]' -PSPath "IIS:\sites\Microsoft Bitlocker Administration and Monitoring\MBAMAdministrationService" -Name "connectionString" -Value "Data Source=$SERVERNAME$\$SQLINSTANCENAME$;Initial Catalog=MBAM Compliance Status;Integrated Security=SSPI;"`

    `PS C:\> Set-WebConfigurationProperty '/connectionStrings/add[@name="Microsoft.Windows.Mdop.BitLockerManagement.StatusReportDataStore.ConnectionString"]' -PSPath "IIS:\sites\Microsoft Bitlocker Administration and Monitoring\MBAMComplianceStatusService" -Name "connectionString" -Value "Data Source=$SERVERNAME$\$SQLINSTANCENAME;Initial Catalog=MBAM Compliance Status;Integrated Security=SSPI;"`

    **注意**  
    将上述示例中的以下值替换为与你的环境匹配的值：

    -   $SERVERNAME $ \\ $SQLINSTANCENAME $-输入恢复数据库所在的服务器名称和实例。



**恢复 MBAM 管理和监视网站的所有实例**

1.  在运行 MBAM 管理和监视功能的每台服务器上，使用 Internet Information Services （IIS）管理器控制台启动名为**Microsoft BitLocker 管理和监视**的 MBAM 网站。

2.  若要自动执行此过程，你可以使用 Windows PowerShell 输入类似于以下内容的命令行：

    `PS C:\> Start-Website “Microsoft BitLocker Administration and Monitoring”`

## 移动合规性和审核报告


如果要将 MBAM 合规性和审核报告从一台计算机移动到另一台计算机（即，将报表从服务器 A 移动到服务器 B），请使用以下过程，其中包括以下高级步骤：

1.  在服务器 B 上运行 MBAM 安装程序。

2.  配置对服务器 B 上的合规性和审核报告的访问权限。

3.  停止 MBAM 管理和监视网站的所有实例。

4.  在 MBAM 管理和监视服务器上更新报表连接数据。

5.  恢复 MBAM 管理和监视网站的所有实例。

**在服务器 B 上运行 MBAM 设置**

1.  在服务器 B 上运行 MBAM 设置，仅选择 "**合规性" 和 "审核报告**" 功能进行安装。

2.  若要自动执行此过程，你可以使用 Windows PowerShell 输入类似于以下内容的命令行：

    `PS C:\> MbamSetup.exe /qn I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 AddLocal=Reports COMPLIDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ REPORTS_USERACCOUNTPW=$PASSWORD$ TOPOLOGY=$X$`

    **注意**  
    将上述示例中的以下值替换为与你的环境匹配的值：

    -   $SERVERNAME $ \\ $SQLINSTANCENAME $-输入合规性和审核数据库所在的服务器名称和实例。

    -   $DOMAIN $ \\ $USERNAME $-输入合规性和审核报告功能将用于连接到合规性和审核数据库的域名和用户名。

    -   $PASSWORD $-输入将用于连接合规性和审核数据库的用户帐户的密码。

    -   如果你要安装 MBAM 独立拓扑，请 $X $-输入**0** ，如果你要安装 MBAM Configuration Manager 拓扑，则输入**1** 。



**配置对服务器 B 上的合规性和审核报告的访问权限**

1.  在服务器 B 上，使用服务器管理器中的 "本地用户和组" 管理单元添加将有权访问合规性和审核报告的用户帐户。 将用户帐户添加到名为 MBAM 报告用户的本地组。

2.  若要自动执行此过程，你可以使用 Windows PowerShell 在服务器 B 上输入类似于以下内容的命令行：

    `PS C:\> net localgroup "MBAM Report Users" $DOMAIN$\$REPORTSUSERNAME$  /add`

    **注意**  
    将上述示例中的以下值替换为适用于你的环境的适用值：

    -   $DOMAIN $ \\ $REPORTSUSERNAME $-输入用于配置合规性和审核报告的数据源的用户帐户名称。



~~~
The command line for adding the users to the MBAM Report Users local group must be run for each user that will be accessing the reports in your environment.
~~~

**停止 MBAM 管理和监视网站的所有实例**

1.  在运行 MBAM 管理和监视服务器功能的每台服务器上，使用 Internet Information Services （IIS）管理器控制台停止名为**Microsoft BitLocker 管理和监视**的 MBAM 网站。

2.  若要自动执行此过程，你可以使用 Windows PowerShell 输入类似于以下内容的命令行：

    `PS C:\> Stop-Website “Microsoft BitLocker Administration and Monitoring”`

**更新 MBAM 管理和监视服务器上的数据库连接数据**

1. 在运行 MBAM 管理和监视服务器功能的每台服务器上，使用 Internet 信息服务（IIS）管理器控制台更新合规性和审核报告 URL。

2. 选择 " **Microsoft BitLocker 管理和监视**" 网站，并使用 "配置编辑器" 功能，该功能位于 "功能"**视图**的 "**管理**" 部分下的 "**配置编辑器**" 功能。

3. 从 "**节列表**" 控件中选择 " **appSettings** " 选项。

4. 选择名为 **（集合）** 的行，然后通过选择行右侧的按钮打开**集合编辑器**。

5. 在**集合编辑器**中，选择名为 " **Mbam**" 的行。

6. 更新**Mbam**的值以反映服务器 B 的服务器名称。如果已在命名的 SQL Reporting Services 实例上安装了合规性和审核报告功能，请确保在 URL 中添加或更新实例的名称（例如，http://$SERVERNAME $/ReportServer\_ $ SQLSRSINSTANCENAME $/Pages....）

7. 若要自动执行此过程，你可以使用 Windows PowerShell 在与以下内容类似的每个管理和监视服务器上输入命令行：

   `PS C:\> Set-WebConfigurationProperty '/appSettings/add[@key="Microsoft.Mbam.Reports.Url"]' -PSPath "IIS:\ \sites\Microsoft Bitlocker Administration and Monitoring\HelpDesk" -Name "Value" -Value “http://$SERVERNAME$/ReportServer_$SRSINSTANCENAME$/Pages/ReportViewer.aspx?/ Microsoft+BitLocker+Administration+and+Monitoring/”`

   **注意**  
   将上述示例中的以下值替换为与你的环境匹配的值：

   -   $SERVERNAME $-输入要安装合规性和审核报告的服务器名称的名称。

   -   $SRSINSTANCENAME $-输入已安装合规性和审核报告的 SQL Reporting Services 实例的名称。



**恢复 MBAM 管理和监视网站的所有实例**

1.  在运行 MBAM 管理和监视服务器功能的每台服务器上，使用 Internet Information Services （IIS）管理器控制台启动名为**Microsoft BitLocker 管理和监视**的 MBAM 网站。

2.  若要自动执行此过程，你可以使用 Windows PowerShell 输入类似于以下内容的命令行：

    `PS C:\> Start-Website “Microsoft BitLocker Administration and Monitoring”`

    **注意**  
    若要运行此命令行，必须将用于 PowerShell 的 IIS 模块添加到当前的 PowerShell 实例。 此外，你必须更新 PowerShell 执行策略以允许运行脚本。



## 移动 "管理和监视" 功能


如果要将 MBAM 管理和监视报告功能从一台计算机移动到另一台计算机（即，将该功能从服务器 A 移动到服务器 B），请使用以下过程，其中包括以下高级步骤：

1.  在服务器 B 上运行 MBAM 安装程序。

2.  在服务器 B 上配置对数据库的访问权限。

**在服务器 B 上运行 MBAM 设置**

1.  在服务器 B 上运行 MBAM 设置，并仅选择 "**管理和监视服务器**" 功能进行安装。

2.  若要自动执行此过程，你可以使用 Windows PowerShell 输入类似于以下内容的命令行：

    `PS C:\> MbamSetup.exe /qn I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 AddLocal=AdministrationMonitoringServer, COMPLIDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ RECOVERYANDHWDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ SRS_REPORTSITEURL=$REPORTSSERVERURL$ TOPOLOGY=$X$`

    **注意**  
    将上述示例中的以下值替换为与你的环境匹配的值：

    -   $SERVERNAME $ \\ $SQLINSTANCENAME $-对于 COMPLIDB \ _SQLINSTANCE 参数，输入合规性和审核数据库所在的服务器名称和实例。 对于 RECOVERYANDHWDB \ _SQLINSTANCE 参数，输入恢复数据库所在的服务器名称和实例。

    -   $DOMAIN $ \\ $USERNAME $-输入合规性和审核报告功能将用于连接到合规性和审核数据库的域名和用户名。

    -   $ REPORTSSERVERURL $-输入 SQL Reporting Services 网站的主位置的 URL。 如果报表已安装到默认 SRS 实例，则 URL 格式将采用 "http://$SERVERNAME $/ReportServer" 格式。 如果报表已安装到默认 SRS 实例，则 URL 格式将采用 "http://$SERVERNAME $/ReportServer\_ $ SQLINSTANCENAME $" 格式。

    -   如果你要安装 MBAM 独立拓扑，请 $X $-输入**0** ，如果你要安装 MBAM Configuration Manager 拓扑，则输入**1** 。



**配置对数据库的访问权限**

1.  在要部署恢复数据库和合规性和审核数据库的服务器或服务器上，使用服务器管理器中的本地用户和组管理单元将运行 MBAM 管理和监视服务器功能的每台服务器中的计算机帐户添加到名为**MBAM 恢复和硬件数据库访问**（恢复 DB 服务器）和**MBAM 合规性状态数据库访问**（合规性和审核数据库服务器）的每台服务器

2.  若要自动执行此过程，你可以使用 Windows PowerShell 在部署合规性和审核数据库的服务器上输入类似于以下内容的命令行。

    `PS C:\> net localgroup "MBAM Compliance Auditing DB Access" $DOMAIN$\$SERVERNAME$$  /add`

3.  在部署恢复数据库的服务器上，可以使用 Windows PowerShell 输入类似于以下内容的命令行：

    `PS C:\> net localgroup "MBAM Recovery and Hardware DB Access" $DOMAIN$\$SERVERNAME$$  /add`

    **注意**  
    将上述示例中的以下值替换为适用于你的环境的适用值：

    -   $DOMAIN $ \ \ $SERVERNAME $ $-输入管理和监视服务器的域名和计算机名称。 服务器名称必须后跟 "$" 符号，如示例中所示（例如，MyDomain\\MyServerName1 $）。

    -   $DOMAIN $ \\ $REPORTSUSERNAME $-输入用于配置合规性和审核报告的数据源的用户帐户名称。



~~~
The command lines that are listed for adding server computer accounts to the MBAM local groups must be run for each Administration and Monitoring Server that will be accessing the databases in your environment.
~~~

## 相关主题


[维护 MBAM 2.0](maintaining-mbam-20-mbam-2.md)









