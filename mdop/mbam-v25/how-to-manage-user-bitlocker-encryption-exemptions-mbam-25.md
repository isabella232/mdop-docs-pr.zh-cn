---
title: 如何管理用户 BitLocker 加密免除
description: 如何管理用户 BitLocker 加密免除
author: dansimp
ms.assetid: f582ab82-5bb5-4cd3-ad7c-483240533cf9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c4224a0fb6d905c2362659efe7cf05e16756f7c0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804039"
---
# 如何管理用户 BitLocker 加密免除


Microsoft BitLocker 管理和监视（MBAM）使你能够从 BitLocker 驱动器加密要求中免除用户。

若要从 BitLocker 保护中免除用户，您必须：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">任务</th>
<th align="left">详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>创建支持被免除的用户的基础结构。</p></td>
<td align="left"><p>此基础结构的示例包括向用户提供可用于请求豁免的联系人电话号码、网页或邮件地址。</p></td>
</tr>
<tr class="even">
<td align="left"><p>将被免除的用户添加到为被免除的用户专门配置的组策略对象的安全组。</p></td>
<td align="left"><p>当此安全组的成员登录到计算机时，用户的组策略设置从 BitLocker 保护 exempts 用户。 用户的组策略设置将覆盖计算机策略，并且计算机将保持不受 BitLocker 加密的阻止。</p>
<div class="alert">
<strong>注意</strong><br/><p>如果计算机已受 BitLocker 保护且用户已被免除，MBAM 不会制定加密策略。 但是，如果其他不是加密策略的用户登录到计算机，则会进行加密。</p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



以下步骤介绍最终用户通过 MBAM 客户端或通过组织使用的任何进程请求来自 BitLocker 驱动器加密豁免进程的豁免时发生的情况。 必须将 MBAM 组策略设置配置为允许最终用户从 BitLocker 驱动器加密中请求豁免。

1.  当最终用户登录到需要加密的计算机时，他们将收到一则通知，告知其计算机将被加密。 他们可以通过选择 "**推迟**" 来选择 "**请求豁免**" 并推迟加密，或者可以选择 "**开始加密**" 以接受 BitLocker 加密。

    **注意**  
    选择 "**请求免除**" 将推迟 BitLocker 保护，直到用户豁免策略中设置的最长时间。



2.  如果最终用户选择 "**请求豁免**"，则会收到通知，告知他们联系组织的 BitLocker 管理组。 根据配置**用户豁免策略**的配置方式，向用户提供以下一种或多种联系方法：

    -   电话号码

    -   网页 URL

    -   通讯地址

3.  收到免除请求后，MBAM 管理员决定是否将用户添加到 BitLocker 豁免 Active Directory 域服务（AD DS）组。

4.  最终用户提交免除请求后，MBAM 客户端会将该用户报告为 "临时豁免"。 然后，客户端将等待指定的天数（IT 管理员配置的天数），然后再次检查计算机的合规性。 如果 MBAM 管理员拒绝免除请求，将停用 "免除请求" 选项，这将阻止用户再次请求例外。

Microsoft BitLocker 管理和监视（MBAM）使你能够从 BitLocker 驱动器加密要求中免除用户。

若要从 BitLocker 保护中免除用户，您必须：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">任务</th>
<th align="left">详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>创建支持被免除的用户的基础结构。</p></td>
<td align="left"><p>此基础结构的示例包括向用户提供可用于请求豁免的联系人电话号码、网页或邮件地址。</p></td>
</tr>
<tr class="even">
<td align="left"><p>将被免除的用户添加到为被免除的用户专门配置的组策略对象的安全组。</p></td>
<td align="left"><p>当此安全组的成员登录到计算机时，用户的组策略设置从 BitLocker 保护 exempts 用户。 用户的组策略设置将覆盖计算机策略，并且计算机将保持不受 BitLocker 加密的阻止。</p>
<div class="alert">
<strong>注意</strong><br/><p>如果计算机已受 BitLocker 保护，则用户豁免策略不起作用。 此外，如果其他用户登录的计算机不是加密策略的例外，将进行加密。</p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



以下步骤介绍最终用户通过 MBAM 客户端或通过组织使用的任何进程请求来自 BitLocker 驱动器加密豁免进程的豁免时发生的情况。 必须将 MBAM 组策略设置配置为允许最终用户从 BitLocker 驱动器加密中请求豁免。

1.  当最终用户登录到需要加密的计算机时，他们将收到一则通知，告知其计算机将被加密。 他们可以通过选择 "**推迟**" 来选择 "**请求豁免**" 并推迟加密，或者可以选择 "**开始加密**" 以接受 BitLocker 加密。

    **注意**  
    选择 "**请求免除**" 将推迟 BitLocker 保护，直到用户豁免策略中设置的最长时间。



2.  如果最终用户选择 "**请求豁免**"，则会收到通知，告知他们联系组织的 BitLocker 管理组。 根据配置**用户豁免策略**的配置方式，向用户提供以下一种或多种联系方法：

    -   电话号码

    -   网页 URL

    -   通讯地址

3.  收到免除请求后，MBAM 管理员决定是否将用户添加到 BitLocker 豁免 Active Directory 域服务（AD DS）组。

4.  最终用户提交免除请求后，MBAM 客户端会将该用户报告为 "临时豁免"。 然后，客户端将等待指定的天数（IT 管理员配置的天数），然后再次检查计算机的合规性。 如果 MBAM 管理员拒绝免除请求，将停用 "免除请求" 选项，这将阻止用户再次请求例外。

**从 BitLocker 驱动器加密中免除用户**

1.  创建将用于管理来自 BitLocker 加密要求的用户免除的 AD DS 安全组。

2.  使用 Microsoft BitLocker 管理和监视组策略模板创建组策略对象。

3.  将组策略对象与您在上一步中创建的 AD DS 组相关联。 豁免用户的策略设置位于： **UserConfiguration** &gt; **管理模板** &gt; **Windows 组件** &gt; **MDOP MBAM （BitLocker Management）**。

4.  对于为 BitLocker 免除的用户创建的安全组，请添加请求豁免的用户的姓名。

    当用户登录由 BitLocker 控制的计算机时，MBAM 客户端会检查用户豁免策略设置。 如果计算机已加密，则不会暂停 BitLocker 保护。 如果计算机未加密，则 MBAM 不会提示用户进行加密。

    **重要提示**  
    使用 BitLocker 用户例外时，共享计算机方案需要特殊考虑。 如果非豁免用户登录与豁免用户共享的计算机，则该计算机可能已加密。




## 相关主题


[管理 MBAM 2.5 功能](administering-mbam-25-features.md)

[规划 MBAM 2.5 组策略要求](planning-for-mbam-25-group-policy-requirements.md)




## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。




