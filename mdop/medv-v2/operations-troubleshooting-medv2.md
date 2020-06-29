---
title: 操作疑难解答
description: 操作疑难解答
author: dansimp
ms.assetid: 948d7869-accd-44da-974f-93409234dee7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 126b5fae517c59914dcb7fb155ef4ad47278b5bd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798121"
---
# <span data-ttu-id="17775-103">操作疑难解答</span><span class="sxs-lookup"><span data-stu-id="17775-103">Operations Troubleshooting</span></span>


<span data-ttu-id="17775-104">本主题包含可用于帮助解决 Microsoft 企业桌面虚拟化（MED-V）2.0 中的常规操作问题的信息。</span><span class="sxs-lookup"><span data-stu-id="17775-104">This topic includes information that you can use to help troubleshoot general operational issues in Microsoft Enterprise Desktop Virtualization (MED-V) 2.0.</span></span>

## <span data-ttu-id="17775-105">对 MED-V 操作中的问题进行故障排除</span><span class="sxs-lookup"><span data-stu-id="17775-105">Troubleshooting Issues in MED-V Operations</span></span>


<span data-ttu-id="17775-106">当最终用户运行 MED-V 和解决方案来帮助解决这些问题时，可能会遇到以下问题：</span><span class="sxs-lookup"><span data-stu-id="17775-106">The following are some issues end users might encounter when they run MED-V and solutions to help troubleshoot these issues:</span></span>

<span data-ttu-id="17775-107">**文档重定向失败**。</span><span class="sxs-lookup"><span data-stu-id="17775-107">**Documentation Redirection Fails**.</span></span> <span data-ttu-id="17775-108">当最终用户的 "我的文档" 文件夹指向网络位置时，通常会出现此问题。</span><span class="sxs-lookup"><span data-stu-id="17775-108">This issue typically occurs when an end user’s My Documents folder points to a network location.</span></span> <span data-ttu-id="17775-109">Windows 不支持从另一个共享文件夹创建共享。</span><span class="sxs-lookup"><span data-stu-id="17775-109">Windows does not support creating a share from another shared folder.</span></span> <span data-ttu-id="17775-110">当驱动器或文件夹被重定向到来宾时，RDP\\Windows Virtual PC 将为该文件夹创建一个共享。</span><span class="sxs-lookup"><span data-stu-id="17775-110">When a drive or folder is redirected to the guest, RDP\\Windows Virtual PC creates a share for that folder.</span></span> <span data-ttu-id="17775-111">因此，如果主机上的 "我的文档" 文件夹已指向共享，RDP\\Windows Virtual PC 无法创建共享共享。</span><span class="sxs-lookup"><span data-stu-id="17775-111">Therefore, if the My Documents folder on the host is already pointing to a share, RDP\\Windows Virtual PC cannot create a share of a share.</span></span>

<span data-ttu-id="17775-112">导致此问题的另一个可能原因是连接到网络资源所需的凭据可能与用户的域凭据不同。</span><span class="sxs-lookup"><span data-stu-id="17775-112">Another possible cause of this issue is that the credentials that are required to connect to the network resource might differ from the user’s domain credentials.</span></span> <span data-ttu-id="17775-113">MED-V 可能检测到在主机上已重定向文档、将该信息发送给来宾，然后尝试重新连接网络资源。</span><span class="sxs-lookup"><span data-stu-id="17775-113">MED-V might be detecting that documents are redirected on the host, send that information to the guest, and then try to reconnect the network resource.</span></span> <span data-ttu-id="17775-114">如果用户的凭据不进行身份验证，则 MED-V 可能会停止尝试进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="17775-114">If the user’s credentials do not authenticate, MED-V might stop trying to authenticate.</span></span>

**<span data-ttu-id="17775-115">解决方案</span><span class="sxs-lookup"><span data-stu-id="17775-115">Solution</span></span>**

<span data-ttu-id="17775-116">若要解决此问题，请尝试以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="17775-116">Try one of the following to resolve this issue:</span></span>

-   <span data-ttu-id="17775-117">在 Active Directory 内设置用户的 root 目录。</span><span class="sxs-lookup"><span data-stu-id="17775-117">Set the user’s root directory inside Active Directory.</span></span> <span data-ttu-id="17775-118">然后，来宾和主机将连接到同一网络资源。</span><span class="sxs-lookup"><span data-stu-id="17775-118">The guest and host should then connect to the same network resource.</span></span>

-   <span data-ttu-id="17775-119">不要将 "我的文档" 文件夹重定向到 UNC 路径，而是将其映射到驱动器号（在主机上，映射指向网络资源的驱动器）。</span><span class="sxs-lookup"><span data-stu-id="17775-119">Instead of redirecting the My Documents folder to a UNC path, map it to a drive letter (on the host, map a drive that points to the network resource).</span></span> <span data-ttu-id="17775-120">然后，可以将 "我的文档" 文件夹设置为使用驱动器号，而不是 UNC 路径。</span><span class="sxs-lookup"><span data-stu-id="17775-120">The My Documents folder can then be set to use the drive letter instead of the UNC path.</span></span> <span data-ttu-id="17775-121">然后，来宾将重定向到所需的同一映射驱动器。</span><span class="sxs-lookup"><span data-stu-id="17775-121">The guest will then redirect to that same mapped drive as expected.</span></span>

-   <span data-ttu-id="17775-122">在来宾中创建一个启动脚本，该脚本可将 "我的文档" 文件夹重定向到网络资源，并根据需要提供其他凭据。</span><span class="sxs-lookup"><span data-stu-id="17775-122">Create a startup script in the guest that redirects the My Documents folder to the network resource and provides additional credentials as needed.</span></span>

<span data-ttu-id="17775-123">**URL 重定向失败**。</span><span class="sxs-lookup"><span data-stu-id="17775-123">**URL Redirection Fails**.</span></span> <span data-ttu-id="17775-124">你为从主机重定向到来宾而指定的 URL 未按预期重定向或返回一条错误消息，指示网站不存在。</span><span class="sxs-lookup"><span data-stu-id="17775-124">A URL that you have specified for redirection from the host to the guest is not redirecting as intended or is returning an error message that indicates that the website does not exist.</span></span>

**<span data-ttu-id="17775-125">解决方案</span><span class="sxs-lookup"><span data-stu-id="17775-125">Solution</span></span>**

<span data-ttu-id="17775-126">如果在 URL 重定向信息中有拼写错误或错误地使用了星号（\ \*）等字符，则可能会发生此错误。</span><span class="sxs-lookup"><span data-stu-id="17775-126">This error can occur when there is a misspelling or incorrect use of characters, such as asterisk (\*), in the URL redirection information.</span></span> <span data-ttu-id="17775-127">检查 URL 重定向的注册表值并更正任何错误。</span><span class="sxs-lookup"><span data-stu-id="17775-127">Check the registry value for URL redirection and correct any mistakes.</span></span>

<span data-ttu-id="17775-128">注册表项的调用 `RedirectUrls` 通常位于以下位置：</span><span class="sxs-lookup"><span data-stu-id="17775-128">The registry key is called `RedirectUrls` and is typically located at:</span></span>

<span data-ttu-id="17775-129">Computer\\HKEY\ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\MEDV\\v2\\UserExperience</span><span class="sxs-lookup"><span data-stu-id="17775-129">Computer\\HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\MEDV\\v2\\UserExperience</span></span>

<span data-ttu-id="17775-130">**任务栏中的图标令人误解**。</span><span class="sxs-lookup"><span data-stu-id="17775-130">**Icon in Taskbar Misleading**.</span></span> <span data-ttu-id="17775-131">默认情况下，在最终用户的任务栏中显示已发布的应用程序和重定向的 Url 的图标是 Windows 虚拟 PC 的图标。</span><span class="sxs-lookup"><span data-stu-id="17775-131">By default, the icon that appears in an end user’s taskbar for published applications and redirected URLs is the icon for Windows Virtual PC.</span></span> <span data-ttu-id="17775-132">如果最终用户不知道此默认行为，则在查看任务栏找到其应用程序时，它们可能会变得混乱。</span><span class="sxs-lookup"><span data-stu-id="17775-132">If an end user is not aware of this default behavior, they can become confused when looking at the taskbar to locate their application.</span></span>

**<span data-ttu-id="17775-133">解决方案</span><span class="sxs-lookup"><span data-stu-id="17775-133">Solution</span></span>**

<span data-ttu-id="17775-134">避免此默认行为的唯一方法是更改任务栏属性的用户设置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="17775-134">The only way to avoid this default behavior is to change the user settings for the taskbar properties as follows:</span></span>

1.  <span data-ttu-id="17775-135">右键单击任务栏，然后单击 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="17775-135">Right-click the taskbar and then click **Properties**.</span></span>

2.  <span data-ttu-id="17775-136">在**任务栏和 "开始菜单属性**" 对话框中，单击 "**任务栏**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="17775-136">In the **Taskbar and Start Menu Properties** dialog box, click the **Taskbar** tab.</span></span>

3.  <span data-ttu-id="17775-137">在 "**任务栏按钮**" 框的下拉栏中，选择 "**从不合并**"。</span><span class="sxs-lookup"><span data-stu-id="17775-137">In the drop-down bar for the **Taskbar buttons** box, select **Never combine**.</span></span>

4.  <span data-ttu-id="17775-138">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="17775-138">Click **OK**.</span></span>

<span data-ttu-id="17775-139">将显示已发布应用程序和重定向 Url 的预期图标。</span><span class="sxs-lookup"><span data-stu-id="17775-139">The expected icons for published applications and redirected URLs are displayed.</span></span>

<span data-ttu-id="17775-140">**如果第二次用户尝试登录或虚拟机正在使用，则发出警告**。</span><span class="sxs-lookup"><span data-stu-id="17775-140">**Warning Issued if Second User Attempts Log on or if Virtual Machine is in Use**.</span></span> <span data-ttu-id="17775-141">当第一个用户仍在运行 MED-V 时，当第二个用户登录到 MED-V 工作区时，将发出一条警告消息。</span><span class="sxs-lookup"><span data-stu-id="17775-141">A warning message is issued when a second user logs on to a MED-V workspace while a first user is still running MED-V.</span></span> <span data-ttu-id="17775-142">如果在使用虚拟机时启动 MED-V （例如，如果虚拟机通过 "**开始**" 菜单上的 WINDOWS virtual PC 启动），也会发出此警告。</span><span class="sxs-lookup"><span data-stu-id="17775-142">The warning is also issued if MED-V is started while the virtual machine is being used, for example, if the virtual machine was started through Windows Virtual PC on the **Start** menu.</span></span> <span data-ttu-id="17775-143">当最终用户接受警告消息时，MED-V 会关闭。</span><span class="sxs-lookup"><span data-stu-id="17775-143">When the end user accepts the warning message, MED-V shuts down.</span></span>

**<span data-ttu-id="17775-144">解决方案</span><span class="sxs-lookup"><span data-stu-id="17775-144">Solution</span></span>**

<span data-ttu-id="17775-145">最终用户必须先验证所有其他用户是否已注销 MED-V，然后再尝试登录。</span><span class="sxs-lookup"><span data-stu-id="17775-145">An end user must verify that all other users are logged off MED-V before they try to log on.</span></span> <span data-ttu-id="17775-146">这可确保不会运行 MED-V 的任何其他实例，并且 Windows 虚拟 PC 不受虚拟机的控制。</span><span class="sxs-lookup"><span data-stu-id="17775-146">This ensures that no other instance of MED-V is running and that Windows Virtual PC is not in control of the virtual machine.</span></span>

<span data-ttu-id="17775-147">**首次设置时听到声响**。</span><span class="sxs-lookup"><span data-stu-id="17775-147">**Beeps Heard During First Time Setup**.</span></span> <span data-ttu-id="17775-148">在某些情况下，系统会在安装时首次运行时听到嘟嘟声。</span><span class="sxs-lookup"><span data-stu-id="17775-148">Occasionally, beeps are heard while MED-V is running first time setup.</span></span> <span data-ttu-id="17775-149">这可能会使最终用户感到困惑。</span><span class="sxs-lookup"><span data-stu-id="17775-149">This can be confusing to an end user.</span></span> <span data-ttu-id="17775-150">在执行某些操作（如关闭）时，嘟嘟声来自虚拟机。</span><span class="sxs-lookup"><span data-stu-id="17775-150">The beeps are originating from the virtual machine when it performs certain actions, such as shutting down.</span></span>

**<span data-ttu-id="17775-151">解决方案</span><span class="sxs-lookup"><span data-stu-id="17775-151">Solution</span></span>**

<span data-ttu-id="17775-152">你可以通过在每个虚拟机启动序列的开头指定 "net stop 嘟嘟声" 命令来停止声响服务。</span><span class="sxs-lookup"><span data-stu-id="17775-152">You can stop the beep service by specifying the "net stop beep" command at the beginning of each virtual machine start sequence.</span></span> <span data-ttu-id="17775-153">或者，您可以通过指定 "sc config 提示开始 = 禁用" 命令禁用声响服务。</span><span class="sxs-lookup"><span data-stu-id="17775-153">Or you can disable the beep service by specifying the “sc config beep start= disabled" command.</span></span> <span data-ttu-id="17775-154">在密封图像之前或作为 Sysprep 的一部分，您可以指定这些命令。</span><span class="sxs-lookup"><span data-stu-id="17775-154">You can specify these commands either before you seal the image or as part of Sysprep.</span></span>

<span data-ttu-id="17775-155">**在桥接模式下为 Med-v 工作区创建的多个网络连接**。</span><span class="sxs-lookup"><span data-stu-id="17775-155">**Multiple Network Connections Created for MED-V Workspaces in BRIDGED Mode**.</span></span> <span data-ttu-id="17775-156">如果首次设置创建的 MED-V 工作区是为 NAT 模式配置的，它仅在 Windows 虚拟 PC 中创建单个网络连接。</span><span class="sxs-lookup"><span data-stu-id="17775-156">If first time setup is creating a MED-V workspace that is configured for NAT mode, it only creates a single network connection in Windows Virtual PC.</span></span> <span data-ttu-id="17775-157">但是，如果首次设置创建的 MED-V 工作区是为桥接模式配置的，则它将为计算机上安装的每个网络适配器创建单独的网络连接，因为 MED-V 无法确定哪个网络适配器处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="17775-157">However, if first time setup is creating a MED-V workspace that is configured for BRIDGED mode, it creates a separate network connection for each network adapter that is installed in the computer, because MED-V cannot determine which network adapter is active.</span></span> <span data-ttu-id="17775-158">这还可确保漫游用户始终具有可用于有线和无线连接的网络适配器。</span><span class="sxs-lookup"><span data-stu-id="17775-158">This also ensures that roaming users always have a network adapter available for wired and wireless connections.</span></span>

**<span data-ttu-id="17775-159">解决方案</span><span class="sxs-lookup"><span data-stu-id="17775-159">Solution</span></span>**

<span data-ttu-id="17775-160">无。</span><span class="sxs-lookup"><span data-stu-id="17775-160">None.</span></span>

<span data-ttu-id="17775-161">**在关闭时，Med-v 应用程序的响应时间太长**。</span><span class="sxs-lookup"><span data-stu-id="17775-161">**MED-V Application is Unresponsive for Too Long when Closing**.</span></span> <span data-ttu-id="17775-162">在某些情况下，MED-V 应用程序在尝试关闭时停止响应。</span><span class="sxs-lookup"><span data-stu-id="17775-162">In some instances, a MED-V application stops responding when it is trying to close.</span></span>

**<span data-ttu-id="17775-163">解决方案</span><span class="sxs-lookup"><span data-stu-id="17775-163">Solution</span></span>**

<span data-ttu-id="17775-164">你可以通过在来宾虚拟机中设置 WaitToKillAppTimeout 注册表项来指定 MED-V 等待关闭未响应的应用程序的时间长度。</span><span class="sxs-lookup"><span data-stu-id="17775-164">You can specify the length of time that MED-V waits to close unresponsive applications by setting the WaitToKillAppTimeout registry key in the guest virtual machine.</span></span> <span data-ttu-id="17775-165">有关详细信息，请参阅[如何延长关闭时间，以便进程可以在 WINDOWS XP 中正常退出](https://go.microsoft.com/fwlink/?LinkId=206819)（ https://go.microsoft.com/fwlink/?LinkId=206819) 。</span><span class="sxs-lookup"><span data-stu-id="17775-165">For more information, see [How To Increase Shutdown Time So That Processes Can Quit Properly in Windows XP](https://go.microsoft.com/fwlink/?LinkId=206819) (https://go.microsoft.com/fwlink/?LinkId=206819).</span></span>

<span data-ttu-id="17775-166">**在来宾虚拟机中重命名已发布的应用程序快捷方式不会更改主机中已发布的名称**。</span><span class="sxs-lookup"><span data-stu-id="17775-166">**Renaming a Published Application Shortcut in the Guest Virtual Machine does not Change the Published Name in the Host**.</span></span> <span data-ttu-id="17775-167">通过创建快捷方式并在来宾虚拟机中重命名快捷方式来发布应用程序时，原始应用程序名称将保留在主机 "**开始**" 菜单中。</span><span class="sxs-lookup"><span data-stu-id="17775-167">When you publish an application by creating a shortcut and then rename the shortcut in the guest virtual machine, the original application name remains in the host **Start** menu.</span></span> <span data-ttu-id="17775-168">程序将继续按预期运行，但程序将始终保留原始名称。</span><span class="sxs-lookup"><span data-stu-id="17775-168">The program continues to run as expected, however the program will always retain the original name.</span></span>

**<span data-ttu-id="17775-169">解决方案</span><span class="sxs-lookup"><span data-stu-id="17775-169">Solution</span></span>**

<span data-ttu-id="17775-170">无。</span><span class="sxs-lookup"><span data-stu-id="17775-170">None.</span></span> <span data-ttu-id="17775-171">这是 Windows 虚拟电脑的已知行为。</span><span class="sxs-lookup"><span data-stu-id="17775-171">This is a known behavior of Windows Virtual PC.</span></span>

<span data-ttu-id="17775-172">**在来宾虚拟机中移动快捷方式不会更新主机计算机 "开始" 菜单上的位置**。</span><span class="sxs-lookup"><span data-stu-id="17775-172">**Moving a Shortcut in the Guest Virtual Machine does not Update the Location on the Host Computer Start Menu**.</span></span> <span data-ttu-id="17775-173">发布到主计算机 "**开始**" 菜单的 "med-v" 应用程序快捷方式在注册表中被编录。</span><span class="sxs-lookup"><span data-stu-id="17775-173">MED-V application shortcuts that are published to the host computer **Start** menu are cataloged in the registry.</span></span> <span data-ttu-id="17775-174">如果将应用程序快捷方式移动到子文件夹中，则不会更新注册表以反映所做的更改。</span><span class="sxs-lookup"><span data-stu-id="17775-174">If you move an application shortcut into a subfolder, the registry is not updated to reflect the change.</span></span>

**<span data-ttu-id="17775-175">解决方案</span><span class="sxs-lookup"><span data-stu-id="17775-175">Solution</span></span>**

<span data-ttu-id="17775-176">请按照以下步骤更改 MED-V 应用程序快捷方式的位置：</span><span class="sxs-lookup"><span data-stu-id="17775-176">Follow these steps to change the location of a MED-V application shortcut:</span></span>

1.  <span data-ttu-id="17775-177">当 MED-V 正在运行时，请在 MED-V 来宾虚拟机上打开 Windows 资源管理器。</span><span class="sxs-lookup"><span data-stu-id="17775-177">When MED-V is running, open up Windows Explorer on the MED-V guest virtual machine.</span></span>

2.  <span data-ttu-id="17775-178">浏览到 "%ALLUSERSPROFILE%\\Start Menu\\Programs" 目录。</span><span class="sxs-lookup"><span data-stu-id="17775-178">Browse to the "%ALLUSERSPROFILE%\\Start Menu\\Programs" directory.</span></span>

3.  <span data-ttu-id="17775-179">将应用程序快捷方式移出 "startmenu" 或 "程序" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="17775-179">Move the application shortcuts out of the startmenu or programs folders.</span></span>

4.  <span data-ttu-id="17775-180">大约30秒后，验证是否已从主机 "**开始**" 菜单中删除快捷方式。</span><span class="sxs-lookup"><span data-stu-id="17775-180">After about 30 seconds, validate that the shortcuts are removed from the host computer **Start** menu.</span></span>

5.  <span data-ttu-id="17775-181">将应用程序快捷方式移回 "开始 Menu\\Programs" 目录下的新程序文件夹。</span><span class="sxs-lookup"><span data-stu-id="17775-181">Move the application shortcuts back in to the new program folders under the Start Menu\\Programs directory.</span></span>

6.  <span data-ttu-id="17775-182">大约30秒后，验证在主机 "**开始**" 菜单中是否更新了快捷方式。</span><span class="sxs-lookup"><span data-stu-id="17775-182">After about 30 seconds, validate that the shortcuts are updated in the host computer **Start** Menu.</span></span>

<span data-ttu-id="17775-183">**已发布的应用程序在处于空闲状态后可能会超时**。</span><span class="sxs-lookup"><span data-stu-id="17775-183">**Published Applications can Time Out after Sitting Idle**.</span></span> <span data-ttu-id="17775-184">在某些情况下，如果已发布的应用程序有一段时间空闲，他们将会超时。</span><span class="sxs-lookup"><span data-stu-id="17775-184">In some cases, published applications will time out if they have sat idle for some time.</span></span> <span data-ttu-id="17775-185">只有在启用了 IPsec 且为 NAT 模式配置了 MED-V 工作区时，才会出现此情况。</span><span class="sxs-lookup"><span data-stu-id="17775-185">This situation only occurs if IPsec is enabled and the MED-V workspace is configured for NAT mode.</span></span> <span data-ttu-id="17775-186">如果在桥接模式下运行，则不会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="17775-186">This situation does not occur if running in BRIDGED mode.</span></span>

**<span data-ttu-id="17775-187">解决方案</span><span class="sxs-lookup"><span data-stu-id="17775-187">Solution</span></span>**

<span data-ttu-id="17775-188">在 NAT 模式下运行 MED-V 工作区时，禁用 IPsec。</span><span class="sxs-lookup"><span data-stu-id="17775-188">Disable IPsec when you are running the MED-V workspace in NAT mode.</span></span>

<span data-ttu-id="17775-189">**将已发布的应用程序固定到任务栏将绕过 med-v**。</span><span class="sxs-lookup"><span data-stu-id="17775-189">**Pinning a Published Application to the Taskbar Bypasses MED-V**.</span></span> <span data-ttu-id="17775-190">如果最终用户将已发布的应用程序固定到任务栏，然后关闭该应用程序，则下次从任务栏图标中打开该应用程序时，将跳过 MED-V。</span><span class="sxs-lookup"><span data-stu-id="17775-190">If an end user pins a published application to the taskbar and then closes the application, MED-V is bypassed the next time that the application is opened from the taskbar icon.</span></span> <span data-ttu-id="17775-191">而是直接在 VMSAL 窗口中打开应用程序。</span><span class="sxs-lookup"><span data-stu-id="17775-191">Instead, the application opens directly in a VMSAL window.</span></span>

**<span data-ttu-id="17775-192">解决方案</span><span class="sxs-lookup"><span data-stu-id="17775-192">Solution</span></span>**

<span data-ttu-id="17775-193">不要将 MED-V 中发布的应用程序固定到任务栏。</span><span class="sxs-lookup"><span data-stu-id="17775-193">Do not pin the applications published in MED-V to the taskbar.</span></span>

## <span data-ttu-id="17775-194">相关主题</span><span class="sxs-lookup"><span data-stu-id="17775-194">Related topics</span></span>


[<span data-ttu-id="17775-195">MED-V 操作的安全最佳方案</span><span class="sxs-lookup"><span data-stu-id="17775-195">Security Best Practices for MED-V Operations</span></span>](security-best-practices-for-med-v-operations.md)

[<span data-ttu-id="17775-196">部署疑难解答</span><span class="sxs-lookup"><span data-stu-id="17775-196">Deployment Troubleshooting</span></span>](deployment-troubleshooting.md)

 

 





