---
title: 复制 MBAM 2.5 组策略模板
description: 复制 MBAM 2.5 组策略模板
author: dansimp
ms.assetid: e526ecec-07ff-435e-bc90-3084b617b84b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/28/2017
ms.openlocfilehash: a3436552256b1632a11037dc94751207cde89d5c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803725"
---
# 复制 MBAM 2.5 组策略模板


在部署 MBAM 客户端安装之前，必须下载 MBAM 组策略模板，其中包含定义用于 BitLocker 驱动器加密的 MBAM 实现设置的组策略设置。 下载模板后，您可以将组策略设置设置为在整个企业中实施。

## 下载和部署 MDOP 组策略模板


MDOP 组策略模板可在自解压缩的压缩文件中下载，按技术和版本分组。

**如何下载和部署 MDOP 组策略模板**

1. 从[Microsoft 桌面优化包组策略管理模板](https://www.microsoft.com/download/details.aspx?id=55531)下载 MDOP 组策略模板。

2. 运行下载的文件以提取模板文件夹。

   **警告**  
   不要将模板直接提取到组策略部署目录中。 此文件中捆绑了多项技术和版本。



3. 在提取的文件夹中，找到技术版本的 admx 文件。 某些 MDOP 技术具有多个组策略对象（Gpo）集。 例如，MBAM 包括 MBAM 管理设置和 MBAM 用户设置。

4. 按语言-区域性（即*En*英语-美国）查找相应的 adml 文件。

5. 将 admx 和 adml 文件复制到策略定义文件夹。 根据你存储模板的位置，你可以从本地设备或域上的任何计算机配置组策略设置。

   **本地文件。** 若要从本地设备配置组策略设置，请将模板文件复制到以下位置：

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">文件类型</th>
   <th align="left">文件位置</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p>组策略模板（admx）</p></td>
   <td align="left"><p><code>%systemroot%</code>&lt;强有力的 &gt; policyDefinitions</strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>组策略语言文件（adml）</p></td>
   <td align="left"><p><code>%systemroot%</code>&lt;强有力的 &gt; policyDefinitions</strong><code>[MUIculture]</code></p></td>
   </tr>
   </tbody>
   </table>



~~~
**Domain central store.** To enable Group Policy settings configuration by a Group Policy administrator from any computer on the domain, copy files to the following locations on the domain controller:

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">File type</th>
<th align="left">File location</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Group Policy template (.admx)</p></td>
<td align="left"><p><code>%systemroot%</code>\<strong>sysvol\domain\policies\PolicyDefinitions</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>Group Policy language file (.adml)</p></td>
<td align="left"><p><code>%systemroot%</code>\<strong>sysvol\domain\policies\PolicyDefinitions\[MUIculture]</strong><code>\[MUIculture]</code></p>
<p>For example, the U.S. English ADML language-specific file will be stored in %systemroot%\sysvol\domain\policies\PolicyDefinitions\en-us.</p></td>
</tr>
</tbody>
</table>
~~~



6. 使用组策略管理控制台（GPMC）或高级组策略管理（AGPM）编辑组策略设置以配置 MDOP 技术的组策略设置。 有关详细信息，请参阅[编辑 MBAM 2.5 组策略设置](editing-the-mbam-25-group-policy-settings.md)。

   有关组策略设置的说明，请参阅[规划 MBAM 2.5 组策略要求](planning-for-mbam-25-group-policy-requirements.md)。


## 相关主题


[部署 MBAM 2.5 组策略对象](deploying-mbam-25-group-policy-objects.md)


## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。 
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。






