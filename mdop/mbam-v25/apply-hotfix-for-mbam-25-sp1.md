---
title: 在 MBAM 2.5 SP1 上应用修补程序
description: 在 MBAM 2.5 SP1 上应用修补程序
ms.author: dansimp
author: dansimp
ms.assetid: ''
ms.reviewer: ''
manager: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 8/30/2018
ms.openlocfilehash: ea564d93a3eec6a46ec7d4c1be0f794abba9c93e
ms.sourcegitcommit: 8ecbf818a6ff2ddafd80b93614c01256484737ad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2020
ms.locfileid: "11014986"
---
# 在 MBAM 2.5 SP1 上应用修补程序
本主题介绍在 MBAM) Server 2.5 SP1 中应用用于 Microsoft BitLocker 管理和监视 (修补程序的过程

### 开始之前，请下载 Microsoft BitLocker 管理和监视 (的最新修复程序 MBAM) Server 2.5 SP1
[桌面优化包](https://www.microsoft.com/download/details.aspx?id=57157)

> [!NOTE]
> 有关修补程序版本的详细信息，请参阅 [MBAM 版本图](https://docs.microsoft.com/archive/blogs/dubaisec/mbam-version-chart)。

#### 为现有 MBAM 环境更新 MBAM 服务器的步骤 
1. 删除 MBAM 服务器功能 (通过打开 MBAM 服务器配置工具，然后选择 "删除功能") 来执行此操作。
2. 从 "控制面板" 中删除 MDOP MBAM |程序和功能。
3. 安装 MBAM 2.5 SP1 RTM 服务器组件。
4. 安装 lastest MBAM 2.5 SP1 累积修补程序。
5. 使用 MBAM 服务器配置器配置 MBAM 功能。

#### 安装新的 MBAM 2.5 SP1 server 修补程序的步骤
有关 [新的服务器安装](deploying-the-mbam-25-server-infrastructure.md)，请参阅文档。
