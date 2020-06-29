---
title: 规划客户端安全
description: 规划客户端安全
author: dansimp
ms.assetid: 4840a60f-4c91-489c-ad0b-6671882abf9b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e0038f7cbc8592d6c7fcdfa485111da88c17791d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798870"
---
# <span data-ttu-id="05041-103">规划客户端安全</span><span class="sxs-lookup"><span data-stu-id="05041-103">Planning for Client Security</span></span>


<span data-ttu-id="05041-104">App-v 客户端提供了在产品的早期版本中不存在的多个安全增强功能。</span><span class="sxs-lookup"><span data-stu-id="05041-104">The App-V Client provides several security enhancements that were not present in previous versions of the product.</span></span> <span data-ttu-id="05041-105">这些更改提供了在安装后和客户端设置的后续配置中改进的安全性。</span><span class="sxs-lookup"><span data-stu-id="05041-105">These changes provide improved security after installation and through later configuration of the client settings.</span></span> <span data-ttu-id="05041-106">本主题介绍了其中一些增强功能，并标识了在规划过程中应考虑的一些重要的安全相关配置设置。</span><span class="sxs-lookup"><span data-stu-id="05041-106">This topic describes some of those enhancements and identifies several important security-related configuration settings that you should consider during your planning process.</span></span> <span data-ttu-id="05041-107">请务必记住，虚拟应用程序仍可执行，因此你必须确保这些资产不会被未经授权的人员篡改。</span><span class="sxs-lookup"><span data-stu-id="05041-107">It is important to remember that virtual applications are still executables, so you must ensure that these assets cannot be tampered with by unauthorized people.</span></span> <span data-ttu-id="05041-108">出于此原因，开放软件描述符（OSD）文件缓存受保护，如本主题后面部分所述，我们强烈建议你使用 RTSPS、HTTPS 和 IPsec 来保护发布和流式处理。</span><span class="sxs-lookup"><span data-stu-id="05041-108">For this reason, the Open Software Descriptor (OSD) file cache is protected as described later in this topic, and we strongly recommend that you use RTSPS, HTTPS, and IPsec to protect publishing and streaming.</span></span>

## <span data-ttu-id="05041-109">App-v 客户端安全性</span><span class="sxs-lookup"><span data-stu-id="05041-109">App-V Client Security</span></span>


<span data-ttu-id="05041-110">默认情况下，在安装时，app-v 客户端配置有允许用户执行发布刷新和启动应用程序所需的最低权限。</span><span class="sxs-lookup"><span data-stu-id="05041-110">By default, at installation the App-V client is configured with the minimum permissions required to allow a user to perform a publishing refresh and to start applications.</span></span> <span data-ttu-id="05041-111">App-v 客户端中提供的其他安全增强功能包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="05041-111">Other security enhancements provided in the App-V client include the following:</span></span>

-   <span data-ttu-id="05041-112">默认情况下，OSD 文件缓存只能由管理员和通过使用发布刷新过程进行更新。</span><span class="sxs-lookup"><span data-stu-id="05041-112">By default, the OSD file cache can be updated only by administrators and by using the publishing refresh process.</span></span>

-   <span data-ttu-id="05041-113">日志文件（sftlog.txt）只能通过对客户端具有本地管理访问权限的帐户进行访问。</span><span class="sxs-lookup"><span data-stu-id="05041-113">The log file (sftlog.txt) is accessible only by accounts with local administrative access to the client.</span></span>

-   <span data-ttu-id="05041-114">日志文件现在具有最大大小。</span><span class="sxs-lookup"><span data-stu-id="05041-114">The log file now has a maximum size.</span></span>

### <span data-ttu-id="05041-115">文件类型关联</span><span class="sxs-lookup"><span data-stu-id="05041-115">File Type Associations</span></span>

<span data-ttu-id="05041-116">默认情况下，客户端的安装将注册 OSD 文件的文件类型关联（FTAs），从而使用户可以直接从 OSD 文件而不是已发布的快捷方式启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="05041-116">By default, the installation of the client registers file type associations (FTAs) for OSD files, which enables users to start applications directly from OSD files instead of the published shortcuts.</span></span> <span data-ttu-id="05041-117">如果具有本地管理员权限的用户收到包含恶意代码的 OSD 文件（来自电子邮件或从网站下载），用户可以打开 OSD 文件并启动该应用程序，即使该客户已设置为限制 "**添加应用程序**" 权限。</span><span class="sxs-lookup"><span data-stu-id="05041-117">If a user with local administrator rights receives an OSD file containing malicious code, either in e-mail or downloaded from a Web site, the user can open the OSD file and start the application even if the client has been set to restrict the **Add Application** permission.</span></span> <span data-ttu-id="05041-118">你可以为 OSD 注销 FTAs 以减少此风险。</span><span class="sxs-lookup"><span data-stu-id="05041-118">You can unregister the FTAs for the OSD to reduce this risk.</span></span> <span data-ttu-id="05041-119">此外，请考虑在电子邮件系统和防火墙上阻止此扩展。</span><span class="sxs-lookup"><span data-stu-id="05041-119">Also, consider blocking this extension in the e-mail system and at the firewall.</span></span> <span data-ttu-id="05041-120">有关将 Outlook 配置为阻止扩展的详细信息，请参阅 <https://go.microsoft.com/fwlink/?LinkId=133278> 。</span><span class="sxs-lookup"><span data-stu-id="05041-120">For more information about configuring Outlook to block extensions, see <https://go.microsoft.com/fwlink/?LinkId=133278>.</span></span>

**<span data-ttu-id="05041-121">安全说明：</span><span class="sxs-lookup"><span data-stu-id="05041-121">Security Note:</span></span>**

<span data-ttu-id="05041-122">从应用程序第4.6 版开始，在新安装客户端期间，将不再为 OSD 文件创建文件类型关联，但在从 App-v 客户端版本4.2 或4.5 升级期间将保留现有设置。</span><span class="sxs-lookup"><span data-stu-id="05041-122">Starting with App-V version4.6, the file type association is no longer created for OSD files during a new installation of the client, although the existing settings will be maintained during an upgrade from version 4.2 or 4.5 of the App-V client.</span></span> <span data-ttu-id="05041-123">如果出于任何原因需要创建文件类型关联，则可以创建以下注册表项并设置其值，如下所示：</span><span class="sxs-lookup"><span data-stu-id="05041-123">If for any reason it is essential to create the file type association, you can create the following registry keys and set their values as shown:</span></span>

    Create HKEY\_CLASSES\_ROOT\\.osd with a default value of SoftGrid.osd.File

    Under HKEY\_LOCAL\_MACHINE\\software\\classes\\Softgrid.osd.file, create a string value named AppUserModelID with a data value of Microsoft.AppV.Client.Tray

### <span data-ttu-id="05041-124">授权</span><span class="sxs-lookup"><span data-stu-id="05041-124">Authorization</span></span>

<span data-ttu-id="05041-125">在安装期间，你可以使用**RequireAuthorizationIfCached**参数将客户端配置为在用户尝试启动应用程序时要求从服务器授权。</span><span class="sxs-lookup"><span data-stu-id="05041-125">During installation, you can use the **RequireAuthorizationIfCached** parameter to configure the client to require authorization from the server when the user tries to start an application.</span></span> <span data-ttu-id="05041-126">应仔细考虑如何设置此参数。</span><span class="sxs-lookup"><span data-stu-id="05041-126">You should consider carefully how to set this parameter.</span></span> <span data-ttu-id="05041-127">如果 App-v server 因任何原因而不可用，应用程序将使用此参数的最新存储状态来控制用户对应用程序的访问权限。</span><span class="sxs-lookup"><span data-stu-id="05041-127">If the App-V server is unavailable for any reason, the application will use the most recent stored state of this parameter to control user access to the application.</span></span> <span data-ttu-id="05041-128">如果用户在 App-v 服务器不可用之前未成功启动应用程序，则它们将无法启动应用程序，直到它们能够与服务器通信并接收授权。</span><span class="sxs-lookup"><span data-stu-id="05041-128">If the user has not launched the application successfully before the App-V server becomes unavailable, they will not be able to launch the application until they can communicate with the server and receive authorization.</span></span> <span data-ttu-id="05041-129">但是，如果你设置参数以使客户端不需要授权，并且如果服务器不可用，则所有以前缓存的应用程序都可以启动，无论是否已授权。</span><span class="sxs-lookup"><span data-stu-id="05041-129">However, if you set the parameter so that the client does not require authorization and if the server is unavailable, all previously cached applications can be started whether authorized or not.</span></span> <span data-ttu-id="05041-130">此外，如果用户有权通过权限将客户端更改为工作脱机模式，或者如果用户是本地管理员，则用户可以打开所有缓存的程序包，就像应用 V 基础结构不可用一样。</span><span class="sxs-lookup"><span data-stu-id="05041-130">Also, if the user has permission to change the client to Work Offline mode through permissions or if the user is a local administrator, the user would be able to open all cached packages as if the App-V infrastructure was unavailable.</span></span>

### <span data-ttu-id="05041-131">防病毒扫描</span><span class="sxs-lookup"><span data-stu-id="05041-131">Antivirus Scanning</span></span>

<span data-ttu-id="05041-132">在 App-v 客户端计算机上运行的防病毒软件可以在虚拟环境中检测和报告感染病毒的文件。</span><span class="sxs-lookup"><span data-stu-id="05041-132">Antivirus software running on an App-V Client computer can detect and report an infected file in the virtual environment.</span></span> <span data-ttu-id="05041-133">但是，它不能对文件进行杀毒。</span><span class="sxs-lookup"><span data-stu-id="05041-133">However, it cannot disinfect the file.</span></span> <span data-ttu-id="05041-134">如果在虚拟环境中检测到病毒，则防病毒软件将在缓存中执行已配置的隔离或修复操作，而不是实际程序包中的操作。</span><span class="sxs-lookup"><span data-stu-id="05041-134">If a virus is detected in the virtual environment, the antivirus software would perform the configured quarantine or repair operation in the cache, not in the actual package.</span></span> <span data-ttu-id="05041-135">使用 sftfs 文件的例外配置防病毒软件。</span><span class="sxs-lookup"><span data-stu-id="05041-135">Configure the antivirus software with an exception for the sftfs.fsd file.</span></span> <span data-ttu-id="05041-136">此文件是将程序包存储在 App-v 客户端的缓存文件。</span><span class="sxs-lookup"><span data-stu-id="05041-136">This file is the cache file that stores packages on the App-V Client.</span></span>

**<span data-ttu-id="05041-137">安全说明：</span><span class="sxs-lookup"><span data-stu-id="05041-137">Security Note:</span></span>**

<span data-ttu-id="05041-138">如果在生产环境中部署的应用程序或程序包中检测到病毒，请使用无病毒版本替换该应用程序或程序包。</span><span class="sxs-lookup"><span data-stu-id="05041-138">If a virus is detected in an application or package deployed in the production environment, replace the application or package with a virus-free version.</span></span>

## <span data-ttu-id="05041-139">客户端和服务器之间的通信</span><span class="sxs-lookup"><span data-stu-id="05041-139">Communication Between Client and Server</span></span>


<span data-ttu-id="05041-140">发布刷新和程序包流也是与客户端服务器通信相关的安全注意事项的区域。</span><span class="sxs-lookup"><span data-stu-id="05041-140">Publishing refreshes and package streaming are also areas where security considerations relating to client-server communication are important.</span></span>

### <span data-ttu-id="05041-141">发布刷新</span><span class="sxs-lookup"><span data-stu-id="05041-141">Publishing Refresh</span></span>

<span data-ttu-id="05041-142">当客户端与服务器通信以执行发布刷新时，它将使用已登录用户的凭据请求有关应用程序包的信息。</span><span class="sxs-lookup"><span data-stu-id="05041-142">When the client communicates with the server to perform a publishing refresh, it uses the credentials of the logged on user to request information about the application packages.</span></span> <span data-ttu-id="05041-143">你应该确保应用 V 客户端和 App-v 管理服务器之间发生的通信安全，以确保在传输过程中不会篡改任何发布信息。</span><span class="sxs-lookup"><span data-stu-id="05041-143">You should secure the communication that occurs between the App-V client and App-V Management Server to ensure that none of the publishing information can be tampered with in transit.</span></span> <span data-ttu-id="05041-144">这是通过使用增强的安全选项完成的，该选项将使用 RTSPS/HTTPS。</span><span class="sxs-lookup"><span data-stu-id="05041-144">This is done by using the Enhanced Security option, which will use RTSPS/HTTPS.</span></span> <span data-ttu-id="05041-145">客户端与要存储 .ICO 和 OSD 文件的位置之间的通信应使用适用于 SMB/CIFS 共享的 IPsec 和 IIS 服务器的 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="05041-145">Communication between the Client and the location where the ICO and OSD files are stored should use IPsec for SMB/CIFS shares and HTTPS for an IIS server.</span></span>

<span data-ttu-id="05041-146">**注意** 如果使用 IIS 发布 .ICO 和 OSD 文件，请为 OSD = TXT 配置 MIME 类型;否则，IIS 将拒绝向客户端提供 .ICO 和 OSD 文件。</span><span class="sxs-lookup"><span data-stu-id="05041-146">**Note** If you are using IIS to publish the ICO and OSD files, configure a MIME type for OSD=TXT; otherwise, IIS will refuse to serve the ICO and OSD files to clients.</span></span>

 

### <span data-ttu-id="05041-147">程序包流</span><span class="sxs-lookup"><span data-stu-id="05041-147">Package Streaming</span></span>

<span data-ttu-id="05041-148">当用户首次启动应用程序时，或者如果在客户端上设置了自动加载参数，则会将应用程序包从服务器传输到客户端缓存。</span><span class="sxs-lookup"><span data-stu-id="05041-148">When a user launches an application for the first time, or if auto-loading parameters have been set on the client, the application package is streamed from a server to the client cache.</span></span> <span data-ttu-id="05041-149">此流程支持 RTSP/RTSPS、HTTP/HTTPS 和 SMB/CIFS 协议。</span><span class="sxs-lookup"><span data-stu-id="05041-149">This process supports the RTSP/RTSPS, HTTP/HTTPS, and SMB/CIFS protocols.</span></span> <span data-ttu-id="05041-150">除非已在客户端上配置了**ApplicationSourceRoot**或**OverrideURL**设置，否则 OSD 文件将控制使用哪些协议。</span><span class="sxs-lookup"><span data-stu-id="05041-150">The OSD files control which protocols are used, unless the **ApplicationSourceRoot** or **OverrideURL** setting has been configured on the clients.</span></span> <span data-ttu-id="05041-151">你应该将通信配置为通过 RTSPS、HTTPS 或 IPsec for SMB/CIFS 进行通信，以获得更高的安全级别。</span><span class="sxs-lookup"><span data-stu-id="05041-151">You should configure communication to occur over RTSPS, HTTPS, or IPsec for SMB/CIFS to achieve higher levels of security.</span></span> <span data-ttu-id="05041-152">有关选择要使用的通信方法的详细信息，请参阅《 App-V 规划和部署指南》 <https://go.microsoft.com/fwlink/?LinkId=122063> 。</span><span class="sxs-lookup"><span data-stu-id="05041-152">For more information about choosing which communication method to use, see the App-V Planning and Deployment Guide at <https://go.microsoft.com/fwlink/?LinkId=122063>.</span></span>

<span data-ttu-id="05041-153">**注意** 如果使用 IIS 发布程序包（SFT 文件），请为 SFT = Binary 配置 MIME 类型;否则，IIS 将拒绝向客户提供 SFT 文件。</span><span class="sxs-lookup"><span data-stu-id="05041-153">**Note** If you are using IIS to publish packages (SFT files), configure a MIME type for SFT=Binary; otherwise, IIS will refuse to serve the SFT files to clients.</span></span>

 

### <span data-ttu-id="05041-154">漫游配置文件和文件夹重定向</span><span class="sxs-lookup"><span data-stu-id="05041-154">Roaming Profiles and Folder Redirection</span></span>

<span data-ttu-id="05041-155">App-v 系统在 usrvol \ _sftfs \ _v1 installer.pkg 文件中存储对程序包的特定于用户的更改。</span><span class="sxs-lookup"><span data-stu-id="05041-155">The App-V system stores user-specific changes to packages in the usrvol\_sftfs\_v1.pkg file.</span></span> <span data-ttu-id="05041-156">此文件位于用户配置文件的 "应用程序数据" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="05041-156">This file is located in the Application Data folder of a user’s profile.</span></span> <span data-ttu-id="05041-157">由于配置文件或重定向的应用程序数据文件夹在客户端和服务器之间传输，因此请使用 IPsec 保护通信。</span><span class="sxs-lookup"><span data-stu-id="05041-157">Because the profile or a redirected Application Data folder is transferred between the client and the server, use IPsec to secure the communication.</span></span>

## <span data-ttu-id="05041-158">面向 Internet 的客户端的注意事项</span><span class="sxs-lookup"><span data-stu-id="05041-158">Considerations for Internet-Facing Clients</span></span>


<span data-ttu-id="05041-159">对于面向 Internet 的客户端，请务必考虑客户端是否已加入域或是否未加入域。</span><span class="sxs-lookup"><span data-stu-id="05041-159">For Internet-facing clients, it is important to consider whether the client is domain joined or non-domain joined.</span></span>

### <span data-ttu-id="05041-160">加入域的客户端</span><span class="sxs-lookup"><span data-stu-id="05041-160">Domain Joined Client</span></span>

<span data-ttu-id="05041-161">默认情况下，App-v 客户端使用 Active Directory 域服务在 intranet 上进行身份验证和授权所颁发的 Kerberos 票证。</span><span class="sxs-lookup"><span data-stu-id="05041-161">By default, App-V Clients use Kerberos tickets that were issued by Active Directory Domain Services for authentication and authorization on the intranet.</span></span> <span data-ttu-id="05041-162">默认情况下，这些 Kerberos 票证的有效期为10小时。</span><span class="sxs-lookup"><span data-stu-id="05041-162">These Kerberos tickets are valid for 10 hours by default.</span></span> <span data-ttu-id="05041-163">只要票证有效，客户端就会使用此票证访问 app-v 服务器，即使计算机无法连接到域控制器来刷新票证也是如此。</span><span class="sxs-lookup"><span data-stu-id="05041-163">The client will use this ticket to access the App-V server for as long as the ticket is valid, even if the computer is unable to connect to the domain controller to refresh the ticket.</span></span> <span data-ttu-id="05041-164">如果 Kerberos 票证已过期，则 App-v 客户端将还原为 NTLM 身份验证，并使用用户的缓存凭据。</span><span class="sxs-lookup"><span data-stu-id="05041-164">If the Kerberos ticket expires, the App-V client will revert to NTLM authentication and use the user’s cached credentials.</span></span>

### <span data-ttu-id="05041-165">非域加入客户端</span><span class="sxs-lookup"><span data-stu-id="05041-165">Non-Domain Joined Client</span></span>

<span data-ttu-id="05041-166">如果用户是基于 home 的用户，并且计算机未加入到公司域，则 App-v 仍可支持应用程序的提供。</span><span class="sxs-lookup"><span data-stu-id="05041-166">If a user is home-based and the computer is not joined to the company domain, App-V can still support delivering applications.</span></span> <span data-ttu-id="05041-167">若要对用户进行身份验证和授权以执行发布刷新并启动应用程序，请在客户端计算机上配置用户帐户以存储具有对 app-v 环境的访问权限的用户名和密码，并为应用程序提供相应的权限。</span><span class="sxs-lookup"><span data-stu-id="05041-167">To authenticate and authorize a user to perform a publishing refresh and to start applications, configure the user account on the client computer to store the user name and password that has access to the App-V environment and to provide appropriate permissions to the applications.</span></span>

## <span data-ttu-id="05041-168">相关主题</span><span class="sxs-lookup"><span data-stu-id="05041-168">Related topics</span></span>


[<span data-ttu-id="05041-169">规划安全和保护</span><span class="sxs-lookup"><span data-stu-id="05041-169">Planning for Security and Protection</span></span>](planning-for-security-and-protection.md)

 

 





