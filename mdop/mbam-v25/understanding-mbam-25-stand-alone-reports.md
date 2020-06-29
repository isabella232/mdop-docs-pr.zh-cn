---
title: 了解 MBAM 2.5 独立报告
description: 了解 MBAM 2.5 独立报告
author: dansimp
ms.assetid: 78b5aaf4-8257-4722-8eb9-e0de48db6a11
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 45e84c7c3b2bcb1602890c7c5a09592324da691e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798130"
---
# 了解 MBAM 2.5 独立报告


本主题介绍了在独立拓扑中运行 Microsoft BitLocker 管理和监视（MBAM）时可用的报表。

**注意**  
如果你正在通过 Configuration Manager 集成拓扑运行 MBAM，则会从 Configuration Manager 生成报表，而不是从 MBAM 生成报表。 有关这些报告的详细信息，请参阅[查看 Configuration Manager 集成拓扑的 MBAM 2.5 报告](viewing-mbam-25-reports-for-the-configuration-manager-integration-topology.md)。



## 了解 MBAM 独立拓扑报告


MBAM 提供三种报告类型，可用于监控你的组织的 BitLocker 合规性：

-   [企业合规性报告](#bkmk-enterprisecompliance)

-   [计算机合规性报告](#bkmk-compliance)

-   [恢复审核报告](#bkmk-recovery)

在独立拓扑中运行 MBAM 时，若要访问 MBAM 报表，请打开 web 浏览器，然后打开 "管理和监视" 网站。 在左侧菜单栏中选择 "**报表**"。 从顶部菜单栏中，选择要生成的报表类型。 有关生成这些报表的详细信息，请参阅[生成 2.5 MBAM 独立报表](generating-mbam-25-stand-alone-reports.md)。

### <a href="" id="bkmk-enterprisecompliance"></a>企业合规性报告

使用此报告类型可收集你的组织中的所有 BitLocker 合规性的相关信息。 可以使用筛选器缩小搜索结果范围，以了解有关组织中计算机的合规性状态和错误状态的详细信息。

**企业合规性概述**

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
<td align="left"><p>% 豁免</p></td>
<td align="left"><p>免除 BitLocker 加密要求的计算机的百分比。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>% 非豁免</p></td>
<td align="left"><p>不受 BitLocker 加密要求免除的计算机的百分比。</p></td>
</tr>
<tr class="even">
<td align="left"><p>性</p></td>
<td align="left"><p>企业中合规性计算机的百分比。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>不符合</p></td>
<td align="left"><p>企业中不符合的计算机的百分比。</p></td>
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



**企业合规性计算机详细信息**

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
<td align="left"><p>由 MBAM 托管的用户指定的 DNS 名称。</p></td>
</tr>
<tr class="even">
<td align="left"><p>域名</p></td>
<td align="left"><p>客户端计算机所在的完全限定的域名，由 MBAM 管理。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>合规性状态</p></td>
<td align="left"><p>根据为计算机指定的策略，对计算机合规的状态。 状态是不相容的和合规的。 有关如何解释合规性状态的详细信息，请参阅以下企业合规性报告合规性状态表。</p></td>
</tr>
<tr class="even">
<td align="left"><p>免除</p></td>
<td align="left"><p>指示此计算机是否不受 BitLocker 策略的状态。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>合规性状态详细信息</p></td>
<td align="left"><p>根据指定策略，有关计算机合规性状态的错误和状态消息。</p></td>
</tr>
<tr class="even">
<td align="left"><p>上次联系人</p></td>
<td align="left"><p>计算机上次联系服务器以报告合规性状态的日期和时间。 可配置联系人频率。 有关详细信息，请参阅 MBAM 组策略设置。</p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-compliance"></a>计算机合规性报告

使用此报告类型可收集特定于计算机或用户的信息。

若要查看此报告，请单击企业合规性报告中的计算机名称，或在计算机合规性报告中键入计算机名称。 此报告显示计算机上每个驱动器（操作系统和固定数据驱动器）的详细加密信息。 它还指示应用于计算机上的每个驱动器类型的策略。 若要查看每个驱动器的详细信息，请展开 "计算机名称" 条目。

**注意**  
可移动数据卷加密状态不会显示在此报告中。



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
<td align="left"><p>在由 MBAM 托管的客户端计算机上找到的操作系统类型。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>合规性状态</p></td>
<td align="left"><p>由 MBAM 管理的计算机的整体合规性状态。 有效状态符合和不相容。</p>
<p>请注意，每个驱动器的合规性状态（请参阅下表）可能指示不同的合规性状态。 但是，此字段根据指定的策略表示符合性状态。</p></td>
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
<td align="left"><p>由 MBAM 托管的计算机上的已知用户。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>免除</p></td>
<td align="left"><p>指示此计算机是否不受 BitLocker 策略的状态。</p></td>
</tr>
<tr class="even">
<td align="left"><p>制造商</p></td>
<td align="left"><p>计算机制造商名称，它显示在计算机 BIOS 中。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>型号</p></td>
<td align="left"><p>计算机制造商模型名称，它显示在计算机 BIOS 中。</p></td>
</tr>
<tr class="even">
<td align="left"><p>合规性状态详细信息</p></td>
<td align="left"><p>根据指定的策略，有关计算机合规性状态的错误和状态消息。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>上次联系人</p></td>
<td align="left"><p>计算机上次联系服务器以报告合规性状态的日期和时间。 可配置联系人频率。 有关详细信息，请参阅 MBAM 组策略设置。</p></td>
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
<td align="left"><p>通过用于加密操作系统或固定数据卷的组策略设置选择的保护器类型。</p></td>
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



### <a href="" id="bkmk-recovery"></a>恢复审核报告

使用此报告类型审核请求访问 BitLocker 恢复密钥的用户。 该报表基于所需的筛选条件提供了多个筛选器。 你可以筛选特定类型的用户（帮助台用户或最终用户），无论请求失败还是成功，所请求的密钥的具体类型以及发生检索的日期范围。

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
<td align="left"><p>审核请求源</p></td>
<td align="left"><p>发起请求的网站。 此条目将具有两个值之一： <strong> 自助服务门户 </strong> 或 <strong> 支持人员 </strong> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>请求状态</p></td>
<td align="left"><p>请求的状态。 有效状态为 "成功" （已检索密钥）或 "失败" （未检索到密钥）。</p></td>
</tr>
<tr class="even">
<td align="left"><p>帮助台用户</p></td>
<td align="left"><p>启动了密钥检索请求的技术支持用户。</p>
<div class="alert">
<strong>注意</strong><br/><p>如果高级帮助台用户在未指定最终用户的情况下恢复密钥，则 " <strong> 最终用户" </strong> 字段将为空。 标准帮助台用户必须指定最终用户，该用户将在此字段中显示。</p>
<p>通过自助服务门户的恢复将在此字段和 "最终用户" 字段中列出请求的最终用户 <strong> </strong> 。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>最终用户</p></td>
<td align="left"><p>启动密钥检索请求的最终用户。</p></td>
</tr>
<tr class="even">
<td align="left"><p>计算机</p></td>
<td align="left"><p>已恢复的计算机的计算机名。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>键类型</p></td>
<td align="left"><p>技术支持用户或最终用户请求的键类型。 MBAM 收集的三种类型的键如下所示：</p>
<ul>
<li><p>恢复密钥密码（用于在恢复模式下恢复计算机）</p></li>
<li><p>恢复密钥 ID （用于以恢复模式代表另一个用户恢复计算机）</p></li>
<li><p>TPM 密码哈希（用于使用已锁定的 TPM 恢复计算机）</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>原因描述</p></td>
<td align="left"><p>由技术支持用户或最终用户请求指定的键类型的原因。 原因在 "驱动器恢复" 和 "管理管理和监视网站的 TPM" 功能中指定。 有效输入为用户输入的文本或以下原因代码之一：</p>
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



**注意**  
通过单击 "**报表**" 菜单栏上的 "**导出**" 按钮，可将报表结果保存到文件中。




## 相关主题


[监视和报告 BitLocker 与 MBAM 2.5 的相容性](monitoring-and-reporting-bitlocker-compliance-with-mbam-25.md)

[生成 MBAM 2.5 独立报告](generating-mbam-25-stand-alone-reports.md)



## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





