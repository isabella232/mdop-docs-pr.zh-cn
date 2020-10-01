---
title: 从 MBAM 2.5 升级到 MBAM 2.5 SP1
description: 从 MBAM 2.5 升级到 MBAM 2.5 SP1
author: dansimp
ms.assetid: ''
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 2/16/2018
ms.openlocfilehash: 330ded822dd9da96a1c33eabcb31d744044dc28e
ms.sourcegitcommit: ae34c5cb5e7979b472b257a4691142e493d5d6fe
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2020
ms.locfileid: "11091617"
---
# <span data-ttu-id="11d30-103">从 MBAM 2.5 升级到 MBAM 2.5 SP1</span><span class="sxs-lookup"><span data-stu-id="11d30-103">Upgrading to MBAM 2.5 SP1 from MBAM 2.5</span></span>
<span data-ttu-id="11d30-104">本主题介绍将 Microsoft BitLocker 管理和监视 (MBAM) Server 2.5 和 MBAM 客户端从2.5 升级到 MBAM 2.5 SP1 的过程。</span><span class="sxs-lookup"><span data-stu-id="11d30-104">This topic describes the process for upgrading the Microsoft BitLocker Administration and Monitoring (MBAM) Server 2.5 and the MBAM Client from 2.5 to MBAM 2.5 SP1.</span></span>

### <span data-ttu-id="11d30-105">开始之前</span><span class="sxs-lookup"><span data-stu-id="11d30-105">Before you begin</span></span>
#### <span data-ttu-id="11d30-106">下载五月2019服务版本</span><span class="sxs-lookup"><span data-stu-id="11d30-106">Download the May 2019 servicing release</span></span>
[<span data-ttu-id="11d30-107">桌面优化包</span><span class="sxs-lookup"><span data-stu-id="11d30-107">Desktop Optimization Pack</span></span>](https://www.microsoft.com/download/details.aspx?id=58345)

#### <span data-ttu-id="11d30-108">下载2018年7月的服务版本</span><span class="sxs-lookup"><span data-stu-id="11d30-108">Download the July 2018 servicing release</span></span>
[<span data-ttu-id="11d30-109">桌面优化包</span><span class="sxs-lookup"><span data-stu-id="11d30-109">Desktop Optimization Pack</span></span>](https://www.microsoft.com/download/details.aspx?id=57157)


#### <span data-ttu-id="11d30-110">验证安装 documentaion</span><span class="sxs-lookup"><span data-stu-id="11d30-110">Verify the installation documentaion</span></span>
<span data-ttu-id="11d30-111">验证您是否拥有 MBAM 环境的当前文档，包括所有服务器名称、数据库名称、服务帐户及其密码。</span><span class="sxs-lookup"><span data-stu-id="11d30-111">Verify you have a current documentation of your MBAM environment, including all server names, database names, service accounts and their passwords.</span></span>

### <span data-ttu-id="11d30-112">升级步骤</span><span class="sxs-lookup"><span data-stu-id="11d30-112">Upgrade steps</span></span>
#### <span data-ttu-id="11d30-113">将 MBAM 数据库升级 (SQL Server 的步骤) </span><span class="sxs-lookup"><span data-stu-id="11d30-113">Steps to upgrade the MBAM Database (SQL Server)</span></span>
1. <span data-ttu-id="11d30-114">使用 MBAM 配置器;从 SQL server 中删除 "报表" 角色，或在其中托管 SSRS 数据库的任何位置。</span><span class="sxs-lookup"><span data-stu-id="11d30-114">Using the MBAM Configurator; remove the Reports role from the SQL server, or wherever the SSRS database is hosted.</span></span> <span data-ttu-id="11d30-115">这可能是同一个服务器或单独的服务器，具体取决于你的环境。</span><span class="sxs-lookup"><span data-stu-id="11d30-115">Depending on your environment, this can be the same server or a separate one.</span></span>
  > [!NOTE]
  > <span data-ttu-id="11d30-116">您将看不到用于删除数据库的选项;这是预期的。</span><span class="sxs-lookup"><span data-stu-id="11d30-116">You will not see an option to remove the Databases; this is expected.</span></span>  
2. <span data-ttu-id="11d30-117">通过批量许可服务中心网站安装 2.5 SP1 (，从 MDOP-Microsoft 桌面优化包2015：</span><span class="sxs-lookup"><span data-stu-id="11d30-117">Install 2.5 SP1(Located with MDOP - Microsoft Desktop Optimization Pack 2015 from the Volume Licensing Service Center site:</span></span>  <https://www.microsoft.com/Licensing/servicecenter/default.aspx>
3. <span data-ttu-id="11d30-118">目前不要配置</span><span class="sxs-lookup"><span data-stu-id="11d30-118">Do not configure it at this time</span></span> 
4. <span data-ttu-id="11d30-119">使用 MBAM 配置器;重新添加报表角色</span><span class="sxs-lookup"><span data-stu-id="11d30-119">Using the MBAM Configurator; re-add the Reports role</span></span>
5. <span data-ttu-id="11d30-120">使用 MBAM 配置器;在 SQL Server 上重新添加 SQL 数据库角色</span><span class="sxs-lookup"><span data-stu-id="11d30-120">Using the MBAM Configurator; re-add the SQL Database role on the SQL Server</span></span>
6. <span data-ttu-id="11d30-121">最后，系统将警告你已经存在并不创建该 "你的"，但这是预期的</span><span class="sxs-lookup"><span data-stu-id="11d30-121">At the end, you will be warned that the DBs already exist and  weren’t created, but this is expected</span></span>
7. <span data-ttu-id="11d30-122">此过程会将现有数据库更新为正在安装的当前版本。</span><span class="sxs-lookup"><span data-stu-id="11d30-122">This process updates the existing databases to the current version being installed.</span></span>              

#### <span data-ttu-id="11d30-123">升级 MBAM 服务器 (运行 MBAM 和 IIS 的步骤) </span><span class="sxs-lookup"><span data-stu-id="11d30-123">Steps to upgrade the MBAM Server (Running MBAM and IIS)</span></span>
1. <span data-ttu-id="11d30-124">使用 MBAM 配置器;从 IIS 服务器中删除管理员和自助服务门户</span><span class="sxs-lookup"><span data-stu-id="11d30-124">Using the MBAM Configurator; remove the Admin and Self Service Portals from  the IIS server</span></span>
2. <span data-ttu-id="11d30-125">安装 MBAM 2.5 SP1</span><span class="sxs-lookup"><span data-stu-id="11d30-125">Install MBAM 2.5 SP1</span></span>
3. <span data-ttu-id="11d30-126">目前不要配置</span><span class="sxs-lookup"><span data-stu-id="11d30-126">Do not configure it at this time</span></span>  
4. <span data-ttu-id="11d30-127">使用 MBAM 配置器;将 Admin 和自助服务门户重新添加到 IIS 服务器</span><span class="sxs-lookup"><span data-stu-id="11d30-127">Using the MBAM Configurator; re-add the Admin and Self Service Portals to the IIS server</span></span> 
5. <span data-ttu-id="11d30-128">打开提升的命令提示符，键入 " **IISRESET**"，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="11d30-128">Open an elevated command prompt, type **IISRESET**, and hit Enter.</span></span>
 
#### <span data-ttu-id="11d30-129">升级 MBAM 客户端/终结点的步骤</span><span class="sxs-lookup"><span data-stu-id="11d30-129">Steps to upgrade the MBAM Clients/Endpoints</span></span>
1. <span data-ttu-id="11d30-130">从客户端终结点卸载2.5 代理</span><span class="sxs-lookup"><span data-stu-id="11d30-130">Uninstall the 2.5 Agent from client endpoints</span></span>
2. <span data-ttu-id="11d30-131">在客户端终结点上安装 2.5 SP1 代理</span><span class="sxs-lookup"><span data-stu-id="11d30-131">Install the 2.5 SP1 Agent on the client endpoints</span></span>
3. <span data-ttu-id="11d30-132">将五月2019汇总客户端更新推送到运行 2.5 SP1 代理的客户端</span><span class="sxs-lookup"><span data-stu-id="11d30-132">Push out the May 2019 Rollup Client update to clients running the 2.5 SP1 Agent</span></span> 
4. <span data-ttu-id="11d30-133">在安装2019的 "汇总" 之前，无需卸载现有客户端。</span><span class="sxs-lookup"><span data-stu-id="11d30-133">There is no need to uninstall the existing client prior to installing the May 2019 Rollup.</span></span>  
