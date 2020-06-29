---
title: 如何重置 TPM 锁定
description: 如何重置 TPM 锁定
author: dansimp
ms.assetid: 20719ab2-18ae-4d3b-989a-539341909816
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6453473ec09c2033346c7e464c08dbfdfe046d47
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803691"
---
# 如何重置 TPM 锁定


Microsoft BitLocker 管理和监视（MBAM）的加密驱动器恢复功能包括数据捕获和存储以及管理受信任的平台模块（TPM）所需的工具的可用性。 本主题介绍了如何在 "管理和监视" 网站中访问集中的密钥恢复数据系统，该系统可以在提供计算机 ID 和关联的用户标识符时提供 TPM 所有者密码文件。

如果用户输入错误 PIN 的次数过多，可能会发生 TPM 锁定。 用户在 TPM 锁定之前可以输入不正确的 PIN 的次数因制造商而异。

只有当 MBAM 拥有 TPM 时，才能重置 TPM 锁定。

**重置 TPM 锁定**

1.  打开 web 浏览器并导航到 "管理和监视" 网站。

2.  在左侧导航窗格中，选择 "**管理 tpm** " 以打开 "**管理 tpm** " 页面。

3.  输入计算机和计算机名的完全限定的域名，并输入用户的 Windows 登录域和用户的用户名以检索 TPM 所有者密码文件。

4.  从 "**请求 TPM 所有者密码文件**" 列表的原因中，选择请求的原因，然后单击 "**提交**"。

    MBAM 返回以下值之一：

    -   如果找不到匹配的 TPM 所有者密码文件，则出现错误消息

    -   已提交计算机的 TPM 所有者密码文件

    **注意**  
    如果您是高级帮助台用户，则不需要 "用户域" 和 "用户 ID" 字段。



~~~
After the TPM owner password is retrieved, the owner password is displayed.
~~~

5. 若要将密码保存到 tpm 文件，请单击 "**保存**" 按钮。

   用户将运行 TPM 管理控制台，选择 "**重置 tpm 锁定**" 选项，并提供 tpm 所有者密码文件以重置 tpm 锁定。

   **重要提示**  
   技术支持管理员不应将 TPM 哈希值或 TPM 所有者密码文件授予最终用户。 TPM 信息不会更改，因此如果向最终用户提供该文件，则可能会带来安全风险。



## 相关主题


[使用 MBAM 执行 BitLocker 管理](performing-bitlocker-management-with-mbam-mbam-2.md)









