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
# <span data-ttu-id="e14d3-103">Microsoft Application Virtualization 管理系统发行说明</span><span class="sxs-lookup"><span data-stu-id="e14d3-103">Microsoft Application Virtualization Management System Release Notes</span></span>


<span data-ttu-id="e14d3-104">若要搜索这些发行说明，请按 CTRL + F。</span><span class="sxs-lookup"><span data-stu-id="e14d3-104">To search these Release Notes, press CTRL+F.</span></span>

<span data-ttu-id="e14d3-105">**重要提示** 在安装应用程序虚拟化管理系统之前，请仔细阅读这些发行说明。</span><span class="sxs-lookup"><span data-stu-id="e14d3-105">**Important** Read these Release Notes thoroughly before you install the Application Virtualization Management System.</span></span> <span data-ttu-id="e14d3-106">这些发行说明包含成功安装应用程序虚拟化管理系统所需的信息。</span><span class="sxs-lookup"><span data-stu-id="e14d3-106">These Release Notes contain information that you need to successfully install the Application Virtualization Management System.</span></span> <span data-ttu-id="e14d3-107">本文档包含产品文档中不可用的信息。</span><span class="sxs-lookup"><span data-stu-id="e14d3-107">This document contains information that is not available in the product documentation.</span></span> <span data-ttu-id="e14d3-108">如果这些发行说明和其他应用程序虚拟化管理系统文档之间存在差异，则应将最新更改视为权威。</span><span class="sxs-lookup"><span data-stu-id="e14d3-108">If there is a discrepancy between these Release Notes and other Application Virtualization Management System documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="e14d3-109">这些发行说明取代了本产品附带的内容。</span><span class="sxs-lookup"><span data-stu-id="e14d3-109">These Release Notes supersede the content included with this product.</span></span>

 

<span data-ttu-id="e14d3-110">有关已知问题的更新信息，请访问 Microsoft TechNet 库 <https://go.microsoft.com/fwlink/?LinkId=122918> 。</span><span class="sxs-lookup"><span data-stu-id="e14d3-110">For updated information about known issues, please visit the Microsoft TechNet Library at <https://go.microsoft.com/fwlink/?LinkId=122918>.</span></span>

## <span data-ttu-id="e14d3-111">关于 Microsoft Application Virtualization 4.5 累积更新1</span><span class="sxs-lookup"><span data-stu-id="e14d3-111">About Microsoft Application Virtualization 4.5 Cumulative Update 1</span></span>


<span data-ttu-id="e14d3-112">这些发行说明已更新，以反映 Microsoft Application Virtualization 4.5 累积 Update1 （App-v 4.5 CU1）引入的更改，这些更改提供了对应用程序虚拟化（app-v）4.5 的最新更新。</span><span class="sxs-lookup"><span data-stu-id="e14d3-112">These Release Notes have been updated to reflect the changes introduced with Microsoft Application Virtualization4.5 Cumulative Update1 (App-V4.5 CU1), which provides the latest updates to Application Virtualization (App-V)4.5.</span></span> <span data-ttu-id="e14d3-113">此累积更新包含以下更改：</span><span class="sxs-lookup"><span data-stu-id="e14d3-113">This cumulative update contains the following changes:</span></span>

-   <span data-ttu-id="e14d3-114">支持 Windows7 Beta 和 Windows Server2008R2 Beta： app-v 4.5 CU1 解决 Windows7 Beta 和 Windows Server2008R2 Beta 的兼容性问题。</span><span class="sxs-lookup"><span data-stu-id="e14d3-114">Support for Windows7 Beta and Windows Server2008R2 Beta: App-V4.5 CU1 addresses compatibility issues with Windows7 Beta and Windows Server2008R2 Beta.</span></span> <span data-ttu-id="e14d3-115">将针对阻止 CU1 在预 RTM 版本的 Windows7 上运行的阻止应用的阻止问题提供支持。</span><span class="sxs-lookup"><span data-stu-id="e14d3-115">Support will be provided for blocking issues that prevent App-V4.5 CU1 running in a test environment on pre-RTM versions of Windows7.</span></span> <span data-ttu-id="e14d3-116">这将帮助确保你的虚拟应用程序可以在测试环境中成功运行，其中需要使用 app-v 4.5 客户端与 Windows7 Beta 之间的兼容性。</span><span class="sxs-lookup"><span data-stu-id="e14d3-116">This will help ensure that your virtual applications can run successfully in a test environment where compatibility between App-V4.5 Client and Windows7 Beta is required.</span></span>

    <span data-ttu-id="e14d3-117">**重要提示** 不支持在实时操作环境中的任何版本的 Windows7 或 Windows Server2008R2 上运行 app-v 4.5 CU1。</span><span class="sxs-lookup"><span data-stu-id="e14d3-117">**Important** Running App-V4.5 CU1 on any version of Windows7 or Windows Server2008R2 in a live operating environment is not supported.</span></span>

     

-   <span data-ttu-id="e14d3-118">改进了对 .NET Framework 序列化的支持： app-v 4.5 CU1 解决了在 WindowsXP （SP2 或更高版本）上排序 .NET Framework 3.5 和更早版本的以前出现的问题。</span><span class="sxs-lookup"><span data-stu-id="e14d3-118">Improved support for sequencing the .NET Framework: App-V4.5 CU1 addresses previous issues with sequencing the .NET Framework3.5 and earlier on WindowsXP (SP2 or later).</span></span> <span data-ttu-id="e14d3-119">有关新功能的详细信息，请参阅 TechNet 文章 <https://go.microsoft.com/fwlink/?LinkId=123412> 。</span><span class="sxs-lookup"><span data-stu-id="e14d3-119">For more information about the new capabilities, see the TechNet article at <https://go.microsoft.com/fwlink/?LinkId=123412>.</span></span>

-   <span data-ttu-id="e14d3-120">客户反馈和修补程序汇总： app-v 4.5 CU1 还包括自 App-v 4.5 RTM 版本以来发现的解决问题的修补程序汇总。</span><span class="sxs-lookup"><span data-stu-id="e14d3-120">Customer Feedback and Hotfix Rollup: App-V4.5 CU1 also includes a rollup up of fixes to address issues found since the App-V4.5 RTM release.</span></span> <span data-ttu-id="e14d3-121">这包括来自我们的内部团队、合作伙伴和使用 App-v 4.5 的客户的已知问题和客户反馈的组合。</span><span class="sxs-lookup"><span data-stu-id="e14d3-121">This includes a combination of known issues and customer feedback from our internal teams, partners, and customers who are using App-V4.5.</span></span> <span data-ttu-id="e14d3-122">有关包含的更新的完整列表，请参阅中的知识库文章 <https://go.microsoft.com/fwlink/?LinkId=141258> 。</span><span class="sxs-lookup"><span data-stu-id="e14d3-122">For a full list of the included updates, see the KB article at <https://go.microsoft.com/fwlink/?LinkId=141258>.</span></span>

## <span data-ttu-id="e14d3-123">关于产品文档</span><span class="sxs-lookup"><span data-stu-id="e14d3-123">About the Product Documentation</span></span>


<span data-ttu-id="e14d3-124">应用程序虚拟化（app-v）的综合文档可在 Microsoft TechNet 上的应用程序虚拟化（app-v）技术支持 <https://go.microsoft.com/fwlink/?LinkId=122939> 。</span><span class="sxs-lookup"><span data-stu-id="e14d3-124">Comprehensive documentation for Application Virtualization (App-V) is available on Microsoft TechNet in the Application Virtualization (App-V) TechCenter at <https://go.microsoft.com/fwlink/?LinkId=122939>.</span></span> <span data-ttu-id="e14d3-125">TechNet 文档包括应用程序虚拟化 Sequencer、应用程序虚拟化客户端和应用程序虚拟化服务器的联机帮助。</span><span class="sxs-lookup"><span data-stu-id="e14d3-125">The TechNet documentation includes the online Help for the Application Virtualization Sequencer, the Application Virtualization Client, and the Application Virtualization Server.</span></span> <span data-ttu-id="e14d3-126">它还包括 "应用程序虚拟化规划和部署指南" 和 "应用程序虚拟化操作指南"。</span><span class="sxs-lookup"><span data-stu-id="e14d3-126">It also includes the Application Virtualization Planning and Deployment Guide and the Application Virtualization Operations Guide.</span></span>

## <span data-ttu-id="e14d3-127">防范安全漏洞和病毒</span><span class="sxs-lookup"><span data-stu-id="e14d3-127">Protect Against Security Vulnerabilities and Viruses</span></span>


<span data-ttu-id="e14d3-128">若要帮助防范安全漏洞和病毒，请务必为正在安装的任何新软件安装最新的可用安全更新。</span><span class="sxs-lookup"><span data-stu-id="e14d3-128">To help protect against security vulnerabilities and viruses, it is important to install the latest available security updates for any new software being installed.</span></span> <span data-ttu-id="e14d3-129">有关详细信息，请参阅 Microsoft 安全性网站 <https://go.microsoft.com/fwlink/?LinkId=3482> 。</span><span class="sxs-lookup"><span data-stu-id="e14d3-129">For more information, see the Microsoft Security Web site at <https://go.microsoft.com/fwlink/?LinkId=3482>.</span></span>

## <span data-ttu-id="e14d3-130">提供反馈</span><span class="sxs-lookup"><span data-stu-id="e14d3-130">Providing Feedback</span></span>


<span data-ttu-id="e14d3-131">你可以通过 Microsoft Application Virtualization 技术中心（）上的社区论坛提供反馈、提出建议或报告 Microsoft Application Virtualization （App-v）管理系统的问题 <https://go.microsoft.com/fwlink/?LinkId=122917> 。</span><span class="sxs-lookup"><span data-stu-id="e14d3-131">You can provide feedback, make a suggestion, or report an issue with the Microsoft Application Virtualization (App-V) Management System via a community forum on the Microsoft Application Virtualization TechCenter (<https://go.microsoft.com/fwlink/?LinkId=122917>).</span></span>

<span data-ttu-id="e14d3-132">你还可以直接向 App-v 文档团队提供有关文档的反馈。</span><span class="sxs-lookup"><span data-stu-id="e14d3-132">You can also provide your feedback on the documentation directly to the App-V documentation team.</span></span> <span data-ttu-id="e14d3-133">将文档反馈发送到 appvdocs@microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="e14d3-133">Send your documentation feedback to appvdocs@microsoft.com.</span></span>

## <span data-ttu-id="e14d3-134">应用程序虚拟化 4.5 CU1 的已知问题</span><span class="sxs-lookup"><span data-stu-id="e14d3-134">Known Issues with Application Virtualization4.5 CU1</span></span>


<span data-ttu-id="e14d3-135">本部分提供有关 Microsoft Application Virtualization （app-v） 4.5 CU1 问题的最新信息。</span><span class="sxs-lookup"><span data-stu-id="e14d3-135">This section provides the most up-to-date information about issues with Microsoft Application Virtualization (App-V)4.5 CU1.</span></span> <span data-ttu-id="e14d3-136">这些问题不会显示在产品文档中，在某些情况下，可能会矛盾现有产品文档。</span><span class="sxs-lookup"><span data-stu-id="e14d3-136">These issues do not appear in the product documentation and in some cases might contradict existing product documentation.</span></span> <span data-ttu-id="e14d3-137">只要有可能，这些问题将在以后的版本中解决。</span><span class="sxs-lookup"><span data-stu-id="e14d3-137">Whenever possible, these issues will be addressed in later releases.</span></span>

### <span data-ttu-id="e14d3-138">使用 setup.msi 将客户端安装或升级到 app-v 4.5 CU1 的指南</span><span class="sxs-lookup"><span data-stu-id="e14d3-138">Guidance for installing or upgrading clients to App-V4.5 CU1 using setup.msi</span></span>

<span data-ttu-id="e14d3-139">当使用 setup.msi 将 App-v 客户端安装或升级到 app-v 4.5 CU1 时，不会自动安装先决条件。</span><span class="sxs-lookup"><span data-stu-id="e14d3-139">When installing or upgrading your App-V clients to App-V4.5 CU1 by using setup.msi, the prerequisites are not installed automatically.</span></span>

<span data-ttu-id="e14d3-140">WORKAROUNDYou 必须先手动安装先决条件，然后再将 App-v 客户端安装或升级到 4.5 CU1。</span><span class="sxs-lookup"><span data-stu-id="e14d3-140">WORKAROUNDYou must manually install the prerequisites before installing or upgrading the App-V client to4.5 CU1.</span></span> <span data-ttu-id="e14d3-141">有关安装先决条件和 App-v 客户端的详细过程，请参阅 <https://go.microsoft.com/fwlink/?LinkId=144106> 。</span><span class="sxs-lookup"><span data-stu-id="e14d3-141">For detailed procedures for installing the prerequisites and the App-V client, see <https://go.microsoft.com/fwlink/?LinkId=144106>.</span></span>

<span data-ttu-id="e14d3-142">完成此操作后，使用具有提升权限的 setup.msi 安装 app-v 4.5 CU1 客户端。</span><span class="sxs-lookup"><span data-stu-id="e14d3-142">When this has been completed, install the App-V4.5 CU1 client by using setup.msi with elevated privileges.</span></span> <span data-ttu-id="e14d3-143">此文件可在 Installers\\Client 文件夹中的 App-v 4.5 CU1 release 媒体上使用。</span><span class="sxs-lookup"><span data-stu-id="e14d3-143">This file is available on the App-V4.5 CU1 release media in the Installers\\Client folder.</span></span>

<span data-ttu-id="e14d3-144">安装 Microsoft 应用程序错误报告时，如果你要安装或升级到 app-v 4.5 CU1 桌面客户端，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="e14d3-144">When installing Microsoft Application Error Reporting, use the following command if you are installing or upgrading to the App-V4.5 CU1 Desktop client:</span></span>

    msiexec /i dw20shared.msi APPGUID={FE495DBC-6D42-4698-B61F-86E655E0796D}  allusers=1 reboot=suppress REINSTALL=all REINSTALLMODE=vomus

<span data-ttu-id="e14d3-145">或者，如果你要安装或升级到 app-v 4.5 CU1 终端服务客户端，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="e14d3-145">Alternatively, if you are installing or upgrading to the App-V 4.5 CU1 Terminal Services client, use the following command:</span></span>

    msiexec /i dw20shared.msi APPGUID={8A97C241-D92A-47DC-B360-E716C1AAA929} allusers=1 reboot=suppress REINSTALL=all REINSTALLMODE=vomus

<span data-ttu-id="e14d3-146">**注意** APPGUID 参数引用你安装或升级到的 app-v 客户端的产品代码。</span><span class="sxs-lookup"><span data-stu-id="e14d3-146">**Note** The APPGUID parameter references the product code of the App-V client that you install or upgrade to.</span></span> <span data-ttu-id="e14d3-147">产品代码对于每个 setup.msi 都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="e14d3-147">The product code is unique for each setup.msi.</span></span> <span data-ttu-id="e14d3-148">可以使用 Orca 数据库编辑器或类似工具检查 Windows 安装程序文件并确定产品代码。</span><span class="sxs-lookup"><span data-stu-id="e14d3-148">You can use the Orca database editor or similar tool to examine Windows Installer files and determine the product code.</span></span> <span data-ttu-id="e14d3-149">此步骤对于 App-v 4.5 CU1 的所有安装或升级都是必需的。</span><span class="sxs-lookup"><span data-stu-id="e14d3-149">This step is required for all installs or upgrades to App-V4.5 CU1.</span></span>

 

### <a href="" id="some-applications-might-fail-to-install-during-the-monitoring-phase-when-sequencing-on-windows-7-beta--"></a><span data-ttu-id="e14d3-150">在 Windows7 Beta 上排序时，某些应用程序可能无法在监视阶段进行安装</span><span class="sxs-lookup"><span data-stu-id="e14d3-150">Some applications might fail to install during the monitoring phase when sequencing on Windows7 Beta</span></span>

<span data-ttu-id="e14d3-151">当在 Windows7 Beta 或装有 Windows Installer 5.0 的计算机上进行排序时，某些应用程序可能无法在监视阶段安装。</span><span class="sxs-lookup"><span data-stu-id="e14d3-151">When sequencing on Windows7 Beta or on a computer with Windows Installer5.0, some applications might fail to install during the monitoring phase.</span></span>

<span data-ttu-id="e14d3-152">WORKAROUNDYou 必须手动授予 Everyone 组对以下注册表项的 "完全控制" 权限：</span><span class="sxs-lookup"><span data-stu-id="e14d3-152">WORKAROUNDYou must manually grant the Everyone group Full Control permissions to the following registry key:</span></span>

    HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\SystemGuard

<span data-ttu-id="e14d3-153">**重要提示** 必须使用 "**高级**" 按钮设置 "包括从该对象的父对象继承的权限" 选项。</span><span class="sxs-lookup"><span data-stu-id="e14d3-153">**Important** You must use the **Advanced** button to set the “Include inheritable permissions from this object’s parent” option.</span></span>

 

### <span data-ttu-id="e14d3-154">Windows7 Beta 上的排序时无法保存程序包</span><span class="sxs-lookup"><span data-stu-id="e14d3-154">Unable to save packages when sequencing on Windows7 Beta</span></span>

<span data-ttu-id="e14d3-155">在 Windows7 Beta 上进行排序时，你可能无法保存已排序的程序包，因为发生共享冲突。</span><span class="sxs-lookup"><span data-stu-id="e14d3-155">When sequencing on Windows7 Beta, you might be unable to save your sequenced package because of a sharing violation.</span></span>

<span data-ttu-id="e14d3-156">WORKAROUNDAs 在 Microsoft Application Virtualization 4.5 排序指南的 "最佳做法" 部分中指定（请参阅 <https://go.microsoft.com/fwlink/?LinkId=144108> ），在开始排序之前，必须关闭并禁用以下软件程序：</span><span class="sxs-lookup"><span data-stu-id="e14d3-156">WORKAROUNDAs specified in the best practices section of the Microsoft Application Virtualization4.5 Sequencing Guide (see <https://go.microsoft.com/fwlink/?LinkId=144108>), you must shutdown and disable the following software programs before you begin sequencing:</span></span>

-   <span data-ttu-id="e14d3-157">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="e14d3-157">Windows Defender</span></span>

-   <span data-ttu-id="e14d3-158">防病毒软件</span><span class="sxs-lookup"><span data-stu-id="e14d3-158">Antivirus software</span></span>

-   <span data-ttu-id="e14d3-159">磁盘碎片整理软件</span><span class="sxs-lookup"><span data-stu-id="e14d3-159">Disk defragmentation software</span></span>

-   <span data-ttu-id="e14d3-160">Windows 搜索</span><span class="sxs-lookup"><span data-stu-id="e14d3-160">Windows Search</span></span>

-   <span data-ttu-id="e14d3-161">任何打开的 Windows 资源管理器会话</span><span class="sxs-lookup"><span data-stu-id="e14d3-161">Any open Windows Explorer session</span></span>

<span data-ttu-id="e14d3-162">此外，如果在序列化工作站上运行 Microsoft 更新以在程序包更新过程中捕获更新，则需要在开始先后顺序之前添加 "C:\\Windows\\SoftwareDistribution" 作为 VFS 排除。</span><span class="sxs-lookup"><span data-stu-id="e14d3-162">In addition, if you have Microsoft Update running on the sequencing station to capture updates during the package update process, you will need to add “C:\\Windows\\SoftwareDistribution” as a VFS exclusion before you start sequencing.</span></span>

### <span data-ttu-id="e14d3-163">在序列化 .NET Framework 时提高性能</span><span class="sxs-lookup"><span data-stu-id="e14d3-163">Improving performance when sequencing the .NET Framework</span></span>

<span data-ttu-id="e14d3-164">对 .NET Framework 进行排序时，你可能会遇到性能降低的系统性能，因为 Microsoft .NET Framework NGEN 服务尝试将程序集作为后台任务进行预编译。</span><span class="sxs-lookup"><span data-stu-id="e14d3-164">When sequencing the .NET Framework, you might experience reduced system performance because the Microsoft .NET Framework NGEN service attempts to precompile assemblies as a background task.</span></span>

<span data-ttu-id="e14d3-165">WORKAROUNDWhen 序列化 .NET Framework 后，在完成监视阶段后禁用 Microsoft .NET Framework NGEN 服务（mscorsvw.exe）。</span><span class="sxs-lookup"><span data-stu-id="e14d3-165">WORKAROUNDWhen sequencing the .NET Framework, disable the Microsoft .NET Framework NGEN service (mscorsvw.exe) after completing the monitoring phase.</span></span> <span data-ttu-id="e14d3-166">你必须使用 Sequencer 中的 "**虚拟服务**" 选项卡，并将启动类型更改为 "已禁用"。</span><span class="sxs-lookup"><span data-stu-id="e14d3-166">You must use the **Virtual Services** tab in the Sequencer and change the startup type to disabled.</span></span>

### <span data-ttu-id="e14d3-167">Windows7 任务栏的互操作性问题</span><span class="sxs-lookup"><span data-stu-id="e14d3-167">Interoperability issues with the Windows7 Taskbar</span></span>

<span data-ttu-id="e14d3-168">在 Windows7 上运行应用程序虚拟化客户端时，Windows7 任务栏不会将虚拟应用程序的多个实例折叠到一个任务栏按钮中。</span><span class="sxs-lookup"><span data-stu-id="e14d3-168">When you run the Application Virtualization Client on Windows7, the Windows7 taskbar does not collapse multiple instances of a virtual application into a single taskbar button.</span></span> <span data-ttu-id="e14d3-169">此外，右键单击虚拟应用程序的任务栏按钮时，不会显示跳转列表，除非应用程序已固定到 Windows7 任务栏。</span><span class="sxs-lookup"><span data-stu-id="e14d3-169">In addition, jump Lists do not appear when you right-click a taskbar button of a virtual application, unless the application has been pinned to the Windows7 taskbar.</span></span>

### <span data-ttu-id="e14d3-170">卸载 Microsoft Application Virtualization 客户端时，将删除与执行卸载的用户相关联的用户设置</span><span class="sxs-lookup"><span data-stu-id="e14d3-170">When you uninstall the Microsoft Application Virtualization Client, user settings associated with the user performing the uninstall will be deleted</span></span>

<span data-ttu-id="e14d3-171">卸载 Microsoft Application Virtualization 客户端时，Windows Installer 将从当前用户的配置文件中删除应用程序虚拟化设置。</span><span class="sxs-lookup"><span data-stu-id="e14d3-171">When you uninstall the Microsoft Application Virtualization Client, the Windows Installer will remove Application Virtualization settings from the current user's profile.</span></span> <span data-ttu-id="e14d3-172">如果你的计算机使用漫游配置文件，请不要使用你的个人网络帐户卸载客户端，因为它将删除你的所有计算机上的虚拟应用程序的设置。</span><span class="sxs-lookup"><span data-stu-id="e14d3-172">If your computer uses roaming profiles, do not use your personal network account to uninstall the client because it will remove settings for your virtual applications on all of your computers.</span></span>

<span data-ttu-id="e14d3-173">WORKAROUNDYou 应使用不用于运行虚拟应用程序的管理帐户来执行 App-v 客户端卸载。</span><span class="sxs-lookup"><span data-stu-id="e14d3-173">WORKAROUNDYou should perform the App-V Client uninstall with an administrative account that is not used for running virtual applications.</span></span>

### <span data-ttu-id="e14d3-174">在运行顺序向导时必须保存在虚拟文件系统和虚拟注册表选项卡上所做的编辑</span><span class="sxs-lookup"><span data-stu-id="e14d3-174">Edits made on the virtual file system and virtual registry tabs must be saved while running the Sequencing wizard</span></span>

<span data-ttu-id="e14d3-175">如果打开程序包以执行升级，或者已使用新程序包运行顺序向导，并且在虚拟文件系统或虚拟注册表选项卡中对该包进行了更改，这些更改不会自动保存。</span><span class="sxs-lookup"><span data-stu-id="e14d3-175">If you open a package to perform an upgrade or have already run the Sequencing wizard with a new package and you make changes to the package in the virtual file system or virtual registry tabs, those changes are not automatically saved.</span></span>

<span data-ttu-id="e14d3-176">在重新运行向导之前 WORKAROUNDSave 更改，以确保它们反映在向导的虚拟环境中。</span><span class="sxs-lookup"><span data-stu-id="e14d3-176">WORKAROUNDSave the changes before re-running the wizard, to ensure that they are reflected inside the wizard’s virtual environment.</span></span>

### <span data-ttu-id="e14d3-177">必须从提升的命令提示符运行命令行排序器</span><span class="sxs-lookup"><span data-stu-id="e14d3-177">Command-line Sequencer must be run from an elevated command prompt</span></span>

<span data-ttu-id="e14d3-178">使用命令行排序器时，它不会提示提升。</span><span class="sxs-lookup"><span data-stu-id="e14d3-178">When you use the command-line Sequencer, it does not prompt for elevation.</span></span>

<span data-ttu-id="e14d3-179">使用提升的命令提示符 WORKAROUNDRun 命令行排序器。</span><span class="sxs-lookup"><span data-stu-id="e14d3-179">WORKAROUNDRun the command-line Sequencer using an elevated command prompt.</span></span>

### <span data-ttu-id="e14d3-180">分布式环境中的服务器管理控制台配置</span><span class="sxs-lookup"><span data-stu-id="e14d3-180">Server Management Console configuration in distributed environments</span></span>

<span data-ttu-id="e14d3-181">如果需要将管理组件安装到主应用程序虚拟化发布和流式服务器之外的系统上，则服务器安装支持在正确配置的主应用程序虚拟化服务器的不同服务器上安装管理控制台和 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="e14d3-181">If you need to install management components onto systems other than the primary Application Virtualization publishing and streaming server, the server install supports installing our management console and Web service on separate servers from the primary Application Virtualization Server when properly configured.</span></span>

<span data-ttu-id="e14d3-182">若要跨多台服务器分发管理组件，必须在安装了 Web 服务的服务器上启用 Kerberos 委派。</span><span class="sxs-lookup"><span data-stu-id="e14d3-182">To distribute the management components across multiple servers, Kerberos delegation must be enabled on the server where the Web service is installed.</span></span>

### <span data-ttu-id="e14d3-183">OSD 文件中的短路径变量名称可能会导致错误</span><span class="sxs-lookup"><span data-stu-id="e14d3-183">Short path variable names in OSD files can cause errors</span></span>

<span data-ttu-id="e14d3-184">如果收到错误 450478-1F702339-0000010B "目录名称无效" 在客户端上启动虚拟应用程序时，OSD 中的变量可能设置错误。</span><span class="sxs-lookup"><span data-stu-id="e14d3-184">If you receive error 450478-1F702339-0000010B “The directory name is invalid” when starting a virtual application on the client, it is possible that the variable in the OSD is set incorrectly.</span></span> <span data-ttu-id="e14d3-185">如果应用程序的安装程序在排序期间设置短路径名，则可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="e14d3-185">This can happen if the application’s installer sets a short path name during sequencing.</span></span>

<span data-ttu-id="e14d3-186">WORKAROUNDRemove OSD 文件中存在的任何 CSIDL 变量的尾随波形符。</span><span class="sxs-lookup"><span data-stu-id="e14d3-186">WORKAROUNDRemove the trailing tilde from any CSIDL variable that exists in the OSD file.</span></span>

### <a href="" id="correct-syntax-for-decodepath-parameter-for-command-line-sequencer-"></a><span data-ttu-id="e14d3-187">命令行 Sequencer 的 DECODEPATH 参数的正确语法</span><span class="sxs-lookup"><span data-stu-id="e14d3-187">Correct syntax for DECODEPATH parameter for command-line Sequencer</span></span>

<span data-ttu-id="e14d3-188">在命令行 Sequencer 中，打开要升级的程序包并将其解码到 Q 驱动器的根时， *DECODEPATH*参数的语法不应包含尾部斜杠。</span><span class="sxs-lookup"><span data-stu-id="e14d3-188">In the command-line Sequencer, when opening a package for upgrade and decoding it to the root of the Q drive, the syntax for the *DECODEPATH* parameter should not include a trailing slash.</span></span>

<span data-ttu-id="e14d3-189">WORKAROUNDYou 可以使用**Q：** 而不是**Q:\\** （省略结尾的 "\" 字符）。</span><span class="sxs-lookup"><span data-stu-id="e14d3-189">WORKAROUNDYou can use **Q:** rather than **Q:\\** (omitting the trailing “\\” character).</span></span>

### <a href="" id="when-upgrading-4-2-packages--you-encounter-problems-caused-by-windows-installer-files-in-the-virtual-file-system-"></a><span data-ttu-id="e14d3-190">升级4.2 程序包时，遇到由虚拟文件系统中的 Windows Installer 文件导致的问题</span><span class="sxs-lookup"><span data-stu-id="e14d3-190">When upgrading4.2 packages, you encounter problems caused by Windows Installer files in the Virtual File System</span></span>

<span data-ttu-id="e14d3-191">从4.2 升级程序包时，可能会遇到与在4.2 中和在序列化工作站上本地安装的 Windows installer 库中的 Windows Installer 系统文件不匹配的问题。</span><span class="sxs-lookup"><span data-stu-id="e14d3-191">When upgrading a package from4.2, you might experience issues relating to a mismatch of Windows Installer system files that were included by default in4.2 and the Windows Installer libraries locally installed on your Sequencing workstation.</span></span> <span data-ttu-id="e14d3-192">以下文件位于 CSIDL \ _SYSTEM \：</span><span class="sxs-lookup"><span data-stu-id="e14d3-192">The following files are located in CSIDL\_SYSTEM\\:</span></span>

<span data-ttu-id="e14d3-193">cabinet.dll</span><span class="sxs-lookup"><span data-stu-id="e14d3-193">cabinet.dll</span></span>

<span data-ttu-id="e14d3-194">msi.dll</span><span class="sxs-lookup"><span data-stu-id="e14d3-194">msi.dll</span></span>

<span data-ttu-id="e14d3-195">msiexec.exe</span><span class="sxs-lookup"><span data-stu-id="e14d3-195">msiexec.exe</span></span>

<span data-ttu-id="e14d3-196">msihnd.dll</span><span class="sxs-lookup"><span data-stu-id="e14d3-196">msihnd.dll</span></span>

<span data-ttu-id="e14d3-197">msimsg.dlll</span><span class="sxs-lookup"><span data-stu-id="e14d3-197">msimsg.dlll</span></span>

<span data-ttu-id="e14d3-198">从程序包中 WORKAROUNDDelete 前面的所有文件。</span><span class="sxs-lookup"><span data-stu-id="e14d3-198">WORKAROUNDDelete all of the preceding files from the package.</span></span> <span data-ttu-id="e14d3-199">删除 " **VFS** " 选项卡上的映射以及解码路径中 CSIDL \ _SYSTEM 文件夹中的实际文件。</span><span class="sxs-lookup"><span data-stu-id="e14d3-199">Delete the mappings on the **VFS** tab as well as the actual files in the CSIDL\_SYSTEM folder in your decode path.</span></span>

### <a href="" id="on-windows-xp--client-install-logging-is-not-enabled-by-default-"></a><span data-ttu-id="e14d3-200">在 WindowsXP 上，默认情况下不启用客户端安装日志记录</span><span class="sxs-lookup"><span data-stu-id="e14d3-200">On WindowsXP, client install logging is not enabled by default</span></span>

<span data-ttu-id="e14d3-201">在安装客户端时，为了确保捕获任何安装错误以进行故障排除，应使用命令行启用日志记录。</span><span class="sxs-lookup"><span data-stu-id="e14d3-201">When installing the client, to ensure that any install errors are captured for troubleshooting purposes, you should enable logging by using the command line.</span></span>

<span data-ttu-id="e14d3-202">WORKAROUNDAdd 参数 */l\ \* vx！ log.txt*到命令行，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="e14d3-202">WORKAROUNDAdd the parameter */l\*vx! log.txt* to the command line, as shown in the following example:</span></span>

<span data-ttu-id="e14d3-203">setup.exe/s/v "/qn/l\ \* vx！</span><span class="sxs-lookup"><span data-stu-id="e14d3-203">setup.exe /s /v”/qn /l\*vx!</span></span> <span data-ttu-id="e14d3-204">log.txt "</span><span class="sxs-lookup"><span data-stu-id="e14d3-204">log.txt”</span></span>

<span data-ttu-id="e14d3-205">msiexec.exe/i setup.msi/qn/l\ \* vx！</span><span class="sxs-lookup"><span data-stu-id="e14d3-205">msiexec.exe /i setup.msi /qn /l\*vx!</span></span> <span data-ttu-id="e14d3-206">log.txt</span><span class="sxs-lookup"><span data-stu-id="e14d3-206">log.txt</span></span>

<span data-ttu-id="e14d3-207">或者，你可以将注册表项设置为以下值：</span><span class="sxs-lookup"><span data-stu-id="e14d3-207">Alternatively, you can set the registry key to the following value:</span></span>

<span data-ttu-id="e14d3-208">\ [HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Policies\\Microsoft\\Windows\\Installer\] "日志记录" = "voicewarmupx！"</span><span class="sxs-lookup"><span data-stu-id="e14d3-208">\[HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Policies\\Microsoft\\Windows\\Installer\] "Logging"="voicewarmupx!"</span></span>

### <span data-ttu-id="e14d3-209">要使 Kerberos 身份验证正常工作，必须为 IIS 注册服务主体名称（Spn）</span><span class="sxs-lookup"><span data-stu-id="e14d3-209">For Kerberos authentication to work, Service Principal Names (SPNs) must be registered for IIS</span></span>

<span data-ttu-id="e14d3-210">当将 IIS 6.0 或7.0 用于图标或 OSD 文件检索以及程序包流时，必须按如下所示注册 Spn：</span><span class="sxs-lookup"><span data-stu-id="e14d3-210">When using IIS6.0 or7.0 for icon or OSD file retrieval and streaming of packages, for Kerberos authentication to be enabled, the SPNs must be registered as follows:</span></span>

-   <span data-ttu-id="e14d3-211">在 IIS 服务器上，使用 "SETSPN.EXE 资源工具包" 工具运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="e14d3-211">On the IIS server, run the following commands by using the SETSPN.EXE Resource Kit tool.</span></span> <span data-ttu-id="e14d3-212">必须使用服务器完全限定的域名（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="e14d3-212">The server fully qualified domain name (FQDN) must be used.</span></span>

    <span data-ttu-id="e14d3-213">Setspn-r SOFTGRID/ &lt; 服务器 FQDN&gt;</span><span class="sxs-lookup"><span data-stu-id="e14d3-213">Setspn -r SOFTGRID/&lt;Server FQDN&gt;</span></span>

    <span data-ttu-id="e14d3-214">Setspn-r HTTP/ &lt; 服务器 FQDN&gt;</span><span class="sxs-lookup"><span data-stu-id="e14d3-214">Setspn -r HTTP/&lt;Server FQDN&gt;</span></span>

<span data-ttu-id="e14d3-215">有关详细信息，请参阅 <https://go.microsoft.com/fwlink/?LinkId=131407>。</span><span class="sxs-lookup"><span data-stu-id="e14d3-215">For more information, see <https://go.microsoft.com/fwlink/?LinkId=131407>.</span></span>

### <span data-ttu-id="e14d3-216">从 RC 升级时，客户端日志的默认权限不允许非管理员用户访问日志以进行疑难解答和支持</span><span class="sxs-lookup"><span data-stu-id="e14d3-216">On upgrade from RC, the default permissions on client logs do not allow for non-admin users to access the logs for troubleshooting and support</span></span>

<span data-ttu-id="e14d3-217">应用程序 VirtualizationRC 客户端的客户端日志的默认权限不允许对日志文件进行非管理员访问，并且当客户端重新启动时，对这些日志权限的手动更改将被还原。</span><span class="sxs-lookup"><span data-stu-id="e14d3-217">The default permissions on client logs for the Application VirtualizationRC client did not allow for non-admin access to log files, and manual changes to these log permissions were reverted when clients were restarted.</span></span> <span data-ttu-id="e14d3-218">此功能已在适用于新客户端安装的 RTM 版本中得到更正，但在从 RC 升级时，不会重置现有日志文件上的自定义权限。</span><span class="sxs-lookup"><span data-stu-id="e14d3-218">This has been corrected in the RTM release for new client installs, but on upgrade from RC, the custom permissions on existing log files are not reset.</span></span> <span data-ttu-id="e14d3-219">但是，当创建任何新日志或在日志重置后，这些文件将具有新的默认权限。</span><span class="sxs-lookup"><span data-stu-id="e14d3-219">However, when any new logs are created or after a log reset, the files will have the new default permissions.</span></span>

<span data-ttu-id="e14d3-220">WORKAROUNDAfter 升级、重置现有客户端日志或手动更改其权限。</span><span class="sxs-lookup"><span data-stu-id="e14d3-220">WORKAROUNDAfter the upgrade, reset existing client logs or manually change their permissions.</span></span>

### <span data-ttu-id="e14d3-221">.NET 兼容性更改</span><span class="sxs-lookup"><span data-stu-id="e14d3-221">.NET compatibility changes</span></span>

<span data-ttu-id="e14d3-222">Microsoft Application Virtualization 累积 Update1 支持在 WindowsXP （SP2 或更高版本）上对 .NET Framework 进行排序。</span><span class="sxs-lookup"><span data-stu-id="e14d3-222">Microsoft Application Virtualization Cumulative Update1 supports sequencing the .NET Framework on WindowsXP (SP2 or later).</span></span> <span data-ttu-id="e14d3-223">在使用 app-v 4.5 排序器时，针对 SoftGrid 4.2 写入的 .NET 应用程序的排序例程可能需要更新。</span><span class="sxs-lookup"><span data-stu-id="e14d3-223">Sequencing routines for .NET applications that were written for SoftGrid4.2 might need to be updated when used with the App-V4.5 Sequencer.</span></span> <span data-ttu-id="e14d3-224">有关详细信息和解决方法，请参阅知识文库文章 <https://go.microsoft.com/fwlink/?LinkId=123412> 。</span><span class="sxs-lookup"><span data-stu-id="e14d3-224">For details and workarounds, please refer to the Knowledge Base article at <https://go.microsoft.com/fwlink/?LinkId=123412>.</span></span>

### <a href="" id="after-client-upgrade-from-app-v-4-2--some-applications-are-not-shown-"></a><span data-ttu-id="e14d3-225">从 App-v 4.2 升级客户端后，某些应用程序不会显示</span><span class="sxs-lookup"><span data-stu-id="e14d3-225">After client upgrade from App-V4.2, some applications are not shown</span></span>

<span data-ttu-id="e14d3-226">在日志中检查以下错误： "Application Virtualization 客户端无法解析 OSD 文件"。</span><span class="sxs-lookup"><span data-stu-id="e14d3-226">Check for the following error in the log: ”The Application Virtualization Client could not parse the OSD file”.</span></span> <span data-ttu-id="e14d3-227">Microsoft Application Virtualization 4.5 客户端筛选出包含包含空 OS 标记（ &lt; os &gt; &lt; /OS）的 OSD 文件的应用程序 &gt; 。</span><span class="sxs-lookup"><span data-stu-id="e14d3-227">The Microsoft Application Virtualization4.5 client filters out applications that have an OSD file containing an empty OS tag (&lt;OS&gt;&lt;/OS&gt;).</span></span>

<span data-ttu-id="e14d3-228">WORKAROUNDDelete OSD 文件中的空 OS 标签。</span><span class="sxs-lookup"><span data-stu-id="e14d3-228">WORKAROUNDDelete the empty OS tag from the OSD file.</span></span>

### <span data-ttu-id="e14d3-229">对于某些进程，app-v 服务器需要其防火墙中的免除</span><span class="sxs-lookup"><span data-stu-id="e14d3-229">The App-V server requires exemptions in its firewall for certain processes</span></span>

<span data-ttu-id="e14d3-230">为使服务器正确流出应用程序，服务器的核心进程（包括调度程序）需要通过防火墙访问。</span><span class="sxs-lookup"><span data-stu-id="e14d3-230">For the server to stream applications correctly, the server's core processes, including the dispatcher, need access through the firewall.</span></span>

<span data-ttu-id="e14d3-231">以下进程的服务器防火墙中的 WORKAROUNDSet 免除： sghwsvr.exe 和 sghwdsptr.exe。</span><span class="sxs-lookup"><span data-stu-id="e14d3-231">WORKAROUNDSet exemptions in the server's firewall for the following processes: sghwsvr.exe and sghwdsptr.exe.</span></span> <span data-ttu-id="e14d3-232">这适用于 App-v 管理服务器和 App-v 流式处理服务器。</span><span class="sxs-lookup"><span data-stu-id="e14d3-232">This applies to the App-V Management Server and App-V Streaming Server.</span></span>

### <span data-ttu-id="e14d3-233">需要新的 Visual Basic 运行时的序列化程序包可能失败</span><span class="sxs-lookup"><span data-stu-id="e14d3-233">Sequencing packages that require new Visual Basic runtimes might fail</span></span>

<span data-ttu-id="e14d3-234">如果在安装了较早版本的 VBruntime 的系统上对使用较新版本的 Visual Basic （VB）运行时序列化程序包，则当你尝试使用程序包时，可能会看到崩溃或其他意外行为。</span><span class="sxs-lookup"><span data-stu-id="e14d3-234">If you sequence a package that uses a newer version of a Visual Basic (VB) runtime on a system where an older version of the VBruntime is installed, you might see a crash or other unexpected behavior when you try to use your package.</span></span> <span data-ttu-id="e14d3-235">例如，如果你尝试将 Microsoft Money2007 （使用 VBruntime 的版本6.00.9782）用于6.00.9690 的版本 VBruntime 的 WindowsXP 系统，则当你尝试在具有旧 WindowsXP 的其他 VBruntime 系统上运行时，你可能会在发票设计器中看到崩溃。</span><span class="sxs-lookup"><span data-stu-id="e14d3-235">For example, if you try to sequence Microsoft Money2007, which uses version6.00.9782 of the VBruntime, on a WindowsXP system with version6.00.9690 of the VBruntime, you might see a crash in the Invoice Designer when you try to run it on another WindowsXP system with that older VBruntime.</span></span>

<span data-ttu-id="e14d3-236">WORKAROUNDAfter 在序列化计算机上安装应用程序，但仍在监视时，将正确的（较新的） VBruntime 复制到程序包中从可执行文件开始的目录。</span><span class="sxs-lookup"><span data-stu-id="e14d3-236">WORKAROUNDAfter installing the application on the sequencing computer, while still monitoring, copy the correct (newer) VBruntime to the directory in the package from where the executable is started.</span></span> <span data-ttu-id="e14d3-237">这允许序列化的应用程序在启动时查找 VBruntime 的预期版本。</span><span class="sxs-lookup"><span data-stu-id="e14d3-237">This allows the sequenced application to find the expected version of the VBruntime when it is started.</span></span>

<span data-ttu-id="e14d3-238">**重要提示** 此问题已在 Microsoft Application Virtualization 4.5 累积 Update1 中得到修复。</span><span class="sxs-lookup"><span data-stu-id="e14d3-238">**Important** This issue has been fixed in Microsoft Application Virtualization4.5 Cumulative Update1.</span></span>

 

### <span data-ttu-id="e14d3-239">当服务器安装程序在静默模式下运行时，它不会正确检查 MSXML6</span><span class="sxs-lookup"><span data-stu-id="e14d3-239">When the server installer is run in silent mode, it does not correctly check for MSXML6</span></span>

<span data-ttu-id="e14d3-240">App-v 管理服务器依赖于 MSXML6。</span><span class="sxs-lookup"><span data-stu-id="e14d3-240">The App-V Management Server depends on MSXML6.</span></span> <span data-ttu-id="e14d3-241">但是，如果你在静默模式下运行安装程序（例如，在尚未安装 MSXML6 的系统上使用命令 "msiexec-i setup.msi/qn"），则安装程序不会注意缺少的依赖项，也不会安装。</span><span class="sxs-lookup"><span data-stu-id="e14d3-241">However, if you run the installer in silent mode—for example, by using the command “msiexec -i setup.msi /qn” on a system where MSXML6 is not already installed—the installer does not notice the missing dependency and installs anyway.</span></span> <span data-ttu-id="e14d3-242">最常见的结果是，当客户尝试从 App-v 管理服务器刷新发布信息时，它们将看到失败。</span><span class="sxs-lookup"><span data-stu-id="e14d3-242">The most common result is that when clients attempt to refresh publishing information from the App-V Management Server, they will see failures.</span></span>

<span data-ttu-id="e14d3-243">WORKAROUNDVerify 在尝试安装 App-v 管理服务器的静默安装之前，系统上已安装 MSXML6。</span><span class="sxs-lookup"><span data-stu-id="e14d3-243">WORKAROUNDVerify that MSXML6 is installed on the system before attempting a silent install of the App-V Management Server.</span></span>

### <span data-ttu-id="e14d3-244">尝试连接到应用程序虚拟化管理控制台时出现错误代码000C800</span><span class="sxs-lookup"><span data-stu-id="e14d3-244">Error code 000C800 when attempting to connect to the Application Virtualization Management Console</span></span>

<span data-ttu-id="e14d3-245">在应用程序虚拟化管理服务服务器上不是本地管理员的应用程序虚拟化管理员将在尝试连接到应用程序虚拟化管理控制台时收到错误（错误代码：000C800），并且 sftmmc 条目将指示对 SftMgmt 的访问权限被拒绝。</span><span class="sxs-lookup"><span data-stu-id="e14d3-245">An Application Virtualization administrator who is not a local admin on the Application Virtualization Management Service server will receive an error (Error code: 000C800) when attempting to connect to the Application Virtualization Management Console, and the sftmmc.log entry will indicate that access to SftMgmt.udl is denied.</span></span> <span data-ttu-id="e14d3-246">若要成功连接到应用程序虚拟化管理控制台，在应用程序虚拟化管理服务服务器上不是本地管理员的应用程序虚拟化管理员必须至少具有 SftMgmt 文件的 "读取" 和 "执行" 访问权限。</span><span class="sxs-lookup"><span data-stu-id="e14d3-246">To successfully connect to the Application Virtualization Management Console, an Application Virtualization administrator who is not a local admin on the Application Virtualization Management Service server must have at least read and execute access to the SftMgmt.udl file.</span></span>

<span data-ttu-id="e14d3-247">应用程序虚拟化管理员必须在%systemdrive%\\Program Files\\Microsoft System Center App Virt Management Server\\App Virt 管理服务 "下为 SftMgmt 文件授予" 读取 "和" 执行 "权限。</span><span class="sxs-lookup"><span data-stu-id="e14d3-247">The Application Virtualization administrators must be given read and execute permissions to the SftMgmt.UDL file under %systemdrive%\\Program Files\\Microsoft System Center App Virt Management Server\\App Virt Management Service.</span></span>

### <span data-ttu-id="e14d3-248">当与 KEEPCURRENTSETTINGS = 1 结合使用时，将忽略客户端安装程序命令行参数</span><span class="sxs-lookup"><span data-stu-id="e14d3-248">Client installer command-line parameters are ignored when used in conjunction with KEEPCURRENTSETTINGS=1</span></span>

<span data-ttu-id="e14d3-249">与 KEEPCURRENTSETTINGS = 1 结合使用时，将忽略以下客户端安装程序命令行参数： SWICACHESIZE、MINFREESPACEMB、ALLOWINDEPENDENTFILESTREAMING、APPLICATIONSOURCEROOT、ICONSOURCEROOT、OSDSOURCEROOT、SYSTEMEVENTLOGLEVEL、SWIGLOBALDATA、DOTIMEOUTMINUTES、SWIFSDRIVE、AUTOLOADTARGET、AUTOLOADTRIGGERS、SWIUSERDATA 和 REQUIRESECURECONNECTION。</span><span class="sxs-lookup"><span data-stu-id="e14d3-249">When used in conjunction with KEEPCURRENTSETTINGS=1, the following client installer command-line parameters are ignored: SWICACHESIZE, MINFREESPACEMB, ALLOWINDEPENDENTFILESTREAMING, APPLICATIONSOURCEROOT, ICONSOURCEROOT, OSDSOURCEROOT, SYSTEMEVENTLOGLEVEL, SWIGLOBALDATA, DOTIMEOUTMINUTES, SWIFSDRIVE, AUTOLOADTARGET, AUTOLOADTRIGGERS, SWIUSERDATA, and REQUIRESECURECONNECTION.</span></span>

<span data-ttu-id="e14d3-250">WORKAROUNDIf 要保留的设置，请使用 KEEPCURRENTSETTINGS = 1，然后在部署后设置其他参数。</span><span class="sxs-lookup"><span data-stu-id="e14d3-250">WORKAROUNDIf you have settings you want to retain, use KEEPCURRENTSETTINGS=1 and then set the other parameters after deployment.</span></span> <span data-ttu-id="e14d3-251">App-v ADM 模板可用于设置以下客户端设置： APPLICATIONSOURCEROOT、ICONSOURCEROOT、OSDSOURCEROOT、AUTOLOADTARGET、AUTOLOADTRIGGERS、DOTIMEOUTMINUTES 和 ALLOWINDEPENDENTFILESTREAMING。</span><span class="sxs-lookup"><span data-stu-id="e14d3-251">The App-V ADM Template can be used to set the following client settings: APPLICATIONSOURCEROOT, ICONSOURCEROOT, OSDSOURCEROOT, AUTOLOADTARGET, AUTOLOADTRIGGERS, DOTIMEOUTMINUTES, and ALLOWINDEPENDENTFILESTREAMING.</span></span> <span data-ttu-id="e14d3-252">可以在上找到 ADM 模板 <https://go.microsoft.com/fwlink/?LinkId=121835> 。</span><span class="sxs-lookup"><span data-stu-id="e14d3-252">The ADM Template can be found at <https://go.microsoft.com/fwlink/?LinkId=121835>.</span></span>

### <span data-ttu-id="e14d3-253">通过 Symantec Endpoint Protection 初始化虚拟应用程序时出错</span><span class="sxs-lookup"><span data-stu-id="e14d3-253">Error initializing virtual applications with Symantec Endpoint Protection</span></span>

<span data-ttu-id="e14d3-254">在启用了 "应用程序和设备控制" 功能的情况下使用 Symantec Endpoint Protection 时，虚拟应用程序可能无法启动，并出现错误 "应用程序未能正确初始化（0xc000007b）"。</span><span class="sxs-lookup"><span data-stu-id="e14d3-254">When using Symantec Endpoint Protection with the Application and Device Control feature enabled, virtual applications might fail to start, with the error “The application failed to initialize properly (0xc000007b)”.</span></span> <span data-ttu-id="e14d3-255">有关详细信息和解决方法，请参阅知识文库文章 <https://go.microsoft.com/fwlink/?LinkId=125851> 。</span><span class="sxs-lookup"><span data-stu-id="e14d3-255">For details and workarounds, please refer to the Knowledge Base article at <https://go.microsoft.com/fwlink/?LinkId=125851>.</span></span>

<span data-ttu-id="e14d3-256">**重要提示** 此问题已在 Microsoft Application Virtualization 4.5 累积 Update1 中得到修复。</span><span class="sxs-lookup"><span data-stu-id="e14d3-256">**Important** This issue has been fixed in Microsoft Application Virtualization4.5 Cumulative Update1.</span></span>

 

## <span data-ttu-id="e14d3-257">发行说明版权信息</span><span class="sxs-lookup"><span data-stu-id="e14d3-257">Release Notes Copyright Information</span></span>


<span data-ttu-id="e14d3-258">本文档中的信息（包括 URL 和其他 Internet 网站引用）如有更改，恕不另行通知，仅供参考。</span><span class="sxs-lookup"><span data-stu-id="e14d3-258">Information in this document, including URL and other Internet Web site references, is subject to change without notice, and is provided for informational purposes only.</span></span> <span data-ttu-id="e14d3-259">本文档使用或结果的全部风险由用户承担，Microsoft Corporation 不作任何明示或暗示的保证。</span><span class="sxs-lookup"><span data-stu-id="e14d3-259">The entire risk of the use or results of the use of this document remains with the user, and Microsoft Corporation makes no warranties, either express or implied.</span></span> <span data-ttu-id="e14d3-260">此处所述的示例公司、组织、产品、人员和事件纯属虚构。</span><span class="sxs-lookup"><span data-stu-id="e14d3-260">The example companies, organizations, products, people and events depicted herein are fictitious.</span></span> <span data-ttu-id="e14d3-261">无意与任何真实公司、组织、产品、人员或事件关联，也不应进行任何推测。</span><span class="sxs-lookup"><span data-stu-id="e14d3-261">No association with any real company, organization, product, person or event is intended or should be inferred.</span></span> <span data-ttu-id="e14d3-262">用户有责任遵守所有适用的版权法。</span><span class="sxs-lookup"><span data-stu-id="e14d3-262">Complying with all applicable copyright laws is the responsibility of the user.</span></span> <span data-ttu-id="e14d3-263">在不限制版权法规定的权利的情况下，未经 Microsoft Corporation 明确书面允许，不得出于任何目的，以任何形式或通过任何方式（电子、机械、影印、录制或其他方式）对本文档中的任何内容进行复制、传输或者将其存储到或引入到检索系统。</span><span class="sxs-lookup"><span data-stu-id="e14d3-263">Without limiting the rights under copyright, no part of this document may be reproduced, stored in or introduced into a retrieval system, or transmitted in any form or by any means (electronic, mechanical, photocopying, recording, or otherwise), or for any purpose, without the express written permission of Microsoft Corporation.</span></span>

<span data-ttu-id="e14d3-264">Microsoft 可能拥有涉及本文档中的主题的专利、专利申请、商标、版权和其他知识产权。</span><span class="sxs-lookup"><span data-stu-id="e14d3-264">Microsoft may have patents, patent applications, trademarks, copyrights, or other intellectual property rights covering subject matter in this document.</span></span> <span data-ttu-id="e14d3-265">除非得到 Microsoft 的明确书面许可，否则本文档不授予用户任何使用这些专利、商标、版权或其他知识产权的许可。</span><span class="sxs-lookup"><span data-stu-id="e14d3-265">Except as expressly provided in any written license agreement from Microsoft, the furnishing of this document does not give you any license to these patents, trademarks, copyrights, or other intellectual property.</span></span>



<span data-ttu-id="e14d3-266">Microsoft、MS-DOS、Windows、WindowsServer、Windows Vista、Active Directory 和 ActiveSync 是 U.S.A. 和/或其他国家/地区的 MicrosoftCorporation 的注册商标或商标。</span><span class="sxs-lookup"><span data-stu-id="e14d3-266">Microsoft, MS-DOS, Windows, WindowsServer, Windows Vista, Active Directory, and ActiveSync are either registered trademarks or trademarks of MicrosoftCorporation in the U.S.A. and/or other countries.</span></span>

<span data-ttu-id="e14d3-267">此处提及的真实公司和产品的名称可能是其各自所有者的商标。</span><span class="sxs-lookup"><span data-stu-id="e14d3-267">The names of actual companies and products mentioned herein may be the trademarks of their respective owners.</span></span>

 

 





