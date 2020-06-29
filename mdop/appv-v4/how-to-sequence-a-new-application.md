---
title: 如何对新应用程序进行排序
description: 如何对新应用程序进行排序
author: dansimp
ms.assetid: e01e98cd-2378-478f-9739-f72c465bf79a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: aab769256116e2635edbc4bcf55d212e3a2152f8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801108"
---
# <span data-ttu-id="454e2-103">如何对新应用程序进行排序</span><span class="sxs-lookup"><span data-stu-id="454e2-103">How to Sequence a New Application</span></span>


<span data-ttu-id="454e2-104">应用程序虚拟化（app-v） Sequencer 创建可以在虚拟环境中运行的应用程序。</span><span class="sxs-lookup"><span data-stu-id="454e2-104">The Application Virtualization (App-V) Sequencer creates applications that can be run in a virtual environment.</span></span> <span data-ttu-id="454e2-105">App-v 排序器监视应用程序的安装和设置过程，并记录应用程序在虚拟环境中运行所需的信息。</span><span class="sxs-lookup"><span data-stu-id="454e2-105">The App-V Sequencer monitors the installation and setup process for an application, and it records the information necessary for the application to run in a virtual environment.</span></span> <span data-ttu-id="454e2-106">你还可以使用 App-v 排序器配置哪些文件和配置适用于所有用户以及用户可以自定义的文件和配置。</span><span class="sxs-lookup"><span data-stu-id="454e2-106">You can also use the App-V Sequencer to configure which files and configurations are applicable to all users and which files and configurations users can customize.</span></span> <span data-ttu-id="454e2-107">对应用程序进行排序时，应将程序包保存到要对其进行排序的计算机的本地驱动器。</span><span class="sxs-lookup"><span data-stu-id="454e2-107">When you sequence an application, you should save the package to a drive that is local to the computer you are sequencing on.</span></span>

<span data-ttu-id="454e2-108">序列化的应用程序不会与操作系统交互，因为每个应用程序都在虚拟环境中运行，并且独立于可能在目标计算机上安装或运行的其他应用程序。</span><span class="sxs-lookup"><span data-stu-id="454e2-108">A sequenced application does not interact with the operating system because each application runs in a virtual environment and is isolated from other applications that might be installed or running on the target computer.</span></span> <span data-ttu-id="454e2-109">这种隔离显著减少了应用程序冲突，并减少了所需的应用程序预部署测试量。</span><span class="sxs-lookup"><span data-stu-id="454e2-109">This isolation dramatically reduces application conflicts and decreases the required amount of application pre-deployment testing.</span></span>

<span data-ttu-id="454e2-110">成功对应用程序进行排序后，即可在 app-v Sequencer 控制台中使用它。</span><span class="sxs-lookup"><span data-stu-id="454e2-110">After you successfully sequence the application, it is available in the App-V Sequencer Console.</span></span> <span data-ttu-id="454e2-111">在安全模式下运行 app-v sequencer 不受支持。</span><span class="sxs-lookup"><span data-stu-id="454e2-111">Running the App-V sequencer in Safe Mode is not supported.</span></span>

**<span data-ttu-id="454e2-112">对新应用程序进行序列化</span><span class="sxs-lookup"><span data-stu-id="454e2-112">To sequence a new application</span></span>**

1.  <span data-ttu-id="454e2-113">必须创建应用程序虚拟化驱动器以对新的虚拟应用程序进行序列化。</span><span class="sxs-lookup"><span data-stu-id="454e2-113">You must create the Application Virtualization drive to sequence a new virtual application.</span></span> <span data-ttu-id="454e2-114">若要创建应用程序虚拟化驱动器，请将 Q:\\ 驱动器映射到可用于在对应用程序进行序列化时保存文件的位置。</span><span class="sxs-lookup"><span data-stu-id="454e2-114">To create the Application Virtualization drive, map the Q:\\ drive to a location that can be used to save files while you are sequencing an application.</span></span> <span data-ttu-id="454e2-115">然后，你必须为计划在 Q:\\ 驱动器上序列的每个应用程序创建单独的目录。</span><span class="sxs-lookup"><span data-stu-id="454e2-115">You must then create individual directories for each application you plan to sequence on the Q:\\ drive.</span></span> <span data-ttu-id="454e2-116">在对应用程序进行排序之前，可以创建虚拟应用程序目标文件夹，也可以在此过程的步骤5中创建虚拟应用程序目标文件夹。</span><span class="sxs-lookup"><span data-stu-id="454e2-116">You can create the virtual application target folders before you sequence an application, or you can create it in step 5 of this procedure.</span></span>

2.  <span data-ttu-id="454e2-117">若要启动 app-v sequencer 控制台，请在运行 app-v 排序器的计算机上，选择 "**开始**  /  **程序**  /  **microsoft application virtualization**  /  **microsoft application virtualization Sequencer**"。</span><span class="sxs-lookup"><span data-stu-id="454e2-117">To start the App-V Sequencer Console, on the computer that is running the App-V Sequencer, select **Start** / **Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span> <span data-ttu-id="454e2-118">若要启动**顺序向导**，请选择 "**文件**  /  **新包**"。</span><span class="sxs-lookup"><span data-stu-id="454e2-118">To start the **Sequencing Wizard**, select **File** / **New Package**.</span></span>

3.  <span data-ttu-id="454e2-119">在 "**程序包信息**" 页面上，指定将分配给虚拟应用程序的**程序包名称**。</span><span class="sxs-lookup"><span data-stu-id="454e2-119">On the **Package Information** page, specify the **Package Name** that will be assigned to the virtual application.</span></span> <span data-ttu-id="454e2-120">要生成关联的 Windows Installer 文件，需要程序包名称。</span><span class="sxs-lookup"><span data-stu-id="454e2-120">The package name is required for generating the associated Windows Installer file.</span></span> <span data-ttu-id="454e2-121">你还应添加一个可选注释，该注释将分配给程序包并提供有关虚拟应用程序的详细信息。</span><span class="sxs-lookup"><span data-stu-id="454e2-121">You should also add an optional comment that will be assigned to the package and that provides detailed information about the virtual application.</span></span> <span data-ttu-id="454e2-122">若要显示 "**高级选项**" 页面，请选择 "**显示高级监视选项**"。</span><span class="sxs-lookup"><span data-stu-id="454e2-122">To display the **Advanced Options** page, select **Show Advanced Monitoring Options**.</span></span> <span data-ttu-id="454e2-123">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="454e2-123">Click **Next**.</span></span>

    **<span data-ttu-id="454e2-124">注意</span><span class="sxs-lookup"><span data-stu-id="454e2-124">Note</span></span>**  
    <span data-ttu-id="454e2-125">若要显示 "**高级选项**" 页面，必须选择 "**显示高级监视选项**"。</span><span class="sxs-lookup"><span data-stu-id="454e2-125">To display the **Advanced Options** page, you must select **Show Advanced Monitoring Options**.</span></span> <span data-ttu-id="454e2-126">如果不需要 "**高级选项**" 页面，请跳到步骤4。</span><span class="sxs-lookup"><span data-stu-id="454e2-126">If you do not require the **Advanced Options** page, skip to step 4.</span></span>



4.  <span data-ttu-id="454e2-127">在 "**高级选项**" 页面上，若要指定虚拟应用程序的**块大小**，请选择所需的大小。</span><span class="sxs-lookup"><span data-stu-id="454e2-127">On the **Advanced Options** page, to specify the **Block Size** for the virtual application, select the size you want.</span></span> <span data-ttu-id="454e2-128">块大小确定在通过网络将程序包流出到目标计算机时将如何划分该**sft**文件。</span><span class="sxs-lookup"><span data-stu-id="454e2-128">The block size determines how the **.sft** file will be divided for streaming the package across the network to target computers.</span></span> <span data-ttu-id="454e2-129">允许 Microsoft 更新按顺序更新应用程序;选择 "**允许 Microsoft 更新在监视期间运行**"。</span><span class="sxs-lookup"><span data-stu-id="454e2-129">To allow Microsoft Update to update the application as it is being sequenced; select **Allow Microsoft Update to run during monitoring**.</span></span> <span data-ttu-id="454e2-130">如果选择此选项，将允许在监视阶段中安装 Microsoft 更新，你需要接受相关更新才能安装这些更新。</span><span class="sxs-lookup"><span data-stu-id="454e2-130">If you select this option, Microsoft Updates are allowed to be installed during the monitoring phase and you will need to accept the associated updates for them to be installed.</span></span> <span data-ttu-id="454e2-131">若要重新映射受支持的动态链接库（.dll）文件，以便它们使用 RAM 的连续空间，请选择 "**变基 dll**"。</span><span class="sxs-lookup"><span data-stu-id="454e2-131">To remap the supported dynamic link library (.dll) files so that they use a contiguous space of RAM, select **Rebase DLLs**.</span></span> <span data-ttu-id="454e2-132">选择此选项可以保留内存并帮助提高性能。</span><span class="sxs-lookup"><span data-stu-id="454e2-132">Selecting this option can conserve memory and help improve performance.</span></span> <span data-ttu-id="454e2-133">许多应用程序不支持此选项，但它在内存有限的环境中（例如在终端服务器方案中）很有用。</span><span class="sxs-lookup"><span data-stu-id="454e2-133">Many applications do not support this option, but it is useful in environments with limited RAM such as in Terminal Server scenarios.</span></span> <span data-ttu-id="454e2-134">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="454e2-134">Click **Next**.</span></span>

5.  <span data-ttu-id="454e2-135">在 "**监视器安装**" 页面上，若要监视应用程序的安装，请单击 "**开始监视**"。</span><span class="sxs-lookup"><span data-stu-id="454e2-135">On the **Monitor Installation** page, to monitor the installation of an application, click **Begin Monitoring**.</span></span> <span data-ttu-id="454e2-136">单击 "**开始监视**" 后，在 Q:\\ 驱动器上指定将安装应用程序的目录。</span><span class="sxs-lookup"><span data-stu-id="454e2-136">After you click **Begin Monitoring**, specify the directory on the Q:\\ drive where the application will be installed.</span></span> <span data-ttu-id="454e2-137">若要将应用程序安装到尚未创建的文件夹，请单击 "**创建新文件夹**"。</span><span class="sxs-lookup"><span data-stu-id="454e2-137">To install the application to a folder that has not been created, click **Make New Folder**.</span></span> <span data-ttu-id="454e2-138">你必须将序列化的每个应用程序安装到单独的目录中。</span><span class="sxs-lookup"><span data-stu-id="454e2-138">You must install each application that you sequence into a separate directory.</span></span>

    **<span data-ttu-id="454e2-139">重要提示</span><span class="sxs-lookup"><span data-stu-id="454e2-139">Important</span></span>**  
    <span data-ttu-id="454e2-140">您指定的文件夹名称长度不得超过8个字符。</span><span class="sxs-lookup"><span data-stu-id="454e2-140">The folder name you specify must not be longer than 8 characters.</span></span>



~~~
Wait for the virtual environment to load, and then install the application so that the App-V Sequencer can monitor the process. When you have completed the installation, click **Stop Monitoring** and then click **Next**.
~~~

6. <span data-ttu-id="454e2-141">在 "**要映射到虚拟文件系统（vfs）的其他文件**" 页面上，若要指定要添加到虚拟文件系统（vfs）的其他文件，请单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="454e2-141">On the **Additional Files to Map to Virtual File System (VFS)** page, to specify additional files to be added to the Virtual File System (VFS), click **Add**.</span></span> <span data-ttu-id="454e2-142">通过浏览找到要添加的文件，然后单击 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="454e2-142">Browse to the file you want to add, and click **Open**.</span></span> <span data-ttu-id="454e2-143">若要清除已添加的现有文件，请单击 "**重置**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="454e2-143">To clear existing files that have been added, click **Reset** and then click **Next**.</span></span>

7. <span data-ttu-id="454e2-144">在 "**配置应用程序**" 页面上，配置将与虚拟应用程序关联的快捷方式和文件类型关联。</span><span class="sxs-lookup"><span data-stu-id="454e2-144">On the **Configure Applications** page, configure the shortcuts and file type associations that will be associated with the virtual application.</span></span> <span data-ttu-id="454e2-145">选择要更新的元素，然后单击 "**编辑位置**"。</span><span class="sxs-lookup"><span data-stu-id="454e2-145">Select the element you want to update, and then click **Edit Locations**.</span></span> <span data-ttu-id="454e2-146">在 "**快捷方式位置**" 对话框中指定配置。</span><span class="sxs-lookup"><span data-stu-id="454e2-146">Specify the configurations in the **Shortcut Locations** dialog box.</span></span> <span data-ttu-id="454e2-147">单击 **"确定"** ，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="454e2-147">Click **OK** and then click **Next**.</span></span>

8. <span data-ttu-id="454e2-148">在 "**启动应用程序**" 页面上，若要启动应用程序以确保程序包针对流进行优化，请选择程序包，然后单击 "**启动**"。</span><span class="sxs-lookup"><span data-stu-id="454e2-148">On the **Launch Applications** page, to start the application to ensure that the package is optimized for streaming, select the package and click **Launch**.</span></span> <span data-ttu-id="454e2-149">此步骤可用于配置应用程序最初在目标计算机上运行的方式，以及在将程序包提供给客户之前接受任何关联的许可协议。</span><span class="sxs-lookup"><span data-stu-id="454e2-149">This step is useful for configuring how the application initially runs on target computers and for accepting any associated license agreements before the package is made available to clients.</span></span> <span data-ttu-id="454e2-150">如果有多个应用程序与此程序包关联，则可以选择 "**全部启动**" 以打开所有应用程序。</span><span class="sxs-lookup"><span data-stu-id="454e2-150">If there are multiple applications associated with this package, you can select **Launch All** to open all of the applications.</span></span> <span data-ttu-id="454e2-151">若要对程序包进行排序，请单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="454e2-151">To sequence the package, click **Next**.</span></span>

9. <span data-ttu-id="454e2-152">在 "**序列包**" 页面上，若要关闭向导，请单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="454e2-152">On the **Sequence Package** page, to close the wizard, click **Finish**.</span></span>

10. <span data-ttu-id="454e2-153">成功创建程序包后，若要保存程序包，请在 app-v Sequencer 控制台中选择 "**文件**  /  **保存**"，然后指定将保存程序包的名称和位置。</span><span class="sxs-lookup"><span data-stu-id="454e2-153">After you have successfully created the package, to save the package, in the App-V Sequencer Console, select **File** / **Save** and specify the name and the location where the package will be saved.</span></span>

## <span data-ttu-id="454e2-154">相关主题</span><span class="sxs-lookup"><span data-stu-id="454e2-154">Related topics</span></span>


[<span data-ttu-id="454e2-155">Application Virtualization Sequencer 的任务</span><span class="sxs-lookup"><span data-stu-id="454e2-155">Tasks for the Application Virtualization Sequencer</span></span>](tasks-for-the-application-virtualization-sequencer.md)









