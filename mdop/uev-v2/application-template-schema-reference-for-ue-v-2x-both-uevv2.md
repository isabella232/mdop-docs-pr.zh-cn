---
title: 用于 UE-V 2 的应用程序模板架构参考
description: 用于 UE-V 2 的应用程序模板架构参考
author: dansimp
ms.assetid: be8735a5-6a3e-4b1f-ba14-2a3bc3e5a8b6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 03ff6eabae68f07c23d5977f901e6a90e292c6ac
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10804162"
---
# 用于 UE-V 2 的应用程序模板架构参考


Microsoft 用户体验虚拟化（UE-V）2.0、2.1 和 2.1 SP1 使用 XML 设置位置模板来定义由 UE-V 捕获和应用的桌面应用程序设置和 Windows 设置。 UE-V 包含一组默认设置位置模板。 你还可以通过 UE-V 生成器创建自定义设置位置模板。

高级用户可以自定义设置位置模板的 XML 文件。 本主题详细介绍了 UE-V 2.1 （SP1）和2.0 设置位置模板的 XML 结构，并提供了编辑这些文件的指南。

## UE-V 2.1 和 2.1 SP1 应用程序模板参考


本节详细介绍了 UE-V 2.1 和 2.1 SP1 设置位置模板的 XML 结构，并提供了编辑此文件的指南。

### 本部分内容

-   [XML 声明和编码属性](#xml21)

-   [命名空间和根元素](#namespace21)

-   [数据类型](#data21)

-   [名称元素](#name21)

-   [ID 元素](#id21)

-   [版本元素](#version21)

-   [作者元素](#author21)

-   [进程和进程元素](#processes21)

-   [应用程序元素](#application21)

-   [常见元素](#common21)

-   [SettingsLocationTemplate 元素](#settingslocationtemplate21)

-   [附录： SettingsLocationTemplate](#appendix21)

### <a href="" id="xml21"></a>XML 声明和编码属性

**强制： True**

**类型： String**

XML 声明必须指定 XML 版本1.0 属性（ &lt; ？ xml version = "1.0" &gt; ）。 由 UE-V 生成器创建的设置位置模板将保存为 UTF-8 编码，尽管编码没有明确指定。 我们建议你在此元素中将 encoding = "UTF-8" 属性作为最佳做法包括在内。 本产品附带的所有模板也都指定了此标记（请参阅%ProgramFiles%\\Microsoft 用户体验 Virtualization\\Templates 中的文档以了解参考）。 例如：

`<?xml version="1.0" encoding="UTF-8"?>`

### <a href="" id="namespace21"></a>命名空间和根元素

**强制： True**

**类型： String**

UE-V 使用 https://schemas.microsoft.com/UserExperienceVirtualization/2012/SettingsLocationTemplate 所有应用程序的命名空间。 SettingsLocationTemplate 是根元素，包含所有其他元素。 使用此标记的所有模板中的引用 SettingsLocationTemplate：

`<SettingsLocationTemplate xmlns='https://schemas.microsoft.com/UserExperienceVirtualization/2012/SettingsLocationTemplate'>`

### <a href="" id="data21"></a>数据类型

以下是 UE-V 应用程序模板架构的数据类型。

<a href="" id="guid"></a>**GUID**GUID 描述一个标准的全局唯一标识符正则表达式，格式为 "\\ {\ [a-F0 \] {8} -\ [a – fa-F0-9 \] {4} [a-Fa-F0 \] {4} -\ [a – F0-9 \] \ [a-- {4} F0-9 \] {12} \}"。 在 Filesetting\\Root\\KnownFolder 元素中使用此功能来验证已知文件夹的格式。

<a href="" id="filenamestring"></a>**FilenameString**FilenameString 是指要监视的进程的文件名。 它的值受 regex \ [^ \ \ \ \ * &lt; &gt; \？/： \] +，（也就是说，它们不能包含反斜杠字符、星号或问号通配符、管道字符、大于或小于符号、正斜杠或冒号字符）。

<a href="" id="idstring"></a>**IDString**IDString 是指应用程序元素、SettingsLocationTemplate 和常见元素（用于描述共享通用设置的应用程序套件）的 ID 值。 它受与 FilenameString 相同的正则表达式的限制（\ [^ \ \ \ \ * \ \ * &lt; &gt; \/:\]+).

<a href="" id="templateversion"></a>**TemplateVersion**TemplateVersion 是用于描述设置位置模板的版本的整数值。 其值的范围可以从0到2147483647。

<a href="" id="empty"></a>**空**空表示空值。 此功能在 Process\\ShellProcess 中用于指示没有要监视的进程。 此值不应在任何应用程序模板中使用。

<a href="" id="author"></a>**作者**"作者" 数据类型是标识模板作者的复杂类型。 它包含两个子元素：**名称**和**电子邮件**。 在 "作者" 数据类型中，Name 元素是必需的，而 Email 元素是可选的。 此类型将在 SettingsLocationTemplate 元素下更详细地进行介绍。

<a href="" id="range"></a>**区域**Range 定义一个包含两个子元素的整数类：**最小值**和**最大值**。 此数据类型在 ProcessVersion 数据类型中实现。 如果已指定，则必须同时包含最小值和最大值。

<a href="" id="processversion"></a>**ProcessVersion**ProcessVersion 定义了一个包含四个子元素的类型：**主要**、**次要**、**内部版本**和**修补程序**。 Process 元素使用此数据类型填充其 ProductVersion 和 FileVersion 值。 此类型的数据是一个范围值。 主要子元素是必需的，而其他元素是可选的。

<a href="" id="architecture"></a>**体系结构**体系结构枚举两个可能的值： **Win32**和**Win64**。 这些值用于指定进程体系结构。

<a href="" id="process"></a>**处理**"流程" 数据类型是用于描述由 UE-V 监视的流程的容器。 它包含六个子元素： **Filename**、**体系结构**、 **ProductName**、 **FileDescription**、 **ProductVersion**和**FileVersion**。 下表详细介绍了每个元素各自的数据类型：

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>元素</strong></p></td>
<td align="left"><p><strong>数据类型</strong></p></td>
<td align="left"><p><strong>Mandatory</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>相配</p></td>
<td align="left"><p>FilenameString</p></td>
<td align="left"><p>True</p></td>
</tr>
<tr class="odd">
<td align="left"><p>体系结构</p></td>
<td align="left"><p>体系结构</p></td>
<td align="left"><p>False</p></td>
</tr>
<tr class="even">
<td align="left"><p>ProductName</p></td>
<td align="left"><p>字符串</p></td>
<td align="left"><p>False</p></td>
</tr>
<tr class="odd">
<td align="left"><p>FileDescription</p></td>
<td align="left"><p>字符串</p></td>
<td align="left"><p>False</p></td>
</tr>
<tr class="even">
<td align="left"><p>ProductVersion</p></td>
<td align="left"><p>ProcessVersion</p></td>
<td align="left"><p>False</p></td>
</tr>
<tr class="odd">
<td align="left"><p>FileVersion</p></td>
<td align="left"><p>ProcessVersion</p></td>
<td align="left"><p>False</p></td>
</tr>
</tbody>
</table>

 

<a href="" id="processes"></a>**流程**"流程" 数据类型表示一个容器，用于一个或多个流程元素的集合。 进程序列类型中支持两个子元素： **Process**和**ShellProcess**。 Process 是 Process 类型的元素，ShellProcess 的数据类型为 Empty。 序列中必须至少标识一个项目。

<a href="" id="path"></a>**路径**RegistrySetting 和 FileSetting 使用 Path 来引用注册表和文件路径。 此元素支持两个可选属性： **Recursive**和**DeleteIfNotFound**。 两个值均设置为默认值 = "False"。

递归表示文件设置包含路径和所有子文件夹，或者注册表设置包含所有子注册表项。 在这两种情况下，当前级别的所有项目都包含在捕获的数据中。 对于 FileSettings 对象，指定文件夹中的所有文件都包含在由 UE-V 捕获的数据中，但不包括文件夹。 对于注册表路径，将捕获当前路径中的所有值，但不捕获子注册表项。 在这两种情况下，应注意避免捕获大型数据集或大量项目。

DeleteIfNotFound 属性从用户的设置存储路径数据中删除设置。 在从包中删除这些设置将在设置存储路径文件服务器上保存大量磁盘空间时，这可能是理想的情况。

<a href="" id="filemask"></a>**FileMask**FileMask 仅指定由 Path 定义的文件夹的某些文件类型。 例如，Path 可能是 `C:\users\username\files` 且 FileMask 可以 `*.txt` 仅包含文本文件。

<a href="" id="registrysetting"></a>**RegistrySetting**RegistrySetting 表示注册表项和值的容器，以及 UE-V Agent 部分相关联的所需行为。 在此类型中定义了四个子元素：**路径**、**名称**、**排除**和值**路径**和**名称**的序列。

<a href="" id="filesetting"></a>**FileSetting**FileSetting 包含与文件和文件路径相关联的参数。 定义了四个子元素： **Root**、 **Path**、 **FileMask**和**Exclude**。 根是强制性的，而其他是可选的。

<a href="" id="settings"></a>**设置**"设置" 是适用于特定模板的所有设置的容器。 它包含前面所述的注册表、文件、SystemParameter 和 CustomAction 设置的实例。 此外，它还可以包含包含以下行为的以下子元素：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>元素</strong></p></td>
<td align="left"><p><strong>描述</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>异步</p></td>
<td align="left"><p>在不阻止应用程序启动的情况下应用异步设置程序包，以便应用程序在设置仍在应用时启动。 这对于可以异步应用的设置（例如 <code>get/set</code> ，通过 API （如 SystemParameterSetting）很有用。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>PreventOverlappingSynchronization</p></td>
<td align="left"><p>默认情况下，当使用模板的最后一个应用程序实例关闭时，UE-V 仅保存应用程序的设置。 当此元素设置为 "false" 时，UE-V 将导出设置，即使应用程序的其他实例正在运行。 适用的模板（包括常见元素部分的模板）使用此标志可使共享设置始终在应用程序关闭时导出，同时防止应用程序特定的设置在最后一个实例关闭之前导出。</p></td>
</tr>
<tr class="even">
<td align="left"><p>AlwaysApplySettings</p></td>
<td align="left"><p>（在2.1 中引入）</p>
<p>此参数会强制应用导入的设置包，即使应用程序的程序包和当前状态之间没有差异也是如此。 此参数应仅在特殊情况下使用，因为它可能会减慢设置导入的速度。</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="name21"></a>名称元素

**强制： True**

**类型： String**

名称指定设置位置模板的唯一名称。 这用于在 WMI、PowerShell、事件查看器和调试日志中引用模板时的显示用途。 通常，请避免引用版本信息，因为这可以从 ProductVersion 元素中 objected。 例如，指定 " `<Name>My Application</Name>` 而不是" `<Name>My Application 1.1</Name>` 。

**注意** UE-V 不引用外部 Dtd，因此不能使用设置位置模板中的命名实体。 例如，不要使用 &reg; 来指注册的商标签名®。 而是使用规范编号引用包括这些类型的特殊字符，例如 &®字符的 \ #174。 此规则适用于此文档中的所有字符串值。

<http://www.w3.org/TR/xhtml1/dtds.html>有关字符实体的完整列表，请参阅。 UTF-8 编码的文档可能直接包含 Unicode 字符。 通过 UE-V 生成器保存模板将自动将字符实体转换为其 Unicode 表示形式。

 

### <a href="" id="id21"></a>ID 元素

**强制： True**

**类型： String**

ID 填充特定模板的唯一标识符。 此标记将成为 UE-V Agent 在运行时引用模板时使用的主标识符（例如，请参阅 UevTemplate 和 UevTemplateProgram PowerShell cmdlet 的输出）。 按照约定，此标记不应包含任何空格，从而简化了脚本编写。 应在此元素中指定应用程序的版本号，以便更轻松地标识模板，例如 `<ID>MicrosoftCalculator6</ID>` 或 `<ID>MicrosoftOffice2010Win64</ID>` 。

### <a href="" id="version21"></a>版本元素

**强制： True**

**类型： Integer**

**最小值：0**

**最大值：2147483647**

版本标识用于管理更改管理跟踪的设置位置模板的版本。 每次保存模板时，UE-V 生成器都会自动将该数字递增1。 请注意，此字段必须为整数整数;不允许使用小数值，例如 `<Version>2.5</Version>` 。

**提示：** 你可以使用 XML 注释标记保存有关版本更改 `<!-- -->` 的注释，例如：

```xml
  <!--
     Version History

     Version 1 Jul 05, 2012 Initial template created by Generator - Denise@Contoso.com
     Version 2 Jul 31, 2012 Added support for app.exe v2.1.3 - Mark@Contoso.com
     Version 3 Jan 01, 2013 Added font settings support - Mark@Contoso.com
     Version 4 Jan 31, 2013 Added support for plugin settings - Tony@Contoso.com
   -->
  <Version>4</Version>
```

**重要提示** 将查询此值，以确定是否应将模板的新版本应用于这些实例中的现有模板：

-   执行计划模板自动更新任务时

-   当执行 UevTemplate PowerShell cmdlet 时

-   当 microsoft\\uev： SettingsLocationTemplate Update 方法通过 WMI 调用时

 

### <a href="" id="author21"></a>作者元素

**强制： False**

**类型： String**

作者标识设置位置模板的创建者。 支持两个可选子元素：**名称**和**电子邮件**。 这两个属性都是可选的，但如果指定了电子邮件子元素，则它必须附有 Name 元素。 作者指的是 "设置位置" 模板的联系人的全名，电子邮件应该指作者的电子邮件地址。 建议在公共发布的模板中包括此信息，例如，在[Ue-v 模板库](https://gallery.technet.microsoft.com/site/search?f%5B0%5D.Type=RootCategory&f%5B0%5D.Value=UE-V)中。

### <a href="" id="processes21"></a>进程和进程元素

**强制： True**

**类型：元素**

进程至少包含一个 `<Process>` 元素，该元素又包含以下子元素： **Filename**、**体系结构**、 **ProductName**、 **FileDescription**、 **ProductVersion**和**FileVersion**。 Filename 子元素是必需的，而其他元素是可选的。 完全填充的元素包含与以下示例类似的标记：

```xml
<Process>
  <Filename>MyApplication.exe</Filename>
  <Architecture>Win64</Architecture>
  <ProductName> MyApplication </ProductName>
  <FileDescription>MyApplication.exe</FileDescription>
  <ProductVersion>
    <Major Minimum="2" Maximum="2" />
    <Minor Minimum="0" Maximum="0" />
    <Build Minimum="0" Maximum="0" />
    <Patch Minimum="5" Maximum="5" />
  </ProductVersion>
  <FileVersion>
    <Major Minimum="2" Maximum="2" />
    <Minor Minimum="0" Maximum="0" />
    <Build Minimum="0" Maximum="0" />
    <Patch Minimum="5" Maximum="5" />
  </FileVersion>
</Process>
```

### 相配

**强制： True**

**类型： String**

文件名是指在文件系统中显示的可执行文件的实际文件名。 此元素指定 UE-V 用于评估模板是否适用于进程的主要条件。 此元素必须在设置位置模板 XML 中指定。

有效的文件名必须与正则表达式 \ [^ \ &lt; &gt; \ \ \ \/： \] + 时，它们不能包含反斜杠字符、星号或问号通配符、管道字符、大于或小于符号、正斜杠或冒号（\\？） \* |&lt; &gt; /或：个字符。）

**提示：** 若要针对此 regex 测试字符串，请使用 PowerShell 命令窗口并将可执行文件的名称替换为**YourFileName**：

`"YourFileName.exe" -match  "[\\\?\*\|<>/:]+"`

**True**值表示字符串包含非法字符。 下面是一些非法值的示例：

-   \\\\server\\share\\program.exe

-   程序 \ * .exe

-   Pro？ ram.exe

-   程序 &lt; 1 &gt; .exe

**注意** UE-V 生成器分别对大于和小于字符进行编码 &gt; &lt; 。

 

在极少数情况下，文件名值不一定包含 .exe 扩展名，但应将其指定为值的一部分。 例如， `<Filename>MyApplictication.exe</Filename>` 应指定而不是 `<Filename>MyApplictication</Filename>` 。 如果可执行文件的实际名称为 "MyApplication.exe"，则第二个示例不会将模板应用于该进程。

### 体系结构

**强制： False**

**类型：体系结构（字符串）**

体系结构是指已编译目标可执行文件的处理器体系结构。 有效值为32位应用程序的 Win32 或64位应用程序的 Win64。 如果存在，此标记将设置位置模板的适用性限制为特定的应用程序体系结构。 有关此操作的示例，请比较%ProgramFiles%\\Microsoft 用户体验 Virtualization\\templates\\ MicrosoftOffice2010Win32.xml 和 UE-V 附带的 MicrosoftOffice2010Win64.xml 文件。 如果相对路径在不同版本的可执行文件之间更改，或者在从一个处理器体系结构移动到另一个时已添加或删除了设置，此方法将非常有用。

如果此元素不存在，则设置位置模板将忽略进程的体系结构，并将其应用于32和64位进程（如果应用了文件名和其他属性）。

**注意** UE-V 不支持此版本中的 ARM 处理器。

 

### ProductName

**强制： False**

**类型： String**

ProductName 是一个可选元素，用于标识用于管理用途或报告的产品。 ProductName 与 Filename 的不同之处在于它的值没有正则表达式限制。 这允许更容易理解的可执行文件名称可能不明显的进程的说明。 例如：

```xml
<Process>
  <Filename>MyApplication.exe</Filename>
  <ProductName>My Application 6.x by Contoso.com</ProductName>
  <ProductVersion>
    <Major Minimum="6" Maximum="6" />
  </ProductVersion>
</Process>
```

### FileDescription

**强制： False**

**类型： String**

FileDescription 是一个可选标记，可提供可执行文件的管理说明。 这是一个免费的文本字段，在需要标识可执行文件的功能的软件包中的多个可执行文件中非常有用。

例如，在一个合适的应用程序中，提供有关两个可执行文件（MyApplication.exe 和 MyApplicationHelper.exe）的功能的提醒可能很有用，如下所示：

```xml
<Processes>
  <Process>
    <Filename>MyApplication.exe</Filename>
    <FileDescription>My Application Main Engine</ FileDescription>
    <ProductVersion>
      <Major Minimum="6" Maximum="6" />
    </ProductVersion>
  </Process>
  <Process>
    <Filename>MyApplicationHelper.exe</Filename>
    <FileDescription>My Application Background Process Executable</FileDescription>
    <ProductVersion>
      <Major Minimum="6" Maximum="6" />
    </ProductVersion>
  </Process>
</Processes>
```

### ProductVersion

**强制： False**

**类型： String**

ProductVersion 是指文件的主要和次要产品版本以及版本和修补程序级别。 ProductVersion 是一个可选元素，但如果指定，它必须至少包含主要子元素。 此值必须以最小为 = "X" 的最大值 = "Y" 表示区域，其中 X 和 Y 是整数。 最小值和最大值可以相同。

产品和文件版本元素可以保留未指定。 这样做会使模板 "版本不限"，这意味着模板将应用于指定的可执行文件的所有版本。

**示例 1：**

UE-V 生成器中指定的产品版本：1.0 生成以下 XML：

```xml
<ProductVersion>
  <Major Minimum="1" Maximum="1" />
  <Minor Minimum="0" Maximum="0" />
</ProductVersion>
```

**示例 2：**

文件版本： UE-V 生成器中指定的5.0.2.1000 生成以下 XML：

```xml
<FileVersion>
  <Major Minimum="5" Maximum="5" />
  <Minor Minimum="0" Maximum="0" />
  <Build Minimum="2" Maximum="2" />
  <Patch Minimum="1000" Maximum="1000" />
</FileVersion>
```

**不正确的示例 1-未完成的范围：**

仅存在最小属性。 范围中还必须包含 "最大"。

```xml
<ProductVersion>
  <Major Minimum="2" />
</ProductVersion>
```

**不正确的示例 2-指定的次要元素没有主要元素：**

仅存在次要元素。 还必须包含主版本。

```xml
<ProductVersion>
  <Minor Minimum="0" Maximum="0" />
</ProductVersion>
```

### FileVersion

**强制： False**

**类型： String**

FileVersion 将区分已发布应用程序的发布版本和组件可执行文件的内部生成详细信息。 对于大多数商业应用程序，这些号码是相同的。 它们的不同之处是，文件的产品版本指示文件的常规版本标识，而文件版本指示文件的特定版本（如修补程序或更新）。 这将在不中断检测逻辑的情况下唯一标识文件。

若要确定特定可执行文件的产品版本和文件版本，请在 Windows 资源管理器中右键单击该文件，选择 "属性"，然后单击 "详细信息" 选项卡。

为应用程序包括 FileVersion 元素可实现更精细的微调检测逻辑，但对于大多数应用程序都不是必需的。 首先检查 ProductVersion 元素设置，然后选中 "FileVersion"。 将应用更严格的设置。

FileVersion 的子元素和语法规则与 ProductVersion 的子元素和语法规则相同。

```xml
<Process>
  <Filename>MSACCESS.EXE</Filename>
  <Architecture>Win32</Architecture>
  <ProductVersion>
    <Major Minimum="14" Maximum="14" />
    <Minor Minimum="0" Maximum="0" />
  </ProductVersion>
  <FileVersion>
    <Major Minimum="14" Maximum="14" />
    <Minor Minimum="0" Maximum="0" />
  </FileVersion>
</Process>
```

### <a href="" id="application21"></a>应用程序元素

应用程序是应用于特定应用程序的设置的容器。 它是以下字段/类型的集合。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>字段/类型</strong></p></td>
<td align="left"><p><strong>描述</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>名称</p></td>
<td align="left"><p>为设置位置模板指定一个唯一名称。 这用于在 WMI、PowerShell、事件查看器和调试日志中引用模板时的显示用途。 有关详细信息，请参阅 <a href="#name21" data-raw-source="[Name](#name21)"> 名称 </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ID</p></td>
<td align="left"><p>填充特定模板的唯一标识符。 此标记将成为 UE-V Agent 在运行时引用模板时使用的主要标识符。 有关详细信息，请参阅 <a href="#id21" data-raw-source="[ID](#id21)"> ID </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>描述</p></td>
<td align="left"><p>模板的可选说明。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>LocalizedNames</p></td>
<td align="left"><p>UI 中显示的可选名称，由语言区域设置本地化。</p></td>
</tr>
<tr class="even">
<td align="left"><p>LocalizedDescriptions</p></td>
<td align="left"><p>由语言区域设置本地化的可选模板说明。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>版本</p></td>
<td align="left"><p>标识用于管理更改管理跟踪的设置位置模板的版本。 有关详细信息，请参阅 <a href="#version21" data-raw-source="[Version](#version21)"> 版本 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>DeferToMSAccount</p></td>
<td align="left"><p>控制是否与 Microsoft 帐户一起启用此模板。 如果对计算机上的用户启用了 MSA 同步，则该模板将自动禁用。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>DeferToOffice365</p></td>
<td align="left"><p>与 MSA 类似，它控制此模板是否与 Office365 一起启用。 如果使用 Office 365 同步设置，此模板将自动禁用。</p></td>
</tr>
<tr class="even">
<td align="left"><p>FixedProfile （在2.1 中引入）</p></td>
<td align="left"><p>指定此模板只能与此元素中指定的配置文件关联，并且不能通过 WMI 或 PowerShell 进行更改。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>进程</p></td>
<td align="left"><p>一个容器，用于一个或多个流程元素的集合。 有关详细信息，请参阅 <a href="#processes21" data-raw-source="[Processes](#processes21)"> 流程 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>设置</p></td>
<td align="left"><p>适用于特定模板的所有设置的容器。 它包含注册表、File、SystemParameter 和 CustomAction 设置的实例。 有关详细信息，请 <strong> 参阅 </strong> 数据类型中的设置 <a href="#data21" data-raw-source="[Data types](#data21)"> </a> 。</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="common21"></a>常见元素

常用于应用程序元素，但它始终与两个或更多个应用程序元素关联。 "常见" 部分表示在这些应用程序实例之间共享的一组设置。 它是以下字段/类型的集合。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>字段/类型</strong></p></td>
<td align="left"><p><strong>描述</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>名称</p></td>
<td align="left"><p>为设置位置模板指定一个唯一名称。 这用于在 WMI、PowerShell、事件查看器和调试日志中引用模板时的显示用途。 有关详细信息，请参阅 <a href="#name21" data-raw-source="[Name](#name21)"> 名称 </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ID</p></td>
<td align="left"><p>填充特定模板的唯一标识符。 此标记将成为 UE-V Agent 在运行时引用模板时使用的主要标识符。 有关详细信息，请参阅 <a href="#id21" data-raw-source="[ID](#id21)"> ID </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>描述</p></td>
<td align="left"><p>模板的可选说明。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>LocalizedNames</p></td>
<td align="left"><p>UI 中显示的可选名称，由语言区域设置本地化。</p></td>
</tr>
<tr class="even">
<td align="left"><p>LocalizedDescriptions</p></td>
<td align="left"><p>由语言区域设置本地化的可选模板说明。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>版本</p></td>
<td align="left"><p>标识用于管理更改管理跟踪的设置位置模板的版本。 有关详细信息，请参阅 <a href="#version21" data-raw-source="[Version](#version21)"> 版本 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>DeferToMSAccount</p></td>
<td align="left"><p>控制是否与 Microsoft 帐户一起启用此模板。 如果对计算机上的用户启用了 MSA 同步，则该模板将自动禁用。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>DeferToOffice365</p></td>
<td align="left"><p>与 MSA 类似，它控制此模板是否与 Office365 一起启用。 如果使用 Office 365 同步设置，此模板将自动禁用。</p></td>
</tr>
<tr class="even">
<td align="left"><p>FixedProfile （在2.1 中引入）</p></td>
<td align="left"><p>指定此模板只能与此元素中指定的配置文件关联，并且不能通过 WMI 或 PowerShell 进行更改。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>设置</p></td>
<td align="left"><p>适用于特定模板的所有设置的容器。 它包含注册表、File、SystemParameter 和 CustomAction 设置的实例。 有关详细信息，请 <strong> 参阅 </strong> 数据类型中的设置 <a href="#data21" data-raw-source="[Data types](#data21)"> </a> 。</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="settingslocationtemplate21"></a>SettingsLocationTemplate 元素

此元素定义单个应用程序或一组应用程序的设置。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>字段/类型</strong></p></td>
<td align="left"><p><strong>描述</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>名称</p></td>
<td align="left"><p>为设置位置模板指定一个唯一名称。 这用于在 WMI、PowerShell、事件查看器和调试日志中引用模板时的显示用途。 有关详细信息，请参阅 <a href="#name21" data-raw-source="[Name](#name21)"> 名称 </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ID</p></td>
<td align="left"><p>填充特定模板的唯一标识符。 此标记将成为 UE-V Agent 在运行时引用模板时使用的主要标识符。 有关详细信息，请参阅 <a href="#id21" data-raw-source="[ID](#id21)"> ID </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>描述</p></td>
<td align="left"><p>模板的可选说明。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>LocalizedNames</p></td>
<td align="left"><p>UI 中显示的可选名称，由语言区域设置本地化。</p></td>
</tr>
<tr class="even">
<td align="left"><p>LocalizedDescriptions</p></td>
<td align="left"><p>由语言区域设置本地化的可选模板说明。</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="appendix21"></a>附录： SettingsLocationTemplate

下面是显示其元素、子元素、属性和参数的 SettingsLocationTemplate 文件：

```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema id="UevSettingsLocationTemplate"
  targetNamespace="https://schemas.microsoft.com/UserExperienceVirtualization/2013A/SettingsLocationTemplate"
  elementFormDefault="qualified"
  xmlns="https://schemas.microsoft.com/UserExperienceVirtualization/2013A/SettingsLocationTemplate"
  xmlns:mstns="https://schemas.microsoft.com/UserExperienceVirtualization/2013A/SettingsLocationTemplate"
  xmlns:xs="http://www.w3.org/2001/XMLSchema">

    <xs:simpleType name="Guid">
        <xs:restriction base="xs:string">
            <xs:pattern value="\{[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{12}\}" />
        </xs:restriction>
    </xs:simpleType>

    <xs:simpleType name="FilenameString">
        <xs:restriction base="xs:string">
            <xs:pattern value="[^\\\?\*\|&lt;&gt;/:]+" />
        </xs:restriction>
    </xs:simpleType>

    <xs:simpleType name="IDString">
        <xs:restriction base="xs:string">
            <xs:pattern value="[^\\\?\*\|&lt;&gt;/:.]+" />
        </xs:restriction>
    </xs:simpleType>

    <xs:simpleType name="CompositeIDString">
        <xs:restriction base="xs:string">
            <xs:pattern value="[^\\\?\*\|&lt;&gt;/:.]+([.][^\\\?\*\|&lt;&gt;/:.]+)?" />
        </xs:restriction>
    </xs:simpleType>

    <xs:simpleType name="TemplateVersion">
        <xs:restriction base="xs:integer">
            <xs:minInclusive value="0" />
            <xs:maxInclusive value="2147483647" />
        </xs:restriction>
    </xs:simpleType>

    <xs:complexType name="Empty">
        <xs:sequence/>
    </xs:complexType>

    <xs:complexType name="LocalizedString">
        <xs:simpleContent>
            <xs:extension base="xs:string">
                <xs:attribute name="Locale" type="xs:string" use="required"/>
            </xs:extension>
        </xs:simpleContent>
    </xs:complexType>

    <xs:complexType name="LocalizedName">
        <xs:sequence>
            <xs:element name="Name" type="LocalizedString" minOccurs="1" maxOccurs="unbounded" />
        </xs:sequence>
    </xs:complexType>

    <xs:complexType name="LocalizedDescription">
        <xs:sequence>
            <xs:element name="Description" type="LocalizedString" minOccurs="1" maxOccurs="unbounded" />
        </xs:sequence>
    </xs:complexType>

    <xs:complexType name="ReplacedTemplates">
      <xs:sequence>
        <xs:element name="ID" type="CompositeIDString" minOccurs="1" maxOccurs="unbounded" />
    </xs:sequence>
    </xs:complexType>

    <xs:complexType name="Author">
        <xs:all>
            <xs:element name="Name" type="xs:string" minOccurs="1" />
            <xs:element name="Email" type="xs:string" minOccurs="0" />
        </xs:all>
    </xs:complexType>

    <xs:complexType name="Range">
        <xs:attribute name="Minimum" type="xs:integer" use="required"/>
        <xs:attribute name="Maximum" type="xs:integer" use="required"/>
    </xs:complexType>

    <xs:complexType name="ProcessVersion">
        <xs:sequence>
            <xs:element name="Major" type="Range" minOccurs="1" />
            <xs:element name="Minor" type="Range" minOccurs="0" />
            <xs:element name="Build" type="Range" minOccurs="0" />
            <xs:element name="Patch" type="Range" minOccurs="0" />
        </xs:sequence>
    </xs:complexType>

    <xs:simpleType name="Architecture">
        <xs:restriction base="xs:string">
            <xs:enumeration value="Win32"/>
            <xs:enumeration value="Win64"/>
        </xs:restriction>
    </xs:simpleType>

    <xs:complexType name="Process">
        <xs:sequence>
            <xs:element name="Filename" type="FilenameString" minOccurs="1" />
            <xs:element name="Architecture" type="Architecture" minOccurs="0" />
            <xs:element name="ProductName" type="xs:string" minOccurs="0" />
            <xs:element name="FileDescription" type="xs:string" minOccurs="0" />
            <xs:element name="ProductVersion" type="ProcessVersion" minOccurs="0" maxOccurs="unbounded"/>
            <xs:element name="FileVersion" type="ProcessVersion" minOccurs="0" maxOccurs="unbounded"/>
        </xs:sequence>
    </xs:complexType>

    <xs:complexType name="Processes">
        <xs:sequence>
            <xs:choice minOccurs="1">
                <xs:element name="Process" type="Process" />
                <xs:element name="ShellProcess" type="Empty" />
            </xs:choice>
            <xs:element name="Process" type="Process" minOccurs="0" maxOccurs="unbounded" />
        </xs:sequence>
    </xs:complexType>

    <xs:complexType name="Path">
        <xs:simpleContent>
            <xs:extension base="xs:string">
                <xs:attribute name="Recursive" type="xs:boolean" default="false"/>
                <xs:attribute name="DeleteIfNotFound" type="xs:boolean" default="false"/>
            </xs:extension>
        </xs:simpleContent>
    </xs:complexType>

    <xs:complexType name="RegistrySetting">
        <xs:sequence>
            <xs:element name="Path" type="Path" />
            <xs:element name="Name" type="xs:string" minOccurs="0" maxOccurs="unbounded" />
            <xs:element name="Exclude" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                    <xs:sequence>
                        <xs:element name="Path" type="Path" minOccurs="0" />
                        <xs:element name="Name" type="xs:string" minOccurs="0" maxOccurs="unbounded" />
                    </xs:sequence>
                </xs:complexType>
            </xs:element>
        </xs:sequence>
    </xs:complexType>

    <xs:complexType name="FileSetting">
        <xs:sequence>

            <xs:element name="Root">
                <xs:complexType>
                    <xs:choice>
                        <xs:element name="KnownFolder" type="Guid" />
                        <xs:element name="RegistryEntry" type="xs:string" />
                        <xs:element name="EnvironmentVariable" type="xs:string" />
                    </xs:choice>
                </xs:complexType>
            </xs:element>

            <xs:element name="Path" minOccurs="0" type="Path" />
            <xs:element name="FileMask" type="xs:string" minOccurs="0" maxOccurs="unbounded"/>

            <xs:element name="Exclude" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                    <xs:sequence>
                        <xs:element name="Path" type="Path" minOccurs="0" />
                        <xs:element name="FileMask" type="xs:string" minOccurs="0" maxOccurs="unbounded" />
                    </xs:sequence>
                </xs:complexType>
            </xs:element>

        </xs:sequence>
    </xs:complexType>

    <xs:simpleType name="CustomActionSetting">
        <xs:restriction base="xs:anyURI"/>
    </xs:simpleType>

    <xs:simpleType name="SystemParameterSetting">
        <xs:restriction base="xs:string">

            <!-- Accessibility parameters -->
            <xs:enumeration value="AccessTimeout"/>
            <xs:enumeration value="AudioDescription"/>
            <xs:enumeration value="ClientAreaAnimation"/>
            <xs:enumeration value="DisableOverlappedContent"/>
            <xs:enumeration value="FilterKeys"/>
            <xs:enumeration value="FocusBorderHeight"/>
            <xs:enumeration value="FocusBorderWidth"/>
            <xs:enumeration value="HighContrast"/>
            <xs:enumeration value="MessageDuration"/>
            <xs:enumeration value="MouseClickLock"/>
            <xs:enumeration value="MouseClickLockTime"/>
            <xs:enumeration value="MouseKeys"/>
            <xs:enumeration value="MouseSonar"/>
            <xs:enumeration value="MouseVanish"/>
            <xs:enumeration value="ScreenReader"/>
            <xs:enumeration value="ShowSounds"/>
            <xs:enumeration value="SoundSentry"/>
            <xs:enumeration value="StickyKeys"/>
            <xs:enumeration value="ToggleKeys"/>

            <!-- Input parameters -->
            <xs:enumeration value="Beep"/>
            <xs:enumeration value="BlockSendInputResets"/>
            <xs:enumeration value="DefaultInputLang"/>
            <xs:enumeration value="DoubleClickTime"/>
            <xs:enumeration value="DoubleClkHeight"/>
            <xs:enumeration value="DoubleClkWidth"/>
            <xs:enumeration value="KeyboardCues"/>
            <xs:enumeration value="KeyboardDelay"/>
            <xs:enumeration value="KeyboardPref"/>
            <xs:enumeration value="KeyboardSpeed"/>
            <xs:enumeration value="Mouse"/>
            <xs:enumeration value="MouseButtonSwap"/>
            <xs:enumeration value="MouseHoverHeight"/>
            <xs:enumeration value="MouseHoverTime"/>
            <xs:enumeration value="MouseHoverWidth"/>
            <xs:enumeration value="MouseSpeed"/>
            <xs:enumeration value="MouseTrails"/>
            <xs:enumeration value="SnapToDefButton"/>
            <xs:enumeration value="WheelScrollChars"/>
            <xs:enumeration value="WheelScrollLines"/>

            <!-- Desktop parameters (limited subset) -->
            <xs:enumeration value="DeskWallpaper"/>
            <xs:enumeration value="DesktopColor"/>

        </xs:restriction>
    </xs:simpleType>

    <xs:complexType name="Settings">
        <xs:sequence>
            <xs:element name="Asynchronous" type="xs:boolean" minOccurs="0" />
            <xs:element name="PreventOverlappingSynchronization" type="xs:boolean" minOccurs="0" />
            <xs:element name="AlwaysApplySettings" type="xs:boolean" minOccurs="0" />
            <xs:choice minOccurs="0" maxOccurs="unbounded">
                <xs:element name="Registry" type="RegistrySetting" />
                <xs:element name="File" type="FileSetting" />
                <xs:element name="SystemParameter" type="SystemParameterSetting" />
                <xs:element name="CustomAction" type="CustomActionSetting" />
            </xs:choice>
        </xs:sequence>
    </xs:complexType>

    <xs:complexType name="Common">
        <xs:sequence>
            <xs:element name="Name" type="xs:string" />
            <xs:element name="ID" type="IDString" />
            <xs:element name="ReplacedTemplates" type="ReplacedTemplates" minOccurs="0" />
            <xs:element name="Description" type="xs:string" minOccurs="0" />
            <xs:element name="LocalizedNames" type="LocalizedName" minOccurs="0" />
            <xs:element name="LocalizedDescriptions" type="LocalizedDescription" minOccurs="0" />
            <xs:element name="Version" type="xs:integer" />
            <xs:element name="DeferToMSAccount" type="Empty"  minOccurs="0" />
            <xs:element name="DeferToOffice365" type="Empty" minOccurs="0" />
            <xs:element name="Settings" type="Settings" />
        </xs:sequence>
    </xs:complexType>

    <xs:complexType name="Application">
        <xs:sequence>
            <xs:element name="Name" type="xs:string" />
            <xs:element name="ID" type="IDString" />
            <xs:element name="ReplacedTemplates" type="ReplacedTemplates" minOccurs="0" />
            <xs:element name="Description" type="xs:string" minOccurs="0" />
            <xs:element name="LocalizedNames" type="LocalizedName" minOccurs="0" />
            <xs:element name="LocalizedDescriptions" type="LocalizedDescription" minOccurs="0" />
            <xs:element name="Version" type="xs:integer" />
            <xs:element name="DeferToMSAccount" type="Empty"  minOccurs="0" />
            <xs:element name="DeferToOffice365" type="Empty" minOccurs="0" />
            <xs:element name="Processes" type="Processes" />
            <xs:element name="Settings" type="Settings" />
        </xs:sequence>
    </xs:complexType>


    <xs:element name="SettingsLocationTemplate">
        <xs:complexType>
            <xs:sequence>

                <xs:element name="Name" type="xs:string" />
                <xs:element name="ID" type="IDString" />
                <xs:element name="Description" type="xs:string" minOccurs="0" />
                <xs:element name="LocalizedNames" type="LocalizedName" minOccurs="0" />
                <xs:element name="LocalizedDescriptions" type="LocalizedDescription" minOccurs="0" />

                <xs:choice>

                    <!-- Single application -->
                    <xs:sequence>
                        <xs:element name="ReplacedTemplates" type="ReplacedTemplates" minOccurs="0" />
                        <xs:element name="Version" type="TemplateVersion" />
                        <xs:element name="Author" type="Author" minOccurs="0" />
                        <xs:element name="FixedProfile" type="xs:string"  minOccurs="0" />
                        <xs:element name="DeferToMSAccount" type="Empty"  minOccurs="0" />
                        <xs:element name="DeferToOffice365" type="Empty" minOccurs="0" />
                        <xs:element name="Processes" type="Processes" />
                        <xs:element name="Settings" type="Settings" />
                    </xs:sequence>

                    <!-- Suite of applications -->
                    <xs:sequence>
                        <xs:element name="ManageSuiteOnly" type="xs:boolean" minOccurs="0" />
                        <xs:element name="Author" type="Author" minOccurs="0" />
                        <xs:element name="FixedProfile" type="xs:string"  minOccurs="0" />
                        <xs:element name="Common" type="Common" />
                        <xs:element name="Application" type="Application" minOccurs="2" maxOccurs="unbounded" />
                    </xs:sequence>

                </xs:choice>

            </xs:sequence>
        </xs:complexType>
    </xs:element>
    <!-- SettingsLocationTemplate -->

</xs:schema>
```

## UE-V 2.0 应用程序模板架构参考


本节详细介绍了 UE-V 2.0 设置位置模板的 XML 结构，并提供了编辑此文件的指南。

### 本部分内容

-   [XML 声明和编码属性](#xml)

-   [命名空间和根元素](#namespace)

-   [数据类型](#data)

-   [名称元素](#name)

-   [ID 元素](#id)

-   [版本元素](#version)

-   [作者元素](#author)

-   [进程和进程元素](#processes)

-   [应用程序元素](#application)

-   [常见元素](#common)

-   [SettingsLocationTemplate 元素](#settingslocationtemplate)

-   [附录： SettingsLocationTemplate](#appendix)

### <a href="" id="xml"></a>XML 声明和编码属性

**强制： True**

**类型： String**

XML 声明必须指定 XML 版本1.0 属性（ &lt; ？ xml version = "1.0" &gt; ）。 由 UE-V 生成器创建的设置位置模板将保存为 UTF-8 编码，尽管编码没有明确指定。 我们建议你在此元素中将 encoding = "UTF-8" 属性作为最佳做法包括在内。 本产品附带的所有模板也都指定了此标记（请参阅%ProgramFiles%\\Microsoft 用户体验 Virtualization\\Templates 中的文档以了解参考）。 例如：

`<?xml version="1.0" encoding="UTF-8"?>`

### <a href="" id="namespace"></a>命名空间和根元素

**强制： True**

**类型： String**

UE-V 使用 https://schemas.microsoft.com/UserExperienceVirtualization/2012/SettingsLocationTemplate 所有应用程序的命名空间。 SettingsLocationTemplate 是根元素，包含所有其他元素。 使用此标记的所有模板中的引用 SettingsLocationTemplate：

`<SettingsLocationTemplate xmlns='https://schemas.microsoft.com/UserExperienceVirtualization/2012/SettingsLocationTemplate'>`

### <a href="" id="data"></a>数据类型

以下是 UE-V 应用程序模板架构的数据类型。

<a href="" id="guid"></a>**GUID**GUID 描述一个标准的全局唯一标识符正则表达式，格式为 "\\ {\ [a-F0 \] {8} -\ [a – fa-F0-9 \] {4} [a-Fa-F0 \] {4} -\ [a – F0-9 \] \ [a-- {4} F0-9 \] {12} \}"。 在 Filesetting\\Root\\KnownFolder 元素中使用此功能来验证已知文件夹的格式。

<a href="" id="filenamestring"></a>**FilenameString**FilenameString 是指要监视的进程的文件名。 它的值受 regex \ [^ \ \ \ \ * &lt; &gt; \？/： \] +，（也就是说，它们不能包含反斜杠字符、星号或问号通配符、管道字符、大于或小于符号、正斜杠或冒号字符）。

<a href="" id="idstring"></a>**IDString**IDString 是指应用程序元素、SettingsLocationTemplate 和常见元素（用于描述共享通用设置的应用程序套件）的 ID 值。 它受与 FilenameString 相同的正则表达式的限制（\ [^ \ \ \ \ * \ \ * &lt; &gt; \/:\]+).

<a href="" id="templateversion"></a>**TemplateVersion**TemplateVersion 是用于描述设置位置模板的版本的整数值。 其值的范围可以从0到2147483647。

<a href="" id="empty"></a>**空**空表示空值。 此功能在 Process\\ShellProcess 中用于指示没有要监视的进程。 此值不应在任何应用程序模板中使用。

<a href="" id="author"></a>**作者**"作者" 数据类型是标识模板作者的复杂类型。 它包含两个子元素：**名称**和**电子邮件**。 在 "作者" 数据类型中，Name 元素是必需的，而 Email 元素是可选的。 此类型将在 SettingsLocationTemplate 元素下更详细地进行介绍。

<a href="" id="range"></a>**区域**Range 定义一个包含两个子元素的整数类：**最小值**和**最大值**。 此数据类型在 ProcessVersion 数据类型中实现。 如果已指定，则必须同时包含最小值和最大值。

<a href="" id="processversion"></a>**ProcessVersion**ProcessVersion 定义了一个包含四个子元素的类型：**主要**、**次要**、**内部版本**和**修补程序**。 Process 元素使用此数据类型填充其 ProductVersion 和 FileVersion 值。 此类型的数据是一个范围值。 主要子元素是必需的，而其他元素是可选的。

<a href="" id="architecture"></a>**体系结构**体系结构枚举两个可能的值： **Win32**和**Win64**。 这些值用于指定进程体系结构。

<a href="" id="process"></a>**处理**"流程" 数据类型是用于描述由 UE-V 监视的流程的容器。 它包含六个子元素： **Filename**、**体系结构**、 **ProductName**、 **FileDescription**、 **ProductVersion**和**FileVersion**。 下表详细介绍了每个元素各自的数据类型：

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">元素</th>
<th align="left">数据类型</th>
<th align="left">Mandatory</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>相配</p></td>
<td align="left"><p>FilenameString</p></td>
<td align="left"><p>True</p></td>
</tr>
<tr class="even">
<td align="left"><p>体系结构</p></td>
<td align="left"><p>体系结构</p></td>
<td align="left"><p>False</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ProductName</p></td>
<td align="left"><p>字符串</p></td>
<td align="left"><p>False</p></td>
</tr>
<tr class="even">
<td align="left"><p>FileDescription</p></td>
<td align="left"><p>字符串</p></td>
<td align="left"><p>False</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ProductVersion</p></td>
<td align="left"><p>ProcessVersion</p></td>
<td align="left"><p>False</p></td>
</tr>
<tr class="even">
<td align="left"><p>FileVersion</p></td>
<td align="left"><p>ProcessVersion</p></td>
<td align="left"><p>False</p></td>
</tr>
</tbody>
</table>

 

<a href="" id="processes"></a>**流程**"流程" 数据类型表示一个容器，用于一个或多个流程元素的集合。 进程序列类型中支持两个子元素： **Process**和**ShellProcess**。 Process 是 Process 类型的元素，ShellProcess 的数据类型为 Empty。 序列中必须至少标识一个项目。

<a href="" id="path"></a>**路径**RegistrySetting 和 FileSetting 使用 Path 来引用注册表和文件路径。 此元素支持两个可选属性： **Recursive**和**DeleteIfNotFound**。 两个值均设置为默认值 = "False"。

递归表示文件设置包含路径和所有子文件夹，或者注册表设置包含所有子注册表项。 在这两种情况下，当前级别的所有项目都包含在捕获的数据中。 对于 FileSettings 对象，指定文件夹中的所有文件都包含在由 UE-V 捕获的数据中，但不包括文件夹。 对于注册表路径，将捕获当前路径中的所有值，但不捕获子注册表项。 在这两种情况下，应注意避免捕获大型数据集或大量项目。

DeleteIfNotFound 属性从用户的设置存储路径数据中删除设置。 在从包中删除这些设置将在设置存储路径文件服务器上保存大量磁盘空间时，这可能是理想的情况。

<a href="" id="filemask"></a>**FileMask**FileMask 仅指定由 Path 定义的文件夹的某些文件类型。 例如，Path 可能是 `C:\users\username\files` 且 FileMask 可以 `*.txt` 仅包含文本文件。

<a href="" id="registrysetting"></a>**RegistrySetting**RegistrySetting 表示注册表项和值的容器，以及 UE-V Agent 部分相关联的所需行为。 在此类型中定义了四个子元素：**路径**、**名称**、**排除**和值**路径**和**名称**的序列。

<a href="" id="filesetting"></a>**FileSetting**FileSetting 包含与文件和文件路径相关联的参数。 定义了四个子元素： **Root**、 **Path**、 **FileMask**和**Exclude**。 根是强制性的，而其他是可选的。

<a href="" id="settings"></a>**设置**"设置" 是适用于特定模板的所有设置的容器。 它包含前面所述的注册表、文件、SystemParameter 和 CustomAction 设置的实例。 此外，它还可以包含包含以下行为的以下子元素：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">元素</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>异步</p></td>
<td align="left"><p>在不阻止应用程序启动的情况下应用异步设置程序包，以便应用程序在设置仍在应用时启动。 这对于可以异步应用的设置（例如 <code>get/set</code> ，通过 API （如 SystemParameterSetting）很有用。</p></td>
</tr>
<tr class="even">
<td align="left"><p>PreventOverlappingSynchronization</p></td>
<td align="left"><p>默认情况下，当使用模板的最后一个应用程序实例关闭时，UE-V 仅保存应用程序的设置。 当此元素设置为 "false" 时，UE-V 将导出设置，即使应用程序的其他实例正在运行。 适用的模板（包括常见元素部分的模板）使用此标志可使共享设置始终在应用程序关闭时导出，同时防止应用程序特定的设置在最后一个实例关闭之前导出。</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="name"></a>名称元素

**强制： True**

**类型： String**

名称指定设置位置模板的唯一名称。 这用于在 WMI、PowerShell、事件查看器和调试日志中引用模板时的显示用途。 通常，请避免引用版本信息，因为这可以从 ProductVersion 元素中 objected。 例如，指定 " `<Name>My Application</Name>` 而不是" `<Name>My Application 1.1</Name>` 。

**注意** UE-V 不引用外部 Dtd，因此不能使用设置位置模板中的命名实体。 例如，不要使用 &reg; 来指注册的商标签名®。 而是使用规范编号引用包括这些类型的特殊字符，例如 &®字符的 \ #174。 此规则适用于此文档中的所有字符串值。

<http://www.w3.org/TR/xhtml1/dtds.html>有关字符实体的完整列表，请参阅。 UTF-8 编码的文档可能直接包含 Unicode 字符。 通过 UE-V 生成器保存模板将自动将字符实体转换为其 Unicode 表示形式。

 

### <a href="" id="id"></a>ID 元素

**强制： True**

**类型： String**

ID 填充特定模板的唯一标识符。 此标记将成为 UE-V Agent 在运行时引用模板时使用的主标识符（例如，请参阅 UevTemplate 和 UevTemplateProgram PowerShell cmdlet 的输出）。 按照约定，此标记不应包含任何空格，从而简化了脚本编写。 应在此元素中指定应用程序的版本号，以便更轻松地标识模板，例如 `<ID>MicrosoftCalculator6</ID>` 或 `<ID>MicrosoftOffice2010Win64</ID>` 。

### <a href="" id="version"></a>版本元素

**强制： True**

**类型： Integer**

**最小值：0**

**最大值：2147483647**

版本标识用于管理更改管理跟踪的设置位置模板的版本。 每次保存模板时，UE-V 生成器都会自动将该数字递增1。 请注意，此字段必须为整数整数;不允许使用小数值，例如 `<Version>2.5</Version>` 。

**提示：** 你可以使用 XML 注释标记保存有关版本更改 `<!-- -->` 的注释，例如：

```xml
<!--
    Version History

    Version 1 Jul 05, 2012 Initial template created by Generator - Denise@Contoso.com
    Version 2 Jul 31, 2012 Added support for app.exe v2.1.3 - Mark@Contoso.com
    Version 3 Jan 01, 2013 Added font settings support - Mark@Contoso.com
    Version 4 Jan 31, 2013 Added support for plugin settings - Tony@Contoso.com
  -->
<Version>4</Version>
```

**重要提示** 将查询此值，以确定是否应将模板的新版本应用于这些实例中的现有模板：

-   执行计划模板自动更新任务时

-   当执行 UevTemplate PowerShell cmdlet 时

-   当 microsoft\\uev： SettingsLocationTemplate Update 方法通过 WMI 调用时

 

### <a href="" id="author"></a>作者元素

**强制： False**

**类型： String**

作者标识设置位置模板的创建者。 支持两个可选子元素：**名称**和**电子邮件**。 这两个属性都是可选的，但如果指定了电子邮件子元素，则它必须附有 Name 元素。 作者指的是 "设置位置" 模板的联系人的全名，电子邮件应该指作者的电子邮件地址。 建议在公共发布的模板中包括此信息，例如，在[Ue-v 模板库](https://gallery.technet.microsoft.com/site/search?f%5B0%5D.Type=RootCategory&f%5B0%5D.Value=UE-V)中。

### <a href="" id="processes"></a>进程和进程元素

**强制： True**

**类型：元素**

进程至少包含一个 `<Process>` 元素，该元素又包含以下子元素： **Filename**、**体系结构**、 **ProductName**、 **FileDescription**、 **ProductVersion**和**FileVersion**。 Filename 子元素是必需的，而其他元素是可选的。 完全填充的元素包含与以下示例类似的标记：

```xml
<Process>
  <Filename>MyApplication.exe</Filename>
  <Architecture>Win64</Architecture>
  <ProductName> MyApplication </ProductName>
  <FileDescription>MyApplication.exe</FileDescription>
  <ProductVersion>
    <Major Minimum="2" Maximum="2" />
    <Minor Minimum="0" Maximum="0" />
    <Build Minimum="0" Maximum="0" />
    <Patch Minimum="5" Maximum="5" />
  </ProductVersion>
  <FileVersion>
    <Major Minimum="2" Maximum="2" />
    <Minor Minimum="0" Maximum="0" />
    <Build Minimum="0" Maximum="0" />
    <Patch Minimum="5" Maximum="5" />
  </FileVersion>
</Process>
```

### 相配

**强制： True**

**类型： String**

文件名是指在文件系统中显示的可执行文件的实际文件名。 此元素指定 UE-V 用于评估模板是否适用于进程的主要条件。 此元素必须在设置位置模板 XML 中指定。

有效的文件名必须与正则表达式 \ [^ \ &lt; &gt; \ \ \ \/： \] + 时，它们不能包含反斜杠字符、星号或问号通配符、管道字符、大于或小于符号、正斜杠或冒号（\\？） \* |&lt; &gt; /或：个字符。）

**提示：** 若要针对此 regex 测试字符串，请使用 PowerShell 命令窗口并将可执行文件的名称替换为**YourFileName**：

`"YourFileName.exe" -match  "[\\\?\*\|<>/:]+"`

**True**值表示字符串包含非法字符。 下面是一些非法值的示例：

-   \\\\server\\share\\program.exe

-   程序 \ * .exe

-   Pro？ ram.exe

-   程序 &lt; 1 &gt; .exe

**注意** UE-V 生成器分别对大于和小于字符进行编码 &gt; &lt; 。

 

在极少数情况下，文件名值不一定包含 .exe 扩展名，但应将其指定为值的一部分。 例如， `<Filename>MyApplictication.exe</Filename>` 应指定而不是 `<Filename>MyApplictication</Filename>` 。 如果可执行文件的实际名称为 "MyApplication.exe"，则第二个示例不会将模板应用于该进程。

### 体系结构

**强制： False**

**类型：体系结构（字符串）**

体系结构是指已编译目标可执行文件的处理器体系结构。 有效值为32位应用程序的 Win32 或64位应用程序的 Win64。 如果存在，此标记将设置位置模板的适用性限制为特定的应用程序体系结构。 有关此操作的示例，请比较%ProgramFiles%\\Microsoft 用户体验 Virtualization\\templates\\ MicrosoftOffice2010Win32.xml 和 UE-V 附带的 MicrosoftOffice2010Win64.xml 文件。 如果相对路径在不同版本的可执行文件之间更改，或者在从一个处理器体系结构移动到另一个时已添加或删除了设置，此方法将非常有用。

如果此元素不存在，则设置位置模板将忽略进程的体系结构，并将其应用于32和64位进程（如果应用了文件名和其他属性）。

**注意** UE-V 不支持此版本中的 ARM 处理器。

 

### ProductName

**强制： False**

**类型： String**

ProductName 是一个可选元素，用于标识用于管理用途或报告的产品。 ProductName 与 Filename 的不同之处在于它的值没有正则表达式限制。 这允许更容易理解的可执行文件名称可能不明显的进程的说明。 例如：

```xml
<Process>
  <Filename>MyApplication.exe</Filename>
  <ProductName>My Application 6.x by Contoso.com</ProductName>
  <ProductVersion>
    <Major Minimum="6" Maximum="6" />
  </ProductVersion>
</Process>
```

### FileDescription

**强制： False**

**类型： String**

FileDescription 是一个可选标记，可提供可执行文件的管理说明。 这是一个免费的文本字段，在需要标识可执行文件的功能的软件包中的多个可执行文件中非常有用。

例如，在一个合适的应用程序中，提供有关两个可执行文件（MyApplication.exe 和 MyApplicationHelper.exe）的功能的提醒可能很有用，如下所示：

```xml
<Processes>
  <Process>
    <Filename>MyApplication.exe</Filename>
    <FileDescription>My Application Main Engine</ FileDescription>
    <ProductVersion>
      <Major Minimum="6" Maximum="6" />
    </ProductVersion>
  </Process>
  <Process>
    <Filename>MyApplicationHelper.exe</Filename>
    <FileDescription>My Application Background Process Executable</FileDescription>
    <ProductVersion>
      <Major Minimum="6" Maximum="6" />
    </ProductVersion>
  </Process>
</Processes>
```

### ProductVersion

**强制： False**

**类型： String**

ProductVersion 是指文件的主要和次要产品版本以及版本和修补程序级别。 ProductVersion 是一个可选元素，但如果指定，它必须至少包含主要子元素。 此值必须以最小为 = "X" 的最大值 = "Y" 表示区域，其中 X 和 Y 是整数。 最小值和最大值可以相同。

产品和文件版本元素可以保留未指定。 这样做会使模板 "版本不限"，这意味着模板将应用于指定的可执行文件的所有版本。

**示例 1：**

UE-V 生成器中指定的产品版本：1.0 生成以下 XML：

```xml
<ProductVersion>
  <Major Minimum="1" Maximum="1" />
  <Minor Minimum="0" Maximum="0" />
</ProductVersion>
```

**示例 2：**

文件版本： UE-V 生成器中指定的5.0.2.1000 生成以下 XML：

```xml
<FileVersion>
  <Major Minimum="5" Maximum="5" />
  <Minor Minimum="0" Maximum="0" />
  <Build Minimum="2" Maximum="2" />
  <Patch Minimum="1000" Maximum="1000" />
</FileVersion>
```

**不正确的示例 1-未完成的范围：**

仅存在最小属性。 范围中还必须包含 "最大"。

```xml
<ProductVersion>
  <Major Minimum="2" />
</ProductVersion>
```

**不正确的示例 2-指定的次要元素没有主要元素：**

仅存在次要元素。 还必须包含主版本。

```xml
<ProductVersion>
  <Minor Minimum="0" Maximum="0" />
</ProductVersion>
```

### FileVersion

**强制： False**

**类型： String**

FileVersion 将区分已发布应用程序的发布版本和组件可执行文件的内部生成详细信息。 对于大多数商业应用程序，这些号码是相同的。 它们的不同之处是，文件的产品版本指示文件的常规版本标识，而文件版本指示文件的特定版本（如修补程序或更新）。 这将在不中断检测逻辑的情况下唯一标识文件。

若要确定特定可执行文件的产品版本和文件版本，请在 Windows 资源管理器中右键单击该文件，选择 "属性"，然后单击 "详细信息" 选项卡。

为应用程序包括 FileVersion 元素可实现更精细的微调检测逻辑，但对于大多数应用程序都不是必需的。 首先检查 ProductVersion 元素设置，然后选中 "FileVersion"。 将应用更严格的设置。

FileVersion 的子元素和语法规则与 ProductVersion 的子元素和语法规则相同。

```xml
<Process>
  <Filename>MSACCESS.EXE</Filename>
  <Architecture>Win32</Architecture>
  <ProductVersion>
    <Major Minimum="14" Maximum="14" />
    <Minor Minimum="0" Maximum="0" />
  </ProductVersion>
  <FileVersion>
    <Major Minimum="14" Maximum="14" />
    <Minor Minimum="0" Maximum="0" />
  </FileVersion>
</Process>
```

### <a href="" id="application"></a>应用程序元素

应用程序是应用于特定应用程序的设置的容器。 它是以下字段/类型的集合。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">字段/类型</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>名称</p></td>
<td align="left"><p>为设置位置模板指定一个唯一名称。 这用于在 WMI、PowerShell、事件查看器和调试日志中引用模板时的显示用途。 有关详细信息，请参阅 <a href="#name" data-raw-source="[Name](#name)"> 名称 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ID</p></td>
<td align="left"><p>填充特定模板的唯一标识符。 此标记将成为 UE-V Agent 在运行时引用模板时使用的主要标识符。 有关详细信息，请参阅 <a href="#id" data-raw-source="[ID](#id)"> ID </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>描述</p></td>
<td align="left"><p>模板的可选说明。</p></td>
</tr>
<tr class="even">
<td align="left"><p>LocalizedNames</p></td>
<td align="left"><p>UI 中显示的可选名称，由语言区域设置本地化。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>LocalizedDescriptions</p></td>
<td align="left"><p>由语言区域设置本地化的可选模板说明。</p></td>
</tr>
<tr class="even">
<td align="left"><p>版本</p></td>
<td align="left"><p>标识用于管理更改管理跟踪的设置位置模板的版本。 有关详细信息，请参阅 <a href="#version" data-raw-source="[Version](#version)"> 版本 </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>DeferToMSAccount</p></td>
<td align="left"><p>控制是否与 Microsoft 帐户一起启用此模板。 如果对计算机上的用户启用了 MSA 同步，则该模板将自动禁用。</p></td>
</tr>
<tr class="even">
<td align="left"><p>DeferToOffice365</p></td>
<td align="left"><p>与 MSA 类似，它控制此模板是否与 Office365 一起启用。 如果使用 Office 365 同步设置，此模板将自动禁用。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>进程</p></td>
<td align="left"><p>一个容器，用于一个或多个流程元素的集合。 有关详细信息，请参阅 <a href="#processes" data-raw-source="[Processes](#processes)"> 流程 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>设置</p></td>
<td align="left"><p>适用于特定模板的所有设置的容器。 它包含注册表、File、SystemParameter 和 CustomAction 设置的实例。 有关详细信息，请 <strong> 参阅 </strong> 数据类型中的设置 <a href="#data" data-raw-source="[Data types](#data)"> </a> 。</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="common"></a>常见元素

常用于应用程序元素，但它始终与两个或更多个应用程序元素关联。 "常见" 部分表示在这些应用程序实例之间共享的一组设置。 它是以下字段/类型的集合。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">字段/类型</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>名称</p></td>
<td align="left"><p>为设置位置模板指定一个唯一名称。 这用于在 WMI、PowerShell、事件查看器和调试日志中引用模板时的显示用途。 有关详细信息，请参阅 <a href="#name" data-raw-source="[Name](#name)"> 名称 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ID</p></td>
<td align="left"><p>填充特定模板的唯一标识符。 此标记将成为 UE-V Agent 在运行时引用模板时使用的主要标识符。 有关详细信息，请参阅 <a href="#id" data-raw-source="[ID](#id)"> ID </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>描述</p></td>
<td align="left"><p>模板的可选说明。</p></td>
</tr>
<tr class="even">
<td align="left"><p>LocalizedNames</p></td>
<td align="left"><p>UI 中显示的可选名称，由语言区域设置本地化。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>LocalizedDescriptions</p></td>
<td align="left"><p>由语言区域设置本地化的可选模板说明。</p></td>
</tr>
<tr class="even">
<td align="left"><p>版本</p></td>
<td align="left"><p>标识用于管理更改管理跟踪的设置位置模板的版本。 有关详细信息，请参阅 <a href="#version" data-raw-source="[Version](#version)"> 版本 </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>DeferToMSAccount</p></td>
<td align="left"><p>控制是否与 Microsoft 帐户一起启用此模板。 如果对计算机上的用户启用了 MSA 同步，则该模板将自动禁用。</p></td>
</tr>
<tr class="even">
<td align="left"><p>DeferToOffice365</p></td>
<td align="left"><p>与 MSA 类似，它控制此模板是否与 Office365 一起启用。 如果使用 Office 365 同步设置，此模板将自动禁用。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>设置</p></td>
<td align="left"><p>适用于特定模板的所有设置的容器。 它包含注册表、File、SystemParameter 和 CustomAction 设置的实例。 有关详细信息，请 <strong> 参阅 </strong> 数据类型中的设置 <a href="#data" data-raw-source="[Data types](#data)"> </a> 。</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="settingslocationtemplate"></a>SettingsLocationTemplate 元素

此元素定义单个应用程序或一组应用程序的设置。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">字段/类型</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>名称</p></td>
<td align="left"><p>为设置位置模板指定一个唯一名称。 这用于在 WMI、PowerShell、事件查看器和调试日志中引用模板时的显示用途。 有关详细信息，请参阅 <a href="#name" data-raw-source="[Name](#name)"> 名称 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ID</p></td>
<td align="left"><p>填充特定模板的唯一标识符。 此标记将成为 UE-V Agent 在运行时引用模板时使用的主要标识符。 有关详细信息，请参阅 <a href="#id" data-raw-source="[ID](#id)"> ID </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>描述</p></td>
<td align="left"><p>模板的可选说明。</p></td>
</tr>
<tr class="even">
<td align="left"><p>LocalizedNames</p></td>
<td align="left"><p>UI 中显示的可选名称，由语言区域设置本地化。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>LocalizedDescriptions</p></td>
<td align="left"><p>由语言区域设置本地化的可选模板说明。</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="appendix"></a>附录： SettingsLocationTemplate

下面是显示其元素、子元素、属性和参数的 SettingsLocationTemplate 文件：

```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema id="UevSettingsLocationTemplate"
  targetNamespace="https://schemas.microsoft.com/UserExperienceVirtualization/2013/SettingsLocationTemplate"
  elementFormDefault="qualified"
  xmlns="https://schemas.microsoft.com/UserExperienceVirtualization/2013/SettingsLocationTemplate"
  xmlns:mstns="https://schemas.microsoft.com/UserExperienceVirtualization/2013/SettingsLocationTemplate"
  xmlns:xs="http://www.w3.org/2001/XMLSchema">

  <xs:simpleType name="Guid">
    <xs:restriction base="xs:string">
      <xs:pattern value="\{[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{12}\}" />
    </xs:restriction>
  </xs:simpleType>

  <xs:simpleType name="FilenameString">
    <xs:restriction base="xs:string">
      <xs:pattern value="[^\\\?\*\|&lt;&gt;/:]+" />
    </xs:restriction>
  </xs:simpleType>

  <xs:simpleType name="IDString">
    <xs:restriction base="xs:string">
      <xs:pattern value="[^\\\?\*\|&lt;&gt;/:.]+" />
    </xs:restriction>
  </xs:simpleType>

  <xs:simpleType name="TemplateVersion">
    <xs:restriction base="xs:integer">
      <xs:minInclusive value="0" />
      <xs:maxInclusive value="2147483647" />
    </xs:restriction>
  </xs:simpleType>

  <xs:complexType name="Empty">
    <xs:sequence/>
  </xs:complexType>

  <xs:complexType name="LocalizedString">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="Locale" type="xs:string" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>

  <xs:complexType name="LocalizedName">
    <xs:sequence>
      <xs:element name="Name" type="LocalizedString" minOccurs="1" maxOccurs="unbounded" />
    </xs:sequence>
  </xs:complexType>

  <xs:complexType name="LocalizedDescription">
    <xs:sequence>
      <xs:element name="Description" type="LocalizedString" minOccurs="1" maxOccurs="unbounded" />
    </xs:sequence>
  </xs:complexType>

  <xs:complexType name="Author">
    <xs:all>
      <xs:element name="Name" type="xs:string" minOccurs="1" />
      <xs:element name="Email" type="xs:string" minOccurs="0" />
    </xs:all>
  </xs:complexType>

  <xs:complexType name="Range">
    <xs:attribute name="Minimum" type="xs:integer" use="required"/>
    <xs:attribute name="Maximum" type="xs:integer" use="required"/>
  </xs:complexType>

  <xs:complexType name="ProcessVersion">
    <xs:sequence>
      <xs:element name="Major" type="Range" minOccurs="1" />
      <xs:element name="Minor" type="Range" minOccurs="0" />
      <xs:element name="Build" type="Range" minOccurs="0" />
      <xs:element name="Patch" type="Range" minOccurs="0" />
    </xs:sequence>
  </xs:complexType>

  <xs:simpleType name="Architecture">
    <xs:restriction base="xs:string">
      <xs:enumeration value="Win32"/>
      <xs:enumeration value="Win64"/>
    </xs:restriction>
  </xs:simpleType>

  <xs:complexType name="Process">
    <xs:sequence>
      <xs:element name="Filename" type="FilenameString" minOccurs="1" />
      <xs:element name="Architecture" type="Architecture" minOccurs="0" />
      <xs:element name="ProductName" type="xs:string" minOccurs="0" />
      <xs:element name="FileDescription" type="xs:string" minOccurs="0" />
      <xs:element name="ProductVersion" type="ProcessVersion" minOccurs="0" maxOccurs="unbounded"/>
      <xs:element name="FileVersion" type="ProcessVersion" minOccurs="0" maxOccurs="unbounded"/>
    </xs:sequence>
  </xs:complexType>

  <xs:complexType name="Processes">
    <xs:sequence>
      <xs:choice minOccurs="1">
        <xs:element name="Process" type="Process" />
        <xs:element name="ShellProcess" type="Empty" />
      </xs:choice>
      <xs:element name="Process" type="Process" minOccurs="0" maxOccurs="unbounded" />
    </xs:sequence>
  </xs:complexType>

  <xs:complexType name="Path">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="Recursive" type="xs:boolean" default="false"/>
        <xs:attribute name="DeleteIfNotFound" type="xs:boolean" default="false"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>

  <xs:complexType name="RegistrySetting">
    <xs:sequence>
      <xs:element name="Path" type="Path" />
      <xs:element name="Name" type="xs:string" minOccurs="0" maxOccurs="unbounded" />
      <xs:element name="Exclude" minOccurs="0" maxOccurs="unbounded">
        <xs:complexType>
          <xs:sequence>
            <xs:element name="Path" type="Path" minOccurs="0" />
            <xs:element name="Name" type="xs:string" minOccurs="0" maxOccurs="unbounded" />
          </xs:sequence>
        </xs:complexType>
      </xs:element>
    </xs:sequence>
  </xs:complexType>

  <xs:complexType name="FileSetting">
    <xs:sequence>

      <xs:element name="Root">
        <xs:complexType>
          <xs:choice>
            <xs:element name="KnownFolder" type="Guid" />
            <xs:element name="RegistryEntry" type="xs:string" />
            <xs:element name="EnvironmentVariable" type="xs:string" />
          </xs:choice>
        </xs:complexType>
      </xs:element>

      <xs:element name="Path" minOccurs="0" type="Path" />
      <xs:element name="FileMask" type="xs:string" minOccurs="0" maxOccurs="unbounded"/>

      <xs:element name="Exclude" minOccurs="0" maxOccurs="unbounded">
        <xs:complexType>
          <xs:sequence>
            <xs:element name="Path" type="Path" minOccurs="0" />
            <xs:element name="FileMask" type="xs:string" minOccurs="0" maxOccurs="unbounded" />
          </xs:sequence>
        </xs:complexType>
      </xs:element>

    </xs:sequence>
  </xs:complexType>

  <xs:simpleType name="SystemParameterSetting">
    <xs:restriction base="xs:string">

      <!-- Accessibility parameters -->
      <xs:enumeration value="AccessTimeout"/>
      <xs:enumeration value="AudioDescription"/>
      <xs:enumeration value="ClientAreaAnimation"/>
      <xs:enumeration value="DisableOverlappedContent"/>
      <xs:enumeration value="FilterKeys"/>
      <xs:enumeration value="FocusBorderHeight"/>
      <xs:enumeration value="FocusBorderWidth"/>
      <xs:enumeration value="HighContrast"/>
      <xs:enumeration value="MessageDuration"/>
      <xs:enumeration value="MouseClickLock"/>
      <xs:enumeration value="MouseClickLockTime"/>
      <xs:enumeration value="MouseKeys"/>
      <xs:enumeration value="MouseSonar"/>
      <xs:enumeration value="MouseVanish"/>
      <xs:enumeration value="ScreenReader"/>
      <xs:enumeration value="ShowSounds"/>
      <xs:enumeration value="SoundSentry"/>
      <xs:enumeration value="StickyKeys"/>
      <xs:enumeration value="ToggleKeys"/>

      <!-- Input parameters -->
      <xs:enumeration value="Beep"/>
      <xs:enumeration value="BlockSendInputResets"/>
      <xs:enumeration value="DefaultInputLang"/>
      <xs:enumeration value="DoubleClickTime"/>
      <xs:enumeration value="DoubleClkHeight"/>
      <xs:enumeration value="DoubleClkWidth"/>
      <xs:enumeration value="KeyboardCues"/>
      <xs:enumeration value="KeyboardDelay"/>
      <xs:enumeration value="KeyboardPref"/>
      <xs:enumeration value="KeyboardSpeed"/>
      <xs:enumeration value="Mouse"/>
      <xs:enumeration value="MouseButtonSwap"/>
      <xs:enumeration value="MouseHoverHeight"/>
      <xs:enumeration value="MouseHoverTime"/>
      <xs:enumeration value="MouseHoverWidth"/>
      <xs:enumeration value="MouseSpeed"/>
      <xs:enumeration value="MouseTrails"/>
      <xs:enumeration value="SnapToDefButton"/>
      <xs:enumeration value="WheelScrollChars"/>
      <xs:enumeration value="WheelScrollLines"/>

      <!-- Desktop parameters (limited subset) -->
      <xs:enumeration value="DeskWallpaper"/>
      <xs:enumeration value="DesktopColor"/>

    </xs:restriction>
  </xs:simpleType>

  <xs:complexType name="Settings">
    <xs:sequence>
      <xs:element name="Asynchronous" type="xs:boolean" minOccurs="0" />
      <xs:element name="PreventOverlappingSynchronization" type="xs:boolean" minOccurs="0" />
      <xs:choice minOccurs="0" maxOccurs="unbounded">
        <xs:element name="Registry" type="RegistrySetting" />
        <xs:element name="File" type="FileSetting" />
        <xs:element name="SystemParameter" type="SystemParameterSetting" />
      </xs:choice>
    </xs:sequence>
  </xs:complexType>

  <xs:complexType name="Common">
    <xs:sequence>
      <xs:element name="Name" type="xs:string" />
      <xs:element name="ID" type="IDString" />
      <xs:element name="Description" type="xs:string" minOccurs="0" />
      <xs:element name="LocalizedNames" type="LocalizedName" minOccurs="0" />
      <xs:element name="LocalizedDescriptions" type="LocalizedDescription" minOccurs="0" />
      <xs:element name="Version" type="xs:integer" />
      <xs:element name="DeferToMSAccount" type="Empty"  minOccurs="0" />
      <xs:element name="Settings" type="Settings" />
    </xs:sequence>
  </xs:complexType>

  <xs:complexType name="Application">
    <xs:sequence>
      <xs:element name="Name" type="xs:string" />
      <xs:element name="ID" type="IDString" />
      <xs:element name="Description" type="xs:string" minOccurs="0" />
      <xs:element name="LocalizedNames" type="LocalizedName" minOccurs="0" />
      <xs:element name="LocalizedDescriptions" type="LocalizedDescription" minOccurs="0" />
      <xs:element name="Version" type="xs:integer" />
      <xs:element name="DeferToMSAccount" type="Empty"  minOccurs="0" />
      <xs:element name="Processes" type="Processes" />
      <xs:element name="Settings" type="Settings" />
    </xs:sequence>
  </xs:complexType>


  <xs:element name="SettingsLocationTemplate">
    <xs:complexType>
      <xs:sequence>

        <xs:element name="Name" type="xs:string" />
        <xs:element name="ID" type="IDString" />
        <xs:element name="Description" type="xs:string" minOccurs="0" />
        <xs:element name="LocalizedNames" type="LocalizedName" minOccurs="0" />
        <xs:element name="LocalizedDescriptions" type="LocalizedDescription" minOccurs="0" />

        <xs:choice>

          <!-- Single application -->
          <xs:sequence>
            <xs:element name="Version" type="TemplateVersion" />
            <xs:element name="Author" type="Author" minOccurs="0" />
            <xs:element name="DeferToMSAccount" type="Empty"  minOccurs="0" />
            <xs:element name="Processes" type="Processes" />
            <xs:element name="Settings" type="Settings" />
          </xs:sequence>

          <!-- Suite of applications -->
          <xs:sequence>
            <xs:element name="ManageSuiteOnly" type="xs:boolean" minOccurs="0" />
            <xs:element name="Author" type="Author" minOccurs="0" />
            <xs:element name="Common" type="Common" />
            <xs:element name="Application" type="Application" minOccurs="2" maxOccurs="unbounded" />
          </xs:sequence>

        </xs:choice>

      </xs:sequence>
    </xs:complexType>
  </xs:element>
  <!-- SettingsLocationTemplate -->

</xs:schema>
```






## 相关主题


[使用自定义 UE-V x 模板和 UE-V 2 版生成器](working-with-custom-ue-v-2x-templates-and-the-ue-v-2x-generator-new-uevv2.md)

[UE-V 2.x 的技术参考](technical-reference-for-ue-v-2x-both-uevv2.md)

 

 





