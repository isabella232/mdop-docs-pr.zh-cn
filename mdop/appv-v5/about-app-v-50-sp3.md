---
title: 关于 App-V 5.0 SP3
description: 关于 App-V 5.0 SP3
author: dansimp
ms.assetid: 67b5268b-edc1-4027-98b0-b3937dd70a6b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/02/2016
ms.openlocfilehash: bc72f3f72c2b06470287dfe4ba3ed22abcc6068b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798678"
---
# 关于 App-V 5.0 SP3


使用以下部分查看有关适用于 Microsoft Application Virtualization （App-v） 5.0 SP3 的重大更改的信息。

-   [App-v 5.0 SP3 软件先决条件和支持的配置](#bkmk-sp3-prereq-configs)

-   [迁移到 App-v 5.0 SP3](#bkmk-migrate-to-50sp3)

-   [手动创建的连接组 xml 文件需要更新到架构](#bkmk-update-schema-cg)

-   [对连接组的改进](#bkmk-cg-improvements)

-   [管理员可以发布和取消发布特定用户的程序包](#bkmk-usersid-pub-pkgs-specf-user)

-   [仅启用管理员发布和取消发布程序包](#bkmk-admins-only-pub-unpub-pkgs)

-   [RunVirtual 注册表项支持发布到用户的程序包](#bkmk-runvirtual-reg-key)

-   [新增 PowerShell cmdlet 和可更新 cmdlet 帮助](#bkmk-posh-cmdlets-help)

-   [主虚拟应用程序目录（PVAD）已隐藏，但可以启用](#bkmk-pvad-hidden)

-   [需要 ClientVersion，才能查看 App-v 发布元数据](#bkmk-pub-metadata-clientversion)

-   [App-v 事件日志已合并](#bkmk-event-logs-moved)

## <a href="" id="bkmk-sp3-prereq-configs"></a>App-v 5.0 SP3 软件先决条件和支持的配置


请参阅应用程序 V 的以下链接-V 5.0 SP3 软件先决条件和支持的配置。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">链接到先决条件和受支持的配置</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="app-v-50-sp3-prerequisites.md" data-raw-source="[App-V 5.0 SP3 Prerequisites](app-v-50-sp3-prerequisites.md)">App-V 5.0 SP3 先决条件</a></p></td>
<td align="left"><p>在启动 app-v 5.0 SP3 安装之前必须安装的必备软件</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="app-v-50-sp3-supported-configurations.md" data-raw-source="[App-V 5.0 SP3 Supported Configurations](app-v-50-sp3-supported-configurations.md)">App-V 5.0 SP3 支持的配置</a></p></td>
<td align="left"><p>支持的操作系统和适用于 app-v Server、Sequencer 和客户端组件的硬件要求</p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-migrate-to-50sp3"></a>迁移到 App-v 5.0 SP3


使用以下信息从早期版本升级到 app-v 5.0 SP3。

### 开始升级之前

在开始升级之前查看以下信息：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">升级前要查看的项目</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>要升级的组件</p></td>
<td align="left"><ol>
<li><p>App-v 服务器</p></li>
<li><p>序列</p></li>
<li><p>App-v 客户端或 App-v 远程桌面服务（RDS）客户端</p></li>
<li><p>连接组</p></li>
</ol>
<div class="alert">
<strong>注意</strong><br/><p>若要使用 App-v 客户端用户界面，请从 " <a href="https://www.microsoft.com/download/details.aspx?id=41186" data-raw-source="[Microsoft Application Virtualization 5.0 Client UI Application](https://www.microsoft.com/download/details.aspx?id=41186)"> Microsoft Application Virtualization 5.0 客户端 UI" 应用程序下载现有版本 </a> 。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>从 App-v 4 升级</p></td>
<td align="left"><p>必须首先升级到 app-v 5.0。 您不能直接从 app-v 4. x 升级到 app-v 5.0 SP3。</p>
<p>有关详细信息，请参阅：</p>
<ul>
<li><p><a href="about-app-v-50.md" data-raw-source="[About App-V 5.0](about-app-v-50.md)">关于 App-V 5.0</a> </p></li>
<li><p><a href="planning-for-migrating-from-a-previous-version-of-app-v.md" data-raw-source="[Planning for Migrating from a Previous Version of App-V](planning-for-migrating-from-a-previous-version-of-app-v.md)">计划从以前版本的 App-V 迁移</a></p></li>
</ul>
<p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>从 App-v 5.0 或更高版本升级</p></td>
<td align="left"><p>你可以直接从以下任何版本升级到 app-v 5.0 SP3：</p>
<ul>
<li><p>App-v 5。0</p></li>
<li><p>App-v 5.0 SP1</p></li>
<li><p>App-v 5.0 SP2</p></li>
</ul>
<p>若要升级到 app-v 5.0 SP3，请按照本文其余部分中的步骤操作。</p></td>
</tr>
<tr class="even">
<td align="left"><p>升级后对程序包和连接组所做的更改</p></td>
<td align="left"><p>无。 程序包和连接组将继续按当前方式工作。</p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-steps-upgrd-infrastruc"></a>升级 app-v 基础结构的步骤

完成以下步骤，将 app-v 基础结构的每个组件升级到 app-v 5.0 SP3。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">步骤</th>
<th align="left">有关详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>步骤1：升级 app-v 服务器。</p>
<p>如果未使用 App-v 服务器，请跳过此步骤，然后转到下一步。</p>
<div class="alert">
<strong>注意</strong><br/><p>App-v 5.0 SP3 客户端与 App-v 5.0 SP1 服务器兼容。</p>
</div>
<div>

</div></td>
<td align="left"><p>请按照下列步骤进行操作：</p>
<ol>
<li><p>查看 app-v <a href="release-notes-for-app-v-50-sp3.md" data-raw-source="[Release Notes for App-V 5.0 SP3](release-notes-for-app-v-50-sp3.md)"> 5.0 SP3 的发行说明， </a> 了解可能会影响 app-v 服务器安装的问题。</p></li>
<li><p>根据用于升级管理数据库和/或报告数据库的方法，执行下列操作之一：</p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">数据库升级方法</th>
<th align="left">步骤</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows Installer</p></td>
<td align="left"><p>跳过此步骤并转到步骤 3 "如果要升级 app-v 服务器 ..."</p></td>
</tr>
<tr class="even">
<td align="left"><p>SQL 脚本</p></td>
<td align="left"><table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>管理数据库</strong></p></td>
<td align="left"><p>若要安装或升级，请参阅 <a href="https://support.microsoft.com/kb/3031340" data-raw-source="[SQL scripts to install or upgrade the App-V 5.0 SP3 Management Server database fail](https://support.microsoft.com/kb/3031340)"> 安装或升级 app-v 5.0 SP3 管理服务器数据库失败的 SQL 脚本 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>报告数据库</strong></p></td>
<td align="left"><p>按照 <a href="how-to-deploy-the-app-v-databases-by-using-sql-scripts.md" data-raw-source="[How to Deploy the App-V Databases by Using SQL Scripts](how-to-deploy-the-app-v-databases-by-using-sql-scripts.md)"> 如何使用 SQL 脚本部署 App-v 数据库中的步骤操作 </a> 。</p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>
<p> </p></li>
<li><p>如果你要从 App-v 5.0 SP1 修补程序包3或更高版本升级 app-v 服务器，请完成 <a href="#bkmk-check-reg-key-svr" data-raw-source="[Check registry keys after installing the App-V 5.0 SP3 Server](#bkmk-check-reg-key-svr)"> 安装 app-v 5.0 SP3 服务器后检查注册表项部分中的步骤 </a> 。</p></li>
<li><p>按照部署 app-v 5.0 服务器的步骤进行操作 <a href="how-to-deploy-the-app-v-50-server-50sp3.md" data-raw-source="[How to Deploy the App-V 5.0 Server](how-to-deploy-the-app-v-50-server-50sp3.md)"> </a> 。</p></li>
</ol></td>
</tr>
<tr class="even">
<td align="left"><p>步骤2：升级 app-v Sequencer。</p></td>
<td align="left"><p>请参阅 <a href="how-to-install-the-sequencer-beta-gb18030.md" data-raw-source="[How to Install the Sequencer](how-to-install-the-sequencer-beta-gb18030.md)"> 如何安装 Sequencer </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>步骤3：升级 App-v 客户端或 App-v RDS 客户端。</p></td>
<td align="left"><p>请参阅 <a href="how-to-deploy-the-app-v-client-gb18030.md" data-raw-source="[How to Deploy the App-V Client](how-to-deploy-the-app-v-client-gb18030.md)"> 如何部署 App-v 客户端 </a> 。</p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-check-reg-key-svr"></a>在安装 app-v 5.0 SP3 服务器之前检查注册表项

这是上表中的步骤3。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>需要执行此步骤时</strong></p></td>
<td align="left"><p>从 App-v SP1 升级到使用 .msp 文件安装的任何后续修补程序包。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>哪些组件需要执行此步骤</strong></p></td>
<td align="left"><p>仅限你要升级的 app-v Server 组件。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>需要执行此步骤时</strong></p></td>
<td align="left"><p>将 App-v Server 升级到 App-v 5.0 SP3 之前</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>需要执行的操作</strong></p></td>
<td align="left"><p>使用下表中的信息，使用 <code>HKLM\Software\Microsoft\AppV\Server</code> 您在原始服务器安装中提供的值更新下的每个注册表项值。 完成此步骤将还原在安装 app-v SP1 修补程序包时可能已删除的注册表值。</p></td>
</tr>
</tbody>
</table>



**ManagementDatabase 键**

如果要安装管理数据库，请在 "" 下设置这些注册表项 `HKLM\Software\Microsoft\AppV\Server\ManagementDatabase` 。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">键名</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</p></td>
<td align="left"><p>描述访问非本地管理数据库是否需要公共访问帐户。 如果需要，值设置为 "1"。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MANAGEMENT_DB_NAME</p></td>
<td align="left"><p>管理数据库的名称。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT</p></td>
<td align="left"><p>用于读取（公共）访问管理数据库的帐户。</p>
<p>在 <code>IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> 设置为1时使用。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_SID</p></td>
<td align="left"><p>用于读取（公共）访问管理数据库的帐户的安全标识符（SID）。</p>
<p>在 <code>IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> 设置为1时使用。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MANAGEMENT_DB_SQL_INSTANCE</p></td>
<td align="left"><p>管理数据库的 SQL Server 实例。</p>
<p>如果值为空，则使用默认数据库实例。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MANAGEMENT_DB_WRITE_ACCESS_ACCOUNT</p></td>
<td align="left"><p>用于写入（管理员）访问管理数据库的帐户。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MANAGEMENT_DB_WRITE_ACCESS_ACCOUNT_SID</p></td>
<td align="left"><p>用于写入（管理员）访问管理数据库的帐户的安全标识符（SID）。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</p></td>
<td align="left"><p>管理服务器远程计算机帐户（域 \ 帐户）。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</p></td>
<td align="left"><p>管理服务器（域 \ 帐户）的安装管理员登录。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MANAGEMENT_SERVER_MACHINE_USE_LOCAL</p></td>
<td align="left"><p>有效值为：</p>
<ul>
<li><p><strong>1 </strong> -管理服务位于本地计算机上，即 MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT 为空。</p></li>
<li><p><strong>0 </strong> - 管理服务位于本地计算机的不同计算机上。</p></li>
</ul></td>
</tr>
</tbody>
</table>



**ManagementService 键**

如果要安装管理服务器，请在 "" 下设置这些注册表项 `HKLM\Software\Microsoft\AppV\Server\ManagementService` 。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">键名</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>MANAGEMENT_ADMINACCOUNT</p></td>
<td align="left"><p>已授权管理 App-v （域 \ 帐户）的 Active Directory 域服务（AD DS）组或帐户。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MANAGEMENT_DB_SQL_INSTANCE</p></td>
<td align="left"><p>包含管理数据库的 SQL server 实例。</p>
<p>如果值为空，则使用默认数据库实例。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MANAGEMENT_DB_SQL_SERVER_NAME</p></td>
<td align="left"><p>带有管理数据库的远程 SQL server 的名称。</p>
<p>如果值为空，则使用本地计算机。</p></td>
</tr>
</tbody>
</table>



**ReportingDatabase 键**

如果要安装报告数据库，请在 "" 下设置这些注册表项 `HKLM\Software\Microsoft\AppV\Server\ReportingDatabase` 。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">键名</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</p></td>
<td align="left"><p>描述访问非本地报告数据库是否需要公共访问帐户。 如果需要，值设置为 "1"。</p></td>
</tr>
<tr class="even">
<td align="left"><p>REPORTING_DB_NAME</p></td>
<td align="left"><p>报告数据库的名称。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>REPORTING_DB_PUBLIC_ACCESS_ACCOUNT</p></td>
<td align="left"><p>用于对报告数据库进行读取（公共）访问的帐户。</p>
<p>在 <code>IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> 设置为1时使用。</p></td>
</tr>
<tr class="even">
<td align="left"><p>REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_SID</p></td>
<td align="left"><p>用于对报告数据库进行读取（公共）访问的帐户的安全标识符（SID）。</p>
<p>在 <code>IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> 设置为1时使用。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>REPORTING_DB_SQL_INSTANCE</p></td>
<td align="left"><p>报告数据库的 SQL Server 实例。</p>
<p>如果值为空，则使用默认数据库实例。</p></td>
</tr>
<tr class="even">
<td align="left"><p>REPORTING_DB_WRITE_ACCESS_ACCOUNT</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>REPORTING_DB_WRITE_ACCESS_ACCOUNT_SID</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</p></td>
<td align="left"><p>报表服务器远程计算机帐户（域 \ 帐户）。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</p></td>
<td align="left"><p>报告服务器（域 \ 帐户）的安装管理员登录。</p></td>
</tr>
<tr class="even">
<td align="left"><p>REPORTING_SERVER_MACHINE_USE_LOCAL</p></td>
<td align="left"><p>有效值为：</p>
<ul>
<li><p><strong>1 </strong> -报告服务在本地计算机上，即 REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT 为空。</p></li>
<li><p><strong>0 </strong> - 报告服务位于本地计算机的不同计算机上。</p></li>
</ul></td>
</tr>
</tbody>
</table>



**ReportingService 键**

如果要安装报表服务器，请在 "" 下设置这些注册表项 `HKLM\Software\Microsoft\AppV\Server\ReportingService` 。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">键名</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>REPORTING_DB_SQL_INSTANCE</p></td>
<td align="left"><p>报告数据库的 SQL Server 实例。</p>
<p>如果值为空，则使用默认数据库实例。</p></td>
</tr>
<tr class="even">
<td align="left"><p>REPORTING_DB_SQL_SERVER_NAME</p></td>
<td align="left"><p>带有报告数据库的远程 SQL 服务器的名称。</p>
<p>如果值为空，则使用本地计算机。</p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-update-schema-cg"></a>手动创建的连接组 xml 文件需要更新到架构


如果你要手动创建连接组 XML 文件，并且希望使用新的 "可选程序包" 和 "使用任何版本" 功能（将在 "[连接组](#bkmk-cg-improvements)" 的改进中介绍），必须在 XML 文件中指定以下架构：

`xmlns="http://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup"`

有关示例和详细信息，请参阅[关于连接组文件](about-the-connection-group-file.md)。

## <a href="" id="bkmk-cg-improvements"></a>对连接组的改进


通过使用 App-v 5.0 SP3 中添加的可选程序包和其他改进，可以更轻松地管理连接组。 下表总结了可使用新的连接组功能执行的任务，并提供了指向有关每个任务的更详细信息的链接。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">任务/功能</th>
<th align="left">描述</th>
<th align="left">指向详细信息的链接</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>启用连接组以包含可选程序包</p></td>
<td align="left"><p>在连接组中包含可选程序包后，你可以根据用户有权使用的应用程序，动态确定哪些应用程序将包含在连接组的虚拟环境中。</p>
<p>你不需要管理任意多个连接组，因为你可以在同一连接组中混合使用可选和非可选的程序包。 混合程序包允许不同组的用户使用相同的连接组，即使用户可能只有一个程序包。</p>
<p><strong>示例 </strong> ：你可以为所有用户启用 Microsoft Office 的程序包，但将包含不同 Office 插件的不同可选程序包启用为不同的用户子集。</p></td>
<td align="left"><p><a href="how-to-use-optional-packages-in-connection-groups.md#bkmk-apps-plugs-optional" data-raw-source="[How to Use Optional Packages in Connection Groups](how-to-use-optional-packages-in-connection-groups.md#bkmk-apps-plugs-optional)">如何使用连接组中的可选程序包</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>取消发布或删除可选程序包，而不更改连接组</p></td>
<td align="left"><p>取消发布或删除或取消发布和重新发布在连接组中的可选程序包，而无需在 App-v 客户端上禁用或重新启用连接组。</p></td>
<td align="left"><p><a href="how-to-use-optional-packages-in-connection-groups.md#bkmk-apps-plugs-optional" data-raw-source="[How to Use Optional Packages in Connection Groups](how-to-use-optional-packages-in-connection-groups.md#bkmk-apps-plugs-optional)">如何使用连接组中的可选程序包</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>发布包含用户发布和全局发布的程序包的连接组</p></td>
<td align="left"><p>创建一个用户发布的连接组，其中包含用户发布和全局发布的程序包。</p></td>
<td align="left"><p><a href="how-to-create-a-connection-group-with-user-published-and-globally-published-packages.md" data-raw-source="[How to Create a Connection Group with User-Published and Globally Published Packages](how-to-create-a-connection-group-with-user-published-and-globally-published-packages.md)">如何创建与用户发布和全局发布的程序包的连接组</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>使连接组忽略程序包版本</p></td>
<td align="left"><p>将连接组配置为接受程序包的任何版本，这使你可以升级程序包，而无需禁用连接组。 此外，如果在连接组中有一个可选程序包，并且该程序包的版本不正确，则会忽略该程序包，并且不会阻止创建连接组的虚拟环境。</p></td>
<td align="left"><p><a href="how-to-make-a-connection-group-ignore-the-package-version.md" data-raw-source="[How to Make a Connection Group Ignore the Package Version](how-to-make-a-connection-group-ignore-the-package-version.md)">如何使连接组忽略程序包版本</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>限制最终用户的发布功能</p></td>
<td align="left"><p>仅允许管理员（而非最终用户）发布程序包和启用连接组。</p></td>
<td align="left"><p>有关连接组的信息，请参阅 <a href="how-to-allow-only-administrators-to-enable-connection-groups.md" data-raw-source="[How to Allow Only Administrators to Enable Connection Groups](how-to-allow-only-administrators-to-enable-connection-groups.md)"> 如何仅允许管理员启用连接组</a></p>
<p>有关程序包的详细信息，请参阅以下文章：</p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">方法</th>
<th align="left">链接到详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>管理控制台</p></td>
<td align="left"><p><a href="how-to-publish-a-package-by-using-the-management-console-50.md" data-raw-source="[How to Publish a Package by Using the Management Console](how-to-publish-a-package-by-using-the-management-console-50.md)">如何使用管理控制台发布程序包</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>PowerShell</p></td>
<td align="left"><p><a href="how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admin-only-posh-topic-cg" data-raw-source="[How to Manage Connection Groups on a Stand-alone Computer by Using PowerShell](how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admin-only-posh-topic-cg)">如何使用 PowerShell 管理独立计算机上的连接组</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>第三方电子软件交付系统</p></td>
<td align="left"><p><a href="how-to-enable-only-administrators-to-publish-packages-by-using-an-esd.md" data-raw-source="[How to Enable Only Administrators to Publish Packages by Using an ESD](how-to-enable-only-administrators-to-publish-packages-by-using-an-esd.md)">如何使用 ESD 来仅允许管理员发布程序包</a></p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
<tr class="even">
<td align="left"><p>为特定用户启用或禁用连接组</p></td>
<td align="left"><p>管理员可以通过将 optional <strong> -UserSID </strong> 参数与以下 cmdlet 结合使用来启用或禁用特定用户的连接组：</p>
<ul>
<li><p>Enable-AppVClientConnectionGroup</p></li>
<li><p>Disable-AppVClientConnectionGroup</p></li>
</ul></td>
<td align="left"><p><a href="how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell.md#bkmk-enable-cg-for-user-poshtopic" data-raw-source="[How to Manage Connection Groups on a Stand-alone Computer by Using PowerShell](how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell.md#bkmk-enable-cg-for-user-poshtopic)">如何使用 PowerShell 管理独立计算机上的连接组</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>将相同的包路径合并到连接组中的一个虚拟目录中</p></td>
<td align="left"><p>如果连接组中的两个或多个程序包包含相同的目录路径，则路径将合并到连接组虚拟环境内的单个虚拟目录中。</p>
<p>这种路径合并允许一个程序包中的应用程序访问不同程序包中的文件。</p></td>
<td align="left"><p><a href="about-the-connection-group-virtual-environment.md#bkmk-merged-root-ve-exp" data-raw-source="[About the Connection Group Virtual Environment](about-the-connection-group-virtual-environment.md#bkmk-merged-root-ve-exp)">关于连接组虚拟环境</a></p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-usersid-pub-pkgs-specf-user"></a>管理员可以发布和取消发布特定用户的程序包


管理员可以使用以下 cmdlet 发布或取消发布特定用户的程序包。 若要使用 cmdlet，请输入 **-UserSID**参数，后跟用户的安全标识符（SID）。 有关详细信息，请参阅：

-   [如何使用 PowerShell 管理在独立计算机上运行的 App-V 5.0 程序包](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md#bkmk-pub-pkg-a-user-standalone-posh)

-   [如何使用 PowerShell 管理在独立计算机上运行的 App-V 5.0 程序包](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md#bkmk-unpub-pkg-specfc-use)

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Cmdlet</th>
<th align="left">示例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>发布-AppvClientPackage</p></td>
<td align="left"><p>发布-AppvClientPackage "ContosoApplication"-UserSID S-1-2-34-56789012-3456789012-345678901-2345</p></td>
</tr>
<tr class="even">
<td align="left"><p>取消发布-AppvClientPackage</p></td>
<td align="left"><p>取消发布-AppvClientPackage "ContosoApplication"-UserSID S-1-2-34-56789012-3456789012-345678901-2345</p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-admins-only-pub-unpub-pkgs"></a>仅启用管理员发布和取消发布程序包


你可以使用以下方法之一，仅允许管理员（而非最终用户）发布和取消发布程序包：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">方法</th>
<th align="left">详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>组策略设置</p></td>
<td align="left"><p>导航到以下组策略对象节点：</p>
<p><strong>计算机配置 &gt; 策略 &gt; 管理模板 &gt; 系统 &gt; 应用程序-V &gt; 发布 </strong> 。</p>
<p>启用 " <strong> 要求发布为管理员 </strong> 组" 策略设置。</p></td>
</tr>
<tr class="even">
<td align="left"><p>PowerShell</p></td>
<td align="left"><p><a href="how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admins-pub-pkgs" data-raw-source="[How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admins-pub-pkgs)">如何使用 PowerShell 管理在独立计算机上运行的 App-V 5.0 程序包</a></p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-runvirtual-reg-key"></a>RunVirtual 注册表项支持发布到用户的程序包


App-v 5.0 SP3 添加了对将**RunVirtual**注册表项与用户发布的程序包中的虚拟化应用程序配合使用的支持。 **RunVirtual**注册表项允许你在虚拟环境中运行本地安装的应用程序，以及已使用 app-v 虚拟化的应用程序。

以前，app-v 程序包中的虚拟化应用程序必须全局发布。 有关**RunVirtual**和其他使用虚拟化应用程序在虚拟环境中运行本地安装的应用程序的方法的详细信息，请参阅在[虚拟环境中使用虚拟化应用程序运行本地安装的应用程序](running-a-locally-installed-application-inside-a-virtual-environment-with-virtualized-applications.md)。

## <a href="" id="bkmk-posh-cmdlets-help"></a>新增 PowerShell cmdlet 和可更新 cmdlet 帮助


App-v 5.0 SP3 中包含新的 PowerShell cmdlet 和可更新的 cmdlet 帮助。 若要下载 cmdlet 模块，请参阅[如何加载 PowerShell cmdlet 和获取 Cmdlet 帮助](how-to-load-the-powershell-cmdlets-and-get-cmdlet-help-50-sp3.md#bkmk-load-cmdlets)。

### 新的 App-v 5.0 SP3 服务器 PowerShell cmdlet

已添加用于 App-v 服务器的新 Windows PowerShell cmdlet，以帮助你管理连接组。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Cmdlet</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Add-AppvServerConnectionGroupPackage</p></td>
<td align="left"><p>将程序包追加到连接组的末尾&#39;s 程序包列表，使你能够将程序包配置为可选和/或在连接组中不使用任何版本。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Set-AppvServerConnectionGroupPackage</p></td>
<td align="left"><p>使你能够编辑有关连接组程序包的详细信息，例如它是否是可选的。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Remove-AppvServerConnectionGroupPackage</p></td>
<td align="left"><p>从连接组中删除程序包。</p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-get-cmdlet-help"></a>获取有关 PowerShell cmdlet 的帮助

Cmdlet 帮助可采用以下格式：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">格式</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>作为可下载的模块</p></td>
<td align="left"><p>下载 cmdlet 模块后获取最新帮助：</p>
<ol>
<li><p>打开 Windows PowerShell 或 Windows PowerShell 集成脚本环境（ISE）。</p></li>
<li><p>键入以下命令之一，为所需的模块加载 cmdlet：</p></li>
</ol>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">App-v 组件</th>
<th align="left">要键入的命令</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-v 服务器</p></td>
<td align="left"><p>Update-Help-Module AppvServer</p></td>
</tr>
<tr class="even">
<td align="left"><p>App-v 排序器</p></td>
<td align="left"><p>Update-Help-Module AppvSequencer</p></td>
</tr>
<tr class="odd">
<td align="left"><p>App-v 客户端</p></td>
<td align="left"><p>Update-Help-Module AppvClient</p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
<tr class="even">
<td align="left"><p>在 TechNet 上作为网页</p></td>
<td align="left"><p>在 <a href="https://technet.microsoft.com/library/dn520245.aspx" data-raw-source="[Microsoft Desktop Optimization Pack Automation with Windows PowerShell](https://technet.microsoft.com/library/dn520245.aspx)"> Windows PowerShell 的 Microsoft 桌面优化包自动化下，查看 app-v 节点 </a> 。</p></td>
</tr>
</tbody>
</table>



有关详细信息，请参阅[如何加载 PowerShell cmdlet 和获取 Cmdlet 帮助](how-to-load-the-powershell-cmdlets-and-get-cmdlet-help-50-sp3.md)。

## <a href="" id="bkmk-pvad-hidden"></a>主虚拟应用程序目录（PVAD）已隐藏，但可以启用


主虚拟应用程序目录（PVAD）在 App-v 5.0 SP3 中处于隐藏状态，但你可以将其重新打开并使用以下方法之一使其可见：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">方法</th>
<th align="left">步骤</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>使用命令行参数</p></td>
<td align="left"><p><strong>将– EnablePVADControl </strong> 参数传递到 <strong>Sequencer.exe</strong> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>创建注册表子项</p></td>
<td align="left"><ol>
<li><p>在注册表编辑器中，导航到： <code>HKLM\SOFTWARE\Microsoft\AppV\Sequencer\Compatibility</code></p>
<div class="alert">
<strong>注意</strong><br/><p>如果该 <code>Compatibility</code> 子项不存在，则必须创建它。</p>
</div>
<div>

</div></li>
<li><p>创建名为 EnablePVADControl 的 DWORD 值 <strong> </strong> ，并将该值设置为 <strong> 1 </strong> 。</p>
<p>值为 <strong> 0 </strong> 意味着 PVAD 已隐藏。</p></li>
</ol></td>
</tr>
</tbody>
</table>



**有关 PVAD 的详细信息：** 使用排序器创建程序包时，可以为程序包输入任何安装路径。 在早期版本的 App-v 中，你需要将应用程序的主虚拟应用程序目录（PVAD）指定为 path。 PVAD 是你通常在本地计算机上安装应用程序（如果你未使用 App-v）的目录。 例如，如果在计算机上安装 Office，则 PVAD 通常会 C:\\program files Files\\Microsoft Office\\。

## <a href="" id="bkmk-pub-metadata-clientversion"></a>需要 ClientVersion，才能查看 App-v 发布元数据


在 App-v 5.0 SP3 中，当你查询用于元数据的 app-v 发布服务器时，必须在地址中提供以下值：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">值</th>
<th align="left">其他详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>ClientVersion</strong></p></td>
<td align="left"><p>如果省略查询中的 <strong> ClientVersion </strong> 参数，则元数据将排除新的 APP-V 5.0 SP3 功能。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>ClientOS</strong></p></td>
<td align="left"><p>只有在对程序包进行排序时选择特定客户端操作系统时，才必须提供此值。 如果选择 "默认（所有操作系统）"，请不要在查询中指定此值。</p>
<p>如果省略查询中的 <strong> ClientOS </strong> 参数，则只有已排序支持任何操作系统的程序包才会显示在元数据中。</p></td>
</tr>
</tbody>
</table>



有关此查询的语法和示例，请参阅[查看 App-v 服务器发布元数据](viewing-app-v-server-publishing-metadata.md)。

## <a href="" id="bkmk-event-logs-moved"></a>App-v 事件日志已合并


以下事件日志（以前位于**应用程序和服务日志/microsoft/appv/app-v &lt; 组件 &gt; **上）已被移动到**应用程序和服务日志/microsoft/appv/ServiceLog**。

若要查看日志，请**View**选择 &gt; 事件查看器应用程序中的 "查看**显示分析日志和调试日志**"。

客户端目录客户端-集成客户端-PackageConfig 客户端-脚本客户端-服务客户端-Vemgr 客户端-VFSC FilesystemMetadataLibrary ManifestLibrary PolicyLibrary 子系统--AppPath 子系统-fta

## 如何获取 MDOP 技术


App-v 是 Microsoft 桌面优化包（MDOP）的一部分。 MDOP 是 Microsoft 软件保障的一部分。 有关 Microsoft 软件保证和获取 MDOP 的详细信息，请参阅[如何获取 mdop](https://go.microsoft.com/fwlink/?LinkId=322049)。






## 相关主题


[App-V 5.0 SP3 发行说明](release-notes-for-app-v-50-sp3.md)









