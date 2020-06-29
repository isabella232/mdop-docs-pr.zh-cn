---
title: 如何确定丢失计算机的 BitLocker 加密状态
description: 如何确定丢失计算机的 BitLocker 加密状态
author: dansimp
ms.assetid: dbd23b64-dff3-4913-9acd-affe67b9462e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b9ea4afd6dd08f2040b9e2bd1e1a8998181d1e60
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803603"
---
# 如何确定丢失计算机的 BitLocker 加密状态


你可以使用 Microsoft BitLocker 管理和监视（MBAM）确定丢失或被盗的计算机的上次已知 BitLocker 加密状态。 以下过程介绍了如何在丢失或被盗时确定计算机上的卷是否已加密。

**确定丢失的计算机的上次已知 BitLocker 加密状态**

1.  打开 web 浏览器并导航到 "管理和监视" 网站。

    **注意** 注意：管理和监视网站的默认地址是 http://* &lt; computername &gt; *。 使用完全限定的服务器名称将产生更快的浏览结果。

     

2.  从导航窗格中选择 "**报告**" 节点，然后选择 "**计算机合规性报告**"。

3.  使用右窗格中的筛选字段缩小搜索结果范围，然后单击 "**搜索**"。 结果将显示在搜索查询下方。

4.  采取相应的操作，由策略为丢失设备确定。

    **注意** 设备合规性由您的企业已部署的 BitLocker 策略确定。 你可能需要先验证已部署的策略，然后再尝试确定设备的 BitLocker 加密状态。

     

## 相关主题


[使用 MBAM 执行 BitLocker 管理](performing-bitlocker-management-with-mbam-mbam-2.md)

 

 





