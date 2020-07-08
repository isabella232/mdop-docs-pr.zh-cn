---
title: 如何使用 U 盘部署 DaRT 恢复映像
description: 如何使用 U 盘部署 DaRT 恢复映像
author: dansimp
ms.assetid: 5b7aa843-731e-47e7-b5f9-48d08da732d6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 1228c9cb5f870162f285d726d48721dde1185107
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803414"
---
# 如何使用 U 盘部署 DaRT 恢复映像


在完成运行**DaRT 恢复映像向导**后，您可以使用中的工具 <https://go.microsoft.com/fwlink/?LinkId=218888> 将 ISO 映像文件复制到 USB 闪存驱动器（UFD）。

您也可以按照本部分中提供的步骤手动将 ISO 映像文件复制到 UFD。

**将 DaRT 恢复映像保存到 USB 闪存驱动器**

1.  格式化 USB 闪存驱动器。

    1.  在正在运行的有效操作系统或 WindowsPE 会话中，插入你的 UFD。

    2.  在具有管理员权限的命令提示符处，键入 " **DISKPART** "，然后键入 "**列出磁盘**"。

        命令提示符窗口显示 UFD 的磁盘号，例如**磁盘 1**。

    3.  在命令提示符处一次输入以下命令。

        ``` syntax
        SELECT DISK 1
        CLEAN
        CREATE PARTITION PRIMARY
        SELECT PARTITION 1
        ACTIVE
        FORMAT FS=NTFS
        ASSIGN
        EXIT
        ```

        **注意** 上面的代码示例假设 Disk1 是 UFD。 如果需要，请将磁盘1替换为您的磁盘号。

         

2.  通过使用贵公司装载映像的首选方法，装载您在**DaRT 恢复映像向导**的 "**创建启动映像**" 对话框中创建的 ISO 图像文件。 这要求你有一种可用于装载图像文件的方法。

3.  打开装载的 ISO 映像文件并将其所有内容复制到格式化的 USB 闪存驱动器。

    **注意** 如果刻录了恢复映像的 CD 或 DVD，则可以打开 CD 或 DVD 上的文件，并将内容复制到 UFD。 这使你可以跳过装入映像的需要。

     

## 相关主题


[部署 DaRT 7.0 恢复映像](deploying-the-dart-70-recovery-image-dart-7.md)

 

 





