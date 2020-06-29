---
title: 为 MED-V 创建 Windows Virtual PC 映像
description: 为 MED-V 创建 Windows Virtual PC 映像
author: dansimp
ms.assetid: fd7c0b1a-0769-4e7b-ad1a-dad19cca081f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: f947479776e84a4c54edb10d583dd21d7ccf6f43
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798107"
---
# <span data-ttu-id="840a9-103">为 MED-V 创建 Windows Virtual PC 映像</span><span class="sxs-lookup"><span data-stu-id="840a9-103">Creating a Windows Virtual PC Image for MED-V</span></span>


<span data-ttu-id="840a9-104">在你可以向用户提供 MED-V 工作区之前，你必须先准备一个虚拟硬盘，用于为 Microsoft 企业版虚拟化（MED-V）2.0 构建 MED-V 工作区安装程序包。</span><span class="sxs-lookup"><span data-stu-id="840a9-104">Before you can deliver a MED-V workspace to users, you have to first prepare a virtual hard disk that you use to build the MED-V workspace installer package for Microsoft Enterprise Desktop Virtualization (MED-V) 2.0.</span></span> <span data-ttu-id="840a9-105">若要准备必要的虚拟硬盘，必须创建包含所需操作系统、更新和软件的 Windows 虚拟 PC 映像，以便你可以在以后将应用程序和 URL 重定向信息部署到用户。</span><span class="sxs-lookup"><span data-stu-id="840a9-105">To prepare the necessary virtual hard disk, you must create a Windows Virtual PC image that contains the required operating system, updates, and software to let you later deploy applications and URL redirection information to users.</span></span> <span data-ttu-id="840a9-106">本部分提供了有关如何创建虚拟硬盘的指南。</span><span class="sxs-lookup"><span data-stu-id="840a9-106">This section provides guidance about how to create the virtual hard disk.</span></span>

<span data-ttu-id="840a9-107">若要创建 MED-V 的虚拟映像，必须执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="840a9-107">To create a virtual image for MED-V, you must follow these steps.</span></span>

1.  [<span data-ttu-id="840a9-108">创建 Windows 虚拟 PC 映像</span><span class="sxs-lookup"><span data-stu-id="840a9-108">Create a Windows Virtual PC image</span></span>](#bkmk-creatingavirtualmachinebyusingmicrosoftvirtualpc)

2.  [<span data-ttu-id="840a9-109">在映像上安装 Windows XP</span><span class="sxs-lookup"><span data-stu-id="840a9-109">Install Windows XP on the image</span></span>](#bkmk-installingwindowsxpontovpc)

3.  [<span data-ttu-id="840a9-110">在映像上安装 .NET Framework</span><span class="sxs-lookup"><span data-stu-id="840a9-110">Install the .NET Framework on the image</span></span>](#bkmk-installingnet)

4.  [<span data-ttu-id="840a9-111">将更新应用到映像</span><span class="sxs-lookup"><span data-stu-id="840a9-111">Apply updates to the image</span></span>](#bkmk-applypatchestovpc)

5.  [<span data-ttu-id="840a9-112">安装集成组件</span><span class="sxs-lookup"><span data-stu-id="840a9-112">Install Integration Components</span></span>](#bkmk-installintegration)

## <a href="" id="bkmk-creatingavirtualmachinebyusingmicrosoftvirtualpc"></a><span data-ttu-id="840a9-113">创建 Windows 虚拟 PC 映像</span><span class="sxs-lookup"><span data-stu-id="840a9-113">Creating a Windows Virtual PC Image</span></span>


<span data-ttu-id="840a9-114">若要创建 Windows 虚拟 PC 映像，请参阅 Windows 虚拟电脑文档：</span><span class="sxs-lookup"><span data-stu-id="840a9-114">To create a Windows Virtual PC image, see the Windows Virtual PC documentation:</span></span>

-   <span data-ttu-id="840a9-115">[Windows 虚拟 PC 主页](https://go.microsoft.com/fwlink/?LinkId=148103)（ https://go.microsoft.com/fwlink/?LinkId=148103) 。</span><span class="sxs-lookup"><span data-stu-id="840a9-115">[Windows Virtual PC Home Page](https://go.microsoft.com/fwlink/?LinkId=148103) (https://go.microsoft.com/fwlink/?LinkId=148103).</span></span>

-   <span data-ttu-id="840a9-116">[Windows 虚拟电脑帮助](https://go.microsoft.com/fwlink/?LinkId=182378)（ https://go.microsoft.com/fwlink/?LinkId=182378) 。</span><span class="sxs-lookup"><span data-stu-id="840a9-116">[Windows Virtual PC Help](https://go.microsoft.com/fwlink/?LinkId=182378) (https://go.microsoft.com/fwlink/?LinkId=182378).</span></span>

<span data-ttu-id="840a9-117">或者，如果你已有要用作虚拟映像基础的 Windows 映像（WIM）文件，你可以将其转换为用于构建 MED-V 工作区的 VHD。</span><span class="sxs-lookup"><span data-stu-id="840a9-117">Alternately, if you already have a Windows Imaging (WIM) file that you want to use as the basis for your virtual image, you can convert it to a VHD that you use to build the MED-V workspace.</span></span> <span data-ttu-id="840a9-118">有关如何将 WIM 转换为虚拟硬盘的详细信息，请参阅[Windows 7 中的本机 VHD 支持](https://go.microsoft.com/fwlink/?LinkId=195922)（ https://go.microsoft.com/fwlink/?LinkId=195922) 。</span><span class="sxs-lookup"><span data-stu-id="840a9-118">For more information about how to convert a WIM to a virtual hard disk, see [Native VHD Support in Windows 7](https://go.microsoft.com/fwlink/?LinkId=195922) (https://go.microsoft.com/fwlink/?LinkId=195922).</span></span>

<span data-ttu-id="840a9-119">**重要提示** MED-V 在每个虚拟磁盘上仅支持一个虚拟硬盘，每个虚拟磁盘上仅支持一个分区。</span><span class="sxs-lookup"><span data-stu-id="840a9-119">**Important** MED-V only supports one virtual hard disk per virtual machine and only one partition on each virtual disk.</span></span>

 

<span data-ttu-id="840a9-120">创建虚拟硬盘后，在映像上安装 Windows XP。</span><span class="sxs-lookup"><span data-stu-id="840a9-120">After you have created your virtual hard disk, install Windows XP on the image.</span></span>

## <a href="" id="bkmk-installingwindowsxpontovpc"></a><span data-ttu-id="840a9-121">在 Windows 虚拟 PC 映像上安装 Windows XP</span><span class="sxs-lookup"><span data-stu-id="840a9-121">Installing Windows XP on a Windows Virtual PC Image</span></span>


<span data-ttu-id="840a9-122">在构建 MED-V 工作区之前，MED-V 要求在 Windows 虚拟 PC 映像上安装 Windows XP SP3。</span><span class="sxs-lookup"><span data-stu-id="840a9-122">MED-V requires that Windows XP SP3 is installed on the Windows Virtual PC image before you build the MED-V workspace.</span></span>

<span data-ttu-id="840a9-123">有关如何安装 Windows XP 的详细信息，请参阅[创建虚拟机和安装来宾操作系统](https://go.microsoft.com/fwlink/?LinkId=182379)（ https://go.microsoft.com/fwlink/?LinkId=182379) 。</span><span class="sxs-lookup"><span data-stu-id="840a9-123">For more information about how to install Windows XP, see [Create a virtual machine and install a guest operating system](https://go.microsoft.com/fwlink/?LinkId=182379) (https://go.microsoft.com/fwlink/?LinkId=182379).</span></span>

## <a href="" id="bkmk-installingnet"></a><span data-ttu-id="840a9-124">在 Windows 虚拟 PC 映像上安装 .NET Framework 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="840a9-124">Installing the .NET Framework 3.5 SP1 on a Windows Virtual PC Image</span></span>


<span data-ttu-id="840a9-125">你必须手动将 .NET Framework 3.5 SP1 和更新 KB959209 安装到你准备用于 MED-V 的 Windows 虚拟 PC 映像中。</span><span class="sxs-lookup"><span data-stu-id="840a9-125">You must manually install the .NET Framework 3.5 SP1 and the update KB959209 into the Windows Virtual PC image that you prepare for use with MED-V.</span></span> <span data-ttu-id="840a9-126">更新[KB959209](https://go.microsoft.com/fwlink/?LinkId=204950) （ https://go.microsoft.com/fwlink/?LinkId=204950) 解决几个已知的应用程序兼容性问题。</span><span class="sxs-lookup"><span data-stu-id="840a9-126">The update [KB959209](https://go.microsoft.com/fwlink/?LinkId=204950) (https://go.microsoft.com/fwlink/?LinkId=204950) addresses several known application compatibility issues.</span></span>

## <a href="" id="bkmk-applypatchestovpc"></a><span data-ttu-id="840a9-127">将更新应用到 Windows 虚拟 PC 映像</span><span class="sxs-lookup"><span data-stu-id="840a9-127">Applying Updates to the Windows Virtual PC Image</span></span>


<span data-ttu-id="840a9-128">在虚拟机上安装 Windows XP 后，在映像上安装任何所需的 Windows XP 更新（如 SP3）。</span><span class="sxs-lookup"><span data-stu-id="840a9-128">After you have installed Windows XP on your virtual machine, install any required Windows XP updates on the image, such as SP3.</span></span> <span data-ttu-id="840a9-129">你还可以安装某些可选更新，以获得更佳性能。</span><span class="sxs-lookup"><span data-stu-id="840a9-129">You can also install certain optional updates for better performance.</span></span>

<span data-ttu-id="840a9-130">**重要提示** MED-V 要求在来宾操作系统上运行 Windows XP SP3。</span><span class="sxs-lookup"><span data-stu-id="840a9-130">**Important** MED-V requires that Windows XP SP3 be running on the guest operating system.</span></span>

 

<span data-ttu-id="840a9-131">**警告** 在安装 Windows XP 更新时，请确保你在要在 MED-V 工作区中使用的来宾中保留了 Internet Explorer 的版本。</span><span class="sxs-lookup"><span data-stu-id="840a9-131">**Warning** When you install updates to Windows XP, make sure that you remain on the version of Internet Explorer in the guest that you intend to use in the MED-V workspace.</span></span> <span data-ttu-id="840a9-132">例如，如果你打算在 MED-V 工作区中运行 Internet Explorer 6，请确保现在安装的任何更新不包括 Internet Explorer 7 或 Internet Explorer 8。</span><span class="sxs-lookup"><span data-stu-id="840a9-132">For example, if you intend to run Internet Explorer 6 in the MED-V workspace, make sure that any updates that you install now do not include Internet Explorer 7 or Internet Explorer 8.</span></span> <span data-ttu-id="840a9-133">此外，建议配置注册表以防止自动更新升级 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="840a9-133">In addition, we recommend that you configure the registry to prevent automatic updates from upgrading Internet Explorer.</span></span>

 

### <span data-ttu-id="840a9-134">安装可选的性能更新</span><span class="sxs-lookup"><span data-stu-id="840a9-134">Installing an Optional Performance Update</span></span>

<span data-ttu-id="840a9-135">尽管这是可选的，但我们建议你安装以下[修补程序 KB972435](https://go.microsoft.com/fwlink/?LinkId=201077)更新（ https://go.microsoft.com/fwlink/?LinkId=201077) 。</span><span class="sxs-lookup"><span data-stu-id="840a9-135">Although it is optional, we recommend that you install the following update for [hotfix KB972435](https://go.microsoft.com/fwlink/?LinkId=201077) (https://go.microsoft.com/fwlink/?LinkId=201077).</span></span> <span data-ttu-id="840a9-136">此更新提高了终端服务会话中共享文件夹的性能：</span><span class="sxs-lookup"><span data-stu-id="840a9-136">This update increases the performance of shared folders in a Terminal Services session:</span></span>

<span data-ttu-id="840a9-137">**注意** 该更新已公开提供。</span><span class="sxs-lookup"><span data-stu-id="840a9-137">**Note** The update is publicly available.</span></span> <span data-ttu-id="840a9-138">但是，系统可能会提示您接受 Microsoft 服务协议。</span><span class="sxs-lookup"><span data-stu-id="840a9-138">However, you might be prompted to accept an agreement for Microsoft Services.</span></span> <span data-ttu-id="840a9-139">按照后续网页上的提示检索此修补程序。</span><span class="sxs-lookup"><span data-stu-id="840a9-139">Follow the prompts on the successive webpages to retrieve this hotfix.</span></span>

 

### <span data-ttu-id="840a9-140">配置组策略性能更新</span><span class="sxs-lookup"><span data-stu-id="840a9-140">Configuring a Group Policy Performance Update</span></span>

<span data-ttu-id="840a9-141">默认情况下，组策略一次下载到计算机一个字节。</span><span class="sxs-lookup"><span data-stu-id="840a9-141">By default, Group Policy is downloaded to a computer one byte at a time.</span></span> <span data-ttu-id="840a9-142">这将导致在 MED-V 加入到域时出现延迟。</span><span class="sxs-lookup"><span data-stu-id="840a9-142">This causes delays while MED-V is being joined to the domain.</span></span> <span data-ttu-id="840a9-143">若要提高组策略的性能，请将以下注册表项值设置为注册表：</span><span class="sxs-lookup"><span data-stu-id="840a9-143">To increase the performance of Group Policy, set the following registry key value to the registry:</span></span>

<span data-ttu-id="840a9-144">注册表子项： HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon</span><span class="sxs-lookup"><span data-stu-id="840a9-144">Registry subkey: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon</span></span>

<span data-ttu-id="840a9-145">Entry： BufferPolicyReads</span><span class="sxs-lookup"><span data-stu-id="840a9-145">Entry: BufferPolicyReads</span></span>

<span data-ttu-id="840a9-146">类型：DWORD</span><span class="sxs-lookup"><span data-stu-id="840a9-146">Type: DWORD</span></span>

<span data-ttu-id="840a9-147">值：1</span><span class="sxs-lookup"><span data-stu-id="840a9-147">Value: 1</span></span>

## <a href="" id="bkmk-installintegration"></a><span data-ttu-id="840a9-148">安装集成组件</span><span class="sxs-lookup"><span data-stu-id="840a9-148">Installing Integration Components</span></span>


<span data-ttu-id="840a9-149">Windows 虚拟 PC 包括集成组件程序包。</span><span class="sxs-lookup"><span data-stu-id="840a9-149">Windows Virtual PC includes the Integration Components package.</span></span> <span data-ttu-id="840a9-150">这提供了改进虚拟环境和物理计算机之间的交互的功能。</span><span class="sxs-lookup"><span data-stu-id="840a9-150">This provides features that improve the interaction between the virtual environment and the physical computer.</span></span> <span data-ttu-id="840a9-151">例如，"集成组件" 程序包允许你在主机和来宾计算机之间移动鼠标。</span><span class="sxs-lookup"><span data-stu-id="840a9-151">For example, the Integration Components package lets your mouse move between the host and the guest computers.</span></span>

<span data-ttu-id="840a9-152">**重要提示** MED-V 需要安装集成组件程序包。</span><span class="sxs-lookup"><span data-stu-id="840a9-152">**Important** MED-V requires the installation of the Integration Components package.</span></span>

 

<span data-ttu-id="840a9-153">将虚拟映像配置为与 MED-V 配合使用时，必须在来宾操作系统上手动安装集成组件程序包，以使集成功能可用。</span><span class="sxs-lookup"><span data-stu-id="840a9-153">When you configure the virtual image to work with MED-V, you must manually install the Integration Components package on the guest operating system to make the integration features that are available.</span></span>

<span data-ttu-id="840a9-154">有关如何安装和使用集成组件程序包的详细信息，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="840a9-154">For more information about how to install and use the Integration Components package, see the following:</span></span>

-   <span data-ttu-id="840a9-155">[安装或升级集成组件程序包](https://go.microsoft.com/fwlink/?LinkId=195923)（ https://go.microsoft.com/fwlink/?LinkId=195923) 。</span><span class="sxs-lookup"><span data-stu-id="840a9-155">[Install or Upgrade the Integration Components Package](https://go.microsoft.com/fwlink/?LinkId=195923) (https://go.microsoft.com/fwlink/?LinkId=195923).</span></span>

-   <span data-ttu-id="840a9-156">[关于集成功能](https://go.microsoft.com/fwlink/?LinkId=195924)（ https://go.microsoft.com/fwlink/?LinkId=195924) 。</span><span class="sxs-lookup"><span data-stu-id="840a9-156">[About Integration Features](https://go.microsoft.com/fwlink/?LinkId=195924) (https://go.microsoft.com/fwlink/?LinkId=195924).</span></span>

### <span data-ttu-id="840a9-157">安装 RemoteApp 更新</span><span class="sxs-lookup"><span data-stu-id="840a9-157">Installing RemoteApp Update</span></span>

<span data-ttu-id="840a9-158">安装集成组件程序包后，系统将提示你安装以下更新： "适用于 Windows XP SP3 的更新以启用 RemoteApp"。</span><span class="sxs-lookup"><span data-stu-id="840a9-158">After you install the Integration Components package, you are prompted to install the following update: "Update for Windows XP SP3 to enable RemoteApp."</span></span> <span data-ttu-id="840a9-159">这是 MED-V 的必需组件。</span><span class="sxs-lookup"><span data-stu-id="840a9-159">This is a required component for MED-V.</span></span>

<span data-ttu-id="840a9-160">**重要提示** 如果系统未提示您安装 RemoteApp 更新，则必须手动下载并安装。</span><span class="sxs-lookup"><span data-stu-id="840a9-160">**Important** If you are not prompted to install the RemoteApp update, you must download and install it manually.</span></span> <span data-ttu-id="840a9-161">有关如何下载此更新的详细信息和说明，请参阅[WINDOWS XP SP3 更新以启用 RemoteApp](https://go.microsoft.com/fwlink/?LinkId=195925) （ https://go.microsoft.com/fwlink/?LinkId=195925) 。</span><span class="sxs-lookup"><span data-stu-id="840a9-161">For more information and instructions about how to download this update, see [Update for Windows XP SP3 to enable RemoteApp](https://go.microsoft.com/fwlink/?LinkId=195925) (https://go.microsoft.com/fwlink/?LinkId=195925).</span></span>

 

### <span data-ttu-id="840a9-162">启用远程桌面</span><span class="sxs-lookup"><span data-stu-id="840a9-162">Enabling Remote Desktop</span></span>

<span data-ttu-id="840a9-163">默认情况下，安装集成组件程序包后，将启用远程桌面。</span><span class="sxs-lookup"><span data-stu-id="840a9-163">By default, Remote Desktop is enabled after you install the Integration Components package.</span></span> <span data-ttu-id="840a9-164">要使 MED-V 能够正常运行，请确保已启用远程桌面，并且不分发任何禁用它的组策略。</span><span class="sxs-lookup"><span data-stu-id="840a9-164">For MED-V to be operational, ensure that Remote Desktop is enabled, and do not distribute any Group Policy that disables it.</span></span>

<span data-ttu-id="840a9-165">有关如何启用远程桌面的信息，请参阅[启用或禁用远程桌面](https://go.microsoft.com/fwlink/?LinkId=201162)（ https://go.microsoft.com/fwlink/?LinkId=201162) 。</span><span class="sxs-lookup"><span data-stu-id="840a9-165">For information about how to enable Remote Desktop, see [Enable or disable Remote Desktop](https://go.microsoft.com/fwlink/?LinkId=201162) (https://go.microsoft.com/fwlink/?LinkId=201162).</span></span>

## <span data-ttu-id="840a9-166">使用 Internet Explorer 管理工具包自定义 Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="840a9-166">Customizing Internet Explorer by Using the Internet Explorer Administration Kit</span></span>


<span data-ttu-id="840a9-167">如果需要，您可以使用 Internet Explorer 管理工具包自定义来宾操作系统上的 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="840a9-167">If you want, you can use the Internet Explorer Administration Kit to customize Internet Explorer on the guest operating system.</span></span> <span data-ttu-id="840a9-168">有关详细信息，请参阅[Internet Explorer 6 管理工具包和部署指南](https://go.microsoft.com/fwlink/?LinkId=200007)（http://go.microsoft.com/fwlink/?LinkId=200007）。</span><span class="sxs-lookup"><span data-stu-id="840a9-168">For more information, see the [Internet Explorer 6 Administration Kit and Deployment Guide](https://go.microsoft.com/fwlink/?LinkId=200007) (http:// go.microsoft.com/fwlink/?LinkId=200007).</span></span>

<span data-ttu-id="840a9-169">**警告** 应考虑与在 MED-V 工作区中自定义 Internet Explorer 相关的安全问题。</span><span class="sxs-lookup"><span data-stu-id="840a9-169">**Warning** You should consider security concerns associated with customizing Internet Explorer in the MED-V workspace.</span></span> <span data-ttu-id="840a9-170">有关详细信息，请参阅[Med-v 操作的安全最佳做法](security-best-practices-for-med-v-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="840a9-170">For more information, see [Security Best Practices for MED-V Operations](security-best-practices-for-med-v-operations.md).</span></span>

 

<span data-ttu-id="840a9-171">使用最新的来宾操作系统安装虚拟硬盘后，您可以在映像上安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="840a9-171">After your virtual hard disk is installed with an up-to-date guest operating system, you can install applications on the image.</span></span>

## <span data-ttu-id="840a9-172">相关主题</span><span class="sxs-lookup"><span data-stu-id="840a9-172">Related topics</span></span>


[<span data-ttu-id="840a9-173">在 Windows Virtual PC 映像上安装应用程序</span><span class="sxs-lookup"><span data-stu-id="840a9-173">Installing Applications on a Windows Virtual PC Image</span></span>](installing-applications-on-a-windows-virtual-pc-image.md)

[<span data-ttu-id="840a9-174">为 MED-V 配置 Windows Virtual PC 映像</span><span class="sxs-lookup"><span data-stu-id="840a9-174">Configuring a Windows Virtual PC Image for MED-V</span></span>](configuring-a-windows-virtual-pc-image-for-med-v.md)

 

 





