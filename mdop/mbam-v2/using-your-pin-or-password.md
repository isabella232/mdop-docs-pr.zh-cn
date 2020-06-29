---
title: 使用 PIN 或密码
description: 使用 PIN 或密码
author: dansimp
ms.assetid: 7fe2aef4-d3e0-49c8-877d-7fee13dc5b7b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b8c4b894b8f3e14d2a5cfb39e744fa43874c6753
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803439"
---
# 使用 PIN 或密码


BitLocker 通过要求使用个人识别码（PIN）或密码解锁计算机上存储的信息来帮助保护计算机的安全。 PIN 或密码要求由你的组织设置，并取决于要加密的驱动器类型。 在未输入 PIN 或密码的情况下，无法查看加密驱动器上的数据。 如果你的计算机硬件包含启用的受信任平台模块（TPM），则 TPM 芯片会在你的计算机上启动 Windows 之前提示你输入 PIN。

## 关于您的 BitLocker PIN 和密码


您的公司指定 PIN 或密码所需的复杂程度。 在 BitLocker 设置过程中，将介绍这些对 PIN 或密码的要求。

密码用于解锁计算机上不包含操作系统的驱动器。 在启动期间请求 PIN 后，BitLocker 将询问你的密码。 计算机上的每个受 BitLocker 保护的硬盘都有自己的唯一密码。 无法解锁受 BitLocker 保护的驱动器，直到你提供密码。

**注意** 您的技术支持人员可能会将驱动器设置为自动解锁。 这样便无需提供 PIN 或密码即可查看驱动器上的信息。

 

## 如果忘记了 PIN 或密码，请解锁你的计算机


如果您忘记了 PIN 或密码，您的技术支持人员可以帮助您解锁受 BitLocker 保护的驱动器。 若要解除锁定使用 BitLocker 保护的驱动器，请与您的技术支持人员联系（如果需要帮助）。

**如果忘记了 PIN 或密码，如何解锁你的计算机**

1.  当您与技术支持人员联系时，您需要向他们提供以下信息：

    -   您的用户名

    -   您的域

    -   恢复密钥 ID 的前八位数字。 这是32位的代码，如果你忘记 PIN 或密码，将显示 BitLocker。

        -   如果您忘记了 PIN，则必须输入恢复密钥 ID 的前八位数字，它将显示在 BitLocker 恢复控制台中。 BitLocker 恢复控制台是 Windows 内置屏幕，如果不输入正确的 PIN 码，将显示该屏幕。

        -   如果您忘记了密码，请在 "BitLocker 加密选项" 控制面板应用程序中查找恢复密钥 ID。 选择 "**解锁驱动器**"，然后单击 "**我不记得我的密码**"。 然后，BitLocker "加密选项" 应用程序将显示您提供给帮助台的恢复密钥 ID。

2.  技术支持人员收到必要的信息后，将通过手机或通过电子邮件向你提供恢复密钥。

    -   如果忘记了 PIN，请在 BitLocker 恢复控制台中输入恢复密钥以解锁你的计算机。

    -   如果您忘记了密码，请在 "BitLocker 加密选项" 控制面板应用程序中输入恢复密钥，在您之前找到恢复密钥 ID 的同一位置。 这将解锁受保护的硬盘。

## 更改 PIN 或密码


必须先解锁驱动器，然后才能更改受 BitLocker 保护的驱动器上的密码。 如果驱动器未解锁，请选择 "**解锁驱动器**"，然后输入您的当前密码。 解锁驱动器后，您可以选择 "**管理密码**" 以更改当前密码。

**如何更改 PIN 或密码**

1.  单击 "**开始**"，然后选择 **"控制面板"**。 将在新窗口中打开 "控制面板"。

2.  选择 "**系统和安全**"，然后选择 " **BitLocker 加密选项**"。

    -   若要更改 PIN，请选择 "**管理你的 pin**"。 在两个字段中键入新的 PIN 码，然后选择 "**重置 PIN**"。

    -   若要更改密码，请选择 "**管理密码**"。 在两个字段中输入新密码，然后选择 "**重置密码**"。

 

 





