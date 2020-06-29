---
title: MBAM 2.0 的高可用性
description: MBAM 2.0 的高可用性
author: dansimp
ms.assetid: 244ee013-9e2a-48d2-b842-4e10594fd74f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6482a099d96aee731f81368b8b787325e592c453
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803626"
---
# MBAM 2.0 的高可用性


本主题提供有关 Microsoft BitLocker 管理和监视（MBAM）的高可用性安装的基本信息。 在此版本的 MBAM 中不完全支持高可用性方案，因此此处未介绍它们。 建议你搜索相关博客和论坛，用户在这里介绍他们在其环境中如何成功配置 MBAM 的高可用性。

## MBAM 的高可用性方案


Microsoft BitLocker 管理和监视设计为具有容错能力。 如果服务器不可用，则不会对用户产生负面影响。 例如，如果 MBAM 代理无法连接到 MBAM web 服务器，则不应提示用户执行操作。

规划 MBAM 安装时，请考虑以下项目，这些项目可能会影响 MBAM 服务的可用性：

-   驱动器加密和恢复密码-如果无法 escrowed 恢复密码，则不会在客户端计算机上开始加密。

-   合规性状态数据上载-如果托管合规性状态报告服务的服务器不可用，则合规性数据不会保持最新。

-   技术支持恢复密钥访问-如果帮助台无法访问 MBAM 数据库信息，技术支持无法向用户提供恢复密钥。

-   报表的可用性-如果托管合规性和审核报告的服务器不可用，则报告将不可用。

## <a href="" id="how-the-mbam-backup-uses-the-volume-shadow-copy-service--vss--"></a>MBAM 备份如何使用卷影复制服务（VSS）


MBAM 2.0 提供了一个卷影复制服务（VSS）编写器，它称为 Microsoft BitLocker 管理和管理编写器，可促进合规性和审核数据库和恢复数据库的备份。

MBAM 服务器 Windows Installer 注册 MBAM VSS 书写器。 在 VSS 写入程序注册过程中，任何失败都会导致 MBAM 服务器安装回滚。 在将合规性和审核数据库以及恢复数据库安装在不同服务器上的拓扑中，在每台服务器上注册了一个单独的 MBAM VSS 编写器实例。 MBAM VSS 编写器依赖于 SQL Server VSS 书写器。 SQL Server VSS 编写器已注册为 Microsoft SQL Server 安装的一部分。 使用 VSS 编写器执行备份的任何备份技术均可发现 MBAM VSS 书写器。

## 相关主题


[维护 MBAM 2.0](maintaining-mbam-20-mbam-2.md)

 

 





