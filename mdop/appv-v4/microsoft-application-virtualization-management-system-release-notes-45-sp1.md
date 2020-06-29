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
# <span data-ttu-id="3003d-103">Microsoft Application Virtualization 管理系统发行说明 4.5 SP1</span><span class="sxs-lookup"><span data-stu-id="3003d-103">Microsoft Application Virtualization Management System Release Notes 4.5 SP1</span></span>


<span data-ttu-id="3003d-104">若要搜索这些发行说明，请按 CTRL + F。</span><span class="sxs-lookup"><span data-stu-id="3003d-104">To search these Release Notes, press CTRL+F.</span></span>

<span data-ttu-id="3003d-105">**重要提示** 在安装应用程序虚拟化管理系统之前，请仔细阅读这些发行说明。</span><span class="sxs-lookup"><span data-stu-id="3003d-105">**Important** Read these Release Notes thoroughly before you install the Application Virtualization Management System.</span></span> <span data-ttu-id="3003d-106">这些发行说明包含成功安装应用程序虚拟化管理系统所需的信息。</span><span class="sxs-lookup"><span data-stu-id="3003d-106">These Release Notes contain information that you need to successfully install the Application Virtualization Management System.</span></span> <span data-ttu-id="3003d-107">这些发行说明包含产品文档中不可用的信息。</span><span class="sxs-lookup"><span data-stu-id="3003d-107">These Release Notes contain information that is not available in the product documentation.</span></span> <span data-ttu-id="3003d-108">如果这些发行说明和其他应用程序虚拟化管理系统文档之间存在差异，则应将最新更改视为权威。</span><span class="sxs-lookup"><span data-stu-id="3003d-108">If there is a discrepancy between these Release Notes and other Application Virtualization Management System documentation, the latest change should be considered authoritative.</span></span>

 

<span data-ttu-id="3003d-109">有关已知问题的更新信息，请访问 Microsoft TechNet 库 <https://go.microsoft.com/fwlink/?LinkId=122918> 。</span><span class="sxs-lookup"><span data-stu-id="3003d-109">For updated information about known issues, please visit the Microsoft TechNet Library at <https://go.microsoft.com/fwlink/?LinkId=122918>.</span></span>

## <span data-ttu-id="3003d-110">关于 Microsoft Application Virtualization 4.5 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="3003d-110">About Microsoft Application Virtualization 4.5 Service Pack 1</span></span>


<span data-ttu-id="3003d-111">这些发行说明已更新，以反映 Microsoft Application Virtualization （app-v） 4.5 Service Pack1 （SP1）引入的更改。</span><span class="sxs-lookup"><span data-stu-id="3003d-111">These Release Notes have been updated to reflect the changes introduced with Microsoft Application Virtualization (App-V)4.5 Service Pack1 (SP1).</span></span> <span data-ttu-id="3003d-112">此服务包包含以下更改：</span><span class="sxs-lookup"><span data-stu-id="3003d-112">This service pack contains the following changes:</span></span>

-   <span data-ttu-id="3003d-113">支持 Windows 7 和 Windows Server 2008 R2： app-v 4.5 SP1 提供对 Windows 7 和 Windows Server 2008 R2 的支持，包括对 Windows 7 功能（如任务栏、AppLocker、BranchCache 和 BitLocker To Go）的支持。</span><span class="sxs-lookup"><span data-stu-id="3003d-113">Support for Windows 7 and Windows Server 2008 R2: App-V 4.5 SP1 provides support for Windows 7 and Windows Server 2008 R2, including support for Windows 7 features such as the taskbar, AppLocker, BranchCache, and BitLocker To Go.</span></span><span data-ttu-id="3003d-114">Windows Server 2008 R2 支持仅适用于应用程序虚拟化服务器。</span><span class="sxs-lookup"><span data-stu-id="3003d-114"> Windows Server 2008 R2 support is for the Application Virtualization Server only.</span></span> <span data-ttu-id="3003d-115">有关 Windows 7 中的 AppLocker 支持的详细信息，请参阅 <https://go.microsoft.com/fwlink/?LinkID=156732> 。</span><span class="sxs-lookup"><span data-stu-id="3003d-115">For more information on AppLocker support in Windows 7, see <https://go.microsoft.com/fwlink/?LinkID=156732>.</span></span>

-   <span data-ttu-id="3003d-116">对第三方 Kerberos 领域的支持： app-v 4.5 SP1 提供对以下环境的支持：具有信任关系和在 Windows 域和 MIT Kerberos 领域之间映射的用户帐户（这是许多大学的常见方案）。</span><span class="sxs-lookup"><span data-stu-id="3003d-116">Support for 3rd Party Kerberos Realms: App-V 4.5 SP1 provides support for environments that have a trust relationship and mapped user accounts between a Windows domain and an MIT Kerberos realm, which is a scenario that is common at many universities.</span></span> <span data-ttu-id="3003d-117">有关如何启用此支持的信息，请访问 Microsoft TechNet 库 <https://go.microsoft.com/fwlink/?LinkId=166004> 。</span><span class="sxs-lookup"><span data-stu-id="3003d-117">For information on how to enable this support, please visit the Microsoft TechNet Library at <https://go.microsoft.com/fwlink/?LinkId=166004>.</span></span>

-   <span data-ttu-id="3003d-118">改进了对应用程序发布和通过 HTTP/HTTPS 进行流式处理的支持： app-v 4.5 SP1 通过 HTTP/HTTPS 协议（适用于 Windows XP 家庭版）、Windows Vista 家庭普通版和 Windows 7 家庭普通版提供对应用程序发布和流处理的支持。</span><span class="sxs-lookup"><span data-stu-id="3003d-118">Improved support for application publishing and streaming via HTTP/HTTPS: App-V 4.5 SP1 provides support for application publishing and streaming via the HTTP/HTTPS protocols for Windows XP Home Edition, Windows Vista Home Basic, and Windows 7 Home Basic.</span></span>

-   <span data-ttu-id="3003d-119">客户反馈和修补程序汇总： app-v 4.5 SP1 还包括一个累积修补程序，用于解决自 Microsoft Application Virtualization （app-v） 4.5 CU1 发布以来发现的问题。</span><span class="sxs-lookup"><span data-stu-id="3003d-119">Customer Feedback and Hotfix Rollup: App-V4.5 SP1 also includes a rollup up of fixes to address issues found since the Microsoft Application Virtualization (App-V)4.5 CU1 release.</span></span> <span data-ttu-id="3003d-120">更新是由我们的内部团队、合作伙伴和使用 App-v 4.5 的客户的已知问题和客户反馈组合导致的。</span><span class="sxs-lookup"><span data-stu-id="3003d-120">The updates are a result of a combination of known issues and customer feedback from our internal teams, partners, and customers who are using App-V4.5.</span></span> <span data-ttu-id="3003d-121">有关更新的完整列表，请参阅中的知识库文章 <https://go.microsoft.com/fwlink/?LinkId=167121> 。</span><span class="sxs-lookup"><span data-stu-id="3003d-121">For a full list of the updates, see the KB article at <https://go.microsoft.com/fwlink/?LinkId=167121>.</span></span>

## <span data-ttu-id="3003d-122">关于产品文档</span><span class="sxs-lookup"><span data-stu-id="3003d-122">About the Product Documentation</span></span>


<span data-ttu-id="3003d-123">应用程序虚拟化（app-v）的综合文档可在 Microsoft TechNet 上的应用程序虚拟化（app-v）技术支持 <https://go.microsoft.com/fwlink/?LinkId=122939> 。</span><span class="sxs-lookup"><span data-stu-id="3003d-123">Comprehensive documentation for Application Virtualization (App-V) is available on Microsoft TechNet in the Application Virtualization (App-V) TechCenter at <https://go.microsoft.com/fwlink/?LinkId=122939>.</span></span> <span data-ttu-id="3003d-124">TechNet 文档包括应用程序虚拟化 Sequencer、应用程序虚拟化客户端和应用程序虚拟化服务器的联机帮助。</span><span class="sxs-lookup"><span data-stu-id="3003d-124">The TechNet documentation includes the online Help for the Application Virtualization Sequencer, the Application Virtualization Client, and the Application Virtualization Server.</span></span> <span data-ttu-id="3003d-125">它还包括 "应用程序虚拟化规划和部署指南" 和 "应用程序虚拟化操作指南"。</span><span class="sxs-lookup"><span data-stu-id="3003d-125">It also includes the Application Virtualization Planning and Deployment Guide and the Application Virtualization Operations Guide.</span></span>

## <span data-ttu-id="3003d-126">防范安全漏洞和病毒</span><span class="sxs-lookup"><span data-stu-id="3003d-126">Protect Against Security Vulnerabilities and Viruses</span></span>


<span data-ttu-id="3003d-127">为了帮助防范安全漏洞和病毒，我们建议你为正在安装的任何新软件安装最新的可用安全更新。</span><span class="sxs-lookup"><span data-stu-id="3003d-127">To help protect against security vulnerabilities and viruses, we recommend that you install the latest available security updates for any new software being installed.</span></span> <span data-ttu-id="3003d-128">有关详细信息，请参阅 Microsoft 安全性网站 <https://go.microsoft.com/fwlink/?LinkId=3482> 。</span><span class="sxs-lookup"><span data-stu-id="3003d-128">For more information, see the Microsoft Security Web site at <https://go.microsoft.com/fwlink/?LinkId=3482>.</span></span>

## <span data-ttu-id="3003d-129">提供反馈</span><span class="sxs-lookup"><span data-stu-id="3003d-129">Providing Feedback</span></span>


<span data-ttu-id="3003d-130">你可以通过 Microsoft Application Virtualization 技术中心（）上的社区论坛提供反馈、提出建议或报告 Microsoft Application Virtualization （App-v）管理系统的问题 <https://go.microsoft.com/fwlink/?LinkId=122917> 。</span><span class="sxs-lookup"><span data-stu-id="3003d-130">You can provide feedback, make a suggestion, or report an issue with the Microsoft Application Virtualization (App-V) Management System via a community forum on the Microsoft Application Virtualization TechCenter (<https://go.microsoft.com/fwlink/?LinkId=122917>).</span></span>

<span data-ttu-id="3003d-131">你还可以直接向 App-v 文档团队提供有关文档的反馈。</span><span class="sxs-lookup"><span data-stu-id="3003d-131">You can also provide your feedback on the documentation directly to the App-V documentation team.</span></span> <span data-ttu-id="3003d-132">将文档反馈发送到 appvdocs@microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="3003d-132">Send your documentation feedback to appvdocs@microsoft.com.</span></span>

## <span data-ttu-id="3003d-133">应用程序虚拟化 4.5 SP1 的已知问题</span><span class="sxs-lookup"><span data-stu-id="3003d-133">Known Issues with Application Virtualization4.5 SP1</span></span>


<span data-ttu-id="3003d-134">本部分提供有关 Microsoft Application Virtualization （app-v） 4.5 SP1 问题的最新信息。</span><span class="sxs-lookup"><span data-stu-id="3003d-134">This section provides the most up-to-date information about issues with Microsoft Application Virtualization (App-V)4.5 SP1.</span></span> <span data-ttu-id="3003d-135">这些问题不会显示在产品文档中，在某些情况下，可能会矛盾现有产品文档。</span><span class="sxs-lookup"><span data-stu-id="3003d-135">These issues do not appear in the product documentation and in some cases might contradict existing product documentation.</span></span> <span data-ttu-id="3003d-136">只要有可能，这些问题将在本软件的后续版本中解决。</span><span class="sxs-lookup"><span data-stu-id="3003d-136">Whenever possible, these issues will be addressed in later releases of the software.</span></span>

### <span data-ttu-id="3003d-137">服务器管理控制台安装指南</span><span class="sxs-lookup"><span data-stu-id="3003d-137">Guidance for installing Server Management Console</span></span>

<span data-ttu-id="3003d-138">如果需要将管理软件安装到主应用程序虚拟化发布和流式服务器以外的系统上，服务器安装支持在不同的服务器上从主 App-v 管理服务器安装管理控制台和管理 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="3003d-138">If you need to install management software onto systems other than the primary Application Virtualization publishing and streaming server, the server install supports installing the Management Console and Management Web service on separate servers from the primary App-V Management Server.</span></span> <span data-ttu-id="3003d-139">若要跨多台服务器分发管理组件，必须在安装了 Web 服务的服务器上启用 Kerberos 委派。</span><span class="sxs-lookup"><span data-stu-id="3003d-139">To distribute the management components across multiple servers, Kerberos delegation must be enabled on the server where the Web service is installed.</span></span> <span data-ttu-id="3003d-140">有关如何启用此支持的信息，请访问 Microsoft TechNet 库</span><span class="sxs-lookup"><span data-stu-id="3003d-140">For information on how to enable this support, please visit the Microsoft TechNet Library at</span></span> <https://go.microsoft.com/fwlink/?LinkId=166682>

### <span data-ttu-id="3003d-141">使用 setup.msi 安装或升级客户端到 App-v 4.5 SP1 的指南</span><span class="sxs-lookup"><span data-stu-id="3003d-141">Guidance for installing or upgrading clients to App-V4.5 SP1 using setup.msi</span></span>

<span data-ttu-id="3003d-142">当使用 setup.msi 将 App-v 客户端安装或升级到 app-v 4.5 SP1 时，不会自动安装先决条件。</span><span class="sxs-lookup"><span data-stu-id="3003d-142">When installing or upgrading your App-V clients to App-V 4.5 SP1 by using setup.msi, the prerequisites are not installed automatically.</span></span>

<span data-ttu-id="3003d-143">WORKAROUNDYou 必须先手动安装先决条件，然后再安装或升级 app-v client toApp-V 4.5 SP1。</span><span class="sxs-lookup"><span data-stu-id="3003d-143">WORKAROUNDYou must manually install the prerequisites before installing or upgrading the App-V client toApp-V 4.5 SP1.</span></span> <span data-ttu-id="3003d-144">有关安装先决条件和 App-v 客户端的详细过程，请参阅 <https://go.microsoft.com/fwlink/?LinkId=144106> 。</span><span class="sxs-lookup"><span data-stu-id="3003d-144">For detailed procedures for installing the prerequisites and the App-V client, see <https://go.microsoft.com/fwlink/?LinkId=144106>.</span></span>

<span data-ttu-id="3003d-145">完成此操作后，使用具有提升权限的 setup.msi 安装 app-v 4.5 SP1 客户端。</span><span class="sxs-lookup"><span data-stu-id="3003d-145">When this has been completed, install the App-V 4.5 SP1 client by using setup.msi with elevated privileges.</span></span> <span data-ttu-id="3003d-146">此文件可在 Installers\\Client 文件夹中的 App-v 4.5 SP1 版本媒体上使用。</span><span class="sxs-lookup"><span data-stu-id="3003d-146">This file is available on the App-V 4.5 SP1 release media in the Installers\\Client folder.</span></span>

<span data-ttu-id="3003d-147">安装 Microsoft 应用程序错误报告时，如果你要安装或升级到 app-v 4.5 SP1 桌面客户端，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="3003d-147">When installing Microsoft Application Error Reporting, use the following command if you are installing or upgrading to the App-V 4.5 SP1 Desktop client:</span></span>

    msiexec /i dw20shared.msi APPGUID={93468B43-C19D-44F9-8BCC-114076DB0443}  allusers=1 reboot=suppress REINSTALL=all REINSTALLMODE=vomus

<span data-ttu-id="3003d-148">或者，如果你要为远程桌面服务（以前称为 "终端服务"）安装或升级到 app-v 4.5 SP1 客户端，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="3003d-148">Alternatively, if you are installing or upgrading to the App-V 4.5 SP1 Client for Remote Desktop Services (formerly Terminal Services), use the following command:</span></span>

    msiexec /i dw20shared.msi APPGUID={0042AD3C-99A4-4E58-B5F0-744D5AD96E1C} allusers=1 reboot=suppress REINSTALL=all REINSTALLMODE=vomus

<span data-ttu-id="3003d-149">**注意** APPGUID 参数引用你安装或升级的 app-v 客户端的产品代码。</span><span class="sxs-lookup"><span data-stu-id="3003d-149">**Note** The APPGUID parameter references the product code of the App-V client that you install or upgrade.</span></span> <span data-ttu-id="3003d-150">产品代码对于每个 setup.msi 都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="3003d-150">The product code is unique for each setup.msi.</span></span> <span data-ttu-id="3003d-151">你可以使用 Orca 数据库编辑器或类似工具检查 Windows Installer 文件并确定产品代码。</span><span class="sxs-lookup"><span data-stu-id="3003d-151">You can use the Orca database editor or a similar tool to examine Windows Installer files and determine the product code.</span></span> <span data-ttu-id="3003d-152">对于 App-v 4.5 SP1 的所有安装或升级，此步骤是必需的。</span><span class="sxs-lookup"><span data-stu-id="3003d-152">This step is required for all installations or upgrades to App-V 4.5 SP1.</span></span>

 

### <span data-ttu-id="3003d-153">在序列化 .NET Framework 时提高性能</span><span class="sxs-lookup"><span data-stu-id="3003d-153">Improving performance when sequencing the .NET Framework</span></span>

<span data-ttu-id="3003d-154">对 .NET Framework 进行排序时，你可能会遇到性能降低的系统性能，因为 Microsoft .NET Framework NGEN 服务尝试将程序集作为后台任务进行预编译。</span><span class="sxs-lookup"><span data-stu-id="3003d-154">When sequencing the .NET Framework, you might experience reduced system performance because the Microsoft .NET Framework NGEN service attempts to precompile assemblies as a background task.</span></span>

<span data-ttu-id="3003d-155">WORKAROUNDWhen 序列化 .NET Framework 后，在完成监视阶段后禁用 Microsoft .NET Framework NGEN 服务（mscorsvw.exe）。</span><span class="sxs-lookup"><span data-stu-id="3003d-155">WORKAROUNDWhen sequencing the .NET Framework, disable the Microsoft .NET Framework NGEN service (mscorsvw.exe) after completing the monitoring phase.</span></span> <span data-ttu-id="3003d-156">你必须使用 Sequencer 中的 "**虚拟服务**" 选项卡，并将启动类型更改为 "已禁用"。</span><span class="sxs-lookup"><span data-stu-id="3003d-156">You must use the **Virtual Services** tab in the Sequencer and change the startup type to disabled.</span></span>

### <span data-ttu-id="3003d-157">卸载 Microsoft Application Virtualization 客户端时，将删除与执行卸载的用户相关联的用户设置</span><span class="sxs-lookup"><span data-stu-id="3003d-157">When you uninstall the Microsoft Application Virtualization Client, user settings associated with the user performing the uninstall will be deleted</span></span>

<span data-ttu-id="3003d-158">卸载 app-v 客户端时，Windows Installer 将从当前用户的配置文件中删除应用程序虚拟化设置。</span><span class="sxs-lookup"><span data-stu-id="3003d-158">When you uninstall the App-V Client, the Windows Installer will remove Application Virtualization settings from the current user's profile.</span></span> <span data-ttu-id="3003d-159">如果你的计算机使用漫游配置文件，请不要使用你的个人网络帐户卸载客户端，因为它将删除你的所有计算机上的虚拟应用程序的设置。</span><span class="sxs-lookup"><span data-stu-id="3003d-159">If your computer uses roaming profiles, do not use your personal network account to uninstall the client because it will remove settings for your virtual applications on all of your computers.</span></span>

<span data-ttu-id="3003d-160">WORKAROUNDYou 应使用不用于运行虚拟应用程序的管理帐户来执行 App-v 客户端卸载。</span><span class="sxs-lookup"><span data-stu-id="3003d-160">WORKAROUNDYou should perform the App-V Client uninstall with an administrative account that is not used for running virtual applications.</span></span>

### <span data-ttu-id="3003d-161">在运行顺序向导时必须保存在虚拟文件系统和虚拟注册表选项卡上所做的编辑</span><span class="sxs-lookup"><span data-stu-id="3003d-161">Edits made on the virtual file system and virtual registry tabs must be saved while running the Sequencing wizard</span></span>

<span data-ttu-id="3003d-162">如果打开程序包以执行升级，或者如果已使用新程序包运行顺序向导，并且在虚拟文件系统或虚拟注册表选项卡中对程序包进行了更改，这些更改不会自动保存。</span><span class="sxs-lookup"><span data-stu-id="3003d-162">If you open a package to perform an upgrade, or if you have already run the Sequencing wizard with a new package and make changes to the package in the virtual file system or virtual registry tabs, those changes are not automatically saved.</span></span>

<span data-ttu-id="3003d-163">在重新运行向导之前 WORKAROUNDSave 更改，以确保它们反映在向导的虚拟环境中。</span><span class="sxs-lookup"><span data-stu-id="3003d-163">WORKAROUNDSave the changes before re-running the wizard, to ensure that they are reflected inside the wizard’s virtual environment.</span></span>

### <span data-ttu-id="3003d-164">必须从提升的命令提示符运行命令行排序器</span><span class="sxs-lookup"><span data-stu-id="3003d-164">Command-line Sequencer must be run from an elevated command prompt</span></span>

<span data-ttu-id="3003d-165">使用命令行排序器时，它不会提示提升。</span><span class="sxs-lookup"><span data-stu-id="3003d-165">When you use the command-line Sequencer, it does not prompt for elevation.</span></span>

<span data-ttu-id="3003d-166">使用提升的命令提示符 WORKAROUNDRun 命令行排序器。</span><span class="sxs-lookup"><span data-stu-id="3003d-166">WORKAROUNDRun the command-line Sequencer using an elevated command prompt.</span></span>

### <span data-ttu-id="3003d-167">OSD 文件中的短路径变量名称可能会导致错误</span><span class="sxs-lookup"><span data-stu-id="3003d-167">Short path variable names in OSD files can cause errors</span></span>

<span data-ttu-id="3003d-168">如果收到错误 450478-1F702339-0000010B "目录名称无效" 在客户端上启动虚拟应用程序时，OSD 中的变量可能设置错误。</span><span class="sxs-lookup"><span data-stu-id="3003d-168">If you receive error 450478-1F702339-0000010B “The directory name is invalid” when starting a virtual application on the client, it is possible that the variable in the OSD is set incorrectly.</span></span> <span data-ttu-id="3003d-169">如果应用程序的安装程序在排序期间设置短路径名，则可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="3003d-169">This can happen if the application’s installer sets a short path name during sequencing.</span></span>

<span data-ttu-id="3003d-170">WORKAROUNDRemove OSD 文件中存在的任何 CSIDL 变量的尾随波形符。</span><span class="sxs-lookup"><span data-stu-id="3003d-170">WORKAROUNDRemove the trailing tilde from any CSIDL variable that exists in the OSD file.</span></span>

### <a href="" id="correct-syntax-for-decodepath-parameter-for-command-line-sequencer-"></a><span data-ttu-id="3003d-171">命令行 Sequencer 的 DECODEPATH 参数的正确语法</span><span class="sxs-lookup"><span data-stu-id="3003d-171">Correct syntax for DECODEPATH parameter for command-line Sequencer</span></span>

<span data-ttu-id="3003d-172">在命令行 Sequencer 中，打开要升级的程序包并将其解码到 Q 驱动器的根时， *DECODEPATH*参数的语法不应包含尾部斜杠。</span><span class="sxs-lookup"><span data-stu-id="3003d-172">In the command-line Sequencer, when opening a package for upgrade and decoding it to the root of the Q drive, the syntax for the *DECODEPATH* parameter should not include a trailing slash.</span></span>

<span data-ttu-id="3003d-173">WORKAROUNDYou 可以使用**Q：** 而不是**Q:\\** （省略结尾的 "\" 字符）。</span><span class="sxs-lookup"><span data-stu-id="3003d-173">WORKAROUNDYou can use **Q:** rather than **Q:\\** (omitting the trailing “\\” character).</span></span>

### <a href="" id="when-upgrading-4-2-packages--you-encounter-problems-caused-by-windows-installer-files-in-the-virtual-file-system-"></a><span data-ttu-id="3003d-174">升级4.2 程序包时，遇到由虚拟文件系统中的 Windows Installer 文件导致的问题</span><span class="sxs-lookup"><span data-stu-id="3003d-174">When upgrading4.2 packages, you encounter problems caused by Windows Installer files in the Virtual File System</span></span>

<span data-ttu-id="3003d-175">从4.2 升级程序包时，可能会遇到与在4.2 中和在序列化工作站上本地安装的 Windows installer 库中的 Windows Installer 系统文件不匹配的问题。</span><span class="sxs-lookup"><span data-stu-id="3003d-175">When upgrading a package from4.2, you might experience issues relating to a mismatch of Windows Installer system files that were included by default in4.2 and the Windows Installer libraries locally installed on your Sequencing workstation.</span></span> <span data-ttu-id="3003d-176">以下文件位于 CSIDL \ _SYSTEM \：</span><span class="sxs-lookup"><span data-stu-id="3003d-176">The following files are located in CSIDL\_SYSTEM\\:</span></span>

<span data-ttu-id="3003d-177">cabinet.dll</span><span class="sxs-lookup"><span data-stu-id="3003d-177">cabinet.dll</span></span>

<span data-ttu-id="3003d-178">msi.dll</span><span class="sxs-lookup"><span data-stu-id="3003d-178">msi.dll</span></span>

<span data-ttu-id="3003d-179">msiexec.exe</span><span class="sxs-lookup"><span data-stu-id="3003d-179">msiexec.exe</span></span>

<span data-ttu-id="3003d-180">msihnd.dll</span><span class="sxs-lookup"><span data-stu-id="3003d-180">msihnd.dll</span></span>

<span data-ttu-id="3003d-181">msimsg.dlll</span><span class="sxs-lookup"><span data-stu-id="3003d-181">msimsg.dlll</span></span>

<span data-ttu-id="3003d-182">从程序包中 WORKAROUNDDelete 前面的所有文件。</span><span class="sxs-lookup"><span data-stu-id="3003d-182">WORKAROUNDDelete all of the preceding files from the package.</span></span> <span data-ttu-id="3003d-183">删除 " **VFS** " 选项卡上的映射以及解码路径中 CSIDL \ _SYSTEM 文件夹中的实际文件。</span><span class="sxs-lookup"><span data-stu-id="3003d-183">Delete the mappings on the **VFS** tab as well as the actual files in the CSIDL\_SYSTEM folder in your decode path.</span></span>

### <a href="" id="on-windows-xp--client-install-logging-is-not-enabled-by-default-"></a><span data-ttu-id="3003d-184">在 WindowsXP 上，默认情况下不启用客户端安装日志记录</span><span class="sxs-lookup"><span data-stu-id="3003d-184">On WindowsXP, client install logging is not enabled by default</span></span>

<span data-ttu-id="3003d-185">在安装客户端时，为了确保捕获任何安装错误以进行故障排除，应使用命令行启用日志记录。</span><span class="sxs-lookup"><span data-stu-id="3003d-185">When installing the client, to ensure that any install errors are captured for troubleshooting purposes, you should enable logging by using the command line.</span></span>

<span data-ttu-id="3003d-186">WORKAROUNDAdd 参数 */l\ \* vx！ log.txt*到命令行，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="3003d-186">WORKAROUNDAdd the parameter */l\*vx! log.txt* to the command line, as shown in the following example:</span></span>

<span data-ttu-id="3003d-187">setup.exe/s/v "/qn/l\ \* vx！</span><span class="sxs-lookup"><span data-stu-id="3003d-187">setup.exe /s /v”/qn /l\*vx!</span></span> <span data-ttu-id="3003d-188">log.txt "</span><span class="sxs-lookup"><span data-stu-id="3003d-188">log.txt”</span></span>

<span data-ttu-id="3003d-189">msiexec.exe/i setup.msi/qn/l\ \* vx！</span><span class="sxs-lookup"><span data-stu-id="3003d-189">msiexec.exe /i setup.msi /qn /l\*vx!</span></span> <span data-ttu-id="3003d-190">log.txt</span><span class="sxs-lookup"><span data-stu-id="3003d-190">log.txt</span></span>

<span data-ttu-id="3003d-191">或者，你可以将注册表项设置为以下值：</span><span class="sxs-lookup"><span data-stu-id="3003d-191">Alternatively, you can set the registry key to the following value:</span></span>

<span data-ttu-id="3003d-192">\ [HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Policies\\Microsoft\\Windows\\Installer\] "日志记录" = "voicewarmupx！"</span><span class="sxs-lookup"><span data-stu-id="3003d-192">\[HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Policies\\Microsoft\\Windows\\Installer\] "Logging"="voicewarmupx!"</span></span>

### <span data-ttu-id="3003d-193">要使 Kerberos 身份验证正常工作，必须为 IIS 注册服务主体名称（Spn）</span><span class="sxs-lookup"><span data-stu-id="3003d-193">For Kerberos authentication to work, Service Principal Names (SPNs) must be registered for IIS</span></span>

<span data-ttu-id="3003d-194">当将 IIS 6.0 或7.0 用于图标或 OSD 文件检索以及程序包流时，必须按如下所示注册 Spn：</span><span class="sxs-lookup"><span data-stu-id="3003d-194">When using IIS6.0 or7.0 for icon or OSD file retrieval and streaming of packages, for Kerberos authentication to be enabled, the SPNs must be registered as follows:</span></span>

-   <span data-ttu-id="3003d-195">在 IIS 服务器上，使用 "SETSPN.EXE 资源工具包" 工具运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="3003d-195">On the IIS server, run the following commands by using the SETSPN.EXE Resource Kit tool.</span></span> <span data-ttu-id="3003d-196">必须使用服务器完全限定的域名（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="3003d-196">The server fully qualified domain name (FQDN) must be used.</span></span>

    <span data-ttu-id="3003d-197">Setspn-r SOFTGRID/ &lt; 服务器 FQDN&gt;</span><span class="sxs-lookup"><span data-stu-id="3003d-197">Setspn -r SOFTGRID/&lt;Server FQDN&gt;</span></span>

    <span data-ttu-id="3003d-198">Setspn-r HTTP/ &lt; 服务器 FQDN&gt;</span><span class="sxs-lookup"><span data-stu-id="3003d-198">Setspn -r HTTP/&lt;Server FQDN&gt;</span></span>

<span data-ttu-id="3003d-199">有关详细信息，请参阅 <https://go.microsoft.com/fwlink/?LinkId=131407>。</span><span class="sxs-lookup"><span data-stu-id="3003d-199">For more information, see <https://go.microsoft.com/fwlink/?LinkId=131407>.</span></span>

### <span data-ttu-id="3003d-200">.NET 兼容性更改</span><span class="sxs-lookup"><span data-stu-id="3003d-200">.NET compatibility changes</span></span>

<span data-ttu-id="3003d-201">Microsoft Application Virtualization （App-v）累积 Update1 或更高版本支持对 WindowsXP （SP2 或更高版本）上的 .NET Framework 进行排序。</span><span class="sxs-lookup"><span data-stu-id="3003d-201">Microsoft Application Virtualization (App-V) Cumulative Update1 or later supports sequencing the .NET Framework on WindowsXP (SP2 or later).</span></span> <span data-ttu-id="3003d-202">当与 App-v 4.5 Sequencer 一起使用时，针对 SoftGrid 4.2 写入的 .NET 应用程序的排序例程可能需要更新。</span><span class="sxs-lookup"><span data-stu-id="3003d-202">Sequencing routines for .NET applications that were written for SoftGrid4.2 might need to be updated when used with the App-V 4.5 Sequencer.</span></span> <span data-ttu-id="3003d-203">有关详细信息和解决方法，请参阅知识文库文章 <https://go.microsoft.com/fwlink/?LinkId=123412> 。</span><span class="sxs-lookup"><span data-stu-id="3003d-203">For details and workarounds, please refer to the Knowledge Base article at <https://go.microsoft.com/fwlink/?LinkId=123412>.</span></span>

### <a href="" id="after-client-upgrade-from-app-v-4-2--some-applications-are-not-shown-"></a><span data-ttu-id="3003d-204">从 App-v 4.2 升级客户端后，某些应用程序不会显示</span><span class="sxs-lookup"><span data-stu-id="3003d-204">After client upgrade from App-V4.2, some applications are not shown</span></span>

<span data-ttu-id="3003d-205">在日志中检查以下错误： "Application Virtualization 客户端无法解析 OSD 文件"。</span><span class="sxs-lookup"><span data-stu-id="3003d-205">Check for the following error in the log: ”The Application Virtualization Client could not parse the OSD file”.</span></span> <span data-ttu-id="3003d-206">App-v 4.5 客户端筛选出包含包含空 OS 标记（ &lt; os &gt; &lt; /OS）的 OSD 文件的应用程序 &gt; 。</span><span class="sxs-lookup"><span data-stu-id="3003d-206">The App-V 4.5 client filters out applications that have an OSD file containing an empty OS tag (&lt;OS&gt;&lt;/OS&gt;).</span></span>

<span data-ttu-id="3003d-207">WORKAROUNDDelete OSD 文件中的空 OS 标签。</span><span class="sxs-lookup"><span data-stu-id="3003d-207">WORKAROUNDDelete the empty OS tag from the OSD file.</span></span>

### <span data-ttu-id="3003d-208">对于某些进程，app-v 服务器需要其防火墙中的免除</span><span class="sxs-lookup"><span data-stu-id="3003d-208">The App-V server requires exemptions in its firewall for certain processes</span></span>

<span data-ttu-id="3003d-209">为使服务器正确流出应用程序，服务器的核心进程（包括调度程序）需要通过防火墙访问。</span><span class="sxs-lookup"><span data-stu-id="3003d-209">For the server to stream applications correctly, the server's core processes, including the dispatcher, need access through the firewall.</span></span>

<span data-ttu-id="3003d-210">以下进程的服务器防火墙中的 WORKAROUNDSet 免除： sghwsvr.exe 和 sghwdsptr.exe。</span><span class="sxs-lookup"><span data-stu-id="3003d-210">WORKAROUNDSet exemptions in the server's firewall for the following processes: sghwsvr.exe and sghwdsptr.exe.</span></span> <span data-ttu-id="3003d-211">这适用于 App-v 管理服务器和 App-v 流式处理服务器。</span><span class="sxs-lookup"><span data-stu-id="3003d-211">This applies to the App-V Management Server and App-V Streaming Server.</span></span>

### <span data-ttu-id="3003d-212">当服务器安装程序在静默模式下运行时，它不会正确检查 MSXML6</span><span class="sxs-lookup"><span data-stu-id="3003d-212">When the server installer is run in silent mode, it does not correctly check for MSXML6</span></span>

<span data-ttu-id="3003d-213">App-v 管理服务器依赖于 MSXML6。</span><span class="sxs-lookup"><span data-stu-id="3003d-213">The App-V Management Server depends on MSXML6.</span></span> <span data-ttu-id="3003d-214">但是，如果你在静默模式下运行安装程序（例如，在尚未安装 MSXML6 的系统上使用命令 "msiexec-i setup.msi/qn"），则安装程序不会检测缺少的依赖项，也不会安装。</span><span class="sxs-lookup"><span data-stu-id="3003d-214">However, if you run the installer in silent mode—for example, by using the command “msiexec -i setup.msi /qn” on a system where MSXML6 is not already installed—the installer does not detect the missing dependency and installs anyway.</span></span> <span data-ttu-id="3003d-215">因此，当客户尝试从 App-v 管理服务器刷新发布信息时，它们将看到失败。</span><span class="sxs-lookup"><span data-stu-id="3003d-215">Therefore, when clients attempt to refresh publishing information from the App-V Management Server, they will see failures.</span></span>

<span data-ttu-id="3003d-216">WORKAROUNDVerify 在尝试安装 App-v 管理服务器的静默安装之前，系统上已安装 MSXML6。</span><span class="sxs-lookup"><span data-stu-id="3003d-216">WORKAROUNDVerify that MSXML6 is installed on the system before attempting a silent install of the App-V Management Server.</span></span>

### <span data-ttu-id="3003d-217">尝试连接到应用程序虚拟化管理控制台时出现错误代码000C800</span><span class="sxs-lookup"><span data-stu-id="3003d-217">Error code 000C800 when attempting to connect to the Application Virtualization Management Console</span></span>

<span data-ttu-id="3003d-218">如果应用程序虚拟化管理员的应用程序虚拟化管理员在尝试连接到 app-v 管理控制台时将收到错误（错误代码：000C800），并且 sftmmc 项将指示对 SftMgmt 的访问权限被拒绝了。</span><span class="sxs-lookup"><span data-stu-id="3003d-218">An Application Virtualization administrator who is not a local administrator on the App-V Management Web Service server will receive an error (Error code: 000C800) when attempting to connect to the App-V Management Console, and the sftmmc.log entry will indicate that access to SftMgmt.udl is denied.</span></span> <span data-ttu-id="3003d-219">若要成功连接到 app-v 管理控制台，没有对 app-v 管理 Web 服务服务器具有本地管理员权限的管理员必须至少拥有 SftMgmt 文件的 "读取" 和 "执行" 权限。</span><span class="sxs-lookup"><span data-stu-id="3003d-219">To successfully connect to the App-V Management Console, an administrator who does not have local administrator rights on the App-V Management Web Service server must have at least read and execute permissions to the SftMgmt.udl file.</span></span>

<span data-ttu-id="3003d-220">应用程序虚拟化管理员必须在%systemdrive%\\Program Files\\Microsoft System Center App Virt Management Server\\App Virt 管理服务 "下为 SftMgmt 文件授予" 读取 "和" 执行 "权限。</span><span class="sxs-lookup"><span data-stu-id="3003d-220">The Application Virtualization administrators must be given read and execute permissions to the SftMgmt.UDL file under %systemdrive%\\Program Files\\Microsoft System Center App Virt Management Server\\App Virt Management Service.</span></span>

### <span data-ttu-id="3003d-221">当与 KEEPCURRENTSETTINGS = 1 结合使用时，将忽略客户端安装程序命令行参数</span><span class="sxs-lookup"><span data-stu-id="3003d-221">Client installer command-line parameters are ignored when used in conjunction with KEEPCURRENTSETTINGS=1</span></span>

<span data-ttu-id="3003d-222">与 KEEPCURRENTSETTINGS = 1 结合使用时，将忽略以下客户端安装程序命令行参数： SWICACHESIZE、MINFREESPACEMB、ALLOWINDEPENDENTFILESTREAMING、APPLICATIONSOURCEROOT、ICONSOURCEROOT、OSDSOURCEROOT、SYSTEMEVENTLOGLEVEL、SWIGLOBALDATA、DOTIMEOUTMINUTES、SWIFSDRIVE、AUTOLOADTARGET、AUTOLOADTRIGGERS、SWIUSERDATA 和 REQUIRESECURECONNECTION。</span><span class="sxs-lookup"><span data-stu-id="3003d-222">When used in conjunction with KEEPCURRENTSETTINGS=1, the following client installer command-line parameters are ignored: SWICACHESIZE, MINFREESPACEMB, ALLOWINDEPENDENTFILESTREAMING, APPLICATIONSOURCEROOT, ICONSOURCEROOT, OSDSOURCEROOT, SYSTEMEVENTLOGLEVEL, SWIGLOBALDATA, DOTIMEOUTMINUTES, SWIFSDRIVE, AUTOLOADTARGET, AUTOLOADTRIGGERS, SWIUSERDATA, and REQUIRESECURECONNECTION.</span></span>

<span data-ttu-id="3003d-223">WORKAROUNDIf 要保留的设置，请使用 KEEPCURRENTSETTINGS = 1，然后在部署后设置其他参数。</span><span class="sxs-lookup"><span data-stu-id="3003d-223">WORKAROUNDIf you have settings you want to retain, use KEEPCURRENTSETTINGS=1 and then set the other parameters after deployment.</span></span> <span data-ttu-id="3003d-224">App-v ADM 模板可用于设置以下客户端设置： APPLICATIONSOURCEROOT、ICONSOURCEROOT、OSDSOURCEROOT、AUTOLOADTARGET、AUTOLOADTRIGGERS、DOTIMEOUTMINUTES 和 ALLOWINDEPENDENTFILESTREAMING。</span><span class="sxs-lookup"><span data-stu-id="3003d-224">The App-V ADM Template can be used to set the following client settings: APPLICATIONSOURCEROOT, ICONSOURCEROOT, OSDSOURCEROOT, AUTOLOADTARGET, AUTOLOADTRIGGERS, DOTIMEOUTMINUTES, and ALLOWINDEPENDENTFILESTREAMING.</span></span> <span data-ttu-id="3003d-225">可以在上找到 ADM 模板 <https://go.microsoft.com/fwlink/?LinkId=121835> 。</span><span class="sxs-lookup"><span data-stu-id="3003d-225">The ADM Template can be found at <https://go.microsoft.com/fwlink/?LinkId=121835>.</span></span>

## <span data-ttu-id="3003d-226">发行说明版权信息</span><span class="sxs-lookup"><span data-stu-id="3003d-226">Release Notes Copyright Information</span></span>


<span data-ttu-id="3003d-227">本文档中的信息（包括 URL 和其他互联网网站引用）如有更改，恕不另行通知，仅供参考之用。</span><span class="sxs-lookup"><span data-stu-id="3003d-227">Information in this document, including URL and other Internet Web site references, is subject to change without notice and is provided for informational purposes only.</span></span> <span data-ttu-id="3003d-228">本文档使用或导致的全部风险由用户承担，Microsoft Corporation 不作任何明示或暗示保证。</span><span class="sxs-lookup"><span data-stu-id="3003d-228">The entire risk of the use or results from the use of this document remains with the user, and Microsoft Corporation makes no warranties, either express or implied.</span></span> <span data-ttu-id="3003d-229">除非另有说明，否则此处的示例中所描述的公司、组织、产品、域名、电子邮件地址、徽标、人员、地点和事件均属虚构。</span><span class="sxs-lookup"><span data-stu-id="3003d-229">Unless otherwise noted, the companies, organizations, products, domain names, e-mail addresses, logos, people, places, and events depicted in examples herein are fictitious.</span></span> <span data-ttu-id="3003d-230">无意与任何真实公司、组织、产品、域名、电子邮件地址、徽标、人员、地点或事件相关联，也不应进行推断。</span><span class="sxs-lookup"><span data-stu-id="3003d-230">No association with any real company, organization, product, domain name, e-mail address, logo, person, place, or event is intended or should be inferred.</span></span> <span data-ttu-id="3003d-231">用户有责任遵守所有适用的版权法。</span><span class="sxs-lookup"><span data-stu-id="3003d-231">Complying with all applicable copyright laws is the responsibility of the user.</span></span> <span data-ttu-id="3003d-232">在不限制版权法规定的权利的情况下，未经 Microsoft Corporation 明确书面允许，不得出于任何目的，以任何形式或通过任何方式（电子、机械、影印、录制或其他方式）对本文档中的任何内容进行复制、传输或者将其存储到或引入到检索系统。</span><span class="sxs-lookup"><span data-stu-id="3003d-232">Without limiting the rights under copyright, no part of this document may be reproduced, stored in or introduced into a retrieval system, or transmitted in any form or by any means (electronic, mechanical, photocopying, recording, or otherwise), or for any purpose, without the express written permission of Microsoft Corporation.</span></span>

<span data-ttu-id="3003d-233">Microsoft 可能拥有涉及本文档中的主题的专利、专利申请、商标、版权和其他知识产权。</span><span class="sxs-lookup"><span data-stu-id="3003d-233">Microsoft may have patents, patent applications, trademarks, copyrights, or other intellectual property rights covering subject matter in this document.</span></span> <span data-ttu-id="3003d-234">除非得到 Microsoft 的明确书面许可，否则本文档不授予用户任何使用这些专利、商标、版权或其他知识产权的许可。</span><span class="sxs-lookup"><span data-stu-id="3003d-234">Except as expressly provided in any written license agreement from Microsoft, the furnishing of this document does not give you any license to these patents, trademarks, copyrights, or other intellectual property.</span></span>



<span data-ttu-id="3003d-235">Microsoft、Active Directory、ActiveSync、MS-DOS、Windows、WindowsServer 和 Windows Vista 是 Microsoft 公司组的商标。</span><span class="sxs-lookup"><span data-stu-id="3003d-235">Microsoft, Active Directory, ActiveSync, MS-DOS, Windows, WindowsServer, and Windows Vista are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="3003d-236">所有其他商标的所有权属于其各自所有者。</span><span class="sxs-lookup"><span data-stu-id="3003d-236">All other trademarks are property of their respective owners.</span></span>

 

 





