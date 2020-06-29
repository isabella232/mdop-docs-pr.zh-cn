---
title: 更改 UE-V 计划任务的频率
description: 更改 UE-V 计划任务的频率
author: dansimp
ms.assetid: 33c2674e-0df4-4717-9c3d-820a90b16e19
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ced608608ffae82a29fb5ca84cfca281082b8127
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803218"
---
# 更改 UE-V 计划任务的频率


Microsoft 用户体验虚拟化（UE-V） Agent 安装程序 AgentSetup.exe 在 UE-V Agent 安装期间会创建两个计划任务。 这两个任务是**模板自动更新**任务和**设置存储位置状态**任务。 这些计划任务无法通过 UE-V 工具进行配置。 希望更改这些项目的计划任务的管理员可以创建使用 Schtasks.exe 命令行选项的脚本。

有关 Schtasks.exe 的详细信息，请参阅[如何使用 Schtasks、exe 在 Windows Server 2003 中安排任务](https://go.microsoft.com/fwlink/?LinkID=264854)。

## 模板自动更新


**模板自动更新**任务检查设置模板目录中是否有新的、已更新或已删除的模板。 仅当配置了 SettingsTemplateCatalog 时，此任务才会运行。 **模板自动更新**任务运行 "ApplySettingsCatalog.exe" 文件，该文件位于 ue-v agent 安装目录中。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">任务名称</th>
<th align="left">默认触发器</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>\Microsoft\UE-V\Template 自动更新</p></td>
<td align="left"><p>每天3:30</p></td>
</tr>
</tbody>
</table>

 

**示例：** 以下命令将代理配置为每小时检查设置模板目录存储。

``` syntax
schtasks /change /tn "Microsoft\UE-V\Template Auto Update" /ri 60
```

## 设置存储位置状态


**设置存储位置状态**任务将执行下列操作：

1.  进行检查以确保 UE-V 文件夹仍在 "脱机文件" 功能中固定或注册。

2.  检查设置存储位置是否处于离线状态或联机状态。

3.  在指定间隔（而不是脱机文件的默认间隔）强制执行同步。

4.  同步配置为预回迁的所有设置包。

5.  检查 Active Directory 主目录路径是否已更改。

6.  将当前设置存储配置写入以下位置

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">任务名称</th>
    <th align="left">默认触发器</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>\Microsoft\UE-V\Settings 存储位置状态</p></td>
    <td align="left"><p>在任何用户登录时，每隔30分钟（每隔30分钟）将无限期重复。</p></td>
    </tr>
    </tbody>
    </table>

     

**示例：** 以下命令将代理配置为在每小时运行上述操作。

``` syntax
schtasks /change /tn "\Microsoft\UE-V\Settings Storage Location Status" /ri 60
```

## 相关主题


[管理 UE-V 1.0](administering-ue-v-10.md)

[UE-V 1.0 的操作](operations-for-ue-v-10.md)

 

 





