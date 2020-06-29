---
title: 更新 MED-V 2.0
description: 更新 MED-V 2.0
author: dansimp
ms.assetid: beea2f54-42d7-4a17-98e0-d243a8562265
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 62e8987ec511783422b8dd336dd4f3be2008c9b2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803427"
---
# <span data-ttu-id="2402c-103">更新 MED-V 2.0</span><span class="sxs-lookup"><span data-stu-id="2402c-103">Updating MED-V 2.0</span></span>


<span data-ttu-id="2402c-104">通过为 Microsoft 企业版桌面虚拟化（MED-V）2.0 应用相应的安全更新来帮助保护您的系统。</span><span class="sxs-lookup"><span data-stu-id="2402c-104">Help secure your system by applying the appropriate security updates for Microsoft Enterprise Desktop Virtualization (MED-V) 2.0.</span></span>

## <span data-ttu-id="2402c-105">更新 MED-V</span><span class="sxs-lookup"><span data-stu-id="2402c-105">Updating MED-V</span></span>


<span data-ttu-id="2402c-106">你可以由最终用户以交互方式或通过使用电子软件分发系统以静默方式更新 MED-V。</span><span class="sxs-lookup"><span data-stu-id="2402c-106">You can update MED-V interactively, by the end user, or silently by using an electronic software distribution system.</span></span> <span data-ttu-id="2402c-107">安装 MED-V 主机代理升级 MED-V 主机代理，并根据需要更新 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="2402c-107">Installation of the MED-V Host Agent upgrades the MED-V Host Agent and then updates the MED-V workspace if required.</span></span> <span data-ttu-id="2402c-108">MED-V 主机代理和来宾代理保持同步。如果在更新 MED-V 主机代理的同时从 MED-V 工作区运行应用程序，则需要重启主机才能完成更新。</span><span class="sxs-lookup"><span data-stu-id="2402c-108">The MED-V Host Agent and Guest Agent keep in sync. If applications are running from the MED-V workspace while the MED-V Host Agent is being updated, a restart of the host computer is required to complete the update.</span></span> <span data-ttu-id="2402c-109">如果没有正在运行的应用程序，则会自动重新启动 MED-V，并且升级完成后不重新启动主机计算机。</span><span class="sxs-lookup"><span data-stu-id="2402c-109">If no applications are running, MED-V is restarted automatically and the upgrade is completed without a restart of the host computer.</span></span>

<span data-ttu-id="2402c-110">如果您使用电子软件分发系统更新 MED-V，则可以控制重启行为。</span><span class="sxs-lookup"><span data-stu-id="2402c-110">If you are updating MED-V by using an electronic software distribution system, you can control the restart behavior.</span></span> <span data-ttu-id="2402c-111">若要执行此操作，请在安装 MED-V\_HostAgent\_Setup.exe 时通过在命令提示符处键入**REBOOT = "ReallySuppress"** 来取消重新启动。</span><span class="sxs-lookup"><span data-stu-id="2402c-111">To do this, suppress the restart by typing **REBOOT=”ReallySuppress”** at the command prompt when installing MED-V\_HostAgent\_Setup.exe.</span></span> <span data-ttu-id="2402c-112">然后，配置电子软件分发系统以捕获3010返回代码（该代码表明需要重启），并执行设置重启行为。</span><span class="sxs-lookup"><span data-stu-id="2402c-112">Then, configure the electronic software distribution system to capture the 3010 return code (which signals that a restart is required) and perform the set restart behavior.</span></span>

## <span data-ttu-id="2402c-113">相关主题</span><span class="sxs-lookup"><span data-stu-id="2402c-113">Related topics</span></span>


[<span data-ttu-id="2402c-114">MED-V 的技术参考</span><span class="sxs-lookup"><span data-stu-id="2402c-114">Technical Reference for MED-V</span></span>](technical-reference-for-med-v.md)

 

 





