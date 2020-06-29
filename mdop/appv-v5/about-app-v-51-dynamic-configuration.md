---
title: 关于应用-V 5.1 动态配置
description: 你可以使用动态配置为用户自定义 app-v 5.1 程序包。 使用以下信息创建或编辑现有动态配置文件。
author: dansimp
ms.assetid: 35bc9908-d502-4a9c-873f-8ee17b6d9d74
ms.reviewer: ''
manager: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/28/2018
ms.author: dansimp
ms.openlocfilehash: ec8a25da6e139ac329810b1e04f7097cadaa6ab4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798676"
---
# 关于应用-V 5.1 动态配置 
通过动态配置，你可以编辑动态配置文件，以自定义用户或组的 App-v 5.1 程序包的运行方式。 程序包自定义消除了使用所需设置 resequence 程序包的需要。  它还提供了一种使程序包内容和自定义设置独立的方式。

虚拟应用程序包包含提供程序包的所有核心信息的清单。 此信息包括程序包设置的默认设置，并确定最基本形式的设置（无需其他自定义）。 

创建程序包时，sequencer 将使用程序包清单数据自动生成默认部署和用户配置 .xml 文件。 因此，这些生成的文件反映在排序期间配置的默认设置。 如果将这些文件应用到由排序器生成的窗体中的程序包，则这些程序包具有的默认设置来自其清单。 

如果需要，请使用这些生成的文件进行更改，这些文件不会直接影响程序包。 如果要添加、删除或更新配置文件，请对清单信息中的默认值进行更改。

>[!TIP]
>文件的阅读顺序：<ul><li>UserConfig.xml</li><li>DeploymentConfig.xml</li><li>部件</li></ul><p>第一个条目表示最后读取的内容。 因此，其内容优先，并且所有程序包本身包含和提供程序包清单中的默认设置。<ol><li> 如果自定义 DeploymentConfig.xml 文件并应用自定义设置，程序包清单中的默认设置将被覆盖。 </li><li> 如果自定义 UserConfig.xml 并应用自定义设置，则将覆盖部署配置和程序包清单的默认设置。 </li></ol>

## 用户配置文件内容（UserConfig.xml）
UserConfig 文件提供将程序包部署到运行 App-v 5.1 客户端的计算机时为特定用户应用的配置设置。  这些设置不会影响客户端上的任何其他用户。

使用 UserConfig 文件指定或修改程序包的自定义设置：

-   每个用户在本机系统中集成的扩展：快捷方式、文件类型关联、URL 协议、AppPaths、软件客户端和 COM
-   虚拟子系统：应用程序对象、环境变量、注册表修改、服务和字体
-   脚本（仅限用户上下文）
-   管理机构（用于控制带有 App-v 4.6 的程序包的共同存在）

### 标题

动态用户配置文件的标题如下所示：

```xml
<?xml version="1.0" encoding="utf-8"?><UserConfiguration PackageId="1f8488bf-2257-46b4-b27f-09c9dbaae707" DisplayName="Reserved" xmlns="http://schemas.microsoft.com/appv/2010/userconfiguration">
```

**PackageId**的值与清单文件中存在的值相同。


### 正文

动态用户配置文件的主体可以包含清单文件中定义的所有应用扩展点，以及用于配置虚拟应用程序的信息。 正文中允许有四个子部分：

1.  **[应用程序](#applications)** 
2.  **[子系统](#subsystems)**
3.  **[UserScripts](#userscripts)**
4.  **[ManagingAuthority](#managingauthority)**

#### 应用程序

程序包中的清单文件中包含的所有应用扩展均分配有一个应用程序 ID，你可以在清单文件中找到该 ID。 应用程序 ID 允许你启用或禁用程序包内给定应用程序的所有扩展。 应用程序 ID 必须存在于清单文件中，否则将被忽略。

```XML
<UserConfiguration PackageId="1f8488bf-2257-46b4-b27f-09c9dbaae707" DisplayName="Reserved"  xmlns="http://schemas.microsoft.com/appv/2010/userconfiguration">

<Applications>

<!--No new application can be defined in policy. AppV Client will ignore any application ID that is not also in the Manifest file-->

<Application Id="{a56fa627-c35f-4a01-9e79-7d36aed8225a}" Enabled="false">

</Application>

</Applications>

..

</UserConfiguration>
```

#### 子系统

以子节点形式排列的 AppExtensions 和其他子系统。

```XML
<UserConfiguration PackageId="1f8488bf-2257-46b4-b27f-09c9dbaae707" DisplayName="Reserved" xmlns="http://schemas.microsoft.com/appv/2010/userconfiguration">

<Subsystems>

..

</Subsystems>

..

</UserConfiguration>
```

你可以使用**已启用**的属性启用或禁用每个子系统。

**Extensions** 

某些子系统（扩展子系统）控制扩展。 这些子系统是快捷方式、文件类型关联、URL 协议、AppPaths、软件客户端和 COM。

可以独立于内容启用和禁用扩展子系统。 例如，如果启用快捷方式，默认情况下，客户端将使用清单中包含的快捷方式。 每个扩展子系统都可以包含一个 \<Extensions\> 节点。 如果此子元素存在，客户端将忽略该子系统的清单文件中的内容，并且仅使用配置文件中的内容。 

_**示例：**_ 

- 如果在用户或部署配置文件中定义此内容，则会忽略清单中的内容。

  ```XML

  <Shortcuts  Enabled="true"\>

  <Extensions>

  ...

  </Extensions>

  </Shortcuts>
  ```
- 如果仅定义以下内容，则清单中的内容将在发布过程中集成。

  ```XML

  <Shortcuts  Enabled="true"/>
  ```

- 如果你定义以下情况，清单中的所有快捷方式仍然被忽略。 换句话说，没有快捷方式集成。

  ```XML

  <Shortcuts  Enabled="true">

     <Extensions/>

  </Shortcuts>
  ```

_**支持的扩展子系统：**_ 

**快捷方式**扩展子系统控制哪些快捷方式集成到了本地系统中。  

```XML

<Subsystems>

<Shortcuts Enabled="true">

  <Extensions>

    <Extension Category="AppV.Shortcut">

      <Shortcut>

        <File>[{Common Programs}]\Microsoft Contoso\Microsoft ContosoApp Filler 2010.lnk</File>

        <Target>[{PackageRoot}]\Contoso\ContosoApp.EXE</Target>


      <Icon>[{Windows}]\Installer\{90140000-0011-0000-0000-0000000FF1CE}\inficon.exe</Icon>

        <Arguments />

        <WorkingDirectory />

        <AppUserModelId>ContosoApp.Filler.3</AppUserModelId>

        <Description>Fill out dynamic forms to gather and reuse information throughout the organization using Microsoft ContosoApp.</Description>

        <Hotkey>0</Hotkey>

        <ShowCommand>1</ShowCommand>

      <ApplicationId>[{PackageRoot}]\Contoso\ContosoApp.EXE</ApplicationId>

      </Shortcut>

  </Extension>

  <Extension Category="AppV.Shortcut">

    <Shortcut>

    <File>[{AppData}]\Microsoft\Contoso\Recent\Templates.LNK</File>

      <Target>[{AppData}]\Microsoft\Templates</Target>

      <Icon />

      <Arguments />

      <WorkingDirectory />

      <AppUserModelId />

      <Description />

      <Hotkey>0</Hotkey>

      <ShowCommand>1</ShowCommand>

      <!-- Note the ApplicationId is optional -->

    </Shortcut>

  </Extension>

 </Extensions>

</Shortcuts>
```

**文件类型 "关联**扩展子系统" 将文件类型与要在默认情况下打开的程序相关联，并设置上下文菜单。 

>[!TIP]
>你可以设置具有 MIME 类型的子系统。

```XML

<FileTypeAssociations Enabled="true">

<Extensions>

  <Extension Category="AppV.FileTypeAssociation">

    <FileTypeAssociation>

      <FileExtension MimeAssociation="true">

      <Name>.docm</Name>

      <ProgId>contosowordpad.DocumentMacroEnabled.12</ProgId>

      <PerceivedType>document</PerceivedType>

    <ContentType>application/vnd.ms-contosowordpad.document.macroEnabled.12</ContentType>

      <OpenWithList>

        <ApplicationName>wincontosowordpad.exe</ApplicationName>

      </OpenWithList>

     <OpenWithProgIds>

        <ProgId>contosowordpad.8</ProgId>

      </OpenWithProgIds>

      <ShellNew>

        <Command />

        <DataBinary />

        <DataText />

        <FileName />

        <NullFile>true</NullFile>

        <ItemName />

        <IconPath />

        <MenuText />

        <Handler />

      </ShellNew>

    </FileExtension>

    <ProgId>

       <Name>contosowordpad.DocumentMacroEnabled.12</Name>

      <DefaultIcon\>[{Windows}]\Installer\{90140000-0011-0000-0000-000000FF1CE}\contosowordpadicon.exe,15</DefaultIcon>

        <Description>Blah Blah Blah</Description>

        <FriendlyTypeName>[{FOLDERID_ProgramFilesX86}]\Microsoft Contoso 14\res.dll,9182</FriendlyTypeName>

        <InfoTip>[{FOLDERID_ProgramFilesX86}]\Microsoft Contoso 14\res.dll,1424</InfoTip>

        <EditFlags>0</EditFlags>

        <ShellCommands>

          <DefaultCommand>Open</DefaultCommand>

          <ShellCommand>

           <ApplicationId>{e56fa627-c35f-4a01-9e79-7d36aed8225a}</ApplicationId>

             <Name>Edit</Name>

             <FriendlyName>&Edit</FriendlyName>

           <CommandLine>"[{PackageRoot}]\Contoso\WINcontosowordpad.EXE" /vu "%1"</CommandLine>

          </ShellCommand>

          </ShellCommand>

          <ApplicationId>{e56fa627-c35f-4a01-9e79-7d36aed8225a}</ApplicationId>

            <Name>Open</Name>

            <FriendlyName>&Open</FriendlyName>

            <CommandLine>"[{PackageRoot}]\Contoso\WINcontosowordpad.EXE" /n "%1"</CommandLine>

            <DropTargetClassId />

            <DdeExec>

              <Application>mscontosowordpad</Application>

              <Topic>ShellSystem</Topic>

              <IfExec>[SHELLNOOP]</IfExec>

              <DdeCommand>[SetForeground][ShellNewDatabase"%1"]</DdeCommand>

            </DdeExec>

          </ShellCommand>

        </ShellCommands>

      </ProgId>

     </FileTypeAssociation>

   </Extension>

  </Extensions>

  </FileTypeAssociations>
```

**Url 协议**扩展子系统控制集成到客户端计算机的本地注册表中的 url 协议，例如_mailto：_。 

```XML

<URLProtocols Enabled="true">

<Extensions>

<Extension Category="AppV.URLProtocol">

<URLProtocol>

  <Name>mailto</Name>

  <ApplicationURLProtocol>

  <DefaultIcon>[{ProgramFilesX86}]\MicrosoftContoso\Contoso\contosomail.EXE,-9403</DefaultIcon>

  <EditFlags>2</EditFlags>

  <Description />

  <AppUserModelId />

  <FriendlyTypeName />

  <InfoTip />

<SourceFilter />

  <ShellFolder />

  <WebNavigableCLSID />

  <ExplorerFlags>2</ExplorerFlags>

  <CLSID />

  <ShellCommands>

  <DefaultCommand>open</DefaultCommand>

  <ShellCommand>

  <ApplicationId>[{ProgramFilesX86}]\Microsoft Contoso\Contoso\contosomail.EXE</ApplicationId>

  <Name>open</Name>

  <CommandLine>[{ProgramFilesX86}\Microsoft Contoso\Contoso\contosomail.EXE" -c OEP.Note /m "%1"</CommandLine>

  <DropTargetClassId />

  <FriendlyName />

  <Extended>0</Extended>

  <LegacyDisable>0</LegacyDisable>

  <SuppressionPolicy>2</SuppressionPolicy>

   <DdeExec>

  <NoActivateHandler />

  <Application>contosomail</Application>

  <Topic>ShellSystem</Topic>

  <IfExec>[SHELLNOOP]</IfExec>

  <DdeCommand>[SetForeground][ShellNewDatabase "%1"]</DdeCommand>

  </DdeExec>

  </ShellCommand>

  </ShellCommands>

  </ApplicationURLProtocol>

  </URLProtocol>

  </Extension>

  </Extension>

  </URLProtocols>
```

**软件客户端**扩展子系统允许应用注册为电子邮件客户端、新闻阅读器、媒体播放器，并使应用在 "设置程序访问和计算机默认值" UI 中可见。 在大多数情况下，你只需启用和禁用它。 如果您希望其他客户端（除了该客户端之外）仍启用，则还可以启用和禁用电子邮件客户端的控件。

```XML

<SoftwareClients Enabled="true">

  <ClientConfiguration EmailEnabled="false" />

</SoftwareClients>
```

**AppPaths**扩展子系统打开使用应用程序路径注册的应用。 例如，如果 contoso.exe 具有_myapp_的 apppath 名称，则用户可以从 "运行" 菜单键入_myapp_ ，打开 "contoso.exe"。

```XML

<AppPaths Enabled="true">

<Extensions>

<Extension Category="AppV.AppPath">

<AppPath>

  <ApplicationId>[{ProgramFilesX86}]\Microsoft Contoso\Contoso\contosomail.EXE</ApplicationId>

  <Name>contosomail.exe</Name>

  <ApplicationPath>[{ProgramFilesX86}]\Microsoft Contoso\Contoso\contosomail.EXE</ApplicationPath>

  <PATHEnvironmentVariablePrefix />

  <CanAcceptUrl>false</CanAcceptUrl>

  <SaveUrl />

</AppPath>

</Extension>

</Extensions>

</AppPaths>
```

**COM**扩展子系统允许将应用程序注册到本地 COM 服务器。 模式可以是：

-   集中
-   确定 
-   关闭

```XML

<COM Mode="Isolated"/>
```

**虚拟内核对象**

```XML

<Objects Enabled="false" />
```

**虚拟注册表**在 HKCU 中的虚拟注册表中设置注册表。

```XML

<Registry Enabled="true">

<Include>

<Key Path="\REGISTRY\USER\[{AppVCurrentUserSID}]\Software\ABC">

<Value Type="REG_SZ" Name="Bar" Data="NewValue" />

 </Key>

  <Key Path="\REGISTRY\USER\[{AppVCurrentUserSID}]\Software\EmptyKey" />

 </Include>

<Delete>

</Registry>
```

**虚拟文件系统**

```XML

    <FileSystem Enabled="true" />
```

**虚拟字体**

```XML

      <Fonts Enabled="false" />
```

**虚拟环境变量**

```XML

<EnvironmentVariables Enabled="true">

<Include>

       <Variable Name="UserPath" Value="%path%;%UserProfile%" />

       <Variable Name="UserLib" Value="%UserProfile%\ABC" />

       </Include>

      <Delete>

       <Variable Name="lib" />

        </Delete>

        </EnvironmentVariables>
```

**虚拟服务**

```XML

      <Services Enabled="false" />
```

#### UserScripts

使用 UserScripts 设置或更改虚拟环境。  你还可以在部署时执行脚本或在应用程序终止后清理环境。 若要查看示例脚本，请参阅由排序器生成的用户配置文件。 下面的 "脚本" 部分提供了有关可以使用的各种触发器的详细信息。

#### ManagingAuthority

当同一台计算机上存在两个版本的程序包（一个部署到 app-v 4.6 和另一个部署在 App-v 5.0 上）时，请使用 ManagingAuthority。 若要允许 App-v vNext 接管已命名程序包的 app-v 4.6 扩展点，请在 UserConfig 文件中输入以下内容（其中 PackageName 是 app-v 4.6 中的程序包 GUID：

```XML

<ManagingAuthority TakeoverExtensionPointsFrom46="true" PackageName="032630c0-b8e2-417c-acef-76fc5297fe81" />
```

## 部署配置文件（DeploymentConfig.xml）

DeploymentConfig 文件提供计算机上下文和用户上下文的配置设置，提供与 UserConfig 文件中列出的相同功能。 在将程序包部署到运行 app-v 5.1 客户端的计算机时，将应用该设置。

使用 DeploymentConfig 文件指定或修改程序包的自定义设置：

- 所有 UserConfig 设置
- 只能为所有用户全局应用的扩展
- 全局计算机位置（如注册表）的虚拟子系统
- 产品源 URL
- 脚本（仅限计算机上下文）
- 用于终止子进程的控件

### 标题

动态部署配置文件的标题如下所示：

```XML
<?xml version="1.0" encoding="utf-8"?><DeploymentConfiguration PackageId="1f8488bf-2257-46b4-b27f-09c9dbaae707" DisplayName="Reserved" xmlns="http://schemas.microsoft.com/appv/2010/deploymentconfiguration">
```

**PackageId**的值与清单文件中存在的值相同。

### 正文

动态部署配置文件的正文包含两个部分：

- **UserConfiguration：** 允许与上一节中所述的用户配置文件相同的内容。  将程序包发布给用户时，此部分中的任何 appextensions 配置设置将覆盖程序包中的清单中的相应设置，除非你提供用户配置文件。 如果也提供 UserConfig 文件，则会使用它，而不是部署配置文件中的用户设置。 如果全局发布程序包，则仅部署配置文件的内容与清单结合使用。 有关更多详细信息，请参阅[用户配置文件内容（UserConfig.xml）](#user-configuration-file-contents-userconfigxml)。

- **MachineConfiguration：** 包含只能为整个计算机配置的信息，而不能为计算机上的特定用户配置信息。 例如，HKEY_LOCAL_MACHINE VFS 中的注册表项。

```XML

<DeploymentConfiguration PackageId="1f8488bf-2257-46b4-b27f-09c9dbaae707" DisplayName="Reserved" xmlns="http://schemas.microsoft.com/appv/2010/deploymentconfiguration">

<UserConfiguration>

...

</UserConfiguration>

<MachineConfiguration>

...

</MachineConfiguration>

...

</MachineConfiguration>

</DeploymentConfiguration>
```

### UserConfiguration

有关为本部分提供的设置的信息，请参阅[用户配置文件内容（UserConfig.xml）](#user-configuration-file-contents-userconfigxml) 。 

### MachineConfiguration

使用 MachineConfiguration 部分配置整个计算机的信息;不适用于计算机上的特定用户。 例如，HKEY_LOCAL_MACHINE 虚拟注册表中的注册表项。 此元素下允许有四个子部分：

1.  **[子系统](#subsystems-1)**
2.  **[ProductSourceURLOptOut](#productsourceurloptout)**
3.  **[MachineScripts](#machinescripts)**
4.  **[TerminateChildProcess](#terminatechildprocess)**

#### 子系统

以子节点形式排列的 AppExtensions 和其他子系统。

```XML

<MachineConfiguration>

  <Subsystems>

  …

  </Subsystems>

…

</MachineConfiguration>
```

你可以使用**已启用**的属性启用或禁用每个子系统。

**Extensions** 

某些子系统（扩展子系统）控制扩展。 子系统是默认程序使用的应用程序功能。 对于此类型的扩展，包必须进行全局发布，才能集成到本地系统。 同样适用于应用于用户配置中的扩展的控件和设置的规则同样适用于 MachineConfiguration 部分中的扩展。

**应用程序功能**：默认程序用于允许应用程序将其自身注册为：

- 能够打开特定的文件扩展名
- "开始" 菜单 internet 浏览器槽的 contender
- 能够打开特定的 windows MIME 类型

此扩展还使虚拟应用程序在 "设置默认程序" UI 中可见。

```XML

<ApplicationCapabilities Enabled="true">

  <Extensions>

   <Extension Category="AppV.ApplicationCapabilities">

    <ApplicationCapabilities>


   <ApplicationId>[{PackageRoot}]\LitView\LitViewBrowser.exe</ApplicationId>

     <Reference>

      <Name>LitView Browser</Name>

      <Path>SOFTWARE\LitView\Browser\Capabilities</Path>

     </Reference>

   <CapabilityGroup>

    <Capabilities>


   <Name>@[{ProgramFilesX86}]\LitView\LitViewBrowser.exe,-12345</Name>


   <Description>@[{ProgramFilesX86}]\LitView\LitViewBrowser.exe,-12346</Description>

     <Hidden>0</Hidden>

     <EMailSoftwareClient>Lit View E-Mail Client</EMailSoftwareClient>

     <FileAssociationList>

      <FileAssociation Extension=".htm" ProgID="LitViewHTML" />

      <FileAssociation Extension=".html" ProgID="LitViewHTML" />

      <FileAssociation Extension=".shtml" ProgID="LitViewHTML" />

     </FileAssociationList>

     <MIMEAssociationList>

      <MIMEAssociation Type="audio/mp3" ProgID="LitViewHTML" />

      <MIMEAssociation Type="audio/mpeg" ProgID="LitViewHTML" />

     </MIMEAssociationList>

    <URLAssociationList>

      <URLAssociation Scheme="http" ProgID="LitViewHTML.URL.http" />

     </URLAssociationList>

     </Capabilities>

  </CapabilityGroup>

   </ApplicationCapabilities>

  </Extension>

</Extensions>

</ApplicationCapabilities>
```

_**支持的扩展子系统：**_ 

**计算机范围的虚拟注册表**扩展子系统在 HKEY_Local_Machine 内的虚拟注册表中设置注册表项。

```XML

<Registry>

<Include>

  <Key Path="\REGISTRY\\Machine\Software\ABC">

    <Value Type="REG_SZ" Name="Bar" Data="Baz" />

   </Key>

  <Key Path="\REGISTRY\Machine\Software\EmptyKey" />

 </Include>

<Delete>

</Registry>
```

**计算机范围的虚拟内核对象**

```XML

<Objects>

<NotIsolate>

   <Object Name="testObject" />

 </NotIsolate>

</Objects>
```

#### ProductSourceURLOptOut

使用 ProductSourceURLOptOut 指示程序包的 URL 可以通过_PackageSourceRoot_全局修改（以支持分支 office 方案）。 更改会在下一次启动时生效。 

```XML

<MachineConfiguration>

  ... 

  <ProductSourceURLOptOut Enabled="true" />

  ...

</MachineConfiguration>
```

#### MachineScripts

程序包可以配置为在部署、发布或删除时执行脚本。 若要查看示例脚本，请参阅由排序器生成的部署配置文件。 

下面的 "脚本" 部分提供了有关可以使用的各种触发器的详细信息。

#### TerminateChildProcess

可指定应用程序可执行文件，其子进程将在应用程序 exe 进程终止时终止。

```XML

<MachineConfiguration>

  ...   

  <TerminateChildProcesses>

    <Application Path="[{PackageRoot}]\Contoso\ContosoApp.EXE" />

    <Application Path="[{PackageRoot}]\LitView\LitViewBrowser.exe" />

    <Application Path="[{ProgramFilesX86}]\Microsoft Contoso\Contoso\contosomail.EXE" />

  </TerminateChildProcesses>

  ...

</MachineConfiguration>
```



## 脚本

下表描述了各种脚本事件和可以在其中运行它们的上下文。

| 脚本执行时间       | 可在部署配置中指定 | 可在 "用户配置" 中指定 | 可以在程序包的虚拟环境中运行 | 可以在特定应用程序的上下文中运行 | 在系统/用户上下文中运行：（部署配置、用户配置） |
|-----------------------------|----------------------------------------------|----------------------------------------|---------------------------------------------------|-----------------------------------------------------|-----------------------------------------------------------------------------|
| AddPackage                  | X                                            |                                        |                                                   |                                                     | （SYSTEM，N/A）                                                               |
| PublishPackage              | X                                            | X                                      |                                                   |                                                     | （系统、用户）                                                              |
| UnpublishPackage            | X                                            | X                                      |                                                   |                                                     | （系统、用户）                                                              |
| RemovePackage               | X                                            |                                        |                                                   |                                                     | （SYSTEM，N/A）                                                               |
| StartProcess                | X                                            | X                                      | X                                                 | X                                                   | （用户、用户）                                                                |
| ExitProcess                 | X                                            | X                                      |                                                   | X                                                   | （用户、用户）                                                                |
| StartVirtualEnvironment     | X                                            | X                                      | X                                                 |                                                     | （用户、用户）                                                                |
| TerminateVirtualEnvironment | X                                            | X                                      |                                                   |                                                     | （用户、用户）                                                                |

### 在单个事件触发器上使用多个脚本

App-v 5.1 支持在应用 V 程序包的单个事件触发器上使用多个脚本，包括从 App-v 4.6 转换到 App-v 5.0 或更高版本的程序包。 若要启用多个脚本的使用，App-v 5.1 使用一个名为 ScriptRunner.exe 的脚本启动器应用程序，该应用程序作为 App-v 客户端安装的一部分安装。

### 如何在单个事件触发器上使用多个脚本

对于要运行的每个脚本，将该脚本作为参数传递给 ScriptRunner.exe 应用程序。 然后，应用程序将单独运行每个脚本，以及为每个脚本指定的参数。 每个触发器仅使用一个脚本（ScriptRunner.exe）。

> [!NOTE]
> 
> 建议首先从命令提示符运行 "多脚本" 行，以确保所有参数都正确生成，然后再将它们添加到部署配置文件中。

### 示例脚本和参数说明

使用以下示例文件和表，修改部署或用户配置文件以添加要运行的脚本。

```XML
<MachineScripts>
 <AddPackage>
   <Path>ScriptRunner.exe</Path>
   <Arguments>
   -appvscript script1.exe arg1 arg2 –appvscriptrunnerparameters –wait –timeout=10
   -appvscript script2.vbs arg1 arg2
   -appvscript script3.bat arg1 arg2 –appvscriptrunnerparameters –wait –timeout=30 –rollbackonerror
   </Arguments>
   <Wait timeout=”40” RollbackOnError=”true”/>
 </AddPackage>
</MachineScripts>
```


**示例文件中的参数包括：**

#### \<AddPackage\>

正在运行脚本的事件触发器的名称，例如添加程序包或发布程序包。

#### \<Path\>ScriptRunner.exe\</Path\>

作为 App-V 客户端安装的一部分安装的脚本启动器应用程序。

> [!NOTE]
> 
> 尽管 ScriptRunner.exe 作为 App-v client 的一部分进行安装，但 app-v 客户端的位置必须在% path% 中，否则 ScriptRunner 将不会运行。 ScriptRunner.exe 通常位于 C:FilesApplication Virtualizationfolder 中。

#### \<Arguments\>

`-appvscript` -表示要运行的实际脚本的令牌。

`script1.exe` -要运行的脚本的名称。

`arg1 arg2` -要运行的脚本的参数。

`-appvscriptrunnerparameters` –表示 script1.exe 的执行选项的令牌。

`-wait` –通知 ScriptRunner 执行 script1.exe 完成，然后再继续下一个脚本的令牌。

`-timeout=x` -通知 ScriptRunner 在 x 秒后停止运行当前脚本的令牌。 所有其他指定的脚本仍将运行。

`-rollbackonerror` -通知 ScriptRunner 停止运行所有尚未运行的脚本的令牌，并将错误回退到 App-v 客户端。

#### \<Wait timeout=”40” RollbackOnError=”true”/\>

等待整个完成 ScriptRunner.exe。

将整个流道的超时值设置为大于或等于单个脚本上的超时值之和。

如果任何单个脚本报告了错误，并且 rollbackonerror 已设置为 true，则 ScriptRunner 会将错误报告给 App-v 客户端。

ScriptRunner 将运行其文件类型与计算机上安装的应用程序相关联的任何脚本。 如果缺少关联的应用程序，或者脚本的文件类型未与计算机上的任何应用程序关联，则脚本不会运行。

### 使用 app-v 5.1 清单文件创建动态配置文件

你可以使用以下三种方法之一创建动态配置文件：手动使用 App-v 5.1 管理控制台或对程序包进行排序，从而生成两个示例文件。 有关如何使用 App-v 5.1 管理控制台创建文件的详细信息，请参阅[如何使用 app-v 5.1 管理控制台创建自定义配置文件](how-to-create-a-custom-configuration-file-by-using-the-app-v-51-management-console.md)。

若要手动创建文件，上一节中的上述信息可以合并到单个文件中。 我们建议使用由排序器生成的文件。



- 在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。
- 对于 App-v 问题，请使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相关主题

- [如何使用 PowerShell 应用部署配置文件](how-to-apply-the-deployment-configuration-file-by-using-powershell51.md)

- [如何使用 PowerShell 应用用户配置文件](how-to-apply-the-user-configuration-file-by-using-powershell51.md)

- [App-V 5.1 的操作](operations-for-app-v-51.md)

---
