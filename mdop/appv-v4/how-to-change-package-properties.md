---
title: 如何更改程序包属性
description: 如何更改程序包属性
author: dansimp
ms.assetid: 6050916a-d4fe-4dac-8f2a-47308dbbf481
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d2427a2651f3941f967c171ae7854facc62b4aa9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801659"
---
# 如何更改程序包属性


你可以使用以下过程修改应用程序虚拟化程序包名称及其关联的注释。

如果这是第一次创建程序包，则还可以更改顺序参数块大小，以确定序列化应用程序包如何从应用程序虚拟化服务器传输到应用程序虚拟化桌面客户端。

**注意** 选择块大小时，请考虑 SFT 文件的大小和你的网络带宽。 块大小较小的文件需要较长时间才能通过网络传输，但带宽占用较少。 块大小较大的文件可能会更快地传输，但它们会占用更多的网络带宽。 通过实验，你可以发现网络上的流式处理应用程序的最佳块大小。

 

"**属性**" 选项卡上的程序包属性的其余部分将自动生成，并且不能在此选项卡上进行修改。

**更改程序包名称或批注**

1.  单击 "**属性**" 选项卡。

2.  在 "**程序包名称**" 文本框中，输入或编辑程序包所使用的单个名称，该名称可以包含多个应用程序。

3.  在 "**批注**" 文本框中，选择性地输入或编辑任何批注。 建议的最佳做法是提供有关程序包和排序的详细信息。

4.  从 "**文件**" 菜单中，选择 "**保存**"。

**更改块大小**

1.  单击 "**属性**" 选项卡。

2.  在 "**块大小**" 下拉列表中，选择 " **4 kb**"、" **16 KB**"、" **32 kb**" 或 " **64 kb**"。

3.  从 "**文件**" 菜单中，选择 "**保存**"。

## 相关主题


[关于“属性”选项卡](about-the-properties-tab.md)

[Sequencer 控制台](sequencer-console.md)

 

 





