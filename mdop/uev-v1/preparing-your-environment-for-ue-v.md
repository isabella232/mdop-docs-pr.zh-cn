---
title: 为 UE-V 准备你的环境
description: 为 UE-V 准备你的环境
author: dansimp
ms.assetid: c93d3b33-e032-451a-9e1b-8534e1625396
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8f806f3c326bad5204a7f1ee69e11b61177e3cce
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803610"
---
# <span data-ttu-id="8b21c-103">为 UE-V 准备你的环境</span><span class="sxs-lookup"><span data-stu-id="8b21c-103">Preparing Your Environment for UE-V</span></span>


<span data-ttu-id="8b21c-104">Microsoft 用户体验虚拟化（UE-V）通过使用设置存储位置在计算机之间漫游设置。</span><span class="sxs-lookup"><span data-stu-id="8b21c-104">Microsoft User Experience Virtualization (UE-V) roams settings between computers by the use of a settings storage location.</span></span> <span data-ttu-id="8b21c-105">设置存储位置是一个文件共享，应在 UE-V Agent 部署期间进行配置。</span><span class="sxs-lookup"><span data-stu-id="8b21c-105">The settings storage location is a file share and should be configured during the UE-V Agent deployment.</span></span> <span data-ttu-id="8b21c-106">它必须定义为 "设置存储位置" 或 "作为 Active Directory 主目录"。</span><span class="sxs-lookup"><span data-stu-id="8b21c-106">It must be defined either as a settings storage location or as an Active Directory home directory.</span></span> <span data-ttu-id="8b21c-107">此外，管理员应将时间服务器配置为支持一致同步。</span><span class="sxs-lookup"><span data-stu-id="8b21c-107">In addition, the administrator should configure a time server to support consistent synchronization.</span></span> <span data-ttu-id="8b21c-108">若要为 UE-V 准备环境，应考虑以下事项：</span><span class="sxs-lookup"><span data-stu-id="8b21c-108">To prepare your environment for UE-V, you should consider the following:</span></span>

-   <span data-ttu-id="8b21c-109">[Ue-v 设置存储](#bkmk-uevsettingsstorage)：</span><span class="sxs-lookup"><span data-stu-id="8b21c-109">[UE-V Settings Storage](#bkmk-uevsettingsstorage):</span></span>

    -   [<span data-ttu-id="8b21c-110">定义设置存储位置</span><span class="sxs-lookup"><span data-stu-id="8b21c-110">Defining a Settings Storage Location</span></span>](#bkmk-definingsettingsstoragelocation)

    -   [<span data-ttu-id="8b21c-111">通过 UE-V 使用 Active Directory 主目录</span><span class="sxs-lookup"><span data-stu-id="8b21c-111">Using Active Directory Home Directory with UE-V</span></span>](#bkmk-usingactivedirectoryhomedirectory)

-   [<span data-ttu-id="8b21c-112">同步 UE-V 设置同步的计算机时钟</span><span class="sxs-lookup"><span data-stu-id="8b21c-112">Synchronize Computer Clocks for UE-V Settings Synchronization</span></span>](#bkmk-synchronizecomputerclocks)

-   [<span data-ttu-id="8b21c-113">性能和容量规划</span><span class="sxs-lookup"><span data-stu-id="8b21c-113">Performance and Capacity Planning</span></span>](#bkmk-performancecapacityplanning)

<span data-ttu-id="8b21c-114">有关操作系统和计算机要求的详细信息，请参阅[ue-v 1.0 支持的配置](supported-configurations-for-ue-v-10.md)。</span><span class="sxs-lookup"><span data-stu-id="8b21c-114">For more information about operating system and computer requirements, see [Supported Configurations for UE-V 1.0](supported-configurations-for-ue-v-10.md).</span></span>

## <a href="" id="bkmk-uevsettingsstorage"></a><span data-ttu-id="8b21c-115">UE-V 设置存储</span><span class="sxs-lookup"><span data-stu-id="8b21c-115">UE-V settings storage</span></span>


<span data-ttu-id="8b21c-116">你可以使用以下两种配置之一定义用户体验虚拟化设置存储：设置存储位置或 Active Directory 主目录。</span><span class="sxs-lookup"><span data-stu-id="8b21c-116">You can define the User Experience Virtualization settings storage in one of two configurations: a settings storage location or an Active Directory home directory.</span></span>

### <a href="" id="bkmk-definingsettingsstoragelocation"></a><span data-ttu-id="8b21c-117">定义设置存储位置</span><span class="sxs-lookup"><span data-stu-id="8b21c-117">Define a settings storage location</span></span>

<span data-ttu-id="8b21c-118">UE-V 设置存储位置是可由 UE-V 用户访问的标准网络共享。</span><span class="sxs-lookup"><span data-stu-id="8b21c-118">The UE-V settings storage location is a standard network share that is accessible by UE-V users.</span></span> <span data-ttu-id="8b21c-119">在定义设置存储位置之前，必须创建根目录。</span><span class="sxs-lookup"><span data-stu-id="8b21c-119">Before you define the settings storage location, you must create a root directory.</span></span> <span data-ttu-id="8b21c-120">将在共享上存储设置的用户必须具有对该存储位置的读/写权限。</span><span class="sxs-lookup"><span data-stu-id="8b21c-120">Users who will store settings on the share must have read/write permissions to the storage location.</span></span> <span data-ttu-id="8b21c-121">UE-V Agent 将在此根目录下创建特定于用户的文件夹。</span><span class="sxs-lookup"><span data-stu-id="8b21c-121">The UE-V Agent will create user-specific folders under this root directory.</span></span> <span data-ttu-id="8b21c-122">设置存储位置通过设置**SettingsStoragePath**配置选项来定义。</span><span class="sxs-lookup"><span data-stu-id="8b21c-122">The settings storage location is defined by setting the **SettingsStoragePath** configuration option.</span></span> <span data-ttu-id="8b21c-123">可通过以下方式配置此选项：</span><span class="sxs-lookup"><span data-stu-id="8b21c-123">This option can be configured in the following ways:</span></span>

-   <span data-ttu-id="8b21c-124">通过命令行参数或在批处理脚本中安装 UE-V agent 期间。</span><span class="sxs-lookup"><span data-stu-id="8b21c-124">During the installation of the UE-V agent through a command-line parameter or in a batch script.</span></span>

-   <span data-ttu-id="8b21c-125">使用组策略。</span><span class="sxs-lookup"><span data-stu-id="8b21c-125">Using Group Policy.</span></span>

-   <span data-ttu-id="8b21c-126">在安装之后，使用 PowerShell 或 WMI。</span><span class="sxs-lookup"><span data-stu-id="8b21c-126">After installation, by using PowerShell or WMI.</span></span>

<span data-ttu-id="8b21c-127">路径必须位于服务器和共享的通用命名约定（UNC）路径中。</span><span class="sxs-lookup"><span data-stu-id="8b21c-127">The path must be in a universal naming convention (UNC) path of the server and share.</span></span> <span data-ttu-id="8b21c-128">例如， **\\\\server\\settingsshare\\**。</span><span class="sxs-lookup"><span data-stu-id="8b21c-128">For example, **\\\\server\\settingsshare\\**.</span></span> <span data-ttu-id="8b21c-129">此配置选项支持使用变量来启用特定的漫游方案。</span><span class="sxs-lookup"><span data-stu-id="8b21c-129">This configuration option supports the use of variables to enable specific roaming scenarios.</span></span>

<span data-ttu-id="8b21c-130">你可以将 `%username%` 变量与服务器的 UNC 路径配合使用，并进行共享。</span><span class="sxs-lookup"><span data-stu-id="8b21c-130">You can use the `%username%` variable with the UNC path of the server and share.</span></span> <span data-ttu-id="8b21c-131">这将在用户登录的所有计算机或会话上提供相同的设置体验。</span><span class="sxs-lookup"><span data-stu-id="8b21c-131">This will provide the same settings experience on all computers or sessions that a user logs into.</span></span> <span data-ttu-id="8b21c-132">在以下情况下，请考虑此配置：</span><span class="sxs-lookup"><span data-stu-id="8b21c-132">Consider this configuration for the following scenarios:</span></span>

1.  <span data-ttu-id="8b21c-133">企业中的用户具有多个同样配置的物理计算机，并且每个用户的设置在所有计算机上都应该是相同的。</span><span class="sxs-lookup"><span data-stu-id="8b21c-133">Users in the enterprise have multiple, similarly configured physical computers and each user’s settings should be the same across all computers.</span></span>

2.  <span data-ttu-id="8b21c-134">企业中的用户使用虚拟桌面基础结构（VDI）池，应在每个用户的 VDI 会话中保留设置。</span><span class="sxs-lookup"><span data-stu-id="8b21c-134">Users in the enterprise use virtual desktop infrastructure (VDI) pools where settings should be retained across each user’s VDI sessions.</span></span>

3.  <span data-ttu-id="8b21c-135">企业中的用户有一台物理计算机，另外还使用 VDI。</span><span class="sxs-lookup"><span data-stu-id="8b21c-135">Users in the enterprise have one physical computer and additionally use a VDI.</span></span> <span data-ttu-id="8b21c-136">无论使用物理计算机还是 VDI 会话，每个用户的设置体验都应相同。</span><span class="sxs-lookup"><span data-stu-id="8b21c-136">Each user’s settings experience should be the same whether using the physical computer or VDI session.</span></span>

4.  <span data-ttu-id="8b21c-137">多个用户使用多个企业计算机。</span><span class="sxs-lookup"><span data-stu-id="8b21c-137">Multiple enterprise computers are used by multiple users.</span></span> <span data-ttu-id="8b21c-138">每个用户的设置体验在所有计算机上都应该是相同的。</span><span class="sxs-lookup"><span data-stu-id="8b21c-138">Each user’s settings experience should be the same across all computers.</span></span>

<span data-ttu-id="8b21c-139">你可以将 **%username%\\%computername%** 变量与服务器的 UNC 路径一起使用，并进行共享。</span><span class="sxs-lookup"><span data-stu-id="8b21c-139">You can use the **%username%\\%computername%** variables with the UNC path of the server and share.</span></span> <span data-ttu-id="8b21c-140">这将保留每台计算机的设置体验。</span><span class="sxs-lookup"><span data-stu-id="8b21c-140">This will preserve the settings experience for each computer.</span></span> <span data-ttu-id="8b21c-141">在以下情况下，请考虑此配置：</span><span class="sxs-lookup"><span data-stu-id="8b21c-141">Consider this configuration for the following scenarios:</span></span>

1.  <span data-ttu-id="8b21c-142">企业中的用户拥有多台物理计算机，并且您希望保留每台计算机的设置体验。</span><span class="sxs-lookup"><span data-stu-id="8b21c-142">Users in the enterprise have multiple physical computers and you want to preserve the settings experience for each computer.</span></span>

2.  <span data-ttu-id="8b21c-143">企业计算机由多个用户使用。</span><span class="sxs-lookup"><span data-stu-id="8b21c-143">The enterprise computers are used by multiple users.</span></span> <span data-ttu-id="8b21c-144">应为用户登录的每台计算机保留设置体验。</span><span class="sxs-lookup"><span data-stu-id="8b21c-144">The settings experience should be preserved for each computer that the user logs into.</span></span>

<span data-ttu-id="8b21c-145">UE-V agent 基于 UE-V `SettingsStoragePath` 配置设置和定义的变量动态创建特定于用户的设置存储路径。</span><span class="sxs-lookup"><span data-stu-id="8b21c-145">The UE-V agent dynamically creates the user-specific settings storage path based on a UE-V `SettingsStoragePath` configuration setting and the variables that are defined.</span></span>

<span data-ttu-id="8b21c-146">UE-V agent 将动态创建 `SettingsPackages` 在每个特定于用户的存储位置中指定的隐藏系统文件夹。</span><span class="sxs-lookup"><span data-stu-id="8b21c-146">The UE-V agent dynamically creates a hidden system folder named `SettingsPackages` within each user-specific storage location.</span></span> <span data-ttu-id="8b21c-147">UE-V agent 读取并将设置写入到由注册的 UE-V 设置位置模板定义的位置。</span><span class="sxs-lookup"><span data-stu-id="8b21c-147">The UE-V agent reads and writes settings to this location as defined by registered UE-V settings location templates.</span></span>

<span data-ttu-id="8b21c-148">如果用户的一组托管计算机的设置存储位置相同，则适用的 UE-V 设置由 "最后一次写入的 wins" 规则确定。</span><span class="sxs-lookup"><span data-stu-id="8b21c-148">If the settings storage location is the same for a set of managed computers of a user, the applicable UE-V settings are determined by a “Last write wins” rule.</span></span> <span data-ttu-id="8b21c-149">在一台计算机上运行的代理独立于在其他计算机上运行的代理读取和写入设置位置。</span><span class="sxs-lookup"><span data-stu-id="8b21c-149">The agent that runs on one computer reads and writes to the settings location independently of agents that run on other computers.</span></span> <span data-ttu-id="8b21c-150">最后写入的设置和值是在下一个代理从设置存储位置读取时应用的设置。</span><span class="sxs-lookup"><span data-stu-id="8b21c-150">The last settings and values written are the settings that are applied when the next agent reads from the settings storage location.</span></span> <span data-ttu-id="8b21c-151">有关详细信息，请参阅[部署 ue-v 1.0 的设置存储位置](deploying-the-settings-storage-location-for-ue-v-10.md)。</span><span class="sxs-lookup"><span data-stu-id="8b21c-151">For more information, see [Deploying the Settings Storage Location for UE-V 1.0](deploying-the-settings-storage-location-for-ue-v-10.md).</span></span>

### <a href="" id="bkmk-usingactivedirectoryhomedirectory"></a><span data-ttu-id="8b21c-152">通过 UE-V 使用 Active Directory 主目录</span><span class="sxs-lookup"><span data-stu-id="8b21c-152">Use Active Directory home directory with UE-V</span></span>

<span data-ttu-id="8b21c-153">如果在部署代理时没有为 UE-V 配置设置存储位置，则用户的 Active Directory （AD）主目录将用于存储设置位置程序包。</span><span class="sxs-lookup"><span data-stu-id="8b21c-153">If no settings storage location is configured for UE-V when the agent is deployed, then the user’s Active Directory (AD) home directory is used to store settings location packages.</span></span> <span data-ttu-id="8b21c-154">UE-V agent 将在每个用户的广告主目录的根下动态创建 "设置存储" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="8b21c-154">The UE-V agent dynamically creates the settings storage folder below the root of the AD home directory of each user.</span></span> <span data-ttu-id="8b21c-155">如果未另外定义设置存储位置（SettingsStoragePath），则代理仅使用 Active Directory 主目录。</span><span class="sxs-lookup"><span data-stu-id="8b21c-155">The agent only uses the Active Directory home directory if a settings storage location (SettingsStoragePath) is not otherwise defined.</span></span>

## <a href="" id="bkmk-synchronizecomputerclocks"></a><span data-ttu-id="8b21c-156">同步 UE-V 设置同步的计算机时钟</span><span class="sxs-lookup"><span data-stu-id="8b21c-156">Synchronize computer clocks for UE-V settings synchronization</span></span>


<span data-ttu-id="8b21c-157">运行 UE-V agent 以同步设置的计算机必须使用时间服务器。</span><span class="sxs-lookup"><span data-stu-id="8b21c-157">Computers that run the UE-V agent to synchronize settings must use a time server.</span></span> <span data-ttu-id="8b21c-158">时间戳用于确定是否需要从设置存储位置同步设置。</span><span class="sxs-lookup"><span data-stu-id="8b21c-158">Time stamps are used to determine if settings need to be synchronized from the settings storage location.</span></span> <span data-ttu-id="8b21c-159">如果计算机时钟不准确，则较旧的设置可能会覆盖较新的设置，或者新设置可能不会保存到设置存储位置。</span><span class="sxs-lookup"><span data-stu-id="8b21c-159">If the computer clock is inaccurate, older settings can overwrite newer settings, or the new settings might not be saved to the settings storage location.</span></span> <span data-ttu-id="8b21c-160">使用时间服务器使 UE-V 能够保持一致的设置体验。</span><span class="sxs-lookup"><span data-stu-id="8b21c-160">The use of a time server enables UE-V to maintain a consistent settings experience.</span></span>

## <a href="" id="bkmk-performancecapacityplanning"></a><span data-ttu-id="8b21c-161">性能和容量规划</span><span class="sxs-lookup"><span data-stu-id="8b21c-161">Performance and capacity planning</span></span>


<span data-ttu-id="8b21c-162">UE-V 的容量要求可以通过使用标准磁盘容量和网络运行状况监视来确定。</span><span class="sxs-lookup"><span data-stu-id="8b21c-162">Capacity requirements for UE-V can be determined by use of standard disk capacity and network health monitoring.</span></span> <span data-ttu-id="8b21c-163">UE-V 使用服务器消息块（SMB）共享存储设置程序包。</span><span class="sxs-lookup"><span data-stu-id="8b21c-163">UE-V uses a Server Message Block (SMB) share for the storage of settings packages.</span></span> <span data-ttu-id="8b21c-164">设置包的大小根据特定应用程序的设置信息而有所不同。</span><span class="sxs-lookup"><span data-stu-id="8b21c-164">The size of settings packages varies depending on the settings information for a specific application.</span></span> <span data-ttu-id="8b21c-165">虽然大多数设置程序包较小，但同步可能较大的文件（如桌面映像）可能会导致性能较差，尤其是在速度较慢的网络上。</span><span class="sxs-lookup"><span data-stu-id="8b21c-165">While most settings packages are small, the synchronization of potentially large files, such as desktop images, can result in poor performance, particularly on slower networks.</span></span> <span data-ttu-id="8b21c-166">若要最大限度地减少网络延迟问题，应在用户计算机所在的同一本地网络上创建设置存储位置。</span><span class="sxs-lookup"><span data-stu-id="8b21c-166">To minimize problems with network latency, you should create settings storage locations on the same local networks where the users’ computers reside.</span></span>

<span data-ttu-id="8b21c-167">默认情况下，如果网络速度较慢或设置包较大，则 UE-V 同步将在2秒钟后超时。</span><span class="sxs-lookup"><span data-stu-id="8b21c-167">By default, the UE-V synchronization will time out after 2 seconds if the network is slow or the settings package is large.</span></span> <span data-ttu-id="8b21c-168">你可以通过组策略配置超时。</span><span class="sxs-lookup"><span data-stu-id="8b21c-168">You can configure the timeout with Group Policy.</span></span> <span data-ttu-id="8b21c-169">有关如何设置超时的详细信息，请参阅[通过组策略对象配置 ue-v](configuring-ue-v-with-group-policy-objects.md)。</span><span class="sxs-lookup"><span data-stu-id="8b21c-169">For more information about how to set the timeout, see [Configuring UE-V with Group Policy Objects](configuring-ue-v-with-group-policy-objects.md).</span></span>

## <span data-ttu-id="8b21c-170">相关主题</span><span class="sxs-lookup"><span data-stu-id="8b21c-170">Related topics</span></span>


[<span data-ttu-id="8b21c-171">Microsoft 用户体验虚拟化 (UE-V) 1.0</span><span class="sxs-lookup"><span data-stu-id="8b21c-171">Microsoft User Experience Virtualization (UE-V) 1.0</span></span>](index.md)

[<span data-ttu-id="8b21c-172">规划 UE-V 1.0</span><span class="sxs-lookup"><span data-stu-id="8b21c-172">Planning for UE-V 1.0</span></span>](planning-for-ue-v-10.md)

[<span data-ttu-id="8b21c-173">UE-V 1.0 支持的配置</span><span class="sxs-lookup"><span data-stu-id="8b21c-173">Supported Configurations for UE-V 1.0</span></span>](supported-configurations-for-ue-v-10.md)

 

 





