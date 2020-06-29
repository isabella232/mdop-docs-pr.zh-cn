---
title: 管理 MBAM 1.0 功能
description: 管理 MBAM 1.0 功能
author: dansimp
ms.assetid: dd9a9eff-f1ad-4af3-85d9-c19131a4ad22
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a99ac556227c0f113fb20f3aca32d21c204877b0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802925"
---
# <span data-ttu-id="49dfc-103">管理 MBAM 1.0 功能</span><span class="sxs-lookup"><span data-stu-id="49dfc-103">Administering MBAM 1.0 Features</span></span>


<span data-ttu-id="49dfc-104">完成所有必需的 Microsoft BitLocker 管理和监视（MBAM）规划和部署后，您可以配置和使用 MBAM 管理企业 BitLocker 加密。</span><span class="sxs-lookup"><span data-stu-id="49dfc-104">After you complete all necessary Microsoft BitLocker Administration and Monitoring (MBAM) planning and deployment, you can configure and use MBAM to manage enterprise BitLocker encryption.</span></span> <span data-ttu-id="49dfc-105">本部分中的信息介绍安装后的日常 MBAM 功能操作任务。</span><span class="sxs-lookup"><span data-stu-id="49dfc-105">The information in this section describes post-installation day-to-day MBAM feature operations tasks.</span></span>

## <span data-ttu-id="49dfc-106">管理 MBAM 管理员角色</span><span class="sxs-lookup"><span data-stu-id="49dfc-106">Manage MBAM Administrator Roles</span></span>


<span data-ttu-id="49dfc-107">完成所有服务器功能的 MBAM 设置后，必须授予管理员用户访问这些服务器功能的权限。</span><span class="sxs-lookup"><span data-stu-id="49dfc-107">After MBAM Setup is complete for all server features, administrative users must be granted access to these server features.</span></span> <span data-ttu-id="49dfc-108">最佳做法是管理或使用 MBAM 服务器功能的管理员应分配给 Active Directory 安全组，然后应将这些组添加到相应的 MBAM 管理本地组。</span><span class="sxs-lookup"><span data-stu-id="49dfc-108">As a best practice, administrators who will manage or use MBAM server features, should be assigned to Active Directory security groups and then those groups should be added to the appropriate MBAM administrative local group.</span></span>

[<span data-ttu-id="49dfc-109">如何管理 MBAM 管理员角色</span><span class="sxs-lookup"><span data-stu-id="49dfc-109">How to Manage MBAM Administrator Roles</span></span>](how-to-manage-mbam-administrator-roles-mbam-1.md)

## <span data-ttu-id="49dfc-110">管理硬件兼容性</span><span class="sxs-lookup"><span data-stu-id="49dfc-110">Manage Hardware Compatibility</span></span>


<span data-ttu-id="49dfc-111">MBAM 硬件兼容性功能可帮助你确保仅加密你指定为支持 BitLocker 的计算机硬件。</span><span class="sxs-lookup"><span data-stu-id="49dfc-111">The MBAM Hardware Compatibility feature can help you to ensure that only the computer hardware that you specify as supporting BitLocker will be encrypted.</span></span> <span data-ttu-id="49dfc-112">当此功能处于打开状态时，位 _admmontla 将仅加密标记为兼容的计算机。</span><span class="sxs-lookup"><span data-stu-id="49dfc-112">When this feature is turned on, bit\_admmontla will encrypt only computers that are marked as Compatible.</span></span>

<span data-ttu-id="49dfc-113">**重要提示** 关闭此功能时，将对部署了 MBAM 策略的所有计算机进行加密。</span><span class="sxs-lookup"><span data-stu-id="49dfc-113">**Important** When this feature is turned off, all computers where the MBAM policy is deployed will be encrypted.</span></span>

 

<span data-ttu-id="49dfc-114">如果你部署 "允许硬件兼容性检查" 组策略，MBAM 可以收集客户端计算机的建立和模型的信息。</span><span class="sxs-lookup"><span data-stu-id="49dfc-114">MBAM can collect information on both the make and model of client computers if you deploy the “Allow Hardware Compatibility Checking” Group Policy.</span></span> <span data-ttu-id="49dfc-115">如果配置此策略，则当在客户端计算机上部署 MBAM 客户端时，MBAM 代理会向 MBAM 服务器报告计算机和模型信息。</span><span class="sxs-lookup"><span data-stu-id="49dfc-115">If you configure this policy, the MBAM agent reports the computer make and model information to the MBAM Server when the MBAM Client is deployed on a client computer.</span></span>

[<span data-ttu-id="49dfc-116">如何管理硬件兼容性</span><span class="sxs-lookup"><span data-stu-id="49dfc-116">How to Manage Hardware Compatibility</span></span>](how-to-manage-hardware-compatibility-mbam-1.md)

[<span data-ttu-id="49dfc-117">如何管理用户 BitLocker 加密免除</span><span class="sxs-lookup"><span data-stu-id="49dfc-117">How to Manage User BitLocker Encryption Exemptions</span></span>](how-to-manage-user-bitlocker-encryption-exemptions-mbam-1.md)

## <span data-ttu-id="49dfc-118">管理 BitLocker 加密免除</span><span class="sxs-lookup"><span data-stu-id="49dfc-118">Manage BitLocker encryption exemptions</span></span>


<span data-ttu-id="49dfc-119">MBAM 可以授予来自 BitLocker 加密的两种形式的免除：计算机豁免和用户豁免。</span><span class="sxs-lookup"><span data-stu-id="49dfc-119">MBAM can grant two forms of exemption from BitLocker encryption: computer exemption and user exemption.</span></span> <span data-ttu-id="49dfc-120">当公司拥有不需要加密的计算机（例如在开发或测试中使用的计算机或不支持 BitLocker 的较旧计算机）时，通常使用计算机豁免。</span><span class="sxs-lookup"><span data-stu-id="49dfc-120">Computer exemption is typically used when a company has computers that do not have to be encrypted, such as computers that are used in development or testing, or older computers that do not support BitLocker.</span></span> <span data-ttu-id="49dfc-121">在某些情况下，当地法律可能还要求某些计算机未加密。</span><span class="sxs-lookup"><span data-stu-id="49dfc-121">In some cases, local law may also require that certain computers are not encrypted.</span></span> <span data-ttu-id="49dfc-122">您也可以选择免除不需要或不希望其驱动器加密的用户。</span><span class="sxs-lookup"><span data-stu-id="49dfc-122">You may also choose to exempt users who do not need or want their drives encrypted.</span></span>

[<span data-ttu-id="49dfc-123">如何管理计算机 BitLocker 加密免除</span><span class="sxs-lookup"><span data-stu-id="49dfc-123">How to Manage Computer BitLocker Encryption Exemptions</span></span>](how-to-manage-computer-bitlocker-encryption-exemptions.md)

## <span data-ttu-id="49dfc-124">使用 "控制面板" 管理 MBAM 客户端 BitLocker 加密选项</span><span class="sxs-lookup"><span data-stu-id="49dfc-124">Manage MBAM Client BitLocker Encryption Options by using the Control Panel</span></span>


<span data-ttu-id="49dfc-125">如果通过组策略对象（GPO）启用，则名为 "BitLocker 加密选项" 的自定义 MBAM 控制面板将在 "**系统和安全**" 下可用。</span><span class="sxs-lookup"><span data-stu-id="49dfc-125">If enabled through a Group Policy Objects (GPO), a custom MBAM control panel that is named BitLocker Encryption Options will be available under **System and Security**.</span></span> <span data-ttu-id="49dfc-126">此自定义控制面板替换默认的 Windows BitLocker 控制面板。</span><span class="sxs-lookup"><span data-stu-id="49dfc-126">This customized control panel replaces the default Windows BitLocker control panel.</span></span> <span data-ttu-id="49dfc-127">MBAM 控制面板使你能够解锁加密的驱动器（固定和可移动），还可帮助你管理 PIN 或密码。</span><span class="sxs-lookup"><span data-stu-id="49dfc-127">The MBAM control panel enables you to unlock encrypted drives (fixed and removable), and also helps you manage your PIN or password.</span></span>

[<span data-ttu-id="49dfc-128">如何使用控制面板管理 MBAM 客户端 BitLocker 加密选项</span><span class="sxs-lookup"><span data-stu-id="49dfc-128">How to Manage MBAM Client BitLocker Encryption Options by Using the Control Panel</span></span>](how-to-manage-mbam-client-bitlocker-encryption-options-by-using-the-control-panel-mbam-1.md)

## <span data-ttu-id="49dfc-129">用于管理 MBAM 功能的其他资源</span><span class="sxs-lookup"><span data-stu-id="49dfc-129">Other resources for Administering MBAM features</span></span>


[<span data-ttu-id="49dfc-130">MBAM 1.0 的操作</span><span class="sxs-lookup"><span data-stu-id="49dfc-130">Operations for MBAM 1.0</span></span>](operations-for-mbam-10.md)

 

 





