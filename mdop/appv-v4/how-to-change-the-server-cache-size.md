---
title: 如何更改服务器缓存大小
description: 如何更改服务器缓存大小
author: dansimp
ms.assetid: 24e63744-21c3-458e-b137-9592f4fe785c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 92e56a8a28f7a00d71805b497f9e404cca65919d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801652"
---
# <span data-ttu-id="fbbcd-103">如何更改服务器缓存大小</span><span class="sxs-lookup"><span data-stu-id="fbbcd-103">How to Change the Server Cache Size</span></span>


<span data-ttu-id="fbbcd-104">你可以使用以下过程直接从应用程序虚拟化服务器管理控制台更改任何服务器的缓存大小。</span><span class="sxs-lookup"><span data-stu-id="fbbcd-104">You can use the following procedure to change the cache size for any server directly from the Application Virtualization Server Management Console.</span></span>

<span data-ttu-id="fbbcd-105">**注意** 虽然你可以更改缓存大小，除非你的配置明确要求你更改大小，否则建议将缓存大小保留设置为默认值。</span><span class="sxs-lookup"><span data-stu-id="fbbcd-105">**Note** Although you can change the cache size, unless your configuration specifically requires you to change the size, it is recommended that you leave the cache size set to the default values.</span></span>

 

**<span data-ttu-id="fbbcd-106">更改服务器缓存大小</span><span class="sxs-lookup"><span data-stu-id="fbbcd-106">To change the server cache size</span></span>**

1.  <span data-ttu-id="fbbcd-107">单击左窗格中的 "**服务器组**" 节点以展开服务器组列表。</span><span class="sxs-lookup"><span data-stu-id="fbbcd-107">Click the **Server Groups** node in the left pane to expand the list of server groups.</span></span>

2.  <span data-ttu-id="fbbcd-108">在 "**结果**" 窗格中，双击所需的服务器组以显示组中的服务器列表。</span><span class="sxs-lookup"><span data-stu-id="fbbcd-108">In the **Results** pane, double-click the desired server group to display the list of servers in the group.</span></span>

3.  <span data-ttu-id="fbbcd-109">在 "**结果**" 窗格中，右键单击所需服务器，然后选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="fbbcd-109">In the **Results** pane, right-click the desired server and select **Properties**.</span></span>

4.  <span data-ttu-id="fbbcd-110">选择 "**高级**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="fbbcd-110">Select the **Advanced** tab.</span></span>

5.  <span data-ttu-id="fbbcd-111">在服务器缓存的 "**最大内存分配**" 字段中输入一个值，然后在 "**警告内存分配**" 字段中输入阈值警告级别的值。</span><span class="sxs-lookup"><span data-stu-id="fbbcd-111">Enter a value in the **Maximum Memory Allocation** field for the server cache, and enter a value for the threshold warning level in the **Warn Memory Allocation** field.</span></span>

6.  <span data-ttu-id="fbbcd-112">在 "**最大块大小**" 字段中输入值。</span><span class="sxs-lookup"><span data-stu-id="fbbcd-112">Enter a value in the **Maximum Block Size** field.</span></span> <span data-ttu-id="fbbcd-113">此数字必须大于或等于将从服务器流出的最大程序包的最大块大小。</span><span class="sxs-lookup"><span data-stu-id="fbbcd-113">This number must be greater than or equal to the maximum block size of the largest package that will be streamed from the server.</span></span>

7.  <span data-ttu-id="fbbcd-114">单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="fbbcd-114">Click **OK**.</span></span>

## <span data-ttu-id="fbbcd-115">相关主题</span><span class="sxs-lookup"><span data-stu-id="fbbcd-115">Related topics</span></span>


[<span data-ttu-id="fbbcd-116">如何更改服务器端口</span><span class="sxs-lookup"><span data-stu-id="fbbcd-116">How to Change the Server Port</span></span>](how-to-change-the-server-port.md)

[<span data-ttu-id="fbbcd-117">如何在 Server Management Console 中管理服务器</span><span class="sxs-lookup"><span data-stu-id="fbbcd-117">How to Manage Servers in the Server Management Console</span></span>](how-to-manage-servers-in-the-server-management-console.md)

 

 





