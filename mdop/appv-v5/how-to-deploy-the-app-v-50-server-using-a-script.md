---
title: 如何使用脚本部署 App-V 5.0 Server
description: 如何使用脚本部署 App-V 5.0 Server
author: dansimp
ms.assetid: b91a35c8-df9e-4065-9187-abafbe565b84
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/15/2018
ms.openlocfilehash: aeb16d166fe7b1c4bb418c212024c49f6b151b94
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798478"
---
# 如何使用脚本部署 App-V 5.0 Server


为了使用命令行成功完成**appv\_server\_setup.exe**服务器设置，必须指定和组合多个参数。

有关使用命令行安装 App-v 5.0 服务器的详细信息，请使用下表。

>[!NOTE]
> 通过键入以下命令，还可以使用命令行访问下表中的信息：
>```
> appv\_server\_setup.exe /?
>```

## 常见参数和示例

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p>在本地计算机上安装管理服务器和管理数据库。</p></td>
    <td align="left"><p>若要使用 Microsoft SQL Server 的默认实例，请使用以下参数：</p>
    <ul>
    <li><p>/MANAGEMENT_SERVER</p></li>
    <li><p>/MANAGEMENT_ADMINACCOUNT</p></li>
    <li><p>/MANAGEMENT_WEBSITE_NAME</p></li>
    <li><p>/MANAGEMENT_WEBSITE_PORT</p></li>
    <li><p>/DB_PREDEPLOY_MANAGEMENT</p></li>
    <li><p>/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</p></li>
    <li><p>/MANAGEMENT_DB_NAME</p></li>
    </ul>
    <p>若要使用 Microsoft SQL Server 的自定义实例，请使用以下参数：</p>
    <ul>
    <li><p>/MANAGEMENT_SERVER</p></li>
    <li><p>/MANAGEMENT_ADMINACCOUNT</p></li>
    <li><p>/MANAGEMENT_WEBSITE_NAME</p></li>
    <li><p>/MANAGEMENT_WEBSITE_PORT</p></li>
    <li><p>/DB_PREDEPLOY_MANAGEMENT</p></li>
    <li><p>/MANAGEMENT_DB_CUSTOM_SQLINSTANCE</p></li>
    <li><p>/MANAGEMENT_DB_NAME</p></li>
    </ul>
    <p>使用 Microsoft SQL Server 的自定义实例示例：</p>
    <p>/appv_server_setup.exe/QUIET</p>
    <p>/MANAGEMENT_SERVER</p>
    <p>/MANAGEMENT_ADMINACCOUNT = "Domain\AdminGroup"</p>
    <p>/MANAGEMENT_WEBSITE_NAME = "Microsoft AppV 管理服务"</p>
    <p>/MANAGEMENT_WEBSITE_PORT = "8080"</p>
    <p>/DB_PREDEPLOY_MANAGEMENT</p>
    <p>/MANAGEMENT_DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</p>
    <p>/MANAGEMENT_DB_NAME = "AppVManagement"</p></td>
    </tr>
    </tbody>
    </table>
     
<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p>使用本地计算机上的现有管理数据库安装管理服务器。</p></td>
    <td align="left"><p>若要使用 Microsoft SQL Server 的默认实例，请使用以下参数：</p>
    <ul>
    <li><p>/MANAGEMENT_SERVER</p></li>
    <li><p>/MANAGEMENT_ADMINACCOUNT</p></li>
    <li><p>/MANAGEMENT_WEBSITE_NAME</p></li>
    <li><p>/MANAGEMENT_WEBSITE_PORT</p></li>
    <li><p>/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</p></li>
    <li><p>/EXISTING_MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</p></li>
    <li><p>/EXISTING_MANAGEMENT_DB_NAME</p></li>
    </ul>
    <p>若要使用 Microsoft SQL Server 的自定义实例，请使用以下参数：</p>
    <ul>
    <li><p>/MANAGEMENT_SERVER</p></li>
    <li><p>/MANAGEMENT_ADMINACCOUNT</p></li>
    <li><p>/MANAGEMENT_WEBSITE_NAME</p></li>
    <li><p>/MANAGEMENT_WEBSITE_PORT</p></li>
    <li><p>/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</p></li>
    <li><p>/EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE</p></li>
    <li><p>/EXISTING_MANAGEMENT_DB_NAME</p></li>
    </ul>
    <p>使用 Microsoft SQL Server 的自定义实例示例：</p>
    <p>/appv_server_setup.exe/QUIET</p>
    <p>/MANAGEMENT_SERVER</p>
    <p>/MANAGEMENT_ADMINACCOUNT = "Domain\AdminGroup"</p>
    <p>/MANAGEMENT_WEBSITE_NAME = "Microsoft AppV 管理服务"</p>
    <p>/MANAGEMENT_WEBSITE_PORT = "8080"</p>
    <p>/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</p>
    <p>/EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</p>
    <p>/EXISTING_MANAGEMENT_DB_NAME = "AppVManagement"</p></td>
    </tr>
    </tbody>
    </table>  

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p>在远程计算机上使用现有管理数据库安装管理服务器。</p></td>
    <td align="left"><p>若要使用 Microsoft SQL Server 的默认实例，请使用以下参数：</p>
    <ul>
    <li><p>/MANAGEMENT_SERVER</p></li>
    <li><p>/MANAGEMENT_ADMINACCOUNT</p></li>
    <li><p>/MANAGEMENT_WEBSITE_NAME</p></li>
    <li><p>/MANAGEMENT_WEBSITE_PORT</p></li>
    <li><p>/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME</p></li>
    <li><p>/EXISTING_MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</p></li>
    <li><p>/EXISTING_MANAGEMENT_DB_NAME</p></li>
    </ul>
    <p>若要使用 Microsoft SQL Server 的自定义实例，请使用以下参数：</p>
    <ul>
    <li><p>/MANAGEMENT_SERVER</p></li>
    <li><p>/MANAGEMENT_ADMINACCOUNT</p></li>
    <li><p>/MANAGEMENT_WEBSITE_NAME</p></li>
    <li><p>/MANAGEMENT_WEBSITE_PORT</p></li>
    <li><p>/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME</p></li>
    <li><p>/EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE</p></li>
    <li><p>/EXISTING_MANAGEMENT_DB_NAME</p></li>
    </ul>
    <p>使用 Microsoft SQL Server 的自定义实例示例：</p>
    <p>/appv_server_setup.exe/QUIET</p>
    <p>/MANAGEMENT_SERVER</p>
    <p>/MANAGEMENT_ADMINACCOUNT = "Domain\AdminGroup"</p>
    <p>/MANAGEMENT_WEBSITE_NAME = "Microsoft AppV 管理服务"</p>
    <p>/MANAGEMENT_WEBSITE_PORT = "8080"</p>
    <p>/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME = "SqlServermachine"</p>
    <p>/EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</p>
    <p>/EXISTING_MANAGEMENT_DB_NAME = "AppVManagement"</p></td>
    </tr>
    </tbody>
    </table>
    
<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p>在同一台计算机上安装管理数据库和管理服务器。</p></td>
    <td align="left"><p>若要使用 Microsoft SQL Server 的默认实例，请使用以下参数：</p>
    <ul>
    <li><p>/DB_PREDEPLOY_MANAGEMENT</p></li>
    <li><p>/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</p></li>
    <li><p>/MANAGEMENT_DB_NAME</p></li>
    <li><p>/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</p></li>
    <li><p>/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</p></li>
    </ul>
    <p>若要使用 Microsoft SQL Server 的自定义实例，请使用以下参数：</p>
    <ul>
    <li><p>/DB_PREDEPLOY_MANAGEMENT</p></li>
    <li><p>/MANAGEMENT_DB_CUSTOM_SQLINSTANCE</p></li>
    <li><p>/MANAGEMENT_DB_NAME</p></li>
    <li><p>/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</p></li>
    <li><p>/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</p></li>
    </ul>
    <p>使用 Microsoft SQL Server 的自定义实例示例：</p>
    <p>/appv_server_setup.exe/QUIET</p>
    <p>/DB_PREDEPLOY_MANAGEMENT</p>
    <p>/MANAGEMENT_DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</p>
    <p>/MANAGEMENT_DB_NAME = "AppVManagement"</p>
    <p>/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</p>
    <p>/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT = "Domain\InstallAdminAccount"</p></td>
    </tr>
    </tbody>
    </table>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p>在不同于管理服务器的计算机上安装管理数据库。</p></td>
    <td align="left"><p>若要使用 Microsoft SQL Server 的默认实例，请使用以下参数：</p>
    <ul>
    <li><p>/DB_PREDEPLOY_MANAGEMENT</p></li>
    <li><p>/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</p></li>
    <li><p>/MANAGEMENT_DB_NAME</p></li>
    <li><p>/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</p></li>
    <li><p>/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</p></li>
    </ul>
    <p>若要使用 Microsoft SQL Server 的自定义实例，请使用以下参数：</p>
    <ul>
    <li><p>/DB_PREDEPLOY_MANAGEMENT</p></li>
    <li><p>/MANAGEMENT_DB_CUSTOM_SQLINSTANCE</p></li>
    <li><p>/MANAGEMENT_DB_NAME</p></li>
    <li><p>/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</p></li>
    <li><p>/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</p></li>
    </ul>
    <p>使用 Microsoft SQL Server 的自定义实例示例：</p>
    <p>/appv_server_setup.exe/QUIET</p>
    <p>/DB_PREDEPLOY_MANAGEMENT</p>
    <p>/MANAGEMENT_DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</p>
    <p>/MANAGEMENT_DB_NAME = "AppVManagement"</p>
    <p>/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT = "Domain\MachineAccount"</p>
    <p>/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT = "Domain\InstallAdminAccount"</p></td>
    </tr>
    </tbody>
    </table>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p>安装发布服务器。</p></td>
    <td align="left"><p>若要使用 Microsoft SQL Server 的默认实例，请使用以下参数：</p>
    <ul>
    <li><p>/PUBLISHING_SERVER</p></li>
    <li><p>/PUBLISHING_MGT_SERVER</p></li>
    <li><p>/PUBLISHING_WEBSITE_NAME</p></li>
    <li><p>/PUBLISHING_WEBSITE_PORT</p></li>
    </ul>
    <p>使用 Microsoft SQL Server 的自定义实例示例：</p>
    <p>/appv_server_setup.exe/QUIET</p>
    <p>/PUBLISHING_SERVER</p>
    <p>/PUBLISHING_MGT_SERVER = " http://ManagementServerName:ManagementPort "</p>
    <p>/PUBLISHING_WEBSITE_NAME = "Microsoft AppV 发布服务"</p>
    <p>/PUBLISHING_WEBSITE_PORT = "8081"</p></td>
    </tr>
    </tbody>
    </table>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p>在本地计算机上安装报表服务器和报告数据库。</p></td>
    <td align="left"><p>若要使用 Microsoft SQL Server 的默认实例，请使用以下参数：</p>
    <ul>
    <li><p>/REPORTING _SERVER</p></li>
    <li><p>/REPORTING _WEBSITE_NAME</p></li>
    <li><p>/REPORTING _WEBSITE_PORT</p></li>
    <li><p>/DB_PREDEPLOY_REPORTING</p></li>
    <li><p>/REPORTING _DB_SQLINSTANCE_USE_DEFAULT</p></li>
    <li><p>/REPORTING _DB_NAME</p></li>
    </ul>
    <p>若要使用 Microsoft SQL Server 的自定义实例，请使用以下参数：</p>
    <ul>
    <li><p>/REPORTING _SERVER</p></li>
    <li><p>/REPORTING _ADMINACCOUNT</p></li>
    <li><p>/REPORTING _WEBSITE_NAME</p></li>
    <li><p>/REPORTING _WEBSITE_PORT</p></li>
    <li><p>/DB_PREDEPLOY_REPORTING</p></li>
    <li><p>/REPORTING _DB_CUSTOM_SQLINSTANCE</p></li>
    <li><p>/REPORTING _DB_NAME</p></li>
    </ul>
    <p>使用 Microsoft SQL Server 的自定义实例示例：</p>
    <ul>
    <li><p>/appv_server_setup.exe/QUIET</p></li>
    <li><p>/REPORTING_SERVER</p></li>
    <li><p>/REPORTING_WEBSITE_NAME = "Microsoft AppV 报告服务"</p></li>
    <li><p>/REPORTING_WEBSITE_PORT = "8082"</p></li>
    <li><p>/DB_PREDEPLOY_REPORTING</p></li>
    <li><p>/REPORTING_DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</p></li>
    <li><p>/REPORTING_DB_NAME = "AppVReporting"</p></li>
    </ul></td>
    </tr>
    </tbody>
    </table>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p>安装报告服务器并使用本地计算机上的现有报告数据库。</p></td>
    <td align="left"><p>若要使用 Microsoft SQL Server 的默认实例，请使用以下参数：</p>
    <ul>
    <li><p>/REPORTING _SERVER</p></li>
    <li><p>/REPORTING _WEBSITE_NAME</p></li>
    <li><p>/REPORTING _WEBSITE_PORT</p></li>
    <li><p>/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</p></li>
    <li><p>/EXISTING_REPORTING _DB_SQLINSTANCE_USE_DEFAULT</p></li>
    <li><p>/EXISTING_REPORTING _DB_NAME</p></li>
    </ul>
    <p>若要使用 Microsoft SQL Server 的自定义实例，请使用以下参数：</p>
    <ul>
    <li><p>/REPORTING _SERVER</p></li>
    <li><p>/REPORTING _ADMINACCOUNT</p></li>
    <li><p>/REPORTING _WEBSITE_NAME</p></li>
    <li><p>/REPORTING _WEBSITE_PORT</p></li>
    <li><p>/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</p></li>
    <li><p>/EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE</p></li>
    <li><p>/EXISTING_REPORTING _DB_NAME</p></li>
    </ul>
    <p>使用 Microsoft SQL Server 的自定义实例示例：</p>
    <p>/appv_server_setup.exe/QUIET</p>
    <p>/REPORTING_SERVER</p>
    <p>/REPORTING_WEBSITE_NAME = "Microsoft AppV 报告服务"</p>
    <p>/REPORTING_WEBSITE_PORT = "8082"</p>
    <p>/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</p>
    <p>/EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</p>
    <p>/EXITING_REPORTING_DB_NAME = "AppVReporting"</p></td>
    </tr>
    </tbody>
    </table>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p>使用远程计算机上的现有报告数据库安装报告服务器。</p></td>
    <td align="left"><p>若要使用 Microsoft SQL Server 的默认实例，请使用以下参数：</p>
    <ul>
    <li><p>/REPORTING _SERVER</p></li>
    <li><p>/REPORTING _WEBSITE_NAME</p></li>
    <li><p>/REPORTING _WEBSITE_PORT</p></li>
    <li><p>/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME</p></li>
    <li><p>/EXISTING_REPORTING _DB_SQLINSTANCE_USE_DEFAULT</p></li>
    <li><p>/EXISTING_REPORTING _DB_NAME</p></li>
    </ul>
    <p>若要使用 Microsoft SQL Server 的自定义实例，请使用以下参数：</p>
    <ul>
    <li><p>/REPORTING _SERVER</p></li>
    <li><p>/REPORTING _ADMINACCOUNT</p></li>
    <li><p>/REPORTING _WEBSITE_NAME</p></li>
    <li><p>/REPORTING _WEBSITE_PORT</p></li>
    <li><p>/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME</p></li>
    <li><p>/EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE</p></li>
    <li><p>/EXISTING_REPORTING _DB_NAME</p></li>
    </ul>
    <p>使用 Microsoft SQL Server 的自定义实例示例：</p>
    <p>/appv_server_setup.exe/QUIET</p>
    <p>/REPORTING_SERVER</p>
    <p>/REPORTING_WEBSITE_NAME = "Microsoft AppV 报告服务"</p>
    <p>/REPORTING_WEBSITE_PORT = "8082"</p>
    <p>/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME = "SqlServerMachine"</p>
    <p>/EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</p>
    <p>/EXITING_REPORTING_DB_NAME = "AppVReporting"</p></td>
    </tr>
    </tbody>
    </table>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p>在报表服务器所在的同一台计算机上安装报告数据库。</p></td>
    <td align="left"><p>若要使用 Microsoft SQL Server 的默认实例，请使用以下参数：</p>
    <ul>
    <li><p>/DB_PREDEPLOY_REPORTING</p></li>
    <li><p>/REPORTING _DB_SQLINSTANCE_USE_DEFAULT</p></li>
    <li><p>/REPORTING _DB_NAME</p></li>
    <li><p>/REPORTING_SERVER_MACHINE_USE_LOCAL</p></li>
    <li><p>/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</p></li>
    </ul>
    <p>若要使用 Microsoft SQL Server 的自定义实例，请使用以下参数：</p>
    <ul>
    <li><p>/DB_PREDEPLOY_REPORTING</p></li>
    <li><p>/REPORTING _DB_CUSTOM_SQLINSTANCE</p></li>
    <li><p>/REPORTING _DB_NAME</p></li>
    <li><p>/REPORTING_SERVER_MACHINE_USE_LOCAL</p></li>
    <li><p>/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</p></li>
    </ul>
    <p>使用 Microsoft SQL Server 的自定义实例示例：</p>
    <p>/appv_server_setup.exe/QUIET</p>
    <p>/DB_PREDEPLOY_REPORTING</p>
    <p>/REPORTING_DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</p>
    <p>/REPORTING_DB_NAME = "AppVReporting"</p>
    <p>/REPORTING_SERVER_MACHINE_USE_LOCAL</p>
    <p>/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT = "Domain\InstallAdminAccount"</p></td>
    </tr>
    </tbody>
    </table>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p>在不同于报表服务器的计算机上安装报告数据库。</p></td>
    <td align="left"><p>若要使用 Microsoft SQL Server 的默认实例，请使用以下参数：</p>
    <ul>
    <li><p>/DB_PREDEPLOY_REPORTING</p></li>
    <li><p>/REPORTING _DB_SQLINSTANCE_USE_DEFAULT</p></li>
    <li><p>/REPORTING _DB_NAME</p></li>
    <li><p>/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</p></li>
    <li><p>/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</p></li>
    </ul>
    <p>若要使用 Microsoft SQL Server 的自定义实例，请使用以下参数：</p>
    <ul>
    <li><p>/DB_PREDEPLOY_REPORTING</p></li>
    <li><p>/REPORTING _DB_CUSTOM_SQLINSTANCE</p></li>
    <li><p>/REPORTING _DB_NAME</p></li>
    <li><p>/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</p></li>
    <li><p>/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</p></li>
    </ul>
    <p>使用 Microsoft SQL Server 的自定义实例示例：</p>
    <p>/appv_server_setup.exe/QUIET</p>
    <p>/DB_PREDEPLOY_REPORTING</p>
    <p>/REPORTING_DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</p>
    <p>/REPORTING_DB_NAME = "AppVReporting"</p>
    <p>/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT = "Domain\MachineAccount"</p>
    <p>/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT = "Domain\InstallAdminAccount"</p></td>
    </tr>
    </tbody>
    </table>

## 参数定义

### 常规参数

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">参数</th>
    <th align="left">信息</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>/QUIET</p></td>
    <td align="left"><p>指定静默安装。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>/UNINSTALL</p></td>
    <td align="left"><p>指定卸载。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>/LAYOUT</p></td>
    <td align="left"><p>指定布局操作。 这会将 MSIs 和脚本文件提取到一个文件夹中，而不会实际安装该产品。 不应为任何值。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>/LAYOUTDIR</p></td>
    <td align="left"><p>指定布局目录。 接受字符串。 例如，/LAYOUTDIR = "C:\Application 虚拟化服务器"</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>/INSTALLDIR</p></td>
    <td align="left"><p>指定安装目录。 接受字符串。 例如 /INSTALLDIR = "C:\Program Files\Application Virtualization\Server"</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>/MUOPTIN</p></td>
    <td align="left"><p>启用 Microsoft 更新。 不需要任何值</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>/ACCEPTEULA</p></td>
    <td align="left"><p>接受许可协议。 这是无人参与安装所必需的。 示例用法： <strong> /ACCEPTEULA </strong> 或 <strong> /ACCEPTEULA = 1 </strong> 。</p></td>
    </tr>
    </tbody>
    </table>

### 管理服务器安装参数

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">参数</th>
    <th align="left">信息</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>/MANAGEMENT_SERVER</p></td>
    <td align="left"><p>指定将安装管理服务器。 不需要任何值</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>/MANAGEMENT_ADMINACCOUNT</p></td>
    <td align="left"><p>指定允许管理员访问管理服务器的帐户此帐户可以是单个用户帐户或组。 示例用法： <strong> /MANAGEMENT_ADMINACCOUNT = "mydomain\admin" </strong> 。 如果 <strong> </strong> 未指定/MANAGEMENT_SERVER，此操作将被忽略。 指定将允许管理员访问管理服务器的帐户。 这可以是用户帐户或组。 例如， <strong> /MANAGEMENT_ADMINACCOUNT = &quot; mydomain\admin &quot; </strong> 。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>/MANAGEMENT_WEBSITE_NAME</p></td>
    <td align="left"><p>指定将为管理服务创建的网站的名称。 例如，/MANAGEMENT_WEBSITE_NAME = "Microsoft App-V 管理服务"</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>MANAGEMENT_WEBSITE_PORT</p></td>
    <td align="left"><p>指定管理服务将使用的端口号。 例如，/MANAGEMENT_WEBSITE_PORT = 82。</p></td>
    </tr>
    </tbody>
    </table>

### 管理服务器数据库的参数

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">参数</th>
    <th align="left">信息</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>/DB_PREDEPLOY_MANAGEMENT</p></td>
    <td align="left"><p>指定将安装管理数据库。 您必须有足够的数据库权限才能完成此安装。 不需要任何值</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</p></td>
    <td align="left"><p>指示应使用默认 SQL 实例。 不应为任何值。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>/MANAGEMENT_DB_ CUSTOM_SQLINSTANCE</p></td>
    <td align="left"><p>指定应用于创建新数据库的自定义 SQL 实例的名称。 示例用法： <strong> /MANAGEMENT_DB_ CUSTOM_SQLINSTANCE = "MYSQLSERVER" </strong> 。 如果未指定/DB_PREDEPLOY_MANAGEMENT，此操作将被忽略。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>/MANAGEMENT_DB_NAME</p></td>
    <td align="left"><p>指定应创建的新管理数据库的名称。 示例用法： <strong> /MANAGEMENT_DB_NAME = "AppVMgmtDB" </strong> 。 如果未指定/DB_PREDEPLOY_MANAGEMENT，此操作将被忽略。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</p></td>
    <td align="left"><p>指示是否在本地服务器上安装了将访问该数据库的管理服务器。 开关参数，因此不需要任何值。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</p></td>
    <td align="left"><p>指定将安装管理服务器的远程计算机的计算机帐户。 示例用法： <strong> /MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT = "domain\computername"</strong></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</p></td>
    <td align="left"><p>指示将用于安装管理服务器的管理员帐户。 示例用法： <strong> /MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT = "domain\alias"</strong></p></td>
    </tr>
    </tbody>
    </table>

### 用于安装发布服务器的参数

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">参数</th>
    <th align="left">信息</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>/PUBLISHING_SERVER</p></td>
    <td align="left"><p>指定将安装发布服务器。 不需要任何值</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>/PUBLISHING_MGT_SERVER</p></td>
    <td align="left"><p>指定发布服务器将连接到的管理服务的 URL。 示例用法： <strong> http:// &lt; 管理服务器名称 &gt; ： &lt; 管理服务器端口号 &gt; </strong> 。 如果未使用/PUBLISHING_SERVER，此参数将被忽略</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>/PUBLISHING_WEBSITE_NAME</p></td>
    <td align="left"><p>指定将为发布服务创建的网站的名称。 例如，/PUBLISHING_WEBSITE_NAME = "Microsoft App-V 发布服务"</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>/PUBLISHING_WEBSITE_PORT</p></td>
    <td align="left"><p>指定发布服务使用的端口号。 例如，/PUBLISHING_WEBSITE_PORT = 83</p></td>
    </tr>
    </tbody>
    </table>

### 用于报告服务器的参数

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">参数</th>
    <th align="left">信息</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>/REPORTING_SERVER</p></td>
    <td align="left"><p>指定将安装报表服务器。 不需要任何值</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>/REPORTING_WEBSITE_NAME</p></td>
    <td align="left"><p>指定将为报告服务创建的网站的名称。 例如 /REPORTING_WEBSITE_NAME = &quot; Microsoft App-V ReportingService&quot;</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>/REPORTING_WEBSITE_PORT</p></td>
    <td align="left"><p>指定报表服务将使用的端口号。 例如 /REPORTING_WEBSITE_PORT = 82</p></td>
    </tr>
    </tbody>
    </table>

     

### 用于使用现有报表服务器数据库的参数

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">参数</th>
    <th align="left">信息</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</p></td>
    <td align="left"><p>指示本地服务器上安装了 Microsoft SQL Server。 开关参数，因此不需要任何值。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME</p></td>
    <td align="left"><p>指定安装 SQL Server 的远程计算机的名称。 接受字符串。 例如 /EXISTING_REPORTING_DB_ REMOTE_SQL_SERVER_NAME = &quot; mycomputer1&quot;</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>/EXISTING_ 报告 <em> DB_SQLINSTANCE_USE_DEFAULT</p></td>
    <td align="left"><p>指示要使用的默认 SQL 实例。 开关参数，因此不需要任何值。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>/EXISTING </em> REPORTING_DB_CUSTOM_SQLINSTANCE</p></td>
    <td align="left"><p>指定应使用的自定义 SQL 实例的名称。 接受字符串。 例如 /EXISTING_REPORTING_DB_ CUSTOM_SQLINSTANCE = &quot; MYSQLSERVER&quot;</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>/EXISTING_ 报告 _DB_NAME</p></td>
    <td align="left"><p>指定应使用的现有报告数据库的名称。 接受字符串。 例如 /EXISTING_REPORTING_DB_NAME = &quot; AppVReporting&quot;</p></td>
    </tr>
    </tbody>
    </table>

### 用于安装报表服务器数据库的参数

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">参数</th>
    <th align="left">信息</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>/DB_PREDEPLOY_REPORTING</p></td>
    <td align="left"><p>指定将安装报告数据库。 此安装需要 DBA 权限。 不需要任何值</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>/REPORTING_DB_SQLINSTANCE_USE_DEFAULT</p></td>
    <td align="left"><p>指定应使用的自定义 SQL 实例的名称。 接受字符串。 例如 /REPORTING_DB_ CUSTOM_SQLINSTANCE = &quot; MYSQLSERVER&quot;</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>/REPORTING_DB_NAME</p></td>
    <td align="left"><p>指定应创建的新报告数据库的名称。 接受字符串。 例如 /REPORTING_DB_NAME = &quot; AppVMgmtDB&quot;</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>/REPORTING_SERVER_MACHINE_USE_LOCAL</p></td>
    <td align="left"><p>指示将访问数据库的报表服务器安装在本地服务器上。 开关参数，因此不需要任何值。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</p></td>
    <td align="left"><p>指定将安装报表服务器的远程计算机的计算机帐户。 接受字符串。 例如 /REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT = &quot; domain\computername&quot;</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</p></td>
    <td align="left"><p>指示将用于安装 app-v 报告服务器的管理员帐户。 接受字符串。 例如 /REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT = &quot; domain\alias&quot;</p></td>
    </tr>
    </tbody>
    </table>

### 用于使用现有管理服务器数据库的参数

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">参数</th>
    <th align="left">信息</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</p></td>
    <td align="left"><p>指示 SQL Server 安装在本地服务器上。 开关参数，因此不需要任何值。如果指定/DB_PREDEPLOY_MANAGEMENT，此操作将被忽略。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME</p></td>
    <td align="left"><p>指定安装 SQL Server 的远程计算机的名称。 接受字符串。 例如 /EXISTING_MANAGEMENT_DB_ REMOTE_SQL_SERVER_NAME = &quot; mycomputer1&quot;</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>/EXISTING_ MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</p></td>
    <td align="left"><p>指示要使用的默认 SQL 实例。 开关参数，因此不需要任何值。 如果指定/DB_PREDEPLOY_MANAGEMENT，此操作将被忽略。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>/EXISTING_MANAGEMENT_DB_ CUSTOM_SQLINSTANCE</p></td>
    <td align="left"><p>指定将使用的自定义 SQL 实例的名称。 示例用法 <strong> /EXISTING_MANAGEMENT_DB_ CUSTOM_SQLINSTANCE = "AppVManagement" </strong> 。 如果指定/DB_PREDEPLOY_MANAGEMENT，此操作将被忽略。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>/EXISTING_MANAGEMENT_DB_NAME</p></td>
    <td align="left"><p>指定应使用的现有管理数据库的名称。 示例用法： <strong> /EXISTING_MANAGEMENT_DB_NAME = "AppVMgmtDB" </strong> 。 如果指定/DB_PREDEPLOY_MANAGEMENT，此操作将被忽略。</p>
    <p></p>
    <p><strong>已获得有关 App-v 的建议 </strong> ？ 在此处添加或投票 <a href="http://appv.uservoice.com/forums/280448-microsoft-application-virtualization" data-raw-source="[here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)"> 建议 </a> 。 <strong>是否有应用程序-V issu </strong> e？ 使用 app-v <a href="https://social.technet.microsoft.com/Forums/home?forum=mdopappv" data-raw-source="[App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)"> TechNet 论坛 </a> 。</p></td>
</tr>
</tbody>
</table>
  

## 相关主题

[部署 App-V 5.0 Server](deploying-the-app-v-50-server.md)

 

 





