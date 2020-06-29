---
title: 如何使用 DaRT 恢复映像向导来创建恢复映像
description: 如何使用 DaRT 恢复映像向导来创建恢复映像
author: dansimp
ms.assetid: 1b8ef983-fff9-4d75-a2f6-53120c5c00c9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 49253a8c0bf9c9073b57712acc773e4a57e31d72
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803265"
---
# <span data-ttu-id="9acfc-103">如何使用 DaRT 恢复映像向导来创建恢复映像</span><span class="sxs-lookup"><span data-stu-id="9acfc-103">How to Use the DaRT Recovery Image Wizard to Create the Recovery Image</span></span>


<span data-ttu-id="9acfc-104">Microsoft 诊断和恢复工具集（DaRT）7包含在 Windows 中用于创建可启动的国际标准化组织（ISO）映像的**DaRT 恢复映像向导**。</span><span class="sxs-lookup"><span data-stu-id="9acfc-104">Microsoft Diagnostics and Recovery Toolset (DaRT)7 includes the **DaRT Recovery Image Wizard** that is used in Windows to create a bootable International Organization for Standardization (ISO) image.</span></span> <span data-ttu-id="9acfc-105">ISO 图像是表示 CD 的原始内容的文件。</span><span class="sxs-lookup"><span data-stu-id="9acfc-105">An ISO image is a file that represents the raw contents of a CD.</span></span>

<span data-ttu-id="9acfc-106">**DaRT 恢复映像向导**需要以下信息：</span><span class="sxs-lookup"><span data-stu-id="9acfc-106">The **DaRT Recovery Image Wizard** requires the following information:</span></span>

-   <span data-ttu-id="9acfc-107">**启动映像**-必须提供创建 DaRT 恢复映像所需的 WINDOWS 7 DVD 或 windows 7 源文件的路径。</span><span class="sxs-lookup"><span data-stu-id="9acfc-107">**Boot Image**˚˚You must provide the path of a Windows 7 DVD or Windows 7 source files that are required to create the DaRT recovery image.</span></span>

-   <span data-ttu-id="9acfc-108">**工具选择**"您可以选择要包含在 DaRT 恢复映像中的工具。</span><span class="sxs-lookup"><span data-stu-id="9acfc-108">**Tool Selection**˚˚You can select the tools to include on the DaRT recovery image.</span></span>

-   <span data-ttu-id="9acfc-109">**远程连接**您可以选择是否希望 DaRT 恢复映像包括在支持人员和最终用户计算机之间建立远程连接的能力。</span><span class="sxs-lookup"><span data-stu-id="9acfc-109">**Remote Connections**˚˚You can select whether you want the DaRT recovery image to include the ability to establish a remote connection between the helpdesk and the end-user computer.</span></span>

-   <span data-ttu-id="9acfc-110">**适用于 windows 的调试工具**-系统要求你提供 Windows 调试工具的位置。</span><span class="sxs-lookup"><span data-stu-id="9acfc-110">**Debugging Tools for Windows**˚˚You are asked to provide the location of the Debugging Tools for Windows.</span></span>

-   <span data-ttu-id="9acfc-111">**独立系统 Sweeper 的定义**您可以决定是否在创建恢复映像或稍后下载定义时下载最新的定义。</span><span class="sxs-lookup"><span data-stu-id="9acfc-111">**Definitions for Standalone System Sweeper**˚˚You can decide whether to download the latest definitions at the time that you create the recovery image or download the definitions later.</span></span>

-   <span data-ttu-id="9acfc-112">**驱动程序**？系统会询问你是否要将驱动程序添加到 ISO 映像。</span><span class="sxs-lookup"><span data-stu-id="9acfc-112">**Drivers**˚˚You are asked whether you want to add drivers to the ISO image.</span></span>

-   <span data-ttu-id="9acfc-113">**其他文件**？您可以将文件添加到可以帮助诊断问题的 ISO 映像。</span><span class="sxs-lookup"><span data-stu-id="9acfc-113">**Additional Files**˚˚You can add files to the ISO image that might help diagnose problems.</span></span>

-   <span data-ttu-id="9acfc-114">**Iso 镜像位置**？系统会要求你指定 ISO 映像所在的位置。</span><span class="sxs-lookup"><span data-stu-id="9acfc-114">**ISO Image Location**˚˚You are asked to specify where the ISO image should be located.</span></span>

-   <span data-ttu-id="9acfc-115">**Cd/DVD 驱动器**？系统将要求您指定是否应使用 CD 或 dvd 驱动器刻录 CD 或 dvd。</span><span class="sxs-lookup"><span data-stu-id="9acfc-115">**CD/DVD Drive**˚˚You are asked to specify whether the CD or DVD drive should be used to burn the CD or DVD.</span></span>

<span data-ttu-id="9acfc-116">**注意** ISO 映像大小可能会有所不同，具体取决于在**DaRT 恢复映像向导**中选择的工具。</span><span class="sxs-lookup"><span data-stu-id="9acfc-116">**Note** The ISO image size can vary, depending on the tools that were selected in the **DaRT Recovery Image Wizard**.</span></span>

 

## <span data-ttu-id="9acfc-117">使用 DaRT 恢复映像向导创建恢复映像</span><span class="sxs-lookup"><span data-stu-id="9acfc-117">To create the recovery image using the DaRT Recovery Image Wizard</span></span>


<span data-ttu-id="9acfc-118">按照以下说明使用**Dart 恢复映像向导**创建 dart 恢复映像。</span><span class="sxs-lookup"><span data-stu-id="9acfc-118">Follow these instructions to use the **DaRT Recovery Image Wizard** to create the DaRT recovery image.</span></span>

### <span data-ttu-id="9acfc-119">选择要包含在 DaRT 恢复映像上的工具</span><span class="sxs-lookup"><span data-stu-id="9acfc-119">To select the tools to include on the DaRT recovery image</span></span>

<span data-ttu-id="9acfc-120">**DaRT 恢复映像向导**显示一个**工具选择**对话框。</span><span class="sxs-lookup"><span data-stu-id="9acfc-120">The **DaRT Recovery Image Wizard** presents a **Tool Selection** dialog box.</span></span> <span data-ttu-id="9acfc-121">通过突出显示工具，然后单击 "**启用**" 或 "**禁用**" 按钮，可以从要包括在 DaRT 恢复映像中的工具列表中选择或删除工具。</span><span class="sxs-lookup"><span data-stu-id="9acfc-121">You can select or remove tools from the list of tools to be included on the DaRT recovery image by highlighting a tool and then clicking the **Enable** or **Disable** buttons.</span></span>

<span data-ttu-id="9acfc-122">选择要包括在恢复映像中的所有工具后，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="9acfc-122">After you have selected all the tools that you want to include on the recovery image, click **Next**.</span></span>

### <span data-ttu-id="9acfc-123">添加允许远程连接的选项</span><span class="sxs-lookup"><span data-stu-id="9acfc-123">To add the option to allow remote connectivity</span></span>

<span data-ttu-id="9acfc-124">你可以选择 "**允许远程连接**" 复选框以在 "**诊断和恢复工具集**" 窗口中提供选项，以便在帮助程序代理和最终用户计算机之间建立远程连接。</span><span class="sxs-lookup"><span data-stu-id="9acfc-124">You can select the **Allow remote connections** check box to provide the option in the **Diagnostics and Recovery Toolset** window to establish a remote connection between the helpdesk agent and an end-user computer.</span></span> <span data-ttu-id="9acfc-125">在帮助台代理建立远程连接后，他们可以从远程位置从最终用户计算机上运行 DaRT 工具。</span><span class="sxs-lookup"><span data-stu-id="9acfc-125">After a helpdesk agent establishes a remote connection, they can run the DaRT tools on the end-user computer from a remote location.</span></span>

<span data-ttu-id="9acfc-126">你可以选中 "**指定端口号"** 复选框以输入建立远程连接时将使用的特定端口号。</span><span class="sxs-lookup"><span data-stu-id="9acfc-126">You can select the **Specify the port number** check box to enter a specific port number that will be used when establishing a remote connection.</span></span> <span data-ttu-id="9acfc-127">你可以指定一个介于1和65535之间的端口号。</span><span class="sxs-lookup"><span data-stu-id="9acfc-127">You can specify a port number between 1 and 65535.</span></span> <span data-ttu-id="9acfc-128">建议端口号为1024或更高，以将冲突可能性降至最低。</span><span class="sxs-lookup"><span data-stu-id="9acfc-128">We recommend that the port number be 1024 or higher to minimize the possibility of a conflict.</span></span>

<span data-ttu-id="9acfc-129">你还可以创建最终用户建立远程连接时将收到的自定义消息。</span><span class="sxs-lookup"><span data-stu-id="9acfc-129">You can also create a customized message that an end user will receive when they establish a remote connection.</span></span> <span data-ttu-id="9acfc-130">该消息最多可以为2048个字符。</span><span class="sxs-lookup"><span data-stu-id="9acfc-130">The message can be a maximum of 2048 characters.</span></span>

<span data-ttu-id="9acfc-131">有关远程运行 DaRT 工具的详细信息，请参阅[如何使用 DaRT 恢复映像恢复远程计算机](how-to-recover-remote-computers-using-the-dart-recovery-image-dart-7.md)。</span><span class="sxs-lookup"><span data-stu-id="9acfc-131">For more information about remotely running the DaRT tools, see [How to Recover Remote Computers Using the DaRT Recovery Image](how-to-recover-remote-computers-using-the-dart-recovery-image-dart-7.md).</span></span>

### <span data-ttu-id="9acfc-132">将 Windows 调试工具添加到 DaRT 恢复映像</span><span class="sxs-lookup"><span data-stu-id="9acfc-132">To add the Debugging Tools for Windows to the DaRT recovery image</span></span>

<span data-ttu-id="9acfc-133">在**DaRT 恢复映像向导**的 "**崩溃分析器**" 对话框中，系统会要求你指定 Windows 调试工具的位置。</span><span class="sxs-lookup"><span data-stu-id="9acfc-133">In the **Crash Analyzer** dialog box of the **DaRT Recovery Image Wizard**, you are asked to specify the location of the Debugging Tools for Windows.</span></span> <span data-ttu-id="9acfc-134">如果您没有这些工具的副本，则可以从 Microsoft 下载它们。</span><span class="sxs-lookup"><span data-stu-id="9acfc-134">If you do not have a copy of the tools, you can download them from Microsoft.</span></span> <span data-ttu-id="9acfc-135">向导中提供了指向下载页面的以下链接：[下载并安装适用于 Windows 的调试工具](https://go.microsoft.com/fwlink/?LinkId=99934)。</span><span class="sxs-lookup"><span data-stu-id="9acfc-135">The following link to the download page is provided in the wizard: [Download and Install Debugging Tools for Windows](https://go.microsoft.com/fwlink/?LinkId=99934).</span></span>

<span data-ttu-id="9acfc-136">你可以在运行**DaRT 恢复映像向导**的计算机上指定调试工具的位置，也可以决定使用位于目标计算机上的工具。</span><span class="sxs-lookup"><span data-stu-id="9acfc-136">You can either specify the location of the debugging tools on the computer where you are running the **DaRT Recovery Image Wizard**, or you can decide to use the tools that are located on the destination computer.</span></span> <span data-ttu-id="9acfc-137">如果你决定在另一台计算机上使用副本，则必须确保在你诊断崩溃的每台计算机上安装工具。</span><span class="sxs-lookup"><span data-stu-id="9acfc-137">If you decide to use a copy on another computer, you must make sure that the tools are installed on each computer on which you are diagnosing a crash.</span></span>

<span data-ttu-id="9acfc-138">**注意** 如果你在 ISO 映像中包含**崩溃分析器**，我们建议你还包括适用于 Windows 的调试工具。</span><span class="sxs-lookup"><span data-stu-id="9acfc-138">**Note** If you include the **Crash Analyzer** in the ISO image, we recommend that you also include the Debugging Tools for Windows.</span></span>

 

<span data-ttu-id="9acfc-139">请按照以下步骤添加适用于 Windows 的调试工具：</span><span class="sxs-lookup"><span data-stu-id="9acfc-139">Follow these steps to add the Debugging Tools for Windows:</span></span>

1.  <span data-ttu-id="9acfc-140">可选单击超链接以下载适用于 Windows 的调试工具。</span><span class="sxs-lookup"><span data-stu-id="9acfc-140">(Optional) Click the hyperlink to download the Debugging Tools for Windows.</span></span>

2.  <span data-ttu-id="9acfc-141">选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="9acfc-141">Select one of the following options:</span></span>

    -   <span data-ttu-id="9acfc-142">**在以下位置使用 Windows 调试工具**。</span><span class="sxs-lookup"><span data-stu-id="9acfc-142">**Use the Debugging Tools for Windows in the following location**.</span></span> <span data-ttu-id="9acfc-143">如果选择此选项，则可以浏览到工具的位置。</span><span class="sxs-lookup"><span data-stu-id="9acfc-143">If you select this option, you can browse to the location of the tools.</span></span>

    -   <span data-ttu-id="9acfc-144">**在要修复的系统上找到用于 Windows 的调试工具**。</span><span class="sxs-lookup"><span data-stu-id="9acfc-144">**Locate the Debugging Tools for Windows on the system that you are repairing**.</span></span> <span data-ttu-id="9acfc-145">如果选择此选项，在问题计算机上找不到 Windows 调试工具时，**崩溃分析器**将无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="9acfc-145">If you select this option, the **Crash Analyzer** will not work if the Debugging Tools for Windows are not found on the problem computer.</span></span>

3.  <span data-ttu-id="9acfc-146">完成后，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="9acfc-146">After you have finished, click **Next**.</span></span>

### <span data-ttu-id="9acfc-147">将独立系统 Sweeper 的定义添加到 DaRT 恢复映像</span><span class="sxs-lookup"><span data-stu-id="9acfc-147">To add definitions for Standalone System Sweeper to the DaRT recovery image</span></span>

<span data-ttu-id="9acfc-148">定义是已知恶意软件和其他潜在的垃圾软件的存储库。</span><span class="sxs-lookup"><span data-stu-id="9acfc-148">Definitions are a repository of known malware and other potentially unwanted software.</span></span> <span data-ttu-id="9acfc-149">由于正在不断开发恶意软件，因此**独立系统 Sweeper**依赖于当前定义来确定尝试在计算机上安装、运行或更改设置的软件是潜在的有害软件还是恶意软件。</span><span class="sxs-lookup"><span data-stu-id="9acfc-149">Because malware is being continually developed, **Standalone System Sweeper** relies on current definitions to determine whether software that is trying to install, run, or change settings on a computer is potentially unwanted or malicious software.</span></span>

<span data-ttu-id="9acfc-150">若要包括 DaRT 恢复映像中的最新定义（推荐），请单击 **"是，下载最新的定义。**</span><span class="sxs-lookup"><span data-stu-id="9acfc-150">To include the latest definitions in the DaRT recovery image (recommended), click **Yes, download the latest definitions.**</span></span> <span data-ttu-id="9acfc-151">定义更新将自动启动。</span><span class="sxs-lookup"><span data-stu-id="9acfc-151">The definition update starts automatically.</span></span> <span data-ttu-id="9acfc-152">必须连接到 Internet 才能完成此过程。</span><span class="sxs-lookup"><span data-stu-id="9acfc-152">You must be connected to the Internet to complete this process.</span></span>

<span data-ttu-id="9acfc-153">若要跳过定义更新，请单击 "**否，稍后手动下载定义"**。</span><span class="sxs-lookup"><span data-stu-id="9acfc-153">To skip the definition update, click **No, manually download definitions later**.</span></span> <span data-ttu-id="9acfc-154">DaRT 恢复映像中将不包含定义。</span><span class="sxs-lookup"><span data-stu-id="9acfc-154">Definitions will not be included in the DaRT recovery image.</span></span>

<span data-ttu-id="9acfc-155">如果你决定不在恢复映像上包含最新的定义，或者恢复映像中包含的定义在你准备好使用**独立系统 Sweeper**时不再是最新的，请按照**独立系统 Sweeper**中提供的说明，在开始扫描之前获取最新的定义。</span><span class="sxs-lookup"><span data-stu-id="9acfc-155">If you decide not to include the latest definitions on the recovery image, or if the definitions included on the recovery image are no longer current by the time that you are ready to use **Standalone System Sweeper**, obtain the latest definitions before you begin a scan by following the instructions that are provided in the **Standalone System Sweeper**.</span></span>

<span data-ttu-id="9acfc-156">**重要提示** 如果没有定义，则无法扫描。</span><span class="sxs-lookup"><span data-stu-id="9acfc-156">**Important** You cannot scan if there are no definitions.</span></span>

 

<span data-ttu-id="9acfc-157">完成后，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="9acfc-157">After you have finished, click **Next**.</span></span>

### <span data-ttu-id="9acfc-158">将驱动程序添加到 DaRT 恢复映像</span><span class="sxs-lookup"><span data-stu-id="9acfc-158">To add drivers to the DaRT recovery image</span></span>

<span data-ttu-id="9acfc-159">**小心** 默认情况下，当你将驱动程序添加到 DaRT 恢复映像时，位于该文件夹中的所有其他文件和子文件夹将添加到恢复映像中。</span><span class="sxs-lookup"><span data-stu-id="9acfc-159">**Caution** By default, when you add a driver to the DaRT recovery image, all additional files and subfolders that are located in that folder are added into the recovery image.</span></span> <span data-ttu-id="9acfc-160">有关详细信息，请参阅[DaRT 7.0 的疑难解答](troubleshooting-dart-70-new-ia.md)。</span><span class="sxs-lookup"><span data-stu-id="9acfc-160">For more information, see [Troubleshooting DaRT 7.0](troubleshooting-dart-70-new-ia.md).</span></span>

 

<span data-ttu-id="9acfc-161">你应该在恢复映像上包括修复计算机时可能需要的 DaRT7 的其他驱动程序。</span><span class="sxs-lookup"><span data-stu-id="9acfc-161">You should include additional drivers on the recovery image for DaRT7 that you may need when repairing a computer.</span></span> <span data-ttu-id="9acfc-162">这些通常包括 Windows DVD 中未包含的存储或网络控制器。</span><span class="sxs-lookup"><span data-stu-id="9acfc-162">These may typically include storage or network controllers that are not included on the Windows DVD.</span></span>

<span data-ttu-id="9acfc-163">**重要提示** 选择要包括的驱动程序时，请注意，DaRT 中不支持无线连接（如蓝牙或 802.11 a/b/n）。</span><span class="sxs-lookup"><span data-stu-id="9acfc-163">**Important** When you select drivers to include, be aware that wireless connectivity (such as Bluetooth or 802.11a/b/g/n) is not supported in DaRT.</span></span>

 

**<span data-ttu-id="9acfc-164">将存储或网络控制器驱动程序添加到恢复映像</span><span class="sxs-lookup"><span data-stu-id="9acfc-164">To add a storage or network controller driver to the recovery image</span></span>**

1.  <span data-ttu-id="9acfc-165">在**DaRT 恢复映像向导**的 "**其他驱动程序**" 对话框中，单击 "**添加设备**"。</span><span class="sxs-lookup"><span data-stu-id="9acfc-165">In the **Additional Drivers** dialog box of the **DaRT Recovery Image Wizard**, click **Add Device**.</span></span>

2.  <span data-ttu-id="9acfc-166">通过浏览找到要为驱动程序添加的文件，然后单击 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="9acfc-166">Browse to the file to be added for the driver, and then click **Open**.</span></span>

    <span data-ttu-id="9acfc-167">**注意** **驱动程序**文件由存储或网络控制器的制造商提供。</span><span class="sxs-lookup"><span data-stu-id="9acfc-167">**Note** The **driver** file is provided by the manufacturer of the storage or network controller.</span></span>

     

3.  <span data-ttu-id="9acfc-168">对要包括的每个驱动程序重复步骤1和2。</span><span class="sxs-lookup"><span data-stu-id="9acfc-168">Repeat Steps 1 and 2 for every driver that you want to include.</span></span>

4.  <span data-ttu-id="9acfc-169">完成后，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="9acfc-169">After you have finished, click **Next**.</span></span>

### <span data-ttu-id="9acfc-170">将文件添加到 DaRT 恢复映像</span><span class="sxs-lookup"><span data-stu-id="9acfc-170">To add files to the DaRT recovery image</span></span>

<span data-ttu-id="9acfc-171">按照以下步骤将文件添加到恢复映像，以便你可以使用它们来诊断计算机问题。</span><span class="sxs-lookup"><span data-stu-id="9acfc-171">Follow these steps to add files to the recovery image so that you can use them to diagnose computer problems.</span></span>

1.  <span data-ttu-id="9acfc-172">在**DaRT 恢复映像向导**的 "**其他文件**" 对话框中，单击 "**显示文件**"。</span><span class="sxs-lookup"><span data-stu-id="9acfc-172">In the **Additional Files** dialog box of the **DaRT Recovery Image Wizard**, click **Show Files**.</span></span> <span data-ttu-id="9acfc-173">这将打开一个 "资源管理器" 窗口，显示包含共享文件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="9acfc-173">This opens an Explorer window that displays the folder that holds the shared files.</span></span>

2.  <span data-ttu-id="9acfc-174">在对话框中列出的文件夹中创建一个子文件夹。</span><span class="sxs-lookup"><span data-stu-id="9acfc-174">Create a subfolder in the folder that is listed in the dialog box.</span></span>

3.  <span data-ttu-id="9acfc-175">将所需的文件复制到新的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="9acfc-175">Copy the files that you want to the new subfolder.</span></span>

4.  <span data-ttu-id="9acfc-176">完成后，单击 "**下一步"。**</span><span class="sxs-lookup"><span data-stu-id="9acfc-176">After you have finished, click **Next.**</span></span>

### <span data-ttu-id="9acfc-177">选择包含 DaRT 恢复映像的 ISO 的位置</span><span class="sxs-lookup"><span data-stu-id="9acfc-177">To select a location for the ISO that contains the DaRT recovery image</span></span>

<span data-ttu-id="9acfc-178">按照以下步骤指定创建 ISO 映像的位置：</span><span class="sxs-lookup"><span data-stu-id="9acfc-178">Follow these steps to specify the location where the ISO image is created:</span></span>

1.  <span data-ttu-id="9acfc-179">在 " **DaRT 恢复映像向导**" 的 "**创建启动映像**" 对话框中，单击 "**浏览**"。</span><span class="sxs-lookup"><span data-stu-id="9acfc-179">In the **Create Startup Image** dialog box of the **DaRT Recovery Image Wizard**, click **Browse**.</span></span>

2.  <span data-ttu-id="9acfc-180">浏览到 "**另存为**" 窗口中的首选位置，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="9acfc-180">Browse to the preferred location in the **Save As** window, and then click **Save**.</span></span>

3.  <span data-ttu-id="9acfc-181">完成后，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="9acfc-181">After you have finished, click **Next**.</span></span>

<span data-ttu-id="9acfc-182">ISO 映像的大小会有所不同，具体取决于你选择的工具和你在向导中添加的文件。</span><span class="sxs-lookup"><span data-stu-id="9acfc-182">The size of the ISO image will vary, depending on the tools that you select and the files that you add in the wizard.</span></span>

<span data-ttu-id="9acfc-183">向导要求 ISO 映像具有 **.iso**文件扩展名，因为刻录 CD 或 DVD 的大多数程序都需要该扩展。</span><span class="sxs-lookup"><span data-stu-id="9acfc-183">The wizard requires the ISO image to have an **.iso** file name extension because most programs that burn a CD or DVD require that extension.</span></span> <span data-ttu-id="9acfc-184">如果不指定其他位置，将在桌面上创建使用名称**DaRT70**的 iso 图像。</span><span class="sxs-lookup"><span data-stu-id="9acfc-184">If you do not specify a different location, the ISO image is created on your desktop with the name **DaRT70.ISO**.</span></span>

### <span data-ttu-id="9acfc-185">将恢复映像刻录到 CD 或 DVD</span><span class="sxs-lookup"><span data-stu-id="9acfc-185">To burn the recovery image to a CD or DVD</span></span>

<span data-ttu-id="9acfc-186">如果**DaRT 恢复映像向导**检测到计算机上兼容的 cd-rw 驱动器，它可以将 ISO 映像刻录到光盘。</span><span class="sxs-lookup"><span data-stu-id="9acfc-186">If the **DaRT Recovery Image Wizard** detects a compatible CD-RW drive on your computer, it offers to burn the ISO image to a disc for you.</span></span> <span data-ttu-id="9acfc-187">如果你想要刻录 CD 或 DVD，并且向导无法识别你的驱动器，则必须使用另一个程序，例如你的驱动器附带的程序。</span><span class="sxs-lookup"><span data-stu-id="9acfc-187">If you want to burn a CD or DVD and the wizard does not recognize your drive, you must use another program, such as the program that was included with your drive.</span></span> <span data-ttu-id="9acfc-188">你可以使用 duplicator、复制服务或 CD 或 DVD 刻录软件来制作任何其他副本。</span><span class="sxs-lookup"><span data-stu-id="9acfc-188">You can use a duplicator, a duplicating service, or CD or DVD-burning software to make any additional copies.</span></span>

1.  <span data-ttu-id="9acfc-189">在 "刻录到**DaRT 恢复映像向导**的**可写入 cd/dvd** " 对话框中，选择 "**将映像刻录到以下可录制的 cd/dvd 驱动器"**。</span><span class="sxs-lookup"><span data-stu-id="9acfc-189">In the **Burn to a recordable CD/DVD** dialog box of the **DaRT Recovery Image Wizard**, select **Burn the image to the following recordable CD/DVD drive**.</span></span>

2.  <span data-ttu-id="9acfc-190">选择 CD 或 DVD 驱动器。</span><span class="sxs-lookup"><span data-stu-id="9acfc-190">Select the CD or DVD drive.</span></span>

    <span data-ttu-id="9acfc-191">**注意** 如果无法识别驱动器且安装了新驱动器，则可以单击 "**刷新驱动器列表**" 以强制向导更新可用驱动器列表。</span><span class="sxs-lookup"><span data-stu-id="9acfc-191">**Note** If a drive is not recognized and you install a new drive, you can click **Refresh Drive List** to force the wizard to update the list of available drives.</span></span>

     

3.  <span data-ttu-id="9acfc-192">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9acfc-192">Click **Next**.</span></span>

## <span data-ttu-id="9acfc-193">相关主题</span><span class="sxs-lookup"><span data-stu-id="9acfc-193">Related topics</span></span>


[<span data-ttu-id="9acfc-194">创建 DaRT 7.0 恢复映像</span><span class="sxs-lookup"><span data-stu-id="9acfc-194">Creating the DaRT 7.0 Recovery Image</span></span>](creating-the-dart-70-recovery-image-dart-7.md)

 

 





