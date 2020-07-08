---
title: MBAM 2.0 部署先决条件
description: MBAM 2.0 部署先决条件
author: dansimp
ms.assetid: 57d1c2bb-5ea3-457e-badd-dd9206ff0f20
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ef7ee64a3661009f18e0963d738c57a59885cb20
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803883"
---
# MBAM 2.0 部署先决条件


在开始 Microsoft BitLocker 管理和监视（MBAM）安装之前，应确保已满足安装该产品的先决条件。 本部分包含的信息可帮助你在部署 Microsoft BitLocker 管理和监视服务器功能和客户端之前成功地计划你的计算环境。 如果你正在通过 Configuration Manager 安装 MBAM，请参阅[计划通过 Configuration manager](planning-to-deploy-mbam-with-configuration-manager-2.md)为其他先决条件部署 MBAM。

## MBAM 服务器功能的安装先决条件


每个 MBAM 服务器功能都具有特定的先决条件，必须先满足这些先决条件，然后才能成功安装 MBAM 功能。 MBAM 安装程序检查在安装开始之前是否满足所有先决条件。

### 管理和监视服务器的先决条件

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">必备</th>
<th align="left">详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>Windows Server Web 服务器角色</strong></p></td>
<td align="left"><p>此角色必须添加到 "管理和监视服务器" 功能支持的服务器操作系统。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Web 服务器（IIS）管理工具</strong></p></td>
<td align="left"><p>选择 " <strong> IIS 管理脚本和工具" </strong> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>SSL 证书</strong></p></td>
<td align="left"><p>可选。 若要保护客户端与 web 服务之间的通信，你必须获取并安装受信任的安全机构签名的证书。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Web 服务器角色服务</strong></p></td>
<td align="left"><p><strong>常见的 HTTP 功能：</strong></p>
<ul>
<li><p>静态内容</p></li>
<li><p>默认文档</p></li>
</ul>
<p><strong>应用程序开发：</strong></p>
<ul>
<li><p>ASP.NET</p></li>
<li><p>.NET 扩展性</p></li>
<li><p>ISAPI 扩展</p></li>
<li><p>ISAPI 筛选器</p></li>
</ul>
<p><strong>安全</strong></p>
<ul>
<li><p>Windows 身份验证</p></li>
<li><p>请求筛选</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Windows Server 功能</strong></p></td>
<td align="left"><p><strong>.NET Framework 3.5.1 功能：</strong></p>
<ul>
<li><p>.NET Framework 3.5。1</p></li>
<li><p>WCF 激活</p>
<ul>
<li><p>HTTP 激活</p></li>
<li><p>非 HTTP 激活</p></li>
</ul></li>
</ul>
<p><strong>Windows 进程激活服务：</strong></p>
<ul>
<li><p>流程模型</p></li>
<li><p>.NET 环境</p></li>
<li><p>配置 Api</p></li>
</ul></td>
</tr>
</tbody>
</table>



**注意**  
有关受支持的操作系统的列表，请参阅[MBAM 2.0 支持的配置](mbam-20-supported-configurations-mbam-2.md)。



### 合规性和审核报告的先决条件

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">必备</th>
<th align="left">详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>SQL Server 支持的版本</p>
<p><a href="mbam-20-supported-configurations-mbam-2.md" data-raw-source="[MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md)"> </a> 有关支持的版本，请参阅 MBAM 2.0 支持的配置。</p></td>
<td align="left"><p>通过以下方式安装 SQL Server：</p>
<ul>
<li><p>SQL_Latin1_General_CP1_CI_AS 排序规则</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>SQL Server Reporting Services （SSRS）</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>SSRS 实例权限–只有在从报表的单独服务器上安装数据库时才需要安装报表。</p></td>
<td align="left"><p>所需实例权限：</p>
<ul>
<li><p>创建文件夹</p></li>
<li><p>发布报表</p></li>
</ul>
<p>在 MBAM 服务器安装期间，必须安装并运行 SSRS。 在 "本机" 模式下配置 SSRS，而不是在未配置或 "SharePoint" 模式下配置。</p></td>
</tr>
</tbody>
</table>



### 恢复数据库的先决条件

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">必备</th>
<th align="left">详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>SQL Server 支持的版本</p>
<p><a href="mbam-20-supported-configurations-mbam-2.md" data-raw-source="[MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md)"> </a> 有关支持的版本，请参阅 MBAM 2.0 支持的配置。</p></td>
<td align="left"><p>通过以下方式安装 SQL Server：</p>
<ul>
<li><p>SQL_Latin1_General_CP1_CI_AS 排序规则</p></li>
<li><p>SQL Server 管理工具</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>所需的 SQL Server 权限</p></td>
<td align="left"><p>所需权限：</p>
<ul>
<li><p>SQL 实例登录服务器角色：</p>
<ul>
<li><p>dbcreator</p></li>
<li><p>processadmin</p></li>
</ul></li>
<li><p>SQL Server Reporting Services 实例权限：</p>
<ul>
<li><p>创建文件夹</p></li>
<li><p>发布报表</p></li>
</ul></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>SQL Server 中可用的可选安装透明数据加密（TDE）功能</p></td>
<td align="left"><p>TDE SQL Server 功能对数据和日志文件执行实时 i/o 加密和解密，这有助于你遵守各种行业中建立的许多法律、法规和指南。</p>
<div class="alert">
<strong>注意</strong><br/><p>TDE 执行数据库信息的实时解密，这意味着如果你在其下登录的帐户在 SQL Server 表中查看恢复密钥信息时有权访问数据库，则恢复密钥信息可见。</p>
</div>
<div>

</div>
<p>有关 TDE 的更多信息： <a href="mbam-20-security-considerations-mbam-2.md" data-raw-source="[MBAM 2.0 Security Considerations](mbam-20-security-considerations-mbam-2.md)"> MBAM 2.0 安全注意事项 </a> 。</p></td>
</tr>
</tbody>
</table>



### 合规性和审核数据库的先决条件

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">必备</th>
<th align="left">详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>SQL Server 支持的版本</p>
<p><a href="mbam-20-supported-configurations-mbam-2.md" data-raw-source="[MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md)"> </a> 有关支持的版本，请参阅 MBAM 2.0 支持的配置。</p></td>
<td align="left"><p>通过以下方式安装 SQL Server：</p>
<ul>
<li><p>SQL_Latin1_General_CP1_CI_AS 排序规则</p></li>
<li><p>SQL Server 管理工具</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>所需的 SQL Server 权限</p></td>
<td align="left"><p>所需权限：</p>
<ul>
<li><p>SQL 实例登录服务器角色：</p>
<ul>
<li><p>dbcreator</p></li>
<li><p>processadmin</p></li>
</ul></li>
<li><p>SQL Server Reporting Services 实例权限：</p>
<ul>
<li><p>创建文件夹</p></li>
<li><p>发布报表</p></li>
</ul></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>SQL Server 中的可选 "安装透明数据加密（TDE）" 功能。</p></td>
<td align="left"><p>TDE SQL Server 功能对数据和日志文件执行实时 i/o 加密和解密，这有助于你遵守各种行业中建立的许多法律、法规和指南。</p>
<div class="alert">
<strong>注意</strong><br/><p>TDE 执行数据库信息的实时解密，这意味着如果你在其下登录的帐户在 SQL Server 表中查看恢复密钥信息时有权访问数据库，则恢复密钥信息可见。</p>
</div>
<div>

</div>
<p>有关 TDE 的更多信息： <a href="mbam-20-security-considerations-mbam-2.md" data-raw-source="[MBAM 2.0 Security Considerations](mbam-20-security-considerations-mbam-2.md)"> MBAM 2.0 安全注意事项</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>在 MBAM 服务器安装期间，SQL Server 必须安装并运行数据库引擎服务。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>SQL Server 代理服务必须在所选 SQL Server 实例上运行并设置为 "自动启动"。</p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



### 自助服务门户的先决条件

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">必备</th>
<th align="left">详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows Server 支持的版本</p>
<p><a href="mbam-20-supported-configurations-mbam-2.md" data-raw-source="[MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md)"> </a> 有关支持的版本，请参阅 MBAM 2.0 支持的配置。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>ASP.NET MVC 2。0</p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=392270" data-raw-source="[ASP.NET MVC 2 download](https://go.microsoft.com/fwlink/?LinkId=392270)">ASP.NET MVC 2 下载</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>Web 服务 IIS 管理工具</p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



## MBAM 客户端的先决条件


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">必备</th>
<th align="left">详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>Windows 7 客户端仅 </strong> - 必须具有受信任的平台模块（TPM）功能。</p></td>
<td align="left"><p>TPM 版本必须为1.2 或更高版本。</p></td>
</tr>
<tr class="even">
<td align="left"><p>必须在 BIOS 中打开 TPM 芯片，并将其从操作系统中 resettable。</p></td>
<td align="left"><p>有关详细信息，请参阅 BIOS 文档。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>仅限 Windows 8 客户端 </strong> ：要让 MBAM 存储和管理 TPM 恢复密钥：必须关闭 tpm 自动预配，并且必须在部署 MBAM 之前将 MBAM 设置为 TPM 的所有者。 要关闭 TPM 自动预配，请参阅 <a href="https://go.microsoft.com/fwlink/?LinkId=286468" data-raw-source="[Disable-TpmAutoProvisioning](https://go.microsoft.com/fwlink/?LinkId=286468)"> 禁用-TpmAutoProvisioning </a> 。</p>
<ul>
<li><p>TPM 自动预配必须处于关闭状态。</p></li>
<li><p>在部署 MBAM 之前，必须将 MBAM 设置为 TPM 的所有者。</p></li>
</ul></td>
<td align="left"><p>要关闭 TPM 自动预配，请参阅 <a href="https://go.microsoft.com/fwlink/?LinkId=286468" data-raw-source="[Disable-TpmAutoProvisioning](https://go.microsoft.com/fwlink/?LinkId=286468)"> 禁用-TpmAutoProvisioning </a> 。</p>
<div class="alert">
<strong>注意</strong><br/><p>确保键盘、视频或鼠标直接连接，而不是通过键盘、视频或鼠标（KVM）切换器管理。 KVM 切换器可能会干扰计算机检测硬件实际存在的能力。</p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



## 相关主题


[计划部署 MBAM 2.0](planning-to-deploy-mbam-20-mbam-2.md)

[MBAM 2.0 支持的配置](mbam-20-supported-configurations-mbam-2.md)









