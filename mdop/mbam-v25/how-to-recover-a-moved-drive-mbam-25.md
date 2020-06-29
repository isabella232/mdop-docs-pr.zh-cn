---
title: 如何恢复已移动的驱动器
description: 如何恢复已移动的驱动器
author: dansimp
ms.assetid: 0d38ce7e-bc64-473e-ae85-99b7099ca758
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: 9e7e03846e0a94902b699377043237c651939a07
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803349"
---
# 如何恢复已移动的驱动器
本主题介绍了如何使用管理和监视网站（也称为帮助桌面）恢复在由 Microsoft BitLocker 管理和监视（MBAM）加密之后移动的操作系统驱动器。 移动驱动器后，由于受信任的平台模块（TPM）芯片已更改，因此它不再接受以前计算机中使用的 PIN。 若要恢复移动的驱动器，您必须获取恢复密钥 ID 才能检索恢复密码。

若要恢复移动的驱动器，必须使用管理和监视网站的**驱动器恢复**区域。 要访问**驱动器恢复**区域，你必须被分配 MBAM 帮助台用户角色或 MBAM 高级帮助台用户角色。 有关这些角色的详细信息，请参阅[规划 MBAM 2.5 组和帐户](planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles)。

**恢复移动的驱动器**
1.  在包含已移动的驱动器的计算机上，在 Windows 恢复环境（WinRE）模式下启动计算机，或使用 Microsoft 诊断和恢复工具集（DaRT）启动计算机。

2.  使用 WinRE 或 DaRT 启动计算机后，MBAM 会将移动的操作系统驱动器视为固定数据驱动器。 MBAM 将显示驱动器的恢复密码 ID 并要求输入恢复密码。

    **注意** 在某些情况下，你可能可以在启动过程中单击 "**我忘记了 PIN** "，然后输入恢复模式以显示恢复密钥 ID。

     

3.  使用恢复密钥 ID 检索恢复密码并通过管理和监视网站解锁驱动器。 有关说明，请参阅[如何在恢复模式下恢复驱动器](how-to-recover-a-drive-in-recovery-mode-mbam-25.md)。

    如果移动的驱动器配置为使用原始计算机上的 TPM 芯片，请完成以下附加步骤。 否则，恢复过程已完成。

4.  解锁驱动器并完成启动过程后，在 WinRE 模式下打开命令提示符并使用该 `manage-bde` 命令对驱动器进行解密。 使用此工具是删除 TPM 以及没有原始 TPM 芯片的引脚保护器的唯一方法。 有关该命令的信息 `manage-bde` ，请参阅[manage-bde](https://go.microsoft.com/fwlink/?LinkId=393567)。

5.  删除完成后，正常启动计算机。 MBAM 代理现在将强制实施该策略，使用新计算机的 TPM 和 PIN 加密驱动器。



## 相关主题


[使用 MBAM 2.5 执行 BitLocker 管理](performing-bitlocker-management-with-mbam-25.md)

 

## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





