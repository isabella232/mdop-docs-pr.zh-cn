---
title: MBAM 1.0 部署清单
description: MBAM 1.0 部署清单
author: dansimp
ms.assetid: 7e00be23-36a0-4b0f-8663-3c4f2c71546d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 96725183af2cb4e3d86d3f42973452c598497773
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798070"
---
# <span data-ttu-id="94a2c-103">MBAM 1.0 部署清单</span><span class="sxs-lookup"><span data-stu-id="94a2c-103">MBAM 1.0 Deployment Checklist</span></span>


<span data-ttu-id="94a2c-104">此清单旨在帮助你部署 Microsoft BitLocker 管理和监视（MBAM）。</span><span class="sxs-lookup"><span data-stu-id="94a2c-104">This checklist is designed to facilitate your deployment of Microsoft BitLocker Administration and Monitoring (MBAM).</span></span>

**<span data-ttu-id="94a2c-105">注意</span><span class="sxs-lookup"><span data-stu-id="94a2c-105">Note</span></span>**  
<span data-ttu-id="94a2c-106">此清单列出了推荐的步骤，并提供了在部署 MBAM 功能时要考虑的项目的高级列表。</span><span class="sxs-lookup"><span data-stu-id="94a2c-106">This checklist outlines the recommended steps and provides a high-level list of items to consider when you deploy the MBAM features.</span></span> <span data-ttu-id="94a2c-107">我们建议你将此清单复制到电子表格程序中，并针对你的特定需求对其进行自定义。</span><span class="sxs-lookup"><span data-stu-id="94a2c-107">We recommend that you copy this checklist into a spreadsheet program and customize it for your specific needs.</span></span>



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left"><span data-ttu-id="94a2c-108">任务</span><span class="sxs-lookup"><span data-stu-id="94a2c-108">Task</span></span></th>
<th align="left"><span data-ttu-id="94a2c-109">引用</span><span class="sxs-lookup"><span data-stu-id="94a2c-109">References</span></span></th>
<th align="left"><span data-ttu-id="94a2c-110">注释</span><span class="sxs-lookup"><span data-stu-id="94a2c-110">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="94a2c-111">完成规划阶段以准备 MBAM 部署的计算环境。</span><span class="sxs-lookup"><span data-stu-id="94a2c-111">Complete the planning phase to prepare the computing environment for MBAM deployment.</span></span></p></td>
<td align="left"><p><a href="mbam-10-planning-checklist.md" data-raw-source="[MBAM 1.0 Planning Checklist](mbam-10-planning-checklist.md)"><span data-ttu-id="94a2c-112">MBAM 1.0 计划清单</span><span class="sxs-lookup"><span data-stu-id="94a2c-112">MBAM 1.0 Planning Checklist</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="94a2c-113">查看有关 MBAM 支持的配置的信息，确保所选客户端和服务器计算机支持 MBAM 功能安装。</span><span class="sxs-lookup"><span data-stu-id="94a2c-113">Review the information on MBAM supported configurations to make sure that your selected client and server computers are supported for MBAM feature installation.</span></span></p></td>
<td align="left"><p><a href="mbam-10-supported-configurations.md" data-raw-source="[MBAM 1.0 Supported Configurations](mbam-10-supported-configurations.md)"><span data-ttu-id="94a2c-114">MBAM 1.0 支持的配置</span><span class="sxs-lookup"><span data-stu-id="94a2c-114">MBAM 1.0 Supported Configurations</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="94a2c-115">按以下顺序运行 MBAM 安装程序以部署 MBAM 服务器功能：</span><span class="sxs-lookup"><span data-stu-id="94a2c-115">Run MBAM Setup to deploy MBAM Server features in the following order:</span></span></p>
<ol>
<li><p><span data-ttu-id="94a2c-116">恢复和硬件数据库</span><span class="sxs-lookup"><span data-stu-id="94a2c-116">Recovery and Hardware Database</span></span></p></li>
<li><p><span data-ttu-id="94a2c-117">合规性状态数据库</span><span class="sxs-lookup"><span data-stu-id="94a2c-117">Compliance Status Database</span></span></p></li>
<li><p><span data-ttu-id="94a2c-118">合规性审核和报告</span><span class="sxs-lookup"><span data-stu-id="94a2c-118">Compliance Audit and Reports</span></span></p></li>
<li><p><span data-ttu-id="94a2c-119">管理和监视服务器</span><span class="sxs-lookup"><span data-stu-id="94a2c-119">Administration and Monitoring Server</span></span></p></li>
<li><p><span data-ttu-id="94a2c-120">MBAM 组策略模板</span><span class="sxs-lookup"><span data-stu-id="94a2c-120">MBAM Group Policy Template</span></span></p></li>
</ol>
<div class="alert">
<strong><span data-ttu-id="94a2c-121">注意</span><span class="sxs-lookup"><span data-stu-id="94a2c-121">Note</span></span></strong><br/><p><span data-ttu-id="94a2c-122">跟踪安装每个功能的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="94a2c-122">Keep track of the names of the servers each feature is installed on.</span></span> <span data-ttu-id="94a2c-123">您将在整个安装过程中使用此信息。</span><span class="sxs-lookup"><span data-stu-id="94a2c-123">You will use this information throughout the installation process.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><a href="deploying-the-mbam-10-server-infrastructure.md" data-raw-source="[Deploying the MBAM 1.0 Server Infrastructure](deploying-the-mbam-10-server-infrastructure.md)"><span data-ttu-id="94a2c-124">部署 MBAM 1.0 服务器基础结构</span><span class="sxs-lookup"><span data-stu-id="94a2c-124">Deploying the MBAM 1.0 Server Infrastructure</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="94a2c-125">将在计划阶段创建的 Active Directory 域服务安全组添加到相应的服务器上的相应本地 MBAM 服务器功能管理员组。</span><span class="sxs-lookup"><span data-stu-id="94a2c-125">Add Active Directory Domain Services security groups created during the planning phase to the appropriate local MBAM Server feature administrators groups on the appropriate servers.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-10-administrator-roles.md" data-raw-source="[Planning for MBAM 1.0 Administrator Roles](planning-for-mbam-10-administrator-roles.md)"><span data-ttu-id="94a2c-126">规划 MBAM 1.0 管理员角色 </a> 以及 <a href="how-to-manage-mbam-administrator-roles-mbam-1.md" data-raw-source="[How to Manage MBAM Administrator Roles](how-to-manage-mbam-administrator-roles-mbam-1.md)"> 如何管理 MBAM 管理员角色</span><span class="sxs-lookup"><span data-stu-id="94a2c-126">Planning for MBAM 1.0 Administrator Roles</a> and <a href="how-to-manage-mbam-administrator-roles-mbam-1.md" data-raw-source="[How to Manage MBAM Administrator Roles](how-to-manage-mbam-administrator-roles-mbam-1.md)">How to Manage MBAM Administrator Roles</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="94a2c-127">创建和部署所需的 MBAM 组策略对象。</span><span class="sxs-lookup"><span data-stu-id="94a2c-127">Create and deploy the required MBAM Group Policy Objects.</span></span></p></td>
<td align="left"><p><a href="deploying-mbam-10-group-policy-objects.md" data-raw-source="[Deploying MBAM 1.0 Group Policy Objects](deploying-mbam-10-group-policy-objects.md)"><span data-ttu-id="94a2c-128">部署 MBAM 1.0 组策略对象</span><span class="sxs-lookup"><span data-stu-id="94a2c-128">Deploying MBAM 1.0 Group Policy Objects</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="94a2c-129">部署 MBAM 客户端软件。</span><span class="sxs-lookup"><span data-stu-id="94a2c-129">Deploy the MBAM Client software.</span></span></p></td>
<td align="left"><p><a href="deploying-the-mbam-10-client.md" data-raw-source="[Deploying the MBAM 1.0 Client](deploying-the-mbam-10-client.md)"><span data-ttu-id="94a2c-130">部署 MBAM 1.0 客户端</span><span class="sxs-lookup"><span data-stu-id="94a2c-130">Deploying the MBAM 1.0 Client</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="94a2c-131">相关主题</span><span class="sxs-lookup"><span data-stu-id="94a2c-131">Related topics</span></span>


[<span data-ttu-id="94a2c-132">部署 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="94a2c-132">Deploying MBAM 1.0</span></span>](deploying-mbam-10.md)









