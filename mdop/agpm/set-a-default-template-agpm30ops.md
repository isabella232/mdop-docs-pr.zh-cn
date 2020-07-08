---
title: 设置默认模板
description: 设置默认模板
author: dansimp
ms.assetid: 84edbd69-451b-4c10-a898-781d4b75d09c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dec198126e98e1267589fdf252e158a0b1181b05
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802544"
---
# 设置默认模板


作为编辑器，你可以指定哪些可用模板将用作为所有组策略管理员创建新组策略对象（Gpo）推荐的默认模板。

**注意** 模板是 GPO 的不可编辑的静态版本，用作创建新的可编辑 Gpo 的起始点。

 

需要具有编辑器或 AGPM 管理员（完全控制）角色的用户帐户或高级组策略管理（AGPM）中的必要权限才能完成此过程。 查看本主题中 "其他注意事项" 中的详细信息。

**设置创建新 Gpo 时使用的默认模板**

1.  在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。

2.  在 "详细信息" 窗格中的 "**目录**" 选项卡上，单击 "**模板**" 选项卡以显示可用模板。

3.  右键单击要设置为默认模板的模板，然后单击 "**设为默认值**"。

4.  单击 **"是"** 进行确认。

5.  当**进度**窗口指示整个进度完成时，单击 "**关闭**"。 默认模板有一个蓝色图标，在 "**模板**" 选项卡上，其状态标识为 "**模板（默认）** "。

### 其他注意事项

-   默认情况下，你必须是编辑器或 AGPM 管理员（完全控制）才能执行此过程。 具体而言，您必须拥有**列表内容**并为域**创建模板**权限。

-   将模板设置为默认值后，该模板将是初始在组策略管理员创建新 Gpo 时的 "**新建受控 GPO** " 对话框中所选的模板。 但是，它们将具有选择任何其他 GPO 模板的选项，包括不包含任何设置的** &lt; 空 gpo &gt; **。

-   重命名或删除模板不会影响从该模板创建的 Gpo。

-   由于不能对其进行更改，因此模板没有历史记录。

### 其他参考资料

-   [创建模板和设置默认模板](creating-a-template-and-setting-a-default-template-agpm30ops.md)

-   [请求创建新的受控 GPO](request-the-creation-of-a-new-controlled-gpo-agpm30ops.md)

 

 





