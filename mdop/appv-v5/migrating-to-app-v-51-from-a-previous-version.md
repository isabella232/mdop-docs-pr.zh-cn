---
title: 从以前版本迁移到 App-V 5.1
description: 从以前版本迁移到 App-V 5.1
author: dansimp
ms.assetid: e7ee0edc-7544-4c0a-aaca-d922a33bc1bb
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7fb6ddbfed4f6fd1ae9613d2ee86361a51918a65
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798324"
---
# 从以前版本迁移到 App-V 5.1


通过 Microsoft Application Virtualization （App-v）5.1，你可以将现有的 app-v 4.6 或 App-v 5.0 基础结构迁移到更灵活、更集成且更易于管理的 app-v 5.1 基础结构。
但是，不能直接从 App-v 4-v 升级到 app-v 5.1，必须首先迁移到 app-v 5.0。 有关从 app-v 4. x 迁移到 app-v 5.0 的详细信息，请参阅[从早期版本迁移](migrating-from-a-previous-version-app-v-50.md)  

**注意** App-v 5.1 程序包与 App-v 5.0 程序包完全相同。 版本之间的程序包格式没有任何变化，因此无需将 app-v 5.0 程序包转换为 App-v 5.1 程序包。

有关 App-v 4.6 和 App-v 5.1 之间的区别的详细信息，请参阅[关于 app-v 5.0](about-app-v-50.md)的**app-v 4.6 和 app-v 5.0 部分之间的差异**。

 

## <a href="" id="bkmk-pkgconvimprove"></a>对 app-v 5.1 程序包转换器的改进


现在，你可以使用程序包转换器转换包含脚本的 app-v 4.6 程序包，并且来自源 osd 文件的注册表信息和脚本现已包含在程序包转换器输出中。

你还可以将该 `–OSDsToIncludeInPackage` 参数与 cmdlet 配合使用 `ConvertFrom-AppvLegacyPackage` ，以指定哪些 osd 文件的信息被转换并放置在新程序包中。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">App-v 5.1 中的新增项</th>
<th align="left">在 App-v 5.1 之前</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>创建新的 .xml 文件，对应于与程序包关联的 .osd 文件;这些文件包括以下信息：</p>
<ul>
<li><p>环境变量</p></li>
<li><p>指向</p></li>
<li><p>文件类型关联</p></li>
<li><p>注册信息</p></li>
<li><p>标</p></li>
</ul>
<p>现在，你可以选择使用该参数将源目录中的 .osd 文件子集中的信息添加到程序包 <code>-OSDsToIncludeInPackage</code> 。</p></td>
<td align="left"><p>与程序包相关联的 .osd 文件中包含的注册表信息和脚本未包含在程序包转换器输出中。</p>
<p>程序包转换器将通过源目录中所有 .osd 文件中的信息填充新包。</p></td>
</tr>
</tbody>
</table>

 

### 转换语句示例

若要了解新进程，请查看下面的示例 `ConvertFrom-AppvLegacyPackage` 程序包转换器语句。

**如果源目录（\\\\OldPkgStore\\ContosoApp）包含以下内容：**

-   ContosoApp

-   ContosoApp.msi

-   ContosoApp.sprj

-   ContosoApp\_manifest.xml

-   X.x.x。x

-   .Osd

-   Z-a

**然后运行以下命令：**

``` syntax
ConvertFrom-AppvLegacyPackage –SourcePath \\OldPkgStore\ContosoApp\ 
-DestinationPath \\NewPkgStore\ContosoApp\
-OSDsToIncludeInPackage X.osd,Y.osd
```

**目标目录（\\\\NewPkgStore\\ContosoApp）中会创建以下内容：**

-   ContosoApp

-   ContosoApp.msi

-   ContosoApp\_DeploymentConfig.xml

-   ContosoApp\_UserConfig.xml

-   X\_Config.xml

-   Y\_Config.xml

-   Z\_Config.xml

**在上面的示例中：**

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">这些源目录文件 .。。</th>
<th align="left">...转换为这些目标目录文件 .。。</th>
<th align="left">...并将包含这些项目</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><ul>
<li><p>X.x.x。x</p></li>
<li><p>.Osd</p></li>
<li><p>Z-a</p></li>
</ul></td>
<td align="left"><ul>
<li><p>X_Config.xml</p></li>
<li><p>Y_Config.xml</p></li>
<li><p>Z_Config.xml</p></li>
</ul></td>
<td align="left"><ul>
<li><p>环境变量</p></li>
<li><p>指向</p></li>
<li><p>文件类型关联</p></li>
<li><p>注册信息</p></li>
<li><p>脚本</p></li>
</ul></td>
<td align="left"><p>每个 .osd 文件都将转换为一个单独的 .xml 文件，其中包含在 App-v 5.1 部署配置格式中列出的项目。 然后，可以从这些 .xml 文件中复制这些项，并根据需要放置在部署配置或用户配置文件中。</p>
<p>在此示例中，存在与源目录中的三个 .osd 文件对应的三个 .xml 文件。 每个 .xml 文件包含环境变量、快捷方式、文件类型关联、注册表信息和其对应的 .osd 文件中的脚本。</p></td>
</tr>
<tr class="even">
<td align="left"><ul>
<li><p>X.x.x。x</p></li>
<li><p>.Osd</p></li>
</ul></td>
<td align="left"><ul>
<li><p>ContosoApp</p></li>
<li><p>ContosoApp_DeploymentConfig.xml</p></li>
<li><p>ContosoApp_UserConfig.xml</p></li>
</ul></td>
<td align="left"><ul>
<li><p>环境变量</p></li>
<li><p>指向</p></li>
<li><p>文件类型关联</p></li>
</ul></td>
<td align="left"><p>将转换参数中指定的 .osd 文件中的信息 <code>-OSDsToIncludeInPackage</code> ，并将其放置在程序包内。 然后，转换器将使用程序包的内容填充部署配置文件和用户配置文件，就像在对新包进行排序时 App-v 排序器一样。</p>
<p>在此示例中，X-osd 和 Y 中包含的环境变量、快捷方式和文件类型关联已转换并放置在 App-v 包中，并且其中一些信息也包含在部署配置和用户配置文件中。 使用了 x.x.x.x 和 a.x，因为它们作为参数包含在 <code>-OSDsToIncludeInPackage</code> 参数中。 程序包中不包含来自 Z 的任何信息，因为它未包含在其中一个参数中。</p></td>
</tr>
</tbody>
</table>

 

## 转换使用早期版本的 App-v 创建的程序包


使用程序包转换器实用工具升级使用 app-v 5.0 之前的 app-v 版本创建的虚拟应用程序包。 程序包转换器使用 PowerShell 转换程序包，如果你有多个需要转换的程序包，则可以帮助自动处理该进程。

**重要提示** 转换现有程序包后，应该先测试程序包，然后再部署程序包，以确保转换过程成功。

 

**转换现有程序包之前需要了解的内容**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">问题</th>
<th align="left">解决方法</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>转换后，使用 DSC 的虚拟包不会链接。</p></td>
<td align="left"><p>使用连接组链接程序包。 请参阅 <a href="managing-connection-groups51.md" data-raw-source="[Managing Connection Groups](managing-connection-groups51.md)"> 管理连接组 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>在转换期间检测到环境变量冲突。</p></td>
<td align="left"><p>解决关联的 .osd 文件中的任何冲突 <strong> </strong> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>在转换期间检测到硬编码路径。</p></td>
<td align="left"><p>硬编码路径难以正确转换。 程序包转换器将检测并返回包含硬编码路径的文件的程序包。 查看带有硬编码路径的文件，并确定软件包是否需要该文件。 如果是这样，建议重新序列化程序包。</p></td>
</tr>
</tbody>
</table>

 

转换程序包时，检查是否有失败的文件或快捷方式。 在 App-v 4.6 程序包中找到该项目。 它可能是一个硬编码的路径。 转换路径。

**注意** 建议使用 app-v 5.1 sequencer 来转换需要利用功能的关键应用程序或应用程序。 请参阅[如何使用 app-v 5.1 对新应用程序进行排序](how-to-sequence-a-new-application-with-app-v-51-beta-gb18030.md)。

如果转换后的程序包未打开，还建议使用 App-v 5.1 sequencer 对应用程序进行重新排序。

 

[如何转换在以前版本的 App-V 中创建的程序包](how-to-convert-a-package-created-in-a-previous-version-of-app-v51.md)

## 迁移客户端


下表显示了升级客户端的推荐方法。

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
<td align="left"><p>将你的环境升级到最新版本的 App-v 4。6</p></td>
<td align="left"><p><a href="../appv-v4/application-virtualization-deployment-and-upgrade-considerations-copy.md" data-raw-source="[Application Virtualization Deployment and Upgrade Considerations](../appv-v4/application-virtualization-deployment-and-upgrade-considerations-copy.md)">应用程序虚拟化部署和升级注意事项 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>安装支持共存的 app-v 5.1 客户端。</p></td>
<td align="left"><p><a href="how-to-deploy-the-app-v-46-and-the-app-v--51-client-on-the-same-computer.md" data-raw-source="[How to Deploy the App-V 4.6 and the App-V 5.1 Client on the Same Computer](how-to-deploy-the-app-v-46-and-the-app-v--51-client-on-the-same-computer.md)">如何在同一台计算机上部署 app-v 4.6 和 app-v 5.1 客户端 </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>顺序和推出 app-v 5.1 程序包。 根据需要，取消发布 app-v 4.6 程序包。</p></td>
<td align="left"><p><a href="how-to-sequence-a-new-application-with-app-v-51-beta-gb18030.md" data-raw-source="[How to Sequence a New Application with App-V 5.1](how-to-sequence-a-new-application-with-app-v-51-beta-gb18030.md)">如何使用 App-v 5.1 对新应用程序进行排序 </a> 。</p></td>
</tr>
</tbody>
</table>

 

**重要提示** 您必须运行最新版本的 App-V 4.6 才能使用共存模式。 此外，在对程序包进行排序时，必须配置 "管理机构" 设置，该设置位于 **"用户****配置**" 部分中。

 

## 迁移 app-v 5.1 服务器的完整基础结构


没有直接的方法可升级到完整的 app-v 5.1 基础结构。 有关升级 app-v 服务器的信息，请使用以下部分中的信息。

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
<td align="left"><p>将你的环境升级到最新版本的 App-v 4.6。</p></td>
<td align="left"><p><a href="../appv-v4/application-virtualization-deployment-and-upgrade-considerations-copy.md" data-raw-source="[Application Virtualization Deployment and Upgrade Considerations](../appv-v4/application-virtualization-deployment-and-upgrade-considerations-copy.md)">应用程序虚拟化部署和升级注意事项 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>部署 app-v 5.1 版本的客户端。</p></td>
<td align="left"><p><a href="how-to-deploy-the-app-v-client-51gb18030.md" data-raw-source="[How to Deploy the App-V Client](how-to-deploy-the-app-v-client-51gb18030.md)">如何部署 app-v 客户端 </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>安装 App-v 5.1 server。</p></td>
<td align="left"><p><a href="how-to-deploy-the-app-v-51-server.md" data-raw-source="[How to Deploy the App-V 5.1 Server](how-to-deploy-the-app-v-51-server.md)">如何部署 app-v 5.1 服务器 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>迁移现有程序包。</p></td>
<td align="left"><p>查看 <strong> 使用本文的早期版本 app-v 部分创建的转换程序包 </strong> 。</p></td>
</tr>
</tbody>
</table>

 

## 其他迁移任务


你还可以执行其他迁移任务，例如重新配置终结点，以及打开使用运行 App-v 5.1 客户端的计算机上的早期版本创建的程序包。 以下链接提供了有关执行这些任务的详细信息。

[如何为特定计算机上的所有用户将 App-V 4.6 程序包中的扩展点迁移到转换后的 App-V 5.1 程序包](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-51-package-for-all-users-on-a-specific-computer.md)

[如何为特定用户将 App-V 4.6 程序包中的扩展点迁移到 App-V 5.1](how-to-migrate-extension-points-from-an-app-v-46-package-to-app-v-51-for-a-specific-user.md)

[如何为特定计算机上的所有用户将 App-V 5.1 程序包中的扩展点还原到 App-V 4.6 程序包](how-to-revert-extension-points-from-an-app-v-51-package-to-an-app-v-46-package-for-all-users-on-a-specific-computer.md)

[如何为特定用户将 App-V 5.1 程序包中的扩展点还原到 App-V 4.6 程序包](how-to-revert-extension-points-from-an-app-v-51-package-to-an-app-v-46-package-for-a-specific-user.md)







## 用于执行 App-v 迁移任务的其他资源


[App-V 5.1 的操作](operations-for-app-v-51.md)

[简化的 Microsoft App-V 5.1 管理服务器升级过程](https://go.microsoft.com/fwlink/p/?LinkId=786330)

 

 





