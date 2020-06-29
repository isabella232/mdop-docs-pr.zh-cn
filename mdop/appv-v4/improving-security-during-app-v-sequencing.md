---
title: 增强 App-V 排序期间的安全性
description: 增强 App-V 排序期间的安全性
author: dansimp
ms.assetid: f30206dd-5749-4a27-bbaf-61fc21b9c663
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ba97c334c4ac9a928fee3d69c265c12e82e43619
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798955"
---
# <span data-ttu-id="e335c-103">增强 App-V 排序期间的安全性</span><span class="sxs-lookup"><span data-stu-id="e335c-103">Improving Security During App-V Sequencing</span></span>


<span data-ttu-id="e335c-104">打包应用程序进行排序是 App-v 基础结构中最大的持续任务。</span><span class="sxs-lookup"><span data-stu-id="e335c-104">Packaging applications for sequencing is the largest ongoing task in an App-V infrastructure.</span></span> <span data-ttu-id="e335c-105">由于此任务正在进行，因此应仔细考虑创建顺序应用程序时要遵循的策略和过程。</span><span class="sxs-lookup"><span data-stu-id="e335c-105">Because this task is ongoing, you should carefully consider creating policies and procedures to follow when sequencing applications.</span></span> <span data-ttu-id="e335c-106">在 App-v 4.5 中，排序期间，你可以捕获虚拟化应用程序的文件资源上的访问控制列表（Acl）。</span><span class="sxs-lookup"><span data-stu-id="e335c-106">In App-V4.5, during sequencing, you can capture Access Control Lists (ACLs) on the file assets of the virtualized application.</span></span>

## <span data-ttu-id="e335c-107">排序器上的病毒扫描</span><span class="sxs-lookup"><span data-stu-id="e335c-107">Virus Scanning on the Sequencer</span></span>


<span data-ttu-id="e335c-108">最佳做法是在排序计算机上安装扫描软件，然后扫描计算机以查找病毒和恶意软件。</span><span class="sxs-lookup"><span data-stu-id="e335c-108">It is a best practice to install the scanning software on the sequencing computer and then scan the computer for viruses and malware.</span></span> <span data-ttu-id="e335c-109">在对顺序计算机进行扫描且没有任何病毒或恶意软件后，在对任何应用程序进行排序之前，在排序计算机上禁用扫描软件（包括所有防病毒和恶意软件检测软件）。</span><span class="sxs-lookup"><span data-stu-id="e335c-109">After the sequencing computer is scanned and free of any viruses or malware, disable the scanning software, including all antivirus and malware detection software, on the sequencing computer before sequencing any applications.</span></span> <span data-ttu-id="e335c-110">这将加快排序过程，并防止扫描软件组件在序列化期间被检测并包含在虚拟应用程序包中。</span><span class="sxs-lookup"><span data-stu-id="e335c-110">This speeds the sequencing process and prevents the scanning software components from being detected during sequencing and included in the virtual application package.</span></span>

## <span data-ttu-id="e335c-111">捕获文件上的 Acl （NTFS）</span><span class="sxs-lookup"><span data-stu-id="e335c-111">Capturing ACLs on Files (NTFS)</span></span>


<span data-ttu-id="e335c-112">Sequencer 将捕获在排序安装阶段中监视的文件的 NTFS 权限（Acl）。</span><span class="sxs-lookup"><span data-stu-id="e335c-112">The Sequencer captures NTFS permissions (the ACLs) for the files that are monitored during the sequencing installation phase.</span></span> <span data-ttu-id="e335c-113">（在发布 app-v 4.5 之前，不会作为排序过程的一部分捕获 Acl。）此新功能允许某些应用程序针对权限级别较低的用户运行，这些用户通常需要管理权限。</span><span class="sxs-lookup"><span data-stu-id="e335c-113">(Before the release of App-V4.5, ACLs were not captured as part of the sequencing process.) This new feature enables certain applications to run for users with a low level of permission that would normally require Administrative privileges.</span></span>

<span data-ttu-id="e335c-114">此功能还使排序工程师能够捕获由供应商标识的安全设置。</span><span class="sxs-lookup"><span data-stu-id="e335c-114">This feature also enables the sequencing engineer to capture the security settings identified by the vendor.</span></span> <span data-ttu-id="e335c-115">无法应用供应商推荐的设置可能会使应用程序开放于用户的攻击或滥用。</span><span class="sxs-lookup"><span data-stu-id="e335c-115">Failing to apply the settings recommended by the vendor could leave the application open to attack or misuse by users.</span></span> <span data-ttu-id="e335c-116">有关是否应使用开放 Acl 部署应用程序的信息，请参阅你的应用程序支持组或软件供应商。</span><span class="sxs-lookup"><span data-stu-id="e335c-116">For information about whether or not you should deploy an application with open ACLs, refer to your application support group or the software vendor.</span></span>

<span data-ttu-id="e335c-117">**重要提示** 虽然排序器在监视排序的安装阶段时捕获了 NTFS Acl，但它不会捕获注册表的 Acl。</span><span class="sxs-lookup"><span data-stu-id="e335c-117">**Important** Although the sequencer captures the NTFS ACLs while monitoring the installation phase of sequencing, it does not capture the ACLs for the registry.</span></span> <span data-ttu-id="e335c-118">用户对虚拟应用程序（服务除外）的所有注册表项具有完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="e335c-118">Users have full access to all registry keys for virtual applications except for services.</span></span> <span data-ttu-id="e335c-119">但是，如果用户修改了虚拟应用程序的注册表，该更改将存储在特定位置（）中， `uservol_sftfs_v1.pkg` 并且不会影响其他用户。</span><span class="sxs-lookup"><span data-stu-id="e335c-119">However, if a user modifies the registry of a virtual application, that change is stored in a specific location (`uservol_sftfs_v1.pkg`) and won’t affect other users.</span></span>

 

<span data-ttu-id="e335c-120">在安装阶段中，如果需要，排序工程师可以修改文件的默认权限。</span><span class="sxs-lookup"><span data-stu-id="e335c-120">During the installation phase, a sequencing engineer can modify the default permissions of the files if necessary.</span></span> <span data-ttu-id="e335c-121">排序过程完成后，在保存程序包之前，先后顺序工程师可以选择强制实施在安装阶段捕获的安全描述符。</span><span class="sxs-lookup"><span data-stu-id="e335c-121">After the sequencing process is complete, but before saving the package, the sequencing engineer can then choose to enforce security descriptors that were captured during the installation phase.</span></span> <span data-ttu-id="e335c-122">最佳做法是，如果任何其他解决方案都不允许应用程序在虚拟化后正常运行，则强制实施安全描述符。</span><span class="sxs-lookup"><span data-stu-id="e335c-122">It is a best practice to enforce security descriptors if no other solution allows the application to run properly once virtualized.</span></span>

 

 





