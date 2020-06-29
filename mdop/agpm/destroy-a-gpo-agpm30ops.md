---
title: 销毁 GPO
description: 销毁 GPO
author: dansimp
ms.assetid: bfabd71a-47f3-462e-b86f-5f15762b9e28
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 842a546c4db9cc6048908521baa05c6cc1a1a8a9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801915"
---
# 销毁 GPO


审批者可以销毁组策略对象（GPO），将其从回收站中删除并将其永久删除，以便不能再还原。

需要具有审批者或 AGPM 管理员（完全控制）角色的用户帐户或高级组策略管理（AGPM）中的必要权限才能完成此过程。 查看本主题中 "其他注意事项" 中的详细信息。

**永久删除 GPO，使其无法再还原**

1.  在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。

2.  在 "**目录**" 选项卡上，单击 "**回收站**" 选项卡以显示已删除的 gpo。

3.  右键单击要销毁的 GPO，然后单击 "**销毁**"。

4.  单击 **"是"** 以确认要从存档中永久删除所选 GPO 和所有备份。

5.  当**进度**窗口指示整个进度完成时，单击 "**关闭**"。 该 GPO 将从 "**回收站**" 选项卡中删除，并被永久删除。

### 其他注意事项

-   默认情况下，你必须是审批者或 AGPM 管理员（完全控制）才能执行此过程。 具体而言，您必须拥有**列表内容**并删除 GPO 的**gpo**权限。

### 其他参考资料

-   [删除、还原或销毁 GPO](deleting-restoring-or-destroying-a-gpo-agpm30ops.md)

 

 





