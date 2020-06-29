---
title: MBAM 2.0 部署清单
description: MBAM 2.0 部署清单
author: dansimp
ms.assetid: 7905d31d-f21c-4683-b9c4-95b815e08fab
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5d8d0ce1a3ff48d4bf2f84e61b4a578b170264a0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803968"
---
# <span data-ttu-id="d41bf-103">MBAM 2.0 部署清单</span><span class="sxs-lookup"><span data-stu-id="d41bf-103">MBAM 2.0 Deployment Checklist</span></span>


<span data-ttu-id="d41bf-104">此清单可用于在使用独立拓扑的 Microsoft BitLocker 管理和监视（MBAM）部署期间帮助你。</span><span class="sxs-lookup"><span data-stu-id="d41bf-104">This checklist can be used to help you during Microsoft BitLocker Administration and Monitoring (MBAM) deployment with a Stand-alone topology.</span></span>

**<span data-ttu-id="d41bf-105">注意</span><span class="sxs-lookup"><span data-stu-id="d41bf-105">Note</span></span>**  
<span data-ttu-id="d41bf-106">此清单列出了在部署 Microsoft BitLocker 管理和监视功能时要考虑的推荐步骤和高级列表。</span><span class="sxs-lookup"><span data-stu-id="d41bf-106">This checklist outlines the recommended steps and a high-level list of items to consider when deploying Microsoft BitLocker Administration and Monitoring features.</span></span> <span data-ttu-id="d41bf-107">建议将此清单复制到电子表格程序中，然后对其进行自定义以供使用。</span><span class="sxs-lookup"><span data-stu-id="d41bf-107">It is recommended that you copy this checklist into a spreadsheet program and customize it for your use.</span></span>



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
<th align="left"><span data-ttu-id="d41bf-108">任务</span><span class="sxs-lookup"><span data-stu-id="d41bf-108">Task</span></span></th>
<th align="left"><span data-ttu-id="d41bf-109">引用</span><span class="sxs-lookup"><span data-stu-id="d41bf-109">References</span></span></th>
<th align="left"><span data-ttu-id="d41bf-110">注释</span><span class="sxs-lookup"><span data-stu-id="d41bf-110">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="d41bf-111">完成规划阶段以准备 MBAM 部署的计算环境。</span><span class="sxs-lookup"><span data-stu-id="d41bf-111">Complete the planning phase to prepare the computing environment for MBAM deployment.</span></span></p></td>
<td align="left"><p><a href="mbam-20-planning-checklist-mbam-2.md" data-raw-source="[MBAM 2.0 Planning Checklist](mbam-20-planning-checklist-mbam-2.md)"><span data-ttu-id="d41bf-112">MBAM 2.0 计划清单</span><span class="sxs-lookup"><span data-stu-id="d41bf-112">MBAM 2.0 Planning Checklist</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="d41bf-113">查看 MBAM 支持的配置信息，确保所选客户端和服务器计算机支持 MBAM 功能安装。</span><span class="sxs-lookup"><span data-stu-id="d41bf-113">Review the MBAM supported configurations information to make sure selected client and server computers are supported for MBAM feature installation.</span></span></p></td>
<td align="left"><p><a href="mbam-20-supported-configurations-mbam-2.md" data-raw-source="[MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md)"><span data-ttu-id="d41bf-114">MBAM 2.0 支持的配置</span><span class="sxs-lookup"><span data-stu-id="d41bf-114">MBAM 2.0 Supported Configurations</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="d41bf-115">按以下顺序运行 MBAM 安装程序以部署 MBAM 服务器功能：</span><span class="sxs-lookup"><span data-stu-id="d41bf-115">Run MBAM Setup to deploy MBAM Server features in the following order:</span></span></p>
<ol>
<li><p><span data-ttu-id="d41bf-116">恢复数据库</span><span class="sxs-lookup"><span data-stu-id="d41bf-116">Recovery Database</span></span></p></li>
<li><p><span data-ttu-id="d41bf-117">合规性和审核数据库</span><span class="sxs-lookup"><span data-stu-id="d41bf-117">Compliance and Audit Database</span></span></p></li>
<li><p><span data-ttu-id="d41bf-118">合规性审核和报告</span><span class="sxs-lookup"><span data-stu-id="d41bf-118">Compliance Audit and Reports</span></span></p></li>
<li><p><span data-ttu-id="d41bf-119">自助服务服务器</span><span class="sxs-lookup"><span data-stu-id="d41bf-119">Self-Service Server</span></span></p></li>
<li><p><span data-ttu-id="d41bf-120">管理和监视服务器</span><span class="sxs-lookup"><span data-stu-id="d41bf-120">Administration and Monitoring Server</span></span></p></li>
<li><p><span data-ttu-id="d41bf-121">MBAM 组策略模板</span><span class="sxs-lookup"><span data-stu-id="d41bf-121">MBAM Group Policy template</span></span></p></li>
</ol>
<div class="alert">
<strong><span data-ttu-id="d41bf-122">注意</span><span class="sxs-lookup"><span data-stu-id="d41bf-122">Note</span></span></strong><br/><p><span data-ttu-id="d41bf-123">跟踪安装每个功能的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="d41bf-123">Keep track of the names of the servers each feature is installed on.</span></span> <span data-ttu-id="d41bf-124">此信息将在整个安装过程中使用。</span><span class="sxs-lookup"><span data-stu-id="d41bf-124">This information will be used throughout the installation process.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><a href="deploying-the-mbam-20-server-infrastructure-mbam-2.md" data-raw-source="[Deploying the MBAM 2.0 Server Infrastructure](deploying-the-mbam-20-server-infrastructure-mbam-2.md)"><span data-ttu-id="d41bf-125">部署 MBAM 2.0 服务器基础结构</span><span class="sxs-lookup"><span data-stu-id="d41bf-125">Deploying the MBAM 2.0 Server Infrastructure</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="d41bf-126">将在计划阶段创建的 Active Directory 域服务安全组添加到相应的本地 MBAM 服务器功能管理员组（在相应的服务器上）。</span><span class="sxs-lookup"><span data-stu-id="d41bf-126">Add Active Directory Domain Services security groups created during the planning phase to the appropriate local MBAM Server feature administrators groups on appropriate servers.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-20-administrator-roles-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Administrator Roles](planning-for-mbam-20-administrator-roles-mbam-2.md)"><span data-ttu-id="d41bf-127">规划 MBAM 2.0 管理员角色 </a> 以及 <a href="how-to-manage-mbam-administrator-roles-mbam-2.md" data-raw-source="[How to Manage MBAM Administrator Roles](how-to-manage-mbam-administrator-roles-mbam-2.md)"> 如何管理 MBAM 管理员角色</span><span class="sxs-lookup"><span data-stu-id="d41bf-127">Planning for MBAM 2.0 Administrator Roles</a> and <a href="how-to-manage-mbam-administrator-roles-mbam-2.md" data-raw-source="[How to Manage MBAM Administrator Roles](how-to-manage-mbam-administrator-roles-mbam-2.md)">How to Manage MBAM Administrator Roles</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="d41bf-128">创建和部署所需的 MBAM 组策略对象。</span><span class="sxs-lookup"><span data-stu-id="d41bf-128">Create and deploy required MBAM Group Policy Objects.</span></span></p></td>
<td align="left"><p><a href="deploying-mbam-20-group-policy-objects-mbam-2.md" data-raw-source="[Deploying MBAM 2.0 Group Policy Objects](deploying-mbam-20-group-policy-objects-mbam-2.md)"><span data-ttu-id="d41bf-129">部署 MBAM 2.0 组策略对象</span><span class="sxs-lookup"><span data-stu-id="d41bf-129">Deploying MBAM 2.0 Group Policy Objects</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="d41bf-130">部署 MBAM 客户端软件。</span><span class="sxs-lookup"><span data-stu-id="d41bf-130">Deploy the MBAM Client software.</span></span></p></td>
<td align="left"><p><a href="deploying-the-mbam-20-client-mbam-2.md" data-raw-source="[Deploying the MBAM 2.0 Client](deploying-the-mbam-20-client-mbam-2.md)"><span data-ttu-id="d41bf-131">部署 MBAM 2.0 客户端</span><span class="sxs-lookup"><span data-stu-id="d41bf-131">Deploying the MBAM 2.0 Client</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="d41bf-132">相关主题</span><span class="sxs-lookup"><span data-stu-id="d41bf-132">Related topics</span></span>


[<span data-ttu-id="d41bf-133">部署 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="d41bf-133">Deploying MBAM 2.0</span></span>](deploying-mbam-20-mbam-2.md)









