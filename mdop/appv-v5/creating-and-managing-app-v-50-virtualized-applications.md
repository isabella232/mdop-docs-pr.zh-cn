---
title: 创建和管理 App-V 5.0 虚拟化应用程序
description: 创建和管理 App-V 5.0 虚拟化应用程序
author: dansimp
ms.assetid: 66bab403-d7e0-4e7b-bc8f-a29a98a7160a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 86332c7753b70abbaaf289fc1ba046bf59d1dd89
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798611"
---
# 创建和管理 App-V 5.0 虚拟化应用程序


在正确部署 Microsoft Application Virtualization （App-v） 5.0 sequencer 后，可以使用它监视和记录应用程序的安装和设置过程，以使应用程序作为虚拟化应用程序运行。

**注意** 有关配置 Microsoft Application Virtualization （App-v） 5.0 sequencer、顺序最佳做法以及创建和更新虚拟应用程序的示例的详细信息，请参阅[Microsoft Application Virtualization 5.0 排序指南](https://download.microsoft.com/download/F/7/8/F784A197-73BE-48FF-83DA-4102C05A6D44/App-V 5.0 Sequencing Guide.docx)（ https://download.microsoft.com/download/F/7/8/F784A197-73BE-48FF-83DA-4102C05A6D44/App-V 5.0 先后顺序 Guide.docx）。

 

## 对应用程序进行排序


你可以使用 app-v 5.0 Sequencer 执行以下任务：

-   创建可部署到运行 App-v 5.0 客户端的计算机的虚拟程序包。

-   升级现有程序包。 你可以将现有程序包扩展到运行 sequencer 的计算机上，然后升级该应用程序以创建较新的版本。

-   编辑与现有程序包相关联的配置信息。 例如，你可以添加快捷方式或修改文件类型关联。

    **注意** 必须创建快捷方式并将其保存到可用的网络位置以允许漫游。 如果在专用位置创建和保存了快捷方式，则程序包必须在本地发布到运行 App-v 5.0 客户端的计算机。

     

-   转换现有虚拟程序包。

排序器使用 **% TMP% \ 暂存**或 **% TEMP% \\ 暂存**目录和**临时**目录在排序期间存储临时文件。 在运行 sequencer 的计算机上，你应该将这些目录配置为与估计的应用程序安装要求等效的可用磁盘空间。 在不同的硬驱分区上配置临时目录和临时目录有助于在序列化期间提高性能。

使用 sequencer 创建新的虚拟应用程序时，将创建以下列出的文件。 这些文件包含 App-v 5.0 程序包。

-   .msi 文件。 此 Windows Installer （.msi）文件由 sequencer 创建，用于在目标计算机上安装虚拟程序包。

-   Report.xml 文件。 在此文件中，sequencer 将保存在排序期间发现的所有问题、警告和错误。 在创建程序包后显示信息。 您可以通过此报告进行诊断和故障排除。

-   appv 文件。 这是虚拟应用程序文件。

-   部署配置文件。 部署配置文件确定如何将虚拟应用程序部署到目标计算机。

-   用户配置文件。 用户配置文件确定虚拟应用程序将如何在目标计算机上运行。

**重要提示** 您必须配置% TMP% 和% TEMP% 的文件夹，程序包转换器使用该文件夹作为安全的位置和目录。 安全位置只能由管理员访问。 此外，当你对程序包进行排序时，你应该将程序包保存到安全的位置，或者确保在转换和监视过程中不允许登录任何其他用户。

 

Sequencer 控制台中的 "**选项**" 对话框包含以下选项卡：

-   **常规**。 使用此选项卡可允许 Microsoft 更新在排序期间运行。 选择 "**将包版本追加到文件名**" 以配置序列以向正在排序的虚拟化程序包添加版本号。 选择 "**始终信任程序包加速器的源"** 以使用软件包加速器创建虚拟化程序包，而不提示进行授权。

    **重要提示** App-v 5.0 不支持使用 App-v 4.6 创建的程序包加速器。

     

-   **分析项目**。 此选项卡显示将在虚拟环境中分析或标记为的关联文件路径位置。 令牌对于使用 "**高级编辑**" 中的 "**包文件**" 选项卡添加文件非常有用。

-   **排除项目**。 使用此选项卡可以指定在排序期间不应监视哪些文件夹和目录。 若要添加保存在程序包的本地应用数据文件夹中的本地应用程序数据，请单击 "**新建**"，然后指定位置和关联的**映射类型**。 某些程序包需要此选项。

App-v 5.0 支持包含 Microsoft Windows 服务的应用程序。 如果应用程序包含 Windows 服务，则该服务将包含在已排序的虚拟程序包中，只要它在由排序器监视时安装。 如果虚拟应用程序在最初运行时创建 Windows 服务，然后在安装之后，应用程序必须在排序器监视时运行，以便将 Windows 服务添加到程序包。 仅支持在本地系统帐户下运行的服务。 在程序包的虚拟环境内运行程序包中的第一个虚拟应用程序之前，将启动为 AutoStart 或延迟的 AutoStart 配置的服务。 当程序包内的虚拟应用程序通过 API 调用启动服务时，将启动配置为按需由应用程序启动的 Windows 服务。

[如何使用 App-V 5.0 对新应用程序进行排序](how-to-sequence-a-new-application-with-app-v-50-beta-gb18030.md)

## <a href="" id="---------app-v-5-0-sp2-shell-extension-support"></a> App-v 5.0 SP2 外壳扩展支持


App-v 5.0 SP2 支持外壳扩展。 在排序期间，将检测并嵌入在程序包中的 Shell 扩展。

在排序过程中，将自动在程序包中嵌入外壳扩展。 程序包发布后，外壳扩展为用户提供与应用程序本地安装的功能相同的功能。

**使用外壳扩展的要求：**

-   包含嵌入式外壳扩展的软件包必须全局发布。 应用程序不需要在客户端上进行额外的设置或配置即可启用外壳扩展功能。

-   应用程序、Sequencer 和 App-v 客户端的 "位数" 必须匹配，否则 shell 扩展将不起作用。 例如：

    -   该应用程序的版本为64位。

    -   Sequencer 在64位计算机上运行。

    -   程序包正在发送到64位 App-v 客户端计算机。

下表列出了支持的外壳扩展：

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
<td align="left"><p>控制操作，单击鼠标右键，然后拖放并修改出现的上下文菜单。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>拖放目标处理程序</p></td>
<td align="left"><p>控制在将数据对象拖放到放置目标（如文件）后执行的操作。</p></td>
</tr>
<tr class="even">
<td align="left"><p>数据对象处理程序</p></td>
<td align="left"><p>控制将文件复制到剪贴板或拖放到放置目标之后的操作。 它可以向放置目标提供其他剪贴板格式。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>属性表处理程序</p></td>
<td align="left"><p>将页面替换或添加到对象的 "属性表" 对话框。</p></td>
</tr>
<tr class="even">
<td align="left"><p>提示处理程序</p></td>
<td align="left"><p>允许检索项目的标志和信息提示信息，并在鼠标悬停时将其显示在弹出工具提示内。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>列处理程序</p></td>
<td align="left"><p>允许在 <strong> Windows 资源管理器的 "详细信息" 视图中创建和显示自定义列 </strong> 。 它可用于扩展排序和分组。</p></td>
</tr>
<tr class="even">
<td align="left"><p>预览处理程序</p></td>
<td align="left"><p>启用要在 Windows 资源管理器预览窗格中显示的文件的预览。</p></td>
</tr>
</tbody>
</table>

 

## 写入时复制（牛）文件扩展名支持


写入时复制（牛）文件扩展名允许使用 app-v 5.0 动态写入虚拟程序包中包含的特定位置。

下表显示了可以存在于 VFS 目录下的虚拟程序包中的文件类型，但无法在运行 App-v 5.0 客户端的计算机上更新。 可以修改所有其他文件和目录。

。

asa

.asp

.aspx

ax

.bat

.cer

.chm

clb

.cmd

.cnt

.cnv

.com

.cpl

.cpx

.crt

.dll

.drv

.exe

.fon

.grp

.hlp

.hta

。 ime

.inf

.ins

.isp

。其

.js

.jse

.lnk

.msc

.msi

.msp

.mst

mui

nls

.ocx

pal

.pcd

.pif

.reg

.scf

.scr

. sct

.shb

.shs

.sys

.tlb

. tsp

.url

.vb

.vbe

.vbs

.vsmacros

.ws

。 esc

.wsf

.wsh

 

## 修改现有虚拟应用程序包


你可以使用 sequencer 修改现有程序包。 您在其上执行此操作的计算机应该与用于创建该应用程序的计算机的芯片体系结构相匹配。 例如，如果最初使用运行64位操作系统的计算机序列化程序包，则应使用运行64位操作系统的计算机修改程序包。

[如何修改现有的虚拟应用程序包](how-to-modify-an-existing-virtual-application-package-beta.md)

## 创建项目模板


Appvt 文件是一个项目模板，可用于保存常用的自定义设置。 然后，您可以更轻松地将这些设置用于将来的 sequencings。

App-v 5.0 项目模板与 App-v 5.0 应用程序加速器不同，因为 App-v 5.0 应用程序加速器是特定于应用程序的，而 app-v 5.0 项目模板可应用于多个应用程序。 此外，使用包加速器创建虚拟应用程序包时，不能使用项目模板。 以下常规设置将与 App-v 5.0 项目模板一起保存：

模板可以指定和存储多个设置，如下所示：

-   **高级监视选项**。 支持在监视期间运行 Microsoft 更新。 保存允许本地交互选项设置

-   **常规选项**。 启用**Windows 安装程序**，将**程序包版本附加到文件名**。

-   **排除项目。** 包含 "排除" 模式列表。

[如何创建和使用项目模板](how-to-create-and-use-a-project-template.md)

## 创建程序包加速器


**注意** 必须使用 App-v 5.0 重新创建使用早期版本的 App-v 创建的程序包加速器。

 

你可以使用 app-v 5.0 程序包加速器自动生成新的虚拟应用程序包。 成功创建程序包加速器后，您可以重复使用和共享程序包加速器。

在某些情况下，若要创建程序包加速器，可能需要在运行 sequencer 的计算机上本地安装应用程序。 在这种情况下，你应该首先尝试用安装媒体创建程序包加速器。 如果需要多个缺少的文件，则应在运行 sequencer 的计算机本地安装应用程序，然后创建程序包加速器。

成功创建程序包加速器后，您可以重复使用和共享程序包加速器。 创建 App-v 5.0 程序包加速器是一种高级任务。 程序包加速器可以包含密码和特定于用户的信息。 因此，你必须将程序包加速器和关联的安装媒体保存在一个安全的位置，并且你应对程序包加速器进行数字签名，以便在应用 V 5.0 程序包加速器应用时可以验证发布者。

[如何创建包加速器](how-to-create-a-package-accelerator.md)

[如何使用 App-V 包加速器创建虚拟应用程序包](how-to-create-a-virtual-application-package-using-an-app-v-package-accelerator.md)

## Sequencer 错误报告


App-v 5.0 Sequencer 可检测排序期间的常见排序问题。 排序向导结束时的 "**安装报告**" 页面显示根据问题的严重程度，归类为**错误**、**警告**和**信息**的诊断消息。

你还可以使用 Windows 事件查看器查找有关序列化错误的其他信息。






## <a href="" id="other-resources-for-the-app-v-5-0-sequencer-"></a>App-v 5.0 sequencer 的其他资源


-   [App-V 5.0 的操作](operations-for-app-v-50.md)

 

 





