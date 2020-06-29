---
title: 安全地安装 App-V Management Server 或 Streaming Server
description: 安全地安装 App-V Management Server 或 Streaming Server
author: dansimp
ms.assetid: d2a51a81-a80f-427c-a727-611e1eb74f02
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 0150f4dc7f489731c4a818fed9780ebb25dbd24f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798949"
---
# <span data-ttu-id="22ee3-103">安全地安装 App-V Management Server 或 Streaming Server</span><span class="sxs-lookup"><span data-stu-id="22ee3-103">Installing App-V Management Server or Streaming Server Securely</span></span>


<span data-ttu-id="22ee3-104">本节中的主题提供有关安装应用程序 V 管理服务器或 App-v 流式处理服务器的增强安全版本的信息。</span><span class="sxs-lookup"><span data-stu-id="22ee3-104">The topics in this section provide information for installing an enhanced security version of the App-V Management Server or the App-V Streaming Server.</span></span>

<span data-ttu-id="22ee3-105">**注意** 安装或配置应用程序 V 管理或流式服务器以使用增强的安全性（例如，传输层安全性或 TLS）要求 x.509 V3 证书已预配到 app-v 服务器。</span><span class="sxs-lookup"><span data-stu-id="22ee3-105">**Note** Installing or configuring an App-V Management or Streaming Server to use enhanced security (for example, Transport Layer Security, or TLS) requires that an X.509 V3 certificate has been provisioned to the App-V server.</span></span>

 

<span data-ttu-id="22ee3-106">准备安装或配置安全管理或流式服务器时，请考虑以下技术要求：</span><span class="sxs-lookup"><span data-stu-id="22ee3-106">When you prepare to install or configure a secure Management or Streaming Server, consider the following technical requirements:</span></span>

-   <span data-ttu-id="22ee3-107">该证书必须有效。</span><span class="sxs-lookup"><span data-stu-id="22ee3-107">The certificate must be valid.</span></span> <span data-ttu-id="22ee3-108">如果证书无效，客户端将结束连接。</span><span class="sxs-lookup"><span data-stu-id="22ee3-108">If the certificate is not valid, the client ends the connection.</span></span>

-   <span data-ttu-id="22ee3-109">证书必须包含正确的*增强密钥用法*（EKU），即服务器身份验证（OID 1.3.6.1.5.5.7.3.1）。</span><span class="sxs-lookup"><span data-stu-id="22ee3-109">The certificate must contain the correct *Enhanced Key Usage* (EKU)—Server Authentication (OID 1.3.6.1.5.5.7.3.1).</span></span> <span data-ttu-id="22ee3-110">如果证书不包含此 EKU，则客户端将终止连接。</span><span class="sxs-lookup"><span data-stu-id="22ee3-110">If the certificate does not contain this EKU, the client ends the connection.</span></span>

-   <span data-ttu-id="22ee3-111">证书完全限定的域名（FQDN）必须与安装它的服务器相匹配。</span><span class="sxs-lookup"><span data-stu-id="22ee3-111">The certificate fully qualified domain name (FQDN) must match the server on which it is installed.</span></span> <span data-ttu-id="22ee3-112">例如，如果客户端正在呼叫， `RTSPS://Myserver.mycompany.com/content/MyApp.sft` 并且 "**颁发给**" 字段的证书设置为 `Server1.mycompany.com` ，则客户端将不会连接到服务器，并且会话将结束。</span><span class="sxs-lookup"><span data-stu-id="22ee3-112">For example, if the client is calling `RTSPS://Myserver.mycompany.com/content/MyApp.sft` and the certificate **Issued To** field is set to `Server1.mycompany.com`, the client will not connect to the server and the session ends.</span></span> <span data-ttu-id="22ee3-113">向用户报告该故障。</span><span class="sxs-lookup"><span data-stu-id="22ee3-113">The failure is reported to the user.</span></span>

    <span data-ttu-id="22ee3-114">**注意** 如果在网络负载平衡群集中使用 App-v，则必须使用主题备用名称（San）配置证书以支持 RTSPS。</span><span class="sxs-lookup"><span data-stu-id="22ee3-114">**Note** If you are using App-V in a Network Load Balancing cluster, you must configure the certificate with Subject Alternate Names (SANs) to support RTSPS.</span></span> <span data-ttu-id="22ee3-115">有关配置证书颁发机构（CA）和通过 San 创建证书的信息，请参阅 <https://go.microsoft.com/fwlink/?LinkId=133228> 。</span><span class="sxs-lookup"><span data-stu-id="22ee3-115">For information about configuring the certification authority (CA) and creating certificates with SANs, see <https://go.microsoft.com/fwlink/?LinkId=133228>.</span></span>

     

-   <span data-ttu-id="22ee3-116">客户端和服务器需要信任根 CA-将证书颁发给 App-v 服务器的 CA 必须受连接到服务器的客户端信任。</span><span class="sxs-lookup"><span data-stu-id="22ee3-116">The client and the server need to trust the root CA—The CA issuing the certificate to the App-V server must by trusted by the client connecting to the server.</span></span> <span data-ttu-id="22ee3-117">如果不是，则客户端结束连接。</span><span class="sxs-lookup"><span data-stu-id="22ee3-117">If not, the client ends the connection.</span></span>

-   <span data-ttu-id="22ee3-118">证书的专用密钥必须更改权限，以允许 App-v 服务帐户访问证书。</span><span class="sxs-lookup"><span data-stu-id="22ee3-118">The certificate’s private key must have permissions changed to allow the App-V Service account to access the certificate.</span></span> <span data-ttu-id="22ee3-119">默认情况下，App-v 使用网络服务帐户，并且默认情况下，网络服务帐户不具有访问私钥的权限，这将阻止安全连接。</span><span class="sxs-lookup"><span data-stu-id="22ee3-119">By default, App-V uses the Network Service account, and by default, the Network Service account does not have permission to access the private key, which will prevent secure connections.</span></span>

## <span data-ttu-id="22ee3-120">本部分内容</span><span class="sxs-lookup"><span data-stu-id="22ee3-120">In This Section</span></span>


<a href="" id="configuring-certificates-to-support-secure-streaming"></a>[<span data-ttu-id="22ee3-121">配置证书以实现安全的流式处理</span><span class="sxs-lookup"><span data-stu-id="22ee3-121">Configuring Certificates to Support Secure Streaming</span></span>](configuring-certificates-to-support-secure-streaming.md)  
<span data-ttu-id="22ee3-122">提供有关获取、配置和安装证书以支持安全流的信息。</span><span class="sxs-lookup"><span data-stu-id="22ee3-122">Provides information about obtaining, configuring, and installing certificates to support secure streaming.</span></span>

<a href="" id="how-to-modify-private-key-permissions-to-support-management-server-or-streaming-server"></a>[<span data-ttu-id="22ee3-123">如何修改私钥权限以支持 Management Server 或 Streaming Server</span><span class="sxs-lookup"><span data-stu-id="22ee3-123">How to Modify Private Key Permissions to Support Management Server or Streaming Server</span></span>](how-to-modify-private-key-permissions-to-support-management-server-or-streaming-server.md)  
<span data-ttu-id="22ee3-124">提供可用于修改 Windows Server2003 和 Windows Server2008 中的密钥的过程。</span><span class="sxs-lookup"><span data-stu-id="22ee3-124">Provides procedures you can use to modify keys in Windows Server2003 and Windows Server2008.</span></span>

<a href="" id="configuring-certificates-to-support-app-v-management-server-or-streaming-server"></a>[<span data-ttu-id="22ee3-125">配置证书以支持 App-V Management Server 或 Streaming Server</span><span class="sxs-lookup"><span data-stu-id="22ee3-125">Configuring Certificates to Support App-V Management Server or Streaming Server</span></span>](configuring-certificates-to-support-app-v-management-server-or-streaming-server.md)  
<span data-ttu-id="22ee3-126">提供有关为 App-v 管理或流式处理服务器配置证书的信息，包括有关为网络负载平衡环境配置证书的信息。</span><span class="sxs-lookup"><span data-stu-id="22ee3-126">Provides information about configuring certificates for the App-V Management or Streaming Servers, including information about configuring certificates for Network Load Balancing environments.</span></span>

 

 





