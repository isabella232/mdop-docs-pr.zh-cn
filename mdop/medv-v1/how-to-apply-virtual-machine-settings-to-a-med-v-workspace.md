---
title: 如何将虚拟机设置应用于 MED-V 工作区
description: 如何将虚拟机设置应用于 MED-V 工作区
author: dansimp
ms.assetid: b50d0dfb-8d61-4543-9607-a29bbb1ed45f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9662bb8202285d51971eeea8beaef938b98ed6b0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803875"
---
# <span data-ttu-id="0a6f1-103">如何将虚拟机设置应用于 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="0a6f1-103">How to Apply Virtual Machine Settings to a MED-V Workspace</span></span>


<span data-ttu-id="0a6f1-104">每个 MED-V 工作区都必须具有与其关联的 Microsoft 虚拟 PC 映像。</span><span class="sxs-lookup"><span data-stu-id="0a6f1-104">Every MED-V workspace must have a Microsoft Virtual PC image associated with it.</span></span> <span data-ttu-id="0a6f1-105">虚拟机设置使你能够分配虚拟 PC 映像以及设置其他虚拟机属性。</span><span class="sxs-lookup"><span data-stu-id="0a6f1-105">The virtual machine settings enable you to assign a Virtual PC image as well as set other virtual machine properties.</span></span>

<span data-ttu-id="0a6f1-106">所有虚拟机设置均在 "**虚拟机设置**" 选项卡上的 "**策略**" 模块中配置。</span><span class="sxs-lookup"><span data-stu-id="0a6f1-106">All virtual machine settings are configured in the **Policy** module, on the **Virtual Machine Settings** tab.</span></span>

**<span data-ttu-id="0a6f1-107">将虚拟机设置应用于 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="0a6f1-107">To apply virtual machine settings to a MED-V workspace</span></span>**

1.  <span data-ttu-id="0a6f1-108">单击要配置的 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="0a6f1-108">Click the MED-V workspace to configure.</span></span>

2.  <span data-ttu-id="0a6f1-109">按下表所述配置虚拟机属性。</span><span class="sxs-lookup"><span data-stu-id="0a6f1-109">Configure the virtual machine properties as described in the following table.</span></span>

3.  <span data-ttu-id="0a6f1-110">在 "**策略**" 菜单上，选择 "**提交**"。</span><span class="sxs-lookup"><span data-stu-id="0a6f1-110">On the **Policy** menu, select **Commit**.</span></span>

**<span data-ttu-id="0a6f1-111">虚拟机属性</span><span class="sxs-lookup"><span data-stu-id="0a6f1-111">Virtual Machine Properties</span></span>**

<span data-ttu-id="0a6f1-112">属性说明*虚拟机设置*</span><span class="sxs-lookup"><span data-stu-id="0a6f1-112">Property Description *Virtual Machine Settings*</span></span>

<span data-ttu-id="0a6f1-113">已分配图像</span><span class="sxs-lookup"><span data-stu-id="0a6f1-113">Assigned Image</span></span>

<span data-ttu-id="0a6f1-114">分配给 MED-V 工作区的实际 Microsoft 虚拟 PC 映像。</span><span class="sxs-lookup"><span data-stu-id="0a6f1-114">The actual Microsoft Virtual PC image assigned to the MED-V workspace.</span></span> <span data-ttu-id="0a6f1-115">该菜单提供所有可用虚拟 PC 映像的列表。</span><span class="sxs-lookup"><span data-stu-id="0a6f1-115">The menu provides a list of all available Virtual PC images.</span></span> <span data-ttu-id="0a6f1-116">**活动**图像列表中有以下图像类型：</span><span class="sxs-lookup"><span data-stu-id="0a6f1-116">The following image types are in the **Active** image list:</span></span>

-   <span data-ttu-id="0a6f1-117">**本地测试图像**-尚未打包的本地计算机上的图像。</span><span class="sxs-lookup"><span data-stu-id="0a6f1-117">**Local test images**—Images on the local computer that are not yet packed.</span></span> <span data-ttu-id="0a6f1-118">这些图像名称后接括号（test）中的 "test" 一词，仅用于测试目的。</span><span class="sxs-lookup"><span data-stu-id="0a6f1-118">These image names are followed by the word “test” in parentheses (test) and are for testing purposes only.</span></span>

-   <span data-ttu-id="0a6f1-119">**本地打包的图像**-在本地计算机上打包的图像。</span><span class="sxs-lookup"><span data-stu-id="0a6f1-119">**Local packed images**—Packed images on the local computer.</span></span> <span data-ttu-id="0a6f1-120">这些图像后跟一个括号（本地）中的 "本地" 字样，并且客户端无法下载这些图像，直到管理员将它们上载到服务器。</span><span class="sxs-lookup"><span data-stu-id="0a6f1-120">These images are followed by the word “local” in parentheses (local) and cannot be downloaded by clients until the administrator uploads them to the server.</span></span>

    <span data-ttu-id="0a6f1-121">如果创建将通过可移动媒体（如 USB 或 DVD）分发给客户端的程序包，则可以选择本地映像。</span><span class="sxs-lookup"><span data-stu-id="0a6f1-121">A local image can be selected if you are creating a package that will be distributed to the client via removable media (such as USB or DVD).</span></span>

-   <span data-ttu-id="0a6f1-122">**服务器上的压缩图像**（服务器上的图像，可供客户端下载）。</span><span class="sxs-lookup"><span data-stu-id="0a6f1-122">**Packed images on server**—Images that are on the server and are available for download by clients.</span></span> <span data-ttu-id="0a6f1-123">单击 "刷新" 以刷新图像列表。</span><span class="sxs-lookup"><span data-stu-id="0a6f1-123">Click Refresh to refresh the images list.</span></span>

    <span data-ttu-id="0a6f1-124">**注意** 每个 MED-V 工作区映像仅可由一个 Windows 用户使用。</span><span class="sxs-lookup"><span data-stu-id="0a6f1-124">**Note** Each MED-V workspace image can only be used by one Windows user.</span></span>

     

<span data-ttu-id="0a6f1-125">工作区持久</span><span class="sxs-lookup"><span data-stu-id="0a6f1-125">Workspace is persistent</span></span>

<span data-ttu-id="0a6f1-126">选中此复选框以将 MED-V 工作区配置为永久。</span><span class="sxs-lookup"><span data-stu-id="0a6f1-126">Select this check box to configure the MED-V workspace as persistent.</span></span> <span data-ttu-id="0a6f1-127">在持久的 MED-V 工作区中，当 MED-V 工作区停止时，将在 MED-V 工作区中保存对 MED-V 工作区所做的更改和添加。</span><span class="sxs-lookup"><span data-stu-id="0a6f1-127">In a persistent MED-V workspace, when the MED-V workspace is stopped, changes and additions to the MED-V workspace are saved in the MED-V workspace.</span></span>

<span data-ttu-id="0a6f1-128">对于域 MED-V 工作区，必须选择此选项。</span><span class="sxs-lookup"><span data-stu-id="0a6f1-128">For a Domain MED-V workspace, this option must be selected.</span></span>

<span data-ttu-id="0a6f1-129">**注意** 在将 MED-V 工作区部署给用户后，不应更改此设置。</span><span class="sxs-lookup"><span data-stu-id="0a6f1-129">**Note** This setting should not be changed after a MED-V workspace is deployed to users.</span></span>

 

<span data-ttu-id="0a6f1-130">停止工作区时关闭 VM</span><span class="sxs-lookup"><span data-stu-id="0a6f1-130">Shut down the VM when stopping the Workspace</span></span>

<span data-ttu-id="0a6f1-131">选中此复选框以在停止 MED-V 工作区时关闭虚拟机。</span><span class="sxs-lookup"><span data-stu-id="0a6f1-131">Select this check box to shut down the virtual machine when stopping the MED-V workspace.</span></span> <span data-ttu-id="0a6f1-132">如果清除此复选框，则在每个会话完成时，虚拟机不会关闭，而是获取虚拟机的快照。</span><span class="sxs-lookup"><span data-stu-id="0a6f1-132">If this check box is cleared, at the completion of each session, the virtual machine is not shut down but instead takes a snapshot of the virtual machine.</span></span> <span data-ttu-id="0a6f1-133">当启动新会话时，Windows 将从快照开始（即 Windows 不会重新启动，也不需要登录）。</span><span class="sxs-lookup"><span data-stu-id="0a6f1-133">Upon the initiation of a new session, Windows starts from the snapshot (that is, Windows does not restart and no login is required).</span></span>

<span data-ttu-id="0a6f1-134">**注意** 仅当选择了 "**工作区持久**" 时，才会启用此属性。</span><span class="sxs-lookup"><span data-stu-id="0a6f1-134">**Note** This property is enabled only if **Workspace is persistent** is selected.</span></span>

 

<span data-ttu-id="0a6f1-135">使用 MED-V 凭据（SSO）登录到 VM 中的 Windows</span><span class="sxs-lookup"><span data-stu-id="0a6f1-135">Logon to Windows in VM using MED-V credentials (SSO)</span></span>

<span data-ttu-id="0a6f1-136">选中此复选框以使用登录到 MED-V 客户端时输入的 MED-V 凭据在虚拟机上登录到 Windows。</span><span class="sxs-lookup"><span data-stu-id="0a6f1-136">Select this check box to log in to Windows on the virtual machine by using the MED-V credentials entered when logging in to MED-V client.</span></span>

<span data-ttu-id="0a6f1-137">**注意** 仅当选择了 "**工作区持久**" 时，才会启用此属性。</span><span class="sxs-lookup"><span data-stu-id="0a6f1-137">**Note** This property is enabled only when **Workspace is persistent** is selected.</span></span>

 

<span data-ttu-id="0a6f1-138">工作区为 revertible</span><span class="sxs-lookup"><span data-stu-id="0a6f1-138">Workspace is revertible</span></span>

<span data-ttu-id="0a6f1-139">选中此复选框以将 MED-V 工作区配置为 revertible。</span><span class="sxs-lookup"><span data-stu-id="0a6f1-139">Select this check box to configure the MED-V workspace as revertible.</span></span> <span data-ttu-id="0a6f1-140">在 revertible 的 MED-V 工作区中，在每个会话完成时（即当用户停止 MED-V 工作区时），MED-V 工作区将还原为部署期间它所处的原始状态。</span><span class="sxs-lookup"><span data-stu-id="0a6f1-140">In a revertible MED-V workspace, at the completion of each session (that is, when the user stops the MED-V workspace), the MED-V workspace reverts to the original state it was in during deployment.</span></span> <span data-ttu-id="0a6f1-141">在会话之间的 MED-V 工作区中，不会保存用户所做的任何更改或添加。</span><span class="sxs-lookup"><span data-stu-id="0a6f1-141">No changes or additions that the user made are saved on the MED-V workspace between sessions.</span></span>

<span data-ttu-id="0a6f1-142">**注意** 在将 MED-V 工作区部署给用户后，不应更改此设置。</span><span class="sxs-lookup"><span data-stu-id="0a6f1-142">**Note** This setting should not be changed after a MED-V workspace is deployed to users.</span></span>

 

<span data-ttu-id="0a6f1-143">将工作区时区与主机同步</span><span class="sxs-lookup"><span data-stu-id="0a6f1-143">Synchronize Workspace time zone with host</span></span>

<span data-ttu-id="0a6f1-144">选中此复选框以将 MED-V 工作区中的时区与主机同步。</span><span class="sxs-lookup"><span data-stu-id="0a6f1-144">Select this check box to synchronize the time zone in the MED-V workspace with the host.</span></span>

<span data-ttu-id="0a6f1-145">同步的工作方式会有所不同，具体取决于 MED-V 工作区是否为 persistent 或 revertible，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0a6f1-145">The synchronization works differently depending on whether the MED-V workspace is persistent or revertible, as follows:</span></span>

-   <span data-ttu-id="0a6f1-146">在永久性的 MED-V 工作区中，时区首先尝试与服务器同步。</span><span class="sxs-lookup"><span data-stu-id="0a6f1-146">In a persistent MED-V workspace, the time zone first tries to synchronize with the server.</span></span> <span data-ttu-id="0a6f1-147">如果此操作失败，它将与主机同步。</span><span class="sxs-lookup"><span data-stu-id="0a6f1-147">If that fails, it synchronizes with the host.</span></span>

-   <span data-ttu-id="0a6f1-148">在 revertible MED-V 工作区中，时区与主机同步。</span><span class="sxs-lookup"><span data-stu-id="0a6f1-148">In a revertible MED-V workspace, the time zone synchronizes with the host.</span></span>

*<span data-ttu-id="0a6f1-149">锁定设置</span><span class="sxs-lookup"><span data-stu-id="0a6f1-149">Lock Settings</span></span>*

<span data-ttu-id="0a6f1-150">在主机待机/休眠事件上锁定工作区</span><span class="sxs-lookup"><span data-stu-id="0a6f1-150">Lock the Workspace on host standby/hibernate event</span></span>

<span data-ttu-id="0a6f1-151">选中此复选框可在主机进入待机或休眠状态时自动锁定 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="0a6f1-151">Select this check box to automatically lock the MED-V workspace when the host computer goes into standby or hibernate.</span></span>

<span data-ttu-id="0a6f1-152">后锁定工作区</span><span class="sxs-lookup"><span data-stu-id="0a6f1-152">Lock the Workspace after</span></span>

<span data-ttu-id="0a6f1-153">选中此复选框以在 MED-V 工作区在指定时间段空闲时锁定 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="0a6f1-153">Select this check box to lock the MED-V workspace when the MED-V workspace is idle for a specified period of time.</span></span> <span data-ttu-id="0a6f1-154">选中此选项时，将启用 "数字" 框。</span><span class="sxs-lookup"><span data-stu-id="0a6f1-154">When selected, the number box is enabled.</span></span> <span data-ttu-id="0a6f1-155">输入锁定 MED-V 工作区之前空闲时间的分钟数。</span><span class="sxs-lookup"><span data-stu-id="0a6f1-155">Enter the number of minutes of idle time before locking the MED-V workspace.</span></span>

<span data-ttu-id="0a6f1-156">**注意** 空闲时间指的是 MED-V 工作区应用程序（而不是宿主应用程序）。</span><span class="sxs-lookup"><span data-stu-id="0a6f1-156">**Note** The idle time refers to the MED-V workspace applications (not the host applications).</span></span>

 

*<span data-ttu-id="0a6f1-157">图像更新设置</span><span class="sxs-lookup"><span data-stu-id="0a6f1-157">Image Update Settings</span></span>*

<span data-ttu-id="0a6f1-158">仅保留</span><span class="sxs-lookup"><span data-stu-id="0a6f1-158">Keep only</span></span>

<span data-ttu-id="0a6f1-159">选中此复选框以限制要保留的旧图像版本的数量。</span><span class="sxs-lookup"><span data-stu-id="0a6f1-159">Select this check box to limit the number of old image versions to keep.</span></span>

<span data-ttu-id="0a6f1-160">选中此选项时，将启用 "数字" 框。</span><span class="sxs-lookup"><span data-stu-id="0a6f1-160">When selected, the number box is enabled.</span></span> <span data-ttu-id="0a6f1-161">输入要保留的旧版本数。</span><span class="sxs-lookup"><span data-stu-id="0a6f1-161">Enter the number of old versions to keep.</span></span>

<span data-ttu-id="0a6f1-162">当有新版本可用时建议更新</span><span class="sxs-lookup"><span data-stu-id="0a6f1-162">Suggest update when a new version is available</span></span>

<span data-ttu-id="0a6f1-163">选中此复选框可在新版本的映像可用时建议（但不强制）更新。</span><span class="sxs-lookup"><span data-stu-id="0a6f1-163">Select this check box to suggest (but not force) an update when a new version of the image is available.</span></span>

<span data-ttu-id="0a6f1-164">下载此工作区的图像时，客户端应使用剪裁传输</span><span class="sxs-lookup"><span data-stu-id="0a6f1-164">Clients should use Trim Transfer when downloading images for this Workspace</span></span>

<span data-ttu-id="0a6f1-165">选中此复选框以启用裁切传输（有关详细信息，请参阅[Med-v 剪裁传输技术](med-v-trim-transfer-technology-medvv2.md)），以便下载与此 med-v 工作区相关联的图像。</span><span class="sxs-lookup"><span data-stu-id="0a6f1-165">Select this check box to enable Trim Transfer (for more information, see [MED-V Trim Transfer Technology](med-v-trim-transfer-technology-medvv2.md)) when downloading images associated with this MED-V workspace.</span></span> <span data-ttu-id="0a6f1-166">如果清除此复选框，将下载完整图像。</span><span class="sxs-lookup"><span data-stu-id="0a6f1-166">If this check box is cleared, the full image will be downloaded.</span></span>

<span data-ttu-id="0a6f1-167">**注意** 修剪传输需要索引硬盘，这可能需要花费大量时间。</span><span class="sxs-lookup"><span data-stu-id="0a6f1-167">**Note** Trim Transfer requires indexing the hard drive, which might take a considerable amount of time.</span></span> <span data-ttu-id="0a6f1-168">当索引硬盘比下载新图像版本更高效时（例如，当下载与现有版本类似的图像版本时），建议使用 "裁切转移"。</span><span class="sxs-lookup"><span data-stu-id="0a6f1-168">It is recommended to use Trim Transfer when indexing the hard drive is more efficient than downloading the new image version, such as when downloading an image version that is similar to the existing version.</span></span>

 

 

## <span data-ttu-id="0a6f1-169">相关主题</span><span class="sxs-lookup"><span data-stu-id="0a6f1-169">Related topics</span></span>


[<span data-ttu-id="0a6f1-170">创建 MED-V 映像</span><span class="sxs-lookup"><span data-stu-id="0a6f1-170">Creating a MED-V Image</span></span>](creating-a-med-v-image.md)

[<span data-ttu-id="0a6f1-171">使用 MED-V 管理控制台用户界面</span><span class="sxs-lookup"><span data-stu-id="0a6f1-171">Using the MED-V Management Console User Interface</span></span>](using-the-med-v-management-console-user-interface.md)

[<span data-ttu-id="0a6f1-172">创建 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="0a6f1-172">Creating a MED-V Workspace</span></span>](creating-a-med-v-workspacemedv-10-sp1.md)

 

 





