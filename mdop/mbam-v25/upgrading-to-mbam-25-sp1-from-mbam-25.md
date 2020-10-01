---
title: 从 MBAM 2.5 升级到 MBAM 2.5 SP1
description: 从 MBAM 2.5 升级到 MBAM 2.5 SP1
author: dansimp
ms.assetid: ''
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 2/16/2018
ms.openlocfilehash: 330ded822dd9da96a1c33eabcb31d744044dc28e
ms.sourcegitcommit: ae34c5cb5e7979b472b257a4691142e493d5d6fe
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2020
ms.locfileid: "11091617"
---
# 从 MBAM 2.5 升级到 MBAM 2.5 SP1
本主题介绍将 Microsoft BitLocker 管理和监视 (MBAM) Server 2.5 和 MBAM 客户端从2.5 升级到 MBAM 2.5 SP1 的过程。

### 开始之前
#### 下载五月2019服务版本
[桌面优化包](https://www.microsoft.com/download/details.aspx?id=58345)

#### 下载2018年7月的服务版本
[桌面优化包](https://www.microsoft.com/download/details.aspx?id=57157)


#### 验证安装 documentaion
验证您是否拥有 MBAM 环境的当前文档，包括所有服务器名称、数据库名称、服务帐户及其密码。

### 升级步骤
#### 将 MBAM 数据库升级 (SQL Server 的步骤) 
1. 使用 MBAM 配置器;从 SQL server 中删除 "报表" 角色，或在其中托管 SSRS 数据库的任何位置。 这可能是同一个服务器或单独的服务器，具体取决于你的环境。
  > [!NOTE]
  > 您将看不到用于删除数据库的选项;这是预期的。  
2. 通过批量许可服务中心网站安装 2.5 SP1 (，从 MDOP-Microsoft 桌面优化包2015：  <https://www.microsoft.com/Licensing/servicecenter/default.aspx>
3. 目前不要配置 
4. 使用 MBAM 配置器;重新添加报表角色
5. 使用 MBAM 配置器;在 SQL Server 上重新添加 SQL 数据库角色
6. 最后，系统将警告你已经存在并不创建该 "你的"，但这是预期的
7. 此过程会将现有数据库更新为正在安装的当前版本。              

#### 升级 MBAM 服务器 (运行 MBAM 和 IIS 的步骤) 
1. 使用 MBAM 配置器;从 IIS 服务器中删除管理员和自助服务门户
2. 安装 MBAM 2.5 SP1
3. 目前不要配置  
4. 使用 MBAM 配置器;将 Admin 和自助服务门户重新添加到 IIS 服务器 
5. 打开提升的命令提示符，键入 " **IISRESET**"，然后按 Enter。
 
#### 升级 MBAM 客户端/终结点的步骤
1. 从客户端终结点卸载2.5 代理
2. 在客户端终结点上安装 2.5 SP1 代理
3. 将五月2019汇总客户端更新推送到运行 2.5 SP1 代理的客户端 
4. 在安装2019的 "汇总" 之前，无需卸载现有客户端。  
