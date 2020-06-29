---
title: 规划应用程序操作系统兼容性
description: 规划应用程序操作系统兼容性
author: dansimp
ms.assetid: cdb0a7f0-9da4-4562-8277-12972eb0fea8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5b10da2c870e5ddc32098136225515cdd0523809
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803774"
---
# <span data-ttu-id="97788-103">规划应用程序操作系统兼容性</span><span class="sxs-lookup"><span data-stu-id="97788-103">Planning for Application Operating System Compatibility</span></span>


<span data-ttu-id="97788-104">本主题帮助确定如何解决应用程序操作系统兼容性问题，并讨论 Microsoft 企业版桌面虚拟化（MED-V）2.0 作为你的组织的解决方案的工作方式。</span><span class="sxs-lookup"><span data-stu-id="97788-104">This topic helps determine how to resolve application operating system compatibility issues, and discusses how Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 works as a solution for your organization.</span></span>

<span data-ttu-id="97788-105">本主题讨论 MED-V 的业务要求，并将 MED-V 与 Windows XP 模式和 Microsoft Application Virtualization （App-v）进行比较：</span><span class="sxs-lookup"><span data-stu-id="97788-105">This topic discusses the business requirements for MED-V and compares MED-V to Windows XP Mode and Microsoft Application Virtualization (App-V):</span></span>

-   [<span data-ttu-id="97788-106">MED-V 的业务要求</span><span class="sxs-lookup"><span data-stu-id="97788-106">Business Requirements for MED-V</span></span>](#bkmk-whenmedv)

-   [<span data-ttu-id="97788-107">MED-V 与 Windows XP 模式的优点</span><span class="sxs-lookup"><span data-stu-id="97788-107">Benefits of MED-V versus Windows XP Mode</span></span>](#bkmk-medvvsxp)

-   [<span data-ttu-id="97788-108">MED-V 与 App-v 的好处</span><span class="sxs-lookup"><span data-stu-id="97788-108">Benefits of MED-V versus App-V</span></span>](#bkmk-medvvsappv)

## <a href="" id="bkmk-whenmedv"></a><span data-ttu-id="97788-109">MED-V 的业务要求</span><span class="sxs-lookup"><span data-stu-id="97788-109">Business Requirements for MED-V</span></span>


<span data-ttu-id="97788-110">当贵公司的 IT 部门确定是否升级到 Windows 7 时，必须注意它的业务线应用程序和基于 web 的业务线应用程序，以确保它们可以在新操作系统上运行。</span><span class="sxs-lookup"><span data-stu-id="97788-110">When your company’s IT department is determining whether to upgrade to Windows 7, it must pay attention to its line-of-business applications and web-based line-of-business applications to make certain that these can run on the new operating system.</span></span> <span data-ttu-id="97788-111">通常，创建这些应用程序和 Url 以使用较早版本的 Windows 或 Internet Explorer 进行工作，并且在新操作系统中尝试使用它们时可能会出现问题。</span><span class="sxs-lookup"><span data-stu-id="97788-111">Often, these applications and URLs were created to work specifically with an older version of Windows or Internet Explorer, and problems can occur when trying to use them in the new operating system.</span></span> <span data-ttu-id="97788-112">Microsoft 提供了多种不同的方法来处理升级时可能出现的各种兼容性问题，例如应用程序兼容性工具包（ACT）和 Windows 7 程序兼容性助手。</span><span class="sxs-lookup"><span data-stu-id="97788-112">Microsoft offers many different methods for handling the various compatibility issues that can occur when you upgrade, such as the Application Compatibility Toolkit (ACT) and the Windows 7 Program Compatibility Assistant.</span></span> <span data-ttu-id="97788-113">即使在所有应用程序都已确定兼容性和修复已确定的情况下，某些应用程序在 Windows 7 上仍无法正常工作，或者太昂贵，无法解决。</span><span class="sxs-lookup"><span data-stu-id="97788-113">But even after all applications have been tested for compatibility and fixes have been determined, some applications still do not work correctly on Windows 7 or are too costly to resolve.</span></span>

<span data-ttu-id="97788-114">通过使用 MED-V，你可以通过运行 Windows XP 的 Windows 虚拟 PC 环境运行这些旧版应用程序。</span><span class="sxs-lookup"><span data-stu-id="97788-114">By using MED-V, you can run these legacy applications through a Windows Virtual PC environment that is running Windows XP.</span></span> <span data-ttu-id="97788-115">由于您不再需要在升级之前在新操作系统上测试和验证这些问题应用程序，因此你的迁移到 Windows 7 的速度将会更快、更快。</span><span class="sxs-lookup"><span data-stu-id="97788-115">Because you no longer have to test and validate these problem applications on the new operating system before upgrading, your migration to Windows 7 is much smoother and quicker.</span></span>

### <span data-ttu-id="97788-116">使用 MED-V 清单</span><span class="sxs-lookup"><span data-stu-id="97788-116">Using MED-V Checklist</span></span>

<span data-ttu-id="97788-117">如果以下任何情况适用于你，请考虑 MED-V：</span><span class="sxs-lookup"><span data-stu-id="97788-117">Consider MED-V if any of the following scenarios apply to you:</span></span>

-   <span data-ttu-id="97788-118">您是大型组织（例如，500用户和更多），拥有与 Microsoft 的企业协议，并计划升级到 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="97788-118">You are a large organization (for example, 500 users and more), have an Enterprise Agreement with Microsoft, and plan to upgrade to Windows 7.</span></span>

-   <span data-ttu-id="97788-119">你已测试你的业务线应用程序并发现与 Windows 7 不兼容的应用程序。</span><span class="sxs-lookup"><span data-stu-id="97788-119">You have tested your line-of-business applications and have found some that are incompatible with Windows 7.</span></span>

-   <span data-ttu-id="97788-120">你已通过升级应用程序或使用 Microsoft 提供的填充（如应用程序兼容性工具包（ACT））解决了其中某些问题应用程序的兼容性问题，但某些应用程序的兼容性问题仍然存在。</span><span class="sxs-lookup"><span data-stu-id="97788-120">You have resolved the compatibility issues for some of these problem applications by upgrading the application or by using a Microsoft-provided shim, such as the Application Compatibility Toolkit (ACT), but compatibility issues remain for some applications.</span></span>

-   <span data-ttu-id="97788-121">你已将 app-v 视为用于传递不兼容的应用程序的选项，并在完成后（即使在实现 App-v 后），你仍然具有必须解决的应用程序操作系统兼容性问题。</span><span class="sxs-lookup"><span data-stu-id="97788-121">You have considered App-V as an option for delivering the incompatible applications and have concluded that even after you implement App-V, you still have application operating system compatibility issues that you must address.</span></span>

-   <span data-ttu-id="97788-122">你已将 Windows XP 模式视为解决方案，并已确定它不是有效的选项，因为：</span><span class="sxs-lookup"><span data-stu-id="97788-122">You have considered Windows XP Mode as a solution and have determined that it is not an efficient option because:</span></span>

    -   <span data-ttu-id="97788-123">你希望能够同时将包含问题应用程序的虚拟映像部署到所有最终用户，而不是单独部署，并让虚拟图像自动加入到域。</span><span class="sxs-lookup"><span data-stu-id="97788-123">You want to be able to deploy virtual images that contain the problem applications to all end users at the same time, instead of individually, and have the virtual images automatically joined to the domain.</span></span>

    -   <span data-ttu-id="97788-124">你已决定管理这些旧式应用程序（实际上是在虚拟上提供），并从一个集中位置（而不是每个最终用户的桌面上）控制 Windows 虚拟 PC 设置。</span><span class="sxs-lookup"><span data-stu-id="97788-124">You have decided it is much more cost effective to manage these legacy applications (that are delivered virtually) and control the Windows Virtual PC settings from a centralized location instead of on each end user’s desktop.</span></span>

    -   <span data-ttu-id="97788-125">你希望能够按比例（而不是按桌面）更新和支持虚拟机。</span><span class="sxs-lookup"><span data-stu-id="97788-125">You want to be able to update and support the virtual machines in scale instead of per desktop.</span></span>

    -   <span data-ttu-id="97788-126">你希望能够将更早版本的 Internet Explorer 中更好地运行的 Url 重定向到虚拟机，并在稍后轻松管理 URL 重定向。</span><span class="sxs-lookup"><span data-stu-id="97788-126">You want the ability to redirect URLs that run better on an older version of Internet Explorer to the virtual machines and to easily manage URL redirection later.</span></span>

-   <span data-ttu-id="97788-127">你已确定它将更加经济高效，并且有助于尽快升级到 Windows 7，并决定推迟解决剩余的应用程序兼容性问题，直到你在 MED-V 中提供了解决方案。</span><span class="sxs-lookup"><span data-stu-id="97788-127">You have determined that it would be more cost effective and helpful to upgrade to Windows 7 as soon as possible and have decided to postpone resolving your remaining application compatibility issues until a later date, knowing that you have a solution available in MED-V.</span></span>

## <a href="" id="bkmk-medvvsxp"></a> <span data-ttu-id="97788-128">MED-V 与 Windows XP 模式的优点</span><span class="sxs-lookup"><span data-stu-id="97788-128">Benefits of MED-V versus Windows XP Mode</span></span>


<span data-ttu-id="97788-129">Windows 虚拟电脑 for Windows 7 允许你在单个设备上同时运行不同版本的操作系统，并且包含在 Windows 7 专业版和更高版本中。</span><span class="sxs-lookup"><span data-stu-id="97788-129">Windows Virtual PC for Windows 7 lets you run different versions of an operating system at the same time on a single device and is included in Windows 7 Professional Edition and higher.</span></span>

<span data-ttu-id="97788-130">通过提供预配置的 Windows XP 映像（可让你创建虚拟 Windows XP 环境），windows XP 模式功能利用 Windows 虚拟 PC。</span><span class="sxs-lookup"><span data-stu-id="97788-130">Windows XP Mode functionality takes advantage of Windows Virtual PC by providing a preconfigured Windows XP image that lets you create a virtual Windows XP environment.</span></span> <span data-ttu-id="97788-131">在此虚拟环境中，你可以手动安装与 Windows 7 不兼容的应用程序，并通过 Windows 虚拟 PC 从桌面无缝运行。</span><span class="sxs-lookup"><span data-stu-id="97788-131">In this virtual environment, you can manually install applications that are incompatible with Windows 7 and that run seamlessly from your desktop through Windows Virtual PC.</span></span>

**<span data-ttu-id="97788-132">通过使用 Windows XP 模式，你可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="97788-132">By using Windows XP Mode, you can do the following:</span></span>**

-   <span data-ttu-id="97788-133">在 Windows 虚拟 PC 中运行的虚拟机内运行与 Windows XP 兼容的应用程序。</span><span class="sxs-lookup"><span data-stu-id="97788-133">Run applications that are compatible with Windows XP inside a virtual machine that runs in Windows Virtual PC.</span></span>

-   <span data-ttu-id="97788-134">将这些应用程序发布到主机的桌面或程序菜单。</span><span class="sxs-lookup"><span data-stu-id="97788-134">Publish these applications to the host’s desktop or Program menu.</span></span>

<span data-ttu-id="97788-135">如果你希望将这些虚拟机作为企业迁移到 Windows 7 的一部分提供，则必须能够快速部署虚拟机、预配和自定义它们，并可轻松地控制其设置和支持这些虚拟机。</span><span class="sxs-lookup"><span data-stu-id="97788-135">When you want to deliver these virtual machines on a large scale as part of an enterprise migration to Windows 7, you must be able to deploy the virtual machines quickly, provision, and customize them efficiently, control their settings, and support them easily.</span></span>

<span data-ttu-id="97788-136">基于 Windows XP 模式构建的 MED-V 提供企业范围的应用程序兼容性。</span><span class="sxs-lookup"><span data-stu-id="97788-136">MED-V builds upon Windows XP Mode to deliver enterprise-wide application compatibility.</span></span> <span data-ttu-id="97788-137">虽然 Windows XP 模式仅限于向个人和小型企业提供虚拟应用程序功能，但 MED-V 允许在整个公司网络中大规模部署预配置的 Windows XP 映像。</span><span class="sxs-lookup"><span data-stu-id="97788-137">Whereas Windows XP mode is limited to providing virtual application functionality to individuals and small businesses, MED-V allows for large-scale deployments of preconfigured Windows XP images throughout your corporate network.</span></span> <span data-ttu-id="97788-138">它为这些虚拟 MED-V 工作区的配置、部署和维护提供了一个企业就绪的管理解决方案。</span><span class="sxs-lookup"><span data-stu-id="97788-138">It gives you an enterprise-ready management solution for the configuration, deployment, and maintenance of these virtual MED-V workspaces.</span></span> <span data-ttu-id="97788-139">MED-V 还为 enterpriseadministrators 提供了一组用于控制图像使用的策略。</span><span class="sxs-lookup"><span data-stu-id="97788-139">MED-V also gives enterpriseadministrators a set of policies to control image use.</span></span> <span data-ttu-id="97788-140">这包括哪些用户将有权访问这些映像中的哪些特定应用程序。</span><span class="sxs-lookup"><span data-stu-id="97788-140">This includes which users will have access to which specific applications within these images.</span></span>

**<span data-ttu-id="97788-141">通过使用 MED-V，您可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="97788-141">By using MED-V, you can do the following:</span></span>**

-   <span data-ttu-id="97788-142">升级到新操作系统，无需测试和解决每个不兼容的应用程序和 URL。</span><span class="sxs-lookup"><span data-stu-id="97788-142">Upgrade to your new operating system without having to test and resolve every incompatible application and URL.</span></span>

-   <span data-ttu-id="97788-143">部署按用户自动加入域和自定义的虚拟 Windows XP 映像。</span><span class="sxs-lookup"><span data-stu-id="97788-143">Deploy virtual Windows XP images that are automatically domain-joined and customized per user.</span></span>

-   <span data-ttu-id="97788-144">为用户预配应用程序和 URL 重定向信息。</span><span class="sxs-lookup"><span data-stu-id="97788-144">Provision applications and URL redirection information to users.</span></span>

-   <span data-ttu-id="97788-145">控制 Windows 虚拟电脑设置。</span><span class="sxs-lookup"><span data-stu-id="97788-145">Control the Windows Virtual PC settings.</span></span>

-   <span data-ttu-id="97788-146">通过监视和疑难解答来维护和支持终结点。</span><span class="sxs-lookup"><span data-stu-id="97788-146">Maintain and support endpoints through monitoring and troubleshooting.</span></span>

-   <span data-ttu-id="97788-147">确保已修补来宾计算机，即使处于暂停状态也是如此。</span><span class="sxs-lookup"><span data-stu-id="97788-147">Ensure that guest computers are patched, even if in a suspended state.</span></span>

-   <span data-ttu-id="97788-148">自动化每用户虚拟机创建和 sysprep 初始化。</span><span class="sxs-lookup"><span data-stu-id="97788-148">Automate per-user virtual machine creation and sysprep initialization.</span></span>

-   <span data-ttu-id="97788-149">轻松诊断主机和来宾计算机上的问题。</span><span class="sxs-lookup"><span data-stu-id="97788-149">Easily diagnose issues on the host and guest computers.</span></span>

-   <span data-ttu-id="97788-150">通过 Windows 虚拟 PC NAT 模式无缝管理连接的来宾计算机。</span><span class="sxs-lookup"><span data-stu-id="97788-150">Seamlessly manage guest computers that are connected through Windows Virtual PC NAT mode.</span></span>

## <a href="" id="bkmk-medvvsappv"></a><span data-ttu-id="97788-151">MED-V 与 App-v 的好处</span><span class="sxs-lookup"><span data-stu-id="97788-151">Benefits of MED-V versus App-V</span></span>


<span data-ttu-id="97788-152">MED-V 和 App-v 是两种截然不同的技术，可轻松协同工作以解决你的应用程序操作系统兼容性问题。</span><span class="sxs-lookup"><span data-stu-id="97788-152">MED-V and App-V are two very different technologies that can easily work together to solve your application operating system compatibility issues.</span></span> <span data-ttu-id="97788-153">通过使用 App-v，你可以为每个应用程序创建一个个性化的程序包，其中每个应用程序都与其他应用程序单独保存。</span><span class="sxs-lookup"><span data-stu-id="97788-153">By using App-V, you create an individualized package for each application, each of which is then kept separate from the others.</span></span> <span data-ttu-id="97788-154">然后，可以将每个虚拟应用程序立即发送到最终用户，这对于 Windows 7 部署策略非常有用。</span><span class="sxs-lookup"><span data-stu-id="97788-154">Each virtual application can then be immediately delivered to the end user, which is very useful for a Windows 7 deployment strategy.</span></span>

<span data-ttu-id="97788-155">MED-V 不单独处理应用程序。</span><span class="sxs-lookup"><span data-stu-id="97788-155">MED-V does not handle applications individually.</span></span> <span data-ttu-id="97788-156">而是在运行 Windows 7 的同一桌面上创建 Windows XP 的其他实例。</span><span class="sxs-lookup"><span data-stu-id="97788-156">Instead, it creates an additional instance of Windows XP on the same desktop that is running Windows 7.</span></span> <span data-ttu-id="97788-157">你可以根据需要在此虚拟图像中安装任意数量的应用程序，并像管理组织中的任何其他桌面一样管理图像。</span><span class="sxs-lookup"><span data-stu-id="97788-157">You can install as many applications as necessary into this virtual image and manage the image just as you would any other desktop in your organization.</span></span>

<span data-ttu-id="97788-158">此外，你可以将 MED-V 与 App-v 结合使用，以便通过使用 MED-V 安装、发布和管理由 App-v 排序的虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="97788-158">In addition, you can use MED-V together with App-V so that virtual applications that are sequenced through App-V are installed, published, and managed by using MED-V.</span></span>

## <span data-ttu-id="97788-159">相关主题</span><span class="sxs-lookup"><span data-stu-id="97788-159">Related topics</span></span>


[<span data-ttu-id="97788-160">定义和规划 MED-V 部署</span><span class="sxs-lookup"><span data-stu-id="97788-160">Define and Plan your MED-V Deployment</span></span>](define-and-plan-your-med-v-deployment.md)

 

 





