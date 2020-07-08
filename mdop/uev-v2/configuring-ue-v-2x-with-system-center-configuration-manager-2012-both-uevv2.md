---
title: 通过 System Center Configuration Manager 2012 配置 UE-V 2
description: 通过 System Center Configuration Manager 2012 配置 UE-V 2
author: dansimp
ms.assetid: 9a4e2a74-7646-4a77-b58f-2b4456487295
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/02/2016
ms.openlocfilehash: 2ff9ccc1a17db31471549ece37461558768c3a2b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803562"
---
# 通过 System Center Configuration Manager 2012 配置 UE-V 2


安装 Microsoft 用户体验虚拟化（UE-V）2.0、2.1 或 2.1 SP1 及其必需功能后，必须配置 UE-V。 UE-V 配置包为管理员使用 System Center Configuration Manager 2012 SP1 或更高版本的合规性设置功能在安装了 UE-V 和配置管理器的网站之间应用一致的配置提供了一种方式。

## UE-V 配置包支持的功能


UE-V 配置包包括用于执行以下任务的工具：

-   创建或更新 UE-V 设置位置模板分布基线。

    -   定义要注册或注销的 UE-V 模板

    -   添加或更新模板时更新 UE-V 模板配置项目和基线

    -   使用标准配置项目补救措施分发和注册 UE-V 模板

-   创建或更新 UE-V Agent 策略配置项目以设置或清除这些设置。

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p>程序包最大大小</p></td>
    <td align="left"><p>启用/禁用 Windows 应用同步</p></td>
    <td align="left"><p>在应用程序启动时等待同步</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>设置导入延迟</p></td>
    <td align="left"><p>同步未列出的 Windows 应用</p></td>
    <td align="left"><p>等待登录时同步</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>设置导入通知</p></td>
    <td align="left"><p>IT 联系人 URL</p></td>
    <td align="left"><p>等待同步超时</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>设置存储路径</p></td>
    <td align="left"><p>联系说明性文本</p></td>
    <td align="left"><p>设置模板目录路径</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>同步启用</p></td>
    <td align="left"><p>托盘图标已启用</p></td>
    <td align="left"><p>开始/停止 UE-V agent 服务</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>同步方法</p></td>
    <td align="left"><p>首次使用通知</p></td>
    <td align="left"><p>定义哪些 Windows 应用将漫游设置</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>同步超时</p></td>
    <td align="left"><p></p></td>
    <td align="left"><p></p></td>
    </tr>
    </tbody>
    </table>

     

-   通过确认 UE-V 正在运行来验证合规性。

## 生成 UE-V Agent 策略配置项目


所有 UE-V Agent 策略和配置均通过使用 UevAgentPolicyGenerator.exe 工具生成的单个配置项目进行分发。 此工具从 XML 配置文件中读取所需的配置，并创建一个 CI，其中包含使计算机遵守合规性所需的发现和更正设置。

UE-V Agent 策略配置项目 CAB 文件是使用 UevTemplateBaselineGenerator.exe 命令行工具创建的，该工具具有以下参数：

-   网站 &lt; 网站代码&gt;

-   PolicyName &lt; 名称 &gt; 可选：默认为 "Ue-v Agent Policy" （如果不存在）

-   PolicyDescription &lt; 说明 &gt; 可选：如果不存在，则提供说明

-   CabFilePath &lt; 配置项目的完整路径。CAB 文件&gt;

-   ConfigurationFile &lt; 代理配置 XML 文件的完整路径&gt;

**注意** 可能需要更改 PowerShell 执行策略以允许这些脚本在你的环境中运行。 在 Configuration Manager 控制台中执行以下步骤：

1.  选择**管理 &gt; 客户端设置 &gt; 属性**

2.  在 "**用户代理**" 选项卡中，将 " **PowerShell 执行策略**" 设置为 "**绕过**"

<a href="" id="create"></a>**创建第一个 UE-V 策略配置项目**

1.  将默认设置配置文件从 UE-V Config Pack 安装目录复制到 ConfigMgr 管理员控制台可见的位置：

    ``` syntax
    C:\Program Files (x86)\Microsoft User Experience Virtualization\ConfigPack\AgentConfiguration.xml c:\<target path>
    ```

    默认配置文件包含五个部分：

    <a href="" id="computer-policy"></a>**计算机策略**  
    所有 UE-V 计算机级设置。 DesiredState 属性可以

    -   **设置**为在注册表中分配值

    -   **清除**以删除设置

    -   **非托管**以使配置项目处于其当前状态

    请勿删除本部分中的行。 如果不希望 Configuration Manager 更改当前值或默认值，请改为将 DesiredState 设置为 "非托管"。

    <a href="" id="currentcomputeruserpolicy"></a>**CurrentComputerUserPolicy**  
    所有 UE-V 用户级别设置。 这些条目会替代用户的计算机设置。 DesiredState 属性可以

    -   **设置**为在注册表中分配值

    -   **清除**以删除设置

    -   **非托管**以使配置项目处于其当前状态

    请勿删除本部分中的行。 如果不希望 Configuration Manager 更改当前值或默认值，请改为将 DesiredState 设置为 "非托管"。

    <a href="" id="services"></a>**服务**  
    此部分控件服务操作中的条目。 默认配置文件包含 UevAgentService 的单个条目。 DesiredState 属性可以设置为 "**正在运行**" 或 "**已停止**"。

    <a href="" id="windows8appscomputerpolicy"></a>**Windows8AppsComputerPolicy**  
    所有计算机级 Windows 应用同步设置。 可以为本部分中列出的每个 PackageFamilyName 分配一个 DesiredState

    -   **已启用**以设置漫游

    -   **禁用**以防止漫游设置

    -   已**清除**以从 ue-v control 中删除条目

    可使用 PowerShell cmdlet GetAppxPackage 查看已安装的 Windows 应用列表，从而将其他行添加到此部分。

    <a href="" id="windows8appscurrentcomputeruserpolicy"></a>**Windows8AppsCurrentComputerUserPolicy**  
    与 Windows8AppsComputerPolicy 的设置相同，该设置会替代单个用户的计算机设置。

2.  通过更改所需的 "状态" 和 "值" 字段来编辑配置文件。

3.  在运行 ConfigMgr 管理员控制台的计算机上运行此命令：

    ``` syntax
    C:\Program Files (x86)\Microsoft User Experience Virtualization\ConfigPack\UevAgentPolicyGenerator.exe –Site ABC –CabFilePath "C:\MyCabFiles\UevPolicyItem.cab" –ConfigurationFile "c:\AgentConfiguration.xml"
    ```

4.  使用 ConfigMgr 控制台或 PowerShell Import 导入 CAB 文件 CMConfigurationItem

**更新 UE-V 策略配置项目**

1.  通过更改所需的 "状态" 和 "值" 字段来编辑配置文件。

2.  在[创建第一个 Ue-v 策略配置项](#create)中的步骤3中运行命令。 如果您已通过 PolicyName 参数更改了名称，请确保输入相同的名称。

3.  重新导入 CAB 文件。 将更新 ConfigMgr 中的版本。

## 生成 UE-V 模板基线
UE-V 模板是使用包含多个配置项目的基线分发的。 每个配置项目都包含安装一个 UE-V 模板所需的发现和修正脚本。 实际 UE-V 模板嵌入在用于使用标准配置项目功能分发的更新脚本中。

UE-V 模板基线是使用 UevTemplateBaselineGenerator.exe 命令行工具创建的，该工具具有以下参数：

-   网站 &lt; 网站代码&gt;

-   BaselineName &lt; 名称 &gt; （可选：默认为 "Ue-v 模板分布基线" （如果不存在）

-   BaselineDescription &lt; 说明 &gt; （可选：如果不存在，则提供说明）

-   TemplateFolder &lt; ue-v 模板文件夹&gt;

-   注册 &lt; 逗号分隔的模板文件列表&gt;

-   注销 &lt; 以逗号分隔的模板列表&gt;

-   CabFilePath 要 &lt; 生成的基线 CAB 文件的完整路径&gt;

结果是一个可以导入到 Configuration Manager 的基线 CAB 文件。 如果在将来日期更新或添加模板，则可以使用相同的基线名称重新运行命令。 在更改后的模板上导入的 CAB 会导致 CI 版本更新。

### <a href="" id="create2"></a>创建第一个 UE-V 模板基线

1.  在运行 ConfigMgr 管理员控制台的计算机可见的稳定文件夹位置中创建一个 "母版" 一组 UE-V 模板。 添加或更新模板后，此文件夹将被拉入以进行分发。 可以从安装了 UE-V 的计算机复制模板的初始列表。 默认模板位置是 C:\\program files Files\\Microsoft 用户体验 Virtualization\\Templates。

2.  创建可在其中添加模板生成器命令的 text.bat 文件。 这是可选的，但如果保存命令参数，则会使再生更简单。

3.  将命令和参数添加到将生成基线的 .bat 文件。 下面的示例创建了一个分发记事本和计算器的比较基准：

    ``` syntax
    C:\Program Files (x86)\Microsoft User Experience Virtualization\ConfigPack\UevTemplateBaselineGenerator.exe –Site "ABC" –TemplateFolder "C:\ProductionUevTemplates" –Register "MicrosoftNotepad.xml, MicrosoftCalculator.xml" –CabFilePath "C:\MyCabFiles\UevTemplateBaseline.cab"
    ```

4.  运行 .bat 文件，创建 UevTemplateBaseline.cab 准备导入到配置管理器。

### 更新 UE-V 模板基线

模板生成器使用模板版本来确定是否应更新模板。 如果你进行模板更改并更新版本，则基线生成器会将你的主文件夹中的模板与 ConfigMgr 服务器上 CI 中包含的模板进行比较。 如果发现差异，则会更新生成的基线和修改后的 CI 版本。

要分发新的记事本模板，请执行以下步骤：

1.  更新位于模板的版本元素中的模板和模板版本 &lt; &gt; 。

2.  将模板复制到您的主模板目录。

3.  在[创建第一个 Ue-v 模板基线](#create2)的步骤3中创建的 .bat 文件中运行该命令。

4.  使用 console 或 PowerShell Import-CMBaseline 将生成的 CAB 文件导入 ConfigMgr。

## 获取 UE-V 配置包


可在[此处](https://go.microsoft.com/fwlink/?LinkId=317263)下载 Configuration MANAGER 2012 SP1 或更高版本的 Ue-v 配置包。






## 相关主题


[管理 UE-V 2.x 的配置](manage-configurations-for-ue-v-2x-new-uevv2.md)

 

 





