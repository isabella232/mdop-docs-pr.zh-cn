---
title: 编辑 MBAM 2.5 组策略设置
description: 编辑 MBAM 2.5 组策略设置
author: dansimp
ms.assetid: a50b6b0c-6818-4419-8447-d0520a533dba
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0f6d180cba6dc721ff7de1607d57f90184303d88
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798085"
---
# <span data-ttu-id="ae929-103">编辑 MBAM 2.5 组策略设置</span><span class="sxs-lookup"><span data-stu-id="ae929-103">Editing the MBAM 2.5 Group Policy Settings</span></span>


<span data-ttu-id="ae929-104">若要成功部署 Microsoft BitLocker 管理和监视（MBAM），您必须：</span><span class="sxs-lookup"><span data-stu-id="ae929-104">To successfully deploy Microsoft BitLocker Administration and Monitoring (MBAM), you have to:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ae929-105">任务</span><span class="sxs-lookup"><span data-stu-id="ae929-105">Task</span></span></th>
<th align="left"><span data-ttu-id="ae929-106">详细信息</span><span class="sxs-lookup"><span data-stu-id="ae929-106">More information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ae929-107">复制 MBAM 2.5 组策略模板。</span><span class="sxs-lookup"><span data-stu-id="ae929-107">Copy the MBAM 2.5 Group Policy Templates.</span></span></p></td>
<td align="left"><p><a href="copying-the-mbam-25-group-policy-templates.md" data-raw-source="[Copying the MBAM 2.5 Group Policy Templates](copying-the-mbam-25-group-policy-templates.md)"><span data-ttu-id="ae929-108">复制 MBAM 2.5 组策略模板</span><span class="sxs-lookup"><span data-stu-id="ae929-108">Copying the MBAM 2.5 Group Policy Templates</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ae929-109">确定要在 MBAM 实现中使用的组策略对象（Gpo）。</span><span class="sxs-lookup"><span data-stu-id="ae929-109">Determine which Group Policy Objects (GPOs) you want to use in your MBAM implementation.</span></span> <span data-ttu-id="ae929-110">根据您的组织的需要，您可能必须配置其他组策略设置。</span><span class="sxs-lookup"><span data-stu-id="ae929-110">Based on the needs of your organization, you might have to configure additional Group Policy settings.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-25-group-policy-requirements.md" data-raw-source="[Planning for MBAM 2.5 Group Policy Requirements](planning-for-mbam-25-group-policy-requirements.md)"><span data-ttu-id="ae929-111">规划 MBAM 2.5 组策略要求 </a> -包含对 gpo 的描述</span><span class="sxs-lookup"><span data-stu-id="ae929-111">Planning for MBAM 2.5 Group Policy Requirements</a> – contains descriptions of the GPOs</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ae929-112">为您的组织设置组策略设置。</span><span class="sxs-lookup"><span data-stu-id="ae929-112">Set the Group Policy settings for your organization.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="ae929-113">**重要提示** 请勿更改**BitLocker 驱动器加密**节点中的组策略设置，否则 MBAM 将无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="ae929-113">**Important** Do not change the Group Policy settings in the **BitLocker Drive Encryption** node, or MBAM will not work correctly.</span></span> <span data-ttu-id="ae929-114">在**MDOP MBAM （BitLocker Management）** 节点中配置组策略设置时，MBAM 会自动为你配置**BitLocker 驱动器加密**设置。</span><span class="sxs-lookup"><span data-stu-id="ae929-114">When you configure the Group Policy settings in the **MDOP MBAM (BitLocker Management)** node, MBAM automatically configures the **BitLocker Drive Encryption** settings for you.</span></span>

 

**<span data-ttu-id="ae929-115">编辑 MBAM 客户端组策略设置</span><span class="sxs-lookup"><span data-stu-id="ae929-115">To edit MBAM Client Group Policy settings</span></span>**

1.  <span data-ttu-id="ae929-116">在安装了 MBAM 组策略模板的计算机上，请确保启用 MBAM 服务。</span><span class="sxs-lookup"><span data-stu-id="ae929-116">On a computer that has the MBAM Group Policy Templates installed, make sure that MBAM Services are enabled.</span></span>

2.  <span data-ttu-id="ae929-117">在安装了 MBAM 组策略模板的计算机上使用组策略管理控制台（GPMC）或 Microsoft 高级组策略管理 MDOP 产品，选择 "**计算机配置** &gt; **策略**" &gt; **管理模板** &gt; **Windows 组件** &gt; **MDOP MBAM （BitLocker Management）**。</span><span class="sxs-lookup"><span data-stu-id="ae929-117">Using the Group Policy Management Console (GPMC.msc) or the Microsoft Advanced Group Policy Management MDOP product on a computer with the MBAM Group Policy Templates installed, select **Computer configuration** &gt; **Policies** &gt; **Administrative Templates** &gt; **Windows Components** &gt; **MDOP MBAM (BitLocker Management)**.</span></span>

3.  <span data-ttu-id="ae929-118">编辑在客户端计算机上启用 MBAM 客户端服务所需的组策略设置。</span><span class="sxs-lookup"><span data-stu-id="ae929-118">Edit the Group Policy settings that are required to enable MBAM Client services on client computers.</span></span> <span data-ttu-id="ae929-119">对于下表中的每个策略，选择 "**策略组**"，单击所需的**策略**，然后配置设置。</span><span class="sxs-lookup"><span data-stu-id="ae929-119">For each policy in the following table, select **Policy Group**, click the **Policy** you want, and then configure the settings.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="ae929-120">策略组</span><span class="sxs-lookup"><span data-stu-id="ae929-120">Policy Group</span></span></th>
    <th align="left"><span data-ttu-id="ae929-121">策略</span><span class="sxs-lookup"><span data-stu-id="ae929-121">Policy</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="ae929-122">客户端管理</span><span class="sxs-lookup"><span data-stu-id="ae929-122">Client Management</span></span></p></td>
    <td align="left"><p><span data-ttu-id="ae929-123">配置 MBAM 服务</span><span class="sxs-lookup"><span data-stu-id="ae929-123">Configure MBAM Services</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="ae929-124">操作系统驱动器</span><span class="sxs-lookup"><span data-stu-id="ae929-124">Operating System Drive</span></span></p></td>
    <td align="left"><p><span data-ttu-id="ae929-125">操作系统驱动器加密设置</span><span class="sxs-lookup"><span data-stu-id="ae929-125">Operating system drive encryption settings</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="ae929-126">可移动驱动器</span><span class="sxs-lookup"><span data-stu-id="ae929-126">Removable Drive</span></span></p></td>
    <td align="left"><p><span data-ttu-id="ae929-127">控制可移动驱动器上的 BitLocker 的使用</span><span class="sxs-lookup"><span data-stu-id="ae929-127">Control use of BitLocker on removable drives</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="ae929-128">固定驱动器</span><span class="sxs-lookup"><span data-stu-id="ae929-128">Fixed Drive</span></span></p></td>
    <td align="left"><p><span data-ttu-id="ae929-129">在固定驱动器上控制 BitLocker 的使用</span><span class="sxs-lookup"><span data-stu-id="ae929-129">Control use of BitLocker on fixed drives</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

## <span data-ttu-id="ae929-130">相关主题</span><span class="sxs-lookup"><span data-stu-id="ae929-130">Related topics</span></span>


[<span data-ttu-id="ae929-131">规划 MBAM 2.5 组策略要求</span><span class="sxs-lookup"><span data-stu-id="ae929-131">Planning for MBAM 2.5 Group Policy Requirements</span></span>](planning-for-mbam-25-group-policy-requirements.md)

[<span data-ttu-id="ae929-132">复制 MBAM 2.5 组策略模板</span><span class="sxs-lookup"><span data-stu-id="ae929-132">Copying the MBAM 2.5 Group Policy Templates</span></span>](copying-the-mbam-25-group-policy-templates.md)

 
## <span data-ttu-id="ae929-133">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="ae929-133">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="ae929-134">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="ae929-134">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="ae929-135">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="ae929-135">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>
 





