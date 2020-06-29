---
title: MBAM 1.0 的高可用性
description: MBAM 1.0 的高可用性
author: dansimp
ms.assetid: 5869ecf8-1056-4c32-aecb-838a37e05d39
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 1227967d647cbfbc16967b5936066fd73d2412e2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803753"
---
# MBAM 1.0 的高可用性


本主题介绍了如何配置 Microsoft BitLocker 管理和监视（MBAM）的高可用性安装。

## MBAM 的高可用性方案


Microsoft BitLocker 管理和监视（MBAM）设计为可容错。 如果服务器不可用，则用户不会受到负面影响。 例如，如果 MBAM 代理无法连接到 MBAM web 服务器，则不应提示用户执行操作。

规划 MBAM 安装时，请考虑以下可能会影响 MBAM 服务可用性的问题：

-   驱动器加密和恢复密码-如果无法 escrowed 恢复密码，则不会在客户端计算机上启动加密。

-   合规性状态数据上载-如果托管合规性状态报告服务的服务器不可用，则合规性数据将不会保持最新。

-   技术支持恢复密钥访问-如果帮助台无法访问 MBAM 数据库信息，他们将无法向用户提供恢复密钥。

-   报表的可用性-如果托管合规性和审核报告的服务器不可用，则报表将不可用。

MBAM 高可用性的主要关注是 BitLocker 密钥恢复可用性。 如果帮助台无法提供恢复密钥，则被锁定的用户无法解锁其计算机。 若要避免此问题，请考虑实现冗余 web 服务器和数据库以确保高可用性。

有关 MBAM 可伸缩性和高可用性的详细信息，请参阅[MBAM 的可伸缩性白皮书](https://go.microsoft.com/fwlink/p/?LinkId=229025)（ https://go.microsoft.com/fwlink/p/?LinkId=229025) 。

有关 Microsoft SQL Server 的高可用性的一般指南，请参阅[高可用性](https://go.microsoft.com/fwlink/p/?LinkId=221504)（ https://go.microsoft.com/fwlink/p/?LinkId=221504) 。

有关 web 服务器可用性和可伸缩性的一般指南，请参阅[可用性和可伸缩性](https://go.microsoft.com/fwlink/p/?LinkId=221503)（ https://go.microsoft.com/fwlink/p/?LinkId=221503) 。

## 相关主题


[维护 MBAM 1.0](maintaining-mbam-10.md)

 

 





