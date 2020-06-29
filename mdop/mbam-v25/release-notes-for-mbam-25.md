---
title: MBAM 2.5 的发行说明
description: MBAM 2.5 的发行说明
author: dansimp
ms.assetid: fcaf03e6-5e39-4771-af3c-a3cd468f3961
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 4bcc17d6295b14a7f3276146d5630b869b94b7f0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803677"
---
# MBAM 2.5 的发行说明


若要搜索这些发行说明，请按 Ctrl + F。

安装 Microsoft BitLocker 管理和监视（MBAM）2.5 之前，请仔细阅读这些发行说明。 这些发行说明包含成功安装 MBAM 所需的信息，并且可以包含产品文档中不可用的信息。 如果这些发行说明与其他 MBAM 2.5 文档不同，请考虑最新更改为权威。 这些发行说明取代了本产品附带的内容。

## <a href="" id="---------mbam-2-5-known-issues"></a> MBAM 2.5 已知问题


本部分包含 MBAM 2.5 的发行说明。

### 无意间以管理员身份运行 Web 浏览器

MBAM 服务器配置工具中的帮助链接可导致浏览器窗口以管理员权限打开。

**解决方法：** 在导航到其他网站之前，启用 Internet Explorer 增强的安全配置（IESC）或关闭您的 web 浏览器。

**注意** 这在 MBAM 2.5 SP1 中已修复。

 

### <a href="" id="-------------mbam-reports-as-noncompliant-a-client-encrypted-with-aes-256-bit-encryption-keys-and-diffuser"></a> 将报表 MBAM 为不符合使用 AES 256 位加密密钥和扩散器加密的客户端

如果计算机安装了 MBAM 2.5 客户端，并且它是通过将 AES 256 位与扩散器密码强度一起加密的，则 MBAM 客户端在 MBAM 合规性报告中报告为不相容。

**解决方法：** 在[KB2975636](https://go.microsoft.com/fwlink/?LinkId=511972)处安装修补程序。

### <a href="" id="-------------mbam-fails-to-encrypt-a-volume-and-reports-an-error-if-you-set-a-tpm---pin-protector-on-a-tablet-device"></a> 如果在平板电脑上设置 TPM + 引脚保护器，MBAM 无法加密卷并报告错误

如果最终用户尝试在平板电脑上设置 TPM + PIN 保护程序，MBAM 无法加密，并且会报告错误。 出现此问题的原因是平板电脑设备没有预引导环境键盘。

**解决方法：** 启用 "**启用 BitLocker 身份验证，需要在平板电脑组上预启动键盘输入"** 策略设置。 此设置是 BitLocker 组策略设置，在 MBAM 组策略模板中不可用。

### 所有服务帐户都需要用户主体名称

必须为 MBAM 中的所有服务帐户设置用户主体名称（UPN）。 如果无法为帐户创建 UPN，则在配置过程中会出现一条错误消息，指示在 Active Directory 中找不到该用户或组。

**解决方法：** 将 UPN 添加到服务帐户。

### 如果客户端计算机无法访问 Microsoft Ajax 内容传递网络，则自助服务门户需要其他配置

如果你的客户端计算机无法访问 Microsoft Ajax 内容传递网络（CDN），从而为自助门户提供对某些 JavaScript 文件所需的访问权限，则必须将自助服务门户配置为从易于访问的源引用 JavaScript 文件。 如果客户端计算机无法访问 CDN 时未配置自助服务门户，则仅显示公司名称和登录帐户。 不会显示任何错误消息。

**解决方法：** 安装 MBAM 2.5 SP1。 或按照以下说明配置自助服务门户：[如何在客户端计算机无法访问 Microsoft 内容传递网络时配置自助服务门户](how-to-configure-the-self-service-portal-when-client-computers-cannot-access-the-microsoft-content-delivery-network.md)。

### 在将 IIS 升级到 .NET Framework 4.5 后，自助服务门户和管理和监视网站不会打开

将 Internet 信息服务（IIS）升级到 Microsoft .NET Framework 4.5 时，无法打开自助服务门户和管理和监视网站。

**解决方法：** 在[安装 .Net Framework 4.0 后，请参阅文章错误消息： "无法加载类型 ' system.servicemodel. HttpModule '](https://go.microsoft.com/fwlink/?LinkId=393568)。

### 管理和监视网站在未配置报表时显示 "找不到报表" 错误消息

如果您配置了管理和监控网站，然后尝试查看报表但没有配置报表功能，则会出现一条错误消息，指示无法找到报表。

**解决方法：** 配置 web 应用程序之前，请先配置报表功能。

### 如果未在 SSRS 中配置 SSL，管理和监视网站中的报表将显示警告

如果 SQL Server Reporting Services （SSRS）未配置为使用安全套接字层（SSL），则当你配置 MBAM 服务器时，"报告" 功能的 URL 将设置为 HTTP 而不是 HTTPS。 如果随后打开 "管理和监视" 网站并选择报表，则会显示以下错误消息： "仅显示安全内容"。

**解决方法：** 若要显示报表，请单击 "**显示所有内容**"。 若要解决此问题，请转到安装了 SQL Server Reporting Services 的 MBAM 计算机，运行**Reporting Services 配置管理器**，然后单击 " **Web 服务 URL**"。 为服务器选择相应的 SSL 证书，输入相应的 SSL 端口（默认端口为443），然后单击 "**应用**"。

### 单击 "BitLocker 合规性摘要" 报告中的 "后退" 可能会引发错误

如果向下钻取到 BitLocker 合规性摘要报告，然后单击 SSRS 报表中的**Back**链接，可能会引发错误。

**解决方法：** 尚.

### "仅使用空间" 加密不会正常工作

如果在安装 MBAM 客户端后首次加密计算机，并且已将组策略设置配置为仅实现已使用的空间加密，则 MBAM 会错误地加密整个磁盘，而不是仅加密磁盘的已用空间。 如果已使用仅在安装 MBAM 客户端时已使用的空间对计算机进行了加密，并且配置了相同的组策略设置，MBAM 将报告该驱动器已正确加密，并且不会尝试重新加密该驱动器。

**解决方法：** 尚.

### 密码强度在 BitLocker 计算机合规性报告上显示不正确

如果未在 "**选择驱动器加密方法" 和 "密码强度**" 组策略对象中设置特定的密码强度，则配置管理器集成拓扑中的 BitLocker 计算机合规性报告始终显示密码强度的 "unknown"，即使密码强度使用默认的128位加密也是如此。 如果在组策略对象中设置了特定的密码强度，则报表将显示正确的密码强度。

**解决方法：** 在 "**选择驱动器加密方法" 和 "密码强度**" 组策略对象中始终设置特定的密码强度。

### 合规性状态按驱动器类型分布在更新配置项目后显示旧数据

在 SystemCenter2012 ConfigurationManager 中更新 MBAM 配置项目后，"BitLocker 企业合规性" 仪表板上的 "驱动器类型" 分布图中的合规性状态分布将显示基于来自旧版本的配置项目的信息的数据。

**解决方法：** 尚. 不支持修改 MBAM 配置项目，并且报表可能不会按预期显示。

### 增强的安全配置可能会导致报表不能正确显示错误消息

如果 Internet Explorer 增强的安全配置（ESC）处于打开状态，则当你尝试在 MBAM 服务器上查看报告时可能会显示 "拒绝访问" 错误消息。 默认情况下，按 ESC 可保护服务器，方法是降低服务器对通过 web 内容和应用程序脚本可能发生的潜在攻击的影响。

**解决方法：** 如果尝试在 MBAM 服务器上查看报告时出现 "拒绝访问" 错误消息，则可以在映像中设置组策略对象或手动更改默认设置，以禁用增强的安全配置。 您也可以从另一台计算机上查看未启用 ESC 的报告。

## <a href="" id="hotfixes-and-knowledge-base-articles-for-mbam-2-5-"></a>MBAM 2.5 的修补程序和知识文库文章


下表列出了 MBAM 2.5 的修补程序和知识库文章。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong>知识库文章</strong></th>
<th align="left">Title</th>
<th align="left"><strong>链接</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>2975636</p></td>
<td align="left"><p>Microsoft BitLocker 管理和监视2.5 的修补程序包1</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2975636/EN-US" data-raw-source="[support.microsoft.com/kb/2975636/EN-US](https://support.microsoft.com/kb/2975636/EN-US)">support.microsoft.com/kb/2975636/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>3015477</p></td>
<td align="left"><p>用于 BitLocker 管理和监视2.5 的修补程序包2</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/3015477" data-raw-source="[support.microsoft.com/kb/3015477](https://support.microsoft.com/kb/3015477)">support.microsoft.com/kb/3015477</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>3011022</p></td>
<td align="left"><p>如果 SSRS 实例的名称包含下划线，MBAM 2.5 安装或 Configuration Manager 报告将失败</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/3011022/EN-US" data-raw-source="[support.microsoft.com/kb/3011022/EN-US](https://support.microsoft.com/kb/3011022/EN-US)">support.microsoft.com/kb/3011022/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2756402</p></td>
<td align="left"><p>MBAM 客户端将失败，并出现事件描述中的事件 ID 4 和错误代码0x8004100E</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2756402/EN-US" data-raw-source="[support.microsoft.com/kb/2756402/EN-US](https://support.microsoft.com/kb/2756402/EN-US)">support.microsoft.com/kb/2756402/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2639518</p></td>
<td align="left"><p>在 MBAM 中打开企业或计算机合规性报告时出错</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2639518/EN-US" data-raw-source="[support.microsoft.com/kb/2639518/EN-US](https://support.microsoft.com/kb/2639518/EN-US)">support.microsoft.com/kb/2639518/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2870842</p></td>
<td align="left"><p>MBAM 2.0 在 SQL Server 2008 的配置管理器集成方案期间安装失败</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2870842/EN-US" data-raw-source="[support.microsoft.com/kb/2870842/EN-US](https://support.microsoft.com/kb/2870842/EN-US)">support.microsoft.com/kb/2870842/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2975472</p></td>
<td align="left"><p>许多 MBAM 客户端连接到 MBAM 恢复数据库时的 SQL 死锁</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2975472/EN-US" data-raw-source="[support.microsoft.com/kb/2975472/EN-US](https://support.microsoft.com/kb/2975472/EN-US)">support.microsoft.com/kb/2975472/EN-US</a></p></td>
</tr>
</tbody>
</table>

 


## 相关主题


[关于 MBAM 2.5](about-mbam-25.md)

 

## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





