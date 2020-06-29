---
title: 如何安装和配置 App-V Management Console 以实现更安全的环境
description: 如何安装和配置 App-V Management Console 以实现更安全的环境
author: dansimp
ms.assetid: 9d89ef09-cdbf-48fc-99da-b24fc987ef8f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9887787d1e203410b5517439d897260305d7526e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801391"
---
# <span data-ttu-id="3a131-103">如何安装和配置 App-V Management Console 以实现更安全的环境</span><span class="sxs-lookup"><span data-stu-id="3a131-103">How to Install and Configure the App-V Management Console for a More Secure Environment</span></span>


<span data-ttu-id="3a131-104">App-v 管理控制台的默认安装包括对安全通信的支持。</span><span class="sxs-lookup"><span data-stu-id="3a131-104">The default installation of the App-V Management Console includes support for secure communications.</span></span> <span data-ttu-id="3a131-105">当控制台首次启动时或连接到其他 App-v Web 管理服务时，将在每个连接的基础上配置每个管理控制台。</span><span class="sxs-lookup"><span data-stu-id="3a131-105">Each Management Console is configured on a per-connection basis when the console is started for the first time or when connecting to an additional App-V Web Management Service.</span></span> <span data-ttu-id="3a131-106">默认配置通过 TCP 端口443使用 SSL。</span><span class="sxs-lookup"><span data-stu-id="3a131-106">The default configuration uses SSL over TCP port 443.</span></span> <span data-ttu-id="3a131-107">如果在服务器上修改了端口号，则可以更改端口号。</span><span class="sxs-lookup"><span data-stu-id="3a131-107">You can change the port number if the port number was modified on the server.</span></span> <span data-ttu-id="3a131-108">你可以使用以下过程通过安全连接连接到 App-v Web 管理服务。</span><span class="sxs-lookup"><span data-stu-id="3a131-108">You can use the following procedure to connect to an App-V Web Management Service by using a secure connection.</span></span>

**<span data-ttu-id="3a131-109">如何使用 SSL 连接连接到 app-v 管理服务</span><span class="sxs-lookup"><span data-stu-id="3a131-109">How to Connect to an App-V Management Service by Using an SSL Connection</span></span>**

1.  <span data-ttu-id="3a131-110">启动应用程序虚拟化管理控制台。</span><span class="sxs-lookup"><span data-stu-id="3a131-110">Start the Application Virtualization Management Console.</span></span>

2.  <span data-ttu-id="3a131-111">在控制台的 "操作" 窗格中，单击 "**配置连接**"。</span><span class="sxs-lookup"><span data-stu-id="3a131-111">Click **Configure Connection** in the actions pane of the console.</span></span>

3.  <span data-ttu-id="3a131-112">键入**Web 服务主机名**，确保选中 "**使用安全连接**"。</span><span class="sxs-lookup"><span data-stu-id="3a131-112">Type the **Web Service Host Name**, and ensure that **Use Secure Connection** is selected.</span></span>

    <span data-ttu-id="3a131-113">**重要提示** Web 服务主机名称中提供的名称必须与证书上的公用名称相匹配，否则连接将失败。</span><span class="sxs-lookup"><span data-stu-id="3a131-113">**Important** The name provided in the Web Service Host Name must match the common name on the certificate, or the connection will fail.</span></span>

     

4.  <span data-ttu-id="3a131-114">选择相应的登录凭据，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="3a131-114">Select the appropriate login credentials, and click **OK**.</span></span>

## <span data-ttu-id="3a131-115">相关主题</span><span class="sxs-lookup"><span data-stu-id="3a131-115">Related topics</span></span>


[<span data-ttu-id="3a131-116">配置证书以支持 App-V Web Management Service</span><span class="sxs-lookup"><span data-stu-id="3a131-116">Configuring Certificates to Support the App-V Web Management Service</span></span>](configuring-certificates-to-support-the-app-v-web-management-service.md)

 

 





