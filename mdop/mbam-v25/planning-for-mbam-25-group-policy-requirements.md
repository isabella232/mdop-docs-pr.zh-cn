---
title: 规划 MBAM 2.5 组策略要求
description: 规划 MBAM 2.5 组策略要求
author: dansimp
ms.assetid: 82d545dc-3fbf-4b46-b62f-47fe178a7c44
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 4beeb9f88f16e7d48d145861c398a90fa29f3491
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803434"
---
# 规划 MBAM 2.5 组策略要求


使用以下信息确定可用于管理企业中的 Microsoft BitLocker 管理和监视（MBAM）客户端计算机的 BitLocker 保护器的类型。

## MBAM 支持的 BitLocker 保护器的类型


MBAM 支持以下类型的 BitLocker 保护器。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">驱动器或卷的类型</th>
<th align="left">支持的 BitLocker 保护器</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>操作系统卷</p></td>
<td align="left"><ul>
<li><p><strong>受信任的平台模块 (TPM)</strong></p></li>
<li><p><strong>TPM + PIN</strong></p></li>
<li><p><strong>TPM + USB 密钥 </strong> -仅当操作系统卷在安装 MBAM 之前已加密时才受支持</p></li>
<li><p><strong></strong> - 仅在安装 MBAM 之前加密操作系统卷时支持 TPM + 引脚 + USB 密钥</p></li>
<li><p><strong></strong> - 仅适用于 Windows To Go 设备、固定数据驱动器、windows 8、windows 8.1 和没有 TPM 的 windows 10 设备支持的密码</p></li>
<li><p><strong></strong> - 在卷加密过程中自动应用的数字密码，不需要在 Windows 7 上的 FIPS 模式下进行配置</p></li>
<li><p><strong>数据恢复代理（DRA）</strong></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>固定数据驱动器</p></td>
<td align="left"><ul>
<li><p><strong>密码</strong></p></li>
<li><p><strong>自动解锁</strong></p></li>
<li><p><strong></strong> - 在卷加密过程中自动应用的数字密码，不需要在 Windows 7 上的 FIPS 模式下进行配置</p></li>
<li><p><strong>数据恢复代理（DRA）</strong></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>可移动驱动器</p></td>
<td align="left"><ul>
<li><p><strong>密码</strong></p></li>
<li><p><strong>自动解锁</strong></p></li>
<li><p><strong></strong> - 作为卷加密的一部分自动应用的数字密码，不需要进行配置</p></li>
<li><p><strong>数据恢复代理（DRA）</strong></p></li>
</ul></td>
</tr>
</tbody>
</table>



### 支持已使用的空间加密 BitLocker 策略

在 MBAM 2.5 SP1 中，如果通过 BitLocker 组策略启用已使用的空间加密，MBAM 客户端将接受它。

此组策略设置称为 **"在操作系统驱动器上强制执行驱动器加密类型"** ，位于以下 GPO 节点中： "**计算机配置** &gt; **管理模板**" &gt; **Windows 组件**" &gt; **BitLocker 驱动器加密** &gt; **操作系统驱动器**"。 如果启用此策略并选择 "**仅限已用空间" 加密**的加密类型，则 MBAM 将接受该策略，并且 BitLocker 将仅加密卷上使用的磁盘空间。

## 如何获取 MBAM 组策略模板并编辑设置


准备好配置所需的 MBAM 组策略设置时，请执行下列操作：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">后续步骤</th>
<th align="left">获取说明的位置</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>将 MBAM 组策略模板从 <a href="https://go.microsoft.com/fwlink/p/?LinkId=393941" data-raw-source="[How to Get MDOP Group Policy (.admx) Templates](https://go.microsoft.com/fwlink/p/?LinkId=393941)"> 如何获取 MDOP 组策略（admx）模板中 </a> ，并将其安装在能够运行组策略管理控制台（GPMC）或高级组策略管理（AGPM）的计算机上。</p></td>
<td align="left"><p><a href="copying-the-mbam-25-group-policy-templates.md" data-raw-source="[Copying the MBAM 2.5 Group Policy Templates](copying-the-mbam-25-group-policy-templates.md)">复制 MBAM 2.5 组策略模板</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>配置要在企业中使用的组策略设置。</p></td>
<td align="left"><p><a href="editing-the-mbam-25-group-policy-settings.md" data-raw-source="[Editing the MBAM 2.5 Group Policy Settings](editing-the-mbam-25-group-policy-settings.md)">编辑 MBAM 2.5 组策略设置</a></p></td>
</tr>
</tbody>
</table>



## MBAM 组策略设置的说明


**MDOP MBAM （BitLocker Management）** GPO 节点包含四个全局策略设置和四个子 GPO 节点：**客户端管理**、**固定驱动器**、**操作系统驱动器**和**可移动驱动器**。 以下部分介绍和建议 MBAM 组策略设置的设置。

**重要提示**  
请勿更改**BitLocker 驱动器加密**节点中的组策略设置，否则 MBAM 将无法正常工作。 当配置**MDOP MBAM （BitLocker Management）** 节点中的设置时，MBAM 会自动配置此节点中的设置。



### 全局组策略定义

本部分介绍了以下 GPO 节点 MBAM 全局组策略定义：**计算机配置** &gt; **策略** &gt; **管理模板** &gt; **Windows 组件** &gt; **MDOP MBAM （BitLocker Management）**。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">策略名称</th>
<th align="left">概述和建议的组策略设置</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>选择驱动器加密方法和密码强度</p></td>
<td align="left"><p>建议的配置： <strong> 已启用</strong></p>
<p>将此策略配置为使用特定加密方法和密码强度。</p>
<p>如果未配置此策略，BitLocker 将使用默认加密方法：使用扩散器的 AES 128 位。</p>
<div class="alert">
<strong>注意</strong><br/><p>BitLocker 计算机合规性报告的问题使其显示 &quot; &quot; 密码强度的 "未知"，即使你使用的是默认值也是如此。 若要解决此问题，请确保启用此设置并为密码强度设置一个值。</p>
</div>
<div>

</div>
<ul>
<li><p>带有扩散器的 AES 128 位-仅适用于 Windows 7</p></li>
<li><p>适用于 Windows 8、Windows 8.1 和 Windows 10 的 AES 128</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>在重启时防止内存覆盖</p></td>
<td align="left"><p>建议的配置： <strong> 未配置</strong></p>
<p>配置此策略可提高重启性能，而无需在重新启动时覆盖内存中的 BitLocker 机密。</p>
<p>如果未配置此策略，当计算机重新启动时，将从内存中删除 BitLocker 机密。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>验证智能卡证书使用规则</p></td>
<td align="left"><p>建议的配置： <strong> 未配置</strong></p>
<p>将此策略配置为使用基于智能卡证书的 BitLocker 保护。</p>
<p>如果未配置此策略，则使用默认对象标识符1.3.6.1.4.1.311.67.1.1 指定证书。</p></td>
</tr>
<tr class="even">
<td align="left"><p>为你的组织提供唯一标识符</p></td>
<td align="left"><p>建议的配置： <strong> 未配置</strong></p>
<p>将此策略配置为使用基于证书的数据恢复代理或 BitLocker To Go 阅读器。</p>
<p>如果未配置此策略，则 <strong> </strong> 不会使用 "标识" 字段。</p>
<p>如果您的公司需要更高的安全测量，则可以配置 <strong> 标识 </strong> 字段以确保所有 USB 设备都具有此字段集，并且它们与此组策略设置对齐。</p></td>
</tr>
</tbody>
</table>



### 客户端管理组策略定义

本部分介绍下列 GPO 节点的 MBAM 的客户端管理策略定义：**计算机配置** &gt; **策略** &gt; **管理模板** &gt; **Windows 组件** &gt; **MDOP MBAM （BitLocker Management）** &gt; **客户端管理**。

你可以为独立和 System Center Configuration Manager 集成拓扑设置相同的组策略设置，但有一种例外：禁用配置**MBAM 服务 &gt; MBAM Status reporting service 终结点**设置，如下表所示。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">策略名称</th>
<th align="left">概述和建议的组策略设置</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>配置 MBAM 服务</p></td>
<td align="left"><p>建议的配置： <strong> 已启用</strong></p>
<ul>
<li><p><strong>MBAM 恢复和硬件服务终结点 </strong> 。 使用此设置启用 MBAM 客户端 BitLocker 加密管理。 输入类似于以下示例的终结点位置： <strong> http （s）：// </strong><em> &lt; MBAM 管理和监视服务器名称 &gt; </em><strong> ： </strong><em> &lt; web 服务绑定到/MBAMRecoveryAndHardwareService/CoreService.svc 的端口 &gt; </em><strong> </strong> 。</p></li>
<li><p><strong>选择要存储的 BitLocker 恢复信息 </strong> 。 此策略设置允许你配置密钥恢复服务以备份 BitLocker 恢复信息。 它还允许你配置用于收集报表的状态报告服务。 该策略提供一种管理方法来恢复由 BitLocker 加密的数据，以防止因缺少密钥信息而导致数据丢失。 "状态报告" 和 "密钥恢复" 活动将自动并以静默方式发送到配置的报表服务器位置。</p>
<p>如果未配置或禁用此策略设置，则不会保存密钥恢复信息，并且不会向服务器报告状态报告和密钥恢复活动。 当此设置设置为 <strong> 恢复密码和密钥包时 </strong> ，将自动将恢复密码和密钥数据包备份到配置的密钥恢复服务器位置。</p></li>
<li><p><strong>以分钟为单位输入客户端检查状态频率 </strong> 。 此策略设置管理客户端计算机上的客户端检查 BitLocker 保护策略和状态的频率。 此策略还管理将客户端合规性状态保存到服务器的频率。 客户端在客户端计算机上检查 BitLocker 保护策略和状态，还将按配置的频率备份客户端恢复密钥。</p>
<p>根据你的公司针对检查计算机合规性状态和备份客户端恢复密钥的频率设置的要求，设置此频率。</p></li>
<li><p><strong>MBAM 状态报告服务终结点：</strong></p>
<p><strong>对于独立拓扑中的 MBAM </strong> ：必须配置此设置以启用 MBAM 客户端 BitLocker 加密管理。</p>
<p>输入类似于以下示例的终结点位置：</p>
<p><strong>http （s）：// </strong><em> &lt; MBAM 管理和监视服务器名称 &gt; </em><strong> ： </strong><em> &lt; web 服务绑定到的端口 &gt; </em><strong> /MBAMComplianceStatusService/StatusReportingService.svc</strong></p>
<p><strong>对于 Configuration Manager 集成拓扑中的 MBAM </strong> ：禁用此设置。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>配置用户豁免策略</p></td>
<td align="left"><p>建议的配置： <strong> 未配置</strong></p>
<p>通过此策略设置，你可以配置网站地址、电子邮件地址或电话号码，以指示用户向 BitLocker 加密请求豁免。</p>
<p>如果启用此策略设置并提供网站地址、电子邮件地址或电话号码，用户将看到一个对话框，其中提供了有关如何申请来自 BitLocker 保护的豁免的说明。 有关为用户启用 BitLocker 加密免除的详细信息，请参阅 <a href="how-to-manage-user-bitlocker-encryption-exemptions-mbam-25.md" data-raw-source="[How to Manage User BitLocker Encryption Exemptions](how-to-manage-user-bitlocker-encryption-exemptions-mbam-25.md)"> 如何管理用户 Bitlocker 加密免除 </a> 。</p>
<p>如果禁用或未配置此策略设置，将不向用户显示豁免请求说明。</p>
<div class="alert">
<strong>注意</strong><br/><p>用户豁免按用户管理，而不是按计算机进行管理。 如果多个用户登录到同一台计算机，而任何一个用户没有豁免，则该计算机已加密。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>配置客户体验改善计划</p></td>
<td align="left"><p>建议的配置： <strong> 已启用</strong></p>
<p>此策略设置允许你配置 MBAM 用户如何加入客户体验改善计划。 此程序将收集有关计算机硬件以及用户如何使用 MBAM 的信息，而无需中断其工作。 此信息可帮助 Microsoft 确定要改进的 MBAM 功能。 Microsoft 不会使用此信息识别或联系 MBAM 用户。</p>
<p>如果启用此策略设置，则用户可以加入客户体验改善计划。</p>
<p>如果禁用此策略设置，则用户无法加入客户体验改善计划。</p>
<p>如果未配置此策略设置，则用户可以选择加入客户体验改善计划。</p></td>
</tr>
<tr class="even">
<td align="left"><p>提供安全策略链接的 URL</p></td>
<td align="left"><p>建议的配置： <strong> 已启用</strong></p>
<p>使用此策略设置指定显示给最终用户的 URL，作为名为 " &quot; 公司安全策略" 的链接。 &quot;该链接指向公司的内部安全策略，并向最终用户提供有关加密要求的信息。 当 MBAM 提示用户加密驱动器时，将显示该链接。</p>
<p>如果启用此策略设置，则可以配置安全策略链接的 URL。</p>
<p>如果禁用或未配置此策略设置，则不会向用户显示 "安全策略" 链接。</p></td>
</tr>
</tbody>
</table>



### 已修复的驱动器组策略定义

本部分介绍了在下列 GPO 节点处进行 Microsoft BitLocker 管理和监视的固定驱动器策略定义：**计算机配置** &gt; **策略** &gt; **管理模板** &gt; **Windows 组件** &gt; **MDOP MBAM （BitLocker Management）** 已 &gt; **修复的驱动器**。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">策略名称</th>
<th align="left">概述和建议的组策略设置</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>固定数据驱动器加密设置</p></td>
<td align="left"><p>建议的配置： <strong> 已启用</strong></p>
<p>通过此策略设置，你可以管理固定数据驱动器是否必须加密。</p>
<p>如果需要加密操作系统卷，请单击 " <strong> 启用自动解锁固定数据驱动器" </strong> 。</p>
<p>如果启用此策略，则不能禁用 " <strong> 配置固定数据驱动器的密码使用" </strong> 策略，除非你要启用或要求对固定数据驱动器使用自动解锁。</p>
<p>如果必须对固定数据驱动器使用自动解锁，必须配置要加密的操作系统卷。</p>
<p>如果启用此策略设置，则用户需要将所有固定的数据驱动器置于 BitLocker 保护下，然后再加密数据驱动器。</p>
<p>如果未配置此策略设置，则不需要用户在 BitLocker 保护下放置固定的数据驱动器。 如果在对固定数据驱动器进行加密之后应用此策略，MBAM 代理将对加密的固定数据驱动器进行解密。</p>
<p>如果禁用此策略设置，则用户无法在 "BitLocker 保护" 下放置固定数据驱动器。</p></td>
</tr>
<tr class="even">
<td align="left"><p>拒绝对不受 BitLocker 保护的固定驱动器的写访问</p></td>
<td align="left"><p>建议的配置： <strong> 未配置</strong></p>
<p>此策略设置确定固定数据驱动器是否需要 BitLocker 保护才能在计算机上写入。 启用 BitLocker 时，将应用此策略设置。</p>
<p>当未配置策略时，计算机上的所有固定数据驱动器都将以读/写权限挂载。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>允许从早期版本的 Windows 访问受 BitLocker 保护的固定驱动器</p></td>
<td align="left"><p>建议的配置： <strong> 未配置</strong></p>
<p>启用此策略，以便可以在运行 Windows Server 2008、Windows Vista、Windows XP SP3 或具有 SP2 的 Windows XP 的计算机上解锁和查看具有 FAT 文件系统的固定驱动器。</p>
<p>如果启用或未配置此策略，则可以解锁通过 FAT 文件系统格式化的固定驱动器，并且可以在运行 Windows Server 2008、Windows Vista、Windows XP SP3 的计算机或具有 SP2 的 Windows XP 的计算机上查看其内容。 这些操作系统对受 BitLocker 保护的驱动器具有只读权限。</p>
<p>禁用该策略时，无法解锁通过 FAT 文件系统格式化的固定驱动器，并且无法在运行 Windows Server 2008、Windows Vista、Windows XP SP3 或 Windows XP SP2 的计算机上查看其内容。</p></td>
</tr>
<tr class="even">
<td align="left"><p>为固定驱动器配置密码的使用</p></td>
<td align="left"><p>建议的配置： <strong> 未配置</strong></p>
<p>使用此策略指定是否需要密码来解锁受 BitLocker 保护的固定数据驱动器。</p>
<p>如果启用此策略设置，则用户可以配置满足你定义的要求的密码。 BitLocker 使用户能够使用驱动器上提供的任何保护程序解锁驱动器。</p>
<p>启用 BitLocker 时，将强制执行这些设置，而不是在解锁卷时执行。</p>
<p>如果禁用此策略设置，则不允许用户使用密码。</p>
<p>如果未配置策略，则密码受默认设置支持，默认设置不包括密码复杂性要求，并且不需要八个字符。</p>
<p>若要获得更高的安全性，请启用此策略，然后选择 <strong> "需要密码才能使用固定数据驱动器" </strong> ，单击 " <strong> 需要密码复杂性 </strong> "，然后设置所 <strong> 需的最小密码长度 </strong> 。</p>
<p>如果禁用此策略设置，则不允许用户使用密码。</p>
<p>如果未配置此策略设置，则密码支持的默认设置（不包括密码复杂性要求），并且不需要八个字符。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>选择如何恢复受 BitLocker 保护的固定驱动器</p></td>
<td align="left"><p>建议的配置： <strong> 未配置</strong></p>
<p>将此策略配置为启用 BitLocker 数据恢复代理或将 BitLocker 恢复信息保存到 Active Directory 域服务（AD DS）。</p>
<p>如果未配置策略，则允许 BitLocker 数据恢复代理，并且不会将恢复信息备份到 AD DS。 MBAM 不需要将恢复信息备份到 AD DS。</p></td>
</tr>
<tr class="even">
<td align="left"><p>加密策略强制设置</p></td>
<td align="left"><p>建议的配置： <strong> 已启用</strong></p>
<p>使用此策略设置配置固定数据驱动器可以保持不兼容的天数，直到它们强制遵从 MBAM 策略。 用户不能推迟所需操作或在宽限期后向其请求豁免。 宽限期在固定数据驱动器被确定为不相容时开始。 但是，固定数据驱动器策略不会强制实施，直到操作系统驱动器符合要求。</p>
<p>如果宽限期已过，并且固定数据驱动器仍不合规，则用户无法选择延期或请求豁免。 如果加密过程需要用户输入，则会显示一个对话框，用户在提供所需的信息之前无法关闭该对话框。</p>
<p><strong> </strong> 在 " <strong> 配置固定驱动器的不符合性宽限期天数" 中输入 0 </strong> ，以强制在操作系统驱动器的宽限期到期后立即开始加密过程。</p>
<p>如果禁用或未配置此设置，则不强制用户遵守 MBAM 策略。</p>
<p>如果无需用户交互即可添加保护程序，则在宽限期到期后，加密将在后台开始。</p></td>
</tr>
</tbody>
</table>



### 操作系统驱动器组策略定义

本部分介绍了以下 GPO 节点上的 Microsoft BitLocker 管理和监视的操作系统驱动器策略定义：**计算机配置** &gt; **策略** &gt; **管理模板** &gt; **Windows 组件** &gt; **MDOP MBAM （BitLocker 管理）** &gt; **操作系统驱动器**。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">策略名称</th>
<th align="left">概述和建议的组策略设置</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>操作系统驱动器加密设置</p></td>
<td align="left"><p>建议的配置： <strong> 已启用</strong></p>
<p>通过此策略设置，你可以管理操作系统驱动器是否必须加密。</p>
<p>若要获得更高的安全性，请考虑在 <strong> </strong> &gt; <strong> </strong> &gt; <strong> </strong> 使用 TPM + 引脚保护器启用时在系统电源管理睡眠设置中禁用以下策略设置：</p>
<ul>
<li><p>睡眠（接通）时允许待机状态（S1-S3）</p></li>
<li><p>睡眠时允许待机状态（S1-S3）（使用电池）</p></li>
</ul>
<p>如果你运行的是 Microsoft Windows 8 或更高版本，并且想要在没有 TPM 的计算机上使用 BitLocker，请选中 " <strong> 允许没有兼容的 TPM 的 bitlocker" </strong> 复选框。 在此模式下，启动时需要密码。 如果您忘记了密码，则必须使用其中一个 BitLocker 恢复选项来访问驱动器。</p>
<p>在具有兼容的 TPM 的计算机上，启动时可以使用两种类型的身份验证方法为加密数据提供额外保护。 当计算机启动时，它只能使用 TPM 进行身份验证，也可以要求输入个人识别码（PIN）。</p>
<p>如果启用此策略设置，则用户必须将操作系统驱动器置于 BitLocker 保护下，然后再加密驱动器。</p>
<p>如果禁用此策略，则用户无法将操作系统驱动器置于 BitLocker 保护下。 如果在加密操作系统驱动器后应用此策略，则会解密驱动器。</p>
<p>如果未配置此策略，则不需要将操作系统驱动器置于 "BitLocker 保护" 下。</p></td>
</tr>
<tr class="even">
<td align="left"><p>允许增强的 Pin 启动</p></td>
<td align="left"><p>建议的配置： <strong> 未配置</strong></p>
<p>使用此策略设置配置是否将增强的启动 Pin 用于 BitLocker。 增强的启动 Pin 允许使用包括大写字母和小写字母、符号、数字和空格的字符。 启用 BitLocker 时，将应用此策略设置。</p>
<p>如果启用此策略设置，则设置的所有新 BitLocker 启动引脚将使最终用户能够创建增强的 Pin。 但是，并非所有计算机都可以支持预引导环境中的增强引脚。 我们强烈建议管理员先评估其系统是否与此功能兼容，然后再启用其使用。</p>
<p>选中 " <strong> 需要 ASCII 专用引脚" </strong> 复选框，以使增强引脚更好地与限制可在预引导环境中输入的字符类型或字符数的计算机兼容。</p>
<p>如果禁用或未配置此策略设置，则不使用增强型 Pin。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>选择可以如何恢复受 BitLocker 保护的操作系统驱动器</p></td>
<td align="left"><p>建议的配置： <strong> 未配置</strong></p>
<p>将此策略配置为启用 BitLocker 数据恢复代理或将 BitLocker 恢复信息保存到 Active Directory 域服务（AD DS）。</p>
<p>如果未配置此策略，则允许数据恢复代理，并且不会将恢复信息备份到 AD DS。</p>
<p>MBAM 操作不需要将恢复信息备份到 AD DS。</p></td>
</tr>
<tr class="even">
<td align="left"><p>为操作系统驱动器配置密码的使用</p></td>
<td align="left"><p>建议的配置： <strong> 未配置</strong></p>
<p>使用此策略设置可设置用于解锁受 BitLocker 保护的操作系统驱动器的密码的约束。 如果在操作系统驱动器上允许非 TPM 保护器，则可以设置密码、强制密码的复杂性要求，并配置密码的最小长度。 为了使复杂性要求设置生效，你还必须启用组策略设置 &quot; 密码必须满足 &quot; 位于 "计算机配置 &gt; Windows 设置 &gt; 安全设置" &gt; 帐户策略 &gt; 密码策略中的复杂性要求。</p>
<div class="alert">
<strong>注意</strong><br/><p>启用 BitLocker 时，将强制执行这些设置，而不是在解锁卷时执行。 BitLocker 允许您使用驱动器上提供的任何保护程序解锁驱动器。</p>
</div>
<div>

</div>
<p>如果启用此策略设置，则用户可以配置满足你定义的要求的密码。 若要对密码强制执行复杂性要求，请单击 " <strong> 需要密码复杂性" </strong> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>为基于 BIOS 的固件配置配置 TPM 平台验证配置文件</p></td>
<td align="left"><p>建议的配置： <strong> 未配置</strong></p>
<p>通过此策略设置，你可以配置计算机&#39;s 受信任的平台模块（TPM）安全硬件如何保护 BitLocker 加密密钥。 如果计算机没有兼容的 TPM，或者如果 BitLocker 已使用 TPM 保护启用，则此策略设置不适用。</p>
<div class="alert">
<strong>重要提示</strong><br/><p>此组策略设置仅适用于使用启用了兼容性服务模块（CSM）的具有 BIOS 配置的计算机或具有 UEFI 固件的计算机。 使用本机 UEFI 固件配置的计算机将不同的值存储到平台配置寄存器（PCRs）中。 使用 " &quot; 配置本机 uefi 固件配置" 组策略设置的 tpm 平台验证配置文件 &quot; ，为使用本机 uefi 固件的计算机配置 tpm PCR 配置文件。</p>
</div>
<div>

</div>
<p>如果启用 BitLocker 之前启用此策略设置，则可以在取消对 BitLocker 加密的操作系统驱动器的访问之前配置 TPM 验证的启动组件。 如果这些组件中的任何一个在 BitLocker 保护生效时更改，则 TPM 不会释放加密密钥以解锁驱动器，而是显示 BitLocker 恢复控制台，并且要求你提供恢复密码或恢复密钥以解锁驱动器。</p>
<p>如果禁用或未配置此策略设置，则 BitLocker 使用由安装脚本指定的默认平台验证配置文件或平台验证配置文件。</p></td>
</tr>
<tr class="even">
<td align="left"><p>配置 TPM 平台验证配置文件</p></td>
<td align="left"><p>建议的配置： <strong> 未配置</strong></p>
<p>通过此策略设置，你可以配置计算机&#39;s 受信任的平台模块（TPM）安全硬件如何保护 BitLocker 加密密钥。 如果计算机没有兼容的 TPM，或者如果 BitLocker 已使用 TPM 保护启用，则此策略设置不适用。</p>
<p>如果启用 BitLocker 之前启用此策略设置，则可以在取消对 BitLocker 加密的操作系统驱动器的访问之前配置 TPM 验证的启动组件。 如果这些组件中的任何一个在 BitLocker 保护生效时更改，则 TPM 不会释放加密密钥以解锁驱动器，而是显示 BitLocker 恢复控制台，并且要求你提供恢复密码或恢复密钥以解锁驱动器。</p>
<p>如果禁用或未配置此策略设置，则 BitLocker 使用由安装脚本指定的默认平台验证配置文件或平台验证配置文件。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>为本机 UEFI 固件配置配置 TPM 平台验证配置文件</p></td>
<td align="left"><p>建议的配置： <strong> 未配置</strong></p>
<p>通过此策略设置，你可以配置计算机&#39;s 受信任的平台模块（TPM）安全硬件如何保护 BitLocker 加密密钥。 如果计算机没有兼容的 TPM，或者如果 BitLocker 已使用 TPM 保护启用，则此策略设置不适用。</p>
<div class="alert">
<strong>重要提示</strong><br/><p>此组策略设置仅适用于具有本机 UEFI 固件配置的计算机。</p>
</div>
<div>

</div>
<p>如果启用 BitLocker 之前启用此策略设置，则可以先配置 TPM 验证的启动组件，然后再解除对 BitLocker 加密操作系统驱动器的访问。 如果这些组件中的任何一个在 BitLocker 保护生效时更改，则 TPM 不会释放加密密钥以解锁驱动器，而是显示 BitLocker 恢复控制台，并且要求你提供恢复密码或恢复密钥以解锁驱动器。</p>
<p>如果禁用或未配置此策略设置，则 BitLocker 使用由安装脚本指定的默认平台验证配置文件或平台验证配置文件。</p></td>
</tr>
<tr class="even">
<td align="left"><p>在 BitLocker 恢复后重置平台验证数据</p></td>
<td align="left"><p>建议的配置： <strong> 未配置</strong></p>
<p>使用此策略设置控制在 BitLocker 恢复后启动 Windows 时是否刷新平台验证数据。</p>
<p>如果启用此策略设置，则在 BitLocker 恢复后启动 Windows 时，将刷新平台验证数据。 如果禁用此策略设置，则在 BitLocker 恢复后启动 Windows 时，不会刷新平台验证数据。 如果未配置此策略设置，则在 BitLocker 恢复后启动 Windows 时，将刷新平台验证数据。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>使用增强的引导配置数据验证配置文件</p></td>
<td align="left"><p>建议的配置： <strong> 未配置</strong></p>
<p>通过此策略设置，你可以选择要在平台验证期间验证的特定引导配置数据（BCD）设置。</p>
<p>如果启用此策略设置，你可以添加其他设置，删除默认设置，或两者都删除。 如果禁用此策略设置，计算机将还原到类似于 Windows 7 使用的默认 BCD 配置文件的 BCD 配置文件。 如果未配置此策略设置，计算机将验证默认 Windows BCD 设置。</p>
<div class="alert">
<strong>注意</strong><br/><p>当 BitLocker 使用针对平台和引导配置数据（BCD）完整性验证（由 " &quot; 允许安全启动以实现完整性验证" 策略定义）进行安全启动时 &quot; ，将 &quot; 忽略 "使用增强的引导配置数据验证配置文件 &quot; 策略"。</p>
</div>
<div>

</div>
<p>控制启动调试（0x16000010）的设置将始终经过验证，并且在提供的字段中包含时不起作用。</p></td>
</tr>
<tr class="even">
<td align="left"><p>加密策略强制设置</p></td>
<td align="left"><p>建议的配置： <strong> 已启用</strong></p>
<p>使用此策略设置，可配置用户使用其操作系统驱动器的 MBAM 策略推迟的天数。 如果首次检测到操作系统不符合要求，则开始宽限期。 此宽限期到期后，用户无法推迟所需操作或向其请求豁免。</p>
<p>如果加密过程需要用户输入，则会显示一个对话框，用户在提供所需的信息之前无法关闭该对话框。</p>
<p>如果禁用或未配置此设置，则不强制用户遵守 MBAM 策略。</p>
<p>如果无需用户交互即可添加保护程序，则在宽限期到期后，加密将在后台开始。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>配置预启动恢复消息和 URL</p></td>
<td align="left"><p>建议的配置： <strong> 未配置</strong></p>
<p>启用此策略设置可配置自定义恢复消息，或指定在操作系统驱动器锁定时在预启动 BitLocker 恢复屏幕上显示的 URL。 此设置仅在运行 Windows 10 的客户端计算机上可用。</p>
<p>如果启用此策略，你可以为预启动恢复消息选择以下选项之一：</p>
<ul>
<li><p><strong>使用自定义恢复消息 </strong> ：选择此选项可在预启动 BitLocker 恢复屏幕中包含自定义消息。 在 " <strong> 自定义恢复消息" 选项 </strong> 框中，键入要显示的消息。 如果你还希望指定恢复 URL，请将其包含在你的自定义恢复消息中。</p></li>
<li><p><strong>使用自定义恢复 URL </strong> ：选择此选项可替换 "预启动 BitLocker 恢复" 屏幕中显示的默认 URL。 在 " <strong> 自定义恢复 URL" 选项 </strong> 框中，键入要显示的 URL。</p></li>
<li><p><strong>使用默认的恢复消息和 URL </strong> ：选择此选项可在预启动 bitlocker 恢复屏幕中显示默认的 BitLocker 恢复消息和 url。 如果你以前配置了自定义恢复消息或 URL 并希望还原到默认消息，则必须启用此策略，然后选择 " <strong> 使用默认恢复消息和 URL" </strong> 选项。</p></li>
</ul>
<div class="alert">
<strong>注意</strong><br/><p>并非所有字符和语言都在预启动中受支持。 我们建议你测试用于自定义消息或 URL 的字符是否正确显示在预启动 BitLocker 恢复屏幕上。</p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



### 可移动驱动器组策略定义

本部分介绍了用于 Microsoft BitLocker 管理和监视以下 GPO 节点的可移动驱动器组策略定义：**计算机配置** &gt; **策略** &gt; **管理模板** &gt; **Windows 组件** &gt; **MDOP MBAM （BitLocker 管理）** &gt; **可移动驱动器**。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">策略名称</th>
<th align="left">概述和建议的组策略设置</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>控制可移动驱动器上的 BitLocker 的使用</p></td>
<td align="left"><p>建议的配置： <strong> 已启用</strong></p>
<p>此策略控制对可移动数据驱动器使用 BitLocker。</p>
<p>单击 " <strong> 允许用户对可移动数据驱动器应用 bitlocker 保护" </strong> ，以允许用户在可移动数据驱动器上运行 bitlocker 设置向导。</p>
<p>单击 " <strong> 允许用户暂停和解密可移动数据驱动器上的 bitlocker"， </strong> 以使用户能够从驱动器中删除 bitlocker 驱动器加密，或者在执行维护时暂停加密。</p>
<p>如果启用此策略，并且单击 " <strong> 允许用户对可移动数据驱动器应用 BitLocker 保护" </strong> ，MBAM 客户端会将可移动驱动器的恢复信息保存到 MBAM 密钥恢复服务器，并允许用户在密码丢失时恢复驱动器。</p></td>
</tr>
<tr class="even">
<td align="left"><p>拒绝对不受 BitLocker 保护的可移动驱动器的写访问</p></td>
<td align="left"><p>建议的配置： <strong> 未配置</strong></p>
<p>启用此策略以仅允许受 BitLocker 保护的驱动器的写入权限。</p>
<p>如果启用此策略，则在允许写入权限之前，计算机上的所有可移动数据驱动器都需要加密。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>允许从早期版本的 Windows 访问受 BitLocker 保护的可移动驱动器</p></td>
<td align="left"><p>建议的配置： <strong> 未配置</strong></p>
<p>启用此策略以允许在运行 Windows Server 2008、Windows Vista、Windows XP SP3 或 Windows XP SP2 的计算机上解除锁定和查看具有 FAT 文件系统的固定驱动器。</p>
<p>如果未配置此策略，则可以在运行 Windows Server 2008、Windows Vista、windows XP SP3 或具有 SP2 的 Windows XP 的计算机上解锁具有 FAT 文件系统格式的可移动驱动器，并且可以查看其内容。 这些操作系统对受 BitLocker 保护的驱动器具有只读权限。</p>
<p>禁用策略时，无法解锁用 FAT 文件系统格式化的可移动驱动器，并且无法在运行 Windows Server 2008、Windows Vista、Windows XP SP3 或 Windows XP SP2 的计算机上查看其内容。</p></td>
</tr>
<tr class="even">
<td align="left"><p>为可移动数据驱动器配置密码的使用</p></td>
<td align="left"><p>建议的配置： <strong> 未配置</strong></p>
<p>启用此策略以在可移动数据驱动器上配置密码保护。</p>
<p>如果未配置此策略，则密码支持的默认设置（不包括密码复杂性要求），并且不需要八个字符。</p>
<p>为了提高安全性，你可以启用此策略，并选择 <strong> "需要密码以使用可移动数据驱动器 </strong> "，单击 " <strong> 需要密码复杂性 </strong> "，然后设置首选的 <strong> 最小密码长度 </strong> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>选择可以如何恢复受 BitLocker 保护的可移动驱动器</p></td>
<td align="left"><p>建议的配置： <strong> 未配置</strong></p>
<p>将此策略配置为启用 BitLocker 数据恢复代理或将 BitLocker 恢复信息保存到 Active Directory 域服务（AD DS）。</p>
<p>如果设置为 <strong> "未配置" </strong> ，则允许数据恢复代理，并且不会将恢复信息备份到 AD DS。</p>
<p>MBAM 操作不需要将恢复信息备份到 AD DS。</p></td>
</tr>
</tbody>
</table>




## 相关主题


[为 MBAM 2.5 准备你的环境](preparing-your-environment-for-mbam-25.md)

[MBAM 2.5 部署先决条件](mbam-25-deployment-prerequisites.md)


## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。






