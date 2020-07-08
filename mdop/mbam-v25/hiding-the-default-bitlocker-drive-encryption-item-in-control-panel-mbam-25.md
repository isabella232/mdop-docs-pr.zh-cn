---
title: 在控制面板中隐藏默认的“BitLocker 驱动器加密”项目
description: 在控制面板中隐藏默认的“BitLocker 驱动器加密”项目
author: dansimp
ms.assetid: 6e2a9a02-a809-43a1-80a3-1b03c7192c89
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: af395928ca8934bfea4eeb848bbd4ee377987293
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803300"
---
# 在控制面板中隐藏默认的“BitLocker 驱动器加密”项目


本主题介绍了如何隐藏 " **BitLocker 驱动器加密**控制面板" 项目，该项目在 "控制面板" 中默认显示为 Windows 操作系统的一部分。

**注意** Microsoft BitLocker 管理和监视（MBAM）将创建一个名为**BitLocker 加密选项**的其他自定义控制面板项，这使最终用户能够管理其 PIN 和密码、为驱动器启用 BitLocker 以及检查加密。

 

请参阅[了解 "控制面板" 中的 Bitlocker 加密选项和 Bitlocker 驱动器加密项目](understanding-the-bitlocker-encryption-options-and-bitlocker-drive-encryption-items-in-control-panel.md)，了解：

-   "MBAM" 和 "默认控制面板" 项目之间的差异

-   **管理**在 Windows 资源管理器中右键单击驱动器时出现的 BitLocker 快捷菜单

**重要提示** 不要更改 " **BitLocker 驱动器加密**" 节点中的组策略设置。 如果您这样做，MBAM 将无法正常工作。 在**MDOP MBAM （BitLocker Management）** 节点中配置组策略设置时，MBAM 会自动为你配置**BitLocker 驱动器加密**设置。

 

**隐藏 "控制面板" 中的默认 BitLocker 驱动器加密项目**

1.  在组策略管理控制台（GPMC）或高级组策略管理中，浏览到 "**用户配置** &gt; **策略** &gt; "**管理模板** &gt; **控制面板**。

2.  在 "**详细信息**" 窗格中，双击 "**隐藏指定的控制面板项目**"，然后单击 "**已启用**"。

3.  单击 "**显示**"，单击 "**添加**"，然后键入 " **BitLockerDriveEncryption**"。



## 相关主题


[了解控制面板中的“BitLocker 加密选项”和“BitLocker 驱动器加密”项](understanding-the-bitlocker-encryption-options-and-bitlocker-drive-encryption-items-in-control-panel.md)

[部署 MBAM 2.5 组策略对象](deploying-mbam-25-group-policy-objects.md)

 

## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





