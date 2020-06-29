---
title: 使用 Application Virtualization Server 作为程序包管理解决方案
description: 使用 Application Virtualization Server 作为程序包管理解决方案
author: dansimp
ms.assetid: 41597355-e7bb-45e2-b300-7b1724419975
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2b81ed3ab6fa3a70fe4780904059091f22579d9e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798708"
---
# 使用 Application Virtualization Server 作为程序包管理解决方案


如果您没有已有的 ESD 系统来部署应用程序虚拟化解决方案或不想使用其中一个，则需要安装一个或多个应用程序虚拟化管理服务器作为系统体系结构的核心。 应用程序虚拟化管理服务器需要专用的服务器计算机，并且需要 Microsoft SQL Server 数据库。 数据库可以位于同一服务器上，也可以在可通过高速 LAN 连接的应用程序虚拟化管理服务器访问的企业数据库服务器上配置。 此外，你需要在应用程序虚拟化管理服务器或指定的管理工作站上安装 Microsoft Application Virtualization 管理控制台，并且你将需要安装 Microsoft Application Virtualization Management Web 服务，该服务还可以安装在应用程序虚拟化管理服务器或单独的 IIS 服务器上。 应用程序虚拟化管理控制台用于连接到应用程序虚拟化管理 Web 服务，使系统管理员能够与应用程序虚拟化管理服务器交互。

**注意** 对应用程序的访问受 Active Directory 域服务中的安全组的控制，因此你需要规划一个过程来为每个虚拟化应用程序设置安全组，并管理每个组中添加的用户。 应用程序虚拟化管理服务器管理员将服务器配置为使用这些 Active Directory 组，然后服务器将根据 Active Directory 组成员身份自动控制对程序包的访问。

 

## 本部分内容


<a href="" id="overview-of-the-application-virtualization-system-components"></a>[Application Virtualization System 组件概述](overview-of-the-application-virtualization-system-components.md)  
列出并介绍 Microsoft Application Virtualization 管理系统的主要组件。

<a href="" id="publishing-virtual-applications-using-application-virtualization-management-servers"></a>[使用 Application Virtualization Management Server 发布虚拟应用程序](publishing-virtual-applications-using-application-virtualization-management-servers.md)  
提供有关如何在基于应用程序虚拟服务器的部署方案中发布虚拟应用程序的简要概述。

<a href="" id="planning-your-streaming-solution-in-an-application-virtualization-server-based-implementation"></a>[在基于 Application Virtualization Server 的实现中计划流式处理解决方案](planning-your-streaming-solution-in-an-application-virtualization-server-based-implementation.md)  
介绍将应用程序虚拟化流服务器与基于应用程序虚拟化管理服务器的实现结合使用的可用选项。

## 相关主题


[基于 Application Virtualization Server 的方案](application-virtualization-server-based-scenario.md)

[规划 Application Virtualization System 部署](planning-for-application-virtualization-system-deployment.md)

 

 





