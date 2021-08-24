---
title: 入门 - 结合使用 MBAM 和 Configuration Manager
description: 入门 - 结合使用 MBAM 和 Configuration Manager
author: dansimp
ms.assetid: b0a1d3cc-0b01-4b69-a2cd-fd09fb3beda4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9f23a0eba923608fb6e25e44ee2843f3cde4c2dc
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910807"
---
# <a name="getting-started---using-mbam-with-configuration-manager"></a>入门 - 结合使用 MBAM 和 Configuration Manager


安装 Microsoft BitLocker 管理和监视 (MBAM) 时，可以选择将 MBAM 与 Configuration Manager 2007 或 System Center 2012 Configuration Manager 相集成拓扑。 有关 MBAM 支持的 Configuration Manager 支持的版本列表，请参阅计划使用[Configuration Manager 部署 MBAM。](planning-to-deploy-mbam-with-configuration-manager-2.md) 在集成拓扑中，硬件合规性和报告功能从 MBAM 中删除，并且从 Configuration Manager 访问。

**重要提示**  
Windows使用 Configuration Manager 2007 安装 MBAM 的集成拓扑时，不支持转到。

 

## <a name="using-mbam-with-configuration-manager"></a>结合使用 MBAM 和 Configuration Manager


MBAM 的集成基于新的配置包，该配置包将以下三项安装到 Configuration Manager 2007 或 System Center 2012 Configuration Manager 中，以下各节对此进行了详细介绍：

由配置项和配置基线组成的配置数据

集合

报告

### <a name="configuration-data"></a>配置数据

配置数据将安装名为"BitLocker Protection"的配置基线，其中包含两个配置项："BitLocker 操作系统驱动器保护"和"BitLocker 固定数据驱动器保护"。 配置基线将部署到集合，在安装 MBAM 时也会创建该集合。 这两个配置项为评估客户端计算机的合规性状态提供了基础。 此信息在 Configuration Manager 中捕获、存储和评估。 配置项基于操作系统驱动器的合规性要求 (OSD) 和固定数据驱动器 (FDs) 。 收集已部署计算机所需的详细信息，以便评估这些驱动器类型的合规性。 默认情况下，配置基线每 12 小时评估一次合规性状态，并将合规性数据发送到 Configuration Manager。

### <a name="collection"></a>集合

MBAM 创建一个称为 MBAM 支持的计算机的集合。 配置基线面向此集合中的客户端计算机。 默认情况下，这是一个动态集合，每 12 小时运行一次，并评估成员身份。 成员身份基于三个条件：

-   它是支持的版本，Windows操作系统。 目前，当 Windows 7 企业版 Go 在 Windows 8 企业版 上运行时，MBAM 仅Windows 7 企业版和 Windows 7 旗舰版、Windows 8 企业版 和 Windows To Windows Go。

-   它是一台物理计算机。 不支持虚拟机。

-   TPM (受信任的平台模块) 可用。 7 版本需要兼容版本的 TPM 1.2 Windows更高版本。 Windows 8 Windows"转到"不需要 TPM。

该集合针对所有计算机进行评估，并创建兼容计算机的子集，这些计算机为 MBAM 集成的合规性评估和报告提供了基础。

### <a name="reports"></a>报告

有四个报告可用于查看合规性。 它们是：

-   **BitLocker 企业级仪表板**– 为 IT 管理员提供单个报告上三种不同的信息视图：合规性状态分布、不兼容 – 错误分布和合规性状态分布（按驱动器类型）。 通过报告上的向下钻取选项，IT 管理员可单击数据并查看与选择的状态匹配的计算机列表。

-   **BitLocker 企业级合规性详细信息**– 允许 IT 管理员查看有关企业的 BitLocker 加密合规性状态的信息，并包括每台计算机的合规性状态。 通过报告上的向下钻取选项，IT 管理员可单击数据并查看与选择的状态匹配的计算机列表。

-   **BitLocker 计算机合规性** – 允许 IT 管理员查看单个计算机并确定报告计算机时给定状态是否合规的原因。 该报告还显示操作系统驱动器的加密状态 (OSD) 和固定数据驱动器 (FDS) 。

-   **BitLocker 企业级合规性摘要**- 允许 IT 管理员使用 MBAM 策略查看企业合规性的状态。 将评估每台计算机的状态，并且报告根据策略显示企业中所有计算机的合规性摘要。 通过报告上的向下钻取选项，IT 管理员可单击数据并查看与选择的状态匹配的计算机列表。

## <a name="high-level-architecture-of-mbam-with-configuration-manager"></a>High-Level Configuration Manager 实现 MBAM 的体系结构


下图显示了具有 Configuration Manager 拓扑的 MBAM 体系结构。 此配置在生产环境中最多支持 200，000 个 MBAM 客户端。

![具有配置管理器的 mbam 体系结构。](images/mbam2-cmserver.gif)

以下是有关此体系结构的服务器、数据库和功能的说明。 体系结构映像中的服务器功能和数据库列在建议您安装它们的计算机或服务器下。

-   **数据库服务器**–**恢复数据库**、**审核数据库**和**** 审核报告安装在 Windows 服务器上，并支持SQL Server实例。 恢复数据库存储从 MBAM 客户端计算机收集的恢复数据。 审核数据库存储从已访问恢复数据的客户端计算机收集的审核活动数据。 审核报告提供有关企业中客户端计算机的合规性状态的数据。

-   **Configuration Manager 主站点服务器**– Configuration Manager 服务器包含具有 System Center Configuration Manager 集成拓扑的 MBAM 服务器安装，该拓扑必须安装在 Configuration Manager 主站点服务器上。 Configuration Manager Server 从客户端计算机收集硬件清单信息，并用于报告客户端计算机的 BitLocker 合规性。 运行 MBAM 安装服务器安装时，集合和配置数据将安装在 Configuration Manager 主站点服务器上。

-   **管理和监控服务器**-**管理和**监控服务器安装在 Windows服务器上，由管理和监控网站以及监控 Web 服务组成。 管理和监控网站用于审核活动以及访问恢复 (例如，BitLocker 恢复密钥) 。 自助式 **门户也** 安装在管理和监控服务器上。 该门户使客户端计算机上的最终用户能够在丢失或忘记 BitLocker 密码时独立登录到网站，获取恢复密钥。 审核报告也安装在管理和监控服务器上。

-   **管理工作站** - **策略模板** 由定义 BitLocker 驱动器加密的 MBAM 实现设置的组策略对象组成。 可以在任何服务器或工作站上安装策略模板，但它通常安装在受服务器或客户端计算机支持Windows工作站上。 工作站不需要是专用计算机。

-   **MBAM** 客户端 **和 Configuration Manager** 客户端计算机

    -   **MBAM 客户端**执行以下任务：

        -   使用组策略对象强制对企业中的客户端计算机进行 BitLocker 加密。

        -   收集三种 BitLocker 数据驱动器类型的恢复密钥：操作系统驱动器、固定数据驱动器和 USB 驱动器 (可移动) 密钥。

        -   收集有关客户端计算机的恢复信息和计算机信息。

    -   **Configuration Manager 客户端** – Configuration Manager 客户端使 Configuration Manager 能够收集有关客户端计算机的硬件兼容性数据，并且使 Configuration Manager 能够报告合规性信息。

## <a name="related-topics"></a>相关主题


[结合使用 MBAM 和 Configuration Manager](using-mbam-with-configuration-manager.md)

 

 





