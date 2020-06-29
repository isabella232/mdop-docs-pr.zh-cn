---
title: 如何编辑 MBAM 2.0 GPO 设置
description: 如何编辑 MBAM 2.0 GPO 设置
author: dansimp
ms.assetid: f5ffa93d-b4d2-4317-8a1c-7d2be0264fe3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: aaf7c7aab4baba66513edbfa2489fbe53c97dda8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803498"
---
# 如何编辑 MBAM 2.0 GPO 设置


若要成功部署 Microsoft BitLocker 管理和监视（MBAM），首先需要确定你将在 Microsoft BitLocker 管理和监视的实现中使用的组策略。 有关可用的不同策略的详细信息，请参阅[规划 MBAM 2.0 组策略要求](planning-for-mbam-20-group-policy-requirements-mbam-2.md)。 确定要使用的策略后，必须修改一个或多个组策略对象（GPO），其中包含 MBAM 的策略设置。

你可以使用以下步骤配置基本的推荐 GPO 设置，以使 MBAM 能够管理组织的客户端计算机的 BitLocker 加密。

**编辑 MBAM 客户端 GPO 设置**

1.  在安装了 MBAM 组策略模板的计算机上，请确保启用 MBAM 服务。

2.  在安装了 MBAM 组策略模板的计算机上使用组策略管理控制台（GPMC）或高级组策略管理（AGPM） MDOP 产品，选择 "**计算机配置**"，选择 "**策略**"，单击 "**管理模板**"，选择 " **Windows 组件**"，然后单击 " **MDOP MBAM" （BitLocker Management）**。

3.  编辑在客户端计算机上启用 MBAM 客户端服务所需的组策略对象设置。 对于后面的表中的每个策略，选择 "**策略组**"，单击该**策略**，然后配置**设置**：

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">策略组</th>
    <th align="left">策略</th>
    <th align="left">设置</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>客户端管理</p></td>
    <td align="left"><p>配置 MBAM 服务</p></td>
    <td align="left"><p>已启用。 设置 <strong> MBAM 恢复和硬件服务终结点 </strong> ，并 <strong> 选择要存储的 BitLocker 恢复信息 </strong> 。 设置 <strong> MBAM 合规性服务终结点 </strong> ，并在（分钟）内输入状态报告频率。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>操作系统驱动器</p></td>
    <td align="left"><p>操作系统驱动器加密设置</p></td>
    <td align="left"><p>已启用。 <strong>为操作系统驱动器设置选择保护程序 </strong> 。 将操作系统驱动器数据保存到 MBAMKey 恢复服务器所需。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>可移动驱动器</p></td>
    <td align="left"><p>控制可移动驱动器上的 BitLocker 的使用</p></td>
    <td align="left"><p>已启用。 如果 MBAM 会将可移动驱动器数据保存到 MBAM 密钥恢复服务器，则为必需。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>固定驱动器</p></td>
    <td align="left"><p>在固定驱动器上控制 BitLocker 的使用</p></td>
    <td align="left"><p>已启用。 如果 MBAM 会将固定驱动器数据保存到 MBAM 密钥恢复服务器，则是必需的。</p>
    <p>设置 <strong> 选择如何恢复受 BitLocker 保护的驱动器 </strong> ，并 <strong> 允许数据恢复代理 </strong> 。</p></td>
    </tr>
    </tbody>
    </table>



~~~
**Important**  
Depending on the policies that your organization decides to deploy, you may have to configure additional policies. See [Planning for MBAM 2.0 Group Policy Requirements](planning-for-mbam-20-group-policy-requirements-mbam-2.md) for Group Policy configuration details for all of the available MBAM GPO policy options.
~~~



## 相关主题


[部署 MBAM 2.0 组策略对象](deploying-mbam-20-group-policy-objects-mbam-2.md)









