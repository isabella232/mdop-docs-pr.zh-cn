---
title: 如何管理用户 BitLocker 加密免除
description: 如何管理用户 BitLocker 加密免除
author: dansimp
ms.assetid: 48d69721-504f-4524-8a04-b9ce213ac9b4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8c3d70558a65c3288174413d6c36cc9c77bc9eaa
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798177"
---
# 如何管理用户 BitLocker 加密免除


Microsoft BitLocker 管理和监视（MBAM）可用于管理 BitLocker 保护，exempting 不需要或不希望其驱动器加密的用户。

若要从 BitLocker 保护中免除用户，组织必须首先创建支持此类免除的基础结构。 支持的基础结构可能包括用于请求豁免的联系人电话号码、网页或邮件地址。 此外，必须将任何豁免用户添加到专为豁免用户创建的组策略的安全组中。 当此安全组的成员登录到计算机时，用户组策略将显示用户已被免除了 BitLocker 保护。 用户策略将覆盖计算机策略，并且计算机将保持不受 BitLocker 加密的阻止。

**注意** 如果计算机已受 BitLocker 保护，则用户豁免策略不起作用。

 

下表显示了如何根据如何设置免除来应用 BitLocker 保护。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">用户状态</th>
<th align="left">计算机未豁免</th>
<th align="left">计算机豁免</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>用户不豁免</strong></p></td>
<td align="left"><p>在计算机上强制执行 BitLocker 保护。</p></td>
<td align="left"><p>不会在计算机上强制执行 BitLocker 保护。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>用户豁免</strong></p></td>
<td align="left"><p>不会在计算机上强制执行 BitLocker 保护。</p></td>
<td align="left"><p>不会在计算机上强制执行 BitLocker 保护。</p></td>
</tr>
</tbody>
</table>

 

**从 BitLocker 加密中免除用户**

1.  创建将用于管理来自 BitLocker 加密的用户免除的 ActiveDirectoryDomainServices 安全组。

2.  通过使用 MBAM 组策略模板来创建组策略对象设置。 将组策略对象与您在上一步中创建的 Active Directory 组相关联。 有关使用户能够从 BitLocker 加密中请求豁免的必要策略设置的详细信息，请参阅[规划 MBAM 1.0 组策略要求](planning-for-mbam-10-group-policy-requirements.md)中的 "配置用户豁免策略" 部分。

3.  为 BitLocker 免除的用户创建安全组之后，将请求豁免的用户的名称添加到此群组。 当用户登录到由 BitLocker 控制的计算机时，MBAM 客户端将检查用户豁免策略设置，并根据用户是否属于 BitLocker 豁免安全组来暂停保护。

    **注意** 共享计算机方案需要针对用户例外的特殊注意事项。 如果非豁免用户登录到与豁免用户共享的计算机，则该计算机可能已加密。

     

**使用户能够从 BitLocker 加密请求豁免**

1.  通过 usingwith MBAM 策略模板配置用户豁免策略后，用户可以通过 MBAM 客户端请求 BitLocker 保护中的豁免。

2.  当用户登录到在 MBAM 硬件兼容性列表中标记为**兼容**的计算机时，系统会向用户显示计算机将要加密的通知。 用户可以选择 "**请求豁免** **"，** 然后通过选择 "开始"，然后选择 "**开始**" 接受 BitLocker 加密来推迟加密。

    **注意** 选择 "**请求豁免**" 将推迟 BitLocker 保护，直到用户豁免策略中设置的最长时间。

     

3.  当用户选择 "**请求豁免**" 时，系统会通知用户联系组织的 BitLocker 管理组。 根据配置用户豁免策略的配置方式，向用户提供以下一种或多种联系方法：

    -   电话号码

    -   网页 URL

    -   通讯地址

    提交请求后，MBAM 管理员可以确定是否适合将用户添加到 BitLocker 豁免 Active Directory 组。

    **注意** 一旦用户豁免策略的延迟时间限制已过期，用户将看不到用于向加密策略请求豁免的选项。 此时，用户必须直接联系 MBAM 管理员，以便从 BitLocker 保护接收豁免。

     

## 相关主题


[管理 MBAM 1.0 功能](administering-mbam-10-features.md)

 

 





