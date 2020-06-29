---
title: 重命名 GPO 或模板
description: 重命名 GPO 或模板
author: dansimp
ms.assetid: 19d17ddf-8b58-4677-929e-9550fa388b93
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 44d1cef33d8c0004ef3639311fbf135b4dea9d39
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801848"
---
# 重命名 GPO 或模板


你可以重命名受控制的组策略对象（GPO）或模板。

具有编辑器或 AGPM 管理员（完全控制）角色的用户帐户、创建 GPO 的审批者的用户帐户，或者需要高级组策略管理（AGPM）中具有必要权限的用户帐户才能完成此过程。 查看本主题中 "其他注意事项" 中的详细信息。

**重命名 GPO 或模板**

1.  在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。

2.  在 "**目录**" 选项卡上，单击 "**受控**模板" 或 "**模板**" 选项卡以显示要重命名的项目。

3.  右键单击要重命名的 GPO 或模板，然后单击 "**重命名**"。

4.  键入 GPO 或模板的新名称和注释，然后单击 **"确定"**。

5.  当**进度**窗口指示整个进度完成时，单击 "**关闭**"。 GPO 或模板将显示在 "**目录**" 选项卡上的新名称下。

### 其他注意事项

-   默认情况下，你必须是创建或控制 GPO、编辑器或 AGPM 管理员（完全控制）的审批者才能执行此过程。 具体而言，您必须具有该 GPO 的 "**列表内容**" 和 "**编辑设置**" 权限。

-   重命名已部署的 GPO 时，将立即在存档中更改名称。 只有重新部署 GPO 时，才会在生产环境中更改名称。 重新部署 GPO （或删除生产副本）之前，旧名称仍将在生产环境中使用，因此不能用于另一个 GPO。 同样，在部署 GPO （更改生产副本的名称）或生产副本已被删除之前，不能将存档中的 GPO 重命名回其原始名称。

### 其他参考资料

-   [编辑 GPO](editing-a-gpo-agpm30ops.md)

 

 





