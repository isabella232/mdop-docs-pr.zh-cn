---
title: 管理 AGPM 服务
description: 管理 AGPM 服务
author: dansimp
ms.assetid: 331f64d2-1236-4711-81b4-1b92f019bfa5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3247be846487ba6d80f30a55654b20b3db96e219
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802671"
---
# <span data-ttu-id="bcaf6-103">管理 AGPM 服务</span><span class="sxs-lookup"><span data-stu-id="bcaf6-103">Managing the AGPM Service</span></span>


<span data-ttu-id="bcaf6-104">AGPM 服务是充当安全代理的 Windows 服务，用于管理客户对存档和生产环境中的组策略对象（Gpo）的访问。</span><span class="sxs-lookup"><span data-stu-id="bcaf6-104">The AGPM Service is a Windows service that acts as a security proxy, managing client access to Group Policy objects (GPOs) in the archive and production environment.</span></span> <span data-ttu-id="bcaf6-105">它强制实施高级组策略管理（AGPM）委派，并提供增强的安全级别。</span><span class="sxs-lookup"><span data-stu-id="bcaf6-105">It enforces Advanced Group Policy Management (AGPM) delegation and provides an enhanced level of security.</span></span> <span data-ttu-id="bcaf6-106">AGPM 服务托管在安装了 Microsoft 高级组策略管理-服务器的服务器上。</span><span class="sxs-lookup"><span data-stu-id="bcaf6-106">The AGPM Service is hosted on the server on which the Microsoft Advanced Group Policy Management - Server is installed.</span></span>

<span data-ttu-id="bcaf6-107">**小心** 不要通过操作系统中的 "**管理工具**和**服务**" 修改 AGPM 服务的设置。</span><span class="sxs-lookup"><span data-stu-id="bcaf6-107">**Caution** Do not modify settings for the AGPM Service through **Administrative Tools** and **Services** in the operating system.</span></span> <span data-ttu-id="bcaf6-108">这样做可能会阻止 AGPM 服务启动。</span><span class="sxs-lookup"><span data-stu-id="bcaf6-108">Doing so can prevent the AGPM Service from starting.</span></span>

 

-   [<span data-ttu-id="bcaf6-109">启动和停止 AGPM 服务</span><span class="sxs-lookup"><span data-stu-id="bcaf6-109">Start and Stop the AGPM Service</span></span>](start-and-stop-the-agpm-service.md)

-   [<span data-ttu-id="bcaf6-110">修改存档路径</span><span class="sxs-lookup"><span data-stu-id="bcaf6-110">Modify the Archive Path</span></span>](modify-the-archive-path.md)

-   [<span data-ttu-id="bcaf6-111">修改 AGPM 服务帐户</span><span class="sxs-lookup"><span data-stu-id="bcaf6-111">Modify the AGPM Service Account</span></span>](modify-the-agpm-service-account.md)

-   [<span data-ttu-id="bcaf6-112">修改 AGPM 服务侦听的端口</span><span class="sxs-lookup"><span data-stu-id="bcaf6-112">Modify the Port on Which the AGPM Service Listens</span></span>](modify-the-port-on-which-the-agpm-service-listens.md)

 

 





