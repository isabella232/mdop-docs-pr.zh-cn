---
title: “AGPM 服务器”选项卡
description: “AGPM 服务器”选项卡
author: dansimp
ms.assetid: a6689437-233e-4f33-a0d6-f7d432c96c00
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7ffaa3f55d4ae1c2a59287d9dc302aec3dd00aed
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802155"
---
# “AGPM 服务器”选项卡


通过 "**更改控制**" 窗格上的 " **AGPM 服务器**" 选项卡，你可以通过输入完全限定的计算机名称和端口来选择 AGPM 服务器，还可以从存档中删除较旧版本的组策略对象（gpo），以节省 agpm 服务器上的磁盘空间。

## 指定 AGPM 服务器


所选的 AGPM 服务器决定在 "**目录**" 选项卡上显示的存档，以及应用**域委派**设置的位置。 高级组策略管理（AGPM）的默认端口是端口4600。

如果 AGPM 服务器连接是使用管理模板设置进行集中配置的，则此选项卡上用于配置连接的选项不可用。 有关详细信息，请参阅[配置 AGPM 服务器连接](configure-agpm-server-connections-agpm40.md)。

## 删除旧 GPO 版本


默认情况下，每个受控制的 GPO 的所有版本都将保留在存档中。 但是，你可以配置 AGPM 服务以限制每个 GPO 的保留版本数，并在超过该限制时自动删除最早的版本。 仅在 "**历史记录**" 窗口的 "**唯一版本**" 选项卡上显示的 GPO 版本将计为 "限制"。

**注意** 要为每个 GPO 存储的唯一版本的最大数量不包括当前版本，因此输入0仅保留当前版本。 该限制不得超过999个版本。

删除 GPO 版本后，该版本的记录将保留在 GPO 的历史记录中，但 GPO 版本本身将从存档中删除。 你可以通过在历史记录中将其标记为不可删除来阻止删除 GPO 版本。

 

### 其他参考资料

-   [用户界面：高级组策略管理](user-interface-advanced-group-policy-management-agpm40.md)

-   [执行 AGPM 管理员任务](performing-agpm-administrator-tasks-agpm40.md)

-   [执行审阅者任务](performing-reviewer-tasks-agpm40.md)

 

 





