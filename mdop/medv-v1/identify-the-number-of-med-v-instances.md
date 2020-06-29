---
title: 确定 MED-V 实例数
description: 确定 MED-V 实例数
author: dansimp
ms.assetid: edea9bdf-a28c-4d24-9298-7bd6536c3a94
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 22f7d54318d2dc489461474e5531c5162d8c087d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803532"
---
# <span data-ttu-id="8c2a8-103">确定 MED-V 实例数</span><span class="sxs-lookup"><span data-stu-id="8c2a8-103">Identify the Number of MED-V Instances</span></span>


<span data-ttu-id="8c2a8-104">你需要确定 MED-V 实例的数量，并为每个实例定义范围，以便你可以设计服务器基础结构。</span><span class="sxs-lookup"><span data-stu-id="8c2a8-104">You need to determine the number of MED-V instances, as well as define the scope for each instance so that you can design the server infrastructure.</span></span> <span data-ttu-id="8c2a8-105">MED-V 实例包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="8c2a8-105">A MED-V instance includes the following:</span></span>

-   <span data-ttu-id="8c2a8-106">在服务器上存储的 MED-V 服务器和 MED-V 工作区（包括 Active Directory 权限）。</span><span class="sxs-lookup"><span data-stu-id="8c2a8-106">The MED-V server and the MED-V workspaces stored on the server, including Active Directory permissions.</span></span>

-   <span data-ttu-id="8c2a8-107">存储客户端事件的 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="8c2a8-107">A SQL Server database that stores client events.</span></span> <span data-ttu-id="8c2a8-108">数据库可以由多个 MED-V 实例共享。</span><span class="sxs-lookup"><span data-stu-id="8c2a8-108">The database may be shared by multiple MED-V instances.</span></span>

-   <span data-ttu-id="8c2a8-109">打包的 MED-V 映像的图像存储库。</span><span class="sxs-lookup"><span data-stu-id="8c2a8-109">The image repository for the packed MED-V images.</span></span> <span data-ttu-id="8c2a8-110">存储库可以由多个 MED-V 实例共享。</span><span class="sxs-lookup"><span data-stu-id="8c2a8-110">The repository may be shared by multiple MED-V instances.</span></span>

-   <span data-ttu-id="8c2a8-111">用于创建和打包映像以及创建 MED-V 工作区的管理控制台。</span><span class="sxs-lookup"><span data-stu-id="8c2a8-111">The management console used to create and pack images and to create MED-V workspaces.</span></span> <span data-ttu-id="8c2a8-112">该控制台不能同时由多个 MED-V 实例使用，但可以从一个 MED-V 服务器断开连接，然后连接到其他 MED-V 服务器。</span><span class="sxs-lookup"><span data-stu-id="8c2a8-112">The console cannot be used simultaneously by multiple MED-V instances, but it can be disconnected from one MED-V server and then connected to a different MED-V server.</span></span>

-   <span data-ttu-id="8c2a8-113">从服务器接收 MED-V 工作区以及授权使用的 MED-V 客户端。</span><span class="sxs-lookup"><span data-stu-id="8c2a8-113">MED-V clients that receive MED-V workspaces, and authorization to use them, from the server.</span></span>

<span data-ttu-id="8c2a8-114">单独的 MED-V 实例不能集成或共享 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="8c2a8-114">Separate MED-V instances cannot be integrated or share MED-V workspaces.</span></span> <span data-ttu-id="8c2a8-115">因此，每个额外实例 decentralizes 虚拟化管理。</span><span class="sxs-lookup"><span data-stu-id="8c2a8-115">Therefore, each additional instance decentralizes the virtualization management.</span></span>

## <span data-ttu-id="8c2a8-116">确定所需的 MED-V 实例数</span><span class="sxs-lookup"><span data-stu-id="8c2a8-116">Determine the Number of MED-V Instances Required</span></span>


<span data-ttu-id="8c2a8-117">首先假设你使用的是一个 MED-V 实例。</span><span class="sxs-lookup"><span data-stu-id="8c2a8-117">Start by assuming you are using one MED-V instance.</span></span> <span data-ttu-id="8c2a8-118">然后，考虑以下条件，并为适用于基础结构的每个条件添加其他实例。</span><span class="sxs-lookup"><span data-stu-id="8c2a8-118">Then, consider the following conditions, and add additional instances for each condition that applies to your infrastructure.</span></span>

-   <span data-ttu-id="8c2a8-119">支持的用户数-每个 MED-V 实例最多可支持5000个并发活动客户端。</span><span class="sxs-lookup"><span data-stu-id="8c2a8-119">Number of supported users—Each MED-V instance can support up to 5,000 concurrently active clients.</span></span> <span data-ttu-id="8c2a8-120">并发活动意味着客户端与 MED-V 服务器在线，并向服务器发送对策略和映像更新以及事件的轮询。</span><span class="sxs-lookup"><span data-stu-id="8c2a8-120">Concurrently active means the client is online with the MED-V server and sending polls to the server for policy and image updates, as well as events.</span></span> <span data-ttu-id="8c2a8-121">如果你的基础结构包含的活动用户超过5000个，请为每个5000用户添加一个实例。</span><span class="sxs-lookup"><span data-stu-id="8c2a8-121">If your infrastructure will include more than 5,000 active users, add one instance for every 5,000 users.</span></span>

-   <span data-ttu-id="8c2a8-122">不受信任域中的用户-MED-V 服务器将 MED-V 工作区权限与 Active Directory 用户和/或组关联。</span><span class="sxs-lookup"><span data-stu-id="8c2a8-122">Users in untrusted domains—The MED-V server associates MED-V workspace permissions with Active Directory users and/or groups.</span></span> <span data-ttu-id="8c2a8-123">这要求 med-v 服务器的信任边界内存在 med-v 用户。</span><span class="sxs-lookup"><span data-stu-id="8c2a8-123">This requires MED-V users to exist within the trust boundary of the MED-V server.</span></span> <span data-ttu-id="8c2a8-124">为位于单独的不受信任域中的每组 MED-V 用户添加一个 MED-V 实例。</span><span class="sxs-lookup"><span data-stu-id="8c2a8-124">Add one MED-V instance for each group of MED-V users that is in a separate, untrusted domain.</span></span>

-   <span data-ttu-id="8c2a8-125">独立网络中的客户端-确定任何客户端是否驻留在已隔离的网络中，因此需要单独的 MED-V 实例。</span><span class="sxs-lookup"><span data-stu-id="8c2a8-125">Clients in isolated networks—Determine whether any clients reside in networks that are isolated and therefore require a separate MED-V instance.</span></span> <span data-ttu-id="8c2a8-126">例如，组织通常将实验室网络与生产网络隔离。</span><span class="sxs-lookup"><span data-stu-id="8c2a8-126">For example, organizations often isolate lab networks from production networks.</span></span> <span data-ttu-id="8c2a8-127">为将包含 MED-V 客户端的每个隔离网络添加 MED-V 实例。</span><span class="sxs-lookup"><span data-stu-id="8c2a8-127">Add a MED-V instance for each isolated network that will contain MED-V clients.</span></span>

-   <span data-ttu-id="8c2a8-128">组织要求-组织可能需要由单独的 MED-V 实例管理一组客户端，出于安全考虑，例如，当敏感应用程序仅向域中的一组受限用户传递时。</span><span class="sxs-lookup"><span data-stu-id="8c2a8-128">Organizational requirements—The organization may require that a group of clients be managed by a separate MED-V instance for security reasons, such as when sensitive applications are delivered only to a restricted set of users within a domain.</span></span> <span data-ttu-id="8c2a8-129">例如，工资部门可能拒绝其他部门的用户访问存储用于工资处理策略的 MED-V 实例。</span><span class="sxs-lookup"><span data-stu-id="8c2a8-129">For example, the payroll department may deny users from other departments access to the MED-V instance that stores policy for payroll processing.</span></span> <span data-ttu-id="8c2a8-130">此外，如果组织使用分布式管理模型，则对于拥有 MED-V 客户端的每个业务组，可能需要一个单独的 MED-V 实例，以使该组能够管理其自己的虚拟化环境。</span><span class="sxs-lookup"><span data-stu-id="8c2a8-130">Additionally, if the organization uses a distributed management model, a separate MED-V instance may be required for each business group having MED-V clients in order to enable the group to manage its own virtualized environment.</span></span> <span data-ttu-id="8c2a8-131">为每个单独的组织要求添加一个 MED-V 实例。</span><span class="sxs-lookup"><span data-stu-id="8c2a8-131">Add one MED-V instance for each separate organizational requirement.</span></span>

-   <span data-ttu-id="8c2a8-132">法律考虑-国内安全或隐私问题和 fiduciary 法律可能需要分离某些数据或防止其他数据跨越全国边框。</span><span class="sxs-lookup"><span data-stu-id="8c2a8-132">Legal considerations—National security or privacy issues and fiduciary laws could require the separation of certain data or prevent other data from crossing national borders.</span></span> <span data-ttu-id="8c2a8-133">如有必要，请添加其他 MED-V 实例以满足此需求。</span><span class="sxs-lookup"><span data-stu-id="8c2a8-133">If necessary, add additional MED-V instances to address this need.</span></span>

<span data-ttu-id="8c2a8-134">确定你的基础结构所需的 MED-V 实例数以及每个实例的推理后，请为每个实例提供一个名称。</span><span class="sxs-lookup"><span data-stu-id="8c2a8-134">After you determine the number of MED-V instances required for your infrastructure, as well as the reasoning for each one, provide a name for each instance.</span></span>

 

 





