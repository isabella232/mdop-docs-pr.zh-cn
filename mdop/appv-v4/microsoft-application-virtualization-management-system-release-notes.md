---
title: Microsoft Application Virtualization 管理系统发行说明
description: Microsoft Application Virtualization 管理系统发行说明
author: dansimp
ms.assetid: e1a4d5ee-53c7-4b48-814c-a34ce0e698dc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: c34abab9a49bd69f760a9b531d0950cc581253c1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798916"
---
# Microsoft Application Virtualization 管理系统发行说明


若要搜索这些发行说明，请按 CTRL + F。

**重要提示** 在安装应用程序虚拟化管理系统之前，请仔细阅读这些发行说明。 这些发行说明包含成功安装应用程序虚拟化管理系统所需的信息。 本文档包含产品文档中不可用的信息。 如果这些发行说明和其他应用程序虚拟化管理系统文档之间存在差异，则应将最新更改视为权威。 这些发行说明取代了本产品附带的内容。

 

有关已知问题的更新信息，请访问 Microsoft TechNet 库 <https://go.microsoft.com/fwlink/?LinkId=122918> 。

## 关于 Microsoft Application Virtualization 4.5 累积更新1


这些发行说明已更新，以反映 Microsoft Application Virtualization 4.5 累积 Update1 （App-v 4.5 CU1）引入的更改，这些更改提供了对应用程序虚拟化（app-v）4.5 的最新更新。 此累积更新包含以下更改：

-   支持 Windows7 Beta 和 Windows Server2008R2 Beta： app-v 4.5 CU1 解决 Windows7 Beta 和 Windows Server2008R2 Beta 的兼容性问题。 将针对阻止 CU1 在预 RTM 版本的 Windows7 上运行的阻止应用的阻止问题提供支持。 这将帮助确保你的虚拟应用程序可以在测试环境中成功运行，其中需要使用 app-v 4.5 客户端与 Windows7 Beta 之间的兼容性。

    **重要提示** 不支持在实时操作环境中的任何版本的 Windows7 或 Windows Server2008R2 上运行 app-v 4.5 CU1。

     

-   改进了对 .NET Framework 序列化的支持： app-v 4.5 CU1 解决了在 WindowsXP （SP2 或更高版本）上排序 .NET Framework 3.5 和更早版本的以前出现的问题。 有关新功能的详细信息，请参阅 TechNet 文章 <https://go.microsoft.com/fwlink/?LinkId=123412> 。

-   客户反馈和修补程序汇总： app-v 4.5 CU1 还包括自 App-v 4.5 RTM 版本以来发现的解决问题的修补程序汇总。 这包括来自我们的内部团队、合作伙伴和使用 App-v 4.5 的客户的已知问题和客户反馈的组合。 有关包含的更新的完整列表，请参阅中的知识库文章 <https://go.microsoft.com/fwlink/?LinkId=141258> 。

## 关于产品文档


应用程序虚拟化（app-v）的综合文档可在 Microsoft TechNet 上的应用程序虚拟化（app-v）技术支持 <https://go.microsoft.com/fwlink/?LinkId=122939> 。 TechNet 文档包括应用程序虚拟化 Sequencer、应用程序虚拟化客户端和应用程序虚拟化服务器的联机帮助。 它还包括 "应用程序虚拟化规划和部署指南" 和 "应用程序虚拟化操作指南"。

## 防范安全漏洞和病毒


若要帮助防范安全漏洞和病毒，请务必为正在安装的任何新软件安装最新的可用安全更新。 有关详细信息，请参阅 Microsoft 安全性网站 <https://go.microsoft.com/fwlink/?LinkId=3482> 。

## 提供反馈


你可以通过 Microsoft Application Virtualization 技术中心（）上的社区论坛提供反馈、提出建议或报告 Microsoft Application Virtualization （App-v）管理系统的问题 <https://go.microsoft.com/fwlink/?LinkId=122917> 。

你还可以直接向 App-v 文档团队提供有关文档的反馈。 将文档反馈发送到 appvdocs@microsoft.com。

## 应用程序虚拟化 4.5 CU1 的已知问题


本部分提供有关 Microsoft Application Virtualization （app-v） 4.5 CU1 问题的最新信息。 这些问题不会显示在产品文档中，在某些情况下，可能会矛盾现有产品文档。 只要有可能，这些问题将在以后的版本中解决。

### 使用 setup.msi 将客户端安装或升级到 app-v 4.5 CU1 的指南

当使用 setup.msi 将 App-v 客户端安装或升级到 app-v 4.5 CU1 时，不会自动安装先决条件。

WORKAROUNDYou 必须先手动安装先决条件，然后再将 App-v 客户端安装或升级到 4.5 CU1。 有关安装先决条件和 App-v 客户端的详细过程，请参阅 <https://go.microsoft.com/fwlink/?LinkId=144106> 。

完成此操作后，使用具有提升权限的 setup.msi 安装 app-v 4.5 CU1 客户端。 此文件可在 Installers\\Client 文件夹中的 App-v 4.5 CU1 release 媒体上使用。

安装 Microsoft 应用程序错误报告时，如果你要安装或升级到 app-v 4.5 CU1 桌面客户端，请使用以下命令：

    msiexec /i dw20shared.msi APPGUID={FE495DBC-6D42-4698-B61F-86E655E0796D}  allusers=1 reboot=suppress REINSTALL=all REINSTALLMODE=vomus

或者，如果你要安装或升级到 app-v 4.5 CU1 终端服务客户端，请使用以下命令：

    msiexec /i dw20shared.msi APPGUID={8A97C241-D92A-47DC-B360-E716C1AAA929} allusers=1 reboot=suppress REINSTALL=all REINSTALLMODE=vomus

**注意** APPGUID 参数引用你安装或升级到的 app-v 客户端的产品代码。 产品代码对于每个 setup.msi 都是唯一的。 可以使用 Orca 数据库编辑器或类似工具检查 Windows 安装程序文件并确定产品代码。 此步骤对于 App-v 4.5 CU1 的所有安装或升级都是必需的。

 

### <a href="" id="some-applications-might-fail-to-install-during-the-monitoring-phase-when-sequencing-on-windows-7-beta--"></a>在 Windows7 Beta 上排序时，某些应用程序可能无法在监视阶段进行安装

当在 Windows7 Beta 或装有 Windows Installer 5.0 的计算机上进行排序时，某些应用程序可能无法在监视阶段安装。

WORKAROUNDYou 必须手动授予 Everyone 组对以下注册表项的 "完全控制" 权限：

    HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\SystemGuard

**重要提示** 必须使用 "**高级**" 按钮设置 "包括从该对象的父对象继承的权限" 选项。

 

### Windows7 Beta 上的排序时无法保存程序包

在 Windows7 Beta 上进行排序时，你可能无法保存已排序的程序包，因为发生共享冲突。

WORKAROUNDAs 在 Microsoft Application Virtualization 4.5 排序指南的 "最佳做法" 部分中指定（请参阅 <https://go.microsoft.com/fwlink/?LinkId=144108> ），在开始排序之前，必须关闭并禁用以下软件程序：

-   Windows Defender

-   防病毒软件

-   磁盘碎片整理软件

-   Windows 搜索

-   任何打开的 Windows 资源管理器会话

此外，如果在序列化工作站上运行 Microsoft 更新以在程序包更新过程中捕获更新，则需要在开始先后顺序之前添加 "C:\\Windows\\SoftwareDistribution" 作为 VFS 排除。

### 在序列化 .NET Framework 时提高性能

对 .NET Framework 进行排序时，你可能会遇到性能降低的系统性能，因为 Microsoft .NET Framework NGEN 服务尝试将程序集作为后台任务进行预编译。

WORKAROUNDWhen 序列化 .NET Framework 后，在完成监视阶段后禁用 Microsoft .NET Framework NGEN 服务（mscorsvw.exe）。 你必须使用 Sequencer 中的 "**虚拟服务**" 选项卡，并将启动类型更改为 "已禁用"。

### Windows7 任务栏的互操作性问题

在 Windows7 上运行应用程序虚拟化客户端时，Windows7 任务栏不会将虚拟应用程序的多个实例折叠到一个任务栏按钮中。 此外，右键单击虚拟应用程序的任务栏按钮时，不会显示跳转列表，除非应用程序已固定到 Windows7 任务栏。

### 卸载 Microsoft Application Virtualization 客户端时，将删除与执行卸载的用户相关联的用户设置

卸载 Microsoft Application Virtualization 客户端时，Windows Installer 将从当前用户的配置文件中删除应用程序虚拟化设置。 如果你的计算机使用漫游配置文件，请不要使用你的个人网络帐户卸载客户端，因为它将删除你的所有计算机上的虚拟应用程序的设置。

WORKAROUNDYou 应使用不用于运行虚拟应用程序的管理帐户来执行 App-v 客户端卸载。

### 在运行顺序向导时必须保存在虚拟文件系统和虚拟注册表选项卡上所做的编辑

如果打开程序包以执行升级，或者已使用新程序包运行顺序向导，并且在虚拟文件系统或虚拟注册表选项卡中对该包进行了更改，这些更改不会自动保存。

在重新运行向导之前 WORKAROUNDSave 更改，以确保它们反映在向导的虚拟环境中。

### 必须从提升的命令提示符运行命令行排序器

使用命令行排序器时，它不会提示提升。

使用提升的命令提示符 WORKAROUNDRun 命令行排序器。

### 分布式环境中的服务器管理控制台配置

如果需要将管理组件安装到主应用程序虚拟化发布和流式服务器之外的系统上，则服务器安装支持在正确配置的主应用程序虚拟化服务器的不同服务器上安装管理控制台和 Web 服务。

若要跨多台服务器分发管理组件，必须在安装了 Web 服务的服务器上启用 Kerberos 委派。

### OSD 文件中的短路径变量名称可能会导致错误

如果收到错误 450478-1F702339-0000010B "目录名称无效" 在客户端上启动虚拟应用程序时，OSD 中的变量可能设置错误。 如果应用程序的安装程序在排序期间设置短路径名，则可能会发生这种情况。

WORKAROUNDRemove OSD 文件中存在的任何 CSIDL 变量的尾随波形符。

### <a href="" id="correct-syntax-for-decodepath-parameter-for-command-line-sequencer-"></a>命令行 Sequencer 的 DECODEPATH 参数的正确语法

在命令行 Sequencer 中，打开要升级的程序包并将其解码到 Q 驱动器的根时， *DECODEPATH*参数的语法不应包含尾部斜杠。

WORKAROUNDYou 可以使用**Q：** 而不是**Q:\\** （省略结尾的 "\" 字符）。

### <a href="" id="when-upgrading-4-2-packages--you-encounter-problems-caused-by-windows-installer-files-in-the-virtual-file-system-"></a>升级4.2 程序包时，遇到由虚拟文件系统中的 Windows Installer 文件导致的问题

从4.2 升级程序包时，可能会遇到与在4.2 中和在序列化工作站上本地安装的 Windows installer 库中的 Windows Installer 系统文件不匹配的问题。 以下文件位于 CSIDL \ _SYSTEM \：

cabinet.dll

msi.dll

msiexec.exe

msihnd.dll

msimsg.dlll

从程序包中 WORKAROUNDDelete 前面的所有文件。 删除 " **VFS** " 选项卡上的映射以及解码路径中 CSIDL \ _SYSTEM 文件夹中的实际文件。

### <a href="" id="on-windows-xp--client-install-logging-is-not-enabled-by-default-"></a>在 WindowsXP 上，默认情况下不启用客户端安装日志记录

在安装客户端时，为了确保捕获任何安装错误以进行故障排除，应使用命令行启用日志记录。

WORKAROUNDAdd 参数 */l\ * vx！ log.txt*到命令行，如以下示例所示：

setup.exe/s/v "/qn/l\ * vx！ log.txt "

msiexec.exe/i setup.msi/qn/l\ * vx！ log.txt

或者，你可以将注册表项设置为以下值：

\ [HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Policies\\Microsoft\\Windows\\Installer\] "日志记录" = "voicewarmupx！"

### 要使 Kerberos 身份验证正常工作，必须为 IIS 注册服务主体名称（Spn）

当将 IIS 6.0 或7.0 用于图标或 OSD 文件检索以及程序包流时，必须按如下所示注册 Spn：

-   在 IIS 服务器上，使用 "SETSPN.EXE 资源工具包" 工具运行以下命令。 必须使用服务器完全限定的域名（FQDN）。

    Setspn-r SOFTGRID/ &lt; 服务器 FQDN&gt;

    Setspn-r HTTP/ &lt; 服务器 FQDN&gt;

有关详细信息，请参阅 <https://go.microsoft.com/fwlink/?LinkId=131407>。

### 从 RC 升级时，客户端日志的默认权限不允许非管理员用户访问日志以进行疑难解答和支持

应用程序 VirtualizationRC 客户端的客户端日志的默认权限不允许对日志文件进行非管理员访问，并且当客户端重新启动时，对这些日志权限的手动更改将被还原。 此功能已在适用于新客户端安装的 RTM 版本中得到更正，但在从 RC 升级时，不会重置现有日志文件上的自定义权限。 但是，当创建任何新日志或在日志重置后，这些文件将具有新的默认权限。

WORKAROUNDAfter 升级、重置现有客户端日志或手动更改其权限。

### .NET 兼容性更改

Microsoft Application Virtualization 累积 Update1 支持在 WindowsXP （SP2 或更高版本）上对 .NET Framework 进行排序。 在使用 app-v 4.5 排序器时，针对 SoftGrid 4.2 写入的 .NET 应用程序的排序例程可能需要更新。 有关详细信息和解决方法，请参阅知识文库文章 <https://go.microsoft.com/fwlink/?LinkId=123412> 。

### <a href="" id="after-client-upgrade-from-app-v-4-2--some-applications-are-not-shown-"></a>从 App-v 4.2 升级客户端后，某些应用程序不会显示

在日志中检查以下错误： "Application Virtualization 客户端无法解析 OSD 文件"。 Microsoft Application Virtualization 4.5 客户端筛选出包含包含空 OS 标记（ &lt; os &gt; &lt; /OS）的 OSD 文件的应用程序 &gt; 。

WORKAROUNDDelete OSD 文件中的空 OS 标签。

### 对于某些进程，app-v 服务器需要其防火墙中的免除

为使服务器正确流出应用程序，服务器的核心进程（包括调度程序）需要通过防火墙访问。

以下进程的服务器防火墙中的 WORKAROUNDSet 免除： sghwsvr.exe 和 sghwdsptr.exe。 这适用于 App-v 管理服务器和 App-v 流式处理服务器。

### 需要新的 Visual Basic 运行时的序列化程序包可能失败

如果在安装了较早版本的 VBruntime 的系统上对使用较新版本的 Visual Basic （VB）运行时序列化程序包，则当你尝试使用程序包时，可能会看到崩溃或其他意外行为。 例如，如果你尝试将 Microsoft Money2007 （使用 VBruntime 的版本6.00.9782）用于6.00.9690 的版本 VBruntime 的 WindowsXP 系统，则当你尝试在具有旧 WindowsXP 的其他 VBruntime 系统上运行时，你可能会在发票设计器中看到崩溃。

WORKAROUNDAfter 在序列化计算机上安装应用程序，但仍在监视时，将正确的（较新的） VBruntime 复制到程序包中从可执行文件开始的目录。 这允许序列化的应用程序在启动时查找 VBruntime 的预期版本。

**重要提示** 此问题已在 Microsoft Application Virtualization 4.5 累积 Update1 中得到修复。

 

### 当服务器安装程序在静默模式下运行时，它不会正确检查 MSXML6

App-v 管理服务器依赖于 MSXML6。 但是，如果你在静默模式下运行安装程序（例如，在尚未安装 MSXML6 的系统上使用命令 "msiexec-i setup.msi/qn"），则安装程序不会注意缺少的依赖项，也不会安装。 最常见的结果是，当客户尝试从 App-v 管理服务器刷新发布信息时，它们将看到失败。

WORKAROUNDVerify 在尝试安装 App-v 管理服务器的静默安装之前，系统上已安装 MSXML6。

### 尝试连接到应用程序虚拟化管理控制台时出现错误代码000C800

在应用程序虚拟化管理服务服务器上不是本地管理员的应用程序虚拟化管理员将在尝试连接到应用程序虚拟化管理控制台时收到错误（错误代码：000C800），并且 sftmmc 条目将指示对 SftMgmt 的访问权限被拒绝。 若要成功连接到应用程序虚拟化管理控制台，在应用程序虚拟化管理服务服务器上不是本地管理员的应用程序虚拟化管理员必须至少具有 SftMgmt 文件的 "读取" 和 "执行" 访问权限。

应用程序虚拟化管理员必须在%systemdrive%\\Program Files\\Microsoft System Center App Virt Management Server\\App Virt 管理服务 "下为 SftMgmt 文件授予" 读取 "和" 执行 "权限。

### 当与 KEEPCURRENTSETTINGS = 1 结合使用时，将忽略客户端安装程序命令行参数

与 KEEPCURRENTSETTINGS = 1 结合使用时，将忽略以下客户端安装程序命令行参数： SWICACHESIZE、MINFREESPACEMB、ALLOWINDEPENDENTFILESTREAMING、APPLICATIONSOURCEROOT、ICONSOURCEROOT、OSDSOURCEROOT、SYSTEMEVENTLOGLEVEL、SWIGLOBALDATA、DOTIMEOUTMINUTES、SWIFSDRIVE、AUTOLOADTARGET、AUTOLOADTRIGGERS、SWIUSERDATA 和 REQUIRESECURECONNECTION。

WORKAROUNDIf 要保留的设置，请使用 KEEPCURRENTSETTINGS = 1，然后在部署后设置其他参数。 App-v ADM 模板可用于设置以下客户端设置： APPLICATIONSOURCEROOT、ICONSOURCEROOT、OSDSOURCEROOT、AUTOLOADTARGET、AUTOLOADTRIGGERS、DOTIMEOUTMINUTES 和 ALLOWINDEPENDENTFILESTREAMING。 可以在上找到 ADM 模板 <https://go.microsoft.com/fwlink/?LinkId=121835> 。

### 通过 Symantec Endpoint Protection 初始化虚拟应用程序时出错

在启用了 "应用程序和设备控制" 功能的情况下使用 Symantec Endpoint Protection 时，虚拟应用程序可能无法启动，并出现错误 "应用程序未能正确初始化（0xc000007b）"。 有关详细信息和解决方法，请参阅知识文库文章 <https://go.microsoft.com/fwlink/?LinkId=125851> 。

**重要提示** 此问题已在 Microsoft Application Virtualization 4.5 累积 Update1 中得到修复。

 

## 发行说明版权信息


本文档中的信息（包括 URL 和其他 Internet 网站引用）如有更改，恕不另行通知，仅供参考。 本文档使用或结果的全部风险由用户承担，Microsoft Corporation 不作任何明示或暗示的保证。 此处所述的示例公司、组织、产品、人员和事件纯属虚构。 无意与任何真实公司、组织、产品、人员或事件关联，也不应进行任何推测。 用户有责任遵守所有适用的版权法。 在不限制版权法规定的权利的情况下，未经 Microsoft Corporation 明确书面允许，不得出于任何目的，以任何形式或通过任何方式（电子、机械、影印、录制或其他方式）对本文档中的任何内容进行复制、传输或者将其存储到或引入到检索系统。

Microsoft 可能拥有涉及本文档中的主题的专利、专利申请、商标、版权和其他知识产权。 除非得到 Microsoft 的明确书面许可，否则本文档不授予用户任何使用这些专利、商标、版权或其他知识产权的许可。



Microsoft、MS-DOS、Windows、WindowsServer、Windows Vista、Active Directory 和 ActiveSync 是 U.S.A. 和/或其他国家/地区的 MicrosoftCorporation 的注册商标或商标。

此处提及的真实公司和产品的名称可能是其各自所有者的商标。

 

 





