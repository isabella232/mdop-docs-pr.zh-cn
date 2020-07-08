---
title: 如何恢复已损坏的驱动器
description: 如何恢复已损坏的驱动器
author: dansimp
ms.assetid: 715491ae-69c0-4fae-ad3f-3bd19a0db2f2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 545ff5c7e6bea29d5f89cce1cf18212b7d0e2870
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798172"
---
# 如何恢复已损坏的驱动器


若要恢复受 BitLocker 保护的损坏的驱动器，Microsoft BitLocker 管理和监视（MBAM）技术支持用户必须创建恢复密钥包文件。 此程序包文件可以复制到包含损坏的驱动器的计算机，然后用于恢复驱动器。 若要实现此目的，请使用以下过程。

**恢复损坏的驱动器**

1.  打开 MBAM 管理网站。

2.  从导航窗格中选择 "**驱动器恢复**"。 输入用户的域名和用户名、解锁驱动器的原因以及用户的恢复密码 ID。

    **注意** 如果您是技术支持管理员角色的成员，则无需输入用户的域名或用户名。

     

3.  单击**提交**。 将显示恢复密钥。

4.  单击 "**保存**"，然后选择 "**恢复密钥包**"。 将在你的计算机上创建恢复密钥包。

5.  将恢复密钥包复制到包含损坏的驱动器的计算机。

6.  打开提升的命令提示符。 若要执行此操作，请单击 "**开始**"，然后 `cmd` 在 "**搜索程序和文件**" 框中键入。 在 "搜索结果" 列表中，右键单击**cmd.exe** ，然后选择 "**以管理员身份运行**"。

7.  在命令提示符处，键入以下内容：

    `repair-bde <fixed drive> <corrupted drive> -kp <location of keypackage> -rp <recovery password>`

    **注意** 对于该 &lt; 命令中的固定驱动器 &gt; ，请指定一个可用的存储设备，该设备的可用空间等于或大于损坏的驱动器上的数据。 已损坏的驱动器上的数据将恢复并移动到指定的固定驱动器。

     

## 相关主题


[使用 MBAM 执行 BitLocker 管理](performing-bitlocker-management-with-mbam.md)

 

 





