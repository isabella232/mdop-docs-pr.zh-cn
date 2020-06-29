---
title: 如何升级虚拟应用程序包 (App-V 4.6)
description: 如何升级虚拟应用程序包 (App-V 4.6)
author: dansimp
ms.assetid: 3566227e-f3dc-4c32-af1f-e0211588118c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ac722dc0e9ce1650f53d8dd22db5428d33cfcf13
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801024"
---
# <span data-ttu-id="2ec96-103">如何升级虚拟应用程序包 (App-V 4.6)</span><span class="sxs-lookup"><span data-stu-id="2ec96-103">How to Upgrade a Virtual Application Package (App-V 4.6)</span></span>


<span data-ttu-id="2ec96-104">使用以下过程，通过使用应用程序虚拟化（App-v） Sequencer 升级现有虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="2ec96-104">Use the following procedure to upgrade an existing virtual application by using the Application Virtualization (App-V) Sequencer.</span></span> <span data-ttu-id="2ec96-105">你还可以使用 App-v Sequencer 控制台对现有虚拟应用程序进行更改，但不执行升级，但不能通过使用此方法对虚拟应用程序的文件系统进行修改，因为 App-v Sequencer 不会实际解码关联的 sft 文件。</span><span class="sxs-lookup"><span data-stu-id="2ec96-105">You can also use the App-V Sequencer Console to make changes to an existing virtual application without performing an upgrade, but you cannot make modifications to the virtual application’s file system by using this method because the App-V Sequencer does not actually decode the associated .sft file.</span></span> <span data-ttu-id="2ec96-106">有关编辑现有程序包的详细信息，请参阅[如何修改虚拟应用程序包（app-v 4.6）](how-to-modify-a-virtual-application-package--app-v-46-.md)。</span><span class="sxs-lookup"><span data-stu-id="2ec96-106">For more information about editing an existing package, see [How to Modify a Virtual Application Package (App-V 4.6)](how-to-modify-a-virtual-application-package--app-v-46-.md).</span></span>

**<span data-ttu-id="2ec96-107">升级现有虚拟应用程序</span><span class="sxs-lookup"><span data-stu-id="2ec96-107">To upgrade an existing virtual application</span></span>**

1.  <span data-ttu-id="2ec96-108">若要启动 app-v sequencer 控制台，请在运行 app-v 排序器的计算机上，选择 "**开始**  /  **程序**  /  **microsoft application virtualization**  /  **microsoft application virtualization Sequencer**"。</span><span class="sxs-lookup"><span data-stu-id="2ec96-108">To start the App-V Sequencer Console, on the computer running the App-V Sequencer, select **Start** / **Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="2ec96-109">若要打开现有虚拟应用程序包并启动**顺序向导**，请选择 "**升级程序包**"。</span><span class="sxs-lookup"><span data-stu-id="2ec96-109">To open the existing virtual application package and start the **Sequencing Wizard**, select **Upgrade a Package**.</span></span> <span data-ttu-id="2ec96-110">找到要升级的程序包，然后单击 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="2ec96-110">Locate the package you want to upgrade, and click **Open**.</span></span> <span data-ttu-id="2ec96-111">在 "**浏览文件夹**" 对话框中，指定将放置程序包升级版本的位置。</span><span class="sxs-lookup"><span data-stu-id="2ec96-111">In the **Browse For Folder** dialog box, specify the location where the upgraded version of the package will be placed.</span></span> <span data-ttu-id="2ec96-112">指定的此位置必须位于指定为应用程序虚拟化驱动器（通常是 Q:\\ 驱动器）的驱动器上。</span><span class="sxs-lookup"><span data-stu-id="2ec96-112">This location specified must be located on the drive specified as the application virtualization drive, which is typically the Q:\\ drive.</span></span> <span data-ttu-id="2ec96-113">若要创建新文件夹，请选择 "创建**新文件夹**"。</span><span class="sxs-lookup"><span data-stu-id="2ec96-113">To create a new folder, select **Make New Folder**.</span></span>

    <span data-ttu-id="2ec96-114">**警告** 必须指定现有虚拟应用程序的根文件夹。</span><span class="sxs-lookup"><span data-stu-id="2ec96-114">**Warning** You must specify the root folder of the existing virtual application.</span></span> <span data-ttu-id="2ec96-115">不要手动创建子文件夹，否则升级将失败。</span><span class="sxs-lookup"><span data-stu-id="2ec96-115">Do not manually create a subfolder or the upgrade will fail.</span></span>

     

3.  <span data-ttu-id="2ec96-116">在 "**程序包信息**" 页面上，指定将分配给更新的程序包的**程序包名称**。</span><span class="sxs-lookup"><span data-stu-id="2ec96-116">On the **Package Information** page, specify the **Package Name** that will be assigned to the updated package.</span></span> <span data-ttu-id="2ec96-117">要生成关联的 Windows Installer 文件，需要程序包名称。</span><span class="sxs-lookup"><span data-stu-id="2ec96-117">The package name is required for generating the associated Windows Installer file.</span></span> <span data-ttu-id="2ec96-118">你还应添加一个可选注释，该注释将分配给程序包并提供有关虚拟应用程序的详细信息（例如版本号）。</span><span class="sxs-lookup"><span data-stu-id="2ec96-118">You should also add an optional comment that will be assigned to the package and that provides detailed information about the virtual application—for example, a version number.</span></span> <span data-ttu-id="2ec96-119">要显示 "**高级选项**" 页面，请选择 "**显示高级监视选项**"，然后单击 "**下一步**"。否则，请继续执行步骤5。</span><span class="sxs-lookup"><span data-stu-id="2ec96-119">To display the **Advanced Options** page, select **Show Advanced Monitoring Options** and click **Next**; otherwise, proceed to step 5.</span></span>

4.  <span data-ttu-id="2ec96-120">在 "**高级选项**" 页面上，若要允许 microsoft 更新按顺序更新应用程序，请选择 "**允许 microsoft 更新在监视期间运行**"。</span><span class="sxs-lookup"><span data-stu-id="2ec96-120">On the **Advanced Options** page, to allow Microsoft Update to update the application as it is being sequenced, select **Allow Microsoft Update to run during monitoring**.</span></span> <span data-ttu-id="2ec96-121">如果选择此选项，将允许在监视阶段中安装 Microsoft 更新，你需要接受相关更新才能安装这些更新。</span><span class="sxs-lookup"><span data-stu-id="2ec96-121">If you select this option, Microsoft Updates are allowed to be installed during the monitoring phase and you will need to accept the associated updates for them to be installed.</span></span> <span data-ttu-id="2ec96-122">若要重新映射受支持的动态链接库（.dll）文件，以便它们使用 RAM 的连续空间，请选择 "**变基 dll**"。</span><span class="sxs-lookup"><span data-stu-id="2ec96-122">To remap the supported dynamic-link library (.dll) files so that they use a contiguous space of RAM, select **Rebase DLLs**.</span></span> <span data-ttu-id="2ec96-123">选择此选项可以保留内存并帮助提高性能。</span><span class="sxs-lookup"><span data-stu-id="2ec96-123">Selecting this option can conserve memory and help improve performance.</span></span> <span data-ttu-id="2ec96-124">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2ec96-124">Click **Next**.</span></span>

5.  <span data-ttu-id="2ec96-125">在 "**监视器安装**" 页面上，当你准备好更新应用程序时，单击 "**开始监视**"。</span><span class="sxs-lookup"><span data-stu-id="2ec96-125">On the **Monitor Installation** page, when you are ready to update the application, click **Begin Monitoring**.</span></span>

    <span data-ttu-id="2ec96-126">应用了应用程序的更新后，单击 "**停止监视**"。</span><span class="sxs-lookup"><span data-stu-id="2ec96-126">When the updates to the application have been applied, click **Stop Monitoring**.</span></span> <span data-ttu-id="2ec96-127">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2ec96-127">Click **Next**.</span></span>

6.  <span data-ttu-id="2ec96-128">在 "**配置应用程序**" 页面上，如有必要，请配置将与虚拟应用程序关联的快捷方式和文件类型关联。</span><span class="sxs-lookup"><span data-stu-id="2ec96-128">On the **Configure Applications** page, if necessary, configure the shortcuts and file type associations that will be associated with the virtual application.</span></span> <span data-ttu-id="2ec96-129">若要添加新的文件类型关联或快捷方式，请单击 "**添加**"，然后在 "**添加应用程序**" 对话框中，指定新元素。</span><span class="sxs-lookup"><span data-stu-id="2ec96-129">To add a new file type association or shortcut, click **Add**, and in the **Add Application** dialog box, specify the new element.</span></span> <span data-ttu-id="2ec96-130">若要删除现有快捷方式或文件类型关联，请单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="2ec96-130">To remove an existing shortcut or file type association, click **Remove**.</span></span> <span data-ttu-id="2ec96-131">若要编辑现有元素，请选择要修改的元素，然后单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="2ec96-131">To edit an existing element, select the element you want to modify, and then click **Edit**.</span></span> <span data-ttu-id="2ec96-132">在 "**编辑应用程序**" 对话框中指定配置。</span><span class="sxs-lookup"><span data-stu-id="2ec96-132">Specify the configurations in the **Edit Application** dialog box.</span></span> <span data-ttu-id="2ec96-133">单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="2ec96-133">Click **Save**.</span></span> <span data-ttu-id="2ec96-134">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2ec96-134">Click **Next**.</span></span>

7.  <span data-ttu-id="2ec96-135">在 "**启动应用程序**" 页面上，若要启动应用程序以确保程序包已正确安装且已针对流式处理进行了优化，请选择程序包，然后单击 "**启动**"。</span><span class="sxs-lookup"><span data-stu-id="2ec96-135">On the **Launch Applications** page, to start the application to ensure that the package has been installed correctly and is optimized for streaming, select the package and click **Launch**.</span></span> <span data-ttu-id="2ec96-136">此步骤可用于配置应用程序最初在目标计算机上运行的方式，以及在将程序包提供给 App-v 客户端之前接受任何关联的许可协议。</span><span class="sxs-lookup"><span data-stu-id="2ec96-136">This step is useful for configuring how the application initially runs on target computers and for accepting any associated license agreements before the package is made available to App-V clients.</span></span> <span data-ttu-id="2ec96-137">如果有多个应用程序与此程序包关联，则可以选择 "**全部启动**" 以打开所有应用程序。</span><span class="sxs-lookup"><span data-stu-id="2ec96-137">If multiple applications are associated with this package, you can select **Launch All** to open all of the applications.</span></span> <span data-ttu-id="2ec96-138">若要对程序包进行排序，请单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="2ec96-138">To sequence the package, click **Next**.</span></span>

8.  <span data-ttu-id="2ec96-139">若要关闭排序向导，请单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="2ec96-139">To close the Sequencing Wizard, click **Finish**.</span></span> <span data-ttu-id="2ec96-140">若要保存已更新的程序包，请在 Sequencer 控制台中选择 "**文件**  /  **保存**"。</span><span class="sxs-lookup"><span data-stu-id="2ec96-140">To save the updated package, in the Sequencer Console, select **File** / **Save**.</span></span>

    <span data-ttu-id="2ec96-141">如果你计划使用 Windows Installer 文件（.msi）部署更新的程序包，则必须创建新程序包，如下所示：在 Sequencer 控制台中，选择 "**工具**  /  **创建 msi**"。</span><span class="sxs-lookup"><span data-stu-id="2ec96-141">If you plan to deploy the updated package by using a Windows Installer file (.msi), you must create new one as follows: in the Sequencer Console, select **Tools** / **Create MSI**.</span></span> <span data-ttu-id="2ec96-142">将创建新的 Windows Installer 文件，并将其保存在保存已更新虚拟应用程序包的目录中。</span><span class="sxs-lookup"><span data-stu-id="2ec96-142">The new Windows Installer file will be created and saved in the directory where the updated virtual application package is saved.</span></span>

## <span data-ttu-id="2ec96-143">相关主题</span><span class="sxs-lookup"><span data-stu-id="2ec96-143">Related topics</span></span>


[<span data-ttu-id="2ec96-144">如何对新应用程序进行排序 (App-V 4.6)</span><span class="sxs-lookup"><span data-stu-id="2ec96-144">How to Sequence a New Application (App-V 4.6)</span></span>](how-to-sequence-a-new-application--app-v-46-.md)

 

 





