---
title: 从备份还原存档
description: 从备份还原存档
author: dansimp
ms.assetid: b83f6173-a236-4da2-b16e-8df20920d4cc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3a1b7039ad587cf9c8d7f914fe3b963e12ba8949
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801800"
---
# <span data-ttu-id="6129b-103">从备份还原存档</span><span class="sxs-lookup"><span data-stu-id="6129b-103">Restore the Archive from a Backup</span></span>


<span data-ttu-id="6129b-104">如果发生灾难且高级组策略管理（AGPM）的存档已损坏或被破坏，则 AGPM 管理员（完全控制）可以先预准备好的备份副本还原存档，然后从域的生产环境中导入不在存档中的任何组策略对象（Gpo），或者生产中版本的版本比存档中的版本更新。</span><span class="sxs-lookup"><span data-stu-id="6129b-104">If a disaster occurs and the archive for Advanced Group Policy Management (AGPM) is damaged or destroyed, an AGPM Administrator (Full Control) can restore the archive from a backup copy prepared in advance and then import from the production environment of the domain any Group Policy Objects (GPOs) that are not in the archive or for which the version in production is more current than that in the archive.</span></span> <span data-ttu-id="6129b-105">有关如何将档案备份还原到其他服务器的信息，请参阅[移动 AGPM 服务器和存档](move-the-agpm-server-and-the-archive-agpm40.md)。</span><span class="sxs-lookup"><span data-stu-id="6129b-105">For information about how to restore an archive backup to a different server, see [Move the AGPM Server and the Archive](move-the-agpm-server-and-the-archive-agpm40.md).</span></span>

<span data-ttu-id="6129b-106">完成此过程需要访问 AGPM 服务器（安装了 AGPM 服务的计算机）和包含该存档的文件夹的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="6129b-106">A user account that has access to the AGPM Server (the computer on which the AGPM Service is installed) and to the folder that contains the archive is required to complete this procedure.</span></span>

**<span data-ttu-id="6129b-107">从备份还原存档</span><span class="sxs-lookup"><span data-stu-id="6129b-107">To restore the archive from a backup</span></span>**

1.  <span data-ttu-id="6129b-108">停止 AGPM 服务。</span><span class="sxs-lookup"><span data-stu-id="6129b-108">Stop the AGPM Service.</span></span> <span data-ttu-id="6129b-109">有关详细信息，请参阅[启动和停止 AGPM 服务](start-and-stop-the-agpm-service-agpm40.md)。</span><span class="sxs-lookup"><span data-stu-id="6129b-109">For more information, see [Start and Stop the AGPM Service](start-and-stop-the-agpm-service-agpm40.md).</span></span>

2.  <span data-ttu-id="6129b-110">删除现有存档。</span><span class="sxs-lookup"><span data-stu-id="6129b-110">Remove the existing archive.</span></span> <span data-ttu-id="6129b-111">默认情况下，"存档" 文件夹是%ProgramData%\\Microsoft\\AGPM，但安装了 Microsoft 高级组策略管理-服务器的 AGPM 管理员可能在安装过程中输入了不同的位置。</span><span class="sxs-lookup"><span data-stu-id="6129b-111">By default, the archive folder is %ProgramData%\\Microsoft\\AGPM, however the AGPM Administrator who installed Microsoft Advanced Group Policy Management - Server may have entered a different location during setup.</span></span>

3.  <span data-ttu-id="6129b-112">通过配置存档路径、AGPM 服务帐户、存档所有者和侦听端口来重新创建存档文件夹。</span><span class="sxs-lookup"><span data-stu-id="6129b-112">Re-create the archive folder by configuring the archive path, AGPM Service Account, Archive Owner, and listening port.</span></span> <span data-ttu-id="6129b-113">使用在原始安装期间使用的相同值不是必需的。</span><span class="sxs-lookup"><span data-stu-id="6129b-113">Using the same values as used during the original installation is not necessary.</span></span> <span data-ttu-id="6129b-114">有关详细信息，请参阅[修改 AGPM 服务](modify-the-agpm-service-agpm40.md)。</span><span class="sxs-lookup"><span data-stu-id="6129b-114">For more information, see [Modify the AGPM Service](modify-the-agpm-service-agpm40.md).</span></span>

4.  <span data-ttu-id="6129b-115">将档案备份的内容复制到 "存档" 文件夹，复制子文件夹和文件，以确保每个子文件夹和文件继承 "存档" 文件夹的权限。</span><span class="sxs-lookup"><span data-stu-id="6129b-115">Copy the contents of the archive backup to the archive folder, copying the subfolders and files to make sure that each subfolder and file inherits the permissions of the archive folder.</span></span> <span data-ttu-id="6129b-116">注意不要覆盖 "存档" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="6129b-116">Be careful not to overwrite the archive folder.</span></span>

5.  <span data-ttu-id="6129b-117">如果不确定存档备份中的 GPO 是否比生产中该 GPO 的副本更新，请生成差异报告并比较其设置。</span><span class="sxs-lookup"><span data-stu-id="6129b-117">If you not sure about whether a GPO in the archive backup is more current than the copy of that GPO in production, generate a difference report and compare their settings.</span></span> <span data-ttu-id="6129b-118">有关详细信息，请参阅[标识 gpo、Gpo 版本或模板之间的差异](identify-differences-between-gpos-gpo-versions-or-templates-agpm40.md)。</span><span class="sxs-lookup"><span data-stu-id="6129b-118">For more information, see [Identify Differences Between GPOs, GPO Versions, or Templates](identify-differences-between-gpos-gpo-versions-or-templates-agpm40.md).</span></span>

6.  <span data-ttu-id="6129b-119">重新启动 AGPM 服务。</span><span class="sxs-lookup"><span data-stu-id="6129b-119">Restart the AGPM Service.</span></span> <span data-ttu-id="6129b-120">有关详细信息，请参阅[启动和停止 AGPM 服务](start-and-stop-the-agpm-service-agpm40.md)。</span><span class="sxs-lookup"><span data-stu-id="6129b-120">For more information, see [Start and Stop the AGPM Service](start-and-stop-the-agpm-service-agpm40.md).</span></span>

### <span data-ttu-id="6129b-121">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="6129b-121">Additional references</span></span>

-   [<span data-ttu-id="6129b-122">备份存档</span><span class="sxs-lookup"><span data-stu-id="6129b-122">Back Up the Archive</span></span>](back-up-the-archive-agpm40.md)

-   [<span data-ttu-id="6129b-123">移动 AGPM 服务器和存档</span><span class="sxs-lookup"><span data-stu-id="6129b-123">Move the AGPM Server and the Archive</span></span>](move-the-agpm-server-and-the-archive-agpm40.md)

-   [<span data-ttu-id="6129b-124">管理存档</span><span class="sxs-lookup"><span data-stu-id="6129b-124">Managing the Archive</span></span>](managing-the-archive-agpm40.md)

 

 




