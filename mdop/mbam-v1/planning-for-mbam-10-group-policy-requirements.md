---
title: 计划 MBAM 1.0 组策略要求
description: 计划 MBAM 1.0 组策略要求
author: dansimp
ms.assetid: 0fc9c509-7850-4a8e-bb82-b949025bcb02
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f5061748107dc1d00baa41188b8cf240ec187317
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798045"
---
# 计划 MBAM 1.0 组策略要求


Microsoft BitLocker 管理和监视（MBAM）客户端管理需要应用自定义组策略设置。 本主题介绍了使用 MBAM 管理企业中的 BitLocker 驱动器加密时，组策略对象（GPO）可用的策略选项。

**重要提示**  
MBAM 不使用 Windows BitLocker 驱动器加密的默认 GPO 设置。 如果启用了默认设置，它们可能会导致冲突行为。 若要启用 MBAM 来管理 BitLocker，必须在安装 MBAM 组策略模板之后定义 GPO 策略设置。



在安装 MBAM 组策略模板之后，你可以查看和修改可启用 MBAM 管理企业 BitLocker 加密的可用自定义 MBAM GPO 策略设置。 MBAM 组策略模板必须安装在能够运行组策略管理控制台（GPMC）或高级组策略管理（AGPM） MDOP 技术的计算机上。 接下来，要编辑适用的 gpo，请打开 GPMC 或 AGPM，然后导航到以下 GPO 节点：**计算机配置** \\ **管理模板** \\ **Windows 组件** \\ **MDOP MBAM （BitLocker 管理）**。

MDOP MBAM （BitLocker Management） GPO 节点分别包含四个全局策略设置和四个子 GPO 设置节点。 四个 GPO 全局策略设置为：客户端管理、固定驱动器、操作系统驱动器和可移动驱动器。 以下各节提供了策略定义和建议的策略设置，可帮助你规划 MBAM GPO 策略设置要求。

**注意**  
有关配置建议的最低 GPO 设置以使 MBAM 管理 BitLocker 加密的详细信息，请参阅[如何编辑 MBAM 1.0 GPO 设置](how-to-edit-mbam-10-gpo-settings.md)。



## 全局策略定义


本部分介绍 MBAM 全局策略定义，可在以下 GPO 节点找到：**计算机配置** \\ **管理模板** \\ **Windows 组件** \\ **MDOP MBAM （BitLocker Management）**。

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


本部分介绍 MBAM 的客户端管理策略定义，可在以下 GPO 节点找到：**计算机配置** \\ **管理模板** \\ **Windows 组件** \\ **MDOP MBAM （BitLocker Management）**  \\  **客户端管理**。

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
<li><p><strong>MBAM 恢复和硬件服务终结点 </strong> 。 这是你必须配置以启用 MBAM 客户端 BitLocker 加密管理的第一个策略设置。 对于此设置，请输入类似于以下示例的终结点位置： <strong> http:// </strong><em> &lt; MBAM 管理和监视服务器名称 &gt; </em><strong> ： </strong><em> &lt; 端口将 web 服务绑定到 &gt; </em><strong> /MBAMRecoveryAndHardwareService/CoreService.svc </strong> 。</p></li>
<li><p><strong>选择要存储的 BitLocker 恢复信息 </strong> 。 此策略设置允许你配置密钥恢复服务以备份 BitLocker 恢复信息。 它还允许你配置状态报告服务以收集合规性和审核报告。 该策略提供一种管理方法来恢复 BitLocker 加密的数据，以帮助防止因缺少密钥信息而导致数据丢失。 状态报告和密钥恢复活动将自动并以静默方式发送到配置的报表服务器位置。</p>
<p>如果未配置或禁用此策略设置，将不会保存密钥恢复信息，并且不会向服务器报告状态报告和密钥恢复活动。 当此设置设置为 <strong> 恢复密码和密钥包时 </strong> ，将自动将恢复密码和密钥数据包备份到配置的密钥恢复服务器位置。</p></li>
<li><p><strong>以分钟为单位输入客户端检查状态频率 </strong> 。 此策略设置管理客户端在客户端计算机上检查 BitLocker 保护策略和状态的频率。 此策略还管理将客户端合规性状态保存到服务器的频率。 客户端在客户端计算机上检查 BitLocker 保护策略和状态，并且它还将按配置的频率备份客户端恢复密钥。</p>
<p>根据公司建立的要求检查计算机合规性状态的频率以及备份客户端恢复密钥的频率，设置此频率。</p></li>
<li><p><strong>MBAM 状态报告服务终结点 </strong> 。 这是你必须配置以启用 MBAM 客户端 BitLocker 加密管理的第二个策略设置。 对于此设置，请使用以下示例输入终结点位置： <strong> http:// </strong><em> &lt; MBAM 管理和监视服务器名称 &gt; </em><strong> ： </strong><em> &lt; 端口将 web 服务绑定到 &gt; </em><strong> /MBAMComplianceStatusService/StatusReportingService。 svc </strong> 。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>允许硬件兼容性检查</p></td>
<td align="left"><p>建议的配置： <strong> 已启用</strong></p>
<p>此策略设置允许你在 MBAM 客户端计算机的驱动器上启用 BitLocker 保护之前，管理硬件兼容性验证。</p>
<p>如果您的企业有较旧的计算机硬件或不支持受信任的平台模块（TPM）的计算机，则应启用此策略选项。 如果满足上述任一条件，请启用硬件兼容性验证，以确保 MBAM 仅应用于支持 BitLocker 的计算机模型。 如果你的组织中的所有计算机都支持 BitLocker，则无需部署硬件兼容性，你可以将此策略设置为 " <strong> 未配置" </strong> 。</p>
<p>如果启用此策略设置，则在该策略在计算机驱动器上启用 BitLocker 保护之前，每隔24小时验证一次硬件兼容性列表的计算机型号。</p>
<div class="alert">
<strong>注意</strong><br/><p>在启用此策略设置之前，请确保你已 <strong> </strong> 在 <strong> 配置 MBAM 服务策略选项中配置了 MBAM 恢复和硬件服务终结点设置 </strong> 。</p>
</div>
<div>

</div>
<p>如果禁用或未配置此策略设置，则不会根据硬件兼容性列表验证计算机模型。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>配置用户豁免策略</p></td>
<td align="left"><p>建议的配置： <strong> 未配置</strong></p>
<p>此策略设置允许你配置网站地址、电子邮件地址或电话号码，以指示用户向 BitLocker 加密请求豁免。</p>
<p>如果启用此策略设置并提供网站地址、电子邮件地址或电话号码，用户将看到一个对话框，其中提供了有关如何申请来自 BitLocker 保护的豁免的说明。 有关如何为用户启用 BitLocker 加密免除的详细信息，请参阅 <a href="how-to-manage-user-bitlocker-encryption-exemptions-mbam-1.md" data-raw-source="[How to Manage User BitLocker Encryption Exemptions](how-to-manage-user-bitlocker-encryption-exemptions-mbam-1.md)"> 如何管理用户 Bitlocker 加密免除 </a> 。</p>
<p>如果禁用或未配置此策略设置，则不会向用户显示有关如何申请豁免请求的说明。</p>
<div class="alert">
<strong>注意</strong><br/><p>用户豁免按用户管理，而不是按计算机进行管理。 如果多个用户登录到同一台计算机，并且一位用户没有豁免，计算机将被加密。</p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



## 固定驱动器策略定义


本部分介绍 MBAM 的固定驱动器策略定义，可在以下 GPO 节点找到：**计算机配置** \\ **管理模板** \\ **Windows 组件** \\ **MDOP MBAM （BitLocker Management）** 已  \\  **修复的驱动器**。

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
<td align="left"><p>建议的配置： <strong> 启用 </strong> ， <strong> </strong> 如果需要加密操作系统卷，请选中 "启用自动解锁固定数据驱动器" 复选框。</p>
<p>通过此策略设置，你可以管理是否加密固定的驱动器。</p>
<p>如果启用此策略，请不要禁用 " <strong> 为固定数据驱动器配置密码使用密码" </strong> 策略。</p>
<p>如果 <strong> 选中 "启用自动解锁固定数据驱动器" </strong> 复选框，则操作系统卷必须加密。</p>
<p>如果启用此策略设置，则用户需要将所有固定驱动器置于 BitLocker 保护下，这将加密驱动器。</p>
<p>如果不配置此策略，或者禁用此策略，则不需要用户在 BitLocker 保护下放置固定的驱动器。</p>
<p>如果禁用此策略，MBAM 代理将对任何已加密的固定驱动器进行解密。</p>
<p>如果不需要加密操作系统卷，请清除 " <strong> 启用自动解锁固定数据驱动器" </strong> 复选框。</p></td>
</tr>
<tr class="even">
<td align="left"><p>拒绝不受 BitLocker 保护的固定驱动器的 "写入" 权限</p></td>
<td align="left"><p>建议的配置： <strong> 未配置</strong></p>
<p>此策略设置确定计算机上的固定驱动器是否需要 BitLocker 保护，以便它们可写。 启用 BitLocker 时，将应用此策略设置。</p>
<p>当未配置策略时，计算机上的所有固定驱动器都将以读/写权限挂载。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>允许从早期版本的 Windows 访问受 BitLocker 保护的固定驱动器</p></td>
<td align="left"><p>建议的配置： <strong> 未配置</strong></p>
<p>启用此策略可解锁和查看在运行 Windows Server 2008、Windows Vista、Windows XP SP3 或 Windows XP SP2 的计算机上使用文件分配表（FAT）文件系统格式化的固定驱动器。</p>
<p>这些操作系统对受 BitLocker 保护的驱动器具有只读权限。</p>
<p>禁用策略时，无法解锁用 FAT 文件系统格式化的固定驱动器，并且无法在运行 Windows Server 2008、Windows Vista、Windows XP SP3 或 Windows XP SP2 的计算机上查看其内容。</p></td>
</tr>
<tr class="even">
<td align="left"><p>为固定驱动器配置密码的使用</p></td>
<td align="left"><p>建议的配置： <strong> 未配置</strong></p>
<p>启用此策略以在固定驱动器上配置密码保护。</p>
<p>当未配置策略时，将支持密码，默认设置不包括密码复杂性要求，并且只需要八个字符。</p>
<p>若要获得更高的安全性，请启用此策略并选择 <strong> "需要密码才能修复固定数据驱动器 </strong> "，选择 <strong> "需要密码复杂性 </strong> "，然后设置所需的 <strong> 最小密码长度 </strong> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>选择如何恢复受 BitLocker 保护的固定驱动器</p></td>
<td align="left"><p>建议的配置： <strong> 未配置</strong></p>
<p>将此策略配置为启用 BitLocker 数据恢复代理或将 BitLocker 恢复信息保存到 Active Directory 域服务（AD DS）。</p>
<p>如果未配置此策略，则允许 BitLocker 数据恢复代理，并且不会将恢复信息备份到 AD DS。 MBAM 不需要将恢复信息备份到 AD DS。</p></td>
</tr>
</tbody>
</table>



## 操作系统驱动器策略定义


本部分介绍 MBAM 的操作系统驱动器策略定义，可在以下 GPO 节点找到：**计算机配置** \\ **管理模板** \\ **Windows 组件** \\ **MDOP MBAM （BitLocker Management）**  \\  **操作系统驱动器**。

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
<p>此策略设置确定操作系统驱动器是否将加密。</p>
<p>配置此策略以执行以下操作：</p>
<ul>
<li><p>为操作系统驱动器强制执行 BitLocker 保护。</p></li>
<li><p>将 "PIN 使用情况" 配置为使用受信任的平台模块（TPM） PIN 以实现操作系统保护。</p></li>
<li><p>配置增强的启动 Pin 以允许字符（如大写字母和小写字母）和数字。 MBAM 不支持将符号和空格用于增强的 Pin，即使 BitLocker 支持符号和空格也是如此。</p></li>
</ul>
<p>如果启用此策略设置，则用户需要使用 BitLocker 保护操作系统驱动器。</p>
<p>如果未配置或禁用此设置，则不需要用户使用 BitLocker 保护操作系统驱动器。</p>
<p>如果禁用此策略，MBAM 代理将对操作系统卷进行解密（如果已加密）。</p>
<p>如果启用此策略设置，则要求用户使用 BitLocker 保护保护操作系统，并且驱动器已加密。 根据您的加密要求，您可以选择操作系统驱动器的保护方法。</p>
<p>对于更高的安全要求，请使用 TPM + PIN，允许增强的 pin，并将最小 PIN 长度设置为八个字符。</p>
<p>当启用 TPM + 引脚保护器的此策略时，可以考虑禁用 " <strong> 系统 </strong>  /  <strong> 电源管理 </strong>  /  <strong> 睡眠设置 </strong> " 下的以下策略：</p>
<ul>
<li><p>睡眠（接通）时允许待机状态（S1-S3）</p></li>
<li><p>睡眠时允许待机状态（S1-S3）（使用电池）</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>配置 TPM 平台验证配置文件</p></td>
<td align="left"><p>建议的配置： <strong> 未配置</strong></p>
<p>此策略设置允许你配置计算机上的 TPM 安全硬件如何保护 BitLocker 加密密钥。 如果计算机没有兼容的 TPM 或 BitLocker 已启用 TPM 保护，则此策略设置不适用。</p>
<p>如果未配置此策略，TPM 将使用默认平台验证配置文件或由安装脚本指定的平台验证配置文件。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>选择如何恢复受 BitLocker 保护的操作系统驱动器</p></td>
<td align="left"><p>建议的配置： <strong> 未配置</strong></p>
<p>将此策略配置为启用 BitLocker 数据恢复代理或将 BitLocker 恢复信息保存到 Active Directory 域服务（AD DS）。</p>
<p>如果未配置此策略，则允许数据恢复代理，并且不会将恢复信息备份到 AD DS。</p>
<p>MBAM 操作不需要将恢复信息备份到 AD DS。</p></td>
</tr>
</tbody>
</table>



## 可移动驱动器策略定义


本部分介绍了 MBAM 的可移动驱动器策略定义，可在以下 GPO 节点找到：**计算机配置** \\ **管理模板** \\ **Windows 组件** \\ **MDOP MBAM （BitLocker Management）**  \\  **可移动驱动器**。

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
<td align="left"><p>控制在可移动驱动器上使用 BitLocker</p></td>
<td align="left"><p>建议的配置： <strong> 已启用</strong></p>
<p>此策略控制对可移动数据驱动器使用 BitLocker。</p>
<p>启用 " <strong> 允许用户对可移动数据驱动器应用 bitlocker 保护" </strong> 选项，以允许用户在可移动数据驱动器上运行 bitlocker 设置向导。</p>
<p>启用 " <strong> 允许用户暂停和解密可移动数据驱动器上的 bitlocker" </strong> 选项，允许用户从驱动器中删除 bitlocker 驱动器加密，或在执行维护时暂停加密。</p>
<p>如果已选中此策略并 <strong> 选中 "允许用户对可移动数据驱动器应用 BitLocker 保护" </strong> 选项，则 MBAM 客户端会将可移动驱动器的恢复信息保存到 MBAM 密钥恢复服务器，并允许用户在密码丢失时恢复驱动器。</p></td>
</tr>
<tr class="even">
<td align="left"><p>拒绝不受 BitLocker 保护的可移动驱动器的 "写入" 权限</p></td>
<td align="left"><p>建议的配置： <strong> 未配置</strong></p>
<p>启用此策略以允许对 BitLocker 受保护的驱动器的仅写权限。</p>
<p>如果启用此策略，则计算机上的所有可移动数据驱动器都需要加密才能允许写入权限。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>允许从早期版本的 Windows 访问受 BitLocker 保护的可移动驱动器</p></td>
<td align="left"><p>建议的配置： <strong> 未配置</strong></p>
<p>启用此策略可解锁和查看在运行 Windows Server 2008、Windows Vista、Windows XP SP3 或 Windows XP SP2 的计算机上使用（FAT）文件系统格式化的固定驱动器。</p>
<p>这些操作系统对受 BitLocker 保护的驱动器具有只读权限。</p>
<p>禁用策略时，无法解锁用 FAT 文件系统格式化的可移动驱动器，并且无法在运行 Windows Server 2008、Windows Vista、Windows XP SP3 或 Windows XP SP2 的计算机上查看其内容。</p></td>
</tr>
<tr class="even">
<td align="left"><p>为可移动数据驱动器配置密码的使用</p></td>
<td align="left"><p>建议的配置： <strong> 未配置</strong></p>
<p>启用此策略以在可移动数据驱动器上配置密码保护。</p>
<p>如果未配置此策略，则密码支持的默认设置包括密码复杂性要求，并且只需要八个字符。</p>
<p>为了提高安全性，你可以启用此策略，并选择 <strong> "需要密码以使用可移动数据驱动器 </strong> "，选择 <strong> "需要密码复杂性 </strong> "，然后设置首选的 <strong> 最小密码长度 </strong> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>选择可以如何恢复受 BitLocker 保护的可移动驱动器</p></td>
<td align="left"><p>建议的配置： <strong> 未配置</strong></p>
<p>你可以将此策略配置为启用 BitLocker 数据恢复代理或将 BitLocker 恢复信息保存到 Active Directory 域服务（AD DS）。</p>
<p>如果策略设置为 <strong> "未配置" </strong> ，则允许数据恢复代理，并且不会将恢复信息备份到 AD DS。</p>
<p>MBAM 操作不需要将恢复信息备份到 AD DS。</p></td>
</tr>
</tbody>
</table>



## 相关主题


[针对 MBAM 1.0 准备环境](preparing-your-environment-for-mbam-10.md)









