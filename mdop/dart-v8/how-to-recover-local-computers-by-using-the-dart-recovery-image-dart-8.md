---
title: 如何使用 DaRT 恢复映像恢复本地计算机
description: 如何使用 DaRT 恢复映像恢复本地计算机
author: dansimp
ms.assetid: f679d522-49ab-429c-93d0-294c3f3e5639
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1b5faa0eb9ac24b33c66f1d5262a050b92e11e52
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803542"
---
# <span data-ttu-id="48a94-103">如何使用 DaRT 恢复映像恢复本地计算机</span><span class="sxs-lookup"><span data-stu-id="48a94-103">How to Recover Local Computers by Using the DaRT Recovery Image</span></span>


<span data-ttu-id="48a94-104">当您在遇到问题的最终用户计算机上物理显示时，请使用这些说明来恢复计算机。</span><span class="sxs-lookup"><span data-stu-id="48a94-104">Use these instructions to recover a computer when you are physically present at the end-user computer that is experiencing problems.</span></span>

**<span data-ttu-id="48a94-105">如何使用 DaRT 恢复映像恢复本地计算机</span><span class="sxs-lookup"><span data-stu-id="48a94-105">How to recover a local computer by using the DaRT recovery image</span></span>**

1.  <span data-ttu-id="48a94-106">使用 Microsoft 诊断和恢复工具集（DaRT）8.0 恢复映像启动最终用户计算机。</span><span class="sxs-lookup"><span data-stu-id="48a94-106">Boot the end-user computer by using the Microsoft Diagnostics and Recovery Toolset (DaRT) 8.0 recovery image.</span></span>

    <span data-ttu-id="48a94-107">当计算机启动到 DaRT 8.0 恢复映像时，将出现 " **NetStart** " 对话框。</span><span class="sxs-lookup"><span data-stu-id="48a94-107">As the computer is booting into the DaRT 8.0 recovery image, the **NetStart** dialog box appears.</span></span>

2.  <span data-ttu-id="48a94-108">当系统询问您是否要初始化网络服务时，请选择下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="48a94-108">When you are asked whether you want to initialize network services, select one of the following:</span></span>

    <span data-ttu-id="48a94-109">**是**-假定 DHCP 服务器在网络上存在，并且尝试从服务器获取 IP 地址的尝试。</span><span class="sxs-lookup"><span data-stu-id="48a94-109">**Yes** - it is assumed that a DHCP server is present on the network, and an attempt is made to obtain an IP address from the server.</span></span> <span data-ttu-id="48a94-110">如果网络使用静态 IP 地址而不是 DHCP，则可以在以后使用 DaRT 中的**Tcp/ip 配置**工具指定静态 ip 地址。</span><span class="sxs-lookup"><span data-stu-id="48a94-110">If the network uses static IP addresses instead of DHCP, you can later use the **TCP/IP Configuration** tool in DaRT to specify a static IP address.</span></span>

    <span data-ttu-id="48a94-111">**No** -跳过网络初始化过程。</span><span class="sxs-lookup"><span data-stu-id="48a94-111">**No** - skip the network initialization process.</span></span>

3.  <span data-ttu-id="48a94-112">指明是否要重新映射驱动器号。</span><span class="sxs-lookup"><span data-stu-id="48a94-112">Indicate whether you want to remap the drive letters.</span></span> <span data-ttu-id="48a94-113">当您运行 Windows online 时，系统卷通常映射到驱动器 C。但是，当你在 WinRE 下运行 Windows 时，原始系统卷可能会映射到其他驱动器，这可能会引起混淆。</span><span class="sxs-lookup"><span data-stu-id="48a94-113">When you run Windows online, the system volume is typically mapped to drive C. However, when you run Windows offline under WinRE, the original system volume might be mapped to another drive, and this can cause confusion.</span></span> <span data-ttu-id="48a94-114">如果您决定重新映射，DaRT 将尝试映射脱机驱动器号以匹配联机驱动器号。</span><span class="sxs-lookup"><span data-stu-id="48a94-114">If you decide to remap, DaRT tries to map the offline drive letters to match the online drive letters.</span></span> <span data-ttu-id="48a94-115">仅在启动过程中稍后选择了脱机操作系统时，才会执行重映射。</span><span class="sxs-lookup"><span data-stu-id="48a94-115">Remapping is performed only if an offline operating system is selected later in the startup process.</span></span>

4.  <span data-ttu-id="48a94-116">在 "**系统恢复选项**" 对话框中，选择一个键盘布局。</span><span class="sxs-lookup"><span data-stu-id="48a94-116">On the **System Recovery Options** dialog box, select a keyboard layout.</span></span>

5.  <span data-ttu-id="48a94-117">检查显示的系统根目录、所安装的操作系统类型和分区大小。</span><span class="sxs-lookup"><span data-stu-id="48a94-117">Check the displayed system root directory, the kind of operating system installed, and the partition size.</span></span> <span data-ttu-id="48a94-118">如果您没有看到您的操作系统列出，并且怀疑缺少驱动程序可能导致故障，请单击 "**加载驱动程序**" 以加载可疑驱动程序，然后插入设备的安装媒体并选择驱动程序。</span><span class="sxs-lookup"><span data-stu-id="48a94-118">If you do not see your operating system listed, and suspect that the lack of drivers is a possible cause of the failure, click **Load Drivers** to load the suspect drivers, and then insert the installation media for the device and select the driver.</span></span>

6.  <span data-ttu-id="48a94-119">选择要修复或诊断的安装，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="48a94-119">Select the installation that you want to repair or diagnose, and then click **Next**.</span></span>

    **<span data-ttu-id="48a94-120">注意</span><span class="sxs-lookup"><span data-stu-id="48a94-120">Note</span></span>**  
    <span data-ttu-id="48a94-121">如果 Windows 恢复环境（WinRE）检测到或怀疑 Windows 8 在最后一次尝试时未正确启动，则**启动修复**可能会开始自动运行。</span><span class="sxs-lookup"><span data-stu-id="48a94-121">If the Windows Recovery Environment (WinRE) detects or suspects that Windows 8 did not start correctly the last time that it was tried, **Startup Repair** might start to run automatically.</span></span>



~~~
If any of the registry hives are corrupted or missing, Registry Editor and several other DaRT utilities will have limited functionality. If no operating system is selected, some tools will not be available.

The **System Recovery Options** window appears and lists various recovery tools.
~~~

7. <span data-ttu-id="48a94-122">在 "**系统恢复选项**" 窗口中，单击 " **Microsoft 诊断和恢复工具集**"。</span><span class="sxs-lookup"><span data-stu-id="48a94-122">On the **System Recovery Options** window, click **Microsoft Diagnostics and Recovery Toolset**.</span></span>

   <span data-ttu-id="48a94-123">将打开 "**诊断和恢复工具集**" 窗口。</span><span class="sxs-lookup"><span data-stu-id="48a94-123">The **Diagnostics and Recovery Toolset** window opens.</span></span> <span data-ttu-id="48a94-124">现在，你可以运行在创建 DaRT 恢复映像时所包含的任何单个工具或向导。</span><span class="sxs-lookup"><span data-stu-id="48a94-124">You can now run any of the individual tools or wizards that were included when the DaRT recovery image was created.</span></span>

<span data-ttu-id="48a94-125">你可以单击 "**诊断和恢复工具集**" 窗口上的 "**帮助**"，打开客户端帮助文件，该文件提供运行单个 DaRT 工具所需的详细说明和信息。</span><span class="sxs-lookup"><span data-stu-id="48a94-125">You can click **Help** on the **Diagnostics and Recovery Toolset** window to open the client Help file that provides detailed instruction and information needed to run the individual DaRT tools.</span></span> <span data-ttu-id="48a94-126">您也可以在 "**诊断和恢复工具集**" 窗口中单击 "**解决方案向导**"，根据向导提供的简短面试，选择适合情况的最佳工具。</span><span class="sxs-lookup"><span data-stu-id="48a94-126">You can also click the **Solution Wizard** on the **Diagnostics and Recovery Toolset** window to choose the best tool for the situation, based on a brief interview that the wizard provides.</span></span>

<span data-ttu-id="48a94-127">有关任何 DaRT 工具的一般信息，请参阅[DaRT 8.0 中的工具概述](overview-of-the-tools-in-dart-80-dart-8.md)。</span><span class="sxs-lookup"><span data-stu-id="48a94-127">For general information about any of the DaRT tools, see [Overview of the Tools in DaRT 8.0](overview-of-the-tools-in-dart-80-dart-8.md).</span></span>

**<span data-ttu-id="48a94-128">如何在命令提示符处运行 DaRT</span><span class="sxs-lookup"><span data-stu-id="48a94-128">How to run DaRT at the command prompt</span></span>**

- <span data-ttu-id="48a94-129">若要在命令提示符处运行 DaRT，请指定**netstart.exe**命令，然后使用以下任一参数：</span><span class="sxs-lookup"><span data-stu-id="48a94-129">To run DaRT at the command prompt, specify the **netstart.exe** command then use any of the following parameters:</span></span>

  <table>
  <colgroup>
  <col width="50%" />
  <col width="50%" />
  </colgroup>
  <tbody>
  <tr class="odd">
  <td align="left"><p><strong><span data-ttu-id="48a94-130">参数</span><span class="sxs-lookup"><span data-stu-id="48a94-130">Parameter</span></span></strong></p></td>
  <td align="left"><p><strong><span data-ttu-id="48a94-131">描述</span><span class="sxs-lookup"><span data-stu-id="48a94-131">Description</span></span></strong></p></td>
  </tr>
  <tr class="even">
  <td align="left"><p><span data-ttu-id="48a94-132">-网络</span><span class="sxs-lookup"><span data-stu-id="48a94-132">-network</span></span></p></td>
  <td align="left"><p><span data-ttu-id="48a94-133">初始化网络服务。</span><span class="sxs-lookup"><span data-stu-id="48a94-133">Initializes the network services.</span></span></p></td>
  </tr>
  <tr class="odd">
  <td align="left"><p><span data-ttu-id="48a94-134">-重新装载</span><span class="sxs-lookup"><span data-stu-id="48a94-134">-remount</span></span></p></td>
  <td align="left"><p><span data-ttu-id="48a94-135">重新映射驱动器号。</span><span class="sxs-lookup"><span data-stu-id="48a94-135">Remaps the drive letters.</span></span></p></td>
  </tr>
  <tr class="even">
  <td align="left"><p><span data-ttu-id="48a94-136">-提示</span><span class="sxs-lookup"><span data-stu-id="48a94-136">-prompt</span></span></p></td>
  <td align="left"><p><span data-ttu-id="48a94-137">显示要求最终用户指定是否初始化网络并重新映射驱动器的消息。</span><span class="sxs-lookup"><span data-stu-id="48a94-137">Displays messages that ask the end user to specify whether to initialize the network and remap the drives.</span></span></p>
  <div class="alert">
  <strong><span data-ttu-id="48a94-138">警告</span><span class="sxs-lookup"><span data-stu-id="48a94-138">Warning</span></span></strong><br/><p><span data-ttu-id="48a94-139">最终用户对提示的响应将覆盖 "网络" 和 "-重新装载" 开关。</span><span class="sxs-lookup"><span data-stu-id="48a94-139">The end user’s response to the prompt overrides the –network and –remount switches.</span></span></p>
  </div>
  <div>

  </div></td>
  </tr>
  </tbody>
  </table>



## <span data-ttu-id="48a94-140">相关主题</span><span class="sxs-lookup"><span data-stu-id="48a94-140">Related topics</span></span>


[<span data-ttu-id="48a94-141">DaRT 8.0 的操作</span><span class="sxs-lookup"><span data-stu-id="48a94-141">Operations for DaRT 8.0</span></span>](operations-for-dart-80-dart-8.md)

[<span data-ttu-id="48a94-142">使用 DaRT 8.0 恢复计算机</span><span class="sxs-lookup"><span data-stu-id="48a94-142">Recovering Computers Using DaRT 8.0</span></span>](recovering-computers-using-dart-80-dart-8.md)









