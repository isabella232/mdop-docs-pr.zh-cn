---
title: 配置证书以实现安全的流式处理
description: 配置证书以实现安全的流式处理
author: dansimp
ms.assetid: 88dc76d8-7745-4729-92a1-af089c921244
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9376634a1b9843f46dba4cd452e672cc9e535226
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803059"
---
# 配置证书以实现安全的流式处理


默认情况下，App-v 服务在网络服务帐户下运行。 但是，你可以在 Active Directory 域服务中创建服务帐户，并使用 Active Directory 域帐户替换网络服务帐户。

服务运行的安全上下文对于配置增强的安全通信非常重要。 此安全上下文必须具有证书私钥的读取权限。 当为 App-v 服务器生成 PKCS \ #10*证书签名请求*（CSR）时，将调用 Windows*加密服务提供程序*并生成私钥。 私钥受到仅授予系统和管理员帐户权限的权限。

必须修改私钥上的访问控制列表（Acl），以便应用程序-V 管理或流式服务器访问成功的 TLS 安全通信所需的私钥。

## 获取和安装证书


为 App-v 获取和安装证书的方案如下所示：

-   内部公钥基础结构（PKI）。

-   第三方证书颁发证书颁发机构（CA）。

    **注意** 如果需要从第三方 CA 获取证书，请按照该 CA 网站上提供的说明进行操作。

     

如果已部署 PKI 基础结构，请咨询 PKI 管理员，获取符合本主题中所述要求的证书。 如果 PKI 基础结构不可用，请使用第三方 CA 获取有效的证书。

有关获取和安装证书的分步指南，请参阅 <https://go.microsoft.com/fwlink/?LinkId=151969> 。

## 相关主题


配置证书以支持安全流式处理[如何修改私钥权限以支持管理服务器或流式处理服务器](how-to-modify-private-key-permissions-to-support-management-server-or-streaming-server.md)

 

 





