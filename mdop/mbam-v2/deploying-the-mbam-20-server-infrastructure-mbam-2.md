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
ms.openlocfilehash: 22a69fe8f6853c02a818bb026b36771cd09632f0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803632"
---
# 部署 MBAM 2.0 服务器基础结构


适用于独立拓扑的 Microsoft BitLocker 管理和监视（MBAM）服务器功能可以在生产环境中的两个或多个服务器上以不同的配置进行安装。 对于生产环境，建议的配置是两台服务器，具体取决于你的可伸缩性要求。 仅在测试环境中使用单个服务器进行 MBAM 安装。 有关规划 MBAM Server 功能部署的详细信息，请参阅[规划2.0 服务器部署](planning-for-mbam-20-server-deployment-mbam-2.md)。

下图显示了如何配置建议的两服务器 MBAM 部署的示例。 此配置在生产环境中最多支持 200000 MBAM 客户端。 体系结构映像中的服务器功能和数据库将在下一节中介绍，并且在建议您安装它们的计算机或服务器下列出。

![mbam 2 2-服务器部署拓扑](images/mbam2-3-servers.gif)

## 管理和监视服务器


此服务器上安装了以下功能：

-   **管理和监视服务器**。 "管理和监视服务器" 功能安装在 Windows 服务器上，由技术支持网站和监视 web 服务组成。

-   **自助服务门户**。 自助服务门户已安装在 Windows 服务器上。 自助服务门户使客户端计算机上的最终用户能够独立登录到网站，在那里，他们可以获取恢复密钥以恢复已锁定的 BitLocker 卷。

## 数据库服务器


此服务器上安装了以下功能：

-   **恢复数据库**。 恢复数据库安装在 Windows server 和受支持的 Microsoft SQLServer 实例中。 此数据库存储从 MBAM 客户端计算机收集的恢复数据。

-   **合规性和审核数据库**。 合规性和审核数据库安装在 Windows server 和支持的 SQLServer 实例上。 此数据库存储 MBAM 客户端计算机的合规性数据。 此数据主要用于 SQL Server Reporting Services （SSRS）主机的报表。

-   **合规性和审核报告**。 合规性和审核报告安装在 Windows server 和支持 SQL Server Reporting Services （SSRS）功能的 SQLServer 实例中。 这些报表提供可从技术支持网站或直接从 SSRS 服务器访问的 MBAM 报表。

## 管理工作站


以下功能安装在管理工作站上，后者可以是 Windows 服务器或客户端计算机。

-   **策略模板**。 策略模板包含定义用于 BitLocker 驱动器加密的 MBAM 实现设置的组策略。 你可以在任何服务器或工作站上安装策略模板，但它通常安装在管理工作站上，后者是受支持的 Windows server 或客户端计算机。 工作站不必是专用计算机。

## <a href="" id="---------mbam-client"></a> MBAM 客户端


MBAM 客户端安装在 Windows 计算机上，具有以下特征：

-   使用组策略强制对企业中的客户端计算机进行 BitLocker 驱动器加密。

-   收集三个 BitLocker 数据驱动器类型的恢复密钥：操作系统驱动器、固定数据驱动器和可移动数据（USB）驱动器。

-   收集计算机的合规性数据并将数据传递到报告系统。

## 用于部署 MBAM 2.0 服务器功能的其他资源


[部署 MBAM 2.0](deploying-mbam-20-mbam-2.md)

 

 





