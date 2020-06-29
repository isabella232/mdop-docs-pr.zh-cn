---
title: 如何使用命令行安装 MBAM 服务器
description: 如何使用命令行安装 MBAM 服务器
author: dansimp
ms.assetid: 6ffc6d41-a793-42c2-b997-95ba47550648
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a689a2df77300300073b2731281004feac87305f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803809"
---
# 如何使用命令行安装 MBAM 服务器


你可以使用命令行使用独立或配置管理器拓扑安装 MBAM 服务器。 下面的命令行示例用于在单个服务器上部署 MBAM，这是一个仅应在测试环境中使用的体系结构。 将 MBAM 部署到生产环境（应具有多台服务器）时，你需要相应地更改命令行。

## 使用独立拓扑部署 MBAM 2.0 服务器的命令行


你可以使用与以下内容类似的命令行来安装具有独立拓扑的 MBAM 服务器。

``` syntax
MbamSetup.exe /qb /l*v MaltaServerInstall.log TOPOLOGY=0 I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 ADDLOCAL=KeyDatabase,ReportsDatabase,Reports,AdministrationMonitoringServer,SelfServiceServer,PolicyTemplate,REPORTS_USERACCOUNT=[UserDomain]\[UserName1] REPORTS_USERACCOUNTPW=[UserPwd1] COMPLIDB_SQLINSTANCE=%computername% RECOVERYANDHWDB_SQLINSTANCE=%computername% SRS_INSTANCENAME=%computername% ADMINANDMON_WEBSITE_PORT=83 WEBSITE_PORT=83
```

下表介绍了用于使用独立拓扑部署 MBAM 服务器的命令行参数。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">参数</th>
<th align="left">参数值</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>拓扑</p></td>
<td align="left"><p>0</p></td>
<td align="left"><p>0-独立拓扑</p></td>
</tr>
<tr class="even">
<td align="left"><p>I_ACCEPT_ENDUSER_LICENSE_AGREEMENT</p></td>
<td align="left"><p>01</p></td>
<td align="left"><p>0–不接受许可证 agreement1 –接受许可协议</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ADDLOCAL</p></td>
<td align="left"><p></p></td>
<td align="left"><p>要在服务器上安装的功能</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p>KeyDatabase</p></td>
<td align="left"><p>恢复数据库</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p>ReportsDatabase</p></td>
<td align="left"><p>合规性和审核报告数据库</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p>报告</p></td>
<td align="left"><p>合规性和审核报告</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p>AdministrationMonitoringServer</p></td>
<td align="left"><p>管理和监视网站</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p>SelfServiceServer</p></td>
<td align="left"><p>自助服务门户</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p>PolicyTemplate</p></td>
<td align="left"><p>MBAM 组策略模板</p></td>
</tr>
<tr class="even">
<td align="left"><p>REPORTS_USERACCOUNT</p></td>
<td align="left"><p>[UserDomain][UserName1]</p></td>
<td align="left"><p>将访问合规性和审核数据库的 Reporting Services 服务帐户的域和用户帐户</p></td>
</tr>
<tr class="odd">
<td align="left"><p>REPORTS_USERACCOUNTPW</p></td>
<td align="left"><p>[UserPwd1]</p></td>
<td align="left"><p>将访问合规性和审核数据库的 Reporting Services 服务帐户的密码</p></td>
</tr>
<tr class="even">
<td align="left"><p>COMPLIDB_SQLINSTANCE</p></td>
<td align="left"><p>名</p></td>
<td align="left"><p>合规性和审核数据库的 SQL Server 实例名称–将 <strong> % computername% 替换 </strong> 为计算机名称</p></td>
</tr>
<tr class="odd">
<td align="left"><p>RECOVERYANDHWDB_SQLINSTANCE</p></td>
<td align="left"><p>名</p></td>
<td align="left"><p>恢复数据库的 SQL Server 实例名称–将 <strong> % computername% 替换 </strong> 为计算机名称</p></td>
</tr>
<tr class="even">
<td align="left"><p>SRS_INSTANCENAME</p></td>
<td align="left"><p>名</p></td>
<td align="left"><p>将安装合规性和审核报告的 SQL Server Reporting Server 实例–将 <strong> % computername% 替换 </strong> 为计算机名称</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ADMINANDMON_WEBSITE_PORT</p></td>
<td align="left"><p>83</p></td>
<td align="left"><p>管理和监视网站的端口;"83" 只是一个示例</p></td>
</tr>
<tr class="even">
<td align="left"><p>WEBSITE_PORT</p></td>
<td align="left"><p>83</p></td>
<td align="left"><p>自助服务门户网站的端口;"83" 只是一个示例</p></td>
</tr>
</tbody>
</table>

 

## 用于通过 Configuration Manager 拓扑部署 MBAM 2.0 服务器的命令行


你可以使用与以下内容类似的命令行来使用 Configuration Manager 拓扑安装 MBAM 服务器。

``` syntax
MbamSetup.exe /qn /l*v MaltaServerInstall.log I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 TOPOLOGY=1 COMPLIDB_SQLINSTANCE=%computername% RECOVERYANDHWDB_SQLINSTANCE=%computername% SRS_INSTANCENAME=%computername% REPORTS_USERACCOUNT=[UserDomain]\[UserName] REPORTS_USERACCOUNTPW=[UserPwd] ADMINANDMON_WEBSITE_PORT=83 WEBSITE_PORT=83
```

下表介绍了用于通过 Configuration Manager 拓扑安装 MBAM 2.0 服务器的命令行参数。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">参数</th>
<th align="left">参数值</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>拓扑</p></td>
<td align="left"><p>raid-1</p></td>
<td align="left"><p>1-配置管理器拓扑</p></td>
</tr>
<tr class="even">
<td align="left"><p>I_ACCEPT_ENDUSER_LICENSE_AGREEMENT</p></td>
<td align="left"><p>01</p></td>
<td align="left"><p>0–不接受许可证 agreement1 –接受许可协议</p></td>
</tr>
<tr class="odd">
<td align="left"><p>COMPLIDB_SQLINSTANCE</p></td>
<td align="left"><p>名</p></td>
<td align="left"><p>审核数据库的 SQL Server 实例名称–将 <strong> % computername% 替换 </strong> 为计算机名称</p></td>
</tr>
<tr class="even">
<td align="left"><p>RECOVERYANDHWDB_SQLINSTANCE</p></td>
<td align="left"><p>名</p></td>
<td align="left"><p>恢复数据库的 SQL Server 实例名称-将 <strong> % computername% 替换为 </strong> 计算机名称</p></td>
</tr>
<tr class="odd">
<td align="left"><p>SRS_INSTANCENAME</p></td>
<td align="left"><p>名</p></td>
<td align="left"><p>将安装审核报告的 SQL Server Reporting Server 实例–将% computername% 替换为计算机名称</p></td>
</tr>
<tr class="even">
<td align="left"><p>REPORTS_USERACCOUNT</p></td>
<td align="left"><p>[UserDomain][UserName1]</p></td>
<td align="left"><p>将访问合规性和审核数据库的 Reporting Services 服务帐户的域和用户帐户</p></td>
</tr>
<tr class="odd">
<td align="left"><p>REPORTS_USERACCOUNTPW</p></td>
<td align="left"><p>[UserPwd1]</p></td>
<td align="left"><p>将访问合规性和审核数据库的 Reporting Services 服务帐户的密码</p></td>
</tr>
<tr class="even">
<td align="left"><p>ADMINANDMON_WEBSITE_PORT</p></td>
<td align="left"><p>83</p></td>
<td align="left"><p>管理和监视网站的端口;"83" 只是一个示例</p></td>
</tr>
<tr class="odd">
<td align="left"><p>WEBSITE_PORT</p></td>
<td align="left"><p>83</p></td>
<td align="left"><p>自助服务门户网站的端口;"83" 只是一个示例</p></td>
</tr>
</tbody>
</table>

 

## 相关主题


[部署 MBAM 2.0 服务器基础结构](deploying-the-mbam-20-server-infrastructure-mbam-2.md)

 

 





