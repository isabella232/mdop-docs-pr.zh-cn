---
title: 确定 MED-V 实例数
description: 确定 MED-V 实例数
author: dansimp
ms.assetid: edea9bdf-a28c-4d24-9298-7bd6536c3a94
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 22f7d54318d2dc489461474e5531c5162d8c087d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803532"
---
# 确定 MED-V 实例数


你需要确定 MED-V 实例的数量，并为每个实例定义范围，以便你可以设计服务器基础结构。 MED-V 实例包括以下内容：

-   在服务器上存储的 MED-V 服务器和 MED-V 工作区（包括 Active Directory 权限）。

-   存储客户端事件的 SQL Server 数据库。 数据库可以由多个 MED-V 实例共享。

-   打包的 MED-V 映像的图像存储库。 存储库可以由多个 MED-V 实例共享。

-   用于创建和打包映像以及创建 MED-V 工作区的管理控制台。 该控制台不能同时由多个 MED-V 实例使用，但可以从一个 MED-V 服务器断开连接，然后连接到其他 MED-V 服务器。

-   从服务器接收 MED-V 工作区以及授权使用的 MED-V 客户端。

单独的 MED-V 实例不能集成或共享 MED-V 工作区。 因此，每个额外实例 decentralizes 虚拟化管理。

## 确定所需的 MED-V 实例数


首先假设你使用的是一个 MED-V 实例。 然后，考虑以下条件，并为适用于基础结构的每个条件添加其他实例。

-   支持的用户数-每个 MED-V 实例最多可支持5000个并发活动客户端。 并发活动意味着客户端与 MED-V 服务器在线，并向服务器发送对策略和映像更新以及事件的轮询。 如果你的基础结构包含的活动用户超过5000个，请为每个5000用户添加一个实例。

-   不受信任域中的用户-MED-V 服务器将 MED-V 工作区权限与 Active Directory 用户和/或组关联。 这要求 med-v 服务器的信任边界内存在 med-v 用户。 为位于单独的不受信任域中的每组 MED-V 用户添加一个 MED-V 实例。

-   独立网络中的客户端-确定任何客户端是否驻留在已隔离的网络中，因此需要单独的 MED-V 实例。 例如，组织通常将实验室网络与生产网络隔离。 为将包含 MED-V 客户端的每个隔离网络添加 MED-V 实例。

-   组织要求-组织可能需要由单独的 MED-V 实例管理一组客户端，出于安全考虑，例如，当敏感应用程序仅向域中的一组受限用户传递时。 例如，工资部门可能拒绝其他部门的用户访问存储用于工资处理策略的 MED-V 实例。 此外，如果组织使用分布式管理模型，则对于拥有 MED-V 客户端的每个业务组，可能需要一个单独的 MED-V 实例，以使该组能够管理其自己的虚拟化环境。 为每个单独的组织要求添加一个 MED-V 实例。

-   法律考虑-国内安全或隐私问题和 fiduciary 法律可能需要分离某些数据或防止其他数据跨越全国边框。 如有必要，请添加其他 MED-V 实例以满足此需求。

确定你的基础结构所需的 MED-V 实例数以及每个实例的推理后，请为每个实例提供一个名称。

 

 





