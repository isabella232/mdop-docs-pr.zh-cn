---
title: 如何管理 MBAM 管理员角色
description: 如何管理 MBAM 管理员角色
author: dansimp
ms.assetid: c0f25a42-dbff-418d-a776-4fe23ee07d16
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9d00b8ebf66d2b066afae33e67298691285ce9fa
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798178"
---
# <span data-ttu-id="8993b-103">如何管理 MBAM 管理员角色</span><span class="sxs-lookup"><span data-stu-id="8993b-103">How to Manage MBAM Administrator Roles</span></span>


<span data-ttu-id="8993b-104">完成所有服务器功能的 Microsoft BitLocker 管理和监视（MBAM）设置后，必须授予管理员用户访问这些服务器功能的权限。</span><span class="sxs-lookup"><span data-stu-id="8993b-104">After Microsoft BitLocker Administration and Monitoring (MBAM) Setup is complete for all server features, administrative users must be granted access to these server features.</span></span> <span data-ttu-id="8993b-105">最佳做法是管理或使用 MBAM 服务器功能的管理员应分配给 Active Directory 安全组，然后应将这些组添加到相应的 MBAM 管理本地组。</span><span class="sxs-lookup"><span data-stu-id="8993b-105">As a best practice, administrators who will manage or use MBAM server features, should be assigned to Active Directory security groups and then those groups should be added to the appropriate MBAM administrative local group.</span></span>

**<span data-ttu-id="8993b-106">管理 MBAM 管理员角色成员身份</span><span class="sxs-lookup"><span data-stu-id="8993b-106">To manage MBAM Administrator Role memberships</span></span>**

1.  <span data-ttu-id="8993b-107">向 ActiveDirectoryDomain Services 中的安全组分配管理用户。</span><span class="sxs-lookup"><span data-stu-id="8993b-107">Assign administrative users to security groups in ActiveDirectoryDomain Services.</span></span>

2.  <span data-ttu-id="8993b-108">将 ActiveDirectoryDomain Services 安全组添加到 Microsoft BitLocker 管理和监视服务器上 MBAM 管理本地组的角色，以供各自的功能。</span><span class="sxs-lookup"><span data-stu-id="8993b-108">Add ActiveDirectoryDomain Services security groups to the roles for MBAM administrative local groups on the Microsoft BitLocker Administration and Monitoring server for the respective features.</span></span> <span data-ttu-id="8993b-109">用户角色如下所示：</span><span class="sxs-lookup"><span data-stu-id="8993b-109">The user roles are as follows:</span></span>

    -   <span data-ttu-id="8993b-110">**MBAM System 管理员**有权访问 MBAM 管理网站中的所有 Microsoft BitLocker 管理和监视功能。</span><span class="sxs-lookup"><span data-stu-id="8993b-110">**MBAM System Administrators** have access to all Microsoft BitLocker Administration and Monitoring features in the MBAM administration website.</span></span>

    -   <span data-ttu-id="8993b-111">**MBAM 硬件用户**有权访问 MBAM 管理网站中的硬件兼容性功能。</span><span class="sxs-lookup"><span data-stu-id="8993b-111">**MBAM Hardware Users** have access to the Hardware Compatibility features in the MBAM administration website.</span></span>

    -   <span data-ttu-id="8993b-112">**MBAM 帮助台用户**有权访问 MBAM 管理网站中的 "管理 TPM" 和 "驱动器恢复" 选项，但在使用其中一个选项时，必须填写所有字段。</span><span class="sxs-lookup"><span data-stu-id="8993b-112">**MBAM Helpdesk Users** have access to the Manage TPM and Drive Recovery options in the MBAM administration website, but must fill in all fields when they use either option.</span></span>

    -   <span data-ttu-id="8993b-113">**MBAM 报表用户**有权访问 MBAM 管理网站中的合规性和审核报告。</span><span class="sxs-lookup"><span data-stu-id="8993b-113">**MBAM Report Users** have access to the Compliance and Audit reports in the MBAM administration website.</span></span>

    -   <span data-ttu-id="8993b-114">**MBAM 高级帮助台使用**有权访问 MBAM 管理网站中的 "管理 TPM" 和 "驱动器恢复" 选项。</span><span class="sxs-lookup"><span data-stu-id="8993b-114">**MBAM Advanced Helpdesk Uses** have access to the Manage TPM and Drive Recovery options in the MBAM administration website.</span></span> <span data-ttu-id="8993b-115">当这些用户使用任一选项时，不需要填写所有字段。</span><span class="sxs-lookup"><span data-stu-id="8993b-115">These users are not required to fill in all fields when they use either option.</span></span>

    <span data-ttu-id="8993b-116">有关 Microsoft BitLocker 管理和监视角色的详细信息，请参阅[规划 MBAM 1.0 管理员角色](planning-for-mbam-10-administrator-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="8993b-116">For more information about roles for Microsoft BitLocker Administration and Monitoring, see [Planning for MBAM 1.0 Administrator Roles](planning-for-mbam-10-administrator-roles.md).</span></span>

## <span data-ttu-id="8993b-117">相关主题</span><span class="sxs-lookup"><span data-stu-id="8993b-117">Related topics</span></span>


[<span data-ttu-id="8993b-118">管理 MBAM 1.0 功能</span><span class="sxs-lookup"><span data-stu-id="8993b-118">Administering MBAM 1.0 Features</span></span>](administering-mbam-10-features.md)

 

 





