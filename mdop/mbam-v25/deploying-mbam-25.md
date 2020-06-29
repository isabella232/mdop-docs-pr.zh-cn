---
title: 部署 MBAM 2.5
description: 部署 MBAM 2.5
author: dansimp
ms.assetid: 45403607-1f4d-42fe-8413-0d4da01808a6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0cfa0a190530186211cd96884b2e32e9c65881f1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803937"
---
# <span data-ttu-id="4e5d8-103">部署 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="4e5d8-103">Deploying MBAM 2.5</span></span>


<span data-ttu-id="4e5d8-104">使用此信息可以确定部署和配置 Microsoft BitLocker 管理和监视（MBAM）2.5 服务器功能以升级到以前版本的 MBAM 2.5 或删除 MBAM 服务器功能时可以遵循的过程。</span><span class="sxs-lookup"><span data-stu-id="4e5d8-104">Use this information to identify the procedures you can follow to deploy and configure Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 Server features to upgrade to MBAM 2.5 from previous versions, or to remove MBAM Server features.</span></span>

## <span data-ttu-id="4e5d8-105">部署信息</span><span class="sxs-lookup"><span data-stu-id="4e5d8-105">Deployment information</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4e5d8-106">主题说明</span><span class="sxs-lookup"><span data-stu-id="4e5d8-106">Topic description</span></span></th>
<th align="left"><span data-ttu-id="4e5d8-107">主题链接</span><span class="sxs-lookup"><span data-stu-id="4e5d8-107">Links to topics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><ul>
<li><p><span data-ttu-id="4e5d8-108">部署拓扑选项。</span><span class="sxs-lookup"><span data-stu-id="4e5d8-108">Deployment topology options.</span></span></p></li>
<li><p><span data-ttu-id="4e5d8-109">如何安装 MBAM 服务器软件。</span><span class="sxs-lookup"><span data-stu-id="4e5d8-109">How to install the MBAM Server software.</span></span></p></li>
<li><p><span data-ttu-id="4e5d8-110">如何配置 MBAM 服务器功能。</span><span class="sxs-lookup"><span data-stu-id="4e5d8-110">How to configure the MBAM Server features.</span></span></p></li>
</ul></td>
<td align="left"><p><a href="deploying-the-mbam-25-server-infrastructure.md" data-raw-source="[Deploying the MBAM 2.5 Server Infrastructure](deploying-the-mbam-25-server-infrastructure.md)"><span data-ttu-id="4e5d8-111">部署 MBAM 2.5 服务器基础结构</span><span class="sxs-lookup"><span data-stu-id="4e5d8-111">Deploying the MBAM 2.5 Server Infrastructure</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4e5d8-112">如何下载和部署 MBAM 组策略模板，这些模板是管理企业中的 MBAM 客户端和 BitLocker 加密策略所必需的。</span><span class="sxs-lookup"><span data-stu-id="4e5d8-112">How to download and deploy the MBAM Group Policy Templates, which are required to manage MBAM Clients and BitLocker encryption policies in the enterprise.</span></span></p></td>
<td align="left"><p><a href="deploying-mbam-25-group-policy-objects.md" data-raw-source="[Deploying MBAM 2.5 Group Policy Objects](deploying-mbam-25-group-policy-objects.md)"><span data-ttu-id="4e5d8-113">部署 MBAM 2.5 组策略对象</span><span class="sxs-lookup"><span data-stu-id="4e5d8-113">Deploying MBAM 2.5 Group Policy Objects</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4e5d8-114">如何使用 MBAM 客户端 Windows 安装程序文件部署 MBAM 客户端软件。</span><span class="sxs-lookup"><span data-stu-id="4e5d8-114">How to use the MBAM Client Windows Installer files to deploy the MBAM Client software.</span></span></p></td>
<td align="left"><p><a href="deploying-the-mbam-25-client.md" data-raw-source="[Deploying the MBAM 2.5 Client](deploying-the-mbam-25-client.md)"><span data-ttu-id="4e5d8-115">部署 MBAM 2.5 客户端</span><span class="sxs-lookup"><span data-stu-id="4e5d8-115">Deploying the MBAM 2.5 Client</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4e5d8-116">可帮助您部署 MBAM 服务器功能和 MBAM 客户端的清单。</span><span class="sxs-lookup"><span data-stu-id="4e5d8-116">Checklist that can assist you in deploying the MBAM Server features and MBAM Client.</span></span></p></td>
<td align="left"><p><a href="mbam-25-deployment-checklist.md" data-raw-source="[MBAM 2.5 Deployment Checklist](mbam-25-deployment-checklist.md)"><span data-ttu-id="4e5d8-117">MBAM 2.5 部署清单</span><span class="sxs-lookup"><span data-stu-id="4e5d8-117">MBAM 2.5 Deployment Checklist</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4e5d8-118">如何从以前的版本升级 MBAM。</span><span class="sxs-lookup"><span data-stu-id="4e5d8-118">How to upgrade MBAM from previous versions.</span></span></p></td>
<td align="left"><p><a href="upgrading-to-mbam-25-or-mbam-25-sp1-from-previous-versions.md" data-raw-source="[Upgrading to MBAM 2.5 or MBAM 2.5 SP1 from Previous Versions](upgrading-to-mbam-25-or-mbam-25-sp1-from-previous-versions.md)"><span data-ttu-id="4e5d8-119">从先前版本升级到 MBAM 2.5 或 MBAM 2.5 SP1</span><span class="sxs-lookup"><span data-stu-id="4e5d8-119">Upgrading to MBAM 2.5 or MBAM 2.5 SP1 from Previous Versions</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4e5d8-120">如何删除 MBAM 服务器功能或软件。</span><span class="sxs-lookup"><span data-stu-id="4e5d8-120">How to remove MBAM Server features or software.</span></span></p></td>
<td align="left"><p><a href="removing-mbam-server-features-or-software.md" data-raw-source="[Removing MBAM Server Features or Software](removing-mbam-server-features-or-software.md)"><span data-ttu-id="4e5d8-121">删除 MBAM 服务器功能或软件</span><span class="sxs-lookup"><span data-stu-id="4e5d8-121">Removing MBAM Server Features or Software</span></span></a></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="4e5d8-122">用于部署 MBAM 的其他资源</span><span class="sxs-lookup"><span data-stu-id="4e5d8-122">Other resources for deploying MBAM</span></span>


[<span data-ttu-id="4e5d8-123">Microsoft BitLocker 管理和监控 2.5</span><span class="sxs-lookup"><span data-stu-id="4e5d8-123">Microsoft BitLocker Administration and Monitoring 2.5</span></span>](index.md)

[<span data-ttu-id="4e5d8-124">MBAM 2.5 入门</span><span class="sxs-lookup"><span data-stu-id="4e5d8-124">Getting Started with MBAM 2.5</span></span>](getting-started-with-mbam-25.md)

[<span data-ttu-id="4e5d8-125">规划 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="4e5d8-125">Planning for MBAM 2.5</span></span>](planning-for-mbam-25.md)

[<span data-ttu-id="4e5d8-126">MBAM 2.5 的操作</span><span class="sxs-lookup"><span data-stu-id="4e5d8-126">Operations for MBAM 2.5</span></span>](operations-for-mbam-25.md)

[<span data-ttu-id="4e5d8-127">MBAM 2.5 故障排除</span><span class="sxs-lookup"><span data-stu-id="4e5d8-127">Troubleshooting MBAM 2.5</span></span>](troubleshooting-mbam-25.md)

[<span data-ttu-id="4e5d8-128">MBAM 2.5 的技术参考</span><span class="sxs-lookup"><span data-stu-id="4e5d8-128">Technical Reference for MBAM 2.5</span></span>](technical-reference-for-mbam-25.md)

[<span data-ttu-id="4e5d8-129">在独立配置中部署 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="4e5d8-129">Deploying MBAM 2.5 in a stand-alone configuration</span></span>](https://support.microsoft.com/kb/3046555)

## <span data-ttu-id="4e5d8-130">已获得 MBAM 的建议？</span><span class="sxs-lookup"><span data-stu-id="4e5d8-130">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="4e5d8-131">在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="4e5d8-131">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="4e5d8-132">对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="4e5d8-132">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>

 

 





