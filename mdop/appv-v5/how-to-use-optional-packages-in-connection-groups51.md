---
title: 如何使用连接组中的可选程序包
description: 如何使用连接组中的可选程序包
author: dansimp
ms.assetid: 67666f18-b704-4852-a1e4-d13633bd2baf
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ffa29f5d62e57a60423b2041cb71787d2c96bd66
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798343"
---
# 如何使用连接组中的可选程序包


从 Microsoft Application Virtualization （App-v） 5.0 SP3 开始，你可以将可选程序包添加到连接组以简化连接组管理。 下表总结了使用可选程序包可以更轻松地完成的任务，并提供了指向每个任务的说明的链接。

**注意** 
**在 app-v 5.0 SP3 之前的版本中不支持可选程序包。**

 

使用可选程序包之前，请参阅[在连接组中使用可选程序包的要求](#bkmk-reqs-using-cg)。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">链接到说明</th>
<th align="left">任务</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="#bkmk-apps-plugs-optional" data-raw-source="[Use one connection group, with optional packages, for multiple users who have different packages entitled to them](#bkmk-apps-plugs-optional)">对具有不同程序包的多个用户使用一个连接组和可选程序包</a></p></td>
<td align="left"><p>使用单个连接组，让不同的最终用户可以使用不同组的应用程序和插件。</p>
<p>例如，你希望将 Microsoft Office 分发给所有最终用户，但将不同的插件分发给不同的用户子集。</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="#bkmk-unpub-del-optl-pkg" data-raw-source="[Unpublish or delete an optional package, or unpublish an optional package and republish it later, without changing the connection group](#bkmk-unpub-del-optl-pkg)">取消发布或删除可选程序包，或取消发布可选程序包并在以后重新发布，而无需更改连接组</a></p></td>
<td align="left"><p>取消发布、删除或重新发布可选程序包，而无需在 App-v 客户端上禁用、删除、编辑、添加和重新启用连接组。</p>
<p>您还可以取消发布可选程序包并在以后重新发布，而无需禁用或重新发布连接组。</p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-apps-plugs-optional"></a>将一个连接组与可选程序包一起使用，让多个用户有权使用不同的程序包


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">任务说明</th>
<th align="left">如何执行任务</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>通过 app-v 5.0 SP3 和 App-v 5。1</strong></p>
<p>你可以将可选程序包添加到连接组，这使你可以为不同的最终用户提供不同的应用程序和插件组合。</p>
<p><strong>示例 </strong> ：你想要将 Microsoft Office 分发给最终用户，但仅为用户子集启用特定插件。</p>
<p>若要执行此操作，请创建包含带有 Office 的程序包的连接组，以及使用 Office 插件的其他程序包，然后使插件程序包可选。</p>
<p>不具备插件程序包权利的最终用户仍能运行 Office。</p></td>
<td align="left"><table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">方法</th>
<th align="left">步骤</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-v Server-管理控制台</p></td>
<td align="left"><ol>
<li><p>在管理控制台中，选择 " <strong> 连接组 </strong> " 以显示 "连接组" 库。</p></li>
<li><p>从 "连接组" 库中选择正确的连接组。</p></li>
<li><p><strong> </strong> 在 "已连接的程序包" 窗格中单击 "编辑"。</p></li>
<li><p>选择 <strong> </strong> 程序包名称旁边的 "可选"。</p></li>
<li><p>选中 " <strong> 添加对组访问的程序包访问权限" </strong> 复选框。 在将程序包分配给 Active Directory 组时，此必需步骤会将你以前配置的程序包权利添加到连接组。</p></li>
</ol></td>
</tr>
<tr class="even">
<td align="left"><p>App-v 服务器-PowerShell cmdlet</p></td>
<td align="left"><p>使用以下 cmdlet，并指定 <strong> -可选 </strong> 参数：</p>
<p><strong>Add-AppvServerConnectionGroupPackage</strong></p>
<p><strong>语法</strong></p>
<p><code>Add-AppvServerConnectionGroupPackage [-AppvServerConnectionGroup] &lt;SerializableConnectionGroup&gt; [[-AppvServerPackage] &lt;PackageVersion&gt;] [-Optional] [-Order &lt;int&gt;] [-UseAnyPackageVersion]</code></p>
<p><strong>示例：</strong></p>
<p><code>Add-AppvServerConnectionGroupPackage -Name &quot;Connection Group 1&quot; -PackageName &quot;Package 1&quot; -Optional</code></p></td>
</tr>
<tr class="odd">
<td align="left"><p>独立计算机上的 app-v 客户端</p></td>
<td align="left"><ol>
<li><p>创建连接组 XML 文档，并将 <strong> 程序包 </strong> 标签属性 IsOptional 设置 <strong> </strong> 为 <strong> "true"。</strong></p></li>
<li><p>使用以下 cmdlet 添加和启用连接组：</p>
<ul>
<li><p>Add-AppvClientConnectionGroup</p></li>
<li><p>Enable-AppvClientConnectionGroup</p></li>
</ul></li>
</ol>
<p><strong>带有可选程序包的连接组 XML 文档示例：</strong></p>
<pre class="syntax" space="preserve"><code>&lt;?xml version=&quot;1.0&quot; ?&gt;
&lt;AppConnectionGroup
   xmlns=&quot;<a href="https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup&amp;quot" data-raw-source="https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup&amp;quot">https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup&quot</a>;
   AppConnectionGroupId=&quot;8105CCD5-244B-4BA1-8888-E321E688D2CB&quot;
   VersionId=&quot;84CE3797-F1CB-4475-A223-757918929EB4&quot;
   DisplayName=&quot;Contoso Software Connection Group&quot; &gt;
&lt;Packages&gt;
&lt;Package
   PackageId=&quot;7735d1a8-5ef9-4df9-a1cf-3aa92ef54fe7&quot;
   VersionId=&quot;ec560d6f-e62e-48eb-a9e5-7c52a8c2e149&quot;
   DisplayName=&quot;Contoso Business Manager&quot;
/&gt;

&lt;Package
   PackageId=&quot;fc6fe0f7-be3d-4643-b37d-fc3f62d4dd5c&quot;
   VersionId=&quot;c67a71cd-3542-4a48-93e8-20c643c50970&quot;
   DisplayName=&quot;Contoso Forms&quot;
   IsOptional=&quot;false&quot;
/&gt;

&lt;Package
   PackageId=&quot;8f6301a5-4348-4039-9560-b27a5bb72711&quot;
   VersionId=&quot;6c694b45-3e19-46c6-a327-d159aa39e1d2&quot;
   DisplayName=&quot;Contoso Tax&quot;
   IsOptional=&quot;true&quot;
/&gt;

&lt;Package
   PackageId=&quot;89d701bc-d507-4299-b6b6-000000003472&quot;
   VersionId=&quot;*&quot;
   DisplayName=&quot;Contoso Accounts&quot;
   IsOptional=&quot;true&quot;
/&gt;

&lt;/Packages&gt;
&lt;/AppConnectionGroup&gt;</code></pre></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>对于早于 app-v 5.0 SP3 的版本</strong></p></td>
<td align="left"><p>您必须创建许多连接组才能使特定用户能够使用特定的应用程序和插件组合。</p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-unpub-del-optl-pkg"></a>取消发布或删除可选程序包，或取消发布可选程序包并在以后重新发布，而无需更改连接组


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">任务说明</th>
<th align="left">如何执行任务</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>通过 app-v 5.0 SP3 和 App-v 5。1</strong></p>
<p>你可以取消发布、删除或重新发布位于连接组中的可选程序包，而无需在 App-v 客户端上禁用或重新启用连接组。</p>
<p>您也可以取消发布可选程序包，稍后重新发布它，而无需禁用或重新发布连接组。</p>
<p><strong>示例 </strong> ：如果发布包含 Microsoft Office 插件的可选程序包，并且想要删除该插件，则可以取消发布程序包，而无需禁用连接组。</p></td>
<td align="left"><table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">方法</th>
<th align="left">步骤</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-v Server-管理控制台</p></td>
<td align="left"><ul>
<li><p>若要取消发布程序包，请执行以下操作：在管理控制台中，选择 "选择 <strong> 程序包" </strong> 页面，单击或右键单击要取消发布的程序包，然后单击 " <strong> 取消发布" </strong> 。</p></li>
<li><p>若要从连接组中删除可选程序包，请执行以下操作：在 " <strong> 连接组" </strong> 页面上，选择要删除的程序包，然后单击右箭头从左下角的 "连接" 组窗格中删除程序包。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>独立计算机上的 app-v 客户端</p></td>
<td align="left"><p>使用以下现有 cmdlet：</p>
<ul>
<li><p>取消发布-AppvClientPackage</p></li>
<li><p>Remove-AppvClientPackage</p></li>
</ul>
<p>有关详细信息，请参阅 <a href="how-to-manage-app-v-51-packages-running-on-a-stand-alone-computer-by-using-powershell.md" data-raw-source="[How to Manage App-V 5.1 Packages Running on a Stand-Alone Computer by Using PowerShell](how-to-manage-app-v-51-packages-running-on-a-stand-alone-computer-by-using-powershell.md)"> 使用 PowerShell 管理独立计算机上运行的 app-v 5.1 程序包 </a> 。</p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>对于早于 app-v 5.0 SP3 的版本</strong></p></td>
<td align="left"><p>您必须：</p>
<ol>
<li><p>从每个已启用的 App-v 客户端计算机中删除连接组。</p></li>
<li><p>取消发布程序包。</p></li>
<li><p>从连接组的定义中删除程序包。</p></li>
<li><p>重新发布连接组。</p></li>
</ol></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-reqs-using-cg"></a>在连接组中使用可选程序包的要求


在连接组中使用可选程序包之前，请查看以下要求：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">要求</th>
<th align="left">详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>连接组必须至少包含一个非可选程序包。</p></td>
<td align="left"><ul>
<li><p>请仔细检查你是否满足此要求，因为 App-v Server 和 PowerShell cmdlet 不会验证是否已满足要求。</p></li>
<li><p>如果您意外创建了一个不包含至少一个非可选程序包的连接组，并且最终用户尝试在该连接组中打开一个打包的应用程序，则连接组将失败。</p></li>
</ul>
<p></p></td>
</tr>
<tr class="even">
<td align="left"><ul>
<li><p>用户发布的连接组可以包含全局发布或向用户发布的程序包。</p></li>
<li><p>全局发布的连接组必须仅包含全局发布的程序包。</p></li>
</ul></td>
<td align="left"><p>全局发布的连接组必须包含全局发布的程序包，以确保程序包将在启动连接组的虚拟环境时可用。</p>
<p>如果你尝试添加或启用包含用户发布的程序包的全局发布的连接组，则连接组将失败。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>发布包含这些程序包的连接组之前，必须发布所有非可选程序包。</p></td>
<td align="left"><p>如果缺少任何非可选程序包，则连接组的虚拟环境无法启动。</p>
<p>如果未发布任何非可选程序包，则 App-v 客户端无法添加或启用连接组。</p></td>
</tr>
<tr class="even">
<td align="left"><p>取消发布全局发布的程序包之前，请确保有权使用该计算机上所有用户的连接组不再需要该程序包。</p></td>
<td align="left"><p>系统不检查软件包是否属于另一个用户的连接组。 取消发布全局程序包将使该计算机上的每个用户都无法使用它，因此请确保每个用户的连接组不再包含该程序包，或者将程序包设置为可选程序包。</p></td>
</tr>
</tbody>
</table>

 






## 相关主题


[管理连接组](managing-connection-groups51.md)

 

 





