---
title: 如何使用脚本部署 App-V 5.1 Server
description: 如何使用脚本部署 App-V 5.1 Server
author: dansimp
ms.assetid: 15c33d7b-9b61-4dbc-8674-399bb33e5f7e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 03/20/2020
ms.openlocfilehash: 579ca685f677aaaa4f5ebb6ac8d2969fdcbe2cd2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798468"
---
# 如何使用脚本部署 App-V 5.1 Server

为了使用命令行成功完成**appv\_server\_setup.exe**服务器设置，必须指定和组合多个参数。

## 使用脚本安装 app-v 5.1 服务器

- 有关使用命令行安装 App-v 5.1 服务器的信息，请使用以下信息。

    > [!NOTE]
    > 通过键入以下命令，还可以使用命令行来访问下表中的信息： " **appv\_server\_setup.exe/？"**。

### 在本地计算机上安装管理服务器和管理数据库

以下参数对于 Microsoft SQL Server 的默认实例和自定义实例均有效：

- /MANAGEMENT_SERVER
- /MANAGEMENT_ADMINACCOUNT
- /MANAGEMENT_WEBSITE_NAME
- /MANAGEMENT_WEBSITE_PORT
- /DB_PREDEPLOY_MANAGEMENT
- /MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT
- /MANAGEMENT_DB_NAME

**示例：使用 Microsoft SQL Server 的自定义实例**

```dos
appv_server_setup.exe /QUIET /MANAGEMENT_SERVER /MANAGEMENT_ADMINACCOUNT="Domain\AdminGroup" /MANAGEMENT_WEBSITE_NAME="Microsoft AppV Management Service" /MANAGEMENT_WEBSITE_PORT="8080" /DB_PREDEPLOY_MANAGEMENT /MANAGEMENT_DB_CUSTOM_SQLINSTANCE="SqlInstanceName" /MANAGEMENT_DB_NAME="AppVManagement"
```

### 使用本地计算机上的现有管理数据库安装管理服务器

若要使用 Microsoft SQL Server 的默认实例，请使用以下参数（与自定义实例在*斜体*中的差异）：

- /MANAGEMENT_SERVER
- /MANAGEMENT_ADMINACCOUNT
- /MANAGEMENT_WEBSITE_NAME
- /MANAGEMENT_WEBSITE_PORT
- /EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL
- */EXISTING_MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT*
- /EXISTING_MANAGEMENT_DB_NAME

若要使用 Microsoft SQL Server 的自定义实例，请使用以下参数（以*斜体*的默认实例为差）：

- /MANAGEMENT_SERVER
- /MANAGEMENT_ADMINACCOUNT
- /MANAGEMENT_WEBSITE_NAME
- /MANAGEMENT_WEBSITE_PORT
- /EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL
- */EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE*
- /EXISTING_MANAGEMENT_DB_NAME

**示例：使用 Microsoft SQL Server 的自定义实例**

```dos
appv_server_setup.exe /QUIET /MANAGEMENT_SERVER /MANAGEMENT_ADMINACCOUNT="Domain\AdminGroup" /MANAGEMENT_WEBSITE_NAME="Microsoft AppV Management Service" /MANAGEMENT_WEBSITE_PORT="8080" /EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL /EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE ="SqlInstanceName" /EXISTING_MANAGEMENT_DB_NAME ="AppVManagement"
```

### 使用远程计算机上的现有管理数据库安装管理服务器

若要使用 Microsoft SQL Server 的默认实例，请使用以下参数（与自定义实例在*斜体*中的差异）：

- /MANAGEMENT_SERVER
- /MANAGEMENT_ADMINACCOUNT
- /MANAGEMENT_WEBSITE_NAME
- /MANAGEMENT_WEBSITE_PORT
- /EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME
- */EXISTING_MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT*
- /EXISTING_MANAGEMENT_DB_NAME

若要使用 Microsoft SQL Server 的自定义实例，请使用以下参数（在默认情况下以*斜体*为差异）：

- /MANAGEMENT_SERVER
- /MANAGEMENT_ADMINACCOUNT
- /MANAGEMENT_WEBSITE_NAME
- /MANAGEMENT_WEBSITE_PORT
- /EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME
- */EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE*
- /EXISTING_MANAGEMENT_DB_NAME

**示例：使用 Microsoft SQL Server 的自定义实例：**

```dos
appv_server_setup.exe /QUIET /MANAGEMENT_SERVER /MANAGEMENT_ADMINACCOUNT="Domain\AdminGroup" /MANAGEMENT_WEBSITE_NAME="Microsoft AppV Management Service" /MANAGEMENT_WEBSITE_PORT="8080" /EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME="SqlServermachine.domainName" /EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE ="SqlInstanceName" /EXISTING_MANAGEMENT_DB_NAME ="AppVManagement"
```

### 在同一台计算机上安装管理数据库和管理服务器

若要使用 Microsoft SQL Server 的默认实例，请使用以下参数（与自定义实例在*斜体*中的差异）：

- /DB_PREDEPLOY_MANAGEMENT
- */MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT*
- /MANAGEMENT_DB_NAME
- /MANAGEMENT_SERVER_MACHINE_USE_LOCAL
- /MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT

若要使用 Microsoft SQL Server 的自定义实例，请使用以下参数（在默认情况下以*斜体*为差异）：

- /DB_PREDEPLOY_MANAGEMENT
- */MANAGEMENT_DB_CUSTOM_SQLINSTANCE*
- /MANAGEMENT_DB_NAME
- /MANAGEMENT_SERVER_MACHINE_USE_LOCAL
- /MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT

**示例：使用 Microsoft SQL Server 的自定义实例**

```dos
appv_server_setup.exe /QUIET /DB_PREDEPLOY_MANAGEMENT /MANAGEMENT_DB_CUSTOM_SQLINSTANCE="SqlInstanceName" /MANAGEMENT_DB_NAME="AppVManagement" /MANAGEMENT_SERVER_MACHINE_USE_LOCAL /MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT="Domain\InstallAdminAccount"
```

### 在不同于管理服务器的计算机上安装管理数据库

若要使用 Microsoft SQL Server 的默认实例，请使用以下参数（与自定义实例在*斜体*中的差异）：

- /DB_PREDEPLOY_MANAGEMENT
- */MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT*
- /MANAGEMENT_DB_NAME
- /MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT
- /MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT

若要使用 Microsoft SQL Server 的自定义实例，请使用以下参数（在默认情况下以*斜体*为差异）：

- /DB_PREDEPLOY_MANAGEMENT
- */MANAGEMENT_DB_CUSTOM_SQLINSTANCE*
- /MANAGEMENT_DB_NAME
- /MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT
- /MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT

**示例：使用 Microsoft SQL Server 的自定义实例**

```dos
appv_server_setup.exe /QUIET /DB_PREDEPLOY_MANAGEMENT /MANAGEMENT_DB_CUSTOM_SQLINSTANCE="SqlInstanceName" /MANAGEMENT_DB_NAME="AppVManagement" /MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT="Domain\MachineAccount" /MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT="Domain\InstallAdminAccount"
```

### 安装发布服务器

若要使用 Microsoft SQL Server 的默认实例，请使用以下参数：

- /PUBLISHING_SERVER
- /PUBLISHING_MGT_SERVER
- /PUBLISHING_WEBSITE_NAME
- /PUBLISHING_WEBSITE_PORT

**示例：使用 Microsoft SQL Server 的自定义实例：**

```dos
appv_server_setup.exe /QUIET /PUBLISHING_SERVER /PUBLISHING_MGT_SERVER="http://ManagementServerName:ManagementPort" /PUBLISHING_WEBSITE_NAME="Microsoft AppV Publishing Service" /PUBLISHING_WEBSITE_PORT="8081"
```

### 在本地计算机上安装报表服务器和报告数据库

若要使用 Microsoft SQL Server 的默认实例，请使用以下参数（与自定义实例在*斜体*中的差异）：

- /REPORTING _SERVER
- /REPORTING _WEBSITE_NAME
- /REPORTING _WEBSITE_PORT
- /DB_PREDEPLOY_REPORTING
- */REPORTING _DB_SQLINSTANCE_USE_DEFAULT*
- /REPORTING _DB_NAME

若要使用 Microsoft SQL Server 的自定义实例，请使用以下参数（在默认情况下以*斜体*为差异）：

- /REPORTING _SERVER
- */REPORTING _ADMINACCOUNT*
- /REPORTING _WEBSITE_NAME
- /REPORTING _WEBSITE_PORT
- /DB_PREDEPLOY_REPORTING
- */REPORTING _DB_CUSTOM_SQLINSTANCE*
- /REPORTING _DB_NAME

**示例：使用 Microsoft SQL Server 的自定义实例：**

```dos
appv_server_setup.exe /QUIET /REPORTING_SERVER /REPORTING_WEBSITE_NAME="Microsoft AppV Reporting Service" /REPORTING_WEBSITE_PORT="8082" /DB_PREDEPLOY_REPORTING /REPORTING_DB_CUSTOM_SQLINSTANCE="SqlInstanceName" /REPORTING_DB_NAME="AppVReporting"
```

### 安装报告服务器并使用本地计算机上的现有报告数据库

若要使用 Microsoft SQL Server 的默认实例，请使用以下参数（与自定义实例在*斜体*中的差异）：

- /REPORTING _SERVER
- /REPORTING _WEBSITE_NAME
- /REPORTING _WEBSITE_PORT
- /EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL
- */EXISTING_REPORTING _DB_SQLINSTANCE_USE_DEFAULT*
- /EXISTING_REPORTING _DB_NAME

若要使用 Microsoft SQL Server 的自定义实例，请使用以下参数（在默认情况下以*斜体*为差异）：

- /REPORTING _SERVER
- */REPORTING _ADMINACCOUNT*
- /REPORTING _WEBSITE_NAME
- /REPORTING _WEBSITE_PORT
- /EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL
- */EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE*
- /EXISTING_REPORTING _DB_NAME

**示例：使用 Microsoft SQL Server 的自定义实例：**

```dos
appv_server_setup.exe /QUIET /REPORTING_SERVER /REPORTING_WEBSITE_NAME="Microsoft AppV Reporting Service" /REPORTING_WEBSITE_PORT="8082" /EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL /EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE="SqlInstanceName" /EXITING_REPORTING_DB_NAME="AppVReporting"
```

### 使用远程计算机上的现有报告数据库安装报告服务器

若要使用 Microsoft SQL Server 的默认实例，请使用以下参数（与自定义实例在*斜体*中的差异）：

- /REPORTING _SERVER
- /REPORTING _WEBSITE_NAME
- /REPORTING _WEBSITE_PORT
- /EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME
- */EXISTING_REPORTING _DB_SQLINSTANCE_USE_DEFAULT*
- /EXISTING_REPORTING _DB_NAME

若要使用 Microsoft SQL Server 的自定义实例，请使用以下参数（在默认情况下以*斜体*为差异）：

- /REPORTING _SERVER
- */REPORTING _ADMINACCOUNT*
- /REPORTING _WEBSITE_NAME
- /REPORTING _WEBSITE_PORT
- /EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME
- */EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE*
- /EXISTING_REPORTING _DB_NAME

**示例：使用 Microsoft SQL Server 的自定义实例：**

```dos
appv_server_setup.exe /QUIET /REPORTING_SERVER /REPORTING_WEBSITE_NAME="Microsoft AppV Reporting Service" /REPORTING_WEBSITE_PORT="8082" /EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME="SqlServerMachine.DomainName" /EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE="SqlInstanceName" /EXITING_REPORTING_DB_NAME="AppVReporting"
```

### 在报表服务器所在的同一台计算机上安装报告数据库

若要使用 Microsoft SQL Server 的默认实例，请使用以下参数（与自定义实例在*斜体*中的差异）：

- /DB_PREDEPLOY_REPORTING
- */REPORTING _DB_SQLINSTANCE_USE_DEFAULT*
- /REPORTING _DB_NAME
- /REPORTING_SERVER_MACHINE_USE_LOCAL
- /REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT

若要使用 Microsoft SQL Server 的自定义实例，请使用以下参数（在默认情况下以*斜体*为差异）：

- /DB_PREDEPLOY_REPORTING
- */REPORTING _DB_CUSTOM_SQLINSTANCE*
- /REPORTING _DB_NAME
- /REPORTING_SERVER_MACHINE_USE_LOCAL
- /REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT

**示例：使用 Microsoft SQL Server 的自定义实例：**

```dos
appv_server_setup.exe /QUIET /DB_PREDEPLOY_REPORTING /REPORTING_DB_CUSTOM_SQLINSTANCE="SqlInstanceName" /REPORTING_DB_NAME="AppVReporting" /REPORTING_SERVER_MACHINE_USE_LOCAL /REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT="Domain\InstallAdminAccount"
```

### 在不同于报告服务器的计算机上安装报告数据库

若要使用 Microsoft SQL Server 的默认实例，请使用以下参数（与自定义实例在*斜体*中的差异）：

- /DB_PREDEPLOY_REPORTING
- /REPORTING _DB_SQLINSTANCE_USE_DEFAULT
- /REPORTING _DB_NAME
- /REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT
- /REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT

若要使用 Microsoft SQL Server 的自定义实例，请使用以下参数（在默认情况下以*斜体*为差异）：

- /DB_PREDEPLOY_REPORTING
- /REPORTING _DB_CUSTOM_SQLINSTANCE
- /REPORTING _DB_NAME
- /REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT
- /REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT

**示例：使用 Microsoft SQL Server 的自定义实例：**

```dos
 appv_server_setup.exe /QUIET /DB_PREDEPLOY_REPORTING /REPORTING_DB_CUSTOM_SQLINSTANCE="SqlInstanceName" /REPORTING_DB_NAME="AppVReporting" /REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT="Domain\MachineAccount" /REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT="Domain\InstallAdminAccount"
```

### 参数定义

#### 常规参数

| 参数 | 信息 |
|--|--|
| /QUIET | 指定静默安装。 |
| /UNINSTALL | 指定卸载。 |
| /LAYOUT | 指定布局操作。 这会将 MSIs 和脚本文件提取到一个文件夹中，而不会实际安装该产品。 不应为任何值。 |
| /LAYOUTDIR | 指定布局目录。 接受字符串。 示例用法： **/LAYOUTDIR = "C:\\Application Virtualization Server"** |
| /INSTALLDIR | 指定安装目录。 接受字符串。 示例用法： **/INSTALLDIR = "C:\\program files Files\\Application Virtualization\\Server"** |
| /MUOPTIN | 启用 Microsoft 更新。 不应为任何值。 |
| /ACCEPTEULA | 接受许可协议。 这是无人参与安装所必需的。 示例用法： **/ACCEPTEULA**或 **/ACCEPTEULA = 1** |

#### 管理服务器安装参数

|参数 |信息 |
|--|--|
| /MANAGEMENT_SERVER | 指定将安装管理服务器。 不需要任何值 |
| /MANAGEMENT_ADMINACCOUNT | 指定将允许管理员访问管理服务器的帐户。 这可以是用户帐户或组。 示例用法： **/MANAGEMENT_ADMINACCOUNT = "mydomain\\admin"**。 如果未指定 **/MANAGEMENT_SERVER** ，此操作将被忽略。 |
| /MANAGEMENT_WEBSITE_NAME | 指定将为管理服务创建的网站的名称。 示例用法： **/MANAGEMENT_WEBSITE_NAME = "Microsoft App-V 管理服务"** |
| MANAGEMENT_WEBSITE_PORT | 指定管理服务将使用的端口号。 示例用法： **/MANAGEMENT_WEBSITE_PORT = 82** |

#### 管理服务器数据库的参数

| 参数 | 信息 |
|--|--|
| /DB_PREDEPLOY_MANAGEMENT | 指定将安装管理数据库。 您必须有足够的数据库权限才能完成此安装。 不应为任何值。 |
| /MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT | 指示应使用默认 SQL 实例。 不应为任何值。 |
| /MANAGEMENT_DB_ CUSTOM_SQLINSTANCE | 指定应用于创建新数据库的自定义 SQL 实例的名称。 示例用法： **/MANAGEMENT_DB_ CUSTOM_SQLINSTANCE = "MYSQLSERVER"**。 如果未指定 **/DB_PREDEPLOY_MANAGEMENT** ，此操作将被忽略。 |
| /MANAGEMENT_DB_NAME | 指定应创建的新管理数据库的名称。 示例用法： **/MANAGEMENT_DB_NAME = "AppVMgmtDB"**。 如果未指定 **/DB_PREDEPLOY_MANAGEMENT** ，此操作将被忽略。 |
| /MANAGEMENT_SERVER_MACHINE_USE_LOCAL | 指示是否在本地服务器上安装了将访问该数据库的管理服务器。 开关参数，因此不需要任何值。 |
| /MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT | 指定将安装管理服务器的远程计算机的计算机帐户。 示例用法： **/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT = "domain\\computername"** |
| /MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT | 指示将用于安装管理服务器的管理员帐户。 示例用法： **/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT = "domain\\alias"** |

#### 用于安装发布服务器的参数

| 参数 | 信息 |
|--|--|
| /PUBLISHING_SERVER | 指定将安装发布服务器。 不应为任何值。 |
| /PUBLISHING_MGT_SERVER | 指定发布服务器将连接到的管理服务的 URL。 示例用法： **http:// &lt; 管理服务器名称 &gt; ： &lt; 管理服务器端口号 &gt; **。 如果未使用 **/PUBLISHING_SERVER** ，此参数将被忽略。 |
| /PUBLISHING_WEBSITE_NAME | 指定将为发布服务创建的网站的名称。 示例用法： **/PUBLISHING_WEBSITE_NAME = "Microsoft App-V 发布服务"** |
| /PUBLISHING_WEBSITE_PORT | 指定发布服务使用的端口号。 示例用法： **/PUBLISHING_WEBSITE_PORT = 83** |

#### 用于报告服务器的参数

| 参数 | 信息 |
|--|--|
| /REPORTING_SERVER | 指定将安装报表服务器。 不应为任何值。 |
| /REPORTING_WEBSITE_NAME | 指定将为报告服务创建的网站的名称。 示例用法： **/REPORTING_WEBSITE_NAME = "Microsoft App-V ReportingService"** |
| /REPORTING_WEBSITE_PORT | 指定报表服务将使用的端口号。 示例用法： **/REPORTING_WEBSITE_PORT = 82** |

#### 用于使用现有报表服务器数据库的参数

| 参数 | 信息 |
|--|--|
| /EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL | 指示本地服务器上安装了 Microsoft SQL Server。 开关参数，因此不需要任何值。 |
| /EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME | 指定安装 SQL Server 的远程计算机的名称。 接受字符串。 示例用法： **/EXISTING_REPORTING_DB_ REMOTE_SQL_SERVER_NAME = "mycomputer1"** |
| /EXISTING_ 报告 _DB_SQLINSTANCE_USE_DEFAULT | 指示要使用的默认 SQL 实例。 开关参数，因此不需要任何值。 |
| /EXISTING_ REPORTING_DB_CUSTOM_SQLINSTANCE | 指定应使用的自定义 SQL 实例的名称。 接受字符串。 示例用法： **/EXISTING_REPORTING_DB_ CUSTOM_SQLINSTANCE = "MYSQLSERVER"** |
| /EXISTING_ 报告 _DB_NAME | 指定应使用的现有报告数据库的名称。 接受字符串。 示例用法： **/EXISTING_REPORTING_DB_NAME = "AppVReporting"** |

#### 用于安装报表服务器数据库的参数

| 参数 | 信息 |
|--|--|
| /DB_PREDEPLOY_REPORTING | 指定将安装报告数据库。 此安装需要 DBA 权限。 不应为任何值。 |
| /REPORTING_DB_SQLINSTANCE_USE_DEFAULT | 指定应使用的自定义 SQL 实例的名称。 接受字符串。 示例用法： **/REPORTING_DB_ CUSTOM_SQLINSTANCE = "MYSQLSERVER"** |
| /REPORTING_DB_NAME | 指定应创建的新报告数据库的名称。 接受字符串。 示例用法： **/REPORTING_DB_NAME = "AppVMgmtDB"** |
| /REPORTING_SERVER_MACHINE_USE_LOCAL | 指示将访问数据库的报表服务器安装在本地服务器上。 开关参数，因此不需要任何值。 |
| /REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT | 指定将安装报表服务器的远程计算机的计算机帐户。 接受字符串。 示例用法： **/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT = "domain\computername"** |
| /REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT | 指示将用于安装 app-v 报告服务器的管理员帐户。 接受字符串。 示例用法： **/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT = "domain\\alias"** |

#### 用于使用现有管理服务器数据库的参数

| 参数 | 信息 |
|--|--|
| /EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL | 指示 SQL Server 安装在本地服务器上。 开关参数，因此不需要任何值。如果指定 **/DB_PREDEPLOY_MANAGEMENT** ，此操作将被忽略。 |
| /EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME | 指定安装 SQL Server 的远程计算机的名称。 接受字符串。 示例用法： **/EXISTING_MANAGEMENT_DB_ REMOTE_SQL_SERVER_NAME = "mycomputer1"** |
| /EXISTING_ MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT | 指示要使用的默认 SQL 实例。 开关参数，因此不需要任何值。 如果指定 **/DB_PREDEPLOY_MANAGEMENT** ，此操作将被忽略。 |
| /EXISTING_MANAGEMENT_DB_ CUSTOM_SQLINSTANCE | 指定将使用的自定义 SQL 实例的名称。 示例用法 **/EXISTING_MANAGEMENT_DB_ CUSTOM_SQLINSTANCE = "AppVManagement"**。 如果指定 **/DB_PREDEPLOY_MANAGEMENT** ，此操作将被忽略。 |
| /EXISTING_MANAGEMENT_DB_NAME | 指定应使用的现有管理数据库的名称。 示例用法： **/EXISTING_MANAGEMENT_DB_NAME = "AppVMgmtDB"**。 如果指定 **/DB_PREDEPLOY_MANAGEMENT** ，此操作将被忽略。 |

遇到了 app-v 问题？ 使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相关主题

[部署 App-V 5.1 Server](deploying-the-app-v-51-server.md)
