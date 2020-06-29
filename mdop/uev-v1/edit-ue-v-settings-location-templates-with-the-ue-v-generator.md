---
title: 使用 UE-V 生成器编辑 UE-V 设置位置模板
description: 使用 UE-V 生成器编辑 UE-V 设置位置模板
author: dansimp
ms.assetid: da78f9c8-1624-4111-8c96-79db7224bd0b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7b90cd58761e6ac40c089f3afeade3c445a52ea6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804103"
---
# <span data-ttu-id="9cc6a-103">使用 UE-V 生成器编辑 UE-V 设置位置模板</span><span class="sxs-lookup"><span data-stu-id="9cc6a-103">Edit UE-V Settings Location Templates with the UE-V Generator</span></span>


<span data-ttu-id="9cc6a-104">使用 Microsoft 用户体验虚拟化（UE-V）生成器编辑设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="9cc6a-104">Use the Microsoft User Experience Virtualization (UE-V) Generator to edit settings location templates.</span></span> <span data-ttu-id="9cc6a-105">使用 UE-V 生成器将修改后的设置添加到模板时，模板内的版本信息将自动更新，以确保在企业中部署的任何现有模板都能正确更新。</span><span class="sxs-lookup"><span data-stu-id="9cc6a-105">When the revised settings are added to the templates using the UE-V Generator, the version information within the template is automatically updated to ensure that any existing templates deployed in the enterprise are updated correctly.</span></span>

**<span data-ttu-id="9cc6a-106">如何使用 UE-V 生成器编辑 UE-V 设置位置模板</span><span class="sxs-lookup"><span data-stu-id="9cc6a-106">How to edit a UE-V settings location template with the UE-V Generator</span></span>**

1.  <span data-ttu-id="9cc6a-107">依次单击 "**开始**"、"**所有程序**"、" **microsoft 用户体验虚拟化**"，然后单击 " **microsoft 用户体验虚拟化生成器**"。</span><span class="sxs-lookup"><span data-stu-id="9cc6a-107">Click **Start**, click **All Programs**, click **Microsoft User Experience Virtualization**, and then click **Microsoft User Experience Virtualization Generator**.</span></span>

2.  <span data-ttu-id="9cc6a-108">单击 "**编辑设置位置模板**"。</span><span class="sxs-lookup"><span data-stu-id="9cc6a-108">Click **Edit a settings location template**.</span></span>

3.  <span data-ttu-id="9cc6a-109">在最近使用的模板列表中，选择要编辑的模板。</span><span class="sxs-lookup"><span data-stu-id="9cc6a-109">In the list of recently used templates, select the template to be edited.</span></span> <span data-ttu-id="9cc6a-110">或者，通过**浏览找到**设置模板文件。</span><span class="sxs-lookup"><span data-stu-id="9cc6a-110">Alternatively, **Browse** to the settings template file.</span></span> <span data-ttu-id="9cc6a-111">单击**下一步**以继续。</span><span class="sxs-lookup"><span data-stu-id="9cc6a-111">Click **Next** to continue.</span></span>

4.  <span data-ttu-id="9cc6a-112">查看设置模板的**属性**、**注册表**位置和**文件**位置。</span><span class="sxs-lookup"><span data-stu-id="9cc6a-112">Review the **Properties**, **Registry** locations, and **Files** locations for the settings template.</span></span> <span data-ttu-id="9cc6a-113">根据需要进行编辑。</span><span class="sxs-lookup"><span data-stu-id="9cc6a-113">Edit as needed.</span></span>

    -   <span data-ttu-id="9cc6a-114">"**属性**" 选项卡允许你查看和编辑以下属性：</span><span class="sxs-lookup"><span data-stu-id="9cc6a-114">The **Properties** tab allows you to view and edit the following properties:</span></span>

        -   <span data-ttu-id="9cc6a-115">**应用程序名称**：写入程序文件属性说明中的应用程序名称。</span><span class="sxs-lookup"><span data-stu-id="9cc6a-115">**Application name**: The application name written in the description of the program file properties.</span></span>

        -   <span data-ttu-id="9cc6a-116">**程序名称**：从程序文件属性中获取的程序的名称。</span><span class="sxs-lookup"><span data-stu-id="9cc6a-116">**Program name**: The name of the program taken from the program file properties.</span></span> <span data-ttu-id="9cc6a-117">此名称通常具有 .exe 扩展名。</span><span class="sxs-lookup"><span data-stu-id="9cc6a-117">This name usually has the .exe extension.</span></span>

        -   <span data-ttu-id="9cc6a-118">**产品版本**：应用程序的 .exe 文件的产品版本号。</span><span class="sxs-lookup"><span data-stu-id="9cc6a-118">**Product version**: The product version number of the .exe file of the application.</span></span> <span data-ttu-id="9cc6a-119">此属性与**文件版本**一起可帮助确定设置位置模板面向的应用程序。</span><span class="sxs-lookup"><span data-stu-id="9cc6a-119">This property, together with the **File version**, helps determine which applications are targeted by the settings location template.</span></span> <span data-ttu-id="9cc6a-120">此属性接受主版本号。</span><span class="sxs-lookup"><span data-stu-id="9cc6a-120">This property accepts a major version number.</span></span> <span data-ttu-id="9cc6a-121">如果此属性为空，则设置位置模板将应用于产品的所有版本。</span><span class="sxs-lookup"><span data-stu-id="9cc6a-121">If this property is empty, then the settings location template will apply to all versions of the product.</span></span>

        -   <span data-ttu-id="9cc6a-122">**文件版本**：应用程序 the.exe 文件的文件版本编号。</span><span class="sxs-lookup"><span data-stu-id="9cc6a-122">**File version**: The file version number of the.exe file of the application.</span></span> <span data-ttu-id="9cc6a-123">此属性与**产品版本**一起有助于确定设置位置模板面向的应用程序。</span><span class="sxs-lookup"><span data-stu-id="9cc6a-123">This property, along with the **Product version**, helps determine which applications are targeted by the settings location template.</span></span> <span data-ttu-id="9cc6a-124">此属性接受主版本号。</span><span class="sxs-lookup"><span data-stu-id="9cc6a-124">This property accepts a major version number.</span></span> <span data-ttu-id="9cc6a-125">如果此属性为空，则设置位置模板将应用于该程序的所有版本。</span><span class="sxs-lookup"><span data-stu-id="9cc6a-125">If this property is empty, the settings location template will apply to all versions of the program.</span></span>

        -   <span data-ttu-id="9cc6a-126">**模板作者名称**（可选）：设置模板作者的名称。</span><span class="sxs-lookup"><span data-stu-id="9cc6a-126">**Template author name** (optional): The name of the settings template author.</span></span>

        -   <span data-ttu-id="9cc6a-127">**模板作者电子邮件**（可选）：设置位置模板作者的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="9cc6a-127">**Template author email** (optional): The email address of the settings location template author.</span></span>

    -   <span data-ttu-id="9cc6a-128">"**注册表**" 选项卡列出了 "设置位置" 模板中包含的注册表位置的**密钥**和**范围**。</span><span class="sxs-lookup"><span data-stu-id="9cc6a-128">The **Registry** tab lists the **Key** and **Scope** of the registry locations that are included in the settings location template.</span></span> <span data-ttu-id="9cc6a-129">可通过使用 "**任务**" 下拉菜单来编辑注册表位置。</span><span class="sxs-lookup"><span data-stu-id="9cc6a-129">You can edit the registry locations by use of the **Tasks** drop-down menu.</span></span> <span data-ttu-id="9cc6a-130">任务包括添加新密钥、编辑现有密钥的名称或作用域、删除密钥和浏览注册表（位于其中的注册表项）。</span><span class="sxs-lookup"><span data-stu-id="9cc6a-130">Tasks include adding new keys, editing the name or scope of existing keys, deleting keys, and browsing the registry in which the keys are located.</span></span> <span data-ttu-id="9cc6a-131">定义注册表的范围时，可以使用 "**所有设置**" 范围将所有注册表设置包含在指定键下。</span><span class="sxs-lookup"><span data-stu-id="9cc6a-131">When you define the scope for the registry, you can use the **All Settings** scope to include all the registry settings under the specified key.</span></span> <span data-ttu-id="9cc6a-132">使用**所有设置**和**子项**将所有注册表设置包含在指定项、子项和子项设置下。</span><span class="sxs-lookup"><span data-stu-id="9cc6a-132">Use **All Settings** and **Subkeys** to include all the registry settings under the specified key, subkeys, and subkey settings.</span></span>

    -   <span data-ttu-id="9cc6a-133">"**文件**" 选项卡列出了 "设置位置" 模板中包含的文件位置的文件路径和文件掩码。</span><span class="sxs-lookup"><span data-stu-id="9cc6a-133">The **Files** tab lists the file path and file mask of the file locations included in the settings location template.</span></span> <span data-ttu-id="9cc6a-134">可以通过使用 "**任务**" 下拉菜单来编辑文件位置。</span><span class="sxs-lookup"><span data-stu-id="9cc6a-134">You can edit the file locations by use of the **Tasks** drop-down menu.</span></span> <span data-ttu-id="9cc6a-135">文件位置的任务包括添加新文件或文件夹位置、编辑现有文件或文件夹的范围、删除文件或文件夹以及在 Windows 资源管理器中打开所选位置。</span><span class="sxs-lookup"><span data-stu-id="9cc6a-135">Tasks for file locations include adding new files or folder locations, editing the scope of existing files or folders, deleting files or folders, and opening the selected location in Windows Explorer.</span></span> <span data-ttu-id="9cc6a-136">若要包括指定文件夹中的所有文件，请将文件掩码保留为空。</span><span class="sxs-lookup"><span data-stu-id="9cc6a-136">To include all files in the specified folder, leave the file mask empty.</span></span>

5.  <span data-ttu-id="9cc6a-137">单击 "**保存**" 以将更改保存到 "设置位置" 模板。</span><span class="sxs-lookup"><span data-stu-id="9cc6a-137">Click **Save** to save the changes to the settings location template.</span></span>

6.  <span data-ttu-id="9cc6a-138">单击 "**关闭**" 以关闭 "设置模板" 向导。</span><span class="sxs-lookup"><span data-stu-id="9cc6a-138">Click **Close** to close the Settings Template Wizard.</span></span> <span data-ttu-id="9cc6a-139">退出 UE-V 发生器应用程序。</span><span class="sxs-lookup"><span data-stu-id="9cc6a-139">Exit the UE-V Generator application.</span></span>

    <span data-ttu-id="9cc6a-140">在编辑应用程序的设置位置模板后，应测试该模板。</span><span class="sxs-lookup"><span data-stu-id="9cc6a-140">After editing the settings location template for an application, you should test the template.</span></span> <span data-ttu-id="9cc6a-141">在实验室环境中部署已修改的设置位置模板，然后再将其置于企业中的生产环境中。</span><span class="sxs-lookup"><span data-stu-id="9cc6a-141">Deploy the revised settings location template in a lab environment before putting it into production in the enterprise.</span></span>

**<span data-ttu-id="9cc6a-142">如何手动编辑设置位置模板</span><span class="sxs-lookup"><span data-stu-id="9cc6a-142">How to manually edit a settings location template</span></span>**

1.  <span data-ttu-id="9cc6a-143">创建设置位置模板（.xml 文件）的本地副本。</span><span class="sxs-lookup"><span data-stu-id="9cc6a-143">Create a local copy of the settings location template (.xml file).</span></span> <span data-ttu-id="9cc6a-144">UE-V 设置位置模板是 .xml 文件，用于标识应用商店设置值的位置。</span><span class="sxs-lookup"><span data-stu-id="9cc6a-144">UE-V settings location templates are .xml files identifying the locations where application store settings values.</span></span>

2.  <span data-ttu-id="9cc6a-145">使用 XML 编辑器打开 "设置位置" 模板文件。</span><span class="sxs-lookup"><span data-stu-id="9cc6a-145">Open the settings location template file with an XML editor.</span></span>

3.  <span data-ttu-id="9cc6a-146">编辑设置位置模板文件。</span><span class="sxs-lookup"><span data-stu-id="9cc6a-146">Edit the settings location template file.</span></span> <span data-ttu-id="9cc6a-147">所有更改都必须符合 SettingsLocationTempate 中定义的 UE-V 架构文件。</span><span class="sxs-lookup"><span data-stu-id="9cc6a-147">All changes must conform to the UE-V schema file defined in SettingsLocationTempate.xsd.</span></span> <span data-ttu-id="9cc6a-148">默认情况下，.xsd 文件的副本位于 `\ProgramData\Microsoft\UEV\Templates` 默认位置。</span><span class="sxs-lookup"><span data-stu-id="9cc6a-148">A copy of the .xsd file is located in `\ProgramData\Microsoft\UEV\Templates` by default.</span></span>

4.  <span data-ttu-id="9cc6a-149">保存设置位置模板文件，然后关闭 "XML 编辑器"。</span><span class="sxs-lookup"><span data-stu-id="9cc6a-149">Save the settings location template file and close the XML editor.</span></span>

5.  <span data-ttu-id="9cc6a-150">通过 UE-V 发生器验证修改后的设置位置模板文件。</span><span class="sxs-lookup"><span data-stu-id="9cc6a-150">Validate the modified settings location template file with the UE-V Generator.</span></span> <span data-ttu-id="9cc6a-151">有关通过 UE-V 生成器进行验证的详细信息，请参阅[通过 Ue-v 生成器验证 Ue-v 设置位置模板](validate-ue-v-settings-location-templates-with-ue-v-generator.md)。</span><span class="sxs-lookup"><span data-stu-id="9cc6a-151">For more information about validating with the UE-V Generator, see [Validate UE-V Settings Location Templates with UE-V Generator](validate-ue-v-settings-location-templates-with-ue-v-generator.md).</span></span>

## <span data-ttu-id="9cc6a-152">相关主题</span><span class="sxs-lookup"><span data-stu-id="9cc6a-152">Related topics</span></span>


[<span data-ttu-id="9cc6a-153">使用自定义 UE-V 模板和 UE-V 生成器</span><span class="sxs-lookup"><span data-stu-id="9cc6a-153">Working with Custom UE-V Templates and the UE-V Generator</span></span>](working-with-custom-ue-v-templates-and-the-ue-v-generator.md)

[<span data-ttu-id="9cc6a-154">UE-V 1.0 的操作</span><span class="sxs-lookup"><span data-stu-id="9cc6a-154">Operations for UE-V 1.0</span></span>](operations-for-ue-v-10.md)

 

 





