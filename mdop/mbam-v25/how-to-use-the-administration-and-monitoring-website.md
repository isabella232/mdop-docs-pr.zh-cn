---
title: 如何使用管理和监控网站
description: 如何使用管理和监控网站
author: dansimp
ms.assetid: bb96a4e8-d4f4-4e6f-b7db-82d96998bfa6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9b9597e29a5a7a6236cb351d8d6d1f682edce3cf
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798197"
---
# 如何使用管理和监控网站


管理和监视网站（也称为帮助桌面）是用于 BitLocker 驱动器加密的管理界面。 使用该网站查看报告、恢复最终用户的驱动器和管理最终用户的 TPMs，如下部分所述。

**注意** 如果在独立拓扑中使用 MBAM，则可以从 "管理和监视" 网站查看所有报表。 如果您使用的是 Configuration Manager 集成拓扑，则可以在 "配置管理器" 中查看所有报表，但恢复审核报表除外，您可以从 "管理和监视" 网站继续查看。 有关报表的详细信息，请参阅[通过 MBAM 2.5 监视和报告 BitLocker 合规性](monitoring-and-reporting-bitlocker-compliance-with-mbam-25.md)。

 

## 使用管理和监视网站所需的角色


若要访问管理和监视网站的特定区域，你必须具有下列角色之一，这些角色是你在 Active Directory 中创建的组。 你可以为这些组使用任何名称。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">帐户</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>MBAM 高级帮助台用户</p></td>
<td align="left"><p>提供对管理和监视网站的所有区域的访问权限。 具有此角色的用户在帮助最终用户恢复其驱动器时，只需输入恢复密钥，而不是最终用户的域和用户名。 如果用户是 MBAM "支持人员" 组和 MBAM "高级帮助台用户" 组的成员，则 MBAM "高级帮助台用户" 组权限将替代 "MBAM 帮助台用户" 组权限。</p>
<p></p></td>
</tr>
<tr class="even">
<td align="left"><p>MBAM 帮助台用户</p></td>
<td align="left"><p>提供对管理和监视网站的 "管理 TPM" 和 "驱动器恢复" 区域的访问权限。 具有此角色的人员必须在使用任一区域时填写所有字段，包括最终用户的域和帐户名称。</p>
<p>如果用户是 MBAM "支持人员" 组和 MBAM "高级帮助台用户" 组的成员，则 MBAM "高级帮助台用户" 组权限将替代 "MBAM 帮助台用户" 组权限。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MBAM 报表用户</p></td>
<td align="left"><p>提供对 <strong> </strong> 管理和监控网站的 "报告" 区域中的报告的访问权限。</p></td>
</tr>
</tbody>
</table>

 

## 可在 "管理和监视" 网站上执行的任务


下表总结了可在 "管理" 和 "监视" 网站上执行的任务，并提供了指向有关每个任务的详细信息的链接。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">任务</th>
<th align="left">您可在其中访问任务的网站区域</th>
<th align="left">描述</th>
<th align="left">有关详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>查看报告</p></td>
<td align="left"><p>报告</p></td>
<td align="left"><p>使你能够运行报告，以监视 BitLocker 使用情况、合规性和密钥恢复活动。 报表提供有关企业合规性、单个计算机以及为特定计算机请求恢复密钥或 TPM OwnerAuth 程序包的数据。</p></td>
<td align="left"><p><a href="viewing-mbam-25-reports-for-the-stand-alone-topology.md" data-raw-source="[Viewing MBAM 2.5 Reports for the Stand-alone Topology](viewing-mbam-25-reports-for-the-stand-alone-topology.md)">查看独立拓扑的 MBAM 2.5 报告</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>确定丢失或被盗计算机的 BitLocker 加密状态</p></td>
<td align="left"><p>报告</p></td>
<td align="left"><p>确定当计算机丢失或被盗时，卷是否已加密。</p></td>
<td align="left"><p><a href="how-to-determine-bitlocker-encryption-state-of-lost-computers-mbam-25.md" data-raw-source="[How to Determine BitLocker Encryption State of Lost Computers](how-to-determine-bitlocker-encryption-state-of-lost-computers-mbam-25.md)">如何确定丢失计算机的 BitLocker 加密状态</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>恢复丢失的驱动器</p></td>
<td align="left"><p>驱动器恢复</p></td>
<td align="left"><p>恢复驱动器：</p>
<ul>
<li><p>在恢复模式下</p></li>
<li><p>已被移动</p></li>
<li><p>已损坏</p></li>
</ul></td>
<td align="left"><ul>
<li><p><a href="how-to-recover-a-drive-in-recovery-mode-mbam-25.md" data-raw-source="[How to Recover a Drive in Recovery Mode](how-to-recover-a-drive-in-recovery-mode-mbam-25.md)">如何在恢复模式下恢复驱动器</a></p></li>
<li><p><a href="how-to-recover-a-moved-drive-mbam-25.md" data-raw-source="[How to Recover a Moved Drive](how-to-recover-a-moved-drive-mbam-25.md)">如何恢复已移动的驱动器</a></p></li>
<li><p><a href="how-to-recover-a-corrupted-drive-mbam-25.md" data-raw-source="[How to Recover a Corrupted Drive](how-to-recover-a-corrupted-drive-mbam-25.md)">如何恢复已损坏的驱动器</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>重置 TPM 锁定</p></td>
<td align="left"><p>管理 TPM</p></td>
<td align="left"><p>提供对 MBAM 客户端收集的 TPM 数据的访问权限。 在 TPM 锁定中，使用 "管理和监视" 网站检索用于解锁 TPM 的必需密码文件。</p></td>
<td align="left"><p><a href="how-to-reset-a-tpm-lockout-mbam-25.md" data-raw-source="[How to Reset a TPM Lockout](how-to-reset-a-tpm-lockout-mbam-25.md)">如何重置 TPM 锁定</a></p></td>
</tr>
</tbody>
</table>

 


## 相关主题


[使用 MBAM 2.5 执行 BitLocker 管理](performing-bitlocker-management-with-mbam-25.md)

 

## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





