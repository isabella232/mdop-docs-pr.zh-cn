---
title: 关于 MBAM 2.5 SP1
description: 关于 MBAM 2.5 SP1
author: dansimp
ms.assetid: 6f12e605-44e6-4646-9c20-aee89c8ff0b7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 09/27/2016
ms.openlocfilehash: 41e47e1561629c00d30b45ad2dcd94f37753af5b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803437"
---
# 关于 MBAM 2.5 SP1


MBAM 2.5 SP1 为 BitLocker 驱动器加密提供简化的管理接口。 对于丢失或被盗的计算机，BitLocker 提供增强的防护功能，防止数据失窃或数据暴露。 BitLocker 将加密存储在 Windows 操作系统和驱动器以及配置的数据驱动器上的所有数据。

## MBAM 概述


MBAM 2.5 SP1 具有以下功能：

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

 

## <a href="" id="what-s-new-in-mbam-2-5-sp1"></a>MBAM 2.5 SP1 中的新增功能


本部分介绍了 MBAM 2.5 SP1 中的新增功能。

### MBAM 2.5 SP1 客户端的新支持语言

以下附加语言现在仅在 MBAM 客户端的 MBAM 2.5 SP1 中受支持，包括自助门户：

捷克语（捷克共和国） cs-CZ

丹麦语（丹麦） da-深色

荷兰语（荷兰） nl-NL

芬兰语（芬兰） wlan

希腊语（希腊） el-GR

匈牙利语（匈牙利） hu-HU

挪威语、博克马尔语（挪威） nb-否

波兰语（波兰） pl-PL

葡萄牙语（葡萄牙） pt

斯洛伐克语（斯洛伐克） sk-SK

斯洛文尼亚语（斯洛文尼亚） sl-SI

瑞典语（瑞典） sv-SE

土耳其语（土耳其） tr-TR

有关 MBAM 2.5 和 MBAM 2.5 SP1 中的客户端和服务器支持的所有语言的列表，请参阅[MBAM 2.5 支持的配置](mbam-25-supported-configurations.md)。

### Windows 10 支持

MBAM 2.5 SP1 除了更早版本的 MBAM 支持的同一软件外，还添加了对 Windows 10 和 Windows Server 2016 的支持。

Windows 10 在 MBAM 2.5 和 MBAM 2.5 SP1 中均受支持。

### Microsoft SQL Server 2014 SP1 的支持

MBAM 2.5 SP1 不仅增加了对 Microsoft SQL Server 2014 SP1 的支持，还添加了与早期版本的 MBAM 中支持的同一软件。

### MBAM 不再附带单独的 MSI

从 MBAM 2.5 SP1 开始，MBAM 产品不再附带单独的 MSI。 但是，你可以从产品附带的可执行文件（.exe）中提取 MSI。

### MBAM 可以在不拥有 TPM 的情况下保管 OwnerAuth 密码

以前，如果 MBAM 不拥有 TPM，则无法将 TPM OwnerAuth escrowed 到 MBAM 数据库。 若要将 MBAM 配置为拥有 TPM 并存储密码，必须禁用 TPM 自动预配，并在客户端计算机上清除 TPM。

在 Windows 8 及更高版本中，MBAM 2.5 SP1 现在可以在不拥有 TPM 的情况下保管 OwnerAuth 密码。 在服务启动期间，MBAM 查询以查看 TPM 是否已拥有，如果是，则它会从操作系统请求密码。 然后，密码将 escrowed 到 MBAM 数据库。 此外，必须设置组策略以防止 OwnerAuth 在本地删除。

在 Windows 7 中，MBAM 必须拥有 TPM 才能在 MBAM 数据库中自动托管 TPM OwnerAuth 信息。 如果 MBAM 不拥有 TPM，并且通过组策略配置 TPM 的 Active Directory （AD）备份，则必须使用**MBAM Active Directory （ad）数据导入 cmdlet**将 TPM OWNERAUTH 从 AD 复制到 MBAM 数据库。 以下是五个新的 PowerShell cmdlet，这些 cmdlet 预填充了存储在 Active Directory 中的卷恢复和 TPM 所有者信息的 MBAM 数据库。

有关详细信息，请参阅[MBAM 2.5 安全注意事项](mbam-25-security-considerations.md#bkmk-tpm)。

### MBAM 可以在锁定后自动解锁 TPM

在运行 TPM 1.2 的计算机上，你现在可以将 MBAM 配置为在锁定时自动解锁 TPM。 如果启用了 TPM 锁定自动重置功能，MBAM 可以检测到用户已被锁定，然后获取 MBAM 数据库中的 OwnerAuth 密码，以便为用户自动解锁 TPM。

必须在服务器端和客户端上的组策略中启用此功能。 有关详细信息，请参阅[MBAM 2.5 安全注意事项](mbam-25-security-considerations.md#bkmk-autounlock)。

### 支持 FIPS 兼容的 BitLocker 数字密码保护器

在 MBAM 2.5 中，为运行 Windows 8.1 操作系统的设备上的联邦信息处理标准（FIPS）兼容的 BitLocker 恢复密钥添加了支持。 但是，Windows 未在 Windows 7 中实现符合 FIPS 的恢复密钥。 因此，Windows 7 和 Windows 8 设备仍需要用于恢复的数据恢复代理（DRA）保护程序。

Windows 团队拥有 backported FIPS 兼容的恢复密钥和一个修补程序，MBAM 2.5 SP1 还添加了对它们的支持。

**注意** 运行 Windows8 操作系统的客户端计算机仍需要 DRA 保护器，因为该修补程序不会 backported 该操作系统。 请参阅[Bitlocker 管理和监视2.5 的修补程序包 2](https://support.microsoft.com/kb/3015477) ，下载并安装适用于 windows 7 和 windows 8 计算机的 bitlocker 修补程序。 有关 DRA 的信息，请参阅将[数据恢复代理与 BitLocker 配合使用](https://go.microsoft.com/fwlink/?LinkId=393557)。

 

若要在你的组织中启用 FIPS 合规性，必须配置联邦信息处理标准（FIPS）组策略设置。 有关配置说明，请参阅[BitLocker 组策略设置](https://go.microsoft.com/fwlink/?LinkId=393560)。

### 通过新的组策略设置自定义启动前恢复消息和 URL

新的组策略设置，**配置预启动恢复消息和 URL**，让你可以配置自定义恢复消息或指定一个在操作系统驱动器锁定时在预启动 BitLocker 恢复屏幕上显示的 URL。 此设置仅在运行 Windows 10 的客户端计算机上可用。

如果启用此策略设置，你可以为预启动恢复消息选择以下选项之一：

-   **使用自定义恢复消息**：选择此选项可在预启动 BitLocker 恢复屏幕中包含自定义消息。

-   **使用自定义恢复 URL**：选择此选项可替换 "预启动 BitLocker 恢复" 屏幕中显示的默认 URL。

-   **使用默认的恢复消息和 URL**：选择此选项可在预启动 bitlocker 恢复屏幕中显示默认的 BitLocker 恢复消息和 url。 如果以前配置了自定义恢复消息或 URL 并希望还原为默认消息，则必须启用此策略，然后选择此选项。

新组策略设置位于以下 GPO 节点中：**计算机配置** &gt; **策略** &gt; **管理模板** &gt; **Windows 组件** &gt; **MDOP MBAM （BitLocker 管理）** &gt; **操作系统驱动器**。 有关详细信息，请参阅[规划 MBAM 2.5 组策略要求](planning-for-mbam-25-group-policy-requirements.md)。

### MBAM 添加了对已用空间加密的支持

在 MBAM 2.5 SP1 中，如果通过 BitLocker 组策略启用已使用的空间加密，MBAM 客户端将接受它。

此组策略设置称为 **"在操作系统驱动器上强制执行驱动器加密类型"** ，位于以下 GPO 节点中： "**计算机配置** &gt; **管理模板**" &gt; **Windows 组件**" &gt; **BitLocker 驱动器加密** &gt; **操作系统驱动器**"。 如果启用此策略并选择 "**仅限已用空间" 加密**的加密类型，则 MBAM 将接受该策略，并且 BitLocker 将仅加密卷上使用的磁盘空间。

有关详细信息，请参阅[规划 MBAM 2.5 组策略要求](planning-for-mbam-25-group-policy-requirements.md)。

### MBAM 客户端对加密硬驱的支持

MBAM 支持在满足 Opal 的 TCG 规范要求和 IEEE 1667 标准的加密硬盘上支持 BitLocker。 在这些设备上启用 BitLocker 时，它将在已加密的驱动器上生成密钥并执行管理功能。 有关详细信息，请参阅[加密的硬驱](https://technet.microsoft.com/library/hh831627.aspx)。

### 注册 Spn 时不再需要委派配置

在 MBAM 2.5 SP1 中不再需要为你注册应用程序池帐户所注册的 Spn 配置受限委派的要求。 但是，它仍是 MBAM 2.5 的必要条件。

### 使用 MBAM 作为 Windows 部署的一部分启用 BitLocker

在 MBAM 2.5 SP1 中，你可以使用 PowerShell 脚本将 BitLocker 驱动器加密和托管恢复密钥配置为 MBAM 服务器。

有关详细信息，请参阅[使用 MBAM 作为 Windows 部署的一部分来启用 BitLocker](how-to-enable-bitlocker-by-using-mbam-as-part-of-a-windows-deploymentmbam-25.md)

### 可以使用 PowerShell 或 SSP 自定义向导自定义自助服务门户

从 MBAM 2.5 SP1，自助服务门户可通过使用自定义向导以及使用 PowerShell 进行配置。 请参阅[如何配置 MBAM 2.5 Web 应用程序](how-to-configure-the-mbam-25-web-applications.md)。

### Web 浏览器不再无意间以管理员身份运行

MBAM 2.5 中的问题导致了服务器配置工具中的帮助链接，导致浏览器窗口以管理员权限打开。 此问题在 MBAM 2.5 SP1 中已修复。

### 当 CDN 不可访问时，不再需要下载 JavaScript 文件以配置自助服务门户

在 MBAM 2.5 和更早版本中，如果访问自助服务门户的客户没有 internet 访问权限，则必须提前从 CDN 下载用于配置自助服务门户的 jQuery 文件。 在 MBAM 2.5 SP1 中，所有 JavaScript 文件都包含在产品中，因此不需要下载它们。

### 可以在报表生成器3.0 中打开报表

在 MBAM 2.5 SP1 中，报表已更新为最新的报表定义语言架构，允许用户在报表生成器3.0 中打开和自定义报表，并将其立即保存，而不损坏报表文件。

### 新的 PowerShell cmdlet

MBAM 2.5 SP1 的新 PowerShell cmdlet 使你可以配置和管理不同的 MBAM 功能，包括数据库、报表和 web 应用程序。 每个功能都具有相应的 PowerShell cmdlet，可用于启用或禁用功能，或获取有关该功能的信息。

已针对 MBAM 2.5 SP1 实现以下 cmdlet：

-   Write-MbamTpmInformation

-   Write-MbamRecoveryInformation

-   Read ADTpmInformation

-   Read ADRecoveryInformation

-   Write-MbamComputerUser

以下参数已在 MBAM 2.5 SP1 的 Enable-MbamWebApplication 和 MbamWebApplication cmdlet 中实现：

-   DataMigrationAccessGroup

-   TpmAutoUnlock

有关 cmdlet 的详细信息，请参阅[MBAM 2.5 安全注意事项](mbam-25-security-considerations.md)和[Microsoft Bitlocker 管理和监视 Cmdlet 帮助](https://technet.microsoft.com/library/dn720418.aspx)。

### MBAM 代理检测演示模式

MBAM 代理可以检测计算机何时处于演示模式，避免在此时调用 MBAM UI。

### MBAM 代理服务现在配置为使用延迟启动

安装完成后，服务将立即将 MBAM 代理服务设置为使用延迟启动，减少启动 Windows 所需的时间量。

### 已锁定的固定数据卷现在报告为合规

"已锁定的固定数据" 卷的合规性计算逻辑已更改为将卷报告为 "合规"，但保护性状态和加密状态为 "Unknown"，并且具有 "卷已锁定" 的合规性状态详细信息。 以前，锁定的卷被报告为 "不合规"、"已加密" 的保护程序状态、"Unknown" 的加密状态以及 "未知错误" 的符合性状态详细信息。


## 如何获取 MDOP 技术


MBAM 是 Microsoft 桌面优化包（MDOP）的一部分。 MDOP 是 Microsoft 软件保障计划的一部分。 有关 Microsoft 软件保证计划以及如何获取 MDOP 的详细信息，请参阅[如何获取 mdop？](https://go.microsoft.com/fwlink/?LinkId=322049)。

## MBAM 2.5 SP1 发行说明


有关此文档中未包括的详细信息和最新新闻，请参阅[MBAM 2.5 SP1 的发行说明](release-notes-for-mbam-25-sp1.md)。

## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。

## 相关主题


[Microsoft BitLocker 管理和监控 2.5](index.md)

[MBAM 2.5 入门](getting-started-with-mbam-25.md)

 

 





