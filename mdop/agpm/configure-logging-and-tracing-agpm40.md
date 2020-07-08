---
title: 配置记录和跟踪
description: 配置记录和跟踪
author: dansimp
ms.assetid: 2418cb6a-7189-4080-8fe2-9c8d47dec62c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: bfc56d418ae83cbc5db24246bfac057305629df7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802028"
---
# 配置记录和跟踪


你可以使用 "管理模板" 集中配置可选日志记录和跟踪。 这可能有助于诊断与高级组策略管理（AGPM）相关的任何问题。

具有 AGPM 管理员（完全控制）角色的用户帐户、创建了在这些过程中使用组策略对象（GPO）的审批者的用户帐户，或者需要使用 AGPM 中的必要权限的用户帐户才能完成这些过程。 此外，若要在 AGPM 服务器上启动日志记录，必须具有访问 AGPM 服务器的用户帐户。 查看本主题中 "其他注意事项" 中的详细信息。

**为 AGPM 配置日志记录和跟踪**

1.  在**组策略管理控制台**树中，编辑应用到要启用日志记录和跟踪的所有组策略管理员的 GPO。 （有关详细信息，请参阅[编辑 GPO](editing-a-gpo-agpm40.md)。）

2.  在**组策略管理编辑器**窗口中，单击 "**计算机配置**"、"**策略**"、"**管理模板**"、" **Windows 组件**" 和 " **AGPM**"。

3.  在 "详细信息" 窗格中，双击 " **AGPM：配置日志记录**"。

4.  在 "**属性**" 窗口中，单击 "**已启用**"，并配置日志中记录的详细信息级别。

5.  单击“确定”****。

6.  关闭 "**组策略管理编辑器**" 窗口。 （有关详细信息，请参阅[部署 GPO](deploy-a-gpo-agpm40.md)。）更新组策略后，必须重新启动 AGPM 服务才能启动、修改或停止 AGPM 服务器上的日志记录。 组策略管理员必须关闭并重新启动 GPMC，才能在其计算机上启动、修改或停止日志记录。

    **跟踪文件位置**：

    -   客户端：%LocalAppData%\\Microsoft\\AGPM\\agpm.log

    -   服务器：%ProgramData%\\Microsoft\\AGPM\\agpmserv.log

### 其他注意事项

-   你必须能够编辑和部署 GPO，才能配置 AGPM 日志记录和跟踪。 有关其他详细信息，请参阅[编辑 gpo](editing-a-gpo-agpm40.md)和[部署 gpo](deploy-a-gpo-agpm40.md) 。

### 其他参考资料

-   [配置高级组策略管理](configuring-advanced-group-policy-management-agpm40.md)

 

 





