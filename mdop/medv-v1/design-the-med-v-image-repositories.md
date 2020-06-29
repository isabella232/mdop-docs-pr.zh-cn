---
title: 设计 MED-V 映像存储库
description: 设计 MED-V 映像存储库
author: dansimp
ms.assetid: e153154d-2751-4990-b94d-a2d76242c15f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e0c59a0dd2d1b3a78bd211c6a6353a86c77d8fc2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803403"
---
# 设计 MED-V 映像存储库


创建并打包 MED-V 图像后，它们可以存储在任何位置的文件服务器上。 文件可能由一个或多个 IIS 服务器通过 HTTP 或 HTTPS 发送。 图像存储库可由多个 MED-V 实例共享。

若要设计图像存储库，必须首先确定如何将映像部署到每个客户端，以及该客户端是否需要本地映像存储库。 然后，设计和放置每个存储库及其随附的 IIS 服务器。

## 确定映像的部署方式


对于每个 MED-V 工作区，确定如何计划将 MED-V 映像部署到客户端。 这对于确定存储打包的图像所需的存储库（将放置这些资料库），然后设计这些存储库很重要。

打包的图像可以通过以下方式进行部署：

-   通过网络从包含文件服务器和 IIS 服务器的映像分发服务器下载。

-   在可移动媒体（如 USB 驱动器或 DVD）上。

-   使用企业软件分发中心预暂存到映像存储在客户端计算机上的目录。

确定将使用哪种方法或方法将 MED-V 映像部署到每个客户端，以及该位置是否需要映像存储库。

## 确定图像存储库的数量


既然你已确定所需的最小存储库数，请在以下任一条件适用时添加更多：

-   用于分离 MED-V 映像的组织或监管理由，某些 MED-V 图像可能无法在同一存储库中共存。 例如，敏感的个人数据可能需要服务器上的存储，该服务器仅适用于需要访问数据的有限的一组员工。

-   隔离网络中的客户端-如果将通过网络部署图像，请确定是否已隔离任何网络，并且需要单独的存储库。 例如，组织通常将实验室网络与生产网络隔离。

-   远程网络中的客户端-如果图像将通过网络部署，则某些客户端计算机可能会通过带宽不足的网络链接与存储库分开，以便在客户端加载 MED-V 工作区时提供充足的体验。 如有必要，可设计其他 MED-V 实例来满足此需求。

将这些资料库添加到设计中。 确定每个存储库的名称以及设计它的原因。 确定存储库将保留哪些 MED-V 映像以及哪些 MED-V 客户端将通过存储库中的图像加载 MED-V 工作区。

## 设计和放置图像存储库


当新图像可供客户端使用时，客户端将开始下载映像，这可能会同时开始。 这将为存储库创建高需求，并且必须在设计图像存储库时考虑。

对于每个存储库，确定它将存储的数据量。 将存储在存储库中的图像的大小相加。 这是文件服务器上所需的磁盘空间的值。

接下来，添加可从存储库下载 MED-V 映像的客户端数。 这是在将新的 MED-V 图像加载到存储库时可能出现的最大并发下载数。 文件服务器必须设计有可满足此将创建的 IO 要求的磁盘子系统。

图像存储库可以与 MED-V 服务器和运行 SQL Server 的服务器或远程文件共享上的系统驻留在同一系统上。 你还可以在 Windows Server2008 Hyper-v VM 中运行它。 检查映像存储库将提供服务的客户端的网络位置，并将存储库放在具有足够带宽的网络位置，以满足这些客户端的服务级别期望值。

### 容错

如果图像存储库不可用，客户端将无法下载新的或更新的 MED-V 映像。 若要为文件服务器和容错磁盘设计容错选项，请参阅[基础结构规划和设计 MICROSOFT SQL server 2008](https://go.microsoft.com/fwlink/?LinkId=163302)指南。

## 设计和放置 IIS 服务器


仅当客户使用 HTTP 或 HTTPS 通过网络下载图像文件时，此部分才会相关。

IIS 服务器可以与 MED-V 服务器所在的同一系统和运行 SQL Server 的服务器共存。 它还可以在 Windows Server2008 Hyper-v VM 中运行。 IIS 服务器基础结构必须具有足够的吞吐量，才能将图像提供给组织的服务级别预期内的客户端。 它必须设计有可满足此创建的 IO 要求的磁盘子系统。

对于每个映像存储库，对可以使用 IIS 下载 MED-V 映像的客户端数进行求和。 这是在将图像加载到存储库时可能出现的最大并发下载数。 使用吞吐量和的服务级别期望值确定[了定义项目范围](define-the-project-scope.md)以规划 IIS 服务器基础结构的设计，并确定为存储库分配适当的带宽量。

若要设计 IIS 基础结构，请参阅[基础结构规划和设计 Microsoft Internet 信息服务](https://go.microsoft.com/fwlink/?LinkId=160826)指南。

### 容错

如果 IIS 服务器基础结构不可用，客户端将无法下载新的或更新的映像。 若要配置容错，基于 Windows Server2008 的 IIS 服务器可以放置在故障转移群集中。 若要为 IIS 服务器基础结构设计容错，请参阅[基础结构规划和设计 Microsoft Internet 信息服务](https://go.microsoft.com/fwlink/?LinkId=160826)指南。

## 相关主题


[使用企业软件分发系统部署 MED-V 工作区](deploying-a-med-v-workspace-using-an-enterprise-software-distribution-system.md)

[使用部署包部署 MED-V 工作区](deploying-a-med-v-workspace-using-a-deployment-package.md)

 

 





