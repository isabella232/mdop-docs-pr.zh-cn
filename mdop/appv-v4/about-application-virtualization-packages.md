---
title: 关于 Application Virtualization 程序包
description: 关于 Application Virtualization 程序包
author: dansimp
ms.assetid: 69bd35c1-7af3-43db-931b-3074780aa926
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cfe6df90881ea4179fa8cd224609ca6d28ff5f61
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802475"
---
# <span data-ttu-id="7f2e3-103">关于 Application Virtualization 程序包</span><span class="sxs-lookup"><span data-stu-id="7f2e3-103">About Application Virtualization Packages</span></span>


<span data-ttu-id="7f2e3-104">在应用程序虚拟化中，*程序包*是排序过程的输出。</span><span class="sxs-lookup"><span data-stu-id="7f2e3-104">In Application Virtualization, a *package* is the output of the sequencing process.</span></span> <span data-ttu-id="7f2e3-105">第一次在服务器上部署应用程序时，以及使用新版本升级应用程序时，可以使用程序包。</span><span class="sxs-lookup"><span data-stu-id="7f2e3-105">You use packages when you first deploy applications on your servers and when you upgrade applications with a new version.</span></span> <span data-ttu-id="7f2e3-106">程序包使你能够控制你的应用程序虚拟化管理服务器上的虚拟应用程序版本。</span><span class="sxs-lookup"><span data-stu-id="7f2e3-106">Packages enable you to control virtual application versions on your Application Virtualization Management Servers.</span></span> <span data-ttu-id="7f2e3-107">单个程序包可以包含一个或多个应用程序。</span><span class="sxs-lookup"><span data-stu-id="7f2e3-107">A single package can contain one or more applications.</span></span> <span data-ttu-id="7f2e3-108">每个应用程序包都包含一组自包含的单元文件。</span><span class="sxs-lookup"><span data-stu-id="7f2e3-108">Each application package contains a set of files as a self-contained unit.</span></span>

## <span data-ttu-id="7f2e3-109">管理程序包</span><span class="sxs-lookup"><span data-stu-id="7f2e3-109">Managing Packages</span></span>


<span data-ttu-id="7f2e3-110">在 Sequencer 创建一个或多个应用程序的程序包作为其进程的一部分后，你可以将 Sequencer 生成的文件复制到应用程序虚拟化管理服务器，并使它们可用于流处理。</span><span class="sxs-lookup"><span data-stu-id="7f2e3-110">After the Sequencer creates a package of one or more applications as part of its process, you can copy the Sequencer-generated files to a Application Virtualization Management Server and make them available for streaming.</span></span>

<span data-ttu-id="7f2e3-111">可用包显示在应用程序虚拟化管理控制台左窗格中的**程序包**容器下方。</span><span class="sxs-lookup"><span data-stu-id="7f2e3-111">Available packages appear under the **Packages** container in the left pane of the Application Virtualization Management Console.</span></span> <span data-ttu-id="7f2e3-112">导入带有 Sequencer 项目（SPRJ）文件或开放软件描述符（OSD）文件的应用程序时，将在**程序包**容器中显示相关条目。</span><span class="sxs-lookup"><span data-stu-id="7f2e3-112">When you import an application with a Sequencer Project (SPRJ) file or an Open Software Descriptor (OSD) file, a related entry appears in the **Packages** container.</span></span> <span data-ttu-id="7f2e3-113">在应用程序虚拟化服务器管理控制台中，你可以部署、升级或删除程序包和版本。</span><span class="sxs-lookup"><span data-stu-id="7f2e3-113">From the Application Virtualization Server Management Console, you can then deploy, upgrade, or delete packages and versions of them.</span></span>

<span data-ttu-id="7f2e3-114">每个虚拟应用程序都有一个关联的程序包。</span><span class="sxs-lookup"><span data-stu-id="7f2e3-114">Each virtual application has an associated package.</span></span> <span data-ttu-id="7f2e3-115">此程序包包含以下文件：</span><span class="sxs-lookup"><span data-stu-id="7f2e3-115">This package includes the following files:</span></span>

-   <span data-ttu-id="7f2e3-116">SFT ——将应用程序流式处理到客户端的文件。</span><span class="sxs-lookup"><span data-stu-id="7f2e3-116">SFT—The file that streams the application to clients.</span></span>

-   <span data-ttu-id="7f2e3-117">OSD-开放软件描述符文件包含查找和启动应用程序所需的信息。</span><span class="sxs-lookup"><span data-stu-id="7f2e3-117">OSD—The Open Software Descriptor file contains the information needed to find and launch the application.</span></span>

-   <span data-ttu-id="7f2e3-118">.ICO-图标文件，直观地表示用户界面和快捷方式中的应用程序。</span><span class="sxs-lookup"><span data-stu-id="7f2e3-118">ICO—The icon file that visually represents the application in user interfaces and shortcuts.</span></span>

-   <span data-ttu-id="7f2e3-119">SPRJ-Sequencer 项目文件。</span><span class="sxs-lookup"><span data-stu-id="7f2e3-119">SPRJ—The Sequencer Project file.</span></span>

<span data-ttu-id="7f2e3-120">导入 SPRJ 文件时，默认情况下，所有已排序的应用程序均可供部署，但应用程序不会启用流式处理。</span><span class="sxs-lookup"><span data-stu-id="7f2e3-120">When you import the SPRJ file, all sequenced applications are available for deployment, by default, but the applications are not enabled for streaming.</span></span> <span data-ttu-id="7f2e3-121">你可以选择在程序包中传输所有或部分应用程序。</span><span class="sxs-lookup"><span data-stu-id="7f2e3-121">You can choose to stream all or some of the applications in the package.</span></span> <span data-ttu-id="7f2e3-122">例如，如果已排序并导入 Microsoft Office，则可以选择不部署某些应用程序，例如 "保存我的设置" 向导。</span><span class="sxs-lookup"><span data-stu-id="7f2e3-122">For example, if you sequenced and imported Microsoft Office, you can choose not to deploy some applications, such as the Save My Settings Wizard.</span></span> <span data-ttu-id="7f2e3-123">在这种情况下，右键单击要部署的每个应用程序，选择 "**属性**"，并确保已清除 "**启用**" 框（空白）。</span><span class="sxs-lookup"><span data-stu-id="7f2e3-123">In this case, right-click each application you want to deploy, choose **Properties**, and make sure that the **Enabled** box is cleared (blank).</span></span> <span data-ttu-id="7f2e3-124">只有选中了 "**已启用**" 框的应用程序才会流入客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="7f2e3-124">Only the applications with the **Enabled** box selected will stream to client computers.</span></span>

<span data-ttu-id="7f2e3-125">在 resequence 程序包并生成用于流处理的新 SFT 文件后，您可以通过应用程序虚拟化服务器管理控制台快速轻松地升级旧程序包。</span><span class="sxs-lookup"><span data-stu-id="7f2e3-125">After you resequence a package and produce a new SFT file for streaming, you can upgrade the old package quickly and easily through the Application Virtualization Server Management Console.</span></span>

<span data-ttu-id="7f2e3-126">需要使用 "**程序包**" 节点的唯一操作方案是在为程序包引入新版本（SFT 文件）时。</span><span class="sxs-lookup"><span data-stu-id="7f2e3-126">The only operational scenario that requires you to use the **Packages** node is when you introduce a new version (SFT file) for the package.</span></span> <span data-ttu-id="7f2e3-127">无论何时导入应用程序、为应用程序分配访问权限和许可证等，应用程序虚拟化系统都会在程序包级别跟踪此信息。</span><span class="sxs-lookup"><span data-stu-id="7f2e3-127">Whenever you import applications, assign access and licenses to applications, and so on, the Application Virtualization System tracks this information at the package level.</span></span> <span data-ttu-id="7f2e3-128">这意味着，当你授权用户使用应用程序时，你将授予用户运行同一程序包中的任何应用程序的权限。</span><span class="sxs-lookup"><span data-stu-id="7f2e3-128">This means that when you authorize a user to use an application, you are giving the user permission to run any application in the same package.</span></span>

### <span data-ttu-id="7f2e3-129">程序包版本</span><span class="sxs-lookup"><span data-stu-id="7f2e3-129">Package Version</span></span>

<span data-ttu-id="7f2e3-130">程序包版本由特定的 SFT 文件表示。</span><span class="sxs-lookup"><span data-stu-id="7f2e3-130">A package version is represented by a specific SFT file.</span></span> <span data-ttu-id="7f2e3-131">升级程序包（应用对应用程序的更新或将应用程序添加到程序包）时，将生成新的 SFT 文件。</span><span class="sxs-lookup"><span data-stu-id="7f2e3-131">When you upgrade a package (apply an update to an application or add an application to a package), you generate a new SFT file.</span></span> <span data-ttu-id="7f2e3-132">每次创建新的 SFT 文件时，都将创建一个新的程序包版本。</span><span class="sxs-lookup"><span data-stu-id="7f2e3-132">Each time you create a new SFT file, you are creating a new package version.</span></span>

<span data-ttu-id="7f2e3-133">通过应用程序虚拟化服务器管理控制台导入应用程序时，如果现有程序包和程序包版本尚不存在，则该软件会自动创建该程序包和程序包版本。</span><span class="sxs-lookup"><span data-stu-id="7f2e3-133">When you import applications through the Application Virtualization Server Management Console, the software automatically creates a package and a package version if they do not already exist.</span></span>

## <span data-ttu-id="7f2e3-134">相关主题</span><span class="sxs-lookup"><span data-stu-id="7f2e3-134">Related topics</span></span>


[<span data-ttu-id="7f2e3-135">关于 Application Virtualization 应用程序</span><span class="sxs-lookup"><span data-stu-id="7f2e3-135">About Application Virtualization Applications</span></span>](about-application-virtualization-applications.md)

[<span data-ttu-id="7f2e3-136">关于 Application Virtualization Server Management Console</span><span class="sxs-lookup"><span data-stu-id="7f2e3-136">About the Application Virtualization Server Management Console</span></span>](about-the-application-virtualization-server-management-console.md)

[<span data-ttu-id="7f2e3-137">如何在 Server Management Console 中管理程序包</span><span class="sxs-lookup"><span data-stu-id="7f2e3-137">How to Manage Packages in the Server Management Console</span></span>](how-to-manage-packages-in-the-server-management-console.md)

 

 





