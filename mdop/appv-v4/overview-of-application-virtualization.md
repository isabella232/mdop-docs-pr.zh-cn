---
title: Application Virtualization 概述
description: Application Virtualization 概述
author: dansimp
ms.assetid: 80545ef4-cf4c-420c-88d6-48e9f226051f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2f3719a817137edfd76b1b972e966c685581c58e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798896"
---
# <span data-ttu-id="36399-103">Application Virtualization 概述</span><span class="sxs-lookup"><span data-stu-id="36399-103">Overview of Application Virtualization</span></span>


<span data-ttu-id="36399-104">Microsoft Application Virtualization （App-v）可使应用程序可用于最终用户计算机，而无需直接在这些计算机上安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="36399-104">Microsoft Application Virtualization (App-V) can make applications available to end user computers without having to install the applications directly on those computers.</span></span> <span data-ttu-id="36399-105">这可通过一个称为*应用程序顺序的*进程来实现，这使每个应用程序都可以在客户端计算机上其自己的自包含虚拟环境中运行。</span><span class="sxs-lookup"><span data-stu-id="36399-105">This is made possible through a process known as *sequencing the application*, which enables each application to run in its own self-contained virtual environment on the client computer.</span></span> <span data-ttu-id="36399-106">序列化的应用程序相互隔离。</span><span class="sxs-lookup"><span data-stu-id="36399-106">The sequenced applications are isolated from each other.</span></span> <span data-ttu-id="36399-107">这消除了应用程序冲突，但应用程序仍可以与客户端计算机交互。</span><span class="sxs-lookup"><span data-stu-id="36399-107">This eliminates application conflicts, but the applications can still interact with the client computer.</span></span>

<span data-ttu-id="36399-108">App-v 客户端是允许最终用户在将应用程序发布到计算机之后与这些应用程序交互的功能。</span><span class="sxs-lookup"><span data-stu-id="36399-108">The App-V client is the feature that lets the end user interact with the applications after they have been published to the computer.</span></span> <span data-ttu-id="36399-109">客户端管理虚拟化应用程序在每台计算机上运行的虚拟环境。</span><span class="sxs-lookup"><span data-stu-id="36399-109">The client manages the virtual environment in which the virtualized applications run on each computer.</span></span> <span data-ttu-id="36399-110">在计算机上安装了客户端后，必须通过称为 "*发布*" 的进程将应用程序提供给计算机，这使最终用户能够运行虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="36399-110">After the client has been installed on a computer, the applications must be made available to the computer through a process known as *publishing*, which enables the end user to run the virtual applications.</span></span> <span data-ttu-id="36399-111">发布过程会将虚拟应用程序图标和快捷方式复制到计算机（通常位于 Windows 桌面或 "**开始**" 菜单上），并且还会将程序包定义和文件类型关联信息复制到计算机。</span><span class="sxs-lookup"><span data-stu-id="36399-111">The publishing process copies the virtual application icons and shortcuts to the computer—typically on the Windows desktop or on the **Start** menu—and also copies the package definition and file type association information to the computer.</span></span> <span data-ttu-id="36399-112">发布还使应用程序包内容可供最终用户的计算机使用。</span><span class="sxs-lookup"><span data-stu-id="36399-112">Publishing also makes the application package content available to the end user’s computer.</span></span>

<span data-ttu-id="36399-113">虚拟应用程序包内容可以复制到一个或多个应用程序虚拟服务器上，以便可以按需将其传输到客户端并在本地缓存。</span><span class="sxs-lookup"><span data-stu-id="36399-113">The virtual application package content can be copied onto one or more Application Virtualization servers so that it can be streamed down to the clients on demand and cached locally.</span></span> <span data-ttu-id="36399-114">文件服务器和 Web 服务器也可以用作流服务器，或者可以将内容直接复制到最终用户的计算机上，例如，如果你使用的是电子软件分发系统（如 Microsoft 终结点配置管理器）。</span><span class="sxs-lookup"><span data-stu-id="36399-114">File servers and Web servers can also be used as streaming servers, or the content can be copied directly to the end user’s computer—for example, if you are using an electronic software distribution system, such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="36399-115">在多服务器实现中，在所有流式处理服务器上维护程序包内容并使其保持最新状态需要全面的程序包管理解决方案。</span><span class="sxs-lookup"><span data-stu-id="36399-115">In a multi-server implementation, maintaining the package content and keeping it up to date on all the streaming servers requires a comprehensive package management solution.</span></span> <span data-ttu-id="36399-116">根据组织的规模，可能需要为全球各地的最终用户提供许多虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="36399-116">Depending on the size of your organization, you might need to have many virtual applications available to end users located all over the world.</span></span> <span data-ttu-id="36399-117">管理程序包以确保所有用户在需要访问这些程序包时都可以使用相应的应用程序，因此这是一个重要的要求。</span><span class="sxs-lookup"><span data-stu-id="36399-117">Managing the packages to ensure that the appropriate applications are available to all users where and when they need access to them is therefore an important requirement.</span></span>

## <span data-ttu-id="36399-118">Microsoft Application Virtualization 系统功能</span><span class="sxs-lookup"><span data-stu-id="36399-118">Microsoft Application Virtualization System Features</span></span>


<span data-ttu-id="36399-119">下表介绍了 Microsoft Application Virtualization 管理系统的主要功能。</span><span class="sxs-lookup"><span data-stu-id="36399-119">The following table describes the primary features of the Microsoft Application Virtualization Management System.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="36399-120">功能</span><span class="sxs-lookup"><span data-stu-id="36399-120">Feature</span></span></th>
<th align="left"><span data-ttu-id="36399-121">函数</span><span class="sxs-lookup"><span data-stu-id="36399-121">Function</span></span></th>
<th align="left"><span data-ttu-id="36399-122">其他信息</span><span class="sxs-lookup"><span data-stu-id="36399-122">Additional Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="36399-123">Microsoft Application Virtualization 管理服务器</span><span class="sxs-lookup"><span data-stu-id="36399-123">Microsoft Application Virtualization Management Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="36399-124">负责对程序包内容进行流式处理，并将快捷方式和文件类型关联发布到应用程序虚拟化客户端。</span><span class="sxs-lookup"><span data-stu-id="36399-124">Responsible for streaming the package content and publishing the shortcuts and file type associations to the Application Virtualization client.</span></span></p></td>
<td align="left"><p><span data-ttu-id="36399-125">应用程序虚拟化管理服务器支持活动升级、许可证管理和可用于报告的数据库。</span><span class="sxs-lookup"><span data-stu-id="36399-125">The Application Virtualization Management Server supports active upgrade, License Management, and a database that can be used for reporting.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="36399-126">内容 </strong> 文件夹</span><span class="sxs-lookup"><span data-stu-id="36399-126">Content</strong> folder</span></span></p></td>
<td align="left"><p><span data-ttu-id="36399-127">指示用于流式处理的应用程序虚拟化程序包的位置。</span><span class="sxs-lookup"><span data-stu-id="36399-127">Indicates the location of the Application Virtualization packages for streaming.</span></span></p></td>
<td align="left"><p><span data-ttu-id="36399-128">此文件夹可以位于应用程序虚拟化管理服务器上的共享位置。</span><span class="sxs-lookup"><span data-stu-id="36399-128">This folder can be located on a share on or off the Application Virtualization Management Server.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="36399-129">Microsoft Application Virtualization 管理控制台</span><span class="sxs-lookup"><span data-stu-id="36399-129">Microsoft Application Virtualization Management Console</span></span></p></td>
<td align="left"><p><span data-ttu-id="36399-130">此控制台是用于 Microsoft Application Virtualization 服务器管理的 MMC 3.0 管理单元管理工具。</span><span class="sxs-lookup"><span data-stu-id="36399-130">This console is an MMC 3.0 snap-in management tool used for Microsoft Application Virtualization Server administration.</span></span></p></td>
<td align="left"><p><span data-ttu-id="36399-131">此工具可以安装在 Microsoft Application Virtualization 服务器上，也可以位于具有 Microsoft 管理控制台（MMC）3.0 和 Microsoft 的单独工作站上。已安装 NETFramework 2.0。</span><span class="sxs-lookup"><span data-stu-id="36399-131">This tool can be installed on the Microsoft Application Virtualization server or located on a separate workstation that has Microsoft Management Console (MMC)3.0 and Microsoft .NETFramework 2.0 installed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="36399-132">Microsoft Application Virtualization 管理 Web 服务</span><span class="sxs-lookup"><span data-stu-id="36399-132">Microsoft Application Virtualization Management Web Service</span></span></p></td>
<td align="left"><p><span data-ttu-id="36399-133">负责将任何读取和写入请求传递到应用程序虚拟化数据存储。</span><span class="sxs-lookup"><span data-stu-id="36399-133">Responsible for communicating any read and write requests to the Application Virtualization data store.</span></span></p></td>
<td align="left"><p><span data-ttu-id="36399-134">管理 Web 服务可以安装在 Microsoft Application Virtualization 管理服务器上，也可以安装在安装了 Microsoft Internet information Services （IIS）的单独计算机上。</span><span class="sxs-lookup"><span data-stu-id="36399-134">The Management Web Service can be installed on the Microsoft Application Virtualization Management server or on a separate computer that has Microsoft Internet Information Services (IIS) installed.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="36399-135">Microsoft Application Virtualization 数据存储</span><span class="sxs-lookup"><span data-stu-id="36399-135">Microsoft Application Virtualization Data Store</span></span></p></td>
<td align="left"><p><span data-ttu-id="36399-136">App-v SQL Server 数据库，负责存储与应用程序虚拟化基础结构相关的所有信息。</span><span class="sxs-lookup"><span data-stu-id="36399-136">The App-V SQL Server database responsible for storing all information related to the Application Virtualization infrastructure.</span></span></p></td>
<td align="left"><p><span data-ttu-id="36399-137">此信息包括所有应用程序记录、应用程序分配以及哪些组负责管理应用程序虚拟化环境。</span><span class="sxs-lookup"><span data-stu-id="36399-137">This information includes all application records, application assignments, and which groups have responsibility for managing the Application Virtualization environment.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="36399-138">Microsoft Application Virtualization 流服务器</span><span class="sxs-lookup"><span data-stu-id="36399-138">Microsoft Application Virtualization Streaming Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="36399-139">负责托管应用程序虚拟化程序包，用于向分支机构中的客户端进行流处理，其中返回到应用程序虚拟化管理服务器的链接被视为广域网络（WAN）连接。</span><span class="sxs-lookup"><span data-stu-id="36399-139">Responsible for hosting the Application Virtualization packages for streaming to clients in a branch office, where the link back to the Application Virtualization Management Server is considered a wide area networks (WAN) connection.</span></span></p></td>
<td align="left"><p><span data-ttu-id="36399-140">此服务器仅包含流功能，并且既不提供应用程序虚拟化管理控制台，也不提供应用程序虚拟化管理 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="36399-140">This server contains streaming functionality only and provides neither the Application Virtualization Management Console nor the Application Virtualization Management Web Service.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="36399-141">Microsoft Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="36399-141">Microsoft Application Virtualization Sequencer</span></span></p></td>
<td align="left"><p><span data-ttu-id="36399-142">Sequencer 用于监视和捕获应用程序的安装以创建虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="36399-142">The sequencer is used to monitor and capture the installation of applications to create virtual application packages.</span></span></p></td>
<td align="left"><p><span data-ttu-id="36399-143">输出包含应用程序的图标、包含程序包定义信息的 .osd 文件、程序包清单文件和包含应用程序内容文件的 sft 文件。</span><span class="sxs-lookup"><span data-stu-id="36399-143">The output consists of the application’s icons, an .osd file that contains package definition information, a package manifest file, and the .sft file that contains the application program’s content files.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="36399-144">Microsoft Application Virtualization 客户端</span><span class="sxs-lookup"><span data-stu-id="36399-144">Microsoft Application Virtualization Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="36399-145">应用程序虚拟化桌面客户端和适用于远程桌面服务的应用程序虚拟化客户端为虚拟化应用程序提供和管理虚拟环境。</span><span class="sxs-lookup"><span data-stu-id="36399-145">The Application Virtualization Desktop Client and the Application Virtualization Client for Remote Desktop Services provide and manage the virtual environment for the virtualized applications.</span></span></p></td>
<td align="left"><p><span data-ttu-id="36399-146">Microsoft Application Virtualization 客户端将程序包流管理到缓存、发布刷新、传输以及与应用程序虚拟化服务器的所有交互。</span><span class="sxs-lookup"><span data-stu-id="36399-146">The Microsoft Application Virtualization client manages the package streaming into cache, publishing refresh, transport, and all interaction with the Application Virtualization servers.</span></span></p></td>
</tr>
</tbody>
</table>

 

 

 





