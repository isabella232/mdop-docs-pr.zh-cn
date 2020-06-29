---
title: 使用 App-V 5.1 Client Management Console
description: 使用 App-V 5.1 Client Management Console
author: dansimp
ms.assetid: be6d4e35-5701-4f9a-ba8a-bede12662cf1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 63dd75395cdfef1aebae30b364f77465ba8a9882
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798250"
---
# <span data-ttu-id="bd3b3-103">使用 App-V 5.1 Client Management Console</span><span class="sxs-lookup"><span data-stu-id="bd3b3-103">Using the App-V 5.1 Client Management Console</span></span>


<span data-ttu-id="bd3b3-104">本主题提供有关如何配置和管理 Microsoft Application Virtualization （App-v）5.1 客户端的信息。</span><span class="sxs-lookup"><span data-stu-id="bd3b3-104">This topic provides information about how you can configure and manage the Microsoft Application Virtualization (App-V) 5.1 client.</span></span>

## <span data-ttu-id="bd3b3-105">修改 App-v 5.1 客户端配置</span><span class="sxs-lookup"><span data-stu-id="bd3b3-105">Modify App-V 5.1 client configuration</span></span>


<span data-ttu-id="bd3b3-106">App-v 5.1 客户端具有相关设置，可配置这些设置以确定客户端在你的环境中的运行方式。</span><span class="sxs-lookup"><span data-stu-id="bd3b3-106">The App-V 5.1 client has associated settings that can be configured to determine how the client will run in your environment.</span></span> <span data-ttu-id="bd3b3-107">可以在运行客户端的计算机上管理这些设置，也可以使用 PowerShell 或组策略管理这些设置。</span><span class="sxs-lookup"><span data-stu-id="bd3b3-107">You can manage these settings on the computer that runs the client or by using PowerShell or Group Policy.</span></span> <span data-ttu-id="bd3b3-108">有关如何使用 PowerShell 或组策略配置修改客户端的详细信息，请参阅[如何使用 Powershell 修改客户端配置](how-to-modify-client-configuration-by-using-powershell51.md)。</span><span class="sxs-lookup"><span data-stu-id="bd3b3-108">For more information about how to modify the client using PowerShell or Group Policy configuration see, [How to Modify Client Configuration by Using PowerShell](how-to-modify-client-configuration-by-using-powershell51.md).</span></span>

## <a href="" id="the-app-v-5-1-client-management-console-"></a><span data-ttu-id="bd3b3-109">App-v 5.1 客户端管理控制台</span><span class="sxs-lookup"><span data-stu-id="bd3b3-109">The App-V 5.1 client management console</span></span>


<span data-ttu-id="bd3b3-110">你可以获取有关 App-v 5.1 客户端的信息，或使用 App-v 5.1 客户端管理控制台执行特定任务。</span><span class="sxs-lookup"><span data-stu-id="bd3b3-110">You can obtain information about the App-V 5.1 client or perform specific tasks by using the App-V 5.1 client management console.</span></span> <span data-ttu-id="bd3b3-111">可以在客户端管理控制台中执行的许多任务也可以使用 PowerShell 执行。</span><span class="sxs-lookup"><span data-stu-id="bd3b3-111">Many of the tasks that you can perform in the client management console you can also perform by using PowerShell.</span></span> <span data-ttu-id="bd3b3-112">下表中还显示了每个操作的关联 PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bd3b3-112">The associated PowerShell cmdlets for each action are also displayed in the following table.</span></span> <span data-ttu-id="bd3b3-113">有关如何使用 PowerShell 的详细信息，请参阅[使用 Powershell 管理 app-v 5.1](administering-app-v-51-by-using-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="bd3b3-113">For more information about how to use PowerShell, see [Administering App-V 5.1 by Using PowerShell](administering-app-v-51-by-using-powershell.md).</span></span>

<span data-ttu-id="bd3b3-114">客户端管理控制台包含以下所述的主选项卡。</span><span class="sxs-lookup"><span data-stu-id="bd3b3-114">The client management console contains the following described main tabs.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bd3b3-115">选项卡</span><span class="sxs-lookup"><span data-stu-id="bd3b3-115">Tab</span></span></th>
<th align="left"><span data-ttu-id="bd3b3-116">描述</span><span class="sxs-lookup"><span data-stu-id="bd3b3-116">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bd3b3-117">概述</span><span class="sxs-lookup"><span data-stu-id="bd3b3-117">Overview</span></span></p></td>
<td align="left"><p><span data-ttu-id="bd3b3-118">" <strong> 概述 </strong> " 选项卡包含以下元素：</span><span class="sxs-lookup"><span data-stu-id="bd3b3-118">The <strong>Overview</strong> tab contains the following elements:</span></span></p>
<ul>
<li><p><span data-ttu-id="bd3b3-119">更新-使用 " <strong> 更新" </strong> 磁贴刷新虚拟化的应用程序或接收新的虚拟化程序包。</span><span class="sxs-lookup"><span data-stu-id="bd3b3-119">Update – Use the <strong>Update</strong> tile to refresh a virtualized application or to receive a new virtualized package.</span></span></p>
<p><span data-ttu-id="bd3b3-120"><strong>上次刷新 </strong> 显示虚拟化程序包的当前版本。</span><span class="sxs-lookup"><span data-stu-id="bd3b3-120">The <strong>Last Refresh</strong> displays the current version of the virtualized package.</span></span></p></li>
<li><p><span data-ttu-id="bd3b3-121">下载所有虚拟应用程序-使用 " <strong> 下载 </strong> " 图块下载所有预配到当前用户的程序包。</span><span class="sxs-lookup"><span data-stu-id="bd3b3-121">Download all virtual applications – Use the <strong>Download</strong> tile to download all of the packages provisioned to the current user.</span></span></p>
<p><span data-ttu-id="bd3b3-122">（关联的 PowerShell cmdlet： <strong>Mount-AppvClientPackage </strong> ）</span><span class="sxs-lookup"><span data-stu-id="bd3b3-122">(Associated PowerShell cmdlet: <strong>Mount-AppvClientPackage</strong>)</span></span></p>
<p></p></li>
<li><p><span data-ttu-id="bd3b3-123">脱机工作–使用此磁贴禁止所有自动和手动虚拟应用程序更新。</span><span class="sxs-lookup"><span data-stu-id="bd3b3-123">Work Offline – Use this tile to disallow all automatic and manual virtual application updates.</span></span></p>
<p><span data-ttu-id="bd3b3-124">（关联的 PowerShell cmdlet： <strong>Set-AppvPublishServer-UserRefreshEnabled-GlobalRefreshEnabled </strong> ）</span><span class="sxs-lookup"><span data-stu-id="bd3b3-124">(Associated PowerShell cmdlet: <strong>Set-AppvPublishServer –UserRefreshEnabled –GlobalRefreshEnabled</strong>)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bd3b3-125">虚拟应用</span><span class="sxs-lookup"><span data-stu-id="bd3b3-125">Virtual Apps</span></span></p></td>
<td align="left"><p><span data-ttu-id="bd3b3-126">" <strong> 虚拟应用 </strong> " 选项卡显示已发布给用户的所有程序包。</span><span class="sxs-lookup"><span data-stu-id="bd3b3-126">The <strong>VIRTUAL APPS</strong> tab displays all of the packages that have been published to the user.</span></span> <span data-ttu-id="bd3b3-127">您也可以单击特定程序包，并查看属于该程序包的所有应用程序。</span><span class="sxs-lookup"><span data-stu-id="bd3b3-127">You can also click a specific package and see all of the applications that are part of that package.</span></span> <span data-ttu-id="bd3b3-128">这将显示有关当前正在使用的程序包的信息以及每个程序包已下载到计算机的数量。</span><span class="sxs-lookup"><span data-stu-id="bd3b3-128">This displays information about packages that are currently in use and how much of each package has been downloaded to the computer.</span></span> <span data-ttu-id="bd3b3-129">你还可以启动和停止程序包下载。</span><span class="sxs-lookup"><span data-stu-id="bd3b3-129">You can also start and stop package downloads.</span></span> <span data-ttu-id="bd3b3-130">此外，您可以修复用户状态。</span><span class="sxs-lookup"><span data-stu-id="bd3b3-130">Additionally, you can repair the user state.</span></span> <span data-ttu-id="bd3b3-131">修复操作将删除与程序包相关联的所有用户数据。</span><span class="sxs-lookup"><span data-stu-id="bd3b3-131">A repair will delete all user data that is associated with a package.</span></span></p>
<p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bd3b3-132">应用连接组</span><span class="sxs-lookup"><span data-stu-id="bd3b3-132">App Connection Groups</span></span></p></td>
<td align="left"><p><span data-ttu-id="bd3b3-133">" <strong> 应用连接组" </strong> 选项卡显示当前用户可用的所有连接组。</span><span class="sxs-lookup"><span data-stu-id="bd3b3-133">The <strong>APP CONNECTION GROUPS</strong> tab displays all of the connection groups that are available to the current user.</span></span> <span data-ttu-id="bd3b3-134">单击特定的连接组以查看属于所选组的所有程序包。</span><span class="sxs-lookup"><span data-stu-id="bd3b3-134">Click a specific connection group to see all of the packages that are part of the selected group.</span></span> <span data-ttu-id="bd3b3-135">这将显示有关已在使用的连接组的信息以及已下载到计算机的连接组内容的数量。</span><span class="sxs-lookup"><span data-stu-id="bd3b3-135">This displays information about connection groups that are already in use and how much of the connection group contents have been downloaded to the computer.</span></span> <span data-ttu-id="bd3b3-136">此外，你可以启动和停止连接组下载。</span><span class="sxs-lookup"><span data-stu-id="bd3b3-136">Additionally, you can start and stop connection group downloads.</span></span> <span data-ttu-id="bd3b3-137">你可以使用此部分启动修复。</span><span class="sxs-lookup"><span data-stu-id="bd3b3-137">You can use this section to initiate a repair.</span></span> <span data-ttu-id="bd3b3-138">修复操作将删除所有与连接组相关联的用户状态。</span><span class="sxs-lookup"><span data-stu-id="bd3b3-138">A repair will remove all of the user state that is associated a connection group.</span></span></p>
<p><span data-ttu-id="bd3b3-139">（关联的 PowerShell cmdlet：下载- <strong>装载-AppvClientConnectionGroup </strong> 。</span><span class="sxs-lookup"><span data-stu-id="bd3b3-139">(Associated PowerShell cmdlets: Download - <strong>Mount-AppvClientConnectionGroup</strong>.</span></span> <span data-ttu-id="bd3b3-140">修复- <strong> AppvClientConnectionGroup </strong> 。）</span><span class="sxs-lookup"><span data-stu-id="bd3b3-140">Repair -<strong>AppvClientConnectionGroup</strong>.)</span></span></p>
<p></p></td>
</tr>
</tbody>
</table>

 

[<span data-ttu-id="bd3b3-141">如何访问 Client Management Console</span><span class="sxs-lookup"><span data-stu-id="bd3b3-141">How to Access the Client Management Console</span></span>](how-to-access-the-client-management-console51.md)

[<span data-ttu-id="bd3b3-142">如何将 Client 配置为从发布服务器接收程序包和连接组更新</span><span class="sxs-lookup"><span data-stu-id="bd3b3-142">How to Configure the Client to Receive Package and Connection Groups Updates From the Publishing Server</span></span>](how-to-configure-the-client-to-receive-package-and-connection-groups-updates-from-the-publishing-server-51.md)






## <span data-ttu-id="bd3b3-143">相关主题</span><span class="sxs-lookup"><span data-stu-id="bd3b3-143">Related topics</span></span>


[<span data-ttu-id="bd3b3-144">App-V 5.1 的操作</span><span class="sxs-lookup"><span data-stu-id="bd3b3-144">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

 

 





