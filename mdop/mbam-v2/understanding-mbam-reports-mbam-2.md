---
title: 了解 MBAM 报告
description: 了解 MBAM 报告
author: dansimp
ms.assetid: 8778f333-760e-4f26-acb4-4e73b6fbb536
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3c3ca5e4da4cbcea80c87520f0ecd05e1e7d6be0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803443"
---
# 了解 MBAM 报告


如果你在安装 Microsoft BitLocker 管理和监视（MBAM）时选择了独立拓扑，则可以在 MBAM 中运行不同的报告，以监视 BitLocker 使用情况和合规性。 MBAM 报告合规性以及它所管理的所有计算机和设备的其他信息。 本主题中的信息可用于帮助你了解适用于企业和个人计算机合规性以及密钥恢复活动的 Microsoft BitLocker 管理和监视报告。

**注意** 如果你在安装 Microsoft BitLocker 管理和监视（MBAM）时选择了 Configuration Manager 拓扑，则报告将从 Configuration Manager 生成，而不是从 MBAM。 有关从配置管理器运行的报表的详细信息，请参阅[了解配置管理器中的 MBAM 报表](understanding-mbam-reports-in-configuration-manager.md)。

 

## 了解报表


若要访问 Microsoft BitLocker 管理和监视的 "报表" 功能，请打开 web 浏览器并打开 "管理和监视" 网站。 在左侧菜单栏中选择 "**报表**"，然后从顶部菜单栏中选择要生成的报表类型。

### 企业合规性报告

使用此报告类型可收集组织中的所有 BitLocker 合规性的信息。 你可以使用不同的筛选器将搜索结果缩小到合规性状态和错误状态。 报表信息每6小时更新一次。

**企业合规性报告字段**

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
<td align="left"><p>由 MBAM 管理的用户指定的 DNS 名称。</p></td>
</tr>
<tr class="even">
<td align="left"><p>域名</p></td>
<td align="left"><p>客户端计算机所在的完全限定的域名，由 MBAM 管理。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>合规性状态</p></td>
<td align="left"><p>根据为计算机指定的策略，对计算机合规的状态。 状态是不相容的和合规的。 有关如何解释合规性状态的详细信息，请参阅企业合规性报告合规性状态表。</p></td>
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

 

**企业合规性报告合规性状态**

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">合规性状态</th>
<th align="left">免除</th>
<th align="left">描述</th>
<th align="left">用户操作</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>标准</p></td>
<td align="left"><p>不豁免</p></td>
<td align="left"><p>根据指定的策略，计算机不相容。</p></td>
<td align="left"><p>通过单击 "计算机名称" 展开 "计算机合规性报告详细信息" <strong> </strong> ，确定每个驱动器的状态是否符合指定的策略。 如果加密状态指示计算机未加密，则可能正在进行加密，或者计算机上出现错误。 如果没有错误，可能是因为计算机仍在连接或建立加密状态的过程中。 稍后再次查看以确定状态是否更改。</p></td>
</tr>
<tr class="even">
<td align="left"><p>性</p></td>
<td align="left"><p>不豁免</p></td>
<td align="left"><p>根据指定的策略，计算机合规。</p></td>
<td align="left"><p>无需执行任何操作;可通过查看计算机合规性报告来确认计算机的状态。</p></td>
</tr>
</tbody>
</table>

 

### 计算机合规性报告

使用此报告类型可收集特定于计算机或用户的信息。

通过在企业合规性报告中单击计算机名称，或在计算机合规性报告中键入计算机名称，可查看此报告。 计算机合规性报告提供有关计算机上每个驱动器（操作系统和固定数据驱动器）的详细加密信息，以及应用于计算机上每个驱动器类型的策略的指示。 若要查看每个驱动器的详细信息，请展开 "计算机名称" 条目。

**注意** 可移动数据卷加密状态将不会显示在报告中。

 

**计算机合规性报告字段**

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
<td align="left"><p>在 MBAM 管理的客户端计算机上找到的操作系统类型。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>合规性状态</p></td>
<td align="left"><p>由 MBAM 管理的计算机的整体合规性状态。 有效状态符合和不相容。 请注意，每个驱动器的合规性状态（请参阅下表）可能指示不同的合规性状态。 但是，此字段根据指定的策略表示符合性状态。</p></td>
</tr>
<tr class="even">
<td align="left"><p>策略密码强度</p></td>
<td align="left"><p>MBAM 策略规范期间管理员选择的密码长度（例如，使用扩散器的128位）。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>策略操作系统驱动器</p></td>
<td align="left"><p>指示操作系统是否需要加密，并显示相应的保护器类型。</p></td>
</tr>
<tr class="even">
<td align="left"><p>策略-固定数据驱动器</p></td>
<td align="left"><p>指示固定数据驱动器是否需要加密。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>策略可移动数据驱动器</p></td>
<td align="left"><p>指示可移动驱动器是否需要加密。</p></td>
</tr>
<tr class="even">
<td align="left"><p>设备用户</p></td>
<td align="left"><p>由 MBAM 管理的计算机上的已知用户。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>制造商</p></td>
<td align="left"><p>计算机制造商名称，它显示在计算机 BIOS 中。</p></td>
</tr>
<tr class="even">
<td align="left"><p>型号</p></td>
<td align="left"><p>计算机制造商模型名称，它显示在计算机 BIOS 中。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>合规性状态详细信息</p></td>
<td align="left"><p>根据指定的策略，对计算机合规性状态的错误和状态消息。</p></td>
</tr>
<tr class="even">
<td align="left"><p>上次联系人</p></td>
<td align="left"><p>计算机上次联系服务器以报告合规性状态的日期和时间。 可配置联系人频率（请参阅 MBAM 策略设置）。</p></td>
</tr>
</tbody>
</table>

 

**计算机合规性报告驱动器字段**

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
<td align="left"><p>通过用于加密操作系统或固定数据卷的策略选择的保护程序类型。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>保护程序状态</p></td>
<td align="left"><p>指示由 MBAM 托管的计算机已启用在策略中指定的保护程序类型。 有效状态为 "开" 或 "关"。</p></td>
</tr>
<tr class="even">
<td align="left"><p>加密状态</p></td>
<td align="left"><p>驱动器的加密状态。 有效状态为加密、未加密和加密。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>合规性状态</p></td>
<td align="left"><p>指示驱动器是否符合策略的状态。 状态是不相容的和合规的。</p></td>
</tr>
<tr class="even">
<td align="left"><p>合规性状态详细信息</p></td>
<td align="left"><p>根据指定的策略，对计算机合规性状态的错误和状态消息。</p></td>
</tr>
</tbody>
</table>

 

### 恢复审核报告

使用此报告类型审核请求了恢复密钥访问权限的用户。 该报表基于所需的筛选条件提供了多个筛选器。 用户可以筛选特定类型的用户，无论是帮助台用户还是最终用户、请求失败还是成功、所请求的特定类型的密钥以及发生检索的日期范围。 管理员可以根据需要生成上下文报告。

**恢复审核报告字段**

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
<td align="left"><p>请求日期和时间</p></td>
<td align="left"><p>最终用户或技术支持用户进行密钥检索请求的日期和时间。</p></td>
</tr>
<tr class="even">
<td align="left"><p>请求状态</p></td>
<td align="left"><p>请求的状态。 有效状态为 "成功" （已检索密钥）或 "失败" （未检索到密钥）。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>帮助台用户</p></td>
<td align="left"><p>启动了密钥检索请求的技术支持用户。 注意：如果技术支持用户代表最终用户检索密钥，则 "最终用户" 字段将为空。</p></td>
</tr>
<tr class="even">
<td align="left"><p>用户</p></td>
<td align="left"><p>启动密钥检索请求的最终用户。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>键类型</p></td>
<td align="left"><p>技术支持用户或最终用户请求的键类型。 MBAM 收集的三种密钥类型为：恢复密钥密码（用于在恢复模式下恢复计算机）、恢复密钥 ID （用于在恢复模式中代表另一个用户恢复计算机）和 TPM 密码哈希（用于使用已锁定的 TPM 恢复计算机）。</p></td>
</tr>
<tr class="even">
<td align="left"><p>原因描述</p></td>
<td align="left"><p>由技术支持用户或最终用户请求指定的键类型的原因。 原因在 "驱动器恢复" 和 "管理管理和监视网站的 TPM" 功能中指定。 有效的条目是用户输入的文本，或者是以下原因代码之一：</p>
<ul>
<li><p>操作系统启动顺序已更改</p></li>
<li><p>BIOS 已更改</p></li>
<li><p>操作系统文件已更改</p></li>
<li><p>已丢失启动密钥</p></li>
<li><p>丢失的 PIN</p></li>
<li><p>TPM 重置</p></li>
<li><p>丢失密码</p></li>
<li><p>失去智能卡</p></li>
<li><p>重置 PIN 锁定</p></li>
<li><p>打开 TPM</p></li>
<li><p>关闭 TPM</p></li>
<li><p>更改 TPM 密码</p></li>
<li><p>清除 TPM</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

**注意** 通过单击 "报表" 菜单栏上的 "**导出**" 按钮，可将报表结果保存到文件中。 有关如何运行 MBAM 报表的详细信息，请参阅[如何生成 MBAM 报表](how-to-generate-mbam-reports-mbam-2.md)。

 

## 相关主题


[使用 MBAM 2.0 监视和报告 BitLocker 符合性](monitoring-and-reporting-bitlocker-compliance-with-mbam-20-mbam-2.md)

 

 





