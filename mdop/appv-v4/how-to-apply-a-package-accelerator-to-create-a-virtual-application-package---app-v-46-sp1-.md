---
title: 如何应用程序包加速器以创建虚拟应用程序包（App-v 4.6 SP1）
description: 如何应用程序包加速器以创建虚拟应用程序包（App-v 4.6 SP1）
author: dansimp
ms.assetid: ca0bd514-2bbf-4130-8c77-98d991cbe016
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ce6960fb95cce7f5e0eeb111412f27f945b0c1a5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802957"
---
# <span data-ttu-id="a6c3a-103">如何应用程序包加速器以创建虚拟应用程序包（App-v 4.6 SP1）</span><span class="sxs-lookup"><span data-stu-id="a6c3a-103">How to Apply a Package Accelerator to Create a Virtual Application Package (App-V 4.6 SP1)</span></span>


<span data-ttu-id="a6c3a-104">你可以使用 App-v 程序包加速器自动生成新的虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-104">You can use App-V Package Accelerators to automatically generate a new virtual application package.</span></span> <span data-ttu-id="a6c3a-105">有关软件包加速器的详细信息，请参阅[关于 App-v 程序包加速器（app-v 4.6 SP1）](about-app-v-package-accelerators--app-v-46-sp1-.md)。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-105">For more information about Package Accelerators, see [About App-V Package Accelerators (App-V 4.6 SP1)](about-app-v-package-accelerators--app-v-46-sp1-.md).</span></span>

**<span data-ttu-id="a6c3a-106">重要提示</span><span class="sxs-lookup"><span data-stu-id="a6c3a-106">Important</span></span>**  
<span data-ttu-id="a6c3a-107">免责声明：应用程序虚拟化 Sequencer 未向你提供用于创建程序包加速器的软件应用程序的许可证权利。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-107">Disclaimer: The Application Virtualization Sequencer does not give you any license rights to the software application you are using to create a Package Accelerator.</span></span> <span data-ttu-id="a6c3a-108">您必须遵守此类应用程序的所有最终用户许可条款。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-108">You must abide by all end user license terms for such application.</span></span> <span data-ttu-id="a6c3a-109">您有责任确保软件应用程序的许可条款允许您使用 Application Virtualization Sequencer 创建软件包加速器。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-109">It is your responsibility to make sure the software application’s license terms allow you to create a Package Accelerator using Application Virtualization Sequencer.</span></span>



**<span data-ttu-id="a6c3a-110">注意</span><span class="sxs-lookup"><span data-stu-id="a6c3a-110">Note</span></span>**  
<span data-ttu-id="a6c3a-111">在开始此过程之前，请将所需的软件包加速器本地复制到运行 App-v Sequencer 的计算机。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-111">Before starting this procedure, copy the required Package Accelerator locally to the computer running the App-V Sequencer.</span></span> <span data-ttu-id="a6c3a-112">你还应将程序包所需的所有安装文件复制到运行 Sequencer 的计算机上的本地目录。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-112">You should also copy all required installation files for the package to a local directory on the computer running the Sequencer.</span></span> <span data-ttu-id="a6c3a-113">这是你必须在此过程的步骤5中指定的目录。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-113">This is the directory that you have to specify in step 5 of this procedure.</span></span>



<span data-ttu-id="a6c3a-114">使用以下过程使用包加速器创建虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-114">Use the following procedure to create a virtual application package by using a Package Accelerator.</span></span>

**<span data-ttu-id="a6c3a-115">使用 App-v 包加速器创建虚拟应用程序包</span><span class="sxs-lookup"><span data-stu-id="a6c3a-115">To create a virtual application package by using an App-V Package Accelerator</span></span>**

1. <span data-ttu-id="a6c3a-116">若要启动 app-v 排序器，请在运行 app-v 排序器的计算机上，单击 "**启动**  /  **所有程序**  /  **microsoft application virtualization**  /  **microsoft application virtualization Sequencer**"。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-116">To start the App-V Sequencer, on the computer that is running the App-V Sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span>

2. <span data-ttu-id="a6c3a-117">若要启动 "**创建新程序包" 向导**，请单击 "**创建新的虚拟应用程序包**"。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-117">To start the **Create New Package Wizard**, click **Create a New Virtual Application Package**.</span></span> <span data-ttu-id="a6c3a-118">若要创建程序包，请选中 "**使用包加速器创建程序包**" 复选框，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-118">To create the package, select the **Create Package using a Package Accelerator** check box, and then click **Next**.</span></span>

3. <span data-ttu-id="a6c3a-119">在 "**选择包加速器**" 页面上，若要指定将用于创建新虚拟应用程序包的程序包加速器，请单击 "**浏览**" 以找到要使用的程序包加速器。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-119">On the **Select Package Accelerator** page, to specify the Package Accelerator that will be used to create the new virtual application package, click **Browse** to locate the Package Accelerator that you want to use.</span></span> <span data-ttu-id="a6c3a-120">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-120">Click **Next**.</span></span>

   **<span data-ttu-id="a6c3a-121">重要提示</span><span class="sxs-lookup"><span data-stu-id="a6c3a-121">Important</span></span>**  
   <span data-ttu-id="a6c3a-122">如果无法验证程序包加速器的发行者，并且不包含有效的数字签名，请在 "**安全警告**" 对话框中，在单击 "**运行**" 之前，必须确认信任程序包加速器的源。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-122">If the publisher of the Package Accelerator cannot be verified and does not contain a valid digital signature, in the **Security Warning** dialog box, you must confirm that you trust the source of the Package Accelerator before you click **Run**.</span></span>



4. <span data-ttu-id="a6c3a-123">在 "**指南**" 页上，查看 "信息" 窗格中显示的发布指南信息。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-123">On the **Guidance** page, review the publishing guidance information displayed in the information pane.</span></span> <span data-ttu-id="a6c3a-124">显示的信息是在创建软件包加速器时添加的，其中包含有关创建和发布程序包的信息。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-124">The information displayed was added when the Package Accelerator was created and contains information about creating and publishing the package.</span></span> <span data-ttu-id="a6c3a-125">若要将指南信息导出到文本（.txt）文件，请单击 "**导出**"，指定应保存该文件的位置，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-125">To export the guidance information to a text (.txt) file, click **Export** and specify the location where the file should be saved, and then click **Next**.</span></span>

5. <span data-ttu-id="a6c3a-126">在 "**选择安装文件**" 页面上，若要创建包含程序包所需的所有安装文件的本地文件夹，请单击 "**新建文件夹**"，然后指定应保存文件夹的位置。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-126">On the **Select Installation Files** page, to create a local folder that contains all required installation files for the package, click **Make New Folder** and specify where the folder should be saved.</span></span> <span data-ttu-id="a6c3a-127">还必须指定要分配给文件夹的名称。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-127">You must also specify a name to be assigned to the folder.</span></span> <span data-ttu-id="a6c3a-128">然后，您必须将所有所需的安装文件复制到您指定的位置。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-128">You must then copy all required installation files to the location that you specified.</span></span> <span data-ttu-id="a6c3a-129">如果运行排序器的计算机上已存在包含安装文件的文件夹，请单击 "**浏览**" 以选择该文件夹。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-129">If the folder that contains the installation files already exists on the computer running the Sequencer, click **Browse** to select the folder.</span></span>

   <span data-ttu-id="a6c3a-130">或者，如果已将安装文件复制到此计算机上的目录中，请单击 "**新建文件夹**"，浏览到包含安装文件的文件夹，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-130">Alternatively, if you have already copied the installation files to a directory on this computer, click **Make New Folder**, browse to the folder that contains the installation files, and then click **Next**.</span></span>

   **<span data-ttu-id="a6c3a-131">注意</span><span class="sxs-lookup"><span data-stu-id="a6c3a-131">Note</span></span>**  
   <span data-ttu-id="a6c3a-132">你可以指定以下支持的安装文件类型：</span><span class="sxs-lookup"><span data-stu-id="a6c3a-132">You can specify the following types of supported installation files:</span></span>

   -   <span data-ttu-id="a6c3a-133">Windows Installer 文件（**.msi** ）</span><span class="sxs-lookup"><span data-stu-id="a6c3a-133">Windows Installer files(**.msi**</span></span>

   -   <span data-ttu-id="a6c3a-134">.cab 文件</span><span class="sxs-lookup"><span data-stu-id="a6c3a-134">.cab files</span></span>

   -   <span data-ttu-id="a6c3a-135">文件扩展名为 .zip 的压缩文件</span><span class="sxs-lookup"><span data-stu-id="a6c3a-135">Compressed files with a .zip file name extension</span></span>

   -   <span data-ttu-id="a6c3a-136">实际应用程序文件</span><span class="sxs-lookup"><span data-stu-id="a6c3a-136">The actual application files</span></span>

   <span data-ttu-id="a6c3a-137">不支持以下文件类型： **.msp**和 <strong> .exe </strong> 文件。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-137">The following file types are not supported: **.msp** and<strong>.exe</strong> files.</span></span> <span data-ttu-id="a6c3a-138">如果指定 **.exe**文件，则必须手动解压缩安装文件。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-138">If you specify an **.exe** file you must extract the installation files manually.</span></span>



~~~
If the Package Accelerator requires an application be installed prior to applying the Package Accelerator and you have installed the application, on the **Local Installation** page, select the check box **I have installed all applications**, and then click **Next**.
~~~

6. <span data-ttu-id="a6c3a-139">在 "**程序包名称**" 页面上，指定将与程序包关联的名称。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-139">On the **Package Name** page, specify a name that will be associated with the package.</span></span> <span data-ttu-id="a6c3a-140">指定的名称在 App-v 管理控制台中标识程序包。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-140">The name specified identifies the package in the App-V Management Console.</span></span> <span data-ttu-id="a6c3a-141">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-141">Click **Next**.</span></span>

7. <span data-ttu-id="a6c3a-142">在 "**创建程序包**" 页面上，提供将与程序包相关联的注释。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-142">On the **Create Package** page, provide comments that will be associated with the package.</span></span> <span data-ttu-id="a6c3a-143">注释应包含有关正在创建的程序包的标识信息。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-143">The comments should contain identifying information about the package you are creating.</span></span> <span data-ttu-id="a6c3a-144">若要确认创建程序包的位置，请查看 "**保存位置**" 中显示的信息。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-144">To confirm the location where the package is created, review the information displayed in **Save Location**.</span></span> <span data-ttu-id="a6c3a-145">若要压缩程序包，请选择 "**压缩包**"。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-145">To compress the package, select **Compress Package**.</span></span> <span data-ttu-id="a6c3a-146">如果要跨网络传输包，或者程序包大小超过 4 GB，请选中 "**压缩包**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-146">Select the **Compress Package** check box if the package will be streamed across the network, or when the package size exceeds 4 GB.</span></span>

   <span data-ttu-id="a6c3a-147">若要创建程序包，请单击 "**创建**"。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-147">To create the package, click **Create**.</span></span> <span data-ttu-id="a6c3a-148">创建程序包后，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-148">After the package has been created, click **Next**.</span></span>

8. <span data-ttu-id="a6c3a-149">在 "**配置软件**" 页面上，若要使 Sequencer 能够配置程序包中包含的应用程序，请选择 "**配置软件**"。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-149">On the **Configure Software** page, to enable the Sequencer to configure the applications contained in the package, select **Configure Software**.</span></span> <span data-ttu-id="a6c3a-150">此步骤适用于配置在目标计算机上运行应用程序时必须完成的任何相关任务，例如配置任何关联的许可协议。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-150">This step is useful for configuring any associated tasks that must be completed to run the application on target computers, such as configuring any associated license agreements.</span></span>

   <span data-ttu-id="a6c3a-151">如果选择 "**配置软件**"，则由 Sequencer 将以下项配置为此步骤的一部分：</span><span class="sxs-lookup"><span data-stu-id="a6c3a-151">If you select **Configure Software**, the following items are configured by the Sequencer as part of this step:</span></span>

   -   <span data-ttu-id="a6c3a-152">**加载程序包**。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-152">**Load Package**.</span></span> <span data-ttu-id="a6c3a-153">Sequencer 将加载与该包关联的文件。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-153">The Sequencer loads the files associated with the package.</span></span> <span data-ttu-id="a6c3a-154">解码包可能需要几秒钟的时间才能长达一小时。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-154">It can take several seconds to up to an hour to decode the package.</span></span>

   -   <span data-ttu-id="a6c3a-155">**运行每个程序**。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-155">**Run Each Program**.</span></span> <span data-ttu-id="a6c3a-156">（可选）运行程序包中包含的程序。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-156">Optionally run the programs contained in the package.</span></span> <span data-ttu-id="a6c3a-157">此步骤有助于完成在目标计算机上部署和运行程序包之前运行应用程序所需的任何相关许可证或配置任务。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-157">This step is helpful for completing any associated license or configuration tasks that are required to run the application before you deploy and run the package on target computers.</span></span> <span data-ttu-id="a6c3a-158">若要一次运行所有程序，请至少选择一个程序，然后单击 "**全部运行**"。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-158">To run all the programs at one time, select at least one program, and then click **Run All**.</span></span> <span data-ttu-id="a6c3a-159">若要运行特定程序，请选择要运行的一个或一些程序，然后单击 "**运行所选**"。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-159">To run specific programs, select the program or programs you want to run, and then click **Run Selected**.</span></span> <span data-ttu-id="a6c3a-160">完成所需的配置任务，然后关闭应用程序。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-160">Complete the required configuration tasks, and then close the applications.</span></span> <span data-ttu-id="a6c3a-161">运行所有程序可能需要几分钟的时间。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-161">It can take several minutes for all programs to run.</span></span> <span data-ttu-id="a6c3a-162">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-162">Click **Next**.</span></span>

   -   <span data-ttu-id="a6c3a-163">**保存程序包**。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-163">**Save Package**.</span></span> <span data-ttu-id="a6c3a-164">Sequencer 将保存包。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-164">The Sequencer saves the package.</span></span>

   -   <span data-ttu-id="a6c3a-165">**主要功能块**。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-165">**Primary Feature Block**.</span></span> <span data-ttu-id="a6c3a-166">Sequencer 通过重新生成主功能块来优化流包。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-166">The Sequencer optimizes the package for streaming by rebuilding the primary feature block.</span></span>

   <span data-ttu-id="a6c3a-167">如果您不想配置应用程序，请单击 "**跳过此步骤**"，转到此过程的步骤9，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-167">If you do not want to configure the applications, click **Skip this step**, and to go to step 9 of this procedure, and then click **Next**.</span></span>

9. <span data-ttu-id="a6c3a-168">在 "**完成**" 页面上，查看 "**虚拟应用程序包报告**" 窗格中显示的信息后，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-168">On the **Completion** page, after you have reviewed the information displayed in the **Virtual Application Package Report** pane, click **Close**.</span></span>

   <span data-ttu-id="a6c3a-169">程序包现在在 Sequencer 中可用。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-169">The package is now available in the Sequencer.</span></span> <span data-ttu-id="a6c3a-170">若要编辑程序包属性，请单击 "**编辑 \ [包名称 \]**"。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-170">To edit the package properties, click **Edit \[Package Name\]**.</span></span> <span data-ttu-id="a6c3a-171">有关修改程序包的详细信息，请参阅[如何修改现有虚拟应用程序包（app-v 4.6 SP1）](how-to-modify-an-existing-virtual-application-package--app-v-46-sp1-.md)。</span><span class="sxs-lookup"><span data-stu-id="a6c3a-171">For more information about modifying a package, see [How to Modify an Existing Virtual Application Package (App-V 4.6 SP1)](how-to-modify-an-existing-virtual-application-package--app-v-46-sp1-.md).</span></span>

## <span data-ttu-id="a6c3a-172">相关主题</span><span class="sxs-lookup"><span data-stu-id="a6c3a-172">Related topics</span></span>


[<span data-ttu-id="a6c3a-173">配置 Application Virtualization Sequencer (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="a6c3a-173">Configuring the Application Virtualization Sequencer (App-V 4.6 SP1)</span></span>](configuring-the-application-virtualization-sequencer--app-v-46-sp1-.md)

[<span data-ttu-id="a6c3a-174">如何创建 App-V 包加速器 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="a6c3a-174">How to Create App-V Package Accelerators (App-V 4.6 SP1)</span></span>](how-to-create-app-v-package-accelerators--app-v-46-sp1-.md)









