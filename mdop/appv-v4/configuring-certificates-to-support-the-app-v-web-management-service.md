---
title: 配置证书以支持 App-V Web Management Service
description: 配置证书以支持 App-V Web Management Service
author: dansimp
ms.assetid: b7960161-2c19-4cbf-a98a-d4b06f547dce
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 23839e6fad79c1f10eb2416941396ad3c6f04d26
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803058"
---
# 配置证书以支持 App-V Web Management Service


App-v Web 管理服务必须配置为支持基于 SSL 的连接，以帮助保护通信。 此过程要求安装管理服务的 Web 服务器或计算机具有向服务或计算机颁发的证书。

以下方案说明了如何为此目的获取证书：

1.  公司基础结构已有一个公钥基础结构（PKI），该公钥基础结构将自动向计算机颁发证书。

2.  公司基础结构已有一个 PKI，虽然它不会自动将证书颁发给计算机。

3.  公司基础结构没有 PKI。

在上述每个方案中，获取证书的方法是不同的，但最终结果是相同的。 管理员必须为 IIS 默认网站分配证书，并将 App-v Web 管理服务配置为需要安全通信。

**重要提示** 证书的名称必须与服务器的名称相匹配。 最佳做法是对证书的通用名称使用完全限定的域名（Fqdn）。

 

App-v 可以使用 IIS 服务器支持不同的基础结构配置。 有关配置 IIS 服务器以支持 HTTPS 的详细信息，请参阅 <https://go.microsoft.com/fwlink/?LinkId=151972> 。

## 相关主题


[如何安装和配置 App-V Management Console 以实现更安全的环境](how-to-install-and-configure-the-app-v-management-console-for-a-more-secure-environment.md)

 

 





