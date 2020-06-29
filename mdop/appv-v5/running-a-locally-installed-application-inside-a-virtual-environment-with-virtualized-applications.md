---
title: 使用虚拟化应用程序在虚拟环境内部运行本地安装的应用程序
description: 使用虚拟化应用程序在虚拟环境内部运行本地安装的应用程序
author: dansimp
ms.assetid: a8affa46-f1f7-416c-8125-9595cfbfdbc7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 10c0f3f3c8a1b88cf1a98fd64fe8f7f49b597a91
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798264"
---
# <span data-ttu-id="4a8e5-103">使用虚拟化应用程序在虚拟环境内部运行本地安装的应用程序</span><span class="sxs-lookup"><span data-stu-id="4a8e5-103">Running a Locally Installed Application Inside a Virtual Environment with Virtualized Applications</span></span>


<span data-ttu-id="4a8e5-104">你可以在虚拟环境中运行本地安装的应用程序，以及使用 Microsoft Application Virtualization （App-v）虚拟化的应用程序。</span><span class="sxs-lookup"><span data-stu-id="4a8e5-104">You can run a locally installed application in a virtual environment, alongside applications that have been virtualized by using Microsoft Application Virtualization (App-V).</span></span> <span data-ttu-id="4a8e5-105">在以下情况下，您可能希望执行此操作：</span><span class="sxs-lookup"><span data-stu-id="4a8e5-105">You might want to do this if you:</span></span>

-   <span data-ttu-id="4a8e5-106">希望在客户端计算机本地安装和运行应用程序，但希望虚拟化并运行与该本地应用程序配合使用的特定插件。</span><span class="sxs-lookup"><span data-stu-id="4a8e5-106">Want to install and run an application locally on client computers, but want to virtualize and run specific plug-ins that work with that local application.</span></span>

-   <span data-ttu-id="4a8e5-107">对 app-v 客户端程序包进行故障排除，并希望在 App-v 虚拟环境中打开本地应用程序。</span><span class="sxs-lookup"><span data-stu-id="4a8e5-107">Are troubleshooting an App-V client package and want to open a local application within the App-V virtual environment.</span></span>

<span data-ttu-id="4a8e5-108">使用以下任一方法在 App-v 虚拟环境内打开本地应用程序：</span><span class="sxs-lookup"><span data-stu-id="4a8e5-108">Use any of the following methods to open a local application inside the App-V virtual environment:</span></span>

-   [<span data-ttu-id="4a8e5-109">RunVirtual 注册表项</span><span class="sxs-lookup"><span data-stu-id="4a8e5-109">RunVirtual registry key</span></span>](#bkmk-runvirtual-regkey)

-   [<span data-ttu-id="4a8e5-110">AppvClientPackage PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="4a8e5-110">Get-AppvClientPackage PowerShell cmdlet</span></span>](#bkmk-get-appvclientpackage-posh)

-   [<span data-ttu-id="4a8e5-111">命令行开关/appvpid： &lt; PID&gt;</span><span class="sxs-lookup"><span data-stu-id="4a8e5-111">Command line switch /appvpid:&lt;PID&gt;</span></span>](#bkmk-cl-switch-appvpid)

-   [<span data-ttu-id="4a8e5-112">命令行挂钩开关/appvve： &lt; GUID&gt;</span><span class="sxs-lookup"><span data-stu-id="4a8e5-112">Command line hook switch /appvve:&lt;GUID&gt;</span></span>](#bkmk-cl-hook-switch-appvve)

<span data-ttu-id="4a8e5-113">每个方法实质上是同一个任务，但某些方法可能更适合于某些应用程序，具体取决于虚拟化的应用程序是否已在运行。</span><span class="sxs-lookup"><span data-stu-id="4a8e5-113">Each method accomplishes essentially the same task, but some methods may be better suited for some applications than others, depending on whether the virtualized application is already running.</span></span>

## <a href="" id="bkmk-runvirtual-regkey"></a><span data-ttu-id="4a8e5-114">RunVirtual 注册表项</span><span class="sxs-lookup"><span data-stu-id="4a8e5-114">RunVirtual registry key</span></span>


<span data-ttu-id="4a8e5-115">若要将本地安装的应用程序添加到程序包或连接组的虚拟环境，请按照以下部分中的说明将子项添加到注册表编辑器中的 `RunVirtual` 注册表项。</span><span class="sxs-lookup"><span data-stu-id="4a8e5-115">To add a locally installed application to a package or to a connection group’s virtual environment, you add a subkey to the `RunVirtual` registry key in the Registry Editor, as described in the following sections.</span></span>

<span data-ttu-id="4a8e5-116">没有可用于管理此注册表项的组策略设置，因此你必须使用 System Center Configuration Manager 或其他电子软件分发（ESD）系统，或者手动编辑注册表。</span><span class="sxs-lookup"><span data-stu-id="4a8e5-116">There is no Group Policy setting available to manage this registry key, so you have to use System Center Configuration Manager or another electronic software distribution (ESD) system, or manually edit the registry.</span></span>

### <a href="" id="bkmk-"></a><span data-ttu-id="4a8e5-117">使用 RunVirtual 时支持的发布程序包的方法</span><span class="sxs-lookup"><span data-stu-id="4a8e5-117">Supported methods of publishing packages when using RunVirtual</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4a8e5-118">App-v 版本</span><span class="sxs-lookup"><span data-stu-id="4a8e5-118">App-V version</span></span></th>
<th align="left"><span data-ttu-id="4a8e5-119">支持的发布方法</span><span class="sxs-lookup"><span data-stu-id="4a8e5-119">Supported publishing methods</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4a8e5-120">App-v 5.0 SP3</span><span class="sxs-lookup"><span data-stu-id="4a8e5-120">App-V 5.0 SP3</span></span></p></td>
<td align="left"><p><span data-ttu-id="4a8e5-121">已全局或向用户发布</span><span class="sxs-lookup"><span data-stu-id="4a8e5-121">Published globally or to the user</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4a8e5-122">App-v 5.0 至 App-V 5.0 SP2</span><span class="sxs-lookup"><span data-stu-id="4a8e5-122">App-V 5.0 through App-V 5.0 SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="4a8e5-123">仅全局发布</span><span class="sxs-lookup"><span data-stu-id="4a8e5-123">Published globally only</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="4a8e5-124">创建子项的步骤</span><span class="sxs-lookup"><span data-stu-id="4a8e5-124">Steps to create the subkey</span></span>

1.  <span data-ttu-id="4a8e5-125">使用下表中的信息，使用可执行文件的名称创建新的注册表项，例如**MyApp.exe**。</span><span class="sxs-lookup"><span data-stu-id="4a8e5-125">Using the information in the following table, create a new registry key using the name of the executable file, for example, **MyApp.exe**.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="4a8e5-126">程序包发布方法</span><span class="sxs-lookup"><span data-stu-id="4a8e5-126">Package publishing method</span></span></th>
    <th align="left"><span data-ttu-id="4a8e5-127">在何处创建注册表项</span><span class="sxs-lookup"><span data-stu-id="4a8e5-127">Where to create the registry key</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="4a8e5-128">全局发布</span><span class="sxs-lookup"><span data-stu-id="4a8e5-128">Published globally</span></span></p></td>
    <td align="left"><p><span data-ttu-id="4a8e5-129">HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\AppV\Client\RunVirtual</span><span class="sxs-lookup"><span data-stu-id="4a8e5-129">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\AppV\Client\RunVirtual</span></span></p>
    <p><strong><span data-ttu-id="4a8e5-130">示例 </strong> ： HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\AppV\Client\RunVirtual\MyApp.exe</span><span class="sxs-lookup"><span data-stu-id="4a8e5-130">Example</strong>: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\AppV\Client\RunVirtual\MyApp.exe</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="4a8e5-131">发布给用户</span><span class="sxs-lookup"><span data-stu-id="4a8e5-131">Published to the user</span></span></p></td>
    <td align="left"><p><span data-ttu-id="4a8e5-132">HKEY_CURRENT_USER \SOFTWARE\Microsoft\AppV\Client\RunVirtual</span><span class="sxs-lookup"><span data-stu-id="4a8e5-132">HKEY_CURRENT_USER\SOFTWARE\Microsoft\AppV\Client\RunVirtual</span></span></p>
    <p><strong><span data-ttu-id="4a8e5-133">示例 </strong> ： HKEY_CURRENT_USER \SOFTWARE\Microsoft\AppV\Client\RunVirtual\MyApp.exe</span><span class="sxs-lookup"><span data-stu-id="4a8e5-133">Example</strong>: HKEY_CURRENT_USER \SOFTWARE\Microsoft\AppV\Client\RunVirtual\MyApp.exe</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="4a8e5-134">连接组可以包含：</span><span class="sxs-lookup"><span data-stu-id="4a8e5-134">Connection group can contain:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="4a8e5-135">仅在全局或仅向用户发布的程序包</span><span class="sxs-lookup"><span data-stu-id="4a8e5-135">Packages that are published just globally or just to the user</span></span></p></li>
    <li><p><span data-ttu-id="4a8e5-136">全局发布和用户发布的程序包</span><span class="sxs-lookup"><span data-stu-id="4a8e5-136">Packages that are published globally and to the user</span></span></p></li>
    </ul></td>
    <td align="left"><p><span data-ttu-id="4a8e5-137">HKEY_LOCAL_MACHINE 或 HKEY_CURRENT_USER 键，但以下所有条件都必须为 true：</span><span class="sxs-lookup"><span data-stu-id="4a8e5-137">Either HKEY_LOCAL_MACHINE or HKEY_CURRENT_USER key, but all of the following must be true:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="4a8e5-138">如果要在虚拟环境中包含多个程序包，则必须将它们包含在已启用的连接组中。</span><span class="sxs-lookup"><span data-stu-id="4a8e5-138">If you want to include multiple packages in the virtual environment, you must include them in an enabled connection group.</span></span></p></li>
    <li><p><span data-ttu-id="4a8e5-139">仅为连接组中的其中一个程序包创建一个子项。</span><span class="sxs-lookup"><span data-stu-id="4a8e5-139">Create only one subkey for one of the packages in the connection group.</span></span> <span data-ttu-id="4a8e5-140">例如，如果你有一个在全局上发布的程序包以及发布给用户的另一个程序包，则会为这些程序包之一创建一个子项，但不能同时创建这两个程序包。</span><span class="sxs-lookup"><span data-stu-id="4a8e5-140">If, for example, you have one package that is published globally, and another package that is published to the user, you create a subkey for either of these packages, but not both.</span></span> <span data-ttu-id="4a8e5-141">虽然只为其中一个程序包创建子项，但连接组中的所有程序包以及本地应用程序都将在虚拟环境中可用。</span><span class="sxs-lookup"><span data-stu-id="4a8e5-141">Although you create a subkey for only one of the packages, all of the packages in the connection group, plus the local application, will be available in the virtual environment.</span></span></p></li>
    <li><p><span data-ttu-id="4a8e5-142">创建子项的键必须与您用于程序包的发布方法相匹配。</span><span class="sxs-lookup"><span data-stu-id="4a8e5-142">The key under which you create the subkey must match the publishing method you used for the package.</span></span></p>
    <p><span data-ttu-id="4a8e5-143">例如，如果你将程序包发布给用户，则必须在下创建该子项 <code>HKEY_CURRENT_USER\SOFTWARE\Microsoft\AppV\Client\RunVirtual</code> 。</span><span class="sxs-lookup"><span data-stu-id="4a8e5-143">For example, if you published the package to the user, you must create the subkey under <code>HKEY_CURRENT_USER\SOFTWARE\Microsoft\AppV\Client\RunVirtual</code>.</span></span></p></li>
    </ul></td>
    </tr>
    </tbody>
    </table>

     

2.  <span data-ttu-id="4a8e5-144">将新的注册表子项的值设置为程序包的 PackageId 和 VersionId，并用下划线分隔这些值。</span><span class="sxs-lookup"><span data-stu-id="4a8e5-144">Set the new registry subkey’s value to the PackageId and VersionId of the package, separating the values with an underscore.</span></span>

    <span data-ttu-id="4a8e5-145">**语法**： &lt; PackageId &gt; \ _ &lt; VersionId&gt;</span><span class="sxs-lookup"><span data-stu-id="4a8e5-145">**Syntax**: &lt;PackageId&gt;\_&lt;VersionId&gt;</span></span>

    <span data-ttu-id="4a8e5-146">**示例**： 4c909996-afc9-4352-b606-0b74542a09c1 \ _Be463724-Oct1-48f1-8604-c4bd7ca92fa</span><span class="sxs-lookup"><span data-stu-id="4a8e5-146">**Example**: 4c909996-afc9-4352-b606-0b74542a09c1\_be463724-Oct1-48f1-8604-c4bd7ca92fa</span></span>

    <span data-ttu-id="4a8e5-147">上一个示例中的应用程序将生成如下所示的注册表导出文件（.reg 文件）：</span><span class="sxs-lookup"><span data-stu-id="4a8e5-147">The application in the previous example would produce a registry export file (.reg file) like the following:</span></span>

    ``` syntax
    Windows Registry Editor Version 5.00 
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\AppV\Client\RunVirtual] 
    @="" 
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\AppV\Client\RunVirtual\MyApp.exe] 
    @="aaaaaaaa-bbbb-cccc-dddd-eeeeeeee_11111111-2222-3333-4444-555555555
    ```

## <a href="" id="bkmk-get-appvclientpackage-posh"></a><span data-ttu-id="4a8e5-148">AppvClientPackage PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="4a8e5-148">Get-AppvClientPackage PowerShell cmdlet</span></span>


<span data-ttu-id="4a8e5-149">你可以使用**AppVVirtualProcess** cmdlet 检索程序包名称，然后在指定程序包的虚拟环境中启动进程。</span><span class="sxs-lookup"><span data-stu-id="4a8e5-149">You can use the **Start-AppVVirtualProcess** cmdlet to retrieve the package name and then start a process within the specified package's virtual environment.</span></span> <span data-ttu-id="4a8e5-150">此方法允许你在 App-v 包的上下文中启动任何命令，无论该包当前是否正在运行。</span><span class="sxs-lookup"><span data-stu-id="4a8e5-150">This method lets you launch any command within the context of an App-V package, regardless of whether the package is currently running.</span></span>

<span data-ttu-id="4a8e5-151">使用以下语法示例，并替换\*\* &lt; 程序包 &gt; \*\*的名称：</span><span class="sxs-lookup"><span data-stu-id="4a8e5-151">Use the following example syntax, and substitute the name of your package for **&lt;Package&gt;**:</span></span>

`$AppVName = Get-AppvClientPackage <Package>`

`Start-AppvVirtualProcess -AppvClientObject $AppVName cmd.exe`

<span data-ttu-id="4a8e5-152">如果不知道程序包的确切名称，则可以使用命令行**AppvClientPackage \ \* executable\\** <em> ，其中 \**可执行 </em> 文件*是应用程序的名称，例如： Get-AppvClientPackage \ \* Word \ \*。</span><span class="sxs-lookup"><span data-stu-id="4a8e5-152">If you don’t know the exact name of your package, you can use the command line **Get-AppvClientPackage \*executable\\**<em>, where \**executable</em>* is the name of the application, for example: Get-AppvClientPackage \*Word\*.</span></span>

## <a href="" id="bkmk-cl-switch-appvpid"></a><span data-ttu-id="4a8e5-153">命令行开关/appvpid： &lt; PID&gt;</span><span class="sxs-lookup"><span data-stu-id="4a8e5-153">Command line switch /appvpid:&lt;PID&gt;</span></span>


<span data-ttu-id="4a8e5-154">你可以将 \*\*/appvpid： &lt; PID &gt; \*\*开关应用到任何命令，从而使该命令能够在你选择的虚拟进程内运行，方法是指定其进程 ID （PID）。</span><span class="sxs-lookup"><span data-stu-id="4a8e5-154">You can apply the **/appvpid:&lt;PID&gt;** switch to any command, which enables that command to run within a virtual process that you select by specifying its process ID (PID).</span></span> <span data-ttu-id="4a8e5-155">使用此方法会在与已运行的可执行文件相同的 App-v 环境中启动新的可执行文件。</span><span class="sxs-lookup"><span data-stu-id="4a8e5-155">Using this method launches the new executable in the same App-V environment as an executable that is already running.</span></span>

<span data-ttu-id="4a8e5-156">示例：</span><span class="sxs-lookup"><span data-stu-id="4a8e5-156">Example:</span></span> `cmd.exe /appvpid:8108`

<span data-ttu-id="4a8e5-157">若要查找 app-v 进程的进程 ID （PID），请从提升的命令提示符处运行命令**tasklist.exe** 。</span><span class="sxs-lookup"><span data-stu-id="4a8e5-157">To find the process ID (PID) of your App-V process, run the command **tasklist.exe** from an elevated command prompt.</span></span>

## <a href="" id="bkmk-cl-hook-switch-appvve"></a><span data-ttu-id="4a8e5-158">命令行挂钩开关/appvve： &lt; GUID&gt;</span><span class="sxs-lookup"><span data-stu-id="4a8e5-158">Command line hook switch /appvve:&lt;GUID&gt;</span></span>


<span data-ttu-id="4a8e5-159">此开关允许你在 App-v 包的虚拟环境内运行本地命令。</span><span class="sxs-lookup"><span data-stu-id="4a8e5-159">This switch lets you run a local command within the virtual environment of an App-V package.</span></span> <span data-ttu-id="4a8e5-160">与 **/appvid**开关（虚拟环境必须已运行）不同，此开关使你能够启动虚拟环境。</span><span class="sxs-lookup"><span data-stu-id="4a8e5-160">Unlike the **/appvid** switch, where the virtual environment must already be running, this switch enables you to start the virtual environment.</span></span>

<span data-ttu-id="4a8e5-161">语法</span><span class="sxs-lookup"><span data-stu-id="4a8e5-161">Syntax:</span></span> `cmd.exe /appvve:<PACKAGEGUID_VERSIONGUID>`

<span data-ttu-id="4a8e5-162">示例：</span><span class="sxs-lookup"><span data-stu-id="4a8e5-162">Example:</span></span> `cmd.exe /appvve:aaaaaaaa-bbbb-cccc-dddd-eeeeeeee_11111111-2222-3333-4444-55555555`

<span data-ttu-id="4a8e5-163">若要获取应用程序的程序包 GUID 和版本 GUID，请运行**AppvClientPackage** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4a8e5-163">To get the package GUID and version GUID of your application, run the **Get-AppvClientPackage** cmdlet.</span></span> <span data-ttu-id="4a8e5-164">将 **/appvve**开关与以下内容连接：</span><span class="sxs-lookup"><span data-stu-id="4a8e5-164">Concatenate the **/appvve** switch with the following:</span></span>

-   <span data-ttu-id="4a8e5-165">冒号</span><span class="sxs-lookup"><span data-stu-id="4a8e5-165">A colon</span></span>

-   <span data-ttu-id="4a8e5-166">所需程序包的程序包 GUID</span><span class="sxs-lookup"><span data-stu-id="4a8e5-166">Package GUID of the desired package</span></span>

-   <span data-ttu-id="4a8e5-167">下划线</span><span class="sxs-lookup"><span data-stu-id="4a8e5-167">An underscore</span></span>

-   <span data-ttu-id="4a8e5-168">所需程序包的版本 ID</span><span class="sxs-lookup"><span data-stu-id="4a8e5-168">Version ID of the desired package</span></span>

<span data-ttu-id="4a8e5-169">如果不知道程序包的确切名称，请使用命令行**AppvClientPackage \ \* executable\\** <em> ，其中 \**可执行 </em> 文件*是应用程序的名称，例如： Get-AppvClientPackage \ \* Word \ \*。</span><span class="sxs-lookup"><span data-stu-id="4a8e5-169">If you don’t know the exact name of your package, use the command line **Get-AppvClientPackage \*executable\\**<em>, where \**executable</em>* is the name of the application, for example: Get-AppvClientPackage \*Word\*.</span></span>

<span data-ttu-id="4a8e5-170">此方法允许你在 App-v 包的上下文中启动任何命令，无论该包当前是否正在运行。</span><span class="sxs-lookup"><span data-stu-id="4a8e5-170">This method lets you launch any command within the context of an App-V package, regardless of whether the package is currently running.</span></span>






## <span data-ttu-id="4a8e5-171">相关主题</span><span class="sxs-lookup"><span data-stu-id="4a8e5-171">Related topics</span></span>


[<span data-ttu-id="4a8e5-172">App-V 5.0 技术参考</span><span class="sxs-lookup"><span data-stu-id="4a8e5-172">Technical Reference for App-V 5.0</span></span>](technical-reference-for-app-v-50.md)

 

 





