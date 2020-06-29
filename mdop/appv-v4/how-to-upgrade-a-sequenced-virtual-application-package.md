---
title: 如何升级已排序的虚拟应用程序包
description: 如何升级已排序的虚拟应用程序包
author: dansimp
ms.assetid: ffa989f3-6621-4c59-9599-e3c3b3332f67
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 45f7b3370e7989bfa860c25fd4ac81f2c2eb0959
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801035"
---
# <span data-ttu-id="70895-103">如何升级已排序的虚拟应用程序包</span><span class="sxs-lookup"><span data-stu-id="70895-103">How to Upgrade a Sequenced Virtual Application Package</span></span>


<span data-ttu-id="70895-104">你可以使用应用程序虚拟化（App-v） Sequencer 将现有虚拟应用程序升级到新版本。</span><span class="sxs-lookup"><span data-stu-id="70895-104">You can upgrade an existing virtual application to a new version by using the Application Virtualization (App-V) Sequencer.</span></span> <span data-ttu-id="70895-105">升级过程类似于创建新的虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="70895-105">The upgrade process is similar to creating a new virtual application.</span></span> <span data-ttu-id="70895-106">必须打开现有虚拟应用程序进行升级，进行必要的更新，然后将已更新的虚拟应用程序保存到程序包根目录中的新位置。</span><span class="sxs-lookup"><span data-stu-id="70895-106">You must open the existing virtual application for an upgrade, make the necessary updates, and then save the updated virtual application to a new location in the package root directory.</span></span> <span data-ttu-id="70895-107">你还可以使用 App-v Sequencer 控制台对现有虚拟应用程序进行更改，而无需执行升级。</span><span class="sxs-lookup"><span data-stu-id="70895-107">You can also use the App-V Sequencer Console to make changes to an existing virtual application without performing an upgrade.</span></span> <span data-ttu-id="70895-108">但是，不能通过使用此方法对虚拟应用程序的文件系统进行修改，因为 App-v 排序器不会实际解码关联的 sft 文件。</span><span class="sxs-lookup"><span data-stu-id="70895-108">However, you cannot make modifications to the virtual application’s file system by using this method because the App-V Sequencer does not actually decode the associated .sft file.</span></span> <span data-ttu-id="70895-109">例如，你可以通过选择 "**文件**" 菜单上的 "**打开**"，在 app-v Sequencer 控制台中打开现有虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="70895-109">For example; you can open an existing virtual application in the App-V Sequencer Console by selecting **Open** on the **File** menu.</span></span> <span data-ttu-id="70895-110">你可以更新**程序包名称**和关联的**注释**，并且可以对虚拟文件系统和虚拟注册表进行更改。</span><span class="sxs-lookup"><span data-stu-id="70895-110">You can update the **Package Name** and the associated **Comments**, and you can make changes to the virtual file system and virtual registry.</span></span> <span data-ttu-id="70895-111">您也可以创建一个 Windows 安装程序文件。</span><span class="sxs-lookup"><span data-stu-id="70895-111">You can also create a Windows Installer file.</span></span>

<span data-ttu-id="70895-112">**小心** 当升级现有虚拟应用程序包时，不应引用以前版本的 Windows Installer （.msi）文件，因为升级期间将修改该 sft 文件的以前版本。</span><span class="sxs-lookup"><span data-stu-id="70895-112">**Caution** You should not reference a previous version of the Windows Installer (.msi) file when you upgrade an existing virtual application package because the previous version of the .sft file will be modified during the upgrade.</span></span>

 

<span data-ttu-id="70895-113">使用以下过程升级现有虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="70895-113">Use the following procedure to upgrade an existing virtual application.</span></span>

**<span data-ttu-id="70895-114">升级现有虚拟应用程序</span><span class="sxs-lookup"><span data-stu-id="70895-114">To upgrade an existing virtual application</span></span>**

1.  <span data-ttu-id="70895-115">若要启动 app-v sequencer 控制台，请在运行 app-v 排序器的计算机上，选择 "**开始** / **程序** / **microsoft application virtualization** / **microsoft application virtualization Sequencer**"。</span><span class="sxs-lookup"><span data-stu-id="70895-115">To start the App-V Sequencer Console, on the computer running the App-V Sequencer, select **Start**/**Programs**/**Microsoft Application Virtualization**/**Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="70895-116">若要打开现有虚拟应用程序，请在 app-v 控制台中，选择 "**文件** / **打开" 以进行程序包升级**。</span><span class="sxs-lookup"><span data-stu-id="70895-116">To open the existing virtual application, in the App-V Console, select **File**/**Open for Package Upgrade**.</span></span> <span data-ttu-id="70895-117">使用 "**打开 For 程序包升级**" 对话框找到要为升级打开的关联 SPRJ 文件。</span><span class="sxs-lookup"><span data-stu-id="70895-117">Use the **Open For Package Upgrade** dialog box to locate the associated SPRJ file you want to open for upgrade.</span></span>

3.  <span data-ttu-id="70895-118">若要指定更新的程序包的解码位置，请使用 "**浏览文件夹**" 对话框浏览到该位置。</span><span class="sxs-lookup"><span data-stu-id="70895-118">To specify the location of where the updated package will be decoded, browse to the location by using the **Browse For Folder** dialog box.</span></span> <span data-ttu-id="70895-119">这是将根据关联的 SFT 文件中的指定创建程序包根目录的位置。</span><span class="sxs-lookup"><span data-stu-id="70895-119">This is the location where the package root directory will be created as specified in the associated SFT file.</span></span> <span data-ttu-id="70895-120">你指定的目录必须是保存虚拟应用程序的原始版本的其他位置。</span><span class="sxs-lookup"><span data-stu-id="70895-120">The directory that you specify must be a different location from where the original version of the virtual application is saved.</span></span> <span data-ttu-id="70895-121">如果尚未创建新目标文件夹，则可以单击 "**创建新文件夹**"。</span><span class="sxs-lookup"><span data-stu-id="70895-121">You can click **Make New Folder** if the new target folder has not been created yet.</span></span> <span data-ttu-id="70895-122">应选择应用程序虚拟化驱动器的根以创建文件夹。</span><span class="sxs-lookup"><span data-stu-id="70895-122">You should select the root of the Application Virtualization drive to create the folder.</span></span> <span data-ttu-id="70895-123">当你创建程序包的更新版本时，它将使用目录名称的顺序添加来表示，例如，"**.1**" 将添加到 Q:\\ 驱动器上的目录名称中。</span><span class="sxs-lookup"><span data-stu-id="70895-123">When you create the updated version of the package, it will be denoted with a sequential addition to the directory name—for example, “**.1**” will be added to the directory name located on the Q:\\ drive.</span></span>

    <span data-ttu-id="70895-124">**重要提示** 你指定的目录必须位于 Q:\\ 驱动器上的程序包根目录中。</span><span class="sxs-lookup"><span data-stu-id="70895-124">**Important** The directory that you specify must be located in the package root directory on the Q:\\ drive.</span></span> <span data-ttu-id="70895-125">你可以创建新文件夹，也可以在保存原始虚拟应用程序的目录下创建一个子文件夹。</span><span class="sxs-lookup"><span data-stu-id="70895-125">You can create a new folder, or you can create a subfolder under the directory where the original virtual application is saved.</span></span> <span data-ttu-id="70895-126">分配给新文件夹的名称不得超过 8 8 个字符。</span><span class="sxs-lookup"><span data-stu-id="70895-126">The name assigned to the new folder must not be longer than 8 eight characters.</span></span>

     

4.  <span data-ttu-id="70895-127">若要打开排序向导，请选择 "**工具** / **序列化向导**"。</span><span class="sxs-lookup"><span data-stu-id="70895-127">To open the Sequencing Wizard, select **Tools**/**Sequencing Wizard**.</span></span> <span data-ttu-id="70895-128">在 "**程序包信息**" 页面上，选择指定新的**程序包名称**，并添加将与已更新的虚拟应用程序关联的可选注释。</span><span class="sxs-lookup"><span data-stu-id="70895-128">On the **Package Information** page, optionally specify the new **Package Name** and add optional comments that will be associated with the updated virtual application.</span></span> <span data-ttu-id="70895-129">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="70895-129">Click **Next**.</span></span>

5.  <span data-ttu-id="70895-130">在 "**监视器安装**" 页面上，要开始监视新安装，请单击 "**开始监视**"。</span><span class="sxs-lookup"><span data-stu-id="70895-130">On the **Monitor Installation** page, to begin monitoring the new installation, click **Begin Monitoring**.</span></span> <span data-ttu-id="70895-131">虚拟环境完成加载后，安装应用程序的更新版本，或将更新应用于现有应用程序。</span><span class="sxs-lookup"><span data-stu-id="70895-131">After the virtual environment has finished loading, install the updated version of the application, or apply updates to the existing application.</span></span> <span data-ttu-id="70895-132">完成虚拟应用程序的更新后，单击 "**停止监视**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="70895-132">After you have finished updating the virtual application, click **Stop Monitoring**, and then click **Next**.</span></span>

6.  <span data-ttu-id="70895-133">在 "**要映射到虚拟文件系统（vfs）的其他文件**" 页面上，若要指定要添加到虚拟文件系统（vfs）的其他文件，请单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="70895-133">On the **Additional Files to Map to Virtual File System (VFS)** page, to specify additional files to be added to the Virtual File System (VFS), click **Add**.</span></span> <span data-ttu-id="70895-134">通过浏览找到要添加的文件，然后单击 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="70895-134">Browse to the file you want to add, and click **Open**.</span></span> <span data-ttu-id="70895-135">若要清除已添加的现有文件，请单击 "**重置**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="70895-135">To clear existing files that have been added, click **Reset**, and then click **Next**.</span></span>

7.  <span data-ttu-id="70895-136">在 "**配置应用程序**" 页面上，配置将与已更新的虚拟应用程序关联的快捷方式和文件类型关联。</span><span class="sxs-lookup"><span data-stu-id="70895-136">On the **Configure Applications** page, configure the shortcuts and file type associations that will be associated with the updated virtual application.</span></span> <span data-ttu-id="70895-137">选择要更新的元素，然后单击 "**编辑位置**"。</span><span class="sxs-lookup"><span data-stu-id="70895-137">Select the element you want to update, and then click **Edit Locations**.</span></span> <span data-ttu-id="70895-138">在 "**快捷方式位置**" 对话框中指定配置，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="70895-138">Specify the configurations in the **Shortcut Locations** dialog box, and then click **Next**.</span></span>

8.  <span data-ttu-id="70895-139">在 "**启动应用程序**" 页面上，若要启动应用程序以确保程序包针对流进行优化，请选择程序包，然后单击 "**启动**"。</span><span class="sxs-lookup"><span data-stu-id="70895-139">On the **Launch Applications** page, to start the application to ensure that the package is optimized for streaming, select the package and click **Launch**.</span></span> <span data-ttu-id="70895-140">此步骤可用于配置应用程序最初在目标计算机上运行的方式，以及在将程序包提供给客户之前接受任何关联的许可协议。</span><span class="sxs-lookup"><span data-stu-id="70895-140">This step is useful for configuring how the application initially runs on target computers and for accepting any associated license agreements before the package is made available to clients.</span></span> <span data-ttu-id="70895-141">如果有多个应用程序与此程序包关联，则可以选择 "**全部启动**" 以打开所有应用程序。</span><span class="sxs-lookup"><span data-stu-id="70895-141">If there are multiple applications associated with this package, you can select **Launch All** to open all of the applications.</span></span> <span data-ttu-id="70895-142">若要对新版本的虚拟应用程序进行排序，请单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="70895-142">To sequence the new version of the virtual application, click **Next**.</span></span>

9.  <span data-ttu-id="70895-143">若要完成并关闭排序向导，请在 "**序列包**" 页面上，单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="70895-143">To finish and to close the Sequencing Wizard, on the **Sequence Package** page, click **Finish**.</span></span>

10. <span data-ttu-id="70895-144">成功更新虚拟应用程序后，若要保存程序包，请在 App-v Sequencer 控制台中的 "**文件**" 菜单上，选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="70895-144">After you have successfully updated the virtual application, to save the package, in the App-V Sequencer Console, on the **File** menu, select **Save**.</span></span> <span data-ttu-id="70895-145">可以在步骤3中指定的目录中访问虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="70895-145">The virtual application can be accessed in the directory specified in step 3.</span></span>

## <span data-ttu-id="70895-146">相关主题</span><span class="sxs-lookup"><span data-stu-id="70895-146">Related topics</span></span>


[<span data-ttu-id="70895-147">Application Virtualization Sequencer 的任务</span><span class="sxs-lookup"><span data-stu-id="70895-147">Tasks for the Application Virtualization Sequencer</span></span>](tasks-for-the-application-virtualization-sequencer.md)

 

 





