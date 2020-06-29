---
title: 如何修改现有的虚拟应用程序包
description: 如何修改现有的虚拟应用程序包
author: dansimp
ms.assetid: 6cdeec00-e4fe-4210-b4c7-6ca1ac643ddd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: 95963610c8b725412f6d516ee22b1c2f4e186df6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798402"
---
# <span data-ttu-id="3b16a-103">如何修改现有的虚拟应用程序包</span><span class="sxs-lookup"><span data-stu-id="3b16a-103">How to Modify an Existing Virtual Application Package</span></span>


<span data-ttu-id="3b16a-104">本主题介绍了如何：</span><span class="sxs-lookup"><span data-stu-id="3b16a-104">This topic explains how to:</span></span>

-   [<span data-ttu-id="3b16a-105">更新现有虚拟应用程序包中的应用程序</span><span class="sxs-lookup"><span data-stu-id="3b16a-105">Update an application in an existing virtual application package</span></span>](#bkmk-update-app-in-pkg)

-   [<span data-ttu-id="3b16a-106">修改与现有虚拟应用程序包相关联的属性</span><span class="sxs-lookup"><span data-stu-id="3b16a-106">Modify the properties associated with an existing virtual application package</span></span>](#bkmk-chg-props-in-pkg)

-   [<span data-ttu-id="3b16a-107">将新应用程序添加到现有虚拟应用程序包</span><span class="sxs-lookup"><span data-stu-id="3b16a-107">Add a new application to an existing virtual application package</span></span>](#bkmk-add-app-to-pkg)

**<span data-ttu-id="3b16a-108">更新程序包之前：</span><span class="sxs-lookup"><span data-stu-id="3b16a-108">Before you update a package:</span></span>**

-   <span data-ttu-id="3b16a-109">确保已安装了 Microsoft Application Virtualization （App-v） Sequencer，这是修改虚拟应用程序包所必需的。</span><span class="sxs-lookup"><span data-stu-id="3b16a-109">Ensure that you’ve installed the Microsoft Application Virtualization (App-V) Sequencer, which is required for modifying a virtual application package.</span></span> <span data-ttu-id="3b16a-110">若要安装 app-v 排序器，请参阅[如何安装 Sequencer](how-to-install-the-sequencer-51beta-gb18030.md)。</span><span class="sxs-lookup"><span data-stu-id="3b16a-110">To install the App-V Sequencer, see [How to Install the Sequencer](how-to-install-the-sequencer-51beta-gb18030.md).</span></span>

-   <span data-ttu-id="3b16a-111">在安全位置保存 appv 文件，并在尝试打开要编辑的程序包之前始终信任源。</span><span class="sxs-lookup"><span data-stu-id="3b16a-111">Save the .appv file in a secure location and always trust the source before trying to open the package for editing.</span></span>

-   <span data-ttu-id="3b16a-112">更新程序包时，从部署配置文件中错误地删除了 "管理机构" 部分。</span><span class="sxs-lookup"><span data-stu-id="3b16a-112">The Managing Authority section is erroneously removed from the deployment configuration file when you update a package.</span></span> <span data-ttu-id="3b16a-113">开始更新之前，从现有部署配置文件复制管理机构部分，然后在转换完成后将复制的分区粘贴到新的配置文件中。</span><span class="sxs-lookup"><span data-stu-id="3b16a-113">Before starting the update, copy the Managing Authority section from the existing deployment configuration file, and then paste the copied section into the new configuration file after the conversion is complete.</span></span>

-   <span data-ttu-id="3b16a-114">如果在 Sequencer 中单击 "**修改现有虚拟应用程序包**" 以编辑程序包，但随后不进行任何更改并关闭程序包，则会更改程序包的流行为。</span><span class="sxs-lookup"><span data-stu-id="3b16a-114">If you click **Modify an Existing Virtual Application Package** in the Sequencer in order to edit a package, but then make no changes and close the package, the streaming behavior of the package is changed.</span></span> <span data-ttu-id="3b16a-115">将从 StreamMap.xml 文件中删除主功能块，并删除发布功能块中列出的所有文件。</span><span class="sxs-lookup"><span data-stu-id="3b16a-115">The primary feature block is removed from the StreamMap.xml file, and any files that were listed in the publishing feature block are removed.</span></span> <span data-ttu-id="3b16a-116">接收已编辑的程序包体验的用户，无论原始程序包的配置如何，这些程序包都将打包为流出故障。</span><span class="sxs-lookup"><span data-stu-id="3b16a-116">Users who receive the edited package experience that package as if it were stream-faulted, regardless of how the original package was configured.</span></span>

<a href="" id="bkmk-update-app-in-pkg"></a>**<span data-ttu-id="3b16a-117">更新现有虚拟应用程序包中的应用程序</span><span class="sxs-lookup"><span data-stu-id="3b16a-117">Update an application in an existing virtual application package</span></span>**

1.  <span data-ttu-id="3b16a-118">在运行 sequencer 的计算机上，单击 "**所有程序**"，指向 " **microsoft application virtualization**"，然后单击 " **microsoft application Virtualization sequencer**"。</span><span class="sxs-lookup"><span data-stu-id="3b16a-118">On the computer that runs the sequencer, click **All Programs**, point to **Microsoft Application Virtualization**, and then click **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="3b16a-119">在 app-v 排序器中，单击 "**修改现有虚拟应用程序包**" &gt; **下一步**。</span><span class="sxs-lookup"><span data-stu-id="3b16a-119">In the App-V Sequencer, click **Modify an Existing Virtual Application Package** &gt; **Next**.</span></span>

3.  <span data-ttu-id="3b16a-120">在 "**选择任务**" 页面上，单击 "**在现有程序包中更新应用程序**" &gt; **下一步**。</span><span class="sxs-lookup"><span data-stu-id="3b16a-120">On the **Select Task** page, click **Update Application in Existing Package** &gt; **Next**.</span></span>

4.  <span data-ttu-id="3b16a-121">在 "**选择程序包**" 页面上，单击 "**浏览**" 以找到包含要更新的应用程序的虚拟应用程序包，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="3b16a-121">On the **Select Package** page, click **Browse** to locate the virtual application package that contains the application to update, and then click **Next**.</span></span>

5.  <span data-ttu-id="3b16a-122">在 "**准备计算机**" 页面上，查看可能导致应用更新失败的问题或导致更新后的应用程序包含不必要的数据。</span><span class="sxs-lookup"><span data-stu-id="3b16a-122">On the **Prepare Computer** page, review the issues that could cause the application update to fail or cause the updated application to contain unnecessary data.</span></span> <span data-ttu-id="3b16a-123">继续之前，请先解决所有潜在问题。</span><span class="sxs-lookup"><span data-stu-id="3b16a-123">Resolve all potential issues before you continue.</span></span> <span data-ttu-id="3b16a-124">在进行更正并解决所有潜在问题后，单击 "**刷新** &gt; **下一个**"。</span><span class="sxs-lookup"><span data-stu-id="3b16a-124">After making any corrections and resolving all potential issues, click **Refresh** &gt; **Next**.</span></span>

    <span data-ttu-id="3b16a-125">**重要提示** 如果需要禁用病毒扫描软件，请首先扫描运行 sequencer 的计算机，以确保不会向程序包添加不需要的或恶意的文件。</span><span class="sxs-lookup"><span data-stu-id="3b16a-125">**Important** If you are required to disable virus scanning software, first scan the computer that runs the sequencer to ensure that no unwanted or malicious files are added to the package.</span></span>

6.  <span data-ttu-id="3b16a-126">在 "**选择安装程序**" 页面上，单击 "**浏览**" 并指定应用程序的更新安装文件。</span><span class="sxs-lookup"><span data-stu-id="3b16a-126">On the **Select Installer** page, click **Browse** and specify the update installation file for the application.</span></span> <span data-ttu-id="3b16a-127">如果更新没有关联的安装程序文件，并且你计划手动运行所有安装步骤，请选中 "**选择此选项以执行自定义安装**" 复选框，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="3b16a-127">If the update does not have an associated installer file, and if you plan to run all installation steps manually, select the **Select this option to perform a custom installation** check box, and then click **Next**.</span></span>

7.  <span data-ttu-id="3b16a-128">在 "**安装**" 页面上，当 sequencer 和应用程序安装准备就绪时，可以继续安装应用程序更新，以便 sequencer 可以监视安装过程。</span><span class="sxs-lookup"><span data-stu-id="3b16a-128">On the **Installation** page, when the sequencer and application installer are ready you can proceed to install the application update so the sequencer can monitor the installation process.</span></span> <span data-ttu-id="3b16a-129">如果必须在安装过程中运行其他安装文件，请单击 "**运行**"，然后找到并运行其他安装文件。</span><span class="sxs-lookup"><span data-stu-id="3b16a-129">If additional installation files must be run as part of the installation, click **Run**, and then locate and run the additional installation files.</span></span> <span data-ttu-id="3b16a-130">完成安装后，请选择 "**我已完成安装**"。</span><span class="sxs-lookup"><span data-stu-id="3b16a-130">When you are finished with the installation, select **I am finished installing**.</span></span> <span data-ttu-id="3b16a-131">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3b16a-131">Click **Next**.</span></span>

    <span data-ttu-id="3b16a-132">**注意** 排序器监视运行 sequencer 的计算机上发生的所有更改和安装。</span><span class="sxs-lookup"><span data-stu-id="3b16a-132">**Note** The sequencer monitors all changes and installations that occur on the computer that runs the sequencer.</span></span> <span data-ttu-id="3b16a-133">这包括在顺序向导之外执行的任何更改和安装。</span><span class="sxs-lookup"><span data-stu-id="3b16a-133">This includes any changes and installations that are performed outside of the sequencing wizard.</span></span>

8.  <span data-ttu-id="3b16a-134">在 "**安装报告**" 页面上，您可以查看有关已更新的虚拟应用程序的信息。</span><span class="sxs-lookup"><span data-stu-id="3b16a-134">On the **Installation Report** page, you can review information about the updated virtual application.</span></span> <span data-ttu-id="3b16a-135">在 "**其他信息**" 中，双击事件以获取更详细的信息。</span><span class="sxs-lookup"><span data-stu-id="3b16a-135">In **Additional Information**, double-click the event to obtain more detailed information.</span></span> <span data-ttu-id="3b16a-136">若要继续，请单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="3b16a-136">To proceed, click **Next**.</span></span>

9.  <span data-ttu-id="3b16a-137">在 "**流**" 页面上，运行每个程序，以便可以在目标计算机上对其进行优化和更高效地运行。</span><span class="sxs-lookup"><span data-stu-id="3b16a-137">On the **Streaming** page, run each program so that it can be optimized and run more efficiently on target computers.</span></span> <span data-ttu-id="3b16a-138">运行所有应用程序可能需要几分钟的时间。</span><span class="sxs-lookup"><span data-stu-id="3b16a-138">It can take several minutes for all of the applications to run.</span></span> <span data-ttu-id="3b16a-139">在所有应用程序运行后，关闭每个应用程序，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="3b16a-139">After all applications have run, close each of the applications, and then click **Next**.</span></span>

    <span data-ttu-id="3b16a-140">**注意** 在此步骤中，你可以停止应用程序的加载。</span><span class="sxs-lookup"><span data-stu-id="3b16a-140">**Note** You can stop an application from loading during this step.</span></span> <span data-ttu-id="3b16a-141">在 "**应用程序启动**" 对话框中，单击 "**停止**"，然后选择 "**停止所有应用程序**" 或 "**仅停止此应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="3b16a-141">In the **Application Launch** dialog box, click **Stop**, and then select either **Stop all applications** or **Stop this application only**.</span></span>   

10. <span data-ttu-id="3b16a-142">在 "**创建程序包**" 页面上，若要在不保存的情况下修改程序包，请选中 "**继续使用程序包编辑器修改包而不**保存" 复选框。</span><span class="sxs-lookup"><span data-stu-id="3b16a-142">On the **Create Package** page, to modify the package without saving it, select the check box for **Continue to modify package without saving using the package editor**.</span></span> <span data-ttu-id="3b16a-143">选择此选项时，程序包将在 App-v Sequencer 控制台中打开，在此情况下，你可以在保存包之前对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="3b16a-143">When you select this option, the package opens in the App-V Sequencer console, where you can modify the package before it is saved.</span></span> <span data-ttu-id="3b16a-144">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3b16a-144">Click **Next**.</span></span>

    <span data-ttu-id="3b16a-145">若要立即保存程序包，请选中 "**立即保存程序包**" 默认值。</span><span class="sxs-lookup"><span data-stu-id="3b16a-145">To save the package immediately, select the default **Save the package now**.</span></span> <span data-ttu-id="3b16a-146">添加可选**注释**以与程序包关联。</span><span class="sxs-lookup"><span data-stu-id="3b16a-146">Add optional **Comments** to associate with the package.</span></span> <span data-ttu-id="3b16a-147">批注有助于标识应用程序版本并提供有关程序包的其他信息。</span><span class="sxs-lookup"><span data-stu-id="3b16a-147">Comments are useful to identify the application version and provide other information about the package.</span></span> <span data-ttu-id="3b16a-148">还会显示默认**保存位置**。</span><span class="sxs-lookup"><span data-stu-id="3b16a-148">The default **Save Location** is also displayed.</span></span> <span data-ttu-id="3b16a-149">若要更改默认位置，请单击 "**浏览**" 并指定新位置。</span><span class="sxs-lookup"><span data-stu-id="3b16a-149">To change the default location, click **Browse** and specify the new location.</span></span> <span data-ttu-id="3b16a-150">单击“创建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3b16a-150">Click **Create**.</span></span>

11. <span data-ttu-id="3b16a-151">在**完成**页上，单击 "**关闭**" 以关闭向导。</span><span class="sxs-lookup"><span data-stu-id="3b16a-151">On the **Completion** page, click **Close** to close the wizard.</span></span> <span data-ttu-id="3b16a-152">程序包现在在 sequencer 中可用。</span><span class="sxs-lookup"><span data-stu-id="3b16a-152">The package is now available in the sequencer.</span></span>

<a href="" id="bkmk-chg-props-in-pkg"></a>**<span data-ttu-id="3b16a-153">修改与现有虚拟应用程序包相关联的属性</span><span class="sxs-lookup"><span data-stu-id="3b16a-153">Modify the properties associated with an existing virtual application package</span></span>**

1.  <span data-ttu-id="3b16a-154">在运行 sequencer 的计算机上，单击 "**所有程序**"，指向 " **microsoft application virtualization**"，然后单击 " **microsoft application Virtualization sequencer**"。</span><span class="sxs-lookup"><span data-stu-id="3b16a-154">On the computer that runs the sequencer, click **All Programs**, point to **Microsoft Application Virtualization**, and then click **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="3b16a-155">在 app-v 排序器中，单击 "**修改现有虚拟应用程序包**" &gt; **下一步**。</span><span class="sxs-lookup"><span data-stu-id="3b16a-155">In the App-V Sequencer, click **Modify an Existing Virtual Application Package** &gt; **Next**.</span></span>

3.  <span data-ttu-id="3b16a-156">在 "**选择任务**" 页面上，单击 " **Edit Package** &gt; **下一步**编辑包"。</span><span class="sxs-lookup"><span data-stu-id="3b16a-156">On the **Select Task** page, click **Edit Package** &gt; **Next**.</span></span>

4.  <span data-ttu-id="3b16a-157">在 "**选择程序包**" 页面上，单击 "**浏览**" 以找到包含要修改的应用程序属性的虚拟应用程序包，然后单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="3b16a-157">On the **Select Package** page, click **Browse** to locate the virtual application package that contains the application properties to modify, and then click **Edit**.</span></span>

5.  <span data-ttu-id="3b16a-158">在 App-v Sequencer 控制台中，根据需要执行以下任何任务：</span><span class="sxs-lookup"><span data-stu-id="3b16a-158">In the App-V Sequencer console, perform any of the following tasks as needed:</span></span>

    -   <span data-ttu-id="3b16a-159">导入和导出清单文件。</span><span class="sxs-lookup"><span data-stu-id="3b16a-159">Import and export the manifest file.</span></span>

    -   <span data-ttu-id="3b16a-160">启用或禁用浏览器帮助程序对象。</span><span class="sxs-lookup"><span data-stu-id="3b16a-160">Enable or disable Browser Helper Objects.</span></span>

    -   <span data-ttu-id="3b16a-161">导入或导出 VFS 文件。</span><span class="sxs-lookup"><span data-stu-id="3b16a-161">Import or export a VFS file.</span></span>

    -   <span data-ttu-id="3b16a-162">将目录导入到虚拟文件系统中。</span><span class="sxs-lookup"><span data-stu-id="3b16a-162">Import a directory into the virtual file system.</span></span>

    -   <span data-ttu-id="3b16a-163">导入和导出虚拟注册表项。</span><span class="sxs-lookup"><span data-stu-id="3b16a-163">Import and export virtual registry keys.</span></span>

    -   <span data-ttu-id="3b16a-164">查看程序包属性。</span><span class="sxs-lookup"><span data-stu-id="3b16a-164">View package properties.</span></span>

    -   <span data-ttu-id="3b16a-165">查看关联的程序包文件。</span><span class="sxs-lookup"><span data-stu-id="3b16a-165">View associated package files.</span></span>

    -   <span data-ttu-id="3b16a-166">编辑注册表设置。</span><span class="sxs-lookup"><span data-stu-id="3b16a-166">Edit registry settings.</span></span>

    -   <span data-ttu-id="3b16a-167">查看其他程序包设置（操作系统文件属性除外）。</span><span class="sxs-lookup"><span data-stu-id="3b16a-167">Review additional package settings (except operating system file properties).</span></span>

    -   <span data-ttu-id="3b16a-168">设置虚拟化注册表项状态（替代或合并）。</span><span class="sxs-lookup"><span data-stu-id="3b16a-168">Set virtualized registry key state (override or merge).</span></span>

    -   <span data-ttu-id="3b16a-169">设置虚拟化文件夹状态。</span><span class="sxs-lookup"><span data-stu-id="3b16a-169">Set virtualized folder state.</span></span>

    -   <span data-ttu-id="3b16a-170">添加或编辑快捷方式和文件类型关联。</span><span class="sxs-lookup"><span data-stu-id="3b16a-170">Add or edit shortcuts and file type associations.</span></span>

        <span data-ttu-id="3b16a-171">**注意** 若要编辑快捷方式或文件类型关联，必须首先打开要升级的程序包以添加新应用程序，然后转到最后一个编辑页面。</span><span class="sxs-lookup"><span data-stu-id="3b16a-171">**Note** To edit shortcuts or file type associations, you must first open the package for upgrade to add a new application, and then proceed to the final editing page.</span></span>

6.  <span data-ttu-id="3b16a-172">完成更改程序包属性后，单击 "**文件** &gt; **保存**" 以保存程序包。</span><span class="sxs-lookup"><span data-stu-id="3b16a-172">When you finish changing the package properties, click **File** &gt; **Save** to save the package.</span></span>

<a href="" id="bkmk-add-app-to-pkg"></a>**<span data-ttu-id="3b16a-173">将新应用程序添加到现有虚拟应用程序包</span><span class="sxs-lookup"><span data-stu-id="3b16a-173">Add a new application to an existing virtual application package</span></span>**

1.  <span data-ttu-id="3b16a-174">在运行 sequencer 的计算机上，单击 "**所有程序**"，指向 " **microsoft application virtualization**"，然后单击 " **microsoft application Virtualization sequencer**"。</span><span class="sxs-lookup"><span data-stu-id="3b16a-174">On the computer that runs the sequencer, click **All Programs**, point to **Microsoft Application Virtualization**, and then click **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="3b16a-175">在 app-v 排序器中，单击 "**修改现有虚拟应用程序包**" &gt; **下一步**。</span><span class="sxs-lookup"><span data-stu-id="3b16a-175">In the App-V Sequencer, click **Modify an Existing Virtual Application Package** &gt; **Next**.</span></span>

3.  <span data-ttu-id="3b16a-176">在 "**选择任务**" 页面上，单击 "下一步**添加新应用程序**" &gt; **Next**。</span><span class="sxs-lookup"><span data-stu-id="3b16a-176">On the **Select Task** page, click **Add New Application** &gt; **Next**.</span></span>

4.  <span data-ttu-id="3b16a-177">在 "**选择程序包**" 页面上，单击 "**浏览**" 以找到将向其添加应用程序的虚拟应用程序包，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="3b16a-177">On the **Select Package** page, click **Browse** to locate the virtual application package to which you will add the application, and then click **Next**.</span></span>

5.  <span data-ttu-id="3b16a-178">在 "**准备计算机**" 页面上，查看可能导致程序包创建失败的问题，或导致修改后的程序包包含不必要的数据。</span><span class="sxs-lookup"><span data-stu-id="3b16a-178">On the **Prepare Computer** page, review the issues that could cause the package creation to fail or cause the revised package to contain unnecessary data.</span></span> <span data-ttu-id="3b16a-179">继续之前，请先解决所有潜在问题。</span><span class="sxs-lookup"><span data-stu-id="3b16a-179">Resolve all potential issues before you continue.</span></span> <span data-ttu-id="3b16a-180">在进行更正并解决所有潜在问题后，单击 "**刷新** &gt; **下一个**"。</span><span class="sxs-lookup"><span data-stu-id="3b16a-180">After making any corrections and resolving all potential issues, click **Refresh** &gt; **Next**.</span></span>

    <span data-ttu-id="3b16a-181">**重要提示** 如果需要禁用病毒扫描软件，请首先扫描运行 sequencer 的计算机，以确保不会向程序包添加不需要的或恶意的文件。</span><span class="sxs-lookup"><span data-stu-id="3b16a-181">**Important** If you are required to disable virus scanning software, first scan the computer that runs the sequencer to ensure that no unwanted or malicious files can be added to the package.</span></span>

6.  <span data-ttu-id="3b16a-182">在 "**选择安装程序**" 页面上，单击 "**浏览**" 并指定应用程序的安装文件。</span><span class="sxs-lookup"><span data-stu-id="3b16a-182">On the **Select Installer** page, click **Browse** and specify the installation file for the application.</span></span> <span data-ttu-id="3b16a-183">如果应用程序没有关联的安装程序文件，并且你计划手动运行所有安装步骤，请选中 "**选择此选项以执行自定义安装**" 复选框，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="3b16a-183">If the application does not have an associated installer file and you plan to run all installation steps manually, select the **Select this option to perform a custom installation** check box, and then click **Next**.</span></span>

7.  <span data-ttu-id="3b16a-184">在 "**安装**" 页面上，当 sequencer 和应用程序安装准备就绪时，请安装该应用程序，以便排序器可以监视安装过程。</span><span class="sxs-lookup"><span data-stu-id="3b16a-184">On the **Installation** page, when the sequencer and application installer are ready, install the application so that the sequencer can monitor the installation process.</span></span> <span data-ttu-id="3b16a-185">如果必须在安装过程中运行其他安装文件，请单击 "**运行**"，然后找到并运行其他安装文件。</span><span class="sxs-lookup"><span data-stu-id="3b16a-185">If additional installation files must be run as part of the installation, click **Run**, and locate and run the additional installation files.</span></span> <span data-ttu-id="3b16a-186">完成安装后，请选择 "**我已完成安装** &gt; **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="3b16a-186">When you finish the installation, select **I am finished installing** &gt; **Next**.</span></span> <span data-ttu-id="3b16a-187">在 "**浏览文件夹**" 对话框中，指定将安装应用程序的主目录。</span><span class="sxs-lookup"><span data-stu-id="3b16a-187">In the **Browse for Folder** dialog box, specify the primary directory where the application will be installed.</span></span> <span data-ttu-id="3b16a-188">确保这是一个新位置，以便你不会覆盖虚拟应用程序包的现有版本。</span><span class="sxs-lookup"><span data-stu-id="3b16a-188">Ensure that this is a new location so that you don’t overwrite the existing version of the virtual application package.</span></span>

    <span data-ttu-id="3b16a-189">**注意** 排序器监视运行 sequencer 的计算机上发生的所有更改和安装。</span><span class="sxs-lookup"><span data-stu-id="3b16a-189">**Note** The sequencer monitors all changes and installations that occur on the computer that runs the sequencer.</span></span> <span data-ttu-id="3b16a-190">这包括在顺序向导之外执行的任何更改和安装。</span><span class="sxs-lookup"><span data-stu-id="3b16a-190">This includes any changes and installations that are performed outside of the sequencing wizard.</span></span>

8.  <span data-ttu-id="3b16a-191">在 "**配置软件**" 页面上，选择运行程序包中包含的程序。</span><span class="sxs-lookup"><span data-stu-id="3b16a-191">On the **Configure Software** page, optionally run the programs contained in the package.</span></span> <span data-ttu-id="3b16a-192">此步骤先完成运行应用程序所需的任何相关许可证或配置任务，然后再在目标计算机上部署和运行程序包。</span><span class="sxs-lookup"><span data-stu-id="3b16a-192">This step completes any associated license or configuration tasks that are required to run the application before you deploy and run the package on target computers.</span></span> <span data-ttu-id="3b16a-193">若要同时运行所有程序，请至少选择一个程序，然后单击 "**全部运行**"。</span><span class="sxs-lookup"><span data-stu-id="3b16a-193">To run all the programs at the same time, select at least one program, and then click **Run All**.</span></span> <span data-ttu-id="3b16a-194">若要运行特定程序，请选择要运行的一个或一些程序，然后单击 "**运行所选**"。</span><span class="sxs-lookup"><span data-stu-id="3b16a-194">To run specific programs, select the program or programs you want to run, and then click **Run Selected**.</span></span> <span data-ttu-id="3b16a-195">完成所需的配置任务，然后关闭应用程序。</span><span class="sxs-lookup"><span data-stu-id="3b16a-195">Complete the required configuration tasks and then close the applications.</span></span> <span data-ttu-id="3b16a-196">运行所有程序可能需要几分钟的时间。</span><span class="sxs-lookup"><span data-stu-id="3b16a-196">It can take several minutes for all programs to run.</span></span> <span data-ttu-id="3b16a-197">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3b16a-197">Click **Next**.</span></span>

9.  <span data-ttu-id="3b16a-198">在 "**安装报告**" 页面上，您可以查看有关已更新的虚拟应用程序的信息。</span><span class="sxs-lookup"><span data-stu-id="3b16a-198">On the **Installation Report** page, you can review information about the updated virtual application.</span></span> <span data-ttu-id="3b16a-199">在 "**其他信息**" 中，双击事件以获取更详细的信息，然后单击 "**下一步**" 以打开 "**自定义**" 页面。</span><span class="sxs-lookup"><span data-stu-id="3b16a-199">In **Additional Information**, double-click the event to obtain more detailed information, and then click **Next** to open the **Customize** page.</span></span>

10. <span data-ttu-id="3b16a-200">如果已完成安装和配置虚拟应用程序，请选择 "**立即停止**"，然后跳到此过程中的步骤13。</span><span class="sxs-lookup"><span data-stu-id="3b16a-200">If you are finished installing and configuring the virtual application, select **Stop now** and skip to step 13 of this procedure.</span></span> <span data-ttu-id="3b16a-201">如果您想要执行以下描述的自定义操作，请单击 "**自定义**"。</span><span class="sxs-lookup"><span data-stu-id="3b16a-201">If you want to perform the following described customization, click **Customize**.</span></span>

    <span data-ttu-id="3b16a-202">如果要自定义，请准备虚拟程序包以进行流式处理，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="3b16a-202">If you are customizing, prepare the virtual package for streaming, and then click **Next**.</span></span> <span data-ttu-id="3b16a-203">流改进了在目标计算机上运行虚拟应用程序包时的体验。</span><span class="sxs-lookup"><span data-stu-id="3b16a-203">Streaming improves the experience when the virtual application package is run on target computers.</span></span>

11. <span data-ttu-id="3b16a-204">在 "**流**" 页面上，运行每个程序，以便可以在目标计算机上对其进行优化和更高效地运行。</span><span class="sxs-lookup"><span data-stu-id="3b16a-204">On the **Streaming** page, run each program so that it can be optimized and run more efficiently on target computers.</span></span> <span data-ttu-id="3b16a-205">运行所有应用程序可能需要几分钟的时间。</span><span class="sxs-lookup"><span data-stu-id="3b16a-205">It can take several minutes for all the applications to run.</span></span> <span data-ttu-id="3b16a-206">在所有应用程序运行后，关闭每个应用程序，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="3b16a-206">After all applications have run, close each of the applications, and then click **Next**.</span></span>

    <span data-ttu-id="3b16a-207">**注意** 在此步骤中，你可以停止应用程序的加载。</span><span class="sxs-lookup"><span data-stu-id="3b16a-207">**Note** You can stop an application from loading during this step.</span></span> <span data-ttu-id="3b16a-208">在 "**应用程序启动**" 对话框中，单击 "**停止**"，然后选择 "**停止所有应用程序**" 或 "**仅停止此应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="3b16a-208">In the **Application Launch** dialog box, click **Stop** and then select either **Stop all applications** or **Stop this application only**.</span></span>

12. <span data-ttu-id="3b16a-209">在 "**创建程序包**" 页面上，若要在不保存的情况下修改程序包，请选中 "**继续使用程序包编辑器修改程序包而不保存**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="3b16a-209">On the **Create Package** page, to modify the package without saving it, select the **Continue to modify package without saving using the package editor** check box.</span></span> <span data-ttu-id="3b16a-210">选择此选项将在 App-v Sequencer 控制台中打开包，在此情况下，你可以在保存包之前对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="3b16a-210">Selecting this option opens the package in the App-V Sequencer console, where you can modify the package before saving it.</span></span> <span data-ttu-id="3b16a-211">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3b16a-211">Click **Next**.</span></span>

    <span data-ttu-id="3b16a-212">若要立即保存程序包，请选中 "**立即保存程序包**" 默认值。</span><span class="sxs-lookup"><span data-stu-id="3b16a-212">To save the package immediately, select the default **Save the package now**.</span></span> <span data-ttu-id="3b16a-213">添加可选**注释**以与程序包关联。</span><span class="sxs-lookup"><span data-stu-id="3b16a-213">Add optional **Comments** to associate with the package.</span></span> <span data-ttu-id="3b16a-214">批注对于提供有关程序包的应用程序版本和其他信息非常有用。</span><span class="sxs-lookup"><span data-stu-id="3b16a-214">Comments are useful for providing application versions and other information about the package.</span></span> <span data-ttu-id="3b16a-215">还会显示默认**保存位置**。</span><span class="sxs-lookup"><span data-stu-id="3b16a-215">The default **Save Location** is also displayed.</span></span> <span data-ttu-id="3b16a-216">若要更改默认位置，请单击 "**浏览**" 并指定新位置。</span><span class="sxs-lookup"><span data-stu-id="3b16a-216">To change the default location, click **Browse** and specify the new location.</span></span> <span data-ttu-id="3b16a-217">将显示未压缩的程序包大小。</span><span class="sxs-lookup"><span data-stu-id="3b16a-217">The uncompressed package size is displayed.</span></span> <span data-ttu-id="3b16a-218">单击“创建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3b16a-218">Click **Create**.</span></span>

13. <span data-ttu-id="3b16a-219">在**完成**页上，单击**关闭**。</span><span class="sxs-lookup"><span data-stu-id="3b16a-219">On the **Completion** page, click **Close**.</span></span> <span data-ttu-id="3b16a-220">程序包现在在 sequencer 中可用。</span><span class="sxs-lookup"><span data-stu-id="3b16a-220">The package is now available in the sequencer.</span></span>

    <span data-ttu-id="3b16a-221">已**获得有关 app-v 的建议**？</span><span class="sxs-lookup"><span data-stu-id="3b16a-221">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="3b16a-222">在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="3b16a-222">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="3b16a-223">遇到了 app-v 问题？</span><span class="sxs-lookup"><span data-stu-id="3b16a-223">Got an App-V issue?</span></span>** <span data-ttu-id="3b16a-224">使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="3b16a-224">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="3b16a-225">相关主题</span><span class="sxs-lookup"><span data-stu-id="3b16a-225">Related topics</span></span>

[<span data-ttu-id="3b16a-226">App-V 5.1 的操作</span><span class="sxs-lookup"><span data-stu-id="3b16a-226">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

 

 





