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
# 检测影响 MED-V 的网络更改


通过 Microsoft 企业桌面虚拟化（MED-V）2.0 解决方案，你可以配置你的环境，以检测在部署 MED-V 工作区后可能会发生的某些网络更改，并且可能会影响 MED-V。

此功能包括在来宾操作系统中运行的组件，该组件会在主机上收到网络配置更改通知。 它允许在来宾中运行的非 Microsoft ESD 或其他应用程序解析为主机 ESD 或应用程序解析到的同一网络终结点。

**注意** 只有在虚拟机配置了网络地址转换（NAT）模式的情况下，此功能才可用。 如果虚拟机配置为桥接模式，则不会生成任何更改指示。

 

本部分提供的信息和说明可帮助你监视可影响 MED-V 的网络更改。

## 检测 MED-V 的网络更改


部署 MED-V 工作区后，您可以通过 preforming 以下任务监视对某些网络配置所做的更改：

1. 创建将查找要监视的网络配置更改的托管对象格式（MOF）文件。 以下代码显示了可以创建的 MOF 文件的示例。

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

2. 编译 MOF 文件。

3. 在来宾中安装 MOF 文件。

安装 MOF 文件后，你可以创建一个事件订阅，用于订阅**CCM \ _NetworkAdapters**类的 Windows Management INSTRUMENTATION （WMI）创建、修改或删除事件。 这会检测到对主机的以下更改：

是否有对网络的任何配置更改，例如 IP 地址或网络适配器的更改？

网络可用还是不可用？

网络设置是否已从桥接模式更改为 NAT 模式？

网络设置是否已从 NAT 模式更改为桥模式？

主机上的 MED-V 组件监视网络的这些更改，然后向访客发出信号。 来宾中的组件创建一个 WMI 实例来监视这些更改的 MED-V 工作区。

当发生一个或多个网络更改时（创建、修改或删除），你创建的事件订阅将通过 WMI 系统提供通知。

## 相关主题


[监视 MED-V 工作区](monitor-med-v-workspaces.md)

[管理 MED-V 工作区设置](manage-med-v-workspace-settings.md)

 

 





