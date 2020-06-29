---
title: 规划服务器安全
description: 规划服务器安全
author: dansimp
ms.assetid: c7cd8227-b359-41e7-a8ae-d0d5718a76a2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9bea1bd8287a15385200bbfb425ed8e00fbcdb02
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798864"
---
# <span data-ttu-id="437ee-103">规划服务器安全</span><span class="sxs-lookup"><span data-stu-id="437ee-103">Planning for Server Security</span></span>


<span data-ttu-id="437ee-104">若要增强环境的安全性，必须查看环境中任何潜在威胁的暴露程度。</span><span class="sxs-lookup"><span data-stu-id="437ee-104">To enhance the security of an environment, you must look at the exposure to any potential threats in the environment.</span></span> <span data-ttu-id="437ee-105">为 App-v 基础结构提供安全性要求你使用特定的 App-v 安全功能以及基础基础结构的安全做法和功能。</span><span class="sxs-lookup"><span data-stu-id="437ee-105">Providing security for an App-V infrastructure requires you to use the specific App-V security features as well as the security practices and features for the underlying infrastructure.</span></span> <span data-ttu-id="437ee-106">为诸如 Internet 信息服务（IIS）、Active Directory 域服务和 SQL Server 之类的服务保护基础基础结构将提高 app-v 系统的整体安全性。</span><span class="sxs-lookup"><span data-stu-id="437ee-106">Securing the underlying infrastructure for services such as Internet Information Services (IIS), Active Directory Domain Services, and SQL Server will improve the overall security for your App-V system.</span></span>

<span data-ttu-id="437ee-107">服务器安装的默认设置提供最高的安全级别。</span><span class="sxs-lookup"><span data-stu-id="437ee-107">The default settings for the server installation provide the highest levels of security.</span></span> <span data-ttu-id="437ee-108">但是，某些组件依赖于未配置为安装的一部分的基础基础结构。</span><span class="sxs-lookup"><span data-stu-id="437ee-108">However, some of the components rely on underlying infrastructure that is not configured as part of the installation.</span></span> <span data-ttu-id="437ee-109">遵循安装后步骤后，将增强 app-v 基础结构的安全性。</span><span class="sxs-lookup"><span data-stu-id="437ee-109">Following up with post-installation steps will enhance the security of the App-V infrastructure.</span></span>

<span data-ttu-id="437ee-110">内容目录包含要向客户端流处理的所有程序包。</span><span class="sxs-lookup"><span data-stu-id="437ee-110">The content directory contains all of the packages that are to be streamed to clients.</span></span> <span data-ttu-id="437ee-111">这些资源需要尽可能安全地消除许多可能的安全威胁。</span><span class="sxs-lookup"><span data-stu-id="437ee-111">These resources need to be as secure as possible to eliminate many possible security threats.</span></span> <span data-ttu-id="437ee-112">下表提供了一些其他指南：</span><span class="sxs-lookup"><span data-stu-id="437ee-112">The following list offers some additional guidance:</span></span>

-   <span data-ttu-id="437ee-113">基于 UNC 的发布和/或流式处理-此项的权限应该是环境中最严格的限制。</span><span class="sxs-lookup"><span data-stu-id="437ee-113">UNC-based publishing and/or streaming—The permissions for this item should be the most restrictive in the environment.</span></span> <span data-ttu-id="437ee-114">使用 NTFS 权限为内容目录实施最严格的访问控制列表（Acl）（用户 = 读取，管理员 = 读取和写入）。</span><span class="sxs-lookup"><span data-stu-id="437ee-114">Use NTFS permissions to implement the most restrictive access control lists (ACLs) for the content directory (Users=Read, Administrators=Read and Write).</span></span>

-   <span data-ttu-id="437ee-115">用于发布和/或流式处理的 IIS-将 IIS 配置为仅支持 Windows 集成身份验证。</span><span class="sxs-lookup"><span data-stu-id="437ee-115">IIS used for publishing and/or streaming—Configure IIS to support only Windows Integrated authentication.</span></span> <span data-ttu-id="437ee-116">删除对 IIS 服务器的匿名访问，并使用 NTFS 权限限制对该目录的访问权限。</span><span class="sxs-lookup"><span data-stu-id="437ee-116">Remove anonymous access to the IIS server, and restrict access to the directory with NTFS permissions.</span></span>

-   <span data-ttu-id="437ee-117">RTSP/RTSPS 流应用程序包-将 App-v 提供程序策略配置为要求身份验证、强制访问权限，并仅启用所需的组以访问提供程序策略。</span><span class="sxs-lookup"><span data-stu-id="437ee-117">RTSP/RTSPS to stream application packages—Configure the App-V Provider Policy to require authentication, enforce access permissions, and enable only required groups to have access to the provider policy.</span></span> <span data-ttu-id="437ee-118">在数据库中配置具有适当权限的应用程序。</span><span class="sxs-lookup"><span data-stu-id="437ee-118">Configure applications with the appropriate permissions in the database.</span></span>

<span data-ttu-id="437ee-119">将具有管理权限的用户数保留为最低，以减少数据存储中的数据可能威胁，避免将恶意应用程序发布到基础结构中。</span><span class="sxs-lookup"><span data-stu-id="437ee-119">Keep the number of users with administrative privileges to a minimum to reduce possible threats to the data in the data store and to avoid publishing malicious applications into the infrastructure.</span></span>

## <span data-ttu-id="437ee-120">应用程序虚拟化安全性</span><span class="sxs-lookup"><span data-stu-id="437ee-120">Application Virtualization Security</span></span>


<span data-ttu-id="437ee-121">App-v 使用基础结构的各种组件之间的多种通信方法。</span><span class="sxs-lookup"><span data-stu-id="437ee-121">App-V uses several methods of communication between the various components of the infrastructure.</span></span> <span data-ttu-id="437ee-122">在规划 app-v 基础结构时，保护服务器之间的通信可以降低现有网络上可能已经存在的安全风险。</span><span class="sxs-lookup"><span data-stu-id="437ee-122">When you plan your App-V infrastructure, securing the communications between servers can reduce the security risks that might already be present on the existing network.</span></span>

### <span data-ttu-id="437ee-123">数据存储</span><span class="sxs-lookup"><span data-stu-id="437ee-123">Data Store</span></span>

<span data-ttu-id="437ee-124">应用程序虚拟化管理服务器和应用程序虚拟化管理服务通过 TCP 端口1433使用 SQL 连接与数据存储进行通信。</span><span class="sxs-lookup"><span data-stu-id="437ee-124">The Application Virtualization Management Server and Application Virtualization Management Service communicate with the data store by using an SQL connection over TCP port 1433.</span></span> <span data-ttu-id="437ee-125">管理服务器使用数据存储检索应用程序和配置数据，并将使用信息写入数据库。</span><span class="sxs-lookup"><span data-stu-id="437ee-125">The Management Server uses the data store to retrieve application and configuration data, and it writes usage information to the database.</span></span> <span data-ttu-id="437ee-126">管理服务代表配置 App-v 基础结构的管理员与数据存储进行通信。</span><span class="sxs-lookup"><span data-stu-id="437ee-126">The Management Service communicates with the data store on behalf of an administrator who is configuring the App-V infrastructure.</span></span> <span data-ttu-id="437ee-127">由于数据存储包含关键信息，因此最大程度地减少对此数据的威胁非常重要。</span><span class="sxs-lookup"><span data-stu-id="437ee-127">Because the data store contains critical information, it is important to minimize threats to this data.</span></span>

<span data-ttu-id="437ee-128">建议使用 Internet 协议安全（IPsec）保护 app-v 管理服务器、管理服务和数据存储之间的通信。</span><span class="sxs-lookup"><span data-stu-id="437ee-128">It is recommended that communications between App-V Management Server, Management Service and the data store be secured with Internet Protocol Security (IPsec).</span></span> <span data-ttu-id="437ee-129">具体说来，创建用于保护数据存储（SQL）和管理服务器以及数据存储和管理服务之间的通信通道安全的策略。</span><span class="sxs-lookup"><span data-stu-id="437ee-129">Specifically, create policies that secure the communication channel between the data store (SQL) and the Management Server and the data store and the Management Service.</span></span> <span data-ttu-id="437ee-130">你还可以通过 IPsec 部署服务器和域隔离，确保所有 App-v 基础结构组件仅与安全通道通信。</span><span class="sxs-lookup"><span data-stu-id="437ee-130">You can also deploy server and domain isolation with IPsec, ensuring all App-V infrastructure components communicate only with secure channels.</span></span> <span data-ttu-id="437ee-131">有关实施 IPsec 的详细信息，请参阅以下文档：</span><span class="sxs-lookup"><span data-stu-id="437ee-131">For information about implementing IPsec, refer to the following documentation:</span></span>

-   <span data-ttu-id="437ee-132">对于 Windows Server2003，请参阅 <https://go.microsoft.com/fwlink/?LinkId=133226> （） https://go.microsoft.com/fwlink/?LinkId=133226) 。</span><span class="sxs-lookup"><span data-stu-id="437ee-132">For Windows Server2003, see <https://go.microsoft.com/fwlink/?LinkId=133226> (https://go.microsoft.com/fwlink/?LinkId=133226).</span></span>

-   <span data-ttu-id="437ee-133">对于 Windows Server2008，请参阅 <https://go.microsoft.com/fwlink/?LinkId=133227> （） https://go.microsoft.com/fwlink/?LinkId=133227) 。</span><span class="sxs-lookup"><span data-stu-id="437ee-133">For Windows Server2008, see <https://go.microsoft.com/fwlink/?LinkId=133227> (https://go.microsoft.com/fwlink/?LinkId=133227).</span></span>

### <span data-ttu-id="437ee-134">内容目录</span><span class="sxs-lookup"><span data-stu-id="437ee-134">Content Directory</span></span>

<span data-ttu-id="437ee-135">App-v 管理服务器安装配置内容目录的位置。</span><span class="sxs-lookup"><span data-stu-id="437ee-135">The App-V Management Server installation configures a location for the content directory.</span></span> <span data-ttu-id="437ee-136">此目录是虚拟化应用程序包的存储位置。</span><span class="sxs-lookup"><span data-stu-id="437ee-136">This directory is the storage location for virtualized application packages.</span></span> <span data-ttu-id="437ee-137">此位置可以是服务器的本地位置，也可以放置在远程网络共享上。</span><span class="sxs-lookup"><span data-stu-id="437ee-137">This location can be local to the server, or it can be placed on a remote network share.</span></span> <span data-ttu-id="437ee-138">因此，实现 IPsec 以帮助保护与内容目录的远程位置的通信。</span><span class="sxs-lookup"><span data-stu-id="437ee-138">Therefore, implement IPsec to help secure the communication with a remote location for the content directory.</span></span>

<span data-ttu-id="437ee-139">你还可以使用 IIS 服务器上的虚拟目录将程序包传输到客户端。</span><span class="sxs-lookup"><span data-stu-id="437ee-139">You can also use a virtual directory on an IIS server to stream packages to the clients.</span></span> <span data-ttu-id="437ee-140">如果为内容创建的虚拟目录位于远程源上，请使用 IPsec 来帮助保护 IIS 服务器和远程存储位置之间的通信。</span><span class="sxs-lookup"><span data-stu-id="437ee-140">If the virtual directory that is created for content is located on a remote source, use IPsec to help secure the communication between the IIS server and the remote storage location.</span></span>

<span data-ttu-id="437ee-141">内容目录包含流入客户端的所有程序包。</span><span class="sxs-lookup"><span data-stu-id="437ee-141">The content directory contains all of the packages that are streamed to clients.</span></span> <span data-ttu-id="437ee-142">这些资源需要尽可能安全地消除许多可能的安全威胁。</span><span class="sxs-lookup"><span data-stu-id="437ee-142">These resources need to be as secure as possible to eliminate many possible security threats.</span></span>

### <span data-ttu-id="437ee-143">安全协议</span><span class="sxs-lookup"><span data-stu-id="437ee-143">Security Protocols</span></span>

<span data-ttu-id="437ee-144">你可以使用 RTSPS 或 HTTPS 进行增强的安全通信。</span><span class="sxs-lookup"><span data-stu-id="437ee-144">You can use RTSPS or HTTPS for enhanced secure communications.</span></span> <span data-ttu-id="437ee-145">RTSPS 是 App-v 服务器使用的协议，HTTPS 是 IIS 服务器使用的协议。</span><span class="sxs-lookup"><span data-stu-id="437ee-145">RTSPS is the protocol used by App-V servers, and HTTPS is the protocol used by IIS servers.</span></span> <span data-ttu-id="437ee-146">将应用程序从服务器发布到应用程序虚拟化桌面客户端时，将使用这些协议。</span><span class="sxs-lookup"><span data-stu-id="437ee-146">These protocols are used when publishing applications from the server to the Application Virtualization Desktop Client.</span></span> <span data-ttu-id="437ee-147">确定所需的协议后，请添加使用该协议的发布服务器。</span><span class="sxs-lookup"><span data-stu-id="437ee-147">After you determine the desired protocol, add a publishing server that uses that protocol.</span></span>

### <a href="" id="configuring-app-v-servers-for-rtsps-"></a><span data-ttu-id="437ee-148">为 RTSPS 配置 app-v 服务器</span><span class="sxs-lookup"><span data-stu-id="437ee-148">Configuring App-V Servers for RTSPS</span></span>

<span data-ttu-id="437ee-149">安装或配置应用程序 V 管理服务器或流服务器以使用增强的安全（例如 TLS）要求将 x.509 V3 证书预配到 App-v 服务器。</span><span class="sxs-lookup"><span data-stu-id="437ee-149">Installing or configuring an App-V Management Server or Streaming Server to use Enhanced Security (for example, TLS) requires that an X.509 V3 certificate be provisioned to the App-V server.</span></span> <span data-ttu-id="437ee-150">准备为服务器安装或配置安全时，必须满足某些特定要求。</span><span class="sxs-lookup"><span data-stu-id="437ee-150">When you prepare to install or configure security for a server, you must fulfill some specific requirements.</span></span> <span data-ttu-id="437ee-151">为更安全的 App-v 管理服务器或流服务器部署和配置证书的技术要求包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="437ee-151">Technical requirements for deploying and configuring certificates for a more secure App-V Management Server or Streaming Server include the following:</span></span>

-   <span data-ttu-id="437ee-152">证书必须有效。</span><span class="sxs-lookup"><span data-stu-id="437ee-152">Certificate must be valid.</span></span> <span data-ttu-id="437ee-153">否则，客户端将终止连接。</span><span class="sxs-lookup"><span data-stu-id="437ee-153">Otherwise, the client terminates the connection.</span></span>

-   <span data-ttu-id="437ee-154">证书必须包含正确的增强密钥用法（EKU）-服务器身份验证（OID 1.3.6.1.5.5.7.3.1）。</span><span class="sxs-lookup"><span data-stu-id="437ee-154">Certificate must contain the correct Enhanced Key Usage (EKU) - Server Authentication (OID 1.3.6.1.5.5.7.3.1).</span></span> <span data-ttu-id="437ee-155">否则，客户端将终止连接。</span><span class="sxs-lookup"><span data-stu-id="437ee-155">Otherwise, the client terminates the connection.</span></span>

-   <span data-ttu-id="437ee-156">证书完全限定的域名（FQDN）必须与安装它的服务器相匹配。</span><span class="sxs-lookup"><span data-stu-id="437ee-156">Certificate fully qualified domain name (FQDN) must match the server on which it is installed.</span></span> <span data-ttu-id="437ee-157">例如，如果客户端正在呼叫 `RTSPS://Myserver.mycompany.com/content/MyApp.sft` ，但**颁发给**field 的证书包含 `Myserver1.mycompany.com` ，则客户端将不会连接到服务器，并且会话将终止，即使 `Myserver.mycompany.com` 和 `Myserver1.mycompany.com` 解析为同一 IP 地址也是如此。</span><span class="sxs-lookup"><span data-stu-id="437ee-157">For example, if the client is calling `RTSPS://Myserver.mycompany.com/content/MyApp.sft`, but the certificate **Issued To** field contains `Myserver1.mycompany.com`, the client will not connect to the server and the session is terminated, even if `Myserver.mycompany.com` and `Myserver1.mycompany.com` resolve to the same IP address.</span></span>

    <span data-ttu-id="437ee-158">**注意** 如果在网络负载平衡群集中使用 app-v，则必须使用*主题备用名称*（san）配置证书以支持 RTSPS。</span><span class="sxs-lookup"><span data-stu-id="437ee-158">**Note** If you use App-V in a network load balanced cluster, the certificate must be configured with *Subject Alternate Names* (SANs) to support RTSPS.</span></span> <span data-ttu-id="437ee-159">有关配置证书颁发机构（CA）和通过 San 创建证书的信息，请参阅 <https://go.microsoft.com/fwlink/?LinkId=133228> （ https://go.microsoft.com/fwlink/?LinkId=133228) 。</span><span class="sxs-lookup"><span data-stu-id="437ee-159">For information about configuring the certification authority (CA) and creating certificates with SANs, see <https://go.microsoft.com/fwlink/?LinkId=133228> (https://go.microsoft.com/fwlink/?LinkId=133228).</span></span>

     

-   <span data-ttu-id="437ee-160">将证书颁发给 App-v 服务器的 CA 必须受连接到服务器的客户端信任。</span><span class="sxs-lookup"><span data-stu-id="437ee-160">The CA issuing the certificate to the App-V server must be trusted by the client connecting to the server.</span></span> <span data-ttu-id="437ee-161">否则，客户端将终止连接。</span><span class="sxs-lookup"><span data-stu-id="437ee-161">Otherwise, the client terminates the connection.</span></span>

-   <span data-ttu-id="437ee-162">必须更改*证书私钥*的权限，才能通过服务器 app-v 服务启用访问权限。</span><span class="sxs-lookup"><span data-stu-id="437ee-162">You must change the permissions for the *Certificate Private Key* to enable access by the Server App-V Service.</span></span> <span data-ttu-id="437ee-163">默认情况下，App-v 管理服务器和流服务器服务在网络服务帐户下运行。</span><span class="sxs-lookup"><span data-stu-id="437ee-163">By default, the App-V Management Server and Streaming Server services run under the Network Service account.</span></span> <span data-ttu-id="437ee-164">在服务器上生成 PKCS \ #10 时，将创建一个私钥。</span><span class="sxs-lookup"><span data-stu-id="437ee-164">When a PKCS\#10 is generated on the server, a private key is created.</span></span> <span data-ttu-id="437ee-165">只有本地系统和管理员组有权访问此注册表项。</span><span class="sxs-lookup"><span data-stu-id="437ee-165">Only the Local System and Administrators groups have access to this key.</span></span> <span data-ttu-id="437ee-166">这些默认 Acl 阻止 App-v 服务器接受安全连接。</span><span class="sxs-lookup"><span data-stu-id="437ee-166">These default ACLs prevent the App-V server from accepting secure connections.</span></span>

    <span data-ttu-id="437ee-167">**注意** 有关配置公钥基础结构（PKI）的信息，请参阅 <https://go.microsoft.com/fwlink/?LinkId=133229> （ https://go.microsoft.com/fwlink/?LinkId=133229) 。</span><span class="sxs-lookup"><span data-stu-id="437ee-167">**Note** For information about configuring a public key infrastructure (PKI), see <https://go.microsoft.com/fwlink/?LinkId=133229> (https://go.microsoft.com/fwlink/?LinkId=133229).</span></span>

     

### <span data-ttu-id="437ee-168">配置具有 HTTPS 的 IIS 服务器</span><span class="sxs-lookup"><span data-stu-id="437ee-168">Configuring IIS Servers with HTTPS</span></span>

<span data-ttu-id="437ee-169">在某些基础结构配置中，app-v 可能使用 IIS 服务器。</span><span class="sxs-lookup"><span data-stu-id="437ee-169">App-V might use IIS servers in certain infrastructure configurations.</span></span> <span data-ttu-id="437ee-170">有关配置 IIS 服务器的详细信息，请参阅 <https://go.microsoft.com/fwlink/?LinkId=133230> （ https://go.microsoft.com/fwlink/?LinkId=133230) 。</span><span class="sxs-lookup"><span data-stu-id="437ee-170">For more information about configuring IIS servers, see <https://go.microsoft.com/fwlink/?LinkId=133230> (https://go.microsoft.com/fwlink/?LinkId=133230).</span></span>

<span data-ttu-id="437ee-171">**注意** 如果使用 IIS 发布 .ICO 和 OSD 文件，请为 OSD = TXT 配置 MIME 类型;否则，IIS 将拒绝向客户端提供 .ICO 和 OSD 文件。</span><span class="sxs-lookup"><span data-stu-id="437ee-171">**Note** If you are using IIS to publish the ICO and OSD files, configure a MIME type for OSD=TXT; otherwise, IIS will refuse to serve the ICO and OSD files to clients.</span></span>

 

### <span data-ttu-id="437ee-172">应用程序级安全性</span><span class="sxs-lookup"><span data-stu-id="437ee-172">Application-Level Security</span></span>

<span data-ttu-id="437ee-173">你可以将服务器配置为将特定应用程序流式传输到用户桌面。</span><span class="sxs-lookup"><span data-stu-id="437ee-173">You can configure the servers to stream specific applications to a user’s desktop.</span></span> <span data-ttu-id="437ee-174">但是，访问权限实际上是在程序包级别授予的，而不是在应用程序级别授予的。</span><span class="sxs-lookup"><span data-stu-id="437ee-174">However, access permission actually is granted at the package level, not at the application level.</span></span> <span data-ttu-id="437ee-175">虽然特定应用程序可能不会发布到用户的桌面，但如果用户有权添加应用程序或客户端计算机上的管理员，则用户可以在客户端上创建并使用快捷方式来运行程序包中的所有应用程序。</span><span class="sxs-lookup"><span data-stu-id="437ee-175">Although a specific application might not be published to the user’s desktop, if the user has permission to add applications or is an administrator on the client computer, the user can create and use a shortcut on the client to run all the applications in a package.</span></span>

## <span data-ttu-id="437ee-176">针对分布式环境配置 App-V 管理</span><span class="sxs-lookup"><span data-stu-id="437ee-176">Configuring App-V Administration for a Distributed Environment</span></span>


<span data-ttu-id="437ee-177">为特定组织设计基础结构时，可以在安装了 app-v 管理服务器的计算机以外的计算机上安装 app-v 管理 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="437ee-177">When designing the infrastructure for your specific organization, you can install the App-V Management Web Service on a computer other than the computer where you install the App-V Management Server.</span></span> <span data-ttu-id="437ee-178">分离这些 App-v 组件的常见原因包括以下几项：</span><span class="sxs-lookup"><span data-stu-id="437ee-178">Common reasons for separating these App-V components include the following:</span></span>

-   <span data-ttu-id="437ee-179">性能</span><span class="sxs-lookup"><span data-stu-id="437ee-179">Performance</span></span>

-   <span data-ttu-id="437ee-180">可靠性</span><span class="sxs-lookup"><span data-stu-id="437ee-180">Reliability</span></span>

-   <span data-ttu-id="437ee-181">可用性</span><span class="sxs-lookup"><span data-stu-id="437ee-181">Availability</span></span>

-   <span data-ttu-id="437ee-182">可伸缩性</span><span class="sxs-lookup"><span data-stu-id="437ee-182">Scalability</span></span>

<span data-ttu-id="437ee-183">为了使基础结构正常运行，分离 App-v 管理控制台、管理服务器和管理 Web 服务需要额外的配置。</span><span class="sxs-lookup"><span data-stu-id="437ee-183">For the infrastructure to operate correctly, separating the App-V Management Console, Management Server and Management Web Service requires additional configuration.</span></span> <span data-ttu-id="437ee-184">有关如何配置服务器的详细信息，请参阅[如何将服务器配置为受信任的委派](how-to-configure-the-server-to-be-trusted-for-delegation.md)。</span><span class="sxs-lookup"><span data-stu-id="437ee-184">For detailed information about how to configure the server, see [How to Configure the Server to be Trusted for Delegation](how-to-configure-the-server-to-be-trusted-for-delegation.md).</span></span>

## <span data-ttu-id="437ee-185">相关主题</span><span class="sxs-lookup"><span data-stu-id="437ee-185">Related topics</span></span>


[<span data-ttu-id="437ee-186">规划安全和保护</span><span class="sxs-lookup"><span data-stu-id="437ee-186">Planning for Security and Protection</span></span>](planning-for-security-and-protection.md)

 

 





