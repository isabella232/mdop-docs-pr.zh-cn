---
title: 应用程序虚拟化属性 "常规" 选项卡
description: 应用程序虚拟化属性 "常规" 选项卡
author: dansimp
ms.assetid: be7449d9-171a-4a11-9382-83b7008ccbdd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6ee00bfc7f70ee7b17da42aad61356540a7a0be0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802316"
---
# Application Virtualization 属性：“常规”选项卡


使用 "**应用程序虚拟化属性**" 对话框的 "**常规**" 选项卡修改日志设置和数据位置。

此选项卡包含以下元素。

<a href="" id="log-level"></a>**日志级别**  
从下拉列表中选择级别。 默认级别为 "**信息**"。

<a href="" id="reset-log"></a>**重置日志**  
单击此按钮备份当前日志文件，并立即开始新的日志文件。

<a href="" id="location"></a>**位置**  
输入或浏览到要在其中保存日志文件 sftlog.txt 的位置。 默认位置如下所示：

-   对于 WindowsXP、Windows Server2003-*C:\\Documents 和 Settings\\All Users\\Application Data\\Microsoft\\Application 虚拟化客户端*

-   对于 Windows Vista、Windows 7、Windows Server2008-*C:\\ProgramData\\Microsoft\\Application 虚拟化客户端*

<a href="" id="system-log-level"></a>**系统日志级别**  
从下拉列表中选择级别。 默认级别为 "**警告**"。

**注意** "**系统日志级别**" 设置控制发送到系统事件日志的消息级别。 记录的消息与记录到客户端事件日志的消息相同，但它们存储在不具有客户端事件日志的空间限制的其他位置。 由于系统事件日志没有空间限制，因此非常适合在需要详细日志记录的情况下使用。

 

<a href="" id="global-data-directory"></a>**全局数据目录**  
输入或浏览到日志文件目录的位置。 默认位置如下所示：

-   对于 WindowsXP、Windows Server2003-*C:\\Documents 和 Settings\\All Users\\Application Data\\Microsoft\\Application 虚拟化客户端*

-   对于 Windows Vista、Windows 7、Windows Server2008-*C:\\ProgramData\\Microsoft\\Application 虚拟化客户端*

<a href="" id="user-data-directory"></a>**用户数据目录**  
输入或浏览到存储特定于用户的数据的目录的位置。 默认值为% APPDATA%。 此路径必须是客户端计算机上的有效环境变量。

## 相关主题


[Client Management Console：Application Virtualization 属性](client-management-console-application-virtualization-properties.md)

 

 





