---
title: MBAM 1.0 发行说明
description: MBAM 1.0 发行说明
author: dansimp
ms.assetid: d82fddde-c360-48ef-86a0-d9b5fe066861
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 705fd1b936da1454081dd14a7f075f642fc4a405
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803886"
---
# <span data-ttu-id="a3ac5-103">MBAM 1.0 发行说明</span><span class="sxs-lookup"><span data-stu-id="a3ac5-103">Release Notes for MBAM 1.0</span></span>


**<span data-ttu-id="a3ac5-104">若要在这些发行说明中搜索特定问题，请按 CTRL + F。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-104">To search for a specific issue in these release notes, press CTRL+F.</span></span>**

<span data-ttu-id="a3ac5-105">安装 Microsoft BitLocker 管理和监视（MBAM）之前，请仔细阅读这些发行说明。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-105">Read these release notes thoroughly before you install Microsoft BitLocker Administration and Monitoring (MBAM).</span></span>

<span data-ttu-id="a3ac5-106">这些发行说明包含成功安装 MBAM 所需的信息。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-106">These release notes contain information that is required to successfully install MBAM.</span></span> <span data-ttu-id="a3ac5-107">发行说明还包含产品文档中不可用的信息。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-107">The release notes also contain information that is not available in the product documentation.</span></span> <span data-ttu-id="a3ac5-108">如果这些发行说明和其他 MBAM 文档之间存在差异，则应将最新更改视为权威。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-108">If there is a difference between these release notes and other MBAM documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="a3ac5-109">这些发行说明取代了本产品附带的内容。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-109">These release notes supersede the content that is included with this product.</span></span>

## <span data-ttu-id="a3ac5-110">关于产品文档</span><span class="sxs-lookup"><span data-stu-id="a3ac5-110">About the Product Documentation</span></span>


<span data-ttu-id="a3ac5-111">有关 MBAM 文档的信息，请参阅 Microsoft TechNet 上的 MBAM 主页。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-111">For information about MBAM documentation, see the MBAM home page on Microsoft TechNet.</span></span>

<span data-ttu-id="a3ac5-112">若要获取 MBAM 文档的可下载副本，请参阅 <https://go.microsoft.com/fwlink/p/?LinkId=225356> Microsoft 下载中心。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-112">To obtain a downloadable copy of the MBAM documentation, see <https://go.microsoft.com/fwlink/p/?LinkId=225356> on the Microsoft Download Center.</span></span>

## <span data-ttu-id="a3ac5-113">提供反馈</span><span class="sxs-lookup"><span data-stu-id="a3ac5-113">Provide Feedback</span></span>


<span data-ttu-id="a3ac5-114">我们对 MBAM 的反馈感兴趣。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-114">We are interested in your feedback on MBAM.</span></span> <span data-ttu-id="a3ac5-115">您可以向发送反馈 <mdopdocs@microsoft.com> 。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-115">You can send your feedback to <mdopdocs@microsoft.com>.</span></span>

<span data-ttu-id="a3ac5-116">**注意** 此电子邮件地址不是支持频道，但你的反馈将帮助我们为我们的文档和产品发布计划未来的更改。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-116">**Note** This email address is not a support channel, but your feedback will help us to plan for future changes in our documentation and product releases.</span></span>

 

<span data-ttu-id="a3ac5-117">有关 MDOP 和其他学习资源的最新信息，请参阅[Mdop 信息体验](https://go.microsoft.com/fwlink/p/?LinkId=236032)页面。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-117">For the latest information about MDOP and additional learning resources, see the [MDOP Information Experience](https://go.microsoft.com/fwlink/p/?LinkId=236032) page.</span></span>

<span data-ttu-id="a3ac5-118">有关新更新或提供反馈的详细信息，请在[Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445)或[Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447)上关注我们。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-118">For more information about new updates or to provide feedback, follow us on [Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445) or [Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447).</span></span>

## <span data-ttu-id="a3ac5-119">MBAM 1.0 的已知问题</span><span class="sxs-lookup"><span data-stu-id="a3ac5-119">Known Issues with MBAM 1.0</span></span>


<span data-ttu-id="a3ac5-120">本部分包含有关 MBAM 设置和安装的已知问题的发行说明。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-120">This section contains release notes about the known issues with MBAM setup and installation.</span></span>

### <a href="" id="if-you-select-the--use-a-certificate-to-encrypt-the-network-communication--option-during-setup--existing-database-connections-and-dependent-applications-can-stop-functioning-"></a><span data-ttu-id="a3ac5-121">如果在安装过程中选择 "使用证书加密网络通信" 选项，则现有数据库连接和依赖应用程序可能停止运行</span><span class="sxs-lookup"><span data-stu-id="a3ac5-121">If you select the “Use a certificate to encrypt the network communication” option during Setup, existing database connections and dependent applications can stop functioning</span></span>

<span data-ttu-id="a3ac5-122">在安装了恢复和硬件数据库或合规性状态数据库功能之后，你可以配置 MBAM 以进行**加密的网络通信**。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-122">You can configure MBAM for **Encrypted network communication** after you install either the Recovery and Hardware Database or the Compliance Status Database features.</span></span> <span data-ttu-id="a3ac5-123">如果你选择为加密网络通信配置 MBAM，MBAM 安装程序会将 SQL Server 数据库引擎的实例配置为使用安全套接字层（SSL），以便在适用数据库之间以及管理和监视服务器以及合规性和审核报表服务器功能之间进行通信。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-123">If you choose to configure MBAM for Encrypted network communication, MBAM Setup configures the instance of the SQL Server Database Engine to use Secure Sockets Layer (SSL) for communication between the applicable database and both the Administration and Monitoring Server and the Compliance and Audit Report Server features.</span></span>

-   <span data-ttu-id="a3ac5-124">如果 SQL Server 数据库引擎的实例尚未配置为使用 SSL，MBAM 安装程序会将其配置为使用 SSL。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-124">If the instance of the SQL Server Database Engine is not already configured to use SSL, MBAM Setup configures it to do so.</span></span> <span data-ttu-id="a3ac5-125">这可以防止尝试在 SQL Server 数据库引擎实例上使用非 MBAM 数据库的应用程序与它们的数据库进行通信。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-125">This can prevent applications that try to use non-MBAM databases on the instance of the SQL Server Database Engine from communicating with their databases.</span></span>

-   <span data-ttu-id="a3ac5-126">如果 SQL Server 数据库引擎的实例已配置为使用 SSL，则将其配置为使用用户在安装过程中选择的证书。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-126">If the instance of the SQL Server Database Engine is already configured to use SSL, it is configured to use the certificate that the user selected during setup.</span></span> <span data-ttu-id="a3ac5-127">如果此证书与已使用的证书不同，则可以阻止在 SQL Server 数据库引擎实例上使用 SQL Server 数据库的应用程序运行。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-127">If this certificate differs from the one that was already in use, it can prevent applications that use SQL Server databases on the instance of the SQL Server Database Engine from running.</span></span>

<span data-ttu-id="a3ac5-128">**解决方法：** 尚</span><span class="sxs-lookup"><span data-stu-id="a3ac5-128">**WORKAROUND:** None</span></span>

### <span data-ttu-id="a3ac5-129">使用本地管理员帐户时，MBAM 安装程序在安装过程中失败</span><span class="sxs-lookup"><span data-stu-id="a3ac5-129">MBAM Setup fails during installation when you use a local Administrator account</span></span>

<span data-ttu-id="a3ac5-130">使用本地管理员帐户时，MBAM 安装程序将失败。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-130">MBAM Setup fails when you use a local Administrator account.</span></span> <span data-ttu-id="a3ac5-131">日志文件包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="a3ac5-131">The log file contains the following information:</span></span>

``` syntax
Locating group 'MBAM Report Users'
Adding <GUID>' to group 'MBAM Report Users'
Locating group 'MBAM Recovery and Hardware DB Access'
Adding 'S-1-5-20' to group 'MBAM Recovery and Hardware DB Access'
Exception: A new member could not be added to a local group because the member has the wrong account type.
 
  StackTrace:    at System.DirectoryServices.AccountManagement.SAMStoreCtx.UpdateGroupMembership(Principal group, DirectoryEntry de, NetCred credentials, AuthenticationTypes authTypes)
   at System.DirectoryServices.AccountManagement.SDSUtils.ApplyChangesToDirectory(Principal p, StoreCtx storeCtx, GroupMembershipUpdater updateGroupMembership, NetCred credentials, AuthenticationTypes authTypes)
   at System.DirectoryServices.AccountManagement.SAMStoreCtx.Update(Principal p)
   at Microsoft.Windows.Mdop.BitlockerManagement.Setup.Groups.CreateGroupsDeferred(Session session)
  InnerException:Exception: A new member could not be added to a local group because the member has the wrong account type.
 
    InnerException:StackTrace:    at System.DirectoryServices.AccountManagement.UnsafeNativeMethods.IADsGroup.Add(String bstrNewItem)
   at System.DirectoryServices.AccountManagement.SAMStoreCtx.UpdateGroupMembership(Principal group, DirectoryEntry de, NetCred credentials, AuthenticationTypes authTypes)
CustomAction MbamCreateGroupsDeferred returned actual error code 1603 (note this may not be 100% accurate if translation happened inside sandbox)
Action ended 11:41:29: InstallExecute. Return value 3.
```

<span data-ttu-id="a3ac5-132">**解决方法：** 在安装 MBAM 时，在服务器计算机上使用具有管理凭据的域帐户。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-132">**WORKAROUND:** Use a domain account with administrative credentials on the server computer when you install MBAM.</span></span>

### <span data-ttu-id="a3ac5-133">如果你选择 "不加密网络通信"，MBAM 安装程序会将 SQL Server 数据库引擎的实例重新配置为不使用 SSL</span><span class="sxs-lookup"><span data-stu-id="a3ac5-133">MBAM Setup reconfigures the instance of the SQL Server Database Engine to not use SSL if you select “Do not encrypt network communication”</span></span>

<span data-ttu-id="a3ac5-134">在安装恢复和硬件数据库或合规性状态数据库时，可以通过选择**加密的网络通信**来使用安装程序配置 MBAM。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-134">When you install either the Recovery and Hardware Database or the Compliance Status Database, you can use Setup to configure MBAM by selecting **Encrypted network communication**.</span></span> <span data-ttu-id="a3ac5-135">如果您决定不加密网络通信，MBAM 安装程序将重新配置 SQL Server 数据库引擎的实例，以使其不使用 SSL。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-135">If you decide not to encrypt the network communication, MBAM Setup reconfigures the instance of the SQL Server Database Engine so that it does not use SSL.</span></span>

-   <span data-ttu-id="a3ac5-136">如果 SQL Server 数据库引擎的实例已配置为使用 SSL，MBAM 安装程序将在 SQL Server 数据库引擎的实例上禁用 SSL。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-136">If the instance of the SQL Server Database Engine is already configured to use SSL, MBAM Setup disables SSL on the instance of the SQL Server Database Engine.</span></span> <span data-ttu-id="a3ac5-137">这将更改在 SQL Server 数据库引擎实例上使用与 MBAM 数据库无关的数据库的应用之间的通信安全。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-137">This changes the communication security between the applications that use databases that are not related to MBAM databases on the instance of the SQL Server Database Engine.</span></span>

<span data-ttu-id="a3ac5-138">**解决方法：** 尚</span><span class="sxs-lookup"><span data-stu-id="a3ac5-138">**WORKAROUND:** None</span></span>

### <span data-ttu-id="a3ac5-139">缺少 Internet Information Services （IIS）管理脚本和工具 web 服务器功能的先决条件</span><span class="sxs-lookup"><span data-stu-id="a3ac5-139">Missing prerequisite for the Internet Information Services (IIS) Management Scripts and Tools web server feature</span></span>

<span data-ttu-id="a3ac5-140">MBAM 安装程序依赖于 IIS 管理脚本和工具 web 服务器功能，但不是强制先决条件。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-140">MBAM Setup is dependent on the IIS Management Scripts and Tools web server feature, but it is not an enforced prerequisite.</span></span> <span data-ttu-id="a3ac5-141">服务器设置允许你在缺少此功能时安装 MBAM。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-141">Server setup lets you install MBAM when this feature is missing.</span></span> <span data-ttu-id="a3ac5-142">但是，这将导致备份服务 MBAM VSS 编写器启动然后停止，因为它无法找到 Windows Management Instrumentation （WMI）和 Internet Information Services （IIS）提供程序。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-142">However, this will cause the backup service MBAM VSS Writer to start and then stop, because it cannot locate the Windows Management Instrumentation (WMI) and the Internet Information Services (IIS) provider.</span></span> <span data-ttu-id="a3ac5-143">除了事件日志中发生的情况外，此条件没有错误消息。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-143">There is no error message for this condition, except that which occurs in the event log.</span></span> <span data-ttu-id="a3ac5-144">不带 IIS 管理脚本和工具的 MBAM 安装会导致不为 MBAM 运行备份操作。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-144">Installation of MBAM without IIS Management Scripts and Tools causes the backup operations not to run for MBAM.</span></span>

<span data-ttu-id="a3ac5-145">**解决方法：** 在启动 MBAM 安装程序之前，请确保已安装 IIS 管理脚本和工具 web 服务器功能。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-145">**WORKAROUND:** Ensure that the IIS Management Scripts and Tools web server feature is installed before you start the MBAM Setup.</span></span>

### <a href="" id="mbam-setup-stops-responding-during-the--installing-selected-features--phase-when-setup-is-configured-to-use-a-certificate"></a><span data-ttu-id="a3ac5-146">设置配置为使用证书时，在 "安装所选功能" 阶段，MBAM 安装程序停止响应</span><span class="sxs-lookup"><span data-stu-id="a3ac5-146">MBAM Setup stops responding during the “Installing selected features” phase when setup is configured to use a certificate</span></span>

<span data-ttu-id="a3ac5-147">MBAM 安装程序在安装的 "**安装选定的功能**" 阶段期间停止响应。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-147">MBAM Setup stops responding during the **Installing selected features** phase of setup.</span></span> <span data-ttu-id="a3ac5-148">在恢复和硬件数据库或合规性状态数据库的安装过程中，选择 "**使用证书加密网络通信"** 选项时，会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-148">This occurs during the installation of the Recovery and Hardware Database or the Compliance Status Database, after you select the **Use a certificate to encrypt the network communication** option.</span></span> <span data-ttu-id="a3ac5-149">此外，如果 SQL Server 数据库引擎的实例无法访问在安装过程中指定的证书，MBAM 安装程序将停止响应。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-149">Furthermore, the MBAM Setup stops responding if the instance of the SQL Server Database Engine cannot access the certificate that was specified during setup.</span></span>

<span data-ttu-id="a3ac5-150">**解决方法：** 更新对证书的权限，以便适用于 SQL Server 数据库引擎的适用实例的 Windows 服务可以访问该证书。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-150">**WORKAROUND:** Update the permissions on the certificate, so that the Windows service for the applicable instance of the SQL Server Database Engine can access the certificate.</span></span> <span data-ttu-id="a3ac5-151">你还可以更改 SQL Server 数据库引擎实例的运行帐户，以便数据库引擎使用该证书。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-151">You can also change the account under which the instance of the SQL Server Database Engine runs, for the database engine to use the certificate.</span></span> <span data-ttu-id="a3ac5-152">若要确定证书的权限，请在命令提示符处键入以下命令： **certutil-v-存储 MY**</span><span class="sxs-lookup"><span data-stu-id="a3ac5-152">To determine the permissions for the certificate, type the following command at the command prompt: **certutil -v -store MY**</span></span>

### <span data-ttu-id="a3ac5-153">安装 SQL Server Reporting Services 时，MBAM 安装程序暂停</span><span class="sxs-lookup"><span data-stu-id="a3ac5-153">MBAM Setup pauses when you install SQL Server Reporting Services</span></span>

<span data-ttu-id="a3ac5-154">在 MBAM 安装期间，如果你选择 SQL Server Reporting Services （SSRS）实例，并且 SSRS 实例的配置不正确，则 MBAM 安装程序在尝试与 SSRS 实例通信时最多可能暂停一分钟。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-154">During MBAM installation, when you select an instance of SQL Server Reporting Services (SSRS) and SSRS instance is not available or it is configured incorrectly, the MBAM Setup might pause for up to one minute while it attempts to communicate with the SSRS instance.</span></span>

<span data-ttu-id="a3ac5-155">**解决方法：** 在安装程序尝试联系 SSRS 实例时，请至少等待一分钟，MBAM 设置才能恢复。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-155">**WORKAROUND:** Wait for at least one minute for MBAM Setup to resume while the Setup program attempts to contact the instance of SSRS.</span></span>

### <a href="" id="administration-and-monitoring-server-does-not-run-after-setup-"></a><span data-ttu-id="a3ac5-156">安装后，管理和监视服务器不运行</span><span class="sxs-lookup"><span data-stu-id="a3ac5-156">Administration and Monitoring Server does not run after setup</span></span>

<span data-ttu-id="a3ac5-157">当 MBAM 安装成功安装 "管理和监视服务器" 功能后，当你尝试访问 MBAM 管理员网站时，MBAM 会显示错误消息。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-157">After MBAM Setup successfully installs the Administration and Monitoring Server feature, MBAM displays error messages when you try to access the MBAM administrator website.</span></span> <span data-ttu-id="a3ac5-158">出现此问题的原因有以下几种：</span><span class="sxs-lookup"><span data-stu-id="a3ac5-158">This issue occurs for one of the following reasons:</span></span>

-   <span data-ttu-id="a3ac5-159">在 MBAM 安装之后，已删除管理和监视服务器上的一个或多个先决条件。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-159">One or more prerequisites on the Administration and Monitoring Server were removed after the MBAM installation.</span></span>

-   <span data-ttu-id="a3ac5-160">在服务器上安装了一个或多个先决条件，并且在运行 MBAM 安装程序之前已将其删除。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-160">One or more prerequisites were installed on the server and later they were removed before running the MBAM Setup.</span></span>

<span data-ttu-id="a3ac5-161">**解决方法：** 查看 MBAM 文档并确认已安装所有 MBAM 先决条件。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-161">**WORKAROUND:** Review the MBAM documentation and confirm that all MBAM prerequisites are installed.</span></span>

### <span data-ttu-id="a3ac5-162">在安装过程中单击文档链接会导致安装完成后出现应用程序错误</span><span class="sxs-lookup"><span data-stu-id="a3ac5-162">Clicking documentation links during Setup results in an application error after Setup is finished</span></span>

<span data-ttu-id="a3ac5-163">在设置过程中单击文档链接，然后在安装程序成功完成后单击 "**取消**" 或 "**完成**" 以关闭安装程序时，将显示应用程序错误消息。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-163">When you click a documentation link during setup and then close the Setup program by clicking **Cancel** or **Finish** after Setup has successfully finished, an application error message appears..</span></span> <span data-ttu-id="a3ac5-164">此问题是由 Windows 任务计划程序中的访问冲突错误导致的。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-164">The problem is caused by an access violation error in the Windows Task Scheduler.</span></span>

<span data-ttu-id="a3ac5-165">**解决方法：** 尚.</span><span class="sxs-lookup"><span data-stu-id="a3ac5-165">**WORKAROUND:** None.</span></span> <span data-ttu-id="a3ac5-166">您可以忽略此错误。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-166">You can ignore this error.</span></span>

### <span data-ttu-id="a3ac5-167">失败的 MBAM 安装程序不会删除新数据库</span><span class="sxs-lookup"><span data-stu-id="a3ac5-167">Failed MBAM Setup does not remove new databases</span></span>

<span data-ttu-id="a3ac5-168">如果 MBAM 设置失败，则安装程序可能不会删除新创建的数据库。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-168">If the MBAM Setup fails, Setup might not remove the newly created databases.</span></span> <span data-ttu-id="a3ac5-169">这可能会导致后续安装期间失败。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-169">This can cause failures during subsequent installations.</span></span>

<span data-ttu-id="a3ac5-170">**解决方法：** 在后续安装期间为数据库实例选择其他名称。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-170">**WORKAROUND:** Choose a different name for the database instance during the subsequent installation.</span></span>

### <span data-ttu-id="a3ac5-171">MBAM 安装程序不识别有效的网络负载平衡群集证书</span><span class="sxs-lookup"><span data-stu-id="a3ac5-171">MBAM Setup does not recognize valid network load-balancing cluster certificates</span></span>

<span data-ttu-id="a3ac5-172">在 MBAM 管理和监视服务器安装期间，如果选择了 "网络加密" 选项，则不会将群集证书识别为有效证书。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-172">During the MBAM Administration and Monitoring Server installation, with the network encryption option selected, the cluster certificate is not recognized as a valid certificate.</span></span> <span data-ttu-id="a3ac5-173">当已安装与数据库通信的证书时，它被识别为有效，但负载平衡群集拒绝通信。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-173">It is recognized as valid when the certificate for communication with the database is installed, but it is rejected for communication by the load-balancing cluster.</span></span>

<span data-ttu-id="a3ac5-174">**解决方法：** 确认与证书相关联的证书吊销列表（CRL）是可访问的，或者使用不需要使用 CRL 进行验证的证书。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-174">**WORKAROUND:** Confirm that the certificate revocation list (CRL) associated with the certificate is accessible, or use a certificate that does not require validation by using the CRL.</span></span>

## <span data-ttu-id="a3ac5-175">发行说明版权信息</span><span class="sxs-lookup"><span data-stu-id="a3ac5-175">Release Notes Copyright Information</span></span>


<span data-ttu-id="a3ac5-176">Microsoft、Active Directory、ActiveX、Bing、Excel、Silverlight、SQLServer、Windows、MicrosoftIntune 和 WindowsPowerShell 是 Microsoft 公司组的商标。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-176">Microsoft, Active Directory, ActiveX, Bing, Excel, Silverlight, SQLServer, Windows, MicrosoftIntune, and WindowsPowerShell are trademarks of the Microsoft group of companies.</span></span> <span data-ttu-id="a3ac5-177">所有其他商标的所有权属于其各自所有者。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-177">All other trademarks are property of their respective owners.</span></span>



## <span data-ttu-id="a3ac5-178">相关主题</span><span class="sxs-lookup"><span data-stu-id="a3ac5-178">Related topics</span></span>


[<span data-ttu-id="a3ac5-179">关于 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="a3ac5-179">About MBAM 1.0</span></span>](about-mbam-10.md)

 

 





