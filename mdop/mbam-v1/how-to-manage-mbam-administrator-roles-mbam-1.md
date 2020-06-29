---
title: 如何管理 MBAM 管理员角色
description: 如何管理 MBAM 管理员角色
author: dansimp
ms.assetid: c0f25a42-dbff-418d-a776-4fe23ee07d16
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9d00b8ebf66d2b066afae33e67298691285ce9fa
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798178"
---
# 如何管理 MBAM 管理员角色


完成所有服务器功能的 Microsoft BitLocker 管理和监视（MBAM）设置后，必须授予管理员用户访问这些服务器功能的权限。 最佳做法是管理或使用 MBAM 服务器功能的管理员应分配给 Active Directory 安全组，然后应将这些组添加到相应的 MBAM 管理本地组。

**管理 MBAM 管理员角色成员身份**

1.  向 ActiveDirectoryDomain Services 中的安全组分配管理用户。

2.  将 ActiveDirectoryDomain Services 安全组添加到 Microsoft BitLocker 管理和监视服务器上 MBAM 管理本地组的角色，以供各自的功能。 用户角色如下所示：

    -   **MBAM System 管理员**有权访问 MBAM 管理网站中的所有 Microsoft BitLocker 管理和监视功能。

    -   **MBAM 硬件用户**有权访问 MBAM 管理网站中的硬件兼容性功能。

    -   **MBAM 帮助台用户**有权访问 MBAM 管理网站中的 "管理 TPM" 和 "驱动器恢复" 选项，但在使用其中一个选项时，必须填写所有字段。

    -   **MBAM 报表用户**有权访问 MBAM 管理网站中的合规性和审核报告。

    -   **MBAM 高级帮助台使用**有权访问 MBAM 管理网站中的 "管理 TPM" 和 "驱动器恢复" 选项。 当这些用户使用任一选项时，不需要填写所有字段。

    有关 Microsoft BitLocker 管理和监视角色的详细信息，请参阅[规划 MBAM 1.0 管理员角色](planning-for-mbam-10-administrator-roles.md)。

## 相关主题


[管理 MBAM 1.0 功能](administering-mbam-10-features.md)

 

 





