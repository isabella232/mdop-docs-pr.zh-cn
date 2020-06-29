---
title: 为 MED-V 创建虚拟 PC 映像
description: 为 MED-V 创建虚拟 PC 映像
author: dansimp
ms.assetid: 5e02ea07-25b9-41a5-a803-d70c55eef586
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 84e45f9ff7213abdd6288bcd750238436d3ab68c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803413"
---
# <span data-ttu-id="126b7-103">为 MED-V 创建虚拟 PC 映像</span><span class="sxs-lookup"><span data-stu-id="126b7-103">Creating a Virtual PC Image for MED-V</span></span>


<span data-ttu-id="126b7-104">若要创建 MED-V 的虚拟 PC （VPC）映像，必须执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="126b7-104">To create a Virtual PC (VPC) image for MED-V, you must perform the following:</span></span>

1.  <span data-ttu-id="126b7-105">[创建 VPC 图像](#bkmk-creatingavirtualmachinebyusingmicrosoftvirtualpc)。</span><span class="sxs-lookup"><span data-stu-id="126b7-105">[Create a VPC image](#bkmk-creatingavirtualmachinebyusingmicrosoftvirtualpc).</span></span>

2.  <span data-ttu-id="126b7-106">[将 med-v 工作区 .msi 程序包安装到 VPC 映像上](#bkmk-howtoinstallthemedvworkspacemsipackage)。</span><span class="sxs-lookup"><span data-stu-id="126b7-106">[Install the MED-V workspace .msi package onto the VPC image](#bkmk-howtoinstallthemedvworkspacemsipackage).</span></span>

3.  <span data-ttu-id="126b7-107">[在 VPC 映像上运行 med-v 虚拟机先决条件工具](#bkmk-howtorunthevirtualmachineprerequisitestool)。</span><span class="sxs-lookup"><span data-stu-id="126b7-107">[Run the MED-V virtual machine prerequisites tool on the VPC image](#bkmk-howtorunthevirtualmachineprerequisitestool).</span></span>

4.  <span data-ttu-id="126b7-108">[在 VPC 映像上手动配置虚拟机先决条件](#bkmk-howtoconfiguremedvvirtualmachinemanualinstallationprerequisites)。</span><span class="sxs-lookup"><span data-stu-id="126b7-108">[Manually configure virtual machine prerequisites on the VPC image](#bkmk-howtoconfiguremedvvirtualmachinemanualinstallationprerequisites).</span></span>

5.  <span data-ttu-id="126b7-109">[为 med-v 映像配置 Sysprep](#bkmk-howtoconfiguresysprepformedvimages) （可选）。</span><span class="sxs-lookup"><span data-stu-id="126b7-109">[Configure Sysprep for MED-V images](#bkmk-howtoconfiguresysprepformedvimages) (optional).</span></span>

6.  <span data-ttu-id="126b7-110">[关闭 Microsoft 虚拟 PC](#bkmk-turningoffmicrosoftvirtualpc)。</span><span class="sxs-lookup"><span data-stu-id="126b7-110">[Turn off Microsoft Virtual PC](#bkmk-turningoffmicrosoftvirtualpc).</span></span>

## <a href="" id="bkmk-creatingavirtualmachinebyusingmicrosoftvirtualpc"></a><span data-ttu-id="126b7-111">使用 Microsoft 虚拟 PC 创建虚拟 PC 映像</span><span class="sxs-lookup"><span data-stu-id="126b7-111">Creating a Virtual PC Image by Using Microsoft Virtual PC</span></span>


<span data-ttu-id="126b7-112">若要使用 Microsoft 虚拟 PC 创建虚拟 PC 映像，请参阅虚拟 PC 文档。</span><span class="sxs-lookup"><span data-stu-id="126b7-112">To create a Virtual PC image using Microsoft Virtual PC, refer to the Virtual PC documentation.</span></span>

<span data-ttu-id="126b7-113">有关详细信息，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="126b7-113">For more information, see the following:</span></span>

-   [<span data-ttu-id="126b7-114">Windows 虚拟电脑帮助</span><span class="sxs-lookup"><span data-stu-id="126b7-114">Windows Virtual PC Help</span></span>](https://go.microsoft.com/fwlink/?LinkId=182378)

-   [<span data-ttu-id="126b7-115">创建虚拟机并安装来宾操作系统</span><span class="sxs-lookup"><span data-stu-id="126b7-115">Create a virtual machine and install a guest operating system</span></span>](https://go.microsoft.com/fwlink/?LinkId=182379)

## <a href="" id="bkmk-howtoinstallthemedvworkspacemsipackage"></a><span data-ttu-id="126b7-116">如何安装 MED-V 工作区 .msi 程序包</span><span class="sxs-lookup"><span data-stu-id="126b7-116">How to Install the MED-V Workspace .msi Package</span></span>


<span data-ttu-id="126b7-117">创建虚拟 PC 映像后，将 MED-V 工作区 .msi 程序包安装到该映像上。</span><span class="sxs-lookup"><span data-stu-id="126b7-117">After the Virtual PC image is created, install the MED-V workspace .msi package onto the image.</span></span>

**<span data-ttu-id="126b7-118">安装 MED-V 工作区映像</span><span class="sxs-lookup"><span data-stu-id="126b7-118">To install the MED-V workspace image</span></span>**

1.  <span data-ttu-id="126b7-119">启动虚拟机，然后将 MED-V 工作区 .msi 程序包复制到其中。</span><span class="sxs-lookup"><span data-stu-id="126b7-119">Start the virtual machine, and copy the MED-V workspace .msi package inside.</span></span>

    <span data-ttu-id="126b7-120">"MED-V" 工作区 .msi 程序包称为 " *MED-V\_workspace\_x.msi*"，其中*x*是版本号。</span><span class="sxs-lookup"><span data-stu-id="126b7-120">The MED-V workspace .msi package is called *MED-V\_workspace\_x.msi*, where *x* is the version number.</span></span>

    <span data-ttu-id="126b7-121">例如， *MED-V\_workspace\_1.0.65.msi*。</span><span class="sxs-lookup"><span data-stu-id="126b7-121">For example, *MED-V\_workspace\_1.0.65.msi*.</span></span>

2.  <span data-ttu-id="126b7-122">双击 "MED-V" 工作区 .msi 程序包，然后按照安装向导中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="126b7-122">Double-click the MED-V workspace .msi package, and follow the installation wizard instructions.</span></span>

    **<span data-ttu-id="126b7-123">注意</span><span class="sxs-lookup"><span data-stu-id="126b7-123">Note</span></span>**  
    <span data-ttu-id="126b7-124">当发布新的 MED-V 版本并更新现有虚拟 PC 映像时，请卸载现有的 MED-V 工作区 .msi 程序包，重新启动计算机，然后安装新的 MED-V 工作区 .msi 程序包。</span><span class="sxs-lookup"><span data-stu-id="126b7-124">When a new MED-V version is released, and an existing Virtual PC image is updated, uninstall the existing MED-V workspace .msi package, reboot the computer, and install the new MED-V workspace .msi package.</span></span>



~~~
**Note**  
After the MED-V workspace .msi package is installed, other products that replace GINA cannot be installed.
~~~



## <a href="" id="bkmk-howtorunthevirtualmachineprerequisitestool"></a><span data-ttu-id="126b7-125">如何运行虚拟机先决条件工具</span><span class="sxs-lookup"><span data-stu-id="126b7-125">How to Run the Virtual Machine Prerequisites Tool</span></span>


<span data-ttu-id="126b7-126">虚拟机（VM）先决条件工具是一个向导，可自动执行若干先决条件。</span><span class="sxs-lookup"><span data-stu-id="126b7-126">The virtual machine (VM) prerequisites tool is a wizard that automates several of the prerequisites.</span></span>

**<span data-ttu-id="126b7-127">注意</span><span class="sxs-lookup"><span data-stu-id="126b7-127">Note</span></span>**  
<span data-ttu-id="126b7-128">尽管许多参数在向导中是可配置的，但 MED-V 的正常运行所需的属性不可配置。</span><span class="sxs-lookup"><span data-stu-id="126b7-128">Although many parameters are configurable in the wizard, the properties required for the proper functioning of MED-V are not configurable.</span></span>



**<span data-ttu-id="126b7-129">运行虚拟机先决条件工具</span><span class="sxs-lookup"><span data-stu-id="126b7-129">To run the virtual machine prerequisites tool</span></span>**

1.  <span data-ttu-id="126b7-130">安装 MED-V 工作区 .msi 程序包后，在 Windows 的 "**开始**" 菜单上，选择 "**所有程序" &gt; med-v &gt; VM 先决条件工具**。</span><span class="sxs-lookup"><span data-stu-id="126b7-130">After the MED-V workspace .msi package is installed, on the Windows **Start** menu, select **All Programs &gt; MED-V &gt; VM Prerequisites Tool**.</span></span>

    **<span data-ttu-id="126b7-131">注意</span><span class="sxs-lookup"><span data-stu-id="126b7-131">Note</span></span>**  
    <span data-ttu-id="126b7-132">运行虚拟机先决条件工具的用户必须具有本地管理员权限，并且必须是唯一登录的用户。</span><span class="sxs-lookup"><span data-stu-id="126b7-132">The user running the virtual machine prerequisites tool must have local administrator rights and must be the only user logged in.</span></span>



~~~
The **MED-V VM Prerequisite Wizard Welcome** page appears.
~~~

2. <span data-ttu-id="126b7-133">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="126b7-133">Click **Next**.</span></span>

3. <span data-ttu-id="126b7-134">在 " **Windows 设置**" 页面上，从以下 "可配置属性" 中，选择要配置的属性：</span><span class="sxs-lookup"><span data-stu-id="126b7-134">On the **Windows Settings** page, from the following configurable properties, select the ones to be configured:</span></span>

   -   **<span data-ttu-id="126b7-135">清除用户的个人历史记录信息</span><span class="sxs-lookup"><span data-stu-id="126b7-135">Clear users’ personal history information</span></span>**

   -   **<span data-ttu-id="126b7-136">清除本地配置文件临时目录</span><span class="sxs-lookup"><span data-stu-id="126b7-136">Clear local profiles temp directory</span></span>**

   -   **<span data-ttu-id="126b7-137">在以下 Windows 事件中禁用声音：开始、登录、注销</span><span class="sxs-lookup"><span data-stu-id="126b7-137">Disable sounds on following Windows events: start, logon, logoff</span></span>**

   **<span data-ttu-id="126b7-138">注意</span><span class="sxs-lookup"><span data-stu-id="126b7-138">Note</span></span>**  
   <span data-ttu-id="126b7-139">不要在组策略中启用 Windows 页面保护程序。</span><span class="sxs-lookup"><span data-stu-id="126b7-139">Do not enable Windows page saver in a group policy.</span></span>



4. <span data-ttu-id="126b7-140">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="126b7-140">Click **Next**.</span></span>

5. <span data-ttu-id="126b7-141">在 " **Internet Explorer 设置**" 页面上，从以下 "可配置属性" 中，选择要配置的属性：</span><span class="sxs-lookup"><span data-stu-id="126b7-141">On the **Internet Explorer Settings** page, from the following configurable properties, select the ones to be configured:</span></span>

   -   **<span data-ttu-id="126b7-142">不要使用自动完成功能</span><span class="sxs-lookup"><span data-stu-id="126b7-142">Don't use auto complete features</span></span>**

   -   **<span data-ttu-id="126b7-143">禁止重复使用 windows 启动快捷方式</span><span class="sxs-lookup"><span data-stu-id="126b7-143">Disable reuse of windows for launching shortcuts</span></span>**

   -   **<span data-ttu-id="126b7-144">清除浏览历史记录</span><span class="sxs-lookup"><span data-stu-id="126b7-144">Clear browsing history</span></span>**

   -   **<span data-ttu-id="126b7-145">在 Internet Explorer 7 中启用选项卡式浏览</span><span class="sxs-lookup"><span data-stu-id="126b7-145">Enable tabbed browsing in Internet Explorer 7</span></span>**

6. <span data-ttu-id="126b7-146">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="126b7-146">Click **Next**.</span></span>

7. <span data-ttu-id="126b7-147">在 " **Windows 服务**" 页面上，从以下 "可配置属性" 中，选择要配置的属性：</span><span class="sxs-lookup"><span data-stu-id="126b7-147">On the **Windows Services** page, from the following configurable properties, select the ones to be configured:</span></span>

   -   **<span data-ttu-id="126b7-148">安全中心服务</span><span class="sxs-lookup"><span data-stu-id="126b7-148">Security center service</span></span>**

   -   **<span data-ttu-id="126b7-149">任务计划程序服务</span><span class="sxs-lookup"><span data-stu-id="126b7-149">Task scheduler service</span></span>**

   -   **<span data-ttu-id="126b7-150">自动更新服务</span><span class="sxs-lookup"><span data-stu-id="126b7-150">Automatic updates service</span></span>**

   -   **<span data-ttu-id="126b7-151">系统还原服务</span><span class="sxs-lookup"><span data-stu-id="126b7-151">System restore service</span></span>**

   -   **<span data-ttu-id="126b7-152">索引服务</span><span class="sxs-lookup"><span data-stu-id="126b7-152">Indexing service</span></span>**

   -   **<span data-ttu-id="126b7-153">无线零配置</span><span class="sxs-lookup"><span data-stu-id="126b7-153">Wireless Zero Configuration</span></span>**

   -   **<span data-ttu-id="126b7-154">快速用户切换兼容性</span><span class="sxs-lookup"><span data-stu-id="126b7-154">Fast User Switching Compatibility</span></span>**

8. <span data-ttu-id="126b7-155">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="126b7-155">Click **Next**.</span></span>

9. <span data-ttu-id="126b7-156">在 " **Windows 自动登录**" 页面上，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="126b7-156">On the **Windows Auto Logon** page, do the following:</span></span>

   1.  <span data-ttu-id="126b7-157">选中 "**启用 Windows 自动登录**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="126b7-157">Select the **Enable Windows Auto Logon** check box.</span></span>

   2.  <span data-ttu-id="126b7-158">分配**用户名**和**密码**。</span><span class="sxs-lookup"><span data-stu-id="126b7-158">Assign a **User name** and **Password**.</span></span>

10. <span data-ttu-id="126b7-159">单击 "**应用**"，然后在出现的确认框中，单击 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="126b7-159">Click **Apply**, and in the confirmation box that appears, click **Yes**.</span></span>

11. <span data-ttu-id="126b7-160">在 "**摘要**" 页面上，单击 "**完成**" 退出向导</span><span class="sxs-lookup"><span data-stu-id="126b7-160">On the **Summary** page, click **Finish** to quit the wizard</span></span>

**<span data-ttu-id="126b7-161">注意</span><span class="sxs-lookup"><span data-stu-id="126b7-161">Note</span></span>**  
<span data-ttu-id="126b7-162">验证组策略不覆盖 "先决条件" 工具中设置的强制设置。</span><span class="sxs-lookup"><span data-stu-id="126b7-162">Verify that group policies do not overwrite the mandatory settings set in the prerequisites tool.</span></span>



## <a href="" id="bkmk-howtoconfiguremedvvirtualmachinemanualinstallationprerequisites"></a><span data-ttu-id="126b7-163">如何配置 MED-V 虚拟机手动安装先决条件</span><span class="sxs-lookup"><span data-stu-id="126b7-163">How to Configure MED-V Virtual Machine Manual Installation Prerequisites</span></span>


<span data-ttu-id="126b7-164">某些配置无法通过虚拟机先决条件工具进行配置，必须手动执行。</span><span class="sxs-lookup"><span data-stu-id="126b7-164">Several of the configurations cannot be configured through the virtual machine prerequisites tool and must be performed manually.</span></span>

-   <span data-ttu-id="126b7-165">虚拟机设置</span><span class="sxs-lookup"><span data-stu-id="126b7-165">Virtual Machine Settings</span></span>

    <span data-ttu-id="126b7-166">建议在 Microsoft Virtual PC 控制台中配置以下虚拟机设置：</span><span class="sxs-lookup"><span data-stu-id="126b7-166">It is recommended to configure the following virtual machine settings in the Microsoft Virtual PC console:</span></span>

    -   <span data-ttu-id="126b7-167">禁用软盘驱动器。</span><span class="sxs-lookup"><span data-stu-id="126b7-167">Disable floppy disk drives.</span></span>

    -   <span data-ttu-id="126b7-168">禁用撤消-磁盘（**设置 " &gt; 撤消-磁盘**"）。</span><span class="sxs-lookup"><span data-stu-id="126b7-168">Disable undo-disks (**Settings &gt; undo-disks**).</span></span>

    -   <span data-ttu-id="126b7-169">确保图像只有一个虚拟 CPU。</span><span class="sxs-lookup"><span data-stu-id="126b7-169">Ensure that the image has only one virtual CPU.</span></span>

    -   <span data-ttu-id="126b7-170">消除虚拟机和用户之间的交互，它们与已发布的应用程序（如需要用户输入的消息）无关。</span><span class="sxs-lookup"><span data-stu-id="126b7-170">Eliminate interactions between the virtual machine and the user, where they are not related to published applications (such as, messages requiring user input).</span></span>

-   <span data-ttu-id="126b7-171">图像设置</span><span class="sxs-lookup"><span data-stu-id="126b7-171">Image Settings</span></span>

    <span data-ttu-id="126b7-172">在映像内配置下列手动设置：</span><span class="sxs-lookup"><span data-stu-id="126b7-172">Configure the following manual settings inside the image:</span></span>

    1.  <span data-ttu-id="126b7-173">在 "**电源选项属性**" 窗口中，禁用休眠和睡眠。</span><span class="sxs-lookup"><span data-stu-id="126b7-173">In the **Power Options Properties** window, disable hibernation and sleep.</span></span>

    2.  <span data-ttu-id="126b7-174">应用最新的 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="126b7-174">Apply the most recent Windows updates.</span></span>

    3.  <span data-ttu-id="126b7-175">在 " **Windows 启动和故障恢复**" 对话框中的 "**系统故障**" 部分中，清除 "**自动重新启动**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="126b7-175">In the **Windows Startup and Recovery** dialog box, in the **System Failure** section, clear the **Automatically restart** check box.</span></span>

    4.  <span data-ttu-id="126b7-176">确保图像使用 VLK 许可证密钥。</span><span class="sxs-lookup"><span data-stu-id="126b7-176">Ensure that the image uses a VLK license key.</span></span>

-   <span data-ttu-id="126b7-177">安装 VPC 添加</span><span class="sxs-lookup"><span data-stu-id="126b7-177">Installing VPC Additions</span></span>

    <span data-ttu-id="126b7-178">在 "**操作**" 菜单上，选择 "**安装或更新虚拟机添加**"。</span><span class="sxs-lookup"><span data-stu-id="126b7-178">On the **Action** menu, select **Install or Update Virtual Machine Additions**.</span></span>

-   <span data-ttu-id="126b7-179">配置打印</span><span class="sxs-lookup"><span data-stu-id="126b7-179">Configuring Printing</span></span>

    <span data-ttu-id="126b7-180">你可以通过以下任一方式配置 MED-V 工作区中的打印：</span><span class="sxs-lookup"><span data-stu-id="126b7-180">You can configure printing from the MED-V workspace in either of the following ways:</span></span>

    -   <span data-ttu-id="126b7-181">将打印机添加到虚拟机。</span><span class="sxs-lookup"><span data-stu-id="126b7-181">Add a printer to the virtual machine.</span></span>

    -   <span data-ttu-id="126b7-182">允许打印在主机计算机上配置的打印机。</span><span class="sxs-lookup"><span data-stu-id="126b7-182">Allow printing with printers that are configured on the host computer.</span></span>

## <a href="" id="bkmk-howtoconfiguresysprepformedvimages"></a><span data-ttu-id="126b7-183">如何配置用于 MED-V 映像的 Sysprep</span><span class="sxs-lookup"><span data-stu-id="126b7-183">How to Configure Sysprep for MED-V Images</span></span>


<span data-ttu-id="126b7-184">在 MED-V 工作区中，可以配置 Sysprep，以便分配唯一的安全 ID （SID），特别是在单台计算机上运行多个 MED-V 工作区时。</span><span class="sxs-lookup"><span data-stu-id="126b7-184">In a MED-V workspace, Sysprep can be configured in order to assign unique security ID (SID), particularly when multiple MED-V workspaces are run on a single computer.</span></span> <span data-ttu-id="126b7-185">建议不要使用 Sysprep 加入域;请改为使用 MED-V join 域脚本操作，如[如何设置脚本操作](how-to-set-up-script-actions.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="126b7-185">It is not recommended to use Sysprep to join a domain; instead, use the MED-V join domain script action as described in [How to Set Up Script Actions](how-to-set-up-script-actions.md).</span></span>

**<span data-ttu-id="126b7-186">注意</span><span class="sxs-lookup"><span data-stu-id="126b7-186">Note</span></span>**  
<span data-ttu-id="126b7-187">Sysprep 是适用于 Windows 操作系统的 Microsoft 系统准备实用工具。</span><span class="sxs-lookup"><span data-stu-id="126b7-187">Sysprep is Microsoft's system preparation utility for the Windows operating system.</span></span>



**<span data-ttu-id="126b7-188">在 MED-V 工作区中配置 Sysprep</span><span class="sxs-lookup"><span data-stu-id="126b7-188">To configure Sysprep in a MED-V workspace</span></span>**

1.  <span data-ttu-id="126b7-189">在名为*Sysprep*的系统驱动器的根目录中创建目录。</span><span class="sxs-lookup"><span data-stu-id="126b7-189">Create a directory in the root of the system drive named *Sysprep*.</span></span>

2.  <span data-ttu-id="126b7-190">从 Windows 安装 CD 中，将*deploy.cab*提取到系统驱动器的根目录，或从 Microsoft 网站下载最新的部署工具更新。</span><span class="sxs-lookup"><span data-stu-id="126b7-190">From the Windows installation CD, extract *deploy.cab* to the root of the system drive, or download the latest Deployment Tools update from the Microsoft Web site.</span></span>

    -   <span data-ttu-id="126b7-191">对于 Windows 2000，请参阅适用[于 windows 2000 的部署工具更新](https://go.microsoft.com/fwlink/?LinkId=143001)。</span><span class="sxs-lookup"><span data-stu-id="126b7-191">For Windows 2000, see [Deployment Tools update for Windows 2000](https://go.microsoft.com/fwlink/?LinkId=143001).</span></span>

    -   <span data-ttu-id="126b7-192">对于 Windows XP，请参阅适用[于 WINDOWS xp 的部署工具更新](https://go.microsoft.com/fwlink/?LinkId=143000)。</span><span class="sxs-lookup"><span data-stu-id="126b7-192">For Windows XP, see [Deployment Tools update for Windows XP](https://go.microsoft.com/fwlink/?LinkId=143000).</span></span>

3.  <span data-ttu-id="126b7-193">运行**安装管理器**（setupmgr.exe）。</span><span class="sxs-lookup"><span data-stu-id="126b7-193">Run **Setup Manager** (setupmgr.exe).</span></span>

4.  <span data-ttu-id="126b7-194">按照安装管理器向导。</span><span class="sxs-lookup"><span data-stu-id="126b7-194">Follow the Setup Manager wizard.</span></span>

<span data-ttu-id="126b7-195">配置 Sysprep 并创建 MED-V 工作区后，必须执行 Sysprep。</span><span class="sxs-lookup"><span data-stu-id="126b7-195">After Sysprep is configured and the MED-V workspace is created, Sysprep must be executed.</span></span>

**<span data-ttu-id="126b7-196">运行 Sysprep</span><span class="sxs-lookup"><span data-stu-id="126b7-196">To run Sysprep</span></span>**

1.  <span data-ttu-id="126b7-197">在位于系统驱动器根目录下的 Sysprep 文件夹中，运行 "系统准备工具" （Sysprep.exe）。</span><span class="sxs-lookup"><span data-stu-id="126b7-197">From the Sysprep folder located in the root of the system drive, run the System Preparation Tool (Sysprep.exe).</span></span>

2.  <span data-ttu-id="126b7-198">在出现的 "警告消息" 框中，单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="126b7-198">In the warning message box that appears, click **OK**.</span></span>

3.  <span data-ttu-id="126b7-199">在 " **Sysprep 属性**" 对话框中，选择 "**不重置激活的宽限期**"，然后**使用 "最小化安装**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="126b7-199">In the **Sysprep Properties** dialog box, select the **Don't reset grace period for activation** and **Use Mini-Setup** check boxes.</span></span>

4.  <span data-ttu-id="126b7-200">单击 "重新**封装**"。</span><span class="sxs-lookup"><span data-stu-id="126b7-200">Click **Reseal**.</span></span>

5.  <span data-ttu-id="126b7-201">如果对显示的确认消息框中列出的信息不满意，请单击 "**取消**" 并更改选择。</span><span class="sxs-lookup"><span data-stu-id="126b7-201">If you are not satisfied with the information listed in the confirmation message box that appears, click **Cancel** and change the selections.</span></span>

6.  <span data-ttu-id="126b7-202">单击 **"确定"** 完成系统准备过程。</span><span class="sxs-lookup"><span data-stu-id="126b7-202">Click **OK** to complete the system preparation process.</span></span>

## <a href="" id="bkmk-turningoffmicrosoftvirtualpc"></a><span data-ttu-id="126b7-203">关闭 Microsoft Virtual PC</span><span class="sxs-lookup"><span data-stu-id="126b7-203">Turning Off Microsoft Virtual PC</span></span>


<span data-ttu-id="126b7-204">安装并配置所有组件后，关闭 "Microsoft 虚拟 PC"，然后选择 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="126b7-204">After all the components are installed and configured, close Microsoft Virtual PC and select **Turn Off**.</span></span>

## <span data-ttu-id="126b7-205">相关主题</span><span class="sxs-lookup"><span data-stu-id="126b7-205">Related topics</span></span>


<span data-ttu-id="126b7-206">创建 MED-V 图像[如何设置脚本操作](how-to-set-up-script-actions.md)</span><span class="sxs-lookup"><span data-stu-id="126b7-206">Creating a MED-V Image [How to Set Up Script Actions](how-to-set-up-script-actions.md)</span></span>









