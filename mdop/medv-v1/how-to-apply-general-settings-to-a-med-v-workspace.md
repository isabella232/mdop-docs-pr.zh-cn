---
title: 如何将常规设置应用于 MED-V 工作区
description: 如何将常规设置应用于 MED-V 工作区
author: dansimp
ms.assetid: 6152dced-e301-4fa2-bfa0-aecf3c23f23a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 176564ae1d22b27a24625d988f46c9746b291748
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803988"
---
# 如何将常规设置应用于 MED-V 工作区


通过定义 MED-V 工作区是否将以无缝集成或完整桌面模式显示，"常规" 设置使你可以配置使用 MED-V 工作区时的基本用户体验。 无缝集成在主机桌面中包含旧版应用程序，以便它们看起来就像是直接安装在主机上一样。 完整桌面在主机上的单独窗口中显示了 MED-V 工作区操作系统的桌面。

所有常规设置均在 "**常规**" 选项卡上的 "**策略**" 模块中配置。

**将常规设置应用于 MED-V 工作区**

1.  单击要配置的 MED-V 工作区。

2.  按下表所述配置常规属性。

3.  在 "**策略**" 菜单上，选择 "**提交**"。

**常规工作区属性**

属性说明*工作区属性*

名称

MED-V 工作区的名称。

**警告** 请勿在客户端计算机上运行现有的 MED-V 工作区时对其进行重命名。

 

描述

MED-V 工作区的说明，其中可以包含 MED-V 工作区的内容或状态以及任何其他有用的信息。

**注意** 说明供管理员使用，对策略没有任何影响。

 

支持联系人信息

用于技术支持的联系信息。 输入的信息将显示在支持联系人信息屏幕中，可通过 MED-V 客户端通知区域访问。

*工作区 UI*

无缝集成

对于 MED-V 工作区窗口、任务栏和通知区域图标，选择此选项以无缝集成到主机桌面。

在每个工作区窗口周围绘制框架

使用无缝集成时，选择此选项以在 MED-V 工作区内运行的所有应用程序以及所有任务栏按钮图标的彩色背景周围创建彩色边框。 在 "**框架颜色**" 字段中，选择颜色。

完整桌面

选择此选项可将 MED-V 工作区显示为整个桌面，而无需与主机集成。

*主机验证*

命令行

在启动 MED-V 工作区之前，键入要在主机上运行的命令行。

如果验证失败，请勿启动工作区（退出代码不是 "0"）

如果使用命令行，并且希望仅在脚本成功完成时启动 MED-V 工作区，请选中此复选框。

 

在启动 MED-V 工作区之前，可以在主机上运行命令行。

**在启动 MED-V 工作区之前运行命令行**

1.  在 "**命令行**" 字段中，输入命令行。

2.  若要仅在命令行成功时启动 MED-V 工作区，请选中 "**如果验证失败，请勿启动工作区**" 复选框。

## 相关主题


[使用 MED-V 管理控制台用户界面](using-the-med-v-management-console-user-interface.md)

[创建 MED-V 工作区](creating-a-med-v-workspacemedv-10-sp1.md)

 

 





