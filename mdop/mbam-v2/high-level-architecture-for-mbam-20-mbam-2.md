---
title: MBAM 2.0 的高级别体系结构
description: MBAM 2.0 的高级别体系结构
author: dansimp
ms.assetid: 7f73dd3a-0b1f-4af6-a2f0-d0c5bc5d183a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ddc061a1aec5141548c2d2141be38f8501d2244d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803621"
---
# MBAM 2.0 的高级别体系结构


Microsoft BitLocker 管理和监视（MBAM）是一种客户端/服务器解决方案，可帮助你简化 BitLocker 预配和部署、改进 BitLocker 的合规性和报告，并减少支持费用。 Microsoft BitLocker 管理和监视包括本主题中所述的功能。

Microsoft BitLocker 管理和监视可在独立拓扑中部署，或在与 Microsoft System Center Configuration Manager 2007 或 MicrosoftSystemCenter2012 ConfigurationManager 集成的拓扑中部署。 本主题介绍独立拓扑的体系结构。 有关在集成配置管理器拓扑中部署的信息，请参阅将[MBAM 与 Configuration Manager 结合使用](using-mbam-with-configuration-manager.md)。

下图显示了生产环境的 MBAM 推荐体系结构，它由两台服务器和一个管理工作站组成。 此体系结构支持最多 200000 MBAM 客户端。 体系结构映像中的服务器功能和数据库将在下一节中介绍，并且在建议您安装它们的计算机或服务器下列出。

**注意** 单服务器体系结构应仅在测试环境中使用。

 

![mbam 2 2-服务器部署拓扑](images/mbam2-3-servers.gif)

## 管理和监视服务器


此服务器上安装了以下功能：

-   **管理和监视服务器**。 "管理和监视服务器" 功能安装在 Windows 服务器上，包括 "管理和监视" 网站，其中包括报表和 "技术支持" 门户以及 "监视 web 服务"。

-   **自助服务门户**。 自助服务门户已安装在 Windows 服务器上。 自助服务门户使客户端计算机上的最终用户能够独立登录到网站，在那里，他们可以获取恢复密钥以恢复已锁定的 BitLocker 卷。

## 数据库服务器


此服务器上安装了以下功能：

-   **恢复数据库**。 恢复数据库安装在 Windows server 和受支持的 Microsoft SQLServer 实例中。 此数据库存储从 MBAM 客户端计算机收集的恢复数据。

-   **合规性和审核数据库**。 合规性和审核数据库安装在 Windows server 和支持的 SQLServer 实例上。 此数据库存储 MBAM 客户端计算机的合规性数据。 此数据主要用于 SQL Server Reporting Services （SSRS）主机的报表。

-   **合规性和审核报告**。 合规性和审核报告安装在 Windows server 和支持 SQL Server Reporting Services （SSRS）功能的 SQLServer 实例中。 这些报表提供可从 "管理" 和 "监视" 网站或直接从 SSRS 服务器访问的 MBAM 报表。

## 管理工作站


以下功能安装在管理工作站上，后者可以是 Windows 服务器或客户端计算机。

-   **策略模板**。 策略模板由定义用于 BitLocker 驱动器加密的 MBAM 实现设置的组策略设置组成。 你可以在任何服务器或工作站上安装策略模板，但它通常安装在管理工作站上，后者是受支持的 Windows server 或客户端计算机。 工作站不必是专用计算机。

## <a href="" id="---------mbam-client"></a> MBAM 客户端


MBAM 客户端安装在 Windows 计算机上，具有以下特征：

-   使用组策略强制对企业中的客户端计算机进行 BitLocker 驱动器加密。

-   收集三个 BitLocker 数据驱动器类型的恢复密钥：操作系统驱动器、固定数据驱动器和可移动数据（USB）驱动器。

-   收集计算机的合规性数据并将数据传递到报告系统。

## 相关主题


[MBAM 2.0 入门](getting-started-with-mbam-20-mbam-2.md)

 

 





