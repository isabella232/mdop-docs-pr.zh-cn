---
title: 关于 App-V 5.0 动态配置
description: 关于 App-V 5.0 动态配置
author: dansimp
ms.assetid: 88afaca1-68c5-45c4-a074-9371c56b5804
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0294a60570d6dea99193c8bd411639c4888ae6b1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798690"
---
# 关于 App-V 5.0 动态配置


你可以使用动态配置为用户自定义 app-v 5.0 程序包。 使用以下信息创建或编辑现有动态配置文件。

当您编辑动态配置文件时，它将自定义如何为用户或组运行 app-v 5.0 程序包。 这有助于通过删除使用所需设置重新序列化程序包的需要，为程序包自定义提供一种更方便的方法，并提供了一种独立于程序包内容和自定义设置的方式。

## 高级：动态配置


虚拟应用程序包包含提供程序包的所有核心信息的清单。 此信息包括程序包设置的默认设置，并确定最基本形式的设置（无需其他自定义）。 如果要为特定用户或组调整这些默认值，可以创建和编辑以下文件：

-   用户配置文件

-   部署配置文件

以前的 .xml 文件指定程序包设置，并允许在不直接影响程序包的情况下自定义程序包。 创建程序包时，sequencer 将使用程序包清单数据自动生成默认部署和用户配置 .xml 文件。 因此，这些自动生成的配置文件仅反映程序包 innately 在排序期间配置的默认设置。 如果将这些配置文件应用到由排序器生成的窗体中的程序包，则这些程序包将具有与它们的清单中的默认设置相同的默认设置。 这将为你提供一个特定于程序包的模板，以便在必须更改任何默认值时开始使用。

**注意** 以下信息仅可用于修改 sequencer 生成的配置文件，以自定义程序包以满足特定的用户或组要求。

 

### 动态配置文件内容

配置文件中的所有添加、删除和更新都需要与包的清单信息所指定的默认值相关。 查看下表：

<table>
<colgroup>
<col width="100%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>用户配置 .xml 文件</p></td>
</tr>
<tr class="even">
<td align="left"><p>部署配置 .xml 文件</p></td>
</tr>
<tr class="odd">
<td align="left"><p>程序包清单</p></td>
</tr>
</tbody>
</table>

 

上表表示文件的读取方式。 第一项表示将最后阅读的内容，因此其内容优先。 因此，所有程序包本身都包含和提供程序包清单中的默认设置。 如果应用了具有自定义设置的部署配置 .xml 文件，它将替代程序包清单默认值。 如果先应用带有自定义设置的用户配置 .xml 文件，它将覆盖部署配置和程序包清单默认值。

以下列表显示了有关两种文件类型的详细信息：

-   **用户配置文件（UserConfig）** -允许你指定或修改程序包的自定义设置。 当程序包部署到运行 App-v 5.0 客户端的计算机时，这些设置将应用于特定用户。

-   **部署配置文件（DeploymentConfig）** -允许你指定或修改程序包的默认设置。 当程序包部署到运行 App-v 5.0 客户端的计算机时，这些设置将应用于所有用户。

若要为计算机上的一组特定用户自定义程序包的设置，或进行将应用于本地用户位置（如 HKCU）的更改，应使用 UserConfig 文件。 若要修改计算机上所有用户的程序包的默认设置，或执行将应用到全局位置（如 HKEY \ _LOCAL \ _MACHINE 和 "所有用户" 文件夹）的更改，请使用 DeploymentConfig 文件。

UserConfig 文件提供的配置设置可应用于单个用户，而不会影响客户端上的任何其他用户：

-   每个用户将集成到本机系统中的扩展：-快捷方式、文件类型关联、URL 协议、AppPaths、软件客户端和 COM

-   虚拟子系统：-应用程序对象、环境变量、注册表修改、服务和字体

-   脚本（仅限用户上下文）

-   管理机构（用于控制带有 App-v 4.6 的程序包的共同存在）

DeploymentConfig 文件提供两个部分中的配置设置，一个相对于计算机上下文，另一个相对于用户上下文，它提供了上述 UserConfig 列表中列出的相同功能：

-   所有 UserConfig 设置

-   只能为所有用户全局应用的扩展

-   可针对全局计算机位置进行配置的虚拟子系统，例如注册表

-   产品源 URL

-   脚本（仅限计算机上下文）

-   用于终止子进程的控件

### 文件结构

App-v 5.0 动态配置文件的结构将在下一节中介绍。

### 动态用户配置文件

**标头**-动态用户配置文件的标题如下所示：

&lt;？ xml 版本 = "1.0" 编码 = "utf-8"？ &gt; &lt;UserConfiguration **PackageId**= "1F8488bf-2257-46b4-b27f-09c9dbaae707" DisplayName = "Reserved" xmlns = " <https://schemas.microsoft.com/appv/2010/userconfiguration"&gt> ;

**PackageId**的值与清单文件中存在的值相同。

**正文**-动态用户配置文件的主体可以包含清单文件中定义的所有应用扩展点，以及用于配置虚拟应用程序的信息。 正文中允许有四个子部分：

1. **应用程序**-程序包内的清单文件中包含的所有应用扩展都分配有一个应用程序 ID，该 ID 也是在清单文件中定义的。 这允许你启用或禁用程序包中给定应用程序的所有扩展。 **应用程序 ID**必须存在于清单文件中，否则将被忽略。

   &lt;UserConfiguration **PackageId**= "1F8488bf-2257-46b4-b27f-09c9dbaae707" DisplayName = "Reserved" xmlns = " <https://schemas.microsoft.com/appv/2010/userconfiguration"&gt> ;

   &lt;应用程序&gt;

   &lt;!--不能在策略中定义任何新应用程序。 AppV 客户端将忽略未在清单文件中还没有的任何应用程序 ID-&gt;

   &lt;应用程序 Id = "{a56fa627-c35f-4a01-9e79-7d36aed8225a}" 已启用 = "false"&gt;

   &lt;/Application&gt;

   &lt;/Applications&gt;

   …

   &lt;/UserConfiguration&gt;

2. **子系统**-AppExtensions 和其他子系统在子系统下排列为子 &lt; 节点 &gt; ：

   &lt;UserConfiguration **PackageId**= "1F8488bf-2257-46b4-b27f-09c9dbaae707" DisplayName = "Reserved" xmlns = " <https://schemas.microsoft.com/appv/2010/userconfiguration"&gt> ;

   &lt;子系统&gt;

   ..

   &lt;/Subsystems&gt;

   ..

   &lt;/UserConfiguration&gt;

   可以使用 "**enabled**" 属性启用/禁用每个子系统。 下面是各种子系统和使用示例。

   **扩充**

   某些子系统（扩展子系统）控制扩展。 这些子系统包括：-快捷方式、文件类型关联、URL 协议、AppPaths、软件客户端和 COM

   可以独立于内容启用和禁用扩展子系统。  因此，如果启用了快捷方式，默认情况下，客户端将使用清单中包含的快捷方式。 每个扩展子系统都可以包含一个 &lt; 扩展 &gt; 节点。 如果此子元素存在，客户端将忽略该子系统的清单文件中的内容，并且仅使用配置文件中的内容。

   使用快捷方式子系统的示例：

   1.  如果用户在动态或部署配置文件中定义了此项，请执行以下操作：

                                    **&lt;Shortcuts  Enabled="true"&gt;**

                                                **&lt;Extensions&gt;**

                                                 ...

                                                **&lt;/Extensions&gt;**

                                    **&lt;/Shortcuts&gt;**

                         Content in the manifest will be ignored.   

   2.  如果用户仅定义下列内容：

                                   **&lt;Shortcuts  Enabled="true"/&gt;**

                         Then the content in the Manifest will be integrated during publishing.

   3.  如果用户定义了以下

                                  **&lt;Shortcuts  Enabled="true"&gt;**

                                                **&lt;Extensions/&gt;**

                                    **&lt;/Shortcuts&gt;**

   然后，清单中的所有快捷方式仍将被忽略。 将不会集成任何快捷方式。

   支持的扩展子系统有：

   **快捷方式：** 此示例控制将集成到本地系统中的快捷方式。 下面是一个包含两个快捷方式的示例：

   &lt;子系统&gt;

   &lt;已启用快捷方式 = "true"&gt;

     &lt;Extensions&gt;

       &lt;Extension Category="AppV.Shortcut"&gt;

         &lt;Shortcut&gt;

           &lt;File&gt;\[{Common Programs}\]\\Microsoft Contoso\\Microsoft ContosoApp Filler 2010.lnk&lt;/File&gt;

           &lt;Target&gt;\[{PackageRoot}\]\\Contoso\\ContosoApp.EXE&lt;/Target&gt;

           &lt;Icon&gt;\[{Windows}\]\\Installer\\{90140000-0011-0000-0000-0000000FF1CE}\\inficon.exe&lt;/Icon&gt;

           &lt;Arguments /&gt;

           &lt;WorkingDirectory /&gt;

           &lt;AppUserModelId&gt;ContosoApp.Filler.3&lt;/AppUserModelId&gt;

           &lt;Description&gt;Fill out dynamic forms to gather and reuse information throughout the organization using Microsoft ContosoApp.&lt;/Description&gt;

           &lt;Hotkey&gt;0&lt;/Hotkey&gt;

           &lt;ShowCommand&gt;1&lt;/ShowCommand&gt;

           &lt;ApplicationId&gt;\[{PackageRoot}\]\\Contoso\\ContosoApp.EXE&lt;/ApplicationId&gt;

         &lt;/Shortcut&gt;

     &lt;/Extension&gt;

     &lt;扩展类别 = "AppV。快捷方式"&gt;

       &lt;Shortcut&gt;

         &lt;File&gt;\[{AppData}\]\\Microsoft\\Contoso\\Recent\\Templates.LNK&lt;/File&gt;

         &lt;Target&gt;\[{AppData}\]\\Microsoft\\Templates&lt;/Target&gt;

         &lt;Icon /&gt;

         &lt;Arguments /&gt;

         &lt;WorkingDirectory /&gt;

         &lt;AppUserModelId /&gt;

         &lt;Description /&gt;

         &lt;Hotkey&gt;0&lt;/Hotkey&gt;

         &lt;ShowCommand&gt;1&lt;/ShowCommand&gt;

         &lt;!-- Note the ApplicationId is optional --&gt;

       &lt;/Shortcut&gt;

     &lt;/Extension&gt;

    &lt;/Extensions&gt;

   &lt;/Shortcuts&gt;

   **文件类型关联：** 将文件类型与要在默认情况下打开的程序相关联，并设置上下文菜单。 （也可以使用此 susbsystem 设置 MIME 类型）。 示例文件类型关联如下所示：

   &lt;FileTypeAssociations 启用 = "true"&gt;

   &lt;Extensions&gt;

     &lt;扩展类别 = "FileTypeAssociation"&gt;

       &lt;FileTypeAssociation&gt;

         &lt;FileExtension MimeAssociation="true"&gt;

         &lt;Name&gt;.docm&lt;/Name&gt;

         &lt;ProgId&gt;contosowordpad.DocumentMacroEnabled.12&lt;/ProgId&gt;

         &lt;PerceivedType&gt;document&lt;/PerceivedType&gt;

         &lt;ContentType&gt;application/vnd.ms-contosowordpad.document.macroEnabled.12&lt;/ContentType&gt;

         &lt;OpenWithList&gt;

           &lt;ApplicationName&gt;wincontosowordpad.exe&lt;/ApplicationName&gt;

         &lt;/OpenWithList&gt;

        &lt;OpenWithProgIds&gt;

           &lt;ProgId&gt;contosowordpad.8&lt;/ProgId&gt;

         &lt;/OpenWithProgIds&gt;

         &lt;ShellNew&gt;

           &lt;Command /&gt;

           &lt;DataBinary /&gt;

           &lt;DataText /&gt;

           &lt;FileName /&gt;

           &lt;NullFile&gt;true&lt;/NullFile&gt;

           &lt;ItemName /&gt;

           &lt;IconPath /&gt;

           &lt;MenuText /&gt;

           &lt;Handler /&gt;

         &lt;/ShellNew&gt;

       &lt;/FileExtension&gt;

       &lt;ProgId&gt;

          &lt;Name&gt;contosowordpad.DocumentMacroEnabled.12&lt;/Name&gt;

           &lt;DefaultIcon&gt;\[{Windows}\]\\Installer\\{90140000-0011-0000-0000-0000000FF1CE}\\contosowordpadicon.exe,15&lt;/DefaultIcon&gt;

           &lt;Description&gt;Blah Blah Blah&lt;/Description&gt;

           &lt;FriendlyTypeName&gt;\[{FOLDERID\_ProgramFilesX86}\]\\Microsoft Contoso 14\\res.dll,9182&lt;/FriendlyTypeName&gt;

           &lt;InfoTip&gt;\[{FOLDERID\_ProgramFilesX86}\]\\Microsoft Contoso 14\\res.dll,1424&lt;/InfoTip&gt;

           &lt;EditFlags&gt;0&lt;/EditFlags&gt;

           &lt;ShellCommands&gt;

             &lt;DefaultCommand&gt;Open&lt;/DefaultCommand&gt;

             &lt;ShellCommand&gt;

                &lt;ApplicationId&gt;{e56fa627-c35f-4a01-9e79-7d36aed8225a}&lt;/ApplicationId&gt;

                &lt;Name&gt;Edit&lt;/Name&gt;

                &lt;FriendlyName&gt;&Edit&lt;/FriendlyName&gt;

                &lt;CommandLine&gt;"\[{PackageRoot}\]\\Contoso\\WINcontosowordpad.EXE" /vu "%1"&lt;/CommandLine&gt;

             &lt;/ShellCommand&gt;

             &lt;/ShellCommand&gt;

               &lt;ApplicationId&gt;{e56fa627-c35f-4a01-9e79-7d36aed8225a}&lt;/ApplicationId&gt;

               &lt;Name&gt;Open&lt;/Name&gt;

               &lt;FriendlyName&gt;&Open&lt;/FriendlyName&gt;

               &lt;CommandLine&gt;"\[{PackageRoot}\]\\Contoso\\WINcontosowordpad.EXE" /n "%1"&lt;/CommandLine&gt;

               &lt;DropTargetClassId /&gt;

               &lt;DdeExec&gt;

                 &lt;Application&gt;mscontosowordpad&lt;/Application&gt;

                 &lt;Topic&gt;ShellSystem&lt;/Topic&gt;

                 &lt;IfExec&gt;\[SHELLNOOP\]&lt;/IfExec&gt;

                 &lt;DdeCommand&gt;\[SetForeground\]\[ShellNewDatabase "%1"\]&lt;/DdeCommand&gt;

               &lt;/DdeExec&gt;

             &lt;/ShellCommand&gt;

           &lt;/ShellCommands&gt;

         &lt;/ProgId&gt;

        &lt;/FileTypeAssociation&gt;

      &lt;/Extension&gt;

     &lt;/Extensions&gt;

     &lt;/FileTypeAssociations&gt;

   **URL 协议**：这将控制与客户端计算机的本地注册表集成的 URL 协议，例如 "mailto："。

   &lt;URLProtocols 启用 = "true"&gt;

   &lt;Extensions&gt;

   &lt;扩展类别 = "URLProtocol"&gt;

   &lt;URLProtocol&gt;

     &lt;名称 &gt; mailto &lt; /Name&gt;

     &lt;ApplicationURLProtocol&gt;

     &lt;DefaultIcon &gt; \ [{ProgramFilesX86} \] \\Microsoft Contoso\\Contoso\\contosomail.EXE，-9403 &lt; /DefaultIcon&gt;

     &lt;EditFlags &gt; 2 &lt; /EditFlags&gt;

     &lt;介绍&gt;

     &lt;AppUserModelId&gt;

     &lt;FriendlyTypeName /&gt;

     &lt;提示&gt;

   &lt;SourceFilter /&gt;

     &lt;ShellFolder /&gt;

     &lt;WebNavigableCLSID /&gt;

     &lt;ExplorerFlags &gt; 2 &lt; /ExplorerFlags&gt;

     &lt;CLSID&gt;

     &lt;ShellCommands&gt;

     &lt;DefaultCommand &gt; open &lt; /DefaultCommand&gt;

     &lt;ShellCommand&gt;

     &lt;ApplicationId &gt; \ [{ProgramFilesX86} \] \\Microsoft Contoso\\Contoso\\contosomail.EXE&lt; /ApplicationId&gt;

     &lt;名称 &gt; open &lt; /Name&gt;

     &lt;命令行 &gt; \ [{ProgramFilesX86} \\Microsoft Contoso\\Contoso\\contosomail.EXE "-c OEP。注意/m "%1" &lt; /CommandLine&gt;

     &lt;DropTargetClassId /&gt;

     &lt;FriendlyName&gt;

     &lt;扩展的 &gt; 0 &lt; /Extended&gt;

     &lt;LegacyDisable &gt; 0 &lt; /LegacyDisable&gt;

     &lt;SuppressionPolicy &gt; 2 &lt; /SuppressionPolicy&gt;

      &lt;DdeExec&gt;

     &lt;NoActivateHandler /&gt;

     &lt;应用程序 &gt; contosomail &lt; /Application&gt;

     &lt;主题 &gt; ShellSystem &lt; /Topic&gt;

     &lt;IfExec &gt; \ [SHELLNOOP \] &lt; /IfExec&gt;

     &lt;DdeCommand &gt; \ [SetForeground \] \ [ShellNewDatabase "%1" \] &lt; /DdeCommand&gt;

     &lt;/DdeExec&gt;

     &lt;/ShellCommand&gt;

     &lt;/ShellCommands&gt;

     &lt;/ApplicationURLProtocol&gt;

     &lt;/URLProtocol&gt;

     &lt;/Extension&gt;

     &lt;/Extension&gt;

     &lt;/URLProtocols&gt;

   **软件客户端**：允许应用注册为电子邮件客户端、新闻阅读器、媒体播放器，并使应用在 "设置程序访问和计算机默认值" UI 中可见。 在大多数情况下，只需启用和禁用它。 如果您希望其他客户端（除了该客户端之外）仍启用，则还可以启用和禁用电子邮件客户端的控件。

   &lt;SoftwareClients 启用 = "true"&gt;

     &lt;ClientConfiguration EmailEnabled = "false"/&gt;

   &lt;/SoftwareClients&gt;

   AppPaths：-如果使用 "myapp" 的 apppath 名称注册应用程序 contoso.exe，则可以在 "运行" 菜单下键入 "myapp"，它将打开 "contoso.exe"。

   &lt;AppPaths 启用 = "true"&gt;

   &lt;Extensions&gt;

   &lt;扩展类别 = "AppPath"&gt;

   &lt;AppPath&gt;

     &lt;ApplicationId &gt; \ [{ProgramFilesX86} \] \\Microsoft Contoso\\Contoso\\contosomail.EXE&lt; /ApplicationId&gt;

     &lt;名称 &gt;contosomail.exe&lt; /Name&gt;

     &lt;ApplicationPath &gt; \ [{ProgramFilesX86} \] \\Microsoft Contoso\\Contoso\\contosomail.EXE&lt; /ApplicationPath&gt;

     &lt;PATHEnvironmentVariablePrefix /&gt;

     &lt;CanAcceptUrl &gt; false &lt; /CanAcceptUrl&gt;

     &lt;SaveUrl /&gt;

   &lt;/AppPath&gt;

   &lt;/Extension&gt;

   &lt;/Extensions&gt;

   &lt;/AppPaths&gt;

   **COM**：允许应用程序注册本地 COM 服务器。 模式可以是集成、隔离或关闭。 Isol 时。

   &lt;COM 模式 = "已隔离"/&gt;

   **其他设置**：

   除了扩展之外，还可以启用/禁用和编辑其他子系统：

   **虚拟内核对象**：

   &lt;已启用对象 = "false"/&gt;

   **虚拟注册表**：如果要在 HKCU 中的虚拟注册表中设置注册表，则使用该注册表

   &lt;已启用注册表 = "true"&gt;

   &lt;包括&gt;

   &lt;Key Path = "\\REGISTRY\\USER\\\ [{AppVCurrentUserSID} \] \\Software\\ABC"&gt;

   &lt;值类型 = "REG \ _SZ" Name = "Bar" 数据 = "NewValue"/&gt;

    &lt;/Key&gt;

     &lt;Key Path = "\\REGISTRY\\USER\\\ [{AppVCurrentUserSID} \] \\Software\\EmptyKey"/&gt;

    &lt;/Include&gt;

   &lt;删除&gt;

     &lt;/Registry&gt;

   **虚拟文件系统**

         &lt;FileSystem Enabled="true" /&gt;

   **虚拟字体**

         &lt;Fonts Enabled="false" /&gt;

   **虚拟环境变量**

   &lt;EnvironmentVariables 启用 = "true"&gt;

   &lt;包括&gt;

          &lt;Variable Name="UserPath" Value="%path%;%UserProfile%" /&gt;

          &lt;Variable Name="UserLib" Value="%UserProfile%\\ABC" /&gt;

          &lt;/Include&gt;

         &lt;Delete&gt;

          &lt;Variable Name="lib" /&gt;

           &lt;/Delete&gt;

           &lt;/EnvironmentVariables&gt;

   **虚拟服务**

         &lt;Services Enabled="false" /&gt;

3. **UserScripts** -脚本可用于设置或更改虚拟环境以及在部署或删除时执行脚本，在应用程序执行之前，或者在应用程序终止后使用它们来 "清理" 环境。 请参考由排序器输出的示例用户配置文件，以查看示例脚本。 下面的 "脚本" 部分提供了有关可以使用的各种触发器的详细信息。

4. **ManagingAuthority** -当程序包的两个版本在同一台计算机上（一个部署到 app-v 4.6 和另一个部署在 app-v 5.0 的计算机上）共存时，可以使用。 若要允许 App-v vNext 接管已命名程序包的 app-v 4.6 扩展点，请在 UserConfig 文件中输入以下内容（其中 PackageName 是 app-v 4.6 中的程序包 GUID：

   &lt;ManagingAuthority TakeoverExtensionPointsFrom46 = "true" PackageName = "032630c0-b8e2-417c-acef-76fc5297fe81"/&gt;

### 动态部署配置文件

**标头**-部署配置文件的标题如下所示：

&lt;？ xml 版本 = "1.0" 编码 = "utf-8"？ &gt; &lt;DeploymentConfiguration **PackageId**= "1F8488bf-2257-46b4-b27f-09c9dbaae707" DisplayName = "Reserved" xmlns = " <https://schemas.microsoft.com/appv/2010/deploymentconfiguration"&gt> ;

**PackageId**的值与清单文件中存在的值相同。

**正文**-部署配置文件的正文包含两个部分：

-   "用户配置" 部分-允许与上一节中所述的用户配置文件相同的内容。 将程序包发布到用户后，此部分中的任何 appextensions 配置设置都将覆盖程序包内的清单中的相应设置，除非还提供用户配置文件。 如果还提供了 UserConfig 文件，则将使用它，而不是部署配置文件中的用户设置。 如果程序包是全局发布的，则仅将部署配置文件的内容与清单结合使用。

-   计算机配置部分-包含只能为整个计算机配置的信息，而不能为计算机上的特定用户配置信息。 例如，HKEY \ _LOCAL 在 VFS 中 _MACHINE 注册表项。

&lt;DeploymentConfiguration **PackageId**= "1F8488bf-2257-46b4-b27f-09c9dbaae707" DisplayName = "Reserved" xmlns = " <https://schemas.microsoft.com/appv/2010/deploymentconfiguration"&gt> ;

&lt;UserConfiguration&gt;

  ..

&lt;/UserConfiguration&gt;

&lt;MachineConfiguration&gt;

..

&lt;/MachineConfiguration&gt;

..

&lt;/MachineConfiguration&gt;

&lt;/DeploymentConfiguration&gt;

**用户配置**-使用以前的 "**动态用户配置文件**" 部分，了解有关部署配置文件的 "用户配置" 部分中提供的设置的信息。

计算机配置-部署配置文件的 "计算机配置" 部分用于配置只能为整个计算机设置的信息，而不能为计算机上的特定用户配置信息。 例如，HKEY \ _LOCAL \ _MACHINE 虚拟注册表中的注册表项。 此元素下允许有四个子部分

1.  **子系统**-AppExtensions 和其他子系统在子系统下排列为子节点 &lt; &gt; ：

    &lt;MachineConfiguration&gt;

      &lt;子系统&gt;

      ..

      &lt;/Subsystems&gt;

    ..

    &lt;/MachineConfiguration&gt;

    下一节将显示各种子系统和使用示例。

    **扩展**：

    某些子系统（扩展子系统）只能控制扩展，这些应用程序只能应用于所有用户。 子系统是应用程序功能。 由于此操作仅适用于所有用户，因此必须对程序包进行全局发布，才能将此类型的扩展集成到本地系统中。 适用于用户配置中的扩展的控件和设置的相同规则同样适用于 MachineConfiguration 部分中的扩展。

    **应用程序功能**：由 Windows 操作系统界面中的默认程序使用。 允许应用程序将其自身注册为能够打开某些文件扩展名，作为 "开始" 菜单 internet 浏览器槽的 contender，以便打开某些 windows MIME 类型。此扩展还使虚拟应用程序在 "设置默认程序" UI 中可见。：

    &lt;ApplicationCapabilities 启用 = "true"&gt;

      &lt;Extensions&gt;

       &lt;扩展类别 = "ApplicationCapabilities"&gt;

        &lt;ApplicationCapabilities&gt;

         &lt;ApplicationId&gt;\[{PackageRoot}\]\\LitView\\LitViewBrowser.exe&lt;/ApplicationId&gt;

         &lt;Reference&gt;

          &lt;Name&gt;LitView Browser&lt;/Name&gt;

          &lt;Path&gt;SOFTWARE\\LitView\\Browser\\Capabilities&lt;/Path&gt;

         &lt;/Reference&gt;

       &lt;CapabilityGroup&gt;

        &lt;Capabilities&gt;

         &lt;Name&gt;@\[{ProgramFilesX86}\]\\LitView\\LitViewBrowser.exe,-12345&lt;/Name&gt;

         &lt;Description&gt;@\[{ProgramFilesX86}\]\\LitView\\LitViewBrowser.exe,-12346&lt;/Description&gt;

         &lt;Hidden&gt;0&lt;/Hidden&gt;

         &lt;EMailSoftwareClient&gt;Lit View E-Mail Client&lt;/EMailSoftwareClient&gt;

         &lt;FileAssociationList&gt;

          &lt;FileAssociation Extension=".htm" ProgID="LitViewHTML" /&gt;

          &lt;FileAssociation Extension=".html" ProgID="LitViewHTML" /&gt;

          &lt;FileAssociation Extension=".shtml" ProgID="LitViewHTML" /&gt;

         &lt;/FileAssociationList&gt;

         &lt;MIMEAssociationList&gt;

          &lt;MIMEAssociation Type="audio/mp3" ProgID="LitViewHTML" /&gt;

          &lt;MIMEAssociation Type="audio/mpeg" ProgID="LitViewHTML" /&gt;

         &lt;/MIMEAssociationList&gt;

        &lt;URLAssociationList&gt;

          &lt;URLAssociation Scheme="http" ProgID="LitViewHTML.URL.http" /&gt;

         &lt;/URLAssociationList&gt;

         &lt;/Capabilities&gt;

      &lt;/CapabilityGroup&gt;

       &lt;/ApplicationCapabilities&gt;

      &lt;/Extension&gt;

    &lt;/Extensions&gt;

    &lt;/ApplicationCapabilities&gt;

    **其他设置**：

    除了扩展外，还可以编辑其他子系统：

    **计算机范围的虚拟注册表**：当你想要在 HKEY 中的虚拟注册表中设置注册表项时，请使用： _Local \ _Machine

    &lt;注册表&gt;

    &lt;包括&gt;

      &lt;注册表项路径 = "\\REGISTRY\\Machine\\Software\\ABC"&gt;

        &lt;Value Type="REG\_SZ" Name="Bar" Data="Baz" /&gt;

       &lt;/Key&gt;

      &lt;键路径 = "\\REGISTRY\\Machine\\Software\\EmptyKey"/&gt;

     &lt;/Include&gt;

    &lt;删除&gt;

    &lt;/Registry&gt;

    **计算机范围的虚拟内核对象**

    &lt;对象&gt;

    &lt;NotIsolate&gt;

       &lt;对象名称 = "testObject"/&gt;

     &lt;/NotIsolate&gt;

    &lt;/Objects&gt;

2.  **ProductSourceURLOptOut**：指示是否可以通过 PackageSourceRoot 全局修改程序包的 URL （以支持分支 office 方案）。 默认值为 false，设置更改将在下一次启动时生效。  

    &lt;MachineConfiguration&gt;

      .. 

      &lt;ProductSourceURLOptOut 启用 = "true"/&gt;

      ..

    &lt;/MachineConfiguration&gt;

3.  **MachineScripts** -程序包可以配置为在部署、发布或删除时执行脚本。 请参考由排序器生成的示例部署配置文件，以查看示例脚本。 下面的 "脚本" 部分提供了有关可使用的各种触发器的详细信息

4.  **TerminateChildProcess**：-可指定应用程序可执行文件，其子进程将在应用程序 exe 进程终止时终止。

    &lt;MachineConfiguration&gt;

      ..   

      &lt;TerminateChildProcesses&gt;

        &lt;Application Path="\[{PackageRoot}\]\\Contoso\\ContosoApp.EXE" /&gt;

        &lt;Application Path="\[{PackageRoot}\]\\LitView\\LitViewBrowser.exe" /&gt;

        &lt;Application Path="\[{ProgramFilesX86}\]\\Microsoft Contoso\\Contoso\\contosomail.EXE" /&gt;

      &lt;/TerminateChildProcesses&gt;

      ..

    &lt;/MachineConfiguration&gt;

### 脚本

下表描述了各种脚本事件和可以在其中运行它们的上下文。

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
<th align="left">脚本执行时间</th>
<th align="left">可在部署配置中指定</th>
<th align="left">可在 "用户配置" 中指定</th>
<th align="left">可以在程序包的虚拟环境中运行</th>
<th align="left">可以在特定应用程序的上下文中运行</th>
<th align="left">在系统/用户上下文中运行：（部署配置、用户配置）</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>AddPackage</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>（SYSTEM，N/A）</p></td>
</tr>
<tr class="even">
<td align="left"><p>PublishPackage</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>（系统、用户）</p></td>
</tr>
<tr class="odd">
<td align="left"><p>UnpublishPackage</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>（系统、用户）</p></td>
</tr>
<tr class="even">
<td align="left"><p>RemovePackage</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>（SYSTEM，N/A）</p></td>
</tr>
<tr class="odd">
<td align="left"><p>StartProcess</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p>（用户、用户）</p></td>
</tr>
<tr class="even">
<td align="left"><p>ExitProcess</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p></p></td>
<td align="left"><p>X</p></td>
<td align="left"><p>（用户、用户）</p></td>
</tr>
<tr class="odd">
<td align="left"><p>StartVirtualEnvironment</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p></p></td>
<td align="left"><p>（用户、用户）</p></td>
</tr>
<tr class="even">
<td align="left"><p>TerminateVirtualEnvironment</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>（用户、用户）</p></td>
</tr>
</tbody>
</table>

 

### 使用 app-v 5.0 清单文件创建动态配置文件

你可以使用以下三种方法之一创建动态配置文件：手动使用 App-v 5.0 管理控制台或对程序包进行排序（将使用两个示例文件生成）。

有关如何使用 App-v 5.0 管理控制台创建文件的详细信息，请参阅[如何使用 app-v 5.0 管理控制台创建自定义配置文件](how-to-create-a-custom-configuration-file-by-using-the-app-v-50-management-console.md)。

若要手动创建文件，上一节中的上述信息可以合并到单个文件中。 我们建议使用由排序器生成的文件。






## 相关主题


[如何使用 PowerShell 应用部署配置文件](how-to-apply-the-deployment-configuration-file-by-using-powershell.md)

[如何使用 PowerShell 应用用户配置文件](how-to-apply-the-user-configuration-file-by-using-powershell.md)

[App-V 5.0 的操作](operations-for-app-v-50.md)

 

 





