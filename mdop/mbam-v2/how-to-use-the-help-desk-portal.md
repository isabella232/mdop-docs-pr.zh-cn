---
title: 如何使用技术支持门户
description: 如何使用技术支持门户
author: dansimp
ms.assetid: c27f7737-10c8-4164-9de8-57987292c89c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fa8813fbe9a7b6980b656ecc673ac4ed618c4cf7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803946"
---
# 如何使用技术支持门户


MBAM 管理和监视网站（也称为帮助桌面门户）是一种管理界面，用于作为 Microsoft BitLocker 管理和监视（MBAM）服务器基础结构的一部分安装的 BitLocker 驱动器加密。 以下部分介绍了如何使用此网站查看报表、恢复最终用户的驱动器以及管理最终用户的 TPMs。

## <a href="" id="bkmk-reports"></a>报告


MBAM 从 Active Directory 和客户端计算机收集信息，这使你可以运行不同的报告来监视 BitLocker 使用情况和合规性。 使用 "管理和监视" 网站的 "**报告**" 部分，你可以生成有关企业合规性、单个计算机和密钥恢复活动的报告。 有关每个报表的说明，请参阅[了解 MBAM 报表](understanding-mbam-reports-mbam-2.md)。

**访问报表**

1.  打开 web 浏览器并导航到 MBAM 管理和监视网站。

2.  在左窗格中选择 "**报表**"。

3.  从顶部菜单栏中，选择要生成的报表类型。 若要保存报表，请单击 "报表" 菜单栏上的 "**导出**" 按钮。

有关如何运行 MBAM 报表的其他信息，请参阅[如何生成 MBAM 报表](how-to-generate-mbam-reports-mbam-2.md)。

## <a href="" id="bkmk-drirec"></a>驱动器恢复


管理和监视网站的**驱动器恢复**功能允许具有特定管理员角色（例如，技术支持用户）的用户访问已由 MBAM 客户端收集的恢复密钥数据。 当 BitLocker 进入恢复模式时，此数据可用于访问受 BitLocker 保护的驱动器。 有关如何恢复处于恢复模式的驱动器的说明，请参阅[如何在恢复模式下恢复驱动器](how-to-recover-a-drive-in-recovery-mode-mbam-2.md)。

您还可以恢复已被移动或损坏的驱动器：

-   [如何恢复已移动的驱动器](how-to-recover-a-moved-drive-mbam-2.md)

-   [如何恢复已损坏的驱动器](how-to-recover-a-corrupted-drive-mbam-2.md)

有关如何恢复受 BitLocker 保护的驱动器的其他信息，请参阅[使用 MBAM 执行 BitLocker 管理](performing-bitlocker-management-with-mbam-mbam-2.md)。

## <a href="" id="bkmk-manatpm"></a>管理 TPM


管理和监视网站的 "管理 TPM" 功能为用户提供某些管理员角色（例如，"MBAM 帮助台用户"）对 MBAM 客户端收集的 TPM 数据的访问权限。 在 TPM 锁定中，管理员可以使用管理和监视网站检索用于解锁 TPM 的必需密码文件。 有关如何在 TPM 锁定后重置 TPM 的说明，请参阅[如何重置 Tpm 锁定](how-to-reset-a-tpm-lockout-mbam-2.md)。

## <a href="" id="bkmk-helpdesk"></a> MBAM 技术支持任务


你可以使用管理和监视网站执行许多管理任务，例如管理受 BitLocker 保护的硬件、恢复驱动器和运行报告。 默认情况下，管理和监视网站的 URL 是 http:// &lt; *MBAMAdministrationServername* &gt; ，但你可以在安装过程中对其进行自定义。

**注意** 若要访问由管理和监视网站提供的各种功能，您必须拥有与您的用户帐户相关联的相应角色。 有关了解用户角色的详细信息，请参阅[如何管理 MBAM 管理员角色](how-to-manage-mbam-administrator-roles-mbam-2.md)。

 

使用以下链接查找有关可通过使用管理和监视网站执行的任务的信息：

-   [如何重置 TPM 锁定](how-to-reset-a-tpm-lockout-mbam-2.md)

-   [如何在恢复模式下恢复驱动器](how-to-recover-a-drive-in-recovery-mode-mbam-2.md)

-   [如何恢复已移动的驱动器](how-to-recover-a-moved-drive-mbam-2.md)

-   [如何恢复已损坏的驱动器](how-to-recover-a-corrupted-drive-mbam-2.md)

-   [如何确定丢失计算机的 BitLocker 加密状态](how-to-determine-bitlocker-encryption-state-of-lost-computers-mbam-2.md)

 

 





