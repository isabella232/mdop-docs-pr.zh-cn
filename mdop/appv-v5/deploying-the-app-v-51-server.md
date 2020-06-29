---
title: 部署 App-V 5.1 Server
description: 部署 App-V 5.1 Server
author: dansimp
ms.assetid: 987b61dc-00d6-49ba-8f1b-92d7b948e702
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2bcff2a3211ea3e2f666aff1d6f2ad919509aa3a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798577"
---
# <span data-ttu-id="44f84-103">部署 App-V 5.1 Server</span><span class="sxs-lookup"><span data-stu-id="44f84-103">Deploying the App-V 5.1 Server</span></span>

<span data-ttu-id="44f84-104">你可以通过使用本主题中介绍的不同部署配置来安装 Microsoft Application Virtualization （App-v）5.1 服务器功能。</span><span class="sxs-lookup"><span data-stu-id="44f84-104">You can install the Microsoft Application Virtualization (App-V) 5.1 server features by using different deployment configurations, which described in this topic.</span></span> <span data-ttu-id="44f84-105">在安装服务器功能之前，请查看 app-v [5.1 安全注意事项](app-v-51-security-considerations.md)的 "服务器" 部分。</span><span class="sxs-lookup"><span data-stu-id="44f84-105">Before you install the server features, review the server section of [App-V 5.1 Security Considerations](app-v-51-security-considerations.md).</span></span>

<span data-ttu-id="44f84-106">有关部署 app-v 服务器的信息，请参阅[关于 app-v 5.1](about-app-v-51.md#bkmk-migrate-to-51)。</span><span class="sxs-lookup"><span data-stu-id="44f84-106">For information about deploying the App-V Server, see [About App-V 5.1](about-app-v-51.md#bkmk-migrate-to-51).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="44f84-107">在安装和配置 App-v 5.1 服务器之前，必须指定将托管每个组件的端口。</span><span class="sxs-lookup"><span data-stu-id="44f84-107">Before you install and configure the App-V 5.1 servers, you must specify a port where each component will be hosted.</span></span> <span data-ttu-id="44f84-108">还必须添加关联的防火墙规则，以便允许传入请求访问指定的端口。</span><span class="sxs-lookup"><span data-stu-id="44f84-108">You must also add the associated firewall rules to allow incoming requests to access the specified ports.</span></span> <span data-ttu-id="44f84-109">安装程序不修改防火墙设置。</span><span class="sxs-lookup"><span data-stu-id="44f84-109">The installer does not modify firewall settings.</span></span>

## <a href="" id="---------app-v-5-1-server-overview"></a> <span data-ttu-id="44f84-110">App-v 5.1 服务器概述</span><span class="sxs-lookup"><span data-stu-id="44f84-110">App-V 5.1 Server overview</span></span>

<span data-ttu-id="44f84-111">App-v 5.1 服务器由五个组件组成。</span><span class="sxs-lookup"><span data-stu-id="44f84-111">The App-V 5.1 Server is made up of five components.</span></span> <span data-ttu-id="44f84-112">每个组件在 App-v 5.1 环境中提供不同用途。</span><span class="sxs-lookup"><span data-stu-id="44f84-112">Each component serves a different purpose within the App-V 5.1 environment.</span></span> <span data-ttu-id="44f84-113">此处简要介绍了这五个组件：</span><span class="sxs-lookup"><span data-stu-id="44f84-113">Each of the five components is briefly described here:</span></span>

- <span data-ttu-id="44f84-114">管理服务器-提供 app-v 5.1 基础结构的总体管理功能。</span><span class="sxs-lookup"><span data-stu-id="44f84-114">Management Server – provides overall management functionality for the App-V 5.1 infrastructure.</span></span>
- <span data-ttu-id="44f84-115">管理数据库-方便了 App-v 5.1 管理的数据库 predeployments。</span><span class="sxs-lookup"><span data-stu-id="44f84-115">Management Database – facilitates database predeployments for App-V 5.1 management.</span></span>
- <span data-ttu-id="44f84-116">发布服务器-提供虚拟应用程序的托管和流功能。</span><span class="sxs-lookup"><span data-stu-id="44f84-116">Publishing Server – provides hosting and streaming functionality for virtual applications.</span></span>
- <span data-ttu-id="44f84-117">报表服务器-提供 app-v 5.1 reporting services。</span><span class="sxs-lookup"><span data-stu-id="44f84-117">Reporting Server – provides App-V 5.1 reporting services.</span></span>
- <span data-ttu-id="44f84-118">报告数据库-为 App-v 5.1 报告简化数据库 predeployments。</span><span class="sxs-lookup"><span data-stu-id="44f84-118">Reporting Database – facilitates database predeployments for App-V 5.1 reporting.</span></span>

## <a href="" id="---------app-v-5-1-stand-alone-deployment"></a> <span data-ttu-id="44f84-119">App-v 5.1 独立部署</span><span class="sxs-lookup"><span data-stu-id="44f84-119">App-V 5.1 stand-alone deployment</span></span>

<span data-ttu-id="44f84-120">App-v 5.1 独立部署为小型部署或测试环境提供良好的拓扑。</span><span class="sxs-lookup"><span data-stu-id="44f84-120">The App-V 5.1 standalone deployment provides a good topology for a small deployment or a test environment.</span></span> <span data-ttu-id="44f84-121">使用此类型的实现时，所有服务器组件都将部署到一台计算机上。</span><span class="sxs-lookup"><span data-stu-id="44f84-121">When you use this type of implementation, all server components are deployed to a single computer.</span></span> <span data-ttu-id="44f84-122">服务和关联数据库将争用运行 App-v 5.1 组件的计算机上的资源。</span><span class="sxs-lookup"><span data-stu-id="44f84-122">The services and associated databases will compete for the resources on the computer that runs the App-V 5.1 components.</span></span> <span data-ttu-id="44f84-123">因此，不应将此拓扑用于较大的部署。</span><span class="sxs-lookup"><span data-stu-id="44f84-123">Therefore, you should not use this topology for larger deployments.</span></span>

[<span data-ttu-id="44f84-124">如何部署 App-V 5.1 Server</span><span class="sxs-lookup"><span data-stu-id="44f84-124">How to Deploy the App-V 5.1 Server</span></span>](how-to-deploy-the-app-v-51-server.md)

[<span data-ttu-id="44f84-125">如何使用脚本部署 App-V 5.1 Server</span><span class="sxs-lookup"><span data-stu-id="44f84-125">How to Deploy the App-V 5.1 Server Using a Script</span></span>](how-to-deploy-the-app-v-51-server-using-a-script.md)

## <a href="" id="---------app-v-5-1-server-distributed-deployment"></a> <span data-ttu-id="44f84-126">App-v 5.1 服务器分布式部署</span><span class="sxs-lookup"><span data-stu-id="44f84-126">App-V 5.1 Server distributed deployment</span></span>

<span data-ttu-id="44f84-127">分布式部署拓扑可以支持大型应用程序-V 5.1 客户端基础，它使您能够更轻松地管理和扩展您的环境。</span><span class="sxs-lookup"><span data-stu-id="44f84-127">The distributed deployment topology can support a large App-V 5.1 client base and it allows you to more easily manage and scale your environment.</span></span> <span data-ttu-id="44f84-128">使用此类型的部署时，将基于组织的结构和要求，在多台计算机上部署 app-v 5.1 服务器组件。</span><span class="sxs-lookup"><span data-stu-id="44f84-128">When you use this type of deployment, the App-V 5.1 Server components are deployed across multiple computers, based on the structure and requirements of the organization.</span></span>

[<span data-ttu-id="44f84-129">如何在单独的计算机上从管理和报告服务安装管理和报告数据库</span><span class="sxs-lookup"><span data-stu-id="44f84-129">How to Install the Management and Reporting Databases on Separate Computers from the Management and Reporting Services</span></span>](how-to-install-the-management-and-reporting-databases-on-separate-computers-from-the-management-and-reporting-services51.md)

[<span data-ttu-id="44f84-130">如何在独立计算机上安装 Management Server 并将其连接到数据库</span><span class="sxs-lookup"><span data-stu-id="44f84-130">How to install the Management Server on a Standalone Computer and Connect it to the Database</span></span>](how-to-install-the-management-server-on-a-standalone-computer-and-connect-it-to-the-database51.md)

[<span data-ttu-id="44f84-131">如何使用脚本部署 App-V 5.1 Server</span><span class="sxs-lookup"><span data-stu-id="44f84-131">How to Deploy the App-V 5.1 Server Using a Script</span></span>](how-to-deploy-the-app-v-51-server-using-a-script.md)

[<span data-ttu-id="44f84-132">如何在远程计算机上安装发布服务器</span><span class="sxs-lookup"><span data-stu-id="44f84-132">How to Install the Publishing Server on a Remote Computer</span></span>](how-to-install-the-publishing-server-on-a-remote-computer51.md)

[<span data-ttu-id="44f84-133">如何在独立计算机上安装 Management Server 并将其连接到数据库</span><span class="sxs-lookup"><span data-stu-id="44f84-133">How to install the Management Server on a Standalone Computer and Connect it to the Database</span></span>](how-to-install-the-management-server-on-a-standalone-computer-and-connect-it-to-the-database51.md)

## <span data-ttu-id="44f84-134">使用企业软件分发（ESD）解决方案和 App-v 5。1</span><span class="sxs-lookup"><span data-stu-id="44f84-134">Using an Enterprise Software Distribution (ESD) solution and App-V 5.1</span></span>

<span data-ttu-id="44f84-135">您也可以使用 ESD 部署 app-v 5.1 客户端和程序包，而无需部署 app-v 5.1。</span><span class="sxs-lookup"><span data-stu-id="44f84-135">You can also deploy the App-V 5.1 clients and packages by using an ESD without having to deploy App-V 5.1.</span></span> <span data-ttu-id="44f84-136">集成的完整功能将因您使用的 ESD 而异。</span><span class="sxs-lookup"><span data-stu-id="44f84-136">The full capabilities for integration will vary depending on the ESD that you use.</span></span>

> [!NOTE]
> <span data-ttu-id="44f84-137">App-v 5.1 报告服务器和报告数据库仍然可以与 ESD 一起部署，以便从 App-v 5.1 客户端收集报告数据。</span><span class="sxs-lookup"><span data-stu-id="44f84-137">The App-V 5.1 reporting server and reporting database can still be deployed alongside the ESD to collect the reporting data from the App-V 5.1 clients.</span></span> <span data-ttu-id="44f84-138">但是，不应部署其他三个服务器组件，因为它们将与 ESD 功能发生冲突。</span><span class="sxs-lookup"><span data-stu-id="44f84-138">However, the other three server components should not be deployed, because they will conflict with the ESD functionality.</span></span>

[<span data-ttu-id="44f84-139">使用电子软件分发 (ESD) 部署 App-V 5.1 程序包</span><span class="sxs-lookup"><span data-stu-id="44f84-139">Deploying App-V 5.1 Packages by Using Electronic Software Distribution (ESD)</span></span>](deploying-app-v-51-packages-by-using-electronic-software-distribution--esd-.md)

## <a href="" id="---------app-v-5-1-server-logs"></a> <span data-ttu-id="44f84-140">App-v 5.1 服务器日志</span><span class="sxs-lookup"><span data-stu-id="44f84-140">App-V 5.1 Server logs</span></span>

<span data-ttu-id="44f84-141">在使用 App-v 5.1 时，可以使用 app-v 5.1 服务器日志信息帮助解决服务器安装和操作事件。</span><span class="sxs-lookup"><span data-stu-id="44f84-141">You can use App-V 5.1 server log information to help troubleshoot the server installation and operational events while using App-V 5.1.</span></span> <span data-ttu-id="44f84-142">与服务器相关的日志信息可以通过**事件查看器**进行查看。</span><span class="sxs-lookup"><span data-stu-id="44f84-142">The server-related log information can be reviewed with the **Event Viewer**.</span></span> <span data-ttu-id="44f84-143">下一行显示与服务器相关的事件的特定路径：</span><span class="sxs-lookup"><span data-stu-id="44f84-143">The following line displays the specific path for Server-related events:</span></span>

**<span data-ttu-id="44f84-144">事件查看器 \ 应用程序和服务日志 \\ Microsoft \\ App V</span><span class="sxs-lookup"><span data-stu-id="44f84-144">Event Viewer \\ Applications and Services Logs \\ Microsoft \\ App V</span></span>**

<span data-ttu-id="44f84-145">关联的安装日志保存在以下目录中：</span><span class="sxs-lookup"><span data-stu-id="44f84-145">Associated setup logs are saved in the following directory:</span></span>

**<span data-ttu-id="44f84-146">高</span><span class="sxs-lookup"><span data-stu-id="44f84-146">%temp%</span></span>**

<span data-ttu-id="44f84-147">在 App-v 5.0 SP3 中，某些日志已合并并移动。</span><span class="sxs-lookup"><span data-stu-id="44f84-147">In App-V 5.0 SP3, some logs were consolidated and moved.</span></span> <span data-ttu-id="44f84-148">请参阅[关于 App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-event-logs-moved)。</span><span class="sxs-lookup"><span data-stu-id="44f84-148">See [About App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-event-logs-moved).</span></span>

## <a href="" id="---------app-v-5-1-reporting"></a> <span data-ttu-id="44f84-149">App-v 5.1 报告</span><span class="sxs-lookup"><span data-stu-id="44f84-149">App-V 5.1 reporting</span></span>

<span data-ttu-id="44f84-150">App-v 5.1 报告允许应用-V 5.1 客户端收集数据，然后将其发送回存储在中央存储库中。</span><span class="sxs-lookup"><span data-stu-id="44f84-150">App-V 5.1 reporting allows App-V 5.1 clients to collect data and then send it back to be stored in a central repository.</span></span> <span data-ttu-id="44f84-151">你可以使用此信息更好地查看你的组织内的虚拟应用程序使用情况。</span><span class="sxs-lookup"><span data-stu-id="44f84-151">You can use this information to get a better view of the virtual application usage within your organization.</span></span> <span data-ttu-id="44f84-152">下表显示了 App-v 5.1 客户端收集的一些信息类型：</span><span class="sxs-lookup"><span data-stu-id="44f84-152">The following list displays some of the types of information the App-V 5.1 client collects:</span></span>

- <span data-ttu-id="44f84-153">有关运行 app-v 5.1 客户端的计算机的信息。</span><span class="sxs-lookup"><span data-stu-id="44f84-153">Information about the computer that runs the App-V 5.1 client.</span></span>
- <span data-ttu-id="44f84-154">有关运行 App-v 5.1 客户端的特定计算机上的虚拟化程序包的信息。</span><span class="sxs-lookup"><span data-stu-id="44f84-154">Information about virtualized packages on a specific computer that runs the App-V 5.1 client.</span></span>
- <span data-ttu-id="44f84-155">有关特定用户的程序包打开和关闭的信息。</span><span class="sxs-lookup"><span data-stu-id="44f84-155">Information about package open and shutdown for a specific user.</span></span>

<span data-ttu-id="44f84-156">报告信息将保留，直到成功发送到报表服务器数据库。</span><span class="sxs-lookup"><span data-stu-id="44f84-156">The reporting information will be maintained until it is successfully sent to the reporting server database.</span></span> <span data-ttu-id="44f84-157">在数据库中数据后，您可以使用 Microsoft SQL Server Reporting Services 生成任何必需的报表。</span><span class="sxs-lookup"><span data-stu-id="44f84-157">After the data is in the database, you can use Microsoft SQL Server Reporting Services to generate any necessary reports.</span></span>

<span data-ttu-id="44f84-158">如果要检索报表信息，则必须使用 microsoft sql Server Reporting Services （SSRS），它可与 Microsoft SQL 一起使用。</span><span class="sxs-lookup"><span data-stu-id="44f84-158">If you want to retrieve report information, you must use Microsoft SQL Server Reporting Services (SSRS) which is available with Microsoft SQL.</span></span> <span data-ttu-id="44f84-159">安装了 app-v 5.1 报告服务器时未安装 SSRS，必须单独部署它才能生成关联的报告。</span><span class="sxs-lookup"><span data-stu-id="44f84-159">SSRS is not installed when you install the App-V 5.1 reporting server and it must be deployed separately to generate the associated reports.</span></span>

<span data-ttu-id="44f84-160">[有关 app-v 5.1 报告](about-app-v-51-reporting.md)的详细信息，请使用以下链接。</span><span class="sxs-lookup"><span data-stu-id="44f84-160">Use the following link for more information [About App-V 5.1 Reporting](about-app-v-51-reporting.md).</span></span>

[<span data-ttu-id="44f84-161">如何使用 PowerShell 在 App-V 5.1 Client 上启用报告</span><span class="sxs-lookup"><span data-stu-id="44f84-161">How to Enable Reporting on the App-V 5.1 Client by Using PowerShell</span></span>](how-to-enable-reporting-on-the-app-v-51-client-by-using-powershell.md)

## <span data-ttu-id="44f84-162">App-v 服务器的其他资源</span><span class="sxs-lookup"><span data-stu-id="44f84-162">Other resources for the App-V server</span></span>

[<span data-ttu-id="44f84-163">部署 App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="44f84-163">Deploying App-V 5.1</span></span>](deploying-app-v-51.md)
