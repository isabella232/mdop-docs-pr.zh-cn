---
title: 如何将网络设置应用于 MED-V 工作区
description: 如何将网络设置应用于 MED-V 工作区
author: dansimp
ms.assetid: 641f46b3-a56f-478a-823b-1d90aa1716b3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5a13227518945e74be9e4b3772af97eadbce3fc4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803984"
---
# <span data-ttu-id="d591e-103">如何将网络设置应用于 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="d591e-103">How to Apply Network Settings to a MED-V Workspace</span></span>


<span data-ttu-id="d591e-104">管理员可以定义每个 MED-V 工作区的网络设置。</span><span class="sxs-lookup"><span data-stu-id="d591e-104">Administrators can define the network settings for each MED-V workspace.</span></span>

<span data-ttu-id="d591e-105">所有网络设置均在 "**网络**" 选项卡上的 "**策略**" 模块中配置。</span><span class="sxs-lookup"><span data-stu-id="d591e-105">All network settings are configured in the **Policy** module, on the **Network** tab.</span></span>

**<span data-ttu-id="d591e-106">将网络设置应用到 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="d591e-106">To apply network settings to a MED-V workspace</span></span>**

1.  <span data-ttu-id="d591e-107">单击要配置的 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="d591e-107">Click the MED-V workspace to configure.</span></span>

2.  <span data-ttu-id="d591e-108">在 "**网络**" 窗格中，按下表中所述配置设置。</span><span class="sxs-lookup"><span data-stu-id="d591e-108">In the **Network** pane, configure the settings as described in the following table.</span></span>

3.  <span data-ttu-id="d591e-109">在 "**策略**" 菜单上，选择 "**提交**"。</span><span class="sxs-lookup"><span data-stu-id="d591e-109">On the **Policy** menu, select **Commit**.</span></span>

**<span data-ttu-id="d591e-110">MED-V 工作区网络属性</span><span class="sxs-lookup"><span data-stu-id="d591e-110">MED-V Workspace Network Properties</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d591e-111">属性</span><span class="sxs-lookup"><span data-stu-id="d591e-111">Property</span></span></th>
<th align="left"><span data-ttu-id="d591e-112">描述</span><span class="sxs-lookup"><span data-stu-id="d591e-112">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d591e-113">TCP/IP 属性</span><span class="sxs-lookup"><span data-stu-id="d591e-113">TCP/IP Properties</span></span></p></td>
<td align="left"><ul>
<li><p><strong><span data-ttu-id="d591e-114">使用主机的 IP 地址（NAT） </strong> ，工作区将使用 NAT 来共享托管通信的主机 IP。</span><span class="sxs-lookup"><span data-stu-id="d591e-114">Use host's IP address (NAT)</strong>—The workspace will use NAT to share the host's IP for outgoing traffic.</span></span></p></li>
<li><p><strong><span data-ttu-id="d591e-115">使用不同于主机的 IP 地址（网桥） </strong> -med-v 工作区将拥有自己的网络地址，通常通过 DHCP 获得。</span><span class="sxs-lookup"><span data-stu-id="d591e-115">Use different IP address than host (Bridge)</strong>—The MED-V workspace will have its own network address, usually obtained via DHCP.</span></span></p></li>
</ul>
<p><span data-ttu-id="d591e-116"><strong> </strong> 当主机具有多个适配器时，选中 "将多个适配器映射到工作区" 复选框。</span><span class="sxs-lookup"><span data-stu-id="d591e-116">Select the <strong>Map multiple adapters into Workspace</strong> check box when the host computer has multiple adapters.</span></span> <span data-ttu-id="d591e-117">当主机在使用不同适配器的不同网络之间移动时，建议使用此配置。</span><span class="sxs-lookup"><span data-stu-id="d591e-117">It is recommended to use this configuration when the host moves between different networks using different adapters.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d591e-118">DNS 服务器</span><span class="sxs-lookup"><span data-stu-id="d591e-118">DNS Server</span></span></p></td>
<td align="left"><ul>
<li><p><strong><span data-ttu-id="d591e-119">不更改 </strong> -不会更改在 med-v 工作区虚拟机中设置的 DNS 设置。</span><span class="sxs-lookup"><span data-stu-id="d591e-119">Don't change</strong>—DNS settings that are set within the MED-V workspace virtual machine will not be changed.</span></span></p></li>
<li><p><strong><span data-ttu-id="d591e-120">使用主机的 DNS 地址 </strong> -将同步 "med-v" 工作区 dns 设置以匹配主机的设置。</span><span class="sxs-lookup"><span data-stu-id="d591e-120">Use Host's DNS address</strong>—MED-V workspace DNS settings will be synchronized to match the host's settings.</span></span> <span data-ttu-id="d591e-121">DNS 同步是动态的。</span><span class="sxs-lookup"><span data-stu-id="d591e-121">The DNS synchronization is dynamic.</span></span> <span data-ttu-id="d591e-122">它将定期与主机进行同步，以便在主机上更改它时，它将在 MED-V 工作区中动态更改。</span><span class="sxs-lookup"><span data-stu-id="d591e-122">It is synchronized periodically with the host so that if it is changed on the host, it will change dynamically in the MED-V workspace.</span></span></p></li>
<li><p><strong><span data-ttu-id="d591e-123">使用特定的 DNS 地址 </strong> -med-v 工作区将根据指定使用特定的 dns。</span><span class="sxs-lookup"><span data-stu-id="d591e-123">Use specific DNS addresses</strong>—The MED-V workspace will use a specific DNS, as specified.</span></span></p>
<p><span data-ttu-id="d591e-124">在 <strong> 主要 </strong> 和 <strong> 辅助字段中 </strong> ，输入主要和辅助 DNS 地址。</span><span class="sxs-lookup"><span data-stu-id="d591e-124">In the <strong>Primary</strong> and <strong>Secondary</strong> fields, enter the primary and secondary DNS addresses.</span></span></p>
<p><span data-ttu-id="d591e-125">选中 " <strong> 追加主机的 DNS 地址" </strong> 复选框以将主机追加到已配置的 DNS 地址。</span><span class="sxs-lookup"><span data-stu-id="d591e-125">Select the <strong>Append Host's DNS addresses</strong> check box to append the host to the configured DNS addresses.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d591e-126">分配 DNS 后缀</span><span class="sxs-lookup"><span data-stu-id="d591e-126">Assign DNS Suffixes</span></span></p></td>
<td align="left"><ul>
<li><p><strong><span data-ttu-id="d591e-127">分配下列后缀 </strong> -选中此复选框以分配特定的 DNS 后缀; 在 "" 框中，输入用逗号分隔的后缀或多个后缀。</span><span class="sxs-lookup"><span data-stu-id="d591e-127">Assign the following suffixes</strong>—Select this check box to assign specific DNS suffixes; in the box, enter a suffix or multiple suffixes separated by commas.</span></span></p></li>
<li><p><strong><span data-ttu-id="d591e-128">"附加主机后缀" </strong> -选中此复选框以将主机后缀追加到 DNS 地址。</span><span class="sxs-lookup"><span data-stu-id="d591e-128">Append host suffixes</strong>—Select this check box to append the host suffixes to the DNS address.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="d591e-129">相关主题</span><span class="sxs-lookup"><span data-stu-id="d591e-129">Related topics</span></span>


[<span data-ttu-id="d591e-130">创建 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="d591e-130">Creating a MED-V Workspace</span></span>](creating-a-med-v-workspacemedv-10-sp1.md)

[<span data-ttu-id="d591e-131">使用 MED-V 管理控制台用户界面</span><span class="sxs-lookup"><span data-stu-id="d591e-131">Using the MED-V Management Console User Interface</span></span>](using-the-med-v-management-console-user-interface.md)

 

 





