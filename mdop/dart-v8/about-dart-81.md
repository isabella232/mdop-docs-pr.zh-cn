---
title: 关于 DaRT 8.1
description: 关于 DaRT 8.1
author: dansimp
ms.assetid: dcaddc57-0111-4a9d-8be9-f5ada0eefa7d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 29c7522b4f5a5da3b451b23f2fd200db44bb9481
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802933"
---
# 关于 DaRT 8.1


Microsoft 诊断和恢复工具集（DaRT）8.1 提供了以下增强功能，本主题对此进行了介绍。

## <a href="" id="what-s-new"></a>新增内容


-   **对 WIMBoot 的支持**

    如果满足以下条件，则诊断和恢复工具集8.1 支持 Windows 映像文件启动（WIMBoot）环境：

    -   WIMBoot 基于 Windows 8.1 更新1或更高版本。

    -   DaRT 8.1 映像构建在 Windows 8.1 更新1或更高版本上。

    有关 WIMBoot 的详细信息，请参阅[Windows 映像文件启动（WIMBoot）概述](https://go.microsoft.com/fwlink/?LinkId=517536)。

-   **Windows Server 2012 R2 和 Windows 8.1 的支持**

    你可以使用 Windows Server 2012 R2 或 Windows 8.1 创建 DaRT 映像。

    **注意**  
    对于 Windows Server 和 Windows 操作系统的早期版本，请继续使用早期版本的 DaRT。



-   **客户反馈**

    DaRT 8.1 包括解决自 DaRT 8.0 SP1 发布以来发现的问题的更新。

-   **Windows Defender**

    Windows 8.1 中的 windows Defender 包括改进的保护。 这些更改不会影响你将 DaRT 与 Windows Defender 配合使用的方式。

## 要求


-   **Windows 评估和开发工具包8。1**

    Windows 评估和开发工具包（ADK）8.1 是 DaRT 恢复映像向导必需的先决条件。 Windows ADK 8.1 包含用于自定义、部署和服务 Windows 映像的部署工具。 它还包含 Windows 预安装环境（Windows PE）。

    **注意**  
    如果仅安装远程连接查看器或故障分析器，则不需要 Windows ADK 8.1。



~~~
To download Windows ADK 8.1, see [Windows Assessment and Deployment Kit (Windows ADK) for Windows 8.1](https://www.microsoft.com/download/details.aspx?id=39982) in the Microsoft Download Center.
~~~

-   **Microsoft .NET Framework 4.5。1**

    DaRT 8.1 需要安装 .NET Framework 4.5.1。 若要下载，请参阅 Microsoft 下载中心中的[Microsoft.NET Framework 4.5.1](https://go.microsoft.com/fwlink/?LinkId=329038) 。

-   **Windows 8.1 调试工具**

    若要使用 DaRT 8.1 中的崩溃分析器工具，需要使用适用于 Windows 8.1 的软件开发工具包的调试工具。

    若要下载，请参阅 Microsoft 下载中心中的 windows[软件开发工具包（SDK）（适用于 windows 8.1）](https://msdn.microsoft.com/library/windows/desktop/bg162891.aspx) 。

## 语言可用性


DaRT 8.1 提供以下语言版本：

-   英语（美国） en-us

-   法语（法国） fr-fr

-   意大利语（意大利） it

-   德语（德国） de

-   西班牙语、国际排序（西班牙） es

-   朝鲜语（韩国） ko-KR

-   日语（日本） ja-jp

-   葡萄牙语（巴西） pt-BR

-   俄语（俄罗斯） ru-RU

-   繁体中文 zh-cn&platform-幼圆

-   中文简体 zh-cn&platform-CN

## 如何获取 MDOP 技术


DaRT 8.1 是 Microsoft 桌面优化包（MDOP）的一部分。 MDOP 是 Microsoft 软件保障的一部分。 有关 Microsoft 软件保证和获取 MDOP 的详细信息，请参阅[如何获取 mdop](https://go.microsoft.com/fwlink/?LinkId=322049) （ https://go.microsoft.com/fwlink/?LinkId=322049) 。

## 相关主题


[DaRT 8.1 发行说明](release-notes-for-dart-81.md)









