---
title: 在安装 App-V 5.x Server 前检查注册表项
description: 在安装 App-V 5.x Server 前检查注册表项
author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.openlocfilehash: 9fe5a1b37d0fb5208d138939bb2fc79c89171fb3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798613"
---
# 在安装 App-V 5.x Server 前检查注册表项

如果你要从 App-v 5.0 SP1 修补程序包3或更高版本升级 app-v 服务器，请先完成本节中的步骤，然后再安装 app-v 5 a.x 服务器

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>需要执行此步骤时</strong></p></td>
<td align="left"><p>从 App-v 5.0 SP1 升级到使用 .msp 文件安装的任何后续修补程序包。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>哪些组件需要执行此步骤</strong></p></td>
<td align="left"><p>仅限你要升级的 app-v Server 组件。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>需要执行此步骤时</strong></p></td>
<td align="left"><p>在将 app-v Server 升级到 App-v 5 之前。 x</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>需要执行的操作</strong></p></td>
<td align="left"><p>使用下表中的信息，使用 <code>HKLM\Software\Microsoft\AppV\Server</code> 您在原始服务器安装中提供的值更新下的每个注册表项值。 完成此步骤将还原在安装 app-v 5.0 SP1 修补程序包时可能已删除的注册表值。</p></td>
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

