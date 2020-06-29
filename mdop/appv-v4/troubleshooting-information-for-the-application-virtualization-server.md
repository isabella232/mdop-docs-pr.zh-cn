---
title: Application Virtualization Server 的故障排除信息
description: Application Virtualization Server 的故障排除信息
author: dansimp
ms.assetid: e9d43d9b-84f2-4d1b-bb90-a13740151e0c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7c98ad42a00e20900263d0598822a6381e2df1ef
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798721"
---
# <span data-ttu-id="0a174-103">Application Virtualization Server 的故障排除信息</span><span class="sxs-lookup"><span data-stu-id="0a174-103">Troubleshooting Information for the Application Virtualization Server</span></span>


<span data-ttu-id="0a174-104">本主题包含可用于解决应用程序虚拟化（app-v）服务器上的各种问题的信息。</span><span class="sxs-lookup"><span data-stu-id="0a174-104">This topic includes information that you can use to troubleshoot various issues on the Application Virtualization (App-V) Servers.</span></span>

## <span data-ttu-id="0a174-105">安装服务器后，在安装程序日志中出现警告消息25017</span><span class="sxs-lookup"><span data-stu-id="0a174-105">Warning Message 25017 in Setup Log After Installing the Server</span></span>


<span data-ttu-id="0a174-106">安装后，你可能会在服务器设置日志中发现以下消息。</span><span class="sxs-lookup"><span data-stu-id="0a174-106">You might find the following message in the server setup log after installation.</span></span>

*<span data-ttu-id="0a174-107">警告25017。</span><span class="sxs-lookup"><span data-stu-id="0a174-107">Warning 25017.</span></span> <span data-ttu-id="0a174-108">安装程序无法为服务器创建 Active Directory 标记对象。</span><span class="sxs-lookup"><span data-stu-id="0a174-108">The installation Program could not create the Active Directory marker object for the server.</span></span> <span data-ttu-id="0a174-109">用于安装的帐户没有足够的权限写入 Active Directory 或 Active Directory 不可用。</span><span class="sxs-lookup"><span data-stu-id="0a174-109">The account used to install did not have the sufficient rights to write to Active Directory or Active Directory was unavailable.</span></span>*

<span data-ttu-id="0a174-110">App-v 管理或流式服务器安装程序在 Active Directory 域服务（添加）中的计算机对象下创建一个服务连接点条目，此条目对应于运行安装程序的帐户具有相应权限时安装了该服务器的计算机。</span><span class="sxs-lookup"><span data-stu-id="0a174-110">The App-V Management or Streaming Server installer creates a Service Connection Point entry under the Computer object in Active Directory Domain Services (ADDS) that corresponds to the computer on which the server is installed if the account used to run the installer has the appropriate rights.</span></span> <span data-ttu-id="0a174-111">如果无法创建此条目，则不会导致安装失败，这不会对产品的功能产生任何影响。</span><span class="sxs-lookup"><span data-stu-id="0a174-111">Failure to create this entry will not cause the install to fail and this should not otherwise affect the functioning of the product.</span></span> <span data-ttu-id="0a174-112">出现故障的可能原因是用于运行安装的用户帐户没有足够的权限来进行添加。</span><span class="sxs-lookup"><span data-stu-id="0a174-112">The likely cause of any failure is that the user account used to run the install did not have sufficient rights to write to ADDS.</span></span> <span data-ttu-id="0a174-113">尽管在 "添加" 中注册 app-v 服务器是可选的，但执行此操作的一个优点是支持集中管理工具找到用于清单和管理用途的 app-v 服务器。</span><span class="sxs-lookup"><span data-stu-id="0a174-113">Although registering the App-V server in ADDS is optional, one benefit of doing so enables centralized management tools to locate the App-V server for inventory and management purposes.</span></span>

## <span data-ttu-id="0a174-114">相关主题</span><span class="sxs-lookup"><span data-stu-id="0a174-114">Related topics</span></span>


[<span data-ttu-id="0a174-115">Application Virtualization Server</span><span class="sxs-lookup"><span data-stu-id="0a174-115">Application Virtualization Server</span></span>](application-virtualization-server.md)

 

 





