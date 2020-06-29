---
title: 如何更改缓存大小和驱动器号指定
description: 如何更改缓存大小和驱动器号指定
author: dansimp
ms.assetid: e7d7b635-079e-41aa-a5e6-655f33b4e317
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cf972f114845064ecf3027cf52d1a038dc6a5118
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801656"
---
# <span data-ttu-id="dc13e-103">如何更改缓存大小和驱动器号指定</span><span class="sxs-lookup"><span data-stu-id="dc13e-103">How to Change the Cache Size and the Drive Letter Designation</span></span>


<span data-ttu-id="dc13e-104">你可以直接从应用程序虚拟化客户端管理控制台中的**应用程序虚拟化**节点更改缓存大小和驱动器号标识。</span><span class="sxs-lookup"><span data-stu-id="dc13e-104">You can change the cache size and drive letter designation directly from the **Application Virtualization** node in the Application Virtualization Client Management Console.</span></span>

**<span data-ttu-id="dc13e-105">注意</span><span class="sxs-lookup"><span data-stu-id="dc13e-105">Note</span></span>**  
<span data-ttu-id="dc13e-106">设置缓存大小后，它不能变得更小。</span><span class="sxs-lookup"><span data-stu-id="dc13e-106">After the cache size has been set, it cannot be made smaller.</span></span>



**<span data-ttu-id="dc13e-107">更改缓存大小</span><span class="sxs-lookup"><span data-stu-id="dc13e-107">To change the cache size</span></span>**

1.  <span data-ttu-id="dc13e-108">右键单击 "**应用程序虚拟化**" 节点，然后从弹出菜单中选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="dc13e-108">Right-click the **Application Virtualization** node, and select **Properties** from the pop-up menu.</span></span>

2.  <span data-ttu-id="dc13e-109">选择 "**属性**" 对话框上的 "**文件系统**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="dc13e-109">Select the **File System** tab on the **Properties** dialog box.</span></span> <span data-ttu-id="dc13e-110">在 "**客户端缓存配置设置**" 部分中，单击下列单选按钮之一，选择如何管理缓存空间：</span><span class="sxs-lookup"><span data-stu-id="dc13e-110">In the **Client Cache Configuration Settings** section, click one of the following radio buttons to choose how to manage the cache space:</span></span>

    **<span data-ttu-id="dc13e-111">重要提示</span><span class="sxs-lookup"><span data-stu-id="dc13e-111">Important</span></span>**  
    <span data-ttu-id="dc13e-112">如果你选择 "**使用空闲磁盘空间阈值**" 设置，则你输入的值会将缓存大小设置为总磁盘大小减去你输入的可用磁盘空间阈值。</span><span class="sxs-lookup"><span data-stu-id="dc13e-112">If you select the **Use free disk space threshold** setting, the value you enter will set the cache size to the total disk size minus the free disk space threshold number you entered.</span></span> <span data-ttu-id="dc13e-113">如果你随后希望使用 "**使用最大缓存大小**" 设置还原，则必须指定比现有缓存大小更大的数字。</span><span class="sxs-lookup"><span data-stu-id="dc13e-113">If you then want revert to using the **Use maximum cache size** setting, you must specify a larger number than the existing cache size.</span></span> <span data-ttu-id="dc13e-114">否则，将显示 "新大小必须大于现有缓存大小" 的错误。</span><span class="sxs-lookup"><span data-stu-id="dc13e-114">Otherwise, the error “New size must be larger than the existing cache size” will appear.</span></span>



~~~
-   **Use maximum cache size**

    Enter a numeric value from 100 to 1,048,576 (1 TB) in the **Maximum size (MB)** field to specify the maximum size of the cache. The value shown in **Reserved Cache Size** indicates the amount of cache in use.

-   **Use free disk space threshold**

    Enter a numeric value to specify the amount of free disk space, in MB, that the cache must leave available on the disk. This allows the cache to grow until the amount of free disk space reaches this limit. The value shown in **Free disk space remaining** indicates how much disk space is unused.
~~~

3. <span data-ttu-id="dc13e-115">单击 **"确定" 或 "** **应用**" 更改设置。</span><span class="sxs-lookup"><span data-stu-id="dc13e-115">Click **OK** or **Apply** to change the setting.</span></span>

**<span data-ttu-id="dc13e-116">更改驱动器号指定</span><span class="sxs-lookup"><span data-stu-id="dc13e-116">To change the drive letter designation</span></span>**

1.  <span data-ttu-id="dc13e-117">右键单击 "**应用程序虚拟化**" 节点，然后从弹出菜单中选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="dc13e-117">Right-click the **Application Virtualization** node, and select **Properties** from the pop-up menu.</span></span>

2.  <span data-ttu-id="dc13e-118">在 "**属性**" 对话框中的 "**文件系统**" 选项卡上的 "**要使用的驱动器**" 字段中，从可用的驱动器号下拉列表中选择所需的驱动器号。</span><span class="sxs-lookup"><span data-stu-id="dc13e-118">On the **File System** tab in the **Properties** dialog box, in the **Drive to use** field, select the desired drive letter from the drop-down list of available drive letters.</span></span> <span data-ttu-id="dc13e-119">重新启动计算机后，此设置才有效。</span><span class="sxs-lookup"><span data-stu-id="dc13e-119">This setting becomes effective when the computer is rebooted.</span></span>

3.  <span data-ttu-id="dc13e-120">单击 **"确定" 或 "** **应用**" 更改设置。</span><span class="sxs-lookup"><span data-stu-id="dc13e-120">Click **OK** or **Apply** to change the setting.</span></span>

## <span data-ttu-id="dc13e-121">相关主题</span><span class="sxs-lookup"><span data-stu-id="dc13e-121">Related topics</span></span>


[<span data-ttu-id="dc13e-122">如何在 Application Virtualization Client Management Console 中配置客户端</span><span class="sxs-lookup"><span data-stu-id="dc13e-122">How to Configure the Client in the Application Virtualization Client Management Console</span></span>](how-to-configure-the-client-in-the-application-virtualization-client-management-console.md)









