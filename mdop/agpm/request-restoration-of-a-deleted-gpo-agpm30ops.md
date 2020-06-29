---
title: 请求还原已删除的 GPO
description: 请求还原已删除的 GPO
author: dansimp
ms.assetid: dcc3baea-8af7-4886-a301-98b6ac5819cd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f85620ed7d9afe676caabe4ce0f7da4fd8d5ae13
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802588"
---
# 请求还原已删除的 GPO


除非你是审批者或 AGPM 管理员（完全控制），否则你必须请求从回收站还原已删除的组策略对象（GPO），以将其返回到存档。

需要高级组策略管理（AGPM）中具有编辑器角色或必需权限的用户帐户才能完成此过程。 查看本主题中 "其他注意事项" 中的详细信息。

**请求还原已删除的 GPO**

1.  在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。

2.  在 "**目录**" 选项卡上，单击 "**回收站**" 选项卡以显示已删除的 gpo。

3.  右键单击要还原的 GPO，然后单击 "**还原**"。

4.  除非你拥有还原 Gpo 的特殊权限，否则你必须提交已删除 GPO 的还原请求。 若要接收请求的副本，请在 "**抄送**" 字段中键入您的电子邮件地址。 键入要显示在 GPO 审核跟踪中的注释，然后单击 "**提交**"。

5.  当**进度**窗口指示整个进度完成时，单击 "**关闭**"。 该 GPO 将从 "**回收站**" 选项卡中删除，并显示在 "**受控**" 选项卡上。

**注意** 如果从生产环境中删除了某个 GPO，则将其还原到存档不会自动将其重新部署到生产环境。 若要将 GPO 返回到生产环境，请部署 GPO。 有关信息，请参阅[部署 GPO](deploy-a-gpo-agpm30ops.md)。

 

### 其他注意事项

-   默认情况下，你必须是编辑器才能执行此过程。 具体而言，您必须具有该 GPO 的 "**列表内容**" 和 "**编辑设置**" 权限。

-   若要撤消已批准的请求，请单击 "**挂起**" 选项卡。右键单击该 GPO，然后单击 "**撤消**"。 GPO 将返回到 "**回收站**" 选项卡。

### 其他参考资料

-   [删除、还原或销毁 GPO](deleting-restoring-or-destroying-a-gpo-agpm30ops.md)

 

 





