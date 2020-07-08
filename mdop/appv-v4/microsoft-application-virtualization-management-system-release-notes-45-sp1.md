---
title: Microsoft Application Virtualization 管理系统发行说明 4.5 SP1
description: Microsoft Application Virtualization 管理系统发行说明 4.5 SP1
author: dansimp
ms.assetid: 5d6b11ea-7b87-4084-9a7c-0d831f247aa3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 5c24d2e98ad09460ca22e4b29d75ae2b9c72d0bf
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798915"
---
# Microsoft Application Virtualization 管理系统发行说明 4.5 SP1


若要搜索这些发行说明，请按 CTRL + F。

**重要提示** 在安装应用程序虚拟化管理系统之前，请仔细阅读这些发行说明。 这些发行说明包含成功安装应用程序虚拟化管理系统所需的信息。 这些发行说明包含产品文档中不可用的信息。 如果这些发行说明和其他应用程序虚拟化管理系统文档之间存在差异，则应将最新更改视为权威。

 

有关已知问题的更新信息，请访问 Microsoft TechNet 库 <https://go.microsoft.com/fwlink/?LinkId=122918> 。

## 关于 Microsoft Application Virtualization 4.5 Service Pack 1


这些发行说明已更新，以反映 Microsoft Application Virtualization （app-v） 4.5 Service Pack1 （SP1）引入的更改。 此服务包包含以下更改：

-   支持 Windows 7 和 Windows Server 2008 R2： app-v 4.5 SP1 提供对 Windows 7 和 Windows Server 2008 R2 的支持，包括对 Windows 7 功能（如任务栏、AppLocker、BranchCache 和 BitLocker To Go）的支持。Windows Server 2008 R2 支持仅适用于应用程序虚拟化服务器。 有关 Windows 7 中的 AppLocker 支持的详细信息，请参阅 <https://go.microsoft.com/fwlink/?LinkID=156732> 。

-   对第三方 Kerberos 领域的支持： app-v 4.5 SP1 提供对以下环境的支持：具有信任关系和在 Windows 域和 MIT Kerberos 领域之间映射的用户帐户（这是许多大学的常见方案）。 有关如何启用此支持的信息，请访问 Microsoft TechNet 库 <https://go.microsoft.com/fwlink/?LinkId=166004> 。

-   改进了对应用程序发布和通过 HTTP/HTTPS 进行流式处理的支持： app-v 4.5 SP1 通过 HTTP/HTTPS 协议（适用于 Windows XP 家庭版）、Windows Vista 家庭普通版和 Windows 7 家庭普通版提供对应用程序发布和流处理的支持。

-   客户反馈和修补程序汇总： app-v 4.5 SP1 还包括一个累积修补程序，用于解决自 Microsoft Application Virtualization （app-v） 4.5 CU1 发布以来发现的问题。 更新是由我们的内部团队、合作伙伴和使用 App-v 4.5 的客户的已知问题和客户反馈组合导致的。 有关更新的完整列表，请参阅中的知识库文章 <https://go.microsoft.com/fwlink/?LinkId=167121> 。

## 关于产品文档


应用程序虚拟化（app-v）的综合文档可在 Microsoft TechNet 上的应用程序虚拟化（app-v）技术支持 <https://go.microsoft.com/fwlink/?LinkId=122939> 。 TechNet 文档包括应用程序虚拟化 Sequencer、应用程序虚拟化客户端和应用程序虚拟化服务器的联机帮助。 它还包括 "应用程序虚拟化规划和部署指南" 和 "应用程序虚拟化操作指南"。

## 防范安全漏洞和病毒


为了帮助防范安全漏洞和病毒，我们建议你为正在安装的任何新软件安装最新的可用安全更新。 有关详细信息，请参阅 Microsoft 安全性网站 <https://go.microsoft.com/fwlink/?LinkId=3482> 。

## 提供反馈


你可以通过 Microsoft Application Virtualization 技术中心（）上的社区论坛提供反馈、提出建议或报告 Microsoft Application Virtualization （App-v）管理系统的问题 <https://go.microsoft.com/fwlink/?LinkId=122917> 。

你还可以直接向 App-v 文档团队提供有关文档的反馈。 将文档反馈发送到 appvdocs@microsoft.com。

## 应用程序虚拟化 4.5 SP1 的已知问题


本部分提供有关 Microsoft Application Virtualization （app-v） 4.5 SP1 问题的最新信息。 这些问题不会显示在产品文档中，在某些情况下，可能会矛盾现有产品文档。 只要有可能，这些问题将在本软件的后续版本中解决。

### 服务器管理控制台安装指南

如果需要将管理软件安装到主应用程序虚拟化发布和流式服务器以外的系统上，服务器安装支持在不同的服务器上从主 App-v 管理服务器安装管理控制台和管理 Web 服务。 若要跨多台服务器分发管理组件，必须在安装了 Web 服务的服务器上启用 Kerberos 委派。 有关如何启用此支持的信息，请访问 Microsoft TechNet 库 <https://go.microsoft.com/fwlink/?LinkId=166682>

### 使用 setup.msi 安装或升级客户端到 App-v 4.5 SP1 的指南

当使用 setup.msi 将 App-v 客户端安装或升级到 app-v 4.5 SP1 时，不会自动安装先决条件。

WORKAROUNDYou 必须先手动安装先决条件，然后再安装或升级 app-v client toApp-V 4.5 SP1。 有关安装先决条件和 App-v 客户端的详细过程，请参阅 <https://go.microsoft.com/fwlink/?LinkId=144106> 。

完成此操作后，使用具有提升权限的 setup.msi 安装 app-v 4.5 SP1 客户端。 此文件可在 Installers\\Client 文件夹中的 App-v 4.5 SP1 版本媒体上使用。

安装 Microsoft 应用程序错误报告时，如果你要安装或升级到 app-v 4.5 SP1 桌面客户端，请使用以下命令：

    msiexec /i dw20shared.msi APPGUID={93468B43-C19D-44F9-8BCC-114076DB0443}  allusers=1 reboot=suppress REINSTALL=all REINSTALLMODE=vomus

或者，如果你要为远程桌面服务（以前称为 "终端服务"）安装或升级到 app-v 4.5 SP1 客户端，请使用以下命令：

    msiexec /i dw20shared.msi APPGUID={0042AD3C-99A4-4E58-B5F0-744D5AD96E1C} allusers=1 reboot=suppress REINSTALL=all REINSTALLMODE=vomus

**注意** APPGUID 参数引用你安装或升级的 app-v 客户端的产品代码。 产品代码对于每个 setup.msi 都是唯一的。 你可以使用 Orca 数据库编辑器或类似工具检查 Windows Installer 文件并确定产品代码。 对于 App-v 4.5 SP1 的所有安装或升级，此步骤是必需的。

 

### 在序列化 .NET Framework 时提高性能

对 .NET Framework 进行排序时，你可能会遇到性能降低的系统性能，因为 Microsoft .NET Framework NGEN 服务尝试将程序集作为后台任务进行预编译。

WORKAROUNDWhen 序列化 .NET Framework 后，在完成监视阶段后禁用 Microsoft .NET Framework NGEN 服务（mscorsvw.exe）。 你必须使用 Sequencer 中的 "**虚拟服务**" 选项卡，并将启动类型更改为 "已禁用"。

### 卸载 Microsoft Application Virtualization 客户端时，将删除与执行卸载的用户相关联的用户设置

卸载 app-v 客户端时，Windows Installer 将从当前用户的配置文件中删除应用程序虚拟化设置。 如果你的计算机使用漫游配置文件，请不要使用你的个人网络帐户卸载客户端，因为它将删除你的所有计算机上的虚拟应用程序的设置。

WORKAROUNDYou 应使用不用于运行虚拟应用程序的管理帐户来执行 App-v 客户端卸载。

### 在运行顺序向导时必须保存在虚拟文件系统和虚拟注册表选项卡上所做的编辑

如果打开程序包以执行升级，或者如果已使用新程序包运行顺序向导，并且在虚拟文件系统或虚拟注册表选项卡中对程序包进行了更改，这些更改不会自动保存。

在重新运行向导之前 WORKAROUNDSave 更改，以确保它们反映在向导的虚拟环境中。

### 必须从提升的命令提示符运行命令行排序器

使用命令行排序器时，它不会提示提升。

使用提升的命令提示符 WORKAROUNDRun 命令行排序器。

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

### .NET 兼容性更改

Microsoft Application Virtualization （App-v）累积 Update1 或更高版本支持对 WindowsXP （SP2 或更高版本）上的 .NET Framework 进行排序。 当与 App-v 4.5 Sequencer 一起使用时，针对 SoftGrid 4.2 写入的 .NET 应用程序的排序例程可能需要更新。 有关详细信息和解决方法，请参阅知识文库文章 <https://go.microsoft.com/fwlink/?LinkId=123412> 。

### <a href="" id="after-client-upgrade-from-app-v-4-2--some-applications-are-not-shown-"></a>从 App-v 4.2 升级客户端后，某些应用程序不会显示

在日志中检查以下错误： "Application Virtualization 客户端无法解析 OSD 文件"。 App-v 4.5 客户端筛选出包含包含空 OS 标记（ &lt; os &gt; &lt; /OS）的 OSD 文件的应用程序 &gt; 。

WORKAROUNDDelete OSD 文件中的空 OS 标签。

### 对于某些进程，app-v 服务器需要其防火墙中的免除

为使服务器正确流出应用程序，服务器的核心进程（包括调度程序）需要通过防火墙访问。

以下进程的服务器防火墙中的 WORKAROUNDSet 免除： sghwsvr.exe 和 sghwdsptr.exe。 这适用于 App-v 管理服务器和 App-v 流式处理服务器。

### 当服务器安装程序在静默模式下运行时，它不会正确检查 MSXML6

App-v 管理服务器依赖于 MSXML6。 但是，如果你在静默模式下运行安装程序（例如，在尚未安装 MSXML6 的系统上使用命令 "msiexec-i setup.msi/qn"），则安装程序不会检测缺少的依赖项，也不会安装。 因此，当客户尝试从 App-v 管理服务器刷新发布信息时，它们将看到失败。

WORKAROUNDVerify 在尝试安装 App-v 管理服务器的静默安装之前，系统上已安装 MSXML6。

### 尝试连接到应用程序虚拟化管理控制台时出现错误代码000C800

如果应用程序虚拟化管理员的应用程序虚拟化管理员在尝试连接到 app-v 管理控制台时将收到错误（错误代码：000C800），并且 sftmmc 项将指示对 SftMgmt 的访问权限被拒绝了。 若要成功连接到 app-v 管理控制台，没有对 app-v 管理 Web 服务服务器具有本地管理员权限的管理员必须至少拥有 SftMgmt 文件的 "读取" 和 "执行" 权限。

应用程序虚拟化管理员必须在%systemdrive%\\Program Files\\Microsoft System Center App Virt Management Server\\App Virt 管理服务 "下为 SftMgmt 文件授予" 读取 "和" 执行 "权限。

### 当与 KEEPCURRENTSETTINGS = 1 结合使用时，将忽略客户端安装程序命令行参数

与 KEEPCURRENTSETTINGS = 1 结合使用时，将忽略以下客户端安装程序命令行参数： SWICACHESIZE、MINFREESPACEMB、ALLOWINDEPENDENTFILESTREAMING、APPLICATIONSOURCEROOT、ICONSOURCEROOT、OSDSOURCEROOT、SYSTEMEVENTLOGLEVEL、SWIGLOBALDATA、DOTIMEOUTMINUTES、SWIFSDRIVE、AUTOLOADTARGET、AUTOLOADTRIGGERS、SWIUSERDATA 和 REQUIRESECURECONNECTION。

WORKAROUNDIf 要保留的设置，请使用 KEEPCURRENTSETTINGS = 1，然后在部署后设置其他参数。 App-v ADM 模板可用于设置以下客户端设置： APPLICATIONSOURCEROOT、ICONSOURCEROOT、OSDSOURCEROOT、AUTOLOADTARGET、AUTOLOADTRIGGERS、DOTIMEOUTMINUTES 和 ALLOWINDEPENDENTFILESTREAMING。 可以在上找到 ADM 模板 <https://go.microsoft.com/fwlink/?LinkId=121835> 。

## 发行说明版权信息


本文档中的信息（包括 URL 和其他互联网网站引用）如有更改，恕不另行通知，仅供参考之用。 本文档使用或导致的全部风险由用户承担，Microsoft Corporation 不作任何明示或暗示保证。 除非另有说明，否则此处的示例中所描述的公司、组织、产品、域名、电子邮件地址、徽标、人员、地点和事件均属虚构。 无意与任何真实公司、组织、产品、域名、电子邮件地址、徽标、人员、地点或事件相关联，也不应进行推断。 用户有责任遵守所有适用的版权法。 在不限制版权法规定的权利的情况下，未经 Microsoft Corporation 明确书面允许，不得出于任何目的，以任何形式或通过任何方式（电子、机械、影印、录制或其他方式）对本文档中的任何内容进行复制、传输或者将其存储到或引入到检索系统。

Microsoft 可能拥有涉及本文档中的主题的专利、专利申请、商标、版权和其他知识产权。 除非得到 Microsoft 的明确书面许可，否则本文档不授予用户任何使用这些专利、商标、版权或其他知识产权的许可。



Microsoft、Active Directory、ActiveSync、MS-DOS、Windows、WindowsServer 和 Windows Vista 是 Microsoft 公司组的商标。

所有其他商标的所有权属于其各自所有者。

 

 





