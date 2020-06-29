---
title: 使用 SQL 脚本创建 App-V 4.5 数据库
description: 使用 SQL 脚本创建 App-V 4.5 数据库
author: dansimp
ms.assetid: 6cd0b180-163e-463f-a658-939ab9a7cfa1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d9ab2c102a43701bfdeaac49359b4ca3c4a063fa
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803876"
---
# <span data-ttu-id="4274f-103">使用 SQL 脚本创建 App-V 4.5 数据库</span><span class="sxs-lookup"><span data-stu-id="4274f-103">Creating App-V 4.5 Databases Using SQL Scripting</span></span>


**<span data-ttu-id="4274f-104">此解决方案的用途是什么？</span><span class="sxs-lookup"><span data-stu-id="4274f-104">Who is this solution intended for?</span></span>** <span data-ttu-id="4274f-105">管理应用程序虚拟化（app-v）4.5 数据库的信息技术专业人员。</span><span class="sxs-lookup"><span data-stu-id="4274f-105">Information technology professionals who manage Application Virtualization (App-V) 4.5 databases.</span></span>

**<span data-ttu-id="4274f-106">本指南如何帮助你？</span><span class="sxs-lookup"><span data-stu-id="4274f-106">How can this guide help you?</span></span>** <span data-ttu-id="4274f-107">本解决方案介绍并介绍在管理员安装对 SQL Server 不具有 "sysadmin" 权限时，安装 Microsoft Application Virtualization 服务器的过程。</span><span class="sxs-lookup"><span data-stu-id="4274f-107">This solution explains and documents the procedure to install the Microsoft Application Virtualization Server when the administrator installing does not have “sysadmin” privileges to the SQL Server.</span></span>

## <span data-ttu-id="4274f-108">概述</span><span class="sxs-lookup"><span data-stu-id="4274f-108">Overview</span></span>


<span data-ttu-id="4274f-109">安装 Microsoft Application Virtualization 4.5 （App-v）的挑战之一是，安装程序假定安装服务器功能的用户不仅是本地计算机管理员，还在将承载数据存储的 SQL server 上拥有 SQL 管理员权限。</span><span class="sxs-lookup"><span data-stu-id="4274f-109">One of the challenges of installing Microsoft Application Virtualization 4.5 (App-V) is that the install program assumes that the user installing the server features will not only be a local computer administrator, but also have SQL administrator privileges on the SQL server that will host the Data Store.</span></span> <span data-ttu-id="4274f-110">此要求基于在安装过程中创建数据库以及相应的角色和权限这一事实。</span><span class="sxs-lookup"><span data-stu-id="4274f-110">This requirement is based on the fact that the database, as well as the appropriate roles and permissions, are created as part of the install.</span></span> <span data-ttu-id="4274f-111">但是，在大多数企业中，SQL server 与将要安装 app-v 的基础结构团队分开管理。</span><span class="sxs-lookup"><span data-stu-id="4274f-111">However, in most enterprises, SQL servers are managed separately from the infrastructure team who will be installing App-V.</span></span> <span data-ttu-id="4274f-112">这些安全要求使 SQL 管理员有可能很难让基础结构管理员安装 app-v，从而获得足够的权限;同样，SQL 管理员将不具有为基础结构团队安装产品所需的权限。</span><span class="sxs-lookup"><span data-stu-id="4274f-112">These security requirements will make it difficult to get SQL administrators to give the infrastructure administrator installing App-V adequate rights; similarly, the SQL administrators will not have the required privileges to install the product for the infrastructure team.</span></span>

<span data-ttu-id="4274f-113">当前，尝试安装 app-v 的管理员必须具有 SQL "sysadmin" 权限。</span><span class="sxs-lookup"><span data-stu-id="4274f-113">Currently, an administrator attempting the installation of App-V must have SQL “sysadmin” privileges.</span></span> <span data-ttu-id="4274f-114">在以前版本的产品中，SQL 管理员允许 SQL 管理员创建临时 "sysadmin" 帐户或在安装过程中显示，以提供具有 "sysadmin" 权限的凭据。</span><span class="sxs-lookup"><span data-stu-id="4274f-114">In previous versions of the product the setup allowed for the SQL administrators to either create a temporary “sysadmin” account or be present during installation to provide credentials with “sysadmin” privileges.</span></span> <span data-ttu-id="4274f-115">在此版本中，脚本在发布产品中提供，供所有管理员在实施其基础结构时使用。</span><span class="sxs-lookup"><span data-stu-id="4274f-115">In this release, scripts are provided in the released product for all administrators to use when implementing their infrastructure.</span></span>

<span data-ttu-id="4274f-116">此白皮书将讨论安装需要划分为两个单独任务的方案：创建 SQL 数据库和安装 App-v server 功能。</span><span class="sxs-lookup"><span data-stu-id="4274f-116">This whitepaper discusses the scenario in which the install will need to be divided into two separate tasks: creating the SQL database, and installing the App-V server features.</span></span> <span data-ttu-id="4274f-117">SQL 管理员可以查看 SQL 脚本并进行修改以解决与其他数据库的任何冲突，或支持与其他工具的集成。</span><span class="sxs-lookup"><span data-stu-id="4274f-117">The SQL administrators would be able to review the SQL scripts and make modifications to resolve any conflicts with other databases, or to support integration with other tools.</span></span> <span data-ttu-id="4274f-118">脚本的结果是允许 SQL 管理员准备数据库，以便基础结构管理员不必在 SQL server 上获得任何高级权限。</span><span class="sxs-lookup"><span data-stu-id="4274f-118">The result of the scripts is to allow SQL administrators to prepare the database so that the infrastructure administrators do not have to be granted any advanced rights on the SQL server.</span></span> <span data-ttu-id="4274f-119">这在安全策略将禁止此操作的环境中非常重要。</span><span class="sxs-lookup"><span data-stu-id="4274f-119">This is important in environments where security policies would prohibit this.</span></span>

### <span data-ttu-id="4274f-120">SQL 数据库创建过程</span><span class="sxs-lookup"><span data-stu-id="4274f-120">SQL Database Creation Process</span></span>

<span data-ttu-id="4274f-121">SQL 脚本允许 SQL 管理员创建所需的数据库，还可以设置 App-v 管理员成功安装和管理环境的权限。</span><span class="sxs-lookup"><span data-stu-id="4274f-121">The SQL scripts allow for SQL administrators to create the required database and also set up the privileges for the App-V administrators to successfully install and manage the environment.</span></span> <span data-ttu-id="4274f-122">本文档后面列出了完成这些任务的步骤。</span><span class="sxs-lookup"><span data-stu-id="4274f-122">The steps for completing these tasks are listed later in this document.</span></span>

<span data-ttu-id="4274f-123">此过程将数据库创建和配置操作与实际的 App-v 安装分开。</span><span class="sxs-lookup"><span data-stu-id="4274f-123">This process separates the database creation and configuration actions from the actual App-V installation.</span></span>

**<span data-ttu-id="4274f-124">向 SQL 管理员提供的信息</span><span class="sxs-lookup"><span data-stu-id="4274f-124">Information to be provided to SQL administrators</span></span>**

-   <span data-ttu-id="4274f-125">将成为 App-v 管理员的广告组的名称</span><span class="sxs-lookup"><span data-stu-id="4274f-125">Name of AD group that is going to be the App-V admin’s</span></span>

-   <span data-ttu-id="4274f-126">将安装 app-v 管理服务器的服务器的名称</span><span class="sxs-lookup"><span data-stu-id="4274f-126">Name of the server where App-V Management Server will be installed</span></span>

**<span data-ttu-id="4274f-127">将返回给基础结构管理员的信息</span><span class="sxs-lookup"><span data-stu-id="4274f-127">Information to be returned to the Infrastructure administrators</span></span>**

-   <span data-ttu-id="4274f-128">数据库服务器或实例的名称和 App-v 数据库的名称</span><span class="sxs-lookup"><span data-stu-id="4274f-128">Name of the database server or instance and the name of the App-V database</span></span>

<span data-ttu-id="4274f-129">准备好数据库后，app-v 管理员无需 SQL 管理员权限即可运行 app-v 安装。</span><span class="sxs-lookup"><span data-stu-id="4274f-129">Once the database has been prepared, the App-V administrators can run the App-V installation without SQL administrator privileges.</span></span>

### <span data-ttu-id="4274f-130">使用 SQL 安装脚本</span><span class="sxs-lookup"><span data-stu-id="4274f-130">Using the SQL Setup Scripts</span></span>

**<span data-ttu-id="4274f-131">要求</span><span class="sxs-lookup"><span data-stu-id="4274f-131">Requirements</span></span>**

<span data-ttu-id="4274f-132">下表列出了使用位于所选提取位置根目录下的 support\\createdb 文件夹中的脚本的要求。</span><span class="sxs-lookup"><span data-stu-id="4274f-132">The following is a list of requirements for using the scripts which are located in the support\\createdb folder at the root of the selected extract location.</span></span>

-   <span data-ttu-id="4274f-133">必须将脚本复制到计算机上将运行的计算机上的可写位置（请确保在复制这些脚本后删除这些脚本中的 read read 属性），并且必须在该计算机上加载 SQL 客户端工具（仅在本地计算机上运行示例批处理文件时才需要 osql）。</span><span class="sxs-lookup"><span data-stu-id="4274f-133">Scripts must be copied to a writeable location on the computer where they will be run (be sure to remove the read only attribute from these scripts after they have been copied) and SQL client tools must be loaded on that computer (osql is only required for running the sample batch files on the local computer).</span></span>

-   <span data-ttu-id="4274f-134">SQL Server 必须支持 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="4274f-134">The SQL Server must support Windows Authentication.</span></span>

-   <span data-ttu-id="4274f-135">确保 SQL Server 实例和 SQL 代理服务正在运行。</span><span class="sxs-lookup"><span data-stu-id="4274f-135">Ensure that the SQL Server Instance and SQL Agent Service are running.</span></span>

-   <span data-ttu-id="4274f-136">使用将在其中完成脚本的计算机上的 SQL 管理员（sysadmin）登录的域帐户登录。</span><span class="sxs-lookup"><span data-stu-id="4274f-136">Log on with a domain account that is a SQL administrator (sysadmin) on the computer where the scripts will be done.</span></span>

<span data-ttu-id="4274f-137">脚本在登录用户的域凭据下运行。</span><span class="sxs-lookup"><span data-stu-id="4274f-137">The scripts runs under the logged-on user’s domain credentials.</span></span>

**<span data-ttu-id="4274f-138">使用 SQL 脚本创建数据库</span><span class="sxs-lookup"><span data-stu-id="4274f-138">Database Creation Using SQL Scripts</span></span>**

**<span data-ttu-id="4274f-139">由 SQL 管理员执行的任务：</span><span class="sxs-lookup"><span data-stu-id="4274f-139">Tasks to be performed by SQL administrators:</span></span>**

1.  <span data-ttu-id="4274f-140">将 support\\createdb 文件夹中包含的脚本从所选提取位置的根复制到将运行脚本的计算机。</span><span class="sxs-lookup"><span data-stu-id="4274f-140">Copy the scripts contained in the support\\createdb folder from the root of the selected extract location to the computer where the scripts will be run.</span></span> <span data-ttu-id="4274f-141">以下文件是脚本正常运行所必需的，并且必须按照下面提供的顺序进行调用。</span><span class="sxs-lookup"><span data-stu-id="4274f-141">The following files are required for the scripts to run properly and must be called in the order presented below.</span></span>

    -   <span data-ttu-id="4274f-142">数据库 .sql</span><span class="sxs-lookup"><span data-stu-id="4274f-142">database.sql</span></span>

    -   <span data-ttu-id="4274f-143">角色 .sql</span><span class="sxs-lookup"><span data-stu-id="4274f-143">roles.sql</span></span>

    -   <span data-ttu-id="4274f-144">表 \ _CODES .sql</span><span class="sxs-lookup"><span data-stu-id="4274f-144">table\_CODES.sql</span></span>

    -   <span data-ttu-id="4274f-145">函数 \ _before \ _tables .sql</span><span class="sxs-lookup"><span data-stu-id="4274f-145">functions\_before\_tables.sql</span></span>

    -   <span data-ttu-id="4274f-146">表 .sql</span><span class="sxs-lookup"><span data-stu-id="4274f-146">tables.sql</span></span>

    -   <span data-ttu-id="4274f-147">函数 .sql</span><span class="sxs-lookup"><span data-stu-id="4274f-147">functions.sql</span></span>

    -   <span data-ttu-id="4274f-148">视图 .sql</span><span class="sxs-lookup"><span data-stu-id="4274f-148">views.sql</span></span>

    -   <span data-ttu-id="4274f-149">过程 .sql</span><span class="sxs-lookup"><span data-stu-id="4274f-149">procedures.sql</span></span>

    -   <span data-ttu-id="4274f-150">trigger。 sql</span><span class="sxs-lookup"><span data-stu-id="4274f-150">triggers.sql</span></span>

    -   <span data-ttu-id="4274f-151">数据 \ _codes .sql</span><span class="sxs-lookup"><span data-stu-id="4274f-151">data\_codes.sql</span></span>

    -   <span data-ttu-id="4274f-152">数据 \ _messages .sql</span><span class="sxs-lookup"><span data-stu-id="4274f-152">data\_messages.sql</span></span>

    -   <span data-ttu-id="4274f-153">数据 \ _defaults .sql</span><span class="sxs-lookup"><span data-stu-id="4274f-153">data\_defaults.sql</span></span>

    -   <span data-ttu-id="4274f-154">警报 \ _jobs</span><span class="sxs-lookup"><span data-stu-id="4274f-154">alerts\_jobs.sql</span></span>

    -   <span data-ttu-id="4274f-155">dbversion</span><span class="sxs-lookup"><span data-stu-id="4274f-155">dbversion.sql</span></span>

2.  <span data-ttu-id="4274f-156">查看和修改文件（如有必要） `database.sql` 。</span><span class="sxs-lookup"><span data-stu-id="4274f-156">Review and modify, if necessary, the `database.sql` file.</span></span> <span data-ttu-id="4274f-157">默认设置将把数据库命名为 "APPVIRTDB"。</span><span class="sxs-lookup"><span data-stu-id="4274f-157">The default settings will name the database “APPVIRTDB.”</span></span>

    -   <span data-ttu-id="4274f-158">如果需要 `APPVIRTDB` `database name` ，请将使用的实例替换为将使用的。</span><span class="sxs-lookup"><span data-stu-id="4274f-158">If necessary replace instances of `APPVIRTDB` with the `database name` that will be used.</span></span>

    -   <span data-ttu-id="4274f-159">`FILENAME`在脚本中修改将在其中创建数据库的 SQL Server 的相应路径的属性。</span><span class="sxs-lookup"><span data-stu-id="4274f-159">Modify the `FILENAME` property in the script with the appropriate path for the SQL Server where the database will be created.</span></span>

3.  <span data-ttu-id="4274f-160">如有必要，请查看并修改 `database name [APPVIRTDB]` `roles.sql` 数据库 .sql 文件中使用的文件中的。</span><span class="sxs-lookup"><span data-stu-id="4274f-160">Review and modify, if necessary, the `database name [APPVIRTDB]` in the `roles.sql` file that was used in the database.sql file.</span></span>

****

### <span data-ttu-id="4274f-161">如何使用批处理文件自动化进程的示例</span><span class="sxs-lookup"><span data-stu-id="4274f-161">Example of how to automate the process using batch files</span></span>

<span data-ttu-id="4274f-162">如果使用，则提供的两个示例批处理文件按以下方式运行 SQL 脚本：</span><span class="sxs-lookup"><span data-stu-id="4274f-162">If used, the two sample batch files provided run the SQL scripts in the following manner:</span></span>

1.  **<span data-ttu-id="4274f-163">Create\_schema.bat （1）</span><span class="sxs-lookup"><span data-stu-id="4274f-163">Create\_schema.bat (1)</span></span>**

    -   <span data-ttu-id="4274f-164">数据库 .sql</span><span class="sxs-lookup"><span data-stu-id="4274f-164">database.sql</span></span>

    -   <span data-ttu-id="4274f-165">角色 .sql</span><span class="sxs-lookup"><span data-stu-id="4274f-165">roles.sql</span></span>

2.  **<span data-ttu-id="4274f-166">Create\_tables.bat （2）</span><span class="sxs-lookup"><span data-stu-id="4274f-166">Create\_tables.bat (2)</span></span>**

    -   <span data-ttu-id="4274f-167">表 \ _CODES .sql</span><span class="sxs-lookup"><span data-stu-id="4274f-167">table\_CODES.sql</span></span>

    -   <span data-ttu-id="4274f-168">函数 \ _before \ _tables .sql</span><span class="sxs-lookup"><span data-stu-id="4274f-168">functions\_before\_tables.sql</span></span>

    -   <span data-ttu-id="4274f-169">表 .sql</span><span class="sxs-lookup"><span data-stu-id="4274f-169">tables.sql</span></span>

    -   <span data-ttu-id="4274f-170">函数 .sql</span><span class="sxs-lookup"><span data-stu-id="4274f-170">functions.sql</span></span>

    -   <span data-ttu-id="4274f-171">视图 .sql</span><span class="sxs-lookup"><span data-stu-id="4274f-171">views.sql</span></span>

    -   <span data-ttu-id="4274f-172">过程 .sql</span><span class="sxs-lookup"><span data-stu-id="4274f-172">procedures.sql</span></span>

    -   <span data-ttu-id="4274f-173">trigger。 sql</span><span class="sxs-lookup"><span data-stu-id="4274f-173">triggers.sql</span></span>

    -   <span data-ttu-id="4274f-174">数据 \ _codes .sql</span><span class="sxs-lookup"><span data-stu-id="4274f-174">data\_codes.sql</span></span>

    -   <span data-ttu-id="4274f-175">数据 \ _messages .sql</span><span class="sxs-lookup"><span data-stu-id="4274f-175">data\_messages.sql</span></span>

    -   <span data-ttu-id="4274f-176">数据 \ _defaults .sql</span><span class="sxs-lookup"><span data-stu-id="4274f-176">data\_defaults.sql</span></span>

    -   <span data-ttu-id="4274f-177">警报 \ _jobs</span><span class="sxs-lookup"><span data-stu-id="4274f-177">alerts\_jobs.sql</span></span>

    -   <span data-ttu-id="4274f-178">dbversion</span><span class="sxs-lookup"><span data-stu-id="4274f-178">dbversion.sql</span></span>

**<span data-ttu-id="4274f-179">注意</span><span class="sxs-lookup"><span data-stu-id="4274f-179">Note</span></span>**  
<span data-ttu-id="4274f-180">必须仔细考虑修改脚本时必须采取的措施，并且只能由具有相应知识的人执行。</span><span class="sxs-lookup"><span data-stu-id="4274f-180">Careful consideration when modifying the scripts must be taken and should only be done by someone with the appropriate knowledge.</span></span> <span data-ttu-id="4274f-181">此外，仅显示以下内容的示例文件应更改： **create\_schema.bat**、 **create\_tables.bat**、 **.sql**和**roles**。</span><span class="sxs-lookup"><span data-stu-id="4274f-181">Also, of the sample files presented only the following should be changed: **create\_schema.bat**, **create\_tables.bat**, **database.sql**, and **roles.sql**.</span></span> <span data-ttu-id="4274f-182">不应以任何方式修改所有其他文件，因为这可能会导致数据库不正确地创建，这将导致安装 App-v 服务失败。</span><span class="sxs-lookup"><span data-stu-id="4274f-182">All other files should not be modified in any way as this could cause the database to be created incorrectly, which will lead to the failure of App-V services to be installed.</span></span>



<span data-ttu-id="4274f-183">两个示例批处理文件必须放置在计算机上复制到其他 SQL 脚本的同一目录中。</span><span class="sxs-lookup"><span data-stu-id="4274f-183">The two sample batch files must be placed in the same directory where the rest of the SQL scripts were copied to on the computer.</span></span>

1.  <span data-ttu-id="4274f-184">运行示例**create\_schema.bat**文件以创建数据库。</span><span class="sxs-lookup"><span data-stu-id="4274f-184">Run the sample **create\_schema.bat** file to create the database.</span></span> <span data-ttu-id="4274f-185">此脚本将需要几秒钟才能完成，不应被打断。</span><span class="sxs-lookup"><span data-stu-id="4274f-185">This script will take several seconds to complete and should not be interrupted.</span></span>

    -   <span data-ttu-id="4274f-186">从将其复制到的目录运行 "创建 schema.bat" 文件。</span><span class="sxs-lookup"><span data-stu-id="4274f-186">Run the create schema.bat file from the directory where it was copied to.</span></span> <span data-ttu-id="4274f-187">语法为： "Create\_schema.bat `SQLSERVERNAME` "</span><span class="sxs-lookup"><span data-stu-id="4274f-187">Syntax is: “Create\_schema.bat `SQLSERVERNAME`”</span></span>

        ![AppV46SQLcreatebat](images/appv46sqlcreatebat.bmp)

    -   <span data-ttu-id="4274f-189">如果此脚本在创建新的 "APPVIRTDB" 数据库期间失败，请按指示的说明检查日志以更正此问题。</span><span class="sxs-lookup"><span data-stu-id="4274f-189">If this script fails during the creation of the new “APPVIRTDB” database, check the log as indicated to correct the issue.</span></span> <span data-ttu-id="4274f-190">有必要删除部分运行脚本创建的数据库，以确保后续的尝试将正常工作。</span><span class="sxs-lookup"><span data-stu-id="4274f-190">It will be necessary to delete the database that was created with a partial running of the scripts in order to ensure that subsequent attempts will work properly.</span></span>

2.  <span data-ttu-id="4274f-191">运行 `create_tables.bat` 文件以在数据库中创建表。</span><span class="sxs-lookup"><span data-stu-id="4274f-191">Run the `create_tables.bat` file to create the tables in the database.</span></span> <span data-ttu-id="4274f-192">此脚本将需要几秒钟才能完成，不应被打断。</span><span class="sxs-lookup"><span data-stu-id="4274f-192">This script will take several seconds to complete and should not be interrupted.</span></span>

    -   <span data-ttu-id="4274f-193">从复制文件的目录运行 create\_tables.bat 文件。</span><span class="sxs-lookup"><span data-stu-id="4274f-193">Run the create\_tables.bat file from the directory where it was copied.</span></span> <span data-ttu-id="4274f-194">语法为： "create\_tables.bat `SQLSERVERNAME DBNAME` "</span><span class="sxs-lookup"><span data-stu-id="4274f-194">Syntax is: “create\_tables.bat `SQLSERVERNAME DBNAME`”</span></span>

        ![app-v 4.6 sql create\-table.bat](images/appv46sqlcreate-tablebat.gif)

        <span data-ttu-id="4274f-196">如果在创建表过程中脚本失败，请按指示的方式查看日志以更正此问题。</span><span class="sxs-lookup"><span data-stu-id="4274f-196">If the script fails during the creation of the tables, check the log as indicated to correct the issue.</span></span> <span data-ttu-id="4274f-197">必须先删除数据库并运行 create\_schema.bat，然后才能尝试在所有后续尝试上运行 create\_tables.bat 文件。</span><span class="sxs-lookup"><span data-stu-id="4274f-197">It will be necessary to delete the database and run create\_schema.bat before attempting to run the create\_tables.bat file on all subsequent attempts.</span></span>

### <span data-ttu-id="4274f-198">在 App-v 数据库上设置权限</span><span class="sxs-lookup"><span data-stu-id="4274f-198">Setting permissions on the App-V database</span></span>

<span data-ttu-id="4274f-199">需要在 SQL server 上创建以下帐户，并将特定权限和角色安装到新数据库中，以便安装、部署和持续管理 App-v 环境。</span><span class="sxs-lookup"><span data-stu-id="4274f-199">The following accounts will need to be created on the SQL server with specific permissions and roles to the new database for the installation, deployment and ongoing administration of the App-V environment.</span></span>

-   <span data-ttu-id="4274f-200">在 SQL Server 上创建 app-v 管理员组的登录和 "domain\\App-V Admins" 的 APPVIRTDB 数据库（其中 "域" 和 "App-v Admins" 将更改为反映你自己的环境），并将其添加到 SFTAdmin 和 SFTEveryone 数据库角色。</span><span class="sxs-lookup"><span data-stu-id="4274f-200">Create a login for the App-V administrators group on the SQL Server and the APPVIRTDB database for the “domain\\App-V Admins” (where “domain” and “App-V Admins” will be changed to reflect your own environment) and add them to the SFTAdmin and SFTEveryone database role.</span></span>

    ![app-v 4.6 sql 脚本设置权限和角色](images/appv46sqlscriptsetpermsroles.gif)

-   <span data-ttu-id="4274f-202">在全局级别授予此组 "查看任何定义" 权限（这允许 Microsoft Application Virtualization 管理服务器安装过程验证管理服务器登录是否已存在）。</span><span class="sxs-lookup"><span data-stu-id="4274f-202">Grant this group “VIEW ANY DEFINITION” permission at the global level (This allows the Microsoft Application Virtualization Management Server setup process to verify that the Management Server login already exists).</span></span> <span data-ttu-id="4274f-203">在 MS-SQL 2005 及更高版本下，已添加对 master 数据库中包含的元数据的访问限制。</span><span class="sxs-lookup"><span data-stu-id="4274f-203">Under MS-SQL 2005 and above access restrictions to the metadata contained in master.db were added.</span></span> <span data-ttu-id="4274f-204">在上一步中创建的用户默认情况下，不会拥有服务器安装所需的权限。</span><span class="sxs-lookup"><span data-stu-id="4274f-204">The user created in the previous step will by default not have the rights needed by the server installation.</span></span> <span data-ttu-id="4274f-205">打开以前创建的登录、登录属性-Securables 的属性 &gt; 。</span><span class="sxs-lookup"><span data-stu-id="4274f-205">Open the properties of the previously created login, Login Properties-&gt;Securables.</span></span> <span data-ttu-id="4274f-206">添加数据库实例，并为 "查看任何定义" 启用 "授权"，如下面的屏幕截图中所示。</span><span class="sxs-lookup"><span data-stu-id="4274f-206">Add the Database instance and enable “GRANT” for “View any definition” as shown in the screenshot below.</span></span>

    ![app-v 4.6 sql 脚本授予 perm 以查看任何定义](images/appv46sqlscriptviewanydef.gif)

-   <span data-ttu-id="4274f-208">将角色添加到在上一步中创建的登录的角色 \ _ASSIGNMENTS 表，以允许 App-v 管理员访问应用程序虚拟化管理控制台，角色 = "管理员" 和组 \ _ref = "domain\\App-V Admins" （其中，"域" 和 "App-v Admins" 将更改以反映你自己的环境）。</span><span class="sxs-lookup"><span data-stu-id="4274f-208">Add a role to the ROLE\_ASSIGNMENTS table for the login created in the previous step to allow App-V administrators access to the Application Virtualization Management Console, with role = “ADMIN” and group\_ref = “domain\\App-V Admins” (where “domain” and “App-V Admins” will be changed to reflect your own environment).</span></span>

    ![app-v 4.6 sql 脚本角色分配](images/appv46sqlscriptroleassign.gif)

-   <span data-ttu-id="4274f-210">为管理服务器创建 SQL Server 和 App-v 数据库的登录。</span><span class="sxs-lookup"><span data-stu-id="4274f-210">Create login for SQL Server and App-V database for the Management Server.</span></span> <span data-ttu-id="4274f-211">Microsoft Application Virtualization 管理服务器使用此帐户连接到数据存储，并且负责为流处理应用程序提供客户端请求。</span><span class="sxs-lookup"><span data-stu-id="4274f-211">This account is used by the Microsoft Application Virtualization Management Server to connect to the data store and is responsible for servicing client requests for streamed applications.</span></span> <span data-ttu-id="4274f-212">根据 SQL Server 和管理服务器的安装位置，有两个选项：</span><span class="sxs-lookup"><span data-stu-id="4274f-212">There are two options, depending on where the SQL Server and Management Server are to be installed:</span></span>

    1.  <span data-ttu-id="4274f-213">如果要在同一台计算机上安装管理服务器和 SQL Server，请为 NT AUTHORITY\\NETWORK 服务添加登录，并将其添加到 SFTUser 和 SFTEveryone 数据库角色。</span><span class="sxs-lookup"><span data-stu-id="4274f-213">If Management Server and SQL Server are going to be installed on the same computer, add a login for NT AUTHORITY\\NETWORK SERVICE and add it to the SFTUser and SFTEveryone database roles.</span></span>

    2.  <span data-ttu-id="4274f-214">如果管理服务器和 SQL Server 要安装在不同的计算机上，请为 "domain\\App-V Server Name $" 添加登录名（其中，"App-v Server Name" 是安装 App-v 管理服务器的服务器的名称），并将其添加到 SFTUser 和 SFTEveryone 数据库角色。</span><span class="sxs-lookup"><span data-stu-id="4274f-214">If the Management Server and SQL Server are to be installed on different computers, add a login for “domain\\App-V Server Name$” (where “App-V Server Name” is the name of the server where the App-V Management Server will be installed) and add it to the SFTUser and SFTEveryone database roles.</span></span>

-   <span data-ttu-id="4274f-215">在 SQL 窗口中打开 "查询" 窗口，然后运行以下 SQL：</span><span class="sxs-lookup"><span data-stu-id="4274f-215">Open the query window on the SQL window and run the following SQL:</span></span>

    ``` syntax
    USE APPVIRTDB
    GRANT ALTER ON ROLE::SFTuser TO “domain\App-V Admins”
    ```

    <span data-ttu-id="4274f-216">其中，APPVIRTDB 是在上一步中在 SQL Server 上创建的 app-v 数据库的名称，并且要执行应用 v 服务器安装的用户需要是 "domain\\App-V Admins" 的成员（其中，"domain" 和 "App-v Admins" 将更改为反映你自己的环境）。</span><span class="sxs-lookup"><span data-stu-id="4274f-216">Where the APPVIRTDB is the name of the App-V Database created on the SQL Server in the previous step, and the user who is going to do the install of the App-v server needs to be a member of “domain\\App-V Admins” (where “domain” and “App-V Admins” will be changed to reflect your own environment).</span></span>

### <span data-ttu-id="4274f-217">由基础结构管理员执行的任务</span><span class="sxs-lookup"><span data-stu-id="4274f-217">Tasks to be performed by the Infrastructure administrators</span></span>

1.  <span data-ttu-id="4274f-218">"App-V 管理员" 组中的管理员应安装 app-v。</span><span class="sxs-lookup"><span data-stu-id="4274f-218">Administrator in the “App-V Admins” group should install App-V.</span></span>

    <span data-ttu-id="4274f-219">使用 SQL 管理员的信息选择在前面的步骤中创建的 SQL Server 和数据库。</span><span class="sxs-lookup"><span data-stu-id="4274f-219">Use information from the SQL administrators for selecting the SQL Server and database created in the previous steps.</span></span>

2.  <span data-ttu-id="4274f-220">"App-v Admins" 组中的管理员登录到应用程序虚拟化管理控制台并从管理控制台中删除以下对象。</span><span class="sxs-lookup"><span data-stu-id="4274f-220">Administrator in the “App-V Admins” group logs in to Application Virtualization Management Console and deletes the following objects from the Management Console.</span></span>

    **<span data-ttu-id="4274f-221">警告</span><span class="sxs-lookup"><span data-stu-id="4274f-221">Warning</span></span>**  
    <span data-ttu-id="4274f-222">这是必需的，因为传统安装会在您针对现有数据库运行安装时填充数据库中未填充的特定记录。</span><span class="sxs-lookup"><span data-stu-id="4274f-222">This is required as the traditional setup populates certain records in the database that are not populated if you run the install against an already existing database.</span></span> <span data-ttu-id="4274f-223">删除以下对象：</span><span class="sxs-lookup"><span data-stu-id="4274f-223">Delete the following objects:</span></span>

    -   <span data-ttu-id="4274f-224">"服务器组"、"默认服务器组"、"删除" 应用程序虚拟化管理服务器 "下的" 删除 "</span><span class="sxs-lookup"><span data-stu-id="4274f-224">Under “Server Groups,” “Default Server Group,” delete “Application Virtualization Management Server”</span></span>

    -   <span data-ttu-id="4274f-225">在 "服务器组" 下，删除 "默认服务器组"</span><span class="sxs-lookup"><span data-stu-id="4274f-225">Under “Server Groups,” delete “Default Server Group”</span></span>

    -   <span data-ttu-id="4274f-226">在 "提供商策略" 下，删除 "默认提供商"</span><span class="sxs-lookup"><span data-stu-id="4274f-226">Under “Provider Policies,” delete “Default Provider”</span></span>



3.  <span data-ttu-id="4274f-227">然后，app-v 管理员组中的管理员应创建：</span><span class="sxs-lookup"><span data-stu-id="4274f-227">Administrator in the App-V admins group should then create:</span></span>

    -   <span data-ttu-id="4274f-228">在 "提供商策略" 下，创建新的提供商策略</span><span class="sxs-lookup"><span data-stu-id="4274f-228">Under “Provider Policies,” create a New Provider Policy</span></span>

    -   <span data-ttu-id="4274f-229">创建 "默认服务器组"</span><span class="sxs-lookup"><span data-stu-id="4274f-229">Create a “Default Server Group”</span></span>

        **<span data-ttu-id="4274f-230">注意</span><span class="sxs-lookup"><span data-stu-id="4274f-230">Note</span></span>**  
        <span data-ttu-id="4274f-231">您必须创建一个 "默认服务器" 组，即使您不会使用。</span><span class="sxs-lookup"><span data-stu-id="4274f-231">You must create a “Default Server” group even if you will not be used.</span></span> <span data-ttu-id="4274f-232">服务器安装程序仅在尝试添加服务器时查找 "默认服务器组"。</span><span class="sxs-lookup"><span data-stu-id="4274f-232">The server installer only looks for the "Default Server Group" when trying to add the server.</span></span>  <span data-ttu-id="4274f-233">如果没有 "默认服务器组"，安装将失败。</span><span class="sxs-lookup"><span data-stu-id="4274f-233">If there is no "Default Server Group" then the installation will fail.</span></span> <span data-ttu-id="4274f-234">如果你计划使用不是默认设置的服务器组，并且你计划将后续的 App-v 管理服务器添加到你的基础结构，则只需保留 "默认服务器组"。</span><span class="sxs-lookup"><span data-stu-id="4274f-234">If you plan on using server groups other than the default that is fine, it’s just necessary to retain the "Default Server Group" if you plan on adding subsequent App-V Management Servers to your infrastructure.</span></span>



~~~
-   Assign the App-V Users Group to the New Provider Policy created above

-   Under “Server Groups,” create a New Server Group, specifying the New Provider Policy

-   Under the New Server group, create a New Application Virtualization Management Server

    **Important**  
    Do not restart the service before completing all of the above steps!



-   Administrator restarts the Application Virtualization Management Server service.
~~~

## <span data-ttu-id="4274f-235">总结</span><span class="sxs-lookup"><span data-stu-id="4274f-235">Conclusion</span></span>


<span data-ttu-id="4274f-236">总之，本文档中的信息允许管理员使用 SQL 管理员开发适用于组织中的安全和管理划分的部署路径。</span><span class="sxs-lookup"><span data-stu-id="4274f-236">In conclusion, the information in this document allows an administrator to work with the SQL administrators to develop a deployment path that works for the security and administrative divisions in an organization.</span></span> <span data-ttu-id="4274f-237">阅读此文档并测试记录的任务后，管理员应准备好在此类型的环境中实现其 App-v 基础结构。</span><span class="sxs-lookup"><span data-stu-id="4274f-237">After reading this document and testing the tasks documented, an administrator should be ready to implement their App-V infrastructure in this type of environment.</span></span>









