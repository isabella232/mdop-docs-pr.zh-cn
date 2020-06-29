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
# <span data-ttu-id="74bea-103">配置 App-V 以实现安全管理</span><span class="sxs-lookup"><span data-stu-id="74bea-103">Configuring App-V for Secure Administration</span></span>


<span data-ttu-id="74bea-104">在安全管理操作很重要的环境中，app-v 允许在 App-v Web 管理服务和 App-v 管理控制台之间进行安全通信。</span><span class="sxs-lookup"><span data-stu-id="74bea-104">In an environment where securing administrative operations is important, App-V allows for secure communication between the App-V Web Management Service and the App-V Management Console.</span></span> <span data-ttu-id="74bea-105">由于管理服务是基于 Web 的应用程序，因此它需要保护托管管理服务的 Web 服务器上的 app-v 管理服务器应用程序。</span><span class="sxs-lookup"><span data-stu-id="74bea-105">Because the Management Service is a Web-based application, it requires securing the App-V Management Server application on the Web server that hosts the Management Service.</span></span> <span data-ttu-id="74bea-106">如下图所示，此过程包括使用 HTTPS 进行通信，并将 IIS 服务器配置为仅允许 Windows 集成身份验证。</span><span class="sxs-lookup"><span data-stu-id="74bea-106">As shown in the following illustration, this process includes using HTTPS for communication and configuring the IIS server to allow only Windows Integrated Authentication.</span></span>

![app-v web 服务网络配置](images/appvmgmtwebservice.gif)

<span data-ttu-id="74bea-108">App-v Web 管理服务在 IIS 上安装为基于 Web 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="74bea-108">The App-V Web Management Service is installed as a Web-based application on IIS.</span></span> <span data-ttu-id="74bea-109">为了支持应用程序 V 管理控制台和 Web 管理服务之间的安全（SSL）连接，你需要配置安装 Web 管理服务的 IIS 服务器，并配置 App-v 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="74bea-109">For the Web Management Service to support secure (SSL) connections between the App-V Management Console and the Web Management Service, you will need to configure the IIS server where the Web Management Service is installed and configure the App-V Management Console.</span></span>

## <span data-ttu-id="74bea-110">本部分内容</span><span class="sxs-lookup"><span data-stu-id="74bea-110">In This Section</span></span>


<a href="" id="configuring-certificates-to-support-the-app-v-web-management-service"></a>[<span data-ttu-id="74bea-111">配置证书以支持 App-V Web Management Service</span><span class="sxs-lookup"><span data-stu-id="74bea-111">Configuring Certificates to Support the App-V Web Management Service</span></span>](configuring-certificates-to-support-the-app-v-web-management-service.md)  
<span data-ttu-id="74bea-112">提供有关配置证书以支持基于 SSL 的连接的有用信息，以帮助确保 App-v Web 管理服务的通信安全。</span><span class="sxs-lookup"><span data-stu-id="74bea-112">Provides helpful information about configuring certificates to support SSL-based connections, to help secure communication for the App-V Web Management Service.</span></span>

<a href="" id="how-to-install-and-configure-the-app-v-management-console-for-a-more-secure-environment"></a>[<span data-ttu-id="74bea-113">如何安装和配置 App-V Management Console 以实现更安全的环境</span><span class="sxs-lookup"><span data-stu-id="74bea-113">How to Install and Configure the App-V Management Console for a More Secure Environment</span></span>](how-to-install-and-configure-the-app-v-management-console-for-a-more-secure-environment.md)  
<span data-ttu-id="74bea-114">提供有关使用安全连接连接到 App-v Web 管理服务的分步过程。</span><span class="sxs-lookup"><span data-stu-id="74bea-114">Provides a step-by-step procedure for connecting to an App-V Web Management Service by using a secure connection.</span></span>

 

 





