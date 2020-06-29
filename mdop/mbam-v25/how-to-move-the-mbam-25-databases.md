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
# <span data-ttu-id="27daf-103">如何移动 MBAM 2.5 数据库</span><span class="sxs-lookup"><span data-stu-id="27daf-103">How to Move the MBAM 2.5 Databases</span></span>

<span data-ttu-id="27daf-104">使用以下过程将以下数据库从一台计算机移动到另一台计算机上;从服务器 A 到服务器 B，例如：</span><span class="sxs-lookup"><span data-stu-id="27daf-104">Use these procedures to move the following databases from one computer to another; from Server A to Server B, for example:</span></span>

-   <span data-ttu-id="27daf-105">合规性和审核数据库</span><span class="sxs-lookup"><span data-stu-id="27daf-105">Compliance and Audit Database</span></span>

-   <span data-ttu-id="27daf-106">恢复数据库</span><span class="sxs-lookup"><span data-stu-id="27daf-106">Recovery Database</span></span>

>[!NOTE]
><span data-ttu-id="27daf-107">在运行 MBAM 配置向导进行更新/配置之前，请务必将数据库还原到计算机 B。</span><span class="sxs-lookup"><span data-stu-id="27daf-107">It is important that the databases be restored to Machine B PRIOR to running the MBAM Configuration Wizard to update/configure them.</span></span>

<span data-ttu-id="27daf-108">如果数据库不存在，配置向导会创建新的、空的数据库。</span><span class="sxs-lookup"><span data-stu-id="27daf-108">If the databases are NOT present, the Configuration Wizard creates NEW, empty, databases.</span></span> <span data-ttu-id="27daf-109">还原现有数据库后，此过程将破坏 MBAM 配置。</span><span class="sxs-lookup"><span data-stu-id="27daf-109">When your existing databases are then restored, this process will break the MBAM configuration.</span></span>

<span data-ttu-id="27daf-110">先还原数据库，然后运行 MBAM 配置向导，选择数据库选项，配置向导将 "连接" 到还原的数据库;如果需要，请在过程中进行升级。</span><span class="sxs-lookup"><span data-stu-id="27daf-110">Restore the databases FIRST, then run the MBAM Configuration Wizard, choose the database option, and the Configuration Wizard will “connect” to the databases you restored; upgrading them if needed as part of the process.</span></span>

**<span data-ttu-id="27daf-111">如果你要移动多个功能，请按以下顺序移动它们：</span><span class="sxs-lookup"><span data-stu-id="27daf-111">If you are moving multiple features, move them in the following order:</span></span>**

1.  <span data-ttu-id="27daf-112">恢复数据库</span><span class="sxs-lookup"><span data-stu-id="27daf-112">Recovery Database</span></span>

2.  <span data-ttu-id="27daf-113">合规性和审核数据库</span><span class="sxs-lookup"><span data-stu-id="27daf-113">Compliance and Audit Database</span></span>

3.  <span data-ttu-id="27daf-114">报告</span><span class="sxs-lookup"><span data-stu-id="27daf-114">Reports</span></span>

4.  <span data-ttu-id="27daf-115">管理和监视网站</span><span class="sxs-lookup"><span data-stu-id="27daf-115">Administration and Monitoring Website</span></span>

5.  <span data-ttu-id="27daf-116">自助服务门户</span><span class="sxs-lookup"><span data-stu-id="27daf-116">Self-Service Portal</span></span>

>[!Note]
><span data-ttu-id="27daf-117">若要运行本主题中提供的 Windows PowerShell 脚本示例，必须更新 Windows PowerShell 执行策略以使脚本能够运行。</span><span class="sxs-lookup"><span data-stu-id="27daf-117">To run the example Windows PowerShell scripts provided in this topic, you must update the Windows PowerShell execution policy to enable scripts to be run.</span></span> <span data-ttu-id="27daf-118">有关说明，请参阅[运行 Windows PowerShell 脚本](https://technet.microsoft.com/library/ee176949.aspx)。</span><span class="sxs-lookup"><span data-stu-id="27daf-118">See [Running Windows PowerShell Scripts](https://technet.microsoft.com/library/ee176949.aspx) for instructions.</span></span>

## <span data-ttu-id="27daf-119">移动恢复数据库</span><span class="sxs-lookup"><span data-stu-id="27daf-119">Move the Recovery Database</span></span>

<span data-ttu-id="27daf-120">移动恢复数据库的高级别步骤如下：</span><span class="sxs-lookup"><span data-stu-id="27daf-120">The high-level steps for moving the Recovery Database are:</span></span>

1.  <span data-ttu-id="27daf-121">停止 MBAM 管理和监视网站的所有实例</span><span class="sxs-lookup"><span data-stu-id="27daf-121">Stop all instances of the MBAM Administration and Monitoring Website</span></span>

2.  <span data-ttu-id="27daf-122">备份服务器 A 上的恢复数据库</span><span class="sxs-lookup"><span data-stu-id="27daf-122">Back up the Recovery Database on Server A</span></span>

3.  <span data-ttu-id="27daf-123">将恢复数据库从服务器 A 移动到服务器 B</span><span class="sxs-lookup"><span data-stu-id="27daf-123">Move the Recovery Database from Server A to Server B</span></span>

4.  <span data-ttu-id="27daf-124">还原服务器 B 上的恢复数据库</span><span class="sxs-lookup"><span data-stu-id="27daf-124">Restore the Recovery Database on Server B</span></span>

5.  <span data-ttu-id="27daf-125">在服务器 B 上配置对数据库的访问并更新连接数据</span><span class="sxs-lookup"><span data-stu-id="27daf-125">Configure access to the Database on Server B and update connection data</span></span>

6.  <span data-ttu-id="27daf-126">安装 MBAM Server 软件并在服务器 B 上运行 MBAM 服务器配置向导</span><span class="sxs-lookup"><span data-stu-id="27daf-126">Install MBAM Server software and run the MBAM Server Configuration wizard on Server B</span></span>

7.  <span data-ttu-id="27daf-127">恢复管理和监视网站的实例</span><span class="sxs-lookup"><span data-stu-id="27daf-127">Resume the instance of the Administration and Monitoring Website</span></span>

### <span data-ttu-id="27daf-128">如何移动恢复数据库</span><span class="sxs-lookup"><span data-stu-id="27daf-128">How to move the Recovery Database</span></span>

**<span data-ttu-id="27daf-129">停止 MBAM 管理和监视网站的所有实例。</span><span class="sxs-lookup"><span data-stu-id="27daf-129">Stop all instances of the MBAM Administration and Monitoring Website.</span></span>** <span data-ttu-id="27daf-130">在运行 MBAM 管理和监视服务器网站的每台服务器上，使用 Internet Information Services （IIS）管理器控制台停止管理和监视网站。</span><span class="sxs-lookup"><span data-stu-id="27daf-130">On each server that is running the MBAM Administration and Monitoring Server Website, use the Internet Information Services (IIS) Manager console to stop the Administration and Monitoring Website.</span></span>

<span data-ttu-id="27daf-131">若要自动执行此过程，你可以使用 Windows PowerShell 输入类似于以下内容的命令：</span><span class="sxs-lookup"><span data-stu-id="27daf-131">To automate this procedure, you can use Windows PowerShell to enter a command that is similar to the following:</span></span>

```powershell
Stop-Website "Microsoft BitLocker Administration and Monitoring"
```

>[!NOTE]
><span data-ttu-id="27daf-132">若要运行此命令，必须将适用于 Windows PowerShell 的 Internet information Services （IIS）模块添加到 Windows PowerShell 的当前实例。</span><span class="sxs-lookup"><span data-stu-id="27daf-132">To run this command, you must add the Internet Information Services (IIS) module for Windows PowerShell to the current instance of Windows PowerShell.</span></span>

### <span data-ttu-id="27daf-133">备份服务器 A 上的恢复数据库</span><span class="sxs-lookup"><span data-stu-id="27daf-133">Back up the Recovery Database on Server A</span></span>

1.  <span data-ttu-id="27daf-134">使用 SQL Server Management Studio 中的**备份**任务备份服务器 A 上的恢复数据库。 默认情况下，数据库名称是**MBAM 恢复数据库**。</span><span class="sxs-lookup"><span data-stu-id="27daf-134">Use the **Back Up** task in SQL Server Management Studio to back up the Recovery Database on Server A.  By default, the database name is **MBAM Recovery Database**.</span></span>

2.  <span data-ttu-id="27daf-135">若要自动执行此过程，请创建包含以下 SQL 脚本的 SQL 文件（.sql），并将 MBAM 恢复数据库更改为使用完整恢复模式：</span><span class="sxs-lookup"><span data-stu-id="27daf-135">To automate this procedure, create a SQL file (.sql) that contains the following SQL script, and change the MBAM Recovery Database to use the full recovery mode:</span></span>

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

3.  <span data-ttu-id="27daf-136">使用以下值将代码示例中的值替换为与你的环境匹配的值：</span><span class="sxs-lookup"><span data-stu-id="27daf-136">Use the following value to replace the values in the code example with values that match your environment:</span></span>

    <span data-ttu-id="27daf-137">**$PASSWORD $** -用于加密私钥文件的密码。</span><span class="sxs-lookup"><span data-stu-id="27daf-137">**$PASSWORD$** - password that you use to encrypt the Private Key file.</span></span>

4.  <span data-ttu-id="27daf-138">在 Windows PowerShell 中，运行存储在文件中的脚本，如下所示：</span><span class="sxs-lookup"><span data-stu-id="27daf-138">In Windows PowerShell, run the script that is stored in the file and similar to the following:</span></span>

    ```powershell
    Invoke-Sqlcmd -InputFile
    'Z:\BackupMBAMRecoveryandHardwarDatabaseScript.sql' -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$
    ```
5.  <span data-ttu-id="27daf-139">使用以下值将代码示例中的值替换为与你的环境匹配的值：</span><span class="sxs-lookup"><span data-stu-id="27daf-139">Use the following value to replace the values in the code example with values that match your environment:</span></span>

    <span data-ttu-id="27daf-140">**$SERVERNAME $ \ $SQLINSTANCENAME $** -将备份恢复数据库的服务器名称和实例。</span><span class="sxs-lookup"><span data-stu-id="27daf-140">**$SERVERNAME$\$SQLINSTANCENAME$** - server name and instance from which the Recovery Database will be backed up.</span></span>

### <span data-ttu-id="27daf-141">将恢复数据库从服务器 A 移动到服务器 B</span><span class="sxs-lookup"><span data-stu-id="27daf-141">Move the Recovery Database from Server A to Server B</span></span>

<span data-ttu-id="27daf-142">使用 Windows 资源管理器将从服务器 A 到服务器 B 的**MBAM 恢复数据库数据 .bak**文件。</span><span class="sxs-lookup"><span data-stu-id="27daf-142">Use Windows Explorer to move the **MBAM Recovery Database Data.bak** file from Server A to Server B.</span></span>

<span data-ttu-id="27daf-143">若要自动执行此过程，你可以使用 Windows PowerShell 运行类似于以下内容的命令：</span><span class="sxs-lookup"><span data-stu-id="27daf-143">To automate this procedure, you can use Windows PowerShell to run a command that is similar to the following:</span></span>

```powershell
Copy-Item "Z:\MBAM Recovery Database Data.bak"
\\$SERVERNAME$\$DESTINATIONSHARE$

Copy-Item "Z:\SQLServerInstanceCertificateFile"
\\$SERVERNAME$\$DESTINATIONSHARE$

Copy-Item "Z:\SQLServerInstanceCertificateFilePrivateKey"
\\$SERVERNAME$\$DESTINATIONSHARE$
```
<span data-ttu-id="27daf-144">使用下表中的信息将代码示例中的值替换为与你的环境匹配的值。</span><span class="sxs-lookup"><span data-stu-id="27daf-144">Use the information in the following table to replace the values in the code example with values that match your environment.</span></span>

| **<span data-ttu-id="27daf-145">参数</span><span class="sxs-lookup"><span data-stu-id="27daf-145">Parameter</span></span>**        | **<span data-ttu-id="27daf-146">描述</span><span class="sxs-lookup"><span data-stu-id="27daf-146">Description</span></span>**  |
|----------------------|------------------|
| <span data-ttu-id="27daf-147">$SERVERNAME $</span><span class="sxs-lookup"><span data-stu-id="27daf-147">$SERVERNAME$</span></span>       | <span data-ttu-id="27daf-148">要将文件复制到其中的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="27daf-148">Name of the server to which the files will be copied.</span></span> |
| <span data-ttu-id="27daf-149">$DESTINATIONSHARE $</span><span class="sxs-lookup"><span data-stu-id="27daf-149">$DESTINATIONSHARE$</span></span> | <span data-ttu-id="27daf-150">要将文件复制到的共享和路径的名称。</span><span class="sxs-lookup"><span data-stu-id="27daf-150">Name of the share and path to which the files will be copied.</span></span> |


### <span data-ttu-id="27daf-151">还原服务器 B 上的恢复数据库</span><span class="sxs-lookup"><span data-stu-id="27daf-151">Restore the Recovery Database on Server B</span></span>

1.  <span data-ttu-id="27daf-152">在 SQL Server Management Studio 中使用 "**还原数据库**" 任务还原服务器 B 上的恢复数据库。</span><span class="sxs-lookup"><span data-stu-id="27daf-152">Restore the Recovery Database on Server B by using the **Restore Database** task in SQL Server Management Studio.</span></span>

2.  <span data-ttu-id="27daf-153">在上一任务完成后，选择 "**从设备**"，然后选择数据库备份文件。</span><span class="sxs-lookup"><span data-stu-id="27daf-153">When the previous task finishes, select **From Device**, and then select the database backup file.</span></span>

3.  <span data-ttu-id="27daf-154">使用 "**添加**" 命令选择**MBAM 恢复数据库数据 .bak**文件，然后单击 **"确定"** 以完成还原过程。</span><span class="sxs-lookup"><span data-stu-id="27daf-154">Use the **Add** command to select the **MBAM Recovery Database Data.bak** file, and click **OK** to complete the restoration process.</span></span>

4.  <span data-ttu-id="27daf-155">若要自动执行此过程，请创建包含以下 SQL 脚本的 SQL 文件（.sql）：</span><span class="sxs-lookup"><span data-stu-id="27daf-155">To automate this procedure, create a SQL file (.sql) that contains the following SQL script:</span></span>

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

5.  <span data-ttu-id="27daf-156">使用以下值将代码示例中的值替换为与你的环境匹配的值。</span><span class="sxs-lookup"><span data-stu-id="27daf-156">Use the following value to replace the values in the code example with values that match your environment.</span></span>

    <span data-ttu-id="27daf-157">**$PASSWORD $** -用于加密私钥文件的密码。</span><span class="sxs-lookup"><span data-stu-id="27daf-157">**$PASSWORD$** - password that you used to encrypt the Private Key file.</span></span>

6.  <span data-ttu-id="27daf-158">在 Windows PowerShell 中，运行存储在文件中的脚本，如下所示：</span><span class="sxs-lookup"><span data-stu-id="27daf-158">In Windows PowerShell, run the script that is stored in the file and similar to the following:</span></span>

    ```powershell
    Invoke-Sqlcmd -InputFile 'Z:\RestoreMBAMRecoveryandHardwarDatabaseScript.sql' -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$
    ```
7.  <span data-ttu-id="27daf-159">使用以下值将代码示例中的值替换为与你的环境匹配的值。</span><span class="sxs-lookup"><span data-stu-id="27daf-159">Use the following value to replace the values in the code example with values that match your environment.</span></span>

    <span data-ttu-id="27daf-160">**$SERVERNAME $ \ $SQLINSTANCENAME $** -恢复数据库将还原到的服务器名称和实例。</span><span class="sxs-lookup"><span data-stu-id="27daf-160">**$SERVERNAME$\$SQLINSTANCENAME$** - Server name and instance to which the Recovery Database will be restored.</span></span>

### <span data-ttu-id="27daf-161">在服务器 B 上配置对数据库的访问并更新连接数据</span><span class="sxs-lookup"><span data-stu-id="27daf-161">Configure access to the Database on Server B and update connection data</span></span>

1. <span data-ttu-id="27daf-162">验证在已还原的数据库上启用恢复数据库访问的 Microsoft SQL Server 用户登录是否映射到配置过程中提供的访问帐户。</span><span class="sxs-lookup"><span data-stu-id="27daf-162">Verify that the Microsoft SQL Server user login that enables Recovery Database access on the restored database is mapped to the access account that you provided during the configuration process.</span></span>

   >[!NOTE]
   ><span data-ttu-id="27daf-163">如果登录不同，请使用 SQL Server Management Studio 创建登录，并将其映射到现有数据库用户。</span><span class="sxs-lookup"><span data-stu-id="27daf-163">If the login is not the same, create a login by using SQL Server Management Studio, and map it to the existing database user.</span></span>

2. <span data-ttu-id="27daf-164">在运行管理和监视网站的服务器上，使用 Internet Information Services （IIS）管理器控制台更新 MBAM 网站的连接字符串信息。</span><span class="sxs-lookup"><span data-stu-id="27daf-164">On the server that is running the Administration and Monitoring Website, use the Internet Information Services (IIS) Manager console to update the connection string information for the MBAM websites.</span></span>

3. <span data-ttu-id="27daf-165">编辑以下注册表项：</span><span class="sxs-lookup"><span data-stu-id="27daf-165">Edit the following registry key:</span></span>

   **<span data-ttu-id="27daf-166">HKLM\\Software\\Microsoft\\MBAM Server\\Web\\RecoveryDBConnectionString</span><span class="sxs-lookup"><span data-stu-id="27daf-166">HKLM\\Software\\Microsoft\\MBAM Server\\Web\\RecoveryDBConnectionString</span></span>**

4. <span data-ttu-id="27daf-167">将**数据源**值更新为将恢复数据库移动到的服务器和实例的名称（例如，\ $SERVERNAME \ $ \\ $SQLINSTANCENAME）。</span><span class="sxs-lookup"><span data-stu-id="27daf-167">Update the **Data Source** value with the name of the server and instance (for example, \$SERVERNAME\$\\\$SQLINSTANCENAME) to which the Recovery Database was moved.</span></span>

5. <span data-ttu-id="27daf-168">将**初始目录**值更新为已恢复的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="27daf-168">Update the **Initial Catalog** value with the recovered database name.</span></span>

6. <span data-ttu-id="27daf-169">若要自动执行此过程，你可以使用 Windows PowerShell 命令提示符在 "管理和监视服务器" 上输入类似于以下内容的命令行：</span><span class="sxs-lookup"><span data-stu-id="27daf-169">To automate this process, you can use the Windows PowerShell command prompt to enter a command line on the Administration and Monitoring Server that is similar to the following:</span></span>

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
   ><span data-ttu-id="27daf-170">此连接字符串由所有本地 MBAM web 应用程序共享。</span><span class="sxs-lookup"><span data-stu-id="27daf-170">This connection string is shared by all local MBAM web applications.</span></span> <span data-ttu-id="27daf-171">因此，每台服务器只需更新一次。</span><span class="sxs-lookup"><span data-stu-id="27daf-171">Therefore, it needs to be updated only once per server.</span></span>


7. <span data-ttu-id="27daf-172">使用下表将代码示例中的值替换为与你的环境匹配的值。</span><span class="sxs-lookup"><span data-stu-id="27daf-172">Use the following table to replace the values in the code example with values that match your environment.</span></span>

   |<span data-ttu-id="27daf-173">参数</span><span class="sxs-lookup"><span data-stu-id="27daf-173">Parameter</span></span>|<span data-ttu-id="27daf-174">描述</span><span class="sxs-lookup"><span data-stu-id="27daf-174">Description</span></span>|
   |---------|-----------|
   |<span data-ttu-id="27daf-175">$SERVERNAME $/\ $SQLINSTANCENAME $</span><span class="sxs-lookup"><span data-stu-id="27daf-175">$SERVERNAME$/\$SQLINSTANCENAME$</span></span>|<span data-ttu-id="27daf-176">恢复数据库所在的 SQL Server 的服务器名称和实例。</span><span class="sxs-lookup"><span data-stu-id="27daf-176">Server name and instance of SQL Server where the Recovery Database is located.</span></span>|
   |<span data-ttu-id="27daf-177">$DATABASE $</span><span class="sxs-lookup"><span data-stu-id="27daf-177">$DATABASE$</span></span>|<span data-ttu-id="27daf-178">恢复数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="27daf-178">Name of the Recovery database.</span></span>|


### <span data-ttu-id="27daf-179">安装 MBAM Server 软件并在服务器 B 上运行 MBAM 服务器配置向导</span><span class="sxs-lookup"><span data-stu-id="27daf-179">Install MBAM Server software and run the MBAM Server Configuration wizard on Server B</span></span>

1.  <span data-ttu-id="27daf-180">在服务器 B 上安装 MBAM 2.5 服务器软件。有关详细信息，请参阅[安装 MBAM 2.5 Server 软件](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/installing-the-mbam-25-server-software)。</span><span class="sxs-lookup"><span data-stu-id="27daf-180">Install the MBAM 2.5 Server software on Server B. For details, see [Installing the MBAM 2.5 Server Software](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/installing-the-mbam-25-server-software).</span></span>

2.  <span data-ttu-id="27daf-181">在服务器 B 上，启动 MBAM 服务器配置向导，单击 "**添加新功能**"，然后仅选择**恢复数据库**功能。</span><span class="sxs-lookup"><span data-stu-id="27daf-181">On Server B, start the MBAM Server Configuration wizard, click **Add New Features**, and then select only the **Recovery Database** feature.</span></span> <span data-ttu-id="27daf-182">有关如何配置数据库的详细信息，请参阅[如何配置 MBAM 2.5 数据库](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-configure-the-mbam-25-databases)。</span><span class="sxs-lookup"><span data-stu-id="27daf-182">For details on how to configure the databases, see [How to Configure the MBAM 2.5 Databases](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-configure-the-mbam-25-databases).</span></span>

    >[!TIP]
    ><span data-ttu-id="27daf-183">或者，你可以使用**Enable-MbamDatabase** Windows PowerShell Cmdlet 配置恢复数据库。</span><span class="sxs-lookup"><span data-stu-id="27daf-183">Alternatively, you can use the **Enable-MbamDatabase** Windows PowerShell cmdlet to configure the Recovery Database.</span></span>


### <span data-ttu-id="27daf-184">恢复管理和监视网站的实例</span><span class="sxs-lookup"><span data-stu-id="27daf-184">Resume the instance of the Administration and Monitoring Website</span></span>

<span data-ttu-id="27daf-185">在运行管理和监视网站的服务器上，使用 Internet Information Services （IIS）管理器控制台启动 "管理和监视" 网站。</span><span class="sxs-lookup"><span data-stu-id="27daf-185">On the server that is running the Administration and Monitoring Website, use the Internet Information Services (IIS) Manager console to start the Administration and Monitoring Website.</span></span>

<span data-ttu-id="27daf-186">若要自动执行此过程，你可以使用 Windows PowerShell 运行类似于以下内容的命令：</span><span class="sxs-lookup"><span data-stu-id="27daf-186">To automate this procedure, you can use Windows PowerShell to run a command that is similar to the following:</span></span>

```powershell
Start-Website "Microsoft BitLocker Administration and Monitoring"
```

>[!NOTE]
><span data-ttu-id="27daf-187">若要运行此命令，必须将适用于 Windows PowerShell 的 IIS 模块添加到 Windows PowerShell 的当前实例。</span><span class="sxs-lookup"><span data-stu-id="27daf-187">To run this command, you must add the IIS module for Windows PowerShell to the current instance of Windows PowerShell.</span></span>

## <span data-ttu-id="27daf-188">移动合规性和审核数据库</span><span class="sxs-lookup"><span data-stu-id="27daf-188">Move the Compliance and Audit Database</span></span>

<span data-ttu-id="27daf-189">移动合规性和审核数据库的高级别步骤如下：</span><span class="sxs-lookup"><span data-stu-id="27daf-189">The high-level steps for moving the Compliance and Audit Database are:</span></span>

1.  <span data-ttu-id="27daf-190">停止 MBAM 管理和监视网站的所有实例</span><span class="sxs-lookup"><span data-stu-id="27daf-190">Stop all instances of the MBAM Administration and Monitoring Website</span></span>

2.  <span data-ttu-id="27daf-191">在服务器 A 上备份合规性和审核数据库</span><span class="sxs-lookup"><span data-stu-id="27daf-191">Back up the Compliance and Audit Database on Server A</span></span>

3.  <span data-ttu-id="27daf-192">将合规性和审核数据库从服务器 A 移动到服务器 B</span><span class="sxs-lookup"><span data-stu-id="27daf-192">Move the Compliance and Audit Database from Server A to Server B</span></span>

4.  <span data-ttu-id="27daf-193">在服务器 B 上还原合规性和审核数据库</span><span class="sxs-lookup"><span data-stu-id="27daf-193">Restore the Compliance and Audit Database on Server B</span></span>

5.  <span data-ttu-id="27daf-194">在服务器 B 上配置对数据库的访问并更新连接数据</span><span class="sxs-lookup"><span data-stu-id="27daf-194">Configure access to the Database on Server B and update connection data</span></span>

6.  <span data-ttu-id="27daf-195">安装 MBAM Server 软件并在服务器 B 上运行 MBAM 服务器配置向导</span><span class="sxs-lookup"><span data-stu-id="27daf-195">Install MBAM Server software and run the MBAM Server Configuration wizard on Server B</span></span>

7.  <span data-ttu-id="27daf-196">恢复管理和监视网站的实例</span><span class="sxs-lookup"><span data-stu-id="27daf-196">Resume the instance of the Administration and Monitoring Website</span></span>

### <span data-ttu-id="27daf-197">如何移动合规性和审核数据库</span><span class="sxs-lookup"><span data-stu-id="27daf-197">How to move the Compliance and Audit Database</span></span>

**<span data-ttu-id="27daf-198">停止 MBAM 管理和监视网站的所有实例。</span><span class="sxs-lookup"><span data-stu-id="27daf-198">Stop all instances of the MBAM Administration and Monitoring Website.</span></span>**  <span data-ttu-id="27daf-199">在运行 MBAM 管理和监视服务器网站的每台服务器上，使用 Internet Information Services （IIS）管理器控制台停止管理和监视网站。</span><span class="sxs-lookup"><span data-stu-id="27daf-199">On each server that is running the MBAM Administration and Monitoring Server Website, use the Internet Information Services (IIS) Manager console to stop the Administration and Monitoring Website.</span></span>

<span data-ttu-id="27daf-200">若要自动执行此过程，你可以使用 Windows PowerShell 输入类似于以下内容的命令：</span><span class="sxs-lookup"><span data-stu-id="27daf-200">To automate this procedure, you can use Windows PowerShell to enter a command that is similar to the following:</span></span>

```powershell
Stop-Website "Microsoft BitLocker Administration and Monitoring"
```

>[!NOTE]
><span data-ttu-id="27daf-201">若要运行此命令，必须将适用于 Windows PowerShell 的 Internet information Services （IIS）模块添加到 Windows PowerShell 的当前实例。</span><span class="sxs-lookup"><span data-stu-id="27daf-201">To run this command, you must add the Internet Information Services (IIS) module for Windows PowerShell to the current instance of Windows PowerShell.</span></span>

### <span data-ttu-id="27daf-202">在服务器 A 上备份合规性和审核数据库</span><span class="sxs-lookup"><span data-stu-id="27daf-202">Back up the Compliance and Audit Database on Server A</span></span>

1.  <span data-ttu-id="27daf-203">使用 SQL Server Management Studio 中的**备份**任务备份服务器 A 上的合规性和审核数据库。默认情况下，数据库名称是**MBAM 合规性状态数据库**。</span><span class="sxs-lookup"><span data-stu-id="27daf-203">Use the **Back Up** task in SQL Server Management Studio to back up the Compliance and Audit Database on Server A. By default, the database name is **MBAM Compliance Status Database**.</span></span>

2.  <span data-ttu-id="27daf-204">若要自动执行此过程，请创建包含以下 SQL 脚本的 SQL 文件（.sql）：</span><span class="sxs-lookup"><span data-stu-id="27daf-204">To automate this procedure, create a SQL file (.sql) that contains the following SQL script:</span></span>

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

3.  <span data-ttu-id="27daf-205">使用类似于以下内容的 Windows PowerShell 命令运行存储在 .sql 文件中的脚本：</span><span class="sxs-lookup"><span data-stu-id="27daf-205">Run the script that is stored in the .sql file by using a Windows PowerShell command that is similar to the following:</span></span>

    ```powershell
    Invoke-Sqlcmd -InputFile "Z:\BackupMBAMComplianceStatusDatabaseScript.sql" –ServerInstance     $SERVERNAME$\$SQLINSTANCENAME$

    ```

4.  <span data-ttu-id="27daf-206">使用以下值，将代码示例中的值替换为与你的环境匹配的值：</span><span class="sxs-lookup"><span data-stu-id="27daf-206">Using the following value, replace the values in the code example with values that match your environment:</span></span>

    <span data-ttu-id="27daf-207">**$SERVERNAME $ \ $SQLINSTANCENAME $** -将备份合规性和审核数据库的服务器名称和实例。</span><span class="sxs-lookup"><span data-stu-id="27daf-207">**$SERVERNAME$\$SQLINSTANCENAME$** - server name and instance from which the Compliance and Audit Database will be backed up.</span></span>

### <span data-ttu-id="27daf-208">将合规性和审核数据库从服务器 A 移动到服务器 B \* \*</span><span class="sxs-lookup"><span data-stu-id="27daf-208">Move the Compliance and Audit Database from Server A to Server B\*\*</span></span>

1.  <span data-ttu-id="27daf-209">使用 Windows 资源管理器将**MBAM 合规性状态数据库数据**从服务器 A 移动到服务器 B。</span><span class="sxs-lookup"><span data-stu-id="27daf-209">Use Windows Explorer to move the **MBAM Compliance Status Database Data.bak** file from Server A to Server B.</span></span>

2.  <span data-ttu-id="27daf-210">若要自动执行此过程，你可以使用 Windows PowerShell 运行类似于以下内容的命令：</span><span class="sxs-lookup"><span data-stu-id="27daf-210">To automate this procedure, you can use Windows PowerShell to run a command that is similar to the following:</span></span>

    ```powershell
    Copy-Item "Z:\MBAM Compliance Status Database Data.bak"
    \\$SERVERNAME$\$DESTINATIONSHARE$
    ```

3.  <span data-ttu-id="27daf-211">使用下表，将代码示例中的值替换为与你的环境匹配的值。</span><span class="sxs-lookup"><span data-stu-id="27daf-211">Using the following table, replace the values in the code example with values that match your environment.</span></span>

    | **<span data-ttu-id="27daf-212">参数</span><span class="sxs-lookup"><span data-stu-id="27daf-212">Parameter</span></span>**        | **<span data-ttu-id="27daf-213">描述</span><span class="sxs-lookup"><span data-stu-id="27daf-213">Description</span></span>**                                               |
    |----------------------|---------------------------------------------------------------|
    | <span data-ttu-id="27daf-214">$SERVERNAME $</span><span class="sxs-lookup"><span data-stu-id="27daf-214">$SERVERNAME$</span></span>       | <span data-ttu-id="27daf-215">要将文件复制到其中的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="27daf-215">Name of the server to which the files will be copied.</span></span>         |
    | <span data-ttu-id="27daf-216">$DESTINATIONSHARE $</span><span class="sxs-lookup"><span data-stu-id="27daf-216">$DESTINATIONSHARE$</span></span> | <span data-ttu-id="27daf-217">要将文件复制到的共享和路径的名称。</span><span class="sxs-lookup"><span data-stu-id="27daf-217">Name of the share and path to which the files will be copied.</span></span> |


### <span data-ttu-id="27daf-218">在服务器 B 上还原合规性和审核数据库</span><span class="sxs-lookup"><span data-stu-id="27daf-218">Restore the Compliance and Audit Database on Server B</span></span>

1.  <span data-ttu-id="27daf-219">通过在 SQL Server Management Studio 中使用 "**还原数据库**" 任务，在服务器 B 上还原合规性和审核数据库。</span><span class="sxs-lookup"><span data-stu-id="27daf-219">Restore the Compliance and Audit Database on Server B by using the **Restore Database** task in SQL Server Management Studio.</span></span>

2.  <span data-ttu-id="27daf-220">在上一任务完成后，选择 "**从设备**"，然后选择数据库备份文件。</span><span class="sxs-lookup"><span data-stu-id="27daf-220">When the previous task finishes, select **From Device**, and then select the database backup file.</span></span>

3.  <span data-ttu-id="27daf-221">使用 "**添加**" 命令选择**MBAM 合规性状态数据库数据 .bak**文件，然后单击 **"确定"** 以完成还原过程。</span><span class="sxs-lookup"><span data-stu-id="27daf-221">Use the **Add** command to select the **MBAM Compliance Status Database Data.bak** file and click **OK** to complete the restoration process.</span></span>

4.  <span data-ttu-id="27daf-222">若要自动执行此过程，请创建包含以下 SQL 脚本的 SQL 文件（.sql）：</span><span class="sxs-lookup"><span data-stu-id="27daf-222">To automate this procedure, create a SQL file (.sql) that contains the following SQL script:</span></span>

    ```
    -- Create MBAM Compliance Status Database Data logical backup devices.

    Use master

    GO

    -- Restore the MBAM Compliance Status database data files.

    RESTORE DATABASE [MBAM Compliance Status]

    FROM DISK = 'C:\test\MBAM Compliance Status Database Data.bak'

    WITH REPLACE

    ```

5.  <span data-ttu-id="27daf-223">在 Windows PowerShell 中，运行存储在文件中的脚本，如下所示：</span><span class="sxs-lookup"><span data-stu-id="27daf-223">In Windows PowerShell, run the script that is stored in the file and similar to the following:</span></span>

    ```powershell
    Invoke-Sqlcmd -InputFile "Z:\RestoreMBAMComplianceStatusDatabaseScript.sql" -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$

    ```

6.  <span data-ttu-id="27daf-224">使用以下值，将代码示例中的值替换为与你的环境匹配的值。</span><span class="sxs-lookup"><span data-stu-id="27daf-224">Using the following value, replace the values in the code example with values that match your environment.</span></span>

    <span data-ttu-id="27daf-225">**$SERVERNAME $ \ $SQLINSTANCENAME $** -将还原合规性和审核数据库的服务器名称和实例。</span><span class="sxs-lookup"><span data-stu-id="27daf-225">**$SERVERNAME$\$SQLINSTANCENAME$** - Server name and instance to which the Compliance and Audit Database will be restored.</span></span>

### <span data-ttu-id="27daf-226">在服务器 B 上配置对数据库的访问并更新连接数据</span><span class="sxs-lookup"><span data-stu-id="27daf-226">Configure access to the Database on Server B and update connection data</span></span>

1. <span data-ttu-id="27daf-227">验证在已还原的数据库上启用合规性和审核数据库访问的 Microsoft SQL Server 用户登录是否映射到配置过程中提供的访问帐户。</span><span class="sxs-lookup"><span data-stu-id="27daf-227">Verify that the Microsoft SQL Server user login that enables Compliance and Audit Database access on the restored database is mapped to the access account that you provided during the configuration process.</span></span>

   >[!NOTE]
   ><span data-ttu-id="27daf-228">如果登录不同，请使用 SQL Server Management Studio 创建登录，并将其映射到现有数据库用户。</span><span class="sxs-lookup"><span data-stu-id="27daf-228">If the login is not the same, create a login by using SQL Server Management Studio, and map it to the existing database user.</span></span>

2. <span data-ttu-id="27daf-229">在运行管理和监视网站的服务器上，使用 Internet 信息服务（IIS）管理器控制台更新网站的连接字符串信息。</span><span class="sxs-lookup"><span data-stu-id="27daf-229">On the server that is running the Administration and Monitoring Website, use the Internet Information Services (IIS) Manager console to update the connection string information for the Website.</span></span>

3. <span data-ttu-id="27daf-230">编辑以下注册表项：</span><span class="sxs-lookup"><span data-stu-id="27daf-230">Edit the following registry key:</span></span>

   **<span data-ttu-id="27daf-231">HKLM\\Software\\Microsoft\\MBAM Server\\Web\\ComplianceDBConnectionString</span><span class="sxs-lookup"><span data-stu-id="27daf-231">HKLM\\Software\\Microsoft\\MBAM Server\\Web\\ComplianceDBConnectionString</span></span>**

4. <span data-ttu-id="27daf-232">将**数据源**值更新为将恢复数据库移动到的服务器和实例的名称（例如，\ $SERVERNAME \ $ \\ $SQLINSTANCENAME）。</span><span class="sxs-lookup"><span data-stu-id="27daf-232">Update the **Data Source** value with the name of the server and instance (for example, \$SERVERNAME\$\\\$SQLINSTANCENAME) to which the Recovery Database was moved.</span></span>

5. <span data-ttu-id="27daf-233">将**初始目录**值更新为已恢复的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="27daf-233">Update the **Initial Catalog** value with the recovered database name.</span></span>

6. <span data-ttu-id="27daf-234">若要自动执行此过程，你可以使用 Windows PowerShell 命令提示符在 "管理和监视服务器" 上输入类似于以下内容的命令行：</span><span class="sxs-lookup"><span data-stu-id="27daf-234">To automate this process, you can use the Windows PowerShell command prompt to enter a command line on the Administration and Monitoring Server that is similar to the following:</span></span>

   ```powershell
   reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MBAM Server\Web" /v
   ComplianceDBConnectionString /t REG_SZ /d "Integrated Security=SSPI;Initial
   Catalog=$DATABASE$;Data Source=$SERVERNAME$\$SQLINSTANCENAME$" /f
   ```
   >[!NOTE]
   ><span data-ttu-id="27daf-235">此连接字符串由所有本地 MBAM web 应用程序共享。</span><span class="sxs-lookup"><span data-stu-id="27daf-235">This connection string is shared by all local MBAM web applications.</span></span> <span data-ttu-id="27daf-236">因此，每台服务器只需更新一次。</span><span class="sxs-lookup"><span data-stu-id="27daf-236">Therefore, it needs to be updated only once per server.</span></span>


7. <span data-ttu-id="27daf-237">使用下表，将代码示例中的值替换为与你的环境匹配的值。</span><span class="sxs-lookup"><span data-stu-id="27daf-237">Using the following table, replace the values in the code example with values that match your environment.</span></span>

   |<span data-ttu-id="27daf-238">参数</span><span class="sxs-lookup"><span data-stu-id="27daf-238">Parameter</span></span> | <span data-ttu-id="27daf-239">描述</span><span class="sxs-lookup"><span data-stu-id="27daf-239">Description</span></span> |
   |---------|------------|
   |<span data-ttu-id="27daf-240">$SERVERNAME $ \ $SQLINSTANCENAME $</span><span class="sxs-lookup"><span data-stu-id="27daf-240">$SERVERNAME$\$SQLINSTANCENAME$</span></span> | <span data-ttu-id="27daf-241">恢复数据库所在的 SQL Server 的服务器名称和实例。</span><span class="sxs-lookup"><span data-stu-id="27daf-241">Server name and instance of SQL Server where the Recovery Database is located.</span></span>|
   |<span data-ttu-id="27daf-242">$DATABASE $</span><span class="sxs-lookup"><span data-stu-id="27daf-242">$DATABASE$</span></span>|<span data-ttu-id="27daf-243">已恢复的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="27daf-243">Name of the recovered database.</span></span>|

### <span data-ttu-id="27daf-244">安装 MBAM Server 软件并在服务器 B 上运行 MBAM 服务器配置向导</span><span class="sxs-lookup"><span data-stu-id="27daf-244">Install MBAM Server software and run the MBAM Server Configuration wizard on Server B</span></span>

1.  <span data-ttu-id="27daf-245">在服务器 B 上安装 MBAM 2.5 服务器软件。有关详细信息，请参阅[安装 MBAM 2.5 Server 软件](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/installing-the-mbam-25-server-software)。</span><span class="sxs-lookup"><span data-stu-id="27daf-245">Install the MBAM 2.5 Server software on Server B. For details, see [Installing the MBAM 2.5 Server Software](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/installing-the-mbam-25-server-software).</span></span>

2.  <span data-ttu-id="27daf-246">在服务器 B 上，启动 MBAM 服务器配置向导，单击 "**添加新功能**"，然后仅选择**合规性和审核数据库**功能。</span><span class="sxs-lookup"><span data-stu-id="27daf-246">On Server B, start the MBAM Server Configuration wizard, click **Add New Features**, and then select only the **Compliance and Audit Database** feature.</span></span> <span data-ttu-id="27daf-247">有关如何配置数据库的详细信息，请参阅[如何配置 MBAM 2.5 数据库](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-configure-the-mbam-25-databases)。</span><span class="sxs-lookup"><span data-stu-id="27daf-247">For details on how to configure the databases, see [How to Configure the MBAM 2.5 Databases](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-configure-the-mbam-25-databases).</span></span>

    >[!TIP]
    ><span data-ttu-id="27daf-248">或者，你可以使用**Enable-MbamDatabase** Windows PowerShell cmdlet 来配置合规性和审核数据库。</span><span class="sxs-lookup"><span data-stu-id="27daf-248">Alternatively, you can use the **Enable-MbamDatabase** Windows PowerShell cmdlet to configure the Compliance and Audit Database.</span></span>


### <span data-ttu-id="27daf-249">恢复管理和监视网站的实例</span><span class="sxs-lookup"><span data-stu-id="27daf-249">Resume the instance of the Administration and Monitoring Website</span></span>

<span data-ttu-id="27daf-250">在运行管理和监视网站的服务器上，使用 Internet Information Services （IIS）管理器控制台启动 "管理和监视" 网站。</span><span class="sxs-lookup"><span data-stu-id="27daf-250">On the server that is running the Administration and Monitoring Website, use the Internet Information Services (IIS) Manager console to start the Administration and Monitoring Website.</span></span>

<span data-ttu-id="27daf-251">若要自动执行此过程，你可以使用 Windows PowerShell 运行类似于以下内容的命令：</span><span class="sxs-lookup"><span data-stu-id="27daf-251">To automate this procedure, you can use Windows PowerShell to run a command that is similar to the following:</span></span>

```powershell
Start-Website "Microsoft BitLocker Administration and Monitoring"
```

>[!NOTE]
><span data-ttu-id="27daf-252">若要运行此命令，必须将适用于 Windows PowerShell 的 IIS 模块添加到 Windows PowerShell 的当前实例。</span><span class="sxs-lookup"><span data-stu-id="27daf-252">To run this command, you must add the IIS module for Windows PowerShell to the current instance of Windows PowerShell.</span></span>
