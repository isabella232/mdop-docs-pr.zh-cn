---
title: 部署 DaRT 7.0 恢复映像
description: 部署 DaRT 7.0 恢复映像
author: dansimp
ms.assetid: 6bba7bff-800f-44e4-bcfc-e143115607ca
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: cef626e50bf1049529c51afca5e536b03b3d915d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798100"
---
# 部署 DaRT 7.0 恢复映像


创建包含 Microsoft Diagnostics 和恢复工具集（DaRT）7恢复映像的国际标准化组织（ISO）文件后，您可以在整个企业中部署 DaRT 恢复映像，以便最终用户和支持人员的代理可以使用该映像。 你可以使用四种受支持的方法来部署 DaRT 恢复映像。

-   将 ISO 图像文件刻录到 CD 或 DVD

-   将 ISO 图像文件的内容保存到 USB 闪存驱动器（UFD）

-   从 ISO 映像提取启动 .wim 文件，并将其部署为可供最终用户计算机使用的远程分区

-   从 ISO 映像提取启动 .wim 文件，并在新的 Windows 7 安装的恢复分区中部署

**重要提示** **DaRT 恢复映像向导**仅提供刻录 CD 或 DVD 的选项。 保存和部署恢复映像的所有其他方法都需要执行其他步骤，这些步骤涉及 DaRT 中未包含的工具。 本部分提供了有关这些其他方法的一些指南和链接。

 

## 使用 USB 闪存驱动器部署 DaRT 恢复映像


在完成运行 DaRT 恢复映像向导后，您可以使用中的工具 <https://go.microsoft.com/fwlink/?LinkId=218888> 将 ISO 映像文件复制到 USB 闪存驱动器（UFD）。

[如何使用 U 盘部署 DaRT 恢复映像](how-to-deploy-the-dart-recovery-image-using-a-usb-flash-drive-dart-7.md)

## 将 DaRT 恢复映像部署为恢复分区的一部分


在完成运行 DaRT 恢复映像向导并创建恢复映像后，可以从 ISO 映像文件提取 boot.ini 文件，并将其部署为 Windows 7 映像中的恢复分区。

[如何将 DaRT 恢复映像作为恢复分区的一部分进行部署](how-to-deploy-the-dart-recovery-image-as-part-of-a-recovery-partition-dart-7.md)

## 将 DaRT 恢复映像部署为远程分区


在完成运行 DaRT 恢复映像向导并创建恢复映像后，可以从 ISO 映像文件中提取 boot.ini 文件，并将其部署为网络上的远程分区。

[如何将 DaRT 恢复映像作为远程分区进行部署](how-to-deploy-the-dart-recovery-image-as-a-remote-partition-dart-7.md)

## 用于维护部署 DaRT 恢复映像的其他资源


-   [部署 DaRT 7.0](deploying-dart-70-new-ia.md)

 

 





