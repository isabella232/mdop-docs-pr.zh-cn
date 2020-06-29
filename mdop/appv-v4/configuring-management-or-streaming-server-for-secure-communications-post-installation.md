---
title: 配置 Management 或 Streaming Server 以实现安全的安装后通信
description: 配置 Management 或 Streaming Server 以实现安全的安装后通信
author: dansimp
ms.assetid: 1062a213-470b-4ae2-b12f-b3e28a6ab745
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2a2713f130809c431b7444f3e928a523838597a6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803056"
---
# 配置 Management 或 Streaming Server 以实现安全的安装后通信


如果在安装 app-v 管理服务器或 App-v 流式处理服务器之前未设置正确的证书，则可以针对初始安装后的应用配置 app-v 以增强安全性。 你可以通过 app-v 管理控制台配置 App-v 管理服务器。 但是，app-v 流处理服务器通过注册表进行管理。 在任何一种情况下，证书都必须包含适用于服务器身份验证的正确*扩展密钥用法*（EKU），并且网络服务必须具有对私钥的读取访问权限。

## 本部分内容


<a href="" id="how-to-configure-management-server-security-post-installation"></a>[如何配置 Management Server 安装后的安全性](how-to-configure-management-server-security-post-installation.md)  
提供可通过使用 App-v 管理控制台执行安装后执行的过程，以添加证书并配置 App-v 管理服务器以增强安全性。

<a href="" id="how-to-configure-streaming-server-security-post-installation"></a>[如何配置 Streaming Server 安装后的安全性](how-to-configure-streaming-server-security-post-installation.md)  
提供可在安装后执行的过程，以添加证书并配置 App-v 流处理服务器以增强安全性。

<a href="" id="troubleshooting-certificate-permission-issues"></a>[解决证书权限问题](troubleshooting-certificate-permission-issues.md)  
提供有关在没有为网络服务的正确 ACL 配置私钥时的故障排除指南。

 

 





