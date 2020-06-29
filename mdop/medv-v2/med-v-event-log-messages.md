---
title: MED-V 事件日志消息
description: MED-V 事件日志消息
author: dansimp
ms.assetid: 7ba7344d-153b-4cc4-a00a-5d42aee9986b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b5d8dcf1cce48d6c1e29d46b4db7ac1550aa9477
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803296"
---
# <span data-ttu-id="a7c63-103">MED-V 事件日志消息</span><span class="sxs-lookup"><span data-stu-id="a7c63-103">MED-V Event Log Messages</span></span>


<span data-ttu-id="a7c63-104">Microsoft 企业桌面虚拟化（MED-V）2.0 的日志文件提供了有关如何在你的企业中部署和管理 MED-V 的详细信息，并帮助验证功能或帮助解决问题。</span><span class="sxs-lookup"><span data-stu-id="a7c63-104">The log files for Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 provide detailed information about how to deploy and manage MED-V in your enterprise and help verify functionality or help troubleshoot issues.</span></span>

## <span data-ttu-id="a7c63-105">事件 Id</span><span class="sxs-lookup"><span data-stu-id="a7c63-105">Event IDs</span></span>


<span data-ttu-id="a7c63-106">以下是 MED-V 事件 Id 的列表，可帮助解决在部署或管理 MED-V 时可能遇到的问题。</span><span class="sxs-lookup"><span data-stu-id="a7c63-106">The following are a list of MED-V event IDs to help troubleshoot issues that you might encounter when you deploy or manage MED-V.</span></span>

### <span data-ttu-id="a7c63-107">Fts</span><span class="sxs-lookup"><span data-stu-id="a7c63-107">Fts</span></span>

<span data-ttu-id="a7c63-108">显示首次设置的事件 Id。</span><span class="sxs-lookup"><span data-stu-id="a7c63-108">Shows the event IDs for first time setup.</span></span>

### <span data-ttu-id="a7c63-109">事件 ID 3066</span><span class="sxs-lookup"><span data-stu-id="a7c63-109">Event ID 3066</span></span>

<span data-ttu-id="a7c63-110">启动虚拟机操作失败。</span><span class="sxs-lookup"><span data-stu-id="a7c63-110">Start virtual machine operation failed.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a7c63-111">描述</span><span class="sxs-lookup"><span data-stu-id="a7c63-111">Description</span></span>**  
<span data-ttu-id="a7c63-112">你用于创建 MED-V 工作区的虚拟硬盘（VHD）存在潜在问题。</span><span class="sxs-lookup"><span data-stu-id="a7c63-112">A potential problem exists with the virtual hard disk (VHD) that you are using to create a MED-V workspace.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a7c63-113">解决方案</span><span class="sxs-lookup"><span data-stu-id="a7c63-113">Solution</span></span>**  
<span data-ttu-id="a7c63-114">验证你是否可以使用适用于 MED-V 的 VHD 创建虚拟机以及它是否可以启动。</span><span class="sxs-lookup"><span data-stu-id="a7c63-114">Verify that you can create a virtual machine with the VHD for MED-V and that it can be started.</span></span>

### <span data-ttu-id="a7c63-115">事件 ID 3071</span><span class="sxs-lookup"><span data-stu-id="a7c63-115">Event ID 3071</span></span>

<span data-ttu-id="a7c63-116">虚拟机准备失败。</span><span class="sxs-lookup"><span data-stu-id="a7c63-116">Virtual machine preparation failed.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a7c63-117">描述</span><span class="sxs-lookup"><span data-stu-id="a7c63-117">Description</span></span>**  
<span data-ttu-id="a7c63-118">首次设置时出现问题，可能是由许多不同的问题导致的。</span><span class="sxs-lookup"><span data-stu-id="a7c63-118">A problem occurred with first time setup that might have been caused by many different issues.</span></span> <span data-ttu-id="a7c63-119">其中包括网络连接问题。</span><span class="sxs-lookup"><span data-stu-id="a7c63-119">These include problems with network connectivity.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a7c63-120">解决方案</span><span class="sxs-lookup"><span data-stu-id="a7c63-120">Solution</span></span>**  
<span data-ttu-id="a7c63-121">重新启动 MED-V 主机代理，以便首次重新运行设置。</span><span class="sxs-lookup"><span data-stu-id="a7c63-121">Restart the MED-V Host Agent to rerun first time setup.</span></span>

### <span data-ttu-id="a7c63-122">事件 ID 3078</span><span class="sxs-lookup"><span data-stu-id="a7c63-122">Event ID 3078</span></span>

<span data-ttu-id="a7c63-123">虚拟机准备失败。</span><span class="sxs-lookup"><span data-stu-id="a7c63-123">Virtual machine preparation failed.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a7c63-124">描述</span><span class="sxs-lookup"><span data-stu-id="a7c63-124">Description</span></span>**  
<span data-ttu-id="a7c63-125">你用于创建 MED-V 工作区的 VHD 存在潜在问题。</span><span class="sxs-lookup"><span data-stu-id="a7c63-125">A potential problem exists with the VHD that you are using to create a MED-V workspace.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a7c63-126">解决方案</span><span class="sxs-lookup"><span data-stu-id="a7c63-126">Solution</span></span>**  
<span data-ttu-id="a7c63-127">验证你是否可以使用适用于 MED-V 的 VHD 创建虚拟机以及它是否可以启动。</span><span class="sxs-lookup"><span data-stu-id="a7c63-127">Verify that you can create a virtual machine with the VHD for MED-V and that it can be started.</span></span>

### <span data-ttu-id="a7c63-128">事件 ID 3079</span><span class="sxs-lookup"><span data-stu-id="a7c63-128">Event ID 3079</span></span>

<span data-ttu-id="a7c63-129">重试虚拟机准备。</span><span class="sxs-lookup"><span data-stu-id="a7c63-129">Retrying virtual machine preparation.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a7c63-130">描述</span><span class="sxs-lookup"><span data-stu-id="a7c63-130">Description</span></span>**  
<span data-ttu-id="a7c63-131">MED-V 正在尝试准备虚拟机。</span><span class="sxs-lookup"><span data-stu-id="a7c63-131">MED-V is trying to prepare the virtual machine.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a7c63-132">解决方案</span><span class="sxs-lookup"><span data-stu-id="a7c63-132">Solution</span></span>**  
<span data-ttu-id="a7c63-133">不需要执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="a7c63-133">No action is required.</span></span> <span data-ttu-id="a7c63-134">第一次设置完成。</span><span class="sxs-lookup"><span data-stu-id="a7c63-134">Let first time setup finish.</span></span>

### <span data-ttu-id="a7c63-135">事件 ID 3080</span><span class="sxs-lookup"><span data-stu-id="a7c63-135">Event ID 3080</span></span>

<span data-ttu-id="a7c63-136">在准备虚拟机时，客户端已停止。</span><span class="sxs-lookup"><span data-stu-id="a7c63-136">The client was stopped when preparing the virtual machine.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a7c63-137">描述</span><span class="sxs-lookup"><span data-stu-id="a7c63-137">Description</span></span>**  
<span data-ttu-id="a7c63-138">MED-V 在尝试准备虚拟机时意外停止。</span><span class="sxs-lookup"><span data-stu-id="a7c63-138">MED-V stops unexpectedly when it tries to prepare the virtual machine.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a7c63-139">解决方案</span><span class="sxs-lookup"><span data-stu-id="a7c63-139">Solution</span></span>**  
<span data-ttu-id="a7c63-140">启动 MED-V 主机代理并让第一次设置完成</span><span class="sxs-lookup"><span data-stu-id="a7c63-140">Start the MED-V Host Agent and let first time setup complete</span></span>

### <span data-ttu-id="a7c63-141">事件 ID 3084</span><span class="sxs-lookup"><span data-stu-id="a7c63-141">Event ID 3084</span></span>

<span data-ttu-id="a7c63-142">虚拟机无效。</span><span class="sxs-lookup"><span data-stu-id="a7c63-142">Virtual machine is not valid.</span></span> <span data-ttu-id="a7c63-143">首次需要重新运行设置。</span><span class="sxs-lookup"><span data-stu-id="a7c63-143">First time setup needs to be re-run.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a7c63-144">描述</span><span class="sxs-lookup"><span data-stu-id="a7c63-144">Description</span></span>**  
<span data-ttu-id="a7c63-145">MED-V 主机代理检测到虚拟机有问题。</span><span class="sxs-lookup"><span data-stu-id="a7c63-145">The MED-V Host Agent detected a problem with the virtual machine.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a7c63-146">解决方案</span><span class="sxs-lookup"><span data-stu-id="a7c63-146">Solution</span></span>**  
<span data-ttu-id="a7c63-147">不需要执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="a7c63-147">No action is required.</span></span> <span data-ttu-id="a7c63-148">第一次设置完成。</span><span class="sxs-lookup"><span data-stu-id="a7c63-148">Let first time setup finish.</span></span>

### <span data-ttu-id="a7c63-149">事件 ID 3099</span><span class="sxs-lookup"><span data-stu-id="a7c63-149">Event ID 3099</span></span>

<span data-ttu-id="a7c63-150">调用以启动虚拟机失败。</span><span class="sxs-lookup"><span data-stu-id="a7c63-150">Call to start virtual machine failed.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a7c63-151">描述</span><span class="sxs-lookup"><span data-stu-id="a7c63-151">Description</span></span>**  
<span data-ttu-id="a7c63-152">用于创建 MED-V 工作区的 VHD 存在潜在问题。</span><span class="sxs-lookup"><span data-stu-id="a7c63-152">A potential problem exists with the VHD you are using to create a MED-V workspace.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a7c63-153">解决方案</span><span class="sxs-lookup"><span data-stu-id="a7c63-153">Solution</span></span>**  
<span data-ttu-id="a7c63-154">验证你是否可以使用适用于 MED-V 的 VHD 创建虚拟机以及它是否可以打开。</span><span class="sxs-lookup"><span data-stu-id="a7c63-154">Verify that you can create a virtual machine with the VHD for MED-V and that it can be opened.</span></span>

### <span data-ttu-id="a7c63-155">VM 管理</span><span class="sxs-lookup"><span data-stu-id="a7c63-155">VM Management</span></span>

### <span data-ttu-id="a7c63-156">事件 ID 4022</span><span class="sxs-lookup"><span data-stu-id="a7c63-156">Event ID 4022</span></span>

<span data-ttu-id="a7c63-157">向 VM 发出命令时出现 VMManagerException 严重错误。</span><span class="sxs-lookup"><span data-stu-id="a7c63-157">VMManagerException Fatal error while issuing command to VM.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a7c63-158">描述</span><span class="sxs-lookup"><span data-stu-id="a7c63-158">Description</span></span>**  
<span data-ttu-id="a7c63-159">最终用户尝试通过注销或关闭 MED-V 主机来退出 MED-V，并且已超过 VMTaskTimeout 配置设置。</span><span class="sxs-lookup"><span data-stu-id="a7c63-159">The end user tried to exit MED-V by logging off or by shutting down the MED-V host, and the VMTaskTimeout configuration setting was exceeded.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a7c63-160">解决方案</span><span class="sxs-lookup"><span data-stu-id="a7c63-160">Solution</span></span>**  
<span data-ttu-id="a7c63-161">重启 MED-V。</span><span class="sxs-lookup"><span data-stu-id="a7c63-161">Restart MED-V.</span></span>

### <span data-ttu-id="a7c63-162">事件 ID 4028</span><span class="sxs-lookup"><span data-stu-id="a7c63-162">Event ID 4028</span></span>

<span data-ttu-id="a7c63-163">虚拟机操作超时。</span><span class="sxs-lookup"><span data-stu-id="a7c63-163">VM Operation timed out.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a7c63-164">描述</span><span class="sxs-lookup"><span data-stu-id="a7c63-164">Description</span></span>**  
<span data-ttu-id="a7c63-165">最终用户尝试通过注销或关闭主机来退出 MED-V，并且已超过 VMTaskTimeout 配置设置。</span><span class="sxs-lookup"><span data-stu-id="a7c63-165">The end user tried to exit MED-V by logging off or by shutting down the host, and the VMTaskTimeout configuration setting was exceeded.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a7c63-166">解决方案</span><span class="sxs-lookup"><span data-stu-id="a7c63-166">Solution</span></span>**  
<span data-ttu-id="a7c63-167">重启 MED-V。</span><span class="sxs-lookup"><span data-stu-id="a7c63-167">Restart MED-V.</span></span>

### <span data-ttu-id="a7c63-168">事件 ID 4038</span><span class="sxs-lookup"><span data-stu-id="a7c63-168">Event ID 4038</span></span>

<span data-ttu-id="a7c63-169">Vmsal 向用户发布了一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="a7c63-169">Vmsal posted an error message to the user.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a7c63-170">描述</span><span class="sxs-lookup"><span data-stu-id="a7c63-170">Description</span></span>**  
<span data-ttu-id="a7c63-171">向最终用户显示一条错误消息，指出 MED-V 无法启动虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="a7c63-171">An error message is displayed to the end user stating that MED-V could not start the virtual application.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a7c63-172">解决方案</span><span class="sxs-lookup"><span data-stu-id="a7c63-172">Solution</span></span>**  
<span data-ttu-id="a7c63-173">如果错误在一行中记录了两次或多次，请停止 MED-V 并使用 Windows 虚拟 PC 控制台连接到虚拟机，并尝试以全屏方式启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="a7c63-173">If the error is logged two or more times in a row, stop MED-V and connect to the virtual machine by using Windows Virtual PC console and attempt to start the application in Full Screen.</span></span>

### <span data-ttu-id="a7c63-174">事件 ID 4040</span><span class="sxs-lookup"><span data-stu-id="a7c63-174">Event ID 4040</span></span>

<span data-ttu-id="a7c63-175">由于 TerminalServices 未在来宾中初始化，因此回收添加。</span><span class="sxs-lookup"><span data-stu-id="a7c63-175">Recycling Additions because TerminalServices is not initialized in the guest.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a7c63-176">描述</span><span class="sxs-lookup"><span data-stu-id="a7c63-176">Description</span></span>**  
<span data-ttu-id="a7c63-177">由于未在虚拟机上初始化远程桌面服务，因此 MED-V 已重新启动虚拟机。</span><span class="sxs-lookup"><span data-stu-id="a7c63-177">MED-V rebooted the virtual machine because Remote Desktop Services was not initialized on the virtual machine.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a7c63-178">解决方案</span><span class="sxs-lookup"><span data-stu-id="a7c63-178">Solution</span></span>**  
<span data-ttu-id="a7c63-179">如果错误在一行中记录了两次或更多次，请停止 MED-V 并使用 Windows 虚拟 PC 控制台连接到虚拟机。</span><span class="sxs-lookup"><span data-stu-id="a7c63-179">If the error is logged two or more times in a row, stop MED-V and connect to the virtual machine by using Windows Virtual PC console.</span></span>

### <span data-ttu-id="a7c63-180">事件 ID 4042</span><span class="sxs-lookup"><span data-stu-id="a7c63-180">Event ID 4042</span></span>

<span data-ttu-id="a7c63-181">无法在来宾中回收添加项。</span><span class="sxs-lookup"><span data-stu-id="a7c63-181">Failed to recycle additions in the guest.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a7c63-182">描述</span><span class="sxs-lookup"><span data-stu-id="a7c63-182">Description</span></span>**  
<span data-ttu-id="a7c63-183">MED-V 无法在虚拟机上回收虚拟机添加内容。</span><span class="sxs-lookup"><span data-stu-id="a7c63-183">MED-V failed to recycle virtual machine additions on the virtual machine.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a7c63-184">解决方案</span><span class="sxs-lookup"><span data-stu-id="a7c63-184">Solution</span></span>**  
<span data-ttu-id="a7c63-185">如果错误在一行中记录了两次或更多次，请停止 MED-V 并使用 Windows 虚拟 PC 控制台连接到虚拟机。</span><span class="sxs-lookup"><span data-stu-id="a7c63-185">If the error is logged two or more times in a row, stop MED-V and connect to the virtual machine by using Windows Virtual PC console.</span></span>

### <span data-ttu-id="a7c63-186">事件 ID 4043</span><span class="sxs-lookup"><span data-stu-id="a7c63-186">Event ID 4043</span></span>

<span data-ttu-id="a7c63-187">无法在虚拟机中重置已过期的密码。</span><span class="sxs-lookup"><span data-stu-id="a7c63-187">Failed to reset expired password in the virtual machine.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a7c63-188">描述</span><span class="sxs-lookup"><span data-stu-id="a7c63-188">Description</span></span>**  
<span data-ttu-id="a7c63-189">最终用户在虚拟机过期之前，未重置该密码。</span><span class="sxs-lookup"><span data-stu-id="a7c63-189">The end user did not reset the password in the virtual machine before it expired.</span></span> <span data-ttu-id="a7c63-190">因此，用户可能无法访问网络资源或保存工作。</span><span class="sxs-lookup"><span data-stu-id="a7c63-190">As a result, the user might not be able to access network resources or save work.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a7c63-191">解决方案</span><span class="sxs-lookup"><span data-stu-id="a7c63-191">Solution</span></span>**  
<span data-ttu-id="a7c63-192">关闭 MED-V 来宾，然后重新启动它。</span><span class="sxs-lookup"><span data-stu-id="a7c63-192">Shut down the MED-V guest and restart it.</span></span>

### <span data-ttu-id="a7c63-193">URL 重定向</span><span class="sxs-lookup"><span data-stu-id="a7c63-193">URL Redirection</span></span>

### <span data-ttu-id="a7c63-194">事件 ID 5005</span><span class="sxs-lookup"><span data-stu-id="a7c63-194">Event ID 5005</span></span>

<span data-ttu-id="a7c63-195">无法从配置获取 VM 名称;无法启动来宾浏览器。</span><span class="sxs-lookup"><span data-stu-id="a7c63-195">Couldn’t get VM name from configuration; can’t launch guest browser.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a7c63-196">描述</span><span class="sxs-lookup"><span data-stu-id="a7c63-196">Description</span></span>**  
<span data-ttu-id="a7c63-197">URL 重定向无法从配置获取 MED-V 工作区名称。</span><span class="sxs-lookup"><span data-stu-id="a7c63-197">URL Redirection could not obtain the MED-V workspace name from the configuration.</span></span> <span data-ttu-id="a7c63-198">因此，它无法通知 Windows 虚拟 PC 在 MED-V 工作区浏览器中打开重定向的 URL。</span><span class="sxs-lookup"><span data-stu-id="a7c63-198">As a result, it cannot inform Windows Virtual PC to open the redirected URL in the MED-V workspace browser.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a7c63-199">解决方案</span><span class="sxs-lookup"><span data-stu-id="a7c63-199">Solution</span></span>**  
<span data-ttu-id="a7c63-200">确保 MED-V 工作区名称已设置，并且它与 C:\\Users\\ &lt; *用户*\\Virtual machine 目录中的虚拟机名称相匹配 &gt; 。</span><span class="sxs-lookup"><span data-stu-id="a7c63-200">Ensure that the MED-V workspace name is set and that it matches a virtual machine name in the C:\\Users\\&lt;*user*&gt;\\Virtual Machines directory.</span></span> <span data-ttu-id="a7c63-201">MED-V 工作区名称位于 HKLM\\SOFTWARE\\Microsoft\\Medv\\v2\\VM\\Name。</span><span class="sxs-lookup"><span data-stu-id="a7c63-201">The MED-V workspace name is located at HKLM\\SOFTWARE\\Microsoft\\Medv\\v2\\VM\\Name.</span></span>

<span data-ttu-id="a7c63-202">例如，如果用户为 "Matt"，而工作区名称为 "mattsworkspace"，则 HKLM\\SOFTWARE\\Microsoft\\Medv\\v2\\VM\\Name 的值应为 "mattsworkspace"，并且应存在名为 C:\\Users\\Matt\\Virtual Machines\\mattsworkspace.vcmx. 的文件</span><span class="sxs-lookup"><span data-stu-id="a7c63-202">For example, if the user is "Matt" and the workspace name is "mattsworkspace", the value of HKLM\\SOFTWARE\\Microsoft\\Medv\\v2\\VM\\Name should be "mattsworkspace", and there should be a file that is named C:\\Users\\Matt\\Virtual Machines\\mattsworkspace.vcmx.</span></span>

### <span data-ttu-id="a7c63-203">事件 ID 5006</span><span class="sxs-lookup"><span data-stu-id="a7c63-203">Event ID 5006</span></span>

<span data-ttu-id="a7c63-204">无法创建管道服务器。</span><span class="sxs-lookup"><span data-stu-id="a7c63-204">Failed to create pipe server.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a7c63-205">描述</span><span class="sxs-lookup"><span data-stu-id="a7c63-205">Description</span></span>**  
<span data-ttu-id="a7c63-206">URL 重定向服务无法创建与 Internet Explorer 通信的管道服务器。</span><span class="sxs-lookup"><span data-stu-id="a7c63-206">The URL Redirection service could not create the pipe server to communicate with Internet Explorer.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a7c63-207">解决方案</span><span class="sxs-lookup"><span data-stu-id="a7c63-207">Solution</span></span>**  
<span data-ttu-id="a7c63-208">检查系统事件日志以尝试创建路径的文件或资源，其路径开始如下所示： "\\\\.\\pipe\\MEDVUrlRedirectionPipe\_"，以用户的用户名和域名结尾。</span><span class="sxs-lookup"><span data-stu-id="a7c63-208">Check system event logs for attempts to create a file or resource whose path begins similar to the following: "\\\\.\\pipe\\MEDVUrlRedirectionPipe\_" and ends with the user’s user name and domain name.</span></span> <span data-ttu-id="a7c63-209">如果事件日志中未显示此项，请重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="a7c63-209">If this is not present in the event log, restart the computer.</span></span>

### <span data-ttu-id="a7c63-210">ConfigMgr （来宾）</span><span class="sxs-lookup"><span data-stu-id="a7c63-210">ConfigMgr (Guest)</span></span>

### <span data-ttu-id="a7c63-211">事件 ID 7001</span><span class="sxs-lookup"><span data-stu-id="a7c63-211">Event ID 7001</span></span>

<span data-ttu-id="a7c63-212">主机网络配置数据格式不正确。</span><span class="sxs-lookup"><span data-stu-id="a7c63-212">The host network configuration data is not properly formatted.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a7c63-213">描述</span><span class="sxs-lookup"><span data-stu-id="a7c63-213">Description</span></span>**  
<span data-ttu-id="a7c63-214">从主机收到的网络配置的 XML 字符串格式不正确，或者从主机返回的网络信息无法写入 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="a7c63-214">Either the network configuration received from the host is an incorrectly formatted XML string, or the network information returned from the host cannot be written to an XML document.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a7c63-215">解决方案</span><span class="sxs-lookup"><span data-stu-id="a7c63-215">Solution</span></span>**  
<span data-ttu-id="a7c63-216">重新启动主机和虚拟机。</span><span class="sxs-lookup"><span data-stu-id="a7c63-216">Restart the host computer and the virtual machine.</span></span>

### <span data-ttu-id="a7c63-217">事件 ID 7005</span><span class="sxs-lookup"><span data-stu-id="a7c63-217">Event ID 7005</span></span>

<span data-ttu-id="a7c63-218">已检测到主机网络配置的更改，但无法应用，因为主机网络配置数据的格式不正确。</span><span class="sxs-lookup"><span data-stu-id="a7c63-218">A change to the host network configuration was detected, but was not able to be applied because the host network configuration data was not properly formatted.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a7c63-219">描述</span><span class="sxs-lookup"><span data-stu-id="a7c63-219">Description</span></span>**  
<span data-ttu-id="a7c63-220">对主机网络配置所做的更改已传递到虚拟机，但由于出现错误，无法在虚拟机中进行处理。</span><span class="sxs-lookup"><span data-stu-id="a7c63-220">A change to the host network configuration was communicated to the virtual machine, but could not be processed in the virtual machine because of an error.</span></span> <span data-ttu-id="a7c63-221">此错误可能是由格式不正确的数据或无法将信息设置到 Windows Management Instrumentation （WMI） CCMNetworkAdapter 实例导致的。</span><span class="sxs-lookup"><span data-stu-id="a7c63-221">This error could be caused by incorrectly formatted data or the inability to set the information into the Windows Management Instrumentation (WMI) CCMNetworkAdapter instance.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a7c63-222">解决方案</span><span class="sxs-lookup"><span data-stu-id="a7c63-222">Solution</span></span>**  
<span data-ttu-id="a7c63-223">重新启动主机和虚拟机。</span><span class="sxs-lookup"><span data-stu-id="a7c63-223">Restart the host and virtual machine.</span></span>

### <span data-ttu-id="a7c63-224">ConfigMgr （主机）</span><span class="sxs-lookup"><span data-stu-id="a7c63-224">ConfigMgr (Host)</span></span>

### <span data-ttu-id="a7c63-225">事件 ID 8006</span><span class="sxs-lookup"><span data-stu-id="a7c63-225">Event ID 8006</span></span>

<span data-ttu-id="a7c63-226">找不到虚拟机。</span><span class="sxs-lookup"><span data-stu-id="a7c63-226">The virtual machine cannot be found.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a7c63-227">描述</span><span class="sxs-lookup"><span data-stu-id="a7c63-227">Description</span></span>**  
<span data-ttu-id="a7c63-228">Windows Virtual 电脑7找不到虚拟机。</span><span class="sxs-lookup"><span data-stu-id="a7c63-228">Windows Virtual PC 7 cannot locate the virtual machine.</span></span> <span data-ttu-id="a7c63-229">虚拟机可能已被删除、移动、删除或访问被拒绝。</span><span class="sxs-lookup"><span data-stu-id="a7c63-229">The virtual machine might have been deleted, moved, removed, or access was denied.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a7c63-230">解决方案</span><span class="sxs-lookup"><span data-stu-id="a7c63-230">Solution</span></span>**  
<span data-ttu-id="a7c63-231">重新安装虚拟机。</span><span class="sxs-lookup"><span data-stu-id="a7c63-231">Reinstall the virtual machine.</span></span>

### <span data-ttu-id="a7c63-232">事件 ID 8008</span><span class="sxs-lookup"><span data-stu-id="a7c63-232">Event ID 8008</span></span>

<span data-ttu-id="a7c63-233">无法检索工作站的网络配置信息。</span><span class="sxs-lookup"><span data-stu-id="a7c63-233">The workstation's network configuration information could not be retrieved.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a7c63-234">描述</span><span class="sxs-lookup"><span data-stu-id="a7c63-234">Description</span></span>**  
<span data-ttu-id="a7c63-235">无法从 MED-V 主机收集网络配置信息，很可能是因为 .NET Framework 中的系统调用失败。</span><span class="sxs-lookup"><span data-stu-id="a7c63-235">Network configuration information could not be collected from the MED-V host, most likely because of a system call failure in the .NET Framework.</span></span> <span data-ttu-id="a7c63-236">如果从 MED-V 主机返回的网络信息无法写入 XML 文档，也可能会发生此错误。</span><span class="sxs-lookup"><span data-stu-id="a7c63-236">This failure can also occur if the network information returned from the MED-V host cannot be written to an XML document.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a7c63-237">解决方案</span><span class="sxs-lookup"><span data-stu-id="a7c63-237">Solution</span></span>**  
<span data-ttu-id="a7c63-238">重新启动主机工作站。</span><span class="sxs-lookup"><span data-stu-id="a7c63-238">Restart the host workstation.</span></span>

### <span data-ttu-id="a7c63-239">事件 ID 8010</span><span class="sxs-lookup"><span data-stu-id="a7c63-239">Event ID 8010</span></span>

<span data-ttu-id="a7c63-240">无法在虚拟机中设置网络配置数据。</span><span class="sxs-lookup"><span data-stu-id="a7c63-240">The network configuration data could not be set in the virtual machine.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a7c63-241">描述</span><span class="sxs-lookup"><span data-stu-id="a7c63-241">Description</span></span>**  
<span data-ttu-id="a7c63-242">无法将 MED-V hostnetwork 地址转换（NAT）传递到虚拟机，很可能是因为虚拟机处于错误状态，或者未安装或启用 Windows 虚拟 PC 添加。</span><span class="sxs-lookup"><span data-stu-id="a7c63-242">The MED-V hostnetwork address translation (NAT) could not be communicated to the virtual machine, most likely because the virtual machine is in a bad state or the Windows Virtual PC Additions were not installed or enabled.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a7c63-243">解决方案</span><span class="sxs-lookup"><span data-stu-id="a7c63-243">Solution</span></span>**  
<span data-ttu-id="a7c63-244">关闭并重新启动虚拟机。</span><span class="sxs-lookup"><span data-stu-id="a7c63-244">Shut down and restart the virtual machine.</span></span> <span data-ttu-id="a7c63-245">此外，你可能需要重新安装虚拟机。</span><span class="sxs-lookup"><span data-stu-id="a7c63-245">In addition, you might have to reinstall the virtual machine.</span></span>

### <span data-ttu-id="a7c63-246">事件 ID 8011</span><span class="sxs-lookup"><span data-stu-id="a7c63-246">Event ID 8011</span></span>

<span data-ttu-id="a7c63-247">无法在虚拟机中重置网络配置数据。</span><span class="sxs-lookup"><span data-stu-id="a7c63-247">The network configuration data could not be reset in the virtual machine.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a7c63-248">描述</span><span class="sxs-lookup"><span data-stu-id="a7c63-248">Description</span></span>**  
<span data-ttu-id="a7c63-249">无法将 MED-V hostnetwork 配置（桥）传递到虚拟机，很可能是因为虚拟机处于错误状态，或者未安装或启用 Windows 虚拟 PC 添加。</span><span class="sxs-lookup"><span data-stu-id="a7c63-249">The MED-V hostnetwork configuration (BRIDGED) could not be communicated to the virtual machine, most likely because the virtual machine is in a bad state or the Windows Virtual PC Additions were not installed or enabled.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a7c63-250">解决方案</span><span class="sxs-lookup"><span data-stu-id="a7c63-250">Solution</span></span>**  
<span data-ttu-id="a7c63-251">关闭并重新启动虚拟机。</span><span class="sxs-lookup"><span data-stu-id="a7c63-251">Shut down and restart the virtual machine.</span></span> <span data-ttu-id="a7c63-252">此外，你可能需要重新安装虚拟机。</span><span class="sxs-lookup"><span data-stu-id="a7c63-252">In addition, you might have to reinstall the virtual machine.</span></span>

### <span data-ttu-id="a7c63-253">打印机重定向</span><span class="sxs-lookup"><span data-stu-id="a7c63-253">Printer Redirection</span></span>

### <span data-ttu-id="a7c63-254">事件 ID 9001</span><span class="sxs-lookup"><span data-stu-id="a7c63-254">Event ID 9001</span></span>

<span data-ttu-id="a7c63-255">文件权限错误。</span><span class="sxs-lookup"><span data-stu-id="a7c63-255">File Permission Error.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a7c63-256">描述</span><span class="sxs-lookup"><span data-stu-id="a7c63-256">Description</span></span>**  
<span data-ttu-id="a7c63-257">最终用户无权访问打开或创建用于读取的 MED-V 打印机文件所需的文件夹。</span><span class="sxs-lookup"><span data-stu-id="a7c63-257">The end user is not authorized to access the folder required to open or create the MED-V printer file for reading.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a7c63-258">解决方案</span><span class="sxs-lookup"><span data-stu-id="a7c63-258">Solution</span></span>**  
<span data-ttu-id="a7c63-259">验证 User\\AppData\\ 路径是否可访问以及用户是否有权读取和写入该路径。</span><span class="sxs-lookup"><span data-stu-id="a7c63-259">Verify that the User\\AppData\\ path can be accessed and that the user has permission to read and write to it.</span></span> <span data-ttu-id="a7c63-260">例如，如果用户是 "Matt"，则路径 C:\\Users\\Matt\\AppData\\ 以及其中的所有文件都应具有 "读取" 和 "写入" 权限。</span><span class="sxs-lookup"><span data-stu-id="a7c63-260">For example, if the user is "Matt", the path C:\\Users\\Matt\\AppData\\, and all files therein should have Read and Write permissions.</span></span> <span data-ttu-id="a7c63-261">如果存在，则路径 C:\\Users\\Matt\\AppData\\Local\\Microsoft\\MEDV\\v2\\ 和其中的所有文件都应具有读写权限。</span><span class="sxs-lookup"><span data-stu-id="a7c63-261">And if it exists, the path C:\\Users\\Matt\\AppData\\Local\\Microsoft\\MEDV\\v2\\ and all files therein should have Read and Write permissions.</span></span>

### <span data-ttu-id="a7c63-262">事件 ID 9002</span><span class="sxs-lookup"><span data-stu-id="a7c63-262">Event ID 9002</span></span>

<span data-ttu-id="a7c63-263">文件权限错误。</span><span class="sxs-lookup"><span data-stu-id="a7c63-263">File Permission Error.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a7c63-264">描述</span><span class="sxs-lookup"><span data-stu-id="a7c63-264">Description</span></span>**  
<span data-ttu-id="a7c63-265">最终用户无权访问打开或创建用于写入的 MED-V 打印机文件所需的文件夹。</span><span class="sxs-lookup"><span data-stu-id="a7c63-265">The end user is not authorized to access the folder required to open or create the MED-V printer file for writing.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a7c63-266">解决方案</span><span class="sxs-lookup"><span data-stu-id="a7c63-266">Solution</span></span>**  
<span data-ttu-id="a7c63-267">确保可以访问 User\\AppData\\ 路径，并且用户有权读取和写入该路径。</span><span class="sxs-lookup"><span data-stu-id="a7c63-267">Ensure that the User\\AppData\\ path can be accessed, and that the user has permission to read and write to it.</span></span> <span data-ttu-id="a7c63-268">例如，如果用户是 "Matt"，则路径 C:\\Users\\Matt\\AppData\\ 和其中的所有文件都应具有 "读取" 和 "写入" 权限。</span><span class="sxs-lookup"><span data-stu-id="a7c63-268">For example, if the user is "Matt", the path C:\\Users\\Matt\\AppData\\ and all files therein should have Read and Write permissions.</span></span> <span data-ttu-id="a7c63-269">如果存在，则路径 C:\\Users\\Matt\\AppData\\Local\\Microsoft\\MEDV\\v2\\ 和其中的所有文件都应具有读写权限。</span><span class="sxs-lookup"><span data-stu-id="a7c63-269">And if it exists, the path C:\\Users\\Matt\\AppData\\Local\\Microsoft\\MEDV\\v2\\ and all files therein should have Read and Write permissions.</span></span>

### <span data-ttu-id="a7c63-270">事件 ID 9004</span><span class="sxs-lookup"><span data-stu-id="a7c63-270">Event ID 9004</span></span>

<span data-ttu-id="a7c63-271">无法创建存储 MEDV 打印机文件的路径。</span><span class="sxs-lookup"><span data-stu-id="a7c63-271">Could not create path for storing MEDV printer files.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a7c63-272">描述</span><span class="sxs-lookup"><span data-stu-id="a7c63-272">Description</span></span>**  
<span data-ttu-id="a7c63-273">打印机重定向服务无法访问文件或创建存储打印机信息所需的目录。</span><span class="sxs-lookup"><span data-stu-id="a7c63-273">The printer redirection service could not access files or create directories required for storing the printer information.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a7c63-274">解决方案</span><span class="sxs-lookup"><span data-stu-id="a7c63-274">Solution</span></span>**  
<span data-ttu-id="a7c63-275">验证 User\\AppData\\ 路径是否可访问以及用户是否有权读取和写入该路径。</span><span class="sxs-lookup"><span data-stu-id="a7c63-275">Verify that the User\\AppData\\ path can be accessed and that the user has permission to read and write to it.</span></span> <span data-ttu-id="a7c63-276">例如，如果用户是 "Matt"，则路径 C:\\Users\\Matt\\AppData\\ 和其中的所有文件都应具有 "读取" 和 "写入" 权限。</span><span class="sxs-lookup"><span data-stu-id="a7c63-276">For example, if the user is "Matt", the path C:\\Users\\Matt\\AppData\\ and all files therein should have Read and Write permissions.</span></span> <span data-ttu-id="a7c63-277">如果存在，则路径 C:\\Users\\Matt\\AppData\\Local\\Microsoft\\MEDV\\v2\\ 和其中的所有文件都应具有读写权限。</span><span class="sxs-lookup"><span data-stu-id="a7c63-277">And if it exists, the path C:\\Users\\Matt\\AppData\\Local\\Microsoft\\MEDV\\v2\\ and all files therein should have Read and Write permissions.</span></span>

### <span data-ttu-id="a7c63-278">事件 ID 9005</span><span class="sxs-lookup"><span data-stu-id="a7c63-278">Event ID 9005</span></span>

<span data-ttu-id="a7c63-279">无法从配置获取 VM 名称;无法启动来宾安装程序。</span><span class="sxs-lookup"><span data-stu-id="a7c63-279">Couldn’t get VM name from configuration; cannot launch guest installer.</span></span> <span data-ttu-id="a7c63-280">无法更新 MED-V-未检测到主机网络。</span><span class="sxs-lookup"><span data-stu-id="a7c63-280">Cannot update MED-V – No host network detected.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a7c63-281">描述</span><span class="sxs-lookup"><span data-stu-id="a7c63-281">Description</span></span>**  
<span data-ttu-id="a7c63-282">打印机重定向服务无法从 MED-V 配置获取 MED-V 工作区名称，并且无法通知 Windows 虚拟 PC 在 MED-V 来宾上启动安装程序。</span><span class="sxs-lookup"><span data-stu-id="a7c63-282">The printer redirection service was not able to obtain the MED-V workspace name from the MED-V configuration and cannot inform Windows Virtual PC to start the installer on the MED-V guest.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a7c63-283">解决方案</span><span class="sxs-lookup"><span data-stu-id="a7c63-283">Solution</span></span>**  
<span data-ttu-id="a7c63-284">确保 MED-V 工作区名称已设置，并且它与 C:\\Users\\ &lt; *用户*\\Virtual machine 目录中的虚拟机名称相匹配 &gt; 。</span><span class="sxs-lookup"><span data-stu-id="a7c63-284">Ensure that the MED-V workspace name is set and that it matches a virtual machine name in the C:\\Users\\&lt;*user*&gt;\\Virtual Machines directory.</span></span> <span data-ttu-id="a7c63-285">MED-V 工作区名称位于 HKLM\\SOFTWARE\\Microsoft\\Medv\\v2\\VM\\Name。</span><span class="sxs-lookup"><span data-stu-id="a7c63-285">The MED-V workspace name is located at HKLM\\SOFTWARE\\Microsoft\\Medv\\v2\\VM\\Name.</span></span>

<span data-ttu-id="a7c63-286">例如，如果用户为 "Matt"，而工作区名称为 "mattsworkspace"，则 HKLM\\SOFTWARE\\Microsoft\\Medv\\v2\\VM\\Name 的值应为 "mattsworkspace"，并且应存在名为 C:\\Users\\Matt\\Virtual Machines\\mattsworkspace.vcmx. 的文件</span><span class="sxs-lookup"><span data-stu-id="a7c63-286">For example, if the user is "Matt" and the workspace name is "mattsworkspace", the value of HKLM\\SOFTWARE\\Microsoft\\Medv\\v2\\VM\\Name should be "mattsworkspace" and there should be a file that is named C:\\Users\\Matt\\Virtual Machines\\mattsworkspace.vcmx.</span></span>

### <span data-ttu-id="a7c63-287">应用程序发布</span><span class="sxs-lookup"><span data-stu-id="a7c63-287">Application Publishing</span></span>

### <span data-ttu-id="a7c63-288">事件 ID 10015</span><span class="sxs-lookup"><span data-stu-id="a7c63-288">Event ID 10015</span></span>

<span data-ttu-id="a7c63-289">协调过程中发生文件系统错误。</span><span class="sxs-lookup"><span data-stu-id="a7c63-289">A file system error occurred during the reconcile process.</span></span> <span data-ttu-id="a7c63-290">"协调" 过程不会处理文件名 &lt; *，* &gt; 但会继续处理任何其他更改。</span><span class="sxs-lookup"><span data-stu-id="a7c63-290">The reconcile process will not process the file &lt;*filename*&gt; but will continue to process any other changes.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a7c63-291">描述</span><span class="sxs-lookup"><span data-stu-id="a7c63-291">Description</span></span>**  
<span data-ttu-id="a7c63-292">创建或删除快捷方式时发生未经授权的访问或 i/o 错误。</span><span class="sxs-lookup"><span data-stu-id="a7c63-292">An unauthorized access or I/O error occurred when a shortcut was being created or deleted.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a7c63-293">解决方案</span><span class="sxs-lookup"><span data-stu-id="a7c63-293">Solution</span></span>**  
<span data-ttu-id="a7c63-294">检查文件路径是否可访问，以及用户是否具有创建或删除指定文件的权限。</span><span class="sxs-lookup"><span data-stu-id="a7c63-294">Check that the file path can be accessed and that the user has permissions to create or delete the specified file.</span></span>

### <span data-ttu-id="a7c63-295">事件 ID 10021</span><span class="sxs-lookup"><span data-stu-id="a7c63-295">Event ID 10021</span></span>

<span data-ttu-id="a7c63-296">错误 &lt; *\ _information* &gt; ，文件操作 &lt; *操作 \ _name* &gt; 文件 &lt; *文件名* &gt; 时出错。</span><span class="sxs-lookup"><span data-stu-id="a7c63-296">Error &lt;*error\_information*&gt; for file operation &lt;*operation\_name*&gt; on file &lt;*filename*&gt;.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a7c63-297">描述</span><span class="sxs-lookup"><span data-stu-id="a7c63-297">Description</span></span>**  
<span data-ttu-id="a7c63-298">创建或删除快捷方式时发生未经授权的访问或 i/o 错误。</span><span class="sxs-lookup"><span data-stu-id="a7c63-298">An unauthorized access or I/O error occurred when a shortcut was being created or deleted.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a7c63-299">解决方案</span><span class="sxs-lookup"><span data-stu-id="a7c63-299">Solution</span></span>**  
<span data-ttu-id="a7c63-300">检查文件路径是否可访问，以及用户是否具有创建或删除指定文件的权限。</span><span class="sxs-lookup"><span data-stu-id="a7c63-300">Check that the file path can be accessed and that the user has permissions to create or delete the specified file.</span></span>

### <span data-ttu-id="a7c63-301">来宾修补</span><span class="sxs-lookup"><span data-stu-id="a7c63-301">Guest Patching</span></span>

### <span data-ttu-id="a7c63-302">事件 ID 11001</span><span class="sxs-lookup"><span data-stu-id="a7c63-302">Event ID 11001</span></span>

<span data-ttu-id="a7c63-303">来宾唤醒任务使用消息。</span><span class="sxs-lookup"><span data-stu-id="a7c63-303">Guest wakeup task usage message.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a7c63-304">描述</span><span class="sxs-lookup"><span data-stu-id="a7c63-304">Description</span></span>**  
<span data-ttu-id="a7c63-305">/GuestWakeup 选项的 MedvHost.exe 未正确执行，或者命令的格式不正确。</span><span class="sxs-lookup"><span data-stu-id="a7c63-305">MedvHost.exe with the /GuestWakeup option was executed incorrectly, or the command is formatted incorrectly.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a7c63-306">解决方案</span><span class="sxs-lookup"><span data-stu-id="a7c63-306">Solution</span></span>**  
<span data-ttu-id="a7c63-307">确保执行以下格式的命令：</span><span class="sxs-lookup"><span data-stu-id="a7c63-307">Ensure that the command is executed with the following format:</span></span>

<span data-ttu-id="a7c63-308">Medvhost.exe/GuestWakeup/d： &lt; *duration \ _in \ _minutes* &gt; /v： " &lt; *workspace \ _name* &gt; "，其中</span><span class="sxs-lookup"><span data-stu-id="a7c63-308">Medvhost.exe /GuestWakeup /d:&lt; *duration\_in\_minutes*&gt; /v:”&lt; *workspace\_name*&gt;” where</span></span>

<span data-ttu-id="a7c63-309">&lt;*duration \ _in \ _minutes* &gt;虚拟机应保持唤醒状态的分钟数（默认值为240）和</span><span class="sxs-lookup"><span data-stu-id="a7c63-309">&lt;*duration\_in\_minutes*&gt; is the number of minutes that the virtual machine should stay awake (default is 240) and</span></span>

<span data-ttu-id="a7c63-310">&lt;*工作区 \ _name* &gt;是应唤醒的虚拟机的名称。</span><span class="sxs-lookup"><span data-stu-id="a7c63-310">&lt;*workspace\_name*&gt; is the name of the virtual machine that should be awakened.</span></span>

### <span data-ttu-id="a7c63-311">事件 ID 11002</span><span class="sxs-lookup"><span data-stu-id="a7c63-311">Event ID 11002</span></span>

<span data-ttu-id="a7c63-312">无法更新 MED-V-未检测到主机网络。</span><span class="sxs-lookup"><span data-stu-id="a7c63-312">Cannot update MED-V – No host network detected.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a7c63-313">描述</span><span class="sxs-lookup"><span data-stu-id="a7c63-313">Description</span></span>**  
<span data-ttu-id="a7c63-314">由于未检测到主机网络连接，无法完成来宾修补。</span><span class="sxs-lookup"><span data-stu-id="a7c63-314">Guest patching could not finish because no host network connection was detected.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a7c63-315">解决方案</span><span class="sxs-lookup"><span data-stu-id="a7c63-315">Solution</span></span>**  
<span data-ttu-id="a7c63-316">在运行来宾修补之前，请将 MED-V 主机连接到活动网络连接。</span><span class="sxs-lookup"><span data-stu-id="a7c63-316">Connect the MED-V host to an active network connection before you run guest patching.</span></span>

### <span data-ttu-id="a7c63-317">事件 ID 11003</span><span class="sxs-lookup"><span data-stu-id="a7c63-317">Event ID 11003</span></span>

<span data-ttu-id="a7c63-318">无法更新 MED-V-未在 A/C powerFailed 上运行的主机，无法创建管道服务器。</span><span class="sxs-lookup"><span data-stu-id="a7c63-318">Cannot update MED-V – Host not running on A/C powerFailed to create pipe server.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a7c63-319">描述</span><span class="sxs-lookup"><span data-stu-id="a7c63-319">Description</span></span>**  
<span data-ttu-id="a7c63-320">来宾修补无法完成，因为主机似乎是使用电池电源而不是电源线运行的。</span><span class="sxs-lookup"><span data-stu-id="a7c63-320">Guest patching could not finish because the host appears to be running on battery power instead of from a power cord.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a7c63-321">解决方案</span><span class="sxs-lookup"><span data-stu-id="a7c63-321">Solution</span></span>**  
<span data-ttu-id="a7c63-322">在运行来宾修补之前，请将主机连接到电源线。</span><span class="sxs-lookup"><span data-stu-id="a7c63-322">Connect the host computer to a power cord before you run guest patching.</span></span>

### <span data-ttu-id="a7c63-323">客户 UX</span><span class="sxs-lookup"><span data-stu-id="a7c63-323">Client UX</span></span>

### <span data-ttu-id="a7c63-324">事件 ID 14003</span><span class="sxs-lookup"><span data-stu-id="a7c63-324">Event ID 14003</span></span>

<span data-ttu-id="a7c63-325">以下托盘状态消息太长，无法显示： &lt; *纸盒 \ _status \ _message*&gt;</span><span class="sxs-lookup"><span data-stu-id="a7c63-325">The following tray status message was too long and could not be displayed: &lt;*tray\_status\_message*&gt;</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a7c63-326">描述</span><span class="sxs-lookup"><span data-stu-id="a7c63-326">Description</span></span>**  
<span data-ttu-id="a7c63-327">MED-V 为任务栏工具提示或气球消息创建了一个太长的意外字符串。</span><span class="sxs-lookup"><span data-stu-id="a7c63-327">MED-V created an unanticipated string that was too long for the tray tooltip or balloon message.</span></span> <span data-ttu-id="a7c63-328">因此，所显示的邮件已被截断。</span><span class="sxs-lookup"><span data-stu-id="a7c63-328">As a result, the displayed message was truncated.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a7c63-329">解决方案</span><span class="sxs-lookup"><span data-stu-id="a7c63-329">Solution</span></span>**  
<span data-ttu-id="a7c63-330">这是一个很少的错误，在 MED-V 随机创建工具提示文本时可能会发生此错误。</span><span class="sxs-lookup"><span data-stu-id="a7c63-330">This is a rare error that can occur when MED-V is randomly creating the tooltip text.</span></span> <span data-ttu-id="a7c63-331">没有解决方案。</span><span class="sxs-lookup"><span data-stu-id="a7c63-331">There is no solution.</span></span>

### <span data-ttu-id="a7c63-332">事件 ID 14004</span><span class="sxs-lookup"><span data-stu-id="a7c63-332">Event ID 14004</span></span>

<span data-ttu-id="a7c63-333">由于未处理的异常，MED-V 已停止。</span><span class="sxs-lookup"><span data-stu-id="a7c63-333">MED-V stopped due to an unhandled exception.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a7c63-334">描述</span><span class="sxs-lookup"><span data-stu-id="a7c63-334">Description</span></span>**  
<span data-ttu-id="a7c63-335">未处理的异常导致 MED-V 停止意外停止。</span><span class="sxs-lookup"><span data-stu-id="a7c63-335">An unhandled exception caused MED-V to stop unexpectedly.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a7c63-336">解决方案</span><span class="sxs-lookup"><span data-stu-id="a7c63-336">Solution</span></span>**  
<span data-ttu-id="a7c63-337">重启 MED-V。</span><span class="sxs-lookup"><span data-stu-id="a7c63-337">Restart MED-V.</span></span>

### <span data-ttu-id="a7c63-338">事件 ID 14005</span><span class="sxs-lookup"><span data-stu-id="a7c63-338">Event ID 14005</span></span>

<span data-ttu-id="a7c63-339">服务器试图创建互斥体，但它已经存在。</span><span class="sxs-lookup"><span data-stu-id="a7c63-339">Server attempted to create mutex but it already existed.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a7c63-340">描述</span><span class="sxs-lookup"><span data-stu-id="a7c63-340">Description</span></span>**  
<span data-ttu-id="a7c63-341">MedvHost.exe 的第二个实例停留在内存中。</span><span class="sxs-lookup"><span data-stu-id="a7c63-341">A second instance of MedvHost.exe is stuck in memory.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a7c63-342">解决方案</span><span class="sxs-lookup"><span data-stu-id="a7c63-342">Solution</span></span>**  
<span data-ttu-id="a7c63-343">打开 TaskManager 并结束所有 MedvHost.exe 进程。</span><span class="sxs-lookup"><span data-stu-id="a7c63-343">Open TaskManager and end all MedvHost.exe processes.</span></span>

### <span data-ttu-id="a7c63-344">事件 ID 14006</span><span class="sxs-lookup"><span data-stu-id="a7c63-344">Event ID 14006</span></span>

<span data-ttu-id="a7c63-345">修改或删除注册表值 &lt; *注册表 \ _value*时出错 &gt; 。</span><span class="sxs-lookup"><span data-stu-id="a7c63-345">Error modifying or deleting registry value &lt;*registry\_value*&gt;.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a7c63-346">描述</span><span class="sxs-lookup"><span data-stu-id="a7c63-346">Description</span></span>**  
<span data-ttu-id="a7c63-347">MED-V 无法修改注册表中的指定条目。</span><span class="sxs-lookup"><span data-stu-id="a7c63-347">MED-V is unable to modify the specified entry in the registry.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a7c63-348">解决方案</span><span class="sxs-lookup"><span data-stu-id="a7c63-348">Solution</span></span>**  
<span data-ttu-id="a7c63-349">确保安装或卸载具有管理凭据的 MED-V。</span><span class="sxs-lookup"><span data-stu-id="a7c63-349">Ensure that you install or uninstall MED-V with administrative credentials.</span></span>

### <span data-ttu-id="a7c63-350">事件 ID 14007</span><span class="sxs-lookup"><span data-stu-id="a7c63-350">Event ID 14007</span></span>

<span data-ttu-id="a7c63-351">指定的文件（ &lt; *文件名* &gt; ）无效。</span><span class="sxs-lookup"><span data-stu-id="a7c63-351">The file specified (&lt;*filename*&gt;) is not valid.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a7c63-352">描述</span><span class="sxs-lookup"><span data-stu-id="a7c63-352">Description</span></span>**  
<span data-ttu-id="a7c63-353">在安装或卸载期间，已将损坏的临时文件传递到了 MED-V 主机。</span><span class="sxs-lookup"><span data-stu-id="a7c63-353">During install or uninstall, a corrupted temp file was passed to MED-V host.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a7c63-354">解决方案</span><span class="sxs-lookup"><span data-stu-id="a7c63-354">Solution</span></span>**  
<span data-ttu-id="a7c63-355">删除 Temp 文件夹中的所有文件，然后重新安装或卸载 MED-V。</span><span class="sxs-lookup"><span data-stu-id="a7c63-355">Delete all files in the Temp folder and reinstall or uninstall MED-V.</span></span>

### <span data-ttu-id="a7c63-356">事件 ID 14008</span><span class="sxs-lookup"><span data-stu-id="a7c63-356">Event ID 14008</span></span>

<span data-ttu-id="a7c63-357">找不到文件： &lt; *filename* &gt; 。</span><span class="sxs-lookup"><span data-stu-id="a7c63-357">File not found: &lt;*filename*&gt;.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a7c63-358">描述</span><span class="sxs-lookup"><span data-stu-id="a7c63-358">Description</span></span>**  
<span data-ttu-id="a7c63-359">在安装或卸载期间，找不到所需 temp 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="a7c63-359">During install or uninstall, a path of a required temp file was not found.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a7c63-360">解决方案</span><span class="sxs-lookup"><span data-stu-id="a7c63-360">Solution</span></span>**  
<span data-ttu-id="a7c63-361">删除 Temp 文件夹中的所有文件，然后重新安装或卸载 MED-V。</span><span class="sxs-lookup"><span data-stu-id="a7c63-361">Delete all files in the Temp folder and reinstall or uninstall MED-V.</span></span>

### <span data-ttu-id="a7c63-362">事件 ID 14009</span><span class="sxs-lookup"><span data-stu-id="a7c63-362">Event ID 14009</span></span>

<span data-ttu-id="a7c63-363">无法读取参数文件 &lt; *文件名* &gt; 。</span><span class="sxs-lookup"><span data-stu-id="a7c63-363">Unable to read parameter file &lt;*filename*&gt;.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a7c63-364">描述</span><span class="sxs-lookup"><span data-stu-id="a7c63-364">Description</span></span>**  
<span data-ttu-id="a7c63-365">在安装或卸载过程中，MED-V 无法读取临时文件。</span><span class="sxs-lookup"><span data-stu-id="a7c63-365">During the install or uninstall process, MED-V was unable to read a temp file.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a7c63-366">解决方案</span><span class="sxs-lookup"><span data-stu-id="a7c63-366">Solution</span></span>**  
<span data-ttu-id="a7c63-367">删除 Temp 文件夹中的所有文件，然后重新安装或卸载 MED-V。</span><span class="sxs-lookup"><span data-stu-id="a7c63-367">Delete all files in the Temp folder and reinstall or uninstall MED-V.</span></span> <span data-ttu-id="a7c63-368">此外，验证用户是否具有 Temp 文件夹的必需权限。</span><span class="sxs-lookup"><span data-stu-id="a7c63-368">In addition, verify that the user has the necessary rights and permissions to the Temp folder.</span></span>

### <span data-ttu-id="a7c63-369">事件 ID 14010</span><span class="sxs-lookup"><span data-stu-id="a7c63-369">Event ID 14010</span></span>

<span data-ttu-id="a7c63-370">反序列化参数文件文件名时出错 &lt; *filename* &gt; 。</span><span class="sxs-lookup"><span data-stu-id="a7c63-370">Error deserializing parameter file &lt;*filename*&gt;.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a7c63-371">描述</span><span class="sxs-lookup"><span data-stu-id="a7c63-371">Description</span></span>**  
<span data-ttu-id="a7c63-372">在安装或卸载过程中，MED-V 遇到损坏的临时文件。</span><span class="sxs-lookup"><span data-stu-id="a7c63-372">During the install or uninstall process, MED-V encountered a corrupted temp file.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a7c63-373">解决方案</span><span class="sxs-lookup"><span data-stu-id="a7c63-373">Solution</span></span>**  
<span data-ttu-id="a7c63-374">删除 Temp 文件夹中的所有文件，然后重新安装或卸载 MED-V。</span><span class="sxs-lookup"><span data-stu-id="a7c63-374">Delete all files in the Temp folder and reinstall or uninstall MED-V.</span></span> <span data-ttu-id="a7c63-375">此外，验证用户是否具有 Temp 文件夹的必需权限。</span><span class="sxs-lookup"><span data-stu-id="a7c63-375">In addition, verify that the user has the necessary rights and permissions to the Temp folder.</span></span>

### <span data-ttu-id="a7c63-376">事件 ID 14011</span><span class="sxs-lookup"><span data-stu-id="a7c63-376">Event ID 14011</span></span>

<span data-ttu-id="a7c63-377">反序列化参数文件文件名时发生意外错误 &lt; *filename* &gt; 。</span><span class="sxs-lookup"><span data-stu-id="a7c63-377">Unexpected error deserializing parameter file &lt;*filename*&gt;.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a7c63-378">描述</span><span class="sxs-lookup"><span data-stu-id="a7c63-378">Description</span></span>**  
<span data-ttu-id="a7c63-379">在安装或卸载过程中，MED-V 遇到损坏的临时文件。</span><span class="sxs-lookup"><span data-stu-id="a7c63-379">During the install or uninstall process, MED-V encountered a corrupted temp file.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a7c63-380">解决方案</span><span class="sxs-lookup"><span data-stu-id="a7c63-380">Solution</span></span>**  
<span data-ttu-id="a7c63-381">删除 Temp 文件夹中的所有文件，然后重新安装或卸载 MED-V。</span><span class="sxs-lookup"><span data-stu-id="a7c63-381">Delete all files in the Temp folder and reinstall or uninstall MED-V.</span></span> <span data-ttu-id="a7c63-382">此外，验证用户是否具有 Temp 文件夹的必需权限。</span><span class="sxs-lookup"><span data-stu-id="a7c63-382">In addition, verify that the user has the necessary rights and permissions to the Temp folder.</span></span>

### <span data-ttu-id="a7c63-383">事件 ID 14012</span><span class="sxs-lookup"><span data-stu-id="a7c63-383">Event ID 14012</span></span>

<span data-ttu-id="a7c63-384">在 &lt; 为用户用户名设置文件夹*文件夹 \ _name*的设置权限时发生意外错误 &gt; &lt; *username* &gt; 。</span><span class="sxs-lookup"><span data-stu-id="a7c63-384">Unexpected error when settings rights on folder &lt;*folder\_name*&gt; for user &lt;*username*&gt;.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a7c63-385">描述</span><span class="sxs-lookup"><span data-stu-id="a7c63-385">Description</span></span>**  
<span data-ttu-id="a7c63-386">当 MED-V 无法在安装期间设置某些文件夹的权限和权限时，将出现错误。</span><span class="sxs-lookup"><span data-stu-id="a7c63-386">An error occurs when MED-V is unable to set rights and permissions on certain folders during installation.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a7c63-387">解决方案</span><span class="sxs-lookup"><span data-stu-id="a7c63-387">Solution</span></span>**  
<span data-ttu-id="a7c63-388">检查下列文件夹的管理员权限：</span><span class="sxs-lookup"><span data-stu-id="a7c63-388">Check the administrator rights to the following folders:</span></span>

<span data-ttu-id="a7c63-389">@"%ProgramData%\\Microsoft\\Medv\\AllUsers"</span><span class="sxs-lookup"><span data-stu-id="a7c63-389">@"%ProgramData%\\Microsoft\\Medv\\AllUsers"</span></span>

<span data-ttu-id="a7c63-390">@"%ProgramData%\\Microsoft\\Medv\\MedvLock"</span><span class="sxs-lookup"><span data-stu-id="a7c63-390">@"%ProgramData%\\Microsoft\\Medv\\MedvLock"</span></span>

<span data-ttu-id="a7c63-391">@"%ProgramData%\\Microsoft\\Medv\\Monitoring"</span><span class="sxs-lookup"><span data-stu-id="a7c63-391">@"%ProgramData%\\Microsoft\\Medv\\Monitoring"</span></span>

### <span data-ttu-id="a7c63-392">事件 ID 14013</span><span class="sxs-lookup"><span data-stu-id="a7c63-392">Event ID 14013</span></span>

<span data-ttu-id="a7c63-393">创建锁定文件时出现意外错误。</span><span class="sxs-lookup"><span data-stu-id="a7c63-393">Unexpected error when creating lock file.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a7c63-394">描述</span><span class="sxs-lookup"><span data-stu-id="a7c63-394">Description</span></span>**  
<span data-ttu-id="a7c63-395">当 MED-V 在安装期间无法在 @ "%ProgramData%\\Microsoft\\Medv\\MedvLock" 文件夹中创建文件时，会出现错误。</span><span class="sxs-lookup"><span data-stu-id="a7c63-395">An error occurs when MED-V is unable to create a file in the @"%ProgramData%\\Microsoft\\Medv\\MedvLock" folder during installation.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a7c63-396">解决方案</span><span class="sxs-lookup"><span data-stu-id="a7c63-396">Solution</span></span>**  
<span data-ttu-id="a7c63-397">检查 MedvLock 文件夹的管理员权限。</span><span class="sxs-lookup"><span data-stu-id="a7c63-397">Check the administrator rights to the MedvLock folder.</span></span>

## <span data-ttu-id="a7c63-398">相关主题</span><span class="sxs-lookup"><span data-stu-id="a7c63-398">Related topics</span></span>


[<span data-ttu-id="a7c63-399">MED-V 故障排除</span><span class="sxs-lookup"><span data-stu-id="a7c63-399">Troubleshooting MED-V</span></span>](troubleshooting-med-vmedv2.md)

 

 





