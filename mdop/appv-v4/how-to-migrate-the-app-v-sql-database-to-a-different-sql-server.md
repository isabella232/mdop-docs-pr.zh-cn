---
title: 如何将 App-V SQL 数据库迁移到其他 SQL Server
description: 如何将 App-V SQL 数据库迁移到其他 SQL Server
author: dansimp
ms.assetid: 353892a1-9327-4489-a19c-4ec7bd1b736f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e3d84b0cb328873db3722ad3eb9af6a2b442fdcf
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801271"
---
# <span data-ttu-id="db821-103">如何将 App-V SQL 数据库迁移到其他 SQL Server</span><span class="sxs-lookup"><span data-stu-id="db821-103">How to Migrate the App-V SQL Database to a Different SQL Server</span></span>


<span data-ttu-id="db821-104">以下过程详细介绍了如何将 Microsoft Application Virtualization （app-v）管理服务器的 SQL 数据库迁移到其他 SQL 服务器。</span><span class="sxs-lookup"><span data-stu-id="db821-104">The following procedures describe in detail how to migrate the SQL database of the Microsoft Application Virtualization (App-V) Management Server to a different SQL Server.</span></span>

<span data-ttu-id="db821-105">**重要提示** 此过程要求停止应用 V 服务器服务，这将阻止最终用户使用其应用程序。</span><span class="sxs-lookup"><span data-stu-id="db821-105">**Important** This procedure requires that the App-V server service is stopped and this will prevent end-users from using their applications.</span></span>

 

**<span data-ttu-id="db821-106">备份 app-v SQL 数据库</span><span class="sxs-lookup"><span data-stu-id="db821-106">To back up the App-V SQL database</span></span>**

1.  <span data-ttu-id="db821-107">打开 services.msc 程序，并停止使用要迁移的数据库的所有管理服务器上的 App-v 管理服务器服务。</span><span class="sxs-lookup"><span data-stu-id="db821-107">Open the Services.msc program and stop the App-V Management Server service on all Management Servers that use the database to be migrated.</span></span>

2.  <span data-ttu-id="db821-108">在应用程序 V 数据库所在的计算机上，打开 SQL Server Management Studio。</span><span class="sxs-lookup"><span data-stu-id="db821-108">On the computer where the App-V database is located, open SQL Server Management Studio.</span></span>

3.  <span data-ttu-id="db821-109">展开 "**数据库**" 节点并找到 "app-v 数据库" （默认名称为 APPVIRT）。</span><span class="sxs-lookup"><span data-stu-id="db821-109">Expand the **Databases** node and locate the App-V database (default name is APPVIRT).</span></span>

4.  <span data-ttu-id="db821-110">右键单击数据库并选择 "**任务**"，然后选择 "**备份**"。</span><span class="sxs-lookup"><span data-stu-id="db821-110">Right-click the database and select **Tasks** and then select **Back Up**.</span></span>

5.  <span data-ttu-id="db821-111">验证 "**恢复模型**" 设置为 "**简单**"，"**备份类型**" 设置为 "**完整**"。</span><span class="sxs-lookup"><span data-stu-id="db821-111">Verify that **Recovery model** is set to **SIMPLE** and the **Backup type** is set to **Full**.</span></span> <span data-ttu-id="db821-112">如有必要，请更改**备份集**和**目标**设置。</span><span class="sxs-lookup"><span data-stu-id="db821-112">Change the **Backup set** and **Destination** settings if it is necessary.</span></span>

6.  <span data-ttu-id="db821-113">单击 **"确定"** 备份数据库。</span><span class="sxs-lookup"><span data-stu-id="db821-113">Click **OK** to back up the database.</span></span> <span data-ttu-id="db821-114">备份成功完成后，单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="db821-114">After the backup has completed successfully, click **OK**.</span></span>

7.  <span data-ttu-id="db821-115">打开 Windows 资源管理器，浏览到包含数据库备份文件的文件夹，例如 APPVIRT。.BAK.</span><span class="sxs-lookup"><span data-stu-id="db821-115">Open Windows Explorer and browse to the folder that contains the database backup file, for example APPVIRT.BAK.</span></span> <span data-ttu-id="db821-116">将数据库备份文件复制到运行 SQL Server 的目标计算机。</span><span class="sxs-lookup"><span data-stu-id="db821-116">Copy the database backup file to the destination computer that is running SQL Server.</span></span>

**<span data-ttu-id="db821-117">将 app-v SQL 数据库还原到目标计算机</span><span class="sxs-lookup"><span data-stu-id="db821-117">To restore the App-V SQL database to the destination computer</span></span>**

1.  <span data-ttu-id="db821-118">在目标计算机上，打开 SQL Server Management Studio，右键单击 "**数据库**" 节点，然后选择 "**还原数据库**"。</span><span class="sxs-lookup"><span data-stu-id="db821-118">On the destination computer, open SQL Server Management Studio, right-click the **Databases** node and select **Restore Database**.</span></span>

2.  <span data-ttu-id="db821-119">在 "**还原源**" 下，选择 "**从设备**"，然后单击 "**..."。**</span><span class="sxs-lookup"><span data-stu-id="db821-119">Under **Source for Restore**, choose **From device** and then click the “**…**”</span></span> <span data-ttu-id="db821-120">按钮。</span><span class="sxs-lookup"><span data-stu-id="db821-120">button.</span></span>

3.  <span data-ttu-id="db821-121">在 "**指定备份**" 对话框中，确保**备份媒体**已设置为 "**文件**"，然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="db821-121">In the **Specify Backup** dialog box, make sure that the **Backup Media** is set to **File** and then click **Add**.</span></span>

4.  <span data-ttu-id="db821-122">选择从运行 SQL Server 的原始计算机复制的备份文件，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="db821-122">Select the backup file that you copied from the original computer that is running SQL Server, and then click **OK**.</span></span>

5.  <span data-ttu-id="db821-123">单击 **"确定"** ，然后单击以选择要还原的备份集。</span><span class="sxs-lookup"><span data-stu-id="db821-123">Click **OK** and then click to select the backup set to restore.</span></span>

6.  <span data-ttu-id="db821-124">在 "**还原目标**" 下，单击 "**数据库**" 下拉列表，然后选择 "app-v" 数据库名称，例如 APPVIRT。</span><span class="sxs-lookup"><span data-stu-id="db821-124">Under **Destination for restore**, click the drop-down for **To database** and select the App-V database name, for example APPVIRT.</span></span>

7.  <span data-ttu-id="db821-125">单击 **"确定"** 启动还原。</span><span class="sxs-lookup"><span data-stu-id="db821-125">Click **OK** to start the restore.</span></span> <span data-ttu-id="db821-126">还原成功完成后，单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="db821-126">After the restore has completed successfully, click **OK**.</span></span>

8.  <span data-ttu-id="db821-127">展开 "**安全**" 节点，右键单击 "**登录**"，然后选择 "**新建登录**"。</span><span class="sxs-lookup"><span data-stu-id="db821-127">Expand the **Security** node, right-click **Logins** and select **New Login**.</span></span>

9.  <span data-ttu-id="db821-128">在 "**登录名**" 字段中，输入 App-v 管理服务器的网络服务帐户详细信息，格式为 DOMAIN\\SERVERNAME $。</span><span class="sxs-lookup"><span data-stu-id="db821-128">In the **Login Name** field, enter the Network Service account details for the App-V Management Server in the format of DOMAIN\\SERVERNAME$.</span></span>

10. <span data-ttu-id="db821-129">在 "**默认数据库**" 下的 "**常规**" 页面上，选择 "app-v" 数据库名称，例如 "APPVIRT"，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="db821-129">On the **General** page under **Default database** select the App-V database name, for example, APPVIRT, and then click **OK**.</span></span>

11. <span data-ttu-id="db821-130">在 "**选择页面**" 下，单击以选择 "**用户映射**" 页面。</span><span class="sxs-lookup"><span data-stu-id="db821-130">Under **Select a page**, click to select the **User Mapping** page.</span></span> <span data-ttu-id="db821-131">在 "**用户映射到此登录名**" 下，单击 "**映射**" 列中的复选框以选择 app-v 数据库。</span><span class="sxs-lookup"><span data-stu-id="db821-131">Under **Users mapped to this login**, click the check box in the **Map** column to select the App-V database.</span></span>

12. <span data-ttu-id="db821-132">在 **： &lt; &gt; Appvdatabasename 的 "数据库角色成员身份**" 下，单击以选择**SFTEveryone** ，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="db821-132">Under **Database role membership for: &lt;appvdatabasename&gt;**, click to select **SFTEveryone** and then click **OK**.</span></span>

13. <span data-ttu-id="db821-133">确保将运行 SQL Server 的新计算机上的 Windows 防火墙配置为允许 App-v 管理服务器访问系统。</span><span class="sxs-lookup"><span data-stu-id="db821-133">Make sure that the Windows Firewall on the new computer that is running SQL Server is configured to allow the App-V Management Server to access the system.</span></span> <span data-ttu-id="db821-134">在 "**管理工具**" 下，使用**具有高级安全程序的 WINDOWS 防火墙**为 SQL Server 使用的端口创建**入站规则**（默认为端口1433）。</span><span class="sxs-lookup"><span data-stu-id="db821-134">Under **Administrative Tools**, use the **Windows Firewall with Advanced Security** program to create an **Inbound Rule** for the port that is used by SQL Server (default is port 1433).</span></span>

**<span data-ttu-id="db821-135">迁移 app-v SQL Server 代理作业</span><span class="sxs-lookup"><span data-stu-id="db821-135">To migrate the App-V SQL Server Agent jobs</span></span>**

1.  <span data-ttu-id="db821-136">在运行 SQL Server 的原始计算机上，在 SQL Server Management Studio 中，展开 " **Sql Server 代理**" 节点，然后展开 "**作业**" 节点。</span><span class="sxs-lookup"><span data-stu-id="db821-136">On the original computer that is running SQL Server, in SQL Server Management Studio, expand the **SQL Server Agent** node, and then expand the **Jobs** node.</span></span>

2.  <span data-ttu-id="db821-137">右键单击以下四个 App-v 作业，然后选择 "**脚本作业" 作为 |创建到 |文件**，并将每个脚本保存到一个文件夹，并为每个脚本提供一个描述性名称。</span><span class="sxs-lookup"><span data-stu-id="db821-137">Right-click the following four App-V jobs and select **Script Job as | CREATE to | File**, and save each script to a folder and give each script a descriptive name.</span></span>

    -   **<span data-ttu-id="db821-138">Softgrid 数据库（appvdbname）检查使用情况历史记录</span><span class="sxs-lookup"><span data-stu-id="db821-138">Softgrid Database (appvdbname) Check Usage History</span></span>**

    -   **<span data-ttu-id="db821-139">Softgrid 数据库（appvdbname）关闭孤立会话</span><span class="sxs-lookup"><span data-stu-id="db821-139">Softgrid Database (appvdbname) Close Orphaned Sessions</span></span>**

    -   **<span data-ttu-id="db821-140">Softgrid 数据库（appvdbname）强制大小限制</span><span class="sxs-lookup"><span data-stu-id="db821-140">Softgrid Database (appvdbname) Enforce Size Limit</span></span>**

    -   **<span data-ttu-id="db821-141">Softgrid 数据库（appvdbname）监视器警报/作业状态</span><span class="sxs-lookup"><span data-stu-id="db821-141">Softgrid Database (appvdbname) Monitor Alert/Job Status</span></span>**

3.  <span data-ttu-id="db821-142">将四个脚本文件（.sql）复制到运行 SQL Server 的目标计算机，并打开 SQL Server Management Studio。</span><span class="sxs-lookup"><span data-stu-id="db821-142">Copy the four script files (.sql) to the destination computer that is running SQL Server and open SQL Server Management Studio.</span></span>

4.  <span data-ttu-id="db821-143">在 Windows 资源管理器中，右键单击每个 .sql 文件，然后单击 "**运行**"。</span><span class="sxs-lookup"><span data-stu-id="db821-143">In Windows Explorer, right-click each .sql file and then click **Run**.</span></span> <span data-ttu-id="db821-144">每个脚本都将在 SQL Server Management Studio 中的查询窗口中打开。</span><span class="sxs-lookup"><span data-stu-id="db821-144">Each script will open in a query window in SQL Server Management Studio.</span></span> <span data-ttu-id="db821-145">单击每个脚本的 "**执行**" 并验证每个脚本是否已成功完成。</span><span class="sxs-lookup"><span data-stu-id="db821-145">Click **Execute** for each script and verify that each is completed successfully.</span></span>

5.  <span data-ttu-id="db821-146">刷新**SQL Server 代理**节点下的 "**作业**" 节点，确认已成功创建四个作业。</span><span class="sxs-lookup"><span data-stu-id="db821-146">Refresh the **Jobs** node under the **SQL Server Agent** node and confirm that the four jobs are created successfully.</span></span>

**<span data-ttu-id="db821-147">更新 app-v 管理服务器的配置</span><span class="sxs-lookup"><span data-stu-id="db821-147">To update the configuration of the App-V Management Server</span></span>**

1.  <span data-ttu-id="db821-148">在 App-v 管理服务器上，修改以下注册表项：</span><span class="sxs-lookup"><span data-stu-id="db821-148">On the App-V Management Server, modify the following registry keys:</span></span>

    -   <span data-ttu-id="db821-149">**SQLServerName**  =  SQLServerName &lt;newservername&gt;</span><span class="sxs-lookup"><span data-stu-id="db821-149">**SQLServerName** = &lt;newservername&gt;</span></span>

    -   <span data-ttu-id="db821-150">**SQLServerPort**  =  SQLServerPort &lt;newserverport&gt;</span><span class="sxs-lookup"><span data-stu-id="db821-150">**SQLServerPort** = &lt;newserverport&gt;</span></span>

    <span data-ttu-id="db821-151">然后重新启动 app-v 服务器服务。</span><span class="sxs-lookup"><span data-stu-id="db821-151">Then restart the App-V server service.</span></span>

2.  <span data-ttu-id="db821-152">通过浏览找到应用程序 V 管理服务器安装目录下的文件 SftMgmt （默认为 C:\\program files Files\\Microsoft System Center App Virt 管理 Server\\App Virt 管理服务）。</span><span class="sxs-lookup"><span data-stu-id="db821-152">Browse to find the file SftMgmt.udl under the App-V Management Server installation directory (default is C:\\Program Files\\Microsoft System Center App Virt Management Server\\App Virt Management Service).</span></span> <span data-ttu-id="db821-153">右键单击文件，然后选择 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="db821-153">Right-click the file and select **Open**.</span></span>

3.  <span data-ttu-id="db821-154">在 "**连接**" 选项卡上，输入运行 SQL Server 的目标计算机的名称，然后单击 "**测试连接**"。</span><span class="sxs-lookup"><span data-stu-id="db821-154">On the **Connection** tab, enter the name of the destination computer that is running SQL Server, and then click **Test Connection**.</span></span> <span data-ttu-id="db821-155">测试成功后，单击 **"确定"** ，然后再次单击 **"确定"** 。</span><span class="sxs-lookup"><span data-stu-id="db821-155">When the test is successful, click **OK** and then click **OK** again.</span></span>

4.  <span data-ttu-id="db821-156">对于 4.5 SP2 之前的 app-v 管理服务器版本，必须更新 SQL 日志记录设置。</span><span class="sxs-lookup"><span data-stu-id="db821-156">For App-V Management Server versions before 4.5 SP2, you must update the SQL Logging settings.</span></span> <span data-ttu-id="db821-157">在 "**服务器组**" 下，右键单击服务器所属的服务器组，然后选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="db821-157">Under **Server Groups**, right-click the server group the server is a member of and select **Properties**.</span></span>

5.  <span data-ttu-id="db821-158">在 "**日志记录**" 选项卡上，单击以选择**SQL 数据库**条目，然后单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="db821-158">On the **Logging** tab click to select the **SQL Database** entry and then click **Edit**.</span></span>

6.  <span data-ttu-id="db821-159">将**DNS 主机名**更改为运行 SQL Server 的新计算机的主机名，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="db821-159">Change the **DNS Host Name** to the host name of the new computer that is running SQL Server and then click **OK**.</span></span> <span data-ttu-id="db821-160">再次单击 **"确定"** 两次，然后重新启动 app-v 服务器服务。</span><span class="sxs-lookup"><span data-stu-id="db821-160">Click **OK** two times more, and then restart the App-V server service.</span></span>

7.  <span data-ttu-id="db821-161">打开 app-v 管理控制台，右键单击 "**应用程序**" 节点，然后选择 "**刷新**"。</span><span class="sxs-lookup"><span data-stu-id="db821-161">Open the App-V Management Console, right-click the **Applications** node and select **Refresh**.</span></span> <span data-ttu-id="db821-162">应用程序列表应显示为 "以前"。</span><span class="sxs-lookup"><span data-stu-id="db821-162">The list of applications should be displayed as before.</span></span>

 

 





