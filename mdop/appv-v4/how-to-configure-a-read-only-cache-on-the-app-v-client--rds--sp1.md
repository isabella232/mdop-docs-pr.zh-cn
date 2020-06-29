---
title: 如何在 App-V Client (RDS) 上配置只读缓存
description: 如何在 App-V Client (RDS) 上配置只读缓存
author: dansimp
ms.assetid: b6607fe2-6f92-4567-99f1-d8e3c8a591e0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a44844ae9ffc3497151be7713f6a43fda0ccd8fa
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801620"
---
# <span data-ttu-id="feae6-103">如何在 App-V Client (RDS) 上配置只读缓存</span><span class="sxs-lookup"><span data-stu-id="feae6-103">How to Configure a Read-only Cache on the App-V Client (RDS)</span></span>


<span data-ttu-id="feae6-104">**重要提示** 必须运行 App-v 4.6、SP1 才能使用此过程。</span><span class="sxs-lookup"><span data-stu-id="feae6-104">**Important** You must be running App-V 4.6, SP1 to use this procedure.</span></span>

 

<span data-ttu-id="feae6-105">你可以通过使用由所有用户所需的所有应用程序填充的共享缓存来部署 app-v 客户端。</span><span class="sxs-lookup"><span data-stu-id="feae6-105">You can deploy the App-V client by using a shared cache that is populated with all the applications required for all users.</span></span> <span data-ttu-id="feae6-106">然后，将 App-v 远程桌面服务（RDS）客户端配置为使用同一缓存文件。</span><span class="sxs-lookup"><span data-stu-id="feae6-106">Then you configure the App-V Remote Desktop Services (RDS) Clients to use the same cache file.</span></span> <span data-ttu-id="feae6-107">用户通过使用 App-v 发布过程向用户授予对特定应用程序的访问权限。</span><span class="sxs-lookup"><span data-stu-id="feae6-107">Users are granted access to specific applications by using the App-V publishing process.</span></span> <span data-ttu-id="feae6-108">由于缓存已预加载了所有应用程序，因此当用户启动应用程序时，不会发生流。</span><span class="sxs-lookup"><span data-stu-id="feae6-108">Because the cache is already preloaded with all applications, no streaming occurs when a user starts an application.</span></span> <span data-ttu-id="feae6-109">但是，用于预填充缓存的程序包必须放置在支持实时流协议（RTSP）流的 app-v 服务器上，并且授予对 App-v 客户端的访问权限。</span><span class="sxs-lookup"><span data-stu-id="feae6-109">However, the packages used to prepopulate the cache must be put on an App-V server that supports Real Time Streaming Protocol (RTSP) streaming and that grants access permissions to the App-V Clients.</span></span> <span data-ttu-id="feae6-110">如果使用 App-v 管理服务器发布应用程序，则可以使用它来提供此流函数。</span><span class="sxs-lookup"><span data-stu-id="feae6-110">If you publish the applications by using an App-V Management Server, you can use it to provide this streaming function.</span></span>

<span data-ttu-id="feae6-111">**注意** 这些过程中概述的详细信息仅用作示例。</span><span class="sxs-lookup"><span data-stu-id="feae6-111">**Note** The details outlined in these procedures are intended as examples only.</span></span> <span data-ttu-id="feae6-112">你可以使用不同的方法来完成整个过程。</span><span class="sxs-lookup"><span data-stu-id="feae6-112">You might use different methods to complete the overall process.</span></span>

 

## <span data-ttu-id="feae6-113">在 RDS 方案中部署 app-v 客户端</span><span class="sxs-lookup"><span data-stu-id="feae6-113">Deploying the App-V Client in an RDS Scenario</span></span>


<span data-ttu-id="feae6-114">部署过程由四个主要任务组成：</span><span class="sxs-lookup"><span data-stu-id="feae6-114">The deployment process consists of four primary tasks:</span></span>

-   <span data-ttu-id="feae6-115">创建和填充主共享缓存文件</span><span class="sxs-lookup"><span data-stu-id="feae6-115">Creating and populating the master shared cache file</span></span>

-   <span data-ttu-id="feae6-116">将共享缓存文件复制到服务器存储</span><span class="sxs-lookup"><span data-stu-id="feae6-116">Copying the shared cache file to the server storage</span></span>

-   <span data-ttu-id="feae6-117">配置 App-v 客户端软件</span><span class="sxs-lookup"><span data-stu-id="feae6-117">Configuring the App-V client software</span></span>

-   <span data-ttu-id="feae6-118">在初始部署后管理共享缓存文件的更新部署周期</span><span class="sxs-lookup"><span data-stu-id="feae6-118">Managing the update deployment cycle for the shared cache file after the initial deployment</span></span>

<span data-ttu-id="feae6-119">这些任务需要仔细规划。</span><span class="sxs-lookup"><span data-stu-id="feae6-119">These tasks require careful planning.</span></span> <span data-ttu-id="feae6-120">我们建议你为你的组织准备并记录可重复执行的流程。</span><span class="sxs-lookup"><span data-stu-id="feae6-120">We recommend that you prepare and document a methodical, reproducible process for your organization to follow.</span></span> <span data-ttu-id="feae6-121">这对于主共享缓存文件的准备和部署尤其重要，并且对于应用程序更新的持续管理，每个更新都需要更新到主共享缓存。</span><span class="sxs-lookup"><span data-stu-id="feae6-121">This is especially important for the preparation and deployment of the master shared cache file, and for the ongoing management of application updates, each of which require an update to the master shared cache.</span></span> <span data-ttu-id="feae6-122">使用以下过程完成这些主要任务。</span><span class="sxs-lookup"><span data-stu-id="feae6-122">Use the following procedures to complete these primary tasks.</span></span>

<span data-ttu-id="feae6-123">**注意** 虽然你可以使用多种不同的方法发布应用程序，但以下过程基于你使用的 app-v 管理服务器进行发布。</span><span class="sxs-lookup"><span data-stu-id="feae6-123">**Note** Although you can publish the applications by using several different methods, the following procedures are based on your using an App-V Management Server for publishing.</span></span>

 

**<span data-ttu-id="feae6-124">为初始部署配置只读缓存</span><span class="sxs-lookup"><span data-stu-id="feae6-124">To configure the read-only cache for initial deployment</span></span>**

1. <span data-ttu-id="feae6-125">设置和配置 app-v 管理服务器，以提供用户身份验证和发布支持。</span><span class="sxs-lookup"><span data-stu-id="feae6-125">Set up and configure an App-V Management Server to provide user authentication and publishing support.</span></span>

2. <span data-ttu-id="feae6-126">将此管理服务器的内容文件夹填充给所有用户所需的所有应用程序包。</span><span class="sxs-lookup"><span data-stu-id="feae6-126">Populate the Content folder of this Management Server with all the application packages required for all users.</span></span>

3. <span data-ttu-id="feae6-127">设置已安装 App-v 客户端的暂存计算机。</span><span class="sxs-lookup"><span data-stu-id="feae6-127">Set up a staging computer that has the App-V Client installed.</span></span> <span data-ttu-id="feae6-128">使用具有对所有应用程序的访问权限的帐户登录到暂存计算机，以便将整个应用程序集发布到计算机，然后将应用程序流式传输到缓存，以便完全加载这些应用程序。</span><span class="sxs-lookup"><span data-stu-id="feae6-128">Log on to the staging computer by using an account that has access to all applications so that the complete set of applications are published to the computer, and then stream the applications to cache so that they are fully loaded.</span></span>

   **<span data-ttu-id="feae6-129">重要提示</span><span class="sxs-lookup"><span data-stu-id="feae6-129">Important</span></span>**  
   <span data-ttu-id="feae6-130">暂存计算机必须使用与应用 V 客户端将运行的 Vm 所使用的相同操作系统类型和系统体系结构。</span><span class="sxs-lookup"><span data-stu-id="feae6-130">The staging computer must use the same operating system type and system architecture as those used by the VMs on which the App-V Client will run.</span></span>

     

4. <span data-ttu-id="feae6-131">在安全模式下重新启动暂存计算机以确保驱动程序未启动，因为这会锁定缓存文件。</span><span class="sxs-lookup"><span data-stu-id="feae6-131">Restart the staging computer in safe mode to make sure that the drivers are not started, because this would lock the cache file.</span></span>

   **<span data-ttu-id="feae6-132">注意</span><span class="sxs-lookup"><span data-stu-id="feae6-132">Note</span></span>**  
   <span data-ttu-id="feae6-133">或者，您可以停止和禁用应用程序虚拟化服务，然后重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="feae6-133">Or, you can stop and disable the Application Virtualization service, and then restart the computer.</span></span> <span data-ttu-id="feae6-134">复制文件后，请记住启用并再次启动服务。</span><span class="sxs-lookup"><span data-stu-id="feae6-134">After the file is copied, remember to enable and start the service again.</span></span>

     

5. <span data-ttu-id="feae6-135">将 Sftfs 缓存文件复制到 SAN，其中所有 RDS 服务器都可以访问它，例如在共享文件夹中。</span><span class="sxs-lookup"><span data-stu-id="feae6-135">Copy the Sftfs.fsd cache file to a SAN where all the RDS servers can access it, such as in a shared folder.</span></span> <span data-ttu-id="feae6-136">将组的 "文件夹访问权限" 设置为 "对所有人只读"，并对将管理缓存文件更新的管理员拥有 "完全控制"。</span><span class="sxs-lookup"><span data-stu-id="feae6-136">Set the folder access permissions to Read-only for the group Everyone and to Full Control for administrators who will manage the cache file updates.</span></span> <span data-ttu-id="feae6-137">可以从注册表中获取缓存文件的位置 AppFS\\FileName。</span><span class="sxs-lookup"><span data-stu-id="feae6-137">The location of the cache file can be obtained from the registry AppFS\\FileName.</span></span>

   **<span data-ttu-id="feae6-138">重要提示</span><span class="sxs-lookup"><span data-stu-id="feae6-138">Important</span></span>**  
   <span data-ttu-id="feae6-139">你必须将 FSD 文件放在具有等于本地附加的存储性能（例如 SAN）的响应性和可靠性的位置。</span><span class="sxs-lookup"><span data-stu-id="feae6-139">You must put the FSD file in a location that has the responsiveness and reliability equal to locally attached storage performance, for example, a SAN.</span></span>

     

6. <span data-ttu-id="feae6-140">在每个 RDS 服务器上安装 app-v RDS 客户端，然后将其配置为使用只读缓存，方法是将以下注册表项值添加到客户端上的 AppFS 项。</span><span class="sxs-lookup"><span data-stu-id="feae6-140">Install the App-V RDS Client on each RDS server, and then configure it to use the read-only cache by adding the following registry key values to the AppFS key on the client.</span></span> <span data-ttu-id="feae6-141">AppFS 键位于32位计算机的 HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\\] Microsoft\\SoftGrid\\4.5\\Client\\AppFS 中，64位计算机的 HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS。</span><span class="sxs-lookup"><span data-stu-id="feae6-141">The AppFS key is located at HKEY\_LOCAL\_MACHINE\\SOFTWARE\\\]Microsoft\\SoftGrid\\4.5\\Client\\AppFS for 32-bit computers and at HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS for 64-bit computers.</span></span>

   <table>
   <colgroup>
   <col width="25%" />
   <col width="25%" />
   <col width="25%" />
   <col width="25%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="feae6-142">项</span><span class="sxs-lookup"><span data-stu-id="feae6-142">Key</span></span></th>
   <th align="left"><span data-ttu-id="feae6-143">类型</span><span class="sxs-lookup"><span data-stu-id="feae6-143">Type</span></span></th>
   <th align="left"><span data-ttu-id="feae6-144">值</span><span class="sxs-lookup"><span data-stu-id="feae6-144">Value</span></span></th>
   <th align="left"><span data-ttu-id="feae6-145">用途</span><span class="sxs-lookup"><span data-stu-id="feae6-145">Purpose</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="feae6-146">FileName</span><span class="sxs-lookup"><span data-stu-id="feae6-146">FileName</span></span></p></td>
   <td align="left"><p><span data-ttu-id="feae6-147">字符串</span><span class="sxs-lookup"><span data-stu-id="feae6-147">String</span></span></p></td>
   <td align="left"><p><span data-ttu-id="feae6-148">FSD 的路径</span><span class="sxs-lookup"><span data-stu-id="feae6-148">path of FSD</span></span></p></td>
   <td align="left"><p><span data-ttu-id="feae6-149">指定共享缓存文件的路径，例如 \RDSServername\Sharefolder\SFTFS。FSD （必需）。</span><span class="sxs-lookup"><span data-stu-id="feae6-149">Specifies the path of the shared cache file, for example, \RDSServername\Sharefolder\SFTFS.FSD (Required).</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="feae6-150">ReadOnlyFSD</span><span class="sxs-lookup"><span data-stu-id="feae6-150">ReadOnlyFSD</span></span></p></td>
   <td align="left"><p><span data-ttu-id="feae6-151">DWORD</span><span class="sxs-lookup"><span data-stu-id="feae6-151">DWORD</span></span></p></td>
   <td align="left"><p><span data-ttu-id="feae6-152">raid-1</span><span class="sxs-lookup"><span data-stu-id="feae6-152">1</span></span></p></td>
   <td align="left"><p><span data-ttu-id="feae6-153">将客户端配置为以只读模式运行。</span><span class="sxs-lookup"><span data-stu-id="feae6-153">Configures the client to operate in Read-Only mode.</span></span> <span data-ttu-id="feae6-154">这可确保客户端不会尝试将更新传输到程序包缓存。</span><span class="sxs-lookup"><span data-stu-id="feae6-154">This ensures that the client will not try to stream updates to the package cache.</span></span> <span data-ttu-id="feae6-155">（必需）</span><span class="sxs-lookup"><span data-stu-id="feae6-155">(Required)</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="feae6-156">ErrorLogLocation</span><span class="sxs-lookup"><span data-stu-id="feae6-156">ErrorLogLocation</span></span></p></td>
   <td align="left"><p><span data-ttu-id="feae6-157">字符串</span><span class="sxs-lookup"><span data-stu-id="feae6-157">String</span></span></p></td>
   <td align="left"><p><span data-ttu-id="feae6-158">错误日志（.etl）文件的路径</span><span class="sxs-lookup"><span data-stu-id="feae6-158">path of error log (.etl) file</span></span></p></td>
   <td align="left"><p><span data-ttu-id="feae6-159">用于指定错误日志路径的条目。</span><span class="sxs-lookup"><span data-stu-id="feae6-159">Entry used to specify the path of the error log.</span></span> <span data-ttu-id="feae6-160">建议您使用.</span><span class="sxs-lookup"><span data-stu-id="feae6-160">(Recommended.</span></span> <span data-ttu-id="feae6-161">使用本地路径，如 C:\Logs\Sftfs.etl）。</span><span class="sxs-lookup"><span data-stu-id="feae6-161">Use a local path such as C:\Logs\Sftfs.etl).</span></span></p></td>
   </tr>
   </tbody>
   </table>

     

7. <span data-ttu-id="feae6-162">将服务器场中的每个 RDS 服务器配置为使用发布服务器，并在用户登录时使用发布更新。</span><span class="sxs-lookup"><span data-stu-id="feae6-162">Configure each RDS server in the farm to use the publishing server and to use publishing update when users log on.</span></span> <span data-ttu-id="feae6-163">当用户登录到 RDS 服务器时，发布更新周期出现，并发布其帐户已获得授权的所有应用程序。</span><span class="sxs-lookup"><span data-stu-id="feae6-163">As users log on to the RDS servers, a publishing update cycle occurs and publishes all the applications for which their account is authorized.</span></span> <span data-ttu-id="feae6-164">这些应用程序从共享缓存中运行。</span><span class="sxs-lookup"><span data-stu-id="feae6-164">These applications are run from the shared cache.</span></span>

**<span data-ttu-id="feae6-165">为程序包升级配置 RDS 客户端</span><span class="sxs-lookup"><span data-stu-id="feae6-165">To configure the RDS client for package upgrade</span></span>**

1.  <span data-ttu-id="feae6-166">完成应用程序包的升级和测试。</span><span class="sxs-lookup"><span data-stu-id="feae6-166">Complete the upgrade and testing of the application package.</span></span>

2.  <span data-ttu-id="feae6-167">升级 app-v 服务器上的程序包。</span><span class="sxs-lookup"><span data-stu-id="feae6-167">Upgrade the package on the App-V server.</span></span> <span data-ttu-id="feae6-168">然后，将新版本的应用程序发布并流式传输到暂存计算机上的客户端，以便它们完全加载到缓存中。</span><span class="sxs-lookup"><span data-stu-id="feae6-168">Then, publish and stream the new version of the applications to the client on the staging computer so that they are fully loaded into cache.</span></span>

3.  <span data-ttu-id="feae6-169">在安全模式下重新启动暂存计算机，以确保驱动程序未启动。</span><span class="sxs-lookup"><span data-stu-id="feae6-169">Restart the staging computer in safe mode to ensure the drivers are not started.</span></span>

    <span data-ttu-id="feae6-170">**注意** 或者，你可以先停止，然后在 services.msc 中禁用应用程序虚拟化服务，然后重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="feae6-170">**Note** Or, you can first stop and then disable the Application Virtualization service in the Services.msc, and restart the computer.</span></span> <span data-ttu-id="feae6-171">复制文件后，请记住启用并再次启动服务。</span><span class="sxs-lookup"><span data-stu-id="feae6-171">After the file has been copied, remember to enable and start the service again.</span></span>

     

4.  <span data-ttu-id="feae6-172">将 Sftfs 缓存文件复制到 SAN，其中所有 RDS 服务器都可以访问它，例如在共享文件夹中。</span><span class="sxs-lookup"><span data-stu-id="feae6-172">Copy the Sftfs.fsd cache file to a SAN where all the RDS servers can access it, such as in a shared folder.</span></span> <span data-ttu-id="feae6-173">你可以使用不同的文件名，例如，SFTFS \ _V2。FSD，以区分新版本。</span><span class="sxs-lookup"><span data-stu-id="feae6-173">You can use a different file name, for example, SFTFS\_V2.FSD, to distinguish the new version.</span></span>

5.  <span data-ttu-id="feae6-174">若要在服务器场中的每个 RDS 服务器上配置 app-v RDS 客户端以使用更新的共享缓存文件，请将 AppFS 注册表项文件名值更改为指向已更新文件的位置，例如，\\\\RDSServername\\Sharefolder\\SFTFS\ _V2。FSD.</span><span class="sxs-lookup"><span data-stu-id="feae6-174">To configure the App-V RDS Client on each RDS server in the farm to use the updated shared cache file, change the AppFS registry key FILENAME value to point to the location of the updated file, for example, \\\\RDSServername\\Sharefolder\\SFTFS\_V2.FSD.</span></span> <span data-ttu-id="feae6-175">这可确保每个 RDS 服务器在应用 Vclient 驱动程序重启时收到缓存的更新副本。</span><span class="sxs-lookup"><span data-stu-id="feae6-175">This guarantees that each RDS server receives the updated copy of the cache when the App-Vclient drivers restart.</span></span>

    <span data-ttu-id="feae6-176">**重要提示** 必须重新启动 RDS 服务器才能使用更新的共享缓存文件。</span><span class="sxs-lookup"><span data-stu-id="feae6-176">**Important** You must restart the RDS servers in order to use the updated shared cache file.</span></span>

     

## <span data-ttu-id="feae6-177">升级缓存时如何使用符号链接</span><span class="sxs-lookup"><span data-stu-id="feae6-177">How to Use Symbolic Links when Upgrading the Cache</span></span>


<span data-ttu-id="feae6-178">不必在每次部署包含新的或已升级的程序包的新缓存文件时更改 AppFS 项文件名，您可以使用以下操作系统中的符号链接： Windows Vista、Windows 7 和 Windows Server 2008。</span><span class="sxs-lookup"><span data-stu-id="feae6-178">Instead of changing the AppFS key FILENAME value every time that a new cache file is deployed that contains new or upgraded packages, you can use a symbolic link in the following operating systems: Windows Vista, Windows 7, and Windows Server 2008.</span></span> <span data-ttu-id="feae6-179">有关符号链接的详细信息，请参阅[符号链接](https://go.microsoft.com/fwlink/?LinkId=157626)（ https://go.microsoft.com/fwlink/?LinkId=157626) 。</span><span class="sxs-lookup"><span data-stu-id="feae6-179">For more information about symbolic links, see [Symbolic Links](https://go.microsoft.com/fwlink/?LinkId=157626) (https://go.microsoft.com/fwlink/?LinkId=157626).</span></span> <span data-ttu-id="feae6-180">相比之下，Windows XP 不支持使用符号链接，您必须改用交接点。</span><span class="sxs-lookup"><span data-stu-id="feae6-180">In contrast, Windows XP does not support the use of symbolic links, and you must use junction points instead.</span></span> <span data-ttu-id="feae6-181">有关联接的详细信息，请参阅 Microsoft 知识库中的[文章 205524](https://go.microsoft.com/fwlink/?LinkId=182553) （ https://go.microsoft.com/fwlink/?LinkId=182553) 以及工具[连接 v 1.05](https://go.microsoft.com/fwlink/?LinkId=182554) （） https://go.microsoft.com/fwlink/?LinkId=182554) 。</span><span class="sxs-lookup"><span data-stu-id="feae6-181">For more information about junctions, see [article 205524](https://go.microsoft.com/fwlink/?LinkId=182553) in the Microsoft Knowledge Base (https://go.microsoft.com/fwlink/?LinkId=182553), and also the tool [Junction v1.05](https://go.microsoft.com/fwlink/?LinkId=182554) (https://go.microsoft.com/fwlink/?LinkId=182554).</span></span>

**<span data-ttu-id="feae6-182">配置符号链接以引用缓存</span><span class="sxs-lookup"><span data-stu-id="feae6-182">To configure a symbolic link to reference the cache</span></span>**

1.  <span data-ttu-id="feae6-183">在初始部署阶段，在 RDS 服务器主机操作系统上以本地管理员身份打开命令提示符窗口。</span><span class="sxs-lookup"><span data-stu-id="feae6-183">During the initial deployment stage, open a Command Prompt window as a local administrator on the RDS server host operating system.</span></span>

2.  <span data-ttu-id="feae6-184">使用 MKLINK 命令创建符号链接，然后将其配置为指向 Sftfs 文件。</span><span class="sxs-lookup"><span data-stu-id="feae6-184">Create a symbolic link by using the MKLINK command, and then configure it to point to the Sftfs.fsd file.</span></span>

    **     <span data-ttu-id="feae6-185">mklink symlinkname \\\\rdshostserver\\sharefolder\\sftfs.fsd</span><span class="sxs-lookup"><span data-stu-id="feae6-185">mklink symlinkname \\\\rdshostserver\\sharefolder\\sftfs.fsd</span></span>**

3.  <span data-ttu-id="feae6-186">在 VDI 主 VM 映像上，使用 "以**管理员身份运行**" 选项打开命令提示符窗口，并授予远程链接权限，以便 VM 可以访问 VDI 主机操作系统上的符号链接。</span><span class="sxs-lookup"><span data-stu-id="feae6-186">On the VDI Master VM Image, open a Command Prompt window by using the **Run as administrator** option and grant remote link permissions so that the VM can access the symbolic link on the VDI Host operating system.</span></span> <span data-ttu-id="feae6-187">默认情况下，禁用远程链接权限。</span><span class="sxs-lookup"><span data-stu-id="feae6-187">By default, remote link permissions are disabled.</span></span>

    **<span data-ttu-id="feae6-188">fsutil behavior set SymlinkEvaluation R2R：1</span><span class="sxs-lookup"><span data-stu-id="feae6-188">fsutil behavior set SymlinkEvaluation R2R:1</span></span>**

    <span data-ttu-id="feae6-189">**注意** 在存储服务器上，必须启用相应的链接权限。</span><span class="sxs-lookup"><span data-stu-id="feae6-189">**Note** On the storage server, appropriate link permissions must be enabled.</span></span> <span data-ttu-id="feae6-190">根据 link 和 Sftfs 文件的位置，权限为**L2L： 1**或**L2R： 1**或**R2L** ： 1**或 R2R：1。**</span><span class="sxs-lookup"><span data-stu-id="feae6-190">Depending on the location of link and the Sftfs.fsd file, the permissions are **L2L:1** or **L2R:1** or **R2L:1** or **R2R:1**.</span></span>

     

4.  <span data-ttu-id="feae6-191">配置 App-v RDS 客户端时，请将 AppFS 项文件名值设置为等于使用符号链接的 FSD 文件的 UNC 路径。</span><span class="sxs-lookup"><span data-stu-id="feae6-191">When you configure the App-V RDS Client, set the AppFS key FILENAME value equal to the UNC path of the FSD file that is using the symbolic link.</span></span> <span data-ttu-id="feae6-192">例如，将文件名设置为 \\\\VDIHostserver\\Symlinkname。</span><span class="sxs-lookup"><span data-stu-id="feae6-192">For example, set the file name to \\\\VDIHostserver\\Symlinkname.</span></span> <span data-ttu-id="feae6-193">当 App-v 客户端首次访问缓存时，符号链接将向客户端传递一个指向缓存文件的句柄。</span><span class="sxs-lookup"><span data-stu-id="feae6-193">When the App-V client first accesses the cache, the symbolic link passes to the client a handle to the cache file.</span></span> <span data-ttu-id="feae6-194">只要客户端运行，客户端就会继续使用该句柄。</span><span class="sxs-lookup"><span data-stu-id="feae6-194">The client continues to use that handle as long as the client is running.</span></span> <span data-ttu-id="feae6-195">即使现有客户端已打开旧的共享缓存，符号链接的值也可以安全更新。</span><span class="sxs-lookup"><span data-stu-id="feae6-195">The value of the symbolic link can safely be updated even if existing clients have the old shared cache open.</span></span>

5.  <span data-ttu-id="feae6-196">当必须升级程序包或将新程序包添加到缓存时，请按照升级过程中的步骤1到步骤4操作。</span><span class="sxs-lookup"><span data-stu-id="feae6-196">When you must upgrade a package or to add a new package to the cache, follow steps 1 through 4 of the upgrade procedure.</span></span> <span data-ttu-id="feae6-197">然后，删除符号链接并重新创建以指向共享缓存文件的新版本。</span><span class="sxs-lookup"><span data-stu-id="feae6-197">Then, delete the symbolic link and re-create it to point to the new version of the shared cache file.</span></span> <span data-ttu-id="feae6-198">这可保证当 App-v 客户端驱动程序重启时，每个 RDS 服务器都会收到更新的缓存副本。</span><span class="sxs-lookup"><span data-stu-id="feae6-198">This guarantees that each RDS server receives the updated copy of the cache when the App-V client drivers restart.</span></span> <span data-ttu-id="feae6-199">当重新启动 RDS 服务器时，App-v 客户端将收到缓存的更新副本的句柄，因为客户端使用包含更新符号链接的路径。</span><span class="sxs-lookup"><span data-stu-id="feae6-199">When the RDS server is restarted, the App-V client receives a handle to the updated copy of the cache because the client uses the path that contains the updated symbolic link.</span></span> <span data-ttu-id="feae6-200">然后，用户有权访问新的和更新的应用程序。</span><span class="sxs-lookup"><span data-stu-id="feae6-200">Then, the users have access to the new and updated applications.</span></span>

## <span data-ttu-id="feae6-201">相关主题</span><span class="sxs-lookup"><span data-stu-id="feae6-201">Related topics</span></span>


[<span data-ttu-id="feae6-202">如何安装 Application Virtualization Management Server</span><span class="sxs-lookup"><span data-stu-id="feae6-202">How to Install Application Virtualization Management Server</span></span>](how-to-install-application-virtualization-management-server.md)

[<span data-ttu-id="feae6-203">如何手动安装 Application Virtualization Client</span><span class="sxs-lookup"><span data-stu-id="feae6-203">How to Manually Install the Application Virtualization Client</span></span>](how-to-manually-install-the-application-virtualization-client.md)

[<span data-ttu-id="feae6-204">如何使用命令行安装客户端</span><span class="sxs-lookup"><span data-stu-id="feae6-204">How to Install the Client by Using the Command Line</span></span>](how-to-install-the-client-by-using-the-command-line-new.md)

 

 





