---
title: 创建模板
description: 创建模板
author: dansimp
ms.assetid: 8208f14a-5c18-43a7-8564-118230398cca
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7f6713cd0fadb651e1de028bbcf2ae3ec1dd067c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802875"
---
# 创建模板


通过创建模板，你可以保存特定版本的组策略对象（GPO）的所有设置，以便将其用作创建新 Gpo 的起始点。

**注意** 模板是 GPO 的不可编辑的静态版本，用作创建新的可编辑 Gpo 的起始点。

 

需要具有编辑器或 AGPM 管理员（完全控制）角色的用户帐户或高级组策略管理（AGPM）中的必要权限才能完成此过程。 查看本主题中 "其他注意事项" 中的详细信息。

**基于现有 GPO 创建模板**

1.  在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。

2.  在 "详细信息" 窗格的 "**目录**" 选项卡上，单击 "**受控**" 或 "未**控制**" 选项卡以显示可用 gpo

3.  右键单击要从中创建模板的 GPO，然后单击 "**另存为模板**"。

4.  键入模板的名称和注释，然后单击 **"确定"**。

5.  当**进度**窗口指示整个进度完成时，单击 "**关闭**"。 新模板将显示在 "**模板**" 选项卡上。

### 其他注意事项

-   默认情况下，你必须是编辑器或 AGPM 管理员（完全控制）才能执行此过程。 具体而言，您必须拥有**列表内容**并为域**创建模板**权限。

-   重命名或删除模板不会影响从该模板创建的 Gpo。

-   由于不能对其进行更改，因此模板没有历史记录。

### 其他参考资料

-   [创建模板和设置默认模板](creating-a-template-and-setting-a-default-template-agpm30ops.md)

-   [请求创建新的受控 GPO](request-the-creation-of-a-new-controlled-gpo-agpm30ops.md)

 

 





