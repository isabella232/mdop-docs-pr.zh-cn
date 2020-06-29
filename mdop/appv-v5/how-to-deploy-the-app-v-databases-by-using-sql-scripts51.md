---
title: 如何使用 SQL 脚本部署 App-V 数据库
description: 如何使用 SQL 脚本部署 App-V 数据库
author: dansimp
ms.assetid: 1183b1bc-d4d7-4914-a049-06e82bf2d96d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4695d105c1aa6732efb6b8ed05169cf29e7f972b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798462"
---
# <span data-ttu-id="bcc62-103">如何使用 SQL 脚本部署 App-V 数据库</span><span class="sxs-lookup"><span data-stu-id="bcc62-103">How to Deploy the App-V Databases by Using SQL Scripts</span></span>

<span data-ttu-id="bcc62-104">按照以下说明使用 SQL 脚本（而不是 Windows 安装程序）执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="bcc62-104">Use the following instructions to use SQL scripts, rather than the Windows Installer, to:</span></span>

- <span data-ttu-id="bcc62-105">安装 app-v 5.1 数据库</span><span class="sxs-lookup"><span data-stu-id="bcc62-105">Install the App-V 5.1 databases</span></span>
- <span data-ttu-id="bcc62-106">将 app-v 数据库升级到更高版本</span><span class="sxs-lookup"><span data-stu-id="bcc62-106">Upgrade the App-V databases to a later version</span></span>

> [!NOTE]
> <span data-ttu-id="bcc62-107">如果您已经部署了 app-v 5.0 SP3 数据库，升级到 app-v 5.1 不需要 SQL 脚本。</span><span class="sxs-lookup"><span data-stu-id="bcc62-107">If you have already deployed the App-V 5.0 SP3 database, the SQL scripts are not required to upgrade to App-V 5.1.</span></span>

## <span data-ttu-id="bcc62-108">如何使用 SQL 脚本安装 app-v 数据库</span><span class="sxs-lookup"><span data-stu-id="bcc62-108">How to install the App-V databases by using SQL scripts</span></span>

1. <span data-ttu-id="bcc62-109">在安装数据库脚本之前，请检查并保留 App-v 许可证条款的副本。</span><span class="sxs-lookup"><span data-stu-id="bcc62-109">Before you install the database scripts, review and keep a copy of the App-V license terms.</span></span> <span data-ttu-id="bcc62-110">运行数据库脚本即已同意许可条款。</span><span class="sxs-lookup"><span data-stu-id="bcc62-110">By running the database scripts, you are agreeing to the license terms.</span></span> <span data-ttu-id="bcc62-111">如果您不接受这些功能，则不应使用本软件。</span><span class="sxs-lookup"><span data-stu-id="bcc62-111">If you do not accept them, you should not use this software.</span></span>
1. <span data-ttu-id="bcc62-112">将**appv\_server\_setup.exe**从 app-v 版本媒体复制到临时位置。</span><span class="sxs-lookup"><span data-stu-id="bcc62-112">Copy the **appv\_server\_setup.exe** from the App-V release media to a temporary location.</span></span>
1. <span data-ttu-id="bcc62-113">在命令提示符处，运行**appv\_server\_setup.exe**并指定用于提取数据库脚本的临时位置。</span><span class="sxs-lookup"><span data-stu-id="bcc62-113">From a command prompt, run **appv\_server\_setup.exe** and specify a temporary location for extracting the database scripts.</span></span>

    <span data-ttu-id="bcc62-114">示例： appv\_server\_setup.exe/layout c:\\ &lt; _临时位置路径_&gt;</span><span class="sxs-lookup"><span data-stu-id="bcc62-114">Example: appv\_server\_setup.exe /layout c:\\&lt;_temporary location path_&gt;</span></span>

1. <span data-ttu-id="bcc62-115">通过浏览找到您创建的临时位置，打开解压缩的**DatabaseScripts**文件夹，然后查看相应的 Readme.txt 文件，了解有关说明：</span><span class="sxs-lookup"><span data-stu-id="bcc62-115">Browse to the temporary location that you created, open the extracted **DatabaseScripts** folder, and review the appropriate Readme.txt file for instructions:</span></span>

    | <span data-ttu-id="bcc62-116">数据库</span><span class="sxs-lookup"><span data-stu-id="bcc62-116">Database</span></span> | <span data-ttu-id="bcc62-117">要使用 Readme.txt 文件的位置</span><span class="sxs-lookup"><span data-stu-id="bcc62-117">Location of Readme.txt file to use</span></span> |
    |--|--|
    | <span data-ttu-id="bcc62-118">管理数据库</span><span class="sxs-lookup"><span data-stu-id="bcc62-118">Management database</span></span> | <span data-ttu-id="bcc62-119">ManagementDatabase 子文件夹</span><span class="sxs-lookup"><span data-stu-id="bcc62-119">ManagementDatabase subfolder</span></span> |
    | <span data-ttu-id="bcc62-120">报告数据库</span><span class="sxs-lookup"><span data-stu-id="bcc62-120">Reporting database</span></span> | <span data-ttu-id="bcc62-121">ReportingDatabase 子文件夹</span><span class="sxs-lookup"><span data-stu-id="bcc62-121">ReportingDatabase subfolder</span></span> |

> [!CAUTION]
> <span data-ttu-id="bcc62-122">ManagementDatabase 子文件夹中的 readme.txt 文件已过期。</span><span class="sxs-lookup"><span data-stu-id="bcc62-122">The readme.txt file in the ManagementDatabase subfolder is out of date.</span></span> <span data-ttu-id="bcc62-123">以下更新的自述文件中的信息是最新的，应该取代**DatabaseScripts**文件夹中提供的自述信息。</span><span class="sxs-lookup"><span data-stu-id="bcc62-123">The information in the updated readme files below is the most current and should supersede the readme information provided in the **DatabaseScripts** folders.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bcc62-124">晚于 app-v 5.0 SP3 的 App-v 管理数据库的版本不需要 InsertVersionInfo 脚本。</span><span class="sxs-lookup"><span data-stu-id="bcc62-124">The InsertVersionInfo.sql script is not required for versions of the App-V management database later than App-V 5.0 SP3.</span></span>

<span data-ttu-id="bcc62-125">应根据[知识库文章 3031340](https://support.microsoft.com/kb/3031340)中的**步骤 2**更新权限。</span><span class="sxs-lookup"><span data-stu-id="bcc62-125">The Permissions.sql script should be updated according to **Step 2** in [KB article 3031340](https://support.microsoft.com/kb/3031340).</span></span> <span data-ttu-id="bcc62-126">在 app-v 5.0 SP3 之后的 app-v 版本中不需要**步骤 1** 。</span><span class="sxs-lookup"><span data-stu-id="bcc62-126">**Step 1** is not required for versions of App-V later than App-V 5.0 SP3.</span></span>

## <span data-ttu-id="bcc62-127">更新的管理数据库自述文件内容</span><span class="sxs-lookup"><span data-stu-id="bcc62-127">Updated management database README file content</span></span>

```plaintext
******************************************************************
Before you install and use the Application Virtualization Database Scripts you must:
1.Review the Microsoft Application Virtualization Server 5.0 license terms.
2.Print and retain a copy of the license terms for your records.
By running the Microsoft Application Virtualization Database Scripts you agree to such license terms.  If you do not accept them, do not use the software.
******************************************************************


Steps to install "AppVManagement" schema in SQL SERVER.


## PREREQUISITES:

 1. Review the installation package.  The following files MUST exist:

    SQL files
    ---------
    Database.sql
    CreateTables.sql
    CreateStoredProcs.sql
    UpdateTables.sql
    Permissions.sql

 2. Ensure the target SQL Server instance and SQL Server Agent service are running.

 3. If you are not running the scripts directly on the server, ensure the
    necessary SQL Server client software is installed and available from
    the specified location.  Specifically, the "osql" command must
##     be supported for these scripts to run.



## PREPARATION:

 1. Review the database.sql file and modify as necessary.  Although the
    defaults are likely sufficient, it is suggested that the following
    settings be reviewed:

    DATABASE - ensure name is satisfactory - default is "AppVManagement".

 2. Review the Permissions.sql file and provide all the necessary account information
    for setting up read and write access on the database. Note: Default settings
##     in the file will not work.



## INSTALLATION:

 1. Run the database.sql against the "master" database.  Your user
    credential must have the ability to create databases.
    This script will create the database.

 2. Run the following scripts against the "AppVManagement" database using the
    same account as above in order.

    CreateTables.sql
    CreateStoredProcs.sql
    UpdateTables.sql
##     Permissions.sql

```

## <span data-ttu-id="bcc62-128">已更新报告数据库自述文件内容</span><span class="sxs-lookup"><span data-stu-id="bcc62-128">Updated reporting database README file content</span></span>

```plaintext
******************************************************************
Before you install and use the Application Virtualization Database Scripts you must:
1.Review the Microsoft Application Virtualization Server 5.0 license terms.
2.Print and retain a copy of the license terms for your records.
By running the Microsoft Application Virtualization Database Scripts you agree to such license terms.  If you do not accept them, do not use the software.
******************************************************************

Steps to install "AppVReporting" schema in SQL SERVER.


## PREREQUISITES:

 1. Review the installation package.  The following files MUST exist:

    SQL files
    ---------
    Database.sql
    UpgradeDatabase.sql
    CreateTables.sql
    CreateReportingStoredProcs.sql
    CreateStoredProcs.sql
    CreateViews.sql
    InsertVersionInfo.sql
    Permissions.sql
    ScheduleReportingJob.sql

 2. Ensure the target SQL Server instance and SQL Server Agent service are running.

 3. If you are not running the scripts directly on the server, ensure the 
    necessary SQL Server client software is installed and executable from
    the location you have chosen.  Specifically, the "osql" command must
##     be supported for these scripts to run.



## PREPARATION:

 1. Review the database.sql file and modify as necessary.  Although the
    defaults are likely sufficient, it is suggested that the following
    settings be reviewed:

    DATABASE - ensure name is satisfactory - default is "AppVReporting".

 2. Review the Permissions.sql file and provide all the necessary account information
    for setting up read and write access on the database. Note: Default settings
    in the file will not work.

 3. Review the ScheduleReportingJob.sql file and make sure that the stored proc schedule
    time is acceptable. The default stored proc schedule time is at 12.01 AM (line 84). 
    If this time is not suitable, you can change this to a more suitable time. The time is
##     in the format HHMMSS.



## INSTALLATION:

 1. Run the database.sql against the "master" database.  Your user
    credential must have the ability to create databases.
    This script will create the database.

 2. If upgrading the database, run UpgradeDatabase.sql This will upgrade database schema.

 2. Run the following scripts against the "AppVReporting" database using the
    same account as above in order.

    CreateTables.sql
    CreateReportingStoredProcs.sql
    CreateStoredProcs.sql
    CreateViews.sql
    InsertVersionInfo.sql
    Permissions.sql
##     ScheduleReportingJob.sql

```

**<span data-ttu-id="bcc62-129">遇到了 app-v 问题？</span><span class="sxs-lookup"><span data-stu-id="bcc62-129">Got an App-V issue?</span></span>** <span data-ttu-id="bcc62-130">使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="bcc62-130">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="bcc62-131">相关主题</span><span class="sxs-lookup"><span data-stu-id="bcc62-131">Related topics</span></span>

[<span data-ttu-id="bcc62-132">部署 App-V 5.1 Server</span><span class="sxs-lookup"><span data-stu-id="bcc62-132">Deploying the App-V 5.1 Server</span></span>](deploying-the-app-v-51-server.md)

[<span data-ttu-id="bcc62-133">如何部署 App-V 5.1 Server</span><span class="sxs-lookup"><span data-stu-id="bcc62-133">How to Deploy the App-V 5.1 Server</span></span>](how-to-deploy-the-app-v-51-server.md)
