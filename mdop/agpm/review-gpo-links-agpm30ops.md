---
title: 查看 GPO 链接
description: 查看 GPO 链接
author: dansimp
ms.assetid: 5ae95afc-2b89-45cf-916c-efe2d43b2211
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6532a669c6841c2342514c0911f74bc0b1fbc86d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801784"
---
# 查看 GPO 链接


你可以显示一个图表，显示你选择的组策略对象（GPO）或 Gpo 链接到组织单位的位置。 每次控制、导入或签入 GPO 时，GPO 链接图都会更新。

需要具有 "审阅者"、"编辑"、"审批者" 或 "AGPM 管理员（完全控制）" 角色或 "高级组策略管理" （AGPM）中的必要权限才能完成此过程的用户帐户。 查看本主题中 "其他注意事项" 中的详细信息。

## 查看 GPO 链接


-   [对于一个或多个 Gpo](#bkmk-gpos)

-   [对于一个或多个 GPO 版本](#bkmk-gpo-versions)

### <a href="" id="bkmk-gpos"></a>

**显示一个或多个 Gpo 的 GPO 链接**

1.  在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。

2.  在 "详细信息" 窗格中的 "**目录**" 选项卡上，单击 "**受控**"、"**挂起**" 或 "**回收站**" 选项卡以显示 gpo。

3.  选择要为其显示链接的一个或多个 Gpo，右键单击所选 GPO，单击 "**设置**"，然后单击 " **GPO 链接**" 以显示包含指向所选 gpo 的链接的域和组织单位的图表。

### <a href="" id="bkmk-gpo-versions"></a>

**显示 GPO 的一个或多个版本的 GPO 链接**

1.  在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。

2.  在 "详细信息" 窗格中的 "**目录**" 选项卡上，单击 "**受控**" 或 "**回收站**" 选项卡以显示 gpo。

3.  双击该 GPO 以显示其历史记录。

4.  右键单击要查看其设置的 GPO 版本，单击 "**设置**"，然后单击 " **HTML 报表**" 或 " **XML 报表**" 以显示 GPO 设置的摘要。

### 其他注意事项

-   默认情况下，你必须是审阅者、编辑者、审批者或 AGPM 管理员（完全控制）才能执行此过程。 具体而言，您必须具有该 GPO 的 "**列表内容**" 和 "**读取设置**" 权限。 此外，若要显示 Gpo 的列表，您必须拥有该域的 "**列表内容**" 权限。

### 其他参考资料

-   [执行审阅者任务](performing-reviewer-tasks-agpm30ops.md)

 

 





