---
title: App-V 5.0 入门
description: App-V 5.0 入门
author: dansimp
ms.assetid: 3e16eafb-ce95-4d06-b214-fe0f4b1b495f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a7979c81b7b57107f824b96d9fef8049a00c5b08
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798574"
---
# <span data-ttu-id="d0a09-103">App-V 5.0 入门</span><span class="sxs-lookup"><span data-stu-id="d0a09-103">Getting Started with App-V 5.0</span></span>


<span data-ttu-id="d0a09-104">App-v 5.0 使管理员可以在需要的基础上实时部署、更新和支持应用程序作为服务。</span><span class="sxs-lookup"><span data-stu-id="d0a09-104">App-V 5.0 enables administrators to deploy, update, and support applications as services in real time, on an as-needed basis.</span></span> <span data-ttu-id="d0a09-105">单个应用程序从本地安装的产品转换为集中管理的服务，并在需要时随时可用，无需预配置计算机或更改操作系统设置。</span><span class="sxs-lookup"><span data-stu-id="d0a09-105">Individual applications are transformed from locally installed products into centrally managed services and are available wherever you need, without the need to preconfigure computers or to change operating system settings.</span></span>

<span data-ttu-id="d0a09-106">App-v 包含以下元素：</span><span class="sxs-lookup"><span data-stu-id="d0a09-106">App-V consists of the following elements:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d0a09-107">元素</span><span class="sxs-lookup"><span data-stu-id="d0a09-107">Element</span></span></th>
<th align="left"><span data-ttu-id="d0a09-108">描述</span><span class="sxs-lookup"><span data-stu-id="d0a09-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d0a09-109">App-v 管理服务器</span><span class="sxs-lookup"><span data-stu-id="d0a09-109">App-V Management Server</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="d0a09-110">提供用于管理 App-v 基础结构的中心位置，该位置将为应用端桌面客户端和远程桌面服务（以前称为终端服务）客户端提供虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="d0a09-110">Provides a central location for managing the App-V infrastructure, which delivers virtual applications to both the App-V Desktop Client and the Remote Desktop Services (formerly Terminal Services) Client.</span></span></p></li>
<li><p><span data-ttu-id="d0a09-111">对其数据存储使用 Microsoft SQL Server®，其中一个或多个 App-v 管理服务器可以共享单个 SQL Server 数据存储。</span><span class="sxs-lookup"><span data-stu-id="d0a09-111">Uses Microsoft SQL Server® for its data store, where one or more App-V Management servers can share a single SQL Server data store.</span></span></p></li>
<li><p><span data-ttu-id="d0a09-112">对请求进行身份验证，并提供安全、计量、监视和数据收集。</span><span class="sxs-lookup"><span data-stu-id="d0a09-112">Authenticates requests and provides security, metering, monitoring, and data gathering.</span></span> <span data-ttu-id="d0a09-113">服务器使用 Active Directory 和支持工具管理用户和应用程序。</span><span class="sxs-lookup"><span data-stu-id="d0a09-113">The server uses Active Directory and supporting tools to manage users and applications.</span></span></p></li>
<li><p><span data-ttu-id="d0a09-114">具有基于 Silverlight®的管理网站，使你能够从任意计算机配置 App-v 基础结构。</span><span class="sxs-lookup"><span data-stu-id="d0a09-114">Has a Silverlight®-based management site, which enables you to configure the App-V infrastructure from any computer.</span></span> <span data-ttu-id="d0a09-115">你可以添加和删除应用程序、操作快捷方式、为用户和组分配访问权限以及创建连接组。</span><span class="sxs-lookup"><span data-stu-id="d0a09-115">You can add and remove applications, manipulate shortcuts, assign access permissions to users and groups, and create connection groups.</span></span></p></li>
<li><p><span data-ttu-id="d0a09-116">启用 app-v Web 管理控制台和 SQL Server 数据存储之间的通信。</span><span class="sxs-lookup"><span data-stu-id="d0a09-116">Enables communication between the App-V Web Management Console and the SQL Server data store.</span></span> <span data-ttu-id="d0a09-117">这些组件可以安装在一台服务器计算机上，也可以安装在一台或多台单独的计算机上，具体取决于所需的系统体系结构。</span><span class="sxs-lookup"><span data-stu-id="d0a09-117">These components can all be installed on a single server computer, or on one or more separate computers, depending on the required system architecture.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d0a09-118">App-v 发布服务器</span><span class="sxs-lookup"><span data-stu-id="d0a09-118">App-V Publishing Server</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="d0a09-119">为特定用户提供具有标题的应用程序的 app-v 客户端</span><span class="sxs-lookup"><span data-stu-id="d0a09-119">Provides App-V Clients with entitled applications for the specific user</span></span></p></li>
<li><p><span data-ttu-id="d0a09-120">托管用于流式处理的虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="d0a09-120">Hosts the virtual application package for streaming.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d0a09-121">App-v 桌面客户端</span><span class="sxs-lookup"><span data-stu-id="d0a09-121">App-V Desktop Client</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="d0a09-122">检索虚拟应用程序</span><span class="sxs-lookup"><span data-stu-id="d0a09-122">Retrieves virtual applications</span></span></p></li>
<li><p><span data-ttu-id="d0a09-123">在客户端上发布应用程序</span><span class="sxs-lookup"><span data-stu-id="d0a09-123">Publishes the applications on the clients</span></span></p></li>
<li><p><span data-ttu-id="d0a09-124">在 Windows 终结点上的运行时自动设置和管理虚拟环境。</span><span class="sxs-lookup"><span data-stu-id="d0a09-124">Automatically sets up and manages virtual environments at runtime on Windows endpoints.</span></span></p></li>
<li><p><span data-ttu-id="d0a09-125">在每个用户&#39;s 配置文件中存储特定于用户的虚拟应用程序设置，如注册表和文件更改。</span><span class="sxs-lookup"><span data-stu-id="d0a09-125">Stores user-specific virtual application settings, such as registry and file changes, in each user&#39;s profile.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d0a09-126">App-v 远程桌面服务（RDS）客户端</span><span class="sxs-lookup"><span data-stu-id="d0a09-126">App-V Remote Desktop Services (RDS) Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="d0a09-127">使远程桌面会话主机服务器能够使用 app-v 桌面客户端的功能来实现共享桌面会话。</span><span class="sxs-lookup"><span data-stu-id="d0a09-127">Enables Remote Desktop Session Host servers to use the capabilities of the App-V Desktop Client for shared desktop sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d0a09-128">App-v 排序器</span><span class="sxs-lookup"><span data-stu-id="d0a09-128">App-V Sequencer</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="d0a09-129">是一个基于向导的工具，可用于将传统应用程序转换为虚拟应用程序。</span><span class="sxs-lookup"><span data-stu-id="d0a09-129">Is a wizard-based tool that you use to transform traditional applications into virtual applications.</span></span></p></li>
<li><p><span data-ttu-id="d0a09-130">生成应用程序 "程序包"，其中包括：</span><span class="sxs-lookup"><span data-stu-id="d0a09-130">Produces the application “package,” which consists of:</span></span></p>
<ol>
<li><p><span data-ttu-id="d0a09-131">顺序应用程序（APPV）文件</span><span class="sxs-lookup"><span data-stu-id="d0a09-131">a sequenced application (APPV) file</span></span></p></li>
<li><p><span data-ttu-id="d0a09-132">可部署到为独立操作配置的客户端的 Windows Installer 文件（MSI）</span><span class="sxs-lookup"><span data-stu-id="d0a09-132">a Windows Installer file (MSI) that can be deployed to clients configured for stand-alone operation</span></span></p></li>
<li><p><span data-ttu-id="d0a09-133">包含 Report.XML、PackageName_DeploymentConfig.XML 和 PackageName_UserConfig.XML 的多个 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="d0a09-133">Several XML files including Report.XML, PackageName_DeploymentConfig.XML, and PackageName_UserConfig.XML.</span></span> <span data-ttu-id="d0a09-134">UserConfig 和 DeploymentConfig XML 文件用于配置对程序包的默认行为的自定义更改。</span><span class="sxs-lookup"><span data-stu-id="d0a09-134">The UserConfig and DeploymentConfig XML files are used to configure custom changes to the default behavior of the package.</span></span></p></li>
</ol></li>
</ul></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="d0a09-135">有关这些元素的详细信息，请参阅[app-v 5.0 的高级别体系结构](high-level-architecture-for-app-v-50.md)。</span><span class="sxs-lookup"><span data-stu-id="d0a09-135">For more information about these elements, see [High Level Architecture for App-V 5.0](high-level-architecture-for-app-v-50.md).</span></span>

<span data-ttu-id="d0a09-136">如果您不熟悉本产品，我们建议您仔细阅读文档。</span><span class="sxs-lookup"><span data-stu-id="d0a09-136">If you are new to this product, we recommend that you read the documentation thoroughly.</span></span> <span data-ttu-id="d0a09-137">在将其部署到生产环境之前，我们还建议你在测试网络环境中验证你的部署计划。</span><span class="sxs-lookup"><span data-stu-id="d0a09-137">Before you deploy it to a production environment, we also recommend that you validate your deployment plan in a test network environment.</span></span> <span data-ttu-id="d0a09-138">你还可以考虑获取有关相关技术的类。</span><span class="sxs-lookup"><span data-stu-id="d0a09-138">You might also consider taking a class about relevant technologies.</span></span> <span data-ttu-id="d0a09-139">有关 Microsoft 培训商机的详细信息，请参阅 Microsoft 培训概述 <https://go.microsoft.com/fwlink/p/?LinkId=80347> 。</span><span class="sxs-lookup"><span data-stu-id="d0a09-139">For more information about Microsoft training opportunities, see the Microsoft Training Overview at <https://go.microsoft.com/fwlink/p/?LinkId=80347>.</span></span>

<span data-ttu-id="d0a09-140">**注意** 此管理员指南的可下载版本不可用。</span><span class="sxs-lookup"><span data-stu-id="d0a09-140">**Note** A downloadable version of this administrator’s guide is not available.</span></span> <span data-ttu-id="d0a09-141">但是，你可以了解 TechNet 库的特殊模式，这种模式允许你选择文章、将它们分组在一个集合中，或将其打印到文件中 <https://go.microsoft.com/fwlink/?LinkId=272491> （ https://go.microsoft.com/fwlink/?LinkId=272491) 。</span><span class="sxs-lookup"><span data-stu-id="d0a09-141">However, you can learn about a special mode of the TechNet Library that allows you to select articles, group them in a collection, and print them or export them to a file at <https://go.microsoft.com/fwlink/?LinkId=272491> (https://go.microsoft.com/fwlink/?LinkId=272491).</span></span>

 

<span data-ttu-id="d0a09-142">本应用程序-V 5.0 管理员指南的此部分包含有关 App-v 5.0 的高级信息，可让你在开始部署计划之前对产品有基本的了解。</span><span class="sxs-lookup"><span data-stu-id="d0a09-142">This section of the App-V 5.0 Administrator’s Guide includes high-level information about App-V 5.0 to provide you with a basic understanding of the product before you begin the deployment planning.</span></span>

## <span data-ttu-id="d0a09-143">App-v 5.0 入门</span><span class="sxs-lookup"><span data-stu-id="d0a09-143">Getting started with App-V 5.0</span></span>


-   [<span data-ttu-id="d0a09-144">关于 App-V 5.0</span><span class="sxs-lookup"><span data-stu-id="d0a09-144">About App-V 5.0</span></span>](about-app-v-50.md)

    <span data-ttu-id="d0a09-145">提供 App-v 5.0 的高级概述以及它在您的组织中的使用方式。</span><span class="sxs-lookup"><span data-stu-id="d0a09-145">Provides a high-level overview of App-V 5.0 and how it can be used in your organization.</span></span>

-   [<span data-ttu-id="d0a09-146">关于 App-V 5.0 SP1</span><span class="sxs-lookup"><span data-stu-id="d0a09-146">About App-V 5.0 SP1</span></span>](about-app-v-50-sp1.md)

    <span data-ttu-id="d0a09-147">提供 app-v 5.0 SP1 的高级概述以及它在您的组织中的使用方式。</span><span class="sxs-lookup"><span data-stu-id="d0a09-147">Provides a high-level overview of App-V 5.0SP1 and how it can be used in your organization.</span></span>

-   [<span data-ttu-id="d0a09-148">关于 App-V 5.0 SP2</span><span class="sxs-lookup"><span data-stu-id="d0a09-148">About App-V 5.0 SP2</span></span>](about-app-v-50-sp2.md)

    <span data-ttu-id="d0a09-149">提供 app-v 5.0 SP2 的高级概述，以及如何在组织中使用它。</span><span class="sxs-lookup"><span data-stu-id="d0a09-149">Provides a high-level overview of App-V 5.0SP2 and how it can be used in your organization.</span></span>

-   [<span data-ttu-id="d0a09-150">关于 App-V 5.0 SP3</span><span class="sxs-lookup"><span data-stu-id="d0a09-150">About App-V 5.0 SP3</span></span>](about-app-v-50-sp3.md)

    <span data-ttu-id="d0a09-151">提供 app-v 5.0 SP2 的高级概述，以及如何在组织中使用它。</span><span class="sxs-lookup"><span data-stu-id="d0a09-151">Provides a high-level overview of App-V 5.0SP2 and how it can be used in your organization.</span></span>

-   [<span data-ttu-id="d0a09-152">评估 App-V 5.0</span><span class="sxs-lookup"><span data-stu-id="d0a09-152">Evaluating App-V 5.0</span></span>](evaluating-app-v-50.md)

    <span data-ttu-id="d0a09-153">提供有关如何在组织中使用 V 5.0 的最佳评估方式的信息。</span><span class="sxs-lookup"><span data-stu-id="d0a09-153">Provides information about how you can best evaluate App-V 5.0 for use in your organization.</span></span>

-   [<span data-ttu-id="d0a09-154">App-V 5.0 的高级别体系结构</span><span class="sxs-lookup"><span data-stu-id="d0a09-154">High Level Architecture for App-V 5.0</span></span>](high-level-architecture-for-app-v-50.md)

    <span data-ttu-id="d0a09-155">提供有关 App-v 5.0 功能以及它们如何协同工作的说明。</span><span class="sxs-lookup"><span data-stu-id="d0a09-155">Provides a description of the App-V 5.0 features and how they work together.</span></span>

-   [<span data-ttu-id="d0a09-156">App-V 5.0 的辅助功能</span><span class="sxs-lookup"><span data-stu-id="d0a09-156">Accessibility for App-V 5.0</span></span>](accessibility-for-app-v-50.md)

    <span data-ttu-id="d0a09-157">提供有关使残障人士更易于访问本产品及其相应文档的功能和服务的信息。</span><span class="sxs-lookup"><span data-stu-id="d0a09-157">Provides information about features and services that make this product and its corresponding documentation more accessible for people with disabilities.</span></span>

## <a href="" id="other-resources-for-this-product-"></a><span data-ttu-id="d0a09-158">此产品的其他资源</span><span class="sxs-lookup"><span data-stu-id="d0a09-158">Other resources for this product</span></span>


-   [<span data-ttu-id="d0a09-159">Microsoft Application Virtualization 5.0 管理员指南</span><span class="sxs-lookup"><span data-stu-id="d0a09-159">Microsoft Application Virtualization 5.0 Administrator's Guide</span></span>](microsoft-application-virtualization-50-administrators-guide.md)

-   [<span data-ttu-id="d0a09-160">计划 App-V 5.0</span><span class="sxs-lookup"><span data-stu-id="d0a09-160">Planning for App-V 5.0</span></span>](planning-for-app-v-50-rc.md)

-   [<span data-ttu-id="d0a09-161">部署 App-V 5.0</span><span class="sxs-lookup"><span data-stu-id="d0a09-161">Deploying App-V 5.0</span></span>](deploying-app-v-50.md)

-   [<span data-ttu-id="d0a09-162">App-V 5.0 的操作</span><span class="sxs-lookup"><span data-stu-id="d0a09-162">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

-   [<span data-ttu-id="d0a09-163">App-V 5.0 疑难解答</span><span class="sxs-lookup"><span data-stu-id="d0a09-163">Troubleshooting App-V 5.0</span></span>](troubleshooting-app-v-50.md)






 

 





