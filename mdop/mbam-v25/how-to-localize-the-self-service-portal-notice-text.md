---
title: 如何本地化自助服务门户通知文本
description: 如何本地化自助服务门户通知文本
author: dansimp
ms.assetid: a4c878b7-e5c8-45af-a537-761bb2991659
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a2385f6b00713e7373bd1707b02324b80f300c0d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804023"
---
# 如何本地化自助服务门户通知文本


你可以将本地化声明文本配置为在自助服务门户中默认显示给最终用户。 显示声明文本的 Notice.txt 文件位于以下根目录中：

&lt;*MBAM 自助服务安装目录* &gt;\\Self 服务 Website\\

若要显示本地化声明文本，请创建一个已本地化的 Notice.txt 文件，然后将其保存在以下示例目录中的特定语言文件夹下：

&lt;*MBAM 自助服务安装目录* &gt;\\Self 服务 Website\\

**注意** 你可以使用**应用程序设置**中的**NoticeTextPath**项配置路径。

 

MBAM 根据以下规则显示声明文本：

-   如果在相应的语言文件夹中创建已本地化的**Notice.txt**文件，MBAM 将显示本地化声明文本（如果默认**Notice.txt**文件存在）。 如果缺少默认**Notice.txt**文件，则会显示一条消息，指示缺少默认文件。

-   如果 MBAM 没有找到 Notice.txt 文件的本地化版本，它将在默认 Notice.txt 文件中显示文本。

-   如果 MBAM 没有找到默认的 Notice.txt 文件，它将在自助服务门户中显示默认文本。

**注意** 如果最终用户的浏览器设置为不具有相应语言子文件夹或 Notice.txt 的语言，则显示以下根目录中 Notice.txt 文件中的文本：

&lt;*MBAM 自助服务安装目录* &gt;\\Self 服务 Website\\

 

**创建本地化的 Notice.txt 文件**

1.  在配置了自助服务门户的服务器上，在 &lt; *Language* &gt; 以下示例目录中创建一个语言文件夹，其中的 &lt; *语言* &gt; 表示本地化语言的名称：

    &lt;*MBAM 自助服务安装目录* &gt;\\Self 服务 Website\\

    **注意** 某些语言文件夹已存在，因此你可能不需要创建文件夹。 如果必须创建语言文件夹，请参阅[国际语言支持（NLS） API 参考](https://go.microsoft.com/fwlink/?LinkId=317947)，了解可用于 &lt; *语言*文件夹的有效名称的列表 &gt; 。

     

2.  创建一个包含本地化声明文本的 Notice.txt 文件。

3.  将 Notice.txt 文件保存在 " &lt; *语言*" &gt; 文件夹中。 例如，若要使用西班牙语创建本地化的 Notice.txt 文件，请在以下示例目录中保存本地化的 Notice.txt 文件：

    &lt;*MBAM 自助服务安装目录* &gt;\\Self 服务 Website\\Es-es

    语言文件夹的名称也可以是语言中性名称**es** ，而不是**es**。 如果最终用户的浏览器设置为**es** ，并且该文件夹不存在，则会以递归方式检索和检查父区域设置（在 .net 中定义），并在 &lt; &gt; 最终成为默认 Notice.txt 文件之前解析到 MBAM 自助服务安装目录\\SelfServiceWebsite\\es\\Notice.txt。 此递归回退模拟 .NET 资源加载规则。



## 相关主题


[为组织自定义自助服务门户](customizing-the-self-service-portal-for-your-organization.md)

 

## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





