---
title: 计划 MBAM 2.0 组策略要求
description: 计划 MBAM 2.0 组策略要求
author: dansimp
ms.assetid: f5e19dcb-eb15-4722-bb71-0734b3799eb8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f6092507996fe6f0234178c8b1abae5cea7bf836
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798143"
---
# 计划 MBAM 2.0 组策略要求


若要管理 Microsoft BitLocker 管理和监视（MBAM）客户端计算机，你需要考虑你希望在你的组织中支持的 BitLocker 保护器的类型，然后配置要应用的相应组策略设置。 本主题介绍使用 Microsoft BitLocker 管理和监视管理企业中的 BitLocker 驱动器加密时可使用的组策略设置。

MBAM 支持以下类型的适用于操作系统驱动器的 BitLocker 保护程序：受信任的平台模块（TPM）、TPM + PIN、TPM + USB 密钥以及 TPM + PIN + USB 密钥、密码、数字密码和数据恢复代理。 只有 Windows To Go 设备和没有 TPM 的 Windows 8 设备支持密码保护程序。 仅当操作系统卷在安装 MBAM 之前已加密时，MBAM 支持 TPM + USB 密钥和 TPM + 引脚 + USB 密钥保护器。

MBAM 支持固定数据驱动器的以下类型的 BitLocker 保护器：密码、自动解锁、数字密码和数据恢复代理。

数字密码保护程序将自动应用为卷加密的一部分，并且不需要进行配置。

**重要提示**  
MBAM 未使用默认 Windows BitLocker 驱动器加密组策略对象（GPO）设置，如果启用，可能会导致冲突行为。 若要启用 MBAM 来管理 BitLocker，必须在安装 MBAM 组策略模板后定义 MBAM 组策略设置。



增强的启动 Pin 可以包含字符，例如大写字母和小写字母以及数字。 与 BitLocker 不同，MBAM 不支持将符号和空格用于增强的引脚。

在能够运行组策略管理控制台（GPMC）或高级组策略管理（AGPM） MDOP 技术的计算机上安装 MBAM 组策略模板。 若要编辑启用 MBAM 功能的 GPO 设置，必须首先安装 MBAM 组策略模板，打开 GPMC 或 AGPM 以编辑适用的 gpo，然后导航到以下 GPO 节点：**计算机配置** \\ **策略** \\ **管理模板** \\ **Windows 组件** \\ **MDOP MBAM （BitLocker Management）。**

MDOP MBAM （BitLocker Management） GPO 节点包含四个全局策略设置和四个子 GPO 设置节点：客户端管理、固定驱动器、操作系统驱动器和可移动驱动器。 以下各节提供了策略定义和建议的策略设置，可帮助你规划 MBAM GPO 策略设置要求。

**注意**  
有关配置最小的推荐 GPO 设置以使 MBAM 管理 BitLocker 加密的详细信息，请参阅[如何编辑 MBAM 2.0 GPO 设置](how-to-edit-mbam-20-gpo-settings-mbam-2.md)。



## 全局策略定义


本部分介绍在以下 GPO 节点中找到的 MBAM 全局策略定义：**计算机配置** \\ **策略** \\ **管理模板** \\ **Windows 组件** \\ **MDOP MBAM （BitLocker Management）**。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">策略名称</th>
<th align="left">概述和建议的策略设置</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>选择驱动器加密方法和密码强度</p></td>
<td align="left"><p>建议的配置： <strong> 未配置</strong></p>
<p>将此策略配置为使用特定加密方法和密码强度。</p>
<p>如果未配置此策略，BitLocker 将使用具有扩散器的 AES 128 位的默认加密方法或由安装脚本指定的加密方法。</p></td>
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
<p>如果您的公司需要更高的安全测量，您可能需要配置 <strong> 标识 </strong> 字段，以确保所有 USB 设备都具有此字段集，并且它们与此组策略设置对齐。</p></td>
</tr>
</tbody>
</table>



## 客户端管理策略定义


本部分介绍在下列 GPO 节点处找到的 Microsoft BitLocker 管理和监视的客户端管理策略定义：**计算机配置** \\ **策略** \\ **管理模板** \\ **Windows 组件** \\ **MDOP MBAM （BitLocker Management）** \\ **客户端管理**。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">策略名称</th>
<th align="left">概述和建议的策略设置</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>配置 MBAM 服务</p></td>
<td align="left"><p>建议的配置： <strong> 已启用</strong></p>
<ul>
<li><p><strong>MBAM 恢复和硬件服务终结点 </strong> 。 使用此设置启用 MBAM 客户端 BitLocker 加密管理。 输入类似于以下示例的终结点位置： <strong> http:// </strong><em> &lt; MBAM 管理和监视服务器名称 &gt; </em><strong> ： </strong><em> &lt; 端口 web 服务绑定到 &gt; </em><strong> /MBAMRecoveryAndHardwareService/CoreService.svc </strong> 。</p></li>
<li><p><strong>选择要存储的 BitLocker 恢复信息 </strong> 。 此策略设置允许你配置密钥恢复服务以备份 BitLocker 恢复信息。 它还允许你配置用于收集合规性和审核报告的状态报告服务。 该策略提供一种管理方法来恢复由 BitLocker 加密的数据，以防止因缺少密钥信息而导致数据丢失。 状态报告和密钥恢复活动将自动并以静默方式发送到配置的报表服务器位置。</p>
<p>如果未配置或禁用此策略设置，将不会保存密钥恢复信息，并且不会向服务器报告状态报告和密钥恢复活动。 当此设置设置为 <strong> 恢复密码和密钥包时 </strong> ，将自动将恢复密码和密钥数据包备份到配置的密钥恢复服务器位置。</p></li>
<li><p><strong>以分钟为单位输入客户端检查状态频率 </strong> 。 此策略设置管理客户端计算机上的客户端检查 BitLocker 保护策略和状态的频率。 此策略还管理将客户端合规性状态保存到服务器的频率。 客户端在客户端计算机上检查 BitLocker 保护策略和状态，还将按配置的频率备份客户端恢复密钥。</p>
<p>根据公司设置的要求检查计算机合规性状态的频率，以及备份客户端恢复密钥的频率，设置此频率。</p></li>
<li><p><strong>MBAM 状态报告服务终结点 </strong> 。 必须将此设置配置为启用 MBAM 客户端 BitLocker 加密管理。 输入类似于以下示例的终结点位置： <strong> http:// </strong><em> &lt; MBAM 管理和监视服务器名称 &gt; </em><strong> ： </strong><em> &lt; 端口 web 服务绑定到 &gt; </em><strong> /MBAMComplianceStatusService/StatusReportingService.svc </strong> 。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>配置用户豁免策略</p></td>
<td align="left"><p>建议的配置： <strong> 未配置</strong></p>
<p>此策略设置允许你配置网站地址、电子邮件地址或电话号码，以指示用户向 BitLocker 加密请求豁免。</p>
<p>如果启用此策略设置并提供网站地址、电子邮件地址或电话号码，用户将看到一个对话框，该对话框向用户提供有关如何申请来自 BitLocker 保护的豁免的说明。 有关为用户启用 BitLocker 加密免除的详细信息，请参阅 <a href="how-to-manage-user-bitlocker-encryption-exemptions-mbam-2.md" data-raw-source="[How to Manage User BitLocker Encryption Exemptions](how-to-manage-user-bitlocker-encryption-exemptions-mbam-2.md)"> 如何管理用户 Bitlocker 加密免除 </a> 。</p>
<p>如果禁用或未配置此策略设置，将不向用户显示豁免请求说明。</p>
<div class="alert">
<strong>注意</strong><br/><p>用户豁免按用户管理，而不是按计算机进行管理。 如果多个用户登录到同一台计算机，并且任何一个用户没有豁免，计算机将被加密。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>配置客户体验改善计划</p></td>
<td align="left"><p>此策略设置允许你配置 MBAM 用户如何加入客户体验改善计划。 此程序将收集有关计算机硬件以及用户如何使用 MBAM 的信息，而无需中断其工作。 此信息可帮助 Microsoft 确定要改进的 MBAM 功能。 Microsoft 不会使用此信息识别或联系 MBAM 用户。</p>
<p>如果启用此策略设置，用户将能够加入客户体验改善计划。</p>
<p>如果禁用此策略设置，用户将无法加入客户体验改善计划。</p>
<p>如果未配置此策略设置，则用户可以选择加入客户体验改善计划。</p></td>
</tr>
</tbody>
</table>



## 固定驱动器策略定义


本部分介绍在下列 GPO 节点处找到的 Microsoft BitLocker 管理和监视的固定驱动器策略定义：**计算机配置** \\ **策略** \\ **管理模板** \\ **Windows 组件** \\ **MDOP MBAM （BitLocker Management）** 已 \\ **修复的驱动器**。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">策略名称</th>
<th align="left">概述和建议的策略设置</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>固定数据驱动器加密设置</p></td>
<td align="left"><p>建议的配置： <strong> 已启用</strong></p>
<p>通过此策略设置，您可以管理固定驱动器是否必须加密。</p>
<p>如果需要加密操作系统卷，请选择 " <strong> 启用自动解锁固定数据驱动器" </strong> 选项。</p>
<p>启用此策略时，您不得禁用 " <strong> 配置固定数据驱动器的密码使用" </strong> 策略，除非允许或需要对固定数据驱动器使用自动解锁。</p>
<p>如果需要对固定数据驱动器使用自动解锁，必须配置要加密的操作系统卷。</p>
<p>如果启用此策略设置，则用户需要将所有固定驱动器置于 BitLocker 保护下，并且驱动器将被加密。</p>
<p>如果未配置此策略设置，则不需要用户在 BitLocker 保护下放置固定驱动器。 如果在对固定数据驱动器进行加密之后应用此策略，MBAM 代理将对已加密的固定驱动器进行解密。</p>
<p>如果禁用此策略设置，用户将无法在 "BitLocker 保护" 下放置固定数据驱动器。</p></td>
</tr>
<tr class="even">
<td align="left"><p>拒绝对不受 BitLocker 保护的固定驱动器的写访问</p></td>
<td align="left"><p>建议的配置： <strong> 未配置</strong></p>
<p>此策略设置确定固定驱动器是否需要 BitLocker 保护才能在计算机上写入。 启用 BitLocker 时，将应用此策略设置。</p>
<p>当未配置策略时，计算机上的所有固定数据驱动器都将使用读写访问权限挂载。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>允许从早期版本的 Windows 访问受 BitLocker 保护的固定驱动器</p></td>
<td align="left"><p>建议的配置： <strong> 未配置</strong></p>
<p>启用此策略，让带有 FAT 文件系统的固定驱动器在运行 Windows Server 2008、Windows Vista、Windows XP SP3 或 Windows XP SP2 的计算机上被解锁和查看。</p>
<p>如果启用或未配置此策略，则可以解除对带有 FAT 文件系统格式的固定驱动器的锁定，并且可以在运行 Windows Server 2008、Windows Vista、Windows XP SP3 或 Windows XP SP2 的计算机上查看其内容。 这些操作系统具有对受 BitLocker 保护的驱动器的只读访问权限。</p>
<p>禁用策略时，无法解锁用 FAT 文件系统格式化的固定驱动器，并且无法在运行 Windows Server 2008、Windows Vista、Windows XP SP3 或 Windows XP SP2 的计算机上查看其内容。</p></td>
</tr>
<tr class="even">
<td align="left"><p>为固定驱动器配置密码的使用</p></td>
<td align="left"><p>建议的配置： <strong> 未配置</strong></p>
<p>使用此策略指定是否需要密码来解锁受 BitLocker 保护的固定数据驱动器。</p>
<p>如果启用此策略设置，则用户可以配置满足你定义的要求的密码。 BitLocker 将允许用户使用驱动器上提供的任何保护程序解锁驱动器。</p>
<p>启用 BitLocker 时强制执行这些设置，而不是在解锁卷时执行。</p>
<p>如果禁用此策略设置，则不允许用户使用密码。</p>
<p>如果未配置策略，则密码受默认设置支持，默认设置不包括密码复杂性要求，并且不需要八个字符。</p>
<p>若要获得更高的安全性，请启用此策略并选择 <strong> "需要密码才能修复固定数据驱动器 </strong> "，选择 <strong> "需要密码复杂性 </strong> "，然后设置所需的 <strong> 最小密码长度 </strong> 。</p>
<p>如果禁用此策略设置，则不允许用户使用密码。</p>
<p>如果未配置此策略设置，则密码将受默认设置支持，这些设置不包括密码复杂性要求，并且不需要八个字符。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>选择如何恢复受 BitLocker 保护的固定驱动器</p></td>
<td align="left"><p>建议的配置： <strong> 未配置</strong></p>
<p>将此策略配置为启用 BitLocker 数据恢复代理或将 BitLocker 恢复信息保存到 Active Directory 域服务（AD DS）。</p>
<p>如果未配置策略，则允许 BitLocker 数据恢复代理，并且不会将恢复信息备份到 AD DS。 MBAM 不需要将恢复信息备份到 AD DS。</p></td>
</tr>
</tbody>
</table>



## 操作系统驱动器策略定义


本部分介绍在下列 GPO 节点处找到的 Microsoft BitLocker 管理和监视的操作系统驱动器策略定义：**计算机配置** \\ **策略** \\ **管理模板** \\ **Windows 组件** \\ **MDOP MBAM （BitLocker 管理）** \\ **操作系统驱动器**。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">策略名称</th>
<th align="left">概述和建议的策略设置</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>操作系统驱动器加密设置</p></td>
<td align="left"><p>建议的配置： <strong> 已启用</strong></p>
<p>通过此策略设置，你可以管理操作系统驱动器是否必须加密。</p>
<p>若要获得更高的安全性，请考虑在 <strong> </strong> 使用 TPM + 引脚保护器启用 "系统/电源管理/睡眠设置" 中的以下策略设置：</p>
<ul>
<li><p>睡眠（接通）时允许待机状态（S1-S3）</p></li>
<li><p>睡眠时允许待机状态（S1-S3）（使用电池）</p></li>
</ul>
<p>如果你运行的是 Microsoft Windows 8 或更高版本，并且想要在没有 TPM 的计算机上使用 BitLocker，请选中 " <strong> 允许没有兼容的 TPM 的 bitlocker" </strong> 复选框。 在此模式下，启动时需要密码。 如果您忘记了密码，则必须使用其中一个 BitLocker 恢复选项来访问驱动器。</p>
<p>在具有兼容的 TPM 的计算机上，启动时可以使用两种类型的身份验证方法为加密数据提供额外保护。 当计算机启动时，它只能使用 TPM 进行身份验证，也可以要求输入个人识别码（PIN）。</p>
<p>如果启用此策略设置，则用户必须将操作系统驱动器置于 BitLocker 保护下，并且将加密驱动器。</p>
<p>如果禁用此策略，用户将无法在 BitLocker 保护下放置操作系统驱动器。 如果在加密操作系统驱动器后应用此策略，则将解密驱动器。</p>
<p>如果未配置此策略，则不需要将操作系统驱动器置于 "BitLocker 保护" 下。</p></td>
</tr>
<tr class="even">
<td align="left"><p>配置 TPM 平台验证配置文件</p></td>
<td align="left"><p>建议的配置： <strong> 未配置</strong></p>
<p>此策略设置允许你配置计算机上的 TPM 安全硬件如何保护 BitLocker 加密密钥。 如果计算机没有兼容的 TPM，或者如果 BitLocker 已使用 TPM 保护启用，则此策略设置不适用。</p>
<p>如果未配置此策略设置，TPM 将使用由安装脚本指定的默认平台验证配置文件或平台验证配置文件。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>选择可以如何恢复受 BitLocker 保护的操作系统驱动器</p></td>
<td align="left"><p>建议的配置： <strong> 未配置</strong></p>
<p>将此策略配置为启用 BitLocker 数据恢复代理或将 BitLocker 恢复信息保存到 Active Directory 域服务（AD DS）。</p>
<p>如果未配置此策略，则允许数据恢复代理，并且不会将恢复信息备份到 AD DS。</p>
<p>MBAM 操作不需要将恢复信息备份到 AD DS。</p></td>
</tr>
</tbody>
</table>



## 可移动驱动器策略定义


本部分介绍在下列 GPO 节点处找到的 Microsoft BitLocker 管理和监视的可移动驱动器策略定义：**计算机配置** \\ **策略** \\ **管理模板** \\ **Windows 组件** \\ **MDOP MBAM （BitLocker Management）**  \\  **可移动驱动器**。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">策略名称</th>
<th align="left">概述和建议的策略设置</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>控制可移动驱动器上的 BitLocker 的使用</p></td>
<td align="left"><p>建议的配置： <strong> 已启用</strong></p>
<p>此策略控制对可移动数据驱动器使用 BitLocker。</p>
<p>启用 " <strong> 允许用户对可移动数据驱动器应用 bitlocker 保护" </strong> 选项，以允许用户在可移动数据驱动器上运行 bitlocker 设置向导。</p>
<p>启用 " <strong> 允许用户暂停和解密可移动数据驱动器上的 bitlocker" </strong> 选项，允许用户从驱动器中删除 bitlocker 驱动器加密，或在执行维护时暂停加密。</p>
<p>如果启用此策略并选中 " <strong> 允许用户对可移动数据驱动器应用 BitLocker 保护" </strong> 选项，则 MBAM 客户端会将可移动驱动器的恢复信息保存到 MBAM 密钥恢复服务器，并允许用户在密码丢失时恢复驱动器。</p></td>
</tr>
<tr class="even">
<td align="left"><p>拒绝对不受 BitLocker 保护的可移动驱动器的写访问</p></td>
<td align="left"><p>建议的配置： <strong> 未配置</strong></p>
<p>启用此策略以仅允许对受 BitLocker 保护的驱动器进行写入访问。</p>
<p>如果启用此策略，则计算机上的所有可移动数据驱动器都需要加密才能允许写入访问。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>允许从早期版本的 Windows 访问受 BitLocker 保护的可移动驱动器</p></td>
<td align="left"><p>建议的配置： <strong> 未配置</strong></p>
<p>启用此策略以允许在运行 Windows Server 2008、Windows Vista、Windows XP SP3 或 Windows XP SP2 的计算机上解除锁定和查看具有 FAT 文件系统的固定驱动器。</p>
<p>如果未配置此策略，则可以在运行 Windows Server 2008、Windows Vista、windows XP SP3 或具有 SP2 的 Windows XP 的计算机上解锁带有 FAT 文件系统格式的可移动数据驱动器，并且可以查看其内容。 这些操作系统具有对受 BitLocker 保护的驱动器的只读访问权限。</p>
<p>禁用策略时，无法解锁用 FAT 文件系统格式化的可移动驱动器，并且无法在运行 Windows Server 2008、Windows Vista、Windows XP SP3 或 Windows XP SP2 的计算机上查看其内容。</p></td>
</tr>
<tr class="even">
<td align="left"><p>为可移动数据驱动器配置密码的使用</p></td>
<td align="left"><p>建议的配置： <strong> 未配置</strong></p>
<p>启用此策略以在可移动数据驱动器上配置密码保护。</p>
<p>如果未配置此策略，则密码支持的默认设置（不包括密码复杂性要求），并且不需要八个字符。</p>
<p>为了提高安全性，你可以启用此策略并选中 <strong> "可移动数据驱动器需要密码 </strong> "，选择 <strong> "需要密码复杂性 </strong> "，然后设置首选的 <strong> 最小密码长度 </strong> 。</p></td>
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


[MBAM 2.0 部署先决条件](mbam-20-deployment-prerequisites-mbam-2.md)









