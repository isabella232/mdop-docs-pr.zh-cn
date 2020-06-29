---
title: 如何为 IIS 配置服务器
description: 如何为 IIS 配置服务器
author: dansimp
ms.assetid: 1fcfc583-322f-4a38-90d0-e64bfa9ee3d8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9fe3367698b6f387d4467afdad1b3e17211134d6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801539"
---
# <span data-ttu-id="1ecea-103">如何为 IIS 配置服务器</span><span class="sxs-lookup"><span data-stu-id="1ecea-103">How to Configure the Server for IIS</span></span>


<span data-ttu-id="1ecea-104">在将虚拟应用程序传输到应用程序虚拟化桌面客户端和远程桌面服务客户端（以前称为终端服务）之前，必须配置 IIS 服务器。</span><span class="sxs-lookup"><span data-stu-id="1ecea-104">Before virtual applications can be streamed to the Application Virtualization Desktop Client and the Client for Remote Desktop Services (formerly Terminal Services), the IIS servers must be configured.</span></span> <span data-ttu-id="1ecea-105">配置服务器时，将设置用于加载和存储 SFT 文件的内容目录。</span><span class="sxs-lookup"><span data-stu-id="1ecea-105">When you configure the servers, you are setting up the content directory where the SFT files are loaded and stored.</span></span> <span data-ttu-id="1ecea-106">SFT 文件包含虚拟应用程序（或应用程序）。</span><span class="sxs-lookup"><span data-stu-id="1ecea-106">The SFT files contain the virtual application (or applications).</span></span>

**<span data-ttu-id="1ecea-107">在 IIS 服务器上配置内容目录</span><span class="sxs-lookup"><span data-stu-id="1ecea-107">To configure the content directory on the IIS server</span></span>**

1.  <span data-ttu-id="1ecea-108">在运行 IIS 的服务器上，找到要用作内容目录的目录，或者创建不存在的目录。</span><span class="sxs-lookup"><span data-stu-id="1ecea-108">On the server that is running IIS, locate the directory that you want to use as the content directory, or create the directory if it does not exist.</span></span> <span data-ttu-id="1ecea-109">将此目录配置为标准文件共享。</span><span class="sxs-lookup"><span data-stu-id="1ecea-109">Configure this directory as a standard file share.</span></span>

2.  <span data-ttu-id="1ecea-110">在运行 IIS 的服务器上，打开**Iis 管理器**，然后在默认网站下创建一个与您在服务器上创建的内容目录相对应的虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="1ecea-110">On the server that is running IIS, open **IIS Manager**, and under the default website, create a virtual directory that corresponds to the content directory that you created on the server.</span></span> <span data-ttu-id="1ecea-111">请确保已选中 "**读取**"。</span><span class="sxs-lookup"><span data-stu-id="1ecea-111">Make sure that **Read** is checked.</span></span>

3.  <span data-ttu-id="1ecea-112">为新创建的虚拟目录提供别名**内容**。</span><span class="sxs-lookup"><span data-stu-id="1ecea-112">Give the newly created virtual directory the alias **Content**.</span></span>

4.  <span data-ttu-id="1ecea-113">接受此虚拟目录的所有其他默认设置。</span><span class="sxs-lookup"><span data-stu-id="1ecea-113">Accept all other default settings for this virtual directory.</span></span>

5.  <span data-ttu-id="1ecea-114">通过使用您之前定义的 Active Directory 域服务中的安全组，在内容目录下配置对内容目录和程序包文件夹的 NTFS 文件系统权限。</span><span class="sxs-lookup"><span data-stu-id="1ecea-114">Configure the NTFS file system permissions to the content directory and the package folders under the content directory by using the Security Groups in Active Directory Domain Services that you defined earlier.</span></span>

<span data-ttu-id="1ecea-115">**注意** 如果使用 IIS 发布 .ICO 和 OSD 文件，则必须为 OSD = TXT 配置 MIME 类型;否则，IIS 不会将 .ICO 和 OSD 文件提供给客户端。</span><span class="sxs-lookup"><span data-stu-id="1ecea-115">**Note** If you are using IIS to publish the ICO and OSD files, you must configure a MIME type for OSD=TXT; otherwise, IIS will not serve the ICO and OSD files to clients.</span></span> <span data-ttu-id="1ecea-116">如果使用 IIS 发布程序包（SFT 文件），则必须为 SFT = Binary 配置 MIME 类型;否则，IIS 不会将 SFT 文件提供给客户端。</span><span class="sxs-lookup"><span data-stu-id="1ecea-116">If you are using IIS to publish packages (SFT files), you must configure a MIME type for SFT=Binary; otherwise, IIS will not serve the SFT files to clients.</span></span>

 

## <span data-ttu-id="1ecea-117">相关主题</span><span class="sxs-lookup"><span data-stu-id="1ecea-117">Related topics</span></span>


[<span data-ttu-id="1ecea-118">基于 Application Virtualization Server 的方案</span><span class="sxs-lookup"><span data-stu-id="1ecea-118">Application Virtualization Server-Based Scenario</span></span>](application-virtualization-server-based-scenario.md)

[<span data-ttu-id="1ecea-119">基于电子软件分发的方案</span><span class="sxs-lookup"><span data-stu-id="1ecea-119">Electronic Software Distribution-Based Scenario</span></span>](electronic-software-distribution-based-scenario.md)

[<span data-ttu-id="1ecea-120">如何配置 Application Virtualization Management Server</span><span class="sxs-lookup"><span data-stu-id="1ecea-120">How to Configure the Application Virtualization Management Servers</span></span>](how-to-configure-the-application-virtualization-management-servers.md)

[<span data-ttu-id="1ecea-121">如何配置 Application Virtualization Streaming Server</span><span class="sxs-lookup"><span data-stu-id="1ecea-121">How to Configure the Application Virtualization Streaming Servers</span></span>](how-to-configure-the-application-virtualization-streaming-servers.md)

[<span data-ttu-id="1ecea-122">如何配置文件服务器</span><span class="sxs-lookup"><span data-stu-id="1ecea-122">How to Configure the File Server</span></span>](how-to-configure-the-file-server.md)

 

 





