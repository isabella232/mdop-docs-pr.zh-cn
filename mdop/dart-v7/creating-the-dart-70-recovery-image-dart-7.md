---
title: 创建 DaRT 7.0 恢复映像
description: 创建 DaRT 7.0 恢复映像
author: dansimp
ms.assetid: ebb2ec58-0349-469d-a23f-3f944fe4c1fa
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f19ff144cac61ca7ea5a8498f67caf8a99229d77
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803337"
---
# 创建 DaRT 7.0 恢复映像


Microsoft 诊断和恢复工具集（DaRT）7包含在 Windows 中用于创建可启动的国际标准化组织（ISO）映像的**DaRT 恢复映像向导**。 ISO 图像是表示 CD 的原始内容的文件。

## 使用 DaRT 恢复映像向导创建恢复映像


由 DaRT 恢复映像向导创建的 ISO 包含允许你启动到问题计算机的 DaRT 恢复映像，即使它可能不会启动。 将计算机启动到 DaRT 后，您可以运行不同的 DaRT 工具来尝试诊断和修复计算机。

你可以将 ISO 写入可写 CD 或 DVD，将其保存到 USB 闪存驱动器，或将其保存为可用于从远程分区或恢复分区启动到 DaRT 的格式。 有关详细信息，请参阅[部署 DaRT 7.0 恢复映像](deploying-the-dart-70-recovery-image-dart-7.md)。

**注意** 如果你的计算机包含 CD-RW 驱动器，向导将提供将 ISO 映像刻录到空白 CD 或 DVD 的向导。 如果你的计算机不包含向导支持的驱动器，你可以通过使用可刻录 CD 或 DVD 的大多数程序将 ISO 映像刻录到 CD 或 DVD 上。

 

若要从 ISO 映像创建可启动 CD 或 DVD，您必须拥有：

-   CD-RW 驱动器。

-   可录制 CD 或 DVD （采用可刻录驱动器支持的格式）。

-   支持可刻录驱动器并支持直接将 ISO 映像刻录到 CD 或 DVD 的软件。

    **重要提示** 在你打算支持的所有不同计算机上测试你创建的 CD 或 DVD，因为某些计算机无法从所有类型的可录制媒体启动。

     

若要将 ISO 映像保存到 USB 闪存驱动器（UFD），您必须具备：

-   格式正确的 UFD。

-   可用于装载 ISO 映像的程序。

[如何使用 DaRT 恢复映像向导来创建恢复映像](how-to-use-the-dart-recovery-image-wizard-to-create-the-recovery-image-dart-7.md)

## 创建时间有限的恢复映像


你可以创建一个只能在生成特定天数后使用的 DaRT 恢复映像。 若要执行此操作，必须在命令提示符处运行**DaRT 恢复映像向导**并指定天数。

[如何创建限期提供的恢复映像](how-to-create-a-time-limited-recovery-image-dart-7.md)

## 用于创建 DaRT7 恢复映像的其他资源


-   [部署 DaRT 7.0](deploying-dart-70-new-ia.md)

 

 





