---
title: 如何管理用户 BitLocker 加密免除
description: 如何管理用户 BitLocker 加密免除
author: dansimp
ms.assetid: 1bfd9d66-6a9a-4d0e-b54a-e5a6627f5ada
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4d5530701fd208d42dc1f6774fac11ee9ca2036b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803695"
---
# 如何管理用户 BitLocker 加密免除


Microsoft BitLocker 管理和监视（MBAM）可用于通过 exempting 用户（如果存在不需要或希望其驱动器加密的用户）来管理 BitLocker 保护。

若要从 BitLocker 保护中免除用户，组织将必须创建支持免除的用户的基础结构，例如向用户提供用于请求豁免的联系人电话号码、网页或通讯地址。 此外，还必须将豁免用户添加到专为豁免用户创建的组策略对象的安全组。 当此安全组的成员登录到计算机时，用户的组策略设置显示用户已被免除了 BitLocker 保护。 用户的组策略设置将覆盖计算机策略，并且计算机将保持不受 BitLocker 加密的阻止。

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
<td align="left"><p>在计算机上强制执行 BitLocker 保护</p></td>
<td align="left"><p>在计算机上未强制执行 BitLocker 保护</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>用户豁免</strong></p></td>
<td align="left"><p>在计算机上未强制执行 BitLocker 保护</p></td>
<td align="left"><p>在计算机上未强制执行 BitLocker 保护</p></td>
</tr>
</tbody>
</table>

 

**从 BitLocker 加密中免除用户**

1.  创建将用于管理来自 BitLocker 加密要求的用户免除的 ActiveDirectoryDomainServices 安全组。

2.  使用 Microsoft BitLocker 管理和监视组策略模板创建组策略对象设置，并将其与您在上一步中创建的 Active Directory 组相关联。 可在**UserConfiguration\\Administrative Templates\\Windows COMPONENTS\\MDOP MBAM （BitLocker Management）** 下找到豁免用户的策略设置。

3.  为 BitLocker 免除的用户创建安全组之后，将请求豁免的用户的名称添加到此群组。 当用户登录到由 BitLocker 控制的计算机时，MBAM 客户端将检查用户豁免策略设置，并根据用户是否属于 BitLocker 豁免安全组来暂停保护。

    **重要提示** 使用用户例外时，共享计算机方案需要特殊考虑。 如果非豁免用户登录到与豁免用户共享的计算机，则该计算机可能已加密。

     

**使用户能够向 BitLocker 加密请求豁免**

1.  如果你已使用 MBAM 策略模板配置了用户豁免策略，则用户可以通过 MBAM 客户端请求 BitLocker 保护的豁免。

2.  当用户登录到需要加密的计算机时，他们将收到一则通知，告知其计算机将被加密。 他们可以选择 "**请求豁免** **"，** 然后通过选择 "开始"，然后选择 "**开始**" 接受 BitLocker 加密来推迟加密。

    **注意** 选择 "**请求免除**" 将推迟 BitLocker 保护，直到用户豁免策略中设置的最长时间。

     

3.  如果用户选择 "**请求豁免**"，他们将收到通知，告知他们联系您的组织的 BitLocker 管理组。 根据配置用户豁免策略的配置方式，向用户提供以下一种或多种联系方法：

    -   电话号码

    -   网页 URL

    -   通讯地址

    收到豁免请求后，MBAM 管理员可以确定是否适合将用户添加到 BitLocker 豁免 Active Directory 组。

    **注意** 用户提交免除请求后，MBAM 代理会将该用户报告为 "暂时豁免"，然后等待一段可配置的天数，然后再重新检查计算机的合规性。 如果 MBAM 管理员拒绝免除请求，将停用 "免除请求" 选项，这将阻止用户再次请求例外。

     

## 相关主题


[管理 MBAM 2.0 功能](administering-mbam-20-features-mbam-2.md)

 

 





