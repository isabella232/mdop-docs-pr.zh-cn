---
title: 如何使用自助服务门户重获计算机访问权限
description: 如何使用自助服务门户重获计算机访问权限
author: dansimp
ms.assetid: 3c24b13a-d1b1-4763-8ac0-0b2db46267e3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cde9c71a957a5270d69aa8388455895f1cb2432b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804021"
---
# 如何使用自助服务门户重获计算机访问权限


自助服务门户是 IT 管理员将其配置为 Microsoft BitLocker 管理和监视（MBAM）2.5 部署的一部分的网站。 如果用户被封锁到 Windows，则该网站使最终用户能够独立地重新获取其计算机的访问权限。 自助服务门户不需要技术支持人员的帮助。

以下说明是从最终用户的角度编写的，但该信息可能有助于 IT 管理员理解。

**重要提示** 最终用户必须至少有一次登录到计算机（非远程）才能使用自助服务门户恢复其密钥。 否则，他们必须使用支持人员门户进行密钥恢复。

 

最终用户可能会在以下情况中遇到锁定：

-   忘记了密码或 PIN 码

-   更改操作系统文件、BIOS 或受信任的平台模块（TPM）

**注意** 如果 IT 管理员配置了一个 IIS 会话状态超时，则在出现超时前的自助服务门户60秒中会显示一条消息。

 

**使用自助服务门户重新获取对计算机的访问权限**

1.  在 "**恢复**密钥 ID" 字段中，输入计算机的 BitLocker 恢复屏幕上显示的至少8个32位的 bitlocker 密钥 ID。 如果前八个数字与多个键匹配，则会显示一条消息，要求你输入恢复密钥 ID 的所有32位。

2.  在 "**原因**" 字段中，为你的恢复密钥请求选择一个原因。

3.  单击 "**获取键**"。 您的 BitLocker 恢复密钥显示在 " **Bitlocker 恢复密钥**" 字段中。

4.  在计算机上的 BitLocker 恢复屏幕中输入48位代码，以重新获取对计算机的访问权限。



## 相关主题


[使用 MBAM 2.5 执行 BitLocker 管理](performing-bitlocker-management-with-mbam-25.md)

 
## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。
 





