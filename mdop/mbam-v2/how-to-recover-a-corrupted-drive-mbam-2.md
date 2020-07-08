---
title: 如何恢复已损坏的驱动器
description: 如何恢复已损坏的驱动器
author: dansimp
ms.assetid: b0457a00-f72e-4ad8-ab3b-7701851ca87e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5bbd4c2a1f5ef3fde78a9f72c1f77ccb0cdea377
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803255"
---
# 如何恢复已损坏的驱动器


若要恢复受 BitLocker 保护的损坏的驱动器，Microsoft BitLocker 管理和监视（MBAM）技术支持用户将需要创建恢复密钥包文件。 然后，可以将此程序包文件复制到包含损坏的驱动器的计算机，然后用于恢复驱动器。 对于执行此操作所需的步骤，请使用以下过程。

**重要提示** 为了避免潜在的数据丢失，强烈建议你阅读 "manage-bde" 帮助并清楚了解如何使用该命令，然后再完成以下说明。

 

**恢复损坏的驱动器**

1.  若要创建恢复已损坏的驱动器所需的恢复密钥包，请启动 web 浏览器并打开 MBAM 管理和监视网站。

2.  从左侧导航窗格中选择 "**驱动器恢复**"。 输入用户的域名、用户名、解锁驱动器的原因以及用户的恢复密码 ID。

    **注意** 如果您是技术支持管理员角色的成员，则无需输入用户的域名或用户名。

     

3.  单击**提交**。 将显示恢复密钥。

4.  单击 "**保存**"，然后选择 "**恢复密钥包**"。 将在你的计算机上创建恢复密钥包。

5.  将恢复密钥包复制到包含损坏的驱动器的计算机。

6.  打开提升的命令提示符。 若要执行此操作，请单击 "**开始**"，然后 `cmd` 在 "**搜索程序和文件" 框**中键入。 右键单击**cmd.exe** ，然后选择 "**以管理员身份运行**"。

7.  在命令提示符处，键入以下内容：

    `repair-bde <corrupted drive> <fixed drive> -kp <location of keypackage> -rp <recovery password>`

    **注意** &lt;将固定驱动器替换 &gt; 为具有等于或大于损坏的驱动器上的数据的可用硬盘空间。 已损坏的驱动器上的数据将恢复并移动到指定的硬盘驱动器。

     

## 相关主题


[使用 MBAM 执行 BitLocker 管理](performing-bitlocker-management-with-mbam-mbam-2.md)

 

 





