---
title: 在 MBAM 2.5 SP1 上应用修补程序
description: 在 MBAM 2.5 SP1 上应用修补程序
ms.author: ppriya-msft
author: dansimp
ms.assetid: ''
ms.reviewer: ''
manager: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 8/30/2018
ms.openlocfilehash: 71f840ce4d57a0698289128f92b9d760ca14ddfc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803518"
---
# 在 MBAM 2.5 SP1 上应用修补程序
本主题介绍应用适用于 Microsoft BitLocker 管理和监视（MBAM） Server 2.5 SP1 的修补程序的过程

### 开始之前，请下载最新的 Microsoft BitLocker 管理和监视（MBAM） Server 2.5 SP1 的修复程序
[桌面优化包](https://www.microsoft.com/download/details.aspx?id=57157)

> [!NOTE]
> 有关修补程序版本的详细信息，请参阅[MBAM 版本图](https://docs.microsoft.com/archive/blogs/dubaisec/mbam-version-chart)。

#### 为现有 MBAM 环境更新 MBAM 服务器的步骤 
1. 删除 MBAM server 功能（通过打开 MBAM 服务器配置工具，然后选择 "删除功能" 执行此操作）。
2. 从 "控制面板" 中删除 MDOP MBAM |程序和功能。
3. 安装 MBAM 2.5 SP1 RTM 服务器组件。
4. 安装 lastest MBAM 2.5 SP1 累积修补程序。
5. 使用 MBAM 服务器配置器配置 MBAM 功能。

#### 安装新的 MBAM 2.5 SP1 server 修补程序的步骤
有关[新的服务器安装](deploying-the-mbam-25-server-infrastructure.md)，请参阅文档。
