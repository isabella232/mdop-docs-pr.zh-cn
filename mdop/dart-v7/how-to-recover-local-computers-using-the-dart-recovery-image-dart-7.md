---
title: 如何使用 DaRT 恢复映像恢复本地计算机
description: 如何使用 DaRT 恢复映像恢复本地计算机
author: dansimp
ms.assetid: be29b5a8-be08-4cf2-822e-77a51d3f3b65
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4c605db895b5ea812d90db51d3c2de9653e2dd2d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803433"
---
# <span data-ttu-id="e1583-103">如何使用 DaRT 恢复映像恢复本地计算机</span><span class="sxs-lookup"><span data-stu-id="e1583-103">How to Recover Local Computers Using the DaRT Recovery Image</span></span>


<span data-ttu-id="e1583-104">若要使用 Microsoft 诊断和恢复工具集（DaRT）7恢复本地计算机，您必须在遇到需要 DaRT 的问题的最终用户计算机上进行物理演示。</span><span class="sxs-lookup"><span data-stu-id="e1583-104">To recover a local computer by using Microsoft Diagnostics and Recovery Toolset (DaRT) 7, you must be physically present at the end-user computer that is experiencing problems that require DaRT.</span></span> <span data-ttu-id="e1583-105">您也可以按照有关[如何使用 Dart 恢复映像恢复远程计算机](how-to-recover-remote-computers-using-the-dart-recovery-image-dart-7.md)的说明，远程运行 DaRT。</span><span class="sxs-lookup"><span data-stu-id="e1583-105">You can also run DaRT remotely by following the instructions at [How to Recover Remote Computers Using the DaRT Recovery Image](how-to-recover-remote-computers-using-the-dart-recovery-image-dart-7.md).</span></span>

**<span data-ttu-id="e1583-106">使用 DaRT 恢复本地计算机</span><span class="sxs-lookup"><span data-stu-id="e1583-106">To recover a local computer by using DaRT</span></span>**

1.  <span data-ttu-id="e1583-107">当计算机启动到 DaRT 恢复映像时，将出现 " **NetStart** " 对话框。</span><span class="sxs-lookup"><span data-stu-id="e1583-107">As the computer is booting into the DaRT recovery image, the **NetStart** dialog box appears.</span></span> <span data-ttu-id="e1583-108">系统将询问您是否要初始化网络服务。</span><span class="sxs-lookup"><span data-stu-id="e1583-108">You are asked whether you want to initialize network services.</span></span> <span data-ttu-id="e1583-109">如果单击 **"是**"，则假设网络上存在 DHCP 服务器，并尝试从服务器获取 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="e1583-109">If you click **Yes**, it is assumed that a DHCP server is present on the network and an attempt is made to obtain an IP address from the server.</span></span> <span data-ttu-id="e1583-110">如果网络使用静态 IP 地址而不是 DHCP，则可以在以后使用 DaRT 中的**Tcp/ip 配置**工具指定静态 ip 地址。</span><span class="sxs-lookup"><span data-stu-id="e1583-110">If the network uses static IP addresses instead of DHCP, you can later use the **TCP/IP Configuration** tool in DaRT to specify a static IP address.</span></span>

    <span data-ttu-id="e1583-111">若要跳过网络初始化过程，请单击 "**否**"。</span><span class="sxs-lookup"><span data-stu-id="e1583-111">To skip the network initialization process, click **No**.</span></span>

2.  <span data-ttu-id="e1583-112">在 "网络初始化" 对话框中，系统会询问你是否要重新映射驱动器号。</span><span class="sxs-lookup"><span data-stu-id="e1583-112">Following the network initialization dialog box, you are asked whether you want to remap the drive letters.</span></span> <span data-ttu-id="e1583-113">当您运行 Windows online 时，系统卷通常映射到驱动器 C。但是，当你在 WinRE 下运行 Windows 时，原始系统卷可能会映射到其他驱动器，这可能会引起混淆。</span><span class="sxs-lookup"><span data-stu-id="e1583-113">When you run Windows online, the system volume is typically mapped to drive C. However, when you run Windows offline under WinRE, the original system volume might be mapped to another drive, and this can cause confusion.</span></span> <span data-ttu-id="e1583-114">如果您决定重新映射，DaRT 将尝试映射脱机驱动器号以匹配联机驱动器号。</span><span class="sxs-lookup"><span data-stu-id="e1583-114">If you decide to remap, DaRT tries to map the offline drive letters to match the online drive letters.</span></span> <span data-ttu-id="e1583-115">仅在启动过程中稍后选择了脱机操作系统时，才会执行重映射。</span><span class="sxs-lookup"><span data-stu-id="e1583-115">Remapping is performed only if an offline operating system is selected later in the startup process.</span></span>

3.  <span data-ttu-id="e1583-116">在 "重新映射" 对话框中，将出现 "**系统恢复选项**" 对话框，要求你选择键盘布局。</span><span class="sxs-lookup"><span data-stu-id="e1583-116">Following the remapping dialog box, a **System Recovery Options** dialog box appears and asks you to select a keyboard layout.</span></span> <span data-ttu-id="e1583-117">然后，它显示系统根目录、所安装的操作系统类型和分区大小。</span><span class="sxs-lookup"><span data-stu-id="e1583-117">Then it displays the system root directory, the kind of operating system installed, and the partition size.</span></span> <span data-ttu-id="e1583-118">如果您没有看到您的操作系统列出，并且怀疑缺少驱动程序可能导致故障，请单击 "**加载驱动程序**" 以加载可疑驱动程序。</span><span class="sxs-lookup"><span data-stu-id="e1583-118">If you do not see your operating system listed, and suspect that the lack of drivers is a possible cause of the failure, click **Load Drivers** to load the suspect drivers.</span></span> <span data-ttu-id="e1583-119">这将提示您插入设备的安装媒体并选择驱动程序。</span><span class="sxs-lookup"><span data-stu-id="e1583-119">This prompts you to insert the installation media for the device and to select the driver.</span></span> <span data-ttu-id="e1583-120">选择要修复或诊断的安装，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="e1583-120">Select the installation that you want to repair or diagnose, and then click **Next**.</span></span>

    **<span data-ttu-id="e1583-121">注意</span><span class="sxs-lookup"><span data-stu-id="e1583-121">Note</span></span>**  
    <span data-ttu-id="e1583-122">如果 Windows 恢复环境（WinRE）检测到或怀疑 Windows 7 未在上次尝试时正常启动，则**启动修复**可能会开始自动运行。</span><span class="sxs-lookup"><span data-stu-id="e1583-122">If the Windows Recovery Environment (WinRE) detects or suspects that Windows 7 did not start correctly the last time that it was tried, **Startup Repair** might start to run automatically.</span></span>



~~~
If any of the registry hives are corrupted or missing, Registry Editor, and several other DaRT utilities, will have limited functionality. If no operating system is selected, some tools will not be available.

The **System Recovery Options** window appears and lists various recovery tools.
~~~

4. <span data-ttu-id="e1583-123">在 "**系统恢复选项**" 窗口中，单击 " **Microsoft 诊断和恢复工具集**"。</span><span class="sxs-lookup"><span data-stu-id="e1583-123">On the **System Recovery Options** window, click **Microsoft Diagnostics and Recovery Toolset**.</span></span>

   <span data-ttu-id="e1583-124">将打开 "**诊断和恢复工具集**" 窗口。</span><span class="sxs-lookup"><span data-stu-id="e1583-124">The **Diagnostics and Recovery Toolset** window opens.</span></span> <span data-ttu-id="e1583-125">现在，你可以运行在创建 DaRT 恢复映像时所包含的任何单个工具或向导。</span><span class="sxs-lookup"><span data-stu-id="e1583-125">You can now run any of the individual tools or wizards that were included when the DaRT recovery image was created.</span></span>

<span data-ttu-id="e1583-126">你可以单击 "**诊断和恢复工具集**" 窗口上的 "**帮助**"，打开客户端帮助文件，该文件提供运行单个 DaRT 工具所需的详细说明和信息。</span><span class="sxs-lookup"><span data-stu-id="e1583-126">You can click **Help** on the **Diagnostics and Recovery Toolset** window to open the client Help file that provides detailed instruction and information needed to run the individual DaRT tools.</span></span> <span data-ttu-id="e1583-127">您也可以在 "**诊断和恢复工具集**" 窗口中单击 "**解决方案向导**"，根据向导提供的简短面试，选择适合情况的最佳工具。</span><span class="sxs-lookup"><span data-stu-id="e1583-127">You can also click the **Solution Wizard** on the **Diagnostics and Recovery Toolset** window to choose the best tool for the situation, based on a brief interview that the wizard provides.</span></span>

<span data-ttu-id="e1583-128">有关任何 DaRT 工具的一般信息，请参阅[DaRT 7.0 中的工具概述](overview-of-the-tools-in-dart-70-new-ia.md)。</span><span class="sxs-lookup"><span data-stu-id="e1583-128">For general information about any of the DaRT tools, see [Overview of the Tools in DaRT 7.0](overview-of-the-tools-in-dart-70-new-ia.md).</span></span>

**<span data-ttu-id="e1583-129">在命令提示符处运行 DaRT</span><span class="sxs-lookup"><span data-stu-id="e1583-129">To run DaRT at the command prompt</span></span>**

1. <span data-ttu-id="e1583-130">你可以通过指定**netstart.exe**命令和使用以下任一参数，在命令提示符处运行 DaRT：</span><span class="sxs-lookup"><span data-stu-id="e1583-130">You can run DaRT at the command prompt by specifying the **netstart.exe** command and by using any of the following parameters:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="e1583-131">参数</span><span class="sxs-lookup"><span data-stu-id="e1583-131">Parameter</span></span></th>
   <th align="left"><span data-ttu-id="e1583-132">描述</span><span class="sxs-lookup"><span data-stu-id="e1583-132">Description</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="e1583-133">-网络</span><span class="sxs-lookup"><span data-stu-id="e1583-133">-network</span></span></p></td>
   <td align="left"><p><span data-ttu-id="e1583-134">初始化网络服务。</span><span class="sxs-lookup"><span data-stu-id="e1583-134">Initializes the network services.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="e1583-135">-重新装载</span><span class="sxs-lookup"><span data-stu-id="e1583-135">-remount</span></span></p></td>
   <td align="left"><p><span data-ttu-id="e1583-136">重新映射驱动器号。</span><span class="sxs-lookup"><span data-stu-id="e1583-136">Remaps the drive letters.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="e1583-137">-提示</span><span class="sxs-lookup"><span data-stu-id="e1583-137">-prompt</span></span></p></td>
   <td align="left"><p><span data-ttu-id="e1583-138">显示要求最终用户指定是否初始化网络并重新映射驱动器的消息。</span><span class="sxs-lookup"><span data-stu-id="e1583-138">Displays messages asking the end user to specify whether to initialize the network and remap the drives.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="e1583-139">重要提示</span><span class="sxs-lookup"><span data-stu-id="e1583-139">Important</span></span></strong><br/><p><span data-ttu-id="e1583-140">最终用户对提示的响应将覆盖网络和重新装载开关。</span><span class="sxs-lookup"><span data-stu-id="e1583-140">The end user’s response to the prompts overrides the -network and -remount switches.</span></span></p>
   </div>
   <div>

   </div></td>
   </tr>
   </tbody>
   </table>



2. <span data-ttu-id="e1583-141">你可以自定义 DaRT，以便启动到 DaRT 的计算机会自动打开用于建立与技术支持的远程连接的**远程连接**工具。</span><span class="sxs-lookup"><span data-stu-id="e1583-141">You can customize DaRT so that a computer that boots into DaRT automatically opens the **Remote Connection** tool that is used to establish a remote connection with the help desk.</span></span>

## <span data-ttu-id="e1583-142">相关主题</span><span class="sxs-lookup"><span data-stu-id="e1583-142">Related topics</span></span>


[<span data-ttu-id="e1583-143">使用 DaRT 7.0 恢复计算机</span><span class="sxs-lookup"><span data-stu-id="e1583-143">Recovering Computers Using DaRT 7.0</span></span>](recovering-computers-using-dart-70-dart-7.md)









