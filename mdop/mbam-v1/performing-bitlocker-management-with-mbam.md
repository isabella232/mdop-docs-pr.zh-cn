---
title: 使用 MBAM 执行 BitLocker 管理
description: 使用 MBAM 执行 BitLocker 管理
author: dansimp
ms.assetid: 2d24390a-87bf-48b3-96a9-3882d6f2a15c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8d0de3711d5b7c3696783a054ee7c7f8220b5356
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803859"
---
# 使用 MBAM 执行 BitLocker 管理


部署 Microsoft BitLocker 管理和监视（MBAM）后，你可以配置和使用 MBAM 管理企业 BitLocker 加密。 本节介绍了可通过使用 MBAM 完成的安装后、日常 BitLocker 加密管理任务。

## 使用 MBAM 重置 TPM 锁定


受信任的平台模块（TPM）微芯片提供与安全相关的基本功能。 这些函数主要通过使用加密密钥来完成。 TPM 通常安装在计算机或笔记本电脑的主板上，通过使用硬件总线与系统的其余部分进行通信。 合并 TPM 的计算机可以创建只能由 TPM 解密的加密密钥。 如果用户输入错误 PIN 的次数过多，可能会发生 TPM 锁定。 用户在 TPM 锁定之前可以输入不正确的 PIN 的次数因制造商而异。 MBAM 管理网站上的密钥恢复数据系统使你能够获取重置 TPM 所有者密码文件。

[如何重置 TPM 锁定](how-to-reset-a-tpm-lockout-mbam-1.md)

## 通过 MBAM 恢复驱动器


请确保你知道在硬件故障、人员的更改或加密密钥丢失的其他情况下，如何尝试从加密的驱动器恢复数据。 MBAM 的加密驱动器恢复功能提供了访问受 BitLocker 保护的卷的数据和可用性所需的工具的捕获和存储，以便在卷进入恢复模式、移动或损坏时访问受 BitLocker 保护的卷。

[如何在恢复模式下恢复驱动器](how-to-recover-a-drive-in-recovery-mode-mbam-1.md)

[如何恢复已移动的驱动器](how-to-recover-a-moved-drive-mbam-1.md)

[如何恢复已损坏的驱动器](how-to-recover-a-corrupted-drive-mbam-1.md)

## 使用 MBAM 确定丢失的计算机的 BitLocker 加密状态


使用 MBAM 时，你可以确定丢失或被盗的计算机的上次已知 BitLocker 加密状态。

[如何确定丢失计算机的 BitLocker 加密状态](how-to-determine-the-bitlocker-encryption-state-of-a-lost-computers-mbam-1.md)

## 用于通过 MBAM 执行 BitLocker 管理的其他资源


[MBAM 1.0 的操作](operations-for-mbam-10.md)

 

 





