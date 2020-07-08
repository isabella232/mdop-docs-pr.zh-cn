---
title: 维护 MBAM 1.0
description: 维护 MBAM 1.0
author: dansimp
ms.assetid: 02ffb093-c364-4837-bbe8-23d4c09fbd3d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7eecef4e82680b08fde1b1bef88487a6fc156fe4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803835"
---
# 维护 MBAM 1.0


完成所有必要的计划，然后部署 Microsoft BitLocker 管理和监视（MBAM）后，你可以将 MBAM 配置为在使用它管理企业 BitLocker 加密操作时以高度可用的方式运行。 本部分中的信息介绍了 MBAM 的高可用性选项，以及如何在必要时移动 MBAM 服务器功能。

## MBAM 管理包


可从 Microsoft 下载中心下载 MBAM 的 MicrosoftSystemCenterOperationsManager 管理包。

此管理包监视服务器端基础结构中的关键交互，例如 web 服务和数据库之间的连接以及网站与其支持的 web 服务之间的操作调用。 它还会在桌面客户端和其各自的接收 web 服务终结点之间上载请求。

[Microsoft BitLocker 管理和监视管理包](https://go.microsoft.com/fwlink/p/?LinkId=258390)

## 确保 MBAM 1.0 的高可用性


MBAM 设计为具有容错能力。 如果服务器不可用，则用户不会受到负面影响。 本部分中的信息可用于配置高可用的 MBAM 安装。

[MBAM 1.0 的高可用性](high-availability-for-mbam-10.md)

## 将 MBAM 1.0 功能移动到另一台服务器


当需要将 MBAM 服务器功能从一台服务器计算机移动到另一台服务器时，应遵循特定的顺序和所需的步骤，以避免生产效率或数据丢失。 本节介绍将一个或多个 MBAM 服务器功能移动到另一台计算机时应采取的步骤。

[如何将 MBAM 1.0 功能移到另一台计算机](how-to-move-mbam-10-features-to-another-computer.md)

## 用于维护 MBAM 的其他资源


[MBAM 1.0 的操作](operations-for-mbam-10.md)

 

 





