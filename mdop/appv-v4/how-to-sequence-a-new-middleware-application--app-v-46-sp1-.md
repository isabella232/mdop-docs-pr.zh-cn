---
title: 如何对新的中间件应用程序进行排序 (App-V 4.6 SP1)
description: 如何对新的中间件应用程序进行排序 (App-V 4.6 SP1)
author: dansimp
ms.assetid: 304045c2-5e5e-4c91-b59e-a91fdf2500fb
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: b26559b8f5c451d01fefe899e96a83dd388b8140
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801111"
---
# <span data-ttu-id="e49da-103">如何对新的中间件应用程序进行排序 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="e49da-103">How to Sequence a New Middleware Application (App-V 4.6 SP1)</span></span>


<span data-ttu-id="e49da-104">使用以下过程，使用应用程序虚拟化（App-v） Sequencer 创建新的中间件虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="e49da-104">Use the following procedure to create a new middleware virtual application package using the Application Virtualization (App-V) Sequencer.</span></span> <span data-ttu-id="e49da-105">中间件应用程序是连接软件模块或应用程序的软件。</span><span class="sxs-lookup"><span data-stu-id="e49da-105">A middleware application is software that connects software modules or applications.</span></span> <span data-ttu-id="e49da-106">有关可进行序列化的应用程序类型的详细信息，请参阅[如何确定要序列化的应用程序类型（app-v 4.6 SP1）](how-to-determine-which-type-of-application-to-sequence---app-v-46-sp1-.md)。</span><span class="sxs-lookup"><span data-stu-id="e49da-106">For more information about the types of applications that you can sequence, see [How to Determine Which Type of Application to Sequence (App-V 4.6 SP1)](how-to-determine-which-type-of-application-to-sequence---app-v-46-sp1-.md).</span></span>

<span data-ttu-id="e49da-107">在 App-v 中使用 "动态套件组合" 使用此类型的程序包。</span><span class="sxs-lookup"><span data-stu-id="e49da-107">Use this type of package by using Dynamic Suite Composition in App-V.</span></span> <span data-ttu-id="e49da-108">动态套件组合使你能够将虚拟应用程序包定义为依赖于另一个虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="e49da-108">Dynamic Suite Composition enables you to define a virtual application package as being dependent on another virtual application package.</span></span> <span data-ttu-id="e49da-109">依赖关系使应用程序能够与虚拟环境中的中间件或插件交互，这通常会阻止此交互。</span><span class="sxs-lookup"><span data-stu-id="e49da-109">The dependency enables the application to interact with the middleware or plug-in in the virtual environment, where typically this interaction is prevented.</span></span> <span data-ttu-id="e49da-110">这很有用，因为辅助应用程序包可以与多个其他主要应用程序一起使用，这使每个主应用程序都可以引用同一辅助程序包。</span><span class="sxs-lookup"><span data-stu-id="e49da-110">This is useful because a secondary application package can be used with several other primary applications, which enables each primary application to reference the same secondary package.</span></span> <span data-ttu-id="e49da-111">有关如何使用动态套件合成的详细信息，请参阅如何在 Microsoft 技术库（）中[使用动态套件合成](https://go.microsoft.com/fwlink/?LinkID=203804&clcid=0x409) https://go.microsoft.com/fwlink/?LinkID=203804&clcid=0x409) 。</span><span class="sxs-lookup"><span data-stu-id="e49da-111">For more information about how to use Dynamic Suite Composition, see [How To Use Dynamic Suite Composition](https://go.microsoft.com/fwlink/?LinkID=203804&clcid=0x409) in the Microsoft Technical Library (https://go.microsoft.com/fwlink/?LinkID=203804&clcid=0x409).</span></span>

**<span data-ttu-id="e49da-112">重要提示</span><span class="sxs-lookup"><span data-stu-id="e49da-112">Important</span></span>**  
<span data-ttu-id="e49da-113">在排序期间，如果运行 app-v 排序器的计算机运行的是 windows Vista 或 windows 7，并且在虚拟环境外启动了重启（例如，**启动**  /  **关闭**），则当系统提示关闭阻止 Windows 关闭的程序时，必须单击 "**取消**"。</span><span class="sxs-lookup"><span data-stu-id="e49da-113">During sequencing, if the computer running the App-V Sequencer is running Windows Vista or Windows 7 and a restart is initiated outside of the virtual environment, for example, **Start** / **Shut Down**, you must click **Cancel** when prompted to close the program that is preventing Windows from shutting down.</span></span> <span data-ttu-id="e49da-114">如果单击 "**强制关闭**"，程序包创建将失败。</span><span class="sxs-lookup"><span data-stu-id="e49da-114">If you click **Force shut down**, the package creation fails.</span></span> <span data-ttu-id="e49da-115">单击 "**取消**" 时，app-v Sequencer 会在应用程序顺序期间成功记录重启。</span><span class="sxs-lookup"><span data-stu-id="e49da-115">When you click **Cancel**, App-V Sequencer successfully records the restart while the application is being sequenced.</span></span>



**<span data-ttu-id="e49da-116">对新的中间件应用程序进行序列化</span><span class="sxs-lookup"><span data-stu-id="e49da-116">To sequence a new middleware application</span></span>**

1.  <span data-ttu-id="e49da-117">若要启动 app-v 排序器，请在运行 app-v sequencer 的计算机上，单击 "**启动**  /  **所有程序**  /  **microsoft application virtualization**  /  **microsoft application virtualization sequencer**"。</span><span class="sxs-lookup"><span data-stu-id="e49da-117">To start App-V Sequencer, on the computer that is running App-V Sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="e49da-118">若要启动 "**创建新程序包" 向导**，请单击 "**创建新的虚拟应用程序包**"。</span><span class="sxs-lookup"><span data-stu-id="e49da-118">To start the **Create New Package Wizard**, click **Create a New Virtual Application Package**.</span></span> <span data-ttu-id="e49da-119">若要创建程序包，请选择 "**创建程序包（默认）**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="e49da-119">To create the package, select **Create Package (default)**, and then click **Next**.</span></span>

3.  <span data-ttu-id="e49da-120">在 "**准备计算机**" 页面上，查看可能导致程序包创建失败的问题，或者查看程序包中是否包含不必要的数据。</span><span class="sxs-lookup"><span data-stu-id="e49da-120">On the **Prepare Computer** page, review the issues that might cause the package creation to fail, or for the package to contain unnecessary data.</span></span> <span data-ttu-id="e49da-121">我们强烈建议您先解决所有潜在问题，然后再继续。</span><span class="sxs-lookup"><span data-stu-id="e49da-121">We strongly recommend that you resolve all potential issues before you continue.</span></span> <span data-ttu-id="e49da-122">修复冲突后，若要更新显示的信息，请单击 "**刷新**"。</span><span class="sxs-lookup"><span data-stu-id="e49da-122">After you have fixed the conflicts, to update the information displayed, click **Refresh**.</span></span> <span data-ttu-id="e49da-123">解决所有潜在问题后，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="e49da-123">After you have resolved all potential issues, click **Next**.</span></span>

    **<span data-ttu-id="e49da-124">重要提示</span><span class="sxs-lookup"><span data-stu-id="e49da-124">Important</span></span>**  
    <span data-ttu-id="e49da-125">如果需要禁用病毒扫描软件，必须扫描运行应用程序 VSequencer 的计算机，以确保不会向程序包添加不需要的或恶意的文件。</span><span class="sxs-lookup"><span data-stu-id="e49da-125">If you are required to disable virus scanning software, you must scan the computer running the App-VSequencer to ensure that no unwanted or malicious files can be added to the package.</span></span>



4.  <span data-ttu-id="e49da-126">在 "**应用程序类型**" 页面上，选择 "**中间件**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="e49da-126">On the **Type of Application** page, select **Middleware**, and then click **Next**.</span></span>

    <span data-ttu-id="e49da-127">有关可进行序列化的应用程序类型的详细信息，请参阅[如何确定要序列化的应用程序类型（app-v 4.6 SP1）](how-to-determine-which-type-of-application-to-sequence---app-v-46-sp1-.md)。</span><span class="sxs-lookup"><span data-stu-id="e49da-127">For more information about the types of applications that you can sequence, see [How to Determine Which Type of Application to Sequence (App-V 4.6 SP1)](how-to-determine-which-type-of-application-to-sequence---app-v-46-sp1-.md).</span></span>

5.  <span data-ttu-id="e49da-128">在 "**选择安装程序**" 页面上，单击 "**浏览**" 并指定应用程序的安装文件。</span><span class="sxs-lookup"><span data-stu-id="e49da-128">On the **Select Installer** page, click **Browse** and specify the installation file for the application.</span></span> <span data-ttu-id="e49da-129">如果应用程序没有关联的安装程序文件，并且你计划手动运行所有安装步骤，请选中 "**选择此选项以执行自定义安装**" 复选框，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="e49da-129">If the application does not have an associated installer file and you plan to run all installation steps manually, select the **Select this option to perform a custom installation** check box, and then click **Next**.</span></span>

6.  <span data-ttu-id="e49da-130">在 "**程序包名称**" 页面上，指定将与程序包关联的名称。</span><span class="sxs-lookup"><span data-stu-id="e49da-130">On the **Package Name** page, specify a name that will be associated with the package.</span></span> <span data-ttu-id="e49da-131">该名称有助于标识将添加到程序包的应用程序的用途和版本。</span><span class="sxs-lookup"><span data-stu-id="e49da-131">The name helps identify the purpose and version of the application that will be added to the package.</span></span> <span data-ttu-id="e49da-132">程序包名称还会显示在 App-v 管理控制台中。</span><span class="sxs-lookup"><span data-stu-id="e49da-132">The package name is also displayed in the App-V Management Console.</span></span> <span data-ttu-id="e49da-133">**安装位置**显示应用程序虚拟化路径，应用程序虚拟化路径将安装在该应用程序中。</span><span class="sxs-lookup"><span data-stu-id="e49da-133">The **Installation Location** displays the application virtualization path where the application will be installed.</span></span> <span data-ttu-id="e49da-134">若要编辑此位置，请选择 "**编辑（高级）**"。</span><span class="sxs-lookup"><span data-stu-id="e49da-134">To edit this location, select **Edit (Advanced)**.</span></span>

    **<span data-ttu-id="e49da-135">重要提示</span><span class="sxs-lookup"><span data-stu-id="e49da-135">Important</span></span>**  
    <span data-ttu-id="e49da-136">编辑应用程序虚拟化路径是一种高级配置任务。</span><span class="sxs-lookup"><span data-stu-id="e49da-136">Editing the Application Virtualization path is an advanced configuration task.</span></span> <span data-ttu-id="e49da-137">你应该完全理解更改路径的含义。</span><span class="sxs-lookup"><span data-stu-id="e49da-137">You should fully understand the implications of changing the path.</span></span> <span data-ttu-id="e49da-138">对于大多数应用程序，我们建议默认路径。</span><span class="sxs-lookup"><span data-stu-id="e49da-138">For most applications, we recommend the default path.</span></span>



~~~
Click **Next**.
~~~

7. <span data-ttu-id="e49da-139">在 "**安装**" 页面上，当 sequencer 和中间件应用程序安装程序准备就绪时，请安装该应用程序，以便排序器可以监视安装过程。</span><span class="sxs-lookup"><span data-stu-id="e49da-139">On the **Installation** page, when the Sequencer and middleware application installer are ready, install the application so that the Sequencer can monitor the installation process.</span></span> <span data-ttu-id="e49da-140">使用应用程序的安装过程执行安装。</span><span class="sxs-lookup"><span data-stu-id="e49da-140">Perform the installation by using the application’s installation process.</span></span> <span data-ttu-id="e49da-141">如果必须在安装过程中运行其他安装文件，请单击 "**运行**" 以查找并运行其他安装文件。</span><span class="sxs-lookup"><span data-stu-id="e49da-141">If additional installation files must be run as part of the installation, click **Run**, to locate and run the additional installation files.</span></span> <span data-ttu-id="e49da-142">完成安装后，选中 "**已完成安装**" 复选框，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="e49da-142">When you are finished with the installation, select the **I am finished installing** check box, and then click **Next**.</span></span>

8. <span data-ttu-id="e49da-143">在 "**安装**" 页面上，在 Sequencer 配置虚拟应用程序包时等待。</span><span class="sxs-lookup"><span data-stu-id="e49da-143">On the **Installation** page, wait while the Sequencer configures the virtual application package.</span></span>

9. <span data-ttu-id="e49da-144">在 "**安装报告**" 页面上，您可以查看刚刚排序的虚拟应用程序包的相关信息。</span><span class="sxs-lookup"><span data-stu-id="e49da-144">On the **Installation Report** page, you can review information about the virtual application package that you just sequenced.</span></span> <span data-ttu-id="e49da-145">有关**其他信息**中显示的信息的更多详细说明，请双击该事件。</span><span class="sxs-lookup"><span data-stu-id="e49da-145">For a more detailed explanation about the information displayed in **Additional Information**, double-click the event.</span></span> <span data-ttu-id="e49da-146">查看信息后，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="e49da-146">After you have reviewed the information, click **Next**.</span></span>

10. <span data-ttu-id="e49da-147">在 "**目标操作系统**" 页面上，指定可运行此程序包的操作系统。</span><span class="sxs-lookup"><span data-stu-id="e49da-147">On the **Target OS** page, specify the operating systems that can run this package.</span></span> <span data-ttu-id="e49da-148">若要在你的环境中启用所有支持的操作系统以运行此程序包，请选中 "**允许此程序包在任何操作系统上运行**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="e49da-148">To enable all supported operating systems in your environment to run this package, select the **Allow this package to run on any operating system** check box.</span></span> <span data-ttu-id="e49da-149">若要将此程序包配置为仅在特定操作系统上运行，请选中 "**仅允许此程序包在下列操作系统上运行**" 复选框，然后选择可以运行此程序包的操作系统。</span><span class="sxs-lookup"><span data-stu-id="e49da-149">To configure this package to run only on specific operating systems, select the **Allow this package to run only on the following operating systems** check box and select the operating systems that can run this package.</span></span> <span data-ttu-id="e49da-150">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e49da-150">Click **Next**.</span></span>

11. <span data-ttu-id="e49da-151">在 "**创建程序包**" 页面上，若要在不保存的情况下修改程序包，请选中 "**继续使用程序包编辑器修改程序包而不保存**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="e49da-151">On the **Create Package** page, to modify the package without saving it, select the **Continue to modify package without saving using the package editor** check box.</span></span> <span data-ttu-id="e49da-152">选择此选项将在 Sequencer 控制台中打开程序包，以便你可以在保存包之前对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="e49da-152">Selecting this option opens the package in the Sequencer console so that you can modify the package before it is saved.</span></span> <span data-ttu-id="e49da-153">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e49da-153">Click **Next**.</span></span>

   <span data-ttu-id="e49da-154">若要立即保存程序包，请选中 "默认" 下的 "**立即保存程序包**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="e49da-154">To save the package immediately, select the default, the **Save the package now** check box.</span></span> <span data-ttu-id="e49da-155">在 "**批注**" 框中添加将与程序包关联的可选注释。</span><span class="sxs-lookup"><span data-stu-id="e49da-155">Add optional comments in the **Comments** box that will be associated with the package.</span></span> <span data-ttu-id="e49da-156">对于标识版本以及有关程序包的其他信息，评论非常有用。</span><span class="sxs-lookup"><span data-stu-id="e49da-156">Comments are useful for identifying version and other information about the package.</span></span> <span data-ttu-id="e49da-157">还会显示默认**保存位置**。</span><span class="sxs-lookup"><span data-stu-id="e49da-157">The default **Save Location** is also displayed.</span></span> <span data-ttu-id="e49da-158">若要更改默认位置，请单击 "**浏览**"，然后指定新位置。</span><span class="sxs-lookup"><span data-stu-id="e49da-158">To change the default location, click **Browse**, and then specify the new location.</span></span> <span data-ttu-id="e49da-159">将显示未压缩的程序包大小。</span><span class="sxs-lookup"><span data-stu-id="e49da-159">The uncompressed package size is displayed.</span></span> <span data-ttu-id="e49da-160">如果程序包大小超过 4 GB （未压缩），并且你打算将程序包流式传输到目标计算机，则必须选择 "**压缩程序包**"。</span><span class="sxs-lookup"><span data-stu-id="e49da-160">If the package size exceeds 4 GB (uncompressed) and you plan to stream the package to target computers, you must select **Compress Package**.</span></span> <span data-ttu-id="e49da-161">单击“创建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e49da-161">Click **Create**.</span></span>

12. <span data-ttu-id="e49da-162">在 "**完成**" 页面上，查看 "**虚拟应用程序包报告**" 窗格中显示的信息后，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="e49da-162">On the **Completion** page, after you have reviewed the information displayed in the **Virtual Application Package Report** pane, click **Close**.</span></span> <span data-ttu-id="e49da-163">在 "**虚拟应用程序包报告**" 窗格中显示的信息也可在此过程的步骤11（位于名为**Report.xml**的文件）中指定的目录中使用。</span><span class="sxs-lookup"><span data-stu-id="e49da-163">The information displayed in the **Virtual Application Package Report** pane is also available in the directory specified in step 11 of this procedure, in a file named **Report.xml**.</span></span>

   <span data-ttu-id="e49da-164">程序包现在在 Sequencer 中可用。</span><span class="sxs-lookup"><span data-stu-id="e49da-164">The package is now available in the Sequencer.</span></span> <span data-ttu-id="e49da-165">若要编辑程序包属性，请单击 "**编辑 \ [包名称 \]**"。</span><span class="sxs-lookup"><span data-stu-id="e49da-165">To edit the package properties, click **Edit \[Package Name\]**.</span></span> <span data-ttu-id="e49da-166">有关修改程序包的详细信息，请参阅[如何修改现有虚拟应用程序包（app-v 4.6 SP1）](how-to-modify-an-existing-virtual-application-package--app-v-46-sp1-.md)</span><span class="sxs-lookup"><span data-stu-id="e49da-166">For more information about modifying a package, see [How to Modify an Existing Virtual Application Package (App-V 4.6 SP1)](how-to-modify-an-existing-virtual-application-package--app-v-46-sp1-.md)</span></span>

   **<span data-ttu-id="e49da-167">重要提示</span><span class="sxs-lookup"><span data-stu-id="e49da-167">Important</span></span>**  
   <span data-ttu-id="e49da-168">成功创建虚拟应用程序包后，不能在运行 Sequencer 的计算机上运行虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="e49da-168">After you have successfully created a virtual application package, you cannot run the virtual application package on the computer that is running the Sequencer.</span></span>



## <span data-ttu-id="e49da-169">相关主题</span><span class="sxs-lookup"><span data-stu-id="e49da-169">Related topics</span></span>


[<span data-ttu-id="e49da-170">Application Virtualization Sequencer 的任务 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="e49da-170">Tasks for the Application Virtualization Sequencer (App-V 4.6 SP1)</span></span>](tasks-for-the-application-virtualization-sequencer--app-v-46-sp1-.md)

[<span data-ttu-id="e49da-171">如何确定要序列化的应用程序类型（App-v 4.6 SP1）</span><span class="sxs-lookup"><span data-stu-id="e49da-171">How to Determine Which Type of Application to Sequence (App-V 4.6 SP1)</span></span>](how-to-determine-which-type-of-application-to-sequence---app-v-46-sp1-.md)









