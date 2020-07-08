---
title: MBAM 2.5 客户端的先决条件
description: MBAM 2.5 客户端的先决条件
author: dansimp
ms.assetid: fc230679-9c84-4b99-a77c-bae7e7bf8145
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 04/23/2017
ms.openlocfilehash: ac5e211e5ea038f47db3d5e68155eb5af38aa231
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804074"
---
# MBAM 2.5 客户端的先决条件


在最终用户的计算机上安装 MBAM 客户端软件之前，请确保你的环境和客户端计算机满足以下先决条件。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">必备</th>
<th align="left">详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>企业域必须包含至少一个 Windows Server 2008 （或更高版本）域控制器。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>客户端计算机必须登录到企业 intranet。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>仅适用于 Windows 7 客户端计算机：每个客户端必须具有受信任的平台模块（TPM）功能（tpm 1.2 或更高版本）。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>对于 Windows 8.1、Windows 10 RTM 或 Windows 10 版本1511客户端计算机：如果你希望 MBAM 能够存储和管理 TPM 恢复密钥，则必须关闭 TPM 自动预配，并且必须在部署 MBAM 之前将 MBAM 设置为 TPM 的所有者。</p>
<p>在 MBAM 2.5 SP1 中，你不再需要关闭 TPM 自动预配，但必须确保 TPM 组策略对象设置为不将 TPM 托管 OwnerAuth 到 Active Directory。</p></td>
<td align="left"><p><a href="mbam-25-security-considerations.md#bkmk-tpm" data-raw-source="[MBAM 2.5 Security Considerations](mbam-25-security-considerations.md#bkmk-tpm)">MBAM 2.5 安全注意事项</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>对于 Windows 10 版本1607或更高版本，只有 Windows 可以获得 TPM 的所有权。 在 addiiton 中，Windows 将不会在预配 TPM 时保留 TPM 所有者密码。</p>
<p>在 MBAM 2.5 SP1 中，必须启用自动预配。</p>
</p></td>
<td align="left"><p><a href="https://technet.microsoft.com/itpro/windows/keep-secure/change-the-tpm-owner-password" data-raw-source="[TPM owner password](https://technet.microsoft.com/itpro/windows/keep-secure/change-the-tpm-owner-password)"> </a> 有关进一步的详细信息，请参阅 TPM 所有者密码。
</p></td>
</tr>
<tr class="even">
<td align="left"><p>必须在 BIOS 中打开 TPM 芯片，并将其从操作系统中 resettable。</p></td>
<td align="left"><p>有关详细信息，请参阅 BIOS 文档。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>计算机的硬盘必须至少有两个分区，并且必须使用 NTFS 文件系统进行格式化。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>计算机的硬盘必须具有与 TPM 兼容且在计算机启动期间支持 USB 设备的 BIOS。</p></td>
<td align="left"><div class="alert">
<strong>注意</strong><br/><p>确保键盘、视频或鼠标直接连接，而不是通过键盘、视频或鼠标（KVM）切换器管理。 KVM 切换器可能会干扰计算机检测硬件实际存在的能力。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>如果使用代理，它必须在系统上下文中可见。 MBAM 在系统上下文下运行，而不是在用户上下文中运行。</p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



**重要提示**  
如果在没有 MBAM 的情况下使用 BitLocker，则可以安装 MBAM 并利用现有的 TPM 信息。




## 相关主题


[MBAM 2.5 支持的配置](mbam-25-supported-configurations.md)

[规划部署 MBAM 2.5](planning-to-deploy-mbam-25.md)


## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。






