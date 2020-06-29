---
title: 如何管理计算机 BitLocker 加密免除
description: 如何管理计算机 BitLocker 加密免除
author: dansimp
ms.assetid: d4400a0d-b36b-4cf5-a294-1f53ec47f9ee
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 51b93061468508900eaee7fce8a7827e2db61d19
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803816"
---
# <span data-ttu-id="0aad3-103">如何管理计算机 BitLocker 加密免除</span><span class="sxs-lookup"><span data-stu-id="0aad3-103">How to Manage Computer BitLocker Encryption Exemptions</span></span>


<span data-ttu-id="0aad3-104">Microsoft BitLocker 管理和监视（MBAM）可用于免除某些计算机的 BitLocker 保护。</span><span class="sxs-lookup"><span data-stu-id="0aad3-104">Microsoft BitLocker Administration and Monitoring (MBAM) can be used to exempt certain computers from BitLocker protection.</span></span> <span data-ttu-id="0aad3-105">例如，组织可能会决定逐个计算机地控制 BitLocker 豁免。</span><span class="sxs-lookup"><span data-stu-id="0aad3-105">For example, an organization may decide to control BitLocker exemption on a computer-by-computer basis.</span></span>

<span data-ttu-id="0aad3-106">若要从 BitLocker 加密中免除计算机，必须将计算机添加到 ActiveDirectoryDomainServices 中的安全组，以便绕过任何基于计算机的 BitLocker 保护规则。</span><span class="sxs-lookup"><span data-stu-id="0aad3-106">To exempt a computer from BitLocker encryption, you must add the computer to a security group in ActiveDirectoryDomainServices in order to bypass any computer-based BitLocker protection rules.</span></span>

<span data-ttu-id="0aad3-107">**注意** 如果计算机已受 BitLocker 保护，则计算机豁免策略将不起作用。</span><span class="sxs-lookup"><span data-stu-id="0aad3-107">**Note** If the computer is already BitLocker-protected, the computer exemption policy has no effect.</span></span>

 

**<span data-ttu-id="0aad3-108">从 BitLocker 加密中免除计算机</span><span class="sxs-lookup"><span data-stu-id="0aad3-108">To exempt a computer from BitLocker encryption</span></span>**

1.  <span data-ttu-id="0aad3-109">将您希望免除的计算机帐户添加到 ActiveDirectoryDomainServices 中的安全组。</span><span class="sxs-lookup"><span data-stu-id="0aad3-109">Add the computer account that you want to be exempted to a security group in ActiveDirectoryDomainServices.</span></span> <span data-ttu-id="0aad3-110">这允许你绕过任何基于计算机的 BitLocker 保护规则。</span><span class="sxs-lookup"><span data-stu-id="0aad3-110">This allows you to bypass any computer-based BitLocker protection rules.</span></span>

2.  <span data-ttu-id="0aad3-111">通过使用 MBAM 组策略模板创建组策略对象，然后将组策略对象与您在上一步中创建的 Active Directory 组相关联。</span><span class="sxs-lookup"><span data-stu-id="0aad3-111">Create a Group Policy Object by using the MBAM Group Policy template, then associate the Group Policy Object with the Active Directory group that you created in the previous step.</span></span> <span data-ttu-id="0aad3-112">有关创建必要的组策略对象的详细信息，请参阅[部署 MBAM 1.0 组策略对象](deploying-mbam-10-group-policy-objects.md)。</span><span class="sxs-lookup"><span data-stu-id="0aad3-112">For more information about creating the necessary Group Policy Objects, see [Deploying MBAM 1.0 Group Policy Objects](deploying-mbam-10-group-policy-objects.md).</span></span>

3.  <span data-ttu-id="0aad3-113">当已免除的计算机启动时，MBAM 客户端将根据计算机是否属于 BitLocker 豁免安全组来检查计算机豁免策略设置并暂停保护。</span><span class="sxs-lookup"><span data-stu-id="0aad3-113">When an exempted computer starts, the MBAM client checks the Computer Exemption Policy setting and suspends protection based on whether the computer is part of the BitLocker exemption security group.</span></span>

## <span data-ttu-id="0aad3-114">相关主题</span><span class="sxs-lookup"><span data-stu-id="0aad3-114">Related topics</span></span>


[<span data-ttu-id="0aad3-115">管理 MBAM 1.0 功能</span><span class="sxs-lookup"><span data-stu-id="0aad3-115">Administering MBAM 1.0 Features</span></span>](administering-mbam-10-features.md)

 

 





