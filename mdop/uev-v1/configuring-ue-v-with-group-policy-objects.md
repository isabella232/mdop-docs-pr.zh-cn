---
title: 使用组策略对象配置 UE-V
description: 使用组策略对象配置 UE-V
author: dansimp
ms.assetid: 5c9be706-a05f-4397-9a38-e6b73ebff1e5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7e479e6bef1a2b38cf822ffca19ed4220b0c59fe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804020"
---
# 使用组策略对象配置 UE-V


某些 Microsoft 用户体验虚拟化（UE-V）组策略设置可为计算机定义，而其他用户可以为用户定义。 可以为计算机或用户定义 UE-V agent 配置策略设置。 有关如何安装 UE-V 组策略 ADMX 文件的信息，请参阅[安装 Ue-v 组策略 Admx 模板](installing-the-ue-v-group-policy-admx-templates.md)。

可为 UE-V 配置以下策略设置：

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>策略设置名称</strong></p></td>
<td align="left"><p><strong>目标</strong></p></td>
<td align="left"><p><strong>策略设置说明</strong></p></td>
<td align="left"><p><strong>配置选项</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>使用用户体验虚拟化（UE-V）</p></td>
<td align="left"><p>计算机和用户</p></td>
<td align="left"><p>通过此策略设置，你可以启用或禁用用户体验虚拟化（UE-V）。</p></td>
<td align="left"><p>启用或禁用此策略设置。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>设置存储路径</p></td>
<td align="left"><p>计算机和用户</p></td>
<td align="left"><p>此策略设置配置将存储用户设置的位置。</p></td>
<td align="left"><p>提供通用命名约定（UNC）路径和变量（如 \Server\SettingsShare%username%.）</p></td>
</tr>
<tr class="even">
<td align="left"><p>设置模板目录路径</p></td>
<td align="left"><p>仅限计算机</p></td>
<td align="left"><p>此策略设置配置自定义设置位置模板的存储位置。 此策略设置还配置目录是否将用于替换随 UE-V agent 一起安装的默认 Microsoft 模板。</p></td>
<td align="left"><p>在计算机上提供通用命名约定（UNC）路径，如 \Server\TemplateShare 或文件夹位置。</p>
<p></p>
<p>选中复选框以替换默认的 Microsoft 模板。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>不使用脱机文件</p></td>
<td align="left"><p>计算机和用户</p></td>
<td align="left"><p>通过此策略设置，你可以配置 UE-V 是否将使用 Windows 脱机文件功能。 此策略设置还允许你启用在用户设置的导入延迟时出现的通知。</p></td>
<td align="left"><p>若要将 UE-V Agent 配置为不使用脱机文件，请启用此设置。</p>
<p></p>
<p>指定在设置导入延迟时是否应提供通知。</p>
<p></p>
<p>指定在通知出现之前等待的时间长度（以秒为单位）。</p></td>
</tr>
<tr class="even">
<td align="left"><p>同步超时</p></td>
<td align="left"><p>计算机和用户</p></td>
<td align="left"><p>此策略设置配置从远程设置位置检索用户设置时，计算机超时之前等待的毫秒数。 如果 "远程存储" 位置不可用，则应用程序启动将延迟此毫秒。</p></td>
<td align="left"><p>指定首选同步超时值（以毫秒为单位）。 2000毫秒的默认值。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>程序包大小警告阈值</p></td>
<td align="left"><p>计算机和用户</p></td>
<td align="left"><p>通过此策略设置，你可以配置 UE-V agent，以便在设置包文件大小达到定义的阈值时进行报告。</p></td>
<td align="left"><p>指定设置包大小的首选阈值（以 kb 为单位）。</p>
<p>默认情况下，UE-V agent 没有程序包文件大小阈值。</p></td>
</tr>
<tr class="even">
<td align="left"><p>漫游应用程序设置</p></td>
<td align="left"><p>仅限用户</p></td>
<td align="left"><p>此策略设置配置应用程序的用户设置的漫游。</p></td>
<td align="left"><p>选择将在计算机之间漫游的 Windows 设置。</p>
<p>默认情况下，由 UE-V 提供的具有设置模板的应用程序的用户设置是在计算机之间漫游。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>漫游 Windows 设置</p></td>
<td align="left"><p>仅限用户</p></td>
<td align="left"><p>此策略设置配置 Windows 设置的漫游。</p></td>
<td align="left"><p>选择将在计算机之间漫游的应用程序。</p>
<p>默认情况下，Windows 主题是在同一操作系统版本的计算机之间漫游。 Windows 桌面设置和 "轻松访问" 设置不在漫游。</p></td>
</tr>
</tbody>
</table>

 

**配置以计算机为目标的策略**

1.  在管理 UE-V 计算机的组策略的域控制器计算机上使用组策略管理控制台（GPMC）或高级组策略管理（AGPM）。 导航到 "**计算机配置**"，选择 "**策略**"，选择 "**管理模板**"，单击 " **Windows 组件**"，然后选择 " **Microsoft 用户体验虚拟化**"。

2.  选择要编辑的策略设置。

**配置用户设定的策略**

1.  在管理 UE-V 的组策略的域控制器计算机上的 Microsoft 桌面优化包（MDOP）中使用组策略管理控制台（GPMC）或高级组策略管理（AGPM）工具。 导航到 "**用户配置**"，选择 "**策略**"，选择 "**管理模板**"，单击 " **Windows 组件**"，然后选择 " **Microsoft 用户体验虚拟化**"。

2.  选择已编辑的策略设置。

UE-V agent 使用以下优先级顺序确定同步。

**UE-V 设置的优先级顺序**

1.  由组策略管理的由用户设定的设置-这些配置设置由 "组策略" 下的 "组策略" 存储在注册表项中 `HKEY_CURRENT_USER\Software\Policies\Microsoft\Uev\Agent\Configuration` 。

2.  由组策略管理的由计算机设定的设置-这些配置设置由 "组策略" 下的 "组策略" 存储在注册表项中 `HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Uev\Agent\Configuration` 。

3.  当前用户使用 PowerShell 或 WMI 定义的配置设置-这些配置设置由 UE-V agent 在此注册表位置下存储： `HKEY_CURRENT_USER\Software\Microsoft\Uev\Agent\Configuration` 。

4.  使用 PowerShell 或 WMI 为计算机定义的配置设置。 这些配置设置由 UE-V agent 存储在 `HKEY_LOCAL_MACHINE \Software\Microsoft\Uev\Agent\Configuration` 。

## 相关主题


[管理 UE-V 1.0](administering-ue-v-10.md)

[UE-V 1.0 的操作](operations-for-ue-v-10.md)

 

 





