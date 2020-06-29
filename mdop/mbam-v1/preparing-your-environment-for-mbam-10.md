---
title: 针对 MBAM 1.0 准备环境
description: 针对 MBAM 1.0 准备环境
author: dansimp
ms.assetid: 915f7c3c-70ad-4a90-a434-73e7fba97ecb
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9a2de4e825d5c89aeabcf57d78dc856bacb03e11
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803319"
---
# <span data-ttu-id="86b2f-103">针对 MBAM 1.0 准备环境</span><span class="sxs-lookup"><span data-stu-id="86b2f-103">Preparing your Environment for MBAM 1.0</span></span>


<span data-ttu-id="86b2f-104">在开始 Microsoft BitLocker 管理和监视（MBAM）安装之前，请确保满足安装该产品所必需的先决条件。</span><span class="sxs-lookup"><span data-stu-id="86b2f-104">Before you begin the Microsoft BitLocker Administration and Monitoring (MBAM) Setup, make sure that you have met the necessary prerequisites to install the product.</span></span> <span data-ttu-id="86b2f-105">如果事先知道先决条件，则可以有效地部署产品并启用其功能，以便更有效地支持组织的业务目标。</span><span class="sxs-lookup"><span data-stu-id="86b2f-105">If you know the prerequisites in advance, you can efficiently deploy the product and enable its features, which can support the business objectives of your organization more effectively.</span></span>

## <span data-ttu-id="86b2f-106">查看 MBAM 1.0 部署先决条件</span><span class="sxs-lookup"><span data-stu-id="86b2f-106">Review MBAM 1.0 deployment prerequisites</span></span>


<span data-ttu-id="86b2f-107">MBAM 客户端和每个 MBAM 服务器功能都具有特定的先决条件，必须先满足这些先决条件，然后才能成功安装它们。</span><span class="sxs-lookup"><span data-stu-id="86b2f-107">The MBAM Client and each of the MBAM Server features have specific prerequisites that must be met before they can be successfully installed.</span></span>

<span data-ttu-id="86b2f-108">为了确保 MBAM 客户端和 MBAM 服务器功能的安装成功，你应该计划确保为 MBAM 客户端或 MBAM Server 功能安装指定的计算机正确做好 MBAM 设置的准备。</span><span class="sxs-lookup"><span data-stu-id="86b2f-108">To ensure successful installation of MBAM Clients and MBAM Server features, you should plan to ensure that computers specified for MBAM Client or MBAM Server feature installation are properly prepared for MBAM Setup.</span></span>

<span data-ttu-id="86b2f-109">**注意** MBAM 安装程序将在安装开始之前验证是否满足所有先决条件。</span><span class="sxs-lookup"><span data-stu-id="86b2f-109">**Note** MBAM Setup verifies if all prerequisites are met before installation starts.</span></span> <span data-ttu-id="86b2f-110">如果不满足这些要求，安装程序将失败。</span><span class="sxs-lookup"><span data-stu-id="86b2f-110">If they are not met, Setup will fail.</span></span>

 

[<span data-ttu-id="86b2f-111">MBAM 1.0 部署先决条件</span><span class="sxs-lookup"><span data-stu-id="86b2f-111">MBAM 1.0 Deployment Prerequisites</span></span>](mbam-10-deployment-prerequisites.md)

## <span data-ttu-id="86b2f-112">规划 MBAM 1.0 组策略要求</span><span class="sxs-lookup"><span data-stu-id="86b2f-112">Plan for MBAM 1.0 Group Policy requirements</span></span>


<span data-ttu-id="86b2f-113">在 MBAM 可以管理企业中的客户端之前，必须为环境的加密要求定义组策略。</span><span class="sxs-lookup"><span data-stu-id="86b2f-113">Before MBAM can manage clients in the enterprise, you must define the Group Policy for the encryption requirements of your environment.</span></span>

<span data-ttu-id="86b2f-114">**重要提示** MBAM 将不会与独立的 BitLocker 驱动器加密的策略配合使用。</span><span class="sxs-lookup"><span data-stu-id="86b2f-114">**Important** MBAM will not work with policies for stand-alone BitLocker drive encryption.</span></span> <span data-ttu-id="86b2f-115">必须为 MBAM 定义组策略;否则，BitLocker 加密和强制将失败。</span><span class="sxs-lookup"><span data-stu-id="86b2f-115">Group Policy must be defined for MBAM; otherwise, the BitLocker encryption and enforcement will fail.</span></span>

 

[<span data-ttu-id="86b2f-116">计划 MBAM 1.0 组策略要求</span><span class="sxs-lookup"><span data-stu-id="86b2f-116">Planning for MBAM 1.0 Group Policy Requirements</span></span>](planning-for-mbam-10-group-policy-requirements.md)

## <span data-ttu-id="86b2f-117">规划 MBAM 1.0 管理员角色</span><span class="sxs-lookup"><span data-stu-id="86b2f-117">Plan for MBAM 1.0 administrator roles</span></span>


<span data-ttu-id="86b2f-118">MBAM 管理员角色由在安装以下各项时由 MBAM 安装程序创建的本地组管理： BitLocker 管理和监视服务器、合规性和审核报告功能以及合规性和审核状态数据库。</span><span class="sxs-lookup"><span data-stu-id="86b2f-118">MBAM administrator roles are managed by local groups that are created by MBAM Setup when you install the following: BitLocker Administration and Monitoring Server, the Compliance and Audit Reports feature, and the Compliance and Audit Status Database.</span></span>

<span data-ttu-id="86b2f-119">如果在 ActiveDirectoryDomainServices 中创建安全组，则可以更有效地管理 MBAM 角色的成员身份，将相应的管理员帐户添加到这些组，然后将这些安全组添加到 MBAM 本地组。</span><span class="sxs-lookup"><span data-stu-id="86b2f-119">The membership of MBAM roles can be managed more effectively if you create security groups in ActiveDirectoryDomainServices, add the appropriate administrator accounts to those groups, and then add those security groups to the MBAM local groups.</span></span> <span data-ttu-id="86b2f-120">有关详细信息，请参阅[如何管理 MBAM 管理员角色](how-to-manage-mbam-administrator-roles-mbam-1.md)。</span><span class="sxs-lookup"><span data-stu-id="86b2f-120">For more information, see [How to Manage MBAM Administrator Roles](how-to-manage-mbam-administrator-roles-mbam-1.md).</span></span>

[<span data-ttu-id="86b2f-121">计划 MBAM 1.0 管理员角色</span><span class="sxs-lookup"><span data-stu-id="86b2f-121">Planning for MBAM 1.0 Administrator Roles</span></span>](planning-for-mbam-10-administrator-roles.md)

## <span data-ttu-id="86b2f-122">MBAM 规划的其他资源</span><span class="sxs-lookup"><span data-stu-id="86b2f-122">Other resources for MBAM planning</span></span>


[<span data-ttu-id="86b2f-123">计划 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="86b2f-123">Planning for MBAM 1.0</span></span>](planning-for-mbam-10.md)

 

 





