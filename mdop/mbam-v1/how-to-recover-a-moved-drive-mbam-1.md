---
title: 如何恢复已移动的驱动器
description: 如何恢复已移动的驱动器
author: dansimp
ms.assetid: 0c7199d8-9463-4f44-9af3-b70eceeaff1d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e73e0878a3102d56494feb33efa69182029988c2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798168"
---
# 如何恢复已移动的驱动器


当您移动以前使用 Microsoft BitLocker 管理和监视（MBAM）加密的操作系统驱动器时，必须解决某些问题。 将 PIN 连接到新计算机后，驱动器将不会接受以前计算机中使用的启动 PIN。 由于对受信任的平台模块（TPM）芯片的更改，系统认为该 PIN 无效。 必须获取恢复密钥 ID 才能检索恢复密码，以便使用移动的驱动器。 若要执行此操作，请使用以下过程。

**恢复移动的驱动器**

1.  在包含移动的驱动器的计算机上，在 Windows 恢复环境（WinRE）模式下启动，或使用 Microsoft 诊断和恢复工具集（DaRT）启动计算机。

2.  使用 WinRE 或 DaRT 启动计算机后，MBAM 会将移动的操作系统驱动器视为数据驱动器。 MBAM 将显示驱动器的恢复密码 ID 并要求输入恢复密码。

    **注意** 在某些情况下，你可能可以在启动过程中单击 "**我忘记 PIN"** 以进入恢复模式。 这还会显示恢复密钥 ID。

     

3.  在 MBAM 管理网站上，使用恢复密钥 ID 检索恢复密码并解锁驱动器。

4.  如果移动的驱动器配置为使用原始计算机上的 TPM 芯片，则必须在解锁驱动器并完成启动过程后执行其他步骤。 在 WinRE 模式中，打开命令提示符，然后使用**manage-bde**工具解密驱动器。 使用此工具的唯一方法是删除没有原始 TPM 芯片的 TPM 加针保护。

5.  删除完成后，正常启动系统。 MBAM 代理将继续实施策略，以使用新计算机的 TPM 加针加密驱动器。

## 相关主题


[使用 MBAM 执行 BitLocker 管理](performing-bitlocker-management-with-mbam.md)

 

 





