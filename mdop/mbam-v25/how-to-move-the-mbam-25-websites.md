---
title: 如何移动 MBAM 2.5 网站
description: 如何移动 MBAM 2.5 网站
author: dansimp
ms.assetid: 71af9a54-c27b-408f-9d75-37c0d02e730e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fa5bd8156810b3dccc1588b4dfd4cadd96fd22fb
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803830"
---
# 如何移动 MBAM 2.5 网站


使用以下过程将以下 MBAM 网站从一台计算机移动到另一台计算机，也就是说，将以下功能从服务器 A 移动到服务器 B：

-   管理和监视网站

-   自助服务门户

**重要提示** 在配置这两个网站期间，你必须提供与你当前使用的连接字符串、报表 URL、组帐户和 web 服务应用程序池域帐户相同的连接字符串。 如果不使用相同的值，则无法访问某些服务器。 若要获取当前值，请使用**MbamWebApplication** Windows PowerShell cmdlet。

 

**将管理和监视网站移动到另一台服务器**

1.  在服务器 B 上，安装 MBAM 2.5 服务器软件。 有关说明，请参阅[安装 MBAM 2.5 Server 软件](installing-the-mbam-25-server-software.md)。

2.  在服务器 B 上，启动 "MBAM 服务器配置向导"，单击 "**添加新功能**"，然后仅选择 "**管理和监视网站**" 功能。

    或者，你可以使用**Enable-MbamWebApplication** Windows PowerShell cmdlet 来配置管理和监视网站。

    有关如何配置管理和监视网站的说明，请参阅[如何配置 MBAM 2.5 Web 应用程序](how-to-configure-the-mbam-25-web-applications.md)。

**将自助服务门户移动到另一台服务器**

1.  在服务器 B 上，安装 MBAM 2.5 服务器软件。 有关说明，请参阅[安装 MBAM 2.5 Server 软件](installing-the-mbam-25-server-software.md)。

2.  在服务器 B 上，启动 "MBAM 服务器配置向导"，单击 "**添加新功能**"，然后仅选择 "**自助服务门户**" 功能。

    或者，你可以使用**Enable-MbamWebApplication** Windows PowerShell Cmdlet 配置自助服务门户。

    有关如何配置管理和监视网站的说明，请参阅[如何配置 MBAM 2.5 Web 应用程序](how-to-configure-the-mbam-25-web-applications.md)。

3.  如果你的组织中的客户端计算机无法访问 Microsoft 内容传递网络，你还必须移动 JavaScript 文件。 有关详细信息，请参阅[如何在客户端计算机无法访问 Microsoft 内容传递网络时配置自助服务门户](how-to-configure-the-self-service-portal-when-client-computers-cannot-access-the-microsoft-content-delivery-network.md)。

4.  为你的组织自定义自助服务门户。 使用[自定义组织的自助服务门户](customizing-the-self-service-portal-for-your-organization.md)中的说明查看当前自定义设置，并在服务器 B 上的自助服务器门户上配置自定义设置。



## 相关主题


[如何配置 MBAM 2.5 Web 应用程序](how-to-configure-the-mbam-25-web-applications.md)

[使用 Windows PowerShell 配置 MBAM 2.5 服务器功能](configuring-mbam-25-server-features-by-using-windows-powershell.md)

[将 MBAM 2.5 功能移动到另一个服务器上](moving-mbam-25-features-to-another-server.md)

 

## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





