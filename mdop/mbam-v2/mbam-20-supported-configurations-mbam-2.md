---
title: MBAM 2.0 支持的配置
description: MBAM 2.0 支持的配置
author: dansimp
ms.assetid: dca63391-39fe-4273-a570-76d0a2f8a0fd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 8f314adcf818c1bdb17b0b239a7469f97fa849e4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803462"
---
# MBAM 2.0 支持的配置


本主题通过使用独立拓扑指定在你的环境中安装和运行 Microsoft BitLocker 管理和监视（MBAM）2.0 的要求。 有关适用于更高版本的受支持的配置，请参阅适用版本的文档。

如果你计划通过使用 Configuration Manager 拓扑安装 MBAM 2.0 并希望查看系统要求的列表，请参阅[计划使用 Configuration Manager 部署 MBAM](planning-to-deploy-mbam-with-configuration-manager-2.md)。

在生产环境中运行 MBAM 的推荐配置是两台服务器，具体取决于你的可伸缩性要求。 此配置最多支持 200000 MBAM 客户端。 有关独立 MBAM 服务器基础结构的图像和说明，请参阅[MBAM 2.0 的高级别体系结构](high-level-architecture-for-mbam-20-mbam-2.md)。

**注意** Microsoft 提供对当前服务包的支持，在某些情况下，还提供了之前的服务包。 若要查找产品的支持时间表，请参阅[支持生命周期的服务包](https://go.microsoft.com/fwlink/p/?LinkId=31975)。 有关 Microsoft 支持生命周期策略的其他信息，请参阅[Microsoft 支持生命周期支持策略常见问题解答](https://go.microsoft.com/fwlink/p/?LinkId=31976)。

 

## <a href="" id="---------mbam-server-system-requirements"></a> MBAM 服务器系统要求


### 服务器操作系统要求

下表列出了 Microsoft BitLocker 管理和监视服务器安装支持的操作系统。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">操作系统</th>
<th align="left">版本</th>
<th align="left">Service pack</th>
<th align="left">系统体系结构</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>WindowsServer2008 R2</p></td>
<td align="left"><p>标准版、企业版或数据中心版</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 位</p></td>
</tr>
<tr class="even">
<td align="left"><p>WindowsServer2012</p></td>
<td align="left"><p>标准版或数据中心版</p></td>
<td align="left"></td>
<td align="left"><p>64 位</p></td>
</tr>
</tbody>
</table>

 

**注意** 不支持在域控制器计算机上安装 MBAM 服务、报表或数据库。

 

### <a href="" id="server-processor--ram--and-disk-space-requirements-"></a>服务器处理器、RAM 和磁盘空间要求

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">硬件组件</th>
<th align="left">最低要求</th>
<th align="left">建议的要求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>处理者</p></td>
<td align="left"><p>2.33 GHz</p></td>
<td align="left"><p>2.33 GHz 或更高版本</p></td>
</tr>
<tr class="even">
<td align="left"><p>RAM</p></td>
<td align="left"><p>8 GB</p></td>
<td align="left"><p>12 GB</p></td>
</tr>
<tr class="odd">
<td align="left"><p>可用磁盘空间</p></td>
<td align="left"><p>1 GB</p></td>
<td align="left"><p>2 GB</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="sql-server-database-requirements-"></a>SQLServer 数据库要求

下表列出了管理和监视服务器功能安装支持的 SQLServer 版本，其中包括恢复数据库、合规性和审核数据库以及合规性和审核报告。 数据库还需要安装 SQL Server 管理工具。

**注意** MBAM 本身不支持 SQL 群集、镜像或可用性组。 若要安装数据库，必须在独立 SQL Server 上运行 MBAM Server 安装。

 

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">SQL Server 版本</th>
<th align="left">版本</th>
<th align="left">Service pack</th>
<th align="left">系统体系结构</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>MicrosoftSQLServer2008 R2</p></td>
<td align="left"><p>标准版、企业版或数据中心版</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 位</p></td>
</tr>
<tr class="even">
<td align="left"><p>MicrosoftSQLServer2012</p></td>
<td align="left"><p>标准版、企业版或数据中心版</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 位</p></td>
</tr>
</tbody>
</table>

 

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">硬件组件</th>
<th align="left">最低要求</th>
<th align="left">建议的要求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>处理者</p></td>
<td align="left"><p>2.33 GHz</p></td>
<td align="left"><p>2.33 GHz 或更高版本</p></td>
</tr>
<tr class="even">
<td align="left"><p>RAM</p></td>
<td align="left"><p>8 GB</p></td>
<td align="left"><p>12 GB</p></td>
</tr>
<tr class="odd">
<td align="left"><p>可用磁盘空间</p></td>
<td align="left"><p>5 GB</p></td>
<td align="left"><p>5 GB 或以上</p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="---------mbam-client-system-requirements"></a> MBAM 客户端系统要求


### 客户端操作系统要求

下表列出了 Microsoft BitLocker 管理和监视客户端安装支持的操作系统。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">操作系统</th>
<th align="left">版本</th>
<th align="left">Service pack</th>
<th align="left">系统体系结构</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows7</p></td>
<td align="left"><p>企业版或旗舰版</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>32 位或 64 位</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 8</p></td>
<td align="left"><p>企业版</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 位或 64 位</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows To Go</p></td>
<td align="left"><p>Windows 8 企业版</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 位或 64 位</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="client-ram-requirements-"></a>客户端 RAM 要求

不存在特定于 Microsoft BitLocker 管理和监视客户端安装的 RAM 要求。

## <a href="" id="---------mbam-group-policy-system-requirements"></a> MBAM 组策略系统要求


下表列出了 Microsoft BitLocker 管理和监视组策略模板安装所支持的操作系统。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">操作系统</th>
<th align="left">版本</th>
<th align="left">Service pack</th>
<th align="left">系统体系结构</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows7</p></td>
<td align="left"><p>企业版或旗舰版</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>32 位或 64 位</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 8</p></td>
<td align="left"><p>企业版</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 位或 64 位</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2008 R2</p></td>
<td align="left"><p>标准版、企业版或数据中心版</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 位</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2012</p></td>
<td align="left"><p>标准版或数据中心版</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 位</p></td>
</tr>
</tbody>
</table>

 

## 相关主题


[计划部署 MBAM 2.0](planning-to-deploy-mbam-20-mbam-2.md)

[MBAM 2.0 部署先决条件](mbam-20-deployment-prerequisites-mbam-2.md)

 

 





