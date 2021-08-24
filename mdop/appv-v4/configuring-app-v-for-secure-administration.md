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
ms.openlocfilehash: c95fab4b2b4f402df4ff0f82f2f346c9bd226e00
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910477"
---
# <a name="configuring-app-v-for-secure-administration"></a>配置 App-V 以实现安全管理


在保护管理操作非常重要的环境中，App-V 允许 App-V Web 管理服务与 App-V 管理控制台之间的安全通信。 由于管理服务是基于 Web 的应用程序，因此它要求保护承载管理服务的 Web 服务器上 App-V 管理服务器应用程序的安全。 如下图所示，此过程包括使用 HTTPS 进行通信，以及将 IIS 服务器配置为仅允许Windows身份验证。

![app-v Web 服务网络配置。](images/appvmgmtwebservice.gif)

App-V Web 管理服务作为基于 Web 的应用程序安装在 IIS 上。 若要使 Web 管理服务支持 App-V 管理控制台和 Web 管理服务之间的安全 (SSL) 连接，您需要配置安装 Web 管理服务的 IIS 服务器，并配置 App-V 管理控制台。

## <a name="in-this-section"></a>本部分内容


<a href="" id="configuring-certificates-to-support-the-app-v-web-management-service"></a>[配置证书以支持 App-V Web Management Service](configuring-certificates-to-support-the-app-v-web-management-service.md)  
提供有关配置证书以支持基于 SSL 的连接以帮助保护 App-V Web 管理服务通信安全的有用信息。

<a href="" id="how-to-install-and-configure-the-app-v-management-console-for-a-more-secure-environment"></a>[如何安装和配置 App-V Management Console 以实现更安全的环境](how-to-install-and-configure-the-app-v-management-console-for-a-more-secure-environment.md)  
提供使用安全连接连接到 App-V Web 管理服务的分步过程。

 

 





