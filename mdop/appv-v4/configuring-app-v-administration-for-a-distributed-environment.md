---
title: 针对分布式环境配置 App-V 管理
description: 针对分布式环境配置 App-V 管理
author: dansimp
ms.assetid: 53971fa9-8319-435c-be74-c37feb9af1da
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: c1a638d6afde9270859c8aa98fc9f421c39cfc72
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803063"
---
# 针对分布式环境配置 App-V 管理


为特定组织设计基础结构时，可以在安装了 app-v 管理服务器的计算机以外的计算机上安装 app-v 管理 Web 服务。 分离这些 App-v 组件的常见原因包括以下几项：

-   性能

-   可靠性

-   可用性

-   可伸缩性

通过分离管理服务器和管理 Web 服务，需要额外配置基础结构才能正常运行。 当你分离这两个功能，但未完成本主题中所述的过程时，管理控制台将连接到管理 Web 服务，但无法通过数据存储正确验证。 管理控制台将无法正常加载，管理员将无法完成任何管理任务。

之所以会出现此行为，是因为管理 Web 服务无法使用从管理控制台传递给它的凭据来访问数据存储。 解决方案是将管理 Web 服务服务器配置为 "受信任以供委派"。

## 配置 Active Directory 域服务


还需要配置正确的 Active Directory 域服务才能在分布式环境中工作。 本部分包含你需要配置 Active Directory 域服务的信息。

### SQL 服务使用本地系统帐户时

若要设置 SQL 服务使用本地系统帐户的环境，请将管理 Web 服务的计算机帐户的属性更改为 "受信任以供委派"。 有关如何执行此操作的详细过程，请参阅[如何将服务器配置为受信任的委派](how-to-configure-the-server-to-be-trusted-for-delegation.md)

### SQL 服务使用基于域的帐户时

若要设置 SQL Server 使用基于域的服务帐户的环境，您需要考虑是否应用各种因素，包括：

-   SQL Server 群集

-   复制

-   自动化任务

-   链接服务器

有关在 SQL 服务使用基于域的帐户时配置 Active Directory 域服务的信息，请参阅 <https://go.microsoft.com/fwlink/?LinkId=151968> 。

 

 





