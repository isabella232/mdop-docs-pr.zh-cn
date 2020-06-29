---
title: 配置 AGPM 服务器连接
description: 配置 AGPM 服务器连接
author: dansimp
ms.assetid: ae78dc74-111d-4509-b0a6-e8b8b451c22a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 50968d8b1b1eb5d464c6dbdb251354a9dc691d62
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802044"
---
# 配置 AGPM 服务器连接


若要确保已连接到正确的中心存档，请查看 AGPM 服务器连接的配置。 如果 AGPM 管理员（完全控制）尚未为你配置 AGPM 服务器连接，则必须手动配置它。

**选择 AGPM 服务器**

1.  在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。

2.  在 "详细信息" 窗格中，单击 " **AGPM 服务器**" 选项卡：

    -   如果 " **Agpm 服务器**" 选项卡上的选项不可用，则是由 AGPM 管理员集中配置的。

    -   如果 " **Agpm server** " 选项卡上的选项可用，请键入 agpm 服务器的完全限定的计算机名称（例如，server.contoso.com）和 agpm 服务侦听的端口（默认情况下为端口4600）。 单击 "**应用**"，然后单击 **"是"** 进行确认。

### 其他注意事项

-   所选的 AGPM 服务器确定在 "**目录**" 选项卡上显示哪些 gpo 以及应用 "**域委派**" 选项卡设置的位置。 如果不是通过管理模板进行集中管理，则每个组策略管理员必须将此设置配置为指向域的 AGPM 服务器。

### 其他参考资料

-   [执行编辑者任务](performing-editor-tasks-agpm30ops.md)

-   [执行审批者任务](performing-approver-tasks-agpm30ops.md)

-   [执行审阅者任务](performing-reviewer-tasks-agpm30ops.md)

 

 





