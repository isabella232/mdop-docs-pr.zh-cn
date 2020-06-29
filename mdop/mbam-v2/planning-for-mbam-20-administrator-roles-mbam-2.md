---
title: 计划 MBAM 2.0 管理员角色
description: 计划 MBAM 2.0 管理员角色
author: dansimp
ms.assetid: 6f813297-6479-42d3-a21b-896d54466b5b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a89a04c0ef074407dc3cd081d351d44023e65e70
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803659"
---
# <span data-ttu-id="7dc46-103">计划 MBAM 2.0 管理员角色</span><span class="sxs-lookup"><span data-stu-id="7dc46-103">Planning for MBAM 2.0 Administrator Roles</span></span>


<span data-ttu-id="7dc46-104">本主题列出并介绍 Microsoft BitLocker 管理和监视（MBAM）中可用的可用管理员角色以及创建本地组的服务器位置。</span><span class="sxs-lookup"><span data-stu-id="7dc46-104">This topic lists and describes the available administrator roles that are available in Microsoft BitLocker Administration and Monitoring (MBAM) as well as the server locations where the local groups are created.</span></span>

## <span data-ttu-id="7dc46-105">MBAM 管理员角色</span><span class="sxs-lookup"><span data-stu-id="7dc46-105">MBAM Administrator Roles</span></span>


<a href="" id="---------------mbam-system-administrators"></a> **<span data-ttu-id="7dc46-106">MBAM 系统管理员</span><span class="sxs-lookup"><span data-stu-id="7dc46-106">MBAM System Administrators</span></span>**  
<span data-ttu-id="7dc46-107">此角色中的管理员有权访问所有 Microsoft BitLocker 管理和监视功能。</span><span class="sxs-lookup"><span data-stu-id="7dc46-107">Administrators in this role have access to all Microsoft BitLocker Administration and Monitoring features.</span></span> <span data-ttu-id="7dc46-108">此角色的本地组安装在管理和监视服务器上。</span><span class="sxs-lookup"><span data-stu-id="7dc46-108">The local group for this role is installed on the Administration and Monitoring Server.</span></span>

<a href="" id="---------------mbam-helpdesk-users"></a> **<span data-ttu-id="7dc46-109">MBAM 帮助台用户</span><span class="sxs-lookup"><span data-stu-id="7dc46-109">MBAM Helpdesk Users</span></span>**  
<span data-ttu-id="7dc46-110">此角色中的管理员可以访问 MBAM 中的技术支持功能。</span><span class="sxs-lookup"><span data-stu-id="7dc46-110">Administrators in this role have access to the Help Desk features from MBAM.</span></span> <span data-ttu-id="7dc46-111">此角色的本地组安装在管理和监视服务器上。</span><span class="sxs-lookup"><span data-stu-id="7dc46-111">The local group for this role is installed on the Administration and Monitoring Server.</span></span>

<a href="" id="---------------mbam-report-users"></a> **<span data-ttu-id="7dc46-112">MBAM 报表用户</span><span class="sxs-lookup"><span data-stu-id="7dc46-112">MBAM Report Users</span></span>**  
<span data-ttu-id="7dc46-113">此角色中的管理员可以访问 MBAM 中的合规性和审核报告。</span><span class="sxs-lookup"><span data-stu-id="7dc46-113">Administrators in this role have access to the Compliance and Audit Reports from MBAM.</span></span> <span data-ttu-id="7dc46-114">此角色的本地组安装在管理和监视服务器、合规性和审核数据库以及托管合规性和审核报告的服务器上。</span><span class="sxs-lookup"><span data-stu-id="7dc46-114">The local group for this role is installed on the Administration and Monitoring Server, Compliance and Audit Database, and on the server that hosts the Compliance and Audit Reports.</span></span>

<a href="" id="---------------mbam-advanced-helpdesk-users"></a> **<span data-ttu-id="7dc46-115">MBAM 高级帮助台用户</span><span class="sxs-lookup"><span data-stu-id="7dc46-115">MBAM Advanced Helpdesk Users</span></span>**  
<span data-ttu-id="7dc46-116">此角色中的管理员已增加了对 MBAM 中技术支持功能的访问权限。</span><span class="sxs-lookup"><span data-stu-id="7dc46-116">Administrators in this role have increased access to the Help Desk features from MBAM.</span></span> <span data-ttu-id="7dc46-117">此角色的本地组安装在管理和监视服务器上。</span><span class="sxs-lookup"><span data-stu-id="7dc46-117">The local group for this role is installed on the Administration and Monitoring Server.</span></span> <span data-ttu-id="7dc46-118">如果用户是 MBAM 帮助台用户和 MBAM 高级帮助台用户的成员，则 MBAM 高级帮助台用户权限将替代 MBAM 帮助台用户权限。</span><span class="sxs-lookup"><span data-stu-id="7dc46-118">If a user is a member of both MBAM Helpdesk Users and MBAM Advanced Helpdesk Users, the MBAM Advanced Helpdesk Users permissions will override the MBAM Helpdesk User permissions.</span></span>

<span data-ttu-id="7dc46-119">**重要提示** 若要查看报表，管理用户必须是管理和监视服务器、合规性和审核数据库以及托管合规性和审核报告功能的服务器上的**MBAM Report Users**安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="7dc46-119">**Important** To view reports, an administrative user must be a member of the **MBAM Report Users** security group on the Administration and Monitoring Server, Compliance and Audit Database, and on the server that hosts the Compliance and Audit Reports feature.</span></span> <span data-ttu-id="7dc46-120">最佳做法是在 Active Directory 域服务中使用本地**MBAM 报表**上的权限在管理和监视服务器以及托管合规性和审核报表的服务器上创建安全组。</span><span class="sxs-lookup"><span data-stu-id="7dc46-120">As a best practice, create a security group in Active Directory Domain Services with rights on the local **MBAM Report Users** security group on both the Administration and Monitoring Server and the server that hosts the Compliance and Audit Reports.</span></span>

 

## <span data-ttu-id="7dc46-121">相关主题</span><span class="sxs-lookup"><span data-stu-id="7dc46-121">Related topics</span></span>


[<span data-ttu-id="7dc46-122">针对 MBAM 2.0 准备环境</span><span class="sxs-lookup"><span data-stu-id="7dc46-122">Preparing your Environment for MBAM 2.0</span></span>](preparing-your-environment-for-mbam-20-mbam-2.md)

 

 





