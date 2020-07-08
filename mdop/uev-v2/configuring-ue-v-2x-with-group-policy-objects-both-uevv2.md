---
title: 通过组策略对象配置 UE-V 2. x
description: 通过组策略对象配置 UE-V 2. x
author: dansimp
ms.assetid: 2bb55834-26ee-4f19-9860-dfdf3c797143
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: bdff63b948752b9bec83e77e275f1cb20a384463
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803565"
---
# 通过组策略对象配置 UE-V 2. x


某些 Microsoft 用户体验虚拟化（UE-V）2.0、2.1 和 2.1 SP1 组策略设置可为计算机定义，并且可以为用户定义其他组策略设置。 有关如何安装 UE-V 组策略 ADMX 文件的信息，请参阅[安装 ue-v 2 组策略 Admx 模板](https://technet.microsoft.com/library/dn458891.aspx#admx)。

可以为 UE-V 配置以下策略设置。

**组策略设置**

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">组策略设置名称</th>
<th align="left">目标</th>
<th align="left">组策略设置说明</th>
<th align="left">配置选项</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>联系 IT 链接文本</p></td>
<td align="left"><p>仅限计算机</p></td>
<td align="left"><p>此组策略设置在 "公司设置中心" 中指定 "联系 IT URL" 超链接的文本。</p></td>
<td align="left"><p>如果启用此组策略设置，公司设置中心将在指向联系人 IT URL 的链接中显示指定文本。</p></td>
</tr>
<tr class="even">
<td align="left"><p>联系 IT URL</p></td>
<td align="left"><p>仅限计算机</p></td>
<td align="left"><p>此组策略设置在 "公司设置中心" 中指定 "联系人 IT" 链接的 URL。</p></td>
<td align="left"><p>如果启用此设置，公司设置中心将联系 IT 文本链接到指定的 URL。 该链接可以是任何标准协议，如 HTTP 或 mailto。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>不使用同步提供程序</p></td>
<td align="left"><p>计算机和用户</p></td>
<td align="left"><p>通过使用此组策略设置，你可以配置 UE-V 是否使用同步提供程序功能。 此策略设置还允许你启用在延迟导入用户设置时显示通知。</p></td>
<td align="left"><p>启用此设置以将 UE-V Agent 配置为不使用同步提供程序。</p></td>
</tr>
<tr class="even">
<td align="left"><p>首次使用通知</p></td>
<td align="left"><p>仅限计算机</p></td>
<td align="left"><p>此组策略设置启用在 UE-V 的通知区域中出现的通知</p>
<p>代理首次运行。</p></td>
<td align="left"><p>默认值为 "已启用"。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>漫游 Windows 设置</p></td>
<td align="left"><p>计算机和用户</p></td>
<td align="left"><p>此组策略设置配置 Windows 设置的同步。</p></td>
<td align="left"><p>选择要在计算机之间同步的 Windows 设置。</p>
<p>默认情况下，Windows 主题、桌面设置和轻松访问设置在同一操作系统版本的计算机之间同步设置。</p></td>
</tr>
<tr class="even">
<td align="left"><p>设置程序包大小警告阈值</p></td>
<td align="left"><p>计算机和用户</p></td>
<td align="left"><p>此组策略设置允许你配置 UE-V Agent，以在设置包文件大小达到定义的阈值时进行报告。</p></td>
<td align="left"><p>指定设置包大小的首选阈值（KB）。</p>
<p>默认情况下，UE-V Agent 没有程序包文件大小阈值。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>设置存储路径</p></td>
<td align="left"><p>计算机和用户</p></td>
<td align="left"><p>此组策略设置配置要存储用户设置的位置。</p></td>
<td align="left"><p>输入通用命名约定（UNC）路径和变量（如 \Server\SettingsShare%username%.）</p></td>
</tr>
<tr class="even">
<td align="left"><p>设置模板目录路径</p></td>
<td align="left"><p>仅限计算机</p></td>
<td align="left"><p>此组策略设置配置自定义设置位置模板的存储位置。 此策略设置还配置目录是否用于替换随 UE-V Agent 一起安装的默认 Microsoft 模板。</p></td>
<td align="left"><p>在计算机上输入通用命名约定（UNC）路径，如 \Server\TemplateShare 或文件夹位置。</p>
<p>选中复选框以替换默认的 Microsoft 模板。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>通过按流量计费的连接同步设置</p></td>
<td align="left"><p>计算机和用户</p></td>
<td align="left"><p>此组策略设置定义 UE-V 是否通过按流量计费的连接同步设置。</p></td>
<td align="left"><p>默认情况下，UE-V Agent 不会通过按流量计费的连接同步设置。</p></td>
</tr>
<tr class="even">
<td align="left"><p>即使在漫游时也通过按流量计费的连接同步设置</p></td>
<td align="left"><p>计算机和用户</p></td>
<td align="left"><p>此组策略设置定义了 UE-V 是否通过主提供商网络之外的按流量计费的连接（例如，当数据连接处于漫游模式时）同步设置。</p></td>
<td align="left"><p>默认情况下，UE-V 在漫游模式下不会通过按流量计费的连接同步设置。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>同步超时</p></td>
<td align="left"><p>计算机和用户</p></td>
<td align="left"><p>此组策略设置配置在从远程设置位置检索用户设置时，计算机在超时之前等待的毫秒数。 如果 "远程存储" 位置不可用，并且用户不使用同步提供程序，则应用程序启动将延迟数毫秒。</p></td>
<td align="left"><p>指定首选同步超时时间（以毫秒为单位）。 默认值为2000毫秒。</p></td>
</tr>
<tr class="even">
<td align="left"><p>托盘图标</p></td>
<td align="left"><p>仅限计算机</p></td>
<td align="left"><p>此组策略设置启用用户体验虚拟化（UE-V）托盘图标。</p></td>
<td align="left"><p>默认值为 "已启用"。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>使用用户体验虚拟化（UE-V）</p></td>
<td align="left"><p>计算机和用户</p></td>
<td align="left"><p>此组策略设置允许你启用或禁用用户体验虚拟化（UE-V）。</p></td>
<td align="left"><p>启用或禁用此组策略设置。</p></td>
</tr>
</tbody>
</table>

 

**注意** 此外，许多桌面应用程序和 Windows 应用均可使用组策略设置。 你可以使用这些设置启用或禁用特定应用程序的设置同步。

 

**Windows 应用组策略设置**

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">组策略设置名称</th>
<th align="left">目标</th>
<th align="left">组策略设置说明</th>
<th align="left">配置选项</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>不同步 Windows 应用</p></td>
<td align="left"><p>计算机和用户</p></td>
<td align="left"><p>此组策略设置定义 UE-V Agent 是否同步 Windows 应用的设置。</p></td>
<td align="left"><p>默认为同步 Windows 应用。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 应用列表</p></td>
<td align="left"><p>计算机和用户</p></td>
<td align="left"><p>此设置列出 Windows 应用的系列程序包名称，并明确表明 UE-V 是否同步了该应用的设置。</p></td>
<td align="left"><p>你可以使用此设置指定应用的设置永远不会通过 UE-V 同步，即使所有其他 Windows 应用的设置都已同步。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>同步未列出的 Windows 应用</p></td>
<td align="left"><p>计算机和用户</p></td>
<td align="left"><p>此组策略设置定义未在 Windows 应用列表中显式列出的 Windows 应用的 UE-V Agent 的默认设置同步行为。</p></td>
<td align="left"><p>默认情况下，UE-V Agent 仅同步 Windows 应用列表中包含的那些 Windows 应用的设置。</p></td>
</tr>
</tbody>
</table>

 

有关同步 Windows 应用的详细信息，请参阅[Windows 应用列表](https://technet.microsoft.com/library/dn458925.aspx#win8applist)。

**配置以计算机为目标的组策略设置**

1.  在充当域控制器的计算机上使用组策略管理控制台（GPMC）或高级组策略管理（AGPM），以管理 UE-V 计算机的组策略设置。 导航到 "**计算机配置**"，选择 "**策略**"，选择 "**管理模板**"，单击 " **Windows 组件**"，然后选择 " **Microsoft 用户体验虚拟化**"。

2.  选择要编辑的组策略设置。

**配置用户定向的组策略设置**

1.  在域控制器计算机上的 Microsoft 桌面优化包（MDOP）中使用组策略管理控制台（GPMC）或高级组策略管理（AGPM）工具管理 UE-V 的组策略设置。 导航到 "**用户配置**"，选择 "**策略**"，选择 "**管理模板**"，单击 " **Windows 组件**"，然后选择 " **Microsoft 用户体验虚拟化**"。

2.  选择 "已编辑的组策略" 设置。

UE-V Agent 使用以下优先级顺序确定同步。

**UE-V 设置的优先级顺序**

1.  由组策略设置管理的由用户设定的设置-这些配置设置由 "组策略" 下的 "组策略" 存储在注册表项中 `HKEY_CURRENT_USER\Software\Policies\Microsoft\Uev\Agent\Configuration` 。

2.  由组策略设置管理的由计算机设定的设置-这些配置设置由 "组策略" 下的 "组策略" 存储在注册表项中 `HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Uev\Agent\Configuration` 。

3.  由当前用户使用 Windows PowerShell 或 Windows 管理规范（WMI）定义的配置设置，这些配置设置由 UE-V Agent 在此注册表位置下存储： `HKEY_CURRENT_USER\Software\Microsoft\Uev\Agent\Configuration` 。

4.  使用 Windows PowerShell 或 WMI 为计算机定义的配置设置。 这些配置设置由 UE-V Agent 在此注册表位置下存储： `HKEY_LOCAL_MACHINE\Software\Microsoft\Uev\Agent\Configuration` 。

    已**获得有关 ue-v 的建议**？ 在[此处](http://uev.uservoice.com/forums/280428-microsoft-user-experience-virtualization)添加或投票建议。 是否**遇到了 ue-v 问题**？ 使用[Ue-v TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopuev)。

## 相关主题


[管理 UE-V 2. x](administering-ue-v-2x-new-uevv2.md)

[管理 UE-V 2.x 的配置](manage-configurations-for-ue-v-2x-new-uevv2.md)

 

 





