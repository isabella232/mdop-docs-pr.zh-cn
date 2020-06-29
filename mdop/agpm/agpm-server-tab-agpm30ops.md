---
title: “AGPM 服务器”选项卡
description: “AGPM 服务器”选项卡
author: dansimp
ms.assetid: fb3b0265-53ed-4bf6-88a4-c409f5f1bed4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 335cad07691f914884583636cef01be8dbaa0266
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802156"
---
# <span data-ttu-id="bd5b9-103">“AGPM 服务器”选项卡</span><span class="sxs-lookup"><span data-stu-id="bd5b9-103">AGPM Server Tab</span></span>


<span data-ttu-id="bd5b9-104">通过 "**更改控制**" 窗格上的 " **AGPM 服务器**" 选项卡，你可以通过输入完全限定的计算机名称和端口来选择 AGPM 服务器，还可以从存档中删除较旧版本的组策略对象（gpo），以节省 agpm 服务器上的磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="bd5b9-104">The **AGPM Server** tab on the **Change Control** pane enables you to select an AGPM Server by entering a fully-qualified computer name and port, and to delete older versions of Group Policy Objects (GPOs) from the archive to conserve disk space on the AGPM Server.</span></span>

## <span data-ttu-id="bd5b9-105">指定 AGPM 服务器</span><span class="sxs-lookup"><span data-stu-id="bd5b9-105">Specifying the AGPM Server</span></span>


<span data-ttu-id="bd5b9-106">所选的 AGPM 服务器决定在 "**目录**" 选项卡上显示的存档，以及应用**域委派**设置的位置。</span><span class="sxs-lookup"><span data-stu-id="bd5b9-106">The AGPM Server selected determines which archive is displayed for you on the **Contents** tab and to which location the **Domain Delegation** settings are applied.</span></span> <span data-ttu-id="bd5b9-107">高级组策略管理（AGPM）的默认端口是端口4600。</span><span class="sxs-lookup"><span data-stu-id="bd5b9-107">The default port for Advanced Group Policy Management (AGPM) is port 4600.</span></span>

<span data-ttu-id="bd5b9-108">如果 AGPM 服务器连接是使用管理模板设置进行集中配置的，则此选项卡上用于配置连接的选项不可用。</span><span class="sxs-lookup"><span data-stu-id="bd5b9-108">If the AGPM Server connection is centrally configured using Administrative template settings, the options on this tab for configuring the connection are unavailable.</span></span> <span data-ttu-id="bd5b9-109">有关详细信息，请参阅[配置 AGPM 服务器连接](configure-agpm-server-connections-agpm30ops.md)。</span><span class="sxs-lookup"><span data-stu-id="bd5b9-109">For more information, see [Configure AGPM Server Connections](configure-agpm-server-connections-agpm30ops.md).</span></span>

## <span data-ttu-id="bd5b9-110">删除旧 GPO 版本</span><span class="sxs-lookup"><span data-stu-id="bd5b9-110">Deleting old GPO versions</span></span>


<span data-ttu-id="bd5b9-111">默认情况下，每个受控制的 GPO 的所有版本都将保留在存档中。</span><span class="sxs-lookup"><span data-stu-id="bd5b9-111">By default, all versions of every controlled GPO are retained in the archive.</span></span> <span data-ttu-id="bd5b9-112">但是，你可以配置 AGPM 服务以限制每个 GPO 的保留版本数，并在超过该限制时自动删除最早的版本。</span><span class="sxs-lookup"><span data-stu-id="bd5b9-112">However, you can configure the AGPM Service to limit the number of versions retained for each GPO and automatically delete the oldest version when that limit is exceeded.</span></span> <span data-ttu-id="bd5b9-113">仅在 "**历史记录**" 窗口的 "**唯一版本**" 选项卡上显示的 GPO 版本将计为 "限制"。</span><span class="sxs-lookup"><span data-stu-id="bd5b9-113">Only GPO versions displayed on the **Unique Versions** tab of the **History** window count toward the limit.</span></span>

<span data-ttu-id="bd5b9-114">**注意** 要为每个 GPO 存储的唯一版本的最大数量不包括当前版本，因此输入0仅保留当前版本。</span><span class="sxs-lookup"><span data-stu-id="bd5b9-114">**Note** The maximum number of unique versions to store for each GPO does not include the current version, so entering 0 retains only the current version.</span></span> <span data-ttu-id="bd5b9-115">该限制不得超过999个版本。</span><span class="sxs-lookup"><span data-stu-id="bd5b9-115">The limit must be no greater than 999 versions.</span></span>

<span data-ttu-id="bd5b9-116">删除 GPO 版本后，该版本的记录将保留在 GPO 的历史记录中，但 GPO 版本本身将从存档中删除。</span><span class="sxs-lookup"><span data-stu-id="bd5b9-116">When a GPO version is deleted, a record of that version remains in the history of the GPO, but the GPO version itself is deleted from the archive.</span></span> <span data-ttu-id="bd5b9-117">你可以通过在历史记录中将其标记为不可删除来阻止删除 GPO 版本。</span><span class="sxs-lookup"><span data-stu-id="bd5b9-117">You can prevent a GPO version from being deleted by marking it in the history as not deletable.</span></span>

 

### <span data-ttu-id="bd5b9-118">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="bd5b9-118">Additional references</span></span>

-   [<span data-ttu-id="bd5b9-119">用户界面：高级组策略管理</span><span class="sxs-lookup"><span data-stu-id="bd5b9-119">User Interface: Advanced Group Policy Management</span></span>](user-interface-advanced-group-policy-management-agpm30ops.md)

-   [<span data-ttu-id="bd5b9-120">执行 AGPM 管理员任务</span><span class="sxs-lookup"><span data-stu-id="bd5b9-120">Performing AGPM Administrator Tasks</span></span>](performing-agpm-administrator-tasks-agpm30ops.md)

-   [<span data-ttu-id="bd5b9-121">执行审阅者任务</span><span class="sxs-lookup"><span data-stu-id="bd5b9-121">Performing Reviewer Tasks</span></span>](performing-reviewer-tasks-agpm30ops.md)

 

 





