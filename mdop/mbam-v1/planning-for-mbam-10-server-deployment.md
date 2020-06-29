---
title: 计划 MBAM 1.0 服务器部署
description: 计划 MBAM 1.0 服务器部署
author: dansimp
ms.assetid: 3cbef284-3092-4c42-9234-2826b18ddef1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 76ff9c444ce3f9c39161341610fb0cd9a763dc6d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798043"
---
# 计划 MBAM 1.0 服务器部署


Microsoft BitLocker 管理和监视（MBAM）服务器基础结构取决于一组服务器功能，这些功能可以基于企业的要求安装在一台或多台服务器计算机上。

## 规划 MBAM Server 部署


以下 MBAM 功能表示 MBAM 服务器部署的服务器基础结构：

-   恢复和硬件数据库

-   合规性和审核数据库

-   合规性和审核报告

-   管理和监视服务器

MBAM 服务器数据库和功能可以安装在不同的配置中，具体取决于你的可伸缩性需求。 所有 MBAM 服务器功能都可以安装在一台服务器上，也可以分布在多台服务器上。 通常，我们建议你对生产环境使用三服务器或五台服务器配置，尽管也可以使用两台或四台服务器的配置，具体取决于你的计算需求。

**注意** 有关 MBAM 和推荐部署拓扑的性能可伸缩性的详细信息，请参阅 MBAM 可伸缩性和高可用性指南白皮书 <https://go.microsoft.com/fwlink/p/?LinkId=258314> 。

 

每个 MBAM 功能都具有特定的先决条件。 有关服务器功能必备条件和硬件和软件要求的完整列表，请参阅[MBAM 1.0 部署先决条件](mbam-10-deployment-prerequisites.md)和[MBAM 1.0 支持的配置](mbam-10-supported-configurations.md)。

除了服务器相关的 MBAM 功能之外，服务器设置应用程序还包含一个 MBAM 组策略模板。 此模板可以安装在可运行组策略管理控制台（GPMC）或高级组策略管理（AGPM）的任何计算机上。

## MBAM 服务器功能的部署顺序


部署 MBAM 服务器功能时，请按以下顺序安装这些功能：

1.  恢复和硬件数据库

2.  合规性和审核数据库

3.  合规性审核和报告

4.  管理和监视服务器

5.  策略模板

**注意** 跟踪安装每个功能的计算机的名称。 您将在整个安装过程中使用此信息。 你可以打印和使用部署清单来帮助你完成安装过程。 有关 MBAM 部署清单的详细信息，请参阅[MBAM 1.0 部署清单](mbam-10-deployment-checklist.md)。

 

## 相关主题


[计划部署 MBAM 1.0](planning-to-deploy-mbam-10.md)

[部署 MBAM 1.0 服务器基础结构](deploying-the-mbam-10-server-infrastructure.md)

 

 





