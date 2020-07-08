---
title: 执行 AGPM 管理员任务
description: 执行 AGPM 管理员任务
author: dansimp
ms.assetid: 9678b0f4-70a5-411e-a896-afa4dc9ea6c4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 26b412e5b22e46af938d127751fdca1da722a8c6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803165"
---
# 执行 AGPM 管理员任务


在高级组策略管理（AGPM）中，AGPM 管理员（完全控制）配置域范围的选项以及将权限委派给审批者、编辑者、审阅者和其他 AGPM 管理员。 默认情况下，AGPM 管理员是拥有 "完全控制" 权限的个人（所有 AGPM 权限），以及因此可以执行与任何角色相关联的任务。

在多个用户开发组策略对象（Gpo）的环境中，你可以选择所有 AGPM 用户是否执行相同的任务以及是否具有相同的访问权限级别，或者 AGPM 管理员是否将权限委派给编辑 Gpo 和向生产环境部署 Gpo 的审批者。 AGPM 管理员可以配置权限以满足组织的需求。

-   [配置高级组策略管理](configuring-advanced-group-policy-management.md)：配置 AGPM 服务器连接和电子邮件通知、委派对生产环境中的 gpo 的访问权限，以及配置日志记录和跟踪以进行故障排除。

-   [管理存档](managing-the-archive.md)：委派对存档中的 gpo 的访问，并限制存储的每个 GPO 的版本数。

-   [管理 Agpm 服务](managing-the-agpm-service-agpm30ops.md)：停止和启动 AGPM 服务，或者更改已存档路径、Agpm 服务帐户或 agpm 服务侦听的端口。

-   [移动 Agpm 服务器和存档](move-the-agpm-server-and-the-archive.md)：将 agpm 服务、存档或两者移动到其他服务器。

此外，由于 AGPM 管理员角色包括所有其他角色的权限，AGPM 管理员可以执行通常与任何其他角色相关联的任务。

-   [执行审批者任务](performing-approver-tasks-agpm30ops.md)，例如创建、部署或删除 gpo

-   执行编辑、重命名、标记或导入 Gpo、创建模板或设置默认模板的[编辑器任务](performing-editor-tasks-agpm30ops.md)

-   [执行审阅者任务](performing-reviewer-tasks-agpm30ops.md)，例如审阅设置和比较 gpo

### 其他注意事项

默认情况下，AGPM 管理员角色具有 "完全控制" （所有 AGPM 权限）：

-   列表内容

-   读取设置

-   编辑设置

-   创建 GPO

-   部署 GPO

-   删除 GPO

-   修改选项

-   修改安全性

-   创建模板

"**修改选项**" 和 "**修改安全**权限" 对于 AGPM 管理员的角色是唯一的。

 

 





