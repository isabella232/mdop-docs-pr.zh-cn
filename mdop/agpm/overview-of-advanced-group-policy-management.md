---
title: 高级组策略管理概述
description: 高级组策略管理概述
author: dansimp
ms.assetid: 028de9dd-848b-42bc-a982-65ba5c433772
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 38396de6bd8bdace72d3add1bba09769ae26de32
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803177"
---
# 高级组策略管理概述


你可以使用高级组策略管理（AGPM）扩展组策略管理控制台（GPMC）的功能，从而为组策略对象（Gpo）提供全面的更改控制和增强的管理。

## 带有更改控制的组策略对象开发


利用 AGPM，你可以将每个 GPO 的副本存储在一个中心存档中，以便组策略管理员可以在不立即影响到已部署的 GPO 的版本的情况下查看和修改它。 此外，AGPM 将在存档中存储每个受控制 GPO 版本的副本，以便你可以在需要时回滚到早期版本。

术语 "签入" 和 "签出" 的使用方式与在库中（或提供用于编程开发的更改控制、版本控制或源代码管理的应用程序）大致相同。 若要使用库中的书籍，请将其从库中签出。 签出后，其他人都无法使用它。完成本书后，请将其签回库，以便其他人可以使用它。

使用 AGPM 开发 Gpo 时：

1.  创建新的受控 GPO 或控制以前不受管理的 GPO。

2.  签出 GPO，以便你和你可以对其进行修改。

3.  编辑 GPO。

4.  签入编辑后的 GPO，以便其他人可以对其进行修改，或者可对其进行部署。

5.  查看更改。

6.  将 GPO 部署到生产环境。

## 基于角色的委派


AGPM 提供了全面、易于使用的基于角色的委派。 域级权限允许 AGPM 管理员提供对单个域的访问权限，而无需提供对其他域的访问权限。 基于 GPO 的委派使 AGPM 管理员可以仅访问特定 Gpo。

在 AGPM 内，有一些专门定义的角色： AGPM 管理员（完全控制）、审批者、编辑者和审阅者。 AGPM 管理员角色包括所有其他角色的权限。 默认情况下，仅审批者有能力将 Gpo 部署到生产环境，保护环境不受经验较少的编辑器意外出错。 此外，默认情况下，所有角色都包含审阅者角色，因此能够在报表中查看 GPO 设置。 但是，AGPM 为 AGPM 管理员提供了自定义 GPO 访问的灵活性，以满足组织的需求。

## 多组策略管理员环境中的委派


在多个用户对 Gpo 进行更改的环境中，AGPM 管理员将权限作为组或个人委派给编辑者、审批者和审阅者。 有关编辑器和审批者的典型 GPO 开发过程，请参阅[清单：创建、编辑和部署 GPO](checklist-create-edit-and-deploy-a-gpo.md)。

### 其他参考资料

-   [清单：创建、编辑和部署 GPO](checklist-create-edit-and-deploy-a-gpo.md)

-   [执行 AGPM 管理员任务](performing-agpm-administrator-tasks.md)

-   [执行编辑者任务](performing-editor-tasks.md)

-   [执行审批者任务](performing-approver-tasks.md)

-   [执行审阅者任务](performing-reviewer-tasks.md)

-   [高级组策略管理疑难解答](troubleshooting-advanced-group-policy-management.md)

-   [用户界面：高级组策略管理](user-interface-advanced-group-policy-management.md)

 

 





