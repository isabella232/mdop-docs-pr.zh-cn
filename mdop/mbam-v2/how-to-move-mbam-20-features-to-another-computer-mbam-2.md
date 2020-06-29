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
# <span data-ttu-id="10972-103">如何将 MBAM 2.0 功能移到另一台计算机</span><span class="sxs-lookup"><span data-stu-id="10972-103">How to Move MBAM 2.0 Features to Another Computer</span></span>


<span data-ttu-id="10972-104">本主题介绍将一个或多个 Microsoft BitLocker 管理和监视（MBAM）功能移动到另一台计算机时应采取的步骤。</span><span class="sxs-lookup"><span data-stu-id="10972-104">This topic describes the steps that you should take to move one or more Microsoft BitLocker Administration and Monitoring (MBAM) features to a different computer.</span></span> <span data-ttu-id="10972-105">移动多个 Microsoft BitLocker 管理和监视功能时，应按照以下顺序移动它们：</span><span class="sxs-lookup"><span data-stu-id="10972-105">When moving more than one Microsoft BitLocker Administration and Monitoring feature, you should move them in the following order:</span></span>

1.  <span data-ttu-id="10972-106">恢复数据库</span><span class="sxs-lookup"><span data-stu-id="10972-106">Recovery Database</span></span>

2.  <span data-ttu-id="10972-107">合规性和审核数据库</span><span class="sxs-lookup"><span data-stu-id="10972-107">Compliance and Audit Database</span></span>

3.  <span data-ttu-id="10972-108">合规性和审核报告</span><span class="sxs-lookup"><span data-stu-id="10972-108">Compliance and Audit Reports</span></span>

4.  <span data-ttu-id="10972-109">管理和监视</span><span class="sxs-lookup"><span data-stu-id="10972-109">Administration and Monitoring</span></span>

## <span data-ttu-id="10972-110">移动恢复数据库</span><span class="sxs-lookup"><span data-stu-id="10972-110">Moving the Recovery Database</span></span>


<span data-ttu-id="10972-111">若要将恢复数据库从一台计算机移动到另一台计算机（例如从服务器 A 移动到服务器 B），请使用以下过程。</span><span class="sxs-lookup"><span data-stu-id="10972-111">To move the Recovery Database from one computer to another (for example, from Server A to Server B), use the following procedure.</span></span>

1.  <span data-ttu-id="10972-112">停止管理和监视网站的所有实例。</span><span class="sxs-lookup"><span data-stu-id="10972-112">Stop all instances of the Administration and Monitoring web site.</span></span>

2.  <span data-ttu-id="10972-113">在服务器 B 上运行 MBAM 安装程序。</span><span class="sxs-lookup"><span data-stu-id="10972-113">Run MBAM Setup on Server B.</span></span>

3.  <span data-ttu-id="10972-114">备份服务器 A 上的 MBAM 恢复数据库。</span><span class="sxs-lookup"><span data-stu-id="10972-114">Back up the MBAM Recovery Database on Server A.</span></span>

4.  <span data-ttu-id="10972-115">将 MBAM 恢复数据库从服务器 A 移动到 B。</span><span class="sxs-lookup"><span data-stu-id="10972-115">Move the MBAM Recovery Database from Server A to B.</span></span>

5.  <span data-ttu-id="10972-116">还原服务器 B 上的 MBAM 恢复数据库。</span><span class="sxs-lookup"><span data-stu-id="10972-116">Restore the MBAM Recovery Database on Server B.</span></span>

6.  <span data-ttu-id="10972-117">在服务器 B 上配置对 MBAM 恢复数据库的访问权限。</span><span class="sxs-lookup"><span data-stu-id="10972-117">Configure access to the MBAM Recovery Database on Server B.</span></span>

7.  <span data-ttu-id="10972-118">在 MBAM 管理和监视服务器上更新数据库连接数据。</span><span class="sxs-lookup"><span data-stu-id="10972-118">Update the database connection data on MBAM Administration and Monitoring servers.</span></span>

8.  <span data-ttu-id="10972-119">恢复 MBAM 管理和监视网站的所有实例。</span><span class="sxs-lookup"><span data-stu-id="10972-119">Resume all instances of the MBAM Administration and Monitoring website.</span></span>

**<span data-ttu-id="10972-120">停止 MBAM 管理和监视网站的所有实例</span><span class="sxs-lookup"><span data-stu-id="10972-120">Stop All Instances of the MBAM Administration and Monitoring Website</span></span>**

1.  <span data-ttu-id="10972-121">在运行 MBAM 管理和监视功能的每台服务器上，使用 Internet Information Services （IIS）管理器控制台停止名为**Microsoft BitLocker 管理和监视**的 MBAM 网站。</span><span class="sxs-lookup"><span data-stu-id="10972-121">On each of the servers running the MBAM Administration and Monitoring feature, use the Internet Information Services (IIS) Manager console to stop the MBAM website, which is named **Microsoft BitLocker Administration and Monitoring**.</span></span>

2.  <span data-ttu-id="10972-122">若要自动执行此过程，你可以使用 Windows PowerShell 输入类似于以下内容的命令行：</span><span class="sxs-lookup"><span data-stu-id="10972-122">To automate this procedure, you can use Windows PowerShell to enter command line that is similar to the:</span></span>

    `PS C:\> Stop-Website “Microsoft BitLocker Administration and Monitoring”`

    **<span data-ttu-id="10972-123">注意</span><span class="sxs-lookup"><span data-stu-id="10972-123">Note</span></span>**  
    <span data-ttu-id="10972-124">若要运行此 PowerShell 命令行，必须将用于 PowerShell 的 IIS 模块添加到当前的 PowerShell 实例。</span><span class="sxs-lookup"><span data-stu-id="10972-124">To run this PowerShell command line, the IIS Module for PowerShell must be added to current instance of PowerShell.</span></span> <span data-ttu-id="10972-125">此外，必须更新 PowerShell 执行策略以启用脚本执行。</span><span class="sxs-lookup"><span data-stu-id="10972-125">In addition, you must update the PowerShell execution policy to enable execution of scripts.</span></span>



**<span data-ttu-id="10972-126">在服务器 B 上运行 MBAM 设置</span><span class="sxs-lookup"><span data-stu-id="10972-126">Run MBAM Setup on Server B</span></span>**

1.  <span data-ttu-id="10972-127">在服务器 B 上运行 MBAM 设置，并仅选择要安装的**恢复数据库**。</span><span class="sxs-lookup"><span data-stu-id="10972-127">Run MBAM Setup on Server B and select only the **Recovery Database** for installation.</span></span>

2.  <span data-ttu-id="10972-128">若要自动执行此过程，你可以使用 Windows PowerShell 输入类似于以下内容的命令行：</span><span class="sxs-lookup"><span data-stu-id="10972-128">To automate this procedure, you can use Windows PowerShell to enter command line that is similar to the following:</span></span>

    `PS C:\> MbamSetup.exe /qn I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 AddLocal=KeyDatabase ADMINANDMON_MACHINENAMES=$DOMAIN$\$SERVERNAME$$ RECOVERYANDHWDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ TOPOLOGY=$X$`

    **<span data-ttu-id="10972-129">注意</span><span class="sxs-lookup"><span data-stu-id="10972-129">Note</span></span>**  
    <span data-ttu-id="10972-130">将上述示例中的以下值替换为与你的环境匹配的值：</span><span class="sxs-lookup"><span data-stu-id="10972-130">Replace the following values in the example above with those that match your environment:</span></span>

    -   <span data-ttu-id="10972-131">$SERVERNAME $ \\ $SQLINSTANCENAME $-输入要将恢复数据库移动到的服务器和实例的名称。</span><span class="sxs-lookup"><span data-stu-id="10972-131">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the name of the server and instance to which the Recovery Database will be moved.</span></span>

    -   <span data-ttu-id="10972-132">$DOMAIN $ \\ $SERVERNAME $-输入将与恢复数据库联系的每个 MBAM 管理和监视服务器的域名和服务器名称。</span><span class="sxs-lookup"><span data-stu-id="10972-132">$DOMAIN$\\$SERVERNAME$ - Enter the domain and server names of each MBAM Administration and Monitoring Server that will contact the Recovery Database.</span></span> <span data-ttu-id="10972-133">使用分号分隔列表中的每个域和服务器对（例如，$DOMAIN \\SERVERNAME $; $DOMAIN \ $SERVERNAME $ $）。</span><span class="sxs-lookup"><span data-stu-id="10972-133">Use a semi-colon to separate each domain and server pairs in the list (for example, $DOMAIN\\SERVERNAME$;$DOMAIN\\$SERVERNAME$$).</span></span> <span data-ttu-id="10972-134">每个服务器名称必须后跟一个 "$" 符号，如示例中所示（MyDomain\\MyServerName1 $;MyDomain\\MyServerName2 $）。</span><span class="sxs-lookup"><span data-stu-id="10972-134">Each server name must be followed by a “$” symbol, as shown in the example (MyDomain\\MyServerName1$; MyDomain\\MyServerName2$).</span></span>

    -   <span data-ttu-id="10972-135">如果你要安装 MBAM 独立拓扑，请 $X $-输入**0** ，如果你要安装 MBAM Configuration Manager 拓扑，则输入**1** 。</span><span class="sxs-lookup"><span data-stu-id="10972-135">$X$ - Enter **0** if you are installing the MBAM Stand-alone topology, or **1** if you are installing the MBAM Configuration Manager topology.</span></span>



**<span data-ttu-id="10972-136">备份服务器 A 上的恢复数据库</span><span class="sxs-lookup"><span data-stu-id="10972-136">Back Up the Recovery Database on Server A</span></span>**

1.  <span data-ttu-id="10972-137">若要备份服务器 A 上的恢复数据库，请使用 SQL Server Management Studio 和名为 "备份" 的任务。</span><span class="sxs-lookup"><span data-stu-id="10972-137">To back up the Recovery Database on Server A, use SQL Server Management Studio and the Task named Back Up.</span></span> <span data-ttu-id="10972-138">默认情况下，数据库名称是**MBAM 恢复数据库**。</span><span class="sxs-lookup"><span data-stu-id="10972-138">By default, the database name is **MBAM Recovery Database**.</span></span>

2.  <span data-ttu-id="10972-139">若要自动执行此过程，请创建包含以下 SQL 脚本的 SQL 文件（.sql）：</span><span class="sxs-lookup"><span data-stu-id="10972-139">To automate this procedure, create a SQL file (.sql) that contains the following SQL script:</span></span>

    <span data-ttu-id="10972-140">修改 MBAM 恢复数据库以使用完整恢复模式。</span><span class="sxs-lookup"><span data-stu-id="10972-140">Modify the MBAM Recovery Database to use the full recovery mode.</span></span>

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

    **<span data-ttu-id="10972-141">注意</span><span class="sxs-lookup"><span data-stu-id="10972-141">Note</span></span>**  
    <span data-ttu-id="10972-142">将上述示例中的以下值替换为与你的环境匹配的值：</span><span class="sxs-lookup"><span data-stu-id="10972-142">Replace the following values in the example above with those that match your environment:</span></span>

    -   <span data-ttu-id="10972-143">$PASSWORD $-输入将用于加密私钥文件的密码。</span><span class="sxs-lookup"><span data-stu-id="10972-143">$PASSWORD$ - Enter a password that you will use to encrypt the Private Key file.</span></span>



3.  <span data-ttu-id="10972-144">使用 SQL Server PowerShell 和类似于以下内容的命令行运行 SQL 文件：</span><span class="sxs-lookup"><span data-stu-id="10972-144">Run the SQL File by using SQL Server PowerShell and a command line that is similar to the following:</span></span>

    `PS C:\> Invoke-Sqlcmd -InputFile 'Z:\BackupMBAMRecoveryandHardwarDatabaseScript.sql' -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$`

    **<span data-ttu-id="10972-145">注意</span><span class="sxs-lookup"><span data-stu-id="10972-145">Note</span></span>**  
    <span data-ttu-id="10972-146">将上述示例中的以下值替换为与你的环境匹配的值：</span><span class="sxs-lookup"><span data-stu-id="10972-146">Replace the following values in the example above with those that match your environment:</span></span>

    -   <span data-ttu-id="10972-147">$SERVERNAME $ \\ $SQLINSTANCENAME $-输入服务器和实例的名称，将从该名称备份恢复数据库。</span><span class="sxs-lookup"><span data-stu-id="10972-147">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the name of the server and instance from which the Recovery Database will be backed up.</span></span>



**<span data-ttu-id="10972-148">将恢复数据库和证书从服务器 A 移动到服务器 B</span><span class="sxs-lookup"><span data-stu-id="10972-148">Move the Recovery Database and Certificate from Server A to Server B</span></span>**

1.  <span data-ttu-id="10972-149">使用 Windows 资源管理器将以下文件从服务器 A 移动到服务器 B。</span><span class="sxs-lookup"><span data-stu-id="10972-149">Move the following file from Server A to Server B by using Windows Explorer.</span></span>

    -   <span data-ttu-id="10972-150">MBAM 恢复数据库数据 .bak</span><span class="sxs-lookup"><span data-stu-id="10972-150">MBAM Recovery Database data.bak</span></span>

2.  <span data-ttu-id="10972-151">若要移动加密数据库的证书，请使用以下自动化步骤。</span><span class="sxs-lookup"><span data-stu-id="10972-151">To move the certificate for the encrypted database, use the following automation steps.</span></span> <span data-ttu-id="10972-152">若要自动执行此过程，你可以使用 Windows PowerShell 输入类似于以下内容的命令行：</span><span class="sxs-lookup"><span data-stu-id="10972-152">To automate this procedure, you can use Windows PowerShell to enter a command line that is similar to the following:</span></span>

    `PS C:\> Copy-Item “Z:\MBAM Recovery Database Data.bak” \\$SERVERNAME$\$DESTINATIONSHARE$`

    `PS C:\> Copy-Item “Z:\SQLServerInstanceCertificateFile” \\$SERVERNAME$\$DESTINATIONSHARE$`

    `PS C:\> Copy-Item “Z:\SQLServerInstanceCertificateFilePrivateKey” \\$SERVERNAME$\$DESTINATIONSHARE$`

    **<span data-ttu-id="10972-153">注意</span><span class="sxs-lookup"><span data-stu-id="10972-153">Note</span></span>**  
    <span data-ttu-id="10972-154">将上述示例中的以下值替换为与你的环境匹配的值：</span><span class="sxs-lookup"><span data-stu-id="10972-154">Replace the following value in the example above with those that match your environment:</span></span>

    -   <span data-ttu-id="10972-155">$SERVERNAME $-输入要将文件复制到的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="10972-155">$SERVERNAME$ - Enter the name of the server to which the files will be copied.</span></span>

    -   <span data-ttu-id="10972-156">$DESTINATIONSHARE $-输入要将文件复制到的共享和路径的名称。</span><span class="sxs-lookup"><span data-stu-id="10972-156">$DESTINATIONSHARE$ - Enter the name of the share and path to which the files will be copied.</span></span>



**<span data-ttu-id="10972-157">还原服务器 B 上的恢复数据库</span><span class="sxs-lookup"><span data-stu-id="10972-157">Restore the Recovery Database on Server B</span></span>**

1.  <span data-ttu-id="10972-158">使用 SQL Server Management Studio 和名为**Restore database**的任务还原服务器 B 上的恢复数据库。</span><span class="sxs-lookup"><span data-stu-id="10972-158">Restore the Recovery Database on Server B by using SQL Server Management Studio and the task named **Restore Database**.</span></span>

2.  <span data-ttu-id="10972-159">完成任务后，选择数据库备份文件，方法是选择 "**发件人设备**" 选项，然后使用 "**添加**" 命令选择 MBAM 恢复数据库**数据 .bak**文件。</span><span class="sxs-lookup"><span data-stu-id="10972-159">Once the task has been completed, select the database backup file by selecting the **From Device** option and then use the **Add** command to select the MBAM Recovery database **Data.bak** file.</span></span>

3.  <span data-ttu-id="10972-160">选择 **"确定"** 完成还原过程。</span><span class="sxs-lookup"><span data-stu-id="10972-160">Select **OK** to complete the restoration process.</span></span>

4.  <span data-ttu-id="10972-161">若要自动执行此过程，请创建包含以下 SQL 脚本的 SQL 文件（.sql）：</span><span class="sxs-lookup"><span data-stu-id="10972-161">To automate this procedure, create a SQL file (.sql) that contains the following-SQL script:</span></span>

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

    **<span data-ttu-id="10972-162">注意</span><span class="sxs-lookup"><span data-stu-id="10972-162">Note</span></span>**  
    <span data-ttu-id="10972-163">将上述示例中的以下值替换为与你的环境匹配的值：</span><span class="sxs-lookup"><span data-stu-id="10972-163">Replace the following values in the example above with those that match your environment:</span></span>

    -   <span data-ttu-id="10972-164">$PASSWORD $-输入用于加密私钥文件的密码。</span><span class="sxs-lookup"><span data-stu-id="10972-164">$PASSWORD$ - Enter a password that you used to encrypt the Private Key file.</span></span>



5.  <span data-ttu-id="10972-165">可以使用 Windows PowerShell 输入类似于以下内容的命令行：</span><span class="sxs-lookup"><span data-stu-id="10972-165">You can use Windows PowerShell to enter a command line that is similar to the following:</span></span>

    `PS C:\> Invoke-Sqlcmd -InputFile 'Z:\RestoreMBAMRecoveryandHardwarDatabaseScript.sql' -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$`

    **<span data-ttu-id="10972-166">注意</span><span class="sxs-lookup"><span data-stu-id="10972-166">Note</span></span>**  
    <span data-ttu-id="10972-167">将上述示例中的以下值替换为与你的环境匹配的值：</span><span class="sxs-lookup"><span data-stu-id="10972-167">Replace the following value in the example above with those that match your environment:</span></span>

    -   <span data-ttu-id="10972-168">$SERVERNAME $ \\ $SQLINSTANCENAME $-输入恢复数据库将还原到的服务器和实例的名称。</span><span class="sxs-lookup"><span data-stu-id="10972-168">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the name of the server and instance to which the Recovery Database will be restored.</span></span>



**<span data-ttu-id="10972-169">在服务器 B 上配置对恢复数据库的访问权限</span><span class="sxs-lookup"><span data-stu-id="10972-169">Configure Access to the Recovery Database on Server B</span></span>**

1.  <span data-ttu-id="10972-170">在服务器 B 上，使用服务器管理器中的 "本地用户和组" 管理单元将运行 MBAM 管理和监视功能的每台服务器中的计算机帐户添加到名为**MBAM 恢复和硬件数据库访问**的本地组。</span><span class="sxs-lookup"><span data-stu-id="10972-170">On Server B, use the Local user and Groups snap-in from Server Manager to add the computer accounts from each server that is running the MBAM Administration and Monitoring feature to the Local Group named **MBAM Recovery and Hardware DB Access**.</span></span>

2.  <span data-ttu-id="10972-171">验证还原的数据库上的 SQL 登录**MBAM 恢复和硬件数据库访问**是否映射到登录名 **$MachineName $ \\MBAM 恢复和硬件数据库访问**。</span><span class="sxs-lookup"><span data-stu-id="10972-171">Verify that the SQL login **MBAM Recovery and Hardware DB Access** on the restored database is mapped to the login name **$MachineName$\\MBAM Recovery and Hardware DB Access**.</span></span> <span data-ttu-id="10972-172">如果未按所述进行映射，请使用类似的组成员身份创建另一个登录，并将其映射到登录名 **$MachineName $ \\MBAM 恢复和硬件数据库访问**。</span><span class="sxs-lookup"><span data-stu-id="10972-172">If it is not mapped as described, create another login with similar group memberships, and map it to the login name **$MachineName$\\MBAM Recovery and Hardware DB Access**.</span></span>

3.  <span data-ttu-id="10972-173">若要自动执行此过程，可以在服务器 B 上使用 Windows PowerShell 输入类似于以下内容的命令行：</span><span class="sxs-lookup"><span data-stu-id="10972-173">To automate this procedure, you can use Windows PowerShell on Server B to enter a command line that is similar to the following:</span></span>

    `PS C:\> net localgroup "MBAM Recovery and Hardware DB Access" $DOMAIN$\$SERVERNAME$$  /add`

    **<span data-ttu-id="10972-174">注意</span><span class="sxs-lookup"><span data-stu-id="10972-174">Note</span></span>**  
    <span data-ttu-id="10972-175">将上述示例中的以下值替换为适用于你的环境的适用值：</span><span class="sxs-lookup"><span data-stu-id="10972-175">Replace the following values in the example above with the applicable values for your environment:</span></span>

    -   <span data-ttu-id="10972-176">$DOMAIN $ \ \ $SERVERNAME $ $-输入 MBAM 管理和监视服务器的域名和计算机名。</span><span class="sxs-lookup"><span data-stu-id="10972-176">$DOMAIN$\\$SERVERNAME$$ - Enter the domain and machine name of the MBAM Administration and Monitoring Server.</span></span> <span data-ttu-id="10972-177">服务器名称后面必须是 $，如示例中所示（例如，MyDomain\\MyServerName1 $）。</span><span class="sxs-lookup"><span data-stu-id="10972-177">The server name must be followed by a $, as shown in the example (for example, MyDomain\\MyServerName1$).</span></span>



~~~
This command line must be run for each Administration and Monitoring Server that will be accessing the database in your environment.
~~~

**<span data-ttu-id="10972-178">更新 MBAM 管理和监视服务器上的恢复数据库连接数据</span><span class="sxs-lookup"><span data-stu-id="10972-178">Update the Recovery Database Connection Data on the MBAM Administration and Monitoring Servers</span></span>**

1. <span data-ttu-id="10972-179">在运行 MBAM 管理和监视功能的每台服务器上，使用 Internet Information Services （IIS）管理器控制台更新以下应用程序的连接字符串信息，这些应用程序位于管理和监视网站中：</span><span class="sxs-lookup"><span data-stu-id="10972-179">On each of the servers running the MBAM Administration and Monitoring feature, use the Internet Information Services (IIS) Manager console to update the Connection String information for the following applications, which are hosted in the Administration and Monitoring website:</span></span>

   -   <span data-ttu-id="10972-180">MBAMAdministrationService</span><span class="sxs-lookup"><span data-stu-id="10972-180">MBAMAdministrationService</span></span>

   -   <span data-ttu-id="10972-181">MBAMRecoveryAndHardwareService</span><span class="sxs-lookup"><span data-stu-id="10972-181">MBAMRecoveryAndHardwareService</span></span>

2. <span data-ttu-id="10972-182">选择每个应用程序并使用 "**配置编辑器**" 功能，该功能位于 "功能"**视图**的 "**管理**" 部分下。</span><span class="sxs-lookup"><span data-stu-id="10972-182">Select each application and use the **Configuration Editor** feature, which is located under the **Management** section of the **Feature View**.</span></span>

3. <span data-ttu-id="10972-183">从 "**节列表**" 控件中选择 " **configurationStrings** " 选项。</span><span class="sxs-lookup"><span data-stu-id="10972-183">Select the **configurationStrings** option from the **Section list** control.</span></span>

4. <span data-ttu-id="10972-184">选择名为 **（集合）** 的行，然后通过选择行右侧的按钮打开**集合编辑器**。</span><span class="sxs-lookup"><span data-stu-id="10972-184">Select the row named **(Collection)** and open the **Collection Editor** by selecting the button on the right side of the row.</span></span>

5. <span data-ttu-id="10972-185">在**集合编辑器**中，在更新 MBAMAdministrationService 应用程序的配置或名为 Mbam 的行时，选择名为**KeyRecoveryConnectionString**的行 <strong> 。 </strong>当更新 MBAMRecoveryAndHardwareService 的配置时，ConnectionString。</span><span class="sxs-lookup"><span data-stu-id="10972-185">In the **Collection Editor**, select the row named **KeyRecoveryConnectionString** when updating the configuration for the MBAMAdministrationService application or the row named <strong>Microsoft.Mbam.RecoveryAndHardwareDataStore.</strong>ConnectionString when updating the configuration for the MBAMRecoveryAndHardwareService.</span></span>

6. <span data-ttu-id="10972-186">更新**configurationStrings**属性的**数据源 =** 值以列出服务器名称和实例（例如，$SERVERNAME $ \\ $SQLINSTANCENAME $），从中移动了恢复数据库。</span><span class="sxs-lookup"><span data-stu-id="10972-186">Update the **Data Source=** value for the **configurationStrings** property to list the server name and instance (for example, $SERVERNAME$\\$SQLINSTANCENAME$) where the Recovery Database was moved to.</span></span>

7. <span data-ttu-id="10972-187">若要自动执行此过程，可以在每个管理和监视服务器上使用 Windows 输入与以下内容类似的命令行：</span><span class="sxs-lookup"><span data-stu-id="10972-187">To automate this procedure, you can use Windows to enter a command line, that is similar to the following, on each Administration and Monitoring Server:</span></span>

   `PS C:\> Set-WebConfigurationProperty '/connectionStrings/add[@name="KeyRecoveryConnectionString"]' -PSPath "IIS:\sites\Microsoft Bitlocker Administration and Monitoring\MBAMAdministrationService" -Name "connectionString" -Value “Data Source=$SERVERNAME$\$SQLINSTANCENAME$;Initial Catalog=MBAM Recovery and Hardware;Integrated Security=SSPI;”`

   `PS C:\> Set-WebConfigurationProperty '/connectionStrings/add[@name="Microsoft.Mbam.RecoveryAndHardwareDataStore.ConnectionString"]' -PSPath "IIS:\sites\Microsoft Bitlocker Administration and Monitoring\MBAMRecoveryAndHardwareService" -Name "connectionString" -Value "Data Source=$SERVERNAME$\$SQLINSTANCENAME$;Initial Catalog=MBAM Recovery and Hardware;Integrated Security=SSPI;"`

   **<span data-ttu-id="10972-188">注意</span><span class="sxs-lookup"><span data-stu-id="10972-188">Note</span></span>**  
   <span data-ttu-id="10972-189">将上述示例中的以下值替换为与你的环境匹配的值：</span><span class="sxs-lookup"><span data-stu-id="10972-189">Replace the following value in the example above with those that match your environment:</span></span>

   -   <span data-ttu-id="10972-190">$SERVERNAME $ \\ $SQLINSTANCENAME $-输入恢复数据库所在的服务器名称和实例。</span><span class="sxs-lookup"><span data-stu-id="10972-190">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the server name and instance where the Recovery Database is.</span></span>



**<span data-ttu-id="10972-191">恢复 MBAM 管理和监视网站的所有实例</span><span class="sxs-lookup"><span data-stu-id="10972-191">Resume all Instances of the MBAM Administration and Monitoring Website</span></span>**

1.  <span data-ttu-id="10972-192">在运行 MBAM 管理和监视功能的每台服务器上，使用 Internet Information Services （IIS）管理器控制台启动名为**Microsoft BitLocker 管理和监视**的 MBAM 网站。</span><span class="sxs-lookup"><span data-stu-id="10972-192">On each server that is running the MBAM Administration and Monitoring feature, use the Internet Information Services (IIS) Manager console to start the MBAM website, which is named **Microsoft BitLocker Administration and Monitoring**.</span></span>

2.  <span data-ttu-id="10972-193">若要自动执行此过程，你可以使用 Windows PowerShell 输入类似于以下内容的命令行：</span><span class="sxs-lookup"><span data-stu-id="10972-193">To automate this procedure, you can use Windows PowerShell to enter a command line that is similar to the:</span></span>

    `PS C:\> Start-Website “Microsoft BitLocker Administration and Monitoring”`

## <span data-ttu-id="10972-194">移动合规性和审核数据库功能</span><span class="sxs-lookup"><span data-stu-id="10972-194">Moving the Compliance and Audit Database Feature</span></span>


<span data-ttu-id="10972-195">如果要将 MBAM 合规性和审核数据库从一台计算机移动到另一台计算机（即，将数据库从服务器 A 移动到服务器 B），请使用以下过程。</span><span class="sxs-lookup"><span data-stu-id="10972-195">If you want to move the MBAM Compliance and Audit Database from one computer to another (that is, move the database from Server A to Server B), use the following procedure.</span></span> <span data-ttu-id="10972-196">该过程包括以下高级别步骤：</span><span class="sxs-lookup"><span data-stu-id="10972-196">The process includes the following high-level steps:</span></span>

1.  <span data-ttu-id="10972-197">停止管理和监视网站的所有实例。</span><span class="sxs-lookup"><span data-stu-id="10972-197">Stop all instances of the Administration and Monitoring website.</span></span>

2.  <span data-ttu-id="10972-198">在服务器 B 上运行 MBAM 安装程序。</span><span class="sxs-lookup"><span data-stu-id="10972-198">Run MBAM setup on Server B.</span></span>

3.  <span data-ttu-id="10972-199">在服务器 A 上备份数据库。</span><span class="sxs-lookup"><span data-stu-id="10972-199">Back up the Database on Server A.</span></span>

4.  <span data-ttu-id="10972-200">将数据库从服务器 A 移动到 B。</span><span class="sxs-lookup"><span data-stu-id="10972-200">Move the Database from Server A to B.</span></span>

5.  <span data-ttu-id="10972-201">在服务器 B 上还原数据库。</span><span class="sxs-lookup"><span data-stu-id="10972-201">Restore the Database on Server B.</span></span>

6.  <span data-ttu-id="10972-202">在服务器 B 上配置对数据库的访问权限。</span><span class="sxs-lookup"><span data-stu-id="10972-202">Configure access to the Database on Server B.</span></span>

7.  <span data-ttu-id="10972-203">更新 MBAM 管理和监视服务器上的数据库连接数据。</span><span class="sxs-lookup"><span data-stu-id="10972-203">Update the database connection data on the MBAM Administration and Monitoring servers.</span></span>

8.  <span data-ttu-id="10972-204">通过合规性和审核数据库的新位置更新 SSRS 报表数据源连接字符串。</span><span class="sxs-lookup"><span data-stu-id="10972-204">Update the SSRS reports data source connection string with the new location of the Compliance and Audit Database.</span></span>

9.  <span data-ttu-id="10972-205">恢复管理和监视网站的所有实例。</span><span class="sxs-lookup"><span data-stu-id="10972-205">Resume all instances of the Administration and Monitoring website.</span></span>

**<span data-ttu-id="10972-206">停止管理和监视网站的所有实例</span><span class="sxs-lookup"><span data-stu-id="10972-206">Stop All Instances of the Administration and Monitoring Website</span></span>**

1.  <span data-ttu-id="10972-207">在运行 MBAM 管理和监视功能的每台服务器上，使用 Internet Information Services （IIS）管理器控制台停止名为**Microsoft BitLocker 管理和监视**的 MBAM 网站。</span><span class="sxs-lookup"><span data-stu-id="10972-207">On each server that is running the MBAM Administration and Monitoring feature, use the Internet Information Services (IIS) Manager console to stop the MBAM website named **Microsoft BitLocker Administration and Monitoring**.</span></span>

2.  <span data-ttu-id="10972-208">若要自动执行此过程，你可以使用 Windows PowerShell 输入类似于以下内容的命令行：</span><span class="sxs-lookup"><span data-stu-id="10972-208">To automate this procedure, you can use Windows PowerShell to enter a command line that is similar to the following:</span></span>

    `PS C:\> Stop-s “Microsoft BitLocker Administration and Monitoring”`

    **<span data-ttu-id="10972-209">注意</span><span class="sxs-lookup"><span data-stu-id="10972-209">Note</span></span>**  
    <span data-ttu-id="10972-210">若要运行此命令行，必须将用于 PowerShell 的 IIS 模块添加到 PowerShell 的当前实例。</span><span class="sxs-lookup"><span data-stu-id="10972-210">To run this command line, you must add the IIS Module for PowerShell to the current instance of PowerShell.</span></span> <span data-ttu-id="10972-211">此外，你必须更新 PowerShell 执行策略以允许运行脚本。</span><span class="sxs-lookup"><span data-stu-id="10972-211">In addition, you must update the PowerShell execution policy to enable scripts to be run.</span></span>



**<span data-ttu-id="10972-212">在服务器 B 上运行 MBAM 设置</span><span class="sxs-lookup"><span data-stu-id="10972-212">Run MBAM Setup on Server B</span></span>**

1.  <span data-ttu-id="10972-213">在服务器 B 上运行 MBAM 设置，并仅选择**合规性和审核数据库**进行安装。</span><span class="sxs-lookup"><span data-stu-id="10972-213">Run MBAM Setup on Server B and select only the **Compliance and Audit Database** for installation.</span></span>

2.  <span data-ttu-id="10972-214">若要自动执行此过程，你可以使用 Windows PowerShell 输入类似于以下内容的命令行：</span><span class="sxs-lookup"><span data-stu-id="10972-214">To automate this procedure, you can use Windows PowerShell to enter a command line that is similar to the following:</span></span>

    `PS C:\> MbamSetup.exe /qn I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 AddLocal= ReportsDatabase ADMINANDMON_MACHINENAMES=$DOMAIN$\$SERVERNAME$ COMPLIDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ REPORTS_USERACCOUNT=$DOMAIN$\$USERNAME$ TOPOLOGY=$X$`

    **<span data-ttu-id="10972-215">注意</span><span class="sxs-lookup"><span data-stu-id="10972-215">Note</span></span>**  
    <span data-ttu-id="10972-216">注意：将上述示例中的以下值替换为与你的环境匹配的值：</span><span class="sxs-lookup"><span data-stu-id="10972-216">Note: Replace the following values in the example above with those that match your environment:</span></span>

    -   <span data-ttu-id="10972-217">$SERVERNAME $ \\ $SQLINSTANCENAME $-输入要将合规性和审核数据库移动到的服务器名称和实例。</span><span class="sxs-lookup"><span data-stu-id="10972-217">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the server name and instance where the Compliance and Audit Database will be moved to.</span></span>

    -   <span data-ttu-id="10972-218">$DOMAIN $ \\ $SERVERNAME $-输入将与合规性和审核数据库联系的每个 MBAM 管理和监视服务器的域名和服务器名称。</span><span class="sxs-lookup"><span data-stu-id="10972-218">$DOMAIN$\\$SERVERNAME$ - Enter the domain and server names of each MBAM Administration and Monitoring Server that will contact the Compliance and Audit Database.</span></span> <span data-ttu-id="10972-219">使用分号分隔列表中的每个域和服务器对（例如，$DOMAIN \\SERVERNAME $; $DOMAIN \ $SERVERNAME $ $）。</span><span class="sxs-lookup"><span data-stu-id="10972-219">Use a semi-colon to separate each domain and server pair in the list (for example, $DOMAIN\\SERVERNAME$;$DOMAIN\\$SERVERNAME$$).</span></span> <span data-ttu-id="10972-220">每个服务器名称必须后跟一个 "$" 符号，如示例中所示（MyDomain\\MyServerName1 $;MyDomain\\MyServerName2 $）。</span><span class="sxs-lookup"><span data-stu-id="10972-220">Each server name must be followed by a “$” symbol, as shown in the example (MyDomain\\MyServerName1$; MyDomain\\MyServerName2$).</span></span>

    -   <span data-ttu-id="10972-221">$DOMAIN $ \\ $USERNAME $-输入合规性和审核报告功能将用于连接到合规性和审核数据库的域名和用户名。</span><span class="sxs-lookup"><span data-stu-id="10972-221">$DOMAIN$\\$USERNAME$ - Enter the domain and user name that will be used by the Compliance and Audit Reports feature to connect to the Compliance and Audit Database.</span></span>

    -   <span data-ttu-id="10972-222">如果你要安装 MBAM 独立拓扑，请 $X $-输入**0** ，如果你要安装 MBAM Configuration Manager 拓扑，则输入**1** 。</span><span class="sxs-lookup"><span data-stu-id="10972-222">$X$ - Enter **0** if you are installing the MBAM Stand-alone topology, or **1** if you are installing the MBAM Configuration Manager topology.</span></span>



**<span data-ttu-id="10972-223">在服务器 A 上备份合规性和审核数据库</span><span class="sxs-lookup"><span data-stu-id="10972-223">Back Up the Compliance and Audit Database on Server A</span></span>**

1.  <span data-ttu-id="10972-224">若要备份服务器 A 上的合规性和审核数据库，请使用 SQL Server Management Studio 和名为 "**备份**" 的任务。</span><span class="sxs-lookup"><span data-stu-id="10972-224">To back up the Compliance and Audit Database on Server A, use SQL Server Management Studio and the task named **Back Up**.</span></span> <span data-ttu-id="10972-225">默认情况下，数据库名称是**MBAM 合规性状态数据库**。</span><span class="sxs-lookup"><span data-stu-id="10972-225">By default, the database name is **MBAM Compliance Status Database**.</span></span>

2.  <span data-ttu-id="10972-226">若要自动执行此过程，请创建包含以下 SQL 脚本的 SQL 文件（.sql）：</span><span class="sxs-lookup"><span data-stu-id="10972-226">To automate this procedure, create a SQL file (.sql) that contains the following-SQL script:</span></span>

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

3.  <span data-ttu-id="10972-227">使用 Windows PowerShell 命令行运行 SQL 文件，如下所示：</span><span class="sxs-lookup"><span data-stu-id="10972-227">Run the SQL file by using a Windows PowerShell command line that is similar to the following:</span></span>

    `PS C:\> Invoke-Sqlcmd -InputFile "Z:\BackupMBAMComplianceStatusDatabaseScript.sql" –ServerInstance $SERVERNAME$\$SQLINSTANCENAME$`

    **<span data-ttu-id="10972-228">注意</span><span class="sxs-lookup"><span data-stu-id="10972-228">Note</span></span>**  
    <span data-ttu-id="10972-229">将上述示例中的以下值替换为与你的环境匹配的值：</span><span class="sxs-lookup"><span data-stu-id="10972-229">Replace the following value in the example above with those that match your environment:</span></span>

    -   <span data-ttu-id="10972-230">$SERVERNAME $ \\ $SQLINSTANCENAME $-输入将从中备份合规性和审核数据库的服务器名称和实例。</span><span class="sxs-lookup"><span data-stu-id="10972-230">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the server name and instance where the Compliance and Audit database will be backed up from.</span></span>



**<span data-ttu-id="10972-231">将合规性和审核数据库从服务器 A 移动到 B</span><span class="sxs-lookup"><span data-stu-id="10972-231">Move the Compliance and Audit Database from Server A to B</span></span>**

1.  <span data-ttu-id="10972-232">使用 Windows 资源管理器将以下文件从服务器 A 移动到服务器 B。</span><span class="sxs-lookup"><span data-stu-id="10972-232">Move the following files from Server A to Server B using Windows Explorer.</span></span>

    -   <span data-ttu-id="10972-233">MBAM 合规性状态数据库数据 .bak</span><span class="sxs-lookup"><span data-stu-id="10972-233">MBAM Compliance Status Database Data.bak</span></span>

2.  <span data-ttu-id="10972-234">若要自动执行此过程，你可以使用 Windows PowerShell 输入类似于以下内容的命令行：</span><span class="sxs-lookup"><span data-stu-id="10972-234">To automate this procedure, you can use Windows PowerShell to enter a command line that is similar to the following:</span></span>

    `PS C:\> Copy-Item “Z:\MBAM Compliance Status Database Data.bak” \\$SERVERNAME$\$DESTINATIONSHARE$`

    **<span data-ttu-id="10972-235">注意</span><span class="sxs-lookup"><span data-stu-id="10972-235">Note</span></span>**  
    <span data-ttu-id="10972-236">将上述示例中的以下值替换为与你的环境匹配的值：</span><span class="sxs-lookup"><span data-stu-id="10972-236">Replace the following values in the example above with those that match your environment:</span></span>

    -   <span data-ttu-id="10972-237">$SERVERNAME $-输入要将文件复制到的服务器名称。</span><span class="sxs-lookup"><span data-stu-id="10972-237">$SERVERNAME$ - Enter the server name where the files will be copied to.</span></span>

    -   <span data-ttu-id="10972-238">$DESTINATIONSHARE $-输入要将文件复制到的共享和路径的名称。</span><span class="sxs-lookup"><span data-stu-id="10972-238">$DESTINATIONSHARE$ - Enter the name of share and path where the files will be copied to.</span></span>



**<span data-ttu-id="10972-239">在服务器 B 上还原合规性和审核数据库</span><span class="sxs-lookup"><span data-stu-id="10972-239">Restore the Compliance and Audit Database on Server B</span></span>**

1.  <span data-ttu-id="10972-240">使用 SQL Server Management Studio 和名为**Restore database**的任务在服务器 B 上还原合规性和审核数据库。</span><span class="sxs-lookup"><span data-stu-id="10972-240">Restore the Compliance and Audit Database on Server B by using SQL Server Management Studio and the task named **Restore Database**.</span></span>

2.  <span data-ttu-id="10972-241">完成任务后，选择数据库备份文件，方法是选择 "**发件人设备**" 选项，然后使用 "**添加**" 命令选择 MBAM 合规性状态数据库数据 .bak 文件。</span><span class="sxs-lookup"><span data-stu-id="10972-241">Once the task has been completed, select the database backup file by selecting the **From Device** option and then use the **Add** command to select the MBAM Compliance Status Database Data.bak file.</span></span> <span data-ttu-id="10972-242">选择 **"确定"** 完成还原过程。</span><span class="sxs-lookup"><span data-stu-id="10972-242">Select **OK** to complete the restoration process.</span></span>

3.  <span data-ttu-id="10972-243">若要自动执行此过程，请创建包含以下 SQL 脚本的 SQL 文件（.sql）：</span><span class="sxs-lookup"><span data-stu-id="10972-243">To automate this procedure, create a SQL file (.sql) that contains the following-SQL script:</span></span>

    ```sql
    -- Create MBAM Compliance Status Database Data logical backup devices. 

    Use master

    GO

    -- Restore the MBAM Compliance Status database data files.

    RESTORE DATABASE [MBAM Compliance Status]

       FROM DISK = 'C:\test\MBAM Compliance Status Database Data.bak'

       WITH REPLACE
    ```

4.  <span data-ttu-id="10972-244">使用 Windows PowerShell 命令行运行 SQL 文件，如下所示：</span><span class="sxs-lookup"><span data-stu-id="10972-244">Run the SQL File by using a Windows PowerShell command line that is similar to the following:</span></span>

    `PS C:\> Invoke-Sqlcmd -InputFile "Z:\RestoreMBAMComplianceStatusDatabaseScript.sql" -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$`

    **<span data-ttu-id="10972-245">注意</span><span class="sxs-lookup"><span data-stu-id="10972-245">Note</span></span>**  
    <span data-ttu-id="10972-246">将上述示例中的以下值替换为与你的环境匹配的值：</span><span class="sxs-lookup"><span data-stu-id="10972-246">Replace the following value in the example above with those that match your environment:</span></span>

    -   <span data-ttu-id="10972-247">$SERVERNAME $ \\ $SQLINSTANCENAME $-输入要将合规性和审核数据库还原到的服务器名称和实例。</span><span class="sxs-lookup"><span data-stu-id="10972-247">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the server name and instance where the Compliance and Audit Database will be restored to.</span></span>



**<span data-ttu-id="10972-248">在服务器 B 上配置合规性和审核数据库的访问权限</span><span class="sxs-lookup"><span data-stu-id="10972-248">Configure Access to the Compliance and Audit Database on Server B</span></span>**

1.  <span data-ttu-id="10972-249">在服务器 B 上，使用服务器管理器中的 "本地用户和组" 管理单元将运行 MBAM 管理和监视功能的每台服务器中的计算机帐户添加到名为**MBAM 合规性状态数据库访问**的本地组。</span><span class="sxs-lookup"><span data-stu-id="10972-249">On Server B, use the Local user and Groups snap-in from Server Manager to add the computer accounts from each server that is running the MBAM Administration and Monitoring feature to the local group named **MBAM Compliance Status DB Access**.</span></span>

2.  <span data-ttu-id="10972-250">验证已还原数据库上的 SQL 登录**MBAM 合规性审核数据库访问**是否映射到登录名 **$MACHINENAME $ \\ MBAM 合规性审核数据库访问**。</span><span class="sxs-lookup"><span data-stu-id="10972-250">Verify that the SQL login **MBAM Compliance Auditing DB Access** on the restored database is mapped to the login name **$MachineName$\\ MBAM Compliance Auditing DB Access**.</span></span> <span data-ttu-id="10972-251">如果未按所述进行映射，请使用类似的组成员身份创建另一个登录，并将其映射到登录名 **$MachineName $ \\ MBAM 合规性审核数据库访问**。</span><span class="sxs-lookup"><span data-stu-id="10972-251">If it is not mapped as described, create another login with similar group memberships, and map it to the login name **$MachineName$\\ MBAM Compliance Auditing DB Access**.</span></span>

3.  <span data-ttu-id="10972-252">若要自动执行此过程，你可以使用 Windows PowerShell 在服务器 B 上输入类似于以下内容的命令行：</span><span class="sxs-lookup"><span data-stu-id="10972-252">To automate this procedure, you can use Windows PowerShell to enter a command line on Server B that is similar to the following:</span></span>

    `PS C:\> net localgroup "MBAM Compliance Auditing DB Access" $DOMAIN$\$SERVERNAME$$  /add`

    `PS C:\> net localgroup "MBAM Compliance Auditing DB Access" $DOMAIN$\$REPORTSUSERNAME$  /add`

    **<span data-ttu-id="10972-253">注意</span><span class="sxs-lookup"><span data-stu-id="10972-253">Note</span></span>**  
    <span data-ttu-id="10972-254">将上述示例中的以下值替换为适用于你的环境的适用值：</span><span class="sxs-lookup"><span data-stu-id="10972-254">Replace the following values in the example above with the applicable values for your environment:</span></span>

    -   <span data-ttu-id="10972-255">$DOMAIN $ \ \ $SERVERNAME $ $-输入 MBAM 管理和监视服务器的域名和计算机名。</span><span class="sxs-lookup"><span data-stu-id="10972-255">$DOMAIN$\\$SERVERNAME$$ - Enter the domain and machine name of the MBAM Administration and Monitoring Server.</span></span> <span data-ttu-id="10972-256">服务器名称必须后跟 "$"，如示例中所示。</span><span class="sxs-lookup"><span data-stu-id="10972-256">The server name must be followed by a “$” as shown in the example.</span></span> <span data-ttu-id="10972-257">（例如，MyDomain\\MyServerName1 $）</span><span class="sxs-lookup"><span data-stu-id="10972-257">(for example, MyDomain\\MyServerName1$)</span></span>

    -   <span data-ttu-id="10972-258">$DOMAIN $ \\ $REPORTSUSERNAME $-输入用于配置合规性和审核报告的数据源的用户帐户名称。</span><span class="sxs-lookup"><span data-stu-id="10972-258">$DOMAIN$\\$REPORTSUSERNAME$ - Enter the user account name that was used to configure the data source for the Compliance and Audit Reports.</span></span>



~~~
The command line for adding the servers to the MBAM Compliance and Audit Database access local group must be run for each Administration and Monitoring Server that will be accessing the database in your environment.
~~~

**<span data-ttu-id="10972-259">在 MBAM 管理和监视服务器上更新数据库连接数据</span><span class="sxs-lookup"><span data-stu-id="10972-259">Update the Database Connection Data on MBAM Administration and Monitoring Servers</span></span>**

1.  <span data-ttu-id="10972-260">在运行 MBAM 管理和监视功能的每台服务器上，使用 Internet Information Services （IIS）管理器控制台更新以下应用程序的连接字符串信息，这些应用程序位于管理和监视网站中：</span><span class="sxs-lookup"><span data-stu-id="10972-260">On each server that is running the MBAM Administration and Monitoring feature, use the Internet Information Services (IIS) Manager console to update the connection string information for the following applications, which are hosted in the Administration and Monitoring website:</span></span>

    -   <span data-ttu-id="10972-261">MBAMAdministrationService</span><span class="sxs-lookup"><span data-stu-id="10972-261">MBAMAdministrationService</span></span>

    -   <span data-ttu-id="10972-262">MBAMComplianceStatusService</span><span class="sxs-lookup"><span data-stu-id="10972-262">MBAMComplianceStatusService</span></span>

2.  <span data-ttu-id="10972-263">选择每个应用程序并使用 "**配置编辑器**" 功能，该功能位于 "功能"**视图**的 "**管理**" 部分下。</span><span class="sxs-lookup"><span data-stu-id="10972-263">Select each application and use the **Configuration Editor** feature, which is located under the **Management** section of the **Feature View**.</span></span>

3.  <span data-ttu-id="10972-264">从 "**节列表**" 控件中选择 " **configurationStrings** " 选项。</span><span class="sxs-lookup"><span data-stu-id="10972-264">Select the **configurationStrings** option from the **Section list** control.</span></span>

4.  <span data-ttu-id="10972-265">选择名为 **（集合）** 的行，然后通过选择行右侧的按钮打开**集合编辑器**。</span><span class="sxs-lookup"><span data-stu-id="10972-265">Select the row named **(Collection)**, and open the **Collection Editor** by selecting the button on the right side of the row.</span></span>

5.  <span data-ttu-id="10972-266">在**集合编辑器**中，在更新 MBAMComplianceStatusService 的配置时，选择名为 " **ComplianceStatusConnectionString** " 的行作为 MBAMAdministrationService 应用程序的配置或名为**BitLockerManagement. StatusReportDataStore**的行。</span><span class="sxs-lookup"><span data-stu-id="10972-266">In the **Collection Editor**, select the row named **ComplianceStatusConnectionString** when updating the configuration for the MBAMAdministrationService application, or the row named **Microsoft.Windows.Mdop.BitLockerManagement.StatusReportDataStore.ConnectionString** when updating the configuration for the MBAMComplianceStatusService.</span></span>

6.  <span data-ttu-id="10972-267">更新**configurationStrings**属性的**数据源 =** value，以列出要将恢复数据库移动到的服务器和实例的名称（例如 $SERVERNAME $ \\ $SQLINSTANCENAME）。</span><span class="sxs-lookup"><span data-stu-id="10972-267">Update the **Data Source=** value for the **configurationStrings** property to list the name of the server and instance (for example, $SERVERNAME$\\$SQLINSTANCENAME) to which the Recovery Database was moved.</span></span>

7.  <span data-ttu-id="10972-268">若要自动执行此过程，你可以使用 Windows 在与以下内容类似的每个管理和监视服务器上输入命令行：</span><span class="sxs-lookup"><span data-stu-id="10972-268">To automate this procedure, you can use Windows to enter a command line on each Administration and Monitoring Server that is similar to the following:</span></span>

    `PS C:\> Set-WebConfigurationProperty '/connectionStrings/add[@name="ComplianceStatusConnectionString"]' -PSPath "IIS:\sites\Microsoft Bitlocker Administration and Monitoring\MBAMAdministrationService" -Name "connectionString" -Value "Data Source=$SERVERNAME$\$SQLINSTANCENAME$;Initial Catalog=MBAM Compliance Status;Integrated Security=SSPI;"`

    `PS C:\> Set-WebConfigurationProperty '/connectionStrings/add[@name="Microsoft.Windows.Mdop.BitLockerManagement.StatusReportDataStore.ConnectionString"]' -PSPath "IIS:\sites\Microsoft Bitlocker Administration and Monitoring\MBAMComplianceStatusService" -Name "connectionString" -Value "Data Source=$SERVERNAME$\$SQLINSTANCENAME;Initial Catalog=MBAM Compliance Status;Integrated Security=SSPI;"`

    **<span data-ttu-id="10972-269">注意</span><span class="sxs-lookup"><span data-stu-id="10972-269">Note</span></span>**  
    <span data-ttu-id="10972-270">将上述示例中的以下值替换为与你的环境匹配的值：</span><span class="sxs-lookup"><span data-stu-id="10972-270">Replace the following values in the example above with those that match your environment:</span></span>

    -   <span data-ttu-id="10972-271">$SERVERNAME $ \\ $SQLINSTANCENAME $-输入恢复数据库所在的服务器名称和实例。</span><span class="sxs-lookup"><span data-stu-id="10972-271">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the server name and instance where the Recovery Database is located.</span></span>



**<span data-ttu-id="10972-272">恢复 MBAM 管理和监视网站的所有实例</span><span class="sxs-lookup"><span data-stu-id="10972-272">Resume All Instances of the MBAM Administration and Monitoring Website</span></span>**

1.  <span data-ttu-id="10972-273">在运行 MBAM 管理和监视功能的每台服务器上，使用 Internet Information Services （IIS）管理器控制台启动名为**Microsoft BitLocker 管理和监视**的 MBAM 网站。</span><span class="sxs-lookup"><span data-stu-id="10972-273">On each server that is running the MBAM Administration and Monitoring feature, use the Internet Information Services (IIS) Manager console to start the MBAM website named **Microsoft BitLocker Administration and Monitoring**.</span></span>

2.  <span data-ttu-id="10972-274">若要自动执行此过程，你可以使用 Windows PowerShell 输入类似于以下内容的命令行：</span><span class="sxs-lookup"><span data-stu-id="10972-274">To automate this procedure, you can use Windows PowerShell to enter a command line that is similar to the following:</span></span>

    `PS C:\> Start-Website “Microsoft BitLocker Administration and Monitoring”`

## <span data-ttu-id="10972-275">移动合规性和审核报告</span><span class="sxs-lookup"><span data-stu-id="10972-275">Moving the Compliance and Audit Reports</span></span>


<span data-ttu-id="10972-276">如果要将 MBAM 合规性和审核报告从一台计算机移动到另一台计算机（即，将报表从服务器 A 移动到服务器 B），请使用以下过程，其中包括以下高级步骤：</span><span class="sxs-lookup"><span data-stu-id="10972-276">If you want to move the MBAM Compliance and Audit Reports from one computer to another (that is, move the reports from Server A to Server B), use the following procedure, which includes the following high-level steps:</span></span>

1.  <span data-ttu-id="10972-277">在服务器 B 上运行 MBAM 安装程序。</span><span class="sxs-lookup"><span data-stu-id="10972-277">Run MBAM setup on Server B.</span></span>

2.  <span data-ttu-id="10972-278">配置对服务器 B 上的合规性和审核报告的访问权限。</span><span class="sxs-lookup"><span data-stu-id="10972-278">Configure access to the Compliance and Audit Reports on Server B.</span></span>

3.  <span data-ttu-id="10972-279">停止 MBAM 管理和监视网站的所有实例。</span><span class="sxs-lookup"><span data-stu-id="10972-279">Stop all instances of the MBAM Administration and Monitoring website.</span></span>

4.  <span data-ttu-id="10972-280">在 MBAM 管理和监视服务器上更新报表连接数据。</span><span class="sxs-lookup"><span data-stu-id="10972-280">Update the reports connection data on MBAM Administration and Monitoring servers.</span></span>

5.  <span data-ttu-id="10972-281">恢复 MBAM 管理和监视网站的所有实例。</span><span class="sxs-lookup"><span data-stu-id="10972-281">Resume all instances of the MBAM Administration and Monitoring website.</span></span>

**<span data-ttu-id="10972-282">在服务器 B 上运行 MBAM 设置</span><span class="sxs-lookup"><span data-stu-id="10972-282">Run MBAM Setup on Server B</span></span>**

1.  <span data-ttu-id="10972-283">在服务器 B 上运行 MBAM 设置，仅选择 "**合规性" 和 "审核报告**" 功能进行安装。</span><span class="sxs-lookup"><span data-stu-id="10972-283">Run MBAM Setup on Server B and select only the **Compliance and Audit Reports** feature for installation.</span></span>

2.  <span data-ttu-id="10972-284">若要自动执行此过程，你可以使用 Windows PowerShell 输入类似于以下内容的命令行：</span><span class="sxs-lookup"><span data-stu-id="10972-284">To automate this procedure, you can use Windows PowerShell to enter a command line that is similar to the following:</span></span>

    `PS C:\> MbamSetup.exe /qn I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 AddLocal=Reports COMPLIDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ REPORTS_USERACCOUNTPW=$PASSWORD$ TOPOLOGY=$X$`

    **<span data-ttu-id="10972-285">注意</span><span class="sxs-lookup"><span data-stu-id="10972-285">Note</span></span>**  
    <span data-ttu-id="10972-286">将上述示例中的以下值替换为与你的环境匹配的值：</span><span class="sxs-lookup"><span data-stu-id="10972-286">Replace the following values in the example above with those that match your environment:</span></span>

    -   <span data-ttu-id="10972-287">$SERVERNAME $ \\ $SQLINSTANCENAME $-输入合规性和审核数据库所在的服务器名称和实例。</span><span class="sxs-lookup"><span data-stu-id="10972-287">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the server name and instance where the Compliance and Audit Database is located.</span></span>

    -   <span data-ttu-id="10972-288">$DOMAIN $ \\ $USERNAME $-输入合规性和审核报告功能将用于连接到合规性和审核数据库的域名和用户名。</span><span class="sxs-lookup"><span data-stu-id="10972-288">$DOMAIN$\\$USERNAME$ - Enter the domain and user name that will be used by the Compliance and Audit Reports feature to connect to the Compliance and Audit Database.</span></span>

    -   <span data-ttu-id="10972-289">$PASSWORD $-输入将用于连接合规性和审核数据库的用户帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="10972-289">$PASSWORD$ - Enter the password of the user account that will be used to connect to the Compliance and Audit Database.</span></span>

    -   <span data-ttu-id="10972-290">如果你要安装 MBAM 独立拓扑，请 $X $-输入**0** ，如果你要安装 MBAM Configuration Manager 拓扑，则输入**1** 。</span><span class="sxs-lookup"><span data-stu-id="10972-290">$X$ - Enter **0** if you are installing the MBAM Stand-alone topology, or **1** if you are installing the MBAM Configuration Manager topology.</span></span>



**<span data-ttu-id="10972-291">配置对服务器 B 上的合规性和审核报告的访问权限</span><span class="sxs-lookup"><span data-stu-id="10972-291">Configure Access to the Compliance and Audit Reports on Server B</span></span>**

1.  <span data-ttu-id="10972-292">在服务器 B 上，使用服务器管理器中的 "本地用户和组" 管理单元添加将有权访问合规性和审核报告的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="10972-292">On Server B, use the Local user and Groups snap-in from Server Manager to add the user accounts that will have access to the Compliance and Audit Reports.</span></span> <span data-ttu-id="10972-293">将用户帐户添加到名为 MBAM 报告用户的本地组。</span><span class="sxs-lookup"><span data-stu-id="10972-293">Add the user accounts to the local group named MBAM Report Users.</span></span>

2.  <span data-ttu-id="10972-294">若要自动执行此过程，你可以使用 Windows PowerShell 在服务器 B 上输入类似于以下内容的命令行：</span><span class="sxs-lookup"><span data-stu-id="10972-294">To automate this procedure, you can use Windows PowerShell to enter a command line on Server B that is similar to the following:</span></span>

    `PS C:\> net localgroup "MBAM Report Users" $DOMAIN$\$REPORTSUSERNAME$  /add`

    **<span data-ttu-id="10972-295">注意</span><span class="sxs-lookup"><span data-stu-id="10972-295">Note</span></span>**  
    <span data-ttu-id="10972-296">将上述示例中的以下值替换为适用于你的环境的适用值：</span><span class="sxs-lookup"><span data-stu-id="10972-296">Replace the following values in the example above with the applicable values for your environment:</span></span>

    -   <span data-ttu-id="10972-297">$DOMAIN $ \\ $REPORTSUSERNAME $-输入用于配置合规性和审核报告的数据源的用户帐户名称。</span><span class="sxs-lookup"><span data-stu-id="10972-297">$DOMAIN$\\$REPORTSUSERNAME$ - Enter the user account name that was used to configure the data source for the Compliance and Audit reports.</span></span>



~~~
The command line for adding the users to the MBAM Report Users local group must be run for each user that will be accessing the reports in your environment.
~~~

**<span data-ttu-id="10972-298">停止 MBAM 管理和监视网站的所有实例</span><span class="sxs-lookup"><span data-stu-id="10972-298">Stop All Instances of the MBAM Administration and Monitoring Website</span></span>**

1.  <span data-ttu-id="10972-299">在运行 MBAM 管理和监视服务器功能的每台服务器上，使用 Internet Information Services （IIS）管理器控制台停止名为**Microsoft BitLocker 管理和监视**的 MBAM 网站。</span><span class="sxs-lookup"><span data-stu-id="10972-299">On each server that is running the MBAM Administration and Monitoring Server feature, use the Internet Information Services (IIS) Manager console to stop the MBAM website named **Microsoft BitLocker Administration and Monitoring**.</span></span>

2.  <span data-ttu-id="10972-300">若要自动执行此过程，你可以使用 Windows PowerShell 输入类似于以下内容的命令行：</span><span class="sxs-lookup"><span data-stu-id="10972-300">To automate this procedure, you can use Windows PowerShell to enter a command line that is similar to the following:</span></span>

    `PS C:\> Stop-Website “Microsoft BitLocker Administration and Monitoring”`

**<span data-ttu-id="10972-301">更新 MBAM 管理和监视服务器上的数据库连接数据</span><span class="sxs-lookup"><span data-stu-id="10972-301">Update the Database Connection Data on the MBAM Administration and Monitoring Servers</span></span>**

1. <span data-ttu-id="10972-302">在运行 MBAM 管理和监视服务器功能的每台服务器上，使用 Internet 信息服务（IIS）管理器控制台更新合规性和审核报告 URL。</span><span class="sxs-lookup"><span data-stu-id="10972-302">On each server that is running the MBAM Administration and Monitoring Server feature, use the Internet Information Services (IIS) Manager console to update the Compliance and Audit Reports URL.</span></span>

2. <span data-ttu-id="10972-303">选择 " **Microsoft BitLocker 管理和监视**" 网站，并使用 "配置编辑器" 功能，该功能位于 "功能"**视图**的 "**管理**" 部分下的 "**配置编辑器**" 功能。</span><span class="sxs-lookup"><span data-stu-id="10972-303">Select the **Microsoft BitLocker Administration and Monitoring** website, and use the **Configuration Editor** feature that is location under the **Management** section of the **Feature View**.</span></span>

3. <span data-ttu-id="10972-304">从 "**节列表**" 控件中选择 " **appSettings** " 选项。</span><span class="sxs-lookup"><span data-stu-id="10972-304">Select the **appSettings** option from the **Section list** control.</span></span>

4. <span data-ttu-id="10972-305">选择名为 **（集合）** 的行，然后通过选择行右侧的按钮打开**集合编辑器**。</span><span class="sxs-lookup"><span data-stu-id="10972-305">Select the row named **(Collection)** and open the **Collection Editor** by selecting the button on the right side of the row.</span></span>

5. <span data-ttu-id="10972-306">在**集合编辑器**中，选择名为 " **Mbam**" 的行。</span><span class="sxs-lookup"><span data-stu-id="10972-306">In the **Collection Editor**, select the row named **Microsoft.Mbam.Reports.Url**.</span></span>

6. <span data-ttu-id="10972-307">更新**Mbam**的值以反映服务器 B 的服务器名称。如果已在命名的 SQL Reporting Services 实例上安装了合规性和审核报告功能，请确保在 URL 中添加或更新实例的名称（例如，http://$SERVERNAME $/ReportServer\_ $ SQLSRSINSTANCENAME $/Pages....）</span><span class="sxs-lookup"><span data-stu-id="10972-307">Update the value for **Microsoft.Mbam.Reports.Url** to reflect the server name for Server B. If the Compliance and Audit Reports feature was installed on a named SQL Reporting Services instance, be sure to add or update the name of the instance to the URL (for example, http://$SERVERNAME$/ReportServer\_$SQLSRSINSTANCENAME$/Pages....)</span></span>

7. <span data-ttu-id="10972-308">若要自动执行此过程，你可以使用 Windows PowerShell 在与以下内容类似的每个管理和监视服务器上输入命令行：</span><span class="sxs-lookup"><span data-stu-id="10972-308">To automate this procedure, you can use Windows PowerShell to enter a command line on each Administration and Monitoring Server that is similar to the following:</span></span>

   `PS C:\> Set-WebConfigurationProperty '/appSettings/add[@key="Microsoft.Mbam.Reports.Url"]' -PSPath "IIS:\ \sites\Microsoft Bitlocker Administration and Monitoring\HelpDesk" -Name "Value" -Value “http://$SERVERNAME$/ReportServer_$SRSINSTANCENAME$/Pages/ReportViewer.aspx?/ Microsoft+BitLocker+Administration+and+Monitoring/”`

   **<span data-ttu-id="10972-309">注意</span><span class="sxs-lookup"><span data-stu-id="10972-309">Note</span></span>**  
   <span data-ttu-id="10972-310">将上述示例中的以下值替换为与你的环境匹配的值：</span><span class="sxs-lookup"><span data-stu-id="10972-310">Replace the following values in the example above with those that match your environment:</span></span>

   -   <span data-ttu-id="10972-311">$SERVERNAME $-输入要安装合规性和审核报告的服务器名称的名称。</span><span class="sxs-lookup"><span data-stu-id="10972-311">$SERVERNAME$ - Enter the name of the server name to which the Compliance and Audit Reports were installed.</span></span>

   -   <span data-ttu-id="10972-312">$SRSINSTANCENAME $-输入已安装合规性和审核报告的 SQL Reporting Services 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="10972-312">$SRSINSTANCENAME$ - Enter the name of the SQL Reporting Services instance to which the Compliance and Audit Reports were installed.</span></span>



**<span data-ttu-id="10972-313">恢复 MBAM 管理和监视网站的所有实例</span><span class="sxs-lookup"><span data-stu-id="10972-313">Resume All Instances of the MBAM Administration and Monitoring Website</span></span>**

1.  <span data-ttu-id="10972-314">在运行 MBAM 管理和监视服务器功能的每台服务器上，使用 Internet Information Services （IIS）管理器控制台启动名为**Microsoft BitLocker 管理和监视**的 MBAM 网站。</span><span class="sxs-lookup"><span data-stu-id="10972-314">On each server that is running the MBAM Administration and Monitoring Server feature, use the Internet Information Services (IIS) Manager console to Start the MBAM website named **Microsoft BitLocker Administration and Monitoring**.</span></span>

2.  <span data-ttu-id="10972-315">若要自动执行此过程，你可以使用 Windows PowerShell 输入类似于以下内容的命令行：</span><span class="sxs-lookup"><span data-stu-id="10972-315">To automate this procedure, you can use Windows PowerShell to enter a command line that is similar to the following:</span></span>

    `PS C:\> Start-Website “Microsoft BitLocker Administration and Monitoring”`

    **<span data-ttu-id="10972-316">注意</span><span class="sxs-lookup"><span data-stu-id="10972-316">Note</span></span>**  
    <span data-ttu-id="10972-317">若要运行此命令行，必须将用于 PowerShell 的 IIS 模块添加到当前的 PowerShell 实例。</span><span class="sxs-lookup"><span data-stu-id="10972-317">To run this command line, you must add the IIS Module for PowerShell to current instance of PowerShell.</span></span> <span data-ttu-id="10972-318">此外，你必须更新 PowerShell 执行策略以允许运行脚本。</span><span class="sxs-lookup"><span data-stu-id="10972-318">In addition, you must update the PowerShell execution policy to enable scripts to be run.</span></span>



## <span data-ttu-id="10972-319">移动 "管理和监视" 功能</span><span class="sxs-lookup"><span data-stu-id="10972-319">Moving the Administration and Monitoring Feature</span></span>


<span data-ttu-id="10972-320">如果要将 MBAM 管理和监视报告功能从一台计算机移动到另一台计算机（即，将该功能从服务器 A 移动到服务器 B），请使用以下过程，其中包括以下高级步骤：</span><span class="sxs-lookup"><span data-stu-id="10972-320">If you want to move the MBAM Administration and Monitoring Reports feature from one computer to another (that is, move the feature from Server A to Server B), use the following procedure, which includes the following high-level steps:</span></span>

1.  <span data-ttu-id="10972-321">在服务器 B 上运行 MBAM 安装程序。</span><span class="sxs-lookup"><span data-stu-id="10972-321">Run MBAM Setup on Server B.</span></span>

2.  <span data-ttu-id="10972-322">在服务器 B 上配置对数据库的访问权限。</span><span class="sxs-lookup"><span data-stu-id="10972-322">Configure access to the Database on Server B.</span></span>

**<span data-ttu-id="10972-323">在服务器 B 上运行 MBAM 设置</span><span class="sxs-lookup"><span data-stu-id="10972-323">Run MBAM Setup on Server B</span></span>**

1.  <span data-ttu-id="10972-324">在服务器 B 上运行 MBAM 设置，并仅选择 "**管理和监视服务器**" 功能进行安装。</span><span class="sxs-lookup"><span data-stu-id="10972-324">Run MBAM Setup on Server B and select only the **Administration and Monitoring Server** feature for installation.</span></span>

2.  <span data-ttu-id="10972-325">若要自动执行此过程，你可以使用 Windows PowerShell 输入类似于以下内容的命令行：</span><span class="sxs-lookup"><span data-stu-id="10972-325">To automate this procedure, you can use Windows PowerShell to enter a command line that is similar to the following:</span></span>

    `PS C:\> MbamSetup.exe /qn I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 AddLocal=AdministrationMonitoringServer, COMPLIDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ RECOVERYANDHWDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ SRS_REPORTSITEURL=$REPORTSSERVERURL$ TOPOLOGY=$X$`

    **<span data-ttu-id="10972-326">注意</span><span class="sxs-lookup"><span data-stu-id="10972-326">Note</span></span>**  
    <span data-ttu-id="10972-327">将上述示例中的以下值替换为与你的环境匹配的值：</span><span class="sxs-lookup"><span data-stu-id="10972-327">Replace the following values in the example above with those that match your environment:</span></span>

    -   <span data-ttu-id="10972-328">$SERVERNAME $ \\ $SQLINSTANCENAME $-对于 COMPLIDB \ _SQLINSTANCE 参数，输入合规性和审核数据库所在的服务器名称和实例。</span><span class="sxs-lookup"><span data-stu-id="10972-328">$SERVERNAME$\\$SQLINSTANCENAME$ - For the COMPLIDB\_SQLINSTANCE parameter, enter the server name and instance where the Compliance and Audit Database is located.</span></span> <span data-ttu-id="10972-329">对于 RECOVERYANDHWDB \ _SQLINSTANCE 参数，输入恢复数据库所在的服务器名称和实例。</span><span class="sxs-lookup"><span data-stu-id="10972-329">For the RECOVERYANDHWDB\_SQLINSTANCE parameter, enter the server name and instance where the Recovery Database is located.</span></span>

    -   <span data-ttu-id="10972-330">$DOMAIN $ \\ $USERNAME $-输入合规性和审核报告功能将用于连接到合规性和审核数据库的域名和用户名。</span><span class="sxs-lookup"><span data-stu-id="10972-330">$DOMAIN$\\$USERNAME$ - Enter the domain and user name that will be used by the Compliance and Audit Reports feature to connect to the Compliance and Audit Database.</span></span>

    -   <span data-ttu-id="10972-331">$ REPORTSSERVERURL $-输入 SQL Reporting Services 网站的主位置的 URL。</span><span class="sxs-lookup"><span data-stu-id="10972-331">$ REPORTSSERVERURL$ - Enter the URL for the Home location of the SQL Reporting Service website.</span></span> <span data-ttu-id="10972-332">如果报表已安装到默认 SRS 实例，则 URL 格式将采用 "http://$SERVERNAME $/ReportServer" 格式。</span><span class="sxs-lookup"><span data-stu-id="10972-332">If the reports were installed to a default SRS instance, the URL format will have the format “http:// $SERVERNAME$/ReportServer”.</span></span> <span data-ttu-id="10972-333">如果报表已安装到默认 SRS 实例，则 URL 格式将采用 "http://$SERVERNAME $/ReportServer\_ $ SQLINSTANCENAME $" 格式。</span><span class="sxs-lookup"><span data-stu-id="10972-333">If the reports were installed to a default SRS instance, the URL format will have the format “http://$SERVERNAME$/ReportServer\_$SQLINSTANCENAME$”.</span></span>

    -   <span data-ttu-id="10972-334">如果你要安装 MBAM 独立拓扑，请 $X $-输入**0** ，如果你要安装 MBAM Configuration Manager 拓扑，则输入**1** 。</span><span class="sxs-lookup"><span data-stu-id="10972-334">$X$ - Enter **0** if you are installing the MBAM Stand-alone topology, or **1** if you are installing the MBAM Configuration Manager topology.</span></span>



**<span data-ttu-id="10972-335">配置对数据库的访问权限</span><span class="sxs-lookup"><span data-stu-id="10972-335">Configure Access to the Databases</span></span>**

1.  <span data-ttu-id="10972-336">在要部署恢复数据库和合规性和审核数据库的服务器或服务器上，使用服务器管理器中的本地用户和组管理单元将运行 MBAM 管理和监视服务器功能的每台服务器中的计算机帐户添加到名为**MBAM 恢复和硬件数据库访问**（恢复 DB 服务器）和**MBAM 合规性状态数据库访问**（合规性和审核数据库服务器）的每台服务器</span><span class="sxs-lookup"><span data-stu-id="10972-336">On the server or servers where the Recovery Database and Compliance and Audit Database are deployed, use the Local user and Groups snap-in from Server Manager to add the computer accounts from each server that is running the MBAM Administration and Monitoring Server feature to the local groups named **MBAM Recovery and Hardware DB Access** (Recovery DB Server) and **MBAM Compliance Status DB Access** (Compliance and Audit Database Server).</span></span>

2.  <span data-ttu-id="10972-337">若要自动执行此过程，你可以使用 Windows PowerShell 在部署合规性和审核数据库的服务器上输入类似于以下内容的命令行。</span><span class="sxs-lookup"><span data-stu-id="10972-337">To automate this procedure, you can use Windows PowerShell to enter a command line, that is similar to the following, on the server where the Compliance and Audit Database was deployed.</span></span>

    `PS C:\> net localgroup "MBAM Compliance Auditing DB Access" $DOMAIN$\$SERVERNAME$$  /add`

3.  <span data-ttu-id="10972-338">在部署恢复数据库的服务器上，可以使用 Windows PowerShell 输入类似于以下内容的命令行：</span><span class="sxs-lookup"><span data-stu-id="10972-338">On the server where the Recovery database was deployed, you can use Windows PowerShell to enter a command line that is similar to the following:</span></span>

    `PS C:\> net localgroup "MBAM Recovery and Hardware DB Access" $DOMAIN$\$SERVERNAME$$  /add`

    **<span data-ttu-id="10972-339">注意</span><span class="sxs-lookup"><span data-stu-id="10972-339">Note</span></span>**  
    <span data-ttu-id="10972-340">将上述示例中的以下值替换为适用于你的环境的适用值：</span><span class="sxs-lookup"><span data-stu-id="10972-340">Replace the following value in the example above with the applicable values for your environment:</span></span>

    -   <span data-ttu-id="10972-341">$DOMAIN $ \ \ $SERVERNAME $ $-输入管理和监视服务器的域名和计算机名称。</span><span class="sxs-lookup"><span data-stu-id="10972-341">$DOMAIN$\\$SERVERNAME$$ - Enter the domain and machine name of the Administration and Monitoring Server.</span></span> <span data-ttu-id="10972-342">服务器名称必须后跟 "$" 符号，如示例中所示（例如，MyDomain\\MyServerName1 $）。</span><span class="sxs-lookup"><span data-stu-id="10972-342">The server name must be followed by a “$” symbol, as shown in the example (for example, MyDomain\\MyServerName1$).</span></span>

    -   <span data-ttu-id="10972-343">$DOMAIN $ \\ $REPORTSUSERNAME $-输入用于配置合规性和审核报告的数据源的用户帐户名称。</span><span class="sxs-lookup"><span data-stu-id="10972-343">$DOMAIN$\\$REPORTSUSERNAME$ - Enter the user account name that was used to configure the data source for the Compliance and Audit Reports.</span></span>



~~~
The command lines that are listed for adding server computer accounts to the MBAM local groups must be run for each Administration and Monitoring Server that will be accessing the databases in your environment.
~~~

## <span data-ttu-id="10972-344">相关主题</span><span class="sxs-lookup"><span data-stu-id="10972-344">Related topics</span></span>


[<span data-ttu-id="10972-345">维护 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="10972-345">Maintaining MBAM 2.0</span></span>](maintaining-mbam-20-mbam-2.md)









