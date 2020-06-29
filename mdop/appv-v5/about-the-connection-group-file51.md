---
title: 关于连接组文件
description: 关于连接组文件
author: dansimp
ms.assetid: 1f4df515-f5f6-4b58-91a8-c71598cb3ea4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 31ef9dc9c4465ed8f261b73518348c05ceb78d15
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798668"
---
# 关于连接组文件


**本主题内容：**

-   [连接组文件用途和位置](#bkmk-cg-purpose-loc)

-   [连接组 XML 文件的结构](#bkmk-define-cg-5-0sp3)

-   [在连接组中配置程序包的优先级](#bkmk-config-pkg-priority-incg)

-   [支持的虚拟应用程序连接配置](#bkmk-va-conn-configs)

## <a href="" id="bkmk-cg-purpose-loc"></a>连接组文件用途和位置


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>连接组用途</p></td>
<td align="left"><p>连接组是一种 App-v 功能，使你能够将程序包组合在一起以创建虚拟环境，这些程序包中的应用程序可以在其中相互交互。</p>
<p>示例：您希望将插件与 Microsoft Office 配合使用。 你可以创建包含插件的程序包，并创建包含 Office 的另一个程序包，然后将这两个程序包添加到连接组，以使 Office 能够使用这些插件。</p></td>
</tr>
<tr class="even">
<td align="left"><p>连接组文件的工作原理</p></td>
<td align="left"><p>当应用 app-v 5.1 连接组文件时，文件中枚举的程序包将在运行时合并到单个虚拟环境中。 使用 Microsoft Application Virtualization （App-v）5.1 连接组文件配置现有的 App-v 5.1 连接组。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>示例文件路径</p></td>
<td align="left"><p>%APPDATA%\Microsoft\AppV\Client\Catalog\PackageGroups {6CCC7575-162E-4152-9407-ED411DA138F4} {4D1E16E1-8EF8-41ED-92D5-8910A8527F96}。</p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-define-cg-5-0sp3"></a>连接组 XML 文件的结构


**本节内容：**

-   [定义连接组的参数](#bkmk-params-define-cg)

-   [用于定义连接组中的程序包的参数](#bkmk-params-define-pkgs-incg)

-   [App-v 示例连接组 XML 文件](#bkmk-50sp3-exp-cg-xml)

-   [App-v 5.0 至 App-V 5.0 SP2 示例连接组 XML 文件](#bkmk-50thru50sp2-exp-cg-xm)

### <a href="" id="bkmk-params-define-cg"></a>定义连接组的参数

下表介绍了定义连接组本身的 XML 文件中的参数，而不是程序包。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">字段</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>架构名称</p></td>
<td align="left"><p>架构的名称。</p>
<p><strong>适用于 app-v 5.0 SP3 </strong> 的入门：如果要使用此表中所述的新 "可选程序包" 和 "使用任何版本" 功能，必须在 XML 文件中指定以下架构：</p>
<p><code>xmlns=&quot;<a href="https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup&amp;quot" data-raw-source="https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup&amp;quot">https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup&quot</a>;</code></p></td>
</tr>
<tr class="even">
<td align="left"><p>AppConnectionGroupId</p></td>
<td align="left"><p>此连接组的唯一 GUID 标识符。 连接组状态与此标识符相关联。 仅在创建连接组时指定此标识符。</p>
<p>你可以通过键入：来创建新的 GUID <strong>[Guid]::NewGuid()</strong> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>VersionId</p></td>
<td align="left"><p>此版本的连接组的版本 GUID 标识符。</p>
<p>更新连接组（例如，通过添加或更新新程序包）时，必须更新版本 GUID 以反映新版本。</p></td>
</tr>
<tr class="even">
<td align="left"><p>DisplayName</p></td>
<td align="left"><p>连接组的显示名称。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>优先级</p></td>
<td align="left"><p>连接组的 "可选优先级" 字段。</p>
<p><strong>"0" </strong> - 表示最高优先级。</p>
<p>如果需要优先级，但尚未配置，程序包将失败，因为无法确定要使用的正确连接组。</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="bkmk-params-define-pkgs-incg"></a>用于定义连接组中的程序包的参数

在 &lt; &gt; 连接组 XML 文件的 "程序包" 部分中，通过指定每个程序包的唯一程序包标识符和版本标识符来列出连接组中的成员包，如下表中所述。 列表中的第一个包具有最高优先级。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">字段</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>PackageId</p></td>
<td align="left"><p>此程序包的唯一 GUID 标识符。 发布程序包的较新版本时，此 GUID 不会更改。</p></td>
</tr>
<tr class="even">
<td align="left"><p>VersionId</p></td>
<td align="left"><p>程序包版本的唯一 GUID 标识符。</p>
<p><strong>适用于 app-v 5.0 SP3 的入门 </strong> ：如果 <strong> 为程序包版本指定 "*" </strong> ，则会动态插入最新可用程序包版本的 GUID。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>IsOptional</p></td>
<td align="left"><p><strong>适用于从 app-v 5.0 SP3 </strong> ：参数，使你能够在连接组中使程序包可选。 有效条目为：</p>
<ul>
<li><p><strong>"true" </strong> –程序包在连接组中是可选的</p></li>
<li><p><strong>"false" </strong> –程序包在连接组中是必需的</p></li>
</ul>
<p>了解 <a href="how-to-use-optional-packages-in-connection-groups51.md" data-raw-source="[How to Use Optional Packages in Connection Groups](how-to-use-optional-packages-in-connection-groups51.md)"> 如何在连接组中使用可选程序包 </a> 。</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="bkmk-50sp3-exp-cg-xml"></a>App-v 示例连接组 XML 文件

以下示例连接组 XML 文件显示了上表中的字段示例，并突出显示了从 App-v 5.0 SP3 开始的新项。

```XML
<?xml version="1.0" encoding="UTF-16">
<appv:AppConnectionGroup 
  xmlns="https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup"
  xmlns:appv="https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup"  
  AppConnectionGroupId="61BE9B14-D2B4-41CE-A6E3-A1B658DE7000"
  VersionId="E6B6AA57-F2A7-49C9-ADF8-F2B5B3C8A42F"
  Priority="0"  
  DisplayName="Sample Connection Group">
  <appv:Packages>    
    <appv:Package
      PackageId="1DC709C8-309F-4AB4-BD47-F75926D04276"
      VersionId="*"
      IsOptional="true"    
    />
    <appv:Package
      PackageId="04220DCA-EE77-42BE-A9F5-96FD8E8593F2"
      VersionId="E15EFFE9-043D-4C01-BC52-AD2BD1E8BAFA"
      IsOptional="false"    
    />  
  </appv:Packages>
</appv:AppConnectionGroup>
```

### <a href="" id="bkmk-50thru50sp2-exp-cg-xm"></a>App-v 5.0 至 App-V 5.0 SP2 示例连接组 XML 文件

以下示例连接组 XML 文件适用于 app-v 5.0 （app-v 5.0 SP2）。 它显示了上表中字段的示例，但它不包括上述对 App-v 5.0 SP3 所述的更改。

```XML
<?xml version="1.0" encoding="UTF-16">
<appv:AppConnectionGroup
  xmlns="https://schemas.microsoft.com/appv/2010/virtualapplicationconnectiongroup"
  xmlns:appv="https://schemas.microsoft.com/appv/2010/virtualapplicationconnectiongroup"
  AppConnectionGroupId="61BE9B14-D2B4-41CE-A6E3-A1B658DE7000"
  VersionId="E6B6AA57-F2A7-49C9-ADF8-F2B5B3C8A42F"
  Priority="0"
  DisplayName="Sample Connection Group">
  <appv:Packages>
    <appv:Package
      PackageId="1DC709C8-309F-4AB4-BD47-F75926D04276"
      VersionId="C7DF4F63-5288-439C-ACEF-EF06BF401EC5"
    />
    <appv:Package
     PackageId="04220DCA-EE77-42BE-A9F5-96FD8E8593F2"
     VersionId="E15EFFE9-043D-4C01-BC52-AD2BD1E8BAFA"
   />
 </appv:Packages>
<appv:AppConnectionGroup>
```

## <a href="" id="bkmk-config-pkg-priority-incg"></a>在连接组中配置程序包的优先级


使用程序包列表顺序配置程序包优先级。 文档中的第一个程序包具有最高优先级。 列表中的后续程序包具有降序优先级。

程序包优先级是在虚拟环境初始化期间因不可避免的资源冲突的解决方案。 例如，如果在同一虚拟环境中打开的两个程序包定义了相同的注册表 DWORD 值，则具有最高优先级的程序包将确定设置的值。

你可以使用连接组文件通过以下方法配置每个连接组：

-   指定连接组的运行时优先级。 若要使用 App-v 管理控制台编辑优先级，请单击连接组，然后单击 "**编辑**"。

    **注意** 只有当程序包与多个连接组关联时，才需要优先级。

     

-   在连接组中指定程序包优先级。

当正在运行的虚拟应用程序从本机应用程序请求（例如 Microsoft Windows 资源管理器）启动时，"优先级" 字段是必需的。 App-v 客户端使用优先级确定应用程序应在哪个连接组虚拟环境中运行。 如果虚拟应用程序是多个连接组的一部分，则会出现此情况。

如果使用另一个虚拟应用程序打开虚拟应用程序，将使用原始虚拟应用程序的虚拟环境。 在此情况下不使用 "优先级" 字段。

**示例：**

Microsoft Outlook 正在虚拟环境**XYZ**中运行的虚拟应用程序。 打开附加的 Microsoft Word 文档时，Microsoft Word 将在虚拟环境**XYZ**中打开，无论虚拟化 Microsoft word 的关联连接组或运行时优先级。

## <a href="" id="bkmk-va-conn-configs"></a>支持的虚拟应用程序连接配置


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">配置</th>
<th align="left">示例方案</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>对. exe 文件和插件（.dll）</p></td>
<td align="left"><ul>
<li><p>你希望将 Microsoft Office 分发给所有用户，但仅将 Microsoft Excel 插件分发给用户的子集。</p></li>
<li><p>为相应用户启用连接组。</p></li>
<li><p>根据需要逐个更新每个程序包。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>对. exe 文件和中间件应用程序</p></td>
<td align="left"><ul>
<li><p>你的应用程序需要中间件应用程序或多个应用程序，它们都依赖于同一中间件运行时版本。</p></li>
<li><p>所有需要一个或多个应用程序的计算机都会收到带有应用程序和中间件应用程序运行时的连接组。</p></li>
<li><p>可以选择将多个中间件应用程序合并到单个连接组中。</p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">示例</th>
<th align="left">示例说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>用于财务部门的虚拟应用程序连接组</p></td>
<td align="left"><ul>
<li><p>中间件应用程序1</p></li>
<li><p>中间件应用程序2</p></li>
<li><p>中间件应用程序3</p></li>
<li><p>中间件应用程序运行时</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>HR 部门的虚拟应用程序连接组</p></td>
<td align="left"><ul>
<li><p>中间件应用程序5</p></li>
<li><p>中间件应用程序6</p></li>
<li><p>中间件应用程序运行时</p></li>
</ul></td>
</tr>
</tbody>
</table>
<p> </p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>对. exe 文件和 .exe 文件</p></td>
<td align="left"><p>你有一个应用程序依赖于另一个应用程序，你希望将这些程序包分开以实现操作效率、许可限制或推出时间线。</p>
<p><strong>示例：</strong></p>
<p>如果要部署 Microsoft Lync 2010，可以使用三个程序包：</p>
<ul>
<li><p>Microsoft Office2010</p></li>
<li><p>Microsoft Communicator2007</p></li>
<li><p>Microsoft Lync2010</p></li>
</ul>
<p>你可以使用以下连接组管理部署：</p>
<ul>
<li><p>Microsoft Office2010 和 Microsoft Communicator2007</p></li>
<li><p>Microsoft Office2010 和 Microsoft Lync2010</p></li>
</ul>
<p>部署完成后，你可以创建一个新的 Microsoft Office2010 + Microsoft Lync2010 程序包，或者将它们保留并保留为单独的程序包并使用连接组进行部署。</p></td>
</tr>
</tbody>
</table>

 






## 相关主题


[管理连接组](managing-connection-groups51.md)

 

 





