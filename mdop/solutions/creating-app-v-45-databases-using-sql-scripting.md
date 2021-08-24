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
ms.openlocfilehash: c119f1d43a70cce04dd6151697318f7cf6a8d1f2
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910587"
---
# <a name="creating-app-v-45-databases-using-sql-scripting"></a>使用 SQL 脚本创建 App-V 4.5 数据库


**Who此解决方案是否适用于？** 管理 Application Virtualization (App-V) 4.5 数据库的信息技术专业人员。

**本指南如何帮助你？** 此解决方案解释并记录当管理员安装时对安装过程没有"sysadmin"权限时安装 Microsoft Application Virtualization Server SQL Server。

## <a name="overview"></a>概述


安装 Microsoft Application Virtualization 4.5 (App-V) 的一个难题是，安装程序假定安装服务器功能的用户不仅将成为本地计算机管理员，而且对将承载数据存储的 SQL 服务器具有 SQL 管理员权限。 此要求基于这样一个事实，即数据库以及相应的角色和权限是在安装时创建的。 但是，在大多数企业中，SQL服务器独立于将安装 App-V 的基础结构团队进行管理。 这些安全要求会使管理员难以SQL为安装 App-V 的基础结构管理员授予足够的权限;同样，SQL管理员将没有为基础结构团队安装产品所需的权限。

目前，尝试安装 App-V 的管理员必须具有SQL"sysadmin"权限。 在以前版本的产品中，SQL 管理员允许安装程序创建临时"sysadmin"帐户或在安装过程中存在以提供具有"sysadmin"权限的凭据。 在此版本中，脚本在已发布的产品中提供，供所有管理员在实施其基础结构时使用。

本白皮书讨论需要将安装分为两个单独的任务的方案：创建 SQL 数据库和安装 App-V 服务器功能。 这些SQL管理员将能够查看 SQL 脚本并进行修改以解决与其他数据库的任何冲突，或者支持与其他工具集成。 脚本的结果是允许SQL管理员准备数据库，以便基础结构管理员不需要被授予对 SQL 服务器的任何高级权限。 在安全策略禁止这样做的环境中，这一点非常重要。

### <a name="sql-database-creation-process"></a>SQL 数据库创建过程

这些SQL脚本允许 SQL 管理员创建所需的数据库，并设置 App-V 管理员成功安装和管理环境的权限。 本文档稍后将列出完成这些任务的步骤。

此过程将数据库创建和配置操作与实际的 App-V 安装分开。

**要提供给管理员SQL的信息**

-   要成为 App-V 管理员的 AD 组的名称

-   将安装 App-V 管理服务器的服务器的名称

**要返回给基础结构管理员的信息**

-   应用程序或数据库服务器的名称以及 App-V 数据库的名称

准备好数据库后，App-V 管理员可以运行 App-V 安装，而无需SQL权限。

### <a name="using-the-sql-setup-scripts"></a>使用 SQL 安装程序脚本

**要求**

以下是使用位于所选提取位置根目录的 support\\createdb 文件夹中的脚本的要求列表。

-   必须将脚本复制到计算机上要运行脚本的可写位置 (确保在将脚本复制为) 后从这些脚本中删除只读属性) 并且必须在该计算机上加载 SQL 客户端工具 (只有在本地计算机) 上运行示例批处理文件时，才需要 osql。

-   此SQL Server必须支持Windows身份验证。

-   确保运行SQL Server实例SQL代理服务。

-   使用域帐户登录，该帐户是SQL执行 (的) 的 sysadmin 管理员帐户。

脚本在登录用户的域凭据下运行。

**使用脚本创建SQL数据库**

**由管理员执行SQL任务：**

1.  将 support\\createdb 文件夹中包含的脚本从所选提取位置的根目录复制到将运行脚本的计算机。 脚本正常运行需要以下文件，并且必须按下面显示的顺序调用这些文件。

    -   database.sql

    -   roles.sql

    -   table\_CODES.sql

    -   functions\_before\_tables.sql

    -   tables.sql

    -   functions.sql

    -   views.sql

    -   procedures.sql

    -   triggers.sql

    -   data\_codes.sql

    -   data\_messages.sql

    -   data\_defaults.sql

    -   alerts\_jobs.sql

    -   dbversion.sql

2.  检查并修改文件（ `database.sql` 如有必要）。 默认设置将数据库名称为"APPVIRTDB"。

    -   如有必要，将 的实例 `APPVIRTDB` 替换为 `database name` 将使用的 。

    -   使用将在其中创建数据库的脚本SQL Server `FILENAME` 相应的路径修改脚本中的 属性。

3.  如有必要，检查和修改 `database name [APPVIRTDB]` `roles.sql` 在 database.sql 文件中使用的 文件。

****

### <a name="example-of-how-to-automate-the-process-using-batch-files"></a>如何使用批处理文件自动执行此过程的示例

如果使用，提供的两个示例批处理文件SQL运行脚本：

1.  **Create\_schema.bat (1) **

    -   database.sql

    -   roles.sql

2.  **Create\_tables.bat (2) **

    -   table\_CODES.sql

    -   functions\_before\_tables.sql

    -   tables.sql

    -   functions.sql

    -   views.sql

    -   procedures.sql

    -   triggers.sql

    -   data\_codes.sql

    -   data\_messages.sql

    -   data\_defaults.sql

    -   alerts\_jobs.sql

    -   dbversion.sql

**注意**  
修改脚本时必须仔细考虑，并且只应由具有相应知识的人完成。 此外，应更改仅呈现以下内容的示例文件：create\_schema.bat、create\_tables.bat、database.sql 和**** **roles.sql** ****。 ** ** 不应以任何方式修改所有其他文件，因为这可能导致错误创建数据库，这可能会导致安装 App-V 服务失败。



这两个示例批处理文件必须放在计算机上将其余 SQL脚本复制到的目录中。

1.  运行示例 **create\_schema.bat** 文件以创建数据库。 此脚本需要几秒钟才能完成，并且不应中断。

    -   从复制到schema.bat目录中运行 create schema.bat 文件。 语法为 `SQLSERVERNAME` ："Create\_schema.bat"

        ![AppV46SQLcreatebat。](images/appv46sqlcreatebat.bmp)

    -   如果在新建"APPVIRTDB"数据库期间此脚本失败，请检查指示的日志以更正问题。 必须删除部分运行脚本创建的数据库，以确保后续尝试能够正常工作。

2.  运行 `create_tables.bat` 文件以在数据库中创建表。 此脚本需要几秒钟才能完成，并且不应中断。

    -   从create\_tables.bat目录中运行文件。 语法为 `SQLSERVERNAME DBNAME` ："create\_tables.bat"

        ![app-v 4.6 sql create\-table.bat。](images/appv46sqlcreate-tablebat.gif)

        如果在创建表期间脚本失败，请检查指示的日志以更正问题。 在尝试在所有后续尝试中运行 create\_schema.bat 之前，需要删除数据库并运行create\_tables.bat文件。

### <a name="setting-permissions-on-the-app-v-database"></a>设置对 App-V 数据库的权限

以下帐户将需要在 SQL 服务器上创建，这些帐户具有新数据库的特定权限和角色，才能安装、部署和持续管理 App-V 环境。

-   在 SQL Server 上为 App-V 管理员组创建登录名，为"domain\\App-V 管理员"创建 APPVIRTDB 数据库 (其中"域"和"App-V 管理员"将发生更改以反映您自己的环境) 并将其添加到 SFTAdmin 和 SFTEveryone 数据库角色。

    ![app-v 4.6 sql 脚本集权限和角色。](images/appv46sqlscriptsetpermsroles.gif)

-   在全局级别向此组授予"查看任何定义" (这允许 Microsoft Application Virtualization Management Server 安装过程验证管理服务器登录名) 。 在 MS-SQL 2005 及以上下添加了对 master.db 中包含的元数据的访问限制。 默认情况下，在上一步中创建的用户将没有服务器安装所需的权限。 打开以前创建的登录名的属性 Login Properties- &gt; Securables。 添加 Database 实例，并针对"查看任何定义"启用"GRANT"，如下面的屏幕截图所示。

    ![app-v 4.6 sql script grant perm for view any def.](images/appv46sqlscriptviewanydef.gif)

-   将角色添加到在上一步中创建的登录名的 ROLE\_ASSIGNMENTS 表中，以允许 App-V 管理员访问 Application Virtualization Management Console，角色为"ADMIN"，group\_ref = "domain\\App-V Admins" (其中"domain"和"App-V Admins"将发生更改以反映您自己的环境) 。

    ![app-v 4.6 sql 脚本角色分配。](images/appv46sqlscriptroleassign.gif)

-   为管理服务器SQL Server App-V 数据库创建登录名。 Microsoft Application Virtualization Management Server 使用该帐户连接到数据存储，并负责为流式处理应用程序的客户端请求提供服务。 有两个选项，具体取决于SQL Server服务器和管理服务器的安装位置：

    1.  如果管理服务器SQL Server将安装在同一计算机上，请添加 NT AUTHORITY\\NETWORK SERVICE 的登录名，并将其添加到 SFTUser 和 SFTEveryone 数据库角色。

    2.  如果要在不同计算机上安装管理服务器和 SQL Server，请为"domain\\App-V Server Name$"添加登录名 (其中"App-V 服务器名称"是安装 App-V 管理服务器的服务器的名称) 并将其添加到 SFTUser 和 SFTEveryone 数据库角色中。

-   打开查询窗口上的SQL，然后运行以下SQL：

    ``` syntax
    USE APPVIRTDB
    GRANT ALTER ON ROLE::SFTuser TO “domain\App-V Admins”
    ```

    其中 APPVIRTDB 是上一步中在 SQL Server 上创建的 App-V 数据库的名称，并且要安装 App-v 服务器的用户需要是"domain\\App-V Admins" (其中"domain"和"App-V Admins"将发生更改以反映您自己的环境) 。

### <a name="tasks-to-be-performed-by-the-infrastructure-administrators"></a>基础结构管理员要执行的任务

1.  "App-V 管理员"组的管理员应安装 App-V。

    使用来自管理员SQL，以选择SQL Server步骤中创建的数据库和数据库。

2.  "App-V 管理员"组的管理员登录到 Application Virtualization Management Console，然后从管理控制台中删除以下对象。

    **警告**  
    这是必填项，因为如果对已有的数据库运行安装，则传统安装程序会填充数据库中未填充的某些记录。 删除以下对象：

    -   在"服务器组"、"默认服务器组"下，删除"Application Virtualization Management Server"

    -   在"服务器组"下，删除"默认服务器组"

    -   在"提供程序策略"下，删除"默认提供程序"



3.  然后，App-V 管理员组的管理员应创建：

    -   在"提供程序策略"下，创建新的提供程序策略

    -   创建"默认服务器组"

        **注意**  
        即使不会使用，也必须创建"默认服务器"组。 服务器安装程序仅在尝试添加服务器时查找"默认服务器组"。  如果没有"默认服务器组"，则安装将失败。 如果计划使用非默认服务器组，则只需保留"默认服务器组"，如果计划将后续 App-V 管理服务器添加到基础结构中。



~~~
-   Assign the App-V Users Group to the New Provider Policy created above

-   Under “Server Groups,” create a New Server Group, specifying the New Provider Policy

-   Under the New Server group, create a New Application Virtualization Management Server

    **Important**  
    Do not restart the service before completing all of the above steps!



-   Administrator restarts the Application Virtualization Management Server service.
~~~

## <a name="conclusion"></a>总结


总之，通过本文档中的信息，管理员可以与 SQL 管理员合作，以开发适用于组织中安全和管理分区的部署路径。 在阅读本文档并测试记录的任务后，管理员应准备好在此类型的环境中实施其 App-V 基础结构。









