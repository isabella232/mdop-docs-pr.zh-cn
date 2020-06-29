---
title: 管理 AGPM 服务
description: 管理 AGPM 服务
author: dansimp
ms.assetid: 48ca02aa-6acf-403b-afd4-66ae8a953246
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cba6890986efdc6dbaec7cee8ebbec38903ca524
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802667"
---
# <span data-ttu-id="c3763-103">管理 AGPM 服务</span><span class="sxs-lookup"><span data-stu-id="c3763-103">Managing the AGPM Service</span></span>


<span data-ttu-id="c3763-104">AGPM 服务是充当安全代理的 Windows 服务，用于管理客户对域的存档和生产环境中的组策略对象（Gpo）的访问。</span><span class="sxs-lookup"><span data-stu-id="c3763-104">The AGPM Service is a Windows service that acts as a security proxy, managing client access to Group Policy Objects (GPOs) in the archive and production environment of the domain.</span></span> <span data-ttu-id="c3763-105">它强制实施高级组策略管理（AGPM）委派，并提供增强的安全级别。</span><span class="sxs-lookup"><span data-stu-id="c3763-105">It enforces Advanced Group Policy Management (AGPM) delegation and provides an enhanced level of security.</span></span> <span data-ttu-id="c3763-106">AGPM 服务托管在安装了 Microsoft 高级组策略管理-服务器的服务器上。</span><span class="sxs-lookup"><span data-stu-id="c3763-106">The AGPM Service is hosted on the server on which the Microsoft Advanced Group Policy Management - Server is installed.</span></span>

<span data-ttu-id="c3763-107">**小心** 不要通过操作系统中的 "**管理工具**和**服务**" 修改 AGPM 服务的设置。</span><span class="sxs-lookup"><span data-stu-id="c3763-107">**Caution** Do not modify settings for the AGPM Service through **Administrative Tools** and **Services** in the operating system.</span></span> <span data-ttu-id="c3763-108">这样做可能会阻止 AGPM 服务启动。</span><span class="sxs-lookup"><span data-stu-id="c3763-108">Doing so can prevent the AGPM Service from starting.</span></span>

 

-   [<span data-ttu-id="c3763-109">启动和停止 AGPM 服务</span><span class="sxs-lookup"><span data-stu-id="c3763-109">Start and Stop the AGPM Service</span></span>](start-and-stop-the-agpm-service-agpm40.md)

-   [<span data-ttu-id="c3763-110">修改 AGPM 服务</span><span class="sxs-lookup"><span data-stu-id="c3763-110">Modify the AGPM Service</span></span>](modify-the-agpm-service-agpm40.md)

### <span data-ttu-id="c3763-111">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="c3763-111">Additional references</span></span>

-   [<span data-ttu-id="c3763-112">移动 AGPM 服务器和存档</span><span class="sxs-lookup"><span data-stu-id="c3763-112">Move the AGPM Server and the Archive</span></span>](move-the-agpm-server-and-the-archive-agpm40.md)

-   [<span data-ttu-id="c3763-113">执行 AGPM 管理员任务</span><span class="sxs-lookup"><span data-stu-id="c3763-113">Performing AGPM Administrator Tasks</span></span>](performing-agpm-administrator-tasks-agpm40.md)

 

 





