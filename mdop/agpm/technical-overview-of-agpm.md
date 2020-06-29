---
title: AGPM 技术概述
description: AGPM 技术概述
author: dansimp
ms.assetid: 36bc0ab5-f752-474c-8559-721ea95169c2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 0cc635f46c2aabb0c9fa1f472a258a3e65a07b55
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801760"
---
# AGPM 技术概述


Microsoft 高级组策略管理（AGPM）是一个客户端/服务器应用程序。 AGPM 服务器在 AGPM 在服务器的文件系统上创建的存档中存储组策略对象（Gpo）。 组策略管理员使用组策略管理控制台（GPMC）的 AGPM 管理单元来处理托管存档的服务器上的 Gpo。 了解 AGPM 和相关项目的组成部分、如何在文件系统中存储 Gpo 以及权限如何控制每个用户角色的操作可通过 AGPM 提高组策略管理员的有效性。

## 术语


下面介绍了基本的 AGPM 术语。

-   **AGPM 客户端：** 运行组策略管理控制台（GPMC）和组策略管理员管理 Gpo 的 AGPM 管理单元的计算机。

-   **AGPM 管理单元：** 在 AGPM 客户端上安装的 AGPM 的软件组件，以便它们可以管理 Gpo。

-   **AGPM 服务器：** 运行 AGPM 服务并管理存档的服务器。 每个 AGPM 服务器只能管理一个存档，但一个 AGPM 服务器可以在一个存档中管理多个域的存档数据。 存档可以托管在不是 AGPM 服务器的计算机上。

-   **AGPM 服务：** 在 AGPM 服务器上作为服务运行的 AGPM 的软件组件。 该服务管理存档中和该林中生产环境中的 Gpo。

-   **存档：** 在 AGPM 中，包含关联的 AGPM 服务器管理的受控 Gpo 的中央存储，以及其中每个 Gpo 的历史记录。 这包括每个 GPO 的所有以前的受控制版本。 存档包含存档索引文件和关联的存档数据，其中可能包含多个域中的 Gpo 的数据。 存档可以托管在不是 AGPM 服务器的计算机上。

-   **受控 GPO：** 由 AGPM 管理的 GPO。 AGPM 管理受控制 Gpo 的历史记录和权限，它存储在存档中。

-   不**受控制的 GPO：** 域生产环境中的 GPO，而不是由 AGPM 托管。

## 哪些 AGPM 安装、创建和影响


在 AGPM 服务器上，AGPM 设置程序将安装 AGPM 服务。 AGPM 不会更改 Active Directory®目录服务或架构。 默认情况下，AGPM 服务器程序文件安装在%ProgramFiles%\\Microsoft\\AGPM\\Server。 如果需要，您可以在域控制器上安装 AGPM 服务;但是，我们建议你在成员服务器上安装 AGPM 服务。

在 AGPM 客户端上，AGPM 设置程序将安装 AGPM 管理单元，将 "**更改控制**" 文件夹添加到 GPMC 中显示的每个域。 默认情况下，AGPM 客户端程序文件安装在%ProgramFiles%\\Microsoft\\AGPM\\Client。

表1介绍了 AGPM 安装或创建的项目以及影响 AGPM 操作的操作系统部分。

**表1：已安装、已创建或受 AGPM 影响的项目**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">项目</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>AGPM 服务</p></td>
<td align="left"><p>AGPM 服务在 AGPM 服务器上运行。 该服务在生产环境中管理包含脱机 Gpo 和受控 Gpo 的存档。 AGPM 服务的默认配置如下所示：</p>
<ul>
<li><p><strong>服务名称： </strong> AGPM 服务</p></li>
<li><p><strong>显示名称： </strong> AGPM 服务</p></li>
<li><p><strong>可执行文件的路径： </strong> % ProgramFiles% \Microsoft\AGPM\Server\Agpm.exe</p></li>
<li><p><strong>启动： </strong> 自动</p></li>
<li><p><strong>在 </strong> 安装 Agpm 服务器期间指定的 Agpm 服务帐户（可使用 <strong> </strong> "控制面板" 中的 "程序和功能" 更改 <strong> ）进行登录 </strong> 。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>AGPM 存档</p></td>
<td align="left"><p>默认情况下，AGPM 在 AGPM 服务器上的%ProgramData%\Microsoft\AGPM 中创建存档。 存档提供脱机 Gpo 的存储，并且它可以存储每个 GPO 的多个版本。 AGPM 对存档中的 Gpo 所做的更改不会影响生产环境，直到 AGPM 管理员或审批者将 GPO 部署到生产环境并将 GPO 链接到组织单元（OU）。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows 防火墙</p></td>
<td align="left"><p>在安装期间，AGPM 支持允许 AGPM 客户端与 AGPM 服务器通信的入站 Windows 防火墙规则。 默认的 Windows 防火墙规则如下所示：</p>
<ul>
<li><p><strong>名称： </strong> AGPM 服务</p></li>
<li><p><strong>操作： </strong> 允许连接</p></li>
<li><p><strong>程序： </strong> 满足指定条件的所有程序</p></li>
<li><p><strong>协议类型： </strong> TCP</p></li>
<li><p><strong>本地端口： </strong> 4600</p></li>
<li><p><strong>远程端口： </strong> 所有端口</p></li>
<li><p><strong>本地 IP 地址： </strong> 任意</p></li>
<li><p><strong>远程 IP 地址： </strong> 任何</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>电子邮件服务器</p></td>
<td align="left"><p>AGPM 使用简单邮件传输协议（SMTP）将电子邮件请求发送到 " <strong> 域委派" 选项卡上配置的地址 </strong> 。例如，当一个编辑器请求创建新的 GPO 时，AGPM 会通知在 " <strong> 域委派" 选项卡上指定的每个电子邮件地址 </strong> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>AGPM 管理单元</p></td>
<td align="left"><p>GPMC 的 AGPM 管理单元在 AGPM 客户端上运行，由组策略管理员用于管理 Gpo。 管理单元将在 GPMC 中显示为 <strong> </strong> 每个域中的更改控制文件夹。</p></td>
</tr>
</tbody>
</table>

 

### 其他参考资料

有关 AGPM 安装的文件的详细信息，请参阅[agpm 的规划指南](https://go.microsoft.com/fwlink/?LinkId=160060)。

## Archive


默认情况下，AGPM 服务器安装过程会在%ProgramData%\\Microsoft\\AGPM. 上的 AGPM 服务器的本地硬盘上创建存档。 但是，你可以在安装过程中更改路径，甚至可以在 AGPM 服务器之外的服务器上创建存档。

存档包含存档包含的每个 GPO 版本的子文件夹。 每个子文件夹的名称是一个 GUID，用于标识 GPO 的一个版本。

gpostate.xml 文件记录存档中每个 GPO 的状态。 该文件是描述存档内容的清单。 例如，GPO 可以有多个版本，每个版本都位于存档中各自的子文件夹中。 gpostate.xml 文件指示哪些子文件夹包含单个 GPO 的不同版本。 此外，GPO 模板在存档中具有子文件夹，但 gpostate.xml 指示这些模板是模板，而不是受控制的 Gpo。 同样，当组策略管理员删除 Gpo 时，AGPM 会在 gpostate.xml 中更改其状态，以指示它们位于**回收站**中，但实际上并不会从存档中删除 gpo 的子文件夹。

**小心** 不要手动编辑 gpostate.xml 或存档包含的 Gpo。 提供此信息只是为了增强对 AGPM 存档的理解。 请改为使用 AGPM 管理单元更改 Gpo。

 

当 AGPM 创建存档时，它会向系统、管理员和 AGPM 服务帐户（在 AGPM 服务器的设置中指定）授予完全控制权。 通过使用 AGPM 管理单元上的 AGPM 用户界面更改权限不会改变对存档的权限，因为 AGPM 服务帐户代表登录用户执行所有操作。

### 其他参考资料

有关如何备份存档、从备份还原存档或同时移动 AGPM 服务器和存档的信息，请参阅[适用于 agpm 的操作指南](https://go.microsoft.com/fwlink/?LinkId=160061)中的 "执行 Agpm 管理员任务" 部分。

## 角色和权限


角色简化了委派。 对于组策略管理员而言，AGPM 管理员可以向组策略管理员分配以下四个角色之一，让他们可以执行与该角色相关的工作：

-   **AGPM 管理员：** 分配了 AGPM 管理员（完全控制）角色的组策略管理员可以在 AGPM 中执行任何任务。 AGPM 管理员可以配置域范围的选项并将权限委派给其他组策略管理员。

-   **审批者：** 分配了审批者角色的组策略管理员可以将 Gpo 部署到域的生产环境中。 审批者还可以创建和删除 Gpo，并批准或拒绝来自编辑者的请求。 审批者可以查看域中的 Gpo 列表、查看 Gpo 中的策略设置以及创建和查看 GPO 中的策略设置报告。 它们不能编辑 Gpo 中的策略设置，除非它们也分配有编辑者角色。

-   **编辑器：** 分配了 "编辑" 角色的组策略管理员可以查看域中的 Gpo 列表、查看 Gpo 中的策略设置、编辑 Gpo 中的策略设置以及创建和查看 GPO 中的策略设置报告。 除非它们也分配给审批者角色，否则编辑者无法创建、部署或删除 Gpo。 但是，他们可以请求创建、部署或删除 Gpo。

-   **审阅者：** 分配了审阅者角色的组策略管理员可以查看域中的 Gpo 列表，并在 GPO 中创建和查看策略设置的报告。 除非它们也分配有编辑器角色，否则它们不能在 GPO 中编辑策略设置。

AGPM 使 AGPM 管理员能够通过使用 AGPM 管理单元以比角色更详细的级别配置权限。 表2描述了这些权限，并指明了默认授予每个角色的权限。

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">权限</th>
<th align="left">描述</th>
<th align="left">AGPM 管理员</th>
<th align="left">审批者</th>
<th align="left">编辑器</th>
<th align="left">姓名</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>完全控制</strong></p></td>
<td align="left"><p>具有所有权限。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>创建 GPO</strong></p></td>
<td align="left"><p>在域中创建 Gpo。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>列表内容</strong></p></td>
<td align="left"><p>列出域中的 Gpo。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>读取设置</strong></p></td>
<td align="left"><p>阅读 GPO 中的策略设置。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>编辑设置</strong></p></td>
<td align="left"><p>更改 GPO 中的策略设置。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p></p></td>
<td align="left"><p>是</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>删除 GPO</strong></p></td>
<td align="left"><p>删除 GPO。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>修改安全性</strong></p></td>
<td align="left"><p>委派域级别的访问权限，委派对单个 GPO 的访问，并委派对生产环境的访问权限。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>部署 GPO</strong></p></td>
<td align="left"><p>将 GPO 从存档部署到生产环境。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>创建模板</strong></p></td>
<td align="left"><p>在 AGPM 中创建 GPO 模板。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p></p></td>
<td align="left"><p>是</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>修改选项</strong></p></td>
<td align="left"><p>配置 AGPM 电子邮件通知，并限制存档中存储的 GPO 版本。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>导出 GPO</strong></p></td>
<td align="left"><p>将 GPO 导出到文件。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p></p></td>
<td align="left"><p>是</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>导入 GPO</strong></p></td>
<td align="left"><p>从文件导入 GPO。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p></p></td>
<td align="left"><p>是</p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 

**注意** 
**导出 gpo**和**导入 GPO**权限在 AGPM 3.0 或2.5 中不可用。

在 AGPM 2.5 中不提供在生产环境中委派对域的 Gpo 的访问权限，以及限制存储的 GPO 版本数的能力。

 

### 其他参考资料

有关分配了特定角色的组策略管理员可以执行哪些任务或有关执行特定任务所需权限的信息，请参阅[AGPM 的操作指南](https://go.microsoft.com/fwlink/?LinkId=160061)。

 

 





