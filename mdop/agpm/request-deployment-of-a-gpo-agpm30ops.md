---
title: 请求部署 GPO
description: 请求部署 GPO
author: dansimp
ms.assetid: f44ae0fb-bcf7-477b-b99e-9dd6a55ee597
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7c8d1ac1ab157f744a6d5f2ede9bb281b553f718
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801816"
---
# 请求部署 GPO


修改并签入组策略对象（GPO）后，部署 GPO，以便它在生产环境中生效。

需要高级组策略管理（AGPM）中具有编辑器角色或必需权限的用户帐户才能完成此过程。 查看本主题中 "其他注意事项" 中的详细信息。

**请求将 GPO 部署到生产环境**

1.  在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。

2.  在 "**目录**" 选项卡上，单击 "**受控**" 选项卡以显示受控 gpo。

3.  右键单击要部署的 GPO，然后单击 "**部署**"。

4.  除非你是审批者或 AGPM 管理员或具有部署 Gpo 的特殊权限，否则你必须提交部署请求。 若要接收请求的副本，请在 "**抄送**" 字段中键入您的电子邮件地址。 键入要在 GPO 的**历史记录**中显示的注释，然后单击 "**提交**"。

5.  当**进度**窗口指示整个进度完成时，单击 "**关闭**"。 GPO 将显示在 "**挂起**" 选项卡上的 gpo 列表中。当审批者批准你的请求后，GPO 将从 "**挂起**" 选项卡移到 "已**控制**" 选项卡并进行部署。

### 其他注意事项

-   默认情况下，你必须是编辑器才能执行此过程。 具体而言，您必须具有该 GPO 的 "**列表内容**" 和 "**编辑设置**" 权限。

-   若要撤消已批准的请求，请单击 "**挂起**" 选项卡。右键单击该 GPO，然后单击 "**撤消**"。 GPO 将返回到 "**受控**" 选项卡。

### 其他参考资料

-   [编辑 GPO](editing-a-gpo-agpm30ops.md)

 

 





