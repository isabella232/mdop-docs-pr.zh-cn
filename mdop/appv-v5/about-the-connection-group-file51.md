---
title: 关于连接组文件
description: 关于连接组文件
author: dansimp
ms.assetid: 1f4df515-f5f6-4b58-91a8-c71598cb3ea4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 31ef9dc9c4465ed8f261b73518348c05ceb78d15
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798668"
---
# <span data-ttu-id="bb800-103">关于连接组文件</span><span class="sxs-lookup"><span data-stu-id="bb800-103">About the Connection Group File</span></span>


**<span data-ttu-id="bb800-104">本主题内容：</span><span class="sxs-lookup"><span data-stu-id="bb800-104">In this topic:</span></span>**

-   [<span data-ttu-id="bb800-105">连接组文件用途和位置</span><span class="sxs-lookup"><span data-stu-id="bb800-105">Connection group file purpose and location</span></span>](#bkmk-cg-purpose-loc)

-   [<span data-ttu-id="bb800-106">连接组 XML 文件的结构</span><span class="sxs-lookup"><span data-stu-id="bb800-106">Structure of the connection group XML file</span></span>](#bkmk-define-cg-5-0sp3)

-   [<span data-ttu-id="bb800-107">在连接组中配置程序包的优先级</span><span class="sxs-lookup"><span data-stu-id="bb800-107">Configuring the priority of packages in a connection group</span></span>](#bkmk-config-pkg-priority-incg)

-   [<span data-ttu-id="bb800-108">支持的虚拟应用程序连接配置</span><span class="sxs-lookup"><span data-stu-id="bb800-108">Supported virtual application connection configurations</span></span>](#bkmk-va-conn-configs)

## <a href="" id="bkmk-cg-purpose-loc"></a><span data-ttu-id="bb800-109">连接组文件用途和位置</span><span class="sxs-lookup"><span data-stu-id="bb800-109">Connection group file purpose and location</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bb800-110">连接组用途</span><span class="sxs-lookup"><span data-stu-id="bb800-110">Connection group purpose</span></span></p></td>
<td align="left"><p><span data-ttu-id="bb800-111">连接组是一种 App-v 功能，使你能够将程序包组合在一起以创建虚拟环境，这些程序包中的应用程序可以在其中相互交互。</span><span class="sxs-lookup"><span data-stu-id="bb800-111">A connection group is an App-V feature that enables you to group packages together to create a virtual environment in which the applications in those packages can interact with each other.</span></span></p>
<p><span data-ttu-id="bb800-112">示例：您希望将插件与 Microsoft Office 配合使用。</span><span class="sxs-lookup"><span data-stu-id="bb800-112">Example: You want to use plug-ins with Microsoft Office.</span></span> <span data-ttu-id="bb800-113">你可以创建包含插件的程序包，并创建包含 Office 的另一个程序包，然后将这两个程序包添加到连接组，以使 Office 能够使用这些插件。</span><span class="sxs-lookup"><span data-stu-id="bb800-113">You can create a package that contains the plug-ins, and create another package that contains Office, and then add both packages to a connection group to enable Office to use those plug-ins.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bb800-114">连接组文件的工作原理</span><span class="sxs-lookup"><span data-stu-id="bb800-114">How the connection group file works</span></span></p></td>
<td align="left"><p><span data-ttu-id="bb800-115">当应用 app-v 5.1 连接组文件时，文件中枚举的程序包将在运行时合并到单个虚拟环境中。</span><span class="sxs-lookup"><span data-stu-id="bb800-115">When you apply an App-V 5.1 connection group file, the packages that are enumerated in the file will be combined at runtime into a single virtual environment.</span></span> <span data-ttu-id="bb800-116">使用 Microsoft Application Virtualization （App-v）5.1 连接组文件配置现有的 App-v 5.1 连接组。</span><span class="sxs-lookup"><span data-stu-id="bb800-116">Use the Microsoft Application Virtualization (App-V) 5.1 connection group file to configure existing App-V 5.1 connection groups.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bb800-117">示例文件路径</span><span class="sxs-lookup"><span data-stu-id="bb800-117">Example file path</span></span></p></td>
<td align="left"><p><span data-ttu-id="bb800-118">%APPDATA%\Microsoft\AppV\Client\Catalog\PackageGroups {6CCC7575-162E-4152-9407-ED411DA138F4} {4D1E16E1-8EF8-41ED-92D5-8910A8527F96}。</span><span class="sxs-lookup"><span data-stu-id="bb800-118">%APPDATA%\Microsoft\AppV\Client\Catalog\PackageGroups{6CCC7575-162E-4152-9407-ED411DA138F4}{4D1E16E1-8EF8-41ED-92D5-8910A8527F96}.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-define-cg-5-0sp3"></a><span data-ttu-id="bb800-119">连接组 XML 文件的结构</span><span class="sxs-lookup"><span data-stu-id="bb800-119">Structure of the connection group XML file</span></span>


**<span data-ttu-id="bb800-120">本节内容：</span><span class="sxs-lookup"><span data-stu-id="bb800-120">In this section:</span></span>**

-   [<span data-ttu-id="bb800-121">定义连接组的参数</span><span class="sxs-lookup"><span data-stu-id="bb800-121">Parameters that define the connection group</span></span>](#bkmk-params-define-cg)

-   [<span data-ttu-id="bb800-122">用于定义连接组中的程序包的参数</span><span class="sxs-lookup"><span data-stu-id="bb800-122">Parameters that define the packages in the connection group</span></span>](#bkmk-params-define-pkgs-incg)

-   [<span data-ttu-id="bb800-123">App-v 示例连接组 XML 文件</span><span class="sxs-lookup"><span data-stu-id="bb800-123">App-V example connection group XML file</span></span>](#bkmk-50sp3-exp-cg-xml)

-   [<span data-ttu-id="bb800-124">App-v 5.0 至 App-V 5.0 SP2 示例连接组 XML 文件</span><span class="sxs-lookup"><span data-stu-id="bb800-124">App-V 5.0 through App-V 5.0 SP2 example connection group XML file</span></span>](#bkmk-50thru50sp2-exp-cg-xm)

### <a href="" id="bkmk-params-define-cg"></a><span data-ttu-id="bb800-125">定义连接组的参数</span><span class="sxs-lookup"><span data-stu-id="bb800-125">Parameters that define the connection group</span></span>

<span data-ttu-id="bb800-126">下表介绍了定义连接组本身的 XML 文件中的参数，而不是程序包。</span><span class="sxs-lookup"><span data-stu-id="bb800-126">The following table describes the parameters in the XML file that define the connection group itself, not the packages.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bb800-127">字段</span><span class="sxs-lookup"><span data-stu-id="bb800-127">Field</span></span></th>
<th align="left"><span data-ttu-id="bb800-128">描述</span><span class="sxs-lookup"><span data-stu-id="bb800-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bb800-129">架构名称</span><span class="sxs-lookup"><span data-stu-id="bb800-129">Schema name</span></span></p></td>
<td align="left"><p><span data-ttu-id="bb800-130">架构的名称。</span><span class="sxs-lookup"><span data-stu-id="bb800-130">Name of the schema.</span></span></p>
<p><strong><span data-ttu-id="bb800-131">适用于 app-v 5.0 SP3 </strong> 的入门：如果要使用此表中所述的新 "可选程序包" 和 "使用任何版本" 功能，必须在 XML 文件中指定以下架构：</span><span class="sxs-lookup"><span data-stu-id="bb800-131">Applicable starting in App-V 5.0 SP3</strong>: If you want to use the new “optional packages” and “use any version” features that are described in this table, you must specify the following schema in the XML file:</span></span></p>
<p><code>xmlns=&quot;<a href="https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup&amp;quot" data-raw-source="https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup&amp;quot">https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup&quot</a>;</code></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bb800-132">AppConnectionGroupId</span><span class="sxs-lookup"><span data-stu-id="bb800-132">AppConnectionGroupId</span></span></p></td>
<td align="left"><p><span data-ttu-id="bb800-133">此连接组的唯一 GUID 标识符。</span><span class="sxs-lookup"><span data-stu-id="bb800-133">Unique GUID identifier for this connection group.</span></span> <span data-ttu-id="bb800-134">连接组状态与此标识符相关联。</span><span class="sxs-lookup"><span data-stu-id="bb800-134">The connection group state is associated with this identifier.</span></span> <span data-ttu-id="bb800-135">仅在创建连接组时指定此标识符。</span><span class="sxs-lookup"><span data-stu-id="bb800-135">Specify this identifier only when you create the connection group.</span></span></p>
<p><span data-ttu-id="bb800-136">你可以通过键入：来创建新的 GUID <strong>[Guid]::NewGuid()</strong> 。</span><span class="sxs-lookup"><span data-stu-id="bb800-136">You can create a new GUID by typing: <strong>[Guid]::NewGuid()</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bb800-137">VersionId</span><span class="sxs-lookup"><span data-stu-id="bb800-137">VersionId</span></span></p></td>
<td align="left"><p><span data-ttu-id="bb800-138">此版本的连接组的版本 GUID 标识符。</span><span class="sxs-lookup"><span data-stu-id="bb800-138">Version GUID identifier for this version of the connection group.</span></span></p>
<p><span data-ttu-id="bb800-139">更新连接组（例如，通过添加或更新新程序包）时，必须更新版本 GUID 以反映新版本。</span><span class="sxs-lookup"><span data-stu-id="bb800-139">When you update a connection group (for example, by adding or updating a new package), you must update the version GUID to reflect the new version.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bb800-140">DisplayName</span><span class="sxs-lookup"><span data-stu-id="bb800-140">DisplayName</span></span></p></td>
<td align="left"><p><span data-ttu-id="bb800-141">连接组的显示名称。</span><span class="sxs-lookup"><span data-stu-id="bb800-141">Display name of the connection group.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bb800-142">优先级</span><span class="sxs-lookup"><span data-stu-id="bb800-142">Priority</span></span></p></td>
<td align="left"><p><span data-ttu-id="bb800-143">连接组的 "可选优先级" 字段。</span><span class="sxs-lookup"><span data-stu-id="bb800-143">Optional priority field for the connection group.</span></span></p>
<p><strong><span data-ttu-id="bb800-144">"0" </strong> - 表示最高优先级。</span><span class="sxs-lookup"><span data-stu-id="bb800-144">“0”</strong> - indicates the highest priority.</span></span></p>
<p><span data-ttu-id="bb800-145">如果需要优先级，但尚未配置，程序包将失败，因为无法确定要使用的正确连接组。</span><span class="sxs-lookup"><span data-stu-id="bb800-145">If a priority is required, but has not been configured, the package will fail because the correct connection group to use cannot be determined.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="bkmk-params-define-pkgs-incg"></a><span data-ttu-id="bb800-146">用于定义连接组中的程序包的参数</span><span class="sxs-lookup"><span data-stu-id="bb800-146">Parameters that define the packages in the connection group</span></span>

<span data-ttu-id="bb800-147">在 &lt; &gt; 连接组 XML 文件的 "程序包" 部分中，通过指定每个程序包的唯一程序包标识符和版本标识符来列出连接组中的成员包，如下表中所述。</span><span class="sxs-lookup"><span data-stu-id="bb800-147">In the &lt;Packages&gt; section of the connection group XML file, you list the member packages in the connection group by specifying each package’s unique package identifier and version identifier, as described in the following table.</span></span> <span data-ttu-id="bb800-148">列表中的第一个包具有最高优先级。</span><span class="sxs-lookup"><span data-stu-id="bb800-148">The first package in the list has the highest precedence.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bb800-149">字段</span><span class="sxs-lookup"><span data-stu-id="bb800-149">Field</span></span></th>
<th align="left"><span data-ttu-id="bb800-150">描述</span><span class="sxs-lookup"><span data-stu-id="bb800-150">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bb800-151">PackageId</span><span class="sxs-lookup"><span data-stu-id="bb800-151">PackageId</span></span></p></td>
<td align="left"><p><span data-ttu-id="bb800-152">此程序包的唯一 GUID 标识符。</span><span class="sxs-lookup"><span data-stu-id="bb800-152">Unique GUID identifier for this package.</span></span> <span data-ttu-id="bb800-153">发布程序包的较新版本时，此 GUID 不会更改。</span><span class="sxs-lookup"><span data-stu-id="bb800-153">This GUID doesn’t change when newer versions of the package are published.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bb800-154">VersionId</span><span class="sxs-lookup"><span data-stu-id="bb800-154">VersionId</span></span></p></td>
<td align="left"><p><span data-ttu-id="bb800-155">程序包版本的唯一 GUID 标识符。</span><span class="sxs-lookup"><span data-stu-id="bb800-155">Unique GUID identifier for the version of the package.</span></span></p>
<p><strong><span data-ttu-id="bb800-156">适用于 app-v 5.0 SP3 的入门 </strong> ：如果 <strong> 为程序包版本指定 "\*" </strong> ，则会动态插入最新可用程序包版本的 GUID。</span><span class="sxs-lookup"><span data-stu-id="bb800-156">Applicable starting in App-V 5.0 SP3</strong>: If you specify <strong>“\*”</strong> for the package version, the GUID of the latest available package version is dynamically inserted.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bb800-157">IsOptional</span><span class="sxs-lookup"><span data-stu-id="bb800-157">IsOptional</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="bb800-158">适用于从 app-v 5.0 SP3 </strong> ：参数，使你能够在连接组中使程序包可选。</span><span class="sxs-lookup"><span data-stu-id="bb800-158">Applicable starting in App-V 5.0 SP3</strong>: Parameter that enables you to make a package optional within the connection group.</span></span> <span data-ttu-id="bb800-159">有效条目为：</span><span class="sxs-lookup"><span data-stu-id="bb800-159">Valid entries are:</span></span></p>
<ul>
<li><p><strong><span data-ttu-id="bb800-160">"true" </strong> –程序包在连接组中是可选的</span><span class="sxs-lookup"><span data-stu-id="bb800-160">“true”</strong> – package is optional in the connection group</span></span></p></li>
<li><p><strong><span data-ttu-id="bb800-161">"false" </strong> –程序包在连接组中是必需的</span><span class="sxs-lookup"><span data-stu-id="bb800-161">“false”</strong> – package is required in the connection group</span></span></p></li>
</ul>
<p><span data-ttu-id="bb800-162">了解 <a href="how-to-use-optional-packages-in-connection-groups51.md" data-raw-source="[How to Use Optional Packages in Connection Groups](how-to-use-optional-packages-in-connection-groups51.md)"> 如何在连接组中使用可选程序包 </a> 。</span><span class="sxs-lookup"><span data-stu-id="bb800-162">See <a href="how-to-use-optional-packages-in-connection-groups51.md" data-raw-source="[How to Use Optional Packages in Connection Groups](how-to-use-optional-packages-in-connection-groups51.md)">How to Use Optional Packages in Connection Groups</a>.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="bkmk-50sp3-exp-cg-xml"></a><span data-ttu-id="bb800-163">App-v 示例连接组 XML 文件</span><span class="sxs-lookup"><span data-stu-id="bb800-163">App-V example connection group XML file</span></span>

<span data-ttu-id="bb800-164">以下示例连接组 XML 文件显示了上表中的字段示例，并突出显示了从 App-v 5.0 SP3 开始的新项。</span><span class="sxs-lookup"><span data-stu-id="bb800-164">The following example connection group XML file shows examples of the fields in the previous tables and highlights the items that are new starting in App-V 5.0 SP3.</span></span>

```XML
<?xml version="1.0" encoding="UTF-16">
<appv:AppConnectionGroup 
  xmlns="https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup"
  xmlns:appv="https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup"  
  AppConnectionGroupId="61BE9B14-D2B4-41CE-A6E3-A1B658DE7000"
  VersionId="E6B6AA57-F2A7-49C9-ADF8-F2B5B3C8A42F"
  Priority="0"  
  DisplayName="Sample Connection Group">
  <appv:Packages>    
    <appv:Package
      PackageId="1DC709C8-309F-4AB4-BD47-F75926D04276"
      VersionId="*"
      IsOptional="true"    
    />
    <appv:Package
      PackageId="04220DCA-EE77-42BE-A9F5-96FD8E8593F2"
      VersionId="E15EFFE9-043D-4C01-BC52-AD2BD1E8BAFA"
      IsOptional="false"    
    />  
  </appv:Packages>
</appv:AppConnectionGroup>
```

### <a href="" id="bkmk-50thru50sp2-exp-cg-xm"></a><span data-ttu-id="bb800-165">App-v 5.0 至 App-V 5.0 SP2 示例连接组 XML 文件</span><span class="sxs-lookup"><span data-stu-id="bb800-165">App-V 5.0 through App-V 5.0 SP2 example connection group XML file</span></span>

<span data-ttu-id="bb800-166">以下示例连接组 XML 文件适用于 app-v 5.0 （app-v 5.0 SP2）。</span><span class="sxs-lookup"><span data-stu-id="bb800-166">The following example connection group XML file applies to App-V 5.0 through App-V 5.0 SP2.</span></span> <span data-ttu-id="bb800-167">它显示了上表中字段的示例，但它不包括上述对 App-v 5.0 SP3 所述的更改。</span><span class="sxs-lookup"><span data-stu-id="bb800-167">It shows examples of the fields in the previous table, but it excludes the changes described above for App-V 5.0 SP3.</span></span>

```XML
<?xml version="1.0" encoding="UTF-16">
<appv:AppConnectionGroup
  xmlns="https://schemas.microsoft.com/appv/2010/virtualapplicationconnectiongroup"
  xmlns:appv="https://schemas.microsoft.com/appv/2010/virtualapplicationconnectiongroup"
  AppConnectionGroupId="61BE9B14-D2B4-41CE-A6E3-A1B658DE7000"
  VersionId="E6B6AA57-F2A7-49C9-ADF8-F2B5B3C8A42F"
  Priority="0"
  DisplayName="Sample Connection Group">
  <appv:Packages>
    <appv:Package
      PackageId="1DC709C8-309F-4AB4-BD47-F75926D04276"
      VersionId="C7DF4F63-5288-439C-ACEF-EF06BF401EC5"
    />
    <appv:Package
     PackageId="04220DCA-EE77-42BE-A9F5-96FD8E8593F2"
     VersionId="E15EFFE9-043D-4C01-BC52-AD2BD1E8BAFA"
   />
 </appv:Packages>
<appv:AppConnectionGroup>
```

## <a href="" id="bkmk-config-pkg-priority-incg"></a><span data-ttu-id="bb800-168">在连接组中配置程序包的优先级</span><span class="sxs-lookup"><span data-stu-id="bb800-168">Configuring the priority of packages in a connection group</span></span>


<span data-ttu-id="bb800-169">使用程序包列表顺序配置程序包优先级。</span><span class="sxs-lookup"><span data-stu-id="bb800-169">Package precedence is configured using the package list order.</span></span> <span data-ttu-id="bb800-170">文档中的第一个程序包具有最高优先级。</span><span class="sxs-lookup"><span data-stu-id="bb800-170">The first package in the document has the highest precedence.</span></span> <span data-ttu-id="bb800-171">列表中的后续程序包具有降序优先级。</span><span class="sxs-lookup"><span data-stu-id="bb800-171">Subsequent packages in the list have descending priority.</span></span>

<span data-ttu-id="bb800-172">程序包优先级是在虚拟环境初始化期间因不可避免的资源冲突的解决方案。</span><span class="sxs-lookup"><span data-stu-id="bb800-172">Package precedence is the resolution for otherwise inevitable resource collisions during virtual environment initialization.</span></span> <span data-ttu-id="bb800-173">例如，如果在同一虚拟环境中打开的两个程序包定义了相同的注册表 DWORD 值，则具有最高优先级的程序包将确定设置的值。</span><span class="sxs-lookup"><span data-stu-id="bb800-173">For example, if two packages that are opening in the same virtual environment define the same registry DWORD value, the package with the highest precedence determines the value that is set.</span></span>

<span data-ttu-id="bb800-174">你可以使用连接组文件通过以下方法配置每个连接组：</span><span class="sxs-lookup"><span data-stu-id="bb800-174">You can use the connection group file to configure each connection group by using the following methods:</span></span>

-   <span data-ttu-id="bb800-175">指定连接组的运行时优先级。</span><span class="sxs-lookup"><span data-stu-id="bb800-175">Specify runtime priorities for connection groups.</span></span> <span data-ttu-id="bb800-176">若要使用 App-v 管理控制台编辑优先级，请单击连接组，然后单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="bb800-176">To edit priority by using the App-V Management Console, click the connection group and then click **Edit**.</span></span>

    <span data-ttu-id="bb800-177">**注意** 只有当程序包与多个连接组关联时，才需要优先级。</span><span class="sxs-lookup"><span data-stu-id="bb800-177">**Note** Priority is required only if the package is associated with more than one connection group.</span></span>

     

-   <span data-ttu-id="bb800-178">在连接组中指定程序包优先级。</span><span class="sxs-lookup"><span data-stu-id="bb800-178">Specify package precedence within the connection group.</span></span>

<span data-ttu-id="bb800-179">当正在运行的虚拟应用程序从本机应用程序请求（例如 Microsoft Windows 资源管理器）启动时，"优先级" 字段是必需的。</span><span class="sxs-lookup"><span data-stu-id="bb800-179">The priority field is required when a running virtual application initiates from a native application request, for example, Microsoft Windows Explorer.</span></span> <span data-ttu-id="bb800-180">App-v 客户端使用优先级确定应用程序应在哪个连接组虚拟环境中运行。</span><span class="sxs-lookup"><span data-stu-id="bb800-180">The App-V client uses the priority to determine which connection group virtual environment the application should run in.</span></span> <span data-ttu-id="bb800-181">如果虚拟应用程序是多个连接组的一部分，则会出现此情况。</span><span class="sxs-lookup"><span data-stu-id="bb800-181">This situation occurs if a virtual application is part of multiple connection groups.</span></span>

<span data-ttu-id="bb800-182">如果使用另一个虚拟应用程序打开虚拟应用程序，将使用原始虚拟应用程序的虚拟环境。</span><span class="sxs-lookup"><span data-stu-id="bb800-182">If a virtual application is opened using another virtual application the virtual environment of the original virtual application will be used.</span></span> <span data-ttu-id="bb800-183">在此情况下不使用 "优先级" 字段。</span><span class="sxs-lookup"><span data-stu-id="bb800-183">The priority field is not used in this case.</span></span>

**<span data-ttu-id="bb800-184">示例：</span><span class="sxs-lookup"><span data-stu-id="bb800-184">Example:</span></span>**

<span data-ttu-id="bb800-185">Microsoft Outlook 正在虚拟环境**XYZ**中运行的虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="bb800-185">The virtual application Microsoft Outlook is running in virtual environment **XYZ**.</span></span> <span data-ttu-id="bb800-186">打开附加的 Microsoft Word 文档时，Microsoft Word 将在虚拟环境**XYZ**中打开，无论虚拟化 Microsoft word 的关联连接组或运行时优先级。</span><span class="sxs-lookup"><span data-stu-id="bb800-186">When you open an attached Microsoft Word document, a virtualized version Microsoft Word opens in the virtual environment **XYZ**, regardless of the virtualized Microsoft Word’s associated connection groups or runtime priorities.</span></span>

## <a href="" id="bkmk-va-conn-configs"></a><span data-ttu-id="bb800-187">支持的虚拟应用程序连接配置</span><span class="sxs-lookup"><span data-stu-id="bb800-187">Supported virtual application connection configurations</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bb800-188">配置</span><span class="sxs-lookup"><span data-stu-id="bb800-188">Configuration</span></span></th>
<th align="left"><span data-ttu-id="bb800-189">示例方案</span><span class="sxs-lookup"><span data-stu-id="bb800-189">Example scenario</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bb800-190">对.</span><span class="sxs-lookup"><span data-stu-id="bb800-190">An.</span></span> <span data-ttu-id="bb800-191">exe 文件和插件（.dll）</span><span class="sxs-lookup"><span data-stu-id="bb800-191">exe file and plug-in (.dll)</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="bb800-192">你希望将 Microsoft Office 分发给所有用户，但仅将 Microsoft Excel 插件分发给用户的子集。</span><span class="sxs-lookup"><span data-stu-id="bb800-192">You want to distribute Microsoft Office to all users, but distribute a Microsoft Excel plug-in to only a subset of users.</span></span></p></li>
<li><p><span data-ttu-id="bb800-193">为相应用户启用连接组。</span><span class="sxs-lookup"><span data-stu-id="bb800-193">Enable the connection group for the appropriate users.</span></span></p></li>
<li><p><span data-ttu-id="bb800-194">根据需要逐个更新每个程序包。</span><span class="sxs-lookup"><span data-stu-id="bb800-194">Update each package individually as required.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bb800-195">对.</span><span class="sxs-lookup"><span data-stu-id="bb800-195">An.</span></span> <span data-ttu-id="bb800-196">exe 文件和中间件应用程序</span><span class="sxs-lookup"><span data-stu-id="bb800-196">exe file and a middleware application</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="bb800-197">你的应用程序需要中间件应用程序或多个应用程序，它们都依赖于同一中间件运行时版本。</span><span class="sxs-lookup"><span data-stu-id="bb800-197">You have an application requires a middleware application, or several applications that all depend on the same middleware runtime version.</span></span></p></li>
<li><p><span data-ttu-id="bb800-198">所有需要一个或多个应用程序的计算机都会收到带有应用程序和中间件应用程序运行时的连接组。</span><span class="sxs-lookup"><span data-stu-id="bb800-198">All computers that require one or more of the applications receive the connection groups with the application and middleware application runtime.</span></span></p></li>
<li><p><span data-ttu-id="bb800-199">可以选择将多个中间件应用程序合并到单个连接组中。</span><span class="sxs-lookup"><span data-stu-id="bb800-199">You can optionally combine multiple middleware applications into a single connection group.</span></span></p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bb800-200">示例</span><span class="sxs-lookup"><span data-stu-id="bb800-200">Example</span></span></th>
<th align="left"><span data-ttu-id="bb800-201">示例说明</span><span class="sxs-lookup"><span data-stu-id="bb800-201">Example description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bb800-202">用于财务部门的虚拟应用程序连接组</span><span class="sxs-lookup"><span data-stu-id="bb800-202">Virtual application connection group for the financial division</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="bb800-203">中间件应用程序1</span><span class="sxs-lookup"><span data-stu-id="bb800-203">Middleware application 1</span></span></p></li>
<li><p><span data-ttu-id="bb800-204">中间件应用程序2</span><span class="sxs-lookup"><span data-stu-id="bb800-204">Middleware application 2</span></span></p></li>
<li><p><span data-ttu-id="bb800-205">中间件应用程序3</span><span class="sxs-lookup"><span data-stu-id="bb800-205">Middleware application 3</span></span></p></li>
<li><p><span data-ttu-id="bb800-206">中间件应用程序运行时</span><span class="sxs-lookup"><span data-stu-id="bb800-206">Middleware application runtime</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bb800-207">HR 部门的虚拟应用程序连接组</span><span class="sxs-lookup"><span data-stu-id="bb800-207">Virtual application connection group for HR division</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="bb800-208">中间件应用程序5</span><span class="sxs-lookup"><span data-stu-id="bb800-208">Middleware application 5</span></span></p></li>
<li><p><span data-ttu-id="bb800-209">中间件应用程序6</span><span class="sxs-lookup"><span data-stu-id="bb800-209">Middleware application 6</span></span></p></li>
<li><p><span data-ttu-id="bb800-210">中间件应用程序运行时</span><span class="sxs-lookup"><span data-stu-id="bb800-210">Middleware application runtime</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>
<p> </p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bb800-211">对.</span><span class="sxs-lookup"><span data-stu-id="bb800-211">An.</span></span> <span data-ttu-id="bb800-212">exe 文件和 .exe 文件</span><span class="sxs-lookup"><span data-stu-id="bb800-212">exe file and an .exe file</span></span></p></td>
<td align="left"><p><span data-ttu-id="bb800-213">你有一个应用程序依赖于另一个应用程序，你希望将这些程序包分开以实现操作效率、许可限制或推出时间线。</span><span class="sxs-lookup"><span data-stu-id="bb800-213">You have an application that relies on another application, and you want to keep the packages separate for operational efficiencies, licensing restrictions, or rollout timelines.</span></span></p>
<p><strong><span data-ttu-id="bb800-214">示例：</span><span class="sxs-lookup"><span data-stu-id="bb800-214">Example:</span></span></strong></p>
<p><span data-ttu-id="bb800-215">如果要部署 Microsoft Lync 2010，可以使用三个程序包：</span><span class="sxs-lookup"><span data-stu-id="bb800-215">If you are deploying Microsoft Lync 2010, you can use three packages:</span></span></p>
<ul>
<li><p><span data-ttu-id="bb800-216">Microsoft Office2010</span><span class="sxs-lookup"><span data-stu-id="bb800-216">Microsoft Office2010</span></span></p></li>
<li><p><span data-ttu-id="bb800-217">Microsoft Communicator2007</span><span class="sxs-lookup"><span data-stu-id="bb800-217">Microsoft Communicator2007</span></span></p></li>
<li><p><span data-ttu-id="bb800-218">Microsoft Lync2010</span><span class="sxs-lookup"><span data-stu-id="bb800-218">Microsoft Lync2010</span></span></p></li>
</ul>
<p><span data-ttu-id="bb800-219">你可以使用以下连接组管理部署：</span><span class="sxs-lookup"><span data-stu-id="bb800-219">You can manage the deployment using the following connection groups:</span></span></p>
<ul>
<li><p><span data-ttu-id="bb800-220">Microsoft Office2010 和 Microsoft Communicator2007</span><span class="sxs-lookup"><span data-stu-id="bb800-220">Microsoft Office2010 and Microsoft Communicator2007</span></span></p></li>
<li><p><span data-ttu-id="bb800-221">Microsoft Office2010 和 Microsoft Lync2010</span><span class="sxs-lookup"><span data-stu-id="bb800-221">Microsoft Office2010 and Microsoft Lync2010</span></span></p></li>
</ul>
<p><span data-ttu-id="bb800-222">部署完成后，你可以创建一个新的 Microsoft Office2010 + Microsoft Lync2010 程序包，或者将它们保留并保留为单独的程序包并使用连接组进行部署。</span><span class="sxs-lookup"><span data-stu-id="bb800-222">When the deployment has completed, you can either create a single new Microsoft Office2010 + Microsoft Lync2010 package, or keep and maintain them as separate packages and deploy them by using a connection group.</span></span></p></td>
</tr>
</tbody>
</table>

 






## <span data-ttu-id="bb800-223">相关主题</span><span class="sxs-lookup"><span data-stu-id="bb800-223">Related topics</span></span>


[<span data-ttu-id="bb800-224">管理连接组</span><span class="sxs-lookup"><span data-stu-id="bb800-224">Managing Connection Groups</span></span>](managing-connection-groups51.md)

 

 





