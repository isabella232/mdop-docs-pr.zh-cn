---
title: 如何管理 MBAM 管理员角色
description: 如何管理 MBAM 管理员角色
author: dansimp
ms.assetid: 813ac0c4-3cf9-47af-b4cb-9395fd915e5c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 14e9128904b448b20e0596a2630627b7ca8e711d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803704"
---
# <span data-ttu-id="fc714-103">如何管理 MBAM 管理员角色</span><span class="sxs-lookup"><span data-stu-id="fc714-103">How to Manage MBAM Administrator Roles</span></span>


<span data-ttu-id="fc714-104">在 Microsoft BitLocker 管理和监视（MBAM）安装完成所有服务器功能后，系统将必须授予管理员用户访问权限。</span><span class="sxs-lookup"><span data-stu-id="fc714-104">After Microsoft BitLocker Administration and Monitoring (MBAM) Setup is complete for all server features, administrative users will have to be granted access to them.</span></span> <span data-ttu-id="fc714-105">最佳做法是将管理或使用 Microsoft BitLocker 管理和监视服务器功能的管理员分配给域服务安全组，然后应将这些组添加到相应的 MBAM 管理本地组。</span><span class="sxs-lookup"><span data-stu-id="fc714-105">As a best practice, administrators who will manage or use Microsoft BitLocker Administration and Monitoring Server features should be assigned to Domain Services security groups, and then those groups should be added to the appropriate MBAM administrative local group.</span></span>

**<span data-ttu-id="fc714-106">管理 MBAM 管理员角色成员身份</span><span class="sxs-lookup"><span data-stu-id="fc714-106">To manage MBAM Administrator Role memberships</span></span>**

1.  <span data-ttu-id="fc714-107">将管理用户分配到 ActiveDirectory 域服务中的安全组。</span><span class="sxs-lookup"><span data-stu-id="fc714-107">Assign administrative users to security groups in ActiveDirectory Domain Services.</span></span>

2.  <span data-ttu-id="fc714-108">将 ActiveDirectory 安全组添加到 MBAM 服务器上 MBAM 管理本地组的角色，以获得各自的功能。</span><span class="sxs-lookup"><span data-stu-id="fc714-108">Add ActiveDirectory security groups to the roles for MBAM administrative local groups on the MBAM server for the respective features.</span></span>

    -   <span data-ttu-id="fc714-109">**MBAM System 管理员**有权访问 MBAM 管理和监控网站中的所有 MBAM 功能。</span><span class="sxs-lookup"><span data-stu-id="fc714-109">**MBAM System Administrators** have access to all MBAM features in the MBAM Administration and Monitoring website.</span></span>

    -   <span data-ttu-id="fc714-110">**MBAM 帮助台用户**有权访问 MBAM 管理和监视网站中的 "管理 TPM" 和 "驱动器恢复" 选项，但在使用其中一个选项时，必须填写所有字段。</span><span class="sxs-lookup"><span data-stu-id="fc714-110">**MBAM Helpdesk Users** have access to the Manage TPM and Drive Recovery options in the MBAM Administration and Monitoring website, but must fill in all fields when they use either option.</span></span>

    -   <span data-ttu-id="fc714-111">**MBAM 报表用户**有权访问 MBAM 管理和监视网站中的合规性和审核报告。</span><span class="sxs-lookup"><span data-stu-id="fc714-111">**MBAM Report Users** have access to the Compliance and Audit reports in the MBAM Administration and Monitoring website.</span></span>

    -   <span data-ttu-id="fc714-112">**MBAM 高级帮助台用户**可以访问 MBAM 管理和监视网站中的 "管理 TPM" 和 "驱动器恢复" 选项，但不需要在使用任一选项时填写所有字段。</span><span class="sxs-lookup"><span data-stu-id="fc714-112">**MBAM Advanced Helpdesk Users** have access to the Manage TPM and Drive Recovery options in the MBAM Administration and Monitoring website, but are not required to fill in all fields when they use either option.</span></span>

    <span data-ttu-id="fc714-113">有关 Microsoft BitLocker 管理和监视角色的详细信息，请参阅[规划 MBAM 2.0 管理员角色](planning-for-mbam-20-administrator-roles-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="fc714-113">For more information about roles for Microsoft BitLocker Administration and Monitoring, see [Planning for MBAM 2.0 Administrator Roles](planning-for-mbam-20-administrator-roles-mbam-2.md).</span></span>

## <span data-ttu-id="fc714-114">相关主题</span><span class="sxs-lookup"><span data-stu-id="fc714-114">Related topics</span></span>


[<span data-ttu-id="fc714-115">管理 MBAM 2.0 功能</span><span class="sxs-lookup"><span data-stu-id="fc714-115">Administering MBAM 2.0 Features</span></span>](administering-mbam-20-features-mbam-2.md)

 

 





