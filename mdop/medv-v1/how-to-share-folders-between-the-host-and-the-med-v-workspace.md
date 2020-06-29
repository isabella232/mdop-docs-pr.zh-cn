---
title: 如何在主机和 MED-V 工作区之间共享文件夹
description: 如何在主机和 MED-V 工作区之间共享文件夹
author: dansimp
ms.assetid: 3cb295f2-c07e-4ee6-aa3c-ce4c8c45c191
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 87f315c9894cd38834413d2549e652a36c5cc16d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803831"
---
# <span data-ttu-id="cdb76-103">如何在主机和 MED-V 工作区之间共享文件夹</span><span class="sxs-lookup"><span data-stu-id="cdb76-103">How to Share Folders Between the Host and the MED-V Workspace</span></span>


<span data-ttu-id="cdb76-104">你可以在主机和 MED-V 工作区之间共享文件夹。</span><span class="sxs-lookup"><span data-stu-id="cdb76-104">You can share folders between the host and the MED-V workspace.</span></span> <span data-ttu-id="cdb76-105">共享文件夹可以存储在以下文件夹中：</span><span class="sxs-lookup"><span data-stu-id="cdb76-105">The shared folders can be stored on the following:</span></span>

-   <span data-ttu-id="cdb76-106">网络上的外部计算机</span><span class="sxs-lookup"><span data-stu-id="cdb76-106">An external computer on the network</span></span>

-   <span data-ttu-id="cdb76-107">主计算机</span><span class="sxs-lookup"><span data-stu-id="cdb76-107">The host computer</span></span>

<span data-ttu-id="cdb76-108">以下过程演示了如何在主机和 MED-V 工作区之间共享文件夹。</span><span class="sxs-lookup"><span data-stu-id="cdb76-108">The following procedures demonstrate how to share folders between the host and the MED-V workspace.</span></span>

**<span data-ttu-id="cdb76-109">共享位于网络上的文件夹</span><span class="sxs-lookup"><span data-stu-id="cdb76-109">To share folders located on the network</span></span>**

1.  <span data-ttu-id="cdb76-110">在完整桌面模式下配置 MED-V。</span><span class="sxs-lookup"><span data-stu-id="cdb76-110">Configure MED-V in full desktop mode.</span></span>

2.  <span data-ttu-id="cdb76-111">在 MED-V 管理的 "网络" 选项卡上，单击 "**使用不同于主机的 IP 地址（桥）**"。</span><span class="sxs-lookup"><span data-stu-id="cdb76-111">In MED-V management, on the Network tab, click **Use different IP address than host (Bridge)**.</span></span>

3.  <span data-ttu-id="cdb76-112">在主机计算机上执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="cdb76-112">Do the following on the host computer:</span></span>

    1.  <span data-ttu-id="cdb76-113">在 "控制面板" 中，单击 "**查看网络状态和任务**"，然后将 "**网络发现**" 设置为 **"打开"**。</span><span class="sxs-lookup"><span data-stu-id="cdb76-113">In Control Panel, click **View network status and tasks**, and set **Network discovery** to **On**.</span></span>

    2.  <span data-ttu-id="cdb76-114">在 "开始" 菜单上，右键单击 "**计算机**"，然后单击 "**映射网络驱动器**"。</span><span class="sxs-lookup"><span data-stu-id="cdb76-114">On the Start menu, right-click **Computer**, and click **Map network drive**.</span></span>

    3.  <span data-ttu-id="cdb76-115">在 "**映射网络驱动器**" 对话框的 "**驱动器**" 字段中，选择一个驱动器。</span><span class="sxs-lookup"><span data-stu-id="cdb76-115">In the **Map Network Drive** dialog box, in the **Drive** field, select a drive.</span></span>

        <span data-ttu-id="cdb76-116">**注意** 确保两台计算机上未使用相同的驱动器号。</span><span class="sxs-lookup"><span data-stu-id="cdb76-116">**Note** Ensure that the same drive letter is not in use on both computers.</span></span>

         

    4.  <span data-ttu-id="cdb76-117">单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="cdb76-117">Click **Browse**.</span></span>

    5.  <span data-ttu-id="cdb76-118">在 "**浏览文件夹**" 对话框中，通过浏览找到共享驱动器，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="cdb76-118">In the **Browse For Folder** dialog box, browse to the shared drive, and click **OK**.</span></span>

    6.  <span data-ttu-id="cdb76-119">单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="cdb76-119">Click **Finish**.</span></span>

4.  <span data-ttu-id="cdb76-120">在 MED-V 工作区中重复步骤3。</span><span class="sxs-lookup"><span data-stu-id="cdb76-120">Repeat step 3 in the MED-V workspace.</span></span> <span data-ttu-id="cdb76-121">指向与主机上相同的驱动器。</span><span class="sxs-lookup"><span data-stu-id="cdb76-121">Point to the same drive as on the host computer.</span></span>

**<span data-ttu-id="cdb76-122">共享位于主机上的文件夹</span><span class="sxs-lookup"><span data-stu-id="cdb76-122">To share folders located on the host</span></span>**

1.  <span data-ttu-id="cdb76-123">将文件夹配置为具有相应权限的共享文件夹。</span><span class="sxs-lookup"><span data-stu-id="cdb76-123">Configure the folder to be shared with the appropriate permissions.</span></span>

2.  <span data-ttu-id="cdb76-124">从 MED-V 工作区，转到 **"网上邻居**" 并找到共享文件夹。</span><span class="sxs-lookup"><span data-stu-id="cdb76-124">From the MED-V workspace, go to **My network places** and locate the shared folder.</span></span>

3.  <span data-ttu-id="cdb76-125">在 MED-V 工作区中，找到共享文件夹。</span><span class="sxs-lookup"><span data-stu-id="cdb76-125">From the MED-V workspace, locate the shared folder.</span></span>

<span data-ttu-id="cdb76-126">**注意** 确保主机和 MED-V 工作区计算机位于同一个域或工作组中。</span><span class="sxs-lookup"><span data-stu-id="cdb76-126">**Note** Ensure that both the host and MED-V workspace computers are in the same domain or workgroup.</span></span>

 

 

 





