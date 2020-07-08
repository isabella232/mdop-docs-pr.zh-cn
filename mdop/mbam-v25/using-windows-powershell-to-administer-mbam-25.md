---
title: 使用 Windows PowerShell 管理 MBAM 2.5
description: 使用 Windows PowerShell 管理 MBAM 2.5
author: dansimp
ms.assetid: 64668e76-2cba-433d-8d2d-50df0a4b2997
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 11/02/2016
ms.openlocfilehash: 8db305bfbdf79723da2b186dd5cc00406a4089cc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798120"
---
# 使用 Windows PowerShell 管理 MBAM 2.5


本主题介绍 Microsoft BitLocker 管理和监视（MBAM）的 Windows PowerShell cmdlet，这些 cmdlet 与用户锁定时恢复计算机或驱动器相关。

对于用于配置 MBAM 服务器功能的 cmdlet，请参阅[使用 Windows PowerShell 配置 MBAM 2.5 服务器功能](configuring-mbam-25-server-features-by-using-windows-powershell.md)。

## <a href="" id="cmdlets-for-recovering-computers-or-drives-that-are-managed-by-mbam-"></a>用于恢复由 MBAM 托管的计算机或驱动器的 cmdlet


使用以下 Windows PowerShell cmdlet 恢复由 MBAM 托管的计算机或驱动器。

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
<td align="left"><p>MbamBitLockerRecoveryKey</p></td>
<td align="left"><p>请求允许用户解锁计算机或加密驱动器的 MBAM 恢复密钥。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MbamTPMOwnerPassword</p></td>
<td align="left"><p>向用户提供 TPM 所有者密码，这些密码可用于在 TPM 已锁定并将不再接受其 PIN 时解锁受信任的平台模块（TPM）。</p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="---------mbam-cmdlet-help"></a> MBAM cmdlet 帮助


适用于 MBAM cmdlet 的 Windows PowerShell 帮助采用以下格式：

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
<td align="left"><p>若要上载最新的 Windows PowerShell cmdlet，请按照 <a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)"> 使用 Windows PowerShell 配置 MBAM 2.5 服务器功能中的说明进行操作</a></p></td>
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

 



## 相关主题


[管理 MBAM 2.5 功能](administering-mbam-25-features.md)

[使用 Windows PowerShell 配置 MBAM 2.5 服务器功能](configuring-mbam-25-server-features-by-using-windows-powershell.md)

 

## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





