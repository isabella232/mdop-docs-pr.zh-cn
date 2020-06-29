---
title: 高级组策略管理疑难解答
description: 高级组策略管理疑难解答
author: dansimp
ms.assetid: f58849cf-6c5b-44d8-b356-0ed7a5b24cee
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c22b9a0983b26252ee0d9c8d99b63cd4ab5dc2b6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801743"
---
# 高级组策略管理疑难解答


本部分列出了使用高级组策略管理（AGPM）管理组策略对象（Gpo）时可能遇到的一些常见问题。

## 你遇到了哪些问题？


-   [我无法访问存档](#bkmk-access-an-archive)

-   [GPO 状态因不同组策略管理员而异](#bkmk-state-varies)

-   [我无法修改 AGPM 服务器连接](#bkmk-modify-archive-location)

-   [我无法更改默认模板或查看、创建、编辑、重命名、部署或删除 Gpo](#bkmk-perform-task)

-   [我无法使用特定的 GPO 名称](#bkmk-use-particular-name)

-   [我没有收到 AGPM 电子邮件通知](#bkmk-email)

-   [我无法为 AGPM 服务使用端口4600](#bkmk-port)

-   [AGPM 服务将不会启动](#bkmk-not-start)

-   [组策略软件安装无法安装软件](#bkmk-software-installation)

### <a href="" id="bkmk-access-an-archive"></a>我无法访问存档

-   **原因**：你没有为存档选择正确的服务器和端口。

-   **解决方案**：

    -   如果你是 AGPM 管理员：请参阅[配置 AGPM 服务器连接](configure-the-agpm-server-connection.md)。

    -   如果您不是 AGPM 管理员：从 AGPM 管理员请求 AGPM 服务器的连接详细信息。 请参阅[配置 AGPM 服务器连接](configure-the-agpm-server-connection-reviewer.md)。

-   **原因**：高级组策略管理服务未运行。

-   **解决方案**：

    -   如果您是 AGPM 管理员：启动 AGPM 服务。 有关详细信息，请参阅[启动和停止 AGPM 服务](start-and-stop-the-agpm-service.md)。

    -   如果您不是 AGPM 管理员：请与 AGPM 管理员联系以获取帮助。

### <a href="" id="bkmk-state-varies"></a>GPO 状态因不同组策略管理员而异

-   **原因**：不同的组策略管理员为同一存档选择了不同的 AGPM 服务器。

-   **解决方案**：

    -   如果你是 AGPM 管理员：请参阅[配置 AGPM 服务器连接](configure-the-agpm-server-connection.md)。

    -   如果您不是 AGPM 管理员：从 AGPM 管理员请求 AGPM 服务器的连接详细信息。 请参阅[配置 AGPM 服务器连接](configure-the-agpm-server-connection-reviewer.md)。

### <a href="" id="bkmk-modify-archive-location"></a>我无法修改 AGPM 服务器连接

-   **原因**：如果 " **agpm 服务器**" 选项卡上的设置不可用，则已使用管理模板对 agpm 服务器进行集中配置。

-   **解决方案**：

    -   如果您是 AGPM 管理员：如果 " **Agpm 服务器**" 选项卡上的设置不可用，请参阅[配置 AGPM 服务器连接](configure-the-agpm-server-connection.md)。

    -   如果您不是 AGPM 管理员：如果 " **Agpm 服务器**" 选项卡上的设置不可用，则不需要修改 AGPM 服务器。

### <a href="" id="bkmk-perform-task"></a>我无法更改默认模板或查看、创建、编辑、重命名、部署或删除 Gpo

-   **原因**：尚未向你分配执行任务所需权限的角色。

-   **解决方案**：

    -   如果您是 AGPM 管理员：请参阅[委派域级访问](delegate-domain-level-access.md)和[委派对单个 GPO 的访问权限](delegate-access-to-an-individual-gpo.md)。 AGPM 权限将从域级联到当前存档中的所有 Gpo。 当新组策略管理员添加到域级别时，其权限必须设置为应用于**此对象和嵌套的对象**。 有关哪些角色可以执行任务以及执行任务需要哪些权限的详细信息，请参阅该任务的帮助。

    -   如果您不是 AGPM 管理员，并且您需要其他角色或权限：请与 AGPM 管理员联系以获取帮助。 请注意，如果你是编辑器，则可以开始创建 GPO、部署 GPO 或从生产环境中删除 GPO 的过程，但审批者或 AGPM 管理员必须批准你的请求。

### <a href="" id="bkmk-use-particular-name"></a>我无法使用特定的 GPO 名称

-   **原因**：该 gpo 名称已在使用或你无权列出该 gpo。

-   **解决方案**：

    -   如果 GPO 名称显示在 "**受控**"、"不**受控制**" 或 "**挂起**" 选项卡上，请选择其他名称。 如果已部署的 GPO 已重命名但尚未重新部署，则它将显示在生产环境中的旧名称下，因此旧名称仍在使用中。 重新部署 GPO 以在生产环境中更新其名称，并释放该名称以供另一个 GPO 使用。

    -   如果 GPO 名称未显示在 "**受控**"、"不**受控制**" 或 "**挂起**" 选项卡上，则您可能无权列出该 gpo。 若要请求权限，请与 AGPM 管理员联系。

### <a href="" id="bkmk-email"></a>我没有收到 AGPM 电子邮件通知

-   **原因**：未提供有效的 SMTP 电子邮件服务器和电子邮件地址，或者没有执行生成电子邮件通知的操作。

-   **解决方案**：

    -   如果你是 AGPM 管理员：有关要通过 AGPM 发送的待执行操作的电子邮件通知，AGPM 管理员必须为 "**域委派**" 选项卡上的审批者提供有效的 SMTP 电子邮件服务器和电子邮件地址。有关详细信息，请参阅[配置电子邮件通知](configure-e-mail-notification.md)。

    -   仅当缺少创建、部署或删除 GPO 所需权限的编辑器、审阅者或其他组策略管理员提交这些操作之一的请求时，才会生成电子邮件通知。 没有自动通知或拒绝请求。

### <a href="" id="bkmk-port"></a>我无法为 AGPM 服务使用端口4600

-   **原因**：默认情况下，AGPM 服务侦听的端口是端口4600。

-   **解决方案**：如果对于 AGPM 服务，端口4600不可用，请修改每个存档索引文件以使用另一个端口，然后为所有组策略管理员更新 AGPM 服务器。 有关详细信息，请参阅[修改 AGPM 服务侦听的端口](modify-the-port-on-which-the-agpm-service-listens.md)。

### <a href="" id="bkmk-not-start"></a>AGPM 服务将不会启动

-   **原因**：您在 "**管理工具**和**服务**" 下的操作系统中修改了 AGPM 服务的设置。

-   **解决方案**：在 "**添加或删除程序**" 下修改**Microsoft 高级组策略管理-服务器**的设置。 有关详细信息，请参阅[修改 AGPM 服务帐户](modify-the-agpm-service-account.md)。

### <a href="" id="bkmk-software-installation"></a>组策略软件安装无法安装软件

-   **原因**： AGPM 保留组策略软件安装程序包的完整性。 虽然脱机编辑 Gpo，但会保留程序包之间的链接和缓存的客户端信息。 这是设计使然。

-   **解决方案**：使用 AGPM 脱机编辑 GPO 时，请将另一个 GPO 中的程序包的任意组策略软件安装升级配置为引用部署的 gpo，而不是签出的副本。 编辑器必须具有已部署 GPO 的**读取**权限。

 

 





