---
title: 配置 MED-V 工作区策略
description: 配置 MED-V 工作区策略
author: dansimp
ms.assetid: 0eaed981-cbf3-4b16-a4b7-4705c5705dc7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 84bdae38b1c801e2c2be2a3dd1d12dd2ca7d932d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803652"
---
# <span data-ttu-id="51ff6-103">配置 MED-V 工作区策略</span><span class="sxs-lookup"><span data-stu-id="51ff6-103">Configuring MED-V Workspace Policies</span></span>


<span data-ttu-id="51ff6-104">MED-V 工作区策略是一组可配置的设置，用于定义虚拟化环境和应用程序在主机上的执行方式。</span><span class="sxs-lookup"><span data-stu-id="51ff6-104">A MED-V workspace policy is a group of configurable settings that define how the virtualized environment and applications perform on the host machine.</span></span> <span data-ttu-id="51ff6-105">本部分中的主题介绍 MED-V 工作区策略中的所有可配置设置，以及这些设置对 MED-V 工作区的影响。</span><span class="sxs-lookup"><span data-stu-id="51ff6-105">The topics in this section describe all the configurable settings in the MED-V workspace policy as well as how these settings influence the MED-V workspace.</span></span>

<span data-ttu-id="51ff6-106">以下 MED-V 工作区类型可用：</span><span class="sxs-lookup"><span data-stu-id="51ff6-106">The following MED-V workspace types are available:</span></span>

-   <span data-ttu-id="51ff6-107">**持久性**-在持久的 med-v 工作区中，用户对 med-v 工作区所做的所有更改和添加都保存在会话之间的 med-v 工作区中。</span><span class="sxs-lookup"><span data-stu-id="51ff6-107">**Persistent**—In a persistent MED-V workspace, all changes and additions the user makes to the MED-V workspace are saved in the MED-V workspace between sessions.</span></span> <span data-ttu-id="51ff6-108">此外，永久的 MED-V 工作区通常在域环境中使用。</span><span class="sxs-lookup"><span data-stu-id="51ff6-108">Additionally, a persistent MED-V workspace is generally used in a domain environment.</span></span>

-   <span data-ttu-id="51ff6-109">**Revertible**-在 Revertible med-v 工作区中，在每个会话完成时（即，在停止 med-v 工作区时），med-v 工作区在部署过程中将还原为其原始状态。</span><span class="sxs-lookup"><span data-stu-id="51ff6-109">**Revertible**—In a revertible MED-V workspace, at the completion of each session (that is, when the MED-V workspace is stopped), the MED-V workspace reverts to its original state during deployment.</span></span> <span data-ttu-id="51ff6-110">在会话之间的 MED-V 工作区中，不会保存用户所做的任何更改或添加。</span><span class="sxs-lookup"><span data-stu-id="51ff6-110">No changes or additions that the user made are saved on the MED-V workspace between sessions.</span></span> <span data-ttu-id="51ff6-111">不能在域环境中使用 revertible MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="51ff6-111">A revertible MED-V workspace cannot be used in a domain environment.</span></span>

<span data-ttu-id="51ff6-112">在部署 MED-V 工作区之前，请务必确定你创建的 MED-V 工作区的类型，因为不建议在向用户部署策略后重新配置 MED-V 工作区的类型。</span><span class="sxs-lookup"><span data-stu-id="51ff6-112">It is important to decide on the type of MED-V workspace you are creating before deploying the MED-V workspace, because it is not recommended to reconfigure the type of MED-V workspace after a policy has been deployed to users.</span></span>

<span data-ttu-id="51ff6-113">**注意** 配置策略时，未填写的必填字段旁边会显示一个警告符号。</span><span class="sxs-lookup"><span data-stu-id="51ff6-113">**Note** When configuring a policy, a warning symbol appears next to mandatory fields that are not filled in.</span></span> <span data-ttu-id="51ff6-114">如果未填写必填字段，则该符号也会显示在选项卡上。</span><span class="sxs-lookup"><span data-stu-id="51ff6-114">If a mandatory field is not filled in, the symbol appears on the tab as well.</span></span>

 

## <span data-ttu-id="51ff6-115">本部分内容</span><span class="sxs-lookup"><span data-stu-id="51ff6-115">In This Section</span></span>


<a href="" id="how-to-apply-general-settings-to-a-med-v-workspace"></a>[<span data-ttu-id="51ff6-116">如何将常规设置应用于 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="51ff6-116">How to Apply General Settings to a MED-V Workspace</span></span>](how-to-apply-general-settings-to-a-med-v-workspace.md)  
<span data-ttu-id="51ff6-117">介绍 MED-V 工作区的常规设置，以及如何将它们应用于策略。</span><span class="sxs-lookup"><span data-stu-id="51ff6-117">Describes the general settings of a MED-V workspace, and how to apply them to a policy.</span></span>

<a href="" id="how-to-apply-virtual-machine-settings-to-a-med-v-workspace"></a>[<span data-ttu-id="51ff6-118">如何将虚拟机设置应用于 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="51ff6-118">How to Apply Virtual Machine Settings to a MED-V Workspace</span></span>](how-to-apply-virtual-machine-settings-to-a-med-v-workspace.md)  
<span data-ttu-id="51ff6-119">描述 MED-V 工作区的虚拟机设置，以及如何将它们应用于策略。</span><span class="sxs-lookup"><span data-stu-id="51ff6-119">Describes the virtual machine settings for a MED-V workspace, and how to apply them to a policy.</span></span>

<a href="" id="how-to-configure-a-domain-user-or-group"></a>[<span data-ttu-id="51ff6-120">如何配置域用户或组</span><span class="sxs-lookup"><span data-stu-id="51ff6-120">How to Configure a Domain User or Group</span></span>](how-to-configure-a-domain-user-or-groupmedvv2.md)  
<span data-ttu-id="51ff6-121">介绍如何配置域用户和组。</span><span class="sxs-lookup"><span data-stu-id="51ff6-121">Describes how to configure domain users and groups.</span></span>

<a href="" id="how-to-configure-published-applications"></a>[<span data-ttu-id="51ff6-122">如何配置已发布的应用程序</span><span class="sxs-lookup"><span data-stu-id="51ff6-122">How to Configure Published Applications</span></span>](how-to-configure-published-applicationsmedvv2.md)  
<span data-ttu-id="51ff6-123">介绍已发布的应用程序和菜单，以及如何将它们应用于策略。</span><span class="sxs-lookup"><span data-stu-id="51ff6-123">Describes published applications and menus, and how to apply them to a policy.</span></span>

<a href="" id="how-to-configure-web-settings-for-a-med-v-workspace"></a>[<span data-ttu-id="51ff6-124">如何为 MED-V 工作区配置 Web 设置</span><span class="sxs-lookup"><span data-stu-id="51ff6-124">How to Configure Web Settings for a MED-V Workspace</span></span>](how-to-configure-web-settings-for-a-med-v-workspace.md)  
<span data-ttu-id="51ff6-125">介绍了可用于 MED-V 工作区的 Web 设置，以及如何将它们应用于策略。</span><span class="sxs-lookup"><span data-stu-id="51ff6-125">Describes the Web settings available for a MED-V workspace, and how to apply them to a policy.</span></span>

<a href="" id="how-to-configure-the-virtual-machine-setup-for-a-med-v-workspace"></a>[<span data-ttu-id="51ff6-126">如何为 MED-V 工作区配置虚拟机设置</span><span class="sxs-lookup"><span data-stu-id="51ff6-126">How to Configure the Virtual Machine Setup for a MED-V Workspace</span></span>](how-to-configure-the-virtual-machine-setup-for-a-med-v-workspace.md)  
<span data-ttu-id="51ff6-127">介绍 MED-V 工作区的虚拟机设置，以及如何将其应用于策略。</span><span class="sxs-lookup"><span data-stu-id="51ff6-127">Describes the virtual machine setup for a MED-V workspace, and how to apply it to a policy.</span></span>

<a href="" id="how-to-apply-network-settings-to-a-med-v-workspace"></a>[<span data-ttu-id="51ff6-128">如何将网络设置应用于 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="51ff6-128">How to Apply Network Settings to a MED-V Workspace</span></span>](how-to-apply-network-settings-to-a-med-v-workspace.md)  
<span data-ttu-id="51ff6-129">描述 MED-V 工作区的网络设置，以及如何将它们应用于策略。</span><span class="sxs-lookup"><span data-stu-id="51ff6-129">Describes the network settings of a MED-V workspace, and how to apply them to a policy.</span></span>

<a href="" id="how-to-apply-performance-settings-to-a-med-v-workspace"></a>[<span data-ttu-id="51ff6-130">如何将性能设置应用于 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="51ff6-130">How to Apply Performance Settings to a MED-V Workspace</span></span>](how-to-apply-performance-settings-to-a-med-v-workspace.md)  
<span data-ttu-id="51ff6-131">介绍 MED-V 工作区的性能设置，以及如何将它们应用于策略。</span><span class="sxs-lookup"><span data-stu-id="51ff6-131">Describes the performance settings of a MED-V workspace, and how to apply them to a policy.</span></span>

<a href="" id="how-to-import-and-export-a-policy"></a>[<span data-ttu-id="51ff6-132">如何导入和导出策略</span><span class="sxs-lookup"><span data-stu-id="51ff6-132">How to Import and Export a Policy</span></span>](how-to-import-and-export-a-policy.md)  
<span data-ttu-id="51ff6-133">介绍如何导入和导出策略。</span><span class="sxs-lookup"><span data-stu-id="51ff6-133">Describes how to import and export a policy.</span></span>

 

 





