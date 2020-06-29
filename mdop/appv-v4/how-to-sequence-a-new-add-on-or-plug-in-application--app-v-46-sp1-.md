---
title: 如何对新的加载项或插件应用程序进行排序 (App-V 4.6 SP1)
description: 如何对新的加载项或插件应用程序进行排序 (App-V 4.6 SP1)
author: dansimp
ms.assetid: 2c018215-66e5-4301-8481-159891a6b35b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5c5bc1e96ead819459cda3879127ebdaf94f0ee7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801124"
---
# <span data-ttu-id="59f9b-103">如何对新的加载项或插件应用程序进行排序 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="59f9b-103">How to Sequence a New Add-on or Plug-in Application (App-V 4.6 SP1)</span></span>


<span data-ttu-id="59f9b-104">通过使用应用程序虚拟化（App-v） Sequencer，使用以下过程创建新的加载项或插件虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="59f9b-104">Use the following procedure to create a new add-on or plug-in virtual application package by using the Application Virtualization (App-V) Sequencer.</span></span> <span data-ttu-id="59f9b-105">加载项或插件应用程序是扩展应用程序功能的应用程序，例如 Microsoft Excel 的插件。</span><span class="sxs-lookup"><span data-stu-id="59f9b-105">An add-on or plug-in application is an application that extends the functionality of an application, for example, a plug-in for Microsoft Excel.</span></span> <span data-ttu-id="59f9b-106">有关可进行序列化的应用程序类型的详细信息，请参阅[如何确定要序列的应用程序类型（app-v 4.6 SP1）](how-to-determine-which-type-of-application-to-sequence---app-v-46-sp1-.md)。</span><span class="sxs-lookup"><span data-stu-id="59f9b-106">For more information about the types of applications you can sequence, see [How to Determine Which Type of Application to Sequence (App-V 4.6 SP1)](how-to-determine-which-type-of-application-to-sequence---app-v-46-sp1-.md).</span></span>

**<span data-ttu-id="59f9b-107">重要提示</span><span class="sxs-lookup"><span data-stu-id="59f9b-107">Important</span></span>**  
<span data-ttu-id="59f9b-108">在执行以下过程之前，请在运行 sequencer 的计算机上本地安装父应用程序。</span><span class="sxs-lookup"><span data-stu-id="59f9b-108">Before performing the following procedure, install the parent application locally on the computer that is running the sequencer.</span></span> <span data-ttu-id="59f9b-109">例如，如果要为 Microsoft Excel 的插件进行排序，请在运行 sequencer 的计算机上本地安装 Microsoft Excel。</span><span class="sxs-lookup"><span data-stu-id="59f9b-109">For example, if you are sequencing a plug-in for Microsoft Excel, install Microsoft Excel locally on the computer that is running the sequencer.</span></span> <span data-ttu-id="59f9b-110">还在目标计算机上安装应用程序的同一目录中安装父应用程序。</span><span class="sxs-lookup"><span data-stu-id="59f9b-110">Also install the parent application in the same directory where the application is installed on target computers.</span></span> <span data-ttu-id="59f9b-111">如果要对现有虚拟应用程序包使用插件或加载项，请在创建父虚拟应用程序包时使用的同一虚拟应用程序驱动器上安装该应用程序。</span><span class="sxs-lookup"><span data-stu-id="59f9b-111">If the plug-in or add-on is going to be used with an existing virtual application package, install the application on the same virtual application drive that was used when you created the parent virtual application package.</span></span>



<span data-ttu-id="59f9b-112">你还可以将现有虚拟应用程序包用作父应用程序。</span><span class="sxs-lookup"><span data-stu-id="59f9b-112">You can also use an existing virtual application package as the parent application.</span></span> <span data-ttu-id="59f9b-113">若要使用现有虚拟应用程序包，请在对新加载项或插件进行排序之前使用以下过程。</span><span class="sxs-lookup"><span data-stu-id="59f9b-113">To use an existing virtual application package, use the following procedure before sequencing the new add-on or plug-in.</span></span>

1.  <span data-ttu-id="59f9b-114">若要启动 app-v 排序器，请在运行 app-v 排序器的计算机上，单击 "**启动**  /  **所有程序**  /  **microsoft application virtualization**  /  **microsoft application virtualization Sequencer**"。</span><span class="sxs-lookup"><span data-stu-id="59f9b-114">To start the App-V Sequencer, on the computer that is running the App-V Sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="59f9b-115">若要将现有程序包扩展到运行 sequencer 的计算机，请单击 "**工具**" 将 "  /  **包展开到本地系统**"。</span><span class="sxs-lookup"><span data-stu-id="59f9b-115">To expand an existing package to the computer running the sequencer, click **Tools** / **Expand Package to Local System**.</span></span>

3.  <span data-ttu-id="59f9b-116">通过浏览找到并选择要展开的程序包（**sprj**文件），然后单击 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="59f9b-116">Browse to and select the package (**.sprj** file) that you want to expand, and then click **Open**.</span></span> <span data-ttu-id="59f9b-117">继续执行以下过程。</span><span class="sxs-lookup"><span data-stu-id="59f9b-117">Continue with the following procedure.</span></span>

**<span data-ttu-id="59f9b-118">对新加载项或插件应用程序进行排序</span><span class="sxs-lookup"><span data-stu-id="59f9b-118">To sequence a new add-on or plug-in application</span></span>**

1.  <span data-ttu-id="59f9b-119">若要启动 app-v 排序器，请在运行 app-v 排序器的计算机上，单击 "**启动**  /  **所有程序**  /  **microsoft application virtualization**  /  **microsoft application virtualization Sequencer**"。</span><span class="sxs-lookup"><span data-stu-id="59f9b-119">To start the App-V Sequencer, on the computer that is running the App-V Sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="59f9b-120">若要启动 "**创建新程序包" 向导**，请单击 "**创建新的虚拟应用程序包**"。</span><span class="sxs-lookup"><span data-stu-id="59f9b-120">To start the **Create New Package Wizard**, click **Create a New Virtual Application Package**.</span></span> <span data-ttu-id="59f9b-121">若要创建程序包，请选择 "**创建程序包（默认）**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="59f9b-121">To create the package, select **Create Package (default)**, and click then **Next**.</span></span>

3.  <span data-ttu-id="59f9b-122">在 "**准备计算机**" 页面上，查看可能导致程序包创建失败的问题，或者查看程序包中是否包含不必要的数据。</span><span class="sxs-lookup"><span data-stu-id="59f9b-122">On the **Prepare Computer** page, review the issues that might cause the package creation to fail, or for the package to contain unnecessary data.</span></span> <span data-ttu-id="59f9b-123">我们强烈建议您先解决所有潜在问题，然后再继续。</span><span class="sxs-lookup"><span data-stu-id="59f9b-123">We strongly recommend that you resolve all potential issues before you continue.</span></span> <span data-ttu-id="59f9b-124">修复冲突后，若要更新显示的信息，请单击 "**刷新**"。</span><span class="sxs-lookup"><span data-stu-id="59f9b-124">After you have fixed the conflicts, to update the information displayed, click **Refresh**.</span></span> <span data-ttu-id="59f9b-125">解决所有潜在问题后，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="59f9b-125">After you have resolved all potential issues, click **Next**.</span></span>

    **<span data-ttu-id="59f9b-126">重要提示</span><span class="sxs-lookup"><span data-stu-id="59f9b-126">Important</span></span>**  
    <span data-ttu-id="59f9b-127">如果需要禁用病毒扫描软件，请扫描运行 sequencer 的计算机，以确保不会向程序包添加不需要的或恶意的文件。</span><span class="sxs-lookup"><span data-stu-id="59f9b-127">If you are required to disable virus scanning software, scan the computer running the sequencer to ensure that no unwanted or malicious files could be added to the package.</span></span>



4.  <span data-ttu-id="59f9b-128">在 "**应用程序类型**" 页面上，选择 "加载项"**或 "插件**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="59f9b-128">On the **Type of Application** page, select **Add-on or Plug-in**, and then click **Next**.</span></span>

    <span data-ttu-id="59f9b-129">有关可进行序列化的应用程序类型的详细信息，请参阅[如何确定要序列化的应用程序类型（app-v 4.6 SP1）](how-to-determine-which-type-of-application-to-sequence---app-v-46-sp1-.md)。</span><span class="sxs-lookup"><span data-stu-id="59f9b-129">For more information about the types of applications that you can sequence, see [How to Determine Which Type of Application to Sequence (App-V 4.6 SP1)](how-to-determine-which-type-of-application-to-sequence---app-v-46-sp1-.md).</span></span>

5.  <span data-ttu-id="59f9b-130">在 "**选择安装程序**" 页面上，单击 "**浏览**" 并为加载项或插件指定安装文件。</span><span class="sxs-lookup"><span data-stu-id="59f9b-130">On the **Select Installer** page, click **Browse** and specify the installation file for the add-on or plug-in.</span></span> <span data-ttu-id="59f9b-131">如果应用程序没有关联的安装程序文件，并且你计划手动运行所有安装步骤，请选中 "**选择此选项以执行自定义安装**" 复选框，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="59f9b-131">If the application does not have an associated installer file and you plan to run all installation steps manually, select the **Select this option to perform a custom installation** check box, and then click **Next**.</span></span>

6.  <span data-ttu-id="59f9b-132">在 "**选择主页**" 页面上，单击 "**浏览**" 并指定父应用程序。</span><span class="sxs-lookup"><span data-stu-id="59f9b-132">On the **Select Primary** page, click **Browse** and specify the parent application.</span></span>

    **<span data-ttu-id="59f9b-133">重要提示</span><span class="sxs-lookup"><span data-stu-id="59f9b-133">Important</span></span>**  
    <span data-ttu-id="59f9b-134">如果你正在安装的加载项或插件所支持的父应用程序尚未在本地安装，请在此处停止并在运行 sequencer 的计算机上安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="59f9b-134">If the parent application that the add-on or plug-in you are installing is going to support has not been installed locally, stop here and install the application on the computer running the sequencer.</span></span> <span data-ttu-id="59f9b-135">例如， **Excel.exe**程序文件必须在本地安装 Microsoft Excel 插件。</span><span class="sxs-lookup"><span data-stu-id="59f9b-135">For example, the **Excel.exe** program file must be installed locally for a Microsoft Excel plug-in.</span></span>



~~~
Click **Next**.
~~~

7. <span data-ttu-id="59f9b-136">在 "**程序包名称**" 页面上，指定将与程序包关联的名称。</span><span class="sxs-lookup"><span data-stu-id="59f9b-136">On the **Package Name** page, specify a name that will be associated with the package.</span></span> <span data-ttu-id="59f9b-137">使用有助于标识将添加到程序包的应用程序用途和版本的名称。</span><span class="sxs-lookup"><span data-stu-id="59f9b-137">Use a name that helps identify the purpose and version of the application that will be added to the package.</span></span> <span data-ttu-id="59f9b-138">程序包名称还将显示在 App-v 管理控制台中。</span><span class="sxs-lookup"><span data-stu-id="59f9b-138">The package name will also be displayed in the App-V management console.</span></span> <span data-ttu-id="59f9b-139">**安装位置**显示应用程序虚拟化路径，应用程序虚拟化路径将安装在该应用程序中。</span><span class="sxs-lookup"><span data-stu-id="59f9b-139">The **Installation Location** displays the Application Virtualization path where the application will be installed.</span></span> <span data-ttu-id="59f9b-140">若要编辑此位置，请选择 "**编辑（高级）**"。</span><span class="sxs-lookup"><span data-stu-id="59f9b-140">To edit this location, select **Edit (Advanced)**.</span></span>

   **<span data-ttu-id="59f9b-141">重要提示</span><span class="sxs-lookup"><span data-stu-id="59f9b-141">Important</span></span>**  
   <span data-ttu-id="59f9b-142">编辑应用程序虚拟化路径是一种高级配置任务。</span><span class="sxs-lookup"><span data-stu-id="59f9b-142">Editing the Application Virtualization path is an advanced configuration task.</span></span> <span data-ttu-id="59f9b-143">你应该完全理解更改路径的含义。</span><span class="sxs-lookup"><span data-stu-id="59f9b-143">You should fully understand the implications of changing the path.</span></span> <span data-ttu-id="59f9b-144">对于大多数应用程序，我们建议默认路径。</span><span class="sxs-lookup"><span data-stu-id="59f9b-144">For most applications, we recommend the default path.</span></span>



~~~
Click **Next**.
~~~

8. <span data-ttu-id="59f9b-145">在 "**安装**" 页面上，当 sequencer 和应用程序安装准备就绪时，请安装插件或加载项应用程序，以便排序器可以监视安装过程。</span><span class="sxs-lookup"><span data-stu-id="59f9b-145">On the **Installation** page, when the sequencer and application installer are ready, install the plug-in or add-in application so the sequencer can monitor the installation process.</span></span> <span data-ttu-id="59f9b-146">使用应用程序的安装过程执行安装。</span><span class="sxs-lookup"><span data-stu-id="59f9b-146">Perform the installation by using the application’s installation process.</span></span> <span data-ttu-id="59f9b-147">如果必须在安装过程中运行其他安装文件，请单击 "**运行**"，然后找到并运行其他安装文件。</span><span class="sxs-lookup"><span data-stu-id="59f9b-147">If additional installation files must be run as part of the installation, click **Run** and locate and run the additional installation files.</span></span> <span data-ttu-id="59f9b-148">完成安装后，选择 "**我已完成安装**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="59f9b-148">When you are finished with the installation, select **I am finished installing**, and then click **Next**.</span></span>

9. <span data-ttu-id="59f9b-149">在 "**安装报告**" 页面上，您可以查看刚刚排序的虚拟应用程序包的相关信息。</span><span class="sxs-lookup"><span data-stu-id="59f9b-149">On the **Installation Report** page, you can review information about the virtual application package that you just sequenced.</span></span> <span data-ttu-id="59f9b-150">有关**其他信息**中显示的信息的更多详细说明，请双击该事件。</span><span class="sxs-lookup"><span data-stu-id="59f9b-150">For a more detailed explanation about the information displayed in **Additional Information**, double-click the event.</span></span> <span data-ttu-id="59f9b-151">查看信息后，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="59f9b-151">After you have reviewed the information, click **Next**.</span></span>

10. <span data-ttu-id="59f9b-152">在 "**自定义**" 页面上，如果已完成安装和配置虚拟应用程序，请选择 "**立即停止**"，然后跳到此过程的步骤14。</span><span class="sxs-lookup"><span data-stu-id="59f9b-152">On the **Customize** page, if you are finished installing and configuring the virtual application, select **Stop now** and skip to step 14 of this procedure.</span></span> <span data-ttu-id="59f9b-153">如果要自定义下表中的任何项目，请选择 "**自定义**"。</span><span class="sxs-lookup"><span data-stu-id="59f9b-153">If you want to customize any of the items in the following list, select **Customize**.</span></span>

    -   <span data-ttu-id="59f9b-154">编辑与应用程序相关联的文件类型关联。</span><span class="sxs-lookup"><span data-stu-id="59f9b-154">Edit the file type associations associated with an application.</span></span>

    -   <span data-ttu-id="59f9b-155">准备用于流式处理的虚拟包。</span><span class="sxs-lookup"><span data-stu-id="59f9b-155">Prepare the virtual package for streaming.</span></span> <span data-ttu-id="59f9b-156">流改进了在目标计算机上运行虚拟应用程序包时的体验。</span><span class="sxs-lookup"><span data-stu-id="59f9b-156">Streaming improves the experience when the virtual application package is run on target computers.</span></span>

    -   <span data-ttu-id="59f9b-157">指定可以运行此程序包的操作系统。</span><span class="sxs-lookup"><span data-stu-id="59f9b-157">Specify the operating systems that can run this package.</span></span>

    <span data-ttu-id="59f9b-158">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="59f9b-158">Click **Next**.</span></span>

11. <span data-ttu-id="59f9b-159">在 "**编辑快捷方式**" 页面上，你可以选择配置将与程序包中的各种应用程序关联的文件类型关联（FTA）。</span><span class="sxs-lookup"><span data-stu-id="59f9b-159">On the **Edit Shortcuts** page, you can optionally configure the file type associations (FTA) that will be associated with the various applications in the package.</span></span> <span data-ttu-id="59f9b-160">若要创建新的 FTA，请在左窗格中，选择并展开要自定义的应用程序，然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="59f9b-160">To create a new FTA, in the left pane, select and expand the application that you want to customize, and then click **Add**.</span></span> <span data-ttu-id="59f9b-161">在 "**添加文件类型关联**" 对话框中，为新的 FTA 提供必要的信息。</span><span class="sxs-lookup"><span data-stu-id="59f9b-161">In the **Add File Type Association** dialog box, provide the necessary information for the new FTA.</span></span> <span data-ttu-id="59f9b-162">在 "应用程序" 下，选择 "**快捷方式**" 以查看与应用程序相关联的快捷方式信息。</span><span class="sxs-lookup"><span data-stu-id="59f9b-162">Under the application, select **Shortcuts** to review the shortcut information associated with an application.</span></span> <span data-ttu-id="59f9b-163">在 "**位置**" 窗格中，您可以查看图标文件信息。</span><span class="sxs-lookup"><span data-stu-id="59f9b-163">In the **Location** pane, you can review the icon file information.</span></span> <span data-ttu-id="59f9b-164">若要编辑现有 FTA，请单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="59f9b-164">To edit an existing FTA, click **Edit**.</span></span> <span data-ttu-id="59f9b-165">若要删除 FTA，请选择 "FTA"，然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="59f9b-165">To remove an FTA, select the FTA, and then click **Remove**.</span></span> <span data-ttu-id="59f9b-166">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="59f9b-166">Click **Next**.</span></span>

12. <span data-ttu-id="59f9b-167">在 "**流**" 页面上，运行每个程序，以便可以在目标计算机上对其进行优化和更高效地运行。</span><span class="sxs-lookup"><span data-stu-id="59f9b-167">On the **Streaming** page, run each program so that it can be optimized and run more efficiently on target computers.</span></span> <span data-ttu-id="59f9b-168">运行所有应用程序可能需要几分钟的时间。</span><span class="sxs-lookup"><span data-stu-id="59f9b-168">It can take several minutes for all the applications to run.</span></span> <span data-ttu-id="59f9b-169">在所有应用程序运行后，关闭每个应用程序，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="59f9b-169">After all applications have run, close each of the applications, and then click **Next**.</span></span>

   **<span data-ttu-id="59f9b-170">注意</span><span class="sxs-lookup"><span data-stu-id="59f9b-170">Note</span></span>**  
   <span data-ttu-id="59f9b-171">如果要在此步骤中停止应用程序的加载，请在 "**应用程序启动**" 对话框中，单击 "**停止**"，然后选择其中一个复选框、"**停止所有应用程序**" 或 "**停止此应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="59f9b-171">If you want to stop an application from loading during this step, in the **Application Launch** dialog box, click **Stop** and select one of the check boxes, **Stop all applications** or **Stop this application only**.</span></span>



13. <span data-ttu-id="59f9b-172">在 "**目标操作系统**" 页面上，指定可运行此程序包的操作系统。</span><span class="sxs-lookup"><span data-stu-id="59f9b-172">On the **Target OS** page, specify the operating systems that can run this package.</span></span> <span data-ttu-id="59f9b-173">若要在你的环境中启用所有支持的操作系统以运行此程序包，请选中 "**允许此程序包在任何操作系统上运行**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="59f9b-173">To enable all supported operating systems in your environment to run this package, select the **Allow this package to run on any operating system** check box.</span></span> <span data-ttu-id="59f9b-174">若要将此程序包配置为仅在特定操作系统上运行，请选中 "**仅允许此程序包在下列操作系统上运行**" 复选框，然后选择可以运行此程序包的操作系统。</span><span class="sxs-lookup"><span data-stu-id="59f9b-174">To configure this package to run only on specific operating systems, select the **Allow this package to run only on the following operating systems** check box, and then select the operating systems that can run this package.</span></span> <span data-ttu-id="59f9b-175">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="59f9b-175">Click **Next**.</span></span>

14. <span data-ttu-id="59f9b-176">在 "**创建程序包**" 页面上，若要在不保存的情况下修改程序包，请选择 **"继续使用程序包编辑器修改程序包而不**保存" 复选框。</span><span class="sxs-lookup"><span data-stu-id="59f9b-176">On the **Create Package** page, to modify the package without saving it, select **Continue to modify package without saving using the package editor** check box.</span></span> <span data-ttu-id="59f9b-177">选择此选项将在 Sequencer 控制台中打开程序包，以便你可以在保存包之前对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="59f9b-177">Selecting this option opens the package in the Sequencer console so that you can modify the package before it is saved.</span></span> <span data-ttu-id="59f9b-178">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="59f9b-178">Click **Next**.</span></span>

   <span data-ttu-id="59f9b-179">若要立即保存程序包，请选中 "**立即保存程序包**" 默认值。</span><span class="sxs-lookup"><span data-stu-id="59f9b-179">To save the package immediately, select the default **Save the package now**.</span></span> <span data-ttu-id="59f9b-180">（可选）选择 "**注释**" 以添加将与程序包相关联的注释。</span><span class="sxs-lookup"><span data-stu-id="59f9b-180">Optionally, select **Comments** to add comments that will be associated with the package.</span></span> <span data-ttu-id="59f9b-181">对于标识版本以及有关程序包的其他信息，评论非常有用。</span><span class="sxs-lookup"><span data-stu-id="59f9b-181">Comments are useful for identifying version and other information about the package.</span></span> <span data-ttu-id="59f9b-182">还会显示默认**保存位置**。</span><span class="sxs-lookup"><span data-stu-id="59f9b-182">The default **Save Location** is also displayed.</span></span> <span data-ttu-id="59f9b-183">若要更改默认位置，请单击 "**浏览**" 并指定新位置。</span><span class="sxs-lookup"><span data-stu-id="59f9b-183">To change the default location, click **Browse** and specify the new location.</span></span> <span data-ttu-id="59f9b-184">将显示未压缩的程序包大小。</span><span class="sxs-lookup"><span data-stu-id="59f9b-184">The uncompressed package size is displayed.</span></span> <span data-ttu-id="59f9b-185">如果程序包大小超过 4 GB （未压缩），并且你打算将程序包流式传输到目标计算机，则必须选择 "**压缩程序包**"。</span><span class="sxs-lookup"><span data-stu-id="59f9b-185">If the package size exceeds 4 GB (uncompressed) and you plan to stream the package to target computers, you must select **Compress Package**.</span></span> <span data-ttu-id="59f9b-186">单击“创建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="59f9b-186">Click **Create**.</span></span>

15. <span data-ttu-id="59f9b-187">在 "**完成**" 页面上，在查看 "**成功的虚拟应用程序包" 报表**窗格中显示的信息后，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="59f9b-187">On the **Completion** page, after you have reviewed the information that is displayed in the **Successful Virtual Application Package Report** pane, click **Close**.</span></span> <span data-ttu-id="59f9b-188">"**成功的虚拟应用程序包报告**" 窗格中显示的信息也可在此过程的步骤14中指定的目录中提供，该目录位于名为**Reports.xml**的文件中。</span><span class="sxs-lookup"><span data-stu-id="59f9b-188">The information displayed in the **Successful Virtual Application Package Report** pane is also available in the directory specified in step 14 of this procedure, in a file named **Reports.xml**.</span></span>

   <span data-ttu-id="59f9b-189">程序包现在在 sequencer 中可用。</span><span class="sxs-lookup"><span data-stu-id="59f9b-189">The package is now available in the sequencer.</span></span> <span data-ttu-id="59f9b-190">单击 "**编辑 \ [包名称 \]** " 以编辑程序包属性。</span><span class="sxs-lookup"><span data-stu-id="59f9b-190">Click **Edit \[Package Name\]** to edit the package properties.</span></span> <span data-ttu-id="59f9b-191">有关修改程序包的详细信息，请参阅[如何修改现有虚拟应用程序包（app-v 4.6 SP1）](how-to-modify-an-existing-virtual-application-package--app-v-46-sp1-.md)。</span><span class="sxs-lookup"><span data-stu-id="59f9b-191">For more information about modifying a package, see [How to Modify an Existing Virtual Application Package (App-V 4.6 SP1)](how-to-modify-an-existing-virtual-application-package--app-v-46-sp1-.md).</span></span>

   **<span data-ttu-id="59f9b-192">重要提示</span><span class="sxs-lookup"><span data-stu-id="59f9b-192">Important</span></span>**  
   <span data-ttu-id="59f9b-193">成功创建虚拟应用程序包后，不能在运行 sequencer 的计算机上运行虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="59f9b-193">After you have successfully created a virtual application package, you cannot run the virtual application package on the computer that is running the sequencer.</span></span>



## <span data-ttu-id="59f9b-194">相关主题</span><span class="sxs-lookup"><span data-stu-id="59f9b-194">Related topics</span></span>


[<span data-ttu-id="59f9b-195">Application Virtualization Sequencer 的任务 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="59f9b-195">Tasks for the Application Virtualization Sequencer (App-V 4.6 SP1)</span></span>](tasks-for-the-application-virtualization-sequencer--app-v-46-sp1-.md)

[<span data-ttu-id="59f9b-196">如何确定要序列化的应用程序类型（App-v 4.6 SP1）</span><span class="sxs-lookup"><span data-stu-id="59f9b-196">How to Determine Which Type of Application to Sequence (App-V 4.6 SP1)</span></span>](how-to-determine-which-type-of-application-to-sequence---app-v-46-sp1-.md)









