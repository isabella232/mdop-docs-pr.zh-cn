---
title: 应用程序发布和客户端交互
description: 应用程序发布和客户端交互
author: dansimp
ms.assetid: c69a724a-85d1-4e2d-94a2-7ffe0b47d971
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: b6080a501a8fdd2a39876ff979aa7a2982c76bbb
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798620"
---
# <span data-ttu-id="6aa5a-103">应用程序发布和客户端交互</span><span class="sxs-lookup"><span data-stu-id="6aa5a-103">Application Publishing and Client Interaction</span></span>


<span data-ttu-id="6aa5a-104">本文提供有关常见应用 V 客户端操作及其与本地操作系统的集成的技术信息。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-104">This article provides technical information about common App-V client operations and their integration with the local operating system.</span></span>

-   [<span data-ttu-id="6aa5a-105">由 Sequencer 创建的 app-v 包文件</span><span class="sxs-lookup"><span data-stu-id="6aa5a-105">App-V package files created by the Sequencer</span></span>](#bkmk-appv-pkg-files-list)

-   [<span data-ttu-id="6aa5a-106">Appv 文件中有哪些内容？</span><span class="sxs-lookup"><span data-stu-id="6aa5a-106">What’s in the appv file?</span></span>](#bkmk-appv-file-contents)

-   [<span data-ttu-id="6aa5a-107">App-v 客户端数据存储位置</span><span class="sxs-lookup"><span data-stu-id="6aa5a-107">App-V client data storage locations</span></span>](#bkmk-files-data-storage)

-   [<span data-ttu-id="6aa5a-108">程序包注册表</span><span class="sxs-lookup"><span data-stu-id="6aa5a-108">Package registry</span></span>](#bkmk-pkg-registry)

-   [<span data-ttu-id="6aa5a-109">App-v 包存储行为</span><span class="sxs-lookup"><span data-stu-id="6aa5a-109">App-V package store behavior</span></span>](#bkmk-pkg-store-behavior)

-   [<span data-ttu-id="6aa5a-110">漫游注册表和数据</span><span class="sxs-lookup"><span data-stu-id="6aa5a-110">Roaming registry and data</span></span>](#bkmk-roaming-reg-data)

-   [<span data-ttu-id="6aa5a-111">App-v 客户端应用程序生命周期管理</span><span class="sxs-lookup"><span data-stu-id="6aa5a-111">App-V client application lifecycle management</span></span>](#bkmk-clt-app-lifecycle)

-   [<span data-ttu-id="6aa5a-112">App-v 程序包的集成</span><span class="sxs-lookup"><span data-stu-id="6aa5a-112">Integration of App-V packages</span></span>](#bkmk-integr-appv-pkgs)

-   [<span data-ttu-id="6aa5a-113">动态配置处理</span><span class="sxs-lookup"><span data-stu-id="6aa5a-113">Dynamic configuration processing</span></span>](#bkmk-dynamic-config)

-   [<span data-ttu-id="6aa5a-114">并行程序集</span><span class="sxs-lookup"><span data-stu-id="6aa5a-114">Side-by-side assemblies</span></span>](#bkmk-sidebyside-assemblies)

-   [<span data-ttu-id="6aa5a-115">客户端日志记录</span><span class="sxs-lookup"><span data-stu-id="6aa5a-115">Client logging</span></span>](#bkmk-client-logging)

<span data-ttu-id="6aa5a-116">有关其他参考信息，请参阅[Microsoft Application Virtualization （app-v）文档资源下载页面](https://www.microsoft.com/download/details.aspx?id=27760)。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-116">For additional reference information, see [Microsoft Application Virtualization (App-V) Documentation Resources Download Page](https://www.microsoft.com/download/details.aspx?id=27760).</span></span>

## <a href="" id="bkmk-appv-pkg-files-list"></a><span data-ttu-id="6aa5a-117">由 Sequencer 创建的 app-v 包文件</span><span class="sxs-lookup"><span data-stu-id="6aa5a-117">App-V package files created by the Sequencer</span></span>


<span data-ttu-id="6aa5a-118">排序器创建 app-v 包并生成一个虚拟化的应用程序。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-118">The Sequencer creates App-V packages and produces a virtualized application.</span></span> <span data-ttu-id="6aa5a-119">排序过程将创建以下文件：</span><span class="sxs-lookup"><span data-stu-id="6aa5a-119">The sequencing process creates the following files:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6aa5a-120">文件</span><span class="sxs-lookup"><span data-stu-id="6aa5a-120">File</span></span></th>
<th align="left"><span data-ttu-id="6aa5a-121">描述</span><span class="sxs-lookup"><span data-stu-id="6aa5a-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6aa5a-122">appv</span><span class="sxs-lookup"><span data-stu-id="6aa5a-122">.appv</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="6aa5a-123">主程序包文件，其中包含来自排序过程的已捕获资源和状态信息。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-123">The primary package file, which contains the captured assets and state information from the sequencing process.</span></span></p></li>
<li><p><span data-ttu-id="6aa5a-124">程序包文件、发布信息和注册表的体系结构，可标记化形式可在传递时重新应用到计算机和特定用户。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-124">Architecture of the package file, publishing information, and registry in a tokenized form that can be reapplied to a machine and to a specific user upon delivery.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6aa5a-125">.MSI</span><span class="sxs-lookup"><span data-stu-id="6aa5a-125">.MSI</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-126">可用于手动部署 appv 文件或使用第三方部署平台的可执行部署包装程序。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-126">Executable deployment wrapper that you can use to deploy .appv files manually or by using a third-party deployment platform.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6aa5a-127">_DeploymentConfig.XML</span><span class="sxs-lookup"><span data-stu-id="6aa5a-127">_DeploymentConfig.XML</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-128">用于自定义程序包中的所有应用程序的默认发布参数的文件，该程序包中将全局部署到运行 App-v 客户端的计算机上的所有用户。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-128">File used to customize the default publishing parameters for all applications in a package that is deployed globally to all users on a computer that is running the App-V client.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6aa5a-129">_UserConfig.XML</span><span class="sxs-lookup"><span data-stu-id="6aa5a-129">_UserConfig.XML</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-130">用于自定义程序包中的所有应用程序的发布参数的文件，该程序包中已部署到运行 App-v 客户端的计算机上的特定用户。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-130">File used to customize the publishing parameters for all applications in a package that is a deployed to a specific user on a computer that is running the App-V client.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6aa5a-131">Report.xml</span><span class="sxs-lookup"><span data-stu-id="6aa5a-131">Report.xml</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-132">排序过程中产生的消息摘要，包括省略的驱动程序、文件和注册表位置。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-132">Summary of messages resulting from the sequencing process, including omitted drivers, files, and registry locations.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6aa5a-133">.CAB</span><span class="sxs-lookup"><span data-stu-id="6aa5a-133">.CAB</span></span></p></td>
<td align="left"><p><em><span data-ttu-id="6aa5a-134">可选： </em> 用于自动重建以前已排序的虚拟应用程序包的程序包加速器文件。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-134">Optional:</em> Package accelerator file used to automatically rebuild a previously sequenced virtual application package.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6aa5a-135">.appvt</span><span class="sxs-lookup"><span data-stu-id="6aa5a-135">.appvt</span></span></p></td>
<td align="left"><p><em><span data-ttu-id="6aa5a-136">可选： </em> sequencer 模板文件，用于保留常用的 sequencer 设置。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-136">Optional:</em> Sequencer template file used to retain commonly reused Sequencer settings.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="6aa5a-137">有关序列化的信息，请参阅[应用程序虚拟化5.0 排序指南](https://www.microsoft.com/download/details.aspx?id=27760)。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-137">For information about sequencing, see [Application Virtualization 5.0 Sequencing Guide](https://www.microsoft.com/download/details.aspx?id=27760).</span></span>

## <a href="" id="bkmk-appv-file-contents"></a><span data-ttu-id="6aa5a-138">Appv 文件中有哪些内容？</span><span class="sxs-lookup"><span data-stu-id="6aa5a-138">What’s in the appv file?</span></span>


<span data-ttu-id="6aa5a-139">Appv 文件是一个容器，它将 XML 和非 XML 文件一起存储在单个实体中。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-139">The appv file is a container that stores XML and non-XML files together in a single entity.</span></span> <span data-ttu-id="6aa5a-140">此文件是从 AppX 格式生成的，该格式基于开放式打包约定（OPC）标准。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-140">This file is built from the AppX format, which is based on the Open Packaging Conventions (OPC) standard.</span></span>

<span data-ttu-id="6aa5a-141">若要查看 appv 文件内容，请制作程序包的副本，然后将复制的文件重命名为 ZIP 扩展。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-141">To view the appv file contents, make a copy of the package, and then rename the copied file to a ZIP extension.</span></span>

<span data-ttu-id="6aa5a-142">Appv 文件包含以下文件夹和文件，这些文件夹和文件是在创建和发布虚拟应用程序时使用的：</span><span class="sxs-lookup"><span data-stu-id="6aa5a-142">The appv file contains the following folder and files, which are used when creating and publishing a virtual application:</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6aa5a-143">名称</span><span class="sxs-lookup"><span data-stu-id="6aa5a-143">Name</span></span></th>
<th align="left"><span data-ttu-id="6aa5a-144">类型</span><span class="sxs-lookup"><span data-stu-id="6aa5a-144">Type</span></span></th>
<th align="left"><span data-ttu-id="6aa5a-145">描述</span><span class="sxs-lookup"><span data-stu-id="6aa5a-145">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6aa5a-146">根</span><span class="sxs-lookup"><span data-stu-id="6aa5a-146">Root</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-147">文件夹</span><span class="sxs-lookup"><span data-stu-id="6aa5a-147">File folder</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-148">包含在排序期间捕获的虚拟化应用程序的文件系统的目录。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-148">Directory that contains the file system for the virtualized application that is captured during sequencing.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6aa5a-149">[Content_Types] .xml</span><span class="sxs-lookup"><span data-stu-id="6aa5a-149">[Content_Types].xml</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-150">XML 文件</span><span class="sxs-lookup"><span data-stu-id="6aa5a-150">XML File</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-151">Appv 文件（如 .DLL、EXE、BIN）中的核心内容类型列表。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-151">List of the core content types in the appv file (e.g. DLL, EXE, BIN).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6aa5a-152">AppxBlockMap.xml</span><span class="sxs-lookup"><span data-stu-id="6aa5a-152">AppxBlockMap.xml</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-153">XML 文件</span><span class="sxs-lookup"><span data-stu-id="6aa5a-153">XML File</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-154">Appv 文件的布局，该布局使用 File、Block 和 BlockMap 元素，这些元素可启用 App-v 包中文件的位置和验证。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-154">Layout of the appv file, which uses File, Block, and BlockMap elements that enable location and validation of files in the App-V package.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6aa5a-155">AppxManifest.xml</span><span class="sxs-lookup"><span data-stu-id="6aa5a-155">AppxManifest.xml</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-156">XML 文件</span><span class="sxs-lookup"><span data-stu-id="6aa5a-156">XML File</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-157">程序包的元数据，其中包含添加、发布和启动程序包所需的信息。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-157">Metadata for the package that contains the required information for adding, publishing, and launching the package.</span></span> <span data-ttu-id="6aa5a-158">包括扩展点（文件类型关联和快捷方式）以及与该包关联的名称和 Guid。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-158">Includes extension points (file type associations and shortcuts) and the names and GUIDs associated with the package.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6aa5a-159">FilesystemMetadata.xml</span><span class="sxs-lookup"><span data-stu-id="6aa5a-159">FilesystemMetadata.xml</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-160">XML 文件</span><span class="sxs-lookup"><span data-stu-id="6aa5a-160">XML File</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-161">排序期间捕获的文件的列表，包括属性（例如，目录、文件、不透明目录、空目录以及长名称和短名称）。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-161">List of the files captured during sequencing, including attributes (e.g., directories, files, opaque directories, empty directories,and long and short names).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6aa5a-162">PackageHistory.xml</span><span class="sxs-lookup"><span data-stu-id="6aa5a-162">PackageHistory.xml</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-163">XML 文件</span><span class="sxs-lookup"><span data-stu-id="6aa5a-163">XML File</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-164">有关排序计算机（操作系统版本、Internet Explorer 版本、.Net Framework 版本）和进程（升级、程序包版本）的信息。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-164">Information about the sequencing computer (operating system version, Internet Explorer version, .Net Framework version) and process (upgrade, package version).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6aa5a-165">注册表 .dat</span><span class="sxs-lookup"><span data-stu-id="6aa5a-165">Registry.dat</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-166">DAT 文件</span><span class="sxs-lookup"><span data-stu-id="6aa5a-166">DAT File</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-167">程序包的排序过程中捕获的注册表项和值。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-167">Registry keys and values captured during the sequencing process for the package.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6aa5a-168">StreamMap.xml</span><span class="sxs-lookup"><span data-stu-id="6aa5a-168">StreamMap.xml</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-169">XML 文件</span><span class="sxs-lookup"><span data-stu-id="6aa5a-169">XML File</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-170">主功能块和发布功能块的文件列表。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-170">List of files for the primary and publishing feature block.</span></span> <span data-ttu-id="6aa5a-171">发布功能块包含用于发布程序包的 .ICO 文件和所需的文件（EXE 和 DLL）部分。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-171">The publishing feature block contains the ICO files and required portions of files (EXE and DLL) for publishing the package.</span></span> <span data-ttu-id="6aa5a-172">当存在时，主要功能块包括已针对排序过程中的流式处理进行了优化的文件。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-172">When present, the primary feature block includes files that have been optimized for streaming during the sequencing process.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-files-data-storage"></a><span data-ttu-id="6aa5a-173">App-v 客户端数据存储位置</span><span class="sxs-lookup"><span data-stu-id="6aa5a-173">App-V client data storage locations</span></span>


<span data-ttu-id="6aa5a-174">App-v 客户端执行任务以确保虚拟应用程序正常运行，例如本地安装的应用程序。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-174">The App-V client performs tasks to ensure that virtual applications run properly and work like locally installed applications.</span></span> <span data-ttu-id="6aa5a-175">打开和运行虚拟应用程序的过程需要从虚拟文件系统和注册表映射，以确保应用程序具有用户期望的传统应用程序所必需的组件。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-175">The process of opening and running virtual applications requires mapping from the virtual file system and registry to ensure the application has the required components of a traditional application expected by users.</span></span> <span data-ttu-id="6aa5a-176">本部分介绍运行虚拟应用程序所需的资源，并列出应用 V 存储资源的位置。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-176">This section describes the assets that are required to run virtual applications and lists the location where App-V stores the assets.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6aa5a-177">名称</span><span class="sxs-lookup"><span data-stu-id="6aa5a-177">Name</span></span></th>
<th align="left"><span data-ttu-id="6aa5a-178">位置</span><span class="sxs-lookup"><span data-stu-id="6aa5a-178">Location</span></span></th>
<th align="left"><span data-ttu-id="6aa5a-179">描述</span><span class="sxs-lookup"><span data-stu-id="6aa5a-179">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6aa5a-180">程序包存储</span><span class="sxs-lookup"><span data-stu-id="6aa5a-180">Package Store</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-181">%ProgramData%\App-V</span><span class="sxs-lookup"><span data-stu-id="6aa5a-181">%ProgramData%\App-V</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-182">只读程序包文件的默认位置</span><span class="sxs-lookup"><span data-stu-id="6aa5a-182">Default location for read only package files</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6aa5a-183">计算机目录</span><span class="sxs-lookup"><span data-stu-id="6aa5a-183">Machine Catalog</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-184">%ProgramData%\Microsoft\AppV\Client\Catalog</span><span class="sxs-lookup"><span data-stu-id="6aa5a-184">%ProgramData%\Microsoft\AppV\Client\Catalog</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-185">包含每台计算机配置文档</span><span class="sxs-lookup"><span data-stu-id="6aa5a-185">Contains per-machine configuration documents</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6aa5a-186">用户目录</span><span class="sxs-lookup"><span data-stu-id="6aa5a-186">User Catalog</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-187">%AppData%\Microsoft\AppV\Client\Catalog</span><span class="sxs-lookup"><span data-stu-id="6aa5a-187">%AppData%\Microsoft\AppV\Client\Catalog</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-188">包含每用户配置文档</span><span class="sxs-lookup"><span data-stu-id="6aa5a-188">Contains per-user configuration documents</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6aa5a-189">快捷方式备份</span><span class="sxs-lookup"><span data-stu-id="6aa5a-189">Shortcut Backups</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-190">%AppData%\Microsoft\AppV\Client\Integration\ShortCutBackups</span><span class="sxs-lookup"><span data-stu-id="6aa5a-190">%AppData%\Microsoft\AppV\Client\Integration\ShortCutBackups</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-191">存储在程序包取消发布时启用还原的以前的集成点</span><span class="sxs-lookup"><span data-stu-id="6aa5a-191">Stores previous integration points that enable restore on package unpublish</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6aa5a-192">写入时复制（牛）漫游</span><span class="sxs-lookup"><span data-stu-id="6aa5a-192">Copy on Write (COW) Roaming</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-193">%AppData%\Microsoft\AppV\Client\VFS</span><span class="sxs-lookup"><span data-stu-id="6aa5a-193">%AppData%\Microsoft\AppV\Client\VFS</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-194">程序包修改的可写入漫游位置</span><span class="sxs-lookup"><span data-stu-id="6aa5a-194">Writeable roaming location for package modification</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6aa5a-195">写入时复制（牛）局部</span><span class="sxs-lookup"><span data-stu-id="6aa5a-195">Copy on Write (COW) Local</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-196">%LocalAppData%\Microsoft\AppV\Client\VFS</span><span class="sxs-lookup"><span data-stu-id="6aa5a-196">%LocalAppData%\Microsoft\AppV\Client\VFS</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-197">程序包修改的可写非漫游位置</span><span class="sxs-lookup"><span data-stu-id="6aa5a-197">Writeable non-roaming location for package modification</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6aa5a-198">计算机注册表</span><span class="sxs-lookup"><span data-stu-id="6aa5a-198">Machine Registry</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-199">HKLM\Software\Microsoft\AppV</span><span class="sxs-lookup"><span data-stu-id="6aa5a-199">HKLM\Software\Microsoft\AppV</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-200">包含程序包状态信息，包括计算机或全局发布的程序包（计算机配置单元）的 VReg</span><span class="sxs-lookup"><span data-stu-id="6aa5a-200">Contains package state information, including VReg for machine or globally published packages (Machine hive)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6aa5a-201">用户注册表</span><span class="sxs-lookup"><span data-stu-id="6aa5a-201">User Registry</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-202">HKCU\Software\Microsoft\AppV</span><span class="sxs-lookup"><span data-stu-id="6aa5a-202">HKCU\Software\Microsoft\AppV</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-203">包含用户程序包状态信息，包括 VReg</span><span class="sxs-lookup"><span data-stu-id="6aa5a-203">Contains user package state information including VReg</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6aa5a-204">用户注册表类</span><span class="sxs-lookup"><span data-stu-id="6aa5a-204">User Registry Classes</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-205">HKCU\Software\Classes\AppV</span><span class="sxs-lookup"><span data-stu-id="6aa5a-205">HKCU\Software\Classes\AppV</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-206">包含其他用户程序包状态信息</span><span class="sxs-lookup"><span data-stu-id="6aa5a-206">Contains additional user package state information</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="6aa5a-207">表格的其他详细信息在以下部分以及整个文档中提供。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-207">Additional details for the table are provided in the section below and throughout the document.</span></span>

### <span data-ttu-id="6aa5a-208">程序包存储</span><span class="sxs-lookup"><span data-stu-id="6aa5a-208">Package store</span></span>

<span data-ttu-id="6aa5a-209">App-v 客户端管理程序包存储中挂载的应用程序资源。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-209">The App-V Client manages the applications assets mounted in the package store.</span></span> <span data-ttu-id="6aa5a-210">此默认存储位置为 `%ProgramData%\App-V` ，但你可以使用 PowerShell 命令在安装过程中或之后配置它 `Set-AppVClientConfiguration` ，这将修改本地注册表（ `PackageInstallationRoot` 注册表项下的值 `HKLM\Software\Microsoft\AppV\Client\Streaming` ）。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-210">This default storage location is `%ProgramData%\App-V`, but you can configure it during or after setup by using the `Set-AppVClientConfiguration` PowerShell command, which modifies the local registry (`PackageInstallationRoot` value under the `HKLM\Software\Microsoft\AppV\Client\Streaming` key).</span></span> <span data-ttu-id="6aa5a-211">程序包存储必须位于客户端操作系统上的本地路径中。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-211">The package store must be located at a local path on the client operating system.</span></span> <span data-ttu-id="6aa5a-212">各个程序包存储在程序包存储区中，位于名为 "程序包 GUID" 和 "版本 GUID" 的子目录中。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-212">The individual packages are stored in the package store in subdirectories named for the Package GUID and Version GUID.</span></span>

<span data-ttu-id="6aa5a-213">特定应用程序的路径示例：</span><span class="sxs-lookup"><span data-stu-id="6aa5a-213">Example of a path to a specific application:</span></span>

``` syntax
C:\ProgramData\App-V\PackGUID\VersionGUID
```

<span data-ttu-id="6aa5a-214">若要在安装过程中更改程序包存储区的默认位置，请参阅[如何部署 App-v 客户端](how-to-deploy-the-app-v-client-gb18030.md)。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-214">To change the default location of the package store during setup, see [How to Deploy the App-V Client](how-to-deploy-the-app-v-client-gb18030.md).</span></span>

### <span data-ttu-id="6aa5a-215">共享内容存储</span><span class="sxs-lookup"><span data-stu-id="6aa5a-215">Shared Content Store</span></span>

<span data-ttu-id="6aa5a-216">如果在 "共享内容存储" 模式下配置了 app-v 客户端，则当出现流错误时，将不会向磁盘写入任何数据，这意味着程序包需要最少的本地磁盘空间（发布数据）。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-216">If the App-V Client is configured in Shared Content Store mode, no data is written to disk when a stream fault occurs, which means that the packages require minimal local disk space (publishing data).</span></span> <span data-ttu-id="6aa5a-217">在 VDI 环境中使用较少的磁盘空间非常可取，在这种情况下，本地存储可以受到限制，并且从高性能的网络位置（如 SAN）流处理应用程序更可取。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-217">The use of less disk space is highly desirable in VDI environments, where local storage can be limited, and streaming the applications from a high performance network location (such as a SAN) is preferable.</span></span> <span data-ttu-id="6aa5a-218">有关共享内容存储模式的详细信息，请参阅 <https://go.microsoft.com/fwlink/p/?LinkId=392750> 。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-218">For more information on shared content store mode, see <https://go.microsoft.com/fwlink/p/?LinkId=392750>.</span></span>

<span data-ttu-id="6aa5a-219">**注意** 计算机和程序包存储必须位于本地驱动器上，即使你使用的是 App-v 客户端的共享内容存储配置也是如此。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-219">**Note** The machine and package store must be located on a local drive, even when you’re using Shared Content Store configurations for the App-V Client.</span></span>

 

### <span data-ttu-id="6aa5a-220">程序包目录</span><span class="sxs-lookup"><span data-stu-id="6aa5a-220">Package catalogs</span></span>

<span data-ttu-id="6aa5a-221">App-v 客户端管理以下两个基于文件的位置：</span><span class="sxs-lookup"><span data-stu-id="6aa5a-221">The App-V Client manages the following two file-based locations:</span></span>

-   **<span data-ttu-id="6aa5a-222">目录（用户和计算机）。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-222">Catalogs (user and machine).</span></span>**

-   <span data-ttu-id="6aa5a-223">**注册表位置**-取决于程序包的目标发布方式。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-223">**Registry locations** - depends on how the package is targeted for publishing.</span></span> <span data-ttu-id="6aa5a-224">计算机的目录（数据存储）和每个单独用户的目录。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-224">There is a Catalog (data store) for the computer, and a catalog for each individual user.</span></span> <span data-ttu-id="6aa5a-225">计算机目录存储适用于所有用户或任何用户的全局信息，用户目录存储适用于特定用户的信息。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-225">The Machine Catalog stores global information applicable to all users or any user, and the User Catalog stores information applicable to a specific user.</span></span> <span data-ttu-id="6aa5a-226">目录是动态配置和清单文件的集合;每个程序包版本的文件和注册表都有离散数据。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-226">The Catalog is a collection of Dynamic Configurations and manifest files; there is discrete data for both file and registry per package version.</span></span> 

### <span data-ttu-id="6aa5a-227">计算机目录</span><span class="sxs-lookup"><span data-stu-id="6aa5a-227">Machine catalog</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6aa5a-228">描述</span><span class="sxs-lookup"><span data-stu-id="6aa5a-228">Description</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-229">在添加和发布程序包时，存储计算机上用户可用的程序包文档。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-229">Stores package documents that are available to users on the machine, when packages are added and published.</span></span> <span data-ttu-id="6aa5a-230">但是，如果程序包在发布时是 "全局" 的，则所有用户都可以使用这些集成。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-230">However, if a package is “global” at publishing time, the integrations are available to all users.</span></span></p>
<p><span data-ttu-id="6aa5a-231">如果程序包是非全局的，则仅为特定用户发布集成，但仍有对客户端计算机上的任何人（例如，程序包目录位于共享磁盘位置）所修改和可见的全局资源。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-231">If a package is non-global, the integrations are published only for specific users, but there are still global resources that are modified and visible to anyone on the client computer (e.g., the package directory is in a shared disk location).</span></span></p>
<p><span data-ttu-id="6aa5a-232">如果程序包对计算机上的用户可用（全局或非全局），则清单存储在计算机目录中。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-232">If a package is available to a user on the computer (global or non-global), the manifest is stored in the Machine Catalog.</span></span> <span data-ttu-id="6aa5a-233">全局发布程序包时，有一个动态配置文件，存储在计算机目录中;因此，根据计算机目录中是否存在策略文件（UserDeploymentConfiguration 文件）确定程序包是否为全局程序包。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-233">When a package is published globally, there is a Dynamic Configuration file, stored in the Machine Catalog; therefore, the determination of whether a package is global is defined according to whether there is a policy file (UserDeploymentConfiguration file) in the Machine Catalog.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6aa5a-234">默认存储位置</span><span class="sxs-lookup"><span data-stu-id="6aa5a-234">Default storage location</span></span></p></td>
<td align="left"><p><code>%programdata%\Microsoft\AppV\Client\Catalog&lt;/code&gt;</p>
<p><span data-ttu-id="6aa5a-235">此位置与程序包存储位置不同。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-235">This location is not the same as the Package Store location.</span></span> <span data-ttu-id="6aa5a-236">程序包存储是程序包文件的黄金或 pristine 副本。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-236">The Package Store is the golden or pristine copy of the package files.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6aa5a-237">计算机目录中的文件</span><span class="sxs-lookup"><span data-stu-id="6aa5a-237">Files in the machine catalog</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="6aa5a-238">Manifest.xml</span><span class="sxs-lookup"><span data-stu-id="6aa5a-238">Manifest.xml</span></span></p></li>
<li><p><span data-ttu-id="6aa5a-239">DeploymentConfiguration.xml</span><span class="sxs-lookup"><span data-stu-id="6aa5a-239">DeploymentConfiguration.xml</span></span></p></li>
<li><p><span data-ttu-id="6aa5a-240">UserManifest.xml （全局发布的程序包）</span><span class="sxs-lookup"><span data-stu-id="6aa5a-240">UserManifest.xml (Globally Published Package)</span></span></p></li>
<li><p><span data-ttu-id="6aa5a-241">UserDeploymentConfiguration.xml （全局发布的程序包）</span><span class="sxs-lookup"><span data-stu-id="6aa5a-241">UserDeploymentConfiguration.xml (Globally Published Package)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6aa5a-242">其他计算机目录位置，在程序包是连接组的一部分时使用</span><span class="sxs-lookup"><span data-stu-id="6aa5a-242">Additional machine catalog location, used when the package is part of a connection group</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-243">以下位置是除上述特定程序包位置之外的其他位置：</span><span class="sxs-lookup"><span data-stu-id="6aa5a-243">The following location is in addition to the specific package location mentioned above:</span></span></p>
<p><code>%programdata%\Microsoft\AppV\Client\Catalog\PackageGroups\ConGroupGUID\ConGroupVerGUID</code></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6aa5a-244">当程序包是连接组的一部分时计算机目录中的其他文件</span><span class="sxs-lookup"><span data-stu-id="6aa5a-244">Additional files in the machine catalog when the package is part of a connection group</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="6aa5a-245">PackageGroupDescriptor.xml</span><span class="sxs-lookup"><span data-stu-id="6aa5a-245">PackageGroupDescriptor.xml</span></span></p></li>
<li><p><span data-ttu-id="6aa5a-246">UserPackageGroupDescriptor.xml （全局发布的连接组）</span><span class="sxs-lookup"><span data-stu-id="6aa5a-246">UserPackageGroupDescriptor.xml (globally published Connection Group)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="6aa5a-247">用户目录</span><span class="sxs-lookup"><span data-stu-id="6aa5a-247">User catalog</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6aa5a-248">描述</span><span class="sxs-lookup"><span data-stu-id="6aa5a-248">Description</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-249">在发布过程中创建。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-249">Created during the publishing process.</span></span> <span data-ttu-id="6aa5a-250">包含用于发布程序包的信息，还可在启动时使用，以确保将程序包预配到特定用户。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-250">Contains information used for publishing the package, and also used at launch to ensure that a package is provisioned to a specific user.</span></span> <span data-ttu-id="6aa5a-251">在漫游位置创建，并且包括特定于用户的发布信息。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-251">Created in a roaming location and includes user-specific publishing information.</span></span></p>
<p><span data-ttu-id="6aa5a-252">为用户发布程序包时，策略文件存储在用户目录中。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-252">When a package is published for a user, the policy file is stored in the User Catalog.</span></span> <span data-ttu-id="6aa5a-253">同时，清单的副本也存储在用户目录中。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-253">At the same time, a copy of the manifest is also stored in the User Catalog.</span></span> <span data-ttu-id="6aa5a-254">删除用户的程序包权限后，将从用户目录中删除相关的程序包文件。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-254">When a package entitlement is removed for a user, the relevant package files are removed from the User Catalog.</span></span> <span data-ttu-id="6aa5a-255">查看用户目录时，管理员可以查看动态配置文件的存在，这表示该程序包有权使用该用户。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-255">Looking at the user catalog, an administrator can view the presence of a Dynamic Configuration file, which indicates that the package is entitled for that user.</span></span></p>
<p><span data-ttu-id="6aa5a-256">对于漫游用户，用户目录需要位于漫游位置或共享位置，以便在默认情况下保留目标用户的旧版 App-v 行为。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-256">For roaming users, the User Catalog needs to be in a roaming or shared location to preserve the legacy App-V behavior of targeting users by default.</span></span> <span data-ttu-id="6aa5a-257">权利和政策与用户（而不是计算机）相关联，因此在用户预配后，他们应与用户漫游。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-257">Entitlement and policy are tied to a user, not a computer, so they should roam with the user once they are provisioned.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6aa5a-258">默认存储位置</span><span class="sxs-lookup"><span data-stu-id="6aa5a-258">Default storage location</span></span></p></td>
<td align="left"><p><code>appdata\roaming\Microsoft\AppV\Client\Catalog\Packages\PkgGUID\VerGUID</code></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6aa5a-259">用户目录中的文件</span><span class="sxs-lookup"><span data-stu-id="6aa5a-259">Files in the user catalog</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="6aa5a-260">UserManifest.xml</span><span class="sxs-lookup"><span data-stu-id="6aa5a-260">UserManifest.xml</span></span></p></li>
<li><p><span data-ttu-id="6aa5a-261">DynamicConfiguration.xml 或 UserDeploymentConfiguration.xml</span><span class="sxs-lookup"><span data-stu-id="6aa5a-261">DynamicConfiguration.xml or UserDeploymentConfiguration.xml</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6aa5a-262">其他用户目录位置，在程序包是连接组的一部分时使用</span><span class="sxs-lookup"><span data-stu-id="6aa5a-262">Additional user catalog location, used when the package is part of a connection group</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-263">以下位置是除上述特定程序包位置之外的其他位置：</span><span class="sxs-lookup"><span data-stu-id="6aa5a-263">The following location is in addition to the specific package location mentioned above:</span></span></p>
<p><code>appdata\roaming\Microsoft\AppV\Client\Catalog\PackageGroups\PkgGroupGUID\PkgGroupVerGUID</code></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6aa5a-264">当程序包是连接组的一部分时计算机目录中的其他文件</span><span class="sxs-lookup"><span data-stu-id="6aa5a-264">Additional file in the machine catalog when the package is part of a connection group</span></span></p></td>
<td align="left"><p><code>UserPackageGroupDescriptor.xml</code></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="6aa5a-265">快捷方式备份</span><span class="sxs-lookup"><span data-stu-id="6aa5a-265">Shortcut backups</span></span>

<span data-ttu-id="6aa5a-266">在发布过程中，App-v 客户端将备份任何快捷方式和集成点到 `%AppData%\Microsoft\AppV\Client\Integration\ShortCutBackups.` 此备份后，在取消发布程序包时，可将这些集成点还原到以前的版本。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-266">During the publishing process, the App-V Client backs up any shortcuts and integration points to `%AppData%\Microsoft\AppV\Client\Integration\ShortCutBackups.` This backup enables the restoration of these integration points to the previous versions when the package is unpublished.</span></span>

### <span data-ttu-id="6aa5a-267">写入文件时复制</span><span class="sxs-lookup"><span data-stu-id="6aa5a-267">Copy on Write files</span></span>

<span data-ttu-id="6aa5a-268">程序包存储包含已从发布服务器流出的程序包文件的 pristine 副本。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-268">The Package Store contains a pristine copy of the package files that have been streamed from the publishing server.</span></span> <span data-ttu-id="6aa5a-269">在应用 V 应用程序的正常运行期间，用户或服务可能需要对文件进行更改。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-269">During normal operation of an App-V application, the user or service may require changes to the files.</span></span> <span data-ttu-id="6aa5a-270">这些更改不会在程序包存储中进行，以便保留你修复应用程序的能力，从而删除这些更改。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-270">These changes are not made in the package store in order to preserve your ability to repair the application, which removes these changes.</span></span> <span data-ttu-id="6aa5a-271">这些位置称为 "写入时复制（牛）"，支持漫游和非漫游位置。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-271">These locations, called Copy on Write (COW), support both roaming and non-roaming locations.</span></span> <span data-ttu-id="6aa5a-272">存储修改的位置取决于应用程序在本机体验中写入更改的编程位置。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-272">The location where the modifications are stored depends where the application has been programmed to write changes to in a native experience.</span></span>

### <span data-ttu-id="6aa5a-273">牛漫游</span><span class="sxs-lookup"><span data-stu-id="6aa5a-273">COW roaming</span></span>

<span data-ttu-id="6aa5a-274">上面所述的牛漫游位置存储指向典型% AppData% location 或 \\Users\\{username}\\AppData\\Roaming 位置的文件和目录的更改。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-274">The COW Roaming location described above stores changes to files and directories that are targeted to the typical %AppData% location or \\Users\\{username}\\AppData\\Roaming location.</span></span> <span data-ttu-id="6aa5a-275">然后，这些目录和文件将基于操作系统设置进行漫游。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-275">These directories and files are then roamed based on the operating system settings.</span></span>

### <span data-ttu-id="6aa5a-276">牛局部</span><span class="sxs-lookup"><span data-stu-id="6aa5a-276">COW local</span></span>

<span data-ttu-id="6aa5a-277">牛本地位置类似于漫游位置，但目录和文件不会漫游到其他计算机，即使已配置漫游支持也是如此。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-277">The COW Local location is similar to the roaming location, but the directories and files are not roamed to other computers, even if roaming support has been configured.</span></span> <span data-ttu-id="6aa5a-278">以上所述的牛本地位置存储适用于典型窗口的更改，而不是% AppData% location。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-278">The COW Local location described above stores changes applicable to typical windows and not the %AppData% location.</span></span> <span data-ttu-id="6aa5a-279">列出的目录将有所不同，但任何典型的 Windows 位置（例如，通用 AppData 和常见 AppDataS）都有两个位置。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-279">The directories listed will vary but there will be two locations for any typical Windows locations (e.g. Common AppData and Common AppDataS).</span></span> <span data-ttu-id="6aa5a-280">当虚拟服务请求从已登录用户的其他提升的用户请求更改时， **S**表示受限制的位置。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-280">The **S** signifies the restricted location when the virtual service requests the change as a different elevated user from the logged on users.</span></span> <span data-ttu-id="6aa5a-281">非**S**位置存储基于用户的更改。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-281">The non-**S** location stores user based changes.</span></span>

## <a href="" id="bkmk-pkg-registry"></a><span data-ttu-id="6aa5a-282">程序包注册表</span><span class="sxs-lookup"><span data-stu-id="6aa5a-282">Package registry</span></span>


<span data-ttu-id="6aa5a-283">在应用程序可以访问程序包注册表数据之前，app-v 客户端必须使程序包注册表数据可用于应用程序。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-283">Before an application can access the package registry data, the App-V Client must make the package registry data available to the applications.</span></span> <span data-ttu-id="6aa5a-284">App-v 客户端将实际注册表用作所有注册表数据的后备应用商店。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-284">The App-V Client uses the real registry as a backing store for all registry data.</span></span>

<span data-ttu-id="6aa5a-285">将新程序包添加到 App-v 客户端时，注册表的副本。已在创建来自程序包的 DAT 文件 `%ProgramData%\Microsoft\AppV\Client\VREG\{Version GUID}.dat` 。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-285">When a new package is added to the App-V Client, a copy of the REGISTRY.DAT file from the package is created at `%ProgramData%\Microsoft\AppV\Client\VREG\{Version GUID}.dat`.</span></span> <span data-ttu-id="6aa5a-286">文件的名称是带有的版本 GUID。DAT 扩展。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-286">The name of the file is the version GUID with the .DAT extension.</span></span> <span data-ttu-id="6aa5a-287">创建此副本的原因是确保程序包中的实际配置单元文件永远不会被使用，这将阻止稍后删除程序包。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-287">The reason this copy is made is to ensure that the actual hive file in the package is never in use, which would prevent the removal of the package at a later time.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="6aa5a-288">软件包存储中的注册表 dat</span><span class="sxs-lookup"><span data-stu-id="6aa5a-288">Registry.dat from Package Store</span></span></strong></p></td>
<td align="left"><p><strong> &gt; </strong></p></td>
<td align="left"><p><strong><span data-ttu-id="6aa5a-289">%ProgramData%\Microsoft\AppV\Client\Vreg {VersionGuid} .dat</span><span class="sxs-lookup"><span data-stu-id="6aa5a-289">%ProgramData%\Microsoft\AppV\Client\Vreg{VersionGuid}.dat</span></span></strong></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="6aa5a-290">当程序包中的第一个应用程序在客户端上启动时，客户端阶段或将内容复制到蜂巢文件中，在备用位置重新创建程序包注册表数据 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\AppV\Client\Packages\PackageGuid\Versions\VersionGuid\REGISTRY` 。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-290">When the first application from the package is launched on the client, the client stages or copies the contents out of the hive file, re-creating the package registry data in an alternate location `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\AppV\Client\Packages\PackageGuid\Versions\VersionGuid\REGISTRY`.</span></span> <span data-ttu-id="6aa5a-291">暂存的注册表数据具有两种不同类型的计算机数据和用户数据。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-291">The staged registry data has two distinct types of machine data and user data.</span></span> <span data-ttu-id="6aa5a-292">在计算机上的所有用户之间共享计算机数据。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-292">Machine data is shared across all users on the machine.</span></span> <span data-ttu-id="6aa5a-293">将每个用户的用户数据暂存到 userspecific 位置 `HKCU\Software\Microsoft\AppV\Client\Packages\PackageGuid\Registry\User` 。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-293">User data is staged for each user to a userspecific location `HKCU\Software\Microsoft\AppV\Client\Packages\PackageGuid\Registry\User`.</span></span> <span data-ttu-id="6aa5a-294">在软件包删除时，计算机数据最终会被删除，并且用户数据会在用户取消发布操作中被删除。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-294">The machine data is ultimately removed at package removal time, and the user data is removed on a user unpublish operation.</span></span>

### <span data-ttu-id="6aa5a-295">程序包注册表暂存和连接组注册表暂存</span><span class="sxs-lookup"><span data-stu-id="6aa5a-295">Package registry staging vs. connection group registry staging</span></span>

<span data-ttu-id="6aa5a-296">当连接组存在时，暂存注册表的以前过程保留为 true，但不需要处理一个配置单元文件。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-296">When connection groups are present, the previous process of staging the registry holds true, but instead of having one hive file to process, there are more than one.</span></span> <span data-ttu-id="6aa5a-297">文件将按照它们在连接组 XML 中的显示顺序进行处理，第一个编写器赢得任何冲突。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-297">The files are processed in the order in which they appear in the connection group XML, with the first writer winning any conflicts.</span></span>

<span data-ttu-id="6aa5a-298">暂存的注册表与单个程序包事例中的保留方式相同。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-298">The staged registry persists the same way as in the single package case.</span></span> <span data-ttu-id="6aa5a-299">暂存用户注册表数据将保留在连接组中，直到被禁用;在删除连接组时，将删除暂存计算机注册表数据。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-299">Staged user registry data remains for the connection group until it is disabled; staged machine registry data is removed on connection group removal.</span></span>

### <span data-ttu-id="6aa5a-300">虚拟注册表</span><span class="sxs-lookup"><span data-stu-id="6aa5a-300">Virtual registry</span></span>

<span data-ttu-id="6aa5a-301">虚拟注册表（VREG）的用途是为应用程序提供程序包注册表和本机注册表的单个合并视图。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-301">The purpose of the virtual registry (VREG) is to provide a single merged view of the package registry and the native registry to applications.</span></span> <span data-ttu-id="6aa5a-302">它还提供 "写入时复制（牛）" 功能，即从虚拟进程上下文到一个单独的牛位置对注册表所做的任何更改。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-302">It also provides copy-on-write (COW) functionality – that is any changes made to the registry from the context of a virtual process are made to a separate COW location.</span></span> <span data-ttu-id="6aa5a-303">这意味着 VREG 必须将最多三个不同的注册表位置合并到一个视图中，具体取决于注册表牛-程序包中的填充位置 &gt; &gt; 。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-303">This means that the VREG must combine up to three separate registry locations into a single view based on the populated locations in the registry COW -&gt; package -&gt; native.</span></span> <span data-ttu-id="6aa5a-304">当对注册表数据发出请求时，它将按顺序找到它，直到找到它所请求的数据。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-304">When a request is made for a registry data it will locate in order until it finds the data it was requesting.</span></span> <span data-ttu-id="6aa5a-305">含义如果在牛位置存储的值不会继续到其他位置，但如果在牛位置没有数据，它将继续到包，然后是本机位置，直到找到相应的数据。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-305">Meaning if there is a value stored in a COW location it will not proceed to other locations, however, if there is no data in the COW location it will proceed to the Package and then Native location until it finds the appropriate data.</span></span>

### <span data-ttu-id="6aa5a-306">注册表位置</span><span class="sxs-lookup"><span data-stu-id="6aa5a-306">Registry locations</span></span>

<span data-ttu-id="6aa5a-307">应用程序-V 客户端存储注册表信息的两个程序包注册表位置和两个连接组位置，具体取决于程序包是单独发布还是作为连接组的一部分发布。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-307">There are two package registry locations and two connection group locations where the App-V Client stores registry information, depending on whether the Package is published individually or as part of a connection group.</span></span> <span data-ttu-id="6aa5a-308">对于程序包，有三个牛位置，而对于连接组，则由 VREG 创建和管理三个。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-308">There are three COW locations for packages and three for connection groups, which are created and managed by the VREG.</span></span> <span data-ttu-id="6aa5a-309">程序包和连接组的设置不共享：</span><span class="sxs-lookup"><span data-stu-id="6aa5a-309">Settings for packages and connection groups are not shared:</span></span>

**<span data-ttu-id="6aa5a-310">单个程序包 VReg：</span><span class="sxs-lookup"><span data-stu-id="6aa5a-310">Single Package VReg:</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="6aa5a-311">位置</span><span class="sxs-lookup"><span data-stu-id="6aa5a-311">Location</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="6aa5a-312">描述</span><span class="sxs-lookup"><span data-stu-id="6aa5a-312">Description</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="6aa5a-313">牛</span><span class="sxs-lookup"><span data-stu-id="6aa5a-313">COW</span></span></strong></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="6aa5a-314">计算机 Registry\Client\Packages\PkgGUID\REGISTRY （仅提升进程可以写入）</span><span class="sxs-lookup"><span data-stu-id="6aa5a-314">Machine Registry\Client\Packages\PkgGUID\REGISTRY (Only elevate process can write)</span></span></p></li>
<li><p><span data-ttu-id="6aa5a-315">用户 Registry\Client\Packages\PkgGUID\REGISTRY （除 Software\Classes 外，在 HKCU 下写入的任何内容</span><span class="sxs-lookup"><span data-stu-id="6aa5a-315">User Registry\Client\Packages\PkgGUID\REGISTRY (User Roaming anything written under HKCU except Software\Classes</span></span></p></li>
<li><p><span data-ttu-id="6aa5a-316">用户注册表 Classes\Client\Packages\PkgGUID\REGISTRY （HKCU\Software\Classes 为非提升的进程编写和 HKLM）</span><span class="sxs-lookup"><span data-stu-id="6aa5a-316">User Registry Classes\Client\Packages\PkgGUID\REGISTRY (HKCU\Software\Classes writes and HKLM for non elevated process)</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="6aa5a-317">包</span><span class="sxs-lookup"><span data-stu-id="6aa5a-317">Package</span></span></strong></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="6aa5a-318">机器 Registry\Client\Packages\PkgGUID\Versions\VerGuid\Registry\Machine</span><span class="sxs-lookup"><span data-stu-id="6aa5a-318">Machine Registry\Client\Packages\PkgGUID\Versions\VerGuid\Registry\Machine</span></span></p></li>
<li><p><span data-ttu-id="6aa5a-319">用户注册表 Classes\Client\Packages\PkgGUID\Versions\VerGUID\Registry</span><span class="sxs-lookup"><span data-stu-id="6aa5a-319">User Registry Classes\Client\Packages\PkgGUID\Versions\VerGUID\Registry</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="6aa5a-320">自己</span><span class="sxs-lookup"><span data-stu-id="6aa5a-320">Native</span></span></strong></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="6aa5a-321">本机应用程序注册表位置</span><span class="sxs-lookup"><span data-stu-id="6aa5a-321">Native application registry location</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

 

**<span data-ttu-id="6aa5a-322">连接组 VReg：</span><span class="sxs-lookup"><span data-stu-id="6aa5a-322">Connection Group VReg:</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="6aa5a-323">位置</span><span class="sxs-lookup"><span data-stu-id="6aa5a-323">Location</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="6aa5a-324">描述</span><span class="sxs-lookup"><span data-stu-id="6aa5a-324">Description</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="6aa5a-325">牛</span><span class="sxs-lookup"><span data-stu-id="6aa5a-325">COW</span></span></strong></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="6aa5a-326">计算机 Registry\Client\PackageGroups\GrpGUID\REGISTRY （仅提升进程可以写入）</span><span class="sxs-lookup"><span data-stu-id="6aa5a-326">Machine Registry\Client\PackageGroups\GrpGUID\REGISTRY (only elevate process can write)</span></span></p></li>
<li><p><span data-ttu-id="6aa5a-327">用户 Registry\Client\PackageGroups\GrpGUID\REGISTRY （除 Software\Classes 之外的任何内容写入 HKCU</span><span class="sxs-lookup"><span data-stu-id="6aa5a-327">User Registry\Client\PackageGroups\GrpGUID\REGISTRY (Anything written to HKCU except Software\Classes</span></span></p></li>
<li><p><span data-ttu-id="6aa5a-328">用户注册表 Classes\Client\PackageGroups\GrpGUID\REGISTRY</span><span class="sxs-lookup"><span data-stu-id="6aa5a-328">User Registry Classes\Client\PackageGroups\GrpGUID\REGISTRY</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="6aa5a-329">包</span><span class="sxs-lookup"><span data-stu-id="6aa5a-329">Package</span></span></strong></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="6aa5a-330">机器 Registry\Client\PackageGroups\GrpGUID\Versions\VerGUID\REGISTRY</span><span class="sxs-lookup"><span data-stu-id="6aa5a-330">Machine Registry\Client\PackageGroups\GrpGUID\Versions\VerGUID\REGISTRY</span></span></p></li>
<li><p><span data-ttu-id="6aa5a-331">用户注册表 Classes\Client\PackageGroups\GrpGUID\Versions\VerGUID\REGISTRY</span><span class="sxs-lookup"><span data-stu-id="6aa5a-331">User Registry Classes\Client\PackageGroups\GrpGUID\Versions\VerGUID\REGISTRY</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="6aa5a-332">自己</span><span class="sxs-lookup"><span data-stu-id="6aa5a-332">Native</span></span></strong></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="6aa5a-333">本机应用程序注册表位置</span><span class="sxs-lookup"><span data-stu-id="6aa5a-333">Native application registry location</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

 

<span data-ttu-id="6aa5a-334">可用于 HKLM 的两个牛位置;提升和未提升的流程。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-334">There are two COW locations for HKLM; elevated and non-elevated processes.</span></span> <span data-ttu-id="6aa5a-335">提升的流程始终会将 HKLM 更改写入 HKLM 下的安全牛中。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-335">Elevated processes always write HKLM changes to the secure COW under HKLM.</span></span> <span data-ttu-id="6aa5a-336">非提升的进程始终会将 HKLM 更改写入到 HKCU\\Software\\Classes. 下的非安全牛中。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-336">Non-elevated processes always write HKLM changes to the non-secure COW under HKCU\\Software\\Classes.</span></span> <span data-ttu-id="6aa5a-337">当应用程序读取来自 HKLM 的更改时，提升的进程将从 HKLM 下的安全牛中读取更改。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-337">When an application reads changes from HKLM, elevated processes will read changes from the secure COW under HKLM.</span></span> <span data-ttu-id="6aa5a-338">非提升的读取，favoring 在不安全的牛中首先进行的更改。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-338">Non-elevated reads from both, favoring the changes made in the unsecure COW first.</span></span>

### <span data-ttu-id="6aa5a-339">传递按键</span><span class="sxs-lookup"><span data-stu-id="6aa5a-339">Pass-through keys</span></span>

<span data-ttu-id="6aa5a-340">传递密钥使管理员可以配置某些键，以便只能从本机注册表中读取程序包和牛位置。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-340">Pass-through keys enable an administrator to configure certain keys so they can only be read from the native registry, bypassing the Package and COW locations.</span></span> <span data-ttu-id="6aa5a-341">传递位置对计算机全局（而非特定于程序包），并且可以通过添加密钥的路径进行配置，该路径应视为传递到**PassThroughPaths**键的**注册 _MULTI \ _SZ**值 `HKLM\Software\Microsoft\AppV\Subsystem\VirtualRegistry` 。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-341">Pass-through locations are global to the machine (not package specific) and can be configured by adding the path to the key, which should be treated as pass-through to the **REG\_MULTI\_SZ** value called **PassThroughPaths** of the key `HKLM\Software\Microsoft\AppV\Subsystem\VirtualRegistry`.</span></span> <span data-ttu-id="6aa5a-342">出现在此多字符串值下的任何键（及其子元素）都将被视为传递。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-342">Any key that appears under this multi-string value (and their children) will be treated as pass-through.</span></span>

<span data-ttu-id="6aa5a-343">默认情况下，以下位置配置为传递位置：</span><span class="sxs-lookup"><span data-stu-id="6aa5a-343">The following locations are configured as pass-through locations by default:</span></span>

-   <span data-ttu-id="6aa5a-344">HKEY \ _CURRENT \ _USER \\SOFTWARE\\Classes\\Local Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\AppModel</span><span class="sxs-lookup"><span data-stu-id="6aa5a-344">HKEY\_CURRENT\_USER\\SOFTWARE\\Classes\\Local Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\AppModel</span></span>

-   <span data-ttu-id="6aa5a-345">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Classes\\Local Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\AppModel</span><span class="sxs-lookup"><span data-stu-id="6aa5a-345">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Classes\\Local Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\AppModel</span></span>

-   <span data-ttu-id="6aa5a-346">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WINEVT</span><span class="sxs-lookup"><span data-stu-id="6aa5a-346">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WINEVT</span></span>

-   <span data-ttu-id="6aa5a-347">HKEY \ _LOCAL \ _MACHINE \\SYSTEM\\CurrentControlSet\\services\\eventlog\\Application</span><span class="sxs-lookup"><span data-stu-id="6aa5a-347">HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\services\\eventlog\\Application</span></span>

-   <span data-ttu-id="6aa5a-348">HKEY \ _LOCAL \ _MACHINE \\SYSTEM\\CurrentControlSet\\Control\\WMI\\Autologger</span><span class="sxs-lookup"><span data-stu-id="6aa5a-348">HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Control\\WMI\\Autologger</span></span>

-   <span data-ttu-id="6aa5a-349">HKEY \ _CURRENT \ _USER \\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet 设置</span><span class="sxs-lookup"><span data-stu-id="6aa5a-349">HKEY\_CURRENT\_USER\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings</span></span>

-   <span data-ttu-id="6aa5a-350">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Perflib</span><span class="sxs-lookup"><span data-stu-id="6aa5a-350">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Perflib</span></span>

-   <span data-ttu-id="6aa5a-351">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Policies</span><span class="sxs-lookup"><span data-stu-id="6aa5a-351">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Policies</span></span>

-   <span data-ttu-id="6aa5a-352">HKEY \ _CURRENT \ _USER \\SOFTWARE\\Policies</span><span class="sxs-lookup"><span data-stu-id="6aa5a-352">HKEY\_CURRENT\_USER\\SOFTWARE\\Policies</span></span>

<span data-ttu-id="6aa5a-353">传递密钥的目的在于确保虚拟应用程序不会在非虚拟应用程序所需的 VReg 中写入注册表数据，以便成功操作或集成。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-353">The purpose of Pass-through keys is to ensure that a virtual application does not write registry data in the VReg that is required for non-virtual applications for successful operation or integration.</span></span> <span data-ttu-id="6aa5a-354">策略键确保管理员设置的基于组策略的设置已使用，而不是每个程序包设置。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-354">The Policies key ensures that Group Policy based settings set by the administrator are utilized and not per package settings.</span></span> <span data-ttu-id="6aa5a-355">要与基于 Windows 新式 UI 的应用程序集成，需要 AppModel 参数。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-355">The AppModel key is required for integration with Windows Modern UI based applications.</span></span> <span data-ttu-id="6aa5a-356">建议管理不要修改任何默认传递密钥，但在某些情况下，根据应用程序行为可能需要添加其他传递密钥。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-356">It is recommend that administers do not modify any of the default pass-through keys, but in some instances, based on application behavior may require adding additional pass-through keys.</span></span>

## <a href="" id="bkmk-pkg-store-behavior"></a><span data-ttu-id="6aa5a-357">App-v 包存储行为</span><span class="sxs-lookup"><span data-stu-id="6aa5a-357">App-V package store behavior</span></span>


<span data-ttu-id="6aa5a-358">App-v 5 管理程序包存储，它是存储 appv 文件中展开的资源文件的位置。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-358">App-V 5 manages the Package Store, which is the location where the expanded asset files from the appv file are stored.</span></span> <span data-ttu-id="6aa5a-359">默认情况下，此位置存储在%ProgramData%\\App-V 上，并且仅受可用磁盘空间限制的存储功能。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-359">By default, this location is stored at %ProgramData%\\App-V, and is limited in terms of storage capabilities only by free disk space.</span></span> <span data-ttu-id="6aa5a-360">程序包存储由程序包和版本的 Guid 组织，如上一节中所述。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-360">The package store is organized by the GUIDs for the package and version as mentioned in the previous section.</span></span>

### <span data-ttu-id="6aa5a-361">添加程序包</span><span class="sxs-lookup"><span data-stu-id="6aa5a-361">Add packages</span></span>

<span data-ttu-id="6aa5a-362">在具有 App-v 客户端的计算机上添加 app-v 包时进行暂存。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-362">App-V Packages are staged upon addition to the computer with the App-V Client.</span></span> <span data-ttu-id="6aa5a-363">App-v 客户端提供按需暂存。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-363">The App-V Client provides on-demand staging.</span></span> <span data-ttu-id="6aa5a-364">在发布或手动加载 AppVClientPackage 期间，数据结构在程序包存储（c:\\programdata\\App-V\\{PkgGUID}\\{VerGUID}）中生成。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-364">During publishing or a manual Add-AppVClientPackage, the data structure is built in the package store (c:\\programdata\\App-V\\{PkgGUID}\\{VerGUID}).</span></span> <span data-ttu-id="6aa5a-365">在 StreamMap.xml 中定义的发布块中标识的程序包文件将添加到系统以及暂存的顶级文件夹和子文件，以确保在启动时有适当的应用程序资源。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-365">The package files identified in the publishing block defined in the StreamMap.xml are added to the system and the top level folders and child files staged to ensure proper application assets exist at launch.</span></span>

### <span data-ttu-id="6aa5a-366">安装程序包</span><span class="sxs-lookup"><span data-stu-id="6aa5a-366">Mounting packages</span></span>

<span data-ttu-id="6aa5a-367">可以使用 PowerShell `Mount-AppVClientPackage` 或通过使用**APP-V Client UI**下载程序包来显式加载程序包。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-367">Packages can be explicitly loaded using the PowerShell `Mount-AppVClientPackage` or by using the **App-V Client UI** to download a package.</span></span> <span data-ttu-id="6aa5a-368">此操作会将整个程序包完全加载到包存储中。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-368">This operation completely loads the entire package into the package store.</span></span>

### <span data-ttu-id="6aa5a-369">流式处理程序包</span><span class="sxs-lookup"><span data-stu-id="6aa5a-369">Streaming packages</span></span>

<span data-ttu-id="6aa5a-370">App-v 客户端可以配置为更改流式处理的默认行为。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-370">The App-V Client can be configured to change the default behavior of streaming.</span></span> <span data-ttu-id="6aa5a-371">所有流策略都存储在以下注册表项下： `HKEY_LOCAL_MAcHINE\Software\Microsoft\AppV\Client\Streaming` 。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-371">All streaming policies are stored under the following registry key: `HKEY_LOCAL_MAcHINE\Software\Microsoft\AppV\Client\Streaming`.</span></span> <span data-ttu-id="6aa5a-372">使用 PowerShell cmdlet 设置策略 `Set-AppvClientConfiguration` 。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-372">Policies are set using the PowerShell cmdlet `Set-AppvClientConfiguration`.</span></span> <span data-ttu-id="6aa5a-373">以下政策适用于流式处理：</span><span class="sxs-lookup"><span data-stu-id="6aa5a-373">The following policies apply to Streaming:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6aa5a-374">策略</span><span class="sxs-lookup"><span data-stu-id="6aa5a-374">Policy</span></span></th>
<th align="left"><span data-ttu-id="6aa5a-375">描述</span><span class="sxs-lookup"><span data-stu-id="6aa5a-375">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6aa5a-376">AllowHighCostLaunch</span><span class="sxs-lookup"><span data-stu-id="6aa5a-376">AllowHighCostLaunch</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-377">在 Windows 8 中，它允许通过3G 和手机网络进行流处理</span><span class="sxs-lookup"><span data-stu-id="6aa5a-377">On Windows 8 it allows streaming over 3G and cellular networks</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6aa5a-378">AutoLoad</span><span class="sxs-lookup"><span data-stu-id="6aa5a-378">AutoLoad</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-379">指定后台加载设置：</span><span class="sxs-lookup"><span data-stu-id="6aa5a-379">Specifies the Background Load setting:</span></span></p>
<p><strong><span data-ttu-id="6aa5a-380">0 </strong> - 已禁用</span><span class="sxs-lookup"><span data-stu-id="6aa5a-380">0</strong> - Disabled</span></span></p>
<p><strong><span data-ttu-id="6aa5a-381">1 </strong> -仅限以前使用的程序包</span><span class="sxs-lookup"><span data-stu-id="6aa5a-381">1</strong> – Previously Used Packages only</span></span></p>
<p><strong><span data-ttu-id="6aa5a-382">2 </strong> -所有程序包</span><span class="sxs-lookup"><span data-stu-id="6aa5a-382">2</strong> – All Packages</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6aa5a-383">PackageInstallationRoot</span><span class="sxs-lookup"><span data-stu-id="6aa5a-383">PackageInstallationRoot</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-384">本地计算机中程序包存储的根文件夹</span><span class="sxs-lookup"><span data-stu-id="6aa5a-384">The root folder for the package store in the local machine</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6aa5a-385">PackageSourceRoot</span><span class="sxs-lookup"><span data-stu-id="6aa5a-385">PackageSourceRoot</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-386">应从其流入包的根替代</span><span class="sxs-lookup"><span data-stu-id="6aa5a-386">The root override where packages should be streamed from</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6aa5a-387">SharedContentStoreMode</span><span class="sxs-lookup"><span data-stu-id="6aa5a-387">SharedContentStoreMode</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-388">支持使用 VDI 方案的共享内容存储</span><span class="sxs-lookup"><span data-stu-id="6aa5a-388">Enables the use of Shared Content Store for VDI scenarios</span></span></p></td>
</tr>
</tbody>
</table>

 

 

<span data-ttu-id="6aa5a-389">这些设置会影响将 app-v 包资源流式处理到客户端的行为。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-389">These settings affect the behavior of streaming App-V package assets to the client.</span></span> <span data-ttu-id="6aa5a-390">默认情况下，app-v 仅下载下载初始发布和主要功能块后所需的资源。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-390">By default, App-V only downloads the assets required after downloading the initial publishing and primary feature blocks.</span></span> <span data-ttu-id="6aa5a-391">对于必须解释的流式处理程序包，有三个特定行为：</span><span class="sxs-lookup"><span data-stu-id="6aa5a-391">There are three specific behaviors around streaming packages that must be explained:</span></span>

-   <span data-ttu-id="6aa5a-392">后台流</span><span class="sxs-lookup"><span data-stu-id="6aa5a-392">Background Streaming</span></span>

-   <span data-ttu-id="6aa5a-393">优化流</span><span class="sxs-lookup"><span data-stu-id="6aa5a-393">Optimized Streaming</span></span>

-   <span data-ttu-id="6aa5a-394">流故障</span><span class="sxs-lookup"><span data-stu-id="6aa5a-394">Stream Faults</span></span>

### <span data-ttu-id="6aa5a-395">后台流</span><span class="sxs-lookup"><span data-stu-id="6aa5a-395">Background streaming</span></span>

<span data-ttu-id="6aa5a-396">PowerShell cmdlet `Get-AppvClientConfiguration` 可用于确定后台流的当前模式和 AutoLoad 设置，并使用 Cmdlet Set-AppvClientConfiguration 或注册表（HKLM\\SOFTWARE\\Microsoft\\AppV\\ClientStreaming 键）进行修改。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-396">The PowerShell cmdlet `Get-AppvClientConfiguration` can be used to determine the current mode for background streaming with the AutoLoad setting and modified with the cmdlet Set-AppvClientConfiguration or from the registry (HKLM\\SOFTWARE\\Microsoft\\AppV\\ClientStreaming key).</span></span> <span data-ttu-id="6aa5a-397">后台流是默认设置，其中 Autoload 设置将设置为下载以前使用的程序包。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-397">Background streaming is a default setting where the Autoload setting is set to download previously used packages.</span></span> <span data-ttu-id="6aa5a-398">基于默认设置（值 = 1）的行为在应用程序启动后，在后台下载 app-v 数据块。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-398">The behavior based on default setting (value=1) downloads App-V data blocks in the background after the application has been launched.</span></span> <span data-ttu-id="6aa5a-399">无论是否已启动所有程序包（值 = 2），此设置均可同时禁用（值 = 0）或启用。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-399">This setting can be disabled all together (value=0) or enabled for all packages (value=2), whether they have been launched.</span></span>

### <span data-ttu-id="6aa5a-400">优化流</span><span class="sxs-lookup"><span data-stu-id="6aa5a-400">Optimized streaming</span></span>

<span data-ttu-id="6aa5a-401">在排序期间，可以使用主要功能块配置 app-v 程序包。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-401">App-V packages can be configured with a primary feature block during sequencing.</span></span> <span data-ttu-id="6aa5a-402">此设置允许排序工程师监视特定应用程序或应用程序的启动文件，并在程序包中的任何应用程序首次启动时将 App-v 包中的数据块标记为流式处理。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-402">This setting allows the sequencing engineer to monitor launch files for a specific application, or applications, and mark the blocks of data in the App-V package for streaming at first launch of any application in the package.</span></span>

### <span data-ttu-id="6aa5a-403">流故障</span><span class="sxs-lookup"><span data-stu-id="6aa5a-403">Stream faults</span></span>

<span data-ttu-id="6aa5a-404">在任何发布数据和主要功能块的初始流之后，对其他文件的请求将执行流错误。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-404">After the initial stream of any publishing data and the primary feature block, requests for additional files perform stream faults.</span></span> <span data-ttu-id="6aa5a-405">这些数据块根据需要下载到程序包存储。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-405">These blocks of data are downloaded to the package store on an as-needed basis.</span></span> <span data-ttu-id="6aa5a-406">这样，用户只需下载程序包的一个小部分，通常就足以启动该程序包并运行正常任务。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-406">This allows a user to download only a small part of the package, typically enough to launch the package and run normal tasks.</span></span> <span data-ttu-id="6aa5a-407">当用户启动需要当前不在程序包存储中的数据的操作时，将下载所有其他块。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-407">All other blocks are downloaded when a user initiates an operation that requires data not currently in the package store.</span></span>

<span data-ttu-id="6aa5a-408">有关 App-v 程序包流访问的详细信息： <https://go.microsoft.com/fwlink/?LinkId=392770> 。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-408">For more information on App-V Package streaming visit: <https://go.microsoft.com/fwlink/?LinkId=392770>.</span></span>

<span data-ttu-id="6aa5a-409">可在以下位置获取流优化的排序： <https://go.microsoft.com/fwlink/?LinkId=392771> 。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-409">Sequencing for streaming optimization is available at: <https://go.microsoft.com/fwlink/?LinkId=392771>.</span></span>

### <span data-ttu-id="6aa5a-410">程序包升级</span><span class="sxs-lookup"><span data-stu-id="6aa5a-410">Package upgrades</span></span>

<span data-ttu-id="6aa5a-411">App-v 程序包需要在应用程序的整个生命周期内更新。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-411">App-V Packages require updating throughout the lifecycle of the application.</span></span> <span data-ttu-id="6aa5a-412">App-v 程序包升级类似于程序包发布操作，因为每个版本都将在其自己的 PackageRoot 位置中创建： `%ProgramData%\App-V\{PkgGUID}\{newVerGUID}` 。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-412">App-V Package upgrades are similar to the package publish operation, as each version will be created in its own PackageRoot location: `%ProgramData%\App-V\{PkgGUID}\{newVerGUID}`.</span></span> <span data-ttu-id="6aa5a-413">通过创建来自同一程序包的其他版本的相同和流文件的硬链接来优化升级操作。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-413">The upgrade operation is optimized by creating hard links to identical- and streamed-files from other versions of the same package.</span></span>

### <span data-ttu-id="6aa5a-414">软件包删除</span><span class="sxs-lookup"><span data-stu-id="6aa5a-414">Package removal</span></span>

<span data-ttu-id="6aa5a-415">删除软件包时 App-v 客户端的行为取决于用于删除的方法。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-415">The behavior of the App-V Client when packages are removed depends on the method used for removal.</span></span> <span data-ttu-id="6aa5a-416">使用 app-v 完整基础结构取消发布应用程序时，将删除用户目录文件（适用于全局发布的应用程序的计算机目录），但保留软件包存储位置和牛位置。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-416">Using an App-V full infrastructure to unpublish the application, the user catalog files (machine catalog for globally published applications) are removed, but retains the package store location and COW locations.</span></span> <span data-ttu-id="6aa5a-417">当 PowerShell cmdlet `Remove-AppVClientPackge` 用于删除 App-v 包时，将清理程序包存储位置。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-417">When the PowerShell cmdlet `Remove-AppVClientPackge` is used to remove an App-V Package, the package store location is cleaned.</span></span> <span data-ttu-id="6aa5a-418">请记住，从管理服务器取消发布 app-v 程序包不会执行删除操作。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-418">Remember that unpublishing an App-V Package from the Management Server does not perform a Remove operation.</span></span> <span data-ttu-id="6aa5a-419">两个操作都不会删除软件包存储包文件。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-419">Neither operation will remove the Package Store package files.</span></span>

## <a href="" id="bkmk-roaming-reg-data"></a><span data-ttu-id="6aa5a-420">漫游注册表和数据</span><span class="sxs-lookup"><span data-stu-id="6aa5a-420">Roaming registry and data</span></span>


<span data-ttu-id="6aa5a-421">App-v 5 可以在漫游时提供近乎真实的体验，具体取决于所使用的应用程序的编写方式。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-421">App-V 5 is able to provide a near-native experience when roaming, depending on how the application being used is written.</span></span> <span data-ttu-id="6aa5a-422">默认情况下，在漫游位置中存储的 App-v 漫游 AppData，这取决于操作系统的漫游配置。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-422">By default, App-V roams AppData that is stored in the roaming location, based on the roaming configuration of the operating system.</span></span> <span data-ttu-id="6aa5a-423">存储基于文件的数据的其他位置不会从计算机漫游到计算机，因为它们位于非漫游位置。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-423">Other locations for storage of file-based data do not roam from computer to computer, since they are in locations that are not roamed.</span></span>

### <a href="" id="bkmk-clt-inter-roam-reqs"></a><span data-ttu-id="6aa5a-424">漫游要求和用户目录数据存储</span><span class="sxs-lookup"><span data-stu-id="6aa5a-424">Roaming requirements and user catalog data storage</span></span>

<span data-ttu-id="6aa5a-425">App-v 存储数据，它以下列形式表示用户目录的状态：</span><span class="sxs-lookup"><span data-stu-id="6aa5a-425">App-V stores data, which represents the state of the user’s catalog, in the form of:</span></span>

-   <span data-ttu-id="6aa5a-426">%Appdata%\\Microsoft\\AppV\\Client\\Catalog 下的文件</span><span class="sxs-lookup"><span data-stu-id="6aa5a-426">Files under %appdata%\\Microsoft\\AppV\\Client\\Catalog</span></span>

-   <span data-ttu-id="6aa5a-427">下的注册表设置</span><span class="sxs-lookup"><span data-stu-id="6aa5a-427">Registry settings under</span></span> `HKEY_CURRENT_USER\Software\Microsoft\AppV\Client\Packages`

<span data-ttu-id="6aa5a-428">这些文件和注册表设置共同表示用户的目录，因此两者都必须是漫游，或者都不是特定用户的漫游。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-428">Together, these files and registry settings represent the user’s catalog, so either both must be roamed, or neither must be roamed for a given user.</span></span> <span data-ttu-id="6aa5a-429">App-v 不支持漫游% AppData%，但不支持漫游用户的配置文件（注册表），反之亦然。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-429">App-V does not support roaming %AppData%, but not roaming the user’s profile (registry), or vice versa.</span></span>

<span data-ttu-id="6aa5a-430">**注意** **AppvClientPackage** cmdlet 不会修复程序包的发布状态，即用户的 app-v 状态 `HKEY_CURRENT_USER` 缺失或与% appdata% 中的数据不匹配。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-430">**Note** The **Repair-AppvClientPackage** cmdlet does not repair the publishing state of packages, where the user’s App-V state under `HKEY_CURRENT_USER` is missing or mismatched with the data in %appdata%.</span></span>

 

### <span data-ttu-id="6aa5a-431">基于注册表的数据</span><span class="sxs-lookup"><span data-stu-id="6aa5a-431">Registry-based data</span></span>

<span data-ttu-id="6aa5a-432">App-v 注册表漫游分为两种方案，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-432">App-V registry roaming falls into two scenarios, as shown in the following table.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6aa5a-433">情形</span><span class="sxs-lookup"><span data-stu-id="6aa5a-433">Scenario</span></span></th>
<th align="left"><span data-ttu-id="6aa5a-434">描述</span><span class="sxs-lookup"><span data-stu-id="6aa5a-434">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6aa5a-435">作为标准用户运行的应用程序</span><span class="sxs-lookup"><span data-stu-id="6aa5a-435">Applications that are run as standard users</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-436">当标准用户启动 App-v 应用程序时，应用 V 应用程序的 HKLM 和 HKCU 均存储在计算机上的 HKCU 配置单元中。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-436">When a standard user launches an App-V application, both HKLM and HKCU for App-V applications are stored in the HKCU hive on the machine.</span></span> <span data-ttu-id="6aa5a-437">这将显示为两个不同的路径：</span><span class="sxs-lookup"><span data-stu-id="6aa5a-437">This presents as two distinct paths:</span></span></p>
<ul>
<li><p><span data-ttu-id="6aa5a-438">HKLM\： HKCU\SOFTWARE\Classes\AppV\Client\Packages {PkgGUID} \ REGISTRY\MACHINE\SOFTWARE</span><span class="sxs-lookup"><span data-stu-id="6aa5a-438">HKLM: HKCU\SOFTWARE\Classes\AppV\Client\Packages{PkgGUID}\REGISTRY\MACHINE\SOFTWARE</span></span></p></li>
<li><p><span data-ttu-id="6aa5a-439">HKCU： HKCU\SOFTWARE\Microsoft\AppV\Client\Packages {PkgGUID} \ REGISTRY\USER {UserSID} \ 软件</span><span class="sxs-lookup"><span data-stu-id="6aa5a-439">HKCU: HKCU\SOFTWARE\Microsoft\AppV\Client\Packages{PkgGUID}\REGISTRY\USER{UserSID}\SOFTWARE</span></span></p></li>
</ul>
<p><span data-ttu-id="6aa5a-440">根据操作系统设置，可启用漫游位置。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-440">The locations are enabled for roaming based on the operating system settings.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6aa5a-441">通过提升运行的应用程序</span><span class="sxs-lookup"><span data-stu-id="6aa5a-441">Applications that are run with elevation</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-442">当使用提升启动应用程序时：</span><span class="sxs-lookup"><span data-stu-id="6aa5a-442">When an application is launched with elevation:</span></span></p>
<ul>
<li><p><span data-ttu-id="6aa5a-443">HKLM 数据存储在本地计算机上的 HKLM 配置单元中</span><span class="sxs-lookup"><span data-stu-id="6aa5a-443">HKLM data is stored in the HKLM hive on the local computer</span></span></p></li>
<li><p><span data-ttu-id="6aa5a-444">HKCU 数据存储在用户的注册表位置</span><span class="sxs-lookup"><span data-stu-id="6aa5a-444">HKCU data is stored in the User Registry location</span></span></p></li>
</ul>
<p><span data-ttu-id="6aa5a-445">在此方案中，这些设置不是通过正常操作系统漫游配置进行漫游，并且生成的注册表项和值存储在以下位置：</span><span class="sxs-lookup"><span data-stu-id="6aa5a-445">In this scenario, these settings are not roamed with normal operating system roaming configurations, and the resulting registry keys and values are stored in the following location:</span></span></p>
<ul>
<li><p><span data-ttu-id="6aa5a-446">HKLM\SOFTWARE\Microsoft\AppV\Client\Packages{PkgGUID}{UserSID}\REGISTRY\MACHINE\SOFTWARE</span><span class="sxs-lookup"><span data-stu-id="6aa5a-446">HKLM\SOFTWARE\Microsoft\AppV\Client\Packages{PkgGUID}{UserSID}\REGISTRY\MACHINE\SOFTWARE</span></span></p></li>
<li><p><span data-ttu-id="6aa5a-447">HKCU\SOFTWARE\Microsoft\AppV\Client\Packages {PkgGUID} \ Registry\User {UserSID} \ 软件</span><span class="sxs-lookup"><span data-stu-id="6aa5a-447">HKCU\SOFTWARE\Microsoft\AppV\Client\Packages{PkgGUID}\Registry\User{UserSID}\SOFTWARE</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="6aa5a-448">App-v 和文件夹重定向</span><span class="sxs-lookup"><span data-stu-id="6aa5a-448">App-V and folder redirection</span></span>

<span data-ttu-id="6aa5a-449">App-v 5.0 SP2 支持漫游 AppData 文件夹的文件夹重定向（% AppData%）。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-449">App-V 5.0SP2 supports folder redirection of the roaming AppData folder (%AppData%).</span></span> <span data-ttu-id="6aa5a-450">启动虚拟环境时，将用户的漫游 AppData 目录中的漫游 AppData 状态复制到本地缓存。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-450">When the virtual environment is started, the roaming AppData state from the user’s roaming AppData directory is copied to the local cache.</span></span> <span data-ttu-id="6aa5a-451">相反，当虚拟环境关闭时，与特定用户的漫游 AppData 相关联的本地缓存将被转移到该用户的漫游 AppData 目录的实际位置。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-451">Conversely, when the virtual environment is shut down, the local cache that is associated with a specific user’s roaming AppData is transferred to the actual location of that user’s roaming AppData directory.</span></span>

<span data-ttu-id="6aa5a-452">典型程序包在用户的后备存储中映射了多个位置，用于 AppData\\Local 和 AppData\\Roaming. 中的设置</span><span class="sxs-lookup"><span data-stu-id="6aa5a-452">A typical package has several locations mapped in the user’s backing store for settings in both AppData\\Local and AppData\\Roaming.</span></span> <span data-ttu-id="6aa5a-453">这些位置是在用户配置文件中为每个用户存储的写位置上的副本，用于存储对软件包 VFS 目录所做的更改，并保护默认程序包 VFS。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-453">These locations are the Copy on Write locations that are stored per user in the user’s profile, and that are used to store changes made to the package VFS directories and to protect the default package VFS.</span></span>

<span data-ttu-id="6aa5a-454">下表显示了未实现文件夹重定向时的本地和漫游位置。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-454">The following table shows local and roaming locations, when folder redirection has not been implemented.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6aa5a-455">程序包中的 VFS 目录</span><span class="sxs-lookup"><span data-stu-id="6aa5a-455">VFS directory in package</span></span></th>
<th align="left"><span data-ttu-id="6aa5a-456">备份存储的映射位置</span><span class="sxs-lookup"><span data-stu-id="6aa5a-456">Mapped location of backing store</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6aa5a-457">ProgramFilesX86</span><span class="sxs-lookup"><span data-stu-id="6aa5a-457">ProgramFilesX86</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-458">C:\users\jsmith\AppData &lt; 强劲的 &gt; 本地 </strong> \Microsoft\AppV\Client\VFS &amp;GUID &gt; \ProgramFilesX86</span><span class="sxs-lookup"><span data-stu-id="6aa5a-458">C:\users\jsmith\AppData&lt;strong&gt;Local</strong>\Microsoft\AppV\Client\VFS&amp;lt;GUID&gt;\ProgramFilesX86</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6aa5a-459">SystemX86</span><span class="sxs-lookup"><span data-stu-id="6aa5a-459">SystemX86</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-460">C:\users\jsmith\AppData &lt; 强劲的 &gt; 本地 </strong> \Microsoft\AppV\Client\VFS &amp;GUID &gt; \SystemX86</span><span class="sxs-lookup"><span data-stu-id="6aa5a-460">C:\users\jsmith\AppData&lt;strong&gt;Local</strong>\Microsoft\AppV\Client\VFS&amp;lt;GUID&gt;\SystemX86</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6aa5a-461">Windows</span><span class="sxs-lookup"><span data-stu-id="6aa5a-461">Windows</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-462">C:\users\jsmith\AppData &lt; 强劲的 &gt; 本地 </strong> \Microsoft\AppV\Client\VFS &amp;GUID &gt; \windows</span><span class="sxs-lookup"><span data-stu-id="6aa5a-462">C:\users\jsmith\AppData&lt;strong&gt;Local</strong>\Microsoft\AppV\Client\VFS&amp;lt;GUID&gt;\Windows</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6aa5a-463">appv_ROOT</span><span class="sxs-lookup"><span data-stu-id="6aa5a-463">appv_ROOT</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-464">C:\users\jsmith\AppData &lt; 强劲的 &gt; 本地 </strong> \Microsoft\AppV\Client\VFS &amp;GUID &gt; \ appv_ROOT</span><span class="sxs-lookup"><span data-stu-id="6aa5a-464">C:\users\jsmith\AppData&lt;strong&gt;Local</strong>\Microsoft\AppV\Client\VFS&amp;lt;GUID&gt;\appv_ROOT</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6aa5a-465">AppData</span><span class="sxs-lookup"><span data-stu-id="6aa5a-465">AppData</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-466">C:\users\jsmith\AppData &lt; 强劲的 &gt; 漫游 </strong> \Microsoft\AppV\Client\VFS &amp;GUID &gt; \AppData</span><span class="sxs-lookup"><span data-stu-id="6aa5a-466">C:\users\jsmith\AppData&lt;strong&gt;Roaming</strong>\Microsoft\AppV\Client\VFS&amp;lt;GUID&gt;\AppData</span></span></p></td>
</tr>
</tbody>
</table>

 

 

<span data-ttu-id="6aa5a-467">下表显示了在为% AppData% 实现文件夹重定向且位置已重定向（通常为网络位置）时，本地和漫游位置。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-467">The following table shows local and roaming locations, when folder redirection has been implemented for %AppData%, and the location has been redirected (typically to a network location).</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6aa5a-468">程序包中的 VFS 目录</span><span class="sxs-lookup"><span data-stu-id="6aa5a-468">VFS directory in package</span></span></th>
<th align="left"><span data-ttu-id="6aa5a-469">备份存储的映射位置</span><span class="sxs-lookup"><span data-stu-id="6aa5a-469">Mapped location of backing store</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6aa5a-470">ProgramFilesX86</span><span class="sxs-lookup"><span data-stu-id="6aa5a-470">ProgramFilesX86</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-471">C:\users\jsmith\AppData &lt; 强劲的 &gt; 本地 </strong> \Microsoft\AppV\Client\VFS &amp;GUID &gt; \ProgramFilesX86</span><span class="sxs-lookup"><span data-stu-id="6aa5a-471">C:\users\jsmith\AppData&lt;strong&gt;Local</strong>\Microsoft\AppV\Client\VFS&amp;lt;GUID&gt;\ProgramFilesX86</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6aa5a-472">SystemX86</span><span class="sxs-lookup"><span data-stu-id="6aa5a-472">SystemX86</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-473">C:\users\jsmith\AppData &lt; 强劲的 &gt; 本地 </strong> \Microsoft\AppV\Client\VFS &amp;GUID &gt; \SystemX86</span><span class="sxs-lookup"><span data-stu-id="6aa5a-473">C:\users\jsmith\AppData&lt;strong&gt;Local</strong>\Microsoft\AppV\Client\VFS&amp;lt;GUID&gt;\SystemX86</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6aa5a-474">Windows</span><span class="sxs-lookup"><span data-stu-id="6aa5a-474">Windows</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-475">C:\users\jsmith\AppData &lt; 强劲的 &gt; 本地 </strong> \Microsoft\AppV\Client\VFS &amp;GUID &gt; \windows</span><span class="sxs-lookup"><span data-stu-id="6aa5a-475">C:\users\jsmith\AppData&lt;strong&gt;Local</strong>\Microsoft\AppV\Client\VFS&amp;lt;GUID&gt;\Windows</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6aa5a-476">appv_ROOT</span><span class="sxs-lookup"><span data-stu-id="6aa5a-476">appv_ROOT</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-477">C:\users\jsmith\AppData &lt; 强劲的 &gt; 本地 </strong> \Microsoft\AppV\Client\VFS &amp;GUID &gt; \ appv_ROOT</span><span class="sxs-lookup"><span data-stu-id="6aa5a-477">C:\users\jsmith\AppData&lt;strong&gt;Local</strong>\Microsoft\AppV\Client\VFS&amp;lt;GUID&gt;\appv_ROOT</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6aa5a-478">AppData</span><span class="sxs-lookup"><span data-stu-id="6aa5a-478">AppData</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="6aa5a-479">\Fileserver </strong> \users\jsmith\roaming\Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \AppData</span><span class="sxs-lookup"><span data-stu-id="6aa5a-479">\Fileserver</strong>\users\jsmith\roaming\Microsoft\AppV\Client\VFS&amp;lt;GUID&gt;\AppData</span></span></p></td>
</tr>
</tbody>
</table>

 

 

<span data-ttu-id="6aa5a-480">当前应用-V 客户端 VFS 驱动程序无法写入到网络位置，因此 App-v 客户端在发布和虚拟环境启动时，检测到 "文件夹重定向" 和 "复制本地驱动器上的数据"。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-480">The current App-V Client VFS driver cannot write to network locations, so the App-V Client detects the presence of folder redirection and copies the data on the local drive during publishing and when the virtual environment starts.</span></span> <span data-ttu-id="6aa5a-481">用户关闭应用程序-v 应用程序并且 app-v 客户端关闭虚拟环境后，会将 VFS AppData 的本地存储复制回网络，从而允许漫游到其他计算机，其中将重复该过程。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-481">After the user closes the App-V application and the App-V Client closes the virtual environment, the local storage of the VFS AppData is copied back to the network, enabling roaming to additional machines, where the process will be repeated.</span></span> <span data-ttu-id="6aa5a-482">流程的详细步骤如下：</span><span class="sxs-lookup"><span data-stu-id="6aa5a-482">The detailed steps of the processes are:</span></span>

1.  <span data-ttu-id="6aa5a-483">在发布或虚拟环境启动期间，App-v 客户端将检测 AppData 目录的位置。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-483">During publishing or virtual environment startup, the App-V Client detects the location of the AppData directory.</span></span>

2.  <span data-ttu-id="6aa5a-484">如果漫游 AppData 路径为 "本地" 或 ".ino AppData\\Roaming 位置已映射"，则不会发生任何反应。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-484">If the roaming AppData path is local or ino AppData\\Roaming location is mapped, nothing happens.</span></span>

3.  <span data-ttu-id="6aa5a-485">如果漫游 AppData 路径不是本地路径，则 VFS AppData 目录将映射到本地 AppData 目录。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-485">If the roaming AppData path is not local, the VFS AppData directory is mapped to the local AppData directory.</span></span>

<span data-ttu-id="6aa5a-486">此过程解决了 App-v 客户端 VFS 驱动程序不支持的非本地% AppData% 的问题。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-486">This process solves the problem of a non-local %AppData% that is not supported by the App-V Client VFS driver.</span></span> <span data-ttu-id="6aa5a-487">但是，此新位置中存储的数据不会通过文件夹重定向进行漫游。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-487">However, the data stored in this new location is not roamed with folder redirection.</span></span> <span data-ttu-id="6aa5a-488">应用程序运行期间的所有更改都将发生在本地 AppData 位置，并且必须复制到重定向的位置。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-488">All changes during the running of the application happen to the local AppData location and must be copied to the redirected location.</span></span> <span data-ttu-id="6aa5a-489">此过程的详细步骤如下：</span><span class="sxs-lookup"><span data-stu-id="6aa5a-489">The detailed steps of this process are:</span></span>

1.  <span data-ttu-id="6aa5a-490">App-v 应用程序已关闭，从而关闭了虚拟环境。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-490">App-V application is shut down, which shuts down the virtual environment.</span></span>

2.  <span data-ttu-id="6aa5a-491">漫游 AppData 位置的本地缓存被压缩并存储在 ZIP 文件中。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-491">The local cache of the roaming AppData location is compressed and stored in a ZIP file.</span></span>

3.  <span data-ttu-id="6aa5a-492">ZIP 打包过程末尾的时间戳用于命名文件。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-492">A timestamp at the end of the ZIP packaging process is used to name the file.</span></span>

4.  <span data-ttu-id="6aa5a-493">时间戳将记录在注册表中： HKEY \ _CURRENT \ _USER \\Software\\Microsoft\\AppV\\Client\\Packages\\ &lt; GUID &gt; \\AppDataTime 作为最后一个已知 AppData 时间戳。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-493">The timestamp is recorded in the registry: HKEY\_CURRENT\_USER\\Software\\Microsoft\\AppV\\Client\\Packages\\&lt;GUID&gt;\\AppDataTime as the last known AppData timestamp.</span></span>

5.  <span data-ttu-id="6aa5a-494">将调用文件夹重定向过程来计算和启动上载到漫游 AppData 目录的 ZIP 文件。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-494">The folder redirection process is called to evaluate and initiate the ZIP file uploaded to the roaming AppData directory.</span></span>

<span data-ttu-id="6aa5a-495">当发布 V 应用程序或启动虚拟环境时，如果存在冲突，并且用于优化数据下载，则时间戳用于确定 "最后一个写入程序入选" 方案。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-495">The timestamp is used to determine a “last writer wins” scenario if there is a conflict and is used to optimize the download of the data when the App-V application is published or the virtual environment is started.</span></span> <span data-ttu-id="6aa5a-496">文件夹重定向将使支持策略覆盖的任何其他客户端提供数据，并启动将 AppData\\Roaming 数据存储到客户端上的本地 AppData 位置的过程。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-496">Folder redirection will make the data available from any other clients covered by the supporting policy and will initiate the process of storing the AppData\\Roaming data to the local AppData location on the client.</span></span> <span data-ttu-id="6aa5a-497">详细流程包括：</span><span class="sxs-lookup"><span data-stu-id="6aa5a-497">The detailed processes are:</span></span>

1.  <span data-ttu-id="6aa5a-498">用户通过启动应用程序来启动虚拟环境。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-498">The user starts the virtual environment by starting an application.</span></span>

2.  <span data-ttu-id="6aa5a-499">应用程序的虚拟环境将检查是否存在最新的加盖时间戳的 ZIP 文件（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-499">The application’s virtual environment checks for the most recent time stamped ZIP file, if present.</span></span>

3.  <span data-ttu-id="6aa5a-500">将检查注册表中是否存在上次已知的上载时间戳（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-500">The registry is checked for the last known uploaded timestamp, if present.</span></span>

4.  <span data-ttu-id="6aa5a-501">除非本地最后一个已知上载时间戳大于或等于 ZIP 文件中的时间戳，否则将下载最新的 ZIP 文件。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-501">The most recent ZIP file is downloaded unless the local last known upload timestamp is greater than or equal to the timestamp from the ZIP file.</span></span>

5.  <span data-ttu-id="6aa5a-502">如果本地上次已知上载时间戳比漫游 AppData 位置中最新的 ZIP 文件的旧版本更早，则会将 ZIP 文件提取到用户配置文件中的本地临时目录中。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-502">If the local last known upload timestamp is earlier than that of the most recent ZIP file in the roaming AppData location, the ZIP file is extracted to the local temp directory in the user’s profile.</span></span>

6.  <span data-ttu-id="6aa5a-503">成功提取 ZIP 文件后，将重命名漫游 AppData 目录的本地缓存，并将新数据移动到相应位置。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-503">After the ZIP file is successfully extracted, the local cache of the roaming AppData directory is renamed and the new data is moved into place.</span></span>

7.  <span data-ttu-id="6aa5a-504">已重命名的目录将被删除，应用程序将打开，其中包含最近保存的漫游 AppData 数据。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-504">The renamed directory is deleted and the application opens with the most recently saved roaming AppData data.</span></span>

<span data-ttu-id="6aa5a-505">这将完成 AppData\\Roaming 位置中存在的应用程序设置的成功漫游。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-505">This completes the successful roaming of application settings that are present in AppData\\Roaming locations.</span></span> <span data-ttu-id="6aa5a-506">唯一必须解决的其他条件是程序包修复操作。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-506">The only other condition that must be addressed is a package repair operation.</span></span> <span data-ttu-id="6aa5a-507">该过程的详细信息如下：</span><span class="sxs-lookup"><span data-stu-id="6aa5a-507">The details of the process are:</span></span>

1.  <span data-ttu-id="6aa5a-508">在修复期间，检测用户的漫游 AppData 目录的路径是否不是本地路径。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-508">During repair, detect if the path to the user’s roaming AppData directory is not local.</span></span>

2.  <span data-ttu-id="6aa5a-509">映射非本地漫游 AppData 路径目标将重新创建预期的漫游和本地 AppData 位置。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-509">Map the non-local roaming AppData path targets are recreated the expected roaming and local AppData locations.</span></span>

3.  <span data-ttu-id="6aa5a-510">删除注册表中存储的时间戳（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-510">Delete the timestamp stored in the registry, if present.</span></span>

<span data-ttu-id="6aa5a-511">此过程将重新创建 AppData 的本地和网络位置，并删除时间戳的注册表记录。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-511">This process will re-create both the local and network locations for AppData and remove the registry record of the timestamp.</span></span>

## <a href="" id="bkmk-clt-app-lifecycle"></a><span data-ttu-id="6aa5a-512">App-v 客户端应用程序生命周期管理</span><span class="sxs-lookup"><span data-stu-id="6aa5a-512">App-V client application lifecycle management</span></span>


<span data-ttu-id="6aa5a-513">在 App-v 完整基础结构中，将应用程序序列化后，通过 App-v 管理和发布服务器对用户或计算机进行管理和发布。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-513">In an App-V Full Infrastructure, after applications are sequenced they are managed and published to users or computers via the App-V Management and Publishing servers.</span></span> <span data-ttu-id="6aa5a-514">本节详细介绍了常见的 app-v 应用程序生命周期操作（添加、发布、启动、升级和删除）期间发生的操作，以及从 App-v 客户端角度更改和修改的文件和注册表位置。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-514">This section details the operations that occur during the common App-V application lifecycle operations (Add, publishing, launch, upgrade, and removal) and the file and registry locations that are changed and modified from the App-V Client perspective.</span></span> <span data-ttu-id="6aa5a-515">App-v 客户端操作以一系列在运行 App-v 客户端的计算机上启动的 PowerShell 命令的形式执行。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-515">The App-V Client operations are performed as a series of PowerShell commands initiated on the computer running the App-V Client.</span></span>

<span data-ttu-id="6aa5a-516">本文档重点介绍应用 V 完整基础结构解决方案。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-516">This document focuses on App-V Full Infrastructure solutions.</span></span> <span data-ttu-id="6aa5a-517">有关与 Configuration Manager 2012 进行的 App-v 集成的详细信息，请访问： <https://go.microsoft.com/fwlink/?LinkId=392773> 。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-517">For specific information on App-V Integration with Configuration Manager 2012 visit: <https://go.microsoft.com/fwlink/?LinkId=392773>.</span></span>

<span data-ttu-id="6aa5a-518">App-v 应用程序生命周期任务将在用户登录（默认）、计算机启动或后台计时操作时触发。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-518">The App-V application lifecycle tasks are triggered at user login (default), machine startup, or as background timed operations.</span></span> <span data-ttu-id="6aa5a-519">应用程序-V 客户端操作的设置（包括发布服务器、刷新间隔、程序包脚本启用以及其他）将在客户端安装期间配置或安装 PowerShell 命令后配置。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-519">The settings for the App-V Client operations, including Publishing Servers, refresh intervals, package script enablement, and others, are configured during setup of the client or post-setup with PowerShell commands.</span></span> <span data-ttu-id="6aa5a-520">有关如何[部署 App-v 客户端](how-to-deploy-the-app-v-client-gb18030.md)或使用 PowerShell 的说明，请参阅 TechNet 上的 "如何部署客户端" 部分：</span><span class="sxs-lookup"><span data-stu-id="6aa5a-520">See the How to Deploy the Client section on TechNet at: [How to Deploy the App-V Client](how-to-deploy-the-app-v-client-gb18030.md) or utilize the PowerShell:</span></span>

```powershell
get-command *appv*
```

### <span data-ttu-id="6aa5a-521">发布刷新</span><span class="sxs-lookup"><span data-stu-id="6aa5a-521">Publishing refresh</span></span>

<span data-ttu-id="6aa5a-522">发布刷新过程由在 App-v 客户端上执行的几个较小的操作组成。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-522">The publishing refresh process is comprised of several smaller operations that are performed on the App-V Client.</span></span> <span data-ttu-id="6aa5a-523">由于 app-v 是应用程序虚拟化技术而不是任务计划技术，因此使用 Windows 任务计划程序在用户登录、计算机启动和按计划的时间间隔启用进程。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-523">Since App-V is an application virtualization technology and not a task scheduling technology, the Windows Task Scheduler is utilized to enable the process at user logon, machine startup, and at scheduled intervals.</span></span> <span data-ttu-id="6aa5a-524">将客户端分配给具有正确设置的大型计算机组时，上述安装期间的客户端配置是首选方法。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-524">The configuration of the client during setup listed above is the preferred method when distributing the client to a large group of computers with the correct settings.</span></span> <span data-ttu-id="6aa5a-525">可通过以下 PowerShell cmdlet 配置这些客户端设置：</span><span class="sxs-lookup"><span data-stu-id="6aa5a-525">These client settings can be configured with the following PowerShell cmdlets:</span></span>

-   <span data-ttu-id="6aa5a-526">**Add-AppVPublishingServer：** 使用提供 app-v 程序包的 App-v 发布服务器配置客户端。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-526">**Add-AppVPublishingServer:** Configures the client with an App-V Publishing Server that provides App-V packages.</span></span>

-   <span data-ttu-id="6aa5a-527">**Set-AppVPublishingServer：** 修改 app-v 发布服务器的当前设置。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-527">**Set-AppVPublishingServer:** Modifies the current settings for the App-V Publishing Server.</span></span>

-   <span data-ttu-id="6aa5a-528">**Set-AppVClientConfiguration：** 修改 app-v 客户端的电流设置。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-528">**Set-AppVClientConfiguration:** Modifies the currents settings for the App-V Client.</span></span>

-   <span data-ttu-id="6aa5a-529">**Sync-AppVPublishingServer：** 手动启动 app-v 发布刷新过程。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-529">**Sync-AppVPublishingServer:** Initiates an App-V Publishing Refresh process manually.</span></span> <span data-ttu-id="6aa5a-530">在配置发布服务器期间创建的计划任务中也会使用此功能。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-530">This is also utilized in the scheduled tasks created during configuration of the publishing server.</span></span>

<span data-ttu-id="6aa5a-531">以下各节的重点是详细介绍在 App-v 发布刷新的不同阶段期间发生的操作。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-531">The focus of the following sections is to detail the operations that occur during different phases of an App-V Publishing Refresh.</span></span> <span data-ttu-id="6aa5a-532">这些主题包括：</span><span class="sxs-lookup"><span data-stu-id="6aa5a-532">The topics include:</span></span>

-   <span data-ttu-id="6aa5a-533">添加 App-v 程序包</span><span class="sxs-lookup"><span data-stu-id="6aa5a-533">Adding an App-V Package</span></span>

-   <span data-ttu-id="6aa5a-534">发布 app-v 程序包</span><span class="sxs-lookup"><span data-stu-id="6aa5a-534">Publishing an App-V Package</span></span>

### <span data-ttu-id="6aa5a-535">添加 App-v 程序包</span><span class="sxs-lookup"><span data-stu-id="6aa5a-535">Adding an App-V package</span></span>

<span data-ttu-id="6aa5a-536">将 app-v 程序包添加到客户端是发布刷新过程的第一步。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-536">Adding an App-V package to the client is the first step of the publishing refresh process.</span></span> <span data-ttu-id="6aa5a-537">最终结果与 `Add-AppVClientPackage` PowerShell 中的 cmdlet 相同，但在发布刷新添加过程中，已配置的发布服务器将被联系，并将一个高级别的应用程序列表传递回客户端，以便提取更详细的信息，而不是单个程序包添加操作。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-537">The end result is the same as the `Add-AppVClientPackage` cmdlet in PowerShell, except during the publishing refresh add process, the configured publishing server is contacted and passes a high-level list of applications back to the client to pull more detailed information and not a single package add operation.</span></span> <span data-ttu-id="6aa5a-538">通过为程序包或连接组添加或更新配置客户端，然后访问 appv 文件，将继续此过程。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-538">The process continues by configuring the client for package or connection group additions or updates, then accesses the appv file.</span></span> <span data-ttu-id="6aa5a-539">接下来，将在本地操作系统上的相应位置展开并放置 appv 文件的内容。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-539">Next, the contents of the appv file are expanded and placed on the local operating system in the appropriate locations.</span></span> <span data-ttu-id="6aa5a-540">以下是进程的详细工作流，假设将程序包配置为用于故障流。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-540">The following is a detailed workflow of the process, assuming the package is configured for Fault Streaming.</span></span>

**<span data-ttu-id="6aa5a-541">如何添加 App-v 程序包</span><span class="sxs-lookup"><span data-stu-id="6aa5a-541">How to add an App-V package</span></span>**

1.  <span data-ttu-id="6aa5a-542">通过发布刷新过程的 PowerShell 或任务序列启动手动启动。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-542">Manual initiation via PowerShell or Task Sequence initiation of the Publishing Refresh process.</span></span>

    1.  <span data-ttu-id="6aa5a-543">App-v 客户端进行 HTTP 连接，并请求基于目标的应用程序列表。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-543">The App-V Client makes an HTTP connection and requests a list of applications based on the target.</span></span> <span data-ttu-id="6aa5a-544">发布刷新过程支持面向计算机或用户。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-544">The Publishing refresh process supports targeting machines or users.</span></span>

    2.  <span data-ttu-id="6aa5a-545">App-v 发布服务器使用启动目标、用户或计算机的标识，并查询数据库以获取具有标题的应用程序的列表。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-545">The App-V Publishing Server uses the identity of the initiating target, user or machine, and queries the database for a list of entitled applications.</span></span> <span data-ttu-id="6aa5a-546">应用程序列表以 XML 响应的形式提供，客户端使用它向服务器发送其他请求，以获取有关每个程序包的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-546">The list of applications is provided as an XML response, which the client uses to send additional requests to the server for more information on a per package basis.</span></span>

2.  <span data-ttu-id="6aa5a-547">App-v 客户端上的发布代理执行以下序列化的所有操作。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-547">The Publishing Agent on the App-V Client performs all actions below serialized.</span></span>

    <span data-ttu-id="6aa5a-548">评估未发布或已禁用的任何连接组，因为无法处理属于连接组的程序包版本更新。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-548">Evaluate any connection groups that are unpublished or disabled, since package version updates that are part of the connection group cannot be processed.</span></span>

3.  <span data-ttu-id="6aa5a-549">通过标识添加或更新操作来配置程序包。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-549">Configure the packages by identifying an Add or Update operations.</span></span>

    1.  <span data-ttu-id="6aa5a-550">App-v 客户端利用 Windows 中的 AppX API，并从发布服务器访问 appv 文件。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-550">The App-V Client utilizes the AppX API from Windows and accesses the appv file from the publishing server.</span></span>

    2.  <span data-ttu-id="6aa5a-551">将打开程序包文件，并将 AppXManifest.xml 和 StreamMap.xml 下载到程序包存储。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-551">The package file is opened and the AppXManifest.xml and StreamMap.xml are downloaded to the Package Store.</span></span>

    3.  <span data-ttu-id="6aa5a-552">已完全流出在 StreamMap.xml 中定义的发布块数据。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-552">Completely stream publishing block data defined in the StreamMap.xml.</span></span> <span data-ttu-id="6aa5a-553">将发布块数据存储在程序包 Store\\PkgGUID\\VerGUID\\Root. 中</span><span class="sxs-lookup"><span data-stu-id="6aa5a-553">Stores the publishing block data in the Package Store\\PkgGUID\\VerGUID\\Root.</span></span>

        -   <span data-ttu-id="6aa5a-554">图标：扩展点的目标。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-554">Icons: Targets of extension points.</span></span>

        -   <span data-ttu-id="6aa5a-555">可移植可执行文件头（PE 标头）：扩展点的目标，其中包含有关图像的基本信息需要在磁盘上、直接访问或通过文件类型。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-555">Portable Executable Headers (PE Headers): Targets of extension points that contain the base information about the image need on disk, directly accessed or via file types.</span></span>

        -   <span data-ttu-id="6aa5a-556">脚本：下载脚本目录以供在整个发布过程中使用。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-556">Scripts: Download scripts directory for use throughout the publishing process.</span></span>

    4.  <span data-ttu-id="6aa5a-557">填充包存储：</span><span class="sxs-lookup"><span data-stu-id="6aa5a-557">Populate the Package store:</span></span>

        1.  <span data-ttu-id="6aa5a-558">在磁盘上创建用于表示列出的任何目录的提取程序包的稀疏文件。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-558">Create sparse files on disk that represent the extracted package for any directories listed.</span></span>

        2.  <span data-ttu-id="6aa5a-559">在 root 之下暂存顶级文件和目录。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-559">Stage top level files and directories under root.</span></span>

        3.  <span data-ttu-id="6aa5a-560">当目录在磁盘上列为稀疏并按需进行流式处理时，将创建所有其他文件。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-560">All other files are created when the directory is listed as sparse on disk and streamed on demand.</span></span>

    5.  <span data-ttu-id="6aa5a-561">创建计算机目录条目。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-561">Create the machine catalog entries.</span></span> <span data-ttu-id="6aa5a-562">从程序包文件创建 Manifest.xml 和 DeploymentConfiguration.xml （如果程序包中没有创建占位符的 DeploymentConfiguration.xml 文件）。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-562">Create the Manifest.xml and DeploymentConfiguration.xml from the package files (if no DeploymentConfiguration.xml file in the package a placeholder is created).</span></span>

    6.  <span data-ttu-id="6aa5a-563">在注册表中创建软件包存储的位置 HKLM\\Software\\Microsoft\\AppV\\Client\\Packages\\PkgGUID\\Versions\\VerGUID\\Catalog</span><span class="sxs-lookup"><span data-stu-id="6aa5a-563">Create location of the package store in the registry HKLM\\Software\\Microsoft\\AppV\\Client\\Packages\\PkgGUID\\Versions\\VerGUID\\Catalog</span></span>

    7.  <span data-ttu-id="6aa5a-564">创建从包存储到%ProgramData%\\Microsoft\\AppV\\Client\\VReg\\ {VersionGUID} .dat 的注册表 .dat 文件</span><span class="sxs-lookup"><span data-stu-id="6aa5a-564">Create the Registry.dat file from the package store to %ProgramData%\\Microsoft\\AppV\\Client\\VReg\\{VersionGUID}.dat</span></span>

    8.  <span data-ttu-id="6aa5a-565">在应用程序 V 内核模式驱动程序 HKLM\\Microsoft\\Software\\AppV\\MAV 注册程序包</span><span class="sxs-lookup"><span data-stu-id="6aa5a-565">Register the package with the App-V Kernel Mode Driver HKLM\\Microsoft\\Software\\AppV\\MAV</span></span>

    9.  <span data-ttu-id="6aa5a-566">从 "AppxManifest.xml" 或 "DeploymentConfig.xml 文件" 中调用脚本以进行程序包添加计时。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-566">Invoke scripting from the AppxManifest.xml or DeploymentConfig.xml file for Package Add timing.</span></span>

4.  <span data-ttu-id="6aa5a-567">通过添加和启用或禁用来配置连接组。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-567">Configure Connection Groups by adding and enabling or disabling.</span></span>

5.  <span data-ttu-id="6aa5a-568">删除未发布到目标（用户或计算机）的对象。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-568">Remove objects that are not published to the target (user or machine).</span></span>

    <span data-ttu-id="6aa5a-569">**注意** 这将不会执行程序包删除，而是删除特定目标（用户或计算机）的集成点，并删除用户目录文件（适用于全局发布的计算机目录文件）。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-569">**Note** This will not perform a package deletion but rather remove integration points for the specific target (user or machine) and remove user catalog files (machine catalog files for globally published).</span></span>

     

6.  <span data-ttu-id="6aa5a-570">基于客户端配置调用后台加载装载。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-570">Invoke background load mounting based on client configuration.</span></span>

7.  <span data-ttu-id="6aa5a-571">已立即还原计算机或用户的发布信息的程序包。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-571">Packages that already have publishing information for the machine or user are immediately restored.</span></span>

    <span data-ttu-id="6aa5a-572">**注意** 这种情况在未通过后台添加程序包的情况下作为删除的产品出现。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-572">**Note** This condition occurs as a product of removal without unpublishing with background addition of the package.</span></span>

     

<span data-ttu-id="6aa5a-573">这将完成发布刷新过程的应用程序-V 包的添加。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-573">This completes an App-V package add of the publishing refresh process.</span></span> <span data-ttu-id="6aa5a-574">下一步是将程序包发布到特定目标（计算机或用户）。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-574">The next step is publishing the package to the specific target (machine or user).</span></span>

![程序包添加文件和注册表数据](images/packageaddfileandregistrydata.png)

### <span data-ttu-id="6aa5a-576">发布 app-v 程序包</span><span class="sxs-lookup"><span data-stu-id="6aa5a-576">Publishing an App-V package</span></span>

<span data-ttu-id="6aa5a-577">在发布刷新操作期间，特定发布操作（Publish-AppVClientPackage）将条目添加到用户目录、将权利映射到用户、标识本地存储以及完成任何集成步骤。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-577">During the Publishing Refresh operation, the specific publishing operation (Publish-AppVClientPackage) adds entries to the user catalog, maps entitlement to the user, identifies the local store, and finishes by completing any integration steps.</span></span> <span data-ttu-id="6aa5a-578">以下是详细步骤。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-578">The following are the detailed steps.</span></span>

**<span data-ttu-id="6aa5a-579">如何发布和 App-v 程序包</span><span class="sxs-lookup"><span data-stu-id="6aa5a-579">How to publish and App-V package</span></span>**

1.  <span data-ttu-id="6aa5a-580">将程序包条目添加到用户目录</span><span class="sxs-lookup"><span data-stu-id="6aa5a-580">Package entries are added to the user catalog</span></span>

    1.  <span data-ttu-id="6aa5a-581">用户目标程序包：将 UserDeploymentConfiguration.xml 和 UserManifest.xml 放在计算机上的用户目录中</span><span class="sxs-lookup"><span data-stu-id="6aa5a-581">User targeted packages: the UserDeploymentConfiguration.xml and UserManifest.xml are placed on the machine in the User Catalog</span></span>

    2.  <span data-ttu-id="6aa5a-582">计算机定向的（全局）程序包： UserDeploymentConfiguration.xml 位于计算机目录中</span><span class="sxs-lookup"><span data-stu-id="6aa5a-582">Machine targeted (global) packages: the UserDeploymentConfiguration.xml is placed in the Machine Catalog</span></span>

2.  <span data-ttu-id="6aa5a-583">在 HKLM\\Software\\Microsoft\\AppV\\MAV 上向用户注册程序包的内核模式驱动程序</span><span class="sxs-lookup"><span data-stu-id="6aa5a-583">Register the package with the kernel mode driver for the user at HKLM\\Software\\Microsoft\\AppV\\MAV</span></span>

3.  <span data-ttu-id="6aa5a-584">执行集成任务。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-584">Perform integration tasks.</span></span>

    1.  <span data-ttu-id="6aa5a-585">创建扩展点。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-585">Create extension points.</span></span>

    2.  <span data-ttu-id="6aa5a-586">将备份信息存储在用户的注册表和漫游配置文件中（快捷方式备份）。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-586">Store backup information in the user’s registry and roaming profile (Shortcut Backups).</span></span>

        <span data-ttu-id="6aa5a-587">**注意** 如果未发布程序包，这将允许还原扩展点。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-587">**Note** This enables restore extension points if the package is unpublished.</span></span>

         

    3.  <span data-ttu-id="6aa5a-588">运行针对发布计时的脚本。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-588">Run scripts targeted for publishing timing.</span></span>

<span data-ttu-id="6aa5a-589">发布属于连接组的 app-v 程序包非常类似于上述过程。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-589">Publishing an App-V Package that is part of a Connection Group is very similar to the above process.</span></span> <span data-ttu-id="6aa5a-590">对于连接组，存储特定目录信息的路径包括 PackageGroups 作为目录目录的子目录。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-590">For connection groups, the path that stores the specific catalog information includes PackageGroups as a child of the Catalog Directory.</span></span> <span data-ttu-id="6aa5a-591">有关详细信息，请查看上述计算机和用户目录信息。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-591">Review the machine and users catalog information above for details.</span></span>

![程序包添加文件和注册表数据-全局](images/packageaddfileandregistrydata-global.png)

### <span data-ttu-id="6aa5a-593">应用程序启动</span><span class="sxs-lookup"><span data-stu-id="6aa5a-593">Application launch</span></span>

<span data-ttu-id="6aa5a-594">发布刷新过程后，用户将启动并重新启动 App-v 应用程序。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-594">After the Publishing Refresh process, the user launches and subsequently re-launches an App-V application.</span></span> <span data-ttu-id="6aa5a-595">该过程非常简单，并且经过优化，可通过最少的网络流量快速启动。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-595">The process is very simple and optimized to launch quickly with a minimum of network traffic.</span></span> <span data-ttu-id="6aa5a-596">App-v 客户端将检查在发布期间创建的文件的用户目录的路径。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-596">The App-V Client checks the path to the user catalog for files created during publishing.</span></span> <span data-ttu-id="6aa5a-597">建立了启动程序包的权限后，App-v 客户端将创建一个虚拟环境、开始流式处理任何必需的数据，并在创建虚拟环境期间应用相应的清单和部署配置文件。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-597">After rights to launch the package are established, the App-V Client creates a virtual environment, begins streaming any necessary data, and applies the appropriate manifest and deployment configuration files during virtual environment creation.</span></span> <span data-ttu-id="6aa5a-598">在为特定程序包和应用程序创建和配置的虚拟环境下，应用程序启动。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-598">With the virtual environment created and configured for the specific package and application, the application starts.</span></span>

**<span data-ttu-id="6aa5a-599">如何启动 app-v 应用程序</span><span class="sxs-lookup"><span data-stu-id="6aa5a-599">How to launch App-V applications</span></span>**

1.  <span data-ttu-id="6aa5a-600">用户通过单击快捷方式或文件类型调用来启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-600">User launches the application by clicking on a shortcut or file type invocation.</span></span>

2.  <span data-ttu-id="6aa5a-601">App-v 客户端验证以下文件的用户目录中是否存在</span><span class="sxs-lookup"><span data-stu-id="6aa5a-601">The App-V Client verifies existence in the User Catalog for the following files</span></span>

    -   <span data-ttu-id="6aa5a-602">UserDeploymentConfiguration.xml</span><span class="sxs-lookup"><span data-stu-id="6aa5a-602">UserDeploymentConfiguration.xml</span></span>

    -   <span data-ttu-id="6aa5a-603">UserManifest.xml</span><span class="sxs-lookup"><span data-stu-id="6aa5a-603">UserManifest.xml</span></span>

3.  <span data-ttu-id="6aa5a-604">如果文件存在，应用程序将有权使用该特定用户，应用程序将启动启动过程。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-604">If the files are present, the application is entitled for that specific user and the application will start the process for launch.</span></span> <span data-ttu-id="6aa5a-605">此时没有网络流量。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-605">There is no network traffic at this point.</span></span>

4.  <span data-ttu-id="6aa5a-606">接下来，App-v 客户端检查注册表中是否找到为 App-v 客户端服务注册的程序包的路径。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-606">Next, the App-V Client checks that the path for the package registered for the App-V Client service is found in the registry.</span></span>

5.  <span data-ttu-id="6aa5a-607">找到程序包存储的路径后，将创建虚拟环境。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-607">Upon finding the path to the package store, the virtual environment is created.</span></span> <span data-ttu-id="6aa5a-608">如果这是首次启动，则主要功能阻止下载（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-608">If this is the first launch, the Primary Feature Block downloads if present.</span></span>

6.  <span data-ttu-id="6aa5a-609">下载后，app-v 客户端服务将使用清单和部署配置文件来配置虚拟环境并加载所有 App-v 子系统。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-609">After downloading, the App-V Client service consumes the manifest and deployment configuration files to configure the virtual environment and all App-V subsystems are loaded.</span></span>

7.  <span data-ttu-id="6aa5a-610">应用程序启动。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-610">The Application launches.</span></span> <span data-ttu-id="6aa5a-611">对于程序包存储（稀疏文件）中的任何缺少的文件，App-v 将根据需要流出文件错误。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-611">For any missing files in the package store (sparse files), App-V will stream fault the files on an as needed basis.</span></span>

    ![程序包添加文件和注册表数据流](images/packageaddfileandregistrydata-stream.png)

### <span data-ttu-id="6aa5a-613">升级 app-v 程序包</span><span class="sxs-lookup"><span data-stu-id="6aa5a-613">Upgrading an App-V package</span></span>

<span data-ttu-id="6aa5a-614">App-v 5 程序包升级过程与早期版本的 App-v 不同。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-614">The App-V 5 package upgrade process differs from the older versions of App-V.</span></span> <span data-ttu-id="6aa5a-615">App-v 支持具有不同用户的计算机上的同一程序包的多个版本。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-615">App-V supports multiple versions of the same package on a machine entitled to different users.</span></span> <span data-ttu-id="6aa5a-616">可以随时添加程序包版本，因为程序包存储和目录已通过新资源进行更新。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-616">Package versions can be added at any time as the package store and catalogs are updated with the new resources.</span></span> <span data-ttu-id="6aa5a-617">特定于添加新版本资源的唯一流程是存储优化。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-617">The only process specific to the addition of new version resources is storage optimization.</span></span> <span data-ttu-id="6aa5a-618">在升级过程中，仅将新文件添加到新版本存储位置，并为未更改的文件创建硬链接。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-618">During an upgrade, only the new files are added to the new version store location and hard links are created for unchanged files.</span></span> <span data-ttu-id="6aa5a-619">这将减少整个存储，只是在一个磁盘位置上显示文件，然后在磁盘上有一个文件位置条目的所有文件夹中投影到该文件。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-619">This reduces the overall storage by only presenting the file on one disk location and then projecting it into all folders with a file location entry on the disk.</span></span> <span data-ttu-id="6aa5a-620">升级 app-v 程序包的具体详细信息如下所示：</span><span class="sxs-lookup"><span data-stu-id="6aa5a-620">The specific details of upgrading an App-V Package are as follows:</span></span>

**<span data-ttu-id="6aa5a-621">如何升级 app-v 程序包</span><span class="sxs-lookup"><span data-stu-id="6aa5a-621">How to upgrade an App-V package</span></span>**

1.  <span data-ttu-id="6aa5a-622">App-v 客户端执行发布刷新并发现较新版本的 App-v 包。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-622">The App-V Client performs a Publishing Refresh and discovers a newer version of an App-V Package.</span></span>

2.  <span data-ttu-id="6aa5a-623">程序包条目将添加到新版本的相应目录中</span><span class="sxs-lookup"><span data-stu-id="6aa5a-623">Package entries are added to the appropriate catalog for the new version</span></span>

    1.  <span data-ttu-id="6aa5a-624">用户目标程序包：将 UserDeploymentConfiguration.xml 和 UserManifest.xml 放在计算机上 appdata\\roaming\\Microsoft\\AppV\\Client\\Catalog\\Packages\\PkgGUID\\VerGUID 的用户目录中</span><span class="sxs-lookup"><span data-stu-id="6aa5a-624">User targeted packages: the UserDeploymentConfiguration.xml and UserManifest.xml are placed on the machine in the user catalog at appdata\\roaming\\Microsoft\\AppV\\Client\\Catalog\\Packages\\PkgGUID\\VerGUID</span></span>

    2.  <span data-ttu-id="6aa5a-625">计算机定向的（全局）程序包： UserDeploymentConfiguration.xml 位于%programdata%\\Microsoft\\AppV\\Client\\Catalog\\Packages\\PkgGUID\\VerGUID 的计算机目录中</span><span class="sxs-lookup"><span data-stu-id="6aa5a-625">Machine targeted (global) packages: the UserDeploymentConfiguration.xml is placed in the machine catalog at %programdata%\\Microsoft\\AppV\\Client\\Catalog\\Packages\\PkgGUID\\VerGUID</span></span>

3.  <span data-ttu-id="6aa5a-626">在 HKLM\\Software\\Microsoft\\AppV\\MAV 上向用户注册程序包的内核模式驱动程序</span><span class="sxs-lookup"><span data-stu-id="6aa5a-626">Register the package with the kernel mode driver for the user at HKLM\\Software\\Microsoft\\AppV\\MAV</span></span>

4.  <span data-ttu-id="6aa5a-627">执行集成任务。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-627">Perform integration tasks.</span></span>

    -   <span data-ttu-id="6aa5a-628">将扩展点（EP）与清单和动态配置文件集成。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-628">Integrate extensions points (EP) from the Manifest and Dynamic Configuration files.</span></span>

    1.  <span data-ttu-id="6aa5a-629">基于文件的 EP 数据存储在 AppData 文件夹中，利用来自程序包存储的交接点。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-629">File based EP data is stored in the AppData folder utilizing Junction Points from the package store.</span></span>

    2.  <span data-ttu-id="6aa5a-630">当有新版本可用时，版本 1 EPs 已存在。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-630">Version 1 EPs already exist when a new version becomes available.</span></span>

    3.  <span data-ttu-id="6aa5a-631">对于任何更新或更新的扩展点，扩展点将切换到计算机或用户目录中的版本2位置。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-631">The extension points are switched to the Version 2 location in machine or user catalogs for any newer or updated extension points.</span></span>

5.  <span data-ttu-id="6aa5a-632">运行针对发布计时的脚本。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-632">Run scripts targeted for publishing timing.</span></span>

6.  <span data-ttu-id="6aa5a-633">根据需要安装 "并行程序集"。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-633">Install Side by Side assemblies as required.</span></span>

### <span data-ttu-id="6aa5a-634">升级使用中的 App-v 包</span><span class="sxs-lookup"><span data-stu-id="6aa5a-634">Upgrading an in-use App-V package</span></span>

<span data-ttu-id="6aa5a-635">**从 app-v 5 SP2 开始**：如果你尝试升级已由最终用户使用的程序包，则会将升级任务置于挂起状态。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-635">**Starting in App-V 5 SP2**: If you try to upgrade a package that is in use by an end user, the upgrade task is placed in a pending state.</span></span> <span data-ttu-id="6aa5a-636">稍后将根据以下规则运行升级：</span><span class="sxs-lookup"><span data-stu-id="6aa5a-636">The upgrade will run later, according to the following rules:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6aa5a-637">任务类型</span><span class="sxs-lookup"><span data-stu-id="6aa5a-637">Task type</span></span></th>
<th align="left"><span data-ttu-id="6aa5a-638">适用规则</span><span class="sxs-lookup"><span data-stu-id="6aa5a-638">Applicable rule</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6aa5a-639">基于用户的任务，例如将程序包发布给用户</span><span class="sxs-lookup"><span data-stu-id="6aa5a-639">User-based task, e.g., publishing a package to a user</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-640">将在用户注销后执行挂起的任务，然后重新登录。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-640">The pending task will be performed after the user logs off and then logs back on.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6aa5a-641">基于全球的任务，例如，全局启用连接组</span><span class="sxs-lookup"><span data-stu-id="6aa5a-641">Globally based task, e.g., enabling a connection group globally</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-642">当计算机关闭然后重新启动时，将执行挂起的任务。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-642">The pending task will be performed when the computer is shut down and then restarted.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="6aa5a-643">当任务置于挂起状态时，App-v 客户端还会为挂起任务生成注册表项，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6aa5a-643">When a task is placed in a pending state, the App-V client also generates a registry key for the pending task, as follows:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6aa5a-644">基于用户或基于全球的任务</span><span class="sxs-lookup"><span data-stu-id="6aa5a-644">User-based or globally based task</span></span></th>
<th align="left"><span data-ttu-id="6aa5a-645">注册表项的生成位置</span><span class="sxs-lookup"><span data-stu-id="6aa5a-645">Where the registry key is generated</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6aa5a-646">基于用户的任务</span><span class="sxs-lookup"><span data-stu-id="6aa5a-646">User-based tasks</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-647">KEY_CURRENT_USER \Software\Microsoft\AppV\Client\PendingTasks</span><span class="sxs-lookup"><span data-stu-id="6aa5a-647">KEY_CURRENT_USER\Software\Microsoft\AppV\Client\PendingTasks</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6aa5a-648">基于全球的任务</span><span class="sxs-lookup"><span data-stu-id="6aa5a-648">Globally based tasks</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-649">HKEY_LOCAL_MACHINE \Software\Microsoft\AppV\Client\PendingTasks</span><span class="sxs-lookup"><span data-stu-id="6aa5a-649">HKEY_LOCAL_MACHINE\Software\Microsoft\AppV\Client\PendingTasks</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="6aa5a-650">必须先完成以下操作，然后用户才能使用程序包的较新版本：</span><span class="sxs-lookup"><span data-stu-id="6aa5a-650">The following operations must be completed before users can use the newer version of the package:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6aa5a-651">任务</span><span class="sxs-lookup"><span data-stu-id="6aa5a-651">Task</span></span></th>
<th align="left"><span data-ttu-id="6aa5a-652">详细信息</span><span class="sxs-lookup"><span data-stu-id="6aa5a-652">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6aa5a-653">将程序包添加到计算机</span><span class="sxs-lookup"><span data-stu-id="6aa5a-653">Add the package to the computer</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-654">此任务是计算机特定的，你可以随时完成上述 "程序包添加" 部分中的步骤执行此任务。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-654">This task is computer specific and you can perform it at any time by completing the steps in the Package Add section above.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6aa5a-655">发布程序包</span><span class="sxs-lookup"><span data-stu-id="6aa5a-655">Publish the package</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-656">有关步骤，请参阅上面的程序包发布部分。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-656">See the Package Publishing section above for steps.</span></span> <span data-ttu-id="6aa5a-657">此过程要求你在系统上更新扩展点。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-657">This process requires that you update extension points on the system.</span></span> <span data-ttu-id="6aa5a-658">完成此任务后，最终用户无法使用该应用程序。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-658">End users cannot be using the application when you complete this task.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="6aa5a-659">将以下示例方案用作更新程序包的指南。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-659">Use the following example scenarios as a guide for updating packages.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6aa5a-660">情形</span><span class="sxs-lookup"><span data-stu-id="6aa5a-660">Scenario</span></span></th>
<th align="left"><span data-ttu-id="6aa5a-661">要求</span><span class="sxs-lookup"><span data-stu-id="6aa5a-661">Requirements</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6aa5a-662">尝试升级时，未使用 app-v 程序包</span><span class="sxs-lookup"><span data-stu-id="6aa5a-662">App-V package is not in use when you try to upgrade</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-663">程序包的以下组件均不能使用：虚拟应用程序、COM 服务器或外壳扩展。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-663">None of the following components of the package can be in use: virtual application, COM server, or shell extensions.</span></span></p>
<p><span data-ttu-id="6aa5a-664">管理员发布较新版本的程序包，升级将在下次启动程序包中的组件或应用程序时运行。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-664">The administrator publishes a newer version of the package and the upgrade works the next time a component or application inside the package is launched.</span></span> <span data-ttu-id="6aa5a-665">数据包的新版本将被流式处理并运行。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-665">The new version of the package is streamed and run.</span></span> <span data-ttu-id="6aa5a-666">从 app-v 5 早期版本的 app-v 5 SP2 中，此方案中没有任何更改。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-666">Nothing has changed in this scenario in App-V 5 SP2 from previous releases of App-V 5.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6aa5a-667">管理员发布更新版本的程序包时，正在使用 app-v 包</span><span class="sxs-lookup"><span data-stu-id="6aa5a-667">App-V package is in use when the administrator publishes a newer version of the package</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-668">升级操作设置为 "App-v 客户端挂起"，这意味着它将排队，稍后在程序包未使用时执行。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-668">The upgrade operation is set to pending by the App-V Client, which means that it is queued and carried out later when the package is not in use.</span></span></p>
<p><span data-ttu-id="6aa5a-669">如果程序包应用程序正在使用中，用户将关闭虚拟应用程序，之后可以进行升级。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-669">If the package application is in use, the user shuts down the virtual application, after which the upgrade can occur.</span></span></p>
<p><span data-ttu-id="6aa5a-670">如果程序包具有外壳扩展（Office 2013），而它们由 Windows 资源管理器永久加载，则用户无法登录。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-670">If the package has shell extensions (Office 2013), which are permanently loaded by Windows Explorer, the user cannot be logged in.</span></span> <span data-ttu-id="6aa5a-671">用户必须注销，然后重新登录才能启动 app-v 程序包升级。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-671">Users must log off and the log back in to initiate the App-V package upgrade.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="6aa5a-672">全局和用户发布</span><span class="sxs-lookup"><span data-stu-id="6aa5a-672">Global vs user publishing</span></span>

<span data-ttu-id="6aa5a-673">可以通过两种方式之一发布 app-v 程序包;用户向特定用户或用户组证明了 app-v 程序包的用户和全局，这将对计算机的所有用户提供对整个计算机的 App-v 程序包。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-673">App-V Packages can be published in one of two ways; User which entitles an App-V package to a specific user or group of users and Global which entitles the App-V package to the entire machine for all users of the machine.</span></span> <span data-ttu-id="6aa5a-674">一旦程序包升级挂起且未使用 app-v 包，请考虑两种类型的发布：</span><span class="sxs-lookup"><span data-stu-id="6aa5a-674">Once a package upgrade has been pended and the App-V package is not in use, consider the two types of publishing:</span></span>

-   <span data-ttu-id="6aa5a-675">**全局发布**：将应用程序发布到计算机;该计算机上的所有用户都可以使用它。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-675">**Globally published**: the application is published to a machine; all users on that machine can use it.</span></span> <span data-ttu-id="6aa5a-676">升级将在 App-v Client 服务启动时进行，这将有效地表示计算机重新启动。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-676">The upgrade will happen when the App-V Client Service starts, which effectively means a machine restart.</span></span>

-   <span data-ttu-id="6aa5a-677">**用户已发布**：应用程序已发布给用户。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-677">**User published**: the application is published to a user.</span></span> <span data-ttu-id="6aa5a-678">如果计算机上有多个用户，则可以将应用程序发布到用户的子集。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-678">If there are multiple users on the machine, the application can be published to a subset of the users.</span></span> <span data-ttu-id="6aa5a-679">当用户登录或再次发布时（定期、ConfigMgr 策略刷新和评估、应用程序 V 定期发布/刷新或通过 PowerShell 命令显式发布），将发生升级。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-679">The upgrade will happen when the user logs in or when it is published again (periodically, ConfigMgr Policy refresh and evaluation, or an App-V periodic publishing/refresh, or explicitly via PowerShell commands).</span></span>

### <span data-ttu-id="6aa5a-680">删除 App-v 程序包</span><span class="sxs-lookup"><span data-stu-id="6aa5a-680">Removing an App-V package</span></span>

<span data-ttu-id="6aa5a-681">在完整基础结构中删除 App-v 应用程序是取消发布操作，不会执行程序包删除。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-681">Removing App-V applications in a Full Infrastructure is an unpublish operation, and does not perform a package removal.</span></span> <span data-ttu-id="6aa5a-682">该过程与上述发布过程相同，但不是添加删除过程会反转对 app-v 程序包所做的更改。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-682">The process is the same as the publish process above, but instead of adding the removal process reverses the changes that have been made for App-V Packages.</span></span>

### <span data-ttu-id="6aa5a-683">修复 App-v 程序包</span><span class="sxs-lookup"><span data-stu-id="6aa5a-683">Repairing an App-V package</span></span>

<span data-ttu-id="6aa5a-684">修复操作非常简单，但可能会影响计算机上的多个位置。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-684">The repair operation is very simple but may affect many locations on the machine.</span></span> <span data-ttu-id="6aa5a-685">前面提到的 "写入" （牛）位置将被删除，扩展点将被取消集成，然后重新集成。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-685">The previously mentioned Copy on Write (COW) locations are removed, and extension points are de-integrated and then re-integrated.</span></span> <span data-ttu-id="6aa5a-686">请通过查看注册表中的注册位置来查看牛数据放置位置。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-686">Please review the COW data placement locations by reviewing where they are registered in the registry.</span></span> <span data-ttu-id="6aa5a-687">此操作自动执行，除了从 App-v 客户端控制台或通过 PowerShell 发起修复操作之外，没有任何管理控制。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-687">This operation is done automatically and there is no administrative control other than initiating a Repair operation from the App-V Client Console or via PowerShell (Repair-AppVClientPackage).</span></span>

## <a href="" id="bkmk-integr-appv-pkgs"></a><span data-ttu-id="6aa5a-688">App-v 程序包的集成</span><span class="sxs-lookup"><span data-stu-id="6aa5a-688">Integration of App-V packages</span></span>


<span data-ttu-id="6aa5a-689">App-v 客户端和程序包体系结构在添加和发布程序包的过程中提供与本地操作系统的特定集成。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-689">The App-V Client and package architecture provides specific integration with the local operating system during the addition and publishing of packages.</span></span> <span data-ttu-id="6aa5a-690">三个文件定义了 app-v 包的集成或扩展点：</span><span class="sxs-lookup"><span data-stu-id="6aa5a-690">Three files define the integration or extension points for an App-V Package:</span></span>

-   <span data-ttu-id="6aa5a-691">AppXManifest.xml：存储在程序包内，并将回退副本存储在程序包存储和用户配置文件中。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-691">AppXManifest.xml: Stored inside of the package with fallback copies stored in the package store and the user profile.</span></span> <span data-ttu-id="6aa5a-692">包含在排序过程中创建的选项。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-692">Contains the options created during the sequencing process.</span></span>

-   <span data-ttu-id="6aa5a-693">DeploymentConfig.xml：提供计算机和基于用户的集成扩展点的配置信息。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-693">DeploymentConfig.xml: Provides configuration information of computer and user based integration extension points.</span></span>

-   <span data-ttu-id="6aa5a-694">UserConfig.xml：仅提供基于用户的配置和仅面向基于用户的扩展点的 Deploymentconfig.xml 的子集。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-694">UserConfig.xml: A subset of the Deploymentconfig.xml that only provides user- based configurations and only targets user-based extension points.</span></span>

### <span data-ttu-id="6aa5a-695">集成规则</span><span class="sxs-lookup"><span data-stu-id="6aa5a-695">Rules of integration</span></span>

<span data-ttu-id="6aa5a-696">在使用 app-v 客户端将 App-v 应用程序发布到计算机时，按照下面的列表中所述执行某些特定操作：</span><span class="sxs-lookup"><span data-stu-id="6aa5a-696">When App-V applications are published to a computer with the App-V Client, some specific actions take place as described in the list below:</span></span>

-   <span data-ttu-id="6aa5a-697">全局发布：快捷方式存储在 "所有用户配置文件" 位置，其他扩展点存储在 HKLM 配置单元中的注册表中。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-697">Global Publishing: Shortcuts are stored in the All Users profile location and other extension points are stored in the registry in the HKLM hive.</span></span>

-   <span data-ttu-id="6aa5a-698">用户发布：快捷方式存储在当前用户帐户配置文件中，其他扩展点存储在 HKCU 配置单元中的注册表中。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-698">User Publishing: Shortcuts are stored in the current user account profile and other extension points are stored in the registry in the HKCU hive.</span></span>

-   <span data-ttu-id="6aa5a-699">备份和还原：在发布期间备份现有的本机应用程序数据和注册表（如 FTA 注册）。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-699">Backup and Restore: Existing native application data and registry (such as FTA registrations) are backed up during publishing.</span></span>

    1.  <span data-ttu-id="6aa5a-700">App-v 程序包基于上一个集成的程序包（所有权已传递到最新发布的 App-v 应用程序）获得所有权。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-700">App-V packages are given ownership based on the last integrated package where the ownership is passed to the newest published App-V application.</span></span>

    2.  <span data-ttu-id="6aa5a-701">当未发布所属的 App-v 包时，所有权将从一个 App-v 包转移到另一个。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-701">Ownership transfers from one App-V package to another when the owning App-V package is unpublished.</span></span> <span data-ttu-id="6aa5a-702">这将不会启动数据或注册表的还原。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-702">This will not initiate a restore of the data or registry.</span></span>

    3.  <span data-ttu-id="6aa5a-703">在每个扩展点取消发布或删除最后一个软件包时，还原已备份的数据。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-703">Restore the backed up data when the last package is unpublished or removed on a per extension point basis.</span></span>

### <span data-ttu-id="6aa5a-704">扩展点</span><span class="sxs-lookup"><span data-stu-id="6aa5a-704">Extension points</span></span>

<span data-ttu-id="6aa5a-705">App-v 发布文件（清单和动态配置）提供了多个扩展点，使应用程序可以与本地操作系统集成。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-705">The App-V publishing files (manifest and dynamic configuration) provide several extension points that enable the application to integrate with the local operating system.</span></span> <span data-ttu-id="6aa5a-706">这些扩展点执行典型的应用程序安装任务，例如放置快捷方式、创建文件类型关联和注册组件。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-706">These extension points perform typical application installation tasks, such as placing shortcuts, creating file type associations, and registering components.</span></span> <span data-ttu-id="6aa5a-707">由于这些应用程序的虚拟应用程序与传统应用程序的安装方式不同，因此存在一些差异。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-707">As these are virtualized applications that are not installed in the same manner a traditional application, there are some differences.</span></span> <span data-ttu-id="6aa5a-708">以下是本部分中介绍的扩展点列表：</span><span class="sxs-lookup"><span data-stu-id="6aa5a-708">The following is a list of extension points covered in this section:</span></span>

-   <span data-ttu-id="6aa5a-709">指向</span><span class="sxs-lookup"><span data-stu-id="6aa5a-709">Shortcuts</span></span>

-   <span data-ttu-id="6aa5a-710">文件类型关联</span><span class="sxs-lookup"><span data-stu-id="6aa5a-710">File Type Associations</span></span>

-   <span data-ttu-id="6aa5a-711">外壳扩展</span><span class="sxs-lookup"><span data-stu-id="6aa5a-711">Shell Extensions</span></span>

-   <span data-ttu-id="6aa5a-712">COM</span><span class="sxs-lookup"><span data-stu-id="6aa5a-712">COM</span></span>

-   <span data-ttu-id="6aa5a-713">软件客户端</span><span class="sxs-lookup"><span data-stu-id="6aa5a-713">Software Clients</span></span>

-   <span data-ttu-id="6aa5a-714">应用程序功能</span><span class="sxs-lookup"><span data-stu-id="6aa5a-714">Application capabilities</span></span>

-   <span data-ttu-id="6aa5a-715">URL 协议处理程序</span><span class="sxs-lookup"><span data-stu-id="6aa5a-715">URL Protocol Handler</span></span>

-   <span data-ttu-id="6aa5a-716">AppPath</span><span class="sxs-lookup"><span data-stu-id="6aa5a-716">AppPath</span></span>

-   <span data-ttu-id="6aa5a-717">虚拟应用程序</span><span class="sxs-lookup"><span data-stu-id="6aa5a-717">Virtual Application</span></span>

### <span data-ttu-id="6aa5a-718">指向</span><span class="sxs-lookup"><span data-stu-id="6aa5a-718">Shortcuts</span></span>

<span data-ttu-id="6aa5a-719">简短剪切是与操作系统集成的基本元素之一，并且是应用 V 应用程序的直接用户启动接口。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-719">The short cut is one of the basic elements of integration with the OS and is the interface for direct user launch of an App-V application.</span></span> <span data-ttu-id="6aa5a-720">在发布和取消发布 App-v 应用程序期间。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-720">During the publishing and unpublishing of App-V applications.</span></span>

<span data-ttu-id="6aa5a-721">从程序包清单和动态配置 XML 文件中，可以在类似以下内容的部分中找到特定应用程序可执行文件的路径：</span><span class="sxs-lookup"><span data-stu-id="6aa5a-721">From the package manifest and dynamic configuration XML files, the path to a specific application executable can be found in a section similar to the following:</span></span>

```xml
<Extension Category="AppV.Shortcut">
          <Shortcut>
            <File>[{Common Desktop}]\Adobe Reader 9.lnk</File>
            <Target>[{AppVPackageRoot}]\Reader\AcroRd32.exe</Target>
            <Icon>[{Windows}]\Installer\{AC76BA86-7AD7-1033-7B44-A94000000001}\SC_Reader.ico</Icon>
            <Arguments />
            <WorkingDirectory />
            <ShowCommand>1</ShowCommand>
            <ApplicationId>[{AppVPackageRoot}]\Reader\AcroRd32.exe</ApplicationId>
          </Shortcut>
        </Extension>
```

<span data-ttu-id="6aa5a-722">如前面所述，默认情况下，App-v 快捷方式基于刷新操作放置在用户的配置文件中。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-722">As mentioned previously, the App-V shortcuts are placed by default in the user’s profile based on the refresh operation.</span></span> <span data-ttu-id="6aa5a-723">全局刷新将 "所有用户" 配置文件和用户刷新中的快捷方式存储在特定用户的配置文件中。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-723">Global refresh places shortcuts in the All Users profile and user refresh stores them in the specific user’s profile.</span></span> <span data-ttu-id="6aa5a-724">实际可执行文件存储在程序包存储中。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-724">The actual executable is stored in the Package Store.</span></span> <span data-ttu-id="6aa5a-725">.ICO 文件的位置是 App-v 包中已标记的位置。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-725">The location of the ICO file is a tokenized location in the App-V package.</span></span>

### <span data-ttu-id="6aa5a-726">文件类型关联</span><span class="sxs-lookup"><span data-stu-id="6aa5a-726">File type associations</span></span>

<span data-ttu-id="6aa5a-727">App-v 客户端在发布期间管理本地操作系统文件类型关联，这使用户可以使用文件类型调用或打开具有特定注册扩展名（.docx）的文件以启动 app-v 应用程序。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-727">The App-V Client manages the local operating system File Type Associations during publishing, which enables users to use file type invocations or to open a file with a specifically registered extension (.docx) to start an App-V application.</span></span> <span data-ttu-id="6aa5a-728">文件类型关联存在于清单和动态配置文件中，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="6aa5a-728">File type associations are present in the manifest and dynamic configuration files as represented in the example below:</span></span>

```xml
<Extension Category="AppV.FileTypeAssociation">
          <FileTypeAssociation>
            <FileExtension MimeAssociation="true">
              <Name>.xdp</Name>
              <ProgId>AcroExch.XDPDoc</ProgId>
              <ContentType>application/vnd.adobe.xdp+xml</ContentType>
            </FileExtension>
            <ProgId>
              <Name>AcroExch.XDPDoc</Name>
              <Description>Adobe Acrobat XML Data Package File</Description>
              <EditFlags>65536</EditFlags>
              <DefaultIcon>[{Windows}]\Installer\{AC76BA86-7AD7-1033-7B44-A94000000001}\XDPFile_8.ico</DefaultIcon>
              <ShellCommands>
                <DefaultCommand>Read</DefaultCommand>
                <ShellCommand>
                  <ApplicationId>[{AppVPackageRoot}]\Reader\AcroRd32.exe</ApplicationId>
                  <Name>Open</Name>
                  <CommandLine>"[{AppVPackageRoot}]\Reader\AcroRd32.exe" "%1"</CommandLine>
                </ShellCommand>
                <ShellCommand>
                  <ApplicationId>[{AppVPackageRoot}]\Reader\AcroRd32.exe</ApplicationId>
                  <Name>Printto</Name>
                  <CommandLine>"[{AppVPackageRoot}]\Reader\AcroRd32.exe"  /t "%1" "%2" "%3" "%4"</CommandLine>
                </ShellCommand>
                <ShellCommand>
                  <ApplicationId>[{AppVPackageRoot}]\Reader\AcroRd32.exe</ApplicationId>
                  <Name>Read</Name>
                  <FriendlyName>Open with Adobe Reader 9</FriendlyName>
                  <CommandLine>"[{AppVPackageRoot}]\Reader\AcroRd32.exe" "%1"</CommandLine>
                </ShellCommand>
              </ShellCommands>
            </ProgId>
          </FileTypeAssociation>
        </Extension>
```

<span data-ttu-id="6aa5a-729">**注意** 在此示例中：</span><span class="sxs-lookup"><span data-stu-id="6aa5a-729">**Note** In this example:</span></span>

-   `<Name>.xdp</Name>` <span data-ttu-id="6aa5a-730">是分机号</span><span class="sxs-lookup"><span data-stu-id="6aa5a-730">is the extension</span></span>

-   `<Name>AcroExch.XDPDoc</Name>` <span data-ttu-id="6aa5a-731">是 ProgId 值（指向相邻的 ProgId）</span><span class="sxs-lookup"><span data-stu-id="6aa5a-731">is the ProgId value (which points to the adjoining ProgId)</span></span>

-   `<CommandLine>"[{AppVPackageRoot}]\Reader\AcroRd32.exe" "%1"</CommandLine>` <span data-ttu-id="6aa5a-732">是指向应用程序可执行文件的命令行</span><span class="sxs-lookup"><span data-stu-id="6aa5a-732">is the command line, which points to the application executable</span></span>

 

### <span data-ttu-id="6aa5a-733">Shell 扩展</span><span class="sxs-lookup"><span data-stu-id="6aa5a-733">Shell extensions</span></span>

<span data-ttu-id="6aa5a-734">在排序过程中，将自动在程序包中嵌入外壳扩展。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-734">Shell extensions are embedded in the package automatically during the sequencing process.</span></span> <span data-ttu-id="6aa5a-735">当程序包以全局方式发布时，外壳扩展为用户提供与应用程序本地安装相同的功能。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-735">When the package is published globally, the shell extension gives users the same functionality as if the application were locally installed.</span></span> <span data-ttu-id="6aa5a-736">应用程序不需要在客户端上进行额外的设置或配置即可启用外壳扩展功能。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-736">The application requires no additional setup or configuration on the client to enable the shell extension functionality.</span></span>

**<span data-ttu-id="6aa5a-737">使用外壳扩展的要求：</span><span class="sxs-lookup"><span data-stu-id="6aa5a-737">Requirements for using shell extensions:</span></span>**

-   <span data-ttu-id="6aa5a-738">包含嵌入式外壳扩展的软件包必须全局发布。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-738">Packages that contain embedded shell extensions must be published globally.</span></span>

-   <span data-ttu-id="6aa5a-739">应用程序、Sequencer 和 App-v 客户端的 "位数" 必须匹配，否则 shell 扩展将不起作用。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-739">The “bitness” of the application, Sequencer, and App-V client must match, or the shell extensions won’t work.</span></span> <span data-ttu-id="6aa5a-740">例如：</span><span class="sxs-lookup"><span data-stu-id="6aa5a-740">For example:</span></span>

    -   <span data-ttu-id="6aa5a-741">该应用程序的版本为64位。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-741">The version of the application is 64-bit.</span></span>

    -   <span data-ttu-id="6aa5a-742">Sequencer 在64位计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-742">The Sequencer is running on a 64-bit computer.</span></span>

    -   <span data-ttu-id="6aa5a-743">程序包正在发送到64位 App-v 客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-743">The package is being delivered to a 64-bit App-V client computer.</span></span>

<span data-ttu-id="6aa5a-744">下表显示受支持的外壳扩展。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-744">The following table displays the supported shell extensions.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6aa5a-745">函数</span><span class="sxs-lookup"><span data-stu-id="6aa5a-745">Handler</span></span></th>
<th align="left"><span data-ttu-id="6aa5a-746">描述</span><span class="sxs-lookup"><span data-stu-id="6aa5a-746">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6aa5a-747">上下文菜单处理程序</span><span class="sxs-lookup"><span data-stu-id="6aa5a-747">Context menu handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-748">将菜单项添加到上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-748">Adds menu items to the context menu.</span></span> <span data-ttu-id="6aa5a-749">在显示上下文菜单之前调用它。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-749">It is called before the context menu is displayed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6aa5a-750">拖放处理程序</span><span class="sxs-lookup"><span data-stu-id="6aa5a-750">Drag-and-drop handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-751">控制在右键单击拖放的操作，并修改出现的上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-751">Controls the action upon right-click drag-and-drop and modifies the context menu that appears.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6aa5a-752">拖放目标处理程序</span><span class="sxs-lookup"><span data-stu-id="6aa5a-752">Drop target handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-753">控制在将数据对象拖放到放置目标（如文件）上后的操作。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-753">Controls the action after a data object is dragged-and-dropped over a drop target such as a file.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6aa5a-754">数据对象处理程序</span><span class="sxs-lookup"><span data-stu-id="6aa5a-754">Data object handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-755">控制在将文件复制到剪贴板或将其拖放到放置目标上后的操作。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-755">Controls the action after a file is copied to the clipboard or dragged-and-dropped over a drop target.</span></span> <span data-ttu-id="6aa5a-756">它可以向放置目标提供其他剪贴板格式。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-756">It can provide additional clipboard formats to the drop target.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6aa5a-757">属性表处理程序</span><span class="sxs-lookup"><span data-stu-id="6aa5a-757">Property sheet handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-758">将页面替换或添加到对象的 "属性表" 对话框。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-758">Replaces or adds pages to the property sheet dialog box of an object.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6aa5a-759">提示处理程序</span><span class="sxs-lookup"><span data-stu-id="6aa5a-759">Infotip handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-760">允许检索某个项目的标志和信息提示信息，并在鼠标悬停时将其显示在弹出工具提示内。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-760">Allows retrieving flags and infotip information for an item and displaying it inside a popup tooltip upon mouse- hover.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6aa5a-761">列处理程序</span><span class="sxs-lookup"><span data-stu-id="6aa5a-761">Column handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-762">允许在 Windows 资源管理器的 "详细信息" 视图中创建和显示自定义列 <em> </em> 。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-762">Allows creating and displaying custom columns in Windows Explorer <em>Details view</em>.</span></span> <span data-ttu-id="6aa5a-763">它可用于扩展排序和分组。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-763">It can be used to extend sorting and grouping.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6aa5a-764">预览处理程序</span><span class="sxs-lookup"><span data-stu-id="6aa5a-764">Preview handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-765">启用要在 Windows 资源管理器预览窗格中显示的文件的预览。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-765">Enables a preview of a file to be displayed in the Windows Explorer Preview Pane.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="6aa5a-766">COM</span><span class="sxs-lookup"><span data-stu-id="6aa5a-766">COM</span></span>

<span data-ttu-id="6aa5a-767">App-v 客户端支持通过 COM 集成和虚拟化支持发布应用程序。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-767">The App-V Client supports publishing applications with support for COM integration and virtualization.</span></span> <span data-ttu-id="6aa5a-768">COM 集成允许 App-v 客户端在本地操作系统和对象的虚拟化中注册 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-768">COM integration allows the App-V Client to register COM objects on the local operating system and virtualization of the objects.</span></span> <span data-ttu-id="6aa5a-769">出于本文档的目的，COM 对象的集成需要更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-769">For the purposes of this document, the integration of COM objects requires additional detail.</span></span>

<span data-ttu-id="6aa5a-770">App-v 支持将程序包中的 COM 对象注册到具有两种进程类型的本地操作系统：进程外和进程内。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-770">App-V supports registering COM objects from the package to the local operating system with two process types: Out-of-process and in-process.</span></span> <span data-ttu-id="6aa5a-771">注册 COM 对象的操作是通过一个或多个特定 App-v 包（包括已关闭、隔离和集成）的操作模式的组合完成的。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-771">Registering COM objects is accomplished with one or a combination of multiple modes of operation for a specific App-V package that includes off, Isolated, and Integrated.</span></span> <span data-ttu-id="6aa5a-772">已针对进程外或进程内类型配置了集成模式。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-772">The integrated mode is configured for either the out-of-process or in-process type.</span></span> <span data-ttu-id="6aa5a-773">COM 模式和类型的配置是通过动态配置文件（deploymentconfig.xml 或 userconfig.xml）实现的。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-773">Configuration of COM modes and types is accomplished with dynamic configuration files (deploymentconfig.xml or userconfig.xml).</span></span>

<span data-ttu-id="6aa5a-774">有关应用 V 集成的详细信息，请访问： <https://go.microsoft.com/fwlink/?LinkId=392834> 。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-774">Details on App-V integration are available at: <https://go.microsoft.com/fwlink/?LinkId=392834>.</span></span>

### <span data-ttu-id="6aa5a-775">软件客户端和应用程序功能</span><span class="sxs-lookup"><span data-stu-id="6aa5a-775">Software clients and application capabilities</span></span>

<span data-ttu-id="6aa5a-776">App-v 支持特定软件客户端和应用程序功能扩展点，使虚拟化应用程序能够注册到操作系统的软件客户端。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-776">App-V supports specific software clients and application capabilities extension points that enable virtualized applications to be registered with the software client of the operating system.</span></span> <span data-ttu-id="6aa5a-777">这使用户能够为诸如电子邮件、即时消息和媒体播放机之类的操作选择默认程序。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-777">This enables users to select default programs for operations like email, instant messaging, and media player.</span></span> <span data-ttu-id="6aa5a-778">使用设置程序访问和计算机默认值在控制面板中执行此操作，并在清单或动态配置文件中的排序期间进行配置。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-778">This operation is performed in the control panel with the Set Program Access and Computer Defaults, and configured during sequencing in the manifest or dynamic configuration files.</span></span> <span data-ttu-id="6aa5a-779">仅当全局发布 app-v 应用程序时，才支持应用程序功能。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-779">Application capabilities are only supported when the App-V applications are published globally.</span></span>

<span data-ttu-id="6aa5a-780">基于 app-v 的邮件客户端注册软件客户端的示例。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-780">Example of software client registration of an App-V based mail client.</span></span>

```xml
    <SoftwareClients Enabled="true">
      <ClientConfiguration EmailEnabled="true" />
      <Extensions>
        <Extension Category="AppV.SoftwareClient">
          <SoftwareClients>
            <EMail MakeDefault="true">
              <Name>Mozilla Thunderbird</Name>
              <Description>Mozilla Thunderbird</Description>
              <DefaultIcon>[{ProgramFilesX86}]\Mozilla Thunderbird\thunderbird.exe,0</DefaultIcon>
              <InstallationInformation>
                <RegistrationCommands>
                  <Reinstall>"[{ProgramFilesX86}]\Mozilla Thunderbird\uninstall\helper.exe" /SetAsDefaultAppGlobal</Reinstall>
                  <HideIcons>"[{ProgramFilesX86}]\Mozilla Thunderbird\uninstall\helper.exe" /HideShortcuts</HideIcons>
                  <ShowIcons>"[{ProgramFilesX86}]\Mozilla Thunderbird\uninstall\helper.exe" /ShowShortcuts</ShowIcons>
                </RegistrationCommands>
                <IconsVisible>1</IconsVisible>
                <OEMSettings />
              </InstallationInformation>
              <ShellCommands>
                <ApplicationId>[{ProgramFilesX86}]\Mozilla Thunderbird\thunderbird.exe</ApplicationId>
                <Open>"[{ProgramFilesX86}]\Mozilla Thunderbird\thunderbird.exe" -mail</Open>
              </ShellCommands>
              <MAPILibrary>[{ProgramFilesX86}]\Mozilla Thunderbird\mozMapi32_InUse.dll</MAPILibrary>
              <MailToProtocol>
                <Description>Thunderbird URL</Description>
                <EditFlags>2</EditFlags>
                <DefaultIcon>[{ProgramFilesX86}]\Mozilla Thunderbird\thunderbird.exe,0</DefaultIcon>
                <ShellCommands>
                  <ApplicationId>[{ProgramFilesX86}]\Mozilla Thunderbird\thunderbird.exe</ApplicationId>
                  <Open>"[{ProgramFilesX86}]\Mozilla Thunderbird\thunderbird.exe" -osint -compose "%1"</Open>
                </ShellCommands>
              </MailToProtocol>
            </EMail>
          </SoftwareClients>
        </Extension>
      </Extensions>
    </SoftwareClients>
```

<span data-ttu-id="6aa5a-781">**注意** 在此示例中：</span><span class="sxs-lookup"><span data-stu-id="6aa5a-781">**Note** In this example:</span></span>

-   `<ClientConfiguration EmailEnabled="true" />` <span data-ttu-id="6aa5a-782">是集成电子邮件客户端的整体软件客户端设置</span><span class="sxs-lookup"><span data-stu-id="6aa5a-782">is the overall Software Clients setting to integrate Email clients</span></span>

-   `<EMail MakeDefault="true">` <span data-ttu-id="6aa5a-783">用于将特定电子邮件客户端设置为默认电子邮件客户端的标志</span><span class="sxs-lookup"><span data-stu-id="6aa5a-783">is the flag to set a particular Email client as the default Email client</span></span>

-   `<MAPILibrary>[{ProgramFilesX86}]\Mozilla Thunderbird\mozMapi32_InUse.dll</MAPILibrary>` <span data-ttu-id="6aa5a-784">是 MAPI dll 注册</span><span class="sxs-lookup"><span data-stu-id="6aa5a-784">is the MAPI dll registration</span></span>

 

### <span data-ttu-id="6aa5a-785">URL 协议处理程序</span><span class="sxs-lookup"><span data-stu-id="6aa5a-785">URL Protocol handler</span></span>

<span data-ttu-id="6aa5a-786">应用程序并非总是特别称为利用文件类型调用的虚拟化应用程序。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-786">Applications do not always specifically called virtualized applications utilizing file type invocation.</span></span> <span data-ttu-id="6aa5a-787">例如，在支持嵌入 mailto：在文档或网页中的应用程序中，用户单击 mailto： link，预期会获取其注册的邮件客户端。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-787">For, example, in an application that supports embedding a mailto: link inside a document or web page, the user clicks on a mailto: link and expects to get their registered mail client.</span></span> <span data-ttu-id="6aa5a-788">App-v 支持可在每个程序包基础上使用本地操作系统注册的 URL 协议处理程序。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-788">App-V supports URL Protocol handlers that can be registered on a per-package basis with the local operating system.</span></span> <span data-ttu-id="6aa5a-789">在排序期间，URL 协议处理程序将自动添加到程序包。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-789">During sequencing, the URL protocol handlers are automatically added to the package.</span></span>

<span data-ttu-id="6aa5a-790">如果存在多个可以注册特定 URL 协议处理程序的应用程序，则可以利用动态配置文件来修改该行为，并为不应启动的应用程序取消或禁用此功能。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-790">For situations where there is more than one application that could register the specific URL Protocol handler, the dynamic configuration files can be utilized to modify the behavior and suppress or disable this feature for an application that should not be the primary application launched.</span></span>

### <span data-ttu-id="6aa5a-791">AppPath</span><span class="sxs-lookup"><span data-stu-id="6aa5a-791">AppPath</span></span>

<span data-ttu-id="6aa5a-792">AppPath 扩展点支持直接从操作系统调用 App-V 应用程序。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-792">The AppPath extension point supports calling App-V applications directly from the operating system.</span></span> <span data-ttu-id="6aa5a-793">这通常是从 "运行" 或 "开始" 屏幕完成的，具体取决于操作系统，使管理员能够从操作系统命令或脚本中提供对 App-v 应用程序的访问权限，而无需调用可执行文件的特定路径。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-793">This is typically accomplished from the Run or Start Screen, depending on the operating system, which enables administrators to provide access to App-V applications from operating system commands or scripts without calling the specific path to the executable.</span></span> <span data-ttu-id="6aa5a-794">因此，它可以避免在所有系统上修改系统 path 环境变量，因为它在发布过程中完成。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-794">It therefore avoids modifying the system path environment variable on all systems, as it is accomplished during publishing.</span></span>

<span data-ttu-id="6aa5a-795">AppPath 扩展点是在清单或动态配置文件中配置的，并且存储在用户的发布期间的本地计算机上的注册表中。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-795">The AppPath extension point is configured either in the manifest or in the dynamic configuration files and is stored in the registry on the local machine during publishing for the user.</span></span> <span data-ttu-id="6aa5a-796">有关 AppPath 审阅的详细信息： <https://go.microsoft.com/fwlink/?LinkId=392835> 。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-796">For additional information on AppPath review: <https://go.microsoft.com/fwlink/?LinkId=392835>.</span></span>

### <span data-ttu-id="6aa5a-797">虚拟应用程序</span><span class="sxs-lookup"><span data-stu-id="6aa5a-797">Virtual application</span></span>

<span data-ttu-id="6aa5a-798">此子系统提供在排序期间捕获的应用程序列表，这些应用程序通常由其他 App-v 组件使用。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-798">This subsystem provides a list of applications captured during sequencing which is usually consumed by other App-V components.</span></span> <span data-ttu-id="6aa5a-799">可以使用动态配置文件禁用属于特定应用程序的扩展点的集成。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-799">Integration of extension points belonging to a particular application can be disabled using dynamic configuration files.</span></span> <span data-ttu-id="6aa5a-800">例如，如果某个程序包包含两个应用程序，则可以禁用属于一个应用程序的所有扩展点，以便只支持其他应用程序的扩展点的集成。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-800">For example, if a package contains two applications, it is possible to disable all extension points belonging to one application, in order to allow only integration of extension points of other application.</span></span>

### <span data-ttu-id="6aa5a-801">扩展点规则</span><span class="sxs-lookup"><span data-stu-id="6aa5a-801">Extension point rules</span></span>

<span data-ttu-id="6aa5a-802">根据程序包的发布方式，上面介绍的扩展点将集成到操作系统中。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-802">The extension points described above are integrated into the operating system based on how the packages has been published.</span></span> <span data-ttu-id="6aa5a-803">全局发布将扩展点放在公共计算机位置，用户发布在用户位置中放置扩展点。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-803">Global publishing places extension points in public machine locations, where user publishing places extension points in user locations.</span></span> <span data-ttu-id="6aa5a-804">例如，在桌面上创建并在全局上发布的快捷方式将导致快捷方式（%Public%\\Desktop）和注册表数据（HKLM\\Software\\Classes）的文件数据。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-804">For example a shortcut that is created on the desktop and published globally will result in the file data for the shortcut (%Public%\\Desktop) and the registry data (HKLM\\Software\\Classes).</span></span> <span data-ttu-id="6aa5a-805">相同的快捷方式将具有文件数据（%UserProfile%\\Desktop）和注册表数据（HKCU\\Software\\Classes）。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-805">The same shortcut would have file data (%UserProfile%\\Desktop) and registry data (HKCU\\Software\\Classes).</span></span>

<span data-ttu-id="6aa5a-806">扩展点并非全部以相同的方式发布，其中某些扩展点将需要全局发布，而其他扩展点需要在其提供的特定操作系统和体系结构上进行排序。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-806">Extension points are not all published the same way, where some extension points will require global publishing and others require sequencing on the specific operating system and architecture where they are delivered.</span></span> <span data-ttu-id="6aa5a-807">下面是描述这两个键规则的表。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-807">Below is a table that describes these two key rules.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6aa5a-808">虚拟扩展</span><span class="sxs-lookup"><span data-stu-id="6aa5a-808">Virtual Extension</span></span></th>
<th align="left"><span data-ttu-id="6aa5a-809">需要目标操作系统排序</span><span class="sxs-lookup"><span data-stu-id="6aa5a-809">Requires target OS Sequencing</span></span></th>
<th align="left"><span data-ttu-id="6aa5a-810">需要全球发布</span><span class="sxs-lookup"><span data-stu-id="6aa5a-810">Requires Global Publishing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6aa5a-811">快捷方式</span><span class="sxs-lookup"><span data-stu-id="6aa5a-811">Shortcut</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6aa5a-812">文件类型关联</span><span class="sxs-lookup"><span data-stu-id="6aa5a-812">File Type Association</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6aa5a-813">URL 协议</span><span class="sxs-lookup"><span data-stu-id="6aa5a-813">URL Protocols</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-814">X</span><span class="sxs-lookup"><span data-stu-id="6aa5a-814">X</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6aa5a-815">AppPaths</span><span class="sxs-lookup"><span data-stu-id="6aa5a-815">AppPaths</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-816">X</span><span class="sxs-lookup"><span data-stu-id="6aa5a-816">X</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6aa5a-817">COM 模式</span><span class="sxs-lookup"><span data-stu-id="6aa5a-817">COM Mode</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6aa5a-818">软件客户端</span><span class="sxs-lookup"><span data-stu-id="6aa5a-818">Software Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-819">X</span><span class="sxs-lookup"><span data-stu-id="6aa5a-819">X</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6aa5a-820">应用程序功能</span><span class="sxs-lookup"><span data-stu-id="6aa5a-820">Application Capabilities</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-821">X</span><span class="sxs-lookup"><span data-stu-id="6aa5a-821">X</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-822">X</span><span class="sxs-lookup"><span data-stu-id="6aa5a-822">X</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6aa5a-823">上下文菜单处理程序</span><span class="sxs-lookup"><span data-stu-id="6aa5a-823">Context Menu Handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-824">X</span><span class="sxs-lookup"><span data-stu-id="6aa5a-824">X</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-825">X</span><span class="sxs-lookup"><span data-stu-id="6aa5a-825">X</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6aa5a-826">拖放处理程序</span><span class="sxs-lookup"><span data-stu-id="6aa5a-826">Drag-and-drop Handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-827">X</span><span class="sxs-lookup"><span data-stu-id="6aa5a-827">X</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6aa5a-828">数据对象处理程序</span><span class="sxs-lookup"><span data-stu-id="6aa5a-828">Data Object Handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-829">X</span><span class="sxs-lookup"><span data-stu-id="6aa5a-829">X</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6aa5a-830">属性表处理程序</span><span class="sxs-lookup"><span data-stu-id="6aa5a-830">Property Sheet Handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-831">X</span><span class="sxs-lookup"><span data-stu-id="6aa5a-831">X</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6aa5a-832">提示处理程序</span><span class="sxs-lookup"><span data-stu-id="6aa5a-832">Infotip Handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-833">X</span><span class="sxs-lookup"><span data-stu-id="6aa5a-833">X</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6aa5a-834">列处理程序</span><span class="sxs-lookup"><span data-stu-id="6aa5a-834">Column Handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-835">X</span><span class="sxs-lookup"><span data-stu-id="6aa5a-835">X</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6aa5a-836">外壳扩展</span><span class="sxs-lookup"><span data-stu-id="6aa5a-836">Shell Extensions</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-837">X</span><span class="sxs-lookup"><span data-stu-id="6aa5a-837">X</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6aa5a-838">浏览器帮助程序对象</span><span class="sxs-lookup"><span data-stu-id="6aa5a-838">Browser Helper Object</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-839">X</span><span class="sxs-lookup"><span data-stu-id="6aa5a-839">X</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-840">X</span><span class="sxs-lookup"><span data-stu-id="6aa5a-840">X</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6aa5a-841">活动 X 对象</span><span class="sxs-lookup"><span data-stu-id="6aa5a-841">Active X Object</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-842">X</span><span class="sxs-lookup"><span data-stu-id="6aa5a-842">X</span></span></p></td>
<td align="left"><p><span data-ttu-id="6aa5a-843">X</span><span class="sxs-lookup"><span data-stu-id="6aa5a-843">X</span></span></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-dynamic-config"></a><span data-ttu-id="6aa5a-844">动态配置处理</span><span class="sxs-lookup"><span data-stu-id="6aa5a-844">Dynamic configuration processing</span></span>


<span data-ttu-id="6aa5a-845">将 app-v 程序包部署到一个计算机或用户非常简单。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-845">Deploying App-V packages to one machine or user is very simple.</span></span> <span data-ttu-id="6aa5a-846">但是，由于组织跨业务线和地理和政治边界部署 AppV 应用程序，因此使用一组设置的一次对应用程序进行排序的能力就不可能了。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-846">However, as organizations deploy AppV applications across business lines and geographic and political boundaries, the ability to sequence an application one time with one set of settings becomes impossible.</span></span> <span data-ttu-id="6aa5a-847">App-v 是针对此方案而设计的，因为它在清单文件中的排序期间捕获特定的设置和配置，并且还支持动态配置文件的修改。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-847">App-V was designed for this scenario, as it captures specific settings and configurations during sequencing in the Manifest file, but also supports modification with Dynamic Configuration files.</span></span>

<span data-ttu-id="6aa5a-848">App-v 动态配置允许为程序包指定计算机级别或用户级别的策略。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-848">App-V dynamic configuration allows for specifying a policy for a package either at the machine level or at the user level.</span></span> <span data-ttu-id="6aa5a-849">动态配置文件使排序工程师能够修改程序包的配置，以满足单个用户或计算机组的需求。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-849">The Dynamic Configuration files enable sequencing engineers to modify the configuration of a package, post-sequencing, to address the needs of individual groups of users or machines.</span></span> <span data-ttu-id="6aa5a-850">在某些情况下，可能需要对应用程序进行修改才能在 App-v 环境中提供适当的功能。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-850">In some instances it may be necessary to make modifications to the application to provide proper functionality within the App-V environment.</span></span> <span data-ttu-id="6aa5a-851">例如，可能需要对 \ _ \ \* config.xml 文件进行修改，以允许在执行应用程序的指定时间执行某些操作，如禁用 mailto 扩展名以防止虚拟化应用程序覆盖另一个应用程序中的该扩展。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-851">For example, it may be necessary to make modifications to the \_\*config.xml files to allow certain actions to be performed at a specified time during the execution of the application, like disabling a mailto extension to prevent a virtualized application from overwriting that extension from another application.</span></span>

<span data-ttu-id="6aa5a-852">App-v 程序包包含 appv 包文件内的清单文件，它代表排序操作，并且是选择策略，除非将动态配置文件分配给特定程序包。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-852">App-V Packages contain the Manifest file inside of the appv package file, which is representative of sequencing operations and is the policy of choice unless Dynamic Configuration files are assigned to a specific package.</span></span> <span data-ttu-id="6aa5a-853">按顺序排序后，可以修改动态配置文件，以允许将应用程序发布到不同的桌面或具有不同扩展点的用户。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-853">Post-sequencing, the Dynamic Configuration files can be modified to allow the publishing of an application to different desktops or users with different extension points.</span></span> <span data-ttu-id="6aa5a-854">这两个动态配置文件是动态部署配置（DDC）和动态用户配置（DUC）文件。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-854">The two Dynamic Configuration Files are the Dynamic Deployment Configuration (DDC) and Dynamic User Configuration (DUC) files.</span></span> <span data-ttu-id="6aa5a-855">本部分重点介绍清单和动态配置文件的组合。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-855">This section focuses on the combination of the manifest and dynamic configuration files.</span></span>

### <span data-ttu-id="6aa5a-856">动态配置文件示例</span><span class="sxs-lookup"><span data-stu-id="6aa5a-856">Example for dynamic configuration files</span></span>

<span data-ttu-id="6aa5a-857">下面的示例显示了发布后和正常操作期间的清单、部署配置和用户配置文件的组合。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-857">The example below shows the combination of the Manifest, Deployment Configuration and User Configuration files after publishing and during normal operation.</span></span> <span data-ttu-id="6aa5a-858">这些示例是每个文件的缩写示例。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-858">These examples are abbreviated examples of each of the files.</span></span> <span data-ttu-id="6aa5a-859">目的仅显示文件组合，而不是显示每个文件中可用的特定类别的完整说明。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-859">The purpose is show the combination of the files only and not to be a complete description of the specific categories available in each of the files.</span></span> <span data-ttu-id="6aa5a-860">有关详细信息，请查看 app-v 5 排序指南，网址为：</span><span class="sxs-lookup"><span data-stu-id="6aa5a-860">For more information review the App-V 5 Sequencing Guide at:</span></span> <https://go.microsoft.com/fwlink/?LinkID=269810>

**<span data-ttu-id="6aa5a-861">部件</span><span class="sxs-lookup"><span data-stu-id="6aa5a-861">Manifest</span></span>**

```xml
<appv:Extension Category="AppV.Shortcut">
     <appv:Shortcut>
          <appv:File>[{Common Programs}]\7-Zip\7-Zip File Manager.lnk</appv:File>
          <appv:Target>[{AppVPackageRoot}]\7zFM.exe</appv:Target>
          <appv:Icon>[{AppVPackageRoot}]\7zFM exe.O.ico</appv:Icon>
     </appv:Shortcut>
</appv:Extension>
```

**<span data-ttu-id="6aa5a-862">部署配置</span><span class="sxs-lookup"><span data-stu-id="6aa5a-862">Deployment Configuration</span></span>**

```xml
<MachineConfiguration>
     <Subsystems>
          <Registry>
               <Include>
                    <Key Path= "\REGISTRY\Machine\Software\7zip">
                    <Value Type="REG_SZ" Name="Config" Data="1234"/>
                    </Key>
               </Include>
          </Registry>
     </Subsystems>
```

**<span data-ttu-id="6aa5a-863">用户配置</span><span class="sxs-lookup"><span data-stu-id="6aa5a-863">User Configuration</span></span>**

```xml
<UserConfiguration>
     <Subsystems>
<appv:ExtensionCategory="AppV.Shortcut">
     <appv:Shortcut>
          <appv:File>[{Desktop}]\7-Zip\7-Zip File Manager.lnk</appv:File>
          <appv:Target>[{AppVPackageRoot}]\7zFM.exe</appv:Target>
          <appv:Icon>[{AppVPackageRoot}]\7zFM exe.O.ico</appv:Icon>
     </appv:Shortcut>
</appv:Extension>
     </Subsystems>
<UserConfiguration>
     <Subsystems>
<appv:Extension Category="AppV.Shortcut">
     <appv:Shortcut>
          <appv:Fìle>[{Desktop}]\7-Zip\7-Zip File Manager.lnk</appv:File>
          <appv:Target>[{AppVPackageRoot}]\7zFM.exe</appv:Target>
          <appv:Icon>[{AppVPackageRoot}]\7zFM.exe.O.ico</appv:Icon>
     </appv:Shortcut>
     <appv:Shortcut>
          <appv:File>[{Common Programs}]\7-Zip\7-Zip File Manager.Ink</appv:File>
          <appv:Target>[{AppVPackageRoot}]\7zFM.exe</appv:Target>
          <appv:Icon>[{AppVPackageRoot)]\7zFM.exe.O.ico</appv: Icon>
     </appv:Shortcut>
</appv:Extension>
     </Subsystems>
<MachineConfiguration>
     <Subsystems>
          <Registry>
               <Include>
                    <Key Path="\REGISTRY\Machine\Software\7zip">
                    <Value Type=”REG_SZ" Name="Config" Data="1234"/>
               </Include>
          </Registry>
     </Subsystems>
```

## <a href="" id="bkmk-sidebyside-assemblies"></a><span data-ttu-id="6aa5a-864">并行程序集</span><span class="sxs-lookup"><span data-stu-id="6aa5a-864">Side-by-side assemblies</span></span>


<span data-ttu-id="6aa5a-865">在虚拟应用程序发布期间，app-v 支持在客户端上的排序和部署期间自动打包并行（SxS）程序集。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-865">App-V supports the automatic packaging of side-by-side (SxS) assemblies during sequencing and deployment on the client during virtual application publishing.</span></span> <span data-ttu-id="6aa5a-866">应用程序-V 5 SP2 支持捕获 SxS 程序集，在对排序计算机上不存在的程序集进行排序。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-866">App-V 5 SP2 supports capturing SxS assemblies during sequencing for assemblies not present on the sequencing machine.</span></span> <span data-ttu-id="6aa5a-867">对于包含 Visual c + + （版本8和更高版本）和/或 MSXML 运行时的程序集，Sequencer 将自动检测和捕获这些依赖关系，即使它们未在监视期间安装。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-867">And for assemblies consisting of Visual C++ (Version 8 and newer) and/or MSXML run-time, the Sequencer will automatically detect and capture these dependencies even if they were not installed during monitoring.</span></span> <span data-ttu-id="6aa5a-868">并列程序集功能消除了以前版本的 App-v 的限制，其中，app-v Sequencer 未捕获序列化工作站上已存在的程序集，并 privatizing 每个程序包限制为一个位版本的程序集。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-868">The Side by Side assemblies feature removes the limitations of previous versions of App-V, where the App-V Sequencer did not capture assemblies already present on the sequencing workstation, and privatizing the assemblies which limited to one bit version per package.</span></span> <span data-ttu-id="6aa5a-869">此行为导致将应用 V 应用程序部署到缺少所需的 SxS 程序集的客户端，从而导致应用程序启动失败。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-869">This behavior resulted in deployed App-V applications to clients missing the required SxS assemblies, causing application launch failures.</span></span> <span data-ttu-id="6aa5a-870">这会强制打包过程进行记录，然后确保程序包所需的所有程序集都在用户的客户端操作系统上本地安装，以确保支持虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-870">This forced the packaging process to document and then ensure that all assemblies required for packages were locally installed on the user’s client operating system to ensure support for the virtual applications.</span></span> <span data-ttu-id="6aa5a-871">根据程序集的数量以及缺少所需依赖关系的应用程序文档，此任务既是管理和实施挑战。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-871">Based on the number of assemblies and the lack of application documentation for the required dependencies, this task was both a management and implementation challenge.</span></span>

<span data-ttu-id="6aa5a-872">App-v 中的并行程序集支持具有以下功能。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-872">Side by Side Assembly support in App-V has the following features.</span></span>

-   <span data-ttu-id="6aa5a-873">排序期间的 SxS 程序集的自动捕获，无论是否已在排序工作站上安装了程序集。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-873">Automatic captures of SxS assembly during Sequencing, regardless of whether the assembly was already installed on the sequencing workstation.</span></span>

-   <span data-ttu-id="6aa5a-874">当发布时，app-v 客户端将在发布时自动在客户端计算机上安装所需的 SxS 程序集。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-874">The App-V Client automatically installs required SxS assemblies to the client computer at publishing time when they are not present.</span></span>

-   <span data-ttu-id="6aa5a-875">Sequencer 在 Sequencer 报告机制中报告 VC 运行时依赖关系。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-875">The Sequencer reports the VC run-time dependency in Sequencer reporting mechanism.</span></span>

-   <span data-ttu-id="6aa5a-876">Sequencer 允许选择不打包已安装在 Sequencer 上的程序集，支持在目标计算机上已安装这些程序集的方案。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-876">The Sequencer allows opting to not package the assemblies that are already installed on the Sequencer, supporting scenarios where the assemblies have previously been installed on the target computers.</span></span>

### <span data-ttu-id="6aa5a-877">自动发布 SxS 程序集</span><span class="sxs-lookup"><span data-stu-id="6aa5a-877">Automatic publishing of SxS assemblies</span></span>

<span data-ttu-id="6aa5a-878">在使用 SxS 程序集发布 app-v 程序包的过程中，app-v 客户端将检查计算机上是否存在该程序集。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-878">During publishing of an App-V package with SxS assemblies the App-V Client will check for the presence of the assembly on the machine.</span></span> <span data-ttu-id="6aa5a-879">如果该程序集不存在，客户端会将该程序集部署到该计算机。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-879">If the assembly does not exist, the client will deploy the assembly to the machine.</span></span> <span data-ttu-id="6aa5a-880">作为连接组一部分的程序包将依赖于属于基本程序包的并列程序集安装，因为连接组不包含有关程序集安装的任何信息。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-880">Packages that are part of connection groups will rely on the Side by Side assembly installations that are part of the base packages, as the connection group does not contain any information about assembly installation.</span></span>

<span data-ttu-id="6aa5a-881">**注意** 使用程序集取消发布或删除程序包不会删除该程序包的程序集。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-881">**Note** UnPublishing or removing a package with an assembly does not remove the assemblies for that package.</span></span>

 

## <a href="" id="bkmk-client-logging"></a><span data-ttu-id="6aa5a-882">客户端日志记录</span><span class="sxs-lookup"><span data-stu-id="6aa5a-882">Client logging</span></span>


<span data-ttu-id="6aa5a-883">App-v 客户端将信息记录到标准 ETW 格式的 Windows 事件日志中。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-883">The App-V client logs information to the Windows Event log in standard ETW format.</span></span> <span data-ttu-id="6aa5a-884">可以在事件查看器中的 "应用程序和服务" Logs\\Microsoft\\AppV\\Client. 下找到特定的 App-v 事件。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-884">The specific App-V events can be found in the event viewer, under Applications and Services Logs\\Microsoft\\AppV\\Client.</span></span>

<span data-ttu-id="6aa5a-885">**注意** 在 App-v 5.0 SP3 中，某些日志已合并并移动到以下位置：</span><span class="sxs-lookup"><span data-stu-id="6aa5a-885">**Note** In App-V 5.0 SP3, some logs have been consolidated and moved to the following location:</span></span>

`Event logs/Applications and Services Logs/Microsoft/AppV/ServiceLog`

<span data-ttu-id="6aa5a-886">有关已移动日志的列表，请参阅[关于 App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-event-logs-moved)。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-886">For a list of the moved logs, see [About App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-event-logs-moved).</span></span>

 

<span data-ttu-id="6aa5a-887">下面介绍了三种特定类别的事件记录。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-887">There are three specific categories of events recorded described below.</span></span>

<span data-ttu-id="6aa5a-888">**管理员**：记录适用于 App-v 客户端的配置的事件，并包含主警告和错误。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-888">**Admin**: Logs events for configurations being applied to the App-V Client, and contains the primary warnings and errors.</span></span>

<span data-ttu-id="6aa5a-889">可**操作**：记录单个组件的常规 app-v 执行和使用情况创建已在 App-v 客户端上完成的 app-v 操作的审核日志。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-889">**Operational**: Logs the general App-V execution and usage of individual components creating an audit log of the App-V operations that have been completed on the App-V Client.</span></span>

<span data-ttu-id="6aa5a-890">**虚拟应用程序**：日志虚拟应用程序启动和使用虚拟化子系统。</span><span class="sxs-lookup"><span data-stu-id="6aa5a-890">**Virtual Application**: Logs virtual application launches and use of virtualization subsystems.</span></span>






 

 





