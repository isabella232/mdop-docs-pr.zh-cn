---
title: 如何针对 MBAM 配置网络负载均衡
description: 如何针对 MBAM 配置网络负载均衡
author: dansimp
ms.assetid: df2208c3-352b-4a48-9722-237b0c8cd6a5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a04bc74a9dab7bfe18eed8e5a3c1b6ca64d88b5b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803783"
---
# <span data-ttu-id="db959-103">如何针对 MBAM 配置网络负载均衡</span><span class="sxs-lookup"><span data-stu-id="db959-103">How to Configure Network Load Balancing for MBAM</span></span>


<span data-ttu-id="db959-104">若要验证是否满足安装 "管理和监视服务器" 功能的先决条件和硬件和软件要求，请参阅[MBAM 1.0 部署先决条件](mbam-10-deployment-prerequisites.md)和[MBAM 1.0 支持的配置](mbam-10-supported-configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="db959-104">To verify that you have met the prerequisites and hardware and software requirements to install the Administration and Monitoring Server feature, see [MBAM 1.0 Deployment Prerequisites](mbam-10-deployment-prerequisites.md) and [MBAM 1.0 Supported Configurations](mbam-10-supported-configurations.md).</span></span>

<span data-ttu-id="db959-105">**注意** 若要获取安装程序日志文件，必须通过使用**msiexec**程序包和 **/l** Location 选项安装 Microsoft BitLocker 管理和监视（MBAM） &lt; &gt; 。</span><span class="sxs-lookup"><span data-stu-id="db959-105">**Note** To obtain the setup log files, you must install Microsoft BitLocker Administration and Monitoring (MBAM) by using the **msiexec** package and the **/l** &lt;location&gt; option.</span></span> <span data-ttu-id="db959-106">将在您指定的位置创建日志文件。</span><span class="sxs-lookup"><span data-stu-id="db959-106">The Log files are created in the location that you specify.</span></span>

<span data-ttu-id="db959-107">其他安装日志文件将在安装 MBAM 的用户的% temp% 文件夹中创建。</span><span class="sxs-lookup"><span data-stu-id="db959-107">Additional setup log files are created in the %temp% folder of the user who installs MBAM.</span></span>

 

<span data-ttu-id="db959-108">用于管理和监视服务器功能的网络负载平衡（NLB）群集在 MBAM 中提供了可伸缩性，并且它应支持超过 55000 MBAM 客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="db959-108">The Network Load Balancing (NLB) clusters for the Administration and Monitoring Server feature provides scalability in MBAM and it should support more than 55,000 MBAM client computers.</span></span>

<span data-ttu-id="db959-109">**注意** Windows Server 网络负载平衡将客户端请求分配到一组配置为单个服务器群集的服务器上。</span><span class="sxs-lookup"><span data-stu-id="db959-109">**Note** Windows Server Network Load Balancing distributes client requests across a set of servers that are configured into a single server cluster.</span></span> <span data-ttu-id="db959-110">当网络负载平衡安装在群集中的每个服务器（主机）上时，群集会向客户端请求显示虚拟 IP 地址或完全限定的域名（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="db959-110">When Network Load Balancing is installed on each of the servers (hosts) in a cluster, the cluster presents a virtual IP address or fully qualified domain name (FQDN) to client requests.</span></span> <span data-ttu-id="db959-111">初始客户端请求转到群集中的所有主机，但只有一个主机接受和处理该请求。</span><span class="sxs-lookup"><span data-stu-id="db959-111">The initial client requests go to all the hosts in the cluster, but only one host accepts and handles the request.</span></span>

<span data-ttu-id="db959-112">所有将属于 NLB 群集的计算机都具有以下要求：</span><span class="sxs-lookup"><span data-stu-id="db959-112">All computers that will be part of a NLB cluster have the following requirements:</span></span>

-   <span data-ttu-id="db959-113">NLB 群集中的所有计算机必须位于同一个域中。</span><span class="sxs-lookup"><span data-stu-id="db959-113">All computers in the NLB cluster must be in the same domain.</span></span>

-   <span data-ttu-id="db959-114">NLB 群集中的每台计算机都必须使用静态 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="db959-114">Each computer in the NLB cluster must use a static IP address.</span></span>

-   <span data-ttu-id="db959-115">NLB 群集中的每台计算机都必须启用网络负载平衡。</span><span class="sxs-lookup"><span data-stu-id="db959-115">Each computer in the NLB cluster must have Network Load Balancing enabled.</span></span>

-   <span data-ttu-id="db959-116">NLB 群集需要静态 IP 地址，并且必须在域名系统（DNS）中手动创建主机记录。</span><span class="sxs-lookup"><span data-stu-id="db959-116">The NLB cluster requires a static IP address, and a host record must be manually created in the domain name system (DNS).</span></span>

 

## <span data-ttu-id="db959-117">为 MBAM 管理和监视服务器配置网络负载平衡</span><span class="sxs-lookup"><span data-stu-id="db959-117">Configuring Network Load Balancing for MBAM Administration and Monitoring Servers</span></span>


<span data-ttu-id="db959-118">以下步骤介绍了如何为两个 MBAM 管理和监视服务器配置 NLB 群集虚拟名称和 IP 地址，以及如何将 MBAM 客户端配置为使用 NLB 群集。</span><span class="sxs-lookup"><span data-stu-id="db959-118">The following steps describe how to configure an NLB cluster virtual name and IP address for two MBAM Administration and Monitoring servers, and how to configure MBAM Clients to use the NLB Cluster.</span></span>

<span data-ttu-id="db959-119">在开始本主题中所述的过程之前，必须通过在两台单独的服务器计算机上使用相同的 IIS 端口绑定来成功安装 MBAM 管理和监视服务器功能，同时满足 MBAM Server 功能安装和 NLB 群集配置的先决条件。</span><span class="sxs-lookup"><span data-stu-id="db959-119">Before you begin the procedures described in this topic, you must have the MBAM Administration and Monitoring Server feature successfully installed by using the same IIS port binding on two separate server computers that meet the prerequisites for both MBAM Server feature installation and NLB Cluster configuration.</span></span>

<span data-ttu-id="db959-120">**注意** 本主题介绍使用网络负载平衡管理器创建 NLB 群集的基本过程。</span><span class="sxs-lookup"><span data-stu-id="db959-120">**Note** This topic describes the basic process of using Network Load Balancing Manager to create an NLB Cluster.</span></span> <span data-ttu-id="db959-121">将 Windows Server 配置为 NLB 群集的确切步骤取决于所使用的 Windows 服务器版本。。</span><span class="sxs-lookup"><span data-stu-id="db959-121">The exact steps to configure a Windows Server as part of an NLB cluster depend on the Windows Server version in use..</span></span> <span data-ttu-id="db959-122">有关如何在 WindowsServer2008 上创建 NLBs 的详细信息，请参阅在 Windows Server2008 TechNet 库中[创建网络负载平衡群集](https://go.microsoft.com/fwlink/?LinkId=197176)。</span><span class="sxs-lookup"><span data-stu-id="db959-122">For more information about how to create NLBs on WindowsServer2008, see [Creating Network Load Balancing Clusters](https://go.microsoft.com/fwlink/?LinkId=197176) in the Windows Server2008 TechNet library.</span></span>

 

**<span data-ttu-id="db959-123">为两个 MBAM 管理和监视服务器配置 NLB 群集虚拟名称和 IP 地址</span><span class="sxs-lookup"><span data-stu-id="db959-123">To configure an NLB Cluster Virtual Name and IP address for two MBAM Administration and Monitoring Servers</span></span>**

1.  <span data-ttu-id="db959-124">单击 "**开始**"，单击 "**所有程序**"，单击 "**管理工具**"，然后单击 "**网络负载平衡管理器**"。</span><span class="sxs-lookup"><span data-stu-id="db959-124">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Network Load Balancing Manager**.</span></span>

    <span data-ttu-id="db959-125">**注意** 如果 NLB 管理器不存在，则可以将其作为 WindowsServer 功能进行安装。</span><span class="sxs-lookup"><span data-stu-id="db959-125">**Note** If the NLB Manager is not present, you can install it as a WindowsServer feature.</span></span> <span data-ttu-id="db959-126">如果要将此功能配置到 NLB 群集，则必须在 MBAM 管理服务器和监视服务器上安装此功能。</span><span class="sxs-lookup"><span data-stu-id="db959-126">You must install this feature on both MBAM Administration and Monitoring servers if you want to configure it into the NLB cluster.</span></span>

     

2.  <span data-ttu-id="db959-127">在菜单栏上，单击 "**群集**"，然后单击 "**新建**" 以打开 "**群集参数**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="db959-127">On the menu bar, click **Cluster**, and then click **New** to open the **Cluster Parameters** dialog box.</span></span>

3.  <span data-ttu-id="db959-128">在 "**群集参数**" 对话框中，输入 NLB 群集 IP 配置的信息：</span><span class="sxs-lookup"><span data-stu-id="db959-128">In the **Cluster Parameters** dialog box, enter the information for the NLB cluster IP configuration:</span></span>

    -   <span data-ttu-id="db959-129">**IP 地址：** 在 DNS 中注册的 NLB 群集 IP 地址</span><span class="sxs-lookup"><span data-stu-id="db959-129">**IP address:** NLB cluster IP address registered in DNS</span></span>

    -   <span data-ttu-id="db959-130">**子网掩码：** 在 DNS 中注册的 NLB 群集 IP 地址子网掩码</span><span class="sxs-lookup"><span data-stu-id="db959-130">**Subnet mask:** NLB cluster IP address subnet mask registered in DNS</span></span>

    -   <span data-ttu-id="db959-131">**Internet 完整名称：** 在 DNS 中注册的 NLB 群集名称的 FQDN</span><span class="sxs-lookup"><span data-stu-id="db959-131">**Full Internet name:** FQDN of NLB cluster name registered in DNS</span></span>

4.  <span data-ttu-id="db959-132">确保在 "**群集操作" 模式**下选中了 "**单播**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="db959-132">Ensure that **Unicast** is selected in **Cluster operation mode**, and then click **Next**.</span></span>

5.  <span data-ttu-id="db959-133">在 "**群集 IP 地址**" 页面上，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="db959-133">On the **Cluster IP Addresses** page, click **Next**.</span></span>

6.  <span data-ttu-id="db959-134">在 "**端口规则**" 页面上，单击 "**编辑**" 以定义 nlb 群集将响应的端口，并配置用于客户端到站点系统通信的端口（在为网站定义）时，或单击 "**下一步**" 以启用 nlb 群集 IP 地址以响应所有 tcp/ip 端口。</span><span class="sxs-lookup"><span data-stu-id="db959-134">On the **Port Rules** page, click **Edit** to define the ports that the NLB cluster will respond to and configure the ports that are used for client-to-site system communication as they are defined for the site, or click **Next** to enable the NLB cluster IP address to respond to all TCP/IP ports.</span></span>

    <span data-ttu-id="db959-135">**注意** 确保将 "**相关性**" 设置为 "**单一**"。</span><span class="sxs-lookup"><span data-stu-id="db959-135">**Note** Ensure that **Affinity** is set to **Single**.</span></span>

     

7.  <span data-ttu-id="db959-136">在 "**连接**" 页面上，输入 MBAM 管理和监视服务器实例主机名称，该名称将成为**主机**中 NLB 群集的一部分，然后单击 "**连接**"。</span><span class="sxs-lookup"><span data-stu-id="db959-136">On the **Connect** page, enter an MBAM Administration and Monitoring server instance host name that will be part of the NLB cluster in **Host**, and then click **Connect**.</span></span>

8.  <span data-ttu-id="db959-137">在**可用于配置新群集的接口**中，选择将配置为响应 NLB 群集通信的网络接口，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="db959-137">In **Interfaces available for configuring a new cluster**, select the networking interface that will be configured to respond to NLB cluster communication, and then click **Next**.</span></span>

9.  <span data-ttu-id="db959-138">在 "**主机参数**" 页面上，查看所显示的信息以确保**专用 IP 配置**设置显示正确的 NLB 群集主机的专用主机 IP 配置，检查是否**已启动**初始主机状态**默认状态：** "已启动"，然后单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="db959-138">On the **Host Parameters** page, review the information displayed to ensure that the **Dedicated IP configuration** settings display the dedicated host IP configuration for the correct NLB cluster host, check that the Initial host state **Default state:** is **Started**, and then click **Finish**.</span></span>

    <span data-ttu-id="db959-139">**注意** "**主机参数**" 页面还显示 NLB 群集主机优先级，即1到32。</span><span class="sxs-lookup"><span data-stu-id="db959-139">**Note** The **Host Parameters** page also displays the NLB cluster host priority, which is 1 through 32.</span></span> <span data-ttu-id="db959-140">在将新主机添加到 NLB 群集时，主机优先级必须与以前添加的主机不同。</span><span class="sxs-lookup"><span data-stu-id="db959-140">As new hosts are added to the NLB cluster, the host priority must differ from the previously added hosts.</span></span> <span data-ttu-id="db959-141">使用网络负载平衡管理器时，将自动增加优先级。</span><span class="sxs-lookup"><span data-stu-id="db959-141">The priority is automatically incremented when you use the Network Load Balancing Manager.</span></span>

     

10. <span data-ttu-id="db959-142">单击 " \*\* &lt; nlb 群集 &gt; 名称**"，确保 NLB 主机接口**状态**在继续操作之前显示**聚合\*\*。</span><span class="sxs-lookup"><span data-stu-id="db959-142">Click **&lt;NLB cluster name&gt;** and ensure that the NLB host interface **Status** displays **Converged** before you continue.</span></span> <span data-ttu-id="db959-143">此步骤可能要求你将 NLB 群集显示刷新为 NLB 管理器正在修改的主机 TCP/IP 配置。</span><span class="sxs-lookup"><span data-stu-id="db959-143">This step might require that you refresh the NLB cluster display as the host TCP/IP configuration that is being modified by the NLB Manager.</span></span>

11. <span data-ttu-id="db959-144">若要向 NLB 群集添加其他主机，请右键单击 " \*\* &lt; nlb 群集 &gt; 名称\*\*"，单击 **"添加主机到群集"，** 然后为将成为 NLB 群集一部分的每个站点系统重复步骤7到10。</span><span class="sxs-lookup"><span data-stu-id="db959-144">To add additional hosts to the NLB cluster, right-click **&lt;NLB cluster name&gt;**, click **Add Host to Cluster,** and then repeat steps 7 through 10 for each site system that will be part of the NLB cluster.</span></span>

12. <span data-ttu-id="db959-145">在安装了 MBAM 组策略模板的计算机上，修改 MBAM 组策略设置以将 MBAM 服务终结点配置为使用 NLB 群集名称和相应的 IIS 端口绑定来访问安装在 NLB 群集计算机上的 MBAM 管理和监视服务器功能。</span><span class="sxs-lookup"><span data-stu-id="db959-145">On a computer that has MBAM Group Policy template installed, modify the MBAM Group Policy settings to configure the MBAM services endpoints to use the NLB Cluster name and the appropriate IIS port binding to access the MBAM Administration and Monitoring Server features that are installed on the NLB Cluster computers.</span></span> <span data-ttu-id="db959-146">有关如何编辑 MBAM GPO 设置的详细信息，请参阅[如何编辑 MBAM 1.0 Gpo 设置](how-to-edit-mbam-10-gpo-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="db959-146">For more information about how to edit MBAM GPO settings, see [How to Edit MBAM 1.0 GPO Settings](how-to-edit-mbam-10-gpo-settings.md).</span></span> <span data-ttu-id="db959-147">如果 MBAM 管理服务器和监视服务器对于你的环境而言是新的，请确保已正确配置所需的本地安全组成员身份。</span><span class="sxs-lookup"><span data-stu-id="db959-147">If the MBAM Administration and Monitoring servers are new to your environment, ensure that the required local security group memberships have been properly configured.</span></span> <span data-ttu-id="db959-148">有关安全组要求的详细信息，请参阅[规划 MBAM 1.0 管理员角色](planning-for-mbam-10-administrator-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="db959-148">For more information about security group requirements, see [Planning for MBAM 1.0 Administrator Roles](planning-for-mbam-10-administrator-roles.md).</span></span>

13. <span data-ttu-id="db959-149">NLB 群集配置完成后，我们建议你验证 MBAM 管理和监视 NLB 群集是否正常工作。</span><span class="sxs-lookup"><span data-stu-id="db959-149">When the NLB Cluster configuration is complete, we recommend that you validate that the MBAM Administration and Monitoring NLB Cluster is functional.</span></span> <span data-ttu-id="db959-150">若要执行此操作，请在不是在 NLB 中配置的服务器之外的计算机上打开 web 浏览器，并确保可以使用 NLB FQDN 访问 MBAM 管理和监视网站。</span><span class="sxs-lookup"><span data-stu-id="db959-150">To do this, open a web browser on a computer other than the servers that are configured in the NLB, and ensure that you can access the MBAM Administration and Monitoring web site by using the NLB FQDN.</span></span>

## <span data-ttu-id="db959-151">相关主题</span><span class="sxs-lookup"><span data-stu-id="db959-151">Related topics</span></span>


[<span data-ttu-id="db959-152">部署 MBAM 1.0 服务器基础结构</span><span class="sxs-lookup"><span data-stu-id="db959-152">Deploying the MBAM 1.0 Server Infrastructure</span></span>](deploying-the-mbam-10-server-infrastructure.md)

 

 





