---
title: Microsoft 高级组策略管理 4.0 SP1 发行说明
description: Microsoft 高级组策略管理 4.0 SP1 发行说明
author: dansimp
ms.assetid: 91835bf8-e53c-4202-986e-8d37050d1267
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ff9ce0405df766aef9b30e67d07ceb579c4fa89f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801855"
---
# Microsoft 高级组策略管理 4.0 SP1 发行说明


若要搜索这些发行说明，请按 Ctrl + F。

在安装 Microsoft 高级组策略管理（AGPM） 4.0 SP1 之前，请仔细阅读这些发行说明。 这些发行说明包含成功安装 AGPM 4.0 SP1 所需的信息，其中包含产品文档中不可用的信息。 如果这些发行说明和其他 AGPM 文档之间存在差异，则应将最新更改视为权威。 这些发行说明取代了本产品附带的内容。

## AGPM 4.0 SP1 已知问题


本部分包含针对 AGPM 4.0 SP1 的发行说明。

### <a href="" id="control-panel-s--uninstall--tool-may-not-work-when-you-try-to-change-agpm-server-settings"></a>尝试更改 AGPM 服务器设置时，"控制面板" 的 "卸载" 工具可能不起作用

当您尝试更改 AGPM 服务器设置时，"控制面板" 中允许卸载或更改程序的工具可能不起作用。

解决方法：在尝试使用 "控制面板" 更改 AGPM 服务器设置之前，请创建 "AGPM 存档" 文件夹的副本。 然后，你可以使用 Setup.exe 重新安装 AGPM 服务器，并选择所需的配置参数。

### 报表不显示已添加到组策略对象的链接

"AGPM 设置" 和 "差异" 报表不显示已添加到组策略对象（GPO）的链接。

解决方法：若要查看报表中的链接，请在组策略管理控制台（GPMC）中选择 GPO，然后单击右窗格中的 "**设置**" 选项卡。

### <a href="" id="reports-do-not-display-all--choice-options-properties--settings"></a>报表不显示所有 "选择选项属性" 设置

"AGPM 设置" 和 "差异" 报表不会显示在 "组策略对象编辑器" 的 "选项" 属性窗口中选择的所有设置。

解决方法：使用 GPMC 查看报表中所选的 "选择选项" 属性设置。

### 报表在某些浏览器中不显示 "显示" 和 "隐藏" 选项卡

查看 Google Chrome 或 Mozilla Firefox 中的报表时，不会显示在 "AGPM 设置" 和 "差异" 报表右侧显示的 "显示" 和 "隐藏" 选项卡。

解决方法：使用 Internet Explorer 查看报表。

### AGPM 设置和差异报表可能显示 GPMC 报表中的不同内容

"AGPM 设置" 和 "差异" 报表可能不会显示与组策略管理控制台（GPMC）中的报表相同的内容。

解决方法：使用 GPMC 查看 AGPM 报表。

### 如果域控制器未联机，则 AGPM 服务不会启动

当 AGPM 服务安装在 Windows 8 上的域控制器上时，如果域控制器未联机，则该服务不会启动。

解决方法：在域控制器联机后手动启动 AGPM 服务。

### 从 AGPM 4.0 发布和修补程序升级到 AGPM 4.0 SP1 时，将阻止升级到 AGPM SP1

如果你尝试将 AGPM 服务器升级到 AGPM 4.0。 SP1 安装了 AGPM 4.0，然后安装 AGPM 修复程序（请参阅知识库文章[2643502](https://go.microsoft.com/fwlink/?LinkId=254474)）后，升级失败，无法完成。

解决方法：卸载 AGPM 4.0 服务器，然后安装 AGPM 4.0 SP1。

### 报表不显示组织单位链接

如果将不受控制的 GPO 链接到组织单元，然后使用 AGPM 控制该 GPO，则 AGPM 设置和差异报告不会显示组织单位链接。

解决方法：在 "**更改设置**" 节点的 "**受控**" 选项卡上，右键单击该 GPO，然后单击 "**设置**"，然后单击 " **GPO 链接**" 以查看组织链接。 或者，你可以使用 GPMC 从 "**范围**" 选项卡查看指向 GPO 的链接。

## 相关主题


[高级组策略管理](index.md)

[AGPM 4.0 SP1 中的新增功能](whats-new-in-agpm-40-sp1.md)

 

 





