---
title: 部署 GPO
description: 部署 GPO
author: dansimp
ms.assetid: a6febeaa-144b-4c02-99af-d972f0f2b544
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 208fd95ec48f81b6c3a2a59bf92f53128eb3d529
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801923"
---
# 部署 GPO


审批者可以将新的或已编辑的组策略对象（GPO）部署到生产环境。 有关重新部署 GPO 的早期版本的信息，请参阅回退[到较早版本的 gpo](roll-back-to-an-earlier-version-of-a-gpo-agpm40.md)。

需要具有审批者或 AGPM 管理员（完全控制）角色的用户帐户或高级组策略管理（AGPM）中的必要权限才能完成此过程。 查看本主题中 "其他注意事项" 中的详细信息。

**将 GPO 部署到生产环境**

1.  在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。

2.  在 "**目录**" 选项卡上，单击 "**受控**" 选项卡以显示受控 gpo。

3.  右键单击要部署的 GPO，然后单击 "**部署**"。

4.  若要查看指向该 GPO 的链接，请单击 "**高级**"。 将鼠标指针暂停在树中的某个项目上以显示详细信息。

    -   默认情况下，将还原指向该 GPO 的所有链接。

    -   若要阻止还原某个链接，请清除该链接的复选框。

    -   若要阻止还原所有链接，请清除 "**部署 GPO** " 对话框中的 "**还原链接**" 复选框。

5.  单击**是**。 当**进度**窗口指示整个进度完成时，单击 "**关闭**"。

**注意** 若要验证是否已部署 GPO 的最新版本，请在 "**受控**" 选项卡上，双击该 GPO 以显示其**历史记录**。 在 GPO 的**历史记录**中，"**状态**" 列指示是否已部署 gpo。

 

### 其他注意事项

-   默认情况下，你必须是审批者或 AGPM 管理员（完全控制）才能执行此过程。 具体而言，您必须拥有**列表内容**并为 GPO**部署 gpo**权限。

### 其他参考资料

-   [执行审批者任务](performing-approver-tasks-agpm40.md)

 

 





