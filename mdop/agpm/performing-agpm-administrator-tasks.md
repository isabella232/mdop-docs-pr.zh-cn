---
title: 执行 AGPM 管理员任务
description: 执行 AGPM 管理员任务
author: dansimp
ms.assetid: 32e694a7-be64-4943-bce2-2a3a15e5341f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0daa8df93a88ed155e9f894011d4dd835761948b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802632"
---
# 执行 AGPM 管理员任务


AGPM 管理员（完全控制）配置域范围的选项并将权限委派给审批者、编辑者、审阅者和其他 AGPM 管理员。 默认情况下，AGPM 管理员是具有 "完全控制" （所有高级组策略管理 \ [AGPM \] 权限）的个人，因此还可以执行与任何角色相关联的任务。

在多人在其中开发组策略对象（Gpo）的环境中，可以选择所有高级组策略管理（AGPM）用户是否执行相同的任务以及是否具有相同的访问权限级别，或者 AGPM 管理员是否将权限委派给对 Gpo 以及向生产环境部署 Gpo 的审批者进行的更改。 AGPM 管理员可以配置权限以满足组织的需求。

-   [配置 AGPM 服务器连接](configure-the-agpm-server-connection.md)

-   [配置电子邮件通知](configure-e-mail-notification.md)

-   [委派域级访问权限](delegate-domain-level-access.md)

-   [委派针对单独 GPO 的访问权限](delegate-access-to-an-individual-gpo.md)

-   [配置记录和跟踪](configure-logging-and-tracing.md)

-   [管理 AGPM 服务](managing-the-agpm-service.md)

    -   [启动和停止 AGPM 服务](start-and-stop-the-agpm-service.md)

    -   [修改存档路径](modify-the-archive-path.md)

    -   [修改 AGPM 服务帐户](modify-the-agpm-service-account.md)

    -   [修改 AGPM 服务侦听的端口](modify-the-port-on-which-the-agpm-service-listens.md)

此外，由于 AGPM 管理员角色包括所有其他角色的权限，AGPM 管理员可以执行通常与任何其他角色相关联的任务。

-   [执行审批者任务](performing-approver-tasks.md)，例如创建、部署或删除 gpo

-   执行编辑、重命名、标记或导入 Gpo、创建模板或设置默认模板的[编辑器任务](performing-editor-tasks.md)

-   [执行审阅者任务](performing-reviewer-tasks.md)，例如审阅设置和比较 gpo

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

 

 





