---
title: 如何下载和部署 MDOP 组策略 (.admx) 模板
description: 如何下载和部署 MDOP 组策略 (.admx) 模板
author: dansimp
ms.assetid: fdb64505-6c66-4fdf-ad74-a6a161191e3f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/15/2018
ms.openlocfilehash: 5bc5f8d536c113ccbc0a1931e6c7e4ed3c7a9a37
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804064"
---
# 如何下载和部署 MDOP 组策略 (.admx) 模板


你可以使用组策略模板、admx 和 adml 文件管理某些 Microsoft 桌面优化包（MDOP）技术（例如，app-v、UE-V 或 MBAM）的功能设置。 MDOP 组策略模板可在自解压缩的压缩文件中下载，按技术和版本分组。

## MDOP 组策略模板

**如何下载和部署 MDOP 组策略模板**

1. 下载最新的[MDOP 组策略模板](https://www.microsoft.com/download/details.aspx?id=55531) 

2. 通过运行展开已下载的 .cab 文件 `expand <download_folder>\MDOP_ADMX_Templates.cab -F:* <destination_folder>`

   **警告**  
   不要将模板直接提取到组策略部署目录中。 此文件中捆绑了多项技术和版本。

3. 在提取的文件夹中，找到技术版本的 admx 文件。 某些 MDOP 技术具有多个组策略对象（Gpo）集。 例如，MBAM 包括 MBAM 管理设置和 MBAM 用户设置。

4. 通过语言（即*En-us*英语-美国）查找相应的 adml 文件。

5. 将 admx 和 adml 文件复制到策略定义文件夹。 根据你存储模板的位置，你可以从本地设备或域上的任何计算机配置组策略设置。

   - **本地文件：** 若要从本地设备配置组策略设置，请将模板文件复制到以下位置：

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

   - **域中央存储：** 若要从域上任何计算机的组策略管理员处启用组策略设置配置，请将文件复制到域控制器上的以下位置：

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
   <td align="left"><p><code>%systemroot%</code>&lt;强有力的 &gt; sysvol\domain\policies\PolicyDefinitions</strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>组策略语言文件（adml）</p></td>
   <td align="left"><p><code>%systemroot%</code>&lt;强 &gt; sysvol\domain\policies\PolicyDefinitions [MUIculture]</strong><code>[MUIculture]</code></p>
   <p>例如，美国英语 ADML 语言特定的文件将存储在%systemroot%\sysvol\domain\policies\PolicyDefinitions\en-us。</p></td>
   </tr>
   </tbody>
   </table>

6. 使用组策略管理控制台（GPMC）或高级组策略管理（AGPM）编辑组策略设置以配置 MDOP 技术的组策略设置。

### 通过技术 MDOP 组策略

有关受支持的 MDOP 组策略的详细信息，请参阅该技术的特定文档。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">MDOP 技术</th>
<th align="left">版本捆绑</th>
<th align="left">注释</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>应用程序虚拟化 (App-V)</strong></p></td>
<td align="left"><p>App-v 5.0 和应用程序-V 5.0 服务包</p></td>
<td align="left"><p><a href="../appv-v5/how-to-modify-app-v-50-client-configuration-using-the-admx-template-and-group-policy.md" data-raw-source="[How to Modify App-V 5.0 Client Configuration Using the ADMX Template and Group Policy](../appv-v5/how-to-modify-app-v-50-client-configuration-using-the-admx-template-and-group-policy.md)">如何使用 ADMX 模板和组策略修改 App-V 5.0 Client 配置</a></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>用户体验虚拟化 (UE-V)</strong></p></td>
<td align="left"><p>UE-V 2.0 和 UE-V 2。1</p></td>
<td align="left"><p><a href="../uev-v2/configuring-ue-v-2x-with-group-policy-objects-both-uevv2.md" data-raw-source="[Configuring UE-V 2.x with Group Policy Objects](../uev-v2/configuring-ue-v-2x-with-group-policy-objects-both-uevv2.md)">通过组策略对象配置 UE-V 2. x</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p>UE-V 1.0 （包括 1.0 SP1）</p></td>
<td align="left"><p><a href="../uev-v1/configuring-ue-v-with-group-policy-objects.md" data-raw-source="[Configuring UE-V with Group Policy Objects](../uev-v1/configuring-ue-v-with-group-policy-objects.md)">使用组策略对象配置 UE-V</a></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Microsoft BitLocker 管理和监控 (MBAM)</strong></p></td>
<td align="left"><p>MBAM 2。5</p></td>
<td align="left"><p><a href="../mbam-v25/planning-for-mbam-25-group-policy-requirements.md" data-raw-source="[Planning for MBAM 2.5 Group Policy Requirements](../mbam-v25/planning-for-mbam-25-group-policy-requirements.md)">规划 MBAM 2.5 组策略要求</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p>MBAM 2.0 （包括 2.0 SP1）</p></td>
<td align="left"><p><a href="../mbam-v2/planning-for-mbam-20-group-policy-requirements-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Group Policy Requirements](../mbam-v2/planning-for-mbam-20-group-policy-requirements-mbam-2.md)">计划 MBAM 2.0 组策略要求</a></p>
<p><a href="../mbam-v2/deploying-mbam-20-group-policy-objects-mbam-2.md" data-raw-source="[Deploying MBAM 2.0 Group Policy Objects](../mbam-v2/deploying-mbam-20-group-policy-objects-mbam-2.md)">部署 MBAM 2.0 组策略对象</a></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p>MBAM 1。0</p></td>
<td align="left"><p><a href="../mbam-v1/how-to-edit-mbam-10-gpo-settings.md" data-raw-source="[How to Edit MBAM 1.0 GPO Settings](../mbam-v1/how-to-edit-mbam-10-gpo-settings.md)">如何编辑 MBAM 1.0 GPO 设置</a></p></td>
</tr>
</tbody>
</table>

 

 

 





