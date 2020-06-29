---
title: 为 App-V Server 配置防火墙
description: 为 App-V Server 配置防火墙
author: dansimp
ms.assetid: f779c450-6c6f-46a8-ac66-5e82e0689d55
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 92db727eb060546ab71f2c647f2d89b662be5c64
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803044"
---
# <span data-ttu-id="5141c-103">为 App-V Server 配置防火墙</span><span class="sxs-lookup"><span data-stu-id="5141c-103">Configuring the Firewall for the App-V Servers</span></span>


<span data-ttu-id="5141c-104">安装 Microsoft Application Virtualization （app-v）管理服务器或流服务器并将其配置为使用 RTSP 或 RTSPS 协议后，必须为 App-v 程序创建防火墙例外。</span><span class="sxs-lookup"><span data-stu-id="5141c-104">After you install the Microsoft Application Virtualization (App-V) Management Server or Streaming Server and configure it to use the RTSP or RTSPS protocol, you must create firewall exceptions for the App-V programs.</span></span>

## <span data-ttu-id="5141c-105">配置应用程序虚拟化管理服务器的防火墙例外</span><span class="sxs-lookup"><span data-stu-id="5141c-105">Configuring Firewall Exceptions for Application Virtualization Management Server</span></span>


<span data-ttu-id="5141c-106">为**sghwdsptr.exe**和**sghwsvr.exe**创建防火墙例外。</span><span class="sxs-lookup"><span data-stu-id="5141c-106">Create a firewall exception for **sghwdsptr.exe** and **sghwsvr.exe**.</span></span> <span data-ttu-id="5141c-107">这些程序位于32位操作系统上的 "C:\\program files Files\\Microsoft System Center App Virt 管理 Server\\App Virt 管理 Server\\bin" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="5141c-107">These programs are found in the folder C:\\Program Files\\Microsoft System Center App Virt Management Server\\App Virt Management Server\\bin on a 32-bit operating system.</span></span> <span data-ttu-id="5141c-108">如果您使用的是64位操作系统版本，则该文件夹位于 C:\\program files Files （x86）下 \\Microsoft System Center App Virt Management Server\\App Virt 管理 Server\\bin。</span><span class="sxs-lookup"><span data-stu-id="5141c-108">If you are using a 64-bit operating system version, the folder is located under C:\\Program Files (x86)\\Microsoft System Center App Virt Management Server\\App Virt Management Server\\bin.</span></span>

## <span data-ttu-id="5141c-109">配置应用程序虚拟化流服务器的防火墙例外</span><span class="sxs-lookup"><span data-stu-id="5141c-109">Configuring Firewall Exceptions for Application Virtualization Streaming Server</span></span>


<span data-ttu-id="5141c-110">为**sglwdsptr.exe**和**sglwsvr.exe**创建防火墙例外。</span><span class="sxs-lookup"><span data-stu-id="5141c-110">Create a firewall exception for **sglwdsptr.exe** and **sglwsvr.exe**.</span></span> <span data-ttu-id="5141c-111">在32位操作系统上 Virt 流 Server\\App Virt 流 Server\\bin 的文件夹 C:\\program files Files\\Microsoft System Center App 中可以找到这些程序。</span><span class="sxs-lookup"><span data-stu-id="5141c-111">These programs are found in the folder C:\\Program Files\\Microsoft System Center App Virt Streaming Server\\App Virt Streaming Server\\bin on a 32-bit operating system.</span></span> <span data-ttu-id="5141c-112">如果您使用的是64位操作系统版本，则该文件夹位于 C:\\program files Files （x86）下 \\Microsoft System Center App Virt 流 Server\\App Virt 流 Server\\bin。</span><span class="sxs-lookup"><span data-stu-id="5141c-112">If you are using a 64-bit operating system version, the folder is located under C:\\Program Files (x86)\\Microsoft System Center App Virt Streaming Server\\App Virt Streaming Server\\bin.</span></span>

## <span data-ttu-id="5141c-113">相关主题</span><span class="sxs-lookup"><span data-stu-id="5141c-113">Related topics</span></span>


[<span data-ttu-id="5141c-114">如何为基于服务器的部署配置服务器</span><span class="sxs-lookup"><span data-stu-id="5141c-114">How to Configure Servers for Server-Based Deployment</span></span>](how-to-configure-servers-for-server-based-deployment.md)

[<span data-ttu-id="5141c-115">如何安装和配置默认应用程序</span><span class="sxs-lookup"><span data-stu-id="5141c-115">How to Install and Configure the Default Application</span></span>](how-to-install-and-configure-the-default-application.md)

 

 





