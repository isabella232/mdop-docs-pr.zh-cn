---
title: 如何安装和配置 App-V Management Console 以实现更安全的环境
description: 如何安装和配置 App-V Management Console 以实现更安全的环境
author: dansimp
ms.assetid: 9d89ef09-cdbf-48fc-99da-b24fc987ef8f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9887787d1e203410b5517439d897260305d7526e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801391"
---
# 如何安装和配置 App-V Management Console 以实现更安全的环境


App-v 管理控制台的默认安装包括对安全通信的支持。 当控制台首次启动时或连接到其他 App-v Web 管理服务时，将在每个连接的基础上配置每个管理控制台。 默认配置通过 TCP 端口443使用 SSL。 如果在服务器上修改了端口号，则可以更改端口号。 你可以使用以下过程通过安全连接连接到 App-v Web 管理服务。

**如何使用 SSL 连接连接到 app-v 管理服务**

1.  启动应用程序虚拟化管理控制台。

2.  在控制台的 "操作" 窗格中，单击 "**配置连接**"。

3.  键入**Web 服务主机名**，确保选中 "**使用安全连接**"。

    **重要提示** Web 服务主机名称中提供的名称必须与证书上的公用名称相匹配，否则连接将失败。

     

4.  选择相应的登录凭据，然后单击 **"确定"**。

## 相关主题


[配置证书以支持 App-V Web Management Service](configuring-certificates-to-support-the-app-v-web-management-service.md)

 

 





