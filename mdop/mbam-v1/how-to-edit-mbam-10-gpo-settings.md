---
title: 如何编辑 MBAM 1.0 GPO 设置
description: 如何编辑 MBAM 1.0 GPO 设置
author: dansimp
ms.assetid: 03d12fbc-4302-43fc-9b38-440607d778a1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 824fbc2fe0d8f2b00c32de177733e4e327cf4d44
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803537"
---
# <span data-ttu-id="00823-103">如何编辑 MBAM 1.0 GPO 设置</span><span class="sxs-lookup"><span data-stu-id="00823-103">How to Edit MBAM 1.0 GPO Settings</span></span>


<span data-ttu-id="00823-104">若要成功部署 Microsoft BitLocker 管理和监视（MBAM），必须首先确定你将在 Microsoft BitLocker 管理和监视的实现中使用的组策略。</span><span class="sxs-lookup"><span data-stu-id="00823-104">To successfully deploy Microsoft BitLocker Administration and Monitoring (MBAM), you must first determine the Group Policies that you will use in your implementation of Microsoft BitLocker Administration and Monitoring.</span></span> <span data-ttu-id="00823-105">有关各种可用策略的详细信息，请参阅[规划 MBAM 1.0 组策略要求](planning-for-mbam-10-group-policy-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="00823-105">For more information about the various available policies, see [Planning for MBAM 1.0 Group Policy Requirements](planning-for-mbam-10-group-policy-requirements.md).</span></span> <span data-ttu-id="00823-106">确定要使用的策略后，必须修改包含 MBAM 策略设置的一个或多个组策略对象（GPO）。</span><span class="sxs-lookup"><span data-stu-id="00823-106">After you have determined the policies that you are going to use, you then must modify one or more Group Policy Objects (GPO) that include the MBAM policy settings.</span></span>

<span data-ttu-id="00823-107">以下步骤介绍了如何配置基本的推荐组策略对象（GPO）设置，以使 MBAM 能够管理组织的客户端计算机的 BitLocker 加密。</span><span class="sxs-lookup"><span data-stu-id="00823-107">The following steps describe how to configure the basic, recommended Group Policy object (GPO) settings to enable MBAM to manage BitLocker encryption for your organization’s client computers.</span></span>

**<span data-ttu-id="00823-108">编辑 MBAM 客户端 GPO 设置</span><span class="sxs-lookup"><span data-stu-id="00823-108">To edit the MBAM Client GPO settings</span></span>**

1.  <span data-ttu-id="00823-109">在安装了 MBAM 组策略模板的计算机上，请确保启用 MBAM 服务。</span><span class="sxs-lookup"><span data-stu-id="00823-109">On a computer that has MBAM Group Policy template installed, make sure that MBAM services are enabled.</span></span>

2.  <span data-ttu-id="00823-110">对这些操作使用组策略管理控制台（GPMC）或高级组策略管理（AGPM） MDOP 产品：选择 "**计算机配置**"，选择 "**策略**"，单击 "**管理模板**"，选择 " **Windows 组件**"，然后单击 " **MDOP MBAM （BitLocker 管理）**"。</span><span class="sxs-lookup"><span data-stu-id="00823-110">Use the Group Policy Management Console (GPMC.msc) or the Advanced Group Policy Management (AGPM) MDOP product for these actions: Select **Computer configuration**, choose **Policies**, click **Administrative Templates**, select **Windows Components**, and then click **MDOP MBAM (BitLocker Management)**.</span></span>

3.  <span data-ttu-id="00823-111">编辑在客户端计算机上启用 MBAM 客户端服务所需的组策略对象设置。</span><span class="sxs-lookup"><span data-stu-id="00823-111">Edit the Group Policy Object settings that are required to enable MBAM Client services on client computers.</span></span> <span data-ttu-id="00823-112">对于下表中的每个策略，依次选择 "**策略组**"、"**策略**" 和 "配置"**设置**。</span><span class="sxs-lookup"><span data-stu-id="00823-112">For each policy in the table that follows, select **Policy Group**, click the **Policy**, and then configure the **Setting**.</span></span>

    <span data-ttu-id="00823-113">策略组</span><span class="sxs-lookup"><span data-stu-id="00823-113">Policy Group</span></span>

    <span data-ttu-id="00823-114">策略</span><span class="sxs-lookup"><span data-stu-id="00823-114">Policy</span></span>

    <span data-ttu-id="00823-115">设置</span><span class="sxs-lookup"><span data-stu-id="00823-115">Setting</span></span>

    <span data-ttu-id="00823-116">客户端管理</span><span class="sxs-lookup"><span data-stu-id="00823-116">Client Management</span></span>

    <span data-ttu-id="00823-117">配置 MBAM 服务</span><span class="sxs-lookup"><span data-stu-id="00823-117">Configure MBAM Services</span></span>

    <span data-ttu-id="00823-118">已启用。</span><span class="sxs-lookup"><span data-stu-id="00823-118">Enabled.</span></span> <span data-ttu-id="00823-119">设置**MBAM 恢复和硬件服务终结点**，并**选择要存储的 BitLocker 恢复信息**。</span><span class="sxs-lookup"><span data-stu-id="00823-119">Set **MBAM Recovery and Hardware service endpoint** and **Select BitLocker recovery information to store**.</span></span>

    <span data-ttu-id="00823-120">设置**MBAM 合规性服务终结点**，并**在（分钟）内输入状态报告频率**。</span><span class="sxs-lookup"><span data-stu-id="00823-120">Set **MBAM compliance service endpoint** and **Enter status report frequency in (minutes)**.</span></span>

    <span data-ttu-id="00823-121">允许硬件兼容性检查</span><span class="sxs-lookup"><span data-stu-id="00823-121">Allow hardware compatibility checking</span></span>

    <span data-ttu-id="00823-122">已禁用。</span><span class="sxs-lookup"><span data-stu-id="00823-122">Disabled.</span></span> <span data-ttu-id="00823-123">此策略默认情况下处于启用状态，但基本 MBAM 实现不需要此策略。</span><span class="sxs-lookup"><span data-stu-id="00823-123">This policy is enabled by default, but is not needed for a basic MBAM implementation.</span></span>

    <span data-ttu-id="00823-124">操作系统驱动器</span><span class="sxs-lookup"><span data-stu-id="00823-124">Operating System Drive</span></span>

    <span data-ttu-id="00823-125">操作系统驱动器加密设置</span><span class="sxs-lookup"><span data-stu-id="00823-125">Operating system drive encryption settings</span></span>

    <span data-ttu-id="00823-126">已启用。</span><span class="sxs-lookup"><span data-stu-id="00823-126">Enabled.</span></span> <span data-ttu-id="00823-127">**为操作系统驱动器设置选择保护程序**。</span><span class="sxs-lookup"><span data-stu-id="00823-127">Set **Select protector for operating system drive**.</span></span> <span data-ttu-id="00823-128">这是将操作系统驱动器数据保存到 MBAM 密钥恢复服务器所必需的。</span><span class="sxs-lookup"><span data-stu-id="00823-128">This is required to save operating system drive data to the MBAM Key Recovery server.</span></span>

    <span data-ttu-id="00823-129">可移动驱动器</span><span class="sxs-lookup"><span data-stu-id="00823-129">Removable Drive</span></span>

    <span data-ttu-id="00823-130">控制可移动驱动器上的 BitLocker 的使用</span><span class="sxs-lookup"><span data-stu-id="00823-130">Control Use of BitLocker on removable drives</span></span>

    <span data-ttu-id="00823-131">已启用。</span><span class="sxs-lookup"><span data-stu-id="00823-131">Enabled.</span></span> <span data-ttu-id="00823-132">如果 MBAM 将可移动驱动器数据保存到 MBAM 密钥恢复服务器，则这是必需的。</span><span class="sxs-lookup"><span data-stu-id="00823-132">This is required if MBAM will save removable drive data to the MBAM Key Recovery server.</span></span>

    <span data-ttu-id="00823-133">固定驱动器</span><span class="sxs-lookup"><span data-stu-id="00823-133">Fixed Drive</span></span>

    <span data-ttu-id="00823-134">在固定驱动器上控制 BitLocker 的使用</span><span class="sxs-lookup"><span data-stu-id="00823-134">Control Use of BitLocker on fixed drives</span></span>

    <span data-ttu-id="00823-135">已启用。</span><span class="sxs-lookup"><span data-stu-id="00823-135">Enabled.</span></span> <span data-ttu-id="00823-136">如果 MBAM 将把固定的驱动器数据保存到 MBAM 密钥恢复服务器，则这是必需的。</span><span class="sxs-lookup"><span data-stu-id="00823-136">This is required if MBAM will save fixed drive data to the MBAM Key Recovery server.</span></span>

    <span data-ttu-id="00823-137">设置**选择如何恢复受 BitLocker 保护的驱动器**，并**允许数据恢复代理**。</span><span class="sxs-lookup"><span data-stu-id="00823-137">Set **Choose how BitLocker-protected drives can be recovered** and **Allow data recovery agent**.</span></span>



~~~
**Important**  
Depending on the policies that your organization decides to deploy, you may have to configure additional policies. See [Planning for MBAM 1.0 Group Policy Requirements](planning-for-mbam-10-group-policy-requirements.md) for Group Policy configuration details for all of the available MBAM GPO policy options.
~~~



## <span data-ttu-id="00823-138">相关主题</span><span class="sxs-lookup"><span data-stu-id="00823-138">Related topics</span></span>


[<span data-ttu-id="00823-139">部署 MBAM 1.0 组策略对象</span><span class="sxs-lookup"><span data-stu-id="00823-139">Deploying MBAM 1.0 Group Policy Objects</span></span>](deploying-mbam-10-group-policy-objects.md)









