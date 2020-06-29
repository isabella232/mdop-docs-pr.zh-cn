---
title: 了解 Configuration Manager 中的 MBAM 报告
description: 了解 Configuration Manager 中的 MBAM 报告
author: dansimp
ms.assetid: b2582190-c9de-4e64-bd5a-f31ac1916f53
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 995d628cafd03c8bdd209e467c9d22169b7e03c3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803445"
---
# 了解 Configuration Manager 中的 MBAM 报告


当 Microsoft BitLocker 管理和监视（MBAM）与 Configuration Manager 集成拓扑一起安装时，硬件合规性和报告功能将被移动到 Configuration Manager 基础结构中，而不是 MBAM。 使用 Configuration Manager 拓扑时，从 Configuration Manager （而不是从 MBAM）运行报表，但不是从 "恢复审核报告" （使用 "管理和监视" 网站继续访问）除外。

Configuration Manager 集成拓扑的报告显示企业和 MBAM 管理的单个计算机和设备的 BitLocker 合规性。 这些报表提供表格信息和图表，使你可以筛选报表以查看来自不同视角的数据。

本主题中的信息介绍了您从配置管理器中运行的 MBAM 报表。 有关独立拓扑的 MBAM 报表的信息，请参阅[了解 MBAM 报表](understanding-mbam-reports-mbam-2.md)。

## 在配置管理器中访问报表


若要访问配置管理器中的报表功能，请打开**Configuration manager 控制台**。 要显示可用报表的列表，请执行以下操作：

-   在 Configuration Manager 2007 中，展开 "**计算机管理**" 节点，然后展开 "**报告**" 节点。

-   在 SystemCenter2012 ConfigurationManager 中，在 "监视" 工作区的 "**概述**" 下，展开 "**报表**" 节点，然后单击 "**报表**"。

### BitLocker 企业合规性仪表板

BitLocker 企业合规性仪表板提供以下图形，其中显示了整个企业的 BitLocker 合规性状态：

-   合规性状态分发

-   不符合的错误分布

-   按驱动器类型的合规性状态分发

**合规性状态分发**

此饼图显示企业内的计算机合规性状态，并显示计算机的百分比，与所选集合中的计算机总数相比较，其符合性状态。 还将显示每个状态的实际计算机数。 饼图显示以下合规性状态：

-   性

-   不符合

-   用户豁免

-   临时用户豁免

-   未强制执行策略

-   未知-状态被报告为错误的计算机，或属于集合一部分但从未报告其合规性状态的设备（例如，在与组织断开连接时）

**不符合的错误分布**

此饼图显示企业中与 BitLocker 驱动器加密策略不兼容的计算机类别，并显示每个类别中的计算机数。 每个类别百分比均由集合中不兼容计算机的总数计算。

-   用户延期的加密

-   找不到兼容的 TPM

-   系统分区不可用或足够大

-   策略冲突

-   正在等待 TPM 自动预配

-   出现未知错误

-   无信息-未安装 MBAM 客户端的计算机，或者安装了 MBAM 客户端但未激活的计算机（例如，服务无法正常工作）

**按驱动器类型的合规性状态分发**

此条形图按驱动器类型显示当前的 BitLocker 合规性状态。 状态为 "合规" 和 "不合规"。 显示固定数据驱动器和操作系统驱动器的栏。 不包含固定数据驱动器的计算机将包含在操作系统驱动器栏中且仅显示一个值。 图表不包括已通过 BitLocker 驱动器加密策略或 "无策略" 类别授予豁免的用户。

### BitLocker 企业合规性详细信息报告

此报表显示有关面向 BitLocker 使用的计算机集合的整个企业范围内的 BitLocker 合规性的信息。

**BitLocker 企业合规性详细信息报表字段**

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
<td align="left"><p>合规性状态未知的计算机的百分比。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>% 豁免</p></td>
<td align="left"><p>免除 BitLocker 加密要求的计算机的百分比。</p></td>
</tr>
<tr class="even">
<td align="left"><p>% 非豁免</p></td>
<td align="left"><p>免除 BitLocker 加密要求的计算机的百分比。</p></td>
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
<td align="left"><p>合规性状态未知的计算机的百分比。</p></td>
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

 

**BitLocker 企业合规性详细信息报告合规性状态**

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

 

### BitLocker 企业合规性摘要报告

使用此报告类型可显示整个企业中的所有 BitLocker 合规性的相关信息，并显示针对 BitLocker 使用的计算机集合中的各个计算机的合规性。

**BitLocker 企业合规性摘要报告字段**

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
<td align="left"><p>合规性状态未知的计算机的百分比。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>% 豁免</p></td>
<td align="left"><p>免除 BitLocker 加密要求的计算机的百分比。</p></td>
</tr>
<tr class="even">
<td align="left"><p>% 非豁免</p></td>
<td align="left"><p>免除 BitLocker 加密要求的计算机的百分比。</p></td>
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
<td align="left"><p>合规性状态未知的计算机的百分比。</p></td>
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

 

**BitLocker 企业合规性摘要报告-计算机详细信息**

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
<td align="left"><p>根据指定策略，计算机符合性状态的错误和状态消息。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>上次联系人</p></td>
<td align="left"><p>计算机上次联系服务器以报告合规性状态的日期和时间。 可配置联系人频率（请参阅 MBAM 策略设置）。</p></td>
</tr>
</tbody>
</table>

 

### BitLocker 计算机合规性报告

使用此报告类型可收集特定于计算机的信息。 计算机合规性报告提供有关计算机上每个驱动器（操作系统和固定数据驱动器）的详细加密信息，以及应用于计算机上每个驱动器类型的策略的指示。 若要查看每个驱动器的详细信息，请展开 "计算机名称" 条目。

**注意** 可移动数据卷加密状态不会显示在报表中。

 

**BitLocker 计算机合规性报告-计算机详细信息字段**

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
<td align="left"><p>计算机上次联系服务器以报告合规性状态的日期和时间。 可配置联系人频率（请参阅 MBAM 策略设置）。</p></td>
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
<td align="left"><p>根据指定策略，计算机符合性状态的错误和状态消息。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>策略密码强度</p></td>
<td align="left"><p>MBAM 策略规范期间管理员选择的密码长度。 （例如，有扩散器的128位）。</p></td>
</tr>
<tr class="even">
<td align="left"><p>策略：操作系统驱动器</p></td>
<td align="left"><p>指示 O/S 和相应的保护器类型是否需要加密。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>策略：固定数据驱动器</p></td>
<td align="left"><p>指示是否需要对固定驱动器进行加密。</p></td>
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

 

**BitLocker 计算机合规性报告-计算机卷字段**

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
<td align="left"><p>通过用于加密操作系统或固定卷的策略选择的保护器类型。 操作系统上的有效保护器类型为 TPM 或 TPM + PIN，并且固定数据卷的密码为密码。</p></td>
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


[结合使用 MBAM 和 Configuration Manager](using-mbam-with-configuration-manager.md)

 

 





