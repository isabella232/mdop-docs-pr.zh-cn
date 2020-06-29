---
title: 如何对新应用程序进行排序 (App-V 4.6)
description: 如何对新应用程序进行排序 (App-V 4.6)
author: dansimp
ms.assetid: f2c398c6-9200-4be3-b502-e00386fcd150
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9a36021adf45f0f4c80ab08bcabbf9f18bf6e66b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801120"
---
# <span data-ttu-id="322ef-103">如何对新应用程序进行排序 (App-V 4.6)</span><span class="sxs-lookup"><span data-stu-id="322ef-103">How to Sequence a New Application (App-V 4.6)</span></span>


<span data-ttu-id="322ef-104">通过使用应用程序虚拟化（App-v） Sequencer，使用以下过程创建新的虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="322ef-104">Use the following procedure to create a new virtual application by using the Application Virtualization (App-V) Sequencer.</span></span> <span data-ttu-id="322ef-105">你还可以使用 App-v 排序器配置哪些文件和配置适用于所有用户以及用户可以自定义的文件和配置。</span><span class="sxs-lookup"><span data-stu-id="322ef-105">You can also use the App-V Sequencer to configure which files and configurations are applicable to all users and which files and configurations users can customize.</span></span> <span data-ttu-id="322ef-106">成功对应用程序进行排序后，即可在 app-v 排序器中使用它。</span><span class="sxs-lookup"><span data-stu-id="322ef-106">After you successfully sequence the application, it is available in the App-V Sequencer.</span></span>

**<span data-ttu-id="322ef-107">重要提示</span><span class="sxs-lookup"><span data-stu-id="322ef-107">Important</span></span>**  
<span data-ttu-id="322ef-108">在排序期间，如果运行 sequencer 的计算机运行的是 windows Vista 或 windows 7，并且在虚拟环境外启动了重启（例如，通过单击 "**开始**  /  **关机**"），则在系统提示关闭阻止 Windows 关闭的程序时，必须单击 "**取消**"。</span><span class="sxs-lookup"><span data-stu-id="322ef-108">During sequencing, if the computer running the sequencer is running Windows Vista or Windows 7, and a restart is initiated outside of the virtual environment, for example, by clicking **Start** / **Shut Down**, you must click **Cancel** when prompted to close the program that is preventing Windows from shutting down.</span></span> <span data-ttu-id="322ef-109">如果单击 "**强制关闭**"，程序包创建将失败，计算机将重新启动。</span><span class="sxs-lookup"><span data-stu-id="322ef-109">If you click **Force shut down**, the package creation will fail, and the computer will restart.</span></span> <span data-ttu-id="322ef-110">单击 "**取消**" 时，sequencer 会在应用程序顺序期间成功记录重启。</span><span class="sxs-lookup"><span data-stu-id="322ef-110">When you click **Cancel**, the sequencer successfully records the restart while the application is being sequenced.</span></span>



**<span data-ttu-id="322ef-111">对新应用程序进行序列化</span><span class="sxs-lookup"><span data-stu-id="322ef-111">To sequence a new application</span></span>**

1.  <span data-ttu-id="322ef-112">若要创建 App-v 驱动器，请将 drive Q 配置为在序列化应用程序时可用于保存文件的位置。</span><span class="sxs-lookup"><span data-stu-id="322ef-112">To create the App-V drive, configure drive Q as the location that can be used to save files while you are sequencing an application.</span></span> <span data-ttu-id="322ef-113">然后，你必须为计划在 drive Q 上排序的每个应用程序创建单独的目录。在对应用程序进行排序之前，可以创建虚拟应用程序目标文件夹，也可以在此过程的步骤5中创建它们。</span><span class="sxs-lookup"><span data-stu-id="322ef-113">You must then create individual directories for each application that you plan to sequence on drive Q. You can create the virtual application targeted folders before you sequence an application, or you can create them in step 5 of this procedure.</span></span>

    **<span data-ttu-id="322ef-114">注意</span><span class="sxs-lookup"><span data-stu-id="322ef-114">Note</span></span>**  
    <span data-ttu-id="322ef-115">你指定的 App-v 驱动器必须可在目标计算机上访问。</span><span class="sxs-lookup"><span data-stu-id="322ef-115">The App-V drive you specify must be accessible on targeted computers.</span></span> <span data-ttu-id="322ef-116">如果驱动器 Q 不可访问，则可以选择不同的驱动器号。</span><span class="sxs-lookup"><span data-stu-id="322ef-116">If drive Q is not accessible, you can choose a different drive letter.</span></span>



2.  <span data-ttu-id="322ef-117">若要启动 app-v sequencer 控制台，请在运行 app-v 排序器的计算机上，选择 "**开始**  /  **程序**  /  **microsoft application virtualization**  /  **microsoft application virtualization Sequencer**"。</span><span class="sxs-lookup"><span data-stu-id="322ef-117">To start the App-V Sequencer Console, on the computer that is running the App-V Sequencer, select **Start** / **Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span> <span data-ttu-id="322ef-118">若要启动顺序向导，请单击 "**创建程序包**"。</span><span class="sxs-lookup"><span data-stu-id="322ef-118">To start the Sequencing Wizard, click **Create a Package**.</span></span>

3.  <span data-ttu-id="322ef-119">在 "**程序包信息**" 页面上，指定将分配给虚拟应用程序的**程序包名称**。</span><span class="sxs-lookup"><span data-stu-id="322ef-119">On the **Package Information** page, specify the **Package Name** that will be assigned to the virtual application.</span></span> <span data-ttu-id="322ef-120">要生成关联的 Windows Installer 文件，需要程序包名称。</span><span class="sxs-lookup"><span data-stu-id="322ef-120">The package name is required for generating the associated Windows Installer file.</span></span> <span data-ttu-id="322ef-121">你还应添加一个可选注释，该注释将分配给程序包并提供有关虚拟应用程序的详细信息。</span><span class="sxs-lookup"><span data-stu-id="322ef-121">You should also add an optional comment that will be assigned to the package and that provides detailed information about the virtual application.</span></span> <span data-ttu-id="322ef-122">若要显示 "**高级选项**" 页面，请选择 "**显示高级监视选项**"，然后单击 "**下一步**"。否则，请继续执行步骤5。</span><span class="sxs-lookup"><span data-stu-id="322ef-122">To display the **Advanced Options** page, select **Show Advanced Monitoring Options**, and then click **Next**; otherwise, proceed to step 5.</span></span>

4.  <span data-ttu-id="322ef-123">在 "**高级选项**" 页面上，若要允许 microsoft 更新按顺序更新应用程序，请选择 "**允许 microsoft 更新在监视期间运行**"。</span><span class="sxs-lookup"><span data-stu-id="322ef-123">On the **Advanced Options** page, to allow Microsoft Update to update the application as it is being sequenced, select **Allow Microsoft Update to run during monitoring**.</span></span> <span data-ttu-id="322ef-124">如果选择此选项，则可以在监视阶段安装 Microsoft 更新，并且必须接受相关联的更新才能安装这些更新。</span><span class="sxs-lookup"><span data-stu-id="322ef-124">If you select this option, Microsoft Updates can be installed during the monitoring phase, and you have to accept the associated updates for them to be installed.</span></span> <span data-ttu-id="322ef-125">若要重新映射受支持的动态链接库（.dll）文件，以便它们使用 RAM 的连续空间，请选择 "**变基 dll**"。</span><span class="sxs-lookup"><span data-stu-id="322ef-125">To remap the supported dynamic link library (.dll) files so that they use a contiguous space of RAM, select **Rebase DLLs**.</span></span> <span data-ttu-id="322ef-126">选择此选项可以保留内存并帮助提高性能。</span><span class="sxs-lookup"><span data-stu-id="322ef-126">Selecting this option can conserve memory and help improve performance.</span></span> <span data-ttu-id="322ef-127">许多应用程序不支持此选项，但它在内存有限的环境中（例如在终端服务器方案中）很有用。</span><span class="sxs-lookup"><span data-stu-id="322ef-127">Many applications do not support this option, but it is useful in environments with limited RAM such as in Terminal Server scenarios.</span></span> <span data-ttu-id="322ef-128">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="322ef-128">Click **Next**.</span></span>

5.  <span data-ttu-id="322ef-129">在 "**监视器安装**" 页面上，当你准备好安装应用程序时，单击 "**开始监视**"，然后在 "**浏览文件夹**" 对话框中，指定驱动器 Q 上将安装应用程序的目录。</span><span class="sxs-lookup"><span data-stu-id="322ef-129">On the **Monitor Installation** page, when you are ready to install the application, click **Begin Monitoring**, and in the **Browse for Folder** dialog box, specify the directory on drive Q where the application will be installed.</span></span> <span data-ttu-id="322ef-130">如果您没有配置驱动器问答，并且对应用程序虚拟化驱动器使用了不同的驱动器号，请选择本过程步骤1中指定的驱动器号。</span><span class="sxs-lookup"><span data-stu-id="322ef-130">If you did not configure drive Q and used a different drive letter for the application virtualization drive, select the drive letter you specified in step 1 of this procedure.</span></span> <span data-ttu-id="322ef-131">若要将应用程序安装到尚未在应用程序虚拟化驱动器上创建的文件夹中，请单击 "**创建新文件夹**"。</span><span class="sxs-lookup"><span data-stu-id="322ef-131">To install the application to a folder that has not been created on the application virtualization drive, click **Make New Folder**.</span></span> <span data-ttu-id="322ef-132">指定文件夹后，请等待排序器配置计算机进行排序。</span><span class="sxs-lookup"><span data-stu-id="322ef-132">After you specify the folder, wait while the Sequencer configures the computer for sequencing.</span></span>

    **<span data-ttu-id="322ef-133">重要提示</span><span class="sxs-lookup"><span data-stu-id="322ef-133">Important</span></span>**  
    <span data-ttu-id="322ef-134">必须在虚拟应用程序驱动器上安装序列化到单独目录中的每个应用程序，并且关联的文件夹名称长度不得超过8个字符。</span><span class="sxs-lookup"><span data-stu-id="322ef-134">You must install each application that you sequence into a separate directory on the virtual application drive, and the associated folder name must not be longer than eight characters.</span></span>



~~~
After the computer has been configured for sequencing, install the application so that the App-V Sequencer can monitor the installation; when you are finished, click **Stop Monitoring**, and then click **Next**.
~~~

6. <span data-ttu-id="322ef-135">在 "**配置应用程序**" 页面上，如有必要，请配置将与虚拟应用程序关联的快捷方式和文件类型关联。</span><span class="sxs-lookup"><span data-stu-id="322ef-135">On the **Configure Applications** page, if necessary, configure the shortcuts and file type associations that will be associated with the virtual application.</span></span> <span data-ttu-id="322ef-136">若要添加新的文件类型关联或快捷方式，请单击 "**添加**"，然后在 "**添加应用程序**" 对话框中，指定新元素。</span><span class="sxs-lookup"><span data-stu-id="322ef-136">To add a new file type association or shortcut, click **Add**, and in the **Add Application** dialog box, specify the new element.</span></span> <span data-ttu-id="322ef-137">若要删除现有快捷方式或文件类型关联，请单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="322ef-137">To remove an existing shortcut or file type association, click **Remove**.</span></span> <span data-ttu-id="322ef-138">若要编辑现有元素，请选择要修改的元素，然后单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="322ef-138">To edit an existing element, select the element you want to modify, and then click **Edit**.</span></span> <span data-ttu-id="322ef-139">在 "**编辑应用程序**" 对话框中指定配置。</span><span class="sxs-lookup"><span data-stu-id="322ef-139">Specify the configurations in the **Edit Application** dialog box.</span></span> <span data-ttu-id="322ef-140">单击 "**保存**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="322ef-140">Click **Save**, and then click **Next**.</span></span>

7. <span data-ttu-id="322ef-141">在 "**启动应用程序**" 页面上，若要启动应用程序以确保程序包已正确安装且已针对流式处理进行了优化，请选择该程序包，然后单击 "**启动**"。</span><span class="sxs-lookup"><span data-stu-id="322ef-141">On the **Launch Applications** page, to start the application to ensure that the package has been installed correctly and is optimized for streaming, select the package, and then click **Launch**.</span></span> <span data-ttu-id="322ef-142">此步骤可用于配置应用程序在目标计算机上的初始运行方式和接受任何关联的许可协议，然后再将程序包提供给 App-v 客户端。</span><span class="sxs-lookup"><span data-stu-id="322ef-142">This step is useful for configuring how the application initially runs on targeted computers and for accepting any associated license agreements before the package becomes available to App-V clients.</span></span> <span data-ttu-id="322ef-143">如果有多个应用程序与此程序包关联，则可以选择 "**全部启动**" 以打开所有应用程序。</span><span class="sxs-lookup"><span data-stu-id="322ef-143">If multiple applications are associated with this package, you can select **Launch All** to open all of the applications.</span></span> <span data-ttu-id="322ef-144">若要对程序包进行排序，请单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="322ef-144">To sequence the package, click **Next**.</span></span>

8. <span data-ttu-id="322ef-145">成功创建程序包后，在 app-v Sequencer 控制台中，选择 "**文件**  /  **保存**"，然后指定将保存程序包的名称和虚拟驱动器位置。</span><span class="sxs-lookup"><span data-stu-id="322ef-145">After you have successfully created the package, in the App-V Sequencer Console, select **File** / **Save** and specify the name and the virtual drive location where the package will be saved.</span></span>

   <span data-ttu-id="322ef-146">你可以选择创建关联的 Windows Installer 文件（**.msi**），以便在目标计算机上安装虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="322ef-146">You can optionally create an associated Windows Installer file (**.msi**) to install the virtual application package on targeted computers.</span></span> <span data-ttu-id="322ef-147">若要创建 Windows 安装程序文件，请在 Sequencer 中打开程序包，然后选择 "**工具**"  /  **创建 MSI**。</span><span class="sxs-lookup"><span data-stu-id="322ef-147">To create a Windows Installer file, open the package in the Sequencer and select **Tools** / **Create MSI**.</span></span> <span data-ttu-id="322ef-148">将创建 Windows 安装程序文件并将其保存在保存虚拟应用程序包的目录中。</span><span class="sxs-lookup"><span data-stu-id="322ef-148">The Windows Installer file will be created and saved in the directory where the virtual application package is saved.</span></span>

   **<span data-ttu-id="322ef-149">重要提示</span><span class="sxs-lookup"><span data-stu-id="322ef-149">Important</span></span>**  
   <span data-ttu-id="322ef-150">成功创建虚拟应用程序包后，不能在运行 sequencer 的计算机上运行虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="322ef-150">After you have successfully created a virtual application package, you cannot run the virtual application package on the computer running the sequencer.</span></span>



## <span data-ttu-id="322ef-151">相关主题</span><span class="sxs-lookup"><span data-stu-id="322ef-151">Related topics</span></span>


[<span data-ttu-id="322ef-152">如何升级虚拟应用程序包 (App-V 4.6)</span><span class="sxs-lookup"><span data-stu-id="322ef-152">How to Upgrade a Virtual Application Package (App-V 4.6)</span></span>](how-to-upgrade-a-virtual-application-package--app-v-46-.md)









