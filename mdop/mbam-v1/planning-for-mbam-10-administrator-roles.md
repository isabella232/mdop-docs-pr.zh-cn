---
title: 计划 MBAM 1.0 管理员角色
description: 计划 MBAM 1.0 管理员角色
author: dansimp
ms.assetid: 95be0eb4-25e9-43ca-a8e7-27373d35544d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 104d650824330ea990881c520a7811511f496dd1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803858"
---
# <span data-ttu-id="c3a06-103">计划 MBAM 1.0 管理员角色</span><span class="sxs-lookup"><span data-stu-id="c3a06-103">Planning for MBAM 1.0 Administrator Roles</span></span>


<span data-ttu-id="c3a06-104">本主题包括和介绍 Microsoft BitLocker 管理和监视（MBAM）中提供的管理员角色，以及创建本地组的服务器位置。</span><span class="sxs-lookup"><span data-stu-id="c3a06-104">This topic includes and describes the administrator roles that are available in Microsoft BitLocker Administration and Monitoring (MBAM), as well as the server locations where the local groups are created.</span></span>

## <span data-ttu-id="c3a06-105">MBAM 管理员角色</span><span class="sxs-lookup"><span data-stu-id="c3a06-105">MBAM Administrator roles</span></span>


<a href="" id="---------------mbam-system-administrators"></a> **<span data-ttu-id="c3a06-106">MBAM 系统管理员</span><span class="sxs-lookup"><span data-stu-id="c3a06-106">MBAM System Administrators</span></span>**  
<span data-ttu-id="c3a06-107">此角色中的管理员有权访问所有 MBAM 功能。</span><span class="sxs-lookup"><span data-stu-id="c3a06-107">Administrators in this role have access to all MBAM features.</span></span> <span data-ttu-id="c3a06-108">此角色的本地组安装在管理和监视服务器上。</span><span class="sxs-lookup"><span data-stu-id="c3a06-108">The local group for this role is installed on the Administration and Monitoring Server.</span></span>

<a href="" id="---------------mbam-hardware-users"></a> **<span data-ttu-id="c3a06-109">MBAM 硬件用户</span><span class="sxs-lookup"><span data-stu-id="c3a06-109">MBAM Hardware Users</span></span>**  
<span data-ttu-id="c3a06-110">此角色中的管理员可以访问 MBAM 中的硬件功能功能。</span><span class="sxs-lookup"><span data-stu-id="c3a06-110">Administrators in this role have access to the Hardware Capability features from MBAM.</span></span> <span data-ttu-id="c3a06-111">此角色的本地组安装在管理和监视服务器上。</span><span class="sxs-lookup"><span data-stu-id="c3a06-111">The local group for this role is installed on the Administration and Monitoring Server.</span></span>

<a href="" id="---------------mbam-helpdesk-users"></a> **<span data-ttu-id="c3a06-112">MBAM 帮助台用户</span><span class="sxs-lookup"><span data-stu-id="c3a06-112">MBAM Helpdesk Users</span></span>**  
<span data-ttu-id="c3a06-113">此角色中的管理员可以访问 MBAM 中的帮助台功能。</span><span class="sxs-lookup"><span data-stu-id="c3a06-113">Administrators in this role have access to the Helpdesk features from MBAM.</span></span> <span data-ttu-id="c3a06-114">此角色的本地组安装在管理和监视服务器上。</span><span class="sxs-lookup"><span data-stu-id="c3a06-114">The local group for this role is installed on the Administration and Monitoring Server.</span></span>

<a href="" id="---------------mbam--report-users"></a> **<span data-ttu-id="c3a06-115">MBAM 报表用户</span><span class="sxs-lookup"><span data-stu-id="c3a06-115">MBAM Report Users</span></span>**  
<span data-ttu-id="c3a06-116">此角色中的管理员可以访问 MBAM 中的合规性和审核报告功能。</span><span class="sxs-lookup"><span data-stu-id="c3a06-116">Administrators in this role have access to the Compliance and Audit Reports feature from MBAM.</span></span> <span data-ttu-id="c3a06-117">此角色的本地组安装在管理和监视服务器、合规性和审核数据库以及托管合规性和审核报告的服务器上。</span><span class="sxs-lookup"><span data-stu-id="c3a06-117">The local group for this role is installed on the Administration and Monitoring Server, Compliance and Audit Database, and on the server that hosts the Compliance and Audit Reports.</span></span>

<a href="" id="---------------mbam--advanced-helpdesk-users"></a> **<span data-ttu-id="c3a06-118">MBAM 高级帮助台用户</span><span class="sxs-lookup"><span data-stu-id="c3a06-118">MBAM Advanced Helpdesk Users</span></span>**  
<span data-ttu-id="c3a06-119">此角色的管理员已增加了对 MBAM 中的帮助台功能的访问权限。</span><span class="sxs-lookup"><span data-stu-id="c3a06-119">Administrators in this role have increased access to the Helpdesk features from MBAM.</span></span> <span data-ttu-id="c3a06-120">此角色的本地组安装在管理和监视服务器上。</span><span class="sxs-lookup"><span data-stu-id="c3a06-120">The local group for this role is installed on the Administration and Monitoring Server.</span></span> <span data-ttu-id="c3a06-121">如果用户是 MBAM 帮助台用户和 MBAM 高级帮助台用户的成员，则 MBAM 高级帮助台用户权限将覆盖 MBAM 帮助台用户权限。</span><span class="sxs-lookup"><span data-stu-id="c3a06-121">If a user is a member of both MBAM Helpdesk Users and MBAM Advanced Helpdesk Users, the MBAM Advanced Helpdesk Users permissions will overwrite the MBAM Helpdesk User permissions.</span></span>

<span data-ttu-id="c3a06-122">**重要提示** 若要查看报表，管理用户必须是管理和监视服务器、合规性和审核数据库以及托管合规性和报告功能的服务器上的**MBAM Report Users**安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="c3a06-122">**Important** To view the reports, an administrative user must be a member of the **MBAM Report Users** security group on the Administration and Monitoring Server, Compliance and Audit Database, and on the server that hosts the Compliance and Reports feature.</span></span> <span data-ttu-id="c3a06-123">最佳做法是在 Active Directory 中创建一个安全组，其中包含管理和监视服务器以及托管合规性和报告的服务器上的本地**MBAM 报表用户**安全组的权限。</span><span class="sxs-lookup"><span data-stu-id="c3a06-123">As a best practice, create a security group in Active Directory with rights on the local **MBAM Report Users** security group on both the Administration and Monitoring Server and on the server that hosts the Compliance and Reports.</span></span>

 

## <span data-ttu-id="c3a06-124">相关主题</span><span class="sxs-lookup"><span data-stu-id="c3a06-124">Related topics</span></span>


[<span data-ttu-id="c3a06-125">针对 MBAM 1.0 准备环境</span><span class="sxs-lookup"><span data-stu-id="c3a06-125">Preparing your Environment for MBAM 1.0</span></span>](preparing-your-environment-for-mbam-10.md)

 

 





