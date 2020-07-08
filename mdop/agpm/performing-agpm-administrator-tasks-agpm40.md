---
title: 执行 AGPM 管理员任务
description: 执行 AGPM 管理员任务
author: dansimp
ms.assetid: bc746f39-bdc9-4e2a-bc48-c3c7905de098
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 609b5b8b27fe24ff93e86bea7113929b1e04984d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803164"
---
# 执行 AGPM 管理员任务


高级组策略管理（AGPM）允许 AGPM 管理员（完全控制）配置域范围的选项以及将权限委派给审批者、编辑者、审阅者和 AGPM 管理员。 默认情况下，AGPM 管理员是拥有 "完全控制" 权限的人员（所有 AGPM 权限），以及因此可以执行与任何角色相关联的任务。

在多个用户开发组策略对象（Gpo）的环境中，你可以选择让所有组策略管理员执行相同的任务并具有相同级别的访问权限。 或者，你可以选择让 AGPM 管理员委派权限来编辑可更改 Gpo 的权限，以及将 Gpo 部署到生产环境的审批者的权限。 AGPM 管理员可以配置权限以满足组织的需求。

-   [配置高级组策略管理](configuring-advanced-group-policy-management-agpm40.md)：配置 AGPM 服务器连接和电子邮件通知、委派对生产环境中的 gpo 的访问权限，以及配置日志记录和跟踪以进行故障排除。

-   [管理存档](managing-the-archive-agpm40.md)：委派对存档中的 gpo 的访问、限制存储的每个 gpo 的版本数、从另一个域导入 gpo 以及备份和还原存档。

-   [管理 Agpm 服务](managing-the-agpm-service-agpm40.md)：停止和启动 AGPM 服务，或者更改已存档路径、Agpm 服务帐户或 agpm 服务侦听的端口。

-   [移动 Agpm 服务器和存档](move-the-agpm-server-and-the-archive-agpm40.md)：将 agpm 服务、存档或两者移动到其他服务器。

**注意** 由于 AGPM 管理员角色包括所有其他角色的权限，因此 AGPM 管理员可以执行通常与任何其他角色相关联的任务。

[执行审批者任务](performing-approver-tasks-agpm40.md)，例如创建、部署或删除 gpo

执行编辑、重命名、标记或导入 Gpo、创建模板或设置默认模板的[编辑器任务](performing-editor-tasks-agpm40.md)

[执行审阅者任务](performing-reviewer-tasks-agpm40.md)，例如审阅设置和比较 gpo

 

### 其他注意事项

默认情况下，AGPM 管理员角色具有 "完全控制" （所有 AGPM 权限）：

-   列表内容

-   读取设置

-   编辑设置

-   创建 GPO

-   部署 GPO

-   删除 GPO

-   导出 GPO

-   导入 GPO

-   创建模板

-   修改选项

-   修改安全性

"**修改选项**" 和 "**修改安全**权限" 对于 AGPM 管理员的角色是唯一的。

 

 





