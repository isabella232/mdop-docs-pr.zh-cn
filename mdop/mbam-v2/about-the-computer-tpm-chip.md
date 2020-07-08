---
title: 关于计算机 TPM 芯片
description: 关于计算机 TPM 芯片
author: dansimp
ms.assetid: 6f1cf18c-277a-4932-886d-14202ca8d175
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f6df54dc8085c398bacc508fdbbb79a30b0e4204
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803387"
---
# 关于计算机 TPM 芯片


BitLocker 在与受信任的平台模块（TPM）芯片配合使用时提供附加保护。 TPM 芯片是计算机制造商在许多较新计算机上安装的硬件组件。 Microsoft BitLocker 管理和监视（MBAM）除了 TPM 芯片之外，还使用 BitLocker 来帮助对你的数据提供额外保护，并确保你的计算机未被篡改。

## 如何设置 TPM


当你在计算机上启动 BitLocker 驱动器加密向导时，如果你的组织已将 BitLocker 配置为使用 TPM 芯片，BitLocker 将检查 TPM 芯片。 如果 BitLocker 找到兼容的 TPM 芯片，系统可能会提示你重启计算机，以使 TPM 芯片可供使用。 一旦计算机重新启动，请按照说明在 BIOS 中配置 TPM 芯片（BIOS 是计算机软件的 Windows 安装层）。

配置 BitLocker 后，您可以通过打开 Windows "控制面板" 中的 "BitLocker 加密选项" 工具，然后选择 " **TPM 管理**" 来访问有关 TPM 芯片的其他信息。

**注意** 您必须拥有计算机的管理凭据才能访问此工具。

 

在 TPM 故障、BIOS 中的更改或某些 Windows 更新中，BitLocker 将锁定你的计算机，并要求你与你的技术支持人员联系以解除锁定。 您必须提供计算机的名称以及计算机的域。 技术支持人员可以为你提供密码文件，该文件可用于解锁你的计算机。

## TPM 问题疑难解答


如果 TPM 故障、在 BIOS 中发生更改或发生某些 Windows 更新，BitLocker 将锁定您的计算机，并要求您与您的技术支持人员联系以解除锁定。 您必须提供计算机的名称以及计算机的域。 技术支持人员可以为您提供一个密码文件，您可以使用该文件解锁您的计算机。

## 相关主题


[帮助最终用户管理 BitLocker](helping-end-users-manage-bitlocker.md)

[使用 PIN 或密码](using-your-pin-or-password.md)

 

 





