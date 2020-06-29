---
title: 使用自定义 UE-V x 模板和 UE-V 2 版生成器
description: 使用自定义 UE-V x 模板和 UE-V 2 版生成器
author: dansimp
ms.assetid: f0bb4920-0132-472c-a564-abf06a884275
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a8d863896e4ccfa92161f8a8f5e2b8955f139872
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802159"
---
# <span data-ttu-id="b0381-103">使用自定义 UE-V x 模板和 UE-V 2 版生成器</span><span class="sxs-lookup"><span data-stu-id="b0381-103">Working with Custom UE-V 2.x Templates and the UE-V 2.x Generator</span></span>


<span data-ttu-id="b0381-104">若要在用户计算机之间同步应用程序设置，Microsoft 用户体验虚拟化（UE-V）2.0、2.1 和 2.1 SP1 使用*设置位置模板*。</span><span class="sxs-lookup"><span data-stu-id="b0381-104">To synchronize application settings between user computers, Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, and 2.1 SP1 use *settings location templates*.</span></span> <span data-ttu-id="b0381-105">某些设置位置模板包含在用户体验虚拟化中。</span><span class="sxs-lookup"><span data-stu-id="b0381-105">Some settings location templates are included in User Experience Virtualization.</span></span> <span data-ttu-id="b0381-106">你还可以使用 UE-V 生成器创建、编辑或验证自定义设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="b0381-106">You can also create, edit, or validate custom settings location templates by using the UE-V Generator.</span></span>

<span data-ttu-id="b0381-107">UE-V 生成器监视 Windows 桌面应用程序以发现和捕获应用程序存储其设置的位置。</span><span class="sxs-lookup"><span data-stu-id="b0381-107">The UE-V Generator monitors Windows desktop applications to discover and capture the locations where the application stores its settings.</span></span> <span data-ttu-id="b0381-108">受监视的应用程序必须是桌面应用程序。</span><span class="sxs-lookup"><span data-stu-id="b0381-108">The application that is monitored must be a desktop application.</span></span> <span data-ttu-id="b0381-109">UE-V 生成器无法为以下应用程序类型创建设置位置模板：</span><span class="sxs-lookup"><span data-stu-id="b0381-109">The UE-V Generator cannot create a settings location template for the following application types:</span></span>

-   <span data-ttu-id="b0381-110">虚拟化应用程序</span><span class="sxs-lookup"><span data-stu-id="b0381-110">Virtualized applications</span></span>

-   <span data-ttu-id="b0381-111">通过终端服务提供的应用程序</span><span class="sxs-lookup"><span data-stu-id="b0381-111">Applications that are offered through Terminal Services</span></span>

-   <span data-ttu-id="b0381-112">Java 应用程序</span><span class="sxs-lookup"><span data-stu-id="b0381-112">Java applications</span></span>

-   <span data-ttu-id="b0381-113">Windows 应用</span><span class="sxs-lookup"><span data-stu-id="b0381-113">Windows apps</span></span>

<span data-ttu-id="b0381-114">本主题 </span><span class="sxs-lookup"><span data-stu-id="b0381-114">This topic</span></span>

<span data-ttu-id="b0381-115">**标准和非标准设置位置：** UE-V 生成器可帮助你识别应用程序在何处搜索应用程序用于存储设置信息的设置文件和注册表设置。</span><span class="sxs-lookup"><span data-stu-id="b0381-115">**Standard and Nonstandard settings locations:** The UE-V Generator helps you identify where applications search for settings files and registry settings that applications use to store settings information.</span></span> <span data-ttu-id="b0381-116">生成器仅发现标准用户可以访问的位置中的设置。</span><span class="sxs-lookup"><span data-stu-id="b0381-116">The generator only discovers settings in locations that are accessible to a standard user.</span></span> <span data-ttu-id="b0381-117">将排除存储在其他位置中的设置。</span><span class="sxs-lookup"><span data-stu-id="b0381-117">Settings that are stored in other locations are excluded.</span></span> <span data-ttu-id="b0381-118">已发现的设置分为两类：**标准**和**非标准**。</span><span class="sxs-lookup"><span data-stu-id="b0381-118">Discovered settings are grouped into two categories: **Standard** and **Non-standard**.</span></span> <span data-ttu-id="b0381-119">建议使用标准设置进行同步，并且 UE-V 可以随时捕获和应用它们。</span><span class="sxs-lookup"><span data-stu-id="b0381-119">Standard settings are recommended for synchronization, and UE-V can readily capture and apply them.</span></span> <span data-ttu-id="b0381-120">非标准设置可能会同步设置，但由于 UE-V 使用的规则，这些设置可能不会持续或 dependably 同步设置。</span><span class="sxs-lookup"><span data-stu-id="b0381-120">Non-standard settings can potentially synchronize settings but, because of the rules that UE-V uses, these settings might not consistently or dependably synchronize settings.</span></span> <span data-ttu-id="b0381-121">这些设置可能依赖于临时文件、导致不可靠的同步，或者可能不起作用。</span><span class="sxs-lookup"><span data-stu-id="b0381-121">These settings might depend on temporary files, result in unreliable synchronization, or might not be useful.</span></span> <span data-ttu-id="b0381-122">这些设置位置显示在 UE-V 生成器中。</span><span class="sxs-lookup"><span data-stu-id="b0381-122">These settings locations are presented in the UE-V Generator.</span></span> <span data-ttu-id="b0381-123">你可以选择逐个案例包括或排除它们。</span><span class="sxs-lookup"><span data-stu-id="b0381-123">You can choose to include or exclude them on a case-by-case basis.</span></span>

<span data-ttu-id="b0381-124">UE-V 生成器将在发现过程中打开应用程序。</span><span class="sxs-lookup"><span data-stu-id="b0381-124">The UE-V Generator opens the application as part of the discovery process.</span></span> <span data-ttu-id="b0381-125">生成器可以捕获以下位置中的设置：</span><span class="sxs-lookup"><span data-stu-id="b0381-125">The generator can capture settings in the following locations:</span></span>

-   <span data-ttu-id="b0381-126">**注册表设置**- **HKEY \ _CURRENT \ _USER**下的注册表位置</span><span class="sxs-lookup"><span data-stu-id="b0381-126">**Registry Settings** – Registry locations under **HKEY\_CURRENT\_USER**</span></span>

-   <span data-ttu-id="b0381-127">**应用程序设置文件**-存储在 \\**用户**\\ [用户名 \] \\ **AppData**  \\  **漫游**中的文件</span><span class="sxs-lookup"><span data-stu-id="b0381-127">**Application Settings Files** – Files that are stored under \\ **Users** \\ \[User name\] \\ **AppData** \\ **Roaming**</span></span>

<span data-ttu-id="b0381-128">UE-V 生成器排除位置，这些位置通常存储应用程序软件文件，但在用户计算机或环境之间不会很好地同步。</span><span class="sxs-lookup"><span data-stu-id="b0381-128">The UE-V Generator excludes locations, which commonly store application software files, but do not synchronize well between user computers or environments.</span></span> <span data-ttu-id="b0381-129">UE-V 生成器将排除这些位置。</span><span class="sxs-lookup"><span data-stu-id="b0381-129">The UE-V Generator excludes these locations.</span></span> <span data-ttu-id="b0381-130">排除的位置如下所示：</span><span class="sxs-lookup"><span data-stu-id="b0381-130">Excluded locations are as follows:</span></span>

-   <span data-ttu-id="b0381-131">HKEY \ _CURRENT 已登录用户无法向其写入值的 _USER 注册表项和文件</span><span class="sxs-lookup"><span data-stu-id="b0381-131">HKEY\_CURRENT\_USER registry keys and files to which the logged-on user cannot write values</span></span>

-   <span data-ttu-id="b0381-132">HKEY \ _CURRENT \ _USER 与 Windows 操作系统的核心功能相关联的注册表项和文件</span><span class="sxs-lookup"><span data-stu-id="b0381-132">HKEY\_CURRENT\_USER registry keys and files that are associated with the core functionality of the Windows operating system</span></span>

-   <span data-ttu-id="b0381-133">位于 HKEY \ _LOCAL \ _MACHINE 配置单元中的所有注册表项，这需要管理员权限，并且可能需要设置用户帐户控制（UAC）协议</span><span class="sxs-lookup"><span data-stu-id="b0381-133">All registry keys that are located in the HKEY\_LOCAL\_MACHINE hive, which requires administrator rights and might require to set a User Account Control (UAC) agreement</span></span>

-   <span data-ttu-id="b0381-134">位于 "Program Files" 目录中的文件，这些文件需要管理员权限，并且可能需要设置 UAC 协议</span><span class="sxs-lookup"><span data-stu-id="b0381-134">Files that are located in Program Files directories, which requires administrator rights and might require to set a UAC agreement</span></span>

-   <span data-ttu-id="b0381-135">位于 Users \\ [User name \] \\ AppData \\ LocalLow 下的文件</span><span class="sxs-lookup"><span data-stu-id="b0381-135">Files that are located under Users \\ \[User name\] \\ AppData \\ LocalLow</span></span>

-   <span data-ttu-id="b0381-136">位于% Systemroot% 中的 Windows 操作系统文件，需要管理员权限，并且可能需要设置 UAC 协议</span><span class="sxs-lookup"><span data-stu-id="b0381-136">Windows operating system files that are located in %Systemroot%, which requires administrator rights and might require to set a UAC agreement</span></span>

<span data-ttu-id="b0381-137">如果在这些位置中存储的注册表项和文件是同步应用程序设置所必需的，则可以在模板创建过程中手动将排除的位置添加到设置位置模板（HKEY \ _LOCAL \ _MACHINE 配置单元中的注册表项除外）。</span><span class="sxs-lookup"><span data-stu-id="b0381-137">If registry keys and files that are stored in these locations are required to synchronize application settings, you can manually add the excluded locations to the settings location template during the template creation process (except for registry entries in the HKEY\_LOCAL\_MACHINE hive).</span></span>

## <a href="" id="edit"></a><span data-ttu-id="b0381-138">通过 UE-V 发电机编辑设置位置模板</span><span class="sxs-lookup"><span data-stu-id="b0381-138">Edit Settings Location Templates with the UE-V Generator</span></span>


<span data-ttu-id="b0381-139">使用 UE-V 生成器编辑设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="b0381-139">Use the UE-V Generator to edit settings location templates.</span></span> <span data-ttu-id="b0381-140">通过使用 UE-V 生成器将修改后的设置添加到模板时，模板内的版本信息将自动更新，以确保在企业中部署的任何现有模板都能正确更新。</span><span class="sxs-lookup"><span data-stu-id="b0381-140">When the revised settings are added to the templates by using the UE-V Generator, the version information within the template is automatically updated to ensure that any existing templates that are deployed in the enterprise are updated correctly.</span></span>

<span data-ttu-id="b0381-141">**注意** 如果您使用 UE-V 2 生成器编辑 UE-V 1.0 模板，该模板将自动转换为 UE-V 2 模板。</span><span class="sxs-lookup"><span data-stu-id="b0381-141">**Note** If you edit a UE-V 1.0 template by using the UE-V 2 Generator, the template is automatically converted to a UE-V 2 template.</span></span> <span data-ttu-id="b0381-142">UE-V 1.0 代理无法再使用已编辑的模板。</span><span class="sxs-lookup"><span data-stu-id="b0381-142">UE-V 1.0 Agents can no longer use the edited template.</span></span>

 

**<span data-ttu-id="b0381-143">使用 UE-V 发生器编辑 UE-V 设置位置模板</span><span class="sxs-lookup"><span data-stu-id="b0381-143">To edit a UE-V settings location template with the UE-V Generator</span></span>**

1.  <span data-ttu-id="b0381-144">依次单击 "**开始**"、"**所有程序**"、" **microsoft 用户体验虚拟化**"，然后单击 " **microsoft 用户体验虚拟化生成器**"。</span><span class="sxs-lookup"><span data-stu-id="b0381-144">Click **Start**, click **All Programs**, click **Microsoft User Experience Virtualization**, and then click **Microsoft User Experience Virtualization Generator**.</span></span>

2.  <span data-ttu-id="b0381-145">单击 "**编辑设置位置模板**"。</span><span class="sxs-lookup"><span data-stu-id="b0381-145">Click **Edit a settings location template**.</span></span>

3.  <span data-ttu-id="b0381-146">在最近使用的模板列表中，选择要编辑的模板。</span><span class="sxs-lookup"><span data-stu-id="b0381-146">In the list of recently used templates, select the template to be edited.</span></span> <span data-ttu-id="b0381-147">或者，单击 "**浏览**" 以搜索设置模板文件。</span><span class="sxs-lookup"><span data-stu-id="b0381-147">Alternatively, click **Browse** to search for the settings template file.</span></span> <span data-ttu-id="b0381-148">单击**下一步**以继续。</span><span class="sxs-lookup"><span data-stu-id="b0381-148">Click **Next** to continue.</span></span>

4.  <span data-ttu-id="b0381-149">查看设置模板的**属性**、**注册表**位置和**文件**位置。</span><span class="sxs-lookup"><span data-stu-id="b0381-149">Review the **Properties**, **Registry** locations, and **Files** locations for the settings template.</span></span> <span data-ttu-id="b0381-150">根据需要进行编辑。</span><span class="sxs-lookup"><span data-stu-id="b0381-150">Edit as required.</span></span>

    -   <span data-ttu-id="b0381-151">在 "**属性**" 选项卡上，您可以查看和编辑以下属性：</span><span class="sxs-lookup"><span data-stu-id="b0381-151">On the **Properties** tab, you can view and edit the following properties:</span></span>

        -   <span data-ttu-id="b0381-152">**应用程序名称**：在程序文件属性的描述中写入的应用程序名称。</span><span class="sxs-lookup"><span data-stu-id="b0381-152">**Application name**: The application name that is written in the description of the program file properties.</span></span>

        -   <span data-ttu-id="b0381-153">**程序名称**：从程序文件属性中获取的程序的名称。</span><span class="sxs-lookup"><span data-stu-id="b0381-153">**Program name**: The name of the program that is taken from the program file properties.</span></span> <span data-ttu-id="b0381-154">此名称通常具有 .exe 文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="b0381-154">This name usually has the .exe file name extension.</span></span>

        -   <span data-ttu-id="b0381-155">**产品版本**：应用程序的 .exe 文件的产品版本号。</span><span class="sxs-lookup"><span data-stu-id="b0381-155">**Product version**: The product version number of the .exe file of the application.</span></span> <span data-ttu-id="b0381-156">此属性与**文件版本**一起可帮助确定设置位置模板面向的应用程序。</span><span class="sxs-lookup"><span data-stu-id="b0381-156">This property, together with the **File version**, helps determine which applications are targeted by the settings location template.</span></span> <span data-ttu-id="b0381-157">此属性接受主版本号。</span><span class="sxs-lookup"><span data-stu-id="b0381-157">This property accepts a major version number.</span></span> <span data-ttu-id="b0381-158">如果此属性为空，则设置位置模板适用于产品的所有版本。</span><span class="sxs-lookup"><span data-stu-id="b0381-158">If this property is empty, then the settings location template applies to all versions of the product.</span></span>

        -   <span data-ttu-id="b0381-159">**文件版本**：应用程序的 .exe 文件的文件版本号。</span><span class="sxs-lookup"><span data-stu-id="b0381-159">**File version**: The file version number of the .exe file of the application.</span></span> <span data-ttu-id="b0381-160">此属性与**产品版本**一起有助于确定设置位置模板面向的应用程序。</span><span class="sxs-lookup"><span data-stu-id="b0381-160">This property, along with the **Product version**, helps determine which applications are targeted by the settings location template.</span></span> <span data-ttu-id="b0381-161">此属性接受主版本号。</span><span class="sxs-lookup"><span data-stu-id="b0381-161">This property accepts a major version number.</span></span> <span data-ttu-id="b0381-162">如果此属性为空，则设置位置模板将应用于该程序的所有版本。</span><span class="sxs-lookup"><span data-stu-id="b0381-162">If this property is empty, the settings location template applies to all versions of the program.</span></span>

        -   <span data-ttu-id="b0381-163">**模板作者名称**（可选）：设置模板作者的名称。</span><span class="sxs-lookup"><span data-stu-id="b0381-163">**Template author name** (optional): The name of the settings template author.</span></span>

        -   <span data-ttu-id="b0381-164">**模板作者电子邮件**（可选）：设置位置模板作者的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="b0381-164">**Template author email** (optional): The email address of the settings location template author.</span></span>

    -   <span data-ttu-id="b0381-165">"**注册表**" 选项卡列出了 "设置位置" 模板中包含的注册表位置的**密钥**和**范围**。</span><span class="sxs-lookup"><span data-stu-id="b0381-165">The **Registry** tab lists the **Key** and **Scope** of the registry locations that are included in the settings location template.</span></span> <span data-ttu-id="b0381-166">可以使用 "**任务**" 下拉菜单编辑注册表位置。</span><span class="sxs-lookup"><span data-stu-id="b0381-166">You can edit the registry locations by using the **Tasks** drop-down menu.</span></span> <span data-ttu-id="b0381-167">在 "任务" 菜单中，你可以添加新密钥、编辑现有密钥的名称或范围、删除密钥，以及浏览注册表中的键所在的注册表。</span><span class="sxs-lookup"><span data-stu-id="b0381-167">In the Tasks menu, you can add new keys, edit the name or scope of existing keys, delete keys, and browse the registry in which the keys are located.</span></span> <span data-ttu-id="b0381-168">定义注册表的范围时，可以使用 "**所有设置**" 范围将所有注册表设置包含在指定键下。</span><span class="sxs-lookup"><span data-stu-id="b0381-168">When you define the scope for the registry, you can use the **All Settings** scope to include all the registry settings under the specified key.</span></span> <span data-ttu-id="b0381-169">使用**所有设置**和**子项**将所有注册表设置包含在指定项、子项和子项设置下。</span><span class="sxs-lookup"><span data-stu-id="b0381-169">Use **All Settings** and **Subkeys** to include all the registry settings under the specified key, subkeys, and subkey settings.</span></span>

    -   <span data-ttu-id="b0381-170">"**文件**" 选项卡列出了 "设置位置" 模板中包含的文件位置的文件路径和文件掩码。</span><span class="sxs-lookup"><span data-stu-id="b0381-170">The **Files** tab lists the file path and file mask of the file locations that are included in the settings location template.</span></span> <span data-ttu-id="b0381-171">可以使用 "**任务**" 下拉菜单编辑文件位置。</span><span class="sxs-lookup"><span data-stu-id="b0381-171">You can edit the file locations by using the **Tasks** drop-down menu.</span></span> <span data-ttu-id="b0381-172">在文件位置的 "**任务**" 菜单中，你可以添加新文件或文件夹位置、编辑现有文件或文件夹的范围、删除文件或文件夹，以及在 Windows 资源管理器中打开所选位置。</span><span class="sxs-lookup"><span data-stu-id="b0381-172">In the **Tasks** menu for file locations, you can add new files or folder locations, edit the scope of existing files or folders, delete files or folders, and open the selected location in Windows Explorer.</span></span> <span data-ttu-id="b0381-173">若要包括指定文件夹中的所有文件，请将文件掩码保留为空。</span><span class="sxs-lookup"><span data-stu-id="b0381-173">To include all files in the specified folder, leave the file mask empty.</span></span>

5.  <span data-ttu-id="b0381-174">单击 "**保存**" 以将更改保存到 "设置位置" 模板。</span><span class="sxs-lookup"><span data-stu-id="b0381-174">Click **Save** to save the changes to the settings location template.</span></span>

6.  <span data-ttu-id="b0381-175">单击 "**关闭**" 以关闭 "设置模板" 向导。</span><span class="sxs-lookup"><span data-stu-id="b0381-175">Click **Close** to close the Settings Template Wizard.</span></span> <span data-ttu-id="b0381-176">退出 UE-V 发生器应用程序。</span><span class="sxs-lookup"><span data-stu-id="b0381-176">Exit the UE-V Generator application.</span></span>

    <span data-ttu-id="b0381-177">编辑应用程序的设置位置模板后，应测试该模板。</span><span class="sxs-lookup"><span data-stu-id="b0381-177">After you edit the settings location template for an application, you should test the template.</span></span> <span data-ttu-id="b0381-178">在实验室环境中部署已修改的设置位置模板，然后再将其放入企业中的 "生产" 中。</span><span class="sxs-lookup"><span data-stu-id="b0381-178">Deploy the revised settings location template in a lab environment before you put it into production in the enterprise.</span></span>

**<span data-ttu-id="b0381-179">如何手动编辑设置位置模板</span><span class="sxs-lookup"><span data-stu-id="b0381-179">How to manually edit a settings location template</span></span>**

1.  <span data-ttu-id="b0381-180">创建设置位置模板 .xml 文件的本地副本。</span><span class="sxs-lookup"><span data-stu-id="b0381-180">Create a local copy of the settings location template .xml file.</span></span> <span data-ttu-id="b0381-181">UE-V 设置位置模板是 .xml 文件，用于标识应用商店设置值的位置。</span><span class="sxs-lookup"><span data-stu-id="b0381-181">UE-V settings location templates are .xml files that identify the locations where application store settings values.</span></span>

    <span data-ttu-id="b0381-182">**注意** 由于模板**ID**的原因，设置位置模板是唯一的。</span><span class="sxs-lookup"><span data-stu-id="b0381-182">**Note** A settings location template is unique because of the template **ID**.</span></span> <span data-ttu-id="b0381-183">如果复制模板并重命名 .xml 文件，则模板注册将失败，因为 UE-V 会读取 .xml 文件中的模板**ID**标记以确定该名称，而不是 .xml 文件的文件名。</span><span class="sxs-lookup"><span data-stu-id="b0381-183">If you copy the template and rename the .xml file, template registration fails because UE-V reads the template **ID** tag in the .xml file to determine the name, not the file name of the .xml file.</span></span> <span data-ttu-id="b0381-184">UE-V 还会读取**版本号**以了解是否有任何更改。</span><span class="sxs-lookup"><span data-stu-id="b0381-184">UE-V also reads the **Version** number to know if anything has changed.</span></span> <span data-ttu-id="b0381-185">如果版本号较高，则 UE-V 会更新模板。</span><span class="sxs-lookup"><span data-stu-id="b0381-185">If the version number is higher, UE-V updates the template.</span></span>

     

2.  <span data-ttu-id="b0381-186">使用 XML 编辑器打开 "设置位置" 模板文件。</span><span class="sxs-lookup"><span data-stu-id="b0381-186">Open the settings location template file with an XML editor.</span></span>

3.  <span data-ttu-id="b0381-187">编辑设置位置模板文件。</span><span class="sxs-lookup"><span data-stu-id="b0381-187">Edit the settings location template file.</span></span> <span data-ttu-id="b0381-188">所有更改都必须符合[SettingsLocationTempate](https://technet.microsoft.com/library/dn763947.aspx)中定义的 ue-v 架构文件。</span><span class="sxs-lookup"><span data-stu-id="b0381-188">All changes must conform to the UE-V schema file that is defined in [SettingsLocationTempate.xsd](https://technet.microsoft.com/library/dn763947.aspx).</span></span> <span data-ttu-id="b0381-189">默认情况下，.xsd 文件的副本位于 \\ProgramData\\Microsoft\\UEV\\Templates. 中。</span><span class="sxs-lookup"><span data-stu-id="b0381-189">By default, a copy of the .xsd file is located in \\ProgramData\\Microsoft\\UEV\\Templates.</span></span>

4.  <span data-ttu-id="b0381-190">递增设置位置模板的**版本号**。</span><span class="sxs-lookup"><span data-stu-id="b0381-190">Increment the **Version** number for the settings location template.</span></span>

5.  <span data-ttu-id="b0381-191">保存设置位置模板文件，然后关闭 "XML 编辑器"。</span><span class="sxs-lookup"><span data-stu-id="b0381-191">Save the settings location template file, and then close the XML editor.</span></span>

6.  <span data-ttu-id="b0381-192">使用 UE-V 生成器验证修改后的设置位置模板文件。</span><span class="sxs-lookup"><span data-stu-id="b0381-192">Validate the modified settings location template file by using the UE-V Generator.</span></span>

7.  <span data-ttu-id="b0381-193">必须先注册已编辑的 UE-V 设置位置模板，然后它才能同步客户端计算机之间的设置。</span><span class="sxs-lookup"><span data-stu-id="b0381-193">You must register the edited UE-V settings location template before it can synchronize settings between client computers.</span></span> <span data-ttu-id="b0381-194">若要注册模板，请打开 Windows PowerShell，然后运行以下 cmdlet： `update-uevtemplate [templatefilename]` 。</span><span class="sxs-lookup"><span data-stu-id="b0381-194">To register a template, open Windows PowerShell, and then run the following cmdlet: `update-uevtemplate [templatefilename]`.</span></span> <span data-ttu-id="b0381-195">然后，你可以将文件复制到设置存储目录。</span><span class="sxs-lookup"><span data-stu-id="b0381-195">You can then copy the file to the settings storage catalog.</span></span> <span data-ttu-id="b0381-196">然后，用户计算机上的 UE-V Agent 将根据计划任务中的计划进行更新。</span><span class="sxs-lookup"><span data-stu-id="b0381-196">The UE-V Agent on users’ computers should then update as scheduled in the scheduled task.</span></span>

## <a href="" id="validate"></a><span data-ttu-id="b0381-197">通过 UE-V 发电机验证设置位置模板</span><span class="sxs-lookup"><span data-stu-id="b0381-197">Validate Settings Location Templates with the UE-V Generator</span></span>


<span data-ttu-id="b0381-198">可以在 XML 编辑器中创建或编辑设置位置模板，而无需使用 UE-V 生成器。</span><span class="sxs-lookup"><span data-stu-id="b0381-198">It is possible to create or edit settings location templates in an XML editor without using the UE-V Generator.</span></span> <span data-ttu-id="b0381-199">如果执行此操作，则可以使用 UE-V 生成器验证新的或修改后的 XML 是否与已针对模板定义的架构相匹配。</span><span class="sxs-lookup"><span data-stu-id="b0381-199">If you do, you can use the UE-V Generator to validate that the new or revised XML matches the schema that has been defined for the template.</span></span>

**<span data-ttu-id="b0381-200">使用 UE-V 发生器验证 UE-V 设置位置模板</span><span class="sxs-lookup"><span data-stu-id="b0381-200">To validate a UE-V settings location template with the UE-V Generator</span></span>**

1.  <span data-ttu-id="b0381-201">单击 "**开始**"，指向 "**所有程序**"，单击 " **microsoft 用户体验虚拟化**"，然后单击 " **microsoft 用户体验虚拟化生成器**"。</span><span class="sxs-lookup"><span data-stu-id="b0381-201">Click **Start**, point to **All Programs**, click **Microsoft User Experience Virtualization**, and then click **Microsoft User Experience Virtualization Generator**.</span></span>

2.  <span data-ttu-id="b0381-202">单击 "**验证设置位置" 模板**。</span><span class="sxs-lookup"><span data-stu-id="b0381-202">Click **Validate a settings location template**.</span></span>

3.  <span data-ttu-id="b0381-203">在最近使用的模板列表中，选择要编辑的模板。</span><span class="sxs-lookup"><span data-stu-id="b0381-203">In the list of recently used templates, select the template to be edited.</span></span> <span data-ttu-id="b0381-204">或者，您也可以**浏览**到设置模板文件。</span><span class="sxs-lookup"><span data-stu-id="b0381-204">Alternatively, you can **Browse** to the settings template file.</span></span> <span data-ttu-id="b0381-205">单击**下一步**以继续。</span><span class="sxs-lookup"><span data-stu-id="b0381-205">Click **Next** to continue.</span></span>

4.  <span data-ttu-id="b0381-206">单击 "**验证**" 以继续。</span><span class="sxs-lookup"><span data-stu-id="b0381-206">Click **Validate** to continue.</span></span>

5.  <span data-ttu-id="b0381-207">单击 "**关闭**" 以关闭 "设置模板" 向导。</span><span class="sxs-lookup"><span data-stu-id="b0381-207">Click **Close** to close the Settings Template Wizard.</span></span> <span data-ttu-id="b0381-208">退出 UE-V 发生器应用程序。</span><span class="sxs-lookup"><span data-stu-id="b0381-208">Exit the UE-V Generator application.</span></span>

    <span data-ttu-id="b0381-209">验证应用程序的设置位置模板后，应测试该模板。</span><span class="sxs-lookup"><span data-stu-id="b0381-209">After you validate the settings location template for an application, you should test the template.</span></span> <span data-ttu-id="b0381-210">在实验室环境中部署模板，然后再将其放入企业的生产环境中。</span><span class="sxs-lookup"><span data-stu-id="b0381-210">Deploy the template in a lab environment before you put it into a production environment in enterprise.</span></span>

## <a href="" id="share"></a><span data-ttu-id="b0381-211">与模板库共享设置位置模板</span><span class="sxs-lookup"><span data-stu-id="b0381-211">Share Settings Location Templates with the Template Gallery</span></span>


<span data-ttu-id="b0381-212">Microsoft 用户体验虚拟化（UE-V）2.0 模板库使管理员可以共享其 UE-V 设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="b0381-212">The Microsoft User Experience Virtualization (UE-V) 2.0 template gallery enables administrators to share their UE-V settings location templates.</span></span> <span data-ttu-id="b0381-213">在库中，你可以上载你的设置位置模板供其他用户使用，并且你可以下载其他用户创建的模板。</span><span class="sxs-lookup"><span data-stu-id="b0381-213">In the gallery, you can upload your settings location templates for other users to use, and you can download templates that other users have created.</span></span> <span data-ttu-id="b0381-214">UE-V 模板库位于 Microsoft TechNet[此处](https://go.microsoft.com/fwlink/p/?LinkId=246589)。</span><span class="sxs-lookup"><span data-stu-id="b0381-214">The UE-V template gallery is located on Microsoft TechNet [here](https://go.microsoft.com/fwlink/p/?LinkId=246589).</span></span>

<span data-ttu-id="b0381-215">在 UE-V 模板库上共享设置位置模板之前，请确保它不包含任何个人或公司信息。</span><span class="sxs-lookup"><span data-stu-id="b0381-215">Before you share a settings location template on the UE-V template gallery, ensure it does not contain any personal or company information.</span></span> <span data-ttu-id="b0381-216">可以使用任何 XML 查看器打开和查看设置位置模板文件的内容。</span><span class="sxs-lookup"><span data-stu-id="b0381-216">You can use any XML viewer to open and view the contents of a settings location template file.</span></span> <span data-ttu-id="b0381-217">在与公司外部的任何人共享模板之前，应查看以下模板值。</span><span class="sxs-lookup"><span data-stu-id="b0381-217">The following template values should be reviewed before you share a template with anyone outside your company.</span></span>

-   <span data-ttu-id="b0381-218">模板作者名称-指定模板作者姓名的常规、非标识名称或从模板中排除此数据。</span><span class="sxs-lookup"><span data-stu-id="b0381-218">Template Author Name – Specify a general, non-identifying name for the template author name or exclude this data from the template.</span></span>

-   <span data-ttu-id="b0381-219">模板作者电子邮件-指定常规、非标识模板作者电子邮件或从模板中排除此数据。</span><span class="sxs-lookup"><span data-stu-id="b0381-219">Template Author Email – Specify a general, non-identifying template author email or exclude this data from the template.</span></span>

<span data-ttu-id="b0381-220">在部署从 UE-V 库下载的任何设置位置模板之前，应首先测试模板以确保应用程序设置在测试环境中正确同步设置。</span><span class="sxs-lookup"><span data-stu-id="b0381-220">Before you deploy any settings location template that you have downloaded from the UE-V gallery, you should first test the template to ensure that the application settings synchronize settings correctly in a test environment.</span></span>






## <span data-ttu-id="b0381-221">相关主题</span><span class="sxs-lookup"><span data-stu-id="b0381-221">Related topics</span></span>


[<span data-ttu-id="b0381-222">管理 UE-V 2. x</span><span class="sxs-lookup"><span data-stu-id="b0381-222">Administering UE-V 2.x</span></span>](administering-ue-v-2x-new-uevv2.md)

[<span data-ttu-id="b0381-223">部署自定义应用程序的 UE-V 2。</span><span class="sxs-lookup"><span data-stu-id="b0381-223">Deploy UE-V 2.x for Custom Applications</span></span>](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)

 

 





