---
title: Microsoft 高级组策略管理 4.0 SP2 发行说明
description: Microsoft 高级组策略管理 4.0 SP2 发行说明
author: dansimp
ms.assetid: 0593cd11-3308-4942-bf19-8a7bb9447f01
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 736eb8d41cbb72b274a2941c60b0357bbc948c9d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802596"
---
# Microsoft 高级组策略管理 4.0 SP2 发行说明


若要搜索这些发行说明，请按 Ctrl + F。

安装 Microsoft 高级组策略管理（AGPM）4.0 服务 Pack2 （SP2）之前，请仔细阅读这些发行说明。 这些发行说明包含成功安装 AGPM 4.0 SP2 所需的信息，其中包含产品文档中不可用的信息。 如果这些发行说明和其他 AGPM 文档之间存在差异，请考虑最新的变更权威。 这些发行说明取代了本产品附带的内容。

## AGPM 4.0 SP2 的已知问题


本部分介绍了 AGPM 4.0 SP2 的已知问题。

### <a href="" id="control-panel-s--uninstall--tool-may-not-work-when-you-try-to-change-agpm-server-settings"></a>尝试更改 AGPM 服务器设置时，"控制面板" 的 "卸载" 工具可能不起作用

尝试更改 AGPM 服务器设置时，用于卸载或更改程序的 "控制面板" 中的工具可能不起作用。

**解决方法：** 在尝试使用 "控制面板" 更改 AGPM 服务器设置之前，请创建 "AGPM 存档" 文件夹的副本。 然后，你可以使用 Setup.exe 重新安装 AGPM 服务器，并选择所需的配置参数。

### 报表不显示已添加到组策略对象的链接

"AGPM 设置" 和 "差异" 报表不显示已添加到组策略对象（GPO）的链接。

**解决方法：** 若要查看报表中的链接，请在组策略管理控制台（GPMC）中选择 GPO，然后单击右窗格中的 "**设置**" 选项卡。

### 报表不显示所有选项属性设置

"AGPM 设置" 和 "差异" 报表不会显示在 "组策略对象编辑器" 的 "**选项" 属性**窗口中选择的所有设置。

**解决方法：** 使用 GPMC 查看报表中所选的 "**选择选项" 属性**设置。

### 报表可能不会显示某些浏览器中的 "显示" 和 "隐藏" 选项卡

在 Google Chrome 或 Mozilla Firefox 中查看报表时，无法显示 "AGPM 设置" 和 "差异" 报表右侧的 "**显示**" 和 "**隐藏**" 选项卡。

**解决方法：** 通过使用 Internet Explorer 浏览器查看报表。

### AGPM 设置和差异报表可能显示 GPMC 报表中的不同内容

AGPM 设置和差异报表可能不会显示与 GPMC 中的报表相同的内容。

**解决方法：** 使用 GPMC 查看 AGPM 报告。

### 如果域控制器处于离线状态，则 AGPM 服务不会启动

在 Windows®8操作系统或更高版本操作系统上的域控制器上安装了 AGPM 服务时，如果域控制器脱机，则该服务不会启动。

**解决方法：** 在域控制器联机后手动启动 AGPM 服务。

### 从 AGPM 4.0 版本和 hotfix1 升级 AGPM 服务器时，将阻止将 AGPM 服务器升级到 AGPM 4.0 SP2

如果你尝试将 AGPM 服务器升级到 AGPM 4.0。 安装了 AGPM 4.0 Server 后安装了 agpm 服务器，然后安装了名为 AGPM 4.0 的 AGPM 修复程序报告 HTML 报表中不正确的差异（请参阅知识库文章[2643502](https://go.microsoft.com/fwlink/?LinkId=254474)），升级失败，无法完成。

**解决方法：** 卸载 AGPM 4.0 服务器，然后安装 AGPM 4.0 SP2。

### 报表不显示组织单位链接

如果将不受管理的 GPO 链接到组织单元，然后使用 AGPM 控制该 GPO，则 AGPM 设置和差异报告不会显示组织单位链接。

**解决方法：** 在 "**更改设置**" 节点的 "**受控**" 选项卡上，右键单击该 GPO，单击 "**设置**"，然后单击 " **GPO 链接**" 以查看组织链接。 或者，你可以使用 GPMC 从 "**范围**" 选项卡查看指向 GPO 的链接。

### 如果单击 "更改"、"修复" 或 "删除 AGPM 客户端" 对话框中的 "后退" 按钮，则 AGPM 将显示错误

如果在 "控制面板" 中浏览到 "**程序和功能**"，然后选择 " **Microsoft 高级组策略管理-客户端**"，则如果单击 "**修改**"，然后单击 "**更改、修复或删除 AGPM 客户端**" 对话框中的 "**返回**" 按钮，则 AGPM 会显示错误。

**解决方法：** 单击 "**取消**" 以清除错误，然后再次启动流程。 单击 "**修改**" 后，请不要单击 "**返回**" 按钮。

### 当审批者部署 GPO 并输入注释时，批注不会显示在 "历史记录" 窗口中

如果具有编辑器角色的用户提交了一个部署 GPO 的请求，并且拥有审批者角色的用户随后部署该 GPO 并输入注释，则注释将无法在 "**历史记录**" 窗口中显示。

**解决方法：** 尚.

## 相关主题


[高级组策略管理](index.md)

[AGPM 4.0 SP2 中的新增功能](whats-new-in-agpm-40-sp2.md)

 

 





