---
title: 如何将 DaRT 恢复映像作为远程分区进行部署
description: 如何将 DaRT 恢复映像作为远程分区进行部署
author: dansimp
ms.assetid: 757c9340-8eac-42e8-85de-4302e436713a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a3acdbf72a2c6dac0238f868c7280f1c389b1311
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803394"
---
# 如何将 DaRT 恢复映像作为远程分区进行部署


在完成运行 DaRT 恢复映像向导并创建恢复映像后，可以从 ISO 映像文件中提取 boot.ini 文件，并将其部署为网络上的远程分区。

**将 DaRT 部署为远程分区**

1.  从 DaRT ISO 映像文件提取启动 .wim 文件。

    1.  通过使用贵公司装载映像的首选方法，装载在 "**创建启动映像**" 对话框中创建的 ISO 图像文件。

    2.  打开 ISO 映像文件，并将装载的映像中的 \\sources 文件夹中的启动 .wim 文件复制到计算机上或外部驱动器上的某个位置。

        **注意** 如果刻录了恢复映像的 CD 或 DVD，则可以打开 CD 或 DVD 上的文件，并从 \\sources 文件夹中复制 boot.ini 文件。 这使你可以跳过装入映像的需要。

         

2.  将启动 .wim 文件部署到可从你的企业中的最终用户计算机访问的 WDS 服务器。

3.  将 WDS 服务器配置为使用适用于 DaRT 的 boot.ini 文件，方法是遵循你的标准 WDS 部署过程。

有关如何将 DaRT 部署为远程分区的详细信息，请参阅以下内容：

-   [演练：使用 PXE 部署映像](https://go.microsoft.com/fwlink/?LinkId=212108)

-   [Windows 部署服务入门指南](https://go.microsoft.com/fwlink/?LinkId=212106)

## 相关主题


[部署 DaRT 7.0 恢复映像](deploying-the-dart-70-recovery-image-dart-7.md)

 

 





