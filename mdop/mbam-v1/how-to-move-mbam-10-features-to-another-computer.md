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
# <span data-ttu-id="e95c2-103">如何将 MBAM 1.0 功能移到另一台计算机</span><span class="sxs-lookup"><span data-stu-id="e95c2-103">How to Move MBAM 1.0 Features to Another Computer</span></span>


<span data-ttu-id="e95c2-104">本主题介绍将一个或多个 Microsoft BitLocker 管理和监视（MBAM）功能移动到另一台计算机时应采取的步骤。</span><span class="sxs-lookup"><span data-stu-id="e95c2-104">This topic describes the steps that you should take to move one or more Microsoft BitLocker Administration and Monitoring (MBAM) features to a different computer.</span></span> <span data-ttu-id="e95c2-105">将多个 MBAM 功能移动到另一台计算机时，应按照以下顺序移动它们：</span><span class="sxs-lookup"><span data-stu-id="e95c2-105">When you move more than one MBAM feature to another computer, you should move them in the following order:</span></span>

1.  <span data-ttu-id="e95c2-106">恢复和硬件数据库</span><span class="sxs-lookup"><span data-stu-id="e95c2-106">Recovery and Hardware Database</span></span>

2.  <span data-ttu-id="e95c2-107">合规性和审核数据库</span><span class="sxs-lookup"><span data-stu-id="e95c2-107">Compliance and Audit Database</span></span>

3.  <span data-ttu-id="e95c2-108">合规性和审核报告</span><span class="sxs-lookup"><span data-stu-id="e95c2-108">Compliance and Audit Reports</span></span>

4.  <span data-ttu-id="e95c2-109">管理和监视</span><span class="sxs-lookup"><span data-stu-id="e95c2-109">Administration and Monitoring</span></span>

## <span data-ttu-id="e95c2-110">移动恢复和硬件数据库</span><span class="sxs-lookup"><span data-stu-id="e95c2-110">To move the Recovery and Hardware Database</span></span>


<span data-ttu-id="e95c2-111">可以使用以下过程将 MBAM 恢复和硬件数据库从一台计算机移动到另一台计算机（可将此 MBAM 服务器的功能从服务器 A 移动到服务器 B）：</span><span class="sxs-lookup"><span data-stu-id="e95c2-111">You can use the following procedure to move the MBAM Recovery and Hardware Database from one computer to another (you can move this MBAM Server feature from Server A to Server B):</span></span>

****

1.  <span data-ttu-id="e95c2-112">停止 MBAM 管理和监视网站的所有实例。</span><span class="sxs-lookup"><span data-stu-id="e95c2-112">Stop all instances of the MBAM Administration and Monitoring web site.</span></span>

2.  <span data-ttu-id="e95c2-113">在服务器 B 上运行 MBAM 设置。</span><span class="sxs-lookup"><span data-stu-id="e95c2-113">Run the MBAM Setup on Server B.</span></span>

3.  <span data-ttu-id="e95c2-114">在服务器 A 上备份 MBAM 恢复和硬件数据库。</span><span class="sxs-lookup"><span data-stu-id="e95c2-114">Back up the MBAM Recovery and Hardware database on Server A.</span></span>

4.  <span data-ttu-id="e95c2-115">从服务器 A 到 B MBAM 恢复和硬件数据库</span><span class="sxs-lookup"><span data-stu-id="e95c2-115">MBAM Recovery and Hardware database from Server A to B</span></span>

5.  <span data-ttu-id="e95c2-116">在服务器 B 上还原 MBAM 恢复和硬件数据库</span><span class="sxs-lookup"><span data-stu-id="e95c2-116">Restore the MBAM Recovery and Hardware database on Server B</span></span>

6.  <span data-ttu-id="e95c2-117">在服务器 B 上配置对 MBAM 恢复和硬件数据库的访问</span><span class="sxs-lookup"><span data-stu-id="e95c2-117">Configure the access to the MBAM Recovery and Hardware database on Server B</span></span>

7.  <span data-ttu-id="e95c2-118">在 MBAM 管理和监视服务器上更新数据库连接数据</span><span class="sxs-lookup"><span data-stu-id="e95c2-118">Update the database connection data on MBAM Administration and Monitoring servers</span></span>

8.  <span data-ttu-id="e95c2-119">恢复 MBAM 管理和监视网站的所有实例</span><span class="sxs-lookup"><span data-stu-id="e95c2-119">Resume all instances of the MBAM Administration and Monitoring web site</span></span>

**<span data-ttu-id="e95c2-120">停止 MBAM 管理和监视网站的所有实例</span><span class="sxs-lookup"><span data-stu-id="e95c2-120">To stop all instances of the MBAM Administration and Monitoring website</span></span>**

1.  <span data-ttu-id="e95c2-121">使用 Internet Information Services （IIS）管理器控制台在运行 MBAM 管理和监视功能的每个服务器上停止 MBAM 网站。</span><span class="sxs-lookup"><span data-stu-id="e95c2-121">Use the Internet Information Services (IIS) Manager console to stop the MBAM website on each of the servers that run the MBAM Administration and Monitoring feature.</span></span> <span data-ttu-id="e95c2-122">MBAM 网站命名为 " **Microsoft BitLocker 管理和监视**"。</span><span class="sxs-lookup"><span data-stu-id="e95c2-122">The MBAM website is named **Microsoft BitLocker Administration and Monitoring**.</span></span>

2.  <span data-ttu-id="e95c2-123">若要自动执行此过程，你可以使用 Windows PowerShell 在命令提示符下使用类似于以下内容的命令：</span><span class="sxs-lookup"><span data-stu-id="e95c2-123">To automate this procedure, you can use a command at the command prompt that is similar to the following, by using Windows PowerShell:</span></span>

    `PS C:\> Stop-Website “Microsoft BitLocker Administration and Monitoring”`

    **<span data-ttu-id="e95c2-124">注意</span><span class="sxs-lookup"><span data-stu-id="e95c2-124">Note</span></span>**  
    <span data-ttu-id="e95c2-125">若要运行此 PowerShell 命令提示符，必须将用于 PowerShell 的 IIS 模块添加到 PowerShell 的当前实例。</span><span class="sxs-lookup"><span data-stu-id="e95c2-125">To run this PowerShell command prompt, you must add the IIS Module for PowerShell to the current instance of PowerShell.</span></span> <span data-ttu-id="e95c2-126">此外，必须更新 PowerShell 执行策略以启用脚本的执行。</span><span class="sxs-lookup"><span data-stu-id="e95c2-126">In addition, you must update the PowerShell execution policy to enable the execution of scripts.</span></span>



**<span data-ttu-id="e95c2-127">在服务器 B 上运行 MBAM 设置</span><span class="sxs-lookup"><span data-stu-id="e95c2-127">To run MBAM setup on Server B</span></span>**

1.  <span data-ttu-id="e95c2-128">在服务器 B 上运行 MBAM 设置，然后选择要安装的恢复和硬件数据库。</span><span class="sxs-lookup"><span data-stu-id="e95c2-128">Run the MBAM setup on Server B and select the Recovery and Hardware Database for installation.</span></span>

2.  <span data-ttu-id="e95c2-129">若要自动执行此过程，你可以使用 Windows PowerShell 在命令提示符下使用类似于以下内容的命令：</span><span class="sxs-lookup"><span data-stu-id="e95c2-129">To automate this procedure, you can use a command at the command prompt that is similar to the following, by using Windows PowerShell:</span></span>

    `PS C:\> MbamSetup.exe /qn I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 AddLocal=KeyDatabase ADMINANDMON_MACHINENAMES=$DOMAIN$\$SERVERNAME$$ RECOVERYANDHWDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$`

    **<span data-ttu-id="e95c2-130">注意</span><span class="sxs-lookup"><span data-stu-id="e95c2-130">Note</span></span>**  
    <span data-ttu-id="e95c2-131">将上述示例中的以下值替换为与你的环境匹配的值：</span><span class="sxs-lookup"><span data-stu-id="e95c2-131">Replace the following values in the example above with those that match your environment:</span></span>

    -   <span data-ttu-id="e95c2-132">$SERVERNAME $ \\ $SQLINSTANCENAME $-输入要将恢复和硬件数据库移动到的服务器和实例的名称。</span><span class="sxs-lookup"><span data-stu-id="e95c2-132">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the name of the server and instance to which the Recovery and Hardware database will be moved.</span></span>

    -   <span data-ttu-id="e95c2-133">$DOMAIN $ \\ $SERVERNAME $-输入将联系恢复和硬件数据库的每个 MBAM 应用程序和监视服务器的域名和服务器名称。</span><span class="sxs-lookup"><span data-stu-id="e95c2-133">$DOMAIN$\\$SERVERNAME$ - Enter the domain and server names of each MBAM Application and Monitoring Server that will contact the Recovery and Hardware database.</span></span> <span data-ttu-id="e95c2-134">如果存在多个域名和服务器名称，请使用分号分隔列表中的每个名称。</span><span class="sxs-lookup"><span data-stu-id="e95c2-134">If there are multiple domain and server names, use a semicolon to separate each one of them in the list.</span></span> <span data-ttu-id="e95c2-135">例如，$DOMAIN \\SERVERNAME $; $DOMAIN \ $SERVERNAME $ $。</span><span class="sxs-lookup"><span data-stu-id="e95c2-135">For example, $DOMAIN\\SERVERNAME$;$DOMAIN\\$SERVERNAME$$.</span></span> <span data-ttu-id="e95c2-136">此外，每个服务器名称必须后跟 a **$** 。</span><span class="sxs-lookup"><span data-stu-id="e95c2-136">Additionally, each server name must be followed by a **$**.</span></span> <span data-ttu-id="e95c2-137">例如，MyDomain\\MyServerName1 $，MyDomain\\MyServerName2 $。</span><span class="sxs-lookup"><span data-stu-id="e95c2-137">For example, MyDomain\\MyServerName1$, MyDomain\\MyServerName2$.</span></span>



**<span data-ttu-id="e95c2-138">备份服务器 A 上的数据库</span><span class="sxs-lookup"><span data-stu-id="e95c2-138">To back up the Database on Server A</span></span>**

1.  <span data-ttu-id="e95c2-139">若要备份服务器 A 上的恢复和硬件数据库，请使用 SQL Server Management Studio 和名为 "**备份 ...**" 的任务。</span><span class="sxs-lookup"><span data-stu-id="e95c2-139">To back up the Recovery and Hardware database on Server A, use SQL Server Management Studio and the Task named **Back Up…**.</span></span> <span data-ttu-id="e95c2-140">默认情况下，数据库名称是**MBAM 恢复和硬件数据库**。</span><span class="sxs-lookup"><span data-stu-id="e95c2-140">By default, the database name is **MBAM Recovery and Hardware Database**.</span></span>

2.  <span data-ttu-id="e95c2-141">若要自动执行此过程，请创建包含以下 SQL 脚本的 SQL 文件（.sql）：</span><span class="sxs-lookup"><span data-stu-id="e95c2-141">To automate this procedure, create a SQL file (.sql) that contains the following SQL script:</span></span>

    <span data-ttu-id="e95c2-142">修改 MBAM 恢复和硬件数据库以使用完整恢复模式。</span><span class="sxs-lookup"><span data-stu-id="e95c2-142">Modify the MBAM Recovery and Hardware Database to use the full recovery mode.</span></span>

    ```sql
    USE master;

    GO

    ALTER DATABASE "MBAM Recovery and Hardware"

       SET RECOVERY FULL;

    GO
    ```

    <span data-ttu-id="e95c2-143">创建 MBAM 恢复和硬件数据库数据以及 MBAM 恢复逻辑备份设备。</span><span class="sxs-lookup"><span data-stu-id="e95c2-143">Create MBAM Recovery and Hardware Database Data and MBAM Recovery logical backup devices.</span></span>

    ```sql
    USE master

    GO

    EXEC sp_addumpdevice 'disk', 'MBAM Recovery and Hardware Database Data Device',

    'Z:\MBAM Recovery and Hardware Database Data.bak';

    GO
    ```

    <span data-ttu-id="e95c2-144">备份完整的 MBAM 恢复和硬件数据库。</span><span class="sxs-lookup"><span data-stu-id="e95c2-144">Back up the full MBAM Recovery and Hardware database.</span></span>

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

    **<span data-ttu-id="e95c2-145">注意</span><span class="sxs-lookup"><span data-stu-id="e95c2-145">Note</span></span>**  
    <span data-ttu-id="e95c2-146">将前面示例中的值替换为与你的环境匹配的值：</span><span class="sxs-lookup"><span data-stu-id="e95c2-146">Replace the values from the preceding example with those that match your environment:</span></span>

    -   <span data-ttu-id="e95c2-147">$PASSWORD $-输入将用于加密私钥文件的密码。</span><span class="sxs-lookup"><span data-stu-id="e95c2-147">$PASSWORD$ - Enter a password that you will use to encrypt the Private Key file.</span></span>



3.  <span data-ttu-id="e95c2-148">使用 SQL Server PowerShell 和类似于以下内容的命令执行 SQL 文件：</span><span class="sxs-lookup"><span data-stu-id="e95c2-148">Execute the SQL file by using SQL Server PowerShell and a command that is similar to the following:</span></span>

    `PS C:\> Invoke-Sqlcmd -InputFile 'Z:\BackupMBAMRecoveryandHardwarDatabaseScript.sql' -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$`

    **<span data-ttu-id="e95c2-149">注意</span><span class="sxs-lookup"><span data-stu-id="e95c2-149">Note</span></span>**  
    <span data-ttu-id="e95c2-150">将上一示例中的值替换为与你的环境匹配的值：</span><span class="sxs-lookup"><span data-stu-id="e95c2-150">Replace the value in the previous example with those that match your environment:</span></span>

    -   <span data-ttu-id="e95c2-151">$SERVERNAME $ \\ $SQLINSTANCENAME $-输入服务器的名称以及备份恢复和硬件数据库的实例。</span><span class="sxs-lookup"><span data-stu-id="e95c2-151">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the name of the server and the instance from which you back up the Recovery and Hardware database.</span></span>



**<span data-ttu-id="e95c2-152">将数据库和证书从服务器 A 移动到 B</span><span class="sxs-lookup"><span data-stu-id="e95c2-152">To move the Database and Certificate from Server A to B</span></span>**

1.  <span data-ttu-id="e95c2-153">使用 Windows 资源管理器将 MBAM 恢复和硬件数据库数据 .bak 从服务器 A 移动到服务器 B。</span><span class="sxs-lookup"><span data-stu-id="e95c2-153">Move the MBAM Recovery and Hardware database data.bak from Server A to Server B by using Windows Explorer.</span></span>

2.  <span data-ttu-id="e95c2-154">若要移动加密数据库的证书，则需要使用以下自动化步骤。</span><span class="sxs-lookup"><span data-stu-id="e95c2-154">To move the certificate for the encrypted database, you will need to use the following automation steps.</span></span> <span data-ttu-id="e95c2-155">若要自动执行此过程，你可以使用 Windows PowerShell 输入类似于以下内容的命令：</span><span class="sxs-lookup"><span data-stu-id="e95c2-155">To automate this procedure, you can use Windows PowerShell to enter a command that is similar to the following:</span></span>

    `PS C:\> Copy-Item “Z:\MBAM Recovery and Hardware Database Data.bak” \\$SERVERNAME$\$DESTINATIONSHARE$`

    `PS C:\> Copy-Item “Z:\SQLServerInstanceCertificateFile” \\$SERVERNAME$\$DESTINATIONSHARE$`

    `PS C:\> Copy-Item “Z:\SQLServerInstanceCertificateFilePrivateKey” \\$SERVERNAME$\$DESTINATIONSHARE$`

    **<span data-ttu-id="e95c2-156">注意</span><span class="sxs-lookup"><span data-stu-id="e95c2-156">Note</span></span>**  
    <span data-ttu-id="e95c2-157">将前面示例中的值替换为与你的环境匹配的值：</span><span class="sxs-lookup"><span data-stu-id="e95c2-157">Replace the value from the preceding example with those that match your environment:</span></span>

    -   <span data-ttu-id="e95c2-158">$SERVERNAME $-输入要将文件复制到的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="e95c2-158">$SERVERNAME$ - Enter the name of the server to which the files will be copied.</span></span>

    -   <span data-ttu-id="e95c2-159">$DESTINATIONSHARE $-输入要将文件复制到的共享和路径的名称。</span><span class="sxs-lookup"><span data-stu-id="e95c2-159">$DESTINATIONSHARE$ - Enter the name of the share and path to which the files will be copied.</span></span>



**<span data-ttu-id="e95c2-160">在服务器 B 上还原数据库</span><span class="sxs-lookup"><span data-stu-id="e95c2-160">To restore the Database on Server B</span></span>**

1.  <span data-ttu-id="e95c2-161">通过使用 SQL Server Management Studio 和名为**Restore database**的任务还原服务器 B 上的恢复和硬件数据库。</span><span class="sxs-lookup"><span data-stu-id="e95c2-161">Restore the Recovery and Hardware database on Server B by using the SQL Server Management Studio and the Task named **Restore Database**.</span></span>

2.  <span data-ttu-id="e95c2-162">执行任务后，选择数据库备份文件，方法是选择 "**发件人设备**" 选项，然后使用 "**添加**" 命令选择 MBAM 恢复和硬件数据库**数据 .bak**文件。</span><span class="sxs-lookup"><span data-stu-id="e95c2-162">Once the task has been executed, choose the database backup file by selecting the **From Device** option, and then use the **Add** command to choose the MBAM Recovery and Hardware database **Data.bak** file.</span></span>

3.  <span data-ttu-id="e95c2-163">选择 **"确定"** 完成还原过程。</span><span class="sxs-lookup"><span data-stu-id="e95c2-163">Select **OK** to complete the restoration process.</span></span>

4.  <span data-ttu-id="e95c2-164">若要自动执行此过程，请创建包含以下 SQL 脚本的 SQL 文件（.sql）：</span><span class="sxs-lookup"><span data-stu-id="e95c2-164">To automate this procedure, create a SQL file (.sql) that contains the following SQL script:</span></span>

    ```sql
    -- Restore MBAM Recovery and Hardware Database. 

    USE master

    GO
    ```

    <span data-ttu-id="e95c2-165">删除由 MBAM 安装程序创建的证书。</span><span class="sxs-lookup"><span data-stu-id="e95c2-165">Drop the certificate created by MBAM Setup.</span></span>

    ```sql
    DROP CERTIFICATE [MBAM Recovery Encryption Certificate]

    GO
    ```

    <span data-ttu-id="e95c2-166">添加证书</span><span class="sxs-lookup"><span data-stu-id="e95c2-166">Add certificate</span></span>

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

    <span data-ttu-id="e95c2-167">还原 MBAM 恢复和硬件数据库数据以及日志文件。</span><span class="sxs-lookup"><span data-stu-id="e95c2-167">Restore the MBAM Recovery and Hardware database data and the log files.</span></span>

    ```sql
    RESTORE DATABASE [MBAM Recovery and Hardware]

       FROM DISK = 'Z:\MBAM Recovery and Hardware Database Data.bak'

       WITH REPLACE
    ```

    **<span data-ttu-id="e95c2-168">注意</span><span class="sxs-lookup"><span data-stu-id="e95c2-168">Note</span></span>**  
    <span data-ttu-id="e95c2-169">将前面示例中的值替换为与你的环境匹配的值：</span><span class="sxs-lookup"><span data-stu-id="e95c2-169">Replace the values from the preceding example with those that match your environment:</span></span>

    -   <span data-ttu-id="e95c2-170">$PASSWORD $-输入用于加密私钥文件的密码。</span><span class="sxs-lookup"><span data-stu-id="e95c2-170">$PASSWORD$ - Enter the password that you used to encrypt the Private Key file.</span></span>



5.  <span data-ttu-id="e95c2-171">使用 Windows PowerShell 输入类似于以下内容的命令行：</span><span class="sxs-lookup"><span data-stu-id="e95c2-171">Use Windows PowerShell to enter a command line that is similar to the following:</span></span>

    `PS C:\> Invoke-Sqlcmd -InputFile 'Z:\RestoreMBAMRecoveryandHardwarDatabaseScript.sql' -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$`

    **<span data-ttu-id="e95c2-172">注意</span><span class="sxs-lookup"><span data-stu-id="e95c2-172">Note</span></span>**  
    <span data-ttu-id="e95c2-173">将 receding 示例中的值替换为与你的环境匹配的值：</span><span class="sxs-lookup"><span data-stu-id="e95c2-173">Replace the value from the receding example with those that match your environment:</span></span>

    -   <span data-ttu-id="e95c2-174">$SERVERNAME $ \\ $SQLINSTANCENAME $-输入服务器的名称以及恢复和硬件数据库将还原到的实例。</span><span class="sxs-lookup"><span data-stu-id="e95c2-174">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the name of the server and the instance to which the Recovery and Hardware Database will be restored.</span></span>



**<span data-ttu-id="e95c2-175">在服务器 B 上配置对数据库的访问</span><span class="sxs-lookup"><span data-stu-id="e95c2-175">Configure the access to the Database on Server B</span></span>**

1.  <span data-ttu-id="e95c2-176">在服务器 B 上，使用服务器管理器中的本地用户和组管理单元，将运行 MBAM 管理和监视功能的每台服务器中的计算机帐户添加到名为**MBAM 恢复和硬件数据库访问**的本地组。</span><span class="sxs-lookup"><span data-stu-id="e95c2-176">On Server B, use the Local user and Groups snap-in from Server Manager, to add the computer accounts from each server that runs the MBAM Administration and Monitoring feature to the Local Group named **MBAM Recovery and Hardware DB Access**.</span></span>

2.  <span data-ttu-id="e95c2-177">若要自动执行此过程，可以在服务器 B 上使用 Windows PowerShell 输入类似于以下内容的命令：</span><span class="sxs-lookup"><span data-stu-id="e95c2-177">To automate this procedure, you can use Windows PowerShell on Server B to enter a command that is similar to the following:</span></span>

    `PS C:\> net localgroup "MBAM Recovery and Hardware DB Access" $DOMAIN$\$SERVERNAME$$  /add`

    **<span data-ttu-id="e95c2-178">注意</span><span class="sxs-lookup"><span data-stu-id="e95c2-178">Note</span></span>**  
    <span data-ttu-id="e95c2-179">将前面示例中的值替换为适用于你的环境的适用值：</span><span class="sxs-lookup"><span data-stu-id="e95c2-179">Replace the values from the preceding example with the applicable values for your environment:</span></span>

    -   <span data-ttu-id="e95c2-180">$DOMAIN $ \ \ $SERVERNAME $ $-输入 MBAM 管理和监视服务器的域名和计算机名。</span><span class="sxs-lookup"><span data-stu-id="e95c2-180">$DOMAIN$\\$SERVERNAME$$ - Enter the domain name and machine name of the MBAM Administration and Monitoring Server.</span></span> <span data-ttu-id="e95c2-181">服务器名称后面必须跟有 a **$** ，例如，MyDomain\\MyServerName1 $。</span><span class="sxs-lookup"><span data-stu-id="e95c2-181">The server name must be followed by a **$**, for example, MyDomain\\MyServerName1$.</span></span>



~~~
You must run the command for each Administration and Monitoring Server that will be accessing the database in your environment.
~~~

**<span data-ttu-id="e95c2-182">更新 MBAM 管理和监视服务器上的数据库连接数据</span><span class="sxs-lookup"><span data-stu-id="e95c2-182">To update the Database Connection data on MBAM Administration and Monitoring Servers</span></span>**

1. <span data-ttu-id="e95c2-183">在运行 MBAM 管理和监视功能的每台服务器上，使用 Internet Information Services （IIS）管理器控制台更新下列应用程序的连接字符串信息，这些应用程序位于 Microsoft BitLocker 管理和监视网站中：</span><span class="sxs-lookup"><span data-stu-id="e95c2-183">On each of the servers that run the MBAM Administration and Monitoring feature, use the Internet Information Services (IIS) Manager console to update the Connection String information for the following applications, which are hosted in the Microsoft BitLocker Administration and Monitoring website:</span></span>

   -   <span data-ttu-id="e95c2-184">MBAM 管理服务</span><span class="sxs-lookup"><span data-stu-id="e95c2-184">MBAM Administration Service</span></span>

   -   <span data-ttu-id="e95c2-185">MBAM 恢复和硬件服务</span><span class="sxs-lookup"><span data-stu-id="e95c2-185">MBAM Recovery And Hardware Service</span></span>

2. <span data-ttu-id="e95c2-186">选择每个应用程序并使用 "**配置编辑器**" 功能，该功能位于 "功能"**视图**的 "**管理**" 部分下。</span><span class="sxs-lookup"><span data-stu-id="e95c2-186">Select each application and use the **Configuration Editor** feature, which is located under the **Management** section of the **Feature View**.</span></span>

3. <span data-ttu-id="e95c2-187">从 "节列表" 控件中选择 " **configurationStrings** " 选项。</span><span class="sxs-lookup"><span data-stu-id="e95c2-187">Select the **configurationStrings** option from the Section list control.</span></span>

4. <span data-ttu-id="e95c2-188">选择名为 **（集合）** 的行，然后通过选择行右侧的按钮打开**集合编辑器**。</span><span class="sxs-lookup"><span data-stu-id="e95c2-188">Choose the row named **(Collection)**, and open the **Collection Editor** by selecting the button on the right side of the row.</span></span>

5. <span data-ttu-id="e95c2-189">在**集合编辑器**中，当你更新 "MBAMAdministrationService" 应用程序的配置时，选择名为 " **KeyRecoveryConnectionString** " 的行，或者选择名为 "Mbam RecoveryAndHardwareDataStore" 的行 <strong> 。 </strong>当更新 "MBAMRecoveryAndHardwareService" 的配置时，ConnectionString。</span><span class="sxs-lookup"><span data-stu-id="e95c2-189">In the **Collection Editor**, choose the row named **KeyRecoveryConnectionString** when you updated the configuration for the ‘MBAMAdministrationService’ application, or choose the row named <strong>Microsoft.Mbam.RecoveryAndHardwareDataStore.</strong>ConnectionString, when updating the configuration for the ‘MBAMRecoveryAndHardwareService’.</span></span>

6. <span data-ttu-id="e95c2-190">更新**configurationStrings**属性的**数据源 =** 值以列出服务器名称以及将恢复和硬件数据库移动到的实例。</span><span class="sxs-lookup"><span data-stu-id="e95c2-190">Update the **Data Source=** value for the **configurationStrings** property to list the server name and the instance where the Recovery and Hardware Database was moved to.</span></span> <span data-ttu-id="e95c2-191">例如，$SERVERNAME $ \ $SQLINSTANCENAME $。</span><span class="sxs-lookup"><span data-stu-id="e95c2-191">For example, $SERVERNAME$\\$SQLINSTANCENAME$.</span></span>

7. <span data-ttu-id="e95c2-192">若要自动执行此过程，你可以使用与以下命令类似的命令，方法是在每个管理和监视服务器上使用 Windows PowerShell：</span><span class="sxs-lookup"><span data-stu-id="e95c2-192">To automate this procedure, you can use a command that is similar to the following one, by using Windows PowerShell on each Administration and Monitoring Server:</span></span>

   `PS C:\> Set-WebConfigurationProperty '/connectionStrings/add[@name="KeyRecoveryConnectionString"]' -PSPath "IIS:\sites\Microsoft BitLocker Administration and Monitoring\MBAMAdministrationService" -Name "connectionString" -Value “Data Source=$SERVERNAME$\$SQLINSTANCENAME$;Initial Catalog=MBAM Recovery and Hardware;Integrated Security=SSPI;”`

   `PS C:\> Set-WebConfigurationProperty '/connectionStrings/add[@name="Microsoft.Mbam.RecoveryAndHardwareDataStore.ConnectionString"]' -PSPath "IIS:\sites\Microsoft BitLocker Administration and Monitoring\MBAMRecoveryAndHardwareService" -Name "connectionString" -Value "Data Source=$SERVERNAME$\$SQLINSTANCENAME$;Initial Catalog=MBAM Recovery and Hardware;Integrated Security=SSPI;"`

   **<span data-ttu-id="e95c2-193">注意</span><span class="sxs-lookup"><span data-stu-id="e95c2-193">Note</span></span>**  
   <span data-ttu-id="e95c2-194">将前面示例中的值替换为与你的环境匹配的值：</span><span class="sxs-lookup"><span data-stu-id="e95c2-194">Replace the value from the preceding example with those that match your environment:</span></span>

   -   <span data-ttu-id="e95c2-195">$SERVERNAME $ \\ $SQLINSTANCENAME $-输入恢复和硬件数据库所在的服务器名称和实例。</span><span class="sxs-lookup"><span data-stu-id="e95c2-195">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the server name and instance where the Recovery and Hardware database is.</span></span>



**<span data-ttu-id="e95c2-196">恢复 MBAM 管理和监视网站的所有实例</span><span class="sxs-lookup"><span data-stu-id="e95c2-196">To resume all instances of the MBAM Administration and Monitoring website</span></span>**

1.  <span data-ttu-id="e95c2-197">在运行 MBAM 管理和监视功能的每台服务器上，使用 Internet Information Services （IIS）管理器控制台启动 MBAM 网站，该网站名为 " **Microsoft BitLocker 管理和监视**"。</span><span class="sxs-lookup"><span data-stu-id="e95c2-197">On each of the servers that run the MBAM Administration and Monitoring feature, use the Internet Information Services (IIS) Manager console to Start the MBAM website, which is named **Microsoft BitLocker Administration and Monitoring**.</span></span>

2.  <span data-ttu-id="e95c2-198">若要自动执行此过程，你可以使用 Windows PowerShell，使用类似于下面的命令：</span><span class="sxs-lookup"><span data-stu-id="e95c2-198">To automate this procedure, you can use a command that is similar to the following one, by using Windows PowerShell:</span></span>

    `PS C:\> Start-Website “Microsoft BitLocker Administration and Monitoring”`

## <span data-ttu-id="e95c2-199">移动合规性状态数据库功能</span><span class="sxs-lookup"><span data-stu-id="e95c2-199">To move the Compliance Status Database feature</span></span>


<span data-ttu-id="e95c2-200">如果你选择将 MBAM 合规状态数据库功能从一台计算机移动到另一台计算机（例如从服务器 A 移动到服务器 B），则应使用以下过程：</span><span class="sxs-lookup"><span data-stu-id="e95c2-200">If you choose to move the MBAM Compliance Status Database feature from one computer to another, such as from Server A to Server B, you should use the following procedure:</span></span>

1.  <span data-ttu-id="e95c2-201">停止 MBAM 管理和监视网站的所有实例</span><span class="sxs-lookup"><span data-stu-id="e95c2-201">Stop all instances of the MBAM Administration and Monitoring website</span></span>

2.  <span data-ttu-id="e95c2-202">在服务器 B 上运行 MBAM 设置</span><span class="sxs-lookup"><span data-stu-id="e95c2-202">Run MBAM setup on Server B</span></span>

3.  <span data-ttu-id="e95c2-203">在服务器 A 上备份数据库</span><span class="sxs-lookup"><span data-stu-id="e95c2-203">Backup the Database on Server A</span></span>

4.  <span data-ttu-id="e95c2-204">将数据库从服务器 A 移动到 B</span><span class="sxs-lookup"><span data-stu-id="e95c2-204">Move the Database from Server A to B</span></span>

5.  <span data-ttu-id="e95c2-205">在服务器 B 上还原数据库</span><span class="sxs-lookup"><span data-stu-id="e95c2-205">Restore the Database on Server B</span></span>

6.  <span data-ttu-id="e95c2-206">在服务器 B 上配置对数据库的访问</span><span class="sxs-lookup"><span data-stu-id="e95c2-206">Configure Access to the Database on Server B</span></span>

7.  <span data-ttu-id="e95c2-207">在 MBAM 管理和监视服务器上更新数据库连接数据</span><span class="sxs-lookup"><span data-stu-id="e95c2-207">Update database connection data on MBAM Administration and Monitoring servers</span></span>

8.  <span data-ttu-id="e95c2-208">恢复 MBAM 管理和监视网站的所有实例</span><span class="sxs-lookup"><span data-stu-id="e95c2-208">Resume all instances of the MBAM Administration and Monitoring website</span></span>

**<span data-ttu-id="e95c2-209">停止 MBAM 管理和监视网站的所有实例</span><span class="sxs-lookup"><span data-stu-id="e95c2-209">To stop all instances of the MBAM Administration and Monitoring website</span></span>**

1.  <span data-ttu-id="e95c2-210">在运行 MBAM 管理和监视功能的每台服务器上，使用 Internet Information Services （IIS）管理器控制台停止名为**Microsoft BitLocker 管理和监视**的 MBAM 网站。</span><span class="sxs-lookup"><span data-stu-id="e95c2-210">On each of the servers that run the MBAM Administration and Monitoring feature, use the Internet Information Services (IIS) Manager console to Stop the MBAM website, which is named **Microsoft BitLocker Administration and Monitoring**.</span></span>

2.  <span data-ttu-id="e95c2-211">若要自动执行此过程，你可以使用 Windows PowerShell，使用类似于下面的命令：</span><span class="sxs-lookup"><span data-stu-id="e95c2-211">To automate this procedure, you can use a command that is similar to the following one,by using Windows PowerShell:</span></span>

    `PS C:\> Stop-Website “Microsoft BitLocker Administration and Monitoring”`

    **<span data-ttu-id="e95c2-212">注意</span><span class="sxs-lookup"><span data-stu-id="e95c2-212">Note</span></span>**  
    <span data-ttu-id="e95c2-213">若要执行此命令，必须将用于 PowerShell 的 IIS 模块添加到当前的 PowerShell 实例。</span><span class="sxs-lookup"><span data-stu-id="e95c2-213">To execute this command, you must add the IIS Module for PowerShell to current instance of PowerShell.</span></span> <span data-ttu-id="e95c2-214">此外，必须更新 PowerShell 执行策略以启用脚本的执行。</span><span class="sxs-lookup"><span data-stu-id="e95c2-214">In addition, you must update the PowerShell execution policy to enable the execution of scripts.</span></span>



**<span data-ttu-id="e95c2-215">在服务器 B 上运行 MBAM 设置</span><span class="sxs-lookup"><span data-stu-id="e95c2-215">To run MBAM Setup on Server B</span></span>**

1.  <span data-ttu-id="e95c2-216">在服务器 B 上运行 MBAM 设置，然后选择要安装的合规性状态数据库功能。</span><span class="sxs-lookup"><span data-stu-id="e95c2-216">Run MBAM Setup on Server B and select the Compliance Status Database feature for installation.</span></span>

2.  <span data-ttu-id="e95c2-217">若要自动执行此过程，你可以使用 Windows PowerShell，使用类似于下面的命令：</span><span class="sxs-lookup"><span data-stu-id="e95c2-217">To automate this procedure, you can use a command that is similar to the following one, by using Windows PowerShell:</span></span>

    `PS C:\> MbamSetup.exe /qn I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 AddLocal= ReportsDatabase ADMINANDMON_MACHINENAMES=$DOMAIN$\$SERVERNAME$ COMPLIDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ REPORTS_USERACCOUNT=$DOMAIN$\$USERNAME$`

    **<span data-ttu-id="e95c2-218">注意</span><span class="sxs-lookup"><span data-stu-id="e95c2-218">Note</span></span>**  
    <span data-ttu-id="e95c2-219">将前面示例中的值替换为与你的环境匹配的值：</span><span class="sxs-lookup"><span data-stu-id="e95c2-219">Replace the values from the preceding example with those that match your environment:</span></span>

    -   <span data-ttu-id="e95c2-220">$SERVERNAME $ \\ $SQLINSTANCENAME $-输入要将合规性状态数据库移动到的服务器名称和实例。</span><span class="sxs-lookup"><span data-stu-id="e95c2-220">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the server name and instance where the Compliance Status Database will be moved to.</span></span>

    -   <span data-ttu-id="e95c2-221">$DOMAIN $ \\ $SERVERNAME $-输入将联系合规性状态数据库的每个 MBAM 应用程序和监视服务器的域名和服务器名称。</span><span class="sxs-lookup"><span data-stu-id="e95c2-221">$DOMAIN$\\$SERVERNAME$ - Enter the domain names and server names of each MBAM Application and Monitoring Server that will contact the Compliance Status Database.</span></span> <span data-ttu-id="e95c2-222">如果有多个域名和服务器名称，请使用分号分隔列表中的每一个名称。</span><span class="sxs-lookup"><span data-stu-id="e95c2-222">If there are multiple domain names and server names, use a semicolon to separate each one of them in the list.</span></span> <span data-ttu-id="e95c2-223">例如，$DOMAIN \\SERVERNAME $; $DOMAIN \ $SERVERNAME $ $。</span><span class="sxs-lookup"><span data-stu-id="e95c2-223">For example, $DOMAIN\\SERVERNAME$;$DOMAIN\\$SERVERNAME$$.</span></span> <span data-ttu-id="e95c2-224">每个服务器名称必须后接一个 **$** ，如示例中所示。</span><span class="sxs-lookup"><span data-stu-id="e95c2-224">Each server name must be followed by a **$** as shown in the example.</span></span> <span data-ttu-id="e95c2-225">例如，MyDomain\\MyServerName1 $，MyDomain\\MyServerName2 $。</span><span class="sxs-lookup"><span data-stu-id="e95c2-225">For example, MyDomain\\MyServerName1$, MyDomain\\MyServerName2$.</span></span>

    -   <span data-ttu-id="e95c2-226">$DOMAIN $ \\ $USERNAME $-输入合规性和审核报告功能将用于连接到合规性状态数据库的域名和用户名。</span><span class="sxs-lookup"><span data-stu-id="e95c2-226">$DOMAIN$\\$USERNAME$ - Enter the domain and user name that will be used by the Compliance and Audit reports feature to connect to the Compliance Status Database.</span></span>



**<span data-ttu-id="e95c2-227">备份服务器 A 上的合规性数据库</span><span class="sxs-lookup"><span data-stu-id="e95c2-227">To back up the Compliance Database on Server A</span></span>**

1.  <span data-ttu-id="e95c2-228">若要备份服务器 A 上的合规性数据库，请使用 SQL Server Management Studio 和名为 "**备份 ...**" 的任务。</span><span class="sxs-lookup"><span data-stu-id="e95c2-228">To back up the Compliance Database on Server A, use SQL Server Management Studio and the Task named **Back Up…**.</span></span> <span data-ttu-id="e95c2-229">默认情况下，数据库名称是**MBAM 合规性状态数据库**。</span><span class="sxs-lookup"><span data-stu-id="e95c2-229">By default, the database name is **MBAM Compliance Status Database**.</span></span>

2.  <span data-ttu-id="e95c2-230">若要自动执行此过程，请创建包含以下 SQL 脚本的 SQL 文件（.sql）：</span><span class="sxs-lookup"><span data-stu-id="e95c2-230">To automate this procedure, create a SQL file (.sql) that contains the following-SQL script:</span></span>

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

3.  <span data-ttu-id="e95c2-231">通过使用 SQL Server PowerShell，使用一个类似于下面的命令运行 SQL 文件：</span><span class="sxs-lookup"><span data-stu-id="e95c2-231">Run the SQL file with a command that is similar to the following one, by using the SQL Server PowerShell:</span></span>

    `PS C:\> Invoke-Sqlcmd -InputFile "Z:\BackupMBAMComplianceStatusDatabaseScript.sql" –ServerInstance $SERVERNAME$\$SQLINSTANCENAME$`

    **<span data-ttu-id="e95c2-232">注意</span><span class="sxs-lookup"><span data-stu-id="e95c2-232">Note</span></span>**  
    <span data-ttu-id="e95c2-233">将前面示例中的值替换为与你的环境匹配的值：</span><span class="sxs-lookup"><span data-stu-id="e95c2-233">Replace the value from the preceding example with those that match your environment:</span></span>

    -   <span data-ttu-id="e95c2-234">$SERVERNAME $ \\ $SQLINSTANCENAME $-输入服务器名称和将备份合规性状态数据库的实例。</span><span class="sxs-lookup"><span data-stu-id="e95c2-234">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the server name and the instance from where the Compliance Status database will be backed up.</span></span>



**<span data-ttu-id="e95c2-235">将数据库从服务器 A 移动到 B</span><span class="sxs-lookup"><span data-stu-id="e95c2-235">To move the Database from Server A to B</span></span>**

1.  <span data-ttu-id="e95c2-236">使用 Windows 资源管理器将以下文件从服务器 A 移动到服务器 B：</span><span class="sxs-lookup"><span data-stu-id="e95c2-236">Move the following files from Server A to Server B, by using Windows Explorer:</span></span>

    -   <span data-ttu-id="e95c2-237">MBAM 合规性状态数据库数据 .bak</span><span class="sxs-lookup"><span data-stu-id="e95c2-237">MBAM Compliance Status Database Data.bak</span></span>

2.  <span data-ttu-id="e95c2-238">若要自动执行此过程，你可以使用类似于以下使用 Windows PowerShell 的命令：</span><span class="sxs-lookup"><span data-stu-id="e95c2-238">To automate this procedure, you can use a command that is similar to the following using Windows PowerShell:</span></span>

    `PS C:\> Copy-Item “Z:\MBAM Compliance Status Database Data.bak” \\$SERVERNAME$\$DESTINATIONSHARE$`

    **<span data-ttu-id="e95c2-239">注意</span><span class="sxs-lookup"><span data-stu-id="e95c2-239">Note</span></span>**  
    <span data-ttu-id="e95c2-240">将前面示例中的值替换为与你的环境匹配的值：</span><span class="sxs-lookup"><span data-stu-id="e95c2-240">Replace the value from the preceding example with those that match your environment:</span></span>

    -   <span data-ttu-id="e95c2-241">$SERVERNAME $-输入要将文件复制到的服务器名称。</span><span class="sxs-lookup"><span data-stu-id="e95c2-241">$SERVERNAME$ - Enter the server name where the files will be copied to.</span></span>

    -   <span data-ttu-id="e95c2-242">$DESTINATIONSHARE $-输入要将文件复制到的共享和路径的名称。</span><span class="sxs-lookup"><span data-stu-id="e95c2-242">$DESTINATIONSHARE$ - Enter the name of share and path where the files will be copied to.</span></span>



**<span data-ttu-id="e95c2-243">在服务器 B 上还原数据库</span><span class="sxs-lookup"><span data-stu-id="e95c2-243">To restore the Database on Server B</span></span>**

1.  <span data-ttu-id="e95c2-244">使用 SQL Server Management Studio 和名为**Restore database**的任务还原服务器 B 上的合规性状态数据库 ...。</span><span class="sxs-lookup"><span data-stu-id="e95c2-244">Restore the Compliance Status database on Server B by using SQL Server Management Studio and the Task named **Restore Database…**.</span></span>

2.  <span data-ttu-id="e95c2-245">执行任务后，选择数据库备份文件，方法是选择 "发件人设备" 选项，然后使用 "添加" 命令选择 MBAM 合规性状态数据库数据 .bak 文件。</span><span class="sxs-lookup"><span data-stu-id="e95c2-245">Once the task is executed, select the database backup file, by selecting the From Device option, and then use the Add command to choose the MBAM Compliance Status Database Data.bak file.</span></span> <span data-ttu-id="e95c2-246">单击 "确定" 完成还原过程。</span><span class="sxs-lookup"><span data-stu-id="e95c2-246">Click OK to complete the restoration process.</span></span>

3.  <span data-ttu-id="e95c2-247">若要自动执行此过程，请创建包含以下 SQL 脚本的 SQL 文件（.sql）：</span><span class="sxs-lookup"><span data-stu-id="e95c2-247">To automate this procedure, create a SQL file (.sql) that contains the following-SQL script:</span></span>

    ```sql
    -- Create MBAM Compliance Status Database Data logical backup devices. 

    Use master

    GO

    -- Restore the MBAM Compliance Status database data files.

    RESTORE DATABASE [MBAM Compliance Status Database]

       FROM DISK = 'C:\test\MBAM Compliance Status Database Data.bak'

       WITH REPLACE
    ```

4.  <span data-ttu-id="e95c2-248">通过使用 SQL Server PowerShell，使用一个类似于下面的命令运行 SQL 文件：</span><span class="sxs-lookup"><span data-stu-id="e95c2-248">Run the SQL File with a command that is similar to the following one, by using the SQL Server PowerShell:</span></span>

    `PS C:\> Invoke-Sqlcmd -InputFile "Z:\RestoreMBAMComplianceStatusDatabaseScript.sql" -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$`

    **<span data-ttu-id="e95c2-249">注意</span><span class="sxs-lookup"><span data-stu-id="e95c2-249">Note</span></span>**  
    <span data-ttu-id="e95c2-250">将前面示例中的值替换为与你的环境匹配的值：</span><span class="sxs-lookup"><span data-stu-id="e95c2-250">Replace the value from the preceding example with those that match your environment:</span></span>

    -   <span data-ttu-id="e95c2-251">$SERVERNAME $ \\ $SQLINSTANCENAME $-输入要将合规性状态数据库还原到的服务器名称和实例。</span><span class="sxs-lookup"><span data-stu-id="e95c2-251">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the server name and instance where the Compliance Status Database will be restored to.</span></span>



**<span data-ttu-id="e95c2-252">在服务器 B 上配置对数据库的访问权限</span><span class="sxs-lookup"><span data-stu-id="e95c2-252">To configure the Access to the Database on Server B</span></span>**

1.  <span data-ttu-id="e95c2-253">在服务器 B 上，使用服务器管理器中的 "本地用户和组" 管理单元将运行 MBAM 管理和监视功能的每台服务器中的计算机帐户添加到名为**MBAM 合规性状态数据库访问**的本地组。</span><span class="sxs-lookup"><span data-stu-id="e95c2-253">On Server B use the Local user and Groups snap-in from Server Manager to add the machine accounts from each server that runs the MBAM Administration and Monitoring feature to the Local Group named **MBAM Compliance Status DB Access**.</span></span>

2.  <span data-ttu-id="e95c2-254">若要自动执行此过程，你可以通过在服务器 B 上使用 Windows PowerShell，使用类似于下面的命令：</span><span class="sxs-lookup"><span data-stu-id="e95c2-254">To automate this procedure, you can use a command that is similar to the following one, by using Windows PowerShell on Server B:</span></span>

    `PS C:\> net localgroup "MBAM Compliance Auditing DB Access" $DOMAIN$\$SERVERNAME$$  /add`

    `PS C:\> net localgroup "MBAM Compliance Auditing DB Access" $DOMAIN$\$REPORTSUSERNAME$  /add`

    **<span data-ttu-id="e95c2-255">注意</span><span class="sxs-lookup"><span data-stu-id="e95c2-255">Note</span></span>**  
    <span data-ttu-id="e95c2-256">将前面示例中的值替换为适用于你的环境的适用值：</span><span class="sxs-lookup"><span data-stu-id="e95c2-256">Replace the value from the preceding example with the applicable values for your environment:</span></span>

    -   <span data-ttu-id="e95c2-257">$DOMAIN $ \ \ $SERVERNAME $ $-输入 MBAM 管理和监视服务器的域名和计算机名。</span><span class="sxs-lookup"><span data-stu-id="e95c2-257">$DOMAIN$\\$SERVERNAME$$ - Enter the domain and machine name of the MBAM Administration and Monitoring Server.</span></span> <span data-ttu-id="e95c2-258">服务器名称后面必须跟有一个 **$** 。例如，MyDomain\\MyServerName1 $。</span><span class="sxs-lookup"><span data-stu-id="e95c2-258">The server name must be followed by a **$**.For example, MyDomain\\MyServerName1$.</span></span>

    -   <span data-ttu-id="e95c2-259">$DOMAIN $ \\ $REPORTSUSERNAME $-输入用于配置合规性和审核报告的数据源的用户帐户名称</span><span class="sxs-lookup"><span data-stu-id="e95c2-259">$DOMAIN$\\$REPORTSUSERNAME$ - Enter the user account name that was used to configure the data source for the Compliance and Audit reports</span></span>



~~~
For each Administration and Monitoring Server that will access the database of your environment, you must run the command that will add the servers to the MBAM Compliance Auditing DB Access local group.
~~~

**<span data-ttu-id="e95c2-260">更新 MBAM 管理和监视服务器上的数据库连接数据</span><span class="sxs-lookup"><span data-stu-id="e95c2-260">To update the database connection data on MBAM Administration and Monitoring servers</span></span>**

1.  <span data-ttu-id="e95c2-261">在运行 MBAM 管理和监视功能的每台服务器上，使用 Internet Information Services （IIS）管理器控制台更新下列应用程序的连接字符串信息，这些应用程序位于 Microsoft BitLocker 管理和监视网站中：</span><span class="sxs-lookup"><span data-stu-id="e95c2-261">On each of the servers that run the MBAM Administration and Monitoring feature, use the Internet Information Services (IIS) Manager console to update the Connection String information for the following Applications, which are hosted in the Microsoft BitLocker Administration and Monitoring website:</span></span>

    -   <span data-ttu-id="e95c2-262">MBAMAdministrationService</span><span class="sxs-lookup"><span data-stu-id="e95c2-262">MBAMAdministrationService</span></span>

    -   <span data-ttu-id="e95c2-263">MBAMComplianceStatusService</span><span class="sxs-lookup"><span data-stu-id="e95c2-263">MBAMComplianceStatusService</span></span>

2.  <span data-ttu-id="e95c2-264">选择每个应用程序并使用 "**配置编辑器**" 功能，该功能位于 "功能"**视图**的 "**管理**" 部分下。</span><span class="sxs-lookup"><span data-stu-id="e95c2-264">Select each application and use the **Configuration Editor** feature, which is located under the **Management** section of the **Feature View**.</span></span>

3.  <span data-ttu-id="e95c2-265">从 "节列表" 控件中选择 " **configurationStrings** " 选项。</span><span class="sxs-lookup"><span data-stu-id="e95c2-265">Select the **configurationStrings** option from the Section list control.</span></span>

4.  <span data-ttu-id="e95c2-266">选择名为 **（集合）** 的行，然后通过选择行右侧的按钮打开集合编辑器。</span><span class="sxs-lookup"><span data-stu-id="e95c2-266">Select the row named **(Collection)**, and open the Collection Editor by selecting the button on the right side of the row.</span></span>

5.  <span data-ttu-id="e95c2-267">在**集合编辑器**中，当你更新 MBAMAdministrationService 应用程序的配置时，请选择名为**ComplianceStatusConnectionString**的行，或者当你更新 MBAMComplianceStatusService 的配置时，请选择名为**BitLockerManagement**. 的行。</span><span class="sxs-lookup"><span data-stu-id="e95c2-267">In the **Collection Editor**, select the row named **ComplianceStatusConnectionString**, when you update the configuration for the MBAMAdministrationService application, or the row named **Microsoft.Windows.Mdop.BitLockerManagement.StatusReportDataStore.ConnectionString**, when you update the configuration for the MBAMComplianceStatusService.</span></span>

6.  <span data-ttu-id="e95c2-268">更新**configurationStrings**属性的**数据源 =** 值以列出服务器名称和实例名称。</span><span class="sxs-lookup"><span data-stu-id="e95c2-268">Update the **Data Source=** value for the **configurationStrings** property to list the server name and the instance name.</span></span> <span data-ttu-id="e95c2-269">例如，$SERVERNAME $ \\ $SQLINSTANCENAME，恢复和硬件数据库被移动到该数据库。</span><span class="sxs-lookup"><span data-stu-id="e95c2-269">For example, $SERVERNAME$\\$SQLINSTANCENAME, to which the Recovery and Hardware Database was moved.</span></span>

7.  <span data-ttu-id="e95c2-270">若要自动执行此过程，你可以使用 Windows PowerShell 在每个管理和监视服务器上输入一个类似于以下内容的命令：</span><span class="sxs-lookup"><span data-stu-id="e95c2-270">To automate this procedure, you can use Windows PowerShell to enter a command that is similar to the following one on each Administration and Monitoring Server:</span></span>

    `PS C:\> Set-WebConfigurationProperty '/connectionStrings/add[@name="ComplianceStatusConnectionString"]' -PSPath "IIS:\sites\Microsoft BitLocker Administration and Monitoring\MBAMAdministrationService" -Name "connectionString" -Value "Data Source=$SERVERNAME$\$SQLINSTANCENAME$;Initial Catalog=MBAM Compliance Status;Integrated Security=SSPI;"`

    `PS C:\> Set-WebConfigurationProperty '/connectionStrings/add[@name="Microsoft.Windows.Mdop.BitLockerManagement.StatusReportDataStore.ConnectionString"]' -PSPath "IIS:\sites\Microsoft BitLocker Administration and Monitoring\MBAMComplianceStatusService" -Name "connectionString" -Value "Data Source=$SERVERNAME$\$SQLINSTANCENAME;Initial Catalog=MBAM Compliance Status;Integrated Security=SSPI;"`

    **<span data-ttu-id="e95c2-271">注意</span><span class="sxs-lookup"><span data-stu-id="e95c2-271">Note</span></span>**  
    <span data-ttu-id="e95c2-272">将前面示例中的值替换为与你的环境匹配的值：</span><span class="sxs-lookup"><span data-stu-id="e95c2-272">Replace the value from the preceding example with those that match your environment:</span></span>

    -   <span data-ttu-id="e95c2-273">$SERVERNAME $ \\ $SQLINSTANCENAME $-输入恢复和硬件数据库所在的服务器名称和实例名称。</span><span class="sxs-lookup"><span data-stu-id="e95c2-273">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the server name and instance name where the Recovery and Hardware Database is located.</span></span>



**<span data-ttu-id="e95c2-274">恢复 MBAM 管理和监视网站的所有实例</span><span class="sxs-lookup"><span data-stu-id="e95c2-274">To resume all instances of the MBAM Administration and Monitoring website</span></span>**

1.  <span data-ttu-id="e95c2-275">在运行 MBAM 管理和监视功能的每台服务器上，使用 Internet Information Services （IIS）管理器控制台启动名为**Microsoft BitLocker 管理和监视**的 MBAM 网站。</span><span class="sxs-lookup"><span data-stu-id="e95c2-275">On each of the servers running the MBAM Administration and Monitoring feature, use the Internet Information Services (IIS) Manager console to start the MBAM web site named **Microsoft BitLocker Administration and Monitoring**.</span></span>

2.  <span data-ttu-id="e95c2-276">若要自动执行此过程，你可以使用 Windows PowerShell 输入类似于以下内容的命令：</span><span class="sxs-lookup"><span data-stu-id="e95c2-276">To automate this procedure, you can use Windows PowerShell to enter a command that is similar to the following:</span></span>

    **<span data-ttu-id="e95c2-277">PS C:\\ &gt; 启动-网站 "Microsoft BitLocker 管理和监视"</span><span class="sxs-lookup"><span data-stu-id="e95c2-277">PS C:\\&gt; Start-Website “Microsoft BitLocker Administration and Monitoring”</span></span>**

## <span data-ttu-id="e95c2-278">移动合规性和审核报告</span><span class="sxs-lookup"><span data-stu-id="e95c2-278">To moving the Compliance and Audit Reports</span></span>


<span data-ttu-id="e95c2-279">如果你选择将 MBAM 合规性和审核报告从一台计算机移动到另一台计算机（特别是，如果你将功能从服务器 A 移动到服务器 B），则应使用以下过程和步骤：</span><span class="sxs-lookup"><span data-stu-id="e95c2-279">If you choose to move the MBAM Compliance and Audit Reports from one computer to another (specifically, if you move feature from Server A to Server B), you should use the following procedure and steps:</span></span>

1.  <span data-ttu-id="e95c2-280">在服务器 B 上运行 MBAM 设置</span><span class="sxs-lookup"><span data-stu-id="e95c2-280">Run MBAM setup on Server B</span></span>

2.  <span data-ttu-id="e95c2-281">配置对服务器 B 上的合规性和审核报告的访问权限</span><span class="sxs-lookup"><span data-stu-id="e95c2-281">Configure Access to the Compliance and Audit Reports on Server B</span></span>

3.  <span data-ttu-id="e95c2-282">停止 MBAM 管理和监视网站的所有实例</span><span class="sxs-lookup"><span data-stu-id="e95c2-282">Stop all instances of the MBAM Administration and Monitoring website</span></span>

4.  <span data-ttu-id="e95c2-283">在 MBAM 管理和监视服务器上更新报表连接数据</span><span class="sxs-lookup"><span data-stu-id="e95c2-283">Update the reports connection data on MBAM Administration and Monitoring servers</span></span>

5.  <span data-ttu-id="e95c2-284">恢复 MBAM 管理和监视网站的所有实例</span><span class="sxs-lookup"><span data-stu-id="e95c2-284">Resume all instances of the MBAM Administration and Monitoring website</span></span>

**<span data-ttu-id="e95c2-285">在服务器 B 上运行 MBAM 设置</span><span class="sxs-lookup"><span data-stu-id="e95c2-285">To run MBAM setup on Server B</span></span>**

1.  <span data-ttu-id="e95c2-286">在服务器 B 上运行 MBAM 设置，并仅选择要安装的合规性和审核功能。</span><span class="sxs-lookup"><span data-stu-id="e95c2-286">Run MBAM setup on Server B and only select the Compliance and Audit feature for installation.</span></span>

2.  <span data-ttu-id="e95c2-287">若要自动执行此过程，可以使用 Windows PowerShell，使用类似于以下内容的命令：</span><span class="sxs-lookup"><span data-stu-id="e95c2-287">To automate this procedure, you can use a command that is similar to the following, by using Windows PowerShell:</span></span>

    `PS C:\> MbamSetup.exe /qn I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 AddLocal=Reports COMPLIDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ REPORTS_USERACCOUNTPW=$PASSWORD$`

    **<span data-ttu-id="e95c2-288">注意</span><span class="sxs-lookup"><span data-stu-id="e95c2-288">Note</span></span>**  
    <span data-ttu-id="e95c2-289">将前面示例中的值替换为与你的环境匹配的值：</span><span class="sxs-lookup"><span data-stu-id="e95c2-289">Replace the values from the preceding example with those that match your environment:</span></span>

    -   <span data-ttu-id="e95c2-290">$SERVERNAME $ \\ $SQLINSTANCENAME $-输入合规性状态数据库所在的服务器名称和实例。</span><span class="sxs-lookup"><span data-stu-id="e95c2-290">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the server name and instance where the Compliance Status Database is located.</span></span>

    -   <span data-ttu-id="e95c2-291">$DOMAIN $ \\ $USERNAME $-输入合规性和审核报告功能将用于连接到合规性状态数据库的域名和用户名。</span><span class="sxs-lookup"><span data-stu-id="e95c2-291">$DOMAIN$\\$USERNAME$ - Enter the domain name and user name that will be used by the Compliance and Audit reports feature to connect to the Compliance Status Database.</span></span>

    -   <span data-ttu-id="e95c2-292">$PASSWORD $-输入将用于连接到合规性状态数据库的用户帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="e95c2-292">$PASSWORD$ - Enter the password of the user account that will be used to connect to the Compliance Status Database.</span></span>



**<span data-ttu-id="e95c2-293">在服务器 B 上配置合规性和审核报告的访问权限</span><span class="sxs-lookup"><span data-stu-id="e95c2-293">To configure the access to the Compliance and Audit Reports on Server B</span></span>**

1.  <span data-ttu-id="e95c2-294">在服务器 B 上，使用服务器管理器中的 "本地用户和组" 管理单元添加将有权访问合规性和审核报告的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="e95c2-294">On Server B, use the Local user and Groups snap-in from Server Manager to add the user accounts that will have access to the Compliance and Audit Reports.</span></span> <span data-ttu-id="e95c2-295">将用户帐户添加到名为 "MBAM Report Users" 的本地组中。</span><span class="sxs-lookup"><span data-stu-id="e95c2-295">Add the user accounts to the local group named “MBAM Report Users”.</span></span>

2.  <span data-ttu-id="e95c2-296">若要自动执行此过程，你可以通过在服务器 B 上使用 Windows PowerShell，使用类似于以下内容的命令。</span><span class="sxs-lookup"><span data-stu-id="e95c2-296">To automate this procedure, you can use a command that is similar to the following, by using Windows PowerShell on Server B.</span></span>

    `PS C:\> net localgroup "MBAM Report Users" $DOMAIN$\$REPORTSUSERNAME$  /add`

    **<span data-ttu-id="e95c2-297">注意</span><span class="sxs-lookup"><span data-stu-id="e95c2-297">Note</span></span>**  
    <span data-ttu-id="e95c2-298">将上述示例中的以下值替换为适用于你的环境的适用值：</span><span class="sxs-lookup"><span data-stu-id="e95c2-298">Replace the following value from the preceding example with the applicable values for your environment:</span></span>

    -   <span data-ttu-id="e95c2-299">$DOMAIN $ \\ $REPORTSUSERNAME $-输入用于配置合规性和审核报告的数据源的用户帐户名称</span><span class="sxs-lookup"><span data-stu-id="e95c2-299">$DOMAIN$\\$REPORTSUSERNAME$ - Enter the user account name that was used to configure the data source for the Compliance and Audit reports</span></span>



~~~
The command to add the users to the MBAM Report Users local group must be run for each user that will be accessing the reports in your environment.
~~~

**<span data-ttu-id="e95c2-300">停止 MBAM 管理和监视网站的所有实例</span><span class="sxs-lookup"><span data-stu-id="e95c2-300">To stop all instances of the MBAM Administration and Monitoring website</span></span>**

1.  <span data-ttu-id="e95c2-301">在运行 MBAM 管理和监视功能的每台服务器上，使用 Internet 信息服务（IIS）管理器控制台停止名为**Microsoft BitLocker 管理和监视**的 MBAM 网站。</span><span class="sxs-lookup"><span data-stu-id="e95c2-301">On each of the servers that run the MBAM Administration and Monitoring Feature use the Internet Information Services (IIS) Manager console to Stop the MBAM website named **Microsoft BitLocker Administration and Monitoring**.</span></span>

2.  <span data-ttu-id="e95c2-302">若要自动执行此过程，你可以使用 Windows PowerShell，使用类似于下面的命令：</span><span class="sxs-lookup"><span data-stu-id="e95c2-302">To automate this procedure, you can use a command that is similar to the following one, by using Windows PowerShell:</span></span>

    `PS C:\> Stop-Website “Microsoft BitLocker Administration and Monitoring”`

**<span data-ttu-id="e95c2-303">更新 MBAM 管理和监视服务器上的数据库连接数据</span><span class="sxs-lookup"><span data-stu-id="e95c2-303">To update the Database Connection Data on MBAM Administration and Monitoring Servers</span></span>**

1. <span data-ttu-id="e95c2-304">在运行 MBAM 管理和监视功能的每台服务器上，使用 Internet Information Services （IIS）管理器控制台更新合规性报告 URL。</span><span class="sxs-lookup"><span data-stu-id="e95c2-304">On each of the servers that run the MBAM Administration and Monitoring Feature, use the Internet Information Services (IIS) Manager console to update the Compliance Reports URL.</span></span>

2. <span data-ttu-id="e95c2-305">选择 " **Microsoft BitLocker 管理和监视**" 网站并使用 "**配置编辑器**" 功能，该功能可在**功能视图**的 "**管理**" 部分下找到。</span><span class="sxs-lookup"><span data-stu-id="e95c2-305">Select the **Microsoft BitLocker Administration and Monitoring** website and use the **Configuration Editor** feature which can be found under the **Management** section of the **Feature View**.</span></span>

3. <span data-ttu-id="e95c2-306">从 "节列表" 控件中选择 " **appSettings** " 选项。</span><span class="sxs-lookup"><span data-stu-id="e95c2-306">Select the **appSettings** option from the Section list control.</span></span>

4. <span data-ttu-id="e95c2-307">在此处，选择名为 **（集合）** 的行，然后通过选择行右侧的按钮打开**集合编辑器**。</span><span class="sxs-lookup"><span data-stu-id="e95c2-307">From here, select the row named **(Collection)**, and open the **Collection Editor** by selecting the button on the right side of the row.</span></span>

5. <span data-ttu-id="e95c2-308">在**集合编辑器**中，选择名为 "Microsoft Mbam" 的行。</span><span class="sxs-lookup"><span data-stu-id="e95c2-308">In the **Collection Editor**, select the row named “Microsoft.Mbam.Reports.Url”.</span></span>

6. <span data-ttu-id="e95c2-309">更新 Mbam 的值以反映服务器 B 的服务器名称。如果已在命名的 SQL Reporting Services 实例上安装了合规性和审核报告功能，请确保将实例的名称添加或更新到 URL。</span><span class="sxs-lookup"><span data-stu-id="e95c2-309">Update the value for Microsoft.Mbam.Reports.Url to reflect the server name for Server B. If the Compliance and Audit reports feature was installed on a named SQL Reporting Services instance, make sure that you add or update the name of the instance to the URL.</span></span> <span data-ttu-id="e95c2-310">例如，http://$SERVERNAME $/ReportServer\_ $ SQLSRSINSTANCENAME $/Pages..。。</span><span class="sxs-lookup"><span data-stu-id="e95c2-310">For example, http://$SERVERNAME$/ReportServer\_$SQLSRSINSTANCENAME$/Pages....</span></span>

7. <span data-ttu-id="e95c2-311">若要自动执行此过程，你可以使用 Windows PowerShell 在每个管理和监视服务器上输入一个类似于以下内容的命令：</span><span class="sxs-lookup"><span data-stu-id="e95c2-311">To automate this procedure, you can use Windows PowerShell to enter a command that is similar to the following one on each Administration and Monitoring Server:</span></span>

   `PS C:\> Set-WebConfigurationProperty '/appSettings/add[@key="Microsoft.Mbam.Reports.Url"]' -PSPath "IIS:\sites\Microsoft BitLocker Administration and Monitoring" -Name "Value" -Value “http://$SERVERNAME$/ReportServer_$SRSINSTANCENAME$/Pages/ReportViewer.aspx?/Malta+Compliance+Reports/”`

   **<span data-ttu-id="e95c2-312">注意</span><span class="sxs-lookup"><span data-stu-id="e95c2-312">Note</span></span>**  
   <span data-ttu-id="e95c2-313">将前面示例中的值替换为与你的环境匹配的值：</span><span class="sxs-lookup"><span data-stu-id="e95c2-313">Replace the value from the preceding example with those that match your environment:</span></span>

   -   <span data-ttu-id="e95c2-314">$SERVERNAME $-输入已安装合规性和审核报告的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="e95c2-314">$SERVERNAME$ - Enter the name of the server to which the Compliance and Audit Reports were installed.</span></span>

   -   <span data-ttu-id="e95c2-315">$SRSINSTANCENAME $-输入已安装合规性和审核报告的 SQL Reporting Services 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="e95c2-315">$SRSINSTANCENAME$ - Enter the name of the SQL Reporting Services instance to which the Compliance and Audit Reports were installed.</span></span>



**<span data-ttu-id="e95c2-316">恢复 MBAM 管理和监视网站的所有实例</span><span class="sxs-lookup"><span data-stu-id="e95c2-316">To resume all instances of the MBAM Administration and Monitoring website</span></span>**

1.  <span data-ttu-id="e95c2-317">在运行 MBAM 管理和监视功能的每台服务器上，使用 Internet Information Services （IIS）管理器控制台启动名为**Microsoft BitLocker 管理和监视**的 MBAM 网站。</span><span class="sxs-lookup"><span data-stu-id="e95c2-317">On each of the servers that run the MBAM Administration and Monitoring feature, use the Internet Information Services (IIS) Manager console to Start the MBAM web site named **Microsoft BitLocker Administration and Monitoring**.</span></span>

2.  <span data-ttu-id="e95c2-318">若要自动执行此过程，你可以使用 Windows PowerShell，使用类似于下面的命令：</span><span class="sxs-lookup"><span data-stu-id="e95c2-318">To automate this procedure, you can use a command that is similar to the following one, by using Windows PowerShell:</span></span>

    `PS C:\> Start-Website “Microsoft BitLocker Administration and Monitoring”`

    **<span data-ttu-id="e95c2-319">注意</span><span class="sxs-lookup"><span data-stu-id="e95c2-319">Note</span></span>**  
    <span data-ttu-id="e95c2-320">若要执行此命令，必须将用于 PowerShell 的 IIS 模块添加到 PowerShell 的当前实例。</span><span class="sxs-lookup"><span data-stu-id="e95c2-320">To execute this command, the IIS Module for PowerShell must be added to the current instance of PowerShell.</span></span> <span data-ttu-id="e95c2-321">此外，必须更新 PowerShell 执行策略以启用脚本执行。</span><span class="sxs-lookup"><span data-stu-id="e95c2-321">In addition, you must update the PowerShell execution policy to enable execution of scripts.</span></span>



## <span data-ttu-id="e95c2-322">移动 "管理和监视" 功能</span><span class="sxs-lookup"><span data-stu-id="e95c2-322">To move the Administration and Monitoring feature</span></span>


<span data-ttu-id="e95c2-323">如果你选择将 MBAM 管理和监视报告功能从一台计算机移动到另一台计算机（如果将功能从服务器 A 移动到服务器 B），则应使用以下过程。</span><span class="sxs-lookup"><span data-stu-id="e95c2-323">If you choose to move the MBAM Administration and Monitoring Reports feature from one computer to another, (if you move feature from Server A to Server B), you should use the following procedure.</span></span> <span data-ttu-id="e95c2-324">该过程包括以下步骤：</span><span class="sxs-lookup"><span data-stu-id="e95c2-324">The process includes the following steps:</span></span>

1.  <span data-ttu-id="e95c2-325">在服务器 B 上运行 MBAM 设置</span><span class="sxs-lookup"><span data-stu-id="e95c2-325">Run MBAM setup on Server B</span></span>

2.  <span data-ttu-id="e95c2-326">在服务器 B 上配置对数据库的访问</span><span class="sxs-lookup"><span data-stu-id="e95c2-326">Configure Access to the Database on Server B</span></span>

**<span data-ttu-id="e95c2-327">在服务器 B 上运行 MBAM 设置</span><span class="sxs-lookup"><span data-stu-id="e95c2-327">To run MBAM setup on Server B</span></span>**

1.  <span data-ttu-id="e95c2-328">在服务器 B 上运行 MBAM 设置，并仅选择安装的管理功能。</span><span class="sxs-lookup"><span data-stu-id="e95c2-328">Run MBAM setup on Server B and only select the Administration feature for installation.</span></span>

2.  <span data-ttu-id="e95c2-329">若要自动执行此过程，你可以使用 Windows PowerShell，使用类似于下面的命令：</span><span class="sxs-lookup"><span data-stu-id="e95c2-329">To automate this procedure, you can use a command that is similar to the following one, by using Windows PowerShell:</span></span>

    `PS C:\> MbamSetup.exe /qn I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 AddLocal=AdministrationMonitoringServer,HardwareCompatibility COMPLIDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ RECOVERYANDHWDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ SRS_REPORTSITEURL=$REPORTSSERVERURL$`

    **<span data-ttu-id="e95c2-330">注意</span><span class="sxs-lookup"><span data-stu-id="e95c2-330">Note</span></span>**  
    <span data-ttu-id="e95c2-331">将前面示例中的值替换为与你的环境匹配的值：</span><span class="sxs-lookup"><span data-stu-id="e95c2-331">Replace the values from the preceding example with those that match your environment:</span></span>

    -   <span data-ttu-id="e95c2-332">$SERVERNAME $ \\ $SQLINSTANCENAME $-对于 COMPLIDB \ _SQLINSTANCE 参数，输入合规性状态数据库所在的服务器名称和实例。</span><span class="sxs-lookup"><span data-stu-id="e95c2-332">$SERVERNAME$\\$SQLINSTANCENAME$ - For the COMPLIDB\_SQLINSTANCE parameter, input the server name and instance where the Compliance Status Database is located.</span></span> <span data-ttu-id="e95c2-333">对于 RECOVERYANDHWDB \ _SQLINSTANCE 参数，输入恢复和硬件数据库所在位置的服务器名称和实例。</span><span class="sxs-lookup"><span data-stu-id="e95c2-333">For the RECOVERYANDHWDB\_SQLINSTANCE parameter, input the server name and instance where the Recovery and Hardware Database is located.</span></span>

    -   <span data-ttu-id="e95c2-334">$DOMAIN $ \\ $USERNAME $-输入合规性和审核报告功能将用于连接到合规性状态数据库的域名和用户名。</span><span class="sxs-lookup"><span data-stu-id="e95c2-334">$DOMAIN$\\$USERNAME$ - Enter the domain and user name that will be used by the Compliance and Audit reports feature to connect to the Compliance Status Database.</span></span>

    -   <span data-ttu-id="e95c2-335">$ REPORTSSERVERURL $-输入 SQL Reporting Services 网站的主位置的 URL。</span><span class="sxs-lookup"><span data-stu-id="e95c2-335">$ REPORTSSERVERURL$ - Enter the URL for the Home location of the SQL Reporting Service website.</span></span> <span data-ttu-id="e95c2-336">如果报表已安装到默认 SRS 实例，URL 格式将设置为 "http://$SERVERNAME $/ReportServer" 的格式。</span><span class="sxs-lookup"><span data-stu-id="e95c2-336">If the reports were installed to a default SRS instance the URL format will formatted “http:// $SERVERNAME$/ReportServer”.</span></span> <span data-ttu-id="e95c2-337">如果报表已安装到默认 SRS 实例，则 URL 格式将设置为 "http://$SERVERNAME $/ReportServer\_ $ SQLINSTANCENAME $"。</span><span class="sxs-lookup"><span data-stu-id="e95c2-337">If the reports were installed to a default SRS instance, the URL format will be formatted to “http://$SERVERNAME$/ReportServer\_$SQLINSTANCENAME$”.</span></span>



**<span data-ttu-id="e95c2-338">配置对数据库的访问权限</span><span class="sxs-lookup"><span data-stu-id="e95c2-338">To configure the Access to the Databases</span></span>**

1.  <span data-ttu-id="e95c2-339">在恢复和硬件所在的服务器或服务器上，并部署合规性和审核数据库，请使用服务器管理器中的本地用户和组管理单元，将运行 MBAM 管理和监视功能的每台服务器中的计算机帐户添加到名为 "MBAM 恢复和硬件数据库访问" （恢复和硬件 DB 服务器）和 "MBAM 合规性状态 DB 访问" （合规性和审核数据库服务器）的本地组。</span><span class="sxs-lookup"><span data-stu-id="e95c2-339">On server or servers where the Recovery and Hardware, and Compliance and Audit databases are deployed, use the Local user and Groups snap-in from Server Manager to add the machine accounts from each server that run the MBAM Administration and Monitoring feature to the Local Groups named “MBAM Recovery and Hardware DB Access” (Recovery and Hardware DB Server) and “MBAM Compliance Status DB Access” (Compliance and Audit DB Server).</span></span>

2.  <span data-ttu-id="e95c2-340">若要自动执行此过程，你可以使用与以下内容类似的命令，方法是在部署合规性和审核数据库的服务器上使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="e95c2-340">To automate this procedure, you can use a command that is similar to the following one, by using Windows PowerShell on the server where the Compliance and Audit databases were deployed.</span></span>

    `PS C:\> net localgroup "MBAM Compliance Auditing DB Access" $DOMAIN$\$SERVERNAME$$  /add`

    `PS C:\> net localgroup "MBAM Compliance Auditing DB Access" $DOMAIN$\$REPORTSUSERNAME$  /add`

3.  <span data-ttu-id="e95c2-341">在部署恢复和硬件数据库的服务器上，使用 Windows PowerShell 运行与以下内容类似的命令。</span><span class="sxs-lookup"><span data-stu-id="e95c2-341">On the server where the Recovery and Hardware databases were deployed, run a command that is similar to the following one, by using Windows PowerShell.</span></span>

    `PS C:\> net localgroup "MBAM Recovery and Hardware DB Access" $DOMAIN$\$SERVERNAME$$  /add`

    **<span data-ttu-id="e95c2-342">注意</span><span class="sxs-lookup"><span data-stu-id="e95c2-342">Note</span></span>**  
    <span data-ttu-id="e95c2-343">将前面示例中的值替换为适用于你的环境的适用值：</span><span class="sxs-lookup"><span data-stu-id="e95c2-343">Replace the value from the preceding example with the applicable values for your environment:</span></span>

    -   <span data-ttu-id="e95c2-344">$DOMAIN $ \ \ $SERVERNAME $ $-输入 MBAM 管理和监视服务器的域名和计算机名。</span><span class="sxs-lookup"><span data-stu-id="e95c2-344">$DOMAIN$\\$SERVERNAME$$ - Enter the domain and machine name of the MBAM Administration and Monitoring Server.</span></span> <span data-ttu-id="e95c2-345">服务器名称后面必须跟有一个 **$** 。</span><span class="sxs-lookup"><span data-stu-id="e95c2-345">The server name must be followed by a **$**.</span></span> <span data-ttu-id="e95c2-346">例如，MyDomain\\MyServerName1 $）</span><span class="sxs-lookup"><span data-stu-id="e95c2-346">For example, MyDomain\\MyServerName1$)</span></span>

    -   <span data-ttu-id="e95c2-347">$DOMAIN $ \\ $REPORTSUSERNAME $-输入用于配置合规性和审核报告的数据源的用户帐户名称。</span><span class="sxs-lookup"><span data-stu-id="e95c2-347">$DOMAIN$\\$REPORTSUSERNAME$ - Enter the user account name that was used to configure the data source for the Compliance and Audit reports.</span></span>



~~~
The commands listed for adding the server computer accounts to the MBAM local groups must be run for each Administration and Monitoring Server that will be accessing the databases in your environment.
~~~

## <span data-ttu-id="e95c2-348">相关主题</span><span class="sxs-lookup"><span data-stu-id="e95c2-348">Related topics</span></span>


[<span data-ttu-id="e95c2-349">管理 MBAM 1.0 功能</span><span class="sxs-lookup"><span data-stu-id="e95c2-349">Administering MBAM 1.0 Features</span></span>](administering-mbam-10-features.md)









