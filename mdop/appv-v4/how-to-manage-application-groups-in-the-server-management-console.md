---
title: 如何在 Server Management Console 中管理应用程序组
description: 如何在 Server Management Console 中管理应用程序组
author: dansimp
ms.assetid: 46997971-bdc8-4565-aefd-f47e90d6d7a6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 59a357d93ea63cc728f59a0633b7a5b9953aad14
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801323"
---
# <span data-ttu-id="c0934-103">如何在 Server Management Console 中管理应用程序组</span><span class="sxs-lookup"><span data-stu-id="c0934-103">How to Manage Application Groups in the Server Management Console</span></span>


<span data-ttu-id="c0934-104">你可以在应用程序虚拟化服务器管理控制台中的应用程序组中显示和管理一个或多个应用程序。</span><span class="sxs-lookup"><span data-stu-id="c0934-104">You can display and manage one or more applications in application groups in the Application Virtualization Server Management Console.</span></span> <span data-ttu-id="c0934-105">如果您要执行以下操作，这可能会很有用：</span><span class="sxs-lookup"><span data-stu-id="c0934-105">This can be useful when you want to do the following:</span></span>

-   <span data-ttu-id="c0934-106">将多个应用程序组织到更易于管理的子组中。</span><span class="sxs-lookup"><span data-stu-id="c0934-106">Organize many applications into more manageable subgroups.</span></span>

-   <span data-ttu-id="c0934-107">创建特定于某个部门或其他公司部门的应用程序组。</span><span class="sxs-lookup"><span data-stu-id="c0934-107">Create groups of applications specific to a department or other company division.</span></span>

-   <span data-ttu-id="c0934-108">组类似的应用程序，如金融软件。</span><span class="sxs-lookup"><span data-stu-id="c0934-108">Group similar types of applications, such as financial software.</span></span>

-   <span data-ttu-id="c0934-109">按组简化访问权限或许可证管理。</span><span class="sxs-lookup"><span data-stu-id="c0934-109">Simplify access permissions or license management by group.</span></span>

-   <span data-ttu-id="c0934-110">同时更改组中的应用程序和应用程序组的属性。</span><span class="sxs-lookup"><span data-stu-id="c0934-110">Change the properties of applications and application groups within a group simultaneously.</span></span>

<span data-ttu-id="c0934-111">你可以创建一个组，将其放在控制台**应用程序**树中的所需位置，然后将应用程序导入到该组。</span><span class="sxs-lookup"><span data-stu-id="c0934-111">You can create a group, place it where you would like in the console's **Applications** tree, and import applications to the group.</span></span> <span data-ttu-id="c0934-112">然后，你可以配置和管理组的属性，以影响其所有应用程序。</span><span class="sxs-lookup"><span data-stu-id="c0934-112">Then you can configure and manage the group's properties to affect all of its applications.</span></span> <span data-ttu-id="c0934-113">你还可以在组之间移动应用程序。</span><span class="sxs-lookup"><span data-stu-id="c0934-113">You can also move applications among groups.</span></span>

<span data-ttu-id="c0934-114">**注意** 将应用程序移动到组不会影响其文件（SFT、OSD 或 SPRJ）在服务器的文件系统上的位置。</span><span class="sxs-lookup"><span data-stu-id="c0934-114">**Note** Moving applications into groups does not affect the locations of their files (SFT, OSD, or SPRJ) on the server's file system.</span></span>

 

## <span data-ttu-id="c0934-115">本部分内容</span><span class="sxs-lookup"><span data-stu-id="c0934-115">In This Section</span></span>


<a href="" id="how-to-create-an-application-group"></a>[<span data-ttu-id="c0934-116">如何创建应用程序组</span><span class="sxs-lookup"><span data-stu-id="c0934-116">How to Create an Application Group</span></span>](how-to-create-an-application-group.md)  
<span data-ttu-id="c0934-117">提供创建应用程序组的分步说明。</span><span class="sxs-lookup"><span data-stu-id="c0934-117">Provides step-by-step instructions for creating an application group.</span></span>

<a href="" id="how-to-move-an-application-group"></a>[<span data-ttu-id="c0934-118">如何移动应用程序组</span><span class="sxs-lookup"><span data-stu-id="c0934-118">How to Move an Application Group</span></span>](how-to-move-an-application-group.md)  
<span data-ttu-id="c0934-119">提供移动应用程序组的分步说明。</span><span class="sxs-lookup"><span data-stu-id="c0934-119">Provides step-by-step instructions for moving an application group.</span></span>

<a href="" id="how-to-rename-an-application-group"></a>[<span data-ttu-id="c0934-120">如何重命名应用程序组</span><span class="sxs-lookup"><span data-stu-id="c0934-120">How to Rename an Application Group</span></span>](how-to-rename-an-application-group.md)  
<span data-ttu-id="c0934-121">提供重命名应用程序组的分步说明。</span><span class="sxs-lookup"><span data-stu-id="c0934-121">Provides step-by-step instructions for renaming an application group.</span></span>

<a href="" id="how-to-remove-an-application-group"></a>[<span data-ttu-id="c0934-122">如何删除应用程序组</span><span class="sxs-lookup"><span data-stu-id="c0934-122">How to Remove an Application Group</span></span>](how-to-remove-an-application-group.md)  
<span data-ttu-id="c0934-123">提供删除或删除应用程序组的分步说明。</span><span class="sxs-lookup"><span data-stu-id="c0934-123">Provides step-by-step instructions for removing or deleting an application group.</span></span>

## <span data-ttu-id="c0934-124">相关主题</span><span class="sxs-lookup"><span data-stu-id="c0934-124">Related topics</span></span>


[<span data-ttu-id="c0934-125">如何在 Server Management Console 中管理应用程序</span><span class="sxs-lookup"><span data-stu-id="c0934-125">How to Manage Applications in the Server Management Console</span></span>](how-to-manage-applications-in-the-server-management-console.md)

[<span data-ttu-id="c0934-126">如何在 Application Virtualization Server Management Console 中执行管理任务</span><span class="sxs-lookup"><span data-stu-id="c0934-126">How to Perform Administrative Tasks in the Application Virtualization Server Management Console</span></span>](how-to-perform-administrative-tasks-in-the-application-virtualization-server-management-console.md)

 

 





