---
title: 如何确定丢失计算机的 BitLocker 加密状态
description: 如何确定丢失计算机的 BitLocker 加密状态
author: dansimp
ms.assetid: 9440890a-9c63-463b-9113-f46071446388
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d9b977b20ecf219830609c3b1f646a29e6678448
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803539"
---
# 如何确定丢失计算机的 BitLocker 加密状态


Microsoft BitLocker 管理和监视（MBAM）使你能够确定丢失或被盗计算机的上次已知 BitLocker 加密状态。 使用以下过程确定是否已在已不再存在的计算机上加密了这些卷。

**确定计算机的上次已知 BitLocker 加密状态**

1.  打开 MBAM 网站。

    **注意** MBAM 网站的默认地址是 http://* &lt; computername &gt; *。 使用完全限定的服务器名称，以便更快地浏览结果。

     

2.  从导航窗格中选择 "**报告**" 节点，然后选择 "**计算机合规性报告**"。

3.  使用右侧窗格中的筛选字段缩小搜索结果范围，然后单击 "**搜索**"。 结果将显示在搜索查询下方。

4.  采取由策略为丢失的设备确定的相应操作。

    **注意** 设备合规性由已部署的 BitLocker 策略确定。 当你尝试确定设备的 BitLocker 加密状态时，应验证这些已部署的策略。

     

## 相关主题


[使用 MBAM 执行 BitLocker 管理](performing-bitlocker-management-with-mbam.md)

 

 





