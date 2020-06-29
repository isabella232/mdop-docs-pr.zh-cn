---
title: 配置 IIS 以实现安全的流式处理
description: 配置 IIS 以实现安全的流式处理
author: dansimp
ms.assetid: 9a80a703-4642-4bec-b7af-dc7cb6b76925
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 724fd247d98c265421cea13f4b91c97049a2b4d4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803057"
---
# <span data-ttu-id="b9c9a-103">配置 IIS 以实现安全的流式处理</span><span class="sxs-lookup"><span data-stu-id="b9c9a-103">Configuring IIS for Secure Streaming</span></span>


<span data-ttu-id="b9c9a-104">使用 Microsoft Application Virtualization （App-v）版本4.5 的发布，你可以将 HTTP 和 HTTPS 用作将应用程序包传输到 App-v 客户端的协议。</span><span class="sxs-lookup"><span data-stu-id="b9c9a-104">With the release of Microsoft Application Virtualization (App-V) version 4.5, you can use HTTP and HTTPS as protocols for streaming application packages to the App-V clients.</span></span> <span data-ttu-id="b9c9a-105">此选项使组织能够利用 IIS 通常提供的其他可伸缩性。</span><span class="sxs-lookup"><span data-stu-id="b9c9a-105">This option enables organizations to leverage the additional scalability that IIS typically offers.</span></span> <span data-ttu-id="b9c9a-106">将 IIS 用作流式处理服务器时，可以使用 HTTPS （而不是 HTTP）来保护客户端与服务器之间的通信。</span><span class="sxs-lookup"><span data-stu-id="b9c9a-106">When you use IIS as a streaming server, you can help secure the communications between the client and server by using HTTPS instead of HTTP.</span></span>

<span data-ttu-id="b9c9a-107">**注意** 如果你想要从文件服务器流出应用程序，你应该增强与应用程序包的通信的安全。</span><span class="sxs-lookup"><span data-stu-id="b9c9a-107">**Note** If you want to stream applications from a file server, you should enhance the security of the communications to the application packages.</span></span> <span data-ttu-id="b9c9a-108">可使用 IPsec 实现此目的。</span><span class="sxs-lookup"><span data-stu-id="b9c9a-108">This can be achieved using IPsec.</span></span> <span data-ttu-id="b9c9a-109">有关详细信息，请参阅 TechNet 库中的以下主题：</span><span class="sxs-lookup"><span data-stu-id="b9c9a-109">For more information see the following topics in the TechNet Library:</span></span>

-   <span data-ttu-id="b9c9a-110">对于 Windows Server2003，</span><span class="sxs-lookup"><span data-stu-id="b9c9a-110">For Windows Server2003,</span></span> <https://go.microsoft.com/fwlink/?LinkId=133226>

-   <span data-ttu-id="b9c9a-111">对于 Windows Server 2008，</span><span class="sxs-lookup"><span data-stu-id="b9c9a-111">For Windows Server 2008,</span></span> <https://go.microsoft.com/fwlink/?LinkId=133227>

 

## <span data-ttu-id="b9c9a-112">MIME 类型</span><span class="sxs-lookup"><span data-stu-id="b9c9a-112">MIME Types</span></span>


<span data-ttu-id="b9c9a-113">当你使用 IIS 使用 HTTP 或 HTTPS 流式处理虚拟应用程序时，为了支持 App-v，必须将以下 MIME 类型添加到 IIS 服务器：</span><span class="sxs-lookup"><span data-stu-id="b9c9a-113">When you use IIS to stream virtual applications with HTTP or HTTPS, to support App-V, the following MIME types must be added to the IIS server:</span></span>

-   <span data-ttu-id="b9c9a-114">.OSD = TXT</span><span class="sxs-lookup"><span data-stu-id="b9c9a-114">.OSD=TXT</span></span>

-   <span data-ttu-id="b9c9a-115">.SFT = Binary</span><span class="sxs-lookup"><span data-stu-id="b9c9a-115">.SFT=Binary</span></span>

<span data-ttu-id="b9c9a-116">将以下知识库文章用作添加 MIME 类型的指南：</span><span class="sxs-lookup"><span data-stu-id="b9c9a-116">Use the following KB articles as guidance for adding MIME types:</span></span>

<span data-ttu-id="b9c9a-117">IIS 6.0：</span><span class="sxs-lookup"><span data-stu-id="b9c9a-117">IIS 6.0:</span></span> <https://go.microsoft.com/fwlink/?LinkId=151973>

<span data-ttu-id="b9c9a-118">IIS 7.0：</span><span class="sxs-lookup"><span data-stu-id="b9c9a-118">IIS 7.0:</span></span> <https://go.microsoft.com/fwlink/?LinkId=151977>

## <span data-ttu-id="b9c9a-119">Kerberos 身份验证</span><span class="sxs-lookup"><span data-stu-id="b9c9a-119">Kerberos Authentication</span></span>


<span data-ttu-id="b9c9a-120">使用 HTTP 或 HTTPS 和 Kerberos 身份验证流式传输 .ICO、OSD 或 SFT 文件时，您将提高环境的安全性。</span><span class="sxs-lookup"><span data-stu-id="b9c9a-120">When you use HTTP or HTTPS and Kerberos authentication to stream ICO, OSD, or SFT files, you are enhancing the security of your environment.</span></span> <span data-ttu-id="b9c9a-121">但是，为了使 IIS 支持 Kerberos 身份验证，必须配置正确的服务主体名称（SPN）。</span><span class="sxs-lookup"><span data-stu-id="b9c9a-121">However, for IIS to support Kerberos authentication, you must configure a proper Service Principal Name (SPN).</span></span> <span data-ttu-id="b9c9a-122">此 `setspn.exe` 工具适用于 Windows Server2003 从安装 CD 上的支持工具，内置于 Windows Server2008。</span><span class="sxs-lookup"><span data-stu-id="b9c9a-122">The `setspn.exe` tool is available for Windows Server2003 from the Support Tools on the installation CD and is built-in to Windows Server2008.</span></span>

<span data-ttu-id="b9c9a-123">若要创建 SPN，请 `setspn.exe` 从作为域管理员成员身份登录的命令提示符处运行，例如 `setspn.exe –A HTTP/FQDN of Server ServerName` 。</span><span class="sxs-lookup"><span data-stu-id="b9c9a-123">To create an SPN, run `setspn.exe` from a command prompt while logged in as a member of Domain Administrators—for example, `setspn.exe –A HTTP/FQDN of Server ServerName`.</span></span>

## <span data-ttu-id="b9c9a-124">相关主题</span><span class="sxs-lookup"><span data-stu-id="b9c9a-124">Related topics</span></span>


[<span data-ttu-id="b9c9a-125">配置 Management 或 Streaming Server 以实现安全的安装后通信</span><span class="sxs-lookup"><span data-stu-id="b9c9a-125">Configuring Management or Streaming Server for Secure Communications Post-Installation</span></span>](configuring-management-or-streaming-server-for-secure-communications-post-installation.md)

 

 





