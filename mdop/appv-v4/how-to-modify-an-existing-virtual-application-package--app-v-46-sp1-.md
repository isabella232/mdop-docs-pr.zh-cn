---
title: 如何修改现有的虚拟应用程序包 (App-V 4.6 SP1)
description: 如何修改现有的虚拟应用程序包 (App-V 4.6 SP1)
author: dansimp
ms.assetid: f43a9927-4325-4b2d-829f-3068e4e84349
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f0e9d45a32afa240ce7f6fb2ee5dfbc51889c1fa
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801256"
---
# <span data-ttu-id="28cfe-103">如何修改现有的虚拟应用程序包 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="28cfe-103">How to Modify an Existing Virtual Application Package (App-V 4.6 SP1)</span></span>


<span data-ttu-id="28cfe-104">使用以下过程修改现有虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="28cfe-104">Use the following procedures to modify an existing virtual application package.</span></span> <span data-ttu-id="28cfe-105">可以使用以下过程执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="28cfe-105">You can use these procedures to:</span></span>

-   <span data-ttu-id="28cfe-106">更新现有虚拟应用程序包中的应用程序。</span><span class="sxs-lookup"><span data-stu-id="28cfe-106">Update an application that is part of an existing virtual application package.</span></span> <span data-ttu-id="28cfe-107">若要执行此任务，请使用本文档中的 **"更新现有应用程序包中的应用程序**" 过程。</span><span class="sxs-lookup"><span data-stu-id="28cfe-107">To perform this task, use the procedure **"To update an application in an existing application package"** in this document.</span></span>

-   <span data-ttu-id="28cfe-108">修改与现有虚拟应用程序包相关联的属性。</span><span class="sxs-lookup"><span data-stu-id="28cfe-108">Modify the properties associated with an existing virtual application package.</span></span> <span data-ttu-id="28cfe-109">若要执行此任务，请使用本文档中的 **"修改与现有虚拟应用程序包关联的属性"** 过程。</span><span class="sxs-lookup"><span data-stu-id="28cfe-109">To perform this task, use the procedure **"To modify the properties associated with an existing virtual application package"** in this document.</span></span>

-   <span data-ttu-id="28cfe-110">将新应用程序添加到现有虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="28cfe-110">Add a new application to an existing virtual application package.</span></span> <span data-ttu-id="28cfe-111">若要执行此任务，请使用本文档中的 **"将新应用程序添加到现有虚拟应用程序包"** 过程。</span><span class="sxs-lookup"><span data-stu-id="28cfe-111">To perform this task, use the procedure **"To add a new application to an existing virtual application package"** in this document.</span></span>

<span data-ttu-id="28cfe-112">必须安装 App-v Sequencer 才能修改虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="28cfe-112">You must have the App-V Sequencer installed to modify a virtual application package.</span></span> <span data-ttu-id="28cfe-113">有关安装 app-v 排序器的详细信息，请参阅[如何安装 Sequencer （app-v 4.6 SP1）](how-to-install-the-sequencer---app-v-46-sp1-.md)。</span><span class="sxs-lookup"><span data-stu-id="28cfe-113">For more information about installing the App-V Sequencer, see [How to Install the Sequencer (App-V 4.6 SP1)](how-to-install-the-sequencer---app-v-46-sp1-.md).</span></span>

**<span data-ttu-id="28cfe-114">更新现有虚拟应用程序包中的应用程序</span><span class="sxs-lookup"><span data-stu-id="28cfe-114">To update an application in an existing virtual application package</span></span>**

1.  <span data-ttu-id="28cfe-115">若要启动 app-v 排序器，请在运行 app-v 排序器的计算机上，单击 "**启动**  /  **所有程序**  /  **microsoft application virtualization**  /  **microsoft application virtualization Sequencer**"。</span><span class="sxs-lookup"><span data-stu-id="28cfe-115">To start the App-V Sequencer, on the computer that is running the App-V Sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="28cfe-116">在 App-v 排序器中，单击 "**修改现有虚拟应用程序包**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="28cfe-116">In the App-V Sequencer, click **Modify an Existing Virtual Application Package**, and then click **Next**.</span></span>

3.  <span data-ttu-id="28cfe-117">在 "**选择任务**" 页面上，单击 "**更新现有程序包中的应用程序**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="28cfe-117">On the **Select Task** page, click **Update Application in Existing Package**, and then click **Next**.</span></span>

4.  <span data-ttu-id="28cfe-118">在 "**选择程序包**" 页面上，单击 "**浏览**" 以找到包含要更新的应用程序的虚拟应用程序包，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="28cfe-118">On the **Select Package** page, click **Browse** to locate the virtual application package that contains the application that you want to update, and then click **Next**.</span></span>

5.  <span data-ttu-id="28cfe-119">在 "**准备计算机**" 页面上，查看可能导致应用程序更新失败的问题，或者查看应用程序更新以包含不必要的数据。</span><span class="sxs-lookup"><span data-stu-id="28cfe-119">On the **Prepare Computer** page, review the issues that could cause the application update to fail, or for the application update to contain unnecessary data.</span></span> <span data-ttu-id="28cfe-120">我们强烈建议您先解决所有潜在问题，然后再继续。</span><span class="sxs-lookup"><span data-stu-id="28cfe-120">We strongly recommend that you resolve all potential issues before you continue.</span></span> <span data-ttu-id="28cfe-121">修复冲突后，若要更新显示的信息，请单击 "**刷新**"。</span><span class="sxs-lookup"><span data-stu-id="28cfe-121">After you have fixed the conflicts, to update the information that is displayed, click **Refresh**.</span></span> <span data-ttu-id="28cfe-122">解决所有潜在问题后，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="28cfe-122">After you have resolved all potential issues, click **Next**.</span></span>

    <span data-ttu-id="28cfe-123">**重要提示** 如果需要禁用病毒扫描软件，请扫描运行 sequencer 的计算机，以确保不会向程序包添加不需要的或恶意的文件。</span><span class="sxs-lookup"><span data-stu-id="28cfe-123">**Important** If you are required to disable virus scanning software, scan the computer running the sequencer to ensure that no unwanted or malicious files are added to the package.</span></span>

     

6.  <span data-ttu-id="28cfe-124">在 "**选择安装程序**" 页面上，单击 "**浏览**" 并指定应用程序的更新安装文件。</span><span class="sxs-lookup"><span data-stu-id="28cfe-124">On the **Select Installer** page, click **Browse** and specify the update installation file for the application.</span></span> <span data-ttu-id="28cfe-125">如果更新没有关联的安装程序文件，并且你计划手动运行所有安装步骤，请选中 "**选择此选项以执行自定义安装**" 复选框，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="28cfe-125">If the update does not have an associated installer file and you plan to run all installation steps manually, select the **Select this option to perform a custom installation** check box, and then click **Next**.</span></span>

7.  <span data-ttu-id="28cfe-126">在 "**安装**" 页面上，当 sequencer 和应用程序安装准备就绪时，请安装应用程序更新，以便 sequencer 可以监视安装过程。</span><span class="sxs-lookup"><span data-stu-id="28cfe-126">On the **Installation** page, when the sequencer and application installer are ready, install the application update so the sequencer can monitor the installation process.</span></span> <span data-ttu-id="28cfe-127">如果必须在安装过程中运行其他安装文件，请单击 "**运行**"，然后找到并运行其他安装文件。</span><span class="sxs-lookup"><span data-stu-id="28cfe-127">If additional installation files must be run as part of the installation, click **Run** and locate and run the additional installation files.</span></span> <span data-ttu-id="28cfe-128">完成安装后，请选择 "**我已完成安装**"。</span><span class="sxs-lookup"><span data-stu-id="28cfe-128">When you are finished with the installation, select **I am finished installing**.</span></span> <span data-ttu-id="28cfe-129">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="28cfe-129">Click **Next**.</span></span>

    <span data-ttu-id="28cfe-130">**注意** Sequencer 将监视运行 sequencer 的计算机的所有更改和安装，包括在序列化向导外执行的更改和安装。</span><span class="sxs-lookup"><span data-stu-id="28cfe-130">**Note** The sequencer monitors all changes and installations to the computer running the sequencer, including the changes and installations that are performed outside of the sequencing wizard.</span></span>

     

8.  <span data-ttu-id="28cfe-131">在 "**安装报告**" 页面上，你可以查看有关你刚刚更新的虚拟应用程序的信息。</span><span class="sxs-lookup"><span data-stu-id="28cfe-131">On the **Installation Report** page, you can review information about the virtual application you just updated.</span></span> <span data-ttu-id="28cfe-132">有关**其他信息**中显示的信息的更多详细说明，请双击该事件。</span><span class="sxs-lookup"><span data-stu-id="28cfe-132">For a more detailed explanation about the information displayed in **Additional Information**, double-click the event.</span></span> <span data-ttu-id="28cfe-133">查看信息后，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="28cfe-133">After you have reviewed the information, click **Next**.</span></span>

9.  <span data-ttu-id="28cfe-134">在 "**流**" 页面上，运行每个程序，以便可以在目标计算机上对其进行优化和更高效地运行。</span><span class="sxs-lookup"><span data-stu-id="28cfe-134">On the **Streaming** page, run each program so that it can be optimized and run more efficiently on target computers.</span></span> <span data-ttu-id="28cfe-135">运行所有应用程序可能需要几分钟的时间。</span><span class="sxs-lookup"><span data-stu-id="28cfe-135">It can take several minutes for all the applications to run.</span></span> <span data-ttu-id="28cfe-136">在所有应用程序运行后，关闭每个应用程序，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="28cfe-136">After all applications have run, close each of the applications, and then click **Next**.</span></span>

    <span data-ttu-id="28cfe-137">**注意** 如果要在此步骤中停止应用程序的加载，请在 "**应用程序启动**" 对话框中，单击 "**停止**"，然后单击下列选项之一： "**停止所有应用程序**" 或 "**仅停止此应用程序**"，具体取决于所需内容。</span><span class="sxs-lookup"><span data-stu-id="28cfe-137">**Note** If you want to stop an application from loading during this step, in the **Application Launch** dialog box, click **Stop**, and then click one of the following options, **Stop all applications** or **Stop this application only**, depending on what you want.</span></span>

     

10. <span data-ttu-id="28cfe-138">在 "**创建程序包**" 页面上，若要在不保存的情况下修改程序包，请选中 "**继续使用程序包编辑器修改程序包而不保存**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="28cfe-138">On the **Create Package** page, to modify the package without saving it, select the **Continue to modify package without saving using the package editor** check box.</span></span> <span data-ttu-id="28cfe-139">选择此选项时，将打开 Sequencer 控制台中的程序包，以便你可以在保存包之前对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="28cfe-139">When you select this option, the package in the Sequencer console opens so that you can modify the package before it is saved.</span></span> <span data-ttu-id="28cfe-140">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="28cfe-140">Click **Next**.</span></span>

    <span data-ttu-id="28cfe-141">若要立即保存程序包，请选中 "**立即保存程序包**" 默认值。</span><span class="sxs-lookup"><span data-stu-id="28cfe-141">To save the package immediately, select the default **Save the package now**.</span></span> <span data-ttu-id="28cfe-142">添加将与程序包关联的可选**注释**。</span><span class="sxs-lookup"><span data-stu-id="28cfe-142">Add optional **Comments** that will be associated with the package.</span></span> <span data-ttu-id="28cfe-143">对于标识版本以及有关程序包的其他信息，评论非常有用。</span><span class="sxs-lookup"><span data-stu-id="28cfe-143">Comments are useful for identifying version and other information about the package.</span></span> <span data-ttu-id="28cfe-144">还会显示默认**保存位置**。</span><span class="sxs-lookup"><span data-stu-id="28cfe-144">The default **Save Location** is also displayed.</span></span> <span data-ttu-id="28cfe-145">若要更改默认位置，请单击 "**浏览**" 并指定新位置。</span><span class="sxs-lookup"><span data-stu-id="28cfe-145">To change the default location, click **Browse** and specify the new location.</span></span> <span data-ttu-id="28cfe-146">将显示未压缩的程序包大小。</span><span class="sxs-lookup"><span data-stu-id="28cfe-146">The uncompressed package size is displayed.</span></span> <span data-ttu-id="28cfe-147">如果程序包大小超过 4 GB （未压缩），并且你打算将程序包流式传输到目标计算机，则必须选择 "**压缩程序包**"，然后单击 "**创建**"。</span><span class="sxs-lookup"><span data-stu-id="28cfe-147">If the package size exceeds 4 GB (uncompressed) and you plan to stream the package to target computers, you must select **Compress Package**, and then click **Create**.</span></span>

11. <span data-ttu-id="28cfe-148">在**完成**页上，单击 "**关闭**" 以关闭向导。</span><span class="sxs-lookup"><span data-stu-id="28cfe-148">On the **Completion** page, click **Close** to close the wizard.</span></span> <span data-ttu-id="28cfe-149">程序包现在在 sequencer 中可用。</span><span class="sxs-lookup"><span data-stu-id="28cfe-149">The package is now available in the sequencer.</span></span>

**<span data-ttu-id="28cfe-150">修改与现有虚拟应用程序包相关联的属性</span><span class="sxs-lookup"><span data-stu-id="28cfe-150">To modify the properties associated with an existing virtual application package</span></span>**

1.  <span data-ttu-id="28cfe-151">若要启动 app-v 排序器，请在运行 app-v 排序器的计算机上，单击 "**启动**  /  **所有程序**  /  **microsoft application virtualization**  /  **microsoft application virtualization Sequencer**"。</span><span class="sxs-lookup"><span data-stu-id="28cfe-151">To start the App-V Sequencer, on the computer that is running the App-V Sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="28cfe-152">在 App-v 排序器中，单击 "**修改现有虚拟应用程序包**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="28cfe-152">In the App-V Sequencer, click **Modify an Existing Virtual Application Package**, and then click **Next**.</span></span>

3.  <span data-ttu-id="28cfe-153">在 "**选择任务**" 页面上，单击 "**编辑包**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="28cfe-153">On the **Select Task** page, click **Edit Package**, and then click **Next**.</span></span>

4.  <span data-ttu-id="28cfe-154">在 "**选择程序包**" 页面上，单击 "**浏览**" 以找到包含要修改的应用程序属性的虚拟应用程序包，然后单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="28cfe-154">On the **Select Package** page, click **Browse** to locate the virtual application package that contains the application properties that you want to modify, and then click **Edit**.</span></span>

5.  <span data-ttu-id="28cfe-155">在 Sequencer 控制台中，你可以执行以下任何任务：</span><span class="sxs-lookup"><span data-stu-id="28cfe-155">In the Sequencer console, you can perform any of the following tasks:</span></span>

    -   <span data-ttu-id="28cfe-156">查看程序包属性。</span><span class="sxs-lookup"><span data-stu-id="28cfe-156">View package properties.</span></span>

    -   <span data-ttu-id="28cfe-157">查看程序包更改历史记录。</span><span class="sxs-lookup"><span data-stu-id="28cfe-157">View package change history.</span></span>

    -   <span data-ttu-id="28cfe-158">查看关联的程序包文件。</span><span class="sxs-lookup"><span data-stu-id="28cfe-158">View associated package files.</span></span>

    -   <span data-ttu-id="28cfe-159">编辑注册表设置。</span><span class="sxs-lookup"><span data-stu-id="28cfe-159">Edit registry settings.</span></span>

    -   <span data-ttu-id="28cfe-160">查看其他程序包设置（操作系统文件属性除外）。</span><span class="sxs-lookup"><span data-stu-id="28cfe-160">Review additional package settings (except operating system file properties).</span></span>

    -   <span data-ttu-id="28cfe-161">创建关联的 Windows Installer （MSI）。</span><span class="sxs-lookup"><span data-stu-id="28cfe-161">Create an associated Windows Installer (MSI).</span></span>

    -   <span data-ttu-id="28cfe-162">修改 OSD 文件。</span><span class="sxs-lookup"><span data-stu-id="28cfe-162">Modify OSD file.</span></span>

    -   <span data-ttu-id="28cfe-163">压缩和解压缩程序包。</span><span class="sxs-lookup"><span data-stu-id="28cfe-163">Compress and uncompress package.</span></span>

    -   <span data-ttu-id="28cfe-164">添加文件类型关联。</span><span class="sxs-lookup"><span data-stu-id="28cfe-164">Add file type associations.</span></span>

    -   <span data-ttu-id="28cfe-165">设置虚拟化注册表项状态（替代或合并）。</span><span class="sxs-lookup"><span data-stu-id="28cfe-165">Set virtualized registry key state (override or merge).</span></span>

    -   <span data-ttu-id="28cfe-166">设置虚拟化文件夹状态。</span><span class="sxs-lookup"><span data-stu-id="28cfe-166">Set virtualized folder state.</span></span>

    -   <span data-ttu-id="28cfe-167">编辑虚拟文件系统映射。</span><span class="sxs-lookup"><span data-stu-id="28cfe-167">Edit virtual file system mappings.</span></span>

6.  <span data-ttu-id="28cfe-168">修改程序包属性后，单击 "**文件**  /  **保存**" 以保存程序包。</span><span class="sxs-lookup"><span data-stu-id="28cfe-168">When you have finished modifying the package properties, click **File** / **Save** to save the package,.</span></span>

**<span data-ttu-id="28cfe-169">将新应用程序添加到现有虚拟应用程序包</span><span class="sxs-lookup"><span data-stu-id="28cfe-169">To add a new application to an existing virtual application package</span></span>**

1.  <span data-ttu-id="28cfe-170">若要启动 app-v 排序器，请在运行 app-v 排序器的计算机上，单击 "**启动**  /  **所有程序**  /  **microsoft application virtualization**  /  **microsoft application virtualization Sequencer**"。</span><span class="sxs-lookup"><span data-stu-id="28cfe-170">To start the App-V Sequencer, on the computer that is running the App-V Sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="28cfe-171">在 App-v 排序器中，单击 "**修改现有虚拟应用程序包**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="28cfe-171">In the App-V Sequencer, click **Modify an Existing Virtual Application Package**, and then click **Next**.</span></span>

3.  <span data-ttu-id="28cfe-172">在 "**选择任务**" 页面上，单击 "**添加新应用程序**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="28cfe-172">On the **Select Task** page, click **Add New Application**, and then click **Next**.</span></span>

4.  <span data-ttu-id="28cfe-173">在 "**选择程序包**" 页面上，单击 "**浏览**" 以找到要将应用程序添加到的虚拟应用程序包，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="28cfe-173">On the **Select Package** page, click **Browse** to locate the virtual application package that you want to add the application to, and then click **Next**.</span></span>

5.  <span data-ttu-id="28cfe-174">在 "**准备计算机**" 页面上，查看可能导致程序包创建失败的问题，或者查看更新以包含不必要的数据。</span><span class="sxs-lookup"><span data-stu-id="28cfe-174">On the **Prepare Computer** page, review the issues that could cause the package creation to fail, or for the update to contain unnecessary data.</span></span> <span data-ttu-id="28cfe-175">我们强烈建议您先解决所有潜在问题，然后再继续。</span><span class="sxs-lookup"><span data-stu-id="28cfe-175">We strongly recommend that you resolve all potential issues before you continue.</span></span> <span data-ttu-id="28cfe-176">修复冲突后，若要更新显示的信息，请单击 "**刷新**"。</span><span class="sxs-lookup"><span data-stu-id="28cfe-176">After you have fixed the conflicts, to update the information that is displayed, click **Refresh**.</span></span> <span data-ttu-id="28cfe-177">解决所有潜在问题后，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="28cfe-177">After you have resolved all potential issues, click **Next**.</span></span>

    <span data-ttu-id="28cfe-178">**重要提示** 如果需要禁用病毒扫描软件，请扫描运行 sequencer 的计算机，以确保不会向程序包添加不需要的或恶意的文件。</span><span class="sxs-lookup"><span data-stu-id="28cfe-178">**Important** If you are required to disable virus scanning software, scan the computer running the sequencer to ensure that no unwanted or malicious files can be added to the package.</span></span>

     

6.  <span data-ttu-id="28cfe-179">在 "**选择安装程序**" 页面上，单击 "**浏览**" 并指定应用程序的安装文件。</span><span class="sxs-lookup"><span data-stu-id="28cfe-179">On the **Select Installer** page, click **Browse** and specify the installation file for the application.</span></span> <span data-ttu-id="28cfe-180">如果应用程序没有关联的安装程序文件，并且你计划手动运行所有安装步骤，请选中 "**选择此选项以执行自定义安装**" 复选框，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="28cfe-180">If the application does not have an associated installer file and you plan to run all installation steps manually, select the **Select this option to perform a custom installation** check box, and then click **Next**.</span></span>

7.  <span data-ttu-id="28cfe-181">在 "**安装**" 页面上，当 sequencer 和应用程序安装准备就绪时，请安装该应用程序，以便排序器可以监视安装过程。</span><span class="sxs-lookup"><span data-stu-id="28cfe-181">On the **Installation** page, when the sequencer and application installer are ready, install the application so the sequencer can monitor the installation process.</span></span> <span data-ttu-id="28cfe-182">如果必须在安装过程中运行其他安装文件，请单击 "**运行**"，然后找到并运行其他安装文件。</span><span class="sxs-lookup"><span data-stu-id="28cfe-182">If additional installation files must be run as part of the installation, click **Run**, and locate and run the additional installation files.</span></span> <span data-ttu-id="28cfe-183">完成安装后，请选择 "**我已完成安装**"。</span><span class="sxs-lookup"><span data-stu-id="28cfe-183">When you are finished with the installation, select **I am finished installing**.</span></span> <span data-ttu-id="28cfe-184">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="28cfe-184">Click **Next**.</span></span> <span data-ttu-id="28cfe-185">在 "**浏览文件夹**" 对话框中，指定将安装应用程序的主目录。</span><span class="sxs-lookup"><span data-stu-id="28cfe-185">In the **Browse for Folder** dialog box, specify the primary directory where the application will be installed.</span></span> <span data-ttu-id="28cfe-186">这应该是一个新位置，这样你就不会覆盖虚拟应用程序包的现有版本。</span><span class="sxs-lookup"><span data-stu-id="28cfe-186">This should be a new location so that you do not overwrite the existing version of the virtual application package.</span></span>

    <span data-ttu-id="28cfe-187">**注意** 排序器将监视运行排序器的计算机的所有更改和安装，包括在序列化向导外执行的更改和安装。</span><span class="sxs-lookup"><span data-stu-id="28cfe-187">**Note** All changes and installations to the computer running the sequencer are monitored by the sequencer, including the changes and installations that are performed outside of the sequencing wizard.</span></span>

     

8.  <span data-ttu-id="28cfe-188">在 "**配置软件**" 页面上，选择运行程序包中包含的程序。</span><span class="sxs-lookup"><span data-stu-id="28cfe-188">On the **Configure Software** page, optionally run the programs contained in the package.</span></span> <span data-ttu-id="28cfe-189">此步骤有助于完成在目标计算机上部署和运行程序包之前运行该应用程序所需的任何相关许可证或配置任务。</span><span class="sxs-lookup"><span data-stu-id="28cfe-189">This step helps complete any associated license or configuration tasks that are required to run the application before you deploy and run the package on target computers.</span></span> <span data-ttu-id="28cfe-190">若要同时运行所有程序，请至少选择一个程序，然后单击 "**全部运行**"。</span><span class="sxs-lookup"><span data-stu-id="28cfe-190">To run all the programs at the same time, select at least one program, and then click **Run All**.</span></span> <span data-ttu-id="28cfe-191">若要运行特定程序，请选择要运行的一个或一些程序，然后单击 "**运行所选**"。</span><span class="sxs-lookup"><span data-stu-id="28cfe-191">To run specific programs, select the program or programs you want to run, and then click **Run Selected**.</span></span> <span data-ttu-id="28cfe-192">完成所需的配置任务，然后关闭应用程序。</span><span class="sxs-lookup"><span data-stu-id="28cfe-192">Complete the required configuration tasks and then close the applications.</span></span> <span data-ttu-id="28cfe-193">运行所有程序可能需要几分钟的时间。</span><span class="sxs-lookup"><span data-stu-id="28cfe-193">It can take several minutes for all programs to run.</span></span> <span data-ttu-id="28cfe-194">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="28cfe-194">Click **Next**.</span></span>

9.  <span data-ttu-id="28cfe-195">在 "**安装报告**" 页面上，你可以查看有关你刚刚更新的虚拟应用程序的信息。</span><span class="sxs-lookup"><span data-stu-id="28cfe-195">On the **Installation Report** page, you can review information about the virtual application you just updated.</span></span> <span data-ttu-id="28cfe-196">有关**其他信息**中显示的信息的更多详细说明，请双击该事件。</span><span class="sxs-lookup"><span data-stu-id="28cfe-196">For a more detailed explanation about the information displayed in **Additional Information**, double-click the event.</span></span> <span data-ttu-id="28cfe-197">查看信息后，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="28cfe-197">After you have reviewed the information, click **Next**.</span></span>

10. <span data-ttu-id="28cfe-198">在 "**自定义**" 页面上，如果已完成安装和配置虚拟应用程序，请选择 "**立即停止**"，然后跳到此过程的步骤14。</span><span class="sxs-lookup"><span data-stu-id="28cfe-198">On the **Customize** page, if you are finished installing and configuring the virtual application, select **Stop now** and skip to step 14 of this procedure.</span></span> <span data-ttu-id="28cfe-199">如果要自定义下表中的任何项目，请单击 "**自定义**"。</span><span class="sxs-lookup"><span data-stu-id="28cfe-199">If you want to customize any of the items in the following list, click **Customize**.</span></span>

    -   <span data-ttu-id="28cfe-200">编辑与应用程序相关联的文件类型关联。</span><span class="sxs-lookup"><span data-stu-id="28cfe-200">Edit the file type associations associated with an application.</span></span>

    -   <span data-ttu-id="28cfe-201">准备用于流式处理的虚拟包。</span><span class="sxs-lookup"><span data-stu-id="28cfe-201">Prepare the virtual package for streaming.</span></span> <span data-ttu-id="28cfe-202">流改进了在目标计算机上运行虚拟应用程序包时的体验。</span><span class="sxs-lookup"><span data-stu-id="28cfe-202">Streaming improves the experience when the virtual application package is run on target computers.</span></span>

    <span data-ttu-id="28cfe-203">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="28cfe-203">Click **Next**.</span></span>

11. <span data-ttu-id="28cfe-204">在 "**编辑快捷方式**" 页面上，你可以选择配置将与程序包中的各种应用程序关联的文件类型关联（FTA）。</span><span class="sxs-lookup"><span data-stu-id="28cfe-204">On the **Edit Shortcuts** page, you can optionally configure the file type associations (FTA) that will be associated with the various applications in the package.</span></span> <span data-ttu-id="28cfe-205">若要创建新的 FTA，请在左窗格中选择并展开要自定义的应用程序，然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="28cfe-205">To create a new FTA, select and expand the application that you want to customize in the left pane, and then click **Add**.</span></span> <span data-ttu-id="28cfe-206">在 "**添加文件类型关联**" 对话框中，为新的 FTA 提供必要的信息。</span><span class="sxs-lookup"><span data-stu-id="28cfe-206">In the **Add File Type Association** dialog box, provide the necessary information for the new FTA.</span></span> <span data-ttu-id="28cfe-207">若要查看与应用程序相关联的快捷方式信息，请在 "应用程序" 下选择 "**快捷方式**" 复选框，然后在 "**位置**" 窗格中查看图标文件信息。</span><span class="sxs-lookup"><span data-stu-id="28cfe-207">To review the shortcut information associated with an application, under the application, select the **Shortcuts** check box, and in the **Location** pane, you can review the icon file information.</span></span> <span data-ttu-id="28cfe-208">若要编辑现有 FTA，请单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="28cfe-208">To edit an existing FTA, click **Edit**.</span></span> <span data-ttu-id="28cfe-209">若要删除 FTA，请选择 "FTA"，然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="28cfe-209">To remove an FTA, select the FTA, and then click **Remove**.</span></span> <span data-ttu-id="28cfe-210">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="28cfe-210">Click **Next**.</span></span>

12. <span data-ttu-id="28cfe-211">在 "**流**" 页面上，运行每个程序，以便可以在目标计算机上对其进行优化和更高效地运行。</span><span class="sxs-lookup"><span data-stu-id="28cfe-211">On the **Streaming** page, run each program so that it can be optimized and run more efficiently on target computers.</span></span> <span data-ttu-id="28cfe-212">运行所有应用程序可能需要几分钟的时间。</span><span class="sxs-lookup"><span data-stu-id="28cfe-212">It can take several minutes for all the applications to run.</span></span> <span data-ttu-id="28cfe-213">在所有应用程序运行后，关闭每个应用程序，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="28cfe-213">After all applications have run, close each of the applications, and then click **Next**.</span></span>

    <span data-ttu-id="28cfe-214">**注意** 如果要在此步骤中停止应用程序的加载，请在 "**应用程序启动**" 对话框中，单击 "**停止**"，然后选择 "**停止所有应用程序**" 或 "**仅停止此应用程序**" 复选框，具体取决于所需的内容。</span><span class="sxs-lookup"><span data-stu-id="28cfe-214">**Note** If you want to stop an application from loading during this step, in the **Application Launch** dialog box, click **Stop** and select either the **Stop all applications** or the **Stop this application only** check box, depending on what you want.</span></span>

     

13. <span data-ttu-id="28cfe-215">在 "**创建程序包**" 页面上，选择 "**继续使用程序包编辑器修改包而不保存**" 复选框，以便在不保存的情况下修改程序包。</span><span class="sxs-lookup"><span data-stu-id="28cfe-215">On the **Create Package** page, select the **Continue to modify package without saving using the package editor** check box, to modify the package without saving it.</span></span> <span data-ttu-id="28cfe-216">选择此选项时，将打开 sequencer 控制台中的程序包，以便你可以在保存包之前对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="28cfe-216">When you select this option, the package in the sequencer console opens so that you can modify the package before it is saved.</span></span> <span data-ttu-id="28cfe-217">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="28cfe-217">Click **Next**.</span></span>

    <span data-ttu-id="28cfe-218">选择 "**立即保存程序包**"，立即保存程序包。</span><span class="sxs-lookup"><span data-stu-id="28cfe-218">Select the default **Save the package now**, to save the package immediately.</span></span> <span data-ttu-id="28cfe-219">添加将与程序包关联的可选**注释**。</span><span class="sxs-lookup"><span data-stu-id="28cfe-219">Add optional **Comments** that will be associated with the package.</span></span> <span data-ttu-id="28cfe-220">对于标识版本以及有关程序包的其他信息，评论非常有用。</span><span class="sxs-lookup"><span data-stu-id="28cfe-220">Comments are useful for identifying version and other information about the package.</span></span> <span data-ttu-id="28cfe-221">还会显示默认**保存位置**。</span><span class="sxs-lookup"><span data-stu-id="28cfe-221">The default **Save Location** is also displayed.</span></span> <span data-ttu-id="28cfe-222">若要更改默认位置，请单击 "**浏览**" 并指定新位置。</span><span class="sxs-lookup"><span data-stu-id="28cfe-222">To change the default location, click **Browse** and specify the new location.</span></span> <span data-ttu-id="28cfe-223">将显示未压缩的程序包大小。</span><span class="sxs-lookup"><span data-stu-id="28cfe-223">The uncompressed package size is displayed.</span></span> <span data-ttu-id="28cfe-224">如果程序包大小超过 4 GB （未压缩），并且你打算将程序包流式传输到目标计算机，则必须选择 "**压缩程序包**"。</span><span class="sxs-lookup"><span data-stu-id="28cfe-224">If the package size exceeds 4 GB (uncompressed) and you plan to stream the package to target computers, you must select **Compress Package**.</span></span> <span data-ttu-id="28cfe-225">单击“创建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="28cfe-225">Click **Create**.</span></span>

14. <span data-ttu-id="28cfe-226">在**完成**页上，单击**关闭**。</span><span class="sxs-lookup"><span data-stu-id="28cfe-226">On the **Completion** page, click **Close**.</span></span> <span data-ttu-id="28cfe-227">程序包现在在 sequencer 中可用。</span><span class="sxs-lookup"><span data-stu-id="28cfe-227">The package is now available in the sequencer.</span></span>

## <span data-ttu-id="28cfe-228">相关主题</span><span class="sxs-lookup"><span data-stu-id="28cfe-228">Related topics</span></span>


[<span data-ttu-id="28cfe-229">Application Virtualization Sequencer 的任务 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="28cfe-229">Tasks for the Application Virtualization Sequencer (App-V 4.6 SP1)</span></span>](tasks-for-the-application-virtualization-sequencer--app-v-46-sp1-.md)

 

 





