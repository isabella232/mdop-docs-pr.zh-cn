---
title: 如何使用 App-V 包加速器创建虚拟应用程序包
description: 如何使用 App-V 包加速器创建虚拟应用程序包
author: dansimp
ms.assetid: 715e7526-e100-419c-8fc1-75cbfe433835
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 547cb93f334e025243937a97a1f904410fe2d504
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798503"
---
# <span data-ttu-id="82de5-103">如何使用 App-V 包加速器创建虚拟应用程序包</span><span class="sxs-lookup"><span data-stu-id="82de5-103">How to Create a Virtual Application Package Using an App-V Package Accelerator</span></span>


**<span data-ttu-id="82de5-104">重要提示</span><span class="sxs-lookup"><span data-stu-id="82de5-104">Important</span></span>**  
<span data-ttu-id="82de5-105">App-v 5.0 Sequencer 不会向你用于创建包加速器的软件应用程序授予任何许可证权限。</span><span class="sxs-lookup"><span data-stu-id="82de5-105">The App-V 5.0 Sequencer does not grant any license rights to the software application that you use to create the Package Accelerator.</span></span> <span data-ttu-id="82de5-106">你必须遵守你使用的应用程序的所有最终用户许可条款。</span><span class="sxs-lookup"><span data-stu-id="82de5-106">You must abide by all end user license terms for the application that you use.</span></span> <span data-ttu-id="82de5-107">您有责任确保软件应用程序的许可条款允许您使用 App-v 5.0 Sequencer 创建软件包加速器。</span><span class="sxs-lookup"><span data-stu-id="82de5-107">It is your responsibility to make sure that the software application’s license terms allow you to create a Package Accelerator with the App-V 5.0 Sequencer.</span></span>



<span data-ttu-id="82de5-108">使用以下过程创建带有 App-v 5.0 程序包加速器的虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="82de5-108">Use the following procedure to create a virtual application package with the App-V 5.0 Package Accelerator.</span></span>

**<span data-ttu-id="82de5-109">注意</span><span class="sxs-lookup"><span data-stu-id="82de5-109">Note</span></span>**  
<span data-ttu-id="82de5-110">在开始此过程之前，请将所需的软件包加速器本地复制到运行 app-v 5.0 Sequencer 的计算机。</span><span class="sxs-lookup"><span data-stu-id="82de5-110">Before you start this procedure, copy the required Package Accelerator locally to the computer that runs the App-V 5.0 Sequencer.</span></span> <span data-ttu-id="82de5-111">你还应将程序包所需的所有安装文件复制到运行 Sequencer 的计算机上的本地目录。</span><span class="sxs-lookup"><span data-stu-id="82de5-111">You should also copy all required installation files for the package to a local directory on the computer that runs the Sequencer.</span></span> <span data-ttu-id="82de5-112">这是你必须在此过程的步骤5中指定的目录。</span><span class="sxs-lookup"><span data-stu-id="82de5-112">This is the directory that you have to specify in step 5 of this procedure.</span></span>



**<span data-ttu-id="82de5-113">使用 app-v 5.0 程序包加速器创建虚拟应用程序包</span><span class="sxs-lookup"><span data-stu-id="82de5-113">To create a virtual application package with an App-V 5.0 Package Accelerator</span></span>**

1.  <span data-ttu-id="82de5-114">若要启动 app-v-sequencer，请在运行 app-v 5.0 Sequencer 的计算机上，单击 "**启动**  /  **所有程序**  /  **microsoft application virtualization**  /  **microsoft application virtualization Sequencer**"。</span><span class="sxs-lookup"><span data-stu-id="82de5-114">To start the App-V Sequencer, on the computer that runs the App-V 5.0 Sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="82de5-115">若要启动 "**创建新程序包" 向导**，请单击 "**创建新的虚拟应用程序包**"。</span><span class="sxs-lookup"><span data-stu-id="82de5-115">To start the **Create New Package Wizard**, click **Create a New Virtual Application Package**.</span></span> <span data-ttu-id="82de5-116">若要创建程序包，请选中 "**使用包加速器创建程序包**" 复选框，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="82de5-116">To create the package, select the **Create Package using a Package Accelerator** check box, and then click **Next**.</span></span>

3.  <span data-ttu-id="82de5-117">若要指定将用于创建新虚拟应用程序包的程序包加速器，请单击 "**选择包加速器**" 页面上的 "**浏览**"。</span><span class="sxs-lookup"><span data-stu-id="82de5-117">To specify the package accelerator that will be used to create the new virtual application package, click **Browse** on the **Select Package Accelerator** page.</span></span> <span data-ttu-id="82de5-118">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="82de5-118">Click **Next**.</span></span>

    **<span data-ttu-id="82de5-119">重要提示</span><span class="sxs-lookup"><span data-stu-id="82de5-119">Important</span></span>**  
    <span data-ttu-id="82de5-120">如果无法验证程序包加速器的发布者，并且它不包含有效的数字签名，则必须确认你信任程序包加速器的源，然后再单击 "**运行**"。</span><span class="sxs-lookup"><span data-stu-id="82de5-120">If the publisher of the package accelerator cannot be verified and does not contain a valid digital signature, then before you click **Run**, you must confirm that you trust the source of the package accelerator.</span></span> <span data-ttu-id="82de5-121">在 "**安全警告**" 对话框中确认您的选择。</span><span class="sxs-lookup"><span data-stu-id="82de5-121">Confirm your choice in the **Security Warning** dialog box.</span></span>



4.  <span data-ttu-id="82de5-122">在 "**指南**" 页上，查看 "信息" 窗格中显示的发布指南信息。</span><span class="sxs-lookup"><span data-stu-id="82de5-122">On the **Guidance** page, review the publishing guidance information that is displayed in the information pane.</span></span> <span data-ttu-id="82de5-123">此信息是在创建程序包加速器时添加的，它包含有关如何创建和发布程序包的指南。</span><span class="sxs-lookup"><span data-stu-id="82de5-123">This information was added when the Package Accelerator was created and it contains guidance about how to create and publish the package.</span></span> <span data-ttu-id="82de5-124">若要将指南信息导出到文本（.txt）文件，请单击 "**导出**"，指定应保存该文件的位置，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="82de5-124">To export the guidance information to a text (.txt) file, click **Export** and specify the location where the file should be saved, and then click **Next**.</span></span>

5.  <span data-ttu-id="82de5-125">在 "**选择安装文件**" 页面上，单击 "创建**新文件夹**" 以创建一个本地文件夹，其中包含程序包所需的所有安装文件，并指定应保存文件夹的位置。</span><span class="sxs-lookup"><span data-stu-id="82de5-125">On the **Select Installation Files** page, click **Make New Folder** to create a local folder that contains all required installation files for the package, and specify where the folder should be saved.</span></span> <span data-ttu-id="82de5-126">还必须指定要分配给文件夹的名称。</span><span class="sxs-lookup"><span data-stu-id="82de5-126">You must also specify a name to be assigned to the folder.</span></span> <span data-ttu-id="82de5-127">然后，您必须将所有所需的安装文件复制到您指定的位置。</span><span class="sxs-lookup"><span data-stu-id="82de5-127">You must then copy all required installation files to the location that you specified.</span></span> <span data-ttu-id="82de5-128">如果包含安装文件的文件夹已存在于运行 Sequencer 的计算机上，请单击 "**浏览**" 以选择该文件夹。</span><span class="sxs-lookup"><span data-stu-id="82de5-128">If the folder that contains the installation files already exists on the computer that runs the Sequencer, click **Browse** to select the folder.</span></span>

    <span data-ttu-id="82de5-129">或者，如果已将安装文件复制到此计算机上的目录中，请单击 "**新建文件夹**"，浏览到包含安装文件的文件夹，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="82de5-129">Alternatively, if you have already copied the installation files to a directory on this computer, click **Make New Folder**, browse to the folder that contains the installation files, and then click **Next**.</span></span>

    **<span data-ttu-id="82de5-130">注意</span><span class="sxs-lookup"><span data-stu-id="82de5-130">Note</span></span>**  
    <span data-ttu-id="82de5-131">你可以指定以下支持的安装文件类型：</span><span class="sxs-lookup"><span data-stu-id="82de5-131">You can specify the following types of supported installation files:</span></span>

    -   <span data-ttu-id="82de5-132">Windows Installer 文件（**.msi**）</span><span class="sxs-lookup"><span data-stu-id="82de5-132">Windows Installer files (**.msi**)</span></span>

    -   <span data-ttu-id="82de5-133">Cabinet 文件（.cab）</span><span class="sxs-lookup"><span data-stu-id="82de5-133">Cabinet files (.cab)</span></span>

    -   <span data-ttu-id="82de5-134">文件扩展名为 .zip 的压缩文件</span><span class="sxs-lookup"><span data-stu-id="82de5-134">Compressed files with a .zip file name extension</span></span>

    -   <span data-ttu-id="82de5-135">实际应用程序文件</span><span class="sxs-lookup"><span data-stu-id="82de5-135">The actual application files</span></span>

    <span data-ttu-id="82de5-136">不支持以下文件类型： **.msp**和 **.exe**文件。</span><span class="sxs-lookup"><span data-stu-id="82de5-136">The following file types are not supported: **.msp** and **.exe** files.</span></span> <span data-ttu-id="82de5-137">如果指定 **.exe**文件，则必须手动解压缩安装文件。</span><span class="sxs-lookup"><span data-stu-id="82de5-137">If you specify an **.exe** file, you must extract the installation files manually.</span></span>



~~~
If the package accelerator requires an application to be installed before you apply the Package Accelerator, and if you have already installed the required application, select **I have installed all applications**, and then click **Next** on the **Local Installation** page.
~~~

6. <span data-ttu-id="82de5-138">在 "**程序包名称**" 页面上，指定将与程序包关联的名称。</span><span class="sxs-lookup"><span data-stu-id="82de5-138">On the **Package Name** page, specify a name that will be associated with the package.</span></span> <span data-ttu-id="82de5-139">你指定的名称在 App-v 管理控制台中标识程序包。</span><span class="sxs-lookup"><span data-stu-id="82de5-139">The name that you specify identifies the package in the App-V Management Console.</span></span> <span data-ttu-id="82de5-140">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="82de5-140">Click **Next**.</span></span>

7. <span data-ttu-id="82de5-141">在 "**创建程序包**" 页面上，提供将与程序包相关联的注释。</span><span class="sxs-lookup"><span data-stu-id="82de5-141">On the **Create Package** page, provide comments that will be associated with the package.</span></span> <span data-ttu-id="82de5-142">注释应包含有关正在创建的程序包的标识信息。</span><span class="sxs-lookup"><span data-stu-id="82de5-142">The comments should contain identifying information about the package that you are creating.</span></span> <span data-ttu-id="82de5-143">若要确认创建程序包的位置，请查看 "**保存位置**" 中显示的信息。</span><span class="sxs-lookup"><span data-stu-id="82de5-143">To confirm the location where the package is created, review the information that is displayed in **Save Location**.</span></span> <span data-ttu-id="82de5-144">若要压缩程序包，请选择 "**压缩包**"。</span><span class="sxs-lookup"><span data-stu-id="82de5-144">To compress the package, select **Compress Package**.</span></span> <span data-ttu-id="82de5-145">如果要跨网络传输包，或者程序包大小超过 4 GB，请选中 "**压缩包**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="82de5-145">Select the **Compress Package** check box if the package will be streamed across the network, or when the package size exceeds 4 GB.</span></span>

   <span data-ttu-id="82de5-146">若要创建程序包，请单击 "**创建**"。</span><span class="sxs-lookup"><span data-stu-id="82de5-146">To create the package, click **Create**.</span></span> <span data-ttu-id="82de5-147">创建程序包后，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="82de5-147">After the package is created, click **Next**.</span></span>

8. <span data-ttu-id="82de5-148">在 "**配置软件**" 页面上，若要启用排序器来配置程序包中包含的应用程序，请选择 "**配置软件**"。</span><span class="sxs-lookup"><span data-stu-id="82de5-148">On the **Configure Software** page, to enable the Sequencer to configure the applications that are contained in the package, select **Configure Software**.</span></span> <span data-ttu-id="82de5-149">在此步骤中，你可以配置必须完成的任何关联任务，以便在目标计算机上运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="82de5-149">In this step you can configure any associated tasks that must be completed in order to run the application on the target computers.</span></span> <span data-ttu-id="82de5-150">例如，您可以配置任何相关的许可协议。</span><span class="sxs-lookup"><span data-stu-id="82de5-150">For example, you can configure any associated license agreements.</span></span>

   <span data-ttu-id="82de5-151">如果选择 "**配置软件**"，则可以使用 Sequencer 作为此步骤的一部分配置以下项：</span><span class="sxs-lookup"><span data-stu-id="82de5-151">If you select **Configure Software**, the following items can be configured using the Sequencer as part of this step:</span></span>

   -   <span data-ttu-id="82de5-152">**加载程序包**。</span><span class="sxs-lookup"><span data-stu-id="82de5-152">**Load Package**.</span></span> <span data-ttu-id="82de5-153">Sequencer 将加载与该包关联的文件。</span><span class="sxs-lookup"><span data-stu-id="82de5-153">The Sequencer loads the files that are associated with the package.</span></span> <span data-ttu-id="82de5-154">解码程序包可能需要几秒钟到一小时。</span><span class="sxs-lookup"><span data-stu-id="82de5-154">It can take several seconds to an hour to decode the package.</span></span>

   -   <span data-ttu-id="82de5-155">**运行每个程序**。</span><span class="sxs-lookup"><span data-stu-id="82de5-155">**Run Each Program**.</span></span> <span data-ttu-id="82de5-156">（可选）运行程序包中包含的程序。</span><span class="sxs-lookup"><span data-stu-id="82de5-156">Optionally run the programs that are contained in the package.</span></span> <span data-ttu-id="82de5-157">此步骤有助于完成在目标计算机上部署和运行程序包之前运行应用程序所需的任何相关许可证或配置任务。</span><span class="sxs-lookup"><span data-stu-id="82de5-157">This step is helpful to complete any associated license or configuration tasks that are required to run the application before you deploy and run the package on target computers.</span></span> <span data-ttu-id="82de5-158">若要一次运行所有程序，请选择至少一个程序，然后单击 "**全部运行**"。</span><span class="sxs-lookup"><span data-stu-id="82de5-158">To run all the programs at once, select at least one program, and then click **Run All**.</span></span> <span data-ttu-id="82de5-159">若要运行特定程序，请选择要运行的一个或一些程序，然后单击 "**运行所选**"。</span><span class="sxs-lookup"><span data-stu-id="82de5-159">To run specific programs, select the program or programs that you want to run, and then click **Run Selected**.</span></span> <span data-ttu-id="82de5-160">完成所需的配置任务，然后关闭应用程序。</span><span class="sxs-lookup"><span data-stu-id="82de5-160">Complete the required configuration tasks, and then close the applications.</span></span> <span data-ttu-id="82de5-161">运行所有程序可能需要几分钟的时间。</span><span class="sxs-lookup"><span data-stu-id="82de5-161">It can take several minutes for all programs to run.</span></span> <span data-ttu-id="82de5-162">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="82de5-162">Click **Next**.</span></span>

   -   <span data-ttu-id="82de5-163">**保存程序包**。</span><span class="sxs-lookup"><span data-stu-id="82de5-163">**Save Package**.</span></span> <span data-ttu-id="82de5-164">Sequencer 将保存包。</span><span class="sxs-lookup"><span data-stu-id="82de5-164">The Sequencer saves the package.</span></span>

   -   <span data-ttu-id="82de5-165">**主要功能块**。</span><span class="sxs-lookup"><span data-stu-id="82de5-165">**Primary Feature Block**.</span></span> <span data-ttu-id="82de5-166">Sequencer 通过重新生成主功能块来优化流包。</span><span class="sxs-lookup"><span data-stu-id="82de5-166">The Sequencer optimizes the package for streaming by rebuilding the primary feature block.</span></span>

   <span data-ttu-id="82de5-167">如果您不想配置应用程序，请单击 "**跳过此步骤**"，转到此过程的步骤9，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="82de5-167">If you do not want to configure the applications, click **Skip this step**, and to go to step 9 of this procedure, and then click **Next**.</span></span>

9. <span data-ttu-id="82de5-168">在 "**完成**" 页面上，查看 "**虚拟应用程序包报告**" 窗格中显示的信息后，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="82de5-168">On the **Completion** page, after you review the information that is displayed in the **Virtual Application Package Report** pane, click **Close**.</span></span>

   <span data-ttu-id="82de5-169">程序包现在在 Sequencer 中可用。</span><span class="sxs-lookup"><span data-stu-id="82de5-169">The package is now available in the Sequencer.</span></span> <span data-ttu-id="82de5-170">若要编辑程序包属性，请单击 "**编辑 \ [包名称 \]**"。</span><span class="sxs-lookup"><span data-stu-id="82de5-170">To edit the package properties, click **Edit \[Package Name\]**.</span></span> <span data-ttu-id="82de5-171">有关如何修改程序包的详细信息，请参阅[如何修改现有虚拟应用程序包](how-to-modify-an-existing-virtual-application-package-beta.md)。</span><span class="sxs-lookup"><span data-stu-id="82de5-171">For more information about how to modify a package, see [How to Modify an Existing Virtual Application Package](how-to-modify-an-existing-virtual-application-package-beta.md).</span></span>

   <span data-ttu-id="82de5-172">已**获得有关 app-v 的建议**？</span><span class="sxs-lookup"><span data-stu-id="82de5-172">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="82de5-173">在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="82de5-173">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="82de5-174">遇到了 app-v 问题？</span><span class="sxs-lookup"><span data-stu-id="82de5-174">Got an App-V issue?</span></span>** <span data-ttu-id="82de5-175">使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="82de5-175">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="82de5-176">相关主题</span><span class="sxs-lookup"><span data-stu-id="82de5-176">Related topics</span></span>


[<span data-ttu-id="82de5-177">App-V 5.0 的操作</span><span class="sxs-lookup"><span data-stu-id="82de5-177">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)









