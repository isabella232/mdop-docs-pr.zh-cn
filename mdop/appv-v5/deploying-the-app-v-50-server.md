---
title: 部署 App-V 5.0 Server
description: 部署 App-V 5.0 Server
author: dansimp
ms.assetid: a47f0dc8-2971-4e4d-8d57-6b69bbed4b63
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e8fb65015a172a88d5e27d377037348dbc044654
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798579"
---
# <span data-ttu-id="f1554-103">部署 App-V 5.0 Server</span><span class="sxs-lookup"><span data-stu-id="f1554-103">Deploying the App-V 5.0 Server</span></span>


<span data-ttu-id="f1554-104">你可以通过使用本主题中介绍的不同部署配置来安装 app-v 5.0 服务器功能。</span><span class="sxs-lookup"><span data-stu-id="f1554-104">You can install the App-V 5.0 server features by using different deployment configurations, which described in this topic.</span></span> <span data-ttu-id="f1554-105">在安装服务器功能之前，请查看 app-v [5.0 安全注意事项](app-v-50-security-considerations.md)的 "服务器" 部分。</span><span class="sxs-lookup"><span data-stu-id="f1554-105">Before you install the server features, review the server section of [App-V 5.0 Security Considerations](app-v-50-security-considerations.md).</span></span>

<span data-ttu-id="f1554-106">有关部署 app-v 5.0 SP3 服务器的信息，请参阅[关于 app-v 5.0 sp3](about-app-v-50-sp3.md#bkmk-migrate-to-50sp3)。</span><span class="sxs-lookup"><span data-stu-id="f1554-106">For information about deploying the App-V 5.0 SP3 Server, see [About App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-migrate-to-50sp3).</span></span>

<span data-ttu-id="f1554-107">**重要提示** 在安装和配置 App-v 5.0 服务器之前，必须指定将托管每个组件的端口。</span><span class="sxs-lookup"><span data-stu-id="f1554-107">**Important** Before you install and configure the App-V 5.0 servers, you must specify a port where each component will be hosted.</span></span> <span data-ttu-id="f1554-108">还必须添加关联的防火墙规则，以便允许传入请求访问指定的端口。</span><span class="sxs-lookup"><span data-stu-id="f1554-108">You must also add the associated firewall rules to allow incoming requests to access the specified ports.</span></span> <span data-ttu-id="f1554-109">安装程序不修改防火墙设置。</span><span class="sxs-lookup"><span data-stu-id="f1554-109">The installer does not modify firewall settings.</span></span>

 

## <a href="" id="---------app-v-5-0-server-overview"></a> <span data-ttu-id="f1554-110">App-v 5.0 服务器概述</span><span class="sxs-lookup"><span data-stu-id="f1554-110">App-V 5.0 Server overview</span></span>


<span data-ttu-id="f1554-111">App-v 5.0 服务器由五个组件组成。</span><span class="sxs-lookup"><span data-stu-id="f1554-111">The App-V 5.0 Server is made up of five components.</span></span> <span data-ttu-id="f1554-112">每个组件在 App-v 5.0 环境中提供不同用途。</span><span class="sxs-lookup"><span data-stu-id="f1554-112">Each component serves a different purpose within the App-V 5.0 environment.</span></span> <span data-ttu-id="f1554-113">此处简要介绍了这五个组件：</span><span class="sxs-lookup"><span data-stu-id="f1554-113">Each of the five components is briefly described here:</span></span>

-   <span data-ttu-id="f1554-114">管理服务器-提供 app-v 5.0 基础结构的总体管理功能。</span><span class="sxs-lookup"><span data-stu-id="f1554-114">Management Server – provides overall management functionality for the App-V 5.0 infrastructure.</span></span>

-   <span data-ttu-id="f1554-115">管理数据库-方便了 App-v 5.0 管理的数据库 predeployments。</span><span class="sxs-lookup"><span data-stu-id="f1554-115">Management Database – facilitates database predeployments for App-V 5.0 management.</span></span>

-   <span data-ttu-id="f1554-116">发布服务器-提供虚拟应用程序的托管和流功能。</span><span class="sxs-lookup"><span data-stu-id="f1554-116">Publishing Server – provides hosting and streaming functionality for virtual applications.</span></span>

-   <span data-ttu-id="f1554-117">报表服务器-提供 app-v 5.0 reporting services。</span><span class="sxs-lookup"><span data-stu-id="f1554-117">Reporting Server – provides App-V 5.0 reporting services.</span></span>

-   <span data-ttu-id="f1554-118">报告数据库-为 App-v 5.0 报告简化数据库 predeployments。</span><span class="sxs-lookup"><span data-stu-id="f1554-118">Reporting Database – facilitates database predeployments for App-V 5.0 reporting.</span></span>

## <a href="" id="---------app-v-5-0-stand-alone-deployment"></a> <span data-ttu-id="f1554-119">App-v 5.0 独立部署</span><span class="sxs-lookup"><span data-stu-id="f1554-119">App-V 5.0 stand-alone deployment</span></span>


<span data-ttu-id="f1554-120">App-v 5.0 独立部署为小型部署或测试环境提供良好的拓扑。</span><span class="sxs-lookup"><span data-stu-id="f1554-120">The App-V 5.0 standalone deployment provides a good topology for a small deployment or a test environment.</span></span> <span data-ttu-id="f1554-121">使用此类型的实现时，所有服务器组件都将部署到一台计算机上。</span><span class="sxs-lookup"><span data-stu-id="f1554-121">When you use this type of implementation, all server components are deployed to a single computer.</span></span> <span data-ttu-id="f1554-122">服务和关联数据库将争用运行 App-v 5.0 组件的计算机上的资源。</span><span class="sxs-lookup"><span data-stu-id="f1554-122">The services and associated databases will compete for the resources on the computer that runs the App-V 5.0 components.</span></span> <span data-ttu-id="f1554-123">因此，不应将此拓扑用于较大的部署。</span><span class="sxs-lookup"><span data-stu-id="f1554-123">Therefore, you should not use this topology for larger deployments.</span></span>

[<span data-ttu-id="f1554-124">如何部署 App-V 5.0 Server</span><span class="sxs-lookup"><span data-stu-id="f1554-124">How to Deploy the App-V 5.0 Server</span></span>](how-to-deploy-the-app-v-50-server-50sp3.md)

[<span data-ttu-id="f1554-125">如何使用脚本部署 App-V 5.0 Server</span><span class="sxs-lookup"><span data-stu-id="f1554-125">How to Deploy the App-V 5.0 Server Using a Script</span></span>](how-to-deploy-the-app-v-50-server-using-a-script.md)

## <a href="" id="---------app-v-5-0-server-distributed-deployment"></a> <span data-ttu-id="f1554-126">App-v 5.0 服务器分布式部署</span><span class="sxs-lookup"><span data-stu-id="f1554-126">App-V 5.0 Server distributed deployment</span></span>


<span data-ttu-id="f1554-127">分布式部署拓扑可以支持大型应用程序-V 5.0 客户端基础，它使您能够更轻松地管理和扩展您的环境。</span><span class="sxs-lookup"><span data-stu-id="f1554-127">The distributed deployment topology can support a large App-V 5.0 client base and it allows you to more easily manage and scale your environment.</span></span> <span data-ttu-id="f1554-128">使用此类型的部署时，将基于组织的结构和要求，在多台计算机上部署 app-v 5.0 服务器组件。</span><span class="sxs-lookup"><span data-stu-id="f1554-128">When you use this type of deployment, the App-V 5.0 Server components are deployed across multiple computers, based on the structure and requirements of the organization.</span></span>

[<span data-ttu-id="f1554-129">如何在单独的计算机上从管理和报告服务安装管理和报告数据库</span><span class="sxs-lookup"><span data-stu-id="f1554-129">How to Install the Management and Reporting Databases on Separate Computers from the Management and Reporting Services</span></span>](how-to-install-the-management-and-reporting-databases-on-separate-computers-from-the-management-and-reporting-services.md)

[<span data-ttu-id="f1554-130">如何在独立计算机上安装报告服务器并将其连接到数据库</span><span class="sxs-lookup"><span data-stu-id="f1554-130">How to install the Reporting Server on a Standalone Computer and Connect it to the Database</span></span>](how-to-install-the-reporting-server-on-a-standalone-computer-and-connect-it-to-the-database.md)

[<span data-ttu-id="f1554-131">如何使用脚本部署 App-V 5.0 Server</span><span class="sxs-lookup"><span data-stu-id="f1554-131">How to Deploy the App-V 5.0 Server Using a Script</span></span>](how-to-deploy-the-app-v-50-server-using-a-script.md)

[<span data-ttu-id="f1554-132">如何在远程计算机上安装发布服务器</span><span class="sxs-lookup"><span data-stu-id="f1554-132">How to Install the Publishing Server on a Remote Computer</span></span>](how-to-install-the-publishing-server-on-a-remote-computer.md)

[<span data-ttu-id="f1554-133">如何在独立计算机上安装 Management Server 并将其连接到数据库</span><span class="sxs-lookup"><span data-stu-id="f1554-133">How to install the Management Server on a Standalone Computer and Connect it to the Database</span></span>](how-to-install-the-management-server-on-a-standalone-computer-and-connect-it-to-the-database.md)

## <span data-ttu-id="f1554-134">使用企业软件分发（ESD）解决方案和 App-v 5。0</span><span class="sxs-lookup"><span data-stu-id="f1554-134">Using an Enterprise Software Distribution (ESD) solution and App-V 5.0</span></span>


<span data-ttu-id="f1554-135">您也可以使用 ESD 部署 app-v 5.0 客户端和程序包，而无需部署 app-v 5.0。</span><span class="sxs-lookup"><span data-stu-id="f1554-135">You can also deploy the App-V 5.0 clients and packages by using an ESD without having to deploy App-V 5.0.</span></span> <span data-ttu-id="f1554-136">集成的完整功能将因您使用的 ESD 而异。</span><span class="sxs-lookup"><span data-stu-id="f1554-136">The full capabilities for integration will vary depending on the ESD that you use.</span></span>

<span data-ttu-id="f1554-137">**注意** App-v 5.0 报告服务器和报告数据库仍然可以与 ESD 一起部署，以便从 App-v 5.0 客户端收集报告数据。</span><span class="sxs-lookup"><span data-stu-id="f1554-137">**Note** The App-V 5.0 reporting server and reporting database can still be deployed alongside the ESD to collect the reporting data from the App-V 5.0 clients.</span></span> <span data-ttu-id="f1554-138">但是，不应部署其他三个服务器组件，因为它们将与 ESD 功能发生冲突。</span><span class="sxs-lookup"><span data-stu-id="f1554-138">However, the other three server components should not be deployed, because they will conflict with the ESD functionality.</span></span>

 

[<span data-ttu-id="f1554-139">使用电子软件分发 (ESD) 部署 App-V 5.0 程序包</span><span class="sxs-lookup"><span data-stu-id="f1554-139">Deploying App-V 5.0 Packages by Using Electronic Software Distribution (ESD)</span></span>](deploying-app-v-50-packages-by-using-electronic-software-distribution--esd-.md)

## <a href="" id="---------app-v-5-0-server-logs"></a> <span data-ttu-id="f1554-140">App-v 5.0 服务器日志</span><span class="sxs-lookup"><span data-stu-id="f1554-140">App-V 5.0 Server logs</span></span>


<span data-ttu-id="f1554-141">在使用 App-v 5.0 时，可以使用 app-v 5.0 服务器日志信息帮助解决服务器安装和操作事件。</span><span class="sxs-lookup"><span data-stu-id="f1554-141">You can use App-V 5.0 server log information to help troubleshoot the server installation and operational events while using App-V 5.0.</span></span> <span data-ttu-id="f1554-142">与服务器相关的日志信息可以通过**事件查看器**进行查看。</span><span class="sxs-lookup"><span data-stu-id="f1554-142">The server-related log information can be reviewed with the **Event Viewer**.</span></span> <span data-ttu-id="f1554-143">下一行显示与服务器相关的事件的特定路径：</span><span class="sxs-lookup"><span data-stu-id="f1554-143">The following line displays the specific path for Server-related events:</span></span>

**<span data-ttu-id="f1554-144">事件查看器 \ 应用程序和服务日志 \\ Microsoft \\ App V</span><span class="sxs-lookup"><span data-stu-id="f1554-144">Event Viewer \\ Applications and Services Logs \\ Microsoft \\ App V</span></span>**

<span data-ttu-id="f1554-145">关联的安装日志保存在以下目录中：</span><span class="sxs-lookup"><span data-stu-id="f1554-145">Associated setup logs are saved in the following directory:</span></span>

**<span data-ttu-id="f1554-146">高</span><span class="sxs-lookup"><span data-stu-id="f1554-146">%temp%</span></span>**

<span data-ttu-id="f1554-147">在 App-v 5.0 SP3 中，某些日志已进行了合并和移动。</span><span class="sxs-lookup"><span data-stu-id="f1554-147">In App-V 5.0 SP3, some logs have been consolidated and moved.</span></span> <span data-ttu-id="f1554-148">请参阅[关于 App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-event-logs-moved)。</span><span class="sxs-lookup"><span data-stu-id="f1554-148">See [About App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-event-logs-moved).</span></span>

## <a href="" id="---------app-v-5-0-reporting"></a> <span data-ttu-id="f1554-149">App-v 5.0 报告</span><span class="sxs-lookup"><span data-stu-id="f1554-149">App-V 5.0 reporting</span></span>


<span data-ttu-id="f1554-150">App-v 5.0 报告允许应用-V 5.0 客户端收集数据，然后将其发送回存储在中央存储库中。</span><span class="sxs-lookup"><span data-stu-id="f1554-150">App-V 5.0 reporting allows App-V 5.0 clients to collect data and then send it back to be stored in a central repository.</span></span> <span data-ttu-id="f1554-151">你可以使用此信息更好地查看你的组织内的虚拟应用程序使用情况。</span><span class="sxs-lookup"><span data-stu-id="f1554-151">You can use this information to get a better view of the virtual application usage within your organization.</span></span> <span data-ttu-id="f1554-152">下表显示了 App-v 5.0 客户端收集的一些信息类型：</span><span class="sxs-lookup"><span data-stu-id="f1554-152">The following list displays some of the types of information the App-V 5.0 client collects:</span></span>

-   <span data-ttu-id="f1554-153">有关运行 app-v 5.0 客户端的计算机的信息。</span><span class="sxs-lookup"><span data-stu-id="f1554-153">Information about the computer that runs the App-V 5.0 client.</span></span>

-   <span data-ttu-id="f1554-154">有关运行 App-v 5.0 客户端的特定计算机上的虚拟化程序包的信息。</span><span class="sxs-lookup"><span data-stu-id="f1554-154">Information about virtualized packages on a specific computer that runs the App-V 5.0 client.</span></span>

-   <span data-ttu-id="f1554-155">有关特定用户的程序包打开和关闭的信息。</span><span class="sxs-lookup"><span data-stu-id="f1554-155">Information about package open and shutdown for a specific user.</span></span>

<span data-ttu-id="f1554-156">报告信息将保留，直到成功发送到报表服务器数据库。</span><span class="sxs-lookup"><span data-stu-id="f1554-156">The reporting information will be maintained until it is successfully sent to the reporting server database.</span></span> <span data-ttu-id="f1554-157">在数据库中数据后，您可以使用 Microsoft SQL Server Reporting Services 生成任何必需的报表。</span><span class="sxs-lookup"><span data-stu-id="f1554-157">After the data is in the database, you can use Microsoft SQL Server Reporting Services to generate any necessary reports.</span></span>

<span data-ttu-id="f1554-158">如果要检索报表信息，则必须使用 microsoft sql Server Reporting Services （SSRS），它可与 Microsoft SQL 一起使用。</span><span class="sxs-lookup"><span data-stu-id="f1554-158">If you want to retrieve report information, you must use Microsoft SQL Server Reporting Services (SSRS) which is available with Microsoft SQL.</span></span> <span data-ttu-id="f1554-159">安装了 app-v 5.0 报告服务器时未安装 SSRS，必须单独部署它才能生成关联的报告。</span><span class="sxs-lookup"><span data-stu-id="f1554-159">SSRS is not installed when you install the App-V 5.0 reporting server and it must be deployed separately to generate the associated reports.</span></span>

<span data-ttu-id="f1554-160">[有关 app-v 5.0 报告](about-app-v-50-reporting.md)的详细信息，请使用以下链接。</span><span class="sxs-lookup"><span data-stu-id="f1554-160">Use the following link for more information [About App-V 5.0 Reporting](about-app-v-50-reporting.md).</span></span>

[<span data-ttu-id="f1554-161">如何使用 PowerShell 在 App-V 5.0 Client 上启用报告</span><span class="sxs-lookup"><span data-stu-id="f1554-161">How to Enable Reporting on the App-V 5.0 Client by Using PowerShell</span></span>](how-to-enable-reporting-on-the-app-v-50-client-by-using-powershell.md)

## <span data-ttu-id="f1554-162">App-v 服务器的其他资源</span><span class="sxs-lookup"><span data-stu-id="f1554-162">Other resources for the App-V server</span></span>


[<span data-ttu-id="f1554-163">部署 App-V 5.0</span><span class="sxs-lookup"><span data-stu-id="f1554-163">Deploying App-V 5.0</span></span>](deploying-app-v-50.md)






 

 





