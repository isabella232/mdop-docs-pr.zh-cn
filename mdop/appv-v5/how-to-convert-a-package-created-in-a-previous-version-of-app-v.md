---
title: 如何转换在以前版本的 App-V 中创建的程序包
description: 如何转换在以前版本的 App-V 中创建的程序包
author: dansimp
ms.assetid: b092a5f8-cc5f-4df8-a5a2-0a68fd7bd5b2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3bd0d5db7cb406a5a7fe67c69ff77461cce2b0a9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798526"
---
# <span data-ttu-id="694bb-103">如何转换在以前版本的 App-V 中创建的程序包</span><span class="sxs-lookup"><span data-stu-id="694bb-103">How to Convert a Package Created in a Previous Version of App-V</span></span>


<span data-ttu-id="694bb-104">你可以使用程序包转换器实用工具升级已使用早期版本的 App-v 创建的虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="694bb-104">You can use the package converter utility to upgrade virtual application packages that have been created with previous versions of App-V.</span></span>

**<span data-ttu-id="694bb-105">注意</span><span class="sxs-lookup"><span data-stu-id="694bb-105">Note</span></span>**  
<span data-ttu-id="694bb-106">如果您运行的是64位体系结构的计算机，则必须使用 PowerShell 的 x86 版本。</span><span class="sxs-lookup"><span data-stu-id="694bb-106">If you are running a computer with a 64-bit architecture, you must use the x86 version of PowerShell.</span></span>



<span data-ttu-id="694bb-107">程序包转换器仅可直接转换使用 app-v 4.5 sequencer 或后续版本创建的程序包。</span><span class="sxs-lookup"><span data-stu-id="694bb-107">The package converter can only directly convert packages that were created by using the App-V 4.5 sequencer or a subsequent version.</span></span> <span data-ttu-id="694bb-108">使用 app-v 4.5 之前的版本创建的程序包必须先升级到 app-v 4.5 或 App-v 4.6 格式，然后转换。</span><span class="sxs-lookup"><span data-stu-id="694bb-108">Packages that were created using a version prior to App-V 4.5 must be upgraded to the App-V 4.5 or App-V 4.6 format before conversion.</span></span>

<span data-ttu-id="694bb-109">以下信息提供了转换现有虚拟应用程序包的方向。</span><span class="sxs-lookup"><span data-stu-id="694bb-109">The following information provides direction for converting existing virtual application packages.</span></span>

**<span data-ttu-id="694bb-110">重要提示</span><span class="sxs-lookup"><span data-stu-id="694bb-110">Important</span></span>**  
<span data-ttu-id="694bb-111">必须配置程序包转换器，以始终将程序包成分文件保存到安全位置和目录。</span><span class="sxs-lookup"><span data-stu-id="694bb-111">You must configure the package converter to always save the package ingredients file to a secure location and directory.</span></span> <span data-ttu-id="694bb-112">安全位置只能由管理员访问。</span><span class="sxs-lookup"><span data-stu-id="694bb-112">A secure location is accessible only by an administrator.</span></span> <span data-ttu-id="694bb-113">此外，当你部署程序包时，应将程序包保存到安全的位置，或者确保在转换过程中不允许登录任何其他用户。</span><span class="sxs-lookup"><span data-stu-id="694bb-113">Additionally, when you deploy the package, you should save the package to a location that is secure, or make sure that no other user is allowed to be logged in during the conversion process.</span></span>



**<span data-ttu-id="694bb-114">即刻体验</span><span class="sxs-lookup"><span data-stu-id="694bb-114">Getting started</span></span>**

1.  <span data-ttu-id="694bb-115">在环境中的计算机上安装 app-v Sequencer。</span><span class="sxs-lookup"><span data-stu-id="694bb-115">Install the App-V Sequencer on a computer in your environment.</span></span> <span data-ttu-id="694bb-116">有关如何安装 Sequencer 的信息，请参阅[如何安装 sequencer](how-to-install-the-sequencer-beta-gb18030.md)。</span><span class="sxs-lookup"><span data-stu-id="694bb-116">For information about how to install the Sequencer, see [How to Install the Sequencer](how-to-install-the-sequencer-beta-gb18030.md).</span></span>

2. <span data-ttu-id="694bb-117">导入所需的 Powershell 模块</span><span class="sxs-lookup"><span data-stu-id="694bb-117">Import the required Powershell Module</span></span>

```powershell
Import-Module AppVPkgConverter
```

3. <span data-ttu-id="694bb-118">以下 cmdlet 可用：</span><span class="sxs-lookup"><span data-stu-id="694bb-118">The following cmdlets are available:</span></span>

   -   <span data-ttu-id="694bb-119">AppvLegacyPackage-此 cmdlet 旨在检查程序包。</span><span class="sxs-lookup"><span data-stu-id="694bb-119">Test-AppvLegacyPackage – This cmdlet is designed to check packages.</span></span> <span data-ttu-id="694bb-120">它将返回有关程序包的任何失败的信息，如缺失**的 sft**文件、无效的源、 **osd**文件错误或无效的程序包版本。</span><span class="sxs-lookup"><span data-stu-id="694bb-120">It will return information about any failures with the package such as missing **.sft** files, an invalid source, **.osd** file errors, or invalid package version.</span></span> <span data-ttu-id="694bb-121">此 cmdlet 不会分析该**sft**文件或执行任何深入的验证。</span><span class="sxs-lookup"><span data-stu-id="694bb-121">This cmdlet will not parse the **.sft** file or do any in depth validation.</span></span> <span data-ttu-id="694bb-122">有关此 cmdlet 的选项和基本功能的信息，请使用 PowerShell cmdline 键入 `Test-AppvLegacyPackage -?` 。</span><span class="sxs-lookup"><span data-stu-id="694bb-122">For information about options and basic functionality for this cmdlet, using the PowerShell cmdline, type `Test-AppvLegacyPackage -?`.</span></span>

   -   <span data-ttu-id="694bb-123">ConvertFrom-AppvLegacyPackage-若要转换现有程序包，请键入 `ConvertFrom-AppvLegacyPackage c:\contentStore c:\convertedPackages` 。</span><span class="sxs-lookup"><span data-stu-id="694bb-123">ConvertFrom-AppvLegacyPackage – To convert an existing package, type `ConvertFrom-AppvLegacyPackage c:\contentStore c:\convertedPackages`.</span></span> <span data-ttu-id="694bb-124">在此命令中， `c:\contentStore` 表示现有程序包的位置，并且 `c:\convertedPackages` 是将保存所生成的 app-v 5.0 虚拟应用程序包文件的输出目录。</span><span class="sxs-lookup"><span data-stu-id="694bb-124">In this command, `c:\contentStore` represents the location of the existing package and `c:\convertedPackages` is the output directory to which the resulting App-V 5.0 virtual application package file will be saved.</span></span> <span data-ttu-id="694bb-125">默认情况下，如果不指定新名称，将为 app-v 5.0 文件名使用旧的程序包名称。</span><span class="sxs-lookup"><span data-stu-id="694bb-125">By default, if you do not specify a new name, the old package name will be used for the App-V 5.0 filename.</span></span>

       <span data-ttu-id="694bb-126">此外，程序包转换器通过将程序包设置为对 App-v 程序包进行流故障来优化 app-v 5.0 中的程序包性能。</span><span class="sxs-lookup"><span data-stu-id="694bb-126">Additionally, the package converter optimizes performance of packages in App-V 5.0 by setting the package to stream fault the App-V package.</span></span>  <span data-ttu-id="694bb-127">这比主要功能块更具性能，并且完全下载程序包。</span><span class="sxs-lookup"><span data-stu-id="694bb-127">This is more performant than the primary feature block and fully downloading the package.</span></span> <span data-ttu-id="694bb-128">标志**DownloadFullPackageOnFirstLaunch**允许你转换程序包，并将程序包默认设置为完全下载。</span><span class="sxs-lookup"><span data-stu-id="694bb-128">The flag **DownloadFullPackageOnFirstLaunch** allows you to convert the package and set the package to be fully downloaded by default.</span></span>

       **<span data-ttu-id="694bb-129">注意</span><span class="sxs-lookup"><span data-stu-id="694bb-129">Note</span></span>**  
       <span data-ttu-id="694bb-130">在指定输出目录之前，必须创建输出目录。</span><span class="sxs-lookup"><span data-stu-id="694bb-130">Before you specify the output directory, you must create the output directory.</span></span>



~~~
**Advanced Conversion Tips**

-   Piping - PowerShell supports piping. Piping allows you to call `dir c:\contentStore\myPackage | Test-AppvLegacyPackage`. In this example, the directory object that represents `myPackage` will be given as input to the `Test-AppvLegacyPackage` command and bound to the `-Source` parameter. Piping like this is especially useful when you want to batch commands together; for example, `dir .\ | Test-AppvLegacyPackage | ConvertFrom-AppvLegacyAppvPackage -Target .\ConvertedPackages`. This piped command would test the packages and then pass those objects on to actually be converted. You can also apply a filter on packages without errors or only specify a directory which contains an **.sprj** file or pipe them to another cmdlet that adds the filtered package to the server or publishes them to the App-V 5.0 client.

-   Batching - The PowerShell command enables batching. More specifically, the cmdlets support taking a string\[\] object for the `-Source` parameter which represents a list of directory paths. This allows you to enter `$packages = dir c:\contentStore` and then call `ConvertFrom-AppvLegacyAppvPackage-Source $packages -Target c:\ConvertedPackages` or to use piping and call `dir c:\ContentStore | ConvertFrom-AppvLegacyAppvPackage -Target C:\ConvertedPackages`.

-   Other functionality - PowerShell has other built-in functionality for features such as aliases, piping, lazy-binding, .NET object, and many others. All of these are usable in PowerShell and can help you create advanced scenarios for the Package Converter.

**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## <span data-ttu-id="694bb-131">相关主题</span><span class="sxs-lookup"><span data-stu-id="694bb-131">Related topics</span></span>


[<span data-ttu-id="694bb-132">App-V 5.0 的操作</span><span class="sxs-lookup"><span data-stu-id="694bb-132">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)









