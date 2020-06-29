---
title: 通过使用管理工具包对 MED-V 进行故障排除
description: 通过使用管理工具包对 MED-V 进行故障排除
author: dansimp
ms.assetid: 6c096a1c-b9ce-4ec7-8dfd-5286e3b9a617
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c1eaa493e5603e8a1275a6ff5f189739b168f319
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803755"
---
# <span data-ttu-id="e7122-103">通过使用管理工具包对 MED-V 进行故障排除</span><span class="sxs-lookup"><span data-stu-id="e7122-103">Troubleshooting MED-V by Using the Administration Toolkit</span></span>


<span data-ttu-id="e7122-104">使用 MED-V 管理工具包解决 MED-V 工作区中的某些问题。</span><span class="sxs-lookup"><span data-stu-id="e7122-104">Use the MED-V Administration Toolkit to troubleshoot certain problems in a MED-V workspace.</span></span> <span data-ttu-id="e7122-105">使用 MED-V 管理工具包，你可以访问和配置事件日志、重启或重置 MED-V 工作区，以及在 MED-V 工作区中查看已发布的应用程序和重定向的 web 地址。</span><span class="sxs-lookup"><span data-stu-id="e7122-105">The MED-V Administration Toolkit lets you access and configure event logs, restart or reset the MED-V workspace, and view the published applications and redirected web addresses in the MED-V workspace.</span></span> <span data-ttu-id="e7122-106">你还可以使用 MED-V 管理工具包以全屏模式打开 MED-V 工作区虚拟机。</span><span class="sxs-lookup"><span data-stu-id="e7122-106">You can also use the MED-V Administration Toolkit to open the MED-V workspace virtual machine in full-screen mode.</span></span>

## <span data-ttu-id="e7122-107">打开 MED-V 管理工具包</span><span class="sxs-lookup"><span data-stu-id="e7122-107">To Open the MED-V Administration Toolkit</span></span>


<span data-ttu-id="e7122-108">若要打开 MED-V 管理工具包，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="e7122-108">Perform the following steps to open the MED-V Administration Toolkit:</span></span>

1.  <span data-ttu-id="e7122-109">在包含您要排除的 MED-V 工作区的主机上，打开命令提示符窗口。</span><span class="sxs-lookup"><span data-stu-id="e7122-109">On the host computer that contains the MED-V workspace you are troubleshooting, open a Command Prompt window.</span></span>

2.  <span data-ttu-id="e7122-110">浏览到%systemdrive%\\Program Files\\Microsoft 企业版桌面虚拟化。</span><span class="sxs-lookup"><span data-stu-id="e7122-110">Browse to %systemdrive%\\Program Files\\Microsoft Enterprise Desktop Virtualization.</span></span>

3.  <span data-ttu-id="e7122-111">在命令提示符处，键入**MedvHost/toolkit**。</span><span class="sxs-lookup"><span data-stu-id="e7122-111">At the command prompt, type **MedvHost /toolkit**.</span></span>

<span data-ttu-id="e7122-112">在 "MED-V 管理" 工具包打开后，您可以使用该工具包帮助解决在故障排除过程中发现的 MED-V 工作区中的问题。</span><span class="sxs-lookup"><span data-stu-id="e7122-112">After the MED-V Administration Toolkit opens, you can use the toolkit to help resolve issues in the MED-V workspace found during troubleshooting.</span></span>

## <span data-ttu-id="e7122-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="e7122-113">In this Section</span></span>


<a href="" id="viewing-and-configuring-med-v-logs"></a>[<span data-ttu-id="e7122-114">查看和配置 MED-V 日志</span><span class="sxs-lookup"><span data-stu-id="e7122-114">Viewing and Configuring MED-V Logs</span></span>](viewing-and-configuring-med-v-logs.md)  
<span data-ttu-id="e7122-115">介绍如何使用 MED-V 管理工具包在主计算机和来宾虚拟机中收集和管理 MED-V 事件日志。</span><span class="sxs-lookup"><span data-stu-id="e7122-115">Describes how to use the MED-V Administration Toolkit to collect and manage MED-V event logs in the host computer and the guest virtual machine.</span></span>

<a href="" id="restarting-and-resetting-a-med-v-workspace"></a>[<span data-ttu-id="e7122-116">重启和重置 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="e7122-116">Restarting and Resetting a MED-V Workspace</span></span>](restarting-and-resetting-a-med-v-workspace.md)  
<span data-ttu-id="e7122-117">介绍如何使用 MED-V 管理工具包重新启动和重置 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="e7122-117">Describes how to restart and reset MED-V workspaces by using the MED-V Administration Toolkit.</span></span>

<a href="" id="viewing-med-v-workspace-configurations"></a>[<span data-ttu-id="e7122-118">查看 MED-V 工作区配置</span><span class="sxs-lookup"><span data-stu-id="e7122-118">Viewing MED-V Workspace Configurations</span></span>](viewing-med-v-workspace-configurations.md)  
<span data-ttu-id="e7122-119">介绍如何使用 MED-V 管理工具包查看 MED-V 工作区中已发布的应用程序和重定向的 web 地址，以及如何在全屏模式下打开 MED-V 工作区虚拟机。</span><span class="sxs-lookup"><span data-stu-id="e7122-119">Describes how to use the MED-V Administration Toolkit to view the published applications and redirected web addresses in a MED-V workspace and how to open the MED-V workspace virtual machine in full-screen mode.</span></span>

## <span data-ttu-id="e7122-120">相关主题</span><span class="sxs-lookup"><span data-stu-id="e7122-120">Related topics</span></span>


[<span data-ttu-id="e7122-121">MED-V 事件日志消息</span><span class="sxs-lookup"><span data-stu-id="e7122-121">MED-V Event Log Messages</span></span>](med-v-event-log-messages.md)

[<span data-ttu-id="e7122-122">MED-V 故障排除</span><span class="sxs-lookup"><span data-stu-id="e7122-122">Troubleshooting MED-V</span></span>](troubleshooting-med-vmedv2.md)

 

 





