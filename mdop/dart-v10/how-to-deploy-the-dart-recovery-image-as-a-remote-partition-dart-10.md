---
title: 如何将 DaRT 恢复映像作为远程分区进行部署
description: 如何将 DaRT 恢复映像作为远程分区进行部署
author: dansimp
ms.assetid: 06a5e250-b992-4f6a-ad74-e7715f9e96e7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 3cdb1313a64bacd652a5253c09f36fa792d0fa3c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798202"
---
# 如何将 DaRT 恢复映像作为远程分区进行部署


在完成运行 Microsoft Diagnostics 和恢复工具集（DaRT）10恢复映像向导并创建恢复映像之后，你可以从 ISO 映像文件提取 boot.ini 文件，并将其部署为网络上的远程分区。

**将 DaRT 10 部署为远程分区**

1.  从 DaRT ISO 映像文件提取启动 .wim 文件。

    1.  通过使用贵公司装载映像的首选方法，装载在 "**创建启动映像**" 对话框中创建的 ISO 图像文件。

    2.  打开 ISO 映像文件，并将装载的映像中的 \\sources 文件夹中的启动 .wim 文件复制到计算机上或外部驱动器上的某个位置。

        **注意** 如果刻录了恢复映像的 CD 或 DVD，则可以打开 CD 或 DVD 上的文件，并从 \\sources 文件夹中复制 boot.ini 文件。 这使你可以跳过装入映像的需要。

         

2.  将启动 .wim 文件部署到可从你的企业中的最终用户计算机访问的 WDS 服务器。

3.  将 WDS 服务器配置为使用适用于 DaRT 的 boot.ini 文件，方法是遵循你的标准 WDS 部署过程。

有关如何将 DaRT 部署为远程分区的详细信息，请参阅[操作实例：使用 PXE](https://go.microsoft.com/fwlink/?LinkId=212108)和[Windows 部署服务入门指南](https://go.microsoft.com/fwlink/?LinkId=212106)部署映像。

## 相关主题


[创建 DaRT 10 恢复映像](creating-the-dart-10-recovery-image.md)

[部署 DaRT 恢复映像](deploying-the-dart-recovery-image-dart-10.md)

[计划 DaRT 10](planning-for-dart-10.md)

 

 





