---
title: 管理存档
description: 管理存档
author: dansimp
ms.assetid: b11a3d71-74ea-4dd7-b243-6f2880b7af2d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 682d720b4095dbfa6a7cc4d868109f57c4f54641
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802664"
---
# <span data-ttu-id="0feb7-103">管理存档</span><span class="sxs-lookup"><span data-stu-id="0feb7-103">Managing the Archive</span></span>


<span data-ttu-id="0feb7-104">在高级组策略管理（AGPM）中，作为 AGPM 管理员（完全控制），你可以管理对存档的访问权限，并且可以选择限制存储在存档中的每个组策略对象（GPO）的版本数。</span><span class="sxs-lookup"><span data-stu-id="0feb7-104">In Advanced Group Policy Management (AGPM), as an AGPM Administrator (Full Control), you manage access to the archive and have the option to limit the number of versions of each Group Policy Object (GPO) stored in the archive.</span></span> <span data-ttu-id="0feb7-105">你可以在域级别或 GPO 级别委派对存档中的 Gpo 的访问权限。</span><span class="sxs-lookup"><span data-stu-id="0feb7-105">You can delegate access to GPOs in the archive at the domain level or GPO level.</span></span> <span data-ttu-id="0feb7-106">此外，你可以备份存档，以便你可以在发生灾难时能够恢复存档。</span><span class="sxs-lookup"><span data-stu-id="0feb7-106">Additionally, you can back up the archive so that you may be able to recover it if a disaster occurs.</span></span>

<span data-ttu-id="0feb7-107">作为 AGPM 管理员，你可以将 GPO 导出到文件，将文件复制到另一个林，然后将 GPO 导入到该林中的域中。</span><span class="sxs-lookup"><span data-stu-id="0feb7-107">As an AGPM Administrator, you can export a GPO to a file, copy the file to another forest, and then import the GPO into a domain in that forest.</span></span> <span data-ttu-id="0feb7-108">与编辑器不同，你可以将 GPO 备份中的策略设置从 GPO 备份直接导入到新的受控 GPO 中。</span><span class="sxs-lookup"><span data-stu-id="0feb7-108">Unlike an Editor, you can import policy settings from a GPO backup directly into a new controlled GPO when you create it.</span></span> <span data-ttu-id="0feb7-109">有关如何导出 GPO 的信息，请参阅[将 Gpo 导出到文件](export-a-gpo-to-a-file.md)。</span><span class="sxs-lookup"><span data-stu-id="0feb7-109">For information about how to export a GPO, see [Export a GPO to a File](export-a-gpo-to-a-file.md).</span></span>

-   [<span data-ttu-id="0feb7-110">委派针对存档的域级访问权限</span><span class="sxs-lookup"><span data-stu-id="0feb7-110">Delegate Domain-Level Access to the Archive</span></span>](delegate-domain-level-access-to-the-archive-agpm40.md)

-   [<span data-ttu-id="0feb7-111">委派针对存档中单独 GPO 的访问权限</span><span class="sxs-lookup"><span data-stu-id="0feb7-111">Delegate Access to an Individual GPO in the Archive</span></span>](delegate-access-to-an-individual-gpo-in-the-archive-agpm40.md)

-   [<span data-ttu-id="0feb7-112">限制存储的 GPO 版本</span><span class="sxs-lookup"><span data-stu-id="0feb7-112">Limit the GPO Versions Stored</span></span>](limit-the-gpo-versions-stored-agpm40.md)

-   [<span data-ttu-id="0feb7-113">从文件导入 GPO</span><span class="sxs-lookup"><span data-stu-id="0feb7-113">Import a GPO from a File</span></span>](import-a-gpo-from-a-file-agpmadmin.md)

-   [<span data-ttu-id="0feb7-114">备份存档</span><span class="sxs-lookup"><span data-stu-id="0feb7-114">Back Up the Archive</span></span>](back-up-the-archive-agpm40.md)

-   [<span data-ttu-id="0feb7-115">从备份还原存档</span><span class="sxs-lookup"><span data-stu-id="0feb7-115">Restore the Archive from a Backup</span></span>](restore-the-archive-from-a-backup-agpm40.md)

### <span data-ttu-id="0feb7-116">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="0feb7-116">Additional references</span></span>

-   <span data-ttu-id="0feb7-117">有关如何在生产环境中委派对 Gpo 的访问权限的信息，请参阅[委派对生产环境的访问权限](delegate-access-to-the-production-environment-agpm40.md)。</span><span class="sxs-lookup"><span data-stu-id="0feb7-117">For information about how to delegate access to GPOs in the production environment, see [Delegate Access to the Production Environment](delegate-access-to-the-production-environment-agpm40.md).</span></span>

-   <span data-ttu-id="0feb7-118">有关如何移动存档的信息，请参阅[移动 AGPM 服务器和存档](move-the-agpm-server-and-the-archive-agpm40.md)。</span><span class="sxs-lookup"><span data-stu-id="0feb7-118">For information about how to move the archive, see [Move the AGPM Server and the Archive](move-the-agpm-server-and-the-archive-agpm40.md).</span></span>

-   [<span data-ttu-id="0feb7-119">执行 AGPM 管理员任务</span><span class="sxs-lookup"><span data-stu-id="0feb7-119">Performing AGPM Administrator Tasks</span></span>](performing-agpm-administrator-tasks-agpm40.md)

 

 





