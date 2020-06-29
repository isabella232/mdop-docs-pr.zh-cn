---
title: “碎片整理正在运行”对话框 (App-V 4.6 SP1)
description: “碎片整理正在运行”对话框 (App-V 4.6 SP1)
author: dansimp
ms.assetid: 0ceb0897-377e-4754-a7ab-3bc2b5af1452
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2ca56723dedb46ba87890ae62d476ca365b201c6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803026"
---
# <span data-ttu-id="3013f-103">“碎片整理正在运行”对话框 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="3013f-103">Defrag Running Dialog Box (App-V 4.6 SP1)</span></span>


<span data-ttu-id="3013f-104">磁盘碎片整理程序服务正在运行。</span><span class="sxs-lookup"><span data-stu-id="3013f-104">The Disk Defragmenter service is running.</span></span> <span data-ttu-id="3013f-105">磁盘碎片整理程序服务使用系统资源，可能会导致性能下降或增加创建虚拟应用程序包所需的时间。</span><span class="sxs-lookup"><span data-stu-id="3013f-105">The Disk Defragmenter service uses system resources and can cause degradation in performance or increase the time it takes to create virtual application package.</span></span>

<span data-ttu-id="3013f-106">使用以下过程可使磁盘碎片整理程序服务在排序期间停止运行。</span><span class="sxs-lookup"><span data-stu-id="3013f-106">Use the following procedure to stop the Disk Defragmenter service from running during sequencing.</span></span>

1.  <span data-ttu-id="3013f-107">在运行 App-v 排序器的计算机上，单击 "**开始**"，右键单击 "**计算机**"，然后单击 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="3013f-107">On the computer running the App-V Sequencer, click **Start**, right-click **Computer**, and then click **Manage**.</span></span>

2.  <span data-ttu-id="3013f-108">在 "**计算机管理**" 控制台中，双击 "**服务和应用程序**"，然后双击 "**服务**" 以展开 "**服务**"。</span><span class="sxs-lookup"><span data-stu-id="3013f-108">In the **Computer Management** console, double-click **Services and Applications**, and then double-click **Services** to expand **Services**,.</span></span>

3.  <span data-ttu-id="3013f-109">在列表中找到它。</span><span class="sxs-lookup"><span data-stu-id="3013f-109">Locate it in the list.</span></span> <span data-ttu-id="3013f-110">右键单击 "**磁盘碎片整理程序**"，单击 "**其他操作**"，单击 "**停止**" 以停止磁盘碎片整理程序，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="3013f-110">Right-click **Disk Defragmenter**, click **More Actions**, click **Stop** to stop Disk Defragmenter, and then click **OK**.</span></span>

## <span data-ttu-id="3013f-111">相关主题</span><span class="sxs-lookup"><span data-stu-id="3013f-111">Related topics</span></span>


[<span data-ttu-id="3013f-112">对话框 (AppV 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="3013f-112">Dialog Boxes (AppV 4.6 SP1)</span></span>](dialog-boxes--appv-46-sp1-.md)

 

 





