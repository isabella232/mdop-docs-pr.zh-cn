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
# 如何使用 SQL 脚本部署 App-V 数据库

按照以下说明使用 SQL 脚本（而不是 Windows 安装程序）执行以下操作：

- 安装 app-v 5.1 数据库
- 将 app-v 数据库升级到更高版本

> [!NOTE]
> 如果您已经部署了 app-v 5.0 SP3 数据库，升级到 app-v 5.1 不需要 SQL 脚本。

## 如何使用 SQL 脚本安装 app-v 数据库

1. 在安装数据库脚本之前，请检查并保留 App-v 许可证条款的副本。 运行数据库脚本即已同意许可条款。 如果您不接受这些功能，则不应使用本软件。
1. 将**appv\_server\_setup.exe**从 app-v 版本媒体复制到临时位置。
1. 在命令提示符处，运行**appv\_server\_setup.exe**并指定用于提取数据库脚本的临时位置。

    示例： appv\_server\_setup.exe/layout c:\\ &lt; _临时位置路径_&gt;

1. 通过浏览找到您创建的临时位置，打开解压缩的**DatabaseScripts**文件夹，然后查看相应的 Readme.txt 文件，了解有关说明：

    | 数据库 | 要使用 Readme.txt 文件的位置 |
    |--|--|
    | 管理数据库 | ManagementDatabase 子文件夹 |
    | 报告数据库 | ReportingDatabase 子文件夹 |

> [!CAUTION]
> ManagementDatabase 子文件夹中的 readme.txt 文件已过期。 以下更新的自述文件中的信息是最新的，应该取代**DatabaseScripts**文件夹中提供的自述信息。

> [!IMPORTANT]
> 晚于 app-v 5.0 SP3 的 App-v 管理数据库的版本不需要 InsertVersionInfo 脚本。

应根据[知识库文章 3031340](https://support.microsoft.com/kb/3031340)中的**步骤 2**更新权限。 在 app-v 5.0 SP3 之后的 app-v 版本中不需要**步骤 1** 。

## 更新的管理数据库自述文件内容

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

## 已更新报告数据库自述文件内容

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

**遇到了 app-v 问题？** 使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相关主题

[部署 App-V 5.1 Server](deploying-the-app-v-51-server.md)

[如何部署 App-V 5.1 Server](how-to-deploy-the-app-v-51-server.md)
