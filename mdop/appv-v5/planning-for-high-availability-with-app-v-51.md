---
title: 计划 App-V 5.1 的高可用性
description: 计划 App-V 5.1 的高可用性
author: dansimp
ms.assetid: 1f190a0e-10ee-4fbe-a602-7e807e943033
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 5c8e0e684051859a4caa2c4ef983c040295bc6d4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798306"
---
# <span data-ttu-id="7ce08-103">计划 App-V 5.1 的高可用性</span><span class="sxs-lookup"><span data-stu-id="7ce08-103">Planning for High Availability with App-V 5.1</span></span>


<span data-ttu-id="7ce08-104">Microsoft Application Virtualization （App-v）5.1 系统配置可以利用维护高级别可用服务的选项。</span><span class="sxs-lookup"><span data-stu-id="7ce08-104">Microsoft Application Virtualization (App-V) 5.1 system configurations can take advantage of options that maintain a high level of available service.</span></span>

<span data-ttu-id="7ce08-105">使用以下部分中的信息帮助你了解在高可用性配置中部署 app-v 5.1 的选项。</span><span class="sxs-lookup"><span data-stu-id="7ce08-105">Use the information in the following sections to help you understand the options to deploy App-V 5.1 in a highly available configuration.</span></span>

-   [<span data-ttu-id="7ce08-106">Microsoft SQL Server 群集支持</span><span class="sxs-lookup"><span data-stu-id="7ce08-106">Support for Microsoft SQL Server clustering</span></span>](#bkmk-sqlcluster)

-   [<span data-ttu-id="7ce08-107">对 IIS 网络负载平衡的支持</span><span class="sxs-lookup"><span data-stu-id="7ce08-107">Support for IIS Network Load Balancing</span></span>](#bkmk-iisloadbal)

-   [<span data-ttu-id="7ce08-108">在运行（SCS）模式时支持群集文件服务器</span><span class="sxs-lookup"><span data-stu-id="7ce08-108">Support for clustered file servers when running (SCS) mode</span></span>](#bkmk-clusterscsmode)

-   [<span data-ttu-id="7ce08-109">Microsoft SQL Server 镜像支持</span><span class="sxs-lookup"><span data-stu-id="7ce08-109">Support for Microsoft SQL Server Mirroring</span></span>](#bkmk-sqlmirroring)

-   [<span data-ttu-id="7ce08-110">Microsoft SQL Server 始终支持的支持</span><span class="sxs-lookup"><span data-stu-id="7ce08-110">Support for Microsoft SQL Server Always On</span></span>](#bkmk-sqlalwayson)

## <a href="" id="bkmk-sqlcluster"></a><span data-ttu-id="7ce08-111">Microsoft SQL Server 群集支持</span><span class="sxs-lookup"><span data-stu-id="7ce08-111">Support for Microsoft SQL Server clustering</span></span>


<span data-ttu-id="7ce08-112">你可以在运行 Microsoft SQL Server 群集的计算机上运行 App-v 管理数据库和报告数据库。</span><span class="sxs-lookup"><span data-stu-id="7ce08-112">You can run the App-V Management database and Reporting database on computers that are running Microsoft SQL Server clusters.</span></span> <span data-ttu-id="7ce08-113">但是，必须使用脚本安装数据库。</span><span class="sxs-lookup"><span data-stu-id="7ce08-113">However, you must install the databases using scripts.</span></span>

<span data-ttu-id="7ce08-114">有关说明，请参阅[如何使用 SQL 脚本部署 App-v 数据库](how-to-deploy-the-app-v-databases-by-using-sql-scripts51.md)。</span><span class="sxs-lookup"><span data-stu-id="7ce08-114">For instructions, see [How to Deploy the App-V Databases by Using SQL Scripts](how-to-deploy-the-app-v-databases-by-using-sql-scripts51.md).</span></span>

## <a href="" id="bkmk-iisloadbal"></a><span data-ttu-id="7ce08-115">对 IIS 网络负载平衡的支持</span><span class="sxs-lookup"><span data-stu-id="7ce08-115">Support for IIS Network Load Balancing</span></span>


<span data-ttu-id="7ce08-116">你可以使用 Internet 信息服务（IIS）网络负载平衡为运行 app-v 5 a.x 管理、发布和报告服务（通过 IIS 部署）的计算机配置高可用环境。</span><span class="sxs-lookup"><span data-stu-id="7ce08-116">You can use Internet Information Services (IIS) Network Load Balancing to configure a highly available environment for computers running the App-V 5.x Management, Publishing, and Reporting services which are deployed through IIS.</span></span>

<span data-ttu-id="7ce08-117">有关为运行 Windows Server 操作系统的计算机配置 IIS 和网络负载平衡的详细信息，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="7ce08-117">Review the following for more information about configuring IIS and Network Load Balancing for computers running Windows Server operating systems:</span></span>

-   <span data-ttu-id="7ce08-118">提供有关配置 Internet Information Services （IIS）7.0 的信息。</span><span class="sxs-lookup"><span data-stu-id="7ce08-118">Provides information about configuring Internet Information Services (IIS) 7.0.</span></span>

    <span data-ttu-id="7ce08-119">[获得高可用性和可伸缩性-ARR 和 NLB](https://go.microsoft.com/fwlink/?LinkId=316369) （https://go.microsoft.com/fwlink/?LinkId=316369)</span><span class="sxs-lookup"><span data-stu-id="7ce08-119">[Achieving High Availability and Scalability - ARR and NLB](https://go.microsoft.com/fwlink/?LinkId=316369) (https://go.microsoft.com/fwlink/?LinkId=316369)</span></span>

-   <span data-ttu-id="7ce08-120">配置 Microsoft Windows Server</span><span class="sxs-lookup"><span data-stu-id="7ce08-120">Configuring Microsoft Windows Server</span></span>

    <span data-ttu-id="7ce08-121">[网络负载平衡](https://go.microsoft.com/fwlink/?LinkId=316370)（ https://go.microsoft.com/fwlink/?LinkId=316370) 。</span><span class="sxs-lookup"><span data-stu-id="7ce08-121">[Network Load Balancing](https://go.microsoft.com/fwlink/?LinkId=316370) (https://go.microsoft.com/fwlink/?LinkId=316370).</span></span>

    <span data-ttu-id="7ce08-122">此信息还适用于 Windows Server2008、Windows Server2008R2 或 Windows Server2012 中的 IIS 网络负载平衡（NLB）群集。</span><span class="sxs-lookup"><span data-stu-id="7ce08-122">This information also applies to IIS Network Load Balancing (NLB) clusters in Windows Server2008, Windows Server2008R2, or Windows Server2012.</span></span>

    <span data-ttu-id="7ce08-123">**注意** Windows Server2012 中的 IIS 网络负载平衡功能通常与 Windows Server2008R2 中的功能相同。</span><span class="sxs-lookup"><span data-stu-id="7ce08-123">**Note** The IIS Network Load Balancing functionality in Windows Server2012 is generally the same as in Windows Server2008R2.</span></span> <span data-ttu-id="7ce08-124">但是，在 Windows Server2012 中更改了一些任务的详细信息。</span><span class="sxs-lookup"><span data-stu-id="7ce08-124">However, some task details are changed in Windows Server2012.</span></span> <span data-ttu-id="7ce08-125">有关执行任务的新方法的信息，请参阅[Windows server 2012 R2 预览版和 Windows server 2012 （）中的常见管理任务和导航](https://go.microsoft.com/fwlink/?LinkId=316371) https://go.microsoft.com/fwlink/?LinkId=316371) 。</span><span class="sxs-lookup"><span data-stu-id="7ce08-125">For information on new ways to do tasks, see [Common Management Tasks and Navigation in Windows Server 2012 R2 Preview and Windows Server 2012](https://go.microsoft.com/fwlink/?LinkId=316371) (https://go.microsoft.com/fwlink/?LinkId=316371).</span></span>

     

## <a href="" id="bkmk-clusterscsmode"></a><span data-ttu-id="7ce08-126">在运行（SCS）模式时支持群集文件服务器</span><span class="sxs-lookup"><span data-stu-id="7ce08-126">Support for clustered file servers when running (SCS) mode</span></span>


<span data-ttu-id="7ce08-127">支持在群集文件服务器的共享内容存储（SCS）模式下运行 app-v 5.1。</span><span class="sxs-lookup"><span data-stu-id="7ce08-127">Running App-V 5.1 in Share Content Store (SCS) mode with clustered file servers is supported.</span></span>

<span data-ttu-id="7ce08-128">以下步骤可用于启用此配置：</span><span class="sxs-lookup"><span data-stu-id="7ce08-128">The following steps can be used to enable this configuration:</span></span>

-   <span data-ttu-id="7ce08-129">将 app-v 5.1 配置为在客户端 SCS 模式下运行。</span><span class="sxs-lookup"><span data-stu-id="7ce08-129">Configure App-V 5.1 to run in client SCS mode.</span></span> <span data-ttu-id="7ce08-130">有关配置 App-v 5.1 SCS 模式的详细信息，请参阅[如何为共享内容存储模式安装 app-v 5.1 客户端](how-to-install-the-app-v-51-client-for-shared-content-store-mode.md)。</span><span class="sxs-lookup"><span data-stu-id="7ce08-130">For more information about configuring App-V 5.1 SCS mode, see [How to Install the App-V 5.1 Client for Shared Content Store Mode](how-to-install-the-app-v-51-client-for-shared-content-store-mode.md).</span></span>

-   <span data-ttu-id="7ce08-131">使用虚拟 SAN 配置在 Microsoft Server2012 横向扩展模式和预**2012**模式下配置的文件服务器群集。</span><span class="sxs-lookup"><span data-stu-id="7ce08-131">Configure the file server cluster configured in both the Microsoft Server2012 scale out mode and pre **2012** mode with a virtual SAN.</span></span>

<span data-ttu-id="7ce08-132">以下步骤可用于验证配置：</span><span class="sxs-lookup"><span data-stu-id="7ce08-132">The following steps can be used to validate the configuration:</span></span>

1.  <span data-ttu-id="7ce08-133">在发布服务器上添加程序包。</span><span class="sxs-lookup"><span data-stu-id="7ce08-133">Add a package on the publishing server.</span></span> <span data-ttu-id="7ce08-134">有关添加程序包的详细信息，请参阅[如何使用管理控制台添加或升级程序包](how-to-add-or-upgrade-packages-by-using-the-management-console-51-gb18030.md)。</span><span class="sxs-lookup"><span data-stu-id="7ce08-134">For more information about adding a package, see [How to Add or Upgrade Packages by Using the Management Console](how-to-add-or-upgrade-packages-by-using-the-management-console-51-gb18030.md).</span></span>

2.  <span data-ttu-id="7ce08-135">在运行 App-v 5.1 客户端的计算机上执行发布刷新，然后打开一个应用程序。</span><span class="sxs-lookup"><span data-stu-id="7ce08-135">Perform a publishing refresh on the computer running the App-V 5.1 client and open an application.</span></span>

3.  <span data-ttu-id="7ce08-136">切换群集节点中的 "发布更新" 和 "中流"，以确保故障转移正常工作。</span><span class="sxs-lookup"><span data-stu-id="7ce08-136">Switch cluster nodes mid-publishing refresh and mid-streaming to ensure fail-over works correctly.</span></span>

<span data-ttu-id="7ce08-137">有关配置 Windows Server 故障转移群集的详细信息，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="7ce08-137">Review the following for more information about configuring Windows Server Failover clusters:</span></span>

-   <span data-ttu-id="7ce08-138">[清单：创建群集文件服务器](https://go.microsoft.com/fwlink/?LinkId=316372)（ https://go.microsoft.com/fwlink/?LinkId=316372) 。</span><span class="sxs-lookup"><span data-stu-id="7ce08-138">[Checklist: Create a Clustered File Server](https://go.microsoft.com/fwlink/?LinkId=316372) (https://go.microsoft.com/fwlink/?LinkId=316372).</span></span>

-   <span data-ttu-id="7ce08-139">[在 Windows Server 2012 故障转移群集中使用群集共享卷](https://go.microsoft.com/fwlink/?LinkId=316373)（ https://go.microsoft.com/fwlink/?LinkId=316373) 。</span><span class="sxs-lookup"><span data-stu-id="7ce08-139">[Use Cluster Shared Volumes in a Windows Server 2012 Failover Cluster](https://go.microsoft.com/fwlink/?LinkId=316373) (https://go.microsoft.com/fwlink/?LinkId=316373).</span></span>

## <a href="" id="bkmk-sqlmirroring"></a><span data-ttu-id="7ce08-140">Microsoft SQL Server 镜像支持</span><span class="sxs-lookup"><span data-stu-id="7ce08-140">Support for Microsoft SQL Server Mirroring</span></span>


<span data-ttu-id="7ce08-141">使用 Microsoft SQL Server 镜像（应用程序 V 5.1 管理服务器数据库是使用两个 SQL Server 实例镜像的），支持 app-v 5.1 管理服务器数据库。</span><span class="sxs-lookup"><span data-stu-id="7ce08-141">Using Microsoft SQL Server mirroring, where the App-V 5.1 management server database is mirrored utilizing two SQL Server instances, for App-V 5.1 management server databases is supported.</span></span>

<span data-ttu-id="7ce08-142">有关配置 Microsoft SQL Server 镜像的详细信息，请查看以下内容：</span><span class="sxs-lookup"><span data-stu-id="7ce08-142">Review the following for more information about configuring Microsoft SQL Server Mirroring:</span></span>

-   <span data-ttu-id="7ce08-143">[如何：准备镜像数据库以进行镜像（transact-sql）](https://go.microsoft.com/fwlink/?LinkId=316375) （https://go.microsoft.com/fwlink/?LinkId=316375)</span><span class="sxs-lookup"><span data-stu-id="7ce08-143">[How to: Prepare a Mirror Database for Mirroring (Transact-SQL)](https://go.microsoft.com/fwlink/?LinkId=316375) (https://go.microsoft.com/fwlink/?LinkId=316375)</span></span>

-   <span data-ttu-id="7ce08-144">[使用 Windows 身份验证（SQL Server Management Studio）建立数据库镜像会话](https://go.microsoft.com/fwlink/?LinkId=316377)（https://go.microsoft.com/fwlink/?LinkId=316377)</span><span class="sxs-lookup"><span data-stu-id="7ce08-144">[Establish a Database Mirroring Session Using Windows Authentication (SQL Server Management Studio)](https://go.microsoft.com/fwlink/?LinkId=316377) (https://go.microsoft.com/fwlink/?LinkId=316377)</span></span>

<span data-ttu-id="7ce08-145">以下步骤可用于验证配置：</span><span class="sxs-lookup"><span data-stu-id="7ce08-145">The following steps can be used to validate the configuration:</span></span>

1.  <span data-ttu-id="7ce08-146">启动 Microsoft SQL Server 镜像会话。</span><span class="sxs-lookup"><span data-stu-id="7ce08-146">Initiate a Microsoft SQL Server Mirroring session.</span></span>

2.  <span data-ttu-id="7ce08-147">选择 "**故障转移**" 以指定新的主 Microsoft SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="7ce08-147">Select **Failover** to designate a new master Microsoft SQL Server instance.</span></span>

3.  <span data-ttu-id="7ce08-148">验证在故障转移后，app-v 5.1 管理服务器是否继续正常工作。</span><span class="sxs-lookup"><span data-stu-id="7ce08-148">Verify that the App-V 5.1 management server continues to function as expected after the failover.</span></span>

<span data-ttu-id="7ce08-149">可以修改管理服务器上的连接字符串，以包括\*\*故障转移合作伙伴 = &lt; server2 &gt; \*\*。</span><span class="sxs-lookup"><span data-stu-id="7ce08-149">The connection string on the management server can be modified to include **failover partner = &lt;server2&gt;**.</span></span> <span data-ttu-id="7ce08-150">这仅有助于当镜像的主映像故障转移到辅助设备，并且运行 App-V 5.1 客户端的计算机执行全新连接时（如重启后）。</span><span class="sxs-lookup"><span data-stu-id="7ce08-150">This will only help when the primary on the mirror has failed over to the secondary and the computer running the App-V 5.1 client is doing a fresh connection (say after reboot).</span></span>

<span data-ttu-id="7ce08-151">使用以下步骤修改连接字符串以包括\*\*故障转移合作伙伴 = &lt; server2 &gt; \*\*：</span><span class="sxs-lookup"><span data-stu-id="7ce08-151">Use the following steps to modify the connection string to include **failover partner = &lt;server2&gt;**:</span></span>

<span data-ttu-id="7ce08-152">**重要提示** 本主题介绍如何使用注册表编辑器更改 Windows 注册表。</span><span class="sxs-lookup"><span data-stu-id="7ce08-152">**Important** This topic describes how to change the Windows registry by using Registry Editor.</span></span> <span data-ttu-id="7ce08-153">如果不正确地更改 Windows 注册表，则可能会导致严重问题，可能需要重新安装 Windows。</span><span class="sxs-lookup"><span data-stu-id="7ce08-153">If you change the Windows registry incorrectly, you can cause serious problems that might require you to reinstall Windows.</span></span> <span data-ttu-id="7ce08-154">在更改注册表之前，应创建注册表文件（.dat 和 .dat）的备份副本。</span><span class="sxs-lookup"><span data-stu-id="7ce08-154">You should make a backup copy of the registry files (System.dat and User.dat) before you change the registry.</span></span> <span data-ttu-id="7ce08-155">Microsoft 无法保证更改注册表时可能出现的问题可以解决。</span><span class="sxs-lookup"><span data-stu-id="7ce08-155">Microsoft cannot guarantee that the problems that might occur when you change the registry can be resolved.</span></span> <span data-ttu-id="7ce08-156">更改注册表的风险由您自己承担。</span><span class="sxs-lookup"><span data-stu-id="7ce08-156">Change the registry at your own risk.</span></span>

 

1.  <span data-ttu-id="7ce08-157">登录管理服务器，然后打开**注册表编辑器**。</span><span class="sxs-lookup"><span data-stu-id="7ce08-157">Login to the management server and open **regedit**.</span></span>

2.  <span data-ttu-id="7ce08-158">导航到**HKEY \ _LOCAL \ _MACHINE**  \\  **软件**  \\  **Microsoft**  \\  **AppV**  \\  **Server**  \\  **ManagementService**。</span><span class="sxs-lookup"><span data-stu-id="7ce08-158">Navigate to **HKEY\_LOCAL\_MACHINE** \\ **Software** \\ **Microsoft** \\ **AppV** \\ **Server** \\ **ManagementService**.</span></span>

3.  <span data-ttu-id="7ce08-159">通过 "**故障转移合作伙伴 = &lt; &gt; Server2**" 修改**管理 \ _SQL \ _CONNECTION \ _STRING**值。</span><span class="sxs-lookup"><span data-stu-id="7ce08-159">Modify the **MANAGEMENT\_SQL\_CONNECTION\_STRING** value with the **failover partner = &lt;server2&gt;**.</span></span>

4.  <span data-ttu-id="7ce08-160">使用 IIS 控制台重新启动管理服务。</span><span class="sxs-lookup"><span data-stu-id="7ce08-160">Restart management service using the IIS console.</span></span>

    <span data-ttu-id="7ce08-161">**注意** 由于 Microsoft sql Server 2012 提供了**AlwaysOn**功能，因此数据库镜像位于 Microsoft sql Server2012 的过时数据库引擎功能列表中。</span><span class="sxs-lookup"><span data-stu-id="7ce08-161">**Note** Database Mirroring is on the list of Deprecated Database Engine Features for Microsoft SQL Server2012 due to the **AlwaysOn** feature available with Microsoft SQL Server 2012.</span></span>

     

<span data-ttu-id="7ce08-162">有关详细信息，请单击以下任一链接：</span><span class="sxs-lookup"><span data-stu-id="7ce08-162">Click any of the following links for more information:</span></span>

-   <span data-ttu-id="7ce08-163">[如何：准备镜像数据库以进行镜像（transact-sql）](https://go.microsoft.com/fwlink/?LinkId=394235) （ https://go.microsoft.com/fwlink/?LinkId=394235) 。</span><span class="sxs-lookup"><span data-stu-id="7ce08-163">[How to: Prepare a Mirror Database for Mirroring (Transact-SQL)](https://go.microsoft.com/fwlink/?LinkId=394235) (https://go.microsoft.com/fwlink/?LinkId=394235).</span></span>

-   <span data-ttu-id="7ce08-164">[如何：配置数据库镜像会话（SQL Server Management Studio）](https://go.microsoft.com/fwlink/?LinkId=394236) （ https://go.microsoft.com/fwlink/?LinkId=394236) 。</span><span class="sxs-lookup"><span data-stu-id="7ce08-164">[How to: Configure a Database Mirroring Session (SQL Server Management Studio)](https://go.microsoft.com/fwlink/?LinkId=394236) (https://go.microsoft.com/fwlink/?LinkId=394236).</span></span>

-   <span data-ttu-id="7ce08-165">[使用 Windows 身份验证（SQL Server Management Studio）（即 SQL Server Management Studio）建立数据库镜像会话](https://go.microsoft.com/fwlink/?LinkId=394237) https://go.microsoft.com/fwlink/?LinkId=394237) 。</span><span class="sxs-lookup"><span data-stu-id="7ce08-165">[Establish a Database Mirroring Session Using Windows Authentication (SQL Server Management Studio)](https://go.microsoft.com/fwlink/?LinkId=394237) (https://go.microsoft.com/fwlink/?LinkId=394237).</span></span>

-   <span data-ttu-id="7ce08-166">[SQL Server 2012 中已过时的数据库引擎功能](https://go.microsoft.com/fwlink/?LinkId=394238)（ https://go.microsoft.com/fwlink/?LinkId=394238) 。</span><span class="sxs-lookup"><span data-stu-id="7ce08-166">[Deprecated Database Engine Features in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=394238) (https://go.microsoft.com/fwlink/?LinkId=394238).</span></span>

## <a href="" id="bkmk-sqlalwayson"></a><span data-ttu-id="7ce08-167">对 Microsoft SQL Server 的支持始终在配置上</span><span class="sxs-lookup"><span data-stu-id="7ce08-167">Support for Microsoft SQL Server Always On configuration</span></span>


<span data-ttu-id="7ce08-168">App-v 5.1 管理服务器数据库支持通过 "**始终启用**" 配置对运行 Microsoft SQL server 的计算机进行部署。</span><span class="sxs-lookup"><span data-stu-id="7ce08-168">The App-V 5.1 management server database supports deployments to computers running Microsoft SQL Server with the **Always On** configuration.</span></span>






## <span data-ttu-id="7ce08-169">相关主题</span><span class="sxs-lookup"><span data-stu-id="7ce08-169">Related topics</span></span>


[<span data-ttu-id="7ce08-170">计划部署 App-V</span><span class="sxs-lookup"><span data-stu-id="7ce08-170">Planning to Deploy App-V</span></span>](planning-to-deploy-app-v51.md)

 

 





