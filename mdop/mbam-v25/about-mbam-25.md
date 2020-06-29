---
title: 关于 MBAM 2.5
description: 关于 MBAM 2.5
author: dansimp
ms.assetid: 1ce218ec-4d2e-4a75-8d1a-68d737a8f3c9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: d4c9ff0bc5ee3f7dc51a56cc428081a7c3783694
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803523"
---
# 关于 MBAM 2.5


Microsoft BitLocker 管理和监视（MBAM）2.5 为 BitLocker 驱动器加密提供简化的管理接口。 对于丢失或被盗的计算机，BitLocker 提供增强的防护功能，防止数据失窃或数据暴露。 BitLocker 将加密存储在 Windows 操作系统卷、驱动器和已配置数据驱动器上的所有数据。

## MBAM 概述


MBAM 2.5 具有以下功能：

-   使管理员能够自动对企业内的客户端计算机上的卷进行加密的过程。

-   使安全监察官能够快速确定单个计算机或甚至企业本身的合规性状态。

-   通过 Microsoft System Center Configuration Manager 提供集中报告和硬件管理。

-   减少了帮助台上的工作负荷，帮助最终用户提供 BitLocker PIN 和恢复密钥请求。

-   使最终用户能够使用自助服务门户单独恢复加密的设备。

-   使安全专员能够轻松审核 access 以恢复密钥信息。

-   使 Windows 企业用户能够在任何位置继续工作，确保其企业数据受到保护。

MBAM 强制执行你为你的企业设置的 BitLocker 加密策略选项，监视客户端计算机与这些策略的合规性，并报告企业和个人计算机的加密状态。 此外，MBAM 允许你在用户忘记其 PIN 或密码时，或者在其 BIOS 或启动记录发生更改时访问恢复密钥信息。

以下组可能对使用 MBAM 管理 BitLocker 感兴趣：

-   管理员、IT 安全专家和合规性监察官负责确保机密数据在未经授权的情况下不公开

-   负责远程或分支办公室中的计算机安全的管理员

-   负责运行 Windows 的客户端计算机的管理员

**注意** 在本 MBAM 文档中不详细介绍 BitLocker。 有关详细信息，请参阅[BitLocker 驱动器加密概述](https://go.microsoft.com/fwlink/p/?LinkId=225013)。

 

## <a href="" id="what-s-new-in-mbam-2-5"></a>MBAM 2.5 中的新增功能


本部分介绍 MBAM 2.5 中的新增功能。

### Microsoft SQL Server 2014 支持

MBAM 还将添加对 Microsoft SQL Server 2014 的支持，以及早期版本的 MBAM 中支持的相同软件。

### <a href="" id="-------------mbam-group-policy-templates-downloaded-separately"></a> MBAM 单独下载的组策略模板

MBAM 组策略模板必须从 MBAM 安装中单独下载。 在早期版本的 MBAM 中，MBAM 安装程序包括一个 MBAM 策略模板，该模板包含用于定义 BitLocker 驱动器加密 MBAM 实现设置的所需的特定 MBAM 组策略对象（Gpo）。 这些 Gpo 已从 MBAM 安装程序中删除。 现在，你可以在开始 MBAM 客户端安装之前，从[如何获取受 MDOP 组策略（admx）的模板](https://go.microsoft.com/fwlink/p/?LinkId=393941)并将其复制到服务器或工作站。 你可以将组策略模板复制到运行受支持的 Windows Server 或 Windows 操作系统版本的任何服务器或工作站。

**重要提示** 请勿更改**BitLocker 驱动器加密**节点中的组策略设置，否则 MBAM 将无法正常工作。 在**MDOP MBAM （BitLocker Management）** 节点中配置组策略设置时，MBAM 会自动为你配置 BitLocker 驱动器加密设置。

 

需要复制到服务器或工作站的模板文件如下所示：

-   BitLockerManagement adml

-   BitLockerManagement

-   BitLockerUserManagement adml

-   BitLockerUserManagement

将模板文件复制到最适合你的需求的位置。 对于必须复制到特定于语言的文件夹的语言特定文件，需要使用组策略管理控制台查看文件。

- 若要在服务器或工作站本地安装模板文件，请将文件复制到以下位置之一。

  <table>
  <colgroup>
  <col width="50%" />
  <col width="50%" />
  </colgroup>
  <thead>
  <tr class="header">
  <th align="left">文件类型</th>
  <th align="left">文件位置</th>
  </tr>
  </thead>
  <tbody>
  <tr class="odd">
  <td align="left"><p>非特定语言（admx）</p></td>
  <td align="left"><p><em>% systemroot% </em> \policyDefinitions</p></td>
  </tr>
  <tr class="even">
  <td align="left"><p>特定语言（adml）</p></td>
  <td align="left"><p><em>% systemroot% </em> \policyDefinitions [ <em> MUIculture </em> ] （例如，美国英语语言特定的文件将存储在 <em> % systemroot% &lt; /em &gt; policyDefinitions\en-us）中</p></td>
  </tr>
  </tbody>
  </table>

     

- 若要使模板对域中的所有组策略管理员可用，请将文件复制到域控制器上的以下位置之一。

  <table>
  <colgroup>
  <col width="50%" />
  <col width="50%" />
  </colgroup>
  <thead>
  <tr class="header">
  <th align="left">文件类型</th>
  <th align="left">域控制器文件位置</th>
  </tr>
  </thead>
  <tbody>
  <tr class="odd">
  <td align="left"><p>非特定语言（admx）</p></td>
  <td align="left"><p><em>% systemroot% </em> sysvol\domain\policies\PolicyDefinitions</p></td>
  </tr>
  <tr class="even">
  <td align="left"><p>特定语言（adml）</p></td>
  <td align="left"><p><em>% systemroot% </em> \sysvol\domain\policies\PolicyDefinitions [ <em> MUIculture </em> ] （例如，美国英语语言特定的文件将存储在 <em> % systemroot% </em> \sysvol\domain\policies\PolicyDefinitions\en-us）中</p></td>
  </tr>
  </tbody>
  </table>

     

有关模板文件的详细信息，请参阅[管理组策略 ADMX 文件分步指南](https://go.microsoft.com/fwlink/?LinkId=392818)。

### 对操作系统和固定数据驱动器实施加密策略的能力

MBAM 2.5 使你能够在你的组织中对计算机的操作系统和固定数据驱动器强制执行加密策略，并限制最终用户可以请求达到符合 MBAM 加密策略要求的延迟的天数。

为使你能够配置加密策略强制，已为操作系统驱动器和固定数据驱动器添加了新的组策略设置，称为加密策略强制设置。 下表中介绍了此策略。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">组策略设置</th>
<th align="left">描述</th>
<th align="left">用于配置此设置的组策略节点</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>加密策略强制设置（操作系统驱动器）</p></td>
<td align="left"><p>对于此设置，使用选项 <strong> 配置操作系统驱动器配置宽限期的不符合的宽限期间天数 </strong> 。</p>
<p>宽限期指定最终用户在第一次检测到驱动器为不符合的情况后，可为其操作系统驱动器推迟遵守 MBAM 策略的天数。</p>
<p>在配置的宽限期到期后，用户无法推迟所需操作或向其请求豁免。</p>
<p>如果需要用户交互（例如，如果你使用的是受信任的平台模块（TPM） + PIN 或使用密码保护程序），则会显示一个对话框，并且用户在提供所需的信息之前无法关闭它。 如果保护程序仅 TPM，则在后台立即开始加密，无需用户输入。</p>
<p>用户无法通过 BitLocker 加密向导请求豁免。 他们必须联系技术支持人员或使用其组织为豁免请求所使用的任何流程。</p></td>
<td align="left"><p>计算机配置 &gt; 策略 &gt; 管理模板 &gt; WINDOWS 组件 &gt; MDOP MBAM （BitLocker 管理） &gt; 操作系统驱动器</p></td>
</tr>
<tr class="even">
<td align="left"><p>加密策略强制设置（固定数据驱动器）</p></td>
<td align="left"><p>对于此设置，请使用选项 <strong> 配置固定驱动器的不符合的宽限期间天数 </strong> 以配置宽限期。</p>
<p>宽限期指定在第一次检测到驱动器为不兼容后，最终用户可以为其固定驱动器推迟遵守 MBAM 策略的天数。</p>
<p>当固定驱动器被确定为不相容时，宽限期开始。 如果您使用的是自动解锁，则在操作系统驱动器符合要求之前，不会强制执行该策略。 但是，如果未使用自动解锁，则可以在操作系统驱动器完全加密之前开始对固定数据驱动器加密。</p>
<p>在配置的宽限期到期后，用户无法推迟所需操作或向其请求豁免。 如果需要用户交互，则会出现一个对话框，用户在提供所需的信息之前无法将其关闭。</p></td>
<td align="left"><p>计算机配置 &gt; 策略 &gt; 管理模板 &gt; WINDOWS 组件 &gt; MDOP MBAM （BitLocker Management）已 &gt; 修复的驱动器</p></td>
</tr>
</tbody>
</table>

 

### 能够在 BitLocker 驱动器加密向导中提供 URL 以指向你的安全策略

新的组策略设置，**提供 "安全策略" 链接的 url**，使你能够将呈现给最终用户的 url 配置为名为 "**公司安全策略**" 的链接。 当 MBAM 提示用户加密卷时，将出现此链接。

如果启用此策略设置，则可以配置 "**公司安全策略**" 链接的 URL。 如果禁用或未配置此策略设置，则不会向用户显示**公司安全策略**链接。

新组策略设置位于以下 GPO 节点中：**计算机配置** &gt; **策略** &gt; **管理模板** &gt; **Windows 组件** &gt; **MDOP MBAM （BitLocker Management） &gt; 客户端管理**。

### 支持 FIPS 兼容的恢复密钥

MBAM 2.5 支持运行 Windows 8.1 操作系统的设备上的符合联邦信息处理标准（FIPS）的 BitLocker 恢复密钥。 在早期版本的 Windows 中，恢复密钥不兼容 FIPS。 此增强功能改进了需要 FIPS 合规的组织中的驱动器恢复过程，因为它使最终用户能够使用自助服务门户或管理和监视网站（帮助桌面）在忘记其 PIN 或密码或将其从计算机中锁定的情况下恢复其驱动器。 新的 FIPS 合规性功能不会扩展到密码保护器。

若要在你的组织中启用 FIPS 合规性，必须配置联邦信息处理标准（FIPS）组策略设置。 有关配置说明，请参阅[BitLocker 组策略设置](https://go.microsoft.com/fwlink/?LinkId=393560)。

对于运行 Windows8 或 Windows7 操作系统但未[安装 BitLocker 修补程序](https://support.microsoft.com/kb/3015477)的客户端计算机，IT 管理员将继续使用 FIPS 兼容的环境中的数据恢复代理（DRA）保护程序。 有关 DRA 的信息，请参阅将[数据恢复代理与 BitLocker 配合使用](https://go.microsoft.com/fwlink/?LinkId=393557)。

请参阅[Bitlocker 管理和监视2.5 的修补程序包 2](https://support.microsoft.com/kb/3015477) ，下载并安装适用于 windows 7 和 windows 8 计算机的 bitlocker 修补程序。

### 支持高可用性部署

除了标准的两服务器和配置管理器集成拓扑之外，MBAM 还支持下列高可用性方案：

-   SQL Server AlwaysOn 可用性组

-   SQL Server 群集

-   网络负载平衡（NLB）

-   SQL Server 镜像

-   卷影复制服务（VSS）备份

有关这些功能的详细信息，请参阅[规划 MBAM 2.5 高可用性](planning-for-mbam-25-high-availability.md)。

### <a href="" id="management-of-roles-for-administration-and-monitoring-website-changed-"></a>管理和监视网站的角色管理已更改

在 MBAM 2.5 中，必须在 Active Directory 域服务（添加）中创建安全组，以管理提供对管理和监视网站的访问权限的角色。 角色使特定安全组中的用户可以在网站中执行不同的任务，例如查看报表或帮助最终用户恢复加密的驱动器。 在早期版本的 MBAM 中，角色是使用本地组进行管理的。

在 MBAM 2.5 中，术语 "roles" 替换了早期版本的 MBAM 中使用的术语 "管理员角色"。 此外，在 MBAM 2.5 中，"MBAM 系统管理员" 角色已被删除。

下表列出了必须在 AD DS 中创建的安全组。 你可以为安全组使用任何名称。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">角色</th>
<th align="left">此角色在 "管理和监视" 网站上的访问权限</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>MBAM 帮助台用户</p></td>
<td align="left"><p>提供对 MBAM 管理和监视网站的 "管理 TPM 和驱动器恢复" 区域的访问权限。 有权访问这些区域的用户在使用任一区域时都必须填写所有字段。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MBAM 报表用户</p></td>
<td align="left"><p>提供对 "管理和监视" 网站中的报表的访问。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MBAM 高级帮助台用户</p></td>
<td align="left"><p>提供对管理和监控网站中的所有区域的访问权限。 在帮助最终用户恢复其驱动器时，此组中的用户只需输入恢复密钥，而不是最终用户的域和用户名。 如果用户是 MBAM "支持人员" 组和 "MBAM 高级帮助台用户" 组的成员，则 MBAM "高级帮助台用户" 组权限将替代 "MBAM 帮助台用户" 组权限。</p></td>
</tr>
</tbody>
</table>

 

在添加安全组后，将用户和/或组分配给相应的安全组，以启用对管理和监视网站的相应级别的访问权限。 若要使具有每个角色的人员能够访问管理和监视网站，你还必须在配置管理和监视网站时指定每个安全组。

### 用于配置 MBAM Server 功能的 Windows PowerShell cmdlet

MBAM 2.5 的 Windows PowerShell cmdlet 使你能够配置和管理 MBAM 服务器功能。 每个功能都有一个对应的 Windows PowerShell cmdlet，可用于启用或禁用功能，或获取有关该功能的信息。

有关使用 Windows PowerShell 的先决条件和先决条件，请参阅[使用 Windows Powershell 配置 MBAM 2.5 服务器功能](configuring-mbam-25-server-features-by-using-windows-powershell.md)。

**在安装 MBAM 服务器软件后加载适用于 Windows PowerShell cmdlet 的 MBAM 2.5 帮助**

1.  打开 Windows PowerShell 或 Windows PowerShell 集成脚本环境（ISE）。

2.  类型**更新-帮助-MBAM**。

适用于 MBAM 的 Windows PowerShell 帮助有以下格式：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Windows PowerShell 帮助格式</th>
<th align="left">详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>在 Windows PowerShell 命令提示符处，键入 <strong> get-help </strong> &lt; <em> cmdlet</em>&gt;</p></td>
<td align="left"><p>若要上载最新的 Windows PowerShell cmdlet，请按照上一节中关于如何加载 MBAM 的 Windows PowerShell 帮助中的说明进行操作。</p></td>
</tr>
<tr class="even">
<td align="left"><p>在 TechNet 上作为网页</p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393498" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393498">https://go.microsoft.com/fwlink/?LinkId=393498</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>在下载中心中作为单词表文件</p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393497" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393497">https://go.microsoft.com/fwlink/?LinkId=393497</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>在下载中心中作为 .pdf 文件</p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393499" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393499">https://go.microsoft.com/fwlink/?LinkId=393499</a></p></td>
</tr>
</tbody>
</table>

 

### 支持仅限 ASCII 的和增强的 Pin，以及阻止顺序和重复字符的功能

**允许启用 "启动" 组策略设置的增强引脚**

组策略设置，**允许使用增强的 pin 启动**，你可以配置是否将增强的启动 Pin 用于 BitLocker。 增强的启动 Pin 允许用户输入全键盘上的任何键，包括大写和小写字母、符号、数字和空格。 如果启用此策略设置，则设置的所有新 BitLocker 启动 Pin 将为增强引脚。 如果禁用或未配置此策略设置，则无法使用增强的 Pin 码。

并非所有计算机都支持预启动执行环境（PXE）中的增强型 Pin 输入。 在为你的组织启用此组策略设置之前，请在 BitLocker 安装过程中运行系统检查，以确保计算机的 BIOS 支持在 PXE 中使用完整的键盘。 有关详细信息，请参阅[规划 MBAM 2.5 组策略要求](planning-for-mbam-25-group-policy-requirements.md)。

**"要求仅限 ASCII 的 Pin" 复选框**

"**允许启动组的增强引脚**" 策略设置还包含 "**需要 ASCII 专用 pin** " 复选框。 如果组织中的计算机不支持在 PXE 中使用完整键盘，则可以启用 "允许启动组的**增强引脚**" 策略设置，然后选中 "**需要 ASCII 专用引脚**" 复选框以要求增强引脚仅使用可打印的 ascii 字符。

**强制使用非顺序和非重复字符**

MBAM 2.5 阻止最终用户创建由重复号码（如1111）或序列号（如1234）组成的引脚。 如果最终用户尝试输入包含三个或更多重复或连续数字的密码，则 Bitlocker 驱动器加密向导将显示一条错误消息，并防止用户输入包含禁止使用的字符的 PIN 码。

### 将 DRA 证书添加到 BitLocker 计算机合规性报告

已在 Configuration Manager 的 BitLocker 计算机合规性报告中添加了新的保护程序类型（数据恢复代理（DRA）证书）。 此保护器类型适用于操作系统驱动器，并且显示在 "**保护类型**" 列中的 "**计算机卷**" 部分。

### 支持多林支持部署

MBAM 2.5 支持以下类型的多林部署：

-   具有单个域的单林

-   具有单个树和多个域的单林

-   具有多个树和不连续命名空间的单林

-   中央林拓扑中的多个林

-   资源林拓扑中的多个林

不支持林迁移（从单一到多、多到单、资源到整个林，等等），或者升级或降级。

在多林部署中部署 MBAM 的先决条件包括：

-   林必须在支持的 Windows Server 版本上运行。

-   需要双向或单向信任。 单向信任要求服务器的域信任客户端的域。 换句话说，服务器的域指向客户的域。

### MBAM 客户端对加密硬驱的支持

MBAM 支持在满足 Opal 的 TCG 规范要求和 IEEE 1667 标准的加密硬盘上支持 BitLocker。 在这些设备上启用 BitLocker 时，它将在已加密的驱动器上生成密钥并执行管理功能。 有关详细信息，请参阅[加密的硬驱](https://technet.microsoft.com/library/hh831627.aspx)。

## 如何获取 MDOP 技术


MBAM 是 Microsoft 桌面优化包（MDOP）的一部分。 MDOP 是 Microsoft 软件保障计划的一部分。 有关 Microsoft 软件保证计划以及如何获取 MDOP 的详细信息，请参阅[如何获取 mdop？](https://go.microsoft.com/fwlink/?LinkId=322049)。

## <a href="" id="---------mbam-2-5-release-notes"></a> MBAM 2.5 发行说明


有关此文档中未包括的详细信息和最新新闻，请参阅[MBAM 2.5 的发行说明](release-notes-for-mbam-25.md)。

## 已获得 MBAM 的建议？
- [在此处](https://support.microsoft.com/help/4021566/windows-10-send-feedback-to-microsoft-with-feedback-hub)发送反馈。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。

## 相关主题


[Microsoft BitLocker 管理和监控 2.5](index.md)

[MBAM 2.5 入门](getting-started-with-mbam-25.md)

 

 





