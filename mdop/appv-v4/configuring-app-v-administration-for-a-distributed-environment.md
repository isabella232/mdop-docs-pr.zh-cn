---
title: 针对分布式环境配置 App-V 管理
description: 针对分布式环境配置 App-V 管理
author: dansimp
ms.assetid: 53971fa9-8319-435c-be74-c37feb9af1da
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: c1a638d6afde9270859c8aa98fc9f421c39cfc72
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803063"
---
# <span data-ttu-id="fd43c-103">针对分布式环境配置 App-V 管理</span><span class="sxs-lookup"><span data-stu-id="fd43c-103">Configuring App-V Administration for a Distributed Environment</span></span>


<span data-ttu-id="fd43c-104">为特定组织设计基础结构时，可以在安装了 app-v 管理服务器的计算机以外的计算机上安装 app-v 管理 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="fd43c-104">When designing the infrastructure for your specific organization, you can install the App-V Management Web Service on a computer other than the computer where you install the App-V Management Server.</span></span> <span data-ttu-id="fd43c-105">分离这些 App-v 组件的常见原因包括以下几项：</span><span class="sxs-lookup"><span data-stu-id="fd43c-105">Common reasons for separating these App-V components include the following:</span></span>

-   <span data-ttu-id="fd43c-106">性能</span><span class="sxs-lookup"><span data-stu-id="fd43c-106">Performance</span></span>

-   <span data-ttu-id="fd43c-107">可靠性</span><span class="sxs-lookup"><span data-stu-id="fd43c-107">Reliability</span></span>

-   <span data-ttu-id="fd43c-108">可用性</span><span class="sxs-lookup"><span data-stu-id="fd43c-108">Availability</span></span>

-   <span data-ttu-id="fd43c-109">可伸缩性</span><span class="sxs-lookup"><span data-stu-id="fd43c-109">Scalability</span></span>

<span data-ttu-id="fd43c-110">通过分离管理服务器和管理 Web 服务，需要额外配置基础结构才能正常运行。</span><span class="sxs-lookup"><span data-stu-id="fd43c-110">Separating the Management Server and Management Web Service requires additional configuration for the infrastructure to operate correctly.</span></span> <span data-ttu-id="fd43c-111">当你分离这两个功能，但未完成本主题中所述的过程时，管理控制台将连接到管理 Web 服务，但无法通过数据存储正确验证。</span><span class="sxs-lookup"><span data-stu-id="fd43c-111">When you separate these two features but do not complete the procedures described in this topic, the Management Console will connect to the Management Web Service but will not be able to properly authenticate with the data store.</span></span> <span data-ttu-id="fd43c-112">管理控制台将无法正常加载，管理员将无法完成任何管理任务。</span><span class="sxs-lookup"><span data-stu-id="fd43c-112">The Management Console will not load properly, and the administrator will not be able to complete any administrative tasks.</span></span>

<span data-ttu-id="fd43c-113">之所以会出现此行为，是因为管理 Web 服务无法使用从管理控制台传递给它的凭据来访问数据存储。</span><span class="sxs-lookup"><span data-stu-id="fd43c-113">This behavior occurs because the Management Web Service cannot use the credentials, passed to it from the Management Console, to access the data store.</span></span> <span data-ttu-id="fd43c-114">解决方案是将管理 Web 服务服务器配置为 "受信任以供委派"。</span><span class="sxs-lookup"><span data-stu-id="fd43c-114">The solution is to configure the Management Web Service server to be “Trusted for delegation.”</span></span>

## <span data-ttu-id="fd43c-115">配置 Active Directory 域服务</span><span class="sxs-lookup"><span data-stu-id="fd43c-115">Configuring Active Directory Domain Services</span></span>


<span data-ttu-id="fd43c-116">还需要配置正确的 Active Directory 域服务才能在分布式环境中工作。</span><span class="sxs-lookup"><span data-stu-id="fd43c-116">It is also necessary to configure Active Directory Domain Services properly to work in a distributed environment.</span></span> <span data-ttu-id="fd43c-117">本部分包含你需要配置 Active Directory 域服务的信息。</span><span class="sxs-lookup"><span data-stu-id="fd43c-117">This section includes the information you need configure Active Directory Domain Services.</span></span>

### <span data-ttu-id="fd43c-118">SQL 服务使用本地系统帐户时</span><span class="sxs-lookup"><span data-stu-id="fd43c-118">When SQL Service Uses Local System account</span></span>

<span data-ttu-id="fd43c-119">若要设置 SQL 服务使用本地系统帐户的环境，请将管理 Web 服务的计算机帐户的属性更改为 "受信任以供委派"。</span><span class="sxs-lookup"><span data-stu-id="fd43c-119">To set up the environment where the SQL Service uses the local system account, change the properties of the machine account of the Management Web Service to be trusted for delegation.</span></span> <span data-ttu-id="fd43c-120">有关如何执行此操作的详细过程，请参阅[如何将服务器配置为受信任的委派](how-to-configure-the-server-to-be-trusted-for-delegation.md)</span><span class="sxs-lookup"><span data-stu-id="fd43c-120">For detailed procedures about how to do this, see [How to Configure the Server to be Trusted for Delegation](how-to-configure-the-server-to-be-trusted-for-delegation.md)</span></span>

### <span data-ttu-id="fd43c-121">SQL 服务使用基于域的帐户时</span><span class="sxs-lookup"><span data-stu-id="fd43c-121">When SQL Service Uses Domain-Based Account</span></span>

<span data-ttu-id="fd43c-122">若要设置 SQL Server 使用基于域的服务帐户的环境，您需要考虑是否应用各种因素，包括：</span><span class="sxs-lookup"><span data-stu-id="fd43c-122">To set up the environment where SQL Servers use domain-based service accounts, you need to consider whether or not a variety of factors apply, including the following:</span></span>

-   <span data-ttu-id="fd43c-123">SQL Server 群集</span><span class="sxs-lookup"><span data-stu-id="fd43c-123">Clustering of SQL Server</span></span>

-   <span data-ttu-id="fd43c-124">复制</span><span class="sxs-lookup"><span data-stu-id="fd43c-124">Replication</span></span>

-   <span data-ttu-id="fd43c-125">自动化任务</span><span class="sxs-lookup"><span data-stu-id="fd43c-125">Automated tasks</span></span>

-   <span data-ttu-id="fd43c-126">链接服务器</span><span class="sxs-lookup"><span data-stu-id="fd43c-126">Linked servers</span></span>

<span data-ttu-id="fd43c-127">有关在 SQL 服务使用基于域的帐户时配置 Active Directory 域服务的信息，请参阅 <https://go.microsoft.com/fwlink/?LinkId=151968> 。</span><span class="sxs-lookup"><span data-stu-id="fd43c-127">For information about configuring Active Directory Domain Services when the SQL service uses a domain-based account, see <https://go.microsoft.com/fwlink/?LinkId=151968>.</span></span>

 

 





