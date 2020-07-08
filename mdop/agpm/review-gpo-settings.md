---
title: 查看 GPO 设置
description: 查看 GPO 设置
author: dansimp
ms.assetid: e82570b2-d8ce-4bf0-8ad7-8910409f3041
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 681492f423266ce3722bb1a657ee93527c6bdd7b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801775"
---
# 查看 GPO 设置


你可以生成基于 HTML 的报表和基于 XML 的报表，用于查看任何版本的组策略对象（GPO）内的设置。

需要具有审阅者、编辑者或 AGPM 管理员（完全控制）角色的用户帐户或高级组策略管理中的必需权限才能完成此过程。 查看本主题中 "其他注意事项" 中的详细信息。

**查看 GPO 的任何版本中的设置**

1.  在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。

2.  在 "详细信息" 窗格中的 "**目录**" 选项卡上，单击选项卡以显示 gpo。

3.  双击该 GPO 以显示其历史记录。

4.  右键单击要查看其设置的 GPO 版本，单击 "**设置**"，然后单击 " **HTML 报表**" 或 " **XML 报表**" 以显示 GPO 设置的摘要。

### 其他注意事项

-   默认情况下，你必须是审阅者、编辑者、审批者或 AGPM 管理员（完全控制）才能执行此过程。 具体而言，您必须具有该 GPO 的 "**列表内容**" 和 "**读取设置**" 权限。 此外，若要显示 Gpo 的列表，您必须拥有该域的 "**列表内容**" 权限。

### 其他参考资料

-   [执行审阅者任务](performing-reviewer-tasks.md)

 

 





