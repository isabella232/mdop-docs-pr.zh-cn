---
title: 设计 MED-V 服务器基础结构
description: 设计 MED-V 服务器基础结构
author: dansimp
ms.assetid: 2781040f-880e-4e16-945d-a38c0adb4151
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 4ba4c38328c5484b7daa292f9fc33a4e59824327
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803517"
---
# <span data-ttu-id="10e42-103">设计 MED-V 服务器基础结构</span><span class="sxs-lookup"><span data-stu-id="10e42-103">Design the MED-V Server Infrastructure</span></span>


<span data-ttu-id="10e42-104">在本主题中，你将为每个 MED-V 实例设计服务器基础结构。</span><span class="sxs-lookup"><span data-stu-id="10e42-104">In this topic, you will design the server infrastructure for each MED-V instance.</span></span> <span data-ttu-id="10e42-105">这包括确定 SQL Server 实例是否将存在于 MED-V 服务器或远程服务器上以及 SQL Server 数据库的大小。</span><span class="sxs-lookup"><span data-stu-id="10e42-105">This includes determining whether the SQL Server instance will exist on the MED-V server or on a remote server, as well as the size of the SQL Server database.</span></span> <span data-ttu-id="10e42-106">你还将确定管理控制台的位置。</span><span class="sxs-lookup"><span data-stu-id="10e42-106">You will also determine the location of the management console.</span></span>

## <span data-ttu-id="10e42-107">为每个 MED-V 实例设计和放置服务器</span><span class="sxs-lookup"><span data-stu-id="10e42-107">Design and Place the Server for Each MED-V Instance</span></span>


<span data-ttu-id="10e42-108">MED-V 服务器实现策略并存储有关其客户端的状态和历史记录数据。</span><span class="sxs-lookup"><span data-stu-id="10e42-108">The MED-V server implements policies and stores state and history data about its clients.</span></span>

### <span data-ttu-id="10e42-109">外形规格</span><span class="sxs-lookup"><span data-stu-id="10e42-109">Form Factor</span></span>

<span data-ttu-id="10e42-110">MED-V 建议将 2.8 GHz 双核 CPU 服务器与2GB 的 RAM 配合使用。</span><span class="sxs-lookup"><span data-stu-id="10e42-110">MED-V recommends using a 2.8-GHz dual core CPU server with 2GB of RAM.</span></span> <span data-ttu-id="10e42-111">此建议基于以下假设： MED-V 服务器将在专用计算机上运行，并且 SQL Server 和 MED-V 管理控制台将在单独的计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="10e42-111">This recommendation is based on the assumption that the MED-V server will run on a dedicated machine and that SQL Server and the MED-V management console will run on separate machines.</span></span>

<span data-ttu-id="10e42-112">鉴于此工作负荷，MED-V 服务器应该相对较轻的负载。</span><span class="sxs-lookup"><span data-stu-id="10e42-112">Given this workload, the MED-V server should be relatively lightly loaded.</span></span> <span data-ttu-id="10e42-113">如果在服务器外形规格上没有特定的体系结构指导，请使用 MED-V 建议设计服务器，其中包含与组织的标准外形规格相匹配的内存。</span><span class="sxs-lookup"><span data-stu-id="10e42-113">In the absence of specific architectural guidance on the server form factor, design the server using the MED-V recommendation, with memory that matches the organization’s standard form factor.</span></span> <span data-ttu-id="10e42-114">MED-V 服务器可以在 Windows Server2008 上的虚拟机（VM）上运行。</span><span class="sxs-lookup"><span data-stu-id="10e42-114">The MED-V server can be run on a virtual machine (VM) on Windows Server2008 Hyper-V.</span></span> <span data-ttu-id="10e42-115">如果将使用 VM，请确保它可以访问与为物理计算机指定的资源等效的 CPU 和内存资源。</span><span class="sxs-lookup"><span data-stu-id="10e42-115">If a VM will be used, ensure that it has access to CPU and memory resources equivalent to those specified for a physical machine.</span></span>

<span data-ttu-id="10e42-116">MED-V 服务器所需的磁盘容量必须足以存储 MED-V 工作区配置文件。</span><span class="sxs-lookup"><span data-stu-id="10e42-116">The disk capacity the MED-V server requires must be sufficient to store the MED-V workspace configuration files.</span></span> <span data-ttu-id="10e42-117">MED-V 工作区只能对一个或多个用户使用一个 VM 和一个策略。</span><span class="sxs-lookup"><span data-stu-id="10e42-117">A MED-V workspace can only use one VM, and one policy, for one or more users.</span></span> <span data-ttu-id="10e42-118">因此，必须存储的 MED-V 工作区的数量取决于同一 VM 的不同用户需要不同策略的程度以及将使用的 Vm 数的程度。</span><span class="sxs-lookup"><span data-stu-id="10e42-118">Therefore, the number of MED-V workspaces that must be stored depends on the degree to which different policies are required for different users of the same VM, as well as the number of VMs that will be used.</span></span> <span data-ttu-id="10e42-119">MED-V 工作区 XML 文件的大小围绕典型的 MED-V 工作区的30KB。</span><span class="sxs-lookup"><span data-stu-id="10e42-119">The MED-V workspace XML files are around 30KB in size for a typical MED-V workspace.</span></span> <span data-ttu-id="10e42-120">若要确定所需的磁盘容量，请将 30 KB 乘以 MED-V 服务器将存储的 MED-V 工作区的数量。</span><span class="sxs-lookup"><span data-stu-id="10e42-120">To determine the required disk capacity, multiply 30 KB by the number of MED-V workspaces that the MED-V server will store.</span></span>

<span data-ttu-id="10e42-121">MED-V 服务器最重要的网络连接是指向其客户端的链接，因此将服务器放在一个网络位置，该位置提供最可用的带宽和最强健的客户端链接。</span><span class="sxs-lookup"><span data-stu-id="10e42-121">The MED-V server’s most important network connections are the links to its clients, therefore place the server in a network location that provides the most available bandwidth and the most robust links to its clients.</span></span>

### <span data-ttu-id="10e42-122">容错</span><span class="sxs-lookup"><span data-stu-id="10e42-122">Fault Tolerance</span></span>

<span data-ttu-id="10e42-123">MED-V 实例中只能有一个活动的 MED-V 服务器，而 MED-V 不包含将服务器置于 Microsoft 群集服务器（MSCS）群集中以提供容错的标准功能。</span><span class="sxs-lookup"><span data-stu-id="10e42-123">There can only be one active MED-V server in a MED-V instance, and MED-V does not include standard capabilities to place the server in a Microsoft Cluster Server (MSCS) cluster to provide fault tolerance.</span></span> <span data-ttu-id="10e42-124">可手动配置被动备份服务器。</span><span class="sxs-lookup"><span data-stu-id="10e42-124">A passive backup server can be manually configured.</span></span>

<span data-ttu-id="10e42-125">若要确定是否应为 MED-V 实例手动配置被动备份服务器，请确定是否允许用户在脱机模式下使用 MED-V 图像。</span><span class="sxs-lookup"><span data-stu-id="10e42-125">To decide whether a passive backup server should be manually configured for the MED-V instance, determine whether users will be permitted to use the MED-V images in offline mode.</span></span> <span data-ttu-id="10e42-126">有关脱机模式的信息，请参阅[如何配置域用户或组](how-to-configure-a-domain-user-or-groupmedvv2.md)。</span><span class="sxs-lookup"><span data-stu-id="10e42-126">For information on offline mode, see [How to Configure a Domain User or Group](how-to-configure-a-domain-user-or-groupmedvv2.md).</span></span> <span data-ttu-id="10e42-127">如果不允许用户脱机工作，则即使尚未在客户端上启动 MED-V 工作区，也无法继续在 MED-V 服务器失败的事件中工作。</span><span class="sxs-lookup"><span data-stu-id="10e42-127">If users are not allowed to work offline, they will be unable to continue working in the event of a MED-V server failure, even if the MED-V workspace has already been started on the client.</span></span> <span data-ttu-id="10e42-128">如果允许脱机工作，对于每个 MED-V 工作区，请确定客户端在必须进行身份验证之前允许多长时间脱机工作。</span><span class="sxs-lookup"><span data-stu-id="10e42-128">If offline work is permitted, for each MED-V workspace, determine how long the client is allowed to work offline before it must authenticate.</span></span> <span data-ttu-id="10e42-129">这是服务器无法使用的最长时间。</span><span class="sxs-lookup"><span data-stu-id="10e42-129">This is the maximum amount of time that the server can be unavailable.</span></span>

## <span data-ttu-id="10e42-130">设计和放置 SQL Server 数据库</span><span class="sxs-lookup"><span data-stu-id="10e42-130">Design and Place the SQL Server Database</span></span>


<span data-ttu-id="10e42-131">MED-V 服务器使用 SQL Server 数据库存储客户端状态和事件。</span><span class="sxs-lookup"><span data-stu-id="10e42-131">The MED-V server uses the SQL Server database to store client status and events.</span></span> <span data-ttu-id="10e42-132">你可以将 SQL Server 数据库安装在 MED-V 服务器所在的同一台计算机上，也可以将其放在运行 SQL Server 的单独服务器上，该服务器可以选择是远程的。</span><span class="sxs-lookup"><span data-stu-id="10e42-132">You can install the SQL Server database on the same machine as the MED-V server or you can place it on a separate server running SQL Server, which can optionally be remote.</span></span> <span data-ttu-id="10e42-133">你可以与其他 MED-V 实例共享数据库，在这种情况下，来自这些实例的事件和警报将存储在同一数据库中，并且报表将包含来自所有实例的事件。</span><span class="sxs-lookup"><span data-stu-id="10e42-133">You can share the database with other MED-V instances, in which case events and alerts from those instances will be stored in the same database, and reports will include events from all instances.</span></span> <span data-ttu-id="10e42-134">可以在现有 SQL Server 实例中安装数据库，其他 MED-V 服务器的数据库可以驻留在同一实例中。</span><span class="sxs-lookup"><span data-stu-id="10e42-134">You can install the database in an existing SQL Server instance, and the databases of other MED-V servers can reside in that same instance.</span></span>

<span data-ttu-id="10e42-135">如果将数据库服务器放在 MED-V 服务器的远程位置，并且跨网络链接没有足够的可用带宽，则在控制台中加载报表可能会很慢，并且可能不会显示客户端的最新数据。</span><span class="sxs-lookup"><span data-stu-id="10e42-135">If you place the database server in a location that is remote from the MED-V server, across networks links that do not have sufficient bandwidth available, reports may be slow to load in the console and may not display the latest data from clients.</span></span> <span data-ttu-id="10e42-136">请参阅在[定义项目范围](define-the-project-scope.md)中确定的组织服务级别期望值，并使用该信息确定 SQL Server 数据库的放置位置。</span><span class="sxs-lookup"><span data-stu-id="10e42-136">Refer to the organization service level expectations that you determined in [Define the Project Scope](define-the-project-scope.md) and use that information to decide where to place the SQL Server database.</span></span>

### <span data-ttu-id="10e42-137">外形规格</span><span class="sxs-lookup"><span data-stu-id="10e42-137">Form Factor</span></span>

<span data-ttu-id="10e42-138">如果你在使用 MED-V 的同一服务器上运行 SQL Server，并且 SQL Server 将仅用于存储该服务器的数据，请从 MED-V 建议开始，为 SQL Server 加载添加资源。</span><span class="sxs-lookup"><span data-stu-id="10e42-138">If you will run SQL Server on the same server as MED-V, and if SQL Server will only be used to store data for that server, start with the MED-V recommendation and add resources for the SQL Server load.</span></span> <span data-ttu-id="10e42-139">如果 SQL Server 将存储来自多个 MED-V 实例的事件和警报，有关如何缩放服务器板型的信息，请参阅[基础结构规划和设计 MICROSOFT SQL Server 2008](https://go.microsoft.com/fwlink/?LinkId=163302)指南（http://go.microsoft.com/fwlink/?LinkId=163302）。</span><span class="sxs-lookup"><span data-stu-id="10e42-139">If SQL Server will store events and alerts from more than one MED-V instance, for information on how to scale up the server form factor, see the [Infrastructure Planning and Design Microsoft SQL Server 2008](https://go.microsoft.com/fwlink/?LinkId=163302) guide (http:// go.microsoft.com/fwlink/?LinkId=163302).</span></span>

<span data-ttu-id="10e42-140">数据库的大小取决于数据库将存储的客户端事件数。</span><span class="sxs-lookup"><span data-stu-id="10e42-140">The size of the database depends on the number of client events that the database will store.</span></span> <span data-ttu-id="10e42-141">事件由客户端的常规操作（例如，启动 MED-V 工作区时）或在 MED-V 工作区中出现错误的情况下创建。</span><span class="sxs-lookup"><span data-stu-id="10e42-141">Events are created by normal operation of the client, such as when a MED-V workspace is started, or when there is an error in the MED-V workspace.</span></span> <span data-ttu-id="10e42-142">客户端发送事件的默认间隔是1分钟。</span><span class="sxs-lookup"><span data-stu-id="10e42-142">The default interval at which the client sends events is 1 minute.</span></span>

<span data-ttu-id="10e42-143">若要估计数据库的大小，请确定以下事项：</span><span class="sxs-lookup"><span data-stu-id="10e42-143">To estimate the size of the database, determine the following:</span></span>

-   <span data-ttu-id="10e42-144">MED-V 实例中的客户端数。</span><span class="sxs-lookup"><span data-stu-id="10e42-144">Number of clients in the MED-V instance.</span></span> <span data-ttu-id="10e42-145">最大值为5000。</span><span class="sxs-lookup"><span data-stu-id="10e42-145">The maximum is 5,000.</span></span>

-   <span data-ttu-id="10e42-146">典型的事件到达率。</span><span class="sxs-lookup"><span data-stu-id="10e42-146">Typical event arrival rate.</span></span> <span data-ttu-id="10e42-147">此速率取决于客户端使用情况，但每个客户端每天大约有15到20个事件。</span><span class="sxs-lookup"><span data-stu-id="10e42-147">This rate depends on client usage behavior but is approximately 15 to 20 events per day per client.</span></span>

-   <span data-ttu-id="10e42-148">事件大小。</span><span class="sxs-lookup"><span data-stu-id="10e42-148">Event size.</span></span> <span data-ttu-id="10e42-149">大小通常约为200字节。</span><span class="sxs-lookup"><span data-stu-id="10e42-149">The size is typically around 200 bytes.</span></span>

-   <span data-ttu-id="10e42-150">存储量。</span><span class="sxs-lookup"><span data-stu-id="10e42-150">Storage amount.</span></span> <span data-ttu-id="10e42-151">将存储事件的天数。</span><span class="sxs-lookup"><span data-stu-id="10e42-151">The number of days for which events will be stored.</span></span>

<span data-ttu-id="10e42-152">将这些值放在一起以计算所需数据存储的大小（以字节为单位），然后为以下各项添加安全因素：</span><span class="sxs-lookup"><span data-stu-id="10e42-152">Multiply these values together to calculate the size of the required data storage in bytes, and then add a safety factor to account for the following:</span></span>

-   <span data-ttu-id="10e42-153">错误，这可能会在较短的时间内从客户端创建大量事件。</span><span class="sxs-lookup"><span data-stu-id="10e42-153">Errors, which could create a large number of events from a client in a short period of time.</span></span>

-   <span data-ttu-id="10e42-154">数据库表和组织空间。</span><span class="sxs-lookup"><span data-stu-id="10e42-154">Database table and organizational space.</span></span>

<span data-ttu-id="10e42-155">若要估计每秒基础结构优化（IOPs）要求，请使用上述值，将典型事件到达率乘以实例中的客户端数。</span><span class="sxs-lookup"><span data-stu-id="10e42-155">To approximate the infrastructure optimization per second (IOPs) requirement, use the above values, multiplying the typical event arrival rate by the number of clients in the instance.</span></span> <span data-ttu-id="10e42-156">这将生成每天可以写入的记录数。</span><span class="sxs-lookup"><span data-stu-id="10e42-156">This yields the number of records that can be written per day.</span></span> <span data-ttu-id="10e42-157">将该数字除以86400以派生每秒写入的记录数。</span><span class="sxs-lookup"><span data-stu-id="10e42-157">Divide that number by 86,400 to derive the number of records written per second.</span></span> <span data-ttu-id="10e42-158">如果可通过单个基础结构优化（IO）操作 equated 写入操作，则此数字是所需的写入 IOPs。</span><span class="sxs-lookup"><span data-stu-id="10e42-158">If a write operations can be equated with a single infrastructure optimization (IO) operation, this number is the write IOPs required.</span></span> <span data-ttu-id="10e42-159">将缓冲区添加到用于报告活动的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="10e42-159">Add a buffer to that for reporting activity.</span></span> <span data-ttu-id="10e42-160">这很难确定，但取决于与实例一起使用的控制台的数量以及用于生成报告的频率。</span><span class="sxs-lookup"><span data-stu-id="10e42-160">This is difficult to determine but depends on the number of consoles in use with the instance and the frequency with which they are used to generate reports.</span></span>

### <span data-ttu-id="10e42-161">容错</span><span class="sxs-lookup"><span data-stu-id="10e42-161">Fault Tolerance</span></span>

<span data-ttu-id="10e42-162">当 MED-V 客户端正在运行时，如果服务器不可用，将在客户端上备份事件，并且报表将在管理控制台中不可用。</span><span class="sxs-lookup"><span data-stu-id="10e42-162">When MED-V client is running, if the server is unavailable, events will be backed up on the client and reports will be unavailable in the management console.</span></span> <span data-ttu-id="10e42-163">请参阅在[定义项目范围](define-the-project-scope.md)中确定的组织的服务级别期望值，以确定是否需要容错 SQL Server 基础结构的设计。</span><span class="sxs-lookup"><span data-stu-id="10e42-163">Refer to the organization’s service level expectations determined in [Define the Project Scope](define-the-project-scope.md) to decide whether the design of a fault-tolerant SQL Server infrastructure is necessary.</span></span>

<span data-ttu-id="10e42-164">MED-V 不提供对 MSCS 群集中运行的 SQL Server 的支持。</span><span class="sxs-lookup"><span data-stu-id="10e42-164">MED-V does not provide support for running SQL Server in an MSCS cluster.</span></span> <span data-ttu-id="10e42-165">为了提供热备用并在出现故障时避免数据丢失，可以将 SQL Server 置于日志传送配置中。</span><span class="sxs-lookup"><span data-stu-id="10e42-165">In order to provide warm standby and to avoid data loss in the event of a failure, you can place SQL Server in a log shipping configuration.</span></span> <span data-ttu-id="10e42-166">有关日志传送的信息，请参阅[基础结构规划和设计 MICROSOFT SQL Server 2008](https://go.microsoft.com/fwlink/?LinkId=163302)指南（ https://go.microsoft.com/fwlink/?LinkId=163302) 。</span><span class="sxs-lookup"><span data-stu-id="10e42-166">For information on log shipping, see the [Infrastructure Planning and Design Microsoft SQL Server 2008](https://go.microsoft.com/fwlink/?LinkId=163302) guide (https://go.microsoft.com/fwlink/?LinkId=163302).</span></span>

## <span data-ttu-id="10e42-167">设计管理控制台</span><span class="sxs-lookup"><span data-stu-id="10e42-167">Design the Management Console</span></span>


<span data-ttu-id="10e42-168">MED-V 管理控制台的部分功能是先测试虚拟机，然后再将其打包以分发到 MED-V 客户端。</span><span class="sxs-lookup"><span data-stu-id="10e42-168">Part of the functionality of the MED-V management console is to test VMs before they are packed for distribution to MED-V clients.</span></span> <span data-ttu-id="10e42-169">因此，管理控制台应采用与典型的 MED-V 客户端计算机的外形规格相似的外形规格设计。</span><span class="sxs-lookup"><span data-stu-id="10e42-169">Therefore, the management console should be designed with a form factor that resembles, as closely as possible, the form factor of a typical MED-V client machine.</span></span>

<span data-ttu-id="10e42-170">管理控制台应用程序与 MED-V 客户端一起安装，并使用 microsoft Virtual PC2007 SP1 和 Microsoft 知识库文章974918中所述的修复程序。</span><span class="sxs-lookup"><span data-stu-id="10e42-170">The management console application is installed together with the MED-V client and uses Microsoft Virtual PC2007 SP1 with the hotfix that is described in Microsoft Knowledge Base article 974918.</span></span> <span data-ttu-id="10e42-171">必须使用客户端操作系统;MED-V 管理控制台无法在与 MED-V 服务器相同的系统上运行。</span><span class="sxs-lookup"><span data-stu-id="10e42-171">A client operating system must be used; the MED-V management console cannot run on the same system as the MED-V server.</span></span>

<span data-ttu-id="10e42-172">不能与多个 MED-V 服务器实例共享管理控制台。</span><span class="sxs-lookup"><span data-stu-id="10e42-172">You cannot share a management console with multiple MED-V server instances.</span></span> <span data-ttu-id="10e42-173">MED-V 服务器的地址是在安装管理控制台的 MED-V 客户端期间指定的;这可以在安装后进行更改，但在任何时候，管理控制台只能使用单个 MED-V 服务器。</span><span class="sxs-lookup"><span data-stu-id="10e42-173">The address of the MED-V server is specified during the installation of the management console’s MED-V client; this can be changed after installation, but at any time the management console can only work with a single MED-V server.</span></span>

<span data-ttu-id="10e42-174">你可以将多个管理控制台与单个 MED-V 服务器配合使用。</span><span class="sxs-lookup"><span data-stu-id="10e42-174">You can use multiple management consoles with a single MED-V server.</span></span> <span data-ttu-id="10e42-175">为避免冲突，有一种机制可用，可在一个控制台对 MED-V 工作区进行更改时通知其他控制台用户。</span><span class="sxs-lookup"><span data-stu-id="10e42-175">To avoid conflicts, a mechanism is available that notifies other console users when one console has made changes to a MED-V workspace.</span></span>

<span data-ttu-id="10e42-176">对于每个 MED-V 实例，确定需要多少个管理控制台和放置它们的位置。</span><span class="sxs-lookup"><span data-stu-id="10e42-176">For each MED-V instance, determine how many management consoles will be needed and where they will be placed.</span></span> <span data-ttu-id="10e42-177">选择要用于管理控制台的典型 MED-V 客户端外形规格。</span><span class="sxs-lookup"><span data-stu-id="10e42-177">Select a typical MED-V client form factor to be used for the management console.</span></span>

## <span data-ttu-id="10e42-178">相关主题</span><span class="sxs-lookup"><span data-stu-id="10e42-178">Related topics</span></span>


[<span data-ttu-id="10e42-179">MED-V 1.0 SP1 支持的配置</span><span class="sxs-lookup"><span data-stu-id="10e42-179">MED-V 1.0 SP1 Supported Configurations</span></span>](med-v-10-sp1-supported-configurationsmedv-10-sp1.md)

[<span data-ttu-id="10e42-180">将 MED-V 服务器配置为群集模式</span><span class="sxs-lookup"><span data-stu-id="10e42-180">Configuring MED-V Server for Cluster Mode</span></span>](configuring-med-v-server-for-cluster-mode.md)

[<span data-ttu-id="10e42-181">如何安装 MED-V 客户端和 MED-V 管理控制台</span><span class="sxs-lookup"><span data-stu-id="10e42-181">How to Install MED-V Client and MED-V Management Console</span></span>](how-to-install-med-v-client-and-med-v-management-console.md)

[<span data-ttu-id="10e42-182">使用 MED-V 管理控制台用户界面</span><span class="sxs-lookup"><span data-stu-id="10e42-182">Using the MED-V Management Console User Interface</span></span>](using-the-med-v-management-console-user-interface.md)

 

 





