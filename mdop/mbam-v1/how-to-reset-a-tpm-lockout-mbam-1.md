---
title: 如何重置 TPM 锁定
description: 如何重置 TPM 锁定
author: dansimp
ms.assetid: 91ec6666-1ae2-4e76-9459-ad65c405f639
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dde77a12e97d050777dac15d4106124ec111b3cd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798166"
---
# 如何重置 TPM 锁定


Microsoft BitLocker 管理和监视（MBAM）的加密驱动器恢复功能包括数据捕获和存储以及管理受信任的平台模块（TPM）所需的工具的可用性。 本主题介绍了如何在 "位 _admmon \ _tlanextref 管理" 网站中访问集中的密钥恢复数据系统。 密钥恢复数据系统可以在提供计算机标识和关联的用户标识符时提供 TPM 所有者密码文件。

如果用户输入错误 PIN 的次数过多，可能会发生 TPM 锁定。 在 TPM 锁定之前，用户可以输入不正确的 PIN 的次数基于计算机制造商的规范。

**重置 TPM 锁定**

1.  打开 MBAM 管理网站。

2.  在导航窗格中，选择 "**管理 TPM**"。 这将打开 "**管理 TPM** " 页面。

3.  输入计算机和计算机名称的完全限定的域名（FQDN）。 输入用户的 Windows 登录域和用户的用户名。 在 "**请求 TPM 所有者密码文件**" 下拉菜单的原因中，选择一个预定义选项。 单击**提交**。

4.  MBAM 将返回下列内容之一：

    -   找不到匹配的 TPM 所有者密码文件时出现的错误消息

    -   已提交计算机的 TPM 所有者密码文件

    **注意** 如果您是高级帮助台用户，则不需要 "用户域" 和 "用户 ID" 字段。

     

5.  检索时，将显示所有者密码。 若要将此密码保存到 tpm 文件，请单击 "**保存**" 按钮。

6.  用户将运行 TPM 管理控制台并选择 "**重置 tpm 锁定**" 选项，并提供 tpm 所有者密码文件以重置 tpm 锁定。

## 相关主题


[使用 MBAM 执行 BitLocker 管理](performing-bitlocker-management-with-mbam.md)

 

 





