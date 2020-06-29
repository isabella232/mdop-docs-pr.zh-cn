---
title: 如何修改私钥权限以支持 Management Server 或 Streaming Server
description: 如何修改私钥权限以支持 Management Server 或 Streaming Server
author: dansimp
ms.assetid: 1ebe86fa-0fbc-4512-aebc-0a5da991cd43
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 2e35c2df518f22ba81a070d2c40ad3862f376a6a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801252"
---
# 如何修改私钥权限以支持 Management Server 或 Streaming Server


若要支持更安全的 app-v 安装，可以使用以下过程在 Windows Server2003 或 Windows Server2008 中修改私钥。 若要修改私钥的权限，您可以使用 Windows Server2003 资源工具包工具 `WinHttpCertCfg.exe` 。

对于 Windows Server2003，此过程需要满足此文档中列出的先决条件的证书已安装在要安装 app-v 管理或流式处理服务器的计算机或计算机上。 有关使用该工具的其他信息 `WinHttpCertCfg.exe` ，请访问 <https://go.microsoft.com/fwlink/?LinkId=151981> 。

在 Windows Server2008 中，更改私钥的 Acl 的过程更简单。 证书的用户界面可用于管理私钥权限。

**注意** 默认安全上下文为网络服务;但是，可以改为使用域帐户。

 

**在 Windows Server2003 中管理私钥**

1.  在将成为 App-v 管理或流式服务器的计算机上，在命令提示符处键入以下命令以列出分配给特定证书的当前权限：

    `winhttpcertcfg -l -c LOCAL_MACHINE\My -s Name_of_cert`

2.  如有必要，请修改证书的权限以提供对将用于管理或流式处理服务的安全上下文的读取访问权限：

    `winhttpcertcfg -g -c LOCAL_MACHINE\My -s Name_of_cert -a NetworkService`

3.  通过列出证书的权限来验证是否已正确添加了安全上下文：

    `winhttpcertcfg –l –c LOCAL_MACHINE\My –s Name_of_cert`

**在 Windows Server2008 中管理私钥**

1.  使用面向*本地计算机*证书存储的 "*证书*" 管理单元创建 MICROSOFT 管理控制台（MMC）。

2.  展开 MMC，然后选择 "**管理私钥**"。

3.  在 "**安全**" 选项卡上，添加具有**读取**权限的**网络服务**帐户。

## 相关主题


[配置证书以支持 App-V Management Server 或 Streaming Server](configuring-certificates-to-support-app-v-management-server-or-streaming-server.md)

[配置证书以实现安全的流式处理](configuring-certificates-to-support-secure-streaming.md)

 

 





