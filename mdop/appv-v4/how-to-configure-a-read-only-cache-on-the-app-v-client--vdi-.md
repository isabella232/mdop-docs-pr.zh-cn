---
title: 如何在 App-V Client (VDI) 上配置只读缓存
description: 如何在 App-V Client (VDI) 上配置只读缓存
author: dansimp
ms.assetid: 7a41e017-9e23-4a6a-a659-04d23f008b83
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 114f9dfbf55a3f62b6bc8bec6b37a659ffbfaf56
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801619"
---
# <span data-ttu-id="55695-103">如何在 App-V Client (VDI) 上配置只读缓存</span><span class="sxs-lookup"><span data-stu-id="55695-103">How to Configure a Read-only Cache on the App-V Client (VDI)</span></span>


<span data-ttu-id="55695-104">在 Microsoft Application Virtualization （App-v）4.6 中，客户端支持使用共享的只读缓存。</span><span class="sxs-lookup"><span data-stu-id="55695-104">In Microsoft Application Virtualization (App-V) 4.6 the Client supports using a shared read-only cache.</span></span> <span data-ttu-id="55695-105">共享的只读缓存使客户能够在虚拟桌面基础结构（VDI）系统中高效使用磁盘空间，用户在其中运行在数据中心服务器环境中托管的虚拟机（VM）上的应用程序，并在存储区域网络（SAN）上共享网络存储。</span><span class="sxs-lookup"><span data-stu-id="55695-105">The shared read-only cache enables the Client to use disk space efficiently in a Virtual Desktop Infrastructure (VDI) system, where users run applications on Virtual Machines (VM) that are hosted in a data center server environment and share network storage on a Storage Area Network (SAN).</span></span> <span data-ttu-id="55695-106">以下过程概述了在任一主 VDI 体系结构（称为 "共用 VM" 或 "静态 VM"）中实现 App-v 客户端所需的过程。</span><span class="sxs-lookup"><span data-stu-id="55695-106">The following procedures provide an overview of the process that is required to implement the App-V Client in either of the primary VDI architectures, known as “Pooled VM” or “Static VM”.</span></span> <span data-ttu-id="55695-107">假定你熟悉 App V 系统及其组件的计划、部署和操作，以及 VDI 服务器的操作和管理。）。</span><span class="sxs-lookup"><span data-stu-id="55695-107">It is assumed that you are familiar with the planning, deployment, and operation of the App-V system and its components, and also the operation and management of the VDI server.</span></span> <span data-ttu-id="55695-108">有关 App-v 的详细信息，请参阅[应用程序虚拟化](https://go.microsoft.com/fwlink/?LinkId=122939)（https://go.microsoft.com/fwlink/?LinkId=122939)</span><span class="sxs-lookup"><span data-stu-id="55695-108">For more information about App-V, see [Application Virtualization](https://go.microsoft.com/fwlink/?LinkId=122939) (https://go.microsoft.com/fwlink/?LinkId=122939)</span></span>

<span data-ttu-id="55695-109">**注意** 这些过程中概述的详细信息仅用作示例。</span><span class="sxs-lookup"><span data-stu-id="55695-109">**Note** The details outlined in these procedures are intended as examples only.</span></span> <span data-ttu-id="55695-110">你可以使用不同的方法来完成整个过程。</span><span class="sxs-lookup"><span data-stu-id="55695-110">You might use different methods to complete the overall process.</span></span>

 

## <span data-ttu-id="55695-111">在 VDI 方案中部署 app-v 客户端</span><span class="sxs-lookup"><span data-stu-id="55695-111">Deploying the App-V Client in a VDI Scenario</span></span>


<span data-ttu-id="55695-112">你可以使用已填充所有用户所需的所有应用程序的共享只读缓存，在 VDI 方案中部署 app-v 客户端。</span><span class="sxs-lookup"><span data-stu-id="55695-112">You can deploy the App-V Client in a VDI scenario by using a shared read-only cache that has been populated with all the applications required for all users.</span></span> <span data-ttu-id="55695-113">然后，配置 VDI 主 VM 映像，以便所有 App-v 客户端都使用相同的缓存文件。</span><span class="sxs-lookup"><span data-stu-id="55695-113">You then configure the VDI Master VM Image so that all the App-V Clients use the same cache file.</span></span> <span data-ttu-id="55695-114">用户通过使用 App-v 发布过程向用户授予对特定应用程序的访问权限。</span><span class="sxs-lookup"><span data-stu-id="55695-114">Users are granted access to specific applications by using the App-V publishing process.</span></span> <span data-ttu-id="55695-115">由于缓存已预加载了所有应用程序，因此当用户启动应用程序时，不会发生流。</span><span class="sxs-lookup"><span data-stu-id="55695-115">Since the cache is already preloaded with all applications, no streaming occurs when a user starts an application.</span></span> <span data-ttu-id="55695-116">但是，用于预填充缓存的程序包必须放置在支持实时流协议（RTSP）流的 app-v 服务器上，并且授予对 App-v 客户端的访问权限。</span><span class="sxs-lookup"><span data-stu-id="55695-116">However, the packages used to prepopulate the cache must be put on an App-V server that supports Real Time Streaming Protocol (RTSP) streaming and that grants access permissions to the App-V Clients.</span></span> <span data-ttu-id="55695-117">如果使用 App-v 管理服务器发布应用程序，则可以使用它来提供此流函数。</span><span class="sxs-lookup"><span data-stu-id="55695-117">If you publish the applications by using an App-V Management Server, you can use it to provide this streaming function.</span></span>

<span data-ttu-id="55695-118">部署过程由四个主要任务组成：</span><span class="sxs-lookup"><span data-stu-id="55695-118">The deployment process consists of four primary tasks:</span></span>

-   <span data-ttu-id="55695-119">创建和填充主共享缓存文件</span><span class="sxs-lookup"><span data-stu-id="55695-119">Creating and populating the master shared cache file</span></span>

-   <span data-ttu-id="55695-120">将共享缓存文件复制到 VDI 服务器存储</span><span class="sxs-lookup"><span data-stu-id="55695-120">Copying the shared cache file to the VDI server storage</span></span>

-   <span data-ttu-id="55695-121">在 VDI 主映像上配置 App-v 客户端软件</span><span class="sxs-lookup"><span data-stu-id="55695-121">Configuring the App-V client software on the VDI Master Image</span></span>

-   <span data-ttu-id="55695-122">在初始部署后管理共享缓存文件的更新部署周期</span><span class="sxs-lookup"><span data-stu-id="55695-122">Managing the update deployment cycle for the shared cache file after the initial deployment</span></span>

<span data-ttu-id="55695-123">这些任务需要仔细规划。</span><span class="sxs-lookup"><span data-stu-id="55695-123">These tasks require careful planning.</span></span> <span data-ttu-id="55695-124">我们建议你为你的组织准备并记录可重复执行的流程。</span><span class="sxs-lookup"><span data-stu-id="55695-124">We recommend that you prepare and document a methodical, reproducible process for your organization to follow.</span></span> <span data-ttu-id="55695-125">这对于主共享缓存文件的初始准备和部署尤其重要，对于应用程序更新，每个更新都需要更新主共享缓存。</span><span class="sxs-lookup"><span data-stu-id="55695-125">This is especially important for the initial preparation and deployment of the master shared cache file, and for the on-going management of application updates, each of which require an update to the master shared cache.</span></span> <span data-ttu-id="55695-126">使用以下过程完成这些主要任务。</span><span class="sxs-lookup"><span data-stu-id="55695-126">Use the following procedures to complete these primary tasks.</span></span>

<span data-ttu-id="55695-127">**注意** 虽然你可以使用多种不同的方法发布应用程序，但以下过程基于用于发布的 app-v 管理服务器的使用。</span><span class="sxs-lookup"><span data-stu-id="55695-127">**Note** Although you can publish the applications by using several different methods, the following procedures are based on the use of an App-V Management Server for publishing.</span></span>

 

**<span data-ttu-id="55695-128">在池中的 VM VDI 或静态 VM VDI 方案中配置初始部署的只读缓存</span><span class="sxs-lookup"><span data-stu-id="55695-128">To configure the read-only cache for initial deployment in a Pooled VM VDI or Static VM VDI scenario</span></span>**

1. <span data-ttu-id="55695-129">在 VDI 服务器上的 VM 中设置和配置 app-v 管理服务器，以提供用户身份验证和发布支持。</span><span class="sxs-lookup"><span data-stu-id="55695-129">Set up and configure an App-V Management Server in a VM on the VDI server to provide user authentication and publishing support.</span></span>

2. <span data-ttu-id="55695-130">将此管理服务器的内容文件夹填充给所有用户所需的所有应用程序包。</span><span class="sxs-lookup"><span data-stu-id="55695-130">Populate the Content folder of this Management Server with all the application packages required for all users.</span></span>

3. <span data-ttu-id="55695-131">设置已安装 App-v 客户端的暂存计算机。</span><span class="sxs-lookup"><span data-stu-id="55695-131">Set up a staging computer that has the App-V Client installed.</span></span> <span data-ttu-id="55695-132">使用具有对所有应用程序的访问权限的帐户登录到暂存计算机，以便将整个应用程序集发布到计算机，然后将应用程序流式传输到缓存，以便完全加载这些应用程序。</span><span class="sxs-lookup"><span data-stu-id="55695-132">Log on to the staging computer with an account that has access to all applications so that the complete set of applications are published to the computer, and then stream the applications to cache so that they are fully loaded.</span></span>

   **<span data-ttu-id="55695-133">重要提示</span><span class="sxs-lookup"><span data-stu-id="55695-133">Important</span></span>**  
   <span data-ttu-id="55695-134">暂存计算机必须使用与应用 V 客户端将运行的 Vm 所使用的相同操作系统类型和系统体系结构。</span><span class="sxs-lookup"><span data-stu-id="55695-134">The staging computer must use the same operating system type and system architecture as those used by the VMs on which the App-V Client will run.</span></span>

     

4. <span data-ttu-id="55695-135">在安全模式下重新启动暂存计算机以确保驱动程序未启动，这将锁定缓存文件。</span><span class="sxs-lookup"><span data-stu-id="55695-135">Restart the staging computer in Safe Mode to ensure the drivers are not started, which would lock the cache file.</span></span>

   **<span data-ttu-id="55695-136">注意</span><span class="sxs-lookup"><span data-stu-id="55695-136">Note</span></span>**  
   <span data-ttu-id="55695-137">或者，你可以停止和禁用应用程序虚拟化服务，然后重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="55695-137">Alternatively, you can stop and disable the Application Virtualization service, and then restart the computer.</span></span> <span data-ttu-id="55695-138">复制文件后，请记住启用并再次启动服务。</span><span class="sxs-lookup"><span data-stu-id="55695-138">After the file has been copied, remember to enable and start the service again.</span></span>

     

5. <span data-ttu-id="55695-139">将 Sftfs 缓存文件复制到 VDI 服务器的 SAN，其中所有 Vm 都可以访问它，例如在共享文件夹中。</span><span class="sxs-lookup"><span data-stu-id="55695-139">Copy the Sftfs.fsd cache file to the VDI server’s SAN where all the VMs can access it, such as in a shared folder.</span></span> <span data-ttu-id="55695-140">将组的 "文件夹访问权限" 设置为 "对所有人只读"，并对将管理缓存文件更新的管理员拥有 "完全控制"。</span><span class="sxs-lookup"><span data-stu-id="55695-140">Set the folder access permissions to Read-only for the group Everyone and to Full Control for administrators who will manage the cache file updates.</span></span> <span data-ttu-id="55695-141">可以从注册表中获取缓存文件的位置 AppFS\\FileName。</span><span class="sxs-lookup"><span data-stu-id="55695-141">The location of the cache file can be obtained from the registry AppFS\\FileName.</span></span>

   **<span data-ttu-id="55695-142">重要提示</span><span class="sxs-lookup"><span data-stu-id="55695-142">Important</span></span>**  
   <span data-ttu-id="55695-143">你必须将 FSD 文件放在具有与本地连接的存储性能（如 SAN）等效的响应性和可靠性的位置。</span><span class="sxs-lookup"><span data-stu-id="55695-143">You must put the FSD file in a location that has the responsiveness and reliability equivalent to locally attached storage performance, for example, a SAN.</span></span>

     

6. <span data-ttu-id="55695-144">在 VDI 主 VM 镜像上安装 app-v 桌面客户端，然后将其配置为使用只读缓存，方法是将以下注册表项值添加到客户端上的 AppFS 项。</span><span class="sxs-lookup"><span data-stu-id="55695-144">Install the App-V Desktop Client on the VDI Master VM Image, and then configure it to use the read-only cache by adding the following registry key values to the AppFS key on the client.</span></span> <span data-ttu-id="55695-145">AppFS 键位于 HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\\ [Wow6432Node\\\] Microsoft\\SoftGrid\\4.5\\Client\\AppFS。</span><span class="sxs-lookup"><span data-stu-id="55695-145">The AppFS key is located at HKEY\_LOCAL\_MACHINE\\SOFTWARE\\\[Wow6432Node\\\]Microsoft\\SoftGrid\\4.5\\Client\\AppFS.</span></span>

   <table>
   <colgroup>
   <col width="25%" />
   <col width="25%" />
   <col width="25%" />
   <col width="25%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="55695-146">项</span><span class="sxs-lookup"><span data-stu-id="55695-146">Key</span></span></th>
   <th align="left"><span data-ttu-id="55695-147">类型</span><span class="sxs-lookup"><span data-stu-id="55695-147">Type</span></span></th>
   <th align="left"><span data-ttu-id="55695-148">值</span><span class="sxs-lookup"><span data-stu-id="55695-148">Value</span></span></th>
   <th align="left"><span data-ttu-id="55695-149">用途</span><span class="sxs-lookup"><span data-stu-id="55695-149">Purpose</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="55695-150">FileName</span><span class="sxs-lookup"><span data-stu-id="55695-150">FileName</span></span></p></td>
   <td align="left"><p><span data-ttu-id="55695-151">字符串</span><span class="sxs-lookup"><span data-stu-id="55695-151">String</span></span></p></td>
   <td align="left"><p><span data-ttu-id="55695-152">FSD 的路径</span><span class="sxs-lookup"><span data-stu-id="55695-152">path to FSD</span></span></p></td>
   <td align="left"><p><span data-ttu-id="55695-153">指定共享缓存文件的路径，例如 \VDIServername\Sharefolder\SFTFS。FSD （必需）。</span><span class="sxs-lookup"><span data-stu-id="55695-153">Specifies the path to the shared cache file, for example, \VDIServername\Sharefolder\SFTFS.FSD (Required).</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="55695-154">ReadOnlyFSD</span><span class="sxs-lookup"><span data-stu-id="55695-154">ReadOnlyFSD</span></span></p></td>
   <td align="left"><p><span data-ttu-id="55695-155">DWORD</span><span class="sxs-lookup"><span data-stu-id="55695-155">DWORD</span></span></p></td>
   <td align="left"><p><span data-ttu-id="55695-156">raid-1</span><span class="sxs-lookup"><span data-stu-id="55695-156">1</span></span></p></td>
   <td align="left"><p><span data-ttu-id="55695-157">将客户端配置为以只读模式运行。</span><span class="sxs-lookup"><span data-stu-id="55695-157">Configures the client to operate in Read-Only mode.</span></span> <span data-ttu-id="55695-158">这可确保客户端不会尝试将更新传输到程序包缓存。</span><span class="sxs-lookup"><span data-stu-id="55695-158">This ensures that the client will not attempt to stream updates to the package cache.</span></span> <span data-ttu-id="55695-159">（必需）</span><span class="sxs-lookup"><span data-stu-id="55695-159">(Required)</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="55695-160">ErrorLogLocation</span><span class="sxs-lookup"><span data-stu-id="55695-160">ErrorLogLocation</span></span></p></td>
   <td align="left"><p><span data-ttu-id="55695-161">字符串</span><span class="sxs-lookup"><span data-stu-id="55695-161">String</span></span></p></td>
   <td align="left"><p><span data-ttu-id="55695-162">错误日志（.etl）文件的路径</span><span class="sxs-lookup"><span data-stu-id="55695-162">path to error log (.etl) file</span></span></p></td>
   <td align="left"><p><span data-ttu-id="55695-163">用于指定错误日志路径的条目。</span><span class="sxs-lookup"><span data-stu-id="55695-163">Entry used to specify the path to the error log.</span></span> <span data-ttu-id="55695-164">建议您使用.</span><span class="sxs-lookup"><span data-stu-id="55695-164">(Recommended.</span></span> <span data-ttu-id="55695-165">使用本地路径，如 C:\Logs\Sftfs.etl）。</span><span class="sxs-lookup"><span data-stu-id="55695-165">Use a local path such as C:\Logs\Sftfs.etl).</span></span></p></td>
   </tr>
   </tbody>
   </table>

     

7. <span data-ttu-id="55695-166">将主 VM 映像客户端配置为使用发布服务器，并在登录时使用发布刷新。</span><span class="sxs-lookup"><span data-stu-id="55695-166">Configure the Master VM Image client to use the publishing server and to use publishing refresh at logon.</span></span> <span data-ttu-id="55695-167">当用户登录到 VDI 系统并且其 VM 是从主 VM 映像生成时，将发生发布刷新周期并发布其帐户已获得授权的所有应用程序。</span><span class="sxs-lookup"><span data-stu-id="55695-167">As users log on to the VDI system and their VM is built from the Master VM Image, a publishing refresh cycle occurs and publishes all the applications for which their account is authorized.</span></span> <span data-ttu-id="55695-168">这些应用程序从共享缓存中运行。</span><span class="sxs-lookup"><span data-stu-id="55695-168">These applications are run from the shared cache.</span></span>

**<span data-ttu-id="55695-169">在池中的 VM 方案中为程序包升级配置客户端</span><span class="sxs-lookup"><span data-stu-id="55695-169">To configure the client for package upgrade in a Pooled VM scenario</span></span>**

1.  <span data-ttu-id="55695-170">完成应用程序包的升级和测试。</span><span class="sxs-lookup"><span data-stu-id="55695-170">Complete the upgrade and testing of the application package.</span></span>

2.  <span data-ttu-id="55695-171">升级 app-v 服务器上的程序包。</span><span class="sxs-lookup"><span data-stu-id="55695-171">Upgrade the package on the App-V server.</span></span> <span data-ttu-id="55695-172">然后，将新版本的应用程序发布并流式传输到暂存计算机上的客户端，以便它们完全加载到缓存中。</span><span class="sxs-lookup"><span data-stu-id="55695-172">Then, publish and stream the new version of the applications to the client on the staging computer so that they are fully loaded into cache.</span></span>

3.  <span data-ttu-id="55695-173">在安全模式下重新启动暂存计算机，以确保驱动程序未启动。</span><span class="sxs-lookup"><span data-stu-id="55695-173">Restart the staging computer in Safe Mode to ensure the drivers are not started.</span></span>

    <span data-ttu-id="55695-174">**注意** 或者，您可以在 services.msc 中停止和禁用应用程序虚拟化服务，然后重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="55695-174">**Note** Alternatively, you can stop and disable the Application Virtualization service in the Services.msc, and then restart the computer.</span></span> <span data-ttu-id="55695-175">复制文件后，请记住启用并再次启动服务。</span><span class="sxs-lookup"><span data-stu-id="55695-175">After the file has been copied, remember to enable and start the service again.</span></span>

     

4.  <span data-ttu-id="55695-176">将 Sftfs 缓存文件复制到 VDI 服务器的 SAN，其中所有 Vm 都可以访问它，例如在共享文件夹中。</span><span class="sxs-lookup"><span data-stu-id="55695-176">Copy the Sftfs.fsd cache file to the VDI server’s SAN where all the VMs can access it, such as in a shared folder.</span></span> <span data-ttu-id="55695-177">你可以使用不同的文件名，例如，SFTFS \ _V2。FSD，以区分新版本。</span><span class="sxs-lookup"><span data-stu-id="55695-177">You can use a different filename, for example, SFTFS\_V2.FSD, to distinguish the new version.</span></span>

5.  <span data-ttu-id="55695-178">若要在 VDI 主机 VM 映像上配置 app-v 桌面客户端以使用更新的共享缓存文件，请将 AppFS 注册表项文件名值更改为指向已更新文件的位置，例如，\\\\VDIServername\\Sharefolder\\SFTFS\ _V2。FSD.</span><span class="sxs-lookup"><span data-stu-id="55695-178">To configure the App-V Desktop Client on the VDI Master VM Image to use the updated shared cache file, change the AppFS registry key FILENAME value to point to the location of the updated file, for example, \\\\VDIServername\\Sharefolder\\SFTFS\_V2.FSD.</span></span> <span data-ttu-id="55695-179">当用户注销然后再次登录时，将使用已更新的主映像为其创建新的 VM。</span><span class="sxs-lookup"><span data-stu-id="55695-179">When users log off and then log on again, a new VM is created for them by using the updated Master Image.</span></span> <span data-ttu-id="55695-180">将保留所有用户设置并将其应用到新 VM。</span><span class="sxs-lookup"><span data-stu-id="55695-180">All their user settings will be retained and applied to the new VM.</span></span> <span data-ttu-id="55695-181">然后他们有权访问已更新的应用程序。</span><span class="sxs-lookup"><span data-stu-id="55695-181">Then they have access to the updated applications.</span></span>

**<span data-ttu-id="55695-182">在静态 VM 方案中为程序包升级配置客户端</span><span class="sxs-lookup"><span data-stu-id="55695-182">To configure the client for package upgrade in a Static VM scenario</span></span>**

1.  <span data-ttu-id="55695-183">完成应用程序包的升级和测试。</span><span class="sxs-lookup"><span data-stu-id="55695-183">Complete the upgrade and testing of the application package.</span></span>

2.  <span data-ttu-id="55695-184">升级 app-v 服务器上的程序包。</span><span class="sxs-lookup"><span data-stu-id="55695-184">Upgrade the package on the App-V server.</span></span> <span data-ttu-id="55695-185">然后，将新版本的应用程序发布并流式传输到暂存计算机上的客户端，以便将应用程序完全加载到缓存中。</span><span class="sxs-lookup"><span data-stu-id="55695-185">Then, publish and stream the new version of the applications to the client on the staging computer so that the applications are fully loaded into cache.</span></span>

3.  <span data-ttu-id="55695-186">在安全模式下重新启动暂存计算机，以确保不会启动驱动程序。</span><span class="sxs-lookup"><span data-stu-id="55695-186">Restart the staging computer in Safe Mode to ensure that the drivers are not started.</span></span>

    <span data-ttu-id="55695-187">**注意** 或者，您可以在 services.msc 中停止和禁用应用程序虚拟化服务，然后重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="55695-187">**Note** Alternatively, you can stop and disable the Application Virtualization service in the Services.msc, and then restart the computer.</span></span> <span data-ttu-id="55695-188">复制文件后，请记住启用并再次启动服务。</span><span class="sxs-lookup"><span data-stu-id="55695-188">After the file has been copied, remember to enable and start the service again.</span></span>

     

4.  <span data-ttu-id="55695-189">将 Sftfs 缓存文件复制到 VDI 服务器的 SAN，其中所有 Vm 都可以访问它，例如在共享文件夹中。</span><span class="sxs-lookup"><span data-stu-id="55695-189">Copy the Sftfs.fsd cache file to the VDI server’s SAN where all the VMs can access it, such as in a shared folder.</span></span> <span data-ttu-id="55695-190">你可以使用不同的文件名，例如，SFTFS \ _V2。FSD，以区分新版本。</span><span class="sxs-lookup"><span data-stu-id="55695-190">You can use a different filename, for example, SFTFS\_V2.FSD, to distinguish the new version.</span></span>

5.  <span data-ttu-id="55695-191">若要在 VDI 主机 VM 映像上配置 app-v 桌面客户端以使用更新的共享缓存文件，请将 AppFS 注册表项文件名值更改为指向已更新文件的位置，例如，\\\\VDIServername\\Sharefolder\\SFTFS\ _V2。FSD.</span><span class="sxs-lookup"><span data-stu-id="55695-191">To configure the App-V Desktop Client on the VDI Master VM Image to use the updated shared cache file, change the AppFS registry key FILENAME value to point to the location of the updated file, for example, \\\\VDIServername\\Sharefolder\\SFTFS\_V2.FSD.</span></span> <span data-ttu-id="55695-192">这可确保新用户获得新版本。</span><span class="sxs-lookup"><span data-stu-id="55695-192">This ensures that new users get the new version.</span></span>

6.  <span data-ttu-id="55695-193">创建编辑 AppFS 键文件名的脚本，以将其设置为更新缓存的位置，例如，\\\\VDIServername\\Sharefolder\\SFTFS\ _V2。FSD.</span><span class="sxs-lookup"><span data-stu-id="55695-193">Create a script that edits the AppFS key FILENAME value to set it to the location of the updated cache, for example, \\\\VDIServername\\Sharefolder\\SFTFS\_V2.FSD.</span></span> <span data-ttu-id="55695-194">将此脚本配置为当用户注销或登录时运行，以便在 App-v 客户端驱动程序启动之前运行，例如使用组策略设置。</span><span class="sxs-lookup"><span data-stu-id="55695-194">Configure this script to run when the user logs off or logs on so that it runs before the App-V client drivers start, for example, by using Group Policy settings.</span></span> <span data-ttu-id="55695-195">当用户注销并再次登录时，其现有 VM 将更新，并且它们将使用缓存的更新副本。</span><span class="sxs-lookup"><span data-stu-id="55695-195">When users log off and log on again, their existing VM is updated, and they will use the updated copy of the cache.</span></span> <span data-ttu-id="55695-196">然后，他们有权访问已更新的应用程序。</span><span class="sxs-lookup"><span data-stu-id="55695-196">Then, they have access to the updated applications.</span></span>

## <span data-ttu-id="55695-197">升级缓存时如何使用符号链接</span><span class="sxs-lookup"><span data-stu-id="55695-197">How to Use Symbolic Links when Upgrading the Cache</span></span>


<span data-ttu-id="55695-198">在每次部署包含新的或已升级的程序包的新缓存文件时，你可以使用以下操作系统中的符号链接： Windows Vista、Windows 7 和 Windows Server 2008，而不是修改 AppFS 项文件名值。</span><span class="sxs-lookup"><span data-stu-id="55695-198">Instead of modifying the AppFS key FILENAME value every time that a new cache file is deployed that contains new or upgraded packages, you can use a symbolic link in the following operating systems: Windows Vista, Windows 7, and Windows Server 2008.</span></span> <span data-ttu-id="55695-199">有关符号链接的详细信息，请参阅[符号链接](https://go.microsoft.com/fwlink/?LinkId=157626)（ https://go.microsoft.com/fwlink/?LinkId=157626) 。</span><span class="sxs-lookup"><span data-stu-id="55695-199">For more information about symbolic links, see [Symbolic Links](https://go.microsoft.com/fwlink/?LinkId=157626) (https://go.microsoft.com/fwlink/?LinkId=157626).</span></span> <span data-ttu-id="55695-200">相比之下，Windows XP 不支持使用符号链接，您必须改用交接点。</span><span class="sxs-lookup"><span data-stu-id="55695-200">In contrast, Windows XP does not support the use of symbolic links, and you must use junction points instead.</span></span> <span data-ttu-id="55695-201">有关联接的详细信息，请参阅 Microsoft 知识库中的[文章 205524](https://go.microsoft.com/fwlink/?LinkId=182553) （ https://go.microsoft.com/fwlink/?LinkId=182553) 以及工具[连接 v 1.05](https://go.microsoft.com/fwlink/?LinkId=182554) （） https://go.microsoft.com/fwlink/?LinkId=182554) 。</span><span class="sxs-lookup"><span data-stu-id="55695-201">For more information about junctions, see [article 205524](https://go.microsoft.com/fwlink/?LinkId=182553) in the Microsoft Knowledge Base (https://go.microsoft.com/fwlink/?LinkId=182553), and also the tool [Junction v1.05](https://go.microsoft.com/fwlink/?LinkId=182554) (https://go.microsoft.com/fwlink/?LinkId=182554).</span></span>

**<span data-ttu-id="55695-202">配置符号链接以引用缓存</span><span class="sxs-lookup"><span data-stu-id="55695-202">To configure a symbolic link to reference the cache</span></span>**

1.  <span data-ttu-id="55695-203">在初始部署阶段，在 VDI 服务器主机操作系统上以本地管理员身份打开命令提示符窗口。</span><span class="sxs-lookup"><span data-stu-id="55695-203">During the initial deployment stage, open a Command Prompt window as a local administrator on the VDI server host operating system.</span></span>

2.  <span data-ttu-id="55695-204">使用 MKLINK 命令创建符号链接，然后将其配置为指向 Sftfs 文件。</span><span class="sxs-lookup"><span data-stu-id="55695-204">Create a symbolic link by using the MKLINK command, and then configure it to point to the Sftfs.fsd file.</span></span>

    **     <span data-ttu-id="55695-205">mklink symlinkname \\\\vdihostserver\\sharefolder\\sftfs.fsd</span><span class="sxs-lookup"><span data-stu-id="55695-205">mklink symlinkname \\\\vdihostserver\\sharefolder\\sftfs.fsd</span></span>**

3.  <span data-ttu-id="55695-206">在 VDI 主 VM 映像上，使用 "以**管理员身份运行**" 选项打开命令提示符窗口，并授予远程链接权限，以便 VM 可以访问 VDI 主机操作系统上的符号链接。</span><span class="sxs-lookup"><span data-stu-id="55695-206">On the VDI Master VM Image, open a Command Prompt window by using the **Run as administrator** option and grant remote link permissions so that the VM can access the symbolic link on the VDI Host operating system.</span></span> <span data-ttu-id="55695-207">默认情况下，禁用远程链接权限。</span><span class="sxs-lookup"><span data-stu-id="55695-207">By default, remote link permissions are disabled.</span></span>

    **<span data-ttu-id="55695-208">fsutil behavior set SymlinkEvaluation R2R：1</span><span class="sxs-lookup"><span data-stu-id="55695-208">fsutil behavior set SymlinkEvaluation R2R:1</span></span>**

    <span data-ttu-id="55695-209">**注意** 在存储服务器上，必须启用相应的链接权限。</span><span class="sxs-lookup"><span data-stu-id="55695-209">**Note** On the storage server, appropriate link permissions must be enabled.</span></span> <span data-ttu-id="55695-210">根据 link 和 Sftfs 文件的位置，权限为**L2L： 1**或**L2R： 1**或**R2L** ： 1**或 R2R：1。**</span><span class="sxs-lookup"><span data-stu-id="55695-210">Depending on the location of link and the Sftfs.fsd file, the permissions are **L2L:1** or **L2R:1** or **R2L:1** or **R2R:1**.</span></span>

     

4.  <span data-ttu-id="55695-211">在 VDI 主 VM 镜像上配置 app-v 桌面客户端时，将 AppFS 项文件名值设置为等于使用符号链接的 FSD 文件的 UNC 路径;例如，将其设置为 \\\\VDIHostserver\\Symlinkname。</span><span class="sxs-lookup"><span data-stu-id="55695-211">When you configure the App-V Desktop Client on the VDI Master VM Image, set the AppFS key FILENAME value equal to the UNC path of the FSD file that is using the symbolic link; for example, set it to \\\\VDIHostserver\\Symlinkname.</span></span> <span data-ttu-id="55695-212">当 App-v 客户端首次访问缓存时，符号链接将向客户端传递一个指向缓存文件的句柄。</span><span class="sxs-lookup"><span data-stu-id="55695-212">When the App-V client first accesses the cache, the symbolic link passes to the client a handle to the cache file.</span></span> <span data-ttu-id="55695-213">只要客户端运行，客户端就会继续使用该句柄。</span><span class="sxs-lookup"><span data-stu-id="55695-213">The client continues to use that handle as long as the client is running.</span></span> <span data-ttu-id="55695-214">即使现有客户端已打开旧的共享缓存，符号链接的值也可以安全更新。</span><span class="sxs-lookup"><span data-stu-id="55695-214">The value of the symbolic link can safely be updated even if existing clients have the old shared cache open.</span></span>

5.  <span data-ttu-id="55695-215">当必须升级程序包或将新程序包添加到缓存时，请对静态 VM 或共用 VM 方案执行升级过程中的步骤1到步骤5。</span><span class="sxs-lookup"><span data-stu-id="55695-215">When you must upgrade a package or to add a new package to the cache, follow steps 1 through 5 of the upgrade procedure for either the Static VM or Pooled VM scenario.</span></span> <span data-ttu-id="55695-216">然后，删除符号链接并重新创建以指向共享缓存文件的新版本。</span><span class="sxs-lookup"><span data-stu-id="55695-216">Then, delete the symbolic link and re-create it to point to the new version of the shared cache file.</span></span> <span data-ttu-id="55695-217">重新启动 VM 时，客户端将收到缓存的更新副本的句柄，因为 VM 使用包含更新符号链接的路径。</span><span class="sxs-lookup"><span data-stu-id="55695-217">When the VM is restarted, the client receives a handle to the updated copy of the cache because the VM uses the path that contains the updated symbolic link.</span></span> <span data-ttu-id="55695-218">然后，用户有权访问新的和更新的应用程序。</span><span class="sxs-lookup"><span data-stu-id="55695-218">Then, the users have access to the new and updated applications.</span></span>

## <span data-ttu-id="55695-219">相关主题</span><span class="sxs-lookup"><span data-stu-id="55695-219">Related topics</span></span>


[<span data-ttu-id="55695-220">如何安装 Application Virtualization Management Server</span><span class="sxs-lookup"><span data-stu-id="55695-220">How to Install Application Virtualization Management Server</span></span>](how-to-install-application-virtualization-management-server.md)

[<span data-ttu-id="55695-221">如何手动安装 Application Virtualization Client</span><span class="sxs-lookup"><span data-stu-id="55695-221">How to Manually Install the Application Virtualization Client</span></span>](how-to-manually-install-the-application-virtualization-client.md)

[<span data-ttu-id="55695-222">如何使用命令行安装客户端</span><span class="sxs-lookup"><span data-stu-id="55695-222">How to Install the Client by Using the Command Line</span></span>](how-to-install-the-client-by-using-the-command-line-new.md)

 

 





