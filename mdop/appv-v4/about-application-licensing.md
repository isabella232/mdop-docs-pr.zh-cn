---
title: 关于应用程序授权
description: 关于应用程序授权
author: dansimp
ms.assetid: 6b487641-1627-4e91-b829-04f001008176
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 546bc630b95fe52f960c7bdfb771d3e2561f9318
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802480"
---
# <span data-ttu-id="55c8d-103">关于应用程序授权</span><span class="sxs-lookup"><span data-stu-id="55c8d-103">About Application Licensing</span></span>


<span data-ttu-id="55c8d-104">你可以直接从应用程序虚拟化服务器管理控制台管理应用程序许可证。</span><span class="sxs-lookup"><span data-stu-id="55c8d-104">You can manage application licenses directly from the Application Virtualization Server Management Console.</span></span>

## <span data-ttu-id="55c8d-105">许可证类型</span><span class="sxs-lookup"><span data-stu-id="55c8d-105">License Types</span></span>


<span data-ttu-id="55c8d-106">系统中心应用程序虚拟化系统目前支持下列许可证类型：</span><span class="sxs-lookup"><span data-stu-id="55c8d-106">The System Center Application Virtualization System currently supports the following license types:</span></span>

-   <span data-ttu-id="55c8d-107">**无限制许可证**-允许任意数量的并行用户访问应用程序。</span><span class="sxs-lookup"><span data-stu-id="55c8d-107">**Unlimited License**—Allows access to the application by any number of simultaneous users.</span></span> <span data-ttu-id="55c8d-108">如果你想要将企业范围许可证与应用程序关联，则此许可方法非常合适。</span><span class="sxs-lookup"><span data-stu-id="55c8d-108">This method of licensing is appropriate when you want to associate an enterprise-wide license with an application.</span></span>

-   <span data-ttu-id="55c8d-109">**并发许可证**-允许你定义允许使用该应用程序的并发用户的最大数量。</span><span class="sxs-lookup"><span data-stu-id="55c8d-109">**Concurrent License**—Enables you to define the maximum number of concurrent users who are allowed to use the application.</span></span>

-   <span data-ttu-id="55c8d-110">**命名许可证**-使您可以为单个用户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="55c8d-110">**Named License**—Enables you to assign a license to an individual user.</span></span> <span data-ttu-id="55c8d-111">命名许可证可用于确保特定用户始终能够运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="55c8d-111">A named license can be used to ensure that a particular user will always be able to run the application.</span></span>

<span data-ttu-id="55c8d-112">你可以将同一应用程序的并发和命名许可证合并在一起。</span><span class="sxs-lookup"><span data-stu-id="55c8d-112">You can combine concurrent and named licenses for the same application.</span></span>

<span data-ttu-id="55c8d-113">默认情况下，许可证已禁用，但你可以从 "**提供程序属性**" 对话框的 "**提供商管道**" 选项卡启用它。</span><span class="sxs-lookup"><span data-stu-id="55c8d-113">Licensing is disabled by default, but you can enable it from the **Provider Pipeline** tab of the **Provider Properties** dialog.</span></span> <span data-ttu-id="55c8d-114">有关启用和禁用授权的详细信息，请参阅[如何设置或禁用应用程序授权](how-to-set-up-or-disable-application-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="55c8d-114">For details about enabling and disabling licensing, see [How to Set Up or Disable Application Licensing](how-to-set-up-or-disable-application-licensing.md).</span></span>

## <span data-ttu-id="55c8d-115">提供商策略</span><span class="sxs-lookup"><span data-stu-id="55c8d-115">Provider Policies</span></span>


<span data-ttu-id="55c8d-116">为应用程序服务提供商（ASP）模型开发了提供程序策略。</span><span class="sxs-lookup"><span data-stu-id="55c8d-116">Provider policies were developed for the Application Service Provider (ASP) model.</span></span> <span data-ttu-id="55c8d-117">在此模型中，单个 ASP 可以为多个客户端托管一个应用程序虚拟化系统，每个客户端都需要保持隔离。</span><span class="sxs-lookup"><span data-stu-id="55c8d-117">In this model, a single ASP can host a single Application Virtualization System for multiple clients, where each client needs to remain isolated.</span></span> <span data-ttu-id="55c8d-118">客户端可能有显著的不同要求-例如，一台客户可能需要身份验证，而另一台不需要身份验证。</span><span class="sxs-lookup"><span data-stu-id="55c8d-118">Clients might have dramatically different requirements—for example, one client might require authentication while another does not.</span></span> <span data-ttu-id="55c8d-119">你可以使用提供程序策略将权限与客户端相关联，以便只有已批准的用户可以访问每个虚拟应用程序或虚拟应用程序包。</span><span class="sxs-lookup"><span data-stu-id="55c8d-119">You can use provider policies to associate permissions with clients so that only the approved users can access each virtual application or virtual application package.</span></span>

<span data-ttu-id="55c8d-120">对于企业客户，当你对一个或多个应用程序具有严格的授权要求时，你可以使用此功能。</span><span class="sxs-lookup"><span data-stu-id="55c8d-120">For the enterprise customer, you can use this feature when you have strict licensing requirements for one or more applications.</span></span> <span data-ttu-id="55c8d-121">在此情况下，将在 "**提供程序属性**" 对话框的 "**提供商管道**" 选项卡上禁用授权组件。</span><span class="sxs-lookup"><span data-stu-id="55c8d-121">Under this situation, the licensing component is disabled on the **Provider Pipeline** tab of the **Provider Properties** dialog.</span></span>

<span data-ttu-id="55c8d-122">**提供程序管道**选项卡还具有用于启用身份验证、授权（**强制访问权限设置**）和计量（**日志使用情况信息**）的复选框。</span><span class="sxs-lookup"><span data-stu-id="55c8d-122">The **Provider Pipeline** tab also has check boxes to enable authentication, authorization (**Enforce Access Permission Settings**), and metering (**Log Usage Information**).</span></span> <span data-ttu-id="55c8d-123">如果你的配置具有特殊要求，你可以编写自己的管道组件并通过单击 "**高级**" 按钮将它们添加到系统。</span><span class="sxs-lookup"><span data-stu-id="55c8d-123">If your configuration has special requirements, you can write your own pipeline components and add them to the system by clicking the **Advanced** button.</span></span>

## <span data-ttu-id="55c8d-124">帐户颁发机构</span><span class="sxs-lookup"><span data-stu-id="55c8d-124">Account Authorities</span></span>


<span data-ttu-id="55c8d-125">"帐户颁发机构" 是安装应用程序虚拟化服务器的域。</span><span class="sxs-lookup"><span data-stu-id="55c8d-125">The account authority is the domain in which the Application Virtualization Server is installed.</span></span> <span data-ttu-id="55c8d-126">在执行服务器安装过程中，系统会提示你提供域名;默认情况下，检测并使用安装计算机的域。</span><span class="sxs-lookup"><span data-stu-id="55c8d-126">As you proceed through the server installation, you are prompted to supply a domain name; the domain in which the computer is installed is detected and used by default.</span></span> <span data-ttu-id="55c8d-127">当用户尝试登录到系统时，系统会提示他们提供其凭据，然后才能访问该域。</span><span class="sxs-lookup"><span data-stu-id="55c8d-127">When users attempt to log in to the system, they are prompted for their credentials before they can access that domain.</span></span>

<span data-ttu-id="55c8d-128">应用程序虚拟化系统支持多个域。</span><span class="sxs-lookup"><span data-stu-id="55c8d-128">The Application Virtualization System supports multiple domains.</span></span> <span data-ttu-id="55c8d-129">如果在域之间建立了信任关系，则可以向其他域中的用户组授予应用程序访问权限。</span><span class="sxs-lookup"><span data-stu-id="55c8d-129">You can grant application access to user groups in other domains if a trust relationship is established between domains.</span></span> <span data-ttu-id="55c8d-130">用户必须提供由每个域识别的凭据。</span><span class="sxs-lookup"><span data-stu-id="55c8d-130">Users must supply credentials that are recognized by each domain.</span></span>

<span data-ttu-id="55c8d-131">在应用程序虚拟化服务器管理控制台中，你可以更改主域（帐户颁发机构）和用于访问它的凭据。</span><span class="sxs-lookup"><span data-stu-id="55c8d-131">In the Application Virtualization Server Management Console, you can change the primary domain (account authority) and the credentials that are used to access it.</span></span>

## <span data-ttu-id="55c8d-132">身份验证</span><span class="sxs-lookup"><span data-stu-id="55c8d-132">Authentication</span></span>


<span data-ttu-id="55c8d-133">身份验证是用于确认用户的身份的机制。</span><span class="sxs-lookup"><span data-stu-id="55c8d-133">Authentication is the mechanism used to confirm a user's identity.</span></span> <span data-ttu-id="55c8d-134">任何具有已识别的用户名和密码的用户都有权访问。</span><span class="sxs-lookup"><span data-stu-id="55c8d-134">Any user with a recognized user name and password has access.</span></span>

<span data-ttu-id="55c8d-135">在应用程序虚拟化系统中，你可以通过 "**提供商管道**" 选项卡上的复选框启用或禁用身份验证。默认情况下，启用 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="55c8d-135">In the Application Virtualization System, you can enable or disable authentication through a check box on the **Provider Pipeline** tab. By default, Windows Authentication is enabled.</span></span>

## <span data-ttu-id="55c8d-136">授权</span><span class="sxs-lookup"><span data-stu-id="55c8d-136">Authorization</span></span>


<span data-ttu-id="55c8d-137">授权是用于确认用户的身份的过程。</span><span class="sxs-lookup"><span data-stu-id="55c8d-137">Authorization is the process used to confirm a user’s identity.</span></span> <span data-ttu-id="55c8d-138">确认用户的身份后，系统会确定用户是否已被授予对系统的访问权限，以及用户被授予访问权限的应用程序。</span><span class="sxs-lookup"><span data-stu-id="55c8d-138">After confirming the user's identity, the system determines whether the user was granted access to the system and to which applications the user was granted access.</span></span> <span data-ttu-id="55c8d-139">应用程序虚拟化服务器管理控制台在 "**提供商管道**" 选项卡上具有 "**强制访问权限设置**" 复选框以启用或禁用授权。</span><span class="sxs-lookup"><span data-stu-id="55c8d-139">The Application Virtualization Server Management Console has an **Enforce Access Permission Settings** check box on the **Provider Pipeline** tab to enable or disable authorization.</span></span>

<span data-ttu-id="55c8d-140">在应用程序虚拟化系统中，仅向用户组（而非单个用户）授予访问权限。</span><span class="sxs-lookup"><span data-stu-id="55c8d-140">In the Application Virtualization System, access is granted to a user group only, not to individual users.</span></span>

## <span data-ttu-id="55c8d-141">相关主题</span><span class="sxs-lookup"><span data-stu-id="55c8d-141">Related topics</span></span>


[<span data-ttu-id="55c8d-142">如何在 Server Management Console 中管理应用程序许可证</span><span class="sxs-lookup"><span data-stu-id="55c8d-142">How to Manage Application Licenses in the Server Management Console</span></span>](how-to-manage-application-licenses-in-the-server-management-console.md)

[<span data-ttu-id="55c8d-143">如何设置或禁用应用程序授权</span><span class="sxs-lookup"><span data-stu-id="55c8d-143">How to Set Up or Disable Application Licensing</span></span>](how-to-set-up-or-disable-application-licensing.md)

[<span data-ttu-id="55c8d-144">Server Management Console：“提供程序策略”节点</span><span class="sxs-lookup"><span data-stu-id="55c8d-144">Server Management Console: Provider Policies Node</span></span>](server-management-console-provider-policies-node.md)

 

 





