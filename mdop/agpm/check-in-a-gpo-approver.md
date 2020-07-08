---
title: 签入 GPO
description: 签入 GPO
author: dansimp
ms.assetid: e428cfff-651f-4903-bf01-d742714d2fa9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6adbcfa1c2b0d79389bc16dd1dde5afc0a4ec4a5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802100"
---
# 签入 GPO


通常情况下，编辑器应签入其修改完成后已编辑过的组策略对象（Gpo）。 （有关详细信息，请参阅在[脱机状态下编辑 GPO](edit-a-gpo-offline.md)。）但是，如果编辑器不可用，则审批者还可以签入 GPO。

必须具有编辑者、审批者或 AGPM 管理员（完全控制）角色的用户帐户或高级组策略管理中的必需权限才能完成此过程。 查看本主题中 "其他注意事项" 中的详细信息。

**签入由编辑器签出的 GPO**

1.  在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。

2.  在 "详细信息" 窗格中的 "**目录**" 选项卡上，单击 "**受控**" 选项卡以显示受控 gpo。

    -   若要放弃编辑器所做的任何更改，请右键单击该 GPO，单击 "**撤消签出**"，然后单击 **"是"** 进行确认。

    -   若要保留编辑器所做的更改，请右键单击该 GPO，然后单击 "**签入**"。

3.  键入要显示在 GPO 审核跟踪中的注释，然后单击 **"确定"**。

4.  当**进度**窗口指示整个进度完成时，单击 "**关闭**"。 在 "**受控**" 选项卡上，将 GPO 的状态标识为 **"已签入**"。

### 其他注意事项

-   默认情况下，你必须是编辑者、审批者或 AGPM 管理员（完全控制）才能执行此过程。 具体而言，您必须具有**列表内容**并**编辑设置**或为 gpo**部署 gpo**权限。 如果您不是审批者或 AGPM 管理员（或具有 "**部署 GPO**权限" 的其他组策略管理员），则您必须是已签出 GPO 的编辑器。

### 其他参考资料

-   [执行审批者任务](performing-approver-tasks.md)

-   [脱机编辑 GPO](edit-a-gpo-offline.md)

 

 





