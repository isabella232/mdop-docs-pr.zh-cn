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
ms.openlocfilehash: 63099d425b51bfde52eac59771007b1c765acf05
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910417"
---
# <a name="deploying-the-mbam-10-server-infrastructure"></a>部署 MBAM 1.0 服务器基础结构


可以使用 1 到 5 台服务器 (不同配置中的 Microsoft BitLocker 管理和) MBAM 和 MBAM 服务器功能。 通常，您应当为生产环境使用三到五台服务器的配置，具体取决于可伸缩性需求。 有关 MBAM 的性能可伸缩性和推荐的部署拓扑结构详细信息，请参阅 [MBAM 可伸缩性和High-Availability指南白皮书](https://go.microsoft.com/fwlink/p/?LinkId=258314)。

## <a name="deploy-all-mbam-10-on-a-single-server"></a>在单台服务器上部署所有 MBAM 1.0


在此配置中，所有 MBAM 功能都安装在单台服务器上。 MBAM 服务器基础结构的此部署拓扑将支持多达 21，000 个 MBAM 客户端计算机。

**重要提示**  
支持此配置，但建议仅进行测试。

 

本节中的过程介绍在单台服务器上完全安装 MBAM 功能。

[如何在单个服务器上安装和配置 MBAM](how-to-install-and-configure-mbam-on-a-single-server-mbam-1.md)

## <a name="deploy-mbam-10-on-distributed-servers"></a>在分布式服务器上部署 MBAM 1.0


MBAM 功能可以安装在不同的配置中，具体取决于可伸缩性需求。 若要详细了解如何规划 MBAM 服务器功能部署，请参阅规划 [MBAM 1.0 服务器部署](planning-for-mbam-10-server-deployment.md)。

本节中的过程介绍在分布式服务器上完全安装 MBAM 功能。

### <a name="three-computer-configuration"></a>三台计算机配置

下图显示了 MBAM 的三台计算机部署拓扑。 我们建议为最多支持 55，000 个 MBAM 客户端的生产环境提供此拓扑。

![mbam 三台计算机部署拓扑。](images/mbam-3-server.jpg)

在此配置中，MBAM 功能安装在以下配置中：

1.  恢复和硬件数据库、合规性和审核数据库以及合规性和审核报告已安装在服务器上。

2.  管理和监控服务器功能已安装在服务器上。

3.  MBAM 组策略模板安装在能够修改组策略对象或 GPO (的计算机上) 。

### <a name="four-computer-configuration"></a>四台计算机配置

下图显示了 MBAM 的四台计算机部署拓扑。 我们建议在支持多达 110，000 个 MBAM 客户端的生产环境中使用此拓扑。

![mbam 四台计算机部署拓扑。](images/mbam-4-computer.jpg)

在此配置中，MBAM 功能安装在以下配置中：

1.  恢复和硬件数据库、合规性和审核数据库以及合规性和审核报告已安装在服务器上。

2.  管理和监控服务器功能安装在在 NLB 服务器群集的网络负载平衡 (配置的) 服务器上。

3.  MBAM 组策略模板安装在能够修改组策略对象的计算机上。

### <a name="five-computer-configuration"></a>五台计算机配置

下图显示了 MBAM 的五台计算机部署拓扑。 我们建议针对支持多达 135，000 个 MBAM 客户端的生产环境采用此拓扑。

![mbam 五台计算机部署拓扑。](images/mbam-5-computer.jpg)

在此配置中，MBAM 功能安装在以下配置中：

1.  恢复和硬件数据库安装在服务器上。

2.  合规性和审核数据库以及合规性和审核报告已安装在服务器上。

3.  管理和监控服务器功能安装在在 NLB 服务器群集的网络负载平衡 (配置的) 服务器上。

4.  MBAM 组策略模板安装在能够修改组策略对象的计算机上。

[如何在分布式服务器上安装和配置 MBAM](how-to-install-and-configure-mbam-on-distributed-servers-mbam-1.md)

[如何针对 MBAM 配置网络负载均衡](how-to-configure-network-load-balancing-for-mbam.md)

## <a name="other-resources-for-mbam-10-server-features-deployment"></a>MBAM 1.0 服务器功能部署的其他资源


[部署 MBAM 1.0](deploying-mbam-10.md)

 

 





