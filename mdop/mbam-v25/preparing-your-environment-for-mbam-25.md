---
title: 为 MBAM 2.5 准备你的环境
description: 为 MBAM 2.5 准备你的环境
author: dansimp
ms.assetid: 7552ba08-9dbf-40cd-8920-203d733fd242
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b18c9853035018c2e36dd447fbf0effbf49c45cd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803779"
---
# <span data-ttu-id="d8037-103">为 MBAM 2.5 准备你的环境</span><span class="sxs-lookup"><span data-stu-id="d8037-103">Preparing your Environment for MBAM 2.5</span></span>


<span data-ttu-id="d8037-104">在开始 Microsoft BitLocker 管理和监视（MBAM）安装之前，应确保已满足安装产品的先决条件。</span><span class="sxs-lookup"><span data-stu-id="d8037-104">Before beginning Microsoft BitLocker Administration and Monitoring (MBAM) Setup, you should make sure that you have met the prerequisites to install the product.</span></span> <span data-ttu-id="d8037-105">当您知道先决条件提前的时候，您可以高效地部署产品并启用其功能，以便最有效地支持组织的业务目标。</span><span class="sxs-lookup"><span data-stu-id="d8037-105">When you know what the prerequisites are ahead of time, you can efficiently deploy the product and enable its features so that it most effectively supports your organization’s business objectives.</span></span>

<span data-ttu-id="d8037-106">如果你要通过配置管理器部署 Microsoft BitLocker 管理和监视，请确保满足本主题后面列出的配置管理器的其他要求。</span><span class="sxs-lookup"><span data-stu-id="d8037-106">If you are deploying Microsoft BitLocker Administration and Monitoring with Configuration Manager, ensure that you meet the additional requirements for Configuration Manager, which are listed later in this topic.</span></span>

## <span data-ttu-id="d8037-107">查看 MBAM 2.5 部署先决条件</span><span class="sxs-lookup"><span data-stu-id="d8037-107">Review MBAM 2.5 deployment prerequisites</span></span>


<span data-ttu-id="d8037-108">若要确保你的 MBAM 部署成功，请确保在安装 MBAM 客户端并配置 MBAM 服务器功能之前，查看并完成所需的必备软件先决条件。</span><span class="sxs-lookup"><span data-stu-id="d8037-108">To ensure that your MBAM deployment is successful, make sure that you review and complete the required software prerequisites before you install the MBAM Client and configure the MBAM Server features.</span></span>

[<span data-ttu-id="d8037-109">MBAM 2.5 部署先决条件</span><span class="sxs-lookup"><span data-stu-id="d8037-109">MBAM 2.5 Deployment Prerequisites</span></span>](mbam-25-deployment-prerequisites.md)

## <span data-ttu-id="d8037-110">规划 MBAM 2.5 组策略要求</span><span class="sxs-lookup"><span data-stu-id="d8037-110">Plan for MBAM 2.5 Group Policy requirements</span></span>


<span data-ttu-id="d8037-111">在 MBAM 可以管理企业中的客户端之前，必须下载并配置特定于 MBAM 的组策略模板，然后配置你的环境所需的组策略设置。</span><span class="sxs-lookup"><span data-stu-id="d8037-111">Before MBAM can manage clients in the enterprise, you must download and configure Group Policy templates that are specific to MBAM, and then configure the Group Policy settings that you want for your environment.</span></span>

[<span data-ttu-id="d8037-112">规划 MBAM 2.5 组策略要求</span><span class="sxs-lookup"><span data-stu-id="d8037-112">Planning for MBAM 2.5 Group Policy Requirements</span></span>](planning-for-mbam-25-group-policy-requirements.md)

## <span data-ttu-id="d8037-113">规划 MBAM 2.5 角色和帐户</span><span class="sxs-lookup"><span data-stu-id="d8037-113">Plan for MBAM 2.5 roles and accounts</span></span>


<span data-ttu-id="d8037-114">作为先决条件的一部分，你必须定义特定的角色和帐户，这些角色和帐户在 MBAM 中用于提供对特定服务器和功能的安全和访问权限，例如在 SQL Server 上运行的数据库和在管理和监视服务器上运行的 web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="d8037-114">As part of the prerequisites, you must define certain roles and accounts, which are used in MBAM to provide security and access rights to specific servers and features, such as the databases running on SQL Server and the web applications running on the Administration and Monitoring Server.</span></span>

[<span data-ttu-id="d8037-115">规划 MBAM 2.5 组和帐户</span><span class="sxs-lookup"><span data-stu-id="d8037-115">Planning for MBAM 2.5 Groups and Accounts</span></span>](planning-for-mbam-25-groups-and-accounts.md)

## <span data-ttu-id="d8037-116">MBAM 规划的其他资源</span><span class="sxs-lookup"><span data-stu-id="d8037-116">Other resources for MBAM planning</span></span>


[<span data-ttu-id="d8037-117">规划 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="d8037-117">Planning for MBAM 2.5</span></span>](planning-for-mbam-25.md)

[<span data-ttu-id="d8037-118">MBAM 2.5 支持的配置</span><span class="sxs-lookup"><span data-stu-id="d8037-118">MBAM 2.5 Supported Configurations</span></span>](mbam-25-supported-configurations.md)

## <span data-ttu-id="d8037-119">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="d8037-119">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="d8037-120">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="d8037-120">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="d8037-121">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="d8037-121">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>

 

 





