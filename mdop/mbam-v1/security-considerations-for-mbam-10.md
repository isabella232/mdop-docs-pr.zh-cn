---
title: MBAM 1.0 的安全注意事项
description: MBAM 1.0 的安全注意事项
author: dansimp
ms.assetid: 5e1c8b8c-235b-4a92-8b0b-da50dca17353
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: b06c343c8193293dde91bc7af2541f35f332d261
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803919"
---
# MBAM 1.0 的安全注意事项


本主题包含帐户和组、日志文件以及有关 Microsoft BitLocker 管理和监视的其他与安全相关的注意事项（MBAM）的简要概述。 有关详细信息，请访问本文中的链接。

## 常规安全注意事项


**了解安全风险。** MBAM 最严重的风险是，未经授权的用户可能会被未经授权的用户劫持，这样就可以在 MBAM 客户端上重新配置 BitLocker 加密和获取 BitLocker 加密密钥数据。 但是，由于拒绝服务攻击，MBAM 功能在短时间内丢失通常不会产生灾难性影响。

**确保计算机的物理安全**。 安全性不完整，没有物理安全。 对 MBAM 服务器具有物理访问权限的任何人都可能会攻击整个客户群。 任何潜在的物理攻击都必须被视为高风险并相应地缓解。 MBAM 服务器应存储在具有可控访问权限的物理安全的服务器机房中。 通过让操作系统锁定计算机，或使用安全的屏幕保护程序，确保管理员不在物理上显示这些计算机。

**对所有计算机应用最新的安全更新**。 通过订阅安全通知服务（），随时了解操作系统、Microsoft SQL Server 和 MBAM 的新更新 <https://go.microsoft.com/fwlink/p/?LinkId=28819> 。

**使用强密码或密码短语**。 对于所有 MBAM 和 MBAM 管理员帐户，请始终使用具有15个或更多字符的强密码。 千万不要使用空白密码。 有关密码概念的详细信息，请参阅 TechNet 上的 "帐户密码和策略" 白皮书（ <https://go.microsoft.com/fwlink/p/?LinkId=30009> ）。

## MBAM 中的帐户和组


用户帐户管理的最佳做法是创建域全局组并向其添加用户帐户。 然后，将域全局帐户添加到 MBAM 服务器上必需的 MBAM 本地组。

### ActiveDirectoryDomainServices 组

MBAM 安装期间不会自动创建任何组。 但是，你应该创建以下 ActiveDirectoryDomainServices 全局组来管理 MBAM 操作。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">组名称</th>
<th align="left">详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>MBAM 高级帮助台用户</p></td>
<td align="left"><p>创建此组以管理在 MBAM 设置期间创建的 MBAM 高级帮助台用户本地组的成员。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MBAM 合规性审核数据库访问</p></td>
<td align="left"><p>创建此组以管理在 MBAM 设置期间创建的 MBAM 合规性审核数据库 Access 本地组的成员。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MBAM 硬件用户</p></td>
<td align="left"><p>创建此组以管理在 MBAM 设置期间创建的 MBAM 硬件用户本地组的成员。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MBAM 帮助台用户</p></td>
<td align="left"><p>创建此组以管理在 MBAM 设置期间创建的 MBAM 帮助台用户本地组的成员。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MBAM 恢复和硬件 DB 访问</p></td>
<td align="left"><p>创建此组以管理在 MBAM 设置期间创建的 MBAM 恢复和硬件数据库 Access 本地组的成员。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MBAM 报表用户</p></td>
<td align="left"><p>创建此组以管理在 MBAM 设置期间创建的 MBAM 报表用户本地组的成员。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MBAM 系统管理员</p></td>
<td align="left"><p>创建此组以管理在 MBAM 设置期间创建的 MBAM 系统管理员本地组的成员。</p></td>
</tr>
<tr class="even">
<td align="left"><p>BitLocker 加密免除</p></td>
<td align="left"><p>创建此组以管理应从登录的计算机上开始免除 BitLocker 加密的用户帐户。</p></td>
</tr>
</tbody>
</table>

 

### MBAM 服务器本地组

MBAM 安装程序创建本地组以支持 MBAM 操作。 应将 ActiveDirectoryDomainServices 全局组添加到相应的 MBAM 本地组，以配置 MBAM 安全和数据访问权限。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">组名称</th>
<th align="left">详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>MBAM 高级帮助台用户</p></td>
<td align="left"><p>此组的成员已扩展对 Microsoft BitLocker 管理和监视的帮助台功能的访问权限。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MBAM 合规性审核数据库访问</p></td>
<td align="left"><p>此组包含有权访问 MBAM 合规性审核数据库的计算机。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MBAM 硬件用户</p></td>
<td align="left"><p>此组的成员可以访问 Microsoft BitLocker 管理和监视中的某些硬件功能功能。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MBAM 帮助台用户</p></td>
<td align="left"><p>本组成员可以访问 Microsoft BitLocker 管理和监视中的某些帮助台功能。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MBAM 恢复和硬件 DB 访问</p></td>
<td align="left"><p>此组包含有权访问 MBAM 恢复和硬件数据库的计算机。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MBAM 报表用户</p></td>
<td align="left"><p>本组成员可以访问 Microsoft BitLocker 管理和监视中的合规性和审核报告。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MBAM 系统管理员</p></td>
<td align="left"><p>此组的成员具有 Microsoft BitLocker 管理和监视的所有功能的访问权限。</p></td>
</tr>
</tbody>
</table>

 

### SSRS 报表访问帐户

SQL Server Reporting Services （SSRS）报表服务帐户提供用于运行 SSRS 提供的 MBAM 报告的安全上下文。 此帐户在 MBAM 安装期间配置。

## MBAM 日志文件


在 MBAM 设置期间，以下 MBAM 安装日志文件将在安装了该文件的用户的% temp% 文件夹中创建。

**MBAM Server 安装程序日志文件**

<a href="" id="msi-five-random-characters--log"></a>MSI <em> &lt; 5 个随机字符 &gt; </em> 。日志  
记录 MBAM 安装和 MBAM 服务器功能安装期间所执行的操作。

<a href="" id="installcompliancedatabase-log"></a>InstallComplianceDatabase  
记录创建 MBAM 合规性状态数据库设置所执行的操作。

<a href="" id="installkeycompliancedatabase-log"></a>InstallKeyComplianceDatabase  
记录创建 MBAM 恢复和硬件数据库所执行的操作。

<a href="" id="addhelpdeskdbauditusers-log"></a>AddHelpDeskDbAuditUsers  
记录在 MBAM 合规性状态数据库上创建 SQL Server 登录并针对报表向数据库授权支持人员 web 服务所执行的操作。

<a href="" id="addhelpdeskdbusers-log"></a>AddHelpDeskDbUsers  
记录对用于密钥恢复的数据库进行授权 web 服务所执行的操作，并创建 MBAM 恢复和硬件数据库的登录。

<a href="" id="addkeycompliancedbusers-log"></a>AddKeyComplianceDbUsers  
将授权 web 服务所执行的操作记录到符合性报告的 MBAM 合规性状态数据库中。

<a href="" id="addrecoveryandhardwaredbusers-log"></a>AddRecoveryAndHardwareDbUsers  
记录授权 web 服务以 MBAM 恢复和硬件数据库进行密钥恢复所执行的操作。

**注意** 为了获取其他 MBAM 安装日志文件，必须使用**msiexec**程序包和 **/l** Location 选项安装 Microsoft BitLocker 管理和监视 &lt; &gt; 。 在指定位置创建日志文件。

 

**MBAM 客户端安装程序日志文件**

<a href="" id="msi-five-random-characters--log"></a>MSI <em> &lt; 5 个随机字符 &gt; </em> 。日志  
记录在 MBAM 客户端安装期间执行的操作。

## MBAM 数据库 TDE 注意事项


SQL Server 2008 中可用的 "透明数据加密" （TDE）功能是将托管数据库功能的数据库实例的必需安装必备项。

通过 TDE，你可以执行实时、完整数据库级别的加密。 TDE 是一种非常合适的选项，可用于批量加密以满足合规性或公司数据安全标准。 TDE 适用于文件级别，它类似于两个 Windows 功能：加密文件系统（EFS）和 BitLocker 驱动器加密，这两者也会对硬盘上的数据进行加密。 TDE 不会替换单元级加密、EFS 或 BitLocker。

在数据库上启用 TDE 时，将加密所有备份。 因此，必须特别注意才能确保使用数据库备份对用于保护数据库加密密钥（DEK）的证书进行备份和维护。 如果没有证书，数据将不可读。 备份证书和数据库。 每个证书备份都应具有两个文件;这两个文件都应存档。最好将它们与数据库备份文件分开存档，以确保安全。

有关如何为 MBAM 数据库实例启用 TDE 的示例，请参阅[评估 MBAM 1.0](evaluating-mbam-10.md)。

有关 SQLServer 2008 中的 TDE 的详细信息，请参阅[SQL Server 2008 企业版中的数据库加密](https://go.microsoft.com/fwlink/?LinkId=269703)。

## 相关主题


[MBAM 1.0 的安全和隐私](security-and-privacy-for-mbam-10.md)

 

 





