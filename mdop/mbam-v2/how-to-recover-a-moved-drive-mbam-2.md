---
title: 如何恢复已移动的驱动器
description: 如何恢复已移动的驱动器
author: dansimp
ms.assetid: 697cd78d-962c-411e-901a-2e9220ba6552
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: bd0d43f2eea95fe71225a50e7fa68d4fb1c35485
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803693"
---
# 如何恢复已移动的驱动器


当你移动使用 Microsoft BitLocker 管理和监视（MBAM）加密的操作系统驱动器时，由于受信任的平台模块（TPM）芯片发生更改，因此驱动器不会接受以前计算机中使用的 PIN。 若要使用移动的驱动器，你将需要获取恢复密钥 ID 以检索恢复密码的方法。 使用以下过程恢复已移动的驱动器。

**恢复移动的驱动器**

1.  在包含已移动的驱动器的计算机上，在 Windows 恢复环境（WinRE）模式下启动计算机，或使用 Microsoft 诊断和恢复工具集（DaRT）启动计算机。

2.  当计算机使用 WinRE 或 DaRT 启动后，Microsoft BitLocker 管理和监视会将移动的操作系统驱动器视为数据驱动器。 MBAM 将显示驱动器的恢复密码 ID 并要求输入恢复密码。

    **注意** 在某些情况下，你可能可以在启动过程中单击 "**我忘记了 PIN** "，然后输入恢复模式以显示恢复密钥 ID。

     

3.  使用恢复密钥 ID 检索恢复密码并通过管理和监视网站解锁驱动器。

4.  如果移动的驱动器配置为使用原始计算机上的 TPM 芯片，则必须在解锁驱动器并完成启动过程后执行其他步骤。 在 WinRE 模式中，打开命令提示符，然后使用**manage-bde**工具解密驱动器。 使用此工具是删除 TPM 以及不使用原始 TPM 芯片的 PIN 保护器的唯一方法。

5.  删除完成后，正常启动计算机。 MBAM 代理现在将强制策略使用新计算机的 TPM 和 PIN 加密驱动器。

## 相关主题


[使用 MBAM 执行 BitLocker 管理](performing-bitlocker-management-with-mbam-mbam-2.md)

 

 





