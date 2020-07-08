---
title: 移动 AGPM 服务器和存档
description: 移动 AGPM 服务器和存档
author: dansimp
ms.assetid: 13cb83c4-bb42-4e81-8660-5b7540f473d8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 6ae5ba9c2346caf81f5aff9f57f6b9dc97127ad1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803184"
---
# 移动 AGPM 服务器和存档


如果要替换 AGPM 服务器和托管存档的服务器，则必须移动 AGPM 服务和存档。 如果愿意，您可以单独移动 AGPM 服务和存档。

**注意**  
-   AGPM 服务器是托管 AGPM 服务和安装了 Microsoft 高级组策略管理-服务器的计算机的计算机。

-   默认情况下，存档位于 AGPM 服务器上，但你可以指定存档路径以在另一台服务器上托管它。

 

要完成此过程，必须是域管理员组的成员并且具有访问以前的和新的 AGPM 服务器的权限。 此外，你必须为要由新的 AGPM 服务器使用的 AGPM 服务帐户提供凭据，才能完成此过程。

**将 AGPM 服务和存档移动到其他服务器或服务器**

1.  备份存档。 有关详细信息，请参阅[备份存档](back-up-the-archive.md)。

2.  移动 AGPM 服务：

    1.  停止 AGPM 服务。 有关详细信息，请参阅[启动和停止 AGPM 服务](start-and-stop-the-agpm-service-agpm30ops.md)。

    2.  在将托管 AGPM 服务的新服务器上安装 Microsoft 高级组策略管理-服务器。 在此过程中，你将指定新的存档路径，即存档相对于 AGPM 服务器的位置。 有关详细信息，请参阅 microsoft 高级组策略管理3.0 （）的分步指南 <https://go.microsoft.com/fwlink/?LinkId=132706> 和 Microsoft 高级组策略管理（）的规划指南 <https://go.microsoft.com/fwlink/?LinkId=141871> 。

    3.  AGPM 管理员（完全控制）必须为将使用新的 AGPM 服务器的所有组策略管理员配置 AGPM 服务器连接并删除旧的 AGPM 服务器的连接，否则每个组策略管理员必须手动配置新的 AGPM 服务器连接并删除其计算机上的 AGPM 管理单元的旧 AGPM 服务器连接。 有关详细信息，请参阅[配置 AGPM 服务器连接](configure-agpm-server-connections-agpm30ops.md)。

        **注意** 最佳做法是从以前的 AGPM 服务器卸载 Microsoft 高级组策略管理-服务器。 这将确保无法在该服务器上无意间重启 AGPM 服务，并且可能会在任何与它的 AGPM 服务器连接保留时导致混乱。

         

3.  将存档从备份复制到将托管存档的新服务器。 有关详细信息，请参阅[从备份还原存档](restore-the-archive-from-a-backup.md)。

    **重要提示** 如果您移动了存档，但没有同时移动 AGPM 服务：

    1.  必须将存档路径更改为指向与 AGPM 服务器相关的存档的新位置。 有关详细信息，请参阅[修改 AGPM 服务](modify-the-agpm-service-agpm30ops.md)。

    2.  您必须重新输入并确认 "**域委派**" 选项卡上的密码。有关详细信息，请参阅[配置电子邮件通知](configure-e-mail-notification-agpm30ops.md)。

     

### 其他参考资料

-   [备份存档](back-up-the-archive.md)

-   [从备份还原存档](restore-the-archive-from-a-backup.md)

-   [配置 AGPM 服务器连接](configure-agpm-server-connections-agpm30ops.md)

-   [修改 AGPM 服务](modify-the-agpm-service-agpm30ops.md)

-   Microsoft 高级组策略管理3.0 （）的分步指南 <https://go.microsoft.com/fwlink/?LinkId=132706>

-   Microsoft 高级组策略管理的规划指南（ <https://go.microsoft.com/fwlink/?LinkId=141871> ）

-   [执行 AGPM 管理员任务](performing-agpm-administrator-tasks-agpm30ops.md)

 

 





