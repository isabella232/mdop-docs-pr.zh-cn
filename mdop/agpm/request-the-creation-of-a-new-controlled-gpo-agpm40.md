---
title: 请求创建新的受控 GPO
description: 请求创建新的受控 GPO
author: dansimp
ms.assetid: cb265238-386f-4780-a59a-0c9a4a87d736
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 85a435f84e055013c5100a720377f4bffaef4319
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802568"
---
# 请求创建新的受控 GPO


除非你是审批者或 AGPM 管理员（完全控制），否则你必须请求创建新的组策略对象（GPO）。

需要高级组策略管理（AGPM）中具有编辑者或审阅者角色或必需权限的用户帐户才能完成此过程。 查看本主题中 "其他注意事项" 中的详细信息。

**使用通过 AGPM 管理的更改控制创建新 GPO**

1.  在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。

2.  右键单击 "**更改控件**"，然后单击 "**新建受控制的 GPO**"。

3.  除非你有创建 Gpo 的特殊权限，否则你必须提交创建请求。 在 "**新建受控 GPO** " 对话框中：

    1.  若要接收请求的副本，请在 "**抄送**" 字段中输入您的电子邮件地址。

    2.  键入新 GPO 的名称。

    3.  可选：键入新 GPO 的注释。

    4.  若要在批准后立即将新 GPO 部署到域的生产环境中，请单击 "**创建 live**"。 若要将新的 GPO 脱机创建而不在批准后立即进行部署，请单击 "**脱机创建**"。

    5.  选择要用作新 GPO 的起始点的 GPO 模板。

    6.  单击**提交**。

4.  当**进度**窗口指示整个进度完成时，单击 "**关闭**"。 新的 GPO 将显示在 "**挂起**" 选项卡上的 gpo 列表中。当审批者批准你的请求后，GPO 将移到 "已**控制**" 选项卡。

### 其他注意事项

-   默认情况下，你必须是编辑者或审阅者才能执行此过程。 具体而言，您必须具有域的 "**列表内容**" 权限。

-   若要撤消已批准的请求，请单击 "**挂起**" 选项卡。右键单击该 GPO，然后单击 "**撤消**"。 GPO 将被破坏。

### 其他参考资料

-   [创建或控制 GPO](creating-or-controlling-a-gpo-agpm40-ed.md)

 

 





