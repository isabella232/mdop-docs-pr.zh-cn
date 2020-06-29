---
title: App-V 5.1 容量计划
description: App-V 5.1 容量计划
author: dansimp
ms.assetid: 7a98062f-5a60-49d6-ab40-dc6057e1dd5a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b152536b3c61e47f3fda84489b1e102c285e01c6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798632"
---
# <span data-ttu-id="eb39d-103">App-V 5.1 容量计划</span><span class="sxs-lookup"><span data-stu-id="eb39d-103">App-V 5.1 Capacity Planning</span></span>


<span data-ttu-id="eb39d-104">以下建议可用作基线，以帮助确定适合你的组织的 app-v 5.1 基础结构的容量计划信息。</span><span class="sxs-lookup"><span data-stu-id="eb39d-104">The following recommendations can be used as a baseline to help determine capacity planning information that is appropriate to your organization’s App-V 5.1 infrastructure.</span></span>

<span data-ttu-id="eb39d-105">**重要提示** 仅将本部分中的信息用作规划 app-v 5.1 部署的常规指南。</span><span class="sxs-lookup"><span data-stu-id="eb39d-105">**Important** Use the information in this section only as a general guide for planning your App-V 5.1 deployment.</span></span> <span data-ttu-id="eb39d-106">你的系统容量要求取决于你的硬件和应用程序环境的具体详细信息。</span><span class="sxs-lookup"><span data-stu-id="eb39d-106">Your system capacity requirements will depend on the specific details of your hardware and application environment.</span></span> <span data-ttu-id="eb39d-107">此外，本文档中显示的性能数字是示例，你的结果可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="eb39d-107">Additionally, the performance numbers displayed in this document are examples and your results may vary.</span></span>

 

## <span data-ttu-id="eb39d-108">确定项目范围</span><span class="sxs-lookup"><span data-stu-id="eb39d-108">Determine the Project Scope</span></span>


<span data-ttu-id="eb39d-109">在设计 app-v 5.1 基础结构之前，必须确定项目的范围。</span><span class="sxs-lookup"><span data-stu-id="eb39d-109">Before you design the App-V 5.1 infrastructure, you must determine the project’s scope.</span></span> <span data-ttu-id="eb39d-110">范围包括确定哪些应用程序将在哪些应用程序中可用，还包括确定目标用户及其位置。</span><span class="sxs-lookup"><span data-stu-id="eb39d-110">The scope consists of determining which applications will be available virtually and to also identify the target users, and their locations.</span></span> <span data-ttu-id="eb39d-111">此信息将帮助确定应实现哪种类型的 App-v 5.1 基础结构。</span><span class="sxs-lookup"><span data-stu-id="eb39d-111">This information will help determine what type of App-V 5.1 infrastructure should be implemented.</span></span> <span data-ttu-id="eb39d-112">有关项目范围的决策必须基于你的组织的特定需求。</span><span class="sxs-lookup"><span data-stu-id="eb39d-112">Decisions about the scope of the project must be based on the specific needs of your organization.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="eb39d-113">任务</span><span class="sxs-lookup"><span data-stu-id="eb39d-113">Task</span></span></th>
<th align="left"><span data-ttu-id="eb39d-114">详细信息</span><span class="sxs-lookup"><span data-stu-id="eb39d-114">More Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="eb39d-115">确定应用程序范围</span><span class="sxs-lookup"><span data-stu-id="eb39d-115">Determine Application Scope</span></span></p></td>
<td align="left"><p><span data-ttu-id="eb39d-116">根据要虚拟化的应用程序，可以采用不同的方式设置 app-v 5.1 基础结构。</span><span class="sxs-lookup"><span data-stu-id="eb39d-116">Depending on the applications to be virtualized, the App-V 5.1 infrastructure can be set up in different ways.</span></span> <span data-ttu-id="eb39d-117">第一个任务是定义要虚拟化的应用程序。</span><span class="sxs-lookup"><span data-stu-id="eb39d-117">The first task is to define what applications you want to virtualize.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="eb39d-118">确定位置范围</span><span class="sxs-lookup"><span data-stu-id="eb39d-118">Determine Location Scope</span></span></p></td>
<td align="left"><p><span data-ttu-id="eb39d-119">"位置范围" 指的是你计划运行虚拟化应用程序的物理位置（例如，企业范围或特定地理位置）。</span><span class="sxs-lookup"><span data-stu-id="eb39d-119">Location scope refers to the physical locations (for example, enterprise-wide or a specific geographic location) where you plan to run the virtualized applications.</span></span> <span data-ttu-id="eb39d-120">它还可以指将运行虚拟应用程序的用户群体（例如单个部门）。</span><span class="sxs-lookup"><span data-stu-id="eb39d-120">It can also refer to the user population (for example, a single department) who will run the virtual applications.</span></span> <span data-ttu-id="eb39d-121">你应该获得一个网络图，其中包括连接路径以及每个位置的可用带宽以及使用虚拟化应用程序的用户数和 WAN 链接速度。</span><span class="sxs-lookup"><span data-stu-id="eb39d-121">You should obtain a network map that includes the connection paths as well as available bandwidth to each location and the number of users using virtualized applications and the WAN link speed.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="eb39d-122">确定所需的 App-v 5.1 基础结构</span><span class="sxs-lookup"><span data-stu-id="eb39d-122">Determine Which App-V 5.1 Infrastructure is Required</span></span>


<span data-ttu-id="eb39d-123">**重要提示** 以下两个模型都需要在计划运行虚拟应用程序的计算机上安装 app-v 5.1 客户端。</span><span class="sxs-lookup"><span data-stu-id="eb39d-123">**Important** Both of the following models require the App-V 5.1 client to be installed on the computer where you plan to run virtual applications.</span></span>

<span data-ttu-id="eb39d-124">你还可以使用电子软件分发（ESD）解决方案（如 Microsoft 系统中心配置管理器）管理你的 App-v 5.1 环境。</span><span class="sxs-lookup"><span data-stu-id="eb39d-124">You can also manage your App-V 5.1 environment using an Electronic Software Distribution (ESD) solution such as Microsoft Systems Center Configuration Manager.</span></span> <span data-ttu-id="eb39d-125">有关详细信息，请参阅[如何使用电子软件分发部署 app-v 5.1 程序包](how-to-deploy-app-v-51-packages-using-electronic-software-distribution.md)。</span><span class="sxs-lookup"><span data-stu-id="eb39d-125">For more information see [How to deploy App-V 5.1 Packages Using Electronic Software Distribution](how-to-deploy-app-v-51-packages-using-electronic-software-distribution.md).</span></span>

 

-   <span data-ttu-id="eb39d-126">**独立模型**-独立模型允许虚拟应用程序支持 Windows 安装程序，可在不进行流式处理的情况下分发。</span><span class="sxs-lookup"><span data-stu-id="eb39d-126">**Standalone Model** - The standalone model allows virtual applications to be Windows Installer-enabled for distribution without streaming.</span></span> <span data-ttu-id="eb39d-127">独立模式下的 app-v 5.1 包括排序器和客户端;不需要其他组件。</span><span class="sxs-lookup"><span data-stu-id="eb39d-127">App-V 5.1 in Standalone Mode consists of the sequencer and the client; no additional components are required.</span></span> <span data-ttu-id="eb39d-128">使用名为 "排序" 的过程为虚拟化准备了应用程序。</span><span class="sxs-lookup"><span data-stu-id="eb39d-128">Applications are prepared for virtualization using a process called sequencing.</span></span> <span data-ttu-id="eb39d-129">有关详细信息，请参阅[规划 app-v 5.1 Sequencer 和客户端部署](planning-for-the-app-v-51-sequencer-and-client-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="eb39d-129">For more information see, [Planning for the App-V 5.1 Sequencer and Client Deployment](planning-for-the-app-v-51-sequencer-and-client-deployment.md).</span></span> <span data-ttu-id="eb39d-130">建议在以下情况下使用独立模型：</span><span class="sxs-lookup"><span data-stu-id="eb39d-130">The stand-alone model is recommended for the following scenarios:</span></span>

    -   <span data-ttu-id="eb39d-131">通过断开连接的远程用户无法连接到 app-v 5.1 基础结构。</span><span class="sxs-lookup"><span data-stu-id="eb39d-131">With disconnected remote users who cannot connect to the App-V 5.1 infrastructure.</span></span>

    -   <span data-ttu-id="eb39d-132">运行软件管理系统（如 Configuration Manager 2012）时。</span><span class="sxs-lookup"><span data-stu-id="eb39d-132">When you are running a software management system, such as Configuration Manager 2012.</span></span>

    -   <span data-ttu-id="eb39d-133">当网络带宽限制抑制电子软件分发时。</span><span class="sxs-lookup"><span data-stu-id="eb39d-133">When network bandwidth limitations inhibit electronic software distribution.</span></span>

-   <span data-ttu-id="eb39d-134">**完整基础结构模型**-完整的基础结构模型提供软件分发、管理和报告功能;它还包括跨网络的应用程序流。</span><span class="sxs-lookup"><span data-stu-id="eb39d-134">**Full Infrastructure Model** - The full infrastructure model provides for software distribution, management, and reporting capabilities; it also includes the streaming of applications across the network.</span></span> <span data-ttu-id="eb39d-135">App-v 5.1 完整基础结构模型由一个或多个 App-v 5.1 管理服务器组成。</span><span class="sxs-lookup"><span data-stu-id="eb39d-135">The App-V 5.1 Full Infrastructure Model consists of one or more App-V 5.1 management servers.</span></span> <span data-ttu-id="eb39d-136">管理服务器可用于将应用程序发布到所有客户端。</span><span class="sxs-lookup"><span data-stu-id="eb39d-136">The Management Server can be used to publish applications to all clients.</span></span> <span data-ttu-id="eb39d-137">发布过程将虚拟应用程序图标和快捷方式放在目标计算机上。</span><span class="sxs-lookup"><span data-stu-id="eb39d-137">The publishing process places the virtual application icons and shortcuts on the target computer.</span></span> <span data-ttu-id="eb39d-138">它还可以将应用程序流式传输到本地用户。</span><span class="sxs-lookup"><span data-stu-id="eb39d-138">It can also stream applications to local users.</span></span> <span data-ttu-id="eb39d-139">有关安装管理服务器的详细信息，请参阅[规划 app-v 5.1 服务器部署](planning-for-the-app-v-51-server-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="eb39d-139">For more information about installing the management server see, [Planning for the App-V 5.1 Server Deployment](planning-for-the-app-v-51-server-deployment.md).</span></span> <span data-ttu-id="eb39d-140">建议在以下情况下使用完整的基础结构模型：</span><span class="sxs-lookup"><span data-stu-id="eb39d-140">The full infrastructure model is recommended for the following scenarios:</span></span>

    <span data-ttu-id="eb39d-141">**重要提示** App-v 5.1 完整基础结构模型要求 Microsoft SQL Server 存储配置数据。</span><span class="sxs-lookup"><span data-stu-id="eb39d-141">**Important** The App-V 5.1 full infrastructure model requires Microsoft SQL Server to store configuration data.</span></span> <span data-ttu-id="eb39d-142">有关详细信息，请参阅[应用 V 5.1 支持的配置](app-v-51-supported-configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="eb39d-142">For more information see [App-V 5.1 Supported Configurations](app-v-51-supported-configurations.md).</span></span>

     

    -   <span data-ttu-id="eb39d-143">希望使用管理服务器将应用程序发布到目标计算机时。</span><span class="sxs-lookup"><span data-stu-id="eb39d-143">When you want to use the Management Server to publish the application to target computers.</span></span>

    -   <span data-ttu-id="eb39d-144">快速调配目标计算机的应用程序。</span><span class="sxs-lookup"><span data-stu-id="eb39d-144">For rapid provisioning of applications to target computers.</span></span>

    -   <span data-ttu-id="eb39d-145">希望使用 app-v 5.1 报告时。</span><span class="sxs-lookup"><span data-stu-id="eb39d-145">When you want to use App-V 5.1 reporting.</span></span>

## <span data-ttu-id="eb39d-146">端到端服务器规模调整指南</span><span class="sxs-lookup"><span data-stu-id="eb39d-146">End-to-end Server Sizing Guidance</span></span>


<span data-ttu-id="eb39d-147">以下部分提供了有关端到端应用-V 5.1 规模调整和规划的信息。</span><span class="sxs-lookup"><span data-stu-id="eb39d-147">The following section provides information about end-to-end App-V 5.1 sizing and planning.</span></span> <span data-ttu-id="eb39d-148">有关更多特定信息，请参阅后续部分。</span><span class="sxs-lookup"><span data-stu-id="eb39d-148">For more specific information, refer to the subsequent sections.</span></span>

<span data-ttu-id="eb39d-149">**注意** 客户端上的往返行程响应时间是运行 App-v 5.1 客户端以接收来自发布服务器成功通知的计算机所用的时间。</span><span class="sxs-lookup"><span data-stu-id="eb39d-149">**Note** Round trip response time on the client is the time taken by the computer running the App-V 5.1 client to receive a successful notification from the publishing server.</span></span> <span data-ttu-id="eb39d-150">发布服务器上的往返行程响应时间是计算机运行发布服务器以接收来自管理服务器的成功程序包元数据更新所用的时间。</span><span class="sxs-lookup"><span data-stu-id="eb39d-150">Round trip response time on the publishing server is the time taken by the computer running the publishing server to receive a successful package metadata update from the management server.</span></span>

 

-   <span data-ttu-id="eb39d-151">20000客户端可以面向单个发布服务器，以便在可接受的往返行程时间内进行程序包刷新。</span><span class="sxs-lookup"><span data-stu-id="eb39d-151">20,000 clients can target a single publishing server to obtain the package refreshes in an acceptable round trip time.</span></span> <span data-ttu-id="eb39d-152">（ &lt; 3 秒）</span><span class="sxs-lookup"><span data-stu-id="eb39d-152">(&lt;3 seconds)</span></span>

-   <span data-ttu-id="eb39d-153">单个管理服务器最多可支持50发布服务器，以便在可接受的往返行程时间内更新软件包元数据。</span><span class="sxs-lookup"><span data-stu-id="eb39d-153">A single management server can support up to 50 publishing servers for package metadata refreshes in an acceptable round trip time.</span></span> <span data-ttu-id="eb39d-154">（ &lt; 5 秒）</span><span class="sxs-lookup"><span data-stu-id="eb39d-154">(&lt;5 seconds)</span></span>

## <a href="" id="---------app-v-5-1-management-server-capacity-planning-recommendations"></a> <span data-ttu-id="eb39d-155">App-v 5.1 管理服务器容量规划建议</span><span class="sxs-lookup"><span data-stu-id="eb39d-155">App-V 5.1 Management Server Capacity Planning Recommendations</span></span>


<span data-ttu-id="eb39d-156">App-v 5.1 发布服务器需要管理服务器才能进行程序包刷新请求和程序包刷新响应。</span><span class="sxs-lookup"><span data-stu-id="eb39d-156">The App-V 5.1 publishing servers require the management server for package refresh requests and package refresh responses.</span></span> <span data-ttu-id="eb39d-157">然后，管理服务器将信息发送到管理数据库以检索信息。</span><span class="sxs-lookup"><span data-stu-id="eb39d-157">The management server then sends the information to the management database to retrieve information.</span></span> <span data-ttu-id="eb39d-158">有关 App-V 5.1 管理服务器支持的配置的详细信息，请参阅[app-v 5.1 支持的配置](app-v-51-supported-configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="eb39d-158">For more information about App-V 5.1 management server supported configurations see [App-V 5.1 Supported Configurations](app-v-51-supported-configurations.md).</span></span>

<span data-ttu-id="eb39d-159">**注意** App-v 5.1 发布服务器上的默认刷新时间是十分钟。</span><span class="sxs-lookup"><span data-stu-id="eb39d-159">**Note** The default refresh time on the App-V 5.1 publishing server is ten minutes.</span></span>

 

<span data-ttu-id="eb39d-160">当多个同时发布服务器与单个管理服务器联系以进行软件包元数据刷新时，以下三个因素会影响发布服务器上的往返行程响应时间：</span><span class="sxs-lookup"><span data-stu-id="eb39d-160">When multiple simultaneous publishing servers contact a single management server for package metadata refreshes, the following three factors influence the round trip response time on the publishing server:</span></span>

1.  <span data-ttu-id="eb39d-161">同时请求的发布服务器数。</span><span class="sxs-lookup"><span data-stu-id="eb39d-161">Number of publishing servers making simultaneous requests.</span></span>

2.  <span data-ttu-id="eb39d-162">管理服务器上配置的连接组的数量。</span><span class="sxs-lookup"><span data-stu-id="eb39d-162">Number of connection groups configured on the management server.</span></span>

3.  <span data-ttu-id="eb39d-163">管理服务器上配置的访问组数。</span><span class="sxs-lookup"><span data-stu-id="eb39d-163">Number of access groups configured on the management server.</span></span>

<span data-ttu-id="eb39d-164">下表显示了影响往返行程时间的每个因素的详细信息。</span><span class="sxs-lookup"><span data-stu-id="eb39d-164">The following table displays more information about each factor that impacts round trip time.</span></span>

<span data-ttu-id="eb39d-165">**注意** 往返行程响应时间是计算机运行 app-v 5.1 发布服务器以接收来自管理服务器的成功程序包元数据更新所用的时间。</span><span class="sxs-lookup"><span data-stu-id="eb39d-165">**Note** Round trip response time is the time taken by the computer running the App-V 5.1 publishing server to receive a successful package metadata update from the management server.</span></span>

 

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="eb39d-166">影响往返行程响应时间的因素</span><span class="sxs-lookup"><span data-stu-id="eb39d-166">Factors impacting round trip response time</span></span></th>
<th align="left"><span data-ttu-id="eb39d-167">详细信息</span><span class="sxs-lookup"><span data-stu-id="eb39d-167">More Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="eb39d-168">同时请求软件包元数据刷新的发布服务器数。</span><span class="sxs-lookup"><span data-stu-id="eb39d-168">The number of publishing servers simultaneously requesting package metadata refreshes.</span></span></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-169">单个管理服务器最多可以响应同时请求发布元数据的320发布服务器。</span><span class="sxs-lookup"><span data-stu-id="eb39d-169">A single management server can respond to up to 320 publishing servers requesting publishing metadata simultaneously.</span></span></p></li>
<li><p><span data-ttu-id="eb39d-170">320 pub 服务器的往返行程响应时间为 ~ 40 秒。</span><span class="sxs-lookup"><span data-stu-id="eb39d-170">Round trip response time for 320 pub servers is ~40 seconds.</span></span></p></li>
<li><p><span data-ttu-id="eb39d-171">对于 &lt; 50 同时请求元数据的发布服务器，往返行程响应时间为 &lt; 5 秒。</span><span class="sxs-lookup"><span data-stu-id="eb39d-171">For &lt;50 publishing servers requesting metadata simultaneously, the round trip response time is &lt;5 seconds.</span></span></p></li>
<li><p><span data-ttu-id="eb39d-172">从50到320发布服务器，响应时间将线性增加（大约2x）。</span><span class="sxs-lookup"><span data-stu-id="eb39d-172">From 50 to 320 publishing servers, the response time increases linearly (approximately 2x).</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="eb39d-173">管理服务器上配置的连接组数。</span><span class="sxs-lookup"><span data-stu-id="eb39d-173">The number of connection groups configured on the management server.</span></span></p>
<p></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-174">对于最多100个连接组，发布服务器上的往返行程响应时间没有显著更改。</span><span class="sxs-lookup"><span data-stu-id="eb39d-174">For up to 100 connection groups, there is no significant change in the round trip response time on the publishing server.</span></span></p></li>
<li><p><span data-ttu-id="eb39d-175">对于 100-400 连接组，"往返行程" 响应时间中有较小的线性增加。</span><span class="sxs-lookup"><span data-stu-id="eb39d-175">For 100 - 400 connection groups, there is a minor linear increase in the round trip response time.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="eb39d-176">管理服务器上配置的访问组数。</span><span class="sxs-lookup"><span data-stu-id="eb39d-176">The number of access groups configured on the management server.</span></span></p>
<p></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-177">对于最多40访问组，发布服务器上的往返行程响应时间有一个线性（大约3倍）的增加。</span><span class="sxs-lookup"><span data-stu-id="eb39d-177">For up to 40 access groups, there is a linear (approximately 3x) increase in the round trip response time on the publishing server.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="eb39d-178">下表显示了上述每个因素的示例值。</span><span class="sxs-lookup"><span data-stu-id="eb39d-178">The following table displays sample values for each of the previous factors.</span></span> <span data-ttu-id="eb39d-179">在每个变体中，120程序包从 App-v 5.1 管理服务器刷新。</span><span class="sxs-lookup"><span data-stu-id="eb39d-179">In each variation, 120 packages are refreshed from the App-V 5.1management server.</span></span>

<table>
<colgroup>
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="eb39d-180">情形</span><span class="sxs-lookup"><span data-stu-id="eb39d-180">Scenario</span></span></th>
<th align="left"><span data-ttu-id="eb39d-181">变体</span><span class="sxs-lookup"><span data-stu-id="eb39d-181">Variation</span></span></th>
<th align="left"><span data-ttu-id="eb39d-182">连接组数</span><span class="sxs-lookup"><span data-stu-id="eb39d-182">Number of connection groups</span></span></th>
<th align="left"><span data-ttu-id="eb39d-183">访问组数</span><span class="sxs-lookup"><span data-stu-id="eb39d-183">Number of access groups</span></span></th>
<th align="left"><span data-ttu-id="eb39d-184">发布服务器数</span><span class="sxs-lookup"><span data-stu-id="eb39d-184">Number of publishing servers</span></span></th>
<th align="left"><span data-ttu-id="eb39d-185">网络连接类型发布服务器/管理服务器</span><span class="sxs-lookup"><span data-stu-id="eb39d-185">Network connection type publishing server / management server</span></span></th>
<th align="left"><span data-ttu-id="eb39d-186">发布服务器上的往返行程响应时间（以秒为单位）</span><span class="sxs-lookup"><span data-stu-id="eb39d-186">Round trip response time on the publishing server (in seconds)</span></span></th>
<th align="left"><span data-ttu-id="eb39d-187">管理服务器上的 CPU 使用率</span><span class="sxs-lookup"><span data-stu-id="eb39d-187">CPU utilization on management server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="eb39d-188">同时发布服务器，同时联系管理服务器以发布元数据。</span><span class="sxs-lookup"><span data-stu-id="eb39d-188">Publishing servers simultaneously contacting management server for publishing metadata.</span></span></p></td>
<td align="left"><p><span data-ttu-id="eb39d-189">发布服务器数</span><span class="sxs-lookup"><span data-stu-id="eb39d-189">Number of publishing servers</span></span></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-190">0</span><span class="sxs-lookup"><span data-stu-id="eb39d-190">0</span></span></p></li>
<li><p><span data-ttu-id="eb39d-191">0</span><span class="sxs-lookup"><span data-stu-id="eb39d-191">0</span></span></p></li>
<li><p><span data-ttu-id="eb39d-192">0</span><span class="sxs-lookup"><span data-stu-id="eb39d-192">0</span></span></p></li>
<li><p><span data-ttu-id="eb39d-193">0</span><span class="sxs-lookup"><span data-stu-id="eb39d-193">0</span></span></p></li>
<li><p><span data-ttu-id="eb39d-194">0</span><span class="sxs-lookup"><span data-stu-id="eb39d-194">0</span></span></p></li>
<li><p><span data-ttu-id="eb39d-195">0</span><span class="sxs-lookup"><span data-stu-id="eb39d-195">0</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-196">raid-1</span><span class="sxs-lookup"><span data-stu-id="eb39d-196">1</span></span></p></li>
<li><p><span data-ttu-id="eb39d-197">raid-1</span><span class="sxs-lookup"><span data-stu-id="eb39d-197">1</span></span></p></li>
<li><p><span data-ttu-id="eb39d-198">raid-1</span><span class="sxs-lookup"><span data-stu-id="eb39d-198">1</span></span></p></li>
<li><p><span data-ttu-id="eb39d-199">raid-1</span><span class="sxs-lookup"><span data-stu-id="eb39d-199">1</span></span></p></li>
<li><p><span data-ttu-id="eb39d-200">raid-1</span><span class="sxs-lookup"><span data-stu-id="eb39d-200">1</span></span></p></li>
<li><p><span data-ttu-id="eb39d-201">raid-1</span><span class="sxs-lookup"><span data-stu-id="eb39d-201">1</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-202">50</span><span class="sxs-lookup"><span data-stu-id="eb39d-202">50</span></span></p></li>
<li><p><span data-ttu-id="eb39d-203">100</span><span class="sxs-lookup"><span data-stu-id="eb39d-203">100</span></span></p></li>
<li><p><span data-ttu-id="eb39d-204">200</span><span class="sxs-lookup"><span data-stu-id="eb39d-204">200</span></span></p></li>
<li><p><span data-ttu-id="eb39d-205">300</span><span class="sxs-lookup"><span data-stu-id="eb39d-205">300</span></span></p></li>
<li><p><span data-ttu-id="eb39d-206">315</span><span class="sxs-lookup"><span data-stu-id="eb39d-206">315</span></span></p></li>
<li><p><span data-ttu-id="eb39d-207">320</span><span class="sxs-lookup"><span data-stu-id="eb39d-207">320</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-208">LAN</span><span class="sxs-lookup"><span data-stu-id="eb39d-208">LAN</span></span></p></li>
<li><p><span data-ttu-id="eb39d-209">LAN</span><span class="sxs-lookup"><span data-stu-id="eb39d-209">LAN</span></span></p></li>
<li><p><span data-ttu-id="eb39d-210">LAN</span><span class="sxs-lookup"><span data-stu-id="eb39d-210">LAN</span></span></p></li>
<li><p><span data-ttu-id="eb39d-211">LAN</span><span class="sxs-lookup"><span data-stu-id="eb39d-211">LAN</span></span></p></li>
<li><p><span data-ttu-id="eb39d-212">LAN</span><span class="sxs-lookup"><span data-stu-id="eb39d-212">LAN</span></span></p></li>
<li><p><span data-ttu-id="eb39d-213">LAN</span><span class="sxs-lookup"><span data-stu-id="eb39d-213">LAN</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-214">级</span><span class="sxs-lookup"><span data-stu-id="eb39d-214">5</span></span></p></li>
<li><p><span data-ttu-id="eb39d-215">10</span><span class="sxs-lookup"><span data-stu-id="eb39d-215">10</span></span></p></li>
<li><p><span data-ttu-id="eb39d-216">19</span><span class="sxs-lookup"><span data-stu-id="eb39d-216">19</span></span></p></li>
<li><p><span data-ttu-id="eb39d-217">32</span><span class="sxs-lookup"><span data-stu-id="eb39d-217">32</span></span></p></li>
<li><p><span data-ttu-id="eb39d-218">大约</span><span class="sxs-lookup"><span data-stu-id="eb39d-218">30</span></span></p></li>
<li><p><span data-ttu-id="eb39d-219">37</span><span class="sxs-lookup"><span data-stu-id="eb39d-219">37</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-220">17</span><span class="sxs-lookup"><span data-stu-id="eb39d-220">17</span></span></p></li>
<li><p><span data-ttu-id="eb39d-221">17</span><span class="sxs-lookup"><span data-stu-id="eb39d-221">17</span></span></p></li>
<li><p><span data-ttu-id="eb39d-222">17</span><span class="sxs-lookup"><span data-stu-id="eb39d-222">17</span></span></p></li>
<li><p><span data-ttu-id="eb39d-223">岁</span><span class="sxs-lookup"><span data-stu-id="eb39d-223">15</span></span></p></li>
<li><p><span data-ttu-id="eb39d-224">17</span><span class="sxs-lookup"><span data-stu-id="eb39d-224">17</span></span></p></li>
<li><p><span data-ttu-id="eb39d-225">岁</span><span class="sxs-lookup"><span data-stu-id="eb39d-225">15</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="eb39d-226">发布元数据包含连接组</span><span class="sxs-lookup"><span data-stu-id="eb39d-226">Publishing metadata contains connection groups</span></span></p></td>
<td align="left"><p><span data-ttu-id="eb39d-227">连接组数</span><span class="sxs-lookup"><span data-stu-id="eb39d-227">Number of connection groups</span></span></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-228">10</span><span class="sxs-lookup"><span data-stu-id="eb39d-228">10</span></span></p></li>
<li><p><span data-ttu-id="eb39d-229">50</span><span class="sxs-lookup"><span data-stu-id="eb39d-229">50</span></span></p></li>
<li><p><span data-ttu-id="eb39d-230">100</span><span class="sxs-lookup"><span data-stu-id="eb39d-230">100</span></span></p></li>
<li><p><span data-ttu-id="eb39d-231">150</span><span class="sxs-lookup"><span data-stu-id="eb39d-231">150</span></span></p></li>
<li><p><span data-ttu-id="eb39d-232">300</span><span class="sxs-lookup"><span data-stu-id="eb39d-232">300</span></span></p></li>
<li><p><span data-ttu-id="eb39d-233">400</span><span class="sxs-lookup"><span data-stu-id="eb39d-233">400</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-234">raid-1</span><span class="sxs-lookup"><span data-stu-id="eb39d-234">1</span></span></p></li>
<li><p><span data-ttu-id="eb39d-235">raid-1</span><span class="sxs-lookup"><span data-stu-id="eb39d-235">1</span></span></p></li>
<li><p><span data-ttu-id="eb39d-236">raid-1</span><span class="sxs-lookup"><span data-stu-id="eb39d-236">1</span></span></p></li>
<li><p><span data-ttu-id="eb39d-237">raid-1</span><span class="sxs-lookup"><span data-stu-id="eb39d-237">1</span></span></p></li>
<li><p><span data-ttu-id="eb39d-238">raid-1</span><span class="sxs-lookup"><span data-stu-id="eb39d-238">1</span></span></p></li>
<li><p><span data-ttu-id="eb39d-239">raid-1</span><span class="sxs-lookup"><span data-stu-id="eb39d-239">1</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-240">100</span><span class="sxs-lookup"><span data-stu-id="eb39d-240">100</span></span></p></li>
<li><p><span data-ttu-id="eb39d-241">100</span><span class="sxs-lookup"><span data-stu-id="eb39d-241">100</span></span></p></li>
<li><p><span data-ttu-id="eb39d-242">100</span><span class="sxs-lookup"><span data-stu-id="eb39d-242">100</span></span></p></li>
<li><p><span data-ttu-id="eb39d-243">100</span><span class="sxs-lookup"><span data-stu-id="eb39d-243">100</span></span></p></li>
<li><p><span data-ttu-id="eb39d-244">100</span><span class="sxs-lookup"><span data-stu-id="eb39d-244">100</span></span></p></li>
<li><p><span data-ttu-id="eb39d-245">100</span><span class="sxs-lookup"><span data-stu-id="eb39d-245">100</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-246">LAN</span><span class="sxs-lookup"><span data-stu-id="eb39d-246">LAN</span></span></p></li>
<li><p><span data-ttu-id="eb39d-247">LAN</span><span class="sxs-lookup"><span data-stu-id="eb39d-247">LAN</span></span></p></li>
<li><p><span data-ttu-id="eb39d-248">LAN</span><span class="sxs-lookup"><span data-stu-id="eb39d-248">LAN</span></span></p></li>
<li><p><span data-ttu-id="eb39d-249">LAN</span><span class="sxs-lookup"><span data-stu-id="eb39d-249">LAN</span></span></p></li>
<li><p><span data-ttu-id="eb39d-250">LAN</span><span class="sxs-lookup"><span data-stu-id="eb39d-250">LAN</span></span></p></li>
<li><p><span data-ttu-id="eb39d-251">LAN</span><span class="sxs-lookup"><span data-stu-id="eb39d-251">LAN</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-252">10</span><span class="sxs-lookup"><span data-stu-id="eb39d-252">10</span></span></p></li>
<li><p><span data-ttu-id="eb39d-253">11</span><span class="sxs-lookup"><span data-stu-id="eb39d-253">11</span></span></p></li>
<li><p><span data-ttu-id="eb39d-254">11</span><span class="sxs-lookup"><span data-stu-id="eb39d-254">11</span></span></p></li>
<li><p><span data-ttu-id="eb39d-255">utf-16</span><span class="sxs-lookup"><span data-stu-id="eb39d-255">16</span></span></p></li>
<li><p><span data-ttu-id="eb39d-256">22</span><span class="sxs-lookup"><span data-stu-id="eb39d-256">22</span></span></p></li>
<li><p><span data-ttu-id="eb39d-257">二十五</span><span class="sxs-lookup"><span data-stu-id="eb39d-257">25</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-258">17</span><span class="sxs-lookup"><span data-stu-id="eb39d-258">17</span></span></p></li>
<li><p><span data-ttu-id="eb39d-259">19</span><span class="sxs-lookup"><span data-stu-id="eb39d-259">19</span></span></p></li>
<li><p><span data-ttu-id="eb39d-260">22</span><span class="sxs-lookup"><span data-stu-id="eb39d-260">22</span></span></p></li>
<li><p><span data-ttu-id="eb39d-261">19</span><span class="sxs-lookup"><span data-stu-id="eb39d-261">19</span></span></p></li>
<li><p><span data-ttu-id="eb39d-262">名</span><span class="sxs-lookup"><span data-stu-id="eb39d-262">20</span></span></p></li>
<li><p><span data-ttu-id="eb39d-263">名</span><span class="sxs-lookup"><span data-stu-id="eb39d-263">20</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="eb39d-264">发布元数据包含访问组</span><span class="sxs-lookup"><span data-stu-id="eb39d-264">Publishing metadata contains access groups</span></span></p></td>
<td align="left"><p><span data-ttu-id="eb39d-265">访问组数</span><span class="sxs-lookup"><span data-stu-id="eb39d-265">Number of access groups</span></span></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-266">0</span><span class="sxs-lookup"><span data-stu-id="eb39d-266">0</span></span></p></li>
<li><p><span data-ttu-id="eb39d-267">0</span><span class="sxs-lookup"><span data-stu-id="eb39d-267">0</span></span></p></li>
<li><p><span data-ttu-id="eb39d-268">0</span><span class="sxs-lookup"><span data-stu-id="eb39d-268">0</span></span></p></li>
<li><p><span data-ttu-id="eb39d-269">0</span><span class="sxs-lookup"><span data-stu-id="eb39d-269">0</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-270">raid-1</span><span class="sxs-lookup"><span data-stu-id="eb39d-270">1</span></span></p></li>
<li><p><span data-ttu-id="eb39d-271">10</span><span class="sxs-lookup"><span data-stu-id="eb39d-271">10</span></span></p></li>
<li><p><span data-ttu-id="eb39d-272">名</span><span class="sxs-lookup"><span data-stu-id="eb39d-272">20</span></span></p></li>
<li><p><span data-ttu-id="eb39d-273">40</span><span class="sxs-lookup"><span data-stu-id="eb39d-273">40</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-274">100</span><span class="sxs-lookup"><span data-stu-id="eb39d-274">100</span></span></p></li>
<li><p><span data-ttu-id="eb39d-275">100</span><span class="sxs-lookup"><span data-stu-id="eb39d-275">100</span></span></p></li>
<li><p><span data-ttu-id="eb39d-276">100</span><span class="sxs-lookup"><span data-stu-id="eb39d-276">100</span></span></p></li>
<li><p><span data-ttu-id="eb39d-277">100</span><span class="sxs-lookup"><span data-stu-id="eb39d-277">100</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-278">LAN</span><span class="sxs-lookup"><span data-stu-id="eb39d-278">LAN</span></span></p></li>
<li><p><span data-ttu-id="eb39d-279">LAN</span><span class="sxs-lookup"><span data-stu-id="eb39d-279">LAN</span></span></p></li>
<li><p><span data-ttu-id="eb39d-280">LAN</span><span class="sxs-lookup"><span data-stu-id="eb39d-280">LAN</span></span></p></li>
<li><p><span data-ttu-id="eb39d-281">LAN</span><span class="sxs-lookup"><span data-stu-id="eb39d-281">LAN</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-282">10</span><span class="sxs-lookup"><span data-stu-id="eb39d-282">10</span></span></p></li>
<li><p><span data-ttu-id="eb39d-283">43</span><span class="sxs-lookup"><span data-stu-id="eb39d-283">43</span></span></p></li>
<li><p><span data-ttu-id="eb39d-284">153</span><span class="sxs-lookup"><span data-stu-id="eb39d-284">153</span></span></p></li>
<li><p><span data-ttu-id="eb39d-285">535</span><span class="sxs-lookup"><span data-stu-id="eb39d-285">535</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-286">17</span><span class="sxs-lookup"><span data-stu-id="eb39d-286">17</span></span></p></li>
<li><p><span data-ttu-id="eb39d-287">个</span><span class="sxs-lookup"><span data-stu-id="eb39d-287">26</span></span></p></li>
<li><p><span data-ttu-id="eb39d-288">全</span><span class="sxs-lookup"><span data-stu-id="eb39d-288">24</span></span></p></li>
<li><p><span data-ttu-id="eb39d-289">全</span><span class="sxs-lookup"><span data-stu-id="eb39d-289">24</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="eb39d-290">运行管理服务器的计算机的 CPU 使用率约为25%，与面向目标的发布服务器的数量无关。</span><span class="sxs-lookup"><span data-stu-id="eb39d-290">The CPU utilization of the computer running the management server is around 25% irrespective of the number of publishing servers targeting it.</span></span> <span data-ttu-id="eb39d-291">Microsoft SQL Server 数据库事务/秒、批处理请求/秒和用户连接与发布服务器的数量无关。</span><span class="sxs-lookup"><span data-stu-id="eb39d-291">The Microsoft SQL Server database transactions/sec, batch requests/sec and user connections are identical irrespective of the number of publishing servers.</span></span> <span data-ttu-id="eb39d-292">例如：交易/秒是 ~ 30、批处理请求 ~ 200 和用户连接 ~ 6。</span><span class="sxs-lookup"><span data-stu-id="eb39d-292">For example: Transactions/sec is ~30, batch requests ~200, and user connects ~6.</span></span>

<span data-ttu-id="eb39d-293">使用地理位置分散的部署，在这种情况下，管理服务器 & 发布服务器在其之间使用慢速链接网络，发布服务器上的往返行程响应时间在可接受的时间限制（ &lt; 5 秒）内，即使100同时请求同一台管理服务器也是如此。</span><span class="sxs-lookup"><span data-stu-id="eb39d-293">Using a geographically distributed deployment, where the management server & publishing servers utilize a slow link network between them, the round trip response time on the publishing servers is within acceptable time limits (&lt;5 seconds), even for 100 simultaneous requests on a single management server.</span></span>

<table>
<colgroup>
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="eb39d-294">情形</span><span class="sxs-lookup"><span data-stu-id="eb39d-294">Scenario</span></span></th>
<th align="left"><span data-ttu-id="eb39d-295">变体</span><span class="sxs-lookup"><span data-stu-id="eb39d-295">Variation</span></span></th>
<th align="left"><span data-ttu-id="eb39d-296">连接组数</span><span class="sxs-lookup"><span data-stu-id="eb39d-296">Number of connection groups</span></span></th>
<th align="left"><span data-ttu-id="eb39d-297">访问组数</span><span class="sxs-lookup"><span data-stu-id="eb39d-297">Number of access groups</span></span></th>
<th align="left"><span data-ttu-id="eb39d-298">发布服务器数</span><span class="sxs-lookup"><span data-stu-id="eb39d-298">Number of publishing servers</span></span></th>
<th align="left"><span data-ttu-id="eb39d-299">网络连接类型发布服务器/管理服务器</span><span class="sxs-lookup"><span data-stu-id="eb39d-299">Network connection type publishing server / management server</span></span></th>
<th align="left"><span data-ttu-id="eb39d-300">发布服务器上的往返行程响应时间（以秒为单位）</span><span class="sxs-lookup"><span data-stu-id="eb39d-300">Round trip response time on the publishing server (in seconds)</span></span></th>
<th align="left"><span data-ttu-id="eb39d-301">管理服务器上的 CPU 使用率</span><span class="sxs-lookup"><span data-stu-id="eb39d-301">CPU utilization on management server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="eb39d-302">发布服务器和管理服务器之间的网络连接</span><span class="sxs-lookup"><span data-stu-id="eb39d-302">Network connection between the publishing server and management server</span></span></p></td>
<td align="left"><p><span data-ttu-id="eb39d-303">1.5 Mbps 慢速链接网络</span><span class="sxs-lookup"><span data-stu-id="eb39d-303">1.5 Mbps Slow link Network</span></span></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-304">0</span><span class="sxs-lookup"><span data-stu-id="eb39d-304">0</span></span></p></li>
<li><p><span data-ttu-id="eb39d-305">0</span><span class="sxs-lookup"><span data-stu-id="eb39d-305">0</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-306">raid-1</span><span class="sxs-lookup"><span data-stu-id="eb39d-306">1</span></span></p></li>
<li><p><span data-ttu-id="eb39d-307">raid-1</span><span class="sxs-lookup"><span data-stu-id="eb39d-307">1</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-308">50</span><span class="sxs-lookup"><span data-stu-id="eb39d-308">50</span></span></p></li>
<li><p><span data-ttu-id="eb39d-309">100</span><span class="sxs-lookup"><span data-stu-id="eb39d-309">100</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-310">1.5 mbps 电缆 DSL</span><span class="sxs-lookup"><span data-stu-id="eb39d-310">1.5Mbps Cable DSL</span></span></p></li>
<li><p><span data-ttu-id="eb39d-311">1.5 mbps 电缆 DSL</span><span class="sxs-lookup"><span data-stu-id="eb39d-311">1.5Mbps Cable DSL</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-312">第</span><span class="sxs-lookup"><span data-stu-id="eb39d-312">4</span></span></p></li>
<li><p><span data-ttu-id="eb39d-313">级</span><span class="sxs-lookup"><span data-stu-id="eb39d-313">5</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-314">raid-1</span><span class="sxs-lookup"><span data-stu-id="eb39d-314">1</span></span></p></li>
<li><p><span data-ttu-id="eb39d-315">ppls-2</span><span class="sxs-lookup"><span data-stu-id="eb39d-315">2</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="eb39d-316">发布服务器和管理服务器之间的网络连接</span><span class="sxs-lookup"><span data-stu-id="eb39d-316">Network connection between the publishing server and management server</span></span></p></td>
<td align="left"><p><span data-ttu-id="eb39d-317">局域网/WIFI 网络</span><span class="sxs-lookup"><span data-stu-id="eb39d-317">LAN / WIFI Network</span></span></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-318">0</span><span class="sxs-lookup"><span data-stu-id="eb39d-318">0</span></span></p></li>
<li><p><span data-ttu-id="eb39d-319">0</span><span class="sxs-lookup"><span data-stu-id="eb39d-319">0</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-320">raid-1</span><span class="sxs-lookup"><span data-stu-id="eb39d-320">1</span></span></p></li>
<li><p><span data-ttu-id="eb39d-321">raid-1</span><span class="sxs-lookup"><span data-stu-id="eb39d-321">1</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-322">100</span><span class="sxs-lookup"><span data-stu-id="eb39d-322">100</span></span></p></li>
<li><p><span data-ttu-id="eb39d-323">200</span><span class="sxs-lookup"><span data-stu-id="eb39d-323">200</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-324">Wifi</span><span class="sxs-lookup"><span data-stu-id="eb39d-324">Wifi</span></span></p></li>
<li><p><span data-ttu-id="eb39d-325">Wifi</span><span class="sxs-lookup"><span data-stu-id="eb39d-325">Wifi</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-326">11</span><span class="sxs-lookup"><span data-stu-id="eb39d-326">11</span></span></p></li>
<li><p><span data-ttu-id="eb39d-327">名</span><span class="sxs-lookup"><span data-stu-id="eb39d-327">20</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-328">岁</span><span class="sxs-lookup"><span data-stu-id="eb39d-328">15</span></span></p></li>
<li><p><span data-ttu-id="eb39d-329">17</span><span class="sxs-lookup"><span data-stu-id="eb39d-329">17</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="eb39d-330">无论管理服务器和发布服务器通过慢速链接网络连接还是高速网络，管理服务器都可以在30分钟内处理大约15000程序包刷新请求。</span><span class="sxs-lookup"><span data-stu-id="eb39d-330">Whether the management server and publishing servers are connected over a slow link network, or a high speed network, the management server can handle approximately 15,000 package refresh requests in 30 minutes.</span></span>

## <a href="" id="---------app-v-5-1-reporting-server-capacity-planning-recommendations"></a> <span data-ttu-id="eb39d-331">App-v 5.1 报告服务器容量规划建议</span><span class="sxs-lookup"><span data-stu-id="eb39d-331">App-V 5.1 Reporting Server Capacity Planning Recommendations</span></span>


<span data-ttu-id="eb39d-332">App-v 5.1 客户端将报告数据发送到报告服务器。</span><span class="sxs-lookup"><span data-stu-id="eb39d-332">App-V 5.1 clients send reporting data to the reporting server.</span></span> <span data-ttu-id="eb39d-333">然后，报告服务器将在 Microsoft SQL Server 数据库中记录信息，并将成功的通知返回到运行 App-v 5.1 客户端的计算机上。</span><span class="sxs-lookup"><span data-stu-id="eb39d-333">The reporting server then records the information in the Microsoft SQL Server database and returns a successful notification back to the computer running App-V 5.1 client.</span></span> <span data-ttu-id="eb39d-334">有关应用-V 5.1 报告服务器支持的配置的详细信息，请参阅[app-v 5.1 支持的配置](app-v-51-supported-configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="eb39d-334">For more information about App-V 5.1 Reporting Server supported configurations see [App-V 5.1 Supported Configurations](app-v-51-supported-configurations.md).</span></span>

<span data-ttu-id="eb39d-335">**注意** 往返行程响应时间是运行 App-v 5.1 客户端以将报告信息发送到报告服务器并从报告服务器接收成功通知所用的时间。</span><span class="sxs-lookup"><span data-stu-id="eb39d-335">**Note** Round trip response time is the time taken by the computer running the App-V 5.1 client to send the reporting information to the reporting server and receive a successful notification from the reporting server.</span></span>

 

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="eb39d-336">情形</span><span class="sxs-lookup"><span data-stu-id="eb39d-336">Scenario</span></span></th>
<th align="left"><span data-ttu-id="eb39d-337">摘要</span><span class="sxs-lookup"><span data-stu-id="eb39d-337">Summary</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="eb39d-338">多个 App-v 5.1 客户端同时向报告服务器发送报告信息。</span><span class="sxs-lookup"><span data-stu-id="eb39d-338">Multiple App-V 5.1 clients send reporting information to the reporting server simultaneously.</span></span></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-339">来自报告服务器的往返行程响应时间为500客户端的2.6 秒。</span><span class="sxs-lookup"><span data-stu-id="eb39d-339">Round trip response time from the reporting server is 2.6 seconds for 500 clients.</span></span></p></li>
<li><p><span data-ttu-id="eb39d-340">来自报告服务器的往返行程响应时间为1000客户端的5.65 秒。</span><span class="sxs-lookup"><span data-stu-id="eb39d-340">Round trip response time from the reporting server is 5.65 seconds for 1000 clients.</span></span></p></li>
<li><p><span data-ttu-id="eb39d-341">往返行程响应时间根据客户数量线性增加。</span><span class="sxs-lookup"><span data-stu-id="eb39d-341">Round trip response time increases linearly depending on number of clients.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="eb39d-342">报告服务器每秒处理的请求数。</span><span class="sxs-lookup"><span data-stu-id="eb39d-342">Requests per second processed by the reporting server.</span></span></p>
<p></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-343">单个报告服务器和单个数据库最多可处理每秒139请求。</span><span class="sxs-lookup"><span data-stu-id="eb39d-343">A single reporting server and a single database, can process a maximum of 139 requests per second.</span></span> <span data-ttu-id="eb39d-344">平均值为每秒121请求。</span><span class="sxs-lookup"><span data-stu-id="eb39d-344">The average is 121 requests/second.</span></span></p></li>
<li><p><span data-ttu-id="eb39d-345">将两个报表服务器与同一 Microsoft SQL Server 数据库一起使用时，平均请求/秒类似于单个报表服务器 = ~ 127，每秒最多为278请求。</span><span class="sxs-lookup"><span data-stu-id="eb39d-345">Using two reporting servers reporting to the same Microsoft SQL Server database, the average requests/second is similar to a single reporting server = ~127, with a max of 278 requests/second.</span></span></p></li>
<li><p><span data-ttu-id="eb39d-346">单个报告服务器可以处理500并发/活动连接。</span><span class="sxs-lookup"><span data-stu-id="eb39d-346">A single reporting server can process 500 concurrent/active connections.</span></span></p></li>
<li><p><span data-ttu-id="eb39d-347">单个报告服务器可以处理最大1500并发连接。</span><span class="sxs-lookup"><span data-stu-id="eb39d-347">A single reporting server can process a maximum 1500 concurrent connections.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="eb39d-348">报告数据库。</span><span class="sxs-lookup"><span data-stu-id="eb39d-348">Reporting Database.</span></span></p>
<p></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-349">运行 Microsoft SQL Server 的计算机上的锁定争用是请求/秒的限制因素。</span><span class="sxs-lookup"><span data-stu-id="eb39d-349">Lock contention on the computer running Microsoft SQL Server is the limiting factor for requests/second.</span></span></p></li>
<li><p><span data-ttu-id="eb39d-350">吞吐量和响应时间与数据库大小无关。</span><span class="sxs-lookup"><span data-stu-id="eb39d-350">Throughput and response time are independent of database size.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="eb39d-351">**计算随机延迟**：</span><span class="sxs-lookup"><span data-stu-id="eb39d-351">**Calculating random delay**:</span></span>

<span data-ttu-id="eb39d-352">随机延迟指定将数据发送到报告服务器的最大延迟（以分钟为单位）。</span><span class="sxs-lookup"><span data-stu-id="eb39d-352">The random delay specifies the maximum delay (in minutes) for data to be sent to the reporting server.</span></span> <span data-ttu-id="eb39d-353">当计划任务启动时，客户端会在**0**和**ReportingRandomDelay**之间生成一个随机延迟，并在发送数据之前等待指定的持续时间。</span><span class="sxs-lookup"><span data-stu-id="eb39d-353">When the scheduled task is started, the client generates a random delay between **0** and **ReportingRandomDelay** and will wait the specified duration before sending data.</span></span>

<span data-ttu-id="eb39d-354">随机延迟 = 4 \ \* 客户端数/每秒平均请求数。</span><span class="sxs-lookup"><span data-stu-id="eb39d-354">Random delay = 4 \* number of clients / average requests per second.</span></span>

<span data-ttu-id="eb39d-355">示例：对于500客户端，每秒120个请求，随机延迟是，4 \ \* 500/120 = ~ 17 分钟。</span><span class="sxs-lookup"><span data-stu-id="eb39d-355">Example: For 500 clients, with 120 requests per second, the Random delay is, 4 \* 500 / 120 = ~17 minutes.</span></span>

## <a href="" id="---------app-v-5-1-publishing-server-capacity-planning-recommendations"></a> <span data-ttu-id="eb39d-356">App-v 5.1 发布服务器容量规划建议</span><span class="sxs-lookup"><span data-stu-id="eb39d-356">App-V 5.1 Publishing Server Capacity Planning Recommendations</span></span>


<span data-ttu-id="eb39d-357">运行 App-V 5.1 客户端的计算机连接到 app-v 5.1 发布服务器以发送发布刷新请求和接收响应。</span><span class="sxs-lookup"><span data-stu-id="eb39d-357">Computers running the App-V 5.1 client connect to the App-V 5.1 publishing server to send a publishing refresh request and to receive a response.</span></span> <span data-ttu-id="eb39d-358">在运行 App-v 5.1 客户端的计算机上测量往返行程响应时间。</span><span class="sxs-lookup"><span data-stu-id="eb39d-358">Round trip response time is measured on the computer running the App-V 5.1 client.</span></span> <span data-ttu-id="eb39d-359">在发布服务器上测量处理器时间。</span><span class="sxs-lookup"><span data-stu-id="eb39d-359">Processor time is measured on the publishing server.</span></span> <span data-ttu-id="eb39d-360">有关应用-V 5.1 发布服务器支持的配置的详细信息，请参阅[app-v 5.1 支持的配置](app-v-51-supported-configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="eb39d-360">For more information about App-V 5.1 Publishing Server supported configurations see [App-V 5.1 Supported Configurations](app-v-51-supported-configurations.md).</span></span>

<span data-ttu-id="eb39d-361">**重要提示** 下表显示了设置 App-v 5.1 发布服务器时要考虑的主要因素：</span><span class="sxs-lookup"><span data-stu-id="eb39d-361">**Important** The following list displays the main factors to consider when setting up the App-V 5.1 publishing server:</span></span>

-   <span data-ttu-id="eb39d-362">同时连接到单个发布服务器的客户端数。</span><span class="sxs-lookup"><span data-stu-id="eb39d-362">The number of clients connecting simultaneously to a single publishing server.</span></span>

-   <span data-ttu-id="eb39d-363">每次刷新中的程序包数。</span><span class="sxs-lookup"><span data-stu-id="eb39d-363">The number of packages in each refresh.</span></span>

-   <span data-ttu-id="eb39d-364">客户端和 app-v 5.1 发布服务器之间的环境中的可用网络带宽。</span><span class="sxs-lookup"><span data-stu-id="eb39d-364">The available network bandwidth in your environment between the client and the App-V 5.1 publishing server.</span></span>

 

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="eb39d-365">情形</span><span class="sxs-lookup"><span data-stu-id="eb39d-365">Scenario</span></span></th>
<th align="left"><span data-ttu-id="eb39d-366">摘要</span><span class="sxs-lookup"><span data-stu-id="eb39d-366">Summary</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="eb39d-367">多个应用程序-V 5.1 客户端同时连接到一个发布服务器。</span><span class="sxs-lookup"><span data-stu-id="eb39d-367">Multiple App-V 5.1 clients connect to a single publishing server simultaneously.</span></span></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-368">运行双核处理器的发布服务器最多可以响应同时请求刷新的5000客户端。</span><span class="sxs-lookup"><span data-stu-id="eb39d-368">A publishing server running dual core processors can respond to at most 5000 clients requesting a refresh simultaneously.</span></span></p></li>
<li><p><span data-ttu-id="eb39d-369">对于5000-10000 客户端，发布服务器需要最低的四核。</span><span class="sxs-lookup"><span data-stu-id="eb39d-369">For 5000-10000 clients, the publishing server requires a minimum quad core.</span></span></p></li>
<li><p><span data-ttu-id="eb39d-370">对于10000-20000 客户端，发布服务器应具有两个四核，以便更高效地响应时间。</span><span class="sxs-lookup"><span data-stu-id="eb39d-370">For 10000-20000 clients, the publishing server should have dual quad cores for more efficient response times.</span></span></p></li>
<li><p><span data-ttu-id="eb39d-371">带有四核的发布服务器最多可以在3秒内刷新10000程序包。</span><span class="sxs-lookup"><span data-stu-id="eb39d-371">A publishing server with a quad core can refresh up to 10000 packages within 3 seconds.</span></span> <span data-ttu-id="eb39d-372">（支持10000同时进行的客户端）</span><span class="sxs-lookup"><span data-stu-id="eb39d-372">(Supporting 10000 simultaneous clients)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="eb39d-373">每次刷新中的程序包数。</span><span class="sxs-lookup"><span data-stu-id="eb39d-373">Number of packages in each refresh.</span></span></p>
<p></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-374">增加的程序包数量将使响应时间增加 ~ 40% （最多1000个程序包）。</span><span class="sxs-lookup"><span data-stu-id="eb39d-374">Increasing number of packages will increase response time by ~40% (up to 1000 packages).</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="eb39d-375">App-v 5.1 客户端和发布服务器之间的网络。</span><span class="sxs-lookup"><span data-stu-id="eb39d-375">Network between the App-V 5.1 client and the publishing server.</span></span></p>
<p></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-376">通过慢速网络（1.5 Mbps 带宽），响应时间比局域网（最多可达1000用户）增加了97%。</span><span class="sxs-lookup"><span data-stu-id="eb39d-376">Across a slow network (1.5 Mbps bandwidth), there is a 97% increase in response time compared to LAN (up to 1000 users).</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="eb39d-377">**注意** 在需要处理同时请求的时间间隔（ &gt; 在大多数情况下为90%），发布服务器 CPU 使用率始终很高。</span><span class="sxs-lookup"><span data-stu-id="eb39d-377">**Note** The publishing server CPU usage is always high during the time interval when it has to process simultaneous requests (&gt;90% in most cases).</span></span> <span data-ttu-id="eb39d-378">发布服务器可以在1秒内处理 ~ 1500 客户端请求。</span><span class="sxs-lookup"><span data-stu-id="eb39d-378">The publishing server can handle ~1500 client requests in 1 second.</span></span>

 

<table>
<colgroup>
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="eb39d-379">情形</span><span class="sxs-lookup"><span data-stu-id="eb39d-379">Scenario</span></span></th>
<th align="left"><span data-ttu-id="eb39d-380">变体</span><span class="sxs-lookup"><span data-stu-id="eb39d-380">Variation</span></span></th>
<th align="left"><span data-ttu-id="eb39d-381">App-v 5.1 客户端数</span><span class="sxs-lookup"><span data-stu-id="eb39d-381">Number of App-V 5.1 clients</span></span></th>
<th align="left"><span data-ttu-id="eb39d-382">程序包数</span><span class="sxs-lookup"><span data-stu-id="eb39d-382">Number of packages</span></span></th>
<th align="left"><span data-ttu-id="eb39d-383">发布服务器上的处理器配置</span><span class="sxs-lookup"><span data-stu-id="eb39d-383">Processor configuration on the publishing server</span></span></th>
<th align="left"><span data-ttu-id="eb39d-384">网络连接类型发布服务器/App-v 5.1 客户端</span><span class="sxs-lookup"><span data-stu-id="eb39d-384">Network connection type publishing server / App-V 5.1 client</span></span></th>
<th align="left"><span data-ttu-id="eb39d-385">App-v 5.1 客户端上的往返行程时间（以秒为单位）</span><span class="sxs-lookup"><span data-stu-id="eb39d-385">Round trip time on the App-V 5.1 client (in seconds)</span></span></th>
<th align="left"><span data-ttu-id="eb39d-386">发布服务器上的 CPU 使用率（以% 为百分比）</span><span class="sxs-lookup"><span data-stu-id="eb39d-386">CPU utilization on publishing server (in %)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="eb39d-387">App-v 5.1 客户端发送发布刷新请求 &amp; 接收响应，每个包含120程序包的请求</span><span class="sxs-lookup"><span data-stu-id="eb39d-387">App-V 5.1 client sends publishing refresh request &amp; receives response, each request containing 120 packages</span></span></p></td>
<td align="left"><p><span data-ttu-id="eb39d-388">客户端数</span><span class="sxs-lookup"><span data-stu-id="eb39d-388">Number of clients</span></span></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-389">100</span><span class="sxs-lookup"><span data-stu-id="eb39d-389">100</span></span></p></li>
<li><p><span data-ttu-id="eb39d-390">1000</span><span class="sxs-lookup"><span data-stu-id="eb39d-390">1000</span></span></p></li>
<li><p><span data-ttu-id="eb39d-391">5000</span><span class="sxs-lookup"><span data-stu-id="eb39d-391">5000</span></span></p></li>
<li><p><span data-ttu-id="eb39d-392">10000</span><span class="sxs-lookup"><span data-stu-id="eb39d-392">10000</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-393">120</span><span class="sxs-lookup"><span data-stu-id="eb39d-393">120</span></span></p></li>
<li><p><span data-ttu-id="eb39d-394">120</span><span class="sxs-lookup"><span data-stu-id="eb39d-394">120</span></span></p></li>
<li><p><span data-ttu-id="eb39d-395">120</span><span class="sxs-lookup"><span data-stu-id="eb39d-395">120</span></span></p></li>
<li><p><span data-ttu-id="eb39d-396">120</span><span class="sxs-lookup"><span data-stu-id="eb39d-396">120</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-397">双核</span><span class="sxs-lookup"><span data-stu-id="eb39d-397">Dual Core</span></span></p></li>
<li><p><span data-ttu-id="eb39d-398">双核</span><span class="sxs-lookup"><span data-stu-id="eb39d-398">Dual Core</span></span></p></li>
<li><p><span data-ttu-id="eb39d-399">四核</span><span class="sxs-lookup"><span data-stu-id="eb39d-399">Quad Core</span></span></p></li>
<li><p><span data-ttu-id="eb39d-400">四核</span><span class="sxs-lookup"><span data-stu-id="eb39d-400">Quad Core</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-401">LAN</span><span class="sxs-lookup"><span data-stu-id="eb39d-401">LAN</span></span></p></li>
<li><p><span data-ttu-id="eb39d-402">LAN</span><span class="sxs-lookup"><span data-stu-id="eb39d-402">LAN</span></span></p></li>
<li><p><span data-ttu-id="eb39d-403">LAN</span><span class="sxs-lookup"><span data-stu-id="eb39d-403">LAN</span></span></p></li>
<li><p><span data-ttu-id="eb39d-404">LAN</span><span class="sxs-lookup"><span data-stu-id="eb39d-404">LAN</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-405">raid-1</span><span class="sxs-lookup"><span data-stu-id="eb39d-405">1</span></span></p></li>
<li><p><span data-ttu-id="eb39d-406">ppls-2</span><span class="sxs-lookup"><span data-stu-id="eb39d-406">2</span></span></p></li>
<li><p><span data-ttu-id="eb39d-407">ppls-2</span><span class="sxs-lookup"><span data-stu-id="eb39d-407">2</span></span></p></li>
<li><p><span data-ttu-id="eb39d-408">三维空间</span><span class="sxs-lookup"><span data-stu-id="eb39d-408">3</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-409">100</span><span class="sxs-lookup"><span data-stu-id="eb39d-409">100</span></span></p></li>
<li><p><span data-ttu-id="eb39d-410">99</span><span class="sxs-lookup"><span data-stu-id="eb39d-410">99</span></span></p></li>
<li><p><span data-ttu-id="eb39d-411">89</span><span class="sxs-lookup"><span data-stu-id="eb39d-411">89</span></span></p></li>
<li><p><span data-ttu-id="eb39d-412">77</span><span class="sxs-lookup"><span data-stu-id="eb39d-412">77</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="eb39d-413">每次刷新中的多个程序包</span><span class="sxs-lookup"><span data-stu-id="eb39d-413">Multiple packages in each refresh</span></span></p></td>
<td align="left"><p><span data-ttu-id="eb39d-414">程序包数</span><span class="sxs-lookup"><span data-stu-id="eb39d-414">Number of packages</span></span></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-415">1000</span><span class="sxs-lookup"><span data-stu-id="eb39d-415">1000</span></span></p></li>
<li><p><span data-ttu-id="eb39d-416">1000</span><span class="sxs-lookup"><span data-stu-id="eb39d-416">1000</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-417">500</span><span class="sxs-lookup"><span data-stu-id="eb39d-417">500</span></span></p></li>
<li><p><span data-ttu-id="eb39d-418">1000</span><span class="sxs-lookup"><span data-stu-id="eb39d-418">1000</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-419">四核</span><span class="sxs-lookup"><span data-stu-id="eb39d-419">Quad Core</span></span></p></li>
<li><p><span data-ttu-id="eb39d-420">四核</span><span class="sxs-lookup"><span data-stu-id="eb39d-420">Quad Core</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-421">LAN</span><span class="sxs-lookup"><span data-stu-id="eb39d-421">LAN</span></span></p></li>
<li><p><span data-ttu-id="eb39d-422">LAN</span><span class="sxs-lookup"><span data-stu-id="eb39d-422">LAN</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-423">ppls-2</span><span class="sxs-lookup"><span data-stu-id="eb39d-423">2</span></span></p></li>
<li><p><span data-ttu-id="eb39d-424">三维空间</span><span class="sxs-lookup"><span data-stu-id="eb39d-424">3</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-425">92</span><span class="sxs-lookup"><span data-stu-id="eb39d-425">92</span></span></p></li>
<li><p><span data-ttu-id="eb39d-426">91</span><span class="sxs-lookup"><span data-stu-id="eb39d-426">91</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="eb39d-427">客户端和发布服务器之间的网络</span><span class="sxs-lookup"><span data-stu-id="eb39d-427">Network between client and publishing server</span></span></p></td>
<td align="left"><p><span data-ttu-id="eb39d-428">1.5 Mbps 慢速链接网络</span><span class="sxs-lookup"><span data-stu-id="eb39d-428">1.5 Mbps Slow link network</span></span></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-429">100</span><span class="sxs-lookup"><span data-stu-id="eb39d-429">100</span></span></p></li>
<li><p><span data-ttu-id="eb39d-430">500</span><span class="sxs-lookup"><span data-stu-id="eb39d-430">500</span></span></p></li>
<li><p><span data-ttu-id="eb39d-431">1000</span><span class="sxs-lookup"><span data-stu-id="eb39d-431">1000</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-432">120</span><span class="sxs-lookup"><span data-stu-id="eb39d-432">120</span></span></p></li>
<li><p><span data-ttu-id="eb39d-433">120</span><span class="sxs-lookup"><span data-stu-id="eb39d-433">120</span></span></p></li>
<li><p><span data-ttu-id="eb39d-434">120</span><span class="sxs-lookup"><span data-stu-id="eb39d-434">120</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-435">四核</span><span class="sxs-lookup"><span data-stu-id="eb39d-435">Quad Core</span></span></p></li>
<li><p><span data-ttu-id="eb39d-436">四核</span><span class="sxs-lookup"><span data-stu-id="eb39d-436">Quad Core</span></span></p></li>
<li><p><span data-ttu-id="eb39d-437">四核</span><span class="sxs-lookup"><span data-stu-id="eb39d-437">Quad Core</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-438">1.5 Mbps 的大陆内网络</span><span class="sxs-lookup"><span data-stu-id="eb39d-438">1.5 Mbps Intra-Continental Network</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-439">三维空间</span><span class="sxs-lookup"><span data-stu-id="eb39d-439">3</span></span></p></li>
<li><p><span data-ttu-id="eb39d-440">10（0.2% 故障率）</span><span class="sxs-lookup"><span data-stu-id="eb39d-440">10 (with 0.2% failure rate)</span></span></p></li>
<li><p><span data-ttu-id="eb39d-441">17（有1% 的故障率）</span><span class="sxs-lookup"><span data-stu-id="eb39d-441">17 (with 1% failure rate)</span></span></p></li>
</ul></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="---------app-v-5-1-streaming-capacity-planning-recommendations"></a> <span data-ttu-id="eb39d-442">App-v 5.1 流容量规划建议</span><span class="sxs-lookup"><span data-stu-id="eb39d-442">App-V 5.1 Streaming Capacity Planning Recommendations</span></span>


<span data-ttu-id="eb39d-443">运行 App-v 5.1 客户端的计算机从流服务器流出虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="eb39d-443">Computers running the App-V 5.1 client stream the virtual application package from the streaming server.</span></span> <span data-ttu-id="eb39d-444">往返行程响应时间在运行 App-v 5.1 客户端的计算机上测量，并且是流式处理整个程序包所花的时间。</span><span class="sxs-lookup"><span data-stu-id="eb39d-444">Round trip response time is measured on the computer running the App-V 5.1 client, and is the time taken to stream the entire package.</span></span>

<span data-ttu-id="eb39d-445">**重要提示** 下表列出了设置 App-v 5.1 流服务器时要考虑的主要因素：</span><span class="sxs-lookup"><span data-stu-id="eb39d-445">**Important** The following list identifies the main factors to consider when setting up the App-V 5.1 streaming server:</span></span>

-   <span data-ttu-id="eb39d-446">从单个流式处理服务器同时处理流应用程序包的客户端数。</span><span class="sxs-lookup"><span data-stu-id="eb39d-446">The number of clients streaming application packages simultaneously from a single streaming server.</span></span>

-   <span data-ttu-id="eb39d-447">正在进行流处理的包的大小。</span><span class="sxs-lookup"><span data-stu-id="eb39d-447">The size of the package being streamed.</span></span>

-   <span data-ttu-id="eb39d-448">客户端和流服务器之间的环境中的可用网络带宽。</span><span class="sxs-lookup"><span data-stu-id="eb39d-448">The available network bandwidth in your environment between the client and the streaming server.</span></span>

 

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="eb39d-449">情形</span><span class="sxs-lookup"><span data-stu-id="eb39d-449">Scenario</span></span></th>
<th align="left"><span data-ttu-id="eb39d-450">摘要</span><span class="sxs-lookup"><span data-stu-id="eb39d-450">Summary</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="eb39d-451">多个 App-v 5.1 客户端从单个流服务器同时流处理应用程序。</span><span class="sxs-lookup"><span data-stu-id="eb39d-451">Multiple App-V 5.1 clients stream applications from a single streaming server simultaneously.</span></span></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-452">如果同时从同一服务器同时流式处理的客户端数量增加，则会有与程序包下载/流时间有关的线性关系。</span><span class="sxs-lookup"><span data-stu-id="eb39d-452">If the number of clients simultaneously streaming from the same server increases, there is a linear relationship with the package download/streaming time.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="eb39d-453">正在进行流处理的包的大小。</span><span class="sxs-lookup"><span data-stu-id="eb39d-453">Size of the package being streamed.</span></span></p>
<p></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-454">程序包大小对大小约为1GB 的较大程序包的流处理/下载时间有重大影响。</span><span class="sxs-lookup"><span data-stu-id="eb39d-454">The package size has a significant impact on the streaming/download time only for larger packages with a size ~ 1GB.</span></span> <span data-ttu-id="eb39d-455">对于从 3 MB 到 100 MB 的程序包大小，流时间的范围从20秒到100秒，同时提供100个客户端。</span><span class="sxs-lookup"><span data-stu-id="eb39d-455">For package sizes ranging from 3 MB to 100 MB, the streaming time ranges from 20 seconds to 100 seconds, with 100 simultaneous clients.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="eb39d-456">App-v 5.1 客户端和流式服务器之间的网络。</span><span class="sxs-lookup"><span data-stu-id="eb39d-456">Network between the App-V 5.1 client and the streaming server.</span></span></p>
<p></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-457">通过慢速网络（1.5 Mbps 带宽），响应时间比局域网（最多可达100用户）增加了70-80%。</span><span class="sxs-lookup"><span data-stu-id="eb39d-457">Across a slow network (1.5 Mbps bandwidth), there is a 70-80% increase in response time compared to LAN (up to 100 users).</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="eb39d-458">下表显示了上一列表中每个因素的示例值：</span><span class="sxs-lookup"><span data-stu-id="eb39d-458">The following table displays sample values for each of the factors in the previous list:</span></span>

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="eb39d-459">情形</span><span class="sxs-lookup"><span data-stu-id="eb39d-459">Scenario</span></span></th>
<th align="left"><span data-ttu-id="eb39d-460">变体</span><span class="sxs-lookup"><span data-stu-id="eb39d-460">Variation</span></span></th>
<th align="left"><span data-ttu-id="eb39d-461">App-v 5.1 客户端数</span><span class="sxs-lookup"><span data-stu-id="eb39d-461">Number of App-V 5.1 clients</span></span></th>
<th align="left"><span data-ttu-id="eb39d-462">每个程序包的大小</span><span class="sxs-lookup"><span data-stu-id="eb39d-462">Size of each package</span></span></th>
<th align="left"><span data-ttu-id="eb39d-463">网络连接类型流式处理服务器/App-v 5.1 客户端</span><span class="sxs-lookup"><span data-stu-id="eb39d-463">Network connection type streaming server / App-V 5.1 client</span></span></th>
<th align="left"><span data-ttu-id="eb39d-464">App-v 5.1 客户端上的往返行程时间（以秒为单位）</span><span class="sxs-lookup"><span data-stu-id="eb39d-464">Round trip time on the App-V 5.1 client (in seconds)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="eb39d-465">多个 App-v 5.1 客户端从流式处理服务器流式处理虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="eb39d-465">Multiple App-V 5.1 clients streaming virtual application packages from a streaming server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="eb39d-466">客户端数。</span><span class="sxs-lookup"><span data-stu-id="eb39d-466">Number of clients.</span></span></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-467">100</span><span class="sxs-lookup"><span data-stu-id="eb39d-467">100</span></span></p></li>
<li><p><span data-ttu-id="eb39d-468">200</span><span class="sxs-lookup"><span data-stu-id="eb39d-468">200</span></span></p></li>
<li><p><span data-ttu-id="eb39d-469">1000</span><span class="sxs-lookup"><span data-stu-id="eb39d-469">1000</span></span></p></li>
<li><p></p></li>
<li><p><span data-ttu-id="eb39d-470">100</span><span class="sxs-lookup"><span data-stu-id="eb39d-470">100</span></span></p></li>
<li><p><span data-ttu-id="eb39d-471">200</span><span class="sxs-lookup"><span data-stu-id="eb39d-471">200</span></span></p></li>
<li><p><span data-ttu-id="eb39d-472">1000</span><span class="sxs-lookup"><span data-stu-id="eb39d-472">1000</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-473">3.5 MB</span><span class="sxs-lookup"><span data-stu-id="eb39d-473">3.5 MB</span></span></p></li>
<li><p><span data-ttu-id="eb39d-474">3.5 MB</span><span class="sxs-lookup"><span data-stu-id="eb39d-474">3.5 MB</span></span></p></li>
<li><p><span data-ttu-id="eb39d-475">3.5 MB</span><span class="sxs-lookup"><span data-stu-id="eb39d-475">3.5 MB</span></span></p></li>
<li><p></p></li>
<li><p><span data-ttu-id="eb39d-476">5 MB</span><span class="sxs-lookup"><span data-stu-id="eb39d-476">5 MB</span></span></p></li>
<li><p><span data-ttu-id="eb39d-477">5 MB</span><span class="sxs-lookup"><span data-stu-id="eb39d-477">5 MB</span></span></p></li>
<li><p><span data-ttu-id="eb39d-478">5 MB</span><span class="sxs-lookup"><span data-stu-id="eb39d-478">5 MB</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-479">LAN</span><span class="sxs-lookup"><span data-stu-id="eb39d-479">LAN</span></span></p></li>
<li><p><span data-ttu-id="eb39d-480">LAN</span><span class="sxs-lookup"><span data-stu-id="eb39d-480">LAN</span></span></p></li>
<li><p><span data-ttu-id="eb39d-481">LAN</span><span class="sxs-lookup"><span data-stu-id="eb39d-481">LAN</span></span></p></li>
<li><p></p></li>
<li><p><span data-ttu-id="eb39d-482">LAN</span><span class="sxs-lookup"><span data-stu-id="eb39d-482">LAN</span></span></p></li>
<li><p><span data-ttu-id="eb39d-483">LAN</span><span class="sxs-lookup"><span data-stu-id="eb39d-483">LAN</span></span></p></li>
<li><p><span data-ttu-id="eb39d-484">LAN</span><span class="sxs-lookup"><span data-stu-id="eb39d-484">LAN</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-485">29</span><span class="sxs-lookup"><span data-stu-id="eb39d-485">29</span></span></p></li>
<li><p><span data-ttu-id="eb39d-486">39</span><span class="sxs-lookup"><span data-stu-id="eb39d-486">39</span></span></p></li>
<li><p><span data-ttu-id="eb39d-487">391</span><span class="sxs-lookup"><span data-stu-id="eb39d-487">391</span></span></p></li>
<li><p></p></li>
<li><p><span data-ttu-id="eb39d-488">35</span><span class="sxs-lookup"><span data-stu-id="eb39d-488">35</span></span></p></li>
<li><p><span data-ttu-id="eb39d-489">68</span><span class="sxs-lookup"><span data-stu-id="eb39d-489">68</span></span></p></li>
<li><p><span data-ttu-id="eb39d-490">461</span><span class="sxs-lookup"><span data-stu-id="eb39d-490">461</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="eb39d-491">正在进行数据流处理的每个程序包的大小。</span><span class="sxs-lookup"><span data-stu-id="eb39d-491">Size of each package being streamed.</span></span></p></td>
<td align="left"><p><span data-ttu-id="eb39d-492">每个程序包的大小。</span><span class="sxs-lookup"><span data-stu-id="eb39d-492">Size of each package.</span></span></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-493">100</span><span class="sxs-lookup"><span data-stu-id="eb39d-493">100</span></span></p></li>
<li><p><span data-ttu-id="eb39d-494">200</span><span class="sxs-lookup"><span data-stu-id="eb39d-494">200</span></span></p></li>
<li><p></p></li>
<li><p><span data-ttu-id="eb39d-495">100</span><span class="sxs-lookup"><span data-stu-id="eb39d-495">100</span></span></p></li>
<li><p><span data-ttu-id="eb39d-496">200</span><span class="sxs-lookup"><span data-stu-id="eb39d-496">200</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-497">21 MB</span><span class="sxs-lookup"><span data-stu-id="eb39d-497">21 MB</span></span></p></li>
<li><p><span data-ttu-id="eb39d-498">21 MB</span><span class="sxs-lookup"><span data-stu-id="eb39d-498">21 MB</span></span></p></li>
<li><p></p></li>
<li><p><span data-ttu-id="eb39d-499">109</span><span class="sxs-lookup"><span data-stu-id="eb39d-499">109</span></span></p></li>
<li><p><span data-ttu-id="eb39d-500">109</span><span class="sxs-lookup"><span data-stu-id="eb39d-500">109</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-501">LAN</span><span class="sxs-lookup"><span data-stu-id="eb39d-501">LAN</span></span></p></li>
<li><p><span data-ttu-id="eb39d-502">LAN</span><span class="sxs-lookup"><span data-stu-id="eb39d-502">LAN</span></span></p></li>
<li><p></p></li>
<li><p><span data-ttu-id="eb39d-503">LAN</span><span class="sxs-lookup"><span data-stu-id="eb39d-503">LAN</span></span></p></li>
<li><p><span data-ttu-id="eb39d-504">LAN</span><span class="sxs-lookup"><span data-stu-id="eb39d-504">LAN</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<p><span data-ttu-id="eb39d-505">33</span><span class="sxs-lookup"><span data-stu-id="eb39d-505">33</span></span></p>
<p><span data-ttu-id="eb39d-506">83</span><span class="sxs-lookup"><span data-stu-id="eb39d-506">83</span></span></p>
<p></p>
<p><span data-ttu-id="eb39d-507">100</span><span class="sxs-lookup"><span data-stu-id="eb39d-507">100</span></span></p>
<p><span data-ttu-id="eb39d-508">160</span><span class="sxs-lookup"><span data-stu-id="eb39d-508">160</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="eb39d-509">客户端和 App-v 5.1 流服务器之间的网络连接。</span><span class="sxs-lookup"><span data-stu-id="eb39d-509">Network connection between client and App-V 5.1 streaming server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="eb39d-510">1.5 Mbps 慢速链接网络。</span><span class="sxs-lookup"><span data-stu-id="eb39d-510">1.5 Mbps Slow link network.</span></span></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-511">100</span><span class="sxs-lookup"><span data-stu-id="eb39d-511">100</span></span></p></li>
<li><p></p></li>
<li><p><span data-ttu-id="eb39d-512">100</span><span class="sxs-lookup"><span data-stu-id="eb39d-512">100</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-513">3.5 MB</span><span class="sxs-lookup"><span data-stu-id="eb39d-513">3.5 MB</span></span></p></li>
<li><p></p></li>
<li><p><span data-ttu-id="eb39d-514">5 MB</span><span class="sxs-lookup"><span data-stu-id="eb39d-514">5 MB</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="eb39d-515">1.5 Mbps 的大陆内网络</span><span class="sxs-lookup"><span data-stu-id="eb39d-515">1.5 Mbps Intra-Continental Network</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<p><span data-ttu-id="eb39d-516">102</span><span class="sxs-lookup"><span data-stu-id="eb39d-516">102</span></span></p>
<p></p>
<p><span data-ttu-id="eb39d-517">121</span><span class="sxs-lookup"><span data-stu-id="eb39d-517">121</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="eb39d-518">每个 App-v 5.1 流服务器都应该能够处理同时流式处理的虚拟化应用程序中最少的200个客户端。</span><span class="sxs-lookup"><span data-stu-id="eb39d-518">Each App-V 5.1 streaming server should be able to handle a minimum of 200 clients concurrently streaming virtualized applications.</span></span>

<span data-ttu-id="eb39d-519">**注意** 流的实际时间将主要由同时流的客户端数、程序包数、程序包大小、服务器的网络活动和网络条件决定。</span><span class="sxs-lookup"><span data-stu-id="eb39d-519">**Note** The actual time to it will take to stream is determined primarily by the number of clients streaming simultaneously, number of packages, package size, the server’s network activity, and network conditions.</span></span>

 

<span data-ttu-id="eb39d-520">例如，当100同时进行来自服务器的流处理时，一般用户可以在2分钟内流出 100 MB 程序包。</span><span class="sxs-lookup"><span data-stu-id="eb39d-520">For example, an average user can stream a 100 MB package in less than 2 minutes, when 100 simultaneous clients are streaming from the server.</span></span> <span data-ttu-id="eb39d-521">但是，一个大小为 1 GB 的程序包可能最多需要30分钟。</span><span class="sxs-lookup"><span data-stu-id="eb39d-521">However, a package of size 1 GB could take up to 30 minutes.</span></span> <span data-ttu-id="eb39d-522">在大多数真实环境中，流请求不是均匀分布的，你需要了解你的环境中存在的近似的峰值流要求，以便正确地调整所需流式处理服务器的数量。</span><span class="sxs-lookup"><span data-stu-id="eb39d-522">In most real world environments streaming demand is not uniformly distributed, you will need to understand the approximate peak streaming requirements present in your environment in order to properly size the number of required streaming servers.</span></span>

<span data-ttu-id="eb39d-523">如果你预缓存了你的应用程序，可显著增加流服务器支持的客户端数和峰值流需求。</span><span class="sxs-lookup"><span data-stu-id="eb39d-523">The number of clients a streaming server can support can be significantly increased and the peak streaming requirements reduced if you pre-cache your applications.</span></span> <span data-ttu-id="eb39d-524">您还可以通过使用点播流式传递和流优化程序包来增加流服务器可以支持的客户端数量。</span><span class="sxs-lookup"><span data-stu-id="eb39d-524">You can also increase the number of clients a streaming server can support by using on-demand streaming delivery and stream optimized packages.</span></span>

## <span data-ttu-id="eb39d-525">结合 app-v 5.1 服务器角色</span><span class="sxs-lookup"><span data-stu-id="eb39d-525">Combining App-V 5.1 Server Roles</span></span>


<span data-ttu-id="eb39d-526">折扣比例和容错要求，连接到 Active Directory 的位置所需的最少服务器数是一个。</span><span class="sxs-lookup"><span data-stu-id="eb39d-526">Discounting scaling and fault-tolerance requirements, the minimum number of servers needed for a location with connectivity to Active Directory is one.</span></span> <span data-ttu-id="eb39d-527">此服务器将托管管理服务器、管理服务器服务和 Microsoft SQL Server 角色。</span><span class="sxs-lookup"><span data-stu-id="eb39d-527">This server will host the management server, management server service, and Microsoft SQL Server roles.</span></span> <span data-ttu-id="eb39d-528">因此，服务器角色可以按所需的任何组合进行排列，因为它们不会相互冲突。</span><span class="sxs-lookup"><span data-stu-id="eb39d-528">Server roles, therefore, can be arranged in any desired combination since they do not conflict with one another.</span></span>

<span data-ttu-id="eb39d-529">忽略缩放要求，提供容错实现所需的最少服务器数是4。</span><span class="sxs-lookup"><span data-stu-id="eb39d-529">Ignoring scaling requirements, the minimum number of servers necessary to provide a fault-tolerant implementation is four.</span></span> <span data-ttu-id="eb39d-530">管理服务器和 Microsoft SQL Server 角色支持被置于容错配置中。</span><span class="sxs-lookup"><span data-stu-id="eb39d-530">The management server, and Microsoft SQL Server roles support being placed in fault-tolerant configurations.</span></span> <span data-ttu-id="eb39d-531">管理服务器服务可以与任何角色结合使用，但仍会出现单点故障。</span><span class="sxs-lookup"><span data-stu-id="eb39d-531">The management server service can be combined with any of the roles, but remains a single point of failure.</span></span>

<span data-ttu-id="eb39d-532">虽然有许多可用的容错策略和技术，但并非所有这些都适用于给定的服务。</span><span class="sxs-lookup"><span data-stu-id="eb39d-532">Although there are a number of fault-tolerance strategies and technologies available, not all are applicable to a given service.</span></span> <span data-ttu-id="eb39d-533">此外，如果结合使用 app-v 5.1 角色，则某些容错选项可能不再适用，因为不兼容。</span><span class="sxs-lookup"><span data-stu-id="eb39d-533">Additionally, if App-V 5.1 roles are combined, certain fault-tolerance options may no longer apply due to incompatibilities.</span></span>






## <span data-ttu-id="eb39d-534">相关主题</span><span class="sxs-lookup"><span data-stu-id="eb39d-534">Related topics</span></span>


[<span data-ttu-id="eb39d-535">App-V 5.1 支持的配置</span><span class="sxs-lookup"><span data-stu-id="eb39d-535">App-V 5.1 Supported Configurations</span></span>](app-v-51-supported-configurations.md)

[<span data-ttu-id="eb39d-536">计划 App-V 5.1 的高可用性</span><span class="sxs-lookup"><span data-stu-id="eb39d-536">Planning for High Availability with App-V 5.1</span></span>](planning-for-high-availability-with-app-v-51.md)

[<span data-ttu-id="eb39d-537">计划部署 App-V</span><span class="sxs-lookup"><span data-stu-id="eb39d-537">Planning to Deploy App-V</span></span>](planning-to-deploy-app-v51.md)

 

 





