---
title: 如何将 DaRT 恢复映像作为恢复分区的一部分进行部署
description: 如何将 DaRT 恢复映像作为恢复分区的一部分进行部署
author: dansimp
ms.assetid: 07c5d539-51d9-4759-adc7-72b40d5d7bb3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e3647d684f64a0635e2875314498bde841204369
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803557"
---
# 如何将 DaRT 恢复映像作为恢复分区的一部分进行部署


在完成运行 Microsoft Diagnostics 和恢复工具集（DaRT）8.0 恢复映像向导并创建恢复映像之后，你可以从 ISO 映像文件提取 boot.ini 文件，并将其作为 Windows 8 映像中的恢复分区进行部署。 建议使用分区，因为阻止 Windows 操作系统启动的任何损坏问题也会阻止恢复映像启动。 单独的分区还无需提供两次 BitLocker 恢复密钥。 考虑隐藏分区以防止用户在其上存储文件。

**在 Windows 8 映像的恢复分区中部署 DaRT**

1.  在 Windows 8 映像中创建一个等于或大于使用**DaRT 8.0 恢复映像向导**创建的 ISO 映像文件大小的目标分区。

    DaRT 分区所需的最小大小是500MB，以适应 DaRT 中的远程连接功能。

2.  从 DaRT ISO 映像文件提取启动 .wim 文件。

    1.  使用贵公司的首选方法，装载您在 "**创建启动映像**" 页面上创建的 ISO 映像文件。

    2.  打开 ISO 映像文件，并将装载的映像中的 \\sources 文件夹中的启动 .wim 文件复制到计算机上或外部驱动器上的某个位置。

        **注意** 如果你刻录了恢复映像的 CD、DVD 或 USB，则可以打开可移动媒体上的文件并从 \\sources 文件夹中复制 boot.ini 文件。 如果复制 boot.ini 文件，则无需装载映像。

         

3.  使用 boot.ini 文件创建可启动的恢复分区，方法是使用贵公司用于创建自定义 Windows RE 映像的标准方法。

    有关如何创建或自定义恢复分区的详细信息，请参阅[自定义 WINDOWS RE 体验](https://go.microsoft.com/fwlink/?LinkId=214222)。

4.  将 Windows 8 映像中的目标分区替换为恢复分区。

    有关如何部署恢复解决方案以在系统发生故障时重新安装工厂映像的详细信息，请参阅[部署系统恢复映像](https://go.microsoft.com/fwlink/?LinkId=214221)。

## 相关主题


[创建 DaRT 8.0 恢复映像](creating-the-dart-80-recovery-image-dart-8.md)

[部署 DaRT 恢复映像](deploying-the-dart-recovery-image-dart-8.md)

[计划 DaRT 8.0](planning-for-dart-80-dart-8.md)

 

 





