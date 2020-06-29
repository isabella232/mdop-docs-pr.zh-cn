---
title: 客户端事件日志
description: 客户端事件日志
author: dansimp
ms.assetid: d5c2f270-db6a-45f1-8557-8c6fb28fd568
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7324d07bf018944fcbe24168bba2e9abea9cea41
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803519"
---
# 客户端事件日志

MBAM 客户端事件日志位于事件查看器-应用程序和服务日志中-Windows-MBAM-操作路径。
下表包含 MBAM 客户端上可能出现的事件 Id。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">事件 ID</th>
<th align="left">频道</th>
<th align="left">活动符号</th>
<th align="left">消息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>raid-1</p></td>
<td align="left"><p>性</p></td>
<td align="left"><p>VolumeEnactmentSuccessful</p></td>
<td align="left"><p>已成功应用 MBAM 策略。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ppls-2</p></td>
<td align="left"><p>管理员</p></td>
<td align="left"><p>VolumeEnactmentFailed</p></td>
<td align="left"><p>应用 MBAM 策略时出错。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>三维空间</p></td>
<td align="left"><p>性</p></td>
<td align="left"><p>TransferStatusDataSuccessful</p></td>
<td align="left"><p>已成功发送加密状态数据。</p></td>
</tr>
<tr class="even">
<td align="left"><p>第</p></td>
<td align="left"><p>管理员</p></td>
<td align="left"><p>TransferStatusDataFailed</p></td>
<td align="left"><p>发送加密状态数据时出错。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>个</p></td>
<td align="left"><p>管理员</p></td>
<td align="left"><p>SystemVolumeNotFound</p></td>
<td align="left"><p>缺少系统卷。 加密操作系统驱动器需要 SystemVolume。</p></td>
</tr>
<tr class="even">
<td align="left"><p>db-9</p></td>
<td align="left"><p>管理员</p></td>
<td align="left"><p>TPMNotFound</p></td>
<td align="left"><p>缺少 TPM 硬件。 需要 TPM 以通过任何 TPM 保护程序对操作系统驱动器进行加密。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>10</p></td>
<td align="left"><p>管理员</p></td>
<td align="left"><p>MachineHWExempted</p></td>
<td align="left"><p>计算机被免除加密。 计算机的硬件状态：已免除</p></td>
</tr>
<tr class="even">
<td align="left"><p>11</p></td>
<td align="left"><p>管理员</p></td>
<td align="left"><p>MachineHWUnknown</p></td>
<td align="left"><p>计算机被免除加密。 计算机的硬件状态：未知</p></td>
</tr>
<tr class="odd">
<td align="left"><p>至</p></td>
<td align="left"><p>管理员</p></td>
<td align="left"><p>HWCheckFailed</p></td>
<td align="left"><p>硬件豁免检查失败。</p></td>
</tr>
<tr class="even">
<td align="left"><p>13</p></td>
<td align="left"><p>管理员</p></td>
<td align="left"><p>UserIsExempted</p></td>
<td align="left"><p>用户豁免加密。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>14</p></td>
<td align="left"><p>管理员</p></td>
<td align="left"><p>UserIsWaiting</p></td>
<td align="left"><p>用户请求了豁免。</p></td>
</tr>
<tr class="even">
<td align="left"><p>岁</p></td>
<td align="left"><p>管理员</p></td>
<td align="left"><p>UserExemptionCheckFailed</p></td>
<td align="left"><p>用户豁免检查失败。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>utf-16</p></td>
<td align="left"><p>管理员</p></td>
<td align="left"><p>UserPostponed</p></td>
<td align="left"><p>用户推迟了加密过程。</p></td>
</tr>
<tr class="even">
<td align="left"><p>17</p></td>
<td align="left"><p>管理员</p></td>
<td align="left"><p>TPMInitializationFailed</p></td>
<td align="left"><p>TPM 初始化失败。 用户拒绝了 BIOS 更改。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>18</p></td>
<td align="left"><p>管理员</p></td>
<td align="left"><p>CoreServiceDown</p></td>
<td align="left"><p>无法连接到 MBAM 恢复和硬件服务。</p></td>
</tr>
<tr class="even">
<td align="left"><p>19</p></td>
<td align="left"><p>性</p></td>
<td align="left"><p>CoreServiceUp</p></td>
<td align="left"><p>已成功连接到 MBAM 恢复和硬件服务。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>名</p></td>
<td align="left"><p>管理员</p></td>
<td align="left"><p>PolicyMismatch</p></td>
<td align="left"><p>MBAM 策略冲突或已损坏。</p></td>
</tr>
<tr class="even">
<td align="left"><p>21日</p></td>
<td align="left"><p>管理员</p></td>
<td align="left"><p>ConflictingOSVolumePolicies</p></td>
<td align="left"><p>检测到的操作系统卷加密策略冲突。 检查与操作系统驱动器保护器相关的 BitLocker 和 MBAM 策略。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>22</p></td>
<td align="left"><p>管理员</p></td>
<td align="left"><p>ConflictingFDDVolumePolicies</p></td>
<td align="left"><p>检测到固定数据驱动器卷加密策略冲突。 检查与 FDD 驱动器保护器相关的 BitLocker 和 MBAM 策略。</p></td>
</tr>
<tr class="even">
<td align="left"><p>7</p></td>
<td align="left"><p>管理员</p></td>
<td align="left"><p>EncryptionFailedNoDra</p></td>
<td align="left"><p>加密时出错。 在适用于 Windows 的 Windows 8.1 计算机的 FIPS 模式中，需要数据恢复代理（DRA）保护器。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>28</p></td>
<td align="left"><p>性</p></td>
<td align="left"><p>TpmOwnerAuthEscrowed</p></td>
<td align="left"><p>TPM OwnerAuth 已 escrowed。</p></td>
</tr>
<tr class="even">
<td align="left"><p>29</p></td>
<td align="left"><p>性</p></td>
<td align="left"><p>RecoveryKeyEscrowed</p></td>
<td align="left"><p>卷的 BitLocker 恢复密钥已 escrowed。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>大约</p></td>
<td align="left"><p>性</p></td>
<td align="left"><p>RecoveryKeyReset</p></td>
<td align="left"><p>卷的 BitLocker 恢复密钥已更新。</p></td>
</tr>
<tr class="even">
<td align="left"><p>之前</p></td>
<td align="left"><p>性</p></td>
<td align="left"><p>EnforcePolicyDateSet</p></td>
<td align="left"><p>已 <em> &lt; &gt; </em> 为卷设置强制策略日期、日期</p></td>
</tr>
<tr class="odd">
<td align="left"><p>32</p></td>
<td align="left"><p>性</p></td>
<td align="left"><p>EnforcePolicyDateCleared</p></td>
<td align="left"><p>已清除卷的强制策略日期、 <em> &lt; 日期 &gt; </em> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>33</p></td>
<td align="left"><p>性</p></td>
<td align="left"><p>TpmLockOutResetSucceeded</p></td>
<td align="left"><p>已成功重置 TPM 锁定。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>34</p></td>
<td align="left"><p>管理员</p></td>
<td align="left"><p>TpmLockOutResetFailed</p></td>
<td align="left"><p>无法重置 TPM 锁定。</p></td>
</tr>
<tr class="even">
<td align="left"><p>35</p></td>
<td align="left"><p>性</p></td>
<td align="left"><p>TpmOwnerAuthRetrievalSucceeded</p></td>
<td align="left"><p>已成功从 MBAM 服务中检索到 TPM OwnerAuth。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>36</p></td>
<td align="left"><p>管理员</p></td>
<td align="left"><p>TpmOwnerAuthRetrievalFailed</p></td>
<td align="left"><p>无法从 MBAM 服务检索 TPM OwnerAuth。</p></td>
</tr>
<tr class="even">
<td align="left"><p>37</p></td>
<td align="left"><p>管理员</p></td>
<td align="left"><p>WmiProviderDllSearchPathUpdateFailed</p></td>
<td align="left"><p>无法更新 WMI 提供程序的 DLL 搜索路径。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>38</p></td>
<td align="left"><p>管理员</p></td>
<td align="left"><p>TimedOutWaitingForWmiProvider</p></td>
<td align="left"><p>代理停止-等待 MBAM WMI 提供程序实例超时。</p></td>
</tr>
<tr class="even">
<td align="left"><p>39</p></td>
<td align="left"><p>性</p></td>
<td align="left"><p>RemovableDriveMounted</p></td>
<td align="left"><p>已装入可移动驱动器。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>40</p></td>
<td align="left"><p>性</p></td>
<td align="left"><p>RemovableDriveDismounted</p></td>
<td align="left"><p>可移动驱动器已卸载。</p></td>
</tr>
<tr class="even">
<td align="left"><p>41</p></td>
<td align="left"><p>性</p></td>
<td align="left"><p>FailedToEnactEndpointUnreachable</p></td>
<td align="left"><p>无法连接到 MBAM 恢复和硬件服务，无法成功将 MBAM 策略应用到卷。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>42</p></td>
<td align="left"><p>性</p></td>
<td align="left"><p>FailedToEnactLockedVolume</p></td>
<td align="left"><p>已锁定卷状态阻止将 MBAM 策略成功应用到卷。</p></td>
</tr>
<tr class="even">
<td align="left"><p>43</p></td>
<td align="left"><p>性</p></td>
<td align="left"><p>TransferStatusDataFailedEndpointUnreachable</p></td>
<td align="left"><p>无法连接到 MBAM 合规性和状态服务，无法传输加密状态数据。</p></td>
</tr>
</tbody>
</table>

 


## 相关主题
[MBAM 2.5 的技术参考](technical-reference-for-mbam-25.md)

[服务器事件日志](server-event-logs.md)

 


## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





