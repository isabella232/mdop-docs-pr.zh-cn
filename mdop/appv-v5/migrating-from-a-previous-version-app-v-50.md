---
title: 从以前版本迁移
description: 从以前版本迁移
author: dansimp
ms.assetid: a13cd353-b22a-48f7-af1e-5d54ede2a7e5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a05bbd498cdb77a1ddf694b1aab6aeb42124775b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798325"
---
# 从以前版本迁移


通过 app-v 5.0，你可以将现有的 App-v 4.6 基础结构迁移到更灵活、更集成且更易于管理的 app-v 5.0 基础结构。

规划迁移策略时，请考虑以下几个部分：

**注意** 有关 App-v 4.6 和 App-v 5.0 之间的区别的详细信息，请参阅[关于 app-v 5.0](about-app-v-50.md)的**app-v 4.6 和 app-v 5.0 部分之间的差异**。

 

## 转换使用早期版本的 App-v 创建的程序包


使用程序包转换器实用工具升级使用早期版本的 App-v 创建的虚拟应用程序包。 程序包转换器使用 PowerShell 转换程序包，如果你有多个需要转换的程序包，则可以帮助自动处理该进程。

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
<td align="left"><p>不转换程序包脚本。</p></td>
<td align="left"><p>测试转换后的程序包。 如果需要，请转换脚本。</p></td>
</tr>
<tr class="even">
<td align="left"><p>不会转换程序包注册表设置替代。</p></td>
<td align="left"><p>测试转换后的程序包。 如有必要，请重新添加注册表覆盖。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>转换后，使用 DSC 的虚拟包不会链接。</p></td>
<td align="left"><p>使用连接组链接程序包。 请参阅 <a href="managing-connection-groups.md" data-raw-source="[Managing Connection Groups](managing-connection-groups.md)"> 管理连接组 </a> 。</p></td>
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

 

转换程序包时，检查是否有失败的文件或快捷方式。 在 App-v 4.6 程序包中找到该项目。 它可能是硬编码的路径。 转换路径。

**注意** 建议使用 app-v 5.0 sequencer 来转换需要利用功能的关键应用程序或应用程序。 请参阅[如何使用 app-v 5.0 对新应用程序进行排序](how-to-sequence-a-new-application-with-app-v-50-beta-gb18030.md)。

如果转换后的程序包未打开，还建议使用 App-v 5.0 sequencer 对应用程序进行重新排序。

 

[如何转换在以前版本的 App-V 中创建的程序包](how-to-convert-a-package-created-in-a-previous-version-of-app-v.md)

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
<td align="left"><p>将环境升级到 App-v 4.6 SP2</p></td>
<td align="left"><p><a href="../appv-v4/application-virtualization-deployment-and-upgrade-considerations-copy.md" data-raw-source="[Application Virtualization Deployment and Upgrade Considerations](../appv-v4/application-virtualization-deployment-and-upgrade-considerations-copy.md)">应用程序虚拟化部署和升级注意事项 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>安装支持共存的 app-v 5.0 客户端。</p></td>
<td align="left"><p><a href="how-to-deploy-the-app-v-46-and-the-app-v--50-client-on-the-same-computer.md" data-raw-source="[How to Deploy the App-V 4.6 and the App-V 5.0 Client on the Same Computer](how-to-deploy-the-app-v-46-and-the-app-v--50-client-on-the-same-computer.md)">如何在同一台计算机上部署 app-v 4.6 和 app-v 5.0 客户端 </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>顺序和推出 app-v 5.0 程序包。 根据需要，取消发布 app-v 4.6 程序包。</p></td>
<td align="left"><p><a href="how-to-sequence-a-new-application-with-app-v-50-beta-gb18030.md" data-raw-source="[How to Sequence a New Application with App-V 5.0](how-to-sequence-a-new-application-with-app-v-50-beta-gb18030.md)">如何使用 App-v 5.0 对新应用程序进行排序 </a> 。</p></td>
</tr>
</tbody>
</table>

 

**重要提示** 必须运行 App-v 4.6 SP3 才能使用共存模式。 此外，在对程序包进行排序时，必须配置 "管理机构" 设置，该设置位于 **"用户****配置**" 部分中。

 

## 迁移 app-v 5.0 服务器的完整基础结构


没有直接的方法可升级到完整的 app-v 5.0 基础结构。 有关升级 app-v 服务器的信息，请使用以下部分中的信息。

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
<td align="left"><p>将你的环境升级到 app-v 4.6 SP3。</p></td>
<td align="left"><p><a href="../appv-v4/application-virtualization-deployment-and-upgrade-considerations-copy.md" data-raw-source="[Application Virtualization Deployment and Upgrade Considerations](../appv-v4/application-virtualization-deployment-and-upgrade-considerations-copy.md)">应用程序虚拟化部署和升级注意事项 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>部署 app-v 5.0 版本的客户端。</p></td>
<td align="left"><p><a href="how-to-deploy-the-app-v-client-gb18030.md" data-raw-source="[How to Deploy the App-V Client](how-to-deploy-the-app-v-client-gb18030.md)">如何部署 app-v 客户端 </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>安装 App-v 5.0 server。</p></td>
<td align="left"><p><a href="how-to-deploy-the-app-v-50-server-50sp3.md" data-raw-source="[How to Deploy the App-V 5.0 Server](how-to-deploy-the-app-v-50-server-50sp3.md)">如何部署 app-v 5.0 服务器 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>迁移现有程序包。</p></td>
<td align="left"><p>查看 <strong> 使用本文的早期版本 app-v 部分创建的转换程序包 </strong> 。</p></td>
</tr>
</tbody>
</table>

 

## 其他迁移任务


你还可以执行其他迁移任务，例如重新配置终结点，以及打开使用运行 App-v 5.0 客户端的计算机上的早期版本创建的程序包。 以下链接提供了有关执行这些任务的详细信息。

[如何为特定计算机上的所有用户将 App-V 4.6 程序包中的扩展点迁移到转换后的 App-V 5.0 程序包](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-50-package-for-all-users-on-a-specific-computer.md)

[如何为特定用户将 App-V 4.6 程序包中的扩展点迁移到 App-V 5.0](how-to-migrate-extension-points-from-an-app-v-46-package-to-app-v-50-for-a-specific-user.md)

[如何为特定计算机上的所有用户将 App-V 5.0 程序包中的扩展点还原到 App-V 4.6 程序包](how-to-revert-extension-points-from-an-app-v-50-package-to-an-app-v-46-package-for-all-users-on-a-specific-computer.md)

[如何为特定用户将 App-V 5.0 程序包中的扩展点还原到 App-V 4.6 程序包](how-to-revert-extension-points-from-an-app-v-50-package-to-an-app-v-46-package-for-a-specific-user.md)







## 用于执行 App-v 迁移任务的其他资源


[App-V 5.0 的操作](operations-for-app-v-50.md)

[简化的 Microsoft App-V 5.1 管理服务器升级过程](https://go.microsoft.com/fwlink/p/?LinkId=786330)

 

 





