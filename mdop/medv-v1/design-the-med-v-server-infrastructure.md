---
title: 设计 MED-V 服务器基础结构
description: 设计 MED-V 服务器基础结构
author: dansimp
ms.assetid: 2781040f-880e-4e16-945d-a38c0adb4151
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 4ba4c38328c5484b7daa292f9fc33a4e59824327
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803517"
---
# 设计 MED-V 服务器基础结构


在本主题中，你将为每个 MED-V 实例设计服务器基础结构。 这包括确定 SQL Server 实例是否将存在于 MED-V 服务器或远程服务器上以及 SQL Server 数据库的大小。 你还将确定管理控制台的位置。

## 为每个 MED-V 实例设计和放置服务器


MED-V 服务器实现策略并存储有关其客户端的状态和历史记录数据。

### 外形规格

MED-V 建议将 2.8 GHz 双核 CPU 服务器与2GB 的 RAM 配合使用。 此建议基于以下假设： MED-V 服务器将在专用计算机上运行，并且 SQL Server 和 MED-V 管理控制台将在单独的计算机上运行。

鉴于此工作负荷，MED-V 服务器应该相对较轻的负载。 如果在服务器外形规格上没有特定的体系结构指导，请使用 MED-V 建议设计服务器，其中包含与组织的标准外形规格相匹配的内存。 MED-V 服务器可以在 Windows Server2008 上的虚拟机（VM）上运行。 如果将使用 VM，请确保它可以访问与为物理计算机指定的资源等效的 CPU 和内存资源。

MED-V 服务器所需的磁盘容量必须足以存储 MED-V 工作区配置文件。 MED-V 工作区只能对一个或多个用户使用一个 VM 和一个策略。 因此，必须存储的 MED-V 工作区的数量取决于同一 VM 的不同用户需要不同策略的程度以及将使用的 Vm 数的程度。 MED-V 工作区 XML 文件的大小围绕典型的 MED-V 工作区的30KB。 若要确定所需的磁盘容量，请将 30 KB 乘以 MED-V 服务器将存储的 MED-V 工作区的数量。

MED-V 服务器最重要的网络连接是指向其客户端的链接，因此将服务器放在一个网络位置，该位置提供最可用的带宽和最强健的客户端链接。

### 容错

MED-V 实例中只能有一个活动的 MED-V 服务器，而 MED-V 不包含将服务器置于 Microsoft 群集服务器（MSCS）群集中以提供容错的标准功能。 可手动配置被动备份服务器。

若要确定是否应为 MED-V 实例手动配置被动备份服务器，请确定是否允许用户在脱机模式下使用 MED-V 图像。 有关脱机模式的信息，请参阅[如何配置域用户或组](how-to-configure-a-domain-user-or-groupmedvv2.md)。 如果不允许用户脱机工作，则即使尚未在客户端上启动 MED-V 工作区，也无法继续在 MED-V 服务器失败的事件中工作。 如果允许脱机工作，对于每个 MED-V 工作区，请确定客户端在必须进行身份验证之前允许多长时间脱机工作。 这是服务器无法使用的最长时间。

## 设计和放置 SQL Server 数据库


MED-V 服务器使用 SQL Server 数据库存储客户端状态和事件。 你可以将 SQL Server 数据库安装在 MED-V 服务器所在的同一台计算机上，也可以将其放在运行 SQL Server 的单独服务器上，该服务器可以选择是远程的。 你可以与其他 MED-V 实例共享数据库，在这种情况下，来自这些实例的事件和警报将存储在同一数据库中，并且报表将包含来自所有实例的事件。 可以在现有 SQL Server 实例中安装数据库，其他 MED-V 服务器的数据库可以驻留在同一实例中。

如果将数据库服务器放在 MED-V 服务器的远程位置，并且跨网络链接没有足够的可用带宽，则在控制台中加载报表可能会很慢，并且可能不会显示客户端的最新数据。 请参阅在[定义项目范围](define-the-project-scope.md)中确定的组织服务级别期望值，并使用该信息确定 SQL Server 数据库的放置位置。

### 外形规格

如果你在使用 MED-V 的同一服务器上运行 SQL Server，并且 SQL Server 将仅用于存储该服务器的数据，请从 MED-V 建议开始，为 SQL Server 加载添加资源。 如果 SQL Server 将存储来自多个 MED-V 实例的事件和警报，有关如何缩放服务器板型的信息，请参阅[基础结构规划和设计 MICROSOFT SQL Server 2008](https://go.microsoft.com/fwlink/?LinkId=163302)指南（http://go.microsoft.com/fwlink/?LinkId=163302）。

数据库的大小取决于数据库将存储的客户端事件数。 事件由客户端的常规操作（例如，启动 MED-V 工作区时）或在 MED-V 工作区中出现错误的情况下创建。 客户端发送事件的默认间隔是1分钟。

若要估计数据库的大小，请确定以下事项：

-   MED-V 实例中的客户端数。 最大值为5000。

-   典型的事件到达率。 此速率取决于客户端使用情况，但每个客户端每天大约有15到20个事件。

-   事件大小。 大小通常约为200字节。

-   存储量。 将存储事件的天数。

将这些值放在一起以计算所需数据存储的大小（以字节为单位），然后为以下各项添加安全因素：

-   错误，这可能会在较短的时间内从客户端创建大量事件。

-   数据库表和组织空间。

若要估计每秒基础结构优化（IOPs）要求，请使用上述值，将典型事件到达率乘以实例中的客户端数。 这将生成每天可以写入的记录数。 将该数字除以86400以派生每秒写入的记录数。 如果可通过单个基础结构优化（IO）操作 equated 写入操作，则此数字是所需的写入 IOPs。 将缓冲区添加到用于报告活动的缓冲区。 这很难确定，但取决于与实例一起使用的控制台的数量以及用于生成报告的频率。

### 容错

当 MED-V 客户端正在运行时，如果服务器不可用，将在客户端上备份事件，并且报表将在管理控制台中不可用。 请参阅在[定义项目范围](define-the-project-scope.md)中确定的组织的服务级别期望值，以确定是否需要容错 SQL Server 基础结构的设计。

MED-V 不提供对 MSCS 群集中运行的 SQL Server 的支持。 为了提供热备用并在出现故障时避免数据丢失，可以将 SQL Server 置于日志传送配置中。 有关日志传送的信息，请参阅[基础结构规划和设计 MICROSOFT SQL Server 2008](https://go.microsoft.com/fwlink/?LinkId=163302)指南（ https://go.microsoft.com/fwlink/?LinkId=163302) 。

## 设计管理控制台


MED-V 管理控制台的部分功能是先测试虚拟机，然后再将其打包以分发到 MED-V 客户端。 因此，管理控制台应采用与典型的 MED-V 客户端计算机的外形规格相似的外形规格设计。

管理控制台应用程序与 MED-V 客户端一起安装，并使用 microsoft Virtual PC2007 SP1 和 Microsoft 知识库文章974918中所述的修复程序。 必须使用客户端操作系统;MED-V 管理控制台无法在与 MED-V 服务器相同的系统上运行。

不能与多个 MED-V 服务器实例共享管理控制台。 MED-V 服务器的地址是在安装管理控制台的 MED-V 客户端期间指定的;这可以在安装后进行更改，但在任何时候，管理控制台只能使用单个 MED-V 服务器。

你可以将多个管理控制台与单个 MED-V 服务器配合使用。 为避免冲突，有一种机制可用，可在一个控制台对 MED-V 工作区进行更改时通知其他控制台用户。

对于每个 MED-V 实例，确定需要多少个管理控制台和放置它们的位置。 选择要用于管理控制台的典型 MED-V 客户端外形规格。

## 相关主题


[MED-V 1.0 SP1 支持的配置](med-v-10-sp1-supported-configurationsmedv-10-sp1.md)

[将 MED-V 服务器配置为群集模式](configuring-med-v-server-for-cluster-mode.md)

[如何安装 MED-V 客户端和 MED-V 管理控制台](how-to-install-med-v-client-and-med-v-management-console.md)

[使用 MED-V 管理控制台用户界面](using-the-med-v-management-console-user-interface.md)

 

 





