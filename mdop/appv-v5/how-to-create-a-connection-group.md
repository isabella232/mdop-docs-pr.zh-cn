---
title: 如何创建连接组
description: 如何创建连接组
author: dansimp
ms.assetid: 9d272052-2d28-4e41-989c-89610482a0ca
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 816fc3b37be056ed54a88c394ef64fa1edaf47ee
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798521"
---
# <span data-ttu-id="8ef16-103">如何创建连接组</span><span class="sxs-lookup"><span data-stu-id="8ef16-103">How to Create a Connection Group</span></span>


<span data-ttu-id="8ef16-104">使用以下步骤创建使用 App-v 管理控制台的连接组。</span><span class="sxs-lookup"><span data-stu-id="8ef16-104">Use these steps to create a connection group by using the App-V Management Console.</span></span> <span data-ttu-id="8ef16-105">若要使用 PowerShell 创建连接组，请参阅[如何使用 Powershell 管理独立计算机上的连接组](how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="8ef16-105">To use PowerShell to create connection groups, see [How to Manage Connection Groups on a Stand-alone Computer by Using PowerShell](how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell.md).</span></span>

<span data-ttu-id="8ef16-106">将程序包放置在连接组中时，它们的程序包根路径将合并。</span><span class="sxs-lookup"><span data-stu-id="8ef16-106">When you place packages in a connection group, their package root paths are merged.</span></span> <span data-ttu-id="8ef16-107">如果删除程序包，则仅剩下剩余的程序包保留合并的根。</span><span class="sxs-lookup"><span data-stu-id="8ef16-107">If you remove packages, only the remaining packages maintain the merged root.</span></span>

**<span data-ttu-id="8ef16-108">创建连接组</span><span class="sxs-lookup"><span data-stu-id="8ef16-108">To create a connection group</span></span>**

1.  <span data-ttu-id="8ef16-109">在 App-v 5.0 管理控制台中，选择 "**程序包**"。</span><span class="sxs-lookup"><span data-stu-id="8ef16-109">In the App-V 5.0 Management Console, select **Packages**.</span></span>

2.  <span data-ttu-id="8ef16-110">选择 "**连接组**" 以显示 "连接组" 库。</span><span class="sxs-lookup"><span data-stu-id="8ef16-110">Select **CONNECTION GROUPS** to display the Connection Groups library.</span></span>

3.  <span data-ttu-id="8ef16-111">选择 "**添加连接组**" 以创建新的连接组。</span><span class="sxs-lookup"><span data-stu-id="8ef16-111">Select **ADD CONNECTION GROUP** to create a new connection group.</span></span>

4.  <span data-ttu-id="8ef16-112">在 "**新建连接组**" 窗格中，键入组的说明。</span><span class="sxs-lookup"><span data-stu-id="8ef16-112">In the **New Connection Group** pane, type a description for the group.</span></span>

5.  <span data-ttu-id="8ef16-113">在 "**已连接的程序包**" 窗格中单击 "**编辑**"，将新应用程序添加到连接组。</span><span class="sxs-lookup"><span data-stu-id="8ef16-113">Click **EDIT** in the **CONNECTED PACKAGES** pane to add a new application to the connection group.</span></span>

6.  <span data-ttu-id="8ef16-114">在 "**打包整个库**" 窗格中，选择要添加的应用程序，然后单击箭头以添加应用程序。</span><span class="sxs-lookup"><span data-stu-id="8ef16-114">In the **PACKAGES Entire Library** pane, select the application to be added, and click the arrow to add the application.</span></span>

    <span data-ttu-id="8ef16-115">若要删除应用程序，请在 "**包**的" 窗格中选择要删除的应用程序，然后单击箭头。</span><span class="sxs-lookup"><span data-stu-id="8ef16-115">To remove an application, select the application to be removed in the **PACKAGES IN** pane and click the arrow.</span></span>

    <span data-ttu-id="8ef16-116">若要重新调整连接组中的应用程序，请使用 "**程序包的**" 窗格中的箭头。</span><span class="sxs-lookup"><span data-stu-id="8ef16-116">To reprioritize the applications in your connection group, use the arrows in the **PACKAGES IN** pane.</span></span>

    <span data-ttu-id="8ef16-117">**重要提示** 默认情况下，与特定应用程序相关联的 Active Directory 域服务访问配置不会添加到连接组。</span><span class="sxs-lookup"><span data-stu-id="8ef16-117">**Important** By default, the Active Directory Domain Services access configurations that are associated with a specific application are not added to the connection group.</span></span> <span data-ttu-id="8ef16-118">若要转移 Active Directory 访问配置，请选择 "**添加对组访问的程序包访问**"，它位于 "**程序包**" 窗格中。</span><span class="sxs-lookup"><span data-stu-id="8ef16-118">To transfer the Active Directory access configuration, select **ADD PACKAGE ACCESS TO GROUP ACCESS**, which is located in the **PACKAGES IN** pane.</span></span>

     

7.  <span data-ttu-id="8ef16-119">添加所有应用程序并配置 Active Directory 访问后，单击 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="8ef16-119">After adding all the applications and configuring Active Directory access, click **Apply**.</span></span>

    <span data-ttu-id="8ef16-120">已**获得有关 app-v 的建议**？</span><span class="sxs-lookup"><span data-stu-id="8ef16-120">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="8ef16-121">在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="8ef16-121">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="8ef16-122">遇到了 app-v 问题？</span><span class="sxs-lookup"><span data-stu-id="8ef16-122">Got an App-V issue?</span></span>** <span data-ttu-id="8ef16-123">使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="8ef16-123">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="8ef16-124">相关主题</span><span class="sxs-lookup"><span data-stu-id="8ef16-124">Related topics</span></span>


[<span data-ttu-id="8ef16-125">App-V 5.0 的操作</span><span class="sxs-lookup"><span data-stu-id="8ef16-125">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

[<span data-ttu-id="8ef16-126">管理连接组</span><span class="sxs-lookup"><span data-stu-id="8ef16-126">Managing Connection Groups</span></span>](managing-connection-groups.md)

 

 





