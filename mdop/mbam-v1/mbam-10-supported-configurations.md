---
title: MBAM 1.0 支持的配置
description: MBAM 1.0 支持的配置
author: dansimp
ms.assetid: 1f5ac58e-6a3f-47df-8a9b-4b57631ab9ee
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 2c72320379d1c9328a6b40537d37998402b1b38b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803868"
---
# MBAM 1.0 支持的配置


本主题指定在你的环境中安装和运行 Microsoft BitLocker 管理和监视（MBAM）的必要要求。

## <a href="" id="---------mbam-server-system-requirements"></a> MBAM 服务器系统要求


### 服务器操作系统要求

下表列出了 Microsoft BitLocker 管理和监视服务器安装支持的操作系统。

**注意**  
Microsoft 提供对当前服务包的支持，在某些情况下，还提供了之前的服务包。 若要查找产品的支持时间表，请参阅[支持生命周期的服务包](https://go.microsoft.com/fwlink/p/?LinkId=31975)。 有关 Microsoft 支持生命周期策略的其他信息，请参阅[Microsoft 支持生命周期支持策略常见问题解答](https://go.microsoft.com/fwlink/p/?LinkId=31976)。



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
<th align="left">Service Pack</th>
<th align="left">系统体系结构</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows Server 2008</p></td>
<td align="left"><p>标准版、企业版、数据中心版或 Web 服务器</p></td>
<td align="left"><p>仅 SP2</p></td>
<td align="left"><p>32 位或 64 位</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2008 R2</p></td>
<td align="left"><p>标准版、企业版、数据中心版或 Web 服务器</p></td>
<td align="left"></td>
<td align="left"><p>64 位</p></td>
</tr>
</tbody>
</table>



**警告**  
不支持在域控制器计算机上安装 MBAM 服务、报表或数据库。



### <a href="" id="server-random-access-memory--ram--requirements-"></a>服务器随机访问内存（RAM）要求

没有特定于 MBAM 服务器安装的 RAM 要求。

### <a href="" id="sql-server-database-requirements-"></a>SQL Server 数据库要求

下表列出了 MBAM Server 功能安装支持的 SQL Server 版本。

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">MBAM Server 功能</th>
<th align="left">SQL Server 版本</th>
<th align="left">版本</th>
<th align="left">Service Pack</th>
<th align="left">系统体系结构</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>合规性和审核报告</p></td>
<td align="left"><p>Microsoft SQL Server 2008 </p></td>
<td align="left"><p>R2、Standard、Enterprise、Datacenter 或开发人员版本</p></td>
<td align="left"><p>SP2</p></td>
<td align="left"><p>32 位或 64 位</p></td>
</tr>
<tr class="even">
<td align="left"><p>恢复和硬件数据库</p></td>
<td align="left"><p>Microsoft SQL Server 2008 </p></td>
<td align="left"><p>R2、企业版、数据中心版或开发人员版</p>
<div class="alert">
<strong>重要提示</strong><br/><p>SQL Server 标准版不支持 MBAM 恢复和硬件数据库服务器功能安装。</p>
</div>
<div>

</div></td>
<td align="left"><p>SP2</p></td>
<td align="left"><p>32 位或 64 位</p></td>
</tr>
<tr class="odd">
<td align="left"><p>合规性和审核数据库</p></td>
<td align="left"><p>Microsoft SQL Server 2008 </p></td>
<td align="left"><p>R2、Standard、Enterprise、Datacenter 或开发人员版本</p></td>
<td align="left"><p>SP2</p></td>
<td align="left"><p>32 位或 64 位</p></td>
</tr>
</tbody>
</table>



## <a href="" id="---------mbam-client-system-requirements"></a> MBAM 客户端系统要求


### 客户端操作系统要求

下表列出了 MBAM 客户端安装支持的操作系统。

**注意**  
Microsoft 提供对当前服务包的支持，在某些情况下，还提供了之前的服务包。 若要查找产品的支持时间表，请参阅[支持生命周期的服务包](https://go.microsoft.com/fwlink/p/?LinkId=31975)。 有关 Microsoft 支持生命周期策略的其他信息，请参阅[Microsoft 支持生命周期支持策略常见问题解答](https://go.microsoft.com/fwlink/p/?LinkId=31976)。



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
<th align="left">Service Pack</th>
<th align="left">系统体系结构</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows 7</p></td>
<td align="left"><p>企业版</p></td>
<td align="left"><p>无、SP1</p></td>
<td align="left"><p>32 位或 64 位</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 7</p></td>
<td align="left"><p>旗舰版</p></td>
<td align="left"><p>无、SP1</p></td>
<td align="left"><p>32 位或 64 位</p></td>
</tr>
</tbody>
</table>



### <a href="" id="client-ram-requirements-"></a>客户端 RAM 要求

没有特定于 MBAM 客户端安装的 RAM 要求。

## 相关主题


[计划部署 MBAM 1.0](planning-to-deploy-mbam-10.md)

[MBAM 1.0 部署先决条件](mbam-10-deployment-prerequisites.md)









