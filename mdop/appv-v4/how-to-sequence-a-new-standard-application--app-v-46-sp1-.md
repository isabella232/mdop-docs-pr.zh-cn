---
title: 如何对新的标准应用程序进行排序 (App-V 4.6 SP1)
description: 如何对新的标准应用程序进行排序 (App-V 4.6 SP1)
author: dansimp
ms.assetid: c4a2eb33-def8-4535-b93a-3d2de21ce29f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 47c93b4880d0095c87a98292fda743acc1659e81
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801107"
---
# <span data-ttu-id="2a626-103">如何对新的标准应用程序进行排序 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="2a626-103">How to Sequence a New Standard Application (App-V 4.6 SP1)</span></span>


<span data-ttu-id="2a626-104">通过使用应用程序虚拟化（app-v） Sequencer，使用以下过程创建新的标准虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="2a626-104">Use the following procedure to create a new standard virtual application package by using the Application Virtualization (App-V) Sequencer.</span></span> <span data-ttu-id="2a626-105">此过程适用于你对其进行排序的大多数应用程序。</span><span class="sxs-lookup"><span data-stu-id="2a626-105">This procedure applies to most applications that you sequence.</span></span> <span data-ttu-id="2a626-106">有关可进行序列化的应用程序类型的详细信息，请参阅[如何确定要序列的应用程序类型（app-v 4.6 SP1）](how-to-determine-which-type-of-application-to-sequence---app-v-46-sp1-.md)。</span><span class="sxs-lookup"><span data-stu-id="2a626-106">For more information about the types of applications you can sequence, see [How to Determine Which Type of Application to Sequence (App-V 4.6 SP1)](how-to-determine-which-type-of-application-to-sequence---app-v-46-sp1-.md).</span></span> <span data-ttu-id="2a626-107">必须使用具有管理员权限的帐户运行 sequencer （**SFTSequencer.exe**），因为 sequencer 对本地系统所做的更改。</span><span class="sxs-lookup"><span data-stu-id="2a626-107">You must run the sequencer (**SFTSequencer.exe**) using an account that has administrator privileges because of the changes the sequencer makes to the local system.</span></span> <span data-ttu-id="2a626-108">这些更改可以包括将文件写入**C:\\program files files**目录、进行注册表更改、启动和停止服务、更新文件的安全描述符以及更改权限。</span><span class="sxs-lookup"><span data-stu-id="2a626-108">These changes can include writing files to the **C:\\Program Files** directory, making registry changes, starting and stopping services, updating security descriptors for files, and changing permissions.</span></span>

**<span data-ttu-id="2a626-109">重要提示</span><span class="sxs-lookup"><span data-stu-id="2a626-109">Important</span></span>**  
<span data-ttu-id="2a626-110">在排序期间，如果运行 Sequencer 的计算机运行的是 windows Vista 或 windows 7，并且在虚拟环境外启动了重启（例如，**启动**  /  **关闭**），则当系统提示关闭阻止 windows Vista 或 windows 关闭的程序时，必须单击 "**取消**"。</span><span class="sxs-lookup"><span data-stu-id="2a626-110">During sequencing, if the computer running the Sequencer is running Windows Vista or Windows 7 and a restart is initiated outside of the virtual environment, for example, **Start** / **Shut Down**, you must click **Cancel** when prompted to close the program that is preventing Windows Vista or Windows from shutting down.</span></span> <span data-ttu-id="2a626-111">如果单击 "**强制关闭**"，程序包创建将失败。</span><span class="sxs-lookup"><span data-stu-id="2a626-111">If you click **Force shut down**, the package creation fails.</span></span> <span data-ttu-id="2a626-112">单击 "**取消**" 时，Sequencer 会在应用程序顺序期间成功记录重启。</span><span class="sxs-lookup"><span data-stu-id="2a626-112">When you click **Cancel**, the Sequencer successfully records the restart while the application is being sequenced.</span></span>



**<span data-ttu-id="2a626-113">注意</span><span class="sxs-lookup"><span data-stu-id="2a626-113">Note</span></span>**  
<span data-ttu-id="2a626-114">在安全模式下运行 app-v sequencer 不受支持。</span><span class="sxs-lookup"><span data-stu-id="2a626-114">Running the App-V sequencer in Safe Mode is not supported.</span></span>



**<span data-ttu-id="2a626-115">对新标准应用程序进行序列化</span><span class="sxs-lookup"><span data-stu-id="2a626-115">To sequence a new standard application</span></span>**

1.  <span data-ttu-id="2a626-116">若要启动 app-v 排序器，请在运行 app-v 排序器的计算机上，单击 "**启动**  /  **所有程序**  /  **microsoft application virtualization**  /  **microsoft application virtualization Sequencer**"。</span><span class="sxs-lookup"><span data-stu-id="2a626-116">To start the App-V Sequencer, on the computer that is running the App-V Sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="2a626-117">若要启动 "**创建新程序包" 向导**，请单击 "**创建新的虚拟应用程序包**"。</span><span class="sxs-lookup"><span data-stu-id="2a626-117">To start the **Create New Package Wizard**, click **Create a New Virtual Application Package**.</span></span> <span data-ttu-id="2a626-118">若要创建程序包，请选择 "**创建程序包（默认）**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="2a626-118">To create the package, select **Create Package (default)**, and then click **Next**.</span></span>

3.  <span data-ttu-id="2a626-119">在 "**准备计算机**" 页面上，查看可能导致程序包创建失败的问题，或者查看程序包中是否包含不必要的数据。</span><span class="sxs-lookup"><span data-stu-id="2a626-119">On the **Prepare Computer** page, review the issues that could cause the package creation to fail, or for the package to contain unnecessary data.</span></span> <span data-ttu-id="2a626-120">我们强烈建议您先解决所有潜在问题，然后再继续。</span><span class="sxs-lookup"><span data-stu-id="2a626-120">We strongly recommend that you resolve all potential issues before you continue.</span></span> <span data-ttu-id="2a626-121">修复冲突后，若要更新显示的信息，请单击 "**刷新**"。</span><span class="sxs-lookup"><span data-stu-id="2a626-121">After you have fixed the conflicts, to update the information that is displayed, click **Refresh**.</span></span> <span data-ttu-id="2a626-122">解决所有潜在问题后，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="2a626-122">After you have resolved all potential issues, click **Next**.</span></span>

    **<span data-ttu-id="2a626-123">重要提示</span><span class="sxs-lookup"><span data-stu-id="2a626-123">Important</span></span>**  
    <span data-ttu-id="2a626-124">如果需要禁用病毒扫描软件，请扫描运行 Sequencer 的计算机，以确保不会向程序包添加不需要的或恶意的文件。</span><span class="sxs-lookup"><span data-stu-id="2a626-124">If you are required to disable virus scanning software, scan the computer running the Sequencer to ensure that no unwanted or malicious files could be added to the package.</span></span>



4.  <span data-ttu-id="2a626-125">在 "**应用程序类型**" 页面上，单击 "**标准应用程序（默认）** " 复选框，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="2a626-125">On the **Type of Application** page, click **Standard Application (default)** check box, and then click **Next**.</span></span>

    <span data-ttu-id="2a626-126">有关可进行序列化的应用程序类型的详细信息，请参阅[如何确定要序列化的应用程序类型（app-v 4.6 SP1）](how-to-determine-which-type-of-application-to-sequence---app-v-46-sp1-.md)。</span><span class="sxs-lookup"><span data-stu-id="2a626-126">For more information about the types of applications that you can sequence, see [How to Determine Which Type of Application to Sequence (App-V 4.6 SP1)](how-to-determine-which-type-of-application-to-sequence---app-v-46-sp1-.md).</span></span>

5.  <span data-ttu-id="2a626-127">在 "**选择安装程序**" 页面上，单击 "**浏览**" 并指定应用程序的安装文件。</span><span class="sxs-lookup"><span data-stu-id="2a626-127">On the **Select Installer** page, click **Browse** and specify the installation file for the application.</span></span> <span data-ttu-id="2a626-128">如果应用程序没有关联的安装程序文件，并且你计划手动运行所有安装步骤，请选中 "**执行自定义安装**" 复选框，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="2a626-128">If the application does not have an associated installer file and you plan to run all installation steps manually, select the **Perform a Custom Installation** check box, and then Click **Next**.</span></span>

6.  <span data-ttu-id="2a626-129">在 "**程序包名称**" 页面上，指定将与程序包关联的名称。</span><span class="sxs-lookup"><span data-stu-id="2a626-129">On the **Package Name** page, specify a name that will be associated with the package.</span></span> <span data-ttu-id="2a626-130">该名称有助于标识添加到程序包的应用程序的用途和版本。</span><span class="sxs-lookup"><span data-stu-id="2a626-130">The name helps identify the purpose and version of the application that are added to the package.</span></span> <span data-ttu-id="2a626-131">程序包名称还会显示在 App-v 管理控制台中。</span><span class="sxs-lookup"><span data-stu-id="2a626-131">The package name is also displayed in the App-V management console.</span></span> <span data-ttu-id="2a626-132">**主虚拟应用程序目录**显示应用程序虚拟化路径，应用程序虚拟化路径将在目标计算机上安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="2a626-132">The **Primary Virtual Application Directory** displays the Application Virtualization path where the application will be installed on target computers.</span></span> <span data-ttu-id="2a626-133">若要编辑此位置，请选择 "**编辑（高级）**"。</span><span class="sxs-lookup"><span data-stu-id="2a626-133">To edit this location, select **Edit (Advanced)**.</span></span>

    **<span data-ttu-id="2a626-134">重要提示</span><span class="sxs-lookup"><span data-stu-id="2a626-134">Important</span></span>**  
    <span data-ttu-id="2a626-135">编辑应用程序虚拟化路径是一种高级配置任务。</span><span class="sxs-lookup"><span data-stu-id="2a626-135">Editing the Application Virtualization path is an advanced configuration task.</span></span> <span data-ttu-id="2a626-136">你应该完全理解更改路径的含义。</span><span class="sxs-lookup"><span data-stu-id="2a626-136">You should fully understand the implications of changing the path.</span></span> <span data-ttu-id="2a626-137">对于大多数应用程序，建议使用默认路径。</span><span class="sxs-lookup"><span data-stu-id="2a626-137">For most applications, the default path is recommended.</span></span>



~~~
Click **Next**.
~~~

7. <span data-ttu-id="2a626-138">在 "**安装**" 页面上，当 sequencer 和应用程序安装准备就绪时，请安装该应用程序，以便排序器可以监视安装过程。</span><span class="sxs-lookup"><span data-stu-id="2a626-138">On the **Installation** page, when the Sequencer and application installer are ready, install the application so that the Sequencer can monitor the installation process.</span></span> <span data-ttu-id="2a626-139">使用应用程序的安装过程执行安装。</span><span class="sxs-lookup"><span data-stu-id="2a626-139">Perform the installation by using the application’s installation process.</span></span> <span data-ttu-id="2a626-140">如果必须在安装过程中运行其他安装文件，请单击 "**运行**" 以查找并运行其他安装文件。</span><span class="sxs-lookup"><span data-stu-id="2a626-140">If additional installation files must be run as part of the installation, click **Run** to locate and run the additional installation files.</span></span> <span data-ttu-id="2a626-141">完成安装后，请选择 "**我已完成安装**"。</span><span class="sxs-lookup"><span data-stu-id="2a626-141">When you are finished with the installation, select **I am finished installing**.</span></span> <span data-ttu-id="2a626-142">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2a626-142">Click **Next**.</span></span>

8. <span data-ttu-id="2a626-143">在 "**安装**" 页面上，在 Sequencer 配置虚拟应用程序包时等待。</span><span class="sxs-lookup"><span data-stu-id="2a626-143">On the **Installation** page, wait while the Sequencer configures the virtual application package.</span></span>

9. <span data-ttu-id="2a626-144">在 "**配置软件**" 页面上，选择运行程序包中包含的程序。</span><span class="sxs-lookup"><span data-stu-id="2a626-144">On the **Configure Software** page, optionally run the programs contained in the package.</span></span> <span data-ttu-id="2a626-145">此步骤有助于完成在目标计算机上部署和运行程序包之前运行该应用程序所需的任何相关许可证或配置任务。</span><span class="sxs-lookup"><span data-stu-id="2a626-145">This step helps complete any associated license or configuration tasks that are required to run the application before you deploy and run the package on target computers.</span></span> <span data-ttu-id="2a626-146">若要一次运行所有程序，请至少选择一个程序，然后单击 "**全部运行**"。</span><span class="sxs-lookup"><span data-stu-id="2a626-146">To run all the programs at one time, select at least one program, and then click **Run All**.</span></span> <span data-ttu-id="2a626-147">若要运行特定程序，请选择要运行的一个或一些程序，然后单击 "**运行所选**"。</span><span class="sxs-lookup"><span data-stu-id="2a626-147">To run specific programs, select the program or programs you want to run, and then click **Run Selected**.</span></span> <span data-ttu-id="2a626-148">完成所需的配置任务，然后关闭应用程序。</span><span class="sxs-lookup"><span data-stu-id="2a626-148">Complete the required configuration tasks and then close the applications.</span></span> <span data-ttu-id="2a626-149">运行所有程序可能需要几分钟的时间。</span><span class="sxs-lookup"><span data-stu-id="2a626-149">It can take several minutes for all programs to run.</span></span> <span data-ttu-id="2a626-150">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2a626-150">Click **Next**.</span></span>

10. <span data-ttu-id="2a626-151">在 "**安装报告**" 页面上，您可以查看刚刚排序的虚拟应用程序包的相关信息。</span><span class="sxs-lookup"><span data-stu-id="2a626-151">On the **Installation Report** page, you can review information about the virtual application package you just sequenced.</span></span> <span data-ttu-id="2a626-152">有关**其他信息**中显示的信息的更多详细说明，请双击该事件。</span><span class="sxs-lookup"><span data-stu-id="2a626-152">For a more detailed explanation about the information displayed in **Additional Information**, double-click the event.</span></span> <span data-ttu-id="2a626-153">查看信息后，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="2a626-153">After you have reviewed the information, click **Next**.</span></span>

11. <span data-ttu-id="2a626-154">在 "**自定义**" 页面上，如果已完成安装和配置虚拟应用程序，请选择 "**立即停止**"，然后跳到此过程的步骤15。</span><span class="sxs-lookup"><span data-stu-id="2a626-154">On the **Customize** page, if you are finished installing and configuring the virtual application, select **Stop now** and skip to step 15 of this procedure.</span></span> <span data-ttu-id="2a626-155">如果要自定义下表中的任何项目，请选择 "**自定义**"。</span><span class="sxs-lookup"><span data-stu-id="2a626-155">If you want to customize any of the items in the following list, select **Customize**.</span></span>

    -   <span data-ttu-id="2a626-156">编辑文件类型关联和与应用程序关联的图标。</span><span class="sxs-lookup"><span data-stu-id="2a626-156">Edit the file type associations and the icons associated with an application.</span></span>

    -   <span data-ttu-id="2a626-157">准备用于流式处理的虚拟包。</span><span class="sxs-lookup"><span data-stu-id="2a626-157">Prepare the virtual package for streaming.</span></span> <span data-ttu-id="2a626-158">流改进了在目标计算机上运行虚拟应用程序包时的体验。</span><span class="sxs-lookup"><span data-stu-id="2a626-158">Streaming improves the experience when the virtual application package is run on target computers.</span></span>

    -   <span data-ttu-id="2a626-159">指定可以运行此程序包的操作系统。</span><span class="sxs-lookup"><span data-stu-id="2a626-159">Specify the operating systems that can run this package.</span></span>

    <span data-ttu-id="2a626-160">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2a626-160">Click **Next**.</span></span>

12. <span data-ttu-id="2a626-161">在 "**编辑快捷方式**" 页面上，你可以选择配置文件类型关联（FTA）和将与程序包中的各种应用程序关联的快捷方式位置。</span><span class="sxs-lookup"><span data-stu-id="2a626-161">On the **Edit Shortcuts** page, you can optionally configure the file type associations (FTA) and shortcut locations that will be associated with the various applications in the package.</span></span> <span data-ttu-id="2a626-162">若要创建新的 FTA，请在左窗格中，选择并展开要自定义的应用程序，然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="2a626-162">To create a new FTA, in the left pane, select and expand the application you want to customize, and then click **Add**.</span></span> <span data-ttu-id="2a626-163">在 "**添加文件类型关联**" 对话框中，为新的 FTA 提供必要的信息。</span><span class="sxs-lookup"><span data-stu-id="2a626-163">In the **Add File Type Association** dialog box, provide the necessary information for the new FTA.</span></span> <span data-ttu-id="2a626-164">若要查看与应用程序相关联的快捷方式信息，请在 "应用程序" 下选择 "**快捷方式**"，然后在 "**位置**" 窗格中编辑图标文件信息。</span><span class="sxs-lookup"><span data-stu-id="2a626-164">To review the shortcut information associated with an application, under the application, select **Shortcuts**, and in the **Location** pane, you can edit the icon file information.</span></span> <span data-ttu-id="2a626-165">若要编辑现有 FTA，请单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="2a626-165">To edit an existing FTA, click **Edit**.</span></span> <span data-ttu-id="2a626-166">若要删除 FTA，请选择 "FTA"，然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="2a626-166">To remove an FTA, select the FTA, and then click **Remove**.</span></span> <span data-ttu-id="2a626-167">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2a626-167">Click **Next**.</span></span>

13. <span data-ttu-id="2a626-168">在 "**流**" 页面上，运行每个程序，以便可以在目标计算机上对其进行优化和更高效地运行。</span><span class="sxs-lookup"><span data-stu-id="2a626-168">On the **Streaming** page, run each program so that it can be optimized and run more efficiently on target computers.</span></span> <span data-ttu-id="2a626-169">运行所有应用程序可能需要几分钟的时间。</span><span class="sxs-lookup"><span data-stu-id="2a626-169">It can take several minutes for all the applications to run.</span></span> <span data-ttu-id="2a626-170">在所有应用程序运行后，关闭每个应用程序，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="2a626-170">After all applications have run, close each of the applications, and then click **Next**.</span></span>

   **<span data-ttu-id="2a626-171">注意</span><span class="sxs-lookup"><span data-stu-id="2a626-171">Note</span></span>**  
   <span data-ttu-id="2a626-172">如果要在此步骤中停止应用程序的加载，请在 "**应用程序启动**" 对话框中，单击 "**停止**"，然后选择其中一个复选框、"**停止所有应用程序**" 或 "**停止此应用程序**"，具体取决于所需内容。</span><span class="sxs-lookup"><span data-stu-id="2a626-172">If you want to stop an application from loading during this step, in the **Application Launch** dialog box, click **Stop**, and select one of the check boxes, **Stop all applications** or **Stop this application only**, depending on what you want.</span></span>



14. <span data-ttu-id="2a626-173">在 "**目标操作系统**" 页面上，指定可运行此程序包的操作系统。</span><span class="sxs-lookup"><span data-stu-id="2a626-173">On the **Target OS** page, specify the operating systems that can run this package.</span></span> <span data-ttu-id="2a626-174">若要在你的环境中启用所有支持的操作系统以运行此程序包，请选择 "**允许此程序包在任何操作系统上运行**"。</span><span class="sxs-lookup"><span data-stu-id="2a626-174">To enable all supported operating systems in your environment to run this package, select **Allow this package to run on any operating system**.</span></span> <span data-ttu-id="2a626-175">若要将此程序包配置为仅在特定操作系统上运行，请选择 "**仅允许此程序包在以下操作系统上运行**"，然后指定可以运行此程序包的操作系统。</span><span class="sxs-lookup"><span data-stu-id="2a626-175">To configure this package to run only on specific operating systems, select **Allow this package to run only on the following operating systems** and specify the operating systems that can run this package.</span></span> <span data-ttu-id="2a626-176">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2a626-176">Click **Next**.</span></span>

   **<span data-ttu-id="2a626-177">重要提示</span><span class="sxs-lookup"><span data-stu-id="2a626-177">Important</span></span>**  
   <span data-ttu-id="2a626-178">在此步骤中指定的操作系统将反映已启用运行程序包的目标计算机上的操作系统。</span><span class="sxs-lookup"><span data-stu-id="2a626-178">The operating systems specified during this step reflect the operating systems on target computers that are enabled to run the package.</span></span> <span data-ttu-id="2a626-179">你必须确保你要序列化的应用程序支持所指定的操作系统。</span><span class="sxs-lookup"><span data-stu-id="2a626-179">You must ensure that the operating systems specified are supported by the application you are sequencing.</span></span>



15. <span data-ttu-id="2a626-180">在 "**创建程序包**" 页面上，若要在不保存的情况下修改程序包，请选择 **"继续" 以在不保存的情况下使用程序包编辑器修改程序包**。</span><span class="sxs-lookup"><span data-stu-id="2a626-180">On the **Create Package** page, to modify the package without saving it, select **Continue to modify package without saving using the package editor**.</span></span> <span data-ttu-id="2a626-181">选择此选项将在 Sequencer 控制台中打开程序包，以便你可以在保存包之前对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="2a626-181">Selecting this option opens the package in the Sequencer console so that you can modify the package before it is saved.</span></span> <span data-ttu-id="2a626-182">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2a626-182">Click **Next**.</span></span>

   <span data-ttu-id="2a626-183">若要立即保存程序包，请选中 "**立即保存程序包**" 默认值。</span><span class="sxs-lookup"><span data-stu-id="2a626-183">To save the package immediately, select the default **Save the package now**.</span></span> <span data-ttu-id="2a626-184">添加将与程序包关联的可选**注释**。</span><span class="sxs-lookup"><span data-stu-id="2a626-184">Add optional **Comments** that will be associated with the package.</span></span> <span data-ttu-id="2a626-185">对于标识版本以及有关程序包的其他信息，评论非常有用。</span><span class="sxs-lookup"><span data-stu-id="2a626-185">Comments are useful for identifying version and other information about the package.</span></span> <span data-ttu-id="2a626-186">还会显示默认**保存位置**。</span><span class="sxs-lookup"><span data-stu-id="2a626-186">The default **Save Location** is also displayed.</span></span> <span data-ttu-id="2a626-187">若要更改默认位置，请单击 "**浏览**" 并指定新位置。</span><span class="sxs-lookup"><span data-stu-id="2a626-187">To change the default location, click **Browse** and specify the new location.</span></span> <span data-ttu-id="2a626-188">将显示未压缩的程序包大小。</span><span class="sxs-lookup"><span data-stu-id="2a626-188">The uncompressed package size is displayed.</span></span> <span data-ttu-id="2a626-189">如果程序包大小超过 4 GB （未压缩），并且你打算将程序包流式传输到目标计算机，则必须选择 "**压缩程序包**"。</span><span class="sxs-lookup"><span data-stu-id="2a626-189">If the package size exceeds 4 GB (uncompressed) and you plan to stream the package to target computers, you must select **Compress Package**.</span></span> <span data-ttu-id="2a626-190">单击“创建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2a626-190">Click **Create**.</span></span>

16. <span data-ttu-id="2a626-191">在 "**完成**" 页面上，查看 "**虚拟应用程序包报告**" 窗格中显示的信息后，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="2a626-191">On the **Completion** page, after you have reviewed the information displayed in the **Virtual Application Package Report** pane, click **Close**.</span></span> <span data-ttu-id="2a626-192">在 "**虚拟应用程序包报告**" 窗格中显示的信息也可在此过程的步骤15中指定的目录中，在名为**Report.xml**的文件中。</span><span class="sxs-lookup"><span data-stu-id="2a626-192">The information displayed in the **Virtual Application Package Report** pane is also available in the directory specified in step 15 of this procedure, in a file named **Report.xml**.</span></span>

    <span data-ttu-id="2a626-193">程序包现在在 Sequencer 中可用。</span><span class="sxs-lookup"><span data-stu-id="2a626-193">The package is now available in the Sequencer.</span></span> <span data-ttu-id="2a626-194">若要编辑程序包属性，请单击 "**编辑 \ [包名称 \]**"。</span><span class="sxs-lookup"><span data-stu-id="2a626-194">To edit the package properties, click **Edit \[Package Name\]**.</span></span> <span data-ttu-id="2a626-195">有关修改程序包的详细信息，请参阅[如何修改现有虚拟应用程序包（app-v 4.6 SP1）](how-to-modify-an-existing-virtual-application-package--app-v-46-sp1-.md)</span><span class="sxs-lookup"><span data-stu-id="2a626-195">For more information about modifying a package, see [How to Modify an Existing Virtual Application Package (App-V 4.6 SP1)](how-to-modify-an-existing-virtual-application-package--app-v-46-sp1-.md)</span></span>

    **<span data-ttu-id="2a626-196">重要提示</span><span class="sxs-lookup"><span data-stu-id="2a626-196">Important</span></span>**  
    <span data-ttu-id="2a626-197">成功创建虚拟应用程序包后，不能在运行 Sequencer 的计算机上运行虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="2a626-197">After you have successfully created a virtual application package, you cannot run the virtual application package on the computer that is running the Sequencer.</span></span>



## <span data-ttu-id="2a626-198">相关主题</span><span class="sxs-lookup"><span data-stu-id="2a626-198">Related topics</span></span>


[<span data-ttu-id="2a626-199">Application Virtualization Sequencer 的任务 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="2a626-199">Tasks for the Application Virtualization Sequencer (App-V 4.6 SP1)</span></span>](tasks-for-the-application-virtualization-sequencer--app-v-46-sp1-.md)

[<span data-ttu-id="2a626-200">如何确定要序列化的应用程序类型（App-v 4.6 SP1）</span><span class="sxs-lookup"><span data-stu-id="2a626-200">How to Determine Which Type of Application to Sequence (App-V 4.6 SP1)</span></span>](how-to-determine-which-type-of-application-to-sequence---app-v-46-sp1-.md)









