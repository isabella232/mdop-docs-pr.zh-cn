---
title: 委派针对 GPO 的访问权限
description: 委派针对 GPO 的访问权限
author: dansimp
ms.assetid: f1d6bb6c-d5bf-4080-a6cb-32774689f804
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 57a71528120b65676d25d952d9f9392dc0250ae4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801955"
---
# 委派针对 GPO 的访问权限


审批者可以委派**由该审批者创建**的受控组策略对象（GPO）的管理。 与 AGPM 管理员（完全控制）一样，审批者可以委派对此类 GPO 的访问权限，以便选定的编辑人员可以对其进行编辑、审阅者可以对其进行审阅，并且其他审批者可以对其进行审核。 默认情况下，审批者无法委派对由其他组策略管理员创建的 Gpo 的访问权限。

具有 AGPM 管理员（完全控制）角色的用户帐户、创建 GPO 的审批者的用户帐户，或者需要高级组策略管理中具有必需权限的用户帐户才能完成此过程。 查看本主题中 "其他注意事项" 中的详细信息。

**委派受控 GPO 的管理**

1.  在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。

2.  在 "详细信息" 窗格中的 "**目录**" 选项卡上，单击 "**受控**" 选项卡以显示 "受控 gpo"，然后单击要委派的 GPO。

3.  单击 "**添加**" 按钮，选择允许访问的用户或组，然后单击 **"确定"**。

4.  若要自定义每个权限的权限，请单击 "**目录**" 选项卡上的 "**高级**" 按钮，然后选中 "允许或拒绝" 角色权限。 （有关更多详细的控件，请单击 "**权限**" 对话框中的 "**高级**"。）

5.  单击 "**应用**"，然后在 "**权限**" 对话框中单击 **"确定"** 。

### 其他注意事项

-   默认情况下，你必须是创建或控制 GPO 的审批者或 AGPM 管理员（完全控制）才能执行此过程。 具体而言，您必须具有域的 "**列表内容**" 权限和 "修改 GPO 的**安全**权限"。

### 其他参考资料

-   [创建、控制或导入 GPO](creating-controlling-or-importing-a-gpo-approver.md)

 

 





