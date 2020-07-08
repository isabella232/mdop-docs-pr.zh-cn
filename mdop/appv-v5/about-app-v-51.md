---
title: 关于 App-V 5.1
description: 关于 App-V 5.1
author: dansimp
ms.assetid: 35bc9908-d502-4a9c-873f-8ee17b6d9d74
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 4f2404dcd431b32f5d9a4ae7c49f1e376979e04e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798673"
---
# 关于 App-V 5.1


使用以下部分查看有关适用于应用程序虚拟化（App-v）5.1 的重大更改的信息：

[App-v 5.1 软件必备条件和支持的配置](#bkmk-51-prereq-configs)

[迁移到 App-v 5。1](#bkmk-migrate-to-51)

[App-v 5.1 中的新增功能](#bkmk-whatsnew)

[适用于 Windows 10 的 app-v 支持](#bkmk-win10support)

[App-v 管理控制台更改](#bkmk-mgmtconsole)

[排序器改进](#bkmk-seqimprove)

[程序包转换器改进](#bkmk-pkgconvimprove)

[对单个事件触发器的多个脚本的支持](#bkmk-supmultscripts)

[已将安装文件夹的硬编码路径重定向到虚拟文件系统根目录](#bkmk-hardcodepath)

## <a href="" id="bkmk-51-prereq-configs"></a>App-v 5.1 软件必备条件和支持的配置


请参阅适用于 app-v 5.1 软件必备条件和支持的配置的以下链接。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">链接到先决条件和受支持的配置</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="app-v-51-prerequisites.md" data-raw-source="[App-V 5.1 Prerequisites](app-v-51-prerequisites.md)">App-V 5.1 先决条件</a></p></td>
<td align="left"><p>在启动 app-v 5.1 安装之前必须安装的必备软件</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="app-v-51-supported-configurations.md" data-raw-source="[App-V 5.1 Supported Configurations](app-v-51-supported-configurations.md)">App-V 5.1 支持的配置</a></p></td>
<td align="left"><p>支持的操作系统和适用于 app-v Server、Sequencer 和客户端组件的硬件要求</p></td>
</tr>
</tbody>
</table>



**支持将 Configuration Manager 与 app-v 配合使用：** App-v 5.1 支持 System Center 2012 R2 Configuration Manager SP1。 有关将 app-v 环境与 Configuration manager 和配置管理器集成的信息，请参阅[规划与 Configuration manager 的 App-v 集成](https://technet.microsoft.com/library/jj822982.aspx)。

## <a href="" id="bkmk-migrate-to-51"></a>迁移到 App-v 5。1


使用以下信息从早期版本升级到 app-v 5.1。 有关详细信息，请参阅[从早期版本迁移到 app-v 5.1](migrating-to-app-v-51-from-a-previous-version.md) 。

### 开始升级之前

在开始升级之前查看以下信息：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">升级前要查看的项目</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>要升级的组件（按任何顺序）</p></td>
<td align="left"><ol>
<li><p>App-v 服务器</p></li>
<li><p>序列</p></li>
<li><p>App-v 客户端或 App-v 远程桌面服务（RDS）客户端</p></li>
</ol>
<div class="alert">
<strong>注意</strong><br/><p>在 app-v 5.0 SP2 之前，客户端管理用户界面（UI）由 App-v 客户端安装提供。 对于 app-v 5.0 SP2 安装（或更高版本），你可以通过从 <a href="https://www.microsoft.com/download/details.aspx?id=41186" data-raw-source="[Application Virtualization 5.0 Client UI Application](https://www.microsoft.com/download/details.aspx?id=41186)"> Application Virtualization 5.0 客户端 Ui 应用程序下载来使用客户端管理 UI </a> 。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>从 App-v 4 升级</p></td>
<td align="left"><p>必须首先升级到 app-v 5.0。 您不能直接从 app-v 4-v 升级到 app-v 5.1。 有关详细信息，请参阅：</p>
<ul>
<li><p>关于 App-v 5.0 中的 "App-v 4.6 和 App-v 5.0 之间的差异" <a href="about-app-v-50.md" data-raw-source="[About App-V 5.0](about-app-v-50.md)"></a></p></li>
<li><p><a href="planning-for-migrating-from-a-previous-version-of-app-v.md" data-raw-source="[Planning for Migrating from a Previous Version of App-V](planning-for-migrating-from-a-previous-version-of-app-v.md)">计划从以前版本的 App-V 迁移</a></p></li>
</ul>
<p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>从 App-v 5.0 或更高版本升级</p></td>
<td align="left"><p>你可以直接从以下任何版本升级到 app-v 5.1：</p>
<ul>
<li><p>App-v 5。0</p></li>
<li><p>App-v 5.0 SP1</p></li>
<li><p>App-v 5.0 SP2</p></li>
<li><p>App-v 5.0 SP3</p></li>
</ul>
<p>若要升级到 app-v 5.1，请按照本主题其余部分中的步骤操作。</p>
<p>程序包和连接组将继续使用 app-v 5.1，就像它们目前一样。</p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-steps-upgrd-infrastruc"></a>升级 app-v 基础结构的步骤

完成以下步骤，将 app-v 基础结构的每个组件升级到 app-v 5.1。 以下顺序只是一个建议;你可以按任意顺序升级组件。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">步骤</th>
<th align="left">有关详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>步骤1：升级 app-v 服务器。</p>
<div class="alert">
<strong>注意</strong><br/><p>如果未使用 App-v 服务器，请跳过此步骤，然后转到下一步。</p>
</div>
<div>

</div></td>
<td align="left"><p>请按照下列步骤进行操作：</p>
<ol>
<li><p>根据用于升级管理数据库和/或报告数据库的方法，执行下列操作之一：</p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">数据库升级方法</th>
<th align="left">步骤</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows Installer</p></td>
<td align="left"><p>跳过此步骤并转到步骤 2 "如果要升级 app-v 服务器 ..."</p></td>
</tr>
<tr class="even">
<td align="left"><p>SQL 脚本</p></td>
<td align="left"><p>按照 <a href="how-to-deploy-the-app-v-databases-by-using-sql-scripts.md" data-raw-source="[How to Deploy the App-V Databases by Using SQL Scripts](how-to-deploy-the-app-v-databases-by-using-sql-scripts.md)"> 如何使用 SQL 脚本部署 App-v 数据库中的步骤操作 </a> 。</p></td>
</tr>
</tbody>
</table>
<li><p>如果你要从 App-v 5.0 SP1 修补程序包3或更高版本升级 app-v 服务器，请完成 <a href="check-reg-key-svr.md" data-raw-source="[Check registry keys after installing the App-V 5.0 SP3 Server](check-reg-key-svr.md)"> 安装 app-v 5.0 SP3 服务器后检查注册表项部分中的步骤 </a> 。</p></li>
<li><p>按照 <a href="how-to-deploy-the-app-v-51-server.md" data-raw-source="[How to Deploy the App-V 5.1 Server](how-to-deploy-the-app-v-51-server.md)"> 如何部署 app-v 5.1 服务器中的步骤操作</a></p></li>
<p> </p></li>
</ol></td>
</tr>
<tr class="even">
<td align="left"><p>步骤2：升级 app-v Sequencer。</p></td>
<td align="left"><p>请参阅 <a href="how-to-install-the-sequencer-beta-gb18030.md" data-raw-source="[How to Install the Sequencer](how-to-install-the-sequencer-beta-gb18030.md)"> 如何安装 Sequencer </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>步骤3：升级 App-v 客户端或 App-v RDS 客户端。</p></td>
<td align="left"><p>请参阅 <a href="how-to-deploy-the-app-v-client-gb18030.md" data-raw-source="[How to Deploy the App-V Client](how-to-deploy-the-app-v-client-gb18030.md)"> 如何部署 App-v 客户端 </a> 。</p></td>
</tr>
</tbody>
</table>



### 转换使用早期版本的 App-v 创建的程序包

使用程序包转换器实用工具升级使用 app-v 5.0 之前的 app-v 版本创建的虚拟应用程序包。 程序包转换器使用 PowerShell 转换程序包，如果你有多个需要转换的程序包，则可以帮助自动处理该进程。

**注意**  
App-v 5.1 程序包与 App-v 5.0 程序包完全相同。 版本之间的程序包格式没有任何变化，因此无需将 app-v 5.0 程序包转换为 App-v 5.1 程序包。



## <a href="" id="bkmk-whatsnew"></a>App-v 5.1 中的新增功能


这些部分适用于已熟悉 app-v 的用户，并且希望知道 App-v 5.1 中的更改。 如果你还不熟悉 App-v，应首先阅读适用[于 app-v 5.1 的规划](planning-for-app-v-51.md)。

### <a href="" id="bkmk-win10support"></a>适用于 Windows 10 的 app-v 支持

下表列出了适用于 app-v 的 Windows 10 支持。 在 app-v 5.1 之前的 app-v 版本中不支持 Windows 10。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">组件</th>
<th align="left">App-V 5.1</th>
<th align="left">App-v 5。0</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-v 客户端</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>否</p></td>
</tr>
<tr class="even">
<td align="left"><p>App-v RDS 客户端</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>否</p></td>
</tr>
<tr class="odd">
<td align="left"><p>App-v 排序器</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>否</p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-mgmtconsole"></a>App-v 管理控制台更改

此部分比较了 app-v 管理控制台的当前和以前的功能。

### 已不再需要 Silverlight

管理控制台 UI 不再需要 Silverlight。 5.1 管理控制台建立在 HTML5 和 Javascript 上。

### 通知和消息分别显示在对话框中

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
<td align="left"><p><strong>邮件指示器的数量：</strong></p>
<p>在 App-v 管理控制台的标题栏上，数字现在显示在标记图标旁边，用于指示等待阅读的邮件数。</p></td>
<td align="left"><p>一次只能看到一条消息或错误，并且无法确定有多少封邮件。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>邮件外观：</strong></p>
<ul>
<li><p>需要用户输入的消息会显示在你正在查看的当前页面顶部的单独对话框中，并且需要响应才能消除它们。</p></li>
<li><p>邮件和错误显示在列表中，一个在下一个列表中。</p></li>
</ul></td>
<td align="left"><p>一次只能看到一条消息或错误消息。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>关闭邮件：</strong></p>
<p>使用 " <strong> 全部消除 </strong> " 链接一次消除所有消息和错误，或一次消除一个。</p></td>
<td align="left"><p>一次只能消除一个消息和错误。</p></td>
</tr>
</tbody>
</table>



### 现在，控制台页面是单独的 Url

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
<td align="left"><p>控制台中的每个页面都有一个不同的 URL，使你能够将特定页面做成书签，以便将来快速访问。</p>
<p>某些 Url 中显示的数字表示特定的程序包。 这些号码是唯一的。</p></td>
<td align="left"><p>通过同一 URL 访问所有控制台页面。</p></td>
</tr>
</tbody>
</table>



### "新建、单独的连接组" 页面和菜单选项

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
<td align="left"><p>"连接组" 页面现在是主菜单的一部分，与 "程序包" 页面位于同一级别。</p></td>
<td align="left"><p>若要打开 "连接组" 页面，请浏览 "程序包" 页面。</p></td>
</tr>
</tbody>
</table>



### 程序包的菜单选项已更改

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
<td align="left"><p>以下选项现在显示在 "程序包" 页面底部：</p>
<ul>
<li><p>添加或升级</p></li>
<li><p>发布</p></li>
<li><p>发布</p></li>
<li><p>删除</p></li>
</ul>
<p>右键单击某个程序包以打开下拉上下文菜单时，仍将显示以下选项：</p>
<ul>
<li><p>发布</p></li>
<li><p>发布</p></li>
<li><p>编辑广告访问</p></li>
<li><p>编辑部署配置</p></li>
<li><p>从传输部署配置 .。。</p></li>
<li><p>转移访问和配置来自 .。。</p></li>
<li><p>删除</p></li>
</ul>
<p>单击 " <strong> 删除 </strong> " 以删除程序包时，将打开一个对话框，要求您确认是否要删除该程序包。</p></td>
<td align="left"><p>" <strong> 添加" 或 "升级" </strong> 选项是 "程序包" 页面右上角的一个按钮。</p>
<p><strong> </strong> <strong> </strong> <strong> </strong> 仅当右键单击 "程序包" 列表中的程序包名称时，"发布"、"取消发布" 和 "删除" 选项才可用。</p></td>
</tr>
<tr class="even">
<td align="left"><p>以下程序包操作现在是每个程序包的程序包详细信息页面上的按钮：</p>
<ul>
<li><p>"传送" （具有下列选项的下拉菜单）：</p>
<ul>
<li><p>从传输部署配置 .。。</p></li>
<li><p>转移访问和配置来自 .。。</p></li>
</ul></li>
<li><p>编辑（连接组和 AD 访问）</p></li>
<li><p>发布</p></li>
<li><p>删除</p></li>
<li><p>编辑默认配置</p></li>
</ul></td>
<td align="left"><p>仅当右键单击 "程序包" 列表中的程序包名称时，这些程序包选项才可用。</p></td>
</tr>
</tbody>
</table>



### 左窗格中的图标具有新的颜色和文本

左窗格中图标的颜色已更改，添加了文本，使图标与其他 Microsoft 产品保持一致。

### 概述页面已删除

在管理控制台的左窗格中，已删除 "概述" 菜单选项及其关联的概述页面。

### <a href="" id="bkmk-seqimprove"></a>排序器改进

在 app-v 5.1 Sequencer 中对程序包编辑器进行了以下改进。

### 导入和导出清单文件

您可以导入和导出 AppxManifest.xml 文件。 若要导出清单文件，请选择 "**高级**" 选项卡，然后在 "清单文件" 框中，单击 "**导出 ...**"。你可以对清单文件进行更改，例如删除外壳扩展或编辑文件类型关联。

在进行更改后，单击 "**导入 ...** "，然后选择所编辑的文件。 成功将其导入后，清单文件将立即在程序包编辑器中更新。

**注意**  
导入文件时，将根据 XML 架构验证你的更改。 如果该文件无效，您将收到错误。 请注意，可以导入根据 XML 架构验证的文件，但由于其他原因，仍可能无法运行。



### 将 Windows 10 添加到操作系统列表

在 "部署" 选项卡中，已将 Windows 10 32 位和 Windows 10-64 位添加到你可以对其进行序列化程序包的操作系统列表。 如果你选择**任何操作系统**，Windows 10 将自动包含在序列化程序包将支持的操作系统中。

### 当前路径显示在虚拟注册表编辑器的底部

在 "虚拟注册表" 选项卡中，路径现在显示在虚拟注册表编辑器的底部，这使你可以确定当前所选的项。 以前，您必须滚动浏览注册表树才能找到当前所选的项。

### <a href="" id="combined--find-and-replace--dialog-box-and-shortcut-keys-added-in-virtual-registry-editor"></a>合并的 "查找和替换" 对话框和 "虚拟注册表编辑器" 中添加的快捷键

在虚拟注册表编辑器中，为 "查找" 选项（Ctrl + F）添加了快捷键，并添加了一个对话框，其中合并了 "查找" 和 "替换" 任务，使你可以查找和替换值和数据。 若要访问 "组合" 对话框，请选择一个键，然后执行下列操作之一：

-   按**Ctrl + H**

-   右键单击某个键，然后选择 "**替换**"。

-   选择 "**查看** &gt; **虚拟注册表** &gt; **替换**"。

以前，"替换" 对话框不存在，您必须手动进行更改。

### 成功重命名注册表项和程序包文件

你可以重命名虚拟注册表项和文件，但不会遇到 Sequencer 问题。 以前，如果尝试重命名密钥，Sequencer 将停止工作。

### 导入和导出虚拟注册表项

你可以导入和导出虚拟注册表项。 若要导入密钥，请右键单击要在其下导入键的节点，导航到要导入的键，然后单击 "**导入**"。 若要导出密钥，请右键单击该注册表项，然后选择 "**导出**"。

### 将目录导入到虚拟文件系统中

你可以将目录导入到 VFS。 若要导入目录，请单击 "**程序包文件**" 选项卡，然后单击 "**查看** &gt; **虚拟文件系统** &gt; **导入目录**"。 如果你尝试导入的目录包含 VFS 中已存在的文件，则导入将失败，并显示说明性消息。 在 App-v 5.1 之前，你无法导入目录。

### 导入或导出 VFS 文件，而无需先删除它，然后再将其添加回程序包

你可以将文件导入或导出 VFS 中的文件，而无需删除该文件，然后再将其添加回程序包。 例如，你可以使用此功能将更改日志导出到本地驱动器，使用外部编辑器编辑文件，然后将该文件重新导入到 VFS。

若要导出文件，请选择 "**程序包文件**" 选项卡，右键单击 "VFS" 中的文件，单击 "**导出**"，然后选择可从中进行编辑的导出位置。

若要导入文件，请选择 "**程序包文件**" 选项卡，然后右键单击已导出的文件。 浏览到您编辑的文件，然后单击 "**导入**"。 导入的文件将覆盖现有文件。

导入文件后，必须通过单击 "**文件**保存" 来保存程序包 &gt; **Save**。

### 已移动用于添加程序包文件的菜单

已移动用于添加程序包文件的菜单选项。 若要查找 "添加" 选项，请选择 "**程序包文件**" 选项卡，然后单击 "**查看** &gt; **虚拟文件系统** &gt; **添加文件**"。 以前，右键单击了 VFS 节点下的文件夹，然后选择 "**添加文件**"。

### 默认情况下，虚拟注册表节点会展开计算机和用户配置单元

当您打开虚拟注册表时，计算机和用户配置单元显示在顶级注册表节点下方。 以前，您必须展开 "注册表" 节点以显示下面的配置单元。

### 启用或禁用浏览器帮助程序对象

你可以通过在 Sequencer 用户界面的 "高级" 选项卡上选中新的复选框 "启用浏览器帮助程序对象" 来启用或禁用浏览器帮助程序对象。 如果浏览器帮助程序对象：

-   存在于程序包中，并且已启用，则默认情况下复选框处于选中状态。

-   存在于程序包中，并且已被禁用，则默认情况下复选框已清除。

-   存在于程序包中，并且启用了一个或多个，但禁用了一个或多个，则默认情况下，复选框设置为 "未确定"。

-   程序包中不存在此复选框，则该复选框处于禁用状态。

### <a href="" id="bkmk-pkgconvimprove"></a>程序包转换器改进

现在，你可以使用程序包转换器转换包含脚本的 app-v 4.6 程序包，并且来自源 osd 文件的注册表信息和脚本现已包含在程序包转换器输出中。

有关详细信息（包括示例），请参阅[从早期版本迁移到 app-v 5.1](migrating-to-app-v-51-from-a-previous-version.md)。

### <a href="" id="bkmk-supmultscripts"></a>对单个事件触发器的多个脚本的支持

App-v 5.1 支持在应用 V 程序包的单个事件触发器上使用多个脚本，包括从 App-v 4.6 转换到 App-v 5.0 或更高版本的程序包。 若要启用多个脚本的使用，App-v 5.1 使用一个名为 ScriptRunner.exe 的脚本启动器应用程序，该应用程序作为 App-v 客户端安装的一部分安装。

有关详细信息，包括事件触发器列表和运行脚本的上下文，请参阅[关于应用-V 5.1 动态配置](about-app-v-51-dynamic-configuration.md)中的脚本部分。

### <a href="" id="bkmk-hardcodepath"></a>已将安装文件夹的硬编码路径重定向到虚拟文件系统根目录

将程序包从 App-v 4.6 转换为5.1 时，App-v 5.1 程序包可以访问创建4.6 程序包时需要使用的硬编码的驱动器。 驱动器号将是您选择的驱动器作为4.6 排序计算机上的安装驱动器。 （默认驱动器号为 Q:\\.）

以前，无法识别4.6 根文件夹，并且无法通过 app-v 5.0 程序包访问该文件夹。 App-v 5.1 程序包可以通过其完整路径访问硬编码文件，也可以通过编程方式枚举 App-v 4.6 安装根下的文件。

**技术详细信息：** App-v 5.1 程序包转换器将在 Filesystem 元素的 FilesystemMetadata.xml 文件中保存 App-v 4.6 安装根文件夹和短文件夹名称。 当 App-v 5.1 客户端创建虚拟进程时，它会将请求从 App-v 4.6 安装根映射到虚拟文件系统根目录。

## 如何获取 MDOP 技术


App-v 是 Microsoft 桌面优化包（MDOP）的一部分。 MDOP 是 Microsoft 软件保障的一部分。 有关 Microsoft 软件保证和获取 MDOP 的详细信息，请参阅[如何获取 mdop](https://go.microsoft.com/fwlink/?LinkId=322049)。






## 相关主题


[App-V 5.1 发行说明](release-notes-for-app-v-51.md)









