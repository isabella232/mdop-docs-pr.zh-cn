---
title: 加入域和未加入域的客户端
description: 加入域和未加入域的客户端
author: dansimp
ms.assetid: a935dc98-de60-45f3-ab74-2444ce082e88
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c4385ab3f26bb867dd649fe768e1500c9d015ffa
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803007"
---
# <span data-ttu-id="2eb46-103">加入域和未加入域的客户端</span><span class="sxs-lookup"><span data-stu-id="2eb46-103">Domain-Joined and Non-Domain-Joined Clients</span></span>


<span data-ttu-id="2eb46-104">App-v 桌面客户端可以配置为允许连接到网络，无论客户端是加入域还是未加入域。</span><span class="sxs-lookup"><span data-stu-id="2eb46-104">The App-V Desktop Client can be configured to allow connection to a network regardless of whether the client is domain joined or non-domain joined.</span></span>

## <span data-ttu-id="2eb46-105">加入域的客户端</span><span class="sxs-lookup"><span data-stu-id="2eb46-105">Domain-Joined Clients</span></span>


<span data-ttu-id="2eb46-106">已加入域但内部网络外部的客户可以通过使用 VPN 连接与 App-v 基础结构通信。</span><span class="sxs-lookup"><span data-stu-id="2eb46-106">Clients that are domain joined, but outside the internal network, can communicate with the App-V infrastructure by using a VPN connection.</span></span> <span data-ttu-id="2eb46-107">如果你希望向用户提供离开内部网络但仍在应用 V 基础结构中进行通信的功能，你的环境需要极少的设置。</span><span class="sxs-lookup"><span data-stu-id="2eb46-107">When you want to provide users the ability to leave the internal network but still communicate in an App-V infrastructure, your environment requires very little setup.</span></span> <span data-ttu-id="2eb46-108">由于用户已是域的一部分，因此只需确保客户端支持缓存的凭据。</span><span class="sxs-lookup"><span data-stu-id="2eb46-108">Because the users are already part of the domain, you simply need to ensure that Cached Credentials are supported on the client.</span></span> <span data-ttu-id="2eb46-109">这是默认配置，对此设置的任何更改均可通过组策略完成。</span><span class="sxs-lookup"><span data-stu-id="2eb46-109">This is the default configuration, and any changes to this setting can be accomplished from Group Policies.</span></span>

<span data-ttu-id="2eb46-110">如应用程序-V 安全最佳做法指南中所述，用户将尝试将其用户票证发送到 App-v 基础结构进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="2eb46-110">As mentioned in the App-V Security Best Practices Guide, the user will attempt to send their user ticket to the App-V infrastructure for authentication.</span></span> <span data-ttu-id="2eb46-111">如果票证已过期，它将还原为使用 NTLM 和计算机上的缓存凭据。</span><span class="sxs-lookup"><span data-stu-id="2eb46-111">If the ticket is expired, it will revert to using NTLM and the cached credentials on the computer.</span></span> <span data-ttu-id="2eb46-112">若要允许漫游，管理员必须确保内部访问的发布服务器在外部的名称中可用于正确解析的名称。</span><span class="sxs-lookup"><span data-stu-id="2eb46-112">To allow roaming, administrators must ensure that the publishing server being accessed internally is available at the same name externally for the names to resolve properly.</span></span>

## <span data-ttu-id="2eb46-113">非域联接的客户端</span><span class="sxs-lookup"><span data-stu-id="2eb46-113">Non-Domain-Joined Clients</span></span>


<span data-ttu-id="2eb46-114">不加入域但需要在 App-v 基础结构中进行通信的客户端必须配置为确保对 App-v 基础结构的身份验证成功。</span><span class="sxs-lookup"><span data-stu-id="2eb46-114">Clients that are non-domain joined but need to communicate in the App-V infrastructure must be configured to ensure that authentication to the App-V infrastructure is successful.</span></span> <span data-ttu-id="2eb46-115">App-v 桌面客户端不允许提示发布刷新过程，因此必须将客户端配置为向 App-v 管理服务器提供正确的凭据。</span><span class="sxs-lookup"><span data-stu-id="2eb46-115">The App-V Desktop Client does not permit prompting for the publishing refresh process, so the client must be configured to present the proper credentials to the App-V Management Server.</span></span>

<span data-ttu-id="2eb46-116">发布服务器配置为从非域加入的客户端发布刷新时，要求客户端访问的外部名称配置为发布服务器的证书上的公用名称或使用者备用名称（SAN）。</span><span class="sxs-lookup"><span data-stu-id="2eb46-116">The publishing server, which is configured for publishing refresh from the non-domain joined client, requires that the external name that clients access is configured as the common name or a subject alternate name (SAN) on the publishing server’s certificate.</span></span>

## <span data-ttu-id="2eb46-117">相关主题</span><span class="sxs-lookup"><span data-stu-id="2eb46-117">Related topics</span></span>


[<span data-ttu-id="2eb46-118">如何为 Windows Vista 分配正确的凭据</span><span class="sxs-lookup"><span data-stu-id="2eb46-118">How to Assign the Proper Credentials for Windows Vista</span></span>](how-to-assign--the-proper-credentials-for-windows-vista.md)

[<span data-ttu-id="2eb46-119">如何为 Windows XP 分配正确的凭据</span><span class="sxs-lookup"><span data-stu-id="2eb46-119">How to Assign the Proper Credentials for Windows XP</span></span>](how-to-assign--the-proper-credentials-for-windows-xp.md)

 

 





