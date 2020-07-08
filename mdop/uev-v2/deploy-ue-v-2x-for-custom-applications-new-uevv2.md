---
title: 部署自定义应用程序的 UE-V 2。
description: 部署自定义应用程序的 UE-V 2。
author: dansimp
ms.assetid: f7cb089f-d764-4a93-82b6-926fe0385a23
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 07/19/2016
ms.openlocfilehash: 217f647d948df016c4a6b72736669c2b3305b705
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803561"
---
# 部署自定义应用程序的 UE-V 2。


Microsoft 用户体验虚拟化（UE-V）2.0。 2.1 和 2.1 SP1 使用名为**设置位置模板**的 XML 文件监视和同步用户计算机之间的桌面应用程序设置和 Windows 桌面设置。 默认情况下，某些设置位置模板包含在 UE-V 中。 但是，如果你希望同步除默认模板中包含的桌面应用程序之外的桌面应用程序的设置，你可以使用 UE-V 生成器创建你自己的自定义设置位置模板。

一旦您已阅读[准备 ue-v 2. x 部署](prepare-a-ue-v-2x-deployment-new-uevv2.md)中的规划资料并确定要同步自定义应用程序（第三方、业务线等）的设置，您将按照本主题中的说明部署 ue-v 的功能。 若要开始，下面是同步自定义应用程序的设置所需的主要步骤：

-   [安装 UEV 生成器](#uevgen)

    使用 UEV 生成器创建自定义 XML 设置位置模板。

-   [配置 UE-V 设置模板目录](#deploycatalogue)

    你可以定义存储自定义设置位置模板的此路径。

-   [创建自定义设置位置模板](#createcustomtemplates)

    这些自定义模板允许用户同步自定义应用程序的设置。

-   [部署自定义设置位置模板](#deploycustomtemplates)

    在测试自定义模板以确保正确同步设置后，你可以通过以下方式之一部署这些模板：

    -   通过现有部署基础结构（如 Configuration Manager）

    -   使用组策略首选项

    -   [部署 UE-V 设置模板目录](#deploycatalogue)

    **注意** 使用 ESD 或组策略部署的模板必须使用 UE-V Windows Management Instrumentation （WMI）或 Windows PowerShell 注册。

     

## 准备为自定义应用程序部署 UE-V 2。


开始部署处理自定义应用程序的 UE-V 功能之前，只需查看几个方面。

### UE-V 生成器

UE-V 生成器监视应用程序以发现和捕获应用程序存储其设置的位置。 被监视的应用程序必须是传统的应用程序。 使用 UE-V 生成器创建设置位置模板，但无法从这些应用程序类型创建设置位置模板：

-   虚拟化应用程序

-   通过终端服务提供的应用程序

-   Java 应用程序

-   Windows 应用

**注意** UE-V 设置位置模板不能从虚拟化应用程序或终端服务应用程序创建。 但是，可将使用模板同步的设置应用于这些应用程序。 若要创建支持虚拟桌面基础结构（VDI）和终端服务应用程序的模板，请使用 UE-V 生成器打开应用程序的 Windows Installer （.msi）程序包版本。 有关同步虚拟应用程序的设置的详细信息，请参阅[使用 ue-v 2 和应用程序虚拟化应用](using-ue-v-2x-with-application-virtualization-applications-both-uevv2.md)程序。

 

**排除的位置：** 发现过程排除了通常存储应用软件文件的位置，这些文件不会在用户计算机或计算环境之间同步设置。 默认情况下，这些值将被排除：

-   HKEY \ _CURRENT 已登录用户无法向其写入值的 _USER 注册表项和文件

-   HKEY \ _CURRENT \ _USER 与 Windows 操作系统的核心功能相关联的注册表项和文件

-   位于 HKEY \ _LOCAL \ _MACHINE 配置单元中的所有注册表项

-   位于程序文件目录中的文件

-   位于用户 \\ [User name \] \\ AppData \\ LocalLow 中的文件

-   位于% Systemroot% 中的 Windows 操作系统文件

如果需要在排除位置存储的注册表项和文件同步应用程序设置，则可以在模板创建过程中手动将位置添加到设置位置模板。
但是，只有对 HKEY \ _CURRENT \ _USER 配置单元的更改才会同步。

### 替换默认的 Microsoft 模板

UE-V Agent 将为常见的 Microsoft 应用程序和 Windows 设置安装默认设置位置模板组。 如果自定义这些模板或创建设置位置模板以同步自定义应用程序的设置，则可以将 UE-V Agent 配置为使用设置模板目录来存储模板。 在这种情况下，你将需要在设置模板目录中包含默认模板以及自定义模板。

在[部署 Ue-v Agent](https://technet.microsoft.com/library/dn458891.aspx#agent)时，可以使用命令行参数 `RegisterMSTemplates` 禁用默认 Microsoft 模板的注册。

使用组策略配置设置模板目录路径时，可以选择替换默认的 Microsoft 模板。 如果将策略设置配置为替换默认的 Microsoft 模板，则将删除由 UE-V Agent 安装的所有默认 Microsoft 模板，并且仅使用位于设置模板目录中的模板。 UE-V Agent 配置设置参数 `RegisterMSTemplates` 必须设置为*true*才能替代默认的 Microsoft 模板。

**注意** 如果在启用此策略设置后禁用此策略设置，则 UE-V Agent 不会还原默认的 Microsoft 模板。

 

如果设置模板目录中存在使用与默认 Microsoft 模板相同 ID 的自定义模板，并且未将 UE-V Agent 配置为替换默认的 Microsoft 模板，则忽略 Microsoft 模板。

你还可以使用 UE-V Windows PowerShell 功能替换默认模板。 若要将默认的 Microsoft 模板替换为 Windows PowerShell，请注销所有默认的 Microsoft 模板，然后注册自定义模板。

**注意** 即使为应用程序部署新的设置位置模板，旧的设置程序包仍保留在设置存储位置。 这些程序包不会由代理读取，但它们都不会自动删除。

 

## <a href="" id="uevgen"></a>安装 UEV 生成器


在可用于创建自定义设置位置模板的计算机上安装 Microsoft 用户体验虚拟化（UE-V）2.0 生成器。 此计算机应为要生成的自定义设置位置模板安装应用程序。

**安装 UE-V 发生器**

1.  作为具有本地管理员权限的用户，找到与 UE-V 软件一起提供的 UE-V 发生器安装文件**ToolSetup.exe** 。 或者，如果你知道计算机体系结构，则可以运行相应的 Windows Installer （.msi）文件， **ToolsSetupx64.msi**或**ToolsSetupx86.msi**。

2.  双击安装文件。 此时将打开 "用户体验虚拟化生成器设置向导"。 单击**下一步**以继续。

3.  接受 Microsoft 软件许可条款，然后单击 "**下一步**"。

4.  单击 "Microsoft 更新" 和 "客户体验改善计划" 的选项。

5.  选择要在其中安装 UE-V 发生器的目标文件夹，然后单击 "**下一步**"。

6.  单击 "**安装**" 以开始安装。

    **注意** 在安装应用程序之前显示**用户帐户控制**提示。 需要具有权限才能安装 UE-V 生成器。

     

7.  安装完成后，单击 "**完成**" 关闭向导。 必须重新启动计算机才能运行 UE-V 发生器。

    若要验证安装是否成功，请依次单击 "**开始**"、"**所有程序**"、" **microsoft 用户体验虚拟化**"，然后单击 " **microsoft 用户体验虚拟化生成器**"。

    **注意** UE-V 2 生成器仅可用于为 UE-V 2 代理创建模板。 在 UE-V 1.0 代理和 UE-V 2 代理的混合部署中，应继续使用 UE-V 1.0 生成器，直到升级了所有 UE-V Agent。

     

## <a href="" id="deploycatalogue"></a>部署设置模板目录


用户体验虚拟化设置模板目录是 UE-V 计算机上的文件夹路径或用于存储所有自定义设置位置模板的服务器消息块（SMB）网络共享。 UE-V Agent 中的计划任务每日检查此位置一次，并根据此文件夹中的模板更新其同步行为。

UE-V Agent 将在最后一次检查文件夹并注销删除的模板后，注册在此文件夹中添加或更新的模板。 默认情况下，在 3:30 A.M. 每天注册和注销模板一次。 任务计划程序和系统启动时的本地时间。 若要自定义此计划任务的频率，请参阅[更改 ue-v 2. x 计划任务的频率](changing-the-frequency-of-ue-v-2x-scheduled-tasks-both-uevv2.md)。

你可以使用安装命令行选项、组策略、WMI 或 Windows PowerShell 配置设置模板目录路径。 存储在设置模板目录路径上的模板由计划任务自动注册和注销。

**配置用于 UE-V 2 的设置模板目录**

1.  在存储 UE-V 设置模板目录的计算机上创建一个新文件夹。

2.  为设置模板目录文件夹设置以下共享级别（SMB）权限。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong>用户帐户</strong></th>
    <th align="left"><strong>推荐的权限</strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>所有人</p></td>
    <td align="left"><p>无权限</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>域计算机</p></td>
    <td align="left"><p>读取权限级别</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>管理员</p></td>
    <td align="left"><p>读/写权限级别</p></td>
    </tr>
    </tbody>
    </table>

     

3.  为设置模板目录文件夹设置以下 NTFS 文件系统权限。

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">用户帐户</th>
    <th align="left">推荐的权限</th>
    <th align="left">应用于</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>创建者/所有者</p></td>
    <td align="left"><p>完全控制</p></td>
    <td align="left"><p>此文件夹、子文件夹和文件</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>域计算机</p></td>
    <td align="left"><p>列出文件夹内容和阅读</p></td>
    <td align="left"><p>此文件夹、子文件夹和文件</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>所有人</p></td>
    <td align="left"><p>无权限</p></td>
    <td align="left"><p>无权限</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>管理员</p></td>
    <td align="left"><p>完全控制</p></td>
    <td align="left"><p>此文件夹、子文件夹和文件</p></td>
    </tr>
    </tbody>
    </table>

     

4.  单击 **"确定"** 关闭对话框。

至少，网络共享必须为 "域计算机" 组授予权限。 此外，将网络共享文件夹的访问权限授予管理已存储模板的管理员。

## <a href="" id="createcustomtemplates"></a>创建自定义设置位置模板


使用 UE-V 生成器为业务线应用程序或其他自定义应用程序创建设置位置模板。 创建应用程序的模板后，可以将其部署到计算机，以便为该应用程序同步设置。

**使用 UE-V 生成器创建 UE-V 设置位置模板**

1.  依次单击 "**开始**"、"**所有程序**"、" **microsoft 用户体验虚拟化**"，然后单击 " **microsoft 用户体验虚拟化生成器**"。

2.  单击 "**创建设置位置模板**"。

3.  指定应用程序。 通过浏览找到要为其创建设置位置模板的应用程序（.exe）或应用程序快捷方式（.lnk）的文件路径。 指定命令行参数（如果有）和工作目录（如果有）。 单击**下一步**以继续。

    **注意** 在应用程序启动之前，系统将显示 "**用户帐户控制**" 提示。 需要权限来监视应用程序用于存储设置的注册表和文件位置。

     

4.  应用程序启动后，关闭该应用程序。 UE-V 生成器记录应用程序存储其设置的位置。

5.  过程完成后，单击 "**下一步**" 以继续。

6.  查看并选择相应注册表设置位置旁边的复选框，并选择要为此应用程序同步的设置文件位置。 该列表包含设置位置的以下两个类别：

    -   **标准**：存储在注册表中的应用程序设置，这些设置存储在 HKEY \ _CURRENT \ _USER 键或在 \\**用户**\\ [用户名 \] \ **AppData**漫游] 下的文件文件夹中  \\  **Roaming**。 UE-V 生成器默认包括这些设置。

    -   **非标准**：在 "设置数据存储" 的最佳做法中指定存储在位置外部的应用程序设置（可选）。 其中包括 " **Users** \\ [用户名 \] \" \ " **AppData**  \\  **本地**的文件和文件夹"。 查看这些位置以确定是否将它们包含在 "设置位置" 模板中。 选中 "位置" 复选框以包括它们。

    单击**下一步**以继续。

7.  查看和编辑设置位置模板的任何**属性**、**注册表**位置和**文件**位置。

    -   在 "**属性**" 选项卡上编辑以下属性：

        -   **应用程序名称**：在程序文件属性的描述中写入的应用程序名称。

        -   **程序名称**：从程序文件属性中获取的程序的名称。 此名称通常具有 .exe 文件扩展名。

        -   **产品版本**：应用程序的 .exe 文件的产品版本号。 此属性与**文件版本**结合使用，可帮助确定设置位置模板面向的应用程序。 此属性接受主版本号。 如果此属性为空，则设置位置模板适用于产品的所有版本。

        -   **文件版本**：应用程序的 .exe 文件的文件版本号。 此属性与**产品版本**结合使用，可帮助确定设置位置模板面向的应用程序。 此属性接受主版本号。 如果此属性为空，则设置位置模板将应用于该程序的所有版本。

        -   **模板作者名称**（可选）：设置位置模板作者的名称。

        -   **模板作者电子邮件**（可选）：设置位置模板作者的电子邮件地址。

    -   "**注册表**" 选项卡列出了 "设置位置" 模板中包含的注册表位置的**密钥**和**范围**。 使用 "**任务**" 下拉菜单编辑注册表位置。 任务使你能够添加新密钥、编辑现有密钥的名称或作用域、删除密钥以及浏览注册表项所在的注册表。 使用 "**所有设置**" 范围将所有注册表设置包含在指定的键下。 使用 "**所有设置" 和 "子项**"，将所有注册表设置包含在指定的项、子项和子项设置下。

    -   "**文件**" 选项卡列出了 "设置位置" 模板中包含的文件位置的文件路径和文件掩码。 通过使用 "**任务**" 下拉菜单来编辑文件位置。 文件位置的任务使你能够添加新文件或文件夹位置、编辑现有文件或文件夹的范围、删除文件或文件夹，以及在 Windows 资源管理器中打开所选位置。 将文件掩码保留为空，以包括指定文件夹中的所有文件。

8.  单击 "**创建**"，然后单击 "**保存**" 以在计算机上保存设置位置模板。

9.  单击 "**关闭**" 以关闭 "设置模板" 向导。 退出 UE-V 发生器应用程序。

    为应用程序创建设置位置模板后，应测试该模板。 在实验室环境中部署模板，然后再将其放入企业中的生产环境中。

UE-V 详细信息的[应用程序模板参考](https://technet.microsoft.com/library/dn763947.aspx)ue-v 设置位置模板的 XML 结构，并提供编辑这些文件的指南。

## <a href="" id="deploycustomtemplates"></a>部署自定义设置位置模板


使用 UE-V 生成器创建设置位置模板后，应对其进行测试以确保正确同步应用程序设置。 然后，您可以安全地将设置位置模板部署到企业中的计算机。

可以使用以下任一方法部署设置位置模板：

-   企业软件分发（ESD）系统，如 System Center Configuration Manager

-   组策略首选项

-   UE-V 设置模板目录

使用 ESD 系统或组策略对象部署的模板必须通过 UE-V Windows Management Instrumentation （WMI）或 Windows PowerShell 注册。 存储在设置模板目录位置的模板由 UE-V Agent 自动注册。

**使用设置模板目录路径部署 UE-V 设置位置模板**

1.  浏览到定义为设置模板目录的网络共享文件夹。

2.  在设置模板目录中添加、删除或更新设置位置模板，以反映你希望用于 UE-V 计算机的 UE-V Agent 模板配置。

    **注意** 计算机上的模板每天更新。 更新基于对设置模板目录所做的更改。

     

3.  若要在运行 UE-V Agent 的计算机上手动更新模板，请打开提升的命令提示符，并浏览到 **% 程序 Files%\\Microsoft 用户体验虚拟化 \\ 代理 \ &lt; x86 或 x64 &gt; **，然后运行**ApplySettingsTemplateCatalog.exe**。

    **注意** 此程序将在计算机启动期间和每天3:30 的中自动运行。 收集最近添加到目录中的任何新模板。

     






## 相关主题


[准备 UE-V 2. x 部署](prepare-a-ue-v-2x-deployment-new-uevv2.md)

[为 UE-V 2.x 部署所需功能](deploy-required-features-for-ue-v-2x-new-uevv2.md)

 

 





