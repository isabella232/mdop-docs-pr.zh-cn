---
title: 使用 Management Console 管理 App-V 5.0 虚拟应用程序
description: 使用 Management Console 管理 App-V 5.0 虚拟应用程序
author: dansimp
ms.assetid: e9280dbd-782b-493a-b495-daab25247795
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 10/03/2016
ms.openlocfilehash: 7a71f7c0fd82f8ef9d1efd5b978591b6838a648a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798653"
---
# <span data-ttu-id="c144e-103">使用 Management Console 管理 App-V 5.0 虚拟应用程序</span><span class="sxs-lookup"><span data-stu-id="c144e-103">Administering App-V 5.0 Virtual Applications by Using the Management Console</span></span>


<span data-ttu-id="c144e-104">使用 Microsoft Application Virtualization （App-v）5.0 管理服务器管理你的环境中的程序包、连接组和程序包访问。</span><span class="sxs-lookup"><span data-stu-id="c144e-104">Use the Microsoft Application Virtualization (App-V) 5.0 management server to manage packages, connection groups, and package access in your environment.</span></span> <span data-ttu-id="c144e-105">服务器将应用程序图标、快捷方式和文件类型关联发布到运行 app-v 5.0 客户端的已授权计算机。</span><span class="sxs-lookup"><span data-stu-id="c144e-105">The server publishes application icons, shortcuts, and file type associations to authorized computers that run the App-V 5.0 client.</span></span> <span data-ttu-id="c144e-106">一个或多个管理服务器通常共享一个用于配置和程序包信息的通用数据存储。</span><span class="sxs-lookup"><span data-stu-id="c144e-106">One or more management servers typically share a common data store for configuration and package information.</span></span>

<span data-ttu-id="c144e-107">管理服务器使用 Active Directory 域服务（AD DS）组管理用户身份验证，并安装 SQL Server 以管理数据库和数据存储。</span><span class="sxs-lookup"><span data-stu-id="c144e-107">The management server uses Active Directory Domain Services (AD DS) groups to manage user authorization and has SQL Server installed to manage the database and data store.</span></span>

<span data-ttu-id="c144e-108">由于管理服务器将应用程序流式处理应用程序，因此，这些服务器非常适合具有可靠、高带宽 Lan 的系统配置。</span><span class="sxs-lookup"><span data-stu-id="c144e-108">Because the management servers stream applications to end users on demand, these servers are ideally suited for system configurations that have reliable, high-bandwidth LANs.</span></span> <span data-ttu-id="c144e-109">管理服务器包含以下组件：</span><span class="sxs-lookup"><span data-stu-id="c144e-109">The management server consists of the following components:</span></span>

-   <span data-ttu-id="c144e-110">管理服务器-使用管理服务器管理程序包和连接组。</span><span class="sxs-lookup"><span data-stu-id="c144e-110">Management Server – Use the management server to manage packages and connection groups.</span></span>

-   <span data-ttu-id="c144e-111">发布服务器-使用发布服务器将程序包部署到运行 app-v 5.0 客户端的计算机。</span><span class="sxs-lookup"><span data-stu-id="c144e-111">Publishing Server – Use the publishing server to deploy packages to computers that run the App-V 5.0 client.</span></span>

-   <span data-ttu-id="c144e-112">管理数据库-使用管理数据库管理程序包访问和发布服务器与管理服务器的同步。</span><span class="sxs-lookup"><span data-stu-id="c144e-112">Management Database - Use the management database to manage the package access and to publish the server’s synchronization with the management server.</span></span>

## <span data-ttu-id="c144e-113">管理控制台任务</span><span class="sxs-lookup"><span data-stu-id="c144e-113">Management Console tasks</span></span>


<span data-ttu-id="c144e-114">可通过 app-v 5.0 管理控制台执行的最常见任务有：</span><span class="sxs-lookup"><span data-stu-id="c144e-114">The most common tasks that you can perform with the App-V 5.0 Management console are:</span></span>

-   [<span data-ttu-id="c144e-115">如何连接到 Management Console</span><span class="sxs-lookup"><span data-stu-id="c144e-115">How to Connect to the Management Console</span></span>](how-to-connect-to-the-management-console-beta.md)

-   [<span data-ttu-id="c144e-116">如何使用管理控制台添加或升级程序包</span><span class="sxs-lookup"><span data-stu-id="c144e-116">How to Add or Upgrade Packages by Using the Management Console</span></span>](how-to-add-or-upgrade-packages-by-using-the-management-console-beta-gb18030.md)

-   [<span data-ttu-id="c144e-117">如何使用管理控制台配置对程序包的访问权限</span><span class="sxs-lookup"><span data-stu-id="c144e-117">How to Configure Access to Packages by Using the Management Console</span></span>](how-to-configure-access-to-packages-by-using-the-management-console-50.md)

-   [<span data-ttu-id="c144e-118">如何使用管理控制台发布程序包</span><span class="sxs-lookup"><span data-stu-id="c144e-118">How to Publish a Package by Using the Management Console</span></span>](how-to-publish-a-package-by-using-the-management-console-50.md)

-   [<span data-ttu-id="c144e-119">如何使用管理控制台删除程序包</span><span class="sxs-lookup"><span data-stu-id="c144e-119">How to Delete a Package in the Management Console</span></span>](how-to-delete-a-package-in-the-management-console-beta.md)

-   [<span data-ttu-id="c144e-120">如何使用管理控制台添加或删除管理员</span><span class="sxs-lookup"><span data-stu-id="c144e-120">How to Add or Remove an Administrator by Using the Management Console</span></span>](how-to-add-or-remove-an-administrator-by-using-the-management-console.md)

-   [<span data-ttu-id="c144e-121">如何使用管理控制台注册和注销发布服务器</span><span class="sxs-lookup"><span data-stu-id="c144e-121">How to Register and Unregister a Publishing Server by Using the Management Console</span></span>](how-to-register-and-unregister-a-publishing-server-by-using-the-management-console.md)

-   [<span data-ttu-id="c144e-122">如何使用 App-V 5.0 Management Console 创建自定义配置文件</span><span class="sxs-lookup"><span data-stu-id="c144e-122">How to Create a Custom Configuration File by Using the App-V 5.0 Management Console</span></span>](how-to-create-a-custom-configuration-file-by-using-the-app-v-50-management-console.md)

-   [<span data-ttu-id="c144e-123">如何使用 Management Console 将访问权限和配置转移到其他版本的程序包</span><span class="sxs-lookup"><span data-stu-id="c144e-123">How to Transfer Access and Configurations to Another Version of a Package by Using the Management Console</span></span>](how-to-transfer-access-and-configurations-to-another-version-of-a-package-by-using-the-management-console.md)

-   [<span data-ttu-id="c144e-124">如何使用管理控制台为特定 AD 组自定义虚拟应用程序扩展</span><span class="sxs-lookup"><span data-stu-id="c144e-124">How to Customize Virtual Applications Extensions for a Specific AD Group by Using the Management Console</span></span>](how-to-customize-virtual-applications-extensions-for-a-specific-ad-group-by-using-the-management-console.md)

-   [<span data-ttu-id="c144e-125">在管理控制台中配置应用程序和默认虚拟应用程序扩展</span><span class="sxs-lookup"><span data-stu-id="c144e-125">Configure Applications and Default Virtual Application Extensions in Management Console</span></span>](configure-applications-and-default-virtual-application-extensions-in-management-console.md)

<span data-ttu-id="c144e-126">App-v 5.0 管理控制台的主要元素包括：</span><span class="sxs-lookup"><span data-stu-id="c144e-126">The main elements of the App-V 5.0 Management Console are:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="c144e-127">管理控制台选项卡</span><span class="sxs-lookup"><span data-stu-id="c144e-127">Management Console tab</span></span></th>
<th align="left"><span data-ttu-id="c144e-128">说明</span><span class="sxs-lookup"><span data-stu-id="c144e-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c144e-129">概述</span><span class="sxs-lookup"><span data-stu-id="c144e-129">Overview</span></span></p></td>
<td align="left"><p></p>
<ul>
<li><p><strong><span data-ttu-id="c144e-130">App-v Sequencer </strong> - 若要查看有关使用 app-v 5.0 Sequencer 的常规信息，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="c144e-130">App-V Sequencer</strong> - Select this option to review general information about using the App-V 5.0 sequencer.</span></span></p></li>
<li><p><strong><span data-ttu-id="c144e-131">应用程序包库 </strong> –选择此选项可打开 <strong> 管理控制台的 "程序包" </strong> 页面。</span><span class="sxs-lookup"><span data-stu-id="c144e-131">Application Packages Library</strong> – Select this option to open the <strong>PACKAGES</strong> page of the Management Console.</span></span> <span data-ttu-id="c144e-132">使用此页面查看已添加到服务器的程序包。</span><span class="sxs-lookup"><span data-stu-id="c144e-132">Use this page to review packages that have been added to the server.</span></span> <span data-ttu-id="c144e-133">您还可以管理连接组以及添加或升级程序包。</span><span class="sxs-lookup"><span data-stu-id="c144e-133">You can also manage the connection groups, as well as add or upgrade packages.</span></span></p></li>
<li><p><strong><span data-ttu-id="c144e-134">服务器 </strong> -选择此选项可打开 <strong> 管理控制台的 "服务器" </strong> 页面。</span><span class="sxs-lookup"><span data-stu-id="c144e-134">SERVERS</strong> – Select this option to open the <strong>SERVERS</strong> page of the Management Console.</span></span> <span data-ttu-id="c144e-135">使用此页面查看已向 app-v 5.0 基础结构注册的服务器的列表。</span><span class="sxs-lookup"><span data-stu-id="c144e-135">Use this page to review the list of servers that have been registered with your App-V 5.0 infrastructure.</span></span></p></li>
<li><p><strong><span data-ttu-id="c144e-136">客户端 </strong> -选择此选项可查看有关 app-v 5.0 客户端的常规信息。</span><span class="sxs-lookup"><span data-stu-id="c144e-136">CLIENTS</strong> – Select this option to review general information about App-V 5.0 clients.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c144e-137">"程序包" 选项卡</span><span class="sxs-lookup"><span data-stu-id="c144e-137">Packages tab</span></span></p></td>
<td align="left"><p><span data-ttu-id="c144e-138">使用 " <strong> 程序包 </strong> " 选项卡添加或升级程序包。</span><span class="sxs-lookup"><span data-stu-id="c144e-138">Use the <strong>PACKAGES</strong> tab to add or upgrade packages.</span></span> <span data-ttu-id="c144e-139">您也可以通过单击 "连接组" 来管理连接组 <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="c144e-139">You can also manage connection groups by clicking <strong>CONNECTION GROUPS</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c144e-140">服务器选项卡</span><span class="sxs-lookup"><span data-stu-id="c144e-140">Servers tab</span></span></p></td>
<td align="left"><p><span data-ttu-id="c144e-141">使用 " <strong> 服务器" </strong> 选项卡注册新服务器。</span><span class="sxs-lookup"><span data-stu-id="c144e-141">Use the <strong>SERVERS</strong> tab to register a new server.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c144e-142">"管理员" 选项卡</span><span class="sxs-lookup"><span data-stu-id="c144e-142">Administrators tab</span></span></p></td>
<td align="left"><p><span data-ttu-id="c144e-143">使用 " <strong> 管理员 </strong> " 选项卡注册、添加或删除 app-v 5.0 环境中的管理员。</span><span class="sxs-lookup"><span data-stu-id="c144e-143">Use the <strong>ADMINISTRATORS</strong> tab to register, add, or remove administrators in your App-V 5.0 environment.</span></span></p></td>
</tr>
</tbody>
</table>

 






## <a href="" id="other-resources-for-this-app-v-5-0-deployment-"></a><span data-ttu-id="c144e-144">此 App-v 5.0 部署的其他资源</span><span class="sxs-lookup"><span data-stu-id="c144e-144">Other resources for this App-V 5.0 deployment</span></span>


-   [<span data-ttu-id="c144e-145">Microsoft Application Virtualization 5.0 管理员指南</span><span class="sxs-lookup"><span data-stu-id="c144e-145">Microsoft Application Virtualization 5.0 Administrator's Guide</span></span>](microsoft-application-virtualization-50-administrators-guide.md)

-   [<span data-ttu-id="c144e-146">App-V 5.0 的操作</span><span class="sxs-lookup"><span data-stu-id="c144e-146">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

 

 





