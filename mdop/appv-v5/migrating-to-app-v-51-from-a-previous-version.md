---
title: 从以前版本迁移到 App-V 5.1
description: 从以前版本迁移到 App-V 5.1
author: dansimp
ms.assetid: e7ee0edc-7544-4c0a-aaca-d922a33bc1bb
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7fb6ddbfed4f6fd1ae9613d2ee86361a51918a65
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798324"
---
# <span data-ttu-id="8b6cd-103">从以前版本迁移到 App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="8b6cd-103">Migrating to App-V 5.1 from a Previous Version</span></span>


<span data-ttu-id="8b6cd-104">通过 Microsoft Application Virtualization （App-v）5.1，你可以将现有的 app-v 4.6 或 App-v 5.0 基础结构迁移到更灵活、更集成且更易于管理的 app-v 5.1 基础结构。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-104">With Microsoft Application Virtualization (App-V) 5.1, you can migrate your existing App-V 4.6 or App-V 5.0 infrastructure to the more flexible, integrated, and easier to manage App-V 5.1 infrastructure.</span></span>
<span data-ttu-id="8b6cd-105">但是，不能直接从 App-v 4-v 升级到 app-v 5.1，必须首先迁移到 app-v 5.0。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-105">However, you cannot migrate directly from App-V 4.x to App-V 5.1, you must migrate to App-V 5.0 first.</span></span> <span data-ttu-id="8b6cd-106">有关从 app-v 4. x 迁移到 app-v 5.0 的详细信息，请参阅[从早期版本迁移](migrating-from-a-previous-version-app-v-50.md)</span><span class="sxs-lookup"><span data-stu-id="8b6cd-106">For more information on migrating from App-V 4.x to App-V 5.0, see [Migrating from a Previous Version](migrating-from-a-previous-version-app-v-50.md)</span></span>  

<span data-ttu-id="8b6cd-107">**注意** App-v 5.1 程序包与 App-v 5.0 程序包完全相同。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-107">**Note** App-V 5.1 packages are exactly the same as App-V 5.0 packages.</span></span> <span data-ttu-id="8b6cd-108">版本之间的程序包格式没有任何变化，因此无需将 app-v 5.0 程序包转换为 App-v 5.1 程序包。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-108">There has been no change in the package format between the versions and therefore, there is no need to convert App-V 5.0 packages to App-V 5.1 packages.</span></span>

<span data-ttu-id="8b6cd-109">有关 App-v 4.6 和 App-v 5.1 之间的区别的详细信息，请参阅[关于 app-v 5.0](about-app-v-50.md)的**app-v 4.6 和 app-v 5.0 部分之间的差异**。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-109">For more information about the differences between App-V 4.6 and App-V 5.1, see the **Differences between App-V 4.6 and App-V 5.0 section** of [About App-V 5.0](about-app-v-50.md).</span></span>

 

## <a href="" id="bkmk-pkgconvimprove"></a><span data-ttu-id="8b6cd-110">对 app-v 5.1 程序包转换器的改进</span><span class="sxs-lookup"><span data-stu-id="8b6cd-110">Improvements to the App-V 5.1 Package Converter</span></span>


<span data-ttu-id="8b6cd-111">现在，你可以使用程序包转换器转换包含脚本的 app-v 4.6 程序包，并且来自源 osd 文件的注册表信息和脚本现已包含在程序包转换器输出中。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-111">You can now use the package converter to convert App-V 4.6 packages that contain scripts, and registry information and scripts from source .osd files are now included in package converter output.</span></span>

<span data-ttu-id="8b6cd-112">你还可以将该 `–OSDsToIncludeInPackage` 参数与 cmdlet 配合使用 `ConvertFrom-AppvLegacyPackage` ，以指定哪些 osd 文件的信息被转换并放置在新程序包中。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-112">You can also use the `–OSDsToIncludeInPackage` parameter with the `ConvertFrom-AppvLegacyPackage` cmdlet to specify which .osd files’ information is converted and placed within the new package.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8b6cd-113">App-v 5.1 中的新增项</span><span class="sxs-lookup"><span data-stu-id="8b6cd-113">New in App-V 5.1</span></span></th>
<th align="left"><span data-ttu-id="8b6cd-114">在 App-v 5.1 之前</span><span class="sxs-lookup"><span data-stu-id="8b6cd-114">Prior to App-V 5.1</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b6cd-115">创建新的 .xml 文件，对应于与程序包关联的 .osd 文件;这些文件包括以下信息：</span><span class="sxs-lookup"><span data-stu-id="8b6cd-115">New .xml files are created corresponding to the .osd files associated with a package; these files include the following information:</span></span></p>
<ul>
<li><p><span data-ttu-id="8b6cd-116">环境变量</span><span class="sxs-lookup"><span data-stu-id="8b6cd-116">environment variables</span></span></p></li>
<li><p><span data-ttu-id="8b6cd-117">指向</span><span class="sxs-lookup"><span data-stu-id="8b6cd-117">shortcuts</span></span></p></li>
<li><p><span data-ttu-id="8b6cd-118">文件类型关联</span><span class="sxs-lookup"><span data-stu-id="8b6cd-118">file type associations</span></span></p></li>
<li><p><span data-ttu-id="8b6cd-119">注册信息</span><span class="sxs-lookup"><span data-stu-id="8b6cd-119">registry information</span></span></p></li>
<li><p><span data-ttu-id="8b6cd-120">标</span><span class="sxs-lookup"><span data-stu-id="8b6cd-120">scripts</span></span></p></li>
</ul>
<p><span data-ttu-id="8b6cd-121">现在，你可以选择使用该参数将源目录中的 .osd 文件子集中的信息添加到程序包 <code>-OSDsToIncludeInPackage</code> 。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-121">You can now choose to add information from a subset of the .osd files in the source directory to the package using the <code>-OSDsToIncludeInPackage</code> parameter.</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b6cd-122">与程序包相关联的 .osd 文件中包含的注册表信息和脚本未包含在程序包转换器输出中。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-122">Registry information and scripts included in .osd files associated with a package were not included in package converter output.</span></span></p>
<p><span data-ttu-id="8b6cd-123">程序包转换器将通过源目录中所有 .osd 文件中的信息填充新包。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-123">The package converter would populate the new package with information from all of the .osd files in the source directory.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="8b6cd-124">转换语句示例</span><span class="sxs-lookup"><span data-stu-id="8b6cd-124">Example conversion statement</span></span>

<span data-ttu-id="8b6cd-125">若要了解新进程，请查看下面的示例 `ConvertFrom-AppvLegacyPackage` 程序包转换器语句。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-125">To understand the new process, review the following example `ConvertFrom-AppvLegacyPackage` package converter statement.</span></span>

**<span data-ttu-id="8b6cd-126">如果源目录（\\\\OldPkgStore\\ContosoApp）包含以下内容：</span><span class="sxs-lookup"><span data-stu-id="8b6cd-126">If the source directory (\\\\OldPkgStore\\ContosoApp) includes the following:</span></span>**

-   <span data-ttu-id="8b6cd-127">ContosoApp</span><span class="sxs-lookup"><span data-stu-id="8b6cd-127">ContosoApp.sft</span></span>

-   <span data-ttu-id="8b6cd-128">ContosoApp.msi</span><span class="sxs-lookup"><span data-stu-id="8b6cd-128">ContosoApp.msi</span></span>

-   <span data-ttu-id="8b6cd-129">ContosoApp.sprj</span><span class="sxs-lookup"><span data-stu-id="8b6cd-129">ContosoApp.sprj</span></span>

-   <span data-ttu-id="8b6cd-130">ContosoApp\_manifest.xml</span><span class="sxs-lookup"><span data-stu-id="8b6cd-130">ContosoApp\_manifest.xml</span></span>

-   <span data-ttu-id="8b6cd-131">X.x.x。x</span><span class="sxs-lookup"><span data-stu-id="8b6cd-131">X.osd</span></span>

-   <span data-ttu-id="8b6cd-132">.Osd</span><span class="sxs-lookup"><span data-stu-id="8b6cd-132">Y.osd</span></span>

-   <span data-ttu-id="8b6cd-133">Z-a</span><span class="sxs-lookup"><span data-stu-id="8b6cd-133">Z.osd</span></span>

**<span data-ttu-id="8b6cd-134">然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="8b6cd-134">And you run this command:</span></span>**

``` syntax
ConvertFrom-AppvLegacyPackage –SourcePath \\OldPkgStore\ContosoApp\ 
-DestinationPath \\NewPkgStore\ContosoApp\
-OSDsToIncludeInPackage X.osd,Y.osd
```

**<span data-ttu-id="8b6cd-135">目标目录（\\\\NewPkgStore\\ContosoApp）中会创建以下内容：</span><span class="sxs-lookup"><span data-stu-id="8b6cd-135">The following is created in the destination directory (\\\\NewPkgStore\\ContosoApp):</span></span>**

-   <span data-ttu-id="8b6cd-136">ContosoApp</span><span class="sxs-lookup"><span data-stu-id="8b6cd-136">ContosoApp.appv</span></span>

-   <span data-ttu-id="8b6cd-137">ContosoApp.msi</span><span class="sxs-lookup"><span data-stu-id="8b6cd-137">ContosoApp.msi</span></span>

-   <span data-ttu-id="8b6cd-138">ContosoApp\_DeploymentConfig.xml</span><span class="sxs-lookup"><span data-stu-id="8b6cd-138">ContosoApp\_DeploymentConfig.xml</span></span>

-   <span data-ttu-id="8b6cd-139">ContosoApp\_UserConfig.xml</span><span class="sxs-lookup"><span data-stu-id="8b6cd-139">ContosoApp\_UserConfig.xml</span></span>

-   <span data-ttu-id="8b6cd-140">X\_Config.xml</span><span class="sxs-lookup"><span data-stu-id="8b6cd-140">X\_Config.xml</span></span>

-   <span data-ttu-id="8b6cd-141">Y\_Config.xml</span><span class="sxs-lookup"><span data-stu-id="8b6cd-141">Y\_Config.xml</span></span>

-   <span data-ttu-id="8b6cd-142">Z\_Config.xml</span><span class="sxs-lookup"><span data-stu-id="8b6cd-142">Z\_Config.xml</span></span>

**<span data-ttu-id="8b6cd-143">在上面的示例中：</span><span class="sxs-lookup"><span data-stu-id="8b6cd-143">In the above example:</span></span>**

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8b6cd-144">这些源目录文件 .。。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-144">These Source directory files…</span></span></th>
<th align="left"><span data-ttu-id="8b6cd-145">...转换为这些目标目录文件 .。。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-145">…are converted to these Destination directory files…</span></span></th>
<th align="left"><span data-ttu-id="8b6cd-146">...并将包含这些项目</span><span class="sxs-lookup"><span data-stu-id="8b6cd-146">…and will contain these items</span></span></th>
<th align="left"><span data-ttu-id="8b6cd-147">描述</span><span class="sxs-lookup"><span data-stu-id="8b6cd-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><ul>
<li><p><span data-ttu-id="8b6cd-148">X.x.x。x</span><span class="sxs-lookup"><span data-stu-id="8b6cd-148">X.osd</span></span></p></li>
<li><p><span data-ttu-id="8b6cd-149">.Osd</span><span class="sxs-lookup"><span data-stu-id="8b6cd-149">Y.osd</span></span></p></li>
<li><p><span data-ttu-id="8b6cd-150">Z-a</span><span class="sxs-lookup"><span data-stu-id="8b6cd-150">Z.osd</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="8b6cd-151">X_Config.xml</span><span class="sxs-lookup"><span data-stu-id="8b6cd-151">X_Config.xml</span></span></p></li>
<li><p><span data-ttu-id="8b6cd-152">Y_Config.xml</span><span class="sxs-lookup"><span data-stu-id="8b6cd-152">Y_Config.xml</span></span></p></li>
<li><p><span data-ttu-id="8b6cd-153">Z_Config.xml</span><span class="sxs-lookup"><span data-stu-id="8b6cd-153">Z_Config.xml</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="8b6cd-154">环境变量</span><span class="sxs-lookup"><span data-stu-id="8b6cd-154">Environment variables</span></span></p></li>
<li><p><span data-ttu-id="8b6cd-155">指向</span><span class="sxs-lookup"><span data-stu-id="8b6cd-155">Shortcuts</span></span></p></li>
<li><p><span data-ttu-id="8b6cd-156">文件类型关联</span><span class="sxs-lookup"><span data-stu-id="8b6cd-156">File type associations</span></span></p></li>
<li><p><span data-ttu-id="8b6cd-157">注册信息</span><span class="sxs-lookup"><span data-stu-id="8b6cd-157">Registry information</span></span></p></li>
<li><p><span data-ttu-id="8b6cd-158">脚本</span><span class="sxs-lookup"><span data-stu-id="8b6cd-158">Scripts</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="8b6cd-159">每个 .osd 文件都将转换为一个单独的 .xml 文件，其中包含在 App-v 5.1 部署配置格式中列出的项目。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-159">Each .osd file is converted to a separate, corresponding .xml file that contains the items listed here in App-V 5.1 deployment configuration format.</span></span> <span data-ttu-id="8b6cd-160">然后，可以从这些 .xml 文件中复制这些项，并根据需要放置在部署配置或用户配置文件中。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-160">These items can then be copied from these .xml files and placed in the deployment configuration or user configuration files as desired.</span></span></p>
<p><span data-ttu-id="8b6cd-161">在此示例中，存在与源目录中的三个 .osd 文件对应的三个 .xml 文件。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-161">In this example, there are three .xml files, corresponding with the three .osd files in the source directory.</span></span> <span data-ttu-id="8b6cd-162">每个 .xml 文件包含环境变量、快捷方式、文件类型关联、注册表信息和其对应的 .osd 文件中的脚本。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-162">Each .xml file contains the environment variables, shortcuts, file type associations, registry information, and scripts in its corresponding .osd file.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><ul>
<li><p><span data-ttu-id="8b6cd-163">X.x.x。x</span><span class="sxs-lookup"><span data-stu-id="8b6cd-163">X.osd</span></span></p></li>
<li><p><span data-ttu-id="8b6cd-164">.Osd</span><span class="sxs-lookup"><span data-stu-id="8b6cd-164">Y.osd</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="8b6cd-165">ContosoApp</span><span class="sxs-lookup"><span data-stu-id="8b6cd-165">ContosoApp.appv</span></span></p></li>
<li><p><span data-ttu-id="8b6cd-166">ContosoApp_DeploymentConfig.xml</span><span class="sxs-lookup"><span data-stu-id="8b6cd-166">ContosoApp_DeploymentConfig.xml</span></span></p></li>
<li><p><span data-ttu-id="8b6cd-167">ContosoApp_UserConfig.xml</span><span class="sxs-lookup"><span data-stu-id="8b6cd-167">ContosoApp_UserConfig.xml</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="8b6cd-168">环境变量</span><span class="sxs-lookup"><span data-stu-id="8b6cd-168">Environment variables</span></span></p></li>
<li><p><span data-ttu-id="8b6cd-169">指向</span><span class="sxs-lookup"><span data-stu-id="8b6cd-169">Shortcuts</span></span></p></li>
<li><p><span data-ttu-id="8b6cd-170">文件类型关联</span><span class="sxs-lookup"><span data-stu-id="8b6cd-170">File type associations</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="8b6cd-171">将转换参数中指定的 .osd 文件中的信息 <code>-OSDsToIncludeInPackage</code> ，并将其放置在程序包内。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-171">The information from the .osd files specified in the <code>-OSDsToIncludeInPackage</code> parameter are converted and placed inside the package.</span></span> <span data-ttu-id="8b6cd-172">然后，转换器将使用程序包的内容填充部署配置文件和用户配置文件，就像在对新包进行排序时 App-v 排序器一样。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-172">The converter then populates the deployment configuration file and the user configuration file with the contents of the package, just as App-V Sequencer does when sequencing a new package.</span></span></p>
<p><span data-ttu-id="8b6cd-173">在此示例中，X-osd 和 Y 中包含的环境变量、快捷方式和文件类型关联已转换并放置在 App-v 包中，并且其中一些信息也包含在部署配置和用户配置文件中。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-173">In this example, environment variables, shortcuts, and file type associations included in X.osd and Y.osd were converted and placed in the App-V package, and some of this information was also included in the deployment configuration and user configuration files.</span></span> <span data-ttu-id="8b6cd-174">使用了 x.x.x.x 和 a.x，因为它们作为参数包含在 <code>-OSDsToIncludeInPackage</code> 参数中。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-174">X.osd and Y.osd were used because they were included as arguments to the <code>-OSDsToIncludeInPackage</code> parameter.</span></span> <span data-ttu-id="8b6cd-175">程序包中不包含来自 Z 的任何信息，因为它未包含在其中一个参数中。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-175">No information from Z.osd was included in the package, because it was not included as one of these arguments.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="8b6cd-176">转换使用早期版本的 App-v 创建的程序包</span><span class="sxs-lookup"><span data-stu-id="8b6cd-176">Converting packages created using a prior version of App-V</span></span>


<span data-ttu-id="8b6cd-177">使用程序包转换器实用工具升级使用 app-v 5.0 之前的 app-v 版本创建的虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-177">Use the package converter utility to upgrade virtual application packages created using versions of App-V prior to App-V 5.0.</span></span> <span data-ttu-id="8b6cd-178">程序包转换器使用 PowerShell 转换程序包，如果你有多个需要转换的程序包，则可以帮助自动处理该进程。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-178">The package converter uses PowerShell to convert packages and can help automate the process if you have many packages that require conversion.</span></span>

<span data-ttu-id="8b6cd-179">**重要提示** 转换现有程序包后，应该先测试程序包，然后再部署程序包，以确保转换过程成功。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-179">**Important** After you convert an existing package you should test the package prior to deploying the package to ensure the conversion process was successful.</span></span>

 

**<span data-ttu-id="8b6cd-180">转换现有程序包之前需要了解的内容</span><span class="sxs-lookup"><span data-stu-id="8b6cd-180">What to know before you convert existing packages</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8b6cd-181">问题</span><span class="sxs-lookup"><span data-stu-id="8b6cd-181">Issue</span></span></th>
<th align="left"><span data-ttu-id="8b6cd-182">解决方法</span><span class="sxs-lookup"><span data-stu-id="8b6cd-182">Workaround</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b6cd-183">转换后，使用 DSC 的虚拟包不会链接。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-183">Virtual packages using DSC are not linked after conversion.</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b6cd-184">使用连接组链接程序包。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-184">Link the packages using connection groups.</span></span> <span data-ttu-id="8b6cd-185">请参阅 <a href="managing-connection-groups51.md" data-raw-source="[Managing Connection Groups](managing-connection-groups51.md)"> 管理连接组 </a> 。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-185">See <a href="managing-connection-groups51.md" data-raw-source="[Managing Connection Groups](managing-connection-groups51.md)">Managing Connection Groups</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8b6cd-186">在转换期间检测到环境变量冲突。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-186">Environment variable conflicts are detected during conversion.</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b6cd-187">解决关联的 .osd 文件中的任何冲突 <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-187">Resolve any conflicts in the associated <strong>.osd</strong> file.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b6cd-188">在转换期间检测到硬编码路径。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-188">Hard-coded paths are detected during conversion.</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b6cd-189">硬编码路径难以正确转换。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-189">Hard-coded paths are difficult to convert correctly.</span></span> <span data-ttu-id="8b6cd-190">程序包转换器将检测并返回包含硬编码路径的文件的程序包。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-190">The package converter will detect and return packages with files that contain hard-coded paths.</span></span> <span data-ttu-id="8b6cd-191">查看带有硬编码路径的文件，并确定软件包是否需要该文件。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-191">View the file with the hard-coded path, and determine whether the package requires the file.</span></span> <span data-ttu-id="8b6cd-192">如果是这样，建议重新序列化程序包。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-192">If so, it is recommended to re-sequence the package.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="8b6cd-193">转换程序包时，检查是否有失败的文件或快捷方式。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-193">When converting a package check for failing files or shortcuts.</span></span> <span data-ttu-id="8b6cd-194">在 App-v 4.6 程序包中找到该项目。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-194">Locate the item in App-V 4.6 package.</span></span> <span data-ttu-id="8b6cd-195">它可能是一个硬编码的路径。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-195">It could possibly be a hard-coded path.</span></span> <span data-ttu-id="8b6cd-196">转换路径。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-196">Convert the path.</span></span>

<span data-ttu-id="8b6cd-197">**注意** 建议使用 app-v 5.1 sequencer 来转换需要利用功能的关键应用程序或应用程序。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-197">**Note** It is recommended that you use the App-V 5.1 sequencer for converting critical applications or applications that need to take advantage of features.</span></span> <span data-ttu-id="8b6cd-198">请参阅[如何使用 app-v 5.1 对新应用程序进行排序](how-to-sequence-a-new-application-with-app-v-51-beta-gb18030.md)。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-198">See, [How to Sequence a New Application with App-V 5.1](how-to-sequence-a-new-application-with-app-v-51-beta-gb18030.md).</span></span>

<span data-ttu-id="8b6cd-199">如果转换后的程序包未打开，还建议使用 App-v 5.1 sequencer 对应用程序进行重新排序。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-199">If a converted package does not open after you convert it, it is also recommended that you re-sequence the application using the App-V 5.1 sequencer.</span></span>

 

[<span data-ttu-id="8b6cd-200">如何转换在以前版本的 App-V 中创建的程序包</span><span class="sxs-lookup"><span data-stu-id="8b6cd-200">How to Convert a Package Created in a Previous Version of App-V</span></span>](how-to-convert-a-package-created-in-a-previous-version-of-app-v51.md)

## <span data-ttu-id="8b6cd-201">迁移客户端</span><span class="sxs-lookup"><span data-stu-id="8b6cd-201">Migrating Clients</span></span>


<span data-ttu-id="8b6cd-202">下表显示了升级客户端的推荐方法。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-202">The following table displays the recommended method for upgrading clients.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8b6cd-203">任务</span><span class="sxs-lookup"><span data-stu-id="8b6cd-203">Task</span></span></th>
<th align="left"><span data-ttu-id="8b6cd-204">详细信息</span><span class="sxs-lookup"><span data-stu-id="8b6cd-204">More Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b6cd-205">将你的环境升级到最新版本的 App-v 4。6</span><span class="sxs-lookup"><span data-stu-id="8b6cd-205">Upgrade your environment to the latest version of App-V4.6</span></span></p></td>
<td align="left"><p><a href="../appv-v4/application-virtualization-deployment-and-upgrade-considerations-copy.md" data-raw-source="[Application Virtualization Deployment and Upgrade Considerations](../appv-v4/application-virtualization-deployment-and-upgrade-considerations-copy.md)"><span data-ttu-id="8b6cd-206">应用程序虚拟化部署和升级注意事项 </a> 。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-206">Application Virtualization Deployment and Upgrade Considerations</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8b6cd-207">安装支持共存的 app-v 5.1 客户端。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-207">Install the App-V 5.1 client with co-existence enabled.</span></span></p></td>
<td align="left"><p><a href="how-to-deploy-the-app-v-46-and-the-app-v--51-client-on-the-same-computer.md" data-raw-source="[How to Deploy the App-V 4.6 and the App-V 5.1 Client on the Same Computer](how-to-deploy-the-app-v-46-and-the-app-v--51-client-on-the-same-computer.md)"><span data-ttu-id="8b6cd-208">如何在同一台计算机上部署 app-v 4.6 和 app-v 5.1 客户端 </a> 。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-208">How to Deploy the App-V 4.6 and the App-V 5.1 Client on the Same Computer</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b6cd-209">顺序和推出 app-v 5.1 程序包。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-209">Sequence and roll out App-V 5.1 packages.</span></span> <span data-ttu-id="8b6cd-210">根据需要，取消发布 app-v 4.6 程序包。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-210">As needed, unpublish App-V 4.6 packages.</span></span></p></td>
<td align="left"><p><a href="how-to-sequence-a-new-application-with-app-v-51-beta-gb18030.md" data-raw-source="[How to Sequence a New Application with App-V 5.1](how-to-sequence-a-new-application-with-app-v-51-beta-gb18030.md)"><span data-ttu-id="8b6cd-211">如何使用 App-v 5.1 对新应用程序进行排序 </a> 。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-211">How to Sequence a New Application with App-V 5.1</a>.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="8b6cd-212">**重要提示** 您必须运行最新版本的 App-V 4.6 才能使用共存模式。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-212">**Important** You must be running the latest version of App-V4.6 to use coexistence mode.</span></span> <span data-ttu-id="8b6cd-213">此外，在对程序包进行排序时，必须配置 "管理机构" 设置，该设置位于 **"用户\*\*\*\*配置**" 部分中。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-213">Additionally, when you sequence a package, you must configure the Managing Authority setting, which is in the **User Configuration** is located in the **User Configuration** section.</span></span>

 

## <span data-ttu-id="8b6cd-214">迁移 app-v 5.1 服务器的完整基础结构</span><span class="sxs-lookup"><span data-stu-id="8b6cd-214">Migrating the App-V 5.1 Server Full Infrastructure</span></span>


<span data-ttu-id="8b6cd-215">没有直接的方法可升级到完整的 app-v 5.1 基础结构。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-215">There is no direct method to upgrade to a full App-V 5.1 infrastructure.</span></span> <span data-ttu-id="8b6cd-216">有关升级 app-v 服务器的信息，请使用以下部分中的信息。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-216">Use the information in the following section for information about upgrading the App-V server.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8b6cd-217">任务</span><span class="sxs-lookup"><span data-stu-id="8b6cd-217">Task</span></span></th>
<th align="left"><span data-ttu-id="8b6cd-218">详细信息</span><span class="sxs-lookup"><span data-stu-id="8b6cd-218">More Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b6cd-219">将你的环境升级到最新版本的 App-v 4.6。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-219">Upgrade your environment to the latest version of App-V4.6.</span></span></p></td>
<td align="left"><p><a href="../appv-v4/application-virtualization-deployment-and-upgrade-considerations-copy.md" data-raw-source="[Application Virtualization Deployment and Upgrade Considerations](../appv-v4/application-virtualization-deployment-and-upgrade-considerations-copy.md)"><span data-ttu-id="8b6cd-220">应用程序虚拟化部署和升级注意事项 </a> 。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-220">Application Virtualization Deployment and Upgrade Considerations</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8b6cd-221">部署 app-v 5.1 版本的客户端。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-221">Deploy App-V 5.1 version of the client.</span></span></p></td>
<td align="left"><p><a href="how-to-deploy-the-app-v-client-51gb18030.md" data-raw-source="[How to Deploy the App-V Client](how-to-deploy-the-app-v-client-51gb18030.md)"><span data-ttu-id="8b6cd-222">如何部署 app-v 客户端 </a> 。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-222">How to Deploy the App-V Client</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b6cd-223">安装 App-v 5.1 server。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-223">Install App-V 5.1 server.</span></span></p></td>
<td align="left"><p><a href="how-to-deploy-the-app-v-51-server.md" data-raw-source="[How to Deploy the App-V 5.1 Server](how-to-deploy-the-app-v-51-server.md)"><span data-ttu-id="8b6cd-224">如何部署 app-v 5.1 服务器 </a> 。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-224">How to Deploy the App-V 5.1 Server</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8b6cd-225">迁移现有程序包。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-225">Migrate existing packages.</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b6cd-226">查看 <strong> 使用本文的早期版本 app-v 部分创建的转换程序包 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-226">See the <strong>Converting packages created using a prior version of App-V</strong> section of this article.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="8b6cd-227">其他迁移任务</span><span class="sxs-lookup"><span data-stu-id="8b6cd-227">Additional Migration tasks</span></span>


<span data-ttu-id="8b6cd-228">你还可以执行其他迁移任务，例如重新配置终结点，以及打开使用运行 App-v 5.1 客户端的计算机上的早期版本创建的程序包。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-228">You can also perform additional migration tasks such as reconfiguring end points as well as opening a package created using a prior version on a computer running the App-V 5.1 client.</span></span> <span data-ttu-id="8b6cd-229">以下链接提供了有关执行这些任务的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8b6cd-229">The following links provide more information about performing these tasks.</span></span>

[<span data-ttu-id="8b6cd-230">如何为特定计算机上的所有用户将 App-V 4.6 程序包中的扩展点迁移到转换后的 App-V 5.1 程序包</span><span class="sxs-lookup"><span data-stu-id="8b6cd-230">How to Migrate Extension Points From an App-V 4.6 Package to a Converted App-V 5.1 Package for All Users on a Specific Computer</span></span>](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-51-package-for-all-users-on-a-specific-computer.md)

[<span data-ttu-id="8b6cd-231">如何为特定用户将 App-V 4.6 程序包中的扩展点迁移到 App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="8b6cd-231">How to Migrate Extension Points From an App-V 4.6 Package to App-V 5.1 for a Specific User</span></span>](how-to-migrate-extension-points-from-an-app-v-46-package-to-app-v-51-for-a-specific-user.md)

[<span data-ttu-id="8b6cd-232">如何为特定计算机上的所有用户将 App-V 5.1 程序包中的扩展点还原到 App-V 4.6 程序包</span><span class="sxs-lookup"><span data-stu-id="8b6cd-232">How to Revert Extension Points from an App-V 5.1 Package to an App-V 4.6 Package For All Users on a Specific Computer</span></span>](how-to-revert-extension-points-from-an-app-v-51-package-to-an-app-v-46-package-for-all-users-on-a-specific-computer.md)

[<span data-ttu-id="8b6cd-233">如何为特定用户将 App-V 5.1 程序包中的扩展点还原到 App-V 4.6 程序包</span><span class="sxs-lookup"><span data-stu-id="8b6cd-233">How to Revert Extension Points From an App-V 5.1 Package to an App-V 4.6 Package for a Specific User</span></span>](how-to-revert-extension-points-from-an-app-v-51-package-to-an-app-v-46-package-for-a-specific-user.md)







## <span data-ttu-id="8b6cd-234">用于执行 App-v 迁移任务的其他资源</span><span class="sxs-lookup"><span data-stu-id="8b6cd-234">Other resources for performing App-V migration tasks</span></span>


[<span data-ttu-id="8b6cd-235">App-V 5.1 的操作</span><span class="sxs-lookup"><span data-stu-id="8b6cd-235">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

[<span data-ttu-id="8b6cd-236">简化的 Microsoft App-V 5.1 管理服务器升级过程</span><span class="sxs-lookup"><span data-stu-id="8b6cd-236">A simplified Microsoft App-V 5.1 Management Server upgrade procedure</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=786330)

 

 





