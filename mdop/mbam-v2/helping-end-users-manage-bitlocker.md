---
title: 帮助最终用户管理 BitLocker
description: 帮助最终用户管理 BitLocker
author: dansimp
ms.assetid: 47776fb3-2d94-4970-b687-c35ec3dd6c64
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 26ef2bc33a75ff7773b75807ab0e10e5aa67b109
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803636"
---
# 帮助最终用户管理 BitLocker


丢失或被盗计算机上的内容容易受到未经授权的访问，这可能会给人员和公司带来安全风险。 Microsoft BitLocker 管理和监视（MBAM）使用 BitLocker 通过锁定您的计算机帮助防止恶意用户的敏感数据，从而帮助防止未经授权的访问。

## 什么是 BitLocker？


通过加密驱动器，BitLocker 驱动器加密可以为操作系统驱动器、数据驱动器和可移动驱动器（如 USB 拇指驱动器）提供保护。 根据 BitLocker 的配置方式，用户可能必须提供密钥（密码或 PIN）才能解锁存储在加密驱动器上的信息。

将新文件添加到使用 BitLocker 加密的驱动器时，BitLocker 会自动对其进行加密。 文件仅在存储在加密驱动器中时保持加密。 将解密复制到其他驱动器或计算机的文件。 如果您与其他用户（如通过网络）共享文件，则这些文件会在存储在加密驱动器上时进行加密，但授权用户可以正常访问这些文件。

如果您加密操作系统驱动器，BitLocker 会在启动期间检查计算机是否存在可能表示安全风险的任何条件（例如，对 BIOS 的更改或对任何启动文件的更改）。 如果检测到潜在的安全风险，BitLocker 将锁定操作系统驱动器，并且需要使用特殊的 BitLocker 恢复密钥解锁。 请确保在首次打开 BitLocker 时创建此恢复密钥。 否则，您可能会永久失去对文件的访问权限。

如果加密数据驱动器（固定或可移动），则可以使用密码或智能卡解锁加密的驱动器，或者将驱动器设置为当您登录到计算机时自动解锁。

除了密码和 Pin，BitLocker 还可以使用在许多较新的计算机中提供的受信任的平台模块（TPM）芯片。 TPM 芯片用于确保你的计算机未被篡改，然后 BitLocker 将无法解锁操作系统驱动器。 在加密过程中，你可能需要启用 TPM 芯片。 当您启动计算机时，BitLocker 会向该驱动器中的密钥请求 TPM，并将其解除锁定。 若要启用 TPM 芯片，必须重新启动计算机，然后在 BIOS 中更改计算机软件的 Windows 之前的设置。 有关 TPM 的详细信息，请参阅[关于计算机 TPM 芯片](about-the-computer-tpm-chip.md)。

一旦你的计算机受 BitLocker 保护，你可能需要在计算机每次从休眠唤醒或启动时输入 PIN 或密码。 您的公司或组织的帮助台可帮助您忘记 PIN 或密码。

你可以通过解密驱动器来临时关闭 BitLocker，方法是暂停或永久关闭。

**注意** 由于 BitLocker 会对整个驱动器进行加密，而不仅仅是对单个文件进行加密，因此在驱动器之间移动敏感数据时要小心。 如果将文件从受 BitLocker 保护的驱动器移动到非加密驱动器，该文件将不再加密。

 

## 关于 BitLocker 加密选项应用程序


若要在计算机上解锁硬盘驱动器以及管理 PIN 和密码，请按照此处所述的步骤，使用 Windows 控制面板中的 BitLocker 加密选项应用程序。 你可以输入密码来解锁受保护的驱动器，并且可以使用此应用程序检查附加的驱动器的 BitLocker 状态。

**打开 "BitLocker 加密选项" 应用程序**

1.  单击 "**开始**"，然后选择 **"控制面板"**。 将在新窗口中打开 "控制面板"。

2.  在 "控制面板" 中，选择 **"****系统和安全**"。

3.  选择 " **Bitlocker 加密选项**" 以打开 "Bitlocker 加密选项" 应用程序。

    有关可用选项的说明，请参阅以下部分。

## BitLocker 加密选项应用程序上的选项


使用 "控制面板" 上的 "BitLocker 加密选项" 应用程序，你可以管理你的 PIN 和密码，BitLocker 使用此功能保护你的计算机。

**BitLocker 驱动器加密-固定磁盘驱动器：**

在此部分中，你可以查看有关连接到计算机的硬盘和当前 BitLocker 加密状态的信息。

-   **管理您的 PIN** -更改 BitLocker 使用的引脚以解锁操作系统驱动器。

-   **管理密码**-更改 BitLocker 用于解锁其他内部驱动器的密码。

**BitLocker 驱动器加密-外部驱动器：**

在此部分中，你可以查看连接到计算机的外部驱动器（如 USB 拇指驱动器）的信息，以及其当前的 BitLocker 加密状态。

-   **管理密码**-更改 BitLocker 用于解锁其他内部驱动器的密码。

**先进**

-   **TPM 管理**-在单独的窗口中打开 TPM 管理工具。 在这里，你可以配置常见的 TPM 任务和获取有关 TPM 芯片组的信息。 您必须具有计算机的管理员权限才能访问此工具。

-   **磁盘管理**-打开 "磁盘管理" 工具。 从这里，你可以查看连接到计算机的所有硬盘的信息，并配置分区和驱动器选项。 您必须具有计算机的管理员权限才能访问此工具。

 

 





