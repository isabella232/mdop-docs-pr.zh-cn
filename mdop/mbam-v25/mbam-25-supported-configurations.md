---
title: MBAM 2.5 支持的配置
description: MBAM 2.5 支持的配置
author: dansimp
ms.assetid: ce689aff-9a55-4ae7-a968-23c7bda9b4d6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 10/24/2018
ms.openlocfilehash: 8ed7915e33c5e4735a7c58674ed5f7d6da8e9a06
ms.sourcegitcommit: 9087f0a1b5bd3f81a9b790d5e39fdf39c18a2411
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2020
ms.locfileid: "11182924"
---
# MBAM 2.5 支持的配置


可以在独立拓扑中或在与 System Center Configuration Manager 集成 MBAM 的 Configuration Manager 集成拓扑中运行 Microsoft BitLocker 管理和监视 (MBAM) 2.5。 如果对生产环境中的任一拓扑使用推荐的配置，MBAM 最多支持 500000 MBAM 客户端。 有关在每个服务器上为每个拓扑配置的推荐体系结构和功能的信息，请参阅 [MBAM 2.5 的高级体系结构](high-level-architecture-for-mbam-25.md)。

有关特定于 Configuration Manager 集成拓扑的其他配置，请参阅 [MBAM 支持的 Configuration Manager 版本](#bkmk-cm-ramreqs)。

**注意**  
Microsoft 提供对当前服务包的支持，在某些情况下，还提供了之前的服务包。 若要查找产品的支持时间表，请参阅 [支持生命周期的服务包](https://go.microsoft.com/fwlink/p/?LinkId=31975)。 有关 Microsoft 支持生命周期策略的其他信息，请参阅 [Microsoft 支持生命周期支持策略常见问题解答](https://go.microsoft.com/fwlink/p/?LinkId=31976)。



## MBAM 支持的语言


下表显示了 MBAM 客户端支持的语言 (包括 Self-Service 门户) 和 MBAM 2.5 和 MBAM 2.5 SP1 中的 MBAM 服务器。

**MBAM 2.5 SP1 中支持的语言：**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">客户端语言</th>
<th align="left">服务器语言</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>捷克 (捷克共和国) CZ</p>
<p>丹麦 (丹麦) da-深色</p>
<p>荷兰语 (荷兰) nl-NL</p>
<p>英语 (美国) en-us</p>
<p>芬兰语 (芬兰) fi</p>
<p>法语 (法国) fr-fr</p>
<p>德国 () de</p>
<p>希腊语 (希腊) el-GR</p>
<p>匈牙利语 (匈牙利) hu-HU</p>
<p>意大利 (意大利) it</p>
<p>日语 (日本) ja-jp</p>
<p>韩国 (韩国) ko-KR</p>
<p>挪威语、博克马尔语 (挪威) nb-否</p>
<p>波兰语 (波兰) pl</p>
<p>葡萄牙语 (巴西) pt-BR</p>
<p>葡萄牙语 (葡萄牙) pt</p>
<p>俄语 (俄罗斯) ru</p>
<p>斯洛伐克语 (斯洛伐克) sk-SK</p>
<p>西班牙 (西班牙) es</p>
<p>瑞典语 (瑞典) sv-SE</p>
<p>土耳其语 (土耳其) tr-TR</p>
<p>斯洛文尼亚语 (斯洛文尼亚) sl-SI</p>
<p>简体中文 (中国) zh-cn&platform-CN</p>
<p>繁体中文 (台湾) zh-cn&platform</p></td>
<td align="left"><ul>
<li><p>英语 (美国) en-us</p></li>
<li><p>法语 (法国) fr-fr</p></li>
<li><p>德国 () de</p></li>
<li><p>意大利 (意大利) it</p></li>
<li><p>日语 (日本) ja-jp</p></li>
<li><p>韩国 (韩国) ko-KR</p></li>
<li><p>葡萄牙语 (巴西) pt-BR</p></li>
<li><p>俄语 (俄罗斯) ru</p></li>
<li><p>西班牙 (西班牙) es</p></li>
<li><p>简体中文 (中国) zh-cn&platform-CN</p></li>
<li><p>繁体中文 (台湾) zh-cn&platform</p></li>
</ul></td>
</tr>
</tbody>
</table>



**MBAM 2.5 中支持的语言：**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">客户端语言</th>
<th align="left">服务器语言</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><ul>
<li><p>英语 (美国) en-us</p></li>
<li><p>法语 (法国) fr-fr</p></li>
<li><p>德国 () de</p></li>
<li><p>意大利 (意大利) it</p></li>
<li><p>日语 (日本) ja-jp</p></li>
<li><p>韩国 (韩国) ko-KR</p></li>
<li><p>葡萄牙语 (巴西) pt-BR</p></li>
<li><p>俄语 (俄罗斯) ru</p></li>
<li><p>西班牙 (西班牙) es</p></li>
<li><p>简体中文 (中国) zh-cn&platform-CN</p></li>
<li><p>繁体中文 (台湾) zh-cn&platform</p></li>
</ul></td>
<td align="left"><ul>
<li><p>英语 (美国) en-us</p></li>
<li><p>法语 (法国) fr-fr</p></li>
<li><p>德国 () de</p></li>
<li><p>意大利 (意大利) it</p></li>
<li><p>日语 (日本) ja-jp</p></li>
<li><p>韩国 (韩国) ko-KR</p></li>
<li><p>葡萄牙语 (巴西) pt-BR</p></li>
<li><p>俄语 (俄罗斯) ru</p></li>
<li><p>西班牙 (西班牙) es</p></li>
<li><p>简体中文 (中国) zh-cn&platform-CN</p></li>
<li><p>繁体中文 (台湾) zh-cn&platform</p></li>
</ul></td>
</tr>
</tbody>
</table>



## <a href="" id="---------mbam-server-system-requirements"></a> MBAM 服务器系统要求


### MBAM 服务器操作系统要求

我们强烈建议你在同一操作系统上运行 MBAM 客户端和 MBAM 服务器。 例如，windows 10 windows Server 2016、windows 8.1 和 Windows Server 2012 R2 等。

下表列出了 MBAM 服务器安装支持的操作系统。

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
<td align="left"><p>Windows Server 2019</p></td>
<td align="left"><p>标准版或数据中心</p></td>
<td align="left"></td>
<td align="left"><p>64 位</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2016</p></td>
<td align="left"><p>标准版或数据中心</p></td>
<td align="left"></td>
<td align="left"><p>64 位</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2012 R2</p></td>
<td align="left"><p>标准版或数据中心</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 位</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2012</p></td>
<td align="left"><p>标准版或数据中心</p></td>
<td align="left"></td>
<td align="left"><p>64 位</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2008 R2</p></td>
<td align="left"><p>标准版、企业版或数据中心</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 位</p></td>
</tr>
</tbody>
</table>



企业域必须包含至少一个 Windows Server 2008 (或更高版本) 域控制器。

### <a href="" id="bkmk-stand-alone-ramreqs"></a>MBAM 服务器处理器、RAM 和磁盘空间要求-独立拓扑

这些要求适用于 MBAM 独立拓扑。 有关 Configuration Manager 集成拓扑的要求，请参阅 [MBAM 服务器处理器、RAM 和磁盘空间要求-配置管理器集成拓扑](#bkmk-cm-ramreqs)。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">硬件项</th>
<th align="left">最低要求</th>
<th align="left">建议的要求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>处理器</p></td>
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



### <a href="" id="bkmk-cm-ramreqs"></a>MBAM 服务器处理器、RAM 和磁盘空间要求-配置管理器集成拓扑

下表列出了使用 Configuration Manager 集成拓扑时 MBAM 服务器的服务器处理器、RAM 和磁盘空间要求。 有关独立拓扑的要求，请参阅 [MBAM 服务器处理器、RAM 和磁盘空间要求-独立拓扑](#bkmk-stand-alone-ramreqs)。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">硬件项</th>
<th align="left">最低要求</th>
<th align="left">建议的要求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>处理器</p></td>
<td align="left"><p>2.33 GHz</p></td>
<td align="left"><p>2.33 GHz 或更高版本</p></td>
</tr>
<tr class="even">
<td align="left"><p>RAM</p></td>
<td align="left"><p>4 GB</p></td>
<td align="left"><p>8 GB</p></td>
</tr>
<tr class="odd">
<td align="left"><p>可用磁盘空间</p></td>
<td align="left"><p>1 GB</p></td>
<td align="left"><p>2 GB</p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-cmversions"></a>MBAM 支持的 Configuration Manager 版本

MBAM 支持以下版本的 Configuration Manager。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">支持的版本</th>
<th align="left">Service pack</th>
<th align="left">系统体系结构</th>
</tr>
</thead>
<tbody>
<tr class="even">
<td align="left"><p>Microsoft System Center Configuration Manager (当前分支) ，最高为1902的版本</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 位</p></td>
</tr>

<tr class="odd">
<td align="left"><p>Microsoft System Center Configuration Manager 1806</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 位</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft System Center Configuration Manager (LTSB-版本 1606) </p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 位</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft System Center 2012 Configuration Manager</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 位</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft System Center Configuration Manager 2007 R2 或更高版本</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 位</p>

&gt;<strong>注意 </strong> 虽然 Configuration Manager 2007 R2 为32位，但必须在64位操作系统上安装它和 SQL Server 才能匹配64位 MBAM 软件。
</td>
</tr>
</tbody>
</table>



有关 Configuration Manager 服务器支持的配置的列表，请参阅适用于你正在使用的 Configuration Manager 版本的相应 TechNet 文档。 MBAM 配置管理器服务器没有其他系统要求。

### <a href="" id="sql-server-database-requirements-"></a>SQL Server 数据库要求

下表列出了 MBAM 服务器功能支持的 Microsoft SQL Server 版本，其中包括恢复数据库、合规性和审核数据库以及报表功能。 所需版本适用于独立版或 Configuration Manager 集成拓扑。

必须以 **sql \ _Latin1 \ _General \ _CP1 _CI \ _AS** 排序规则安装 sql Server。

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
<td align="left"><p>Microsoft SQL Server 2019</p></td>
<td align="left"><p>标准版、企业版或数据中心</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 位</p></td><br/><tr class="even">
<td align="left"><p>Microsoft SQL Server 2017</p></td>
<td align="left"><p>标准版、企业版或数据中心</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 位</p></td><br/><tr class="even">
<td align="left"><p>Microsoft SQL Server 2016</p></td>
<td align="left"><p>标准版、企业版或数据中心</p></td>
<td align="left"><p>SP1</p></td>
<a href="https://www.microsoft.com/download/details.aspx?id=54967" data-raw-source="https://www.microsoft.com/download/details.aspx?id=54967">https://www.microsoft.com/download/details.aspx?id=54967</a><td align="left"><p>64 位</p></td>
<tr class="odd">
<td align="left"><p>Microsoft SQL Server 2014</p></td>
<td align="left"><p>标准版、企业版或数据中心</p></td>
<td align="left"><p>SP1、SP2</p></td>
<td align="left"><p>64 位</p></td>
<tr class="odd">
<td align="left"><p>Microsoft SQL Server 2012</p></td>
<td align="left"><p>标准版、企业版或数据中心</p></td>
<td align="left"><p>又</p></td>
<td align="left"><p>64 位</p></td>
<tr class="even">
<td align="left"><p>Microsoft SQL Server 2008 R2</p></td>
<td align="left"><p>Standard 或 Enterprise</p></td>
<td align="left"><p>又</p></td>
<td align="left"><p>64 位</p></td>
</tr>
</tbody>
</table>

**注意**  
MBAM 具有最高支持的兼容性级别140。 在 SQL Server 2019 上创建的新数据库的默认兼容级别是150，在创建数据库之后，需要使用 ALTER DATABASE 命令将其更改为140或更低。 从 SQL server 2017 或更低版本迁移的现有数据库将保持其以前的兼容级别，无需更改。

为了支持 SQL 2016，您必须安装 MDOP 的三月2017服务版本 https://www.microsoft.com/download/details.aspx?id=54967  ，并支持 SQL 2017 必须安装用于 mdop 的2018年7月的服务发布 https://www.microsoft.com/download/details.aspx?id=57157 。 通常，通过始终使用最近的服务更新保持最新，因为它还包括所有缺陷修复和新功能。


### <a href="" id="bkmk-sql-stand-alone-ramreqs"></a>SQL Server 处理器、RAM 和磁盘空间要求-独立拓扑

下表列出了使用独立拓扑时所推荐的 SQL Server 计算机的服务器处理器、RAM 和磁盘空间要求。 将这些要求用作指南。 特定要求将根据您的企业中支持的客户端计算机的数量而有所不同。 若要查看 Configuration Manager 集成拓扑的要求，请参阅 [SQL Server 处理器、RAM 和磁盘空间要求-配置管理器集成拓扑](#bkmk-cm-sql-ramreqs)。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">硬件项</th>
<th align="left">最低要求</th>
<th align="left">建议的要求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>处理器</p></td>
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



### <a href="" id="bkmk-cm-sql-ramreqs"></a>SQL Server 处理器、RAM 和磁盘空间要求-配置管理器集成拓扑

下表列出了使用 Configuration Manager 集成拓扑时 Microsoft SQL Server 计算机的服务器处理器、RAM 和磁盘空间要求，请参阅 [SQL Server 处理器、RAM 和磁盘空间要求-独立拓扑](#bkmk-sql-stand-alone-ramreqs)。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">硬件项</th>
<th align="left">最低要求</th>
<th align="left">建议的要求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>处理器</p></td>
<td align="left"><p>2.33 GHz</p></td>
<td align="left"><p>2.33 GHz 或更高版本</p></td>
</tr>
<tr class="even">
<td align="left"><p>RAM</p></td>
<td align="left"><p>4 GB</p></td>
<td align="left"><p>8 GB</p></td>
</tr>
<tr class="odd">
<td align="left"><p>可用磁盘空间</p></td>
<td align="left"><p>5 GB</p></td>
<td align="left"><p>5 GB</p></td>
</tr>
</tbody>
</table>



## <a href="" id="---------mbam-client-system-requirements"></a> MBAM 客户端系统要求


### 客户端操作系统要求

我们强烈建议你在同一操作系统上运行 MBAM 客户端和 MBAM 服务器。 例如，windows 10 windows Server 2016、windows 8.1 和 Windows Server 2012 R2 等。

下表列出了 MBAM 客户端安装支持的操作系统。 相同的要求适用于独立和 Configuration Manager 集成拓扑。

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
<tr class="even">
    <td align="left"><p>Windows 10 IoT</p></td>
    <td align="left"><p>企业</p></td>
    <td align="left"><p></p></td>
    <td align="left"><p>32 位或 64 位</p></td>
</tr><br/><tr class="odd">
<td align="left"><p>Windows 10</p></td>
<td align="left"><p>企业</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 位或 64 位</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 8.1</p></td>
<td align="left"><p>企业</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 位或 64 位</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows 7</p></td>
<td align="left"><p>企业版或旗舰版</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>32 位或 64 位</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows To Go</p></td>
<td align="left"><p>Windows 8.1 和 Windows 10 企业版</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 位或 64 位</p></td>
</tr>
</tbody>
</table>



### <a href="" id="client-ram-requirements-"></a>客户端 RAM 要求

没有特定于 MBAM 客户端安装的 RAM 要求。

## <a href="" id="---------mbam-group-policy-system-requirements"></a> MBAM 组策略系统要求


下表列出了 MBAM 组策略模板安装支持的操作系统。

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
 <tr class="even">
      <td align="left"><p>Windows 10 IoT</p></td>
      <td align="left"><p>企业</p></td>
      <td align="left"><p></p></td>
      <td align="left"><p>32 位或 64 位</p></td>
 </tr>
<tr class="odd">
<td align="left"><p>Windows 10</p></td>
<td align="left"><p>企业</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 位或 64 位</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 8.1</p></td>
<td align="left"><p>企业</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 位或 64 位</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows 7</p></td>
<td align="left"><p>企业版或旗舰版</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>32 位或 64 位</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2012 R2</p></td>
<td align="left"><p>标准版或数据中心</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 位</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2012</p></td>
<td align="left"><p>标准版或数据中心</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 位</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2008 R2</p></td>
<td align="left"><p>标准版、企业版或数据中心</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 位</p></td>
</tr>
</tbody>
</table>

## Azure IaaS 中的 MBAM

MBAM 服务器可以作为服务部署在以上列出的任何受支持的操作系统版本上的服务 (IaaS) ，连接到托管在本地的 Active Directory 或也托管在 Azure IaaS 中的 Active Directory。  [此处](https://msdn.microsoft.com/library/azure/jj156090.aspx)提供了在 Azure IaaS 上设置和配置 Active Directory 的文档。

MBAM 客户端在虚拟机上不受支持，并且在 Azure IaaS 上也不受支持。


## 服务版本 

- [2016年4月的修复程序](https://support.microsoft.com/help/3144445/april-2016-hotfix-rollup-for-microsoft-desktop-optimization-pack)
- [2016年9月](https://support.microsoft.com/ms-my/help/3168628/september-2016-servicing-release-for-microsoft-desktop-optimization-pa)
- [2016 年 12 月](https://support.microsoft.com/help/3198158/december-2016-servicing-release-for-microsoft-desktop-optimization-pac)
- [2017 年 3 月](https://support.microsoft.com/en-ie/help/4014009/march-2017-servicing-release-for-microsoft-desktop-optimization-pack) 
- [2017 年 6 月](https://support.microsoft.com/af-za/help/4018510/june-2017-servicing-release-for-microsoft-desktop-optimization-pack)
- [2017 年 9 月](https://support.microsoft.com/en-ie/help/4041137/september-2017-servicing-release-for-microsoft-desktop-optimization)
- [2018 年 3 月](https://support.microsoft.com/help/4074878/march-2018-servicing-release-for-microsoft-desktop-optimization-pack)
- [2018年7月](https://support.microsoft.com/help/4340040/july-2018-servicing-release-for-microsoft-desktop-optimization-pack)
- [五月2019](https://support.microsoft.com/help/4505175/may-2019-servicing-release-for-microsoft-desktop-optimization-pack)

## 相关主题


[规划部署 MBAM 2.5](planning-to-deploy-mbam-25.md)

[为 MBAM 2.5 准备你的环境](preparing-your-environment-for-mbam-25.md)




## 已获得 MBAM 的建议？
- 在 [此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用 [MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。




