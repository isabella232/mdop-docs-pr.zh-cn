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
ms.openlocfilehash: 19da3df0976b51700e0d10c302a31421a88d17e4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798122"
---
# <span data-ttu-id="79396-103">从 MBAM 2.5 升级到 MBAM 2.5 SP1</span><span class="sxs-lookup"><span data-stu-id="79396-103">Upgrading to MBAM 2.5 SP1 from MBAM 2.5</span></span>
<span data-ttu-id="79396-104">本主题介绍将 Microsoft BitLocker 管理和监视（MBAM） Server 2.5 和 MBAM 客户端从2.5 升级到 MBAM 2.5 SP1 的过程。</span><span class="sxs-lookup"><span data-stu-id="79396-104">This topic describes the process for upgrading the Microsoft BitLocker Administration and Monitoring (MBAM) Server 2.5 and the MBAM Client from 2.5 to MBAM 2.5 SP1.</span></span>

### <span data-ttu-id="79396-105">开始之前</span><span class="sxs-lookup"><span data-stu-id="79396-105">Before you begin</span></span>
#### <span data-ttu-id="79396-106">下载五月2019服务版本</span><span class="sxs-lookup"><span data-stu-id="79396-106">Download the May 2019 servicing release</span></span>
[<span data-ttu-id="79396-107">桌面优化包</span><span class="sxs-lookup"><span data-stu-id="79396-107">Desktop Optimization Pack</span></span>](https://www.microsoft.com/download/details.aspx?id=58345)

#### <span data-ttu-id="79396-108">验证安装 documentaion</span><span class="sxs-lookup"><span data-stu-id="79396-108">Verify the installation documentaion</span></span>
<span data-ttu-id="79396-109">验证您是否拥有 MBAM 环境的当前文档，包括所有服务器名称、数据库名称、服务帐户及其密码。</span><span class="sxs-lookup"><span data-stu-id="79396-109">Verify you have a current documentation of your MBAM environment, including all server names, database names, service accounts and their passwords.</span></span>

### <span data-ttu-id="79396-110">升级步骤</span><span class="sxs-lookup"><span data-stu-id="79396-110">Upgrade steps</span></span>
#### <span data-ttu-id="79396-111">升级 MBAM 数据库（SQL Server）的步骤</span><span class="sxs-lookup"><span data-stu-id="79396-111">Steps to upgrade the MBAM Database (SQL Server)</span></span>
1. <span data-ttu-id="79396-112">使用 MBAM 配置器;从 SQL server 中删除 "报表" 角色，或在其中托管 SSRS 数据库的任何位置。</span><span class="sxs-lookup"><span data-stu-id="79396-112">Using the MBAM Configurator; remove the Reports role from the SQL server, or wherever the SSRS database is hosted.</span></span> <span data-ttu-id="79396-113">这可能是同一个服务器或单独的服务器，具体取决于你的环境。</span><span class="sxs-lookup"><span data-stu-id="79396-113">Depending on your environment, this can be the same server or a separate one.</span></span>
  > [!NOTE]
  > <span data-ttu-id="79396-114">您将看不到用于删除数据库的选项;这是预期的。</span><span class="sxs-lookup"><span data-stu-id="79396-114">You will not see an option to remove the Databases; this is expected.</span></span>  
2. <span data-ttu-id="79396-115">安装 2.5 SP1 （与 MDOP-Microsoft 桌面优化包2015位于批量许可服务中心网站中）：</span><span class="sxs-lookup"><span data-stu-id="79396-115">Install 2.5 SP1(Located with MDOP - Microsoft Desktop Optimization Pack 2015 from the Volume Licensing Service Center site:</span></span>  <https://www.microsoft.com/Licensing/servicecenter/default.aspx>
3. <span data-ttu-id="79396-116">目前不要配置</span><span class="sxs-lookup"><span data-stu-id="79396-116">Do not configure it at this time</span></span> 
4. <span data-ttu-id="79396-117">使用 MBAM 配置器;重新添加报表角色</span><span class="sxs-lookup"><span data-stu-id="79396-117">Using the MBAM Configurator; re-add the Reports role</span></span>
5. <span data-ttu-id="79396-118">使用 MBAM 配置器;在 SQL Server 上重新添加 SQL 数据库角色</span><span class="sxs-lookup"><span data-stu-id="79396-118">Using the MBAM Configurator; re-add the SQL Database role on the SQL Server</span></span>
6. <span data-ttu-id="79396-119">最后，系统将警告你已经存在并不创建该 "你的"，但这是预期的</span><span class="sxs-lookup"><span data-stu-id="79396-119">At the end, you will be warned that the DBs already exist and  weren’t created, but this is expected</span></span>
7. <span data-ttu-id="79396-120">此过程会将现有数据库更新为正在安装的当前版本。</span><span class="sxs-lookup"><span data-stu-id="79396-120">This process updates the existing databases to the current version being installed.</span></span>              

#### <span data-ttu-id="79396-121">升级 MBAM 服务器（运行 MBAM 和 IIS）的步骤</span><span class="sxs-lookup"><span data-stu-id="79396-121">Steps to upgrade the MBAM Server (Running MBAM and IIS)</span></span>
1. <span data-ttu-id="79396-122">使用 MBAM 配置器;从 IIS 服务器中删除管理员和自助服务门户</span><span class="sxs-lookup"><span data-stu-id="79396-122">Using the MBAM Configurator; remove the Admin and Self Service Portals from  the IIS server</span></span>
2. <span data-ttu-id="79396-123">安装 MBAM 2.5 SP1</span><span class="sxs-lookup"><span data-stu-id="79396-123">Install MBAM 2.5 SP1</span></span>
3. <span data-ttu-id="79396-124">目前不要配置</span><span class="sxs-lookup"><span data-stu-id="79396-124">Do not configure it at this time</span></span>  
4. <span data-ttu-id="79396-125">使用 MBAM 配置器;将 Admin 和自助服务门户重新添加到 IIS 服务器</span><span class="sxs-lookup"><span data-stu-id="79396-125">Using the MBAM Configurator; re-add the Admin and Self Service Portals to the IIS server</span></span> 
5. <span data-ttu-id="79396-126">打开提升的命令提示符，键入 " **IISRESET**"，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="79396-126">Open an elevated command prompt, type **IISRESET**, and hit Enter.</span></span>
 
#### <span data-ttu-id="79396-127">升级 MBAM 客户端/终结点的步骤</span><span class="sxs-lookup"><span data-stu-id="79396-127">Steps to upgrade the MBAM Clients/Endpoints</span></span>
1. <span data-ttu-id="79396-128">从客户端终结点卸载2.5 代理</span><span class="sxs-lookup"><span data-stu-id="79396-128">Uninstall the 2.5 Agent from client endpoints</span></span>
2. <span data-ttu-id="79396-129">在客户端终结点上安装 2.5 SP1 代理</span><span class="sxs-lookup"><span data-stu-id="79396-129">Install the 2.5 SP1 Agent on the client endpoints</span></span>
3. <span data-ttu-id="79396-130">将五月2019汇总客户端更新推送到运行 2.5 SP1 代理的客户端</span><span class="sxs-lookup"><span data-stu-id="79396-130">Push out the May 2019 Rollup Client update to clients running the 2.5 SP1 Agent</span></span> 
4. <span data-ttu-id="79396-131">在安装2019的 "汇总" 之前，无需卸载现有客户端。</span><span class="sxs-lookup"><span data-stu-id="79396-131">There is no need to uninstall the existing client prior to installing the May 2019 Rollup.</span></span>  
