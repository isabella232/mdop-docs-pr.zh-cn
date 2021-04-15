---
title: 使用组策略对象配置 UE-V 2.x
description: 使用组策略对象配置 UE-V 2.x
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
ms.openlocfilehash: b6c9636df36a53cbf65bf1904965f2809484b99c
ms.sourcegitcommit: bdc377477a8cc9e973fbcdd67c2f07b882c5d61e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "11494057"
---
# <a name="configuring-ue-v-2x-with-group-policy-objects"></a>使用组策略对象配置 UE-V 2.x


某些 Microsoft 用户体验虚拟化 (UE-V) 2.0、2.1 和 2.1 SP1 组策略设置可以定义用于计算机，也可以为用户定义其他组策略设置。 若要了解如何安装 UE-V 组策略 ADMX 文件，请参阅安装 [UE-V 2 组策略 ADMX 模板](https://technet.microsoft.com/library/dn458891.aspx#admx)。

可以针对 UE-V 配置以下策略设置。

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
<td align="left"><p>配置 Sync 方法</p></td>
<td align="left"><p>计算机和用户</p></td>
<td align="left"><p>通过使用此组策略设置，您可以配置用户体验虚拟化 (UE-V) 是否使用同步提供程序功能。 此策略设置还允许您在用户设置导入延迟时显示通知。</p></td>
<td align="left"><p>启用此设置可配置 UE-V 代理不使用同步提供程序或使用外部同步引擎。</p></td>
</tr>
<tr class="even">
<td align="left"><p>联系 IT 链接文本</p></td>
<td align="left"><p>仅计算机</p></td>
<td align="left"><p>此组策略设置指定公司设置中心中"联系人 IT URL"超链接的文本。</p></td>
<td align="left"><p>如果启用此组策略设置，公司设置中心将在指向"联系人 IT URL"的链接中显示指定的文本。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>联系 IT URL</p></td>
<td align="left"><p>仅计算机</p></td>
<td align="left"><p>此组策略设置指定公司设置中心中"联系人 IT"链接的 URL。</p></td>
<td align="left"><p>如果启用此设置，公司设置中心"联系 IT 人员"文本将链接到指定的 URL。 该链接可以是任何标准协议，如 HTTP 或 mailto。</p></td>
</tr>
<tr class="even">
<td align="left"><p>首次使用通知</p></td>
<td align="left"><p>仅计算机</p></td>
<td align="left"><p>此组策略设置启用当 UE-V 时在通知区域中显示的通知</p>
<p>代理首次运行。</p></td>
<td align="left"><p>默认值为启用。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>同步前 Ping 设置存储位置</p></td>
<td align="left"><p>计算机和用户</p></td>
<td align="left"><p>此策略设置允许配置 UE-V 同步提供程序在尝试同步设置之前 ping 设置存储路径，以便验证连接。</p></td>
<td align="left"><p>启用或禁用此组策略设置。</p></td>
</tr>
<tr class="even">
<td align="left"><p>设置程序包大小警告阈值</p></td>
<td align="left"><p>计算机和用户</p></td>
<td align="left"><p>通过此组策略设置，可以将 UE-V 代理配置为在设置包文件大小达到定义的阈值时报告。</p></td>
<td align="left"><p>指定设置包大小的首选阈值（以 KB (KB) ）。</p>
<p>默认情况下，UE-V 代理没有程序包文件大小阈值。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>设置存储路径</p></td>
<td align="left"><p>计算机和用户</p></td>
<td align="left"><p>此组策略设置配置存储用户设置的位置。</p></td>
<td align="left"><p>在 UNC 路径和变量（如 \Server\SettingsShare%username%） () UNC (通用命名约定。</p></td>
</tr>
<tr class="even">
<td align="left"><p>设置模板目录路径</p></td>
<td align="left"><p>仅计算机</p></td>
<td align="left"><p>此组策略设置配置存储自定义设置位置模板的位置。 此策略设置还配置目录是否用于替换随 UE-V 代理一起安装的默认 Microsoft 模板。</p></td>
<td align="left"><p>输入 UNC (通用命名) 路径，如 \Server\TemplateShare 或计算机上文件夹位置。</p>
<p>选中此复选框以替换默认的 Microsoft 模板。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>通过按流量计费的连接同步设置</p></td>
<td align="left"><p>计算机和用户</p></td>
<td align="left"><p>此组策略设置定义 UE-V 是否通过按流量计费的连接同步设置。</p></td>
<td align="left"><p>默认情况下，UE-V 代理不会通过按流量计费的连接同步设置。</p></td>
</tr>
<tr class="even">
<td align="left"><p>即使漫游时，也通过按流量计费的连接同步设置</p></td>
<td align="left"><p>计算机和用户</p></td>
<td align="left"><p>此组策略设置定义 UE-V 是否通过主提供商网络外部的按流量计费的连接同步设置，例如，当数据连接在漫游模式下时。</p></td>
<td align="left"><p>默认情况下，当 UE-V 在漫游模式下时，它不会通过按流量计费的连接同步设置。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>同步超时</p></td>
<td align="left"><p>计算机和用户</p></td>
<td align="left"><p>此组策略设置配置计算机从远程设置位置检索用户设置时在退出之前等待的毫秒数。 如果远程存储位置不可用，并且用户不使用同步提供程序，则应用程序启动将延迟多毫秒。</p></td>
<td align="left"><p>指定首选同步的退出时间（以毫秒为单位）。 默认值为 2000 毫秒。</p></td>
</tr>
<tr class="even">
<td align="left"><p>同步 Windows 设置 </p></td>
<td align="left"><p>计算机和用户</p></td>
<td align="left"><p>此组策略设置配置 Windows 设置的同步。</p></td>
<td align="left"><p>选择在计算机之间同步的 Windows 设置。</p>
<p>默认情况下，Windows 主题、桌面设置和轻松使用设置在相同操作系统版本的计算机之间同步设置。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>任务栏图标</p></td>
<td align="left"><p>仅计算机</p></td>
<td align="left"><p>此组策略设置启用 UE-V 任务栏图标。</p></td>
<td align="left"><p>默认值为启用。</p></td>
</tr>
<tr class="even">
<td align="left"><p>使用用户体验虚拟化 (UE-V) </p></td>
<td align="left"><p>计算机和用户</p></td>
<td align="left"><p>此组策略设置允许你启用或禁用 UE-V。</p></td>
<td align="left"><p>启用或禁用此组策略设置。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>VDI 配置</p></td>
<td align="left"><p>计算机和用户</p></td>
<td align="left"><p>此策略设置为在池 VDI 环境中运行的计算机配置 UE-V 回滚信息的同步。 如果启用此策略，则 UE-V 回滚状态在注销时复制到设置存储位置，在登录时还原。</p></td>
<td align="left"><p>启用或禁用此组策略设置。</p></td>
</tr>
</tbody>
</table>

 

**注意**  
此外，组策略设置可用于许多桌面应用程序和 Windows 应用。 可以使用这些设置为特定应用程序启用或禁用设置同步。

 

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
<td align="left"><p>此组策略设置定义 UE-V 代理是否同步 Windows 应用的设置。</p></td>
<td align="left"><p>默认设置是同步 Windows 应用。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 应用列表</p></td>
<td align="left"><p>计算机和用户</p></td>
<td align="left"><p>此设置列出 Windows 应用的系列程序包名称，并明确指出 UE-V 是否同步该应用的设置。</p></td>
<td align="left"><p>可以使用此设置指定 UE-V 从不同步应用的设置，即使所有其他 Windows 应用的设置已同步。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>同步未列出的 Windows 应用</p></td>
<td align="left"><p>计算机和用户</p></td>
<td align="left"><p>此组策略设置定义未在 Windows 应用列表中显式列出的 Windows 应用的 UE-V 代理的默认设置同步行为。</p></td>
<td align="left"><p>默认情况下，UE-V 代理仅同步 Windows 应用列表中包含的这些 Windows 应用的设置。</p></td>
</tr>
</tbody>
</table>

 

有关同步 Windows 应用详细信息，请参阅 Windows [应用列表](https://technet.microsoft.com/library/dn458925.aspx#win8applist)。

**配置面向计算机的组策略设置**

1.  在充当域控制器的计算机上使用组策略管理控制台 (GPMC) 或高级组策略管理 (AGPM) 来管理 UE-V 计算机的组策略设置。 导航到 **"计算机配置"，** 选择"**策略****"，选择"管理模板"，** 单击 **"Windows**组件"，然后选择 **"Microsoft 用户体验虚拟化"。**

2.  选择要编辑的组策略设置。

**配置面向用户的组策略设置**

1.  使用域控制器计算机上 Microsoft 桌面优化包 (MDOP) 中的组策略管理控制台 (GPMC) 或高级组策略管理 (AGPM) 工具管理 UE-V 的组策略设置。 导航到 **"用户配置"，** 选择"**策略**"，选择"**管理模板"，** 单击 **"Windows**组件"，然后选择 **"Microsoft 用户体验虚拟化"。**

2.  选择已编辑的组策略设置。

UE-V 代理按以下优先顺序确定同步。

**UE-V 设置的优先级顺序**

1.  由组策略设置管理的用户目标设置 - 这些配置设置由 下的组策略存储在注册表项中 `HKEY_CURRENT_USER\Software\Policies\Microsoft\Uev\Agent\Configuration` 。

2.  由组策略设置管理的计算机目标设置 - 这些配置设置由 下的组策略存储在注册表项中 `HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Uev\Agent\Configuration` 。

3.  当前用户使用 Windows PowerShell 或 Windows management Instrumentation (WMI) 定义的配置设置 - 这些配置设置由 UE-V 代理存储在此注册表位置下 `HKEY_CURRENT_USER\Software\Microsoft\Uev\Agent\Configuration` ：。

4.  通过使用或 WMI 为计算机定义的Windows PowerShell设置。 这些配置设置由 UE-V 代理存储在此注册表位置下 `HKEY_LOCAL_MACHINE\Software\Microsoft\Uev\Agent\Configuration` ：。

    **收到有关 UE-V 的建议**？ 在此处添加建议或对建议 [投票](http://uev.uservoice.com/forums/280428-microsoft-user-experience-virtualization)。 **有 UE-V 问题**？ 使用 [UE-V TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopuev)。

## <a name="related-topics"></a>相关主题


[管理 UE-V 2.x](administering-ue-v-2x-new-uevv2.md)

[管理 UE-V 2.x 的配置](manage-configurations-for-ue-v-2x-new-uevv2.md)

 

 
