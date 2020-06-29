---
title: 应用程序虚拟化系统的规划和部署指南
description: 应用程序虚拟化系统的规划和部署指南
author: dansimp
ms.assetid: 6c012e33-9ac6-4cd8-84ff-54f40973833f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 10bcac26fddae2f0e5826dbd7335adda06d3987e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798875"
---
# 应用程序虚拟化系统的规划和部署指南


Microsoft Application 虚拟化管理提供了使应用程序可供最终用户计算机使用的功能，而无需直接在这些计算机上安装应用程序。 这可通过一个称为*应用程序顺序的*进程来实现，这使每个应用程序都可以在客户端计算机上其自己的自包含虚拟环境中运行。 序列化的应用程序彼此隔离，消除了应用程序冲突，但仍可以与客户端计算机交互。

应用程序虚拟化客户端是应用程序虚拟化系统组件，使最终用户能够在应用程序发布到计算机后与应用程序交互。 客户端管理虚拟化应用程序在每台计算机上运行的虚拟环境。 在计算机上安装了客户端后，必须通过称为 "*发布*" 的进程将应用程序提供给计算机，这使最终用户能够运行虚拟应用程序。 发布过程会将计算机上的虚拟应用程序图标和快捷方式置于计算机上（通常在 Windows 桌面或 "**开始**" 菜单上），并且还会将程序包定义和文件类型关联信息放置在计算机上。 发布还使应用程序包内容可供最终用户的计算机使用。

虚拟应用程序包内容可以放置在一个或多个应用程序虚拟服务器上，以便可以按需将其传输到客户端并在本地缓存。 文件服务器和 Web 服务器也可以用作流服务器，或者内容可以直接放置在最终用户的计算机上，例如，如果您使用的是电子软件分发系统（如 Microsoft 终结点配置管理器）。 在多服务器实现中，在所有流式处理服务器上维护程序包内容并使其保持最新状态需要全面的程序包管理解决方案。 根据你的组织的规模，你可能需要拥有可供全球各地的最终用户访问的多个虚拟应用程序。 管理程序包以确保所有用户在需要访问这些应用程序的情况下以及他们需要访问这些应用程序时，它们都可以使用。

应用程序虚拟化规划和部署指南提供的信息可帮助你更好地了解和部署 Microsoft Application Virtualization 应用程序及其组件。 它还提供了实现密钥部署方案的分步过程。

## 本部分内容


<a href="" id="planning-for-application-virtualization-system-deployment"></a>[规划 Application Virtualization System 部署](planning-for-application-virtualization-system-deployment.md)  
提供规划应用程序虚拟化系统的实施和部署所需的指南。

<a href="" id="application-virtualization-deployment-and-upgrade-considerations"></a>[Application Virtualization 部署和升级注意事项](application-virtualization-deployment-and-upgrade-considerations.md)  
提供有关安装各种应用程序虚拟化组件的硬件和软件要求以及升级信息的信息。

<a href="" id="electronic-software-distribution-based-scenario"></a>[基于电子软件分发的方案](electronic-software-distribution-based-scenario.md)  
提供有关使用电子软件分发（ESD）系统部署应用程序虚拟化的信息。

<a href="" id="application-virtualization-server-based-scenario"></a>[基于 Application Virtualization Server 的方案](application-virtualization-server-based-scenario.md)  
提供有关使用应用程序虚拟化管理服务器部署应用程序虚拟化的信息。

<a href="" id="stand-alone-delivery-scenario-for-application-virtualization-clients"></a>[适用于 Application Virtualization Client 的独立传递方案](stand-alone-delivery-scenario-for-application-virtualization-clients.md)  
介绍如何在独立模式下部署应用程序虚拟化，而无需使用 ESD 或基于服务器的资源。

<a href="" id="application-virtualization-reference"></a>[Application Virtualization 参考](application-virtualization-reference.md)  
包含与安装和管理系统组件相关的详细技术参考资料。

 

 





