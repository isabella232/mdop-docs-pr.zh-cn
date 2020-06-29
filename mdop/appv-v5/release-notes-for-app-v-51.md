---
title: App-V 5.1 发行说明
description: App-V 5.1 发行说明
author: dansimp
ms.assetid: 62c5be3b-0a46-4512-93ed-97c23184f343
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 09/26/2016
ms.openlocfilehash: 7437a16bc10b21bb15b0f8307c2711177e78cb72
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798263"
---
# <span data-ttu-id="4a0c4-103">App-V 5.1 发行说明</span><span class="sxs-lookup"><span data-stu-id="4a0c4-103">Release Notes for App-V 5.1</span></span>


<span data-ttu-id="4a0c4-104">以下是 Microsoft Application Virtualization （App-v）5.1 中的已知问题。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-104">The following are known issues in Microsoft Application Virtualization (App-V) 5.1.</span></span>

## <span data-ttu-id="4a0c4-105">在 Windows 10 上的 App-v 5.0 SP3 管理服务器和 App-v 5.1 客户端之间的发布刷新期间出现错误</span><span class="sxs-lookup"><span data-stu-id="4a0c4-105">Error occurs during publishing refresh between App-V 5.0 SP3 Management Server and App-V 5.1 Client on Windows 10</span></span>


<span data-ttu-id="4a0c4-106">将程序包从 App-v 5.0 SP3 管理服务器同步到 Windows 10 上的 App-v 5.1 客户端时，将在发布刷新期间生成错误。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-106">An error is generated during publishing refresh when synchronizing packages from the App-V 5.0 SP3 management server to an App-V 5.1 client on Windows 10 .</span></span> <span data-ttu-id="4a0c4-107">出现此错误的原因是，app-v 5.0 SP3 服务器不理解发布 URL 中指定的 Windows 10 操作系统。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-107">This error occurs because the App-V 5.0 SP3 server does not understand the Windows 10 operating system that is specified in the publishing URL.</span></span> <span data-ttu-id="4a0c4-108">此问题适用于 app-v 5.1 发布服务器，但不适用于 app-v 5.0 SP3 或更早版本的 backported。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-108">The issue is fixed for App-V 5.1 publishing server, but is not backported to versions of App-V 5.0 SP3 or earlier.</span></span>

<span data-ttu-id="4a0c4-109">**解决方法**：将 App-v 5.0 管理服务器升级到适用于 Windows 10 客户端的 App-v 5.1 管理服务器。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-109">**Workaround**: Upgrade the App-V 5.0 Management server to the App-V 5.1 Management server for Windows 10 Clients.</span></span>

## <span data-ttu-id="4a0c4-110">如果使用 App-v 5.1 Server 进行设置，则不会为将在全局发布的程序包应用自定义配置</span><span class="sxs-lookup"><span data-stu-id="4a0c4-110">Custom configurations do not get applied for packages that will be published globally if they are set using the App-V 5.1 Server</span></span>


<span data-ttu-id="4a0c4-111">如果将程序包分配给包含计算机帐户的 AD 组，并使用 App-v 服务器将自定义配置应用到该组，则不会将自定义配置应用到这些计算机。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-111">If you assign a package to an AD group that contains machine accounts and apply a custom configuration to that group using the App-V Server, the custom configuration will not be applied to those machines.</span></span> <span data-ttu-id="4a0c4-112">App-v 5.1 客户端将在全局范围内发布分配给计算机帐户的程序包。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-112">The App-V 5.1 Client will publish packages assigned to a machine account globally.</span></span> <span data-ttu-id="4a0c4-113">但是，它会在每个用户的配置文件中存储每个用户的自定义配置文件。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-113">However, it stores custom configuration files per user in each user’s profile.</span></span> <span data-ttu-id="4a0c4-114">全局发布的程序包将无法访问此自定义配置。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-114">Globally published packages will not have access to this custom configuration.</span></span>

<span data-ttu-id="4a0c4-115">**解决方法**：执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="4a0c4-115">**Workaround**: Do one of the following:</span></span>

-   <span data-ttu-id="4a0c4-116">将程序包分配给仅包含用户帐户的组。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-116">Assign the package to groups containing only user accounts.</span></span> <span data-ttu-id="4a0c4-117">这将确保程序包的自定义配置将存储在每个用户的配置文件中，并且将正确应用。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-117">This will ensure that the package’s custom configuration will be stored in each user’s profile and will be applied correctly.</span></span>

-   <span data-ttu-id="4a0c4-118">创建自定义部署配置文件，并将其应用于客户端上的程序包，并将 AppvClientPackage cmdlet 与-DynamicDeploymentConfiguration 参数结合使用。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-118">Create a custom deployment configuration file and apply it to the package on the client using the Add-AppvClientPackage cmdlet with the –DynamicDeploymentConfiguration parameter.</span></span> <span data-ttu-id="4a0c4-119">有关详细信息，请参阅[关于 App-V 5.1 动态配置](about-app-v-51-dynamic-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-119">See [About App-V 5.1 Dynamic Configuration](about-app-v-51-dynamic-configuration.md) for more information.</span></span>

-   <span data-ttu-id="4a0c4-120">使用 App-v 5.1 Sequencer 创建具有自定义配置的新程序包。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-120">Create a new package with the custom configuration using the App-V 5.1 Sequencer.</span></span>

## <span data-ttu-id="4a0c4-121">在新应用-V 5.1 服务器安装后未删除的服务器文件</span><span class="sxs-lookup"><span data-stu-id="4a0c4-121">Server files not deleted after new App-V 5.1 Server installation</span></span>


<span data-ttu-id="4a0c4-122">如果卸载 V 5.0 SP1 服务器，然后安装 app-v 5.1 服务器，安装将失败，安装的管理服务器版本不正确，并返回错误消息。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-122">If you uninstall the App-V 5.0 SP1 Server and then install the App-V 5.1 Server, the installation fails, the wrong version of the Management server is installed, and an error message is returned.</span></span> <span data-ttu-id="4a0c4-123">出现此问题的原因是，卸载 app-v 5.0 SP1 时未删除服务器文件，因此安装过程将执行升级而不是全新安装。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-123">The issue occurs because the Server files are not being deleted when you uninstall App-V 5.0 SP1, so the installation process does an upgrade instead of a new installation.</span></span>

<span data-ttu-id="4a0c4-124">**解决方法**：在开始安装 app-v 5.1 之前删除此注册表项：</span><span class="sxs-lookup"><span data-stu-id="4a0c4-124">**Workaround**: Delete this registry key before you start installing App-V 5.1:</span></span>

<span data-ttu-id="4a0c4-125">在 "HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Wow6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall" 下，找到并删除包含 "Microsoft Application Virtualization （app-v）服务器" 值数据的 DWORD 值 "DisplayName" 的安装 GUID 注册表项。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-125">Under HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall, locate and delete the installation GUID key that contains the DWORD value "DisplayName" with value data "Microsoft Application Virtualization (App-V) Server".</span></span> <span data-ttu-id="4a0c4-126">这是唯一应删除的键。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-126">This is the only key that should be deleted.</span></span>

## <span data-ttu-id="4a0c4-127">手动添加的文件类型关联未正确保存</span><span class="sxs-lookup"><span data-stu-id="4a0c4-127">File type associations added manually are not saved correctly</span></span>


<span data-ttu-id="4a0c4-128">使用应用程序升级向导末尾的 "快捷方式" 和 "FTAs" 选项卡手动添加到应用程序包中的文件类型关联不会正确保存。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-128">File type associations added to an application package manually using the Shortcuts and FTAs tab at the end of the application upgrade wizard are not saved correctly.</span></span> <span data-ttu-id="4a0c4-129">当再次更新已保存的程序包时，应用程序或 Sequencer 将无法使用它们。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-129">They will not be available to the App-V Client or to the Sequencer when updating the saved package again.</span></span>

<span data-ttu-id="4a0c4-130">**解决方法**：若要添加文件类型关联，请打开要修改的程序包，然后运行 "更新向导"。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-130">**Workaround**: To add a file type association, open the package for modification and run the update wizard.</span></span> <span data-ttu-id="4a0c4-131">在安装步骤中，通过操作系统添加新的文件类型关联。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-131">During the Installation step, add the new file type association through the operating system.</span></span> <span data-ttu-id="4a0c4-132">Sequencer 将检测系统注册表中的新关联，并将其添加到程序包的虚拟注册表，该关联将可用于客户端。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-132">The sequencer will detect the new association in the system registry and add it to the package’s virtual registry, where it will be available to the client.</span></span>

## <span data-ttu-id="4a0c4-133">将共享内容存储（SCS）模式中的流包添加到同时使用 AppLocker 托管的客户端时，会将其他数据写入本地磁盘。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-133">When streaming packages in Shared Content Store (SCS) mode to a client that is also managed with AppLocker, additional data is written to the local disk.</span></span>


<span data-ttu-id="4a0c4-134">若要减少写入客户端本地磁盘的数据量，可以在 App-v 5.1 客户端上启用 SCS 模式，以根据需要流式处理程序包的内容。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-134">To decrease the amount of data written to a client’s local disk, you can enable SCS mode on the App-V 5.1 Client to stream the contents of a package on demand.</span></span> <span data-ttu-id="4a0c4-135">但是，如果 AppLocker 在程序包中管理应用程序，则某些数据可能会写入到不会被写入的客户端本地磁盘中。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-135">However, if AppLocker manages an application within the package, some data might be written to the client’s local disk that would not otherwise be written.</span></span>

<span data-ttu-id="4a0c4-136">**解决方法**：无</span><span class="sxs-lookup"><span data-stu-id="4a0c4-136">**Workaround**: None</span></span>

## <span data-ttu-id="4a0c4-137">在 "管理控制台添加程序包" 对话框中，使用 Chrome 或 Firefox 时，"浏览" 按钮不可用</span><span class="sxs-lookup"><span data-stu-id="4a0c4-137">In the Management Console Add Package dialog box, the Browse button is not available when using Chrome or Firefox</span></span>


<span data-ttu-id="4a0c4-138">在管理控制台的 "程序包" 页面上，如果在右下角单击 "**添加" 或 "升级**"，将显示 "**添加程序包**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-138">On the Packages page of the Management Console, if you click **Add or Upgrade** in the lower-right corner, the **Add Package** dialog box appears.</span></span> <span data-ttu-id="4a0c4-139">如果您使用 Chrome 或 Firefox 作为浏览器访问管理控制台，您将无法浏览到程序包的位置。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-139">If you are accessing the Management Console using Chrome or Firefox as your browser, you will not be able to browse to the location of the package.</span></span>

<span data-ttu-id="4a0c4-140">**解决方法**：在 "**添加包**" 输入字段中键入或复制并粘贴程序包的路径。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-140">**Workaround**: Type or copy and paste the path to the package into the **Add Package** input field.</span></span> <span data-ttu-id="4a0c4-141">如果管理控制台有权访问此路径，你将能够添加程序包。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-141">If the Management Console has access to this path, you will be able to add the package.</span></span> <span data-ttu-id="4a0c4-142">如果程序包位于网络共享位置，则可以通过执行以下步骤浏览到使用文件资源管理器的位置：</span><span class="sxs-lookup"><span data-stu-id="4a0c4-142">If the package is on a network share, you can browse to the location using File Explorer by doing these steps:</span></span>

1.  <span data-ttu-id="4a0c4-143">按**Shift**的同时，右键单击软件包文件</span><span class="sxs-lookup"><span data-stu-id="4a0c4-143">While pressing **Shift**, right-click on the package file</span></span>

2.  <span data-ttu-id="4a0c4-144">选择 "**复制为路径**"</span><span class="sxs-lookup"><span data-stu-id="4a0c4-144">Select **Copy as path**</span></span>

3.  <span data-ttu-id="4a0c4-145">将路径粘贴到 "**添加包**" 对话框输入字段</span><span class="sxs-lookup"><span data-stu-id="4a0c4-145">Paste the path into the **Add Package** dialog box input field</span></span>

## <a href="" id="upgrading-app-v-management-server-to-5-1-sometimes-fails-with-the-message--a-database-error-occurred-"></a><span data-ttu-id="4a0c4-146">将 App-v 管理服务器升级到5.1 有时会失败，并出现消息 "数据库出错"</span><span class="sxs-lookup"><span data-stu-id="4a0c4-146">Upgrading App-V Management Server to 5.1 sometimes fails with the message “A database error occurred”</span></span>


<span data-ttu-id="4a0c4-147">如果安装了 app-v 5.0 SP1 管理服务器，然后尝试升级到 app-v 5.1 服务器，当配置和启用多个连接组时，将显示以下错误： "数据库出错。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-147">If you install the App-V 5.0 SP1 Management Server, and then try to upgrade to App-V 5.1 Server when multiple connection groups are configured and enabled, the following error is displayed: “A database error occurred.</span></span> <span data-ttu-id="4a0c4-148">原因： "列名称" PackageOptional "无效。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-148">Reason: 'Invalid column name 'PackageOptional'.</span></span> <span data-ttu-id="4a0c4-149">无效的列名称 "VersionOptional"。 "</span><span class="sxs-lookup"><span data-stu-id="4a0c4-149">Invalid column name 'VersionOptional'.”</span></span>

<span data-ttu-id="4a0c4-150">**解决方法**：在 SQL 数据库上运行此命令：</span><span class="sxs-lookup"><span data-stu-id="4a0c4-150">**Workaround**: Run this command on your SQL database:</span></span>

`ALTER TABLE AppVManagement.dbo.PackageGroupMembers ADD PackageOptional bit NOT NULL DEFAULT 0, VersionOptional bit NOT NULL DEFAULT 0`

<span data-ttu-id="4a0c4-151">其中 "AppVManagement" 是数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-151">where “AppVManagement” is the name of the database.</span></span>

## <span data-ttu-id="4a0c4-152">如果添加或删除可选程序包，则用户无法打开用户发布的连接组中的程序包</span><span class="sxs-lookup"><span data-stu-id="4a0c4-152">Users cannot open a package in a user-published connection group if you add or remove an optional package</span></span>


<span data-ttu-id="4a0c4-153">在运行 RDS 客户端的环境中或每台计算机有多个并发用户的环境中，如果在连接组中添加或删除了可选程序包，则登录用户无法打开用户发布的连接组中的程序包中的应用程序。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-153">In environments that are running the RDS Client or that have multiple concurrent users per computer, logged-in users cannot open applications in packages that are in a user-published connection group if an optional package is added to or removed from the connection group.</span></span>

<span data-ttu-id="4a0c4-154">**解决方法**：让用户注销，然后重新登录。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-154">**Workaround**: Have users log out and then log back in.</span></span>

## <span data-ttu-id="4a0c4-155">将连接组仅发布给用户时错误消息被错误地显示</span><span class="sxs-lookup"><span data-stu-id="4a0c4-155">Error message is erroneously displayed when the connection group is published only to the user</span></span>


<span data-ttu-id="4a0c4-156">当你运行 AppvClientConnectionGroup 时，将显示以下错误，即使仅将连接组发布给用户： "内部应用 V 集成错误：未针对用户集成程序包。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-156">When you run Repair-AppvClientConnectionGroup, the following error is displayed, even when the connection group is published only to the user: “Internal App-V Integration error: Package not integrated for the user.</span></span> <span data-ttu-id="4a0c4-157">请确保程序包已添加到计算机并发布给用户。 "</span><span class="sxs-lookup"><span data-stu-id="4a0c4-157">Please ensure that the package is added to the machine and published to the user.”</span></span>

<span data-ttu-id="4a0c4-158">**解决方法**：执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="4a0c4-158">**Workaround**: Do one of the following:</span></span>

-   <span data-ttu-id="4a0c4-159">发布连接组中的所有程序包。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-159">Publish all packages in a connection group.</span></span>

    <span data-ttu-id="4a0c4-160">如果正在修复的连接组具有缺失或不可用于用户的程序包（即，未在全局发布或向用户发布），则会出现此问题。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-160">The problem arises when the connection group being repaired has packages that are missing or not available to the user (that is, not published globally or to the user).</span></span> <span data-ttu-id="4a0c4-161">但是，如果所有连接组的程序包都可用，则修复将正常运行，因此请确保发布所有程序包。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-161">However, the repair will work if all of the connection group’s packages are available, so ensure that all packages are published.</span></span>

-   <span data-ttu-id="4a0c4-162">使用 AppvClientPackage 命令（而不是 Repair AppvClientConnectionGroup 命令）单独修复程序包。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-162">Repair packages individually using the Repair-AppvClientPackage command rather than the Repair-AppvClientConnectionGroup command.</span></span>

    <span data-ttu-id="4a0c4-163">确定哪些程序包对用户可用，然后对每个程序包运行 AppvClientPackage 命令一次。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-163">Determine which packages are available to users and then run the Repair-AppvClientPackage command once for each package.</span></span> <span data-ttu-id="4a0c4-164">使用 PowerShell cmdlet 执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4a0c4-164">Use PowerShell cmdlets to do the following:</span></span>

    1.  <span data-ttu-id="4a0c4-165">获取连接组中的所有程序包。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-165">Get all the packages in a connection group.</span></span>

    2.  <span data-ttu-id="4a0c4-166">检查是否每个程序包当前是否已发布。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-166">Check to see if each package is currently published.</span></span>

    3.  <span data-ttu-id="4a0c4-167">如果程序包当前已发布，请在该程序包上运行 AppvClientPackage。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-167">If the package is currently published, run Repair-AppvClientPackage on that package.</span></span>

## <span data-ttu-id="4a0c4-168">Sequencer 中的图标未正确显示</span><span class="sxs-lookup"><span data-stu-id="4a0c4-168">Icons not displayed properly in Sequencer</span></span>


<span data-ttu-id="4a0c4-169">修改 app-v 排序器中的程序包时，"快捷方式" 和 "文件类型关联" 选项卡中的图标不会正确显示。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-169">Icons in the Shortcuts and File Type Associations tab are not displayed correctly when modifying a package in the App-V Sequencer.</span></span> <span data-ttu-id="4a0c4-170">如果图标的大小不是16x16 或32x32，则会出现此问题。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-170">This problem occurs when the size of the icons are not 16x16 or 32x32.</span></span>

<span data-ttu-id="4a0c4-171">**解决方法**：仅使用16x16 或32x32 的图标。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-171">**Workaround**: Only use icons that are 16x16 or 32x32.</span></span>

## <span data-ttu-id="4a0c4-172">管理数据库不再需要 InsertVersionInfo 脚本</span><span class="sxs-lookup"><span data-stu-id="4a0c4-172">InsertVersionInfo.sql script no longer required for the Management Database</span></span>


<span data-ttu-id="4a0c4-173">晚于 app-v 5.0 SP3 的 App-v 管理数据库的版本不需要 InsertVersionInfo 脚本。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-173">The InsertVersionInfo.sql script is not required for versions of the App-V management database later than App-V 5.0 SP3.</span></span>

<span data-ttu-id="4a0c4-174">应根据[知识库文章 3031340](https://support.microsoft.com/kb/3031340)中的**步骤 2**更新权限。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-174">The Permissions.sql script should be updated according to **Step 2** in [KB article 3031340](https://support.microsoft.com/kb/3031340).</span></span>

<span data-ttu-id="4a0c4-175">**重要提示** 
在 app-v 5.0 SP3 之后的 app-v 版本中不需要**步骤 1** 。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-175">**Important**
**Step 1** is not required for versions of App-V later than App-V 5.0 SP3.</span></span>

 

## <span data-ttu-id="4a0c4-176">Microsoft Visual Studio 2012 不受支持</span><span class="sxs-lookup"><span data-stu-id="4a0c4-176">Microsoft Visual Studio 2012 not supported</span></span>


<span data-ttu-id="4a0c4-177">App-v 5.1 不支持 Visual Studio 2012。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-177">App-V 5.1 does not support Visual Studio 2012.</span></span>

<span data-ttu-id="4a0c4-178">**解决方法**：无</span><span class="sxs-lookup"><span data-stu-id="4a0c4-178">**Workaround**: None</span></span>

## <span data-ttu-id="4a0c4-179">应用的应用程序文件名限制-V-V 排序器</span><span class="sxs-lookup"><span data-stu-id="4a0c4-179">Application filename restrictions for App-V 5.x Sequencer</span></span>


<span data-ttu-id="4a0c4-180">App-v 5. x Sequencer 无法序列文件名与 "CO_ x" 匹配的应用 &lt; 程序 &gt; ，其中 x 是任何数字。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-180">The App-V 5.x Sequencer cannot sequence applications with filenames matching "CO_&lt;x&gt;" where x is any numeral.</span></span> <span data-ttu-id="4a0c4-181">将生成错误0x8007139F。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-181">Error 0x8007139F will be generated.</span></span>

<span data-ttu-id="4a0c4-182">**解决方法**：使用其他文件名</span><span class="sxs-lookup"><span data-stu-id="4a0c4-182">**Workaround**: Use a different filename</span></span>

## <span data-ttu-id="4a0c4-183">装入程序包时出现间歇性的 "找不到文件" 错误</span><span class="sxs-lookup"><span data-stu-id="4a0c4-183">Intermittent "File Not Found" error when Mounting a Package</span></span>


<span data-ttu-id="4a0c4-184">有时，当装载程序包时，将生成 "找不到文件" （0x80070002）错误。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-184">Occasionally when mounting a package, a "File Not Found" (0x80070002) error is generated.</span></span> <span data-ttu-id="4a0c4-185">通常，当 App-v 包中的文件夹包含许多文件（即20K 或更多文件）时，会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-185">Typically, this occurs when a folder in an App-V package contains many files ( i.e. 20K or more).</span></span> <span data-ttu-id="4a0c4-186">这可能导致流出的时间比预期长，并将生成 "找不到文件" 错误。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-186">This can cause streaming to take longer than expected and to time out which generates the "File Not Found" error.</span></span>

<span data-ttu-id="4a0c4-187">**解决方法**：从 HF06 开始，引入了新的注册表项以启用延长此超时周期。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-187">**Workaround**: Starting with HF06, a new registry key has been introduced to enable extending this time-out period.</span></span>

<table>
<colgroup>
<col width="20%" />
<col width="80%" />
</colgroup>
<tbody>
<tr>
<td align="left"><span data-ttu-id="4a0c4-188">路径</span><span class="sxs-lookup"><span data-stu-id="4a0c4-188">Path</span></span></td>
<td align="left"><span data-ttu-id="4a0c4-189">HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\AppV\Client\Streaming</span><span class="sxs-lookup"><span data-stu-id="4a0c4-189">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\AppV\Client\Streaming</span></span></td>
</tr>
<tr>
<td align="left"><span data-ttu-id="4a0c4-190">设置</span><span class="sxs-lookup"><span data-stu-id="4a0c4-190">Setting</span></span></td>
<td align="left"><span data-ttu-id="4a0c4-191">StreamResponseWaitTimeout</span><span class="sxs-lookup"><span data-stu-id="4a0c4-191">StreamResponseWaitTimeout</span></span></td>
</tr>
<tr>
<td align="left"><span data-ttu-id="4a0c4-192">Udt</span><span class="sxs-lookup"><span data-stu-id="4a0c4-192">DataType</span></span></td>
<td align="left"><span data-ttu-id="4a0c4-193">DWORD</span><span class="sxs-lookup"><span data-stu-id="4a0c4-193">DWORD</span></span></td>
</tr>
<tr>
<td align="left"><span data-ttu-id="4a0c4-194">刻度</span><span class="sxs-lookup"><span data-stu-id="4a0c4-194">Units</span></span></td>
<td align="left"><span data-ttu-id="4a0c4-195">秒</span><span class="sxs-lookup"><span data-stu-id="4a0c4-195">Seconds</span></span></td>
</tr>
<tr>
<td align="left"><span data-ttu-id="4a0c4-196">默认值</span><span class="sxs-lookup"><span data-stu-id="4a0c4-196">Default</span></span></td>
<td align="left"><span data-ttu-id="4a0c4-197">级</span><span class="sxs-lookup"><span data-stu-id="4a0c4-197">5</span></span><br />
<strong><span data-ttu-id="4a0c4-198">注意 </strong> ：如果未定义注册表项或指定了值 = 5，则此值为默认值 &lt; 。</span><span class="sxs-lookup"><span data-stu-id="4a0c4-198">Note</strong>: this value is the default if the registry key is not defined or a value &lt;=5 is specified.</span></span>
</td>
</tr>
</tbody>
</table>






## <span data-ttu-id="4a0c4-199">相关主题</span><span class="sxs-lookup"><span data-stu-id="4a0c4-199">Related topics</span></span>


[<span data-ttu-id="4a0c4-200">关于 App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="4a0c4-200">About App-V 5.1</span></span>](about-app-v-51.md)

 

 





