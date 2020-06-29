---
title: MBAM 2.5 部署清单
description: MBAM 2.5 部署清单
author: dansimp
ms.assetid: 2ba7de17-e3a4-4798-99e0-cd1dc28c5b76
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 11609b3d6d44d62b032e35005e5d967ca6d4e83b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803247"
---
# <span data-ttu-id="689e7-103">MBAM 2.5 部署清单</span><span class="sxs-lookup"><span data-stu-id="689e7-103">MBAM 2.5 Deployment Checklist</span></span>


<span data-ttu-id="689e7-104">在使用独立拓扑的 Microsoft BitLocker 管理和监视（MBAM）部署期间，你可以使用此清单帮助你。</span><span class="sxs-lookup"><span data-stu-id="689e7-104">You can use this checklist to help you during Microsoft BitLocker Administration and Monitoring (MBAM) deployment with a Stand-alone topology.</span></span>

**<span data-ttu-id="689e7-105">注意</span><span class="sxs-lookup"><span data-stu-id="689e7-105">Note</span></span>**  
<span data-ttu-id="689e7-106">此清单列出了在部署 Microsoft BitLocker 管理和监视功能时要考虑的推荐步骤和高级列表项。</span><span class="sxs-lookup"><span data-stu-id="689e7-106">This checklist outlines the recommended steps and a high-level list of items to consider when you deploy Microsoft BitLocker Administration and Monitoring features.</span></span> <span data-ttu-id="689e7-107">我们建议您将此清单复制到电子表格程序中，并对其进行自定义以供使用。</span><span class="sxs-lookup"><span data-stu-id="689e7-107">We recommend that you copy this checklist into a spreadsheet program and customize it for your use.</span></span>



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
<th align="left"><span data-ttu-id="689e7-108">任务</span><span class="sxs-lookup"><span data-stu-id="689e7-108">Task</span></span></th>
<th align="left"><span data-ttu-id="689e7-109">引用</span><span class="sxs-lookup"><span data-stu-id="689e7-109">References</span></span></th>
<th align="left"><span data-ttu-id="689e7-110">注释</span><span class="sxs-lookup"><span data-stu-id="689e7-110">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="689e7-111">查看并完成所有计划步骤，以便为 MBAM 部署准备环境。</span><span class="sxs-lookup"><span data-stu-id="689e7-111">Review and complete all planning steps to prepare your environment for MBAM deployment.</span></span></p></td>
<td align="left"><p><a href="mbam-25-planning-checklist.md" data-raw-source="[MBAM 2.5 Planning Checklist](mbam-25-planning-checklist.md)"><span data-ttu-id="689e7-112">MBAM 2.5 规划清单</span><span class="sxs-lookup"><span data-stu-id="689e7-112">MBAM 2.5 Planning Checklist</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="689e7-113">查看受支持的配置信息，确保 MBAM 支持所选客户端和服务器计算机。</span><span class="sxs-lookup"><span data-stu-id="689e7-113">Review the supported configurations information to ensure that MBAM supports the selected client and server computers.</span></span></p></td>
<td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"><span data-ttu-id="689e7-114">MBAM 2.5 支持的配置</span><span class="sxs-lookup"><span data-stu-id="689e7-114">MBAM 2.5 Supported Configurations</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="689e7-115">安装 MBAM Server 软件。</span><span class="sxs-lookup"><span data-stu-id="689e7-115">Install the MBAM Server software.</span></span></p></td>
<td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)"><span data-ttu-id="689e7-116">安装 MBAM 2.5 服务器软件</span><span class="sxs-lookup"><span data-stu-id="689e7-116">Installing the MBAM 2.5 Server Software</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="689e7-117">配置 MBAM 服务器功能：</span><span class="sxs-lookup"><span data-stu-id="689e7-117">Configure the MBAM Server features:</span></span></p>
<ul>
<li><p><span data-ttu-id="689e7-118">合规性和审核数据库和恢复数据库</span><span class="sxs-lookup"><span data-stu-id="689e7-118">Compliance and Audit Database and Recovery Database</span></span></p></li>
<li><p><span data-ttu-id="689e7-119">报告</span><span class="sxs-lookup"><span data-stu-id="689e7-119">Reports</span></span></p></li>
<li><p><span data-ttu-id="689e7-120">Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="689e7-120">Web applications</span></span></p></li>
<li><p><span data-ttu-id="689e7-121">Configuration Manager 集成拓扑（仅在你通过此拓扑运行 MBAM 时才需要）</span><span class="sxs-lookup"><span data-stu-id="689e7-121">Configuration Manager Integration topology (needed only if you are running MBAM with this topology)</span></span></p></li>
</ul>
<div class="alert">
<strong><span data-ttu-id="689e7-122">注意</span><span class="sxs-lookup"><span data-stu-id="689e7-122">Note</span></span></strong><br/><p><span data-ttu-id="689e7-123">记下在其上配置每个功能的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="689e7-123">Note the names of the servers on which you configure each feature.</span></span> <span data-ttu-id="689e7-124">您将在整个配置过程中使用此信息。</span><span class="sxs-lookup"><span data-stu-id="689e7-124">You will use this information throughout the configuration process.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><a href="configuring-the-mbam-25-server-features.md" data-raw-source="[Configuring the MBAM 2.5 Server Features](configuring-the-mbam-25-server-features.md)"><span data-ttu-id="689e7-125">配置 MBAM 2.5 服务器功能</span><span class="sxs-lookup"><span data-stu-id="689e7-125">Configuring the MBAM 2.5 Server Features</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="689e7-126">验证 MBAM 配置。</span><span class="sxs-lookup"><span data-stu-id="689e7-126">Validate the MBAM configuration.</span></span></p></td>
<td align="left"><p><a href="validating-the-mbam-25-server-feature-configuration.md" data-raw-source="[Validating the MBAM 2.5 Server Feature Configuration](validating-the-mbam-25-server-feature-configuration.md)"><span data-ttu-id="689e7-127">验证 MBAM 2.5 服务器功能配置</span><span class="sxs-lookup"><span data-stu-id="689e7-127">Validating the MBAM 2.5 Server Feature Configuration</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="689e7-128">复制 MBAM 组策略模板并编辑组策略设置。</span><span class="sxs-lookup"><span data-stu-id="689e7-128">Copy the MBAM Group Policy Template and edit the Group Policy settings.</span></span></p></td>
<td align="left"><p><a href="copying-the-mbam-25-group-policy-templates.md" data-raw-source="[Copying the MBAM 2.5 Group Policy Templates](copying-the-mbam-25-group-policy-templates.md)"><span data-ttu-id="689e7-129">复制 MBAM 2.5 组策略模板 </a> 并 <a href="editing-the-mbam-25-group-policy-settings.md" data-raw-source="[Editing the MBAM 2.5 Group Policy Settings](editing-the-mbam-25-group-policy-settings.md)"> 编辑 MBAM 2.5 组策略设置</span><span class="sxs-lookup"><span data-stu-id="689e7-129">Copying the MBAM 2.5 Group Policy Templates</a> and <a href="editing-the-mbam-25-group-policy-settings.md" data-raw-source="[Editing the MBAM 2.5 Group Policy Settings](editing-the-mbam-25-group-policy-settings.md)">Editing the MBAM 2.5 Group Policy Settings</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="689e7-130">部署 MBAM 客户端软件。</span><span class="sxs-lookup"><span data-stu-id="689e7-130">Deploy the MBAM Client software.</span></span></p></td>
<td align="left"><p><a href="deploying-the-mbam-25-client.md" data-raw-source="[Deploying the MBAM 2.5 Client](deploying-the-mbam-25-client.md)"><span data-ttu-id="689e7-131">部署 MBAM 2.5 客户端</span><span class="sxs-lookup"><span data-stu-id="689e7-131">Deploying the MBAM 2.5 Client</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>




## <span data-ttu-id="689e7-132">相关主题</span><span class="sxs-lookup"><span data-stu-id="689e7-132">Related topics</span></span>


[<span data-ttu-id="689e7-133">部署 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="689e7-133">Deploying MBAM 2.5</span></span>](deploying-mbam-25.md)




## <span data-ttu-id="689e7-134">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="689e7-134">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="689e7-135">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="689e7-135">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="689e7-136">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="689e7-136">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>




