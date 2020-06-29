---
title: 如何在客户端计算机无法访问 Microsoft 内容交付网络时配置自助服务门户
description: 如何在客户端计算机无法访问 Microsoft 内容交付网络时配置自助服务门户
author: dansimp
ms.assetid: 90ee76db-9876-41b5-994a-118556d5ed3b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ffce3dd023cb6ff9bd5cdb13ea789b348661de24
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803579"
---
# 如何在客户端计算机无法访问 Microsoft 内容交付网络时配置自助服务门户


如果组织中的客户端计算机无法访问 Microsoft Ajax 内容交付网络（CDN），请按照以下说明操作。

**为什么需要配置：**

客户端计算机需要访问 CDN，这将为自助服务门户提供对某些 JavaScript 文件所需的访问权限。 如果在客户端计算机无法访问 CDN 时未配置自助服务门户，则仅显示公司名称和最终用户登录时所用的帐户。 将不会显示任何错误消息。

**注意** 在 MBAM 2.5 SP1 中，这些 JavaScript 文件包含在产品中，你无需按照本部分中的说明将 SSP 配置为支持无法访问 internet 的客户端。

 

**如何在客户端计算机无法访问 CDN 时配置自助服务门户**

1. 从 CDN 下载以下 JavaScript 文件：

   -   [jQuery-1.10.2.min.js](https://go.microsoft.com/fwlink/?LinkID=390515)

   -   [jQuery.validate.min.js](https://go.microsoft.com/fwlink/?LinkID=390516)

   -   [jQuery.validate.unobtrusive.min.js](https://go.microsoft.com/fwlink/?LinkID=390517)

2. 将 JavaScript 文件复制到自助服务门户的 "**脚本**" 目录中。 此目录位于 <em> &lt; MBAM 自助服务安装目录 &gt; \\ </em> 自助服务 Website\\Scripts。

3. 打开 Internet Information Services （IIS）管理器。

4. 展开 "**网站** &gt; **Microsoft BitLocker 管理和监视**"，然后突出显示**SelfService**。

   **注意**  
   *SelfService*是默认的虚拟目录名称。 如果在配置期间为此目录选择了其他名称，请记住使用您选择的名称替换这些说明中的*SelfService* 。

     

5. 在中间窗格中，双击 "**应用程序设置**"。

6. 对于下表中的每个项目，通过 &lt; *virtual directory* &gt; 使用/SelfService/（或在配置期间选择的任何名称），编辑应用程序设置以引用新位置。 例如，虚拟目录路径将类似于/selfservice/Scripts/jQuery-1.10.2.min.js。

   -   jQueryPath：/ &lt; *virtual directory* &gt; /Scripts/jQuery-1.10.2.min.js

   -   jQueryValidatePath：/ &lt; *virtual directory* &gt; /Scripts/jQuery.validate.min.js

   -   jQueryValidateUnobtrusivePath：/ &lt; *virtual directory* &gt; /Scripts/jQuery.validate.unobtrusive.min.js



## 相关主题


[如何配置 MBAM 2.5 Web 应用程序](how-to-configure-the-mbam-25-web-applications.md)

 

## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





