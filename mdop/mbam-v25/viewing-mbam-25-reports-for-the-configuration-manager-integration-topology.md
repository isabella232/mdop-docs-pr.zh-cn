---
title: 查看 Configuration Manager 集成拓扑的 MBAM 2.5 报告
description: 查看 Configuration Manager 集成拓扑的 MBAM 2.5 报告
author: dansimp
ms.assetid: 60d11b2f-3a76-4023-8da4-f89e9f35b790
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3384fee62d302ac47775fe106265456ef119ab47
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803489"
---
# 查看 Configuration Manager 集成拓扑的 MBAM 2.5 报告


本主题介绍使用 Configuration Manager 集成拓扑配置 Microsoft BitLocker 管理和监视（MBAM）时可用的报告。 这些报表显示企业和 MBAM 管理的单个计算机和设备的 BitLocker 合规性。 报表提供表格信息和图表，并且它们具有可用于从不同视角查看数据的筛选器。

在 Configuration Manager 集成拓扑中，你可以从 Configuration Manager 查看报告，而不是从管理和监视网站查看报告，除了**恢复审核报告**外，你还可以从 "管理和监控" 网站继续查看。

有关独立拓扑的 MBAM 报表的信息，请参阅[查看独立拓扑的 MBAM 2.5 报表](viewing-mbam-25-reports-for-the-stand-alone-topology.md)。

## 在配置管理器中访问报表


要访问配置管理器中的 "报表" 功能，请执行以下操作：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">版本的 Configuration Manager</th>
<th align="left">如何查看报表</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>SystemCenter2012 ConfigurationManager</p></td>
<td align="left"><ol>
<li><p>在左窗格中，选择 " <strong> 监视" </strong> 工作区。</p></li>
<li><p>在树中，展开 " <strong> 概述 </strong> &gt; <strong> 报告 </strong> &gt; <strong> 报告 </strong> &gt; <strong> MBAM" </strong> 。</p></li>
<li><p>选择表示要查看报表的语言的文件夹，然后从右窗格中选择报表。</p></li>
</ol></td>
</tr>
<tr class="even">
<td align="left"><p>配置管理器 2007</p></td>
<td align="left"><ol>
<li><p>在左窗格中，展开 " <strong> 计算机管理报告 </strong> &gt; <strong> </strong> &gt; <strong> 服务 </strong> &gt; <strong> &lt; 服务器名称 &gt; </strong> &gt; <strong> 报告文件夹 </strong> &gt; <strong> MBAM" </strong> 。</p></li>
<li><p>选择表示要查看报表的语言的文件夹，然后从右窗格中选择报表。</p></li>
</ol></td>
</tr>
</tbody>
</table>

 

## 配置管理器中的报表说明


Configuration Manager 集成拓扑和独立拓扑的报表有一些细微差别。 以下部分介绍了 Configuration Manager 集成拓扑的 MBAM 报告中的数据：

-   [BitLocker 企业合规性仪表板](#bkmk-dashboard)

-   [BitLocker 企业合规性详细信息](#bkmk-compliancedetails)

-   [BitLocker 企业合规性摘要](#bkmk-compliancesummary)

-   [BitLocker 计算机合规性报告](#bkmk-compliancereport)

### <a href="" id="bkmk-dashboard"></a>BitLocker 企业合规性仪表板

BitLocker 企业合规性仪表板提供以下图形，其中显示了整个企业的 BitLocker 合规性状态：

-   合规性状态分发

-   不符合的错误分布

-   按驱动器类型的合规性状态分发

**合规性状态分发**

此饼图显示企业内计算机的合规性状态。 它还显示计算机的百分比，与所选集合中的计算机总数相比较，这些计算机具有符合性状态。 还将显示每个状态的实际计算机数。 饼图显示以下合规性状态：

-   性

-   不符合

-   用户豁免

-   临时用户豁免

-   未强制执行策略

-   可知. 这些计算机报告了状态错误，或者它们是集合的一部分，但从未报告过合规性状态。 如果计算机与组织断开连接，则可能会出现合规性状态。

**不符合的错误分布**

此饼图显示企业中与 BitLocker 驱动器加密策略不兼容的计算机类别，并显示每个类别中的计算机数。 每个类别百分比均由集合中不兼容计算机的总数计算。

-   用户延期的加密

-   找不到兼容的 TPM

-   系统分区不可用或足够大

-   策略冲突

-   正在等待 TPM 自动预配

-   出现未知错误

-   无信息。 这些计算机未安装 MBAM 客户端，或者安装了 MBAM 客户端但未激活（例如，服务不工作）。

**按驱动器类型的合规性状态分发**

此条形图按驱动器类型显示当前的 BitLocker 合规性状态。 状态**符合标准**且**不合规**。 显示固定数据驱动器和操作系统驱动器的栏。 不包含固定数据驱动器的计算机将包含在**操作系统驱动器**栏中且仅显示一个值。 图表不包括已被授予 BitLocker 驱动器加密策略或 "无策略" 类别的豁免的用户。

### <a href="" id="bkmk-compliancedetails"></a>BitLocker 企业合规性详细信息

此报表显示有关面向 BitLocker 使用的计算机集合的整个企业范围内的 BitLocker 合规性的信息。

**BitLocker 企业合规性详细信息字段**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">列名称</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>托管计算机</p></td>
<td align="left"><p>MBAM 管理的计算机数。</p></td>
</tr>
<tr class="even">
<td align="left"><p>符合百分比</p></td>
<td align="left"><p>企业中合规性计算机的百分比。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>不符合的%</p></td>
<td align="left"><p>企业中不符合的计算机的百分比。</p></td>
</tr>
<tr class="even">
<td align="left"><p>% 的未知合规性</p></td>
<td align="left"><p>符合性状态为未知的计算机的百分比。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>% 豁免</p></td>
<td align="left"><p>免除 BitLocker 加密要求的计算机的百分比。</p></td>
</tr>
<tr class="even">
<td align="left"><p>% 非豁免</p></td>
<td align="left"><p>不受 BitLocker 加密要求免除的计算机的百分比。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>性</p></td>
<td align="left"><p>企业中合规性计算机的百分比。</p></td>
</tr>
<tr class="even">
<td align="left"><p>不符合</p></td>
<td align="left"><p>企业中不符合的计算机的百分比。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>未知合规性</p></td>
<td align="left"><p>符合性状态为未知的计算机的百分比。</p></td>
</tr>
<tr class="even">
<td align="left"><p>例外</p></td>
<td align="left"><p>免除 BitLocker 加密要求的计算机的总数。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>非豁免</p></td>
<td align="left"><p>不免除 BitLocker 加密要求的计算机的总数。</p></td>
</tr>
</tbody>
</table>

 

**BitLocker 企业合规性详细信息状态**

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">合规性状态</th>
<th align="left">免除</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>标准</p></td>
<td align="left"><p>不豁免</p></td>
<td align="left"><p>根据指定的策略，计算机不相容。</p></td>
</tr>
<tr class="even">
<td align="left"><p>性</p></td>
<td align="left"><p>不豁免</p></td>
<td align="left"><p>计算机符合指定的策略。</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="bkmk-compliancesummary"></a>BitLocker 企业合规性摘要

使用此报告类型可显示整个企业中的所有 BitLocker 合规性的相关信息，并显示针对 BitLocker 使用的计算机集合中的各个计算机的合规性。

**BitLocker 企业合规性摘要字段**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">列名称</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>托管计算机</p></td>
<td align="left"><p>MBAM 管理的计算机数。</p></td>
</tr>
<tr class="even">
<td align="left"><p>符合百分比</p></td>
<td align="left"><p>企业中合规性计算机的百分比。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>不符合的%</p></td>
<td align="left"><p>企业中不符合的计算机的百分比。</p></td>
</tr>
<tr class="even">
<td align="left"><p>% 的未知合规性</p></td>
<td align="left"><p>符合性状态为未知的计算机的百分比。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>% 豁免</p></td>
<td align="left"><p>免除 BitLocker 加密要求的计算机的百分比。</p></td>
</tr>
<tr class="even">
<td align="left"><p>% 非豁免</p></td>
<td align="left"><p>不受 BitLocker 加密要求免除的计算机的百分比。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>性</p></td>
<td align="left"><p>企业中合规性计算机的百分比。</p></td>
</tr>
<tr class="even">
<td align="left"><p>不符合</p></td>
<td align="left"><p>企业中不符合的计算机的百分比。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>未知合规性</p></td>
<td align="left"><p>符合性状态为未知的计算机的百分比。</p></td>
</tr>
<tr class="even">
<td align="left"><p>例外</p></td>
<td align="left"><p>免除 BitLocker 加密要求的计算机的总数。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>非豁免</p></td>
<td align="left"><p>不免除 BitLocker 加密要求的计算机的总数。</p></td>
</tr>
</tbody>
</table>

 

**BitLocker 企业合规性摘要计算机详细信息**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">列名称</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>计算机名</p></td>
<td align="left"><p>由 MBAM 管理的用户指定的 DNS 计算机名。</p></td>
</tr>
<tr class="even">
<td align="left"><p>域名</p></td>
<td align="left"><p>客户端计算机所在的完全限定的域名，由 MBAM 管理。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>合规性状态</p></td>
<td align="left"><p>由 MBAM 管理的计算机的整体合规性状态。 有效状态符合和不相容。 请注意，每个驱动器的合规性状态（请参阅后面的表）可能指示不同的合规性状态。 但是，此字段根据指定的策略表示符合性状态。</p></td>
</tr>
<tr class="even">
<td align="left"><p>免除</p></td>
<td align="left"><p>用于指示用户是否为 BitLocker 策略豁免或非豁免的状态。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>设备用户</p></td>
<td align="left"><p>设备的用户。</p></td>
</tr>
<tr class="even">
<td align="left"><p>合规性状态详细信息</p></td>
<td align="left"><p>根据指定的策略，有关计算机合规性状态的错误和状态消息。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>上次联系人</p></td>
<td align="left"><p>计算机上次联系服务器以报告合规性状态的日期和时间。 可通过组策略设置配置联系人频率。</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="bkmk-compliancereport"></a>BitLocker 计算机合规性报告

使用此报告类型可收集特定于计算机的信息。 BitLocker 计算机合规性报告提供有关计算机上的每个驱动器（操作系统和固定数据驱动器）的详细加密信息。 它还提供了应用于计算机上每个驱动器类型的策略的指示。 若要查看每个驱动器的详细信息，请展开 "计算机名称" 条目。

**注意** 可移动数据卷加密状态不会显示在此报告中。

 

**BitLocker 计算机合规性报告：计算机详细信息字段**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">列名称</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>计算机名</p></td>
<td align="left"><p>由 MBAM 管理的用户指定的 DNS 计算机名。</p></td>
</tr>
<tr class="even">
<td align="left"><p>域名</p></td>
<td align="left"><p>客户端计算机所在的完全限定的域名，由 MBAM 管理。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>计算机类型</p></td>
<td align="left"><p>计算机的类型。 有效类型为非便携式和可移植。</p></td>
</tr>
<tr class="even">
<td align="left"><p>操作系统</p></td>
<td align="left"><p>在 MBAM 托管客户端计算机上找到的操作系统类型。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>整体合规性</p></td>
<td align="left"><p>由 MBAM 管理的计算机的整体合规性状态。 有效状态符合和不相容。 请注意，每个驱动器的合规性状态（请参阅后面的表）可能指示不同的合规性状态。 但是，此字段根据指定的策略表示符合性状态。</p></td>
</tr>
<tr class="even">
<td align="left"><p>操作系统合规性</p></td>
<td align="left"><p>由 MBAM 托管的操作系统的合规性状态。 有效状态符合和不相容。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>固定数据驱动器合规性</p></td>
<td align="left"><p>由 MBAM 管理的固定数据驱动器的合规性状态。 有效状态符合和不相容。</p></td>
</tr>
<tr class="even">
<td align="left"><p>上次更新日期</p></td>
<td align="left"><p>计算机上次联系服务器以报告合规性状态的日期和时间。 可通过组策略设置配置联系人频率。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>免除</p></td>
<td align="left"><p>用于指示用户是否为 BitLocker 策略豁免或非豁免的状态。</p></td>
</tr>
<tr class="even">
<td align="left"><p>已免除用户</p></td>
<td align="left"><p>不受 BitLocker 策略阻止的用户。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>豁免日期</p></td>
<td align="left"><p>已获豁免的日期。</p></td>
</tr>
<tr class="even">
<td align="left"><p>合规性状态详细信息</p></td>
<td align="left"><p>根据指定的策略，有关计算机合规性状态的错误和状态消息。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>策略密码强度</p></td>
<td align="left"><p>MBAM 策略规范期间管理员选择的密码长度（例如，使用扩散器的128位）。</p></td>
</tr>
<tr class="even">
<td align="left"><p>策略：操作系统驱动器</p></td>
<td align="left"><p>指示操作系统是否需要加密以及相应的保护器类型。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>策略：固定数据驱动器</p></td>
<td align="left"><p>指示固定数据驱动器是否需要加密。</p></td>
</tr>
<tr class="even">
<td align="left"><p>制造商</p></td>
<td align="left"><p>计算机 BIOS 中显示的计算机制造商名称。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>型号</p></td>
<td align="left"><p>计算机 BIOS 中显示的计算机制造商型号名称。</p></td>
</tr>
<tr class="even">
<td align="left"><p>设备用户</p></td>
<td align="left"><p>由 MBAM 管理的计算机上的已知用户。</p></td>
</tr>
</tbody>
</table>

 

**BitLocker 计算机合规性报告：计算机卷字段**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">列名称</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>驱动器号</p></td>
<td align="left"><p>用户分配给特定驱动器的计算机驱动器号。</p></td>
</tr>
<tr class="even">
<td align="left"><p>驱动器类型</p></td>
<td align="left"><p>驱动器的类型。 有效值为操作系统驱动器和固定数据驱动器。 这些驱动器是物理驱动器，而不是逻辑卷。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>密码强度</p></td>
<td align="left"><p>MBAM 策略规范期间管理员选择的密码长度。</p></td>
</tr>
<tr class="even">
<td align="left"><p>保护器类型</p></td>
<td align="left"><p>通过用于加密操作系统或固定数据驱动器的策略选择的保护器类型。 操作系统的有效保护程序类型为 TPM 或 TPM + PIN。 固定数据驱动器的有效保护器类型是密码。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>保护程序状态</p></td>
<td align="left"><p>指示由 MBAM 托管的计算机已启用在策略中指定的保护者类型。 有效状态为 "开" 或 "关"。</p></td>
</tr>
<tr class="even">
<td align="left"><p>加密状态</p></td>
<td align="left"><p>驱动器的加密状态。 有效状态为加密、未加密和加密。</p></td>
</tr>
</tbody>
</table>

 

## 相关主题


[监视和报告 BitLocker 与 MBAM 2.5 的相容性](monitoring-and-reporting-bitlocker-compliance-with-mbam-25.md)

 

## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





