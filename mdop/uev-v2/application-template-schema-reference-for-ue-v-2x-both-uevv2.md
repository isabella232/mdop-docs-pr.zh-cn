---
title: 用于 UE-V 2 的应用程序模板架构参考
description: 用于 UE-V 2 的应用程序模板架构参考
author: dansimp
ms.assetid: be8735a5-6a3e-4b1f-ba14-2a3bc3e5a8b6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 03ff6eabae68f07c23d5977f901e6a90e292c6ac
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804162"
---
# <span data-ttu-id="3ec6a-103">用于 UE-V 2 的应用程序模板架构参考</span><span class="sxs-lookup"><span data-stu-id="3ec6a-103">Application Template Schema Reference for UE-V 2.x</span></span>


<span data-ttu-id="3ec6a-104">Microsoft 用户体验虚拟化（UE-V）2.0、2.1 和 2.1 SP1 使用 XML 设置位置模板来定义由 UE-V 捕获和应用的桌面应用程序设置和 Windows 设置。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-104">Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, and 2.1 SP1 use XML settings location templates to define the desktop application settings and Windows settings that are captured and applied by UE-V.</span></span> <span data-ttu-id="3ec6a-105">UE-V 包含一组默认设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-105">UE-V includes a set of default settings location templates.</span></span> <span data-ttu-id="3ec6a-106">你还可以通过 UE-V 生成器创建自定义设置位置模板。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-106">You can also create custom settings location templates with the UE-V Generator.</span></span>

<span data-ttu-id="3ec6a-107">高级用户可以自定义设置位置模板的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-107">An advanced user can customize the XML file for a settings location template.</span></span> <span data-ttu-id="3ec6a-108">本主题详细介绍了 UE-V 2.1 （SP1）和2.0 设置位置模板的 XML 结构，并提供了编辑这些文件的指南。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-108">This topic details the XML structure of the UE-V 2.1 (SP1) and 2.0 settings location templates and provides guidance for editing these files.</span></span>

## <span data-ttu-id="3ec6a-109">UE-V 2.1 和 2.1 SP1 应用程序模板参考</span><span class="sxs-lookup"><span data-stu-id="3ec6a-109">UE-V 2.1 and 2.1 SP1 Application Template Schema Reference</span></span>


<span data-ttu-id="3ec6a-110">本节详细介绍了 UE-V 2.1 和 2.1 SP1 设置位置模板的 XML 结构，并提供了编辑此文件的指南。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-110">This section details the XML structure of the UE-V 2.1 and 2.1 SP1 settings location template and provides guidance for editing this file.</span></span>

### <span data-ttu-id="3ec6a-111">本部分内容</span><span class="sxs-lookup"><span data-stu-id="3ec6a-111">In This Section</span></span>

-   [<span data-ttu-id="3ec6a-112">XML 声明和编码属性</span><span class="sxs-lookup"><span data-stu-id="3ec6a-112">XML Declaration and Encoding Attribute</span></span>](#xml21)

-   [<span data-ttu-id="3ec6a-113">命名空间和根元素</span><span class="sxs-lookup"><span data-stu-id="3ec6a-113">Namespace and Root Element</span></span>](#namespace21)

-   [<span data-ttu-id="3ec6a-114">数据类型</span><span class="sxs-lookup"><span data-stu-id="3ec6a-114">Data types</span></span>](#data21)

-   [<span data-ttu-id="3ec6a-115">名称元素</span><span class="sxs-lookup"><span data-stu-id="3ec6a-115">Name Element</span></span>](#name21)

-   [<span data-ttu-id="3ec6a-116">ID 元素</span><span class="sxs-lookup"><span data-stu-id="3ec6a-116">ID Element</span></span>](#id21)

-   [<span data-ttu-id="3ec6a-117">版本元素</span><span class="sxs-lookup"><span data-stu-id="3ec6a-117">Version Element</span></span>](#version21)

-   [<span data-ttu-id="3ec6a-118">作者元素</span><span class="sxs-lookup"><span data-stu-id="3ec6a-118">Author Element</span></span>](#author21)

-   [<span data-ttu-id="3ec6a-119">进程和进程元素</span><span class="sxs-lookup"><span data-stu-id="3ec6a-119">Processes and Process Element</span></span>](#processes21)

-   [<span data-ttu-id="3ec6a-120">应用程序元素</span><span class="sxs-lookup"><span data-stu-id="3ec6a-120">Application Element</span></span>](#application21)

-   [<span data-ttu-id="3ec6a-121">常见元素</span><span class="sxs-lookup"><span data-stu-id="3ec6a-121">Common Element</span></span>](#common21)

-   [<span data-ttu-id="3ec6a-122">SettingsLocationTemplate 元素</span><span class="sxs-lookup"><span data-stu-id="3ec6a-122">SettingsLocationTemplate Element</span></span>](#settingslocationtemplate21)

-   [<span data-ttu-id="3ec6a-123">附录： SettingsLocationTemplate</span><span class="sxs-lookup"><span data-stu-id="3ec6a-123">Appendix: SettingsLocationTemplate.xsd</span></span>](#appendix21)

### <a href="" id="xml21"></a><span data-ttu-id="3ec6a-124">XML 声明和编码属性</span><span class="sxs-lookup"><span data-stu-id="3ec6a-124">XML Declaration and Encoding Attribute</span></span>

**<span data-ttu-id="3ec6a-125">强制： True</span><span class="sxs-lookup"><span data-stu-id="3ec6a-125">Mandatory: True</span></span>**

**<span data-ttu-id="3ec6a-126">类型： String</span><span class="sxs-lookup"><span data-stu-id="3ec6a-126">Type: String</span></span>**

<span data-ttu-id="3ec6a-127">XML 声明必须指定 XML 版本1.0 属性（ &lt; ？ xml version = "1.0" &gt; ）。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-127">The XML declaration must specify the XML version 1.0 attribute (&lt;?xml version="1.0"&gt;).</span></span> <span data-ttu-id="3ec6a-128">由 UE-V 生成器创建的设置位置模板将保存为 UTF-8 编码，尽管编码没有明确指定。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-128">Settings location templates created by the UE-V Generator are saved in UTF-8 encoding, although the encoding is not explicitly specified.</span></span> <span data-ttu-id="3ec6a-129">我们建议你在此元素中将 encoding = "UTF-8" 属性作为最佳做法包括在内。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-129">We recommend that you include the encoding="UTF-8" attribute in this element as a best practice.</span></span> <span data-ttu-id="3ec6a-130">本产品附带的所有模板也都指定了此标记（请参阅%ProgramFiles%\\Microsoft 用户体验 Virtualization\\Templates 中的文档以了解参考）。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-130">All templates included with the product specify this tag as well (see the documents in %ProgramFiles%\\Microsoft User Experience Virtualization\\Templates for reference).</span></span> <span data-ttu-id="3ec6a-131">例如：</span><span class="sxs-lookup"><span data-stu-id="3ec6a-131">For example:</span></span>

`<?xml version="1.0" encoding="UTF-8"?>`

### <a href="" id="namespace21"></a><span data-ttu-id="3ec6a-132">命名空间和根元素</span><span class="sxs-lookup"><span data-stu-id="3ec6a-132">Namespace and Root Element</span></span>

**<span data-ttu-id="3ec6a-133">强制： True</span><span class="sxs-lookup"><span data-stu-id="3ec6a-133">Mandatory: True</span></span>**

**<span data-ttu-id="3ec6a-134">类型： String</span><span class="sxs-lookup"><span data-stu-id="3ec6a-134">Type: String</span></span>**

<span data-ttu-id="3ec6a-135">UE-V 使用 https://schemas.microsoft.com/UserExperienceVirtualization/2012/SettingsLocationTemplate 所有应用程序的命名空间。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-135">UE-V uses the https://schemas.microsoft.com/UserExperienceVirtualization/2012/SettingsLocationTemplate namespace for all applications.</span></span> <span data-ttu-id="3ec6a-136">SettingsLocationTemplate 是根元素，包含所有其他元素。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-136">SettingsLocationTemplate is the root element and contains all other elements.</span></span> <span data-ttu-id="3ec6a-137">使用此标记的所有模板中的引用 SettingsLocationTemplate：</span><span class="sxs-lookup"><span data-stu-id="3ec6a-137">Reference SettingsLocationTemplate in all templates using this tag:</span></span>

`<SettingsLocationTemplate xmlns='https://schemas.microsoft.com/UserExperienceVirtualization/2012/SettingsLocationTemplate'>`

### <a href="" id="data21"></a><span data-ttu-id="3ec6a-138">数据类型</span><span class="sxs-lookup"><span data-stu-id="3ec6a-138">Data types</span></span>

<span data-ttu-id="3ec6a-139">以下是 UE-V 应用程序模板架构的数据类型。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-139">These are the data types for the UE-V application template schema.</span></span>

<a href="" id="guid"></a><span data-ttu-id="3ec6a-140">**GUID**GUID 描述一个标准的全局唯一标识符正则表达式，格式为 "\\ {\ [a-F0 \] {8} -\ [a – fa-F0-9 \] {4} [a-Fa-F0 \] {4} -\ [a – F0-9 \] \ [a-- {4} F0-9 \] {12} \}"。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-140">**GUID** GUID describes a standard globally unique identifier regular expression in the form "\\{\[a-fA-F0-9\]{8}-\[a-fA-F0-9\]{4}-\[a-fA-F0-9\]{4}-\[a-fA-F0-9\]{4}-\[a-fA-F0-9\]{12}\\}".</span></span> <span data-ttu-id="3ec6a-141">在 Filesetting\\Root\\KnownFolder 元素中使用此功能来验证已知文件夹的格式。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-141">This is used in the Filesetting\\Root\\KnownFolder element to verify the formatting of well-known folders.</span></span>

<a href="" id="filenamestring"></a><span data-ttu-id="3ec6a-142">**FilenameString**FilenameString 是指要监视的进程的文件名。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-142">**FilenameString** FilenameString refers to the file name of a process to be monitored.</span></span> <span data-ttu-id="3ec6a-143">它的值受 regex \ [^ \ \ \ \ \* &lt; &gt; \？/： \] +，（也就是说，它们不能包含反斜杠字符、星号或问号通配符、管道字符、大于或小于符号、正斜杠或冒号字符）。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-143">Its values are restricted by the regex \[^\\\\\\?\\\*\\|&lt;&gt;/:\]+, (that is, they may not contain backslash characters, asterisk or question mark wild-card characters, the pipe character, the greater than or less than sign, forward slash, or colon characters).</span></span>

<a href="" id="idstring"></a><span data-ttu-id="3ec6a-144">**IDString**IDString 是指应用程序元素、SettingsLocationTemplate 和常见元素（用于描述共享通用设置的应用程序套件）的 ID 值。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-144">**IDString** IDString refers to the ID value of Application elements, SettingsLocationTemplate, and Common elements (used to describe application suites that share common settings).</span></span> <span data-ttu-id="3ec6a-145">它受与 FilenameString 相同的正则表达式的限制（\ [^ \ \ \ \ \* \ \ \* &lt; &gt; \/:\]+).</span><span class="sxs-lookup"><span data-stu-id="3ec6a-145">It is restricted by the same regex as FilenameString (\[^\\\\\\?\\\*\\|&lt;&gt;/:\]+).</span></span>

<a href="" id="templateversion"></a><span data-ttu-id="3ec6a-146">**TemplateVersion**TemplateVersion 是用于描述设置位置模板的版本的整数值。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-146">**TemplateVersion** TemplateVersion is an integer value used to describe the revision of the settings location template.</span></span> <span data-ttu-id="3ec6a-147">其值的范围可以从0到2147483647。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-147">Its value may range from 0 to 2147483647.</span></span>

<a href="" id="empty"></a><span data-ttu-id="3ec6a-148">**空**空表示空值。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-148">**Empty** Empty refers to a null value.</span></span> <span data-ttu-id="3ec6a-149">此功能在 Process\\ShellProcess 中用于指示没有要监视的进程。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-149">This is used in Process\\ShellProcess to indicate that there is no process to monitor.</span></span> <span data-ttu-id="3ec6a-150">此值不应在任何应用程序模板中使用。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-150">This value should not be used in any application templates.</span></span>

<a href="" id="author"></a><span data-ttu-id="3ec6a-151">**作者**"作者" 数据类型是标识模板作者的复杂类型。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-151">**Author** The Author data type is a complex type that identifies the author of a template.</span></span> <span data-ttu-id="3ec6a-152">它包含两个子元素：**名称**和**电子邮件**。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-152">It contains two child elements: **Name** and **Email**.</span></span> <span data-ttu-id="3ec6a-153">在 "作者" 数据类型中，Name 元素是必需的，而 Email 元素是可选的。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-153">Within the Author data type, the Name element is mandatory while the Email element is optional.</span></span> <span data-ttu-id="3ec6a-154">此类型将在 SettingsLocationTemplate 元素下更详细地进行介绍。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-154">This type is described in more detail under the SettingsLocationTemplate element.</span></span>

<a href="" id="range"></a><span data-ttu-id="3ec6a-155">**区域**Range 定义一个包含两个子元素的整数类：**最小值**和**最大值**。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-155">**Range** Range defines an integer class consisting of two child elements: **Minimum** and **Maximum**.</span></span> <span data-ttu-id="3ec6a-156">此数据类型在 ProcessVersion 数据类型中实现。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-156">This data type is implemented in the ProcessVersion data type.</span></span> <span data-ttu-id="3ec6a-157">如果已指定，则必须同时包含最小值和最大值。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-157">If specified, both Minimum and Maximum values must be included.</span></span>

<a href="" id="processversion"></a><span data-ttu-id="3ec6a-158">**ProcessVersion**ProcessVersion 定义了一个包含四个子元素的类型：**主要**、**次要**、**内部版本**和**修补程序**。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-158">**ProcessVersion** ProcessVersion defines a type with four child elements: **Major**, **Minor**, **Build**, and **Patch**.</span></span> <span data-ttu-id="3ec6a-159">Process 元素使用此数据类型填充其 ProductVersion 和 FileVersion 值。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-159">This data type is used by the Process element to populate its ProductVersion and FileVersion values.</span></span> <span data-ttu-id="3ec6a-160">此类型的数据是一个范围值。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-160">The data for this type is a Range value.</span></span> <span data-ttu-id="3ec6a-161">主要子元素是必需的，而其他元素是可选的。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-161">The Major child element is mandatory and the others are optional.</span></span>

<a href="" id="architecture"></a><span data-ttu-id="3ec6a-162">**体系结构**体系结构枚举两个可能的值： **Win32**和**Win64**。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-162">**Architecture** Architecture enumerates two possible values: **Win32** and **Win64**.</span></span> <span data-ttu-id="3ec6a-163">这些值用于指定进程体系结构。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-163">These values are used to specify process architecture.</span></span>

<a href="" id="process"></a><span data-ttu-id="3ec6a-164">**处理**"流程" 数据类型是用于描述由 UE-V 监视的流程的容器。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-164">**Process** The Process data type is a container used to describe processes to be monitored by UE-V.</span></span> <span data-ttu-id="3ec6a-165">它包含六个子元素： **Filename**、**体系结构**、 **ProductName**、 **FileDescription**、 **ProductVersion**和**FileVersion**。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-165">It contains six child elements: **Filename**, **Architecture**, **ProductName**, **FileDescription**, **ProductVersion**, and **FileVersion**.</span></span> <span data-ttu-id="3ec6a-166">下表详细介绍了每个元素各自的数据类型：</span><span class="sxs-lookup"><span data-stu-id="3ec6a-166">This table details each element’s respective data type:</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="3ec6a-167">元素</span><span class="sxs-lookup"><span data-stu-id="3ec6a-167">Element</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="3ec6a-168">数据类型</span><span class="sxs-lookup"><span data-stu-id="3ec6a-168">Data Type</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="3ec6a-169">Mandatory</span><span class="sxs-lookup"><span data-stu-id="3ec6a-169">Mandatory</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3ec6a-170">相配</span><span class="sxs-lookup"><span data-stu-id="3ec6a-170">Filename</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-171">FilenameString</span><span class="sxs-lookup"><span data-stu-id="3ec6a-171">FilenameString</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-172">True</span><span class="sxs-lookup"><span data-stu-id="3ec6a-172">True</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3ec6a-173">体系结构</span><span class="sxs-lookup"><span data-stu-id="3ec6a-173">Architecture</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-174">体系结构</span><span class="sxs-lookup"><span data-stu-id="3ec6a-174">Architecture</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-175">False</span><span class="sxs-lookup"><span data-stu-id="3ec6a-175">False</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3ec6a-176">ProductName</span><span class="sxs-lookup"><span data-stu-id="3ec6a-176">ProductName</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-177">字符串</span><span class="sxs-lookup"><span data-stu-id="3ec6a-177">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-178">False</span><span class="sxs-lookup"><span data-stu-id="3ec6a-178">False</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3ec6a-179">FileDescription</span><span class="sxs-lookup"><span data-stu-id="3ec6a-179">FileDescription</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-180">字符串</span><span class="sxs-lookup"><span data-stu-id="3ec6a-180">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-181">False</span><span class="sxs-lookup"><span data-stu-id="3ec6a-181">False</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3ec6a-182">ProductVersion</span><span class="sxs-lookup"><span data-stu-id="3ec6a-182">ProductVersion</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-183">ProcessVersion</span><span class="sxs-lookup"><span data-stu-id="3ec6a-183">ProcessVersion</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-184">False</span><span class="sxs-lookup"><span data-stu-id="3ec6a-184">False</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3ec6a-185">FileVersion</span><span class="sxs-lookup"><span data-stu-id="3ec6a-185">FileVersion</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-186">ProcessVersion</span><span class="sxs-lookup"><span data-stu-id="3ec6a-186">ProcessVersion</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-187">False</span><span class="sxs-lookup"><span data-stu-id="3ec6a-187">False</span></span></p></td>
</tr>
</tbody>
</table>

 

<a href="" id="processes"></a><span data-ttu-id="3ec6a-188">**流程**"流程" 数据类型表示一个容器，用于一个或多个流程元素的集合。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-188">**Processes** The Processes data type represents a container for a collection of one or more Process elements.</span></span> <span data-ttu-id="3ec6a-189">进程序列类型中支持两个子元素： **Process**和**ShellProcess**。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-189">Two child elements are supported in the Processes sequence type: **Process** and **ShellProcess**.</span></span> <span data-ttu-id="3ec6a-190">Process 是 Process 类型的元素，ShellProcess 的数据类型为 Empty。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-190">Process is an element of type Process and ShellProcess is of data type Empty.</span></span> <span data-ttu-id="3ec6a-191">序列中必须至少标识一个项目。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-191">At least one item must be identified in the sequence.</span></span>

<a href="" id="path"></a><span data-ttu-id="3ec6a-192">**路径**RegistrySetting 和 FileSetting 使用 Path 来引用注册表和文件路径。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-192">**Path** Path is consumed by RegistrySetting and FileSetting to refer to registry and file paths.</span></span> <span data-ttu-id="3ec6a-193">此元素支持两个可选属性： **Recursive**和**DeleteIfNotFound**。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-193">This element supports two optional attributes: **Recursive** and **DeleteIfNotFound**.</span></span> <span data-ttu-id="3ec6a-194">两个值均设置为默认值 = "False"。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-194">Both values are set to default=”False”.</span></span>

<span data-ttu-id="3ec6a-195">递归表示文件设置包含路径和所有子文件夹，或者注册表设置包含所有子注册表项。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-195">Recursive indicates that the path and all subfolders are included for file settings or that all child registry keys are included for registry settings.</span></span> <span data-ttu-id="3ec6a-196">在这两种情况下，当前级别的所有项目都包含在捕获的数据中。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-196">In both cases, all items at the current level are included in the data captured.</span></span> <span data-ttu-id="3ec6a-197">对于 FileSettings 对象，指定文件夹中的所有文件都包含在由 UE-V 捕获的数据中，但不包括文件夹。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-197">For a FileSettings object, all files within the specified folder are included in the data captured by UE-V but folders are not included.</span></span> <span data-ttu-id="3ec6a-198">对于注册表路径，将捕获当前路径中的所有值，但不捕获子注册表项。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-198">For registry paths, all values in the current path are captured but child registry keys are not captured.</span></span> <span data-ttu-id="3ec6a-199">在这两种情况下，应注意避免捕获大型数据集或大量项目。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-199">In both cases, care should be taken to avoid capturing large data sets or large numbers of items.</span></span>

<span data-ttu-id="3ec6a-200">DeleteIfNotFound 属性从用户的设置存储路径数据中删除设置。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-200">The DeleteIfNotFound attribute removes the setting from the user’s settings storage path data.</span></span> <span data-ttu-id="3ec6a-201">在从包中删除这些设置将在设置存储路径文件服务器上保存大量磁盘空间时，这可能是理想的情况。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-201">This may be desirable in cases where removing these settings from the package will save a large amount of disk space on the settings storage path file server.</span></span>

<a href="" id="filemask"></a><span data-ttu-id="3ec6a-202">**FileMask**FileMask 仅指定由 Path 定义的文件夹的某些文件类型。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-202">**FileMask** FileMask specifies only certain file types for the folder that is defined by Path.</span></span> <span data-ttu-id="3ec6a-203">例如，Path 可能是 `C:\users\username\files` 且 FileMask 可以 `*.txt` 仅包含文本文件。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-203">For example, Path might be `C:\users\username\files` and FileMask could be `*.txt` to include only text files.</span></span>

<a href="" id="registrysetting"></a><span data-ttu-id="3ec6a-204">**RegistrySetting**RegistrySetting 表示注册表项和值的容器，以及 UE-V Agent 部分相关联的所需行为。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-204">**RegistrySetting** RegistrySetting represents a container for registry keys and values and the associated desired behavior on the part of the UE-V Agent.</span></span> <span data-ttu-id="3ec6a-205">在此类型中定义了四个子元素：**路径**、**名称**、**排除**和值**路径**和**名称**的序列。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-205">Four child elements are defined within this type: **Path**, **Name**, **Exclude**, and a sequence of the values **Path** and **Name**.</span></span>

<a href="" id="filesetting"></a><span data-ttu-id="3ec6a-206">**FileSetting**FileSetting 包含与文件和文件路径相关联的参数。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-206">**FileSetting** FileSetting contains parameters associated with files and files paths.</span></span> <span data-ttu-id="3ec6a-207">定义了四个子元素： **Root**、 **Path**、 **FileMask**和**Exclude**。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-207">Four child elements are defined: **Root**, **Path**, **FileMask**, and **Exclude**.</span></span> <span data-ttu-id="3ec6a-208">根是强制性的，而其他是可选的。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-208">Root is mandatory and the others are optional.</span></span>

<a href="" id="settings"></a><span data-ttu-id="3ec6a-209">**设置**"设置" 是适用于特定模板的所有设置的容器。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-209">**Settings** Settings is a container for all the settings that apply to a particular template.</span></span> <span data-ttu-id="3ec6a-210">它包含前面所述的注册表、文件、SystemParameter 和 CustomAction 设置的实例。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-210">It contains instances of the Registry, File, SystemParameter, and CustomAction settings described earlier.</span></span> <span data-ttu-id="3ec6a-211">此外，它还可以包含包含以下行为的以下子元素：</span><span class="sxs-lookup"><span data-stu-id="3ec6a-211">In addition, it can also contain the following child elements with behaviors described:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="3ec6a-212">元素</span><span class="sxs-lookup"><span data-stu-id="3ec6a-212">Element</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="3ec6a-213">描述</span><span class="sxs-lookup"><span data-stu-id="3ec6a-213">Description</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3ec6a-214">异步</span><span class="sxs-lookup"><span data-stu-id="3ec6a-214">Asynchronous</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-215">在不阻止应用程序启动的情况下应用异步设置程序包，以便应用程序在设置仍在应用时启动。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-215">Asynchronous settings packages are applied without blocking the application startup so that the application start proceeds while the settings are still being applied.</span></span> <span data-ttu-id="3ec6a-216">这对于可以异步应用的设置（例如 <code>get/set</code> ，通过 API （如 SystemParameterSetting）很有用。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-216">This is useful for settings that can be applied asynchronously, such as those <code>get/set</code> through an API, like SystemParameterSetting.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3ec6a-217">PreventOverlappingSynchronization</span><span class="sxs-lookup"><span data-stu-id="3ec6a-217">PreventOverlappingSynchronization</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-218">默认情况下，当使用模板的最后一个应用程序实例关闭时，UE-V 仅保存应用程序的设置。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-218">By default, UE-V only saves settings for an application when the last instance of an application using the template is closed.</span></span> <span data-ttu-id="3ec6a-219">当此元素设置为 "false" 时，UE-V 将导出设置，即使应用程序的其他实例正在运行。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-219">When this element is set to ‘false’, UE-V exports the settings even if other instances of an application are running.</span></span> <span data-ttu-id="3ec6a-220">适用的模板（包括常见元素部分的模板）使用此标志可使共享设置始终在应用程序关闭时导出，同时防止应用程序特定的设置在最后一个实例关闭之前导出。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-220">Suited templates – those that include a Common element section– that are shipped with UE-V use this flag to enable shared settings to always export on application close, while preventing application-specific settings from exporting until the last instance is closed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3ec6a-221">AlwaysApplySettings</span><span class="sxs-lookup"><span data-stu-id="3ec6a-221">AlwaysApplySettings</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-222">（在2.1 中引入）</span><span class="sxs-lookup"><span data-stu-id="3ec6a-222">(introduced in 2.1)</span></span></p>
<p><span data-ttu-id="3ec6a-223">此参数会强制应用导入的设置包，即使应用程序的程序包和当前状态之间没有差异也是如此。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-223">This parameter forces an imported settings package to be applied even if there are no differences between the package and the current state of the application.</span></span> <span data-ttu-id="3ec6a-224">此参数应仅在特殊情况下使用，因为它可能会减慢设置导入的速度。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-224">This parameter should be used only in special cases since it can slow down settings import.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="name21"></a><span data-ttu-id="3ec6a-225">名称元素</span><span class="sxs-lookup"><span data-stu-id="3ec6a-225">Name Element</span></span>

**<span data-ttu-id="3ec6a-226">强制： True</span><span class="sxs-lookup"><span data-stu-id="3ec6a-226">Mandatory: True</span></span>**

**<span data-ttu-id="3ec6a-227">类型： String</span><span class="sxs-lookup"><span data-stu-id="3ec6a-227">Type: String</span></span>**

<span data-ttu-id="3ec6a-228">名称指定设置位置模板的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-228">Name specifies a unique name for the settings location template.</span></span> <span data-ttu-id="3ec6a-229">这用于在 WMI、PowerShell、事件查看器和调试日志中引用模板时的显示用途。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-229">This is used for display purposes when referencing the template in WMI, PowerShell, Event Viewer and debug logs.</span></span> <span data-ttu-id="3ec6a-230">通常，请避免引用版本信息，因为这可以从 ProductVersion 元素中 objected。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-230">In general, avoid referencing version information, as this can be objected from the ProductVersion element.</span></span> <span data-ttu-id="3ec6a-231">例如，指定 " `<Name>My Application</Name>` 而不是" `<Name>My Application 1.1</Name>` 。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-231">For example, specify `<Name>My Application</Name>` rather than `<Name>My Application 1.1</Name>`.</span></span>

<span data-ttu-id="3ec6a-232">**注意** UE-V 不引用外部 Dtd，因此不能使用设置位置模板中的命名实体。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-232">**Note** UE-V does not reference external DTDs, so it is not possible to use named entities in a settings location template.</span></span> <span data-ttu-id="3ec6a-233">例如，不要使用 &reg; 来指注册的商标签名®。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-233">For example, do not use &reg; to refer to the registered trade mark sign ®.</span></span> <span data-ttu-id="3ec6a-234">而是使用规范编号引用包括这些类型的特殊字符，例如 &®字符的 \ #174。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-234">Instead, use canonical numbered references to include these types of special characters, for example, &\#174 for the ® character.</span></span> <span data-ttu-id="3ec6a-235">此规则适用于此文档中的所有字符串值。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-235">This rule applies to all string values in this document.</span></span>

<span data-ttu-id="3ec6a-236"><http://www.w3.org/TR/xhtml1/dtds.html>有关字符实体的完整列表，请参阅。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-236">See <http://www.w3.org/TR/xhtml1/dtds.html> for a complete list of character entities.</span></span> <span data-ttu-id="3ec6a-237">UTF-8 编码的文档可能直接包含 Unicode 字符。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-237">UTF-8-encoded documents may include the Unicode characters directly.</span></span> <span data-ttu-id="3ec6a-238">通过 UE-V 生成器保存模板将自动将字符实体转换为其 Unicode 表示形式。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-238">Saving templates through the UE-V Generator converts character entities to their Unicode representations automatically.</span></span>

 

### <a href="" id="id21"></a><span data-ttu-id="3ec6a-239">ID 元素</span><span class="sxs-lookup"><span data-stu-id="3ec6a-239">ID Element</span></span>

**<span data-ttu-id="3ec6a-240">强制： True</span><span class="sxs-lookup"><span data-stu-id="3ec6a-240">Mandatory: True</span></span>**

**<span data-ttu-id="3ec6a-241">类型： String</span><span class="sxs-lookup"><span data-stu-id="3ec6a-241">Type: String</span></span>**

<span data-ttu-id="3ec6a-242">ID 填充特定模板的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-242">ID populates a unique identifier for a particular template.</span></span> <span data-ttu-id="3ec6a-243">此标记将成为 UE-V Agent 在运行时引用模板时使用的主标识符（例如，请参阅 UevTemplate 和 UevTemplateProgram PowerShell cmdlet 的输出）。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-243">This tag becomes the primary identifier that the UE-V Agent uses to reference the template at runtime (for example, see the output of the Get-UevTemplate and Get-UevTemplateProgram PowerShell cmdlets).</span></span> <span data-ttu-id="3ec6a-244">按照约定，此标记不应包含任何空格，从而简化了脚本编写。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-244">By convention, this tag should not contain any spaces, which simplifies scripting.</span></span> <span data-ttu-id="3ec6a-245">应在此元素中指定应用程序的版本号，以便更轻松地标识模板，例如 `<ID>MicrosoftCalculator6</ID>` 或 `<ID>MicrosoftOffice2010Win64</ID>` 。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-245">Version numbers of applications should be specified in this element to allow for easy identification of the template, such as `<ID>MicrosoftCalculator6</ID>` or `<ID>MicrosoftOffice2010Win64</ID>`.</span></span>

### <a href="" id="version21"></a><span data-ttu-id="3ec6a-246">版本元素</span><span class="sxs-lookup"><span data-stu-id="3ec6a-246">Version Element</span></span>

**<span data-ttu-id="3ec6a-247">强制： True</span><span class="sxs-lookup"><span data-stu-id="3ec6a-247">Mandatory: True</span></span>**

**<span data-ttu-id="3ec6a-248">类型： Integer</span><span class="sxs-lookup"><span data-stu-id="3ec6a-248">Type: Integer</span></span>**

**<span data-ttu-id="3ec6a-249">最小值：0</span><span class="sxs-lookup"><span data-stu-id="3ec6a-249">Minimum Value: 0</span></span>**

**<span data-ttu-id="3ec6a-250">最大值：2147483647</span><span class="sxs-lookup"><span data-stu-id="3ec6a-250">Maximum Value: 2147483647</span></span>**

<span data-ttu-id="3ec6a-251">版本标识用于管理更改管理跟踪的设置位置模板的版本。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-251">Version identifies the version of the settings location template for administrative tracking of changes.</span></span> <span data-ttu-id="3ec6a-252">每次保存模板时，UE-V 生成器都会自动将该数字递增1。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-252">The UE-V Generator automatically increments this number by one each time the template is saved.</span></span> <span data-ttu-id="3ec6a-253">请注意，此字段必须为整数整数;不允许使用小数值，例如 `<Version>2.5</Version>` 。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-253">Notice that this field must be a whole number integer; fractional values, such as `<Version>2.5</Version>` are not allowed.</span></span>

<span data-ttu-id="3ec6a-254">**提示：** 你可以使用 XML 注释标记保存有关版本更改 `<!-- -->` 的注释，例如：</span><span class="sxs-lookup"><span data-stu-id="3ec6a-254">**Hint:** You can save notes about version changes using XML comment tags `<!-- -->`, for example:</span></span>

```xml
  <!--
     Version History

     Version 1 Jul 05, 2012 Initial template created by Generator - Denise@Contoso.com
     Version 2 Jul 31, 2012 Added support for app.exe v2.1.3 - Mark@Contoso.com
     Version 3 Jan 01, 2013 Added font settings support - Mark@Contoso.com
     Version 4 Jan 31, 2013 Added support for plugin settings - Tony@Contoso.com
   -->
  <Version>4</Version>
```

<span data-ttu-id="3ec6a-255">**重要提示** 将查询此值，以确定是否应将模板的新版本应用于这些实例中的现有模板：</span><span class="sxs-lookup"><span data-stu-id="3ec6a-255">**Important** This value is queried to determine if a new version of a template should be applied to an existing template in these instances:</span></span>

-   <span data-ttu-id="3ec6a-256">执行计划模板自动更新任务时</span><span class="sxs-lookup"><span data-stu-id="3ec6a-256">When the scheduled Template Auto Update task executes</span></span>

-   <span data-ttu-id="3ec6a-257">当执行 UevTemplate PowerShell cmdlet 时</span><span class="sxs-lookup"><span data-stu-id="3ec6a-257">When the Update-UevTemplate PowerShell cmdlet is executed</span></span>

-   <span data-ttu-id="3ec6a-258">当 microsoft\\uev： SettingsLocationTemplate Update 方法通过 WMI 调用时</span><span class="sxs-lookup"><span data-stu-id="3ec6a-258">When the microsoft\\uev:SettingsLocationTemplate Update method is called through WMI</span></span>

 

### <a href="" id="author21"></a><span data-ttu-id="3ec6a-259">作者元素</span><span class="sxs-lookup"><span data-stu-id="3ec6a-259">Author Element</span></span>

**<span data-ttu-id="3ec6a-260">强制： False</span><span class="sxs-lookup"><span data-stu-id="3ec6a-260">Mandatory: False</span></span>**

**<span data-ttu-id="3ec6a-261">类型： String</span><span class="sxs-lookup"><span data-stu-id="3ec6a-261">Type: String</span></span>**

<span data-ttu-id="3ec6a-262">作者标识设置位置模板的创建者。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-262">Author identifies the creator of the settings location template.</span></span> <span data-ttu-id="3ec6a-263">支持两个可选子元素：**名称**和**电子邮件**。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-263">Two optional child elements are supported: **Name** and **Email**.</span></span> <span data-ttu-id="3ec6a-264">这两个属性都是可选的，但如果指定了电子邮件子元素，则它必须附有 Name 元素。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-264">Both attributes are optional, but, if the Email child element is specified, it must be accompanied by the Name element.</span></span> <span data-ttu-id="3ec6a-265">作者指的是 "设置位置" 模板的联系人的全名，电子邮件应该指作者的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-265">Author refers to the full name of the contact for the settings location template, and email should refer to an email address for the author.</span></span> <span data-ttu-id="3ec6a-266">建议在公共发布的模板中包括此信息，例如，在[Ue-v 模板库](https://gallery.technet.microsoft.com/site/search?f%5B0%5D.Type=RootCategory&f%5B0%5D.Value=UE-V)中。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-266">We recommend that you include this information in templates published publicly, for example, on the [UE-V Template Gallery](https://gallery.technet.microsoft.com/site/search?f%5B0%5D.Type=RootCategory&f%5B0%5D.Value=UE-V).</span></span>

### <a href="" id="processes21"></a><span data-ttu-id="3ec6a-267">进程和进程元素</span><span class="sxs-lookup"><span data-stu-id="3ec6a-267">Processes and Process Element</span></span>

**<span data-ttu-id="3ec6a-268">强制： True</span><span class="sxs-lookup"><span data-stu-id="3ec6a-268">Mandatory: True</span></span>**

**<span data-ttu-id="3ec6a-269">类型：元素</span><span class="sxs-lookup"><span data-stu-id="3ec6a-269">Type: Element</span></span>**

<span data-ttu-id="3ec6a-270">进程至少包含一个 `<Process>` 元素，该元素又包含以下子元素： **Filename**、**体系结构**、 **ProductName**、 **FileDescription**、 **ProductVersion**和**FileVersion**。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-270">Processes contains at least one `<Process>` element, which in turn contains the following child elements: **Filename**, **Architecture**, **ProductName**, **FileDescription**, **ProductVersion**, and **FileVersion**.</span></span> <span data-ttu-id="3ec6a-271">Filename 子元素是必需的，而其他元素是可选的。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-271">The Filename child element is mandatory and the others are optional.</span></span> <span data-ttu-id="3ec6a-272">完全填充的元素包含与以下示例类似的标记：</span><span class="sxs-lookup"><span data-stu-id="3ec6a-272">A fully populated element contains tags similar to this example:</span></span>

```xml
<Process>
  <Filename>MyApplication.exe</Filename>
  <Architecture>Win64</Architecture>
  <ProductName> MyApplication </ProductName>
  <FileDescription>MyApplication.exe</FileDescription>
  <ProductVersion>
    <Major Minimum="2" Maximum="2" />
    <Minor Minimum="0" Maximum="0" />
    <Build Minimum="0" Maximum="0" />
    <Patch Minimum="5" Maximum="5" />
  </ProductVersion>
  <FileVersion>
    <Major Minimum="2" Maximum="2" />
    <Minor Minimum="0" Maximum="0" />
    <Build Minimum="0" Maximum="0" />
    <Patch Minimum="5" Maximum="5" />
  </FileVersion>
</Process>
```

### <span data-ttu-id="3ec6a-273">相配</span><span class="sxs-lookup"><span data-stu-id="3ec6a-273">Filename</span></span>

**<span data-ttu-id="3ec6a-274">强制： True</span><span class="sxs-lookup"><span data-stu-id="3ec6a-274">Mandatory: True</span></span>**

**<span data-ttu-id="3ec6a-275">类型： String</span><span class="sxs-lookup"><span data-stu-id="3ec6a-275">Type: String</span></span>**

<span data-ttu-id="3ec6a-276">文件名是指在文件系统中显示的可执行文件的实际文件名。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-276">Filename refers to the actual file name of the executable as it appears in the file system.</span></span> <span data-ttu-id="3ec6a-277">此元素指定 UE-V 用于评估模板是否适用于进程的主要条件。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-277">This element specifies the primary criterion that UE-V uses to evaluate whether a template applies to a process or not.</span></span> <span data-ttu-id="3ec6a-278">此元素必须在设置位置模板 XML 中指定。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-278">This element must be specified in the settings location template XML.</span></span>

<span data-ttu-id="3ec6a-279">有效的文件名必须与正则表达式 \ [^ \ &lt; &gt; \ \ \ \/： \] + 时，它们不能包含反斜杠字符、星号或问号通配符、管道字符、大于或小于符号、正斜杠或冒号（\\？）</span><span class="sxs-lookup"><span data-stu-id="3ec6a-279">Valid filenames must not match the regular expression \[^\\\\\\?\\\*\\|&lt;&gt;/:\]+, that is, they may not contain backslash characters, asterisk or question mark wild-card characters, the pipe character, the greater than or less than sign, forward slash, or colon (the \\ ?</span></span> <span data-ttu-id="3ec6a-280">\* |&lt; &gt; /或：个字符。）</span><span class="sxs-lookup"><span data-stu-id="3ec6a-280">\* | &lt; &gt; / or : characters.).</span></span>

<span data-ttu-id="3ec6a-281">**提示：** 若要针对此 regex 测试字符串，请使用 PowerShell 命令窗口并将可执行文件的名称替换为**YourFileName**：</span><span class="sxs-lookup"><span data-stu-id="3ec6a-281">**Hint:** To test a string against this regex, use a PowerShell command window and substitute your executable’s name for **YourFileName**:</span></span>

`"YourFileName.exe" -match  "[\\\?\*\|<>/:]+"`

<span data-ttu-id="3ec6a-282">**True**值表示字符串包含非法字符。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-282">A value of **True** indicates that the string contains illegal characters.</span></span> <span data-ttu-id="3ec6a-283">下面是一些非法值的示例：</span><span class="sxs-lookup"><span data-stu-id="3ec6a-283">Here are some examples of illegal values:</span></span>

-   <span data-ttu-id="3ec6a-284">\\\\server\\share\\program.exe</span><span class="sxs-lookup"><span data-stu-id="3ec6a-284">\\\\server\\share\\program.exe</span></span>

-   <span data-ttu-id="3ec6a-285">程序 \ \* .exe</span><span class="sxs-lookup"><span data-stu-id="3ec6a-285">Program\*.exe</span></span>

-   <span data-ttu-id="3ec6a-286">Pro？ ram.exe</span><span class="sxs-lookup"><span data-stu-id="3ec6a-286">Pro?ram.exe</span></span>

-   <span data-ttu-id="3ec6a-287">程序 &lt; 1 &gt; .exe</span><span class="sxs-lookup"><span data-stu-id="3ec6a-287">Program&lt;1&gt;.exe</span></span>

<span data-ttu-id="3ec6a-288">**注意** UE-V 生成器分别对大于和小于字符进行编码 &gt; &lt; 。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-288">**Note** The UE-V Generator encodes the greater than and less than characters as &gt; and &lt; respectively.</span></span>

 

<span data-ttu-id="3ec6a-289">在极少数情况下，文件名值不一定包含 .exe 扩展名，但应将其指定为值的一部分。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-289">In rare circumstances, the FileName value will not necessarily include the .exe extension, but it should be specified as part of the value.</span></span> <span data-ttu-id="3ec6a-290">例如， `<Filename>MyApplictication.exe</Filename>` 应指定而不是 `<Filename>MyApplictication</Filename>` 。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-290">For example, `<Filename>MyApplictication.exe</Filename>` should be specified instead of `<Filename>MyApplictication</Filename>`.</span></span> <span data-ttu-id="3ec6a-291">如果可执行文件的实际名称为 "MyApplication.exe"，则第二个示例不会将模板应用于该进程。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-291">The second example will not apply the template to the process if the actual name of the executable file is “MyApplication.exe”.</span></span>

### <span data-ttu-id="3ec6a-292">体系结构</span><span class="sxs-lookup"><span data-stu-id="3ec6a-292">Architecture</span></span>

**<span data-ttu-id="3ec6a-293">强制： False</span><span class="sxs-lookup"><span data-stu-id="3ec6a-293">Mandatory: False</span></span>**

**<span data-ttu-id="3ec6a-294">类型：体系结构（字符串）</span><span class="sxs-lookup"><span data-stu-id="3ec6a-294">Type: Architecture (String)</span></span>**

<span data-ttu-id="3ec6a-295">体系结构是指已编译目标可执行文件的处理器体系结构。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-295">Architecture refers to the processor architecture for which the target executable was compiled.</span></span> <span data-ttu-id="3ec6a-296">有效值为32位应用程序的 Win32 或64位应用程序的 Win64。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-296">Valid values are Win32 for 32-bit applications or Win64 for 64-bit applications.</span></span> <span data-ttu-id="3ec6a-297">如果存在，此标记将设置位置模板的适用性限制为特定的应用程序体系结构。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-297">If present, this tag limits the applicability of the settings location template to a particular application architecture.</span></span> <span data-ttu-id="3ec6a-298">有关此操作的示例，请比较%ProgramFiles%\\Microsoft 用户体验 Virtualization\\templates\\ MicrosoftOffice2010Win32.xml 和 UE-V 附带的 MicrosoftOffice2010Win64.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-298">For an example of this, compare the %ProgramFiles%\\Microsoft User Experience Virtualization\\templates\\ MicrosoftOffice2010Win32.xml and MicrosoftOffice2010Win64.xml files included with UE-V.</span></span> <span data-ttu-id="3ec6a-299">如果相对路径在不同版本的可执行文件之间更改，或者在从一个处理器体系结构移动到另一个时已添加或删除了设置，此方法将非常有用。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-299">This is useful when relative paths change between different versions of an executable or if settings have been added or removed when moving from one processor architecture to another.</span></span>

<span data-ttu-id="3ec6a-300">如果此元素不存在，则设置位置模板将忽略进程的体系结构，并将其应用于32和64位进程（如果应用了文件名和其他属性）。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-300">If this element is absent, the settings location template ignores the process’ architecture and applies to both 32 and 64-bit processes if the file name and other attributes apply.</span></span>

<span data-ttu-id="3ec6a-301">**注意** UE-V 不支持此版本中的 ARM 处理器。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-301">**Note** UE-V does not support ARM processors in this version.</span></span>

 

### <span data-ttu-id="3ec6a-302">ProductName</span><span class="sxs-lookup"><span data-stu-id="3ec6a-302">ProductName</span></span>

**<span data-ttu-id="3ec6a-303">强制： False</span><span class="sxs-lookup"><span data-stu-id="3ec6a-303">Mandatory: False</span></span>**

**<span data-ttu-id="3ec6a-304">类型： String</span><span class="sxs-lookup"><span data-stu-id="3ec6a-304">Type: String</span></span>**

<span data-ttu-id="3ec6a-305">ProductName 是一个可选元素，用于标识用于管理用途或报告的产品。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-305">ProductName is an optional element used to identify a product for administrative purposes or reporting.</span></span> <span data-ttu-id="3ec6a-306">ProductName 与 Filename 的不同之处在于它的值没有正则表达式限制。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-306">ProductName differs from Filename in that there are no regular expression restrictions on its value.</span></span> <span data-ttu-id="3ec6a-307">这允许更容易理解的可执行文件名称可能不明显的进程的说明。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-307">This allows for more easily understood descriptions of a process where the executable name may not be obvious.</span></span> <span data-ttu-id="3ec6a-308">例如：</span><span class="sxs-lookup"><span data-stu-id="3ec6a-308">For example:</span></span>

```xml
<Process>
  <Filename>MyApplication.exe</Filename>
  <ProductName>My Application 6.x by Contoso.com</ProductName>
  <ProductVersion>
    <Major Minimum="6" Maximum="6" />
  </ProductVersion>
</Process>
```

### <span data-ttu-id="3ec6a-309">FileDescription</span><span class="sxs-lookup"><span data-stu-id="3ec6a-309">FileDescription</span></span>

**<span data-ttu-id="3ec6a-310">强制： False</span><span class="sxs-lookup"><span data-stu-id="3ec6a-310">Mandatory: False</span></span>**

**<span data-ttu-id="3ec6a-311">类型： String</span><span class="sxs-lookup"><span data-stu-id="3ec6a-311">Type: String</span></span>**

<span data-ttu-id="3ec6a-312">FileDescription 是一个可选标记，可提供可执行文件的管理说明。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-312">FileDescription is an optional tag that allows for an administrative description of the executable file.</span></span> <span data-ttu-id="3ec6a-313">这是一个免费的文本字段，在需要标识可执行文件的功能的软件包中的多个可执行文件中非常有用。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-313">This is a free text field and can be useful in distinguishing multiple executables within a software package where there is a need to identify the function of the executable.</span></span>

<span data-ttu-id="3ec6a-314">例如，在一个合适的应用程序中，提供有关两个可执行文件（MyApplication.exe 和 MyApplicationHelper.exe）的功能的提醒可能很有用，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3ec6a-314">For example, in a suited application, it might be useful to provide reminders about the function of two executables (MyApplication.exe and MyApplicationHelper.exe), as shown here:</span></span>

```xml
<Processes>
  <Process>
    <Filename>MyApplication.exe</Filename>
    <FileDescription>My Application Main Engine</ FileDescription>
    <ProductVersion>
      <Major Minimum="6" Maximum="6" />
    </ProductVersion>
  </Process>
  <Process>
    <Filename>MyApplicationHelper.exe</Filename>
    <FileDescription>My Application Background Process Executable</FileDescription>
    <ProductVersion>
      <Major Minimum="6" Maximum="6" />
    </ProductVersion>
  </Process>
</Processes>
```

### <span data-ttu-id="3ec6a-315">ProductVersion</span><span class="sxs-lookup"><span data-stu-id="3ec6a-315">ProductVersion</span></span>

**<span data-ttu-id="3ec6a-316">强制： False</span><span class="sxs-lookup"><span data-stu-id="3ec6a-316">Mandatory: False</span></span>**

**<span data-ttu-id="3ec6a-317">类型： String</span><span class="sxs-lookup"><span data-stu-id="3ec6a-317">Type: String</span></span>**

<span data-ttu-id="3ec6a-318">ProductVersion 是指文件的主要和次要产品版本以及版本和修补程序级别。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-318">ProductVersion refers to the major and minor product versions of a file, as well as a build and patch level.</span></span> <span data-ttu-id="3ec6a-319">ProductVersion 是一个可选元素，但如果指定，它必须至少包含主要子元素。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-319">ProductVersion is an optional element, but if specified, it must contain at least the Major child element.</span></span> <span data-ttu-id="3ec6a-320">此值必须以最小为 = "X" 的最大值 = "Y" 表示区域，其中 X 和 Y 是整数。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-320">The value must express a range in the form Minimum="X" Maximum="Y" where X and Y are integers.</span></span> <span data-ttu-id="3ec6a-321">最小值和最大值可以相同。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-321">The Minimum and Maximum values can be identical.</span></span>

<span data-ttu-id="3ec6a-322">产品和文件版本元素可以保留未指定。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-322">The product and file version elements may be left unspecified.</span></span> <span data-ttu-id="3ec6a-323">这样做会使模板 "版本不限"，这意味着模板将应用于指定的可执行文件的所有版本。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-323">Doing so makes the template “version agnostic”, meaning that the template will apply to all versions of the specified executable.</span></span>

**<span data-ttu-id="3ec6a-324">示例 1：</span><span class="sxs-lookup"><span data-stu-id="3ec6a-324">Example 1:</span></span>**

<span data-ttu-id="3ec6a-325">UE-V 生成器中指定的产品版本：1.0 生成以下 XML：</span><span class="sxs-lookup"><span data-stu-id="3ec6a-325">Product version: 1.0 specified in the UE-V Generator produces the following XML:</span></span>

```xml
<ProductVersion>
  <Major Minimum="1" Maximum="1" />
  <Minor Minimum="0" Maximum="0" />
</ProductVersion>
```

**<span data-ttu-id="3ec6a-326">示例 2：</span><span class="sxs-lookup"><span data-stu-id="3ec6a-326">Example 2:</span></span>**

<span data-ttu-id="3ec6a-327">文件版本： UE-V 生成器中指定的5.0.2.1000 生成以下 XML：</span><span class="sxs-lookup"><span data-stu-id="3ec6a-327">File version: 5.0.2.1000 specified in the UE-V Generator produces the following XML:</span></span>

```xml
<FileVersion>
  <Major Minimum="5" Maximum="5" />
  <Minor Minimum="0" Maximum="0" />
  <Build Minimum="2" Maximum="2" />
  <Patch Minimum="1000" Maximum="1000" />
</FileVersion>
```

**<span data-ttu-id="3ec6a-328">不正确的示例 1-未完成的范围：</span><span class="sxs-lookup"><span data-stu-id="3ec6a-328">Incorrect Example 1 – incomplete range:</span></span>**

<span data-ttu-id="3ec6a-329">仅存在最小属性。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-329">Only the Minimum attribute is present.</span></span> <span data-ttu-id="3ec6a-330">范围中还必须包含 "最大"。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-330">Maximum must be included in a range as well.</span></span>

```xml
<ProductVersion>
  <Major Minimum="2" />
</ProductVersion>
```

**<span data-ttu-id="3ec6a-331">不正确的示例 2-指定的次要元素没有主要元素：</span><span class="sxs-lookup"><span data-stu-id="3ec6a-331">Incorrect Example 2 – Minor specified without Major element:</span></span>**

<span data-ttu-id="3ec6a-332">仅存在次要元素。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-332">Only the Minor element is present.</span></span> <span data-ttu-id="3ec6a-333">还必须包含主版本。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-333">Major must be included as well.</span></span>

```xml
<ProductVersion>
  <Minor Minimum="0" Maximum="0" />
</ProductVersion>
```

### <span data-ttu-id="3ec6a-334">FileVersion</span><span class="sxs-lookup"><span data-stu-id="3ec6a-334">FileVersion</span></span>

**<span data-ttu-id="3ec6a-335">强制： False</span><span class="sxs-lookup"><span data-stu-id="3ec6a-335">Mandatory: False</span></span>**

**<span data-ttu-id="3ec6a-336">类型： String</span><span class="sxs-lookup"><span data-stu-id="3ec6a-336">Type: String</span></span>**

<span data-ttu-id="3ec6a-337">FileVersion 将区分已发布应用程序的发布版本和组件可执行文件的内部生成详细信息。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-337">FileVersion differentiates between the release version of a published application and the internal build details of a component executable.</span></span> <span data-ttu-id="3ec6a-338">对于大多数商业应用程序，这些号码是相同的。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-338">For the majority of commercial applications, these numbers are identical.</span></span> <span data-ttu-id="3ec6a-339">它们的不同之处是，文件的产品版本指示文件的常规版本标识，而文件版本指示文件的特定版本（如修补程序或更新）。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-339">Where they vary, the product version of a file indicates a generic version identification of a file, while file version indicates a specific build of a file (as in the case of a hotfix or update).</span></span> <span data-ttu-id="3ec6a-340">这将在不中断检测逻辑的情况下唯一标识文件。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-340">This uniquely identifies files without breaking detection logic.</span></span>

<span data-ttu-id="3ec6a-341">若要确定特定可执行文件的产品版本和文件版本，请在 Windows 资源管理器中右键单击该文件，选择 "属性"，然后单击 "详细信息" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-341">To determine the product version and file version of a particular executable, right-click on the file in Windows Explorer, select Properties, then click on the Details tab.</span></span>

<span data-ttu-id="3ec6a-342">为应用程序包括 FileVersion 元素可实现更精细的微调检测逻辑，但对于大多数应用程序都不是必需的。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-342">Including a FileVersion element for an application allows for more granular fine-tuning detection logic, but is not necessary for most applications.</span></span> <span data-ttu-id="3ec6a-343">首先检查 ProductVersion 元素设置，然后选中 "FileVersion"。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-343">The ProductVersion element settings are checked first, and then FileVersion is checked.</span></span> <span data-ttu-id="3ec6a-344">将应用更严格的设置。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-344">The more restrictive setting will apply.</span></span>

<span data-ttu-id="3ec6a-345">FileVersion 的子元素和语法规则与 ProductVersion 的子元素和语法规则相同。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-345">The child elements and syntax rules for FileVersion are identical to those of ProductVersion.</span></span>

```xml
<Process>
  <Filename>MSACCESS.EXE</Filename>
  <Architecture>Win32</Architecture>
  <ProductVersion>
    <Major Minimum="14" Maximum="14" />
    <Minor Minimum="0" Maximum="0" />
  </ProductVersion>
  <FileVersion>
    <Major Minimum="14" Maximum="14" />
    <Minor Minimum="0" Maximum="0" />
  </FileVersion>
</Process>
```

### <a href="" id="application21"></a><span data-ttu-id="3ec6a-346">应用程序元素</span><span class="sxs-lookup"><span data-stu-id="3ec6a-346">Application Element</span></span>

<span data-ttu-id="3ec6a-347">应用程序是应用于特定应用程序的设置的容器。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-347">Application is a container for settings that apply to a particular application.</span></span> <span data-ttu-id="3ec6a-348">它是以下字段/类型的集合。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-348">It is a collection of the following fields/types.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="3ec6a-349">字段/类型</span><span class="sxs-lookup"><span data-stu-id="3ec6a-349">Field/Type</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="3ec6a-350">描述</span><span class="sxs-lookup"><span data-stu-id="3ec6a-350">Description</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3ec6a-351">名称</span><span class="sxs-lookup"><span data-stu-id="3ec6a-351">Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-352">为设置位置模板指定一个唯一名称。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-352">Specifies a unique name for the settings location template.</span></span> <span data-ttu-id="3ec6a-353">这用于在 WMI、PowerShell、事件查看器和调试日志中引用模板时的显示用途。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-353">This is used for display purposes when referencing the template in WMI, PowerShell, Event Viewer and debug logs.</span></span> <span data-ttu-id="3ec6a-354">有关详细信息，请参阅 <a href="#name21" data-raw-source="[Name](#name21)"> 名称 </a> 。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-354">For more information, see <a href="#name21" data-raw-source="[Name](#name21)">Name</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3ec6a-355">ID</span><span class="sxs-lookup"><span data-stu-id="3ec6a-355">ID</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-356">填充特定模板的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-356">Populates a unique identifier for a particular template.</span></span> <span data-ttu-id="3ec6a-357">此标记将成为 UE-V Agent 在运行时引用模板时使用的主要标识符。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-357">This tag becomes the primary identifier that the UE-V Agent uses to reference the template at runtime.</span></span> <span data-ttu-id="3ec6a-358">有关详细信息，请参阅 <a href="#id21" data-raw-source="[ID](#id21)"> ID </a> 。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-358">For more information, see <a href="#id21" data-raw-source="[ID](#id21)">ID</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3ec6a-359">描述</span><span class="sxs-lookup"><span data-stu-id="3ec6a-359">Description</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-360">模板的可选说明。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-360">An optional description of the template.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3ec6a-361">LocalizedNames</span><span class="sxs-lookup"><span data-stu-id="3ec6a-361">LocalizedNames</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-362">UI 中显示的可选名称，由语言区域设置本地化。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-362">An optional name displayed in the UI, localized by a language locale.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3ec6a-363">LocalizedDescriptions</span><span class="sxs-lookup"><span data-stu-id="3ec6a-363">LocalizedDescriptions</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-364">由语言区域设置本地化的可选模板说明。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-364">An optional template description localized by a language locale.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3ec6a-365">版本</span><span class="sxs-lookup"><span data-stu-id="3ec6a-365">Version</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-366">标识用于管理更改管理跟踪的设置位置模板的版本。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-366">Identifies the version of the settings location template for administrative tracking of changes.</span></span> <span data-ttu-id="3ec6a-367">有关详细信息，请参阅 <a href="#version21" data-raw-source="[Version](#version21)"> 版本 </a> 。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-367">For more information, see <a href="#version21" data-raw-source="[Version](#version21)">Version</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3ec6a-368">DeferToMSAccount</span><span class="sxs-lookup"><span data-stu-id="3ec6a-368">DeferToMSAccount</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-369">控制是否与 Microsoft 帐户一起启用此模板。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-369">Controls whether this template is enabled in conjunction with a Microsoft account or not.</span></span> <span data-ttu-id="3ec6a-370">如果对计算机上的用户启用了 MSA 同步，则该模板将自动禁用。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-370">If MSA syncing is enabled for a user on a machine, then this template will automatically be disabled.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3ec6a-371">DeferToOffice365</span><span class="sxs-lookup"><span data-stu-id="3ec6a-371">DeferToOffice365</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-372">与 MSA 类似，它控制此模板是否与 Office365 一起启用。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-372">Similar to MSA, this controls whether this template is enabled in conjunction with Office365.</span></span> <span data-ttu-id="3ec6a-373">如果使用 Office 365 同步设置，此模板将自动禁用。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-373">If Office 365 is being used to sync settings, this template will automatically be disabled.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3ec6a-374">FixedProfile （在2.1 中引入）</span><span class="sxs-lookup"><span data-stu-id="3ec6a-374">FixedProfile (Introduced in 2.1)</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-375">指定此模板只能与此元素中指定的配置文件关联，并且不能通过 WMI 或 PowerShell 进行更改。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-375">Specifies that this template can only be associated with the profile specified within this element, and cannot be changed via WMI or PowerShell.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3ec6a-376">进程</span><span class="sxs-lookup"><span data-stu-id="3ec6a-376">Processes</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-377">一个容器，用于一个或多个流程元素的集合。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-377">A container for a collection of one or more Process elements.</span></span> <span data-ttu-id="3ec6a-378">有关详细信息，请参阅 <a href="#processes21" data-raw-source="[Processes](#processes21)"> 流程 </a> 。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-378">For more information, see <a href="#processes21" data-raw-source="[Processes](#processes21)">Processes</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3ec6a-379">设置</span><span class="sxs-lookup"><span data-stu-id="3ec6a-379">Settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-380">适用于特定模板的所有设置的容器。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-380">A container for all the settings that apply to a particular template.</span></span> <span data-ttu-id="3ec6a-381">它包含注册表、File、SystemParameter 和 CustomAction 设置的实例。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-381">It contains instances of the Registry, File, SystemParameter, and CustomAction settings.</span></span> <span data-ttu-id="3ec6a-382">有关详细信息，请 <strong> 参阅 </strong> 数据类型中的设置 <a href="#data21" data-raw-source="[Data types](#data21)"> </a> 。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-382">For more information, see <strong>Settings</strong> in <a href="#data21" data-raw-source="[Data types](#data21)">Data types</a>.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="common21"></a><span data-ttu-id="3ec6a-383">常见元素</span><span class="sxs-lookup"><span data-stu-id="3ec6a-383">Common Element</span></span>

<span data-ttu-id="3ec6a-384">常用于应用程序元素，但它始终与两个或更多个应用程序元素关联。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-384">Common is similar to an Application element, but it is always associated with two or more Application elements.</span></span> <span data-ttu-id="3ec6a-385">"常见" 部分表示在这些应用程序实例之间共享的一组设置。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-385">The Common section represents the set of settings that are shared between those Application instances.</span></span> <span data-ttu-id="3ec6a-386">它是以下字段/类型的集合。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-386">It is a collection of the following fields/types.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="3ec6a-387">字段/类型</span><span class="sxs-lookup"><span data-stu-id="3ec6a-387">Field/Type</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="3ec6a-388">描述</span><span class="sxs-lookup"><span data-stu-id="3ec6a-388">Description</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3ec6a-389">名称</span><span class="sxs-lookup"><span data-stu-id="3ec6a-389">Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-390">为设置位置模板指定一个唯一名称。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-390">Specifies a unique name for the settings location template.</span></span> <span data-ttu-id="3ec6a-391">这用于在 WMI、PowerShell、事件查看器和调试日志中引用模板时的显示用途。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-391">This is used for display purposes when referencing the template in WMI, PowerShell, Event Viewer and debug logs.</span></span> <span data-ttu-id="3ec6a-392">有关详细信息，请参阅 <a href="#name21" data-raw-source="[Name](#name21)"> 名称 </a> 。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-392">For more information, see <a href="#name21" data-raw-source="[Name](#name21)">Name</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3ec6a-393">ID</span><span class="sxs-lookup"><span data-stu-id="3ec6a-393">ID</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-394">填充特定模板的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-394">Populates a unique identifier for a particular template.</span></span> <span data-ttu-id="3ec6a-395">此标记将成为 UE-V Agent 在运行时引用模板时使用的主要标识符。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-395">This tag becomes the primary identifier that the UE-V Agent uses to reference the template at runtime.</span></span> <span data-ttu-id="3ec6a-396">有关详细信息，请参阅 <a href="#id21" data-raw-source="[ID](#id21)"> ID </a> 。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-396">For more information, see <a href="#id21" data-raw-source="[ID](#id21)">ID</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3ec6a-397">描述</span><span class="sxs-lookup"><span data-stu-id="3ec6a-397">Description</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-398">模板的可选说明。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-398">An optional description of the template.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3ec6a-399">LocalizedNames</span><span class="sxs-lookup"><span data-stu-id="3ec6a-399">LocalizedNames</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-400">UI 中显示的可选名称，由语言区域设置本地化。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-400">An optional name displayed in the UI, localized by a language locale.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3ec6a-401">LocalizedDescriptions</span><span class="sxs-lookup"><span data-stu-id="3ec6a-401">LocalizedDescriptions</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-402">由语言区域设置本地化的可选模板说明。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-402">An optional template description localized by a language locale.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3ec6a-403">版本</span><span class="sxs-lookup"><span data-stu-id="3ec6a-403">Version</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-404">标识用于管理更改管理跟踪的设置位置模板的版本。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-404">Identifies the version of the settings location template for administrative tracking of changes.</span></span> <span data-ttu-id="3ec6a-405">有关详细信息，请参阅 <a href="#version21" data-raw-source="[Version](#version21)"> 版本 </a> 。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-405">For more information, see <a href="#version21" data-raw-source="[Version](#version21)">Version</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3ec6a-406">DeferToMSAccount</span><span class="sxs-lookup"><span data-stu-id="3ec6a-406">DeferToMSAccount</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-407">控制是否与 Microsoft 帐户一起启用此模板。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-407">Controls whether this template is enabled in conjunction with a Microsoft account or not.</span></span> <span data-ttu-id="3ec6a-408">如果对计算机上的用户启用了 MSA 同步，则该模板将自动禁用。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-408">If MSA syncing is enabled for a user on a machine, then this template will automatically be disabled.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3ec6a-409">DeferToOffice365</span><span class="sxs-lookup"><span data-stu-id="3ec6a-409">DeferToOffice365</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-410">与 MSA 类似，它控制此模板是否与 Office365 一起启用。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-410">Similar to MSA, this controls whether this template is enabled in conjunction with Office365.</span></span> <span data-ttu-id="3ec6a-411">如果使用 Office 365 同步设置，此模板将自动禁用。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-411">If Office 365 is being used to sync settings, this template will automatically be disabled.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3ec6a-412">FixedProfile （在2.1 中引入）</span><span class="sxs-lookup"><span data-stu-id="3ec6a-412">FixedProfile (Introduced in 2.1)</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-413">指定此模板只能与此元素中指定的配置文件关联，并且不能通过 WMI 或 PowerShell 进行更改。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-413">Specifies that this template can only be associated with the profile specified within this element, and cannot be changed via WMI or PowerShell.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3ec6a-414">设置</span><span class="sxs-lookup"><span data-stu-id="3ec6a-414">Settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-415">适用于特定模板的所有设置的容器。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-415">A container for all the settings that apply to a particular template.</span></span> <span data-ttu-id="3ec6a-416">它包含注册表、File、SystemParameter 和 CustomAction 设置的实例。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-416">It contains instances of the Registry, File, SystemParameter, and CustomAction settings.</span></span> <span data-ttu-id="3ec6a-417">有关详细信息，请 <strong> 参阅 </strong> 数据类型中的设置 <a href="#data21" data-raw-source="[Data types](#data21)"> </a> 。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-417">For more information, see <strong>Settings</strong> in <a href="#data21" data-raw-source="[Data types](#data21)">Data types</a>.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="settingslocationtemplate21"></a><span data-ttu-id="3ec6a-418">SettingsLocationTemplate 元素</span><span class="sxs-lookup"><span data-stu-id="3ec6a-418">SettingsLocationTemplate Element</span></span>

<span data-ttu-id="3ec6a-419">此元素定义单个应用程序或一组应用程序的设置。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-419">This element defines the settings for a single application or a suite of applications.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="3ec6a-420">字段/类型</span><span class="sxs-lookup"><span data-stu-id="3ec6a-420">Field/Type</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="3ec6a-421">描述</span><span class="sxs-lookup"><span data-stu-id="3ec6a-421">Description</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3ec6a-422">名称</span><span class="sxs-lookup"><span data-stu-id="3ec6a-422">Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-423">为设置位置模板指定一个唯一名称。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-423">Specifies a unique name for the settings location template.</span></span> <span data-ttu-id="3ec6a-424">这用于在 WMI、PowerShell、事件查看器和调试日志中引用模板时的显示用途。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-424">This is used for display purposes when referencing the template in WMI, PowerShell, Event Viewer and debug logs.</span></span> <span data-ttu-id="3ec6a-425">有关详细信息，请参阅 <a href="#name21" data-raw-source="[Name](#name21)"> 名称 </a> 。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-425">For more information, see <a href="#name21" data-raw-source="[Name](#name21)">Name</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3ec6a-426">ID</span><span class="sxs-lookup"><span data-stu-id="3ec6a-426">ID</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-427">填充特定模板的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-427">Populates a unique identifier for a particular template.</span></span> <span data-ttu-id="3ec6a-428">此标记将成为 UE-V Agent 在运行时引用模板时使用的主要标识符。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-428">This tag becomes the primary identifier that the UE-V Agent uses to reference the template at runtime.</span></span> <span data-ttu-id="3ec6a-429">有关详细信息，请参阅 <a href="#id21" data-raw-source="[ID](#id21)"> ID </a> 。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-429">For more information, see <a href="#id21" data-raw-source="[ID](#id21)">ID</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3ec6a-430">描述</span><span class="sxs-lookup"><span data-stu-id="3ec6a-430">Description</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-431">模板的可选说明。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-431">An optional description of the template.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3ec6a-432">LocalizedNames</span><span class="sxs-lookup"><span data-stu-id="3ec6a-432">LocalizedNames</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-433">UI 中显示的可选名称，由语言区域设置本地化。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-433">An optional name displayed in the UI, localized by a language locale.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3ec6a-434">LocalizedDescriptions</span><span class="sxs-lookup"><span data-stu-id="3ec6a-434">LocalizedDescriptions</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-435">由语言区域设置本地化的可选模板说明。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-435">An optional template description localized by a language locale.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="appendix21"></a><span data-ttu-id="3ec6a-436">附录： SettingsLocationTemplate</span><span class="sxs-lookup"><span data-stu-id="3ec6a-436">Appendix: SettingsLocationTemplate.xsd</span></span>

<span data-ttu-id="3ec6a-437">下面是显示其元素、子元素、属性和参数的 SettingsLocationTemplate 文件：</span><span class="sxs-lookup"><span data-stu-id="3ec6a-437">Here is the SettingsLocationTemplate.xsd file showing its elements, child elements, attributes, and parameters:</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema id="UevSettingsLocationTemplate"
  targetNamespace="https://schemas.microsoft.com/UserExperienceVirtualization/2013A/SettingsLocationTemplate"
  elementFormDefault="qualified"
  xmlns="https://schemas.microsoft.com/UserExperienceVirtualization/2013A/SettingsLocationTemplate"
  xmlns:mstns="https://schemas.microsoft.com/UserExperienceVirtualization/2013A/SettingsLocationTemplate"
  xmlns:xs="http://www.w3.org/2001/XMLSchema">

    <xs:simpleType name="Guid">
        <xs:restriction base="xs:string">
            <xs:pattern value="\{[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{12}\}" />
        </xs:restriction>
    </xs:simpleType>

    <xs:simpleType name="FilenameString">
        <xs:restriction base="xs:string">
            <xs:pattern value="[^\\\?\*\|&lt;&gt;/:]+" />
        </xs:restriction>
    </xs:simpleType>

    <xs:simpleType name="IDString">
        <xs:restriction base="xs:string">
            <xs:pattern value="[^\\\?\*\|&lt;&gt;/:.]+" />
        </xs:restriction>
    </xs:simpleType>

    <xs:simpleType name="CompositeIDString">
        <xs:restriction base="xs:string">
            <xs:pattern value="[^\\\?\*\|&lt;&gt;/:.]+([.][^\\\?\*\|&lt;&gt;/:.]+)?" />
        </xs:restriction>
    </xs:simpleType>

    <xs:simpleType name="TemplateVersion">
        <xs:restriction base="xs:integer">
            <xs:minInclusive value="0" />
            <xs:maxInclusive value="2147483647" />
        </xs:restriction>
    </xs:simpleType>

    <xs:complexType name="Empty">
        <xs:sequence/>
    </xs:complexType>

    <xs:complexType name="LocalizedString">
        <xs:simpleContent>
            <xs:extension base="xs:string">
                <xs:attribute name="Locale" type="xs:string" use="required"/>
            </xs:extension>
        </xs:simpleContent>
    </xs:complexType>

    <xs:complexType name="LocalizedName">
        <xs:sequence>
            <xs:element name="Name" type="LocalizedString" minOccurs="1" maxOccurs="unbounded" />
        </xs:sequence>
    </xs:complexType>

    <xs:complexType name="LocalizedDescription">
        <xs:sequence>
            <xs:element name="Description" type="LocalizedString" minOccurs="1" maxOccurs="unbounded" />
        </xs:sequence>
    </xs:complexType>

    <xs:complexType name="ReplacedTemplates">
      <xs:sequence>
        <xs:element name="ID" type="CompositeIDString" minOccurs="1" maxOccurs="unbounded" />
    </xs:sequence>
    </xs:complexType>

    <xs:complexType name="Author">
        <xs:all>
            <xs:element name="Name" type="xs:string" minOccurs="1" />
            <xs:element name="Email" type="xs:string" minOccurs="0" />
        </xs:all>
    </xs:complexType>

    <xs:complexType name="Range">
        <xs:attribute name="Minimum" type="xs:integer" use="required"/>
        <xs:attribute name="Maximum" type="xs:integer" use="required"/>
    </xs:complexType>

    <xs:complexType name="ProcessVersion">
        <xs:sequence>
            <xs:element name="Major" type="Range" minOccurs="1" />
            <xs:element name="Minor" type="Range" minOccurs="0" />
            <xs:element name="Build" type="Range" minOccurs="0" />
            <xs:element name="Patch" type="Range" minOccurs="0" />
        </xs:sequence>
    </xs:complexType>

    <xs:simpleType name="Architecture">
        <xs:restriction base="xs:string">
            <xs:enumeration value="Win32"/>
            <xs:enumeration value="Win64"/>
        </xs:restriction>
    </xs:simpleType>

    <xs:complexType name="Process">
        <xs:sequence>
            <xs:element name="Filename" type="FilenameString" minOccurs="1" />
            <xs:element name="Architecture" type="Architecture" minOccurs="0" />
            <xs:element name="ProductName" type="xs:string" minOccurs="0" />
            <xs:element name="FileDescription" type="xs:string" minOccurs="0" />
            <xs:element name="ProductVersion" type="ProcessVersion" minOccurs="0" maxOccurs="unbounded"/>
            <xs:element name="FileVersion" type="ProcessVersion" minOccurs="0" maxOccurs="unbounded"/>
        </xs:sequence>
    </xs:complexType>

    <xs:complexType name="Processes">
        <xs:sequence>
            <xs:choice minOccurs="1">
                <xs:element name="Process" type="Process" />
                <xs:element name="ShellProcess" type="Empty" />
            </xs:choice>
            <xs:element name="Process" type="Process" minOccurs="0" maxOccurs="unbounded" />
        </xs:sequence>
    </xs:complexType>

    <xs:complexType name="Path">
        <xs:simpleContent>
            <xs:extension base="xs:string">
                <xs:attribute name="Recursive" type="xs:boolean" default="false"/>
                <xs:attribute name="DeleteIfNotFound" type="xs:boolean" default="false"/>
            </xs:extension>
        </xs:simpleContent>
    </xs:complexType>

    <xs:complexType name="RegistrySetting">
        <xs:sequence>
            <xs:element name="Path" type="Path" />
            <xs:element name="Name" type="xs:string" minOccurs="0" maxOccurs="unbounded" />
            <xs:element name="Exclude" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                    <xs:sequence>
                        <xs:element name="Path" type="Path" minOccurs="0" />
                        <xs:element name="Name" type="xs:string" minOccurs="0" maxOccurs="unbounded" />
                    </xs:sequence>
                </xs:complexType>
            </xs:element>
        </xs:sequence>
    </xs:complexType>

    <xs:complexType name="FileSetting">
        <xs:sequence>

            <xs:element name="Root">
                <xs:complexType>
                    <xs:choice>
                        <xs:element name="KnownFolder" type="Guid" />
                        <xs:element name="RegistryEntry" type="xs:string" />
                        <xs:element name="EnvironmentVariable" type="xs:string" />
                    </xs:choice>
                </xs:complexType>
            </xs:element>

            <xs:element name="Path" minOccurs="0" type="Path" />
            <xs:element name="FileMask" type="xs:string" minOccurs="0" maxOccurs="unbounded"/>

            <xs:element name="Exclude" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                    <xs:sequence>
                        <xs:element name="Path" type="Path" minOccurs="0" />
                        <xs:element name="FileMask" type="xs:string" minOccurs="0" maxOccurs="unbounded" />
                    </xs:sequence>
                </xs:complexType>
            </xs:element>

        </xs:sequence>
    </xs:complexType>

    <xs:simpleType name="CustomActionSetting">
        <xs:restriction base="xs:anyURI"/>
    </xs:simpleType>

    <xs:simpleType name="SystemParameterSetting">
        <xs:restriction base="xs:string">

            <!-- Accessibility parameters -->
            <xs:enumeration value="AccessTimeout"/>
            <xs:enumeration value="AudioDescription"/>
            <xs:enumeration value="ClientAreaAnimation"/>
            <xs:enumeration value="DisableOverlappedContent"/>
            <xs:enumeration value="FilterKeys"/>
            <xs:enumeration value="FocusBorderHeight"/>
            <xs:enumeration value="FocusBorderWidth"/>
            <xs:enumeration value="HighContrast"/>
            <xs:enumeration value="MessageDuration"/>
            <xs:enumeration value="MouseClickLock"/>
            <xs:enumeration value="MouseClickLockTime"/>
            <xs:enumeration value="MouseKeys"/>
            <xs:enumeration value="MouseSonar"/>
            <xs:enumeration value="MouseVanish"/>
            <xs:enumeration value="ScreenReader"/>
            <xs:enumeration value="ShowSounds"/>
            <xs:enumeration value="SoundSentry"/>
            <xs:enumeration value="StickyKeys"/>
            <xs:enumeration value="ToggleKeys"/>

            <!-- Input parameters -->
            <xs:enumeration value="Beep"/>
            <xs:enumeration value="BlockSendInputResets"/>
            <xs:enumeration value="DefaultInputLang"/>
            <xs:enumeration value="DoubleClickTime"/>
            <xs:enumeration value="DoubleClkHeight"/>
            <xs:enumeration value="DoubleClkWidth"/>
            <xs:enumeration value="KeyboardCues"/>
            <xs:enumeration value="KeyboardDelay"/>
            <xs:enumeration value="KeyboardPref"/>
            <xs:enumeration value="KeyboardSpeed"/>
            <xs:enumeration value="Mouse"/>
            <xs:enumeration value="MouseButtonSwap"/>
            <xs:enumeration value="MouseHoverHeight"/>
            <xs:enumeration value="MouseHoverTime"/>
            <xs:enumeration value="MouseHoverWidth"/>
            <xs:enumeration value="MouseSpeed"/>
            <xs:enumeration value="MouseTrails"/>
            <xs:enumeration value="SnapToDefButton"/>
            <xs:enumeration value="WheelScrollChars"/>
            <xs:enumeration value="WheelScrollLines"/>

            <!-- Desktop parameters (limited subset) -->
            <xs:enumeration value="DeskWallpaper"/>
            <xs:enumeration value="DesktopColor"/>

        </xs:restriction>
    </xs:simpleType>

    <xs:complexType name="Settings">
        <xs:sequence>
            <xs:element name="Asynchronous" type="xs:boolean" minOccurs="0" />
            <xs:element name="PreventOverlappingSynchronization" type="xs:boolean" minOccurs="0" />
            <xs:element name="AlwaysApplySettings" type="xs:boolean" minOccurs="0" />
            <xs:choice minOccurs="0" maxOccurs="unbounded">
                <xs:element name="Registry" type="RegistrySetting" />
                <xs:element name="File" type="FileSetting" />
                <xs:element name="SystemParameter" type="SystemParameterSetting" />
                <xs:element name="CustomAction" type="CustomActionSetting" />
            </xs:choice>
        </xs:sequence>
    </xs:complexType>

    <xs:complexType name="Common">
        <xs:sequence>
            <xs:element name="Name" type="xs:string" />
            <xs:element name="ID" type="IDString" />
            <xs:element name="ReplacedTemplates" type="ReplacedTemplates" minOccurs="0" />
            <xs:element name="Description" type="xs:string" minOccurs="0" />
            <xs:element name="LocalizedNames" type="LocalizedName" minOccurs="0" />
            <xs:element name="LocalizedDescriptions" type="LocalizedDescription" minOccurs="0" />
            <xs:element name="Version" type="xs:integer" />
            <xs:element name="DeferToMSAccount" type="Empty"  minOccurs="0" />
            <xs:element name="DeferToOffice365" type="Empty" minOccurs="0" />
            <xs:element name="Settings" type="Settings" />
        </xs:sequence>
    </xs:complexType>

    <xs:complexType name="Application">
        <xs:sequence>
            <xs:element name="Name" type="xs:string" />
            <xs:element name="ID" type="IDString" />
            <xs:element name="ReplacedTemplates" type="ReplacedTemplates" minOccurs="0" />
            <xs:element name="Description" type="xs:string" minOccurs="0" />
            <xs:element name="LocalizedNames" type="LocalizedName" minOccurs="0" />
            <xs:element name="LocalizedDescriptions" type="LocalizedDescription" minOccurs="0" />
            <xs:element name="Version" type="xs:integer" />
            <xs:element name="DeferToMSAccount" type="Empty"  minOccurs="0" />
            <xs:element name="DeferToOffice365" type="Empty" minOccurs="0" />
            <xs:element name="Processes" type="Processes" />
            <xs:element name="Settings" type="Settings" />
        </xs:sequence>
    </xs:complexType>


    <xs:element name="SettingsLocationTemplate">
        <xs:complexType>
            <xs:sequence>

                <xs:element name="Name" type="xs:string" />
                <xs:element name="ID" type="IDString" />
                <xs:element name="Description" type="xs:string" minOccurs="0" />
                <xs:element name="LocalizedNames" type="LocalizedName" minOccurs="0" />
                <xs:element name="LocalizedDescriptions" type="LocalizedDescription" minOccurs="0" />

                <xs:choice>

                    <!-- Single application -->
                    <xs:sequence>
                        <xs:element name="ReplacedTemplates" type="ReplacedTemplates" minOccurs="0" />
                        <xs:element name="Version" type="TemplateVersion" />
                        <xs:element name="Author" type="Author" minOccurs="0" />
                        <xs:element name="FixedProfile" type="xs:string"  minOccurs="0" />
                        <xs:element name="DeferToMSAccount" type="Empty"  minOccurs="0" />
                        <xs:element name="DeferToOffice365" type="Empty" minOccurs="0" />
                        <xs:element name="Processes" type="Processes" />
                        <xs:element name="Settings" type="Settings" />
                    </xs:sequence>

                    <!-- Suite of applications -->
                    <xs:sequence>
                        <xs:element name="ManageSuiteOnly" type="xs:boolean" minOccurs="0" />
                        <xs:element name="Author" type="Author" minOccurs="0" />
                        <xs:element name="FixedProfile" type="xs:string"  minOccurs="0" />
                        <xs:element name="Common" type="Common" />
                        <xs:element name="Application" type="Application" minOccurs="2" maxOccurs="unbounded" />
                    </xs:sequence>

                </xs:choice>

            </xs:sequence>
        </xs:complexType>
    </xs:element>
    <!-- SettingsLocationTemplate -->

</xs:schema>
```

## <span data-ttu-id="3ec6a-438">UE-V 2.0 应用程序模板架构参考</span><span class="sxs-lookup"><span data-stu-id="3ec6a-438">UE-V 2.0 Application Template Schema Reference</span></span>


<span data-ttu-id="3ec6a-439">本节详细介绍了 UE-V 2.0 设置位置模板的 XML 结构，并提供了编辑此文件的指南。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-439">This section details the XML structure of the UE-V 2.0 settings location template and provides guidance for editing this file.</span></span>

### <span data-ttu-id="3ec6a-440">本部分内容</span><span class="sxs-lookup"><span data-stu-id="3ec6a-440">In This Section</span></span>

-   [<span data-ttu-id="3ec6a-441">XML 声明和编码属性</span><span class="sxs-lookup"><span data-stu-id="3ec6a-441">XML Declaration and Encoding Attribute</span></span>](#xml)

-   [<span data-ttu-id="3ec6a-442">命名空间和根元素</span><span class="sxs-lookup"><span data-stu-id="3ec6a-442">Namespace and Root Element</span></span>](#namespace)

-   [<span data-ttu-id="3ec6a-443">数据类型</span><span class="sxs-lookup"><span data-stu-id="3ec6a-443">Data types</span></span>](#data)

-   [<span data-ttu-id="3ec6a-444">名称元素</span><span class="sxs-lookup"><span data-stu-id="3ec6a-444">Name Element</span></span>](#name)

-   [<span data-ttu-id="3ec6a-445">ID 元素</span><span class="sxs-lookup"><span data-stu-id="3ec6a-445">ID Element</span></span>](#id)

-   [<span data-ttu-id="3ec6a-446">版本元素</span><span class="sxs-lookup"><span data-stu-id="3ec6a-446">Version Element</span></span>](#version)

-   [<span data-ttu-id="3ec6a-447">作者元素</span><span class="sxs-lookup"><span data-stu-id="3ec6a-447">Author Element</span></span>](#author)

-   [<span data-ttu-id="3ec6a-448">进程和进程元素</span><span class="sxs-lookup"><span data-stu-id="3ec6a-448">Processes and Process Element</span></span>](#processes)

-   [<span data-ttu-id="3ec6a-449">应用程序元素</span><span class="sxs-lookup"><span data-stu-id="3ec6a-449">Application Element</span></span>](#application)

-   [<span data-ttu-id="3ec6a-450">常见元素</span><span class="sxs-lookup"><span data-stu-id="3ec6a-450">Common Element</span></span>](#common)

-   [<span data-ttu-id="3ec6a-451">SettingsLocationTemplate 元素</span><span class="sxs-lookup"><span data-stu-id="3ec6a-451">SettingsLocationTemplate Element</span></span>](#settingslocationtemplate)

-   [<span data-ttu-id="3ec6a-452">附录： SettingsLocationTemplate</span><span class="sxs-lookup"><span data-stu-id="3ec6a-452">Appendix: SettingsLocationTemplate.xsd</span></span>](#appendix)

### <a href="" id="xml"></a><span data-ttu-id="3ec6a-453">XML 声明和编码属性</span><span class="sxs-lookup"><span data-stu-id="3ec6a-453">XML Declaration and Encoding Attribute</span></span>

**<span data-ttu-id="3ec6a-454">强制： True</span><span class="sxs-lookup"><span data-stu-id="3ec6a-454">Mandatory: True</span></span>**

**<span data-ttu-id="3ec6a-455">类型： String</span><span class="sxs-lookup"><span data-stu-id="3ec6a-455">Type: String</span></span>**

<span data-ttu-id="3ec6a-456">XML 声明必须指定 XML 版本1.0 属性（ &lt; ？ xml version = "1.0" &gt; ）。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-456">The XML declaration must specify the XML version 1.0 attribute (&lt;?xml version="1.0"&gt;).</span></span> <span data-ttu-id="3ec6a-457">由 UE-V 生成器创建的设置位置模板将保存为 UTF-8 编码，尽管编码没有明确指定。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-457">Settings location templates created by the UE-V Generator are saved in UTF-8 encoding, although the encoding is not explicitly specified.</span></span> <span data-ttu-id="3ec6a-458">我们建议你在此元素中将 encoding = "UTF-8" 属性作为最佳做法包括在内。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-458">We recommend that you include the encoding="UTF-8" attribute in this element as a best practice.</span></span> <span data-ttu-id="3ec6a-459">本产品附带的所有模板也都指定了此标记（请参阅%ProgramFiles%\\Microsoft 用户体验 Virtualization\\Templates 中的文档以了解参考）。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-459">All templates included with the product specify this tag as well (see the documents in %ProgramFiles%\\Microsoft User Experience Virtualization\\Templates for reference).</span></span> <span data-ttu-id="3ec6a-460">例如：</span><span class="sxs-lookup"><span data-stu-id="3ec6a-460">For example:</span></span>

`<?xml version="1.0" encoding="UTF-8"?>`

### <a href="" id="namespace"></a><span data-ttu-id="3ec6a-461">命名空间和根元素</span><span class="sxs-lookup"><span data-stu-id="3ec6a-461">Namespace and Root Element</span></span>

**<span data-ttu-id="3ec6a-462">强制： True</span><span class="sxs-lookup"><span data-stu-id="3ec6a-462">Mandatory: True</span></span>**

**<span data-ttu-id="3ec6a-463">类型： String</span><span class="sxs-lookup"><span data-stu-id="3ec6a-463">Type: String</span></span>**

<span data-ttu-id="3ec6a-464">UE-V 使用 https://schemas.microsoft.com/UserExperienceVirtualization/2012/SettingsLocationTemplate 所有应用程序的命名空间。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-464">UE-V uses the https://schemas.microsoft.com/UserExperienceVirtualization/2012/SettingsLocationTemplate namespace for all applications.</span></span> <span data-ttu-id="3ec6a-465">SettingsLocationTemplate 是根元素，包含所有其他元素。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-465">SettingsLocationTemplate is the root element and contains all other elements.</span></span> <span data-ttu-id="3ec6a-466">使用此标记的所有模板中的引用 SettingsLocationTemplate：</span><span class="sxs-lookup"><span data-stu-id="3ec6a-466">Reference SettingsLocationTemplate in all templates using this tag:</span></span>

`<SettingsLocationTemplate xmlns='https://schemas.microsoft.com/UserExperienceVirtualization/2012/SettingsLocationTemplate'>`

### <a href="" id="data"></a><span data-ttu-id="3ec6a-467">数据类型</span><span class="sxs-lookup"><span data-stu-id="3ec6a-467">Data types</span></span>

<span data-ttu-id="3ec6a-468">以下是 UE-V 应用程序模板架构的数据类型。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-468">These are the data types for the UE-V application template schema.</span></span>

<a href="" id="guid"></a><span data-ttu-id="3ec6a-469">**GUID**GUID 描述一个标准的全局唯一标识符正则表达式，格式为 "\\ {\ [a-F0 \] {8} -\ [a – fa-F0-9 \] {4} [a-Fa-F0 \] {4} -\ [a – F0-9 \] \ [a-- {4} F0-9 \] {12} \}"。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-469">**GUID** GUID describes a standard globally unique identifier regular expression in the form "\\{\[a-fA-F0-9\]{8}-\[a-fA-F0-9\]{4}-\[a-fA-F0-9\]{4}-\[a-fA-F0-9\]{4}-\[a-fA-F0-9\]{12}\\}".</span></span> <span data-ttu-id="3ec6a-470">在 Filesetting\\Root\\KnownFolder 元素中使用此功能来验证已知文件夹的格式。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-470">This is used in the Filesetting\\Root\\KnownFolder element to verify the formatting of well-known folders.</span></span>

<a href="" id="filenamestring"></a><span data-ttu-id="3ec6a-471">**FilenameString**FilenameString 是指要监视的进程的文件名。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-471">**FilenameString** FilenameString refers to the file name of a process to be monitored.</span></span> <span data-ttu-id="3ec6a-472">它的值受 regex \ [^ \ \ \ \ \* &lt; &gt; \？/： \] +，（也就是说，它们不能包含反斜杠字符、星号或问号通配符、管道字符、大于或小于符号、正斜杠或冒号字符）。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-472">Its values are restricted by the regex \[^\\\\\\?\\\*\\|&lt;&gt;/:\]+, (that is, they may not contain backslash characters, asterisk or question mark wild-card characters, the pipe character, the greater than or less than sign, forward slash, or colon characters).</span></span>

<a href="" id="idstring"></a><span data-ttu-id="3ec6a-473">**IDString**IDString 是指应用程序元素、SettingsLocationTemplate 和常见元素（用于描述共享通用设置的应用程序套件）的 ID 值。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-473">**IDString** IDString refers to the ID value of Application elements, SettingsLocationTemplate, and Common elements (used to describe application suites that share common settings).</span></span> <span data-ttu-id="3ec6a-474">它受与 FilenameString 相同的正则表达式的限制（\ [^ \ \ \ \ \* \ \ \* &lt; &gt; \/:\]+).</span><span class="sxs-lookup"><span data-stu-id="3ec6a-474">It is restricted by the same regex as FilenameString (\[^\\\\\\?\\\*\\|&lt;&gt;/:\]+).</span></span>

<a href="" id="templateversion"></a><span data-ttu-id="3ec6a-475">**TemplateVersion**TemplateVersion 是用于描述设置位置模板的版本的整数值。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-475">**TemplateVersion** TemplateVersion is an integer value used to describe the revision of the settings location template.</span></span> <span data-ttu-id="3ec6a-476">其值的范围可以从0到2147483647。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-476">Its value may range from 0 to 2147483647.</span></span>

<a href="" id="empty"></a><span data-ttu-id="3ec6a-477">**空**空表示空值。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-477">**Empty** Empty refers to a null value.</span></span> <span data-ttu-id="3ec6a-478">此功能在 Process\\ShellProcess 中用于指示没有要监视的进程。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-478">This is used in Process\\ShellProcess to indicate that there is no process to monitor.</span></span> <span data-ttu-id="3ec6a-479">此值不应在任何应用程序模板中使用。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-479">This value should not be used in any application templates.</span></span>

<a href="" id="author"></a><span data-ttu-id="3ec6a-480">**作者**"作者" 数据类型是标识模板作者的复杂类型。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-480">**Author** The Author data type is a complex type that identifies the author of a template.</span></span> <span data-ttu-id="3ec6a-481">它包含两个子元素：**名称**和**电子邮件**。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-481">It contains two child elements: **Name** and **Email**.</span></span> <span data-ttu-id="3ec6a-482">在 "作者" 数据类型中，Name 元素是必需的，而 Email 元素是可选的。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-482">Within the Author data type, the Name element is mandatory while the Email element is optional.</span></span> <span data-ttu-id="3ec6a-483">此类型将在 SettingsLocationTemplate 元素下更详细地进行介绍。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-483">This type is described in more detail under the SettingsLocationTemplate element.</span></span>

<a href="" id="range"></a><span data-ttu-id="3ec6a-484">**区域**Range 定义一个包含两个子元素的整数类：**最小值**和**最大值**。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-484">**Range** Range defines an integer class consisting of two child elements: **Minimum** and **Maximum**.</span></span> <span data-ttu-id="3ec6a-485">此数据类型在 ProcessVersion 数据类型中实现。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-485">This data type is implemented in the ProcessVersion data type.</span></span> <span data-ttu-id="3ec6a-486">如果已指定，则必须同时包含最小值和最大值。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-486">If specified, both Minimum and Maximum values must be included.</span></span>

<a href="" id="processversion"></a><span data-ttu-id="3ec6a-487">**ProcessVersion**ProcessVersion 定义了一个包含四个子元素的类型：**主要**、**次要**、**内部版本**和**修补程序**。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-487">**ProcessVersion** ProcessVersion defines a type with four child elements: **Major**, **Minor**, **Build**, and **Patch**.</span></span> <span data-ttu-id="3ec6a-488">Process 元素使用此数据类型填充其 ProductVersion 和 FileVersion 值。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-488">This data type is used by the Process element to populate its ProductVersion and FileVersion values.</span></span> <span data-ttu-id="3ec6a-489">此类型的数据是一个范围值。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-489">The data for this type is a Range value.</span></span> <span data-ttu-id="3ec6a-490">主要子元素是必需的，而其他元素是可选的。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-490">The Major child element is mandatory and the others are optional.</span></span>

<a href="" id="architecture"></a><span data-ttu-id="3ec6a-491">**体系结构**体系结构枚举两个可能的值： **Win32**和**Win64**。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-491">**Architecture** Architecture enumerates two possible values: **Win32** and **Win64**.</span></span> <span data-ttu-id="3ec6a-492">这些值用于指定进程体系结构。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-492">These values are used to specify process architecture.</span></span>

<a href="" id="process"></a><span data-ttu-id="3ec6a-493">**处理**"流程" 数据类型是用于描述由 UE-V 监视的流程的容器。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-493">**Process** The Process data type is a container used to describe processes to be monitored by UE-V.</span></span> <span data-ttu-id="3ec6a-494">它包含六个子元素： **Filename**、**体系结构**、 **ProductName**、 **FileDescription**、 **ProductVersion**和**FileVersion**。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-494">It contains six child elements: **Filename**, **Architecture**, **ProductName**, **FileDescription**, **ProductVersion**, and **FileVersion**.</span></span> <span data-ttu-id="3ec6a-495">下表详细介绍了每个元素各自的数据类型：</span><span class="sxs-lookup"><span data-stu-id="3ec6a-495">This table details each element’s respective data type:</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3ec6a-496">元素</span><span class="sxs-lookup"><span data-stu-id="3ec6a-496">Element</span></span></th>
<th align="left"><span data-ttu-id="3ec6a-497">数据类型</span><span class="sxs-lookup"><span data-stu-id="3ec6a-497">Data Type</span></span></th>
<th align="left"><span data-ttu-id="3ec6a-498">Mandatory</span><span class="sxs-lookup"><span data-stu-id="3ec6a-498">Mandatory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3ec6a-499">相配</span><span class="sxs-lookup"><span data-stu-id="3ec6a-499">Filename</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-500">FilenameString</span><span class="sxs-lookup"><span data-stu-id="3ec6a-500">FilenameString</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-501">True</span><span class="sxs-lookup"><span data-stu-id="3ec6a-501">True</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3ec6a-502">体系结构</span><span class="sxs-lookup"><span data-stu-id="3ec6a-502">Architecture</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-503">体系结构</span><span class="sxs-lookup"><span data-stu-id="3ec6a-503">Architecture</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-504">False</span><span class="sxs-lookup"><span data-stu-id="3ec6a-504">False</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3ec6a-505">ProductName</span><span class="sxs-lookup"><span data-stu-id="3ec6a-505">ProductName</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-506">字符串</span><span class="sxs-lookup"><span data-stu-id="3ec6a-506">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-507">False</span><span class="sxs-lookup"><span data-stu-id="3ec6a-507">False</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3ec6a-508">FileDescription</span><span class="sxs-lookup"><span data-stu-id="3ec6a-508">FileDescription</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-509">字符串</span><span class="sxs-lookup"><span data-stu-id="3ec6a-509">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-510">False</span><span class="sxs-lookup"><span data-stu-id="3ec6a-510">False</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3ec6a-511">ProductVersion</span><span class="sxs-lookup"><span data-stu-id="3ec6a-511">ProductVersion</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-512">ProcessVersion</span><span class="sxs-lookup"><span data-stu-id="3ec6a-512">ProcessVersion</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-513">False</span><span class="sxs-lookup"><span data-stu-id="3ec6a-513">False</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3ec6a-514">FileVersion</span><span class="sxs-lookup"><span data-stu-id="3ec6a-514">FileVersion</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-515">ProcessVersion</span><span class="sxs-lookup"><span data-stu-id="3ec6a-515">ProcessVersion</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-516">False</span><span class="sxs-lookup"><span data-stu-id="3ec6a-516">False</span></span></p></td>
</tr>
</tbody>
</table>

 

<a href="" id="processes"></a><span data-ttu-id="3ec6a-517">**流程**"流程" 数据类型表示一个容器，用于一个或多个流程元素的集合。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-517">**Processes** The Processes data type represents a container for a collection of one or more Process elements.</span></span> <span data-ttu-id="3ec6a-518">进程序列类型中支持两个子元素： **Process**和**ShellProcess**。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-518">Two child elements are supported in the Processes sequence type: **Process** and **ShellProcess**.</span></span> <span data-ttu-id="3ec6a-519">Process 是 Process 类型的元素，ShellProcess 的数据类型为 Empty。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-519">Process is an element of type Process and ShellProcess is of data type Empty.</span></span> <span data-ttu-id="3ec6a-520">序列中必须至少标识一个项目。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-520">At least one item must be identified in the sequence.</span></span>

<a href="" id="path"></a><span data-ttu-id="3ec6a-521">**路径**RegistrySetting 和 FileSetting 使用 Path 来引用注册表和文件路径。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-521">**Path** Path is consumed by RegistrySetting and FileSetting to refer to registry and file paths.</span></span> <span data-ttu-id="3ec6a-522">此元素支持两个可选属性： **Recursive**和**DeleteIfNotFound**。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-522">This element supports two optional attributes: **Recursive** and **DeleteIfNotFound**.</span></span> <span data-ttu-id="3ec6a-523">两个值均设置为默认值 = "False"。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-523">Both values are set to default=”False”.</span></span>

<span data-ttu-id="3ec6a-524">递归表示文件设置包含路径和所有子文件夹，或者注册表设置包含所有子注册表项。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-524">Recursive indicates that the path and all subfolders are included for file settings or that all child registry keys are included for registry settings.</span></span> <span data-ttu-id="3ec6a-525">在这两种情况下，当前级别的所有项目都包含在捕获的数据中。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-525">In both cases, all items at the current level are included in the data captured.</span></span> <span data-ttu-id="3ec6a-526">对于 FileSettings 对象，指定文件夹中的所有文件都包含在由 UE-V 捕获的数据中，但不包括文件夹。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-526">For a FileSettings object, all files within the specified folder are included in the data captured by UE-V but folders are not included.</span></span> <span data-ttu-id="3ec6a-527">对于注册表路径，将捕获当前路径中的所有值，但不捕获子注册表项。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-527">For registry paths, all values in the current path are captured but child registry keys are not captured.</span></span> <span data-ttu-id="3ec6a-528">在这两种情况下，应注意避免捕获大型数据集或大量项目。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-528">In both cases, care should be taken to avoid capturing large data sets or large numbers of items.</span></span>

<span data-ttu-id="3ec6a-529">DeleteIfNotFound 属性从用户的设置存储路径数据中删除设置。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-529">The DeleteIfNotFound attribute removes the setting from the user’s settings storage path data.</span></span> <span data-ttu-id="3ec6a-530">在从包中删除这些设置将在设置存储路径文件服务器上保存大量磁盘空间时，这可能是理想的情况。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-530">This may be desirable in cases where removing these settings from the package will save a large amount of disk space on the settings storage path file server.</span></span>

<a href="" id="filemask"></a><span data-ttu-id="3ec6a-531">**FileMask**FileMask 仅指定由 Path 定义的文件夹的某些文件类型。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-531">**FileMask** FileMask specifies only certain file types for the folder that is defined by Path.</span></span> <span data-ttu-id="3ec6a-532">例如，Path 可能是 `C:\users\username\files` 且 FileMask 可以 `*.txt` 仅包含文本文件。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-532">For example, Path might be `C:\users\username\files` and FileMask could be `*.txt` to include only text files.</span></span>

<a href="" id="registrysetting"></a><span data-ttu-id="3ec6a-533">**RegistrySetting**RegistrySetting 表示注册表项和值的容器，以及 UE-V Agent 部分相关联的所需行为。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-533">**RegistrySetting** RegistrySetting represents a container for registry keys and values and the associated desired behavior on the part of the UE-V Agent.</span></span> <span data-ttu-id="3ec6a-534">在此类型中定义了四个子元素：**路径**、**名称**、**排除**和值**路径**和**名称**的序列。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-534">Four child elements are defined within this type: **Path**, **Name**, **Exclude**, and a sequence of the values **Path** and **Name**.</span></span>

<a href="" id="filesetting"></a><span data-ttu-id="3ec6a-535">**FileSetting**FileSetting 包含与文件和文件路径相关联的参数。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-535">**FileSetting** FileSetting contains parameters associated with files and files paths.</span></span> <span data-ttu-id="3ec6a-536">定义了四个子元素： **Root**、 **Path**、 **FileMask**和**Exclude**。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-536">Four child elements are defined: **Root**, **Path**, **FileMask**, and **Exclude**.</span></span> <span data-ttu-id="3ec6a-537">根是强制性的，而其他是可选的。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-537">Root is mandatory and the others are optional.</span></span>

<a href="" id="settings"></a><span data-ttu-id="3ec6a-538">**设置**"设置" 是适用于特定模板的所有设置的容器。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-538">**Settings** Settings is a container for all the settings that apply to a particular template.</span></span> <span data-ttu-id="3ec6a-539">它包含前面所述的注册表、文件、SystemParameter 和 CustomAction 设置的实例。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-539">It contains instances of the Registry, File, SystemParameter, and CustomAction settings described earlier.</span></span> <span data-ttu-id="3ec6a-540">此外，它还可以包含包含以下行为的以下子元素：</span><span class="sxs-lookup"><span data-stu-id="3ec6a-540">In addition, it can also contain the following child elements with behaviors described:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3ec6a-541">元素</span><span class="sxs-lookup"><span data-stu-id="3ec6a-541">Element</span></span></th>
<th align="left"><span data-ttu-id="3ec6a-542">描述</span><span class="sxs-lookup"><span data-stu-id="3ec6a-542">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3ec6a-543">异步</span><span class="sxs-lookup"><span data-stu-id="3ec6a-543">Asynchronous</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-544">在不阻止应用程序启动的情况下应用异步设置程序包，以便应用程序在设置仍在应用时启动。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-544">Asynchronous settings packages are applied without blocking the application startup so that the application start proceeds while the settings are still being applied.</span></span> <span data-ttu-id="3ec6a-545">这对于可以异步应用的设置（例如 <code>get/set</code> ，通过 API （如 SystemParameterSetting）很有用。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-545">This is useful for settings that can be applied asynchronously, such as those <code>get/set</code> through an API, like SystemParameterSetting.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3ec6a-546">PreventOverlappingSynchronization</span><span class="sxs-lookup"><span data-stu-id="3ec6a-546">PreventOverlappingSynchronization</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-547">默认情况下，当使用模板的最后一个应用程序实例关闭时，UE-V 仅保存应用程序的设置。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-547">By default, UE-V only saves settings for an application when the last instance of an application using the template is closed.</span></span> <span data-ttu-id="3ec6a-548">当此元素设置为 "false" 时，UE-V 将导出设置，即使应用程序的其他实例正在运行。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-548">When this element is set to ‘false’, UE-V exports the settings even if other instances of an application are running.</span></span> <span data-ttu-id="3ec6a-549">适用的模板（包括常见元素部分的模板）使用此标志可使共享设置始终在应用程序关闭时导出，同时防止应用程序特定的设置在最后一个实例关闭之前导出。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-549">Suited templates – those that include a Common element section– that are shipped with UE-V use this flag to enable shared settings to always export on application close, while preventing application-specific settings from exporting until the last instance is closed.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="name"></a><span data-ttu-id="3ec6a-550">名称元素</span><span class="sxs-lookup"><span data-stu-id="3ec6a-550">Name Element</span></span>

**<span data-ttu-id="3ec6a-551">强制： True</span><span class="sxs-lookup"><span data-stu-id="3ec6a-551">Mandatory: True</span></span>**

**<span data-ttu-id="3ec6a-552">类型： String</span><span class="sxs-lookup"><span data-stu-id="3ec6a-552">Type: String</span></span>**

<span data-ttu-id="3ec6a-553">名称指定设置位置模板的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-553">Name specifies a unique name for the settings location template.</span></span> <span data-ttu-id="3ec6a-554">这用于在 WMI、PowerShell、事件查看器和调试日志中引用模板时的显示用途。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-554">This is used for display purposes when referencing the template in WMI, PowerShell, Event Viewer and debug logs.</span></span> <span data-ttu-id="3ec6a-555">通常，请避免引用版本信息，因为这可以从 ProductVersion 元素中 objected。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-555">In general, avoid referencing version information, as this can be objected from the ProductVersion element.</span></span> <span data-ttu-id="3ec6a-556">例如，指定 " `<Name>My Application</Name>` 而不是" `<Name>My Application 1.1</Name>` 。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-556">For example, specify `<Name>My Application</Name>` rather than `<Name>My Application 1.1</Name>`.</span></span>

<span data-ttu-id="3ec6a-557">**注意** UE-V 不引用外部 Dtd，因此不能使用设置位置模板中的命名实体。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-557">**Note** UE-V does not reference external DTDs, so it is not possible to use named entities in a settings location template.</span></span> <span data-ttu-id="3ec6a-558">例如，不要使用 &reg; 来指注册的商标签名®。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-558">For example, do not use &reg; to refer to the registered trade mark sign ®.</span></span> <span data-ttu-id="3ec6a-559">而是使用规范编号引用包括这些类型的特殊字符，例如 &®字符的 \ #174。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-559">Instead, use canonical numbered references to include these types of special characters, for example, &\#174 for the ® character.</span></span> <span data-ttu-id="3ec6a-560">此规则适用于此文档中的所有字符串值。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-560">This rule applies to all string values in this document.</span></span>

<span data-ttu-id="3ec6a-561"><http://www.w3.org/TR/xhtml1/dtds.html>有关字符实体的完整列表，请参阅。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-561">See <http://www.w3.org/TR/xhtml1/dtds.html> for a complete list of character entities.</span></span> <span data-ttu-id="3ec6a-562">UTF-8 编码的文档可能直接包含 Unicode 字符。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-562">UTF-8-encoded documents may include the Unicode characters directly.</span></span> <span data-ttu-id="3ec6a-563">通过 UE-V 生成器保存模板将自动将字符实体转换为其 Unicode 表示形式。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-563">Saving templates through the UE-V Generator converts character entities to their Unicode representations automatically.</span></span>

 

### <a href="" id="id"></a><span data-ttu-id="3ec6a-564">ID 元素</span><span class="sxs-lookup"><span data-stu-id="3ec6a-564">ID Element</span></span>

**<span data-ttu-id="3ec6a-565">强制： True</span><span class="sxs-lookup"><span data-stu-id="3ec6a-565">Mandatory: True</span></span>**

**<span data-ttu-id="3ec6a-566">类型： String</span><span class="sxs-lookup"><span data-stu-id="3ec6a-566">Type: String</span></span>**

<span data-ttu-id="3ec6a-567">ID 填充特定模板的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-567">ID populates a unique identifier for a particular template.</span></span> <span data-ttu-id="3ec6a-568">此标记将成为 UE-V Agent 在运行时引用模板时使用的主标识符（例如，请参阅 UevTemplate 和 UevTemplateProgram PowerShell cmdlet 的输出）。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-568">This tag becomes the primary identifier that the UE-V Agent uses to reference the template at runtime (for example, see the output of the Get-UevTemplate and Get-UevTemplateProgram PowerShell cmdlets).</span></span> <span data-ttu-id="3ec6a-569">按照约定，此标记不应包含任何空格，从而简化了脚本编写。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-569">By convention, this tag should not contain any spaces, which simplifies scripting.</span></span> <span data-ttu-id="3ec6a-570">应在此元素中指定应用程序的版本号，以便更轻松地标识模板，例如 `<ID>MicrosoftCalculator6</ID>` 或 `<ID>MicrosoftOffice2010Win64</ID>` 。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-570">Version numbers of applications should be specified in this element to allow for easy identification of the template, such as `<ID>MicrosoftCalculator6</ID>` or `<ID>MicrosoftOffice2010Win64</ID>`.</span></span>

### <a href="" id="version"></a><span data-ttu-id="3ec6a-571">版本元素</span><span class="sxs-lookup"><span data-stu-id="3ec6a-571">Version Element</span></span>

**<span data-ttu-id="3ec6a-572">强制： True</span><span class="sxs-lookup"><span data-stu-id="3ec6a-572">Mandatory: True</span></span>**

**<span data-ttu-id="3ec6a-573">类型： Integer</span><span class="sxs-lookup"><span data-stu-id="3ec6a-573">Type: Integer</span></span>**

**<span data-ttu-id="3ec6a-574">最小值：0</span><span class="sxs-lookup"><span data-stu-id="3ec6a-574">Minimum Value: 0</span></span>**

**<span data-ttu-id="3ec6a-575">最大值：2147483647</span><span class="sxs-lookup"><span data-stu-id="3ec6a-575">Maximum Value: 2147483647</span></span>**

<span data-ttu-id="3ec6a-576">版本标识用于管理更改管理跟踪的设置位置模板的版本。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-576">Version identifies the version of the settings location template for administrative tracking of changes.</span></span> <span data-ttu-id="3ec6a-577">每次保存模板时，UE-V 生成器都会自动将该数字递增1。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-577">The UE-V Generator automatically increments this number by one each time the template is saved.</span></span> <span data-ttu-id="3ec6a-578">请注意，此字段必须为整数整数;不允许使用小数值，例如 `<Version>2.5</Version>` 。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-578">Notice that this field must be a whole number integer; fractional values, such as `<Version>2.5</Version>` are not allowed.</span></span>

<span data-ttu-id="3ec6a-579">**提示：** 你可以使用 XML 注释标记保存有关版本更改 `<!-- -->` 的注释，例如：</span><span class="sxs-lookup"><span data-stu-id="3ec6a-579">**Hint:** You can save notes about version changes using XML comment tags `<!-- -->`, for example:</span></span>

```xml
<!--
    Version History

    Version 1 Jul 05, 2012 Initial template created by Generator - Denise@Contoso.com
    Version 2 Jul 31, 2012 Added support for app.exe v2.1.3 - Mark@Contoso.com
    Version 3 Jan 01, 2013 Added font settings support - Mark@Contoso.com
    Version 4 Jan 31, 2013 Added support for plugin settings - Tony@Contoso.com
  -->
<Version>4</Version>
```

<span data-ttu-id="3ec6a-580">**重要提示** 将查询此值，以确定是否应将模板的新版本应用于这些实例中的现有模板：</span><span class="sxs-lookup"><span data-stu-id="3ec6a-580">**Important** This value is queried to determine if a new version of a template should be applied to an existing template in these instances:</span></span>

-   <span data-ttu-id="3ec6a-581">执行计划模板自动更新任务时</span><span class="sxs-lookup"><span data-stu-id="3ec6a-581">When the scheduled Template Auto Update task executes</span></span>

-   <span data-ttu-id="3ec6a-582">当执行 UevTemplate PowerShell cmdlet 时</span><span class="sxs-lookup"><span data-stu-id="3ec6a-582">When the Update-UevTemplate PowerShell cmdlet is executed</span></span>

-   <span data-ttu-id="3ec6a-583">当 microsoft\\uev： SettingsLocationTemplate Update 方法通过 WMI 调用时</span><span class="sxs-lookup"><span data-stu-id="3ec6a-583">When the microsoft\\uev:SettingsLocationTemplate Update method is called through WMI</span></span>

 

### <a href="" id="author"></a><span data-ttu-id="3ec6a-584">作者元素</span><span class="sxs-lookup"><span data-stu-id="3ec6a-584">Author Element</span></span>

**<span data-ttu-id="3ec6a-585">强制： False</span><span class="sxs-lookup"><span data-stu-id="3ec6a-585">Mandatory: False</span></span>**

**<span data-ttu-id="3ec6a-586">类型： String</span><span class="sxs-lookup"><span data-stu-id="3ec6a-586">Type: String</span></span>**

<span data-ttu-id="3ec6a-587">作者标识设置位置模板的创建者。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-587">Author identifies the creator of the settings location template.</span></span> <span data-ttu-id="3ec6a-588">支持两个可选子元素：**名称**和**电子邮件**。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-588">Two optional child elements are supported: **Name** and **Email**.</span></span> <span data-ttu-id="3ec6a-589">这两个属性都是可选的，但如果指定了电子邮件子元素，则它必须附有 Name 元素。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-589">Both attributes are optional, but, if the Email child element is specified, it must be accompanied by the Name element.</span></span> <span data-ttu-id="3ec6a-590">作者指的是 "设置位置" 模板的联系人的全名，电子邮件应该指作者的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-590">Author refers to the full name of the contact for the settings location template, and email should refer to an email address for the author.</span></span> <span data-ttu-id="3ec6a-591">建议在公共发布的模板中包括此信息，例如，在[Ue-v 模板库](https://gallery.technet.microsoft.com/site/search?f%5B0%5D.Type=RootCategory&f%5B0%5D.Value=UE-V)中。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-591">We recommend that you include this information in templates published publicly, for example, on the [UE-V Template Gallery](https://gallery.technet.microsoft.com/site/search?f%5B0%5D.Type=RootCategory&f%5B0%5D.Value=UE-V).</span></span>

### <a href="" id="processes"></a><span data-ttu-id="3ec6a-592">进程和进程元素</span><span class="sxs-lookup"><span data-stu-id="3ec6a-592">Processes and Process Element</span></span>

**<span data-ttu-id="3ec6a-593">强制： True</span><span class="sxs-lookup"><span data-stu-id="3ec6a-593">Mandatory: True</span></span>**

**<span data-ttu-id="3ec6a-594">类型：元素</span><span class="sxs-lookup"><span data-stu-id="3ec6a-594">Type: Element</span></span>**

<span data-ttu-id="3ec6a-595">进程至少包含一个 `<Process>` 元素，该元素又包含以下子元素： **Filename**、**体系结构**、 **ProductName**、 **FileDescription**、 **ProductVersion**和**FileVersion**。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-595">Processes contains at least one `<Process>` element, which in turn contains the following child elements: **Filename**, **Architecture**, **ProductName**, **FileDescription**, **ProductVersion**, and **FileVersion**.</span></span> <span data-ttu-id="3ec6a-596">Filename 子元素是必需的，而其他元素是可选的。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-596">The Filename child element is mandatory and the others are optional.</span></span> <span data-ttu-id="3ec6a-597">完全填充的元素包含与以下示例类似的标记：</span><span class="sxs-lookup"><span data-stu-id="3ec6a-597">A fully populated element contains tags similar to this example:</span></span>

```xml
<Process>
  <Filename>MyApplication.exe</Filename>
  <Architecture>Win64</Architecture>
  <ProductName> MyApplication </ProductName>
  <FileDescription>MyApplication.exe</FileDescription>
  <ProductVersion>
    <Major Minimum="2" Maximum="2" />
    <Minor Minimum="0" Maximum="0" />
    <Build Minimum="0" Maximum="0" />
    <Patch Minimum="5" Maximum="5" />
  </ProductVersion>
  <FileVersion>
    <Major Minimum="2" Maximum="2" />
    <Minor Minimum="0" Maximum="0" />
    <Build Minimum="0" Maximum="0" />
    <Patch Minimum="5" Maximum="5" />
  </FileVersion>
</Process>
```

### <span data-ttu-id="3ec6a-598">相配</span><span class="sxs-lookup"><span data-stu-id="3ec6a-598">Filename</span></span>

**<span data-ttu-id="3ec6a-599">强制： True</span><span class="sxs-lookup"><span data-stu-id="3ec6a-599">Mandatory: True</span></span>**

**<span data-ttu-id="3ec6a-600">类型： String</span><span class="sxs-lookup"><span data-stu-id="3ec6a-600">Type: String</span></span>**

<span data-ttu-id="3ec6a-601">文件名是指在文件系统中显示的可执行文件的实际文件名。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-601">Filename refers to the actual file name of the executable as it appears in the file system.</span></span> <span data-ttu-id="3ec6a-602">此元素指定 UE-V 用于评估模板是否适用于进程的主要条件。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-602">This element specifies the primary criterion that UE-V uses to evaluate whether a template applies to a process or not.</span></span> <span data-ttu-id="3ec6a-603">此元素必须在设置位置模板 XML 中指定。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-603">This element must be specified in the settings location template XML.</span></span>

<span data-ttu-id="3ec6a-604">有效的文件名必须与正则表达式 \ [^ \ &lt; &gt; \ \ \ \/： \] + 时，它们不能包含反斜杠字符、星号或问号通配符、管道字符、大于或小于符号、正斜杠或冒号（\\？）</span><span class="sxs-lookup"><span data-stu-id="3ec6a-604">Valid filenames must not match the regular expression \[^\\\\\\?\\\*\\|&lt;&gt;/:\]+, that is, they may not contain backslash characters, asterisk or question mark wild-card characters, the pipe character, the greater than or less than sign, forward slash, or colon (the \\ ?</span></span> <span data-ttu-id="3ec6a-605">\* |&lt; &gt; /或：个字符。）</span><span class="sxs-lookup"><span data-stu-id="3ec6a-605">\* | &lt; &gt; / or : characters.).</span></span>

<span data-ttu-id="3ec6a-606">**提示：** 若要针对此 regex 测试字符串，请使用 PowerShell 命令窗口并将可执行文件的名称替换为**YourFileName**：</span><span class="sxs-lookup"><span data-stu-id="3ec6a-606">**Hint:** To test a string against this regex, use a PowerShell command window and substitute your executable’s name for **YourFileName**:</span></span>

`"YourFileName.exe" -match  "[\\\?\*\|<>/:]+"`

<span data-ttu-id="3ec6a-607">**True**值表示字符串包含非法字符。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-607">A value of **True** indicates that the string contains illegal characters.</span></span> <span data-ttu-id="3ec6a-608">下面是一些非法值的示例：</span><span class="sxs-lookup"><span data-stu-id="3ec6a-608">Here are some examples of illegal values:</span></span>

-   <span data-ttu-id="3ec6a-609">\\\\server\\share\\program.exe</span><span class="sxs-lookup"><span data-stu-id="3ec6a-609">\\\\server\\share\\program.exe</span></span>

-   <span data-ttu-id="3ec6a-610">程序 \ \* .exe</span><span class="sxs-lookup"><span data-stu-id="3ec6a-610">Program\*.exe</span></span>

-   <span data-ttu-id="3ec6a-611">Pro？ ram.exe</span><span class="sxs-lookup"><span data-stu-id="3ec6a-611">Pro?ram.exe</span></span>

-   <span data-ttu-id="3ec6a-612">程序 &lt; 1 &gt; .exe</span><span class="sxs-lookup"><span data-stu-id="3ec6a-612">Program&lt;1&gt;.exe</span></span>

<span data-ttu-id="3ec6a-613">**注意** UE-V 生成器分别对大于和小于字符进行编码 &gt; &lt; 。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-613">**Note** The UE-V Generator encodes the greater than and less than characters as &gt; and &lt; respectively.</span></span>

 

<span data-ttu-id="3ec6a-614">在极少数情况下，文件名值不一定包含 .exe 扩展名，但应将其指定为值的一部分。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-614">In rare circumstances, the FileName value will not necessarily include the .exe extension, but it should be specified as part of the value.</span></span> <span data-ttu-id="3ec6a-615">例如， `<Filename>MyApplictication.exe</Filename>` 应指定而不是 `<Filename>MyApplictication</Filename>` 。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-615">For example, `<Filename>MyApplictication.exe</Filename>` should be specified instead of `<Filename>MyApplictication</Filename>`.</span></span> <span data-ttu-id="3ec6a-616">如果可执行文件的实际名称为 "MyApplication.exe"，则第二个示例不会将模板应用于该进程。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-616">The second example will not apply the template to the process if the actual name of the executable file is “MyApplication.exe”.</span></span>

### <span data-ttu-id="3ec6a-617">体系结构</span><span class="sxs-lookup"><span data-stu-id="3ec6a-617">Architecture</span></span>

**<span data-ttu-id="3ec6a-618">强制： False</span><span class="sxs-lookup"><span data-stu-id="3ec6a-618">Mandatory: False</span></span>**

**<span data-ttu-id="3ec6a-619">类型：体系结构（字符串）</span><span class="sxs-lookup"><span data-stu-id="3ec6a-619">Type: Architecture (String)</span></span>**

<span data-ttu-id="3ec6a-620">体系结构是指已编译目标可执行文件的处理器体系结构。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-620">Architecture refers to the processor architecture for which the target executable was compiled.</span></span> <span data-ttu-id="3ec6a-621">有效值为32位应用程序的 Win32 或64位应用程序的 Win64。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-621">Valid values are Win32 for 32-bit applications or Win64 for 64-bit applications.</span></span> <span data-ttu-id="3ec6a-622">如果存在，此标记将设置位置模板的适用性限制为特定的应用程序体系结构。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-622">If present, this tag limits the applicability of the settings location template to a particular application architecture.</span></span> <span data-ttu-id="3ec6a-623">有关此操作的示例，请比较%ProgramFiles%\\Microsoft 用户体验 Virtualization\\templates\\ MicrosoftOffice2010Win32.xml 和 UE-V 附带的 MicrosoftOffice2010Win64.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-623">For an example of this, compare the %ProgramFiles%\\Microsoft User Experience Virtualization\\templates\\ MicrosoftOffice2010Win32.xml and MicrosoftOffice2010Win64.xml files included with UE-V.</span></span> <span data-ttu-id="3ec6a-624">如果相对路径在不同版本的可执行文件之间更改，或者在从一个处理器体系结构移动到另一个时已添加或删除了设置，此方法将非常有用。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-624">This is useful when relative paths change between different versions of an executable or if settings have been added or removed when moving from one processor architecture to another.</span></span>

<span data-ttu-id="3ec6a-625">如果此元素不存在，则设置位置模板将忽略进程的体系结构，并将其应用于32和64位进程（如果应用了文件名和其他属性）。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-625">If this element is absent, the settings location template ignores the process’ architecture and applies to both 32 and 64-bit processes if the file name and other attributes apply.</span></span>

<span data-ttu-id="3ec6a-626">**注意** UE-V 不支持此版本中的 ARM 处理器。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-626">**Note** UE-V does not support ARM processors in this version.</span></span>

 

### <span data-ttu-id="3ec6a-627">ProductName</span><span class="sxs-lookup"><span data-stu-id="3ec6a-627">ProductName</span></span>

**<span data-ttu-id="3ec6a-628">强制： False</span><span class="sxs-lookup"><span data-stu-id="3ec6a-628">Mandatory: False</span></span>**

**<span data-ttu-id="3ec6a-629">类型： String</span><span class="sxs-lookup"><span data-stu-id="3ec6a-629">Type: String</span></span>**

<span data-ttu-id="3ec6a-630">ProductName 是一个可选元素，用于标识用于管理用途或报告的产品。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-630">ProductName is an optional element used to identify a product for administrative purposes or reporting.</span></span> <span data-ttu-id="3ec6a-631">ProductName 与 Filename 的不同之处在于它的值没有正则表达式限制。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-631">ProductName differs from Filename in that there are no regular expression restrictions on its value.</span></span> <span data-ttu-id="3ec6a-632">这允许更容易理解的可执行文件名称可能不明显的进程的说明。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-632">This allows for more easily understood descriptions of a process where the executable name may not be obvious.</span></span> <span data-ttu-id="3ec6a-633">例如：</span><span class="sxs-lookup"><span data-stu-id="3ec6a-633">For example:</span></span>

```xml
<Process>
  <Filename>MyApplication.exe</Filename>
  <ProductName>My Application 6.x by Contoso.com</ProductName>
  <ProductVersion>
    <Major Minimum="6" Maximum="6" />
  </ProductVersion>
</Process>
```

### <span data-ttu-id="3ec6a-634">FileDescription</span><span class="sxs-lookup"><span data-stu-id="3ec6a-634">FileDescription</span></span>

**<span data-ttu-id="3ec6a-635">强制： False</span><span class="sxs-lookup"><span data-stu-id="3ec6a-635">Mandatory: False</span></span>**

**<span data-ttu-id="3ec6a-636">类型： String</span><span class="sxs-lookup"><span data-stu-id="3ec6a-636">Type: String</span></span>**

<span data-ttu-id="3ec6a-637">FileDescription 是一个可选标记，可提供可执行文件的管理说明。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-637">FileDescription is an optional tag that allows for an administrative description of the executable file.</span></span> <span data-ttu-id="3ec6a-638">这是一个免费的文本字段，在需要标识可执行文件的功能的软件包中的多个可执行文件中非常有用。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-638">This is a free text field and can be useful in distinguishing multiple executables within a software package where there is a need to identify the function of the executable.</span></span>

<span data-ttu-id="3ec6a-639">例如，在一个合适的应用程序中，提供有关两个可执行文件（MyApplication.exe 和 MyApplicationHelper.exe）的功能的提醒可能很有用，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3ec6a-639">For example, in a suited application, it might be useful to provide reminders about the function of two executables (MyApplication.exe and MyApplicationHelper.exe), as shown here:</span></span>

```xml
<Processes>
  <Process>
    <Filename>MyApplication.exe</Filename>
    <FileDescription>My Application Main Engine</ FileDescription>
    <ProductVersion>
      <Major Minimum="6" Maximum="6" />
    </ProductVersion>
  </Process>
  <Process>
    <Filename>MyApplicationHelper.exe</Filename>
    <FileDescription>My Application Background Process Executable</FileDescription>
    <ProductVersion>
      <Major Minimum="6" Maximum="6" />
    </ProductVersion>
  </Process>
</Processes>
```

### <span data-ttu-id="3ec6a-640">ProductVersion</span><span class="sxs-lookup"><span data-stu-id="3ec6a-640">ProductVersion</span></span>

**<span data-ttu-id="3ec6a-641">强制： False</span><span class="sxs-lookup"><span data-stu-id="3ec6a-641">Mandatory: False</span></span>**

**<span data-ttu-id="3ec6a-642">类型： String</span><span class="sxs-lookup"><span data-stu-id="3ec6a-642">Type: String</span></span>**

<span data-ttu-id="3ec6a-643">ProductVersion 是指文件的主要和次要产品版本以及版本和修补程序级别。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-643">ProductVersion refers to the major and minor product versions of a file, as well as a build and patch level.</span></span> <span data-ttu-id="3ec6a-644">ProductVersion 是一个可选元素，但如果指定，它必须至少包含主要子元素。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-644">ProductVersion is an optional element, but if specified, it must contain at least the Major child element.</span></span> <span data-ttu-id="3ec6a-645">此值必须以最小为 = "X" 的最大值 = "Y" 表示区域，其中 X 和 Y 是整数。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-645">The value must express a range in the form Minimum="X" Maximum="Y" where X and Y are integers.</span></span> <span data-ttu-id="3ec6a-646">最小值和最大值可以相同。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-646">The Minimum and Maximum values can be identical.</span></span>

<span data-ttu-id="3ec6a-647">产品和文件版本元素可以保留未指定。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-647">The product and file version elements may be left unspecified.</span></span> <span data-ttu-id="3ec6a-648">这样做会使模板 "版本不限"，这意味着模板将应用于指定的可执行文件的所有版本。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-648">Doing so makes the template “version agnostic”, meaning that the template will apply to all versions of the specified executable.</span></span>

**<span data-ttu-id="3ec6a-649">示例 1：</span><span class="sxs-lookup"><span data-stu-id="3ec6a-649">Example 1:</span></span>**

<span data-ttu-id="3ec6a-650">UE-V 生成器中指定的产品版本：1.0 生成以下 XML：</span><span class="sxs-lookup"><span data-stu-id="3ec6a-650">Product version: 1.0 specified in the UE-V Generator produces the following XML:</span></span>

```xml
<ProductVersion>
  <Major Minimum="1" Maximum="1" />
  <Minor Minimum="0" Maximum="0" />
</ProductVersion>
```

**<span data-ttu-id="3ec6a-651">示例 2：</span><span class="sxs-lookup"><span data-stu-id="3ec6a-651">Example 2:</span></span>**

<span data-ttu-id="3ec6a-652">文件版本： UE-V 生成器中指定的5.0.2.1000 生成以下 XML：</span><span class="sxs-lookup"><span data-stu-id="3ec6a-652">File version: 5.0.2.1000 specified in the UE-V Generator produces the following XML:</span></span>

```xml
<FileVersion>
  <Major Minimum="5" Maximum="5" />
  <Minor Minimum="0" Maximum="0" />
  <Build Minimum="2" Maximum="2" />
  <Patch Minimum="1000" Maximum="1000" />
</FileVersion>
```

**<span data-ttu-id="3ec6a-653">不正确的示例 1-未完成的范围：</span><span class="sxs-lookup"><span data-stu-id="3ec6a-653">Incorrect Example 1 – incomplete range:</span></span>**

<span data-ttu-id="3ec6a-654">仅存在最小属性。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-654">Only the Minimum attribute is present.</span></span> <span data-ttu-id="3ec6a-655">范围中还必须包含 "最大"。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-655">Maximum must be included in a range as well.</span></span>

```xml
<ProductVersion>
  <Major Minimum="2" />
</ProductVersion>
```

**<span data-ttu-id="3ec6a-656">不正确的示例 2-指定的次要元素没有主要元素：</span><span class="sxs-lookup"><span data-stu-id="3ec6a-656">Incorrect Example 2 – Minor specified without Major element:</span></span>**

<span data-ttu-id="3ec6a-657">仅存在次要元素。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-657">Only the Minor element is present.</span></span> <span data-ttu-id="3ec6a-658">还必须包含主版本。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-658">Major must be included as well.</span></span>

```xml
<ProductVersion>
  <Minor Minimum="0" Maximum="0" />
</ProductVersion>
```

### <span data-ttu-id="3ec6a-659">FileVersion</span><span class="sxs-lookup"><span data-stu-id="3ec6a-659">FileVersion</span></span>

**<span data-ttu-id="3ec6a-660">强制： False</span><span class="sxs-lookup"><span data-stu-id="3ec6a-660">Mandatory: False</span></span>**

**<span data-ttu-id="3ec6a-661">类型： String</span><span class="sxs-lookup"><span data-stu-id="3ec6a-661">Type: String</span></span>**

<span data-ttu-id="3ec6a-662">FileVersion 将区分已发布应用程序的发布版本和组件可执行文件的内部生成详细信息。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-662">FileVersion differentiates between the release version of a published application and the internal build details of a component executable.</span></span> <span data-ttu-id="3ec6a-663">对于大多数商业应用程序，这些号码是相同的。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-663">For the majority of commercial applications, these numbers are identical.</span></span> <span data-ttu-id="3ec6a-664">它们的不同之处是，文件的产品版本指示文件的常规版本标识，而文件版本指示文件的特定版本（如修补程序或更新）。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-664">Where they vary, the product version of a file indicates a generic version identification of a file, while file version indicates a specific build of a file (as in the case of a hotfix or update).</span></span> <span data-ttu-id="3ec6a-665">这将在不中断检测逻辑的情况下唯一标识文件。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-665">This uniquely identifies files without breaking detection logic.</span></span>

<span data-ttu-id="3ec6a-666">若要确定特定可执行文件的产品版本和文件版本，请在 Windows 资源管理器中右键单击该文件，选择 "属性"，然后单击 "详细信息" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-666">To determine the product version and file version of a particular executable, right-click on the file in Windows Explorer, select Properties, then click on the Details tab.</span></span>

<span data-ttu-id="3ec6a-667">为应用程序包括 FileVersion 元素可实现更精细的微调检测逻辑，但对于大多数应用程序都不是必需的。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-667">Including a FileVersion element for an application allows for more granular fine-tuning detection logic, but is not necessary for most applications.</span></span> <span data-ttu-id="3ec6a-668">首先检查 ProductVersion 元素设置，然后选中 "FileVersion"。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-668">The ProductVersion element settings are checked first, and then FileVersion is checked.</span></span> <span data-ttu-id="3ec6a-669">将应用更严格的设置。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-669">The more restrictive setting will apply.</span></span>

<span data-ttu-id="3ec6a-670">FileVersion 的子元素和语法规则与 ProductVersion 的子元素和语法规则相同。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-670">The child elements and syntax rules for FileVersion are identical to those of ProductVersion.</span></span>

```xml
<Process>
  <Filename>MSACCESS.EXE</Filename>
  <Architecture>Win32</Architecture>
  <ProductVersion>
    <Major Minimum="14" Maximum="14" />
    <Minor Minimum="0" Maximum="0" />
  </ProductVersion>
  <FileVersion>
    <Major Minimum="14" Maximum="14" />
    <Minor Minimum="0" Maximum="0" />
  </FileVersion>
</Process>
```

### <a href="" id="application"></a><span data-ttu-id="3ec6a-671">应用程序元素</span><span class="sxs-lookup"><span data-stu-id="3ec6a-671">Application Element</span></span>

<span data-ttu-id="3ec6a-672">应用程序是应用于特定应用程序的设置的容器。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-672">Application is a container for settings that apply to a particular application.</span></span> <span data-ttu-id="3ec6a-673">它是以下字段/类型的集合。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-673">It is a collection of the following fields/types.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3ec6a-674">字段/类型</span><span class="sxs-lookup"><span data-stu-id="3ec6a-674">Field/Type</span></span></th>
<th align="left"><span data-ttu-id="3ec6a-675">描述</span><span class="sxs-lookup"><span data-stu-id="3ec6a-675">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3ec6a-676">名称</span><span class="sxs-lookup"><span data-stu-id="3ec6a-676">Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-677">为设置位置模板指定一个唯一名称。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-677">Specifies a unique name for the settings location template.</span></span> <span data-ttu-id="3ec6a-678">这用于在 WMI、PowerShell、事件查看器和调试日志中引用模板时的显示用途。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-678">This is used for display purposes when referencing the template in WMI, PowerShell, Event Viewer and debug logs.</span></span> <span data-ttu-id="3ec6a-679">有关详细信息，请参阅 <a href="#name" data-raw-source="[Name](#name)"> 名称 </a> 。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-679">For more information, see <a href="#name" data-raw-source="[Name](#name)">Name</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3ec6a-680">ID</span><span class="sxs-lookup"><span data-stu-id="3ec6a-680">ID</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-681">填充特定模板的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-681">Populates a unique identifier for a particular template.</span></span> <span data-ttu-id="3ec6a-682">此标记将成为 UE-V Agent 在运行时引用模板时使用的主要标识符。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-682">This tag becomes the primary identifier that the UE-V Agent uses to reference the template at runtime.</span></span> <span data-ttu-id="3ec6a-683">有关详细信息，请参阅 <a href="#id" data-raw-source="[ID](#id)"> ID </a> 。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-683">For more information, see <a href="#id" data-raw-source="[ID](#id)">ID</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3ec6a-684">描述</span><span class="sxs-lookup"><span data-stu-id="3ec6a-684">Description</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-685">模板的可选说明。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-685">An optional description of the template.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3ec6a-686">LocalizedNames</span><span class="sxs-lookup"><span data-stu-id="3ec6a-686">LocalizedNames</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-687">UI 中显示的可选名称，由语言区域设置本地化。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-687">An optional name displayed in the UI, localized by a language locale.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3ec6a-688">LocalizedDescriptions</span><span class="sxs-lookup"><span data-stu-id="3ec6a-688">LocalizedDescriptions</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-689">由语言区域设置本地化的可选模板说明。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-689">An optional template description localized by a language locale.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3ec6a-690">版本</span><span class="sxs-lookup"><span data-stu-id="3ec6a-690">Version</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-691">标识用于管理更改管理跟踪的设置位置模板的版本。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-691">Identifies the version of the settings location template for administrative tracking of changes.</span></span> <span data-ttu-id="3ec6a-692">有关详细信息，请参阅 <a href="#version" data-raw-source="[Version](#version)"> 版本 </a> 。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-692">For more information, see <a href="#version" data-raw-source="[Version](#version)">Version</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3ec6a-693">DeferToMSAccount</span><span class="sxs-lookup"><span data-stu-id="3ec6a-693">DeferToMSAccount</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-694">控制是否与 Microsoft 帐户一起启用此模板。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-694">Controls whether this template is enabled in conjunction with a Microsoft account or not.</span></span> <span data-ttu-id="3ec6a-695">如果对计算机上的用户启用了 MSA 同步，则该模板将自动禁用。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-695">If MSA syncing is enabled for a user on a machine, then this template will automatically be disabled.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3ec6a-696">DeferToOffice365</span><span class="sxs-lookup"><span data-stu-id="3ec6a-696">DeferToOffice365</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-697">与 MSA 类似，它控制此模板是否与 Office365 一起启用。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-697">Similar to MSA, this controls whether this template is enabled in conjunction with Office365.</span></span> <span data-ttu-id="3ec6a-698">如果使用 Office 365 同步设置，此模板将自动禁用。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-698">If Office 365 is being used to sync settings, this template will automatically be disabled.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3ec6a-699">进程</span><span class="sxs-lookup"><span data-stu-id="3ec6a-699">Processes</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-700">一个容器，用于一个或多个流程元素的集合。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-700">A container for a collection of one or more Process elements.</span></span> <span data-ttu-id="3ec6a-701">有关详细信息，请参阅 <a href="#processes" data-raw-source="[Processes](#processes)"> 流程 </a> 。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-701">For more information, see <a href="#processes" data-raw-source="[Processes](#processes)">Processes</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3ec6a-702">设置</span><span class="sxs-lookup"><span data-stu-id="3ec6a-702">Settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-703">适用于特定模板的所有设置的容器。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-703">A container for all the settings that apply to a particular template.</span></span> <span data-ttu-id="3ec6a-704">它包含注册表、File、SystemParameter 和 CustomAction 设置的实例。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-704">It contains instances of the Registry, File, SystemParameter, and CustomAction settings.</span></span> <span data-ttu-id="3ec6a-705">有关详细信息，请 <strong> 参阅 </strong> 数据类型中的设置 <a href="#data" data-raw-source="[Data types](#data)"> </a> 。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-705">For more information, see <strong>Settings</strong> in <a href="#data" data-raw-source="[Data types](#data)">Data types</a>.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="common"></a><span data-ttu-id="3ec6a-706">常见元素</span><span class="sxs-lookup"><span data-stu-id="3ec6a-706">Common Element</span></span>

<span data-ttu-id="3ec6a-707">常用于应用程序元素，但它始终与两个或更多个应用程序元素关联。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-707">Common is similar to an Application element, but it is always associated with two or more Application elements.</span></span> <span data-ttu-id="3ec6a-708">"常见" 部分表示在这些应用程序实例之间共享的一组设置。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-708">The Common section represents the set of settings that are shared between those Application instances.</span></span> <span data-ttu-id="3ec6a-709">它是以下字段/类型的集合。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-709">It is a collection of the following fields/types.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3ec6a-710">字段/类型</span><span class="sxs-lookup"><span data-stu-id="3ec6a-710">Field/Type</span></span></th>
<th align="left"><span data-ttu-id="3ec6a-711">描述</span><span class="sxs-lookup"><span data-stu-id="3ec6a-711">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3ec6a-712">名称</span><span class="sxs-lookup"><span data-stu-id="3ec6a-712">Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-713">为设置位置模板指定一个唯一名称。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-713">Specifies a unique name for the settings location template.</span></span> <span data-ttu-id="3ec6a-714">这用于在 WMI、PowerShell、事件查看器和调试日志中引用模板时的显示用途。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-714">This is used for display purposes when referencing the template in WMI, PowerShell, Event Viewer and debug logs.</span></span> <span data-ttu-id="3ec6a-715">有关详细信息，请参阅 <a href="#name" data-raw-source="[Name](#name)"> 名称 </a> 。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-715">For more information, see <a href="#name" data-raw-source="[Name](#name)">Name</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3ec6a-716">ID</span><span class="sxs-lookup"><span data-stu-id="3ec6a-716">ID</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-717">填充特定模板的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-717">Populates a unique identifier for a particular template.</span></span> <span data-ttu-id="3ec6a-718">此标记将成为 UE-V Agent 在运行时引用模板时使用的主要标识符。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-718">This tag becomes the primary identifier that the UE-V Agent uses to reference the template at runtime.</span></span> <span data-ttu-id="3ec6a-719">有关详细信息，请参阅 <a href="#id" data-raw-source="[ID](#id)"> ID </a> 。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-719">For more information, see <a href="#id" data-raw-source="[ID](#id)">ID</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3ec6a-720">描述</span><span class="sxs-lookup"><span data-stu-id="3ec6a-720">Description</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-721">模板的可选说明。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-721">An optional description of the template.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3ec6a-722">LocalizedNames</span><span class="sxs-lookup"><span data-stu-id="3ec6a-722">LocalizedNames</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-723">UI 中显示的可选名称，由语言区域设置本地化。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-723">An optional name displayed in the UI, localized by a language locale.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3ec6a-724">LocalizedDescriptions</span><span class="sxs-lookup"><span data-stu-id="3ec6a-724">LocalizedDescriptions</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-725">由语言区域设置本地化的可选模板说明。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-725">An optional template description localized by a language locale.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3ec6a-726">版本</span><span class="sxs-lookup"><span data-stu-id="3ec6a-726">Version</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-727">标识用于管理更改管理跟踪的设置位置模板的版本。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-727">Identifies the version of the settings location template for administrative tracking of changes.</span></span> <span data-ttu-id="3ec6a-728">有关详细信息，请参阅 <a href="#version" data-raw-source="[Version](#version)"> 版本 </a> 。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-728">For more information, see <a href="#version" data-raw-source="[Version](#version)">Version</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3ec6a-729">DeferToMSAccount</span><span class="sxs-lookup"><span data-stu-id="3ec6a-729">DeferToMSAccount</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-730">控制是否与 Microsoft 帐户一起启用此模板。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-730">Controls whether this template is enabled in conjunction with a Microsoft account or not.</span></span> <span data-ttu-id="3ec6a-731">如果对计算机上的用户启用了 MSA 同步，则该模板将自动禁用。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-731">If MSA syncing is enabled for a user on a machine, then this template will automatically be disabled.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3ec6a-732">DeferToOffice365</span><span class="sxs-lookup"><span data-stu-id="3ec6a-732">DeferToOffice365</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-733">与 MSA 类似，它控制此模板是否与 Office365 一起启用。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-733">Similar to MSA, this controls whether this template is enabled in conjunction with Office365.</span></span> <span data-ttu-id="3ec6a-734">如果使用 Office 365 同步设置，此模板将自动禁用。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-734">If Office 365 is being used to sync settings, this template will automatically be disabled.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3ec6a-735">设置</span><span class="sxs-lookup"><span data-stu-id="3ec6a-735">Settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-736">适用于特定模板的所有设置的容器。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-736">A container for all the settings that apply to a particular template.</span></span> <span data-ttu-id="3ec6a-737">它包含注册表、File、SystemParameter 和 CustomAction 设置的实例。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-737">It contains instances of the Registry, File, SystemParameter, and CustomAction settings.</span></span> <span data-ttu-id="3ec6a-738">有关详细信息，请 <strong> 参阅 </strong> 数据类型中的设置 <a href="#data" data-raw-source="[Data types](#data)"> </a> 。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-738">For more information, see <strong>Settings</strong> in <a href="#data" data-raw-source="[Data types](#data)">Data types</a>.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="settingslocationtemplate"></a><span data-ttu-id="3ec6a-739">SettingsLocationTemplate 元素</span><span class="sxs-lookup"><span data-stu-id="3ec6a-739">SettingsLocationTemplate Element</span></span>

<span data-ttu-id="3ec6a-740">此元素定义单个应用程序或一组应用程序的设置。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-740">This element defines the settings for a single application or a suite of applications.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3ec6a-741">字段/类型</span><span class="sxs-lookup"><span data-stu-id="3ec6a-741">Field/Type</span></span></th>
<th align="left"><span data-ttu-id="3ec6a-742">描述</span><span class="sxs-lookup"><span data-stu-id="3ec6a-742">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3ec6a-743">名称</span><span class="sxs-lookup"><span data-stu-id="3ec6a-743">Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-744">为设置位置模板指定一个唯一名称。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-744">Specifies a unique name for the settings location template.</span></span> <span data-ttu-id="3ec6a-745">这用于在 WMI、PowerShell、事件查看器和调试日志中引用模板时的显示用途。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-745">This is used for display purposes when referencing the template in WMI, PowerShell, Event Viewer and debug logs.</span></span> <span data-ttu-id="3ec6a-746">有关详细信息，请参阅 <a href="#name" data-raw-source="[Name](#name)"> 名称 </a> 。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-746">For more information, see <a href="#name" data-raw-source="[Name](#name)">Name</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3ec6a-747">ID</span><span class="sxs-lookup"><span data-stu-id="3ec6a-747">ID</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-748">填充特定模板的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-748">Populates a unique identifier for a particular template.</span></span> <span data-ttu-id="3ec6a-749">此标记将成为 UE-V Agent 在运行时引用模板时使用的主要标识符。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-749">This tag becomes the primary identifier that the UE-V Agent uses to reference the template at runtime.</span></span> <span data-ttu-id="3ec6a-750">有关详细信息，请参阅 <a href="#id" data-raw-source="[ID](#id)"> ID </a> 。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-750">For more information, see <a href="#id" data-raw-source="[ID](#id)">ID</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3ec6a-751">描述</span><span class="sxs-lookup"><span data-stu-id="3ec6a-751">Description</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-752">模板的可选说明。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-752">An optional description of the template.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3ec6a-753">LocalizedNames</span><span class="sxs-lookup"><span data-stu-id="3ec6a-753">LocalizedNames</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-754">UI 中显示的可选名称，由语言区域设置本地化。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-754">An optional name displayed in the UI, localized by a language locale.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3ec6a-755">LocalizedDescriptions</span><span class="sxs-lookup"><span data-stu-id="3ec6a-755">LocalizedDescriptions</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ec6a-756">由语言区域设置本地化的可选模板说明。</span><span class="sxs-lookup"><span data-stu-id="3ec6a-756">An optional template description localized by a language locale.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="appendix"></a><span data-ttu-id="3ec6a-757">附录： SettingsLocationTemplate</span><span class="sxs-lookup"><span data-stu-id="3ec6a-757">Appendix: SettingsLocationTemplate.xsd</span></span>

<span data-ttu-id="3ec6a-758">下面是显示其元素、子元素、属性和参数的 SettingsLocationTemplate 文件：</span><span class="sxs-lookup"><span data-stu-id="3ec6a-758">Here is the SettingsLocationTemplate.xsd file showing its elements, child elements, attributes, and parameters:</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema id="UevSettingsLocationTemplate"
  targetNamespace="https://schemas.microsoft.com/UserExperienceVirtualization/2013/SettingsLocationTemplate"
  elementFormDefault="qualified"
  xmlns="https://schemas.microsoft.com/UserExperienceVirtualization/2013/SettingsLocationTemplate"
  xmlns:mstns="https://schemas.microsoft.com/UserExperienceVirtualization/2013/SettingsLocationTemplate"
  xmlns:xs="http://www.w3.org/2001/XMLSchema">

  <xs:simpleType name="Guid">
    <xs:restriction base="xs:string">
      <xs:pattern value="\{[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{12}\}" />
    </xs:restriction>
  </xs:simpleType>

  <xs:simpleType name="FilenameString">
    <xs:restriction base="xs:string">
      <xs:pattern value="[^\\\?\*\|&lt;&gt;/:]+" />
    </xs:restriction>
  </xs:simpleType>

  <xs:simpleType name="IDString">
    <xs:restriction base="xs:string">
      <xs:pattern value="[^\\\?\*\|&lt;&gt;/:.]+" />
    </xs:restriction>
  </xs:simpleType>

  <xs:simpleType name="TemplateVersion">
    <xs:restriction base="xs:integer">
      <xs:minInclusive value="0" />
      <xs:maxInclusive value="2147483647" />
    </xs:restriction>
  </xs:simpleType>

  <xs:complexType name="Empty">
    <xs:sequence/>
  </xs:complexType>

  <xs:complexType name="LocalizedString">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="Locale" type="xs:string" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>

  <xs:complexType name="LocalizedName">
    <xs:sequence>
      <xs:element name="Name" type="LocalizedString" minOccurs="1" maxOccurs="unbounded" />
    </xs:sequence>
  </xs:complexType>

  <xs:complexType name="LocalizedDescription">
    <xs:sequence>
      <xs:element name="Description" type="LocalizedString" minOccurs="1" maxOccurs="unbounded" />
    </xs:sequence>
  </xs:complexType>

  <xs:complexType name="Author">
    <xs:all>
      <xs:element name="Name" type="xs:string" minOccurs="1" />
      <xs:element name="Email" type="xs:string" minOccurs="0" />
    </xs:all>
  </xs:complexType>

  <xs:complexType name="Range">
    <xs:attribute name="Minimum" type="xs:integer" use="required"/>
    <xs:attribute name="Maximum" type="xs:integer" use="required"/>
  </xs:complexType>

  <xs:complexType name="ProcessVersion">
    <xs:sequence>
      <xs:element name="Major" type="Range" minOccurs="1" />
      <xs:element name="Minor" type="Range" minOccurs="0" />
      <xs:element name="Build" type="Range" minOccurs="0" />
      <xs:element name="Patch" type="Range" minOccurs="0" />
    </xs:sequence>
  </xs:complexType>

  <xs:simpleType name="Architecture">
    <xs:restriction base="xs:string">
      <xs:enumeration value="Win32"/>
      <xs:enumeration value="Win64"/>
    </xs:restriction>
  </xs:simpleType>

  <xs:complexType name="Process">
    <xs:sequence>
      <xs:element name="Filename" type="FilenameString" minOccurs="1" />
      <xs:element name="Architecture" type="Architecture" minOccurs="0" />
      <xs:element name="ProductName" type="xs:string" minOccurs="0" />
      <xs:element name="FileDescription" type="xs:string" minOccurs="0" />
      <xs:element name="ProductVersion" type="ProcessVersion" minOccurs="0" maxOccurs="unbounded"/>
      <xs:element name="FileVersion" type="ProcessVersion" minOccurs="0" maxOccurs="unbounded"/>
    </xs:sequence>
  </xs:complexType>

  <xs:complexType name="Processes">
    <xs:sequence>
      <xs:choice minOccurs="1">
        <xs:element name="Process" type="Process" />
        <xs:element name="ShellProcess" type="Empty" />
      </xs:choice>
      <xs:element name="Process" type="Process" minOccurs="0" maxOccurs="unbounded" />
    </xs:sequence>
  </xs:complexType>

  <xs:complexType name="Path">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="Recursive" type="xs:boolean" default="false"/>
        <xs:attribute name="DeleteIfNotFound" type="xs:boolean" default="false"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>

  <xs:complexType name="RegistrySetting">
    <xs:sequence>
      <xs:element name="Path" type="Path" />
      <xs:element name="Name" type="xs:string" minOccurs="0" maxOccurs="unbounded" />
      <xs:element name="Exclude" minOccurs="0" maxOccurs="unbounded">
        <xs:complexType>
          <xs:sequence>
            <xs:element name="Path" type="Path" minOccurs="0" />
            <xs:element name="Name" type="xs:string" minOccurs="0" maxOccurs="unbounded" />
          </xs:sequence>
        </xs:complexType>
      </xs:element>
    </xs:sequence>
  </xs:complexType>

  <xs:complexType name="FileSetting">
    <xs:sequence>

      <xs:element name="Root">
        <xs:complexType>
          <xs:choice>
            <xs:element name="KnownFolder" type="Guid" />
            <xs:element name="RegistryEntry" type="xs:string" />
            <xs:element name="EnvironmentVariable" type="xs:string" />
          </xs:choice>
        </xs:complexType>
      </xs:element>

      <xs:element name="Path" minOccurs="0" type="Path" />
      <xs:element name="FileMask" type="xs:string" minOccurs="0" maxOccurs="unbounded"/>

      <xs:element name="Exclude" minOccurs="0" maxOccurs="unbounded">
        <xs:complexType>
          <xs:sequence>
            <xs:element name="Path" type="Path" minOccurs="0" />
            <xs:element name="FileMask" type="xs:string" minOccurs="0" maxOccurs="unbounded" />
          </xs:sequence>
        </xs:complexType>
      </xs:element>

    </xs:sequence>
  </xs:complexType>

  <xs:simpleType name="SystemParameterSetting">
    <xs:restriction base="xs:string">

      <!-- Accessibility parameters -->
      <xs:enumeration value="AccessTimeout"/>
      <xs:enumeration value="AudioDescription"/>
      <xs:enumeration value="ClientAreaAnimation"/>
      <xs:enumeration value="DisableOverlappedContent"/>
      <xs:enumeration value="FilterKeys"/>
      <xs:enumeration value="FocusBorderHeight"/>
      <xs:enumeration value="FocusBorderWidth"/>
      <xs:enumeration value="HighContrast"/>
      <xs:enumeration value="MessageDuration"/>
      <xs:enumeration value="MouseClickLock"/>
      <xs:enumeration value="MouseClickLockTime"/>
      <xs:enumeration value="MouseKeys"/>
      <xs:enumeration value="MouseSonar"/>
      <xs:enumeration value="MouseVanish"/>
      <xs:enumeration value="ScreenReader"/>
      <xs:enumeration value="ShowSounds"/>
      <xs:enumeration value="SoundSentry"/>
      <xs:enumeration value="StickyKeys"/>
      <xs:enumeration value="ToggleKeys"/>

      <!-- Input parameters -->
      <xs:enumeration value="Beep"/>
      <xs:enumeration value="BlockSendInputResets"/>
      <xs:enumeration value="DefaultInputLang"/>
      <xs:enumeration value="DoubleClickTime"/>
      <xs:enumeration value="DoubleClkHeight"/>
      <xs:enumeration value="DoubleClkWidth"/>
      <xs:enumeration value="KeyboardCues"/>
      <xs:enumeration value="KeyboardDelay"/>
      <xs:enumeration value="KeyboardPref"/>
      <xs:enumeration value="KeyboardSpeed"/>
      <xs:enumeration value="Mouse"/>
      <xs:enumeration value="MouseButtonSwap"/>
      <xs:enumeration value="MouseHoverHeight"/>
      <xs:enumeration value="MouseHoverTime"/>
      <xs:enumeration value="MouseHoverWidth"/>
      <xs:enumeration value="MouseSpeed"/>
      <xs:enumeration value="MouseTrails"/>
      <xs:enumeration value="SnapToDefButton"/>
      <xs:enumeration value="WheelScrollChars"/>
      <xs:enumeration value="WheelScrollLines"/>

      <!-- Desktop parameters (limited subset) -->
      <xs:enumeration value="DeskWallpaper"/>
      <xs:enumeration value="DesktopColor"/>

    </xs:restriction>
  </xs:simpleType>

  <xs:complexType name="Settings">
    <xs:sequence>
      <xs:element name="Asynchronous" type="xs:boolean" minOccurs="0" />
      <xs:element name="PreventOverlappingSynchronization" type="xs:boolean" minOccurs="0" />
      <xs:choice minOccurs="0" maxOccurs="unbounded">
        <xs:element name="Registry" type="RegistrySetting" />
        <xs:element name="File" type="FileSetting" />
        <xs:element name="SystemParameter" type="SystemParameterSetting" />
      </xs:choice>
    </xs:sequence>
  </xs:complexType>

  <xs:complexType name="Common">
    <xs:sequence>
      <xs:element name="Name" type="xs:string" />
      <xs:element name="ID" type="IDString" />
      <xs:element name="Description" type="xs:string" minOccurs="0" />
      <xs:element name="LocalizedNames" type="LocalizedName" minOccurs="0" />
      <xs:element name="LocalizedDescriptions" type="LocalizedDescription" minOccurs="0" />
      <xs:element name="Version" type="xs:integer" />
      <xs:element name="DeferToMSAccount" type="Empty"  minOccurs="0" />
      <xs:element name="Settings" type="Settings" />
    </xs:sequence>
  </xs:complexType>

  <xs:complexType name="Application">
    <xs:sequence>
      <xs:element name="Name" type="xs:string" />
      <xs:element name="ID" type="IDString" />
      <xs:element name="Description" type="xs:string" minOccurs="0" />
      <xs:element name="LocalizedNames" type="LocalizedName" minOccurs="0" />
      <xs:element name="LocalizedDescriptions" type="LocalizedDescription" minOccurs="0" />
      <xs:element name="Version" type="xs:integer" />
      <xs:element name="DeferToMSAccount" type="Empty"  minOccurs="0" />
      <xs:element name="Processes" type="Processes" />
      <xs:element name="Settings" type="Settings" />
    </xs:sequence>
  </xs:complexType>


  <xs:element name="SettingsLocationTemplate">
    <xs:complexType>
      <xs:sequence>

        <xs:element name="Name" type="xs:string" />
        <xs:element name="ID" type="IDString" />
        <xs:element name="Description" type="xs:string" minOccurs="0" />
        <xs:element name="LocalizedNames" type="LocalizedName" minOccurs="0" />
        <xs:element name="LocalizedDescriptions" type="LocalizedDescription" minOccurs="0" />

        <xs:choice>

          <!-- Single application -->
          <xs:sequence>
            <xs:element name="Version" type="TemplateVersion" />
            <xs:element name="Author" type="Author" minOccurs="0" />
            <xs:element name="DeferToMSAccount" type="Empty"  minOccurs="0" />
            <xs:element name="Processes" type="Processes" />
            <xs:element name="Settings" type="Settings" />
          </xs:sequence>

          <!-- Suite of applications -->
          <xs:sequence>
            <xs:element name="ManageSuiteOnly" type="xs:boolean" minOccurs="0" />
            <xs:element name="Author" type="Author" minOccurs="0" />
            <xs:element name="Common" type="Common" />
            <xs:element name="Application" type="Application" minOccurs="2" maxOccurs="unbounded" />
          </xs:sequence>

        </xs:choice>

      </xs:sequence>
    </xs:complexType>
  </xs:element>
  <!-- SettingsLocationTemplate -->

</xs:schema>
```






## <span data-ttu-id="3ec6a-759">相关主题</span><span class="sxs-lookup"><span data-stu-id="3ec6a-759">Related topics</span></span>


[<span data-ttu-id="3ec6a-760">使用自定义 UE-V x 模板和 UE-V 2 版生成器</span><span class="sxs-lookup"><span data-stu-id="3ec6a-760">Working with Custom UE-V 2.x Templates and the UE-V 2.x Generator</span></span>](working-with-custom-ue-v-2x-templates-and-the-ue-v-2x-generator-new-uevv2.md)

[<span data-ttu-id="3ec6a-761">UE-V 2.x 的技术参考</span><span class="sxs-lookup"><span data-stu-id="3ec6a-761">Technical Reference for UE-V 2.x</span></span>](technical-reference-for-ue-v-2x-both-uevv2.md)

 

 





