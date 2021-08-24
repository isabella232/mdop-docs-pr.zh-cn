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
ms.openlocfilehash: b94ef87043d428ac92fe1656b3afeb8a8b743808
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910817"
---
# <a name="application-publishing-and-client-interaction"></a>应用程序发布和客户端交互


本文提供有关常见 App-V 客户端操作及其与本地操作系统的集成的技术信息。

-   [Sequencer 创建的 App-V 包文件](#bkmk-appv-pkg-files-list)

-   [appv 文件中有什么？](#bkmk-appv-file-contents)

-   [App-V 客户端数据存储位置](#bkmk-files-data-storage)

-   [包注册表](#bkmk-pkg-registry)

-   [App-V 程序包存储行为](#bkmk-pkg-store-behavior)

-   [漫游注册表和数据](#bkmk-roaming-reg-data)

-   [App-V 客户端应用程序生命周期管理](#bkmk-clt-app-lifecycle)

-   [App-V 程序包的集成](#bkmk-integr-appv-pkgs)

-   [动态配置处理](#bkmk-dynamic-config)

-   [并排程序集](#bkmk-sidebyside-assemblies)

-   [客户端日志记录](#bkmk-client-logging)

有关其他参考信息，请参阅 [Microsoft Application Virtualization (App-V) 文档资源下载页](https://www.microsoft.com/download/details.aspx?id=27760)。

## <a name="app-v-package-files-created-by-the-sequencer"></a><a href="" id="bkmk-appv-pkg-files-list"></a>Sequencer 创建的 App-V 包文件


Sequencer 创建 App-V 包并生成虚拟化应用程序。 排序过程将创建以下文件：

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
<td align="left"><p>.appv</p></td>
<td align="left"><ul>
<li><p>主包文件，其中包含排序过程中捕获的资产和状态信息。</p></li>
<li><p>程序包文件的体系结构、发布信息和注册表（在传递时可重新应用至计算机和特定用户）的标记化表单。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>.MSI</p></td>
<td align="left"><p>可执行部署包装，可用于手动或使用第三方部署平台部署 .appv 文件。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>_DeploymentConfig.XML</p></td>
<td align="left"><p>用于自定义程序包中所有应用程序的默认发布参数的文件，该包全局部署到运行 App-V 客户端的计算机上的所有用户。</p></td>
</tr>
<tr class="even">
<td align="left"><p>_UserConfig.XML</p></td>
<td align="left"><p>用于自定义包中所有应用程序的发布参数的文件，这些应用程序部署到运行 App-V 客户端的计算机上的特定用户。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Report.xml</p></td>
<td align="left"><p>排序过程生成的消息摘要，包括省略的驱动程序、文件和注册表位置。</p></td>
</tr>
<tr class="even">
<td align="left"><p>.CAB</p></td>
<td align="left"><p><em>可选 </em> ：用于自动重新生成以前排序的虚拟应用程序包的包加速器文件。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>.appvt</p></td>
<td align="left"><p><em>可选： </em> 用于保留通常重复使用的 Sequencer 设置的 Sequencer 模板文件。</p></td>
</tr>
</tbody>
</table>

 

有关排序的信息，请参阅 [Application Virtualization 序列化指南](https://go.microsoft.com/fwlink/?LinkID=269810)。

## <a name="whats-in-the-appv-file"></a><a href="" id="bkmk-appv-file-contents"></a>appv 文件中有什么？


appv 文件是一个容器，将 XML 和非 XML 文件一起存储在单个实体中。 此文件基于 AppX 格式生成，该格式基于 OPEN Packaging Conventions (OPC) 标准。

若要查看 appv 文件内容，请制作包的副本，然后将复制的文件重命名为 ZIP 扩展名。

appv 文件包含以下文件夹和文件，这些文件夹和文件在创建和发布虚拟应用程序时使用：

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
<td align="left"><p>包含排序期间捕获的虚拟化应用程序的文件系统的目录。</p></td>
</tr>
<tr class="even">
<td align="left"><p>[Content_Types].xml</p></td>
<td align="left"><p>XML 文件</p></td>
<td align="left"><p>appv 文件中的核心内容类型列表 (例如 DLL、EXE、BIN) 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>AppxBlockMap.xml</p></td>
<td align="left"><p>XML 文件</p></td>
<td align="left"><p>appv 文件的布局，它使用 File、Block 和 BlockMap 元素，这些元素启用 App-V 包中文件的位置和验证。</p></td>
</tr>
<tr class="even">
<td align="left"><p>AppxManifest.xml</p></td>
<td align="left"><p>XML 文件</p></td>
<td align="left"><p>包含添加、发布和启动程序包所需信息的程序包的元数据。 包括扩展 (文件类型关联和快捷方式) 包关联的名称和 GUID。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>FilesystemMetadata.xml</p></td>
<td align="left"><p>XML 文件</p></td>
<td align="left"><p>排序期间捕获的文件列表，包括属性 (，例如目录、文件、不透明目录、空目录以及长名称和短名称) 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>PackageHistory.xml</p></td>
<td align="left"><p>XML 文件</p></td>
<td align="left"><p>有关排序计算机 (操作系统版本、Internet Explorer 版本、.Net Framework 版本) 以及处理 (升级、程序包版本) 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Registry.dat</p></td>
<td align="left"><p>DAT 文件</p></td>
<td align="left"><p>在程序包的排序过程中捕获的注册表项和值。</p></td>
</tr>
<tr class="even">
<td align="left"><p>StreamMap.xml</p></td>
<td align="left"><p>XML 文件</p></td>
<td align="left"><p>主功能块和发布功能块的文件列表。 发布功能块包含用于发布包的 ICO 文件和 (EXE) DLL 文件部分。 存在此参数时，主要功能块包括已在排序过程中针对流式处理进行了优化的文件。</p></td>
</tr>
</tbody>
</table>

 

## <a name="app-v-client-data-storage-locations"></a><a href="" id="bkmk-files-data-storage"></a>App-V 客户端数据存储位置


App-V 客户端执行任务以确保虚拟应用程序正常运行，并像本地安装的应用程序一样工作。 打开和运行虚拟应用程序的过程需要从虚拟文件系统和注册表进行映射，以确保应用程序具有用户期望的传统应用程序所需的组件。 本节介绍运行虚拟应用程序所需的资产，并列出 App-V 存储资产的位置。

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
<td align="left"><p>只读包文件的默认位置</p></td>
</tr>
<tr class="even">
<td align="left"><p>计算机目录</p></td>
<td align="left"><p>%ProgramData%\Microsoft\AppV\Client\Catalog</p></td>
<td align="left"><p>包含每台计算机的配置文档</p></td>
</tr>
<tr class="odd">
<td align="left"><p>用户目录</p></td>
<td align="left"><p>%AppData%\Microsoft\AppV\Client\Catalog</p></td>
<td align="left"><p>包含每用户配置文档</p></td>
</tr>
<tr class="even">
<td align="left"><p>快捷备份</p></td>
<td align="left"><p>%AppData%\Microsoft\AppV\Client\Integration\ShortCutBackups</p></td>
<td align="left"><p>存储支持在程序包取消发布上还原的以前集成点</p></td>
</tr>
<tr class="odd">
<td align="left"><p>在写入时复制 (或) 进行复制</p></td>
<td align="left"><p>%AppData%\Microsoft\AppV\Client\VFS</p></td>
<td align="left"><p>程序包修改的可写漫游位置</p></td>
</tr>
<tr class="even">
<td align="left"><p>在本地写入时 (的) </p></td>
<td align="left"><p>%LocalAppData%\Microsoft\AppV\Client\VFS</p></td>
<td align="left"><p>用于包修改的可写非漫游位置</p></td>
</tr>
<tr class="odd">
<td align="left"><p>计算机注册表</p></td>
<td align="left"><p>HKLM\Software\Microsoft\AppV</p></td>
<td align="left"><p>包含程序包状态信息，包括计算机或全局发布的程序包的 VReg (计算机配置单元) </p></td>
</tr>
<tr class="even">
<td align="left"><p>用户注册表</p></td>
<td align="left"><p>HKCU\Software\Microsoft\AppV</p></td>
<td align="left"><p>包含用户包状态信息，包括 VReg</p></td>
</tr>
<tr class="odd">
<td align="left"><p>用户注册表类</p></td>
<td align="left"><p>HKCU\Software\Classes\AppV</p></td>
<td align="left"><p>包含其他用户包状态信息</p></td>
</tr>
</tbody>
</table>

 

下表和整个文档中的部分提供了表的其他详细信息。

### <a name="package-store"></a>程序包存储

App-V 客户端管理程序包存储中装载的应用程序资产。 此默认存储位置是 ，但您可以在安装期间或之后使用 PowerShell 命令对其进行配置，此命令将修改注册表项下 (`%ProgramData%\App-V` `Set-AppVClientConfiguration` `PackageInstallationRoot` 注册表 `HKLM\Software\Microsoft\AppV\Client\Streaming`) 。 程序包存储必须位于客户端操作系统上的本地路径。 单个程序包存储在程序包存储中，这些子目录以 Package GUID 和 Version GUID 命名。

特定应用程序的路径示例：

``` syntax
C:\ProgramData\App-V\PackGUID\VersionGUID
```

若要在安装期间更改程序包存储的默认位置，请参阅 [如何部署 App-V 客户端](how-to-deploy-the-app-v-client-51gb18030.md)。

### <a name="shared-content-store"></a>共享内容存储

如果在共享内容存储模式下配置 App-V 客户端，则当发生流错误时不会将数据写入磁盘，这意味着包在发布数据存储区时需要最少的本地 (空间) 。 在 VDI 环境中，最好使用较少的磁盘空间，因为本地存储可能会受到限制，并且最好从高性能网络位置流式传输应用程序 (如 SAN) 流。 有关共享内容存储模式详细信息，请参阅 <https://go.microsoft.com/fwlink/p/?LinkId=392750> 。

**注意**  
计算机和程序包存储必须位于本地驱动器上，即使您对 App-V 客户端使用共享内容存储配置时也必须位于该驱动器上。

 

### <a name="package-catalogs"></a>包目录

App-V 客户端管理以下两个基于文件的位置：

-   **用户 (计算机目录) 。**

-   **注册表位置** - 取决于程序包的发布目标。 为计算机 (目录) 目录，以及每个用户的目录。 计算机目录存储适用于所有用户或任何用户的全局信息，用户目录存储适用于特定用户的信息。 Catalog 是动态配置和清单文件的集合;每个程序包版本的文件和注册表都有离散数据。 

### <a name="machine-catalog"></a>计算机目录

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>描述</p></td>
<td align="left"><p>在添加和发布程序包时，存储计算机上可供用户使用的程序包文档。 但是，如果包在发布时是"全局"的，则集成可供所有用户使用。</p>
<p>如果包是非全局的，则仅为特定用户发布集成，但客户端计算机上的任何人仍可以修改和查看全局资源 (例如，包目录位于共享磁盘位置) 。</p>
<p>如果程序包可供使用全局或非全局 (的计算机上的用户) 清单存储在计算机目录中。 在全局发布包时，有一个存储在计算机目录中的动态配置文件;因此，根据计算机目录中是否有策略文件 (UserDeploymentConfiguration) 定义包是否是全局的。</p></td>
</tr>
<tr class="even">
<td align="left"><p>默认存储位置</p></td>
<td align="left"><p><code>%programdata%\Microsoft\AppV\Client\Catalog&lt;/code&gt;</p>
<p>此位置与程序包存储位置不同。 程序包存储是程序包文件的黄金或黄金副本。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>计算机目录中的文件</p></td>
<td align="left"><ul>
<li><p>Manifest.xml</p></li>
<li><p>DeploymentConfiguration.xml</p></li>
<li><p>UserManifest.xml (全局发布的程序包) </p></li>
<li><p>UserDeploymentConfiguration.xml (全局发布的程序包) </p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>其他计算机目录位置，在程序包为连接组的一部分时使用</p></td>
<td align="left"><p>除了上面提到的特定程序包位置之外，还有以下位置：</p>
<p><code>%programdata%\Microsoft\AppV\Client\Catalog\PackageGroups\ConGroupGUID\ConGroupVerGUID</code></p></td>
</tr>
<tr class="odd">
<td align="left"><p>当包是连接组的一部分时计算机目录中的其他文件</p></td>
<td align="left"><ul>
<li><p>PackageGroupDescriptor.xml</p></li>
<li><p>UserPackageGroupDescriptor.xml (全局发布的连接组) </p></li>
</ul></td>
</tr>
</tbody>
</table>

 

### <a name="user-catalog"></a>用户目录

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>描述</p></td>
<td align="left"><p>在发布过程中创建。 包含用于发布程序包的信息，也包含在启动时用于确保将包预配到特定用户。 在漫游位置创建，包括特定于用户的发布信息。</p>
<p>为用户发布包时，策略文件将存储在用户目录中。 同时，清单副本也存储在用户目录中。 为用户删除包权利后，相关包文件将从用户目录中删除。 通过查看用户目录，管理员可以查看动态配置文件的存在，这表示该包为该用户授权。</p>
<p>对于漫游用户，用户目录需要位于漫游或共享位置，以默认保留目标用户的旧 App-V 行为。 授权和策略绑定到用户，而不是计算机，因此在预配后，它们应该与用户一起漫游。</p></td>
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
<td align="left"><p>除了上面提到的特定程序包位置之外，还有以下位置：</p>
<p><code>appdata\roaming\Microsoft\AppV\Client\Catalog\PackageGroups\PkgGroupGUID\PkgGroupVerGUID</code></p></td>
</tr>
<tr class="odd">
<td align="left"><p>当包是连接组的一部分时计算机目录中的其他文件</p></td>
<td align="left"><p><code>UserPackageGroupDescriptor.xml</code></p></td>
</tr>
</tbody>
</table>

 

### <a name="shortcut-backups"></a>快捷方式备份

在发布过程中，App-V 客户端将备份所有快捷方式和集成点到 此备份可在包取消发布时将集成点还原到 `%AppData%\Microsoft\AppV\Client\Integration\ShortCutBackups.` 以前的版本。

### <a name="copy-on-write-files"></a>写入文件时复制

程序包存储包含从发布服务器流式传输的程序包文件的原始副本。 在 App-V 应用程序的正常操作过程中，用户或服务可能需要更改文件。 为了保留修复应用程序的能力，不会在程序包存储中进行这些更改，这将删除这些更改。 这些位置（称为 WRITE 时复制 (使用) ，支持漫游和非漫游位置。 存储修改的位置取决于应用程序已编程以在本机体验中写入更改的位置。

### <a name="cow-roaming"></a>ROAM 漫游

上述的 ROAM 漫游位置存储针对典型 %AppData% 位置或 \\Users\\{username}\\AppData\\Roaming 位置的文件和目录的更改。 然后，这些目录和文件根据操作系统设置进行漫游。

### <a name="cow-local"></a>LOCAL 本地

但即使已配置漫游支持，但 DIRECTORIES 本地位置类似于漫游位置，但目录和文件不会漫游到其他计算机。 上述的更新本地位置存储适用于典型窗口的更改，而不是 %AppData% 位置。 列出的目录将有所不同，但任何典型的 Windows 位置 (例如 Common AppData 和 Common AppDataS) 。 S **** 表示虚拟服务以与登录用户不同的提升用户身份请求更改时受限制的位置。 非**S 位置** 存储基于用户的更改。

## <a name="package-registry"></a><a href="" id="bkmk-pkg-registry"></a>包注册表


在应用程序可以访问包注册表数据之前，App-V 客户端必须将包注册表数据提供给应用程序。 App-V 客户端使用真实注册表作为所有注册表数据的备份存储。

将新包添加到 App-V 客户端时，即为 REGISTRY 的副本。包中的 DAT 文件是在 中创建的 `%ProgramData%\Microsoft\AppV\Client\VREG\{Version GUID}.dat` 。 文件的名称是具有 的版本 GUID。DAT 扩展。 创建此副本的原因是为了确保包中的实际配置单元文件永远不会使用，这将阻止稍后删除包。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>程序包存储中的 Registry.dat</strong></p></td>
<td align="left"><p><strong> &gt; </strong></p></td>
<td align="left"><p><strong>%ProgramData%\Microsoft\AppV\Client\Vreg{VersionGuid}.dat</strong></p></td>
</tr>
</tbody>
</table>

 

当在客户端上启动包的第一个应用程序时，客户端会从配置单元文件中分步或复制内容，在备用位置重新创建包注册表数据 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\AppV\Client\Packages\PackageGuid\Versions\VersionGuid\REGISTRY` 。 The staged registry data has two distinct types of machine data and user data. 计算机上所有用户共享计算机数据。 将每个用户的用户数据分步到用户特定位置 `HKCU\Software\Microsoft\AppV\Client\Packages\PackageGuid\Registry\User` 。 计算机数据最终在程序包删除时删除，用户取消发布操作上的用户数据将被删除。

### <a name="package-registry-staging-vs-connection-group-registry-staging"></a>包注册表暂存与连接组注册表暂存

当存在连接组时，上一个暂存注册表的过程将保持 true，但存在多个配置单元文件，而不是处理一个配置单元文件。 文件按照它们在连接组 XML 中的显示顺序进行处理，第一个编写器会赢得任何冲突。

The staged registry persists the same way as in the single package case. 将保留连接组的分步用户注册表数据，直到该数据被禁用;删除连接组时，将删除分步计算机注册表数据。

### <a name="virtual-registry"></a>虚拟注册表

VREG (虚拟注册表) 为应用程序提供包注册表和本机注册表的单个合并视图。 它还提供写入时复制 (功能) ，即从虚拟进程上下文对注册表进行的任何更改都对单独的一个"安装"位置进行更改。 这意味着 VREG 必须将最多三个单独的注册表位置组合到一个视图中，该视图基于注册表的 POPULAT - package - native 中的填充 &gt; &gt; 位置。 当对注册表数据提出请求时，它将按顺序排列，直到找到所请求的数据。 这意味着，如果一个值存储在一个更新位置，则它将不会继续到其他位置，但是，如果这些位置没有数据，它将继续打包，然后是本机位置，直到找到相应的数据。

### <a name="registry-locations"></a>注册表位置

App-V 客户端存储注册表信息的位置有两个程序包注册表位置和两个连接组位置，具体取决于程序包是单独发布还是作为连接组的一部分发布。 程序包有三个（一个为一个，三个为连接组）的位置，这些位置由 VREG 创建和管理。 设置包和连接组不共享：

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
<td align="left"><p><strong>一些</strong></p></td>
<td align="left"><ul>
<li><p>Machine Registry\Client\Packages\PkgGUID\REGISTRY (只有提升进程才能写入) </p></li>
<li><p>User Registry\Client\Packages\PkgGUID\REGISTRY (在 HKCU 下写入除 Software\Classes 之外的所有内容的用户漫游</p></li>
<li><p>用户注册表类\Client\Packages\PkgGUID\REGISTRY (HKCU\Software\Classes 针对非提升的进程编写和 HKLM) </p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>包</strong></p></td>
<td align="left"><ul>
<li><p>Machine Registry\Client\Packages\PkgGUID\Versions\VerGuid\Registry\Machine</p></li>
<li><p>User Registry Classes\Client\Packages\PkgGUID\Versions\VerGUID\Registry</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><strong>本机</strong></p></td>
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
<td align="left"><p><strong>一些</strong></p></td>
<td align="left"><ul>
<li><p>Machine Registry\Client\PackageGroups\GrpGUID\REGISTRY (只有提升进程才能写入) </p></li>
<li><p>User Registry\Client\PackageGroups\GrpGUID\REGISTRY (任何写入 HKCU 的内容（Software\Classes 除外）</p></li>
<li><p>User Registry Classes\Client\PackageGroups\GrpGUID\REGISTRY</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>包</strong></p></td>
<td align="left"><ul>
<li><p>Machine Registry\Client\PackageGroups\GrpGUID\Versions\VerGUID\REGISTRY</p></li>
<li><p>User Registry Classes\Client\PackageGroups\GrpGUID\Versions\VerGUID\REGISTRY</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><strong>本机</strong></p></td>
<td align="left"><ul>
<li><p>本机应用程序注册表位置</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

 

HKLM 有两个"安装"位置;提升和非提升的进程。 提升的进程始终将 HKLM 更改写入 HKLM 下的安全的 ELEVAT。 非提升的进程始终将 HKLM 更改写入 HKCU\\Software\\Classes 下的非安全的"未提升的""。。 当应用程序从 HKLM 读取更改时，提升的进程会从 HKLM 下的安全的"设计"中读取更改。 非提升读取两者，首先支持在不安全的 UNSECURE 中所做的更改。

### <a name="pass-through-keys"></a>传递键

通过传递项，管理员可以配置某些项，以便只能从本机注册表中读取它们，同时绕过 Package 和一些安装位置。 传递位置是计算机全局的 (而不是特定于程序包的) 并且可以通过向密钥添加路径进行配置，该路径应视为传递到名为**PassThroughPaths**的密钥 的**REG\_MULTI\_SZ**值 `HKLM\Software\Microsoft\AppV\Subsystem\VirtualRegistry` 。 在此多字符串值下显示的任何键 (及其子) 将视为传递。

默认情况下，以下位置配置为传递位置：

-   HKEY\_CURRENT\_USER\\SOFTWARE\\Classes\\Local 设置\\Software\\Microsoft\\Windows\\CurrentVersion\\AppModel

-   HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Classes\\Local 设置\\Software\\Microsoft\\Windows\\CurrentVersion\\AppModel

-   HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WINEVT

-   HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\services\\eventlog\\Application

-   HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Control\\WMI\\Autologger

-   HKEY\_CURRENT\_USER\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet 设置

-   HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Perflib

-   HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Policies

-   HKEY\_CURRENT\_USER\\SOFTWARE\\Policies

传递项的目的是确保虚拟应用程序不会在 VReg 中写入非虚拟应用程序成功操作或集成所需的注册表数据。 Policies 键确保利用管理员设置的基于组策略的设置，而不是每个程序包设置。 AppModel 键与基于 UI 的新式Windows集成是必需的。 建议管理程序不要修改任何默认传递键，但在某些情况下，基于应用程序行为可能需要添加其他传递密钥。

## <a name="app-v-package-store-behavior"></a><a href="" id="bkmk-pkg-store-behavior"></a>App-V 程序包存储行为


App-V 5 管理程序包存储，它是存储 appv 文件中扩展的资产文件的位置。 默认情况下，此位置存储在 %ProgramData%\\App-V 中，并且仅在存储功能方面受限于可用磁盘空间。 程序包存储按程序包和版本的 GUID 组织，如上一节所述。

### <a name="add-packages"></a>添加程序包

App-V 程序包在计算机使用 App-V 客户端时进行分步。 App-V 客户端提供按需暂存。 在发布或手动 Add-AppVClientPackage 过程中，数据结构内置在程序包存储 (c：\\programdata\\App-V\\{PkgGUID}\\{VerGUID}) 。 在 StreamMap.xml 中定义的发布块中标识的包文件将添加到系统中，并且顶级文件夹和子文件会进行分步，以确保在启动时存在适当的应用程序资产。

### <a name="mounting-packages"></a>装载程序包

程序包可以使用 PowerShell 或 `Mount-AppVClientPackage` **App-V** 客户端 UI 显式加载以下载程序包。 此操作将整个包完全加载至程序包存储中。

### <a name="streaming-packages"></a>流式处理包

App-V 客户端可以配置为更改流式处理的默认行为。 所有流式处理策略都存储在以下注册表项下 `HKEY_LOCAL_MAcHINE\Software\Microsoft\AppV\Client\Streaming` ：。 策略是使用 PowerShell cmdlet 设置的 `Set-AppvClientConfiguration` 。 以下策略适用于流式处理：

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
<td align="left"><p>在 Windows 8 及更高版本上，它允许通过 3G 和手机网络流式传输</p></td>
</tr>
<tr class="even">
<td align="left"><p>AutoLoad</p></td>
<td align="left"><p>指定后台加载设置：</p>
<p><strong>0 </strong> - 已禁用</p>
<p><strong>1 </strong> – 仅以前使用的程序包</p>
<p><strong>2 </strong> – 所有程序包</p></td>
</tr>
<tr class="odd">
<td align="left"><p>PackageInstallationRoot</p></td>
<td align="left"><p>本地计算机中程序包存储的根文件夹</p></td>
</tr>
<tr class="even">
<td align="left"><p>PackageSourceRoot</p></td>
<td align="left"><p>应从其中流式传输包的根替代</p></td>
</tr>
<tr class="odd">
<td align="left"><p>SharedContentStoreMode</p></td>
<td align="left"><p>允许对 VDI 方案使用共享内容存储</p></td>
</tr>
</tbody>
</table>

 

 

这些设置影响将 App-V 包资产流式处理到客户端的行为。 默认情况下，App-V 仅在下载初始发布和主要功能块后下载所需的资产。 必须说明流式处理包的三种特定行为：

-   后台流式处理

-   优化的流式处理

-   流故障

### <a name="background-streaming"></a>后台流式处理

PowerShell cmdlet 可用于确定使用"自动加载"设置进行后台流式处理的当前模式，并且使用 cmdlet Set-AppvClientConfiguration 或注册表 `Get-AppvClientConfiguration` (HKLM\\SOFTWARE\\Microsoft\\AppV\\ClientStreaming 项) 进行修改。 后台流是默认设置，其中自动加载设置设置为下载之前使用的程序包。 基于默认设置的行为 (value=1) 启动应用程序后在后台下载 App-V 数据块。 此设置可以一起禁用 (value=0) ，也可以针对所有程序包 (value=2) 启用，无论它们是否已启动。

### <a name="optimized-streaming"></a>优化的流式处理

在排序过程中，可以使用主要功能块配置 App-V 包。 此设置允许排序工程师监视特定应用程序或应用程序的启动文件，并标记 App-V 包中的数据块，以在程序包中任何应用程序首次启动时进行流式处理。

### <a name="stream-faults"></a>流故障

在任何发布数据的初始流和主要功能块之后，其他文件的请求将执行流错误。 这些数据块将根据需要下载到程序包存储。 这允许用户仅下载程序包的一小部分，通常足以启动程序包并运行常规任务。 当用户启动需要当前不在程序包存储中数据的操作时，将下载所有其他块。

有关 App-V 程序包流式处理的信息，请访问： <https://go.microsoft.com/fwlink/?LinkId=392770> 。

流优化的排序方法位于 <https://go.microsoft.com/fwlink/?LinkId=392771> ：。

### <a name="package-upgrades"></a>程序包升级

App-V 包要求在应用程序的整个生命周期内进行更新。 App-V 程序包升级类似于程序包发布操作，因为每个版本都将在其自己的 PackageRoot 位置创建 `%ProgramData%\App-V\{PkgGUID}\{newVerGUID}` ：。 通过从同一程序包的其他版本创建指向相同文件和流式文件的硬链接来优化升级操作。

### <a name="package-removal"></a>包删除

删除程序包时 App-V 客户端的行为取决于用于删除的方法。 使用 App-V 完整基础结构取消发布应用程序，将删除全局发布应用程序 (计算机目录中的用户目录文件) ，但会保留程序包存储位置和一些用户目录位置。 当 PowerShell cmdlet 用于删除 `Remove-AppVClientPackge` App-V 程序包时，将清除程序包存储位置。 请记住，从管理服务器取消发布 App-V 包不会执行删除操作。 这两个操作均不会删除程序包存储包文件。

## <a name="roaming-registry-and-data"></a><a href="" id="bkmk-roaming-reg-data"></a>漫游注册表和数据


App-V 5 能够在漫游时提供接近本机的体验，具体取决于所使用的应用程序的编写方式。 默认情况下，App-V 根据操作系统的漫游配置来漫游存储在漫游位置中的 AppData。 用于存储基于文件的数据的其他位置不会在计算机间漫游，因为它们位于未漫游的位置。

### <a name="roaming-requirements-and-user-catalog-data-storage"></a><a href="" id="bkmk-clt-inter-roam-reqs"></a>漫游要求和用户目录数据存储

App-V 以以下形式存储表示用户目录状态的数据：

-   %appdata%\\Microsoft\\AppV\\Client\\Catalog 下的文件

-   下的注册表设置 `HKEY_CURRENT_USER\Software\Microsoft\AppV\Client\Packages`

这些文件和注册表设置共同表示用户的目录，因此两者都必须漫游，或者两者均不能为给定用户漫游。 App-V 不支持漫游 %AppData%，但不支持在注册表 (漫游用户配置文件) ，反之亦然。

**注意**  
**Repair-AppvClientPackage** cmdlet 不修复包的发布状态，其中用户的 App-V 状态缺失或与 `HKEY_CURRENT_USER` %appdata% 中的数据不匹配。

 

### <a name="registry-based-data"></a>基于注册表的数据

App-V 注册表漫游分为两种方案，如下表所示。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">方案</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>作为标准用户运行的应用程序</p></td>
<td align="left"><p>当标准用户启动 App-V 应用程序时，HKLM 和 HKCU for App-V 应用程序都存储在该计算机上 HKCU 配置单元中。 这表示为两个不同的路径：</p>
<ul>
<li><p>HKLM：HKCU\SOFTWARE\Classes\AppV\Client\Packages{PkgGUID}\REGISTRY\MACHINE\SOFTWARE</p></li>
<li><p>HKCU：HKCU\SOFTWARE\Microsoft\AppV\Client\Packages{PkgGUID}\REGISTRY\USER{UserSID}\SOFTWARE</p></li>
</ul>
<p>位置根据操作系统设置启用漫游。</p></td>
</tr>
<tr class="even">
<td align="left"><p>使用提升权限运行的应用程序</p></td>
<td align="left"><p>当通过提升权限启动应用程序时：</p>
<ul>
<li><p>HKLM 数据存储在本地计算机的 HKLM 配置单元中</p></li>
<li><p>HKCU 数据存储在用户注册表位置</p></li>
</ul>
<p>在此方案中，这些设置不会随正常的操作系统漫游配置一起漫游，生成的注册表项和值将存储在以下位置：</p>
<ul>
<li><p>HKLM\SOFTWARE\Microsoft\AppV\Client\Packages{PkgGUID}{UserSID}\REGISTRY\MACHINE\SOFTWARE</p></li>
<li><p>HKCU\SOFTWARE\Microsoft\AppV\Client\Packages{PkgGUID}\Registry\User{UserSID}\SOFTWARE</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

### <a name="app-v-and-folder-redirection"></a>App-V 和文件夹重定向

App-V 5.1 支持漫游 AppData 文件夹的文件夹重定向 (%AppData%) 。 当虚拟环境启动时，用户的漫游 AppData 目录中的漫游 AppData 状态将复制到本地缓存。 相反，当虚拟环境关闭时，与特定用户的漫游 AppData 关联的本地缓存将传输到该用户的漫游 AppData 目录的实际位置。

对于 AppData\\Local 和 AppData\\Roaming 中的设置，典型包具有多个映射在用户支持存储中的位置。 这些位置是按用户存储在用户配置文件中的"写入时复制"位置，用于存储对程序包 VFS 目录所做的更改和保护默认包 VFS。

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
<td align="left"><p>C：\users\jsmith\AppData &lt; strong &gt; Local </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \ProgramFilesX86</p></td>
</tr>
<tr class="even">
<td align="left"><p>SystemX86</p></td>
<td align="left"><p>C：\users\jsmith\AppData &lt; strong &gt; Local </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \SystemX86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows</p></td>
<td align="left"><p>C：\users\jsmith\AppData &lt; strong &gt; Local </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \Windows</p></td>
</tr>
<tr class="even">
<td align="left"><p>appv_ROOT</p></td>
<td align="left"><p>C：\users\jsmith\AppData &lt; strong &gt; Local </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \appv_ROOT</p></td>
</tr>
<tr class="odd">
<td align="left"><p>AppData</p></td>
<td align="left"><p>C：\users\jsmith\AppData &lt; &gt; strong Roaming </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \AppData</p></td>
</tr>
</tbody>
</table>

 

 

下表显示了本地和漫游位置，当为 %AppData% 实现文件夹重定向时，该位置 (通常重定向到网络位置) 。

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
<td align="left"><p>C：\users\jsmith\AppData &lt; strong &gt; Local </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \ProgramFilesX86</p></td>
</tr>
<tr class="even">
<td align="left"><p>SystemX86</p></td>
<td align="left"><p>C：\users\jsmith\AppData &lt; strong &gt; Local </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \SystemX86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows</p></td>
<td align="left"><p>C：\users\jsmith\AppData &lt; strong &gt; Local </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \Windows</p></td>
</tr>
<tr class="even">
<td align="left"><p>appv_ROOT</p></td>
<td align="left"><p>C：\users\jsmith\AppData &lt; strong &gt; Local </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \appv_ROOT</p></td>
</tr>
<tr class="odd">
<td align="left"><p>AppData</p></td>
<td align="left"><p><strong>\Fileserver </strong> \users\jsmith\roaming\Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \AppData</p></td>
</tr>
</tbody>
</table>

 

 

当前的 App-V 客户端 VFS 驱动程序无法写入网络位置，因此 App-V 客户端会在发布期间和虚拟环境启动时检测是否存在文件夹重定向，并复制本地驱动器上的数据。 在用户关闭 App-V 应用程序并且 App-V 客户端关闭虚拟环境后，VFS AppData 的本地存储将复制回网络，从而允许漫游到将重复该过程的其他计算机。 过程的详细步骤如下：

1.  在发布或虚拟环境启动期间，App-V 客户端会检测 AppData 目录的位置。

2.  如果漫游 AppData 路径是本地路径或 ino AppData\\Roaming 位置映射路径，则不执行任何操作。

3.  如果漫游 AppData 路径不是本地路径，则 VFS AppData 目录将映射到本地 AppData 目录。

此过程解决了 App-V 客户端 VFS 驱动程序不支持的非本地 %AppData% 的问题。 但是，存储在此新位置的数据不会随文件夹重定向一起漫游。 应用程序运行期间的所有更改都发生在本地 AppData 位置，并且必须复制到重定向的位置。 此过程的详细步骤如下：

1.  App-V 应用程序将关闭，这将关闭虚拟环境。

2.  漫游 AppData 位置的本地缓存被压缩并存储在 ZIP 文件中。

3.  ZIP 打包过程结束时的时间戳用于命名文件。

4.  时间戳记录在注册表中：HKEY\_CURRENT\_USER\\Software\\Microsoft\\AppV\\Client\\Packages\\ &lt; GUID \\AppDataTime 作为上一个已知的 AppData 时间戳。 &gt;

5.  调用文件夹重定向过程以评估和启动上载到漫游 AppData 目录的 ZIP 文件。

如果发生冲突，时间戳用于确定"最后一个编写器获胜"方案，用于在 App-V 应用程序发布或虚拟环境启动时优化数据下载。 文件夹重定向将允许来自支持策略涵盖的其他任何客户端的数据，并启动将 AppData\\Roaming 数据存储到客户端上的本地 AppData 位置的过程。 详细过程如下：

1.  用户通过启动应用程序启动虚拟环境。

2.  应用程序的虚拟环境检查最新的时间戳 ZIP 文件（如果存在）。

3.  检查注册表中上次上传的已知时间戳（如果存在）。

4.  下载最新的 ZIP 文件，除非本地上次已知上传时间戳大于或等于 ZIP 文件的时间戳。

5.  如果本地上次已知上传时间戳早于漫游 AppData 位置中最新 ZIP 文件的时间戳，ZIP 文件将提取到用户配置文件中的本地临时目录。

6.  成功提取 ZIP 文件后，将重命名漫游 AppData 目录的本地缓存，并且新数据将移动到位置。

7.  重命名的目录将被删除，应用程序会使用最近保存的漫游 AppData 数据打开。

这将完成 AppData\\Roaming 位置中的应用程序设置的成功漫游。 唯一必须解决的其他条件是包修复操作。 此过程的详细信息包括：

1.  在修复过程中，检测用户漫游 AppData 目录的路径是否不是本地路径。

2.  映射非本地漫游 AppData 路径目标将重新创建预期的漫游和本地 AppData 位置。

3.  删除注册表中存储的时间戳（如果存在）。

此过程将为 AppData 重新创建本地和网络位置，并删除时间戳的注册表记录。

## <a name="app-v-client-application-lifecycle-management"></a><a href="" id="bkmk-clt-app-lifecycle"></a>App-V 客户端应用程序生命周期管理


在 App-V 完整基础结构中，在应用程序排序后，它们通过 App-V 管理和发布服务器进行管理并发布到用户或计算机。 本节详细介绍在常见的 App-V 应用程序生命周期操作期间发生的操作 (添加、发布、启动、升级和删除) 以及从 App-V 客户端角度更改和修改的文件和注册表位置。 App-V 客户端操作作为在运行 App-V 客户端的计算机上启动的一系列 PowerShell 命令执行。

本文档重点介绍 App-V 完整基础结构解决方案。 有关 App-V 与 Configuration Manager 2012 集成的特定信息，请访问： <https://go.microsoft.com/fwlink/?LinkId=392773> 。

App-V 应用程序生命周期任务在用户登录时触发， (默认) 计算机启动或后台时间操作。 App-V 客户端操作（包括发布服务器、刷新间隔、包脚本启用和其他操作）的设置在客户端设置期间或安装后使用 PowerShell 命令进行配置。 请参阅 TechNet 上的如何部署客户端部分：如何部署 [App-V 客户端](how-to-deploy-the-app-v-client-51gb18030.md) 或利用 PowerShell：

```powershell
get-command *appv*
```

### <a name="publishing-refresh"></a>发布刷新

发布刷新过程由几个在 App-V 客户端上执行的较小操作组成。 由于 App-V 是一种应用程序虚拟化技术，而不是任务计划技术，Windows 任务计划程序可用于在用户登录、计算机启动和按计划间隔启用此过程。 在以上列出的设置过程中配置客户端是向一大组具有正确设置的计算机分发客户端时的首选方法。 可以使用以下 PowerShell cmdlet 配置这些客户端设置：

-   **Add-AppVPublishingServer：** 使用提供 App-V 包的 App-V 发布服务器配置客户端。

-   **Set-AppVPublishingServer：** 修改 App-V 发布服务器的当前设置。

-   **Set-AppVClientConfiguration：** 修改 App-V 客户端的当前设置。

-   **Sync-AppVPublishingServer：** 手动启动 App-V 发布刷新过程。 在配置发布服务器期间创建的计划任务中也会利用这一点。

以下各节重点介绍在 App-V 发布刷新的不同阶段发生的操作。 这些主题包括：

-   添加 App-V 程序包

-   发布 App-V 包

### <a name="adding-an-app-v-package"></a>添加 App-V 包

将 App-V 包添加到客户端是发布刷新过程的第一步。 最终结果与 PowerShell 中的 cmdlet 相同，除非在发布刷新添加过程中，将联系配置的发布服务器，将应用程序高级列表传回客户端以拉取更详细的信息，而不是单个包添加操作。 `Add-AppVClientPackage` 此过程将继续，为程序包或连接组添加或更新配置客户端，然后访问 appv 文件。 接下来，将展开 appv 文件的内容，并放置在适当位置的本地操作系统上。 下面是过程的详细工作流，假定包已配置为容错流。

**如何添加 App-V 程序包**

1.  通过 PowerShell 或任务序列启动发布刷新过程手动启动。

    1.  App-V 客户端建立 HTTP 连接，并基于目标请求应用程序列表。 发布刷新过程支持目标计算机或用户。

    2.  App-V 发布服务器使用启动目标、用户或计算机的身份，并查询数据库中的授权应用程序列表。 应用程序列表作为 XML 响应提供，客户端使用该响应向服务器发送其他请求，以基于每个程序包获取详细信息。

2.  App-V 客户端上的发布代理执行以下序列化的所有操作。

    评估未发布或禁用的任何连接组，因为无法处理属于连接组的程序包版本更新。

3.  通过标识添加或更新操作来配置程序包。

    1.  App-V 客户端从应用程序Windows AppX API，然后从发布服务器访问 appv 文件。

    2.  程序包文件将打开，AppXManifest.xmlStreamMap.xml文件下载到程序包存储。

    3.  完全流式处理发布流中定义的StreamMap.xml。 将发布块数据存储在程序包存储\\PkgGUID\\VerGUID\\Root 中。

        -   图标：扩展点的目标。

        -   可移植可执行 (PE 标头) ：包含磁盘上图像需求的基本信息的扩展点的目标，可直接访问或通过文件类型访问。

        -   脚本：下载脚本目录以在整个发布过程中使用。

    4.  填充程序包存储：

        1.  在磁盘上创建稀疏文件，这些文件表示列出的任何目录的解压缩包。

        2.  将顶级文件和目录放在根目录下。

        3.  当目录在磁盘上列为稀疏并按需流式传输时，将创建所有其他文件。

    5.  创建计算机目录条目。 如果Manifest.xmlDeploymentConfiguration.xml占位符， (包文件创建DeploymentConfiguration.xml和) 。

    6.  在注册表 HKLM\\Software\\Microsoft\\AppV\\Client\\Packages\\PkgGUID\\Versions\\VerGUID\\Catalog 中创建程序包存储的位置

    7.  将 Registry.dat 文件从程序包存储创建到 %ProgramData%\\Microsoft\\AppV\\Client\\VReg\\{VersionGUID}.dat

    8.  使用 App-V 内核模式驱动程序 HKLM\\Microsoft\\Software\\AppV\\MAV 注册程序包

    9.  从程序包添加计时AppxManifest.xml或DeploymentConfig.xml文件调用脚本。

4.  通过添加和启用或禁用来配置连接组。

5.  删除未发布到目标用户或计算机 (对象) 。

    **注意**  
    这将不执行程序包删除，而是删除特定目标 (用户或计算机) 的集成点，并删除全局发布的 (计算机目录文件的用户) 。

     

6.  根据客户端配置调用后台负载装载。

7.  将立即还原已具有计算机或用户的发布信息的程序包。

    **注意**  
    此条件作为删除产品发生，无需通过后台添加包取消发布。

     

这将完成发布刷新过程的 App-V 程序包添加。 下一步是将程序包发布到计算机或用户 (特定) 。

![包添加文件和注册表数据。](images/packageaddfileandregistrydata.png)

### <a name="publishing-an-app-v-package"></a>发布 App-V 包

在发布刷新操作期间，特定发布操作 (Publish-AppVClientPackage) 会将条目添加到用户目录、将权利映射到用户、标识本地存储，然后完成所有集成步骤。 以下是详细步骤。

**如何发布和 App-V 包**

1.  程序包条目将添加到用户目录

    1.  用户目标包：UserDeploymentConfiguration.xml和UserManifest.xml放置在用户目录中的计算机上

    2.  面向全局 (包) ：UserDeploymentConfiguration.xml位于计算机目录中

2.  在 HKLM\\Software\\Microsoft\\AppV\\MAV 上为用户注册内核模式驱动程序包

3.  执行集成任务。

    1.  创建扩展点。

    2.  将备份信息存储在用户的注册表和漫游配置文件中 (快捷方式备份) 。

        **注意**  
        如果包未发布，这将启用还原扩展点。

         

    3.  运行面向发布计时的脚本。

发布属于连接组的 App-V 包的过程与上述过程非常相似。 对于连接组，存储特定目录信息的路径包括 PackageGroups 作为目录目录的子项。 有关详细信息，请查看上面的计算机和用户目录信息。

![包添加文件和注册表数据 - 全局。](images/packageaddfileandregistrydata-global.png)

### <a name="application-launch"></a>应用程序启动

在发布刷新过程之后，用户启动并随后重新启动 App-V 应用程序。 此过程非常简单，并且经过优化，以使用最少的网络流量快速启动。 App-V 客户端检查在发布期间创建的文件的用户目录的路径。 建立启动程序包权限后，App-V 客户端将创建一个虚拟环境，开始流式处理任何必要数据，并应用虚拟环境创建期间的适当清单和部署配置文件。 为特定包和应用程序创建和配置虚拟环境后，应用程序将启动。

**如何启动 App-V 应用程序**

1.  用户通过单击快捷方式或文件类型调用来启动应用程序。

2.  App-V 客户端验证用户目录中是否存在以下文件

    -   UserDeploymentConfiguration.xml

    -   UserManifest.xml

3.  如果存在这些文件，则该应用程序将授权给该特定用户，应用程序将启动启动过程。 此时没有网络流量。

4.  接下来，App-V 客户端检查注册表中是否找到为 App-V 客户端服务注册的程序包的路径。

5.  找到程序包存储的路径后，将创建虚拟环境。 如果这是首次启动，则主要功能阻止将下载（如果存在）。

6.  下载后，App-V 客户端服务使用清单和部署配置文件来配置虚拟环境，并加载所有 App-V 子系统。

7.  应用程序启动。 对于程序包存储中任何缺失的文件 (稀疏) ，App-V 将根据需要对文件进行流式处理。

    ![包添加文件和注册表数据 - 流。](images/packageaddfileandregistrydata-stream.png)

### <a name="upgrading-an-app-v-package"></a>升级 App-V 程序包

App-V 5 程序包升级过程与旧版 App-V 不同。 App-V 在授权给不同用户的计算机上支持同一程序包的多个版本。 程序包存储和目录使用新资源更新时，随时都可以添加程序包版本。 特定于增加新版本资源的唯一过程是存储优化。 在升级过程中，仅将新文件添加到新版本存储位置，并针对未更改的文件创建硬链接。 这可减少总存储量，只需在一个磁盘位置显示文件，然后在磁盘上使用文件位置条目将文件计划到所有文件夹中。 以下是升级 App-V 程序包的具体详细信息：

**如何升级 App-V 程序包**

1.  App-V 客户端执行发布刷新并发现较新版本的 App-V 程序包。

2.  程序包条目将添加到新版本的适当目录中

    1.  用户目标程序包：UserDeploymentConfiguration.xml 和 UserManifest.xml 位于 appdata\\roaming\\Microsoft\\AppV\\Client\\Catalog\\Packages\\PkgGUID\\VerGUID 上的用户目录中

    2.  面向全局 (包) 计算机：UserDeploymentConfiguration.xml 位于 %programdata%\\Microsoft\\AppV\\Client\\Catalog\\Packages\\PkgGUID\\VerGUID

3.  在 HKLM\\Software\\Microsoft\\AppV\\MAV 上为用户注册内核模式驱动程序包

4.  执行集成任务。

    -   将扩展点 (清单) 动态配置文件中的 EP 文件。

    1.  基于文件的 EP 数据存储在 AppData 文件夹中，该文件夹利用程序包存储中的节点。

    2.  版本 1 在新版本可用时已存在 EPS。

    3.  扩展点将切换到计算机或用户目录中的任何更新或更新的扩展点的"版本 2"位置。

5.  运行面向发布计时的脚本。

6.  安装并排程序集（如果需要）。

### <a name="upgrading-an-in-use-app-v-package"></a>升级使用中的 App-V 程序包

**从 App-V 5 SP2**开始：如果尝试升级最终用户使用的包，升级任务将处于挂起状态。 升级将稍后根据以下规则运行：

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
<td align="left"><p>基于用户的任务，例如，向用户发布包</p></td>
<td align="left"><p>在用户注销然后重新登录后，将执行待定任务。</p></td>
</tr>
<tr class="even">
<td align="left"><p>基于全局的任务，例如，在全局启用连接组</p></td>
<td align="left"><p>当计算机关闭然后重新启动时，将执行挂起的任务。</p></td>
</tr>
</tbody>
</table>

 

当任务处于待定状态时，App-V 客户端还会为待定任务生成注册表项，如下所示：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">基于用户或基于全局的任务</th>
<th align="left">生成注册表项的地方</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>基于用户的任务</p></td>
<td align="left"><p>KEY_CURRENT_USER\Software\Microsoft\AppV\Client\PendingTasks</p></td>
</tr>
<tr class="even">
<td align="left"><p>基于全局的任务</p></td>
<td align="left"><p>HKEY_LOCAL_MACHINE\Software\Microsoft\AppV\Client\PendingTasks</p></td>
</tr>
</tbody>
</table>

 

用户必须先完成以下操作，然后才能使用较新版本的程序包：

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
<td align="left"><p>此任务特定于计算机，你可通过完成上述"程序包添加"部分中的步骤随时执行它。</p></td>
</tr>
<tr class="even">
<td align="left"><p>发布程序包</p></td>
<td align="left"><p>有关步骤，请参阅上面的程序包发布部分。 此过程要求您更新系统的扩展点。 完成此任务后，最终用户无法使用该应用程序。</p></td>
</tr>
</tbody>
</table>

 

使用以下示例方案作为更新程序包的指南。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">方案</th>
<th align="left">要求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>尝试升级时，App-V 程序包不使用</p></td>
<td align="left"><p>程序包的以下组件均无法使用：虚拟应用程序、COM 服务器或 shell 扩展。</p>
<p>管理员发布较新版本的程序包，并且升级将在下次启动包内的组件或应用程序时运行。 将流式传输并运行新版本的程序包。 在 App-V 5 SP2 的此方案中，与以前版本 App-V 5 相比没有任何变化。</p></td>
</tr>
<tr class="even">
<td align="left"><p>当管理员发布较新版本的程序包时，App-V 程序包在使用中</p></td>
<td align="left"><p>App-V 客户端将升级操作设置为"挂起"，这意味着它将在程序包不使用时排队并稍后执行。</p>
<p>如果包应用程序在使用中，则用户关闭虚拟应用程序，之后将进行升级。</p>
<p>如果包在 2013 (Office 2013) （由 Windows 资源管理器永久加载）的 shell 扩展，则用户无法登录。 用户必须注销并重新登录才能启动 App-V 程序包升级。</p></td>
</tr>
</tbody>
</table>

 

### <a name="global-vs-user-publishing"></a>全局与用户发布

App-V 程序包可通过两种方式之一发布;将 App-V 包授权给特定用户或用户组的用户，以及使计算机所有用户的 App-V 程序包授权给整台计算机的全局用户。 在绘制包升级且 App-V 程序包未使用后，请考虑以下两种类型的发布：

-   **全局发布**：应用程序发布到计算机;该计算机上所有用户都可以使用它。 App-V 客户端服务启动时将进行升级，这实际上意味着计算机重新启动。

-   **用户已发布**：应用程序已发布到用户。 如果计算机上有多个用户，则该应用程序可以发布到用户的子集。 当用户登录或定期再次发布它、 (ConfigMgr 策略刷新和评估或 App-V 定期发布/刷新时，或者通过 PowerShell 命令或) 显式进行升级。

### <a name="removing-an-app-v-package"></a>删除 App-V 程序包

在完整基础结构中删除 App-V 应用程序是一项未发布操作，不会执行包删除。 此过程与上述发布过程相同，但无需添加删除过程，而是会撤消对 App-V 程序包所做的更改。

### <a name="repairing-an-app-v-package"></a>修复 App-V 包

修复操作非常简单，但可能会影响计算机上很多位置。 将删除前面提到的 Write (的 COPY) ，扩展点将被取消集成，然后重新集成。 请查看在注册表中注册的一些位置，查看这些位置的一些数据放置位置。 此操作将自动完成，并且除了从 App-V 客户端控制台或 PowerShell (Repair-AppVClientPackage) 启动修复操作外，没有任何管理控制。

## <a name="integration-of-app-v-packages"></a><a href="" id="bkmk-integr-appv-pkgs"></a>App-V 程序包的集成


App-V 客户端和程序包体系结构在添加和发布程序包期间提供与本地操作系统的特定集成。 三个文件定义 App-V 程序包的集成或扩展点：

-   AppXManifest.xml：在程序包内存储，回退副本存储在程序包存储和用户配置文件中。 包含排序过程中创建的选项。

-   DeploymentConfig.xml：提供计算机和基于用户的集成扩展点的配置信息。

-   UserConfig.xml：仅Deploymentconfig.xml基于用户的配置且仅面向基于用户的扩展点的扩展的子集。

### <a name="rules-of-integration"></a>集成规则

当 App-V 应用程序发布到具有 App-V 客户端的计算机时，将执行一些特定操作，如下面的列表所述：

-   全局发布：快捷方式存储在 All Users 配置文件位置，其他扩展点存储在 HKLM 配置单元的注册表中。

-   用户发布：快捷方式存储在当前用户帐户配置文件中，其他扩展点存储在 HKCU 配置单元的注册表中。

-   备份和还原：现有本机应用程序数据和注册表 (如 FTA 注册) 发布期间进行备份。

    1.  App-V 包基于上一个集成包获得所有权，其中所有权将传递到最新发布的 App-V 应用程序。

    2.  当拥有 App-V 程序包未发布时，所有权从一个 App-V 包转移到另一个程序包。 这不会启动数据或注册表的还原。

    3.  在基于每个扩展点取消发布或删除最后一个包时还原备份的数据。

### <a name="extension-points"></a>扩展点

App-V 发布 (清单和动态) 提供了多个扩展点，使应用程序能够与本地操作系统集成。 这些扩展点执行典型的应用程序安装任务，例如放置快捷方式、创建文件类型关联和注册组件。 由于这些虚拟化应用程序不是以与传统应用程序相同的方式安装，因此存在一些差异。 以下是本节中介绍的扩展点列表：

-   快捷方式

-   文件类型关联

-   Shell 扩展

-   COM

-   软件客户端

-   应用程序功能

-   URL 协议处理程序

-   AppPath

-   虚拟应用程序

### <a name="shortcuts"></a>快捷方式

简短内容是与操作系统集成的基本元素之一，也是直接启动 App-V 应用程序的界面。 在发布和取消发布 App-V 应用程序期间。

在程序包清单和动态配置 XML 文件中，可以在类似于以下内容的部分中找到特定应用程序可执行文件的路径：

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

如前所述，App-V 快捷方式默认基于刷新操作放置在用户配置文件中。 全局刷新将快捷方式放在 All Users 配置文件中，用户刷新将其存储在特定用户配置文件中。 实际的可执行文件存储在程序包存储中。 ICO 文件的位置是 App-V 包中的标记化位置。

### <a name="file-type-associations"></a>文件类型关联

App-V 客户端在发布期间管理本地操作系统文件类型关联，这使用户可以使用文件类型调用或打开具有特定注册扩展名 (.docx) 的文件以启动 App-V 应用程序。 文件类型关联存在于清单和动态配置文件中，如以下示例所示：

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

**注意**  
在本示例中：

-   `<Name>.xdp</Name>` 是扩展

-   `<Name>AcroExch.XDPDoc</Name>` 是 ProgId 值 (，它指向相邻的 ProgId) 

-   `<CommandLine>"[{AppVPackageRoot}]\Reader\AcroRd32.exe" "%1"</CommandLine>` 是指向应用程序可执行文件的命令行

 

### <a name="shell-extensions"></a>Shell 扩展

Shell 扩展在排序过程中自动嵌入到包中。 在全局发布程序包时，shell 扩展为用户提供了与本地安装应用程序相同的功能。 应用程序不需要在客户端上进行其他设置或配置，以启用 shell 扩展功能。

**使用 shell 扩展的要求：**

-   包含嵌入式 shell 扩展的程序包必须在全局发布。

-   应用程序、Sequencer 和 App-V 客户端的"位"必须匹配，否则 shell 扩展将不起作用。 例如：

    -   应用程序的版本为 64 位。

    -   Sequencer 在 64 位计算机上运行。

    -   程序包将传递到 64 位 App-V 客户端计算机。

下表显示了受支持的 shell 扩展。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Handler</th>
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
<td align="left"><p>控制右键单击拖放时的操作，并修改出现的上下文菜单。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>删除目标处理程序</p></td>
<td align="left"><p>控制将数据对象拖放到拖放目标（如文件）之后的操作。</p></td>
</tr>
<tr class="even">
<td align="left"><p>数据对象处理程序</p></td>
<td align="left"><p>控制将文件复制到剪贴板或拖放到拖放目标之后的操作。 它可以为放置目标提供其他剪贴板格式。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>属性表处理程序</p></td>
<td align="left"><p>替换页面或将页面添加到属性表对话框中。</p></td>
</tr>
<tr class="even">
<td align="left"><p>信息提示处理程序</p></td>
<td align="left"><p>允许检索项目的标志和信息提示信息，并可以在鼠标悬停时在弹出工具提示中显示该信息。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>列处理程序</p></td>
<td align="left"><p>允许在"资源管理器详细信息"视图中Windows和显示 <em> 自定义列 </em> 。 它可用于扩展排序和分组。</p></td>
</tr>
<tr class="even">
<td align="left"><p>预览处理程序</p></td>
<td align="left"><p>启用要显示在资源管理器预览窗格中Windows预览。</p></td>
</tr>
</tbody>
</table>

 

### <a name="com"></a>COM

App-V 客户端支持发布应用程序，并支持 COM 集成和虚拟化。 COM 集成允许 App-V 客户端在本地操作系统和对象的虚拟化上注册 COM 对象。 对于本文档，COM 对象的集成需要其他详细信息。

App-V 支持使用两种进程类型将 COM 对象从程序包注册到本地操作系统：进程外和进程内。 注册 COM 对象是使用特定 App-V 程序包（包括 off、Isolated 和 Integrated）的一种或多种操作模式的组合完成的。 集成模式针对进程外类型或进程内类型进行配置。 COM 模式和类型的配置通过使用动态配置文件 (deploymentconfig.xml或userconfig.xml) 。

有关 App-V 集成的详细信息，请参阅： <https://go.microsoft.com/fwlink/?LinkId=392834> 。

### <a name="software-clients-and-application-capabilities"></a>软件客户端和应用程序功能

App-V 支持特定的软件客户端和应用程序功能扩展点，这些扩展点允许向操作系统的软件客户端注册虚拟化应用程序。 这使用户能够为电子邮件、即时消息和媒体播放器等操作选择默认程序。 此操作使用"设置程序访问和计算机默认值"在控制面板中执行，在清单或动态配置文件中排序期间进行配置。 仅在全局发布 App-V 应用程序时，才支持应用程序功能。

基于 App-V 的邮件客户端的软件客户端注册示例。

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

**注意**  
在本示例中：

-   `<ClientConfiguration EmailEnabled="true" />` 是集成电子邮件客户端的整体软件客户端设置

-   `<EMail MakeDefault="true">` 是将特定电子邮件客户端设置为默认电子邮件客户端的标志

-   `<MAPILibrary>[{ProgramFilesX86}]\Mozilla Thunderbird\mozMapi32_InUse.dll</MAPILibrary>` 是 MAPI dll 注册

 

### <a name="url-protocol-handler"></a>URL 协议处理程序

应用程序并不总是专门调用利用文件类型调用的虚拟化应用程序。 例如，在支持在文档或网页内嵌入 mailto： 链接的应用程序中，用户单击 mailto： 链接，并期望获取其注册的邮件客户端。 App-V 支持 URL 协议处理程序，这些处理程序可以基于每个程序包向本地操作系统注册。 在排序过程中，URL 协议处理程序将自动添加到包中。

对于可能注册特定 URL 协议处理程序的多个应用程序的情况，动态配置文件可用于修改行为，并禁止或禁用不应作为主应用程序启动的应用程序的此功能。

### <a name="apppath"></a>AppPath

AppPath 扩展点支持直接从操作系统调用 App-V 应用程序。 这通常是通过"运行"或"开始"屏幕完成的，具体取决于操作系统，通过操作系统，管理员可以从操作系统命令或脚本提供对 App-V 应用程序的访问权限，而无需调用可执行文件的特定路径。 因此，它避免修改所有系统上的系统路径环境变量，因为它在发布过程中完成。

AppPath 扩展点在清单或动态配置文件中配置，在发布用户期间存储在本地计算机上注册表中。 有关 AppPath 查看的其他信息 <https://go.microsoft.com/fwlink/?LinkId=392835> ：。

### <a name="virtual-application"></a>虚拟应用程序

此子系统提供排序期间捕获的应用程序列表，这些应用程序通常由其他 App-V 组件使用。 可以使用动态配置文件禁用属于特定应用程序的扩展点的集成。 例如，如果包包含两个应用程序，可以禁用属于一个应用程序的所有扩展点，以便只允许集成其他应用程序的扩展点。

### <a name="extension-point-rules"></a>扩展点规则

上述扩展点根据程序包的发布方式集成到操作系统中。 全局发布将扩展点位于公用计算机位置，其中用户发布将扩展点位于用户位置。 例如，在桌面上创建并全局发布的快捷方式将导致快捷方式 (%Public%\\Desktop) 的文件数据以及注册表数据 (HKLM\\Software\\Classes) 。 相同的快捷方式将具有文件数据 (%UserProfile%\\Desktop) ，注册表数据 (HKCU\\Software\\Classes) 。

扩展点的发布方式并非全部相同，其中一些扩展点需要全局发布，而其他扩展点要求在交付它们的特定操作系统和体系结构上排序。 下表介绍了这两个关键规则。

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
<th align="left">需要全局发布</th>
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
<td align="left"><p>信息提示处理程序</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>列处理程序</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>Shell 扩展</p></td>
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

 

## <a name="dynamic-configuration-processing"></a><a href="" id="bkmk-dynamic-config"></a>动态配置处理


将 App-V 程序包部署到一台计算机或用户非常简单。 但是，随着组织跨业务线以及地理与政治边界部署 AppV 应用程序，一次使用一组设置对应用程序排序的能力变得不可能。 App-V 专为此方案设计，因为它在清单文件中排序期间捕获特定设置和配置，但还支持使用动态配置文件进行修改。

App-V 动态配置允许在计算机级别或用户级别为程序包指定策略。 动态配置文件使排序工程师能够修改程序包的配置，后排序以满足各个用户组或计算机的需求。 在某些情况下，可能需要对应用程序进行修改，以在 App-V 环境中提供适当的功能。 例如，可能需要对 \_\*config.xml 文件进行修改，以允许特定操作在应用程序执行期间指定的时间执行，例如禁用 mailto 扩展以防止虚拟化应用程序从另一个应用程序覆盖该扩展。

App-V 包包含 appv 包文件内的清单文件，该文件代表排序操作，并且是选择的策略，除非将动态配置文件分配给特定包。 排序后，可以修改动态配置文件，以允许将应用程序发布到不同的桌面或具有不同扩展点的用户。 两个动态配置文件是动态部署配置 (DDC) 和 DYNAMIC User Configuration (DUC) 文件。 本节重点介绍清单和动态配置文件的组合。

### <a name="example-for-dynamic-configuration-files"></a>动态配置文件示例

下面的示例演示发布后和正常操作期间清单、部署配置和用户配置文件的组合。 这些示例是每个文件的缩写示例。 用途是只显示文件的组合，而不是每个文件中提供的特定类别的完整说明。 有关详细信息，请参阅 App-V 5 排序指南，位于： <https://go.microsoft.com/fwlink/?LinkID=269810>

**Manifest**

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

## <a name="side-by-side-assemblies"></a><a href="" id="bkmk-sidebyside-assemblies"></a>并排程序集


App-V 支持在虚拟应用程序发布期间在客户端上排序 (部署期间并行打包 (SxS) 程序集。 App-V 5 SP2 支持在排序过程中捕获排序计算机上不存在的程序集的 SxS 程序集。 对于包含 Visual C++ (版本 8 和更高版本) 和/或 MSXML 运行时的程序集，Sequencer 将自动检测并捕获这些依赖项，即使在监控期间未安装它们。 并排程序集功能消除了以前版本的 App-V 的限制，即 App-V Sequencer 未捕获排序工作站上已存在的程序集，并取消限制每个程序包一位版本的程序集。 此行为导致将 App-V 应用程序部署到缺少所需 SxS 程序集的客户端，从而导致应用程序启动失败。 这将强制打包过程进行记录，然后确保程序包所需的所有程序集都在本地安装在用户的客户端操作系统上，以确保对虚拟应用程序的支持。 根据程序集数量和缺少所需依赖项的应用程序文档，此任务既是管理和实现难题。

App-V 中的并排程序集支持具有以下功能。

-   在排序过程中自动捕获 SxS 程序集，而不管该程序集是否已安装在排序工作站上。

-   App-V 客户端会在发布时自动将所需的 SxS 程序集安装到客户端计算机上（如果它们不存在）。

-   Sequencer 在 Sequencer 报告机制中报告 VC 运行时依赖关系。

-   Sequencer 允许选择不打包已在 Sequencer 上安装的程序集，支持之前已在目标计算机上安装程序集的方案。

### <a name="automatic-publishing-of-sxs-assemblies"></a>自动发布 SxS 程序集

在发布包含 SxS 程序集的 App-V 包期间，App-V 客户端将检查计算机上是否存在程序集。 如果程序集不存在，客户端将程序集部署到计算机。 作为连接组的一部分的程序包将依赖作为基本包一部分的并行程序集安装，因为连接组不包含有关程序集安装的任何信息。

**注意**  
使用程序集取消发布或删除包不会删除该包的程序集。

 

## <a name="client-logging"></a><a href="" id="bkmk-client-logging"></a>客户端日志记录


App-V 客户端将信息记录到Windows ETW 格式的事件日志中。 可以在事件查看器中的应用程序和服务日志\\Microsoft\\AppV\\Client 下找到特定的 App-V 事件。

**注意**  
在 App-V 5.0 SP3 中，某些日志已合并并移动到以下位置：

`Event logs/Applications and Services Logs/Microsoft/AppV/ServiceLog`

有关移动日志的列表，请参阅[关于 App-V 5.0 SP3。](about-app-v-50-sp3.md#bkmk-event-logs-moved)

 

下面记录了三种特定类别的事件。

**管理员**：记录应用到 App-V 客户端的配置的事件，并包含主要警告和错误。

**操作**：记录各个组件的常规 App-V 执行和使用情况，审核日志 App-V 操作已在 App-V 客户端上完成的所有操作。

**虚拟应用程序**：记录虚拟应用程序启动和虚拟化子系统的使用。






 

 





