---
title: 维护 MBAM 1.0
description: 维护 MBAM 1.0
author: dansimp
ms.assetid: 02ffb093-c364-4837-bbe8-23d4c09fbd3d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7eecef4e82680b08fde1b1bef88487a6fc156fe4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803835"
---
# <span data-ttu-id="28dc2-103">维护 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="28dc2-103">Maintaining MBAM 1.0</span></span>


<span data-ttu-id="28dc2-104">完成所有必要的计划，然后部署 Microsoft BitLocker 管理和监视（MBAM）后，你可以将 MBAM 配置为在使用它管理企业 BitLocker 加密操作时以高度可用的方式运行。</span><span class="sxs-lookup"><span data-stu-id="28dc2-104">After you complete all the necessary planning and then deploy Microsoft BitLocker Administration and Monitoring (MBAM), you can configure MBAM to run in a highly available fashion while using it to manage enterprise BitLocker encryption operations.</span></span> <span data-ttu-id="28dc2-105">本部分中的信息介绍了 MBAM 的高可用性选项，以及如何在必要时移动 MBAM 服务器功能。</span><span class="sxs-lookup"><span data-stu-id="28dc2-105">The information in this section describes high availability options for MBAM, as well as how to move MBAM Server features if necessary.</span></span>

## <span data-ttu-id="28dc2-106">MBAM 管理包</span><span class="sxs-lookup"><span data-stu-id="28dc2-106">MBAM Management Pack</span></span>


<span data-ttu-id="28dc2-107">可从 Microsoft 下载中心下载 MBAM 的 MicrosoftSystemCenterOperationsManager 管理包。</span><span class="sxs-lookup"><span data-stu-id="28dc2-107">The MicrosoftSystemCenterOperationsManager Management Pack for MBAM is available for download from the Microsoft Download Center.</span></span>

<span data-ttu-id="28dc2-108">此管理包监视服务器端基础结构中的关键交互，例如 web 服务和数据库之间的连接以及网站与其支持的 web 服务之间的操作调用。</span><span class="sxs-lookup"><span data-stu-id="28dc2-108">This management pack monitors the critical interactions in the server-side infrastructure, such as the connections between the web services and databases and the operational calls between websites and their supportive web service.</span></span> <span data-ttu-id="28dc2-109">它还会在桌面客户端和其各自的接收 web 服务终结点之间上载请求。</span><span class="sxs-lookup"><span data-stu-id="28dc2-109">It also uploads the requests between desktop clients and their respective receiving web service endpoints.</span></span>

[<span data-ttu-id="28dc2-110">Microsoft BitLocker 管理和监视管理包</span><span class="sxs-lookup"><span data-stu-id="28dc2-110">Microsoft BitLocker Administration And Monitoring Management Pack</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=258390)

## <span data-ttu-id="28dc2-111">确保 MBAM 1.0 的高可用性</span><span class="sxs-lookup"><span data-stu-id="28dc2-111">Ensure high availability for MBAM 1.0</span></span>


<span data-ttu-id="28dc2-112">MBAM 设计为具有容错能力。</span><span class="sxs-lookup"><span data-stu-id="28dc2-112">MBAM is designed to be fault-tolerant.</span></span> <span data-ttu-id="28dc2-113">如果服务器不可用，则用户不会受到负面影响。</span><span class="sxs-lookup"><span data-stu-id="28dc2-113">If a server becomes unavailable, the users should not be negatively affected.</span></span> <span data-ttu-id="28dc2-114">本部分中的信息可用于配置高可用的 MBAM 安装。</span><span class="sxs-lookup"><span data-stu-id="28dc2-114">The information in this section can be used to configure a highly available MBAM installation.</span></span>

[<span data-ttu-id="28dc2-115">MBAM 1.0 的高可用性</span><span class="sxs-lookup"><span data-stu-id="28dc2-115">High Availability for MBAM 1.0</span></span>](high-availability-for-mbam-10.md)

## <span data-ttu-id="28dc2-116">将 MBAM 1.0 功能移动到另一台服务器</span><span class="sxs-lookup"><span data-stu-id="28dc2-116">Move MBAM 1.0 features to another server</span></span>


<span data-ttu-id="28dc2-117">当需要将 MBAM 服务器功能从一台服务器计算机移动到另一台服务器时，应遵循特定的顺序和所需的步骤，以避免生产效率或数据丢失。</span><span class="sxs-lookup"><span data-stu-id="28dc2-117">When you need to move an MBAM Server feature from one server computer to another, there is a specific order and required steps that you should follow to avoid loss of productivity or data.</span></span> <span data-ttu-id="28dc2-118">本节介绍将一个或多个 MBAM 服务器功能移动到另一台计算机时应采取的步骤。</span><span class="sxs-lookup"><span data-stu-id="28dc2-118">This section describes the steps that you should take to move one or more MBAM Server features to a different computer.</span></span>

[<span data-ttu-id="28dc2-119">如何将 MBAM 1.0 功能移到另一台计算机</span><span class="sxs-lookup"><span data-stu-id="28dc2-119">How to Move MBAM 1.0 Features to Another Computer</span></span>](how-to-move-mbam-10-features-to-another-computer.md)

## <span data-ttu-id="28dc2-120">用于维护 MBAM 的其他资源</span><span class="sxs-lookup"><span data-stu-id="28dc2-120">Other resources for maintaining MBAM</span></span>


[<span data-ttu-id="28dc2-121">MBAM 1.0 的操作</span><span class="sxs-lookup"><span data-stu-id="28dc2-121">Operations for MBAM 1.0</span></span>](operations-for-mbam-10.md)

 

 





