---
title: 配置证书以支持 App-V Management Server 或 Streaming Server
description: 配置证书以支持 App-V Management Server 或 Streaming Server
author: dansimp
ms.assetid: 2f24e550-585e-4b7e-b486-22a3f181f543
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e537244b24d7303af550b3ced8286ba2680009e7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803060"
---
# 配置证书以支持 App-V Management Server 或 Streaming Server


完成证书预配过程并更改私钥权限以支持 App-v 安装后，你可以启动管理服务器或流式处理服务器的设置。 在设置过程中，如果在运行安装程序之前预配了证书，则向导将在**连接安全模式**屏幕中显示证书，并且默认情况下，"**使用增强的安全**" 复选框处于选中状态。

**注意** 选择为 App-v 配置的证书（如果为此服务器预配了一个证书）。

 

**重要提示** 从版本4.2 升级到版本4.5 时，安装程序具有**使用增强安全性**的选项;但是，选择此选项将不会禁用通过 RTSP 进行流式传输。 必须使用管理控制台在安装后禁用 RTSP。

 

选择服务将用于客户端通信的 TCP 端口。 默认端口是 TCP 322;但是，你可以将该端口更改为你的环境的自定义端口。

向导的剩余步骤与在不使用**增强的安全**功能的情况下部署 app-v 管理或流式服务器的情况相同。

## 为 NLB 环境配置证书


为了支持大型企业，通常会将管理服务器放入网络负载平衡（NLB）群集以支持大量连接。 这需要至少两个显示为单个管理服务器的管理服务器。 当你的环境使用具有多个管理服务器的 NLB 群集时，你需要一个用于 NLB 群集的证书的高级配置。

App-v 证书被提交到在运行 Windows Server2003 的计算机上配置的证书颁发机构（CA）。 SAN 允许你通过使用可能与实际计算机名称不同的域名系统（DNS）名称连接到特定的管理服务器 NLB 群集主机名，因为可以有最多32个服务器组成 NLB 群集。

只有在使用 NLB 群集时才需要此配置。 当客户端连接到服务器时，它将使用 NLB 群集的完全限定的域名（FQDN），而不是单个服务器的 FQDN 进行连接。 如果不将 SAN 属性与群集中服务器节点的 FQDN 相加，则所有客户端连接都会被拒绝，因为证书的公用名称不匹配服务器名称。

有关配置具有 SAN 属性的证书的详细信息，请参阅 <https://go.microsoft.com/fwlink/?LinkId=133228> 。

## 相关主题


[配置证书以实现安全的流式处理](configuring-certificates-to-support-secure-streaming.md)

[如何修改私钥权限以支持 Management Server 或 Streaming Server](how-to-modify-private-key-permissions-to-support-management-server-or-streaming-server.md)

 

 





