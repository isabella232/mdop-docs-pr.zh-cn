---
title: 关于用户体验虚拟化 1.0
description: 关于用户体验虚拟化 1.0
author: dansimp
ms.assetid: 3758b100-35a8-4e10-ac08-f583fb8ddbd9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6010f9c4ebc260eec0324fb880dc2c92fd675130
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803223"
---
# 关于用户体验虚拟化 1.0


Microsoft 用户体验虚拟化（UE-V）监视用户对应用程序设置和 Windows 操作系统设置所做的更改。 将捕获用户设置并将其集中到设置存储位置。 然后，这些设置可应用于用户访问的不同计算机，包括桌面计算机、便携式计算机和虚拟桌面基础结构（VDI）会话。

用户体验虚拟化使用设置位置模板指定监视和集中的用户计算机上的应用程序和 Windows 设置。 设置位置模板是一个 XML 文件，用于指定与每个应用程序或操作系统设置相关联的文件和注册表位置。 该模板不包含设置的值;它仅包含要监视的设置的位置。

当用户在其计算机上工作时，由 UE-V 监视应用程序设置和 Windows 设置。 当用户关闭应用程序时，应用程序设置的值存储在设置存储服务器上。 当用户注销、计算机处于锁定状态或从计算机远程断开连接时，将存储 Windows 设置的值。

管理员可以创建 UE-V 设置位置模板来指定将漫游的企业应用程序设置。 UE-V 包含一组针对某些 Microsoft 应用程序和 Windows 设置的设置位置模板。 有关 UE-V 中的默认应用程序和设置的列表，请参阅[规划要与 ue-v 1.0 同步的应用程序](planning-which-applications-to-synchronize-with-ue-v-10.md)。

## UEV 1.0 发行说明


有关详细信息，以及未使其进入文档的最新消息，请参阅[Microsoft 用户体验虚拟化（ue-v）1.0 发行说明](microsoft-user-experience-virtualization--ue-v--10-release-notes.md)。

## 相关主题


[用户体验虚拟化 1.0 入门](getting-started-with-user-experience-virtualization-10.md)

[Microsoft 用户体验虚拟化 (UE-V) 1.0](index.md)

[UE-V 1.0 的高级别体系结构](high-level-architecture-for-ue-v-10.md)

 

 





