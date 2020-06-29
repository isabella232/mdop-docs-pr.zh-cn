---
title: 计划 MBAM 2.0 服务器部署
description: 计划 MBAM 2.0 服务器部署
author: dansimp
ms.assetid: b57f1a42-134f-4997-8697-7fbed08e2fc4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 57e6510556522dce029c958172bd89a361e06b83
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798089"
---
# 计划 MBAM 2.0 服务器部署


Microsoft BitLocker 管理和监视（MBAM）服务器基础结构取决于一组服务器功能，这些功能可以基于企业的要求安装在一台或多台服务器计算机上。 如果你要安装 Microsoft BitLocker 管理并通过 Configuration Manager 拓扑进行监视，请参阅[计划通过 Configuration Manager 部署 MBAM](planning-to-deploy-mbam-with-configuration-manager-2.md)。

**注意** 建议仅针对测试环境对单个服务器上的 Microsoft BitLocker 管理和监视进行安装。

 

## 规划 MBAM Server 部署


MBAM 服务器部署的基础结构包括以下功能：

-   恢复数据库

-   合规性和审核数据库

-   合规性和审核报告

-   自助服务门户

-   管理和监视服务器

-   MBAM 组策略模板

MBAM 服务器数据库和功能可以安装在不同的配置中，具体取决于你的可伸缩性要求。 所有 MBAM 服务器功能都可以安装在一台服务器上，也可以分布在多台服务器上。 我们建议你对生产环境使用双服务器配置，尽管还可以使用2到4台服务器的配置，具体取决于你的计算要求。

每个 MBAM 功能都具有特定的先决条件。 有关服务器功能必备条件和硬件和软件要求的完整列表，请参阅[MBAM 2.0 部署先决条件](mbam-20-deployment-prerequisites-mbam-2.md)和[MBAM 2.0 支持的配置](mbam-20-supported-configurations-mbam-2.md)。

除了服务器相关的 MBAM 功能之外，服务器设置应用程序还包含一个 MBAM 组策略模板。 该模板包含您配置用于管理企业中的 BitLocker 驱动器加密的组策略对象（GPO）设置。 你可以在任何可运行组策略管理控制台（GPMC）或高级组策略管理（AGPM）的计算机上安装此模板。

在规划 MBAM 服务器部署时，请考虑 MBAM 中的 BitLocker 恢复密钥仅供一次性使用，之后恢复密钥将过期。 为了使密钥在使用后过期，必须通过问讯台门户或自助服务门户进行检索。

## MBAM 服务器功能的部署顺序


若要在多台服务器上部署 MBAM 功能，必须按照以下顺序安装这些功能：

1.  恢复数据库

2.  合规性和审核数据库

3.  合规性审核和报告

4.  自助服务门户

5.  管理和监视服务器

6.  MBAM 组策略模板

**注意** 跟踪安装每个功能的计算机的名称。 您必须在整个安装过程中使用此信息。 您可以打印和使用部署清单来帮助完成这一工作。 有关 MBAM 部署清单的详细信息，请参阅[MBAM 2.0 部署清单](mbam-20-deployment-checklist-mbam-2.md)。

 

## 相关主题


[计划部署 MBAM 2.0](planning-to-deploy-mbam-20-mbam-2.md)

[部署 MBAM 2.0 服务器基础结构](deploying-the-mbam-20-server-infrastructure-mbam-2.md)

 

 





