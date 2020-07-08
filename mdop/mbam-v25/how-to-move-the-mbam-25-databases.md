---
title: 如何移动 MBAM 2.5 数据库
description: 如何移动 MBAM 2.5 数据库
author: dansimp
ms.assetid: 34b46f2d-0add-4377-8e4e-04b628fdfcf1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/15/2018
ms.openlocfilehash: 63c509e7ae1460ece815ef6c0a22350f76b52018
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798036"
---
# 如何移动 MBAM 2.5 数据库

使用以下过程将以下数据库从一台计算机移动到另一台计算机上;从服务器 A 到服务器 B，例如：

-   合规性和审核数据库

-   恢复数据库

>[!NOTE]
>在运行 MBAM 配置向导进行更新/配置之前，请务必将数据库还原到计算机 B。

如果数据库不存在，配置向导会创建新的、空的数据库。 还原现有数据库后，此过程将破坏 MBAM 配置。

先还原数据库，然后运行 MBAM 配置向导，选择数据库选项，配置向导将 "连接" 到还原的数据库;如果需要，请在过程中进行升级。

**如果你要移动多个功能，请按以下顺序移动它们：**

1.  恢复数据库

2.  合规性和审核数据库

3.  报告

4.  管理和监视网站

5.  自助服务门户

>[!Note]
>若要运行本主题中提供的 Windows PowerShell 脚本示例，必须更新 Windows PowerShell 执行策略以使脚本能够运行。 有关说明，请参阅[运行 Windows PowerShell 脚本](https://technet.microsoft.com/library/ee176949.aspx)。

## 移动恢复数据库

移动恢复数据库的高级别步骤如下：

1.  停止 MBAM 管理和监视网站的所有实例

2.  备份服务器 A 上的恢复数据库

3.  将恢复数据库从服务器 A 移动到服务器 B

4.  还原服务器 B 上的恢复数据库

5.  在服务器 B 上配置对数据库的访问并更新连接数据

6.  安装 MBAM Server 软件并在服务器 B 上运行 MBAM 服务器配置向导

7.  恢复管理和监视网站的实例

### 如何移动恢复数据库

**停止 MBAM 管理和监视网站的所有实例。** 在运行 MBAM 管理和监视服务器网站的每台服务器上，使用 Internet Information Services （IIS）管理器控制台停止管理和监视网站。

若要自动执行此过程，你可以使用 Windows PowerShell 输入类似于以下内容的命令：

```powershell
Stop-Website "Microsoft BitLocker Administration and Monitoring"
```

>[!NOTE]
>若要运行此命令，必须将适用于 Windows PowerShell 的 Internet information Services （IIS）模块添加到 Windows PowerShell 的当前实例。

### 备份服务器 A 上的恢复数据库

1.  使用 SQL Server Management Studio 中的**备份**任务备份服务器 A 上的恢复数据库。 默认情况下，数据库名称是**MBAM 恢复数据库**。

2.  若要自动执行此过程，请创建包含以下 SQL 脚本的 SQL 文件（.sql），并将 MBAM 恢复数据库更改为使用完整恢复模式：

    ```
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

3.  使用以下值将代码示例中的值替换为与你的环境匹配的值：

    **$PASSWORD $** -用于加密私钥文件的密码。

4.  在 Windows PowerShell 中，运行存储在文件中的脚本，如下所示：

    ```powershell
    Invoke-Sqlcmd -InputFile
    'Z:\BackupMBAMRecoveryandHardwarDatabaseScript.sql' -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$
    ```
5.  使用以下值将代码示例中的值替换为与你的环境匹配的值：

    **$SERVERNAME $ \ $SQLINSTANCENAME $** -将备份恢复数据库的服务器名称和实例。

### 将恢复数据库从服务器 A 移动到服务器 B

使用 Windows 资源管理器将从服务器 A 到服务器 B 的**MBAM 恢复数据库数据 .bak**文件。

若要自动执行此过程，你可以使用 Windows PowerShell 运行类似于以下内容的命令：

```powershell
Copy-Item "Z:\MBAM Recovery Database Data.bak"
\\$SERVERNAME$\$DESTINATIONSHARE$

Copy-Item "Z:\SQLServerInstanceCertificateFile"
\\$SERVERNAME$\$DESTINATIONSHARE$

Copy-Item "Z:\SQLServerInstanceCertificateFilePrivateKey"
\\$SERVERNAME$\$DESTINATIONSHARE$
```
使用下表中的信息将代码示例中的值替换为与你的环境匹配的值。

| **参数**        | **描述**  |
|----------------------|------------------|
| $SERVERNAME $       | 要将文件复制到其中的服务器的名称。 |
| $DESTINATIONSHARE $ | 要将文件复制到的共享和路径的名称。 |


### 还原服务器 B 上的恢复数据库

1.  在 SQL Server Management Studio 中使用 "**还原数据库**" 任务还原服务器 B 上的恢复数据库。

2.  在上一任务完成后，选择 "**从设备**"，然后选择数据库备份文件。

3.  使用 "**添加**" 命令选择**MBAM 恢复数据库数据 .bak**文件，然后单击 **"确定"** 以完成还原过程。

4.  若要自动执行此过程，请创建包含以下 SQL 脚本的 SQL 文件（.sql）：

    ```
    -- Restore MBAM Recovery Database.

    USE master

    GO

    -- Drop certificate created by MBAM Setup.

    DROP CERTIFICATE [MBAM Recovery Encryption Certificate]

    GO

    --Add certificate

    CREATE CERTIFICATE [MBAM Recovery Encryption Certificate]

    FROM FILE = 'Z:\SQLServerInstanceCertificateFile'

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

5.  使用以下值将代码示例中的值替换为与你的环境匹配的值。

    **$PASSWORD $** -用于加密私钥文件的密码。

6.  在 Windows PowerShell 中，运行存储在文件中的脚本，如下所示：

    ```powershell
    Invoke-Sqlcmd -InputFile 'Z:\RestoreMBAMRecoveryandHardwarDatabaseScript.sql' -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$
    ```
7.  使用以下值将代码示例中的值替换为与你的环境匹配的值。

    **$SERVERNAME $ \ $SQLINSTANCENAME $** -恢复数据库将还原到的服务器名称和实例。

### 在服务器 B 上配置对数据库的访问并更新连接数据

1. 验证在已还原的数据库上启用恢复数据库访问的 Microsoft SQL Server 用户登录是否映射到配置过程中提供的访问帐户。

   >[!NOTE]
   >如果登录不同，请使用 SQL Server Management Studio 创建登录，并将其映射到现有数据库用户。

2. 在运行管理和监视网站的服务器上，使用 Internet Information Services （IIS）管理器控制台更新 MBAM 网站的连接字符串信息。

3. 编辑以下注册表项：

   **HKLM\\Software\\Microsoft\\MBAM Server\\Web\\RecoveryDBConnectionString**

4. 将**数据源**值更新为将恢复数据库移动到的服务器和实例的名称（例如，\ $SERVERNAME \ $ \\ $SQLINSTANCENAME）。

5. 将**初始目录**值更新为已恢复的数据库名称。

6. 若要自动执行此过程，你可以使用 Windows PowerShell 命令提示符在 "管理和监视服务器" 上输入类似于以下内容的命令行：

   ```powershell
   reg add "HKEY_LOCAL_MACHINE\SOFTWARE\\Microsoft\MBAM Server\\Web" /v
   RecoveryDBConnectionString /t REG_SZ /d "Integrated Security=SSPI;Initial
   Catalog=$DATABASE$;Data Source=$SERVERNAME$\$SQLINSTANCENAME$" /f

   Set-WebConfigurationProperty
   'connectionStrings/add[@name="KeyRecoveryConnectionString"]' -PSPath
   "IIS:\sites\Microsoft Bitlocker Administration and
   Monitoring\MBAMAdministrationService" -Name "connectionString" -Value "Data
   Source=$SERVERNAME$\$SQLINSTANCENAME$;Initial Catalog=MBAM Recovery and
   Hardware;Integrated Security=SSPI;"

   Set-WebConfigurationProperty
   'connectionStrings/add[\@name="Microsoft.Mbam.RecoveryAndHardwareDataStore.ConnectionString"]'
   -PSPath "IIS:\sites\Microsoft Bitlocker Administration and
   Monitoring\MBAMRecoveryAndHardwareService" -Name "connectionString" -Value
   "Data Source=$SERVERNAME$\$SQLINSTANCENAME$;Initial Catalog=MBAM Recovery
   and Hardware;Integrated Security=SSPI;"
   ```

   >[!Note]
   >此连接字符串由所有本地 MBAM web 应用程序共享。 因此，每台服务器只需更新一次。


7. 使用下表将代码示例中的值替换为与你的环境匹配的值。

   |参数|描述|
   |---------|-----------|
   |$SERVERNAME $/\ $SQLINSTANCENAME $|恢复数据库所在的 SQL Server 的服务器名称和实例。|
   |$DATABASE $|恢复数据库的名称。|


### 安装 MBAM Server 软件并在服务器 B 上运行 MBAM 服务器配置向导

1.  在服务器 B 上安装 MBAM 2.5 服务器软件。有关详细信息，请参阅[安装 MBAM 2.5 Server 软件](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/installing-the-mbam-25-server-software)。

2.  在服务器 B 上，启动 MBAM 服务器配置向导，单击 "**添加新功能**"，然后仅选择**恢复数据库**功能。 有关如何配置数据库的详细信息，请参阅[如何配置 MBAM 2.5 数据库](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-configure-the-mbam-25-databases)。

    >[!TIP]
    >或者，你可以使用**Enable-MbamDatabase** Windows PowerShell Cmdlet 配置恢复数据库。


### 恢复管理和监视网站的实例

在运行管理和监视网站的服务器上，使用 Internet Information Services （IIS）管理器控制台启动 "管理和监视" 网站。

若要自动执行此过程，你可以使用 Windows PowerShell 运行类似于以下内容的命令：

```powershell
Start-Website "Microsoft BitLocker Administration and Monitoring"
```

>[!NOTE]
>若要运行此命令，必须将适用于 Windows PowerShell 的 IIS 模块添加到 Windows PowerShell 的当前实例。

## 移动合规性和审核数据库

移动合规性和审核数据库的高级别步骤如下：

1.  停止 MBAM 管理和监视网站的所有实例

2.  在服务器 A 上备份合规性和审核数据库

3.  将合规性和审核数据库从服务器 A 移动到服务器 B

4.  在服务器 B 上还原合规性和审核数据库

5.  在服务器 B 上配置对数据库的访问并更新连接数据

6.  安装 MBAM Server 软件并在服务器 B 上运行 MBAM 服务器配置向导

7.  恢复管理和监视网站的实例

### 如何移动合规性和审核数据库

**停止 MBAM 管理和监视网站的所有实例。**  在运行 MBAM 管理和监视服务器网站的每台服务器上，使用 Internet Information Services （IIS）管理器控制台停止管理和监视网站。

若要自动执行此过程，你可以使用 Windows PowerShell 输入类似于以下内容的命令：

```powershell
Stop-Website "Microsoft BitLocker Administration and Monitoring"
```

>[!NOTE]
>若要运行此命令，必须将适用于 Windows PowerShell 的 Internet information Services （IIS）模块添加到 Windows PowerShell 的当前实例。

### 在服务器 A 上备份合规性和审核数据库

1.  使用 SQL Server Management Studio 中的**备份**任务备份服务器 A 上的合规性和审核数据库。默认情况下，数据库名称是**MBAM 合规性状态数据库**。

2.  若要自动执行此过程，请创建包含以下 SQL 脚本的 SQL 文件（.sql）：

    ```
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

    -- Back up the full MBAM Compliance Recovery database.

    BACKUP DATABASE [MBAM Compliance Status] TO [MBAM Compliance Status Database Data Device];

    GO

    ```

3.  使用类似于以下内容的 Windows PowerShell 命令运行存储在 .sql 文件中的脚本：

    ```powershell
    Invoke-Sqlcmd -InputFile "Z:\BackupMBAMComplianceStatusDatabaseScript.sql" –ServerInstance     $SERVERNAME$\$SQLINSTANCENAME$

    ```

4.  使用以下值，将代码示例中的值替换为与你的环境匹配的值：

    **$SERVERNAME $ \ $SQLINSTANCENAME $** -将备份合规性和审核数据库的服务器名称和实例。

### 将合规性和审核数据库从服务器 A 移动到服务器 B * *

1.  使用 Windows 资源管理器将**MBAM 合规性状态数据库数据**从服务器 A 移动到服务器 B。

2.  若要自动执行此过程，你可以使用 Windows PowerShell 运行类似于以下内容的命令：

    ```powershell
    Copy-Item "Z:\MBAM Compliance Status Database Data.bak"
    \\$SERVERNAME$\$DESTINATIONSHARE$
    ```

3.  使用下表，将代码示例中的值替换为与你的环境匹配的值。

    | **参数**        | **描述**                                               |
    |----------------------|---------------------------------------------------------------|
    | $SERVERNAME $       | 要将文件复制到其中的服务器的名称。         |
    | $DESTINATIONSHARE $ | 要将文件复制到的共享和路径的名称。 |


### 在服务器 B 上还原合规性和审核数据库

1.  通过在 SQL Server Management Studio 中使用 "**还原数据库**" 任务，在服务器 B 上还原合规性和审核数据库。

2.  在上一任务完成后，选择 "**从设备**"，然后选择数据库备份文件。

3.  使用 "**添加**" 命令选择**MBAM 合规性状态数据库数据 .bak**文件，然后单击 **"确定"** 以完成还原过程。

4.  若要自动执行此过程，请创建包含以下 SQL 脚本的 SQL 文件（.sql）：

    ```
    -- Create MBAM Compliance Status Database Data logical backup devices.

    Use master

    GO

    -- Restore the MBAM Compliance Status database data files.

    RESTORE DATABASE [MBAM Compliance Status]

    FROM DISK = 'C:\test\MBAM Compliance Status Database Data.bak'

    WITH REPLACE

    ```

5.  在 Windows PowerShell 中，运行存储在文件中的脚本，如下所示：

    ```powershell
    Invoke-Sqlcmd -InputFile "Z:\RestoreMBAMComplianceStatusDatabaseScript.sql" -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$

    ```

6.  使用以下值，将代码示例中的值替换为与你的环境匹配的值。

    **$SERVERNAME $ \ $SQLINSTANCENAME $** -将还原合规性和审核数据库的服务器名称和实例。

### 在服务器 B 上配置对数据库的访问并更新连接数据

1. 验证在已还原的数据库上启用合规性和审核数据库访问的 Microsoft SQL Server 用户登录是否映射到配置过程中提供的访问帐户。

   >[!NOTE]
   >如果登录不同，请使用 SQL Server Management Studio 创建登录，并将其映射到现有数据库用户。

2. 在运行管理和监视网站的服务器上，使用 Internet 信息服务（IIS）管理器控制台更新网站的连接字符串信息。

3. 编辑以下注册表项：

   **HKLM\\Software\\Microsoft\\MBAM Server\\Web\\ComplianceDBConnectionString**

4. 将**数据源**值更新为将恢复数据库移动到的服务器和实例的名称（例如，\ $SERVERNAME \ $ \\ $SQLINSTANCENAME）。

5. 将**初始目录**值更新为已恢复的数据库名称。

6. 若要自动执行此过程，你可以使用 Windows PowerShell 命令提示符在 "管理和监视服务器" 上输入类似于以下内容的命令行：

   ```powershell
   reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MBAM Server\Web" /v
   ComplianceDBConnectionString /t REG_SZ /d "Integrated Security=SSPI;Initial
   Catalog=$DATABASE$;Data Source=$SERVERNAME$\$SQLINSTANCENAME$" /f
   ```
   >[!NOTE]
   >此连接字符串由所有本地 MBAM web 应用程序共享。 因此，每台服务器只需更新一次。


7. 使用下表，将代码示例中的值替换为与你的环境匹配的值。

   |参数 | 描述 |
   |---------|------------|
   |$SERVERNAME $ \ $SQLINSTANCENAME $ | 恢复数据库所在的 SQL Server 的服务器名称和实例。|
   |$DATABASE $|已恢复的数据库的名称。|

### 安装 MBAM Server 软件并在服务器 B 上运行 MBAM 服务器配置向导

1.  在服务器 B 上安装 MBAM 2.5 服务器软件。有关详细信息，请参阅[安装 MBAM 2.5 Server 软件](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/installing-the-mbam-25-server-software)。

2.  在服务器 B 上，启动 MBAM 服务器配置向导，单击 "**添加新功能**"，然后仅选择**合规性和审核数据库**功能。 有关如何配置数据库的详细信息，请参阅[如何配置 MBAM 2.5 数据库](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-configure-the-mbam-25-databases)。

    >[!TIP]
    >或者，你可以使用**Enable-MbamDatabase** Windows PowerShell cmdlet 来配置合规性和审核数据库。


### 恢复管理和监视网站的实例

在运行管理和监视网站的服务器上，使用 Internet Information Services （IIS）管理器控制台启动 "管理和监视" 网站。

若要自动执行此过程，你可以使用 Windows PowerShell 运行类似于以下内容的命令：

```powershell
Start-Website "Microsoft BitLocker Administration and Monitoring"
```

>[!NOTE]
>若要运行此命令，必须将适用于 Windows PowerShell 的 IIS 模块添加到 Windows PowerShell 的当前实例。
