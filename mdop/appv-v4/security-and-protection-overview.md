---
title: 安全和保护概述
description: 安全和保护概述
author: dansimp
ms.assetid: a43e1c53-7936-4d48-a110-0be26c8e9d97
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b08b7dcb3defa8a01a4fd8a3e7234b5ac2956c4e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798815"
---
# <span data-ttu-id="3e997-103">安全和保护概述</span><span class="sxs-lookup"><span data-stu-id="3e997-103">Security and Protection Overview</span></span>


<span data-ttu-id="3e997-104">Microsoft Application Virtualization 4.5 提供以下增强的安全功能，可帮助你规划和实现更安全的部署策略：</span><span class="sxs-lookup"><span data-stu-id="3e997-104">Microsoft Application Virtualization4.5 provides the following enhanced security features to help you plan and implement a more secure deployment strategy:</span></span>

-   <span data-ttu-id="3e997-105">现在，应用程序虚拟化支持使用 x.509 V3 证书的传输层安全（TLS）。</span><span class="sxs-lookup"><span data-stu-id="3e997-105">Application Virtualization now supports Transport Layer Security (TLS) using X.509 V3 certificates.</span></span> <span data-ttu-id="3e997-106">如果服务器证书已预配到计划的应用程序虚拟化管理或流服务器，则使用 RTSPS 协议通过端口322的安装将默认安全。</span><span class="sxs-lookup"><span data-stu-id="3e997-106">Provided that a server certificate has been provisioned to the planned Application Virtualization Management or Streaming Server, the installation will default to secure, using the RTSPS protocol over port 322.</span></span> <span data-ttu-id="3e997-107">使用 RTSPS 可确保应用程序虚拟化服务器和应用程序虚拟化客户端之间的通信已签名和加密。</span><span class="sxs-lookup"><span data-stu-id="3e997-107">Using RTSPS ensures that communication between the Application Virtualization Servers and the Application Virtualization Clients is signed and encrypted.</span></span> <span data-ttu-id="3e997-108">如果在应用程序虚拟化服务器安装期间未向服务器分配证书，则通信将通过端口554设置为 RTSP。</span><span class="sxs-lookup"><span data-stu-id="3e997-108">If no certificate is assigned to the server during the Application Virtualization Server installation, the communication will be set to RTSP over port 554.</span></span>

    **<span data-ttu-id="3e997-109">安全说明：</span><span class="sxs-lookup"><span data-stu-id="3e997-109">Security Note:</span></span>**

    <span data-ttu-id="3e997-110">若要帮助提供服务器的安全设置，必须确保 RTSP 端口已被禁用，即使已将所有程序包配置为使用 RTSPS。</span><span class="sxs-lookup"><span data-stu-id="3e997-110">To help provide a secure setup of the server, you must make sure that RTSP ports are disabled even if you have all packages configured to use RTSPS.</span></span>

    <span data-ttu-id="3e997-111">如果在安装服务器之后向服务器添加安全证书，则服务器可能无法检测到证书。</span><span class="sxs-lookup"><span data-stu-id="3e997-111">If you add security certificates to the server after installing the server, the server might not detect the certificates.</span></span> <span data-ttu-id="3e997-112">若要帮助确保安全证书检测，请在添加证书后重新启动服务器。</span><span class="sxs-lookup"><span data-stu-id="3e997-112">To help ensure security certificate detection, restart the server after adding the certificates.</span></span>

-   <span data-ttu-id="3e997-113">客户端必须配置为使用与服务器相同的协议和端口，否则它将无法与服务器通信。</span><span class="sxs-lookup"><span data-stu-id="3e997-113">The client must be configured to use the same protocol and port as the server, or it will not be able to communicate with the server.</span></span> <span data-ttu-id="3e997-114">客户端还必须信任该证书的颁发者，并与其受信任的根存储中的几个主要提供商一起提供。</span><span class="sxs-lookup"><span data-stu-id="3e997-114">The client must also trust the issuer of the certificate and ships with several of the primary providers in its Trusted Root Store.</span></span> <span data-ttu-id="3e997-115">你可以使用自签名证书，但你将需要更新客户端。</span><span class="sxs-lookup"><span data-stu-id="3e997-115">You can use self-signed certificates, but you will need to update the clients.</span></span>

-   <span data-ttu-id="3e997-116">将 IIS 服务器配置为使用 HTTPS 协议进行流式处理时，你需要在 IIS 服务器上设置安全套接字层（SSL），并为服务器预配证书。</span><span class="sxs-lookup"><span data-stu-id="3e997-116">When configuring IIS servers to use the HTTPS protocol for streaming, you will need to set up Secure Sockets Layer (SSL) on the IIS server and provision the certificate for the server.</span></span> <span data-ttu-id="3e997-117">客户端也需要配置为信任颁发服务器证书的根证书颁发机构。</span><span class="sxs-lookup"><span data-stu-id="3e997-117">The clients will also need to be configured to trust the root certification authority that issued the server certificate.</span></span>

-   <span data-ttu-id="3e997-118">已将 Kerberos 身份验证作为默认身份验证机制添加到 Microsoft Application Virtualization。</span><span class="sxs-lookup"><span data-stu-id="3e997-118">Kerberos authentication has been added to Microsoft Application Virtualization as the default authentication mechanism.</span></span> <span data-ttu-id="3e997-119">早期版本依赖于 NTLM V2 进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="3e997-119">Earlier versions relied upon NTLM V2 for authentication.</span></span> <span data-ttu-id="3e997-120">使用 Kerberos 身份验证增强了客户端与应用程序虚拟化服务器之间的通信安全。</span><span class="sxs-lookup"><span data-stu-id="3e997-120">Using Kerberos Authentication strengthens the security of the communication between the client and the Application Virtualization server.</span></span> <span data-ttu-id="3e997-121">从客户端启动连接后，应用程序虚拟化服务器使用密钥分发中心（KDC）验证会话票证。</span><span class="sxs-lookup"><span data-stu-id="3e997-121">When a connection has been initiated from the client, the Application Virtualization Server verifies the session ticket with the Key Distribution Center (KDC).</span></span>

-   <span data-ttu-id="3e997-122">由于支持使用服务器证书和使用 RTSPS 或 HTTPS 协议，因此您现在可以支持企业网络外部的客户端。</span><span class="sxs-lookup"><span data-stu-id="3e997-122">Because of the support for using server certificates and using the RTSPS or HTTPS protocols, you can now support clients outside of the corporate network.</span></span> <span data-ttu-id="3e997-123">这有助于消除移动用户在启动应用程序虚拟化预配应用程序之前设置到企业网络（VPN、RAS 等）的安全连接的需要。</span><span class="sxs-lookup"><span data-stu-id="3e997-123">This can help eliminate the need for mobile users to set up a secure connection to the corporate network (VPN, RAS, and so on) prior to launching Application Virtualization provisioned applications.</span></span>

<span data-ttu-id="3e997-124">应考虑的其他重要安全注意事项包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="3e997-124">Other important security considerations to consider include the following:</span></span>

-   <span data-ttu-id="3e997-125">始终保持服务器完全更新和保护。</span><span class="sxs-lookup"><span data-stu-id="3e997-125">Always keep servers fully updated and protected.</span></span>

-   <span data-ttu-id="3e997-126">若要添加证书以启用到应用程序虚拟化管理服务器的更安全的通信，必须满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="3e997-126">To add a certificate to enable more secure communications to the Application Virtualization Management Server, the following criteria must be met:</span></span>

    -   <span data-ttu-id="3e997-127">将添加证书的用户必须是证书存储所在的服务器上的管理员。</span><span class="sxs-lookup"><span data-stu-id="3e997-127">The user who will be adding the certificate must be an administrator on the server where the certificate store is located.</span></span>

    -   <span data-ttu-id="3e997-128">必须启动服务器服务。</span><span class="sxs-lookup"><span data-stu-id="3e997-128">The server service must be started.</span></span>

    -   <span data-ttu-id="3e997-129">管理服务器上的端口139必须打开 Web 服务 server'sIP。</span><span class="sxs-lookup"><span data-stu-id="3e997-129">Port 139 on the Management Server must be open to the Web Service server’sIP.</span></span>

-   <span data-ttu-id="3e997-130">使用访问控制列表（Acl）确保应用程序包和所有程序包文件受到保护，并且不能被篡改。</span><span class="sxs-lookup"><span data-stu-id="3e997-130">Use access control lists (ACLs) to ensure that the application packages and all package files are protected and cannot be tampered.</span></span> <span data-ttu-id="3e997-131">Acl 限制对存储程序包的位置或文件夹的访问权限，仅允许特定帐户访问。</span><span class="sxs-lookup"><span data-stu-id="3e997-131">ACLs restrict access to the location or folder where you store the packages, allowing access only to certain accounts.</span></span>

-   <span data-ttu-id="3e997-132">确保应用程序虚拟化管理服务器和数据库之间的通道受保护，例如使用 IPsec。</span><span class="sxs-lookup"><span data-stu-id="3e997-132">Make sure that the channel between the Application Virtualization Management Server and the database is secured—for example, by using IPsec.</span></span>

-   <span data-ttu-id="3e997-133">如果程序包存储在 SAN 或 NAS 上，请确保中央存储设备与应用程序虚拟化服务器之间的连接受到保护。</span><span class="sxs-lookup"><span data-stu-id="3e997-133">If packages are stored on a SAN or NAS, ensure the connection between the central storage device and the Application Virtualization Servers is protected.</span></span>

-   <span data-ttu-id="3e997-134">客户端的所有通信信道都应受到保护，包括与发布服务器、应用程序虚拟化服务器的连接，以及到 OSD 和 .ICO 文件的路径-使用 HTTPS 或 IPsec 等协议。</span><span class="sxs-lookup"><span data-stu-id="3e997-134">All communication channels to the client should be protected—including connections to the publishing server, the Application Virtualization Server, and the path to the OSD and ICO files—by using a protocol such as HTTPS or IPsec.</span></span> 

-   <span data-ttu-id="3e997-135">客户端权限应配置为帮助确保程序包不会被用户篡改。</span><span class="sxs-lookup"><span data-stu-id="3e997-135">Client permissions should be configured to help ensure that packages cannot be tampered with by users.</span></span> <span data-ttu-id="3e997-136">特别重要的是，不要授予用户在系统上添加或更新程序包的权限，例如与多个用户共享的远程桌面会话主机（RDSession Host）服务器。</span><span class="sxs-lookup"><span data-stu-id="3e997-136">It is especially important that you do not grant users permission to add or update packages on systems, such as Remote Desktop Session Host (RDSession Host) servers, that are shared with multiple users.</span></span>

-   <span data-ttu-id="3e997-137">必须跨域或林环境允许 Kerberos 身份验证，服务器管理控制台才能正常工作。</span><span class="sxs-lookup"><span data-stu-id="3e997-137">Kerberos authentication must be permitted across domain or forest environments for the Server Management Console to work correctly.</span></span>

-   <span data-ttu-id="3e997-138">此版本的软件不支持在同一台计算机上托管基于 Kerberos 的 RTSP 服务器和基于 Microsoft NTLM 的 IIS 服务器。</span><span class="sxs-lookup"><span data-stu-id="3e997-138">This release of the software does not support hosting a Kerberos-based RTSP server and a Microsoft NTLM-only-based IIS server on the same computer.</span></span> <span data-ttu-id="3e997-139">若要在同一台计算机上托管 RTSP 服务器和 IIS 服务器，请从 IIS 服务器中删除 SPN 并使用 NTLM 身份验证。</span><span class="sxs-lookup"><span data-stu-id="3e997-139">To host an RTSP server and an IIS server on the same computer, remove the SPN from the IIS server and use NTLM authentication.</span></span>

## <span data-ttu-id="3e997-140">相关主题</span><span class="sxs-lookup"><span data-stu-id="3e997-140">Related topics</span></span>


[<span data-ttu-id="3e997-141">规划 Application Virtualization System 部署</span><span class="sxs-lookup"><span data-stu-id="3e997-141">Planning for Application Virtualization System Deployment</span></span>](planning-for-application-virtualization-system-deployment.md)

 

 





