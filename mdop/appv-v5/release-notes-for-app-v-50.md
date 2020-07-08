---
title: App-V 5.0 发行说明
description: App-V 5.0 发行说明
author: dansimp
ms.assetid: 68a6a5a1-4b3c-4c09-b00c-9ca4237695d5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e49f6072d738b45afe25de24f2ee9a2d09d64a2e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798266"
---
# App-V 5.0 发行说明


**若要在这些发行说明中搜索特定问题，请按 CTRL + F。**

安装 App-v 5.0 之前，请仔细阅读这些发行说明。

这些发行说明包含成功安装 app-v 5.0 所需的信息。 发行说明还包含产品文档中不可用的信息。 如果这些发行说明和其他 App-v 5.0 文档之间存在差异，则应将最新更改视为权威。 这些发行说明取代了本产品附带的内容。

## 关于产品文档


有关 App-V 5.0 文档的详细信息，请参阅 Microsoft TechNet 上的 app-v 5.0 主页。

## 提供反馈


我们对 app-v 5.0 的反馈感兴趣。 您可以向发送反馈 <mdopdocs@microsoft.com> 。

**注意** 此电子邮件地址不是支持频道，但你的反馈将帮助我们为我们的文档和产品发布计划未来的更改。

 

有关 MDOP 和其他学习资源的最新信息，请参阅[Mdop 信息体验](https://go.microsoft.com/fwlink/p/?LinkId=236032)页面。

有关新更新或提供反馈的详细信息，请在[Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445)或[Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447)上关注我们。

## 有关 App-v 5.0 的已知问题


本部分包含有关 app-v 5.0 的已知问题的发行说明。

### 使用服务器 PowerShell cmdlet 时无法终止添加程序包的添加

使用 PowerShell 添加程序包时，不存在退出添加新程序包的方法。

解决方法：要停止添加程序包，请在添加最终程序包后按**enter** 。

### <a href="" id="-------------app-v-5-0-client-rejects-packages-from-servers-whose-ssl-certificate-has-been-revoked"></a> App-v 5.0 客户端拒绝来自其 SSL 证书已被吊销的服务器的程序包

使用 HTTPS 协议时，App-v 5.0 客户端将默认拒绝来自其 SSL 证书已被吊销的服务器的程序包。 通过修改**VerifyCertificateRevocationList**设置，可以通过配置关闭此行为。 在重新启动 app-v 5.0 服务之前，应用此设置的新配置将不会生效。

解决方法：重新启动 app-v 5.0 服务。

## 发行说明版权信息


Microsoft、Active Directory、ActiveX、Bing、Excel、Silverlight、SQLServer、Windows、MicrosoftIntune 和 WindowsPowerShell 是 Microsoft 公司组的商标。 所有其他商标的所有权属于其各自所有者。








## 相关主题


[关于 App-V 5.0](about-app-v-50.md)

 

 





