---
title: 使用 MBAM 执行 BitLocker 管理
description: 使用 MBAM 执行 BitLocker 管理
author: dansimp
ms.assetid: 9bfc6c67-f12c-4daa-8f08-5884fb47443c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d261ec4fa789cd331209afe1c2f1858d627209a3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803980"
---
# 使用 MBAM 执行 BitLocker 管理


在规划并部署 Microsoft BitLocker 管理和监视（MBAM）之后，你可以配置和使用它来管理企业 BitLocker 加密。 本部分中的信息介绍了通过使用 Microsoft BitLocker 管理和监视来完成的安装后的每天 BitLocker 加密管理任务。

## 使用 MBAM 重置 TPM 锁定


受信任的平台模块（TPM）是一种微芯片，旨在提供基本的与安全相关的功能，主要涉及加密密钥。 TPM 通常安装在计算机或笔记本电脑的主板上，并通过使用硬件总线与系统的其余部分进行通信。 合并 TPM 的计算机能够创建加密密钥并对其进行加密，以便仅可由 TPM 解密。

如果用户输入错误 PIN 的次数过多，可能会发生 TPM 锁定。 用户在 TPM 锁定之前可以输入不正确的 PIN 的次数因制造商而异。 你可以使用 MBAM 访问 "管理和监视" 网站中的集中式密钥恢复数据系统，在此情况下，你可以在提供计算机 ID 和关联的用户标识符时检索 TPM 所有者密码文件。

[如何重置 TPM 锁定](how-to-reset-a-tpm-lockout-mbam-2.md)

## 通过 MBAM 恢复驱动器


当处理数据加密时（尤其是在企业环境中），请考虑在硬件故障、人员更改或可能会丢失加密密钥的其他情况下如何恢复数据。

MBAM 的加密驱动器恢复功能确保可以捕获和存储数据，并且在 BitLocker 转到恢复模式时，可以使用所需的工具访问受 BitLocker 保护的卷，或者将其移动或损坏。

[如何在恢复模式下恢复驱动器](how-to-recover-a-drive-in-recovery-mode-mbam-2.md)

[如何恢复已移动的驱动器](how-to-recover-a-moved-drive-mbam-2.md)

[如何恢复已损坏的驱动器](how-to-recover-a-corrupted-drive-mbam-2.md)

## 使用 MBAM 确定丢失的计算机的 BitLocker 加密状态


使用 MBAM，你可以确定丢失或被盗的计算机的上次已知 BitLocker 加密状态。

[如何确定丢失计算机的 BitLocker 加密状态](how-to-determine-bitlocker-encryption-state-of-lost-computers-mbam-2.md)

## 使用自助服务门户重新获取对计算机的访问权限


如果最终用户通过 BitLocker 从 Windows 中被锁定，则他们可以使用本部分中的说明获取 BitLocker 恢复密钥，以重新获得其计算机的访问权限。

[如何使用自助服务门户重获计算机访问权限](how-to-use-the-self-service-portal-to-regain-access-to-a-computer.md)

## 用于通过 MBAM 执行 BitLocker 管理的其他资源


[MBAM 2.0 的操作](operations-for-mbam-20-mbam-2.md)

 

 





