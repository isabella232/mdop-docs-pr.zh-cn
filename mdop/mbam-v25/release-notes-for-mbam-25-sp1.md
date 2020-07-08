---
title: MBAM 2.5 SP1 的发行说明
description: MBAM 2.5 SP1 的发行说明
author: dansimp
ms.assetid: 3ac424c8-c490-4d62-aba4-1b462c02e962
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 09/06/2017
ms.openlocfilehash: 837892897aeca341433de54aca1228c0faeee124
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803678"
---
# MBAM 2.5 SP1 的发行说明


若要搜索这些发行说明，请按 Ctrl + F。

在安装 Microsoft BitLocker 管理和监视（MBAM） 2.5 SP1 之前，请仔细阅读这些发行说明。 这些发行说明包含成功安装 MBAM 所需的信息，并且可以包含产品文档中不可用的信息。 如果这些发行说明与其他 MBAM 2.5 SP1 文档不同，请考虑最新的更改为权威。 这些发行说明取代了本产品附带的内容。

## <a href="" id="---------mbam-2-5-sp1-known-issues"></a> MBAM 2.5 SP1 已知问题


本部分包含适用于 MBAM 2.5 SP1 的发行说明。

### <a href="" id="powershell-read-ad--cmdlets-do-not-provide-feedback-if-user-does-not-have-sufficient-rights"></a>如果用户没有足够的权限，PowerShell Read-AD \ * cmdlet 不提供反馈

如果尝试对 MBAM 服务器使用 PowerShell Read-AD \ * cmdlet 的用户没有读取 Active Directory 恢复信息或读取 TPM 信息的用户权限，则 cmdlet 将不会向用户提供任何错误或警告。

**解决方法：** 如果你拥有所需的用户权限，请仅使用 PowerShell Read AD * cmdlet。

### MBAM Active Directory （AD）迁移 cmdlet 不检索卷恢复信息

MBAM Active Directory （AD）迁移 cmdlet 无法检索组织单位（Ou）中的计算机的卷恢复信息，前提是 "正斜杠字符（/）" 是组织单位名称的一部分。 当遇到此错误时，重复的广告拉将失败，并出现管道终止错误。

**技术详细信息：** 运行命令时，您将看到此错误：

``` syntax
Read-ADRecoveryInformation : Unknown error (0x80005000)
At line:1 char:1
+ Read-ADRecoveryInformation -Server "…" -SearchBase " ...
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [Read-ADRecoveryInformation], COMException
    + FullyQualifiedErrorId : System.Runtime.InteropServices.COMException,Microsoft.Mbam.Server.Commands.ADPullCommands.ReadADRecoveryInformationCommand
```

此外，异常堆栈跟踪 `Error[0].Exception.StackTrace` 将如下所示：

``` syntax
   at System.DirectoryServices.DirectoryEntry.Bind(Boolean throwIfFail)
   at System.DirectoryServices.DirectoryEntry.Bind()
   at System.DirectoryServices.DirectoryEntry.get_AdsObject()
   at System.DirectoryServices.PropertyValueCollection.PopulateList()
   at System.DirectoryServices.PropertyValueCollection..ctor(DirectoryEntry entry, String propertyName)
   at System.DirectoryServices.PropertyCollection.get_Item(String propertyName)
   at Microsoft.Mbam.Server.Commands.ADPullCommands.ReadCore.VerifySettingsConnectivity()
   at Microsoft.Mbam.Server.Commands.ADPullCommands.ReadCore.ExecuteRead()
   at Microsoft.Mbam.Server.Commands.ADPullCommands.ReadADInformationBase.ProcessRecord()
   at System.Management.Automation.CommandProcessor.ProcessRecord()
```

**解决方法：** 若要解决此问题，请执行以下任务之一：

-   重命名 OU 以删除正斜杠字符，然后运行脚本。

-   若要从备份过程中排除任何有问题的 OU，请查找名称不包含正斜杠字符的 Ou 的列表。 对这些 Ou 运行脚本，一次一个 OU。

### <a href="" id="-------------mbam-fails-to-encrypt-a-volume-and-reports-an-error-if-you-set-a-tpm---pin-protector-on-a-tablet-device"></a> 如果在平板电脑上设置 TPM + 引脚保护器，MBAM 无法加密卷并报告错误

如果最终用户尝试在平板电脑上设置 TPM + PIN 保护程序，MBAM 无法加密，并且会报告错误。 出现此问题的原因是平板电脑设备没有预引导环境键盘。

**解决方法：** 启用 "**启用 BitLocker 身份验证，需要在平板电脑组上预启动键盘输入"** 策略设置。 此设置是 BitLocker 组策略设置，在 MBAM 组策略模板中不可用。

### 所有服务帐户都需要用户主体名称

必须为 MBAM 中的所有服务帐户设置用户主体名称（UPN）。 如果无法为帐户创建 UPN，则在配置过程中会出现一条错误消息，指示在 Active Directory 中找不到该用户或组。

**解决方法：** 将 UPN 添加到服务帐户。

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

### 密码强度在 BitLocker 计算机合规性报告上显示不正确

如果未在 "**选择驱动器加密方法" 和 "密码强度**" 组策略对象中设置特定的密码强度，则配置管理器集成拓扑中的 BitLocker 计算机合规性报告始终显示密码强度的 "unknown"，即使密码强度使用默认的128位加密也是如此。 如果在组策略对象中设置了特定的密码强度，则报表将显示正确的密码强度。

**解决方法：** 在 "**选择驱动器加密方法" 和 "密码强度**" 组策略对象中始终设置特定的密码强度。

### 合规性状态按驱动器类型分布在更新配置项目后显示旧数据

在 SystemCenter2012 ConfigurationManager 中更新 MBAM 配置项目后，"BitLocker 企业合规性" 仪表板上的 "驱动器类型" 分布图中的合规性状态分布将显示基于来自旧版本的配置项目的信息的数据。

**解决方法：** 尚. 不支持修改 MBAM 配置项目，并且报表可能不会按预期显示。

### 增强的安全配置可能会导致报表不能正确显示错误消息

如果 Internet Explorer 增强的安全配置（ESC）处于打开状态，则当你尝试在 MBAM 服务器上查看报告时可能会显示 "拒绝访问" 错误消息。 默认情况下，按 ESC 可保护服务器，方法是降低服务器对通过 web 内容和应用程序脚本可能发生的潜在攻击的影响。

**解决方法：** 如果尝试在 MBAM 服务器上查看报告时出现 "拒绝访问" 错误消息，则可以在映像中设置组策略对象或手动更改默认设置，以禁用增强的安全配置。 您也可以从另一台计算机上查看未启用 ESC 的报告。

### 支持 Bitlocker XTS-AES 加密算法
Bitlocker 添加了对 Windows 10 版本1511中的 XTS 加密算法的支持。 通过 HF02、MBAM 添加了适用于此 Bitlocker 选项和 HF04 中的客户端支持，添加了服务器端支持。 但是，有一个已知的限制：

* 客户必须对同一台计算机上的操作系统和数据量使用相同的加密强度。
如果使用不同的加密强度，MBAM 会将计算机报告为**不合规**。

### 自助服务门户会自动在键 ID 条目上添加 "-"
自 HF02 到 MBAM，Portal 会自动在键 ID 条目上添加 "-"。  
**注意：** 必须重新配置服务器才能使 Javascript 生效。

### MBAM 2.5 Sp1 报告无法正常工作/呈现
当 SSRS 托管在 SQL Server 2016 edition 上时，"报表" 页面不会正确呈现。 
例如，浏览到 "帮助台"-单击 "报表"-（突出显示部分在其上有 "x"）使用 Fiddler 尽情这一功能-如果单击 "报表"，它看起来就像是使用 HTML 4.0 呈现格式调用 SSRS 页面。

**解决方法：** 查看网站。主代码并注意 X-UA 模式是 IE8。 作为 IE8 在生命周期结束，客户使用 IE11。 将设置更新为以下代码。 这使网站能够利用 IE11 呈现技术

    <meta http-equiv="X-UA-Compatible" content="IE=Edge" />

原始设置为： 

    <meta http-equiv="X-UA-Compatible" content="IE=8" />


这是与其他浏览器（如 Chrome、Firefox 等）看不到此问题的原因。



## 相关主题


[关于 MBAM 2.5](about-mbam-25.md)

 

## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





