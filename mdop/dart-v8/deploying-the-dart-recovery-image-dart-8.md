---
title: 部署 DaRT 恢复映像
description: 部署 DaRT 恢复映像
author: dansimp
ms.assetid: df5cb54a-be8c-4ed2-89ea-d3c67c2ef4d4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e445873324f005455ba3c96319847dea8ba761ae
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803503"
---
# 部署 DaRT 恢复映像


创建包含 Microsoft Diagnostics 和恢复工具集（DaRT）8.0 恢复映像的国际标准化组织（ISO）文件后，您可以在整个企业中部署 DaRT 8.0 恢复映像，以供最终用户和技术支持人员使用。 你可以使用四种受支持的方法来部署 DaRT 恢复映像。 若要查看每种方法的优点和缺点，请参阅[规划如何保存和部署 DaRT 8.0 恢复映像](planning-how-to-save-and-deploy-the-dart-80-recovery-image-dart-8.md)。

使用 DaRT 恢复映像向导将 ISO 图像文件刻录到 CD 或 DVD

使用 DaRT 恢复映像向导将 ISO 图像文件的内容保存到 USB 闪存驱动器（UFD）

从 ISO 映像提取启动 .wim 文件，并将其部署为可供最终用户计算机使用的远程分区

从 ISO 映像提取启动 .wim 文件，并在新的 Windows 8 安装的恢复分区中部署

**重要提示** **DaRT 恢复映像向导**提供将映像刻录到 CD、DVD 或 UFD 的选项，但保存和部署恢复映像的其他方法需要额外的步骤，这些步骤涉及 DaRT 中未包含的工具。 本部分提供了有关这些其他方法的一些指南和链接。

 

## 将 DaRT 恢复映像部署为恢复分区的一部分


在完成运行 DaRT 恢复映像向导并创建恢复映像后，可以从 ISO 映像文件提取 boot.ini 文件，并将其作为 Windows 8 映像中的恢复分区进行部署。

[如何将 DaRT 恢复映像作为恢复分区的一部分进行部署](how-to-deploy-the-dart-recovery-image-as-part-of-a-recovery-partition-dart-8.md)

## 将 DaRT 恢复映像部署为远程分区


你可以在中央网络启动服务器（如 Windows 部署服务）上托管恢复映像，并允许用户或支持人员将映像流式传输到计算机按需传输。

[如何将 DaRT 恢复映像作为远程分区进行部署](how-to-deploy-the-dart-recovery-image-as-a-remote-partition-dart-8.md)

## 用于部署 DaRT 恢复映像的其他资源


[部署 DaRT 8.0](deploying-dart-80-dart-8.md)

 

 





