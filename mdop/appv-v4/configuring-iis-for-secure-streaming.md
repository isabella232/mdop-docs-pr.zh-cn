---
title: 配置 IIS 以实现安全的流式处理
description: 配置 IIS 以实现安全的流式处理
author: dansimp
ms.assetid: 9a80a703-4642-4bec-b7af-dc7cb6b76925
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 724fd247d98c265421cea13f4b91c97049a2b4d4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803057"
---
# 配置 IIS 以实现安全的流式处理


使用 Microsoft Application Virtualization （App-v）版本4.5 的发布，你可以将 HTTP 和 HTTPS 用作将应用程序包传输到 App-v 客户端的协议。 此选项使组织能够利用 IIS 通常提供的其他可伸缩性。 将 IIS 用作流式处理服务器时，可以使用 HTTPS （而不是 HTTP）来保护客户端与服务器之间的通信。

**注意** 如果你想要从文件服务器流出应用程序，你应该增强与应用程序包的通信的安全。 可使用 IPsec 实现此目的。 有关详细信息，请参阅 TechNet 库中的以下主题：

-   对于 Windows Server2003， <https://go.microsoft.com/fwlink/?LinkId=133226>

-   对于 Windows Server 2008， <https://go.microsoft.com/fwlink/?LinkId=133227>

 

## MIME 类型


当你使用 IIS 使用 HTTP 或 HTTPS 流式处理虚拟应用程序时，为了支持 App-v，必须将以下 MIME 类型添加到 IIS 服务器：

-   .OSD = TXT

-   .SFT = Binary

将以下知识库文章用作添加 MIME 类型的指南：

IIS 6.0： <https://go.microsoft.com/fwlink/?LinkId=151973>

IIS 7.0： <https://go.microsoft.com/fwlink/?LinkId=151977>

## Kerberos 身份验证


使用 HTTP 或 HTTPS 和 Kerberos 身份验证流式传输 .ICO、OSD 或 SFT 文件时，您将提高环境的安全性。 但是，为了使 IIS 支持 Kerberos 身份验证，必须配置正确的服务主体名称（SPN）。 此 `setspn.exe` 工具适用于 Windows Server2003 从安装 CD 上的支持工具，内置于 Windows Server2008。

若要创建 SPN，请 `setspn.exe` 从作为域管理员成员身份登录的命令提示符处运行，例如 `setspn.exe –A HTTP/FQDN of Server ServerName` 。

## 相关主题


[配置 Management 或 Streaming Server 以实现安全的安装后通信](configuring-management-or-streaming-server-for-secure-communications-post-installation.md)

 

 





