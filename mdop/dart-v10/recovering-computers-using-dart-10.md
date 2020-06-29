---
title: 使用 DaRT 10 恢复计算机
description: 使用 DaRT 10 恢复计算机
author: dansimp
ms.assetid: 2ad7fab0-c22d-4171-8b5a-b2b7d7c0ad2d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2031d55427e24638e41dfc6ed7b0ef437922e9c4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803272"
---
# <span data-ttu-id="fd3bc-103">使用 DaRT 10 恢复计算机</span><span class="sxs-lookup"><span data-stu-id="fd3bc-103">Recovering Computers Using DaRT 10</span></span>


<span data-ttu-id="fd3bc-104">部署 Microsoft 诊断和恢复工具集（DaRT）10恢复映像后，您可以使用 DaRT 10 恢复计算机。</span><span class="sxs-lookup"><span data-stu-id="fd3bc-104">After deploying the Microsoft Diagnostics and Recovery Toolset (DaRT) 10 recovery image, you can use DaRT 10 to recover computers.</span></span> <span data-ttu-id="fd3bc-105">本部分中的信息介绍了您可以执行的恢复任务。</span><span class="sxs-lookup"><span data-stu-id="fd3bc-105">The information in this section describes the recovery tasks that you can perform.</span></span>

<span data-ttu-id="fd3bc-106">你可以选择多种不同的方法来启动到 DaRT，具体取决于你部署 DaRT 恢复映像的方式。</span><span class="sxs-lookup"><span data-stu-id="fd3bc-106">You have several different methods to choose from to boot into DaRT, depending on how you deploy the DaRT recovery image.</span></span>

-   <span data-ttu-id="fd3bc-107">将 DaRT 恢复映像 CD、DVD 或 USB 闪存驱动器插入到有问题的计算机中，然后使用它启动到计算机。</span><span class="sxs-lookup"><span data-stu-id="fd3bc-107">Insert a DaRT recovery image CD, DVD, or USB flash drive into the problem computer and use it to boot into the computer.</span></span>

-   <span data-ttu-id="fd3bc-108">从有问题的计算机上的恢复分区启动到 DaRT。</span><span class="sxs-lookup"><span data-stu-id="fd3bc-108">Boot into DaRT from a recovery partition on the problem computer.</span></span>

-   <span data-ttu-id="fd3bc-109">从网络上的远程分区启动到 DaRT。</span><span class="sxs-lookup"><span data-stu-id="fd3bc-109">Boot into DaRT from a remote partition on the network.</span></span>

<span data-ttu-id="fd3bc-110">有关每种方法的优点和缺点的信息，请参阅[规划如何保存和部署 DaRT 10 恢复映像](planning-how-to-save-and-deploy-the-dart-10-recovery-image.md)。</span><span class="sxs-lookup"><span data-stu-id="fd3bc-110">For information about the advantages and disadvantages of each method, see [Planning How to Save and Deploy the DaRT 10 Recovery Image](planning-how-to-save-and-deploy-the-dart-10-recovery-image.md).</span></span>

<span data-ttu-id="fd3bc-111">无论使用哪种方法启动到 DaRT，您都必须在 BIOS 中为启动选项启用启动设备，或者您希望向最终用户提供的选项。</span><span class="sxs-lookup"><span data-stu-id="fd3bc-111">Whichever method that you use to boot into DaRT, you must enable the boot device in the BIOS for the boot option or options that you want to make available to the end user.</span></span>

<span data-ttu-id="fd3bc-112">**注意** 配置 BIOS 是唯一的，具体取决于您的组织中使用的硬盘驱动器、网络适配器和其他硬件的类型。</span><span class="sxs-lookup"><span data-stu-id="fd3bc-112">**Note** Configuring the BIOS is unique, depending on the kind of hard disk drive, network adapters, and other hardware that is used in your organization.</span></span>

 

## <span data-ttu-id="fd3bc-113">使用 DaRT 恢复映像恢复本地计算机</span><span class="sxs-lookup"><span data-stu-id="fd3bc-113">Recover a local computer by using the DaRT recovery image</span></span>


<span data-ttu-id="fd3bc-114">若要使用 DaRT 恢复本地计算机，您必须在遇到需要 DaRT 的问题的最终用户计算机上进行物理演示。</span><span class="sxs-lookup"><span data-stu-id="fd3bc-114">To recover a local computer by using DaRT, you must be physically present at the end-user computer that is experiencing problems that require DaRT.</span></span>

[<span data-ttu-id="fd3bc-115">如何使用 DaRT 恢复映像恢复本地计算机</span><span class="sxs-lookup"><span data-stu-id="fd3bc-115">How to Recover Local Computers by Using the DaRT Recovery Image</span></span>](how-to-recover-local-computers-by-using-the-dart-recovery-image-dart-10.md)

## <span data-ttu-id="fd3bc-116">使用 DaRT 恢复映像恢复远程计算机</span><span class="sxs-lookup"><span data-stu-id="fd3bc-116">Recover a remote computer by using the DaRT recovery image</span></span>


<span data-ttu-id="fd3bc-117">DaRT 中的远程连接功能允许 IT 管理员在最终用户计算机上远程运行 DaRT 工具。</span><span class="sxs-lookup"><span data-stu-id="fd3bc-117">The Remote Connection feature in DaRT lets an IT administrator run the DaRT tools remotely on an end-user computer.</span></span> <span data-ttu-id="fd3bc-118">当最终用户（或由支持最终用户计算机的技术支持人员）提供某些信息后，IT 管理员或技术支持人员可以控制最终用户的计算机并远程运行必要的 DaRT 工具。</span><span class="sxs-lookup"><span data-stu-id="fd3bc-118">After certain information is provided by the end user (or by a help desk professional working on the end-user computer), the IT administrator or help desk worker can take control of the end user's computer and run the necessary DaRT tools remotely.</span></span>

<span data-ttu-id="fd3bc-119">**重要提示** 建立远程连接的两台计算机必须是同一网络的一部分。</span><span class="sxs-lookup"><span data-stu-id="fd3bc-119">**Important** The two computers establishing a remote connection must be part of the same network.</span></span>

 

<span data-ttu-id="fd3bc-120">"**诊断和恢复工具集**" 窗口包括从管理员计算机远程运行最终用户计算机上的 DaRT 的选项。</span><span class="sxs-lookup"><span data-stu-id="fd3bc-120">The **Diagnostics and Recovery Toolset** window includes the option to run DaRT on an end-user computer remotely from an administrator computer.</span></span> <span data-ttu-id="fd3bc-121">最终用户在问题计算机上打开 DaRT 工具，然后通过单击 "**远程连接**" 启动远程会话。</span><span class="sxs-lookup"><span data-stu-id="fd3bc-121">The end user opens the DaRT tools on the problem computer and starts the remote session by clicking **Remote Connection**.</span></span>

<span data-ttu-id="fd3bc-122">最终用户计算机上的 "远程连接" 功能创建以下连接信息：票证编号、端口和所有可用 IP 地址的列表。</span><span class="sxs-lookup"><span data-stu-id="fd3bc-122">The Remote Connection feature on the end-user computer creates the following connection information: a ticket number, a port, and a list of all available IP addresses.</span></span> <span data-ttu-id="fd3bc-123">票据号码和端口是随机生成的。</span><span class="sxs-lookup"><span data-stu-id="fd3bc-123">The ticket number and port are generated randomly.</span></span>

<span data-ttu-id="fd3bc-124">IT 管理员或技术支持人员将此信息输入到**DaRT 远程连接查看器**中，以便与最终用户计算机建立终端服务连接。</span><span class="sxs-lookup"><span data-stu-id="fd3bc-124">The IT administrator or help desk worker enters this information into the **DaRT Remote Connection Viewer** to establish the terminal services connection to the end-user computer.</span></span> <span data-ttu-id="fd3bc-125">已建立的终端服务连接允许 IT 管理员与最终用户计算机上的 DaRT 工具远程交互。</span><span class="sxs-lookup"><span data-stu-id="fd3bc-125">The terminal services connection that is established lets an IT administrator remotely interact with the DaRT tools on the end-user computer.</span></span> <span data-ttu-id="fd3bc-126">最终用户计算机将处理连接信息、共享其屏幕，并响应来自 IT 管理员计算机的说明。</span><span class="sxs-lookup"><span data-stu-id="fd3bc-126">The end-user computer then processes the connection information, shares its screen, and responds to instructions from the IT administrator computer.</span></span>

[<span data-ttu-id="fd3bc-127">如何使用 DaRT 恢复映像恢复远程计算机</span><span class="sxs-lookup"><span data-stu-id="fd3bc-127">How to Recover Remote Computers by Using the DaRT Recovery Image</span></span>](how-to-recover-remote-computers-by-using-the-dart-recovery-image-dart-10.md)

## <span data-ttu-id="fd3bc-128">使用 DaRT 10 恢复计算机的其他资源</span><span class="sxs-lookup"><span data-stu-id="fd3bc-128">Other resources for recovering computers using DaRT 10</span></span>


[<span data-ttu-id="fd3bc-129">DaRT 10 的操作</span><span class="sxs-lookup"><span data-stu-id="fd3bc-129">Operations for DaRT 10</span></span>](operations-for-dart-10.md)

 

 





