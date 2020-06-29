---
title: 配置证书以实现安全的流式处理
description: 配置证书以实现安全的流式处理
author: dansimp
ms.assetid: 88dc76d8-7745-4729-92a1-af089c921244
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9376634a1b9843f46dba4cd452e672cc9e535226
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803059"
---
# <span data-ttu-id="662c4-103">配置证书以实现安全的流式处理</span><span class="sxs-lookup"><span data-stu-id="662c4-103">Configuring Certificates to Support Secure Streaming</span></span>


<span data-ttu-id="662c4-104">默认情况下，App-v 服务在网络服务帐户下运行。</span><span class="sxs-lookup"><span data-stu-id="662c4-104">By default, the App-V service runs under the Network Service account.</span></span> <span data-ttu-id="662c4-105">但是，你可以在 Active Directory 域服务中创建服务帐户，并使用 Active Directory 域帐户替换网络服务帐户。</span><span class="sxs-lookup"><span data-stu-id="662c4-105">However, you can create a service account in Active Directory Domain Services and replace the Network Service account with the Active Directory Domain account.</span></span>

<span data-ttu-id="662c4-106">服务运行的安全上下文对于配置增强的安全通信非常重要。</span><span class="sxs-lookup"><span data-stu-id="662c4-106">The security context under which the service runs is important for configuring enhanced secure communications.</span></span> <span data-ttu-id="662c4-107">此安全上下文必须具有证书私钥的读取权限。</span><span class="sxs-lookup"><span data-stu-id="662c4-107">This security context must have read permissions for the certificate private key.</span></span> <span data-ttu-id="662c4-108">当为 App-v 服务器生成 PKCS \ #10*证书签名请求*（CSR）时，将调用 Windows*加密服务提供程序*并生成私钥。</span><span class="sxs-lookup"><span data-stu-id="662c4-108">When a PKCS\#10 *Certificate Signing Request* (CSR) is generated for the App-V server, the Windows *Cryptographic Service Provider* is called and a private key is generated.</span></span> <span data-ttu-id="662c4-109">私钥受到仅授予系统和管理员帐户权限的权限。</span><span class="sxs-lookup"><span data-stu-id="662c4-109">The private key is secured with permissions given to the System and Administrator accounts only.</span></span>

<span data-ttu-id="662c4-110">必须修改私钥上的访问控制列表（Acl），以便应用程序-V 管理或流式服务器访问成功的 TLS 安全通信所需的私钥。</span><span class="sxs-lookup"><span data-stu-id="662c4-110">You must modify the access control lists (ACLs) on the private key to let the App-V Management or Streaming Server access the private key required for successful TLS secured communication.</span></span>

## <span data-ttu-id="662c4-111">获取和安装证书</span><span class="sxs-lookup"><span data-stu-id="662c4-111">Obtaining and Installing a Certificate</span></span>


<span data-ttu-id="662c4-112">为 App-v 获取和安装证书的方案如下所示：</span><span class="sxs-lookup"><span data-stu-id="662c4-112">The scenarios for obtaining and installing a certificate for App-V are as follows:</span></span>

-   <span data-ttu-id="662c4-113">内部公钥基础结构（PKI）。</span><span class="sxs-lookup"><span data-stu-id="662c4-113">Internal public key infrastructure (PKI).</span></span>

-   <span data-ttu-id="662c4-114">第三方证书颁发证书颁发机构（CA）。</span><span class="sxs-lookup"><span data-stu-id="662c4-114">Third-party certificate issuing certification authority (CA).</span></span>

    <span data-ttu-id="662c4-115">**注意** 如果需要从第三方 CA 获取证书，请按照该 CA 网站上提供的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="662c4-115">**Note** If you need to obtain a certificate from a third-party CA, follow the documentation available on that CA’s Web site.</span></span>

     

<span data-ttu-id="662c4-116">如果已部署 PKI 基础结构，请咨询 PKI 管理员，获取符合本主题中所述要求的证书。</span><span class="sxs-lookup"><span data-stu-id="662c4-116">If a PKI infrastructure has been deployed, consult with the PKI administrators to acquire a certificate that complies with the requirements described in this topic.</span></span> <span data-ttu-id="662c4-117">如果 PKI 基础结构不可用，请使用第三方 CA 获取有效的证书。</span><span class="sxs-lookup"><span data-stu-id="662c4-117">If a PKI infrastructure is not available, use a third-party CA to obtain a valid certificate.</span></span>

<span data-ttu-id="662c4-118">有关获取和安装证书的分步指南，请参阅 <https://go.microsoft.com/fwlink/?LinkId=151969> 。</span><span class="sxs-lookup"><span data-stu-id="662c4-118">For step-by-step guidance for obtaining and installing a certificate, see <https://go.microsoft.com/fwlink/?LinkId=151969>.</span></span>

## <span data-ttu-id="662c4-119">相关主题</span><span class="sxs-lookup"><span data-stu-id="662c4-119">Related topics</span></span>


<span data-ttu-id="662c4-120">配置证书以支持安全流式处理[如何修改私钥权限以支持管理服务器或流式处理服务器](how-to-modify-private-key-permissions-to-support-management-server-or-streaming-server.md)</span><span class="sxs-lookup"><span data-stu-id="662c4-120">Configuring Certificates to Support Secure Streaming [How to Modify Private Key Permissions to Support Management Server or Streaming Server](how-to-modify-private-key-permissions-to-support-management-server-or-streaming-server.md)</span></span>

 

 





