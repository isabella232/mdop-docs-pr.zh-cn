---
title: 安全地安装 App-V Management Server 或 Streaming Server
description: 安全地安装 App-V Management Server 或 Streaming Server
author: dansimp
ms.assetid: d2a51a81-a80f-427c-a727-611e1eb74f02
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 0150f4dc7f489731c4a818fed9780ebb25dbd24f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798949"
---
# 安全地安装 App-V Management Server 或 Streaming Server


本节中的主题提供有关安装应用程序 V 管理服务器或 App-v 流式处理服务器的增强安全版本的信息。

**注意** 安装或配置应用程序 V 管理或流式服务器以使用增强的安全性（例如，传输层安全性或 TLS）要求 x.509 V3 证书已预配到 app-v 服务器。

 

准备安装或配置安全管理或流式服务器时，请考虑以下技术要求：

-   该证书必须有效。 如果证书无效，客户端将结束连接。

-   证书必须包含正确的*增强密钥用法*（EKU），即服务器身份验证（OID 1.3.6.1.5.5.7.3.1）。 如果证书不包含此 EKU，则客户端将终止连接。

-   证书完全限定的域名（FQDN）必须与安装它的服务器相匹配。 例如，如果客户端正在呼叫， `RTSPS://Myserver.mycompany.com/content/MyApp.sft` 并且 "**颁发给**" 字段的证书设置为 `Server1.mycompany.com` ，则客户端将不会连接到服务器，并且会话将结束。 向用户报告该故障。

    **注意** 如果在网络负载平衡群集中使用 App-v，则必须使用主题备用名称（San）配置证书以支持 RTSPS。 有关配置证书颁发机构（CA）和通过 San 创建证书的信息，请参阅 <https://go.microsoft.com/fwlink/?LinkId=133228> 。

     

-   客户端和服务器需要信任根 CA-将证书颁发给 App-v 服务器的 CA 必须受连接到服务器的客户端信任。 如果不是，则客户端结束连接。

-   证书的专用密钥必须更改权限，以允许 App-v 服务帐户访问证书。 默认情况下，App-v 使用网络服务帐户，并且默认情况下，网络服务帐户不具有访问私钥的权限，这将阻止安全连接。

## 本部分内容


<a href="" id="configuring-certificates-to-support-secure-streaming"></a>[配置证书以实现安全的流式处理](configuring-certificates-to-support-secure-streaming.md)  
提供有关获取、配置和安装证书以支持安全流的信息。

<a href="" id="how-to-modify-private-key-permissions-to-support-management-server-or-streaming-server"></a>[如何修改私钥权限以支持 Management Server 或 Streaming Server](how-to-modify-private-key-permissions-to-support-management-server-or-streaming-server.md)  
提供可用于修改 Windows Server2003 和 Windows Server2008 中的密钥的过程。

<a href="" id="configuring-certificates-to-support-app-v-management-server-or-streaming-server"></a>[配置证书以支持 App-V Management Server 或 Streaming Server](configuring-certificates-to-support-app-v-management-server-or-streaming-server.md)  
提供有关为 App-v 管理或流式处理服务器配置证书的信息，包括有关为网络负载平衡环境配置证书的信息。

 

 





