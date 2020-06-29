---
title: 配置 Management 或 Streaming Server 以实现安全的安装后通信
description: 配置 Management 或 Streaming Server 以实现安全的安装后通信
author: dansimp
ms.assetid: 1062a213-470b-4ae2-b12f-b3e28a6ab745
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2a2713f130809c431b7444f3e928a523838597a6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803056"
---
# <span data-ttu-id="b35d0-103">配置 Management 或 Streaming Server 以实现安全的安装后通信</span><span class="sxs-lookup"><span data-stu-id="b35d0-103">Configuring Management or Streaming Server for Secure Communications Post-Installation</span></span>


<span data-ttu-id="b35d0-104">如果在安装 app-v 管理服务器或 App-v 流式处理服务器之前未设置正确的证书，则可以针对初始安装后的应用配置 app-v 以增强安全性。</span><span class="sxs-lookup"><span data-stu-id="b35d0-104">If the proper certificate was not provisioned before the installation of the App-V Management Server or the App-V Streaming Server, App-V can be configured for enhanced security after the initial installation.</span></span> <span data-ttu-id="b35d0-105">你可以通过 app-v 管理控制台配置 App-v 管理服务器。</span><span class="sxs-lookup"><span data-stu-id="b35d0-105">You can configure the App-V Management Server through the App-V Management Console.</span></span> <span data-ttu-id="b35d0-106">但是，app-v 流处理服务器通过注册表进行管理。</span><span class="sxs-lookup"><span data-stu-id="b35d0-106">However, the App-V Streaming Server is managed through the registry.</span></span> <span data-ttu-id="b35d0-107">在任何一种情况下，证书都必须包含适用于服务器身份验证的正确*扩展密钥用法*（EKU），并且网络服务必须具有对私钥的读取访问权限。</span><span class="sxs-lookup"><span data-stu-id="b35d0-107">In either case, the certificate must include the proper *extended key usage* (EKU) for Server authentication and the Network Service must have read access to the private key.</span></span>

## <span data-ttu-id="b35d0-108">本部分内容</span><span class="sxs-lookup"><span data-stu-id="b35d0-108">In This Section</span></span>


<a href="" id="how-to-configure-management-server-security-post-installation"></a>[<span data-ttu-id="b35d0-109">如何配置 Management Server 安装后的安全性</span><span class="sxs-lookup"><span data-stu-id="b35d0-109">How to Configure Management Server Security Post-Installation</span></span>](how-to-configure-management-server-security-post-installation.md)  
<span data-ttu-id="b35d0-110">提供可通过使用 App-v 管理控制台执行安装后执行的过程，以添加证书并配置 App-v 管理服务器以增强安全性。</span><span class="sxs-lookup"><span data-stu-id="b35d0-110">Provides a procedure that can be performed post-installation, using the App-V Management Console, to add the certificate and configure the App-V Management Server for enhanced security.</span></span>

<a href="" id="how-to-configure-streaming-server-security-post-installation"></a>[<span data-ttu-id="b35d0-111">如何配置 Streaming Server 安装后的安全性</span><span class="sxs-lookup"><span data-stu-id="b35d0-111">How to Configure Streaming Server Security Post-Installation</span></span>](how-to-configure-streaming-server-security-post-installation.md)  
<span data-ttu-id="b35d0-112">提供可在安装后执行的过程，以添加证书并配置 App-v 流处理服务器以增强安全性。</span><span class="sxs-lookup"><span data-stu-id="b35d0-112">Provides a procedure that can be performed post-installation, to add the certificate and configure the App-V Streaming Server for enhanced security.</span></span>

<a href="" id="troubleshooting-certificate-permission-issues"></a>[<span data-ttu-id="b35d0-113">解决证书权限问题</span><span class="sxs-lookup"><span data-stu-id="b35d0-113">Troubleshooting Certificate Permission Issues</span></span>](troubleshooting-certificate-permission-issues.md)  
<span data-ttu-id="b35d0-114">提供有关在没有为网络服务的正确 ACL 配置私钥时的故障排除指南。</span><span class="sxs-lookup"><span data-stu-id="b35d0-114">Provides troubleshooting guidance for when the private key has not been configured with the proper ACL for the Network Service.</span></span>

 

 





