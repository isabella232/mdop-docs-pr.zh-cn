---
title: 在 MED-V 工作区上管理打印机
description: 在 MED-V 工作区上管理打印机
author: dansimp
ms.assetid: ba0a65ad-444f-4d18-95eb-8b9fa1a3ffba
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: bc7a62075c95e8816a425eff89ffb992f1185d04
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803904"
---
# <span data-ttu-id="6eec1-103">在 MED-V 工作区上管理打印机</span><span class="sxs-lookup"><span data-stu-id="6eec1-103">Managing Printers on a MED-V Workspace</span></span>


<span data-ttu-id="6eec1-104">在 Microsoft 企业桌面虚拟化（MED-V）2.0 中，打印机重定向使最终用户在 MED-V 虚拟机和主机计算机之间具有一致的打印体验。</span><span class="sxs-lookup"><span data-stu-id="6eec1-104">In Microsoft Enterprise Desktop Virtualization (MED-V) 2.0, printer redirection provides end users with a consistent printing experience between the MED-V virtual machine and the host computer.</span></span>

<span data-ttu-id="6eec1-105">本主题提供有关如何在 MED-V 工作区中管理打印的信息。</span><span class="sxs-lookup"><span data-stu-id="6eec1-105">This topic provides information about how to manage printing in a MED-V workspace.</span></span>

## <span data-ttu-id="6eec1-106">在 MED-V 工作区中管理打印机</span><span class="sxs-lookup"><span data-stu-id="6eec1-106">Managing Printers in MED-V Workspaces</span></span>


<span data-ttu-id="6eec1-107">在大多数情况下，MED-V 会自动处理打印机重定向。</span><span class="sxs-lookup"><span data-stu-id="6eec1-107">In most cases, MED-V handles printer redirection automatically.</span></span> <span data-ttu-id="6eec1-108">第一次安装完成后，MED-V 标识安装在主机上的所有网络打印机，从网络打印服务器检索对应的驱动程序，如果找到，则在 MED-V 工作区中安装相关的驱动程序。</span><span class="sxs-lookup"><span data-stu-id="6eec1-108">After first time setup finishes, MED-V identifies all network printers installed on the host, retrieves the corresponding drivers from the network print server, and if found, installs the relevant drivers in the MED-V workspace.</span></span> <span data-ttu-id="6eec1-109">找到并安装所有驱动程序后，MED-V 将重新启动 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="6eec1-109">After all drivers are found and installed, MED-V reboots the MED-V workspace.</span></span> <span data-ttu-id="6eec1-110">只有在 MED-V 工作区重启后，主机打印机才存在且在来宾上可用，通常在几分钟内才可用。</span><span class="sxs-lookup"><span data-stu-id="6eec1-110">Only after the MED-V workspace restarts, the host printers are present and available on the guest, typically in a few minutes.</span></span>

<span data-ttu-id="6eec1-111">**注意** 如果应用程序在 MED-V 工作区上运行，系统将提示最终用户让重启继续进行，或将其推迟到更高版本。</span><span class="sxs-lookup"><span data-stu-id="6eec1-111">**Note** If applications are running on the MED-V workspace, the end user is prompted to let the restart continue or postpone it until later.</span></span> <span data-ttu-id="6eec1-112">如果没有正在运行的应用程序，将自动重启，并且不会向最终用户显示。</span><span class="sxs-lookup"><span data-stu-id="6eec1-112">If no applications are running, the restart is automatic and not shown to the end user.</span></span>

 

<span data-ttu-id="6eec1-113">每次都重新启动时，它会检查主机上是否已安装了任何新打印机，如果找到，则从网络打印服务器检索相应的驱动程序，并将其安装在来宾设备上。</span><span class="sxs-lookup"><span data-stu-id="6eec1-113">Every time MED-V is re-started, it checks whether any new printers are installed on the host and, if found, retrieves the corresponding drivers from the network print server and installs them on the guest.</span></span> <span data-ttu-id="6eec1-114">然后，MED-V 将重新启动 MED-V 工作区，就像首次完成设置一样。</span><span class="sxs-lookup"><span data-stu-id="6eec1-114">MED-V then restarts the MED-V workspace just as when first time setup was completed.</span></span>

<span data-ttu-id="6eec1-115">**重要提示** 在来宾上安装了相关的驱动程序后，在重启后，打印机才会在来宾上可见。</span><span class="sxs-lookup"><span data-stu-id="6eec1-115">**Important** After the relevant drivers are installed on the guest, the printers only become visible on the guest after the restart occurs.</span></span>

 

<span data-ttu-id="6eec1-116">如果在任何时候无法找到或安装驱动程序，则必须手动将其安装在来宾上，网络打印机才能供最终用户使用。</span><span class="sxs-lookup"><span data-stu-id="6eec1-116">If at any time a driver cannot be located or installed, it must be manually installed on the guest for the network printer to be available to the end user.</span></span>

<span data-ttu-id="6eec1-117">下表提供了一些其他指南：</span><span class="sxs-lookup"><span data-stu-id="6eec1-117">The following list offers some additional guidance:</span></span>

<span data-ttu-id="6eec1-118">**Med-v 仅管理网络打印机**。</span><span class="sxs-lookup"><span data-stu-id="6eec1-118">**MED-V only manages network printers**.</span></span> <span data-ttu-id="6eec1-119">本地安装在主机上的打印机的驱动程序不会自动安装在来宾设备上。</span><span class="sxs-lookup"><span data-stu-id="6eec1-119">Drivers for printers that are installed locally on the host are not automatically installed on the guest.</span></span>

<span data-ttu-id="6eec1-120">**如果在打印服务器上发现打印机驱动程序，则 med-v 仅安装打印机驱动程序**。</span><span class="sxs-lookup"><span data-stu-id="6eec1-120">**MED-V only installs printer drivers if found on the print server**.</span></span> <span data-ttu-id="6eec1-121">如果未找到，则必须手动安装打印机驱动程序。</span><span class="sxs-lookup"><span data-stu-id="6eec1-121">If not found, printer drivers must be manually installed.</span></span>

<span data-ttu-id="6eec1-122">**主机无法访问手动安装在来宾上的打印机**。</span><span class="sxs-lookup"><span data-stu-id="6eec1-122">**Printers manually installed on the guest are not accessible to the host**.</span></span> <span data-ttu-id="6eec1-123">默认情况下，MED-V 仅支持从来宾到主机的打印机重定向。</span><span class="sxs-lookup"><span data-stu-id="6eec1-123">By default, MED-V only supports printer redirection from the guest to the host.</span></span>

<span data-ttu-id="6eec1-124">**警告** 如果在来宾上手动安装了打印机，并且在主机上安装了相同的打印机，则结果是在来宾中安装了两次打印机。</span><span class="sxs-lookup"><span data-stu-id="6eec1-124">**Warning** If a printer is manually installed on the guest, and the same printer is later installed on the host, the result is that the printer is installed two times in the guest.</span></span> <span data-ttu-id="6eec1-125">为了避免这种情况，MED-V 最佳做法是仅以一种方式管理打印机重定向：禁用重定向并在来宾上手动安装打印机，或者启用重定向，不要在来宾上手动安装打印机。</span><span class="sxs-lookup"><span data-stu-id="6eec1-125">To avoid this situation, a MED-V best practice is to manage printer redirection in one manner only: either disable redirection and install printers manually on the guest, or enable redirection and do not install printers manually on the guest.</span></span>

 

## <span data-ttu-id="6eec1-126">相关主题</span><span class="sxs-lookup"><span data-stu-id="6eec1-126">Related topics</span></span>


[<span data-ttu-id="6eec1-127">管理 MED-V 工作区设置</span><span class="sxs-lookup"><span data-stu-id="6eec1-127">Manage MED-V Workspace Settings</span></span>](manage-med-v-workspace-settings.md)

 

 





