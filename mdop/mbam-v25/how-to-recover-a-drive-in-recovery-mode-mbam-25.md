---
title: 如何在恢复模式下恢复驱动器
description: 如何在恢复模式下恢复驱动器
author: dansimp
ms.assetid: e126eaf8-9ae7-40fe-a28e-dbd78d26859e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d15f33f461e60fceeed3acbce3a0c82b02b56f98
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803354"
---
# 如何在恢复模式下恢复驱动器


本主题介绍了如何使用管理和监视网站（也称为帮助桌面）获取恢复密码，以便在其受 BitLocker 保护的驱动器进入恢复模式时向最终用户提供。 如果用户丢失或忘记了其 PIN 或密码，或者受信任的模块平台（TPM）芯片检测到计算机的 BIOS 或启动文件发生更改，则驱动器将进入恢复模式。

若要获取恢复密码，请使用管理和监视网站的**驱动器恢复**区域。 你必须被分配 MBAM 帮助台用户角色或 MBAM 高级帮助台用户角色才能访问该网站的此区域。

**注意**  
创建这些角色时，可能会为这些角色指定不同的名称。 有关详细信息，请参阅[规划 MBAM 2.5 组和帐户](planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles)。



**重要提示**  
恢复密码在一次使用后过期。 在操作系统驱动器和固定数据驱动器上，自动应用单一使用规则。 在可移动驱动器上，当驱动器被删除，然后在已激活组策略设置以管理可移动驱动器的计算机上重新插入和解锁时，将应用该驱动器。



**在恢复模式下恢复驱动器**

1.  打开 web 浏览器并导航到 "**管理和监视" 网站**。

2.  在左窗格中，选择 "**驱动器恢复**" 以打开 "**恢复对加密驱动器的访问**" 页面。

3.  输入最终用户的 Windows 登录域和用户名以查看恢复信息。

    **注意**  
    如果您在 MBAM 高级帮助台用户组中，则不需要 "用户域" 和 "用户 ID" 字段。



4.  输入恢复密钥 ID 的前八位数字以查看可能匹配的恢复密钥的列表，或输入整个恢复密钥 ID 以获取准确的恢复密钥。

5.  从 "**驱动器解锁**" 列表中，选择一个预定义的选项，然后单击 "**提交**"。

    MBAM 返回以下内容：

    -   找不到匹配的恢复密码时出现的错误消息

    -   如果用户具有多个匹配的恢复密码，则可以进行多个可能的匹配

    -   已提交用户的恢复密码和恢复程序包

        **注意**  
        如果要恢复损坏的驱动器，恢复包选项将提供 BitLocker，其中包含恢复驱动器所需的关键信息。



~~~
After the recovery password and recovery package are retrieved, the recovery password is displayed.
~~~

6. 若要复制密码，请单击 "**复制密钥**"，然后将恢复密码粘贴到电子邮件中。 或者，单击 "**保存**" 以将恢复密码保存到文件。

   当用户在系统中键入恢复密码或使用恢复包时，驱动器将解锁。



## 相关主题


[使用 MBAM 2.5 执行 BitLocker 管理](performing-bitlocker-management-with-mbam-25.md)



## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





