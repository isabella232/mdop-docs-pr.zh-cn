---
title: 如何加载文件和程序包
description: 如何加载文件和程序包
author: dansimp
ms.assetid: f86f5bf1-99a4-44d7-ae2f-e6049c482f68
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9427fd8089ec9c22d7d379b15ae94bf421ca2d44
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801336"
---
# <span data-ttu-id="7bd63-103">如何加载文件和程序包</span><span class="sxs-lookup"><span data-stu-id="7bd63-103">How to Load Files and Packages</span></span>


<span data-ttu-id="7bd63-104">你可以使用以下过程在应用程序虚拟化服务器上加载文件和程序包。</span><span class="sxs-lookup"><span data-stu-id="7bd63-104">You can use the following procedure to load files and packages on Application Virtualization Servers.</span></span>

<span data-ttu-id="7bd63-105">**注意** 在安装过程中，你在 "**内容路径**" 页面上指定了 \\Content 目录的位置。</span><span class="sxs-lookup"><span data-stu-id="7bd63-105">**Note** During the installation process, you specified the location of the \\Content directory on the **Content Path** page.</span></span> <span data-ttu-id="7bd63-106">在指向该目录的位置之前，应创建并将其配置为标准文件共享。</span><span class="sxs-lookup"><span data-stu-id="7bd63-106">This directory should be created and configured as a standard file share before you point to its location.</span></span>

 

**<span data-ttu-id="7bd63-107">加载文件和程序包</span><span class="sxs-lookup"><span data-stu-id="7bd63-107">To load files and packages</span></span>**

1.  <span data-ttu-id="7bd63-108">在要将应用程序流式传输到的计算机上，导航到您为 \\Content 目录指定的位置。</span><span class="sxs-lookup"><span data-stu-id="7bd63-108">On the computer from which you will stream applications, navigate to the location that you specified for the \\Content directory.</span></span> <span data-ttu-id="7bd63-109">如有必要，请创建目录并将其配置为标准文件共享。</span><span class="sxs-lookup"><span data-stu-id="7bd63-109">If necessary, create the directory and configure it as a standard file share.</span></span>

2.  <span data-ttu-id="7bd63-110">将虚拟应用程序和程序包的 SFT 文件移动到 \\Content 目录。</span><span class="sxs-lookup"><span data-stu-id="7bd63-110">Move the SFT files for the virtual applications and packages to the \\Content directory.</span></span> <span data-ttu-id="7bd63-111">若要使 SFT 文件保持井然有序并避免混淆，请将应用程序和程序包放在专用子文件夹中。</span><span class="sxs-lookup"><span data-stu-id="7bd63-111">To keep the SFT files organized and to avoid confusion, put applications and packages in dedicated subfolders.</span></span>

3.  <span data-ttu-id="7bd63-112">根据你的方案和配置的要求加载应用程序和程序包，考虑以下情况：</span><span class="sxs-lookup"><span data-stu-id="7bd63-112">Load the applications and packages according to the requirements of your scenario and configuration, considering the following conditions:</span></span>

    -   <span data-ttu-id="7bd63-113">如果你的应用程序和程序包存储在应用程序虚拟化（App-v）管理服务器上，请通过管理控制台加载它们。</span><span class="sxs-lookup"><span data-stu-id="7bd63-113">If your applications and packages are stored on an Application Virtualization (App-V) Management Server, load them through the Management Console.</span></span> <span data-ttu-id="7bd63-114">有关详细信息，请参阅[如何加载或卸载应用程序](how-to-load-or-unload-an-application.md)或[如何从桌面通知区域加载虚拟应用程序](how-to-load-virtual-applications-from-the-desktop-notification-area.md)。</span><span class="sxs-lookup"><span data-stu-id="7bd63-114">For more information, see [How to Load or Unload an Application](how-to-load-or-unload-an-application.md) or [How to Load Virtual Applications from the Desktop Notification Area](how-to-load-virtual-applications-from-the-desktop-notification-area.md).</span></span>

    -   <span data-ttu-id="7bd63-115">如果你的应用程序存储在 app-v 流服务器、Web 服务器或配置为文件服务器的计算机上，则可以自动加载应用程序。</span><span class="sxs-lookup"><span data-stu-id="7bd63-115">If your applications are stored on an App-V Streaming Server, a Web server, or a computer configured as a file server, the applications can be automatically loaded.</span></span>

        <span data-ttu-id="7bd63-116">**注意** App-v 流处理服务器将自动轮询 \\Content 目录以查找应用程序和程序包，并将此信息放入内存以服务应用程序请求。</span><span class="sxs-lookup"><span data-stu-id="7bd63-116">**Note** The App-V Streaming Server automatically polls the \\Content directory for applications and packages and puts this information in RAM to service application requests.</span></span>

        <span data-ttu-id="7bd63-117">必须正确配置 app-v 客户端，才能从 Web 服务器和文件服务器检索应用程序和程序包。</span><span class="sxs-lookup"><span data-stu-id="7bd63-117">The App-V Clients must be properly configured to retrieve applications and packages from Web servers and file servers.</span></span> <span data-ttu-id="7bd63-118">有关详细信息，请参阅[如何为应用程序包检索配置客户端](how-to-configure-the-client-for-application-package-retrieval.md)。</span><span class="sxs-lookup"><span data-stu-id="7bd63-118">For more information, see [How to Configure the Client for Application Package Retrieval](how-to-configure-the-client-for-application-package-retrieval.md).</span></span>

         

## <span data-ttu-id="7bd63-119">相关主题</span><span class="sxs-lookup"><span data-stu-id="7bd63-119">Related topics</span></span>


[<span data-ttu-id="7bd63-120">Application Virtualization Server</span><span class="sxs-lookup"><span data-stu-id="7bd63-120">Application Virtualization Server</span></span>](application-virtualization-server.md)

 

 





