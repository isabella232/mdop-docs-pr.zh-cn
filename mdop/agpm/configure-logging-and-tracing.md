---
title: 配置记录和跟踪
description: 配置记录和跟踪
author: dansimp
ms.assetid: 419231f9-e9db-4f91-a7cf-a0a73db25256
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fa3dfa71edb25f6641ade595cd4469e846410ac2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802031"
---
# 配置记录和跟踪


你可以使用管理模板集中配置高级组策略管理（AGPM）的可选日志记录和跟踪。

具有 AGPM 管理员（完全控制）角色的用户帐户、创建在这些过程中使用的 GPO 的审批者的用户帐户，或者需要高级组策略管理中具有必需权限的用户帐户才能完成这些过程。 此外，若要在 AGPM 服务器上启动日志记录，必须具有访问 AGPM 服务器的用户帐户。 查看本主题中 "其他注意事项" 中的详细信息。

**为 AGPM 配置日志记录和跟踪**

1.  在**组策略管理控制台**树中，编辑应用到要启用日志记录和跟踪的所有组策略管理员的 GPO。 （有关详细信息，请参阅[编辑 GPO](editing-a-gpo.md)。）

2.  在 "**组策略对象编辑器**" 中，单击 "**计算机配置**"、"**管理模板**" 和 " **Windows 组件**"。

3.  如果 " **Windows 组件**" 下列出的是**AGPM**未列出：

    1.  右键单击 "**管理模板**"，然后单击 "**添加/删除模板**"。

    2.  单击 "**添加**"，选择 " **agpm** " 或 " **agpm .Adm**"，单击 "**打开**"，然后单击 "**关闭**"。

4.  在 " **Windows 组件**" 下，双击 " **AGPM**"。

5.  在 "详细信息" 窗格中，双击 " **AGPM 日志记录**"。

6.  在 " **AGPM 日志记录属性**" 窗口中，单击 "**已启用**"，并配置日志中记录的详细信息级别。

7.  单击“确定”****。

8.  关闭 "**组策略对象编辑器**"。 （有关详细信息，请参阅[部署 GPO](deploy-a-gpo.md)。）更新组策略后，必须重新启动 AGPM 服务才能开始在 AGPM 服务器上登录。 组策略管理员必须关闭并重新启动 GPMC，才能在其计算机上开始日志记录。

    **跟踪文件位置**：

    -   客户端：%LocalAppData%\\Microsoft\\AGPM\\agpm.log

    -   服务器：%ProgramData%\\Microsoft\\AGPM\\agpmserv.log

### 其他注意事项

-   你必须能够编辑和部署 GPO，才能配置 AGPM 日志记录和跟踪。 有关其他详细信息，请参阅[编辑 gpo](editing-a-gpo.md)和[部署 gpo](deploy-a-gpo.md) 。

### 其他参考资料

-   [执行 AGPM 管理员任务](performing-agpm-administrator-tasks.md)

 

 





