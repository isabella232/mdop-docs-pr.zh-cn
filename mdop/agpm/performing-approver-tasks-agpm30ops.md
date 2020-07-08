---
title: 执行审批者任务
description: 执行审批者任务
author: dansimp
ms.assetid: 9f711824-191b-4b4b-a1c6-a3b2116006a4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d8e4a848608a3be1dbb0632f0145b4fc1d1bc631
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802631"
---
# 执行审批者任务


审批者是由 AGPM 管理员（完全控制）授权的人员，用于创建、部署和删除组策略对象（Gpo），以及批准或拒绝请求（通常来自编辑者）来创建、部署或删除 Gpo。

**重要提示** 请确保你连接到 Gpo 的中心存档。 有关详细信息，请参阅[配置 AGPM 服务器连接](configure-an-agpm-server-connection-reviewer-agpm30ops.md)。

 

-   [批准或拒绝挂起的操作](approve-or-reject-a-pending-action-agpm30ops.md)

-   [创建、控制或导入 GPO](creating-controlling-or-importing-a-gpo-editor-agpm30ops.md)

-   [签入 GPO](check-in-a-gpo-agpm30ops.md)

-   [部署 GPO](deploy-a-gpo-agpm30ops.md)

-   [回滚到以前版本的 GPO](roll-back-to-a-previous-version-of-a-gpo-agpm30ops.md)

-   [删除、还原或销毁 GPO](deleting-restoring-or-destroying-a-gpo-agpm30ops.md)

**注意** 在批准 GPO 之前，审批者应检查它所包含的策略设置。 审批者角色包括审阅者角色的权限，以便审批者可以查看策略设置和比较 Gpo。 有关详细信息，请参阅[执行审阅者任务](performing-reviewer-tasks-agpm30ops.md)。

 

### 其他注意事项

默认情况下，为审批者角色提供以下权限：

-   列表内容

-   读取设置

-   创建 GPO

-   部署 GPO

-   删除 GPO

此外，审批者对他创建或控制的 Gpo 拥有完全控制权。

 

 





