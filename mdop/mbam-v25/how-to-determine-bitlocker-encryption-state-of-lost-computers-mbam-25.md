---
title: 如何确定丢失计算机的 BitLocker 加密状态
description: 如何确定丢失计算机的 BitLocker 加密状态
author: dansimp
ms.assetid: 4f4bec1b-df3e-40ee-b431-291440268d64
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 95fb843b230804417e375946814a585d1d681634
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803575"
---
# 如何确定丢失计算机的 BitLocker 加密状态


将此过程与管理和监视网站配合使用以确定以下内容：

-   已丢失或被盗计算机的上次已知 BitLocker 加密状态

-   已丢失或被盗计算机上的卷是否已加密

若要完成此任务，你需要访问管理和监视网站的 "**报告**" 区域。 若要获取对此区域的访问权限，您必须分配有 MBAM Report Users 角色。 创建这些角色时，可能会为这些角色指定不同的名称。 有关详细信息，请参阅[规划 MBAM 2.5 组和帐户](planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles)。

**注意** 设备合规性由您的企业已部署的 BitLocker 策略确定。 你可能需要先验证已部署的策略，然后再尝试确定设备的 BitLocker 加密状态。

 

**确定丢失的计算机的上次已知 BitLocker 加密状态**

1.  打开 web 浏览器并导航到 "**管理和监视" 网站**。

2.  在左窗格中，选择 "**报表**" 以打开 "报表" 页面。

3.  选择 "**计算机合规性报告**"。

4.  使用右窗格中的筛选字段缩小搜索结果范围，然后单击 "**搜索**"。 结果将显示在搜索查询下。

5.  采取相应的操作，由策略为丢失设备确定。



## 相关主题


[使用 MBAM 2.5 执行 BitLocker 管理](performing-bitlocker-management-with-mbam-25.md)

 
## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。
 





