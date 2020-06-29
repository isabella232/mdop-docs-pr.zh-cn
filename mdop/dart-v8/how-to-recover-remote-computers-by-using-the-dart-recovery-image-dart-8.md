---
title: 如何使用 DaRT 恢复映像恢复远程计算机
description: 如何使用 DaRT 恢复映像恢复远程计算机
author: dansimp
ms.assetid: 363ccd48-6820-4b5b-a43a-323c0b208a9d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 3b3e3155dbea8da18338b8a167d22f73b1c8e4bb
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803560"
---
# <span data-ttu-id="89013-103">如何使用 DaRT 恢复映像恢复远程计算机</span><span class="sxs-lookup"><span data-stu-id="89013-103">How to Recover Remote Computers by Using the DaRT Recovery Image</span></span>


<span data-ttu-id="89013-104">使用 Microsoft Diagnostics 和恢复工具集（DaRT）8.0 中的远程连接功能，在最终用户计算机上远程运行 DaRT 工具。</span><span class="sxs-lookup"><span data-stu-id="89013-104">Use the Remote Connection feature in Microsoft Diagnostics and Recovery Toolset (DaRT) 8.0 to run the DaRT tools remotely on an end-user computer.</span></span> <span data-ttu-id="89013-105">在最终用户向管理员或技术支持人员提供特定信息后，IT 管理员或技术支持人员可以控制最终用户的计算机并远程运行必要的 DaRT 工具。</span><span class="sxs-lookup"><span data-stu-id="89013-105">After the end user provides the administrator or help desk worker with certain information, the IT administrator or help desk worker can take control of the end user's computer and run the necessary DaRT tools remotely.</span></span>

<span data-ttu-id="89013-106">如果您在创建恢复映像时禁用了 DaRT 工具，您仍有权访问所有工具。</span><span class="sxs-lookup"><span data-stu-id="89013-106">If you disabled the DaRT tools when you created the recovery image, you still have access to all of the tools.</span></span> <span data-ttu-id="89013-107">所有工具（远程连接除外）对最终用户不可用。</span><span class="sxs-lookup"><span data-stu-id="89013-107">All of the tools, except Remote Connection, are unavailable to end users.</span></span>

**<span data-ttu-id="89013-108">使用 DaRT 恢复映像恢复远程计算机</span><span class="sxs-lookup"><span data-stu-id="89013-108">To recover a remote computer by using the DaRT recovery image</span></span>**

1.  <span data-ttu-id="89013-109">使用 DaRT 恢复映像启动最终用户计算机。</span><span class="sxs-lookup"><span data-stu-id="89013-109">Boot an end-user computer by using the DaRT recovery image.</span></span>

    <span data-ttu-id="89013-110">通常，你可以使用以下方法之一启动到 DaRT 以恢复远程计算机，具体取决于你部署 DaRT 恢复映像的方式。</span><span class="sxs-lookup"><span data-stu-id="89013-110">You will typically use one of the following methods to boot into DaRT to recover a remote computer, depending on how you deploy the DaRT recovery image.</span></span> <span data-ttu-id="89013-111">有关部署 DaRT 恢复映像的详细信息，请参阅[部署 dart 8.0](deploying-dart-80-dart-8.md)。</span><span class="sxs-lookup"><span data-stu-id="89013-111">For more information about deploying the DaRT recovery image, see [Deploying DaRT 8.0](deploying-dart-80-dart-8.md).</span></span>

    -   <span data-ttu-id="89013-112">从有问题的计算机上的恢复分区启动到 DaRT。</span><span class="sxs-lookup"><span data-stu-id="89013-112">Boot into DaRT from a recovery partition on the problem computer.</span></span>

    -   <span data-ttu-id="89013-113">从网络上的远程分区启动到 DaRT。</span><span class="sxs-lookup"><span data-stu-id="89013-113">Boot into DaRT from a remote partition on the network.</span></span>

    <span data-ttu-id="89013-114">有关每种方法的优点和缺点的信息，请参阅[规划如何保存和部署 DaRT 8.0 恢复映像](planning-how-to-save-and-deploy-the-dart-80-recovery-image-dart-8.md)。</span><span class="sxs-lookup"><span data-stu-id="89013-114">For information about the advantages and disadvantages of each method, see [Planning How to Save and Deploy the DaRT 8.0 Recovery Image](planning-how-to-save-and-deploy-the-dart-80-recovery-image-dart-8.md).</span></span>

    <span data-ttu-id="89013-115">无论使用哪种方法启动到 DaRT，您都必须在 BIOS 中为启动选项启用启动设备，或者您希望向最终用户提供的选项。</span><span class="sxs-lookup"><span data-stu-id="89013-115">Whichever method that you use to boot into DaRT, you must enable the boot device in the BIOS for the boot option or options that you want to make available to the end user.</span></span>

    **<span data-ttu-id="89013-116">注意</span><span class="sxs-lookup"><span data-stu-id="89013-116">Note</span></span>**  
    <span data-ttu-id="89013-117">配置 BIOS 是唯一的，具体取决于您的组织中使用的硬盘驱动器、网络适配器和其他硬件的类型。</span><span class="sxs-lookup"><span data-stu-id="89013-117">Configuring the BIOS is unique, depending on the kind of hard disk drive, network adapters, and other hardware that is used in your organization.</span></span>



~~~
As the computer is booting into the DaRT recovery image, the **NetStart** dialog box appears.
~~~

2. <span data-ttu-id="89013-118">当系统询问您是否要初始化网络服务时，请选择下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="89013-118">When you are asked whether you want to initialize network services, select one of the following:</span></span>

   <span data-ttu-id="89013-119">**是**-假定 DHCP 服务器在网络上存在，并且尝试从服务器获取 IP 地址的尝试。</span><span class="sxs-lookup"><span data-stu-id="89013-119">**Yes** - it is assumed that a DHCP server is present on the network, and an attempt is made to obtain an IP address from the server.</span></span> <span data-ttu-id="89013-120">如果网络使用静态 IP 地址而不是 DHCP，则可以在以后使用 DaRT 中的**Tcp/ip 配置**工具指定静态 ip 地址。</span><span class="sxs-lookup"><span data-stu-id="89013-120">If the network uses static IP addresses instead of DHCP, you can later use the **TCP/IP Configuration** tool in DaRT to specify a static IP address.</span></span>

   <span data-ttu-id="89013-121">**No** -跳过网络初始化过程。</span><span class="sxs-lookup"><span data-stu-id="89013-121">**No** - skip the network initialization process.</span></span>

3. <span data-ttu-id="89013-122">指明是否要重新映射驱动器号。</span><span class="sxs-lookup"><span data-stu-id="89013-122">Indicate whether you want to remap the drive letters.</span></span> <span data-ttu-id="89013-123">当您运行 Windows online 时，系统卷通常映射到驱动器 C。但是，当你在 WinRE 下运行 Windows 时，原始系统卷可能会映射到其他驱动器，这可能会引起混淆。</span><span class="sxs-lookup"><span data-stu-id="89013-123">When you run Windows online, the system volume is typically mapped to drive C. However, when you run Windows offline under WinRE, the original system volume might be mapped to another drive, and this can cause confusion.</span></span> <span data-ttu-id="89013-124">如果您决定重新映射，DaRT 将尝试映射脱机驱动器号以匹配联机驱动器号。</span><span class="sxs-lookup"><span data-stu-id="89013-124">If you decide to remap, DaRT tries to map the offline drive letters to match the online drive letters.</span></span> <span data-ttu-id="89013-125">仅在启动过程中稍后选择了脱机操作系统时，才会执行重映射。</span><span class="sxs-lookup"><span data-stu-id="89013-125">Remapping is performed only if an offline operating system is selected later in the startup process.</span></span>

4. <span data-ttu-id="89013-126">在 "**系统恢复选项**" 对话框中，选择一个键盘布局。</span><span class="sxs-lookup"><span data-stu-id="89013-126">On the **System Recovery Options** dialog box, select a keyboard layout.</span></span>

5. <span data-ttu-id="89013-127">检查显示的系统根目录、所安装的操作系统类型和分区大小。</span><span class="sxs-lookup"><span data-stu-id="89013-127">Check the displayed system root directory, the kind of operating system installed, and the partition size.</span></span> <span data-ttu-id="89013-128">如果您没有看到您的操作系统列出，并且怀疑缺少驱动程序可能导致故障，请单击 "**加载驱动程序**" 以加载可疑驱动程序，然后插入设备的安装媒体并选择驱动程序。</span><span class="sxs-lookup"><span data-stu-id="89013-128">If you do not see your operating system listed, and suspect that the lack of drivers is a possible cause of the failure, click **Load Drivers** to load the suspect drivers, and then insert the installation media for the device and select the driver.</span></span>

6. <span data-ttu-id="89013-129">选择要修复或诊断的安装，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="89013-129">Select the installation that you want to repair or diagnose, and then click **Next**.</span></span>

   **<span data-ttu-id="89013-130">注意</span><span class="sxs-lookup"><span data-stu-id="89013-130">Note</span></span>**  
   <span data-ttu-id="89013-131">如果 Windows 恢复环境（WinRE）检测到或怀疑 Windows 8 在最后一次尝试时未正确启动，则**启动修复**可能会开始自动运行。</span><span class="sxs-lookup"><span data-stu-id="89013-131">If the Windows Recovery Environment (WinRE) detects or suspects that Windows 8 did not start correctly the last time that it was tried, **Startup Repair** might start to run automatically.</span></span> <span data-ttu-id="89013-132">有关如何解决此问题的信息，请参阅[DaRT 8.0 的疑难解答](troubleshooting-dart-80-dart-8.md)。</span><span class="sxs-lookup"><span data-stu-id="89013-132">For information about how to resolve this issue, see [Troubleshooting DaRT 8.0](troubleshooting-dart-80-dart-8.md).</span></span>



~~~
If any of the registry hives are corrupted or missing, Registry Editor and several other DaRT utilities will have limited functionality. If no operating system is selected, some tools will not be available.

The **System Recovery Options** window appears and lists various recovery tools.
~~~

7. <span data-ttu-id="89013-133">在 "**系统恢复选项**" 窗口中，单击 " **Microsoft 诊断和恢复工具集**" 以打开**诊断和恢复工具集**。</span><span class="sxs-lookup"><span data-stu-id="89013-133">On the **System Recovery Options** window, click **Microsoft Diagnostics and Recovery Toolset** to open the **Diagnostics and Recovery Toolset**.</span></span>

8. <span data-ttu-id="89013-134">在 "**诊断和恢复工具集**" 窗口中，单击 "**远程连接**" 以打开 " **DaRT 远程连接**" 窗口。</span><span class="sxs-lookup"><span data-stu-id="89013-134">On the **Diagnostics and Recovery Toolset** window, click **Remote Connection** to open the **DaRT Remote Connection** window.</span></span> <span data-ttu-id="89013-135">如果系统提示您提供帮助台远程访问，请单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="89013-135">If you are prompted to give the help desk remote access, click **OK**.</span></span>

   <span data-ttu-id="89013-136">将打开 "DaRT 远程连接" 窗口，并显示票证编号、IP 地址和端口信息。</span><span class="sxs-lookup"><span data-stu-id="89013-136">The DaRT Remote Connection window opens and displays a ticket number, IP address, and port information.</span></span>

9. <span data-ttu-id="89013-137">在技术支持计算机上，打开 " **DaRT 远程连接查看器**"。</span><span class="sxs-lookup"><span data-stu-id="89013-137">On the help desk computer, open the **DaRT Remote Connection Viewer**.</span></span>

10. <span data-ttu-id="89013-138">单击 "**开始**"，单击 "**所有程序**"，单击 " **Microsoft dart 8.0**"，然后单击 " **DaRT 远程连接查看器**"。</span><span class="sxs-lookup"><span data-stu-id="89013-138">Click **Start**, click **All Programs**, click **Microsoft DaRT 8.0**, and then click **DaRT Remote Connection Viewer**.</span></span>

11. <span data-ttu-id="89013-139">在 " **DaRT 远程连接**" 窗口中，输入所需的票证、IP 地址和端口信息。</span><span class="sxs-lookup"><span data-stu-id="89013-139">In the **DaRT Remote Connection** window, enter the required ticket, IP address, and port information.</span></span>

   **<span data-ttu-id="89013-140">注意</span><span class="sxs-lookup"><span data-stu-id="89013-140">Note</span></span>**  
   <span data-ttu-id="89013-141">此信息在最终用户计算机上创建，并且必须由最终用户提供。</span><span class="sxs-lookup"><span data-stu-id="89013-141">This information is created on the end-user computer and must be provided by the end user.</span></span> <span data-ttu-id="89013-142">可能有多个 IP 地址可供选择，具体取决于最终用户计算机上可用的数量。</span><span class="sxs-lookup"><span data-stu-id="89013-142">There might be multiple IP addresses to choose from, depending on how many are available on the end-user computer.</span></span>



12. <span data-ttu-id="89013-143">单击**连接**。</span><span class="sxs-lookup"><span data-stu-id="89013-143">Click **Connect**.</span></span>

<span data-ttu-id="89013-144">IT 管理员现在假定控制最终用户计算机，并且可以远程运行 DaRT 工具。</span><span class="sxs-lookup"><span data-stu-id="89013-144">The IT administrator now assumes control of the end-user computer and can run the DaRT tools remotely.</span></span>

**<span data-ttu-id="89013-145">注意</span><span class="sxs-lookup"><span data-stu-id="89013-145">Note</span></span>**  
<span data-ttu-id="89013-146">提供了名为 inv32.xml 的文件，其中包含远程连接信息，例如端口号和 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="89013-146">A file is provided that is named inv32.xml and contains remote connection information, such as the port number and IP address.</span></span> <span data-ttu-id="89013-147">默认情况下，该文件通常位于%windir%\\system32。</span><span class="sxs-lookup"><span data-stu-id="89013-147">By default, the file is typically located at %windir%\\system32.</span></span>



**<span data-ttu-id="89013-148">自定义远程连接过程</span><span class="sxs-lookup"><span data-stu-id="89013-148">To customize the Remote Connection process</span></span>**

1. <span data-ttu-id="89013-149">您可以通过编辑 winpeshl.ini 文件来自定义远程连接过程。</span><span class="sxs-lookup"><span data-stu-id="89013-149">You can customize the Remote Connection process by editing the winpeshl.ini file.</span></span> <span data-ttu-id="89013-150">有关如何编辑 winpeshl.ini 文件的详细信息，请参阅[Winpeshl.ini 文件](https://go.microsoft.com/fwlink/?LinkId=219413)。</span><span class="sxs-lookup"><span data-stu-id="89013-150">For more information about how to edit the winpeshl.ini file, see [Winpeshl.ini Files](https://go.microsoft.com/fwlink/?LinkId=219413).</span></span>

   <span data-ttu-id="89013-151">指定以下命令和参数以自定义如何与最终用户计算机建立远程连接：</span><span class="sxs-lookup"><span data-stu-id="89013-151">Specify the following commands and parameters to customize how a remote connection is established with an end-user computer:</span></span>

   <table>
   <colgroup>
   <col width="33%" />
   <col width="33%" />
   <col width="33%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="89013-152">命令</span><span class="sxs-lookup"><span data-stu-id="89013-152">Command</span></span></th>
   <th align="left"><span data-ttu-id="89013-153">参数</span><span class="sxs-lookup"><span data-stu-id="89013-153">Parameter</span></span></th>
   <th align="left"><span data-ttu-id="89013-154">描述</span><span class="sxs-lookup"><span data-stu-id="89013-154">Description</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="89013-155">RemoteRecovery.exe</span><span class="sxs-lookup"><span data-stu-id="89013-155">RemoteRecovery.exe</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="89013-156">-nomessage</span><span class="sxs-lookup"><span data-stu-id="89013-156">-nomessage</span></span></p></td>
   <td align="left"><p><span data-ttu-id="89013-157">指定不显示确认提示。</span><span class="sxs-lookup"><span data-stu-id="89013-157">Specifies that the confirmation prompt is not displayed.</span></span> <strong><span data-ttu-id="89013-158">远程连接 </strong> 继续执行，就像最终用户 &quot; &quot; 对确认提示做出响应一样。</span><span class="sxs-lookup"><span data-stu-id="89013-158">Remote Connection</strong> continues just as if the end user had responded &quot;Yes&quot; to the confirmation prompt.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="89013-159">WaitForConnection.exe</span><span class="sxs-lookup"><span data-stu-id="89013-159">WaitForConnection.exe</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="89013-160">无</span><span class="sxs-lookup"><span data-stu-id="89013-160">none</span></span></p></td>
   <td align="left"><p><span data-ttu-id="89013-161">防止自定义脚本在 <strong> 远程连接 </strong> 未运行或与最终用户计算机建立有效连接的情况下继续进行。</span><span class="sxs-lookup"><span data-stu-id="89013-161">Prevents a custom script from continuing until either <strong>Remote Connection</strong> is not running or a valid connection is established with the end-user computer.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="89013-162">重要提示</span><span class="sxs-lookup"><span data-stu-id="89013-162">Important</span></span></strong><br/><p><span data-ttu-id="89013-163">如果单独指定此命令，此命令将不起作用。</span><span class="sxs-lookup"><span data-stu-id="89013-163">This command serves no function if it is specified independently.</span></span> <span data-ttu-id="89013-164">必须在脚本中指定它才能正常工作。</span><span class="sxs-lookup"><span data-stu-id="89013-164">It must be specified in a script to function correctly.</span></span></p>
   </div>
   <div>

   </div></td>
   </tr>
   </tbody>
   </table>



2. <span data-ttu-id="89013-165">以下是自定义的 winpeshl.ini 文件的一个示例，在尝试启动到 DaRT 后立即打开**远程连接**工具：</span><span class="sxs-lookup"><span data-stu-id="89013-165">The following is an example of a winpeshl.ini file that is customized to open the **Remote Connection** tool as soon as an attempt is made to boot into DaRT:</span></span>

   ```ini
   [LaunchApps]
   "%windir%\system32\netstart.exe -network -remount"
   "cmd /C start %windir%\system32\RemoteRecovery.exe -nomessage"
   "%windir%\system32\WaitForConnection.exe"
   "%SYSTEMDRIVE%\sources\recovery\recenv.exe"
   ```

<span data-ttu-id="89013-166">当 DaRT 启动时，它会在 RAM 磁盘上的 \\Windows\\System32\\ 中创建文件 inv32.xml。</span><span class="sxs-lookup"><span data-stu-id="89013-166">When DaRT starts, it creates the file inv32.xml in \\Windows\\System32\\ on the RAM disk.</span></span> <span data-ttu-id="89013-167">此文件包含连接信息： IP 地址、端口和票证编号。</span><span class="sxs-lookup"><span data-stu-id="89013-167">This file contains connection information: IP address, port, and ticket number.</span></span> <span data-ttu-id="89013-168">你可以将此文件复制到网络共享以触发帮助台工作流。</span><span class="sxs-lookup"><span data-stu-id="89013-168">You can copy this file to a network share to trigger a Help desk workflow.</span></span> <span data-ttu-id="89013-169">例如，自定义程序可以检查网络共享中的连接文件，然后创建支持票证或发送电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="89013-169">For example, a custom program can check the network share for connection files, and then create a support ticket or send email notifications.</span></span>

**<span data-ttu-id="89013-170">在命令提示符处运行远程连接查看器</span><span class="sxs-lookup"><span data-stu-id="89013-170">To run the Remote Connection Viewer at the command prompt</span></span>**

1.  <span data-ttu-id="89013-171">要在命令提示符处运行**DaRT 远程连接查看器**，请指定**DartRemoteViewer.exe**命令并使用以下参数：</span><span class="sxs-lookup"><span data-stu-id="89013-171">To run the **DaRT Remote Connection Viewer** at the command prompt, specify the **DartRemoteViewer.exe** command and use the following parameters:</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="89013-172">参数</span><span class="sxs-lookup"><span data-stu-id="89013-172">Parameter</span></span></th>
    <th align="left"><span data-ttu-id="89013-173">描述</span><span class="sxs-lookup"><span data-stu-id="89013-173">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="89013-174">-票证 = &lt; <em> ticketnumber</em>&gt;</span><span class="sxs-lookup"><span data-stu-id="89013-174">-ticket=&lt;<em>ticketnumber</em>&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="89013-175">其中， &lt; <em> ticketnumber </em> &gt; 是由远程连接生成的票据号码，包括短划线。</span><span class="sxs-lookup"><span data-stu-id="89013-175">Where &lt;<em>ticketnumber</em>&gt; is the ticket number, including the dashes, that is generated by Remote Connection.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="89013-176">-ipaddress = &lt; <em> ipaddress</em>&gt;</span><span class="sxs-lookup"><span data-stu-id="89013-176">-ipaddress=&lt;<em>ipaddress</em>&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="89013-177">其中 ip &lt; <em> </em> &gt; 地址是由远程连接生成的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="89013-177">Where &lt;<em>ipaddress</em>&gt; is the IP address that is generated by Remote Connection.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="89013-178">-port = &lt; <em> 端口</em>&gt;</span><span class="sxs-lookup"><span data-stu-id="89013-178">-port=&lt;<em>port</em>&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="89013-179">其中 &lt; <em> 端口 </em> &gt; 是对应于指定 IP 地址的端口。</span><span class="sxs-lookup"><span data-stu-id="89013-179">Where &lt;<em>port</em>&gt; is the port that corresponds to the specified IP address.</span></span></p></td>
    </tr>
    </tbody>
    </table>



~~~
**Note**  
The variables for these parameters are created on the end-user computer and must be provided by the end user.
~~~



2. <span data-ttu-id="89013-180">如果所有三个参数均已指定且数据有效，则会在程序启动时立即尝试连接。</span><span class="sxs-lookup"><span data-stu-id="89013-180">If all three parameters are specified and the data is valid, a connection is immediately tried when the program starts.</span></span> <span data-ttu-id="89013-181">如果任何参数无效，程序将在未指定参数的情况下启动。</span><span class="sxs-lookup"><span data-stu-id="89013-181">If any parameter is not valid, the program starts as if there were no parameters specified.</span></span>

## <span data-ttu-id="89013-182">相关主题</span><span class="sxs-lookup"><span data-stu-id="89013-182">Related topics</span></span>


[<span data-ttu-id="89013-183">DaRT 8.0 的操作</span><span class="sxs-lookup"><span data-stu-id="89013-183">Operations for DaRT 8.0</span></span>](operations-for-dart-80-dart-8.md)

[<span data-ttu-id="89013-184">使用 DaRT 8.0 恢复计算机</span><span class="sxs-lookup"><span data-stu-id="89013-184">Recovering Computers Using DaRT 8.0</span></span>](recovering-computers-using-dart-80-dart-8.md)









