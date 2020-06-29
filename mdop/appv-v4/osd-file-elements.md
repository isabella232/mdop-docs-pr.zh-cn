---
title: OSD 文件元素
description: OSD 文件元素
author: dansimp
ms.assetid: 8211b562-7549-4331-8321-144f52574e99
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a8e3ebcf53ff39ecd2ef7ad0feec0bbbcae199db
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798905"
---
# OSD 文件元素


Sequencer 安装目录包含 XML 架构文件**Softricity**，该文件定义了开放软件描述符（OSD）文件的有效结构。 下面是一些使用较频繁的 OSD 元素。

<a href="" id="softpkg"></a>SOFTPKG  
包含定义软件包的所有元素的 OSD 文件的根元素。

<a href="" id="codebase"></a>CODEBASE  
有关此程序包的 sft 文件的信息，包括 HREF、文件名和 GUID 属性。 如果更改此特定程序包的分发点，则可以编辑 HREF 属性。

<a href="" id="os"></a>操作系统  
根据最初在排序向导中设置的值，定义此应用程序可以运行的操作系统。 此值只能包含**Softricity**中定义的值。

<a href="" id="local-interaction-allowed"></a>本地 \ _INTERACTION \ _ALLOWED  
设置为 TRUE，这将允许在全局命名空间中创建命名对象（事件、mutex、信号、文件映射和 mailslots）和 COM 对象，而不是在特定虚拟环境内隔离，从而允许虚拟应用程序与主机操作系统的应用程序交互。

示例： &lt; SOFTPKG &gt; &lt; 实现&gt;

&lt;VIRTUALENV &gt; &lt; 策略&gt;

&lt;本地 \ _INTERACTION \ _ALLOWED &gt; TRUE

&lt;/LOCAL\ _INTERACTION \ _ALLOWED&gt;

&lt;/POLICIES &gt; &lt; /VIRTUALENV&gt;

&lt;/IMPLEMENTATION &gt; &lt; /SOFTPKG&gt;

<a href="" id="dependencies"></a>相关  
使用另一个程序包中的 CODEBASE 标记定义动态套件合成（其他程序包上的依赖项）。

示例： &lt; 依赖项 &gt; &lt; 基本代码 HREF = "rtsps：//server/package.sft" GUID = "7579F4DF-2461-4219-494E1FDC69E3" SYSGUARDFILE = "installer.pkg =" osguard = "6572748" SIZE = "/DEPENDENCIES" 必需 = "FALSE"/ &gt; &lt;&gt;

<a href="" id="package-name"></a>程序包名称  
在 "排序向导"**包信息**页面中输入的程序包的公用名，使你能够指定用于包含多个应用程序的序列化应用程序的单个名称。

<a href="" id="title"></a>标题  
要对其进行排序的应用程序的可选描述性名称。

<a href="" id="abstract"></a>抽象化  
在排序向导**包信息**页面的 "**注释**" 字段中输入的软件包的简短说明。 最佳做法是指定诸如 Sequencer 工作站、Sequencer 版本的操作系统和服务包级别以及排序工程师的名称等信息。

<a href="" id="script"></a>书写  
定义要在启动、关闭或流式处理期间发生的特定脚本事件。

<a href="" id="mgmt-shortcutlist"></a>管理 \ _SHORTCUTLIST  
向导中定义的所有快捷方式的列表。

<a href="" id="mgmt-fileassociations"></a>管理 \ _FILEASSOCIATIONS  
在向导中指定的文件类型的列表。

## 相关主题


[关于“OSD”选项卡](about-the-osd-tab.md)

 

 





