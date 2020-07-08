---
title: 如何将 DaRT 恢复映像作为恢复分区的一部分进行部署
description: 如何将 DaRT 恢复映像作为恢复分区的一部分进行部署
author: dansimp
ms.assetid: 462f2d08-f03b-4a07-b2d3-c69205dc6f70
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e75c3f9e58d784c13003feb84001f89c4607115d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803392"
---
# 如何将 DaRT 恢复映像作为恢复分区的一部分进行部署


在完成运行 DaRT 恢复映像向导并创建恢复映像后，可以从 ISO 映像文件提取 boot.ini 文件，并将其部署为 Windows 7 映像中的恢复分区。

**在 Windows 7 映像的恢复分区中部署 DaRT**

1.  在 Windows 7 映像中创建一个等于或大于使用**DaRT 恢复映像向导**创建的 ISO 映像文件大小的目标分区。

    DaRT 分区所需的最小大小约为300MB。 但是，我们建议450MB 以满足 DaRT 中的远程连接功能。

2.  从 DaRT ISO 映像文件提取启动 .wim 文件。

    1.  通过使用贵公司装载映像的首选方法，装载在 "**创建启动映像**" 对话框中创建的 ISO 图像文件。

    2.  打开 ISO 映像文件，并将装载的映像中的 \\sources 文件夹中的启动 .wim 文件复制到计算机上或外部驱动器上的某个位置。

        **注意** 如果刻录了恢复映像的 CD 或 DVD，则可以打开 CD 或 DVD 上的文件，并从 \\sources 文件夹中复制 boot.ini 文件。 这使你可以跳过装入映像的需要。

         

3.  使用 boot.ini 文件创建可启动的恢复分区，方法是使用贵公司用于创建自定义 Windows RE 映像的标准方法。

    有关如何创建或自定义恢复分区的详细信息，请参阅[自定义 WINDOWS RE 体验](https://go.microsoft.com/fwlink/?LinkId=214222)。

4.  将 Windows 7 映像中的目标分区替换为恢复分区。

在 Windows 7 映像准备就绪后，使用贵公司的标准映像部署过程将映像分发到企业中的计算机。 有关如何创建 Windows 7 映像的详细信息，请参阅[构建 windows 7 的标准映像：分步指南](https://go.microsoft.com/fwlink/?LinkId=212103)。

有关如何部署恢复解决方案以在系统发生故障时重新安装工厂映像的详细信息，请参阅[部署系统恢复映像](https://go.microsoft.com/fwlink/?LinkId=214221)。

## 相关主题


[部署 DaRT 7.0 恢复映像](deploying-the-dart-70-recovery-image-dart-7.md)

 

 





