---
title: 如何管理 MBAM 管理员角色
description: 如何管理 MBAM 管理员角色
author: dansimp
ms.assetid: 813ac0c4-3cf9-47af-b4cb-9395fd915e5c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 14e9128904b448b20e0596a2630627b7ca8e711d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803704"
---
# 如何管理 MBAM 管理员角色


在 Microsoft BitLocker 管理和监视（MBAM）安装完成所有服务器功能后，系统将必须授予管理员用户访问权限。 最佳做法是将管理或使用 Microsoft BitLocker 管理和监视服务器功能的管理员分配给域服务安全组，然后应将这些组添加到相应的 MBAM 管理本地组。

**管理 MBAM 管理员角色成员身份**

1.  将管理用户分配到 ActiveDirectory 域服务中的安全组。

2.  将 ActiveDirectory 安全组添加到 MBAM 服务器上 MBAM 管理本地组的角色，以获得各自的功能。

    -   **MBAM System 管理员**有权访问 MBAM 管理和监控网站中的所有 MBAM 功能。

    -   **MBAM 帮助台用户**有权访问 MBAM 管理和监视网站中的 "管理 TPM" 和 "驱动器恢复" 选项，但在使用其中一个选项时，必须填写所有字段。

    -   **MBAM 报表用户**有权访问 MBAM 管理和监视网站中的合规性和审核报告。

    -   **MBAM 高级帮助台用户**可以访问 MBAM 管理和监视网站中的 "管理 TPM" 和 "驱动器恢复" 选项，但不需要在使用任一选项时填写所有字段。

    有关 Microsoft BitLocker 管理和监视角色的详细信息，请参阅[规划 MBAM 2.0 管理员角色](planning-for-mbam-20-administrator-roles-mbam-2.md)。

## 相关主题


[管理 MBAM 2.0 功能](administering-mbam-20-features-mbam-2.md)

 

 





