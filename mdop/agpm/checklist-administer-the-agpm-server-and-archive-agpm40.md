---
title: 清单管理 AGPM 服务器和存档
description: 清单管理 AGPM 服务器和存档
author: dansimp
ms.assetid: d9c60203-90c2-48a7-9318-197e0ec5038b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f0e464dafa68b9d93c5a1051c986a0efde4702c6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802091"
---
# <span data-ttu-id="175e9-103">清单：管理 AGPM 服务器和存档</span><span class="sxs-lookup"><span data-stu-id="175e9-103">Checklist: Administer the AGPM Server and Archive</span></span>


<span data-ttu-id="175e9-104">在高级组策略管理（AGPM）中，AGPM 服务和存档由 AGPM 管理员（完全控制）管理。</span><span class="sxs-lookup"><span data-stu-id="175e9-104">In Advanced Group Policy Management (AGPM), both the AGPM Service and the archive are managed by AGPM Administrators (Full Control).</span></span> <span data-ttu-id="175e9-105">以下是 AGPM 管理员的典型任务。</span><span class="sxs-lookup"><span data-stu-id="175e9-105">The following are typical tasks for an AGPM Administrator.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="175e9-106">常见任务</span><span class="sxs-lookup"><span data-stu-id="175e9-106">Frequent Task</span></span></th>
<th align="left"><span data-ttu-id="175e9-107">参考</span><span class="sxs-lookup"><span data-stu-id="175e9-107">Reference</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="175e9-108">委派对存档中的组策略对象（Gpo）的访问权限。</span><span class="sxs-lookup"><span data-stu-id="175e9-108">Delegate access to Group Policy Objects (GPOs) in the archive.</span></span></p></td>
<td align="left"><p><a href="delegate-domain-level-access-to-the-archive-agpm40.md" data-raw-source="[Delegate Domain-Level Access to the Archive](delegate-domain-level-access-to-the-archive-agpm40.md)"><span data-ttu-id="175e9-109">委派针对存档的域级访问权限</span><span class="sxs-lookup"><span data-stu-id="175e9-109">Delegate Domain-Level Access to the Archive</span></span></a></p>
<p><a href="delegate-access-to-an-individual-gpo-in-the-archive-agpm40.md" data-raw-source="[Delegate Access to an Individual GPO in the Archive](delegate-access-to-an-individual-gpo-in-the-archive-agpm40.md)"><span data-ttu-id="175e9-110">委派针对存档中单独 GPO 的访问权限</span><span class="sxs-lookup"><span data-stu-id="175e9-110">Delegate Access to an Individual GPO in the Archive</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="175e9-111">备份存档以启用灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="175e9-111">Back up the archive to enable disaster recovery.</span></span></p></td>
<td align="left"><p><a href="back-up-the-archive-agpm40.md" data-raw-source="[Back Up the Archive](back-up-the-archive-agpm40.md)"><span data-ttu-id="175e9-112">备份存档</span><span class="sxs-lookup"><span data-stu-id="175e9-112">Back Up the Archive</span></span></a></p></td>
</tr>
</tbody>
</table>

 

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="175e9-113">不常用任务</span><span class="sxs-lookup"><span data-stu-id="175e9-113">Infrequent Task</span></span></th>
<th align="left"><span data-ttu-id="175e9-114">参考</span><span class="sxs-lookup"><span data-stu-id="175e9-114">Reference</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="175e9-115">从备份还原存档以从灾难中恢复。</span><span class="sxs-lookup"><span data-stu-id="175e9-115">Restore the archive from a backup to recover from a disaster.</span></span></p></td>
<td align="left"><p><a href="restore-the-archive-from-a-backup-agpm40.md" data-raw-source="[Restore the Archive from a Backup](restore-the-archive-from-a-backup-agpm40.md)"><span data-ttu-id="175e9-116">从备份还原存档</span><span class="sxs-lookup"><span data-stu-id="175e9-116">Restore the Archive from a Backup</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="175e9-117">将 AGPM 服务、存档或两者移动到其他服务器。</span><span class="sxs-lookup"><span data-stu-id="175e9-117">Move the AGPM Service, the archive, or both to a different server.</span></span></p></td>
<td align="left"><p><a href="move-the-agpm-server-and-the-archive-agpm40.md" data-raw-source="[Move the AGPM Server and the Archive](move-the-agpm-server-and-the-archive-agpm40.md)"><span data-ttu-id="175e9-118">移动 AGPM 服务器和存档</span><span class="sxs-lookup"><span data-stu-id="175e9-118">Move the AGPM Server and the Archive</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="175e9-119">更改存档路径、AGPM 服务帐户或 AGPM 服务侦听的端口。</span><span class="sxs-lookup"><span data-stu-id="175e9-119">Change the archive path, the AGPM Service Account, or the port on which the AGPM Service listens.</span></span></p></td>
<td align="left"><p><a href="modify-the-agpm-service-agpm40.md" data-raw-source="[Modify the AGPM Service](modify-the-agpm-service-agpm40.md)"><span data-ttu-id="175e9-120">修改 AGPM 服务</span><span class="sxs-lookup"><span data-stu-id="175e9-120">Modify the AGPM Service</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="175e9-121">对 AGPM 服务器的常见问题进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="175e9-121">Troubleshoot common problems with the AGPM Server.</span></span></p></td>
<td align="left"><p><a href="troubleshooting-agpm-agpm40.md" data-raw-source="[Troubleshooting AGPM](troubleshooting-agpm-agpm40.md)"><span data-ttu-id="175e9-122">AGPM 疑难解答</span><span class="sxs-lookup"><span data-stu-id="175e9-122">Troubleshooting AGPM</span></span></a></p>
<p><a href="configure-logging-and-tracing-agpm40.md" data-raw-source="[Configure Logging and Tracing](configure-logging-and-tracing-agpm40.md)"><span data-ttu-id="175e9-123">配置记录和跟踪</span><span class="sxs-lookup"><span data-stu-id="175e9-123">Configure Logging and Tracing</span></span></a></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="175e9-124">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="175e9-124">Additional references</span></span>

-   [<span data-ttu-id="175e9-125">高级组策略管理 4.0</span><span class="sxs-lookup"><span data-stu-id="175e9-125">Advanced Group Policy Management 4.0</span></span>](advanced-group-policy-management-40.md)

 

 





