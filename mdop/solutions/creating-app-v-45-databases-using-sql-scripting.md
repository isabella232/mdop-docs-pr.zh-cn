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
# 使用 SQL 脚本创建 App-V 4.5 数据库


**此解决方案的用途是什么？** 管理应用程序虚拟化（app-v）4.5 数据库的信息技术专业人员。

**本指南如何帮助你？** 本解决方案介绍并介绍在管理员安装对 SQL Server 不具有 "sysadmin" 权限时，安装 Microsoft Application Virtualization 服务器的过程。

## 概述


安装 Microsoft Application Virtualization 4.5 （App-v）的挑战之一是，安装程序假定安装服务器功能的用户不仅是本地计算机管理员，还在将承载数据存储的 SQL server 上拥有 SQL 管理员权限。 此要求基于在安装过程中创建数据库以及相应的角色和权限这一事实。 但是，在大多数企业中，SQL server 与将要安装 app-v 的基础结构团队分开管理。 这些安全要求使 SQL 管理员有可能很难让基础结构管理员安装 app-v，从而获得足够的权限;同样，SQL 管理员将不具有为基础结构团队安装产品所需的权限。

当前，尝试安装 app-v 的管理员必须具有 SQL "sysadmin" 权限。 在以前版本的产品中，SQL 管理员允许 SQL 管理员创建临时 "sysadmin" 帐户或在安装过程中显示，以提供具有 "sysadmin" 权限的凭据。 在此版本中，脚本在发布产品中提供，供所有管理员在实施其基础结构时使用。

此白皮书将讨论安装需要划分为两个单独任务的方案：创建 SQL 数据库和安装 App-v server 功能。 SQL 管理员可以查看 SQL 脚本并进行修改以解决与其他数据库的任何冲突，或支持与其他工具的集成。 脚本的结果是允许 SQL 管理员准备数据库，以便基础结构管理员不必在 SQL server 上获得任何高级权限。 这在安全策略将禁止此操作的环境中非常重要。

### SQL 数据库创建过程

SQL 脚本允许 SQL 管理员创建所需的数据库，还可以设置 App-v 管理员成功安装和管理环境的权限。 本文档后面列出了完成这些任务的步骤。

此过程将数据库创建和配置操作与实际的 App-v 安装分开。

**向 SQL 管理员提供的信息**

-   将成为 App-v 管理员的广告组的名称

-   将安装 app-v 管理服务器的服务器的名称

**将返回给基础结构管理员的信息**

-   数据库服务器或实例的名称和 App-v 数据库的名称

准备好数据库后，app-v 管理员无需 SQL 管理员权限即可运行 app-v 安装。

### 使用 SQL 安装脚本

**要求**

下表列出了使用位于所选提取位置根目录下的 support\\createdb 文件夹中的脚本的要求。

-   必须将脚本复制到计算机上将运行的计算机上的可写位置（请确保在复制这些脚本后删除这些脚本中的 read read 属性），并且必须在该计算机上加载 SQL 客户端工具（仅在本地计算机上运行示例批处理文件时才需要 osql）。

-   SQL Server 必须支持 Windows 身份验证。

-   确保 SQL Server 实例和 SQL 代理服务正在运行。

-   使用将在其中完成脚本的计算机上的 SQL 管理员（sysadmin）登录的域帐户登录。

脚本在登录用户的域凭据下运行。

**使用 SQL 脚本创建数据库**

**由 SQL 管理员执行的任务：**

1.  将 support\\createdb 文件夹中包含的脚本从所选提取位置的根复制到将运行脚本的计算机。 以下文件是脚本正常运行所必需的，并且必须按照下面提供的顺序进行调用。

    -   数据库 .sql

    -   角色 .sql

    -   表 \ _CODES .sql

    -   函数 \ _before \ _tables .sql

    -   表 .sql

    -   函数 .sql

    -   视图 .sql

    -   过程 .sql

    -   trigger。 sql

    -   数据 \ _codes .sql

    -   数据 \ _messages .sql

    -   数据 \ _defaults .sql

    -   警报 \ _jobs

    -   dbversion

2.  查看和修改文件（如有必要） `database.sql` 。 默认设置将把数据库命名为 "APPVIRTDB"。

    -   如果需要 `APPVIRTDB` `database name` ，请将使用的实例替换为将使用的。

    -   `FILENAME`在脚本中修改将在其中创建数据库的 SQL Server 的相应路径的属性。

3.  如有必要，请查看并修改 `database name [APPVIRTDB]` `roles.sql` 数据库 .sql 文件中使用的文件中的。

****

### 如何使用批处理文件自动化进程的示例

如果使用，则提供的两个示例批处理文件按以下方式运行 SQL 脚本：

1.  **Create\_schema.bat （1）**

    -   数据库 .sql

    -   角色 .sql

2.  **Create\_tables.bat （2）**

    -   表 \ _CODES .sql

    -   函数 \ _before \ _tables .sql

    -   表 .sql

    -   函数 .sql

    -   视图 .sql

    -   过程 .sql

    -   trigger。 sql

    -   数据 \ _codes .sql

    -   数据 \ _messages .sql

    -   数据 \ _defaults .sql

    -   警报 \ _jobs

    -   dbversion

**注意**  
必须仔细考虑修改脚本时必须采取的措施，并且只能由具有相应知识的人执行。 此外，仅显示以下内容的示例文件应更改： **create\_schema.bat**、 **create\_tables.bat**、 **.sql**和**roles**。 不应以任何方式修改所有其他文件，因为这可能会导致数据库不正确地创建，这将导致安装 App-v 服务失败。



两个示例批处理文件必须放置在计算机上复制到其他 SQL 脚本的同一目录中。

1.  运行示例**create\_schema.bat**文件以创建数据库。 此脚本将需要几秒钟才能完成，不应被打断。

    -   从将其复制到的目录运行 "创建 schema.bat" 文件。 语法为： "Create\_schema.bat `SQLSERVERNAME` "

        ![AppV46SQLcreatebat](images/appv46sqlcreatebat.bmp)

    -   如果此脚本在创建新的 "APPVIRTDB" 数据库期间失败，请按指示的说明检查日志以更正此问题。 有必要删除部分运行脚本创建的数据库，以确保后续的尝试将正常工作。

2.  运行 `create_tables.bat` 文件以在数据库中创建表。 此脚本将需要几秒钟才能完成，不应被打断。

    -   从复制文件的目录运行 create\_tables.bat 文件。 语法为： "create\_tables.bat `SQLSERVERNAME DBNAME` "

        ![app-v 4.6 sql create\-table.bat](images/appv46sqlcreate-tablebat.gif)

        如果在创建表过程中脚本失败，请按指示的方式查看日志以更正此问题。 必须先删除数据库并运行 create\_schema.bat，然后才能尝试在所有后续尝试上运行 create\_tables.bat 文件。

### 在 App-v 数据库上设置权限

需要在 SQL server 上创建以下帐户，并将特定权限和角色安装到新数据库中，以便安装、部署和持续管理 App-v 环境。

-   在 SQL Server 上创建 app-v 管理员组的登录和 "domain\\App-V Admins" 的 APPVIRTDB 数据库（其中 "域" 和 "App-v Admins" 将更改为反映你自己的环境），并将其添加到 SFTAdmin 和 SFTEveryone 数据库角色。

    ![app-v 4.6 sql 脚本设置权限和角色](images/appv46sqlscriptsetpermsroles.gif)

-   在全局级别授予此组 "查看任何定义" 权限（这允许 Microsoft Application Virtualization 管理服务器安装过程验证管理服务器登录是否已存在）。 在 MS-SQL 2005 及更高版本下，已添加对 master 数据库中包含的元数据的访问限制。 在上一步中创建的用户默认情况下，不会拥有服务器安装所需的权限。 打开以前创建的登录、登录属性-Securables 的属性 &gt; 。 添加数据库实例，并为 "查看任何定义" 启用 "授权"，如下面的屏幕截图中所示。

    ![app-v 4.6 sql 脚本授予 perm 以查看任何定义](images/appv46sqlscriptviewanydef.gif)

-   将角色添加到在上一步中创建的登录的角色 \ _ASSIGNMENTS 表，以允许 App-v 管理员访问应用程序虚拟化管理控制台，角色 = "管理员" 和组 \ _ref = "domain\\App-V Admins" （其中，"域" 和 "App-v Admins" 将更改以反映你自己的环境）。

    ![app-v 4.6 sql 脚本角色分配](images/appv46sqlscriptroleassign.gif)

-   为管理服务器创建 SQL Server 和 App-v 数据库的登录。 Microsoft Application Virtualization 管理服务器使用此帐户连接到数据存储，并且负责为流处理应用程序提供客户端请求。 根据 SQL Server 和管理服务器的安装位置，有两个选项：

    1.  如果要在同一台计算机上安装管理服务器和 SQL Server，请为 NT AUTHORITY\\NETWORK 服务添加登录，并将其添加到 SFTUser 和 SFTEveryone 数据库角色。

    2.  如果管理服务器和 SQL Server 要安装在不同的计算机上，请为 "domain\\App-V Server Name $" 添加登录名（其中，"App-v Server Name" 是安装 App-v 管理服务器的服务器的名称），并将其添加到 SFTUser 和 SFTEveryone 数据库角色。

-   在 SQL 窗口中打开 "查询" 窗口，然后运行以下 SQL：

    ``` syntax
    USE APPVIRTDB
    GRANT ALTER ON ROLE::SFTuser TO “domain\App-V Admins”
    ```

    其中，APPVIRTDB 是在上一步中在 SQL Server 上创建的 app-v 数据库的名称，并且要执行应用 v 服务器安装的用户需要是 "domain\\App-V Admins" 的成员（其中，"domain" 和 "App-v Admins" 将更改为反映你自己的环境）。

### 由基础结构管理员执行的任务

1.  "App-V 管理员" 组中的管理员应安装 app-v。

    使用 SQL 管理员的信息选择在前面的步骤中创建的 SQL Server 和数据库。

2.  "App-v Admins" 组中的管理员登录到应用程序虚拟化管理控制台并从管理控制台中删除以下对象。

    **警告**  
    这是必需的，因为传统安装会在您针对现有数据库运行安装时填充数据库中未填充的特定记录。 删除以下对象：

    -   "服务器组"、"默认服务器组"、"删除" 应用程序虚拟化管理服务器 "下的" 删除 "

    -   在 "服务器组" 下，删除 "默认服务器组"

    -   在 "提供商策略" 下，删除 "默认提供商"



3.  然后，app-v 管理员组中的管理员应创建：

    -   在 "提供商策略" 下，创建新的提供商策略

    -   创建 "默认服务器组"

        **注意**  
        您必须创建一个 "默认服务器" 组，即使您不会使用。 服务器安装程序仅在尝试添加服务器时查找 "默认服务器组"。  如果没有 "默认服务器组"，安装将失败。 如果你计划使用不是默认设置的服务器组，并且你计划将后续的 App-v 管理服务器添加到你的基础结构，则只需保留 "默认服务器组"。



~~~
-   Assign the App-V Users Group to the New Provider Policy created above

-   Under “Server Groups,” create a New Server Group, specifying the New Provider Policy

-   Under the New Server group, create a New Application Virtualization Management Server

    **Important**  
    Do not restart the service before completing all of the above steps!



-   Administrator restarts the Application Virtualization Management Server service.
~~~

## 总结


总之，本文档中的信息允许管理员使用 SQL 管理员开发适用于组织中的安全和管理划分的部署路径。 阅读此文档并测试记录的任务后，管理员应准备好在此类型的环境中实现其 App-v 基础结构。









