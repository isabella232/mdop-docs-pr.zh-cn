---
title: 创建和管理 App-V 5.0 虚拟化应用程序
description: 创建和管理 App-V 5.0 虚拟化应用程序
author: dansimp
ms.assetid: 66bab403-d7e0-4e7b-bc8f-a29a98a7160a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 86332c7753b70abbaaf289fc1ba046bf59d1dd89
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798611"
---
# <span data-ttu-id="b7aee-103">创建和管理 App-V 5.0 虚拟化应用程序</span><span class="sxs-lookup"><span data-stu-id="b7aee-103">Creating and Managing App-V 5.0 Virtualized Applications</span></span>


<span data-ttu-id="b7aee-104">在正确部署 Microsoft Application Virtualization （App-v） 5.0 sequencer 后，可以使用它监视和记录应用程序的安装和设置过程，以使应用程序作为虚拟化应用程序运行。</span><span class="sxs-lookup"><span data-stu-id="b7aee-104">After you have properly deployed the Microsoft Application Virtualization (App-V) 5.0 sequencer, you can use it to monitor and record the installation and setup process for an application to be run as a virtualized application.</span></span>

<span data-ttu-id="b7aee-105">**注意** 有关配置 Microsoft Application Virtualization （App-v） 5.0 sequencer、顺序最佳做法以及创建和更新虚拟应用程序的示例的详细信息，请参阅[Microsoft Application Virtualization 5.0 排序指南](https://download.microsoft.com/download/F/7/8/F784A197-73BE-48FF-83DA-4102C05A6D44/App-V 5.0 Sequencing Guide.docx)（ https://download.microsoft.com/download/F/7/8/F784A197-73BE-48FF-83DA-4102C05A6D44/App-V 5.0 先后顺序 Guide.docx）。</span><span class="sxs-lookup"><span data-stu-id="b7aee-105">**Note** For more information about configuring the Microsoft Application Virtualization (App-V) 5.0 sequencer, sequencing best practices, and an example of creating and updating a virtual application, see the [Microsoft Application Virtualization 5.0 Sequencing Guide](https://download.microsoft.com/download/F/7/8/F784A197-73BE-48FF-83DA-4102C05A6D44/App-V 5.0 Sequencing Guide.docx) (https://download.microsoft.com/download/F/7/8/F784A197-73BE-48FF-83DA-4102C05A6D44/App-V 5.0 Sequencing Guide.docx).</span></span>

 

## <span data-ttu-id="b7aee-106">对应用程序进行排序</span><span class="sxs-lookup"><span data-stu-id="b7aee-106">Sequencing an application</span></span>


<span data-ttu-id="b7aee-107">你可以使用 app-v 5.0 Sequencer 执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="b7aee-107">You can use the App-V 5.0 Sequencer to perform the following tasks:</span></span>

-   <span data-ttu-id="b7aee-108">创建可部署到运行 App-v 5.0 客户端的计算机的虚拟程序包。</span><span class="sxs-lookup"><span data-stu-id="b7aee-108">Create virtual packages that can be deployed to computers running the App-V 5.0 client.</span></span>

-   <span data-ttu-id="b7aee-109">升级现有程序包。</span><span class="sxs-lookup"><span data-stu-id="b7aee-109">Upgrade existing packages.</span></span> <span data-ttu-id="b7aee-110">你可以将现有程序包扩展到运行 sequencer 的计算机上，然后升级该应用程序以创建较新的版本。</span><span class="sxs-lookup"><span data-stu-id="b7aee-110">You can expand an existing package onto the computer running the sequencer and then upgrade the application to create a newer version.</span></span>

-   <span data-ttu-id="b7aee-111">编辑与现有程序包相关联的配置信息。</span><span class="sxs-lookup"><span data-stu-id="b7aee-111">Edit configuration information associated with an existing package.</span></span> <span data-ttu-id="b7aee-112">例如，你可以添加快捷方式或修改文件类型关联。</span><span class="sxs-lookup"><span data-stu-id="b7aee-112">For example, you can add a shortcut or modify a file type association.</span></span>

    <span data-ttu-id="b7aee-113">**注意** 必须创建快捷方式并将其保存到可用的网络位置以允许漫游。</span><span class="sxs-lookup"><span data-stu-id="b7aee-113">**Note** You must create shortcuts and save them to an available network location to allow roaming.</span></span> <span data-ttu-id="b7aee-114">如果在专用位置创建和保存了快捷方式，则程序包必须在本地发布到运行 App-v 5.0 客户端的计算机。</span><span class="sxs-lookup"><span data-stu-id="b7aee-114">If a shortcut is created and saved in a private location, the package must be published locally to the computer running the App-V 5.0 client.</span></span>

     

-   <span data-ttu-id="b7aee-115">转换现有虚拟程序包。</span><span class="sxs-lookup"><span data-stu-id="b7aee-115">Convert existing virtual packages.</span></span>

<span data-ttu-id="b7aee-116">排序器使用 **% TMP% \ 暂存**或 **% TEMP% \\ 暂存**目录和**临时**目录在排序期间存储临时文件。</span><span class="sxs-lookup"><span data-stu-id="b7aee-116">The sequencer uses the **%TMP% \\ Scratch** or **%TEMP% \\ Scratch** directory and the **Temp** directory to store temporary files during sequencing.</span></span> <span data-ttu-id="b7aee-117">在运行 sequencer 的计算机上，你应该将这些目录配置为与估计的应用程序安装要求等效的可用磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="b7aee-117">On the computer that runs the sequencer, you should configure these directories with free disk space equivalent to the estimated application installation requirements.</span></span> <span data-ttu-id="b7aee-118">在不同的硬驱分区上配置临时目录和临时目录有助于在序列化期间提高性能。</span><span class="sxs-lookup"><span data-stu-id="b7aee-118">Configuring the temp directories and the Temp directory on different hard drive partitions can help improve performance during sequencing.</span></span>

<span data-ttu-id="b7aee-119">使用 sequencer 创建新的虚拟应用程序时，将创建以下列出的文件。</span><span class="sxs-lookup"><span data-stu-id="b7aee-119">When you use the sequencer to create a new virtual application, the following listed files are created.</span></span> <span data-ttu-id="b7aee-120">这些文件包含 App-v 5.0 程序包。</span><span class="sxs-lookup"><span data-stu-id="b7aee-120">These files comprise the App-V 5.0 package.</span></span>

-   <span data-ttu-id="b7aee-121">.msi 文件。</span><span class="sxs-lookup"><span data-stu-id="b7aee-121">.msi file.</span></span> <span data-ttu-id="b7aee-122">此 Windows Installer （.msi）文件由 sequencer 创建，用于在目标计算机上安装虚拟程序包。</span><span class="sxs-lookup"><span data-stu-id="b7aee-122">This Windows Installer (.msi) file is created by the sequencer and is used to install the virtual package on target computers.</span></span>

-   <span data-ttu-id="b7aee-123">Report.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="b7aee-123">Report.xml file.</span></span> <span data-ttu-id="b7aee-124">在此文件中，sequencer 将保存在排序期间发现的所有问题、警告和错误。</span><span class="sxs-lookup"><span data-stu-id="b7aee-124">In this file, the sequencer saves all issues, warnings, and errors that were discovered during sequencing.</span></span> <span data-ttu-id="b7aee-125">在创建程序包后显示信息。</span><span class="sxs-lookup"><span data-stu-id="b7aee-125">It displays the information after the package has been created.</span></span> <span data-ttu-id="b7aee-126">您可以通过此报告进行诊断和故障排除。</span><span class="sxs-lookup"><span data-stu-id="b7aee-126">You can us this report for diagnosing and troubleshooting.</span></span>

-   <span data-ttu-id="b7aee-127">appv 文件。</span><span class="sxs-lookup"><span data-stu-id="b7aee-127">.appv file.</span></span> <span data-ttu-id="b7aee-128">这是虚拟应用程序文件。</span><span class="sxs-lookup"><span data-stu-id="b7aee-128">This is the virtual application file.</span></span>

-   <span data-ttu-id="b7aee-129">部署配置文件。</span><span class="sxs-lookup"><span data-stu-id="b7aee-129">Deployment configuration file.</span></span> <span data-ttu-id="b7aee-130">部署配置文件确定如何将虚拟应用程序部署到目标计算机。</span><span class="sxs-lookup"><span data-stu-id="b7aee-130">The deployment configuration file determines how the virtual application will be deployed to target computers.</span></span>

-   <span data-ttu-id="b7aee-131">用户配置文件。</span><span class="sxs-lookup"><span data-stu-id="b7aee-131">User configuration file.</span></span> <span data-ttu-id="b7aee-132">用户配置文件确定虚拟应用程序将如何在目标计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="b7aee-132">The user configuration file determines how the virtual application will run on target computers.</span></span>

<span data-ttu-id="b7aee-133">**重要提示** 您必须配置% TMP% 和% TEMP% 的文件夹，程序包转换器使用该文件夹作为安全的位置和目录。</span><span class="sxs-lookup"><span data-stu-id="b7aee-133">**Important** You must configure the %TMP% and %TEMP% folders that the package converter uses to be a secure location and directory.</span></span> <span data-ttu-id="b7aee-134">安全位置只能由管理员访问。</span><span class="sxs-lookup"><span data-stu-id="b7aee-134">A secure location is only accessible by an administrator.</span></span> <span data-ttu-id="b7aee-135">此外，当你对程序包进行排序时，你应该将程序包保存到安全的位置，或者确保在转换和监视过程中不允许登录任何其他用户。</span><span class="sxs-lookup"><span data-stu-id="b7aee-135">Additionally, when you sequence the package you should save the package to a location that is secure, or make sure that no other user is allowed to be logged in during the conversion and monitoring process.</span></span>

 

<span data-ttu-id="b7aee-136">Sequencer 控制台中的 "**选项**" 对话框包含以下选项卡：</span><span class="sxs-lookup"><span data-stu-id="b7aee-136">The **Options** dialog box in the sequencer console contains the following tabs:</span></span>

-   <span data-ttu-id="b7aee-137">**常规**。</span><span class="sxs-lookup"><span data-stu-id="b7aee-137">**General**.</span></span> <span data-ttu-id="b7aee-138">使用此选项卡可允许 Microsoft 更新在排序期间运行。</span><span class="sxs-lookup"><span data-stu-id="b7aee-138">Use this tab to enable Microsoft Updates to run during sequencing.</span></span> <span data-ttu-id="b7aee-139">选择 "**将包版本追加到文件名**" 以配置序列以向正在排序的虚拟化程序包添加版本号。</span><span class="sxs-lookup"><span data-stu-id="b7aee-139">Select **Append Package Version to Filename** to configure the sequence to add a version number to the virtualized package that is being sequenced.</span></span> <span data-ttu-id="b7aee-140">选择 "**始终信任程序包加速器的源"** 以使用软件包加速器创建虚拟化程序包，而不提示进行授权。</span><span class="sxs-lookup"><span data-stu-id="b7aee-140">Select **Always trust the source of Package Accelerators** to create virtualized packages using a package accelerator without being prompted for authorization.</span></span>

    <span data-ttu-id="b7aee-141">**重要提示** App-v 5.0 不支持使用 App-v 4.6 创建的程序包加速器。</span><span class="sxs-lookup"><span data-stu-id="b7aee-141">**Important** Package Accelerators created using App-V4.6 are not supported by App-V 5.0.</span></span>

     

-   <span data-ttu-id="b7aee-142">**分析项目**。</span><span class="sxs-lookup"><span data-stu-id="b7aee-142">**Parse Items**.</span></span> <span data-ttu-id="b7aee-143">此选项卡显示将在虚拟环境中分析或标记为的关联文件路径位置。</span><span class="sxs-lookup"><span data-stu-id="b7aee-143">This tab displays the associated file path locations that will be parsed or tokenized into in the virtual environment.</span></span> <span data-ttu-id="b7aee-144">令牌对于使用 "**高级编辑**" 中的 "**包文件**" 选项卡添加文件非常有用。</span><span class="sxs-lookup"><span data-stu-id="b7aee-144">Tokens are useful for adding files using the **Package Files** tab in **Advanced Editing**.</span></span>

-   <span data-ttu-id="b7aee-145">**排除项目**。</span><span class="sxs-lookup"><span data-stu-id="b7aee-145">**Exclusion Items**.</span></span> <span data-ttu-id="b7aee-146">使用此选项卡可以指定在排序期间不应监视哪些文件夹和目录。</span><span class="sxs-lookup"><span data-stu-id="b7aee-146">Use this tab to specify which folders and directories should not be monitored during sequencing.</span></span> <span data-ttu-id="b7aee-147">若要添加保存在程序包的本地应用数据文件夹中的本地应用程序数据，请单击 "**新建**"，然后指定位置和关联的**映射类型**。</span><span class="sxs-lookup"><span data-stu-id="b7aee-147">To add local application data that is saved in the Local App Data folder in the package, click **New** and specify the location and the associated **Mapping Type**.</span></span> <span data-ttu-id="b7aee-148">某些程序包需要此选项。</span><span class="sxs-lookup"><span data-stu-id="b7aee-148">This option is required for some packages.</span></span>

<span data-ttu-id="b7aee-149">App-v 5.0 支持包含 Microsoft Windows 服务的应用程序。</span><span class="sxs-lookup"><span data-stu-id="b7aee-149">App-V 5.0 supports applications that include Microsoft Windows Services.</span></span> <span data-ttu-id="b7aee-150">如果应用程序包含 Windows 服务，则该服务将包含在已排序的虚拟程序包中，只要它在由排序器监视时安装。</span><span class="sxs-lookup"><span data-stu-id="b7aee-150">If an application includes a Windows service, the Service will be included in the sequenced virtual package as long as it is installed while being monitored by the sequencer.</span></span> <span data-ttu-id="b7aee-151">如果虚拟应用程序在最初运行时创建 Windows 服务，然后在安装之后，应用程序必须在排序器监视时运行，以便将 Windows 服务添加到程序包。</span><span class="sxs-lookup"><span data-stu-id="b7aee-151">If a virtual application creates a Windows service when it initially runs, then later, after installation, the application must be run while the sequencer is monitoring so that the Windows Service will be added to the package.</span></span> <span data-ttu-id="b7aee-152">仅支持在本地系统帐户下运行的服务。</span><span class="sxs-lookup"><span data-stu-id="b7aee-152">Only Services that run under the Local System account are supported.</span></span> <span data-ttu-id="b7aee-153">在程序包的虚拟环境内运行程序包中的第一个虚拟应用程序之前，将启动为 AutoStart 或延迟的 AutoStart 配置的服务。</span><span class="sxs-lookup"><span data-stu-id="b7aee-153">Services that are configured for AutoStart or Delayed AutoStart are started before the first virtual application in a package runs inside the package’s Virtual Environment.</span></span> <span data-ttu-id="b7aee-154">当程序包内的虚拟应用程序通过 API 调用启动服务时，将启动配置为按需由应用程序启动的 Windows 服务。</span><span class="sxs-lookup"><span data-stu-id="b7aee-154">Windows Services that are configured to be started on demand by an application are started when the virtual application inside the package starts the Service via API call.</span></span>

[<span data-ttu-id="b7aee-155">如何使用 App-V 5.0 对新应用程序进行排序</span><span class="sxs-lookup"><span data-stu-id="b7aee-155">How to Sequence a New Application with App-V 5.0</span></span>](how-to-sequence-a-new-application-with-app-v-50-beta-gb18030.md)

## <a href="" id="---------app-v-5-0-sp2-shell-extension-support"></a> <span data-ttu-id="b7aee-156">App-v 5.0 SP2 外壳扩展支持</span><span class="sxs-lookup"><span data-stu-id="b7aee-156">App-V 5.0SP2 shell extension support</span></span>


<span data-ttu-id="b7aee-157">App-v 5.0 SP2 支持外壳扩展。</span><span class="sxs-lookup"><span data-stu-id="b7aee-157">App-V 5.0SP2 supports shell extensions.</span></span> <span data-ttu-id="b7aee-158">在排序期间，将检测并嵌入在程序包中的 Shell 扩展。</span><span class="sxs-lookup"><span data-stu-id="b7aee-158">Shell extensions will be detected and embedded in the package during sequencing.</span></span>

<span data-ttu-id="b7aee-159">在排序过程中，将自动在程序包中嵌入外壳扩展。</span><span class="sxs-lookup"><span data-stu-id="b7aee-159">Shell extensions are embedded in the package automatically during the sequencing process.</span></span> <span data-ttu-id="b7aee-160">程序包发布后，外壳扩展为用户提供与应用程序本地安装的功能相同的功能。</span><span class="sxs-lookup"><span data-stu-id="b7aee-160">When the package is published, the shell extension gives users the same functionality as if the application were locally installed.</span></span>

**<span data-ttu-id="b7aee-161">使用外壳扩展的要求：</span><span class="sxs-lookup"><span data-stu-id="b7aee-161">Requirements for using shell extensions:</span></span>**

-   <span data-ttu-id="b7aee-162">包含嵌入式外壳扩展的软件包必须全局发布。</span><span class="sxs-lookup"><span data-stu-id="b7aee-162">Packages that contain embedded shell extensions must be published globally.</span></span> <span data-ttu-id="b7aee-163">应用程序不需要在客户端上进行额外的设置或配置即可启用外壳扩展功能。</span><span class="sxs-lookup"><span data-stu-id="b7aee-163">The application requires no additional setup or configuration on the client to enable the shell extension functionality.</span></span>

-   <span data-ttu-id="b7aee-164">应用程序、Sequencer 和 App-v 客户端的 "位数" 必须匹配，否则 shell 扩展将不起作用。</span><span class="sxs-lookup"><span data-stu-id="b7aee-164">The “bitness” of the application, Sequencer, and App-V client must match, or the shell extensions won’t work.</span></span> <span data-ttu-id="b7aee-165">例如：</span><span class="sxs-lookup"><span data-stu-id="b7aee-165">For example:</span></span>

    -   <span data-ttu-id="b7aee-166">该应用程序的版本为64位。</span><span class="sxs-lookup"><span data-stu-id="b7aee-166">The version of the application is 64-bit.</span></span>

    -   <span data-ttu-id="b7aee-167">Sequencer 在64位计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="b7aee-167">The Sequencer is running on a 64-bit computer.</span></span>

    -   <span data-ttu-id="b7aee-168">程序包正在发送到64位 App-v 客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="b7aee-168">The package is being delivered to a 64-bit App-V client computer.</span></span>

<span data-ttu-id="b7aee-169">下表列出了支持的外壳扩展：</span><span class="sxs-lookup"><span data-stu-id="b7aee-169">The following table lists the supported shell extensions:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b7aee-170">函数</span><span class="sxs-lookup"><span data-stu-id="b7aee-170">Handler</span></span></th>
<th align="left"><span data-ttu-id="b7aee-171">描述</span><span class="sxs-lookup"><span data-stu-id="b7aee-171">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b7aee-172">上下文菜单处理程序</span><span class="sxs-lookup"><span data-stu-id="b7aee-172">Context menu handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7aee-173">将菜单项添加到上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="b7aee-173">Adds menu items to the context menu.</span></span> <span data-ttu-id="b7aee-174">在显示上下文菜单之前调用它。</span><span class="sxs-lookup"><span data-stu-id="b7aee-174">It is called before the context menu is displayed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b7aee-175">拖放处理程序</span><span class="sxs-lookup"><span data-stu-id="b7aee-175">Drag-and-drop handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7aee-176">控制操作，单击鼠标右键，然后拖放并修改出现的上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="b7aee-176">Controls the action where right-click, drag and drop and modifies the context menu that appears.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b7aee-177">拖放目标处理程序</span><span class="sxs-lookup"><span data-stu-id="b7aee-177">Drop target handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7aee-178">控制在将数据对象拖放到放置目标（如文件）后执行的操作。</span><span class="sxs-lookup"><span data-stu-id="b7aee-178">Controls the action after a data object is dragged and dropped over a drop target such as a file.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b7aee-179">数据对象处理程序</span><span class="sxs-lookup"><span data-stu-id="b7aee-179">Data object handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7aee-180">控制将文件复制到剪贴板或拖放到放置目标之后的操作。</span><span class="sxs-lookup"><span data-stu-id="b7aee-180">Controls the action after a file is copied to the clipboard or dragged and dropped over a drop target.</span></span> <span data-ttu-id="b7aee-181">它可以向放置目标提供其他剪贴板格式。</span><span class="sxs-lookup"><span data-stu-id="b7aee-181">It can provide additional clipboard formats to the drop target.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b7aee-182">属性表处理程序</span><span class="sxs-lookup"><span data-stu-id="b7aee-182">Property sheet handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7aee-183">将页面替换或添加到对象的 "属性表" 对话框。</span><span class="sxs-lookup"><span data-stu-id="b7aee-183">Replaces or adds pages to the property sheet dialog box of an object.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b7aee-184">提示处理程序</span><span class="sxs-lookup"><span data-stu-id="b7aee-184">Infotip handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7aee-185">允许检索项目的标志和信息提示信息，并在鼠标悬停时将其显示在弹出工具提示内。</span><span class="sxs-lookup"><span data-stu-id="b7aee-185">Allows retrieving flags and infotip information for an item and displaying it inside a pop-up tooltip upon mouse hover.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b7aee-186">列处理程序</span><span class="sxs-lookup"><span data-stu-id="b7aee-186">Column handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7aee-187">允许在 <strong> Windows 资源管理器的 "详细信息" 视图中创建和显示自定义列 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="b7aee-187">Allows creating and displaying custom columns in <strong>Windows Explorer Details view</strong>.</span></span> <span data-ttu-id="b7aee-188">它可用于扩展排序和分组。</span><span class="sxs-lookup"><span data-stu-id="b7aee-188">It can be used to extend sorting and grouping.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b7aee-189">预览处理程序</span><span class="sxs-lookup"><span data-stu-id="b7aee-189">Preview handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7aee-190">启用要在 Windows 资源管理器预览窗格中显示的文件的预览。</span><span class="sxs-lookup"><span data-stu-id="b7aee-190">Enables a preview of a file to be displayed in the Windows Explorer Preview pane.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="b7aee-191">写入时复制（牛）文件扩展名支持</span><span class="sxs-lookup"><span data-stu-id="b7aee-191">Copy on Write (CoW) file extension support</span></span>


<span data-ttu-id="b7aee-192">写入时复制（牛）文件扩展名允许使用 app-v 5.0 动态写入虚拟程序包中包含的特定位置。</span><span class="sxs-lookup"><span data-stu-id="b7aee-192">Copy on write (CoW) file extensions allow App-V 5.0 to dynamically write to specific locations contained in the virtual package while it is being used.</span></span>

<span data-ttu-id="b7aee-193">下表显示了可以存在于 VFS 目录下的虚拟程序包中的文件类型，但无法在运行 App-v 5.0 客户端的计算机上更新。</span><span class="sxs-lookup"><span data-stu-id="b7aee-193">The following table displays the file types that can exist in a virtual package under the VFS directory, but cannot be updated on the computer running the App-V 5.0 client.</span></span> <span data-ttu-id="b7aee-194">可以修改所有其他文件和目录。</span><span class="sxs-lookup"><span data-stu-id="b7aee-194">All other files and directories can be modified.</span></span>

<span data-ttu-id="b7aee-195">。</span><span class="sxs-lookup"><span data-stu-id="b7aee-195">.acm</span></span>

<span data-ttu-id="b7aee-196">asa</span><span class="sxs-lookup"><span data-stu-id="b7aee-196">.asa</span></span>

<span data-ttu-id="b7aee-197">.asp</span><span class="sxs-lookup"><span data-stu-id="b7aee-197">.asp</span></span>

<span data-ttu-id="b7aee-198">.aspx</span><span class="sxs-lookup"><span data-stu-id="b7aee-198">.aspx</span></span>

<span data-ttu-id="b7aee-199">ax</span><span class="sxs-lookup"><span data-stu-id="b7aee-199">.ax</span></span>

<span data-ttu-id="b7aee-200">.bat</span><span class="sxs-lookup"><span data-stu-id="b7aee-200">.bat</span></span>

<span data-ttu-id="b7aee-201">.cer</span><span class="sxs-lookup"><span data-stu-id="b7aee-201">.cer</span></span>

<span data-ttu-id="b7aee-202">.chm</span><span class="sxs-lookup"><span data-stu-id="b7aee-202">.chm</span></span>

<span data-ttu-id="b7aee-203">clb</span><span class="sxs-lookup"><span data-stu-id="b7aee-203">.clb</span></span>

<span data-ttu-id="b7aee-204">.cmd</span><span class="sxs-lookup"><span data-stu-id="b7aee-204">.cmd</span></span>

<span data-ttu-id="b7aee-205">.cnt</span><span class="sxs-lookup"><span data-stu-id="b7aee-205">.cnt</span></span>

<span data-ttu-id="b7aee-206">.cnv</span><span class="sxs-lookup"><span data-stu-id="b7aee-206">.cnv</span></span>

<span data-ttu-id="b7aee-207">.com</span><span class="sxs-lookup"><span data-stu-id="b7aee-207">.com</span></span>

<span data-ttu-id="b7aee-208">.cpl</span><span class="sxs-lookup"><span data-stu-id="b7aee-208">.cpl</span></span>

<span data-ttu-id="b7aee-209">.cpx</span><span class="sxs-lookup"><span data-stu-id="b7aee-209">.cpx</span></span>

<span data-ttu-id="b7aee-210">.crt</span><span class="sxs-lookup"><span data-stu-id="b7aee-210">.crt</span></span>

<span data-ttu-id="b7aee-211">.dll</span><span class="sxs-lookup"><span data-stu-id="b7aee-211">.dll</span></span>

<span data-ttu-id="b7aee-212">.drv</span><span class="sxs-lookup"><span data-stu-id="b7aee-212">.drv</span></span>

<span data-ttu-id="b7aee-213">.exe</span><span class="sxs-lookup"><span data-stu-id="b7aee-213">.exe</span></span>

<span data-ttu-id="b7aee-214">.fon</span><span class="sxs-lookup"><span data-stu-id="b7aee-214">.fon</span></span>

<span data-ttu-id="b7aee-215">.grp</span><span class="sxs-lookup"><span data-stu-id="b7aee-215">.grp</span></span>

<span data-ttu-id="b7aee-216">.hlp</span><span class="sxs-lookup"><span data-stu-id="b7aee-216">.hlp</span></span>

<span data-ttu-id="b7aee-217">.hta</span><span class="sxs-lookup"><span data-stu-id="b7aee-217">.hta</span></span>

<span data-ttu-id="b7aee-218">。 ime</span><span class="sxs-lookup"><span data-stu-id="b7aee-218">.ime</span></span>

<span data-ttu-id="b7aee-219">.inf</span><span class="sxs-lookup"><span data-stu-id="b7aee-219">.inf</span></span>

<span data-ttu-id="b7aee-220">.ins</span><span class="sxs-lookup"><span data-stu-id="b7aee-220">.ins</span></span>

<span data-ttu-id="b7aee-221">.isp</span><span class="sxs-lookup"><span data-stu-id="b7aee-221">.isp</span></span>

<span data-ttu-id="b7aee-222">。其</span><span class="sxs-lookup"><span data-stu-id="b7aee-222">.its</span></span>

<span data-ttu-id="b7aee-223">.js</span><span class="sxs-lookup"><span data-stu-id="b7aee-223">.js</span></span>

<span data-ttu-id="b7aee-224">.jse</span><span class="sxs-lookup"><span data-stu-id="b7aee-224">.jse</span></span>

<span data-ttu-id="b7aee-225">.lnk</span><span class="sxs-lookup"><span data-stu-id="b7aee-225">.lnk</span></span>

<span data-ttu-id="b7aee-226">.msc</span><span class="sxs-lookup"><span data-stu-id="b7aee-226">.msc</span></span>

<span data-ttu-id="b7aee-227">.msi</span><span class="sxs-lookup"><span data-stu-id="b7aee-227">.msi</span></span>

<span data-ttu-id="b7aee-228">.msp</span><span class="sxs-lookup"><span data-stu-id="b7aee-228">.msp</span></span>

<span data-ttu-id="b7aee-229">.mst</span><span class="sxs-lookup"><span data-stu-id="b7aee-229">.mst</span></span>

<span data-ttu-id="b7aee-230">mui</span><span class="sxs-lookup"><span data-stu-id="b7aee-230">.mui</span></span>

<span data-ttu-id="b7aee-231">nls</span><span class="sxs-lookup"><span data-stu-id="b7aee-231">.nls</span></span>

<span data-ttu-id="b7aee-232">.ocx</span><span class="sxs-lookup"><span data-stu-id="b7aee-232">.ocx</span></span>

<span data-ttu-id="b7aee-233">pal</span><span class="sxs-lookup"><span data-stu-id="b7aee-233">.pal</span></span>

<span data-ttu-id="b7aee-234">.pcd</span><span class="sxs-lookup"><span data-stu-id="b7aee-234">.pcd</span></span>

<span data-ttu-id="b7aee-235">.pif</span><span class="sxs-lookup"><span data-stu-id="b7aee-235">.pif</span></span>

<span data-ttu-id="b7aee-236">.reg</span><span class="sxs-lookup"><span data-stu-id="b7aee-236">.reg</span></span>

<span data-ttu-id="b7aee-237">.scf</span><span class="sxs-lookup"><span data-stu-id="b7aee-237">.scf</span></span>

<span data-ttu-id="b7aee-238">.scr</span><span class="sxs-lookup"><span data-stu-id="b7aee-238">.scr</span></span>

<span data-ttu-id="b7aee-239">. sct</span><span class="sxs-lookup"><span data-stu-id="b7aee-239">.sct</span></span>

<span data-ttu-id="b7aee-240">.shb</span><span class="sxs-lookup"><span data-stu-id="b7aee-240">.shb</span></span>

<span data-ttu-id="b7aee-241">.shs</span><span class="sxs-lookup"><span data-stu-id="b7aee-241">.shs</span></span>

<span data-ttu-id="b7aee-242">.sys</span><span class="sxs-lookup"><span data-stu-id="b7aee-242">.sys</span></span>

<span data-ttu-id="b7aee-243">.tlb</span><span class="sxs-lookup"><span data-stu-id="b7aee-243">.tlb</span></span>

<span data-ttu-id="b7aee-244">. tsp</span><span class="sxs-lookup"><span data-stu-id="b7aee-244">.tsp</span></span>

<span data-ttu-id="b7aee-245">.url</span><span class="sxs-lookup"><span data-stu-id="b7aee-245">.url</span></span>

<span data-ttu-id="b7aee-246">.vb</span><span class="sxs-lookup"><span data-stu-id="b7aee-246">.vb</span></span>

<span data-ttu-id="b7aee-247">.vbe</span><span class="sxs-lookup"><span data-stu-id="b7aee-247">.vbe</span></span>

<span data-ttu-id="b7aee-248">.vbs</span><span class="sxs-lookup"><span data-stu-id="b7aee-248">.vbs</span></span>

<span data-ttu-id="b7aee-249">.vsmacros</span><span class="sxs-lookup"><span data-stu-id="b7aee-249">.vsmacros</span></span>

<span data-ttu-id="b7aee-250">.ws</span><span class="sxs-lookup"><span data-stu-id="b7aee-250">.ws</span></span>

<span data-ttu-id="b7aee-251">。 esc</span><span class="sxs-lookup"><span data-stu-id="b7aee-251">.esc</span></span>

<span data-ttu-id="b7aee-252">.wsf</span><span class="sxs-lookup"><span data-stu-id="b7aee-252">.wsf</span></span>

<span data-ttu-id="b7aee-253">.wsh</span><span class="sxs-lookup"><span data-stu-id="b7aee-253">.wsh</span></span>

 

## <span data-ttu-id="b7aee-254">修改现有虚拟应用程序包</span><span class="sxs-lookup"><span data-stu-id="b7aee-254">Modifying an existing virtual application package</span></span>


<span data-ttu-id="b7aee-255">你可以使用 sequencer 修改现有程序包。</span><span class="sxs-lookup"><span data-stu-id="b7aee-255">You can use the sequencer to modify an existing package.</span></span> <span data-ttu-id="b7aee-256">您在其上执行此操作的计算机应该与用于创建该应用程序的计算机的芯片体系结构相匹配。</span><span class="sxs-lookup"><span data-stu-id="b7aee-256">The computer on which you do this should match the chip architecture of the computer you used to create the application.</span></span> <span data-ttu-id="b7aee-257">例如，如果最初使用运行64位操作系统的计算机序列化程序包，则应使用运行64位操作系统的计算机修改程序包。</span><span class="sxs-lookup"><span data-stu-id="b7aee-257">For example, if you initially sequenced a package using a computer running a 64-bit operating system, you should modify the package using a computer running a 64-bit operating system.</span></span>

[<span data-ttu-id="b7aee-258">如何修改现有的虚拟应用程序包</span><span class="sxs-lookup"><span data-stu-id="b7aee-258">How to Modify an Existing Virtual Application Package</span></span>](how-to-modify-an-existing-virtual-application-package-beta.md)

## <span data-ttu-id="b7aee-259">创建项目模板</span><span class="sxs-lookup"><span data-stu-id="b7aee-259">Creating a project template</span></span>


<span data-ttu-id="b7aee-260">Appvt 文件是一个项目模板，可用于保存常用的自定义设置。</span><span class="sxs-lookup"><span data-stu-id="b7aee-260">A .appvt file is a project template that can be used to save commonly applied, customized settings.</span></span> <span data-ttu-id="b7aee-261">然后，您可以更轻松地将这些设置用于将来的 sequencings。</span><span class="sxs-lookup"><span data-stu-id="b7aee-261">You can then more easily use these settings for future sequencings.</span></span>

<span data-ttu-id="b7aee-262">App-v 5.0 项目模板与 App-v 5.0 应用程序加速器不同，因为 App-v 5.0 应用程序加速器是特定于应用程序的，而 app-v 5.0 项目模板可应用于多个应用程序。</span><span class="sxs-lookup"><span data-stu-id="b7aee-262">App-V 5.0 project templates differ from App-V 5.0 Application Accelerators because App-V 5.0 Application Accelerators are application-specific, and App-V 5.0 project templates can be applied to multiple applications.</span></span> <span data-ttu-id="b7aee-263">此外，使用包加速器创建虚拟应用程序包时，不能使用项目模板。</span><span class="sxs-lookup"><span data-stu-id="b7aee-263">Additionally, you cannot use a project template when you use a Package Accelerator to create a virtual application package.</span></span> <span data-ttu-id="b7aee-264">以下常规设置将与 App-v 5.0 项目模板一起保存：</span><span class="sxs-lookup"><span data-stu-id="b7aee-264">The following general settings are saved with an App-V 5.0 project template:</span></span>

<span data-ttu-id="b7aee-265">模板可以指定和存储多个设置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b7aee-265">A template can specify and store multiple settings as follows:</span></span>

-   <span data-ttu-id="b7aee-266">**高级监视选项**。</span><span class="sxs-lookup"><span data-stu-id="b7aee-266">**Advanced Monitoring Options**.</span></span> <span data-ttu-id="b7aee-267">支持在监视期间运行 Microsoft 更新。</span><span class="sxs-lookup"><span data-stu-id="b7aee-267">Enables Microsoft Update to run during monitoring.</span></span> <span data-ttu-id="b7aee-268">保存允许本地交互选项设置</span><span class="sxs-lookup"><span data-stu-id="b7aee-268">Saves allow local interaction option settings</span></span>

-   <span data-ttu-id="b7aee-269">**常规选项**。</span><span class="sxs-lookup"><span data-stu-id="b7aee-269">**General Options**.</span></span> <span data-ttu-id="b7aee-270">启用**Windows 安装程序**，将**程序包版本附加到文件名**。</span><span class="sxs-lookup"><span data-stu-id="b7aee-270">Enables the use of **Windows Installer**, **Append Package Version to Filename**.</span></span>

-   **<span data-ttu-id="b7aee-271">排除项目。</span><span class="sxs-lookup"><span data-stu-id="b7aee-271">Exclusion Items.</span></span>** <span data-ttu-id="b7aee-272">包含 "排除" 模式列表。</span><span class="sxs-lookup"><span data-stu-id="b7aee-272">Contains the Exclusion pattern list.</span></span>

[<span data-ttu-id="b7aee-273">如何创建和使用项目模板</span><span class="sxs-lookup"><span data-stu-id="b7aee-273">How to Create and Use a Project Template</span></span>](how-to-create-and-use-a-project-template.md)

## <span data-ttu-id="b7aee-274">创建程序包加速器</span><span class="sxs-lookup"><span data-stu-id="b7aee-274">Creating a package accelerator</span></span>


<span data-ttu-id="b7aee-275">**注意** 必须使用 App-v 5.0 重新创建使用早期版本的 App-v 创建的程序包加速器。</span><span class="sxs-lookup"><span data-stu-id="b7aee-275">**Note** Package accelerators created using a previous version of App-V must be recreated using App-V 5.0.</span></span>

 

<span data-ttu-id="b7aee-276">你可以使用 app-v 5.0 程序包加速器自动生成新的虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="b7aee-276">You can use App-V 5.0 package accelerators to automatically generate a new virtual application packages.</span></span> <span data-ttu-id="b7aee-277">成功创建程序包加速器后，您可以重复使用和共享程序包加速器。</span><span class="sxs-lookup"><span data-stu-id="b7aee-277">After you have successfully created a package accelerator, you can reuse and share the package accelerator.</span></span>

<span data-ttu-id="b7aee-278">在某些情况下，若要创建程序包加速器，可能需要在运行 sequencer 的计算机上本地安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="b7aee-278">In some situations, to create the package accelerator, you might have to install the application locally on the computer that runs the sequencer.</span></span> <span data-ttu-id="b7aee-279">在这种情况下，你应该首先尝试用安装媒体创建程序包加速器。</span><span class="sxs-lookup"><span data-stu-id="b7aee-279">In such cases, you should first try to create the package accelerator with the installation media.</span></span> <span data-ttu-id="b7aee-280">如果需要多个缺少的文件，则应在运行 sequencer 的计算机本地安装应用程序，然后创建程序包加速器。</span><span class="sxs-lookup"><span data-stu-id="b7aee-280">If multiple missing files are required, you should install the application locally to the computer that runs the sequencer, and then create the package accelerator.</span></span>

<span data-ttu-id="b7aee-281">成功创建程序包加速器后，您可以重复使用和共享程序包加速器。</span><span class="sxs-lookup"><span data-stu-id="b7aee-281">After you have successfully created a Package Accelerator, you can reuse and share the Package Accelerator.</span></span> <span data-ttu-id="b7aee-282">创建 App-v 5.0 程序包加速器是一种高级任务。</span><span class="sxs-lookup"><span data-stu-id="b7aee-282">Creating App-V 5.0 Package Accelerators is an advanced task.</span></span> <span data-ttu-id="b7aee-283">程序包加速器可以包含密码和特定于用户的信息。</span><span class="sxs-lookup"><span data-stu-id="b7aee-283">Package Accelerators can contain password and user-specific information.</span></span> <span data-ttu-id="b7aee-284">因此，你必须将程序包加速器和关联的安装媒体保存在一个安全的位置，并且你应对程序包加速器进行数字签名，以便在应用 V 5.0 程序包加速器应用时可以验证发布者。</span><span class="sxs-lookup"><span data-stu-id="b7aee-284">Therefore you must save Package Accelerators and the associated installation media in a secure location, and you should digitally sign the Package Accelerator after you create it so that the publisher can be verified when the App-V 5.0 Package Accelerator is applied.</span></span>

[<span data-ttu-id="b7aee-285">如何创建包加速器</span><span class="sxs-lookup"><span data-stu-id="b7aee-285">How to Create a Package Accelerator</span></span>](how-to-create-a-package-accelerator.md)

[<span data-ttu-id="b7aee-286">如何使用 App-V 包加速器创建虚拟应用程序包</span><span class="sxs-lookup"><span data-stu-id="b7aee-286">How to Create a Virtual Application Package Using an App-V Package Accelerator</span></span>](how-to-create-a-virtual-application-package-using-an-app-v-package-accelerator.md)

## <span data-ttu-id="b7aee-287">Sequencer 错误报告</span><span class="sxs-lookup"><span data-stu-id="b7aee-287">Sequencer error reporting</span></span>


<span data-ttu-id="b7aee-288">App-v 5.0 Sequencer 可检测排序期间的常见排序问题。</span><span class="sxs-lookup"><span data-stu-id="b7aee-288">The App-V 5.0 Sequencer can detect common sequencing issues during sequencing.</span></span> <span data-ttu-id="b7aee-289">排序向导结束时的 "**安装报告**" 页面显示根据问题的严重程度，归类为**错误**、**警告**和**信息**的诊断消息。</span><span class="sxs-lookup"><span data-stu-id="b7aee-289">The **Installation Report** page at the end of the sequencing wizard displays diagnostic messages categorized into **Errors**, **Warnings**, and **Info** depending on the severity of the issue.</span></span>

<span data-ttu-id="b7aee-290">你还可以使用 Windows 事件查看器查找有关序列化错误的其他信息。</span><span class="sxs-lookup"><span data-stu-id="b7aee-290">You can also find additional information about sequencing errors using the Windows Event Viewer.</span></span>






## <a href="" id="other-resources-for-the-app-v-5-0-sequencer-"></a><span data-ttu-id="b7aee-291">App-v 5.0 sequencer 的其他资源</span><span class="sxs-lookup"><span data-stu-id="b7aee-291">Other resources for the App-V 5.0 sequencer</span></span>


-   [<span data-ttu-id="b7aee-292">App-V 5.0 的操作</span><span class="sxs-lookup"><span data-stu-id="b7aee-292">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

 

 





