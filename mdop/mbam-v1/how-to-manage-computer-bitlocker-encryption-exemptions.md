---
title: 如何管理计算机 BitLocker 加密免除
description: 如何管理计算机 BitLocker 加密免除
author: dansimp
ms.assetid: d4400a0d-b36b-4cf5-a294-1f53ec47f9ee
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 51b93061468508900eaee7fce8a7827e2db61d19
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803816"
---
# 如何管理计算机 BitLocker 加密免除


Microsoft BitLocker 管理和监视（MBAM）可用于免除某些计算机的 BitLocker 保护。 例如，组织可能会决定逐个计算机地控制 BitLocker 豁免。

若要从 BitLocker 加密中免除计算机，必须将计算机添加到 ActiveDirectoryDomainServices 中的安全组，以便绕过任何基于计算机的 BitLocker 保护规则。

**注意** 如果计算机已受 BitLocker 保护，则计算机豁免策略将不起作用。

 

**从 BitLocker 加密中免除计算机**

1.  将您希望免除的计算机帐户添加到 ActiveDirectoryDomainServices 中的安全组。 这允许你绕过任何基于计算机的 BitLocker 保护规则。

2.  通过使用 MBAM 组策略模板创建组策略对象，然后将组策略对象与您在上一步中创建的 Active Directory 组相关联。 有关创建必要的组策略对象的详细信息，请参阅[部署 MBAM 1.0 组策略对象](deploying-mbam-10-group-policy-objects.md)。

3.  当已免除的计算机启动时，MBAM 客户端将根据计算机是否属于 BitLocker 豁免安全组来检查计算机豁免策略设置并暂停保护。

## 相关主题


[管理 MBAM 1.0 功能](administering-mbam-10-features.md)

 

 





