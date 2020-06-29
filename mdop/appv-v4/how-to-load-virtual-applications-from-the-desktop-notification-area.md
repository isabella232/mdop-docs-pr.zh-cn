---
title: 如何从桌面通知区域加载虚拟应用程序
description: 如何从桌面通知区域加载虚拟应用程序
author: dansimp
ms.assetid: f52758eb-8b81-4b3c-9bc3-adcf7c00c238
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d7004f9e0031dfeeedc8b6a916e2f3488f1d31e1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801328"
---
# 如何从桌面通知区域加载虚拟应用程序


如果你是移动用户，你可能希望将应用程序中的应用程序完全加载到缓存中，以便在断开连接操作或脱机模式下使用它们。 若要流式处理应用程序虚拟化（app-v）服务器或应用程序虚拟化（app-v）流服务器中的应用程序，必须连接到服务器才能加载应用程序。 如果尝试加载应用程序时未连接到服务器，系统将生成相应的错误消息。 你还可以从文件或磁盘将应用程序流式传输到客户端。

应用程序一次加载一个应用程序。 进度条显示应用程序名称、加载的应用程序百分比以及已处理的应用程序数与排队的应用程序总数。 你可以跳过在100% 加载前正在进行的任何应用程序。 您也可以跳过所有剩余应用程序的加载。

**注意** 如果你的系统在加载应用程序时遇到错误，它会向你报告错误。 必须先取消错误对话框，然后它才会加载下一个应用程序。

 

**加载所有应用程序**

1.  右键单击通知区域中的 "应用程序虚拟化系统" 图标。

2.  从弹出菜单中选择 "**加载应用程序**"。

**跳过应用程序**

1.  单击进度栏以显示该对话框。

2.  选择以下按钮之一以获得所需的结果：

    1.  **跳过**-跳过当前加载的应用程序。

    2.  **全部跳过**-跳过所有剩余的应用程序。

    3.  **继续**-取消对话框并继续加载应用程序。

## 相关主题


[如何为 Application Virtualization Client Management 使用桌面通知区域](how-to-use-the-desktop-notification-area-for-application-virtualization-client-management.md)

 

 





