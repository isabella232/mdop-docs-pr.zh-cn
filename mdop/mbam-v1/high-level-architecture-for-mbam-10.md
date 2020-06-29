---
title: MBAM 1.0 的高级别体系结构
description: MBAM 1.0 的高级别体系结构
author: dansimp
ms.assetid: b1349196-88ed-4d6c-8a1d-998f18127b6b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: de3529fdb565859fcc212d1a9a614ac4ef4b183e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803728"
---
# MBAM 1.0 的高级别体系结构


Microsoft BitLocker 管理和监视（MBAM）是一种客户端/服务器数据加密解决方案，可帮助你简化 BitLocker 预配和部署、改进 BitLocker 合规性和报告，并减少支持费用。 MBAM 包括本主题中所述的功能。

此外，还提供了一种视频，提供 MBAM 体系结构和 MBAM 设置的概述。 有关详细信息，请参阅[MBAM 部署和体系结构概述](https://go.microsoft.com/fwlink/p/?LinkId=258392)。

## 体系结构概述


下图显示了 MBAM 体系结构。 将显示单服务器 MBAM 部署拓扑，介绍 MBAM 功能。 但是，建议仅针对实验室环境使用此 MBAM 部署拓扑。

**注意** 对于生产部署，建议至少使用三台计算机 MBAM 部署拓扑。 有关 MBAM 部署拓扑的详细信息，请参阅[部署 MBAM 1.0 服务器基础结构](deploying-the-mbam-10-server-infrastructure.md)。

 

![mbam 单服务器部署拓扑](images/mbam-1-server.jpg)

1.  **管理和监视服务器**。 MBAM 管理和监视服务器安装在 Windows 服务器上，并托管 MBAM 管理和管理网站以及监视 web 服务。 MBAM 管理和管理网站用于确定企业合规性状态、审核活动、管理硬件功能和访问恢复数据，如 BitLocker 恢复密钥。 管理和监视服务器连接到以下数据库和服务：

    -   恢复和硬件数据库。 恢复和硬件数据库安装在基于 Windows 的服务器上，并且支持 SQLServer 实例。 此数据库存储从 MBAM 客户端计算机收集的恢复数据和硬件信息。

    -   合规性和审核数据库。 合规性和审核数据库安装在 Windows server 上并支持 SQLServer 实例。 此数据库存储 MBAM 客户端计算机的合规性数据。 此数据主要用于由 SQL Server Reporting Services （SSRS）托管的报表。

    -   合规性和审核报告。 合规性和审核报告安装在基于 Windows 的服务器上，并且支持安装了 SSRS 功能的 SQLServer 实例。 这些报表提供 Microsoft BitLocker 管理和监视报告。 可以从 MBAM 管理和管理网站或直接从 SSRS 服务器访问这些报告。

2.  **MBAM 客户端**。 Microsoft BitLocker 管理和监视客户端执行以下任务：

    -   使用组策略强制对企业中的客户端计算机进行 BitLocker 加密。

    -   收集三个 BitLocker 数据驱动器类型的恢复密钥：操作系统驱动器、固定数据驱动器和可移动数据（USB）驱动器。

    -   收集有关客户端计算机的恢复信息和硬件信息。

    -   收集计算机的合规性数据并将数据传递到报告系统。

3.  **策略模板**。 MBAM 组策略模板安装在受支持的基于 Windows 的服务器或客户端计算机上。 此模板用于指定用于 BitLocker 驱动器加密的 MBAM 实现设置。

## 相关主题


[MBAM 1.0 入门](getting-started-with-mbam-10.md)

 

 





