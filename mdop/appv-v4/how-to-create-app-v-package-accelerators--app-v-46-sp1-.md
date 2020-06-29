---
title: 如何创建 App-V 包加速器 (App-V 4.6 SP1)
description: 如何创建 App-V 包加速器 (App-V 4.6 SP1)
author: dansimp
ms.assetid: 585e692e-cebb-48ac-93ab-b2e7eb7ae7ad
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: eb806ccf04fcd5ae7db87c5de21e85217739fcbc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801496"
---
# <span data-ttu-id="a36d1-103">如何创建 App-V 包加速器 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="a36d1-103">How to Create App-V Package Accelerators (App-V 4.6 SP1)</span></span>


<span data-ttu-id="a36d1-104">你可以使用 App-v 程序包加速器自动生成新的虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="a36d1-104">You can use App-V Package Accelerators to automatically generate a new virtual application package.</span></span> <span data-ttu-id="a36d1-105">成功创建程序包加速器后，您可以重复使用和共享程序包加速器。</span><span class="sxs-lookup"><span data-stu-id="a36d1-105">After you have successfully created a Package Accelerator, you can reuse and share the Package Accelerator.</span></span> <span data-ttu-id="a36d1-106">有关软件包加速器的详细信息，请参阅[关于 App-v 程序包加速器（app-v 4.6 SP1）](about-app-v-package-accelerators--app-v-46-sp1-.md)。</span><span class="sxs-lookup"><span data-stu-id="a36d1-106">For more information about Package Accelerators, see [About App-V Package Accelerators (App-V 4.6 SP1)](about-app-v-package-accelerators--app-v-46-sp1-.md).</span></span> <span data-ttu-id="a36d1-107">创建 App-v 包加速器是一种高级任务。</span><span class="sxs-lookup"><span data-stu-id="a36d1-107">Creating App-V Package Accelerators is an advanced task.</span></span> <span data-ttu-id="a36d1-108">程序包加速器可以包含密码和特定于用户的信息。</span><span class="sxs-lookup"><span data-stu-id="a36d1-108">Package Accelerators can contain password and user-specific information.</span></span> <span data-ttu-id="a36d1-109">因此，你必须将程序包加速器和关联的安装媒体保存在一个安全位置，并且你应对程序包加速器进行数字签名，以便在应用 V 程序包加速器应用时可以验证发布者。</span><span class="sxs-lookup"><span data-stu-id="a36d1-109">Therefore you must save Package Accelerators and the associated installation media in a secure location, and you should digitally sign the Package Accelerator after you create it so that the publisher can be verified when the App-V Package Accelerator is applied.</span></span>

<span data-ttu-id="a36d1-110">在某些情况下，若要创建程序包加速器，可能需要在运行 Sequencer 的计算机上本地安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="a36d1-110">In some situations, to create the Package Accelerator, you might have to install the application locally on the computer running the Sequencer.</span></span> <span data-ttu-id="a36d1-111">首先尝试使用安装媒体创建程序包加速器，如果有多个缺少的文件，请在运行 Sequencer 的计算机本地安装应用程序，然后创建程序包加速器。</span><span class="sxs-lookup"><span data-stu-id="a36d1-111">First try to create the Package Accelerator by using the installation media, and if there are a number of missing files that are required, install the application locally to the computer running the Sequencer, and then create the Package Accelerator.</span></span>

**<span data-ttu-id="a36d1-112">重要提示</span><span class="sxs-lookup"><span data-stu-id="a36d1-112">Important</span></span>**  
<span data-ttu-id="a36d1-113">开始执行以下过程之前，应执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="a36d1-113">Before you begin the following procedure, you should do the following:</span></span>

-   <span data-ttu-id="a36d1-114">将你必须使用的虚拟应用程序包复制到运行 Sequencer 的计算机本地创建程序包加速器。</span><span class="sxs-lookup"><span data-stu-id="a36d1-114">Copy the virtual application package that you must use to create the Package Accelerator locally to the computer running the Sequencer.</span></span>

-   <span data-ttu-id="a36d1-115">将与虚拟应用程序包相关联的所有所需安装文件复制到运行 Sequencer 的计算机。</span><span class="sxs-lookup"><span data-stu-id="a36d1-115">Copy all required installation files associated with the virtual application package to the computer running the Sequencer.</span></span>



**<span data-ttu-id="a36d1-116">重要提示</span><span class="sxs-lookup"><span data-stu-id="a36d1-116">Important</span></span>**  
<span data-ttu-id="a36d1-117">免责声明： Microsoft Application Virtualization Sequencer 不向你提供用于创建程序包加速器的软件应用程序的许可证权利。</span><span class="sxs-lookup"><span data-stu-id="a36d1-117">Disclaimer: The Microsoft Application Virtualization Sequencer does not give you any license rights to the software application you are using to create a Package Accelerator.</span></span> <span data-ttu-id="a36d1-118">您必须遵守此类应用程序的所有最终用户许可条款。</span><span class="sxs-lookup"><span data-stu-id="a36d1-118">You must abide by all end user license terms for such application.</span></span> <span data-ttu-id="a36d1-119">您有责任确保软件应用程序的许可条款允许您使用 Application Virtualization Sequencer 创建软件包加速器。</span><span class="sxs-lookup"><span data-stu-id="a36d1-119">It is your responsibility to make sure the software application’s license terms allow you to create a Package Accelerator using Application Virtualization Sequencer.</span></span>



**<span data-ttu-id="a36d1-120">创建 App-v 包加速器</span><span class="sxs-lookup"><span data-stu-id="a36d1-120">To create an App-V Package Accelerator</span></span>**

1.  <span data-ttu-id="a36d1-121">若要启动 app-v 排序器，请在运行 app-v 排序器的计算机上，单击 "**启动**  /  **所有程序**  /  **microsoft application virtualization**  /  **microsoft application virtualization Sequencer**"。</span><span class="sxs-lookup"><span data-stu-id="a36d1-121">To start the App-V Sequencer, on the computer that is running the App-V Sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="a36d1-122">若要启动 app-v**创建包加速器**向导，请在 app-v 排序器中单击 "**工具**  /  **创建包加速器**"。</span><span class="sxs-lookup"><span data-stu-id="a36d1-122">To start the App-V **Create Package Accelerator** wizard, in the App-V Sequencer, click **Tools** / **Create Package Accelerator**.</span></span>

3.  <span data-ttu-id="a36d1-123">在 "**选择程序包**" 页面上，若要指定要用于创建程序包加速器的现有虚拟应用程序包，请单击 "**浏览**"，然后找到现有虚拟应用程序包（sprj 文件）。</span><span class="sxs-lookup"><span data-stu-id="a36d1-123">On the **Select Package** page, to specify an existing virtual application package to use to create the Package Accelerator, click **Browse**, and locate the existing virtual application package (.sprj file).</span></span>

    **<span data-ttu-id="a36d1-124">提示</span><span class="sxs-lookup"><span data-stu-id="a36d1-124">Tip</span></span>**  
    <span data-ttu-id="a36d1-125">将与你计划要使用的虚拟应用程序包关联的文件复制到运行 Sequencer 的计算机。</span><span class="sxs-lookup"><span data-stu-id="a36d1-125">Copy the files associated with the virtual application package you plan to use locally to the computer running the Sequencer.</span></span>



~~~
Click **Next**.
~~~

4. <span data-ttu-id="a36d1-126">在 "**安装文件**" 页面上，若要指定包含用于创建原始虚拟应用程序包的安装文件的文件夹，请单击 "**浏览**"，然后选择包含安装文件的目录。</span><span class="sxs-lookup"><span data-stu-id="a36d1-126">On the **Installation Files** page, to specify the folder that contains the installation files that you used to create the original virtual application package, click **Browse**, and then select the directory that contains the installation files.</span></span>

   **<span data-ttu-id="a36d1-127">提示</span><span class="sxs-lookup"><span data-stu-id="a36d1-127">Tip</span></span>**  
   <span data-ttu-id="a36d1-128">将包含所需安装文件的文件夹复制到运行 Sequencer 的计算机。</span><span class="sxs-lookup"><span data-stu-id="a36d1-128">Copy the folder that contains the required installation files to the computer running the Sequencer.</span></span>



~~~
If the application is already installed on the computer running the Sequencer, to specify the installation file, select **Files installed on local system**. To use this option, the application must already be installed in the default installation location.
~~~

5. <span data-ttu-id="a36d1-129">在 "**收集信息**" 页面上，查看在此向导的 "**安装文件**" 页面上指定的位置中未找到的文件。</span><span class="sxs-lookup"><span data-stu-id="a36d1-129">On the **Gathering Information** page, review the files that were not found in the location specified on the **Installation Files** page of this wizard.</span></span> <span data-ttu-id="a36d1-130">如果显示的文件不是必需的，请选择 "**删除这些文件**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="a36d1-130">If the files displayed are not required, select **Remove these files**, and then click **Next**.</span></span> <span data-ttu-id="a36d1-131">如果需要这些文件，请单击 "**上一步**"，然后将所需的文件复制到 "**安装文件**" 页面上指定的目录中。</span><span class="sxs-lookup"><span data-stu-id="a36d1-131">If the files are required, click **Previous** and copy the required files to the directory specified on the **Installation Files** page.</span></span>

   **<span data-ttu-id="a36d1-132">注意</span><span class="sxs-lookup"><span data-stu-id="a36d1-132">Note</span></span>**  
   <span data-ttu-id="a36d1-133">必须删除 unrequired 文件，或单击 "**上一**步"，然后找到所需的文件以转到此向导的下一页。</span><span class="sxs-lookup"><span data-stu-id="a36d1-133">You must either remove the unrequired files, or click **Previous** and locate the required files to advance to the next page of this wizard.</span></span>



6. <span data-ttu-id="a36d1-134">在 "**选择文件**" 页面上，仔细查看检测到的文件，并清除应从程序包加速器中删除的任何文件。</span><span class="sxs-lookup"><span data-stu-id="a36d1-134">On the **Select Files** page, carefully review the files that were detected, and clear any file that should be removed from the Package Accelerator.</span></span> <span data-ttu-id="a36d1-135">仅选择应用程序成功运行所需的文件，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="a36d1-135">Select only files that are required for the application to run successfully, and then click **Next**.</span></span>

7. <span data-ttu-id="a36d1-136">在 "**验证应用程序**" 页面上，确认显示生成程序包所需的所有安装文件。</span><span class="sxs-lookup"><span data-stu-id="a36d1-136">On the **Verify Applications** page, confirm that all installation files that are required to build the package are displayed.</span></span> <span data-ttu-id="a36d1-137">当程序包加速器用于创建新程序包时，必须在 "**应用程序**" 窗格中显示所有安装文件才能创建程序包。</span><span class="sxs-lookup"><span data-stu-id="a36d1-137">When the Package Accelerator is used to create a new package, all installation files displayed in the **Applications** pane are required to create the package.</span></span>

   <span data-ttu-id="a36d1-138">如有必要，要添加其他安装程序文件，请单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="a36d1-138">If necessary, to add additional Installer files, click **Add**.</span></span> <span data-ttu-id="a36d1-139">若要删除不需要的安装文件，请选择安装程序文件，然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="a36d1-139">To remove unnecessary installation files, select the Installer file, and then click **Delete**.</span></span> <span data-ttu-id="a36d1-140">若要编辑与安装程序相关联的属性，请单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="a36d1-140">To edit the properties associated with an installer, click **Edit**.</span></span> <span data-ttu-id="a36d1-141">当程序包加速器用于创建新的虚拟应用程序包时，将需要在此步骤中指定的安装文件。</span><span class="sxs-lookup"><span data-stu-id="a36d1-141">The installation files specified in this step will be required when the Package Accelerator is used to create a new virtual application package.</span></span> <span data-ttu-id="a36d1-142">确认所显示的信息后，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="a36d1-142">After you have confirmed the information displayed, click **Next**.</span></span>

8. <span data-ttu-id="a36d1-143">在 "**选择指南**" 页面上，若要指定包含程序包加速器相关信息的文件，请单击 "**浏览**"。</span><span class="sxs-lookup"><span data-stu-id="a36d1-143">On the **Select Guidance** page, to specify a file that contains information about how the Package Accelerator, click **Browse**.</span></span> <span data-ttu-id="a36d1-144">例如，此文件可以包含有关运行 Sequencer 的计算机的配置、目标计算机的应用程序必备信息以及常规注释的信息。</span><span class="sxs-lookup"><span data-stu-id="a36d1-144">For example, this file can contain information about how the computer running the Sequencer should be configured, application prerequisite information for target computers, and general notes.</span></span> <span data-ttu-id="a36d1-145">你应提供要成功应用的程序包加速器所需的所有信息。</span><span class="sxs-lookup"><span data-stu-id="a36d1-145">You should provide all required information for the Package Accelerator to be successfully applied.</span></span> <span data-ttu-id="a36d1-146">所选文件必须是 rtf （.rtf）或文本文件（.txt）格式。</span><span class="sxs-lookup"><span data-stu-id="a36d1-146">The file you select must be in rich text (.rtf) or text file (.txt) format.</span></span> <span data-ttu-id="a36d1-147">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a36d1-147">Click **Next**.</span></span>

9. <span data-ttu-id="a36d1-148">在 "**创建包加速器**" 页面上，若要指定程序包加速器的保存位置，请单击 "**浏览**" 并选择目录。</span><span class="sxs-lookup"><span data-stu-id="a36d1-148">On the **Create Package Accelerator** page, to specify where to save the Package Accelerator, click **Browse** and select the directory.</span></span>

10. <span data-ttu-id="a36d1-149">在**完成**页上，若要关闭 "**创建程序包加速器**" 向导，请单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="a36d1-149">On the **Completion** page, to close the **Create Package Accelerator** wizard, click **Close**.</span></span>

   **<span data-ttu-id="a36d1-150">重要提示</span><span class="sxs-lookup"><span data-stu-id="a36d1-150">Important</span></span>**  
   <span data-ttu-id="a36d1-151">为了帮助确保程序包加速器尽可能安全，并且可以在应用包加速器时验证发布者，你应该始终对程序包加速器进行数字签名。</span><span class="sxs-lookup"><span data-stu-id="a36d1-151">To help ensure that the Package Accelerator is as secure as possible, and so that the publisher can be verified when the Package Accelerator is applied, you should always digitally sign the Package Accelerator.</span></span>



## <span data-ttu-id="a36d1-152">相关主题</span><span class="sxs-lookup"><span data-stu-id="a36d1-152">Related topics</span></span>


<span data-ttu-id="a36d1-153">配置应用程序虚拟化排序器（App-v 4.6 SP1）[如何应用程序包加速器以创建虚拟应用程序包（app-v 4.6 SP1）](how-to-apply-a-package-accelerator-to-create-a-virtual-application-package---app-v-46-sp1-.md)</span><span class="sxs-lookup"><span data-stu-id="a36d1-153">Configuring the Application Virtualization Sequencer (App-V 4.6 SP1) [How to Apply a Package Accelerator to Create a Virtual Application Package (App-V 4.6 SP1)](how-to-apply-a-package-accelerator-to-create-a-virtual-application-package---app-v-46-sp1-.md)</span></span>









