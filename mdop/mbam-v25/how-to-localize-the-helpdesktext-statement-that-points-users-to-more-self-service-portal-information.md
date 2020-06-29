---
title: 如何本地化指示用户了解更多自助服务门户信息的“HelpdeskText”声明
description: 如何本地化指示用户了解更多自助服务门户信息的“HelpdeskText”声明
author: dansimp
ms.assetid: 09ba2a07-3186-45d9-adef-4034c70ae7cf
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 2367424185da813a46fa52f3614c03083864f75f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803365"
---
# 如何本地化指示用户了解更多自助服务门户信息的“HelpdeskText”声明


你可以配置自助服务门户 "HelpdeskText" 语句的本地化版本，这将通知最终用户使用自助服务门户时如何获取更多帮助。 如果为语句配置本地化的文本，如以下说明中所述，MBAM 显示本地化版本。 如果 MBAM 未找到本地化版本，它将显示**HelpdeskText**参数中的值。

**注意** 在以下说明中， *SelfService*是自助服务门户的默认虚拟目录名称。 当您配置了自助服务门户时，您可能使用了其他名称。

 

**显示 HelpdeskText 语句的本地化版本**

1.  在配置了自助服务门户的服务器上，浏览到 " **Sites** &gt; **Microsoft BitLocker 管理和监视** &gt; **SelfService** &gt; **应用程序设置**" 网站。

2.  在 "**操作**" 窗格中，单击 "**添加**" 以打开 "**添加应用程序设置**" 对话框。

3.  在 "**名称**" 字段中，键入**HelpdeskText**\ _ &lt; *语言* &gt; ，其中 &lt; *语言* &gt; 是文本的相应语言代码。

    例如，若要使用西班牙语创建本地化的 HelpdeskText 语句，请将参数命名为**HelpdeskText \ _es**。

    语言文件夹的名称也可以是语言中性名称**es** ，而不是**es**。 如果最终用户的浏览器设置为**es** ，并且该文件夹不存在，则会以递归方式检索和检查父区域设置（在 .net 中定义），并在 &lt; &gt; 最终成为默认 Notice.txt 文件之前解析到 MBAM 自助服务安装目录\\SelfServiceWebsite\\es\\Notice.txt。 此递归回退模拟 .NET 资源加载规则。

    有关可使用的有效语言代码的列表，请参阅[国际语言支持（NLS） API 参考](https://go.microsoft.com/fwlink/?LinkId=317947)。

4.  在 "**值**" 字段中，键入要向最终用户显示的本地化文本。



## 相关主题


[为组织自定义自助服务门户](customizing-the-self-service-portal-for-your-organization.md)

 

 

## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。



