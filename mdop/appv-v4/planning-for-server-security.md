---
title: 规划服务器安全
description: 规划服务器安全
author: dansimp
ms.assetid: c7cd8227-b359-41e7-a8ae-d0d5718a76a2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9bea1bd8287a15385200bbfb425ed8e00fbcdb02
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798864"
---
# 规划服务器安全


若要增强环境的安全性，必须查看环境中任何潜在威胁的暴露程度。 为 App-v 基础结构提供安全性要求你使用特定的 App-v 安全功能以及基础基础结构的安全做法和功能。 为诸如 Internet 信息服务（IIS）、Active Directory 域服务和 SQL Server 之类的服务保护基础基础结构将提高 app-v 系统的整体安全性。

服务器安装的默认设置提供最高的安全级别。 但是，某些组件依赖于未配置为安装的一部分的基础基础结构。 遵循安装后步骤后，将增强 app-v 基础结构的安全性。

内容目录包含要向客户端流处理的所有程序包。 这些资源需要尽可能安全地消除许多可能的安全威胁。 下表提供了一些其他指南：

-   基于 UNC 的发布和/或流式处理-此项的权限应该是环境中最严格的限制。 使用 NTFS 权限为内容目录实施最严格的访问控制列表（Acl）（用户 = 读取，管理员 = 读取和写入）。

-   用于发布和/或流式处理的 IIS-将 IIS 配置为仅支持 Windows 集成身份验证。 删除对 IIS 服务器的匿名访问，并使用 NTFS 权限限制对该目录的访问权限。

-   RTSP/RTSPS 流应用程序包-将 App-v 提供程序策略配置为要求身份验证、强制访问权限，并仅启用所需的组以访问提供程序策略。 在数据库中配置具有适当权限的应用程序。

将具有管理权限的用户数保留为最低，以减少数据存储中的数据可能威胁，避免将恶意应用程序发布到基础结构中。

## 应用程序虚拟化安全性


App-v 使用基础结构的各种组件之间的多种通信方法。 在规划 app-v 基础结构时，保护服务器之间的通信可以降低现有网络上可能已经存在的安全风险。

### 数据存储

应用程序虚拟化管理服务器和应用程序虚拟化管理服务通过 TCP 端口1433使用 SQL 连接与数据存储进行通信。 管理服务器使用数据存储检索应用程序和配置数据，并将使用信息写入数据库。 管理服务代表配置 App-v 基础结构的管理员与数据存储进行通信。 由于数据存储包含关键信息，因此最大程度地减少对此数据的威胁非常重要。

建议使用 Internet 协议安全（IPsec）保护 app-v 管理服务器、管理服务和数据存储之间的通信。 具体说来，创建用于保护数据存储（SQL）和管理服务器以及数据存储和管理服务之间的通信通道安全的策略。 你还可以通过 IPsec 部署服务器和域隔离，确保所有 App-v 基础结构组件仅与安全通道通信。 有关实施 IPsec 的详细信息，请参阅以下文档：

-   对于 Windows Server2003，请参阅 <https://go.microsoft.com/fwlink/?LinkId=133226> （） https://go.microsoft.com/fwlink/?LinkId=133226) 。

-   对于 Windows Server2008，请参阅 <https://go.microsoft.com/fwlink/?LinkId=133227> （） https://go.microsoft.com/fwlink/?LinkId=133227) 。

### 内容目录

App-v 管理服务器安装配置内容目录的位置。 此目录是虚拟化应用程序包的存储位置。 此位置可以是服务器的本地位置，也可以放置在远程网络共享上。 因此，实现 IPsec 以帮助保护与内容目录的远程位置的通信。

你还可以使用 IIS 服务器上的虚拟目录将程序包传输到客户端。 如果为内容创建的虚拟目录位于远程源上，请使用 IPsec 来帮助保护 IIS 服务器和远程存储位置之间的通信。

内容目录包含流入客户端的所有程序包。 这些资源需要尽可能安全地消除许多可能的安全威胁。

### 安全协议

你可以使用 RTSPS 或 HTTPS 进行增强的安全通信。 RTSPS 是 App-v 服务器使用的协议，HTTPS 是 IIS 服务器使用的协议。 将应用程序从服务器发布到应用程序虚拟化桌面客户端时，将使用这些协议。 确定所需的协议后，请添加使用该协议的发布服务器。

### <a href="" id="configuring-app-v-servers-for-rtsps-"></a>为 RTSPS 配置 app-v 服务器

安装或配置应用程序 V 管理服务器或流服务器以使用增强的安全（例如 TLS）要求将 x.509 V3 证书预配到 App-v 服务器。 准备为服务器安装或配置安全时，必须满足某些特定要求。 为更安全的 App-v 管理服务器或流服务器部署和配置证书的技术要求包括以下内容：

-   证书必须有效。 否则，客户端将终止连接。

-   证书必须包含正确的增强密钥用法（EKU）-服务器身份验证（OID 1.3.6.1.5.5.7.3.1）。 否则，客户端将终止连接。

-   证书完全限定的域名（FQDN）必须与安装它的服务器相匹配。 例如，如果客户端正在呼叫 `RTSPS://Myserver.mycompany.com/content/MyApp.sft` ，但**颁发给**field 的证书包含 `Myserver1.mycompany.com` ，则客户端将不会连接到服务器，并且会话将终止，即使 `Myserver.mycompany.com` 和 `Myserver1.mycompany.com` 解析为同一 IP 地址也是如此。

    **注意** 如果在网络负载平衡群集中使用 app-v，则必须使用*主题备用名称*（san）配置证书以支持 RTSPS。 有关配置证书颁发机构（CA）和通过 San 创建证书的信息，请参阅 <https://go.microsoft.com/fwlink/?LinkId=133228> （ https://go.microsoft.com/fwlink/?LinkId=133228) 。

     

-   将证书颁发给 App-v 服务器的 CA 必须受连接到服务器的客户端信任。 否则，客户端将终止连接。

-   必须更改*证书私钥*的权限，才能通过服务器 app-v 服务启用访问权限。 默认情况下，App-v 管理服务器和流服务器服务在网络服务帐户下运行。 在服务器上生成 PKCS \ #10 时，将创建一个私钥。 只有本地系统和管理员组有权访问此注册表项。 这些默认 Acl 阻止 App-v 服务器接受安全连接。

    **注意** 有关配置公钥基础结构（PKI）的信息，请参阅 <https://go.microsoft.com/fwlink/?LinkId=133229> （ https://go.microsoft.com/fwlink/?LinkId=133229) 。

     

### 配置具有 HTTPS 的 IIS 服务器

在某些基础结构配置中，app-v 可能使用 IIS 服务器。 有关配置 IIS 服务器的详细信息，请参阅 <https://go.microsoft.com/fwlink/?LinkId=133230> （ https://go.microsoft.com/fwlink/?LinkId=133230) 。

**注意** 如果使用 IIS 发布 .ICO 和 OSD 文件，请为 OSD = TXT 配置 MIME 类型;否则，IIS 将拒绝向客户端提供 .ICO 和 OSD 文件。

 

### 应用程序级安全性

你可以将服务器配置为将特定应用程序流式传输到用户桌面。 但是，访问权限实际上是在程序包级别授予的，而不是在应用程序级别授予的。 虽然特定应用程序可能不会发布到用户的桌面，但如果用户有权添加应用程序或客户端计算机上的管理员，则用户可以在客户端上创建并使用快捷方式来运行程序包中的所有应用程序。

## 针对分布式环境配置 App-V 管理


为特定组织设计基础结构时，可以在安装了 app-v 管理服务器的计算机以外的计算机上安装 app-v 管理 Web 服务。 分离这些 App-v 组件的常见原因包括以下几项：

-   性能

-   可靠性

-   可用性

-   可伸缩性

为了使基础结构正常运行，分离 App-v 管理控制台、管理服务器和管理 Web 服务需要额外的配置。 有关如何配置服务器的详细信息，请参阅[如何将服务器配置为受信任的委派](how-to-configure-the-server-to-be-trusted-for-delegation.md)。

## 相关主题


[规划安全和保护](planning-for-security-and-protection.md)

 

 





