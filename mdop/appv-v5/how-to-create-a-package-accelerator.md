---
title: 如何创建包加速器
description: 如何创建包加速器
author: dansimp
ms.assetid: dfe305e5-7cf8-498f-9581-4805ffc722bd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0710bff5e5ea420119ac3c395c2e8917f7c582dd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798505"
---
# <span data-ttu-id="dac00-103">如何创建包加速器</span><span class="sxs-lookup"><span data-stu-id="dac00-103">How to Create a Package Accelerator</span></span>


<span data-ttu-id="dac00-104">App-v 5.0 程序包加速器会自动生成新的虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="dac00-104">App-V 5.0 package accelerators automatically generate new virtual application packages.</span></span>

**<span data-ttu-id="dac00-105">注意</span><span class="sxs-lookup"><span data-stu-id="dac00-105">Note</span></span>**  
<span data-ttu-id="dac00-106">你可以使用 PowerShell 创建程序包加速器。</span><span class="sxs-lookup"><span data-stu-id="dac00-106">You can use PowerShell to create a package accelerator.</span></span> <span data-ttu-id="dac00-107">有关详细信息，请参阅[如何使用 PowerShell 创建程序包加速器](how-to-create-a-package-accelerator-by-using-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="dac00-107">For more information see [How to Create a Package Accelerator by Using PowerShell](how-to-create-a-package-accelerator-by-using-powershell.md).</span></span>



<span data-ttu-id="dac00-108">使用以下过程创建包加速器。</span><span class="sxs-lookup"><span data-stu-id="dac00-108">Use the following procedure to create a package accelerator.</span></span>

**<span data-ttu-id="dac00-109">重要提示</span><span class="sxs-lookup"><span data-stu-id="dac00-109">Important</span></span>**  
<span data-ttu-id="dac00-110">程序包加速器可以包含密码和特定于用户的信息。</span><span class="sxs-lookup"><span data-stu-id="dac00-110">Package Accelerators can contain password and user-specific information.</span></span> <span data-ttu-id="dac00-111">因此，你必须将程序包加速器和关联的安装媒体保存在一个安全的位置，并且你应对程序包加速器进行数字签名，以便在应用 V 5.0 程序包加速器应用时可以验证发布者。</span><span class="sxs-lookup"><span data-stu-id="dac00-111">Therefore you must save Package Accelerators and the associated installation media in a secure location, and you should digitally sign the Package Accelerator after you create it so that the publisher can be verified when the App-V 5.0 Package Accelerator is applied.</span></span>



**<span data-ttu-id="dac00-112">重要提示</span><span class="sxs-lookup"><span data-stu-id="dac00-112">Important</span></span>**  
<span data-ttu-id="dac00-113">开始执行以下过程之前，应执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="dac00-113">Before you begin the following procedure, you should perform the following:</span></span>

-   <span data-ttu-id="dac00-114">将用于在本地创建程序包加速器的虚拟应用程序包复制到运行 sequencer 的计算机。</span><span class="sxs-lookup"><span data-stu-id="dac00-114">Copy the virtual application package that you will use to create the package accelerator locally to the computer running the sequencer.</span></span>

-   <span data-ttu-id="dac00-115">将与虚拟应用程序包相关联的所有所需安装文件复制到运行 sequencer 的计算机。</span><span class="sxs-lookup"><span data-stu-id="dac00-115">Copy all required installation files associated with the virtual application package to the computer running the sequencer.</span></span>



**<span data-ttu-id="dac00-116">创建包加速器</span><span class="sxs-lookup"><span data-stu-id="dac00-116">To create a package accelerator</span></span>**

1.  **<span data-ttu-id="dac00-117">重要提示</span><span class="sxs-lookup"><span data-stu-id="dac00-117">Important</span></span>**  
    <span data-ttu-id="dac00-118">App-v 5.0 Sequencer 不会向你用于创建包加速器的软件应用程序授予任何许可证权限。</span><span class="sxs-lookup"><span data-stu-id="dac00-118">The App-V 5.0 Sequencer does not grant any license rights to the software application you are using to create the Package Accelerator.</span></span> <span data-ttu-id="dac00-119">你必须遵守你正在使用的应用程序的所有最终用户许可条款。</span><span class="sxs-lookup"><span data-stu-id="dac00-119">You must abide by all end user license terms for the application you are using.</span></span> <span data-ttu-id="dac00-120">您有责任确保软件应用程序的许可条款允许您使用 app-v 5.0 Sequencer 创建软件包加速器。</span><span class="sxs-lookup"><span data-stu-id="dac00-120">It is your responsibility to make sure the software application’s license terms allow you to create a Package Accelerator using App-V 5.0 Sequencer.</span></span>



~~~
To start the App-V 5.0 sequencer, on the computer that is running the sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.
~~~

2. <span data-ttu-id="dac00-121">若要启动 app-v 5.0**创建程序包加速器**向导，请在 app-v 5.0 sequencer 控制台中单击 "**工具**  /  **创建加速器**"。</span><span class="sxs-lookup"><span data-stu-id="dac00-121">To start the App-V 5.0 **Create Package Accelerator** wizard, in the App-V 5.0 sequencer console, click **Tools** / **Create Accelerator**.</span></span>

3. <span data-ttu-id="dac00-122">在 "**选择程序包**" 页面上，若要指定要用于创建程序包加速器的现有虚拟应用程序包，请单击 "**浏览**"，然后找到现有虚拟应用程序包（appv 文件）。</span><span class="sxs-lookup"><span data-stu-id="dac00-122">On the **Select Package** page, to specify an existing virtual application package to use to create the Package Accelerator, click **Browse**, and locate the existing virtual application package (.appv file).</span></span>

   **<span data-ttu-id="dac00-123">提示</span><span class="sxs-lookup"><span data-stu-id="dac00-123">Tip</span></span>**  
   <span data-ttu-id="dac00-124">将与你计划要使用的虚拟应用程序包关联的文件复制到运行 Sequencer 的计算机。</span><span class="sxs-lookup"><span data-stu-id="dac00-124">Copy the files associated with the virtual application package you plan to use locally to the computer running the Sequencer.</span></span>



~~~
Click **Next**.
~~~

4. <span data-ttu-id="dac00-125">在 "**安装文件**" 页面上，若要指定包含用于创建原始虚拟应用程序包的安装文件的文件夹，请单击 "**浏览**"，然后选择包含安装文件的目录。</span><span class="sxs-lookup"><span data-stu-id="dac00-125">On the **Installation Files** page, to specify the folder that contains the installation files that you used to create the original virtual application package, click **Browse**, and then select the directory that contains the installation files.</span></span>

   **<span data-ttu-id="dac00-126">提示</span><span class="sxs-lookup"><span data-stu-id="dac00-126">Tip</span></span>**  
   <span data-ttu-id="dac00-127">将包含所需安装文件的文件夹复制到运行 Sequencer 的计算机。</span><span class="sxs-lookup"><span data-stu-id="dac00-127">Copy the folder that contains the required installation files to the computer running the Sequencer.</span></span>



5. <span data-ttu-id="dac00-128">如果应用程序已安装在运行 sequencer 的计算机上，若要指定安装文件，请选择 "**本地系统上安装的文件**"。</span><span class="sxs-lookup"><span data-stu-id="dac00-128">If the application is already installed on the computer running the sequencer, to specify the installation file, select **Files installed on local system**.</span></span> <span data-ttu-id="dac00-129">若要使用此选项，应用程序必须已安装在默认安装位置。</span><span class="sxs-lookup"><span data-stu-id="dac00-129">To use this option, the application must already be installed in the default installation location.</span></span>

6. <span data-ttu-id="dac00-130">在 "**收集信息**" 页面上，查看在此向导的 "**安装文件**" 页面上指定的位置中未找到的文件。</span><span class="sxs-lookup"><span data-stu-id="dac00-130">On the **Gathering Information** page, review the files that were not found in the location specified on the **Installation Files** page of this wizard.</span></span> <span data-ttu-id="dac00-131">如果显示的文件不是必需的，请选择 "**删除这些文件**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="dac00-131">If the files displayed are not required, select **Remove these files**, and then click **Next**.</span></span> <span data-ttu-id="dac00-132">如果需要这些文件，请单击 "**上一步**"，然后将所需的文件复制到 "**安装文件**" 页面上指定的目录中。</span><span class="sxs-lookup"><span data-stu-id="dac00-132">If the files are required, click **Previous** and copy the required files to the directory specified on the **Installation Files** page.</span></span>

   **<span data-ttu-id="dac00-133">注意</span><span class="sxs-lookup"><span data-stu-id="dac00-133">Note</span></span>**  
   <span data-ttu-id="dac00-134">必须删除 unrequired 文件，或单击 "**上一**步"，然后找到所需的文件以转到此向导的下一页。</span><span class="sxs-lookup"><span data-stu-id="dac00-134">You must either remove the unrequired files, or click **Previous** and locate the required files to advance to the next page of this wizard.</span></span>



7. <span data-ttu-id="dac00-135">在 "**选择文件**" 页面上，仔细查看检测到的文件，并清除应从程序包加速器中删除的任何文件。</span><span class="sxs-lookup"><span data-stu-id="dac00-135">On the **Select Files** page, carefully review the files that were detected, and clear any file that should be removed from the package accelerator.</span></span> <span data-ttu-id="dac00-136">仅选择应用程序成功运行所需的文件，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="dac00-136">Select only files that are required for the application to run successfully, and then click **Next**.</span></span>

8. <span data-ttu-id="dac00-137">在 "**验证应用程序**" 页面上，确认显示生成程序包所需的所有安装文件。</span><span class="sxs-lookup"><span data-stu-id="dac00-137">On the **Verify Applications** page, confirm that all installation files that are required to build the package are displayed.</span></span> <span data-ttu-id="dac00-138">当程序包加速器用于创建新程序包时，必须在 "**应用程序**" 窗格中显示所有安装文件才能创建程序包。</span><span class="sxs-lookup"><span data-stu-id="dac00-138">When the Package Accelerator is used to create a new package, all installation files displayed in the **Applications** pane are required to create the package.</span></span>

   <span data-ttu-id="dac00-139">如有必要，要添加其他安装程序文件，请单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="dac00-139">If necessary, to add additional Installer files, click **Add**.</span></span> <span data-ttu-id="dac00-140">若要删除不需要的安装文件，请选择安装程序文件，然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="dac00-140">To remove unnecessary installation files, select the Installer file, and then click **Delete**.</span></span> <span data-ttu-id="dac00-141">若要编辑与安装程序相关联的属性，请单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="dac00-141">To edit the properties associated with an installer, click **Edit**.</span></span> <span data-ttu-id="dac00-142">当程序包加速器用于创建新的虚拟应用程序包时，将需要在此步骤中指定的安装文件。</span><span class="sxs-lookup"><span data-stu-id="dac00-142">The installation files specified in this step will be required when the Package Accelerator is used to create a new virtual application package.</span></span> <span data-ttu-id="dac00-143">确认所显示的信息后，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="dac00-143">After you have confirmed the information displayed, click **Next**.</span></span>

9. <span data-ttu-id="dac00-144">在 "**选择指南**" 页面上，若要指定包含程序包加速器相关信息的文件，请单击 "**浏览**"。</span><span class="sxs-lookup"><span data-stu-id="dac00-144">On the **Select Guidance** page, to specify a file that contains information about how the Package Accelerator, click **Browse**.</span></span> <span data-ttu-id="dac00-145">例如，此文件可以包含有关运行 Sequencer 的计算机的配置、目标计算机的应用程序必备信息以及常规注释的信息。</span><span class="sxs-lookup"><span data-stu-id="dac00-145">For example, this file can contain information about how the computer running the Sequencer should be configured, application prerequisite information for target computers, and general notes.</span></span> <span data-ttu-id="dac00-146">你应提供要成功应用的程序包加速器所需的所有信息。</span><span class="sxs-lookup"><span data-stu-id="dac00-146">You should provide all required information for the Package Accelerator to be successfully applied.</span></span> <span data-ttu-id="dac00-147">所选文件必须是 rtf （.rtf）或文本文件（.txt）格式。</span><span class="sxs-lookup"><span data-stu-id="dac00-147">The file you select must be in rich text (.rtf) or text file (.txt) format.</span></span> <span data-ttu-id="dac00-148">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dac00-148">Click **Next**.</span></span>

10. <span data-ttu-id="dac00-149">在 "**创建包加速器**" 页面上，若要指定程序包加速器的保存位置，请单击 "**浏览**" 并选择目录。</span><span class="sxs-lookup"><span data-stu-id="dac00-149">On the **Create Package Accelerator** page, to specify where to save the Package Accelerator, click **Browse** and select the directory.</span></span>

11. <span data-ttu-id="dac00-150">在**完成**页上，若要关闭 "**创建程序包加速器**" 向导，请单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="dac00-150">On the **Completion** page, to close the **Create Package Accelerator** wizard, click **Close**.</span></span>

   **<span data-ttu-id="dac00-151">重要提示</span><span class="sxs-lookup"><span data-stu-id="dac00-151">Important</span></span>**  
   <span data-ttu-id="dac00-152">为了帮助确保程序包加速器尽可能安全，并且可以在应用包加速器时验证发布者，你应该始终对程序包加速器进行数字签名。</span><span class="sxs-lookup"><span data-stu-id="dac00-152">To help ensure that the package accelerator is as secure as possible, and so that the publisher can be verified when the package accelerator is applied, you should always digitally sign the package accelerator.</span></span>



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## <span data-ttu-id="dac00-153">相关主题</span><span class="sxs-lookup"><span data-stu-id="dac00-153">Related topics</span></span>


[<span data-ttu-id="dac00-154">App-V 5.0 的操作</span><span class="sxs-lookup"><span data-stu-id="dac00-154">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

[<span data-ttu-id="dac00-155">如何使用 App-V 包加速器创建虚拟应用程序包</span><span class="sxs-lookup"><span data-stu-id="dac00-155">How to Create a Virtual Application Package Using an App-V Package Accelerator</span></span>](how-to-create-a-virtual-application-package-using-an-app-v-package-accelerator.md)









