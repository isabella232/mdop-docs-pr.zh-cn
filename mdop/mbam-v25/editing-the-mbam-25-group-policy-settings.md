---
title: 编辑 MBAM 2.5 组策略设置
description: 编辑 MBAM 2.5 组策略设置
author: dansimp
ms.assetid: a50b6b0c-6818-4419-8447-d0520a533dba
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0f6d180cba6dc721ff7de1607d57f90184303d88
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798085"
---
# 编辑 MBAM 2.5 组策略设置


若要成功部署 Microsoft BitLocker 管理和监视（MBAM），您必须：

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
<td align="left"><p>复制 MBAM 2.5 组策略模板。</p></td>
<td align="left"><p><a href="copying-the-mbam-25-group-policy-templates.md" data-raw-source="[Copying the MBAM 2.5 Group Policy Templates](copying-the-mbam-25-group-policy-templates.md)">复制 MBAM 2.5 组策略模板</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>确定要在 MBAM 实现中使用的组策略对象（Gpo）。 根据您的组织的需要，您可能必须配置其他组策略设置。</p></td>
<td align="left"><p><a href="planning-for-mbam-25-group-policy-requirements.md" data-raw-source="[Planning for MBAM 2.5 Group Policy Requirements](planning-for-mbam-25-group-policy-requirements.md)">规划 MBAM 2.5 组策略要求 </a> -包含对 gpo 的描述</p></td>
</tr>
<tr class="odd">
<td align="left"><p>为您的组织设置组策略设置。</p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 

**重要提示** 请勿更改**BitLocker 驱动器加密**节点中的组策略设置，否则 MBAM 将无法正常工作。 在**MDOP MBAM （BitLocker Management）** 节点中配置组策略设置时，MBAM 会自动为你配置**BitLocker 驱动器加密**设置。

 

**编辑 MBAM 客户端组策略设置**

1.  在安装了 MBAM 组策略模板的计算机上，请确保启用 MBAM 服务。

2.  在安装了 MBAM 组策略模板的计算机上使用组策略管理控制台（GPMC）或 Microsoft 高级组策略管理 MDOP 产品，选择 "**计算机配置** &gt; **策略**" &gt; **管理模板** &gt; **Windows 组件** &gt; **MDOP MBAM （BitLocker Management）**。

3.  编辑在客户端计算机上启用 MBAM 客户端服务所需的组策略设置。 对于下表中的每个策略，选择 "**策略组**"，单击所需的**策略**，然后配置设置。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">策略组</th>
    <th align="left">策略</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>客户端管理</p></td>
    <td align="left"><p>配置 MBAM 服务</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>操作系统驱动器</p></td>
    <td align="left"><p>操作系统驱动器加密设置</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>可移动驱动器</p></td>
    <td align="left"><p>控制可移动驱动器上的 BitLocker 的使用</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>固定驱动器</p></td>
    <td align="left"><p>在固定驱动器上控制 BitLocker 的使用</p></td>
    </tr>
    </tbody>
    </table>

     

## 相关主题


[规划 MBAM 2.5 组策略要求](planning-for-mbam-25-group-policy-requirements.md)

[复制 MBAM 2.5 组策略模板](copying-the-mbam-25-group-policy-templates.md)

 
## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。
 





