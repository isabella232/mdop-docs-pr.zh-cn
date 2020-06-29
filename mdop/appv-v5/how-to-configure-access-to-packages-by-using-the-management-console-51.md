---
title: 如何使用管理控制台配置对程序包的访问权限
description: 如何使用管理控制台配置对程序包的访问权限
author: dansimp
ms.assetid: 4fd39bc2-d814-46de-a108-1c21fa404e8a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3c6c8f930fb1fbd82432f6d43dae8b9bed7a563c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798540"
---
# <span data-ttu-id="7eea8-103">如何使用管理控制台配置对程序包的访问权限</span><span class="sxs-lookup"><span data-stu-id="7eea8-103">How to Configure Access to Packages by Using the Management Console</span></span>


<span data-ttu-id="7eea8-104">在部署 app-v 5.1 虚拟化程序包之前，必须配置将允许访问和运行应用程序的 Active Directory 域服务（AD DS）安全组。</span><span class="sxs-lookup"><span data-stu-id="7eea8-104">Before you deploy an App-V 5.1 virtualized package, you must configure the Active Directory Domain Services (AD DS) security groups that will be allowed to access and run the applications.</span></span> <span data-ttu-id="7eea8-105">安全组可能包含计算机或用户。</span><span class="sxs-lookup"><span data-stu-id="7eea8-105">The security groups may contain computers or users.</span></span> <span data-ttu-id="7eea8-106">将程序包 Entitling 到计算机组将程序包全局发布到该组中的所有计算机。</span><span class="sxs-lookup"><span data-stu-id="7eea8-106">Entitling a package to a computer group publishes the package globally to all computers in the group.</span></span>

<span data-ttu-id="7eea8-107">使用以下过程配置对虚拟化程序包的访问权限。</span><span class="sxs-lookup"><span data-stu-id="7eea8-107">Use the following procedure to configure access to virtualized packages.</span></span>

**<span data-ttu-id="7eea8-108">授予对 app-v 5.1 程序包的访问权限</span><span class="sxs-lookup"><span data-stu-id="7eea8-108">To grant access to an App-V 5.1 package</span></span>**

1.  <span data-ttu-id="7eea8-109">查找要配置的程序包：</span><span class="sxs-lookup"><span data-stu-id="7eea8-109">Find the package you want to configure:</span></span>

    1.  <span data-ttu-id="7eea8-110">打开 app-v 5.1 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="7eea8-110">Open the App-V 5.1 Management console.</span></span>

    2.  <span data-ttu-id="7eea8-111">若要显示**广告访问**页面，请右键单击要配置的程序包，然后选择 "**编辑 active directory 访问**"。</span><span class="sxs-lookup"><span data-stu-id="7eea8-111">To display the **AD ACCESS** page, right-click the package to be configured, and select **Edit active directory access**.</span></span> <span data-ttu-id="7eea8-112">或者，选择程序包，然后单击 "**广告访问**" 窗格中的 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="7eea8-112">Alternatively, select the package and click **EDIT** in the **AD ACCESS** pane.</span></span>

2.  <span data-ttu-id="7eea8-113">为程序包预配安全组：</span><span class="sxs-lookup"><span data-stu-id="7eea8-113">Provision a security group for the package:</span></span>

    1.  <span data-ttu-id="7eea8-114">转到 "**查找有效的 ACTIVE DIRECTORY 名称" 和 "授予访问权限**" 页面。</span><span class="sxs-lookup"><span data-stu-id="7eea8-114">Go to the **FIND VALID ACTIVE DIRECTORY NAMES AND GRANT ACCESS** page.</span></span>

    2.  <span data-ttu-id="7eea8-115">使用 "设置**mydomain**  \\  名称 **" 格式**，键入 Active Directory 组对象的名称或部分名称，然后单击 "**检查**"。</span><span class="sxs-lookup"><span data-stu-id="7eea8-115">Using the format **mydomain** \\ **groupname**, type the name or part of the name of an Active Directory group object, and click **Check**.</span></span>

        <span data-ttu-id="7eea8-116">**注意** 确保为你要搜索的组提供相关联的域名。</span><span class="sxs-lookup"><span data-stu-id="7eea8-116">**Note** Ensure that you provide an associated domain name for the group that you are searching for.</span></span>

         

3.  <span data-ttu-id="7eea8-117">若要授予对程序包的访问权限，请选择所需的组，然后单击 "**授予访问权限**"。</span><span class="sxs-lookup"><span data-stu-id="7eea8-117">To grant access to the package, select the desired group and click **Grant Access**.</span></span> <span data-ttu-id="7eea8-118">新添加的组将显示在**具有 ACCESS 窗格的广告实体**中。</span><span class="sxs-lookup"><span data-stu-id="7eea8-118">The newly added group is displayed in the **AD ENTITIES WITH ACCESS** pane.</span></span>

4.  

    <span data-ttu-id="7eea8-119">若要接受默认配置设置并关闭**广告访问**页，请单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="7eea8-119">To accept the default configuration settings and close the **AD ACCESS** page, click **Close**.</span></span>

    <span data-ttu-id="7eea8-120">若要自定义特定组的配置，请单击 "**分配的配置**" 下拉列表，然后选择 "**自定义**"。</span><span class="sxs-lookup"><span data-stu-id="7eea8-120">To customize configurations for a specific group, click the **ASSIGNED CONFIGURATIONS** drop-down and select **Custom**.</span></span> <span data-ttu-id="7eea8-121">若要配置自定义配置，请单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="7eea8-121">To configure the custom configurations, click **EDIT**.</span></span> <span data-ttu-id="7eea8-122">授予访问权限后，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="7eea8-122">After you grant access, click **Close**.</span></span>

**<span data-ttu-id="7eea8-123">删除对 app-v 5.1 程序包的访问权限</span><span class="sxs-lookup"><span data-stu-id="7eea8-123">To remove access to an App-V 5.1 package</span></span>**

1.  <span data-ttu-id="7eea8-124">查找要配置的程序包：</span><span class="sxs-lookup"><span data-stu-id="7eea8-124">Find the package you want to configure:</span></span>

    1.  <span data-ttu-id="7eea8-125">打开 app-v 5.1 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="7eea8-125">Open the App-V 5.1 Management console.</span></span>

    2.  <span data-ttu-id="7eea8-126">若要显示**广告访问**页面，请右键单击要配置的程序包，然后选择 "**编辑 active directory 访问**"。</span><span class="sxs-lookup"><span data-stu-id="7eea8-126">To display the **AD ACCESS** page, right-click the package to be configured, and select **Edit active directory access**.</span></span> <span data-ttu-id="7eea8-127">或者，选择程序包，然后单击 "**广告访问**" 窗格中的 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="7eea8-127">Alternatively, select the package and click **EDIT** in the **AD ACCESS** pane.</span></span>

2.  <span data-ttu-id="7eea8-128">选择要删除的组，然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="7eea8-128">Select the group you want to remove, and click **DELETE**.</span></span>

3.  <span data-ttu-id="7eea8-129">若要关闭**广告访问**页面，请单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="7eea8-129">To close the **AD ACCESS** page, click **Close**.</span></span>

    <span data-ttu-id="7eea8-130">已**获得有关 app-v 的建议**？</span><span class="sxs-lookup"><span data-stu-id="7eea8-130">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="7eea8-131">在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="7eea8-131">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="7eea8-132">遇到了 app-v 问题？</span><span class="sxs-lookup"><span data-stu-id="7eea8-132">Got an App-V issue?</span></span>** <span data-ttu-id="7eea8-133">使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="7eea8-133">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="7eea8-134">相关主题</span><span class="sxs-lookup"><span data-stu-id="7eea8-134">Related topics</span></span>


[<span data-ttu-id="7eea8-135">App-V 5.1 的操作</span><span class="sxs-lookup"><span data-stu-id="7eea8-135">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

 

 





