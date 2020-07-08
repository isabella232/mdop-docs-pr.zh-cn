---
title: 部署 App-V 5.1 Server
description: 部署 App-V 5.1 Server
author: dansimp
ms.assetid: 987b61dc-00d6-49ba-8f1b-92d7b948e702
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2bcff2a3211ea3e2f666aff1d6f2ad919509aa3a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798577"
---
# 部署 App-V 5.1 Server

你可以通过使用本主题中介绍的不同部署配置来安装 Microsoft Application Virtualization （App-v）5.1 服务器功能。 在安装服务器功能之前，请查看 app-v [5.1 安全注意事项](app-v-51-security-considerations.md)的 "服务器" 部分。

有关部署 app-v 服务器的信息，请参阅[关于 app-v 5.1](about-app-v-51.md#bkmk-migrate-to-51)。

> [!IMPORTANT]
> 在安装和配置 App-v 5.1 服务器之前，必须指定将托管每个组件的端口。 还必须添加关联的防火墙规则，以便允许传入请求访问指定的端口。 安装程序不修改防火墙设置。

## <a href="" id="---------app-v-5-1-server-overview"></a> App-v 5.1 服务器概述

App-v 5.1 服务器由五个组件组成。 每个组件在 App-v 5.1 环境中提供不同用途。 此处简要介绍了这五个组件：

- 管理服务器-提供 app-v 5.1 基础结构的总体管理功能。
- 管理数据库-方便了 App-v 5.1 管理的数据库 predeployments。
- 发布服务器-提供虚拟应用程序的托管和流功能。
- 报表服务器-提供 app-v 5.1 reporting services。
- 报告数据库-为 App-v 5.1 报告简化数据库 predeployments。

## <a href="" id="---------app-v-5-1-stand-alone-deployment"></a> App-v 5.1 独立部署

App-v 5.1 独立部署为小型部署或测试环境提供良好的拓扑。 使用此类型的实现时，所有服务器组件都将部署到一台计算机上。 服务和关联数据库将争用运行 App-v 5.1 组件的计算机上的资源。 因此，不应将此拓扑用于较大的部署。

[如何部署 App-V 5.1 Server](how-to-deploy-the-app-v-51-server.md)

[如何使用脚本部署 App-V 5.1 Server](how-to-deploy-the-app-v-51-server-using-a-script.md)

## <a href="" id="---------app-v-5-1-server-distributed-deployment"></a> App-v 5.1 服务器分布式部署

分布式部署拓扑可以支持大型应用程序-V 5.1 客户端基础，它使您能够更轻松地管理和扩展您的环境。 使用此类型的部署时，将基于组织的结构和要求，在多台计算机上部署 app-v 5.1 服务器组件。

[如何在单独的计算机上从管理和报告服务安装管理和报告数据库](how-to-install-the-management-and-reporting-databases-on-separate-computers-from-the-management-and-reporting-services51.md)

[如何在独立计算机上安装 Management Server 并将其连接到数据库](how-to-install-the-management-server-on-a-standalone-computer-and-connect-it-to-the-database51.md)

[如何使用脚本部署 App-V 5.1 Server](how-to-deploy-the-app-v-51-server-using-a-script.md)

[如何在远程计算机上安装发布服务器](how-to-install-the-publishing-server-on-a-remote-computer51.md)

[如何在独立计算机上安装 Management Server 并将其连接到数据库](how-to-install-the-management-server-on-a-standalone-computer-and-connect-it-to-the-database51.md)

## 使用企业软件分发（ESD）解决方案和 App-v 5。1

您也可以使用 ESD 部署 app-v 5.1 客户端和程序包，而无需部署 app-v 5.1。 集成的完整功能将因您使用的 ESD 而异。

> [!NOTE]
> App-v 5.1 报告服务器和报告数据库仍然可以与 ESD 一起部署，以便从 App-v 5.1 客户端收集报告数据。 但是，不应部署其他三个服务器组件，因为它们将与 ESD 功能发生冲突。

[使用电子软件分发 (ESD) 部署 App-V 5.1 程序包](deploying-app-v-51-packages-by-using-electronic-software-distribution--esd-.md)

## <a href="" id="---------app-v-5-1-server-logs"></a> App-v 5.1 服务器日志

在使用 App-v 5.1 时，可以使用 app-v 5.1 服务器日志信息帮助解决服务器安装和操作事件。 与服务器相关的日志信息可以通过**事件查看器**进行查看。 下一行显示与服务器相关的事件的特定路径：

**事件查看器 \ 应用程序和服务日志 \\ Microsoft \\ App V**

关联的安装日志保存在以下目录中：

**高**

在 App-v 5.0 SP3 中，某些日志已合并并移动。 请参阅[关于 App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-event-logs-moved)。

## <a href="" id="---------app-v-5-1-reporting"></a> App-v 5.1 报告

App-v 5.1 报告允许应用-V 5.1 客户端收集数据，然后将其发送回存储在中央存储库中。 你可以使用此信息更好地查看你的组织内的虚拟应用程序使用情况。 下表显示了 App-v 5.1 客户端收集的一些信息类型：

- 有关运行 app-v 5.1 客户端的计算机的信息。
- 有关运行 App-v 5.1 客户端的特定计算机上的虚拟化程序包的信息。
- 有关特定用户的程序包打开和关闭的信息。

报告信息将保留，直到成功发送到报表服务器数据库。 在数据库中数据后，您可以使用 Microsoft SQL Server Reporting Services 生成任何必需的报表。

如果要检索报表信息，则必须使用 microsoft sql Server Reporting Services （SSRS），它可与 Microsoft SQL 一起使用。 安装了 app-v 5.1 报告服务器时未安装 SSRS，必须单独部署它才能生成关联的报告。

[有关 app-v 5.1 报告](about-app-v-51-reporting.md)的详细信息，请使用以下链接。

[如何使用 PowerShell 在 App-V 5.1 Client 上启用报告](how-to-enable-reporting-on-the-app-v-51-client-by-using-powershell.md)

## App-v 服务器的其他资源

[部署 App-V 5.1](deploying-app-v-51.md)
