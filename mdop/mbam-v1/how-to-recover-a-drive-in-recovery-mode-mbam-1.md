---
title: 如何在恢复模式下恢复驱动器
description: 如何在恢复模式下恢复驱动器
author: dansimp
ms.assetid: 09d27e4b-57fa-47c7-a004-8b876a49f27e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c1151ffe7453eb8d07d2aa6dcb4c41f6b3efe6de
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798174"
---
# 如何在恢复模式下恢复驱动器


Microsoft BitLocker 管理和监视（MBAM）包括加密的驱动器恢复功能。 当 BitLocker 将该卷置于恢复模式时，这些功能可确保捕获和存储访问受 BitLocker 保护的卷所需的工具的数据和可用性。 当丢失或忘记 PIN 或密码时，或者当受信任的模块平台（TPM）芯片检测到计算机的 BIOS 或启动文件的更改时，受 BitLocker 保护的卷将进入恢复模式。

使用此过程访问可在提供恢复密码 ID 和关联的用户标识符时提供恢复密码的集中密钥恢复数据系统。

**重要提示** MBAM 生成单一使用恢复密钥。 在此限制下，只能使用一个恢复密钥一次，然后它将不再有效。 恢复密码的单个用途将自动应用于操作系统驱动器和固定驱动器。 在可移动驱动器上，当删除驱动器，然后在已激活组策略设置以管理可移动驱动器的计算机上重新插入和解除锁定时，将应用单一使用。

 

**在恢复模式下恢复驱动器**

1.  打开 MBAM 网站。

2.  在导航窗格中，单击 "**驱动器恢复**"。 将打开 "**恢复对加密驱动器的访问**" 网页。

3.  输入用户的 Windows 登录域和用户名以及恢复密钥 ID 的前八位数字，以接收可能匹配的恢复密钥的列表。 或者，输入整个恢复密钥 ID 以接收准确的恢复密钥。 在 "**驱动器解锁的原因**" 下拉列表中选择预定义选项之一，然后单击 "**提交**"。

    **注意** 如果你是 MBAM 高级帮助台用户，则不需要用户域和用户 ID 条目。

     

4.  MBAM 返回以下内容：

    1.  找不到匹配的恢复密码时出现的错误消息

    2.  如果用户具有多个匹配的恢复密码，则可以进行多个可能的匹配

    3.  已提交用户的恢复密码和恢复程序包

        **注意** 如果要恢复损坏的驱动器，恢复包选项会提供 BitLocker，其中包含尝试恢复所必需的关键信息。

         

5.  检索恢复密码和恢复程序包后，将显示恢复密码。 若要复制密码，请单击 "**复制密钥**"，然后将恢复密码粘贴到电子邮件或其他文本文件中以进行临时存储。 或者，要将恢复密码保存到文件中，请单击 "**保存**"。

6.  当用户在系统中键入恢复密码或使用恢复包时，驱动器将解锁。

## 相关主题


[使用 MBAM 执行 BitLocker 管理](performing-bitlocker-management-with-mbam.md)

 

 





