---
title: 安全和保护概述
description: 安全和保护概述
author: dansimp
ms.assetid: a43e1c53-7936-4d48-a110-0be26c8e9d97
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b08b7dcb3defa8a01a4fd8a3e7234b5ac2956c4e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798815"
---
# 安全和保护概述


Microsoft Application Virtualization 4.5 提供以下增强的安全功能，可帮助你规划和实现更安全的部署策略：

-   现在，应用程序虚拟化支持使用 x.509 V3 证书的传输层安全（TLS）。 如果服务器证书已预配到计划的应用程序虚拟化管理或流服务器，则使用 RTSPS 协议通过端口322的安装将默认安全。 使用 RTSPS 可确保应用程序虚拟化服务器和应用程序虚拟化客户端之间的通信已签名和加密。 如果在应用程序虚拟化服务器安装期间未向服务器分配证书，则通信将通过端口554设置为 RTSP。

    **安全说明：**

    若要帮助提供服务器的安全设置，必须确保 RTSP 端口已被禁用，即使已将所有程序包配置为使用 RTSPS。

    如果在安装服务器之后向服务器添加安全证书，则服务器可能无法检测到证书。 若要帮助确保安全证书检测，请在添加证书后重新启动服务器。

-   客户端必须配置为使用与服务器相同的协议和端口，否则它将无法与服务器通信。 客户端还必须信任该证书的颁发者，并与其受信任的根存储中的几个主要提供商一起提供。 你可以使用自签名证书，但你将需要更新客户端。

-   将 IIS 服务器配置为使用 HTTPS 协议进行流式处理时，你需要在 IIS 服务器上设置安全套接字层（SSL），并为服务器预配证书。 客户端也需要配置为信任颁发服务器证书的根证书颁发机构。

-   已将 Kerberos 身份验证作为默认身份验证机制添加到 Microsoft Application Virtualization。 早期版本依赖于 NTLM V2 进行身份验证。 使用 Kerberos 身份验证增强了客户端与应用程序虚拟化服务器之间的通信安全。 从客户端启动连接后，应用程序虚拟化服务器使用密钥分发中心（KDC）验证会话票证。

-   由于支持使用服务器证书和使用 RTSPS 或 HTTPS 协议，因此您现在可以支持企业网络外部的客户端。 这有助于消除移动用户在启动应用程序虚拟化预配应用程序之前设置到企业网络（VPN、RAS 等）的安全连接的需要。

应考虑的其他重要安全注意事项包括以下内容：

-   始终保持服务器完全更新和保护。

-   若要添加证书以启用到应用程序虚拟化管理服务器的更安全的通信，必须满足以下条件：

    -   将添加证书的用户必须是证书存储所在的服务器上的管理员。

    -   必须启动服务器服务。

    -   管理服务器上的端口139必须打开 Web 服务 server'sIP。

-   使用访问控制列表（Acl）确保应用程序包和所有程序包文件受到保护，并且不能被篡改。 Acl 限制对存储程序包的位置或文件夹的访问权限，仅允许特定帐户访问。

-   确保应用程序虚拟化管理服务器和数据库之间的通道受保护，例如使用 IPsec。

-   如果程序包存储在 SAN 或 NAS 上，请确保中央存储设备与应用程序虚拟化服务器之间的连接受到保护。

-   客户端的所有通信信道都应受到保护，包括与发布服务器、应用程序虚拟化服务器的连接，以及到 OSD 和 .ICO 文件的路径-使用 HTTPS 或 IPsec 等协议。 

-   客户端权限应配置为帮助确保程序包不会被用户篡改。 特别重要的是，不要授予用户在系统上添加或更新程序包的权限，例如与多个用户共享的远程桌面会话主机（RDSession Host）服务器。

-   必须跨域或林环境允许 Kerberos 身份验证，服务器管理控制台才能正常工作。

-   此版本的软件不支持在同一台计算机上托管基于 Kerberos 的 RTSP 服务器和基于 Microsoft NTLM 的 IIS 服务器。 若要在同一台计算机上托管 RTSP 服务器和 IIS 服务器，请从 IIS 服务器中删除 SPN 并使用 NTLM 身份验证。

## 相关主题


[规划 Application Virtualization System 部署](planning-for-application-virtualization-system-deployment.md)

 

 





