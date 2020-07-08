---
title: MBAM 2.5 安全注意事项
description: MBAM 2.5 安全注意事项
author: dansimp
ms.assetid: f6613c63-b32b-45fb-a6e8-673d6dae7d16
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 04/23/2017
ms.openlocfilehash: 86a756ab6f983fa1f22de6835b5993e1215d1dbe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804048"
---
# MBAM 2.5 安全注意事项


本主题包含有关如何保护 Microsoft BitLocker 管理和监视（MBAM）的以下信息：

-   [配置 MBAM 以托管 TPM 和存储 OwnerAuth 密码](#bkmk-tpm)

-   [将 MBAM 配置为在锁定后自动解锁 TPM](#bkmk-autounlock)

-   [连接到 SQL Server 的安全连接](#bkmk-secure-databases)

-   [创建帐户和组](#bkmk-accts-groups)

-   [使用 MBAM 日志文件](#bkmk-logfiles)

-   [查看 MBAM 数据库 TDE 注意事项](#bkmk-tde)

-   [了解常规安全注意事项](#bkmk-general-security)

## <a href="" id="bkmk-tpm"></a>配置 MBAM 以托管 TPM 和存储 OwnerAuth 密码

**注意**对于 Windows 10 版本1607或更高版本，只有 Windows 可以获得 TPM 的所有权。 此外，预配 TPM 时，Windows 不会保留 TPM 所有者密码。 有关进一步的详细信息，请参阅[TPM 所有者密码](https://docs.microsoft.com/windows/security/information-protection/tpm/change-the-tpm-owner-password)。

根据其配置，受信任的平台模块（TPM）将在某些情况下锁定自身，例如在输入了太多不正确的密码时，可以在一段时间内保持锁定。 在 TPM 锁定期间，BitLocker 无法访问加密密钥以执行解锁或解密操作，要求用户输入其 BitLocker 恢复密钥才能访问操作系统驱动器。 若要重置 TPM 锁定，必须提供 TPM OwnerAuth 密码。

MBAM 可以在 MBAM 数据库中存储 TPM OwnerAuth 密码（如果它拥有 TPM 或 escrows 该密码）。 当必须从 TPM 锁定恢复时，可以在管理和监视网站上轻松访问 OwnerAuth 密码，这样就不必等到锁定自行解决。

### Windows 8 及更高版本中的 Escrowing TPM OwnerAuth

**注意**对于 Windows 10 版本1607或更高版本，只有 Windows 可以获得 TPM 的所有权。 在 addiiton 中，Windows 将不会在预配 TPM 时保留 TPM 所有者密码。 有关进一步的详细信息，请参阅[TPM 所有者密码](https://docs.microsoft.com/windows/security/information-protection/tpm/change-the-tpm-owner-password)。

在 Windows 8 或更高版本中，只要 OwnerAuth 在本地计算机上可用，MBAM 就不能再拥有 TPM 来存储 OwnerAuth 密码。

若要使 MBAM 能够进行托管，然后存储 TPM OwnerAuth 密码，必须配置这些组策略设置。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">组策略设置</th>
<th align="left">配置</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>将 TPM 备份启用到 Active Directory 域服务</p></td>
<td align="left"><p>已禁用或未配置</p></td>
</tr>
<tr class="even">
<td align="left"><p>配置操作系统可用的 TPM 所有者授权信息级别</p></td>
<td align="left"><p>已委派/无或未配置</p></td>
</tr>
</tbody>
</table>

 

这些组策略设置的位置是 "**计算机配置**" &gt; **管理模板** &gt; **系统** &gt; **受信任的平台模块服务**。

**注意** 在 MBAM 成功 escrows 所有设置后，Windows 将 OwnerAuth 在本地删除。

 

### Windows 7 中的 Escrowing TPM OwnerAuth

在 Windows 7 中，MBAM 必须拥有 TPM 才能在 MBAM 数据库中自动托管 TPM OwnerAuth 信息。 如果 MBAM 不拥有 TPM，则必须使用 MBAM Active Directory （AD）数据导入 cmdlet 将 TPM OwnerAuth 从 Active Directory 复制到 MBAM 数据库中。

### MBAM Active Directory 数据导入 cmdlet

MBAM Active Directory 数据导入 cmdlet 可用于检索存储在 Active Directory 中的恢复密钥包和 OwnerAuth 密码。

MBAM 2.5 SP1 服务器随附有四个 PowerShell cmdlet，这些 cmdlet 通过存储在 Active Directory 中的卷恢复和 TPM 所有者信息预填充 MBAM 数据库。

对于卷恢复密钥和程序包：

-   Read ADRecoveryInformation

-   Write-MbamRecoveryInformation

对于 TPM 所有者信息：

-   Read ADTpmInformation

-   Write-MbamTpmInformation

将用户与计算机相关联：

-   Write-MbamComputerUser

Read 广告 \ * cmdlet 读取 Active Directory 中的信息。 Write Mbam \ * cmdlet 将数据推送到 MBAM 数据库中。 有关这些 cmdlet 的详细信息，请参阅[Microsoft Bitlocker 管理和监视 2.5 Cmdlet 参考](https://technet.microsoft.com/library/dn459018.aspx)，包括语法、参数和示例。

**创建用户到计算机的关联：** MBAM Active Directory 数据导入 cmdlet 从 Active Directory 中收集信息，并将数据插入 MBAM 数据库中。 但是，它们不会将用户与卷相关联。 你可以下载 Add-ComputerUser.ps1 PowerShell 脚本以创建用户到计算机关联，从而使用户可以通过管理和监视网站或通过使用自助服务门户进行恢复来重新访问计算机。 Add-ComputerUser.ps1 脚本从 Active Directory （AD）、AD 中的对象所有者或自定义 CSV 文件中的 "**托管者**" 属性收集数据。 然后，该脚本将发现的用户添加到恢复信息管道对象，该对象必须传递到 MbamRecoveryInformation 以将数据插入到恢复数据库中。

从[Microsoft 下载中心](https://go.microsoft.com/fwlink/?LinkId=613122)下载 Add-ComputerUser.ps1 PowerShell 脚本。

你可以指定**帮助 Add-ComputerUser.ps1**获取有关脚本的帮助，包括如何使用 cmdlet 和脚本的示例。

若要在安装 MBAM 服务器之后创建用户到计算机的关联，请使用 MbamComputerUser PowerShell cmdlet。 与 Add-ComputerUser.ps1 PowerShell 脚本类似，此 cmdlet 允许你指定可使用自助服务门户获取指定计算机的 TPM OwnerAuth 信息或卷恢复密码的用户。

**注意** 当该计算机开始向服务器报告时，MBAM 代理将替代用户到计算机的关联。

 

**先决条件：** 只有当用户以高度特权的用户帐户（如域管理员）身份运行，或以帐户的形式作为帐户在被授予对该信息的读取访问权限的自定义安全组中运行时，"已读广告 \ *" cmdlet 才能检索来自该信息的信息（推荐）。

[BitLocker 驱动器加密操作指南：使用 AD DS 恢复加密的卷](https://technet.microsoft.com/library/cc771778(WS.10).aspx)提供有关创建自定义安全组（或多个组）以及对广告信息的读取访问权限的详细信息。

**MBAM 恢复和硬件 Web 服务写入权限：** Write Mbam \ * cmdlet 接受用于发布恢复或 TPM 信息的 MBAM 恢复和硬件服务的 URL。 通常，只有域计算机服务帐户可以与 MBAM 恢复和硬件服务进行通信。 在 MBAM 2.5 SP1 中，你可以使用名为 DataMigrationAccessGroup 的安全组将 MBAM 恢复和硬件服务配置为允许其成员绕过域计算机服务帐户检查。 Write-Mbam \ * cmdlet 必须作为属于此配置组的用户运行。 （或者，可以使用 Write-Mbam \ * cmdlet 中的– Credential 参数指定已配置组中单个用户的凭据。）

你可以通过以下方式之一将 MBAM 恢复和硬件服务与此安全组的名称进行配置：

-   在 Enable-MbamWebApplication-AgentService Powershell cmdlet 的-DataMigrationAccessGroup 参数中提供安全组（或个人）的名称。

-   通过在 &lt; inetpub &gt; \\Microsoft Bitlocker 管理 Solution\\Recovery 和硬件 Service\\ 文件夹中编辑 web.config 文件，在安装 MBAM 恢复和硬件服务之后配置组。

    ```xml
    <add key="DataMigrationUsersGroupName" value="<groupName>|<empty>" />
    ```

    &lt; &gt; 将用于允许从 Active Directory 进行数据迁移的域和组名（或单个用户）替换了组名。

-   在 IIS 管理器中使用配置编辑器编辑此 appSetting。

在以下示例中，当作为 ADRecoveryInformation 组和数据迁移用户组的成员运行时，该命令将从 contoso.com 域中的工作站组织单位（OU）内的计算机提取卷恢复信息，并使用 mbam.contoso.com 服务器上运行的 MBAM 恢复和硬件服务将这些信息写入 MBAM。

``` syntax
PS C:\> Read-ADRecoveryInformation -Server contoso.com -SearchBase "OU=WORKSTATIONS,DC=CONTOSO,DC=COM" | Write-MbamRecoveryInformation -RecoveryServiceEndPoint "https://mbam.contoso.com/MBAMRecoveryAndHardwareService/CoreService.svc"
```

**Read-广告 \ * cmdlet**接受托管服务器计算机的 Active Directory 的名称或 IP 地址，以查询恢复或 TPM 信息。 我们建议你提供将计算机对象作为 SearchBase 参数的值驻留的广告容器的可分辨名称。 如果计算机存储在多个 Ou 中，则 cmdlet 可以接受针对每个容器运行一次的管道输入。 广告容器的可分辨名称看起来将类似于 OU = 计算机，DC = contoso，DC = com。 执行针对特定容器的搜索可提供以下好处：

-   在查询大型 AD 数据集以查找计算机对象时，降低超时风险。

-   可以忽略包含数据中心服务器或可能不需要备份的其他计算机类的 Ou。

另一个选择是提供带有或不带可选 SearchBase 的-递归标志，以在指定的 SearchBase 或整个域下的所有容器中搜索计算机对象。 使用-递归标志时，还可以使用-MaxPageSize 参数来控制服务查询所需的本地和远程内存量。

这些 cmdlet 将写入类型为 PsObject 的管道对象。 每个 PsObject 实例都包含一个卷恢复密钥或 TPM 所有者字符串以及将其与其关联的计算机名称、时间戳和其他信息发布到 MBAM 数据存储中所需的其他信息。

**Write-Mbam \ * cmdlet**按属性名称从管道中接受恢复信息参数值。 这允许 Write-Mbam \ * cmdlet 接受 Read 广告 \ * cmdlet 的管道输出（例如，Read ADRecoveryInformation-Server contoso.com-递归 |Write-MbamRecoveryInformation-RecoveryServiceEndpoint mbam.contoso.com）。

**Write-Mbam \ * cmdlet**包括可选参数，这些参数提供容错、详细日志记录和 WhatIf 和确认首选项的选项。

**Write Mbam \ * cmdlet**还包括值为**DateTime**对象的可选*Time*参数。 此对象包括可设置为、或的*Kind*属性 `Local` `UTC` `Unspecified` 。 当使用从 Active Directory 中获取的数据填充*时间*参数时，时间将转换为 UTC，并且此*Kind*属性将自动设置为 `UTC` 。 但是，当使用另一个源（如文本文件）填充*时间*参数时，必须将*Kind*属性显式设置为相应值。

**注意** 已读广告 \ * cmdlet 不能发现代表计算机用户的用户帐户。 以下情况需要用户帐户关联：

-   用户使用自助服务门户恢复卷密码/程序包

-   在安装期间未在 MBAM 高级支持人员用户安全组中定义的用户，代表其他用户进行恢复

 

## <a href="" id="bkmk-autounlock"></a>将 MBAM 配置为在锁定后自动解锁 TPM


你可以将 MBAM 2.5 SP1 配置为在锁定时自动解锁 TPM。 如果启用了 TPM 锁定自动重置，MBAM 可以检测到用户已被锁定，然后获取 MBAM 数据库中的 OwnerAuth 密码，以自动解锁用户的 TPM。 仅当使用自助服务门户或管理和监视网站检索该计算机的操作系统恢复密钥时，TPM 锁定自动重置才可用。

**重要提示** 若要启用 TPM 锁定自动重置，必须在服务器端和客户端上的组策略中配置此功能。

 

-   若要在客户端启用 TPM 锁定自动重置，请在 "**计算机配置**" &gt; **管理模板** &gt; **Windows 组件** &gt; **MDOP MBAM** &gt; **客户端管理**中配置组策略设置 "配置 TPM 锁定自动重置"。

-   若要在服务器端启用 TPM 锁定自动重置，可以在安装期间在 MBAM Server 配置向导中选中 "启用 TPM 锁定自动重置"。

    你还可以通过在启用代理服务 web 组件时指定 "-TPM 锁定自动重置" 切换器，在 PowerShell 中启用 TPM 锁定自动重置。

用户输入从自助服务门户或管理和监视网站获取的 BitLocker 恢复密钥后，MBAM 代理将确定 TPM 是否已锁定。如果它已被锁定，它将尝试从 MBAM 数据库检索计算机的 TPM OwnerAuth。 如果 TPM OwnerAuth 已成功检索，它将用于解锁 TPM。 解锁 TPM 将使 TPM 完全正常工作，并且不会强制用户在从 TPM 锁定的后续重启过程中输入恢复密码。

默认情况下，将禁用 TPM 锁定自动重置。

**注意** 仅在运行 TPM 版本1.2 的计算机上支持 TPM 锁定自动重置。 TPM 2.0 提供了内置的锁定自动重置功能。

 

**恢复审核报告**包括与 TPM 锁定自动重置相关的事件。 如果从 MBAM 客户端发出请求以检索 TPM OwnerAuth 密码，则会记录一个事件以指示恢复。 审核条目将包括以下事件：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Entry</th>
<th align="left">值</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>审核请求源</p></td>
<td align="left"><p>代理 TPM 解锁</p></td>
</tr>
<tr class="even">
<td align="left"><p>键类型</p></td>
<td align="left"><p>TPM 密码哈希</p></td>
</tr>
<tr class="odd">
<td align="left"><p>原因描述</p></td>
<td align="left"><p>TPM 重置</p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-secure-databases"></a>连接到 SQL Server 的安全连接


在 MBAM 中，SQL Server 与 SQL Server Reporting Services 以及用于管理和监视网站和自助服务门户的 web 服务进行通信。 我们建议您确保与 SQL Server 的通信安全。 有关详细信息，请参阅[加密到 SQL Server 的连接](https://technet.microsoft.com/library/ms189067.aspx)。

有关保护 MBAM 网站安全的详细信息，请参阅[规划如何保护 MBAM 网站的安全](planning-how-to-secure-the-mbam-websites.md)。

## <a href="" id="bkmk-accts-groups"></a>创建帐户和组


管理用户帐户的最佳做法是创建域全局组并向其添加用户帐户。 有关推荐的帐户和组的说明，请参阅[规划 MBAM 2.5 组和帐户](planning-for-mbam-25-groups-and-accounts.md)。

## <a href="" id="bkmk-logfiles"></a>使用 MBAM 日志文件


本部分介绍 MBAM 服务器和 MBAM 客户端日志文件。

**MBAM Server 安装程序日志文件**

在 MBAM 安装期间， **MBAMServerSetup.exe**文件将在用户的 **% temp%** 文件夹中生成以下日志文件：

-   **Microsoft \ _BitLocker \ _Administration \ _and \ _Monitoring \ \ &lt; 14 号码 &gt; 。日志**

    记录在 MBAM 设置和 MBAM 服务器功能配置期间执行的操作。

-   **Microsoft \ _BitLocker \ _Administration \ _and \ _Monitoring \ _ &lt; 14 \ _numbers &gt;\_0\_MBAMServer.msi**

    记录安装期间执行的其他操作。

**MBAM 服务器配置日志文件**

-   **应用程序和服务日志/Microsoft Windows/MBAM-设置**

    记录使用 Windows Powershell cmdlet 或 MBAM Server 配置向导配置 MBAM 服务器功能时出现的错误。

**MBAM 客户端安装程序日志文件**

-   **MSI &lt; 5 个随机字符 &gt; 。日志**

    记录在 MBAM 客户端安装期间执行的操作。

**MBAM-Web 日志文件**

-   显示来自 web 门户和服务的活动。

## <a href="" id="bkmk-tde"></a>查看 MBAM 数据库 TDE 注意事项


SQL Server 中可用的透明数据加密（TDE）功能是用于承载 MBAM 数据库功能的数据库实例的可选安装。

通过 TDE，你可以执行实时、完整数据库级别的加密。 TDE 是批量加密的最佳选择，可满足法规遵从性或公司数据安全标准。 TDE 适用于文件级别，它类似于两个 Windows 功能：加密文件系统（EFS）和 BitLocker 驱动器加密。 这两种功能还会加密硬盘上的数据。 TDE 不会替换单元级加密、EFS 或 BitLocker。

在数据库上启用 TDE 时，将加密所有备份。 因此，必须特别注意才能确保使用数据库备份对用于保护数据库加密密钥的证书进行备份和维护。 如果此证书（或证书）丢失，则数据将不可读。

备份数据库中的证书。 每个证书备份都应具有两个文件。 这两个文件都应存档。 理想情况下，应将其与数据库备份文件分开备份。 您也可以考虑使用可扩展密钥管理（EKM）功能（请参阅可扩展密钥管理）存储和维护用于 TDE 的密钥。

有关如何为 MBAM 数据库实例启用 TDE 的示例，请参阅[了解透明数据加密（TDE）](https://technet.microsoft.com/library/bb934049.aspx)。

## <a href="" id="bkmk-general-security"></a>了解常规安全注意事项


**了解安全风险。** 使用 Microsoft BitLocker 管理和监视时，最严重的风险是，未经授权的用户可能会泄漏其功能，这样就可以在 MBAM 客户端上重新配置 BitLocker 驱动器加密和获取 BitLocker 加密密钥数据。 但是，由于拒绝服务攻击而导致的 MBAM 功能的损失通常不会产生灾难性影响，例如，丢失电子邮件或网络通信，或使用电源。

**确保计算机的物理安全**。 没有物理安全的安全性。 获得 MBAM 服务器物理访问权限的攻击者可能会使用它来攻击整个客户端。 所有潜在的物理攻击都必须被视为高风险并相应地缓解。 MBAM 服务器应存储在具有受控访问权限的安全服务器机房中。 通过让操作系统锁定计算机，或使用安全的屏幕保护程序，确保管理员不在物理上显示这些计算机。

**对所有计算机应用最新的安全更新**。 通过在[安全技术中心](https://go.microsoft.com/fwlink/?LinkId=28819)订阅安全通知服务，随时了解 Windows 操作系统、SQL SERVER 和 MBAM 的新更新。

**使用强密码或密码短语**。 始终对所有 MBAM 管理员帐户使用具有15个或更多字符的强密码。 千万不要使用空白密码。 有关密码概念的详细信息，请参阅[密码策略](https://technet.microsoft.com/library/hh994572.aspx)。



## 相关主题


[规划部署 MBAM 2.5](planning-to-deploy-mbam-25.md)

 
## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。
 





