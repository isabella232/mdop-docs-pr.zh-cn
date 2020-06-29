---
title: 确定设备接收不合规消息的原因
description: 确定设备接收不合规消息的原因
author: dansimp
ms.assetid: 793df330-a0ee-4759-b53a-95618ac74428
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/22/2017
ms.openlocfilehash: ce1d344676ebf4328506228f1bfa87c76e8036f9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803595"
---
# 确定设备接收不合规消息的原因


以下不符合的代码由 WMI 提供，并描述了 MBAM 将特定设备报告为不符合的原因。

你可以使用你的首选方法查看 WMI。 如果使用 PowerShell，请 `gwmi -class mbam_volume -Namespace root\microsoft\mbam` 从 PowerShell 提示符运行，然后搜索 ReasonsForNoncompliance。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">不合规代码</th>
<th align="left">违反合规性的原因</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>0</p></td>
<td align="left"><p>密码长度不是 AES 256。</p></td>
</tr>
<tr class="even">
<td align="left"><p>raid-1</p></td>
<td align="left"><p>MBAM 策略要求将此卷加密，而不是。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ppls-2</p></td>
<td align="left"><p>MBAM 策略要求此卷不加密，但它是。</p></td>
</tr>
<tr class="even">
<td align="left"><p>三维空间</p></td>
<td align="left"><p>MBAM 策略需要此卷使用 TPM 保护程序，但不需要。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>第</p></td>
<td align="left"><p>MBAM 策略需要此卷使用 TPM + 引脚保护程序，但不需要。</p></td>
</tr>
<tr class="even">
<td align="left"><p>级</p></td>
<td align="left"><p>MBAM 策略不允许非 TPM 计算机报告为合规。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>型</p></td>
<td align="left"><p>卷具有 TPM 保护程序，但 TPM 不可见（使用恢复密钥在 BIOS 中禁用 TPM 后启动）。</p></td>
</tr>
<tr class="even">
<td align="left"><p>7</p></td>
<td align="left"><p>MBAM 策略需要此卷使用密码保护程序，但没有密码保护程序。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>个</p></td>
<td align="left"><p>MBAM 策略要求此卷不使用密码保护程序，但有一个密码保护器。</p></td>
</tr>
<tr class="even">
<td align="left"><p>db-9</p></td>
<td align="left"><p>MBAM 策略需要此卷使用自动解锁保护程序，但没有该卷。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>10</p></td>
<td align="left"><p>MBAM 策略需要此卷不使用自动解锁保护程序，但它有一个。</p></td>
</tr>
<tr class="even">
<td align="left"><p>11</p></td>
<td align="left"><p>检测到策略冲突阻止 MBAM 将此卷报告为合规。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>至</p></td>
<td align="left"><p>需要系统卷来加密操作系统卷，但该卷不存在。</p></td>
</tr>
<tr class="even">
<td align="left"><p>13</p></td>
<td align="left"><p>已针对卷暂停保护。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>14</p></td>
<td align="left"><p>AutoUnlock 不安全，除非操作系统卷已加密。</p></td>
</tr>
<tr class="even">
<td align="left"><p>岁</p></td>
<td align="left"><p>策略要求最低的 cypher 强度为 XTS-128 位，实际 cypher 强度比这更弱。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>utf-16</p></td>
<td align="left"><p>策略要求最低的 cypher 强度为 XTS-256 位，实际 cypher 强度比这更弱。</p></td>
</tr>
</tbody>
</table>

 

## 相关主题


[MBAM 2.5 的技术参考](technical-reference-for-mbam-25.md)

[使用 Windows PowerShell 配置 MBAM 2.5 服务器功能](configuring-mbam-25-server-features-by-using-windows-powershell.md)

 
## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。
 





