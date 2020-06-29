---
title: App-V 预安装清单
description: App-V 预安装清单
author: dansimp
ms.assetid: 3af609b1-2c09-4edb-b083-b913b6d5e8c4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 70e71d3dea02daeadedb4cff78c58302ac743dda
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802356"
---
# <span data-ttu-id="b84da-103">App-V 预安装清单</span><span class="sxs-lookup"><span data-stu-id="b84da-103">App-V Pre-Installation Checklist</span></span>


<span data-ttu-id="b84da-104">下面的清单旨在提供要考虑的项目的高级列表，并概括介绍在安装 Microsoft Application Virtualization （app-v）服务器之前应执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="b84da-104">The following checklist is intended to provide a high-level list of items to consider and outlines the steps you should take before you install the Microsoft Application Virtualization (App-V) servers.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b84da-105">步骤</span><span class="sxs-lookup"><span data-stu-id="b84da-105">Step</span></span></th>
<th align="left"><span data-ttu-id="b84da-106">参考</span><span class="sxs-lookup"><span data-stu-id="b84da-106">Reference</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b84da-107">确保你的计算环境满足 App-v 所需的支持配置。</span><span class="sxs-lookup"><span data-stu-id="b84da-107">Ensure your computing environment meets the supported configurations required for App-V.</span></span></p></td>
<td align="left"><p><a href="application-virtualization-deployment-requirements.md" data-raw-source="[Application Virtualization Deployment Requirements](application-virtualization-deployment-requirements.md)"><span data-ttu-id="b84da-108">Application Virtualization 部署要求</span><span class="sxs-lookup"><span data-stu-id="b84da-108">Application Virtualization Deployment Requirements</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b84da-109">配置必要的 Active Directory 组和帐户。</span><span class="sxs-lookup"><span data-stu-id="b84da-109">Configure the necessary Active Directory groups and accounts.</span></span></p></td>
<td align="left"><p><a href="configuring-prerequisite-groups-in-active-directory-for-app-v.md" data-raw-source="[Configuring Prerequisite Groups in Active Directory for App-V](configuring-prerequisite-groups-in-active-directory-for-app-v.md)"><span data-ttu-id="b84da-110">在 Active Directory 中为 App-V 配置必备组</span><span class="sxs-lookup"><span data-stu-id="b84da-110">Configuring Prerequisite Groups in Active Directory for App-V</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b84da-111">在运行 IIS 的服务器上配置 Internet 信息服务（IIS）设置。</span><span class="sxs-lookup"><span data-stu-id="b84da-111">Configure the Internet Information Services (IIS) settings on the server that is running IIS.</span></span></p></td>
<td align="left"><p><a href="how-to-configure-windows-server-2008-for-app-v-management-servers.md" data-raw-source="[How to Configure Windows Server 2008 for App-V Management Servers](how-to-configure-windows-server-2008-for-app-v-management-servers.md)"><span data-ttu-id="b84da-112">如何为 App-V Management Server 配置 Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="b84da-112">How to Configure Windows Server 2008 for App-V Management Servers</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b84da-113">将运行 IIS 的服务器配置为受信任的委派。</span><span class="sxs-lookup"><span data-stu-id="b84da-113">Configure the server that is running IIS to be trusted for delegation.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="b84da-114">注意</span><span class="sxs-lookup"><span data-stu-id="b84da-114">Note</span></span></strong><br/><p><span data-ttu-id="b84da-115">只有当你使用分布式系统体系结构安装 app-v 管理服务器（即，如果你在不同计算机上安装了 app-v 管理控制台、管理 Web 服务和数据库）时，此操作才是必需的。</span><span class="sxs-lookup"><span data-stu-id="b84da-115">This is required only if you are installing the App-V Management Server by using a distributed system architecture, that is, if you install the App-V Management Console, the Management Web Service, and the database on different computers.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><a href="how-to-configure-the-server-to-be-trusted-for-delegation.md" data-raw-source="[How to Configure the Server to be Trusted for Delegation](how-to-configure-the-server-to-be-trusted-for-delegation.md)"><span data-ttu-id="b84da-116">如何将服务器配置为受信任以进行委派</span><span class="sxs-lookup"><span data-stu-id="b84da-116">How to Configure the Server to be Trusted for Delegation</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b84da-117">安装 Microsoft SQL Server 2008。</span><span class="sxs-lookup"><span data-stu-id="b84da-117">Install Microsoft SQL Server 2008.</span></span></p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=181924" data-raw-source="[Install SQL Server 2008](https://go.microsoft.com/fwlink/?LinkId=181924)"><span data-ttu-id="b84da-118">安装 SQL Server 2008 </a> （ <a href="https://go.microsoft.com/fwlink/?LinkId=181924" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=181924"> https://go.microsoft.com/fwlink/?LinkId=181924 </a> ）。</span><span class="sxs-lookup"><span data-stu-id="b84da-118">Install SQL Server 2008</a> (<a href="https://go.microsoft.com/fwlink/?LinkId=181924" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=181924">https://go.microsoft.com/fwlink/?LinkId=181924</a>).</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="b84da-119">相关主题</span><span class="sxs-lookup"><span data-stu-id="b84da-119">Related topics</span></span>


[<span data-ttu-id="b84da-120">Application Virtualization 部署和升级清单</span><span class="sxs-lookup"><span data-stu-id="b84da-120">Application Virtualization Deployment and Upgrade Checklists</span></span>](application-virtualization-deployment-and-upgrade-checklists.md)

[<span data-ttu-id="b84da-121">App-V 安装清单</span><span class="sxs-lookup"><span data-stu-id="b84da-121">App-V Installation Checklist</span></span>](app-v-installation-checklist.md)









