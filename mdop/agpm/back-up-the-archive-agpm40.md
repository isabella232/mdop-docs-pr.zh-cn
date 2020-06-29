---
title: 备份存档
description: 备份存档
author: dansimp
ms.assetid: 538d85eb-3596-4c1d-bbd7-26bc28857c28
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8c6888d61e126d603aefa4e818f1070c5a493ea6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802127"
---
# <span data-ttu-id="14d79-103">备份存档</span><span class="sxs-lookup"><span data-stu-id="14d79-103">Back Up the Archive</span></span>


<span data-ttu-id="14d79-104">若要帮助恢复高级组策略管理（AGPM）的存档（如果存在灾难），AGPM 管理员（完全控制）应经常备份存档。</span><span class="sxs-lookup"><span data-stu-id="14d79-104">To help in the recovery of the archive for Advanced Group Policy Management (AGPM) if there is a disaster, an AGPM Administrator (Full Control) should back up the archive frequently.</span></span> <span data-ttu-id="14d79-105">默认情况下，将在%ProgramData%\\Microsoft\\AGPM. 中创建存档。</span><span class="sxs-lookup"><span data-stu-id="14d79-105">By default, the archive is created in %ProgramData%\\Microsoft\\AGPM.</span></span> <span data-ttu-id="14d79-106">但是，你可以在 Microsoft 高级组策略管理-服务器的安装期间指定另一个路径。</span><span class="sxs-lookup"><span data-stu-id="14d79-106">However, you can specify a different path during the setup of Microsoft Advanced Group Policy Management - Server.</span></span>

<span data-ttu-id="14d79-107">对 AGPM 服务器具有访问权限的用户帐户（安装了 AGPM 服务的计算机）和包含存档的文件夹需要完成此过程。</span><span class="sxs-lookup"><span data-stu-id="14d79-107">A user account that has access to both the AGPM Server—the computer on which the AGPM Service is installed—and to the folder that contains the archive is required to complete this procedure.</span></span>

**<span data-ttu-id="14d79-108">备份存档</span><span class="sxs-lookup"><span data-stu-id="14d79-108">To back up the archive</span></span>**

1.  <span data-ttu-id="14d79-109">停止 AGPM 服务。</span><span class="sxs-lookup"><span data-stu-id="14d79-109">Stop the AGPM Service.</span></span> <span data-ttu-id="14d79-110">有关详细信息，请参阅[启动和停止 AGPM 服务](start-and-stop-the-agpm-service-agpm40.md)。</span><span class="sxs-lookup"><span data-stu-id="14d79-110">For more information, see [Start and Stop the AGPM Service](start-and-stop-the-agpm-service-agpm40.md).</span></span>

2.  <span data-ttu-id="14d79-111">使用 Windows 资源管理器、Xcopy、Windows Server®备份或其他备份工具备份存档文件夹。</span><span class="sxs-lookup"><span data-stu-id="14d79-111">Back up the archive folder by using Windows Explorer, Xcopy, Windows Server® Backup, or another backup tool.</span></span> <span data-ttu-id="14d79-112">请确保备份隐藏、系统和只读文件。</span><span class="sxs-lookup"><span data-stu-id="14d79-112">Make sure that you back up hidden, system, and read-only files.</span></span>

3.  <span data-ttu-id="14d79-113">将档案备份存储在安全位置。</span><span class="sxs-lookup"><span data-stu-id="14d79-113">Store the archive backup in a secure location.</span></span>

4.  <span data-ttu-id="14d79-114">重新启动 AGPM 服务。</span><span class="sxs-lookup"><span data-stu-id="14d79-114">Restart the AGPM Service.</span></span> <span data-ttu-id="14d79-115">有关详细信息，请参阅[启动和停止 AGPM 服务](start-and-stop-the-agpm-service-agpm40.md)。</span><span class="sxs-lookup"><span data-stu-id="14d79-115">For more information, see [Start and Stop the AGPM Service](start-and-stop-the-agpm-service-agpm40.md).</span></span>

<span data-ttu-id="14d79-116">**注意** 如果 AGPM 管理员很少备份存档，则档案备份中的组策略对象（Gpo）将不会是最新的。</span><span class="sxs-lookup"><span data-stu-id="14d79-116">**Note** If an AGPM Administrator backs up the archive infrequently, the Group Policy Objects (GPOs) in the archive backup will not be current.</span></span> <span data-ttu-id="14d79-117">为了更好地确保存档备份是最新的，请将存档备份为组织的每日备份策略的一部分。</span><span class="sxs-lookup"><span data-stu-id="14d79-117">To better ensure that the archive backup is current, back up the archive as part of your organization’s daily backup strategy.</span></span>

 

### <span data-ttu-id="14d79-118">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="14d79-118">Additional references</span></span>

-   [<span data-ttu-id="14d79-119">从备份还原存档</span><span class="sxs-lookup"><span data-stu-id="14d79-119">Restore the Archive from a Backup</span></span>](restore-the-archive-from-a-backup-agpm40.md)

-   [<span data-ttu-id="14d79-120">移动 AGPM 服务器和存档</span><span class="sxs-lookup"><span data-stu-id="14d79-120">Move the AGPM Server and the Archive</span></span>](move-the-agpm-server-and-the-archive-agpm40.md)

-   [<span data-ttu-id="14d79-121">管理存档</span><span class="sxs-lookup"><span data-stu-id="14d79-121">Managing the Archive</span></span>](managing-the-archive-agpm40.md)

 

 





