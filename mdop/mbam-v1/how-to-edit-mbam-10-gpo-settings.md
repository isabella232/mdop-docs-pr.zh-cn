---
title: 如何编辑 MBAM 1.0 GPO 设置
description: 如何编辑 MBAM 1.0 GPO 设置
author: dansimp
ms.assetid: 03d12fbc-4302-43fc-9b38-440607d778a1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 824fbc2fe0d8f2b00c32de177733e4e327cf4d44
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803537"
---
# 如何编辑 MBAM 1.0 GPO 设置


若要成功部署 Microsoft BitLocker 管理和监视（MBAM），必须首先确定你将在 Microsoft BitLocker 管理和监视的实现中使用的组策略。 有关各种可用策略的详细信息，请参阅[规划 MBAM 1.0 组策略要求](planning-for-mbam-10-group-policy-requirements.md)。 确定要使用的策略后，必须修改包含 MBAM 策略设置的一个或多个组策略对象（GPO）。

以下步骤介绍了如何配置基本的推荐组策略对象（GPO）设置，以使 MBAM 能够管理组织的客户端计算机的 BitLocker 加密。

**编辑 MBAM 客户端 GPO 设置**

1.  在安装了 MBAM 组策略模板的计算机上，请确保启用 MBAM 服务。

2.  对这些操作使用组策略管理控制台（GPMC）或高级组策略管理（AGPM） MDOP 产品：选择 "**计算机配置**"，选择 "**策略**"，单击 "**管理模板**"，选择 " **Windows 组件**"，然后单击 " **MDOP MBAM （BitLocker 管理）**"。

3.  编辑在客户端计算机上启用 MBAM 客户端服务所需的组策略对象设置。 对于下表中的每个策略，依次选择 "**策略组**"、"**策略**" 和 "配置"**设置**。

    策略组

    策略

    设置

    客户端管理

    配置 MBAM 服务

    已启用。 设置**MBAM 恢复和硬件服务终结点**，并**选择要存储的 BitLocker 恢复信息**。

    设置**MBAM 合规性服务终结点**，并**在（分钟）内输入状态报告频率**。

    允许硬件兼容性检查

    已禁用。 此策略默认情况下处于启用状态，但基本 MBAM 实现不需要此策略。

    操作系统驱动器

    操作系统驱动器加密设置

    已启用。 **为操作系统驱动器设置选择保护程序**。 这是将操作系统驱动器数据保存到 MBAM 密钥恢复服务器所必需的。

    可移动驱动器

    控制可移动驱动器上的 BitLocker 的使用

    已启用。 如果 MBAM 将可移动驱动器数据保存到 MBAM 密钥恢复服务器，则这是必需的。

    固定驱动器

    在固定驱动器上控制 BitLocker 的使用

    已启用。 如果 MBAM 将把固定的驱动器数据保存到 MBAM 密钥恢复服务器，则这是必需的。

    设置**选择如何恢复受 BitLocker 保护的驱动器**，并**允许数据恢复代理**。



~~~
**Important**  
Depending on the policies that your organization decides to deploy, you may have to configure additional policies. See [Planning for MBAM 1.0 Group Policy Requirements](planning-for-mbam-10-group-policy-requirements.md) for Group Policy configuration details for all of the available MBAM GPO policy options.
~~~



## 相关主题


[部署 MBAM 1.0 组策略对象](deploying-mbam-10-group-policy-objects.md)









