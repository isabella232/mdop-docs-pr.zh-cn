---
title: 如何升级现有的虚拟应用程序
description: 如何升级现有的虚拟应用程序
author: dansimp
ms.assetid: ec531576-2423-4c2c-9b9f-da74174a6858
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 71fb096c103a0bcb9913d4eea33b1259a33a54ee
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798973"
---
# <span data-ttu-id="95d74-103">如何升级现有的虚拟应用程序</span><span class="sxs-lookup"><span data-stu-id="95d74-103">How to Upgrade an Existing Virtual Application</span></span>


<span data-ttu-id="95d74-104">你可以使用应用程序虚拟化（App-v） Sequencer 将现有虚拟应用程序升级到新版本。</span><span class="sxs-lookup"><span data-stu-id="95d74-104">You can upgrade an existing virtual application to a new version by using the Application Virtualization (App-V) Sequencer.</span></span> <span data-ttu-id="95d74-105">升级过程类似于创建新的虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="95d74-105">The upgrade process is similar to creating a new virtual application.</span></span> <span data-ttu-id="95d74-106">必须打开现有虚拟应用程序进行升级，进行必要的更新，然后将已更新的虚拟应用程序保存到程序包根目录中的新位置。</span><span class="sxs-lookup"><span data-stu-id="95d74-106">You must open the existing virtual application for an upgrade, make the necessary updates, and then save the updated virtual application to a new location in the package root directory.</span></span>

<span data-ttu-id="95d74-107">你还可以使用 App-v Sequencer 控制台对现有虚拟应用程序进行更改，而无需执行升级。</span><span class="sxs-lookup"><span data-stu-id="95d74-107">You can also use the App-V Sequencer Console to make changes to an existing virtual application without performing an upgrade.</span></span> <span data-ttu-id="95d74-108">但是，不能通过使用此方法对虚拟应用程序的文件系统进行修改，因为 App-v 排序器不会实际解码关联的 sft 文件。</span><span class="sxs-lookup"><span data-stu-id="95d74-108">However, you cannot make modifications to the virtual application’s file system by using this method because the App-V Sequencer does not actually decode the associated .sft file.</span></span> <span data-ttu-id="95d74-109">例如，你可以通过选择 "**文件**" 菜单上的 "**打开**"，在 app-v Sequencer 控制台中打开现有虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="95d74-109">For example; you can open an existing virtual application in the App-V Sequencer Console by selecting **Open** on the **File** menu.</span></span> <span data-ttu-id="95d74-110">你可以更新**程序包名称**和关联的**注释**，并且可以对虚拟文件系统和虚拟注册表进行更改。</span><span class="sxs-lookup"><span data-stu-id="95d74-110">You can update the **Package Name** and the associated **Comments**, and you can make changes to the virtual file system and virtual registry.</span></span> <span data-ttu-id="95d74-111">您也可以创建一个 Windows 安装程序文件。</span><span class="sxs-lookup"><span data-stu-id="95d74-111">You can also create a Windows Installer file.</span></span>

<span data-ttu-id="95d74-112">使用以下过程升级现有虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="95d74-112">Use the following procedure to upgrade an existing virtual application.</span></span>

**<span data-ttu-id="95d74-113">升级现有虚拟应用程序</span><span class="sxs-lookup"><span data-stu-id="95d74-113">To upgrade an existing virtual application</span></span>**

1.  <span data-ttu-id="95d74-114">若要启动 app-v sequencer 控制台，请在运行 app-v 排序器的计算机上，选择 "**开始** / **程序** / **microsoft application virtualization** / **microsoft application virtualization Sequencer**"。</span><span class="sxs-lookup"><span data-stu-id="95d74-114">To start the App-V Sequencer Console, on the computer running the App-V Sequencer, select **Start**/**Programs**/**Microsoft Application Virtualization**/**Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="95d74-115">若要打开现有虚拟应用程序，请在 app-v 控制台中，选择 "**文件** / **打开" 以进行程序包升级**。</span><span class="sxs-lookup"><span data-stu-id="95d74-115">To open the existing virtual application, in the App-V Console, select **File**/**Open for Package Upgrade**.</span></span> <span data-ttu-id="95d74-116">使用 "**打开 For 程序包升级**" 对话框找到要为升级打开的关联 SPRJ 文件。</span><span class="sxs-lookup"><span data-stu-id="95d74-116">Use the **Open For Package Upgrade** dialog box to locate the associated SPRJ file you want to open for upgrade.</span></span>

3.  <span data-ttu-id="95d74-117">若要指定程序包的解码位置，请单击 "**浏览文件夹**" 并指定 Q:\\。</span><span class="sxs-lookup"><span data-stu-id="95d74-117">To specify the location of where the package will be decoded, click **Browse For Folder** and specify the Q:\\.</span></span> <span data-ttu-id="95d74-118">这是将根据关联的 SFT 文件中的指定创建程序包根目录的位置。</span><span class="sxs-lookup"><span data-stu-id="95d74-118">This is the location where the package root directory will be created as specified in the associated SFT file.</span></span> <span data-ttu-id="95d74-119">当你创建程序包的更新版本时，它将使用目录名称的顺序添加来表示，例如，"**.1**" 将添加到 Q:\\ 驱动器上的目录名称中。</span><span class="sxs-lookup"><span data-stu-id="95d74-119">When you create the updated version of the package, it will be denoted with a sequential addition to the directory name—for example, “**.1**” will be added to the directory name located on the Q:\\ drive.</span></span>

4.  <span data-ttu-id="95d74-120">若要打开排序向导，请选择 "**工具** / **序列化向导**"。</span><span class="sxs-lookup"><span data-stu-id="95d74-120">To open the Sequencing Wizard, select **Tools**/**Sequencing Wizard**.</span></span> <span data-ttu-id="95d74-121">在 "**程序包信息**" 页面上，选择指定新的**程序包名称**，并添加将与已更新的虚拟应用程序关联的可选注释。</span><span class="sxs-lookup"><span data-stu-id="95d74-121">On the **Package Information** page, optionally specify the new **Package Name** and add optional comments that will be associated with the updated virtual application.</span></span> <span data-ttu-id="95d74-122">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="95d74-122">Click **Next**.</span></span>

5.  <span data-ttu-id="95d74-123">在 "**监视器安装**" 页面上，要开始监视新安装，请单击 "**开始监视**"。</span><span class="sxs-lookup"><span data-stu-id="95d74-123">On the **Monitor Installation** page, to begin monitoring the new installation, click **Begin Monitoring**.</span></span> <span data-ttu-id="95d74-124">虚拟环境完成加载后，安装应用程序的更新版本，或将更新应用于现有应用程序。</span><span class="sxs-lookup"><span data-stu-id="95d74-124">After the virtual environment has finished loading, install the updated version of the application, or apply updates to the existing application.</span></span> <span data-ttu-id="95d74-125">完成虚拟应用程序的更新后，单击 "**停止监视**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="95d74-125">After you have finished updating the virtual application, click **Stop Monitoring**, and then click **Next**.</span></span>

6.  <span data-ttu-id="95d74-126">在 "**要映射到虚拟文件系统（vfs）的其他文件**" 页面上，若要指定要添加到虚拟文件系统（vfs）的其他文件，请单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="95d74-126">On the **Additional Files to Map to Virtual File System (VFS)** page, to specify additional files to be added to the Virtual File System (VFS), click **Add**.</span></span> <span data-ttu-id="95d74-127">通过浏览找到要添加的文件，然后单击 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="95d74-127">Browse to the file you want to add, and click **Open**.</span></span> <span data-ttu-id="95d74-128">若要清除已添加的现有文件，请单击 "**重置**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="95d74-128">To clear existing files that have been added, click **Reset**, and then click **Next**.</span></span>

7.  <span data-ttu-id="95d74-129">在 "**配置应用程序**" 页面上，配置将与已更新的虚拟应用程序关联的快捷方式和文件类型关联。</span><span class="sxs-lookup"><span data-stu-id="95d74-129">On the **Configure Applications** page, configure the shortcuts and file type associations that will be associated with the updated virtual application.</span></span> <span data-ttu-id="95d74-130">选择要更新的元素，然后单击 "**编辑位置**"。</span><span class="sxs-lookup"><span data-stu-id="95d74-130">Select the element you want to update, and then click **Edit Locations**.</span></span> <span data-ttu-id="95d74-131">在 "**快捷方式位置**" 对话框中指定配置，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="95d74-131">Specify the configurations in the **Shortcut Locations** dialog box, and then click **Next**.</span></span>

8.  <span data-ttu-id="95d74-132">在 "**启动应用程序**" 页面上，若要启动应用程序以确保程序包针对流进行优化，请选择程序包，然后单击 "**启动**"。</span><span class="sxs-lookup"><span data-stu-id="95d74-132">On the **Launch Applications** page, to start the application to ensure that the package is optimized for streaming, select the package and click **Launch**.</span></span> <span data-ttu-id="95d74-133">此步骤可用于配置应用程序最初在目标计算机上运行的方式，以及在将程序包提供给客户之前接受任何关联的许可协议。</span><span class="sxs-lookup"><span data-stu-id="95d74-133">This step is useful for configuring how the application initially runs on target computers and for accepting any associated license agreements before the package is made available to clients.</span></span> <span data-ttu-id="95d74-134">如果有多个应用程序与此程序包关联，则可以选择 "**全部启动**" 以打开所有应用程序。</span><span class="sxs-lookup"><span data-stu-id="95d74-134">If there are multiple applications associated with this package, you can select **Launch All** to open all of the applications.</span></span> <span data-ttu-id="95d74-135">若要对新版本的虚拟应用程序进行排序，请单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="95d74-135">To sequence the new version of the virtual application, click **Next**.</span></span>

9.  <span data-ttu-id="95d74-136">若要完成并关闭排序向导，请在 "**序列包**" 页面上，单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="95d74-136">To finish and to close the Sequencing Wizard, on the **Sequence Package** page, click **Finish**.</span></span>

10. <span data-ttu-id="95d74-137">成功更新虚拟应用程序后，若要保存程序包，请在 App-v Sequencer 控制台中的 "**文件**" 菜单上，选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="95d74-137">After you have successfully updated the virtual application, to save the package, in the App-V Sequencer Console, on the **File** menu, select **Save**.</span></span> <span data-ttu-id="95d74-138">可以在步骤3中指定的目录中访问虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="95d74-138">The virtual application can be accessed in the directory specified in step 3.</span></span>

## <span data-ttu-id="95d74-139">相关主题</span><span class="sxs-lookup"><span data-stu-id="95d74-139">Related topics</span></span>


[<span data-ttu-id="95d74-140">Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="95d74-140">Application Virtualization Sequencer</span></span>](application-virtualization-sequencer.md)

[<span data-ttu-id="95d74-141">如何使用命令行升级虚拟应用程序</span><span class="sxs-lookup"><span data-stu-id="95d74-141">How to Upgrade a Virtual Application by Using the Command Line</span></span>](how-to-upgrade-a-virtual-application-by-using-the-command-line.md)

 

 





