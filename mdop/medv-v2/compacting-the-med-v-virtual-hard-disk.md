---
title: 压缩 MED-V 虚拟硬盘
description: 压缩 MED-V 虚拟硬盘
author: dansimp
ms.assetid: 5e6122d1-9847-4b33-adab-594919eec3c5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f71aefb1e4e901078b4d0a421065b7bd5acdf0ee
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803336"
---
# <span data-ttu-id="8f090-103">压缩 MED-V 虚拟硬盘</span><span class="sxs-lookup"><span data-stu-id="8f090-103">Compacting the MED-V Virtual Hard Disk</span></span>


<span data-ttu-id="8f090-104">尽管它是可选的，但你可以在配置 Windows 虚拟 PC 映像之前压缩虚拟硬盘（VHD）以回收空磁盘空间并减小 VHD 的大小。</span><span class="sxs-lookup"><span data-stu-id="8f090-104">Although it is optional, you can compact the virtual hard disk (VHD) to reclaim empty disk space and reduce the size of the VHD before you configure the Windows Virtual PC image.</span></span>

<span data-ttu-id="8f090-105">**重要提示** 在继续操作之前，请创建 Windows XP 映像的备份副本。</span><span class="sxs-lookup"><span data-stu-id="8f090-105">**Important** Before you proceed, create a backup copy of your Windows XP image.</span></span>

 

**<span data-ttu-id="8f090-106">准备虚拟硬盘</span><span class="sxs-lookup"><span data-stu-id="8f090-106">Preparing the Virtual Hard Disk</span></span>**

1.  <span data-ttu-id="8f090-107">打开 Windows XP 映像。</span><span class="sxs-lookup"><span data-stu-id="8f090-107">Open your Windows XP image.</span></span>

    <span data-ttu-id="8f090-108">单击 "**开始**"，单击 "**所有程序**"，单击 " **windows 虚拟 Pc**"，单击 " **Windows 虚拟 pc**"，然后双击 windows XP 映像。</span><span class="sxs-lookup"><span data-stu-id="8f090-108">Click **Start**, click **All Programs**, click **Windows Virtual PC**, click **Windows Virtual PC**, then double-click your Windows XP image.</span></span>

2.  <span data-ttu-id="8f090-109">清除 DLL 缓存。</span><span class="sxs-lookup"><span data-stu-id="8f090-109">Clear the DLL cache.</span></span>

    1.  <span data-ttu-id="8f090-110">在虚拟机中的命令提示符处，键入**sfc/cachesize = 1**。</span><span class="sxs-lookup"><span data-stu-id="8f090-110">At a command prompt in the virtual machine, type **sfc /cachesize=1**.</span></span>

    2.  <span data-ttu-id="8f090-111">重新启动虚拟机。</span><span class="sxs-lookup"><span data-stu-id="8f090-111">Restart the virtual machine.</span></span>

    3.  <span data-ttu-id="8f090-112">在虚拟机中的命令提示符处，键入 " **sfc/purgecache**"。</span><span class="sxs-lookup"><span data-stu-id="8f090-112">At a command prompt in the virtual machine, type **sfc /purgecache**.</span></span>

3.  <span data-ttu-id="8f090-113">删除不必要的文件，例如 uninstallers、临时文件、日志文件、页面文件、共享文件夹等。</span><span class="sxs-lookup"><span data-stu-id="8f090-113">Delete unnecessary files, such as uninstallers, temp files, log files, page files, shared folders, and so on.</span></span>

4.  <span data-ttu-id="8f090-114">关闭系统还原。</span><span class="sxs-lookup"><span data-stu-id="8f090-114">Turn off System Restore.</span></span> <span data-ttu-id="8f090-115">您也可以在 Sysprep.inf 文件中指定此步骤。</span><span class="sxs-lookup"><span data-stu-id="8f090-115">You can also specify this step in your Sysprep.inf file.</span></span>

    1.  <span data-ttu-id="8f090-116">在 "**控制面板**" 中，双击 "**系统**"，然后选择 "**系统还原**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="8f090-116">In **Control Panel**, double-click **System**, and then select the **System Restore** tab.</span></span>

    2.  <span data-ttu-id="8f090-117">选择 "**关闭系统还原**"，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="8f090-117">Select **Turn off System Restore**, and then click **OK**.</span></span>

5.  <span data-ttu-id="8f090-118">设置最大事件日志大小并清除所有事件。</span><span class="sxs-lookup"><span data-stu-id="8f090-118">Set maximum event log sizes and clear all events.</span></span>

    1.  <span data-ttu-id="8f090-119">打开 "事件查看器"。</span><span class="sxs-lookup"><span data-stu-id="8f090-119">Open the event viewer.</span></span>

        <span data-ttu-id="8f090-120">单击 "**开始**"，单击 "**控制面板**"，双击 "**管理工具**"，然后双击 "**事件查看器**"。</span><span class="sxs-lookup"><span data-stu-id="8f090-120">Click **Start**, click **Control Panel**, double-click **Administrative Tools**, then double-click **Event Viewer**.</span></span>

    2.  <span data-ttu-id="8f090-121">右键单击 "**应用程序**"，然后单击 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="8f090-121">Right-click **Application**, and click **Properties**.</span></span>

    3.  <span data-ttu-id="8f090-122">在 "**日志大小**" 区域中，将**日志大小的最大值**设置为512kb，然后选择 "**根据需要覆盖事件**"。</span><span class="sxs-lookup"><span data-stu-id="8f090-122">In the **Log Size** area, set **Maximum Log Size** to 512KB and then select **Overwrite events as needed**.</span></span>

    4.  <span data-ttu-id="8f090-123">单击 "**清除日志**"。</span><span class="sxs-lookup"><span data-stu-id="8f090-123">Click **Clear Log**.</span></span> <span data-ttu-id="8f090-124">在出现的 "**事件查看器**" 对话框中，单击 "**否**"。</span><span class="sxs-lookup"><span data-stu-id="8f090-124">In the **Event Viewer** dialog box that appears, click **No**.</span></span>

    5.  <span data-ttu-id="8f090-125">在 "**属性**" 窗口中，单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="8f090-125">In the **Properties** window, click **OK**.</span></span>

    6.  <span data-ttu-id="8f090-126">对于**安全**和**系统**日志，请重复步骤 a 到 e。</span><span class="sxs-lookup"><span data-stu-id="8f090-126">Repeat steps a through e for the **Security** and **System** logs.</span></span>

6.  <span data-ttu-id="8f090-127">运行 "磁盘清理" 工具。</span><span class="sxs-lookup"><span data-stu-id="8f090-127">Run the Disk Cleanup Tool.</span></span>

    <span data-ttu-id="8f090-128">依次单击 "**开始**"、"**所有程序**"、"**附件**"、"**系统工具**"，然后单击 "**磁盘清理**"。</span><span class="sxs-lookup"><span data-stu-id="8f090-128">Click **Start**, click **All Programs**, click **Accessories**, click **System Tools**, and then click **Disk Cleanup**.</span></span>

7.  <span data-ttu-id="8f090-129">根据需要为你的应用程序配置你的页面文件。</span><span class="sxs-lookup"><span data-stu-id="8f090-129">Configure your page file as needed for your applications.</span></span>

    1.  <span data-ttu-id="8f090-130">在 "**控制面板**" 中，双击 "**系统**"，然后选择 "**高级**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="8f090-130">In **Control Panel**, double-click **System**, and then select the **Advanced** tab.</span></span>

    2.  <span data-ttu-id="8f090-131">在 "**性能**" 区域中，单击 "**设置**"。</span><span class="sxs-lookup"><span data-stu-id="8f090-131">In the **Performance** area, click **Settings**.</span></span>

    3.  <span data-ttu-id="8f090-132">在 "**虚拟内存**" 区域中，单击 "**更改**"。</span><span class="sxs-lookup"><span data-stu-id="8f090-132">In the **Virtual Memory** area, click **Change**.</span></span>

    4.  <span data-ttu-id="8f090-133">配置页面文件设置。</span><span class="sxs-lookup"><span data-stu-id="8f090-133">Configure your page file settings.</span></span>

8.  <span data-ttu-id="8f090-134">关闭 Windows XP 映像。</span><span class="sxs-lookup"><span data-stu-id="8f090-134">Shut down the Windows XP image.</span></span>

**<span data-ttu-id="8f090-135">对虚拟硬盘进行碎片整理和预压缩</span><span class="sxs-lookup"><span data-stu-id="8f090-135">Defragmenting and Pre-compacting the Virtual Hard Disk</span></span>**

1.  <span data-ttu-id="8f090-136">在运行 Windows 7 的主机上的 **"控制面板**" 中，单击 "**管理工具**"，双击 "**计算机管理**"，然后单击 "**磁盘管理**"。</span><span class="sxs-lookup"><span data-stu-id="8f090-136">In **Control Panel** on the host computer that is running Windows 7, click **Administrative Tools**, double-click **Computer Management**, then click **Disk Management**.</span></span>

2.  <span data-ttu-id="8f090-137">通过使用磁盘管理控制台，附加（装载）虚拟硬盘，然后对磁盘进行碎片整理。</span><span class="sxs-lookup"><span data-stu-id="8f090-137">By using the Disk Management Console, attach (mount) the virtual hard disk and then defragment the disk.</span></span>

3.  <span data-ttu-id="8f090-138">通过使用 ISO 提取工具，提取位于 \\Program Files\\Windows 虚拟 PC\\Integration 组件文件夹中的 precompact。</span><span class="sxs-lookup"><span data-stu-id="8f090-138">By using an ISO extraction tool, extract the precompact.iso located in the \\Program Files\\Windows Virtual PC\\Integration Components folder.</span></span>

4.  <span data-ttu-id="8f090-139">使用 precompact.exe 程序压缩 Windows XP 虚拟硬盘。</span><span class="sxs-lookup"><span data-stu-id="8f090-139">Use the precompact.exe program to compress the Windows XP virtual hard disk.</span></span>

5.  <span data-ttu-id="8f090-140">通过使用 "磁盘管理" 控制台，分离虚拟硬盘。</span><span class="sxs-lookup"><span data-stu-id="8f090-140">By using the Disk Management Console, detach the virtual hard disk.</span></span>

**<span data-ttu-id="8f090-141">压缩虚拟硬盘</span><span class="sxs-lookup"><span data-stu-id="8f090-141">Compacting the Virtual Hard Disk</span></span>**

1.  <span data-ttu-id="8f090-142">打开 Windows 虚拟电脑。</span><span class="sxs-lookup"><span data-stu-id="8f090-142">Open Windows Virtual PC.</span></span>

    <span data-ttu-id="8f090-143">单击 "**开始**"，单击 "**所有程序**"，单击 " **windows 虚拟 pc**"，然后单击 " **windows 虚拟 pc**"。</span><span class="sxs-lookup"><span data-stu-id="8f090-143">Click **Start**, click **All Programs**, click **Windows Virtual PC**, then click **Windows Virtual PC**.</span></span>

2.  <span data-ttu-id="8f090-144">右键单击您的 Windows XP 映像，然后选择 "**设置**"。</span><span class="sxs-lookup"><span data-stu-id="8f090-144">Right-click your Windows XP image and select **Settings**.</span></span>

3.  <span data-ttu-id="8f090-145">单击与你的 Windows XP 映像对应的**硬盘**，然后单击 "**修改**"。</span><span class="sxs-lookup"><span data-stu-id="8f090-145">Click **Hard Disk** for the one that corresponds to your Windows XP image, and then click **Modify**.</span></span>

4.  <span data-ttu-id="8f090-146">单击 "**压缩虚拟硬盘**"。</span><span class="sxs-lookup"><span data-stu-id="8f090-146">Click **Compact virtual hard disk**.</span></span>

5.  <span data-ttu-id="8f090-147">单击 "**压缩**"，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="8f090-147">Click **Compact** and then click **OK**.</span></span>

<span data-ttu-id="8f090-148">创建压缩的虚拟硬盘的备份副本。</span><span class="sxs-lookup"><span data-stu-id="8f090-148">Create a backup copy of your compacted virtual hard disk.</span></span>

## <span data-ttu-id="8f090-149">相关主题</span><span class="sxs-lookup"><span data-stu-id="8f090-149">Related topics</span></span>


[<span data-ttu-id="8f090-150">为 MED-V 配置 Windows Virtual PC 映像</span><span class="sxs-lookup"><span data-stu-id="8f090-150">Configuring a Windows Virtual PC Image for MED-V</span></span>](configuring-a-windows-virtual-pc-image-for-med-v.md)

[<span data-ttu-id="8f090-151">MED-V 的技术参考</span><span class="sxs-lookup"><span data-stu-id="8f090-151">Technical Reference for MED-V</span></span>](technical-reference-for-med-v.md)

 

 





