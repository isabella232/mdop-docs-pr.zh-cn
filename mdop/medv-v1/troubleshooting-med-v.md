---
title: MED-V 故障排除
description: MED-V 故障排除
author: dansimp
ms.assetid: f43dae36-6485-4e06-9c66-0a646e27079d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 38d13be699a92368ff258026acd8e0d5f0e28cd6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803853"
---
# <span data-ttu-id="7d457-103">MED-V 故障排除</span><span class="sxs-lookup"><span data-stu-id="7d457-103">Troubleshooting MED-V</span></span>


<span data-ttu-id="7d457-104">本部分提供的信息可帮助解决 Microsoft 企业桌面虚拟化（MED-V）中的常见问题。</span><span class="sxs-lookup"><span data-stu-id="7d457-104">This section provides information to help troubleshoot general issues with Microsoft Enterprise Desktop Virtualization (MED-V).</span></span>

## <span data-ttu-id="7d457-105">更改主机分辨率，然后最大化 MED-V 工作区使桌面显示为黑色</span><span class="sxs-lookup"><span data-stu-id="7d457-105">Changing the host resolution and then maximizing the MED-V workspace causes the desktop to appear black</span></span>


<span data-ttu-id="7d457-106">在完整桌面模式下工作时，如果更改主机分辨率，然后最大化 MED-V 工作区窗口，则桌面会显示为黑色，并且 MED-V 工作区可能不会响应。</span><span class="sxs-lookup"><span data-stu-id="7d457-106">When working in full desktop mode, if you change the host resolution and then maximize the MED-V workspace window, the desktop appears black and the MED-V workspace might not respond.</span></span>

### <span data-ttu-id="7d457-107">解决方案</span><span class="sxs-lookup"><span data-stu-id="7d457-107">Solution</span></span>

<span data-ttu-id="7d457-108">停止并启动 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="7d457-108">Stop and then start the MED-V workspace.</span></span>

## <span data-ttu-id="7d457-109">在禁用网络适配器后启动 MED-V 工作区，随后启用适配器不会还原网络连接</span><span class="sxs-lookup"><span data-stu-id="7d457-109">Starting a MED-V workspace with a network adapter disabled and then later enabling the adapter does not restore network connectivity</span></span>


<span data-ttu-id="7d457-110">如果在桥模式下配置 MED-V 工作区，然后在禁用网络适配器时启动 MED-V 工作区，则如果该适配器已启用，则不会还原通过该适配器的网络连接。</span><span class="sxs-lookup"><span data-stu-id="7d457-110">If you configure a MED-V workspace in bridge mode and then start the MED-V workspace while a network adapter is disabled, if the adapter is later enabled, the network connectivity through that adapter is not restored.</span></span>

### <span data-ttu-id="7d457-111">解决方案</span><span class="sxs-lookup"><span data-stu-id="7d457-111">Solution</span></span>

<span data-ttu-id="7d457-112">停止并启动 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="7d457-112">Stop and then start the MED-V workspace.</span></span>

## <span data-ttu-id="7d457-113">每台计算机只能由一个 Windows 用户使用图像</span><span class="sxs-lookup"><span data-stu-id="7d457-113">An image can be used by only one Windows user per computer</span></span>


<span data-ttu-id="7d457-114">MED-V 工作区映像只能由下载或导入该映像的 Windows 用户使用。</span><span class="sxs-lookup"><span data-stu-id="7d457-114">A MED-V workspace image can be used only by the Windows user who downloaded or imported the image.</span></span> <span data-ttu-id="7d457-115">除了对下载的图像所在的文件夹拥有权限的管理员而言，此用户是唯一的用户。</span><span class="sxs-lookup"><span data-stu-id="7d457-115">This user is the only user aside from administrators who have permissions to the folder where the downloaded images are located.</span></span>

### <span data-ttu-id="7d457-116">解决方案</span><span class="sxs-lookup"><span data-stu-id="7d457-116">Solution</span></span>

<span data-ttu-id="7d457-117">在映像存储上手动更改访问控制列表（ACL）。</span><span class="sxs-lookup"><span data-stu-id="7d457-117">Manually change the access control list (ACL) on the image store.</span></span>

## <span data-ttu-id="7d457-118">使用启用了用户权限的配置管理器安装 MED-V 时，卸载失败</span><span class="sxs-lookup"><span data-stu-id="7d457-118">When installing MED-V by using Configuration Manager with users rights enabled, uninstall fails</span></span>


<span data-ttu-id="7d457-119">如果 MED-V 是使用 Microsoft System Center Configuration Manager 安装的，并且程序包的运行模式设置为 "用户权限"，则卸载失败并显示一条错误消息，指出只有管理员用户可以卸载 MED-V。</span><span class="sxs-lookup"><span data-stu-id="7d457-119">If MED-V is installed by using Microsoft System Center Configuration Manager and the run mode of the package is set to users rights, uninstall fails with an error message that says that only administrative users can uninstall MED-V.</span></span>

### <span data-ttu-id="7d457-120">解决方案</span><span class="sxs-lookup"><span data-stu-id="7d457-120">Solution</span></span>

<span data-ttu-id="7d457-121">创建 MED-V 的 Configuration Manager 程序包时，请将 "运行模式" 设置为 "管理权限"。</span><span class="sxs-lookup"><span data-stu-id="7d457-121">When creating a Configuration Manager package for MED-V, set the run mode to administrative rights.</span></span>

## <span data-ttu-id="7d457-122">使用企业部署系统安装 MED-V 时（安装过程配置为在安装后运行客户端）时，无法运行客户端</span><span class="sxs-lookup"><span data-stu-id="7d457-122">When installing MED-V by using a corporate deployment system, where the installation is configured to run the client following installation, you cannot run the client</span></span>


<span data-ttu-id="7d457-123">如果 MED-V 是使用企业部署系统安装的，并且安装程序包配置为在安装后运行 MED-V 客户端，则在客户端在系统帐户下运行后，你将看不到客户端正在运行（在通知区域中除外），你无法与之进行交互。</span><span class="sxs-lookup"><span data-stu-id="7d457-123">If MED-V is installed by using a corporate deployment system and the installation package is configured to run MED-V client following the installation, after the client is running under the system account, you cannot see that the client is running (except in the notification area), and you cannot interact with it.</span></span>

### <span data-ttu-id="7d457-124">解决方案</span><span class="sxs-lookup"><span data-stu-id="7d457-124">Solution</span></span>

<span data-ttu-id="7d457-125">使用企业部署系统安装 MED-V 时，请使用*START \ _MEDV = 0* .msi 参数。</span><span class="sxs-lookup"><span data-stu-id="7d457-125">When installing MED-V by using a corporate deployment system, use the *START\_MEDV=0* .msi parameter.</span></span>

## <span data-ttu-id="7d457-126">MED-V 测试图像无法启动</span><span class="sxs-lookup"><span data-stu-id="7d457-126">MED-V test image fails to start</span></span>


<span data-ttu-id="7d457-127">如果不能启动 MED-V 测试映像，它将不会恢复，并且所有未来启动将失败，并出现 "GINA 无法加载" 错误消息。</span><span class="sxs-lookup"><span data-stu-id="7d457-127">If a MED-V test image fails to start, it will never recover and all future startups will fail with a “GINA fail to load” error message.</span></span>

### <span data-ttu-id="7d457-128">解决方案</span><span class="sxs-lookup"><span data-stu-id="7d457-128">Solution</span></span>

<span data-ttu-id="7d457-129">删除现有测试映像，然后重新创建它。</span><span class="sxs-lookup"><span data-stu-id="7d457-129">Delete the existing test image and then re-create it.</span></span>

## <span data-ttu-id="7d457-130">在尝试使用错误的凭据加入域之后，该映像在加入域时永远不会成功</span><span class="sxs-lookup"><span data-stu-id="7d457-130">After attempting to join a domain with the wrong credentials, the image never succeeds in joining the domain</span></span>


<span data-ttu-id="7d457-131">如果加入域构建基块中存在配置错误（这是虚拟机首次设置脚本的一部分），则它会在尝试加入域时导致 MED-V 工作区失败。</span><span class="sxs-lookup"><span data-stu-id="7d457-131">If there is a configuration error in the join domain building block, which is part of the virtual machine first-time setup script, it causes the MED-V workspace to fail when attempting to join a domain.</span></span> <span data-ttu-id="7d457-132">修复配置错误后，MED-V 工作区中包含的图像无法加入域。</span><span class="sxs-lookup"><span data-stu-id="7d457-132">After the configuration error is repaired, the image included in the MED-V workspace cannot join the domain.</span></span>

### <span data-ttu-id="7d457-133">解决方案</span><span class="sxs-lookup"><span data-stu-id="7d457-133">Solution</span></span>

<span data-ttu-id="7d457-134">如果已部署映像，请重新发布该映像。</span><span class="sxs-lookup"><span data-stu-id="7d457-134">If the image was deployed, redistribute the image.</span></span> <span data-ttu-id="7d457-135">如果图像是测试图像，请重新创建图像。</span><span class="sxs-lookup"><span data-stu-id="7d457-135">If the image was a test image, re-create the image.</span></span>

## <span data-ttu-id="7d457-136">MED-V 不支持多台监视器</span><span class="sxs-lookup"><span data-stu-id="7d457-136">MED-V does not support multiple monitors</span></span>


<span data-ttu-id="7d457-137">MED-V 不支持在多台监视器上显示已发布的应用程序。</span><span class="sxs-lookup"><span data-stu-id="7d457-137">MED-V does not support displaying published applications across multiple monitors.</span></span> <span data-ttu-id="7d457-138">已发布的应用程序和其他客户端窗口可能显示在错误的屏幕上，有时在屏幕断开连接后，MED-V 会尝试将屏幕发送到监视器，以便连接的监视器显示为空白。</span><span class="sxs-lookup"><span data-stu-id="7d457-138">Published applications and other client windows may be displayed in the wrong screen, and sometimes after a screen is disconnected, MED-V attempts to send the screen to the monitor so that the connected monitor appears blank.</span></span>

### <span data-ttu-id="7d457-139">解决方案</span><span class="sxs-lookup"><span data-stu-id="7d457-139">Solution</span></span>

<span data-ttu-id="7d457-140">断开其他屏幕，然后重新启动客户端。</span><span class="sxs-lookup"><span data-stu-id="7d457-140">Disconnect the additional screen, and restart the client.</span></span>

## <span data-ttu-id="7d457-141">如果在 MED-V 工作区启动期间主机崩溃，则 MED-V 工作区可能无法启动</span><span class="sxs-lookup"><span data-stu-id="7d457-141">MED-V workspace might fail to start if the host crashes during MED-V workspace startup</span></span>


<span data-ttu-id="7d457-142">如果主机在 MED-V 工作区启动过程中崩溃，并且出现一条错误消息，显示 "根元素缺失"，则 MED-V 工作区可能会将数据添加到空虚拟机配置（VMC）文件，这将导致启动过程失败。</span><span class="sxs-lookup"><span data-stu-id="7d457-142">If the host crashes during the MED-V workspace startup process and an error message appears that says “Root element is missing,” the MED-V workspace might add data to an empty virtual machine configuration (VMC) file, which will cause the startup process to fail.</span></span>

### <span data-ttu-id="7d457-143">解决方案</span><span class="sxs-lookup"><span data-stu-id="7d457-143">Solution</span></span>

<span data-ttu-id="7d457-144">将空的 VMC 文件替换为基本图像中的 VMC 文件。</span><span class="sxs-lookup"><span data-stu-id="7d457-144">Replace the empty VMC file with a VMC file from the base image.</span></span>

## <span data-ttu-id="7d457-145">键盘在已发布的应用程序窗口中不响应</span><span class="sxs-lookup"><span data-stu-id="7d457-145">The keyboard does not respond in published application windows</span></span>


<span data-ttu-id="7d457-146">在 MED-V 工作区中，如果在已发布的应用程序处于焦点时按 Windows 徽标键，键盘将不再在已发布的应用程序窗口中响应。</span><span class="sxs-lookup"><span data-stu-id="7d457-146">In a MED-V workspace, if you press the Windows logo key when a published application is in focus, the keyboard no longer responds in published application windows.</span></span>

### <span data-ttu-id="7d457-147">解决方案</span><span class="sxs-lookup"><span data-stu-id="7d457-147">Solution</span></span>

<span data-ttu-id="7d457-148">当已发布的应用程序处于焦点时，按 Windows 徽标键。</span><span class="sxs-lookup"><span data-stu-id="7d457-148">Press the Windows logo key while a published application is in focus.</span></span>

## <span data-ttu-id="7d457-149">域 MED-V 工作区不会更新域凭据</span><span class="sxs-lookup"><span data-stu-id="7d457-149">A domain MED-V workspace does not update domain credentials</span></span>


<span data-ttu-id="7d457-150">在域环境中使用持久的 MED-V 工作区时，如果您更改域密码，则 MED-V 客户端不会更新 MED-V 工作区域凭据。</span><span class="sxs-lookup"><span data-stu-id="7d457-150">When using a persistent MED-V workspace in a domain environment, if you change your domain password, the MED-V client does not update the MED-V workspace domain credentials.</span></span> <span data-ttu-id="7d457-151">当已发布的应用程序尝试访问网络资源时，将收到一条错误消息，通知您凭据已过期。</span><span class="sxs-lookup"><span data-stu-id="7d457-151">When a published application attempts to access a network resource, you will receive an error message notifying you that your credentials expired.</span></span>

### <span data-ttu-id="7d457-152">解决方案</span><span class="sxs-lookup"><span data-stu-id="7d457-152">Solution</span></span>

<span data-ttu-id="7d457-153">重启 MED-V 工作区操作系统。</span><span class="sxs-lookup"><span data-stu-id="7d457-153">Restart the MED-V workspace operating system.</span></span>

## <span data-ttu-id="7d457-154">最大化的已发布应用程序窗口覆盖主机任务栏</span><span class="sxs-lookup"><span data-stu-id="7d457-154">Maximized published application windows cover the host taskbar</span></span>


<span data-ttu-id="7d457-155">如果将已发布的应用程序窗口最大化到全屏，它可能会覆盖主机任务栏。</span><span class="sxs-lookup"><span data-stu-id="7d457-155">If you maximize a published application window to full screen, it might cover the host taskbar.</span></span>

### <span data-ttu-id="7d457-156">解决方案</span><span class="sxs-lookup"><span data-stu-id="7d457-156">Solution</span></span>

<span data-ttu-id="7d457-157">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="7d457-157">Do one of the following:</span></span>

<span data-ttu-id="7d457-158">最小化已发布的应用程序窗口以获取对通知区域的访问权限，然后重启 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="7d457-158">Minimize the published application window to gain access to the notification area, and restart the MED-V workspace.</span></span>

<span data-ttu-id="7d457-159">最小化已发布的应用程序窗口，然后将窗口还原为最大化状态。</span><span class="sxs-lookup"><span data-stu-id="7d457-159">Minimize the published application window, and then restore the window to its maximized state.</span></span>

## <span data-ttu-id="7d457-160">在 MED-V 服务器配置管理器中添加用户或组不起作用</span><span class="sxs-lookup"><span data-stu-id="7d457-160">Adding users or groups in the MED-V Server Configuration Manager does not work</span></span>


<span data-ttu-id="7d457-161">在 "**选择用户或组**" 对话框中添加用户或组时，所选用户或组不会添加到 Med-v 服务器配置管理器中的访问控制列表。</span><span class="sxs-lookup"><span data-stu-id="7d457-161">When adding users or groups in the **Select Users or Groups** dialog box, the selected users or groups are not added to the access control list in the MED-V Server Configuration Manager.</span></span>

### <span data-ttu-id="7d457-162">解决方案</span><span class="sxs-lookup"><span data-stu-id="7d457-162">Solution</span></span>

<span data-ttu-id="7d457-163">使用 "**输入用户或组名称**" 对话框添加用户或组。</span><span class="sxs-lookup"><span data-stu-id="7d457-163">Add users or groups using the **Enter User or Group names** dialog box.</span></span> <span data-ttu-id="7d457-164">有关详细信息，请参阅[如何安装和配置 Med-v 服务器组件](how-to-install-and-configure-the-med-v-server-component.md#bkmk-configuringpermissions)。</span><span class="sxs-lookup"><span data-stu-id="7d457-164">For detailed information, see [How to Install and Configure the MED-V Server Component](how-to-install-and-configure-the-med-v-server-component.md#bkmk-configuringpermissions).</span></span>

## <span data-ttu-id="7d457-165">在安装了 windows 7 的 Windows 虚拟 PC 的计算机上，MED-V 不起作用</span><span class="sxs-lookup"><span data-stu-id="7d457-165">MED-V does not work on computers with Windows Virtual PC for Windows 7 installed</span></span>


<span data-ttu-id="7d457-166">MED-V 需要 Windows 虚拟 PC2007。</span><span class="sxs-lookup"><span data-stu-id="7d457-166">MED-V requires Windows Virtual PC2007.</span></span> <span data-ttu-id="7d457-167">Windows 虚拟电脑 for Windows7 和 Virtual PC2007 SP1 无法安装在同一台计算机上。</span><span class="sxs-lookup"><span data-stu-id="7d457-167">Windows Virtual PC for Windows7 and Virtual PC2007 SP1 cannot be installed on the same computer.</span></span>

### <span data-ttu-id="7d457-168">解决方案</span><span class="sxs-lookup"><span data-stu-id="7d457-168">Solution</span></span>

<span data-ttu-id="7d457-169">在安装 Virtual PC2007 SP1 和 MED-V 之前卸载 Windows7 的虚拟电脑。</span><span class="sxs-lookup"><span data-stu-id="7d457-169">Uninstall Virtual PC for Windows7 before installing Virtual PC2007 SP1 and MED-V.</span></span>

## <a href="" id="med-v-does-not-support-virtual-pc-and-windows-xp-mode-images-"></a><span data-ttu-id="7d457-170">MED-V 不支持虚拟 PC 和 WindowsXP 模式图像</span><span class="sxs-lookup"><span data-stu-id="7d457-170">MED-V does not support Virtual PC and WindowsXP Mode images</span></span>


<span data-ttu-id="7d457-171">MED-V 1.0 SP1 不支持 Windows 虚拟电脑 for Windows7 创建的图像。</span><span class="sxs-lookup"><span data-stu-id="7d457-171">MED-V1.0 SP1 does not support images created by Windows Virtual PC for Windows7.</span></span> <span data-ttu-id="7d457-172">如果使用 Windows7 映像的虚拟 PC，则客户端在启动期间将失败。</span><span class="sxs-lookup"><span data-stu-id="7d457-172">If a Virtual PC for Windows7 image is used, the client will fail during startup.</span></span>

### <span data-ttu-id="7d457-173">解决方案</span><span class="sxs-lookup"><span data-stu-id="7d457-173">Solution</span></span>

<span data-ttu-id="7d457-174">使用 Virtual PC2007 SP1 创建 MED-V 图像。</span><span class="sxs-lookup"><span data-stu-id="7d457-174">Create MED-V images by using Virtual PC2007 SP1.</span></span>

## <span data-ttu-id="7d457-175">Windows 防火墙阻止虚拟 PC2007 SP1 网络活动</span><span class="sxs-lookup"><span data-stu-id="7d457-175">Windows firewall blocks Virtual PC2007 SP1 network activity</span></span>


<span data-ttu-id="7d457-176">默认情况下，Windows 防火墙阻止虚拟 PC2007 SP1 网络活动，并且当 Virtual PC2007 SP1 在客户端计算机上启动时，将阻止其启动顺序和所有网络访问。</span><span class="sxs-lookup"><span data-stu-id="7d457-176">By default, Windows firewall blocks Virtual PC2007 SP1 network activity, and when Virtual PC2007 SP1 initiates on the client computer, there is a firewall message that blocks its startup sequence and all network access.</span></span>

### <span data-ttu-id="7d457-177">解决方案</span><span class="sxs-lookup"><span data-stu-id="7d457-177">Solution</span></span>

<span data-ttu-id="7d457-178">在由最终用户使用 MED-V 之前使用组策略更新防火墙例外。</span><span class="sxs-lookup"><span data-stu-id="7d457-178">Update the firewall exception by using Group Policy before MED-V is used by the end user.</span></span>

## <span data-ttu-id="7d457-179">升级客户端时会出现一条错误消息</span><span class="sxs-lookup"><span data-stu-id="7d457-179">When upgrading the client an error message appears</span></span>


<span data-ttu-id="7d457-180">将客户端从 MED-V 1.0 升级到 MED-V 1.0 SP1 时，可能会显示一条消息，通知您未定义任何 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="7d457-180">When upgrading the client from MED-V1.0 to MED-V1.0 SP1, a message may appear notifying you that no MED-V workspace is defined.</span></span>

### <span data-ttu-id="7d457-181">解决方案</span><span class="sxs-lookup"><span data-stu-id="7d457-181">Solution</span></span>

<span data-ttu-id="7d457-182">关闭客户端，然后重新启动它。</span><span class="sxs-lookup"><span data-stu-id="7d457-182">Close the client and restart it.</span></span>

## <span data-ttu-id="7d457-183">相关主题</span><span class="sxs-lookup"><span data-stu-id="7d457-183">Related topics</span></span>


[<span data-ttu-id="7d457-184">MED-V 1.0 发行说明</span><span class="sxs-lookup"><span data-stu-id="7d457-184">MED-V 1.0 Release Notes</span></span>](med-v-10-release-notesmedv-10.md)

[<span data-ttu-id="7d457-185">MED-V 1.0 SP1 和 SP2 发行说明</span><span class="sxs-lookup"><span data-stu-id="7d457-185">MED-V 1.0 SP1 and SP2 Release Notes</span></span>](med-v-10-sp1-and-sp2-release-notesmedv-10-sp1.md)

 

 





