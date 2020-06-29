---
title: 确定 MED-V 工作区的数量和类型
description: 确定 MED-V 工作区的数量和类型
author: dansimp
ms.assetid: 11642253-6b1f-4c4a-a11e-48d8a360e1ea
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e0c9ed4b0ce92d0ca752525b847405bbce90a270
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804133"
---
# 确定 MED-V 工作区的数量和类型


MED-V 创建一个虚拟环境，用于运行需要 Windows XP 的应用程序，或者需要与主机上的版本不同的 Internet Explorer 版本。 此虚拟环境称为 MED-V 工作区。

根据你的组织在迁移到 Windows 7 时所面临的应用程序兼容性要求，只有特定用户或部门可能需要 MED-V 工作区。 在规划部署时，必须确定企业中所需的 MED-V 工作区的数量。 你还必须定义每个 MED-V 工作区的要求。

## 标识 MED-V 工作区的数量和类型


确定你的企业中将为其创建 MED-V 工作区的计算机和组。 通常情况下，这些用户需要访问无法迁移到 Windows 7 的应用程序。 标识无法迁移的应用程序和需要 MED-V 工作区才能运行这些应用程序的用户。

你可能还具有尚未针对 Windows 7 进行优化的 intranet 地址。 MED-V 工作区提供了 Internet Explorer 浏览器，最终用户可以通过该浏览器更好地访问尚未准备好用于迁移到 Windows 7 的这些 web 地址。 当你准备和规划 MED-V 部署时，你将必须标识和编译 URL 地址列表，以便从主机上的 Internet Explorer 重定向到 MED-V 工作区中的 Internet Explorer。

最后，你必须评估磁盘空间需求。 大多数 MED-V 工作区都是2千兆字节（GB）或更大。 系统上的可用磁盘空间可以快速使用，具体取决于用户数和 MED-V 的配置。 此外，贵公司的首选分发方式可能需要额外的空间。 通常，你应该为 MED-V 工作区释放至少 10 GB 的磁盘空间，但这种情况会有所不同，具体取决于图像的大小。

### 计算 MED-V 工作区的磁盘空间要求

MED-V 工作区需要内存和磁盘空间来自安装它的主机。 主机上至少需要 2 GB 的磁盘空间。 磁盘空间是可变的，取决于用户的 MED-V 工作区中的应用程序和数据的数量。

我们建议最少 10 GB 的磁盘空间用于 MED-V。 此金额允许基本 Windows XP 工作区和某些基本安装的应用程序和 web 重定向。 它还提供主机交换驱动器的可用空间。 在基本配置中，MED-V 和单个部署的 MED-V 工作区最多可使用6到 8 GB。 如果在 MED-V 工作区上包含许多应用程序，或者每台计算机有多个用户，则可以使用以下计算更准确地确定 MED-V 工作区所需的磁盘空间：

*基本 VHD + （每台计算机 x 的用户数（磁盘差异 + 已保存状态））*

若要计算所需的磁盘空间，请确定以下各项：

-   **基本 VHD 的大小**-用于创建 med-v 工作区的虚拟硬盘。

    **重要提示** 不要对计算使用 medv 文件大小，因为 medv 文件已压缩。

     

-   **每台计算机的用户数**-med-v 为计算机上的每个用户创建了一个 med-v 工作区;在每个用户登录和创建 MED-V 工作区时，MED-V 工作区会占用磁盘空间。

-   **差异磁盘的大小**-用于跟踪与基本 VHD 之间的差异。 此大小因你将应用程序和软件更新添加到虚拟硬盘而不同。 第一次启动 MED-V 时，将为每个 MED-V 用户创建差异磁盘。

-   **已保存状态文件的大小**-用于维护虚拟机中的状态。 通常，这比分配给虚拟机的 RAM 稍大一些。 例如，分配的 1 GB RAM 将创建一个大约 1081000 KB 的文件。

以下示例显示基于具有 2.6 GB 虚拟硬盘的 MED-V 工作区的三个用户的计算：

*2.6 gb + （3 x （1.5 gb + 1gb）） = 10.1 gb*

**注意** MED-V 最佳做法是使用实验室部署来验证要求，从而计算所需的空间。

 

### 找到文件以确定文件大小

以下位置包含计算机和用户设置的文件：

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">类型</th>
<th align="left">位置</th>
<th align="left">文件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>基本 VHD</p></td>
<td align="left"><p>%ProgramData%\Microsoft\Medv\Workspace</p></td>
<td align="left"><p><em>InternalName </em> -其中 <em> InternalName </em> 是你在 Med-v 工作区包装程序中选择的虚拟硬盘的名称。</p></td>
</tr>
<tr class="even">
<td align="left"><p>差异磁盘</p></td>
<td align="left"><p>%LocalAppData%\Microsoft\MEDV\v2\Virtual 计算机</p></td>
<td align="left"><p><em>WorkspaceName </em></p></td>
</tr>
<tr class="odd">
<td align="left"><p>已保存状态文件</p></td>
<td align="left"><p>%LocalAppData%\Microsoft\MEDV\v2\Virtual 计算机</p></td>
<td align="left"><p><em>WorkspaceName </em> vsv</p></td>
</tr>
</tbody>
</table>

 

### 计算共享的 MED-V 工作区的磁盘空间要求

如果你在一台计算机上计算共享的 MED-V 工作区部署，则你的计算中的每台计算机的用户数始终为 "1"，因为 MED-V 仅为所有用户配置单个差异磁盘。

你可以在%ProgramData%\\Microsoft\\Medv\\AllUsers. 中找到共享的 MED-V 工作区的差异磁盘和已保存状态文件

## 相关主题


[定义和规划 MED-V 部署](define-and-plan-your-med-v-deployment.md)

[规划 MED-V](planning-for-med-v.md)

 

 





