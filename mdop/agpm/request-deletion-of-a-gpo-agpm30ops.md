---
title: 请求删除 GPO
description: 请求删除 GPO
author: dansimp
ms.assetid: 576ece5c-dc6d-4b5e-8628-01c15ae2c9a8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 87368d9f132d1ef7dc6a70fffa0611d33a23aa78
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801819"
---
# 请求删除 GPO


除非你是审批者或 AGPM 管理员（完全控制），否则你必须请求删除组策略对象（GPO）。

需要高级组策略管理（AGPM）中具有编辑器角色或必需权限的用户帐户才能完成此过程。 查看本主题中 "其他注意事项" 中的详细信息。

**请求删除受控 GPO**

1.  在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。

2.  在 "**目录**" 选项卡上，单击 "**受控**" 选项卡以显示受控 gpo。

3.  右键单击要删除的 GPO，然后单击 "**删除**"。

    -   若要从存档中删除 GPO，同时在生产环境中保持 GPO 的部署版本，请单击 "**仅从存档中删除 gpo**"。

    -   若要从存档和生产环境中删除 GPO，请单击 "**从存档和生产中删除 gpo**"。

4.  除非你有删除 Gpo 的特殊权限，否则你必须提交删除已部署 GPO 的请求。 若要接收请求的副本，请在 "**抄送**" 字段中键入您的电子邮件地址。 键入要显示在 GPO 审核跟踪中的注释，然后单击 "**提交**"。

5.  当**进度**窗口指示整个进度完成时，单击 "**关闭**"。 GPO 将显示在 "**挂起**" 选项卡上的 gpo 列表中。当审批者批准你的请求后，GPO 将从 "**挂起**" 选项卡移动到 "**回收站**" 选项卡，可在该选项卡上还原或销毁。

### 其他注意事项

-   默认情况下，你必须是编辑器才能执行此过程。 具体而言，您必须具有该 GPO 的 "**列表内容**" 和 "**编辑设置**" 权限。

-   若要撤消已批准的请求，请单击 "**挂起**" 选项卡。右键单击该 GPO，然后单击 "**撤消**"。 GPO 将返回到 "**受控**" 选项卡。

-   若要从生产环境中删除不受管理的 GPO 而不先对其进行控制，请在**组策略管理控制台**中单击 "**林**"，单击 "**域**"，单击 " ** &lt; MyDomain &gt; **"，然后单击 "**组策略对象**"。 右键单击不受控制的 GPO，然后单击 "**删除**"。

### 其他参考资料

-   [执行编辑者任务](performing-editor-tasks-agpm30ops.md)

 

 





