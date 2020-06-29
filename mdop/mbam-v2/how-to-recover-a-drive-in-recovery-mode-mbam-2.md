---
title: 如何在恢复模式下恢复驱动器
description: 如何在恢复模式下恢复驱动器
author: dansimp
ms.assetid: 8b792bc8-b671-4345-9d37-0208db3e5b03
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7d5ce509599d0eb800a71360e3be9d0fa3b33f4f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803692"
---
# 如何在恢复模式下恢复驱动器


Microsoft BitLocker 管理和监视（MBAM）的加密驱动器恢复功能可确保在 BitLocker 进入恢复模式时访问受 BitLocker 保护的卷所需的数据和可用工具的捕获和存储。 当丢失或忘记 PIN 或密码，或者当受信任模块平台（TPM）芯片检测到计算机的 BIOS 或启动文件更改时，受 BitLocker 保护的卷将进入恢复模式。

使用此过程访问集中的密钥恢复数据系统，如果提供了恢复密码 ID 和关联的用户标识符，该系统可以提供恢复密码。

**重要提示**  
Microsoft BitLocker 管理和监视使用在使用时过期的单一使用恢复密钥。 恢复密码的单个用途将自动应用于操作系统驱动器和固定驱动器。 在可移动驱动器上，当删除驱动器，然后在已激活组策略设置以管理可移动驱动器的计算机上重新插入和解除锁定时，将应用该驱动器。



**在恢复模式下恢复驱动器**

1.  打开 web 浏览器并导航到 "管理和监视" 网站。

2.  在导航窗格中，单击 "**驱动器恢复**"。 "恢复对加密驱动器的访问" 网页随即打开。

3.  输入用户的 Windows 登录域和用户名以查看恢复信息，以及恢复密钥 ID 的前八位数字，以接收可能匹配的恢复密钥的列表或整个恢复密钥 ID 以接收准确的恢复密钥。

4.  从 "**驱动器解锁的原因**" 列表中选择一个预定义选项，然后单击 "**提交**"。

    **注意**  
    如果你是 MBAM 高级帮助台用户，则不需要用户域和用户 ID 条目。



~~~
MBAM returns the following:

-   An error message if no matching recovery password is found

-   Multiple possible matches if the user has multiple matching recovery passwords

-   The recovery password and recovery package for the submitted user

    **Note**  
    If you are recovering a damaged drive, the recovery package option provides BitLocker with critical information that it needs to recover the drive.



After the recovery password and recovery package are retrieved, the recovery password is displayed.
~~~

5. 若要复制密码，请单击 "**复制密钥**"，然后将恢复密码粘贴到电子邮件中。 或者，单击 "**保存**" 以将恢复密码保存到文件。

   当用户在系统中键入恢复密码或使用恢复包时，驱动器将解锁。

## 相关主题


[使用 MBAM 执行 BitLocker 管理](performing-bitlocker-management-with-mbam-mbam-2.md)









