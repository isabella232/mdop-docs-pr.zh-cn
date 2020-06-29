---
title: 部署 App-V 5.1 Sequencer 和 Client
description: 部署 App-V 5.1 Sequencer 和 Client
author: dansimp
ms.assetid: 74f32794-4c76-436f-a542-f9e95d89063d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: 3b78059e5005f563bb99d7e6f4b5fe0af2eae8d5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798578"
---
# <span data-ttu-id="d8083-103">部署 App-V 5.1 Sequencer 和 Client</span><span class="sxs-lookup"><span data-stu-id="d8083-103">Deploying the App-V 5.1 Sequencer and Client</span></span>


<span data-ttu-id="d8083-104">Microsoft Application Virtualization （App-v） 5.1 Sequencer 和客户端使管理员能够虚拟化和运行虚拟化的应用程序。</span><span class="sxs-lookup"><span data-stu-id="d8083-104">The Microsoft Application Virtualization (App-V) 5.1 Sequencer and client enable administrators to virtualize and run virtualized applications.</span></span>

## <span data-ttu-id="d8083-105">部署客户端</span><span class="sxs-lookup"><span data-stu-id="d8083-105">Deploy the client</span></span>


<span data-ttu-id="d8083-106">App-v 5.1 客户端是在目标计算机上运行虚拟化应用程序的组件。</span><span class="sxs-lookup"><span data-stu-id="d8083-106">The App-V 5.1 client is the component that runs a virtualized application on a target computer.</span></span> <span data-ttu-id="d8083-107">客户端使用户能够与图标交互并双击文件类型，以便他们可以启动虚拟化的应用程序。</span><span class="sxs-lookup"><span data-stu-id="d8083-107">The client enables users to interact with icons and to double-click file types, so that they can start a virtualized application.</span></span> <span data-ttu-id="d8083-108">客户端还可以从管理服务器获取虚拟应用程序内容。</span><span class="sxs-lookup"><span data-stu-id="d8083-108">The client can also obtain the virtual application content from the management server.</span></span>

[<span data-ttu-id="d8083-109">如何部署 App-V Client</span><span class="sxs-lookup"><span data-stu-id="d8083-109">How to Deploy the App-V Client</span></span>](how-to-deploy-the-app-v-client-51gb18030.md)

[<span data-ttu-id="d8083-110">如何卸载 App-V 5.1 Client</span><span class="sxs-lookup"><span data-stu-id="d8083-110">How to Uninstall the App-V 5.1 Client</span></span>](how-to-uninstall-the-app-v-51-client.md)

[<span data-ttu-id="d8083-111">如何在同一台计算机上部署 app-v 4.6 和 app-v 5.1 客户端</span><span class="sxs-lookup"><span data-stu-id="d8083-111">How to Deploy the App-V 4.6 and the App-V 5.1 Client on the Same Computer</span></span>](how-to-deploy-the-app-v-46-and-the-app-v--51-client-on-the-same-computer.md)

## <span data-ttu-id="d8083-112">客户端配置设置</span><span class="sxs-lookup"><span data-stu-id="d8083-112">Client Configuration Settings</span></span>


<span data-ttu-id="d8083-113">App-v 5.1 客户端将其配置存储在注册表中。</span><span class="sxs-lookup"><span data-stu-id="d8083-113">The App-V 5.1 client stores its configuration in the registry.</span></span> <span data-ttu-id="d8083-114">如果你了解注册表中的数据的格式，则可以收集有关客户端的一些有用信息。</span><span class="sxs-lookup"><span data-stu-id="d8083-114">You can gather some useful information about the client if you understand the format of data in the registry.</span></span> <span data-ttu-id="d8083-115">您也可以通过更改注册表项来配置多个客户端操作。</span><span class="sxs-lookup"><span data-stu-id="d8083-115">You can also configure many client actions by changing registry entries.</span></span>

[<span data-ttu-id="d8083-116">关于 Client 配置设置</span><span class="sxs-lookup"><span data-stu-id="d8083-116">About Client Configuration Settings</span></span>](about-client-configuration-settings51.md)

## <span data-ttu-id="d8083-117">使用 ADMX 模板和组策略配置客户端</span><span class="sxs-lookup"><span data-stu-id="d8083-117">Configure the client by using the ADMX template and Group Policy</span></span>


<span data-ttu-id="d8083-118">你可以使用 Microsoft ADMX 模板来配置 app-v 5.1 客户端和远程桌面服务客户端的客户端设置。</span><span class="sxs-lookup"><span data-stu-id="d8083-118">You can use the Microsoft ADMX template to configure the client settings for the App-V 5.1 client and the Remote Desktop Services client.</span></span> <span data-ttu-id="d8083-119">ADMX 模板通过使用现有组策略基础结构管理常见的客户端配置，其中包括 App-v 5.1 客户端配置的设置。</span><span class="sxs-lookup"><span data-stu-id="d8083-119">The ADMX template manages common client configurations by using an existing Group Policy infrastructure and it includes settings for the App-V 5.1 client configuration.</span></span>

<span data-ttu-id="d8083-120">**重要提示** 您可以从 Microsoft 下载中心获取 App-v 5.1 ADMX 模板。</span><span class="sxs-lookup"><span data-stu-id="d8083-120">**Important** You can obtain the App-V 5.1 ADMX template from the Microsoft Download Center.</span></span>

 

<span data-ttu-id="d8083-121">下载并安装 ADMX 模板后，请在将用于管理组策略的计算机上执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="d8083-121">After you download and install the ADMX template, perform the following steps on the computer that you will use to manage Group Policy.</span></span> <span data-ttu-id="d8083-122">这通常是域控制器。</span><span class="sxs-lookup"><span data-stu-id="d8083-122">This is typically the Domain Controller.</span></span>

1.  <span data-ttu-id="d8083-123">将该**admx**文件保存到以下目录： **Windows \\ PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="d8083-123">Save the **.admx** file to the following directory: **Windows \\ PolicyDefinitions**</span></span>

2.  <span data-ttu-id="d8083-124">将**adml**文件保存到以下目录： **Windows \\ PolicyDefinitions \\ &lt; &gt; 语言目录**</span><span class="sxs-lookup"><span data-stu-id="d8083-124">Save the **.adml** file to the following directory: **Windows \\ PolicyDefinitions \\ &lt;Language Directory&gt;**</span></span>

<span data-ttu-id="d8083-125">完成上述步骤后，您可以使用**组策略管理**控制台管理 app-v 5.1 客户端配置设置。</span><span class="sxs-lookup"><span data-stu-id="d8083-125">After you have completed the preceding steps, you can manage the App-V 5.1 client configuration settings with the **Group Policy Management** console.</span></span>

<span data-ttu-id="d8083-126">App-v 5.1 客户端还将其配置存储在注册表中。</span><span class="sxs-lookup"><span data-stu-id="d8083-126">The App-V 5.1 client also stores its configuration in the registry.</span></span> <span data-ttu-id="d8083-127">如果你了解注册表中数据的格式，则可以收集有关客户端的一些有用信息。</span><span class="sxs-lookup"><span data-stu-id="d8083-127">You can gather some useful information about the client if you understand the format of the data in the registry.</span></span> <span data-ttu-id="d8083-128">您也可以通过更改注册表项来配置多个客户端操作。</span><span class="sxs-lookup"><span data-stu-id="d8083-128">You can also configure many client actions by changing registry entries.</span></span>

[<span data-ttu-id="d8083-129">如何使用 ADMX 模板和组策略修改 App-V 5.1 Client 配置</span><span class="sxs-lookup"><span data-stu-id="d8083-129">How to Modify App-V 5.1 Client Configuration Using the ADMX Template and Group Policy</span></span>](how-to-modify-app-v-51-client-configuration-using-the-admx-template-and-group-policy.md)

## <span data-ttu-id="d8083-130">使用 "共享内容存储" 模式部署客户端</span><span class="sxs-lookup"><span data-stu-id="d8083-130">Deploy the client by using the Shared Content Store mode</span></span>


<span data-ttu-id="d8083-131">App-v 5.1 共享内容存储（SCS）模式使 SCS 应用-V 5.1 客户可以运行虚拟化的应用程序，而无需在本地保存任何关联的程序包数据。</span><span class="sxs-lookup"><span data-stu-id="d8083-131">The App-V 5.1 Shared Content Store (SCS) mode enables the SCS App-V 5.1 clients to run virtualized applications without saving any of the associated package data locally.</span></span> <span data-ttu-id="d8083-132">所有需要的虚拟化软件包数据均通过网络传输;因此，你应仅在具有快速连接的环境中使用 SCS 模式。</span><span class="sxs-lookup"><span data-stu-id="d8083-132">All required virtualized package data is transmitted across the network; therefore, you should only use the SCS mode in environments with a fast connection.</span></span> <span data-ttu-id="d8083-133">"SCS" 模式支持远程桌面服务（RDS）和标准版本的 App-v 5.1 客户端。</span><span class="sxs-lookup"><span data-stu-id="d8083-133">Both the Remote Desktop Services (RDS) and the standard version of the App-V 5.1 client are supported with SCS mode.</span></span>

<span data-ttu-id="d8083-134">**重要提示** 如果将 app-v 5.1 客户端配置为在 SCS 模式下运行，则从其流入的 app-v 5.1 程序包的位置必须可用，否则虚拟化程序包将失败。</span><span class="sxs-lookup"><span data-stu-id="d8083-134">**Important** If the App-V 5.1 client is configured to run in the SCS mode, the location where the App-V 5.1 packages are streamed from must be available, otherwise, the virtualized package will fail.</span></span> <span data-ttu-id="d8083-135">此外，我们不建议将虚拟化应用程序部署到在 SCS 模式下通过 internet 运行 app-v 5.1 客户端的计算机。</span><span class="sxs-lookup"><span data-stu-id="d8083-135">Additionally, we do not recommend deployment of virtualized applications to computers that run the App-V 5.1 client in the SCS mode across the internet.</span></span>

 

<span data-ttu-id="d8083-136">此外，SCS 不是包含虚拟化程序包的物理位置。</span><span class="sxs-lookup"><span data-stu-id="d8083-136">Additionally, the SCS is not a physical location that contains virtualized packages.</span></span> <span data-ttu-id="d8083-137">它是一种允许应用-V 5.1 客户端通过网络传输所需的虚拟化包数据的模式。</span><span class="sxs-lookup"><span data-stu-id="d8083-137">It is a mode that allows the App-V 5.1 client to stream the required virtualized package data across the network.</span></span>

<span data-ttu-id="d8083-138">SCS 模式在以下情况下很有用：</span><span class="sxs-lookup"><span data-stu-id="d8083-138">The SCS mode is helpful in the following scenarios:</span></span>

-   <span data-ttu-id="d8083-139">虚拟桌面基础结构（VDI）部署</span><span class="sxs-lookup"><span data-stu-id="d8083-139">Virtual desktop infrastructure (VDI) deployments</span></span>

-   <span data-ttu-id="d8083-140">远程桌面服务（RDS）部署</span><span class="sxs-lookup"><span data-stu-id="d8083-140">Remote desktop services (RDS) deployments</span></span>

<span data-ttu-id="d8083-141">若要在你的环境中使用 SCS，必须启用 app-v 5.1 客户端以在 SCS 模式下运行。</span><span class="sxs-lookup"><span data-stu-id="d8083-141">To use SCS in your environment, you must enable the App-V 5.1 client to run in SCS mode.</span></span> <span data-ttu-id="d8083-142">应在安装期间指定此设置。</span><span class="sxs-lookup"><span data-stu-id="d8083-142">This setting should be specified during installation.</span></span> <span data-ttu-id="d8083-143">默认情况下，客户端未配置为使用 SCS 模式。</span><span class="sxs-lookup"><span data-stu-id="d8083-143">By default, the client is not configured to use SCS mode.</span></span> <span data-ttu-id="d8083-144">如果计划使用 SCS，则应使用建议的过程安装客户端。</span><span class="sxs-lookup"><span data-stu-id="d8083-144">You should install the client by using the suggested procedure if you plan to use SCS.</span></span> <span data-ttu-id="d8083-145">但是，你可以通过在运行 app-v 5.1 客户端的计算机上输入以下 PowerShell 命令来配置现有的应用程序 V 5.1 客户端以在 SCS 模式下运行：</span><span class="sxs-lookup"><span data-stu-id="d8083-145">However, you can configure an existing App-V 5.1 client to run in SCS mode by entering the following PowerShell command on the computer that runs the App-V 5.1 client:</span></span>

**<span data-ttu-id="d8083-146">set-AppvClientConfiguration-SharedContentStoreMode 1</span><span class="sxs-lookup"><span data-stu-id="d8083-146">set-AppvClientConfiguration -SharedContentStoreMode 1</span></span>**

<span data-ttu-id="d8083-147">当管理员在 SCS 模式下运行 App-v 5.1 客户端的计算机上预加载某些虚拟应用程序时，可能会出现这种情况。</span><span class="sxs-lookup"><span data-stu-id="d8083-147">There might be cases when the administrator pre-loads some virtual applications on the computer that runs the App-V 5.1 client in SCS mode.</span></span> <span data-ttu-id="d8083-148">可通过将 PowerShell 命令添加、发布和装载程序包来完成此操作。</span><span class="sxs-lookup"><span data-stu-id="d8083-148">This can be accomplished with PowerShell commands to add, publish, and mount the package.</span></span> <span data-ttu-id="d8083-149">例如，如果在所有计算机上预加载了程序包，则管理员可以使用 PowerShell 命令添加、发布和装入程序包。</span><span class="sxs-lookup"><span data-stu-id="d8083-149">For example, if a package is pre-loaded on all computers, the administrator could add, publish, and mount the package by using PowerShell commands.</span></span> <span data-ttu-id="d8083-150">程序包不会通过网络传输，因为它将在本地存储。</span><span class="sxs-lookup"><span data-stu-id="d8083-150">The package would not stream across the network because it would be locally stored.</span></span>

[<span data-ttu-id="d8083-151">如何针对共享内容存储模式安装 App-V 5.1 Client</span><span class="sxs-lookup"><span data-stu-id="d8083-151">How to Install the App-V 5.1 Client for Shared Content Store Mode</span></span>](how-to-install-the-app-v-51-client-for-shared-content-store-mode.md)

## <span data-ttu-id="d8083-152">部署 Sequencer</span><span class="sxs-lookup"><span data-stu-id="d8083-152">Deploy the Sequencer</span></span>


<span data-ttu-id="d8083-153">Sequencer 是一个工具，用于将标准应用程序转换为虚拟程序包，以便部署到运行 app-v 5.1 客户端的计算机。</span><span class="sxs-lookup"><span data-stu-id="d8083-153">The Sequencer is a tool that is used to convert standard applications into virtual packages for deployment to computers that run the App-V 5.1 client.</span></span> <span data-ttu-id="d8083-154">排序器可提供简单且可预测的转换过程，对之前的排序工作流进行最少的更改。</span><span class="sxs-lookup"><span data-stu-id="d8083-154">The Sequencer helps provide a simple and predictable conversion process with minimal changes to prior sequencing workflows.</span></span> <span data-ttu-id="d8083-155">此外，排序器允许用户更轻松地配置应用程序以启用虚拟化应用程序的连接。</span><span class="sxs-lookup"><span data-stu-id="d8083-155">In addition, the Sequencer allows users to more easily configure applications to enable connections of virtualized applications.</span></span>

<span data-ttu-id="d8083-156">有关 app-v 5.1 排序器中的更改的列表，请参阅[关于 app-V 5.1](about-app-v-51.md)。</span><span class="sxs-lookup"><span data-stu-id="d8083-156">For a list of changes in the App-V 5.1 Sequencer, see [About App-V 5.1](about-app-v-51.md).</span></span>

[<span data-ttu-id="d8083-157">如何安装 Sequencer</span><span class="sxs-lookup"><span data-stu-id="d8083-157">How to Install the Sequencer</span></span>](how-to-install-the-sequencer-51beta-gb18030.md)

## <a href="" id="---------app-v-5-1-client-and-sequencer-logs"></a> <span data-ttu-id="d8083-158">App-v 5.1 客户端和 Sequencer 日志</span><span class="sxs-lookup"><span data-stu-id="d8083-158">App-V 5.1 Client and Sequencer logs</span></span>


<span data-ttu-id="d8083-159">在使用 app-v 5.1 时，可以使用 app-v 5.1 Sequencer 日志信息来帮助解决 Sequencer 安装和操作事件。</span><span class="sxs-lookup"><span data-stu-id="d8083-159">You can use the App-V 5.1 Sequencer log information to help troubleshoot the Sequencer installation and operational events while using App-V 5.1.</span></span> <span data-ttu-id="d8083-160">与排序器相关的日志信息可以通过**事件查看器**进行检查。</span><span class="sxs-lookup"><span data-stu-id="d8083-160">The Sequencer-related log information can be reviewed with the **Event Viewer**.</span></span> <span data-ttu-id="d8083-161">下一行显示与 Sequencer 相关的事件的特定路径：</span><span class="sxs-lookup"><span data-stu-id="d8083-161">The following line displays the specific path for Sequencer-related events:</span></span>

<span data-ttu-id="d8083-162">**事件查看器 \\ 应用程序和服务日志 \\ Microsoft \\ App V**。与排序器相关的事件预置了**AppV \ _Sequencer**。</span><span class="sxs-lookup"><span data-stu-id="d8083-162">**Event Viewer \\ Applications and Services Logs \\ Microsoft \\ App V**. Sequencer-related events are prepended with **AppV\_Sequencer**.</span></span> <span data-ttu-id="d8083-163">与客户端相关的事件预置到**AppV \ _Client**。</span><span class="sxs-lookup"><span data-stu-id="d8083-163">Client-related events are prepended with **AppV\_Client**.</span></span>

## <span data-ttu-id="d8083-164">用于部署 Sequencer 和客户端的其他资源</span><span class="sxs-lookup"><span data-stu-id="d8083-164">Other resources for deploying the Sequencer and client</span></span>


[<span data-ttu-id="d8083-165">部署 App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="d8083-165">Deploying App-V 5.1</span></span>](deploying-app-v-51.md)

[<span data-ttu-id="d8083-166">规划 App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="d8083-166">Planning for App-V 5.1</span></span>](planning-for-app-v-51.md)






 

 





