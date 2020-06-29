---
title: 如何重置 TPM 锁定
description: 如何重置 TPM 锁定
author: dansimp
ms.assetid: dd20a728-c52e-48e6-9f6c-1311c71dee74
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f5aea277e80c54fb01d1a6c00b62f0c617d1ad12
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803345"
---
# 如何重置 TPM 锁定


本主题介绍了如何使用管理和监视网站（也称为帮助桌面）重置 TPM 锁定。 如果最终用户输入错误 PIN 的次数过多，可能会发生 TPM 锁定。 用户在 TPM 锁定之前可以输入不正确的 PIN 的次数因制造商而异。

在管理和监视网站的 "**管理 TPM** " 区域中，你可以访问集中密钥恢复数据系统，该系统在你提供计算机 ID 和关联的用户标识符时提供 TPM 所有者密码文件。

若要访问管理和监视网站的 "管理 TPM" 区域，你必须分配 MBAM 帮助台用户角色或 MBAM 高级帮助台用户角色。 这些角色是管理员在 Active Directory 中创建的组。 你可以为这些组使用任何名称。 有关详细信息，请参阅[规划 MBAM 2.5 组和帐户](planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles)。

有关 MBAM 和 TPM 所有权的信息，请参阅[MBAM 2.5 安全注意事项](mbam-25-security-considerations.md#bkmk-tpm)。

**重置 TPM 锁定**

1.  打开 web 浏览器并导航到 "**管理和监视" 网站**。

2.  在左窗格中，单击 "**管理 tpm** " 以打开 "**管理 tpm** " 页面。

3.  输入计算机和计算机名称的完全限定的域名。

4.  输入最终用户的 Windows 登录域和用户名以检索 TPM 所有者密码文件。

    **注意** 如果您在 MBAM 高级帮助台用户组中，则不需要 "用户域" 和 "用户 ID" 字段。

     

5.  从 "**请求 TPM 所有者密码文件**" 列表的原因中，选择请求的原因，然后单击 "**提交**"。

    MBAM 返回以下值之一：

    -   找不到匹配的 TPM 所有者密码文件时出现的错误消息

    -   已提交计算机的 TPM 所有者密码文件

    检索 TPM 所有者密码后，将显示所有者密码。

6.  若要将密码保存到 tpm 文件，请单击 "**保存**" 按钮。

7.  在**管理和监视网站**的 "**管理 tpm** " 区域中，选择 "**重置 tpm 锁定**" 选项并提供 TPM 所有者密码文件。

    将重置 TPM 锁定，并还原最终用户的访问权限。

    **重要提示** 不要向最终用户提供 TPM 哈希值或 TPM 所有者密码文件。 由于 TPM 信息不会更改，因此为最终用户提供文件会带来安全风险。

     



## 相关主题


[使用 MBAM 2.5 执行 BitLocker 管理](performing-bitlocker-management-with-mbam-25.md)

 

## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





