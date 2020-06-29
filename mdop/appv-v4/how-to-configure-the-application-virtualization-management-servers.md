---
title: 如何配置 Application Virtualization Management Server
description: 如何配置 Application Virtualization Management Server
author: dansimp
ms.assetid: a9f96148-bf2d-486f-98c2-23409bfb0935
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d6d54dd213efb8d5cbff5d0e730e6dc08c8d19b1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801579"
---
# <span data-ttu-id="30b4a-103">如何配置 Application Virtualization Management Server</span><span class="sxs-lookup"><span data-stu-id="30b4a-103">How to Configure the Application Virtualization Management Servers</span></span>


<span data-ttu-id="30b4a-104">必须先配置应用程序虚拟化管理服务器，然后才能将虚拟化的应用程序流式传输到应用程序虚拟化桌面客户端或客户端以用于远程桌面服务（以前称为终端服务）。</span><span class="sxs-lookup"><span data-stu-id="30b4a-104">Before virtualized applications can be streamed to the Application Virtualization Desktop Client or the Client for Remote Desktop Services (formerly Terminal Services), the Application Virtualization Management Server must be configured.</span></span> <span data-ttu-id="30b4a-105">配置服务器时，将设置用于加载和存储 SFT 文件的*内容目录*。</span><span class="sxs-lookup"><span data-stu-id="30b4a-105">When you configure the server, you are setting up the *content directory* where the SFT files are loaded and stored.</span></span> <span data-ttu-id="30b4a-106">SFT 文件包含虚拟化的应用程序（或应用程序）。</span><span class="sxs-lookup"><span data-stu-id="30b4a-106">The SFT files contain the virtualized application (or applications).</span></span>

<span data-ttu-id="30b4a-107">**重要提示** 应用程序虚拟化服务器使用 RTSP 或 RTSPS 协议将 SFT 文件流式传输到桌面客户端和远程桌面服务客户端。</span><span class="sxs-lookup"><span data-stu-id="30b4a-107">**Important** Application Virtualization Servers stream SFT files to the Desktop Client and the Client for Remote Desktop Services using only RTSP or RTSPS protocols.</span></span> <span data-ttu-id="30b4a-108">.ICO （图标）文件和 OSD （开放软件描述符）文件可以配置为从其他文件或 HTTP 服务器流。</span><span class="sxs-lookup"><span data-stu-id="30b4a-108">The ICO (icon) file and the OSD (open software descriptor) file can be configured to stream from a different file or HTTP server.</span></span>

 

**<span data-ttu-id="30b4a-109">配置应用程序虚拟化管理服务器</span><span class="sxs-lookup"><span data-stu-id="30b4a-109">To configure the Application Virtualization Management Server</span></span>**

1.  <span data-ttu-id="30b4a-110">完成以下过程：</span><span class="sxs-lookup"><span data-stu-id="30b4a-110">Complete the following procedure:</span></span>

    [<span data-ttu-id="30b4a-111">如何安装 Application Virtualization Management Server</span><span class="sxs-lookup"><span data-stu-id="30b4a-111">How to Install Application Virtualization Management Server</span></span>](how-to-install-application-virtualization-management-server.md)

    <span data-ttu-id="30b4a-112">**注意** 在安装过程中，在 "**内容路径**" 屏幕上指定 \\Content 目录的位置。</span><span class="sxs-lookup"><span data-stu-id="30b4a-112">**Note** During the installation procedure, you specify the location of the \\Content directory on the **Content Path** screen.</span></span>

     

2.  <span data-ttu-id="30b4a-113">导航到为 \\Content 目录指定的位置，如有必要，请创建目录。</span><span class="sxs-lookup"><span data-stu-id="30b4a-113">Navigate to the location that you specified for the \\Content directory, and if necessary, create the directory.</span></span>

3.  <span data-ttu-id="30b4a-114">创建内容目录时，将此目录配置为标准文件共享。</span><span class="sxs-lookup"><span data-stu-id="30b4a-114">When the content directory is created, configure this directory as a standard file share.</span></span>

## <span data-ttu-id="30b4a-115">相关主题</span><span class="sxs-lookup"><span data-stu-id="30b4a-115">Related topics</span></span>


[<span data-ttu-id="30b4a-116">基于 Application Virtualization Server 的方案</span><span class="sxs-lookup"><span data-stu-id="30b4a-116">Application Virtualization Server-Based Scenario</span></span>](application-virtualization-server-based-scenario.md)

[<span data-ttu-id="30b4a-117">Application Virtualization System 要求</span><span class="sxs-lookup"><span data-stu-id="30b4a-117">Application Virtualization System Requirements</span></span>](application-virtualization-system-requirements.md)

[<span data-ttu-id="30b4a-118">基于电子软件分发的方案</span><span class="sxs-lookup"><span data-stu-id="30b4a-118">Electronic Software Distribution-Based Scenario</span></span>](electronic-software-distribution-based-scenario.md)

[<span data-ttu-id="30b4a-119">如何为基于服务器的部署配置服务器</span><span class="sxs-lookup"><span data-stu-id="30b4a-119">How to Configure Servers for Server-Based Deployment</span></span>](how-to-configure-servers-for-server-based-deployment.md)

 

 





