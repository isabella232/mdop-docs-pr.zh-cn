---
title: 启动和停止 AGPM 服务
description: 启动和停止 AGPM 服务
author: dansimp
ms.assetid: dcc9566c-c515-4fbe-b7f5-8ac030141307
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3c254cc122c43262ff5ec4cb0bf5a5ab2c77fac3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802524"
---
# <span data-ttu-id="af970-103">启动和停止 AGPM 服务</span><span class="sxs-lookup"><span data-stu-id="af970-103">Start and Stop the AGPM Service</span></span>


<span data-ttu-id="af970-104">AGPM 服务是充当安全代理的 Windows 服务，用于管理客户对存档和生产环境中的组策略对象（Gpo）的访问。</span><span class="sxs-lookup"><span data-stu-id="af970-104">The AGPM Service is a Windows service that acts as a security proxy, managing client access to Group Policy Objects (GPOs) in the archive and production environment.</span></span>

<span data-ttu-id="af970-105">**重要提示** 停止或禁用 AGPM 服务将阻止 AGPM 客户端通过服务器执行任何操作（如列出或编辑 Gpo）。</span><span class="sxs-lookup"><span data-stu-id="af970-105">**Important** Stopping or disabling the AGPM Service will prevent AGPM Clients from performing any operations (such as listing or editing GPOs) through the server.</span></span>

 

<span data-ttu-id="af970-106">需要访问 AGPM 服务器（安装了 AGPM 服务的计算机）的用户帐户才能完成此过程。</span><span class="sxs-lookup"><span data-stu-id="af970-106">A user account with access to the AGPM Server (the computer on which the AGPM Service is installed) is required to complete this procedure.</span></span>

**<span data-ttu-id="af970-107">启动或停止 AGPM 服务</span><span class="sxs-lookup"><span data-stu-id="af970-107">To start or stop the AGPM Service</span></span>**

1.  <span data-ttu-id="af970-108">在安装了 Microsoft 高级组策略管理-服务器（以及 AGPM 服务）的计算机上，单击 "**开始**"，单击 "**控制面板**"，单击 "**管理工具**"，然后单击 "**服务**"。</span><span class="sxs-lookup"><span data-stu-id="af970-108">On the computer on which Microsoft Advanced Group Policy Management - Server (and therefore the AGPM Service) is installed, click **Start**, click **Control Panel**, click **Administrative Tools**, and then click **Services**.</span></span>

2.  <span data-ttu-id="af970-109">在服务列表中，右键单击 " **AGPM 服务**"，然后选择 "**开始**"、"**重新启动**" 或 "**停止**"。</span><span class="sxs-lookup"><span data-stu-id="af970-109">In the list of services, right-click **AGPM Service** and select **Start**, **Restart**, or **Stop**.</span></span>

    <span data-ttu-id="af970-110">**小心** 不要通过操作系统中的 "**管理工具**和**服务**" 修改 AGPM 服务的设置。</span><span class="sxs-lookup"><span data-stu-id="af970-110">**Caution** Do not modify settings for the AGPM Service through **Administrative Tools** and **Services** in the operating system.</span></span> <span data-ttu-id="af970-111">这样做可能会阻止 AGPM 服务启动。</span><span class="sxs-lookup"><span data-stu-id="af970-111">Doing so can prevent the AGPM Service from starting.</span></span>

     

### <span data-ttu-id="af970-112">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="af970-112">Additional references</span></span>

-   [<span data-ttu-id="af970-113">管理 AGPM 服务</span><span class="sxs-lookup"><span data-stu-id="af970-113">Managing the AGPM Service</span></span>](managing-the-agpm-service-agpm40.md)

 

 





