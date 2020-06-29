---
title: 定义项目范围
description: 定义项目范围
author: dansimp
ms.assetid: 84637d2a-2e30-417d-b150-dc81f414b3a5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4f33562452327bba9036f56d9f6f96650f00c1f0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803409"
---
# 定义项目范围


定义项目范围时，请确定以下事项：

1.  MED-V 最终用户—最终用户的位置和数量用于确定 MED-V 客户端安装的位置和 med-v 实例的数量，以及 MED-V 图像存储库的数量和位置的位置。

2.  由 MED-V 管理的虚拟机（VM）映像，用于确定分发图像和放置图像存储库的方法。

3.  组织的服务级别期望值-确定 MED-V 服务器和数据库以及映像存储库的性能和容错要求。

4.  与业务部门进行验证-确保有完整地了解计划的基础结构对企业有何影响。

## 定义 MED-V 最终用户


首先，确定最终用户所在的位置，以及每个位置中的用户数。 第二，获取网络基础结构图，显示用户位置和这些位置的可用带宽。 第三，了解用户是否在两个位置之间旅行。 如果用户旅行，在服务器基础结构和图像存储库的设计中可能需要额外的容量。

## 确定 MED-V 要管理的 MED-V 图像


定义了 MED-V 最终用户后，确定将由 MED-V 对每个位置中的用户管理哪些 Vm。

如果任何 Vm 存储在一个集中的库中，请确定该库的位置，以便将其评估用作 MED-V 存储库。

## <a href="" id="determine-the-organization-s-service-level-expectations"></a>确定组织的服务级别期望值


对于每个 MED-V 工作区，请注意要加载的新映像的可接受时间和要部署的关键更新的时间范围。

如果适用，请记录 MED-V 报告的服务级别期望值，以便在服务器基础结构的设计中使用。

## 与业务部门进行验证


询问业务利益干系人和应用程序所有者下列问题：

-   是否有任何现有图像可以合并？ 例如，如果 WindowsXP 上的应用程序是一个 VPC 图像，而 WindowsXP 上的应用程序 B 是另一个 VPC 映像，则可能是单个映像可以同时包含这两个应用程序，从而减少了下载图像所需的存储库空间和带宽。

-   如果由 MED-V 在 VM 中传递，则范围内应用程序是否受许可和支持？ 通过 MED-V 提供应用程序，与应用程序供应商联系，以确保不会违反许可和支持条款。

 

 





