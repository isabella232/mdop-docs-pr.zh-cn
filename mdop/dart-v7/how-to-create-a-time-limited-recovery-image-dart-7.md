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
# <span data-ttu-id="c86bb-103">如何创建限期提供的恢复映像</span><span class="sxs-lookup"><span data-stu-id="c86bb-103">How to Create a Time Limited Recovery Image</span></span>


<span data-ttu-id="c86bb-104">你可以创建一个只能在生成特定天数后使用的 DaRT 恢复映像。</span><span class="sxs-lookup"><span data-stu-id="c86bb-104">You can create a DaRT recovery image that can only be used for a certain number of days after it is generated.</span></span> <span data-ttu-id="c86bb-105">若要执行此操作，必须在命令提示符处运行**DaRT 恢复映像向导**并指定天数。</span><span class="sxs-lookup"><span data-stu-id="c86bb-105">To do this, you must run the **DaRT Recovery Image Wizard** at a command prompt and specify the number of days.</span></span>

**<span data-ttu-id="c86bb-106">创建具有时间限制的恢复映像</span><span class="sxs-lookup"><span data-stu-id="c86bb-106">To create a recovery image that has a time limit</span></span>**

1.  <span data-ttu-id="c86bb-107">使用管理员凭据打开命令提示符。</span><span class="sxs-lookup"><span data-stu-id="c86bb-107">Open a Command Prompt with administrator credentials.</span></span>

2.  <span data-ttu-id="c86bb-108">将目录更改为 ERDC.exe 程序的位置。</span><span class="sxs-lookup"><span data-stu-id="c86bb-108">Change the directory to the location of the ERDC.exe program.</span></span>

3.  <span data-ttu-id="c86bb-109">使用以下语法，运行**DaRT 恢复映像向导**。</span><span class="sxs-lookup"><span data-stu-id="c86bb-109">Using the following syntax, run the **DaRT Recovery Image Wizard**.</span></span> <span data-ttu-id="c86bb-110">*NumberOfDays*是一个正整数值，表示 DaRT 恢复映像可用的天数。</span><span class="sxs-lookup"><span data-stu-id="c86bb-110">*NumberOfDays* is a positive integer that represents the number of days that the DaRT recovery image will be usable.</span></span>

    ``` syntax
    ERDC /e NumberOfDays
    ```

## <span data-ttu-id="c86bb-111">相关主题</span><span class="sxs-lookup"><span data-stu-id="c86bb-111">Related topics</span></span>


[<span data-ttu-id="c86bb-112">创建 DaRT 7.0 恢复映像</span><span class="sxs-lookup"><span data-stu-id="c86bb-112">Creating the DaRT 7.0 Recovery Image</span></span>](creating-the-dart-70-recovery-image-dart-7.md)

 

 





