---
title: 如何编辑 MBAM 2.0 GPO 设置
description: 如何编辑 MBAM 2.0 GPO 设置
author: dansimp
ms.assetid: f5ffa93d-b4d2-4317-8a1c-7d2be0264fe3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: aaf7c7aab4baba66513edbfa2489fbe53c97dda8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803498"
---
# <span data-ttu-id="79847-103">如何编辑 MBAM 2.0 GPO 设置</span><span class="sxs-lookup"><span data-stu-id="79847-103">How to Edit MBAM 2.0 GPO Settings</span></span>


<span data-ttu-id="79847-104">若要成功部署 Microsoft BitLocker 管理和监视（MBAM），首先需要确定你将在 Microsoft BitLocker 管理和监视的实现中使用的组策略。</span><span class="sxs-lookup"><span data-stu-id="79847-104">To successfully deploy Microsoft BitLocker Administration and Monitoring (MBAM), you first have to determine the Group Policies that you will use in your implementation of Microsoft BitLocker Administration and Monitoring.</span></span> <span data-ttu-id="79847-105">有关可用的不同策略的详细信息，请参阅[规划 MBAM 2.0 组策略要求](planning-for-mbam-20-group-policy-requirements-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="79847-105">See [Planning for MBAM 2.0 Group Policy Requirements](planning-for-mbam-20-group-policy-requirements-mbam-2.md) for more information on the different policies that are available.</span></span> <span data-ttu-id="79847-106">确定要使用的策略后，必须修改一个或多个组策略对象（GPO），其中包含 MBAM 的策略设置。</span><span class="sxs-lookup"><span data-stu-id="79847-106">After you have determined the policies that you are going to use, you then must modify one or more Group Policy Objects (GPO) that include the policy settings for MBAM.</span></span>

<span data-ttu-id="79847-107">你可以使用以下步骤配置基本的推荐 GPO 设置，以使 MBAM 能够管理组织的客户端计算机的 BitLocker 加密。</span><span class="sxs-lookup"><span data-stu-id="79847-107">You can use the following steps to configure the basic, recommended GPO settings to enable MBAM to manage BitLocker encryption for your organization’s client computers.</span></span>

**<span data-ttu-id="79847-108">编辑 MBAM 客户端 GPO 设置</span><span class="sxs-lookup"><span data-stu-id="79847-108">To Edit MBAM Client GPO Settings</span></span>**

1.  <span data-ttu-id="79847-109">在安装了 MBAM 组策略模板的计算机上，请确保启用 MBAM 服务。</span><span class="sxs-lookup"><span data-stu-id="79847-109">On a computer that has MBAM Group Policy template installed, make sure that MBAM services are enabled.</span></span>

2.  <span data-ttu-id="79847-110">在安装了 MBAM 组策略模板的计算机上使用组策略管理控制台（GPMC）或高级组策略管理（AGPM） MDOP 产品，选择 "**计算机配置**"，选择 "**策略**"，单击 "**管理模板**"，选择 " **Windows 组件**"，然后单击 " **MDOP MBAM" （BitLocker Management）**。</span><span class="sxs-lookup"><span data-stu-id="79847-110">Using the Group Policy Management Console (GPMC.msc) or the Advanced Group Policy Management (AGPM) MDOP product on a computer with the MBAM Group Policy template installed, select **Computer configuration**, choose **Policies**, click **Administrative Templates**, select **Windows Components**, and then click **MDOP MBAM (BitLocker Management)**.</span></span>

3.  <span data-ttu-id="79847-111">编辑在客户端计算机上启用 MBAM 客户端服务所需的组策略对象设置。</span><span class="sxs-lookup"><span data-stu-id="79847-111">Edit the Group Policy Object settings that are required to enable MBAM Client services on client computers.</span></span> <span data-ttu-id="79847-112">对于后面的表中的每个策略，选择 "**策略组**"，单击该**策略**，然后配置**设置**：</span><span class="sxs-lookup"><span data-stu-id="79847-112">For each policy in the table that follows, select **Policy Group**, click the **Policy**, and then configure the **Setting**:</span></span>

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="79847-113">策略组</span><span class="sxs-lookup"><span data-stu-id="79847-113">Policy Group</span></span></th>
    <th align="left"><span data-ttu-id="79847-114">策略</span><span class="sxs-lookup"><span data-stu-id="79847-114">Policy</span></span></th>
    <th align="left"><span data-ttu-id="79847-115">设置</span><span class="sxs-lookup"><span data-stu-id="79847-115">Setting</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="79847-116">客户端管理</span><span class="sxs-lookup"><span data-stu-id="79847-116">Client Management</span></span></p></td>
    <td align="left"><p><span data-ttu-id="79847-117">配置 MBAM 服务</span><span class="sxs-lookup"><span data-stu-id="79847-117">Configure MBAM Services</span></span></p></td>
    <td align="left"><p><span data-ttu-id="79847-118">已启用。</span><span class="sxs-lookup"><span data-stu-id="79847-118">Enabled.</span></span> <span data-ttu-id="79847-119">设置 <strong> MBAM 恢复和硬件服务终结点 </strong> ，并 <strong> 选择要存储的 BitLocker 恢复信息 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="79847-119">Set <strong>MBAM Recovery and Hardware service endpoint</strong> and <strong>Select BitLocker recovery information to store</strong>.</span></span> <span data-ttu-id="79847-120">设置 <strong> MBAM 合规性服务终结点 </strong> ，并在（分钟）内输入状态报告频率。</span><span class="sxs-lookup"><span data-stu-id="79847-120">Set <strong>MBAM compliance service endpoint</strong> and Enter status report frequency in (minutes).</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="79847-121">操作系统驱动器</span><span class="sxs-lookup"><span data-stu-id="79847-121">Operating System Drive</span></span></p></td>
    <td align="left"><p><span data-ttu-id="79847-122">操作系统驱动器加密设置</span><span class="sxs-lookup"><span data-stu-id="79847-122">Operating system drive encryption settings</span></span></p></td>
    <td align="left"><p><span data-ttu-id="79847-123">已启用。</span><span class="sxs-lookup"><span data-stu-id="79847-123">Enabled.</span></span> <span data-ttu-id="79847-124"><strong>为操作系统驱动器设置选择保护程序 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="79847-124">Set <strong>Select protector for operating system drive</strong>.</span></span> <span data-ttu-id="79847-125">将操作系统驱动器数据保存到 MBAMKey 恢复服务器所需。</span><span class="sxs-lookup"><span data-stu-id="79847-125">Required to save operating system drive data to the MBAMKey Recovery server.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="79847-126">可移动驱动器</span><span class="sxs-lookup"><span data-stu-id="79847-126">Removable Drive</span></span></p></td>
    <td align="left"><p><span data-ttu-id="79847-127">控制可移动驱动器上的 BitLocker 的使用</span><span class="sxs-lookup"><span data-stu-id="79847-127">Control Use of BitLocker on removable drives</span></span></p></td>
    <td align="left"><p><span data-ttu-id="79847-128">已启用。</span><span class="sxs-lookup"><span data-stu-id="79847-128">Enabled.</span></span> <span data-ttu-id="79847-129">如果 MBAM 会将可移动驱动器数据保存到 MBAM 密钥恢复服务器，则为必需。</span><span class="sxs-lookup"><span data-stu-id="79847-129">Required if MBAM will save removable drive data to the MBAM Key Recovery server.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="79847-130">固定驱动器</span><span class="sxs-lookup"><span data-stu-id="79847-130">Fixed Drive</span></span></p></td>
    <td align="left"><p><span data-ttu-id="79847-131">在固定驱动器上控制 BitLocker 的使用</span><span class="sxs-lookup"><span data-stu-id="79847-131">Control Use of BitLocker on fixed drives</span></span></p></td>
    <td align="left"><p><span data-ttu-id="79847-132">已启用。</span><span class="sxs-lookup"><span data-stu-id="79847-132">Enabled.</span></span> <span data-ttu-id="79847-133">如果 MBAM 会将固定驱动器数据保存到 MBAM 密钥恢复服务器，则是必需的。</span><span class="sxs-lookup"><span data-stu-id="79847-133">Required if MBAM will save fixed drive data to the MBAM Key Recovery server.</span></span></p>
    <p><span data-ttu-id="79847-134">设置 <strong> 选择如何恢复受 BitLocker 保护的驱动器 </strong> ，并 <strong> 允许数据恢复代理 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="79847-134">Set <strong>Choose how BitLocker-protected drives can be recovered</strong> and <strong>Allow data recovery agent</strong>.</span></span></p></td>
    </tr>
    </tbody>
    </table>



~~~
**Important**  
Depending on the policies that your organization decides to deploy, you may have to configure additional policies. See [Planning for MBAM 2.0 Group Policy Requirements](planning-for-mbam-20-group-policy-requirements-mbam-2.md) for Group Policy configuration details for all of the available MBAM GPO policy options.
~~~



## <span data-ttu-id="79847-135">相关主题</span><span class="sxs-lookup"><span data-stu-id="79847-135">Related topics</span></span>


[<span data-ttu-id="79847-136">部署 MBAM 2.0 组策略对象</span><span class="sxs-lookup"><span data-stu-id="79847-136">Deploying MBAM 2.0 Group Policy Objects</span></span>](deploying-mbam-20-group-policy-objects-mbam-2.md)









