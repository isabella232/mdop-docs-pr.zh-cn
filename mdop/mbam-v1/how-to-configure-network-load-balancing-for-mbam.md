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
# 如何针对 MBAM 配置网络负载均衡


若要验证是否满足安装 "管理和监视服务器" 功能的先决条件和硬件和软件要求，请参阅[MBAM 1.0 部署先决条件](mbam-10-deployment-prerequisites.md)和[MBAM 1.0 支持的配置](mbam-10-supported-configurations.md)。

**注意** 若要获取安装程序日志文件，必须通过使用**msiexec**程序包和 **/l** Location 选项安装 Microsoft BitLocker 管理和监视（MBAM） &lt; &gt; 。 将在您指定的位置创建日志文件。

其他安装日志文件将在安装 MBAM 的用户的% temp% 文件夹中创建。

 

用于管理和监视服务器功能的网络负载平衡（NLB）群集在 MBAM 中提供了可伸缩性，并且它应支持超过 55000 MBAM 客户端计算机。

**注意** Windows Server 网络负载平衡将客户端请求分配到一组配置为单个服务器群集的服务器上。 当网络负载平衡安装在群集中的每个服务器（主机）上时，群集会向客户端请求显示虚拟 IP 地址或完全限定的域名（FQDN）。 初始客户端请求转到群集中的所有主机，但只有一个主机接受和处理该请求。

所有将属于 NLB 群集的计算机都具有以下要求：

-   NLB 群集中的所有计算机必须位于同一个域中。

-   NLB 群集中的每台计算机都必须使用静态 IP 地址。

-   NLB 群集中的每台计算机都必须启用网络负载平衡。

-   NLB 群集需要静态 IP 地址，并且必须在域名系统（DNS）中手动创建主机记录。

 

## 为 MBAM 管理和监视服务器配置网络负载平衡


以下步骤介绍了如何为两个 MBAM 管理和监视服务器配置 NLB 群集虚拟名称和 IP 地址，以及如何将 MBAM 客户端配置为使用 NLB 群集。

在开始本主题中所述的过程之前，必须通过在两台单独的服务器计算机上使用相同的 IIS 端口绑定来成功安装 MBAM 管理和监视服务器功能，同时满足 MBAM Server 功能安装和 NLB 群集配置的先决条件。

**注意** 本主题介绍使用网络负载平衡管理器创建 NLB 群集的基本过程。 将 Windows Server 配置为 NLB 群集的确切步骤取决于所使用的 Windows 服务器版本。。 有关如何在 WindowsServer2008 上创建 NLBs 的详细信息，请参阅在 Windows Server2008 TechNet 库中[创建网络负载平衡群集](https://go.microsoft.com/fwlink/?LinkId=197176)。

 

**为两个 MBAM 管理和监视服务器配置 NLB 群集虚拟名称和 IP 地址**

1.  单击 "**开始**"，单击 "**所有程序**"，单击 "**管理工具**"，然后单击 "**网络负载平衡管理器**"。

    **注意** 如果 NLB 管理器不存在，则可以将其作为 WindowsServer 功能进行安装。 如果要将此功能配置到 NLB 群集，则必须在 MBAM 管理服务器和监视服务器上安装此功能。

     

2.  在菜单栏上，单击 "**群集**"，然后单击 "**新建**" 以打开 "**群集参数**" 对话框。

3.  在 "**群集参数**" 对话框中，输入 NLB 群集 IP 配置的信息：

    -   **IP 地址：** 在 DNS 中注册的 NLB 群集 IP 地址

    -   **子网掩码：** 在 DNS 中注册的 NLB 群集 IP 地址子网掩码

    -   **Internet 完整名称：** 在 DNS 中注册的 NLB 群集名称的 FQDN

4.  确保在 "**群集操作" 模式**下选中了 "**单播**"，然后单击 "**下一步**"。

5.  在 "**群集 IP 地址**" 页面上，单击 "**下一步**"。

6.  在 "**端口规则**" 页面上，单击 "**编辑**" 以定义 nlb 群集将响应的端口，并配置用于客户端到站点系统通信的端口（在为网站定义）时，或单击 "**下一步**" 以启用 nlb 群集 IP 地址以响应所有 tcp/ip 端口。

    **注意** 确保将 "**相关性**" 设置为 "**单一**"。

     

7.  在 "**连接**" 页面上，输入 MBAM 管理和监视服务器实例主机名称，该名称将成为**主机**中 NLB 群集的一部分，然后单击 "**连接**"。

8.  在**可用于配置新群集的接口**中，选择将配置为响应 NLB 群集通信的网络接口，然后单击 "**下一步**"。

9.  在 "**主机参数**" 页面上，查看所显示的信息以确保**专用 IP 配置**设置显示正确的 NLB 群集主机的专用主机 IP 配置，检查是否**已启动**初始主机状态**默认状态：** "已启动"，然后单击 "**完成**"。

    **注意** "**主机参数**" 页面还显示 NLB 群集主机优先级，即1到32。 在将新主机添加到 NLB 群集时，主机优先级必须与以前添加的主机不同。 使用网络负载平衡管理器时，将自动增加优先级。

     

10. 单击 " ** &lt; nlb 群集 &gt; 名称**"，确保 NLB 主机接口**状态**在继续操作之前显示**聚合**。 此步骤可能要求你将 NLB 群集显示刷新为 NLB 管理器正在修改的主机 TCP/IP 配置。

11. 若要向 NLB 群集添加其他主机，请右键单击 " ** &lt; nlb 群集 &gt; 名称**"，单击 **"添加主机到群集"，** 然后为将成为 NLB 群集一部分的每个站点系统重复步骤7到10。

12. 在安装了 MBAM 组策略模板的计算机上，修改 MBAM 组策略设置以将 MBAM 服务终结点配置为使用 NLB 群集名称和相应的 IIS 端口绑定来访问安装在 NLB 群集计算机上的 MBAM 管理和监视服务器功能。 有关如何编辑 MBAM GPO 设置的详细信息，请参阅[如何编辑 MBAM 1.0 Gpo 设置](how-to-edit-mbam-10-gpo-settings.md)。 如果 MBAM 管理服务器和监视服务器对于你的环境而言是新的，请确保已正确配置所需的本地安全组成员身份。 有关安全组要求的详细信息，请参阅[规划 MBAM 1.0 管理员角色](planning-for-mbam-10-administrator-roles.md)。

13. NLB 群集配置完成后，我们建议你验证 MBAM 管理和监视 NLB 群集是否正常工作。 若要执行此操作，请在不是在 NLB 中配置的服务器之外的计算机上打开 web 浏览器，并确保可以使用 NLB FQDN 访问 MBAM 管理和监视网站。

## 相关主题


[部署 MBAM 1.0 服务器基础结构](deploying-the-mbam-10-server-infrastructure.md)

 

 





