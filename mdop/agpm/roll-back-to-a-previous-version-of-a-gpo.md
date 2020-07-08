---
title: 回滚到以前版本的 GPO
description: 回滚到以前版本的 GPO
author: dansimp
ms.assetid: 028631c0-4cb9-4642-90ad-04cd813051b7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a71740eaa60a4b1292e47ca8aa57d4657231ab57
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802555"
---
# 回滚到以前版本的 GPO


通过高级组策略管理（AGPM），审批者可以通过从其历史记录重新部署 GPO 的早期版本来回退对组策略对象（GPO）的更改。 部署早期版本的 GPO 会覆盖当前生产中的 GPO 版本。

需要具有审批者或 AGPM 管理员（完全控制）角色的用户帐户或高级组策略管理中的必要权限才能完成此过程。 查看本主题中 "其他注意事项" 中的详细信息。

**将 GPO 的以前版本部署到生产环境**

1.  在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。

2.  在 "**目录**" 选项卡上，单击 "**受控**" 选项卡以显示受控 gpo。

3.  双击要部署的 GPO 以显示其**历史记录**。

4.  右键单击要部署的版本，单击 "**部署**"，然后单击 **"是"**。

5.  当**进度**窗口指示整个进度完成时，单击 "**关闭**"。 在 "**历史记录**" 窗口中，单击 "**关闭**"。

**注意** 若要验证已重新部署的版本是否与所需版本相匹配，请检查这两个版本的差异报告。 在 GPO 的 "**历史记录**" 窗口中，突出显示两个版本，然后右键单击并选择 "**差异**" 和 " **HTML 报表**" 或 " **XML 报表**"。

 

### 其他注意事项

-   默认情况下，你必须是审批者或 AGPM 管理员（完全控制）才能执行此过程。 具体而言，您必须拥有**列表内容**并为 GPO**部署 gpo**权限。

### 其他参考资料

-   [执行审批者任务](performing-approver-tasks.md)

 

 





