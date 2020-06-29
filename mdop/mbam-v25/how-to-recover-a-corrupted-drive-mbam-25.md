---
title: 如何恢复已损坏的驱动器
description: 如何恢复已损坏的驱动器
author: dansimp
ms.assetid: fa5b846b-dda6-4ae4-bf6c-39e4f1d8aa00
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: fd9fd8a65d57cbfe965197fa26b57319ee046784
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803191"
---
# 如何恢复已损坏的驱动器


你可以将此过程与管理和监视网站（也称为帮助桌面）网站结合使用，以恢复受 BitLocker 保护的损坏的驱动器。 若要执行此操作，您将完成下表中列出的任务。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">任务</th>
<th align="left">详细信息和详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>通过访问 <strong> </strong> 管理和监视网站的驱动器恢复区域来创建恢复密钥包文件。</p></td>
<td align="left"><p>要访问 <strong> 驱动器恢复 </strong> 区域，你必须被分配 MBAM 帮助台用户角色或 MBAM 高级帮助台用户角色。 创建这些角色时，可能会为这些角色指定不同的名称。 有关详细信息，请参阅 <a href="planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles" data-raw-source="[Planning for MBAM 2.5 Groups and Accounts](planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles)"> 规划 MBAM 2.5 组和帐户 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>将程序包文件复制到包含损坏的驱动器的计算机。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>使用 <code>repair-bde</code> 命令完成恢复过程。</p></td>
<td align="left"><p>为了避免可能丢失数据，强烈建议你 <a href="https://go.microsoft.com/fwlink/?LinkId=393567" data-raw-source="[Manage-bde](https://go.microsoft.com/fwlink/?LinkId=393567)"> 先查看 manage-bde </a> 命令，然后再使用它。</p></td>
</tr>
</tbody>
</table>

 

**恢复损坏的驱动器**

1.  打开 web 浏览器并导航到 "**管理和监视" 网站**。

2.  在左窗格中，选择 "**驱动器恢复**" 以打开 "**恢复对加密驱动器的访问**" 页面。

3.  输入最终用户的 Windows 登录域和用户名、解锁驱动器的原因以及最终用户的恢复密码 ID。

    **注意** 如果您是 "高级帮助台用户" 访问组的成员，则无需输入用户的域名或用户名。

     

4.  单击**提交**。 将显示恢复密钥。

5.  单击 "**保存**"，然后选择 "**恢复密钥包**"。 将在你的计算机上创建恢复密钥包。

6.  将恢复密钥包复制到包含损坏的驱动器的计算机。

7.  打开提升的命令提示符。 若要执行此操作，请单击 "**开始**"，然后 `cmd` 在 "**搜索程序和文件**" 文本框中键入。 右键单击**cmd.exe**，然后选择 "**以管理员身份运行**"。

8.  在命令提示符处，键入以下内容：

    `repair-bde <corrupted drive> <fixed drive> -kp <location of keypackage> -rp <recovery password>`

    **注意** 将 &lt; *固定驱动器*替换 &gt; 为具有等于或大于损坏的驱动器上的数据的可用硬盘空间。 已损坏的驱动器上的数据将恢复并移动到指定的硬盘驱动器。

     


## 相关主题


[使用 MBAM 2.5 执行 BitLocker 管理](performing-bitlocker-management-with-mbam-25.md)

 
## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。
 





