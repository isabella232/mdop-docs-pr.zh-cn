---
title: 配置证书以支持 App-V Web Management Service
description: 配置证书以支持 App-V Web Management Service
author: dansimp
ms.assetid: b7960161-2c19-4cbf-a98a-d4b06f547dce
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 23839e6fad79c1f10eb2416941396ad3c6f04d26
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803058"
---
# <span data-ttu-id="a2aef-103">配置证书以支持 App-V Web Management Service</span><span class="sxs-lookup"><span data-stu-id="a2aef-103">Configuring Certificates to Support the App-V Web Management Service</span></span>


<span data-ttu-id="a2aef-104">App-v Web 管理服务必须配置为支持基于 SSL 的连接，以帮助保护通信。</span><span class="sxs-lookup"><span data-stu-id="a2aef-104">The App-V Web Management Service must be configured to support SSL-based connections to help secure the communication.</span></span> <span data-ttu-id="a2aef-105">此过程要求安装管理服务的 Web 服务器或计算机具有向服务或计算机颁发的证书。</span><span class="sxs-lookup"><span data-stu-id="a2aef-105">This process requires that the Web server or computer on which the Management Service is installed has a certificate issued to the service or computer.</span></span>

<span data-ttu-id="a2aef-106">以下方案说明了如何为此目的获取证书：</span><span class="sxs-lookup"><span data-stu-id="a2aef-106">The following scenarios illustrate how to obtain a certificate for this purpose:</span></span>

1.  <span data-ttu-id="a2aef-107">公司基础结构已有一个公钥基础结构（PKI），该公钥基础结构将自动向计算机颁发证书。</span><span class="sxs-lookup"><span data-stu-id="a2aef-107">The company infrastructure already has a public key infrastructure (PKI) in place that automatically issues certificates to computers.</span></span>

2.  <span data-ttu-id="a2aef-108">公司基础结构已有一个 PKI，虽然它不会自动将证书颁发给计算机。</span><span class="sxs-lookup"><span data-stu-id="a2aef-108">The company infrastructure already has a PKI in place, although it does not automatically issue certificates to computers.</span></span>

3.  <span data-ttu-id="a2aef-109">公司基础结构没有 PKI。</span><span class="sxs-lookup"><span data-stu-id="a2aef-109">The company infrastructure has no PKI in place.</span></span>

<span data-ttu-id="a2aef-110">在上述每个方案中，获取证书的方法是不同的，但最终结果是相同的。</span><span class="sxs-lookup"><span data-stu-id="a2aef-110">In each of the preceding scenarios, the method for obtaining a certificate is different, but the end result is the same.</span></span> <span data-ttu-id="a2aef-111">管理员必须为 IIS 默认网站分配证书，并将 App-v Web 管理服务配置为需要安全通信。</span><span class="sxs-lookup"><span data-stu-id="a2aef-111">The administrator must assign a certificate to the IIS Default Web Site and configure the App-V Web Management Service to require secure communications.</span></span>

<span data-ttu-id="a2aef-112">**重要提示** 证书的名称必须与服务器的名称相匹配。</span><span class="sxs-lookup"><span data-stu-id="a2aef-112">**Important** The name of the certificate must match the name of the server.</span></span> <span data-ttu-id="a2aef-113">最佳做法是对证书的通用名称使用完全限定的域名（Fqdn）。</span><span class="sxs-lookup"><span data-stu-id="a2aef-113">It is a best practice to use fully qualified domain names (FQDNs) for the common name of the certificate.</span></span>

 

<span data-ttu-id="a2aef-114">App-v 可以使用 IIS 服务器支持不同的基础结构配置。</span><span class="sxs-lookup"><span data-stu-id="a2aef-114">App-V can use IIS servers to support different infrastructure configurations.</span></span> <span data-ttu-id="a2aef-115">有关配置 IIS 服务器以支持 HTTPS 的详细信息，请参阅 <https://go.microsoft.com/fwlink/?LinkId=151972> 。</span><span class="sxs-lookup"><span data-stu-id="a2aef-115">For more information about configuring IIS servers to support HTTPS, see <https://go.microsoft.com/fwlink/?LinkId=151972>.</span></span>

## <span data-ttu-id="a2aef-116">相关主题</span><span class="sxs-lookup"><span data-stu-id="a2aef-116">Related topics</span></span>


[<span data-ttu-id="a2aef-117">如何安装和配置 App-V Management Console 以实现更安全的环境</span><span class="sxs-lookup"><span data-stu-id="a2aef-117">How to Install and Configure the App-V Management Console for a More Secure Environment</span></span>](how-to-install-and-configure-the-app-v-management-console-for-a-more-secure-environment.md)

 

 





