---
title: 关于“属性”选项卡
description: 关于“属性”选项卡
author: dansimp
ms.assetid: a6cf6f51-3778-4c8d-9632-3af4005775d2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4b2d6c3e01dde48fdd6701984f66610ea0333b74
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802411"
---
# 关于“属性”选项卡


使用 "**属性**" 选项卡查看有关序列化应用程序包的基本统计信息。 除非另有说明，否则将自动生成信息。 此选项卡包含以下元素。

## 程序包信息


<a href="" id="package-name"></a>**程序包名称**  
用于可能包含一个或多个应用程序的序列化应用程序包的单个名称，例如，Microsoft Office 可以用于标记序列化应用程序包，其中包含在同一虚拟环境中运行的 Microsoft Word 和 Microsoft Excel 应用程序。

<a href="" id="comments"></a>**备注**  
显示将在开放软件描述符（OSD）文件摘要元素中显示的软件包的简短说明。 此项目是可选的。

<a href="" id="package-version"></a>**程序包版本**  
序列化应用程序包版本。

<a href="" id="package-guid"></a>**程序包 GUID**  
自动分配给顺序应用程序包的全局唯一标识符（GUID）将其与可能在序列化应用程序包流入的计算机上运行的其他序列化应用程序包区分开。

<a href="" id="package-version-guid"></a>**程序包版本 GUID**  
序列化应用程序包版本 GUID。

<a href="" id="root-directory"></a>**根目录**  
排序计算机上安装了序列化应用程序包的文件的目录。 还会在将对序列化应用程序包进行流式处理的计算机上创建此目录。 建议向后兼容，这是 Q 驱动器根目录下的8.3 格式目录名称，例如 Q:\\MyApp.1\\。

<a href="" id="created"></a>**已创建**  
已排序的应用程序包的创建日期和时间。

<a href="" id="modified"></a>**修改日期**  
已排序的应用程序包的上次修改日期和时间。

<a href="" id="package-size"></a>**程序包大小**  
程序包的大小（以 mb 为单位）。

<a href="" id="launch-size"></a>**启动大小**  
启动应用程序所需的 SFT 文件部分的大小（以 mb 为单位）。

## 排序参数


<a href="" id="block-size"></a>**块大小**  
指定为跨网络传输 SFT 文件的主要和辅助功能块的大小。 所有块都等于指定的大小;但是，最后一个块可能小于指定的大小。 你将看到以下值之一：

-   4 KB

-   16 KB

-   32 KB

-   64 KB

**注意** 创建初始程序包后，"块大小" 值不可更改。

 

## 相关主题


[如何更改程序包属性](how-to-change-package-properties.md)

[Sequencer 控制台](sequencer-console.md)

 

 





