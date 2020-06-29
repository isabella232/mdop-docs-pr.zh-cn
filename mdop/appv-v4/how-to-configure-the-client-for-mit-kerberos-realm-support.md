---
title: 如何配置客户端以实现 MIT Kerberos 领域支持
description: 如何配置客户端以实现 MIT Kerberos 领域支持
author: dansimp
ms.assetid: 46102f4c-270c-4115-8eb4-7ff5ae3be32d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ae5cd73d00f340bc50070fdd0a5fd3e038cc3789
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801567"
---
# 如何配置客户端以实现 MIT Kerberos 领域支持


在应用程序虚拟化（App-v） 4.5 SP1 中，为 MIT Kerberos 领域添加了支持。 本主题提供有关如何启用该支持的详细信息。

**启用对 MIT Kerberos 领域的支持**

-   创建名为**UseMitKerberos**的新注册表项，如下所示，然后将其设置为值1。

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\UseMitKerberos

 

 





