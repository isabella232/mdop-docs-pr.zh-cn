---
title: 部署 MBAM 1.0 语言版本更新
description: 部署 MBAM 1.0 语言版本更新
author: dansimp
ms.assetid: 9dbd85c3-e470-4752-a90f-25754dd46dab
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a819be81594efd9349e3f6c0f6559c2b810bdc9d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798142"
---
# <span data-ttu-id="1ca19-103">部署 MBAM 1.0 语言版本更新</span><span class="sxs-lookup"><span data-stu-id="1ca19-103">Deploying the MBAM 1.0 Language Release Update</span></span>


<span data-ttu-id="1ca19-104">Microsoft BitLocker 管理和监视（MBAM）1.0 语言版本是对 MBAM 的更新，其中包括新语言的支持。</span><span class="sxs-lookup"><span data-stu-id="1ca19-104">Microsoft BitLocker Administration and Monitoring (MBAM)1.0 Language Release is an update to MBAM and includes the support of new languages.</span></span> <span data-ttu-id="1ca19-105">新语言为：</span><span class="sxs-lookup"><span data-stu-id="1ca19-105">The new languages are:</span></span>

-   <span data-ttu-id="1ca19-106">英语（en-us）</span><span class="sxs-lookup"><span data-stu-id="1ca19-106">English (en-us)</span></span>

-   <span data-ttu-id="1ca19-107">法语（fr）</span><span class="sxs-lookup"><span data-stu-id="1ca19-107">French (fr)</span></span>

-   <span data-ttu-id="1ca19-108">意大利语（it）</span><span class="sxs-lookup"><span data-stu-id="1ca19-108">Italian (it)</span></span>

-   <span data-ttu-id="1ca19-109">德语（de）</span><span class="sxs-lookup"><span data-stu-id="1ca19-109">German (de)</span></span>

-   <span data-ttu-id="1ca19-110">西班牙语（es）</span><span class="sxs-lookup"><span data-stu-id="1ca19-110">Spanish (es)</span></span>

-   <span data-ttu-id="1ca19-111">朝鲜语（ko）</span><span class="sxs-lookup"><span data-stu-id="1ca19-111">Korean (ko)</span></span>

-   <span data-ttu-id="1ca19-112">日语（ja）</span><span class="sxs-lookup"><span data-stu-id="1ca19-112">Japanese (ja)</span></span>

-   <span data-ttu-id="1ca19-113">巴西葡萄牙语（pt-br）</span><span class="sxs-lookup"><span data-stu-id="1ca19-113">Brazilian Portuguese (pt-br)</span></span>

-   <span data-ttu-id="1ca19-114">俄语（ru）</span><span class="sxs-lookup"><span data-stu-id="1ca19-114">Russian (ru)</span></span>

-   <span data-ttu-id="1ca19-115">繁体中文（zh-cn&platform）</span><span class="sxs-lookup"><span data-stu-id="1ca19-115">Chinese Traditional (zh-tw)</span></span>

-   <span data-ttu-id="1ca19-116">简体中文（zh-cn&platform-cn）</span><span class="sxs-lookup"><span data-stu-id="1ca19-116">Chinese Simplified (zh-cn)</span></span>

<span data-ttu-id="1ca19-117">MBAM 1.0 语言更新将版本号从 MBAM 1.0.1237.1 更改为 MBAM 1.0.2001。</span><span class="sxs-lookup"><span data-stu-id="1ca19-117">The MBAM1.0 language update will change the version number from MBAM 1.0.1237.1 to MBAM 1.0.2001.</span></span>

<span data-ttu-id="1ca19-118">无需重新安装所有 MBAM 功能即可添加这些其他语言。</span><span class="sxs-lookup"><span data-stu-id="1ca19-118">You do not need to reinstall all of the MBAM features in order to add these additional languages.</span></span> <span data-ttu-id="1ca19-119">本主题定义添加新支持的语言所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="1ca19-119">This topic defines the steps required to add the newly supported languages.</span></span>

## <span data-ttu-id="1ca19-120">将 MBAM 国际版部署到 MBAM 服务器功能</span><span class="sxs-lookup"><span data-stu-id="1ca19-120">Deploy the MBAM international release to MBAM Server features</span></span>


<span data-ttu-id="1ca19-121">若要开始，必须更新以下 MBAM 服务器功能：</span><span class="sxs-lookup"><span data-stu-id="1ca19-121">To begin, you must update the following MBAM server features:</span></span>

-   <span data-ttu-id="1ca19-122">合规性和审核报告</span><span class="sxs-lookup"><span data-stu-id="1ca19-122">Compliance and Audit Report</span></span>

-   <span data-ttu-id="1ca19-123">管理和监视服务器</span><span class="sxs-lookup"><span data-stu-id="1ca19-123">Administration and Monitoring Server</span></span>

-   <span data-ttu-id="1ca19-124">策略模板</span><span class="sxs-lookup"><span data-stu-id="1ca19-124">Policy Templates</span></span>

<span data-ttu-id="1ca19-125">然后，您必须运行**MbamSetup.exe**以升级在同一台服务器上运行的 MBAM 功能。</span><span class="sxs-lookup"><span data-stu-id="1ca19-125">Then, you must run **MbamSetup.exe** to upgrade the MBAM features that run on the same server at the same time.</span></span>

[<span data-ttu-id="1ca19-126">如何在单个服务器上安装 MBAM 语言更新</span><span class="sxs-lookup"><span data-stu-id="1ca19-126">How to Install the MBAM Language Update on a Single Server</span></span>](how-to-install-the-mbam-language-update-on-a-single-server-mbam-1.md)

[<span data-ttu-id="1ca19-127">如何在分布式服务器上安装 MBAM 语言更新</span><span class="sxs-lookup"><span data-stu-id="1ca19-127">How to Install the MBAM Language Update on Distributed Servers</span></span>](how-to-install-the-mbam-language-update-on-distributed-servers-mbam-1.md)

## <span data-ttu-id="1ca19-128">为组策略安装 MBAM 语言更新</span><span class="sxs-lookup"><span data-stu-id="1ca19-128">Install the MBAM language update for Group Policies</span></span>


<span data-ttu-id="1ca19-129">可以在每个管理工作站上安装 MBAM 组策略模板，也可以将其复制到组策略中央存储，以便所有组策略管理员均可使用这些模板。</span><span class="sxs-lookup"><span data-stu-id="1ca19-129">The MBAM Group Policy templates can be installed on each management workstation or they can be copied to the Group Policy central store, in order to make the templates available to all Group Policy administrators.</span></span> <span data-ttu-id="1ca19-130">策略模板不能直接安装在域控制器上。</span><span class="sxs-lookup"><span data-stu-id="1ca19-130">The policy templates cannot be directly installed on a domain controller.</span></span> <span data-ttu-id="1ca19-131">如果不使用组策略中央存储，则必须手动将策略复制到管理 MBAM 组策略的每个域控制器。</span><span class="sxs-lookup"><span data-stu-id="1ca19-131">If you do not use a Group Policy central store, then you must copy the policies manually to each domain controller that manages MBAM Group Policy.</span></span>

<span data-ttu-id="1ca19-132">若要添加 MBAM 语言策略模板，请将组策略语言文件从安装了 "策略模板" 角色的计算机上的%SystemRoot%\\PolicyDefinitions 复制到工作站计算机上的同一位置。</span><span class="sxs-lookup"><span data-stu-id="1ca19-132">To add the MBAM language policies templates, copy the Group Policy language files from %SystemRoot%\\PolicyDefinitions on the computer where the “Policy Templates” role was installed to the same location on the workstation computer.</span></span> <span data-ttu-id="1ca19-133">下面是组策略文件的一些示例：</span><span class="sxs-lookup"><span data-stu-id="1ca19-133">Here are some examples of Group Policy files:</span></span>

-   <span data-ttu-id="1ca19-134">BitLockerManagement</span><span class="sxs-lookup"><span data-stu-id="1ca19-134">BitLockerManagement.admx</span></span>

-   <span data-ttu-id="1ca19-135">BitLockerUserManagement</span><span class="sxs-lookup"><span data-stu-id="1ca19-135">BitLockerUserManagement.admx</span></span>

-   <span data-ttu-id="1ca19-136">en-us\\BitLockerManagement.adml</span><span class="sxs-lookup"><span data-stu-id="1ca19-136">en-us\\BitLockerManagement.adml</span></span>

-   <span data-ttu-id="1ca19-137">en-us\\BitLockerUserManagement.adml</span><span class="sxs-lookup"><span data-stu-id="1ca19-137">en-us\\BitLockerUserManagement.adml</span></span>

-   <span data-ttu-id="1ca19-138">fr-fr\\ BitLockerManagement adml</span><span class="sxs-lookup"><span data-stu-id="1ca19-138">fr-fr\\ BitLockerManagement.adml</span></span>

-   <span data-ttu-id="1ca19-139">fr-fr\\ BitLockerUserManagement adml</span><span class="sxs-lookup"><span data-stu-id="1ca19-139">fr-fr\\ BitLockerUserManagement.adml</span></span>

-   <span data-ttu-id="1ca19-140">（同样适用于每种支持的语言）</span><span class="sxs-lookup"><span data-stu-id="1ca19-140">(and similarly for each supported language)</span></span>

## <span data-ttu-id="1ca19-141">MBAM 国际发行版中的已知问题</span><span class="sxs-lookup"><span data-stu-id="1ca19-141">Known issues in the MBAM international release</span></span>


<span data-ttu-id="1ca19-142">本主题包含 Microsoft BitLocker 管理和监控国际发布版的已知问题。</span><span class="sxs-lookup"><span data-stu-id="1ca19-142">This topic contains known issues for Microsoft BitLocker Administration and Monitoring International Release.</span></span>

[<span data-ttu-id="1ca19-143">MBAM 国际版本中的已知问题</span><span class="sxs-lookup"><span data-stu-id="1ca19-143">Known Issues in the MBAM International Release</span></span>](known-issues-in-the-mbam-international-release-mbam-1.md)

## <span data-ttu-id="1ca19-144">用于部署 MBAM 1.0 语言更新的其他资源</span><span class="sxs-lookup"><span data-stu-id="1ca19-144">Other resources for deploying the MBAM 1.0 Language Update</span></span>


[<span data-ttu-id="1ca19-145">部署 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="1ca19-145">Deploying MBAM 1.0</span></span>](deploying-mbam-10.md)

 

 





