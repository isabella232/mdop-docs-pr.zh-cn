---
title: 高级别体系结构
description: 高级别体系结构
author: dansimp
ms.assetid: a78e12ad-5aa6-40e0-ae8b-51acaf005712
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 00df29c751653645ab4bee9762af57576a40092a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803921"
---
# <span data-ttu-id="036c8-103">高级别体系结构</span><span class="sxs-lookup"><span data-stu-id="036c8-103">High-Level Architecture</span></span>


<span data-ttu-id="036c8-104">MED-V 解决方案包含以下元素：</span><span class="sxs-lookup"><span data-stu-id="036c8-104">The MED-V solution comprises the following elements:</span></span>

-   <span data-ttu-id="036c8-105">**管理员定义的虚拟机**-封装了一个完整的桌面环境，包括操作系统、应用程序以及可选的管理和安全工具。</span><span class="sxs-lookup"><span data-stu-id="036c8-105">**Administrator-defined virtual machine**—Encapsulates a full desktop environment, including an operating system, applications, and optional management and security tools.</span></span>

-   <span data-ttu-id="036c8-106">**图像存储库**-通过 "修剪传输技术" 将所有虚拟图像存储在标准 IIS 服务器上，并支持虚拟图像版本管理、客户端验证的图像检索和高效下载（新映像或更新）。</span><span class="sxs-lookup"><span data-stu-id="036c8-106">**Image repository**—Stores all virtual images on a standard IIS server and enables virtual images version management, client-authenticated image retrieval, and efficient download (of a new image or updates) via Trim Transfer technology.</span></span>

-   <span data-ttu-id="036c8-107">**管理服务器**—将映像存储库中的虚拟图像和管理员使用策略关联到 Active Directory®用户或组。</span><span class="sxs-lookup"><span data-stu-id="036c8-107">**Management server**—Associates virtual images from the image repository along with administrator usage policies to Active Directory® users or groups.</span></span> <span data-ttu-id="036c8-108">管理服务器还会聚合客户端的事件，并将它们存储在外部数据库（Microsoft SQL Server®）中，用于监视和报告目的。</span><span class="sxs-lookup"><span data-stu-id="036c8-108">The management server also aggregates clients' events and stores them in an external database (Microsoft SQL Server®) for monitoring and reporting purposes.</span></span>

-   <span data-ttu-id="036c8-109">**管理控制台**-使管理员能够控制管理服务器和映像存储库。</span><span class="sxs-lookup"><span data-stu-id="036c8-109">**Management console**—Enables administrators to control the management server and the image repository.</span></span>

-   **<span data-ttu-id="036c8-110">最终用户客户端</span><span class="sxs-lookup"><span data-stu-id="036c8-110">End-user client</span></span>**

    1.  <span data-ttu-id="036c8-111">虚拟图像生命周期-身份验证、图像检索、使用策略的实施。</span><span class="sxs-lookup"><span data-stu-id="036c8-111">Virtual image life-cycle—Authentication, image retrieval, enforcement of usage policies.</span></span>

    2.  <span data-ttu-id="036c8-112">虚拟机会话管理-启动、停止、锁定虚拟机。</span><span class="sxs-lookup"><span data-stu-id="036c8-112">Virtual machine session management—Start, stop, lock the virtual machine.</span></span>

    3.  <span data-ttu-id="036c8-113">单一桌面体验-通过标准的桌面 "开始" 菜单并与用户桌面上的其他应用程序集成，在虚拟机中安装的应用程序无缝提供。</span><span class="sxs-lookup"><span data-stu-id="036c8-113">Single desktop experience—Applications installed in the virtual machine seamlessly available through the standard desktop Start menu and integrated with other applications on the user desktop.</span></span>

<span data-ttu-id="036c8-114">客户端和服务器（管理服务器和映像存储库）之间的所有通信都将置于标准的 HTTP 或 HTTPS 通道顶部。</span><span class="sxs-lookup"><span data-stu-id="036c8-114">All communication between the client and the servers (management server and image repository) is carried on top of a standard HTTP or HTTPS channel.</span></span>

![](images/506f54d0-38fa-446a-8070-17ae26da5355.gif)

 

 





