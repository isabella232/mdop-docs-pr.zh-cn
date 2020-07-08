---
title: 监视 MED-V 工作区部署
description: 监视 MED-V 工作区部署
author: dansimp
ms.assetid: 5de0cb06-b8a9-48a5-b8b3-836954295765
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6ec4c7c85326e7945aa3d61b7f96872afe24fe37
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804123"
---
# 监视 MED-V 工作区部署


通过 Microsoft 企业桌面虚拟化（MED-V）2.0 中的 "监视" 功能，你可以在单个 MED-V 工作区上运行查询，以确定在部署 MED-V 工作区后是否在整个企业中首次设置成功。 监视首次设置是否成功是很重要的，因为在首次成功完成设置之前，MED-V 不处于可用状态。

本部分提供的信息和说明可帮助你在首次设置成功时进行监视。

## 监视 MED-V 工作区部署


监视功能包含一个耦合的进程内 Windows 管理规范（WMI）提供程序，你可以使用 WMI 查询语言查询该提供程序，以便在 MED-V 工作区中针对所有最终用户首次设置状态。

WMI 提供程序是使用 Microsoft .Net Framework 3.5 中的 WMI 提供程序扩展框架实现的。 WMI 提供程序在 LocalService 的上下文中执行，并在 \\ProgramData. 下安全地存储首次设置状态。

WMI 提供程序在**root\\microsoft\\medv**命名空间中实现并实现类**FTS \ _Status**，该类将公开该方法**SetFtsState**。 MED-V 使用**SetFtsState**设置首次设置状态。

此类包含以下属性。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">属性</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>计算机</strong></p></td>
<td align="left"><p><strong>"只读" </strong> 属性，包含首次设置时预配的来宾虚拟机的名称。 此项包含来宾在首次设置失败时所拥有的名称。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>StatusCode</strong></p></td>
<td align="left"><p><strong>只读 </strong> 属性，如果首次设置成功，则该属性包含零。 返回的任何其他值等于所记录错误的事件 ID。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>时间</strong></p></td>
<td align="left"><p>首次设置完成时的 UTC 时间。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>用户</strong></p></td>
<td align="left"><p>首次运行设置的用户。</p></td>
</tr>
</tbody>
</table>

 

以下代码显示了托管对象格式（MOF）文件，该文件定义了**FTS \ _Status**类。

``` syntax
[dynamic: ToInstance, provider("MedvWmi, Version=2.0.258.0, Culture=neutral, PublicKeyToken=14986c3f172d1c2c")]
class FTS_Status
{
[read, key] string User;
[read] string Machine;
[read] sint32 StatusCode;
[read] datetime Time;
[static, implemented] void SetFtsState([in] sint32 statusCode, [in] string machine);
};
```

由于主要关注的问题很可能是首次未成功完成的 MED-V 工作区，因此你可以编写查询以仅返回首次设置失败的查询，例如：

``` syntax
Select * from FTS_Status where StatusCode != 0
```

在这种情况下，监视功能将返回第一次失败设置失败的那些 MED-V 工作区的列表，您可以使用该列表执行相应的操作来解决该故障。

## 相关主题


[监视 MED-V 工作区](monitor-med-v-workspaces.md)

[如何验证首次安装设置](how-to-verify-first-time-setup-settings.md)

 

 





