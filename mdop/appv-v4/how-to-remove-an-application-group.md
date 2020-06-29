---
title: 如何删除应用程序组
description: 如何删除应用程序组
author: dansimp
ms.assetid: 3016b373-f5a0-4c82-96e8-e5e7960f0cc4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b392fe84f4318cf7f355de0c07e4d6f1f5108ed7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801155"
---
# <span data-ttu-id="ccc7b-103">如何删除应用程序组</span><span class="sxs-lookup"><span data-stu-id="ccc7b-103">How to Remove an Application Group</span></span>


<span data-ttu-id="ccc7b-104">可以通过以下两种方式之一使用以下过程在应用程序虚拟化服务器管理控制台中删除应用程序组：</span><span class="sxs-lookup"><span data-stu-id="ccc7b-104">You can use the following procedures to remove an application group in the Application Virtualization Server Management Console in one of two ways:</span></span>

<span data-ttu-id="ccc7b-105">**小心** 删除具有其应用程序的组将从应用程序虚拟化管理服务器中删除这些应用程序。</span><span class="sxs-lookup"><span data-stu-id="ccc7b-105">**Caution** Deleting a group with its applications deletes those applications from the Application Virtualization Management Server.</span></span> <span data-ttu-id="ccc7b-106">当您尝试执行此操作时，必须在弹出窗口中确认删除。</span><span class="sxs-lookup"><span data-stu-id="ccc7b-106">When you try to do this, you must confirm the deletion in a pop-up window.</span></span>

 

**<span data-ttu-id="ccc7b-107">清空并删除应用程序组</span><span class="sxs-lookup"><span data-stu-id="ccc7b-107">To empty and then delete an application group</span></span>**

1.  <span data-ttu-id="ccc7b-108">在应用程序虚拟化服务器管理控制台中，在左窗格中展开 "**应用**程序"，然后选择要删除的**应用程序**组。</span><span class="sxs-lookup"><span data-stu-id="ccc7b-108">In the Application Virtualization Server Management Console, expand **Applications** in the left pane and select the **Application** group you want to remove.</span></span>

2.  <span data-ttu-id="ccc7b-109">在右窗格中，选择要保留的应用程序和应用程序组。</span><span class="sxs-lookup"><span data-stu-id="ccc7b-109">In the right pane, select the applications and application groups you want to keep.</span></span> <span data-ttu-id="ccc7b-110">可以使用**CTRL**和**Shift**键选择多个应用程序和应用程序组。</span><span class="sxs-lookup"><span data-stu-id="ccc7b-110">You can use the **CTRL** and **Shift** keys to select multiple applications and application groups.</span></span>

3.  <span data-ttu-id="ccc7b-111">右键单击所选应用程序，然后选择 "**移动**"。</span><span class="sxs-lookup"><span data-stu-id="ccc7b-111">Right-click the selected applications, and choose **Move**.</span></span>

4.  <span data-ttu-id="ccc7b-112">在 "**选择目标**" 窗口中，导航到新位置，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="ccc7b-112">In the **Select Target** window, navigate to the new location and click **OK**.</span></span> <span data-ttu-id="ccc7b-113">如果要将不同的应用程序移动到多个组，请重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="ccc7b-113">Repeat this step if you want to move different applications to more than one group.</span></span>

5.  <span data-ttu-id="ccc7b-114">完成移动要保留的应用程序后，右键单击该应用程序组，然后选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="ccc7b-114">When you finish moving the applications you want to keep, right-click the application group and choose **Delete**.</span></span>

6.  <span data-ttu-id="ccc7b-115">单击 **"是"** 进行确认。</span><span class="sxs-lookup"><span data-stu-id="ccc7b-115">Click **Yes** to confirm.</span></span>

**<span data-ttu-id="ccc7b-116">删除组及其所有子组及其应用程序</span><span class="sxs-lookup"><span data-stu-id="ccc7b-116">To delete the group, with all its child groups and its applications</span></span>**

1.  <span data-ttu-id="ccc7b-117">在应用程序虚拟化服务器管理控制台中，在左窗格中展开 "**应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="ccc7b-117">In the Application Virtualization Server Management Console, expand **Applications** in the left pane.</span></span>

2.  <span data-ttu-id="ccc7b-118">右键单击要删除的应用程序组，然后选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="ccc7b-118">Right-click the application group you want to remove, and choose **Delete**.</span></span>

3.  <span data-ttu-id="ccc7b-119">单击 **"是"** 进行确认。</span><span class="sxs-lookup"><span data-stu-id="ccc7b-119">Click **Yes** to confirm.</span></span>

    <span data-ttu-id="ccc7b-120">**注意** 你可以同时选择和删除多个应用程序组。</span><span class="sxs-lookup"><span data-stu-id="ccc7b-120">**Note** You can select and remove multiple application groups simultaneously.</span></span> <span data-ttu-id="ccc7b-121">在右窗格中，使用**CTRL**-单击或**按住 Shift**单击组合键选择多个组。</span><span class="sxs-lookup"><span data-stu-id="ccc7b-121">In the right pane, use the **CTRL**-click or **Shift**-click key combinations to select more than one group.</span></span>

     

## <span data-ttu-id="ccc7b-122">相关主题</span><span class="sxs-lookup"><span data-stu-id="ccc7b-122">Related topics</span></span>


[<span data-ttu-id="ccc7b-123">如何在 Server Management Console 中管理应用程序组</span><span class="sxs-lookup"><span data-stu-id="ccc7b-123">How to Manage Application Groups in the Server Management Console</span></span>](how-to-manage-application-groups-in-the-server-management-console.md)

[<span data-ttu-id="ccc7b-124">如何在 Server Management Console 中管理应用程序</span><span class="sxs-lookup"><span data-stu-id="ccc7b-124">How to Manage Applications in the Server Management Console</span></span>](how-to-manage-applications-in-the-server-management-console.md)

 

 





