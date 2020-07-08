---
title: 使用 PowerShell 管理 MBAM 1.0
description: 使用 PowerShell 管理 MBAM 1.0
author: dansimp
ms.assetid: 3bf2eca5-4ab7-4e84-9e80-c0c7d709647b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3547bee9b2efc58252bb6f0a1cb0aa4c484e4e80
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803708"
---
# 使用 PowerShell 管理 MBAM 1.0


Microsoft BitLocker 管理和监视（MBAM）提供以下列出的一组 Windows PowerShell cmdlet。 管理员可以使用这些 PowerShell cmdlet 从命令提示符处而不是 MBAM 管理网站执行各种 MBAM 服务器任务。

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
<td align="left"><p>Add-MbamHardwareType</p></td>
<td align="left"><p>将新硬件模型添加到 MBAM 硬件清单。 此 cmdlet 还可指定 BitLocker 驱动器加密是否支持或不支持硬件。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MbamBitLockerRecoveryKey</p></td>
<td align="left"><p>请求将使用户能够解锁计算机或加密驱动器的 MBAM 恢复密钥。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MbamHardwareType</p></td>
<td align="left"><p>获取包含指示硬件模型是否兼容或与 BitLocker 驱动器加密不兼容的数据的主硬件清单。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MbamTPMOwnerPassword</p></td>
<td align="left"><p>为用户提供 TPM 所有者密码以管理其 TPM （受信任的平台模块）访问。 当 TPM 已锁定并将不再接受其 PIN 时，可帮助用户。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>安装-Mbam</p></td>
<td align="left"><p>安装提供高级组策略、加密、密钥恢复和合规性报告工具的 MBAM 功能。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Remove-MbamHardwareType</p></td>
<td align="left"><p>从硬件清单中删除硬件型号。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Set-MbamHardwareType</p></td>
<td align="left"><p>允许管理主硬件清单，以指定硬件模型是否支持或不能执行 BitLocker 加密。</p></td>
</tr>
<tr class="even">
<td align="left"><p>卸载-Mbam</p></td>
<td align="left"><p>删除以前安装的 MBAM 功能，这些功能提供高级策略、加密、密钥恢复和合规性报告工具。</p></td>
</tr>
</tbody>
</table>

 

## 相关主题


[MBAM 1.0 的操作](operations-for-mbam-10.md)

 

 





