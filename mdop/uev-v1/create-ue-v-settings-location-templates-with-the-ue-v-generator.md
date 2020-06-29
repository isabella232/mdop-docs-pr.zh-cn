---
title: 使用 UE-V 生成器创建 UE-V 设置位置模板
description: 使用 UE-V 生成器创建 UE-V 设置位置模板
author: dansimp
ms.assetid: b8e50e2f-0cc6-4f74-bb48-c471fefdc7d8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ef7e3e5d00a95b9fcfc426207ce04f928cc0ebbb
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804009"
---
# <span data-ttu-id="a72d5-103">使用 UE-V 生成器创建 UE-V 设置位置模板</span><span class="sxs-lookup"><span data-stu-id="a72d5-103">Create UE-V Settings Location Templates with the UE-V Generator</span></span>


<span data-ttu-id="a72d5-104">Microsoft 用户体验虚拟化（UE-V）使用*设置位置模板*在用户计算机之间漫游应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="a72d5-104">Microsoft User Experience Virtualization (UE-V) uses *settings location templates* to roam application settings between user computers.</span></span> <span data-ttu-id="a72d5-105">用户体验虚拟化附带了一些标准设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="a72d5-105">Some standard settings location templates are included with User Experience Virtualization.</span></span> <span data-ttu-id="a72d5-106">你还可以通过 UE-V 生成器创建、编辑或验证自定义设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="a72d5-106">You can also create, edit, or validate custom settings location templates with the UE-V Generator.</span></span>

<span data-ttu-id="a72d5-107">UE-V 生成器监视应用程序以发现和捕获应用程序存储其设置的位置。</span><span class="sxs-lookup"><span data-stu-id="a72d5-107">The UE-V Generator monitors an application to discover and capture the locations where the application stores its settings.</span></span> <span data-ttu-id="a72d5-108">正在监视的应用程序必须是传统的应用程序。</span><span class="sxs-lookup"><span data-stu-id="a72d5-108">The application that is being monitored must be a traditional application.</span></span> <span data-ttu-id="a72d5-109">UE-V 生成器无法从以下应用程序类型创建设置位置模板：</span><span class="sxs-lookup"><span data-stu-id="a72d5-109">The UE-V Generator cannot create a settings location template from the following application types:</span></span>

-   <span data-ttu-id="a72d5-110">虚拟化应用程序</span><span class="sxs-lookup"><span data-stu-id="a72d5-110">Virtualized applications</span></span>

-   <span data-ttu-id="a72d5-111">通过终端服务提供的应用程序</span><span class="sxs-lookup"><span data-stu-id="a72d5-111">Application offered through terminal services</span></span>

-   <span data-ttu-id="a72d5-112">Java 应用程序</span><span class="sxs-lookup"><span data-stu-id="a72d5-112">Java applications</span></span>

-   <span data-ttu-id="a72d5-113">Windows 8 应用程序</span><span class="sxs-lookup"><span data-stu-id="a72d5-113">Windows 8 applications</span></span>

<span data-ttu-id="a72d5-114">**注意** UE-V 模板不能从虚拟化应用程序或终端服务应用程序创建。</span><span class="sxs-lookup"><span data-stu-id="a72d5-114">**Note** UE-V templates cannot be created from virtualized applications or terminal services applications.</span></span> <span data-ttu-id="a72d5-115">但是，可将使用模板同步的设置应用于这些应用程序。</span><span class="sxs-lookup"><span data-stu-id="a72d5-115">However, settings synchronized using the templates can be applied to those applications.</span></span> <span data-ttu-id="a72d5-116">若要创建支持虚拟桌面基础结构（VDI）和终端服务应用程序的模板，请使用 UE-V 生成器打开 Windows Installer 文件（.msi）版本的应用程序。</span><span class="sxs-lookup"><span data-stu-id="a72d5-116">To create templates that support Virtual Desktop Infrastructure (VDI) and terminal services applications, open a Windows Installer File (.msi) version of the application with UE-V Generator.</span></span>

 

**<span data-ttu-id="a72d5-117">排除的位置</span><span class="sxs-lookup"><span data-stu-id="a72d5-117">Excluded Locations</span></span>**

<span data-ttu-id="a72d5-118">发现过程不包括经常存储应用软件文件的位置，这些文件不能在用户计算机或环境之间实现良好漫游。</span><span class="sxs-lookup"><span data-stu-id="a72d5-118">The discovery process excludes locations which commonly store application software files that do not roam well between user computers or environments.</span></span> <span data-ttu-id="a72d5-119">以下内容将被排除：</span><span class="sxs-lookup"><span data-stu-id="a72d5-119">The following are excluded:</span></span>

-   <span data-ttu-id="a72d5-120">HKEY \ _CURRENT 已登录用户无法向其写入值的 _USER 注册表项和文件</span><span class="sxs-lookup"><span data-stu-id="a72d5-120">HKEY\_CURRENT\_USER registry keys and files to which the logged-on user cannot write values</span></span>

-   <span data-ttu-id="a72d5-121">HKEY \ _CURRENT \ _USER 与 Windows 操作系统的核心功能相关联的注册表项和文件</span><span class="sxs-lookup"><span data-stu-id="a72d5-121">HKEY\_CURRENT\_USER registry keys and files associated with the core functionality of the Windows operating system</span></span>

-   <span data-ttu-id="a72d5-122">位于 HKEY \ _LOCAL \ _MACHINE 配置单元中的所有注册表项</span><span class="sxs-lookup"><span data-stu-id="a72d5-122">All registry keys located in the HKEY\_LOCAL\_MACHINE hive</span></span>

-   <span data-ttu-id="a72d5-123">位于程序文件目录中的文件</span><span class="sxs-lookup"><span data-stu-id="a72d5-123">Files located in Program Files directories</span></span>

-   <span data-ttu-id="a72d5-124">位于用户 \\ [用户名 \] \\ AppData \\ LocalLow 中的文件</span><span class="sxs-lookup"><span data-stu-id="a72d5-124">Files located in Users \\ \[User name\] \\ AppData \\ LocalLow</span></span>

-   <span data-ttu-id="a72d5-125">位于% systemroot% 中的 Windows 操作系统文件</span><span class="sxs-lookup"><span data-stu-id="a72d5-125">Windows operating system files located in %systemroot%</span></span>

<span data-ttu-id="a72d5-126">如果需要在这些排除位置存储的注册表项和文件才能漫游应用程序设置，管理员可以在模板创建过程中手动将位置添加到设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="a72d5-126">If registry keys and files stored in these excluded locations are required in order to roam application settings, administrators can manually add the locations to the settings location template during the template creation process.</span></span>

## <span data-ttu-id="a72d5-127">创建 UE-V 模板</span><span class="sxs-lookup"><span data-stu-id="a72d5-127">Create UE-V templates</span></span>


<span data-ttu-id="a72d5-128">使用 UE-V 生成器为业务线应用程序或其他应用程序创建设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="a72d5-128">Use the UE-V Generator to create settings location templates for line-of-business applications or other applications.</span></span> <span data-ttu-id="a72d5-129">创建应用程序的模板后，你可以将模板部署到计算机，以便用户可以漫游该应用程序的设置。</span><span class="sxs-lookup"><span data-stu-id="a72d5-129">After the template for an application is created, you can deploy the template to computers so users can roam the settings for that application.</span></span>

**<span data-ttu-id="a72d5-130">使用 UE-V 生成器创建 UE-V 设置位置模板</span><span class="sxs-lookup"><span data-stu-id="a72d5-130">To create a UE-V settings location template with the UE-V Generator</span></span>**

1.  <span data-ttu-id="a72d5-131">依次单击 "**开始**"、"**所有程序**"、" **microsoft 用户体验虚拟化**"，然后单击 " **microsoft 用户体验虚拟化生成器**"。</span><span class="sxs-lookup"><span data-stu-id="a72d5-131">Click **Start**, click **All Programs**, click **Microsoft User Experience Virtualization**, and then click **Microsoft User Experience Virtualization Generator**.</span></span>

2.  <span data-ttu-id="a72d5-132">单击 "**创建设置位置模板**"。</span><span class="sxs-lookup"><span data-stu-id="a72d5-132">Click **Create a settings location template**.</span></span>

3.  <span data-ttu-id="a72d5-133">指定应用程序。</span><span class="sxs-lookup"><span data-stu-id="a72d5-133">Specify the application.</span></span> <span data-ttu-id="a72d5-134">通过浏览找到要为其创建设置位置模板的应用程序（.exe）或应用程序快捷方式（.lnk）的文件路径。</span><span class="sxs-lookup"><span data-stu-id="a72d5-134">Browse to the file path of the application (.exe) or the application shortcut (.lnk) for which you want to create a settings location template.</span></span> <span data-ttu-id="a72d5-135">指定命令行参数（如果有）和工作目录（如果有）。</span><span class="sxs-lookup"><span data-stu-id="a72d5-135">Specify the command line arguments, if any, and working directory, if any.</span></span> <span data-ttu-id="a72d5-136">单击**下一步**以继续。</span><span class="sxs-lookup"><span data-stu-id="a72d5-136">Click **Next** to continue.</span></span>

    <span data-ttu-id="a72d5-137">**注意** 在应用程序启动之前，系统将显示 "**用户帐户控制**" 提示。</span><span class="sxs-lookup"><span data-stu-id="a72d5-137">**Note** Before the application is started, the system displays a prompt for **User Account Control**.</span></span> <span data-ttu-id="a72d5-138">需要权限来监视应用程序用于存储设置的注册表和文件位置。</span><span class="sxs-lookup"><span data-stu-id="a72d5-138">Permission is required to monitor the registry and file locations that the application uses to store settings.</span></span>

     

4.  <span data-ttu-id="a72d5-139">应用程序启动后，关闭该应用程序。</span><span class="sxs-lookup"><span data-stu-id="a72d5-139">After the application starts, close the application.</span></span> <span data-ttu-id="a72d5-140">UE-V 生成器记录应用程序存储其设置的位置。</span><span class="sxs-lookup"><span data-stu-id="a72d5-140">The UE-V Generator records the locations where the application stores its settings.</span></span>

5.  <span data-ttu-id="a72d5-141">过程完成后，单击 "**下一步**" 以继续。</span><span class="sxs-lookup"><span data-stu-id="a72d5-141">After the process is complete, click **Next** to continue.</span></span>

6.  <span data-ttu-id="a72d5-142">查看并选中相应注册表设置位置和设置文件位置旁边的复选框，以便为此应用程序漫游。</span><span class="sxs-lookup"><span data-stu-id="a72d5-142">Review and select the check boxes next to the appropriate registry settings locations and settings file locations to roam for this application.</span></span> <span data-ttu-id="a72d5-143">该列表包含设置位置的以下两个类别：</span><span class="sxs-lookup"><span data-stu-id="a72d5-143">The list includes the following two categories for settings locations:</span></span>

    -   <span data-ttu-id="a72d5-144">**标准**：存储在注册表中的应用程序设置，这些设置存储在 HKEY \ _CURRENT \ _USER 键或在 \\**用户**\\ [用户名 \] \ **AppData**漫游] 下的文件文件夹中  \\  **Roaming**。</span><span class="sxs-lookup"><span data-stu-id="a72d5-144">**Standard**: Application settings that are stored in the registry under the HKEY\_CURRENT\_USER keys or in the file folders under \\ **Users** \\ \[User name\] \\ **AppData** \\ **Roaming**.</span></span> <span data-ttu-id="a72d5-145">UE-V 生成器默认包括这些设置。</span><span class="sxs-lookup"><span data-stu-id="a72d5-145">The UE-V Generator includes these settings by default.</span></span>

    -   <span data-ttu-id="a72d5-146">**非标准**：存储在设置数据存储的最佳做法中指定的位置之外的应用程序设置（可选）。</span><span class="sxs-lookup"><span data-stu-id="a72d5-146">**Nonstandard**: Application settings that are stored outside the locations specified in the best practices for settings data storage (optional).</span></span> <span data-ttu-id="a72d5-147">其中包括 " **Users** \\ [用户名 \] \" \ " **AppData**  \\  **本地**的文件和文件夹"。</span><span class="sxs-lookup"><span data-stu-id="a72d5-147">These include files and folders under **Users** \\ \[User name\] \\ **AppData** \\ **Local**.</span></span> <span data-ttu-id="a72d5-148">查看这些位置以确定是否将它们包含在 "设置位置" 模板中。</span><span class="sxs-lookup"><span data-stu-id="a72d5-148">Review these locations to determine whether to include them in the settings location template.</span></span> <span data-ttu-id="a72d5-149">选中 "位置" 复选框以包括它们。</span><span class="sxs-lookup"><span data-stu-id="a72d5-149">Select the locations check boxes to include them.</span></span>

    <span data-ttu-id="a72d5-150">单击**下一步**以继续。</span><span class="sxs-lookup"><span data-stu-id="a72d5-150">Click **Next** to continue.</span></span>

7.  <span data-ttu-id="a72d5-151">查看和编辑设置位置模板的任何**属性**、**注册表**位置和**文件**位置。</span><span class="sxs-lookup"><span data-stu-id="a72d5-151">Review and edit any **Properties**, **Registry** locations, and **Files** locations for the settings location template.</span></span>

    -   <span data-ttu-id="a72d5-152">在 "**属性**" 选项卡上编辑以下属性：</span><span class="sxs-lookup"><span data-stu-id="a72d5-152">Edit the following properties on the **Properties** tab:</span></span>

        -   <span data-ttu-id="a72d5-153">**应用程序名称**：写入程序文件属性说明中的应用程序名称。</span><span class="sxs-lookup"><span data-stu-id="a72d5-153">**Application Name**: The application name written in the description of the program files properties.</span></span>

        -   <span data-ttu-id="a72d5-154">**程序名称**：从程序文件属性中获取的程序的名称。</span><span class="sxs-lookup"><span data-stu-id="a72d5-154">**Program name**: The name of the program taken from the program file properties.</span></span> <span data-ttu-id="a72d5-155">此名称通常具有 .exe 扩展名。</span><span class="sxs-lookup"><span data-stu-id="a72d5-155">This name usually has the .exe extension.</span></span>

        -   <span data-ttu-id="a72d5-156">**产品版本**：应用程序的 .exe 文件的产品版本号。</span><span class="sxs-lookup"><span data-stu-id="a72d5-156">**Product version**: The product version number of the .exe file of the application.</span></span> <span data-ttu-id="a72d5-157">此属性与文件版本结合使用，可帮助确定设置位置模板面向的应用程序。</span><span class="sxs-lookup"><span data-stu-id="a72d5-157">This property, in conjunction with the File version, helps determine which applications are targeted by the settings location template.</span></span> <span data-ttu-id="a72d5-158">此属性接受主版本号。</span><span class="sxs-lookup"><span data-stu-id="a72d5-158">This property accepts a major version number.</span></span> <span data-ttu-id="a72d5-159">如果此属性为空，则设置位置模板将应用于产品的所有版本。</span><span class="sxs-lookup"><span data-stu-id="a72d5-159">If this property is empty, the settings location template will apply to all versions of the product.</span></span>

        -   <span data-ttu-id="a72d5-160">**文件版本**：应用程序 the.exe 文件的文件版本编号。</span><span class="sxs-lookup"><span data-stu-id="a72d5-160">**File version**: The file version number of the.exe file of the application.</span></span> <span data-ttu-id="a72d5-161">此属性与产品版本结合使用，可帮助确定设置位置模板面向的应用程序。</span><span class="sxs-lookup"><span data-stu-id="a72d5-161">This property, in conjunction with the Product version, helps determine which applications are targeted by the settings location template.</span></span> <span data-ttu-id="a72d5-162">此属性接受主版本号。</span><span class="sxs-lookup"><span data-stu-id="a72d5-162">This property accepts a major version number.</span></span> <span data-ttu-id="a72d5-163">如果此属性为空，则设置位置模板将应用于该程序的所有版本。</span><span class="sxs-lookup"><span data-stu-id="a72d5-163">If this property is empty, the settings location template will apply to all versions of the program.</span></span>

        -   <span data-ttu-id="a72d5-164">**模板作者名称**（可选）：设置位置模板作者的名称。</span><span class="sxs-lookup"><span data-stu-id="a72d5-164">**Template author name** (optional): The name of the settings location template author.</span></span>

        -   <span data-ttu-id="a72d5-165">**模板作者电子邮件**（可选）：设置位置模板作者的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="a72d5-165">**Template author email** (optional): The email address of the settings location template author.</span></span>

    -   <span data-ttu-id="a72d5-166">"**注册表**" 选项卡列出了 "设置位置" 模板中包含的注册表位置的**密钥**和**范围**。</span><span class="sxs-lookup"><span data-stu-id="a72d5-166">The **Registry** tab lists the **Key** and **Scope** of the registry locations that are included in the settings location template.</span></span> <span data-ttu-id="a72d5-167">通过使用 "**任务**" 下拉菜单编辑注册表位置。</span><span class="sxs-lookup"><span data-stu-id="a72d5-167">Edit the registry locations by use of the **Tasks** drop-down menu.</span></span> <span data-ttu-id="a72d5-168">任务包括添加新密钥、编辑现有密钥的名称或范围、删除密钥以及浏览注册表项所在的位置。</span><span class="sxs-lookup"><span data-stu-id="a72d5-168">Tasks include adding new keys, editing the name or scope of existing keys, deleting keys, and browsing the registry where the keys are located.</span></span> <span data-ttu-id="a72d5-169">使用 "**所有设置**" 范围将所有注册表设置包含在指定的键下。</span><span class="sxs-lookup"><span data-stu-id="a72d5-169">Use the **All Settings** scope to include all the registry settings under the specified key.</span></span> <span data-ttu-id="a72d5-170">使用 "**所有设置" 和 "子项**"，将所有注册表设置包含在指定的项、子项和子项设置下。</span><span class="sxs-lookup"><span data-stu-id="a72d5-170">Use the **All Settings and Subkeys** to include all the registry settings under the specified key, subkeys, and subkey settings.</span></span>

    -   <span data-ttu-id="a72d5-171">"**文件**" 选项卡列出了 "设置位置" 模板中包含的文件位置的文件路径和文件掩码。</span><span class="sxs-lookup"><span data-stu-id="a72d5-171">The **Files** tab lists the file path and file mask of the file locations included in the settings location template.</span></span> <span data-ttu-id="a72d5-172">通过使用 "**任务**" 下拉菜单来编辑文件位置。</span><span class="sxs-lookup"><span data-stu-id="a72d5-172">Edit the file locations by use of the **Tasks** drop-down menu.</span></span> <span data-ttu-id="a72d5-173">文件位置的任务包括添加新文件或文件夹位置、编辑现有文件或文件夹的范围、删除文件或文件夹以及在 Windows 资源管理器中打开所选位置。</span><span class="sxs-lookup"><span data-stu-id="a72d5-173">Tasks for file locations include adding new files or folder locations, editing the scope of existing files or folders, deleting files or folders, and opening the selected location in Windows Explorer.</span></span> <span data-ttu-id="a72d5-174">将文件掩码保留为空，以包括指定文件夹中的所有文件。</span><span class="sxs-lookup"><span data-stu-id="a72d5-174">Leave the file mask empty to include all files in the specified folder.</span></span>

8.  <span data-ttu-id="a72d5-175">单击 "**创建**" 并将设置位置模板保存在计算机上。</span><span class="sxs-lookup"><span data-stu-id="a72d5-175">Click **Create** and save the settings location template on the computer.</span></span>

9.  <span data-ttu-id="a72d5-176">单击 "**关闭**" 以关闭 "设置模板" 向导。</span><span class="sxs-lookup"><span data-stu-id="a72d5-176">Click **Close** to close the Settings Template Wizard.</span></span> <span data-ttu-id="a72d5-177">退出 UE-V 发生器应用程序。</span><span class="sxs-lookup"><span data-stu-id="a72d5-177">Exit the UE-V Generator application.</span></span>

    <span data-ttu-id="a72d5-178">为应用程序创建设置位置模板后，应测试该模板。</span><span class="sxs-lookup"><span data-stu-id="a72d5-178">After you have created the settings location template for an application, you should test the template.</span></span> <span data-ttu-id="a72d5-179">在实验室环境中部署模板，然后再将其放入企业中的生产环境中。</span><span class="sxs-lookup"><span data-stu-id="a72d5-179">Deploy the template in a lab environment before putting it into production in the enterprise.</span></span>

## <span data-ttu-id="a72d5-180">相关主题</span><span class="sxs-lookup"><span data-stu-id="a72d5-180">Related topics</span></span>


[<span data-ttu-id="a72d5-181">使用自定义 UE-V 模板和 UE-V 生成器</span><span class="sxs-lookup"><span data-stu-id="a72d5-181">Working with Custom UE-V Templates and the UE-V Generator</span></span>](working-with-custom-ue-v-templates-and-the-ue-v-generator.md)

[<span data-ttu-id="a72d5-182">UE-V 1.0 的操作</span><span class="sxs-lookup"><span data-stu-id="a72d5-182">Operations for UE-V 1.0</span></span>](operations-for-ue-v-10.md)

 

 





