---
title: “发布服务器”节点
description: “发布服务器”节点
author: dansimp
ms.assetid: b5823c6c-15bc-4e8d-aeeb-acc366ffedd1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8c001e246c63919773d29a2317d5a43937c0813f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798843"
---
# “发布服务器”节点


"**发布服务器**" 节点位于应用程序虚拟化客户端管理控制台的**作用域**窗格中的**应用程序虚拟化**节点下一级。 选择此节点时，"**结果**" 窗格将显示发布服务器的列表。

右键单击 "**发布服务器**" 节点可显示一个弹出菜单，其中包含以下元素。

<a href="" id="new-server"></a>**新服务器**  
此菜单项显示 "新建服务器" 向导。 此向导包含两个页面：

1.  输入服务器显示名称和服务器类型：

    -   **显示名称**-输入要为服务器显示的名称。 默认情况下，此字段为空。

    -   **类型**—从服务器类型的下拉列表中选择服务器类型。

2.  指定服务器的连接设置：

    -   **主机名**—输入服务器的名称或 IP 地址。

    -   **端口**-输入与端口号对应的数值。 如果服务器类型为 "应用程序虚拟化服务器" 和80（如果服务器类型为 "标准 HTTP 服务器"），则默认值为554。

    -   **路径**-当服务器类型为 "Application Virtualization server" 或 "增强的安全应用程序虚拟化服务器" 时，此字段默认为 "/"，并且是只读的。 当服务器类型为 "标准 HTTP 服务器" 或 "增强的安全 HTTP 服务器" 时，**路径**字段也是可编辑的。

<a href="" id="new-window-from-here"></a>**从此处新建窗口**  
选择此菜单项以打开新的管理控制台，其中将选定的节点用作根节点。

<a href="" id="export-list"></a>**导出列表**  
可以使用此菜单项创建一个以制表符分隔的文本文件，其中包含 "**结果**" 窗格的内容。 此项显示一个标准的 "**文件保存**" 对话框，您可以在其中指定要创建的文本文件的位置。

<a href="" id="view"></a>**视图**  
此弹出菜单项列表使你能够更改 "**结果**" 窗格的外观和内容。

<a href="" id="refresh"></a>**刷新**  
选择此项目以刷新管理控制台。

<a href="" id="help"></a>**帮助**  
此项目显示管理控制台的帮助系统。

## 相关主题


[“发布服务器结果”窗格](publishing-servers-results-pane.md)

[“发布服务器结果”窗格列](publishing-servers-results-pane-columns.md)

 

 





