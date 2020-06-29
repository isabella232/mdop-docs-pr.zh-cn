---
title: 如何使用 App-V 5.0 对新应用程序进行排序
description: 如何使用 App-V 5.0 对新应用程序进行排序
author: dansimp
ms.assetid: a263fa84-cd6d-4219-a5c2-eb6a553b826c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 13fdda066f79d918da1970e0cab6c1d6e60f6585
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798366"
---
# <span data-ttu-id="18047-103">如何使用 App-V 5.0 对新应用程序进行排序</span><span class="sxs-lookup"><span data-stu-id="18047-103">How to Sequence a New Application with App-V 5.0</span></span>


**<span data-ttu-id="18047-104">在开始排序之前查看或执行此操作</span><span class="sxs-lookup"><span data-stu-id="18047-104">To review or do before you start sequencing</span></span>**

1.  <span data-ttu-id="18047-105">确定要创建的虚拟化应用程序包的类型：</span><span class="sxs-lookup"><span data-stu-id="18047-105">Determine the type of virtualized application package you want to create:</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="18047-106">应用程序类型</span><span class="sxs-lookup"><span data-stu-id="18047-106">Application type</span></span></th>
    <th align="left"><span data-ttu-id="18047-107">描述</span><span class="sxs-lookup"><span data-stu-id="18047-107">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="18047-108">Standard</span><span class="sxs-lookup"><span data-stu-id="18047-108">Standard</span></span></p></td>
    <td align="left"><p><span data-ttu-id="18047-109">创建一个包含应用程序或一组应用程序的程序包。</span><span class="sxs-lookup"><span data-stu-id="18047-109">Creates a package that contains an application or a suite of applications.</span></span> <span data-ttu-id="18047-110">这是大多数应用程序类型的首选选项。</span><span class="sxs-lookup"><span data-stu-id="18047-110">This is the preferred option for most application types.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="18047-111">加载项或插件</span><span class="sxs-lookup"><span data-stu-id="18047-111">Add-on or plug-in</span></span></p></td>
    <td align="left"><p><span data-ttu-id="18047-112">创建扩展标准应用程序（例如 Microsoft Excel 插件）的功能的程序包。</span><span class="sxs-lookup"><span data-stu-id="18047-112">Creates a package that extends the functionality of a standard application, for example, a plug-in for Microsoft Excel.</span></span> <span data-ttu-id="18047-113">此外，你可以为本机安装的应用程序或使用连接组链接的其他程序包使用插件。</span><span class="sxs-lookup"><span data-stu-id="18047-113">Additionally, you can use plug-ins for natively installed applications, or for another package that is linked by using connection groups.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="18047-114">中间件</span><span class="sxs-lookup"><span data-stu-id="18047-114">Middleware</span></span></p></td>
    <td align="left"><p><span data-ttu-id="18047-115">创建标准应用程序（例如，Java）所需的程序包。</span><span class="sxs-lookup"><span data-stu-id="18047-115">Creates a package that is required by a standard application, for example, Java.</span></span> <span data-ttu-id="18047-116">中间件程序包用于通过使用连接组链接到其他程序包。</span><span class="sxs-lookup"><span data-stu-id="18047-116">Middleware packages are used for linking to other packages by using connection groups.</span></span></p></td>
    </tr>
    </tbody>
    </table>



2.  <span data-ttu-id="18047-117">将所有所需的安装文件复制到运行 sequencer 的计算机。</span><span class="sxs-lookup"><span data-stu-id="18047-117">Copy all required installation files to the computer that is running the sequencer.</span></span>

3.  <span data-ttu-id="18047-118">在对应用程序进行排序之前制作虚拟环境的备份映像，并在每次完成应用程序序列化后恢复到该映像。</span><span class="sxs-lookup"><span data-stu-id="18047-118">Make a backup image of your virtual environment before sequencing an application, and then revert to that image each time after you finish sequencing an application.</span></span>

4.  <span data-ttu-id="18047-119">查看以下项目：</span><span class="sxs-lookup"><span data-stu-id="18047-119">Review the following items:</span></span>

    -   <span data-ttu-id="18047-120">如果应用程序安装程序将安全访问更改为新的或现有的文件或目录，则不会在程序包中捕获这些更改。</span><span class="sxs-lookup"><span data-stu-id="18047-120">If an application installer changes the security access to a new or existing file or directory, those changes are not captured in the package.</span></span>

    -   <span data-ttu-id="18047-121">如果已为虚拟化程序包的目标卷禁用短路径，则还必须将程序包序列化到已创建且仍具有短路径禁用的卷。</span><span class="sxs-lookup"><span data-stu-id="18047-121">If short paths have been disabled for the virtualized package’s target volume, you must also sequence the package to a volume that was created and still has short-paths disabled.</span></span> <span data-ttu-id="18047-122">它不能是系统卷。</span><span class="sxs-lookup"><span data-stu-id="18047-122">It cannot be the system volume.</span></span>

    -   <span data-ttu-id="18047-123">从 app-v 5.0 SP3 开始，主虚拟应用程序目录（PVAD）处于隐藏状态，但你可以将其重新打开。</span><span class="sxs-lookup"><span data-stu-id="18047-123">Starting in App-V 5.0 SP3, the primary virtual application directory (PVAD) is hidden, but you can turn it back on.</span></span> <span data-ttu-id="18047-124">请参阅[关于 App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-pvad-hidden)。</span><span class="sxs-lookup"><span data-stu-id="18047-124">See [About App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-pvad-hidden).</span></span>

**<span data-ttu-id="18047-125">对新标准应用程序进行序列化</span><span class="sxs-lookup"><span data-stu-id="18047-125">To sequence a new standard application</span></span>**

1.  <span data-ttu-id="18047-126">在运行 sequencer 的计算机上，单击 "**所有程序**"，然后单击 " **Microsoft**application virtualization sequencer"，然后单击 " **microsoft application virtualization sequencer**"。</span><span class="sxs-lookup"><span data-stu-id="18047-126">On the computer that runs the sequencer, click **All Programs**, and then Click **Microsoft Application Virtualization**, and then click **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="18047-127">在排序器中，单击 "**创建新的虚拟应用程序包**"。</span><span class="sxs-lookup"><span data-stu-id="18047-127">In the sequencer, click **Create a New Virtual Application Package**.</span></span> <span data-ttu-id="18047-128">选择 "**创建程序包（默认）**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="18047-128">Select **Create Package (default)**, and then click **Next**.</span></span>

3.  <span data-ttu-id="18047-129">在 "**准备计算机**" 页面上，查看可能导致程序包创建失败或可能导致程序包包含不必要的数据的问题。</span><span class="sxs-lookup"><span data-stu-id="18047-129">On the **Prepare Computer** page, review the issues that could cause the package creation to fail or could cause the package to contain unnecessary data.</span></span> <span data-ttu-id="18047-130">您应该先解决所有潜在问题，然后再继续。</span><span class="sxs-lookup"><span data-stu-id="18047-130">You should resolve all potential issues before you continue.</span></span> <span data-ttu-id="18047-131">进行更正后，单击 "**刷新**" 以显示更新的信息。</span><span class="sxs-lookup"><span data-stu-id="18047-131">After making any corrections, click **Refresh** to display the updated information.</span></span> <span data-ttu-id="18047-132">解决所有潜在问题后，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="18047-132">After you have resolved all potential issues, click **Next**.</span></span>

    **<span data-ttu-id="18047-133">重要提示</span><span class="sxs-lookup"><span data-stu-id="18047-133">Important</span></span>**  
    <span data-ttu-id="18047-134">如果需要禁用病毒扫描软件，应首先扫描运行 sequencer 的计算机，以确保不会将不需要的或恶意文件添加到程序包。</span><span class="sxs-lookup"><span data-stu-id="18047-134">If you are required to disable virus scanning software, you should first scan the computer that runs the sequencer in order to ensure that no unwanted or malicious files could be added to the package.</span></span>



4.  <span data-ttu-id="18047-135">在 "**应用程序类型**" 页面上，单击 "**标准应用程序（默认）** " 复选框，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="18047-135">On the **Type of Application** page, click the **Standard Application (default)** check box, and then click **Next**.</span></span>

5.  <span data-ttu-id="18047-136">在 "**选择安装程序**" 页面上，单击 "**浏览**" 并指定应用程序的安装文件。</span><span class="sxs-lookup"><span data-stu-id="18047-136">On the **Select Installer** page, click **Browse** and specify the installation file for the application.</span></span>

    **<span data-ttu-id="18047-137">注意</span><span class="sxs-lookup"><span data-stu-id="18047-137">Note</span></span>**  
    <span data-ttu-id="18047-138">如果指定的应用程序安装程序修改了对文件或目录的安全访问权限（现有的或新的），则不会将关联的更改捕获到程序包中。</span><span class="sxs-lookup"><span data-stu-id="18047-138">If the specified application installer modifies security access to a file or directory, existing or new, the associated changes will not be captured into the package.</span></span>



~~~
If the application does not have an associated installer file and you plan to run all installation steps manually, select the **Perform a Custom Installation** check box, and then Click **Next**.
~~~

6. <span data-ttu-id="18047-139">在 "**程序包名称**" 页面上，键入将与该程序包关联的名称。</span><span class="sxs-lookup"><span data-stu-id="18047-139">On the **Package Name** page, type a name that will be associated with the package.</span></span> <span data-ttu-id="18047-140">使用有助于标识将添加到程序包的应用程序用途和版本的名称。</span><span class="sxs-lookup"><span data-stu-id="18047-140">Use a name that helps identify the purpose and version of the application that will be added to the package.</span></span> <span data-ttu-id="18047-141">程序包名称将显示在 app-v 5.0 管理控制台中。</span><span class="sxs-lookup"><span data-stu-id="18047-141">The package name is displayed in the App-V 5.0 Management Console.</span></span>

   <span data-ttu-id="18047-142">**主虚拟应用程序目录**显示将在目标计算机上安装应用程序的路径。</span><span class="sxs-lookup"><span data-stu-id="18047-142">The **Primary Virtual Application Directory** displays the path where the application will be installed on target computers.</span></span> <span data-ttu-id="18047-143">若要指定此位置，请选择 "**浏览**"。</span><span class="sxs-lookup"><span data-stu-id="18047-143">To specify this location, select **Browse**.</span></span>

   **<span data-ttu-id="18047-144">注意</span><span class="sxs-lookup"><span data-stu-id="18047-144">Note</span></span>**  
   <span data-ttu-id="18047-145">从 app-v 5.0 SP3 开始，主虚拟应用程序目录（PVAD）处于隐藏状态，但你可以将其重新打开。</span><span class="sxs-lookup"><span data-stu-id="18047-145">Starting in App-V 5.0 SP3, the primary virtual application directory (PVAD) is hidden, but you can turn it back on.</span></span> <span data-ttu-id="18047-146">请参阅[关于 App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-pvad-hidden)。</span><span class="sxs-lookup"><span data-stu-id="18047-146">See [About App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-pvad-hidden).</span></span>



~~~
**Important**  
The primary application virtual directory should match the installation location for the application that is being sequenced. For example, if you install Notepad to **C:\\Program Files\\Notepad**; you should configure **C:\\Program Files\\Notepad** as your primary virtual directory. Alternatively, you can choose to set **C:\\Notepad** as the primary virtual application directory, as long as during installation time, you configure the installer to install to **C:\\Notepad**. Editing the Application Virtualization path is an advanced configuration task. For most applications, the default path is recommended for the following reasons:

-   Application Compatibility. Some virtualized applications will not function correctly, or will fail to open if the directories are not configured with identical virtual directory paths.

-   Performance. Since no file system redirection is required, the runtime performance can improve.



**Tip**  
It is recommended that prior to Sequencing an application, you open the associated installer to determine the default installation directory, and then configure that location as the **Primary Virtual Application Directory**.



Click **Next**.
~~~

7. <span data-ttu-id="18047-147">在 "**安装**" 页面上，当 sequencer 和应用程序安装准备就绪时，可以继续安装应用程序，以便排序器可以监视安装过程。</span><span class="sxs-lookup"><span data-stu-id="18047-147">On the **Installation** page, when the sequencer and application installer are ready you can proceed to install the application so that the sequencer can monitor the installation process.</span></span>

   **<span data-ttu-id="18047-148">重要提示</span><span class="sxs-lookup"><span data-stu-id="18047-148">Important</span></span>**  
   <span data-ttu-id="18047-149">你应该始终将应用程序安装到安全位置，并确保在监视期间没有其他用户登录到运行 sequencer 的计算机。</span><span class="sxs-lookup"><span data-stu-id="18047-149">You should always install applications to a secure location and make sure no other users are logged on to the computer running the sequencer during monitoring.</span></span>



~~~
Use the application's installation process to perform the installation. If additional installation files must be run as part of the installation, click **Run** to locate and run the additional installation files. When you are finished with the installation, select **I am finished installing**. Click **Next**.
~~~

8. <span data-ttu-id="18047-150">在 "**安装**" 页面上，在 sequencer 配置虚拟化应用程序包时等待。</span><span class="sxs-lookup"><span data-stu-id="18047-150">On the **Installation** page, wait while the sequencer configures the virtualized application package.</span></span>

9. <span data-ttu-id="18047-151">在 "**配置软件**" 页面上，选择运行程序包中包含的程序。</span><span class="sxs-lookup"><span data-stu-id="18047-151">On the **Configure Software** page, optionally run the programs contained in the package.</span></span> <span data-ttu-id="18047-152">此步骤允许你在目标计算机上部署和运行程序包之前完成任何必要的许可证或配置任务。</span><span class="sxs-lookup"><span data-stu-id="18047-152">This step allows you to complete any necessary license or configuration tasks before you deploy and run the package on target computers.</span></span> <span data-ttu-id="18047-153">若要一次运行所有程序，请至少选择一个程序，然后单击 "**全部运行**"。</span><span class="sxs-lookup"><span data-stu-id="18047-153">To run all the programs at one time, select at least one program, and then click **Run All**.</span></span> <span data-ttu-id="18047-154">若要运行特定程序，请选择该程序或程序，然后单击 "**运行所选**"。</span><span class="sxs-lookup"><span data-stu-id="18047-154">To run specific programs, select the program or programs, and then click **Run Selected**.</span></span> <span data-ttu-id="18047-155">完成所需的配置任务，然后关闭应用程序。</span><span class="sxs-lookup"><span data-stu-id="18047-155">Complete the required configuration tasks and then close the applications.</span></span> <span data-ttu-id="18047-156">您可能需要等待几分钟才能让所有程序运行。</span><span class="sxs-lookup"><span data-stu-id="18047-156">You may need to wait several minutes for all programs to run.</span></span>

   **<span data-ttu-id="18047-157">注意</span><span class="sxs-lookup"><span data-stu-id="18047-157">Note</span></span>**  
   <span data-ttu-id="18047-158">若要对列表中不可用的任何应用程序运行第一次使用任务，请打开该应用程序。</span><span class="sxs-lookup"><span data-stu-id="18047-158">To run first-use tasks for any application that is not available in the list, open the application.</span></span> <span data-ttu-id="18047-159">相关信息将在此步骤中捕获。</span><span class="sxs-lookup"><span data-stu-id="18047-159">The associated information will be captured during this step.</span></span>



~~~
Click **Next**.
~~~

10. <span data-ttu-id="18047-160">在 "**安装报告**" 页面上，您可以查看刚刚排序的虚拟化应用程序包的相关信息。</span><span class="sxs-lookup"><span data-stu-id="18047-160">On the **Installation Report** page, you can review information about the virtualized application package you have just sequenced.</span></span> <span data-ttu-id="18047-161">在**其他信息**中，双击事件以获取更详细的信息。</span><span class="sxs-lookup"><span data-stu-id="18047-161">In **Additional Information**, double-click an event to obtain more detailed information.</span></span> <span data-ttu-id="18047-162">若要继续，请单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="18047-162">To proceed, click **Next**.</span></span>

11. <span data-ttu-id="18047-163">将显示 "**自定义**" 页面。</span><span class="sxs-lookup"><span data-stu-id="18047-163">The **Customize** page is displayed.</span></span> <span data-ttu-id="18047-164">如果已完成安装和配置虚拟应用程序，请选择 "**立即停止**"，然后跳到此过程的步骤14。</span><span class="sxs-lookup"><span data-stu-id="18047-164">If you are finished installing and configuring the virtual application, select **Stop now** and skip to step 14 of this procedure.</span></span> <span data-ttu-id="18047-165">若要执行下列任一自定义操作，请选择 "**自定义**"。</span><span class="sxs-lookup"><span data-stu-id="18047-165">To perform either of the following customizations, select **Customize**.</span></span>

    -   <span data-ttu-id="18047-166">准备用于流式处理的虚拟包。</span><span class="sxs-lookup"><span data-stu-id="18047-166">Prepare the virtual package for streaming.</span></span> <span data-ttu-id="18047-167">流改进了在目标计算机上运行虚拟应用程序包时的体验。</span><span class="sxs-lookup"><span data-stu-id="18047-167">Streaming improves the experience when the virtual application package is run on target computers.</span></span>

    -   <span data-ttu-id="18047-168">指定可以运行此程序包的操作系统。</span><span class="sxs-lookup"><span data-stu-id="18047-168">Specify the operating systems that can run this package.</span></span>

    <span data-ttu-id="18047-169">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="18047-169">Click **Next**.</span></span>

12. <span data-ttu-id="18047-170">在 "**流**" 页面上，运行每个程序，以便可以在目标计算机上对其进行优化和更高效地运行。</span><span class="sxs-lookup"><span data-stu-id="18047-170">On the **Streaming** page, run each program so that it can be optimized and run more efficiently on target computers.</span></span> <span data-ttu-id="18047-171">运行所有应用程序可能需要几分钟的时间。</span><span class="sxs-lookup"><span data-stu-id="18047-171">It can take several minutes for all the applications to run.</span></span> <span data-ttu-id="18047-172">在所有应用程序运行后，关闭每个应用程序，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="18047-172">After all applications have run, close each of the applications, and then click **Next**.</span></span>

   **<span data-ttu-id="18047-173">注意</span><span class="sxs-lookup"><span data-stu-id="18047-173">Note</span></span>**  
   <span data-ttu-id="18047-174">如果在此步骤中不打开任何应用程序，则默认流方法为按需流式传递。</span><span class="sxs-lookup"><span data-stu-id="18047-174">If you do not open any applications during this step, the default streaming method is on-demand streaming delivery.</span></span> <span data-ttu-id="18047-175">这意味着将按位下载应用程序，直到可以打开应用程序，然后根据后台加载的配置，将加载应用程序的其余部分。</span><span class="sxs-lookup"><span data-stu-id="18047-175">This means applications will be downloaded bit by bit until it can be opened, and then depending on how the background loading is configured, will load the rest of the application.</span></span>



13. <span data-ttu-id="18047-176">在 "**目标操作系统**" 页面上，指定可运行此程序包的操作系统。</span><span class="sxs-lookup"><span data-stu-id="18047-176">On the **Target OS** page, specify the operating systems that can run this package.</span></span> <span data-ttu-id="18047-177">若要允许环境中的所有受支持的操作系统运行此程序包，请选择 "**允许此程序包在任何操作系统上运行**"。</span><span class="sxs-lookup"><span data-stu-id="18047-177">To allow all supported operating systems in your environment to run this package, select **Allow this package to run on any operating system**.</span></span> <span data-ttu-id="18047-178">若要将此程序包配置为仅在特定操作系统上运行，请选择 "**仅允许此程序包在以下操作系统上运行**"，然后选择可以运行此程序包的操作系统。</span><span class="sxs-lookup"><span data-stu-id="18047-178">To configure this package to run only on specific operating systems, select **Allow this package to run only on the following operating systems** and select the operating systems that can run this package.</span></span> <span data-ttu-id="18047-179">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="18047-179">Click **Next**.</span></span>

   **<span data-ttu-id="18047-180">重要提示</span><span class="sxs-lookup"><span data-stu-id="18047-180">Important</span></span>**  
   <span data-ttu-id="18047-181">请确保你在此处指定的操作系统由你正在排序的应用程序支持。</span><span class="sxs-lookup"><span data-stu-id="18047-181">Make sure that the operating systems you specify here are supported by the application you are sequencing.</span></span>



14. <span data-ttu-id="18047-182">将显示 "**创建程序包**" 页面。</span><span class="sxs-lookup"><span data-stu-id="18047-182">The **Create Package** page is displayed.</span></span> <span data-ttu-id="18047-183">若要在不保存的情况下修改程序包，请选择 **"继续" 以在不保存的情况下使用程序包编辑器修改程序包**。</span><span class="sxs-lookup"><span data-stu-id="18047-183">To modify the package without saving it, select **Continue to modify package without saving using the package editor**.</span></span> <span data-ttu-id="18047-184">此选项将在 sequencer 控制台中打开程序包，以便你可以在保存包之前对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="18047-184">This option opens the package in the sequencer console so that you can modify the package before it is saved.</span></span> <span data-ttu-id="18047-185">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="18047-185">Click **Next**.</span></span>

   <span data-ttu-id="18047-186">若要立即保存程序包，请选择 **"立即保存程序包"** （默认）。</span><span class="sxs-lookup"><span data-stu-id="18047-186">To save the package immediately, select **Save the package now** (default).</span></span> <span data-ttu-id="18047-187">添加要与程序包关联的可选**注释**。</span><span class="sxs-lookup"><span data-stu-id="18047-187">Add optional **Comments** to be associated with the package.</span></span> <span data-ttu-id="18047-188">注释适用于标识程序版本和有关程序包的其他信息。</span><span class="sxs-lookup"><span data-stu-id="18047-188">Comments are useful for identifying the program version and other information about the package.</span></span>

   **<span data-ttu-id="18047-189">重要提示</span><span class="sxs-lookup"><span data-stu-id="18047-189">Important</span></span>**  
   <span data-ttu-id="18047-190">系统不支持**批注**和**说明**中的不可打印字符。</span><span class="sxs-lookup"><span data-stu-id="18047-190">The system does not support non-printable characters in **Comments** and **Descriptions**.</span></span>



~~~
The default **Save Location** is also displayed on this page. To change the default location, click **Browse** and specify the new location. Click **Create**.
~~~

15. <span data-ttu-id="18047-191">将显示**完成**页。</span><span class="sxs-lookup"><span data-stu-id="18047-191">The **Completion** page is displayed.</span></span> <span data-ttu-id="18047-192">根据需要查看 "**虚拟应用程序包" 报表**窗格中的信息，然后单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="18047-192">Review the information in the **Virtual Application Package Report** pane as needed, then click **Close**.</span></span> <span data-ttu-id="18047-193">也可以在创建程序包的目录中的**Report.xml**文件中找到此信息。</span><span class="sxs-lookup"><span data-stu-id="18047-193">This information is also available in the **Report.xml** file that is located in the directory where the package was created.</span></span>

   <span data-ttu-id="18047-194">程序包现在在 sequencer 中可用。</span><span class="sxs-lookup"><span data-stu-id="18047-194">The package is now available in the sequencer.</span></span>

   **<span data-ttu-id="18047-195">重要提示</span><span class="sxs-lookup"><span data-stu-id="18047-195">Important</span></span>**  
   <span data-ttu-id="18047-196">成功创建虚拟应用程序包后，不能在运行 sequencer 的计算机上运行虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="18047-196">After you have successfully created a virtual application package, you cannot run the virtual application package on the computer that is running the sequencer.</span></span>



**<span data-ttu-id="18047-197">对加载项或插件应用程序进行排序</span><span class="sxs-lookup"><span data-stu-id="18047-197">To sequence an add-on or plug-in application</span></span>**

1.  

    **<span data-ttu-id="18047-198">注意</span><span class="sxs-lookup"><span data-stu-id="18047-198">Note</span></span>**  
    <span data-ttu-id="18047-199">在执行以下过程之前，请在运行 sequencer 的计算机上本地安装父应用程序。</span><span class="sxs-lookup"><span data-stu-id="18047-199">Before performing the following procedure, install the parent application locally on the computer that is running the sequencer.</span></span> <span data-ttu-id="18047-200">或者，如果你已将父应用程序虚拟化，则可以按照加载项或插件工作流中的步骤将父应用程序解压缩到计算机上。</span><span class="sxs-lookup"><span data-stu-id="18047-200">Or if you have the parent application virtualized, you can follow the steps in the add-on or plug-in workflow to unpack the parent application on the computer.</span></span>

    <span data-ttu-id="18047-201">例如，如果要为 Microsoft Excel 的插件进行排序，请在运行 sequencer 的计算机上本地安装 Microsoft Excel。</span><span class="sxs-lookup"><span data-stu-id="18047-201">For example, if you are sequencing a plug-in for Microsoft Excel, install Microsoft Excel locally on the computer that is running the sequencer.</span></span> <span data-ttu-id="18047-202">还在目标计算机上安装应用程序的同一目录中安装父应用程序。</span><span class="sxs-lookup"><span data-stu-id="18047-202">Also install the parent application in the same directory where the application is installed on target computers.</span></span> <span data-ttu-id="18047-203">如果要对现有虚拟应用程序包使用插件或加载项，请在创建父虚拟应用程序包时使用的同一虚拟应用程序驱动器上安装该应用程序。</span><span class="sxs-lookup"><span data-stu-id="18047-203">If the plug-in or add-on is going to be used with an existing virtual application package, install the application on the same virtual application drive that was used when you created the parent virtual application package.</span></span>



~~~
On the computer that runs the sequencer, click **All Programs**, and then Click **Microsoft Application Virtualization**, and then click **Microsoft Application Virtualization Sequencer**.
~~~

2. <span data-ttu-id="18047-204">*<strong><em>在排序器中，单击 "* </em> 创建新的虚拟应用程序包" </strong> 。</span><span class="sxs-lookup"><span data-stu-id="18047-204">\*<strong><em>In the sequencer, click \*</em>Create a New Virtual Application Package</strong>.</span></span> <span data-ttu-id="18047-205">选择 "**创建程序包（默认）**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="18047-205">Select **Create Package (default)**, and then click **Next**.</span></span>

3. <span data-ttu-id="18047-206">在 "**准备计算机**" 页面上，查看可能导致程序包创建失败或可能导致程序包包含不必要的数据的问题。</span><span class="sxs-lookup"><span data-stu-id="18047-206">On the **Prepare Computer** page, review the issues that might cause the package creation to fail or could cause the package to contain unnecessary data.</span></span> <span data-ttu-id="18047-207">您应该先解决所有潜在问题，然后再继续。</span><span class="sxs-lookup"><span data-stu-id="18047-207">You should resolve all potential issues before you continue.</span></span> <span data-ttu-id="18047-208">进行更正后，单击 "**刷新**" 以显示更新的信息。</span><span class="sxs-lookup"><span data-stu-id="18047-208">After making any corrections, click **Refresh** to display the updated information.</span></span> <span data-ttu-id="18047-209">解决所有潜在问题后，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="18047-209">After you have resolved all potential issues, click **Next**.</span></span>

   **<span data-ttu-id="18047-210">重要提示</span><span class="sxs-lookup"><span data-stu-id="18047-210">Important</span></span>**  
   <span data-ttu-id="18047-211">如果需要禁用病毒扫描软件，应首先扫描运行 sequencer 的计算机，以确保不会将不需要的或恶意文件添加到程序包。</span><span class="sxs-lookup"><span data-stu-id="18047-211">If you are required to disable virus scanning software, you should first scan the computer that runs the sequencer in order to ensure that no unwanted or malicious files could be added to the package.</span></span>



4. <span data-ttu-id="18047-212">在 "**应用程序类型**" 页面上，选择 "加载项"**或 "插件**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="18047-212">On the **Type of Application** page, select **Add-on or Plug-in**, and then click **Next**.</span></span>

5. <span data-ttu-id="18047-213">在 "**选择安装程序**" 页面上，单击 "**浏览**" 并为加载项或插件指定安装文件。</span><span class="sxs-lookup"><span data-stu-id="18047-213">On the **Select Installer** page, click **Browse** and specify the installation file for the add-on or plug-in.</span></span> <span data-ttu-id="18047-214">如果加载项或插件没有关联的安装程序文件，并且你计划手动运行所有安装步骤，请选中 "**选择此选项以执行自定义安装**" 复选框，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="18047-214">If the add-on or plug-in does not have an associated installer file and you plan to run all installation steps manually, select the **Select this option to perform a custom installation** check box, and then click **Next**.</span></span>

6. <span data-ttu-id="18047-215">在 "**安装主页**" 上，确保在运行 sequencer 的计算机上安装了主应用程序。</span><span class="sxs-lookup"><span data-stu-id="18047-215">On the **Install Primary** page, ensure that the primary application is installed on the computer that runs the sequencer.</span></span> <span data-ttu-id="18047-216">或者，你可以展开本地保存在运行 sequencer 的计算机上的现有程序包。</span><span class="sxs-lookup"><span data-stu-id="18047-216">Alternatively, you can expand an existing package that has been saved locally on the computer that runs the sequencer.</span></span> <span data-ttu-id="18047-217">若要执行此操作，请单击 "**展开包**"，然后选择程序包。</span><span class="sxs-lookup"><span data-stu-id="18047-217">To do this, click **Expand Package**, and then select the package.</span></span> <span data-ttu-id="18047-218">展开或安装父程序后，选择 **"我已安装主要父程序"**。</span><span class="sxs-lookup"><span data-stu-id="18047-218">After you have expanded or installed the parent program, select **I have installed the primary parent program**.</span></span>

   <span data-ttu-id="18047-219">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="18047-219">Click **Next**.</span></span>

7. <span data-ttu-id="18047-220">在 "**程序包名称**" 页面上，键入将与该程序包关联的名称。</span><span class="sxs-lookup"><span data-stu-id="18047-220">On the **Package Name** page, type a name that will be associated with the package.</span></span> <span data-ttu-id="18047-221">使用有助于标识将添加到程序包的应用程序用途和版本的名称。</span><span class="sxs-lookup"><span data-stu-id="18047-221">Use a name that helps identify the purpose and version of the application that will be added to the package.</span></span> <span data-ttu-id="18047-222">程序包名称将显示在 app-v 5.0 管理控制台中。</span><span class="sxs-lookup"><span data-stu-id="18047-222">The package name will be displayed in the App-V 5.0 Management Console.</span></span> <span data-ttu-id="18047-223">**主虚拟应用程序目录**显示将安装应用程序的路径。</span><span class="sxs-lookup"><span data-stu-id="18047-223">The **Primary Virtual Application Directory** displays the path where the application will be installed.</span></span> <span data-ttu-id="18047-224">若要指定此位置，请键入路径，或单击 "**浏览**"。</span><span class="sxs-lookup"><span data-stu-id="18047-224">To specify this location, type the path, or click **Browse**.</span></span>

   **<span data-ttu-id="18047-225">注意</span><span class="sxs-lookup"><span data-stu-id="18047-225">Note</span></span>**  
   <span data-ttu-id="18047-226">从 app-v 5.0 SP3 开始，主虚拟应用程序目录（PVAD）处于隐藏状态，但你可以将其重新打开。</span><span class="sxs-lookup"><span data-stu-id="18047-226">Starting in App-V 5.0 SP3, the primary virtual application directory (PVAD) is hidden, but you can turn it back on.</span></span> <span data-ttu-id="18047-227">请参阅[关于 App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-pvad-hidden)。</span><span class="sxs-lookup"><span data-stu-id="18047-227">See [About App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-pvad-hidden).</span></span>



~~~
Click **Next**.
~~~

8. <span data-ttu-id="18047-228">在 "**安装**" 页面上，当 sequencer 和应用程序安装准备就绪时，可以继续安装插件或加载项应用程序，以便排序器可以监视安装过程。</span><span class="sxs-lookup"><span data-stu-id="18047-228">On the **Installation** page, when the sequencer and application installer are ready you can proceed to install the plug-in or add-in application so the sequencer can monitor the installation process.</span></span> <span data-ttu-id="18047-229">使用应用程序的安装过程执行安装。</span><span class="sxs-lookup"><span data-stu-id="18047-229">Use the application's installation process to perform the installation.</span></span> <span data-ttu-id="18047-230">如果必须在安装过程中运行其他安装文件，请单击 "**运行**"，然后找到并运行其他安装文件。</span><span class="sxs-lookup"><span data-stu-id="18047-230">If additional installation files must be run as part of the installation, click **Run** and locate and run the additional installation files.</span></span> <span data-ttu-id="18047-231">完成安装后，选择 "**我已完成安装**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="18047-231">When you are finished with the installation, select **I am finished installing**, and then click **Next**.</span></span>

9. <span data-ttu-id="18047-232">在 "**安装报告**" 页面上，您可以查看刚刚排序的虚拟应用程序包的相关信息。</span><span class="sxs-lookup"><span data-stu-id="18047-232">On the **Installation Report** page, you can review information about the virtual application package that you just sequenced.</span></span> <span data-ttu-id="18047-233">有关**其他信息**中显示的信息的更多详细说明，请双击该事件。</span><span class="sxs-lookup"><span data-stu-id="18047-233">For a more detailed explanation about the information displayed in **Additional Information**, double-click the event.</span></span> <span data-ttu-id="18047-234">查看信息后，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="18047-234">After you have reviewed the information, click **Next**.</span></span>

10. <span data-ttu-id="18047-235">将显示 "**自定义**" 页面。</span><span class="sxs-lookup"><span data-stu-id="18047-235">The **Customize** page is displayed.</span></span> <span data-ttu-id="18047-236">如果已完成安装和配置虚拟应用程序，请选择 "**立即停止**"，然后跳到此过程的步骤12。</span><span class="sxs-lookup"><span data-stu-id="18047-236">If you are finished installing and configuring the virtual application, select **Stop now** and skip to step 12 of this procedure.</span></span> <span data-ttu-id="18047-237">若要执行下列任一自定义操作，请选择 "**自定义**"。</span><span class="sxs-lookup"><span data-stu-id="18047-237">To perform either of the following customizations, select **Customize**.</span></span>

    -   <span data-ttu-id="18047-238">优化数据包在慢速或不可靠网络上的运行方式。</span><span class="sxs-lookup"><span data-stu-id="18047-238">Optimize how the package will run across a slow or unreliable network.</span></span>

    -   <span data-ttu-id="18047-239">指定可以运行此程序包的操作系统。</span><span class="sxs-lookup"><span data-stu-id="18047-239">Specify the operating systems that can run this package.</span></span>

    <span data-ttu-id="18047-240">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="18047-240">Click **Next**.</span></span>

11. <span data-ttu-id="18047-241">在 "**流**" 页面上，运行每个程序，以便可以在目标计算机上对其进行优化和更高效地运行。</span><span class="sxs-lookup"><span data-stu-id="18047-241">On the **Streaming** page, run each program so that it can be optimized and run more efficiently on target computers.</span></span> <span data-ttu-id="18047-242">流改进了在高延迟网络上的目标计算机上运行虚拟应用程序包时的体验。</span><span class="sxs-lookup"><span data-stu-id="18047-242">Streaming improves the experience when the virtual application package is run on target computers on high-latency networks.</span></span> <span data-ttu-id="18047-243">运行所有应用程序可能需要几分钟的时间。</span><span class="sxs-lookup"><span data-stu-id="18047-243">It can take several minutes for all the applications to run.</span></span> <span data-ttu-id="18047-244">运行所有应用程序后，关闭每个应用程序。</span><span class="sxs-lookup"><span data-stu-id="18047-244">After all applications have run, close each of the applications.</span></span> <span data-ttu-id="18047-245">您还可以通过选中 "**强制下载应用程序**" 复选框，将程序包配置为在打开前需要完全下载。</span><span class="sxs-lookup"><span data-stu-id="18047-245">You can also configure the package to be required to be fully downloaded before opening by selecting the **Force applications to be downloaded** check-box.</span></span> <span data-ttu-id="18047-246">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="18047-246">Click **Next**.</span></span>

   **<span data-ttu-id="18047-247">注意</span><span class="sxs-lookup"><span data-stu-id="18047-247">Note</span></span>**  
   <span data-ttu-id="18047-248">如有必要，您可以在执行此步骤期间停止应用程序的加载。</span><span class="sxs-lookup"><span data-stu-id="18047-248">If necessary, you can stop an application from loading during this step.</span></span> <span data-ttu-id="18047-249">在 "**应用程序启动**" 对话框中，单击 "**停止**"，然后选择其中一个复选框： "**停止所有应用程序**" 或 "**仅停止此应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="18047-249">In the **Application Launch** dialog box, click **Stop** and select one of the check boxes: **Stop all applications** or **Stop this application only**.</span></span>



12. <span data-ttu-id="18047-250">在 "**目标操作系统**" 页面上，指定可运行此程序包的操作系统。</span><span class="sxs-lookup"><span data-stu-id="18047-250">On the **Target OS** page, specify the operating systems that can run this package.</span></span> <span data-ttu-id="18047-251">若要允许环境中的所有受支持的操作系统运行此程序包，请选中 "**允许此程序包在任何操作系统上运行**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="18047-251">To allow all supported operating systems in your environment to run this package, select the **Allow this package to run on any operating system** check box.</span></span> <span data-ttu-id="18047-252">若要将此程序包配置为仅在特定操作系统上运行，请选中 "**仅允许此程序包在下列操作系统上运行**" 复选框，然后选择可以运行此程序包的操作系统。</span><span class="sxs-lookup"><span data-stu-id="18047-252">To configure this package to run only on specific operating systems, select the **Allow this package to run only on the following operating systems** check box, and then select the operating systems that can run this package.</span></span> <span data-ttu-id="18047-253">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="18047-253">Click **Next**.</span></span>

13. <span data-ttu-id="18047-254">将显示 "**创建程序包**" 页面。</span><span class="sxs-lookup"><span data-stu-id="18047-254">The **Create Package** page is displayed.</span></span> <span data-ttu-id="18047-255">若要在不保存的情况下修改程序包，请选择 **"继续使用程序包编辑器修改程序包而不保存**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="18047-255">To modify the package without saving it, select **Continue to modify package without saving using the package editor** check box.</span></span> <span data-ttu-id="18047-256">此选项将在 sequencer 控制台中打开程序包，以便你可以在保存包之前对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="18047-256">This option opens the package in the sequencer console so that you can modify the package before it is saved.</span></span> <span data-ttu-id="18047-257">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="18047-257">Click **Next**.</span></span>

   <span data-ttu-id="18047-258">若要立即保存程序包，请选择 **"立即保存程序包"**。</span><span class="sxs-lookup"><span data-stu-id="18047-258">To save the package immediately, select **Save the package now**.</span></span> <span data-ttu-id="18047-259">（可选）添加将与程序包关联的**说明**。</span><span class="sxs-lookup"><span data-stu-id="18047-259">Optionally, add a **Description** that will be associated with the package.</span></span> <span data-ttu-id="18047-260">说明适用于标识有关程序包的版本和其他信息。</span><span class="sxs-lookup"><span data-stu-id="18047-260">Descriptions are useful for identifying the version and other information about the package.</span></span>

   **<span data-ttu-id="18047-261">重要提示</span><span class="sxs-lookup"><span data-stu-id="18047-261">Important</span></span>**  
   <span data-ttu-id="18047-262">系统不支持批注和说明中的不可打印字符。</span><span class="sxs-lookup"><span data-stu-id="18047-262">The system does not support non-printable characters in Comments and Descriptions.</span></span>



~~~
The default **Save Location** is also displayed on this page. To change the default location, click **Browse** and specify the new location. Click **Create**.
~~~

**<span data-ttu-id="18047-263">对中间件应用程序进行排序</span><span class="sxs-lookup"><span data-stu-id="18047-263">To sequence a middleware application</span></span>**

1. <span data-ttu-id="18047-264">在运行 sequencer 的计算机上，单击 "**所有程序**"，然后单击 " **Microsoft**application virtualization sequencer"，然后单击 " **microsoft application virtualization sequencer**"。</span><span class="sxs-lookup"><span data-stu-id="18047-264">On the computer that runs the sequencer, click **All Programs**, and then Click **Microsoft Application Virtualization**, and then click **Microsoft Application Virtualization Sequencer**.</span></span>

2. <span data-ttu-id="18047-265">*<strong><em>在排序器中，单击 "* </em> 创建新的虚拟应用程序包" </strong> 。</span><span class="sxs-lookup"><span data-stu-id="18047-265">\*<strong><em>In the sequencer, click \*</em>Create a New Virtual Application Package</strong>.</span></span> <span data-ttu-id="18047-266">选择 "**创建程序包（默认）**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="18047-266">Select **Create Package (default)**, and then click **Next**.</span></span>

3. <span data-ttu-id="18047-267">在 "**准备计算机**" 页面上，查看可能导致程序包创建失败或可能导致程序包包含不必要的数据的问题。</span><span class="sxs-lookup"><span data-stu-id="18047-267">On the **Prepare Computer** page, review the issues that could cause the package creation to fail or could cause the package to contain unnecessary data.</span></span> <span data-ttu-id="18047-268">您应该先解决所有潜在问题，然后再继续。</span><span class="sxs-lookup"><span data-stu-id="18047-268">You should resolve all potential issues before you continue.</span></span> <span data-ttu-id="18047-269">进行更正后，单击 "**刷新**" 以显示更新的信息。</span><span class="sxs-lookup"><span data-stu-id="18047-269">After making any corrections, click **Refresh** to display the updated information.</span></span> <span data-ttu-id="18047-270">解决所有潜在问题后，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="18047-270">After you have resolved all potential issues, click **Next**.</span></span>

   **<span data-ttu-id="18047-271">重要提示</span><span class="sxs-lookup"><span data-stu-id="18047-271">Important</span></span>**  
   <span data-ttu-id="18047-272">如果需要禁用病毒扫描软件，应首先扫描运行 app-v 5.0 Sequencer 的计算机，以确保不会向程序包添加不需要的文件或恶意文件。</span><span class="sxs-lookup"><span data-stu-id="18047-272">If you are required to disable virus scanning software, you should first scan the computer that runs the App-V 5.0 Sequencer in order to ensure that no unwanted or malicious files can be added to the package.</span></span>



4. <span data-ttu-id="18047-273">在 "**应用程序类型**" 页面上，选择 "**中间件**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="18047-273">On the **Type of Application** page, select **Middleware**, and then click **Next**.</span></span>

5. <span data-ttu-id="18047-274">在 "**选择安装程序**" 页面上，单击 "**浏览**" 并指定应用程序的安装文件。</span><span class="sxs-lookup"><span data-stu-id="18047-274">On the **Select Installer** page, click **Browse** and specify the installation file for the application.</span></span> <span data-ttu-id="18047-275">如果应用程序没有关联的安装程序文件，并且你计划手动运行所有安装步骤，请选中 "**选择此选项以执行自定义安装**" 复选框，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="18047-275">If the application does not have an associated installer file and you plan to run all installation steps manually, select the **Select this option to perform a custom installation** check box, and then click **Next**.</span></span>

6. <span data-ttu-id="18047-276">在 "**程序包名称**" 页面上，键入将与该程序包关联的名称。</span><span class="sxs-lookup"><span data-stu-id="18047-276">On the **Package Name** page, type a name that will be associated with the package.</span></span> <span data-ttu-id="18047-277">使用有助于标识将添加到程序包的应用程序用途和版本的名称。</span><span class="sxs-lookup"><span data-stu-id="18047-277">Use a name that helps identify the purpose and version of the application that will be added to the package.</span></span> <span data-ttu-id="18047-278">程序包名称将显示在 app-v 5.0 管理控制台中。</span><span class="sxs-lookup"><span data-stu-id="18047-278">The package name is displayed in the App-V 5.0 Management Console.</span></span> <span data-ttu-id="18047-279">**主虚拟应用程序目录**显示将安装应用程序的路径。</span><span class="sxs-lookup"><span data-stu-id="18047-279">The **Primary Virtual Application Directory** displays the path where the application will be installed.</span></span> <span data-ttu-id="18047-280">若要指定此位置，请键入路径或单击 "**浏览**"。</span><span class="sxs-lookup"><span data-stu-id="18047-280">To specify this location, type the path or click **Browse**.</span></span>

   <span data-ttu-id="18047-281">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="18047-281">Click **Next**.</span></span>

7. <span data-ttu-id="18047-282">在 "**安装**" 页面上，当 sequencer 和中间件应用程序安装程序准备就绪时，可以继续安装应用程序，以便排序器可以监视安装过程。</span><span class="sxs-lookup"><span data-stu-id="18047-282">On the **Installation** page, when the sequencer and middleware application installer are ready you can proceed to install the application so that the sequencer can monitor the installation process.</span></span> <span data-ttu-id="18047-283">使用应用程序的安装过程执行安装。</span><span class="sxs-lookup"><span data-stu-id="18047-283">Use the application's installation process to perform the installation.</span></span> <span data-ttu-id="18047-284">如果必须在安装过程中运行其他安装文件，请单击 "**运行**" 以查找并运行其他安装文件。</span><span class="sxs-lookup"><span data-stu-id="18047-284">If additional installation files must be run as part of the installation, click **Run**, to locate and run the additional installation files.</span></span> <span data-ttu-id="18047-285">完成安装后，选中 "**已完成安装**" 复选框，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="18047-285">When you are finished with the installation, select the **I am finished installing** check box, and then click **Next**.</span></span>

8. <span data-ttu-id="18047-286">在 "**安装**" 页面上，在 sequencer 配置虚拟应用程序包时等待。</span><span class="sxs-lookup"><span data-stu-id="18047-286">On the **Installation** page, wait while the sequencer configures the virtual application package.</span></span>

9. <span data-ttu-id="18047-287">在 "**安装报告**" 页面上，你可以查看你刚刚排序过的虚拟应用程序包的相关信息。</span><span class="sxs-lookup"><span data-stu-id="18047-287">On the **Installation Report** page, you can review information about the virtual application package that you have just sequenced.</span></span> <span data-ttu-id="18047-288">在**其他信息**中，双击事件以获取更详细的信息。</span><span class="sxs-lookup"><span data-stu-id="18047-288">In **Additional Information**, double-click an event to obtain more detailed information.</span></span> <span data-ttu-id="18047-289">若要继续，请单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="18047-289">To proceed, click **Next**.</span></span>

10. <span data-ttu-id="18047-290">在 "**目标操作系统**" 页面上，指定可运行此程序包的操作系统。</span><span class="sxs-lookup"><span data-stu-id="18047-290">On the **Target OS** page, specify the operating systems that can run this package.</span></span> <span data-ttu-id="18047-291">若要在你的环境中启用所有支持的操作系统以运行此程序包，请选中 "**允许此程序包在任何操作系统上运行**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="18047-291">To enable all supported operating systems in your environment to run this package, select the **Allow this package to run on any operating system** check box.</span></span> <span data-ttu-id="18047-292">若要将此程序包配置为仅在特定操作系统上运行，请选中 "**仅允许此程序包在下列操作系统上运行**" 复选框，然后选择可以运行此程序包的操作系统。</span><span class="sxs-lookup"><span data-stu-id="18047-292">To configure this package to run only on specific operating systems, select the **Allow this package to run only on the following operating systems** check box and select the operating systems that can run this package.</span></span> <span data-ttu-id="18047-293">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="18047-293">Click **Next**.</span></span>

11. <span data-ttu-id="18047-294">在 "**创建程序包**" 页面上显示。</span><span class="sxs-lookup"><span data-stu-id="18047-294">On the **Create Package** page is displayed.</span></span> <span data-ttu-id="18047-295">若要在不保存的情况下修改程序包，请选择 **"继续" 以在不保存的情况下使用程序包编辑器修改程序包**。</span><span class="sxs-lookup"><span data-stu-id="18047-295">To modify the package without saving it, select **Continue to modify package without saving using the package editor**.</span></span> <span data-ttu-id="18047-296">此选项将在 sequencer 控制台中打开程序包，以便你可以在保存包之前对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="18047-296">This option opens the package in the sequencer console so that you can modify the package before it is saved.</span></span> <span data-ttu-id="18047-297">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="18047-297">Click **Next**.</span></span>

    <span data-ttu-id="18047-298">若要立即保存程序包，请选择 **"立即保存程序包"**。</span><span class="sxs-lookup"><span data-stu-id="18047-298">To save the package immediately, select **Save the package now**.</span></span> <span data-ttu-id="18047-299">（可选）添加与程序包关联的**说明**。</span><span class="sxs-lookup"><span data-stu-id="18047-299">Optionally, add a **Description** to be associated with the package.</span></span> <span data-ttu-id="18047-300">说明适用于标识程序版本和有关程序包的其他信息。</span><span class="sxs-lookup"><span data-stu-id="18047-300">Descriptions are useful for identifying the program version and other information about the package.</span></span>

    **<span data-ttu-id="18047-301">重要提示</span><span class="sxs-lookup"><span data-stu-id="18047-301">Important</span></span>**  
    <span data-ttu-id="18047-302">系统不支持批注和说明中的不可打印字符。</span><span class="sxs-lookup"><span data-stu-id="18047-302">The system does not support non-printable characters in Comments and Descriptions.</span></span>



~~~
The default **Save Location** is also displayed on this page. To change the default location, click **Browse** and specify the new location. Click **Create**.
~~~

12. <span data-ttu-id="18047-303">将显示**完成**页。</span><span class="sxs-lookup"><span data-stu-id="18047-303">The **Completion** page is displayed.</span></span> <span data-ttu-id="18047-304">根据需要查看 "**虚拟应用程序包" 报表**窗格中的信息，然后单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="18047-304">Review the information in the **Virtual Application Package Report** pane as needed, then click **Close**.</span></span> <span data-ttu-id="18047-305">此信息也可在此过程的步骤11中指定的目录中的**Report.xml**文件中使用。</span><span class="sxs-lookup"><span data-stu-id="18047-305">This information is also available in the **Report.xml** file that is located in the directory specified in step 11 of this procedure.</span></span>

   <span data-ttu-id="18047-306">程序包现在在 sequencer 中可用。</span><span class="sxs-lookup"><span data-stu-id="18047-306">The package is now available in the sequencer.</span></span> <span data-ttu-id="18047-307">若要编辑程序包属性，请单击 "**编辑 \ [包名称 \]**"。</span><span class="sxs-lookup"><span data-stu-id="18047-307">To edit the package properties, click **Edit \[Package Name\]**.</span></span>

   **<span data-ttu-id="18047-308">重要提示</span><span class="sxs-lookup"><span data-stu-id="18047-308">Important</span></span>**  
   <span data-ttu-id="18047-309">成功创建虚拟应用程序包后，不能在运行 sequencer 的计算机上运行虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="18047-309">After you have successfully created a virtual application package, you cannot run the virtual application package on the computer that is running the sequencer.</span></span>



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## <span data-ttu-id="18047-310">相关主题</span><span class="sxs-lookup"><span data-stu-id="18047-310">Related topics</span></span>


[<span data-ttu-id="18047-311">App-V 5.0 的操作</span><span class="sxs-lookup"><span data-stu-id="18047-311">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)









