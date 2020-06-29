---
title: 管理 MED-V 工作区的自动更新
description: 管理 MED-V 工作区的自动更新
author: dansimp
ms.assetid: 306f28a2-d653-480d-b737-4b8b3132de5d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: b22d3250db806e740c1d62da4fed98d5956b0eeb
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803739"
---
# <span data-ttu-id="4ec67-103">管理 MED-V 工作区的自动更新</span><span class="sxs-lookup"><span data-stu-id="4ec67-103">Managing Automatic Updates for MED-V Workspaces</span></span>


<span data-ttu-id="4ec67-104">MED-V 工作区是一个虚拟机，它包含一个单独的操作系统，其自动软件更新过程必须像企业中的物理计算机一样进行管理。</span><span class="sxs-lookup"><span data-stu-id="4ec67-104">The MED-V workspace is a virtual machine that contains a separate operating system, whose automatic software update process must be managed just like the physical computers in your enterprise.</span></span> <span data-ttu-id="4ec67-105">由于来宾操作系统在主机操作系统运行时不一定始终运行，因此你必须确保以某种方式配置 MED-V 虚拟机，以便根据需要将软件更新应用到来宾操作系统。</span><span class="sxs-lookup"><span data-stu-id="4ec67-105">Because the guest operating system is not always necessarily running when the host operating system is running, you must ensure that the MED-V virtual machine is configured in such a way that software updates can be applied to the guest operating system as required.</span></span> <span data-ttu-id="4ec67-106">Microsoft 企业版桌面虚拟化（MED-V）2.0 解决方案提供的功能可让你确定如何在 MED-V 工作区中处理自动软件更新。</span><span class="sxs-lookup"><span data-stu-id="4ec67-106">The Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 solution provides the functionality that lets you determine how automatic software updates are processed in a MED-V workspace.</span></span>

## <span data-ttu-id="4ec67-107">管理 MED-V 工作区唤醒策略</span><span class="sxs-lookup"><span data-stu-id="4ec67-107">Managing MED-V Workspace Wake-Up Policy</span></span>


<span data-ttu-id="4ec67-108">MED-V 工作区唤醒策略可确保 MED-V 虚拟机在你在 MED-V 配置设置中指定的时间内可用于更新。</span><span class="sxs-lookup"><span data-stu-id="4ec67-108">The MED-V workspace wake-up policy guarantees that the MED-V virtual machine is made available for updates for the time that you specify in your MED-V configuration settings.</span></span> <span data-ttu-id="4ec67-109">这适用于从 Microsoft 发布的更新，这些更新是通过 Windows 更新和非 Microsoft 解决方案（如防病毒应用程序）部署和控制的更新。</span><span class="sxs-lookup"><span data-stu-id="4ec67-109">This applies to both updates that are published from Microsoft through Windows Update and updates deployed and controlled by non-Microsoft solutions, such as antivirus applications.</span></span>

<span data-ttu-id="4ec67-110">**重要提示** MED-V 工作区唤醒策略已针对 Microsoft Update 基础结构进行了优化。</span><span class="sxs-lookup"><span data-stu-id="4ec67-110">**Important** The MED-V workspace wake-up policy is optimized for the Microsoft Update infrastructure.</span></span> <span data-ttu-id="4ec67-111">如果你使用 Microsoft System Center Configuration Manager 部署非 Microsoft 更新，我们建议你还使用 System Center Updates Publisher，它利用与 Microsoft 更新相同的基础结构，因此可以从 MED-V 工作区唤醒策略中受益。</span><span class="sxs-lookup"><span data-stu-id="4ec67-111">If you are using Microsoft System Center Configuration Manager to deploy non-Microsoft updates, we recommend that you also use the System Center Updates Publisher, which takes advantage of the same infrastructure as Microsoft Update and therefore benefits from the MED-V workspace wake-up policy.</span></span> <span data-ttu-id="4ec67-112">有关详细信息，请参阅[System Center Update Publisher](https://go.microsoft.com/fwlink/?LinkId=200035) （ https://go.microsoft.com/fwlink/?LinkId=200035) 。</span><span class="sxs-lookup"><span data-stu-id="4ec67-112">For more information, see [System Center Updates Publisher](https://go.microsoft.com/fwlink/?LinkId=200035) (https://go.microsoft.com/fwlink/?LinkId=200035).</span></span>

 

<span data-ttu-id="4ec67-113">当你创建 MED-V 工作区程序包时，在最终用户登录（**快速启动**）或最终用户首次打开已发布的应用程序（**正常启动**）时，你将配置该程序包的启动和操作方式。</span><span class="sxs-lookup"><span data-stu-id="4ec67-113">When you created your MED-V workspace package, you configured when and how it starts, either when the end user logs on (**Fast Start**) or when the end user first opens a published application (**Normal Start**).</span></span> <span data-ttu-id="4ec67-114">或者，设置该选项以允许最终用户控制此设置。</span><span class="sxs-lookup"><span data-stu-id="4ec67-114">Or you set the option to let the end user control this setting.</span></span>

<span data-ttu-id="4ec67-115">无论是哪一种情况，只要选择了 "**快速启动**" 选项，只要 med-v 主机作为用户登录，虚拟机就会继续运行。</span><span class="sxs-lookup"><span data-stu-id="4ec67-115">Either way, whenever the **Fast Start** option is selected, the virtual machine continues to run as long as the MED-V host is logged on as User.</span></span> <span data-ttu-id="4ec67-116">在此配置中，因为当主机处于活动状态时，MED-V 处于活动状态，因此无需从 MED-V 中进行任何额外处理即可应用自动更新。</span><span class="sxs-lookup"><span data-stu-id="4ec67-116">In this configuration, because MED-V is active when the host is active, automatic updates are applied without requiring any extra processing from MED-V.</span></span>

<span data-ttu-id="4ec67-117">但是，对于未指定 "**快速启动**" 或虚拟机处于休眠或停止状态的情况，med-v 通过其 med-v 工作区唤醒策略（即使不定期使用 med-v）来确保来宾操作系统定期更新。</span><span class="sxs-lookup"><span data-stu-id="4ec67-117">However, for those cases in which **Fast Start** is not specified or the virtual machine hibernates or stops, MED-V guarantees through its MED-V workspace wake-up policy that the guest operating system is being regularly updated even when MED-V is not used regularly.</span></span> <span data-ttu-id="4ec67-118">MED-V 通过基于你指定的配置设置定期唤醒虚拟机来执行此函数。</span><span class="sxs-lookup"><span data-stu-id="4ec67-118">MED-V performs this function by regularly waking up the virtual machine based on the configuration settings that you specify.</span></span> <span data-ttu-id="4ec67-119">这使虚拟机中的自动更新客户端能够根据其配置执行。</span><span class="sxs-lookup"><span data-stu-id="4ec67-119">This enables the automatic update clients in the virtual machine to execute based on their configurations.</span></span><span data-ttu-id="4ec67-120">在 MED-V 配置设置定义的时间段过后，MED-V 会将虚拟机恢复到其以前的状态。</span><span class="sxs-lookup"><span data-stu-id="4ec67-120">After the time period defined by the MED-V configuration setting elapses, MED-V returns the virtual machine to its previous state.</span></span>

<span data-ttu-id="4ec67-121">**注意** 如果最终用户在更新期间打开已发布的应用程序，则会应用所需的更新，但在更新期结束后，MED-V 不会自动休眠或关闭。</span><span class="sxs-lookup"><span data-stu-id="4ec67-121">**Note** If the end user opens a published application during the update period, the required updates are applied, but MED-V is not automatically hibernated or shut down after the update period ends.</span></span> <span data-ttu-id="4ec67-122">而 MED-V 将继续运行。</span><span class="sxs-lookup"><span data-stu-id="4ec67-122">Instead, MED-V continues running.</span></span>

 

<span data-ttu-id="4ec67-123">MED-V 工作区唤醒策略包括三个主要组件：</span><span class="sxs-lookup"><span data-stu-id="4ec67-123">The MED-V workspace wake-up policy includes three main components:</span></span>

**<span data-ttu-id="4ec67-124">来宾更新管理器</span><span class="sxs-lookup"><span data-stu-id="4ec67-124">Guest Update Manager</span></span>**

<span data-ttu-id="4ec67-125">此独立的可执行程序驻留在 MED-V 主机上，负责根据预定义的可配置计划来唤醒虚拟机。</span><span class="sxs-lookup"><span data-stu-id="4ec67-125">Residing on the MED-V host, this stand-alone executable program is responsible for waking up the virtual machine according to a predefined, configurable schedule.</span></span> <span data-ttu-id="4ec67-126">指定配置设置以指示更新管理器每日唤醒虚拟机的时间，以及虚拟机应保持唤醒状态的时间（以分钟为单位）以允许应用更新。</span><span class="sxs-lookup"><span data-stu-id="4ec67-126">Specify the configuration settings to indicate at what time the update manager should wake up the virtual machine every day, and how long the virtual machine should be kept awake (in minutes) to allow for updates to be applied.</span></span> <span data-ttu-id="4ec67-127">指定的分钟数达到指定的分钟数后，来宾更新管理器会将虚拟机置于休眠状态，为下一次使用做好准备。</span><span class="sxs-lookup"><span data-stu-id="4ec67-127">After the number of minutes specified has been reached, the guest update manager puts the virtual machine into hibernation, prepared for the next use.</span></span> <span data-ttu-id="4ec67-128">你可以通过 Windows 任务管理器安排此可执行程序的执行。</span><span class="sxs-lookup"><span data-stu-id="4ec67-128">You can schedule the execution of this executable program through the Windows Task Manager.</span></span>

**<span data-ttu-id="4ec67-129">来宾重启管理服务</span><span class="sxs-lookup"><span data-stu-id="4ec67-129">Guest Restart Management Service</span></span>**

<span data-ttu-id="4ec67-130">驻留在 MED-V 主机上，此服务有三个主要职责。</span><span class="sxs-lookup"><span data-stu-id="4ec67-130">Residing on the MED-V host, this service has three primary responsibilities.</span></span> <span data-ttu-id="4ec67-131">与来宾更新管理器一起，它会在用户登录时管理虚拟机的重启（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="4ec67-131">Along with the Guest Update Manager, it manages the restart of the virtual machine at user logon, if it is required.</span></span> <span data-ttu-id="4ec67-132">它会检测到需要重新启动虚拟机的情况，因为安装了更新。</span><span class="sxs-lookup"><span data-stu-id="4ec67-132">It detects when virtual machine restarts are required caused by updates being installed.</span></span> <span data-ttu-id="4ec67-133">并且确保始终按照配置对来宾更新管理器的任务进行计划。</span><span class="sxs-lookup"><span data-stu-id="4ec67-133">And it ensures that the task for the Guest Update Manager is always scheduled according to configuration.</span></span>

**<span data-ttu-id="4ec67-134">来宾更新服务</span><span class="sxs-lookup"><span data-stu-id="4ec67-134">Guest Update Service</span></span>**

<span data-ttu-id="4ec67-135">在 MED-V 虚拟机上，此 Windows 服务负责在安装更新需要重启时进行监视。</span><span class="sxs-lookup"><span data-stu-id="4ec67-135">Residing on the MED-V virtual machine, this Windows service has the responsibility of monitoring when installed updates require a restart.</span></span> <span data-ttu-id="4ec67-136">在服务意识到需要重启后，它会在主机上通知来宾重启管理服务。</span><span class="sxs-lookup"><span data-stu-id="4ec67-136">After the service becomes aware of the need for a restart, it notifies the guest restart management service on the host.</span></span>

### <span data-ttu-id="4ec67-137">MED-V 工作区唤醒策略的配置设置</span><span class="sxs-lookup"><span data-stu-id="4ec67-137">Configuration Settings for MED-V Workspace Wake-Up Policy</span></span>

<span data-ttu-id="4ec67-138">你可以通过在注册表中定义以下两个配置值来控制虚拟机 awakens 接收自动更新的时间和时间。</span><span class="sxs-lookup"><span data-stu-id="4ec67-138">You control when and for how long the virtual machine awakens to receive automatic updates by defining the following two configuration values in the registry.</span></span> <span data-ttu-id="4ec67-139">这两个值均位于 HKLM\\Software\\Microsoft\\MEDV\\v2\\VM 键下。</span><span class="sxs-lookup"><span data-stu-id="4ec67-139">Both of these values are located under the HKLM\\Software\\Microsoft\\MEDV\\v2\\VM key.</span></span>

<span data-ttu-id="4ec67-140">**GuestUpdateTime** -如果 med-v 必须根据24小时制时钟标准唤醒更新虚拟机，则每天配置小时和分钟数。</span><span class="sxs-lookup"><span data-stu-id="4ec67-140">**GuestUpdateTime** – Configures the hour and minute each day when MED-V must wake up the virtual machine for updating, based on the 24-hour clock standard.</span></span> <span data-ttu-id="4ec67-141">以 HH： MM 的格式指定时间。</span><span class="sxs-lookup"><span data-stu-id="4ec67-141">Specify the time in the format HH:MM.</span></span> <span data-ttu-id="4ec67-142">默认值为00:00 （午夜）。</span><span class="sxs-lookup"><span data-stu-id="4ec67-142">The default value is 00:00 (midnight).</span></span>

<span data-ttu-id="4ec67-143">**GuestUpdateDuration** -配置在 GuestUpdateTime 配置设置中指定的时间开始，med-v 必须保持虚拟机唤醒以进行更新的分钟数。</span><span class="sxs-lookup"><span data-stu-id="4ec67-143">**GuestUpdateDuration** – Configures the number of minutes that MED-V must keep the virtual machine awake for updating, starting at the time specified in the GuestUpdateTime configuration setting.</span></span> <span data-ttu-id="4ec67-144">默认值为240（4小时）。</span><span class="sxs-lookup"><span data-stu-id="4ec67-144">The default value is 240 (4 hours).</span></span> <span data-ttu-id="4ec67-145">将此值设置为零（0）将禁用 MED-V 工作区唤醒策略。</span><span class="sxs-lookup"><span data-stu-id="4ec67-145">Setting this value to zero (0) disables the MED-V workspace wake-up policy.</span></span>

<span data-ttu-id="4ec67-146">有关如何定义 MED-V 配置值的详细信息，请参阅[管理 Med-v 工作区配置设置](managing-med-v-workspace-configuration-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="4ec67-146">For more information about how to define your MED-V configuration values, see [Managing MED-V Workspace Configuration Settings](managing-med-v-workspace-configuration-settings.md).</span></span>

<span data-ttu-id="4ec67-147">**注意** MED-V 最佳做法是设置唤醒时间间隔，以匹配 MED-V 虚拟机计划定期更新的时间。</span><span class="sxs-lookup"><span data-stu-id="4ec67-147">**Note** A MED-V best practice is to set your wake up interval to match the time when MED-V virtual machines are planned to be updated regularly.</span></span> <span data-ttu-id="4ec67-148">此外，我们建议你将这些设置配置为类似于主机的行为。</span><span class="sxs-lookup"><span data-stu-id="4ec67-148">In addition, we recommend that you configure these settings to resemble the host computer’s behavior.</span></span>

 

### <span data-ttu-id="4ec67-149">使用 ESD 系统重启通知</span><span class="sxs-lookup"><span data-stu-id="4ec67-149">Reboot Notification Using your ESD System</span></span>

<span data-ttu-id="4ec67-150">你可以将你的 ESD 系统配置为在应用自动更新后的 MED-V 工作区需要重启时通知 MED-V。</span><span class="sxs-lookup"><span data-stu-id="4ec67-150">You can configure your ESD system to notify MED-V whenever a restart is required for the MED-V workspace after automatic updates have been applied.</span></span> <span data-ttu-id="4ec67-151">通过你知道需要重启的 ESD 系统应用自动更新时，你应该编写一个脚本来通知 MED-V 工作区上的以下全局事件：</span><span class="sxs-lookup"><span data-stu-id="4ec67-151">When you apply automatic updates through your ESD system that you know require a restart, you should write a script to signal the following global event on the MED-V workspace:</span></span>

<span data-ttu-id="4ec67-152">**重要提示** 您必须以 "仅修改" 权限打开该事件，然后向其发送信号。</span><span class="sxs-lookup"><span data-stu-id="4ec67-152">**Important** You must open the event with Modify Only rights and then signal it.</span></span> <span data-ttu-id="4ec67-153">如果不使用正确的权限将其打开，它将不起作用。</span><span class="sxs-lookup"><span data-stu-id="4ec67-153">If you do not open it with the correct permissions, it does not work.</span></span>

 

``` syntax
/// <summary>
/// The guest is required to be restarted due to an ESD update.
/// </summary>
public const string MedvGuestRebootRequiredEventName = @"Global\MedvGuestRebootRequiredEvent";
using (EventWaitHandle notificationEvent = 
EventWaitHandle.OpenExisting(eventName, EventWaitHandleRights.Modify))
{
notificationEvent.Set();
}
```

<span data-ttu-id="4ec67-154">当你发出此事件的信号时，MED-V 会捕获它并通知虚拟机需要重启。</span><span class="sxs-lookup"><span data-stu-id="4ec67-154">When you signal this event, MED-V captures it and informs the virtual machine that a restart is required.</span></span>

## <span data-ttu-id="4ec67-155">相关主题</span><span class="sxs-lookup"><span data-stu-id="4ec67-155">Related topics</span></span>


[<span data-ttu-id="4ec67-156">管理 MED-V 工作区的软件更新</span><span class="sxs-lookup"><span data-stu-id="4ec67-156">Managing Software Updates for MED-V Workspaces</span></span>](managing-software-updates-for-med-v-workspaces.md)

 

 





