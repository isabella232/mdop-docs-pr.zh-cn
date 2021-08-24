---
title: 部署 MBAM 2.0 服务器基础结构
description: 部署 MBAM 2.0 服务器基础结构
author: dansimp
ms.assetid: 52e68d94-e2b4-4b06-ae55-f900ea6cc59f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8aee322b9a1aacbf98ff8362e95e21c2dd3d289a
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910797"
---
# <a name="deploying-the-mbam-20-server-infrastructure"></a>部署 MBAM 2.0 服务器基础结构


独立拓扑的 Microsoft BitLocker 管理和 (MBAM) Server 功能可以安装在生产环境中的两台或多台服务器上的不同配置中。 根据可伸缩性要求，建议为生产环境配置两台服务器。 仅在测试环境中将单个服务器用于 MBAM 安装。 有关规划 MBAM Server 功能部署的信息，请参阅[Planning for MBAM 2.0 Server Deployment。](planning-for-mbam-20-server-deployment-mbam-2.md)

下图显示了如何配置建议的双服务器 MBAM 部署的示例。 此配置在生产环境中最多支持 200，000 个 MBAM 客户端。 体系结构映像中的服务器功能和数据库如下一节所述，它们列在建议您安装它们的计算机或服务器下。

![mbam 2 双服务器部署拓扑。](images/mbam2-3-servers.gif)

## <a name="administration-and-monitoring-server"></a>管理和监控服务器


此服务器上安装了以下功能：

-   **管理和监控服务器**。 管理和监控服务器功能安装在 Windows 服务器上，由技术支持网站和监控 Web 服务组成。

-   **自助服务门户**。 Self-Service门户安装在 Windows 服务器上。 利用Self-Service门户，客户端计算机上的最终用户可以独立登录到网站，他们可以从网站获取恢复密钥以恢复锁定的 BitLocker 卷。

## <a name="database-server"></a>数据库服务器


此服务器上安装了以下功能：

-   **恢复数据库**。 恢复数据库安装在 Windows 服务器上和支持的 Microsoft SQL Server。 此数据库存储从 MBAM 客户端计算机收集的恢复数据。

-   **合规性和审核数据库**。 合规性和审核数据库安装在 Windows 服务器上和支持的 SQL Server。 此数据库存储 MBAM 客户端计算机的合规性数据。 此数据主要用于 SSRS SQL Server Reporting Services (报告) 报告。

-   **合规性和审核报告**。 合规性和审核报告安装在安装了 Windows SSRS SQL Server 的 SQL Server 服务器上，SQL Server Reporting Services (SSRS) 安装。 这些报告提供 MBAM 报告，你可以从 Help Desk 网站或直接从 SSRS 服务器访问这些报告。

## <a name="management-workstation"></a>管理工作站


以下功能安装在管理工作站上，该工作站可以是Windows或客户端计算机。

-   **策略模板**。 策略模板由定义 BitLocker 驱动器加密的 MBAM 实现设置的组策略组成。 可以在任何服务器或工作站上安装策略模板，但它通常安装在管理工作站上，该工作站是受Windows服务器或客户端计算机支持。 工作站不需要是专用计算机。

## <a name="mbam-client"></a><a href="" id="---------mbam-client"></a> MBAM 客户端


MBAM 客户端安装在 Windows计算机上，具有以下特征：

-   使用组策略强制对企业中的客户端计算机进行 BitLocker 驱动器加密。

-   收集三种 BitLocker 数据驱动器类型的恢复密钥：操作系统驱动器、固定数据驱动器和 USB 驱动器 (可移动) 密钥。

-   收集计算机的合规性数据，并将数据传递给报告系统。

## <a name="other-resources-for-deploying-mbam-20-server-features"></a>用于部署 MBAM 2.0 服务器功能的其他资源


[部署 MBAM 2.0](deploying-mbam-20-mbam-2.md)

 

 





