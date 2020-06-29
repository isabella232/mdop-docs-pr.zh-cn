---
title: 关于 Application Virtualization 应用程序
description: 关于 Application Virtualization 应用程序
author: dansimp
ms.assetid: 3bf833b7-d172-4eef-a9e8-4b4f0c7eb15b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4eeea7a0ec4454aefcdde5196ae15ed029da45b5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802476"
---
# 关于 Application Virtualization 应用程序


在应用程序虚拟化中，*应用程序*是从应用程序虚拟化管理服务器流入到应用程序虚拟化桌面客户端或远程桌面服务（以前称为终端服务）的客户端的可执行程序（如 Microsoft Visio）。 必须先通过使用 Application Virtualization Sequencer 处理应用程序，才能将该应用程序流式传输到客户端。

## 管理应用程序


必须先将应用程序添加到系统，然后才能使应用程序可供用户使用。 将应用程序添加到系统的最常见方法是导入这些应用程序。 若要访问此功能，请右键单击应用程序虚拟化服务器管理控制台中的 "**应用程序**" 节点，然后选择 "**导入应用程序**"。

你可以同时导入多个开放软件描述符（OSD）文件，也可以导入一个可以包含多个 OSD 文件的 Sequencer 项目文件（SPRJ）。 此功能使你能够以同样的方式配置相关的应用程序。

你还可以使用以下功能来帮助你管理应用程序：

-   **应用程序组**-使你能够创建应用程序的逻辑组以简化管理。 对组进行更改（例如，访问权限）时，所做的更改将应用到组中的所有应用程序。 组中的应用程序可以来自不同的程序包。

-   **多重选择**-允许你在单击应用程序以修改应用程序属性时按住 CTRL 键，同时选择多个应用程序。 但是，如果你想要维护应用程序之间的关系，你应该创建一个应用程序组来保存应用程序。

-   **跨系统副本**-使你能够在一个步骤中将应用程序从一个环境复制到另一个运行相同版本 app-v 的环境中。 例如，你可能有一个用户验收测试环境，你可以在其中开始部署和配置应用程序。 完成测试阶段后，您可能希望将同一组应用程序（包括权限）复制到生产环境。

## 相关主题


[关于 Application Virtualization 程序包](about-application-virtualization-packages.md)

[关于 Application Virtualization Server Management Console](about-the-application-virtualization-server-management-console.md)

[如何在 Server Management Console 中管理应用程序组](how-to-manage-application-groups-in-the-server-management-console.md)

[如何在 Server Management Console 中管理应用程序](how-to-manage-applications-in-the-server-management-console.md)

 

 





