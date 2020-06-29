---
title: 如何修改私钥权限以支持 Management Server 或 Streaming Server
description: 如何修改私钥权限以支持 Management Server 或 Streaming Server
author: dansimp
ms.assetid: 1ebe86fa-0fbc-4512-aebc-0a5da991cd43
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 2e35c2df518f22ba81a070d2c40ad3862f376a6a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801252"
---
# <span data-ttu-id="a6084-103">如何修改私钥权限以支持 Management Server 或 Streaming Server</span><span class="sxs-lookup"><span data-stu-id="a6084-103">How to Modify Private Key Permissions to Support Management Server or Streaming Server</span></span>


<span data-ttu-id="a6084-104">若要支持更安全的 app-v 安装，可以使用以下过程在 Windows Server2003 或 Windows Server2008 中修改私钥。</span><span class="sxs-lookup"><span data-stu-id="a6084-104">To support a more secure App-V installation, you can use the following procedures to modify private keys in either Windows Server2003 or Windows Server2008.</span></span> <span data-ttu-id="a6084-105">若要修改私钥的权限，您可以使用 Windows Server2003 资源工具包工具 `WinHttpCertCfg.exe` 。</span><span class="sxs-lookup"><span data-stu-id="a6084-105">To modify the permissions of the private key, you can use the Windows Server2003 Resource Kit tool `WinHttpCertCfg.exe`.</span></span>

<span data-ttu-id="a6084-106">对于 Windows Server2003，此过程需要满足此文档中列出的先决条件的证书已安装在要安装 app-v 管理或流式处理服务器的计算机或计算机上。</span><span class="sxs-lookup"><span data-stu-id="a6084-106">For Windows Server2003, the procedure requires that a certificate that meets the prerequisites listed in this document is installed on the computer or computers on which you will install the App-V Management or Streaming Server.</span></span> <span data-ttu-id="a6084-107">有关使用该工具的其他信息 `WinHttpCertCfg.exe` ，请访问 <https://go.microsoft.com/fwlink/?LinkId=151981> 。</span><span class="sxs-lookup"><span data-stu-id="a6084-107">Additional information about using the `WinHttpCertCfg.exe` tool is available at <https://go.microsoft.com/fwlink/?LinkId=151981>.</span></span>

<span data-ttu-id="a6084-108">在 Windows Server2008 中，更改私钥的 Acl 的过程更简单。</span><span class="sxs-lookup"><span data-stu-id="a6084-108">In Windows Server2008, the process of changing the ACLs on the private key is much simpler.</span></span> <span data-ttu-id="a6084-109">证书的用户界面可用于管理私钥权限。</span><span class="sxs-lookup"><span data-stu-id="a6084-109">The certificate’s user interface can be used to manage private key permissions.</span></span>

<span data-ttu-id="a6084-110">**注意** 默认安全上下文为网络服务;但是，可以改为使用域帐户。</span><span class="sxs-lookup"><span data-stu-id="a6084-110">**Note** The default security context is Network Service; however, a domain account can be used instead.</span></span>

 

**<span data-ttu-id="a6084-111">在 Windows Server2003 中管理私钥</span><span class="sxs-lookup"><span data-stu-id="a6084-111">To manage private keys in Windows Server2003</span></span>**

1.  <span data-ttu-id="a6084-112">在将成为 App-v 管理或流式服务器的计算机上，在命令提示符处键入以下命令以列出分配给特定证书的当前权限：</span><span class="sxs-lookup"><span data-stu-id="a6084-112">On the computer that will become the App-V Management or Streaming Server, type the following command in a command prompt to list the current permissions assigned to a specific certificate:</span></span>

    `winhttpcertcfg -l -c LOCAL_MACHINE\My -s Name_of_cert`

2.  <span data-ttu-id="a6084-113">如有必要，请修改证书的权限以提供对将用于管理或流式处理服务的安全上下文的读取访问权限：</span><span class="sxs-lookup"><span data-stu-id="a6084-113">If necessary, modify the permissions of the certificate to provide read access to the security context that will be used for Management or Streaming Service:</span></span>

    `winhttpcertcfg -g -c LOCAL_MACHINE\My -s Name_of_cert -a NetworkService`

3.  <span data-ttu-id="a6084-114">通过列出证书的权限来验证是否已正确添加了安全上下文：</span><span class="sxs-lookup"><span data-stu-id="a6084-114">Verify that the security context was properly added by listing the permissions on the certificate:</span></span>

    `winhttpcertcfg –l –c LOCAL_MACHINE\My –s Name_of_cert`

**<span data-ttu-id="a6084-115">在 Windows Server2008 中管理私钥</span><span class="sxs-lookup"><span data-stu-id="a6084-115">To manage private keys in Windows Server2008</span></span>**

1.  <span data-ttu-id="a6084-116">使用面向*本地计算机*证书存储的 "*证书*" 管理单元创建 MICROSOFT 管理控制台（MMC）。</span><span class="sxs-lookup"><span data-stu-id="a6084-116">Create a Microsoft Management Console (MMC) with the *Certificates* snap-in that targets the *Local Machine* certificate store.</span></span>

2.  <span data-ttu-id="a6084-117">展开 MMC，然后选择 "**管理私钥**"。</span><span class="sxs-lookup"><span data-stu-id="a6084-117">Expand the MMC and select **Manage Private Keys**.</span></span>

3.  <span data-ttu-id="a6084-118">在 "**安全**" 选项卡上，添加具有**读取**权限的**网络服务**帐户。</span><span class="sxs-lookup"><span data-stu-id="a6084-118">On the **Security** tab, add the **Network Service** account with **Read** access.</span></span>

## <span data-ttu-id="a6084-119">相关主题</span><span class="sxs-lookup"><span data-stu-id="a6084-119">Related topics</span></span>


[<span data-ttu-id="a6084-120">配置证书以支持 App-V Management Server 或 Streaming Server</span><span class="sxs-lookup"><span data-stu-id="a6084-120">Configuring Certificates to Support App-V Management Server or Streaming Server</span></span>](configuring-certificates-to-support-app-v-management-server-or-streaming-server.md)

[<span data-ttu-id="a6084-121">配置证书以实现安全的流式处理</span><span class="sxs-lookup"><span data-stu-id="a6084-121">Configuring Certificates to Support Secure Streaming</span></span>](configuring-certificates-to-support-secure-streaming.md)

 

 





