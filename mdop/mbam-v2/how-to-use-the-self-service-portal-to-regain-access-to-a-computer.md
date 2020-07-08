---
title: 如何使用自助服务门户重获计算机访问权限
description: 如何使用自助服务门户重获计算机访问权限
author: dansimp
ms.assetid: bcf095de-0237-4bb0-b450-da8fb6d6f3d0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4abcffcf35e09bd5e24f4715a38dca74518ba29e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803896"
---
# 如何使用自助服务门户重获计算机访问权限


如果最终用户因忘记了密码或 PIN 而被 BitLocker 锁定了 Windows，或者他们更改了操作系统文件或者更改了 BIOS 或受信任的平台模块（TPM），他们可以使用自助服务门户重新获取对 Windows 的访问权限，而无需向其支持人员寻求帮助。

**注意** 如果 IT 管理员配置了 IIS 会话状态超时，则会在超时前60秒显示一条消息。

 

**注意** 这些说明针对最终用户的观点进行编写。

 

**使用自助服务门户重新获取对计算机的访问权限**

1.  在 "**恢复**密钥 ID" 字段中，输入计算机的 BitLocker 恢复屏幕上显示的至少8个32位的 bitlocker 密钥 ID。

    **注意** 如果前八个数字与多个键匹配，则会显示一条消息，要求你输入恢复密钥 ID 的所有32位。

     

2.  在 "**原因**" 字段中，为你的恢复密钥请求选择一个原因。

3.  单击 "**获取键**"。 你的 BitLocker 恢复密钥显示在 "BitLocker 恢复密钥" 字段中。

4.  在计算机上的 BitLocker 恢复屏幕中输入48位代码，以重新获取对计算机的访问权限。

## 相关主题


[使用 MBAM 执行 BitLocker 管理](performing-bitlocker-management-with-mbam-mbam-2.md)

 

 





