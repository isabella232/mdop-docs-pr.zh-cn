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
ms.openlocfilehash: 654de38918102a41395efe37dc593ce8f49113e4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803714"
---
# 入门 - 结合使用 MBAM 和 Configuration Manager


安装 Microsoft BitLocker 管理和监视（MBAM）时，你可以选择将 MBAM 与 Configuration Manager 2007 或 SystemCenter2012 ConfigurationManager 集成的拓扑。 有关 MBAM 支持的 Configuration Manager 的受支持版本的列表，请参阅[计划使用 Configuration Manager 部署 MBAM](planning-to-deploy-mbam-with-configuration-manager-2.md)。 在集成拓扑中，将从 MBAM 中删除硬件合规性和报告功能，并从配置管理器访问。

**重要提示** 将 MBAM 的集成拓扑安装到 Configuration Manager 2007 时，不支持 Windows To Go。

 

## 结合使用 MBAM 和 Configuration Manager


MBAM 的集成基于将以下三项安装到 Configuration Manager 2007 或 SystemCenter2012 ConfigurationManager 的新配置包，这些内容将在以下部分中详细介绍：

包含配置项目和配置基线的配置数据

集合

报告

### 配置数据

配置数据将安装名为 "BitLocker 保护" 的配置基线，其中包含两个配置项目： "BitLocker 操作系统驱动器保护" 和 "BitLocker 固定数据驱动器保护"。 配置基线将部署到集合，该集合也会在安装 MBAM 时创建。 这两个配置项目提供评估客户端计算机合规性状态的基础。 在 Configuration Manager 中捕获、存储和评估此信息。 配置项目基于操作系统驱动器（OSDs）和固定数据驱动器（FDDs）的符合性要求。 收集已部署计算机所需的详细信息，以便可以评估这些驱动器类型的合规性。 默认情况下，配置基线每隔12小时评估合规性状态，并将合规性数据发送到配置管理器。

### 集合

MBAM 将创建一个名为 MBAM 支持的计算机的集合。 配置基线针对此集合中的客户端计算机。 这是一个动态集合，默认情况下，每12小时运行一次，并评估成员资格。 成员身份基于三个条件：

-   它是受支持的 Windows 操作系统版本。 目前，MBAM 在 windows 8 企业版上运行时，仅支持 Windows 7 企业版和 Windows 7 旗舰版、Windows 8 企业版和 Windows To Go。

-   它是一台物理计算机。 不支持虚拟机。

-   受信任的平台模块（TPM）可用。 Windows 7 需要使用兼容版本的 TPM 1.2 或更高版本。 Windows 8 和 Windows To Go 不需要 TPM。

该集合针对所有计算机进行评估，并创建兼容计算机的子集，这些计算机为 MBAM 集成提供了合规性评估和报告的基础。

### 报告

你可以使用四个报表来查看合规性。 它们是：

-   **BitLocker 企业合规性仪表板**-为 IT 管理员提供单个报告上的三种不同的信息视图：合规性状态分发、不合规性-错误分发以及合规性状态按驱动器类型分发。 报表上的向下钻取选项让 IT 管理员可以单击浏览数据并查看与所选状态相匹配的计算机列表。

-   **BitLocker 企业合规性详细信息**-允许 IT 管理员查看有关企业的 BitLocker 加密合规性状态的信息，包括每台计算机的合规性状态。 报表上的向下钻取选项让 IT 管理员可以单击浏览数据并查看与所选状态相匹配的计算机列表。

-   **BitLocker 计算机合规性**-允许 IT 管理员查看单个计算机，并确定报告其给定状态符合或不合规的原因。 该报告还显示操作系统驱动器（OSD）和固定数据驱动器（FDDs）的加密状态。

-   **BitLocker 企业合规性摘要**-允许 IT 管理员通过 MBAM 策略查看企业合规性的状态。 评估每台计算机的省/市/自治区，并且报告将显示企业中所有计算机针对策略的合规性摘要。 报表上的向下钻取选项让 IT 管理员可以单击浏览数据并查看与所选状态相匹配的计算机列表。

## 具有 Configuration Manager 的 MBAM 的高级别体系结构


下图显示了具有配置管理器拓扑的 MBAM 体系结构。 此配置在生产环境中最多支持 200000 MBAM 客户端。

![具有 configuration manager 的 mbam 体系结构](images/mbam2-cmserver.gif)

以下是对此体系结构的服务器、数据库和功能的描述。 体系结构图像中的服务器功能和数据库在建议您安装它们的计算机或服务器下列出。

-   **数据库服务器**-**恢复数据库**、**审核数据库**和**审核报告**安装在 Windows 服务器上并支持 SQLServer 实例。 恢复数据库存储从 MBAM 客户端计算机收集的恢复数据。 审核数据库存储从已访问恢复数据的客户端计算机收集的审核活动数据。 审核报告提供有关您的企业中客户端计算机的合规性状态的数据。

-   **Configuration Manager 主站点服务器**-配置管理器服务器包含具有 System Center Configuration Manager 集成拓扑的 MBAM 服务器安装（必须在 Configuration Manager 主站点服务器上安装）。 Configuration Manager 服务器从客户端计算机收集硬件清单信息，并用于报告客户端计算机的 BitLocker 合规性。 运行 MBAM 安装服务器安装时，将在 Configuration Manager 主站点服务器上安装一个集合和配置数据。

-   **管理和监视服务器**-**管理和监视服务器**安装在 Windows 服务器上，包括管理和监视网站以及监视 web 服务。 管理和监视网站用于审核活动和访问恢复数据（例如，BitLocker 恢复密钥）。 **自助服务门户**也安装在管理和监视服务器上。 门户使客户端计算机上的最终用户能够独立登录到网站，以便在丢失或忘记其 BitLocker 密码时获取恢复密钥。 审核报告还安装在管理和监视服务器上。

-   **管理工作站**-**策略模板**包含定义用于 BITLOCKER 驱动器加密的 MBAM 实现设置的组策略对象。 你可以在任何服务器或工作站上安装策略模板，但它通常安装在受支持的 Windows server 或客户端计算机的管理工作站上。 工作站不必是专用计算机。

-   **MBAM 客户端**和**Configuration Manager 客户端**计算机

    -   **MBAM 客户端**执行以下任务：

        -   使用组策略对象对企业中的客户端计算机强制执行 BitLocker 加密。

        -   收集三个 BitLocker 数据驱动器类型的恢复密钥：操作系统驱动器、固定数据驱动器和可移动数据（USB）驱动器。

        -   收集有关客户端计算机的恢复信息和计算机信息。

    -   **Configuration Manager 客户端**-配置管理器客户端使 configuration manager 能够收集有关客户端计算机的硬件兼容性数据，并使 configuration manager 能够报告合规性信息。

## 相关主题


[结合使用 MBAM 和 Configuration Manager](using-mbam-with-configuration-manager.md)

 

 





