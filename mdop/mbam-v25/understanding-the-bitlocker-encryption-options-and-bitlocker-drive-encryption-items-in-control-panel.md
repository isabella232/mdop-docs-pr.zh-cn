---
title: 了解控制面板中的“BitLocker 加密选项”和“BitLocker 驱动器加密”项
description: 了解控制面板中的“BitLocker 加密选项”和“BitLocker 驱动器加密”项
author: dansimp
ms.assetid: f8a01cc2-0c77-48b9-8351-8194e80b0cf8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 739b65680ebfdf19f006ee8f3079f7c7e602f697
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798129"
---
# 了解控制面板中的“BitLocker 加密选项”和“BitLocker 驱动器加密”项


本主题介绍**Bitlocker 加密选项**和**bitlocker 驱动器加密**控制面板项目，并介绍以下内容：

-   如何创建这些项目

-   使你能够执行的任务

-   **管理 BitLocker**"右键单击" 快捷菜单（可见）和隐藏，以及如何将其设置为在默认情况下可见

## BitLocker 加密选项和 BitLocker 驱动器加密控制面板项目


下表列出了可以从每个 "控制面板" 项执行的任务，并介绍了如何创建这些项目。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left">BitLocker 加密选项（MBAM）</th>
<th align="left">BitLocker 驱动器加密（Windows）</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>可以执行的任务</p></td>
<td align="left"><ul>
<li><p>更改 PIN 或密码</p></li>
<li><p>检查驱动器的加密状态</p></li>
<li><p>打开 TPM 管理控制台</p></li>
<li><p>“启用 BitLocker”</p></li>
</ul></td>
<td align="left"><ul>
<li><p>暂停对驱动器的保护</p></li>
<li><p>备份恢复密钥</p></li>
<li><p>更改 PIN</p></li>
<li><p>关闭驱动器的 BitLocker</p></li>
<li><p>为驱动器启用 BitLocker</p></li>
<li><p>打开 TPM 管理控制台</p></li>
<li><p>解密驱动器（仅当未安装 MBAM 客户端时才出现）</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>如何创建 "控制面板" 项目</p></td>
<td align="left"><p>在安装 MBAM 客户端时在 "控制面板" 中创建。 无法隐藏此项目。</p>
<div class="alert">
<strong>注意</strong><br/><p>除了默认的 BitLocker 驱动器加密控制面板项目之外，此项还将出现在默认的 BitLocker 驱动器加密控制面板项目中。</p>
</div>
<div>

</div></td>
<td align="left"><p>在 "控制面板" 中默认显示为 Windows 操作系统的一部分，但您可以将其隐藏。</p>
<p>若要隐藏它，请参阅 <a href="hiding-the-default-bitlocker-drive-encryption-item-in-control-panel-mbam-25.md" data-raw-source="[Hiding the Default BitLocker Drive Encryption Item in Control Panel](hiding-the-default-bitlocker-drive-encryption-item-in-control-panel-mbam-25.md)"> 在 "控制面板" 中隐藏默认的 BitLocker 驱动器加密项目 </a> 。</p></td>
</tr>
</tbody>
</table>



## <a href="" id="-manage-bitlocker--shortcut-menu"></a>"管理 BitLocker" 快捷菜单


下表介绍了 "**管理 BitLocker** " 快捷菜单的不同，具体取决于是否安装了 MBAM 客户端。 术语 "快捷菜单" 指在 Windows 资源管理器中右键单击驱动器时显示的选项。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left">安装 MBAM 客户端时</th>
<th align="left">未安装 MBAM 客户端时</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>快捷菜单的可见性</p></td>
<td align="left"><p>"管理 BitLocker" 选项处于隐藏状态。</p>
<p>若要使 "管理 BitLocker" 选项显示在快捷菜单上，其中显示了用于解密驱动器的选项，请删除以下注册表项：</p>
<pre class="syntax" space="preserve"><code>HKEY_CLASSES_ROOT\Drive\Shell\manage-bde \REG_SZ LegacyDisable</code></pre></td>
<td align="left"><p>"管理 BitLocker" 选项显示在快捷菜单上。</p></td>
</tr>
<tr class="even">
<td align="left"><p>用户可以执行的操作</p></td>
<td align="left"><p>隐藏快捷方式后，用户可以打开 "BitLocker 驱动器加密控制面板" 项目，但用于解密驱动器的选项不可用。</p></td>
<td align="left"><p>在快捷方式可见的情况下，选择 " <strong> 管理 BitLocker" </strong> 选项将打开 "Bitlocker 驱动器加密控制面板" 项目，其中显示了用于解密驱动器的选项。</p></td>
</tr>
</tbody>
</table>




## 相关主题


[管理 MBAM 2.5 功能](administering-mbam-25-features.md)



## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





