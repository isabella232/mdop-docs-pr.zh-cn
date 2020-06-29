---
title: 移动 AGPM 服务器和存档
description: 移动 AGPM 服务器和存档
author: dansimp
ms.assetid: 9ec48d3a-c293-45f0-8939-32ccdc062303
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 61ad2eb6e0ea46eef89379894a99469254e0fd5e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803187"
---
# <span data-ttu-id="ecc8c-103">移动 AGPM 服务器和存档</span><span class="sxs-lookup"><span data-stu-id="ecc8c-103">Move the AGPM Server and the Archive</span></span>


<span data-ttu-id="ecc8c-104">如果要替换 AGPM 服务器和托管存档的服务器，则必须移动 AGPM 服务和存档。</span><span class="sxs-lookup"><span data-stu-id="ecc8c-104">If you are replacing the AGPM Server and the server on which the archive is hosted, you must move the AGPM Service and the archive.</span></span> <span data-ttu-id="ecc8c-105">如果愿意，您可以单独移动 AGPM 服务和存档。</span><span class="sxs-lookup"><span data-stu-id="ecc8c-105">If you prefer, you can move the AGPM Service and the archive separately.</span></span>

**<span data-ttu-id="ecc8c-106">注意</span><span class="sxs-lookup"><span data-stu-id="ecc8c-106">Note</span></span>**  
-   <span data-ttu-id="ecc8c-107">AGPM 服务器是托管 AGPM 服务和安装了 Microsoft 高级组策略管理-服务器的计算机的计算机。</span><span class="sxs-lookup"><span data-stu-id="ecc8c-107">The AGPM Server is the computer that hosts the AGPM Service and the computer on which Microsoft Advanced Group Policy Management – Server is installed.</span></span>

-   <span data-ttu-id="ecc8c-108">默认情况下，存档位于 AGPM 服务器上，但你可以指定存档路径以在另一台服务器上托管它。</span><span class="sxs-lookup"><span data-stu-id="ecc8c-108">By default, the archive is hosted on the AGPM Server, but you can specify an archive path to host it on another server instead.</span></span>

 

<span data-ttu-id="ecc8c-109">要完成此过程，必须是域管理员组的成员并且具有访问以前的和新的 AGPM 服务器的权限。</span><span class="sxs-lookup"><span data-stu-id="ecc8c-109">A user account that is a member of the Domain Admins group and has access to the previous and new AGPM Servers is required to complete this procedure.</span></span> <span data-ttu-id="ecc8c-110">此外，你必须为要由新的 AGPM 服务器使用的 AGPM 服务帐户提供凭据，才能完成此过程。</span><span class="sxs-lookup"><span data-stu-id="ecc8c-110">Additionally, you must provide credentials for the AGPM Service Account to be used by the new AGPM Server to complete this procedure.</span></span>

**<span data-ttu-id="ecc8c-111">将 AGPM 服务和存档移动到其他服务器或服务器</span><span class="sxs-lookup"><span data-stu-id="ecc8c-111">To move the AGPM Service and the archive to a different server or servers</span></span>**

1.  <span data-ttu-id="ecc8c-112">备份存档。</span><span class="sxs-lookup"><span data-stu-id="ecc8c-112">Back up the archive.</span></span> <span data-ttu-id="ecc8c-113">有关详细信息，请参阅[备份存档](back-up-the-archive-agpm40.md)。</span><span class="sxs-lookup"><span data-stu-id="ecc8c-113">For more information, see [Back Up the Archive](back-up-the-archive-agpm40.md).</span></span>

2.  <span data-ttu-id="ecc8c-114">移动 AGPM 服务：</span><span class="sxs-lookup"><span data-stu-id="ecc8c-114">Move the AGPM Service:</span></span>

    1.  <span data-ttu-id="ecc8c-115">停止 AGPM 服务。</span><span class="sxs-lookup"><span data-stu-id="ecc8c-115">Stop the AGPM Service.</span></span> <span data-ttu-id="ecc8c-116">有关详细信息，请参阅[启动和停止 AGPM 服务](start-and-stop-the-agpm-service-agpm40.md)。</span><span class="sxs-lookup"><span data-stu-id="ecc8c-116">For more information, see [Start and Stop the AGPM Service](start-and-stop-the-agpm-service-agpm40.md).</span></span>

    2.  <span data-ttu-id="ecc8c-117">在将托管 AGPM 服务的新服务器上安装 Microsoft 高级组策略管理-服务器。</span><span class="sxs-lookup"><span data-stu-id="ecc8c-117">Install Microsoft Advanced Group Policy Management - Server on the new server that will host the AGPM Service.</span></span> <span data-ttu-id="ecc8c-118">在此过程中，你将指定新的存档路径，即存档相对于 AGPM 服务器的位置。</span><span class="sxs-lookup"><span data-stu-id="ecc8c-118">During this process, you specify the new archive path, the location for the archive in relation to the AGPM Server.</span></span> <span data-ttu-id="ecc8c-119">有关详细信息，请参阅[Microsoft 高级组策略管理4.0 的分步指南](https://go.microsoft.com/fwlink/?LinkId=153505)（ https://go.microsoft.com/fwlink/?LinkId=153505) 以及[Microsoft 高级组策略管理的规划指南](https://go.microsoft.com/fwlink/?LinkId=156883)（） https://go.microsoft.com/fwlink/?LinkId=156883) 。</span><span class="sxs-lookup"><span data-stu-id="ecc8c-119">For more information, see [Step-by-Step Guide for Microsoft Advanced Group Policy Management 4.0](https://go.microsoft.com/fwlink/?LinkId=153505) (https://go.microsoft.com/fwlink/?LinkId=153505) and [Planning Guide for Microsoft Advanced Group Policy Management](https://go.microsoft.com/fwlink/?LinkId=156883) (https://go.microsoft.com/fwlink/?LinkId=156883).</span></span>

    3.  <span data-ttu-id="ecc8c-120">AGPM 管理员（完全控制）必须为将使用新的 AGPM 服务器的所有组策略管理员配置 AGPM 服务器连接并删除旧的 AGPM 服务器的连接，否则每个组策略管理员必须手动配置新的 AGPM 服务器连接并删除其计算机上的 AGPM 管理单元的旧 AGPM 服务器连接。</span><span class="sxs-lookup"><span data-stu-id="ecc8c-120">Either an AGPM Administrator (Full Control) must configure the AGPM Server connection for all Group Policy administrators who will use the new AGPM Server and remove the connection for the old AGPM Server, or else each Group Policy administrator must manually configure the new AGPM Server connection and remove the old AGPM Server connection for the AGPM snap-in on their computer.</span></span> <span data-ttu-id="ecc8c-121">有关详细信息，请参阅[配置 AGPM 服务器连接](configure-agpm-server-connections-agpm40.md)。</span><span class="sxs-lookup"><span data-stu-id="ecc8c-121">For more information, see [Configure AGPM Server Connections](configure-agpm-server-connections-agpm40.md).</span></span>

        <span data-ttu-id="ecc8c-122">**注意** 最佳做法是从以前的 AGPM 服务器卸载 Microsoft 高级组策略管理-服务器。</span><span class="sxs-lookup"><span data-stu-id="ecc8c-122">**Note** As a best practice, you should uninstall Microsoft Advanced Group Policy Management – Server from the previous AGPM Server.</span></span> <span data-ttu-id="ecc8c-123">这将确保无法在该服务器上无意间重启 AGPM 服务，并且可能会在任何与它的 AGPM 服务器连接保留时导致混乱。</span><span class="sxs-lookup"><span data-stu-id="ecc8c-123">This will ensure that the AGPM Service cannot be unintentionally restarted on that server and potentially cause confusion if any AGPM Server connections to it remain.</span></span>

         

3.  <span data-ttu-id="ecc8c-124">将存档从备份复制到将托管存档的新服务器。</span><span class="sxs-lookup"><span data-stu-id="ecc8c-124">Copy the archive from the backup to the new server that will host the archive.</span></span> <span data-ttu-id="ecc8c-125">有关详细信息，请参阅[从备份还原存档](restore-the-archive-from-a-backup-agpm40.md)。</span><span class="sxs-lookup"><span data-stu-id="ecc8c-125">For more information, see [Restore the Archive from a Backup](restore-the-archive-from-a-backup-agpm40.md).</span></span>

    <span data-ttu-id="ecc8c-126">**重要提示** 如果您移动了存档，但没有同时移动 AGPM 服务：</span><span class="sxs-lookup"><span data-stu-id="ecc8c-126">**Important** If you moved the archive without moving the AGPM Service at the same time:</span></span>

    1.  <span data-ttu-id="ecc8c-127">必须将存档路径更改为指向与 AGPM 服务器相关的存档的新位置。</span><span class="sxs-lookup"><span data-stu-id="ecc8c-127">You must change the archive path to point to the new location for the archive in relation to the AGPM Server.</span></span> <span data-ttu-id="ecc8c-128">有关详细信息，请参阅[修改 AGPM 服务](modify-the-agpm-service-agpm40.md)。</span><span class="sxs-lookup"><span data-stu-id="ecc8c-128">For more information, see [Modify the AGPM Service](modify-the-agpm-service-agpm40.md).</span></span>

    2.  <span data-ttu-id="ecc8c-129">您必须重新输入并确认 "**域委派**" 选项卡上的密码。有关详细信息，请参阅[配置电子邮件通知](configure-e-mail-notification-agpm40.md)。</span><span class="sxs-lookup"><span data-stu-id="ecc8c-129">You must re-enter and confirm the password on the **Domain Delegation** tab. For more information, see [Configure E-Mail Notification](configure-e-mail-notification-agpm40.md).</span></span>

     

### <span data-ttu-id="ecc8c-130">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="ecc8c-130">Additional references</span></span>

-   [<span data-ttu-id="ecc8c-131">备份存档</span><span class="sxs-lookup"><span data-stu-id="ecc8c-131">Back Up the Archive</span></span>](back-up-the-archive-agpm40.md)

-   [<span data-ttu-id="ecc8c-132">从备份还原存档</span><span class="sxs-lookup"><span data-stu-id="ecc8c-132">Restore the Archive from a Backup</span></span>](restore-the-archive-from-a-backup-agpm40.md)

-   [<span data-ttu-id="ecc8c-133">配置 AGPM 服务器连接</span><span class="sxs-lookup"><span data-stu-id="ecc8c-133">Configure AGPM Server Connections</span></span>](configure-agpm-server-connections-agpm40.md)

-   [<span data-ttu-id="ecc8c-134">修改 AGPM 服务</span><span class="sxs-lookup"><span data-stu-id="ecc8c-134">Modify the AGPM Service</span></span>](modify-the-agpm-service-agpm40.md)

-   <span data-ttu-id="ecc8c-135">[Microsoft 高级组策略管理4.0 的分步指南](https://go.microsoft.com/fwlink/?LinkId=153505)（https://go.microsoft.com/fwlink/?LinkId=153505)</span><span class="sxs-lookup"><span data-stu-id="ecc8c-135">[Step-by-Step Guide for Microsoft Advanced Group Policy Management 4.0](https://go.microsoft.com/fwlink/?LinkId=153505) (https://go.microsoft.com/fwlink/?LinkId=153505)</span></span>

-   <span data-ttu-id="ecc8c-136">[Microsoft 高级组策略管理的规划指南](https://go.microsoft.com/fwlink/?LinkId=156883)（https://go.microsoft.com/fwlink/?LinkId=156883)</span><span class="sxs-lookup"><span data-stu-id="ecc8c-136">[Planning Guide for Microsoft Advanced Group Policy Management](https://go.microsoft.com/fwlink/?LinkId=156883) (https://go.microsoft.com/fwlink/?LinkId=156883)</span></span>

-   [<span data-ttu-id="ecc8c-137">执行 AGPM 管理员任务</span><span class="sxs-lookup"><span data-stu-id="ecc8c-137">Performing AGPM Administrator Tasks</span></span>](performing-agpm-administrator-tasks-agpm40.md)

 

 





