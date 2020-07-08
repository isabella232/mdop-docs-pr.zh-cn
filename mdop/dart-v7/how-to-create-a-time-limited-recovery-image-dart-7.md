---
title: 如何创建限期提供的恢复映像
description: 如何创建限期提供的恢复映像
author: dansimp
ms.assetid: d2e29cac-c24c-4239-997f-0320b8a830ae
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a11891753f80d41f0089311771b906865950337c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798094"
---
# 如何创建限期提供的恢复映像


你可以创建一个只能在生成特定天数后使用的 DaRT 恢复映像。 若要执行此操作，必须在命令提示符处运行**DaRT 恢复映像向导**并指定天数。

**创建具有时间限制的恢复映像**

1.  使用管理员凭据打开命令提示符。

2.  将目录更改为 ERDC.exe 程序的位置。

3.  使用以下语法，运行**DaRT 恢复映像向导**。 *NumberOfDays*是一个正整数值，表示 DaRT 恢复映像可用的天数。

    ``` syntax
    ERDC /e NumberOfDays
    ```

## 相关主题


[创建 DaRT 7.0 恢复映像](creating-the-dart-70-recovery-image-dart-7.md)

 

 





