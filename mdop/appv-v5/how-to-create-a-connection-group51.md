---
title: 如何创建连接组
description: 如何创建连接组
author: dansimp
ms.assetid: 221e2eed-7ebb-42e3-b3d6-11c37c0578e6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7f20b3e71c7c0b72d66700bbad945860112ffd03
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798519"
---
# <span data-ttu-id="ef1eb-103">如何创建连接组</span><span class="sxs-lookup"><span data-stu-id="ef1eb-103">How to Create a Connection Group</span></span>


<span data-ttu-id="ef1eb-104">使用以下步骤创建使用 App-v 管理控制台的连接组。</span><span class="sxs-lookup"><span data-stu-id="ef1eb-104">Use these steps to create a connection group by using the App-V Management Console.</span></span> <span data-ttu-id="ef1eb-105">若要使用 PowerShell 创建连接组，请参阅[如何使用 Powershell 管理独立计算机上的连接组](how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell51.md)。</span><span class="sxs-lookup"><span data-stu-id="ef1eb-105">To use PowerShell to create connection groups, see [How to Manage Connection Groups on a Stand-alone Computer by Using PowerShell](how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell51.md).</span></span>

<span data-ttu-id="ef1eb-106">将程序包放置在连接组中时，它们的程序包根路径将合并。</span><span class="sxs-lookup"><span data-stu-id="ef1eb-106">When you place packages in a connection group, their package root paths are merged.</span></span> <span data-ttu-id="ef1eb-107">如果删除程序包，则仅剩下剩余的程序包保留合并的根。</span><span class="sxs-lookup"><span data-stu-id="ef1eb-107">If you remove packages, only the remaining packages maintain the merged root.</span></span>

**<span data-ttu-id="ef1eb-108">创建连接组</span><span class="sxs-lookup"><span data-stu-id="ef1eb-108">To create a connection group</span></span>**

1.  <span data-ttu-id="ef1eb-109">在 App-v 5.1 管理控制台中，选择 "**连接组**" 以显示 "连接组" 库。</span><span class="sxs-lookup"><span data-stu-id="ef1eb-109">In the App-V 5.1 Management Console, select **CONNECTION GROUPS** to display the Connection Groups library.</span></span>

2.  <span data-ttu-id="ef1eb-110">选择 "**添加连接组**" 以创建新的连接组。</span><span class="sxs-lookup"><span data-stu-id="ef1eb-110">Select **ADD CONNECTION GROUP** to create a new connection group.</span></span>

3.  <span data-ttu-id="ef1eb-111">在 "**新建连接组**" 窗格中，键入组的说明。</span><span class="sxs-lookup"><span data-stu-id="ef1eb-111">In the **New Connection Group** pane, type a description for the group.</span></span>

4.  <span data-ttu-id="ef1eb-112">在 "**已连接的程序包**" 窗格中单击 "**编辑**"，将新应用程序添加到连接组。</span><span class="sxs-lookup"><span data-stu-id="ef1eb-112">Click **EDIT** in the **CONNECTED PACKAGES** pane to add a new application to the connection group.</span></span>

5.  <span data-ttu-id="ef1eb-113">在 "**打包整个库**" 窗格中，选择要添加的应用程序，然后单击箭头以添加应用程序。</span><span class="sxs-lookup"><span data-stu-id="ef1eb-113">In the **PACKAGES Entire Library** pane, select the application to be added, and click the arrow to add the application.</span></span>

    <span data-ttu-id="ef1eb-114">若要删除应用程序，请在 "**包**的" 窗格中选择要删除的应用程序，然后单击箭头。</span><span class="sxs-lookup"><span data-stu-id="ef1eb-114">To remove an application, select the application to be removed in the **PACKAGES IN** pane and click the arrow.</span></span>

    <span data-ttu-id="ef1eb-115">若要重新调整连接组中的应用程序，请使用 "**程序包的**" 窗格中的箭头。</span><span class="sxs-lookup"><span data-stu-id="ef1eb-115">To reprioritize the applications in your connection group, use the arrows in the **PACKAGES IN** pane.</span></span>

    <span data-ttu-id="ef1eb-116">**重要提示** 默认情况下，与特定应用程序相关联的 Active Directory 域服务访问配置不会添加到连接组。</span><span class="sxs-lookup"><span data-stu-id="ef1eb-116">**Important** By default, the Active Directory Domain Services access configurations that are associated with a specific application are not added to the connection group.</span></span> <span data-ttu-id="ef1eb-117">若要转移 Active Directory 访问配置，请选择 "**添加对组访问的程序包访问**"，它位于 "**程序包**" 窗格中。</span><span class="sxs-lookup"><span data-stu-id="ef1eb-117">To transfer the Active Directory access configuration, select **ADD PACKAGE ACCESS TO GROUP ACCESS**, which is located in the **PACKAGES IN** pane.</span></span>

     

6.  <span data-ttu-id="ef1eb-118">添加所有应用程序并配置 Active Directory 访问后，单击 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="ef1eb-118">After adding all the applications and configuring Active Directory access, click **Apply**.</span></span>

    <span data-ttu-id="ef1eb-119">已**获得有关 app-v 的建议**？</span><span class="sxs-lookup"><span data-stu-id="ef1eb-119">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="ef1eb-120">在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。</span><span class="sxs-lookup"><span data-stu-id="ef1eb-120">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="ef1eb-121">遇到了 app-v 问题？</span><span class="sxs-lookup"><span data-stu-id="ef1eb-121">Got an App-V issue?</span></span>** <span data-ttu-id="ef1eb-122">使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="ef1eb-122">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="ef1eb-123">相关主题</span><span class="sxs-lookup"><span data-stu-id="ef1eb-123">Related topics</span></span>


[<span data-ttu-id="ef1eb-124">App-V 5.1 的操作</span><span class="sxs-lookup"><span data-stu-id="ef1eb-124">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

[<span data-ttu-id="ef1eb-125">管理连接组</span><span class="sxs-lookup"><span data-stu-id="ef1eb-125">Managing Connection Groups</span></span>](managing-connection-groups51.md)

 

 





