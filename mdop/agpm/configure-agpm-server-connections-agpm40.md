---
title: 配置 AGPM 服务器连接
description: 配置 AGPM 服务器连接
author: dansimp
ms.assetid: bbbb15e8-35e7-403c-b695-7a6ebeb87839
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9b6b065b9855c6edf44456026baa32e8d9a4674f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802071"
---
# 配置 AGPM 服务器连接


每个受控制的组策略对象（GPO）的所有版本都存储在一个中央存档中，以便组策略管理员可以脱机查看和修改 Gpo，而不会立即影响每个 GPO 的已部署版本。

具有 AGPM 管理员（完全控制）角色的用户帐户、创建在这些过程中使用的 GPO 的审批者的用户帐户，或者需要高级组策略管理（AGPM）中具有必要权限的用户帐户才能完成为所有组策略管理员集中配置存档位置的这些过程。 查看本主题中 "其他注意事项" 中的详细信息。

## 配置 AGPM 服务器连接


作为 AGPM 管理员，你可以通过集中配置关联的设置来确保所有组策略管理员都连接到同一 AGPM 服务器。 如果你的环境需要某些或所有域的单独的 AGPM 服务器，请将这些其他 AGPM 服务器配置为默认的例外。 如果未集中配置 AGPM 服务器连接，则每个组策略管理员必须手动配置要为每个域显示的 AGPM 服务器。

-   [为所有组策略管理员配置 AGPM 服务器连接](#bkmk-defaultarchiveloc)

-   [为所有组策略管理员配置其他 AGPM 服务器连接](#bkmk-additionalarchiveloc)

-   [为你的帐户手动配置 AGPM 服务器连接](#bkmk-manuallyconfigurearchiveloc)

### <a href="" id="bkmk-defaultarchiveloc"></a>

**为所有组策略管理员配置 AGPM 服务器连接**

1.  在**组策略管理控制台**树中，编辑应用到所有组策略管理员的 GPO。 （有关详细信息，请参阅[编辑 GPO](editing-a-gpo-agpm40.md)。）

2.  在**组策略管理编辑器**窗口中，单击 "**用户配置**"、"**策略**"、"**管理模板**"、" **Windows 组件**" 和 " **AGPM**"。

3.  在 "详细信息" 窗格中，双击 " **AGPM：指定默认 Agpm 服务器（所有域）**"。

4.  在 "**属性**" 窗口中，选中 "**已启用**" 复选框，然后键入完全限定的计算机名称和端口（例如，server.contoso.com:4600）。

5.  单击“确定”****。 除非你想要配置其他 AGPM 服务器连接，否则请关闭 "**组策略管理编辑器**" 窗口并部署 GPO。 （有关详细信息，请参阅[部署 GPO](deploy-a-gpo-agpm40.md)。）更新组策略时，将为所有组策略管理员配置 AGPM 服务器连接。

### <a href="" id="bkmk-additionalarchiveloc"></a>

**为所有组策略管理员配置其他 AGPM 服务器连接**

1.  如果尚未配置 AGPM 服务器连接，请按照上述步骤为所有域配置默认的 AGPM 服务器。

2.  若要为部分或所有域配置单独的 AGPM 服务器（替代默认的 AGPM 服务器），请在**组策略管理控制台**树中，编辑应用到所有组策略管理员的 GPO。 （有关详细信息，请参阅[编辑 GPO](editing-a-gpo-agpm40.md)。）

3.  在 "**组策略管理编辑器**" 窗口中，单击 "**用户配置**"、"**策略**"、"**管理模板**"、" **Windows 组件**" 和 " **AGPM**"。

4.  在 "详细信息" 窗格中，双击 " **agpm：指定 Agpm 服务器**"。

5.  在 "**属性**" 窗口中，选中 "**已启用**" 复选框，然后单击 "**显示**"。

6.  在 "**显示内容**" 窗口中：

    1.  单击**添加**。

    2.  对于 "**值名称**"，请键入域名（例如，server1.contoso.com）。

    3.  对于 "**值**"，请键入要用于此域的 AGPM 服务器名称和端口（例如，server2.contoso.com:4600），然后单击 **"确定"**。 （默认情况下，AGPM 服务在端口4600上侦听。 若要使用其他端口，请参阅[修改 AGPM 服务](modify-the-agpm-service-agpm40.md)。

    4.  对不使用默认 AGPM 服务器的每个域重复此操作。

7.  单击 **"确定"** 以关闭 "**显示内容**和**属性**" 窗口。

8.  关闭 "**组策略管理编辑器**" 窗口。 （有关详细信息，请参阅[部署 GPO](deploy-a-gpo-agpm40.md)。）更新组策略时，将为所有组策略管理员配置新的 AGPM 服务器连接。

### <a href="" id="bkmk-manuallyconfigurearchiveloc"></a>

如果已集中配置 AGPM 服务器连接，则用于手动配置它的选项对所有组策略管理员不可用。

**手动配置要为你的帐户显示的 AGPM 服务器**

1.  在 "**组策略管理" 控制台**树中，单击要在其中管理 gpo 的林和域中的 "**更改控制**"。

2.  在 "详细信息" 窗格中，单击 " **AGPM 服务器**" 选项卡。

3.  输入用于管理用于此域的存档的 AGPM 服务器的完全限定计算机名（例如，server.contoso.com）和 AGPM 服务侦听的端口（默认情况下为端口4600）。

4.  单击 "**应用**"，然后单击 **"是"** 进行确认。

### 其他注意事项

-   你必须能够编辑和部署 GPO，才能执行为所有组策略管理员集中配置 AGPM 服务器连接的过程。 有关其他详细信息，请参阅[编辑 gpo](editing-a-gpo-agpm40.md)和[部署 gpo](deploy-a-gpo-agpm40.md) 。

-   所选的 AGPM 服务器确定在 "**目录**" 选项卡上显示哪些 gpo 以及应用 "**域委派**" 选项卡设置的位置。 如果不是通过管理模板进行集中管理，则每个组策略管理员必须将此设置配置为指向域的 AGPM 服务器。

-   组策略创建者所有者组的成员身份应受到限制，soit 不会用于绕过对 Gpo 的访问的 AGPM 管理。 （在**组策略管理控制台**中，单击要在其中管理 gpo 的林和域中的 "**组策略对象**"，单击 "**委派**"，然后配置设置以满足组织的需要。）

### 其他参考资料

-   [配置高级组策略管理](configuring-advanced-group-policy-management-agpm40.md)

 

 





