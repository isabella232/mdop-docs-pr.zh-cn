---
title: AGPM 升级疑难解答
description: AGPM 升级疑难解答
author: dansimp
ms.assetid: 1abbf0c1-fd32-46a8-a3ba-c005f066523d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2089eac51803dca60da51f61ebdb112fbf0bda08
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801740"
---
# AGPM 升级疑难解答

本部分列出了将高级组策略管理（AGPM）服务器升级到较新版本时可能遇到的常见问题（例如，AGPM 4.0 到 AGPM 4.3）。 若要诊断此处未列出的问题，请查看[疑难解答 AGPM](troubleshooting-agpm-agpm40.md)或 AGPM 管理员（"完全控制"）以使用日志记录和跟踪。 有关详细信息，请参阅[配置日志记录和跟踪](configure-logging-and-tracing-agpm40.md)。

## 你遇到了哪些问题？

-   [无法生成 HTML GPO 差异报告（错误代码80004003）](#bkmk-error-80004003)

### <a href="" id="bkmk-error-80004003"></a>无法生成 HTML GPO 差异报告（错误代码80004003）

-   **原因**：你已使用不正确的帐户安装了 AGPM 升级包。

-   **解决方案**：你将需要成为 AGPM 管理员才能解决此问题。
    
    -   请确保你知道**AGPM 服务帐户**的用户名 & 密码。

    -   作为 AGPM 服务帐户交互式登录到 AGPM 服务器。
        
        -   这极其重要，因为如果你使用其他帐户，安装将失败。

    -   关闭 AGPM 服务。
    
    -   安装所需的修补程序。
    
    -   使用 AGPM 客户端连接到 AGPM 以测试差异报告现在是否可正常工作。
    
## 安装修补程序包1（适用于 Microsoft 高级组策略管理 4.0 SP3）
    
**此修复程序中修复的问题**： AGPM 无法在控制或管理新组策略对象（gpo）时生成差异报告。

**如何获取此更新**：安装最新版本的 Microsoft 桌面优化包（[2017 年3月的服务发布](https://www.microsoft.com/download/details.aspx?id=54967)）。 有关详细信息，请参阅[KB 4014009](https://support.microsoft.com/help/4014009/) 。

更具体地说，您可以选择仅下载第一个文件， `AGPM4.0SP1_Server_X64_KB4014009.exe` 从按下 "下载" 按钮后显示的列表中进行选择。
      
Microsoft 桌面优化包的下载链接（2017年3月的服务发布）可在[此处](https://www.microsoft.com/download/details.aspx?id=54967)找到。
      
      
## 引用链接
https://support.microsoft.com/help/3127165/hotfix-package-1-for-microsoft-advanced-group-policy-management-4-0-sp
      
