---
title: 创建 DaRT 8.0 恢复映像
description: 创建 DaRT 8.0 恢复映像
author: dansimp
ms.assetid: 39001b8e-86c0-45ef-8f34-2d6199f9922d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/21/2017
ms.openlocfilehash: 79ce5859e7d0eacf95124c2a7409ff6c21890d65
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798074"
---
# <span data-ttu-id="485d7-103">创建 DaRT 8.0 恢复映像</span><span class="sxs-lookup"><span data-stu-id="485d7-103">Creating the DaRT 8.0 Recovery Image</span></span>


<span data-ttu-id="485d7-104">安装 Microsoft 诊断和恢复工具集（DaRT）8.0 后，创建一个 DaRT 8.0 恢复映像。</span><span class="sxs-lookup"><span data-stu-id="485d7-104">After installing Microsoft Diagnostics and Recovery Toolset (DaRT) 8.0, you create a DaRT 8.0 recovery image.</span></span> <span data-ttu-id="485d7-105">恢复映像将启动 Windows RE，您可以从中启动 DaRT 工具。</span><span class="sxs-lookup"><span data-stu-id="485d7-105">The recovery image starts Windows RE, from which you can then start the DaRT tools.</span></span> <span data-ttu-id="485d7-106">你可以生成国际标准化组织（ISO）文件和 Windows 映像格式（WIM）映像。</span><span class="sxs-lookup"><span data-stu-id="485d7-106">You can generate International Organization for Standardization (ISO) files and Windows Imaging Format (WIM) images.</span></span> <span data-ttu-id="485d7-107">此外，你可以使用 PowerShell 生成使用在 DaRT 恢复映像向导中选择的设置的脚本。</span><span class="sxs-lookup"><span data-stu-id="485d7-107">In addition, you can use PowerShell to generate scripts that use the settings you select in the DaRT Recovery Image wizard.</span></span> <span data-ttu-id="485d7-108">你可以在以后使用该脚本，使用相同的设置重新生成恢复映像。</span><span class="sxs-lookup"><span data-stu-id="485d7-108">You can use the script later to rebuild recovery images by using the same settings.</span></span> <span data-ttu-id="485d7-109">恢复映像提供各种恢复工具。</span><span class="sxs-lookup"><span data-stu-id="485d7-109">The recovery image provides a variety of recovery tools.</span></span> <span data-ttu-id="485d7-110">有关工具的说明，请参阅[DaRT 8.0 中的工具概述](overview-of-the-tools-in-dart-80-dart-8.md)。</span><span class="sxs-lookup"><span data-stu-id="485d7-110">For a description of the tools, see [Overview of the Tools in DaRT 8.0](overview-of-the-tools-in-dart-80-dart-8.md).</span></span>

<span data-ttu-id="485d7-111">将计算机启动到 DaRT 后，您可以运行不同的 DaRT 工具来尝试诊断和修复计算机。</span><span class="sxs-lookup"><span data-stu-id="485d7-111">After you boot the computer into DaRT, you can run the different DaRT tools to try to diagnose and repair the computer.</span></span> <span data-ttu-id="485d7-112">本部分将引导你完成创建 DaRT 恢复映像的过程，并允许你选择要包含在映像中的工具和功能。</span><span class="sxs-lookup"><span data-stu-id="485d7-112">This section walks you through the process of creating the DaRT recovery image and lets you select the tools and features that you want to include as part of the image.</span></span>

<span data-ttu-id="485d7-113">你可以使用以下两种方法之一创建 DaRT 恢复映像：</span><span class="sxs-lookup"><span data-stu-id="485d7-113">You can create the DaRT recovery image by using either of two methods:</span></span>

-   <span data-ttu-id="485d7-114">使用 DaRT 恢复映像向导，该向导在 Windows 环境中运行。</span><span class="sxs-lookup"><span data-stu-id="485d7-114">Use the DaRT Recovery Image wizard, which runs in a Windows environment.</span></span>

-   <span data-ttu-id="485d7-115">使用所需的值修改示例 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="485d7-115">Modify an example PowerShell script with the values you want.</span></span> <span data-ttu-id="485d7-116">有关详细信息，请参阅[如何使用 PowerShell 脚本创建恢复映像](how-to-use-a-powershell-script-to-create-the-recovery-image-dart-8.md)。</span><span class="sxs-lookup"><span data-stu-id="485d7-116">For more information, see [How to Use a PowerShell Script to Create the Recovery Image](how-to-use-a-powershell-script-to-create-the-recovery-image-dart-8.md).</span></span>

<span data-ttu-id="485d7-117">你可以将 ISO 写入可写 CD 或 DVD，将其保存到 USB 闪存驱动器，或将其保存为可用于从远程分区或恢复分区启动到 DaRT 的格式。</span><span class="sxs-lookup"><span data-stu-id="485d7-117">You can write the ISO to a recordable CD or DVD, save it to a USB flash drive, or save it in a format that you can use to boot into DaRT from a remote partition or from a recovery partition.</span></span>

<span data-ttu-id="485d7-118">创建 ISO 映像后，可以将其刻录到空白 CD 或 DVD （如果计算机具有 CD 或 DVD 驱动器）。</span><span class="sxs-lookup"><span data-stu-id="485d7-118">Once you have created the ISO image, you can burn it onto a blank CD or DVD (if your computer has a CD or DVD drive).</span></span> <span data-ttu-id="485d7-119">如果计算机没有用于此用途的驱动器，则可以使用用于刻录 Cd 或 Dvd 的大多数通用程序。</span><span class="sxs-lookup"><span data-stu-id="485d7-119">If your computer does not have a drive for this purpose, you can use most generic programs that are used to burn CDs or DVDs.</span></span>

## <span data-ttu-id="485d7-120">选择图像体系结构并指定路径</span><span class="sxs-lookup"><span data-stu-id="485d7-120">Select the image architecture and specify the path</span></span>


<span data-ttu-id="485d7-121">在 "Windows 8 媒体" 页面上，选择是创建32位还是64位 DaRT 恢复映像。</span><span class="sxs-lookup"><span data-stu-id="485d7-121">On the Windows 8 Media page, you select whether to create a 32-bit or 64-bit DaRT recovery image.</span></span> <span data-ttu-id="485d7-122">使用32位 Windows 构建32位 DaRT 恢复映像，并使用64位 Windows 构建64位 DaRT 恢复映像。</span><span class="sxs-lookup"><span data-stu-id="485d7-122">Use the 32-bit Windows to build 32-bit DaRT recovery images, and 64-bit Windows to build 64-bit DaRT recovery images.</span></span> <span data-ttu-id="485d7-123">你可以使用一台计算机为两种体系结构类型创建恢复映像，但不能创建一个可在32位和64位体系结构上运行的映像。</span><span class="sxs-lookup"><span data-stu-id="485d7-123">You can use a single computer to create recovery images for both architecture types, but you cannot create one image that works on both 32-bit and 64-bit architectures.</span></span> <span data-ttu-id="485d7-124">你还可以指示 Windows 8 安装媒体的路径。</span><span class="sxs-lookup"><span data-stu-id="485d7-124">You also indicate the path of the Windows 8 installation media.</span></span> <span data-ttu-id="485d7-125">选择与你正在创建的恢复映像之一相匹配的体系结构。</span><span class="sxs-lookup"><span data-stu-id="485d7-125">Choose the architecture that matches the one of the recovery image that you are creating.</span></span>

**<span data-ttu-id="485d7-126">选择图像体系结构并指定路径</span><span class="sxs-lookup"><span data-stu-id="485d7-126">To select the image architecture and specify the path</span></span>**

1.  <span data-ttu-id="485d7-127">在 " **Windows 8 媒体**" 页面上，选择下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="485d7-127">On the **Windows 8 Media** page, select one of the following:</span></span>

    -   <span data-ttu-id="485d7-128">如果要为64位计算机创建恢复映像，请选择 "**创建 x64 （64位） DaRT 映像**"。</span><span class="sxs-lookup"><span data-stu-id="485d7-128">If you are creating a recovery image for 64-bit computers, select **Create x64 (64-bit) DaRT image**.</span></span>

    -   <span data-ttu-id="485d7-129">如果要为32位计算机创建恢复映像，请选择 "**创建 x86 （32位） DaRT 映像**"。</span><span class="sxs-lookup"><span data-stu-id="485d7-129">If you are creating a recovery image for 32-bit computers, select **Create x86 (32-bit) DaRT image**.</span></span>

2.  <span data-ttu-id="485d7-130">在 "**指定 windows 8 &lt; 64 位或32位 &gt; 安装媒体的根路径**" 框中，键入 windows 8 安装文件的路径。</span><span class="sxs-lookup"><span data-stu-id="485d7-130">In the **Specify the root path of the Windows 8 &lt;64-bit or 32-bit&gt; install media** box, type the path of the Windows 8 installation files.</span></span> <span data-ttu-id="485d7-131">使用与正在创建的恢复映像的体系结构相匹配的路径。</span><span class="sxs-lookup"><span data-stu-id="485d7-131">Use a path that matches the architecture of the recovery image that you are creating.</span></span>

3.  <span data-ttu-id="485d7-132">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="485d7-132">Click **Next**.</span></span>

## <span data-ttu-id="485d7-133">选择要包括在恢复映像中的工具</span><span class="sxs-lookup"><span data-stu-id="485d7-133">Select the tools to include on the recovery image</span></span>


<span data-ttu-id="485d7-134">在 "工具" 页面上，您可以选择要包含在恢复映像上的多个工具。</span><span class="sxs-lookup"><span data-stu-id="485d7-134">On the Tools page, you can select numerous tools to include on the recovery image.</span></span> <span data-ttu-id="485d7-135">这些工具将在最终用户启动到 DaRT 映像时可用。</span><span class="sxs-lookup"><span data-stu-id="485d7-135">These tools will be available to end users when they boot into the DaRT image.</span></span> <span data-ttu-id="485d7-136">但是，如果你在创建 DaRT 映像时启用远程连接，则无论你选择将哪些工具包括在映像中，所有工具都将在技术支持人员连接到最终用户的计算机时可用。</span><span class="sxs-lookup"><span data-stu-id="485d7-136">However, if you enable remote connectivity when creating the DaRT image, all of the tools will be available when a help desk worker connects to the end user’s computer, regardless of which tools you chose to include on the image.</span></span>

<span data-ttu-id="485d7-137">若要限制最终用户访问这些工具，但仍保留通过远程连接查看器对工具的完全访问权限，请不要在 "工具" 页面上选择这些工具。</span><span class="sxs-lookup"><span data-stu-id="485d7-137">To restrict end-user access to these tools, but still retain full access to the tools through the Remote Connection Viewer, do not select those tools on the Tools page.</span></span> <span data-ttu-id="485d7-138">最终用户将只能使用远程连接，并且能够看到从恢复映像中排除的任何工具，但不能访问。</span><span class="sxs-lookup"><span data-stu-id="485d7-138">End users will be able to use only Remote Connection and will be able to see, but not access, any tools that you exclude from the recovery image.</span></span>

**<span data-ttu-id="485d7-139">选择要包括在恢复映像中的工具</span><span class="sxs-lookup"><span data-stu-id="485d7-139">To select the tools to include on the recovery image</span></span>**

1.  <span data-ttu-id="485d7-140">在 "**工具**" 页面上，选中要包括在图像上的每个工具旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="485d7-140">On the **Tools** page, select the check box beside each tool that you want to include on the image.</span></span>

2.  <span data-ttu-id="485d7-141">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="485d7-141">Click **Next**.</span></span>

## <span data-ttu-id="485d7-142">选择是否允许帮助台远程连接</span><span class="sxs-lookup"><span data-stu-id="485d7-142">Choose whether to allow remote connectivity by a help desk</span></span>


<span data-ttu-id="485d7-143">在 "远程连接" 页面上，您可以选择启用技术支持人员以在最终用户的计算机上远程连接和运行 DaRT 工具。</span><span class="sxs-lookup"><span data-stu-id="485d7-143">On the Remote Connection page, you can choose to enable a help desk worker to remotely connect to and run the DaRT tools on an end user’s computer.</span></span> <span data-ttu-id="485d7-144">远程连接选项随后在 "诊断和恢复工具集" 窗口中显示为可用选项。</span><span class="sxs-lookup"><span data-stu-id="485d7-144">The remote connectivity option is then shown as an available option in the Diagnostics and Recovery Toolset window.</span></span> <span data-ttu-id="485d7-145">技术支持人员建立远程连接后，他们可以从远程位置从最终用户计算机上运行 DaRT 工具。</span><span class="sxs-lookup"><span data-stu-id="485d7-145">After help desk workers establish a remote connection, they can run the DaRT tools on the end-user computer from a remote location.</span></span>

**<span data-ttu-id="485d7-146">选择是否允许帮助台工作人员进行远程连接</span><span class="sxs-lookup"><span data-stu-id="485d7-146">To choose whether to allow remote connectivity by help desk workers</span></span>**

1.  <span data-ttu-id="485d7-147">在 "**远程连接**" 页面上，选中 "**允许远程连接**" 复选框以允许远程连接，或清除复选框以防止远程连接。</span><span class="sxs-lookup"><span data-stu-id="485d7-147">On the **Remote Connection** page, select the **Allow remote connections** check box to allow remote connections, or clear the check box to prevent remote connections.</span></span>

2.  <span data-ttu-id="485d7-148">如果已清除 "**允许远程连接**" 复选框，请单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="485d7-148">If you cleared the **Allow remote connections** check box, click **Next**.</span></span> <span data-ttu-id="485d7-149">否则，请转到下一步，继续配置远程连接。</span><span class="sxs-lookup"><span data-stu-id="485d7-149">Otherwise, go to the next step to continue configuring remote connectivity.</span></span>

3.  <span data-ttu-id="485d7-150">选择以下其中一项：</span><span class="sxs-lookup"><span data-stu-id="485d7-150">Select one of the following:</span></span>

    -   <span data-ttu-id="485d7-151">让 Windows 选择打开的端口号。</span><span class="sxs-lookup"><span data-stu-id="485d7-151">Let Windows choose an open port number.</span></span>

    -   <span data-ttu-id="485d7-152">指定端口号。</span><span class="sxs-lookup"><span data-stu-id="485d7-152">Specify the port number.</span></span> <span data-ttu-id="485d7-153">如果选择此选项，请在选项下方的字段中输入一个介于1和65535之间的端口号。</span><span class="sxs-lookup"><span data-stu-id="485d7-153">If you select this option, enter a port number between 1 and 65535 in the field beneath the option.</span></span> <span data-ttu-id="485d7-154">将在建立远程连接时使用此端口号。</span><span class="sxs-lookup"><span data-stu-id="485d7-154">This port number will be used when establishing a remote connection.</span></span> <span data-ttu-id="485d7-155">建议端口号为1024或更高，以将冲突可能性降至最低。</span><span class="sxs-lookup"><span data-stu-id="485d7-155">We recommend that the port number be 1024 or higher to minimize the possibility of a conflict.</span></span>

4.  <span data-ttu-id="485d7-156">（可选）在 "**远程连接欢迎**消息" 框中，创建最终用户建立远程连接时接收的自定义消息。</span><span class="sxs-lookup"><span data-stu-id="485d7-156">(Optional) in the **Remote connection welcome** message box, create a customized message that end users receive when they establish a remote connection.</span></span> <span data-ttu-id="485d7-157">该消息最多可以为2048个字符。</span><span class="sxs-lookup"><span data-stu-id="485d7-157">The message can be a maximum of 2048 characters.</span></span>

5.  <span data-ttu-id="485d7-158">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="485d7-158">Click **Next**.</span></span>

    <span data-ttu-id="485d7-159">有关远程运行 DaRT 工具的详细信息，请参阅[如何使用 DaRT 恢复映像恢复远程计算机](how-to-recover-remote-computers-by-using-the-dart-recovery-image-dart-8.md)。</span><span class="sxs-lookup"><span data-stu-id="485d7-159">For more information about running the DaRT tools remotely, see [How to Recover Remote Computers by Using the DaRT Recovery Image](how-to-recover-remote-computers-by-using-the-dart-recovery-image-dart-8.md).</span></span>

## <span data-ttu-id="485d7-160">将驱动程序添加到恢复映像</span><span class="sxs-lookup"><span data-stu-id="485d7-160">Add drivers to the recovery image</span></span>


<span data-ttu-id="485d7-161">在 "高级选项" 页面的 "驱动程序" 选项卡上，你可以添加修复计算机时可能需要的其他设备驱动程序。</span><span class="sxs-lookup"><span data-stu-id="485d7-161">On the Drivers tab of the Advanced Options page, you can add additional device drivers that you may need when repairing a computer.</span></span> <span data-ttu-id="485d7-162">这些通常可能包括 Windows 8 不提供的存储或网络控制器。</span><span class="sxs-lookup"><span data-stu-id="485d7-162">These may typically include storage or network controllers that Windows 8 does not provide.</span></span> <span data-ttu-id="485d7-163">驱动程序是在创建映像时安装的。</span><span class="sxs-lookup"><span data-stu-id="485d7-163">Drivers are installed when the image is created.</span></span>

<span data-ttu-id="485d7-164">**重要提示** 选择要包括的驱动程序时，请注意，DaRT 中不支持无线连接（如蓝牙或 802.11 a/b/n）。</span><span class="sxs-lookup"><span data-stu-id="485d7-164">**Important** When you select drivers to include, be aware that wireless connectivity (such as Bluetooth or 802.11a/b/g/n) is not supported in DaRT.</span></span>

 

**<span data-ttu-id="485d7-165">将驱动程序添加到恢复映像</span><span class="sxs-lookup"><span data-stu-id="485d7-165">To add drivers to the recovery image</span></span>**

1.  <span data-ttu-id="485d7-166">在 "**高级选项**" 页面上，单击 "**驱动程序**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="485d7-166">On the **Advanced Options** page, click the **Drivers** tab.</span></span>

2.  <span data-ttu-id="485d7-167">单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="485d7-167">Click **Add**.</span></span>

3.  <span data-ttu-id="485d7-168">通过浏览找到要为驱动程序添加的文件，然后单击 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="485d7-168">Browse to the file to be added for the driver, and then click **Open**.</span></span>

    <span data-ttu-id="485d7-169">**注意** 驱动程序文件由存储或网络控制器的制造商提供。</span><span class="sxs-lookup"><span data-stu-id="485d7-169">**Note** The driver file is provided by the manufacturer of the storage or network controller.</span></span>

     

4.  <span data-ttu-id="485d7-170">对要包括的每个驱动程序重复步骤2和3。</span><span class="sxs-lookup"><span data-stu-id="485d7-170">Repeat Steps 2 and 3 for every driver that you want to include.</span></span>

5.  <span data-ttu-id="485d7-171">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="485d7-171">Click **Next**.</span></span>

## <span data-ttu-id="485d7-172">将 WinPE 可选程序包添加到恢复映像</span><span class="sxs-lookup"><span data-stu-id="485d7-172">Add WinPE optional packages to the recovery image</span></span>


<span data-ttu-id="485d7-173">在 "高级选项" 页面的 "WinPE" 选项卡上，你可以将 WinPE 可选程序包添加到 DaRT 映像。</span><span class="sxs-lookup"><span data-stu-id="485d7-173">On the WinPE tab of the Advanced Options page, you can add WinPE optional packages to the DaRT image.</span></span> <span data-ttu-id="485d7-174">这些程序包是 Windows ADK 的一部分，它是 DaRT 恢复映像向导的安装先决条件。</span><span class="sxs-lookup"><span data-stu-id="485d7-174">These packages are part of the Windows ADK, which is an installation prerequisite for the DaRT Recovery Image wizard.</span></span> <span data-ttu-id="485d7-175">可以选择的工具全都是可选的。</span><span class="sxs-lookup"><span data-stu-id="485d7-175">The tools that you can select are all optional.</span></span> <span data-ttu-id="485d7-176">将根据你在 "工具" 页面上选择的工具自动添加任何所需的程序包。</span><span class="sxs-lookup"><span data-stu-id="485d7-176">Any required packages are added automatically, based on the tools you selected on the Tools page.</span></span>

<span data-ttu-id="485d7-177">你还可以指定暂存空间的大小。</span><span class="sxs-lookup"><span data-stu-id="485d7-177">You can also specify the size of the scratch space.</span></span> <span data-ttu-id="485d7-178">"暂存空间" 表示为使 DaRT 运行而留出的 RAM 磁盘空间量。</span><span class="sxs-lookup"><span data-stu-id="485d7-178">Scratch space is the amount of RAM disk space that is set aside for DaRT to run.</span></span> <span data-ttu-id="485d7-179">如果最终用户的硬盘不可用，则暂存空间非常有用。</span><span class="sxs-lookup"><span data-stu-id="485d7-179">The scratch space is useful in case the end user’s hard disk is not available.</span></span> <span data-ttu-id="485d7-180">如果你正在运行其他工具和驱动程序，你可能需要增加暂存空间。</span><span class="sxs-lookup"><span data-stu-id="485d7-180">If you are running additional tools and drivers, you may want to increase the scratch space.</span></span>

**<span data-ttu-id="485d7-181">将 WinPE 可选程序包添加到恢复映像</span><span class="sxs-lookup"><span data-stu-id="485d7-181">To add WinPE optional packages to the recovery image</span></span>**

1.  <span data-ttu-id="485d7-182">在 "**高级选项**" 页面上，单击 " **WinPE** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="485d7-182">On the **Advanced Options** page, click the **WinPE** tab.</span></span>

2.  <span data-ttu-id="485d7-183">选中要包括在图像上的每个程序包旁边的复选框，或单击 "**名称**" 复选框以选择所有程序包。</span><span class="sxs-lookup"><span data-stu-id="485d7-183">Select the check box beside each package that you want to include on the image, or click the **Name** check box to select all of the packages.</span></span>

3.  <span data-ttu-id="485d7-184">在 "**暂存空间**" 字段中，选择要分配用于运行 DART 的 RAM 磁盘空间量（如果最终用户的硬盘不可用）。</span><span class="sxs-lookup"><span data-stu-id="485d7-184">In the **Scratch Space** field, select the amount of RAM disk space to allocate for running DaRT in case the end user’s hard disk is not available.</span></span>

4.  <span data-ttu-id="485d7-185">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="485d7-185">Click **Next**.</span></span>

## <span data-ttu-id="485d7-186">为崩溃分析程序添加调试工具</span><span class="sxs-lookup"><span data-stu-id="485d7-186">Add the debugging tools for Crash Analyzer</span></span>


<span data-ttu-id="485d7-187">如果在 ISO 映像中包含崩溃分析器工具，则还必须包括 Windows 调试工具。</span><span class="sxs-lookup"><span data-stu-id="485d7-187">If you include the Crash Analyzer tool in the ISO image, you must also include the Debugging Tools for Windows.</span></span> <span data-ttu-id="485d7-188">在 "高级选项" 页面的 "崩溃分析程序" 选项卡上，输入 Windows 8 调试工具的路径，崩溃分析程序使用这些工具分析内存转储文件。</span><span class="sxs-lookup"><span data-stu-id="485d7-188">On the Crash Analyzer tab of the Advanced Options page, you enter the path of the Windows 8 Debugging Tools, which Crash Analyzer uses to analyze memory dump files.</span></span> <span data-ttu-id="485d7-189">你可以使用运行 DaRT 恢复映像向导的计算机上的工具，也可以使用最终用户计算机上的工具。</span><span class="sxs-lookup"><span data-stu-id="485d7-189">You can use the tools that are on the computer where you are running the DaRT Recovery Image wizard, or you can use the tools that are on the end-user computer.</span></span> <span data-ttu-id="485d7-190">如果你决定使用最终用户计算机上的工具，请记住你诊断的每台计算机必须安装调试工具。</span><span class="sxs-lookup"><span data-stu-id="485d7-190">If you decide to use the tools on the end-user computer, remember that every computer that you diagnose must have the Debugging Tools installed.</span></span>

<span data-ttu-id="485d7-191">如果安装了 Microsoft Windows 软件开发工具包（SDK）或 Microsoft Windows 开发工具包（WDK），则默认情况下会将 Windows 8 调试工具添加到恢复映像，并自动填充调试工具的路径。</span><span class="sxs-lookup"><span data-stu-id="485d7-191">If you installed the Microsoft Windows Software Development Kit (SDK) or the Microsoft Windows Development Kit (WDK), the Windows 8 Debugging Tools are added to the recovery image by default, and the path to the Debugging Tools is automatically filled in.</span></span> <span data-ttu-id="485d7-192">如果文件位于默认文件路径所指示的位置以外的位置，则可以更改 Windows 8 调试工具的路径。</span><span class="sxs-lookup"><span data-stu-id="485d7-192">You can change the path of the Windows 8 Debugging Tools if the files are located somewhere other than the location indicated by the default file path.</span></span> <span data-ttu-id="485d7-193">通过向导中的链接，你可以下载并安装 Windows 调试工具（如果尚未安装）。</span><span class="sxs-lookup"><span data-stu-id="485d7-193">A link in the wizard lets you download and install debugging tools for Windows if they are not already installed.</span></span>

<span data-ttu-id="485d7-194">若要下载 Windows 调试工具，请参阅[Windows 调试工具](https://go.microsoft.com/fwlink/?LinkId=266248)。</span><span class="sxs-lookup"><span data-stu-id="485d7-194">To download the Windows Debugging Tools, see [Debugging Tools for Windows](https://go.microsoft.com/fwlink/?LinkId=266248).</span></span> <span data-ttu-id="485d7-195">将调试工具安装到默认位置。</span><span class="sxs-lookup"><span data-stu-id="485d7-195">Install the Debugging Tools to the default location.</span></span>

<span data-ttu-id="485d7-196">**注意** DaRT 向导将检查注册表项中的工具 `HKLM\Software\Microsoft\Windows Kits\Installed Roots\WindowsDebuggersRoot` 。</span><span class="sxs-lookup"><span data-stu-id="485d7-196">**Note** The DaRT wizard checks for the tools in the `HKLM\Software\Microsoft\Windows Kits\Installed Roots\WindowsDebuggersRoot` registry key.</span></span> <span data-ttu-id="485d7-197">如果注册表值不在该位置，向导将根据您的系统体系结构查找下列位置之一：</span><span class="sxs-lookup"><span data-stu-id="485d7-197">If the registry value is not there, the wizard looks in one of the following locations, depending on your system architecture:</span></span>

`%ProgramFilesX86%\Windows Kits\8.0\Debuggers\x64`

`%ProgramFilesX86%\Windows Kits\8.0\Debuggers\x86`

 

**<span data-ttu-id="485d7-198">为崩溃分析程序添加调试工具</span><span class="sxs-lookup"><span data-stu-id="485d7-198">To add the debugging tools for Crash Analyzer</span></span>**

1.  <span data-ttu-id="485d7-199">在 "**高级选项**" 页面上，单击 "**崩溃分析器**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="485d7-199">On the **Advanced Options** page, click the **Crash Analyzer** tab.</span></span>

2.  <span data-ttu-id="485d7-200">可选单击 "**下载调试工具**" 以下载 Windows 调试工具。</span><span class="sxs-lookup"><span data-stu-id="485d7-200">(Optional) Click **Download the Debugging Tools** to download the Debugging Tools for Windows.</span></span>

3.  <span data-ttu-id="485d7-201">选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="485d7-201">Select one of the following options:</span></span>

    -   <span data-ttu-id="485d7-202">**包括 Windows 8 &lt; 64 位或32位 &gt; 调试工具**。</span><span class="sxs-lookup"><span data-stu-id="485d7-202">**Include the Windows 8 &lt;64-bit or 32-bit&gt; Debugging Tools**.</span></span> <span data-ttu-id="485d7-203">如果选择此选项，请通过浏览找到并选择工具的位置（如果路径尚未显示）。</span><span class="sxs-lookup"><span data-stu-id="485d7-203">If you select this option, browse to and select the location of the tools if the path is not already displaying.</span></span>

    -   <span data-ttu-id="485d7-204">**使用正在调试的系统中的调试工具**。</span><span class="sxs-lookup"><span data-stu-id="485d7-204">**Use the Debugging Tools from the system that is being debugged**.</span></span> <span data-ttu-id="485d7-205">如果选择此选项，在问题计算机上找不到 Windows 调试工具时，崩溃分析器将无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="485d7-205">If you select this option, the Crash Analyzer will not work if the Debugging Tools for Windows are not found on the problem computer.</span></span>

4.  <span data-ttu-id="485d7-206">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="485d7-206">Click **Next**.</span></span>

## <span data-ttu-id="485d7-207">添加 Defender 工具的定义</span><span class="sxs-lookup"><span data-stu-id="485d7-207">Add definitions for the Defender tool</span></span>


<span data-ttu-id="485d7-208">在 "高级选项" 页面的 "Defender" 选项卡上，添加定义，由 Defender 工具用于确定尝试在计算机上安装、运行或更改设置的软件是不需要还是恶意软件。</span><span class="sxs-lookup"><span data-stu-id="485d7-208">On the Defender tab of the Advanced Options page, you add definitions, which are used by the Defender tool to determine whether software that is trying to install, run, or change settings on a computer is unwanted or malicious software.</span></span>

**<span data-ttu-id="485d7-209">为 Defender 工具添加定义</span><span class="sxs-lookup"><span data-stu-id="485d7-209">To add definitions for the Defender tool</span></span>**

1.  <span data-ttu-id="485d7-210">在 "**高级选项**" 页面上，单击 " **Defender** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="485d7-210">On the **Advanced Options** page, click the **Defender** tab.</span></span>

2.  <span data-ttu-id="485d7-211">选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="485d7-211">Select one of the following options:</span></span>

    -   <span data-ttu-id="485d7-212">**下载最新的定义（推荐）** -定义更新会自动启动，并且定义将添加到 DaRT 恢复映像。</span><span class="sxs-lookup"><span data-stu-id="485d7-212">**Download the latest definitions (Recommended)** – The definition update starts automatically, and the definitions are added to the DaRT recovery image.</span></span> <span data-ttu-id="485d7-213">建议使用此选项，以帮助避免这些定义可能不可用的情况。</span><span class="sxs-lookup"><span data-stu-id="485d7-213">This option is recommended to help you avoid cases where the definitions might not be available.</span></span> <span data-ttu-id="485d7-214">必须连接到 Internet 才能下载定义。</span><span class="sxs-lookup"><span data-stu-id="485d7-214">You must be connected to the Internet to download the definitions.</span></span>

    -   <span data-ttu-id="485d7-215">**稍后下载定义**-不会将定义包括在 dart 恢复映像中，你将需要从运行 dart 的计算机下载定义。</span><span class="sxs-lookup"><span data-stu-id="485d7-215">**Download the definitions later** – Definitions will not be included in the DaRT recovery image, and you will need to download the definitions from the computer that is running DaRT.</span></span>

        <span data-ttu-id="485d7-216">如果你决定不在恢复映像上包含最新的定义，或者在你准备好使用 Defender 时恢复映像中包含的定义不再是最新的，请按照 Defender 中提供的说明在开始扫描之前获取最新的定义。</span><span class="sxs-lookup"><span data-stu-id="485d7-216">If you decide not to include the latest definitions on the recovery image, or if the definitions included on the recovery image are no longer current by the time that you are ready to use Defender, obtain the latest definitions before you begin a scan by following the instructions that are provided in Defender.</span></span>

        <span data-ttu-id="485d7-217">**重要提示** 如果没有定义，则无法扫描。</span><span class="sxs-lookup"><span data-stu-id="485d7-217">**Important** You cannot scan if there are no definitions.</span></span>

         

3.  <span data-ttu-id="485d7-218">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="485d7-218">Click **Next**.</span></span>

## <span data-ttu-id="485d7-219">选择要创建的恢复图像文件的类型</span><span class="sxs-lookup"><span data-stu-id="485d7-219">Select the types of recovery image files to create</span></span>


<span data-ttu-id="485d7-220">在 "创建图像" 页面上，为恢复映像选择输出文件夹，输入一个图像名称，然后选择要创建的 DaRT 恢复图像文件的类型。</span><span class="sxs-lookup"><span data-stu-id="485d7-220">On the Create Image page, you choose an output folder for the recovery image, enter an image name, and select the types of DaRT recovery image files to create.</span></span> <span data-ttu-id="485d7-221">在恢复映像创建过程中，将解压缩 Windows 源文件，并将 DaRT 文件复制到该文件，然后将该映像 "重新打包" 为您在此页面上选择的文件格式。</span><span class="sxs-lookup"><span data-stu-id="485d7-221">During the recovery image creation process, Windows source files are unpacked, DaRT files are copied to it, and the image is then “re-packed” into the file formats that you select on this page.</span></span>

<span data-ttu-id="485d7-222">可用的图像文件类型包括：</span><span class="sxs-lookup"><span data-stu-id="485d7-222">The available image file types are:</span></span>

-   <span data-ttu-id="485d7-223">**Windows 映像文件（WIM）** -用于将 DaRT 部署到预启动执行环境（PXE）或本地分区。</span><span class="sxs-lookup"><span data-stu-id="485d7-223">**Windows Imaging File (WIM)** - used to deploy DaRT to a preboot execution environment (PXE) or local partition).</span></span>

-   <span data-ttu-id="485d7-224">**ISO 映像文件**-用于部署到 CD 或 DVD，或用于在虚拟机（VM）中使用的文件。</span><span class="sxs-lookup"><span data-stu-id="485d7-224">**ISO image file** – used to deploy to CD or DVD, or for use in virtual machines (VM)s).</span></span> <span data-ttu-id="485d7-225">该向导要求 ISO 映像具有 .iso 文件扩展名，因为刻录 CD 或 DVD 的大多数程序都需要该扩展。</span><span class="sxs-lookup"><span data-stu-id="485d7-225">The wizard requires that the ISO image have an .iso file name extension because most programs that burn a CD or DVD require that extension.</span></span> <span data-ttu-id="485d7-226">如果不指定其他位置，将在桌面上创建使用名称 DaRT8 的 ISO 图像。</span><span class="sxs-lookup"><span data-stu-id="485d7-226">If you do not specify a different location, the ISO image is created on your desktop with the name DaRT8.ISO.</span></span>

-   <span data-ttu-id="485d7-227">**PowerShell 脚本**–创建一个 DaRT 恢复映像，其命令实际上提供的选项与你可以使用 DaRT 恢复映像向导选择的选项基本相同。</span><span class="sxs-lookup"><span data-stu-id="485d7-227">**PowerShell script** – creates a DaRT recovery image with commands that provide essentially the same options that you can select by using the DaRT Recovery Image wizard.</span></span> <span data-ttu-id="485d7-228">该脚本还允许你在 DaRT 恢复映像中添加或更改文件。</span><span class="sxs-lookup"><span data-stu-id="485d7-228">The script also enables you to add or changes files in the DaRT recovery image.</span></span>

<span data-ttu-id="485d7-229">如果您在此页面上选择 "编辑图像" 复选框，则可以在创建图像过程中自定义恢复图像。</span><span class="sxs-lookup"><span data-stu-id="485d7-229">If you select the Edit Image check box on this page, you can customize the recovery image during the image creation process.</span></span> <span data-ttu-id="485d7-230">例如，你可以更改 "winpeshl.ini" 文件以创建自定义启动顺序或添加第三方工具。</span><span class="sxs-lookup"><span data-stu-id="485d7-230">For example, you can change the “winpeshl.ini” file to create a custom startup order or to add third-party tools.</span></span>

**<span data-ttu-id="485d7-231">选择要创建的恢复图像文件的类型</span><span class="sxs-lookup"><span data-stu-id="485d7-231">To select the types of recovery image files to create</span></span>**

1.  <span data-ttu-id="485d7-232">在 "**创建图像**" 页面上，单击 "**浏览**" 以选择图像文件的输出文件夹。</span><span class="sxs-lookup"><span data-stu-id="485d7-232">On the **Create Image** page, click **Browse** to choose the output folder for the image file.</span></span>

    <span data-ttu-id="485d7-233">**注意** 图像的大小会有所不同，具体取决于你选择的工具和你在向导中添加的文件。</span><span class="sxs-lookup"><span data-stu-id="485d7-233">**Note** The size of the image will vary, depending on the tools that you select and the files that you add in the wizard.</span></span>

     

2.  <span data-ttu-id="485d7-234">在 "**映像名称**" 框中，输入 DaRT 恢复映像的名称，或接受默认名称 DaRT8。</span><span class="sxs-lookup"><span data-stu-id="485d7-234">In the **Image name** box, enter a name for the DaRT recovery image, or accept the default name, which is DaRT8.</span></span>

    <span data-ttu-id="485d7-235">向导将在输出路径中使用此名称创建一个子文件夹。</span><span class="sxs-lookup"><span data-stu-id="485d7-235">The wizard creates a subfolder in the output path by this name.</span></span>

3.  <span data-ttu-id="485d7-236">选择要创建的图像文件的类型。</span><span class="sxs-lookup"><span data-stu-id="485d7-236">Select the types of image files that you want to create.</span></span>

4.  <span data-ttu-id="485d7-237">选择下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="485d7-237">Choose one of the following:</span></span>

    -   <span data-ttu-id="485d7-238">若要在创建图像文件之前更改恢复映像中的文件，请选中 "**编辑图像**" 复选框，然后单击 "**准备**"。</span><span class="sxs-lookup"><span data-stu-id="485d7-238">To change the files in the recovery image before you create the image files, select the **Edit Image** check box, and then click **Prepare**.</span></span>

    -   <span data-ttu-id="485d7-239">若要在不更改文件的情况下创建恢复映像，请单击 "**创建**"。</span><span class="sxs-lookup"><span data-stu-id="485d7-239">To create the recovery image without changing the files, click **Create**.</span></span>

5.  

    <span data-ttu-id="485d7-240">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="485d7-240">Click **Next**.</span></span>

## <span data-ttu-id="485d7-241">编辑恢复图像文件</span><span class="sxs-lookup"><span data-stu-id="485d7-241">Edit the recovery image files</span></span>


<span data-ttu-id="485d7-242">只有选中 "创建图像" 页面上的 "编辑图像" 复选框，才能编辑恢复图像。</span><span class="sxs-lookup"><span data-stu-id="485d7-242">You can edit the recovery image only if you selected the Edit Image check box on the Create Image page.</span></span> <span data-ttu-id="485d7-243">在恢复映像准备好进行编辑之后，你可以在创建可启动媒体之前添加和修改恢复镜像文件。</span><span class="sxs-lookup"><span data-stu-id="485d7-243">After the recovery image has been prepared for editing, you can add and modify the recovery image files before creating the bootable media.</span></span> <span data-ttu-id="485d7-244">例如，你可以创建启动的自定义顺序、添加各种第三方工具等。</span><span class="sxs-lookup"><span data-stu-id="485d7-244">For example, you can create a custom order for startup, add various third-party tools, and so on.</span></span>

**<span data-ttu-id="485d7-245">编辑恢复图像文件</span><span class="sxs-lookup"><span data-stu-id="485d7-245">To edit the recovery image files</span></span>**

1.  <span data-ttu-id="485d7-246">在 "**编辑图像**" 页面上，单击 "在 Windows 资源管理器中**打开**"。</span><span class="sxs-lookup"><span data-stu-id="485d7-246">On the **Edit Image** page, click **Open** in Windows Explorer.</span></span>

2.  <span data-ttu-id="485d7-247">在对话框中列出的文件夹中创建一个子文件夹。</span><span class="sxs-lookup"><span data-stu-id="485d7-247">Create a subfolder in the folder that is listed in the dialog box.</span></span>

3.  <span data-ttu-id="485d7-248">将所需的文件复制到新子文件夹，或删除不需要的文件。</span><span class="sxs-lookup"><span data-stu-id="485d7-248">Copy the files that you want to the new subfolder, or remove files that you don’t want.</span></span>

4.  <span data-ttu-id="485d7-249">单击 "**创建**" 开始创建恢复映像。</span><span class="sxs-lookup"><span data-stu-id="485d7-249">Click **Create** to start creating the recovery image.</span></span>

## <span data-ttu-id="485d7-250">生成恢复图像文件</span><span class="sxs-lookup"><span data-stu-id="485d7-250">Generate the recovery image files</span></span>


<span data-ttu-id="485d7-251">在 "生成文件" 页面上，将为你在 "创建映像" 页面上选择的文件类型生成 DaRT 恢复映像。</span><span class="sxs-lookup"><span data-stu-id="485d7-251">On the Generate Files page, the DaRT recovery image is generated for the file types that you selected on the Create Image page.</span></span>

**<span data-ttu-id="485d7-252">生成恢复图像文件</span><span class="sxs-lookup"><span data-stu-id="485d7-252">To generate the recovery image files</span></span>**

-   <span data-ttu-id="485d7-253">在 "**生成文件**" 页面上，单击 "**下一步**" 以生成恢复图像文件。</span><span class="sxs-lookup"><span data-stu-id="485d7-253">On the **Generate Files** page, click **Next** to generate the recovery image files.</span></span>

## <span data-ttu-id="485d7-254">将恢复映像复制到 CD、DVD 或 USB</span><span class="sxs-lookup"><span data-stu-id="485d7-254">Copy the recovery image to a CD, DVD, or USB</span></span>


<span data-ttu-id="485d7-255">在 "创建可启动媒体" 页面上，你可以选择将图像文件复制到 CD、DVD 或 USB 闪存驱动器（UFD）。</span><span class="sxs-lookup"><span data-stu-id="485d7-255">On the Create Bootable Media page, you can optionally copy the image file to a CD, DVD, or USB flash drive (UFD).</span></span> <span data-ttu-id="485d7-256">您也可以通过重新启动向导，从该页面创建其他可启动媒体。</span><span class="sxs-lookup"><span data-stu-id="485d7-256">You can also create additional bootable media from this page by restarting the wizard.</span></span>

<span data-ttu-id="485d7-257">**注意** 此工具本身不支持预启动执行环境（PXE）和本地映像部署，因为它们需要其他企业工具，如 System Center Configuration Manager 服务器和 Microsoft 开发工具包。</span><span class="sxs-lookup"><span data-stu-id="485d7-257">**Note** The Preboot execution environment (PXE) and local image deployment are not supported natively by this tool since they require additional enterprise tools, such as System Center Configuration Manager server and Microsoft Development Toolkit.</span></span>

 

**<span data-ttu-id="485d7-258">将恢复映像复制到 CD、DVD 或 USB</span><span class="sxs-lookup"><span data-stu-id="485d7-258">To copy the recovery image to a CD, DVD, or USB</span></span>**

1.  <span data-ttu-id="485d7-259">在 "**创建可启动媒体**" 页面上，选择要复制的 iso 文件。</span><span class="sxs-lookup"><span data-stu-id="485d7-259">On the **Create Bootable Media** page, select the iso file that you want to copy.</span></span>

2.  <span data-ttu-id="485d7-260">插入 CD、DVD 或 USB，然后选择驱动器。</span><span class="sxs-lookup"><span data-stu-id="485d7-260">Insert a CD, DVD, or USB, and then select the drive.</span></span>

    <span data-ttu-id="485d7-261">**注意** 如果无法识别驱动器且安装了新驱动器，则可以单击 "**刷新**" 以强制向导更新可用的驱动器列表。</span><span class="sxs-lookup"><span data-stu-id="485d7-261">**Note** If a drive is not recognized and you install a new drive, you can click **Refresh** to force the wizard to update the list of available drives.</span></span>

     

3.  <span data-ttu-id="485d7-262">单击 "**创建可启动介质**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="485d7-262">Click the **Create Bootable Media** button.</span></span>

4.  <span data-ttu-id="485d7-263">若要创建另一个恢复映像，请单击 "重新启动"，如果已完成创建所需的所有媒体，请单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="485d7-263">To create another recovery image, click Restart, or click **Close** if you have finished creating all of the media that you want.</span></span>

## <span data-ttu-id="485d7-264">相关主题</span><span class="sxs-lookup"><span data-stu-id="485d7-264">Related topics</span></span>


[<span data-ttu-id="485d7-265">DaRT 8.0 中的工具概述</span><span class="sxs-lookup"><span data-stu-id="485d7-265">Overview of the Tools in DaRT 8.0</span></span>](overview-of-the-tools-in-dart-80-dart-8.md)

[<span data-ttu-id="485d7-266">部署 DaRT 8.0</span><span class="sxs-lookup"><span data-stu-id="485d7-266">Deploying DaRT 8.0</span></span>](deploying-dart-80-dart-8.md)

 

 





