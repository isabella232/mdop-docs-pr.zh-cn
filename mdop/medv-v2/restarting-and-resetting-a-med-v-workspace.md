---
title: 重启和重置 MED-V 工作区
description: 重启和重置 MED-V 工作区
author: dansimp
ms.assetid: a959cdb3-a727-47c7-967e-e58f224e74de
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 48a644c2ed1668f87eb6e1a78521e780e8b783dd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803765"
---
# <span data-ttu-id="ed009-103">重启和重置 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="ed009-103">Restarting and Resetting a MED-V Workspace</span></span>


<span data-ttu-id="ed009-104">在故障排除期间，有时您可能会发现需要重新启动或重置 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="ed009-104">During troubleshooting, you may sometimes find it necessary to restart or reset the MED-V workspace.</span></span> <span data-ttu-id="ed009-105">重启 MED-V 工作区与重启物理计算机基本相同。</span><span class="sxs-lookup"><span data-stu-id="ed009-105">Restarting the MED-V workspace is basically the same as restarting a physical computer.</span></span> <span data-ttu-id="ed009-106">重置 MED-V 工作区首次重新运行设置并删除虚拟机中存储的所有数据。</span><span class="sxs-lookup"><span data-stu-id="ed009-106">Resetting the MED-V workspace reruns first time setup and deletes all data that is stored in the virtual machine.</span></span> <span data-ttu-id="ed009-107">由于删除了所有存储的数据，因此通常应仅重置 MED-V 工作区以解决最严重的疑难解答问题，或者将以前工作的 MED-V 工作区还原为工作状态。</span><span class="sxs-lookup"><span data-stu-id="ed009-107">Because all stored data is deleted, you typically should only reset the MED-V workspace to resolve the most serious troubleshooting issues, or to restore a previously working MED-V workspace back to a working state.</span></span>

<span data-ttu-id="ed009-108">有关如何打开 MED-V 管理工具包的信息，请参阅[使用管理工具包对 Med-v 进行故障排除](troubleshooting-med-v-by-using-the-administration-toolkit.md)。</span><span class="sxs-lookup"><span data-stu-id="ed009-108">For information about how to open the MED-V Administration Toolkit, see [Troubleshooting MED-V by Using the Administration Toolkit](troubleshooting-med-v-by-using-the-administration-toolkit.md).</span></span>

**<span data-ttu-id="ed009-109">重新启动 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="ed009-109">Restarting a MED-V Workspace</span></span>**

1.  <span data-ttu-id="ed009-110">在 " **Med-v 管理工具包**" 窗口中，单击 "**重启 med-v 工作区**"。</span><span class="sxs-lookup"><span data-stu-id="ed009-110">On the **MED-V Administration Toolkit** window, click **Restart MED-V Workspace**.</span></span> <span data-ttu-id="ed009-111">将打开一个对话框窗口，您必须确认是否要重新启动 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="ed009-111">A dialog window opens in which you must confirm that you want to restart the MED-V workspace.</span></span>

2.  <span data-ttu-id="ed009-112">单击 "**重新启动**"。</span><span class="sxs-lookup"><span data-stu-id="ed009-112">Click **Restart**.</span></span>

    <span data-ttu-id="ed009-113">当 MED-V 工作区重新启动时，任何运行的或重定向的网站已打开的应用程序都将关闭。</span><span class="sxs-lookup"><span data-stu-id="ed009-113">Any published applications that are running or redirected web sites that are open will be closed when the MED-V workspace restarts.</span></span>

**<span data-ttu-id="ed009-114">重置 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="ed009-114">Resetting a MED-V Workspace</span></span>**

1.  <span data-ttu-id="ed009-115">在 " **Med-v 管理工具包**" 窗口中，单击 "**重置 med-v 工作区**"。</span><span class="sxs-lookup"><span data-stu-id="ed009-115">On the **MED-V Administration Toolkit** window, click **Reset MED-V Workspace**.</span></span> <span data-ttu-id="ed009-116">将打开一个对话框窗口，您必须确认是否要重置 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="ed009-116">A dialog window opens in which you must confirm that you want to reset the MED-V workspace.</span></span>

    <span data-ttu-id="ed009-117">**警告** 重置 MED-V 工作区会导致首次设置再次运行，从而重新加载原始虚拟硬盘。</span><span class="sxs-lookup"><span data-stu-id="ed009-117">**Warning** Resetting the MED-V workspace causes first time setup to run again, and thus reloads the original virtual hard disk.</span></span> <span data-ttu-id="ed009-118">自首次运行设置后的 MED-V 工作区中存储的所有数据将被删除。</span><span class="sxs-lookup"><span data-stu-id="ed009-118">All data that is stored in the MED-V workspace since first time setup was originally run will be deleted.</span></span>

     

2.  <span data-ttu-id="ed009-119">单击**重置**。</span><span class="sxs-lookup"><span data-stu-id="ed009-119">Click **Reset**.</span></span>

    <span data-ttu-id="ed009-120">当 MED-V 工作区重置时，任何运行的或重定向的网站都将关闭的已发布应用程序。</span><span class="sxs-lookup"><span data-stu-id="ed009-120">Any published applications that are running or redirected web sites that are open will be closed when the MED-V workspace resets.</span></span>

## <span data-ttu-id="ed009-121">相关主题</span><span class="sxs-lookup"><span data-stu-id="ed009-121">Related topics</span></span>


[<span data-ttu-id="ed009-122">查看和配置 MED-V 日志</span><span class="sxs-lookup"><span data-stu-id="ed009-122">Viewing and Configuring MED-V Logs</span></span>](viewing-and-configuring-med-v-logs.md)

[<span data-ttu-id="ed009-123">查看 MED-V 工作区配置</span><span class="sxs-lookup"><span data-stu-id="ed009-123">Viewing MED-V Workspace Configurations</span></span>](viewing-med-v-workspace-configurations.md)

 

 





