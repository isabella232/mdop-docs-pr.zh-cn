---
title: 为 UE-V 2.x 部署所需功能
description: 为 UE-V 2.x 部署所需功能
author: dansimp
ms.assetid: 10399bb3-cc7b-4578-bc0c-2f6b597abe4d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f2123ec75fb151a8f5b836b9b2522a9d6090b043
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803614"
---
# <span data-ttu-id="618e9-103">为 UE-V 2.x 部署所需功能</span><span class="sxs-lookup"><span data-stu-id="618e9-103">Deploy Required Features for UE-V 2.x</span></span>


<span data-ttu-id="618e9-104">所有 Microsoft 用户体验虚拟化（UE-V）2.0、2.1 和 2.1 SP1 部署都需要这些功能</span><span class="sxs-lookup"><span data-stu-id="618e9-104">All Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, and 2.1 SP1 deployments require these features</span></span>

-   <span data-ttu-id="618e9-105">部署最终用户易于访问的[设置存储位置](#ssl)。</span><span class="sxs-lookup"><span data-stu-id="618e9-105">[Deploy a Settings Storage Location](#ssl) that is accessible to end users.</span></span>

    <span data-ttu-id="618e9-106">这是一个标准的网络共享，用于存储和检索用户设置。</span><span class="sxs-lookup"><span data-stu-id="618e9-106">This is a standard network share that stores and retrieves user settings.</span></span>

-   [<span data-ttu-id="618e9-107">选择 UE-V 的配置方法</span><span class="sxs-lookup"><span data-stu-id="618e9-107">Choose the Configuration Method for UE-V</span></span>](#config)

    <span data-ttu-id="618e9-108">可以使用通用管理工具（包括组策略、配置管理器或 Windows 管理基础结构和 Powershell）部署和配置 UE-V。</span><span class="sxs-lookup"><span data-stu-id="618e9-108">UE-V can be deployed and configured using common management tools including group policy, Configuration Manager, or Windows Management Infrastructure and Powershell.</span></span>

-   <span data-ttu-id="618e9-109">部署要在同步设置的每台计算机上安装的[Ue-v Agent](#agent) 。</span><span class="sxs-lookup"><span data-stu-id="618e9-109">[Deploy a UE-V Agent](#agent) to be installed on every computer that synchronizes settings.</span></span>

    <span data-ttu-id="618e9-110">这将监视已注册应用程序和操作系统的任何设置更改，并在计算机之间同步这些设置。</span><span class="sxs-lookup"><span data-stu-id="618e9-110">This monitors registered applications and the operating system for any settings changes and synchronizes those settings between computers.</span></span>

<span data-ttu-id="618e9-111">本部分中的主题介绍了如何部署这些功能。</span><span class="sxs-lookup"><span data-stu-id="618e9-111">The topics in this section describe how to deploy these features.</span></span>

## <a href="" id="ssl"></a><span data-ttu-id="618e9-112">部署 UE-V 设置存储位置</span><span class="sxs-lookup"><span data-stu-id="618e9-112">Deploy a UE-V Settings Storage Location</span></span>


<span data-ttu-id="618e9-113">UE-V 需要在设置包文件中存储用户设置的位置。</span><span class="sxs-lookup"><span data-stu-id="618e9-113">UE-V requires a location in which to store user settings in settings package files.</span></span> <span data-ttu-id="618e9-114">你可以通过以下方式之一配置此设置存储位置：</span><span class="sxs-lookup"><span data-stu-id="618e9-114">You can configure this settings storage location in one of these ways:</span></span>

-   <span data-ttu-id="618e9-115">创建您自己的设置存储位置</span><span class="sxs-lookup"><span data-stu-id="618e9-115">Create your own settings storage location</span></span>

-   <span data-ttu-id="618e9-116">将现有 Active Directory 用于设置存储位置</span><span class="sxs-lookup"><span data-stu-id="618e9-116">Use existing Active Directory for your settings storage location</span></span>

<span data-ttu-id="618e9-117">如果不创建设置存储位置，则 UE-V Agent 默认情况下将使用 Active Directory （AD）。</span><span class="sxs-lookup"><span data-stu-id="618e9-117">If you don’t create a settings storage location, the UE-V Agent will use Active Directory (AD) by default.</span></span>

**<span data-ttu-id="618e9-118">注意</span><span class="sxs-lookup"><span data-stu-id="618e9-118">Note</span></span>**  
<span data-ttu-id="618e9-119">作为[性能和容量规划](https://technet.microsoft.com/library/dn458932.aspx#capacity)以及减少网络延迟问题，请在用户计算机所在的同一本地网络上创建设置存储位置。</span><span class="sxs-lookup"><span data-stu-id="618e9-119">As a matter of [performance and capacity planning](https://technet.microsoft.com/library/dn458932.aspx#capacity) and to reduce problems with network latency, create settings storage locations on the same local networks where the users’ computers reside.</span></span> <span data-ttu-id="618e9-120">我们建议每个用户 20 MB 的磁盘空间用于设置存储位置。</span><span class="sxs-lookup"><span data-stu-id="618e9-120">We recommend 20 MB of disk space per user for the settings storage location.</span></span>



### <span data-ttu-id="618e9-121">创建 UE-V 设置存储位置</span><span class="sxs-lookup"><span data-stu-id="618e9-121">Create a UE-V Settings Storage Location</span></span>

<span data-ttu-id="618e9-122">在定义设置存储位置之前，必须为在共享上存储设置的用户创建一个具有读/写权限的 root 目录。</span><span class="sxs-lookup"><span data-stu-id="618e9-122">Before you define the settings storage location, you must create a root directory with read/write permissions for users who store settings on the share.</span></span> <span data-ttu-id="618e9-123">UE-V Agent 在此根目录下创建特定于用户的文件夹。</span><span class="sxs-lookup"><span data-stu-id="618e9-123">The UE-V Agent creates user-specific folders under this root directory.</span></span>

<span data-ttu-id="618e9-124">设置存储位置通过设置 SettingsStoragePath 配置选项来定义，可通过以下方法之一进行配置：</span><span class="sxs-lookup"><span data-stu-id="618e9-124">The settings storage location is defined by setting the SettingsStoragePath configuration option, which you can configure by using one of these methods:</span></span>

-   <span data-ttu-id="618e9-125">通过命令行参数或在批处理脚本中[部署 Ue-v Agent](#agent)时</span><span class="sxs-lookup"><span data-stu-id="618e9-125">When you [Deploy the UE-V Agent](#agent) through a command-line parameter or in a batch script</span></span>

-   <span data-ttu-id="618e9-126">通过[组策略](https://technet.microsoft.com/library/dn458893.aspx)设置</span><span class="sxs-lookup"><span data-stu-id="618e9-126">Through [Group Policy](https://technet.microsoft.com/library/dn458893.aspx) settings</span></span>

-   <span data-ttu-id="618e9-127">对于 UE-V 的[System Center 配置包](https://technet.microsoft.com/library/dn458917.aspx)</span><span class="sxs-lookup"><span data-stu-id="618e9-127">With the [System Center Configuration Pack](https://technet.microsoft.com/library/dn458917.aspx) for UE-V</span></span>

-   <span data-ttu-id="618e9-128">在安装 UE-V Agent 之后，使用[Windows PowerShell 或 Windows Management Instrumentation （WMI）](https://technet.microsoft.com/library/dn458937.aspx)</span><span class="sxs-lookup"><span data-stu-id="618e9-128">After installation of the UE-V Agent, by using [Windows PowerShell or Windows Management Instrumentation (WMI)](https://technet.microsoft.com/library/dn458937.aspx)</span></span>

<span data-ttu-id="618e9-129">路径必须位于服务器和共享的通用命名约定（UNC）路径中。</span><span class="sxs-lookup"><span data-stu-id="618e9-129">The path must be in a universal naming convention (UNC) path of the server and share.</span></span> <span data-ttu-id="618e9-130">例如， **\\\\Server\\Settingsshare\\**。</span><span class="sxs-lookup"><span data-stu-id="618e9-130">For example, **\\\\Server\\Settingsshare\\**.</span></span> <span data-ttu-id="618e9-131">此配置选项支持使用变量来启用特定的同步方案。</span><span class="sxs-lookup"><span data-stu-id="618e9-131">This configuration option supports the use of variables to enable specific synchronization scenarios.</span></span> <span data-ttu-id="618e9-132">例如，你可以 `%username%\%computername%` 在以下情况下使用变量来保留最终用户设置体验：</span><span class="sxs-lookup"><span data-stu-id="618e9-132">For example, you can use the `%username%\%computername%` variables to preserve the end user settings experience in these scenarios:</span></span>

-   <span data-ttu-id="618e9-133">在您的企业中使用多台物理计算机的最终用户</span><span class="sxs-lookup"><span data-stu-id="618e9-133">End users that use multiple physical computers in your enterprise</span></span>

-   <span data-ttu-id="618e9-134">多个最终用户使用的企业计算机</span><span class="sxs-lookup"><span data-stu-id="618e9-134">Enterprise computers that are used by multiple end users</span></span>

<span data-ttu-id="618e9-135">UE-V Agent `SettingsPackages` 基于**SettingsStoragePath**的配置设置，动态创建一个特定于用户的设置存储路径，该路径具有一个名为的隐藏系统文件夹。</span><span class="sxs-lookup"><span data-stu-id="618e9-135">The UE-V Agent dynamically creates a user-specific settings storage path, with a hidden system folder named `SettingsPackages`, based on the configuration setting of **SettingsStoragePath**.</span></span> <span data-ttu-id="618e9-136">代理读取并将设置写入到此位置，如注册的 UE-V 设置位置模板所定义。</span><span class="sxs-lookup"><span data-stu-id="618e9-136">The agent reads and writes settings to this location as defined by the registered UE-V settings location templates.</span></span>

<span data-ttu-id="618e9-137">**Ue-v 设置由 "最后一次写入的 wins" 规则确定：** 如果对于具有多台托管计算机的用户而言，设置存储位置是相同的，则一个 UE-V Agent 将在其他计算机上运行的代理独立地读取和写入设置位置。</span><span class="sxs-lookup"><span data-stu-id="618e9-137">**UE-V settings are determined by a "Last write wins" rule:** If the settings storage location is the same for user with multiple managed computers, one UE-V Agent reads and writes to the settings location independently of agents running on other computers.</span></span> <span data-ttu-id="618e9-138">最后写入的设置和值是在下一个代理从设置存储位置读取时应用的值。</span><span class="sxs-lookup"><span data-stu-id="618e9-138">The last written settings and values are the ones applied when the next agent reads from the settings storage location.</span></span>

<span data-ttu-id="618e9-139">**部署设置存储位置：** 请按照以下步骤定义设置存储位置，而不是使用现有的 Active Directory 服务。</span><span class="sxs-lookup"><span data-stu-id="618e9-139">**Deploy the settings storage location:** Follow these steps to define the settings storage location rather than using your existing Active Directory service.</span></span> <span data-ttu-id="618e9-140">你应该将对设置存储共享的访问限制到需要它的用户，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="618e9-140">You should limit access to the settings storage share to those users that require it, as shown in the tables below.</span></span>

**<span data-ttu-id="618e9-141">部署 UE-V 网络共享</span><span class="sxs-lookup"><span data-stu-id="618e9-141">To deploy the UE-V network share</span></span>**

1.  <span data-ttu-id="618e9-142">为 UE-V 用户创建新的安全组。</span><span class="sxs-lookup"><span data-stu-id="618e9-142">Create a new security group for UE-V users.</span></span>

2.  <span data-ttu-id="618e9-143">在存储 UE-V settings 程序包的集中位置的计算机上创建一个新文件夹，然后向 UE-V 用户授予对该文件夹的组权限。</span><span class="sxs-lookup"><span data-stu-id="618e9-143">Create a new folder on the centrally located computer that stores the UE-V settings packages, and then grant the UE-V users access with group permissions to the folder.</span></span> <span data-ttu-id="618e9-144">支持 UE-V 的管理员必须具有此共享文件夹的权限。</span><span class="sxs-lookup"><span data-stu-id="618e9-144">The administrator who supports UE-V must have permissions to this shared folder.</span></span>

3.  <span data-ttu-id="618e9-145">为 "设置存储位置" 文件夹设置以下共享级服务器消息块（SMB）权限。</span><span class="sxs-lookup"><span data-stu-id="618e9-145">Set the following share-level Server Message Block (SMB) permissions for the settings storage location folder.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong><span data-ttu-id="618e9-146">用户帐户</span><span class="sxs-lookup"><span data-stu-id="618e9-146">User account</span></span></strong></th>
    <th align="left"><strong><span data-ttu-id="618e9-147">推荐的权限</span><span class="sxs-lookup"><span data-stu-id="618e9-147">Recommended permissions</span></span></strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="618e9-148">所有人</span><span class="sxs-lookup"><span data-stu-id="618e9-148">Everyone</span></span></p></td>
    <td align="left"><p><span data-ttu-id="618e9-149">无权限</span><span class="sxs-lookup"><span data-stu-id="618e9-149">No permissions</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="618e9-150">UE-V 用户的安全组</span><span class="sxs-lookup"><span data-stu-id="618e9-150">Security group of UE-V users</span></span></p></td>
    <td align="left"><p><span data-ttu-id="618e9-151">完全控制</span><span class="sxs-lookup"><span data-stu-id="618e9-151">Full control</span></span></p></td>
    </tr>
    </tbody>
    </table>



4.  <span data-ttu-id="618e9-152">为 "设置存储位置" 文件夹设置以下 NTFS 文件系统权限。</span><span class="sxs-lookup"><span data-stu-id="618e9-152">Set the following NTFS file system permissions for the settings storage location folder.</span></span>

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong><span data-ttu-id="618e9-153">用户帐户</span><span class="sxs-lookup"><span data-stu-id="618e9-153">User account</span></span></strong></th>
    <th align="left"><strong><span data-ttu-id="618e9-154">推荐的权限</span><span class="sxs-lookup"><span data-stu-id="618e9-154">Recommended permissions</span></span></strong></th>
    <th align="left"><strong><span data-ttu-id="618e9-155">文件夹</span><span class="sxs-lookup"><span data-stu-id="618e9-155">Folder</span></span></strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="618e9-156">创建者/所有者</span><span class="sxs-lookup"><span data-stu-id="618e9-156">Creator/owner</span></span></p></td>
    <td align="left"><p><span data-ttu-id="618e9-157">完全控制</span><span class="sxs-lookup"><span data-stu-id="618e9-157">Full control</span></span></p></td>
    <td align="left"><p><span data-ttu-id="618e9-158">仅子文件夹和文件</span><span class="sxs-lookup"><span data-stu-id="618e9-158">Subfolders and files only</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="618e9-159">UE-V 用户的安全组</span><span class="sxs-lookup"><span data-stu-id="618e9-159">Security group of UE-V users</span></span></p></td>
    <td align="left"><p><span data-ttu-id="618e9-160">列出文件夹/读取数据、创建文件夹/附加数据</span><span class="sxs-lookup"><span data-stu-id="618e9-160">List folder/read data, create folders/append data</span></span></p></td>
    <td align="left"><p><span data-ttu-id="618e9-161">仅此文件夹</span><span class="sxs-lookup"><span data-stu-id="618e9-161">This folder only</span></span></p></td>
    </tr>
    </tbody>
    </table>



<span data-ttu-id="618e9-162">通过此配置，UE-V Agent 在用户的上下文中运行时创建并保护 Settingspackage 文件夹，并授予每个用户创建设置存储文件夹的权限。</span><span class="sxs-lookup"><span data-stu-id="618e9-162">With this configuration, the UE-V Agent creates and secures a Settingspackage folder while it runs in the context of the user, and grants each user permission to create folders for settings storage.</span></span> <span data-ttu-id="618e9-163">用户接收 Settingspackage 文件夹的完全控制，而其他用户无法访问它。</span><span class="sxs-lookup"><span data-stu-id="618e9-163">Users receive full control to their Settingspackage folder while other users cannot access it.</span></span>

**<span data-ttu-id="618e9-164">注意</span><span class="sxs-lookup"><span data-stu-id="618e9-164">Note</span></span>**  
<span data-ttu-id="618e9-165">如果在运行 Windows Server 操作系统的计算机上创建设置存储共享，请配置 UE-V 以验证本地管理员组或当前用户是否为存储设置包的文件夹的所有者。</span><span class="sxs-lookup"><span data-stu-id="618e9-165">If you create the settings storage share on a computer running a Windows Server operating system, configure UE-V to verify that either the local Administrators group or the current user is the owner of the folder where settings packages are stored.</span></span> <span data-ttu-id="618e9-166">若要启用此附加安全性，请在 Windows Server 注册表编辑器中指定此设置：</span><span class="sxs-lookup"><span data-stu-id="618e9-166">To enable this additional security, specify this setting in the Windows Server Registry Editor:</span></span>

1.  <span data-ttu-id="618e9-167">将名为 **"RepositoryOwnerCheckEnabled"** 的**REG \ _DWORD**注册表项添加到**HKEY \ _LOCAL \ _MACHINE \\software\\microsoft\\uev\\agent\\configuration**。</span><span class="sxs-lookup"><span data-stu-id="618e9-167">Add a **REG\_DWORD** registry key named **"RepositoryOwnerCheckEnabled"** to **HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\UEV\\Agent\\Configuration**.</span></span>

2.  <span data-ttu-id="618e9-168">将注册表项值设置为*1*。</span><span class="sxs-lookup"><span data-stu-id="618e9-168">Set the registry key value to *1*.</span></span>



### <span data-ttu-id="618e9-169">将 Active Directory 与 UE-V 2. x 配合使用</span><span class="sxs-lookup"><span data-stu-id="618e9-169">Use Active Directory with UE-V 2.x</span></span>

<span data-ttu-id="618e9-170">如果未另外定义设置存储位置，则 UE-V Agent 默认使用 Active Directory （AD）。</span><span class="sxs-lookup"><span data-stu-id="618e9-170">The UE-V Agent uses Active Directory (AD) by default if a settings storage location is not otherwise defined.</span></span> <span data-ttu-id="618e9-171">在这些情况下，UE-V Agent 会在每个用户的广告主目录的根目录下动态创建设置存储文件夹。</span><span class="sxs-lookup"><span data-stu-id="618e9-171">In these cases, the UE-V Agent dynamically creates the settings storage folder under the root of the AD home directory of each user.</span></span> <span data-ttu-id="618e9-172">但是，如果在 AD 中配置了自定义目录设置，则改为使用该目录。</span><span class="sxs-lookup"><span data-stu-id="618e9-172">But, if a custom directory setting is configured in AD, then that directory is used instead.</span></span>

## <a href="" id="config"></a><span data-ttu-id="618e9-173">选择 UE-V 2 的配置方法。</span><span class="sxs-lookup"><span data-stu-id="618e9-173">Choose the Configuration Method for UE-V 2.x</span></span>


<span data-ttu-id="618e9-174">你想要确定你将用于在部署后管理 UE-V 的配置方法，因为这将是你用于部署 UE-V Agent 的配置方法。</span><span class="sxs-lookup"><span data-stu-id="618e9-174">You want to figure out which configuration method you'll use to manage UE-V after deployment since this will be the configuration method you use to deploy the UE-V Agent.</span></span> <span data-ttu-id="618e9-175">通常，这是你已在你的环境中使用的配置方法，例如 Windows PowerShell 或配置管理器。</span><span class="sxs-lookup"><span data-stu-id="618e9-175">Typically, this is the configuration method that you already use in your environment, such as Windows PowerShell or Configuration Manager.</span></span>

<span data-ttu-id="618e9-176">你可以在 UE-V Agent 安装前后配置 UE-V，具体取决于你使用的配置方法。</span><span class="sxs-lookup"><span data-stu-id="618e9-176">You can configure UE-V before, during, or after UE-V Agent installation, depending on the configuration method that you use.</span></span>

-   <span data-ttu-id="618e9-177">[组策略](https://technet.microsoft.com/library/dn458893.aspx)**：** 您可以使用现有的组策略结构在 ue-v agent 部署之前或之后配置 ue-v。</span><span class="sxs-lookup"><span data-stu-id="618e9-177">[Group Policy](https://technet.microsoft.com/library/dn458893.aspx)**:** You can use your existing Group Policy infrastructure to configure UE-V before or after UE-V Agent deployment.</span></span> <span data-ttu-id="618e9-178">UE-V 组策略 ADMX 模板支持集中管理常见的 UE-V Agent 配置选项，其中包括用于配置 UE-V 同步的设置。</span><span class="sxs-lookup"><span data-stu-id="618e9-178">The UE-V Group Policy ADMX template enables the central management of common UE-V Agent configuration options, and it includes settings to configure UE-V synchronization.</span></span>

    <span data-ttu-id="618e9-179">**安装 Ue-v 组策略 ADMX 模板：** UE-V 的组策略 ADMX 模板配置 UE-V Agent 的同步设置，并通过使用现有的组策略基础结构启用常见 UE-V Agent 配置设置的集中管理。</span><span class="sxs-lookup"><span data-stu-id="618e9-179">**Installing the UE-V Group Policy ADMX Templates:** Group Policy ADMX templates for UE-V configure the synchronization settings for the UE-V Agent and enable the central management of common UE-V Agent configuration settings by using an existing Group Policy infrastructure.</span></span>

    <span data-ttu-id="618e9-180">部署组策略对象的域控制器支持的操作系统包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="618e9-180">Supported operating systems for the domain controller that deploys the Group Policy Objects include the following:</span></span>

    <span data-ttu-id="618e9-181">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="618e9-181">Windows Server 2008 R2</span></span>

    <span data-ttu-id="618e9-182">Windows Server 2012 和 Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="618e9-182">Windows Server 2012 and Windows Server 2012 R2</span></span>

-   <span data-ttu-id="618e9-183">[配置管理器](https://technet.microsoft.com/library/dn458917.aspx)**：** ue-v 配置包使你可以使用 System Center configuration Manager 2012 SP1 或更高版本的合规性设置功能在安装了 ue-v 和配置管理器的网站之间应用一致的配置。</span><span class="sxs-lookup"><span data-stu-id="618e9-183">[Configuration Manager](https://technet.microsoft.com/library/dn458917.aspx)**:** The UE-V Configuration Pack lets you use the Compliance Settings feature of System Center Configuration Manager 2012 SP1 or later to apply consistent configurations across sites where UE-V and Configuration Manager are installed.</span></span>

-   <span data-ttu-id="618e9-184">[Windows powershell 和 WMI](https://technet.microsoft.com/library/dn458937.aspx)**：** 你可以使用 windows powershell 和 windows Management Instrumentation （WMI）的脚本命令在安装 ue-v Agent 后修改配置。</span><span class="sxs-lookup"><span data-stu-id="618e9-184">[Windows PowerShell and WMI](https://technet.microsoft.com/library/dn458937.aspx)**:** You can use scripted commands for Windows PowerShell and Windows Management Instrumentation (WMI) to modify configurations after you install the UE-V Agent.</span></span>

    **<span data-ttu-id="618e9-185">注意</span><span class="sxs-lookup"><span data-stu-id="618e9-185">Note</span></span>**  
    <span data-ttu-id="618e9-186">注册表修改可能导致数据丢失或计算机无法响应。</span><span class="sxs-lookup"><span data-stu-id="618e9-186">Registry modification can result in data loss, or the computer becomes unresponsive.</span></span> <span data-ttu-id="618e9-187">我们建议你使用其他配置方法。</span><span class="sxs-lookup"><span data-stu-id="618e9-187">We recommend that you use other configuration methods.</span></span>



-   <span data-ttu-id="618e9-188">**命令行或批处理脚本安装：**[部署 Ue-v Agent](#agent)时使用的参数配置许多 ue-v 设置。</span><span class="sxs-lookup"><span data-stu-id="618e9-188">**Command-line or Batch Script Installation:** Parameters that are used when you [Deploy the UE-V Agent](#agent) configure many UE-V settings.</span></span> <span data-ttu-id="618e9-189">电子软件分发系统（如 System Center 2012 配置管理器）在部署和安装 UE-V Agent 软件时使用这些参数配置其客户端。</span><span class="sxs-lookup"><span data-stu-id="618e9-189">Electronic software distribution systems, such as System Center 2012 Configuration Manager, use these parameters to configure their clients when they deploy and install the UE-V Agent software.</span></span>

## <a href="" id="agent"></a><span data-ttu-id="618e9-190">部署 UE-V 2. x 代理</span><span class="sxs-lookup"><span data-stu-id="618e9-190">Deploy the UE-V 2.x Agent</span></span>


<span data-ttu-id="618e9-191">UE-V Agent 是 UE-V 部署的核心，并且必须在使用 UE-V 的每台计算机上运行以同步应用程序和 Windows 设置。</span><span class="sxs-lookup"><span data-stu-id="618e9-191">The UE-V Agent is the core of a UE-V deployment and must run on each computer that uses UE-V to synchronize application and Windows settings.</span></span>

<span data-ttu-id="618e9-192">**Ue-v Agent 安装文件：** AgentSetup.exe 在32位和64位操作系统上安装 UE-V Agent 的单个安装文件。</span><span class="sxs-lookup"><span data-stu-id="618e9-192">**UE-V Agent Installation Files:** A single installation file, AgentSetup.exe, installs the UE-V Agent on both 32-bit and 64-bit operating systems.</span></span> <span data-ttu-id="618e9-193">此外，提供了 AgentSetupx86.msi 或 AgentSetupx64.msi 体系结构特定的 Windows Installer 文件，由于它们较小，因此它们可能会简化代理部署。</span><span class="sxs-lookup"><span data-stu-id="618e9-193">In addition, AgentSetupx86.msi or AgentSetupx64.msi architecture-specific Windows Installer files are provided, and since they are smaller, they might streamline the agent deployments.</span></span> <span data-ttu-id="618e9-194">Windows Installer 安装还支持[AgentSetup.exe 安装程序的命令行参数](#params)。</span><span class="sxs-lookup"><span data-stu-id="618e9-194">The [command-line parameters for the AgentSetup.exe installer](#params) are supported for the Windows Installer installation as well.</span></span>

**<span data-ttu-id="618e9-195">重要提示</span><span class="sxs-lookup"><span data-stu-id="618e9-195">Important</span></span>**  
<span data-ttu-id="618e9-196">在 UE-V Agent 安装或卸载期间，你可以使用 AgentSetup.exe 文件或 AgentSetup xxx &lt; &gt; 文件，但不能同时使用这两者。</span><span class="sxs-lookup"><span data-stu-id="618e9-196">During UE-V Agent installation or uninstallation, you can either use the AgentSetup.exe file or the AgentSetup&lt;arch&gt;.msi file, but not both.</span></span> <span data-ttu-id="618e9-197">必须使用相同的文件卸载用于安装 UE-V Agent 的 UE-V Agent 程序。</span><span class="sxs-lookup"><span data-stu-id="618e9-197">The same file must be used to uninstall the UE-V Agent that was used to install the UE-V Agent.</span></span>



### <span data-ttu-id="618e9-198">部署 UE-V Agent</span><span class="sxs-lookup"><span data-stu-id="618e9-198">To Deploy the UE-V Agent</span></span>

<span data-ttu-id="618e9-199">你可以使用以下方法来部署 UE-V Agent：</span><span class="sxs-lookup"><span data-stu-id="618e9-199">You can use the following methods to deploy the UE-V Agent:</span></span>

-   <span data-ttu-id="618e9-200">可安装 Windows Installer （.msi）文件的电子软件分发（ESD）解决方案系统（如配置管理器）。</span><span class="sxs-lookup"><span data-stu-id="618e9-200">An electronic software distribution (ESD) solution system, such as Configuration Manager, that can install a Windows Installer (.msi) file.</span></span>

-   <span data-ttu-id="618e9-201">一个安装脚本，它引用在一个共享位置集中存储的 Windows Installer （.msi）文件。</span><span class="sxs-lookup"><span data-stu-id="618e9-201">An installation script that references the Windows Installer (.msi) file that is stored centrally on a share.</span></span>

-   <span data-ttu-id="618e9-202">在计算机上手动运行的安装程序。</span><span class="sxs-lookup"><span data-stu-id="618e9-202">An installation program that you run manually on the computer.</span></span>

<span data-ttu-id="618e9-203">使用以下过程从网络共享部署 UE-V Agent。</span><span class="sxs-lookup"><span data-stu-id="618e9-203">Use the following procedure to deploy the UE-V Agent from a network share.</span></span>

**<span data-ttu-id="618e9-204">从网络共享安装和配置 UE-V Agent</span><span class="sxs-lookup"><span data-stu-id="618e9-204">To install and configure the UE-V Agent from a network share</span></span>**

1.  <span data-ttu-id="618e9-205">在用户具有 "读取" 权限的网络共享上，暂存 UE-V Agent 安装文件 AgentSetup.exe。</span><span class="sxs-lookup"><span data-stu-id="618e9-205">Stage the UE-V Agent installation file AgentSetup.exe on a network share to which users have Read permission.</span></span>

2.  <span data-ttu-id="618e9-206">将脚本部署到安装 UE-V Agent 的用户计算机。</span><span class="sxs-lookup"><span data-stu-id="618e9-206">Deploy a script to user computers that installs the UE-V Agent.</span></span> <span data-ttu-id="618e9-207">脚本应指定设置存储位置。</span><span class="sxs-lookup"><span data-stu-id="618e9-207">The script should specify the settings storage location.</span></span>

<span data-ttu-id="618e9-208">**部署选项：** 请确保在安装 UE-V Agent 时使用正确的变量格式。</span><span class="sxs-lookup"><span data-stu-id="618e9-208">**Deployment options:** Be sure to use the correct variable format when you install the UE-V Agent.</span></span> <span data-ttu-id="618e9-209">下表提供了使用 AgentSetup.exe 或 Windows Installer （.msi）文件的部署选项的示例。</span><span class="sxs-lookup"><span data-stu-id="618e9-209">The following table provides examples of deployment options for using the AgentSetup.exe or the Windows Installer (.msi) files.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="618e9-210">部署类型</span><span class="sxs-lookup"><span data-stu-id="618e9-210">Deployment type</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="618e9-211">部署说明</span><span class="sxs-lookup"><span data-stu-id="618e9-211">Deployment description</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="618e9-212">示例</span><span class="sxs-lookup"><span data-stu-id="618e9-212">Example</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="618e9-213">命令提示符</span><span class="sxs-lookup"><span data-stu-id="618e9-213">Command prompt</span></span></p></td>
<td align="left"><p><span data-ttu-id="618e9-214">在命令提示符处安装 UE-V Agent 时，请使用 <em> % ^ username% </em> 变量格式。</span><span class="sxs-lookup"><span data-stu-id="618e9-214">When you install the UE-V Agent at a command prompt, use the <em>%^username%</em> variable format.</span></span> <span data-ttu-id="618e9-215">如果由于设置存储路径中的空格而需要引号，请使用批处理脚本文件进行部署。</span><span class="sxs-lookup"><span data-stu-id="618e9-215">If quotation marks are required because of spaces in the settings storage path, use a batch script file for deployment.</span></span></p>
<p></p></td>
<td align="left"><p><code>AgentSetup.exe /quiet /norestart /log &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare%^username%</code></p>
<p></p>
<p><code>msiexec.exe /i &quot;&lt;path to msi file&gt;&quot; /quiet /norestart /l<em>v &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare%^username%</code></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="618e9-216">批处理脚本</span><span class="sxs-lookup"><span data-stu-id="618e9-216">Batch script</span></span></p></td>
<td align="left"><p><span data-ttu-id="618e9-217">从批处理脚本文件安装 UE-V Agent 时，请使用 <em> %% 用户名%% </em> 变量格式。</span><span class="sxs-lookup"><span data-stu-id="618e9-217">When you install the UE-V Agent from a batch script file, use the <em>%%username%%</em> variable format.</span></span> <span data-ttu-id="618e9-218">如果使用此安装方法，则必须使用%% 字符转义变量。</span><span class="sxs-lookup"><span data-stu-id="618e9-218">If you use this installation method, you must escape the variable with the %% characters.</span></span> <span data-ttu-id="618e9-219">如果没有此字符，脚本将 <em> </em> 在安装时（而不是在运行时）扩展用户名变量，从而导致 ue-v 对所有用户使用单个设置存储位置。</span><span class="sxs-lookup"><span data-stu-id="618e9-219">Without this character, the script expands the <em>username</em> variable at installation time, rather than at run time, which causes UE-V to use a single settings storage location for all users.</span></span></p></td>
<td align="left"><p><code>AgentSetup.exe /quiet /norestart /log &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=&quot;\server\settingsshare%%username%%&quot;</code></p>
<p></p>
<p><code>msiexec.exe /i &quot;&lt;path to msi file&gt;&quot; /quiet /norestart /l</em>v &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=&quot;\server\settingsshare%%username%%&quot;</code></p>
<p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="618e9-220">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="618e9-220">Windows PowerShell</span></span></p></td>
<td align="left"><p><span data-ttu-id="618e9-221">从 Windows PowerShell 提示或 Windows PowerShell 脚本安装 UE-V Agent 时，请使用 <em> % username% </em> 变量格式。</span><span class="sxs-lookup"><span data-stu-id="618e9-221">When you install the UE-V Agent from a Windows PowerShell prompt or a Windows PowerShell script, use the <em>%username%</em> variable format.</span></span></p></td>
<td align="left"><p><code>&amp; AgentSetup.exe /quiet /norestart /log &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare%username%</code></p>
<p></p>
<p><code>&amp; msiexec.exe /i &quot;&lt;path to msi file&gt;&quot; /quiet /norestart /l<em>v &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare%username%</code></p>
<p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="618e9-222">电子软件分发，如 Configuration Manager 软件部署的部署</span><span class="sxs-lookup"><span data-stu-id="618e9-222">Electronic software distribution, such as deployment of Configuration Manager Software Deployment</span></span></p></td>
<td align="left"><p><span data-ttu-id="618e9-223">使用配置管理器安装 UE-V Agent 时，请使用 <em> ^% 用户名 ^% </em> 变量格式。</span><span class="sxs-lookup"><span data-stu-id="618e9-223">When you install the UE-V Agent by using Configuration Manager, use the <em>^%username^%</em> variable format.</span></span></p></td>
<td align="left"><p><code>AgentSetup.exe /quiet /norestart /log &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare^%username^%</code></p>
<p></p>
<p><code>msiexec.exe /i &quot;&lt;path to msi file&gt;&quot; /quiet /norestart /l</em>v &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare^%username^%</code></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="618e9-224">注意</span><span class="sxs-lookup"><span data-stu-id="618e9-224">Note</span></span>**  
<span data-ttu-id="618e9-225">UE-V Agent 的安装需要管理员权限，并且计算机需要重启才能运行 UE-V Agent。</span><span class="sxs-lookup"><span data-stu-id="618e9-225">The installation of the UE-V Agent requires administrator rights, and the computer requires a restart before the UE-V Agent can run.</span></span>



### <a href="" id="params"></a><span data-ttu-id="618e9-226">UE-V Agent 部署的命令行参数</span><span class="sxs-lookup"><span data-stu-id="618e9-226">Command-line parameters for UE-V Agent deployment</span></span>

<span data-ttu-id="618e9-227">UE-V Agent 的命令行参数如下所示。</span><span class="sxs-lookup"><span data-stu-id="618e9-227">The command-line parameters of the UE-V Agent are as follows.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="618e9-228">命令行参数</span><span class="sxs-lookup"><span data-stu-id="618e9-228">Command-line parameter</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="618e9-229">定义</span><span class="sxs-lookup"><span data-stu-id="618e9-229">Definition</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="618e9-230">注释</span><span class="sxs-lookup"><span data-stu-id="618e9-230">Notes</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="618e9-231">/help 或/h 或/？</span><span class="sxs-lookup"><span data-stu-id="618e9-231">/help or /h or /?</span></span></p></td>
<td align="left"><p><span data-ttu-id="618e9-232">显示 "AgentSetup.exe 用法" 对话框。</span><span class="sxs-lookup"><span data-stu-id="618e9-232">Displays the AgentSetup.exe usage dialog box.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="618e9-233">SettingsStoragePath</span><span class="sxs-lookup"><span data-stu-id="618e9-233">SettingsStoragePath</span></span></p></td>
<td align="left"><p><span data-ttu-id="618e9-234">指示用于定义存储设置的位置的通用命名约定（UNC）路径。</span><span class="sxs-lookup"><span data-stu-id="618e9-234">Indicates the Universal Naming Convention (UNC) path that defines where settings are stored.</span></span></p></td>
<td align="left"><div class="alert">
<strong><span data-ttu-id="618e9-235">重要提示</span><span class="sxs-lookup"><span data-stu-id="618e9-235">Important</span></span></strong><br/><p><span data-ttu-id="618e9-236">必须在 UE-V 2.1 和 UE-V 2.1 SP1 中指定 SettingsStoragePath。</span><span class="sxs-lookup"><span data-stu-id="618e9-236">You must specify a SettingsStoragePath in UE-V 2.1 and UE-V 2.1 SP1.</span></span> <span data-ttu-id="618e9-237">你可以设置 AdHomePath 字符串以指定使用用户&#39;s Active Directory 主路径。</span><span class="sxs-lookup"><span data-stu-id="618e9-237">You can set the AdHomePath string to specify that the user&#39;s Active Directory home path is used.</span></span> <span data-ttu-id="618e9-238">例如，<code>SettingsStoragePath = \share\path|AdHomePath</code>。</span><span class="sxs-lookup"><span data-stu-id="618e9-238">For example, <code>SettingsStoragePath = \share\path|AdHomePath</code>.</span></span></p>
<p><span data-ttu-id="618e9-239">在 UE-V 2.0 中，可以将 SettingsStoragePath 保留为空，以改用 Active Directory 主路径。</span><span class="sxs-lookup"><span data-stu-id="618e9-239">In UE-V 2.0, you can leave SettingsStoragePath blank to use the Active Directory home path instead.</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="618e9-240">已接受% 用户名% 或% computername% 环境变量。</span><span class="sxs-lookup"><span data-stu-id="618e9-240">%username% or %computername% environment variables are accepted.</span></span> <span data-ttu-id="618e9-241">脚本可能需要转义变量。</span><span class="sxs-lookup"><span data-stu-id="618e9-241">Scripting can require escaped variables.</span></span></p>
<p><strong><span data-ttu-id="618e9-242">默认 </strong> ： &lt; 无&gt;</span><span class="sxs-lookup"><span data-stu-id="618e9-242">Default</strong>: &lt;none&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="618e9-243">SettingsStoragePathReg</span><span class="sxs-lookup"><span data-stu-id="618e9-243">SettingsStoragePathReg</span></span></p></td>
<td align="left"><p><span data-ttu-id="618e9-244">在安装期间获取来自注册表的 SettingsStoragePath 值。</span><span class="sxs-lookup"><span data-stu-id="618e9-244">Gets the SettingsStoragePath value from the registry during installation.</span></span></p></td>
<td align="left"><p><span data-ttu-id="618e9-245">在命令提示符处，键入以下示例，强制 UE-V 使用 Active Directory 主路径，而不是特定的 UNC。</span><span class="sxs-lookup"><span data-stu-id="618e9-245">At the command prompt, type the following example to force UE-V to use the Active Directory home path instead of a specific UNC.</span></span></p>
<p><code>msiexec.exe /i AgentSetupx64.msi acceptlicenseterms=true SettingsStoragePathReg=TRUE /quiet /norestart</code></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="618e9-246">SettingsTemplateCatalogPath</span><span class="sxs-lookup"><span data-stu-id="618e9-246">SettingsTemplateCatalogPath</span></span></p></td>
<td align="left"><p><span data-ttu-id="618e9-247">指示用于定义为新设置位置模板检查的位置的通用命名约定（UNC）路径。</span><span class="sxs-lookup"><span data-stu-id="618e9-247">Indicates the Universal Naming Convention (UNC) path that defines the location that was checked for new settings location templates.</span></span></p></td>
<td align="left"><p><span data-ttu-id="618e9-248">仅对于自定义设置位置模板是必需的</span><span class="sxs-lookup"><span data-stu-id="618e9-248">Only required for custom settings location templates</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="618e9-249">RegisterMSTemplates</span><span class="sxs-lookup"><span data-stu-id="618e9-249">RegisterMSTemplates</span></span></p></td>
<td align="left"><p><span data-ttu-id="618e9-250">指定是否应在安装期间注册默认 Microsoft 模板。</span><span class="sxs-lookup"><span data-stu-id="618e9-250">Specifies whether the default Microsoft templates should be registered during installation.</span></span></p></td>
<td align="left"><p><span data-ttu-id="618e9-251">True |;</span><span class="sxs-lookup"><span data-stu-id="618e9-251">True | False</span></span></p>
<p><strong><span data-ttu-id="618e9-252">默认值 </strong> ： True</span><span class="sxs-lookup"><span data-stu-id="618e9-252">Default</strong>: True</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="618e9-253">Powerschool</span><span class="sxs-lookup"><span data-stu-id="618e9-253">SyncMethod</span></span></p></td>
<td align="left"><p><span data-ttu-id="618e9-254">指定应使用的同步方法。</span><span class="sxs-lookup"><span data-stu-id="618e9-254">Specifies which synchronization method should be used.</span></span></p></td>
<td align="left"><p><span data-ttu-id="618e9-255">SyncProvider |尚</span><span class="sxs-lookup"><span data-stu-id="618e9-255">SyncProvider | None</span></span></p>
<p><strong><span data-ttu-id="618e9-256">默认 </strong> ： SyncProvider</span><span class="sxs-lookup"><span data-stu-id="618e9-256">Default</strong>: SyncProvider</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="618e9-257">SyncTimeoutInMilliseconds</span><span class="sxs-lookup"><span data-stu-id="618e9-257">SyncTimeoutInMilliseconds</span></span></p></td>
<td align="left"><p><span data-ttu-id="618e9-258">指定在从设置存储位置检索用户设置时，计算机超时之前等待的毫秒数。</span><span class="sxs-lookup"><span data-stu-id="618e9-258">Specifies the number of milliseconds that the computer waits before time-out when it retrieves user settings from the settings storage location.</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="618e9-259">默认 </strong> ：2000毫秒</span><span class="sxs-lookup"><span data-stu-id="618e9-259">Default</strong>: 2000 milliseconds</span></span></p>
<p><span data-ttu-id="618e9-260">（等待2秒钟）</span><span class="sxs-lookup"><span data-stu-id="618e9-260">(wait up to 2 seconds)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="618e9-261">SyncEnabled</span><span class="sxs-lookup"><span data-stu-id="618e9-261">SyncEnabled</span></span></p></td>
<td align="left"><p><span data-ttu-id="618e9-262">指定是启用还是禁用 UE-V 同步。</span><span class="sxs-lookup"><span data-stu-id="618e9-262">Specifies whether UE-V synchronization is enabled or disabled.</span></span></p></td>
<td align="left"><p><span data-ttu-id="618e9-263">True |;</span><span class="sxs-lookup"><span data-stu-id="618e9-263">True | False</span></span></p>
<p><strong><span data-ttu-id="618e9-264">默认值 </strong> ： True</span><span class="sxs-lookup"><span data-stu-id="618e9-264">Default</strong>: True</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="618e9-265">MaxPackageSizeInBytes</span><span class="sxs-lookup"><span data-stu-id="618e9-265">MaxPackageSizeInBytes</span></span></p></td>
<td align="left"><p><span data-ttu-id="618e9-266">指定当 UE-V Agent 报告文件超过阈值时的设置程序包文件大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="618e9-266">Specifies a settings package file size in bytes when the UE-V Agent reports that files exceed the threshold.</span></span></p></td>
<td align="left"><p><span data-ttu-id="618e9-267">&lt;size&gt;</span><span class="sxs-lookup"><span data-stu-id="618e9-267">&lt;size&gt;</span></span></p>
<p><strong><span data-ttu-id="618e9-268">默认值 </strong> ：无（无警告阈值）</span><span class="sxs-lookup"><span data-stu-id="618e9-268">Default</strong>: none (no warning threshold)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="618e9-269">CEIPEnabled</span><span class="sxs-lookup"><span data-stu-id="618e9-269">CEIPEnabled</span></span></p></td>
<td align="left"><p><span data-ttu-id="618e9-270">指定参与客户体验改善计划的设置。</span><span class="sxs-lookup"><span data-stu-id="618e9-270">Specifies the setting for participation in the Customer Experience Improvement program.</span></span> <span data-ttu-id="618e9-271">如果设置为 <strong> True </strong> ，则将安装程序信息上载到 "Microsoft 客户体验改善计划" 网站。</span><span class="sxs-lookup"><span data-stu-id="618e9-271">If set to <strong>True</strong>, installer information is uploaded to the Microsoft Customer Experience Improvement Program site.</span></span> <span data-ttu-id="618e9-272">如果设置为 <strong> False </strong> ，则不会上载任何信息。</span><span class="sxs-lookup"><span data-stu-id="618e9-272">If set to <strong>False</strong>, no information is uploaded.</span></span></p></td>
<td align="left"><p><span data-ttu-id="618e9-273">True |;</span><span class="sxs-lookup"><span data-stu-id="618e9-273">True | False</span></span></p>
<p><strong><span data-ttu-id="618e9-274">默认值 </strong> ： False</span><span class="sxs-lookup"><span data-stu-id="618e9-274">Default</strong>: False</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="618e9-275">NoRestart</span><span class="sxs-lookup"><span data-stu-id="618e9-275">NoRestart</span></span></p></td>
<td align="left"><p><span data-ttu-id="618e9-276">支持在安装 UE-V Agent 后延迟计算机重启。</span><span class="sxs-lookup"><span data-stu-id="618e9-276">Supports deferral of the restart of the computer after the UE-V Agent is installed.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="618e9-277">INSTALLFOLDER</span><span class="sxs-lookup"><span data-stu-id="618e9-277">INSTALLFOLDER</span></span></p></td>
<td align="left"><p><span data-ttu-id="618e9-278">允许为 UE-V Agent 或 UE-V 发生器设置不同的安装文件夹。</span><span class="sxs-lookup"><span data-stu-id="618e9-278">Enables a different installation folder to be set for the UE-V Agent or UE-V Generator.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="618e9-279">MUENABLED</span><span class="sxs-lookup"><span data-stu-id="618e9-279">MUENABLED</span></span></p></td>
<td align="left"><p><span data-ttu-id="618e9-280">使安装程序能够接受包含在 Microsoft Update 程序中的选项。</span><span class="sxs-lookup"><span data-stu-id="618e9-280">Enables Setup to accept the option to be included in the Microsoft Update program.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="618e9-281">ACCEPTLICENSETERMS</span><span class="sxs-lookup"><span data-stu-id="618e9-281">ACCEPTLICENSETERMS</span></span></p></td>
<td align="left"><p><span data-ttu-id="618e9-282">让 UE-V 可以自行安装。</span><span class="sxs-lookup"><span data-stu-id="618e9-282">Lets UE-V be installed silently.</span></span> <span data-ttu-id="618e9-283">必须将此值设置为 <strong> True </strong> 才能以静默方式安装 ue-v，并绕过用户接受 ue-v 许可条款的要求。</span><span class="sxs-lookup"><span data-stu-id="618e9-283">This must be set to <strong>True</strong> to install UE-V silently and bypass the requirement that the user accepts the UE-V license terms.</span></span> <span data-ttu-id="618e9-284">如果设置为 <strong> False </strong> 或保留为空，用户将收到一条错误消息，并且未安装 ue-v。</span><span class="sxs-lookup"><span data-stu-id="618e9-284">If set to <strong>False</strong> or left empty, the user receives an error message and UE-V is not installed.</span></span></p></td>
<td align="left"><div class="alert">
<strong><span data-ttu-id="618e9-285">重要提示</span><span class="sxs-lookup"><span data-stu-id="618e9-285">Important</span></span></strong><br/><p><span data-ttu-id="618e9-286">此参数是自行安装 UE-V 所必需的。</span><span class="sxs-lookup"><span data-stu-id="618e9-286">This parameter is required to install UE-V silently.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="618e9-287">NORESTART</span><span class="sxs-lookup"><span data-stu-id="618e9-287">NORESTART</span></span></p></td>
<td align="left"><p><span data-ttu-id="618e9-288">阻止在安装 UE-V Agent 后强制重启。</span><span class="sxs-lookup"><span data-stu-id="618e9-288">Prevents a mandatory restart after the UE-V Agent is installed.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="618e9-289">更新 UE-V Agent</span><span class="sxs-lookup"><span data-stu-id="618e9-289">Update the UE-V Agent</span></span>

<span data-ttu-id="618e9-290">UE-V Agent 软件的更新通过 Microsoft Update 提供。</span><span class="sxs-lookup"><span data-stu-id="618e9-290">Updates for the UE-V Agent software are provided through Microsoft Update.</span></span> <span data-ttu-id="618e9-291">你可以使用企业软件分发（ESD）基础结构系统部署 UE-V Agent 更新。</span><span class="sxs-lookup"><span data-stu-id="618e9-291">You can deploy UE-V Agent updates by using Enterprise Software Distribution (ESD) infrastructure systems.</span></span>

<span data-ttu-id="618e9-292">在 UE-V Agent 升级过程中，可以更新常见 Microsoft 应用程序和 Windows 设置的默认设置位置模板组。</span><span class="sxs-lookup"><span data-stu-id="618e9-292">During a UE-V Agent upgrade, the default group of settings location templates for common Microsoft applications and Windows settings can be updated.</span></span>

### <span data-ttu-id="618e9-293">升级 UE-V 2. x 代理</span><span class="sxs-lookup"><span data-stu-id="618e9-293">Upgrade the UE-V 2.x Agent</span></span>

<span data-ttu-id="618e9-294">UE-V 2 x Agent 引入了许多新功能，并修改了代理将内容上载到设置存储共享的方式和时间。</span><span class="sxs-lookup"><span data-stu-id="618e9-294">The UE-V 2.x Agent introduces many new features and modifies how and when the agent uploads content to the settings storage share.</span></span> <span data-ttu-id="618e9-295">升级过程将自动执行这些更改。</span><span class="sxs-lookup"><span data-stu-id="618e9-295">The upgrade process automates these changes.</span></span> <span data-ttu-id="618e9-296">若要升级 UE-V Agent，请在用户的计算机上运行 UE-V Agent 安装程序包（AgentSetup.exe、AgentSetupx86.msi 或 AgentSetupx64.msi）。</span><span class="sxs-lookup"><span data-stu-id="618e9-296">To upgrade the UE-V Agent, run the UE-V Agent install package (AgentSetup.exe, AgentSetupx86.msi, or AgentSetupx64.msi) on users’ computers.</span></span>

**<span data-ttu-id="618e9-297">注意</span><span class="sxs-lookup"><span data-stu-id="618e9-297">Note</span></span>**  
<span data-ttu-id="618e9-298">升级 UE-V Agent 时，必须使用安装了以前的 UE-V Agent 的同一安装程序类型（.exe 文件或 .msi 数据包）。</span><span class="sxs-lookup"><span data-stu-id="618e9-298">When you upgrade the UE-V Agent, you must use the same installer type (.exe file or .msi packet) that installed the previous UE-V Agent.</span></span> <span data-ttu-id="618e9-299">例如，使用 UE-V 2 AgentSetup.exe 升级使用 AgentSetup.exe 安装的 UE-V 1.0 代理。</span><span class="sxs-lookup"><span data-stu-id="618e9-299">For example, use the UE-V 2 AgentSetup.exe to upgrade UE-V 1.0 Agents that were installed by using AgentSetup.exe.</span></span>



<span data-ttu-id="618e9-300">当代理安装程序运行时，将保留以下配置：</span><span class="sxs-lookup"><span data-stu-id="618e9-300">The following configurations are preserved when the Agent Setup program runs:</span></span>

-   <span data-ttu-id="618e9-301">设置存储路径</span><span class="sxs-lookup"><span data-stu-id="618e9-301">Settings storage path</span></span>

-   <span data-ttu-id="618e9-302">注册表设置</span><span class="sxs-lookup"><span data-stu-id="618e9-302">Registry settings</span></span>

-   <span data-ttu-id="618e9-303">计划任务（间隔设置被重置为默认值）</span><span class="sxs-lookup"><span data-stu-id="618e9-303">Scheduled tasks (Interval settings are reset to their defaults)</span></span>

**<span data-ttu-id="618e9-304">注意</span><span class="sxs-lookup"><span data-stu-id="618e9-304">Note</span></span>**  
<span data-ttu-id="618e9-305">具有 UE-V 2 个设置位置模板的计算机，这些位置模板在 UE-V 1.0 代理中注册了 Windows 事件日志中的错误。</span><span class="sxs-lookup"><span data-stu-id="618e9-305">A computer with UE-V 2.x settings location templates that are registered in the UE-V 1.0 Agent register errors in the Windows Event Log.</span></span>



<span data-ttu-id="618e9-306">你可以使用 Microsoft System Center 2012 Configuration Manager 或其他企业版软件分发工具自动执行并分发 UE-V Agent 升级。</span><span class="sxs-lookup"><span data-stu-id="618e9-306">You can use Microsoft System Center 2012 Configuration Manager or another enterprise software distribution tool to automate and distribute the UE-V Agent upgrade.</span></span>

<span data-ttu-id="618e9-307">**建议：** 我们建议你升级计算环境中的所有 UE-V 1.0 代理，但这不是必需的。</span><span class="sxs-lookup"><span data-stu-id="618e9-307">**Recommendations:** We recommend that you upgrade all of the UE-V 1.0 Agents in a computing environment, but it is not required.</span></span> <span data-ttu-id="618e9-308">UE-V 2. x 设置位置模板可以与 UE-V 1.0 代理交互，因为它们仅共享设置存储路径中的设置。</span><span class="sxs-lookup"><span data-stu-id="618e9-308">UE-V 2.x settings location templates can interact with a UE-V 1.0 Agent because they only share the settings from the settings storage path.</span></span> <span data-ttu-id="618e9-309">但是，我们建议你将部署移动到单个代理版本以简化管理并支持 UE-V。</span><span class="sxs-lookup"><span data-stu-id="618e9-309">We recommend, however, that you move the deployments to a single agent version to simplify management and to support UE-V.</span></span>

### <span data-ttu-id="618e9-310">升级失败后修复 UE-V Agent</span><span class="sxs-lookup"><span data-stu-id="618e9-310">Repair the UE-V Agent after an unsuccessful upgrade</span></span>

<span data-ttu-id="618e9-311">在尝试下列操作之一后，可能会遇到错误：</span><span class="sxs-lookup"><span data-stu-id="618e9-311">You might experience errors after you attempt one of the following operations:</span></span>

-   <span data-ttu-id="618e9-312">从 UE-V 1.0 升级到 UE-V 2</span><span class="sxs-lookup"><span data-stu-id="618e9-312">Upgrade from UE-V 1.0 to UE-V 2</span></span>

-   <span data-ttu-id="618e9-313">升级到较新版本的 Windows，例如从 Windows 7 升级到 Windows 8 或从 Windows 8 升级到 Windows 8.1。</span><span class="sxs-lookup"><span data-stu-id="618e9-313">Upgrade to a newer version of Windows, for example, from Windows 7 to Windows 8 or from Windows 8 to Windows 8.1.</span></span>

-   <span data-ttu-id="618e9-314">升级 UE-V Agent 后卸载代理</span><span class="sxs-lookup"><span data-stu-id="618e9-314">Uninstall the agent after upgrading the UE-V Agent</span></span>

<span data-ttu-id="618e9-315">若要解决任何问题，请尝试通过在安装了代理的计算机上的命令提示符处输入此命令来修复 UE-V Agent。</span><span class="sxs-lookup"><span data-stu-id="618e9-315">To resolve any issues, attempt to repair the UE-V Agent by entering this command at a command prompt on the computer where the agent is installed.</span></span>

``` syntax
msiexec.exe /f "<path to msi file>" /quiet /norestart /l*v "%temp%\UE-VAgentInstaller.log
```

<span data-ttu-id="618e9-316">然后，你可以通过安装较新版本的 UE-V Agent 重试卸载过程或升级。</span><span class="sxs-lookup"><span data-stu-id="618e9-316">You can then retry the uninstall process or upgrade by installing the newer version of the UE-V Agent.</span></span>






## <span data-ttu-id="618e9-317">相关主题</span><span class="sxs-lookup"><span data-stu-id="618e9-317">Related topics</span></span>


[<span data-ttu-id="618e9-318">准备 UE-V 2. x 部署</span><span class="sxs-lookup"><span data-stu-id="618e9-318">Prepare a UE-V 2.x Deployment</span></span>](prepare-a-ue-v-2x-deployment-new-uevv2.md)

[<span data-ttu-id="618e9-319">部署自定义应用程序的 UE-V 2。</span><span class="sxs-lookup"><span data-stu-id="618e9-319">Deploy UE-V 2.x for Custom Applications</span></span>](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)









