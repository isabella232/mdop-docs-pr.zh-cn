---
title: 配置 App-V 以实现安全管理
description: 配置 App-V 以实现安全管理
author: dansimp
ms.assetid: 4543fa81-c8cc-4b10-83b7-060778eb1349
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: de70c1df734bbf1168fd7dacf9410d3451a8a3c2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803061"
---
# 配置 App-V 以实现安全管理


在安全管理操作很重要的环境中，app-v 允许在 App-v Web 管理服务和 App-v 管理控制台之间进行安全通信。 由于管理服务是基于 Web 的应用程序，因此它需要保护托管管理服务的 Web 服务器上的 app-v 管理服务器应用程序。 如下图所示，此过程包括使用 HTTPS 进行通信，并将 IIS 服务器配置为仅允许 Windows 集成身份验证。

![app-v web 服务网络配置](images/appvmgmtwebservice.gif)

App-v Web 管理服务在 IIS 上安装为基于 Web 的应用程序。 为了支持应用程序 V 管理控制台和 Web 管理服务之间的安全（SSL）连接，你需要配置安装 Web 管理服务的 IIS 服务器，并配置 App-v 管理控制台。

## 本部分内容


<a href="" id="configuring-certificates-to-support-the-app-v-web-management-service"></a>[配置证书以支持 App-V Web Management Service](configuring-certificates-to-support-the-app-v-web-management-service.md)  
提供有关配置证书以支持基于 SSL 的连接的有用信息，以帮助确保 App-v Web 管理服务的通信安全。

<a href="" id="how-to-install-and-configure-the-app-v-management-console-for-a-more-secure-environment"></a>[如何安装和配置 App-V Management Console 以实现更安全的环境](how-to-install-and-configure-the-app-v-management-console-for-a-more-secure-environment.md)  
提供有关使用安全连接连接到 App-v Web 管理服务的分步过程。

 

 





