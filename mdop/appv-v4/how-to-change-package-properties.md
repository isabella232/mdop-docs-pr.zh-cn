---
title: 如何更改程序包属性
description: 如何更改程序包属性
author: dansimp
ms.assetid: 6050916a-d4fe-4dac-8f2a-47308dbbf481
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d2427a2651f3941f967c171ae7854facc62b4aa9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801659"
---
# <span data-ttu-id="2ad48-103">如何更改程序包属性</span><span class="sxs-lookup"><span data-stu-id="2ad48-103">How to Change Package Properties</span></span>


<span data-ttu-id="2ad48-104">你可以使用以下过程修改应用程序虚拟化程序包名称及其关联的注释。</span><span class="sxs-lookup"><span data-stu-id="2ad48-104">You can use the following procedures to modify an Application Virtualization package name and its associated comments.</span></span>

<span data-ttu-id="2ad48-105">如果这是第一次创建程序包，则还可以更改顺序参数块大小，以确定序列化应用程序包如何从应用程序虚拟化服务器传输到应用程序虚拟化桌面客户端。</span><span class="sxs-lookup"><span data-stu-id="2ad48-105">If this is the first time the package has been created, you can also change the sequencing parameter block size, which determines how a sequenced application package is streamed from an Application Virtualization Server to an Application Virtualization Desktop Client.</span></span>

<span data-ttu-id="2ad48-106">**注意** 选择块大小时，请考虑 SFT 文件的大小和你的网络带宽。</span><span class="sxs-lookup"><span data-stu-id="2ad48-106">**Note** When selecting a block size, consider the size of the SFT file and your network bandwidth.</span></span> <span data-ttu-id="2ad48-107">块大小较小的文件需要较长时间才能通过网络传输，但带宽占用较少。</span><span class="sxs-lookup"><span data-stu-id="2ad48-107">A file with a smaller block size takes longer to stream over the network, but it is less bandwidth intensive.</span></span> <span data-ttu-id="2ad48-108">块大小较大的文件可能会更快地传输，但它们会占用更多的网络带宽。</span><span class="sxs-lookup"><span data-stu-id="2ad48-108">Files with larger block sizes might stream faster, but they use more network bandwidth.</span></span> <span data-ttu-id="2ad48-109">通过实验，你可以发现网络上的流式处理应用程序的最佳块大小。</span><span class="sxs-lookup"><span data-stu-id="2ad48-109">Through experimentation, you can discover the optimum block size for streaming applications on your network.</span></span>

 

<span data-ttu-id="2ad48-110">"**属性**" 选项卡上的程序包属性的其余部分将自动生成，并且不能在此选项卡上进行修改。</span><span class="sxs-lookup"><span data-stu-id="2ad48-110">The remainder of the package properties on the **Properties** tab is automatically generated and cannot be modified on this tab.</span></span>

**<span data-ttu-id="2ad48-111">更改程序包名称或批注</span><span class="sxs-lookup"><span data-stu-id="2ad48-111">To change the package name or comments</span></span>**

1.  <span data-ttu-id="2ad48-112">单击 "**属性**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="2ad48-112">Click the **Properties** tab.</span></span>

2.  <span data-ttu-id="2ad48-113">在 "**程序包名称**" 文本框中，输入或编辑程序包所使用的单个名称，该名称可以包含多个应用程序。</span><span class="sxs-lookup"><span data-stu-id="2ad48-113">In the **Package Name** text box, enter or edit the single name used for the package, which can contain multiple applications.</span></span>

3.  <span data-ttu-id="2ad48-114">在 "**批注**" 文本框中，选择性地输入或编辑任何批注。</span><span class="sxs-lookup"><span data-stu-id="2ad48-114">In the **Comments** text box, optionally enter or edit any comments.</span></span> <span data-ttu-id="2ad48-115">建议的最佳做法是提供有关程序包和排序的详细信息。</span><span class="sxs-lookup"><span data-stu-id="2ad48-115">The suggested best practice is to provide detail information about the package and sequencing.</span></span>

4.  <span data-ttu-id="2ad48-116">从 "**文件**" 菜单中，选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="2ad48-116">From the **File** menu, select **Save**.</span></span>

**<span data-ttu-id="2ad48-117">更改块大小</span><span class="sxs-lookup"><span data-stu-id="2ad48-117">To change the block size</span></span>**

1.  <span data-ttu-id="2ad48-118">单击 "**属性**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="2ad48-118">Click the **Properties** tab.</span></span>

2.  <span data-ttu-id="2ad48-119">在 "**块大小**" 下拉列表中，选择 " **4 kb**"、" **16 KB**"、" **32 kb**" 或 " **64 kb**"。</span><span class="sxs-lookup"><span data-stu-id="2ad48-119">On the **Block Size** drop-down list, select **4 KB**, **16 KB**, **32 KB**, or **64 KB**.</span></span>

3.  <span data-ttu-id="2ad48-120">从 "**文件**" 菜单中，选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="2ad48-120">From the **File** menu, select **Save**.</span></span>

## <span data-ttu-id="2ad48-121">相关主题</span><span class="sxs-lookup"><span data-stu-id="2ad48-121">Related topics</span></span>


[<span data-ttu-id="2ad48-122">关于“属性”选项卡</span><span class="sxs-lookup"><span data-stu-id="2ad48-122">About the Properties Tab</span></span>](about-the-properties-tab.md)

[<span data-ttu-id="2ad48-123">Sequencer 控制台</span><span class="sxs-lookup"><span data-stu-id="2ad48-123">Sequencer Console</span></span>](sequencer-console.md)

 

 





