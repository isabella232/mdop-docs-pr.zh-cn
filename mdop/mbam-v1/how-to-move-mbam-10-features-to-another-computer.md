---
title: 如何将 MBAM 1.0 功能移到另一台计算机
description: 如何将 MBAM 1.0 功能移到另一台计算机
author: dansimp
ms.assetid: e1907d92-6b42-4ba3-b0e4-60a9cc8285cc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 874c3983220f341e39fa5fb7c60f655e2f208082
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798173"
---
# 如何将 MBAM 1.0 功能移到另一台计算机


本主题介绍将一个或多个 Microsoft BitLocker 管理和监视（MBAM）功能移动到另一台计算机时应采取的步骤。 将多个 MBAM 功能移动到另一台计算机时，应按照以下顺序移动它们：

1.  恢复和硬件数据库

2.  合规性和审核数据库

3.  合规性和审核报告

4.  管理和监视

## 移动恢复和硬件数据库


可以使用以下过程将 MBAM 恢复和硬件数据库从一台计算机移动到另一台计算机（可将此 MBAM 服务器的功能从服务器 A 移动到服务器 B）：

****

1.  停止 MBAM 管理和监视网站的所有实例。

2.  在服务器 B 上运行 MBAM 设置。

3.  在服务器 A 上备份 MBAM 恢复和硬件数据库。

4.  从服务器 A 到 B MBAM 恢复和硬件数据库

5.  在服务器 B 上还原 MBAM 恢复和硬件数据库

6.  在服务器 B 上配置对 MBAM 恢复和硬件数据库的访问

7.  在 MBAM 管理和监视服务器上更新数据库连接数据

8.  恢复 MBAM 管理和监视网站的所有实例

**停止 MBAM 管理和监视网站的所有实例**

1.  使用 Internet Information Services （IIS）管理器控制台在运行 MBAM 管理和监视功能的每个服务器上停止 MBAM 网站。 MBAM 网站命名为 " **Microsoft BitLocker 管理和监视**"。

2.  若要自动执行此过程，你可以使用 Windows PowerShell 在命令提示符下使用类似于以下内容的命令：

    `PS C:\> Stop-Website “Microsoft BitLocker Administration and Monitoring”`

    **注意**  
    若要运行此 PowerShell 命令提示符，必须将用于 PowerShell 的 IIS 模块添加到 PowerShell 的当前实例。 此外，必须更新 PowerShell 执行策略以启用脚本的执行。



**在服务器 B 上运行 MBAM 设置**

1.  在服务器 B 上运行 MBAM 设置，然后选择要安装的恢复和硬件数据库。

2.  若要自动执行此过程，你可以使用 Windows PowerShell 在命令提示符下使用类似于以下内容的命令：

    `PS C:\> MbamSetup.exe /qn I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 AddLocal=KeyDatabase ADMINANDMON_MACHINENAMES=$DOMAIN$\$SERVERNAME$$ RECOVERYANDHWDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$`

    **注意**  
    将上述示例中的以下值替换为与你的环境匹配的值：

    -   $SERVERNAME $ \\ $SQLINSTANCENAME $-输入要将恢复和硬件数据库移动到的服务器和实例的名称。

    -   $DOMAIN $ \\ $SERVERNAME $-输入将联系恢复和硬件数据库的每个 MBAM 应用程序和监视服务器的域名和服务器名称。 如果存在多个域名和服务器名称，请使用分号分隔列表中的每个名称。 例如，$DOMAIN \\SERVERNAME $; $DOMAIN \ $SERVERNAME $ $。 此外，每个服务器名称必须后跟 a **$** 。 例如，MyDomain\\MyServerName1 $，MyDomain\\MyServerName2 $。



**备份服务器 A 上的数据库**

1.  若要备份服务器 A 上的恢复和硬件数据库，请使用 SQL Server Management Studio 和名为 "**备份 ...**" 的任务。 默认情况下，数据库名称是**MBAM 恢复和硬件数据库**。

2.  若要自动执行此过程，请创建包含以下 SQL 脚本的 SQL 文件（.sql）：

    修改 MBAM 恢复和硬件数据库以使用完整恢复模式。

    ```sql
    USE master;

    GO

    ALTER DATABASE "MBAM Recovery and Hardware"

       SET RECOVERY FULL;

    GO
    ```

    创建 MBAM 恢复和硬件数据库数据以及 MBAM 恢复逻辑备份设备。

    ```sql
    USE master

    GO

    EXEC sp_addumpdevice 'disk', 'MBAM Recovery and Hardware Database Data Device',

    'Z:\MBAM Recovery and Hardware Database Data.bak';

    GO
    ```

    备份完整的 MBAM 恢复和硬件数据库。

    ```sql
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
    将前面示例中的值替换为与你的环境匹配的值：

    -   $PASSWORD $-输入将用于加密私钥文件的密码。



3.  使用 SQL Server PowerShell 和类似于以下内容的命令执行 SQL 文件：

    `PS C:\> Invoke-Sqlcmd -InputFile 'Z:\BackupMBAMRecoveryandHardwarDatabaseScript.sql' -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$`

    **注意**  
    将上一示例中的值替换为与你的环境匹配的值：

    -   $SERVERNAME $ \\ $SQLINSTANCENAME $-输入服务器的名称以及备份恢复和硬件数据库的实例。



**将数据库和证书从服务器 A 移动到 B**

1.  使用 Windows 资源管理器将 MBAM 恢复和硬件数据库数据 .bak 从服务器 A 移动到服务器 B。

2.  若要移动加密数据库的证书，则需要使用以下自动化步骤。 若要自动执行此过程，你可以使用 Windows PowerShell 输入类似于以下内容的命令：

    `PS C:\> Copy-Item “Z:\MBAM Recovery and Hardware Database Data.bak” \\$SERVERNAME$\$DESTINATIONSHARE$`

    `PS C:\> Copy-Item “Z:\SQLServerInstanceCertificateFile” \\$SERVERNAME$\$DESTINATIONSHARE$`

    `PS C:\> Copy-Item “Z:\SQLServerInstanceCertificateFilePrivateKey” \\$SERVERNAME$\$DESTINATIONSHARE$`

    **注意**  
    将前面示例中的值替换为与你的环境匹配的值：

    -   $SERVERNAME $-输入要将文件复制到的服务器的名称。

    -   $DESTINATIONSHARE $-输入要将文件复制到的共享和路径的名称。



**在服务器 B 上还原数据库**

1.  通过使用 SQL Server Management Studio 和名为**Restore database**的任务还原服务器 B 上的恢复和硬件数据库。

2.  执行任务后，选择数据库备份文件，方法是选择 "**发件人设备**" 选项，然后使用 "**添加**" 命令选择 MBAM 恢复和硬件数据库**数据 .bak**文件。

3.  选择 **"确定"** 完成还原过程。

4.  若要自动执行此过程，请创建包含以下 SQL 脚本的 SQL 文件（.sql）：

    ```sql
    -- Restore MBAM Recovery and Hardware Database. 

    USE master

    GO
    ```

    删除由 MBAM 安装程序创建的证书。

    ```sql
    DROP CERTIFICATE [MBAM Recovery Encryption Certificate]

    GO
    ```

    添加证书

    ```sql
    CREATE CERTIFICATE [MBAM Recovery Encryption Certificate]

    FROM FILE = 'Z: \SQLServerInstanceCertificateFile'

    WITH PRIVATE KEY

    (

        FILE = ' Z:\SQLServerInstanceCertificateFilePrivateKey',

        DECRYPTION BY PASSWORD = '$PASSWORD$'

    );

    GO
    ```

    还原 MBAM 恢复和硬件数据库数据以及日志文件。

    ```sql
    RESTORE DATABASE [MBAM Recovery and Hardware]

       FROM DISK = 'Z:\MBAM Recovery and Hardware Database Data.bak'

       WITH REPLACE
    ```

    **注意**  
    将前面示例中的值替换为与你的环境匹配的值：

    -   $PASSWORD $-输入用于加密私钥文件的密码。



5.  使用 Windows PowerShell 输入类似于以下内容的命令行：

    `PS C:\> Invoke-Sqlcmd -InputFile 'Z:\RestoreMBAMRecoveryandHardwarDatabaseScript.sql' -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$`

    **注意**  
    将 receding 示例中的值替换为与你的环境匹配的值：

    -   $SERVERNAME $ \\ $SQLINSTANCENAME $-输入服务器的名称以及恢复和硬件数据库将还原到的实例。



**在服务器 B 上配置对数据库的访问**

1.  在服务器 B 上，使用服务器管理器中的本地用户和组管理单元，将运行 MBAM 管理和监视功能的每台服务器中的计算机帐户添加到名为**MBAM 恢复和硬件数据库访问**的本地组。

2.  若要自动执行此过程，可以在服务器 B 上使用 Windows PowerShell 输入类似于以下内容的命令：

    `PS C:\> net localgroup "MBAM Recovery and Hardware DB Access" $DOMAIN$\$SERVERNAME$$  /add`

    **注意**  
    将前面示例中的值替换为适用于你的环境的适用值：

    -   $DOMAIN $ \ \ $SERVERNAME $ $-输入 MBAM 管理和监视服务器的域名和计算机名。 服务器名称后面必须跟有 a **$** ，例如，MyDomain\\MyServerName1 $。



~~~
You must run the command for each Administration and Monitoring Server that will be accessing the database in your environment.
~~~

**更新 MBAM 管理和监视服务器上的数据库连接数据**

1. 在运行 MBAM 管理和监视功能的每台服务器上，使用 Internet Information Services （IIS）管理器控制台更新下列应用程序的连接字符串信息，这些应用程序位于 Microsoft BitLocker 管理和监视网站中：

   -   MBAM 管理服务

   -   MBAM 恢复和硬件服务

2. 选择每个应用程序并使用 "**配置编辑器**" 功能，该功能位于 "功能"**视图**的 "**管理**" 部分下。

3. 从 "节列表" 控件中选择 " **configurationStrings** " 选项。

4. 选择名为 **（集合）** 的行，然后通过选择行右侧的按钮打开**集合编辑器**。

5. 在**集合编辑器**中，当你更新 "MBAMAdministrationService" 应用程序的配置时，选择名为 " **KeyRecoveryConnectionString** " 的行，或者选择名为 "Mbam RecoveryAndHardwareDataStore" 的行 <strong> 。 </strong>当更新 "MBAMRecoveryAndHardwareService" 的配置时，ConnectionString。

6. 更新**configurationStrings**属性的**数据源 =** 值以列出服务器名称以及将恢复和硬件数据库移动到的实例。 例如，$SERVERNAME $ \ $SQLINSTANCENAME $。

7. 若要自动执行此过程，你可以使用与以下命令类似的命令，方法是在每个管理和监视服务器上使用 Windows PowerShell：

   `PS C:\> Set-WebConfigurationProperty '/connectionStrings/add[@name="KeyRecoveryConnectionString"]' -PSPath "IIS:\sites\Microsoft BitLocker Administration and Monitoring\MBAMAdministrationService" -Name "connectionString" -Value “Data Source=$SERVERNAME$\$SQLINSTANCENAME$;Initial Catalog=MBAM Recovery and Hardware;Integrated Security=SSPI;”`

   `PS C:\> Set-WebConfigurationProperty '/connectionStrings/add[@name="Microsoft.Mbam.RecoveryAndHardwareDataStore.ConnectionString"]' -PSPath "IIS:\sites\Microsoft BitLocker Administration and Monitoring\MBAMRecoveryAndHardwareService" -Name "connectionString" -Value "Data Source=$SERVERNAME$\$SQLINSTANCENAME$;Initial Catalog=MBAM Recovery and Hardware;Integrated Security=SSPI;"`

   **注意**  
   将前面示例中的值替换为与你的环境匹配的值：

   -   $SERVERNAME $ \\ $SQLINSTANCENAME $-输入恢复和硬件数据库所在的服务器名称和实例。



**恢复 MBAM 管理和监视网站的所有实例**

1.  在运行 MBAM 管理和监视功能的每台服务器上，使用 Internet Information Services （IIS）管理器控制台启动 MBAM 网站，该网站名为 " **Microsoft BitLocker 管理和监视**"。

2.  若要自动执行此过程，你可以使用 Windows PowerShell，使用类似于下面的命令：

    `PS C:\> Start-Website “Microsoft BitLocker Administration and Monitoring”`

## 移动合规性状态数据库功能


如果你选择将 MBAM 合规状态数据库功能从一台计算机移动到另一台计算机（例如从服务器 A 移动到服务器 B），则应使用以下过程：

1.  停止 MBAM 管理和监视网站的所有实例

2.  在服务器 B 上运行 MBAM 设置

3.  在服务器 A 上备份数据库

4.  将数据库从服务器 A 移动到 B

5.  在服务器 B 上还原数据库

6.  在服务器 B 上配置对数据库的访问

7.  在 MBAM 管理和监视服务器上更新数据库连接数据

8.  恢复 MBAM 管理和监视网站的所有实例

**停止 MBAM 管理和监视网站的所有实例**

1.  在运行 MBAM 管理和监视功能的每台服务器上，使用 Internet Information Services （IIS）管理器控制台停止名为**Microsoft BitLocker 管理和监视**的 MBAM 网站。

2.  若要自动执行此过程，你可以使用 Windows PowerShell，使用类似于下面的命令：

    `PS C:\> Stop-Website “Microsoft BitLocker Administration and Monitoring”`

    **注意**  
    若要执行此命令，必须将用于 PowerShell 的 IIS 模块添加到当前的 PowerShell 实例。 此外，必须更新 PowerShell 执行策略以启用脚本的执行。



**在服务器 B 上运行 MBAM 设置**

1.  在服务器 B 上运行 MBAM 设置，然后选择要安装的合规性状态数据库功能。

2.  若要自动执行此过程，你可以使用 Windows PowerShell，使用类似于下面的命令：

    `PS C:\> MbamSetup.exe /qn I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 AddLocal= ReportsDatabase ADMINANDMON_MACHINENAMES=$DOMAIN$\$SERVERNAME$ COMPLIDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ REPORTS_USERACCOUNT=$DOMAIN$\$USERNAME$`

    **注意**  
    将前面示例中的值替换为与你的环境匹配的值：

    -   $SERVERNAME $ \\ $SQLINSTANCENAME $-输入要将合规性状态数据库移动到的服务器名称和实例。

    -   $DOMAIN $ \\ $SERVERNAME $-输入将联系合规性状态数据库的每个 MBAM 应用程序和监视服务器的域名和服务器名称。 如果有多个域名和服务器名称，请使用分号分隔列表中的每一个名称。 例如，$DOMAIN \\SERVERNAME $; $DOMAIN \ $SERVERNAME $ $。 每个服务器名称必须后接一个 **$** ，如示例中所示。 例如，MyDomain\\MyServerName1 $，MyDomain\\MyServerName2 $。

    -   $DOMAIN $ \\ $USERNAME $-输入合规性和审核报告功能将用于连接到合规性状态数据库的域名和用户名。



**备份服务器 A 上的合规性数据库**

1.  若要备份服务器 A 上的合规性数据库，请使用 SQL Server Management Studio 和名为 "**备份 ...**" 的任务。 默认情况下，数据库名称是**MBAM 合规性状态数据库**。

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

    -- Back up the full MBAM Recovery and Hardware database.

    BACKUP DATABASE [MBAM Compliance Status] TO [MBAM Compliance Status Database Data Device];

    GO
    ```

3.  通过使用 SQL Server PowerShell，使用一个类似于下面的命令运行 SQL 文件：

    `PS C:\> Invoke-Sqlcmd -InputFile "Z:\BackupMBAMComplianceStatusDatabaseScript.sql" –ServerInstance $SERVERNAME$\$SQLINSTANCENAME$`

    **注意**  
    将前面示例中的值替换为与你的环境匹配的值：

    -   $SERVERNAME $ \\ $SQLINSTANCENAME $-输入服务器名称和将备份合规性状态数据库的实例。



**将数据库从服务器 A 移动到 B**

1.  使用 Windows 资源管理器将以下文件从服务器 A 移动到服务器 B：

    -   MBAM 合规性状态数据库数据 .bak

2.  若要自动执行此过程，你可以使用类似于以下使用 Windows PowerShell 的命令：

    `PS C:\> Copy-Item “Z:\MBAM Compliance Status Database Data.bak” \\$SERVERNAME$\$DESTINATIONSHARE$`

    **注意**  
    将前面示例中的值替换为与你的环境匹配的值：

    -   $SERVERNAME $-输入要将文件复制到的服务器名称。

    -   $DESTINATIONSHARE $-输入要将文件复制到的共享和路径的名称。



**在服务器 B 上还原数据库**

1.  使用 SQL Server Management Studio 和名为**Restore database**的任务还原服务器 B 上的合规性状态数据库 ...。

2.  执行任务后，选择数据库备份文件，方法是选择 "发件人设备" 选项，然后使用 "添加" 命令选择 MBAM 合规性状态数据库数据 .bak 文件。 单击 "确定" 完成还原过程。

3.  若要自动执行此过程，请创建包含以下 SQL 脚本的 SQL 文件（.sql）：

    ```sql
    -- Create MBAM Compliance Status Database Data logical backup devices. 

    Use master

    GO

    -- Restore the MBAM Compliance Status database data files.

    RESTORE DATABASE [MBAM Compliance Status Database]

       FROM DISK = 'C:\test\MBAM Compliance Status Database Data.bak'

       WITH REPLACE
    ```

4.  通过使用 SQL Server PowerShell，使用一个类似于下面的命令运行 SQL 文件：

    `PS C:\> Invoke-Sqlcmd -InputFile "Z:\RestoreMBAMComplianceStatusDatabaseScript.sql" -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$`

    **注意**  
    将前面示例中的值替换为与你的环境匹配的值：

    -   $SERVERNAME $ \\ $SQLINSTANCENAME $-输入要将合规性状态数据库还原到的服务器名称和实例。



**在服务器 B 上配置对数据库的访问权限**

1.  在服务器 B 上，使用服务器管理器中的 "本地用户和组" 管理单元将运行 MBAM 管理和监视功能的每台服务器中的计算机帐户添加到名为**MBAM 合规性状态数据库访问**的本地组。

2.  若要自动执行此过程，你可以通过在服务器 B 上使用 Windows PowerShell，使用类似于下面的命令：

    `PS C:\> net localgroup "MBAM Compliance Auditing DB Access" $DOMAIN$\$SERVERNAME$$  /add`

    `PS C:\> net localgroup "MBAM Compliance Auditing DB Access" $DOMAIN$\$REPORTSUSERNAME$  /add`

    **注意**  
    将前面示例中的值替换为适用于你的环境的适用值：

    -   $DOMAIN $ \ \ $SERVERNAME $ $-输入 MBAM 管理和监视服务器的域名和计算机名。 服务器名称后面必须跟有一个 **$** 。例如，MyDomain\\MyServerName1 $。

    -   $DOMAIN $ \\ $REPORTSUSERNAME $-输入用于配置合规性和审核报告的数据源的用户帐户名称



~~~
For each Administration and Monitoring Server that will access the database of your environment, you must run the command that will add the servers to the MBAM Compliance Auditing DB Access local group.
~~~

**更新 MBAM 管理和监视服务器上的数据库连接数据**

1.  在运行 MBAM 管理和监视功能的每台服务器上，使用 Internet Information Services （IIS）管理器控制台更新下列应用程序的连接字符串信息，这些应用程序位于 Microsoft BitLocker 管理和监视网站中：

    -   MBAMAdministrationService

    -   MBAMComplianceStatusService

2.  选择每个应用程序并使用 "**配置编辑器**" 功能，该功能位于 "功能"**视图**的 "**管理**" 部分下。

3.  从 "节列表" 控件中选择 " **configurationStrings** " 选项。

4.  选择名为 **（集合）** 的行，然后通过选择行右侧的按钮打开集合编辑器。

5.  在**集合编辑器**中，当你更新 MBAMAdministrationService 应用程序的配置时，请选择名为**ComplianceStatusConnectionString**的行，或者当你更新 MBAMComplianceStatusService 的配置时，请选择名为**BitLockerManagement**. 的行。

6.  更新**configurationStrings**属性的**数据源 =** 值以列出服务器名称和实例名称。 例如，$SERVERNAME $ \\ $SQLINSTANCENAME，恢复和硬件数据库被移动到该数据库。

7.  若要自动执行此过程，你可以使用 Windows PowerShell 在每个管理和监视服务器上输入一个类似于以下内容的命令：

    `PS C:\> Set-WebConfigurationProperty '/connectionStrings/add[@name="ComplianceStatusConnectionString"]' -PSPath "IIS:\sites\Microsoft BitLocker Administration and Monitoring\MBAMAdministrationService" -Name "connectionString" -Value "Data Source=$SERVERNAME$\$SQLINSTANCENAME$;Initial Catalog=MBAM Compliance Status;Integrated Security=SSPI;"`

    `PS C:\> Set-WebConfigurationProperty '/connectionStrings/add[@name="Microsoft.Windows.Mdop.BitLockerManagement.StatusReportDataStore.ConnectionString"]' -PSPath "IIS:\sites\Microsoft BitLocker Administration and Monitoring\MBAMComplianceStatusService" -Name "connectionString" -Value "Data Source=$SERVERNAME$\$SQLINSTANCENAME;Initial Catalog=MBAM Compliance Status;Integrated Security=SSPI;"`

    **注意**  
    将前面示例中的值替换为与你的环境匹配的值：

    -   $SERVERNAME $ \\ $SQLINSTANCENAME $-输入恢复和硬件数据库所在的服务器名称和实例名称。



**恢复 MBAM 管理和监视网站的所有实例**

1.  在运行 MBAM 管理和监视功能的每台服务器上，使用 Internet Information Services （IIS）管理器控制台启动名为**Microsoft BitLocker 管理和监视**的 MBAM 网站。

2.  若要自动执行此过程，你可以使用 Windows PowerShell 输入类似于以下内容的命令：

    **PS C:\\ &gt; 启动-网站 "Microsoft BitLocker 管理和监视"**

## 移动合规性和审核报告


如果你选择将 MBAM 合规性和审核报告从一台计算机移动到另一台计算机（特别是，如果你将功能从服务器 A 移动到服务器 B），则应使用以下过程和步骤：

1.  在服务器 B 上运行 MBAM 设置

2.  配置对服务器 B 上的合规性和审核报告的访问权限

3.  停止 MBAM 管理和监视网站的所有实例

4.  在 MBAM 管理和监视服务器上更新报表连接数据

5.  恢复 MBAM 管理和监视网站的所有实例

**在服务器 B 上运行 MBAM 设置**

1.  在服务器 B 上运行 MBAM 设置，并仅选择要安装的合规性和审核功能。

2.  若要自动执行此过程，可以使用 Windows PowerShell，使用类似于以下内容的命令：

    `PS C:\> MbamSetup.exe /qn I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 AddLocal=Reports COMPLIDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ REPORTS_USERACCOUNTPW=$PASSWORD$`

    **注意**  
    将前面示例中的值替换为与你的环境匹配的值：

    -   $SERVERNAME $ \\ $SQLINSTANCENAME $-输入合规性状态数据库所在的服务器名称和实例。

    -   $DOMAIN $ \\ $USERNAME $-输入合规性和审核报告功能将用于连接到合规性状态数据库的域名和用户名。

    -   $PASSWORD $-输入将用于连接到合规性状态数据库的用户帐户的密码。



**在服务器 B 上配置合规性和审核报告的访问权限**

1.  在服务器 B 上，使用服务器管理器中的 "本地用户和组" 管理单元添加将有权访问合规性和审核报告的用户帐户。 将用户帐户添加到名为 "MBAM Report Users" 的本地组中。

2.  若要自动执行此过程，你可以通过在服务器 B 上使用 Windows PowerShell，使用类似于以下内容的命令。

    `PS C:\> net localgroup "MBAM Report Users" $DOMAIN$\$REPORTSUSERNAME$  /add`

    **注意**  
    将上述示例中的以下值替换为适用于你的环境的适用值：

    -   $DOMAIN $ \\ $REPORTSUSERNAME $-输入用于配置合规性和审核报告的数据源的用户帐户名称



~~~
The command to add the users to the MBAM Report Users local group must be run for each user that will be accessing the reports in your environment.
~~~

**停止 MBAM 管理和监视网站的所有实例**

1.  在运行 MBAM 管理和监视功能的每台服务器上，使用 Internet 信息服务（IIS）管理器控制台停止名为**Microsoft BitLocker 管理和监视**的 MBAM 网站。

2.  若要自动执行此过程，你可以使用 Windows PowerShell，使用类似于下面的命令：

    `PS C:\> Stop-Website “Microsoft BitLocker Administration and Monitoring”`

**更新 MBAM 管理和监视服务器上的数据库连接数据**

1. 在运行 MBAM 管理和监视功能的每台服务器上，使用 Internet Information Services （IIS）管理器控制台更新合规性报告 URL。

2. 选择 " **Microsoft BitLocker 管理和监视**" 网站并使用 "**配置编辑器**" 功能，该功能可在**功能视图**的 "**管理**" 部分下找到。

3. 从 "节列表" 控件中选择 " **appSettings** " 选项。

4. 在此处，选择名为 **（集合）** 的行，然后通过选择行右侧的按钮打开**集合编辑器**。

5. 在**集合编辑器**中，选择名为 "Microsoft Mbam" 的行。

6. 更新 Mbam 的值以反映服务器 B 的服务器名称。如果已在命名的 SQL Reporting Services 实例上安装了合规性和审核报告功能，请确保将实例的名称添加或更新到 URL。 例如，http://$SERVERNAME $/ReportServer\_ $ SQLSRSINSTANCENAME $/Pages..。。

7. 若要自动执行此过程，你可以使用 Windows PowerShell 在每个管理和监视服务器上输入一个类似于以下内容的命令：

   `PS C:\> Set-WebConfigurationProperty '/appSettings/add[@key="Microsoft.Mbam.Reports.Url"]' -PSPath "IIS:\sites\Microsoft BitLocker Administration and Monitoring" -Name "Value" -Value “http://$SERVERNAME$/ReportServer_$SRSINSTANCENAME$/Pages/ReportViewer.aspx?/Malta+Compliance+Reports/”`

   **注意**  
   将前面示例中的值替换为与你的环境匹配的值：

   -   $SERVERNAME $-输入已安装合规性和审核报告的服务器的名称。

   -   $SRSINSTANCENAME $-输入已安装合规性和审核报告的 SQL Reporting Services 实例的名称。



**恢复 MBAM 管理和监视网站的所有实例**

1.  在运行 MBAM 管理和监视功能的每台服务器上，使用 Internet Information Services （IIS）管理器控制台启动名为**Microsoft BitLocker 管理和监视**的 MBAM 网站。

2.  若要自动执行此过程，你可以使用 Windows PowerShell，使用类似于下面的命令：

    `PS C:\> Start-Website “Microsoft BitLocker Administration and Monitoring”`

    **注意**  
    若要执行此命令，必须将用于 PowerShell 的 IIS 模块添加到 PowerShell 的当前实例。 此外，必须更新 PowerShell 执行策略以启用脚本执行。



## 移动 "管理和监视" 功能


如果你选择将 MBAM 管理和监视报告功能从一台计算机移动到另一台计算机（如果将功能从服务器 A 移动到服务器 B），则应使用以下过程。 该过程包括以下步骤：

1.  在服务器 B 上运行 MBAM 设置

2.  在服务器 B 上配置对数据库的访问

**在服务器 B 上运行 MBAM 设置**

1.  在服务器 B 上运行 MBAM 设置，并仅选择安装的管理功能。

2.  若要自动执行此过程，你可以使用 Windows PowerShell，使用类似于下面的命令：

    `PS C:\> MbamSetup.exe /qn I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 AddLocal=AdministrationMonitoringServer,HardwareCompatibility COMPLIDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ RECOVERYANDHWDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ SRS_REPORTSITEURL=$REPORTSSERVERURL$`

    **注意**  
    将前面示例中的值替换为与你的环境匹配的值：

    -   $SERVERNAME $ \\ $SQLINSTANCENAME $-对于 COMPLIDB \ _SQLINSTANCE 参数，输入合规性状态数据库所在的服务器名称和实例。 对于 RECOVERYANDHWDB \ _SQLINSTANCE 参数，输入恢复和硬件数据库所在位置的服务器名称和实例。

    -   $DOMAIN $ \\ $USERNAME $-输入合规性和审核报告功能将用于连接到合规性状态数据库的域名和用户名。

    -   $ REPORTSSERVERURL $-输入 SQL Reporting Services 网站的主位置的 URL。 如果报表已安装到默认 SRS 实例，URL 格式将设置为 "http://$SERVERNAME $/ReportServer" 的格式。 如果报表已安装到默认 SRS 实例，则 URL 格式将设置为 "http://$SERVERNAME $/ReportServer\_ $ SQLINSTANCENAME $"。



**配置对数据库的访问权限**

1.  在恢复和硬件所在的服务器或服务器上，并部署合规性和审核数据库，请使用服务器管理器中的本地用户和组管理单元，将运行 MBAM 管理和监视功能的每台服务器中的计算机帐户添加到名为 "MBAM 恢复和硬件数据库访问" （恢复和硬件 DB 服务器）和 "MBAM 合规性状态 DB 访问" （合规性和审核数据库服务器）的本地组。

2.  若要自动执行此过程，你可以使用与以下内容类似的命令，方法是在部署合规性和审核数据库的服务器上使用 Windows PowerShell。

    `PS C:\> net localgroup "MBAM Compliance Auditing DB Access" $DOMAIN$\$SERVERNAME$$  /add`

    `PS C:\> net localgroup "MBAM Compliance Auditing DB Access" $DOMAIN$\$REPORTSUSERNAME$  /add`

3.  在部署恢复和硬件数据库的服务器上，使用 Windows PowerShell 运行与以下内容类似的命令。

    `PS C:\> net localgroup "MBAM Recovery and Hardware DB Access" $DOMAIN$\$SERVERNAME$$  /add`

    **注意**  
    将前面示例中的值替换为适用于你的环境的适用值：

    -   $DOMAIN $ \ \ $SERVERNAME $ $-输入 MBAM 管理和监视服务器的域名和计算机名。 服务器名称后面必须跟有一个 **$** 。 例如，MyDomain\\MyServerName1 $）

    -   $DOMAIN $ \\ $REPORTSUSERNAME $-输入用于配置合规性和审核报告的数据源的用户帐户名称。



~~~
The commands listed for adding the server computer accounts to the MBAM local groups must be run for each Administration and Monitoring Server that will be accessing the databases in your environment.
~~~

## 相关主题


[管理 MBAM 1.0 功能](administering-mbam-10-features.md)









