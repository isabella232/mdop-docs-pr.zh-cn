---
title: Application Virtualization System 要求
description: Application Virtualization System 要求
author: dansimp
ms.assetid: a2798dd9-168e-45eb-8103-e12e128fae7c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c160a7532b521bb41570b419b22b9e7daaec2987
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802248"
---
# Application Virtualization System 要求


本主题介绍 Microsoft Application Virtualization （app-v）管理服务器和流服务器的最低硬件和软件要求。

## 应用程序虚拟化管理和流服务器


下表列出了 app-v Management Server 和 App-v 流式处理服务器建议的最低硬件和软件要求。

### 硬件要求

-   处理器-英特尔奔腾 III，1 GHz

-   RAM — 512 MB

-   磁盘空间-200 MB 可用硬盘空间，不包括内容目录

### 软件要求

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
<td align="left"><p>Windows Server2003</p></td>
<td align="left"><p>标准版</p></td>
<td align="left"><p>SP1 或 SP2</p></td>
<td align="left"><p>x86 或 x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2003</p></td>
<td align="left"><p>企业版或数据中心版</p></td>
<td align="left"><p>SP1 或 SP2</p></td>
<td align="left"><p>x86 或 x64</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2003 R2</p></td>
<td align="left"><p>标准版</p></td>
<td align="left"><p>无服务包或 SP2</p></td>
<td align="left"><p>x86 或 x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2003 R2</p></td>
<td align="left"><p>企业版或数据中心版</p></td>
<td align="left"><p>无服务包或 SP2</p></td>
<td align="left"><p>x86 或 x64</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008</p></td>
<td align="left"><p>标准版、企业版或数据中心版</p></td>
<td align="left"><p>SP1 或 SP2</p></td>
<td align="left"><p>x86 或 x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008 R2 ¹</p></td>
<td align="left"><p>标准版、企业版或数据中心版</p></td>
<td align="left"><p></p></td>
<td align="left"><p>x64</p></td>
</tr>
</tbody>
</table>

 

¹仅适用于 App-v 4.5 SP1 和 SP2。

## 数据存储


下表列出了在单独的服务器上安装数据存储时所使用的计算机建议的最低硬件和软件要求。 只有应用程序虚拟化管理服务器才需要数据存储。

### 硬件要求

-   处理器-英特尔奔腾 III，850 MHz

-   RAM — 512 MB

-   磁盘空间-200 MB 可用硬盘空间

### 软件要求

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
<td align="left"><p>Windows Server2003</p></td>
<td align="left"><p>标准版</p></td>
<td align="left"><p>SP1 或 SP2</p></td>
<td align="left"><p>x86 或 x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2003</p></td>
<td align="left"><p>企业版或数据中心版</p></td>
<td align="left"><p>SP1 或 SP2</p></td>
<td align="left"><p>x86 或 x64</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2003 R2</p></td>
<td align="left"><p>标准版</p></td>
<td align="left"><p>无服务包或 SP2</p></td>
<td align="left"><p>x86 或 x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2003 R2</p></td>
<td align="left"><p>企业版或数据中心版</p></td>
<td align="left"><p>无服务包或 SP2</p></td>
<td align="left"><p>x86 或 x64</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008</p></td>
<td align="left"><p>标准版、企业版或数据中心版</p></td>
<td align="left"><p>SP1 或 SP2</p></td>
<td align="left"><p>x86 或 x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008 R2 ¹</p></td>
<td align="left"><p>标准版、企业版或数据中心版</p></td>
<td align="left"><p></p></td>
<td align="left"><p>x64</p></td>
</tr>
</tbody>
</table>

 

¹仅适用于 App-v 4.5 SP1 和 SP2。

-   数据库-Microsoft SQL Server2000 SP3a 或 SP4、SQL Server2005 SP1、SP2 或 SP3，或者 SQL Server2008 没有 service pack 或 SP1 或 SQL Server2008 R2 （32位或64位）

-   Microsoft 数据访问组件-MDAC 2。7

-   域控制器-作为中央身份验证机构的 Active Directory 域服务或基于 Windows NT 4.0 的主域控制器（PDC）

## 管理 Web 服务


下表列出了在单独的计算机上安装应用程序虚拟化管理 Web 服务时建议的最低硬件和软件要求。

### 硬件要求

-   处理器-英特尔奔腾 III，800 MHz

-   RAM-256 MB

-   磁盘空间-50 MB 可用硬盘空间

### 软件要求

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
<td align="left"><p>Windows Server2003</p></td>
<td align="left"><p>标准版</p></td>
<td align="left"><p>SP1 或 SP2</p></td>
<td align="left"><p>x86 或 x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2003</p></td>
<td align="left"><p>企业版或数据中心版</p></td>
<td align="left"><p>SP1 或 SP2</p></td>
<td align="left"><p>x86 或 x64</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2003 R2</p></td>
<td align="left"><p>标准版</p></td>
<td align="left"><p>无服务包或 SP2</p></td>
<td align="left"><p>x86 或 x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2003 R2</p></td>
<td align="left"><p>企业版或数据中心版</p></td>
<td align="left"><p>无服务包或 SP2</p></td>
<td align="left"><p>x86 或 x64</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008</p></td>
<td align="left"><p>标准版、企业版或数据中心版</p></td>
<td align="left"><p>SP1 或 SP2</p></td>
<td align="left"><p>x86 或 x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008 R2 ¹</p></td>
<td align="left"><p>标准版、企业版或数据中心版</p></td>
<td align="left"><p></p></td>
<td align="left"><p>x64</p></td>
</tr>
</tbody>
</table>

 

¹仅适用于 App-v 4.5 SP1 和 SP2。

-   Internet information Services-Internet information Services （IIS）6.0 配置为 Microsoft ASP.NET，IIS 7

-   Microsoft .NET Framework 2。0

## 管理控制台


下表列出了在单独的计算机上安装应用程序虚拟化管理控制台时推荐的最低硬件和软件要求。

### 硬件要求

-   处理器-英特尔奔腾 III，450 MHz

-   RAM-256 MB

-   磁盘空间-200 MB 可用硬盘空间

### 软件要求

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
<td align="left"><p>WindowsXP</p></td>
<td align="left"><p>专业版</p></td>
<td align="left"><p>SP2 或 SP3</p></td>
<td align="left"><p>x86 或 x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Vista</p></td>
<td align="left"><p>企业版、企业版或旗舰版</p></td>
<td align="left"><p>无服务包、SP1 或 SP2</p></td>
<td align="left"><p>x86 或 x64</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows7</p></td>
<td align="left"><p>专业版、企业版或旗舰版</p></td>
<td align="left"><p></p></td>
<td align="left"><p>x86 或 x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2003</p></td>
<td align="left"><p>标准版、企业版或数据中心版</p></td>
<td align="left"><p>SP1 或 SP2</p></td>
<td align="left"><p>x86 或 x64</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2003 R2</p></td>
<td align="left"><p>标准版、企业版或数据中心版</p></td>
<td align="left"><p>无服务包或 SP2</p></td>
<td align="left"><p>x86 或 x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008</p></td>
<td align="left"><p>标准版、企业版或数据中心版</p></td>
<td align="left"><p>SP1 或 SP2</p></td>
<td align="left"><p>x86 或 x64</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008 R2 ¹</p></td>
<td align="left"><p>标准版、企业版或数据中心版</p></td>
<td align="left"><p></p></td>
<td align="left"><p>x64</p></td>
</tr>
</tbody>
</table>

 

¹仅适用于 App-v 4.5 SP1 和 SP2。

-   Microsoft 管理控制台-MMC 3.0 或更高版本

-   Microsoft .NET Framework 2.0 SP2 （最低）

    **重要提示** 如果必须在运行 app-v Management Console 的计算机上安装 app-v 修补程序 KB980850 或后续 App-v 修补程序，则最低要求为 .NET Framework 2.0 SP2。

     

## 相关主题


[Application Virtualization Client 硬件和软件要求](application-virtualization-client-hardware-and-software-requirements.md)

[Application Virtualization Sequencer 硬件和软件要求](application-virtualization-sequencer-hardware-and-software-requirements.md)

[如何为基于服务器的部署配置服务器](how-to-configure-servers-for-server-based-deployment.md)

[如何安装服务器和系统组件](how-to-install-the-servers-and-system-components.md)

[如何升级服务器和系统组件](how-to-upgrade-the-servers-and-system-components.md)

 

 





