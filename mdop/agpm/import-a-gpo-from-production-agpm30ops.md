---
title: 从生产导入 GPO
description: 从生产导入 GPO
author: dansimp
ms.assetid: 35c2a682-ece8-4577-a083-7e3e9facfd13
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3d739a46d5ca078ec9d218c1cc1e5bd258c55601
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802727"
---
# 从生产导入 GPO


如果在高级组策略管理（AGPM）之外对受控组策略对象（GPO）进行了更改，则可以从生产环境导入该 GPO 的副本并将其保存到存档中，以使存档和生产环境处于一致状态。 （若要导入不受控制的 GPO，请控制该 GPO。 请参阅[请求控制不受控制的 GPO](request-control-of-an-uncontrolled-gpo-agpm30ops.md)。

具有 "编辑"、"审批者" 或 "AGPM 管理员（完全控制）" 角色或必需权限 inAGPM 的用户帐户需要完成此过程。 查看本主题中 "其他注意事项" 中的详细信息。

**从生产环境导入 GPO**

1.  在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。

2.  在 "**目录**" 选项卡上，单击 "**受控**" 选项卡以显示受控 gpo。

3.  右键单击该 GPO，然后单击 "**从生产导入**"。

4.  为 GPO 的审核跟踪键入注释，然后单击 **"确定"**。

### 其他注意事项

-   默认情况下，你必须是编辑者、审批者或 AGPM 管理员（完全控制）才能执行此过程。 具体而言，您必须具有**列表内容**，并且可以**编辑设置**、**部署 GPO**或删除 gpo 的**gpo**权限。

### 其他参考资料

-   [创建、控制或导入 GPO](creating-controlling-or-importing-a-gpo-agpm30ops.md)

 

 





