---
title: 如何转换在以前版本的 App-V 中创建的程序包
description: 如何转换在以前版本的 App-V 中创建的程序包
author: dansimp
ms.assetid: 3366d399-2891-491d-8de1-f8cfdf39bbab
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 402e64e3bdbc55eea1edb91d070bb7ebb11c912b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798525"
---
# 如何转换在以前版本的 App-V 中创建的程序包


你可以使用程序包转换器实用工具升级已使用早期版本的 App-v 创建的虚拟应用程序包。

**注意**  
如果您运行的是64位体系结构的计算机，则必须使用 PowerShell 的 x86 版本。



程序包转换器仅可直接转换使用 app-v 4.5 sequencer 或后续版本创建的程序包。 使用 app-v 4.5 之前的版本创建的程序包必须先升级到 app-v 4.5 或 App-v 4.6 格式，然后转换。

以下信息提供了转换现有虚拟应用程序包的方向。

**重要提示**  
必须配置程序包转换器，以始终将程序包成分文件保存到安全位置和目录。 安全位置只能由管理员访问。 此外，当你部署程序包时，应将程序包保存到安全的位置，或者确保在转换过程中不允许登录任何其他用户。



**将 app-v 4.6 安装文件夹重定向到虚拟文件系统根目录**

将程序包从 App-v 4.6 转换为5.1 时，App-v 5.1 程序包可以访问创建4.6 程序包时需要使用的硬编码的驱动器。 驱动器号将是您选择的驱动器作为4.6 排序计算机上的安装驱动器。 （默认驱动器号为 Q:\\.）

在 app-v 5.1 之前，无法识别4.6 根文件夹，并且无法通过 app-v 5.0 程序包访问该文件夹。 现在，App-v 5.1 程序包可以通过其完整路径访问硬编码文件，也可以通过编程方式枚举 App-v 4.6 安装根下的文件。

**技术详细信息：** App-v 5.1 程序包转换器将在 Filesystem 元素的 FilesystemMetadata.xml 文件中保存 App-v 4.6 安装根文件夹和短文件夹名称。 当 App-v 5.1 客户端创建虚拟进程时，它会将请求从 App-v 4.6 安装根映射到虚拟文件系统根目录。

**即刻体验**

1.  在环境中的计算机上安装 app-v Sequencer。 有关如何安装 Sequencer 的信息，请参阅[如何安装 sequencer](how-to-install-the-sequencer-51beta-gb18030.md)。

2.  

    以下 cmdlet 可用：

    -   AppvLegacyPackage-此 cmdlet 旨在检查程序包。 它将返回有关程序包的任何失败的信息，如缺失**的 sft**文件、无效的源、 **osd**文件错误或无效的程序包版本。 此 cmdlet 不会分析该**sft**文件或执行任何深入的验证。 有关此 cmdlet 的选项和基本功能的信息，请使用 PowerShell cmdline 键入 `Test-AppvLegacyPackage -?` 。

    -   ConvertFrom-AppvLegacyPackage-若要转换现有程序包，请键入 `ConvertFrom-AppvLegacyPackage c:\contentStore c:\convertedPackages` 。 在此命令中， `c:\contentStore` 表示现有程序包的位置，并且 `c:\convertedPackages` 是将保存所生成的 app-v 5.1 虚拟应用程序包文件的输出目录。 默认情况下，如果不指定新名称，将为 app-v 5.1 文件名使用旧的程序包名称。

        此外，程序包转换器通过将程序包设置为对 App-v 程序包进行流故障来优化 app-v 5.1 中的程序包性能。  这比主要功能块更具性能，并且完全下载程序包。 标志**DownloadFullPackageOnFirstLaunch**允许你转换程序包，并将程序包默认设置为完全下载。

        **注意**  
        在指定输出目录之前，必须创建输出目录。



~~~
**Advanced Conversion Tips**

-   Piping - PowerShell supports piping. Piping allows you to call `dir c:\contentStore\myPackage | Test-AppvLegacyPackage`. In this example, the directory object that represents `myPackage` will be given as input to the `Test-AppvLegacyPackage` command and bound to the `-Source` parameter. Piping like this is especially useful when you want to batch commands together; for example, `dir .\ | Test-AppvLegacyPackage | ConvertFrom-AppvLegacyAppvPackage -Target .\ConvertedPackages`. This piped command would test the packages and then pass those objects on to actually be converted. You can also apply a filter on packages without errors or only specify a directory which contains an **.sprj** file or pipe them to another cmdlet that adds the filtered package to the server or publishes them to the App-V 5.1 client.

-   Batching - The PowerShell command enables batching. More specifically, the cmdlets support taking a string\[\] object for the `-Source` parameter which represents a list of directory paths. This allows you to enter `$packages = dir c:\contentStore` and then call `ConvertFrom-AppvLegacyAppvPackage-Source $packages -Target c:\ConvertedPackages` or to use piping and call `dir c:\ContentStore | ConvertFrom-AppvLegacyAppvPackage -Target C:\ConvertedPackages`.

-   Other functionality - PowerShell has other built-in functionality for features such as aliases, piping, lazy-binding, .NET object, and many others. All of these are usable in PowerShell and can help you create advanced scenarios for the Package Converter.

**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## 相关主题


[App-V 5.1 的操作](operations-for-app-v-51.md)









