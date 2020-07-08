---
title: 使用 PowerShell 管理 MBAM 2.0
description: 使用 PowerShell 管理 MBAM 2.0
author: dansimp
ms.assetid: d785a8df-0a8c-4d70-abd2-93a762b4f3de
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 736943e707b5d033b8ba6c26641393f02f0cdaf8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803381"
---
# 使用 PowerShell 管理 MBAM 2.0


Microsoft BitLocker 管理和监视（MBAM）提供以下列出的一组 Windows PowerShell cmdlet。 管理员可以使用这些 PowerShell cmdlet 从命令行执行各种 Microsoft BitLocker 管理和监视服务器任务，而不是从 MBAM 管理网站执行。

## 如何使用 PowerShell 管理 MBAM


使用此处介绍的 PowerShell cmdlet 管理 MBAM。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名称</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>安装-Mbam</p></td>
<td align="left"><p>安装提供高级策略、加密、密钥恢复和合规性报告的 MBAM 功能。</p></td>
</tr>
<tr class="even">
<td align="left"><p>卸载-Mbam</p></td>
<td align="left"><p>删除提供高级策略、加密、密钥恢复和合规性报告工具的 MBAM 功能。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MbamBitLockerRecoveryKey</p></td>
<td align="left"><p>请求可使用户解锁计算机或加密驱动器的 MBAM 恢复密钥。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MbamTPMOwnerPassword</p></td>
<td align="left"><p>向用户提供 TPM 所有者密码，这些密码可用于在 TPM 已锁定并将不再接受其 PIN 时解锁受信任的平台模块（TPM）。</p></td>
</tr>
</tbody>
</table>

 

## 相关主题


[MBAM 2.0 的操作](operations-for-mbam-20-mbam-2.md)

 

 





