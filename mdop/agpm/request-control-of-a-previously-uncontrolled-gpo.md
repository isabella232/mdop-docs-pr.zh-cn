---
title: 请求控制以前不受控的 GPO
description: 请求控制以前不受控的 GPO
author: dansimp
ms.assetid: 00e8725d-5d7f-4eed-a5e6-c3631632cfbd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a92db48d87398568900fc0031e688c862a69b417
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801827"
---
# 请求控制以前不受控的 GPO


若要使用高级组策略管理（AGPM）为现有组策略对象（GPO）提供更改控制，则必须使用 AGPM 控制 GPO。 除非你是审批者或 AGPM 管理员（完全控制），否则你必须请求控制 GPO。

要完成此过程，需要具有编辑者或审阅者角色的用户帐户或高级组策略管理中的必需权限。 查看本主题中 "其他注意事项" 中的详细信息。

**控制以前的不受控制的 GPO**

1.  在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。

2.  在 "详细信息" 窗格中的 "**目录**" 选项卡上，单击 "未**控制**" 选项卡以显示非受控 gpo。

3.  右键单击要通过 AGPM 控制的 GPO，然后单击 "**控制**"。

4.  除非拥有控制 Gpo 的特殊权限，否则必须提交控制请求。 若要接收请求的副本，请在 "**抄送**" 字段中键入您的电子邮件地址。 键入要在 GPO 的**历史记录**中显示的注释，然后单击 "**提交**"。

5.  当**进度**窗口指示整个进度完成时，单击 "**关闭**"。 该 GPO 将从 "不可**控制**" 选项卡上的列表中删除，并添加到 "**挂起**" 选项卡。当审批者批准你的请求后，GPO 将移到 "已**控制**" 选项卡。

### 其他注意事项

-   默认情况下，你必须是编辑者或审阅者才能执行此过程。 具体而言，您必须具有 "**列表内容**" 和 "**读取设置**" 的域权限。

-   若要撤消已批准的请求，请单击 "**挂起**" 选项卡。右键单击该 GPO，然后单击 "**撤消**"。 GPO 将返回到 "不**受控制**" 选项卡。

### 其他参考资料

-   [创建、控制或导入 GPO](creating-controlling-or-importing-a-gpo-editor.md)

 

 





