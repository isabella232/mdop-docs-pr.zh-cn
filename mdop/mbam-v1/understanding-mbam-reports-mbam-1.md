---
title: 了解 MBAM 报告
description: 了解 MBAM 报告
author: dansimp
ms.assetid: 34e4aaeb-7f89-41a1-b816-c6fe8397b060
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fa64a4724c87a42774e569b556013bfec2ed5514
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803254"
---
# 了解 MBAM 报告


Microsoft BitLocker 管理和监视（MBAM）生成各种报告以监控 BitLocker 使用情况和合规性。 本主题介绍针对企业合规性、单独计算机、硬件兼容性和密钥恢复活动的 MBAM 报告。

## 了解报表


若要访问 MBAM 的报表功能，请打开 MBAM 管理网站。 在导航窗格中选择 "**报表**"。 然后，在 "主内容" 窗格中，单击报表类型的选项卡： "**企业合规性报告**"、"**计算机合规性报告**"、"**硬件审核报告**" 或 "**恢复审核报告**"。

### 企业合规性报告

企业合规性报告提供有关您的组织中的所有 BitLocker 合规性的信息。 此报告的可用筛选器允许你根据合规性状态和错误状态缩小搜索结果的范围。 此报告每6小时运行一次。

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
<td align="left"><p>根据为计算机指定的策略，对计算机合规性的状态。 可能的状态是不相容的和合规的。 有关详细信息，请参阅本主题中的企业合规性报告合规性状态。</p></td>
</tr>
<tr class="even">
<td align="left"><p>免除</p></td>
<td align="left"><p>确定硬件类型的标识以及计算机是否受策略豁免的计算机硬件状态。 有三种可能的状态：硬件未知（MBAM 未识别硬件类型）、硬件免除（硬件类型已识别并被标记为不受 MBAM 策略的免除），并且不例外（硬件已确定，不会免于策略的例外）。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>设备用户</p></td>
<td align="left"><p>由 MBAM 管理的计算机上的已知用户。</p></td>
</tr>
<tr class="even">
<td align="left"><p>合规性状态详细信息</p></td>
<td align="left"><p>根据指定策略，有关计算机合规性状态的错误和状态消息。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>上次联系人</p></td>
<td align="left"><p>计算机上次联系服务器以报告合规性状态的日期和时间。 此时间可配置。 请参阅 MBAM 策略设置。</p></td>
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
<td align="left"><p>根据指定的策略，计算机不符合规则，并且硬件类型未被指定为策略例外。</p></td>
<td align="left"><p>单击 " <strong> 计算机名 </strong> " 以展开计算机合规性报告，并确定每个驱动器的状态是否符合指定的策略。 如果加密状态指示计算机未加密，可能仍在处理加密，或者计算机上可能存在错误。 如果没有错误，可能是因为计算机仍在连接或建立加密状态的过程中。 稍后再次查看以确定状态是否更改。</p></td>
</tr>
<tr class="even">
<td align="left"><p>性</p></td>
<td align="left"><p>不豁免</p></td>
<td align="left"><p>计算机符合指定的策略。</p></td>
<td align="left"><p>无需执行任何操作。 或者，您可以查看计算机合规性报告以确认计算机的状态。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>性</p></td>
<td align="left"><p>硬件豁免</p></td>
<td align="left"><p>如果硬件类型不受豁免。 无论策略的设置方式或每个硬驱的单个状态如何，整体状态均视为合规。</p></td>
<td align="left"><p>无需执行任何操作。</p></td>
</tr>
<tr class="even">
<td align="left"><p>性</p></td>
<td align="left"><p>硬件未知</p></td>
<td align="left"><p>MBAM 识别硬件类型，但 MBAM 不知道它是否豁免。 如果管理员未设置硬件的兼容状态，则会出现此情况。 因此，默认情况下，MBAM 将恢复为合规状态。</p></td>
<td align="left"><p>这是新部署的 MBAM 客户端的初始状态。 它通常仅是瞬时状态。 即使管理员已将硬件标记为兼容，在客户端计算机重新报告之前，可能会有很长的延迟或可配置的等待时间。 记下上次联系人的时间，并在指定间隔后再次签入，以查看状态是否已更改。 如果状态未更改，则此计算机或硬件类型可能存在错误。</p></td>
</tr>
</tbody>
</table>

 

### 计算机合规性报告

"计算机合规性" 报表显示特定于计算机或用户的信息。

计算机合规性报告为计算机上的每个驱动器提供详细的加密信息和适用的策略，包括操作系统驱动器和固定数据驱动器。 若要查看此报告类型，请在企业合规性报告中单击计算机名称，或在 "计算机合规性报告" 中键入计算机名称。 若要查看每个驱动器的详细信息，请展开 "计算机名称" 条目。

**注意** 此报告不提供可移动数据卷的加密状态。

 

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
<td align="left"><p>计算机的可移植性类型。 有效类型为非便携式和可移植。</p></td>
</tr>
<tr class="even">
<td align="left"><p>操作系统</p></td>
<td align="left"><p>MBAM 托管客户端计算机上安装的操作系统类型。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>合规性状态</p></td>
<td align="left"><p>由 MBAM 管理的计算机的整体合规性状态。 有效状态符合和不相容。 尽管可以在同一台计算机中具有兼容和不兼容的驱动器，但此字段指示每个指定策略的计算机总体合规性。</p></td>
</tr>
<tr class="even">
<td align="left"><p>策略 Cypher 强度</p></td>
<td align="left"><p>MBAM 策略规范期间管理员选择的密码强度。 例如，带扩散器的128位</p></td>
</tr>
<tr class="odd">
<td align="left"><p>策略操作系统驱动器</p></td>
<td align="left"><p>指示是否需要对 O/S 和保护器类型进行加密（如果适用）。</p></td>
</tr>
<tr class="even">
<td align="left"><p>策略固定数据驱动器</p></td>
<td align="left"><p>指示是否需要对固定驱动器进行加密。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>策略可移动数据驱动器</p></td>
<td align="left"><p>指示可移动驱动器是否需要加密。</p></td>
</tr>
<tr class="even">
<td align="left"><p>设备用户</p></td>
<td align="left"><p>提供计算机上已知用户的标识。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>免除</p></td>
<td align="left"><p>指示计算机硬件类型是否由 MBAM 识别，如果知道计算机是否已被指示为策略例外。 有三种状态：硬件未知（硬件类型尚未由 MBAM 标识）;硬件例外（识别硬件类型，并标记为不受 MBAM 策略的豁免）;不例外（硬件已确定，不会被策略豁免）。</p></td>
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
<td align="left"><p>合规性状态详细信息</p></td>
<td align="left"><p>根据指定策略，计算机合规性状态的错误和状态消息。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>上次联系人</p></td>
<td align="left"><p>计算机上次联系服务器以报告合规性状态的日期和时间。 T</p></td>
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
<td align="left"><p>用户分配给此特定驱动器的计算机驱动器号。</p></td>
</tr>
<tr class="even">
<td align="left"><p>驱动器类型</p></td>
<td align="left"><p>驱动器的类型。 有效值为操作系统驱动器和固定数据驱动器。 这些驱动器是物理驱动器，而不是逻辑卷。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Cypher 强度</p></td>
<td align="left"><p>MBAM 策略规范期间管理员选择的密码长度。</p></td>
</tr>
<tr class="even">
<td align="left"><p>保护器类型</p></td>
<td align="left"><p>通过用于加密操作系统或固定卷的策略选择的保护器类型。 操作系统驱动器上的有效保护器类型为 TPM 或 TPM + PIN。 固定数据卷的唯一有效保护程序类型是密码。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>保护程序状态</p></td>
<td align="left"><p>此字段指示计算机是否已启用在策略中指定的保护器类型。 有效状态为 "开" 或 "关"。</p></td>
</tr>
<tr class="even">
<td align="left"><p>加密状态</p></td>
<td align="left"><p>这是驱动器的当前加密状态。 有效状态为加密、未加密和加密。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>合规性状态</p></td>
<td align="left"><p>指示驱动器是否符合策略。 状态是不相容的和合规的。</p></td>
</tr>
<tr class="even">
<td align="left"><p>合规性状态详细信息</p></td>
<td align="left"><p>包含有关计算机合规性状态的错误和状态消息。</p></td>
</tr>
</tbody>
</table>

 

### 硬件审核报告

此报告可帮助你审核对特定计算机和模型的硬件兼容性状态所做的更改。 为了帮助您缩小搜索结果的范围，此报告包括筛选条件等条件，例如更改类型和发生时间。 每个状态更改均按用户和日期和时间进行跟踪。 硬件类型由在客户端计算机上运行的 MBAM 代理自动填充。 此报告跟踪用户对从 MBAM 托管计算机直接收集的信息所做的更改。 典型的管理更改是从兼容性更改到不兼容。 但是，管理员还可以修改任何字段。

**硬件审核报告字段**

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
<td align="left"><p>日期和时间</p></td>
<td align="left"><p>对硬件类型进行更改的日期和时间。 请注意，每个唯一硬件类型都分配给至少一个条目。</p></td>
</tr>
<tr class="even">
<td align="left"><p>用户</p></td>
<td align="left"><p>对特定条目进行更改的管理用户。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>更改类型</p></td>
<td align="left"><p>对硬件类型信息所做的更改的类型。 有效值为加法（新条目）、更新（更改现有条目）或删除（删除现有条目）。</p></td>
</tr>
<tr class="even">
<td align="left"><p>原始值</p></td>
<td align="left"><p>在进行更改之前硬件类型规范的值。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>当前值</p></td>
<td align="left"><p>在进行更改后硬件类型规范的值。</p></td>
</tr>
</tbody>
</table>

 

### 恢复审核报告

恢复审核报告可帮助你审核已请求恢复密钥访问权限的用户。 此报告的筛选条件包括发出请求的用户类型、请求的密钥类型、发生时间、成功或失败、发生时间和用户请求类型（帮助桌面、最终用户）。 此报表使管理员能够根据需要生成上下文报告。

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
<td align="left"><p>最终用户或技术支持用户发出密钥检索请求的日期和时间。</p></td>
</tr>
<tr class="even">
<td align="left"><p>请求状态</p></td>
<td align="left"><p>请求的状态。 有效状态为 "成功" （已检索密钥）或 "失败" （未检索到密钥）。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>帮助台用户</p></td>
<td align="left"><p>启动了密钥检索请求的技术支持用户。 如果技术支持用户代表最终用户检索密钥，则 "最终用户" 字段将为空。</p></td>
</tr>
<tr class="even">
<td align="left"><p>用户</p></td>
<td align="left"><p>启动密钥检索请求的最终用户。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>键类型</p></td>
<td align="left"><p>所请求的键的类型。 MBAM 收集三种密钥类型：恢复密钥密码（恢复模式下恢复计算机）;恢复密钥 ID （代表另一个用户在恢复模式下恢复计算机）;和受信任的平台模块（TPM）密码哈希（使用已锁定的 TPM 恢复计算机）。</p></td>
</tr>
<tr class="even">
<td align="left"><p>原因描述</p></td>
<td align="left"><p>请求指定键类型的原因。 原因在管理网站的驱动器恢复和管理 TPM 功能中指定。 有效条目包括用户输入的文本或以下原因代码之一：</p>
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
</ul>
<p></p></td>
</tr>
</tbody>
</table>

 

**注意** 若要将报告结果保存到文件中，请单击 "报告" 菜单栏上的 "**导出**" 按钮。

 

## 相关主题


[使用 MBAM 1.0 监视和报告 BitLocker 符合性](monitoring-and-reporting-bitlocker-compliance-with-mbam-10.md)

 

 





