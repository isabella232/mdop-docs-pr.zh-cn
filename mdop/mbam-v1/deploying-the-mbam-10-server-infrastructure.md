---
title: 部署 MBAM 1.0 服务器基础结构
description: 部署 MBAM 1.0 服务器基础结构
author: dansimp
ms.assetid: 90529379-b70e-4c92-b188-3d7aaf1844af
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: de136db557233a097d95f47ef0a1bba5996798c5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803716"
---
# 部署 MBAM 1.0 服务器基础结构


通过使用一到五台服务器，你可以在不同配置中安装 Microsoft BitLocker 管理和监视（MBAM）服务器功能。 通常，你应该为生产环境使用三到五台服务器的配置，具体取决于你的可伸缩性需求。 有关 MBAM 和推荐部署拓扑的性能可伸缩性的详细信息，请参阅[MBAM 可伸缩性和高可用性指南白皮书](https://go.microsoft.com/fwlink/p/?LinkId=258314)。

## 在单个服务器上部署所有 MBAM 1。0


在此配置中，所有 MBAM 功能都安装在一台服务器上。 MBAM server 基础结构的此部署拓扑将最多支持 21000 MBAM 客户端计算机。

**重要提示** 此配置受支持，但我们建议仅用于测试。

 

本节中的过程介绍了单个服务器上的 MBAM 功能的完整安装。

[如何在单个服务器上安装和配置 MBAM](how-to-install-and-configure-mbam-on-a-single-server-mbam-1.md)

## 在分布式服务器上部署 MBAM 1。0


MBAM 功能可以采用不同的配置进行安装，具体取决于您的可伸缩性需求。 有关如何规划 MBAM server 功能部署的详细信息，请参阅[规划1.0 服务器部署](planning-for-mbam-10-server-deployment.md)。

本节中的过程介绍了分布式服务器上的 MBAM 功能的完整安装。

### 三台计算机配置

下图显示了 MBAM 的三计算机部署拓扑。 对于支持最多 55000 MBAM 客户端的生产环境，我们建议采用此拓扑。

![mbam 三台计算机部署拓扑](images/mbam-3-server.jpg)

在此配置中，MBAM 功能安装在以下配置中：

1.  在服务器上安装恢复和硬件数据库、合规性和审核数据库以及合规性和审核报告。

2.  "管理和监视服务器" 功能安装在服务器上。

3.  MBAM 组策略模板安装在能够修改组策略对象（GPO）的计算机上。

### 四计算机配置

下图显示了用于 MBAM 的四计算机部署拓扑。 对于支持最多 110000 MBAM 客户端的生产环境，建议使用此拓扑。

![mbam 4 计算机部署拓扑。](images/mbam-4-computer.jpg)

在此配置中，MBAM 功能安装在以下配置中：

1.  在服务器上安装恢复和硬件数据库、合规性和审核数据库以及合规性和审核报告。

2.  "管理和监视服务器" 功能安装在网络负载平衡（NLB）服务器群集中配置的服务器上。

3.  MBAM 组策略模板安装在能够修改组策略对象的计算机上。

### 五台计算机配置

下图显示了用于 MBAM 的五台计算机部署拓扑。 对于支持最多 135000 MBAM 客户端的生产环境，我们建议采用此拓扑。

![mbam 五台计算机部署拓扑。](images/mbam-5-computer.jpg)

在此配置中，MBAM 功能安装在以下配置中：

1.  恢复和硬件数据库安装在服务器上。

2.  在服务器上安装合规性和审核数据库以及合规性和审核报告。

3.  "管理和监视服务器" 功能安装在网络负载平衡（NLB）服务器群集中配置的服务器上。

4.  MBAM 组策略模板安装在能够修改组策略对象的计算机上。

[如何在分布式服务器上安装和配置 MBAM](how-to-install-and-configure-mbam-on-distributed-servers-mbam-1.md)

[如何针对 MBAM 配置网络负载均衡](how-to-configure-network-load-balancing-for-mbam.md)

## 适用于 MBAM 1.0 服务器功能部署的其他资源


[部署 MBAM 1.0](deploying-mbam-10.md)

 

 





