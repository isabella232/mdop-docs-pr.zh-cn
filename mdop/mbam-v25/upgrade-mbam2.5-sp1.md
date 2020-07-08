---
title: 从 MBAM 2.5 升级到 MBAM 2.5 SP1 服务发布更新
author: dansimp
ms.author: ksharma
manager: miaposto
audience: ITPro
ms.topic: article
ms.prod: w10
ms.localizationpriority: Normal
ms.openlocfilehash: 372822e1ec049871c62af9f429290b88bbfac949
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798128"
---
# 从 MBAM 2.5 升级到 MBAM 2.5 SP1 服务发布更新

本文提供了升级 Microsoft BitLocker 管理和监视（MBAM）2.5 到 MBAM 2.5 Service Pack 1 （SP1）和[Microsoft 桌面优化包（MDOP）在独立配置中可能2019服务更新](https://support.microsoft.com/help/4505175/may-2019-servicing-release-for-microsoft-desktop-optimization-pack)的分步说明。

在本指南中，我们将使用两个服务器的配置。 一台服务器将是运行 Microsoft SQL Server 2016 的数据库服务器。 此服务器将托管 MBAM 数据库和报告。 另一台服务器将是 Windows Server 2012 R2 web 服务器。 此服务器将托管 "管理和监视" 和 "自助服务门户"。

## 准备升级 MBAM 2.5 SP1

### 了解你的环境中的 MBAM 服务器

1. SQL Server 数据库引擎：托管 MBAM 数据库的服务器。
2. SQL Server Reporting Services：托管 MBAM 报表的服务器。
3. Internet information Services （IIS） web 服务器：托管 MBAM Web 应用程序和 MBAM 服务的服务器。
4. 可选Microsoft System Center Configuration Manager 主站点服务器：在此服务器上运行 MBAM 配置应用程序，以将 MBAM 报告与 Configuration Manager 集成。 然后，这些报表将与 Configuration Manager SQL Server Reporting Services （SSRS）实例上的现有配置管理器报告合并。

### 标识服务帐户、组、服务器名称和报表 URL

1. 标识 IIS web 服务器用于在 MBAM 数据库中读取和写入数据的 MBAM 应用程序池服务帐户。
2. 标识在 MBAM web 功能配置和 "报表" web 服务 URL 期间使用的组。
3. 标识 SQL Server 名称和实例名称。 观看此视频以了解详细信息。

    > [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE3ANP1]

4. 确定用于从合规性和审核数据库中读取合规性数据的 SQL Server Reporting Services 帐户。 观看此视频以了解详细信息。

    > [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE3ALdZ]

## 将 MBAM 基础结构升级到可用的最新版本

MBAM 服务器基础结构的安装或升级始终按下面列出的顺序执行：

- SQL Server 数据库引擎：数据库
- SQL Server Reporting Services：报表
- Web 服务器： Web 应用程序
- SCCM 服务器： if 适用的 SCCM 集成报表
- 客户端： MBAM 代理或客户端更新
- 组策略模板：使用新模板更新现有组策略，并启用现有 MBAM 组策略上的新设置

> [!NOTE]
> 我们建议你先创建 MBAM 数据库的完整数据库备份，然后再运行升级。

### 升级 MBAM SQL Server

观看此视频，了解如何升级 MBAM SQL Server：

   > [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE3ALew]

### 升级 MBAM Web 服务器

观看此视频，了解如何升级 MBAM Web 服务器：

   > [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE3ALex]

## 详细信息

有关 MBAM 2.5 SP1 中已知问题的详细信息，请参阅[MBAM 2.5 SP1 的发行说明](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/release-notes-for-mbam-25-sp1)。
