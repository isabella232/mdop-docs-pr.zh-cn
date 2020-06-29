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
# 管理 MED-V 工作区的自动更新


MED-V 工作区是一个虚拟机，它包含一个单独的操作系统，其自动软件更新过程必须像企业中的物理计算机一样进行管理。 由于来宾操作系统在主机操作系统运行时不一定始终运行，因此你必须确保以某种方式配置 MED-V 虚拟机，以便根据需要将软件更新应用到来宾操作系统。 Microsoft 企业版桌面虚拟化（MED-V）2.0 解决方案提供的功能可让你确定如何在 MED-V 工作区中处理自动软件更新。

## 管理 MED-V 工作区唤醒策略


MED-V 工作区唤醒策略可确保 MED-V 虚拟机在你在 MED-V 配置设置中指定的时间内可用于更新。 这适用于从 Microsoft 发布的更新，这些更新是通过 Windows 更新和非 Microsoft 解决方案（如防病毒应用程序）部署和控制的更新。

**重要提示** MED-V 工作区唤醒策略已针对 Microsoft Update 基础结构进行了优化。 如果你使用 Microsoft System Center Configuration Manager 部署非 Microsoft 更新，我们建议你还使用 System Center Updates Publisher，它利用与 Microsoft 更新相同的基础结构，因此可以从 MED-V 工作区唤醒策略中受益。 有关详细信息，请参阅[System Center Update Publisher](https://go.microsoft.com/fwlink/?LinkId=200035) （ https://go.microsoft.com/fwlink/?LinkId=200035) 。

 

当你创建 MED-V 工作区程序包时，在最终用户登录（**快速启动**）或最终用户首次打开已发布的应用程序（**正常启动**）时，你将配置该程序包的启动和操作方式。 或者，设置该选项以允许最终用户控制此设置。

无论是哪一种情况，只要选择了 "**快速启动**" 选项，只要 med-v 主机作为用户登录，虚拟机就会继续运行。 在此配置中，因为当主机处于活动状态时，MED-V 处于活动状态，因此无需从 MED-V 中进行任何额外处理即可应用自动更新。

但是，对于未指定 "**快速启动**" 或虚拟机处于休眠或停止状态的情况，med-v 通过其 med-v 工作区唤醒策略（即使不定期使用 med-v）来确保来宾操作系统定期更新。 MED-V 通过基于你指定的配置设置定期唤醒虚拟机来执行此函数。 这使虚拟机中的自动更新客户端能够根据其配置执行。在 MED-V 配置设置定义的时间段过后，MED-V 会将虚拟机恢复到其以前的状态。

**注意** 如果最终用户在更新期间打开已发布的应用程序，则会应用所需的更新，但在更新期结束后，MED-V 不会自动休眠或关闭。 而 MED-V 将继续运行。

 

MED-V 工作区唤醒策略包括三个主要组件：

**来宾更新管理器**

此独立的可执行程序驻留在 MED-V 主机上，负责根据预定义的可配置计划来唤醒虚拟机。 指定配置设置以指示更新管理器每日唤醒虚拟机的时间，以及虚拟机应保持唤醒状态的时间（以分钟为单位）以允许应用更新。 指定的分钟数达到指定的分钟数后，来宾更新管理器会将虚拟机置于休眠状态，为下一次使用做好准备。 你可以通过 Windows 任务管理器安排此可执行程序的执行。

**来宾重启管理服务**

驻留在 MED-V 主机上，此服务有三个主要职责。 与来宾更新管理器一起，它会在用户登录时管理虚拟机的重启（如果需要）。 它会检测到需要重新启动虚拟机的情况，因为安装了更新。 并且确保始终按照配置对来宾更新管理器的任务进行计划。

**来宾更新服务**

在 MED-V 虚拟机上，此 Windows 服务负责在安装更新需要重启时进行监视。 在服务意识到需要重启后，它会在主机上通知来宾重启管理服务。

### MED-V 工作区唤醒策略的配置设置

你可以通过在注册表中定义以下两个配置值来控制虚拟机 awakens 接收自动更新的时间和时间。 这两个值均位于 HKLM\\Software\\Microsoft\\MEDV\\v2\\VM 键下。

**GuestUpdateTime** -如果 med-v 必须根据24小时制时钟标准唤醒更新虚拟机，则每天配置小时和分钟数。 以 HH： MM 的格式指定时间。 默认值为00:00 （午夜）。

**GuestUpdateDuration** -配置在 GuestUpdateTime 配置设置中指定的时间开始，med-v 必须保持虚拟机唤醒以进行更新的分钟数。 默认值为240（4小时）。 将此值设置为零（0）将禁用 MED-V 工作区唤醒策略。

有关如何定义 MED-V 配置值的详细信息，请参阅[管理 Med-v 工作区配置设置](managing-med-v-workspace-configuration-settings.md)。

**注意** MED-V 最佳做法是设置唤醒时间间隔，以匹配 MED-V 虚拟机计划定期更新的时间。 此外，我们建议你将这些设置配置为类似于主机的行为。

 

### 使用 ESD 系统重启通知

你可以将你的 ESD 系统配置为在应用自动更新后的 MED-V 工作区需要重启时通知 MED-V。 通过你知道需要重启的 ESD 系统应用自动更新时，你应该编写一个脚本来通知 MED-V 工作区上的以下全局事件：

**重要提示** 您必须以 "仅修改" 权限打开该事件，然后向其发送信号。 如果不使用正确的权限将其打开，它将不起作用。

 

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

当你发出此事件的信号时，MED-V 会捕获它并通知虚拟机需要重启。

## 相关主题


[管理 MED-V 工作区的软件更新](managing-software-updates-for-med-v-workspaces.md)

 

 





