---
title: 管理 MED-V 工作区配置设置
description: 管理 MED-V 工作区配置设置
author: dansimp
ms.assetid: 517d04de-c31f-4b50-b2b3-5f8c312ed37b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 97add695f605b71547b564789cce07a1d58763f2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803912"
---
# 管理 MED-V 工作区配置设置


Microsoft 企业版桌面虚拟化（MED-V）2.0 将其配置设置存储在注册表中。 我们在此处介绍的有关注册表的信息可以帮助你更好地管理 MED-V 服务。

在查找结果设置值时，MED-V 使用以下搜索路径：

MED-V 首先在计算机策略中查找。

如果找不到该值，则 MED-V 将在用户策略中查找。

如果找不到该值，则 MED-V 将在 HKEY _LOCAL \ _MACHINE \\System 配置单元中查找。

如果找不到该值，则 MED-V 将在 HKEY \ _CURRENT 用户注册表配置单元中查找。

如果仍然找不到值，则 MED-V 使用默认值。

通常，最佳做法是在 HKEY _LOCAL \ _MACHINE \\System 配置单元或计算机策略中设置值。 但是，如果希望最终用户能够配置特定设置，则应将其保留。

**注意**  
在部署 MED-V 工作区之前，可以使用脚本编辑器更改 MED-V 工作区包装程序创建的 Windows PowerShell 脚本（ps1 文件）。 有关详细信息，请参阅[使用 Windows PowerShell 配置高级设置](configuring-advanced-settings-by-using-windows-powershell.md)。

部署 MED-V 工作区后，您可以通过编辑注册表项来更改某些 MED-V 配置设置。



本部分列出了所有可配置的 MED-V 注册表项并解释其用法。

## 诊断密钥


下表提供了与 HKEY _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\Medv\\v2\\Diagnostics 键相关联的注册表值的相关信息。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名称 </th>
<th align="left">类型 </th>
<th align="left">Data/Default </th>
<th align="left">描述 </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>EventLogLevel </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>默认值 = 3</p></td>
<td align="left"><p>事件日志中记录的信息类型。 级别包括以下内容：0（无）、1（错误）、2（警告）、3（信息）、4（调试）。</p></td>
</tr>
</tbody>
</table>



## Fts 键


下表提供了与 HKEY _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\Medv\\v2\\Fts 键相关联的注册表值的相关信息。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名称</th>
<th align="left">类型</th>
<th align="left">Data/Default</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>AddUserToAdminGroupEnabled </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 0</p></td>
<td align="left"><p>配置首次设置是否自动将最终用户添加到管理员&#39;s 组。 0 = false;1 = true。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>0 = false：首次设置不会自动将最终用户添加到管理员&#39;s 组。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>1 = true：首次设置会自动将最终用户添加到管理员&#39;s 组。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ComputerNameMask </p></td>
<td align="left"><p>SZ</p></td>
<td align="left"><p>MEDV* </p></td>
<td align="left"><p>用于创建来宾虚拟机&#39;计算机名的计算机名称掩码。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>掩码可以包含% username% 标签以插入用户名作为计算机名称的一部分。 同样，% hostname% 标签插入主计算机的名称。</p>
<p>&quot; # &quot; 掩码中的每个字符替换为随机数字。 掩码结尾处的星号（*）字符将替换为随机字母数字字符。</p>
<p>可以使用方括号捕获% hostname% 和% 用户名% 中的特定数量的字符。 例如， &quot; % 用户名% [3] &quot; 将使用用户名的前三个字符。</p></td>
</tr>
<tr class="even">
<td align="left"><p>DeleteVMStateTimeout</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 90</p></td>
<td align="left"><p>首次设置尝试删除虚拟机时的超时值（以秒为单位）。 范围 = 0 到2147483647。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>DetachVfdTimeout</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 120</p></td>
<td align="left"><p>第一次设置尝试从虚拟机分离虚拟软盘的超时值（以秒为单位）。 范围 = 0 到2147483647。</p></td>
</tr>
<tr class="even">
<td align="left"><p>DialogUrl </p></td>
<td align="left"><p>SZ</p></td>
<td align="left"><p></p></td>
<td align="left"><p>链接到内部网页且由首次设置对话框消息显示的可自定义 URL。 </p></td>
</tr>
<tr class="odd">
<td align="left"><p>ExplorerTimeout</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 900</p></td>
<td align="left"><p>首次设置等待 Windows 资源管理器时的超时值（以秒为单位）。 范围 = 0 到2147483647。</p></td>
</tr>
<tr class="even">
<td align="left"><p>FailureDialogMsg </p></td>
<td align="left"><p>MULTI_SZ</p></td>
<td align="left"><p>在资源文件中找到邮件 </p></td>
<td align="left"><p>首次设置无法完成时显示给最终用户的可自定义消息。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>GiveUserGroupRightsMaxRetryCount </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>默认值 = 3</p></td>
<td align="left"><p>MED-V 尝试授予最终用户组权限的最大次数。 超过指定的重试值，并且不能成功授予最终用户组权限后，最有可能会导致虚拟机的预准备失败，然后受 MaxRetryCount 值的制约。 范围 = 0 到2147483647。</p></td>
</tr>
<tr class="even">
<td align="left"><p>GiveUserGroupRightsTimeout </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 300</p></td>
<td align="left"><p>授予用户组权限的超时值（以秒为单位）。 范围 = 0 到2147483647。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>LogFilePaths </p></td>
<td align="left"><p>MULTI_SZ</p></td>
<td align="left"><p></p></td>
<td align="left"><p>第一次设置期间的 MED-V 收集的日志文件路径的列表。 </p></td>
</tr>
<tr class="even">
<td align="left"><p>MaxPostponeTime </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 120</p></td>
<td align="left"><p>最终用户第一次可以延迟的最大小时数。 范围 = 0 到2147483647。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MaxRetryCount </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 3</p></td>
<td align="left"><p>如果每次尝试在软件错误之外的故障中停止，则 MED-V 尝试准备虚拟机的最大次数。 当虚拟机准备失败并且超过了首次设置重试的次数时，MED-V 将通知最终用户该故障，并且不会提供重试选项。 每次启动 MED-V 时，都会重新设置计数。 范围 = 0 到2147483647。</p></td>
</tr>
<tr class="even">
<td align="left"><p>模式 </p></td>
<td align="left"><p>SZ</p></td>
<td align="left"><p>默认值 = 无人参与</p></td>
<td align="left"><p>配置首次设置与用户交互的方式。 可能的值如下所示：</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><strong>参加了.</strong> 最终用户在首次设置时必须输入信息。</p>
<div class="alert">
<strong>注意</strong><br/><p>如果你创建了 Sysprep.inf 文件，以便最小化安装需要用户输入才能完成，则你必须选择 " <strong> 有人参与 </strong> 模式" 或 "首次设置时可能出现问题"。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><strong>无人参与 </strong> 。 第一次设置期间，虚拟机不会向最终用户显示，但最终用户在首次启动设置之前会收到提示。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><strong>无声 </strong> 。 首次设置时，虚拟机不会显示给最终用户。</p></td>
</tr>
<tr class="even">
<td align="left"><p>NonInteractiveRetryTimeoutInc </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 15</p></td>
<td align="left"><p>第一次必须在重新尝试安装程序时首次完成设置的超时值（以分钟为单位）。 范围 = 0 到2147483647。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>NonInteractiveTimeout </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 45</p></td>
<td align="left"><p>第一次必须在第一次设置交互模式时首次完成设置的超时值（以分钟为单位）。 范围 = 0 到2147483647。</p></td>
</tr>
<tr class="even">
<td align="left"><p>PostponeUtcDateTimeLimit </p></td>
<td align="left"><p>SZ</p></td>
<td align="left"><p></p></td>
<td align="left"><p>第一次可以延迟设置的日期和时间（采用 UTC 日期时间格式）。 以 " &quot; 24 小时制" 标准的格式输入 yyyy hh： MM &quot; 和小时数。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>RetryDialogMsg </p></td>
<td align="left"><p>MULTI_SZ</p></td>
<td align="left"><p>在资源文件中找到邮件 </p></td>
<td align="left"><p>首次设置必须重新尝试设置时显示给最终用户的可自定义消息。</p></td>
</tr>
<tr class="even">
<td align="left"><p>SetComputerNameEnabled </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 0</p></td>
<td align="left"><p>配置来宾中的 Sysprep.inf 文件的 [UserData] 部分下的 ComputerName 条目是否应根据指定的 ComputerNameMask 进行更新。   0 = false;1 = true。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>0 = false：不会根据 ComputerNameMask 更新 Sysprep.inf 文件中的 ComputerName 条目。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>1 = true：将根据 ComputerNameMask 更新 Sysprep.inf 文件中的 ComputerName 条目。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>SetJoinDomainEnabled </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 0</p></td>
<td align="left"><p>配置是否应更新来宾中 Sysprep.inf 文件的 [标识] 部分中的 JoinDomain 设置以匹配主机上的设置。  0 = false;1 = true。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>0 = false：不会更新 Sysprep.inf 文件中的 JoinDomain 设置以匹配主机上的设置。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>1 = true： Sysprep.inf 文件中的 JoinDomain 设置会更新，以匹配主机上的设置。</p></td>
</tr>
<tr class="even">
<td align="left"><p>SetMachineObjectOUEnabled </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 0</p></td>
<td align="left"><p>配置来宾中的 Sysprep.inf 文件的 [标识] 部分下的 MachineObjectOU 设置是否会更新，以匹配主机。  0 = false;1 = true。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>0 = false：不会更新 Sysprep.inf 文件中的 MachineObjectOU 设置以匹配主机上的设置。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>1 = true： Sysprep.inf 文件中的 MachineObjectOU 设置会更新，以匹配主机上的设置。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>SetRegionalSettingsEnabled </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 0</p></td>
<td align="left"><p>配置来宾中的 Sysprep.inf 文件的 [RegionalSettings] 部分下的设置是否会更新，以匹配主机。  0 = false;1 = true。</p>
<div class="alert">
<strong>注意</strong><br/><p>默认情况下，来宾中的时区设置始终与主机中的时区设置同步。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>0 = false：来宾中 Sysprep.inf 文件的 [RegionalSettings] 部分下的设置不会更新以匹配主机。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>1 = true：来宾中 Sysprep.inf 文件的 [RegionalSettings] 部分下的设置已更新，以匹配主机。</p></td>
</tr>
<tr class="even">
<td align="left"><p>SetUserDataEnabled </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 0</p></td>
<td align="left"><p>配置来宾中的 Sysprep.inf 文件的 [UserData] 部分下的 FullName 和 OrgName 设置是否会更新，以匹配主机上的设置。  0 = false;1 = true。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>0 = false：不会更新 Sysprep.inf 文件中的 FullName 和 OrgName 设置以匹配主机上的设置。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>1 = true：将更新 Sysprep.inf 文件中的 FullName 和 OrgName 设置以匹配主机上的设置。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>StartDialogMsg </p></td>
<td align="left"><p>MULTI_SZ</p></td>
<td align="left"><p>在资源文件中找到邮件 </p></td>
<td align="left"><p>可自定义的消息，在首次设置准备好开始时显示给最终用户。 </p></td>
</tr>
<tr class="even">
<td align="left"><p>TaskCancelTimeout</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 30</p></td>
<td align="left"><p>超时值（以秒为单位），在设置为取消操作的第一次等待来自虚拟机的响应时。 范围 = 0 到2147483647。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>TaskVMTurnOffTimeout</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 60</p></td>
<td align="left"><p>第一次设置等待虚拟机关闭的超时值（以秒为单位）。 范围 = 0 到2147483647。</p></td>
</tr>
<tr class="even">
<td align="left"><p>UpgradeTimeout</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 600</p></td>
<td align="left"><p>尝试升级 MED-V 来宾代理软件超时前的时间（以秒为单位）。范围 = 0 到2147483647。</p></td>
</tr>
</tbody>
</table>



## UserExperience 键


下表提供了与 HKEY _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\Medv\\v2\\UserExperience 键和 HKEY \ _CURRENT \ _USER \\Software\\Microsoft\\Medv\\v2\\UserExperience 键相关联的注册表值的相关信息。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名称</th>
<th align="left">类型</th>
<th align="left">Data/Default</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>AppPublishingEnabled </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 1</p></td>
<td align="left"><p>配置是否启用从来宾到主机的应用程序发布。  0 = false;1 = true。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>0 = false：禁用从来宾到主机的应用程序发布。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>1 = true：支持从来宾到主机的应用程序发布。</p></td>
</tr>
<tr class="even">
<td align="left"><p>AudioSharingEnabled </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 1</p></td>
<td align="left"><p>配置在来宾和主机之间共享音频 i/o 设备是否已启用。  0 = false;1 = true。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>0 = false：在来宾和主机之间禁用音频 i/o 设备的共享。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>1 = true：支持在来宾和主机之间共享音频输入/输出设备。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ClipboardSharingEnabled </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 1</p></td>
<td align="left"><p>配置是否启用了来宾和主机之间的剪贴板共享。  0 = false;1 = true。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>0 = false：禁用来宾和主机之间的剪贴板共享。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>1 = true：支持在来宾和主机之间共享剪贴板。</p></td>
</tr>
<tr class="even">
<td align="left"><p>DialogTimeout</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 300</p></td>
<td align="left"><p>首次设置 "开始" 对话框超时之前的时间（以秒为单位）。范围 = 0 到2147483647。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>HideVmTimeout</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 30</p></td>
<td align="left"><p>长时间登录尝试期间从最终用户隐藏全屏虚拟机窗口的超时值（以分钟为单位）。</p></td>
</tr>
<tr class="even">
<td align="left"><p>LogonStartEnabled </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 1</p></td>
<td align="left"><p>配置当最终用户登录到桌面或启动第一个来宾应用程序时是否应启动来宾。  0 = false;1 = true。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>0 = false：启动第一个来宾应用程序时，将启动来宾。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>1 = true：当最终用户登录到桌面时，将启动来宾。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>PrinterSharingEnabled </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 1</p></td>
<td align="left"><p>配置是否启用来宾和主机之间的打印机共享。  0 = false;1 = true。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>0 = false：禁用来宾和主机之间的打印机共享。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>1 = true：启用来宾和主机之间的打印机共享。</p></td>
</tr>
<tr class="even">
<td align="left"><p>RebootAbsoluteDelayTimeout </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认 = 1440</p></td>
<td align="left"><p>第一次设置等待重启的超时值（以分钟为单位）。 范围 = 0 到2147483647。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>RedirectUrls </p></td>
<td align="left"><p>MULTI_SZ</p></td>
<td align="left"><p>指定的 URL 列表</p></td>
<td align="left"><p>指定要从主机重定向到来宾的 Url 的列表。 </p></td>
</tr>
<tr class="even">
<td align="left"><p>SmartCardLogonEnabled</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 0</p></td>
<td align="left"><p>配置智能卡是否可用于对用户进行身份验证以使用 MED-V。 0 = false;1 = true。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>0 = false：不允许智能卡向 MED-V 用户验证最终用户。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>1 = true：让智能卡向 MED-V 用户验证最终用户。</p>
<div class="alert">
<strong>重要提示</strong><br/><p>如果 SmartCardLogonEnabled 和 CredentialCacheEnabled 都已启用，SmartCardLogonEnabled 将忽略 CredentialCacheEnabled。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>SmartCardSharingEnabled </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 1</p></td>
<td align="left"><p>配置是否启用来宾与主机之间的智能卡共享。  0 = false;1 = true。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>0 = false：禁用来宾和主机之间的智能卡共享。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>1 = true：启用来宾和主机之间的智能卡共享。</p></td>
</tr>
<tr class="even">
<td align="left"><p>USBDeviceSharingEnabled </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 1</p></td>
<td align="left"><p>配置是否启用来宾与主机之间的 USB 设备共享。  0 = false;1 = true。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>0 = false：禁用来宾和主机之间的 USB 设备共享。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>1 = true：启用来宾和主机之间的 USB 设备共享。</p></td>
</tr>
</tbody>
</table>



## VM 密钥


下表提供了与 HKEY _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\Medv\\v2\\VM 键和 HKEY \ _CURRENT \ _USER \\Software\\Microsoft\\Medv\\v2\\VM 键相关联的注册表值的相关信息。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名称</th>
<th align="left">类型</th>
<th align="left">Data/Default</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>CloseAction </p></td>
<td align="left"><p>SZ</p></td>
<td align="left"><p>默认 = 休眠</p></td>
<td align="left"><p>虚拟机在运行的最后一个应用程序关闭后执行的操作。 如果启用了 LogonStartEnabled 值，此设置将被忽略。 可能的选项如下所示：</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><strong>休眠 </strong> 。 此选项将释放虚拟机正在使用的所有物理资源（如内存和 CPU），并保存所有运行的应用程序和操作的状态。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><strong>关闭 </strong> 。 此选项将安全地关闭来宾操作系统，然后释放虚拟机使用的所有物理资源，例如内存和 CPU。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><strong>关闭 </strong> 。 此选项可能会导致数据丢失，因为它与关闭电源按钮或在物理计算机上拉出电源线的方式相同。 只有在不能使用其他两个选项时，才可使用此选项。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>GuestMemFromHostMem </p></td>
<td align="left"><p>MULTI_SZ</p></td>
<td align="left"><p>378、512、1024、1536、2048 </p></td>
<td align="left"><p>来宾的内存（MB）值的列表。 此值用于确定来宾可使用的 RAM 量。 与 HostMemToGuestMem 结合使用时，将创建一个查找表，以确定要在来宾虚拟机上分配的 RAM 量。 可能的值可以从128到3712。</p></td>
</tr>
<tr class="even">
<td align="left"><p>GuestUpdateDuration </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 240</p></td>
<td align="left"><p>从 GuestUpdateTime 值中指定的时间开始，MED-V 应将来宾保持唤醒状态以进行自动更新。 范围 = 0 到1440。 将此值设置为零（0）可禁用来宾修补功能。</p>
<p>有关自动更新的来宾修补的详细信息，请参阅 <a href="managing-automatic-updates-for-med-v-workspaces.md" data-raw-source="[Managing Automatic Updates for MED-V Workspaces](managing-automatic-updates-for-med-v-workspaces.md)"> 管理 Med-v 工作区的自动更新 </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>GuestUpdateTime </p></td>
<td align="left"><p>SZ</p></td>
<td align="left"><p>默认值 = 00：00</p></td>
<td align="left"><p>当 MED-V 应使用24小时制时钟标准唤醒客户进行自动更新时，每个工作日的小时数和分钟数。 以 HH： MM 的格式指定时间  </p>
<p>有关自动更新的来宾修补的详细信息，请参阅 <a href="managing-automatic-updates-for-med-v-workspaces.md" data-raw-source="[Managing Automatic Updates for MED-V Workspaces](managing-automatic-updates-for-med-v-workspaces.md)"> 管理 Med-v 工作区的自动更新 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>HostMemToGuestMem </p></td>
<td align="left"><p>MULTI_SZ</p></td>
<td align="left"><p>1024、2048、4096、8192、16384 </p></td>
<td align="left"><p>来宾的内存（MB）值列表，由主机上可用的 RAM 确定。 与 GuestMemFromHostMem 结合使用时，将创建一个查找表，以确定要在来宾虚拟机上分配的 RAM 量。 可能的值可以从1024到16384。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>HostMemToGuestMemCalcEnabled</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 1</p></td>
<td align="left"><p>配置是否从主机上存在的内存计算为来宾分配的内存。  0 = false;1 = true。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>0 = false：分配给来宾的内存不是通过主机上存在的内存计算的。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>1 = true：为来宾分配的内存是根据主机上存在的内存计算的。</p></td>
</tr>
<tr class="even">
<td align="left"><p>内存 </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 512</p></td>
<td align="left"><p>应为来宾虚拟机分配的 RAM （MB）。 如果启用了 HostMemToGuestMemEnabled 设置，此设置将被忽略。 范围 = 128 到2048。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MultiUserEnabled </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 0</p></td>
<td align="left"><p>配置多个用户是否共享同一个 MED-V 工作区。  0 = false;1 = true。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>0 = false：多个用户不共享同一个 MED-V 工作区。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>1 = true：多个用户共享同一个 MED-V 工作区。</p></td>
</tr>
<tr class="even">
<td align="left"><p>NetworkingMode </p></td>
<td align="left"><p>SZ</p></td>
<td align="left"><p>默认值 = NAT</p></td>
<td align="left"><p>来宾上使用的网络连接类型。 可能的值如下所示：</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><strong>已桥接 </strong> 。 MED-V 有自己的网络地址，通常通过 DHCP 获得。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><strong>NAT </strong> 。 MED-V 使用网络地址转换（NAT）共享主机&#39;s IP 用于传出通信。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>TaskTimeout </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>默认值 = 600</p></td>
<td align="left"><p>常规超时值（以秒为单位），MED-V 将等待任务完成，例如重启和关闭。 范围 = 0 到2147483647。</p></td>
</tr>
</tbody>
</table>



## 来宾注册表设置


本部分列出了可配置的 MED-V 来宾注册表项并解释其用法。

### 2

下表提供了与 HKEY _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\Medv\\v2\\ 键相关联的来宾注册表值的相关信息。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名称 </th>
<th align="left">类型 </th>
<th align="left">Data/Default </th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>EnableGPWorkarounds</p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>默认值 = 1 </p></td>
<td align="left"><p>配置 MED-V 处理密钥 BufferPolicyReads 和 GroupPolicyMinTransferRate 的方式。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>默认情况下，MED-V 按如下方式设置这些键：</p>
<p>BufferPolicyReads = 1 和 GroupPolicyMinTransferRate = 0。</p>
<p>创建 EnableGPWorkarounds 键（如有必要），如果不希望 MED-V 更改 BufferPolicyReads 和 GroupPolicyMinTransferRate 的默认设置，则将键设置为零。</p>
<div class="alert">
<strong>注意</strong><br/><p>如果你的 MED-V 工作区在 NAT 模式下运行，EnableGPWorkarounds 将影响注册表项 BufferPolicyReads 和 GroupPolicyMinTransferRate。 如果你的 MED-V 工作区在桥接模式下运行，EnableGPWorkarounds 仅影响注册表项 BufferPolicyReads。</p>
</div>
<div>

</div>
<p>1 = true： MED-V 设置键 BufferPolicyReads = 1 和 GroupPolicyMinTransferRate = 0 （如果在 NAT 模式下运行）或仅 BufferPolicyReads = 1 （如果在桥接模式下运行）。</p>
<p>0 = false： MED-V 不会对键 BufferPolicyReads 和 GroupPolicyMinTransferRate 进行任何更改。</p></td>
</tr>
</tbody>
</table>



## 相关主题


[管理 MED-V 工作区应用程序](manage-med-v-workspace-applications.md)

[管理 MED-V URL 重定向](manage-med-v-url-redirection.md)

[管理 MED-V 工作区设置](manage-med-v-workspace-settings.md)









