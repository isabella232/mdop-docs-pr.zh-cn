---
title: 如何配置 Application Virtualization Streaming Server
description: 如何配置 Application Virtualization Streaming Server
author: dansimp
ms.assetid: 3e2dde35-9d72-40ba-9fdf-d0338bd4d561
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a0ec5497b010d18bcba60e81e96cbe6334c27fb8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801571"
---
# <span data-ttu-id="b66b1-103">如何配置 Application Virtualization Streaming Server</span><span class="sxs-lookup"><span data-stu-id="b66b1-103">How to Configure the Application Virtualization Streaming Servers</span></span>


<span data-ttu-id="b66b1-104">在将虚拟应用程序流式传输到应用程序虚拟化桌面客户端或远程桌面服务客户端（以前称为终端服务）之前，必须配置应用程序虚拟化流服务器。</span><span class="sxs-lookup"><span data-stu-id="b66b1-104">Before virtual applications can be streamed to the Application Virtualization Desktop Client or the Client for Remote Desktop Services (formerly Terminal Services), the Application Virtualization Streaming Servers must be configured.</span></span> <span data-ttu-id="b66b1-105">配置服务器时，将设置用于加载和存储 SFT 文件的*内容目录*。</span><span class="sxs-lookup"><span data-stu-id="b66b1-105">When you configure the servers, you are setting up the *content directory* where the SFT files are loaded and stored.</span></span> <span data-ttu-id="b66b1-106">SFT 文件包含虚拟应用程序（或应用程序）。</span><span class="sxs-lookup"><span data-stu-id="b66b1-106">The SFT files contain the virtual application (or applications).</span></span>

<span data-ttu-id="b66b1-107">**重要提示** 应用程序虚拟化服务器使用 RTSP 或 RTSPS 协议将 SFT 文件流式传输到桌面客户端和远程桌面服务客户端。</span><span class="sxs-lookup"><span data-stu-id="b66b1-107">**Important** Application Virtualization Servers stream SFT files to the Desktop Client and the Client for Remote Desktop Services using only RTSP or RTSPS protocols.</span></span> <span data-ttu-id="b66b1-108">.ICO （图标）文件和 OSD （开放软件描述符）文件可以配置为从其他文件或 HTTP 服务器流。</span><span class="sxs-lookup"><span data-stu-id="b66b1-108">The ICO (icon) file and the OSD (open software descriptor) file can be configured to stream from a different file or HTTP server.</span></span>

 

**<span data-ttu-id="b66b1-109">配置应用程序虚拟化流服务器</span><span class="sxs-lookup"><span data-stu-id="b66b1-109">To configure the Application Virtualization Streaming Servers</span></span>**

1.  <span data-ttu-id="b66b1-110">完成应用程序虚拟化流服务器的安装过程。</span><span class="sxs-lookup"><span data-stu-id="b66b1-110">Complete the installation procedure for the Application Virtualization Streaming Server.</span></span> <span data-ttu-id="b66b1-111">在安装过程中，在 "**内容路径**" 屏幕上指定 \\Content 目录的位置。</span><span class="sxs-lookup"><span data-stu-id="b66b1-111">During the installation procedure, you specify the location of the \\Content directory on the **Content Path** screen.</span></span>

2.  <span data-ttu-id="b66b1-112">导航到你为 \\Content 目录指定的位置，如果需要，请创建目录。</span><span class="sxs-lookup"><span data-stu-id="b66b1-112">Navigate to the location that you specified for the \\Content directory, and if you have to, create the directory.</span></span>

3.  <span data-ttu-id="b66b1-113">创建内容目录时，将此目录配置为标准文件共享。</span><span class="sxs-lookup"><span data-stu-id="b66b1-113">When the Content directory is created, configure this directory as a standard file share.</span></span>

4.  <span data-ttu-id="b66b1-114">将 NTFS 文件系统权限配置为内容目录和内容目录下的程序包文件夹。</span><span class="sxs-lookup"><span data-stu-id="b66b1-114">Configure the NTFS file system permissions to the Content directory and the package folders under the Content directory.</span></span> <span data-ttu-id="b66b1-115">应使用 Active Directory 域服务中的安全组定义哪些用户可以访问每个应用程序。</span><span class="sxs-lookup"><span data-stu-id="b66b1-115">You should use Security Groups in Active Directory Domain Services that define which users can access each application.</span></span>

## <span data-ttu-id="b66b1-116">相关主题</span><span class="sxs-lookup"><span data-stu-id="b66b1-116">Related topics</span></span>


[<span data-ttu-id="b66b1-117">基于 Application Virtualization Server 的方案</span><span class="sxs-lookup"><span data-stu-id="b66b1-117">Application Virtualization Server-Based Scenario</span></span>](application-virtualization-server-based-scenario.md)

[<span data-ttu-id="b66b1-118">基于电子软件分发的方案</span><span class="sxs-lookup"><span data-stu-id="b66b1-118">Electronic Software Distribution-Based Scenario</span></span>](electronic-software-distribution-based-scenario.md)

[<span data-ttu-id="b66b1-119">如何配置 Application Virtualization Management Server</span><span class="sxs-lookup"><span data-stu-id="b66b1-119">How to Configure the Application Virtualization Management Servers</span></span>](how-to-configure-the-application-virtualization-management-servers.md)

[<span data-ttu-id="b66b1-120">如何配置文件服务器</span><span class="sxs-lookup"><span data-stu-id="b66b1-120">How to Configure the File Server</span></span>](how-to-configure-the-file-server.md)

[<span data-ttu-id="b66b1-121">如何为 IIS 配置服务器</span><span class="sxs-lookup"><span data-stu-id="b66b1-121">How to Configure the Server for IIS</span></span>](how-to-configure-the-server-for-iis.md)

 

 





