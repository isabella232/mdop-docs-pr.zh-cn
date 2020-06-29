---
title: 使用 Management Console 管理 App-V 5.1 虚拟应用程序
description: 使用 Management Console 管理 App-V 5.1 虚拟应用程序
author: dansimp
ms.assetid: a4d078aa-ec54-4fa4-9463-bfb3b971d724
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 63ec965519bedef08b09c961dc5d1c90e1d8d694
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798652"
---
# <span data-ttu-id="bf248-103">使用 Management Console 管理 App-V 5.1 虚拟应用程序</span><span class="sxs-lookup"><span data-stu-id="bf248-103">Administering App-V 5.1 Virtual Applications by Using the Management Console</span></span>


<span data-ttu-id="bf248-104">使用 Microsoft Application Virtualization （App-v）5.1 管理服务器管理你的环境中的程序包、连接组和程序包访问。</span><span class="sxs-lookup"><span data-stu-id="bf248-104">Use the Microsoft Application Virtualization (App-V) 5.1 management server to manage packages, connection groups, and package access in your environment.</span></span> <span data-ttu-id="bf248-105">服务器将应用程序图标、快捷方式和文件类型关联发布到运行 app-v 5.1 客户端的已授权计算机。</span><span class="sxs-lookup"><span data-stu-id="bf248-105">The server publishes application icons, shortcuts, and file type associations to authorized computers that run the App-V 5.1 client.</span></span> <span data-ttu-id="bf248-106">一个或多个管理服务器通常共享一个用于配置和程序包信息的通用数据存储。</span><span class="sxs-lookup"><span data-stu-id="bf248-106">One or more management servers typically share a common data store for configuration and package information.</span></span>

<span data-ttu-id="bf248-107">管理服务器使用 Active Directory 域服务（AD DS）组管理用户身份验证，并安装 SQL Server 以管理数据库和数据存储。</span><span class="sxs-lookup"><span data-stu-id="bf248-107">The management server uses Active Directory Domain Services (AD DS) groups to manage user authorization and has SQL Server installed to manage the database and data store.</span></span>

<span data-ttu-id="bf248-108">由于管理服务器将应用程序流式处理应用程序，因此，这些服务器非常适合具有可靠、高带宽 Lan 的系统配置。</span><span class="sxs-lookup"><span data-stu-id="bf248-108">Because the management servers stream applications to end users on demand, these servers are ideally suited for system configurations that have reliable, high-bandwidth LANs.</span></span> <span data-ttu-id="bf248-109">管理服务器包含以下组件：</span><span class="sxs-lookup"><span data-stu-id="bf248-109">The management server consists of the following components:</span></span>

-   <span data-ttu-id="bf248-110">管理服务器-使用管理服务器管理程序包和连接组。</span><span class="sxs-lookup"><span data-stu-id="bf248-110">Management Server – Use the management server to manage packages and connection groups.</span></span>

-   <span data-ttu-id="bf248-111">发布服务器-使用发布服务器将程序包部署到运行 app-v 5.1 客户端的计算机。</span><span class="sxs-lookup"><span data-stu-id="bf248-111">Publishing Server – Use the publishing server to deploy packages to computers that run the App-V 5.1 client.</span></span>

-   <span data-ttu-id="bf248-112">管理数据库-使用管理数据库管理程序包访问和发布服务器与管理服务器的同步。</span><span class="sxs-lookup"><span data-stu-id="bf248-112">Management Database - Use the management database to manage the package access and to publish the server’s synchronization with the management server.</span></span>

## <span data-ttu-id="bf248-113">管理控制台任务</span><span class="sxs-lookup"><span data-stu-id="bf248-113">Management Console tasks</span></span>


<span data-ttu-id="bf248-114">可通过 app-v 5.1 管理控制台执行的最常见任务有：</span><span class="sxs-lookup"><span data-stu-id="bf248-114">The most common tasks that you can perform with the App-V 5.1 Management console are:</span></span>

-   [<span data-ttu-id="bf248-115">如何连接到 Management Console</span><span class="sxs-lookup"><span data-stu-id="bf248-115">How to Connect to the Management Console</span></span>](how-to-connect-to-the-management-console-51.md)

-   [<span data-ttu-id="bf248-116">如何使用管理控制台添加或升级程序包</span><span class="sxs-lookup"><span data-stu-id="bf248-116">How to Add or Upgrade Packages by Using the Management Console</span></span>](how-to-add-or-upgrade-packages-by-using-the-management-console-51-gb18030.md)

-   [<span data-ttu-id="bf248-117">如何使用管理控制台配置对程序包的访问权限</span><span class="sxs-lookup"><span data-stu-id="bf248-117">How to Configure Access to Packages by Using the Management Console</span></span>](how-to-configure-access-to-packages-by-using-the-management-console-51.md)

-   [<span data-ttu-id="bf248-118">如何使用管理控制台发布程序包</span><span class="sxs-lookup"><span data-stu-id="bf248-118">How to Publish a Package by Using the Management Console</span></span>](how-to-publish-a-package-by-using-the-management-console-51.md)

-   [<span data-ttu-id="bf248-119">如何使用管理控制台删除程序包</span><span class="sxs-lookup"><span data-stu-id="bf248-119">How to Delete a Package in the Management Console</span></span>](how-to-delete-a-package-in-the-management-console-51.md)

-   [<span data-ttu-id="bf248-120">如何使用管理控制台添加或删除管理员</span><span class="sxs-lookup"><span data-stu-id="bf248-120">How to Add or Remove an Administrator by Using the Management Console</span></span>](how-to-add-or-remove-an-administrator-by-using-the-management-console51.md)

-   [<span data-ttu-id="bf248-121">如何使用管理控制台注册和注销发布服务器</span><span class="sxs-lookup"><span data-stu-id="bf248-121">How to Register and Unregister a Publishing Server by Using the Management Console</span></span>](how-to-register-and-unregister-a-publishing-server-by-using-the-management-console51.md)

-   [<span data-ttu-id="bf248-122">如何使用 App-V 5.1 Management Console 创建自定义配置文件</span><span class="sxs-lookup"><span data-stu-id="bf248-122">How to Create a Custom Configuration File by Using the App-V 5.1 Management Console</span></span>](how-to-create-a-custom-configuration-file-by-using-the-app-v-51-management-console.md)

-   [<span data-ttu-id="bf248-123">如何使用 Management Console 将访问权限和配置转移到其他版本的程序包</span><span class="sxs-lookup"><span data-stu-id="bf248-123">How to Transfer Access and Configurations to Another Version of a Package by Using the Management Console</span></span>](how-to-transfer-access-and-configurations-to-another-version-of-a-package-by-using-the-management-console51.md)

-   [<span data-ttu-id="bf248-124">如何使用管理控制台为特定 AD 组自定义虚拟应用程序扩展</span><span class="sxs-lookup"><span data-stu-id="bf248-124">How to Customize Virtual Applications Extensions for a Specific AD Group by Using the Management Console</span></span>](how-to-customize-virtual-applications-extensions-for-a-specific-ad-group-by-using-the-management-console51.md)

-   [<span data-ttu-id="bf248-125">如何使用管理控制台查看和配置应用程序和默认虚拟应用程序扩展</span><span class="sxs-lookup"><span data-stu-id="bf248-125">How to View and Configure Applications and Default Virtual Application Extensions by Using the Management Console</span></span>](how-to-view-and-configure-applications-and-default-virtual-application-extensions-by-using-the-management-console-beta.md)

<span data-ttu-id="bf248-126">App-v 5.1 管理控制台的主要元素包括：</span><span class="sxs-lookup"><span data-stu-id="bf248-126">The main elements of the App-V 5.1 Management Console are:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bf248-127">管理控制台选项卡</span><span class="sxs-lookup"><span data-stu-id="bf248-127">Management Console tab</span></span></th>
<th align="left"><span data-ttu-id="bf248-128">描述</span><span class="sxs-lookup"><span data-stu-id="bf248-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bf248-129">"程序包" 选项卡</span><span class="sxs-lookup"><span data-stu-id="bf248-129">Packages tab</span></span></p></td>
<td align="left"><p><span data-ttu-id="bf248-130">使用 " <strong> 程序包 </strong> " 选项卡添加或升级程序包。</span><span class="sxs-lookup"><span data-stu-id="bf248-130">Use the <strong>PACKAGES</strong> tab to add or upgrade packages.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bf248-131">"连接组" 选项卡</span><span class="sxs-lookup"><span data-stu-id="bf248-131">Connection Groups tab</span></span></p></td>
<td align="left"><p><span data-ttu-id="bf248-132">使用 " <strong> 连接组" </strong> 选项卡管理连接组。</span><span class="sxs-lookup"><span data-stu-id="bf248-132">Use the <strong>CONNECTION GROUPS</strong> tab to manage connection groups.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bf248-133">服务器选项卡</span><span class="sxs-lookup"><span data-stu-id="bf248-133">Servers tab</span></span></p></td>
<td align="left"><p><span data-ttu-id="bf248-134">使用 " <strong> 服务器" </strong> 选项卡注册新服务器。</span><span class="sxs-lookup"><span data-stu-id="bf248-134">Use the <strong>SERVERS</strong> tab to register a new server.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bf248-135">"管理员" 选项卡</span><span class="sxs-lookup"><span data-stu-id="bf248-135">Administrators tab</span></span></p></td>
<td align="left"><p><span data-ttu-id="bf248-136">使用 " <strong> 管理员 </strong> " 选项卡注册、添加或删除 app-v 5.1 环境中的管理员。</span><span class="sxs-lookup"><span data-stu-id="bf248-136">Use the <strong>ADMINISTRATORS</strong> tab to register, add, or remove administrators in your App-V 5.1 environment.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="bf248-137">**重要提示** 必须在打开 Web 管理控制台的浏览器上启用 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="bf248-137">**Important** JavaScript must be enabled on the browser that opens the Web Management Console.</span></span>

 






## <a href="" id="other-resources-for-this-app-v-5-1-deployment-"></a><span data-ttu-id="bf248-138">此 App-v 5.1 部署的其他资源</span><span class="sxs-lookup"><span data-stu-id="bf248-138">Other resources for this App-V 5.1 deployment</span></span>


-   [<span data-ttu-id="bf248-139">Microsoft Application Virtualization 5.1 管理员指南</span><span class="sxs-lookup"><span data-stu-id="bf248-139">Microsoft Application Virtualization 5.1 Administrator's Guide</span></span>](microsoft-application-virtualization-51-administrators-guide.md)

-   [<span data-ttu-id="bf248-140">App-V 5.1 的操作</span><span class="sxs-lookup"><span data-stu-id="bf248-140">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

 

 





