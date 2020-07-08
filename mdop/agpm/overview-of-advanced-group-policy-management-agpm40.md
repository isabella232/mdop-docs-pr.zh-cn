---
title: 高级组策略管理概述
description: 高级组策略管理概述
author: dansimp
ms.assetid: 2c12f3b4-8472-4c5b-b7f8-1c98a80d6b47
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 94e47075ae865096f9fe7d327cc7b11cb54217d6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803178"
---
# 高级组策略管理概述


你可以使用高级组策略管理（AGPM）扩展组策略管理控制台（GPMC）的功能，以便为组策略对象（Gpo）提供全面的更改控制和改进的管理。

## 带有更改控制的组策略对象开发


使用 AGPM，你可以将每个 GPO 的副本存储在一个中央存档中，以便组策略管理员可以在不立即影响 GPO 的已部署版本的情况下查看和更改它。 此外，AGPM 将在存档中存储每个受控制 GPO 版本的副本，以便你可以在需要时回滚到早期版本。

"签入" 和 "签出" 一词的使用方式与在库中（或提供用于编程开发的更改控制、版本控制或源代码管理）的应用程序中一样。 若要使用库中的书籍，请将其从库中签出。 签出后，其他人都无法使用它。完成本书后，请将其签回库，以便其他人可以使用它。

若要使用这些 GPO 控制功能，您将在 "组策略管理编辑器" 中单击 "更改控制" 节点。 仅当安装了 AGPM 客户端时，才会显示 "更改控制" 节点。

使用 AGPM 开发 Gpo 时：

1.  创建新的受控 GPO 或控制以前不受管理的 GPO。

2.  签出 GPO，以便你和你可以更改它。

3.  编辑 GPO。

4.  签入编辑后的 GPO，以便其他人可以对其进行更改，也可以将其部署。

5.  查看更改。

6.  将 GPO 部署到生产环境。

## 基于角色的委派


AGPM 提供了全面、易于使用的基于角色的委派，可用于管理对存档中的 Gpo 的访问。 域级权限使 AGPM 管理员可以在不提供对其他域的访问权限的情况下提供对单个域的访问权限。 基于 GPO 的委派使 AGPM 管理员能够提供对特定 Gpo 的访问权限，而无需提供域范围的访问权限。

在 AGPM 内，有一些专门定义的角色： AGPM 管理员（完全控制）、审批者、编辑者和审阅者。 AGPM 管理员角色包括所有其他角色的权限。 默认情况下，只有审批者有能力将 Gpo 部署到域的生产环境，通过较少经验的编辑器保护环境不受错误。 此外，默认情况下，所有角色都包含审阅者角色，因此能够在报表中查看 GPO 设置。 但是，AGPM 为 AGPM 管理员提供了自定义 GPO 访问的灵活性，以满足组织的需求。

## 多组策略管理员环境中的委派


在多个用户更改 Gpo 的环境中，AGPM 管理员将权限作为组或个人委派给编辑者、审批者和审阅者。 有关编辑器和审批者的典型 GPO 开发过程，请参阅[清单：创建、编辑和部署 GPO](checklist-create-edit-and-deploy-a-gpo-agpm40.md)。

### 其他参考资料

-   [高级组策略管理 4.0](advanced-group-policy-management-40.md)

 

 





