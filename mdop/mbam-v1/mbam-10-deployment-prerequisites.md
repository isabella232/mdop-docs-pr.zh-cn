---
title: MBAM 1.0 部署先决条件
description: MBAM 1.0 部署先决条件
author: dansimp
ms.assetid: bd9e1010-7d25-43e7-8dc6-b521226a659d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6ed14343d37a859364bcabbe6ca72c041502a23c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803213"
---
# MBAM 1.0 部署先决条件


在开始 Microsoft BitLocker 管理和监视（MBAM）安装之前，请确保满足安装该产品所必需的先决条件。 本部分包含的信息可帮助你在部署 MBAM 客户端和服务器功能之前成功准备你的计算环境。

## MBAM 服务器功能的安装先决条件


每个 MBAM 服务器功能都具有特定的先决条件，必须先满足这些先决条件，然后才能成功安装它们。 MBAM 安装程序将验证在安装开始之前是否满足所有先决条件。

### 管理和监视服务器的安装先决条件

下表包含 MBAM 管理和监视服务器的安装先决条件：

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
<td align="left"><p><strong>Windows ServerWeb 服务器角色</strong></p></td>
<td align="left"><p>此角色必须添加到 mbam 管理和监视服务器功能支持的服务器操作系统。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Web 服务器（IIS）管理工具</strong></p></td>
<td align="left"><p><strong>IIS 管理脚本和工具</strong></p></td>
</tr>
<tr class="odd">
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
<tr class="even">
<td align="left"><p><strong>Windows Server 功能</strong></p></td>
<td align="left"><p><strong>Microsoft .NET Framework 3.5.1 功能：</strong></p>
<ul>
<li><p>.NET Framework 3.5。1</p></li>
<li><p>WCF 激活</p>
<ul>
<li><p>HTTP 激活</p></li>
<li><p>非 HTTP 激活</p></li>
</ul></li>
</ul>
<p><strong>Windows Process Activation Service</strong></p>
<ul>
<li><p>流程模型</p></li>
<li><p>.NET 环境</p></li>
<li><p>配置 Api</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

**注意** 有关受支持的操作系统的列表，请参阅[MBAM 1.0 支持的配置](mbam-10-supported-configurations.md)。

 

### 合规性和审核报告的安装先决条件

必须在支持的 SQLServer 版本上安装合规性和审核报告。 此功能的安装先决条件包括 SQL Server Reporting Services （SSRS）。

在 MBAM 服务器安装期间，必须安装并运行 SSRS。 SSRS 还应在 "本机" 模式下配置，而不是在 "未配置" 或 "SharePoint" 模式下进行配置。

**注意** 有关受支持的操作系统和 SQLServer 版本的列表，请参阅[MBAM 1.0 支持的配置](mbam-10-supported-configurations.md)。

 

### 恢复和硬件数据库的安装先决条件

恢复和硬件数据库必须安装在支持的 SQLServer 版本上。

SQL Server 必须在 MBAM 服务器安装期间安装并运行数据库引擎服务。 必须启用透明数据加密（TDE）功能。

**注意** 有关受支持的操作系统和 SQLServer 版本的列表，请参阅[MBAM 1.0 支持的配置](mbam-10-supported-configurations.md)。

 

TDE SQLServer 功能执行实时输入/输出（i/o）加密以及数据和日志文件的解密。 TDE 保护 "静止" 数据，其中包括数据和日志文件。 它使您能够遵守各种行业中建立的许多法律、法规和指南。

**注意** 由于 TDE 执行数据库信息的实时解密，因此，当你登录时所用的帐户在你查看恢复密钥信息 SQL 表时具有数据库的权限时，将显示恢复密钥信息。

 

### 符合性和审核数据库的安装先决条件

合规性和审核数据库必须安装在支持的 SQLServer 版本上。

在 MBAM 服务器安装期间，SQL Server 必须安装并运行数据库引擎服务。

**注意** 有关受支持的操作系统和 SQLServer 版本的列表，请参阅[MBAM 1.0 支持的配置](mbam-10-supported-configurations.md)。

 

## MBAM 客户端的安装先决条件


开始 MBAM 客户端安装之前必须满足的必需先决条件如下所示：

-   受信任的平台模块（TPM） v 1.2 功能

-   TPM 芯片必须在 BIOS 中打开，并且必须从操作系统 resettable。 有关详细信息，请参阅 BIOS 文档。

**警告** 确保键盘、鼠标和视频直接连接到计算机，而不是键盘、视频、鼠标（KVM）开关。 KVM 切换器可能会干扰计算机检测硬件实际存在的能力。

 

## 相关主题


[计划部署 MBAM 1.0](planning-to-deploy-mbam-10.md)

[MBAM 1.0 支持的配置](mbam-10-supported-configurations.md)

 

 





