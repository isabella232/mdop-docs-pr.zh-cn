---
title: 应用程序发布和客户端交互
description: 应用程序发布和客户端交互
author: dansimp
ms.assetid: 36a4bf6f-a917-41a6-9856-6248686df352
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 69fcf119faaf35e53ae36f386bcb3480e2ee3b0e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798619"
---
# 应用程序发布和客户端交互


本文提供有关常见应用 V 客户端操作及其与本地操作系统的集成的技术信息。

-   [由 Sequencer 创建的 app-v 包文件](#bkmk-appv-pkg-files-list)

-   [Appv 文件中有哪些内容？](#bkmk-appv-file-contents)

-   [App-v 客户端数据存储位置](#bkmk-files-data-storage)

-   [程序包注册表](#bkmk-pkg-registry)

-   [App-v 包存储行为](#bkmk-pkg-store-behavior)

-   [漫游注册表和数据](#bkmk-roaming-reg-data)

-   [App-v 客户端应用程序生命周期管理](#bkmk-clt-app-lifecycle)

-   [App-v 程序包的集成](#bkmk-integr-appv-pkgs)

-   [动态配置处理](#bkmk-dynamic-config)

-   [并行程序集](#bkmk-sidebyside-assemblies)

-   [客户端日志记录](#bkmk-client-logging)

有关其他参考信息，请参阅[Microsoft Application Virtualization （app-v）文档资源下载页面](https://www.microsoft.com/download/details.aspx?id=27760)。

## <a href="" id="bkmk-appv-pkg-files-list"></a>由 Sequencer 创建的 app-v 包文件


排序器创建 app-v 包并生成一个虚拟化的应用程序。 排序过程将创建以下文件：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">文件</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>appv</p></td>
<td align="left"><ul>
<li><p>主程序包文件，其中包含来自排序过程的已捕获资源和状态信息。</p></li>
<li><p>程序包文件、发布信息和注册表的体系结构，可标记化形式可在传递时重新应用到计算机和特定用户。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>.MSI</p></td>
<td align="left"><p>可用于手动部署 appv 文件或使用第三方部署平台的可执行部署包装程序。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>_DeploymentConfig.XML</p></td>
<td align="left"><p>用于自定义程序包中的所有应用程序的默认发布参数的文件，该程序包中将全局部署到运行 App-v 客户端的计算机上的所有用户。</p></td>
</tr>
<tr class="even">
<td align="left"><p>_UserConfig.XML</p></td>
<td align="left"><p>用于自定义程序包中的所有应用程序的发布参数的文件，该程序包中已部署到运行 App-v 客户端的计算机上的特定用户。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Report.xml</p></td>
<td align="left"><p>排序过程中产生的消息摘要，包括省略的驱动程序、文件和注册表位置。</p></td>
</tr>
<tr class="even">
<td align="left"><p>.CAB</p></td>
<td align="left"><p><em>可选： </em> 用于自动重建以前已排序的虚拟应用程序包的程序包加速器文件。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>.appvt</p></td>
<td align="left"><p><em>可选： </em> sequencer 模板文件，用于保留常用的 sequencer 设置。</p></td>
</tr>
</tbody>
</table>

 

有关顺序的信息，请参阅[应用程序虚拟化排序指南](https://go.microsoft.com/fwlink/?LinkID=269810)。

## <a href="" id="bkmk-appv-file-contents"></a>Appv 文件中有哪些内容？


Appv 文件是一个容器，它将 XML 和非 XML 文件一起存储在单个实体中。 此文件是从 AppX 格式生成的，该格式基于开放式打包约定（OPC）标准。

若要查看 appv 文件内容，请制作程序包的副本，然后将复制的文件重命名为 ZIP 扩展。

Appv 文件包含以下文件夹和文件，这些文件夹和文件是在创建和发布虚拟应用程序时使用的：

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名称</th>
<th align="left">类型</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>根</p></td>
<td align="left"><p>文件夹</p></td>
<td align="left"><p>包含在排序期间捕获的虚拟化应用程序的文件系统的目录。</p></td>
</tr>
<tr class="even">
<td align="left"><p>[Content_Types] .xml</p></td>
<td align="left"><p>XML 文件</p></td>
<td align="left"><p>Appv 文件（如 .DLL、EXE、BIN）中的核心内容类型列表。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>AppxBlockMap.xml</p></td>
<td align="left"><p>XML 文件</p></td>
<td align="left"><p>Appv 文件的布局，该布局使用 File、Block 和 BlockMap 元素，这些元素可启用 App-v 包中文件的位置和验证。</p></td>
</tr>
<tr class="even">
<td align="left"><p>AppxManifest.xml</p></td>
<td align="left"><p>XML 文件</p></td>
<td align="left"><p>程序包的元数据，其中包含添加、发布和启动程序包所需的信息。 包括扩展点（文件类型关联和快捷方式）以及与该包关联的名称和 Guid。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>FilesystemMetadata.xml</p></td>
<td align="left"><p>XML 文件</p></td>
<td align="left"><p>排序期间捕获的文件的列表，包括属性（例如，目录、文件、不透明目录、空目录以及长名称和短名称）。</p></td>
</tr>
<tr class="even">
<td align="left"><p>PackageHistory.xml</p></td>
<td align="left"><p>XML 文件</p></td>
<td align="left"><p>有关排序计算机（操作系统版本、Internet Explorer 版本、.Net Framework 版本）和进程（升级、程序包版本）的信息。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>注册表 .dat</p></td>
<td align="left"><p>DAT 文件</p></td>
<td align="left"><p>程序包的排序过程中捕获的注册表项和值。</p></td>
</tr>
<tr class="even">
<td align="left"><p>StreamMap.xml</p></td>
<td align="left"><p>XML 文件</p></td>
<td align="left"><p>主功能块和发布功能块的文件列表。 发布功能块包含用于发布程序包的 .ICO 文件和所需的文件（EXE 和 DLL）部分。 当存在时，主要功能块包括已针对排序过程中的流式处理进行了优化的文件。</p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-files-data-storage"></a>App-v 客户端数据存储位置


App-v 客户端执行任务以确保虚拟应用程序正常运行，例如本地安装的应用程序。 打开和运行虚拟应用程序的过程需要从虚拟文件系统和注册表映射，以确保应用程序具有用户期望的传统应用程序所必需的组件。 本部分介绍运行虚拟应用程序所需的资源，并列出应用 V 存储资源的位置。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名称</th>
<th align="left">位置</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>程序包存储</p></td>
<td align="left"><p>%ProgramData%\App-V</p></td>
<td align="left"><p>只读程序包文件的默认位置</p></td>
</tr>
<tr class="even">
<td align="left"><p>计算机目录</p></td>
<td align="left"><p>%ProgramData%\Microsoft\AppV\Client\Catalog</p></td>
<td align="left"><p>包含每台计算机配置文档</p></td>
</tr>
<tr class="odd">
<td align="left"><p>用户目录</p></td>
<td align="left"><p>%AppData%\Microsoft\AppV\Client\Catalog</p></td>
<td align="left"><p>包含每用户配置文档</p></td>
</tr>
<tr class="even">
<td align="left"><p>快捷方式备份</p></td>
<td align="left"><p>%AppData%\Microsoft\AppV\Client\Integration\ShortCutBackups</p></td>
<td align="left"><p>存储在程序包取消发布时启用还原的以前的集成点</p></td>
</tr>
<tr class="odd">
<td align="left"><p>写入时复制（牛）漫游</p></td>
<td align="left"><p>%AppData%\Microsoft\AppV\Client\VFS</p></td>
<td align="left"><p>程序包修改的可写入漫游位置</p></td>
</tr>
<tr class="even">
<td align="left"><p>写入时复制（牛）局部</p></td>
<td align="left"><p>%LocalAppData%\Microsoft\AppV\Client\VFS</p></td>
<td align="left"><p>程序包修改的可写非漫游位置</p></td>
</tr>
<tr class="odd">
<td align="left"><p>计算机注册表</p></td>
<td align="left"><p>HKLM\Software\Microsoft\AppV</p></td>
<td align="left"><p>包含程序包状态信息，包括计算机或全局发布的程序包（计算机配置单元）的 VReg</p></td>
</tr>
<tr class="even">
<td align="left"><p>用户注册表</p></td>
<td align="left"><p>HKCU\Software\Microsoft\AppV</p></td>
<td align="left"><p>包含用户程序包状态信息，包括 VReg</p></td>
</tr>
<tr class="odd">
<td align="left"><p>用户注册表类</p></td>
<td align="left"><p>HKCU\Software\Classes\AppV</p></td>
<td align="left"><p>包含其他用户程序包状态信息</p></td>
</tr>
</tbody>
</table>

 

表格的其他详细信息在以下部分以及整个文档中提供。

### 程序包存储

App-v 客户端管理程序包存储中挂载的应用程序资源。 此默认存储位置为 `%ProgramData%\App-V` ，但你可以使用 PowerShell 命令在安装过程中或之后配置它 `Set-AppVClientConfiguration` ，这将修改本地注册表（ `PackageInstallationRoot` 注册表项下的值 `HKLM\Software\Microsoft\AppV\Client\Streaming` ）。 程序包存储必须位于客户端操作系统上的本地路径中。 各个程序包存储在程序包存储区中，位于名为 "程序包 GUID" 和 "版本 GUID" 的子目录中。

特定应用程序的路径示例：

``` syntax
C:\ProgramData\App-V\PackGUID\VersionGUID
```

若要在安装过程中更改程序包存储区的默认位置，请参阅[如何部署 App-v 客户端](how-to-deploy-the-app-v-client-51gb18030.md)。

### 共享内容存储

如果在 "共享内容存储" 模式下配置了 app-v 客户端，则当出现流错误时，将不会向磁盘写入任何数据，这意味着程序包需要最少的本地磁盘空间（发布数据）。 在 VDI 环境中使用较少的磁盘空间非常可取，在这种情况下，本地存储可以受到限制，并且从高性能的网络位置（如 SAN）流处理应用程序更可取。 有关共享内容存储模式的详细信息，请参阅 <https://go.microsoft.com/fwlink/p/?LinkId=392750> 。

**注意** 计算机和程序包存储必须位于本地驱动器上，即使你使用的是 App-v 客户端的共享内容存储配置也是如此。

 

### 程序包目录

App-v 客户端管理以下两个基于文件的位置：

-   **目录（用户和计算机）。**

-   **注册表位置**-取决于程序包的目标发布方式。 计算机的目录（数据存储）和每个单独用户的目录。 计算机目录存储适用于所有用户或任何用户的全局信息，用户目录存储适用于特定用户的信息。 目录是动态配置和清单文件的集合;每个程序包版本的文件和注册表都有离散数据。 

### 计算机目录

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>描述</p></td>
<td align="left"><p>在添加和发布程序包时，存储计算机上用户可用的程序包文档。 但是，如果程序包在发布时是 "全局" 的，则所有用户都可以使用这些集成。</p>
<p>如果程序包是非全局的，则仅为特定用户发布集成，但仍有对客户端计算机上的任何人（例如，程序包目录位于共享磁盘位置）所修改和可见的全局资源。</p>
<p>如果程序包对计算机上的用户可用（全局或非全局），则清单存储在计算机目录中。 全局发布程序包时，有一个动态配置文件，存储在计算机目录中;因此，根据计算机目录中是否存在策略文件（UserDeploymentConfiguration 文件）确定程序包是否为全局程序包。</p></td>
</tr>
<tr class="even">
<td align="left"><p>默认存储位置</p></td>
<td align="left"><p><code>%programdata%\Microsoft\AppV\Client\Catalog&lt;/code&gt;</p>
<p>此位置与程序包存储位置不同。 程序包存储是程序包文件的黄金或 pristine 副本。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>计算机目录中的文件</p></td>
<td align="left"><ul>
<li><p>Manifest.xml</p></li>
<li><p>DeploymentConfiguration.xml</p></li>
<li><p>UserManifest.xml （全局发布的程序包）</p></li>
<li><p>UserDeploymentConfiguration.xml （全局发布的程序包）</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>其他计算机目录位置，在程序包是连接组的一部分时使用</p></td>
<td align="left"><p>以下位置是除上述特定程序包位置之外的其他位置：</p>
<p><code>%programdata%\Microsoft\AppV\Client\Catalog\PackageGroups\ConGroupGUID\ConGroupVerGUID</code></p></td>
</tr>
<tr class="odd">
<td align="left"><p>当程序包是连接组的一部分时计算机目录中的其他文件</p></td>
<td align="left"><ul>
<li><p>PackageGroupDescriptor.xml</p></li>
<li><p>UserPackageGroupDescriptor.xml （全局发布的连接组）</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

### 用户目录

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>描述</p></td>
<td align="left"><p>在发布过程中创建。 包含用于发布程序包的信息，还可在启动时使用，以确保将程序包预配到特定用户。 在漫游位置创建，并且包括特定于用户的发布信息。</p>
<p>为用户发布程序包时，策略文件存储在用户目录中。 同时，清单的副本也存储在用户目录中。 删除用户的程序包权限后，将从用户目录中删除相关的程序包文件。 查看用户目录时，管理员可以查看动态配置文件的存在，这表示该程序包有权使用该用户。</p>
<p>对于漫游用户，用户目录需要位于漫游位置或共享位置，以便在默认情况下保留目标用户的旧版 App-v 行为。 权利和政策与用户（而不是计算机）相关联，因此在用户预配后，他们应与用户漫游。</p></td>
</tr>
<tr class="even">
<td align="left"><p>默认存储位置</p></td>
<td align="left"><p><code>appdata\roaming\Microsoft\AppV\Client\Catalog\Packages\PkgGUID\VerGUID</code></p></td>
</tr>
<tr class="odd">
<td align="left"><p>用户目录中的文件</p></td>
<td align="left"><ul>
<li><p>UserManifest.xml</p></li>
<li><p>DynamicConfiguration.xml 或 UserDeploymentConfiguration.xml</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>其他用户目录位置，在程序包是连接组的一部分时使用</p></td>
<td align="left"><p>以下位置是除上述特定程序包位置之外的其他位置：</p>
<p><code>appdata\roaming\Microsoft\AppV\Client\Catalog\PackageGroups\PkgGroupGUID\PkgGroupVerGUID</code></p></td>
</tr>
<tr class="odd">
<td align="left"><p>当程序包是连接组的一部分时计算机目录中的其他文件</p></td>
<td align="left"><p><code>UserPackageGroupDescriptor.xml</code></p></td>
</tr>
</tbody>
</table>

 

### 快捷方式备份

在发布过程中，App-v 客户端将备份任何快捷方式和集成点到 `%AppData%\Microsoft\AppV\Client\Integration\ShortCutBackups.` 此备份后，在取消发布程序包时，可将这些集成点还原到以前的版本。

### 写入文件时复制

程序包存储包含已从发布服务器流出的程序包文件的 pristine 副本。 在应用 V 应用程序的正常运行期间，用户或服务可能需要对文件进行更改。 这些更改不会在程序包存储中进行，以便保留你修复应用程序的能力，从而删除这些更改。 这些位置称为 "写入时复制（牛）"，支持漫游和非漫游位置。 存储修改的位置取决于应用程序在本机体验中写入更改的编程位置。

### 牛漫游

上面所述的牛漫游位置存储指向典型% AppData% location 或 \\Users\\{username}\\AppData\\Roaming 位置的文件和目录的更改。 然后，这些目录和文件将基于操作系统设置进行漫游。

### 牛局部

牛本地位置类似于漫游位置，但目录和文件不会漫游到其他计算机，即使已配置漫游支持也是如此。 以上所述的牛本地位置存储适用于典型窗口的更改，而不是% AppData% location。 列出的目录将有所不同，但任何典型的 Windows 位置（例如，通用 AppData 和常见 AppDataS）都有两个位置。 当虚拟服务请求从已登录用户的其他提升的用户请求更改时， **S**表示受限制的位置。 非**S**位置存储基于用户的更改。

## <a href="" id="bkmk-pkg-registry"></a>程序包注册表


在应用程序可以访问程序包注册表数据之前，app-v 客户端必须使程序包注册表数据可用于应用程序。 App-v 客户端将实际注册表用作所有注册表数据的后备应用商店。

将新程序包添加到 App-v 客户端时，注册表的副本。已在创建来自程序包的 DAT 文件 `%ProgramData%\Microsoft\AppV\Client\VREG\{Version GUID}.dat` 。 文件的名称是带有的版本 GUID。DAT 扩展。 创建此副本的原因是确保程序包中的实际配置单元文件永远不会被使用，这将阻止稍后删除程序包。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>软件包存储中的注册表 dat</strong></p></td>
<td align="left"><p><strong> &gt; </strong></p></td>
<td align="left"><p><strong>%ProgramData%\Microsoft\AppV\Client\Vreg {VersionGuid} .dat</strong></p></td>
</tr>
</tbody>
</table>

 

当程序包中的第一个应用程序在客户端上启动时，客户端阶段或将内容复制到蜂巢文件中，在备用位置重新创建程序包注册表数据 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\AppV\Client\Packages\PackageGuid\Versions\VersionGuid\REGISTRY` 。 暂存的注册表数据具有两种不同类型的计算机数据和用户数据。 在计算机上的所有用户之间共享计算机数据。 将每个用户的用户数据暂存到 userspecific 位置 `HKCU\Software\Microsoft\AppV\Client\Packages\PackageGuid\Registry\User` 。 在软件包删除时，计算机数据最终会被删除，并且用户数据会在用户取消发布操作中被删除。

### 程序包注册表暂存和连接组注册表暂存

当连接组存在时，暂存注册表的以前过程保留为 true，但不需要处理一个配置单元文件。 文件将按照它们在连接组 XML 中的显示顺序进行处理，第一个编写器赢得任何冲突。

暂存的注册表与单个程序包事例中的保留方式相同。 暂存用户注册表数据将保留在连接组中，直到被禁用;在删除连接组时，将删除暂存计算机注册表数据。

### 虚拟注册表

虚拟注册表（VREG）的用途是为应用程序提供程序包注册表和本机注册表的单个合并视图。 它还提供 "写入时复制（牛）" 功能，即从虚拟进程上下文到一个单独的牛位置对注册表所做的任何更改。 这意味着 VREG 必须将最多三个不同的注册表位置合并到一个视图中，具体取决于注册表牛-程序包中的填充位置 &gt; &gt; 。 当对注册表数据发出请求时，它将按顺序找到它，直到找到它所请求的数据。 含义如果在牛位置存储的值不会继续到其他位置，但如果在牛位置没有数据，它将继续到包，然后是本机位置，直到找到相应的数据。

### 注册表位置

应用程序-V 客户端存储注册表信息的两个程序包注册表位置和两个连接组位置，具体取决于程序包是单独发布还是作为连接组的一部分发布。 对于程序包，有三个牛位置，而对于连接组，则由 VREG 创建和管理三个。 程序包和连接组的设置不共享：

**单个程序包 VReg：**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>位置</strong></p></td>
<td align="left"><p><strong>描述</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>牛</strong></p></td>
<td align="left"><ul>
<li><p>计算机 Registry\Client\Packages\PkgGUID\REGISTRY （仅提升进程可以写入）</p></li>
<li><p>用户 Registry\Client\Packages\PkgGUID\REGISTRY （除 Software\Classes 外，在 HKCU 下写入的任何内容</p></li>
<li><p>用户注册表 Classes\Client\Packages\PkgGUID\REGISTRY （HKCU\Software\Classes 为非提升的进程编写和 HKLM）</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>包</strong></p></td>
<td align="left"><ul>
<li><p>机器 Registry\Client\Packages\PkgGUID\Versions\VerGuid\Registry\Machine</p></li>
<li><p>用户注册表 Classes\Client\Packages\PkgGUID\Versions\VerGUID\Registry</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><strong>自己</strong></p></td>
<td align="left"><ul>
<li><p>本机应用程序注册表位置</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

 

**连接组 VReg：**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>位置</strong></p></td>
<td align="left"><p><strong>描述</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>牛</strong></p></td>
<td align="left"><ul>
<li><p>计算机 Registry\Client\PackageGroups\GrpGUID\REGISTRY （仅提升进程可以写入）</p></li>
<li><p>用户 Registry\Client\PackageGroups\GrpGUID\REGISTRY （除 Software\Classes 之外的任何内容写入 HKCU</p></li>
<li><p>用户注册表 Classes\Client\PackageGroups\GrpGUID\REGISTRY</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>包</strong></p></td>
<td align="left"><ul>
<li><p>机器 Registry\Client\PackageGroups\GrpGUID\Versions\VerGUID\REGISTRY</p></li>
<li><p>用户注册表 Classes\Client\PackageGroups\GrpGUID\Versions\VerGUID\REGISTRY</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><strong>自己</strong></p></td>
<td align="left"><ul>
<li><p>本机应用程序注册表位置</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

 

可用于 HKLM 的两个牛位置;提升和未提升的流程。 提升的流程始终会将 HKLM 更改写入 HKLM 下的安全牛中。 非提升的进程始终会将 HKLM 更改写入到 HKCU\\Software\\Classes. 下的非安全牛中。 当应用程序读取来自 HKLM 的更改时，提升的进程将从 HKLM 下的安全牛中读取更改。 非提升的读取，favoring 在不安全的牛中首先进行的更改。

### 传递按键

传递密钥使管理员可以配置某些键，以便只能从本机注册表中读取程序包和牛位置。 传递位置对计算机全局（而非特定于程序包），并且可以通过添加密钥的路径进行配置，该路径应视为传递到**PassThroughPaths**键的**注册 _MULTI \ _SZ**值 `HKLM\Software\Microsoft\AppV\Subsystem\VirtualRegistry` 。 出现在此多字符串值下的任何键（及其子元素）都将被视为传递。

默认情况下，以下位置配置为传递位置：

-   HKEY \ _CURRENT \ _USER \\SOFTWARE\\Classes\\Local Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\AppModel

-   HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Classes\\Local Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\AppModel

-   HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WINEVT

-   HKEY \ _LOCAL \ _MACHINE \\SYSTEM\\CurrentControlSet\\services\\eventlog\\Application

-   HKEY \ _LOCAL \ _MACHINE \\SYSTEM\\CurrentControlSet\\Control\\WMI\\Autologger

-   HKEY \ _CURRENT \ _USER \\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet 设置

-   HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Perflib

-   HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Policies

-   HKEY \ _CURRENT \ _USER \\SOFTWARE\\Policies

传递密钥的目的在于确保虚拟应用程序不会在非虚拟应用程序所需的 VReg 中写入注册表数据，以便成功操作或集成。 策略键确保管理员设置的基于组策略的设置已使用，而不是每个程序包设置。 要与基于 Windows 新式 UI 的应用程序集成，需要 AppModel 参数。 建议管理不要修改任何默认传递密钥，但在某些情况下，根据应用程序行为可能需要添加其他传递密钥。

## <a href="" id="bkmk-pkg-store-behavior"></a>App-v 包存储行为


App-v 5 管理程序包存储，它是存储 appv 文件中展开的资源文件的位置。 默认情况下，此位置存储在%ProgramData%\\App-V 上，并且仅受可用磁盘空间限制的存储功能。 程序包存储由程序包和版本的 Guid 组织，如上一节中所述。

### 添加程序包

在具有 App-v 客户端的计算机上添加 app-v 包时进行暂存。 App-v 客户端提供按需暂存。 在发布或手动加载 AppVClientPackage 期间，数据结构在程序包存储（c:\\programdata\\App-V\\{PkgGUID}\\{VerGUID}）中生成。 在 StreamMap.xml 中定义的发布块中标识的程序包文件将添加到系统以及暂存的顶级文件夹和子文件，以确保在启动时有适当的应用程序资源。

### 安装程序包

可以使用 PowerShell `Mount-AppVClientPackage` 或通过使用**APP-V Client UI**下载程序包来显式加载程序包。 此操作会将整个程序包完全加载到包存储中。

### 流式处理程序包

App-v 客户端可以配置为更改流式处理的默认行为。 所有流策略都存储在以下注册表项下： `HKEY_LOCAL_MAcHINE\Software\Microsoft\AppV\Client\Streaming` 。 使用 PowerShell cmdlet 设置策略 `Set-AppvClientConfiguration` 。 以下政策适用于流式处理：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">策略</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>AllowHighCostLaunch</p></td>
<td align="left"><p>在 Windows 8 及更高版本中，它允许通过3G 和手机网络进行流处理</p></td>
</tr>
<tr class="even">
<td align="left"><p>AutoLoad</p></td>
<td align="left"><p>指定后台加载设置：</p>
<p><strong>0 </strong> - 已禁用</p>
<p><strong>1 </strong> -仅限以前使用的程序包</p>
<p><strong>2 </strong> -所有程序包</p></td>
</tr>
<tr class="odd">
<td align="left"><p>PackageInstallationRoot</p></td>
<td align="left"><p>本地计算机中程序包存储的根文件夹</p></td>
</tr>
<tr class="even">
<td align="left"><p>PackageSourceRoot</p></td>
<td align="left"><p>应从其流入包的根替代</p></td>
</tr>
<tr class="odd">
<td align="left"><p>SharedContentStoreMode</p></td>
<td align="left"><p>支持使用 VDI 方案的共享内容存储</p></td>
</tr>
</tbody>
</table>

 

 

这些设置会影响将 app-v 包资源流式处理到客户端的行为。 默认情况下，app-v 仅下载下载初始发布和主要功能块后所需的资源。 对于必须解释的流式处理程序包，有三个特定行为：

-   后台流

-   优化流

-   流故障

### 后台流

PowerShell cmdlet `Get-AppvClientConfiguration` 可用于确定后台流的当前模式和 AutoLoad 设置，并使用 Cmdlet Set-AppvClientConfiguration 或注册表（HKLM\\SOFTWARE\\Microsoft\\AppV\\ClientStreaming 键）进行修改。 后台流是默认设置，其中 Autoload 设置将设置为下载以前使用的程序包。 基于默认设置（值 = 1）的行为在应用程序启动后，在后台下载 app-v 数据块。 无论是否已启动所有程序包（值 = 2），此设置均可同时禁用（值 = 0）或启用。

### 优化流

在排序期间，可以使用主要功能块配置 app-v 程序包。 此设置允许排序工程师监视特定应用程序或应用程序的启动文件，并在程序包中的任何应用程序首次启动时将 App-v 包中的数据块标记为流式处理。

### 流故障

在任何发布数据和主要功能块的初始流之后，对其他文件的请求将执行流错误。 这些数据块根据需要下载到程序包存储。 这样，用户只需下载程序包的一个小部分，通常就足以启动该程序包并运行正常任务。 当用户启动需要当前不在程序包存储中的数据的操作时，将下载所有其他块。

有关 App-v 程序包流访问的详细信息： <https://go.microsoft.com/fwlink/?LinkId=392770> 。

可在以下位置获取流优化的排序： <https://go.microsoft.com/fwlink/?LinkId=392771> 。

### 程序包升级

App-v 程序包需要在应用程序的整个生命周期内更新。 App-v 程序包升级类似于程序包发布操作，因为每个版本都将在其自己的 PackageRoot 位置中创建： `%ProgramData%\App-V\{PkgGUID}\{newVerGUID}` 。 通过创建来自同一程序包的其他版本的相同和流文件的硬链接来优化升级操作。

### 软件包删除

删除软件包时 App-v 客户端的行为取决于用于删除的方法。 使用 app-v 完整基础结构取消发布应用程序时，将删除用户目录文件（适用于全局发布的应用程序的计算机目录），但保留软件包存储位置和牛位置。 当 PowerShell cmdlet `Remove-AppVClientPackge` 用于删除 App-v 包时，将清理程序包存储位置。 请记住，从管理服务器取消发布 app-v 程序包不会执行删除操作。 两个操作都不会删除软件包存储包文件。

## <a href="" id="bkmk-roaming-reg-data"></a>漫游注册表和数据


App-v 5 可以在漫游时提供近乎真实的体验，具体取决于所使用的应用程序的编写方式。 默认情况下，在漫游位置中存储的 App-v 漫游 AppData，这取决于操作系统的漫游配置。 存储基于文件的数据的其他位置不会从计算机漫游到计算机，因为它们位于非漫游位置。

### <a href="" id="bkmk-clt-inter-roam-reqs"></a>漫游要求和用户目录数据存储

App-v 存储数据，它以下列形式表示用户目录的状态：

-   %Appdata%\\Microsoft\\AppV\\Client\\Catalog 下的文件

-   下的注册表设置 `HKEY_CURRENT_USER\Software\Microsoft\AppV\Client\Packages`

这些文件和注册表设置共同表示用户的目录，因此两者都必须是漫游，或者都不是特定用户的漫游。 App-v 不支持漫游% AppData%，但不支持漫游用户的配置文件（注册表），反之亦然。

**注意** **AppvClientPackage** cmdlet 不会修复程序包的发布状态，即用户的 app-v 状态 `HKEY_CURRENT_USER` 缺失或与% appdata% 中的数据不匹配。

 

### 基于注册表的数据

App-v 注册表漫游分为两种方案，如下表所示。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">情形</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>作为标准用户运行的应用程序</p></td>
<td align="left"><p>当标准用户启动 App-v 应用程序时，应用 V 应用程序的 HKLM 和 HKCU 均存储在计算机上的 HKCU 配置单元中。 这将显示为两个不同的路径：</p>
<ul>
<li><p>HKLM\： HKCU\SOFTWARE\Classes\AppV\Client\Packages {PkgGUID} \ REGISTRY\MACHINE\SOFTWARE</p></li>
<li><p>HKCU： HKCU\SOFTWARE\Microsoft\AppV\Client\Packages {PkgGUID} \ REGISTRY\USER {UserSID} \ 软件</p></li>
</ul>
<p>根据操作系统设置，可启用漫游位置。</p></td>
</tr>
<tr class="even">
<td align="left"><p>通过提升运行的应用程序</p></td>
<td align="left"><p>当使用提升启动应用程序时：</p>
<ul>
<li><p>HKLM 数据存储在本地计算机上的 HKLM 配置单元中</p></li>
<li><p>HKCU 数据存储在用户的注册表位置</p></li>
</ul>
<p>在此方案中，这些设置不是通过正常操作系统漫游配置进行漫游，并且生成的注册表项和值存储在以下位置：</p>
<ul>
<li><p>HKLM\SOFTWARE\Microsoft\AppV\Client\Packages{PkgGUID}{UserSID}\REGISTRY\MACHINE\SOFTWARE</p></li>
<li><p>HKCU\SOFTWARE\Microsoft\AppV\Client\Packages {PkgGUID} \ Registry\User {UserSID} \ 软件</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

### App-v 和文件夹重定向

App-v 5.1 支持漫游 AppData 文件夹的文件夹重定向（% AppData%）。 启动虚拟环境时，将用户的漫游 AppData 目录中的漫游 AppData 状态复制到本地缓存。 相反，当虚拟环境关闭时，与特定用户的漫游 AppData 相关联的本地缓存将被转移到该用户的漫游 AppData 目录的实际位置。

典型程序包在用户的后备存储中映射了多个位置，用于 AppData\\Local 和 AppData\\Roaming. 中的设置 这些位置是在用户配置文件中为每个用户存储的写位置上的副本，用于存储对软件包 VFS 目录所做的更改，并保护默认程序包 VFS。

下表显示了未实现文件夹重定向时的本地和漫游位置。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">程序包中的 VFS 目录</th>
<th align="left">备份存储的映射位置</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>ProgramFilesX86</p></td>
<td align="left"><p>C:\users\jsmith\AppData &lt; 强劲的 &gt; 本地 </strong> \Microsoft\AppV\Client\VFS &amp;GUID &gt; \ProgramFilesX86</p></td>
</tr>
<tr class="even">
<td align="left"><p>SystemX86</p></td>
<td align="left"><p>C:\users\jsmith\AppData &lt; 强劲的 &gt; 本地 </strong> \Microsoft\AppV\Client\VFS &amp;GUID &gt; \SystemX86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows</p></td>
<td align="left"><p>C:\users\jsmith\AppData &lt; 强劲的 &gt; 本地 </strong> \Microsoft\AppV\Client\VFS &amp;GUID &gt; \windows</p></td>
</tr>
<tr class="even">
<td align="left"><p>appv_ROOT</p></td>
<td align="left"><p>C:\users\jsmith\AppData &lt; 强劲的 &gt; 本地 </strong> \Microsoft\AppV\Client\VFS &amp;GUID &gt; \ appv_ROOT</p></td>
</tr>
<tr class="odd">
<td align="left"><p>AppData</p></td>
<td align="left"><p>C:\users\jsmith\AppData &lt; 强劲的 &gt; 漫游 </strong> \Microsoft\AppV\Client\VFS &amp;GUID &gt; \AppData</p></td>
</tr>
</tbody>
</table>

 

 

下表显示了在为% AppData% 实现文件夹重定向且位置已重定向（通常为网络位置）时，本地和漫游位置。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">程序包中的 VFS 目录</th>
<th align="left">备份存储的映射位置</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>ProgramFilesX86</p></td>
<td align="left"><p>C:\users\jsmith\AppData &lt; 强劲的 &gt; 本地 </strong> \Microsoft\AppV\Client\VFS &amp;GUID &gt; \ProgramFilesX86</p></td>
</tr>
<tr class="even">
<td align="left"><p>SystemX86</p></td>
<td align="left"><p>C:\users\jsmith\AppData &lt; 强劲的 &gt; 本地 </strong> \Microsoft\AppV\Client\VFS &amp;GUID &gt; \SystemX86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows</p></td>
<td align="left"><p>C:\users\jsmith\AppData &lt; 强劲的 &gt; 本地 </strong> \Microsoft\AppV\Client\VFS &amp;GUID &gt; \windows</p></td>
</tr>
<tr class="even">
<td align="left"><p>appv_ROOT</p></td>
<td align="left"><p>C:\users\jsmith\AppData &lt; 强劲的 &gt; 本地 </strong> \Microsoft\AppV\Client\VFS &amp;GUID &gt; \ appv_ROOT</p></td>
</tr>
<tr class="odd">
<td align="left"><p>AppData</p></td>
<td align="left"><p><strong>\Fileserver </strong> \users\jsmith\roaming\Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \AppData</p></td>
</tr>
</tbody>
</table>

 

 

当前应用-V 客户端 VFS 驱动程序无法写入到网络位置，因此 App-v 客户端在发布和虚拟环境启动时，检测到 "文件夹重定向" 和 "复制本地驱动器上的数据"。 用户关闭应用程序-v 应用程序并且 app-v 客户端关闭虚拟环境后，会将 VFS AppData 的本地存储复制回网络，从而允许漫游到其他计算机，其中将重复该过程。 流程的详细步骤如下：

1.  在发布或虚拟环境启动期间，App-v 客户端将检测 AppData 目录的位置。

2.  如果漫游 AppData 路径为 "本地" 或 ".ino AppData\\Roaming 位置已映射"，则不会发生任何反应。

3.  如果漫游 AppData 路径不是本地路径，则 VFS AppData 目录将映射到本地 AppData 目录。

此过程解决了 App-v 客户端 VFS 驱动程序不支持的非本地% AppData% 的问题。 但是，此新位置中存储的数据不会通过文件夹重定向进行漫游。 应用程序运行期间的所有更改都将发生在本地 AppData 位置，并且必须复制到重定向的位置。 此过程的详细步骤如下：

1.  App-v 应用程序已关闭，从而关闭了虚拟环境。

2.  漫游 AppData 位置的本地缓存被压缩并存储在 ZIP 文件中。

3.  ZIP 打包过程末尾的时间戳用于命名文件。

4.  时间戳将记录在注册表中： HKEY \ _CURRENT \ _USER \\Software\\Microsoft\\AppV\\Client\\Packages\\ &lt; GUID &gt; \\AppDataTime 作为最后一个已知 AppData 时间戳。

5.  将调用文件夹重定向过程来计算和启动上载到漫游 AppData 目录的 ZIP 文件。

当发布 V 应用程序或启动虚拟环境时，如果存在冲突，并且用于优化数据下载，则时间戳用于确定 "最后一个写入程序入选" 方案。 文件夹重定向将使支持策略覆盖的任何其他客户端提供数据，并启动将 AppData\\Roaming 数据存储到客户端上的本地 AppData 位置的过程。 详细流程包括：

1.  用户通过启动应用程序来启动虚拟环境。

2.  应用程序的虚拟环境将检查是否存在最新的加盖时间戳的 ZIP 文件（如果存在）。

3.  将检查注册表中是否存在上次已知的上载时间戳（如果存在）。

4.  除非本地最后一个已知上载时间戳大于或等于 ZIP 文件中的时间戳，否则将下载最新的 ZIP 文件。

5.  如果本地上次已知上载时间戳比漫游 AppData 位置中最新的 ZIP 文件的旧版本更早，则会将 ZIP 文件提取到用户配置文件中的本地临时目录中。

6.  成功提取 ZIP 文件后，将重命名漫游 AppData 目录的本地缓存，并将新数据移动到相应位置。

7.  已重命名的目录将被删除，应用程序将打开，其中包含最近保存的漫游 AppData 数据。

这将完成 AppData\\Roaming 位置中存在的应用程序设置的成功漫游。 唯一必须解决的其他条件是程序包修复操作。 该过程的详细信息如下：

1.  在修复期间，检测用户的漫游 AppData 目录的路径是否不是本地路径。

2.  映射非本地漫游 AppData 路径目标将重新创建预期的漫游和本地 AppData 位置。

3.  删除注册表中存储的时间戳（如果存在）。

此过程将重新创建 AppData 的本地和网络位置，并删除时间戳的注册表记录。

## <a href="" id="bkmk-clt-app-lifecycle"></a>App-v 客户端应用程序生命周期管理


在 App-v 完整基础结构中，将应用程序序列化后，通过 App-v 管理和发布服务器对用户或计算机进行管理和发布。 本节详细介绍了常见的 app-v 应用程序生命周期操作（添加、发布、启动、升级和删除）期间发生的操作，以及从 App-v 客户端角度更改和修改的文件和注册表位置。 App-v 客户端操作以一系列在运行 App-v 客户端的计算机上启动的 PowerShell 命令的形式执行。

本文档重点介绍应用 V 完整基础结构解决方案。 有关与 Configuration Manager 2012 进行的 App-v 集成的详细信息，请访问： <https://go.microsoft.com/fwlink/?LinkId=392773> 。

App-v 应用程序生命周期任务将在用户登录（默认）、计算机启动或后台计时操作时触发。 应用程序-V 客户端操作的设置（包括发布服务器、刷新间隔、程序包脚本启用以及其他）将在客户端安装期间配置或安装 PowerShell 命令后配置。 有关如何[部署 App-v 客户端](how-to-deploy-the-app-v-client-51gb18030.md)或使用 PowerShell 的说明，请参阅 TechNet 上的 "如何部署客户端" 部分：

```powershell
get-command *appv*
```

### 发布刷新

发布刷新过程由在 App-v 客户端上执行的几个较小的操作组成。 由于 app-v 是应用程序虚拟化技术而不是任务计划技术，因此使用 Windows 任务计划程序在用户登录、计算机启动和按计划的时间间隔启用进程。 将客户端分配给具有正确设置的大型计算机组时，上述安装期间的客户端配置是首选方法。 可通过以下 PowerShell cmdlet 配置这些客户端设置：

-   **Add-AppVPublishingServer：** 使用提供 app-v 程序包的 App-v 发布服务器配置客户端。

-   **Set-AppVPublishingServer：** 修改 app-v 发布服务器的当前设置。

-   **Set-AppVClientConfiguration：** 修改 app-v 客户端的电流设置。

-   **Sync-AppVPublishingServer：** 手动启动 app-v 发布刷新过程。 在配置发布服务器期间创建的计划任务中也会使用此功能。

以下各节的重点是详细介绍在 App-v 发布刷新的不同阶段期间发生的操作。 这些主题包括：

-   添加 App-v 程序包

-   发布 app-v 程序包

### 添加 App-v 程序包

将 app-v 程序包添加到客户端是发布刷新过程的第一步。 最终结果与 `Add-AppVClientPackage` PowerShell 中的 cmdlet 相同，但在发布刷新添加过程中，已配置的发布服务器将被联系，并将一个高级别的应用程序列表传递回客户端，以便提取更详细的信息，而不是单个程序包添加操作。 通过为程序包或连接组添加或更新配置客户端，然后访问 appv 文件，将继续此过程。 接下来，将在本地操作系统上的相应位置展开并放置 appv 文件的内容。 以下是进程的详细工作流，假设将程序包配置为用于故障流。

**如何添加 App-v 程序包**

1.  通过发布刷新过程的 PowerShell 或任务序列启动手动启动。

    1.  App-v 客户端进行 HTTP 连接，并请求基于目标的应用程序列表。 发布刷新过程支持面向计算机或用户。

    2.  App-v 发布服务器使用启动目标、用户或计算机的标识，并查询数据库以获取具有标题的应用程序的列表。 应用程序列表以 XML 响应的形式提供，客户端使用它向服务器发送其他请求，以获取有关每个程序包的详细信息。

2.  App-v 客户端上的发布代理执行以下序列化的所有操作。

    评估未发布或已禁用的任何连接组，因为无法处理属于连接组的程序包版本更新。

3.  通过标识添加或更新操作来配置程序包。

    1.  App-v 客户端利用 Windows 中的 AppX API，并从发布服务器访问 appv 文件。

    2.  将打开程序包文件，并将 AppXManifest.xml 和 StreamMap.xml 下载到程序包存储。

    3.  已完全流出在 StreamMap.xml 中定义的发布块数据。 将发布块数据存储在程序包 Store\\PkgGUID\\VerGUID\\Root. 中

        -   图标：扩展点的目标。

        -   可移植可执行文件头（PE 标头）：扩展点的目标，其中包含有关图像的基本信息需要在磁盘上、直接访问或通过文件类型。

        -   脚本：下载脚本目录以供在整个发布过程中使用。

    4.  填充包存储：

        1.  在磁盘上创建用于表示列出的任何目录的提取程序包的稀疏文件。

        2.  在 root 之下暂存顶级文件和目录。

        3.  当目录在磁盘上列为稀疏并按需进行流式处理时，将创建所有其他文件。

    5.  创建计算机目录条目。 从程序包文件创建 Manifest.xml 和 DeploymentConfiguration.xml （如果程序包中没有创建占位符的 DeploymentConfiguration.xml 文件）。

    6.  在注册表中创建软件包存储的位置 HKLM\\Software\\Microsoft\\AppV\\Client\\Packages\\PkgGUID\\Versions\\VerGUID\\Catalog

    7.  创建从包存储到%ProgramData%\\Microsoft\\AppV\\Client\\VReg\\ {VersionGUID} .dat 的注册表 .dat 文件

    8.  在应用程序 V 内核模式驱动程序 HKLM\\Microsoft\\Software\\AppV\\MAV 注册程序包

    9.  从 "AppxManifest.xml" 或 "DeploymentConfig.xml 文件" 中调用脚本以进行程序包添加计时。

4.  通过添加和启用或禁用来配置连接组。

5.  删除未发布到目标（用户或计算机）的对象。

    **注意** 这将不会执行程序包删除，而是删除特定目标（用户或计算机）的集成点，并删除用户目录文件（适用于全局发布的计算机目录文件）。

     

6.  基于客户端配置调用后台加载装载。

7.  已立即还原计算机或用户的发布信息的程序包。

    **注意** 这种情况在未通过后台添加程序包的情况下作为删除的产品出现。

     

这将完成发布刷新过程的应用程序-V 包的添加。 下一步是将程序包发布到特定目标（计算机或用户）。

![程序包添加文件和注册表数据](images/packageaddfileandregistrydata.png)

### 发布 app-v 程序包

在发布刷新操作期间，特定发布操作（Publish-AppVClientPackage）将条目添加到用户目录、将权利映射到用户、标识本地存储以及完成任何集成步骤。 以下是详细步骤。

**如何发布和 App-v 程序包**

1.  将程序包条目添加到用户目录

    1.  用户目标程序包：将 UserDeploymentConfiguration.xml 和 UserManifest.xml 放在计算机上的用户目录中

    2.  计算机定向的（全局）程序包： UserDeploymentConfiguration.xml 位于计算机目录中

2.  在 HKLM\\Software\\Microsoft\\AppV\\MAV 上向用户注册程序包的内核模式驱动程序

3.  执行集成任务。

    1.  创建扩展点。

    2.  将备份信息存储在用户的注册表和漫游配置文件中（快捷方式备份）。

        **注意** 如果未发布程序包，这将允许还原扩展点。

         

    3.  运行针对发布计时的脚本。

发布属于连接组的 app-v 程序包非常类似于上述过程。 对于连接组，存储特定目录信息的路径包括 PackageGroups 作为目录目录的子目录。 有关详细信息，请查看上述计算机和用户目录信息。

![程序包添加文件和注册表数据-全局](images/packageaddfileandregistrydata-global.png)

### 应用程序启动

发布刷新过程后，用户将启动并重新启动 App-v 应用程序。 该过程非常简单，并且经过优化，可通过最少的网络流量快速启动。 App-v 客户端将检查在发布期间创建的文件的用户目录的路径。 建立了启动程序包的权限后，App-v 客户端将创建一个虚拟环境、开始流式处理任何必需的数据，并在创建虚拟环境期间应用相应的清单和部署配置文件。 在为特定程序包和应用程序创建和配置的虚拟环境下，应用程序启动。

**如何启动 app-v 应用程序**

1.  用户通过单击快捷方式或文件类型调用来启动应用程序。

2.  App-v 客户端验证以下文件的用户目录中是否存在

    -   UserDeploymentConfiguration.xml

    -   UserManifest.xml

3.  如果文件存在，应用程序将有权使用该特定用户，应用程序将启动启动过程。 此时没有网络流量。

4.  接下来，App-v 客户端检查注册表中是否找到为 App-v 客户端服务注册的程序包的路径。

5.  找到程序包存储的路径后，将创建虚拟环境。 如果这是首次启动，则主要功能阻止下载（如果存在）。

6.  下载后，app-v 客户端服务将使用清单和部署配置文件来配置虚拟环境并加载所有 App-v 子系统。

7.  应用程序启动。 对于程序包存储（稀疏文件）中的任何缺少的文件，App-v 将根据需要流出文件错误。

    ![程序包添加文件和注册表数据流](images/packageaddfileandregistrydata-stream.png)

### 升级 app-v 程序包

App-v 5 程序包升级过程与早期版本的 App-v 不同。 App-v 支持具有不同用户的计算机上的同一程序包的多个版本。 可以随时添加程序包版本，因为程序包存储和目录已通过新资源进行更新。 特定于添加新版本资源的唯一流程是存储优化。 在升级过程中，仅将新文件添加到新版本存储位置，并为未更改的文件创建硬链接。 这将减少整个存储，只是在一个磁盘位置上显示文件，然后在磁盘上有一个文件位置条目的所有文件夹中投影到该文件。 升级 app-v 程序包的具体详细信息如下所示：

**如何升级 app-v 程序包**

1.  App-v 客户端执行发布刷新并发现较新版本的 App-v 包。

2.  程序包条目将添加到新版本的相应目录中

    1.  用户目标程序包：将 UserDeploymentConfiguration.xml 和 UserManifest.xml 放在计算机上 appdata\\roaming\\Microsoft\\AppV\\Client\\Catalog\\Packages\\PkgGUID\\VerGUID 的用户目录中

    2.  计算机定向的（全局）程序包： UserDeploymentConfiguration.xml 位于%programdata%\\Microsoft\\AppV\\Client\\Catalog\\Packages\\PkgGUID\\VerGUID 的计算机目录中

3.  在 HKLM\\Software\\Microsoft\\AppV\\MAV 上向用户注册程序包的内核模式驱动程序

4.  执行集成任务。

    -   将扩展点（EP）与清单和动态配置文件集成。

    1.  基于文件的 EP 数据存储在 AppData 文件夹中，利用来自程序包存储的交接点。

    2.  当有新版本可用时，版本 1 EPs 已存在。

    3.  对于任何更新或更新的扩展点，扩展点将切换到计算机或用户目录中的版本2位置。

5.  运行针对发布计时的脚本。

6.  根据需要安装 "并行程序集"。

### 升级使用中的 App-v 包

**从 app-v 5 SP2 开始**：如果你尝试升级已由最终用户使用的程序包，则会将升级任务置于挂起状态。 稍后将根据以下规则运行升级：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">任务类型</th>
<th align="left">适用规则</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>基于用户的任务，例如将程序包发布给用户</p></td>
<td align="left"><p>将在用户注销后执行挂起的任务，然后重新登录。</p></td>
</tr>
<tr class="even">
<td align="left"><p>基于全球的任务，例如，全局启用连接组</p></td>
<td align="left"><p>当计算机关闭然后重新启动时，将执行挂起的任务。</p></td>
</tr>
</tbody>
</table>

 

当任务置于挂起状态时，App-v 客户端还会为挂起任务生成注册表项，如下所示：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">基于用户或基于全球的任务</th>
<th align="left">注册表项的生成位置</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>基于用户的任务</p></td>
<td align="left"><p>KEY_CURRENT_USER \Software\Microsoft\AppV\Client\PendingTasks</p></td>
</tr>
<tr class="even">
<td align="left"><p>基于全球的任务</p></td>
<td align="left"><p>HKEY_LOCAL_MACHINE \Software\Microsoft\AppV\Client\PendingTasks</p></td>
</tr>
</tbody>
</table>

 

必须先完成以下操作，然后用户才能使用程序包的较新版本：

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
<td align="left"><p>将程序包添加到计算机</p></td>
<td align="left"><p>此任务是计算机特定的，你可以随时完成上述 "程序包添加" 部分中的步骤执行此任务。</p></td>
</tr>
<tr class="even">
<td align="left"><p>发布程序包</p></td>
<td align="left"><p>有关步骤，请参阅上面的程序包发布部分。 此过程要求你在系统上更新扩展点。 完成此任务后，最终用户无法使用该应用程序。</p></td>
</tr>
</tbody>
</table>

 

将以下示例方案用作更新程序包的指南。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">情形</th>
<th align="left">要求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>尝试升级时，未使用 app-v 程序包</p></td>
<td align="left"><p>程序包的以下组件均不能使用：虚拟应用程序、COM 服务器或外壳扩展。</p>
<p>管理员发布较新版本的程序包，升级将在下次启动程序包中的组件或应用程序时运行。 数据包的新版本将被流式处理并运行。 从 app-v 5 早期版本的 app-v 5 SP2 中，此方案中没有任何更改。</p></td>
</tr>
<tr class="even">
<td align="left"><p>管理员发布更新版本的程序包时，正在使用 app-v 包</p></td>
<td align="left"><p>升级操作设置为 "App-v 客户端挂起"，这意味着它将排队，稍后在程序包未使用时执行。</p>
<p>如果程序包应用程序正在使用中，用户将关闭虚拟应用程序，之后可以进行升级。</p>
<p>如果程序包具有外壳扩展（Office 2013），而它们由 Windows 资源管理器永久加载，则用户无法登录。 用户必须注销，然后重新登录才能启动 app-v 程序包升级。</p></td>
</tr>
</tbody>
</table>

 

### 全局和用户发布

可以通过两种方式之一发布 app-v 程序包;用户向特定用户或用户组证明了 app-v 程序包的用户和全局，这将对计算机的所有用户提供对整个计算机的 App-v 程序包。 一旦程序包升级挂起且未使用 app-v 包，请考虑两种类型的发布：

-   **全局发布**：将应用程序发布到计算机;该计算机上的所有用户都可以使用它。 升级将在 App-v Client 服务启动时进行，这将有效地表示计算机重新启动。

-   **用户已发布**：应用程序已发布给用户。 如果计算机上有多个用户，则可以将应用程序发布到用户的子集。 当用户登录或再次发布时（定期、ConfigMgr 策略刷新和评估、应用程序 V 定期发布/刷新或通过 PowerShell 命令显式发布），将发生升级。

### 删除 App-v 程序包

在完整基础结构中删除 App-v 应用程序是取消发布操作，不会执行程序包删除。 该过程与上述发布过程相同，但不是添加删除过程会反转对 app-v 程序包所做的更改。

### 修复 App-v 程序包

修复操作非常简单，但可能会影响计算机上的多个位置。 前面提到的 "写入" （牛）位置将被删除，扩展点将被取消集成，然后重新集成。 请通过查看注册表中的注册位置来查看牛数据放置位置。 此操作自动执行，除了从 App-v 客户端控制台或通过 PowerShell 发起修复操作之外，没有任何管理控制。

## <a href="" id="bkmk-integr-appv-pkgs"></a>App-v 程序包的集成


App-v 客户端和程序包体系结构在添加和发布程序包的过程中提供与本地操作系统的特定集成。 三个文件定义了 app-v 包的集成或扩展点：

-   AppXManifest.xml：存储在程序包内，并将回退副本存储在程序包存储和用户配置文件中。 包含在排序过程中创建的选项。

-   DeploymentConfig.xml：提供计算机和基于用户的集成扩展点的配置信息。

-   UserConfig.xml：仅提供基于用户的配置和仅面向基于用户的扩展点的 Deploymentconfig.xml 的子集。

### 集成规则

在使用 app-v 客户端将 App-v 应用程序发布到计算机时，按照下面的列表中所述执行某些特定操作：

-   全局发布：快捷方式存储在 "所有用户配置文件" 位置，其他扩展点存储在 HKLM 配置单元中的注册表中。

-   用户发布：快捷方式存储在当前用户帐户配置文件中，其他扩展点存储在 HKCU 配置单元中的注册表中。

-   备份和还原：在发布期间备份现有的本机应用程序数据和注册表（如 FTA 注册）。

    1.  App-v 程序包基于上一个集成的程序包（所有权已传递到最新发布的 App-v 应用程序）获得所有权。

    2.  当未发布所属的 App-v 包时，所有权将从一个 App-v 包转移到另一个。 这将不会启动数据或注册表的还原。

    3.  在每个扩展点取消发布或删除最后一个软件包时，还原已备份的数据。

### 扩展点

App-v 发布文件（清单和动态配置）提供了多个扩展点，使应用程序可以与本地操作系统集成。 这些扩展点执行典型的应用程序安装任务，例如放置快捷方式、创建文件类型关联和注册组件。 由于这些应用程序的虚拟应用程序与传统应用程序的安装方式不同，因此存在一些差异。 以下是本部分中介绍的扩展点列表：

-   指向

-   文件类型关联

-   外壳扩展

-   COM

-   软件客户端

-   应用程序功能

-   URL 协议处理程序

-   AppPath

-   虚拟应用程序

### 指向

简短剪切是与操作系统集成的基本元素之一，并且是应用 V 应用程序的直接用户启动接口。 在发布和取消发布 App-v 应用程序期间。

从程序包清单和动态配置 XML 文件中，可以在类似以下内容的部分中找到特定应用程序可执行文件的路径：

```xml
<Extension Category="AppV.Shortcut">
          <Shortcut>
            <File>[{Common Desktop}]\Adobe Reader 9.lnk</File>
            <Target>[{AppVPackageRoot}]\Reader\AcroRd32.exe</Target>
            <Icon>[{Windows}]\Installer\{AC76BA86-7AD7-1033-7B44-A94000000001}\SC_Reader.ico</Icon>
            <Arguments />
            <WorkingDirectory />
            <ShowCommand>1</ShowCommand>
            <ApplicationId>[{AppVPackageRoot}]\Reader\AcroRd32.exe</ApplicationId>
          </Shortcut>
        </Extension>
```

如前面所述，默认情况下，App-v 快捷方式基于刷新操作放置在用户的配置文件中。 全局刷新将 "所有用户" 配置文件和用户刷新中的快捷方式存储在特定用户的配置文件中。 实际可执行文件存储在程序包存储中。 .ICO 文件的位置是 App-v 包中已标记的位置。

### 文件类型关联

App-v 客户端在发布期间管理本地操作系统文件类型关联，这使用户可以使用文件类型调用或打开具有特定注册扩展名（.docx）的文件以启动 app-v 应用程序。 文件类型关联存在于清单和动态配置文件中，如下面的示例所示：

```xml
<Extension Category="AppV.FileTypeAssociation">
          <FileTypeAssociation>
            <FileExtension MimeAssociation="true">
              <Name>.xdp</Name>
              <ProgId>AcroExch.XDPDoc</ProgId>
              <ContentType>application/vnd.adobe.xdp+xml</ContentType>
            </FileExtension>
            <ProgId>
              <Name>AcroExch.XDPDoc</Name>
              <Description>Adobe Acrobat XML Data Package File</Description>
              <EditFlags>65536</EditFlags>
              <DefaultIcon>[{Windows}]\Installer\{AC76BA86-7AD7-1033-7B44-A94000000001}\XDPFile_8.ico</DefaultIcon>
              <ShellCommands>
                <DefaultCommand>Read</DefaultCommand>
                <ShellCommand>
                  <ApplicationId>[{AppVPackageRoot}]\Reader\AcroRd32.exe</ApplicationId>
                  <Name>Open</Name>
                  <CommandLine>"[{AppVPackageRoot}]\Reader\AcroRd32.exe" "%1"</CommandLine>
                </ShellCommand>
                <ShellCommand>
                  <ApplicationId>[{AppVPackageRoot}]\Reader\AcroRd32.exe</ApplicationId>
                  <Name>Printto</Name>
                  <CommandLine>"[{AppVPackageRoot}]\Reader\AcroRd32.exe"  /t "%1" "%2" "%3" "%4"</CommandLine>
                </ShellCommand>
                <ShellCommand>
                  <ApplicationId>[{AppVPackageRoot}]\Reader\AcroRd32.exe</ApplicationId>
                  <Name>Read</Name>
                  <FriendlyName>Open with Adobe Reader 9</FriendlyName>
                  <CommandLine>"[{AppVPackageRoot}]\Reader\AcroRd32.exe" "%1"</CommandLine>
                </ShellCommand>
              </ShellCommands>
            </ProgId>
          </FileTypeAssociation>
        </Extension>
```

**注意** 在此示例中：

-   `<Name>.xdp</Name>` 是分机号

-   `<Name>AcroExch.XDPDoc</Name>` 是 ProgId 值（指向相邻的 ProgId）

-   `<CommandLine>"[{AppVPackageRoot}]\Reader\AcroRd32.exe" "%1"</CommandLine>` 是指向应用程序可执行文件的命令行

 

### Shell 扩展

在排序过程中，将自动在程序包中嵌入外壳扩展。 当程序包以全局方式发布时，外壳扩展为用户提供与应用程序本地安装相同的功能。 应用程序不需要在客户端上进行额外的设置或配置即可启用外壳扩展功能。

**使用外壳扩展的要求：**

-   包含嵌入式外壳扩展的软件包必须全局发布。

-   应用程序、Sequencer 和 App-v 客户端的 "位数" 必须匹配，否则 shell 扩展将不起作用。 例如：

    -   该应用程序的版本为64位。

    -   Sequencer 在64位计算机上运行。

    -   程序包正在发送到64位 App-v 客户端计算机。

下表显示受支持的外壳扩展。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">函数</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>上下文菜单处理程序</p></td>
<td align="left"><p>将菜单项添加到上下文菜单。 在显示上下文菜单之前调用它。</p></td>
</tr>
<tr class="even">
<td align="left"><p>拖放处理程序</p></td>
<td align="left"><p>控制在右键单击拖放的操作，并修改出现的上下文菜单。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>拖放目标处理程序</p></td>
<td align="left"><p>控制在将数据对象拖放到放置目标（如文件）上后的操作。</p></td>
</tr>
<tr class="even">
<td align="left"><p>数据对象处理程序</p></td>
<td align="left"><p>控制在将文件复制到剪贴板或将其拖放到放置目标上后的操作。 它可以向放置目标提供其他剪贴板格式。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>属性表处理程序</p></td>
<td align="left"><p>将页面替换或添加到对象的 "属性表" 对话框。</p></td>
</tr>
<tr class="even">
<td align="left"><p>提示处理程序</p></td>
<td align="left"><p>允许检索某个项目的标志和信息提示信息，并在鼠标悬停时将其显示在弹出工具提示内。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>列处理程序</p></td>
<td align="left"><p>允许在 Windows 资源管理器的 "详细信息" 视图中创建和显示自定义列 <em> </em> 。 它可用于扩展排序和分组。</p></td>
</tr>
<tr class="even">
<td align="left"><p>预览处理程序</p></td>
<td align="left"><p>启用要在 Windows 资源管理器预览窗格中显示的文件的预览。</p></td>
</tr>
</tbody>
</table>

 

### COM

App-v 客户端支持通过 COM 集成和虚拟化支持发布应用程序。 COM 集成允许 App-v 客户端在本地操作系统和对象的虚拟化中注册 COM 对象。 出于本文档的目的，COM 对象的集成需要更多详细信息。

App-v 支持将程序包中的 COM 对象注册到具有两种进程类型的本地操作系统：进程外和进程内。 注册 COM 对象的操作是通过一个或多个特定 App-v 包（包括已关闭、隔离和集成）的操作模式的组合完成的。 已针对进程外或进程内类型配置了集成模式。 COM 模式和类型的配置是通过动态配置文件（deploymentconfig.xml 或 userconfig.xml）实现的。

有关应用 V 集成的详细信息，请访问： <https://go.microsoft.com/fwlink/?LinkId=392834> 。

### 软件客户端和应用程序功能

App-v 支持特定软件客户端和应用程序功能扩展点，使虚拟化应用程序能够注册到操作系统的软件客户端。 这使用户能够为诸如电子邮件、即时消息和媒体播放机之类的操作选择默认程序。 使用设置程序访问和计算机默认值在控制面板中执行此操作，并在清单或动态配置文件中的排序期间进行配置。 仅当全局发布 app-v 应用程序时，才支持应用程序功能。

基于 app-v 的邮件客户端注册软件客户端的示例。

```xml
    <SoftwareClients Enabled="true">
      <ClientConfiguration EmailEnabled="true" />
      <Extensions>
        <Extension Category="AppV.SoftwareClient">
          <SoftwareClients>
            <EMail MakeDefault="true">
              <Name>Mozilla Thunderbird</Name>
              <Description>Mozilla Thunderbird</Description>
              <DefaultIcon>[{ProgramFilesX86}]\Mozilla Thunderbird\thunderbird.exe,0</DefaultIcon>
              <InstallationInformation>
                <RegistrationCommands>
                  <Reinstall>"[{ProgramFilesX86}]\Mozilla Thunderbird\uninstall\helper.exe" /SetAsDefaultAppGlobal</Reinstall>
                  <HideIcons>"[{ProgramFilesX86}]\Mozilla Thunderbird\uninstall\helper.exe" /HideShortcuts</HideIcons>
                  <ShowIcons>"[{ProgramFilesX86}]\Mozilla Thunderbird\uninstall\helper.exe" /ShowShortcuts</ShowIcons>
                </RegistrationCommands>
                <IconsVisible>1</IconsVisible>
                <OEMSettings />
              </InstallationInformation>
              <ShellCommands>
                <ApplicationId>[{ProgramFilesX86}]\Mozilla Thunderbird\thunderbird.exe</ApplicationId>
                <Open>"[{ProgramFilesX86}]\Mozilla Thunderbird\thunderbird.exe" -mail</Open>
              </ShellCommands>
              <MAPILibrary>[{ProgramFilesX86}]\Mozilla Thunderbird\mozMapi32_InUse.dll</MAPILibrary>
              <MailToProtocol>
                <Description>Thunderbird URL</Description>
                <EditFlags>2</EditFlags>
                <DefaultIcon>[{ProgramFilesX86}]\Mozilla Thunderbird\thunderbird.exe,0</DefaultIcon>
                <ShellCommands>
                  <ApplicationId>[{ProgramFilesX86}]\Mozilla Thunderbird\thunderbird.exe</ApplicationId>
                  <Open>"[{ProgramFilesX86}]\Mozilla Thunderbird\thunderbird.exe" -osint -compose "%1"</Open>
                </ShellCommands>
              </MailToProtocol>
            </EMail>
          </SoftwareClients>
        </Extension>
      </Extensions>
    </SoftwareClients>
```

**注意** 在此示例中：

-   `<ClientConfiguration EmailEnabled="true" />` 是集成电子邮件客户端的整体软件客户端设置

-   `<EMail MakeDefault="true">` 用于将特定电子邮件客户端设置为默认电子邮件客户端的标志

-   `<MAPILibrary>[{ProgramFilesX86}]\Mozilla Thunderbird\mozMapi32_InUse.dll</MAPILibrary>` 是 MAPI dll 注册

 

### URL 协议处理程序

应用程序并非总是特别称为利用文件类型调用的虚拟化应用程序。 例如，在支持嵌入 mailto：在文档或网页中的应用程序中，用户单击 mailto： link，预期会获取其注册的邮件客户端。 App-v 支持可在每个程序包基础上使用本地操作系统注册的 URL 协议处理程序。 在排序期间，URL 协议处理程序将自动添加到程序包。

如果存在多个可以注册特定 URL 协议处理程序的应用程序，则可以利用动态配置文件来修改该行为，并为不应启动的应用程序取消或禁用此功能。

### AppPath

AppPath 扩展点支持直接从操作系统调用 App-V 应用程序。 这通常是从 "运行" 或 "开始" 屏幕完成的，具体取决于操作系统，使管理员能够从操作系统命令或脚本中提供对 App-v 应用程序的访问权限，而无需调用可执行文件的特定路径。 因此，它可以避免在所有系统上修改系统 path 环境变量，因为它在发布过程中完成。

AppPath 扩展点是在清单或动态配置文件中配置的，并且存储在用户的发布期间的本地计算机上的注册表中。 有关 AppPath 审阅的详细信息： <https://go.microsoft.com/fwlink/?LinkId=392835> 。

### 虚拟应用程序

此子系统提供在排序期间捕获的应用程序列表，这些应用程序通常由其他 App-v 组件使用。 可以使用动态配置文件禁用属于特定应用程序的扩展点的集成。 例如，如果某个程序包包含两个应用程序，则可以禁用属于一个应用程序的所有扩展点，以便只支持其他应用程序的扩展点的集成。

### 扩展点规则

根据程序包的发布方式，上面介绍的扩展点将集成到操作系统中。 全局发布将扩展点放在公共计算机位置，用户发布在用户位置中放置扩展点。 例如，在桌面上创建并在全局上发布的快捷方式将导致快捷方式（%Public%\\Desktop）和注册表数据（HKLM\\Software\\Classes）的文件数据。 相同的快捷方式将具有文件数据（%UserProfile%\\Desktop）和注册表数据（HKCU\\Software\\Classes）。

扩展点并非全部以相同的方式发布，其中某些扩展点将需要全局发布，而其他扩展点需要在其提供的特定操作系统和体系结构上进行排序。 下面是描述这两个键规则的表。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">虚拟扩展</th>
<th align="left">需要目标操作系统排序</th>
<th align="left">需要全球发布</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>快捷方式</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>文件类型关联</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>URL 协议</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>AppPaths</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>COM 模式</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>软件客户端</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>应用程序功能</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p>X</p></td>
</tr>
<tr class="even">
<td align="left"><p>上下文菜单处理程序</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p>X</p></td>
</tr>
<tr class="odd">
<td align="left"><p>拖放处理程序</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>数据对象处理程序</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>属性表处理程序</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>提示处理程序</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>列处理程序</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>外壳扩展</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>浏览器帮助程序对象</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p>X</p></td>
</tr>
<tr class="even">
<td align="left"><p>活动 X 对象</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p>X</p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-dynamic-config"></a>动态配置处理


将 app-v 程序包部署到一个计算机或用户非常简单。 但是，由于组织跨业务线和地理和政治边界部署 AppV 应用程序，因此使用一组设置的一次对应用程序进行排序的能力就不可能了。 App-v 是针对此方案而设计的，因为它在清单文件中的排序期间捕获特定的设置和配置，并且还支持动态配置文件的修改。

App-v 动态配置允许为程序包指定计算机级别或用户级别的策略。 动态配置文件使排序工程师能够修改程序包的配置，以满足单个用户或计算机组的需求。 在某些情况下，可能需要对应用程序进行修改才能在 App-v 环境中提供适当的功能。 例如，可能需要对 \ _ \ * config.xml 文件进行修改，以允许在执行应用程序的指定时间执行某些操作，如禁用 mailto 扩展名以防止虚拟化应用程序覆盖另一个应用程序中的该扩展。

App-v 程序包包含 appv 包文件内的清单文件，它代表排序操作，并且是选择策略，除非将动态配置文件分配给特定程序包。 按顺序排序后，可以修改动态配置文件，以允许将应用程序发布到不同的桌面或具有不同扩展点的用户。 这两个动态配置文件是动态部署配置（DDC）和动态用户配置（DUC）文件。 本部分重点介绍清单和动态配置文件的组合。

### 动态配置文件示例

下面的示例显示了发布后和正常操作期间的清单、部署配置和用户配置文件的组合。 这些示例是每个文件的缩写示例。 目的仅显示文件组合，而不是显示每个文件中可用的特定类别的完整说明。 有关详细信息，请查看 app-v 5 排序指南，网址为： <https://go.microsoft.com/fwlink/?LinkID=269810>

**部件**

```xml
<appv:Extension Category="AppV.Shortcut">
     <appv:Shortcut>
          <appv:File>[{Common Programs}]\7-Zip\7-Zip File Manager.lnk</appv:File>
          <appv:Target>[{AppVPackageRoot}]\7zFM.exe</appv:Target>
          <appv:Icon>[{AppVPackageRoot}]\7zFM exe.O.ico</appv:Icon>
     </appv:Shortcut>
</appv:Extension>
```

**部署配置**

```xml
<MachineConfiguration>
     <Subsystems>
          <Registry>
               <Include>
                    <Key Path= "\REGISTRY\Machine\Software\7zip">
                    <Value Type="REG_SZ" Name="Config" Data="1234"/>
                    </Key>
               </Include>
          </Registry>
     </Subsystems>
```

**用户配置**

```xml
<UserConfiguration>
     <Subsystems>
<appv:ExtensionCategory="AppV.Shortcut">
     <appv:Shortcut>
          <appv:File>[{Desktop}]\7-Zip\7-Zip File Manager.lnk</appv:File>
          <appv:Target>[{AppVPackageRoot}]\7zFM.exe</appv:Target>
          <appv:Icon>[{AppVPackageRoot}]\7zFM exe.O.ico</appv:Icon>
     </appv:Shortcut>
</appv:Extension>
     </Subsystems>
<UserConfiguration>
     <Subsystems>
<appv:Extension Category="AppV.Shortcut">
     <appv:Shortcut>
          <appv:Fìle>[{Desktop}]\7-Zip\7-Zip File Manager.lnk</appv:File>
          <appv:Target>[{AppVPackageRoot}]\7zFM.exe</appv:Target>
          <appv:Icon>[{AppVPackageRoot}]\7zFM.exe.O.ico</appv:Icon>
     </appv:Shortcut>
     <appv:Shortcut>
          <appv:File>[{Common Programs}]\7-Zip\7-Zip File Manager.Ink</appv:File>
          <appv:Target>[{AppVPackageRoot}]\7zFM.exe</appv:Target>
          <appv:Icon>[{AppVPackageRoot)]\7zFM.exe.O.ico</appv: Icon>
     </appv:Shortcut>
</appv:Extension>
     </Subsystems>
<MachineConfiguration>
     <Subsystems>
          <Registry>
               <Include>
                    <Key Path="\REGISTRY\Machine\Software\7zip">
                    <Value Type=”REG_SZ" Name="Config" Data="1234"/>
               </Include>
          </Registry>
     </Subsystems>
```

## <a href="" id="bkmk-sidebyside-assemblies"></a>并行程序集


在虚拟应用程序发布期间，app-v 支持在客户端上的排序和部署期间自动打包并行（SxS）程序集。 应用程序-V 5 SP2 支持捕获 SxS 程序集，在对排序计算机上不存在的程序集进行排序。 对于包含 Visual c + + （版本8和更高版本）和/或 MSXML 运行时的程序集，Sequencer 将自动检测和捕获这些依赖关系，即使它们未在监视期间安装。 并列程序集功能消除了以前版本的 App-v 的限制，其中，app-v Sequencer 未捕获序列化工作站上已存在的程序集，并 privatizing 每个程序包限制为一个位版本的程序集。 此行为导致将应用 V 应用程序部署到缺少所需的 SxS 程序集的客户端，从而导致应用程序启动失败。 这会强制打包过程进行记录，然后确保程序包所需的所有程序集都在用户的客户端操作系统上本地安装，以确保支持虚拟应用程序。 根据程序集的数量以及缺少所需依赖关系的应用程序文档，此任务既是管理和实施挑战。

App-v 中的并行程序集支持具有以下功能。

-   排序期间的 SxS 程序集的自动捕获，无论是否已在排序工作站上安装了程序集。

-   当发布时，app-v 客户端将在发布时自动在客户端计算机上安装所需的 SxS 程序集。

-   Sequencer 在 Sequencer 报告机制中报告 VC 运行时依赖关系。

-   Sequencer 允许选择不打包已安装在 Sequencer 上的程序集，支持在目标计算机上已安装这些程序集的方案。

### 自动发布 SxS 程序集

在使用 SxS 程序集发布 app-v 程序包的过程中，app-v 客户端将检查计算机上是否存在该程序集。 如果该程序集不存在，客户端会将该程序集部署到该计算机。 作为连接组一部分的程序包将依赖于属于基本程序包的并列程序集安装，因为连接组不包含有关程序集安装的任何信息。

**注意** 使用程序集取消发布或删除程序包不会删除该程序包的程序集。

 

## <a href="" id="bkmk-client-logging"></a>客户端日志记录


App-v 客户端将信息记录到标准 ETW 格式的 Windows 事件日志中。 可以在事件查看器中的 "应用程序和服务" Logs\\Microsoft\\AppV\\Client. 下找到特定的 App-v 事件。

**注意** 在 App-v 5.0 SP3 中，某些日志已合并并移动到以下位置：

`Event logs/Applications and Services Logs/Microsoft/AppV/ServiceLog`

有关已移动日志的列表，请参阅[关于 App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-event-logs-moved)。

 

下面介绍了三种特定类别的事件记录。

**管理员**：记录适用于 App-v 客户端的配置的事件，并包含主警告和错误。

可**操作**：记录单个组件的常规 app-v 执行和使用情况创建已在 App-v 客户端上完成的 app-v 操作的审核日志。

**虚拟应用程序**：日志虚拟应用程序启动和使用虚拟化子系统。






 

 





