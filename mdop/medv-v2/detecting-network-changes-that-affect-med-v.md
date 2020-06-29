---
title: 检测影响 MED-V 的网络更改
description: 检测影响 MED-V 的网络更改
author: dansimp
ms.assetid: fd29b95a-cda2-464d-b86d-50b6bd64b4ca
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b5f43c30dee9ef8e06a7ae226849a4f21e83257c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803355"
---
# <span data-ttu-id="417e6-103">检测影响 MED-V 的网络更改</span><span class="sxs-lookup"><span data-stu-id="417e6-103">Detecting Network Changes that Affect MED-V</span></span>


<span data-ttu-id="417e6-104">通过 Microsoft 企业桌面虚拟化（MED-V）2.0 解决方案，你可以配置你的环境，以检测在部署 MED-V 工作区后可能会发生的某些网络更改，并且可能会影响 MED-V。</span><span class="sxs-lookup"><span data-stu-id="417e6-104">The Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 solution lets you configure your environment to detect certain network changes that might occur after MED-V workspaces are deployed and that can affect MED-V.</span></span>

<span data-ttu-id="417e6-105">此功能包括在来宾操作系统中运行的组件，该组件会在主机上收到网络配置更改通知。</span><span class="sxs-lookup"><span data-stu-id="417e6-105">The feature includes a component running in the guest operating system that is notified of network configuration changes on the host computer.</span></span> <span data-ttu-id="417e6-106">它允许在来宾中运行的非 Microsoft ESD 或其他应用程序解析为主机 ESD 或应用程序解析到的同一网络终结点。</span><span class="sxs-lookup"><span data-stu-id="417e6-106">It allows a non-Microsoft ESD or other application that is running in the guest to resolve to the same network endpoints that the host ESD or application resolves to.</span></span>

<span data-ttu-id="417e6-107">**注意** 只有在虚拟机配置了网络地址转换（NAT）模式的情况下，此功能才可用。</span><span class="sxs-lookup"><span data-stu-id="417e6-107">**Note** This feature is only available if the virtual machine is configured for network address translation (NAT) mode.</span></span> <span data-ttu-id="417e6-108">如果虚拟机配置为桥接模式，则不会生成任何更改指示。</span><span class="sxs-lookup"><span data-stu-id="417e6-108">If the virtual machine is configured for BRIDGED mode, no change indications are generated.</span></span>

 

<span data-ttu-id="417e6-109">本部分提供的信息和说明可帮助你监视可影响 MED-V 的网络更改。</span><span class="sxs-lookup"><span data-stu-id="417e6-109">This section provides information and instruction to assist you in monitoring those network changes that can affect MED-V.</span></span>

## <span data-ttu-id="417e6-110">检测 MED-V 的网络更改</span><span class="sxs-lookup"><span data-stu-id="417e6-110">To detect network changes for MED-V</span></span>


<span data-ttu-id="417e6-111">部署 MED-V 工作区后，您可以通过 preforming 以下任务监视对某些网络配置所做的更改：</span><span class="sxs-lookup"><span data-stu-id="417e6-111">After you have deployed your MED-V workspaces, you can monitor changes to certain network configurations by preforming the following tasks:</span></span>

1. <span data-ttu-id="417e6-112">创建将查找要监视的网络配置更改的托管对象格式（MOF）文件。</span><span class="sxs-lookup"><span data-stu-id="417e6-112">Create a Managed Object Format (MOF) file that will look for the network configuration changes that you want to monitor.</span></span> <span data-ttu-id="417e6-113">以下代码显示了可以创建的 MOF 文件的示例。</span><span class="sxs-lookup"><span data-stu-id="417e6-113">The following code shows an example of the MOF file that you can create.</span></span>

   ``` syntax
   #pragma namespace ("\\\\.\\root\\ccm\\NetworkConfig")

   class CCM_IPConfig
   {
       [NotNull: ToInstance ToSubClass] uint32 AddressFamily; // AF_INET, AF_INET6
       [Key, NotNull: ToInstance ToSubClass] string IPAddress; // IPv4 or IPv6 address
       [NotNull: ToInstance ToSubClass] string SubnetMask; // IPv4 subnet mask
   };

   class CCM_NetworkAdapter
   {
       [Key, NotNull: ToInstance ToSubClass] string Name;
       [NotNull: ToInstance ToSubClass] uint32 DHCPEnabled = 0; 
       [NotNull: ToInstance ToSubClass] uint32 Quarantined = 0; // To check if it is quarantined.
       CCM_IPConfig IPConfigInfo[];
   };

   [singleton]
   class CCM_NetworkAdapters
   {
       [NotNull: ToInstance ToSubClass] String ProviderName; // MED-V or other provider
       CCM_NetworkAdapter AdaptersInfo[];
   };
   ```

2. <span data-ttu-id="417e6-114">编译 MOF 文件。</span><span class="sxs-lookup"><span data-stu-id="417e6-114">Compile the MOF file.</span></span>

3. <span data-ttu-id="417e6-115">在来宾中安装 MOF 文件。</span><span class="sxs-lookup"><span data-stu-id="417e6-115">Install the MOF file in the guest.</span></span>

<span data-ttu-id="417e6-116">安装 MOF 文件后，你可以创建一个事件订阅，用于订阅**CCM \ _NetworkAdapters**类的 Windows Management INSTRUMENTATION （WMI）创建、修改或删除事件。</span><span class="sxs-lookup"><span data-stu-id="417e6-116">After you have installed the MOF file, you can create an event subscription that subscribes to Windows Management Instrumentation (WMI) creation, modification, or deletion events for the **CCM\_NetworkAdapters** class.</span></span> <span data-ttu-id="417e6-117">这会检测到对主机的以下更改：</span><span class="sxs-lookup"><span data-stu-id="417e6-117">This detects the following changes to the host:</span></span>

<span data-ttu-id="417e6-118">是否有对网络的任何配置更改，例如 IP 地址或网络适配器的更改？</span><span class="sxs-lookup"><span data-stu-id="417e6-118">Are there any configuration changes to the network, such as changes to the IP address or network adapter?</span></span>

<span data-ttu-id="417e6-119">网络可用还是不可用？</span><span class="sxs-lookup"><span data-stu-id="417e6-119">Is the network available or unavailable?</span></span>

<span data-ttu-id="417e6-120">网络设置是否已从桥接模式更改为 NAT 模式？</span><span class="sxs-lookup"><span data-stu-id="417e6-120">Was the network setup changed from BRIDGED mode to NAT mode?</span></span>

<span data-ttu-id="417e6-121">网络设置是否已从 NAT 模式更改为桥模式？</span><span class="sxs-lookup"><span data-stu-id="417e6-121">Was the network setup changed from NAT mode to BRIDGED mode?</span></span>

<span data-ttu-id="417e6-122">主机上的 MED-V 组件监视网络的这些更改，然后向访客发出信号。</span><span class="sxs-lookup"><span data-stu-id="417e6-122">A MED-V component on the host monitors the network for these changes and then signals the guest of the change.</span></span> <span data-ttu-id="417e6-123">来宾中的组件创建一个 WMI 实例来监视这些更改的 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="417e6-123">A component in the guest creates a WMI instance to monitor the MED-V workspace for these changes.</span></span>

<span data-ttu-id="417e6-124">当发生一个或多个网络更改时（创建、修改或删除），你创建的事件订阅将通过 WMI 系统提供通知。</span><span class="sxs-lookup"><span data-stu-id="417e6-124">The event subscription you created provides notification through the WMI system when one or more of these network changes – creation, modification, or deletion – occurs.</span></span>

## <span data-ttu-id="417e6-125">相关主题</span><span class="sxs-lookup"><span data-stu-id="417e6-125">Related topics</span></span>


[<span data-ttu-id="417e6-126">监视 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="417e6-126">Monitor MED-V Workspaces</span></span>](monitor-med-v-workspaces.md)

[<span data-ttu-id="417e6-127">管理 MED-V 工作区设置</span><span class="sxs-lookup"><span data-stu-id="417e6-127">Manage MED-V Workspace Settings</span></span>](manage-med-v-workspace-settings.md)

 

 





