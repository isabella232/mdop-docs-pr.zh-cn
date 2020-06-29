---
title: 如何配置文件服务器
description: 如何配置文件服务器
author: dansimp
ms.assetid: 0977554c-1741-411b-85e7-7e1cd017542f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8a8971ad5c9f83dec4d0c77a16f1093ef7026b5c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801555"
---
# <span data-ttu-id="a1755-103">如何配置文件服务器</span><span class="sxs-lookup"><span data-stu-id="a1755-103">How to Configure the File Server</span></span>


<span data-ttu-id="a1755-104">你可以使用以下过程来配置本地计算机，该计算机用作文件共享并将应用程序流式处理到应用程序虚拟化桌面客户端和远程桌面服务（以前称为终端服务）客户端。</span><span class="sxs-lookup"><span data-stu-id="a1755-104">You can use the following procedure to configure a local computer that is used as a file share and streams applications to the Application Virtualization Desktop Client and the Client for Remote Desktop Services (formerly Terminal Services).</span></span> <span data-ttu-id="a1755-105">当你不希望向现有硬件环境添加其他服务器基础结构时，请使用此方案。</span><span class="sxs-lookup"><span data-stu-id="a1755-105">This scenario is used when you do not want to add an additional server infrastructure to your existing hardware environment.</span></span>

<span data-ttu-id="a1755-106">如果你使用应用程序虚拟化管理服务器作为本地办公室中安装的文件共享的分发点，则必须先配置此服务器，然后才能将虚拟应用程序流式传输到用作文件共享的计算机。</span><span class="sxs-lookup"><span data-stu-id="a1755-106">If you are using an Application Virtualization Management Server as a distribution point to the file share installed in local offices, you must configure this server before virtual applications can be streamed to the computers that are used as file shares.</span></span> <span data-ttu-id="a1755-107">配置服务器和文件共享时，您将设置用于加载和存储 SFT 文件的内容目录。</span><span class="sxs-lookup"><span data-stu-id="a1755-107">When you configure the servers and the file shares, you are setting up the content directory where the SFT files are loaded and stored.</span></span> <span data-ttu-id="a1755-108">SFT 文件包含虚拟应用程序（或应用程序）。</span><span class="sxs-lookup"><span data-stu-id="a1755-108">The SFT files contain the virtual application (or applications).</span></span>

<span data-ttu-id="a1755-109">**重要提示** 要使应用程序能够正确地流处理到应用程序虚拟化桌面客户端和客户端以进行远程桌面服务，从存储虚拟应用程序的服务器上的内容目录中的 SFT 文件流;.ICO （图标）文件和 OSD （开放软件描述符）文件可以配置为从其他服务器流。</span><span class="sxs-lookup"><span data-stu-id="a1755-109">**Important** For applications to stream properly to the Application Virtualization Desktop Client and the Client for Remote Desktop Services, the SFT file streams from the content directory on the server where you store the virtual application; the ICO (icon) file and the OSD (open software descriptor) file can be configured to stream from a different server.</span></span>

 

**<span data-ttu-id="a1755-110">配置应用程序虚拟化文件服务器</span><span class="sxs-lookup"><span data-stu-id="a1755-110">To configure the Application Virtualization file server</span></span>**

1.  <span data-ttu-id="a1755-111">完成以下安装过程以配置用作分发点的服务器：</span><span class="sxs-lookup"><span data-stu-id="a1755-111">Complete the following installation procedure to configure the server that is used as the distribution point:</span></span>

    [<span data-ttu-id="a1755-112">如何安装 Application Virtualization Management Server</span><span class="sxs-lookup"><span data-stu-id="a1755-112">How to Install Application Virtualization Management Server</span></span>](how-to-install-application-virtualization-management-server.md)

    <span data-ttu-id="a1755-113">**注意** 在安装过程中，在 "**内容路径**" 屏幕上指定 \\Content 目录的位置。</span><span class="sxs-lookup"><span data-stu-id="a1755-113">**Note** During the installation procedure, you specify the location of the \\Content directory on the **Content Path** screen.</span></span>

     

2.  <span data-ttu-id="a1755-114">创建 \\Content 目录，该目录对应于你在用作文件共享的每台计算机上安装服务器时指定的目录。</span><span class="sxs-lookup"><span data-stu-id="a1755-114">Create a \\Content directory, which corresponds to the directory you specified when you installed the server, on each computer that you are using as a file share.</span></span>

    <span data-ttu-id="a1755-115">**重要提示** 将应用程序虚拟化桌面客户端配置为将应用程序从你用作文件共享的计算机流出，而不是从应用程序虚拟化服务器或 IIS 服务器流出。</span><span class="sxs-lookup"><span data-stu-id="a1755-115">**Important** Configure the Application Virtualization Desktop Clients to stream applications from the computer you are using as a file share rather than from an Application Virtualization Server or IIS server.</span></span>

     

3.  <span data-ttu-id="a1755-116">创建 \\Content 目录时，将此目录配置为标准文件共享。</span><span class="sxs-lookup"><span data-stu-id="a1755-116">When the \\Content directory is created, configure this directory as a standard file share.</span></span>

## <span data-ttu-id="a1755-117">相关主题</span><span class="sxs-lookup"><span data-stu-id="a1755-117">Related topics</span></span>


[<span data-ttu-id="a1755-118">基于 Application Virtualization Server 的方案</span><span class="sxs-lookup"><span data-stu-id="a1755-118">Application Virtualization Server-Based Scenario</span></span>](application-virtualization-server-based-scenario.md)

[<span data-ttu-id="a1755-119">基于电子软件分发的方案</span><span class="sxs-lookup"><span data-stu-id="a1755-119">Electronic Software Distribution-Based Scenario</span></span>](electronic-software-distribution-based-scenario.md)

[<span data-ttu-id="a1755-120">如何配置 Application Virtualization Management Server</span><span class="sxs-lookup"><span data-stu-id="a1755-120">How to Configure the Application Virtualization Management Servers</span></span>](how-to-configure-the-application-virtualization-management-servers.md)

[<span data-ttu-id="a1755-121">如何配置 Application Virtualization Streaming Server</span><span class="sxs-lookup"><span data-stu-id="a1755-121">How to Configure the Application Virtualization Streaming Servers</span></span>](how-to-configure-the-application-virtualization-streaming-servers.md)

[<span data-ttu-id="a1755-122">如何为 IIS 配置服务器</span><span class="sxs-lookup"><span data-stu-id="a1755-122">How to Configure the Server for IIS</span></span>](how-to-configure-the-server-for-iis.md)

 

 





